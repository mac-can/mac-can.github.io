---
layout: single
title:  "SLCAN - Version 1.0 released"
tag: SLCAN
categories: Change-log Serial macOS Linux Cygwin Windows Lawicel SLCAN
artifacts: https://github.com/mac-can/SLCAN/releases/tag/v1.0
release: Version 1.0 (Commit f28577f of April 1, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

Raw Lawicel SLCAN protocol implementation
as a spin-off from the [SerialCAN](https://github.com/mac-can/SerialCAN) project.

### Target Platforms

POSIX&reg; compatible operating systems:

1. macOS&reg;
1. Linux&reg;
1. Cygwin&reg;

Windows&reg; (x64 operating system):

1. Windows 10 Pro
1. Windows 11 Pro

### CAN Hardware

- Lawicel CANUSB (Hardware 1.0, Firmware 1.1)

## Known Bugs and Caveats

1. Transmitting messages over the TTY is extremely slow; approx. 16ms per frame.
   I guess this is because the transmission is acknowledged by the CAN device.

1. Time-stamps are currently not supported.
