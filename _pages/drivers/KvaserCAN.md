---
permalink: /drivers/KvaserCAN/
layout: single
toc: true
toc_sticky: true
title: macOS User-Space Driver for CAN Leaf Interfaces from Kvaser
tag: MacCAN-KvaserCAN
type: driver
latest: https://github.com/mac-can/MacCAN-KvaserCAN/releases/download/v0.1/artifacts.zip
srczip: https://github.com/mac-can/MacCAN-KvaserCAN/archive/tags/v0.1.zip
srctar: https://github.com/mac-can/MacCAN-KvaserCAN/archive/tags/v0.1.tar.gz
github: https://github.com/mac-can/MacCAN-KvaserCAN
issues: https://github.com/mac-can/MacCAN-KvaserCAN/issues
---
The Swedish company Kvaser AB supplies advanced CAN solutions to engineers designing and deploying systems for manifold areas of applications.
They offer a wide range of CAN hardware and CAN software, mainly for applications under Windows but also under Linux.
A macOS user-space driver for CAN Leaf Interfaces from Kvaser is provided by UV&nbsp;Software.

[~~Download~~]({{page.latest}}){: .btn .btn--light-outline}
[~~Sources (zip)~~]({{page.srczip}}){: .btn .btn--light-outline}
[~~Sources (tar.gz)~~]({{page.srctar}}){: .btn .btn--light-outline}
[@GitHub]({{page.github}}){: .btn .btn--primary}

## MacCAN-KvaserCAN Driver

The macOS driver for CAN Leaf interfaces from Kvaser is based on MacCAN-Core which is an abstraction (or rather a wrapper) of Apple´s IOUsbKit to create USB user-space drivers for CAN interfaces from various vendors under macOS.
The GitHub repository contains the source code for the MacCAN-KvaserCAN driver and several alternatives to build dynamic libraries for macOS, either as a C++ class library (_libKvaserCAN_), or as a CAN&nbsp;API&nbsp;V3 wrapper library (_libUVCANKVL_), as well as some example programs and my beloved CAN utilities `can_moni` and `can_test`.

The MacCAN-KvaserCAN driver comes with an CAN&nbsp;API&nbsp;V3 compatible API.
CAN&nbsp;API&nbsp;V3 is a wrapper specification by UV&nbsp;Software to have a uniform CAN Interface API for various CAN interfaces from different vendors running under multiple operating systems. See header file `CANAPI.h` for the CAN&nbsp;API&nbsp;V3 interface.

Note: _This project does not aim to implement Kvaser´s CANlib API on macOS._

### Supported Devices

Only the following devices from Kvaser AB are supported:
- Kvaser Leaf Light v2 (EAN: 73-30130-00685-0)

For technical specifications, prices and delivery terms see [Kvaser´s website](https://www.kvaser.com/products-services/our-products/#/?pc_int=usb).

### Known Bugs and Caveats

For a list of known bugs and caveats see tab [Issues]({{page.issues}}) in the GitHub repo.

### License

MacCAN-KvaserCAN is free software: you can redistribute it and/or modify
it under the terms of the GNU Lesser General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

MacCAN-KvaserCAN is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License
along with MacCAN-KvaserCAN.  If not, see &lt;http://www.gnu.org/licenses/&gt;.

### Trademarks

Mac and macOS are trademarks of Apple Inc., registered in the U.S. and other countries. \
Windows is a registered trademark of Microsoft Corporation in the United States and/or other countries. \
Linux is a registered trademark of Linus Torvalds. \
All other company, product and service names mentioned herein are trademarks, registered trademarks or service marks of their respective owners.

### Hazard Note

_If you connect your CAN device to a real CAN network when using this library, you might damage your application._
