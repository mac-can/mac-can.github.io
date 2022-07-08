---
layout: single
title:  "MacCAN-KvaserCAN - Version 0.3 released"
tag: MacCAN-KvaserCAN
categories: Change-log Drivers macOS Kvaser
artifacts: https://github.com/mac-can/KvaserCAN-Library/releases/tag/v0.3
project: /drivers/KvaserCAN/
release: Version 0.3 (Commit 1ef5e9f of July 8, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Refactoring of the device driver layer:
  - one module `KvaserUSB_LeafDevice` to access **all** devices from _Kvaser CAN Leaf_ device family (i.e. Leaf Light v2)
  - one module `KvaserUSB_MhydraDevice` to access **all** devices from _Kvaser CAN Mhydra_ device family (i.e . U100P)
  - new module `KvaserCAN_Devices` with USB `ProductId` and other properties for **all** devices from both device families
  - implemented error event handling for Mhydra compatible devices
- Updated MacCAN-Core sources to rev. 1200
- Updated CAN API sources to rev. 1053
- Updated CAN API Testing sources to rev. 1062
- Adapted bit-rate settings according to Kvaser´s Linux driver
- Added test suites for function `SetBusParams` and `SetBusParamsFd`
- Fixed a bug with outdated clocks array
- Fixed a bug with CAN clock from software options
- Fixed a bug with `READ_CLOCK_NOW` for Leaf compatible devices
- Fixed a bug with time-stamp conversion ([24MHz issue](https://github.com/mac-can/KvaserCAN-Library/issues/10))
- Fixed a bug with `DRIVERMODE_OFF` for Leaf compatible devices
- Fixed a bug with operation mode `NISO` in the driver layer
- Fixed a bug with getting capabilities from device
- Fixed a bug with HE addresses in the Mhydra driver
- Fixed a bug with setting CAN bus parameters
- Fixed a bug with setting CAN FD bus parameters
- Fixed a bug with data phase settings w/o flag `BRSE` (U100P issue)
- Fixed a bug with converting Kvaser bus params to CAN API bit-rate settings
- Fixed a bug with error handling of device info commands
- Fixed a bug with incorrectly mapped firmware error code
- Fixed a bug with tx message flags in the Swift wrapper ([SwiftCAN issue](https://github.com/mac-can/KvaserCAN-Library/issues/12))
- Fixed a bug with `mask` & `value` in the response `CMD_GET_CAPABILITIES_RESP`
- Fixed a bug with unsupported command `CMD_GET_INTERFACE_INFO_REQ`
- Fixed some findings from static code analysis (`cppcheck`)
- Added `@rpath` to linker option `--install_name`
- Added a scanner for test case annotations to generate the test specs
