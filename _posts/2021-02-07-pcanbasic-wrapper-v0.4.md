---
layout: single
title:  "PCANBasic-Wrapper - Version 0.4 released"
tag: PCANBasic-Wrapper
categories: Change-log Wrapper Windows Peak PCANBasic
artifacts: https://github.com/uv-software/PCANBasic-Wrapper/releases/tag/v0.4
release: Version 0.4 (Commit 53db869 of February 7, 2021)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Applied changes from CAN API V3 specification (rev. 951 to 987)
- Added C++ class `CPeakCAN` derived from abstract class `CCANAPI`
- Reworked the trial program (it is now based on class `CPeakCAN`)
- Reorganized the entire folder structure of the repository
- Added my beloved CAN utilities `can_moni` and `can_test`
- Added two simple C++ examples for sending and receiving CAN frames
- Added a Python wrapper and two Python examples
- Added a Doxygen configuration
