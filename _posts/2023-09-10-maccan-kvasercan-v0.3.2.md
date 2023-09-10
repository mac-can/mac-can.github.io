---
layout: single
title:  "MacCAN-KvaserCAN - Version 0.3.2 released"
tag: MacCAN-KvaserCAN
categories: Change-log Drivers macOS Kvaser
artifacts: https://github.com/mac-can/KvaserCAN-Library/releases/tag/v0.3.2
project: /drivers/KvaserCAN/
release: Version 0.3.2 (Commit 2f3cb7c of September 10, 2023)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated MacCAN Core sources to rev. 1757 (core 0.4)
- Updated CAN API V3 sources to rev. 1187 and applied the changes 
  - Added old error code -40 as *queue overrun* error and renumbered error *error frame received* from -40 to -19
  - Removed unused error code `CANERR_ERR_FRAME` (note: the error code -19 is marked as reserved)
  - Removed flag `fdoe` and `brse` from `struct can_speed_t` (note: the flags are marked as reserved)
  - Integrated reworked module `can_btr`:
    - `btr_check_bitrate`: if FDOE w/o BRSE then check data phase field acc. `OPTION_CANBTR_DATA_FIELDS`
    - `btr_bitrate2speed`: no range checks anymore, calculation is done completely in float
    - `btr_bitrate2index`: returns the index if an index is given
    - `btr_bitrate2string`: no range checks anymore
    - `btr_sja10002bitrate`: set data phase field acc. `OPTION_CANBTR_DATA_FIELDS`
    - `btr_compare_bitrates`: comparision on basis of transmission rates (new function)
    - Removed flag `fdoe` and `brse` from `struct btr_speed_t` (standalone variant)
    - Documented all interface functions by Doxygen comments
    - Added header file `CANBTR_Defaults.h`
    - Reworked the bit-rate string scanner (`btr_string2bitrate`):
      - Return a flag if any data phase key is found
      - Return a flag if no. samp. key is found
      - Return `BTRERR_ILLPARA` on error
      - Removed the range checks
      - Set miminum frequency to 1
      - Checked for duplicated keys
      - Accept only case sensitive keys
    - Reworked the bit-rate string printer (`btr_bitrate2string`):
      - Added a parameter to output data phase keys
      - Added a parameter to output no. samp. key
      - Added a parameter for maximum buffer size
    - Fixed a bug with `strtol` if a correct value is outside the range of representable values (note: long is 32 bit wide for MS compilers and 64 bit for gcc based compilers!)
  - Added property values for transmit queue properties (note: values for filtering have been shifted by 8)
  - Fixed a bug with saturation of CAN FD DLC conversion
  - Updated description of compiler switches
  - Reworked formatting of message flags
- Added CAN API V3 Tests with GoogleTest (rev. 1194)
- Added Kvaser-specific bit-rate defaults 
- Added bit-rate settings for 5kbps 
- Fixed a bug with bus error state flags 
- Fixed a bug with capability flag `ERR` 
- Fixed a bug with mode flag `ERR` 
- Fixed a bug with message flag `ESI` 
- Fixed a bug with message flag `RTR` 
- Made the utilities more generic 
- Updated Swift wrapper and package 
- Updated the trial program 
- Updated the examples 
