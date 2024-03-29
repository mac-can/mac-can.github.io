---
layout: single
title:  "PCBUSB-Library - Version 0.10.1 released"
tag: PCBUSB-Library
categories: Change-log Drivers macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.10.1
release: Version 0.10.1 (Build 1016 of December 6, 2021)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Built the library as Universal macOS Binary ([macOS_Library_for_PCANUSB_v0.10.1.tar.gz](https://github.com/mac-can/PCBUSB-Library/releases/download/v0.10.1/macOS_Library_for_PCANUSB_v0.10.1.tar.gz)).
- Built the library for x86_64 architecture ([OS_X_Library_for_PCANUSB_v0.10.1.tar.gz](https://github.com/mac-can/PCBUSB-Library/releases/download/v0.10.1/OS_X_Library_for_PCANUSB_v0.10.1.tar.gz)).
- Parameter `PCAN_CHANNEL_VERSION` displays machine architecture from `utsname()`.
- Fixed a bug with parameter `PCAN_EXT_HARDWARE_VERSION` for PCAN-USB Pro FD devices.
- Solved an issue with file system relative paths that are not allowed in hardened programs in Python 2.7 under macOS.
- Updated the C++ examples: Blocking Read using system call `select()`.
