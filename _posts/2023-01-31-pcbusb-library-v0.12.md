---
layout: single
title:  "PCBUSB-Library - Version 0.12 released"
tag: PCBUSB-Library
categories: Change-log Drivers macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.12
release: Version 0.12 (Build 1668 of January 31, 2023)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Realized setting of device id. for PCAN-USB FD devices
- Reworked status frame handling:
  - fixed some bugs in the driver layer (all device types)
  - suppressed initial CAN FD status frame in CAN 2.0 mode
  - corrected mapping of bus error states to PCAN status
  - fixed a bug with CAN id. of status messages
  - `CAN_Read()`, `CAN_ReadFD()`, `CAN_Write()`, `CAN_WriteFD()`: return bus error states
- `SetValue()`: Set default value if argument '`BufferLength`' is equal to 0:
  - `PCAN_LISTEN_ONLY` (default = OFF)
  - `PCAN_DEVICE_ID` (default = 0)
  - `PCAN_TRACE_LOCATION` (default = cwd)
  - `PCAN_TRACE_STATUS` (default = OFF)
  - `PCAN_TRACE_SIZE` (default 0 = 100k frames!)
  - `PCAN_TRACE_CONFIGURE` (default = SINGLE_FILE)
- `GetValue()`: Implemented missing parameters:
  - `PCAN_ALLOW_RTR_FRAMES` (read-only!)
  - `PCAN_ALLOW_STATUS_FRAMES` (read-only!)
  - `PCAN_ALLOW_ERROR_FRAMES` (read-only!)
  - `PCAN_CONTROLLER_NUMBER` (read-only)
  - `PCAN_DEVICE_PART_NUMBER` (read-only)
- Made `GetValue(PCAN_RECEIVE_EVENT)` more robust if argument is greater than size of `int`
- Reading of additional bytes from firmware info packet to distinguish product variants \
  (issue [#11](https://github.com/mac-can/PCBUSB-Library/issues/11): PCAN-USB FD (IPEH-004022) cannot be initialized)
- Fixed a bug with **stuck in** `CAN_Write()` when errors on bus \
  (note: the solution only works on macOS 11.0 and newer)
- Fixed a bug with status frames not triggering the pipe for blocking read
- Fixed a bug with getting the firmware version from USB device name \
  (note: since firmware 3.x the version is not encoded in the device name anymore)
- Fixed a bug with string length for bit-rate strings
- Fixed a bug with `GetValue(BITRATE_INFO_FD)` w/o BRSE
- Fixed a bug with size of parameter `PCAN_TRACE_SIZE`
- Fixed some findings from static code analysis (Xcode and cppcheck)

Artifacts:
- Library as Universal macOS Binary ([macOS_Library_for_PCANUSB_v0.12.tar.gz](https://github.com/mac-can/PCBUSB-Library/releases/download/v0.12/macOS_Library_for_PCANUSB_v0.12.tar.gz))
- Library for x86_64 architecture ([OS_X_Library_for_PCANUSB_v0.12.tar.gz](https://github.com/mac-can/PCBUSB-Library/releases/download/v0.12/OS_X_Library_for_PCANUSB_v0.12.tar.gz))

