---
layout: single
title:  "KvaserCAN-Wrapper - Version 0.3.1 released"
tag: KvaserCAN-Wrapper
categories: Change-log Wrapper Windows Kvaser CANLib32
artifacts: https://github.com/uv-software/KvaserCAN-Wrapper/releases/tag/v0.3.1
release: Version 0.3.1 (Commit 7922988 of June 11, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated Kvaser canLib DLL (version 5.45)
- Updated CAN API V3 sources to rev. 1312
- Updated CAN API V3 testing sources to rev. 1336
- Removed upper size limit of string properties
- Reworked CAN API V3 return values (**C** vs. **C++**)
- Optimized KvaserCAN wrapper (`can_api.c`)
- Integrated generic CAN API V3 utilities (rev. 1323)
- Updated release documents
