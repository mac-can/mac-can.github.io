---
layout: single
title:  "PCBUSB-Wrapper - Version 0.2 released"
tag: PCBUSB-Wrapper
categories: Change-log Wrapper macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Wrapper/releases/tag/v0.2
release: Version 0.2 (Commit 0354cb4 of February 7, 2021)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Applied changes from CAN API V3 specification (rev. 925 to 987)
- Added C++ class `CPeakCAN` derived from abstract class `CCANAPI`
- Reworked the trial program (it is now based on class `CPeakCAN`)
- Reorganized the entire folder structure of the repository
- Added my beloved CAN utilities `can_moni` and `can_test`
- Added two simple C++ examples for sending and receiving CAN frames
- Added a Python wrapper and two Python examples
- Added a Doxygen configuration
