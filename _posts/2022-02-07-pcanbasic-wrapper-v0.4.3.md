---
layout: single
title:  "PCANBasic-Wrapper - Version 0.4.3 released"
tag: PCANBasic-Wrapper
categories: Change-log Wrapper Windows Peak PCANBasic
artifacts: https://github.com/uv-software/PCANBasic-Wrapper/releases/tag/v0.4.3
release: Version 0.4.3 (Commit 7ffb5a3 of February 7, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated CAN API sources to rev. 1036
- Fixed a bug with message flag `sts` on reception
- Fixed a bug with getting properties from device
- Changed resolution of property `GET_BUSLOAD`
- Implemented device property `GET_CAN_CHANNEL`
- Added a check for minimum required PCANBasic DLL version (4.5 or later)
- Added two operations to class `CPeakCAN` to query channel information
- Updated the utilities to get the list of CAN channels from the library
