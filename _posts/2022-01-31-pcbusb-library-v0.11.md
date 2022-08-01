---
layout: single
title:  "PCBUSB-Library - Version 0.11 released"
tag: PCBUSB-Library
categories: Change-log Drivers macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.11
release: Version 0.11 (Build 1143 of January 31, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Built the library as Universal macOS Binary ([macOS_Library_for_PCANUSB_v0.11.tar.gz](https://github.com/mac-can/PCBUSB-Library/releases/download/v0.11/macOS_Library_for_PCANUSB_v0.11.tar.gz)).
- Built the library for x86_64 architecture ([OS_X_Library_for_PCANUSB_v0.11.tar.gz](https://github.com/mac-can/PCBUSB-Library/releases/download/v0.11/OS_X_Library_for_PCANUSB_v0.11.tar.gz)).
- Synchronized PCBUSB header with PCANBasic header for v4.6.0.
- Fixed a bug with `PCAN_CHANNEL_CONDITION` when used by another process.
- Fixed an omission with export declaration for `CAN_LookUpChannel`.
- Implemented parameter `PCAN_FIRMWARE_VERSION` (read-only).
- Added error text for `PCAN_ERROR_ILLMODE` (all languages).
- Corrected some French error text (acc. to Peak´s changes).
- Return `PCAN_ERROR_HWINUSE` when interface is used by another process:[^footnote]
  - `CAN_GetValue`: `PCAN_LISTEN_ONLY, PCAN_RECEIVE_STATUS, PCAN_LISTEN_ONLY`
- Return `PCAN_ERROR_ILLCLIENT` if an invalid channel handle is given:[^footnote]
  - `CAN_GetValue`: `PCAN_RECEIVE_EVENT, PCAN_CHANNEL_CONDITION, PCAN_TRACE_LOCATION, PCAN_TRACE_STATUS, PCAN_TRACE_SIZE, PCAN_TRACE_CONFIGURE, PCAN_BITRATE_INFO, PCAN_BITRATE_INFO_FD, PCAN_BUSSPEED_NOMINAL, PCAN_BUSSPEED_DATA, PCAN_FIRMWARE_VERSION`
  - `CAN_SetValue`: `PCAN_DEVICE_ID, PCAN_TRACE_LOCATION, PCAN_TRACE_STATUS, PCAN_TRACE_SIZE, PCAN_TRACE_CONFIGURE`
  - `CAN_Reset`
  - `CAN_GetStatus`
  - `CAN_Read`
  - `CAN_ReadFD`
  - `CAN_Write`
  - `CAN_WriteFD`
- Added `@rpath` to the build environment (it got lost for some releases).
- Code signed the Universal macOS Binary (Apple Development certificate).

[^footnote]: Peak-System harmonized its return codes in PCANBasic DLL version 4.6.0. Now the return codes matches my expectation.
