---
layout: single
title:  "PCBUSB-Wrapper - Version 0.3 released"
tag: PCBUSB-Wrapper
categories: Change-log Wrapper macOS Linux Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Wrapper/releases/tag/v0.3
release: Version 0.3 (Commit b3ab49a of August 2, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Integrated changes from [PCBUSB library](https://github.com/mac-can/PCBUSB-Library) [v0.13](https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.13):
  - Acceptance filtering by setting parameter:
    - `PCAN_ACCEPTANCE_FILTER_11BIT`
    - `PCAN_ACCEPTANCE_FILTER_29BIT`
    - `PCAN_MESSAGE_FILTER`
    - `PCAN_RECEIVE_STATUS`
  - Suppression of status frames by setting parameter:
    - `PCAN_ALLOW_STATUS_FRAMES`
  - Suppression of remote frames by setting parameter:
    - `PCAN_ALLOW_RTR_FRAMES`
- Updated CAN API V3 sources to rev. 1356:
  - Implemented acceptance filtering
  - Solved an issue with `PCAN_RECEIVE_STATUS`
- Updated CAN API V3 testing to rev. 1373:
  - GoogleTest framework v1.15.0
  - Test suites for acceptance filtering
- Updated CAN API V3 utilities to rev. 1375:
  - Filtering options (`can_moni` and `can_test`)
  - Option to send extended frames (`can_test`)
  - Fixed a bug with extended frames (`can_moni`)
- Updated the Python wrapper and examples
- Fixed an installation issue on Linux

_Note: This release requires version [0.13](https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.13) (or later) of the [PCBUSB library](https://github.com/mac-can/PCBUSB-Library) to be installed._
