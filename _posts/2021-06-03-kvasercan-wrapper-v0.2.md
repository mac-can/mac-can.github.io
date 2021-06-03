---
layout: single
title:  "KvaserCAN-Wrapper - Version 0.2 released"
tag: KvaserCAN-Wrapper
categories: Change-log Wrapper Windows Kvaser CANLib32
artifacts: https://github.com/uv-software/KvaserCAN-Wrapper/releases/tag/v0.2
release: Version 0.2 (Commit 5799eff of June 3, 2021)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Migrated to Visual Studio 2019 and adapted the MSC build environments
- Switched to a dual-license: **BSD-2-Clause** OR **GPL-3.0-or-later**
- Updated to Kvaser´s CANlib SDK version **5.35**
- Realized class `CKvaserCAN: public CCANAPI` (`uvKvaserCAN.dll`)
- Implemented operation mode `NXTD` and `NRTR`
- Added a check for operation mode bit `FDOE` when bit `BRSE` is set
- Added a check for valid identifier range in `can_write`
- Added a check for operation capability in `can_init`
- Fixed a mistake with channel name displayed instead of device name
- Fixed an out-of-bound violation in companion module `can_btr`
- Fixed a bug with wrong return values from `kvaser_capacity`
- Fixed an unnecessary decl-specifier on `can_boards[]`
- Added my beloved CAN utilities
- Added two simple C++ examples
- Added a Doxygen configuration
