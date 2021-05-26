---
permalink: /apps/demo/PCBUSB-Monitor.html
layout: single
toc: true
toc_sticky: true
title: CAN Monitor App for macOS (Demo)
tag: PCBUSB-Monitor
type: demo
latest: http://www.uv-software.de/files/downloads/MacCAN/PCANUSB/Applications/MacCAN_Monitor_App/MacCAN_Monitor.0.3.dmg
readme: http://www.uv-software.de/files/downloads/MacCAN/PCANUSB/Applications/MacCAN_Monitor_App/MacCAN_Monitor.0.3.pdf
---
The MacCAN Monitor App is a little demo program to show the functionally of the [PCBUSB library](/drivers/libPCBUSB.html): the macOS library for PCAN-USB interfaces.

[Download]({{page.latest}}){: .btn .btn--primary} [Readme]({{page.readme}}){: .btn .btn--primary}

## Demo App for PCAN-USB interfaces

The program displays received CAN messages in a table view; its size is limited to 1024 rows.
Furthermore it is possible to send single standard CAN messages with 0 to 8 data bytes.

{% include video id="v0U_WN7s3ao" provider="youtube" %}

Only PCAN-USB devices from PEAK-System Technik GmbH are supported; and only the first channel of a device.
The PCAN-USB interface number is taken from the IO registry.
USB interface and CAN baud rate must be chosen once the program is started; they cannot be changed afterwards.

### System Requirements

- Supported architecture: i386 x86_64
- Supported CAN interfaces: PCAN-USB
- Minimal required library: libPCBUSB.0.9.dylib

### Installation

1. Download the PCBUSB library and run the `install.sh` script in a terminal session.
   Make sure that you have write permission to `/usr/local/lib` folder.
2. Download the MacCAN Monitor App or drag the program icon from the disk image to any folder you like (e.g. `Programs`).

### Change-log

{% for post in site.posts %}
{% if post.categories contains 'Change-log' and post.tag == 'PCBUSB-Monitor' %}
{{ post.content }}
{% endif %}
{% endfor %}

### License

The MacCAN Monitor App for PCAN-USB interfaces is freeware without any warranty or support! \
Please note the copyright and license agreement.

### Credits

Toolbar icons by Oxygen Team (GNU Lesser General Public License, Version 3).

### Trademarks

Mac and macOS are trademarks of Apple Inc., registered in the U.S. and other countries. \
PCAN is a registered trademark of PEAK-System Technik GmbH, Darmstadt, Germany. \
All other company, product and service names mentioned herein are trademarks, registered trademarks or service marks of their respective owners.

### Hazard Note

_If you connect your CAN device to a real CAN network when using this program, you might damage your application._
