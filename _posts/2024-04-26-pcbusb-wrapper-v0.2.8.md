---
layout: single
title:  "PCBUSB-Wrapper - Version 0.2.8 released"
tag: PCBUSB-Wrapper
categories: Change-log Wrapper macOS Linux Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Wrapper/releases/tag/v0.2.8
release: Version 0.2.8 (Commit 4b57e39 of April 26, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Added common `Version.h` to the project
- Updated CAN API V3 sources to rev. 1270
- Updated CAN API V3 testing sources to rev. 1273
- Removed unused attributes from class `CPeakCAN` 
- Changed the resolution of `CTimer` to 64 bit
- Added option `--list-bitrates` to the utilities
- Updated `Makefile`s and `build_no.sh`
- Improved compiler and linker flags 
- Updated the Python wrapper
- Updated the examples 
- Updated the deployment rules
