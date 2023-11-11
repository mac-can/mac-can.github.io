---
permalink: /wrapper/windows/KvaserCAN/
layout: single
toc: true
toc_sticky: true
title: CAN API V3 Wrapper Library for Kvaser CAN Interfaces (Windows)
tag: KvaserCAN-Wrapper
type: wrapper
latest: https://github.com/uv-software/KvaserCAN-Wrapper/releases/download/v0.2.5/artifacts.zip
srczip: https://github.com/uv-software/KvaserCAN-Wrapper/archive/tags/v0.2.5.zip
srctar: https://github.com/uv-software/KvaserCAN-Wrapper/archive/tags/v0.2.5.tar.gz
github: https://github.com/uv-software/KvaserCAN-Wrapper
issues: https://github.com/uv-software/KvaserCAN-Wrapper/issues
---
The Kvaser CANlib SDK is a software development kit providing everything you need to develop software for the Kvaser CAN and LIN interfaces on Windows.
For the realization of multi-vendor CAN applications UV&nbsp;Software provides a CAN&nbsp;API&nbsp;V3 compatible wrapper library build upon Kvaser´s CANlib DLL.

[Download]({{page.latest}}){: .btn .btn--primary}
[Sources (zip)]({{page.srczip}}){: .btn .btn--primary}
[Sources (tar.gz)]({{page.srctar}}){: .btn .btn--primary}
[@GitHub]({{page.github}}){: .btn .btn--primary}

## CAN API V3 Wrapper

CAN&nbsp;API&nbsp;V3 is a wrapper specification by UV&nbsp;Software to have a uniform CAN Interface API for various CAN interfaces from different vendors running under multiple operating systems.
The KvaserCAN wrapper library provides a CAN&nbsp;API&nbsp;V3 compatible API for Kvaser´s CANlib DLL on Windows.

The GitHub repository contains the source code for the KvaserCAN wrapper library and several alternatives to build dynamic link libraries, either as a C++ class library (_uvKvaserCAN.dll_), or as a CAN&nbsp;API&nbsp;V3 wrapper library (_u3cankvl.dll_), as well as some example programs and my beloved CAN utilities `can_moni.exe` and `can_test.exe`.

Note: _UV&nbsp;Software also provides a CAN&nbsp;API&nbsp;V3 compatible [Wrapper Library](/wrapper/KvaserCAN/) for macOS._

### Features

|         Feature          | Supported | Remarks |
| ------------------------ |:----------:| ------- |
| CAN 2.0                  | :heavy_check_mark: | Classical CAN |
| CAN FD                   | :heavy_check_mark: | Flexible Data-rate CAN |
| Bit-rate, CAN 2.0        | :heavy_check_mark: | high speed: up to 1 Mbps |
| Bit-rate, CAN FD         | :heavy_check_mark: | nominal: up to 1 Mbps <br/> data phase: up to 8 Mbps |
| 11-bit identifier (STD)  | :heavy_check_mark: | CAN 2.0 and CAN FD |
| 29-bit identifier (XTD)  | :heavy_check_mark: | CAN 2.0 and CAN FD |
| Remote frames (RTR)      | :heavy_check_mark: | CAN 2.0 only |
| Error frames (ERR)       | :heavy_check_mark: | CAN 2.0 and CAN FD |
| Error indicator (ESI)    | :heavy_check_mark: | CAN FD only |
| Bit-rate switching (BRS) | :heavy_check_mark: | CAN FD only |
| Silent operation (MON)   | :heavy_check_mark: | CAN 2.0 and CAN FD |
| Identifier filtering     | :x: | CAN 2.0 and CAN FD |
| Operation modes: | | |
| - Monitor mode enable/disable (MON)        | :heavy_check_mark: | disabled by default |
| - Error frames enable/disable (ERR)        | :heavy_check_mark: | disabled by default |
| - Remote frames disable/enable (NRTR)      | :heavy_check_mark: | enabled by default |
| - Extended frames disable/enable (NXTD)    | :heavy_check_mark: | enabled by default |
| - Shared access enable/disable (SHRD)      | :heavy_check_mark: | disabled by default |
| - Non-ISO CAN FD enable/disable (NISO)     | :heavy_check_mark: | disabled by default |
| - Bit-rate switching enable/disable (BRSE) | :heavy_check_mark: | disabled by default |
| - CAN FD operation enable/disable (FDOE)   | :heavy_check_mark: | disabled by default |
| Bit-rate settings: | | |
| - Pre-defined bit-timing indexes | :heavy_check_mark: | acc. CiA CANopen specification |
| - BTR register values            | :heavy_check_mark: | register fields:<br/>- `freq` (clock frequency in [Hz])<br/>- `brp` (bit-rate prescaler)<br/>- `tseg1` (time segment 1)<br/>- `tseg2` (time segment 2)<br/>- `sjw` (synchronization jump width)<br/>- `sam` (number of samples) |
| Message reception: | | |
| - Message queue (FIFO) | :heavy_check_mark: | _queue size depends on the hardware_ |
|   - Polling            | :heavy_check_mark: | return immediately |
|   - Timed out          | :heavy_check_mark: | wait up to 65'534 milliseconds |
|   - Blocking read      | :heavy_check_mark: | wait infinitely |
| Message transmission:  | | |
| - Acknowledged write   | :heavy_check_mark: | wait up to 65'534 milliseconds  |
| - Buffered write       | :heavy_check_mark: | _buffer size depends on the hardware_ |
| Software Development Kit: | | |
| - CAN API V3           | :heavy_check_mark: | [C API and C++ API](/wrapper/canapi-v3/) by UV&nbsp;Software |
| - Dynamic link library | :heavy_check_mark: | `u3cankvl.dll`, `uvKvaserCAN.dll` |
| - Static library       | :heavy_check_mark: | `u3cankvl.lib`, `uvKvaserCAN.lib` |
| - 32-bit version (x86) | :heavy_check_mark: | supported |
| - 64-bit version (x64) | :heavy_check_mark: | supported |
| - Source code          | :heavy_check_mark: | BDS-2-Clause or GPL-3.0-or-later |
| - Python wrapper       | :x: | Python 3.7 |
| - macOS wrapper        | :heavy_check_mark: | [macOS Driver and SDK](/wrapper/KvaserCAN/) |
| - Utilities            | :heavy_check_mark: | CLI utilities `can_moni` and `can_test`|
| - Examples             | :heavy_check_mark: | C, C++, Python |

### Change-log

{% for post in site.posts %}
{% if post.categories contains 'Change-log' and post.tag == 'KvaserCAN-Wrapper' %}
{{ post.content }}
{% endif %}
{% endfor %}

### Supported Devices

For a list of supported device see [Kvaser´s website](https://www.kvaser.com/download/#?categories=development-kits-and-tools).

### Known Bugs and Caveats

For a list of known bugs and caveats see tab [Issues]({{page.issues}}) in the GitHub repo.

### CAN API V3 Reference

A generic documentation of the CAN API V3 application programming interface can be found [here](https://uv-software.github.io/CANAPI-Docs). 

### Dual-License

This work is dual-licensed under the terms of the BSD 2-Clause "Simplified" License and under the terms of the GNU General Public License v3.0 (or any later version).
You can choose between one of them if you use this work in whole or in part.

### Trademarks

Windows is a registered trademark of Microsoft Corporation in the United States and/or other countries. \
Mac and macOS are trademarks of Apple Inc., registered in the U.S. and other countries. \
All other company, product and service names mentioned herein may be trademarks, registered trademarks, or service marks of their respective owners.

### Hazard Note

_If you connect your CAN device to a real CAN network when using this library, you might damage your application._
