---
layout: single
title:  "KvaserCAN-Wrapper - Version 0.3 released"
tag: KvaserCAN-Wrapper
categories: Change-log Wrapper Windows Kvaser CANLib32
artifacts: https://github.com/uv-software/KvaserCAN-Wrapper/releases/tag/v0.3
release: Version 0.3 (Commit d9ef6b6 of April 6, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Recreated the library projects
- Updated all MSBuild environments
- Updated Kvaser canLib DLL (version 5.44)
- Updated CAN API V3 sources to rev. 1260
- Updated CAN API V3 testing sources to rev. 1255
- Updated class `CTimer` from SourceMedley repo
- Implemented identifier acceptance filtering
- Added a test suite for identifier filtering
- Added filtering option to utility `can_moni`
- Added option `/LIST-BITRATES` to the utilities
- Implemented Kvaser-specific properties
- Fixed a bug with flag `ESI` in TC05.20
- Updated the trial program
- Updated the utilities
- Updated the examples
- Added an GitHub action
