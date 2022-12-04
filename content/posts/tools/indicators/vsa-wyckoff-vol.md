---
title: "VSA Wyckoff Volume"
date: 2022-12-04T16:17:18+04:00
draft: false
---

## Source Code

```
//@version=4
study(title="VSA Wyckoff Volume", shorttitle="VSA Wyckoff Volume", format=format.volume, resolution="")

showMA =                input(defval=false,  title="Show Volume Moving Average")
lengthVolumeMA =        input(defval=20,    title="Length of MA applied on Volume",     type=input.integer)
ratioUltraVolume =      input(defval=2.2,   title="Ultra High Volume Ratio",            type=input.float)
ratioVeryHighVolume =   input(defval=1.8,   title="Very High Volume Ratio",             type=input.float)
ratioHighVolume =       input(defval=1.2,   title="High Volume Ratio",                  type=input.float)
ratioNormalVolume =     input(defval=0.8,   title="Normal Volume Ratio",                type=input.float)
ratioLowVolume =        input(defval=0.4,   title="Low Volume Ratio",                   type=input.float)
ratioVeryLowVolume =    input(defval=0.4,   title="Very Low Volume Ratio",              type=input.float)

// WILDERS MA
float volumeMA  = 0
volumeMA := nz(volumeMA[1]) + (volume-nz(volumeMA[1])) / lengthVolumeMA

ultraHighVolumeMin   = volumeMA * ratioUltraVolume
veryHighVolumeMin    = volumeMA * ratioVeryHighVolume
highVolumeMin        = volumeMA * ratioHighVolume
normalVolumeMin      = volumeMA * ratioNormalVolume
lowVolumeMin         = volumeMA * ratioLowVolume
veryLowVolumeMin     = volumeMA * ratioVeryLowVolume

volUltraHigh        = volume >= ultraHighVolumeMin                                      ? true : false
volVeryHigh         = volume >= veryHighVolumeMin   and volume < ultraHighVolumeMin     ? true : false
volHigh             = volume >= highVolumeMin       and volume < veryHighVolumeMin      ? true : false
volNormal           = volume >= normalVolumeMin     and volume < highVolumeMin          ? true : false
volLow              = volume >= lowVolumeMin        and volume < normalVolumeMin        ? true : false
volVeryLow          = volume < lowVolumeMin                                             ? true : false

palette = volUltraHigh ? color.purple : volVeryHigh ? color.red : volHigh ? color.orange : volNormal ? color.green : volLow ? color.blue : color.silver
plot(volume, color = palette, style=plot.style_columns, title="Volume", transp=0)
plot(showMA ? volumeMA : na, style=plot.style_line, color=color.green, title="Volume MA")
```
