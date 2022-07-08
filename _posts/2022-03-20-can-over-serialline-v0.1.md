---
layout: single
title:  "SerialCAN - Version 0.1 released"
tag: SerialCAN
categories: Change-log Serial macOS Linux Cygwin Windows Lawicel SLCAN
artifacts: https://github.com/mac-can/SerialCAN/releases/tag/v0.1
release: Version 0.1 (Commit b828e81 of March 20, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

**Target Platforms**

POSIX<sup>&reg;</sup> compatible operating systems:

1. macOS<sup>&reg;</sup>
2. Linux<sup>&reg;</sup>
3. Cygwin<sup>&reg;</sup>

Windows<sup>&reg;</sup> (x64 operating system):

1. Windows 10 Pro

**CAN Hardware**

- Lawicel CANUSB (Hardware 1.0, Firmware 1.1)

**Known Bugs and Caveats**

1. Transmitting messages over the TTY is extremely slow; approx. 16ms per frame.
   I guess this is because the transmission is acknowledged by the CAN device.

2. Time-stamps are currently not supported.

3. Python Ctrl+C issue on Linux still unsolved.
