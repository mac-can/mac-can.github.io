---
layout: single
title:  "PCANBasic-Wrapper - Version 0.6 released"
tag: PCANBasic-Wrapper
categories: Change-log Wrapper Windows Peak PCANBasic
artifacts: https://github.com/uv-software/PCANBasic-Wrapper/releases/tag/v0.6
release: Version 0.6 (Commit 906a2ce of February 28, 2025)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated PCANBasic DLL to v4.10.0 (964)
- Updated CAN API V3 sources to rev. 1467
  - Added an ASCII parser for CAN messages*
  - Added property `PEAKCAN_PROPERTY_DEVICE_GUID`**
- Updated GoogleTest framework to v1.15.2
- Updated CAN API V3 testing to rev. 1412
  - Few plastic surgeries
- Updated CAN API V3 utilities to rev. 1481
  - Added new utility `can_send`
  - Optimized commandline argument handling
- Updated Python wrapper to v0.3.2
- Updated C++ examples

_*) The syntax is taken from SocketCAN utility [can-utils/cansend](https://github.com/linux-can/can-utils/tree/master)_ \
_**) But it doesn't work with my PCAN devices :(_
