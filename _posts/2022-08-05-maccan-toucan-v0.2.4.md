---
layout: single
title:  "MacCAN-TouCAN - Version 0.2.4 released"
tag: MacCAN-TouCAN
categories: Change-log Drivers macOS Rusoku TouCAN
artifacts: https://github.com/mac-can/RusokuCAN.dylib/releases/tag/v0.2.4
release: Version 0.2.4 (Commit 46ecb27 of August 5, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated CAN API V3 sources to rev. 1082
- Realized new property `GET_CAN_CLOCK`
- Applied changes from module `can_btr`
- Updated CAN API V3 Testing sources to rev. 1084
- Fixed a possible bug with USB device name length
- Fixed a bug with missing check of the CAN clock frequency (50MHz)
- Fixed a bug with tx message flags in the Swift wrapper (SwiftCAN issue [#23](https://github.com/mac-can/RusokuCAN.dylib/issues/23))
- Fixed some findings from static code analysis
- Added a scanner for test case annotations
- Added `@rpath` to the library Makefiles
