---
layout: single
title:  "PCANBasic-Wrapper - Version 0.4.1 released"
tag: PCANBasic-Wrapper
categories: Change-log Wrapper Windows Peak PCANBasic
artifacts: https://github.com/uv-software/PCANBasic-Wrapper/releases/tag/v0.4.1
release: Version 0.4.1 (Commit 60fa2d4 of June 7, 2021)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated to PCANBasic DLL version 4.5.4
- Switched to a dual-license: BSD-2-Clause OR GPL-3.0-or-later
- Added a check operation mode bit `FDOE` when bit `BRSE` is set
- Added a check for valid identifier range in `can_write`
- Added a check for valid messages flags in `can_write`
- Added a check for operation capability in `can_init`
- Fixed an out-of-bound violation in companion module `can_btr`
- Fixed a but with casting from CAN API channel to PCAN handle
- Fixed a mistake with channel name displayed instead of device name
- Repaired the C++ examples; Python examples are still broken
