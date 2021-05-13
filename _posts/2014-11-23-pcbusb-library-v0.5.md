---
layout: single
title:  "PCBUSB-Library - Version 0,5 released"
tag: PCBUSB-Library
categories: Change-log Drivers macOS Peak PCBUSB
artifacts: https://www.uv-software.de/dokuwiki/doku.php?id=uvs:programs:pcbusb_library
release: Version 0.5 (Build 370 of November 23, 2014)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Feature 'Reading/Writing of parameter `PCAN_DEVICE_NUMBER` implemented.
- Fixed issue \#104 'Hot plugging was not detected by the library/driver'.
- Fixed issue \#117 'Permission for libPCBUSB.x.y.lib wrong' (chmod 755).
- Return codes of API functions harmonized with PCANBasic.dll (1.3.3.61).
