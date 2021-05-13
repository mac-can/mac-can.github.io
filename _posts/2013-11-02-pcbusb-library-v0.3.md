---
layout: single
title:  "PCBUSB-Library - Version 0.3 released"
tag: PCBUSB-Library
categories: Change-log Drivers macOS Peak PCBUSB
artifacts: https://www.uv-software.de/dokuwiki/doku.php?id=uvs:programs:pcbusb_library
release: Version 0.3 (Build 235 of November 2, 2013)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Fixed issue \#11 'All channel initialized by the application will be closed even if they are in use'.
- `CAN_Unitialize`: closing all channel initialized by the application at once implemented.
- `CAN_Read`: receive queue overrun handling reworked.
- `CAN_*`: wrong function return codes corrected.
- `CAN_GetErrorText`: language support for _English_, _German_, _French_, _Italian_ and _Spanish_ added.
