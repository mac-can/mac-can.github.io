---
layout: single
title:  "MacCAN-KvaserCAN - Version 0.3.4 released"
tag: MacCAN-KvaserCAN
categories: Change-log Drivers macOS Kvaser
artifacts: https://github.com/mac-can/KvaserCAN-Library/releases/tag/v0.3.4
project: /drivers/KvaserCAN/
release: Version 0.3.4 (Commit e8fb32f of June 11, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated CAN API V3 sources to rev. 1312 
- Updated CAN API V3 Xcode testing to rev. 1334 
- Updated CAN API V3 GoogleTest suites to rev. 1336
- Removed unnecessary class attributes 
- Removed upper size limit of string properties
- Reworked CAN API V3 return values (**C** vs. **C++**)
- Optimized CAN API V3 wrapper (`can_api.c`)
- Integrated generic CAN API V3 Utilities (rev. 1323)
- Updated release documents 