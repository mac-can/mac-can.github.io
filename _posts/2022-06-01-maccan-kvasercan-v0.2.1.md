---
layout: single
title:  "MacCAN-KvaserCAN - Version 0.2.1 released"
tag: MacCAN-KvaserCAN
categories: Change-log Drivers macOS Kvaser
artifacts: https://github.com/mac-can/KvaserCAN-Library/releases/tag/v0.2.1
project: /drivers/KvaserCAN/
release: Version 0.2.1 (Commit e334212 of June 1, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Fixed bit-rate issue for devices not running at 80 MHz (issue [#10](https://github.com/mac-can/KvaserCAN-Library/issues/10))
- Added methods to query channel information to the Swift wrapper
- Added a `cppcheck` configuration to the project
