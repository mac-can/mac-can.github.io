---
layout: single
title:  "PCBUSB-Library - Version 0.6 released"
tag: PCBUSB-Library
categories: Change-log Drivers macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.6
release: Version 0.6 (Build 425 of February 20, 2015)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Parameter `PCAN_RECEIVE_EVENT` returns a file descriptor to realize 'blocking read' by `select()`` as on the Linux implementation of the PCAN-Basic API.
- Added two C++ examples and one Python example using the PCBUSB library
