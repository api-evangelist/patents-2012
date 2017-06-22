---

title: Digital system and method of processing service data thereof
abstract: A digital system and a method of processing service data thereof are disclosed. The digital system includes a first device configured to transmit at least one of device information and device location information of a first device to a second device which is connected to the first device, receive service data from the second device, the service data being extracted based upon at least one of the device information and the device location information of the first device, process and output the service data on a screen, transmit a command signal which is selected from the outputted service data to the second device and receive respond data corresponding to the command signal from the second device and outputting the respond data on the screen.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08627364&OS=08627364&RS=08627364
owner: LG Electronics Inc.
number: 08627364
owner_city: Seoul
owner_country: KR
publication_date: 20120919
---
This application claims the benefit of the Korean Patent Application Nos. 10 2011 0094570 filed on Sep. 20 2011 and 10 2011 0125287 filed on Nov. 28 2011 which are hereby incorporated by reference as if fully set forth herein.

The present invention relates to a digital system including digital devices and more particularly to a method of providing an enhanced service in terms of quality and quantity via inter authentication and data transmission reception between a server and a digital device and between digital devices included in a digital system.

As compared to traditional analog broadcasting digital broadcasting has lower data loss owing to high resistance to noise is advantageous for error correction and provides higher resolution and consequently more vivid imagery. Moreover provision of a bidirectional service is possible under digital broadcasting unlike in analog broadcasting.

Although digital broadcasting has been realized via terrestrial satellite and cable media in recent years an Internet Protocol Television IPTV broadcasting service related to digital content such as real time broadcasting and Content on Demand CoD for example has also been implemented via an IP network connected to individual homes.

Accordingly the present invention is directed to a digital system and a method of processing service data thereof that substantially obviate one or more problems due to limitations and disadvantages of the related art.

One object of the present invention is to provide a digital system including at least one server and a plurality of digital devices which can expand a channel or service coverage originally included in each digital device.

Another object of the present invention is to provide a digital system which can ensure exchange of related service data between digital devices as well as between a server and each digital device included in the digital system.

A further object of the present invention is to provide a digital device which can acquire more abundant service data than in the related art thereby providing an improved service guide in terms of quantity and or quality.

Additional advantages objects and features of the invention will be set forth in part in the description which follows and in part will become apparent to those having ordinary skill in the art upon examination of the following or may be learned from practice of the invention. The objectives and other advantages of the invention may be realized and attained by the structure particularly pointed out in the written description and claims hereof as well as the appended drawings.

To achieve the above objectives according to an embodiment of the present invention to a digital system of processing service data includes a first device configured to transmit at least one of device information and device location information of a first device to a second device which is connected to the first device receive service data from the second device the service data being extracted based upon at least one of the device information and the device location information of the first device process and output the service data on a screen transmit a command signal which is selected from the outputted service data to the second device and receive respond data corresponding to the command signal from the second device and outputting the respond data on the screen.

The digital system further comprises the second device configured to determine a group of the first device based upon the device location information transmit an identifier of the determined group of the first device store Uniform Resource Locator URL information to be downloaded the thumbnail image in the service data and transmit the stored URL information corresponding to the determined group to the first device.

The device location information includes at least one an original network identifier a Zone Improvement Plan ZIP code and a Global Positioning System GPS information wherein the device information of the first device includes at least one of a nation a language a receiver type a device model a service list and a user identifier wherein the service data includes at least one of program data thumbnail image data channel browse data and guide data and wherein the service list includes a 3 id which comprises an original network identifier a transport stream identifier a service identifier and a service or channel name.

The first device is further configured to transmit a request of both transferring a device identifier according to a HTTP protocol and a key for data encryption to the second device receive a response code and the key from the second device and encrypt a service list which is currently displayed on the screen using the key and transmitting the encrypted service list to the second device.

The first device is further configured to reproduce a service if the transmitted service list is valid transmit a security authentication code to be coupled to the second device and couple to the second device according to a response of the second device.

If the transmitted service list is not valid the first device is further configured to at least one of return a response code indicating a service to be not reproduced to the first device transmit the service list and request the service to be reproduced.

The first device is further configured to extract the URL information received from the second device download the thumbnail image based on the URL information and output the downloaded thumbnail image.

A method of processing service data in a digital system includes receiving service data and device information from a first device transmitting a identifier of a group from a second device to the first device based upon the device information the group including the first device processing the service data and storing the processed service data based upon the identifier of the group and transmitting the stored service data to the first device based upon the identifier of the group.

The service data includes at least one of program data thumbnail image data channel browse data and guide data and wherein the device information of the first device includes at least one of a nation a language a receiver type a device model a service list and a user identifier.

The service list includes a 3 id which comprises an original network identifier a transport stream identifier a service identifier and a service or channel name.

The step of processing the service data comprises combining the service of the first device and service data received from a third device.

The second device controls the stored service to be transmitted periodically to the first device and wherein the second device controls a changed transmission period of the stored service to be changed if the service data of the first device is duplicated to the service data which is previously stored in the second device.

A method of processing service data in a digital system includes transmitting device location information of a first device to a second device which is connected to the first device receiving service data from the second device the service data being extracted based upon the device location information of the first device processing and outputting the service data on a screen transmitting a command signal which is selected from the outputted service data to the second device and receiving respond data corresponding to the command signal from the second device and outputting the respond data on the screen.

The device location information includes at least one of an original network identifier a ZIP code and Global Positioning System GPS information wherein the service data includes at least one of program data thumbnail image data channel browse data and guide data and wherein the device information of the first device includes at least one of a nation a language a receiver type a device model a service list and a user identifier.

The service list includes a 3 id which comprises an original network identifier a transport stream identifier and a service identifier and wherein the service list further includes a service or channel name.

The step of transmitting a command signal comprises transmitting a request of both transferring a device identifier according to a HTTP protocol and a key for data encryption to the second device receiving a response code and the key from the second device and encrypting a service list which is currently displayed on the screen using the key and transmitting the encrypted service list to the second device.

The method further comprises at least one of returning a response code indicating a service to be not reproduced to the first device and transmitting the service list and requesting the service to be reproduced.

The step of transmitting a command signal further comprises transmitting a security authentication code to be coupled to the second device and coupling to the second device according to a response of the second device.

The second device stores Uniform Resource Locator URL information to be downloaded the thumbnail image in the service data and wherein the first device extracts the URL information received from the second device downloads the thumbnail image based on the URL information and outputs the downloaded thumbnail image.

Reference will now be made in detail to the embodiments of the present invention examples of which are illustrated in the accompanying drawings.

With respect to constituent elements used in the following description suffixes module and unit are simply given in consideration of ease in the preparation of the specification and may be mingled with each other.

A digital device according to the present invention as set forth herein may be an intelligent device that additionally provides a computer support function in addition to a broadcasting reception function for example. As a result of adding an Internet function to the broadcasting reception function the digital device may be provided with a more convenient interface such as a handwriting input device a touch screen or a spatial remote controller. Also the digital device enables for example e mailing Web browsing banking and game playing functions by accessing the Internet or a computer because the digital device supports a wired or wireless Internet function. To implement these various functions a standardized general purpose Operating System OS may be used. In addition since the digital device allows various applications to be freely added to or deleted from for example a general purpose OS kernel it may perform various user friendly functions. Examples of the digital device include a network TV a Hybrid Broadcast Broadband TV HBBTV and a smart TV and as occasion demands may further include a Personal Digital Assistant PDA or a smart phone. In the following description the digital device may correspond to any one of a mobile terminal and an image display device. However for convenience of description in this specification the terms digital device mobile terminal and image display device may be used interchangeably and may respectively represent a particular device name in the corresponding drawing.

The embodiments of the present invention will now be described in detail with reference to the accompanying drawings and the disclosure illustrated in the accompanying drawings. However it is to be understood that the invention is not limited to or restricted by the following embodiments.

Although the terms used in the following description are selected as much as possible from general terms that are widely used at present while taking into consideration of the functions obtained in accordance with the present invention these terms may be replaced by other terms based on intensions of those skilled in the art customs emergence of new technologies or the like. Also in a particular case terms that are arbitrarily selected by the applicant of the present invention may be used. In this case the meanings of these terms may be described in corresponding description parts of the invention. Accordingly it should be noted that the terms used herein should be construed based on practical meanings thereof and the whole content of this specification rather than being simply construed based on names of the terms.

As shown in according to the embodiment of the present invention the digital system includes a Content Provider CP a Service Provider SP a Network Provider NP and a Home Network End User HNED . For example the FINED may correspond to a client i.e. a digital device according to the present invention. As described above the digital device may include a network TV a smart TV and an IPTV for example.

The CP may produce and provide a variety of content. The CP as shown in may include a terrestrial broadcaster a System Operator SO a Multiple System Operator MSO a satellite broadcaster an Internet broadcaster and a private CP. The CP may provide for example a variety of applications as well as broadcast content. This will be described hereinafter in more detail.

The SP may service package the content provided by the CP and transmit the service packaged content. For example the SP shown in may package a first terrestrial broadcast a second terrestrial broadcast a cable MSO a satellite broadcast various Internet broadcasts and applications and provide the packaged broadcasts to a user.

The SP may provide the service to a client using a uni cast or multi cast method or using a push or pull method. The uni cast method transmits data between a single transmitter and a single receiver in a one to one ratio. For example if a receiver requests data to a server in the uni cast method the server transmits the data to the corresponding receiver in response to the request. On the other hand the multi cast method transmits data to a plurality of receivers within a particular group. For example a server transmits data to a plurality of pre registered receivers simultaneously. An Internet Group Management Protocol IGMP may be used for the multicast registration.

The CP and the SP may be the same entity. For example the CP may produce content service package the content and provide the packaged service. Thus the CP may perform the function of the SP . The converse case is also possible.

Meanwhile to protect content transmitted in the digital system the server may utilize certain means such as conditional access content protection or the like. In this case the client may utilize certain means to correspond to the conditional access or content protection such as a CableCARD a Downloadable Conditional Access System DCAS or the like.

In addition the client may adopt a bi directional service via a network. In this case the client may also function as a CP and the SP may receive content from the client and in turn transmit the content to another client.

The digital device includes a network interface a Transmission Control Protocol Internet Protocol TCP IP manager a service delivery manager a Service or System Information SI decoder a demultiplexer DEMUX an audio decoder a video decoder a display Audio Video A V and On Screen Display OSD module a service control manager a service discovery manager an SI metadata database DB a metadata manager a service manager and an User Interface UI manager for example.

The network interface may receive or transmit IP packets via a network. That is the network interface may receive for example a service and content from the SP via a network.

The TCP IP manager has a role in transmission of the IP packets to and from the digital device i.e. in packet transmission between a source and a destination. The TCP IP manager may sort the received packets to correspond to appropriate protocols and output the sorted packets to the service delivery manager the service the service control manager discovery manager and the metadata manager for example.

The service delivery manager serves to control received service data. For example the service delivery manager may use a Real time Transport Protocol RTP RT Control Protocol RTCP in the case of controlling real time streaming data. When transmitting the real time streaming data using the RTP the service delivery manager may parse the received data packets based on the RTP and transmit the parsed data packets to the DEMUX or may store the receive data packets in the SI metadata DB based on control of the service manager . The service delivery manager may feedback information received via the network to a service providing server using the RTCP.

The DEMUX demultiplexes the received packets to audio video and System Information SI data and transmits the demultiplexed data to the audio and video decoders and and the SI decoder .

The SI decoder decodes service information such as for example Program Specific Information PSI Program and System Information protocol PSIP and Digital Video Broadcasting SI DVB SI .

The SI decoder stores the decoded service information in for example the SI metadata DB . The stored service information for example may be read and used by a corresponding component in response to a user request. In the present invention service information related to an Electronic Program Guide EPG service depending on a user request a channel browser service or the like may also be read from the SI metadata DB . This will be described later in more detail.

The audio and video decoders and respectively decode audio data and video data demultiplexed in the DEMUX . The decoded audio and video data are provided to the user via the display A V and OSD module .

An application manager may consist of the UT manager and the service manager for example. The application manager may manage overall states of the digital device provide a user interface and manage other managers.

The UI manager provides a Graphic User Interface GUI for the user using an OSD and the like and performs an operation of the device upon receiving a key input from the user. For example when receiving a key input signal for channel selection from the user the UI manager transmits the key input signal to the service manager .

The service manager controls a service associated manager such as the service delivery manager the service discovery manager the service control manager and the metadata manager for example.

The service manager makes a channel map and selects a channel using the channel map based on the key input received from the UT manager . Additionally the service manager receives service information on the channel from the SI decoder and sets an audio video Packet Identifier PID of the selected channel to the DEMUX . The set PID is used for the above described demultiplexing. Thus the DEMUX filters audio and video data and SI data using the PID.

The service discovery manager provides information required to select an SP that provides a service. When receiving a signal for channel selection from the service manager the service discovery manager searches a service using the information.

The service control manager takes charge of selection and control of a service. For example the service control manager may perform selection and control of a service using the IGMP or the Real Time Streaming Protocol RTSP if the user selects a live broadcasting service of the same type as a traditional broadcasting service or using the RTSP if the user selects a Video on Demand VOD service. The RTSP may provide a trick mode with respect to real time streaming The service control manager may initialize and manage a session through an IMS gateway using an IP Multimedia Subsystem IMS and a Session Initiation Protocol SIP . The aforementioned protocols are given by way of example and other protocols may be used according to embodiments.

The metadata manager manages service associated metadata and stores the metadata in the SI metadata DB .

The SI metadata DB stores the service information decoded by the SI decoder the metadata managed by the metadata manager and information required to select the SP provided by the service discovery manager . Additionally the SI metadata DB may store for example system setup data.

The IMS gateway may be a gateway in which functions required to access an IMS based IPTV service are collected.

Referring to the digital device according to another exemplary embodiment of the present invention may include a broadcast receiving unit an external device interface a storage unit a user input interface a control unit a display unit an audio output unit a power supply unit and an image capturing unit not shown . The broadcast receiving unit may include at least one tuner a demodulator and a network interface . As necessary the broadcast receiving unit may be designed to include the tuner and the demodulator without the network interface or may be designed to include only the network interface without the tuner and the demodulator . Although not shown the broadcast receiving unit may further include a multiplexer to multiplex a signal that has passed through the tuner and demodulated by the demodulator and a signal that has been received through the network interface . Additionally although not shown the broadcast receiving unit may further include a demultiplexer to demultiplex the multiplexed signal or the demodulated signal or to demultiplex the signal that has passed through the network interface .

The tuner receives one of Radio Frequency RF broadcast signals received through an antenna by tuning a user selected channel or all pre stored channels. Then the tuner converts the received RF broadcast signal into an Intermediate Frequency IF signal or a baseband signal.

For example the tuner may convert the received RF broadcast signal into a digital IF DIF signal if the RF broadcast signal is a digital broadcast signal or may convert the received RF broadcast signal into an analog baseband audio or video signal Composite Video Banking Sync Sound Intercarrier Frequency CVBS SIF signal if the RF broadcast signal is an analog broadcast signal. That is the tuner is capable of processing both digital and analog broadcast signals. The analog baseband audio or video signal CVBS SIF signal output from the tuner may be directly input to the control unit .

The tuner may receive an RF broadcast signal of a single carrier based on an Advanced Television System Committee ATSC mode or an RF broadcast signal of multiple carriers based on a Digital Video Broadcasting DVB mode.

Additionally the tuner may convert one of the RF broadcast signals received through the antenna into the IF signal or the baseband signal by sequentially tuning and receiving the RF broadcast signals of all broadcast channels stored via a channel memory function.

For example if the DIF signal output from the tuner is based on the ATSC mode the demodulator performs for example 8 Vestigal Side Band 8 VSB demodulation. Also the demodulator may perform channel decoding. To this end the demodulator may include a trellis decoder a de interleaver and a Reed Solomon RS decoder and may perform trellis decoding de interleaving and RS decoding.

For example if the DIF signal output from the tuner is based on the DVB mode the demodulator performs for example Coded Orthogonal Frequency Division Multiple Access COFDMA demodulation. Also the demodulator may perform channel decoding. To this end the demodulator may include a convolution decoder a de interleaver and an RS decoder and may perform convolution decoding de interleaving and RS decoding.

The demodulator may output a stream signal after performing the demodulation and the channel decoding.

The stream signal may be obtained by multiplexing a video signal an audio signal or a data signal. For example the stream signal may be MPEG 2 Transport Stream TS obtained by multiplexing an MPEG 2 video signal or a Dolby AC 3 audio signal. More specifically the MPEG 2 TS may contain a 4 byte header and a 184 byte payload.

The demodulator as described above may be provided separately for the ATSC mode and the DVB mode. That is the broadcast receiving unit may include an ATSC demodulator and a DVB demodulator.

The stream signal output from the demodulator may be input to the control unit . For example the control unit may control demultiplexing and video audio signal processing and may also control video output through the display unit and audio output through the audio output unit .

The external device interface enables interface between the digital device and various external devices. To this end the external device interface may include an A V input output unit not shown or a wireless communication unit not shown .

The external device interface may be connected to an external device such as a Digital Versatile Disk DVD a blu ray a game device a camera a camcorder a computer e.g. a laptop computer or a tablet PC a smart phone a Bluetooth device a Cloud or the like in a wire wireless manner The external device interface transmits a video audio or data containing an image signal externally input through the external device connected thereto to the control unit of the digital device . Also the external device interface may output the video audio or data signal processed by the control unit to the external device. To this end the external device interface may further include an A V input output unit or a wireless communication unit not shown .

The A V input output unit may include a Universal Serial Bus USB terminal a CVBS terminal a component terminal an S video terminal analog a Digital Visual Interface DVI terminal a High Definition Multimedia Interface HDMI terminal an RGB terminal and a D SUB terminal for example to input video and audio signals of the external device to the digital device .

The wireless communication unit may perform a short range wireless communication with other electronic devices. For example network connection between the digital device and other electronic devices may be realized via a communication protocol such as Bluetooth Radio Frequency Identification RFID infrared Data Association IrDA Ultra Wideband UWB ZigBee Digital Living Network Alliance DLNA and the like.

In addition the external device interface may be connected to various set top boxes through at least one of the above mentioned various terminals and may perform an input output operation with the set top boxes.

The external device interface may receive an application or an application list from an adjacent external device and may transmit the same to the control unit or the storage unit .

The network interface provides an interface for connecting the digital device to a wire wireless network including an Internet network. The network interface may include an Ethernet terminal for example for wire network connection or may use a communication standard such as Wireless Local Area Network WLAN Wi Fi Wireless broadband Wibro World Interoperability for Microwave Access Wimax and High Speed Downlink Packet Access for example for wireless network connection.

The network interface may transmit or receive data to and from other users or other digital devices through a network connected thereto or another network linked on the connected network. In particular the network interface may transmit a part of content data stored in the digital device to a selected one of other users previously registered in the digital device or a selected one of other digital devices previously registered in the digital device .

The network interface may access a predetermined Web page through a network connected thereto or another network linked on the connected network. That is the network interface may transmit or receive data to or from a corresponding server by accessing the predetermined Web page through the network. Additionally the network interface may receive content or data provided by a CP or a network manager. More specifically the network interface may receive content such as movies advertisements games VOD and broadcast signals for example and associated information provided by a CP or a network manager through a network. In addition the network interface may receive update information and update files of firmware provided by a network manager and may transmit data to the Internet a CP or a network manager.

The network interface may select and receive a desired application among multiple applications that are open to the public through a network.

The storage unit may store a program for processing and controlling each signal of the control unit or may store the processed video audio or data signal.

Also the storage unit may temporarily store the video audio or data signal input from the external device interface or the network interface . The storage unit may store information on a predetermined broadcast channel through a channel memory function.

The storage unit may store an application or an application list input from the external device interface or the network interface .

For example the storage unit may include a storage medium of at least one type of a flash memory type a hard disk type a multimedia card micro type a card type memory for example SD or XD memory RAM and ROM for example EEPROM . The digital device may play a content file for example a moving picture file a still image file a music file a text file and an application file stored in the storage unit to provide the played content file to the user.

Although shows the embodiment in which the storage unit and the control unit are provided separately the scope of the invention is not limited to the embodiment of . The storage unit may be included in the control unit .

The user input interface may transmit a signal input by the user to the control unit or may transmit a signal input from the control unit to the user.

For example the user input interface may receive and process a control signal such as power on off channel selection and screen setup for example from a remote controller in accordance with various communication modes such as an RF communication mode and IR communication mode for example. Alternatively the user input interface may transmit a control signal from the control unit to the remote controller .

Also the user input interface may transmit a control signal input by a local key such as a power key a channel key a volume key and a setup key to the control unit .

The user input interface may transmit a control signal input by a sensing unit not shown which senses gesture of the user to the control unit or may transmit the signal from the control unit to the sensing unit. In this case the sensing unit not shown may include a touch sensor an audio sensor a position sensor and an action sensor for example.

The control unit may demultiplex a stream input through the tuner the demodulator or the external device interface or may process the demultiplexed signal to generate and output a signal for a video and audio output.

The video signal processed by the control unit may be input to the display unit and be displayed as a corresponding image. Also the video signal processed by the control unit may be input to the external output device through the external device interface .

The audio signal processed by the control unit may be output to the audio output unit . Also the audio signal processed by the control unit may be input to an external output device through the external device interface .

Although not shown in the control unit may include a demultiplexer and a video processor for example.

The control unit may control the overall operations of the digital device . For example the control unit may control the tuner so as to tune an RF broadcast signal corresponding to a user selected channel or a pre stored channel.

The control unit may control the digital device in response to a user command input through the user input interface or using a program stored therein. In particular the control unit may access a network and download an application or an application list selected by the user to the digital device over the network.

In one example the control unit controls the tuner so as to receive a signal of a channel selected in response to a specific channel selection command received through the user input interface . Then the control unit processes an audio video or data signal of the selected channel. The control unit may also output for example information on the user selected channel as well as the processed video or audio signal to the display unit or the audio output unit .

In another example the control unit may output a video or audio signal input from an external device such as for example a camera or a camcorder through the external device interface to the display unit or the audio output unit in response to an external device video playback command received through the user input interface .

The control unit may control the display device to display an image. For example the control unit may control the display unit so as to display a broadcast image received from the tuner an externally input image received through the external device interface an image received through the network interface or an image stored in the storage unit . In this case the image displayed on the display unit may be a 2 Dimensional 2D or 3 Dimensional 3D still image or moving image.

Additionally the control unit may control content playback. Here the content may be content stored in the digital device received broadcasting content or externally input content. The content may include at least one of a broadcast image an externally input image an audio file a still image an accessed Web page and a text file.

In the case of entering an application view item the control unit may control display of an application or an application list that is stored in the digital device or is downloadable from an external network.

The control unit may control installation and driving of an application downloaded from an external network in addition to various user interfaces. Also the control unit may control the display unit to display an image associated with an application that is executed by user selection.

Although not shown in the drawings a channel browsing processor to produce a thumbnail image corresponding to a channel signal or an externally input signal may be further provided.

The channel browsing processor may receive for example a stream signal output from the demodulator or a stream signal output from the external device interface extract an image from the received stream signal and produce a thumbnail image. The produced thumbnail image may be directly input to the control unit or may be input after being encoded. Also the produced thumbnail image may be encoded into a stream and input to the control unit . The control unit may control the display unit to display a thumbnail list consisting of a plurality of input thumbnail images. The thumbnail images within the thumbnail list may be updated sequentially or simultaneously. Therefore the user can readily identify content of a plurality of broadcasting channels.

The display unit converts the video data and OSD signals processed by the controller or the video and data signals received from the external device interface to R G B signals respectively to generate driving signals.

The display unit may be selected from among a Plasma Display Panel PDP a Liquid Crystal Display LCD an Organic Light Emitting Diode OLED a flexible display and a 3D display for example.

The display unit may take the form of a touch screen. In this case the display unit may serve not only an output device but also an input device.

The audio output unit receives a signal audio processed by the control unit for example a stereo signal a 3.1 channel signal or a 5.1 channel signal and outputs the received signal as sound. Various types of speakers may be used as the audio output unit .

To sense gesture of the user as described above the digital device may further include a sensing unit not shown that includes at least one of a touch sensor an audio sensor a position sensor and an action sensor. The signal sensed by the sensing unit not shown may be transmitted to the control unit through the user input interface .

The digital device may further include an image capturing unit not shown to capture an image of the user. Image information taken by the image capturing unit not shown may be input to the control unit .

The control module may sense gesture of the user by using the image captured by the image capturing unit not shown and the signal sensed from the sensing unit not shown respectively or in combination.

In particular the power supply unit may supply power to the control unit that may be realized in a System on Chip SoC form the display unit for image display and the audio output unit for audio output.

To this end the power supply unit may include a converter not shown that converts AC power to DC power. For example if the display unit takes the form of a liquid crystal panel having a plurality of backlight lamps it may further include an inverter not shown that is operable in a Pulse Width Modulation PWM manner for brightness change or dimming driving.

The remote controller transmits a user input to the user input interface . To this end the remote controller may use Bluetooth RF communication infrared IR communication UWB ZigBee and the like.

Also the remote controller may receive the video audio or data signal output from the user input interface to display the received signal or output sound or vibration.

The above described digital device may be a fixed type or mobile type digital broadcast receiver that can process ATSC mode or DVB mode digital broadcast signals.

The digital devices shown in are provided according to the exemplary embodiments of the present invention and the respective components thereof may be incorporated added or omitted depending on options of the digital device which is actually implemented. In other words two or more components may be incorporated into one component or one component may be divided into two or more components as occasion demands. Also the function performed by each block is intended for description of the embodiment of the invention and its detailed action or device does not limit the scope of the invention.

In addition the digital device according to the present invention may further include some components not illustrated in or may omit some components illustrated in as occasion demands. Unlike the embodiments illustrated in the digital device may receive and play content through the network interface or the external device interface without the tuner and the demodulator.

The digital device is an example of an image signal processor that performs signal processing of an image stored therein or an input image. Other examples of the image signal processor include a set top box that excludes the display unit and the audio output unit the aforementioned DVD player a blu ray player a game device and a computer as well as others.

Referring to the mobile terminal may include a wireless communication unit an A V input unit a user input unit a sensing unit an output unit a memory an interface a control unit and a power supply unit 

The wireless communication unit may include a broadcast receiving module a mobile communication module a wireless Internet module a Near Field Communication NFC module a Global Positioning System GPS module for example.

The broadcast receiving module may receive at least one of broadcast signals and broadcast associated information from an external broadcast management server through a broadcast channel. In this case the broadcast channel may include a satellite channel and a terrestrial channel for example.

The broadcast signals and or broadcast associated information received through the broadcast receiving module may be stored in the memory .

The mobile communication module transmits and receives a radio signal to and from at least one of a base station an external terminal and a server over a mobile communication network. Here the radio signal may include an audio call signal a video call signal or various types of data according to text and or multimedia message transmission and or reception.

The wireless Internet module may be a module for supporting wireless Internet access. The wireless Internet module may be built in or externally installed to the mobile terminal .

The NFC module may perform a near field magnetic induction communication. The NFC module may receive information associated with content from a media card when it accesses the media card within a predetermined distance i.e. when tagging the media card.

Here it may be used a near filed communication technology including Bluetooth RFID IrDA UWB ZigBee and the like.

The A V input unit receives an audio or video signal and may include a camera and a microphone for example.

The user input unit may generate key input data input by the user to control an operation of the terminal. To this end the user input unit may include a keypad a dome switch and a touch pad pressure capacitance for example. In particular in the case in which a touch pad and the display unit which will be described later form an interlayer structure it may be referred to as a touch screen.

The sensing unit may sense a current state of the mobile terminal such as an open or closed state of the mobile terminal a position of the mobile terminal or whether or not the user touches the mobile terminal for example. The sensing unit may generate a sensing signal to control an operation of the mobile terminal .

The sensing unit may include a proximity sensor a pressure sensor and a motion sensor for example. The motion sensor may sense for example a motion or position of the mobile terminal using an acceleration sensor a gyro sensor a gravity sensor and the like. In particular the gyro sensor is a sensor to measure angular velocity and may sense orientation rotating angle on the basis of a reference direction.

The output unit may include a display unit an audio output module an alarm module and a haptic module for example.

As described above in the case in which the display unit and the touch pad form an interlayer structure that will be referred to as a touch screen the display unit may also serve as not only an output device but also an input device that allows the user to touch input information.

The audio output module may output audio data received from the wireless communication unit or stored in the memory . The audio output module may include a speaker a buzzer and the like.

The alarm module outputs a signal to indicate generation of an event of the mobile terminal . For example the alarm module may output a signal in the form of vibration.

The haptic module generates various tactile effects that the user can perceive. A representative example of a tactile effect generated by the haptic module is vibration.

The memory may store a program for the processing and control of the control unit and may perform functions for temporarily storage of input output data for example a phonebook messages moving images and still images .

The interface unit may perform a role of interfacing to all external devices connected to the mobile terminal . The interface unit may allow a data reception from an external device a power delivery to each component in the mobile terminal or a data transmission from the mobile terminal to an external device.

The control unit typically controls the overall operations of the mobile terminal by controlling operations of the respective units. For example the control unit may perform control and processing associated with an audio call a video call data communication and the like. The control unit may include a multimedia playback module for playing a multimedia. The multimedia playback module may be hardware within the control unit or may be software separate from the control unit .

The power supply unit receives external and internal power and provides power required by various components under the control of the control unit .

The mobile terminal having the above described configuration may include a wire wireless communication system and a satellite based communication system and may be operable in a communication system capable of transmitting data through a frame or a packet.

The network interface may receive a request for a content list associated with a home screen of the image display device from the image display device and correspondingly may transmit the content list associated with the home screen to the image display device .

Alternatively the network interface may receive a request for a content list associated with the home screen of the image display device from the mobile terminal and correspondingly may transmit the content list associated with the home screen to the image display device .

Also the network interface may receive a request for transmission of content corresponding to a selected item from the image display device and correspondingly may transmit the content corresponding to the selected item to the image display device .

The storage unit may store authentication information for authentication with the image display device and may store device information on the image display device . In this case the authentication information or the device information may be sorted and stored on a per user basis of the image display device.

The storage unit may store authentication information for authentication with the mobile terminal and may store device information on the mobile terminal . In this case the authentication information or the device information may be sorted and stored on a per user basis of the mobile terminal .

The authentication information and device information on the image display device and the authentication information and device information on the mobile terminal may be linked with each other. For example the authentication information of the image display device and the authentication information of the mobile terminal may be identical on a per user basis.

The storage unit may store a content list associated with the home screen of the image display device on a per image display device basis or on a per user basis. Also the storage unit may store content within the corresponding content list.

In the case in which the image display device requests a content list associated with the home screen or in the case in which the image display device requests transmission of content corresponding a selected item within the content list the processor may control transmission of the content list or the corresponding content to the image display device in response to the corresponding request.

According to an exemplary embodiment of the present invention the control unit or may include a DEMUX a video processor an On Screen Display generator a mixer a Frame Rate Converter FRC and a formatter . Additionally although not shown the control unit or may further include an audio processor and a data processor.

The DEMUX demultiplexes an input stream. For example the DEMUX may demultiplex an input MPEG 2 TS into a video signal an audio signal and a data signal. Here the stream signal input to the DEMUX may be a stream signal output from the tuner the demodulator or the external device interface .

The video processor may process the demultiplexed video signal. For video signal processing the video processor may include a video decoder and a scaler .

The video decoder decodes the demultiplexed video signal and the scaler scales the decoded video signal so that the video signal can be displayed on the display unit or .

The video decoder may operate based on various standards. For example the video decoder may function as an MPEG 2 decoder in the case in which the video signal is an MPEG 2 encoded video signal. Also the video decoder may function as an H.264 decoder in the case in which the video signal is a Digital Multimedia Broadcasting DMB or H.264 encoded signal.

The OSD generator generates OSD data autonomously or in response to a user input. For example the OSD generator generates data by which a variety of data is displayed as graphics or text on a screen of the display unit based on a control signal of the user input interface. The generated OSD data includes various data such as a UI screen of the digital device a variety of menu screens widgets icons and information on an audience rating for example.

The OSD generator may generate data by which subtitles are displayed for a broadcast image or EPG based broadcasting information.

The mixer may mix the decoded video signal processed by the video processor with the OSD data generated by the OSD generator and output the mixed signal to the formatter . As the decoded video signal is mixed with the OSD data an OSD may be overlaid on the broadcast image or the externally input image.

The FRC may change the frame rate of an input image. For example the FRC may change a frame rate of 60 Hz of an input image into a frame rate of 120 or 240 Hz according to an output frequency of the display unit. As described above a variety of methods to change the frame range may be used. In one example in the case in which the frame rate is to be changed from 60 Hz to 120 Hz the FRC may insert a first frame between the first frame and a second frame or a predicted third frame between the first and second frames. In another example in the case in which the frame rate is to be changed from 60 Hz to 240 Hz the FRC may insert three identical frames or three predicted frames between the first and second frames. It is also possible to bypass the FRC when frame rate conversion is not performed.

The formatter changes the output of the FRC to suit the output format of the display unit. For example the formatter may convert a received signal into an RGB data signal. The RGB signal may be output in the form of a Low Voltage Differential Signal LVDS or mini LVDS. Also in the case in which the FRC outputs a 3D video signal the formatter converts the 3D video signal into a 3D signal to suit the output format of the display unit thereby assisting a 3D service via the display unit.

The audio processor not shown of the control unit or may process the demultiplexed audio signal. For audio signal processing the audio processor not shown may be configured to process a variety of formats. For example in the case in which the audio signal is encoded into an MPEG 2 MPEG 4 MPEG Surround AAC HE AAC AC 3 and BSAC format the audio processor not shown may include corresponding decoders to process the respective encoded signals.

The audio processor not shown within the control unit or may also adjust the base treble and volume of the audio signal.

The data processor not shown within the control unit or may process the demultiplexed data signal. For example in the case in which the demultiplexed data signal is an encoded data signal the data processor may decode the encoded data signal. Here the encoded data signal may include EPG information which includes broadcast information specifying the start time end time etc. of scheduled broadcast programs of each channel.

The control unit or shown in is given by way of example and other components may be added or some of the illustrated components may be omitted according to the needs of those skilled in the art.

A platform for the image display device according to the embodiment of the present invention may have OS based software to implement the above described various operations.

Referring first to the platform for the image display device according to the embodiment of the present invention is of a separate type. The platform may be designed separately from a legacy system platform and a smart system platform . An OS kernel may be shared between the legacy system platform and the smart system platform .

The legacy system platform may include a stack of a driver middleware and an application layer on the OS kernel . The smart system platform may include a stack of a library a framework and an application layer on the OS kernel .

The OS kernel is the core of an operating system. When the image display device is driven the OS kernel may be responsible for operation of at least one of control of hardware drivers security protection for hardware and processors in the image display device efficient management of system resources memory management hardware interfacing by hardware abstraction multi processing and scheduling associated with multi processing. Meanwhile the OS kernel may further perform power management.

The hardware drivers within the OS kernel may include for example at least one of a display driver a Wi Fi driver a Bluetooth driver a USB driver an audio driver a power manager a binder driver and a memory driver.

The hardware drivers within the OS kernel may be a driver for hardware devices within the OS kernel . The hardware drivers may include a character device driver a block device driver and a network device driver. The block device driver may need a buffer for buffering data on a per block basis because data is transmitted on a per block basis. The character device driver may not require a buffer since data is transmitted on a per basic data unit basis that is on a per character basis.

The OS kernel may be implemented based on any of various Oss such as Unix Linux Windows etc. The OS kernel may be a general purpose open kernel which can be implemented in other electronic devices.

The driver is interposed between the OS kernel and the middleware . A long with the middleware the driver drives devices for operation of the application layer . For example the driver may include a driver s for a microcomputer a display module a Graphics Processing Unit GPU an FRC a General Purpose Input Output GPIO pin a HDMI a System Decoder SDEC or DEMUX a Video Decoder VDEC an Audio Decoder ADEC a Personal Video Recorder PVR and or an Inter Integrated Circuit I2C . These drivers operate in conjunction with the hardware drivers of the OS kernel .

In addition the driver may further include a driver for the remote controller especially a 3D pointing device that will be described below. The driver for the 3D pointing device may be located in the OS kernel or the middleware instead of the driver .

The middleware may be located between the OS kernel and the application layer . The middleware may mediate between different hardware devices or different software programs for data transmission and reception between the hardware devices or the software programs. Therefore the middleware can provide standard interfaces support various environments and enable interaction between tasks conforming to heterogeneous communication protocols.

Examples of the middleware in the legacy system platform may include Multimedia and Hypermedia information coding Experts Group MHEG and Advanced Common Application Platform ACAP as data broadcasting related middleware PSIP or SI middleware as broadcasting information related middleware and DLNA middleware as peripheral device communication related middleware.

The application layer on the middleware i.e. the application layer in the legacy system platform may include for example UI applications associated with various menus in the image display device. The application layer on top of the middleware may allow editing and updating over a network by user selection. Through use of the application layer the user may enter a desired menu among various user interfaces by manipulating the remote controller while viewing a broadcast program.

The application layer in the legacy system platform may further include at least one of a TV guide application a Bluetooth application a reservation application a Digital Video Recorder DVR application and a hotkey application.

In the smart system platform the library is positioned between the OS kernel and the framework forming the basis of the framework . For example the library may include Secure Socket Layer SSL a security related library WebKit a Web engine related library c library libc and Media Framework a media related library specifying for example a video format and an audio format. The library may be written in C or C . Also the library may be exposed to a developer through the framework .

The library may include a runtime with a core Java library and a Virtual Machine VM . The runtime and the library form the basis of the framework .

The VM may be a virtual machine that enables concurrent execution of a plurality of instances that is multi tasking. For each application of the application layer a VM may be allocated and executed. In this case for scheduling or interconnection between the plurality of instances the binder driver not shown of the OS kernel may be operated.

In the smart system platform the framework includes programs on which applications of the application layer are based. The framework is compatible with any application and may allow component reuse movement or exchange. The framework may include supporting programs and programs for interconnecting different software components. For example the framework may include a resource manager an activity manager related to activities of applications a notification manager and a CP for abstracting common information between applications. This framework may be written in Java.

The application layer on top of the framework includes a variety of programs that can be executed and displayed in the image display device. The application layer may include for example a core application that provides at least one of e mail a Short Message Service SMS calendar map or browser functions. The application layer may be written in Java.

In the application layer applications may be categorized into user undeletable applications stored in the image display device or user deletable applications that are downloaded from an external device or a network and stored in the image display device so as to be freely installed or omitted by the user.

Using the applications of the application layer a variety of functions such as an Internet telephony service a VOD service a Web album service a Social Networking Service SNS a Location Based Service LBS a map service a Web browsing service and an application search service may be performed through network access. In addition other functions such as gaming and schedule management may be performed by the applications.

Referring next to a platform for the image display device according to another embodiment of the present invention is of an integrated type. The integrated type platform may include an OS kernel a driver middleware a framework and an application layer .

The integrated type platform shown in is different from the separate type platform shown in in that the library shown in is deleted and the application layer is included as an integrated layer. The driver and the framework correspond to the driver and the framework of respectively.

The library of may be incorporated into the middleware of . That is the middleware may include both the legacy system middleware and the image display device system middleware. As described above the legacy system middleware includes MHEG or ACAP as data broadcasting related middleware PSIP or SI middleware as broadcasting information related middleware and DLNA middleware as peripheral device communication related middleware and the image display system middleware includes SSL as a security related library WebKit as a Web engine related library libc and Media Framework as a media related library. The middleware may further include the above described runtime.

The application layer may include a menu related application a TV guide application and reservation application for example as legacy system applications and e mail SMS a calendar a map and a browser for example as image display system applications.

In the application layer applications may be categorized into user undeletable applications that are stored in the image display device and user installable or user deletable applications that are downloaded from an external device or a network and stored in the image display device.

The above described platform shown in may be used in a variety of general purpose electronic devices as well as the image display device .

Also the platform shown in may be loaded on the above described storage unit or control unit or on a separate processor not shown .

To perform a variety of operations according to embodiments of the present invention a variety of User Interface Devices UIDs that enable wire wireless communication with a digital device may be used as remote controllers.

Communication means for the remote controllers may be selected from among a variety of communication standards such as for example Bluetooth RFID IrDA UWB ZigBee and DLNA.

The UID may include a typical remote controller a magic remote controller and a remote controller consisting of a keyboard and a touch pad for example.

The magic remote controller may be equipped with a gyro sensor therein to detect trembling or rotation of the hand. That is the magic remote controller may move a pointer as the user moves the magic remote controller up and down side to side and back and forth which assists the user in easily performing a desired operation for example in easily controlling a channel or a menu.

In the remote controller consisting of a keyboard and a touch pad the keyboard facilitates easy input of text and the touch pad facilitates easy movement of the pointer and control in the expansion and reduction of pictures or moving images.

Hereinafter for example an EPG thumbnail image channel browser service according to the present invention will be described in more detail. To provide the aforementioned service a digital system or a service system hereinafter referred to as the digital system for example may be constituted of at least one device corresponding to a client and a server. Meanwhile in the following description service data refers to data for at least one of an EPG service a thumbnail image service and a channel browser service.

In the following description to assist understanding of the present invention and for convenience of explanation a service between the device and the server of the digital system will be described as being divided into an operation of transmitting service data from the digital device to the server and storing and processing the transmitted service data in the server an operation of transmitting the processed service data from the server to the digital device and an operation of processing the service data transmitted from the server between digital devices.

In particular examples of the operation of processing service data between the digital devices may include the case in which a mobile terminal controls a digital television receiver using service data or the case in which service data is shared via a Social Network Service such as Twitter and the like.

According to the present invention the digital device can provide a user friendly service close to an actual broadcasting environment by acquiring a greater quantity of various data than in the related art in relation to an EPG thumbnail image channel browser service in response to a user request. An example of this user friendly service is an Advanced EPG.

First the operation of transmitting service data from the digital device to the server and storing and processing the transmitted service data in the server and the operation of transmitting the processed service data from the server to the digital device will be described as follows.

As set forth herein the digital device may include for example a digital television receiver such as a smart TV and a mobile terminal such as a tablet PC or a smart phone. In the following description the digital device will be referred to as the digital television receiver or the mobile terminal as necessary. However it will be clearly understood that the present invention is not essentially limited to the above described digital television receiver or mobile terminal and is applicable based on the same or similar principle to other communicable electronic devices.

For example an operation of acquiring EPG thumbnail image channel browser service data using the digital device is as follows.

A digital device may provide at least one of an EPG service a thumbnail image service and a channel browser service for example as will be described below.

The digital device may receive EPG thumbnail image channel browser service data from a digital broadcast signal or from service information contained in the digital broadcast signal transmitted from a transmitter for example a broadcasting station configure a corresponding service based on the received service data and provide the service to the user.

Alternatively the digital device may receive EPG thumbnail image channel browser service data from a separate external server that is provided for provision of a particular service configure a corresponding service based on the received service data and provide the service to the user.

In particular in the case of the EPG service generally the digital device tunes to a particular channel in response to a user request such that the EPG service is acquired from service information contained in a digital broadcast signal received from the tuned channel. To this end the format of service information in a transmitter may change according to an ATSC mode or a DVB mode. For example DVB Terrestrial DVB T service information may contain Program Association Table PAT Program Map Table PMT Virtual Channel Table Service Description Table VCT SDT and Event Information Table EIT for example. In this case the digital device may autonomously configure the EPG service based on the received service data and provide the EPG service in response to a user request.

On the other hand in the latter case the external server may provide additional data that is not provided by the broadcasting station or various other service data about a prime time or a prime program.

As described above the digital device may receive the service data transmitted from the broadcasting station and or the external server and provide the received service data to the user.

Referring to the image display system according to the embodiment of the present invention may include an image display device a mobile terminal and a server .

The image display device may display an image more particularly a broadcast image. To this end the image display device may include a broadcast receiver as will be described below.

A home screen of the image display device may contain a broadcast image a content list and an application menu for example. The image display device may display the home screen.

The image display device may be connected to the mobile terminal or the server via a network. For example the image display device may receive for example a content list or an application program from the server and may transmit for example the received content list or application program to the mobile terminal .

The image display device may include the above described legacy system platform shown in or the above described smart system platform shown in .

Examples of the image display device may include a TV a monitor and a computer which can display a broadcast program.

The mobile terminal may perform wireless communication. To this end the mobile terminal may include a wireless communication unit as will be described below.

The mobile terminal may execute a remote control application capable of controlling the image display device remotely. That is the mobile terminal may execute a remote control mode with respect to the image display device .

The mobile terminal may be connected to the image display device or the server via a network. For example the mobile terminal may receive for example a content list and an application program from the image display device or the server . Also if a specific item within the content list is selected the mobile terminal may transmit information on the selected item to the image display device .

Examples of the mobile terminal include a cellular phone a smart phone a tablet PC a digital camera a camcorder and a portable printer.

The server may provide content. To this end the server may include a storage unit for storing content as will be described below.

The server may be connected to the image display device or the mobile terminal via a network. For example the server may receive for example a content list transmission request an application program transmission request and a content transmission request from the image display device or the mobile terminal . Also the server may transmit for example content and a content list to the image display device and transmit for example a content list and an application program to the mobile terminal .

The server may be any one of a content server for providing content a service server for providing a service and a network server for providing a network.

Referring to the digital system according to the embodiment of the present invention includes a digital device and a data server . The digital system may further include a broadcast station an external server and the like as necessary.

The digital device may be any one of a mobile terminal and a digital television receiver as an image display device.

The data server may be a server of a manufacturer of the mobile terminal or the digital television receiver.

As described above the digital device may receive EPG thumbnail image channel browser service data from a digital broadcast signal and or from service information contained in the digital broadcast signal transmitted from the broadcasting station and or the external server .

However in the case in which the EPG thumbnail image channel browser service data which can be acquired by the single digital device is acquired from a digital broadcast signal received by directly tuning to a corresponding channel via a tuner or is acquired from the external server generally service coverage per area is low less than 50 . Therefore the digital device has a difficulty in providing an EPG thumbnail image channel browser service that reflects an actual service environment. That is the single digital device may frequently fail to provide a user requested data service or a searched data service under the above described environment.

As will be described hereinafter according to the present invention the data server is built and used to address the problem in that it is actually difficult to appropriately reply to a user request for the EPG thumbnail image channel browser service using only the broadcasting station or the external server .

In the digital system according to the present invention the data server may serve to collect EPG thumbnail image channel browser service data from respective digital devices and to store process and manage the service data thereby ensuring that the digital devices can provide a higher quality of various services to the user.

Unlike digital devices of the related art according to the present invention as the data server can collect EPG thumbnail image channel browser service data acquired from a plurality of digital devices that have the same service list and or can couple or combine EPG thumbnail image channel browser service data acquired from the external server to transmit the processed service data to the respective digital devices. In this way an upgraded service can be acquired from an abundance of the latest high quality service data within a short time.

The collection processing storage and management of the service data between the digital device and the data server will hereinafter be described in more detail with reference to .

In the embodiment of the present invention as shown in the data server includes a control module an EPG processor and a thumbnail processor .

The digital device for provision of the EPG service according to the present invention performs a registration or authentication procedure by communicating with the data server .

For example the digital device initially transmits device information thereof to the data server A and receives a setting value from the data server based on the transmitted device information C . In the following description the setting value for example will be referred to as a service list set identifier.

The device information includes for example at least one of a device model device country language receiver type channel or service list and user ID.

The device model is for example a device model number or ID which is important for transmission of accurate information to prevent a possible service error because even products of the same manufacturer may have differences in options or support services according to device model.

The language indicates for example language used in the country of the device and may include language that can be supported via a caption function in the corresponding device.

The service list may mean a list of services or channels that can be accessed or used by the digital device through auto scan for example. The service list may further include service name or channel name for example.

The user ID is used to determine for example whether or not a corresponding user is a registered user and whether or not the corresponding user is a proper user via user authentication. The user ID may be an inherent value allotted per device or per manufacturer.

If the digital device performs auto scan as described above the digital device collects device information and transmits the device information to the data server . The device information may further include three identifiers hereinafter referred to as 3 ID in addition to the aforementioned information. The 3 ID may be transmitted in particular information such as the service list among the device information.

The 3 ID may include an original network identifier a transport stream identifier and a service identifier for example.

The 3 ID may serve as a reference that allows any one country to identify a device that can share the same service for example service data per receiver type. Alternatively identification of the service may be accomplished using a service name or channel name acquired from the EPG service data as well as the 3 ID.

For example the digital device may configure device information with a device country of UK a receiver type of MUX DVB T and a service list in a format of dvb 233a.2f.1 and transmit the configured device information to the data server . In this case 233a may mean an original network identifier that represents an area 2f may mean a transport stream identifier that represents MUX and 1 may mean a service identifier that represents a service.

Meanwhile the data server determines a group to which the corresponding digital device belongs based on the device information transmitted from the digital device . Here the 3 ID within the device information may be used for determination of the group. The data server transmits group identification information i.e. the aforementioned service list set identifier to the corresponding digital device based on the determined result.

In the following description the group will be referred to as a super set. The service list set identifier for example is information provided as the data server configures a super set to be managed together based on the country and receiver type information within the device information of each digital device and determines a super set to which a specific receiver is allocated.

The service list set identifier functions as identification information between the digital device and the data server .

In other words so long as there is no special circumstance after a single service list set identifier is allotted for information exchange between the digital device and the data server an appropriate process may be possible with only the allotted service list set identifier in the following procedures.

For example when updating EPG thumbnail image channel browser service data from each digital device to the data server or when transmitting the EPG thumbnail image channel browser service data from the data server to each digital device collection processing and management of all data may be performed using or based on the service list set identifier.

In the present invention the service list set identifier is a value for identifying a bundle of service lists i.e. super sets if the data server manages the EPG thumbnail image channel browser service data on a per service list basis. In general as described above two types of the device information i.e. the country and receiver type information may constitute the super set. For example in the case of Europe if 3 ID is equally used in one country on a per receiver type basis the service lists may be regarded as the same service.

Referring to after the procedure A each digital device may transmit EPG service data including previously allotted 3 UD to the data server to update the EPG service data periodically or non periodically B .

In this case initial transmission of the EPG service data may be performed at the aforementioned procedure A for example.

The transmitted EPG service data may be configured by the digital device based on service information which includes the EPG thumbnail image channel browser service data within a digital broadcast signal transmitted from the broadcasting station .

As described above the service information which includes the EPG service data for example includes an event and VCT SDT associated with a service i.e. an EIT associated with a program in the case of DVB terrestrial.

In other words the digital television receiver extracts data for configuring EPG by parsing VCT SDT and EIT from the digital broadcast signal stores the extracted data in a storage unit reads the stored data in the aforementioned 3 ID format and transmits the read data and the aforementioned 3 ID i.e. the service list set identifier to the data server .

The data server may receive the EPG thumbnail image channel browser service data from each digital device and transmit the received data directly or after processing the received data. The data server may use the EPG thumbnail image channel browser service data transmitted from the external server when processing the data received from each digital device. However if the EPG thumbnail image channel browser service data from the external server collide with the EPG thumbnail image channel browser service data from each digital receiver during the processing procedure any one of the data from the external server and the data from each digital device based on SI information may be used. For example the data server may apply a weighted value to service data based on SI information transmitted from the broadcasting station that provides a program other than service data from the external server thereby prioritizing the service data from the broadcasting station when the aforementioned data collision occurs.

Hereinafter the procedure of processing the EPG service data in the data server will be described in more detail.

If the device information of each digital device is received at the aforementioned procedure A or B the control module transmits the received device information to the crawler module .

The crawler module configures a super set based on the device information of each digital device and returns an identifier of the configured super set i.e. a service list set identifier to the control module . Here instead of the crawler module the control module may configure a super set and produce a service list set identifier for the super set.

The control module returns the service list set identifier transmitted from the crawler module to each corresponding digital device.

Also if updated EPG service data is received from each digital device after the service list set identifier has been returned to the digital device the control module transmits the updated EPG service data to the crawler module .

The crawler module transmits the updated EPG service data of each digital device which has been input through the control module to the processing module .

In this case the crawler module may analyze for example an updated parameter from the updated EPG data of each digital device.

Also the crawler module may process the analyzed result on a per service list set identifier basis and transmit the analyzed result to the processing module together with the service list set identifier.

In this case although each digital device may transmit the EPG service data to the data server at the same time alternatively each digital device may transmit the EPG service data to the data server at different times.

In this case as a result of analyzing the EPG service data received from a specific digital device for example if the EPG service data has the same parameter as updated service data or service data received from another digital device at a previous time or of the EPG service data has a version lower than the previously data the crawler module may remove the EPG service data without transferring it to the processing module .

The crawler module may transmit the EPG service data to the processing module whenever the EPG service data is received from each digital device. However in this case since load may occur in the processing module a parameter updated at a sufficient level may be accumulated or may periodically be transmitted to the processing module whereby overall load of the server may be reduced.

The processing module receives the updated EPG service data of each digital device transmitted from the crawler module and stores the received EPG service data in the database directly or after processing the received EPG service data.

The processing module may receive the EPG service data from the external server periodically or non periodically. The EPG service data from the external server may be used to process the updated EPG service data of each digital device prior to storing the updated EPG service data.

The processing module sorts the EPG service data received from the crawler module and the external server on the basis of for example a previously set super set i.e. a service list set identifier.

The processing module processes the sorted EPG service data and stores the processed EPG service data in the database in a unit of the aforementioned super set.

For example translation and merge may be used for the processing procedure. The service list set identifier for later EPG data search and basic information required for channel change per broadcast standard may be added.

Each digital device has higher service coverage per area than the related art and thus can provide an EPG service optimal for an actual broadcasting environment in response to an EPG service request from the user. A procedure of providing the EPG service will be described hereinafter.

If an EPG request is received from the user the digital device transmits a search parameter to the data server together with the previously received service list set identifier to request the EPG service data 

In this case the search parameter may include for example query information start index startIndex information maximum result maxResults information category information and sort information in addition to the aforementioned device information.

In particular an EPG service may be set based on the category information for the aforementioned EPG service request. However if the category is set to all for example information on CP tap for example YouTube tap as well as real time tap may be received. In the case of the CP tap only Uniform Resource Locator URL may be provided.

The control module checks the request of the digital device and determines whether or the corresponding request is a request for the updated EPG service data.

If it is determined that the corresponding input is the EPG service request the control module transmits a search request to a search module not shown together with the search parameter.

The search module transmits the result of the analyzed search parameter to a search engine and the search engine searches for the database based on the transmitted search parameter. In this case the database is required to store a great quantity of data for a long time because the EPG service data may generally provide not only information of the day or current information but also information on the past and or the future for a predetermined period on the basis of the current time or date. However as will be described below in the case of thumbnail image service data that does not essentially need long time or large capacity storage a buffer or memory for temporary storage may be used.

The search engine receives the searched result from the database and transmits the received result to the search module. The search module analyzes the search result received from the search engine configures the analyzed result in a response format corresponding to the request and returns the response to the control module . In this case the returned response of the search module may be xml format for example.

The control module may transmit the EPG service data returned from the search module to the corresponding digital device alone or together with the service list set identifier.

The corresponding digital device parses the EPG service data received from the data server and configures an EPG screen from the parsed result to provide the configured EPG screen to the user. In this case the parsed EPG service data may be stored in the storage unit within the digital device or a cloud or a mobile terminal connected to the digital device.

Referring to an example illustrated at the left side may mean a digital device and an example illustrated at the right side may mean a data server .

In for example a procedure of updating EPG service data according to the present invention will hereinafter be described by exemplifying three digital devices with respect to the same service UK ENG DVB T.

The first digital device is associated with the service UK ENG DVB T and a service list to which the corresponding digital device is accessible i.e. an EPG service list may include for example six services of No. 1 dvb 233a.2f.1 No. 2 dvb 233a.2f.2 No. 3 dvb 233a.2f.3 No. 4 dvb 233a.3f.1 No. 5 dvb 233a.4f.1 and No. 6 dvb 233a.4f.2.

The second digital device is associated with the service UK ENG DVB T and a service list to which the corresponding digital device is accessible i.e. an EPG service list may include for example five services of No. 1 dvb 233a.2f.2 No. 2 dvb 233a.2f.3 No. 3 dvb 233a.3f.1 No. 4 dvb 233a.4f.1 and No. 5 dvb 233a.6f.1.

The third digital device is associated with the service UK ENG DVB T and a service list to which the corresponding digital device is accessible i.e. an EPG service list may include for example five services of No. 1 dvb 233a.2f.1 No. 2 dvb 233a.2f.2 No. 3 dvb 233a.2f.3 No. 4 dvb 233a.3f.1 and No. 5 dvb 233a.5f.1.

In in particular an update service of the first digital device is No. 2 service an update service of the second digital device is No. 3 service and an update service of the third digital device is No. 5 service.

The three digital devices and have the same service list set identifier. That is EPG service data of the three digital devices and belongs to a single super set.

The super set contains for example data of a total of eight EPG services. That is EPG service data may include eight services of No. 1 dvb 233a.2f.1 No. 2 dvb 233a.2f.2 No. 3 dvb 233a.2f.3 No. 4 dvb 233a.3f.1 No. 5 dvb 233a.4f.1 No. 6 dvb 233a.4f.2 No. 7 dvb 233a.5f.1 and No. 8 dvb 233a.7f.1.

The above description is one example of EPG service data that is received and updated from the respective digital devices belonging to the super set. In other words the respective digital devices belonging to the same super set for example may equally receive the EPG service data list within the super set from the data server .

For example the first digital device can access a total of six services. However if the first digital device requests EPG service data from the data server the data server responds and transmits data of eight EPG services within the super set to which the corresponding digital device belongs.

In this case the first digital device parses the response of the data server and configures an EPG from the parsed EPG service data to provide the EPG to the user.

However the first digital device may not include EPG service data with respect to an inaccessible service by filtering the EPG service data and may configure EPG service data with respect to only an accessible service to provide the EPG service data to the user via a screen.

For example the first digital device cannot access the services of No. 7 dvb 233a.5f.1 and No. 8 dvb 233a.7f.1 among the EPG service data within the response received from the data server and therefore filtering the inaccessible services prior to providing the EPG service data may increase user convenience. However even the filtered service for example may be used by the corresponding digital device to configure an EPG service if it is a service or content associated with other accessible services.

Even in the case of the second digital device and the third digital device an EPG service may be provided in the same manner as the above described processing procedure of the first digital device .

The super set is exemplified herein only for convenience of explanation and may correspond to an example obtained by updating EPG service data processed through the control module the crawler module and the processing module within the above described data server and thereafter searching the updated EPG service through the search module and the search engine.

In addition in the course of transmitting the updated EPG service data to the server or separately from this course the digital device may periodically or non periodically transmit or receive information on a viewer rating associated with a channel or program that the corresponding digital device currently shows together with the 3 ID.

In this way the data server may additionally receive information on a viewer rating with respect to EPG service data together with the EPG service data of each digital device and provide the additional information together or separately from provision of the EPG service which results in a differentiated service as compared to the related art.

The above description generally exemplifies and explains a DVB mode. However the present invention is not limited to the above described DVB mode and for example may be equally applied to an ATSC mode. In the case of the ATSC mode a channel name and or a program name may be additionally necessary due to differences in a broadcasting mode. Here the channel name for example may have the same function as the aforementioned 3 ID.

Accordingly the server configures a super set on the basis of a channel name of each digital device adds service list set identifier information on the configured super set maps the super set with the digital device based on the added information and transmits the mapped result to the corresponding digital device. The procedure of updating the EPG service data or the procedure of searching EPG service data in response to the EPG service request from the digital device are completely the same as the above description and a detailed description thereof will be omitted hereinafter. However in the case of North America if collision of EPG data provided by a variety of sources occurs under the condition of a channel name reference any one EPG data may be selected or all collided EPG data may be transmitted to the digital device so that the corresponding digital device filters the EPG data based on information on a local area.

Hereinafter channel browser service data will be described in the same manner as the service EPG service data. Since a basic processing concept of channel browser service is similar to that of the EPG service data a detailed description thereof is replaced by the above description and the following description is centered only on context corresponding to a channel browser.

In the case of the channel browser data required to configure the channel browser may be extracted from service information contained in a digital broadcast signal transmitted from a broadcasting station or may be received from a channel browser server such as an EPG server.

However respective digital devices have different various channel coverages and realistically the channel browser server has difficulty in providing proper channel browsers for all channels which a corresponding digital device can access due to limited channel coverage. Thus although some channels may provide thumbnail images if the user requests for a channel browser some channels may show only a black screen. This may cause dissatisfaction with the digital device and the broadcast service.

In consideration of the above described circumstance the above described broadcasting system as shown in may also be used to process the channel browser in a method similar to the above described EPG service providing method.

More specifically the digital device serves as a channel browser for a currently tuned channel and captures a current screen as a back channel to thereby store a thumbnail image even if no user request is present.

The captured thumbnail image for the particular channel may be configured for example into a 3 ID format and be transmitted to the data server together with or separately from the above described updated EPG service data.

The thumbnail image of a screen with respect to the channel may be captured in various ways. For example when channel change occurs a corresponding screen may be immediately captured and a current screen may be periodically captured. In this case the digital device may select only the latest stored thumbnail image among captured images of respective channels provided therein and treats the selected thumbnail image as a representative thumbnail image for the corresponding channel to transmit the thumbnail image as channel browser update data to the data server.

The control module within the data server may transmit the updated channel browser data to the crawler module and in turn the crawler module may analyze the channel browser data to transmit the analyzed result to the processing module.

The processing module processes the updated channel browser data for the respective channels on the basis of each service list set identifier by combining the updated channel browser data with for example additional channel browser data provided by the channel browser server. The processed channel browser data is stored in the database for example separately from the EPG service data.

In this case the channel browser service data includes for example thumbnail images and therefore URL addresses required to access the corresponding thumbnail images are stored in the database together with the thumbnail images.

In the case of the stored channel browser service data if a user request for a channel browser occurs in the future similar to the case of processing the EPG service data as described above a search parameter for search of the channel browser is transmitted to the data server and in turn the control module within the data server transmits the search parameter to the search module so that the search module analyzes the search parameter and drives the search engine based on the analyzed result.

The search engine for example searches the database based on the search parameter transmitted from the search module collects data associated with the corresponding channel browser and transmits the collected data to the search module.

In response to a user request the search module configures a response including an URL to access the thumbnail image of each channel from the collected channel browser data and transmits the response to the corresponding digital device through the control module.

The digital device reads each channel and the URL of the corresponding channel by parsing the aforementioned response. Then the digital device extracts the thumbnail image for the corresponding channel by accessing the read URL and provides a channel browser to the user.

According to the present invention channel coverage of each digital device may be increased and advanced EPG with an abundance of metadata per program and a channel browser may be provided.

The authentication module determines whether or not the digital device has uploading authority generates an authentication signal depending on the determined result and transmits the signal to the control module and or the program thumbnail crawler module. In this case if it is determined based on the authentication signal transmitted from the authentication module that the digital device has no uploading authority the control module may generate a control signal for controlling access of the corresponding device and transmit the control signal to the corresponding digital device. On the contrary if it is determined based on the authentication signal transmitted from the authentication module that the digital device has uploading authority the control module may transmit a control signal that allows access of the corresponding device and contains a message indicating authentication success to the corresponding digital device.

The program thumbnail crawler module may be activated according to the authentication signal transmitted from the authentication module and may perform the same crawling function as the above described EPG crawler module with respect to the thumbnail image transmitted from each digital device.

In this case like the above described EPG processor the thumbnail processor may build the database to store the thumbnail image processed by the program thumbnail crawler module. Alternatively unlike the above described EPG processor the thumbnail processor may temporarily store the thumbnail image processed by the program thumbnail crawler module in a buffer or memory without building the database . The buffer or memory for example may be located inside or outside of the thumbnail processor.

The processing module for example may process EPG service data processed by the EPG crawler module and or may combine and process the EPG service data with EPG service data collected by the external server . Also the processing module may process even the program thumbnail image service data in the same manner as the EPG service data to transmit the program thumbnail image service data to the thumbnail processor or to store the program thumbnail image service data in the database . The processing module may process input data on the basis of various references e.g. may add identification information and store the data in the database or transmit the data to the corresponding processor.

Referring to in the digital system according to the present invention for example EPG service data channel browser data and thumbnail images may be processed in different modules.

Transmission of data from the digital device to the data server may be performed on a per service data basis. As shown in if the respective categories of service data are previously collected and transmitted to the data server the control module within the data server may sort the service data into respective categories and transmit each category of the service data to the corresponding module.

In the present invention each digital device transmits service data stored therein to the data server and in turn the data server processes the service data transmitted from each digital device as well as service data separately collected via an external server and thereafter transmits the processed data upon receiving a request from each digital device whereby a greater quantity of higher quality service data may be provided.

In this case it is unnecessary to provide an infinite number of digital devices that are connected to the data server of the digital system and transmit service data to the data server for example. This is because if an infinite number of digital devices respectively transmit service data stored therein to the data server data traffic may occur and cause deterioration in service quality and the data server has needs for high performance and high capacity which results in cost burden. In addition this is because data transmitted from the respective digital devices that communicate with the data server are not completely different from one another and may overlap to some extent. In this case the digital system may be understood transmission of service data from the digital devices to the data server and transmission of the processed service data from the data server to the respective digital devices from different viewpoints. In other words it is assumed that there are 100 digital devices and at least one data server connected to one another via a digital system. In this case the digital devices may be controlled such that only 50 digital devices transmit service data to the data server but the 100 digital devices receive processed service data from the data server so as to provide a corresponding service. This control mode may be appropriately determined to provide a differentiated service in terms of data traffic cost and the like.

In addition the data server within the digital system may transmit a control signal to each digital device to assist the digital device in setting authority to transmit service data to the data server a transmission cycle and the like. This control mode as described above may be appropriately determined in terms of data traffic the capacity of the server and the like.

For example it is assumed that a digital device A transmits EPG thumbnail image channel browser service data to the data server by a cycle of 10 seconds.

Basically the data server determines whether or not the corresponding digital device A has transmission authority. If the digital device A has transmission authority the data server determines a service list set identifier of the corresponding digital device A and then determines whether or not another digital device having the same service list set identifier has already transmitted the same service data as that transmitted from the digital device A to the data server.

If it is determined that the service data received from the digital device A overlaps with the previously received service data from another digital device having the same service list set identifier the data server may fix a service data transmission cycle to the corresponding digital device A but may control a data transmission cycle of another digital device. For example if the data is transmitted from the digital device A at an interval of 10 seconds from a predetermined time the data server may control the transmission cycle of another digital device to transmit the data at an interval of 10 seconds from a time delayed by from the predetermined time. Alternatively the data server may transmit a control signal to change a service data transmission cycle. For example if the previous transmission cycle is 10 seconds the data server may change the transmission cycle to 11 seconds. Here may be for example 1 to 3 seconds.

In the above described case the data server may transmit a rejection message as well as the control signal to allow the corresponding control signal to be identified and processed in the digital device. Thus if the rejection message is received the digital device may extract the control signal transmitted from the data server decode the extracted control signal and transmit the service data to the data server in the same manner after resetting a transmission time or transmission cycle.

Referring to the digital system may include a digital device and a data server . The data server may receive service data associated with the present invention by individually communicating with an external server .

Hereinafter a detailed description of the same configurations as those in will be omitted and only differences will be described.

In particular the digital system shown in has a slight difference in terms of configuration of the data server from the above described digital system shown in .

More specifically basically the data server shown in includes an EPG service data processor and a thumbnail image service data processor in the same manner as that shown in but has differences in the configurations of the respective processors.

For example the EPG service data processor shown in may further include a first analysis module and an EPG provider module in addition to the above described crawler module .

If the digital device transmits device information or updated service data together with or separately from area information or position information on the digital device for example the first analysis module receives the transmitted data from a control module provided in the data server . Here the position information for example may be at least one of GPS information an identifier of the area to which the corresponding digital device belongs e.g. an original network identifier and a Zone Improvement Plan ZIP code of the area to which the corresponding digital device belongs. The first analysis module analyzes the received position information on the digital device . The analyzed data for example may be the identifier of the area to which the corresponding digital device belongs GPS information or the ZIP code. That is the first analysis module extracts at least one of the GPS information then original network identifier and the ZIP code as the position information on the corresponding digital device and transmits the extracted position information to the EPG provider module .

The EPG provider module may extract EPG service data based on the position information on the digital device received from the first analysis module by accessing a database in which the EPG service data is stored and may again transmit the EPG service data to the digital device through the control module . When extracting the service data the EPG provider module may determine proper service data by analytically comparing the received position information on the digital device with device information that is received through another digital device and is used for grouping. This is applicable in the same principle even to the case of a program thumbnail image that will be described hereinafter. For example if the position information is the original network identifier coincident groups may be searched by comparing original network identifiers of respective groups with one another. On the other hand if the position information is the ZIP code an original network identifier of the area corresponding to the ZIP code is extracted and a group corresponding to the ZIP code may be searched. In the case of GPS information similarly a group corresponding to the GPS information may be searched from the original network identifier of the area corresponding to the GPS information.

The aforementioned position information for example may be continuously changed rather than providing information on a fixed position if the digital device is a mobile terminal. This is because EPG service data may be changed on a per position basis.

Similarly in the case of a thumbnail image the thumbnail processor receives the position information on the digital device from the corresponding digital device. A second analysis module analyzes the received device position information and thereafter transmits at least one of the original network identifier and the ZIP code to a program thumbnail provider module .

The program thumbnail provider module accesses a database or a buffer or memory incorporated therein based on the original network identifier and or the ZIP code extracts service data having a service list set identifier coincident with the original network identifier and or the ZIP code and transmits the extracted service data to the corresponding digital device .

In the case in which the digital device is a mobile terminal for example as shown in if the mobile terminal transmits area information thereof to the server to receive service data such as previously stored EPG data the data server may transmit the EPG service data to the corresponding mobile terminal based on the received area information. In this case the data server may select an optimal super set based on the received area information extract service data of the selected super set and transmit the extracted service data to the mobile terminal. However since the mobile terminal may have change in the position information thereof the super set may be again determined and selected if the area information differs from previous area information.

Referring to for example a data server may be equal to the data server described with reference to or .

However shows transmission of service data from the data server to each digital device other than data transmission from the digital device to the data server.

In particular shows the case of transmitting thumbnail image service data included in the format of EPG service data.

Alternatively as described above EPG service data and thumbnail image service data may be respectively configured into single service data and be transmitted separately.

Referring to in the digital system three digital devices and transmit EPG thumbnail image channel browser service data to a data server .

The data server collects processes and stores the service data. Then if the digital device requests the service data the data server transmits the stored service data to the corresponding digital device. In this case for example the digital device may be at least one of three digital television receivers and and two mobile terminals and as shown in .

Although the above description exemplifies the case in which the digital device periodically or non periodically transmits service data stored therein to the data server and receives processed service data from the data server exemplifies the case in which a device that transmits service data may differ from a device that receives the service data. In other words as shown in service data transmitted from the aforementioned three digital television receivers and to the data server may be transmitted from the data server to the mobile terminals and .

Assuming the case in which one digital device receives latest processed service data from a data server as described above with reference to exemplifies the concept of expanding service from the corresponding digital device to another digital device that is not registered in or connected to the data server and thus has no authority.

Referring to it is assumed that a mobile terminal receives latest processed EPG thumbnail image channel browser service data from a data server.

The mobile terminal may transmit the received service data to a digital device to which the mobile terminal is connectable via a wired wireless network to which the mobile terminal belongs or is connectable.

A variety of wired wireless communication means such as various wired wireless communication networks and an N screen for example may be constructed for transmission reception of data between the mobile terminal and the digital television receiver .

In this case the mobile terminal or the digital television receiver may be connected to the broadcasting station and or the external server as shown in thereby being capable of receiving service data.

For example the situation in which a digital television receiver is present at home and a passerby who is present within a home network range accesses the network using a portable terminal thereof and attempts to control the digital television receiver is problematic.

Accordingly to prevent occurrence of the aforementioned situation it can be contemplated that inter authentication between digital devices is performed such that only a digital device that has proper authority is connectable to the other digital device and can perform transmission and reception of service data after being coupled with the other digital device.

As shown in if the mobile terminal having service data transmits security authentication information represented as xpto25 to the digital television receiver that belongs to a network the digital television receiver decodes the authentication information and transmits a message for access permission to the corresponding mobile terminal if an owner of the mobile terminal has proper authority or displaying the message on a screen of the digital television receiver .

The security authentication information for example may be generated and transmitted from the data server that transmits the processed service data and may be generated from the mobile terminal .

A variety of authentication algorithms may be used in relation to generation of the security authentication information .

Referring again to there is illustrated a screen of the digital television receiver that is controlled based on service data for example EPG service data received from the mobile terminal that is connected to the digital television receiver .

A digital system prepared based on the expanded concept of the above description will be configured as shown in .

Referring to a first digital device mobile terminal transmits service data stored therein to a data server and receives latest processed service data stored in a database from the data server .

The first digital device may transmit the latest processed service data received from the data server to a second digital device digital television receiver via communication with the first digital device .

Referring to for example the first digital device may receive service data from the second digital device and may transmit the received service data to the data server to enable processing of the service data.

In assuming that a digital device is a mobile terminal for example the mobile terminal may directly receive service data from a data server or may indirectly receive service data from another digital device that has received the service data from the data server. Then the mobile terminal may output detailed information in response to a user request by decoding the received service data as shown in .

In this case as shown in for example a screen of the mobile terminal may contain buttons used to select a previous program item and a next program item . Also program information containing a thumbnail image may be displayed on the center of the screen .

The mobile terminal for example may control another digital device connected thereto. Thus the screen of the mobile terminal may further contain a TV display item that allows a selected program to be displayed on a digital television receiver and an SNS sharing item that allows a selected program to be shaped via an SNS.

For example when using an EPG thumbnail channel browser service in the mobile terminal having a limited screen size transmitting the corresponding service data to a digital device having a larger screen size may provide viewer convenience. Alternatively when the service data along with text data is shared via Twitter expanded service coverage may be accomplished.

Referring to it can be appreciated that a single digital device can control at least one of other digital devices and using service data received from a data server or the other digital devices.

For example if the user receives service data from the data server using a mobile terminal the user can control the other digital devices and so long as the mobile terminal of the user has control authorities for the other digital devices and . In this case the mobile terminal of the user may function as a remote controller.

In addition the mobile terminal may control only one digital device and in turn the digital device may control the other digital device. Alternatively the mobile terminal may directly control both the digital devices.

For example the mobile terminal transmits a device identifier to a digital device A in a HyperText Transfer Protocol HTTP manner and requests a key for data encryption.

The digital device A transmits a response code and an encryption key in response to the request from the mobile terminal .

The mobile terminal encrypts a service displayed on a current screen or at least one of three program identifiers including an original network identifier a TS identifier and a Service identifier and a service name using the encryption key transmitted from the digital device A and thereafter transmits the encrypted data to the digital device A .

The digital device initially determines whether or not a current channel is available by decoding received channel information. If it is determined that the channel is available the digital device plays a corresponding broadcast. However if it is determined that the channel is not available the digital device may transmit a response containing a code to inform that the corresponding digital device cannot play the broadcast to the mobile terminal . Thus if the mobile terminal receives the response containing a playback not possible code from the corresponding digital device the mobile terminal may be connected to the other digital device instead of the corresponding digital device or may communicate with the other digital device to inquire and request broadcast playback in the above described manner after changing a service or program.

The digital device A may communicate with the other digital device connected thereto even when it cannot play a broadcast as well as when it can play a broadcast so as to inquiry as to whether or not playback is possible or so as to process playback.

As described above the mobile terminal and the digital television receiver can exchange functions thereof. In addition to transmission reception of service data and service control between the mobile terminal and the digital television receiver transmission reception of service data and service control between two mobile terminals or between two digital television receivers are possible.

Each digital device receives a service list set identifier to which the corresponding digital device belongs from the data server based on the transmitted device information S .

Each digital device transmits EPG thumbnail image channel browser service data to the data server S .

The control module within the data server sorts the service data transmitted from each digital device and transmits the sorted service data to the corresponding crawler module S . Also the control module analyzes service data transmitted from the analysis module and or position information on each digital device and transmits the analyzed results to the processing module S .

The processing module processes the service data by coupling or combining the service data received from each digital device with service data received from an external server and stores the processed service data in the database in a unit of service list set identifier or in a unit of super set. Here if the corresponding service data is thumbnail image data the service data may not pass through the processing module. In this case the service data may be temporarily stored in a buffer or a volatile memory provided in a separate module S .

The digital device transmits a search parameter to request the service data in response to a user request to the data server S .

If the data server receives the service data request from the corresponding digital device the data server determines whether or not the corresponding digital device has proper authority. If it is determined that the digital device has proper authority the control module transmits the search parameter to a search engine S .

The data server analyzes the search parameter and accesses the database or the corresponding buffer or memory based on the service list set identifier to search the service data S . Then the data server analyzes the searched service data and generates a message in response to the service data request S .

The data server transmits the generated service data to the corresponding digital device S and the corresponding digital device parses the transmitted service data. Then the digital device configures a service screen based on the parsed result and provides the configured service screen to the user S .

Here in the case in which the digital device is connected to the other digital device via a network or utilizes a social network service such as Twitter as described above the digital device may perform transmission reception of the service data without an authentication procedure.

According to the present invention the digital device may realize an improved EPG thumbnail image channel browser service in terms of quantity and or quality than the related art and may expand a service via inter communication with other digital devices or via a social network service thus satisfying needs for enhanced user convenience and the like.

In the above description the search module configures a response containing an URL required to access a thumbnail image of each channel using collected channel browsers in response to a user request and transmits the response to the corresponding digital device by way of the control module.

The digital device reads each channel and the URL of the corresponding channel by parsing the aforementioned response. Then the digital device extracts the thumbnail image for the corresponding channel by accessing the read URL thereby providing the extracted thumbnail image to the user.

Referring to the drawings the mobile terminal executes an application associated with the image display device S . For example in a state in which an application for remote control of the image display device is installed in the mobile terminal the corresponding application may be executed. The control unit of the mobile terminal executes the corresponding application.

Meanwhile it is preferable to install the application for remote control of the image display device prior to Operation S.

Next the mobile terminal determines whether or not the mobile terminal can access the image display device S . If the mobile terminal can access the image display device the mobile terminal is connected to the image display device S .

In the case of executing the application for remote control of the image display device the mobile terminal transmits a pairing signal to the image display device. As such the image display device receives the pairing signal from the mobile terminal S .

The image display device generates a pairing response signal in response to the received pairing signal and transmits the pairing response signal to the mobile terminal S . As such the mobile terminal receives the pairing response signal from the image display device.

The mobile terminal can be connected to the image display device via transmission of the pairing signal and reception of the pairing response signal.

On the other hand if the pairing response signal is not received within a predetermined time or if a signal level of the received pairing response signal is less than a predetermined value the mobile terminal may determine that the mobile terminal cannot access the image display device.

Alternatively if the pairing response signal is received within the predetermined time the mobile terminal may determine that the mobile terminal cannot access the image display device.

After pairing the mobile terminal can exchange data with the image display device through an RF frequency band. This pairing end state may mean that the mobile terminal and the image display device are connected to each other.

Meanwhile for connection to the mobile terminal the image display device may transmit at least one of device information or user information on the image display device authentication information for connection to the image display device or authentication information with respect to a server connected to the image display device to the mobile terminal via a network interface.

Thereby for connection to the image display device the mobile terminal may receive at least one of the device information or user information on the image display device authentication information for connection to the image display device or authentication information with respect to the server connected to the image display device via a wireless communication unit.

Transmission and reception of the device information for example may be performed during pairing or after completion of pairing. If the authentication information for connection to the image display device is received during pairing the mobile terminal may be connected to the image display device using the corresponding authentication information.

In the above description Operations S and S may correspond to Operations S and S of . Also Operations S and S of may correspond to Operations S and S of .

If the mobile terminal cannot access the image display device Operation and the following operations may be performed.

Next after pairing of the image display device and the mobile terminal is completed the image display device requests a content list associated with a home screen to the server S . The server receives the request for the content list associated with the home screen from the image display device S . Then the server transmits the content list associated with the home screen to the image display device S . As such the image display device receives the content list from the server S .

If pairing of the mobile terminal and the image display device is completed in a state in which a display unit of the image display device displays a home screen a control unit of the image display device may transmit the request for the content list associated with the home screen to the server via the network interface.

The server receives the content list request via the network interface. The content list request may be transmitted to a processor.

The processor may extract the content list stored in a storage unit and may transmit the content list to the image display device via the network interface.

To transmit the content list the server may receive for example the device information or user information on the image display device. The server may transmit a content list on a per image display device or user basis.

To enable transmission of the content list request and the content list in response to the content list request between the image display device and the server the image display device may transmit authentication information to the server. The server may transmit an authentication completion message to the image display device.

Meanwhile operations S and S may correspond to Operation S of and Operations S and S may correspond to Operation S of .

Next the image display device transmits the content list associated with the home screen of the image display device to the mobile terminal S . The mobile terminal receives the content list associated with the home screen of the image display device from the image display device or the server while being connected to the image display device S . The mobile terminal displays the received content list S .

Since the mobile terminal is connected to the image display device the mobile terminal may perform a remote control mode associated with an image displayed on the image display device.

In one example if the image displayed on the image display device is a broadcast image of a predetermined channel a display unit of the mobile terminal may display at least one of a channel change menu a volume adjusting menu a screen quality adjusting menu and the like of the corresponding broadcast image.

In another example if the image displayed on the image display device is the home screen of the image display device as shown in the display unit of the mobile terminal may display for example a remote control screen containing a broadcast image item a content list item and an application menu item associated with the home screen.

That is the control unit of the mobile terminal may receive information on the image displayed on the image display device under the remote control mode and may configure the remote control screen based on the corresponding image information.

If the content list item among a plurality of items shown in is selected the mobile terminal may receive the content list associated with the home screen of the image display device from the image display device or the server via the wireless communication unit. The mobile terminal may display the received content list on the display unit.

Meanwhile operations S and S may correspond to Operation S of and Operation S may correspond to Operation S of .

Next the mobile terminal determines whether or not selection of a specific item included in the displayed content list is input S . If the specific item is selected the mobile terminal transmits information on the selected item to the image display device S . The image display device receives the input of selection of the specific item S .

If touch on a specific item included in the displayed content list is input the mobile terminal selects the corresponding item. The selected item may be focused and displayed so as to differentiable from other items.

The control unit of the mobile terminal controls transmission of information on the selected item to the image display device via the wireless communication unit.

The network interface of the image display device receives the information on the selected item to the control unit.

Meanwhile operations S and S may correspond to Operation S of and Operation S may correspond to Operation S of .

Next the image display device transmits a content transmission request corresponding to the selected item to the server S . The server receives the content transmission request S . The server transmits content corresponding to the content transmission request to the image display device S . The image display device receives content from the server S . The image display device plays the corresponding content and displays the content on the display unit S .

In response to the content transmission request the server may extract corresponding content stored in the storage unit or may receive content stored in another server via a network. The server may transmit the extracted or received content to the image display device via the network interface.

The image display device receives the corresponding content via the network interface and transmits the content to the control unit. The control unit performs for example demultiplexing decoding and scaling of the received content and may play the content. The control unit may control display of the played content image on the display unit.

In this way it is possible to easily play and display content corresponding to an item selected by the user on the image display device using the mobile terminal which results in enhanced user convenience.

Meanwhile operations S and S may correspond to Operation S of Operations S and S may correspond to S of and Operation S may correspond to Operation S of .

If the mobile terminal is not connected to the image display device for example if the user using the mobile terminal is out as described above Operation S and the following operations may be performed.

First the control unit of the mobile terminal determines whether or not information on the image display device is stored in the memory of the mobile terminal S .

In particular the control unit of the mobile terminal determines whether or not authentication information with respect to the server connected to the image display device is stored in the memory.

Prior to the aforementioned operation if the mobile terminal and the image display device are connected to each other the mobile terminal may receive at least one of device information on the image display device authentication information to permit connection to the image display device or authentication information with respect to the server connected to the image display device. In this case the memory of the mobile terminal may store the received information.

If the authentication information with respect to the server connected to the image display device is stored in the memory the mobile terminal is connected to the server using the authentication information S . The mobile terminal receives the content list associated with the home screen of the image display device from the server S . Then the mobile terminal displays the received content list S .

The mobile terminal can be connected to the server using the authentication information with respect to the server connected to the image display device.

On the other hand the mobile terminal may transmit a request for the content list associated with the home screen. Thus in response to the request the server transmits the content list associated with the home screen to the mobile terminal.

The mobile terminal may transmit information that indicates the mobile terminal is not connected to the image display device to the server. In this case the server may transmit a default content list among content lists associated with the home screen to the mobile terminal.

The mobile terminal may transmit device information or user information on the mobile terminal to the server. In response to the transmitted information the server may transmit a preset content list on a per device or user basis to the mobile terminal.

Next if a specific item included in the content list is selected S the mobile terminal stores information on the selected item S .

If a touch on the specific item in the displayed content list is input the mobile terminal selects the corresponding item. The selected item may be focused and displayed so as to be differentiable from other items.

Since the mobile terminal is not connected to the image display device the control unit of the mobile terminal controls storage of the information on the selected item in the memory of the mobile terminal.

The memory may store a bookmark list containing the user selected item of the content list. Also the control unit of the mobile terminal extracts the bookmark list if display of the stored list is input and controls display of the extracted bookmark list on the display unit.

In this way in the case in which the mobile terminal is not connected to the image display device the mobile terminal can select a desired item of the content list and store the selected item.

The operating method of the server shown in is similar to the operating method of the server shown in except that the content list request is received from the mobile terminal other than the image display device.

That is the server receives a request for the content list associated with the home screen from the mobile terminal S . The server transmits the content list associated with the home screen to the mobile terminal S .

As described above the mobile terminal may be directly connected to the server without the image display device interposed therebetween. In particular if the mobile terminal and the image display device are not connected to each other the mobile terminal may be directly connected to the server without the image display device interposed therebetween.

The mobile terminal may be directly connected to the server using the authentication information with respect to the server.

The mobile terminal may transmit the request for the content list associated with the home screen. In response to the request the server transmits the content list associated with the home screen to the mobile terminal.

On the other hand the mobile terminal may transmit device information or user information on the mobile terminal to the server. In response to the transmitted information the server may transmit a preset content list on a per device or user basis to the mobile terminal.

Next the server receives a content transmission request corresponding to the selected item from the image display device S . The image display device transmits content corresponding to the selected item S .

Operations S and S correspond to Operations S and S of and a description thereof will be omitted hereinafter.

The home screen shown in may be set to an initial screen when power is turned on or when switching from a standby mode to an on mode or may be set to a basic screen by selection of a local key not shown or a home key of a remote controller.

In order to implement the home screen a smart system platform may be installed in a processor of the control unit of the image display device or in a separate processor.

For example the smart system platform may include an OS kernel a library on an OAS kernel a framework and an application layer. Under the smart system platform a download an installation an execution and a deletion of an application may be freely performed.

The home screen of may be broadly divided into a live image area for displaying a live image a card object area including card objects and representing items from various sources e.g. CPs or applications on a per list basis and an application menu area including a shortcut menu of an application item.

In the application menu area is displayed on the lower side of the home screen . Also log in and log out items may further be displayed.

In this case in the live image area and the application menu area internal items or objects thereof may be displayed at fixed positions.

On the other hand the card object area includes the card objects and including a content list. In the card object is a CP card object including a CP list and the card object is an application card object including an application list.

Positions of the card objects and may be moved or replaced. Alternatively a position of each item e.g. an item yakoo in the card objects and may be moved or replaced.

Although not shown in the drawing the card object area may include for example a broadcast card object not shown including a broadcast program list a preferred channel card object not shown including a preferred channel list a stored content card object not shown including a stored content list and a channel browser card object not shown including a channel list.

In this case the application screen may include an application for remote control of the image display device among a plurality of applications. The application screen may further include an application for remote control of a washing machine and an application for remote control of a refrigerator for example.

The application for remote control of the image display device may be downloaded from the server and be installed in the mobile terminal when the mobile terminal is connected to the server .

If the application for remote control of the image display device is selected from the application screen the corresponding application item may be focused and displayed so as to be differentiable from other applications.

If the application for remote control of the image display device is executed the image display device may enter a remote control mode thereof. Thus as described above the image display device may perform transmission of a pairing signal reception of a pairing response signal reception of device information on the image display device and reception of personal information for example.

The image display device remote control screen is variable according to the kind of images displayed on the image display device .

For example if the image display device displays the home screen as shown in the image display device remote control screen may include items associated with the home screen.

If the content list item among the items of is selected the mobile terminal may transmit information on the selected item to the image display device . As such the image display device may transmit a content list request to the server the server may transmit a content list to the image display device and the image display device may transmit the received content list to the mobile terminal . As such the content provider list may be displayed on the display unit of the mobile terminal .

In this case the display unit of the image display device may display an enlarged broadcast image on the home screen other than the home screen image of .

In this way it is possible to allow the user to continuously watch the displayed image without interruption. In particular in the case in which the mobile terminal displays content not associated with a broadcast image such as the content list and the image display device does not display content. This ensures that the user can perform desired operations using the mobile terminal while watching the broadcast image which results in enhanced user convenience.

Referring to if a specific item among the content provider items in the content provider list of is selected the corresponding item may be focused and displayed on the display unit of the mobile terminal .

Referring to if the specific item among the content provider items of the content provider list of is selected a content list provided by a content provider may be displayed on the display unit of the mobile terminal .

If the specific item among the content provider items of the content provider list of is selected the mobile terminal may transmit information on the selected item to the image display device . As such the image display device may transmit a request for information on the selected item i.e. information on the corresponding content provider to the server and the server may transmit the information on the corresponding content provider to the image display device . In this case the content provider information may include a content list provided by the content provider. The image display device may transmit the received content provider information to the mobile terminal . As such the content list provided by the content provider may be displayed on the display unit of the mobile terminal .

Referring to if a specific item among content items of the content list shown in is selected a corresponding content image is played and is displayed on the display unit of the mobile terminal . Also illustrates that a corresponding content image is played and is displayed on the display unit of the image display device .

If the specific item among the content items of the content list shown in is selected the mobile terminal may transmit information on the selected item to the image display device . As such the image display device may transmit a request for information on the selected item i.e. a request for corresponding content to the server and the server may transmit the corresponding content to the image display device . The image display device may play the received content and display the played content image on the display unit thereof.

Thus the user may simply and rapidly watch the desired content image using the mobile terminal while watching a broadcast image via the image display device .

On the other hand the image display device may transmit the received content to the mobile terminal . As such the mobile terminal may play the received content and display the played content image on the display unit thereof.

If the specific item among the content items of the content list is selected the mobile terminal may be directly connected to the server without the image display device and may receive the corresponding content from the server . Even in this case information on the selected item may be transmitted to the image display device .

Although the drawing illustrates that both the mobile terminal and the image display device play and display content images differently only the image display device may play and display content images. That is the display unit of the mobile terminal may display only the focused selected item in a state in which the content list is displayed as shown in .

If a next screen view request is input in a state in which the content provider list is displayed as shown in an application list may be displayed on the display unit of the mobile terminal .

Referring to if a specific item among application items of the application list shown in is selected an application associated image is displayed on the display unit of the image display device .

If the specific item among the application items of the application list shown in is selected the mobile terminal may transmit information on the selected item to the image display device . As such the image display device transmits a request for information on the selected item i.e. information on a corresponding application item to the server and the server may transmit the information on the corresponding application item to the image display device .

In particular if the image display device is not equipped with the corresponding application item the application item information may include download information or purchase information for example.

As such the image display device may receive the information on the application item and display the associated image on the display unit thereof.

The drawing illustrates display of the downloading associated image of the corresponding application item.

In this way an application not equipped in the image display device can be searched and selected and be installed in the image display device using the mobile terminal .

The image display device remote control screen may include a broadcast item a content list item and an application item .

Referring to if the application item of the image display device remote control screen shown in is selected an application menu including an application list is displayed on the display unit of the mobile terminal .

The application menu may correspond to an application menu displayed in the application menu area of .

Referring to if a search application item of the application menu shown in is selected a search screen is displayed on the display unit of the mobile terminal .

In this case if a search word is input to the search screen the mobile terminal transmits search information to the image display device and in turn the image display device transmits the search information to the server . The server collects searched result information based on the search information and transmits the searched result information to the image display device . The image display device may display a searched result screen on the display unit thereof.

In this way when inputting a search word through the mobile terminal the searched result can be displayed on the image display device which results in enhanced user convenience.

If a specific item is selected in a state in which the content provider list is displayed as shown in a content list provided by a selected content provider may be displayed on the display unit of the mobile terminal as shown in .

If any one content item is selected as shown in an information image associated with corresponding content may be displayed on the display unit of the mobile terminal .

In this case if the mobile terminal is not connected to the image display device it is impossible to transmit the selected content information to the image display device as shown in and thus the information is stored in the memory of the mobile terminal .

Referring to if a specific content item of a bookmark list is selected in a state in which the mobile terminal and the image display device are connected to each other the mobile terminal transmits information on the corresponding content item to the image display device . As such the image display device transmits a request for transmission of corresponding content to the server . The server which has received the request transmits the corresponding content stored in the memory thereof to the image display device .

The image display device receives and plays the corresponding content and displays a played content image on the display unit thereof.

In this way in the case in which the user is located at the outside rather than being located near the image display device in other words the mobile terminal cannot be connected to the image display device the user can select a desired item included in a content list in advance using the mobile terminal and store the item in the image display device .

Thereafter if the mobile terminal can be connected to the image display device a bookmark list is displayed on the mobile terminal and the selected item is transmitted to the image display device whereby content of the desired item selected by the user can be rapidly played and displayed on the image display device .

According to an embodiment of the present invention an operating method of a mobile terminal may include entering a remote control mode for an image display device receiving a content list from the image display device or a server connected to the image display device displaying the received content list and if a specific item of the content list is selected transmitting information associated with the selected item to the image display device . Here the content list may be a content list associated with a home screen of the image display device and the operating method may further include accessing the image display device . The operating method of the mobile terminal may further include transmitting a pairing signal to the image display device and receiving a pairing response signal from the image display device .

The operating method of the mobile terminal may further include receiving at least one of device information on the image display device authentication information for connection to the image display device and authentication information with respect to the server connected to the image display device .

The operating method of the mobile terminal may further include receiving the authentication information with respect to the server connected to the image display device and accessing the server using the authentication information. In this case the operating method of the mobile terminal may further include storing the authentication information with respect to the server connected to the image display device .

If the mobile terminal cannot be connected to the image display device the operating method of the mobile terminal may further include accessing the server that transmits data to the image display device using pre stored information associated with the image display device receiving the content list from the server displaying the received content list and if a specific item of the content list is selected storing information associated with the selected item.

The operating method of the mobile terminal may further include displaying a bookmark list and transmitting information associated with the item of the bookmark list to the image display device .

According to another embodiment of the present invention an operating method of an image display device may include requesting transmission of content corresponding to a specific item from a server if an input for selection of the specific item included in a content list is received from a mobile terminal receiving the content corresponding to the selected item from the server and playing and displaying the received content. The operating method of the image display device may further include receiving a pairing signal from the mobile terminal and transmitting a pairing response signal to the mobile terminal . Additionally the operating method of the image display device may include requesting the content list from the server that can exchange data with the image display device receiving the content list from the server and transmitting the content list to the mobile terminal .

In this case the content list may be a content list associated with a home screen of the image display device . The operating method of the image display device may further include transmitting authentication information with respect to the server connected to the image display device and receiving an authentication completion message from the server .

The operating method of the image display device may further include transmitting at least one of device information on the image display device authentication information for connection to the image display device and authentication information with respect to the server connected to the image display device to the mobile terminal . The operating method of the image display device may further include displaying the home screen including a broadcast image and a content list and displaying an enlarged broadcast image on the home screen if the mobile terminal is connected to the image display device .

According to the present invention to implement the remote control mode for the image display device the mobile terminal may include a wireless communication unit for receiving a content list a display unit for displaying the received content list and a control unit for controlling transmission of information associated with a specific item if the specific item included in the content list is selected. The wireless communication unit may receive at least one of device information on the image display device authentication information for connection to the image display device and authentication information with respect to the server connected to the image display device . In this way the wireless communication unit may receive the authentication information with respect to the server connected to the image display device and the control unit may control connection to the server using the authentication information.

Additionally the mobile terminal may include a memory for storing a bookmark list including the selected item of the content list. The control unit may control display of the bookmark list and transmission of information on the selected item of the bookmark list to the image display device .

The image display device ac cording to the present invention may include a network interface for receiving an input for selection of a specific item included in a content list from the mobile terminal a control unit for controlling a request for transmission of content corresponding to the selected item from the server in response to the selection input and a display unit for playing and displaying received content if the content corresponding to the selected item is received. If the mobile device is connected to the image display device the control unit of the image display device may transmit a request for transmission of a content list from the server receive the content list from the server and transmit the content list to the mobile terminal . The network interface may transmit authentication information with respect to the server connected to the image display device and receive an authentication completion message from the server . The control unit may control transmission of at least one of device information on the image display device authentication information for connection to the image display device and authentication information with respect to the server connected to the image display device to the mobile terminal . Also if the mobile terminal is connected to the image display device in a state in which the home screen including a broadcast image and the content list is displayed on the display unit the control unit may display an enlarged image of the broadcast image on the home screen.

According to a further embodiment of the present invention an operating method of a digital receiver may be implemented as code that can be written on a processor readable recording medium and thus read by a processor provided in the digital receiver. The processor readable recording medium may be any type of recording device in which data is stored in a processor readable manner. Examples of the processor readable recording medium include a ROM a RAM a CD ROM a magnetic tape a floppy disc an optical data storage device and a carrier wave e.g. data transmission over the Internet . The processor readable recording medium can be distributed over a plurality of computer systems connected to a network so that processor readable code is written thereto and executed therefrom in a decentralized manner.

As is apparent from the above description according to the present invention in a digital system including at least one server and a plurality of digital devices it is possible to expand a channel or service coverage originally included in each digital device to acquire more abundant service data from each digital device than in the related art thereby providing an improved service guide in terms of quantity and or quality and to enable sharing of service data between the digital devices as well as between the server and each digital device included in the digital system via an SNS and the like.

Further according to the present invention the mobile terminal can enter a remote control mode for an image display device to select a specific item of a content list displayed on the mobile terminal and transmit the selected item to the image display device while watching an image displayed on the image display device . Also the mobile terminal can function to receive content corresponding to the selected item from a server play the content and display the content on the image display device thereby assisting the user in performing various operations under the image display device remote control mode while continuously watching an image displayed on the image display device . This may result in enhanced user convenience.

In particular if the content list is a content list associated with a home screen of the image display device it is possible to allow the user to directly select a desired item of the corresponding content list displayed on the mobile terminal in a state in which the image display device displays the image.

In the case in which the mobile terminal enters the image display device remote control mode and is connected to the image display device the image display device is capable of displaying an enlarged image of the displayed image. This assists the user in watching the displayed image.

Additionally the mobile terminal may receive authentication information with respect to the server connected to the image display device may be connected to the server using the authentication information and may directly receiving the content list from the server . Accordingly if the user is located at the outside other than near the image display device the user can select a desired item of the content list in advance using the mobile terminal and store the selected item in the mobile terminal .

As the mobile terminal can display a bookmark list on the mobile terminal and transmit the selected item to the image display device in a state in which the mobile terminal can be connected to the image display device content of the item selected by the user can be rapidly played and displayed on the image display device .

In this way the mobile terminal the image display device and the server can realize various UI operations.

It will be apparent to those skilled in the art that various modifications and variations can be made in the present invention without departing from the spirit or scope of the invention. Thus it is intended that the present invention covers the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

