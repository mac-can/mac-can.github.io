---
layout: single
title:  "PCBUSB-Library - Version 0.9 released"
tag: PCBUSB-Library
categories: Change-log Drivers macOS Peak PCBUSB
artifacts: https://www.uv-software.de/dokuwiki/doku.php?id=uvs:programs:pcbusb_library
release: Version 0.9 (Build 902 of June 25, 2020)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Data types from `<MacTypes.h>` as replacement for Peak´s usage of Windows `BYTE`, `WORD`, `DWORD` and `UINT64` (field CAN ID is now 32-bit wide)
- Synchronized the API to Peak´s PCANBasic version 4.4.0.288
- Parameter `PCAN_DEVICE_ID` can be read in pre-initialization state
- Fixed some bugs with status bit: `PCAN_ERROR_QXMTFULL`, `PCAN_ERROR_XMTFULL`, `PCAN_ERROR_QOVERRUN`, `PCAN_ERROR_BUSLIGHT`
- Added a delay of 1 &mu;sec in `CAN_Write` to run on macOS 10.15 (Catalina)
