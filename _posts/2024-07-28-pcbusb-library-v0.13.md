---
layout: single
title:  "PCBUSB-Library - Version 0.13 released"
tag: PCBUSB-Library
categories: Change-log Drivers macOS Peak PCBUSB
artifacts: https://github.com/mac-can/PCBUSB-Library/releases/tag/v0.13
release: Version 0.13 (Build 1978 of July 28, 2024)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- synchronized PCBUSB header with PCANBasic header from PEAK's version 4.9.0
- realized acceptance filtering by setting parameter:
  - `PCAN_ACCEPTANCE_FILTER_11BIT` (default = `0x00000000000007FF`)
  - `PCAN_ACCEPTANCE_FILTER_29BIT` (default = `0x000000001FFFFFFF`)
  - `PCAN_MESSAGE_FILTER` (default = `PCAN_FILTER_OPEN`)
  - `PCAN_RECEIVE_STATUS` (default = `PCAN_PARAMETER_ON`)
- realized suppression of status frames by setting parameter:
  - `PCAN_ALLOW_STATUS_FRAMES` (default = `PCAN_PARAMETER_ON`)
- realized suppression of remote frames by setting parameter:
  - `PCAN_ALLOW_RTR_FRAMES` (default = `PCAN_PARAMETER_ON`)

Artifacts:
- library as Universal macOS Binary ([macOS_Library_for_PCANUSB_v0.13.tar.gz](https://github.com/mac-can/PCBUSB-Library/releases/download/v0.13/macOS_Library_for_PCANUSB_v0.13.tar.gz))
- library for Intel x86_64 architecture ([OS_X_Library_for_PCANUSB_v0.13.tar.gz](https://github.com/mac-can/PCBUSB-Library/releases/download/v0.13/OS_X_Library_for_PCANUSB_v0.13.tar.gz))
