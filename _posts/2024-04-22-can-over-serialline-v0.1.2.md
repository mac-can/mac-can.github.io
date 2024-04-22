---
layout: single
title:  "SerialCAN - Version 0.1.2 released"
tag: SerialCAN
categories: Change-log Serial macOS Linux Cygwin Windows Lawicel SLCAN
artifacts: https://github.com/mac-can/SerialCAN/releases/tag/v0.1.2
release: Version 0.1.2 (Commit 5b43ec4 of April 22, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Added common file `Version.h` to the project
- Updated SLCAN sources to rev. 811
- Updated CAN API V3 sources to rev. 1270
- Changed resolution of `CTimer` to 64 bit
- Corrected a #pragma message text
- Updated all build environments
- Improved compiler and linker flags
- Updated the utilities (Posix and Windows)
- Fixed a bug with 800kbps in the utilities
- Updated the Python wrapper and examples
