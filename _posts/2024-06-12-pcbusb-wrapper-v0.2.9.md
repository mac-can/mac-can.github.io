---
layout: single
title:  "PCBUSB-Wrapper - Version 0.2.9 released"
tag: PCBUSB-Wrapper
categories: Change-log Wrapper macOS Linux Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Wrapper/releases/tag/v0.2.9
release: Version 0.2.9 (Commit 44b0d6e of June 12, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated CAN API V3 sources to rev. 1312
- Updated CAN API V3 Xcode testing to rev. 1334 
- Updated CAN API V3 GoogleTest testing to rev. 1336
- Removed upper size limit of string properties
- Reworked CAN API V3 return values (**C** vs. **C++**)
- Optimized PeakCANBasic wrapper (`can_api.c`)
- Fixed a bug with compiler switch `__MAC_11_0`
- Fixed some findings from static code analysis
- Moved the run-time loader into a separate file
- Integrated generic CAN API V3 Utilities (rev. 1323)
- Updated release documents
  