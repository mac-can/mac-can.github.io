---
permalink: /drivers/
layout: single
toc: true
toc_sticky: true
title: macOS&reg; User-Space Drivers for USB-to-CAN Interfaces
---
There are many companies in the world offering multifarious CAN hardware and CAN software.
Unfortunately, few of them offer a driver for the Mac.
UV&nbsp;Software provides USB-to-CAN user-space drivers for macOS&reg;.

## macOS&reg; User-Space Driver for TouCAN USB Interfaces from Rusoku

Rusoku Technologies is an innovative engineering team based in Lithuania, Europe.
They offer CAN adapters at a reasonable price;
drivers and utilities for Windows&reg; and Linux&reg; are available as open source.
A macOS user-space driver for TouCAN USB interfaces from Rusoku is provided by UV&nbsp;Software.

{% for page in site.pages %}
{% if page.type == 'driver' and page.tag == 'MacCAN-TouCAN' %}
[Download]({{page.latest}}){: .btn .btn--primary}
[Sources (zip)]({{page.srczip}}){: .btn .btn--primary}
[Sources (tar.gz)]({{page.srctar}}){: .btn .btn--primary}
[More...](/drivers/RusokuCAN/){: .btn .btn--primary}
{% endif %}
{% endfor %}

## macOS&reg; User-Space Driver for CAN Leaf Interfaces from Kvaser

The Swedish company Kvaser AB supplies advanced CAN solutions to engineers designing and deploying systems for manifold areas of applications.
They offer a wide range of CAN hardware and CAN software, mainly for applications under Windows&reg; but also under Linux&reg;.
A macOS user-space driver for CAN Leaf Interfaces from Kvaser is provided by UV&nbsp;Software.

{% for page in site.pages %}
{% if page.type == 'driver' and page.tag == 'MacCAN-KvaserCAN' %}
[~~Download~~]({{page.latest}}){: .btn .btn--light-outline}
[~~Sources (zip)~~]({{page.srczip}}){: .btn .btn--light-outline}
[~~Sources (tar.gz)~~]({{page.srctar}}){: .btn .btn--light-outline}
[More...](/drivers/KvaserCAN/){: .btn .btn--primary}
{% endif %}
{% endfor %}

## macOS&reg; User-Space Driver for PCAN-USB Interfaces from PEAK-System

PEAK-System is a leading provider of hardware, software, and services for the mobile and industrial communication sector with emphasis on the field buses CAN and LIN.
The PCBUSB library realizes a USB-to-CAN user-space driver under macOS for PCAN-USB interfaces from PEAK-System.

{% for page in site.pages %}
{% if page.type == 'driver' and page.tag == 'PCBUSB-Library' %}
[Download]({{page.latest}}){: .btn .btn--primary}
[Readme]({{page.readme}}){: .btn .btn--primary}
[mac-can.com](https://mac-can.com){: .btn .btn--primary}
[More...](/drivers/libPCBUSB.html){: .btn .btn--primary}
{% endif %}
{% endfor %}
