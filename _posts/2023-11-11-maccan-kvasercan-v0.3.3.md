---
layout: single
title:  "MacCAN-KvaserCAN - Version 0.3.3 released"
tag: MacCAN-KvaserCAN
categories: Change-log Drivers macOS Kvaser
artifacts: https://github.com/mac-can/KvaserCAN-Library/releases/tag/v0.3.3
project: /drivers/KvaserCAN/
release: Version 0.3.3 (Commit d950b79 of November 11, 2023)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated MacCAN-Core sources to rev. 1816 
- Updated CAN API V3 sources to rev. 1212 
- Updated CAN API V3 testing sources to rev. 1219 
- Updated GoogleTest to version 1.14.0 
- Updated the trial program 
- Updated the Python wrapper
- Updated Doxygen configuration 
- Updated deployment rules
- Replaced deprecated `gettimeofday` and `usleep` 
- Added linker option `-rpath /usr/local/lib` (Xcode 15)