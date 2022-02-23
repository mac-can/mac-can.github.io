---
layout: single
title:  "MacCAN-TouCAN - Version 0.2.1 released"
tag: MacCAN-TouCAN
categories: Change-log Drivers macOS Rusoku TouCAN
artifacts: https://github.com/mac-can/RusokuCAN.dylib/releases/tag/v0.2.1
release: Version 0.2.1 (Commit 0b4a139 of June 5, 2021)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Fixed the hibernation issue (issue #11)
- Fixed a bug when trying to send a status message
- Fixed a bug  when the channel number is invalid
- Fixed a bug  when requested operation mode is not supported
- Fixed an out-of-bound violation in companion module `can_btr`
- Fixed some issues from code analysis
