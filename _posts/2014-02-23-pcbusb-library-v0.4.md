---
layout: single
title:  "PCBUSB-Library - Version 0.4 released"
tag: PCBUSB-Library
categories: Change-log Drivers macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.4
release: Version 0.4 (Build 293 of February 23, 2014)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Time-stamps are now taken from CAN controller instead of taking them from the system clock.
- Getting and setting of `PCAN_*` parameters reworked (to be almost compatible to the PCANBasic DLL, version 1.3).
- Resetting of RCV queue and XMT queue on the CAN controller realized.
