---
layout: single
title:  "MacCAN-KvaserCAN - Version 0.2 released"
tag: MacCAN-KvaserCAN
categories: Change-log Drivers macOS Kvaser
artifacts: https://github.com/mac-can/MacCAN-KvaserCAN/releases/tag/v0.2
project: /drivers/KvaserCAN/
release: Version 0.2 (Commit 18b198f of February 11, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Implemented **CAN FD operation mode** for Leaf Pro devices
- Implemented properties `NUM_CHANNELS`, `CAN_CHANNEL`, `QUEUE_OVFL`, `QUEUE_SIZE` and `QUEUE_HIGH`
- MacCAN-Core changes:
  - Updated MacCAN-Core sources to rev. 1090
  - Removed class `CMacCAN` from project
  - Replaced CAN API error codes by MacCAN error codes
  - Fixed a bug with forgotten NULL pointer check in `CANUSB_ReadPipe`
  - Fixed a bug with calculation of queue high counter
- CAN API V3 changes:
  - Updated CAN API sources to rev. 1036 and applied latest changes
  - Fixed a bug with probing a device when it is used by another process
  - Fixed a bug with CAN FD operation dependent mode flags
  - Fixed some omissions with handling of device properties
  - Fixed a bug with property `GET_DEVICE_TYPE`
  - Fixed a bug with Swift property `deviceInfo`
  - Fixed a bug with device vendor instead of library vendor
  - Added operations to class `CCanApi` to query channel information
  - Updated the utilities to get the list of channels from library
  - Updated the Swift wrapper and examples
- Testing changes:
  - Updated CAN API Testing sources to rev. 1086
  - Changed template concept for CAN API Testing
  - Moved CAN API Testing sources to `$(PROJROOT)/Tests/UnitTests`
  - Replaced test suite for `can_software` by `can_firmware`
  - Reworked test suite for function `can_property`
  - Implemented a test case to measure time-stamp accuracy
  - Add a workaround to TC11.10 for Kvaser bus parameters
- Set deployment target to macOS 11.0
- Updated the Travis CI configuration (`osx_image: xcode12.5`)
- Updated the `Makefile`s to build the artifacts as *Universal macOS Binary*
- Updated `README.md` (**"Running CAN and CAN FD on Mac"**)
