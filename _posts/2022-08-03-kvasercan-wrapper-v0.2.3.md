---
layout: single
title:  "KvaserCAN-Wrapper - Version 0.2.3 released"
tag: KvaserCAN-Wrapper
categories: Change-log Wrapper Windows Kvaser CANLib32
artifacts: https://github.com/uv-software/KvaserCAN-Wrapper/releases/tag/v0.2.3
release: Version 0.2.3 (Commit e5504dc August 3, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated Kvaser canLib DLL (version 5.39)
- Updated CAN API V3 sources to rev. 1082
- Fixed a bug with transceiver off in function `can_reset`
- Fixed a bug with field `SAM` in BTR0BTR1 register
- Fixed a bug with Kvaser CAN bus params (`noSamp`)
- Updated class `CKvaserCAN` (some property keys)
- Updated the trial program
- Updated the utilities
