---
layout: single
title:  "MacCAN-KvaserCAN - Version 0.1 released"
tag: MacCAN-KvaserCAN
categories: Change-log Drivers macOS Kvaser
artifacts: https://github.com/mac-can/MacCAN-KvaserCAN/releases/tag/v0.1
release: Version 0.1 (Commit 64e4388 of June 3, 2021)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- CAN 2.0:
  - 11-bit and 29-bit identifier
  - bit-rates up to 1'000 kbps
- Bit-rate settings:
  - via register values (clock, prescaler, time segment TSeg1 and TSeg2, SJW, SAM)
  - as pre-defined bit-timing index (according to CiA CANopen specification)
- Operation modes:
  - Monitor mode enable/disable (default=disabled)
  - Error frames enable/disable (default=disabled)
  - Extended frames disable/enable (default=enabled)
  - Remote frames disable/enable (default=enabled)
- Message reception:
  - Message queue (FIFO) for 64K CAN message
  - Read queue via polling, blocking read, or with time-out up to 65 seconds
- Message transmission:
  - with or without acknowlege (with time-out up to 65 seconds)
- Application Programming Interface:
  - CAN API V3 by UV Software (C and C++ API)
  - CAN API V3 Python Wrapper (Python 2.7 and 3.8)
- Supported Kvaser CAN Leaf devices:
  - Kvaser Leaf Light v2 (EAN: 73-30130-00685-0)
  - Kvaser Leaf Pro HS v2 (EAN: 73-30130-00843-4)
- Limitations (selected):
  - _**Leaf Pro HS v2** devices can currently only be operated in **CAN 2.0 mode**!_
  - _**Monitor mode** (listen-only) is not supported by the **Leaf Light v2** hardware._
