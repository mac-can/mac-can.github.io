---
layout: single
title:  "PCBUSB-Utilities - Version 0.6.2 released"
tag: PCBUSB-Utilities
categories: Change-log Utilities macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Utilities/releases/tag/v0.6.2
release: Version 0.6 SR2 (Build 2065 of March 1, 2025)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- realized new program options:
  - `--code=<id>` acceptance code for 11-bit IDs (default=0x000)
  - `--mask=<id>` acceptance mask for 11-bit IDs (default=0x7FF)
  - `--xtd-code=<id>` acceptance code for 29-bit IDs (default=0x00000000)
  - `--xtd-mask=<id>` acceptance mask for 29-bit IDs (default=0x1FFFFFFF)
- compiled against PCBUSB v0.13 sources as Universal macOS Binary