---
layout: single
title:  "PCBUSB-Utilities - Version 0.5.6 released"
tag: PCBUSB-Utilities
categories: Change-log Utilities macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Utilities/releases/tag/v0.5.6
release: Version 0.5 SR6 (Build 1679 of February 2, 2023)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Display device id. when listing available CAN interfaces (option `-T`).
- Fixed a bug with default CAN FD bit-rate settings (**250kbps:2Mbps**).
- Compiled against [PCBUSB-Library](https://github.com/mac-can/PCBUSB-Library) [v0.12](https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.12) sources as Universal macOS Binary (requires macOS 11.x or higher)
