---
layout: single
title:  "KvaserCAN-Wrapper - Version 0.3 released"
tag: KvaserCAN-Wrapper
categories: Change-log Wrapper Windows Kvaser CANLib32
artifacts: https://github.com/uv-software/KvaserCAN-Wrapper/releases/tag/v0.3
release: Version 0.3 (Commit 1fe917a of April 24, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Added an unified version file
- Recreated the library projects
- Updated all MSBuild environments
- Updated Kvaser canLib DLL (version 5.44)
- Updated CAN API V3 sources to rev. 1270
- Updated CAN API V3 testing sources to rev. 1273
- Changed the resolution of `CTimer` to 64 bit
- Implemented identifier acceptance filtering
- Added test suites for acceptance filtering
- Added filtering option to utility `can_moni`
- Added option `/LIST-BITRATES` to the utilities
- Implemented Kvaser-specific properties
- Fixed a bug with flag `ESI` in TC05.20
- Fixed a bug with Kvaser vs. CiA bit-rate settings
- Fixed compiler warnings with legacy CAN 2.0 frame format
- Updated the Python wrapper
- Updated the examples
