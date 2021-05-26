---
permalink: /wrapper/canapi-v3/
layout: single
toc: true
toc_sticky: true
title: CAN Interface API by UV Software
---
CAN&nbsp;API&nbsp;V3 is a wrapper specification by UV&nbsp;Software to have a uniform CAN Interface API for various CAN interfaces from different vendors running under multiple operating systems.
Due to the fact that the CAN APIs of the different OEMs are not compatible with each other, UV&nbsp;Software has defined a CAN Interface Wrapper specification.
Its goal is to have a multi-vendor, cross-platform CAN Interface API.

## CAN Interface Wrapper Specification

Originally, the CAN Interface API was based on an interface definition as part of a microcontroller hardware abstraction layer for an 82527-compatible on-chip CAN controller.
It was developed for use by (simple hand-coded) CANopen applications and migrated to different microcontroller types (even if the CAN peripherals on the micro had a different design).

### CAN API V1

What works on microcontrollers should also work on PC.
The interface definition was then used as a wrapper specification for different CAN devices from various vendors: e.g. for IXXAT, PEAK, Vector, Kvaser, and also for Linux-CAN (aka SocketCAN).

### CAN API V2

Dealing around with 14 virtual Basic-CAN messages boxes and a FIFO upon a virtual Full-CAN message box was a little bit over-engineered and error-prone.
Version 2 optimized the interface definition to have an easy to use API following an _init-start-read-write-stop-exit_ pattern.

### CAN API V3

Version 3 is the latest adaption of the CAN API wrapper specification.
As new features it supports CAN FD long frames and fast frames, selectable operation-modes, blocking-read, and is multi-channel capable.
Additionally it provides companion modules for bit-rate conversion and message formatting.

## CAN Interface API, Version 3

{% include figure image_path="/assets/images/canapi_macos.png" alt="CAN API V3 for macOS" caption="CAN API V3 on macOS&reg; (Copyright &copy; 2012-2021 by UV Software, Berlin)" %}

### API

In case of doubt the source code:
{% include figure image_path="/assets/images/canapi_c_api.png" alt="CAN API V3 (C API)" caption="CAN API V3 C Interface (Copyright &copy; 2004-2021 by UV Software, Berlin)" %}
See header file `can_api.h` for a description of the provided functions.

### SDKs

The macOS driver libraries come with a CAN&nbsp;API&nbsp;V3 compatible API in the SDK,
or alternatively wrapper libraries are available as separate SDKs for macOS as well as for Windows.

| CAN&nbsp;API&nbsp;V3 SDK | macOS&reg;<br/>Driver Library | macOS&reg;<br/>Wrapper Library | Windows&reg;<br/>Wrapper Library |
|:-------------- |:--------------------:|:---------------------:|:-----------------------:|
| [TouCAN USB Interfaces](/wrapper/RusokuCAN/) | :heavy_check_mark: | (:heavy_check_mark:)<sup>*</sup> | :x: |
| [CAN Leaf Interfaces](/wrapper/KvaserCAN/) | :heavy_check_mark: | (:heavy_check_mark:)<sup>*</sup> | :heavy_check_mark: |
| [PCAN-USB Interfaces](/wrapper/PCANBasic/) | :x: | :heavy_check_mark: | :heavy_check_mark: |

_<sup>*)</sup> The wrapper API is included in the SDK of the driver library._
