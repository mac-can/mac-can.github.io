---
permalink: /drivers/KvaserCAN/
layout: single
toc: true
toc_sticky: true
title: macOS User-Space Driver for CAN Leaf Interfaces from Kvaser
tag: MacCAN-KvaserCAN
type: driver
latest: https://github.com/mac-can/MacCAN-KvaserCAN/releases/download/v0.1.1/artifacts.zip
srczip: https://github.com/mac-can/MacCAN-KvaserCAN/archive/tags/v0.1.1.zip
srctar: https://github.com/mac-can/MacCAN-KvaserCAN/archive/tags/v0.1.1.tar.gz
github: https://github.com/mac-can/MacCAN-KvaserCAN
issues: https://github.com/mac-can/MacCAN-KvaserCAN/issues
---
The Swedish company Kvaser AB supplies advanced CAN solutions to engineers designing and deploying systems for manifold areas of applications.
They offer a wide range of CAN hardware and CAN software, mainly for applications under Windows but also under Linux.
A macOS user-space driver for CAN Leaf Interfaces from Kvaser is provided by UV&nbsp;Software.

[Download]({{page.latest}}){: .btn .btn--primary}
[Sources (zip)]({{page.srczip}}){: .btn .btn--primary}
[Sources (tar.gz)]({{page.srctar}}){: .btn .btn--primary}
[@GitHub]({{page.github}}){: .btn .btn--primary}

## MacCAN-KvaserCAN Driver

The macOS driver for CAN Leaf interfaces from Kvaser is based on MacCAN-Core which is an abstraction (or rather a wrapper) of Apple´s IOUsbKit to create USB user-space drivers for CAN interfaces from various vendors under macOS.
The GitHub repository contains the source code for the MacCAN-KvaserCAN driver and several alternatives to build dynamic libraries for macOS, either as a C++ class library (_libKvaserCAN_), or as a CAN&nbsp;API&nbsp;V3 wrapper library (_libUVCANKVL_), as well as some example programs and my beloved CAN utilities `can_moni` and `can_test`.

The MacCAN-KvaserCAN driver comes with an CAN&nbsp;API&nbsp;V3 compatible API.
CAN&nbsp;API&nbsp;V3 is a wrapper specification by UV&nbsp;Software to have a uniform CAN Interface API for various CAN interfaces from different vendors running under multiple operating systems. See header file `CANAPI.h` for the CAN&nbsp;API&nbsp;V3 interface.

Note: _This project does not aim to implement Kvaser´s CANlib API on macOS._

### Features

|         Feature          |   Leaf<br/>Light   |    Leaf<br/>Pro    | Remarks |
| ------------------------ |:------------------:|:------------------:| ------- |
| CAN 2.0                  | :heavy_check_mark: | :heavy_check_mark: |  Classical CAN |
| CAN FD                   | :x: | :x: |  Flexible Data-rate CAN |
| Bit-rate, CAN 2.0        | :heavy_check_mark: | :heavy_check_mark: | high speed: up to 1 Mbps |
| Bit-rate, CAN FD         | :x: | :x: | nominal: up to 1 Mbps <br/> data phase: up to 8 Mbps |
| 11-bit identifier (STD)  | :heavy_check_mark: | :heavy_check_mark: | CAN 2.0 and CAN FD |
| 29-bit identifier (XTD)  | :heavy_check_mark: | :heavy_check_mark: | CAN 2.0 and CAN FD |
| Remote frames (RTR)      | :heavy_check_mark: | :heavy_check_mark: | CAN 2.0 only |
| Error frames (ERR)       | :heavy_check_mark: | :heavy_check_mark: | CAN 2.0 and CAN FD |
| Error indicator (ESI)    | :x: | :x: | CAN FD only |
| Bit-rate switching (BRS) | :x: | :x: | CAN FD only |
| Silent operation (MON)   | :x: | :heavy_check_mark: | CAN 2.0 and CAN FD |
| Identifier filtering     | :x: | :x: | CAN 2.0 and CAN FD |
| Operation modes: | | | |
| - Monitor mode enable/disable (MON)        | :x: | :heavy_check_mark: | disabled by default |
| - Error frames enable/disable (ERR)        | :heavy_check_mark: | :heavy_check_mark: | disabled by default |
| - Remote frames disable/enable (NRTR)      | :heavy_check_mark: | :heavy_check_mark: | enabled by default |
| - Extended frames disable/enable (NXTD)    | :heavy_check_mark: | :heavy_check_mark: | enabled by default |
| - Shared access enable/disable (SHRD)      | :x: | :x: | _not supported_ |
| - Non-ISO CAN FD enable/disable (NISO)     | :x: | :x: | _not supported_ |
| - Bit-rate switching enable/disable (BRSE) | :x: | :x: | disabled by default |
| - CAN FD operation enable/disable (FDOE)   | :x: | :x: | disabled by default |
| Bit-rate settings: | | | |
| - Pre-defined bit-timing indexes | :heavy_check_mark: | :heavy_check_mark: | acc. CiA CANopen specification |
| - BTR register values            | :heavy_check_mark: | :heavy_check_mark: | register fields:<br/>- `freq` (clock frequency in [Hz])<br/>- `brp` (bit-rate prescaler)<br/>- `tseg1` (time segment 1)<br/>- `tseg2` (time segment 2)<br/>- `sjw` (synchronization jump width)<br/>- `sam` (number of samples) |
| Message reception: | | | |
| - Message queue (FIFO) | :heavy_check_mark: | :heavy_check_mark: | up to 64K CAN messages |
|   - Polling            | :heavy_check_mark: | :heavy_check_mark: | return immediately |
|   - Timed out          | :heavy_check_mark: | :heavy_check_mark: | wait up to 65'534 milliseconds |
|   - Blocking read      | :heavy_check_mark: | :heavy_check_mark: | wait infinitely |
| Message transmission: | | | |
| - Acknowledged write | :heavy_check_mark: | :heavy_check_mark: | wait up to 65'534 milliseconds  |
| - Buffered write     | :heavy_check_mark: | :heavy_check_mark: | _buffer size depends on the hardware_ |
| Software Development Kit: | | | |
| - Kvaser CANlib   | :x: | :x: | _not available_ |
| - CAN API V3      | :heavy_check_mark: | :heavy_check_mark: | [C API and C++ API](/wrapper/canapi-v3/) by UV&nbsp;Software |
| - Dynamic library | :heavy_check_mark: | :heavy_check_mark: | `libUVCANKVL.dylib`, `libKvaserCAN.dylib` |
| - Static library  | :heavy_check_mark: | :heavy_check_mark: | `libUVCANKVL.a`, `libKvaserCAN.a` |
| - Source code     | :heavy_check_mark: | :heavy_check_mark: | BDS-2-Clause or GPL-3.0-or-later |
| - Apple silicon   | :grey_question: | :grey_question: | _not tested_ |
| - Swift wrapper   | :heavy_check_mark: | :heavy_check_mark: | Swift 5.4 (including SPM) |
| - Python wrapper  | :heavy_check_mark: | :heavy_check_mark: | Python 2.7 and 3.8 |
| - Windows wrapper | :heavy_check_mark: | :heavy_check_mark: | [CAN API V3 Wrapper Library](/wrapper/windows/KvaserCAN/) |
| - Utilities       | :heavy_check_mark: | :heavy_check_mark: | CLI utilities `can_moni` and `can_test`|
| - Examples        | :heavy_check_mark: | :heavy_check_mark: | C, C++, Swift, Python |

### Change-log

{% for post in site.posts %}
{% if post.categories contains 'Change-log' and post.tag == 'MacCAN-KvaserCAN' %}
{{ post.content }}
{% endif %}
{% endfor %}

### Supported Devices

Only the following devices from Kvaser AB are supported:
- Kvaser Leaf Light v2 (EAN: 73-30130-00685-0)
- Kvaser Leaf Pro HS v2 (EAN: 73-30130-00843-4)

Note: _**Leaf Pro HS v2** devices can currently only be operated in **CAN 2.0 mode**!_

For technical specifications, prices and delivery terms see [Kvaser´s website](https://www.kvaser.com/products-services/our-products/#/?pc_int=usb).

### Known Bugs and Caveats

For a list of known bugs and caveats see tab [Issues]({{page.issues}}) in the GitHub repo.

### Dual-License

This work is dual-licensed under the terms of the BSD 2-Clause "Simplified" License and under the terms of the GNU General Public License v3.0 (or any later version).
You can choose between one of them if you use this work in whole or in part.

### Trademarks

Mac and macOS are trademarks of Apple Inc., registered in the U.S. and other countries. \
Windows is a registered trademark of Microsoft Corporation in the United States and/or other countries. \
Linux is a registered trademark of Linus Torvalds. \
All other company, product and service names mentioned herein are trademarks, registered trademarks or service marks of their respective owners.

### Hazard Note

_If you connect your CAN device to a real CAN network when using this library, you might damage your application._
