---
layout: single
title:  "PCBUSB-Wrapper - Version 0.2.6 released"
tag: PCBUSB-Wrapper
categories: Change-log Wrapper macOS Linux Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Wrapper/releases/tag/v0.2.6
release: Version 0.2.6 (Commit e088ff of September 21, 2023)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated CAN API V3 testing sources to rev. 1201
- Updated CAN API V3 sources to rev. 1187 and applied the changes
  - Fixed a small bug in `btr_compare_bitrates` 
  - Reworked formatting of message flags
- Reworked handling of receive queue empty
- Fixed a possible string truncation
- Made the utilities more generic
- Updated the examples
- Linux support
