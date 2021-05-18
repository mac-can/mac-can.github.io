---
permalink: /wrapper/canapi-v3/
layout: single
toc: true
toc_sticky: true
title: CAN Interface API by UV Software
---
CAN&nbsp;API&nbsp;V3 is a wrapper specification by UV&nbsp;Software to have a uniform CAN Interface API for various CAN interfaces from different vendors running under multiple operating systems.
Due to the fact that the CAN APIs of the different OEMs are not compatible with each other, I have defined a CAN Interface Wrapper specification.
Its goal is to have multi-vendor, cross-platform CAN Interface API.

## CAN Interface Wrapper Specification

Originally, the CAN Interface API was based on an interface definition as part of a microcontroller hardware abstraction layer for an 82527-compatible on-chip CAN controller.
It was developed for use by (simple hand-coded) CANopen applications and migrated to different microcontroller types (even if the CAN peripherals on the micro had a different design).

### CAN API V1

What works on microcontrollers should also work on PC.
So I started to use this interface definition as a wrapper specification for different CAN devices from various vendors: e.g. for IXXAT, PEAK, Vector, Kvaser, and also for Linux-CAN (aka SocketCAN).

### CAN API V2

Dealing around with 14 virtual Basic-CAN messages boxes and a FIFO upon a virtual Full-CAN message box was a little bit over-engineered and error-prone.
So I optimized the interface definition to have an easy to use API following an _init-start-read-write-stop-exit_ pattern.

### CAN API V3

Version 3 is the latest adaption of the CAN API wrapper specification.
As new features it supports CAN FD long frames and fast frames, selectable operation-modes, blocking-read, and is multi-channel capable.
Additionally it provides companion modules for bit-rate conversion and message formatting.

## CAN Interface API, Version 3

### API

In case of doubt the source code:

```C
#if (OPTION_CANAPI_LIBRARY != 0)
extern int can_test(int32_t library, int32_t channel, uint8_t mode, const void *param, int *result);
extern int can_init(int32_t library, int32_t channel, uint8_t mode, const void *param);
#else
extern int can_test(int32_t channel, uint8_t mode, const void *param, int *result);
extern int can_init(int32_t channel, uint8_t mode, const void *param);
#endif
extern int can_exit(int handle);
extern int can_kill(int handle);

extern int can_start(int handle, const can_bitrate_t *bitrate);
extern int can_reset(int handle);

extern int can_write(int handle, const can_message_t *message, uint16_t timeout);
extern int can_read(int handle, can_message_t *message, uint16_t timeout);

extern int can_status(int handle, uint8_t *status);
extern int can_busload(int handle, uint8_t *load, uint8_t *status);

extern int can_bitrate(int handle, can_bitrate_t *bitrate, can_speed_t *speed);
extern int can_property(int handle, uint16_t param, void *value, uint32_t nbyte);

extern char *can_hardware(int handle);
extern char *can_software(int handle);

#if (OPTION_CANAPI_LIBRARY != 0)
extern char *can_library(int handle);
#endif
extern char* can_version(void);
```
See header file `can_api.h` for a description of the provided functions.

### SDKs

The macOS driver libraries come with a CAN&nbsp;API&nbsp;V3 compatible API in the SDK,
or alternatively wrapper libraries are available as separate SDKs for macOS as well as for Windows.

| CAN&nbsp;API&nbsp;V3 SDK | macOS&reg;<br/>Driver Library | macOS&reg;<br/>Wrapper Library | Windows&reg;<br/>Wrapper Library |
|:-------------- |:--------------------:|:---------------------:|:-----------------------:|
| [TouCAN USB Interfaces](/drivers/RusokuCAN/) | :heavy_check_mark: | (:heavy_check_mark:)<sup>*</sup> | :x: |
| [CAN Leaf Interfaces](/drivers/KvaserCAN/) | :heavy_check_mark: | (:heavy_check_mark:)<sup>*</sup> | :heavy_check_mark: |
| [PCAN-USB Interfaces](/drivers/libPCBUSB.html) | :x: | :heavy_check_mark: | :heavy_check_mark: |

_<sup>*)</sup> The wrapper API is included in the SDK of the driver library._

## License

CAN API V3 is free software: you can redistribute it and/or modify
it under the terms of the GNU Lesser General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

CAN API V3 is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License
along with CAN API V3.  If not, see &lt;http://www.gnu.org/licenses/&gt;.
