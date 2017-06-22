---

title: Multimedia device having operating system capable of processing multiple graphic data and method for controlling the same
abstract: A multimedia device provided with an operating system (OS) capable of processing a plurality of graphic data comprises a first client receiving first graphic data of a managed application; a native module pre-processing an application drafted in a native code; a second client receiving second graphic data of the application pre-processed by the native module; a composite module compositing the first graphic data output from the first client and the second graphic data output from the second client; and a display module outputting the composited first and second graphic data, wherein the composite module is accessed to the first client and the second client.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08553152&OS=08553152&RS=08553152
owner: LG Electronics Inc.
number: 08553152
owner_city: Seoul
owner_country: KR
publication_date: 20120106
---
This application claims priority under 35 U.S.C. 119 to U.S. Provisional Application No. 61 431 445 filed on Jan. 11 2011 and Korean Patent Application No. 10 2011 0002943 filed on Jan. 12 2011 whose entire disclosures are hereby incorporated by reference.

The present disclosure relates to a multimedia device technology and more particularly to a multimedia device having an operating system capable of processing multiple graphic data and a method for controlling the same.

A display apparatus is an apparatus having a function for receiving and processing broadcast video for example which can be viewed by a user. The display apparatus displays broadcasting selected by the user from broadcast signals transmitted from a broadcasting station. The worldwide tendency is currently towards digital broadcasting from analog broadcasting.

Digital broadcasting means broadcasting for transmitting digital image and audio signals. Since digital broadcasting is robuster to external noise than analog broadcasting it little causes data loss is more favorable for error correction has high resolution and provides definite picture image. Also digital broadcasting enables bidirectional services unlike analog broadcasting. Recently a smart TV having functions of a display apparatus and functions of a multimedia apparatus has been discussed.

Moreover a mobile device a PC a tablet and a TV which are provided with a specific operating system OS have been developed. However since the specific OS supports an application only drafted in a specific computing language for example C language C language Java language etc. in case of an application drafted in other language a problem occurs in that the application should be redrafted in a corresponding computing language to support its graphics.

The above references are incorporated by reference herein where appropriate for appropriate teachings of additional or alternative details features and or technical background.

Reference will now be made in detail to the preferred embodiments of the present disclosure examples of which are illustrated in the accompanying drawings. Wherever possible the same reference numbers will be used throughout the drawings to refer to the same or like parts.

The terms module and unit attached to describe the names of components are used herein to help the understanding of the components and thus should not be considered as having specific meanings or roles. Accordingly the terms module and unit may be used interchangeably.

An image display device as set forth herein is an intelligent image display device equipped with a computer support function in addition to a broadcast reception function for example. Since an Internet function is added to a broadcast reception function the image display device may have user friendly interfaces such as a handwriting input device a touchscreen or a pointing device. Further because the image display device supports wired or wireless Internet it is capable of e mail transmission reception Web browsing banking gaming etc. by connecting to the Internet or a computer. To implement these functions the image display device may operate based on a standard general purpose Operating System OS such as Windows Linux Android Unix based e.g. MAC OSX .

Various applications can be freely added to or deleted from for example a general purpose OS kernel of the image display device according to the present disclosure. Therefore the image display device may perform a number of user friendly functions. The image display device may be a network TV a Hybrid broadcast broadband TV HBBTV a smart TV etc. for example.

Embodiments of the present disclosure will be described in detail with reference to the attached drawings but it should be understood that they are merely illustrative of the present disclosure and should not be interpreted as limiting the scope of the present disclosure.

In addition although the terms used in the present disclosure are selected from generally known and used terms some of the terms mentioned in the description of the present disclosure the detailed meanings of which are described in relevant parts of the description herein have been selected at the discretion of the applicant. Furthermore the present disclosure must be understood not simply by the actual terms used but by the meanings of each term lying within.

As shown in the broadcast system including the image display device according to the embodiment of the present disclosure may include a Content Provider CP a Service Provider SP a Network Provider NP and a Home Network End Device HNED . The HNED corresponds to for example a client which is an image display device according to an embodiment of the present disclosure. The client corresponds to the image display device according to the embodiment of the present disclosure and the image display device may be a network TV a smart TV an Internet Protocol TV IPTV etc.

The CP creates and provides a variety of content. The CP may be for example a terrestrial broadcaster a cable System Operator SO or Multiple System Operator MSO a satellite broadcaster or an Internet broadcaster as illustrated in .

Besides broadcast content the CP may provide various applications which will be described later in detail.

The SP may provide content received from the CP as a service package. For instance the SP may package first terrestrial broadcasts second terrestrial broadcasts cable MSOs satellite broadcasts various Internet broadcasts and applications and provide the package to users.

The SP may unicast or multicast a service to the client . Unicast is a form of transmission in which data is sent from only one transmitter to only one receiver. In an example of unicast transmission upon receipt of a request for data from a receiver a server transmits the data to only one receiver. Multicast is a type of transmission or communication in which a transmitter transmits data to a group of receivers. For example a server may transmit data to a plurality of pre registered receivers at one time. For multicast registration the Internet Group Management Protocol IGMP may be used.

The NP may provide a network over which a service is provided to the client . The client may construct a home network end user HNED and receive a service over the HNED.

Content transmitted in the above described system including the image display device may be protected through conditional access or content protection. CableCard and Downloadable Conditional Access System DCAS are examples of such conditional access or content protection systems.

The client may also transmit content over a network. In this case the client serves as a CP and thus the CP may receive content from the client . Therefore an interactive content service or data service can be provided.

As shown in the image display device according to another embodiment of the present disclosure is connected to a broadcast network and the Internet. The image display device is for example a network TV a smart TV an HBBTV etc.

The image display device includes for example a broadcast interface a section filter an Application Information Table AIT filter an application data processor a broadcast data processor a media player an Internet Protocol IP processor an Internet interface and a runtime module .

The image display device receives AIT data real time broadcast content application data and stream events through the broadcast interface . The real time broadcast content may be referred to as linear Audio Video A V content.

The section filter performs section filtering on the four types of data received through the broadcast interface and outputs the AIT data to the AIT filter the linear A V content to the broadcast data processor and the stream events and application data to the application data processor .

Meanwhile the image display device receives non linear A V content and application data through the Internet interface . The non linear NV content may be for example a Content On Demand CoD application.

The non linear A V content and the application data are transmitted to the media player and the runtime module respectively.

The runtime module includes for example an application manager and a browser as illustrated in . The application manager controls the life cycle of an interactive application using the AIT data for example. The browser displays and processes the interactive application.

The game application according to one embodiment of the present disclosure is received through the broadcast interface or the Internet interface shown in .

The game application received through the broadcast interface is transmitted to the runtime module through the application data processor . The game application received through the Internet interface is transmitted to the runtime module through the IP processor .

The SP performs an SP discovery operation S . The image display device transmits an SP attachment request signal S . Upon completion of attachment to the SP the image display device receives provisioning information from the SP S . Further the image display device receives Master System Information SI Tables S receives Virtual Channel Map Tables S receives Virtual Channel Description Tables S and receives Source Tables from the SP S .

More specifically SP Discovery is a process by which SPs that provide IPTV services search for servers providing services to the SPs.

In order to receive information e.g. SP discovery information about the service discovery SD servers an SD server address list can be detected for example using three methods specifically use of an address preset in the image display device or an address manually set by a user Dynamic Host Configuration Protocol DHCP based SP Discovery and Domain Name System Service DNS SRV based SP Discovery. The image display device accesses a specific SD server using the SD server address list obtained through one of the above three methods and receives an SP Discovery record from the specific SD server. The Service Provider Discovery record includes information needed to perform Service Discovery on an SP basis. The image display device then starts a Service Discovery operation using the SP Discovery record. These operations can be performed in a push mode or a pull mode.

The image display device accesses an SP attachment server specified by an SP attachment locator included in the SP Discovery record and performs a registration procedure or a service attachment procedure .

Further after accessing an authentication service server of an SP specified by an SP authentication locator and performing an authentication procedure the image display device may perform a service authentication procedure.

Once service attachment is successfully completed a server may transmit data to the image display device in the form of a provision information table.

During service attachment the image display device may include an Identifier ID and location information thereof in data and transmit the data to the service attachment server. Thus the service attachment server may specify a service that the image display device has subscribed to based on the ID and location information. In addition the service attachment server provides in the form of a provisioning information table address information from which the image display device can obtain Service Information SI . The address information corresponds to access information about a Master SI Table. This method facilitates provision of a customized service to each subscriber.

The SI is divided into a Master SI Table record for managing access information and version information about a Virtual Channel Map a Virtual Channel Map Table for providing a list of services in the form of a package a Virtual Channel Description Table that contains details of each channel and a Source Table that contains access information about actual services.

The image display device shown in receives the game application according to the embodiment of the present disclosure from the SP or a virtual channel provided by a broadcast station.

Each Virtual Channel MAP is identified by its Virtual Channel MAP identifier. Virtual Channel MAP Version specifies the version number of the Virtual Channel MAP. If any of the tables connected to the Master SI Table shown in in the arrowed direction is modified the versions of the modified table and overlying tables thereof up to the Master SI Table are incremented. Accordingly a change in any of the SI tables can be readily identified by monitoring the Master SI Table.

For example when the Source Table is changed the version of the Source Table is incremented and the version of the Virtual Channel Description Table that references the Source Table is also incremented. In conclusion a change in any lower table leads to a change in its higher tables and eventually a change in the Master SI Table.

One Master SI Table may exist for each SP. However in the case where service configurations differ for regions or subscribers or subscriber groups an SP may have a plurality of Master SI Tables in order to provide a customized service on a unit basis. Thus it is possible to efficiently provide a customized service to a subscriber through the master SI table according to a region in which the subscriber is located and subscriber information regarding the subscriber.

A Virtual Channel Map Table may contain one or more virtual channels. A Virtual Channel Map includes not only details of the channels but information about the locations of the details of the channels. In the Virtual Channel Map Table Virtual Channel Description Location specifies the location of a Virtual Channel Description Table including the details of the channels.

The Virtual Channel Description Table contains the details of the virtual channels. The Virtual Channel Description Table can be accessed using the Virtual Channel Description Location of the Virtual Channel Map Table.

A Source Table provides information necessary to access actual services e.g. IP addresses ports AV Codecs transmission protocols etc. on a service basis.

The above described Master SI Table the Virtual Channel Map Table the Virtual Channel Description Table and the Source Table are delivered in four logically separate flows in a push mode or a pull mode. For version management the Master SI Table may be multicast and thus version changes can be monitored by receiving a multicast stream.

An image display device includes a network interface a Transmission Control Protocol Internet Protocol TCP IP manager a service delivery manager a demultiplexer DEMUX a Program Specific Information PSI Program and System Information Protocol PSIP and or SI decoder an audio decoder a video decoder a display A V and OSD module a service control manager a service discovery manager a metadata manager an SI metadata database DB a User Interface UI manager and a service manager .

The network interface transmits packets to and receives packets from a network. Specifically the network interface receives services and content from an SP over the network.

The TCP IP manager is involved in packet reception and transmission of the image display device that is packet delivery from a source to a destination. The TCP IP manager classifies received packets according to appropriate protocols and outputs the classified packets to the service delivery manager the service discovery manager the service control manager and the metadata manager .

For example when controlling real time streaming data the service delivery manager may use the Real time Transport Protocol Real time Transport Control Protocol RTP RTCP . If real time streaming data is transmitted over RTP the service delivery manager parses the received real time streaming data using RTP and transmits the parsed real time streaming data to the DEMUX or stores the parsed real time streaming data in the SI metadata DB under the control of the service manager . In addition the service delivery manager feeds back network reception information to a server that provides the service using RTCP.

The DEMUX demultiplexes a received packet into audio data video data and PSI data and transmits the audio data video data and PSI data to the audio decoder the video decoder and the PSI PSIP and or SI decoder respectively.

The PSI PSIP and or SI decoder decodes SI such as PSI. More specifically the PSI PSIP and or SI decoder receives and decodes PSI sections PSIP sections or SI sections demultiplexed by the DEMUX .

The PSI PSIP and or SI decoder constructs an SI DB by decoding the received sections and stores the SI DB in the SI metadata DB .

The audio decoder and the video decoder decode the audio data and the video data received from the DEMUX and output the decoded audio and video data to a user through the display A V and OSD module .

The UI manager and the service manager manage the overall state of the image display device provide UIs and manage other managers.

The UI manager provides a Graphical User Interface GUI in the form of an OSD and performs a reception operation corresponding to a key input received from the user. For example upon reception of a key input signal regarding channel selection from the user the UI manager transmits the key input signal to the service manager .

The service manager controls managers associated with services such as the service delivery manager the service discovery manager the service control manager and the metadata manager .

The service manager also creates a channel map and selects a channel using the channel map according to the key input signal received from the UI manager . The service manager sets the audio video Packet ID PID of the selected channel based on SI of the channel received from the PSI PSIP and or SI decoder in the demultiplexer .

The service discovery manager provides information necessary to select an SP that provides a service. Upon receipt of a channel selection signal from the service manager the service discovery manager detects a service based on the channel selection signal.

The service control manager takes charge of selection and control services. For example if a user selects a live broadcasting service such as a conventional broadcasting service the service control manager selects and controls the service using Internet Group Management Protocol IGMP or Real Time Streaming Protocol RTSP . If the user selects Video on Demand VoD the service control manager selects and controls the service using RTSP.

RTSP supports trick mode for real time streaming. Further the service control manager may initialize and manage a session through an IP Multimedia Control IMC gateway using IP Multimedia Subsystem IMS and Session Initiation Protocol SIP . The protocols are only exemplary and thus other protocols are also applicable.

The metadata manager manages metadata related to services and stores the metadata in the SI metadata DB .

The SI metadata DB stores the SI decoded by the PSI PSIP and or SI decoder the metadata managed by the metadata manager and the information required to select an SP received from the service discovery manager . The SI metadata DB may store system setup data.

The UI manager of the image display device shown in serves to control the game application according to the embodiment of the present disclosure. In particular the UI manager operates according to a user input signal.

Referring to an image display device according to another embodiment of the present disclosure includes a broadcast receiver an external device interface a memory a user input interface a controller a display an audio output unit a power supply and a camera module not shown . The broadcasting receiver may include a tuner a demodulator and a network interface . As needed the broadcasting receiver may be configured so as to include only the tuner and the demodulator or only the network interface .

The tuner tunes to a Radio Frequency RF broadcast signal corresponding to a channel selected by a user from among a plurality of RF broadcast signals received through an antenna and downconverts the tuned RF broadcast signal into a digital Intermediate Frequency IF signal or an analog baseband video or audio signal.

More specifically if the tuned RF broadcast signal is a digital broadcast signal the tuner downconverts the tuned RF broadcast signal into a digital IF signal DIF . On the other hand if the tuned RF broadcast signal is an analog broadcast signal the tuner downconverts the tuned RF broadcast signal into an analog baseband video or audio signal CVBS SIF. That is the tuner may be a hybrid tuner capable of processing not only digital broadcast signals but also analog broadcast signals. The analog baseband video or audio signal CVBS SIF may be directly input to the controller .

The tuner may be capable of receiving RF broadcast signals from an Advanced Television Systems Committee ATSC single carrier system or from a Digital Video Broadcasting DVB multi carrier system.

The tuner may sequentially tune to a number of RF broadcast signals corresponding to all broadcast channels previously stored by a channel storage function from a plurality of RF signals received through the antenna and may downconvert the tuned RF broadcast signals into IF signals or baseband video or audio signals.

The demodulator receives the digital IF signal DIF from the tuner and demodulates the digital IF signal DIF.

For example if the digital IF signal DIF is an ATSC signal the demodulator may perform 8 Vestigal SideBand VSB demodulation on the digital IF signal DIF. The demodulator may also perform channel decoding.

For channel decoding the demodulator may include a Trellis decoder not shown a de interleaver not shown and a Reed Solomon decoder not shown so as to perform Trellis decoding de interleaving and Reed Solomon decoding.

For example if the digital IF signal DIF is a DVB signal the demodulator performs Coded Orthogonal Frequency Division Multiple Access COFDMA demodulation upon the digital IF signal DIF. The demodulator may also perform channel decoding. For channel decoding the demodulator may include a convolution decoder not shown a de interleaver not shown and a Reed Solomon decoder not shown so as to perform convolution decoding de interleaving and Reed Solomon decoding.

The demodulator may perform demodulation and channel decoding on the digital IF signal DIF thereby obtaining a Transport Stream TS . The TS may be a signal in which a video signal an audio signal and a data signal are multiplexed. For example the TS may be an MPEG 2 TS in which an MPEG 2 video signal and a Dolby AC 3 audio signal are multiplexed. An MPEG 2 TS may include a 4 byte header and a 184 byte payload.

In order to properly handle not only ATSC signals but also DVB signals the demodulator may include an ATSC demodulator and a DVB demodulator.

The TS output from the demodulator may be input to the controller and thus subjected to demultiplexing and A V signal processing. The processed video and audio signals are output to the display and the audio output unit respectively.

The external device interface may serve as an interface between an external device and the image display device . For interfacing the external device interface may include an A V Input Output I O unit not shown and or a wireless communication module not shown .

The external device interface may be connected to an external device such as a Digital Versatile Disc DVD player a Blu ray player a game console a camera a camcorder or a computer e.g. a laptop computer wirelessly or by wire. Then the external device interface externally receives video audio and or data signals from the external device and transmits the received input signals to the controller . In addition the external device interface may output video audio and data signals processed by the controller to the external device. In order to receive or transmit audio video and data signals from or to the external device the external device interface includes the A V I O unit not shown and or the wireless communication module not shown .

The A V I O unit may include a Universal Serial Bus USB port a Composite Video Banking Sync CVBS port a Component port a Super video S video analog port a Digital Visual Interface DVI port a High Definition Multimedia Interface HDMI port a Red Green Blue RGB port and a D sub port in order to input the video and audio signals of the external device to the image display device .

The wireless communication module may perform short range wireless communication with other electronic devices. For short range wireless communication the wireless communication module may use Bluetooth Radio Frequency IDentification RFID Infrared Data Association IrDA Ultra WideBand UWB ZigBee and Digital Living Network Alliance DLNA communication standards.

The external device interface may be connected to various set top boxes through at least one of the above described ports and may thus perform an I O operation with the various set top boxes.

The external device interface may receive applications or an application list from an adjacent external device and provide the applications or the application list to the controller or the memory .

The network interface serves as an interface between the image display device and a wired wireless network such as the Internet. The network interface may include an Ethernet port for connection to a wired network. For connection to wireless networks the network interface may use Wireless Local Area Network WLAN i.e. Wi Fi Wireless Broadband WiBro World Interoperability for Microwave Access WiMax and High Speed Downlink Packet Access HSDPA .

The network interface may transmit data to or receive data from another user or electronic device over a connected network or another network linked to the connected network. Especially the network interface may transmit data stored in the image display device to a user or electronic device selected from among users or electronic devices pre registered with the image display device .

The network interface may access a specific Web page over a connected network or another network linked to the connected network. That is the network interface may access a specific Web page over a network and transmit or receive data to or from a server. Additionally the network interface may receive content or data from a CP or an NP. Specifically the network interface may receive content such as movies advertisements games VoD and broadcast signals and information related to the content from a CP or an NP. Also the network interface may receive update information about firmware from the NP and update the firmware. The network interface may transmit data over the Internet or to the CP or the NP.

The network interface may selectively receive a desired application among open applications over a network.

In an embodiment of the present disclosure when a game application is executed in the image display device the network interface may transmit data to or receive data from a user terminal connected to the image display device through a network. In addition the network interface may transmit specific data to or receive specific data from a server that records game scores.

The memory may store various programs necessary for the controller to process and control signals and may also store processed video audio and data signals.

The memory may temporarily store a video audio and or data signal received from the external device interface or the network interface .

The memory may store applications or a list of applications received from the external device interface or the network interface .

In an embodiment of the present disclosure when the image display device provides a game application the memory may store user specific information and game play information of a user terminal used as a game controller.

The memory may include for example at least one of a flash memory type storage medium a hard disk type storage medium a multimedia card micro type storage medium a card type memory e.g. a Secure Digital SD or eXtreme Digital XD memory a Random Access Memory RAM or a Read Only Memory ROM such as an Electrically Erasable and Programmable Read Only Memory EEPROM . The image display device may reproduce content stored in the memory e.g. video files still image files music files text files and application files to the user.

While the memory is shown in as configured separately from the controller to which the present disclosure is not limited the memory may be incorporated into the controller for example.

The user input interface transmits a signal received from the user to the controller or transmits a signal received from the controller to the user.

For example the user input interface may receive control signals such as a power on off signal a channel selection signal and a screen setting signal from a remote controller or may transmit a control signal received from the controller to the remote controller according to various communication schemes for example RF communication and IR communication.

For example the user input interface may provide the controller with control signals received from local keys not shown such as inputs of a power key a channel key and a volume key and setting values.

Also the user input interface may transmit a control signal received from a sensor unit not shown for sensing a user gesture to the controller or transmit a signal received from the controller to the sensor unit. The sensor unit may include a touch sensor a voice sensor a position sensor a motion sensor etc.

The controller may demultiplex the TS received from the tuner the demodulator or the external device interface into a number of signals and process the demultiplexed signals into audio and video data.

The video signal processed by the controller may be displayed as an image on the display . The video signal processed by the controller may also be transmitted to an external output device through the external device interface .

The audio signal processed by the controller may be audibly output through the audio output unit . Also the audio signal processed by the controller may be transmitted to the external output device through the external device interface .

While not shown in the controller may include a DEMUX and a video processor which will be described later with reference to .

In addition the controller may provide overall control to the image display device . For example the controller may control the tuner to tune to an RF broadcast signal corresponding to a user selected channel or a pre stored channel.

The controller may control the image display device according to a user command received through the user input interface or according to an internal program. Especially the controller may access a network and download an application or application list selected by the user to the image display device over the network.

For example the controller controls the tuner to receive a signal of a channel selected according to a specific channel selection command received through the user input interface and processes a video audio and or data signal of the selected channel. The controller outputs the processed video or audio signal along with information about the user selected channel to the display or the audio output unit .

As another example the controller outputs a video or audio signal received from an external device such as a camera or a camcorder through the external device interface to the display or the audio output unit according to an external device video playback command received through the external device interface .

The controller may control the display to display images. For instance the controller may control the display to display a broadcast image received from the tuner an externally input image received through the external device interface an image received through the network interface or an image stored in the memory . The image displayed on the display may be a Two Dimensional 2D or Three Dimensional 3D still image or moving picture.

The controller may control content playback. The content may include any content stored in the image display device received broadcast content and externally input content. The content includes at least one of a broadcast image an externally input image an audio file a still image a Web page or a text file.

Upon receipt of a return to home screen input the controller may control display of the home screen on the display .

The home screen may include a plurality of card objects classified according to content sources. The card objects may include at least one of a card object representing a thumbnail list of broadcast channels a card object representing a broadcast program guide a card object representing a program reservation list or a program recording list or a card object representing a media list of a device connected to the image display device.

The card objects may further include at least one of a card object representing a list of connected external devices or a card object representing a call associated list.

The home screen may further include an application menu including at least one application that can be executed. Accordingly the game application according to the embodiment of the present disclosure may be designed in a format selectable through the application menu of the above described home screen. Further in the present disclosure user convenience may be improved by adding or deleting the game application to or from the application menu according to user selection.

Upon receipt of a card object move input the controller may control movement of a card object corresponding to the card object move input on the display or if the card object is not displayed on the display the controller may control display of the card object on the display .

When a card object is selected from among the card objects on the home screen the controller may control display of an image corresponding to the selected card object on the display .

The controller may control display of an input broadcast image and an object representing information about the broadcast image in a card object representing broadcast images. The size of the broadcast image may be set to a fixed size.

The controller may control display of a set up object for at least one of image setting audio setting screen setting reservation setting setting of a pointer of the remote controller or network setting on the home screen.

The controller may control display of a log in object a help object or an exit object on a part of the home screen.

The controller may control display of an object representing the total number of available card objects or the number of card objects displayed on the display among all card objects on a part of the home screen.

If one of the card objects displayed on the display is selected the controller may fullscreen the selected card object to cover the entirety of the display .

Upon receipt of an incoming call at a connected external device or the image display device the controller may control focusing on or shift of a call related card object among the plurality of card objects.

If an application view menu item is selected the controller may control display of applications or a list of applications that are present in the image display device or downloadable from an external network.

The controller may control installation and execution of an application downloaded from the external network along with various UIs.

Also the controller may control display of an image related to the executed application on the display upon user selection.

In an embodiment of the present disclosure when the image display device provides a game application the controller may control assignment of player IDs to specific user terminals creation of game play information by executing the game application transmission of the game play information corresponding to the player IDS assigned to the user terminals through the network interface and reception of the game play information at the user terminals.

The controller may control detection of user terminals connected to the image display device over a network through the network interface display of a list of the detected user terminals on the display and reception of a selection signal indicating a user terminal selected for use as a user controller from among the detected user terminals through the user input interface .

The controller may control output of a game play screen of the game application inclusive of player information of each user terminal and game play information through the display .

The controller may determine the specific signal received from a user terminal through the network interface as game play information and thus control the game play information to be reflected in the game application in progress.

The controller may control transmission of the game play information of the game application to a specific server connected over a network through the network interface .

As another embodiment upon receipt of information about a change in the game play information from a predetermined server through the network interface the controller may control output of a notification message in a predetermined area of the display .

Although not shown the image display device may further include a channel browsing processor for generating thumbnail images corresponding to channel signals or externally input signals.

The channel browsing processor may receive the TS output from the demodulator or the TS output from the external device interface extract images of the received TS and generate thumbnail images. The thumbnail images may be directly output to the controller or may be output after being encoded. Also it is possible to encode the thumbnail images into a stream and output the stream to the controller . The controller may display a thumbnail list including a plurality of received thumbnail images on the display . The thumbnail images may be updated sequentially or simultaneously in the thumbnail list. Therefore the user can readily identify the content of broadcast programs received through a plurality of channels.

The display may convert a processed video signal a processed data signal and an OSD signal received from the controller or a video signal and a data signal received from the external device interface into RGB signals thereby generating driving signals.

The display may be various types of displays such as a Plasma Display Panel PDP a Liquid Crystal Display LCD an Organic Light Emitting Diode OLED display a flexible display and a 3D display.

The display may also be a touchscreen that can be used not only as an output device but also as an input device.

The audio output unit may receive a processed audio signal e.g. a stereo signal a 3.1 channel signal or a 5.1 channel signal from the controller and output the received audio signal as sound. The audio output unit may employ various speaker configurations.

To sense a user gesture the image display device may further include the sensor unit not shown that has at least one of a touch sensor a voice sensor a position sensor and a motion sensor as stated before. A signal sensed by the sensor unit may be output to the controller through the user input interface .

The image display device may further include the camera unit not shown for capturing images of a user. Image information captured by the camera unit may be input to the controller .

The controller may sense a user gesture from an image captured by the camera unit or a signal sensed by the sensor unit or by combining the captured image and the sensed signal.

Particularly the power supply may supply power to the controller which may be implemented as a System On Chip SOC the display for displaying an image and the audio output unit for audio output.

For supplying power the power supply may include a converter not shown for converting Alternating Current AC into Direct Current DC . If the display is configured with for example a liquid crystal panel having a plurality of backlight lamps the power supply may further include an inverter not shown capable of performing Pulse Width Modulation PWM for luminance change or dimming driving.

The remote controller transmits a user input to the user input interface . For transmission of user input the remote controller may use various communication techniques such as Bluetooth RF communication IR communication Ultra Wideband UWB and ZigBee.

In addition the remote controller may receive a video signal an audio signal or a data signal from the user input interface and output the received signals visually audibly or as vibrations.

The above described image display device may be a fixed digital broadcast receiver capable of receiving at least one of ATSC 8 VSB broadcast programs DVB T COFDM broadcast programs and ISDB T BST OFDM broadcast programs.

The block diagram of the image display device illustrated in is purely exemplary. Depending upon the specifications of the image display device in actual implementation the components of the image display device may be combined or omitted or new components may be added. That is two or more components may be incorporated into one component or one component may be configured as separate components as needed. In addition the function of each block is described for the purpose of describing the embodiment of the present disclosure and thus specific operations or devices should not be construed as limiting the scope and spirit of the present disclosure.

Unlike the configuration illustrated in the image display device may be configured so as to receive and play back video content through the network interface or the external device interface without the tuner and the demodulator shown in .

The game application according to the embodiment of the present disclosure is received through the network interface of the image display device shown in . Further the received game application is stored in the memory .

The network interface performs communication with a mobile device executing the above described game application.

The image display device is an exemplary image signal processing device that processes a stored image or an input image. Other examples of the image signal processing device include a set top box without the display and the audio output unit a DVD player a Blu ray player a game console and a computer. The set top box will be described later with reference to .

The set top box may include a network interface a memory a signal processor a user input interface and an external device interface .

The network interface serves as an interface between the set top box and a wired wireless network such as the Internet. The network interface may transmit data to or receive data from another user or another electronic device over a connected network or over another network linked to the connected network.

The memory may store programs necessary for the signal processor to process and control signals and temporarily store a video audio and or data signal received from the external device interface or the network interface . The memory may also store platforms shown in as described later.

The signal processor processes an input signal. For example the signal processor may demultiplex or decode an input video or audio signal. For signal processing the signal processor may include a video decoder or an audio decoder. The processed video or audio signal may be transmitted to the display device through the external device interface .

The user input interface transmits a signal received from the user to the signal processor or a signal received from the signal processor to the user. For example the user input interface may receive various control signals such as a power on off signal an operation input signal and a setting input signal through a local key not shown or the remote controller and output the control signals to the signal processor .

The external device interface serves as an interface between the set top box and an external device that is connected wirelessly or by wire particularly the display device for data transmission or reception. The external device interface may also interface with an external device such as a game console a camera a camcorder and a computer e.g. a laptop computer for data transmission or reception.

The set top box may further include a media input unit for media playback. The media input unit may be a Blu ray input unit not shown for example. That is the set top box may include a Blu ray player. After signal processing such as demultiplexing or decoding in the signal processor a media signal from a Blu ray disc may be transmitted to the display device through the external device interface so as to be displayed on the display device .

The display device may include a tuner an external device interface a demodulator a memory a controller a user input interface a display and an audio output unit .

The tuner the demodulator the memory the controller the user input interface the display and the audio output unit are identical respectively to the tuner the demodulator the memory the controller the user input interface the display and the audio output unit illustrated in and thus a description thereof is not provided herein.

The external device interface serves as an interface between the display device and a wireless or wired external device particularly the set top box for data transmission or reception.

Hence a video signal or an audio signal received through the set top box is output through the display or through the audio output unit under control of the controller .

Referring to the configuration of the set top box and the display device shown in is similar to that of the set top box and the display device shown in except that the tuner and the demodulator reside in the set top box not in the display device .

The signal processor may process a broadcast signal received through the tuner and the demodulator . The user input interface may receive a channel selection input a channel store input etc.

As shown in the image display device according to the embodiment of the present disclosure may communicate with a broadcast station a network server or an external device .

The image display device may receive a broadcast signal including a video signal from the broadcast station . The image display device may process the audio and video signals of the broadcast signal or the data signal of the broadcast signal suitably for output from the image display device . The image display device may output video or audio based on the processed video or audio signal.

Meanwhile the image display device may communicate with the network server . The network server is capable of transmitting signals to and receiving signals from the image display device over a network.

For example the network server may be a portable terminal that can be connected to the image display device through a wired or wireless base station. In addition the network server may provide content to the image display device over the Internet. A CP may provide content to the image display device through the network server.

The image display device may communicate with the external device . The external device can transmit and receive signals directly to and from the image display device wirelessly or by wire. For instance the external device may be a media storage or player. That is the external device may be any of a camera a DVD player a Blu ray player a PC etc.

The broadcast station the network server or the external device may transmit a signal including a video signal to the image display device . The image display device may display an image based on the video signal included in the received signal. Also the image display device may transmit a signal transmitted from the network server to the broadcast station to the external device and may transmit a signal transmitted from the external device to the image display device to the broadcast station or the network server . That is the image display device may transmit content included in signals received from the broadcast station the network server and the external device or may immediately play back the content.

The controller may include a DEMUX a video processor an OSD generator a mixer a Frame Rate Converter FRC and a formatter according to an embodiment of the present disclosure. The controller may further include an audio processor not shown and a data processor not shown .

The DEMUX demultiplexes an input stream. For example the DEMUX may demultiplex an MPEG 2 TS into a video signal an audio signal and a data signal. The stream signal input to the DEMUX may be received from the tuner the demodulator or the external device interface .

The video decoder decodes the demultiplexed video signal and the scaler scales the decoded video signal so that the video signal can be displayed on the display .

If the demultiplexed video signal is for example an MPEG 2 encoded video signal the video signal may be decoded by an MPEG 2 decoder.

On the other hand if the video signal is an H.264 encoded DMB or DVB handheld DVB H signal the video signal may be decoded by an H.264 decoder.

The OSD generator generates an OSD signal autonomously or according to user input. For example the OSD generator may generate signals by which a variety of information is displayed as graphics or text on the display based on control signals received from the user input interface . The generated OSD signal may include various data such as a UI screen a variety of menu screens widgets icons etc. of the image display device

For example the OSD generator may generate a signal by which subtitles are displayed for a broadcast image or Electronic Program Guide EPG based broadcasting information.

The mixer may mix the decoded video signal processed by the image processor with the OSD signal generated by the OSD generator and output the mixed signal to the formatter . As the decoded broadcast video signal or the externally input signal is mixed with the OSD signal an OSD may be overlaid on the broadcast image or the externally input image.

The FRC may change the frame rate of an input image signal. For example a frame rate of 60 Hz is converted into a frame rate of 120 or 240 Hz. When the frame rate is to be changed from 60 Hz to 120 Hz a first frame is inserted between the first frame and a second frame or a predicted third frame is inserted between the first and second frames. If the frame rate is to be changed from 60 Hz to 240 Hz three identical frames or three predicted frames are inserted between the first and second frames. It is also possible to maintain the frame rate of the input image without frame rate conversion.

The formatter changes the format of the signal received from the FRC to suit the display . For example the formatter may convert a received signal into an RGB data signal. The RGB signal may be output in the form of a Low Voltage Differential Signal LVDS or mini LVDS.

The audio processor not shown of the controller may process the demultiplexed audio signal. For audio signal processing the audio processor not shown may have a plurality of decoders.

If the demultiplexed audio signal is a coded audio signal the audio processor not shown of the controller may decode the audio signal. For example the demultiplexed audio signal may be decoded by an MPEG 2 decoder an MPEG 4 decoder an Advanced Audio Coding AAC decoder or an AC 3 decoder.

The audio processor not shown of the controller may also adjust the bass treble or volume of the audio signal.

The data processor not shown of the controller may process the demultiplexed data signal. For example if the demultiplexed data signal is an encoded data signal such as an Electronic Program Guide EPG which includes broadcast information specifying the start time end time etc. of scheduled broadcast programs of each channel the controller may decode the data signal. Examples of an EPG include ATSC Program and System Information Protocol PSIP information and DVB Service Information SI .

ATSC PSIP information or DVB SI may be included in the header of the above described TS i.e. a 4 byte header of an MPEG 2 TS.

The block diagram of the controller shown in is an embodiment of the present disclosure. Depending upon the specifications of the controller the components of the controller may be combined or omitted. Or new components may be added to the controller .

A platform for either of the image display devices according to the embodiments of the present disclosure may have OS based software to implement the above described various operations.

Referring to a platform for either of the image display devices according to the embodiments of the present disclosure is of a separate type. The platform may be designed separately as a legacy system platform and a smart system platform . An OS kernel may be shared between the legacy system platform and the smart system platform .

The legacy system platform may include a stack of a driver middleware and an application layer on the OS kernel .

On the other hand the smart system platform may include a stack of a library a framework and an application layer on the OS kernel .

The OS kernel is the core of an operating system. When the image display device is driven the OS kernel may be responsible for operation of at least one of control of hardware drivers security protection for hardware and processors in the image display device efficient management of system resources memory management hardware interfacing by hardware abstraction multi processing or scheduling associated with multi processing. Meanwhile the OS kernel may further perform power management.

The hardware drivers of the OS kernel may include for example at least one of a display driver a Wi Fi driver a Bluetooth driver a USB driver an audio driver a power manager a binder driver or a memory driver.

Alternatively or additionally the hardware drivers of the OS kernel may be drivers for hardware devices within the OS kernel . The hardware drivers may include a character device driver a block device driver and a network device driver. The block device driver may require a buffer for buffering data on a block basis because data is transmitted on a block basis. The character device driver may not need a buffer since data is transmitted on a basic data unit basis that is on a character basis.

The OS kernel may be implemented based on any of various OSs such as Unix Linux or MAC OS Windows etc. The OS kernel may be a general purpose open source kernel which can be implemented in other electronic devices.

The driver is interposed between the OS kernel and the middleware . Along with the middleware the driver drives devices for operation of the application layer . For example the driver may include a driver s for a microcomputer a display module a Graphics Processing Unit GPU an FRC a General Purpose Input Output GPIO pin a High Definition Multimedia Interface HDMI a System Decoder SDEC or DEMUX a Video Decoder VDEC an Audio Decoder ADEC a Personal Video Recorder PVR and or an Inter Integrated Circuit I2C . These drivers operate in conjunction with the hardware drivers of the OS kernel .

In addition the driver may further include a driver for the remote controller especially a pointing device to be described below. The remote controller driver may reside in the OS kernel or the middleware instead of the driver .

The middleware resides between the OS kernel and the application layer . The middleware may mediate between different hardware devices or different software programs for data transmission and reception between the hardware devices or the software programs. Therefore the middleware can provide standard interfaces support various environments and enable interaction between tasks conforming to heterogeneous communication protocols.

Examples of the middleware in the legacy system platform may include Multimedia and Hypermedia information coding Experts Group MHEG and Advanced Common Application Platform ACAP as data broadcasting related middleware PSIP or SI middleware as broadcasting information related middleware and DLNA middleware as peripheral device communication related middleware.

The application layer that runs atop the middleware in the legacy system platform may include for example UI applications associated with various menus in the image display device. The application layer on top of the middleware may allow editing and updating over a network by user selection. Through the application layer the user may navigate a desired menu by manipulating the remote controller while viewing a broadcast program.

The application layer in the legacy system platform may further include at least one of a TV guide application a Bluetooth application a reservation application a Digital Video Recorder DVR application and a hotkey application.

In the smart system platform the library is positioned between the OS kernel and the framework forming the basis of the framework . For example the library may include Secure Socket Layer SSL a security related library WebKit a Web engine related library c library libc and Media Framework a media related library specifying for example a video format and an audio format. The library may be written in C or C . Also the library may be exposed to a developer through the framework .

The library may include a runtime with a core Java library and a Virtual Machine VM . The runtime and the library form the basis of the framework .

The VM may be a virtual machine that enables concurrent execution of a plurality of instances that is multi tasking. For each application of the application layer a VM may be allocated and executed. For scheduling or interconnection between the plurality of instances the binder driver not shown of the OS kernel may operate.

In the smart system platform the framework includes programs on which applications of the application layer are based. The framework is compatible with any application and may allow component reuse movement or exchange. The framework may include supporting programs and programs for interconnecting different software components. For example the framework may include an activity manager related to activities of applications a notification manager and a CP for abstracting common information between applications. This framework may be written in Java.

The application layer on top of the framework includes a variety of programs that can be executed and displayed in the image display device. The application layer may include for example a core application that is a suite providing at least one of e mail Short Message Service SMS calendar map or browser functions. The application layer may be written in Java.

In the application layer applications may be categorized into user undeletable applications stored in the image display device or user deletable applications that are downloaded from an external device or a network and stored in the image display device.

Using the applications of the application layer a variety of functions such as an Internet telephony service VoD service Web album service Social Networking Service SNS Location Based Service LBS map service Web browsing service and application search service may be performed through network access. In addition other functions such as gaming and schedule management may be performed by the applications.

Referring to a platform for any of the image display devices according to the embodiments of the present disclosure is of an integrated type. The integrated type platform may include an OS kernel a driver middleware a framework and an application layer .

The integrated type platform shown in is different from the separate type platform shown in in that the library shown in is deleted and the application layer is included as an integrated layer. The driver and the framework correspond to the driver and the framework of respectively.

The library of may be incorporated into the middleware of . That is the middleware may include both the legacy system middleware and the image display system middleware. As described before the legacy system middleware includes MHEG or ACAP as data broadcasting related middleware PSIP or SI middleware as broadcasting information related middleware and DLNA middleware as peripheral device communication related middleware and the image display system middleware includes SSL as a security related library WebKit as a Web engine related library libc and Media Framework as a media related library. The middleware may further include the above described runtime.

The application layer may include a menu related application a TV guide application a reservation application etc. as legacy system applications and e mail SMS a calendar a map and a browser as image display system applications.

In the application layer applications may be categorized into user undeletable applications that are stored in the image display device and user installable or user deletable applications that are downloaded from an external device or a network and stored in the image display device.

The platforms shown in may be general purpose ones that can be implemented in many other electronic devices as well as in image display devices. The platforms of may be stored or loaded in the memory the controller or any other processor not shown or may be stored or load in the SI metadata DB the UI manager or the service manager shown in . To execute applications an additional application processor not shown may be further provided.

The game application according to the embodiment of the present disclosure is located in the application layer shown in or .

In particular if the game application is installed in a process of producing a display device e.g. TV the display device is designed such that a user of the display device may not arbitrarily access or delete the game application.

The user may move or rotate the remote controller up and down side to side and back and forth . The pointer displayed on the display of the image display device moves according to the movement of the remote controller . Since the pointer moves in accordance with the movement of the remote controller in a 3D space as shown in the remote controller may be referred to as a pointing device.

Referring to if the user moves the remote controller to the left the pointer moves to the left on the display .

A sensor of the remote controller detects movement of the remote controller and transmits motion information of the remote controller to the image display device. Then the image display device calculates the coordinates of the pointer from the motion information of the remote controller . The image display device then displays the pointer at the calculated coordinates.

Referring to while pressing a predetermined button of the remote controller the user moves the remote controller away from the display . Then a selected area corresponding to the pointer may be zoomed in on and enlarged on the display . On the contrary if the user moves the remote controller toward the display the selected area corresponding to the pointer is zoomed out and thus contracted on the display . On the contrary when the remote controller moves away from the display the selected area may be zoomed out and when the remote controller approaches the display the selected area may be zoomed in.

With the predetermined button of the remote controller pressed the up down left and right movements of the remote controller may be ignored. That is when the remote controller moves away from or approaches the display only the back and forth movements of the remote controller are sensed while the up down left and right movements of the remote controller are ignored. Unless the predetermined button is pressed in the remote controller the pointer moves in accordance with the up down left or right movement of the remote controller .

The movement speed and direction of the pointer may correspond to the movement speed and direction of the remote controller .

The pointer of the present specification is an object displayed on the display in correspondence with the movement of the remote controller . Therefore the pointer may have various shapes other than the arrow illustrated in . For example the pointer may be a dot a cursor a prompt a thick outline etc. The pointer may be displayed across a plurality of points such as a line and a surface as well as at a single point on horizontal and vertical axes.

Referring to the remote controller may include a wireless communication module a user input unit a sensor unit an output unit a power supply a memory and a controller .

The wireless communication module transmits signals to and or receives signals from either of the above described image display devices according to the embodiments of the present disclosure that is the image display device .

The remote controller may include an RF module for transmitting RF signals to and or receiving RF signals from the image display device according to an RF communication standard. The remote controller may also include an IR module for transmitting IR signals to and or receiving IR signals from the image display device according to an IR communication standard.

In the present embodiment the remote controller transmits motion information representing movement of the remote controller to the image display device through the RF module .

The remote controller may also receive signals from the image display device through the RF module . As needed the remote controller may transmit commands such as a power on off command a channel switch command or a volume change command to the image display device through the IR module .

The user input unit may include a keypad a plurality of buttons a touchpad and or a touchscreen. The user may enter commands associated with the image display device to the remote controller by manipulating the user input unit . If the user input unit includes a plurality of hard buttons the user may input various commands associated with the image display device to the remote controller by pressing the hard buttons. Alternatively or additionally if the user input unit includes a touchscreen displaying a plurality of soft keys the user may input various commands associated with the image display device to the remote controller by touching the soft keys. The user input unit may also include various input tools other than those set forth herein such as a scroll key and or a jog wheel which should not be construed as limiting the present disclosure.

For example the gyro sensor may sense movement of the remote controller in X Y and Z axis directions. The acceleration sensor may sense the speed of the remote controller . The sensor unit may further include a distance sensor for sensing the distance between the remote controller and the display device .

The output unit may output a video and or audio signal corresponding to manipulation of the user input unit or corresponding to a signal received from the image display device . The user may easily identify whether the user input unit has been manipulated or whether the image display device has been controlled based on the video and or audio signal output by the output unit .

The output unit may include a Light Emitting Diode LED module which is turned on or off whenever the user input unit is manipulated or whenever a signal is received from or transmitted to the image display device through the wireless communication module a vibration module which generates vibrations an audio output module which outputs audio data and or a display module which outputs video data.

The power supply supplies power to the remote controller . If the remote controller remains stationary for a predetermined time or longer the power supply may for example reduce or shut off supply of power to the spatial remote controller in order to save power. The power supply may resume power supply if a predetermined key of the remote controller is manipulated.

The memory may store various types of programs and application data necessary to control or drive the remote controller . The remote controller may wirelessly transmit signals to and or receive signals from the image display device over a predetermined frequency band with the aid of the RF module . The controller of the remote controller may store information regarding the frequency band used for the remote controller to wirelessly transmit signals to and or wirelessly receive signals from the paired image display device in the memory for later use.

The controller provides overall control to the remote controller . The controller may transmit a signal corresponding to a key manipulation detected from the user input unit or a signal corresponding to motion of the remote controller as sensed by the sensor unit 

In association with the embodiments of the present disclosure the remote controller may correspond to a user terminal necessary to execute a game application.

Accordingly in association with gaming by the game application of the present disclosure a signal input through the user input unit of the remote controller is analyzed by the controller and is transmitted to the image display device through the wireless communication module thereby being applied to the played game. That is the game may be played by controlling a card or a pointer displayed on the image display device.

In the embodiment the remote controller may determine a distance between the image display device and the remote controller using the wireless communication module or the distance sensor not shown . If the remote controller moves away from the image display device a game main screen displayed on the image display device is enlarged and if the remote controller approaches the image display device the game main screen is reduced. Enlargement and reduction may be inversely controlled according to user setting.

In another embodiment enlargement and reduction may be performed only when the distance between the remote controller and the image display apparatus is changed in a state in which a predetermined button of the remote controller is pressed.

Referring to an application list received over a network is displayed on the display . A user may directly access a CP or an NP search for various applications and download the applications from the CP or the NP.

Specifically illustrates an application list available in a connected server displayed on the display . The application list may include an icon representing each application and a brief description of the application. Because each of the image display devices according to the embodiments of the present disclosure is capable of full browsing it may enlarge the icons or descriptions of applications received from the connected server on the display . Accordingly the user can readily identify applications.

In association with the embodiment of the present disclosure a game application according to the present disclosure may be included in the application list .

The game application included in the application list may include a game application for performing a game play process and providing a display screen to the image display device and a game application for performing a user control function necessary to play a game.

Accordingly a user may select a game application according to the embodiment of the present disclosure from the application list and download the game application to the image display device or the user terminal.

While it is shown in that the user selects a desired item by moving the pointer using the remote controller the application may be selected in many other ways. For example the user may select a specific item using a cursor displayed on the screen by combined input of an OK key and a direction key of a local key not shown or the remote controller .

In another example if the remote controller has a touch pad the pointer moves on the display according to touch input of the touch pad. Thus the user may select a specific item using the touch based pointer .

Specifically illustrates a Web page with a search window displayed on the display. The user may enter a character into the search window by use of character keys not shown of a keypad displayed on a screen character keys not shown of local keys or character keys not shown of the remote controller.

Since the image display devices according to the embodiments of the present disclosure are capable of fully browsing a Web page the user can easily read the Web page.

Specifically illustrates a mail service page including an ID input window and a password input window displayed on the display. The user may enter a specific numeral and or text into the ID input window and the password input window using a keypad not shown displayed on the mail service page character keys not shown of local keys or character keys not shown of the remote controller. Hence the user can log in to a mail service.

The image display devices according to the embodiments of the present disclosure are capable of full browsing when displaying a mail service page.

Although the network TV has been described exemplarily in to for convenience of description the scope of the present disclosure is not limited to the network TV and can be applied to various multimedia devices for example mobile device notebook computers tablet PC DTV and smart TV . Accordingly a multimedia device adopted instead of the network TV will be used to describe the embodiments of the present disclosure with reference to to .

As illustrated in the OS architecture layer according to one embodiment of the present disclosure is divided into a total of five layers. In other words the OS architecture layer includes an application layer an application framework a library layer a hardware abstraction layer HAL and a kernel layer .

First of all the highest layer corresponds to an application program region and a region located below the highest layer is the application framework . The application framework includes processors that control Android through a daemon server type.

Also an activity manager of the application framework takes the role of lifecycle of an application program. A package manager processes information of application programs which is operating in the system. The window manager takes the role of screen processing related to all application programs. A view system processes standard widget and a first home screen may be designed as a widget.

The library region and the HAL mean a part that is developed as a native and can be connected with the application framework . Also a Dalvik virtual machine VM and a core library region are included in the library region . Java applications that cannot control hardware are designed to perform communication with processors inside Android through a path called JNI.

In the mean time the library region includes a surface manager a media framework SQLite OpenGLjES FreeType WebKit SGL SSL Libc etc. Main elements of the library region will be described as follows.

The aforementioned Libc is an element implemented for an embedded environment for example and serves to support lightweight and quick pthread POSIX Threads . Also the aforementioned WebKit is based on an open source WebKit Browser and supports full browsing.

The aforementioned SQLite is an open source project provides a lightweight DB solution and is used by various services inside Android. Also the aforementioned media framework is based on a PocketVideo OpenCore platform and supports standard video audio and still frame format. Moreover the media framework supports H W and S W codec plug in.

The aforementioned surface manager forwards surface rendering of all application programs to a frame buffer whereby 2D and 3D can be displayed by various application programs at the same time and forwards the buffer through Binder IPC call. The surface manager will be described later in more detail with reference to and .

For example the HAL region serves as a link where Android and hardware meet. For example the HAL region includes an audio interface a graphic interface and WiFi. The HAL region further includes standardized APIs. The HAL region has an advantage in that it can add user defined components optionally as the case may be.

A Linux kernel can be used as the kernel region . In more detail the kernel region includes a display a driver a camera driver a Bluetooth driver a shared memory driver a binder driver a USB driver a keypad driver a WiFi driver an audio driver and a power management. In particular the binder driver and the power management will be described later in more detail with reference to and .

As described above the OS platform according to one embodiment of the present disclosure includes the kernel layer the HAL layer the library the application program framework and the application .

Also the application program framework is implemented in Java language for example. A Java native interface JNI mapping different calling conventions between Java and C languages exists between the framework and the library .

The library is a library built in an embedded applications binary interface EABI for example. Also since the library includes a binder and is connected with a code C through JNI of Java a size of C library which is essentially used can be reduced and efficiency can be improved.

Also the surface manager located in the library region forwards surface rendering of all application programs to the frame buffer. Since the frame buffer is different from LCD in CPU speed the same structure is provided in a DRAM or SRAM and all of memory blocks are copied whereby the memory blocks are output to the LCD at one time. At this time the memory space will be referred to as the frame buffer. Although the existing embedded Linux processes 2D and 3D separately this case processes 2D and 3D at the same time. Screen compositing screen combining and an aero glass effect can be processed at one time. Although a single buffer is enough for 2D if it is applied to 3D bottle neck phenomenon may be caused due to large data amount of 3D. For this reason a double frame is used for 3D as the frame buffer. For example the existing buffer size is increased as much as twice in case of 3D. If double buffering is applied to 2D panorama pictures and background picture can be managed separately whereby overhead can be reduced.

Also in case of an application such as games an application drafted in a specific computing language for example Java should be used to display graphic data by using the application framework . However another application for example host dependent application related to time critical and maximum performance and not supported by Java drafted in a native code not the specific computing language should be processed through a separate path whereby graphic data can be displayed quickly. Accordingly a new OS architecture for processing the application in more detail subtitle caption teletext etc. drafted in a native code will be described later in more detail with reference to to .

Since the binder is operated separately the possibility of hacking in communication is lowered and security is improved. It is required to make the binder lightweight if possible to reduce waste of memory.

Also the binder maintains ThreadPool. The binder is attached to both sides of each of the driver and the manager service. The binder is designed so as not to take time in binding whereby resources are previously reserved for direct mapping. If application A and device driver B perform communication a channel is generated. In this case if another application C other than application A connected inside the channel the binder should not be ended even though the application A has been ended.

As illustrated in the OS according to one embodiment of the present disclosure does not end each application application A B C etc. automatically. In other words the OS is designed such that the applications are managed as one by the power management of the kernel region and a specific process is removed by a priority algorithm inside the operating system if memory is sufficient. A further explanation of can be found at http 5963581449325967972 a 1802744773732722657 s sites.googlegroups.com site io anatomy physiology of an android Android Anatomy GoogleIO.pdf attachauth ANoY7crUJxDhdhQOS89sHm6Jc Xb1vj2Q7Qfi Z1p0SithzDOPbUPYRsgROsIXQEJWEyb0XakeGgWIp5Pzci2KgmzeGk9vuXUjbpUufi7qK9q WcaY1V2sk4dfCIf5BCHgpkF idJ0OAqlbos IFCcwZtSpVWijM7s4uTOUnqHnJxnGZetNyzem P8CHb0pAdImwijaRxoSCUUisJo0vB3Zktlj0Br mnDjJIBGbhMPu7n 2gwffnq4tYgbyuAvhc TEGlkyTFkrJy attredirects 0 http www.youtube.com watch v G 36noTCaiA eurl http 3A 2F 2Fsites.google.com 2Fsite 2Fio 2Fanatomy physiology of an android feature player embedded or http sites.google.com site io anatomy physiology of an android.

In other words a surface corresponding to graphic data of a managed application is processed through a first surface composer client a surface flinger HAL a kernel driver and hardware . The may surface mean e.g. an object that displays a memory block composited in a screen. The surface may retain one canvas object for display for example and provides various helper methods for changing a layer and a size of the surface.

An application random application drafted in a native code may correspond to external broadcast data or network data which is pre processed by a native module . The native module will be described later in detail with reference to and .

The graphic data of the application which are pre processed by the native module are displayed on the screen through a second composer client the surface flinger the HAL the kernel driver and the hardware .

As illustrated in the multimedia device provided with an operating system OS capable of processing a plurality of graphic data includes a first client corresponding to of receiving first graphic data of the managed application a native module of pre processing the application drafted in a native code and a second client of receiving second graphic data of the application drafted in a native code pre processed by the native module. Moreover the multimedia device further includes a composite module of compositing the first graphic data output from the first client corresponding to of and the second graphic data output from the second client of and a display module corresponding to of outputting the composited first and second graphic data.

The composite module is designed such that it is accessed to the first client and the second client to perform data communication. Accordingly even though broadcast data or network data are not drafted in Java language the broadcast data or network data can be composited with graphic data of an application drafted in Java language without being redrafted in Java language.

A surface corresponding to graphic data of a managed application may be designed to bypass a native module . The surface corresponding to graphic data of the managed application is processed through a first surface composer client a surface flinger HAL a kernel driver and hardware . An application random application drafted in a native code corresponding to external broadcast data or network data may be pre processed by the native module . The native module will be described later in detail with reference to and .

The graphic data of the application which are pre processed by the native module are displayed on the screen through a second composer client the surface flinger the HAL the kernel driver and the hardware .

The application interface may be controlled by the managed application for example and may control start and end of the native module . The data interface may receive applications and drafted in a native code through broadcasting or network.

The graphic module may process the graphic data of the application received from the data interface into second graphic data that can be output. The engine part parses the data forwarded from the data interface and the graphic part processes graphic data to be output.

The client interface may serve to forward the processed second graphic data to the second surface composer client illustrated in or . As described above the second surface composer client may be referred to as a second client.

A native module according to another embodiment of the present disclosure may include an application interface a data interface an MHEG API an MHEG engine a GL surface interface and a client interface .

The application interface may be controlled e.g. by the managed application and control start and end of the native module . The data interface may receive MHEG applications and drafted in a native code through broadcasting or network.

The MHEG API may process MHEG On Off and remote key control and the MHEG engine may parse MHEG App data by receiving section data through broadcasting or network. The GL surface interface may receive data to be displayed from the engine and then may forward the received data to the client interface . The client interface may be referred to as a surface interface.

Alternatively the MHEG API illustrated in may be replaced with a caption API and the MHEG engine may be replaced with a caption engine. If the MHEG API and the MHEG engine are designed as above it may be advantageous in that a native application provided by another broadcast environment can be processed simultaneously with the managed application.

Surfaces and constituting graphic data of a managed application are directly forwarded to a surface flinger . On the other hand a surface constituting graphic data of an application which is drafted in a native code not the managed application is pre processed by the native module described above and then forwarded to the surface flinger . The surface flinger collects various surface data to update a frame buffer thereby outputting composited graphic data. This will be described in more detail with reference to .

On the other hand a surface constituting graphic data of an application which is drafted in a native code not a managed application is pre processed by the native module described above and then forwarded to the surface flinger . As illustrated in the surface constituting graphic data of the application drafted in a native code language may correspond to teletext data received through broadcasting or network. The surface flinger collects the aforementioned surface data to output a finally composited screen .

In the mean time it is to be understood that the application drafted in a native code is not limited to the example of or . For example the application drafted in a native code may correspond to an application related to at least one or more of teletext subtitle or caption.

Moreover there is no limitation in the OS illustrated in and . The Android OS based layer may be designed through modifications illustrated in to .

A multimedia device provided with an OS capable of processing a plurality of graphic data receives first graphic data of a managed application from a first client S . In the mean time the multimedia device pre processes an application drafted in a native code S and receives second graphic data of the pre processed application drafted in a native code from a second client S . The step S will be described later in more detail with reference to .

The multimedia device is designed to composite the first graphic data output from the first client and the second graphic data output from the second client S .

The multimedia device displays the first graphic data of the composited data in a first region inside a screen S and displays the second graphic data of the composited data in a second region inside the screen S . The multimedia device may be designed such that the steps S and S may be performed in due order or at the same time.

According to the aforementioned embodiments graphic data of the application that requires time critical maximum performance etc. can be displayed through the native module the surface composer client etc.

Also according to the aforementioned embodiments as the native module is defined in detail it is advantageous in that porting scalability and easiness of the application drafted in the existing native code can be improved.

Moreover according to the aforementioned embodiments the graphic data of the applications not drafted in a specific computing language for example Java language can be processed without redrafting in the specific computing language.

As illustrated in a multimedia device according to one embodiment of the present disclosure is provided with an OS described above.

First of all it is assumed that the multimedia device outputs a normal broadcast screen . The normal broadcast screen may be replaced with a home screen or an AV output screen from an external device.

If a command that executes a first application using a user interface of the multimedia device is received first graphic data corresponding to the first application are displayed.

If a command that executes a second application using the user interface of the multimedia device is received second graphic data corresponding to the second application are displayed. At this time as illustrated in the first graphic data of a managed application and the second graphic data based on an application drafted in native code are overlaid. As described above since an OS according to one embodiment of the present disclosure is designed to pre process the application drafted in a native code graphic data corresponding to a plurality of different kinds of applications can be overlaid.

Moreover although the screen where graphic data of the application that has received a command most recently based on time are displayed most definitely or in the uppermost layer is illustrated in the scope of the present disclosure is not limited to the example of .

As illustrated in a multimedia device according to another embodiment of the present disclosure is provided with an OS described above. The OS can be understood with reference to to . Also a main screen illustrated in corresponds e.g. to a normal broadcast screen.

The graphic data of the applications are overlaid based on time reference of each command in whereas the graphic data are overlaid in in accordance with a priority previously set by a user or a priority set as default regardless of the time reference.

For example it is assumed that the user sets an application related to channel additional information to have a priority over a caption application of course automatic setting of the priority regardless of user setting pertains to the scope of the present disclosure . Accordingly after a command to execute a managed application related to channel additional information is received even though a command to execute the caption application is received data are displayed in such a manner that first graphic data corresponding to the managed application related to channel additional information having the priority is overlaid on second graphic data corresponding to the caption application drafted in a native language.

According to the related art a problem occurs in that two different applications if one is a managed application the other one is an application drafted in a native code cannot be output in an overlaid type. However according to the embodiments of the present disclosure the problem of the related art can be solved. Moreover as illustrated in to since a module for pre processing native applications is designed as one chip it is advantageous in that a plurality of chips are not required to process each application.

As illustrated in a multimedia device according to another embodiment of the present disclosure is provided with an OS described above. The OS can be understood with reference to to . A main screen illustrated in corresponds to a normal broadcast screen for example. Moreover unlike and it is assumed in that graphic data of three applications are processed at the same time.

In more detail it is assumed that the multimedia device sequentially receives commands for executing a first application and a second application while outputting a normal broadcast screen. Also if a command to execute a third application for example main menu is received as illustrated in first graphic data corresponding to the first application and second graphic data corresponding to the second application are designed to have relatively lower definition than that of third graphic data .

At this time the first graphic data and the second graphic data are changed to an inactive state that cannot be selected by the user and the third graphic data is maintained in an active state that can be selected by the user. As described above the third application corresponding to the third graphic data has the highest priority or corresponds to the application selected most recently by the user. In this example first graphic data may be from a managed application and the second graphic data may be from an application written in native code. The third graphic data may be from a managed application or an application written in native code.

According to the related art a problem occurs in that graphic data corresponding to different applications can be neither overlaid at the same time nor processed more quickly.

In order to configure a 3D screen having two or more regions a position of a layer corresponding to each region should be designated. For example it is required that a layer position of the first application caption application and a layer position of the second application application related to channel additional information should be designated.

Accordingly before graphic data of an application drafted in a native code are forwarded to the client interface the 3D data processing part illustrated in FIG. temporarily sets a layer where the graphic data of the application drafted in a native code should be located.

If one embodiment of the present disclosure is applied to a 3DTV the OS of the multimedia device illustrated in is designed as illustrated in . As compared with a 3D rendering part is additionally provided in . Accordingly the description of the other modules can be understood with reference to . However a native module illustrated in corresponds to that of .

Accordingly the 3D rendering part illustrated in is designed to render 2D graphic into 3D graphic based on the layer temporarily set by the 3D data processing part of the native module.

If the multimedia device is designed as illustrated in and it is advantageous in that the applications drafted in different codes can be displayed in their respective layer in a 3D type.

Moreover although the drawings are illustrated respectively for convenience of description the embodiments illustrated in the drawings may be incorporated to achieve a new embodiment. A recording medium that can be read from a computer having a program for implementing the aforementioned embodiments may be designed within the scope of the present disclosure.

The multimedia device and the operation method thereof according to the present disclosure may be configured by selective combination of all or some of the aforementioned embodiments without limited application of the embodiments whereby various modifications can be made in the embodiments.

In the mean time the operation method for the multimedia device according to the present disclosure can be implemented in a recording medium which can be read by a processor provided in the multimedia device as a code that can be read by the processor. The recording medium that can be read by the processor includes all kinds of recording media in which data that can be read by the processor are stored.

Examples of the recording medium include ROM RAM CD ROM magnetic tape floppy disk and optical data memory. Also another example of the recording medium may be implemented in a type of carrier wave such as transmission through Internet. Also the recording medium that can be read by the processor may be distributed in a computer system connected to a network whereby codes that can be read by the processor can be stored and implemented in a distributive mode.

Accordingly the present disclosure is directed to a multimedia device having an operating system capable of processing multiple graphic data and a method for controlling the same which substantially obviate ones or more problems due to limitations and disadvantages of the related art.

An object of the present disclosure is to provide an operating system that can simultaneously process graphic data of a managed application and graphic data of an application drafted in a native code.

Another object of the present disclosure is to provide a solution for more exactly and quickly processing graphic data of an application for example subtitle teletext caption etc. that requires time critical maximum performance etc.

Other object of the present disclosure is to provide an operating system that can reuse an application drafted in a native code without changing it in a specific computing language.

Additional advantages objects and features of the disclosure will be set forth in part in the description which follows and in part will become apparent to those having ordinary skill in the art upon examination of the following or may be learned from practice of the disclosure. The objectives and other advantages of the disclosure may be realized and attained by the structure particularly pointed out in the written description and claims hereof as well as the appended drawings.

To achieve these objects and other advantages and in accordance with the purpose of the disclosure as embodied and broadly described herein a multimedia device provided with an operating system OS capable of processing a plurality of graphic data comprises a first client receiving first graphic data of a managed application a native module pre processing an application drafted in a native code a second client receiving second graphic data of the application pre processed by the native module a composite module compositing the first graphic data output from the first client and the second graphic data output from the second client and a display module outputting the composited first and second graphic data wherein the composite module is accessed to the first client and the second client.

In another aspect of the present disclosure a method for controlling a multimedia device provided with an operating system OS capable of processing a plurality of graphic data comprises the steps of receiving first graphic data of a managed application from a first client pre processing an application drafted in a native code receiving second graphic data of the application pre processed by the native module from a second client compositing the first graphic data output from the first client and the second graphic data output from the second client displaying the first graphic data of the composited data in a first region inside a screen of the multimedia device and displaying the second graphic data of the composited data in a second region inside the screen of the multimedia device.

According to one embodiment of the present disclosure there is provided an operating system that can simultaneously process graphic data of a managed application and graphic data of an application drafted in a native code.

Also according to another embodiment of the present disclosure there is provided a solution for more exactly and quickly processing graphic data of an application for example subtitle teletext caption etc. that requires time critical maximum performance etc.

Moreover according to other embodiment of the present disclosure there is provided an operating system that can reuse an application drafted in a native code without changing it in a specific computing language.

It is to be understood that both the foregoing general description and the following detailed description of the present disclosure are exemplary and explanatory and are intended to provide further explanation of the disclosure as claimed.

Any reference in this specification to one embodiment an embodiment example embodiment etc. means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the disclosure. The appearances of such phrases in various places in the specification are not necessarily all referring to the same embodiment. Further when a particular feature structure or characteristic is described in connection with any embodiment it is submitted that it is within the purview of one skilled in the art to effect such feature structure or characteristic in connection with other ones of the embodiments.

Although embodiments have been described with reference to a number of illustrative embodiments thereof it should be understood that numerous other modifications and embodiments can be devised by those skilled in the art that will fall within the spirit and scope of the principles of this disclosure. More particularly various variations and modifications are possible in the component parts and or arrangements of the subject combination arrangement within the scope of the disclosure the drawings and the appended claims. In addition to variations and modifications in the component parts and or arrangements alternative uses will also be apparent to those skilled in the art.

