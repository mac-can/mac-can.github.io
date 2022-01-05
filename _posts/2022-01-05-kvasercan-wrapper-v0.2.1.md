---
layout: single
title:  "KvaserCAN-Wrapper - Version 0.2.1 released"
tag: KvaserCAN-Wrapper
categories: Change-log Wrapper Windows Kvaser CANLib32
artifacts: https://github.com/uv-software/KvaserCAN-Wrapper/releases/tag/v0.2.1
release: Version 0.2.1 (Commit c4bb537 of January 5, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated Kvaser canLib DLL (version 5.37)
- Updated CAN API sources to rev. 1020 and applied the changes
- Resolved firmware version vs. software version confusion
- Fixed some bugs with getting properties from device and from library:
  - accept NULL pointer for `SET_FIRST_CHANNEL` and `SET_NEXT_CHANNEL`
  - getting device properties requires a valid handle
  - string values must be at least one byte in size
- Fixed a bug with missing length for property `CANPROP_GET_DEVICE_NAME`
- Fixed a possible build issue with outdated define `CAN_20_ONLY`
- Updated Python examples (although they do not work under Windows)
- Updated my beloved utilities
