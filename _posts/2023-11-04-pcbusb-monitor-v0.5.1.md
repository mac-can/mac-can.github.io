---
layout: single
title:  "PCBUSB-Monitor - Version 0.5.1 released"
tag: PCBUSB-Monitor
categories: Change-log Monitor Demos Apps macOS Peak PCBUSB
artifacts: https://www.uv-software.de/dokuwiki/doku.php?id=uvs:programs:maccan_monitor_app
release: Version 0.5.1 (Service Release of November 4, 2023)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Fixed a bug with pipe numbers for PCAN-USB FD devices (hardware version 6.0)
- Added missing linker option `-rpath /usr/local/lib` ([cmd line tools 2397](https://developer.apple.com/forums/thread/737920))
- App as Universal macOS Binary: [MacCAN_Monitor_0.5.1_uni.dmg](https://github.com/mac-can/PCBUSB-Monitor/releases/download/v0.5.1/MacCAN_Monitor_0.5.1_uni.dmg)
- App for x86_64 architecture: [MacCAN_Monitor_0.5.1_x86.dmg](https://github.com/mac-can/PCBUSB-Monitor/releases/download/v0.5.1/MacCAN_Monitor_0.5.1_x86.dmg)