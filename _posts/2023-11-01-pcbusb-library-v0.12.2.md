---
layout: single
title:  "PCBUSB-Library - Version 0.12.2 released"
tag: PCBUSB-Library
categories: Change-log Drivers macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.12.2
release: Version 0.12.2 (Build 1856 of November 1, 2023)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- synchronized PCBUSB header with PCANBasic header from PEAK's version 4.8.0
- fixed a bug with pipe numbers for PCAN-USB FD devices (hardware version 6.0)
- added missing linker option '-rpath /usr/local/lib' to the C++ examples
- updated the README file (unsupported parameter PCAN_HARD_RESET_STATUS)
- build the library as Universal macOS Binary: [macOS_Library_for_PCANUSB_v0.12.2.tar.gz](https://github.com/mac-can/PCBUSB-Library/releases/download/v0.12.2/macOS_Library_for_PCANUSB_v0.12.2.tar.gz)
- build the library for Intel x86_64 architecture: [OS_X_Library_for_PCANUSB_v0.12.2.tar.gz](https://github.com/mac-can/PCBUSB-Library/releases/download/v0.12.2/OS_X_Library_for_PCANUSB_v0.12.2.tar.gz)