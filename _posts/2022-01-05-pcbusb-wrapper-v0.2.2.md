---
layout: single
title:  "PCBUSB-Wrapper - Version 0.2.2 released"
tag: PCBUSB-Wrapper
categories: Change-log Wrapper macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Wrapper/releases/tag/v0.2.2
release: Version 0.2.2 (Commit 58dd221 of January 5, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated CAN API sources to rev. 1020 and applied the changes
- Renamed C interface function `can_software` in `can_firmware`
- Reworked output of function `can_hardware` and `can_firmware`
- Added a check for minimum required PCBUSB library version (v0.9 and above)
- Fixed an issue with missing copy constructor (to avoid dynamic allocation of class members)
- Fixed a bug with uncleared initialization flag when all handles have been released
- Fixed a bug with vendor-specific property values
- Fixed a bug with enumeration of PCAN channels
- Activated option for PCBUSB issue 198 (old messages in URB of the reception queue)
- Added an Xctest target for CAN API V3 C interface to the trial program:
  - workaround to run the test suites with [PCBUSB.dylib](https://github.com/mac-can/PCBUSB-Library) in Xcode
  - workaround for PCANBasic init delay issue and PCBUSB flag QXMTFULL issue
- Set all Xcode deployment targets to macOS **11.0** (`Makefile`s still work on OS X 10.13)
- Updated the `Makefile`s to build the artifacts as **Universal macOS Binary**
