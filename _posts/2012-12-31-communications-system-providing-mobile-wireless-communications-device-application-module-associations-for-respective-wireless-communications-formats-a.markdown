---

title: Communications system providing mobile wireless communications device application module associations for respective wireless communications formats and related methods
abstract: A communications system may include a plurality of electronic devices having respective different device types and each configured to wirelessly communicate via a plurality of different wireless communications formats. The system may also include a mobile wireless communications device including a plurality of application modules associated with respective electronic device types and configured to communicate via a first one of the wireless communications formats. The mobile wireless communications device may further include a control module configured to establish an initial wireless communications link with a given electronic device using a second one of the wireless communications formats, determine a respective device type for the given electronic device based upon the established initial wireless communications link, and cause a respective application module to establish a subsequent wireless communications link with the given electronic device using the second wireless communications format based upon the determined respective device type.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08730845&OS=08730845&RS=08730845
owner: BlackBerry Limited
number: 08730845
owner_city: Waterloo, Ontario
owner_country: CA
publication_date: 20121231
---
This application is based upon prior filed provisional application Ser. No. 61 384 573 filed Sep. 20 2010 the disclosure of which is incorporated herein by reference in its entirety.

This application relates to the field of wireless communications and more particularly to wireless communications devices and related methods.

Mobile communication systems continue to grow in popularity and have become an integral part of both personal and business communications. Various mobile devices now incorporate Personal Digital Assistant PDA features such as calendars address books task lists calculators memo and writing programs media players games etc. These multi function devices usually allow electronic mail email messages to be sent and received wirelessly as well as access the Internet via a cellular network and or a wireless local area network WLAN for example.

Some mobile devices incorporate contactless card technology and or near field communication NFC chips. NFC technology is used for contactless short range communications based on radio frequency identification RFID standards using magnetic field induction to enable communication between electronic devices including mobile wireless communications devices. These short range communications include payment and ticketing electronic keys identification device set up service and similar information sharing. This short range high frequency wireless communications technology exchanges data between devices over a short distance such as only a few centimeters.

The present description is made with reference to the accompanying drawings in which example embodiments are shown. However many different embodiments may be used and thus the description should not be construed as limited to the embodiments set forth herein. Rather these embodiments are provided so that this disclosure will be thorough and complete.

Generally speaking a communications system is provided herein which may include a plurality of electronic devices having respective different device types and each electronic device may be configured to wirelessly communicate via a plurality of different wireless communications formats. The communications system may also include a mobile wireless communications device comprising a plurality of application modules associated with respective electronic device types and configured to communicate via a first one of the wireless communications formats. The mobile wireless communications device may further include a control module configured to establish an initial wireless communications link with a given electronic device using a second one of the wireless communications formats determine a respective device type for the given electronic device based upon the established initial wireless communications link and cause a respective application module to establish a subsequent wireless communications link with the given electronic device using the second wireless communications format based upon the determined respective device type. Accordingly enhanced efficiencies of wireless communication handovers between different communications formats may be achieved for example.

By way of example the second wireless communications format may comprise a near field communication NFC format while the first wireless communications format may comprise a Bluetooth format a wireless local area network WLAN format a cellular communications format etc. Moreover the application modules may be further configured to register respective electronic device types with the control module. Also the plurality of application modules may comprise at least one of an image application module a video application module an audio module an Internet browser module etc.

A mobile wireless communication device such as the one described briefly above and a related communications method are also provided. The method may include establishing an initial wireless communications link between a mobile wireless communications device and a given electronic device where the mobile wireless communication device comprises a plurality of application modules associated with respective electronic device types and configured to communicate via a first one of the wireless communications formats. The initial wireless communications link may be established using a second one of the wireless communications formats. The method may further include determining a respective device type for the given electronic device based upon the established initial wireless communications link and establishing a subsequent wireless communications link between a respective application module and the given electronic device using the second wireless communications format based upon the determined respective device type.

A related computer readable medium for a mobile wireless communication device is also provided. The computer readable medium may have computer executable instruction modules comprising a plurality of application modules associated with respective electronic device types and configured to communicate via a first one of the wireless communications formats and a control module. The control module may be configured to establish an initial wireless communications link with a given electronic device using a second one of the wireless communications formats determine a respective device type for the given electronic device based upon the established initial wireless communications link and cause a respective application module to establish a subsequent wireless communications link with the given electronic device using the second wireless communications format based upon the determined respective device type.

Referring initially to a communications system and related method aspects are first described. The system illustratively includes a plurality of electronic devices having respective different device types and each electronic device is configured to wirelessly communicate via a plurality of different wireless communications formats. By way of example the electronic devices may be of different types such as media e.g. video audio etc. players displays gaming devices telephones point of sale POS terminals etc. Moreover the electronic devices may be implemented as portable or mobile devices as well as stationary devices in different embodiments.

Also by way of example the different wireless communications formats standards or protocols may include a near field communication NFC format a Bluetooth format a wireless local area network WLAN format a cellular communications format etc. By way of background NFC is a short range wireless communications technology in which NFC enabled devices are swiped bumped or otherwise moved in close proximity to communicate. In one non limiting example implementation NFC may operate at 13.56 MHz and with an effective range of about 10 cm but other suitable versions of near field communication which may have different operating frequencies effective ranges etc. for example may also be used.

Beginning at Block the communications system also illustratively includes a mobile wireless communications device which comprises a plurality of application modules that are associated with respective electronic device types here types A B or C at Block . Moreover the application modules are configured to communicate via a first one of the wireless communications formats. For the present example Bluetooth will be used as the first wireless communications format but other formats such as those described above may also be used. Also by way of example the application modules may comprise media application modules such as for images videos audio or a combination thereof. Other application modules may include Internet browser modules document processing modules social networking modules electronic commerce modules etc. The application modules may also be considered as mobile software applications or apps from the device manufacturer or third party developers which take the form of software modules comprising computer executable instructions stored on a computer readable medium. Example types of mobile wireless communications devices may include portable or personal media players e.g. MP3 players video players etc. remote controls e.g. television or stereo remotes etc. portable gaming devices portable or mobile telephones smartphones tablet computers etc.

By way of example the application modules may be associated with respective electronic device types by registration. That is the application modules may be further configured to register respective electronic device types with a control module of the mobile wireless communications device such as upon installation for example as will be discussed further in the accompanying Appendix A.

The control module may be configured to establish an initial wireless communications link with a given electronic device using a second one of the wireless communications formats Block which for the present example is NFC although other formats may also be used in different embodiments. Thus for example upon swiping or bumping the mobile wireless communications device with the electronic device these devices establish an NFC communications link therebetween. Upon establishing of this link the control module determines a respective device type for the given electronic device based upon the established initial NFC wireless communications link at Block and causes a respective application module to establish a subsequent wireless communications link with the given electronic device using the second wireless communications format e.g. Bluetooth in the present example based upon the determined respective device type.

In one example use case the given electronic device may comprise a POS terminal such as at a retail store and the application module may comprise an electronic payment application module e.g. a PayPal app Visa app American Express app etc. . Upon swiping or bumping of the mobile wireless communications device with the POS terminal the control module may alert the electronic payment application module of the POS terminal so that the electronic payment application module may initiate or otherwise establish a Bluetooth or other connection with the POS terminal to complete an electronic payment operation.

The various operations or functions of the control module described herein may be implemented as part of an example application programming interface API . An example API for a BlackBerry mobile device architecture from Research In Motion Limited RIM is provided below although it will be appreciated that the various elements and operations described herein may be used with other mobile device architectures as well.

Near Field Communication NFC is used for contactless communication between devices and tags cards. It has a range of roughly 10 cm operates at 13.56 Mhz and supports transfer speeds of 106 Kbps 212 Kbps and 424 Kbps.

Support for NFC opens up a range of new capabilities for the BlackBerry. Some of the use cases we will be able to support include 

A Bluetooth connection handover feature may be implemented in java The document covers MRD 1 6.7.1 NFC AP001 NFC API requirement.

The Java layer will be communicating with native layer over the bridge. It will call into a NFC driver that runs inside user mode process.

IT Policy may be updated to give BES administrators a way to enable disable the following NFC features 

The API covers tag emulation tag reading tag writing and peer to peer connections. All of these could potentially be requested by multiple applications concurrently.

Both Secure Element based card tag emulation and baseband card tag emulation are supported but each may have a different API. One tag or card may be emulated at a time. Also the foreground application may be allowed to perform card emulation. Once that application moves to the background it may lose the ability to emulate a card or tag.

The baseband card tag emulation API will provide simple stopping and starting of emulation as well as a method to check if a target is currently being emulated. There will be an internal API method to stop tag emulation.

The Secure Element based API will allow applications to determine what secure elements are present embedded and or SIM activate or deactivate each one and set the technology type used. JSR 177 is used for APDU based interaction with the Secure Elements.

The API will provide 2 levels of event registration one for Tag detection events and one for NDEF record detection events. Applications can decide which approach makes sense for them.

Multiple applications may be registered to detect tags. Tag detection events may be sent to all of the currently running listeners registered for that type of NFC event.

The NDEF Record detection registration methods have an autostart boolean parameter that indicates whether the registering application should be started if it is not running at the time a matching event occurs. If the foreground application is registered to handle any NDEF record on the tag we assume that no other application needs to be started. If there is only one matching autostart application that one is started. One application may be started per tag read. If there are multiple matching applications we may check to see if the user previously configured a default application for any of the NDEF record types on the tag and start the default application. If there is not exactly one default application the user may select which one they want to start. They may indicate that this is the application they want to start in future for the same NDEF record type.

For the case of writing to tags we may allow one application to connect to one tag at a time. If another Connection is attempted to the tag in the same detection cycle the API will throw an NFC exception.

More than one peer to peer connection may be active at a time on the device. Peer to Peer connections will need to have a unique connection type service name pair note that the same service name may be used for a client and a server connection on a device . We will restrict access to any LLCP service name that begins with urn nfc sn RIM to internal applications signed with 3. key.

NFC based connection handover 2 6 is supported. Initially we will only support Bluetooth but the API is designed to handle other transports in the future if required.

To support the requested user experience flows there will be a Connection Handover process that is almost always running. It may be disabled turned off from time to time due to conflicts with a card emulation request . It will use the NFC APIs to do the following 

The Connection Handover process may support Bluetooth Connection Handover. The Connection Handover happens automatically when two Bluetooth devices are tapped. The Connection Handover process pops up a dialog box to the user asking if they want to proceed with the pairing.

3rd party applications may register to be notified about Bluetooth Connection Handover tap events. Each application may determine their own context and establish the Bluetooth connection if necessary.

We will provide a mechanism to allow applications to register a persistent interest in specific NDEF RTDs and then exit. When the NDEF data dispatcher sees a tag that matches the registration it will launch the application and send the NDEFMessage to it for processing.

Because of the very short duration of an NFC tap and the length of time it takes for an application to load this feature will not be available for target detection listeners.

JSR 177 support may be provided for the SIM card for SATSA APDU SATSA RMI and access control files. Support may be added for JSR 177 for the embedded secure element for SATSA APDU.

The NFC API will integrate with the existing Device Capability API. A new DeviceCapability.TYPE NFC constant may be defined and the NFC subsystem may register its availability with the Device Capability API on startup. Additionally the NFC subsystem will notify any DeviceCapability API NFC listeners when NFC is enabled or disabled.

Due to the nature of NFC and underlying hardware limitations all combinations of NFC operations may not be possible by multiple applications concurrently.

The NFC Manager may resolve the conflicts. Requests may fail with an NFCException if they cannot be satisfied. Alternatively a request may succeed and another application may lose access to some part of the NFC API. In this case that application will receive a notification via an NFCStatusListener.

The default rule for resolving conflicts is that the first request for a resource should succeed and that any conflicting requests should fail. The first application will retain the resource until it gives it up.

In order to help manage the conflicts we may provide an internal API that allows RIM application to configure certain NFC services as Foreground Only meaning that applications that are in the foreground can use them and when they move to the background they will lose access to them.

Tag Card emulation and Secure Element based operations may be available to the foreground application. NFC peer to peer operations may be available to all applications both foreground and background however they may not be able to be performed while a foreground application is using Tag Card emulation or Secure Element based emulation.

An internal API may be provided for enabling or disabling all or part of the NFC subsystem. The following pieces may be enabled disabled separately or together 

The DeviceCapabilityManager API may be used to query if NFC is available on a device. If an application tries to call this API when NFC is not available an NFC exception may be thrown.

For security reasons and also to save on battery usage we may not want to initiate or receive NFC taps while the device is holstered password locked screen locked or when the backlight is off. The NFCManager may register listeners to track these events and enable disable the operation of the NFC feature accordingly. If an NFC API is accessed when it is disabled an NFCException may be thrown.

The NFCManager is the main entry point to the NFC API. It is also responsible for determining and resolving any conflicts between requested NFC operations.

Classes implementing this interface will be notified when a matching NDEF message has been retrieved from a tag. NFCManager.addNDEFMessageListener NDEFMessageListener listener int typeNameFormat String recordType boolean autostart allows applications to be notified when specific NDEF record type is detected. The autostart parameter indicates whether the registered application should be started if it is not running when the NDEF message is detected.

This interface defines the call back that an application will receive when a matching target is detected by the NFC system. An NFCDetectionListener is registered with NFCManager s addDetectionListener NFCDetectionListener listener int type method.

This interface defines the call back that an application will receive when the availability of NFC services for the application is detected. An NFCStatusListener is registered with NFCManagex s addStatusListener NFCStatusListener listener method.

This interface defines the call back that an application will receive when the device is introduced to and removed from an NFC RF field. A FieldListener is registered with NFCManager s addFieldListener FieldListener listener method. See 

Target represents a card tag that was detected by NFC. It also identifies a type of contactless protocol that is used to connect to the card. The API groups contactless protocols in four categories from the lowest layer 

getUri int connectionType returns URI that needs to be passed to Connector.open to open a connection to the card tag.

getProperty returns the value of a requested target property. These properties have not yet been defined but will likely vary by target type. At a minimum each target should have a Name property.

If there is more than one target type specified in a call to NFCManager s addDetectionListener method that NFCDetectionListener s detectedTarget method will still only be called once for a target that matches more than one type. See .

Supports reading and writing of tags by sending ISO14443 3 commands and the reading responses. This is the lowest level of tag access and requires knowledge of the command set for the tag. See .

NDEFMessage is a container for an array of NDEFRecords. Once all the records are in place it provides a way to get the byte representation for writing to a tag or NFC P2P connection.

Contains the payload data in an NDEFMessage. Provides methods for building up the bytes in the expected format. See .

This class represents a tag or card that is being emulated. It provides methods for starting and stopping emulation as well as checking its type A or B .

This is a subclass of VirtualTarget and class represents an ISO 14443 Type A tag or card that is being emulated.

This is a subclass of VirtualTarget and class represents an ISO 14443 Type B tag or card that is being emulated.

This class represents a tag or card that is being emulated. It provides methods for starting and stopping emulation as well as checking its type A or B .

This class is used for emulating an NFC Forum NDEF tag. It provides methods for setting its NDEF contents and registering a listener to receive callbacks.

This class covers all non NDEF emulation cases. It can be used to emulate cards or tags. The associated VirtualISO14443TargetListener instance is responsible for generating suitable responses for incoming command bytes. Note that this class is not intended to be used for secure card emulation see SecureElementNanager instead .

This interface defines the call backs that an application will receive when one of the following virtual target events occur target selected target read target updated or reader left.

This interface defines the callbacks that an application will receive when a virtual tag event occurs. It extends the VirtualTargetListener interface and adds a method for responding to external reader commands. See 

NFC Exception that is thrown when an NFC service cannot be provided because a requested resource is in use. See .

This class is a point of entry for initiating or configuring connection handover behaviour. API allows registration of connection handover listeners for 3rd party applications so that they can be notified when a Bluetooth connection is advertised or negotiated over NFC and also if a connection handover fails for some reason. Support for transports other than Bluetooth may be added in the future.

This is the interface that 3rd party applications use to receive notifications about connection handover events triggered by NFC. It is up to each application to decide what action the user intended by the tap.

Class representing a connection handover failure events. Contains data that allows the listener to determine why the failure occurred.

This class extends ConnectionHandoverCompletedEvent and adds Bluetooth specific information so that the 3rd party application can establish the Bluetooth connection if it wishes. See .

This class represents a single secure element. It provides public methods for getting type connection information mode as well as updating the mode and associating a transaction listener with the secure element. Valid modes for the secure element are 

This callback interface is invoked when an active secure element is accessed. This allows application to monitor activity and perform some application specific logic such as query SE for new state.

The tag reader API allows applications to detect and read write NDEF tags as well as send raw tag commands to non NDEF tags cards.

One way to discover and read a tag is to register one or more listeners for tag detection. When the tag is detected in the RF field the listeners are invoked. The listener implementations will be responsible for connecting to the tag and reading the data.

Another approach is to use NDEFMessageListener. When an NDEF tag with a specific NDEF record is detected entire NDEF message is passed to a callback. This approach does not require connecting to a tag but it also does not support writing to a tag. An additional advantage of this approach is that it can be used to autostart an application to consume the NDEF message. This feature is not available for Connection oriented tag interactions because of the delay introduced by launching an application.

Applications will be able to register their persistent interest in an NDEF record via custom properties in a JAD file. Entries will follow the format NDEFMessageListener. TNF . Type Class name eg. NDEFMessageListener.2.text plain com.my.ndef.listener.MyNDEFListener

These properties will be read when the application is installed and the registration will be initialized at that time. The persistent listener registrations will be removed when the application is uninstalled.

The following security checks may be done internally to verify that applications are allowed to access the NFC tag reader writer APIs 

Fledge device simulator may need to be extended to support emulation of NFC tag reading functionality.

The tag card emulation API will allow devices to act as if they were RFID tags and interact with NFC readers accordingly. Two flavors of emulation are provided Virtual NDEF Tag and Virtual ISO14443 Target. For secure card emulation the API will support detection and setting the mode of available secure elements letting the emulation be done by an application running on the secure element. Note that secure card emulation and regular tag card emulation cannot happen at the same time.

NDEF tag emulation is done by initializing a VirtualNDEFTag with an NDEFMessage. A listener can be attached to the virtual tag to monitor tag events if desired. Emulation is started by invoking startEmulation on the tag instance. Card emulation is done by constructing a VirtualISO14443TypeATarget or VirtualISO14443TypeBTarget with a VirtualISO14443Target Listener and invoking startEmulation on the target instance. The listener will be notified about any incoming commands and is responsible for generating the responses.

For payment and other high value use cases card emulation via a secure element is recommended expected. This API provides a way to check what secure elements are present on a device and enable one of them. JSR 177 may be used for the actual APDU interaction with the secure element.

One target can be emulated by the device at a time and the application attempting the emulation operation must be running in the foreground. Note that this applies to secure element based card emulation too. 3rd party applications attempting to start a second emulation may get an exception. RIM internal applications may stop another application s emulation activities but some UI may be added behind the API to let the device user control this in the future.

NOTE There is additional Technology Type Change listener API work that is pending. This feature will allow applications to determine if an SE s technology type is changed by some other entity. We anticipate that there will be a additional class an some additional methods added to support this.

The following security checks may be done internally to verify that applications are allowed to access the NFC tag card emulation APIs 

The NFC API may support Peer to Peer communication through LLCP 5 . Each end of the communication link can send application defined bytes to the other.

The client and the server sides may each attempt to open a connection using the NFC API with Connector.open method calls. The connection parameters appended to the URI may specify which side of the connection a device wants to be client or server as well LLCP 5 specific parameters. When the connection is established the client and server may both get their Connection objects and they can send receive data

Note Open NFC API from Inside Contactless currently does not support setting of miu rw and timeout LLCP parameters. It also does not support LLCP s connectionless datagram transport service.

When mode is not specified in the URI mode client is used by default. In addition connection parameters should include a unique sn service name. Multiple LLCP connections can be opened as long as each connection mode service name pair is unique on the device.

The following security checks may be done internally to verify that applications are allowed to access the NFC Peer to Peer APIs 

The API will supports establishing Bluetooth connections using NFC to determine connection parameters. Protocol is described in 2 6 .

Connection Handover can be accomplished through an LLCP connection or by detecting an NFC tag that contains a connection handover NDEF record.

A single RIM application will listen for connection handover NDEF tags records as well as for LLCP peers using a service name of urn nfc sn handover . It will use a connection type of any so that it may end up being the requestor or selector for the connection handover NDEF exchange.

Applications may register their interest in connection handovers for specific types of transport along with a listener to handle them. The applications will receive connection metadata as part of the listener callback they receive when a Bluetooth peer is tapped on. It is up to them to decide the context of the tap and establish the connection if appropriate.

A 3rd party application may check whether the connection handover is the result of a static or negotiated exchange by inspecting the connection event instance.

The following security checks may be provided to verify that applications are allowed to access the NFC APIs underneath the Connection Handover API. Note that access to the Connection Handover API may not be restricted directly because the lower level APIs could allow a malicious app to implement its own Connection Handover thus circumventing the checks 

The API provides ways to query for NFC availability enable or disable different NFC features and listen for changes in feature availability for an application.

The NFC API integrates with the Device Capability API so that 3rd party applications can determine in a standard way if NFC is supported. Applications may also listen for high level NFC availability change notifications.

Applications may use a lower level API to track NFC Status Changes. This is particularly useful for situations where an application loses access to an NFC feature due to contention with another application. The difference between this API and the device capability API is that the first one tracks device status and the second one customizes the status for each application to handle conflicts. E.g. Secure Element APIs may be available to the foreground application but not available fox other applications.

There are also internal APIs for enabling and disabling different parts of the API as well as methods to help configure which NFC service should require the application to be running in the foreground.

Example components of a mobile wireless communications device that may be used in accordance with the above described embodiments are further described below with reference to . The device illustratively includes a housing a keyboard or keypad and an output device . The output device shown is a display which may comprise a full graphic LCD. Other types of output devices may alternatively be utilized. A processing device is contained within the housing and is coupled between the keypad and the display . The processing device controls the operation of the display as well as the overall operation of the mobile device in response to actuation of keys on the keypad .

The housing may be elongated vertically or may take on other sizes and shapes including clamshell housing structures . The keypad may include a mode selection key or other hardware or software for switching between text entry and telephony entry.

In addition to the processing device other parts of the mobile device are shown schematically in . These include a communications subsystem a short range communications subsystem the keypad and the display along with other input output devices and as well as memory devices and various other device subsystems . The mobile device may comprise a two way RF communications device having data and optionally voice communications capabilities. In addition the mobile device may have the capability to communicate with other computer systems via the Internet.

Operating system software executed by the processing device is stored in a persistent store such as the flash memory but may be stored in other types of memory devices such as a read only memory ROM or similar storage element. In addition system software specific device applications or parts thereof may be temporarily loaded into a volatile store such as the random access memory RAM . Communications signals received by the mobile device may also be stored in the RAM .

The processing device in addition to its operating system functions enables execution of software applications A N on the device . A predetermined set of applications that control basic device operations such as data and voice communications A and B may be installed on the device during manufacture. In addition a personal information manager PIM application may be installed during manufacture. The PIM may be capable of organizing and managing data items such as e mail calendar events voice mails appointments and task items. The PIM application may also be capable of sending and receiving data items via a wireless network . The PIM data items may be seamlessly integrated synchronized and updated via the wireless network with corresponding data items stored or associated with a host computer system.

Communication functions including data and voice communications are performed through the communications subsystem and possibly through the short range communications subsystem. The communications subsystem includes a receiver a transmitter and one or more antennas and . In addition the communications subsystem also includes a processing module such as a digital signal processor DSP and local oscillators LOs . The specific design and implementation of the communications subsystem is dependent upon the communications network in which the mobile device is intended to operate. For example a mobile device may include a communications subsystem designed to operate with the Mobitex Data TAC or General Packet Radio Service GPRS mobile data communications networks and also designed to operate with any of a variety of voice communications networks such as AMPS TDMA CDMA WCDMA PCS GSM EDGE etc. Other types of data and voice networks both separate and integrated may also be utilized with the mobile device . The mobile device may also be compliant with other communications standards such as 3GSM 3GPP UMTS 4G etc.

Network access requirements vary depending upon the type of communication system. For example in the Mobitex and DataTAC networks mobile devices are registered on the network using a unique personal identification number or PIN associated with each device. In GPRS networks however network access is associated with a subscriber or user of a device. A GPRS device therefore typically involves use of a subscriber identity module commonly referred to as a SIM card in order to operate on a GPRS network.

When required network registration or activation procedures have been completed the mobile device may send and receive communications signals over the communication network . Signals received from the communications network by the antenna are routed to the receiver which provides for signal amplification frequency down conversion filtering channel selection etc. and may also provide analog to digital conversion. Analog to digital conversion of the received signal allows the DSP to perform more complex communications functions such as demodulation and decoding. In a similar manner signals to be transmitted to the network are processed e.g. modulated and encoded by the DSP and are then provided to the transmitter for digital to analog conversion frequency up conversion filtering amplification and transmission to the communication network or networks via the antenna .

In addition to processing communications signals the DSP provides for control of the receiver and the transmitter . For example gains applied to communications signals in the receiver and transmitter may be adaptively controlled through automatic gain control algorithms implemented in the DSP .

In a data communications mode a received signal such as a text message or web page download is processed by the communications subsystem and is input to the processing device . The received signal is then further processed by the processing device for an output to the display or alternatively to some other auxiliary I O device . A device may also be used to compose data items such as e mail messages using the keypad and or some other auxiliary I O device such as a touchpad a rocker switch a thumb wheel or some other type of input device. The composed data items may then be transmitted over the communications network via the communications subsystem .

In a voice communications mode overall operation of the device is substantially similar to the data communications mode except that received signals are output to a speaker and signals for transmission are generated by a microphone . Alternative voice or audio I O subsystems such as a voice message recording subsystem may also be implemented on the device . In addition the display may also be utilized in voice communications mode for example to display the identity of a calling party the duration of a voice call or other voice call related information.

The short range communications subsystem enables communication between the mobile device and other proximate systems or devices which need not necessarily be similar devices. For example the short range communications subsystem may include an infrared device and associated circuits and components a Bluetooth communications module to provide for communication with similarly enabled systems and devices or a near field communications NFC sensor for communicating with a NFC device or NFC tag via NFC communications.

Many modifications and other embodiments will come to the mind of one skilled in the art having the benefit of the teachings presented in the foregoing descriptions and the associated drawings. Therefore it is understood that various modifications and embodiments are intended to be included within the scope of the appended claims.

