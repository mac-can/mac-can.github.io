---
layout: single
title:  "PCANBasic-Wrapper - Version 0.4.4 released"
tag: PCANBasic-Wrapper
categories: Change-log Wrapper Windows Peak PCANBasic
artifacts: https://github.com/uv-software/PCANBasic-Wrapper/releases/tag/v0.4.4
release: Version 0.4.4 (Commit 501c6e6 August 3, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated CAN API V3 sources to rev. 1082
- Fixed a bug with transceiver off in function `can_reset`
- Fixed a bug with field `SAM` in BTR0BTR1 register
- Fixed a bug with BTR0BTR1 register in CAN FD mode
- Fixed a bug with mapping CAN FD bit-rate settings to Peak bit-rate string
- Fixed a bug with uncleared initialization flag when all channels released
- Realized feature `NXTD` and `NRTR` (software solution)
- Updated class `CPeakCAN` (some property keys)
- Updated the trial program
- Updated the utilities
