---
layout: single
title:  "PCBUSB-Wrapper - Version 0.2.5 released"
tag: PCBUSB-Wrapper
categories: Change-log Wrapper macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Wrapper/releases/tag/v0.2.5
release: Version 0.2.5 (Commit fa172d5 of August 25, 2023)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated `PCBUSB-Library` header (version 4.7.0.1)
- Added a compatibility check from `PCAN_CHANNEL_VERSION` (v0.9 or higher)
- Updated CAN API V3 sources to SVN rev. 1155 and apply the changes:
  - Added old error code -40 as `queue overrun error` and renumbered error `error frame received` from -40 to -19
  - Removed unused error code `CANERR_ERR_FRAME` (note: the error code -19 is marked as reserved)
  - Removed flag `fdoe` and `brse` from struct `can_speed_t` (note: the flags are marked as reserved)
  - Integrated reworked module `can_btr`:
    - `btr_check_bitrate`: if FDOE w/o BRSE then check data phase field acc. `OPTION_CANBTR_DATA_FIELDS`
    - `btr_bitrate2speed`: no range checks anymore, calculation is done completely in float
    - `btr_bitrate2index`: returns the index if an index is given
    - `btr_bitrate2string`: no range checks anymore (except `frequency` greater than 0)
    - `btr_sja10002bitrate`: set data phase field acc. `OPTION_CANBTR_DATA_FIELDS`
    - `btr_compare_bitrates`: comparision on basis of transmission rates (new function)
    - Removed flag `fdoe` and `brse` from struct `btr_speed_t` (standalone variant)
    - Documented all interface functions by Doxygen comments
    - Added header file `CANBTR_Defaults.h`
    - Reworked the bit-rate string scanner (`btr_string2bitrate`):
      - Return a flag if any data phase key is found
      - Return a flag if no. samp. key is found
      - Return `BTRERR_ILLPARA` on error
      - Removed the range checks
      - Set miminum frequency to 1
      - Check for duplicated keys
      - Accept only case sensitive keys
    - Reworked the bit-rate string printer (`btr_bitrate2string`):
      - Added a parameter to output data phase keys
      - Added a parameter to output no. samp. key
      - Added a parameter for maximum buffer size
    - Fixed a bug with `strtol` if a correct value is outside the range of representable values (note: `long` is 32 bit wide for MS compilers and 64 bit for gcc based compilers!)
  - Added property values for transmit queue properties (note: values for filtering has been shifted by 8)
  - Fixed a bug with saturation of CAN FD DLC conversion
  - Updated description of compiler switches
- Reworked status message and error frame handling (mode flag `err` and message flag `sts`)
- Synchronized the Utilities with [PCBUSB-Utilities](https://github.com/mac-can/PCBUSB-Utilities) v0.5.7
  - Fixed an issue with option `--verbose`
- Added CAN API V3 Tests with GoogleTest
- Updated CAN API V3 Xctest suites
- Updated the trial program

Tested with [PCBUSB-Library](https://github.com/mac-can/PCBUSB-Library) version [0.12.1](https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.12.1)