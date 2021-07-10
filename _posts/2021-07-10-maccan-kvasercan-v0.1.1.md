---
layout: single
title:  "MacCAN-KvaserCAN - Version 0.1.1 released"
tag: MacCAN-KvaserCAN
categories: Change-log Drivers macOS Kvaser
artifacts: https://github.com/mac-can/MacCAN-KvaserCAN/releases/tag/v0.1.1
project: /drivers/KvaserCAN/
release: Version 0.1 SR1 (Commit 7f6274f of July 10, 2021)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Add a CAN API V3 compatible Swift wrapper and two Swift examples
- Add Swift Package Manager (SPM) configuration and test template
- Move CAN API wrapper code from C++ class to C interface (`can_api.c`)
- Add abstract class `CCanApi` (as replacement for class `CMacCAN`)
- Fix a bug with checking for valid handle in function `can_init`
- Fix a bug with uncleared receive queue after re-start
- Fix a bug when teardown all channels (`CANEXIT_ALL`)
- Fix a bug with reading device independent properties
- Fix some bugs with getting properties from device and from library:
  - accept NULL pointer for SET_FIRST_CHANNEL and SET_NEXT_CHANNEL
  - getting device properties requires a valid handle
  - string values must be at least one byte in size
- Temporary fix for investigation of issue #5
