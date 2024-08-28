---
layout: single
title:  "SLCAN - Version 2.0 released"
tag: SLCAN
categories: Change-log Serial macOS Linux Cygwin Windows Lawicel SLCAN
artifacts: https://github.com/mac-can/SLCAN/releases/tag/v2.0
release: Version 2.0 (Commit 5b10c41 of August 28, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

Extension to include the CANable 2.0 protocol with the following restrictions:
- The firmware currently does not provide ACK/NACK feedback for serial commands
- CAN FD operation mode (bit-rate switching) is not supported by the library
- Silent operation mode (listen-only) is not supported by the library
- SJA1000 bit-rates (BTR register) are not provided by the firmware
- Acceptance filtering is not provided by the firmware
- Bus errors (status flags) are not provided by the firmware
- Hardware and firmware versions are displayed as fake number `0.0`[*]
- Serial number is displayed as fake number `99999999`[*]

*) If compiler switch `OPTION_SLCAN_FAKE_COMMANDS` is specified.
