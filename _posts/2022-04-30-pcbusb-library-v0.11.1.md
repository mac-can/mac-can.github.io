---
layout: single
title:  "PCBUSB-Library - Version 0.11.1 released"
tag: PCBUSB-Library
categories: Change-log Drivers macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.11.1
release: Version 0.11.1 (Build 1183 of April 30, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Built library as Universal macOS Binary ([macOS_Library_for_PCANUSB_v0.11.1.tar.gz](https://github.com/mac-can/PCBUSB-Library/releases/download/v0.11.1/macOS_Library_for_PCANUSB_v0.11.1.tar.gz)).
- Built library for x86_64 architecture ([OS_X_Library_for_PCANUSB_v0.11.1.tar.gz](https://github.com/mac-can/PCBUSB-Library/releases/download/v0.11.1/OS_X_Library_for_PCANUSB_v0.11.1.tar.gz)).
- Fixed the Monterey issue [#6](https://github.com/mac-can/PCBUSB-Library/issues/6) ('Driver not loaded').
- Fixed some findings from static code analysis.
- Added `@rpath` to **all** build environments.
- Improved the installation script.
- Updated the README file.
