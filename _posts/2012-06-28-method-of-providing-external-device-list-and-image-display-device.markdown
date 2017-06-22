---

title: Method of providing external device list and image display device
abstract: Provided are a method of providing an external device list and an image display device. The method includes: displaying a plurality of external device icons connectible to the image display device; positioning a pointer on a first external device icon among the plurality of external device icons; and displaying on a screen of the image display device an image signal of an external device corresponding to the first external device icon having the pointer thereon.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09532102&OS=09532102&RS=09532102
owner: LG ELECTRONICS INC.
number: 09532102
owner_city: Seoul
owner_country: KR
publication_date: 20120628
---
The present application claims priority under 35 U.S.C. 119 and 35 U.S.C. 365 to Korean Patent Application No. 10 2011 0088863 filed on Sep. 2 2011 which is hereby incorporated by reference in its entirety.

The present invention relates to an image display device and more particularly to a method for providing a list of external devices thereof.

Recently digital TV services using a wire or wireless communication network are becoming more common. The digital TV services provide various services that typical analog broadcasting services cannot provide.

For example an Internet Protocol Television IPTV service i.e. one type of the digital TV services provides interaction through which a user may actively select kinds of watching programs and watching time. The IPTV service may provide various additional services such as internet search home shopping and online game on the basis of the interaction.

Embodiments provide a method of providing an external device list which allows a user to recognize an input switch in advance before an image signal of an external device which is applied to an image display device is switched for input and an image display device thereof.

In one embodiment a method of providing an external device list to an image display device includes displaying a plurality of external device icons connectible to the image display device positioning a pointer on a first external device icon among the plurality of external device icons and displaying on a screen of the image display device an image signal of an external device corresponding to the first external device icon having the pointer thereon.

In another embodiment an image display device includes a display unit displaying a plurality of external device icons connectible to the image display device and a control unit performing a control to display an image signal of an external device corresponding to a first external device icon having a pointer thereon when the pointer is positioned on the first external device icon among the plurality of external device icons.

The details of one or more embodiments are set forth in the accompanying drawings and the description below. Other features will be apparent from the description and drawings and from the claims.

Hereinafter a method for providing an external device list and an image display device thereof will be described in more detail with reference to the accompanying drawings.

The image display device as an intelligent image display device having a computer supporting function in addition to a broadcasting receiving function further includes an internet function besides a solid broadcasting receiving function so that it may have an easy to use interface such as a handwriting input device a touch screen or a space remote controller. Moreover after accessing internet and a computer with a wire or wireless internet supporting function a function for e mail web browsing banking or game may be available. For such various functions a standardized general OS may be used.

Accordingly the image display device according to an embodiment may perform user friendly various functions because a variety of applications may be freely added or deleted on a general OS kernel. The image display device may be a network TV HBBTV and a smart TV for a specific example and may be applied to a smart phone if necessary.

Furthermore although embodiments of the present invention will be described with reference to the accompanying drawings and contents therein the present invention is not limited thereto.

The terms used in this specification are selected from currently widely used general terms in consideration of functions of the present invention but may vary according to the intentions or practices of those skilled in the art or the advent of new technology. Additionally in certain cases there may be terms that an applicant may arbitrarily select and in this case their meanings are described below. Accordingly the terms used in this specification should be interpreted on the basis of substantial implications that the terms have and the contents across this specification not the simple names of the terms

Referring to the broadcasting system includes a Content Provider CP a Service Provider SP a Network Provider NP and a Home Network End User HNED .

The HNED may correspond to a client i.e. the image display device according to an embodiment and for example the client may be a network TV a smart TV and an IPTV.

Moreover the CP manufactures and provides various contents. As shown in the CP may be a terrestrial broadcaster a cable System Operator SO a Multiple System Operator MSO a satellite broadcaster or an Internet broadcaster.

Additionally the CP may provide various applications besides the broadcast contents. This will be described in more detail later.

The SP may package contents that the CP provides and provides the packaged contents as services. For example the SP may package first terrestrial broadcast second terrestrial broadcast cable MSO satellite broadcast various internet broadcasts and applications and then provide them to a user.

The unicast method is a 1 1 data transmission method between one transmitter and one receiver. For example in the case of the unicast method when a receiver requests data to a server the server transmits the requested data to the receiver in response to the request.

The multicast method is to transmit data to a plurality of receivers in a specific group. For example a server may transmit data to a plurality of pre registered receivers simultaneously. In order for such a multicast registration an Internet Group Management Protocol IGMP may be used.

The NP may provide a network to provide the service to the client and the client may establish a Home Network End User HNED to receive the service.

Conditional Access or Content Protection may be used as a means to protect contents transmitted from the system. As examples of the Conditional Access or Content Protection methods such as CableCARD and Downloadable Conditional Access System DCAS may be used.

Moreover it is possible for the client to provide contents via a network. In this case the client may become a CP and the CP may receive contents from the client . Accordingly a bidirectional contents service or data service may be available.

According to an embodiment the CP may provide a network service such as a Social Network Site SNS a blog a micro blog or an instant messenger.

For example the CP providing the SNS service may include a server not shown storing various kinds of contents such as texts or uploaded images that a plurality of users create in the SNS.

In more detail a user accesses the server of the CP providing the SNS service by using an image display device and designates accounts that the user wants so that the user may confirm messages created by the plurality of the designated accounts.

Additionally if a user requests the SNS service an image display device i.e. the client accesses the server of the CP in order to receive the messages of the designated accounts and then displays the received messages sequentially in order of a corresponding message created for example displays them in a top to bottom direction.

Referring to the image display device corresponding to the client of may be connected to a broadcasting network and internet network.

For example the image display device may include a broadcast interface a section filter an AIT filter an application data processor a broadcast data processor a media player an internet protocol processor an internet interface and a runtime module .

Moreover the broadcast interface of the image display device may receive Application Information Table AIT data real time broadcast content application data or a stream event. The real time broadcast content may be Linear A V Content.

The section filter performs section filtering on four data received through the broadcast interface in order to transmit AIT data into the AIT filter linear A V content into the broadcast data processor and stream event and application data into the application data processor .

The internet interface may receive Non Linear A V content and application data. For example the Non Linear A V content may be Content On Demand COD application.

Furthermore the Non Linear A V content may be transmitted to the media player and the application data may be transmitted to the runtime module .

Additionally the runtime module may include an application manager and a browser. The application manager may control a life cycle on interactive application by using AIT data and the browser may display and process the interactive application

Referring to the SP performs a service provider discovery operation in operation S. The image display device transmits a SP Attachment Request signal in operation S. Once the SP attachment is completed the image display device receives provisioning information in operation S. Furthermore the image display device receives a master SI table from the SP in operation S a Virtual Channel Map table in operation S a Virtual Channel Description table in operation S and a Source table in operation S.

For example the service provider discovery operation may refer to a process that SPs providing IPTV related services search for a server that provides information on the services that the SPs provide.

A method of searching for an address list that helps receiving information on a Service Discovery SD server for example SP discovery information may be the following three methods. First an address preset in an image display device or an address manually set by a user may be used. Second a DHCP based SP discovery method may be used. Third a DNS SRV based SP discovery method may be used.

Moreover the image display device accesses a server having an address obtained by one of the three methods in order to receive a service provider discovery record that contains information necessary for service discovery for each SP and performs a service search operation by using the received service provider discovery record. Moreover the above processes may be available in a push mode or a pull mode.

Furthermore the image display device accesses a SP attachment server designated as a SP attachment locator of a SP discovery record and performs a registration procedure or a service attachment procedure .

Moreover the image display device accesses an authentication service server of the SP designated as the SP authentication locator to perform an additional authentication procedure and then performs a service authentication procedure.

After the service attachment procedure is successful data transmitted from the server to the image display device may have a form of a provisioning information table.

During the service attachment operation the image display device includes its ID and position information in data that are transmitted to the server and a service attachment server may specify a service that the image display device subscribes on the basis of the data.

Address information used for obtaining Service Information that the image display device wants to receive may be provided in a form of the provisioning information table. In addition the address information may correspond to access information on the master SI table. In this case providing a customized service for each subscriber may be easy.

Moreover the Service Information may include a master SI table record for managing access information on a virtual channel map and its version a virtual channel map table for providing a service list in a package form a virtual channel description table including detailed information of each channel and a source table including access information for accessing an actual service.

Referring to the image display device includes an Network Interface a TCP IP Manager a Service Delivery Manager a Demux a PSI PSIP and or SI decoder an Audio Decoder a Video Decoder a Display A V and OSD Module a Service Control Manager a Service Discovery Manager a Metadata Manager an SI Metadata DB a UI manager and a service manager .

The network interface receives or transmits packets from or to a network. That is the network interface unit may receive services and contents from a SP via a network.

The TCP IP manager may be involved in delivering packets from a source to a destination which are received and transmitted by the image display device . Moreover the TCP IP manager classifies the received packets in order correspond to a proper protocol and outputs the classified packets into the service delivery manager the service discovery manager the service control manager and the metadata manager .

Additionally the service delivery manager is responsible for controlling the received service data. For example when the service delivery manager controls real time streaming data RTP RTCP may be used.

When the real time streaming data are transmitted using the RTP the service delivery manager parses the received data packet according to the RTP and transmits the parsed data to the Demux or stores the received data packet in the SI Metadata DB . Moreover the service delivery manager may feed back the network reception information to a server that provides services by using the RTCP.

The Demux demultiplexes the received packet into audio video and Program Specific Information PSI data in order to transmit them into the audio video decoders and and the PSI PSIP and or SI Decoder .

The PSI PSIP and or SI Decoder may decode service information such as PSI and for example may receive a PSI section a Program and Service Information Protocol PSIP section or a Service Information SI section demultiplexed in the Demux in order to decode them.

Moreover the PSI PSIP and or SI Decoder may decode the received sections to create a database for service information and the service information may be stored in the SI Metadata DB .

The audio video decoders and may decode vide data and audio data received from the Demux and the decoded audio and video data may be provided to a user through the Display A V and OSD Module .

Moreover the UI manager and the service manager may manage an overall status of the image display device provide a user interface and mange another manager.

For example the UI manager provides a Graphic User Interface GUI for a user through an On Screen Display OSD and receives a key input from a user in order to perform an operation of a receiver according to the key input. Moreover when receiving a key input signal for a channel selection from a user the UI manager may transmit the key input signal to the service manager .

The service manager may control a service related manager such as the service delivery manager the service discovery manager the service control manager and the metadata manager .

Additionally the service manager creates a channel map and selects a channel by using the channel map according to a key input received from the UI manager .

And the service manager receives service information on a channel from the PSI PSIP and or SI Decoder and sets audio video Packet Identifier PID of the selected channel in the Demux .

The service discovery manager provides information necessary for selecting s SP that provides service. For example on receiving a signal on channel selection from the service manager the service discovery manager may find a service by using the received signal.

Moreover the service control manager is responsible for service selection and control. For example when a user selects a Live Broadcasting service like a typical broadcasting method IGMP or RTSP is used. When a service such as Video On Demand VOD is selected RTSP is used for service selection and control.

The RTSP protocol provides a trick mode with respect to real time streaming. The service control manager may initialize and manage a section passing through an IMC gateway by using an IP Multimedia Subsystem IMS and a Session Initiation Protocol SIP .

The metadata manager manages service related metadata and stores the metadata in the SI Metadata DB .

And the SI Metadata DB may store the service information decoded by the PSI PSIP and or SI Decoder the metadata that the metadata manager manages and the information necessary for selecting a SP that the service discovery manager provides.

Furthermore the SI Metadata DB may store setup data on a system and for example may be implemented using NonVolatile RAM NVRAM or flash memory.

Additionally an IG may be a gateway including functions necessary for accessing an IMS based IPTV service.

Referring to the image display device may include a broadcast receiving unit an external device interface unit a storage unit a user input interface unit a control unit a display unit an audio output unit and a power supply unit . Moreover the broadcast receiving unit may include a tuner a demodulation unit and a network interface unit .

The tuner may select a channel selected by a user among Radio Frequency RF broadcast signals received through an antenna or an RF broadcast signal corresponding to all pre stored channels and may convert the selected RF broadcast signal into an intermediate frequency signal or a baseband image or sound signal.

For example the tuner converts the selected RF broadcast signal into a digital IF signal DIF if it is a digital broadcast signal or into an analog baseband image or sound signal CVBS SIF if it is an analog broadcast signal.

That is the tuner may process both a digital broadcast signal and an analog broadcast signal and the analog baseband image or sound signal CVBS SIF outputted from the tuner may be directly inputted to the control unit .

Moreover the tuner may receive an RF broadcast signal of a single carrier according to the Advanced Television System Committee ATSC format or an RF broadcast signal of a plurality of carriers according to the Digital Video Broadcasting DVB format.

Furthermore the tuner may sequentially select RF broadcast signals of all broadcast channels stored through a channel memory function from RF broadcast signals received through an antenna and then may convert the selected RF broadcast signals into an intermediate frequency signal or a baseband image or sound signal.

The demodulation unit may receive the digital IF signal DIF converted by the tuner and then may perform a demodulation operation thereon. For example if the digital IF signal outputted from the tuner is the ATSC format the demodulator may perform an 8 Vestigal Side Band 8 VSB demodulation.

Additionally the demodulation unit may perform channel decoding and for this may include a Trellis Decoder a De interleaver and a Reed Solomon Decoder to perform Trellis decoding de interleaving and Reed Solomon decoding.

For example if the digital IF signal outputted from the tuner is the DVB format the demodulation unit may perform Coded Orthogonal Frequency Division Modulation COFDMA modulation.

Additionally the demodulation unit may perform channel decoding and for this may include a convolution decoder a De interleaver and a Reed Solomon Decoder to perform convolutional decoding de interleaving and Reed Solomon decoding.

The demodulation unit may output a stream signal TS after performing demodulation and channel decoding and the stream signal may be a signal into which an image signal sound signal or a data signal is multiplexed.

For example the stream signal may be an MPEG 2 Transport Stream TS into which an MPEG 2 standard image signal and a Dolby AC 3 standard sound signal are multiplexed. In more detail the MPEG 2 TS may include a 4 byte header and a 184 byte payload.

Furthermore the demodulation unit may include an ATSC demodulation unit and a DVB demodulation unit separately according to the ATSC format and the DVB format.

The stream signal outputted from the demodulation unit may be inputted to the control unit . The control unit may output an image to the display unit and a sound to the audio output unit after demultiplexing and processing an image sound signal.

The external device interface unit may connect an external device with the image display device and for this may include an A V input output unit not shown or a wireless communication unit not shown .

The external device interface unit may be used for wire wireless connection of an external device such as a Digital Versatile Disk DVD player a Bluray player a game console a camera a camcorder and a computer such as a notebook computer .

Moreover the external device interface unit may deliver an image sound or data signal inputted from a connected external into the control unit of the image display device and may output the image sound or data signal processed in the control unit into the connected external device.

The A V input output unit may include a USB terminal a Composite Video Banking Sync CVBS terminal a component terminal an S video terminal i.e. an analog type a Digital Visual Interface DVI terminal a High Definition Multimedia Interface HDMI terminal an RGB terminal and a D SUB terminal in order to input an image and sound signal of an external device into the image display device .

Furthermore the wireless communication unit may perform a short range wireless communication with another electronic device. For example the image display device and another electronic device may be connected to a network through communication standards such as Bluetooth Radio Frequency Identification RFID infrared Data Association IrDA Ultra Wideband UWB ZigBee and Digital Living Network Alliance DLNA .

Moreover the external device interface unit is connected to various set top boxes through at least one of the above various terminals in order to perform an input output operation of a set top box.

In addition the external device interface unit may receive applications or lists of applications in an adjacent external device and then may deliver them to the control unit or the storage unit .

The network interface unit may provide an interface for connecting the image display device to a wire wireless network including an internet network. For example the network interface unit may include an Ethernet terminal for accessing a wired network or may be connected to a wireless network through a communication standard such as Wireless LAN WLAN such as Wi Fi Wireless broadband Wibro World Interoperability for Microwave Access Wimax and High Speed Downlink Packet Access HSDPA .

Moreover the network interface unit may transmit receive data to from another user or another electronic device via a connected network or another network linked to the connected network.

Additionally the network interface unit may transmit some contents data stored in the image display device to a selected user or electronic device among users or other electronic devices pre registered in the image display device .

The network interface unit may access a predetermined web page via a connected network or another network linked to the connected network. That is the network interface unit may access a predetermined web page via a network to transmit receive data to from a corresponding sever.

Then the network interface unit may receive contents or data provided from a CP or a network operator. That is the network interface unit may receive contents such as movies advertisings games VODs and broadcast signals and information thereon which are provided from a CP or an NP via a network.

Additionally the network interface unit may receive update information and update files of a firmware provided from a CP or a network operator and may transmit data to an internet provider a CP or a network operator.

The network interface unit may select and receive a wanted application from applications open to air via a network.

The storage unit may store a program for processing and controlling each signal in the control unit and may store the processed image sound or data signals.

Moreover the storage unit may perform a function for temporarily storing image sound or data signals inputted from the external device interface unit or the network interface unit and may store information on a predetermined broadcast channel through a channel memory function.

The storage unit may store applications or lists of applications inputted from the external device interface unit or the network interface unit .

The storage unit may include a storage medium having at least one type of a flash memory type a hard disk type a multimedia card micro type a card memory type for example SD or XD memory a RAM type and an EEPROM type.

The image display device may play contents files stored in the storage unit such as movie files still image files music files document files and application files and may provide them to a user.

The user input interface unit may deliver a signal that a user inputs to the control unit or may deliver a signal from the control unit to a user. For example the user input interface unit may receive a control signal such as power on off channel selection and screen setting from a remote control device and may process the received control signal according to various communication methods such as an RF communication method or an IR communication method. Or the user input interface unit may transmit a control signal from the control unit to the remote control device .

Additionally the user input interface unit may deliver to the control unit a control signal inputted from a local key not shown such as a power key a channel key a volume key and a setting key.

For example the user input interface unit may deliver to the control unit a control signal inputted from a sensing unit not shown that senses a gesture of a user and may transmit a signal from the control unit to a sensing unit not shown . Moreover the sensing unit not shown may include a touch sensor a sound sensor a position sensor and a motion sensor.

The control unit may demultiplex a stream inputted from the tuner the demodulation unit or the external device interface unit or may process demultiplexed signals in order to generate and output a signal for image or sound output.

The image signal processed in the control unit is inputted to the display unit and then is displayed as an image corresponding to a corresponding image signal. Additionally the image signal processed in the control unit is inputted to an external output device through the external device interface unit

The sound signal processed in the control unit may be outputted to the audio output unit as audio. Moreover the sound signal processed in the control unit is inputted to an external output device through the external device interface unit .

Although not shown in the control unit may include a demultiplexing unit and an image processing unit. This will be described below with reference to .

Besides that the control unit may control overall operations of the image display device . For example the control unit controls the turner to tune an RF broadcast corresponding to a channel that a user selects or a pre stored channel.

Additionally the control unit may control the image display device through a user command inputted through the user input interface unit or an internal program and may access a network to download applications that a user wants or lists of applications into the image display device .

For example the control unit controls the tuner to receive a signal of a selected channel according to a predetermined channel selection command received through the user input interface unit and may process an image sound or data signal of the selected channel.

The control unit may output channel information that a user selects in addition to a processed image or sound signal through the display unit or the audio output unit .

Moreover the control unit may output an image or sound signal of an external device such as a camera or a camcorder which is inputted through the external device interface unit through the display unit or the audio output unit according to an external device image play command received through the user input interface unit .

Furthermore the control unit may control the display unit to display an image and for example the control unit may control the display unit to display a broadcast image inputted through the tuner an external input image inputted through the external device interface unit an image inputted through a network interface unit or an image stored in the storage unit . In this case an image displayed on the display unit may be a still or moving image or a 2D or 3D image.

Additionally the control unit may play contents stored in the image display device received broadcast contents or external input contents inputted from an external. The contents may have various formats such as a broadcast image an external input image an audio file a sill image an accessed web page and a document file.

Moreover although not shown in the image display device may further include a channel browsing processing unit for generating a thumbnail image corresponding to a channel signal or an external input signal.

The channel browsing processing unit receives a stream signal TS outputted from the demodulation unit or a stream signal outputted from the external device interface unit and extracts an image from the inputted stream signal to generate a thumbnail image.

The generated thumbnail image may be inputted to the control unit as it is or after being encoded or may be inputted to the control unit after being encoded into a stream format.

The control unit may display a thumbnail list including a plurality of thumbnail images on the display unit by using the inputted thumbnail image. The plurality of thumbnail images in the thumbnail list may be sequentially or simultaneously updated. Accordingly a user may simply recognize contents of a plurality of broadcast channels.

The display unit converts an image signal a data signal and an OSD signal processed in the control unit or an image signal and a data signal received in the external device interface unit into R G and B signals in order to generate a driving signal.

For this the display unit may include a PDP an LCD an OLED a flexible display and a 3D display or may include a touch screen used as an input device in addition to an output device.

The audio output unit receives a signal sound processed in the control unit for example a stereo signal a 3.1 channel signal or a 5.1 channel signal and then outputs the signal as sound. For this various types of speakers may be used.

Moreover the image display device may further include a capturing unit not shown for capturing an image of a user and image information obtained by the capturing unit not shown may be inputted to the control unit .

In this case the control unit may detect a user s gesture by combining an image captured through the capturing unit not shown and a signal detected through a sensing unit not shown or using it separately.

The power supply unit supplies corresponding power to the image display device generally. For example the power supply unit may supply power to the control unit the display unit and the audio output unit which may be realized in a form of a System On Chip SOC .

For this the power supply unit may include a converter not shown for converting AC power into DC power. If the display unit is implemented using a liquid crystal panel including a plurality of backlight lamps the power supply unit may further include an inverter not shown for PWM operation in order to provide brightness adjustment and dimming driving.

The remote control device transmits a user input to the user input interface unit . For this the remote control device may use Bluetooth Radio Frequency RF communication IR communication Ultra Wideband UWB or ZigBee.

Additionally the remote control device receives an image sound or data signal outputted from the user input interface unit and then displays the received signal or outputs sound or vibration.

The image display device may be a fixed digital broadcast receiver that receives at least one of an ATSC type 8 VSB type digital broadcast a DVB T type COFDM type digital broadcast and an ISDB T type BST OFDM type digital broadcast.

Moreover since the image display device of is just one embodiment of the present invention some components shown herein may be integrated added or omitted according to the specification of the actually realized image display device .

That is more than two components may be integrated into one component or one component may be divided into more than two components if necessary. Furthermore a function in each block is used for describing an embodiment of the present invention and its specific operation or device does not limit the scope of the present invention.

According to another embodiment of the present invention unlike the image display device may receive an image through the network interface unit or the external device interface unit and may play the received image without the tuner and the demodulation unit

For example the image display device may include an image processing device such as a set top box for receiving broadcast signals or contents according to various network services and a contents playing device for playing contents inputted from the image processing device.

In this case a method of providing an external device list according to an embodiment may be performed by the above separated image processing device such as a set top box or the above separate contents playing device including the display unit and the audio output unit in addition to the image display device described with reference to .

Referring to the platform of the image display device as a separate platform includes a Legacy System platform and a smart system platform which are separately designed.

An OS kernel may be commonly used in the Legacy System platform and the smart system platform . The Legacy System platform may include a driver a Middleware and an Application on the OS kernel .

Moreover the smart system platform may include a Library a Framework and an application on the OS kernel .

The OS kernel as a core of an operating system may provide hardware driver driving when the image display device is driven the security of hardware and a processor in the image display device efficient management of a system resource memory management an interface for hardware by hardware abstraction a multi processor schedule management according to a multi processor and power management.

For example a hardware driver in the OS kernel may include at least one of a display driver a Wi Fi driver a Bluetooth driver a USB driver an audio driver a power management driver a binder driver and a memory driver.

Moreover the hardware driver in the OS kernel as a driver for a hardware device in the OS kernel may include a character device driver a block device driver and a network device driver.

Furthermore the block device driver may include a buffer for storing a unit size as data are transmitted by a specific block unit and the character device driver may not include the buffer as data are transmitted by a basic data unit i.e. a character unit.

The OS kernel may be implemented with various OS based kernels such as Unix base Linux kernel and Window base kernel and may be available for other electronic devices as an open OS.

The driver is disposed between the OS kernel and the middleware and drives a device in order for operations of the middleware and the application .

For example the driver may include drivers for a micom a display module a Graphic Processing Unit GPU a Frame Rate Converter FRC a General Purpose Input Output Pin GPIO an HDMI a System Decoder or demultiplexer SDEC a Video Decoder VDEC an Audio Decoder ADEC a Personal Video Recorder PVR an Inter Integrated Circuit I2C in the image display device . The above drivers may operate in linkage with a hardware driver in the OS kernel .

Additionally the driver may further include a driver for a remote control device for example a space remote controller. The driver for a space remote controller may be included in the OS kernel or the middleware in addition to the driver .

The middleware is disposed between the OS kernel and the application and serves as a medium to exchange data between other hardware or software. Accordingly the standardized interface may be available and various environmental supports and interworking with other tasks having different systems may also be available.

For example the middleware in the legacy system platform may include a Multimedia and Hypermedia information coding Experts Group MHEG middleware and an Advanced Common Application Platform ACAP middleware and may further include a PSIP or SI middleware i.e. a broadcast information related middleware and a DLNA middleware i.e. a peripheral communication related middleware .

Additionally the application on the middleware i.e. the application in the legacy system platform may include a User Interface Application for various menus in the image display device .

The application on the middleware may be edited by a user s choice and may be updated via a network. Through the application it is possible to enter a wanted menu in various user interfaces according to an input of a remote control device while watching a broadcast image.

Moreover the application in the legacy system platform may further include at least one of a TV guide application a Bluetooth application a reservation application a Digital Video Recorder DVR application and a hotkey application.

Moreover the library in the smart system platform is disposed between the OS kernel and the framework and forms a base of the Framework . For example the library may include a Secure Socket Layer SSL i.e. a security related library a WebKit i.e. a web engine related library a libc i.e. a c library and a Media Framework i.e. a media related library such as video formats and audio formats. The library may be programmed with C or C so that it may be exposed to developer through the framework .

The library may include the runtime having a core java library and a Virtual Machine VM . The runtime may form a basic of the framework in addition to the library .

The VM may perform a plurality of instances i.e. multitasking. Furthermore according to each application in the application each VM may be allocated and executed. In this case a Binder driver not shown in the OS kernel may operate for schedule adjustment or interconnect between plurality of instances.

In addition the binder driver and the runtime may connect a java based application with a C based library. The library and the runtime may correspond to the middleware of the legacy system.

Moreover the framework in the smart system platform includes a program which is a base of an application in the application . The framework is compatible with any application. Its component may be reused moved or replaced.

The framework may include a support program i.e. a program for binding components of other software. For example the framework may include a resource manager an activity manager related to the activity of application a notification manager and a content provider for summarizing sharing information between applications.

The application on the framework includes various programs that are driven in the image display device to be displayed. For example the application may include a Core Application that has at least one of email short message service SMS calendar map and browser.

In addition the application may be divided into an application stored in the image display device and cannot be deleted by a user and an application downloaded via a network and stored and freely installed or deleted by a user.

Through applications in the application internet phone service Video On Demand VOD service web album service Social Networking Service SNS Location Based Service LBS map service web search service and application search service may be provided. Additionally various functions such as games and scheduling may be performed.

Moreover as shown in the platform of the image display device as an integrated platform may include an OS kernel a driver a Middleware a Framework and an Application .

When compared to there are differences that the library is omitted and the application is an integrated layer in the platform shown in . Besides that the driver and the framework are the same as those in .

The platforms shown in may be generally available for various electronic devices in addition to the image display device and may be stored in or loaded into the storage unit or control unit of or an additional processor not shown .

Moreover the platform may be stored in or installed into the SI metadata DB UI manager and service manager of and may further include an additional application processor not shown to execute the application.

Furthermore a method of providing an external device list according to an embodiment which will be described in detail below may be implemented with a computer executable program.

A user may move the remote control device up and down and left and right or may rotate it. The pointer displayed on the display unit of the image display device corresponds to the movement of the remote control device . Since the corresponding pointer moves and is displayed corresponding to the movement on 3D space as shown in the drawing the remote control device may be called a space remote controller.

As shown in when a user moves the remote control device to the left the pointer displayed on the display unit of the image display device moves to the left in correspondence to the movement of the remote control device .

Information on the movement of the remote control device which is sensed by a sensor of the remote control device is transmitted to the image display device. The image display device may calculate the coordinates of the pointer from the information on the movement of the remote control device . The image display device may display the pointer in correspondence to the calculated coordinates.

On the contrary when a user moves the remote control device closer to the display unit a selected area on the display unit corresponding to the pointer may be zoomed out and reduced.

On the other hand when the remote control device becomes far from the display unit a selected area may be zoomed out and when the remote control device becomes closer to the display unit a selected area may be zoomed in.

Moreover while a specific button in the remote control device is pressed up down and left right movements may be disregarded. That is when the remote control device becomes closer to or away from the display unit up down and left right movements may be disregarded but only the back and forth movements may be recognized. While a specific button in the remote control device is not pressed the pointer moves in correspondence to the up down and left right movements of the remote control device .

Moreover the moving speed or moving direction of the pointer may correspond to that of the remote control device .

Furthermore the pointer of this specification means an object displayed on the display unit in correspondence to an operation of the remote control device . Accordingly besides an arrow shape displayed as the pointer in the drawing the pointer may have various shapes of objects. For example the pointer conceptually may include a dot a cursor and a thick outline. Moreover the pointer may be displayed on the display unit corresponding to a point on the x axis and the y axis and also a plurality of points such as a line and a surface.

Referring to the wireless communication unit transmits receives a signal to from an arbitrary one of the image display devices according to the above mentioned embodiments.

The remote control device includes an RF module for transmitting receiving a signal to from the image display device according to RF communication standards and an IR module for transmitting receiving a signal to from the image display device according to IR communication standards.

Moreover the remote control device transmits a signal containing information on the movement thereof to the image display device through the RF module .

Moreover the remote control device may receive a signal that the image display device transmits through the RF module and may transmit commands on power on off channel change and volume change to the image display device through the IR module if necessary.

The user input unit may be configured with a keypad a button a touch pad or a touch screen. A user may input commands related to the image display device to the remote control device by manipulating the user input unit . If the user input unit has a hard key button a user may input commands related to the image display device to the remote control device through a push operation of the hard key button.

If the user input unit has a touch screen a user may input commands related to the image display device to the remote control device by touching a soft key of the touch screen. Moreover the user input unit may include various kinds of input means that a user manipulates such as a scroll key and a jog key and this embodiment does not limit the scope of the present invention.

The sensor unit may include a gyro sensor or an acceleration sensor . The gyro sensor may sense information on the movement of the remote control device .

For example the gyro sensor may sense information on the operation of the remote control device on the bases of x y and z axes and the acceleration sensor may sense information on the moving speed of the remote control device . Furthermore the remote control device may further include a distance measurement sensor that senses the distance between the remote control device and the display unit of the image display device .

The output unit may output an image or sound signal corresponding to the manipulation of the user input unit or a signal transmitted from the image display device . A user may recognize the manipulation of the user input unit or the control of the image display device through the output unit .

For example the output unit may include an LED module that is turned on off a vibration module that vibrates a sound outputting module that outputs sound or a display module that outputs an image when the user input unit is manipulated or a signal is transmitted to or received from the image display device through the wireless communication unit .

Moreover the power supply unit supplies power to the remote control device and stops supplying power to the remote control device when the remote control device does not move for a predetermined time so that power waste may be reduced. The power supply unit may restart to supply power after a predetermined key in the remote control device is manipulated.

The storage unit may store various kinds of programs and application data necessary for controls or operations of the remote control device . If the remote control device wirelessly transmits and receives a signal through the image display device and the RF module the remote control device and the image display device may transmit receive a signal in a predetermined frequency band.

The control unit of the remote control device may store in the storage unit information on a frequency band for wirelessly transmitting receiving a signal to from the image display device paired with the remote control device and may refer to the stored information.

The control unit controls general matters related to a control of the remote control device . The control unit may transmit to the image display device a signal corresponding to a predetermined key manipulation of the user input unit or a signal corresponding to the movement of the remote control device sensed by the sensing unit through the wireless communication unit .

The configuration of the home screen shown in may be an example of a basic screen of the image display device . Such a screen may be set with an initial screen when power is on or starting from a standby mode or a basic screen by an operation of a home key equipped in the remote control device .

Referring to the home screen may include a card object region. The card object region may include a plurality of card objects and which are classified by the sources of contents.

A card object BROADCAST for displaying a broadcast image a card object NETCAST for displaying a CP list and a card object APP STORE for displaying a list of applications provided are shown in the drawing.

Moreover as a card object that is not displayed on the display unit and is disposed on a hidden area but is replaced and displayed when a card object is moved a card object CHANNEL BROWSER for displaying a thumbnail list of broadcast channels a card object TV GUIDE for displaying a broadcast guide list a card object RESERVATION REC for displaying a reservation list a card object MY MEDIA for displaying a media list of a device disposed in or connected to the image display device and a card object TV GUIDE for displaying a broadcast guide list may be shown in the drawing.

The card object BROADCAT for displaying a broadcast image may include a broadcast image received through the tuner or the network interface unit an object for displaying corresponding broadcast image related information an object for displaying an external device and a setup object .

Since the broadcast image is displayed as a card object and its size is fixed by a locking function a user may continuously watch a broadcast image.

The broadcast image may have a size that is changed by the manipulation of a user. For example the size of the corresponding broadcast image may be enlarged or reduced by drag using the pointer of the remote control device . By such an enlargement or reduction the number of card objects displayed on the display unit may be two or four instead of three in the drawing.

Moreover when the broadcast image in the card object is selected it may be displayed on the display unit in a full screen.

The object for displaying corresponding broadcast image related information may include a channel number DTV7 1 a channel name YBC HD a broadcast program title Oh Lady and a broadcast time pm 08 00 08 50. By doing so a user may intuitively recognize information on the broadcast image .

When the object for displaying corresponding broadcast image related information is selected related EPG information may be displayed on the display unit .

Moreover an object for displaying a date 03.24 a day of the week THU and a current time pm 08 13 may be displayed on the card object for displaying a broadcast image. By doing so a user may intuitively recognize time information.

An object for displaying an external device may display an external device connected to the image display device . For example when the object for displaying an external device is selected a list of external devices connected to the image display device may be displayed.

The setup object may be used for inputting various settings of the image display device . For example various settings such as image setting audio setting screen setting reservation setting pointing setting of the remote control device and network setting may be made.

Moreover the card object for displaying a CP list may include a card object title NETCAST and a CP list . In the drawing Yakoo Metflix weather.com Picason and My tube are shown as CPs in the CP list but various settings are possible.

When the card object title is selected the corresponding card object may be displayed on the display unit in a full screen.

Moreover when a predetermined CP in the CP list is selected a screen including a contents list that a corresponding CP provides may be displayed on the display unit .

The card object for displaying a list of applications provided may include the card object title APP STORE and the application list . The application list may be a list which is aligned being classified by each item in an application store. In the drawing the list may be displayed being aligned in a popular order HOT and the latest order NEW but the present invention is not limited thereto. That is various examples are available.

When the card object title is selected the corresponding card object may be displayed on the display unit in a full screen.

Moreover when a predetermined application item in the application list is selected a screen for providing information on a corresponding application may be displayed on the display unit .

The login item may be used for accessing an application store or logging in a network connected to an image display device. The help item may be used for the help during an operation of the image display device . The exit item may be used for exiting from a corresponding home screen. At this point a broadcast image being received may be displayed in a full screen.

An object for displaying the number of entire card objects may be displayed below the card objects and . The object may display the number of entire card objects of course the number of card objects among the entire card objects displayed on the display unit .

Moreover the card object for displaying a thumbnail list of a broadcast channel may include a card object title CHANNEL BROWSER and a thumbnail list of a broadcast channel. Broadcast channels received sequentially are displayed as thumbnail images in the drawing but the present invention is not limited thereto. That is a video is possible. The thumbnail list may include a thumbnail image and channel information on a corresponding channel. By doing so a user may intuitively recognize content of a corresponding channel.

Such a thumbnail image may be a thumbnail image on a preference channel that a user registers in advance or a thumbnail image on a channel after or before the broadcast image in the card object . Moreover eight thumbnail images are shown in the drawing but various settings are possible. Additionally a thumbnail image in a thumbnail list may be updated.

When the card object title is selected the corresponding card object may be displayed on the display unit in a full screen. That is content on a thumbnail list may be displayed on the display unit .

Moreover when a predetermined thumbnail image in the thumbnail list of a broadcast channel is selected a broadcast image corresponding to a corresponding thumbnail image may be displayed on the display unit .

The card object for displaying a broadcast guide list may include a card object title TV GUIDE and a broadcast guide list . The broadcast guide list may be a list for broadcast programs or broadcast images of other channels after the broadcast image in the card object but the present invention is not limited thereto. That is various examples are available.

Additionally when the card object title is selected the corresponding card object may be displayed on the display unit in a full screen.

Moreover when a predetermined broadcast item in the broadcast guide list is selected a broadcast image corresponding to a corresponding broadcast item may be displayed on the display unit or broadcast information corresponding to a corresponding broadcast item may be displayed on the display unit .

The card object for displaying a broadcast reservation list or a recording list may include a card object title RESERVATION REC and a broadcast reservation list or recording list . The broadcast reservation list or recording list may be a list including broadcast items that a user reserves in advance or broadcast items recorded according thereto. In the drawing a thumbnail image is displayed by each corresponding item but various examples are available.

Additionally when the card object title is selected the corresponding card object may be displayed on the display unit in a full screen.

Furthermore a broadcast item set in advance for reservation or a broadcast item recorded in the broadcast reservation list or recording list is selected broadcast information on a corresponding broadcast or a recorded broadcast image may be displayed on the display unit .

The card object for displaying a media list may include a card object title MY MEDIA and a media list . The media list may be a list of media stored in the image display device or stored in a device connected to thereto. Video still images and audio are shown as an example in the drawing but besides that various examples such as text documents and e book documents are available.

Additionally when the card object title is selected the corresponding card object may be displayed on the display unit in a full screen.

Moreover when a predetermined media item in the media list is selected a screen corresponding to a corresponding media may be displayed on the display unit .

The card object TV GUIDE for displaying a broadcast guide list may include a card object title TV GUIDE and a broadcast guide list . The broadcast guide list may be a guide list for each broadcast type. A list for each broadcast type is shown in the drawing by classifying broadcasts into entertainments such as drama news or sports but various settings are available. That is the broadcast guide list may be a list for each type such as drama movie news sports and animation. By doing so a user may confirm a guide list that classifies broadcasts into each genre

When the card object title is selected the corresponding card object may be displayed on the display unit in a full screen.

Moreover when a predetermined broadcast item in the broadcast guide list is selected a screen corresponding to a corresponding broadcast image may be displayed on the display unit .

The card objects and displayed on the display unit and the card objects and disposed on the hidden area and not displayed on the display unit may be interchangeable by an input for moving a card object.

That is at least one of the card objects and displayed on the display unit may be moved on the hidden area and at least one of the card objects and disposed on the hidden area may be displayed on the display unit .

Furthermore the home screen of the image display device may further include a card object for displaying information on software upgrade.

Hereinafter referring to a method of providing an external device list according to a first embodiment will be described. is a flowchart illustrating the method of providing an external device list according to the first embodiment. are views illustrating a screen that provides an external device list of an image display device according to the first embodiment.

Referring to first the control unit displays a plurality of external device icons which allows external devices to be connected to the image display device on the display unit of the image display device in operation S. Here a plurality of external devices as external devices connected to the image display device via a wired wireless network may include a Digital Versatile Disc DVD player a DVD recorder a Blu ray Disc BD player a set top box a digital TV a personal computer PC a camera a camcorder an HDD player and a memory card. However they are just examples of external devices. Thus a device having a built in recording medium for recording a file may serve as an external device.

As shown in a plurality of external device icons representing a plurality of external devices are displayed on the full screen of the display unit . Moreover the control unit determines which external device icons are connected to the image display device in order to display specific symbols and on the external device icons that are being connected to the image display device . Therefore external device icons that are not being connected to the image display device are distinguished. Here displaying a specific symbol on an external device icon is used as one example of a method of distinguishing icons from each other but the present invention is not limited thereto. That is any one of letters symbols colors and flashing lights may be used for distinction.

The control unit determines which one of the plurality of external device icons displayed on the display unit has a pointer thereon in operation S.

As shown in when the pointer is positioned on the first external device icon among the plurality of external device icons the control unit may display an image signal which is inputted from an external device related the first external device icon for example a BD player on the full screen of the image display device in operation S. Through this a user could confirm an image signal in advance which is inputted from an external device before switching the input of the external device so that the user s convenience may be improved.

Moreover when the pointer is positioned on the first external device icon among the plurality of external device icons the first external device icon having the pointer thereon may be highlighted.

Moreover as shown in an image signal of an external device related to the first external device icon having the pointer thereon may be displayed on the area where the first external device icon is displayed.

Moreover as shown in when the pointer is positioned on the first external device icon a predetermined popup window is displayed on an area adjacent to the first external device icon and an image signal of an external device related to the first external device icon may be displayed on the popup window .

As shown in when the pointer is positioned on one of the plurality of external device icons for example the second external device icon representing a PC the control unit displays the image signal which inputted from an external device for example the PC related to the first external device icon having the pointer thereon on the full screen of the image display device. In this state when an input is received to select the second external device icon in operation S as shown in a popup window that asks whether to select an input switch to a PC i.e. a second external device is displayed on the full screen of the image display device .

Then if the input switch to the external device is selected through the popup window the input is switched to the PC i.e. the second external device in operation S.

Accordingly as shown in an image signal of the PC i.e. the selected second external device is displayed on the full screen of the image display device .

Furthermore the remote control device that controls the image display device may control the input switched external device. This will be described in more detail.

The remote control device transmits a control command for controlling an external device to the input switched external device through the image display device in operation S. In response to the transmitted control command a control command result of the external device is displayed on the full screen of the image display device .

For example as shown in while the image signal of the second external device is displayed on the display unit in case that a control command of the remote control device is transmitted to a corresponding external device the pointer displayed on the image signal of the second external device may be manipulated in response to the control command.

By doing so the remote control device that controls the image display device may identically control the input switched external device so that the user s convenience may be improved.

According to embodiments since an image signal inputted from an external device is provided in advance before input switching ease of use and service efficiency may be improved.

The method of providing an external device list according to the present invention may be programmed to be executed in a computer and may be stored on a computer readable recording medium. Examples of the computer readable recording medium include read only memory ROM random access memory RAM CD ROMs magnetic tapes floppy disks and optical data storage devices.

The computer readable recording medium can also be distributed over network coupled computer systems so that the computer readable code is stored and executed in a distributed fashion. Also functional programs codes and code segments for accomplishing the present invention can be easily construed by programmers skilled in the art to which the present invention pertains.

Moreover although the preferred embodiments of the present invention are described above the present invention is not limited the above mentioned specific embodiments. It will be understood by those skilled in the art that various changes in forms and details may be made therein without departing from the spirit and scope of the invention. Also these modified embodiments should be understood without departing from the technical scope or prospect of the present invention.

