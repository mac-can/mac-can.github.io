---
layout: single
title:  "MacCAN-TouCAN - Version 0.2.2 released"
tag: MacCAN-TouCAN
categories: Change-log Drivers macOS Rusoku TouCAN
artifacts: https://github.com/mac-can/RusokuCAN/releases/tag/v0.2.2
release: Version 0.2.2 (Commit d93fbfe of December 27, 2021)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Reworked the driver layer (to solve the copy constructor issue [#16](https://github.com/mac-can/RusokuCAN/issues/16)):
  - rename sub-folders in `$(PROJROOT)/Sources`
  - switch CAN API V3 wrapper from **C++** to **C**
  - create a lot of new driver layer modules
  - prepare the driver to support further devices
  - no obvious functional changes
- Added a Swift wrapper including SPM configuration
- Added two simple Swift examples for sending and receiving CAN frames
- Added an Xctest target for CAN API V3 **C** interface to the trial program
  - take over all test suites and test cases from [MacCAN-KvaserCAN](https://github.com/mac-can/KvaserCAN-Library/tree/main/Trial/Testing)
  - test execution: 131 tests, 6 failed - but false positives
- Fixed a testing issue with unsupported acknowledge of transmit messages
- Fixed a testing issue with unsupported bit-timing index 1 (800kbps)
- Fixed a bug with unchecked device handle
- Fixed a bug with missing header file in class `CTouCAN`
- Fixed an omission with forgotten TouCAN specific properties
- Fixed a bug with non-boolean return value in a boolean function
- Fixed an issue with deprecated function `IOMasterPort` (first deprecated in macOS 12.0)
- Set all Xcode deployment targets to macOS **11.0** (`Makefile`s still work on OS X 10.13)
- Updated the `Makefile`s to build the artifacts as **Universal macOS Binary**
- Updated my beloved utilities
- Updated the C++ examples
