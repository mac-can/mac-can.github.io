---
layout: single
title:  "MacCAN-TouCAN - Version 0.2 released"
tag: MacCAN-TouCAN
categories: Change-log Drivers macOS Rusoku TouCAN
artifacts: https://github.com/mac-can/RusokuCAN/releases/tag/v0.2
release: Version 0.2 (Commit 52f784a of February 28, 2021)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Worked in the latest changes from MacCAN-Core (SVN rev. 986)
- Added a CAN API V3 compatible Python wrapper and two Python examples
- Added two simple C++ examples for sending and receiving CAN frames
- Weakened the sizeof check while reading numerical properties
- Fixed a bug with a locked mutex when device is not present
- Fixed a bug with signaling a wait condition
- Updated the trial program and the utilities
