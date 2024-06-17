---
layout: single
title:  "SerialCAN - Version 0.2 released"
tag: SerialCAN
categories: Change-log Serial macOS Linux Cygwin Windows Lawicel SLCAN
artifacts: https://github.com/mac-can/SerialCAN/releases/tag/v0.2
release: Version 0.2 (Commit a1d9719 of June 17, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Update CAN API V3 sources to rev. 1312 
- **Implemented acceptance filtering**
- Removed upper size limit of string properties
- Reworked CAN API V3 return values (**C** vs. **C++**)
- Optimized CAN API V3 wrapper (`can_api.c`)
- Fixed a bug with `can_status` if not running (cf. issue [#17](https://github.com/mac-can/SerialCAN/issues/17))  
- Moved `SerialCAN_Defines.h` to CAN API V3 sources 
- Added an Xcode test target to the Trial program 
- Updated `Makefile`s and MSC project 
