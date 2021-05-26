---
permalink: /wrapper/PCANBasic/
layout: single
toc: true
toc_sticky: true
title: macOS Wrapper Library for PCAN-USB Interfaces from PEAK-System
tag: PCBUSB-Wrapper
type: wrapper
latest: https://github.com/mac-can/PCBUSB-Wrapper/releases/download/v0.2/artifacts.zip
srczip: https://github.com/mac-can/PCBUSB-Wrapper/archive/tags/v0.2.zip
srctar: https://github.com/mac-can/PCBUSB-Wrapper/archive/tags/v0.2.tar.gz
github: https://github.com/mac-can/PCBUSB-Wrapper
issues: https://github.com/mac-can/PCBUSB-Wrapper/issues
---
The PCBUSB library realizes a USB-to-CAN user-space driver under macOS for PCAN-USB interfaces from PEAK-System Technik, Darmstadt.
Its API is almost compatible to PEAK´s PCANBasic DLL on Windows.
For the realization of multi-vendor applications UV&nbsp;Software provides a CAN&nbsp;API&nbsp;V3 compatible wrapper library.

[Download]({{page.latest}}){: .btn .btn--primary}
[Sources (zip)]({{page.srczip}}){: .btn .btn--primary}
[Sources (tar.gz)]({{page.srctar}}){: .btn .btn--primary}
[@GitHub]({{page.github}}){: .btn .btn--primary}

## CAN API V3 Wrapper

CAN&nbsp;API&nbsp;V3 is a wrapper specification by UV&nbsp;Software to have a uniform CAN Interface API for various CAN interfaces from different vendors running under multiple operating systems.
The PCBUSB library comes with a PCANBasic compatible API.
The PCBUSB wrapper library provides a CAN&nbsp;API&nbsp;V3 compatible API for it.

The GitHub repository contains the source code for the PCBUSB wrapper library and several alternatives to build dynamic libraries for macOS, either as a C++ class library (_libPeakCAN_), or as a CAN&nbsp;API&nbsp;V3 wrapper library (_libUVCANPCB_), as well as some example programs and my beloved CAN utilities `can_moni` and `can_test`.

Note: _UV&nbsp;Software also provides a CAN&nbsp;API&nbsp;V3 compatible [Wrapper Library](/wrapper/windows/PCANBasic/) for PEAK´s PCANBasic DLL for Windows._

### Change-log

{% for post in site.posts %}
{% if post.categories contains 'Change-log' and post.tag == 'PCBUSB-Wrapper' %}
{{ post.content }}
{% endif %}
{% endfor %}

### Supported Devices

For a list of supported device see page [PCBUSB library](/drivers/libPCBUSB.html/#supported-devices).

### Known Bugs and Caveats

For a list of known bugs and caveats see tab [Issues]({{page.issues}}) in the GitHub repo.

### Dual-License

This work is dual-licensed under the terms of the BSD 2-Clause "Simplified" License and under the terms of the GNU General Public License v3.0 (or any later version).
You can choose between one of them if you use this work in whole or in part.

### Trademarks

Mac and macOS are trademarks of Apple Inc., registered in the U.S. and other countries. \
Windows is a registered trademark of Microsoft Corporation in the United States and/or other countries. \
PCAN is a registered trademark of PEAK-System Technik GmbH, Darmstadt, Germany. \
All other company, product and service names mentioned herein are trademarks, registered trademarks or service marks of their respective owners.

### Hazard Note

_If you connect your CAN device to a real CAN network when using this library, you might damage your application._
