---
layout: single
title:  "PCANBasic-Wrapper - Version 0.4.6 released"
tag: PCANBasic-Wrapper
categories: Change-log Wrapper Windows Peak PCANBasic
artifacts: https://github.com/uv-software/PCANBasic-Wrapper/releases/tag/v0.4.6
release: Version 0.4.6 (Commit ac17786 September 19, 2023)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated CAN API V3 testing sources to rev. 1201
- Updated CAN API V3 sources to rev. 1187 and applied the changes
  - Fixed a small bug in `btr_compare_bitrates` 
  - Reworked formatting of message flags
- Reworked handling of receive queue empty
- Made the utilities more generic
- Updated the Python examples
