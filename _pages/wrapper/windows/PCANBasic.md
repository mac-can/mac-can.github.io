---
permalink: /wrapper/windows/PCANBasic/
layout: single
toc: true
toc_sticky: true
title: CAN API V3 Wrapper Library for PEAK PCAN Interfaces (Windows)
tag: PCANBasic-Wrapper
type: wrapper
latest: https://github.com/uv-software/PCANBasic-Wrapper/releases/download/v0.4.1/artifacts.zip
srczip: https://github.com/uv-software/PCANBasic-Wrapper/archive/tags/v0.4.1.zip
srctar: https://github.com/uv-software/PCANBasic-Wrapper/archive/tags/v0.4.1.tar.gz
github: https://github.com/uv-software/PCANBasic-Wrapper
issues: https://github.com/uv-software/PCANBasic-Wrapper/issues
---
The PCANBasic DLL provides an easy to use API (Application Programming Interface) for all PCAN interfaces from PEAK-System Technik, Darmstadt.
For the realization of multi-vendor applications UV&nbsp;Software provides a CAN&nbsp;API&nbsp;V3 compatible wrapper library build upon PEAK´s PCANBasic DLL.

[Download]({{page.latest}}){: .btn .btn--primary}
[Sources (zip)]({{page.srczip}}){: .btn .btn--primary}
[Sources (tar.gz)]({{page.srctar}}){: .btn .btn--primary}
[@GitHub]({{page.github}}){: .btn .btn--primary}

## CAN API V3 Wrapper

CAN&nbsp;API&nbsp;V3 is a wrapper specification by UV&nbsp;Software to have a uniform CAN Interface API for various CAN interfaces from different vendors running under multiple operating systems.
The PCANBasic wrapper library provides a CAN&nbsp;API&nbsp;V3 compatible API for PEAK´s PCANBasic DLL on Windows.

The GitHub repository contains the source code for the PCANBasic wrapper library and several alternatives to build dynamic link libraries, either as a C++ class library (_uvPeakCAN.dll_), or as a CAN&nbsp;API&nbsp;V3 wrapper library (_u3canpcb.dll_), as well as some example programs and my beloved CAN utilities `can_moni.exe` and `can_test.exe`.

Note: _UV&nbsp;Software also provides a CAN&nbsp;API&nbsp;V3 compatible [Wrapper Library](/wrapper/PCANBasic/) for macOS._

### Change-log

{% for post in site.posts %}
{% if post.categories contains 'Change-log' and post.tag == 'PCANBasic-Wrapper' %}
{{ post.content }}
{% endif %}
{% endfor %}

### Supported Devices

For a list of supported device see [PEAK´s website](https://www.peak-system.com/PCAN-Basic.239.0.html).

### Known Bugs and Caveats

For a list of known bugs and caveats see tab [Issues]({{page.issues}}) in the GitHub repo.

### Dual-License

This work is dual-licensed under the terms of the BSD 2-Clause "Simplified" License and under the terms of the GNU General Public License v3.0 (or any later version).
You can choose between one of them if you use this work in whole or in part.

### Trademarks

Windows is a registered trademark of Microsoft Corporation in the United States and/or other countries. \
Mac and macOS are trademarks of Apple Inc., registered in the U.S. and other countries. \
PCAN is a registered trademark of PEAK-System Technik GmbH, Darmstadt, Germany. \
All other company, product and service names mentioned herein are trademarks, registered trademarks or service marks of their respective owners.

### Hazard Note

_If you connect your CAN device to a real CAN network when using this library, you might damage your application._
