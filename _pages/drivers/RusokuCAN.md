---
permalink: /drivers/RusokuCAN/
layout: single
toc: true
toc_sticky: true
title: macOS&reg; User-Space Driver for TouCAN USB Interfaces from Rusoku
tag: MacCAN-TouCAN
type: driver
latest: https://github.com/mac-can/RusokuCAN/releases/download/v0.2/artifacts.zip
srczip: https://github.com/mac-can/RusokuCAN/archive/tags/v0.2.zip
srctar: https://github.com/mac-can/RusokuCAN/archive/tags/v0.2.tar.gz
github: https://github.com/mac-can/RusokuCAN
issues: https://github.com/mac-can/RusokuCAN/issues
---
Rusoku Technologies is an innovative engineering team based in Lithuania, Europe.
They offer CAN adapters at a reasonable price;
drivers and utilities for Windows&reg; and Linux&reg; are available as open source.
A macOS user-space driver for TouCAN USB interfaces from Rusoku is provided by UV&nbsp;Software.

[Download]({{page.latest}}){: .btn .btn--primary}
[Sources (zip)]({{page.srczip}}){: .btn .btn--primary}
[Sources (tar.gz)]({{page.srctar}}){: .btn .btn--primary}
[@GitHub]({{page.github}}){: .btn .btn--primary}

## MacCAN-TouCAN Driver

The macOS driver for TouCAN USB Interfaces from Rusoku is based on MacCAN-Core which is an abstraction (or rather a wrapper) of Apple´s IOUsbKit to create USB user-space drivers for CAN interfaces from various vendors under macOS.
The GitHub repository contains the source code for the MacCAN-TouCAN driver and several alternatives to build dynamic libraries for macOS, either as a C++ class library (_libTouCAN_), or as a CAN&nbsp;API&nbsp;V3 wrapper library (_libUVCANTOU_), as well as some example programs and my beloved CAN utilities `can_moni` and `can_test`.

CAN&nbsp;API&nbsp;V3 is a wrapper specification by UV&nbsp;Software to have a uniform CAN Interface API for various CAN interfaces from different vendors running under multiple operating systems. See header file `CANAPI.h` for the CAN&nbsp;API&nbsp;V3 wrapper specification.

### Supported Devices

Only the following devices from Rusoku Technologies are supported:
- TouCAN USB (Model F4FS1)

For technical specifications, prices and delivery conditions see [Rusoku´s website](https://www.rusoku.com/products).

### Change-log

{% for post in site.posts %}
{% if post.categories contains 'Change-log' and post.tag == 'MacCAN-TouCAN' %}
{{ post.content }}
{% endif %}
{% endfor %}

### Known Bugs and Caveats

For a list of known bugs and caveats see [Issues]({{page.issues}}) tracked in the GitHub repo.

### License

MacCAN-TouCAN is free software: you can redistribute it and/or modify
it under the terms of the GNU Lesser General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

MacCAN-TouCAN is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License
along with MacCAN-TouCAN.  If not, see &lt;http://www.gnu.org/licenses/&gt;.

### Trademarks

Mac and macOS are trademarks of Apple Inc., registered in the U.S. and other countries. \
Windows is a registered trademark of Microsoft Corporation in the United States and/or other countries. \
Linux is a registered trademark of Linus Torvalds. \
All other company, product and service names mentioned herein are trademarks, registered trademarks or service marks of their respective owners.

### Hazard Note

_If you connect your CAN device to a real CAN network when using this library, you might damage your application._
