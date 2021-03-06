# Running CAN and CAN FD on a Mac&reg;

_Running CAN and CAN FD on a Mac_ is the mission of the MacCAN project.
The MacCAN-Core repo is not aimed at building a driver or a library.
It provides the source code of an abstraction (or rather of a wrapper) of Apple´s IOUsbKit to create USB user-space drivers for CAN interfaces from various vendors under macOS.

## A Stupid Question

I´m working with the CAN bus since the late 1990th, mainly on microcontrollers
 (CANopen, SAE J1939, ISO-TP, UDS, etc.), but also on PC. See my [blog](https://www.uv-software.com/wordpress/) for the things I did.

Sometimes I tend to ask myself some stupid questions like _"Is it possible to ...?"_.
In 2010 I asked a well known search engine if it is possible to run CAN on a Mac.
I only found the request of a student, who had to do a semester work with CAN bus.
But that poor boy only owned a Mac.

## MacCAN - macOS Driver for PCAN-USB Interfaces and more

In the absence of a CAN driver for Mac, I started developing an OS X user space driver for my PEAK USB-to-CAN dongle.
Many thanks to Uwe Wilhelm, CEO of PEAK-System Technik GmbH, who had supported me with technical information and several hardware.

### PCBUSB Library for PEAK´s PCAN-USB Interfaces

The _PCBUSB_ library realizes a USB user-space driver under macOS for PCAN&reg; USB interfaces from PEAK-System Technik.
See the [MacCAN](https://www.mac-can.com) website for further information, downloads and links.

The library supports up to 8 PCAN-USB and PCAN-USB FD devices.
It offers an easy to use API that is almost compatible to PEAK´s PCANBasic DLL on Windows.
Standard CAN frames (11-bit identifier) as well as extended CAN frames (29-bit identifier) are supported.
PCAN-USB FD devices can be operated in CAN 2.0 mode and in CAN FD mode.

The library comes with an Objective-C wrapper and a demo App; see https://youtu.be/v0U_WN7s3ao/ \
Furthermore, it can be used with the Qt&reg; Serial Bus API on a Mac; see https://doc.qt.io/qt-5/qtserialbus-index.html

The PCBUSB library is closed source, please note the copyright and license agreements.

### TouCAN USB Interfaces from Rusoku

In 2020 I´ve received the request from Gediminas Simanskis, CEO of Rusoku technologijos UAB, Lithuania, if it is possible to roll out the MacCAN project to their TouCAN USB devices.
See [Rusoku](https://www.rusoku.com)´s website for the products and the services they offer.

The driver for TouCAN USB interfaces from Rusoku is the first driver implementation based on MacCAN-Core.
And it is open source;
goto https://github.com/mac-can/RusokuCAN/.

### CAN Leaf Interfaces from Kvaser

Welcome the MacCAN-KvaserCAN driver for CAN Leaf interfaces from [Kvaser](https://www.kvaser.com) as the next member of the MacCAN family.
Find its source code on GitHub;
goto https://github.com/mac-can/MacCAN-KvaserCAN/.

## CAN Interface API, Version 3

### A CAN Interface Wrapper Specification

Originally, the CAN Interface API was based on a CAN interface definition as part of a microcontroller hardware abstraction layer for an 82527-compatible on-chip CAN controller.
It was developed for use by (simple hand-coded) CANopen applications and migrated to different microcontroller types (even if the CAN peripherals on the micro had a different design).

#### CAN API V1

What works on microcontrollers should also work on PC.
So I started to use this interface definition as a wrapper specification for different CAN devices from various vendors: e.g. for IXXAT, PEAK, Vector, Kvaser, and also for Linux-CAN (aka SocketCAN).

#### CAN API V2

Dealing around with 14 virtual Basic-CAN messages boxes and a FIFO upon a virtual Full-CAN message box was a little bit over-engineered and error-prone.
So I optimized the interface definition to have an easy to use API following an _init-start-read-write-stop-exit_ pattern.

#### CAN API V3

Version 3 is the latest adaption of the CAN API wrapper specification.
As new features it supports CAN FD long frames and fast frames, selectable operation-modes, blocking-read, and is multi-channel capable.
Additionally it provides companion modules for bit-rate conversion and message formatting.

#### CAN Interface API, Version 3

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

### MacCAN API Specification

```C++
/// \name   MacCAN API
/// \brief  MacCAN API based on CAN Interface API Version 3 (CAN API V3).
/// \note   To implement a MacCAN driver derive a class from abstract class
///         CMacCAN, and override all pure virtual functions and optionally
///         the static function 'ProbeChannel'.
/// \{
class CMacCAN {
public:
    /// \brief  CAN channel states
    enum EChannelState {
        ChannelOccupied = CANBRD_OCCUPIED, ///< channel is available, but occupied
        ChannelAvailable = CANBRD_PRESENT, ///< channel is available and can be used
        ChannelNotAvailable = CANBRD_NOT_PRESENT,  ///< channel is not available
        ChannelNotTestable  = CANBRD_NOT_TESTABLE  ///< channel is not testable
    };
    /// \brief  Common error codes (CAN API V3 compatible)
    enum EErrorCodes {
        NoError = CANERR_NOERROR,  ///< no error!
        BusOFF = CANERR_BOFF,  ///< busoff status
        ErrorWarning = CANERR_EWRN,  ///< error warning status
        BusError = CANERR_BERR,  ///< bus error
        ControllerOffline = CANERR_OFFLINE,  ///< not started
        ControllerOnline = CANERR_ONLINE,  ///< already started
        MessageLost = CANERR_MSG_LST,  ///< message lost
        TransmitterBusy = CANERR_TX_BUSY,  ///< transmitter busy
        ReceiverEmpty = CANERR_RX_EMPTY,  ///< receiver empty
        ErrorFrame = CANERR_ERR_FRAME,  ///< error frame
        Timeout = CANERR_TIMEOUT,  ///< timed out
        ResourceError = CANERR_RESOURCE,  ///< resource allocation
        InvalidBaudrate = CANERR_BAUDRATE,  ///<  illegal baudrate
        IllegalParameter = CANERR_ILLPARA,  ///< illegal parameter
        NullPointer = CANERR_NULLPTR,  ///< null-pointer assignment
        NotInitialized = CANERR_NOTINIT,  ///< not initialized
        AlreadyInitialized = CANERR_YETINIT,  ///< already initialized
        NotSupported = CANERR_NOTSUPP,  ///< not supported
        FatalError = CANERR_FATAL,  ///< fatal error
        VendorSpecific = CANERR_VENDOR  ///< offset for vendor-specific error code
    };
/// \name   MacCAN Driver Interface
/// \brief  Methods to be overridden by a MacCAN driver implementation.
/// \{
public:
    /// \brief       probes if the CAN interface (hardware and driver) given by
    ///              the argument 'channel' is present, and if the requested
    ///              operation mode is supported by the CAN controller.
    //
    /// \note        When a requested operation mode is not supported by the
    ///              CAN controller, error CANERR_ILLPARA will be returned.
    //
    /// \param[in]   channel - channel number of the CAN interface
    /// \param[in]   opMode  - operation mode to be checked
    /// \param[in]   param   - pointer to channel-specific parameters
    /// \param[out]  state   - state of the CAN channel:
    ///                            < 0 - channel is not present,
    ///                            = 0 - channel is present,
    ///                            > 0 - channel is present, but in use
    //
    /// \returns     0 if successful, or a negative value on error.
    //
    static MacCAN_Return_t ProbeChannel(int32_t channel, MacCAN_OpMode_t opMode, const void *param, EChannelState &state);
    static MacCAN_Return_t ProbeChannel(int32_t channel, MacCAN_OpMode_t opMode, EChannelState &state);

    /// \brief       initializes the CAN interface (hardware and driver) given by
    ///              the argument 'channel'.
    ///              The operation state of the CAN controller is set to 'stopped';
    ///              no communication is possible in this state.
    //
    /// \param[in]   channel - channel number of the CAN interface
    /// \param[in]   opMode  - operation mode of the CAN controller
    /// \param[in]   param   - pointer to channel-specific parameters
    //
    /// \returns     handle of the CAN interface if successful,
    ///              or a negative value on error.
    //
    virtual MacCAN_Return_t InitializeChannel(int32_t channel, MacCAN_OpMode_t opMode, const void *param = NULL) = 0;

    /// \brief       stops any operation of the CAN interface and sets the operation
    ///              state of the CAN controller to 'stopped'.
    //
    /// \returns     0 if successful, or a negative value on error.
    ///
    virtual MacCAN_Return_t TeardownChannel() = 0;

    /// \brief       signals waiting event objects of the CAN interface. This can
    ///              be used to terminate blocking operations in progress
    ///              (e.g. by means of a Ctrl-C handler or similar).
    //
    /// \remarks     Some drivers are using waitable objects to realize blocking
    ///              operations by a call to WaitForSingleObject (Windows) or
    ///              pthread_cond_wait (POSIX), but these waitable objects are
    ///              no cancellation points. This means that they cannot be
    ///              terminated by Ctrl-C (SIGINT).
    //
    /// \note        Even though this is not the case with Darwin, we support
    ///              this feature for compatibility reasons..
    //
    /// \returns     0 if successful, or a negative value on error.
    ///
    virtual MacCAN_Return_t SignalChannel() = 0;

    /// \brief       initializes the operation mode and the bit-rate settings of the
    ///              CAN interface and sets the operation state of the CAN controller
    ///              to 'running'.
    //
    /// \note        All statistical counters (tx/rx/err) will be reset by this.
    //
    /// \param[in]   bitrate - bit-rate as btr register or baud rate index
    //
    /// \returns     0 if successful, or a negative value on error.
    //
    virtual MacCAN_Return_t StartController(MacCAN_Bitrate_t bitrate) = 0;

    /// \brief       stops any operation of the CAN interface and sets the operation
    ///              state of the CAN controller to 'stopped'; no communication is
    ///              possible in this state.
    //
    /// \returns     0 if successful, or a negative value on error.
    //
    virtual MacCAN_Return_t ResetController() = 0;

    /// \brief       transmits one message over the CAN bus. The CAN controller must
    ///              be in operation state 'running'.
    //
    /// \param[in]   message - the message to send
    /// \param[in]   timeout - time to wait for the transmission of the message:
    ///                             0 means the function returns immediately,
    ///                             65535 means blocking read, and any other
    ///                             value means the time to wait im milliseconds
    //
    /// \returns     0 if successful, or a negative value on error.
    //
    virtual MacCAN_Return_t WriteMessage(MacCAN_Message_t message, uint16_t timeout = 0U) = 0;

    /// \brief       read one message from the message queue of the CAN interface, if
    ///              any message was received. The CAN controller must be in operation
    ///              state 'running'.
    //
    /// \param[out]  message - the message read from the message queue, if any
    /// \param[in]   timeout - time to wait for the reception of a message:
    ///                             0 means the function returns immediately,
    ///                             65535 means blocking read, and any other
    ///                             value means the time to wait im milliseconds
    //
    /// \returns     0 if successful, or a negative value on error.
    //
    virtual MacCAN_Return_t ReadMessage(MacCAN_Message_t &message, uint16_t timeout = CANREAD_INFINITE) = 0;

    /// \brief       retrieves the status register of the CAN interface.
    //
    /// \param[out]  status  - 8-bit status register.
    //
    /// \returns     0 if successful, or a negative value on error.
    //
    virtual MacCAN_Return_t GetStatus(MacCAN_Status_t &status) = 0;

    /// \brief       retrieves the bus-load (in percent) of the CAN interface.
    //
    /// \param[out]  load    - bus-load in [%]
    //
    /// \returns     0 if successful, or a negative value on error.
    //
    virtual MacCAN_Return_t GetBusLoad(uint8_t &load) = 0;

    /// \brief       retrieves the bit-rate setting of the CAN interface. The
    ///              CAN controller must be in operation state 'running'.
    //
    /// \param[out]  bitrate - bit-rate setting
    //
    /// \returns     0 if successful, or a negative value on error.
    //
    virtual MacCAN_Return_t GetBitrate(MacCAN_Bitrate_t &bitrate) = 0;

    /// \brief       retrieves the transmission rate of the CAN interface. The
    ///              CAN controller must be in operation state 'running'.
    //
    /// \param[out]  speed   - transmission rate
    //
    /// \returns     0 if successful, or a negative value on error.
    //
    virtual MacCAN_Return_t GetBusSpeed(MacCAN_BusSpeed_t &speed) = 0;

    /// \brief       retrieves a property value of the CAN interface.
    //
    /// \param[in]   param    - property id to be read
    /// \param[out]  value    - pointer to a buffer for the value to be read
    /// \param[in]   nbytes   - size of the given buffer in bytes
    //
    /// \returns     0 if successful, or a negative value on error.
    //
    virtual MacCAN_Return_t GetProperty(uint16_t param, void *value, uint32_t nbytes) = 0;

    /// \brief       modifies a property value of the CAN interface.
    //
    /// \param[in]   param    - property id to be written
    /// \param[in]   value    - pointer to a buffer with the value to be written
    /// \param[in]   nbytes   - size of the given buffer in bytes
    //
    /// \returns     0 if successful, or a negative value on error.
    //
    virtual MacCAN_Return_t SetProperty(uint16_t param, const void *value, uint32_t nbytes) = 0;

    /// \brief       retrieves the hardware version of the CAN controller
    ///              board as a zero-terminated string.
    //
    /// \returns     pointer to a zero-terminated string, or NULL on error.
    //
    virtual char *GetHardwareVersion() = 0;

    /// \brief       retrieves the firmware version of the CAN controller
    ///              board as a zero-terminated string.
    //
    /// \returns     pointer to a zero-terminated string, or NULL on error.
    //
    virtual char *GetFirmwareVersion() = 0;
/// \}

/// \name   MacCAN Bit-rate converstion
/// \brief  Methods for bit-rate conversion.
/// \note   To be overridden when required.
/// \{
public:
    static MacCAN_Return_t MapIndex2Bitrate(int32_t index, MacCAN_Bitrate_t &bitrate);
    static MacCAN_Return_t MapString2Bitrate(const char *string, MacCAN_Bitrate_t &bitrate);
    static MacCAN_Return_t MapBitrate2String(MacCAN_Bitrate_t bitrate, char *string, size_t length);
    static MacCAN_Return_t MapBitrate2Speed(MacCAN_Bitrate_t bitrate, MacCAN_BusSpeed_t &speed);
/// \}

/// \name   CAN FD Data Length Code
/// \brief  Methods for DLC conversion.
/// \{
public:
    static uint8_t Dlc2Len(uint8_t dlc);
    static uint8_t Len2Dlc(uint8_t len);
/// \}
};
/// \}
```

### Contact

E-Mail: mailto://info@mac.can.com \
Internet: https://www.mac-can.com

##### *Happy CANgineering!*
