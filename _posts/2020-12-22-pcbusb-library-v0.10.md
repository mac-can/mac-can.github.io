---
layout: single
title:  "PCBUSB-Library - Version 0.10 released"
tag: PCBUSB-Library
categories: Change-log Drivers macOS Peak PCBUSB
artifacts: https://www.uv-software.de/dokuwiki/doku.php?id=uvs:programs:pcbusb_library
release: Version 0.10 (Build 957 of December 22, 2020)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Support of PCAN-USB Pro FD devices, _**but only the first channel (CAN1)**_.
- Set linker options `-install_name`, `-compatibility_version`, and `-current_version`.
- Synchronized the API with Peak´s PCANBasic version 4.5.0.440
- Updated the Python example: reworked the output format.
