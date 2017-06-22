---

title: Method of managing contents to include display of thumbnail images and image display device using the same
abstract: Provided are a method of managing the contents and an image display device using the same. The method includes: obtaining contents information on each of a plurality of contents sources; displaying the obtained contents information on one screen as a plurality of lists that are differently configured according a plurality of classified items; and receiving meta information on at least one content in the contents lists and displaying the received meta information in correspondence to the content.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09088820&OS=09088820&RS=09088820
owner: LG ELECTRONICS INC.
number: 09088820
owner_city: Seoul
owner_country: KR
publication_date: 20120905
---
The present application claims priority under 35 U.S.C. 119 and 35 U.S.C. 365 to Korean Patent Application No. 10 2011 0097484 filed on Sep. 27 2011 which is hereby incorporated by reference in its entirety.

The present disclosure relates to a method of managing contents provided from contents sources connected to an image display device via a wired wireless network.

As digital TVs having more excellent signal processing and storage capacity than typical analog TVs and also wired wireless network technologies are commercialized various kinds of contents services such as real time broadcasting Contents on Demand COD games news and video communication are allowed to be provided to users through an internet network connected to each home in addition to typical broadcast media.

As an example of a contents service provider using an internet network IPTVs may be introduced. The IPTVs transmit various information services video contents and broadcasts to user s TVs via a high speed internet network.

Additionally image display devices such as digital TVs may share contents in p playback or stored therein with external image display devices such as other TVs smart phones PCs and tablet PCs via a wired wireless network.

Embodiments provide a method of efficiently managing various contents provided from a plurality of contents sources via a wired wireless network and an image display device using the same.

In one embodiment a method of managing contents includes obtaining contents information on each of a plurality of contents sources displaying the obtained contents information on one screen as a plurality of lists that are differently configured according a plurality of classified items and receiving meta information on at least one content in the contents lists and displaying the received meta information in correspondence to the content.

In another embodiment an image display device includes a storage unit for storing contents information a control unit for storing information on each of a plurality of contents sources in the storage unit and constructing information on the plurality of contents with a plurality of contents lists according to at least two classified items a display unit for displaying the plurality of constructed contents lists on one screen together with meta information on at least one content and a network interface unit for receiving meta information on at least one content in the contents lists.

The details of one or more embodiments are set forth in the accompanying drawings and the description below. Other features will be apparent from the description and drawings and from the claims.

The terms and words used in the specification and claims should not be interpreted as conventional or dictionary meanings and thus should be interpreted as meanings and concepts corresponding to the technical idea of the present invention on the basis of the principle that the inventor may appropriately define the concept of the terms in the best way in order to describe his her own invention.

Accordingly the invention may however be embodied in many different forms and should not be construed as being limited to the embodiments set forth herein rather that alternate embodiments included in other retrogressive inventions or falling within the spirit and scope of the present disclosure can easily be derived through adding altering and changing and will fully convey the concept of the invention to those skilled in the art.

Referring to the first image display device and the second image display device are connected to each other via a wired wireless network and transmit receive contents data so that they share specific contents

For example the first and second image display devices and are connected to each other through various communication standards such as Digital Living Network Alliance DLNA Wireless Lan WiFi Wireless HD WiHD Wireless Home Digital Interface WHDi Blutooth ZigBee binary Code Division Multiple Access CDMA and Digital Interactive Interface for Video Audio DiiVA and thus exchange data with each other.

Additionally each of the first and second image display devices and is connected to a media server via a wired wireless network such as Internet and shares contents by transmitting receiving contents through the media server .

Moreover each of the first and second image display devices and may be various devices such as a digital TV for example a network TV an HBBTV or a smart TV a PC a notebook computer a mobile communication terminal for example a smart phone and a tablet PC.

An N screen service which continuously provides one content to various devices such as TVs PCs tablet PCs and smart phones may be provided through the contents sharing system described with reference to .

For example a user may continuously view a broadcast or movie that the user previously viewed using a TV through another smart phone or tablet PC and also may view additional information on a corresponding drama through a smart phone or tablet PC while viewing the drama in a TV.

With the above N screen service a contents file or a screen of the first and second image display devices and may be shared therebetween.

For this the first image display device may transmit contents received from an external or stored therein to the second image display device at a user s request through the above various communication methods.

Additionally as contents that a user purchases are stored in the media server a user may play the contents in desired one of the first and second image display devices and as needed by downloading the contents from the media server via Internet.

As shown in the first and second image display devices and are connected to at leas tone contents source via a wired wireless network so that contents are received from the contents source and shared with each other.

For example the contents source may be a storage device equipped in or connected to an image display device a Network Attached Storage NAS a Digital Living Network Alliance DLNA or a media server but the present invention is not limited thereto.

Referring to the image display device is connected to the plurality of contents sources and for providing contents to the image display device and thus receives contents including image signals and sound signals. For this the image display device may include input output terminals such as HDMI USB components and RGB in order to transmit receive data to from the external devices and .

For example the external devices and may include various devices such as an image playback device for example a DVD player Dvix player and a Blu ray player a set top box for example an IPTV set top box a cable set top box or a satellite set top box a PC a game console a home theater a portable terminal an HDD recorder and a USB memory.

However the external devices and connected to the image display device are not limited to the above devices and may be any devices connected to the image display device to transmit image signals.

For example the external device may include various devices such as digital TVs PCs notebook computers mobile communication terminals for example smart phones tablet PCs NAS equipment DLNA servers and media servers which are connected to the image display device via a wired wireless network.

Additionally the image display device may receive broadcast signals through a tuner not shown or may receive contents from an external device through various communication standards such as WiFi WiHD WHDi Blutooth ZigBee binary CDMA and DiiVA or may download contents from the media server of via internet.

Furthermore as mentioned above after contents received from an external are stored in a storage device not shown equipped in or connected to the image display device they may be played at a user s request.

As shown in the contents management system may include a Service Delivery Platform SDP according to an embodiment.

The SDP maintains horizontal and common services in development distribution authentication billing and messaging of services provided from Contents Providers CPs or Service Providers SPs and also integrates and develops them.

The image display device requests metadata including detailed information on specific contents to the SDP server and provides various information on contents to a user by receiving the requested metadata from the SDP server .

For example the image display device may receive metadata including movie title director actors or plot information on specific video contents from the SDP server and may display them on a screen.

Referring to the tuner may select an RF broadcast signal corresponding to a channel selected by a user or all pre stored channels among Radio Frequency RF broadcast signals received through an antenna and may convert the selected RF broadcast signal into an intermediate frequency signal or a base band image or sound signal.

The demodulation unit may receive the digital IF signal DIF converted by the tuner and then may perform a demodulation operation thereon. For example if the digital IF signal outputted from the tuner is the ATSC format the demodulator may perform an 8 Vestigal Side Band 8 VSB demodulation operation.

Additionally the demodulation unit may perform channel decoding and for this may include a Trellis Decoder a De interleaver and a Reed Solomon Decoder in order to perform Trellis decoding de interleaving and Reed Solomon decoding.

The demodulation unit may output a stream signal TS after performing the demodulation and channel decoding and the stream signal may be a signal into which an image signal sound signal or a data signal is multiplexed.

For example the stream signal may be an MPEG 2 Transport Stream TS into which an MPEG 2 standard image signal and a Dolby AC 3 standard sound signal are multiplexed. In more detail the MPEG 2 TS may include a 4 byte header and a 184 byte payload.

The stream signal outputted from the demodulation unit may be inputted to the control unit . The control unit may output an image to the display unit and a sound to the audio output unit after demultiplexing and processing the image sound signal.

The external device interface unit may connect an external device and the image display device and for this may include an A V input output unit not shown or a wireless communication unit not shown .

The external device interface unit may be used for wired wireless connection of an external device such as a Digital Versatile Disk DVD player a Bluray player a game console a camera a camcorder and a computer for example a notebook computer .

Moreover the external device interface unit may deliver an image sound or data signal inputted from a connected external into the control unit of the image display device and may output the image sound or data signal processed in the control unit into the connected external device.

The A V input output unit may include a USB terminal a Composite Video Banking Sync CVBS terminal a component terminal an S video terminal i.e. an analog type a Digital Visual Interface DVI terminal a High Definition Multimedia Interface HDMI terminal an RGB terminal and a D SUB terminal in order to input image and sound signals of an external device into the image display device .

Furthermore the wireless communication unit may perform a short range wireless communication with another electronic device. For example the image display device and another electronic device may be connected to a network through communication standards such as Bluetooth Radio Frequency Identification RFID infrared Data Association IrDA Ultra Wideband UWB ZigBee and Digital Living Network Alliance DLNA .

Moreover the external device interface unit is connected to various set top boxes through at least one of the above various terminals in order to perform an input output operation of a set top box.

In addition the external device interface unit may receive applications or lists of applications in an adjacent external device and then may deliver them to the control unit or the storage unit .

The network interface unit may provide an interface for connecting the image display device to a wire wireless network including an internet network. For example the network interface unit may include an Ethernet terminal for accessing a wired network or may be connected to a wireless network through communication standards such as WiFi WiHD WHDi Blutooth ZigBee binary CDMA DiiVA Wibro Wimax and HSDPA.

Moreover the network interface unit may transmit receive data to from another user or another electronic device via a connected network or another network linked to the connected network.

Additionally the network interface unit may transmit some contents data stored in the image display device to a selected user or electronic device among users or other electronic devices pre registered in the image display device .

The network interface unit may access a predetermined web page via a connected network or another network linked to the connected network. That is the network interface unit may access a predetermined web page via a network to transmit receive data to from a corresponding sever.

Then the network interface unit may receive contents or data provided from a CP or a network operator. That is the network interface unit may receive contents such as movies advertisings games VODs and broadcast signals and information thereon which are provided from a CP or a network provider via a network.

Additionally the network interface unit may receive update information and update files of a firmware provided from a CP or a network operator and may transmit data to an internet provider a CP or a network operator.

The network interface unit may select and receive a wanted application from applications open to air via a network.

The storage unit may store a program for processing and controlling each signal in the control unit and may store the processed image sound or data signals.

Moreover the storage unit may perform a function for temporarily storing image sound or data signals inputted from the external device interface unit or the network interface unit and may store information on a predetermined broadcast channel through a channel memory function.

The image display device may play contents files stored in the storage unit such as movie files still image files music files document files and application files and then may provide them to a user.

The user input interface unit may deliver a signal that a user inputs to the control unit or may deliver a signal from the control unit to a user. For example the user input interface unit may receive a control signal such as power on off channel selection and screen setting from a remote control device and may process the received control signal according to various communication methods such as an RF communication method or an IR communication method. Or the user input interface unit may transmit a control signal from the control unit to the remote control device .

Additionally the user input interface unit may deliver to the control unit a control signal inputted from a local key not shown such as a power key a channel key a volume key and a setting key.

For example the user input interface unit may deliver to the control unit a control signal inputted from a sensing unit not shown that senses a gesture of a user and may transmit a signal from the control unit to a sensing unit not shown . Moreover the sensing unit not shown may include a touch sensor a sound sensor a position sensor and a motion sensor.

The control unit may demultiplex a stream inputted from the tuner the demodulation unit or the external device interface unit or may process demultiplexed signals in order to generate and output a signal for image or sound output.

The image signal processed in the control unit is inputted to the display unit and then is displayed as an image corresponding to a corresponding image signal. Additionally the image signal processed in the control unit is inputted to an external output device through the external device interface unit .

The sound signal processed in the control unit may be outputted to the audio output unit as audio. Moreover the sound signal processed in the control unit is inputted to an external output device through the external device interface unit .

Although not shown in the control unit may include a demultiplexing unit and an image processing unit.

Besides that the control unit may control overall operations of the image display device . For example the control unit controls the turner to tune an RF broadcast corresponding to a channel that a user selects or a pre stored channel.

Additionally the control unit may control the image display device through a user command inputted through the user input interface unit or an internal program and may access a network to download applications that a user wants or lists of applications into the image display device .

For example the control unit controls the tuner to receive a signal of a selected channel according to a predetermined channel selection command received through the user input interface unit and may process an image sound or data signal of the selected channel.

The control unit may output channel information that a user selects in addition to a processed image or sound signal through the display unit or the audio output unit .

Moreover the control unit may output an image or sound signal of an external device such as a camera or a camcorder which is inputted through the external device interface unit into the display unit or the audio output unit according to an external device image playback command received through the user input interface unit .

Furthermore the control unit may control the display unit to display an image and for example the control unit may control the display unit to display a broadcast image inputted through the tuner an external input image inputted through the external device interface unit an image inputted through a network interface unit or an image stored in the storage unit . In this case an image displayed on the display unit may be a still or moving image or a 2D or 3D image.

Additionally the control unit may play contents stored in the image display device received broadcast contents or external input contents inputted from an external. The contents may have various formats such as a broadcast image an external input image an audio file a sill image an accessed web page and a document file.

According to an embodiment the image display device integrates and manages contents provided from a plurality of contents sources in one screen regardless of contents sources. Also the image display device may receive metadata on specific contents among the contents from the SDP and then may provide various information thereon to a user.

Hereinafter a method of managing contents according to an embodiment will be described with reference to .

Referring to the image display device obtains information on available contents with respect to each of a plurality of contents sources in operation .

For example the control unit of the image display device searches for contents in each contents source connected to the image display device in order to store information on the searched contents in the storage unit and also periodically performs contents search on a plurality of contents sources in order to update contents information stored in the storage unit according to a search result.

Then the control unit of the image display device constructs the obtained contents information with a plurality of contents lists according to at least two classified items in operation S.

For example the control unit constructs a list of available contents from the plurality of contents sources by using the contents information obtained in operation S. Accordingly the constructed contents list is not limited to a specific contents source and thus includes all available contents that a user can select in the image display device .

Additionally the constructed contents list may be displayed on one screen of the display unit and thus a user may integrally mange various contents provided from a plurality of contents sources regardless of contents sources for example selecting playing or transmitting contents in one screen .

Referring to the contents list including information on a plurality of contents may be displayed on the screen of the image display device and Content to Content in the contents list may be contents provided from a plurality of contents sources.

For example Content Content and Content are contents provided from a first contents source. Content Content and Content are contents provided from a second contents source. The contents may be aligned according to a predetermined standard and then may be displayed in the contents list .

Additionally as shown in the contents information in the contents list may be a thumbnail image representing corresponding contents. For example a thumbnail image may be an image obtained by reducing an image in video contents to the display area size of the contents list .

Moreover one of contents thumbnail images in the contents list may be displayed larger then other images and the displayed position or size of each thumbnail image is determined according to predetermined standards or user s settings .

Furthermore the above contents list may include a plurality of different lists according to classified items such as recommended contents recently played contents recently added contents preferred contents and contents type.

That is contents provided from a plurality of contents sources may be represented as a plurality of contents lists corresponding to each of a plurality of predetermined classified items. Since the plurality of contents lists classify and align contents provided from the plurality of contents sources according to the standard based on different classified items they may include contents of different groups.

Referring to a plurality of contents lists and corresponding to respective classified item classified item and classified item may be simultaneously displayed on the screen of the image display device .

For example the first contents list may include Content Content and Content classified and aligned according to the classified item among contents provided from a plurality of contents sources.

Additionally the second contents list may include Content Content Content and Content classified and aligned according to the classified item among contents provided from a plurality of contents sources.

Furthermore the third contents list may include Content Content Content Content Content and Content classified and aligned according to the classified item among contents provided from a plurality of contents sources.

As shown in the number of contents in a contents list and the size of an area where each contents information is displayed may set differently according to a classified item. This also may vary depending on a user s input.

Additionally as Contents is included in the first contents list and the second contents list simultaneously a plurality of contents lists configured according to at least two classified items may commonly include specific contents.

The image display device receives meta information on contents in operation S and displays the plurality of configured contents lists in addition to the received meta information in operation .

For example the network interface unit of the image display device may request metadata transmission on video contents in the contents list to the SDP server and then may receive the metadata on the video contents from the SDP server .

Furthermore the metadata received from the SDP server may include meta information such as the title director actors and plot of the video contents and the meta information may be displayed on a contents list in correspondence to corresponding contents.

For example as shown in if the Content in the first contents list corresponding to the classified item is a movie the network interface unit requests the transmission of metadata on the Content to the SDP server and then receives meta information on the movie title director actors or plot of the Content from the SDP server .

Furthermore the received metadata on the Content may be displayed together with the thumbnail image of the Content in the first contents list .

As described with reference to according to an embodiment a user may integrally manage contents provided from a plurality of contents sources in one screen of the image display device regardless of contents sources and also together with that may easily confirm contents meta information provided from the SDP server on the screen regardless of an additional search process.

Hereinafter referring to embodiments for a method of configuring and managing contents provided from a plurality of contents sources by a plurality of contents lists according to at least two classified items.

Referring to the image display device may display a CONTENTS SHARE User Interface UI on the screen in order to share contents with external devices at a user s request.

The CONTENTS SHARE UI includes a plurality of contents lists and configured by at least two classified items as described with reference to and a list of external devices connectible to the image display device .

That is a CONTENTS TYPE item is to classify a list of contents provided from a plurality of contents sources by the types of the corresponding contents. A RECENTLY STOPPED ADDED item is to provide the list of contents provided from the plurality of contents sources according to a recently played or added order. A FRIENDS LIKE item is to provide a contents list according to a contents preference in more detail whether it is recommended by friends .

For example the CONTENTS TYPE item may display contents provided from a plurality of contents sources as a contents type list which classifies the contents into contents recorded in the image display device RECORDED photo contents PHOTO music contents MUSIC and movie contents MOVIE .

The RECENTLY STOPPED ADDED item may be displayed as the recent contents list including contents which are the most recently stopped or added in the image display device among the contents provided from the plurality of contents sources.

For example the most recently stopped or added contents are selected by a predetermined number from contents stopped during playback or newly added to the CONTETS SHARE UI. One content that is the most recently stopped among the selected stopped added contents may be displayed greater than other contents in the recent contents list .

Moreover a plurality of thumbnail images in the recent contents list may be stored in advance in the storage unit so that they may be displayed without delay. Contents stopped or added on the same date may be grouped and displayed.

The FRIENDS LIKE item may be displayed as the recommended contents list including contents that friends recommend through a contents sharing service provided via internet among contents provided from a plurality of contents sources.

Moreover a user may select at least one from the contents in the contents lists and and then may play it or transmit it to an external device. For this a pointer displayed on the screen may be moved or a highlighted box may be moved in order to select a specific content by using a remote control device.

A LINKED DEVICE item may be displayed as the connected device list including a plurality of contents sharing external devices connected to the image display device or connected according to a user s input.

Additionally a user may input a search word in a search object displayed on the screen in order to search for a desired content from contents provided from a plurality of sources.

Referring to the connected device list may include a plurality of external devices connectible to the image display device such as My phone LG stick X USB Your phone Blu ray and RGB PC .

External devices in the connected device list may be displayed to be distinguished from each other by using a device name and icon or may be displayed with different color cells according to a device type for example a storage device a portable terminal a playback device or a server .

A user may select one of the external devices to in the connected device list and then may receive contents from the selected external device and play them or may transmit contents to the selected external device in order to share the contents.

Additionally devices for inputting contents in connection with the image display device via a wired wireless network for example Blu ray and RGB PC may be displayed with an input device icon for representing an input device.

When a user selects the RGB PC displayed with the input device icon as shown in a popup window for notifying that a screen of the image display device switches to a screen of the selected RGB PC may be displayed on the screen .

When a user selects confirm from the popup window as shown in data corresponding to contents currently played in the RGB PC are inputted to the image display device so that the screen of the RGB PC may be shared in the image display device .

Moreover external devices displayed in the connected device list may be determined according to a predetermined priority order. For example according to the priority order such as the order of devices connected within the last two weeks devices connected using USB DLNA and WiFi direct devices connected using WiFi display devices connected using DiiVa input devices and power off devices external devices may be selected by a predetermined number and then arranged.

A device that requires authentication among external devices in the connected device list for example a server that requires authentication for wireless network connection such as WiFi display or WiFi direct may be displayed with an additional icon in order to represent whether the authentication is successful.

Referring to when there is no device to be displayed in the connected device list because there is no external device connected to the image display device a Help for Contents Share button for setting a connection with an external device may be displayed in the connected device list .

Referring to a CONTENTS SHARE UI screen may include a History reset button for initializing a contents usage history. When the History reset button is selected a popup window for notifying that all items of RECENTLY STOPPED ADDED are deleted may be displayed on the screen .

In this case when a user selects a confirm button of the popup window as shown in all contents information is initialized in the recent contents list .

Referring to the network interface unit of the image display device may access a server providing a specific sharing service which is preset during a device manufacturing process or set by a user. A user registered as a friend in a corresponding service may receive information on uploaded downloaded or recommended contents.

The received information may include thumbnail images for each of the contents and accordingly the recommended contents list may arrange and display thumbnail images for contents that a user who is registered as a friend uploads downloads or recommends according to a time sequence in the contents sharing service.

Moreover one content among the contents in the recommended contents list may be displayed as a larger image then other contents. When the number of contents that the user registered as a friend uploads downloads or recommends is less than the number of contents displayable in the recommended contents list some cells may be dimmed without an additional image.

Referring to when the image display device is not logged in the contents sharing service a Log in button for logging in the contents sharing service may be displayed in the recommended contents list .

Referring to when the image display device is logged in the contents sharing service if there are no contents that a user registered as a friend uploads downloads or recommends contents information may not be displayed in the recommended contents list .

Referring to when a user selects an area having a CONTENTS TYPE item displayed on the screen of a list for entire contents provided from contents sources connectible to the image display device may be displayed on the list .

Moreover when one of the contents in the contents list is selected meta information on the selected content may be displayed on the screen in addition to the contents list .

As described with reference to the meta information may be information received from the SDP server at the request of the image display device .

Moreover in the case of music contents album jackets song titles or singers may be provided as detailed information. In the case of photo contents thumbnail images file names or shooting dates may be displayed. In the case of recordings thumbnail images titles channels recoding dates or recording times may be displayed.

With a method of displaying the ALL type contents list described with reference to when a Batman Forever movie content is selected from contents displayed on the screen detailed information on the selected movie content may be displayed on a detailed information window in addition to the thumbnail image .

The detailed information on the movie content may include information such as the title director actors rating review impression synopsis or playing time of a corresponding movie. The above detailed information may include metadata received from the SDP server .

Moreover contents in the ALL type contents list may be arranged according to time order. When a user selects an Alphabetic order button displayed on the screen the contents may be rearranged according to an alphabetic order of the corresponding contents titles.

For example a user moves a scroll box on the first scroll bar by using the remote control device in order to select a contents type corresponding to the position of the scroll bar .

Additionally the CONTENTS SHARE UI may include a second scroll bar that allows a user to select a specific position of a contents list.

For example a user moves a scroll box on the second scroll bar by using the remote control device in order to display on the screen a portion corresponding to the position of the scroll box in the contents list.

That is when the scroll box on the second scroll bar moves in one direction a contents list on the screen moves in a corresponding direction. Also new contents in the contents list may be displayed on the screen .

Additionally a user may recognize a rough position of a portion displayed on the current screen in the contents list by using the position of the scroll box on the second scroll bar .

Referring to when a user selects a MOVIE from a CONTENTS TYPE item on the screen of among contents provided from a plurality of content sources connectible to the image display device a movie contents list may be displayed on the screen .

Moreover when one of the contents in the movie contents list is selected meta information on the selected movie content may be displayed on the screen in addition to the contents list received from the SDP server .

Referring to if there is no connected network for the metadata transmission between the image display device and the SDP server a network connection button may be displayed on the screen in order to provide a connection with the SDP server .

Moreover no meta information on one content selected from the movie contents list is stored in the SDP server and thus as shown in a message for notifying that there is no meta information on the selected movie content may be provided to a user.

As mentioned above when no network is connected or there is no meta information contents related information that a file itself of movie contents selected by a user has may be displayed on an area where meta information is displayed.

Referring to a user moves the scroll box on the first scroll bar to a position corresponding to Movie in order to display the movie contents list on the screen .

Moreover series of contents in the movie contents list may be displayed on the screen as one group contents .

Referring to when a user selects a PHOTO from a CONTENTS TYPE item on the screen of among contents provided from a plurality of content sources connectible to the image display device a photo contents list including photo contents may be displayed on the screen .

Referring to a user moves the scroll box on the first scroll bar to a position corresponding to Photo in order to display the photo contents list on the screen .

Furthermore when a user selects one photo content in the photo contents list information on the selected photo content is displayed and also information on the file name shooting date size and compression type of the photo content may be displayed adjacent to the information on the one photo content .

Referring to when a user selects a RECORDED from a CONTENTS TYPE item on the screen of a recordings list may be displayed on the screen .

Moreover when one recording is selected from a recordings list displayed on the screen meta information on the selected recording may be displayed.

Hereinafter configurations and operations of the image display device and the SDP server will be described in more detail with reference to .

Referring to a scanning unit searches for contents in each of a plurality of contents sources and an update management unit obtains information on changed contents among the searched contents.

For this the scanning unit includes a plurality of scanners respectively corresponding to a plurality of contents sources and scans and searches for contents in each corresponding external device.

For example the scanning unit may include a USB File Scanner a DLNA File Scanner and a Metadata Scanner which respectively correspond to a USB device a DLNA server and a media server.

In more detail the USB file scanner accesses a USB device connected to the image display device through a USB Plug in out Manager and searches for contents stored in the USB device.

Additionally the DLNA file scanner receives an event message through a DLNA status manager using UpnP when a network between the image display device and a DLNA server is connected or disconnected and searches for contents in the eDLNA server by using HTTP protocol.

Moreover the metadata scanner receives an event message through a DLNA status manager using mDNS when a network is connected or disconnected and searches for contents in the media server by using HTTP protocol.

Also the control unit may further include a USB DVR manager not shown . The USB DVR manager may search for contents stored in an Electronic DataBase Management System EDBMS .

An MGE interface unit may request the transmission of meta information on movie contents among the searched contents to the SDP server and then may receive an eXtensible MarkUp Language XML file including the meta information from the SDP server .

Furthermore a parsing unit parses the received XML file in order to obtain meta information on the movie contents and then delivers the meta information to the update management unit .

Accordingly the update management unit obtains information on the contents searched from a plurality of contents sources and meta information matching some of the contents for example movie contents and the matched contents information and meta information may be stored in the storage unit through the storage management unit .

The contents list management unit constructs a contents list by using the contents information and meta information stored in the storage unit and the constructed contents list is delivered to the display unit in order to be displayed on the screen of the image display device .

According to an embodiment the scanning unit confirms whether contents information on each of a plurality of contents sources is changed for example contents addition deletion or modification by using a plurality of scanners and searches for all contents again in a corresponding contents source when the contents information is changed in order to deliver a contents list to the update management unit .

Moreover the update management unit obtains information on the changed contents by confirming the contents list delivered from the scanning unit . In addition to stored time information the changed contents information may be stored in the storage unit through the storage management unit . The stored time information may represent a time at which the contents information is stored in the storage unit .

In this case the contents list management unit may update a previously constructed list according to recently added deleted or modified contents information by using the contents information and stored time information stored in the storage unit .

Additionally when contents in the contents list are played time information on the contents playback stop may be stored in the storage unit and accordingly the contents list management unit may update a previously constructed contents list according to recent playback information.

According to an embodiment the image display device and the SDP server may communicate with each other through Representational state transfer REST and the MGE interface unit of the image display device may transmit the name of a contents file to the SDP server through HTTP thereby requesting the transmission of meta information on corresponding contents.

For example the meta information transmission request from the MGE interface unit of the image display device to the SDP server may have a format such as http IP address specific path query filename including extension .

Then the following is the case that the image display device requests meta information on movie contents having an avartar.avi file name to the SDP server .

Referring to the MGE interface unit of the SDP server receives the name of a contents file from the image display device through HTTP. A Contents Title extracting unit separates and extracts an actual title for example a movie title from the file name received from the image display device .

Moreover a search engine may search a DB for meta information on corresponding contents by using the contents title extracted from the Contents Title extracting unit .

According to an embodiment the search engine reads updated meta information from the DB periodically and then indexes the read meta information in order to store it in a memory not shown .

In this case the search engine does not directly search the DB for the contents title extracted from the Contents Title extracting unit but searches the meta information by first using indexing information stored in the memory so that search speed and accuracy on meta information may be improved.

A Metadata Aggregation System MAS receives meta information on various contents periodically from SPs and parses the received meta information to store it in the DB .

Additionally a Matching Score calculating unit may detect meta information that is the most corresponding to a corresponding contents file from the search results inputted from the search engine and for this a Levenshtein distance algorithm may be used.

Then the MGE interface unit constructs the meta information detected by the Matching Score calculating unit with XML and transmits the XML to the image display device through HTTP so that a response to the metal information transmission request from the image display device may be completed.

Referring to in response to the meta information transmission request of the image display device the MGE interface unit of the SDP server may include the obtained meta information in XML and then provides it to the image display device .

For example the MGE interface unit constructs the XML of by using items of the meta information and a meta information value corresponding to each item and then transmits the constructed XML to the image display device through HTTP.

The method of managing contents according to the present invention can also be embodied as computer readable codes on a computer readable recording medium. The computer readable recording medium is any data storage device that can store data which can be thereafter read by a computer system. Examples of the computer readable recording medium include read only memory ROM random access memory RAM CD ROMs magnetic tapes floppy disks and optical data storage devices and also include carrier waves such as data transmission through the Internet .

The computer readable recording medium can also be distributed over network coupled computer systems so that the computer readable code is stored and executed in a distributed fashion. Also functional programs codes and code segments for accomplishing the present invention can be easily construed by programmers skilled in the art to which the present invention pertains.

Although embodiments have been described with reference to a number of illustrative embodiments thereof it should be understood that numerous other modifications and embodiments can be devised by those skilled in the art that will fall within the spirit and scope of the principles of this disclosure. More particularly various variations and modifications are possible in the component parts and or arrangements of the subject combination arrangement within the scope of the disclosure the drawings and the appended claims. In addition to variations and modifications in the component parts and or arrangements alternative uses will also be apparent to those skilled in the art.

