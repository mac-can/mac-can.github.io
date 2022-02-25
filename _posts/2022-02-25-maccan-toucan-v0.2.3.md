---
layout: single
title:  "MacCAN-TouCAN - Version 0.2.3 released"
tag: MacCAN-TouCAN
categories: Change-log Drivers macOS Rusoku TouCAN
artifacts: https://github.com/mac-can/RusokuCAN.dylib/releases/tag/v0.2.3
release: Version 0.2.3 (Commit c1a3633 of February 25, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated MacCAN-Core sources to rev. 1090
- Removed class `CMacCAN` from project (R.I.P.)
- Updated CAN API sources to rev. 1036 and applied the changes
- Fixed a bug with probing a device when it is used by another process
- Fixed a bug with string length of device vendor
- Added operations to class `CTouCAN` to query channel information
- Updated the utilities to get the list of channels from library
- Moved unit test suites into `$(PROJROOT)/Tests/UnitTests`
- Added `cppcheck` target to `Makefile` of the Trial program
- Updated the Swift and Python examples
