---
layout: single
title:  "MacCAN-TouCAN - Version 0.3 released"
tag: MacCAN-TouCAN
categories: Change-log Drivers macOS Rusoku TouCAN
artifacts: https://github.com/mac-can/RusokuCAN.dylib/releases/tag/v0.3
release: Version 0.3 (Commit 1b0d095 of November 12, 2023)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Removed all **CANAL** references from the project
- Created a **new** TouCAN USB command interface
- Added common `Version.h` to the project
- Updated CAN API V3 sources to rev. 1270
- Updated CAN API V3 testing sources to rev. 1273
- Removed unused attributes from class `CTouCAN` 
- Changed the resolution of `CTimer` to 64 bit
- Implemented identifier acceptance filtering
- Added test suites for acceptance filtering
- Added filtering option to utility `can_moni`
- Added option `--list-bitrates` to the utilities
- Fixed a bug with macro `DLC2LEN()`
- Updated `Makefile`s and `build_no.sh`
- Improved compiler and linker flags 
- Updated the Python wrapper and examples 
- Updated the Swift wrapper and examples 
- Updated the deployment rules
