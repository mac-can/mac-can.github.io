---
layout: single
title:  "PCBUSB-Wrapper - Version 0.4 released"
tag: PCBUSB-Wrapper
categories: Change-log Wrapper macOS Linux Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Wrapper/releases/tag/v0.4
release: Version 0.4 (Commit 6ba281f of February 28, 2025)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated CAN API V3 sources to rev. 1467
  - Added an IPC interface (**RocketCAN**)
  - Added an ASCII parser for CAN messages*
- Updated GoogleTest framework to v1.15.2
- Updated CAN API V3 testing to rev. 1478
  - Integrated IPC interface (server and client)
- Updated CAN API V3 utilities to rev. 1481
  - Added new utility `can_send` (ASCII parser)
  - Added new utility `can_port` (RocketCAN server)
  - Added new utility `can_simu` (RocketCAN server w/o HW)
  - Optimized commandline argument handling
- Updated Python wrapper to v0.3.2
- Updated C++ examples
- Created IPC examples

_*) The syntax is taken from SocketCAN utility [can-utils/cansend](https://github.com/linux-can/can-utils/tree/master)_
