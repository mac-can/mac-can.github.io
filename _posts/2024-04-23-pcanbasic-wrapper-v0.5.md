---
layout: single
title:  "PCANBasic-Wrapper - Version 0.5 released"
tag: PCANBasic-Wrapper
categories: Change-log Wrapper Windows Peak PCANBasic
artifacts: https://github.com/uv-software/PCANBasic-Wrapper/releases/tag/v0.5
release: Version 0.5 (Commit af5d678 of April 23, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Added an unified version file 
- Recreated the library projects
- Updated all MSBuild environments
- Updated PCANBasic DLL (version 4.8.2)
- Updated CAN API V3 sources to rev. 1270
- Updated CAN API V3 testing sources to rev. 1273
- Removed unused attributes from class `CPeakCAN`
- Changed the resolution of `CTimer` to 64 bit 
- Implemented identifier acceptance filtering
- Added test suites for acceptance filtering
- Added filtering option to utility `can_moni`
- Added option `/LIST-BITRATES` to the utilities
- Fixed a bug with flag `ESI` in TC05.20
- Fixed a bug with Peak vs. CiA bit-rate settings 
- Fixed compiler warnings with legacy CAN 2.0 frame format 
- Updated the Python wrapper
- Updated the examples
