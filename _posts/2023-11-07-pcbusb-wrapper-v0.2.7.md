---
layout: single
title:  "PCBUSB-Wrapper - Version 0.2.7 released"
tag: PCBUSB-Wrapper
categories: Change-log Wrapper macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Wrapper/releases/tag/v0.2.7
release: Version 0.2.7 (Commit f60fed3 of November 7, 2023)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated PCBUSB header file (version 4.8.0)
- Updated CAN API V3 sources to rev. 1212 
- Updated CAN API V3 testing sources to rev. 1219 
- Updated the trial program 
- Updated deployment rules
- Replaced deprecated `gettimeofday()` and `usleep()` 
- Added linker option `-rpath /usr/local/lib` (issue [#15](https://github.com/mac-can/PCBUSB-Wrapper/issues/15)) 
