---
layout: single
title:  "PCANBasic-Wrapper - Version 0.5 released"
tag: PCANBasic-Wrapper
categories: Change-log Wrapper Windows Peak PCANBasic
artifacts: https://github.com/uv-software/PCANBasic-Wrapper/releases/tag/v0.5
release: Version 0.5 (Commit 31a0049 of April 6, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Recreated the library projects
- Updated all MSBuild environments
- Updated PCANBasic DLL (version 4.8.2)
- Updated CAN API V3 sources to rev. 1260
- Updated CAN API V3 testing sources to rev. 1255
- Updated class `CTimer` from SourceMedley repo
- Implemented identifier acceptance filtering
- Added a test suite for identifier filtering
- Added filtering option to utility `can_moni`
- Added option `/LIST-BITRATES` to the utilities
- Fixed a bug with flag `ESI` in TC05.20
- Updated the trial program
- Updated the utilities
- Updated the examples
- Added an GitHub action
