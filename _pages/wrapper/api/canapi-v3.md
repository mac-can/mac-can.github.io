---
permalink: /wrapper/canapi-v3/
layout: single
toc: true
toc_sticky: true
title: CAN Interface API by UV Software
---
CAN&nbsp;API&nbsp;V3 is a wrapper specification by UV&nbsp;Software to have a uniform CAN Interface API for various CAN interfaces from different vendors running under multiple operating systems.
Due to the fact that the CAN APIs of the different OEMs are not compatible with each other, UV&nbsp;Software has defined a CAN Interface Wrapper specification.
Its goal is to have multi-vendor, cross-platform CAN Interface API.

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

## Dual-License

CAN API V3 is dual-licensed under the BSD 2-Clause "Simplified" License and under the GNU General Public License v3.0 (or any later version).
You can choose between one of them if you use CAN API V3 in whole or in part.

### BSD 2-Clause "Simplified" License

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

CAN API V3 IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF CAN API V3, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

### GNU General Public License v3.0 or later

CAN API V3 is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

CAN API V3 is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with CAN API V3.  If not, see &lt;http://www.gnu.org/licenses/&gt;.
