---
layout: single
title:  "SerialCAN - Version 0.3 released"
tag: SerialCAN
categories: Change-log Serial macOS Linux Cygwin Windows Lawicel SLCAN
artifacts: https://github.com/mac-can/SerialCAN/releases/tag/v0.3
release: Version 0.3 (Commit 4bb7945 of August 28, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

**Extension to include the CANable 2.0 protocol with the following restrictions**:
- The firmware currently does not provide ACK/NACK feedback for serial commands
- CAN FD operation mode (bit-rate switching) is not supported by the libraries
- Silent operation mode (listen-only) is not supported by the libraries
- SJA1000 bit-rates (BTR register) are not provided by the firmware
- Acceptance filtering is not provided by the firmware
- Bus errors (status flags) are not provided by the firmware
- Hardware and firmware versions are displayed as fake number `0.0`
- Serial number is displayed as fake number `99999999`

**Other changes**:
- Updated CAN API V3 sources to rev. 1398
- Updated CAN API V3 utilities to rev. 1396
- Adapted the Xcode unit tests (macOS only)
- Updated the Python wrapper and examples
- Updated the C/C++ examples
- Updated the trial program
