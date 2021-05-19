---
permalink: /wrapper/windows/KvaserCAN/
layout: single
toc: true
toc_sticky: true
title: CAN API V3 Wrapper Library for Kvaser CAN Interfaces (Windows)
tag: KvaserCAN-Wrapper
type: wrapper
latest: https://github.com/uv-software/KvaserCAN-Wrapper/releases/download/v0.1/artifacts.zip
srczip: https://github.com/uv-software/KvaserCAN-Wrapper/archive/tags/v0.1.zip
srctar: https://github.com/uv-software/KvaserCAN-Wrapper/archive/tags/v0.1.tar.gz
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

Note: _UV&nbsp;Software also provides a CAN&nbsp;API&nbsp;V3 compatible [Wrapper Library for macOS](/wrapper/KvaserCAN/)._

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

### License

KvaserCAN-Wrapper is free software: you can redistribute it and/or modify
it under the terms of the GNU Lesser General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

KvaserCAN-Wrapper is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License
along with KvaserCAN-Wrapper.  If not, see &lt;http://www.gnu.org/licenses/&gt;.

### Trademarks

Windows is a registered trademark of Microsoft Corporation in the United States and/or other countries. \
Mac and macOS are trademarks of Apple Inc., registered in the U.S. and other countries.

### Hazard Note

_If you connect your CAN device to a real CAN network when using this library, you might damage your application._
