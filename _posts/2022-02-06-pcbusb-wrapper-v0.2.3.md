---
layout: single
title:  "PCBUSB-Wrapper - Version 0.2.3 released"
tag: PCBUSB-Wrapper
categories: Change-log Wrapper macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Wrapper/releases/tag/v0.2.3
release: Version 0.2.3 (Commit d2e9369 of February 6, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated CAN API sources to rev. 1036
- Fixed a bug with property GET_DEVICE_TYPE (re-renamed property `GET_DEVICE_CHANNEL` into `GET_DEVICE_TYPE` to display the device type as specified instead of the channel no of the device)
- Fixed a bug with reading property `GET_DEVICE_VENDOR` and `GET_DEVICE_DLLNAME` (they can also be read without a handle)
- Fixed a bug with message flag `sts` on reception
- Added operations `GetFirstChannel` and `GetNextChannel` to class `CPeakCAN` to query channel information
- Updated the utilities to get the list of channels from the library (like `can_boards[]` in C interface)
