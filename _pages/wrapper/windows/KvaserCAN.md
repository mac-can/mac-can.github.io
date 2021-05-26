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

Note: _UV&nbsp;Software also provides a CAN&nbsp;API&nbsp;V3 compatible [Wrapper Library](/wrapper/KvaserCAN/) for macOS._

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

### Dual-License

This work is dual-licensed under the terms of the BSD 2-Clause "Simplified" License and under the terms of the GNU General Public License v3.0 (or any later version).
You can choose between one of them if you use this work in whole or in part.

### Trademarks

Windows is a registered trademark of Microsoft Corporation in the United States and/or other countries. \
Mac and macOS are trademarks of Apple Inc., registered in the U.S. and other countries. \
All other company, product and service names mentioned herein are trademarks, registered trademarks or service marks of their respective owners.

### Hazard Note

_If you connect your CAN device to a real CAN network when using this library, you might damage your application._
