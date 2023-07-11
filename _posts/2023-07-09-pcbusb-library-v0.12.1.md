---
layout: single
title:  "PCBUSB-Library - Version 0.12.1 released"
tag: PCBUSB-Library
categories: Change-log Drivers macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.12.1
release: Version 0.12.1 (Build 1678 of July 9, 2023)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- fixed a bug with endianess of 32-bit device id. (issue #384: PCAN-USB [Pro] FD)
- reworked return values of CAN_Read(), CAN_ReadFD(), CAN_Write(), CAN_WriteFD()
- reset USB pipe #4 after write timed out (CAN Write stalled; macOS 11 and higher)
- build the library as Universal macOS Binary: [macOS_Library_for_PCANUSB_v0.12.1.tar.gz](https://github.com/mac-can/PCBUSB-Library/releases/download/v0.12.1/macOS_Library_for_PCANUSB_v0.12.1.tar.gz)
- build the library for Intel x86_64 architecture: [OS_X_Library_for_PCANUSB_v0.12.1.tar.gz](https://github.com/mac-can/PCBUSB-Library/releases/download/v0.12.1/OS_X_Library_for_PCANUSB_v0.12.1.tar.gz)