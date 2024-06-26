---
permalink: /drivers/RusokuCAN/
layout: single
toc: true
toc_sticky: true
title: macOS<sup>&reg;</sup> User-Space Driver and SDK for TouCAN USB Interfaces from Rusoku
tag: MacCAN-TouCAN
type: driver
latest: https://github.com/mac-can/RusokuCAN.dylib/releases/download/v0.3.1/artifacts.zip
srczip: https://github.com/mac-can/RusokuCAN.dylib/archive/tags/v0.3.1.zip
srctar: https://github.com/mac-can/RusokuCAN.dylib/archive/tags/v0.3.1.tar.gz
github: https://github.com/mac-can/RusokuCAN.dylib
issues: https://github.com/mac-can/RusokuCAN.dylib/issues
---
Rusoku Technologies is an innovative engineering team based in Lithuania, Europe.
They offer CAN adapter at a reasonable price.
Drivers and utilities for Windows and Linux are available as open-source.
A macOS user-space driver for TouCAN USB interfaces from Rusoku is provided by UV&nbsp;Software.

[Download]({{page.latest}}){: .btn .btn--primary}
[Sources (zip)]({{page.srczip}}){: .btn .btn--primary}
[Sources (tar.gz)]({{page.srctar}}){: .btn .btn--primary}
[@GitHub]({{page.github}}){: .btn .btn--primary}

## MacCAN-TouCAN Driver

The macOS driver for TouCAN USB Interfaces from Rusoku is based on MacCAN-Core which is an abstraction (or rather a wrapper) of Apple´s IOUsbKit to create USB user-space drivers for CAN interfaces from various vendors under macOS.
The GitHub repository contains the source code for the MacCAN-TouCAN driver and several alternatives to build dynamic libraries for macOS, either as a C++ class library (_libTouCAN_), or as a CAN&nbsp;API&nbsp;V3 wrapper library (_libUVCANTOU_), as well as some example programs and my beloved CAN utilities `can_moni` and `can_test`.

The MacCAN-TouCAN SDK comes with a CAN&nbsp;API&nbsp;V3 compatible API.
CAN&nbsp;API&nbsp;V3 is a wrapper specification by UV&nbsp;Software to have a uniform CAN Interface API for various CAN interfaces from different vendors running under multiple operating systems. See header file `CANAPI.h` for the CAN&nbsp;API&nbsp;V3 wrapper specification.

### Features

|         Feature          |     Supported      | Remarks |
| ------------------------ |:------------------:| ------- |
| CAN 2.0                  | :heavy_check_mark: |  Classical CAN |
| CAN FD                   | :x: |  Flexible Data-rate CAN |
| Bit-rate, CAN 2.0        | :heavy_check_mark: | high speed: up to 1 Mbps |
| Bit-rate, CAN FD         | :x: | nominal: up to 1 Mbps <br/> data phase: up to 8 Mbps |
| 11-bit identifier (STD)  | :heavy_check_mark: | CAN 2.0 |
| 29-bit identifier (XTD)  | :heavy_check_mark: | CAN 2.0 |
| Remote frames (RTR)      | :heavy_check_mark: | CAN 2.0 |
| Error frames (ERR)       | :heavy_check_mark: | CAN 2.0 |
| Error indicator (ESI)    | :x: | CAN FD only |
| Bit-rate switching (BRS) | :x: | CAN FD only |
| Listen-only mode (MON)   | :heavy_check_mark: | CAN 2.0 |
| Identifier filtering     | :heavy_check_mark: | CAN 2.0, Std. and Xtd. IDs |
| Operation modes: | | | |
| - Monitor mode enable/disable (MON)        | :heavy_check_mark: | disabled by default |
| - Error frames enable/disable (ERR)        | :heavy_check_mark: | disabled by default |
| - Remote frames disable/enable (NRTR)      | :heavy_check_mark: | enabled by default |
| - Extended frames disable/enable (NXTD)    | :heavy_check_mark: | enabled by default |
| - Shared access enable/disable (SHRD)      | :x: | _not supported_ |
| - Non-ISO CAN FD enable/disable (NISO)     | :x: | _not supported_ |
| - Bit-rate switching enable/disable (BRSE) | :x: | _not supported_ |
| - CAN FD operation enable/disable (FDOE)   | :x: | _not supported_ |
| Bit-rate settings: | | | |
| - Pre-defined bit-timing indexes | :heavy_check_mark: | acc. CiA CANopen specification |
| - BTR register values            | :heavy_check_mark: | register fields:<br/>- `freq` (clock frequency in [Hz])<br/>- `brp` (bit-rate prescaler)<br/>- `tseg1` (time segment 1)<br/>- `tseg2` (time segment 2)<br/>- `sjw` (synchronization jump width)<br/>- `sam` (number of samples) |
| Message reception: | | | |
| - Message queue (FIFO) | :heavy_check_mark: | up to 64K CAN messages |
|   - Polling            | :heavy_check_mark: | return immediately |
|   - Timed out          | :heavy_check_mark: | wait up to 65'534 milliseconds |
|   - Blocking read      | :heavy_check_mark: | wait infinitely |
| Message transmission: | | | |
| - Acknowledged write | :x: | _not supported_  |
| - Buffered write     | :heavy_check_mark: | _buffer size depends on the hardware_ |
| Software Development Kit: | | | |
| - VSCP CANAL API  | :x: | _not available_ |
| - CAN API V3      | :heavy_check_mark: | [C API and C++ API](/wrapper/canapi-v3/) by UV&nbsp;Software |
| - Dynamic library | :heavy_check_mark: | `libUVCANTOU.dylib`, `libTouCAN.dylib` |
| - Static library  | :heavy_check_mark: | `libUVCANTOU.a`, `libTouCAN.a` |
| - Source code     | :heavy_check_mark: | BDS-2-Clause or GPL-3.0-or-later |
| - Apple silicon   | :heavy_check_mark: | and Intel architecture |
| - Swift wrapper   | :heavy_check_mark: | Swift 5.5 (including SPM) |
| - Python wrapper  | :heavy_check_mark: | Python 3.8 |
| - Windows wrapper | :heavy_check_mark: | _not available_ |
| - Utilities       | :heavy_check_mark: | CLI utilities `can_moni` and `can_test`|
| - Examples        | :heavy_check_mark: | C, C++, Swift, Python |

### Change-log

{% for post in site.posts %}
{% if post.categories contains 'Change-log' and post.tag == 'MacCAN-TouCAN' %}
{{ post.content }}
{% endif %}
{% endfor %}

### Supported Devices

Only the following devices from Rusoku Technologies are supported:
- TouCAN USB (Model F4FS1)

For technical specifications, prices and delivery terms see [Rusoku´s website](https://www.rusoku.com/products).

### Known Bugs and Caveats

For a list of known bugs and caveats see tab [Issues]({{page.issues}}) in the GitHub repo.

### CAN API V3 Reference

A generic documentation of the CAN API V3 application programming interface can be found [here](https://uv-software.github.io/CANAPI-Docs/#/).

### Dual-License

Except where otherwise noted, this work is dual-licensed under the terms of the BSD 2-Clause "Simplified" License
and under the terms of the GNU General Public License v3.0 (or any later version).
You can choose between one of them if you use these portions of this work in whole or in part.

### Trademarks

Mac and macOS are trademarks of Apple Inc., registered in the U.S. and other countries. \
Windows is a registered trademark of Microsoft Corporation in the United States and/or other countries. \
Linux is a registered trademark of Linus Torvalds. \
All other company, product and service names mentioned herein may be trademarks, registered trademarks, or service marks of their respective owners.

### Hazard Note

_If you connect your CAN device to a real CAN network when using this library, you might damage your application._
