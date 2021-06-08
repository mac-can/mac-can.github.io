---
layout: single
title:  "PCBUSB-Wrapper - Version 0.2.1 released"
tag: PCBUSB-Wrapper
categories: Change-log Wrapper macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Wrapper/releases/tag/v0.2.1
release: Version 0.2.1 (Commit 95dcdc6 of June 8, 2021)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Added a check for valid identifier range in `can_write`
- Added a check for valid messages flags in `can_write`
- Added a check for operation capability in `can_init`
- Added a check for operation mode bit `FDOE` when bit `BRSE` is set
- Fixed a mistake with channel name displayed instead of device name
- Fixed a bug with casting from CAN API channel to PCAN handle
- Fixed an out-of-bound violation in companion module `can_btr`
- Repaired the Python examples (they still not work with Python 2.7)
- Switched to a dual-license: BSD-2-Clause OR GPL-3.0-or-later
