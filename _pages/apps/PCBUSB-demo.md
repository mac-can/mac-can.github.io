---
permalink: /apps/demo/PCBUSB-Monitor.html
layout: single
toc: true
toc_sticky: true
title: CAN Monitor App for macOS (Demo)
tag: PCBUSB-Monitor
type: demo
latest: http://www.uv-software.de/files/downloads/MacCAN/PCANUSB/Applications/MacCAN_Monitor_App/MacCAN_Monitor.0.4_uni.dmg
x86_64: http://www.uv-software.de/files/downloads/MacCAN/PCANUSB/Applications/MacCAN_Monitor_App/MacCAN_Monitor.0.4_x86.dmg
readme: http://www.uv-software.de/files/downloads/MacCAN/PCANUSB/Applications/MacCAN_Monitor_App/MacCAN_Monitor.0.4.pdf
---
The MacCAN Monitor App is a little demo program to show the functionally of the [PCBUSB library](/drivers/libPCBUSB.html): the macOS Library for PCAN-USB interfaces.

[Download (arm64)]({{page.latest}}){: .btn .btn--primary}
[Download (x86_64)]({{page.x86_64}}){: .btn .btn--primary}
[Readme]({{page.readme}}){: .btn .btn--primary}

## Demo App for PCAN-USB interfaces

The program displays received CAN messages in a table view.

{% include video id="v0U_WN7s3ao" provider="youtube" %}

Furthermore it is possible to send single standard CAN messages with 0 to 8 data bytes.

**Limitations (Demo Program):**

- CAN channel and CAN bit rate must be chosen once the program is started; they cannot be changed afterwards.
- PCAN-USB FD devices can only be operated in CAN Classic mode (CAN 2.0).
- The size of the table view is limited to 1024 rows.
- The size of the trace file is limited to 100K frames.

### macOS<sup>&reg;</sup> Library for PCAN-USB Interfaces

The dynamic library libPCBUSB is running under macOS 10.13 and later (Intel architecture and Apple silicon).
The API is almost compatible to PEAK´s PCANBasic DLL on Windows.
See the [MacCAN](https://www.mac-can.com/) website to learn more.

### Supported Devices

Only the following devices from PEAK-System Technik are supported:
- PCAN-USB (product code: IPEH-002021, IPEH-002022)
- PCAN-USB FD (product code: IPEH-004022)

### Required Library Version

The minimum required library version is v0.9 (Build 902 of June 25, 2020), but _Latest is Greatest_.

### License

This work is licensed under the terms of the BSD 2-Clause "Simplified" License.

### Installation

1. Download the PCBUSB Library and run the `install.sh` script in a terminal session. Make sure that you have write permission to `/usr/local` folder
2. Download the MacCAN Monitor App, open the disk image and drag-and-drop the program icon to your Applications folder (or any other folder you like).

### Change-log

{% for post in site.posts %}
{% if post.categories contains 'Change-log' and post.tag == 'PCBUSB-Monitor' %}
{{ post.content }}
{% endif %}
{% endfor %}

### Credits

Toolbar icons by Oxygen Team (GNU Lesser General Public License). \
Apple M1 support by Sebastião Beirão (https://github.com/sebashb).

### Trademarks

Mac and macOS are trademarks of Apple Inc., registered in the U.S. and other countries. \
PCAN is a registered trademark of PEAK-System Technik GmbH, Darmstadt, Germany. \
All other company, product and service names mentioned herein may be trademarks, registered trademarks or service marks of their respective owners.

### Hazard Note

_If you connect your CAN device to a real CAN network when using this program, you might damage your application._
