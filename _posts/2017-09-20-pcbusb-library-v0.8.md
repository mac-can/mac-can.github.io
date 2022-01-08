---
layout: single
title:  "PCBUSB-Library - Version 0.8 released"
tag: PCBUSB-Library
categories: Change-log Drivers macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.8
release: Version 0.8 (Build 689 of September 20, 2017)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Support of PCAN-USB FD devices in CAN 2.0 mode (CAN classic) and CAN FD mode!
- Adapted the API according to Peak's changes in version 4.2.0.134 and harmonized return codes with it.
- Fixed issue \#208 'CAN_Write stuck when errors on the bus are present'.
- Conducted an intermediate solution for issue \#246 (writing into a trace file).
- Added run-path-relative install name to the library (using the `\@rpath` macro).
