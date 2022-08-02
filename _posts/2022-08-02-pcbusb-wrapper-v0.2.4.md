---
layout: single
title:  "PCBUSB-Wrapper - Version 0.2.4 released"
tag: PCBUSB-Wrapper
categories: Change-log Wrapper macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Wrapper/releases/tag/v0.2.4
release: Version 0.2.4 (Commit 24603cc of August 2, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated CAN API V3 sources to SVN rev. 1082
- Updated CAN API V3 Testing sources to SVN rev. 1084
- Fixed a bug with transceiver off in `can_reset`
- Fixed a bug with BTR0BTR1 register in CAN FD mode
- Fixed a bug with mapping CAN FD bit-rate to Peak string
- Updated class `CPeakCAN` (some property values)
- Updated the trial program
- Updated the Python wrapper
- Updated the utilities

Tested with [PCBUSB-Library](https://github.com/mac-can/PCBUSB-Library) version [0.11.2](https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.11.2)
