---
layout: single
title:  "KvaserCAN-Wrapper - Version 0.2.2 released"
tag: KvaserCAN-Wrapper
categories: Change-log Wrapper Windows Kvaser CANLib32
artifacts: https://github.com/uv-software/KvaserCAN-Wrapper/releases/tag/v0.2.2
release: Version 0.2.2 (Commit 4971c3f of February 8, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated CAN API sources to rev. 1036
- Fixed a bug with message flag `sts` on reception
- Fixed a bug with getting properties from device
- Fixed a bug with state of virtual CAN channels
- Changed resolution of property `GET_BUSLOAD`
- Added two operations to class `CPeakCAN` to query channel information
- Updated the utilities to get the list of channels from the library
