---
layout: single
title:  "PCBUSB-Utilities - Version 0.6 released"
tag: PCBUSB-Utilities
categories: Change-log Utilities macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Utilities/releases/tag/v0.6
release: Version 0.5 SR8 (Build 1986 of July 29, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- realized new program options:
  - `--no-status-frames`  suppress reception of status frames (default=`ON`)
  - `--no-remote-frames`  suppress reception of remote frames (default=`ON`)
  - `--code=`&lt;id&gt;       acceptance code for 11-bit IDs (default=`0x000`)
  - `--mask=`&lt;id&gt;       acceptance mask for 11-bit IDs (default=`0x7FF`)
  - `--xtd-code=`&lt;id&gt;   acceptance code for 29-bit IDs (default=`0x00000000`)
  - `--xtd-mask=`&lt;id&gt;   acceptance mask for 29-bit IDs (default=`0x1FFFFFFF`)
  - `--trace=`(`ON`|`OFF)`    write a trace file (default=`OFF`)
- compiled against [PCBUSB](https://github.com/mac-can/PCBUSB-Library) [v0.13](https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.13) sources as Universal macOS Binary
