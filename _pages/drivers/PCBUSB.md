---
permalink: /drivers/libPCBUSB.html
layout: single
toc: true
toc_sticky: true
title: macOS User-Space Driver for PCAN-USB Interfaces from PEAK-System
tag: PCBUSB-Library
type: driver
latest_x86_64: http://www.uv-software.de/files/downloads/MacCAN/PCANUSB/Library/OS_X_Library_for_PCANUSB_v0.10.1.tar.gz
latest_arm64: http://www.uv-software.de/files/downloads/MacCAN/PCANUSB/Library/macOS_Library_for_PCANUSB_v0.10.1.tar.gz
readme: http://www.uv-software.de/files/downloads/MacCAN/PCANUSB/Library/macOS_Library_for_PCANUSB_v0.10.1.readme
---
The PCBUSB library realizes a USB-to-CAN user-space driver under macOS for PCAN-USB interfaces from PEAK-System Technik, Darmstadt.
It supports up to 8 PCAN-USB and PCAN-USB FD devices.
The library offers an easy to use API to read received CAN messages from a 64K message queue and to transmit CAN messages.
Standard CAN frames (11-bit identifier) as well as extended CAN frames (29-bit identifier) are supported.
The PCAN-USB FD device can be operated in CAN 2.0 and CAN FD mode.

[Download (x86_64)]({{page.latest_x86_64}}){: .btn .btn--primary}
[Download (arm64)]({{page.latest_arm64}}){: .btn .btn--primary}
[Readme]({{page.readme}}){: .btn .btn--primary}
[mac-can.com](https://mac-can.com){: .btn .btn--primary}

## PCBUSB Library

The dynamic library libPCBUSB is running under macOS 10.13 and later (Intel architecture and Apple silicon).
The API is almost compatible to PEAK´s PCANBasic DLL on Windows.
See the [MacCAN](https://www.mac-can.com/) website to learn more.

The library comes with an Objective-C wrapper and a Demo App: [MacCAN Monitor App](/apps/demo/PCBUSB-Monitor.html) \
Furthermore, it can be used with the Qt Serial Bus API on a Mac: [Qt CAN Bus example](https://doc.qt.io/qt-5/qtserialbus-can-example.html)

Note: _UV&nbsp;Software also provides a CAN&nbsp;API&nbsp;V3 compatible [Wrapper Library](/wrapper/PCANBasic/) for macOS._

### Features

| Feature | Supported | Remarks |
| ------- |:---------:| ------- |
| CAN 2.0 | :heavy_check_mark: | supported by PCAN-USB, PCAN-USB FD |
| CAN FD | :heavy_check_mark: | supported by PCAN-USB FD only |
| Bit-rate, CAN 2.0 | :heavy_check_mark: | high speed: up to 1 Mbps |
| Bit-rate, CAN FD | :heavy_check_mark: | nominal: up to 1 Mbps <br/> data phase: up to 8 Mbps |
| 11-bit identifier (STD) | :heavy_check_mark: | CAN 2.0 and CAN FD mode |
| 29-bit identifier (XTD) | :heavy_check_mark: | CAN 2.0 and CAN FD mode |
| Remote frames (RTR) | :heavy_check_mark: | CAN 2.0 mode only |
| Error frames (ERR) | :x: | _not realized yet_ |
| Error indicator (ESI) | :heavy_check_mark: | CAN FD mode only |
| Monitor mode (MON) | :heavy_check_mark: | listen-only mode (transmitter off) |
| Receive queue (FIFO) | :heavy_check_mark: | up to 65'536 CAN messages |
| Blocking read | :heavy_check_mark: | via a file descriptor and system call `select`; see [example](https://gist.github.com/mac-can/8fea17c5e8398478a2e065dd37fe5f6f) |
| Identifier filtering | :x: | _not realized yet_ |
| Non-ISO CAN FD mode | (:heavy_check_mark:) | _HW settings of the device cannot be changed by the library_ |
| Software interface (API) | :heavy_check_mark: | compatible to PEAK´s PCANBasic API _with some limitations_ |
| Dynamic library (`.dylib`) | :heavy_check_mark: | for Intel architecture and as Universal macOS Binary |
| Static library (`.a`) | :x: | _not available_ |
| Source code | :x: | **_not available_** |
| M1 Chip | :heavy_check_mark: | Universal macOS Binary |
| Objective-C Wrapper | :heavy_check_mark: | available |
| Python Wrapper | :heavy_check_mark: | available |
| Swift Wrapper | :x: | _not available_ |
| CAN&nbsp;API&nbsp;V3 Wrapper | :heavy_check_mark: | available for [macOS](/wrapper/PCANBasic/) and [Windows](/wrapper/windows/PCANBasic/) |
| Utilities | :heavy_check_mark: | CLI utilities: [`can_moni`](https://www.uv-software.de/dokuwiki/doku.php?id=uvs:programs:can_moni_mac) and [`can_test`](https://www.uv-software.de/dokuwiki/doku.php?id=uvs:programs:can_moni_mac) |
| Examples | :heavy_check_mark: | C++, Python, Objective-C ([Demo App](https://github.com/mac-can/PCBUSB-Monitor)) |

### Change-log

{% for post in site.posts %}
{% if post.categories contains 'Change-log' and post.tag == 'PCBUSB-Library' %}
{{ post.content }}
{% endif %}
{% endfor %}

### Supported Devices

Only the following devices from PEAK-System Technik are supported:
- PCAN-USB (product code: IPEH-002021, IPEH-002022)

Since version 0.8 (Build 689 of September 20, 2017):
- PCAN-USB FD (product code: IPEH-004022)

For technical specifications, prices and delivery terms see [PEAK´s website](https://www.peak-system.com/Product-Overview.333.0.html).

### Known Bugs and Caveats

For a list of known bugs and caveats see the `README` file delivered with each release.

### License

The PCBUSB library is freeware without any warranty or support! \
Please note the copyright and license agreement.

### Trademarks

Mac and macOS are trademarks of Apple Inc., registered in the U.S. and other countries. \
PCAN is a registered trademark of PEAK-System Technik GmbH, Darmstadt, Germany. \
Qt is a registered trademark of The Qt Company Ltd. and its subsidiaries. \
All other company, product and service names mentioned herein are trademarks, registered trademarks or service marks of their respective owners.

### Hazard Note

_If you connect your CAN device to a real CAN network when using this library, you might damage your application._
