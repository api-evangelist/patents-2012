---

title: Display apparatus connected with at least one device via integrated wire interface and controlling method thereof
abstract: The present invention includes making a request for information for listing at least one content previously saved in a plurality of source devices sequentially connected via the integrated wire interface to a plurality of the source devices, receiving the information for listing the previously saved at least one content from a plurality of the source devices, displaying the received listing information on a 1region of a screen of the display device, transmitting a signal for requesting an activation of a specific content to the source device which the specific content save in, receiving an AV data corresponding to the specific content from the source device which the specific content saved in, and controlling the received AV data to be displayed on a 2region of the screen.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09143824&OS=09143824&RS=09143824
owner: LG ELECTRONICS INC.
number: 09143824
owner_city: Seoul
owner_country: KR
publication_date: 20120126
---
This application claims the benefit of the U.S. Provisional Patent Application Nos. 61 438 244 filed on Jan. 31 2011 61 471 663 filed on Apr. 4 2011 and Korean Application No. 10 2011 0032541 filed on Apr. 8 2011 which are hereby incorporated by reference as if fully set forth herein.

The present invention relates to a display apparatus and more particularly to a display apparatus connected with at least one device using an integrated wire interface and controlling method thereof. Although this invention is suitable for a wide scope of applications it is particularly suitable for a network TV a smart TV an HBBTV hybrid broadcast broadband television an internet TV a web TV an IPTV internet protocol television and the like.

Recently the recent development of technology has brought about the advent of unprecedented digital devices. Moreover in order to connect various kinds of devices an interface suitable for each of the devices is necessary. In the following description a current status of a related art is explained with reference to .

However according to the related art a number of wire cables are necessary to connect the source devices to the TV that is one example of a sink device. For instance the number of source devices is limited to the number of connectors of the TV . And the TV is complicatedly surrounded with numerous cables.

Moreover in order to control the source devices each of the source devices needs a corresponding remote controller . For instance if there are 7 source devices 7 remote controllers are mandatory.

Besides according to the related art a user interface further optimized for a user to facilitate controls of the source devices has not been provided yet.

Accordingly this invention is directed to a display apparatus connected with at least one device using an integrated wire interface and controlling method thereof that substantially obviate one or more problems due to limitations and disadvantages of the related art.

An object of this invention is to provide an integrated wire user interface by which the data transmission between a sink device and a plurality of source devices may be further simplified with increased speed.

Another object of this invention is to define a data transmission protocol at middleware hardware interface level required for the implementation of an integrated wire interface.

Another object of this invention is to provide a user interface by which side information may be provided to a user in case that one sink device and a plurality of source devices are present.

A further object of this invention is to provide a user interface by which side information may be provided to a user in case that a plurality of sink devices and a plurality of source devices are present.

Additional advantages objects and features of the invention will be set forth in part in the description which follows and in part will become apparent to those having ordinary skill in the art upon examination of the following or may be learned from practice of the invention. The objectives and other advantages of the invention may be realized and attained by the structure particularly pointed out in the written description and claims hereof as well as the appended drawings.

To achieve these objects and other advantages and in accordance with the purpose of the invention as embodied and broadly described herein a method of controlling a display device which is connected with at least one device using an integrated wire interface according to one embodiment of the present invention includes the steps of making a request for information for listing at least one content previously saved in a plurality of source devices sequentially connected via the integrated wire interface to a plurality of the source devices receiving the information for listing the previously saved at least one content from a plurality of the source devices displaying the received listing information on a 1region of a screen of the display device transmitting a signal for requesting an activation of a specific content to the source device which the specific content saved in receiving an AV data corresponding to the specific content from the source device which the specific content saved in and controlling the received AV data to be displayed on a 2region of the screen.

In another aspect of this invention a computer readable recording medium according to another embodiment of the present invention includes a program for executing the above display device controlling method recorded therein.

In a further aspect of this invention a display device which is connected with at least one device using an integrated wire interface according to a further embodiment of the present invention includes a transmitting module making a request for information for listing at least one content previously saved in a plurality of source devices sequentially connected via the integrated wire interface to a plurality of the source devices a receiving module receiving the information for listing the previously saved at least one content from a plurality of the source devices and a display module displaying the received listing information on a 1region of a screen of the display device.

First of all according to one embodiment of the present invention as an integrated wire interface is provided between a sink device and a plurality of source devices a data rate may be raised and controls of various kinds of source devices may be facilitated.

Secondly according to another embodiment of the present invention a data transmission protocol at middleware hardware level required for the implementation of an integrated wire interface may be defined.

Thirdly according to a further embodiment of the present invention if one sink device or a plurality of sink devices and a plurality of source devices are present a user is provided with a user interface that provides side information of different formats to enhance user convenience and accessibility.

Besides the effects of the present invention will be explained in detail later in this specification.

It is to be understood that both the foregoing general description and the following detailed description of this invention are exemplary and explanatory and are intended to provide further explanation of the invention as claimed.

In the following description suffixes module and part for elements are given to facilitate the preparation of this disclosure only. So significant meanings or roles are not given to the suffixes themselves. Hence it is understood that the module and part may be interchangeably used.

Meanwhile for example a display apparatus described in the present specification includes an intelligent network TV having a computer support function in addition to a broadcast receiving function. Since an internet function and the like are added to the display apparatus based on the broadcast receiving function the display apparatus may be equipped with such a convenient interface in use as a manual input device a touchscreen a space remote controller and the like. The display apparatus may access internet and computer owing to the support of a wire wireless internet function to perform such a function as a web browsing function a banking function a game function and the like. For these various functions a standardized universal operating system OS may be usable.

Therefore a network TV mentioned in the present invention may be able to add delete various applications to from a universal OS kernel for example thereby performing various kinds of user friendly functions. Moreover for clarity and convenience in the following description of this specification although a display apparatus a network TV and the like may be usable together with each other it will be apparent to those skilled in the art that the present invention covers the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

Furthermore although embodiments of this invention are described in detail with reference to the accompanying drawings and contents contained therein this invention is non limited by the described embodiments.

Terminologies used in the present specification may be selected from general terminologies used currently and widely in consideration of functions in this invention. Yet the selected terminologies may be changeable in accordance with intentions of those skilled in the art the custom of the corresponding field the advent of new technology and the like. Occasionally some terminologies may bee arbitrarily selected by the applicant s and their meanings may be noted at the corresponding description in the present specification. Therefore the terminology used in the present specification should be construed based on the substantial meaning of the terminology and the overall contents in the present specification instead of being construed as its simple name.

Referring to first of all a sink device according to one embodiment needs to be individually connected with a plurality of source devices. In particular the sink device may correspond to one of a display device a TV a DTV a smart TV a network TV and the like for example.

In particular although shows that it is enough for the sink device to be connected with one source device e.g. AV receiver in a different source device etc. using an integrated wire interface the rest of source devices including STB Blue ray DVD player game console hard drive recorder and the like for example are connected with each other using an inter source device integrated wire interface.

In this case the sink device according to one embodiment of the present invention may be able to receive data from other source devices as well as the source device directly connected via the sink device . And the sink device shall be described in detail with reference to and the like later.

Compared to shows that all the source devices are controllable using one remote controller corresponding to the sink device . Besides has such a problem that a separate remote controller is mandatory for each source device.

Meanwhile a sink device defined in this specification may correspond to a device configured to output AV data received from a source device for example. In this case the source device may correspond to a device configured to transmit AV data to the sink device. Of course the present invention may be characterized in that control data is designed to enable interactive transmission and reception.

Referring to an integrated wire interface according to one embodiment of the present invention may be configured with architecture layers connected with each other in 8 layer structure which is just exemplary. And the present invention may basically cover the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

Besides the hardware of the integrated wire interface shown in shall be described in detail with reference to layer.

An integrated wire interface application shown in may perform such a function as content acquisition management control and the like.

Integrated wire interface middleware layer may play a role as toolkits for application development and may further transmit a call signal to an abstraction layer and other libraries.

Integrated wire interface middleware API application programming interface is the interface configured to control functions provided by an operating system or programming language to be applicable to application programs.

Abstraction layer may play a role in performing a high level AV streaming function a USB connection management and device control function and the like.

Host interface layer may play a role in performing a messaging function between DCL driver comparator load and IC integrated circuit firmware.

And DLNA UPnP HTTP TCP IP and the like may be used as complementary protocols for example which is just exemplary. If necessary it is apparent to those skilled in the art that other complementary protocols may apply to the present invention to come within the scope of the appended claims and their equivalents.

Moreover a detailed data flow for source and sink devices to transceive data using the integrated wire interface middleware layers and the integrated wire interface hardware shown in shall be described with reference to later.

Referring to a sink device according to one embodiment of the present invention is connected with a 1source device via an integrated wire interface . And the 1source device is connected with a 2source device via an integrated wire interface . Alternatively the 2source device and the sink device may be directly connected to each other via an integrated wire interface and the 2device and the 1source device may be connected together which may pertain to the scope of the appended claims and their equivalents.

Although shows the detailed circuit diagram of the integrated wire interface connecting the sink device and the 1source device together the integrated wire interface may be designed to have the same configuration of the circuit diagram of the integrated wire interface shown in .

Referring to the integrated wire interface may be designed to have two physical channels including a 1channel and a 2channel. In particular the 1physical channel may mean the channel for carrying AV data and may be designed to uni directionally transmit the AV data only. Although shows a video stream for example an audio stream is transmitted on the same channel uni directionally. In particular AV data saved in the 1source device may be transmitted to the sink device on the aforesaid 1physical channel.

The 2physical channel may mean the channel for carrying control data and may be designed to transmit the control data bi directionally. In particular the control data may be transmitted in a direction from the sink device to the 1source device or in an opposite direction from the 1source device to the sink device .

In case that a sink device and a source device are connected with each other using the integrated wire interface designed as shown in it may bring an advantageous effect that a maximum video bandwidth transmitted from the source device to the sink device is increased up to about 13.5 Gbps. Moreover if the AV channel is designed to have 3 lines as shown a data rate may be raised three times higher.

Moreover it may be able to supply power from the sink device to the source device using the bi directional data channel shown in or a separate power line. In case that the integrated wire interface according to one embodiment of the present invention is used a power of about 5 W may be supplied to an external device for example.

The integrated wire interface shown in may be designed using category 6 cable for example. In this case since data is transmitted in a manner of overlapping a clock signal several times and then encoding it at 8 b bit 10 b bit a click signal line may be unnecessary.

In case that the sink device attempts to use the data saved in the 2source device since the 1source device is situated between the sink device and the 2source device a solution for solving this matter is required.

Therefore in case of a source device a sink device attempts to access related data may be designed to bypass. And in order to transmit several AV data simultaneously it may be necessary to subdivide the above mentioned 1channel. This shall be described with reference to and later.

Referring to if a sink device e.g. TV etc. according to one embodiment of the present invention is connected with a 1source device e.g. a game console etc. via an integrated wire interface data communication with a different source device may be enabled.

Of source assume that source devices controllable by the sink device are connected with one another via integrated wire interfaces. For instance the 1source device connected with the sink device via the integrated wire interface is connected to the 2source device e.g. a home theater system etc. via the integrated wire interface .

The 2source device is connected with the 3source device e.g. Blu ray player etc. via the integrated wire interface . And the 3rs source device is connected with the 4source device e.g. PC etc. via the integrated wire interface .

Hence although the sink device is not directly connected to each of the 2source device the 3source device and the 4source device since data communications are enabled between the devices all the sink device may be able to bring and display data which is previously saved in at least one of the 2source device the 3source device and the 4source devices .

Meanwhile the terminologies Tx and Rx among the terminologies mentioned in the description with reference to and this specification may basically mean a transmitter and a receiver respectively and may be further construed in accordance with the purpose of the entire specification.

Referring to first of all a receiver RX middleware of an integrated wire interface transmits a video connection request signal to a receiver RX hardware interface of the integrated wire interface S . In doing so information rxID for identifying a receiver and information txID for identifying a transmitter may be included. Moreover the receiver of the integrated wire interface may include the sink device shown in .

The receiver hardware interface of the integrated wire interface transmits a video connection request signal to the transmitter TX hardware interface of the integrated wire interface S . The transmitter TX hardware interface of the integrated wire interface transmits information for notifying that the video connection request signal has been received to the transmitter middleware of the integrated wire interface S . Moreover the transmitter of the integrated wire interface may correspond to one of the source devices shown in for example.

The transmitter middleware of the integrated wire interface transmits a video connection response signal to the transmitter hardware interface of the integrated wire interface S . And the transmitter hardware interface of the integrated wire interface transmits a video connection response signal to the receiver hardware interface of the integrated wire interface S .

After the receiver hardware interface of the integrated wire interface has transmitted the information for notifying that the video connection response signal has been received to the receiver middleware of the integrated wire interface S substantial video data is transmitted S .

Meanwhile although shows the case that the sink device and the source device are directly connected together via the integrated interface a communication with a specific source device may be possible in case that a different source device is connected between the sink device and the source device via an integrated interface.

Since the rxID information and the txID information may be usable in each of the steps as shown in the data shown in may bypass a source device not having the same ID of a source device a sink device attempts to access.

The data format used for the flowchart shown in may be designed as the format shown in which is just exemplary. And the present invention may basically cover the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

Referring to a data format transmitted between devices connected together via an integrated wire interface may include such information as txID rxID command parameter payload length payload and the like.

The txID may correspond to the data for identifying a source device that transmits AV data for example. And the rxID may correspond to a sink device that receives AV data for example. In particular since the data format transmitted by the integrated wire interface includes such information as txID rxID and the like it may be designed to enable a communication with a desired source device but bypass a source device not having a corresponding ID.

The command is the data for identifying a type of a command intended to be transmitted from a source device to a sink device and vice versa for example. The parameter may contain detailed attribute information on the command.

The payload may mean a region in which substantial video data is included. And the payload length may include information for identifying a size of the payload.

First of all the system shown in may be configured as summarized into . Referring to a sink device according to one embodiment of the present invention is sequentially connected with a 1source device a 2source device and a 3source device via integrated wire interfaces respectively.

As mentioned in the foregoing description the sink device may be able to perform data communications with all the source devices and connected via the integrated wire interfaces. Hence using the data communications with the source devices the sink device creates an OSD to guide a 1option for selecting Contents Share a 2option for selecting Video Source and a 3option for selecting Search and then outputs the created OSD.

The 1option is a function of simultaneously displaying data retained by all the source devices connected with the sink device via the integrated wire interfaces. This shall be described in detail with reference to later.

The 2option is a function of primarily displaying types of the source devices connected with the sink device via the integrated wire interfaces and secondarily displaying data retained by a selected specific source device only. This shall be described in detail with reference to later.

The 3option is a function of searching data retained by the source devices connected with the sink device via the integrated wire interfaces using a specific keyword. This shall be described in detail with reference to later.

Referring to the sink device connected with the source devices via the integrated wire interfaces accesses each of the source devices and then extracts information indicating the data retained by the corresponding source device. And the sink device displays a plurality of informations e.g. title indicating the data retained by the source devices connected via the integrated wire interfaces respectively.

For instance photo and photo shown in correspond to informations collected from the 1source device movie and entertainment shown in correspond to informations collected from the 2source device drama shown in corresponds to information collected from the 3source device and movie shown in corresponds to information collected from the 4source device.

This design may consider the following user s purpose. First of all when the sink device is used a user mainly intends to check and output data itself more quickly rather than check whether user desired data is collected from a specific source device.

Referring to the sink device connected with the source devices via the integrated wire interfaces may primarily display information for identifying the source devices connected with the sink device via the integrated wire interfaces.

In particular the sink device may display the source devices in a manner that the source devices to belonging to the group of source devices in power on mode are discriminated from the source devices and belonging to the group of source devices in standby mode. As mentioned in the foregoing description since the integrated wire interface according to one embodiment of the present invention is equipped with a separate power line it may be able to directly supply power to the source devices in standby mode. Moreover it may be able to design the source devices to enter a power on mode by transmitting command data related to power on .

If a user of the sink device selects a specific source device e.g. a game console the sink device creates and outputs an OSD containing information for identifying data retained by the game console .

This design may consider the following reason. Namely in aspect of a user who uses the sink device if data are transmitted from all the connected source devices a size of the data is very large or the user may attempt to check the data related to a specific one of the source devices only.

Referring to in case that a user of a sink device according to one embodiment of the present invention activates a search function an OSD for guiding 2 kinds of search modes is created and outputted. A function All Search shall be described in detail with reference to . And a function searching in a specific device shall be described in detail with reference to later.

Referring to if the all search function shown in is activated a sink device according to one embodiment of the present invention creates and displays an OSD for enabling a user to randomly input a keyword . In assume that the user inputs the keyword drama .

In this case the sink device according to one embodiment of the present invention may be designed to filter data containing the keyword drama from all source devices connected to the sink device via integrated wire interface and to display a corresponding result on an OSD .

If the function searching in a specific device shown in is activated referring to a sink device according to one embodiment of the present invention preferentially outputs a list of source devices to search with a keyword. Moreover the present invention is characterized in designing at least two source devices which are to be searched with the keyword to be selected.

In doing so assuming that a user selects a game console referring to the sink device creates and displays an OSD for enabling the user to randomly input a keyword. In assume that the user inputs the keyword baseball .

Finally referring to the sink device according to one embodiment of the present invention is designed to filter data containing the keyword baseball from all the source devices connected via the integrated wire interface and more particularly from the a game console device and to display a corresponding result as an OSD .

Referring to a plurality of sink devices and are connected with a hardware including a switching module. And the hardware is connected with source devices e.g. game console Blu ray host etc. via integrated wire interfaces.

If the hardware including the switching module as shown in is additionally designed it may be advantageous in that AV data received from a source device may be transmitted to each of sink devices individually.

Referring to a plurality of sink devices and are connected with a hardware including a switching module. And the hardware including the switching module is connected with a 1source device a second source device and a 3source device via integrated wire interfaces.

The specific one of a plurality of the sink devices outputs an OSD screen as a popup window as shown in to set a function of monitoring another sink device connected via the integrated wire interface.

The hardware including the switching module is capable of monitoring data inputted to each sink device and is designed to notify a corresponding result to another sink device.

First of all assume that a 1sink device shown in activates a baseball game from a specific source device via a hardware including a switching module. In this case the hardware delivers information which notifies that the 1sink device has activated the baseball game to a 2sink device currently outputting a general broadcast screen.

Referring to the 2sink device may display an OSD as a popup window to indicate that the 1sink device has activated the baseball game.

Referring to if the popup window of the OSD shown in is selected a 2sink device activates the same content of the 1sink device . As mentioned in the foregoing description since a hardware including a switching module is equipped with at least two AV stream out connectors the AV data received from the same source device may be delivered to each of the different sink devices.

Yet referring to the 2sink device brings the content activated by the 1sink device from the beginning and then displays the brought content. If the source device includes one of a game console a DVD player and the like instead of the NAS or DLNA device it may be possible to output the same scene which shall be described in detail with reference to .

Unlike shows that a 1sink device and a 2sink device may be able to simultaneously output the AV data received from a specific source. For instance assume that the 1sink device is activating a specific AV file from a DVD player.

Since all devices are connected together using an integrated wire interface proposed by the present invention the 2sink device may be able to collect information on the AV file currently activated by the 1sink device . Moreover a host of performing this function shall be described in detail with reference to later.

Since the specific AV file transmitted from the DVD player is being delivered to the 1sink device via the switching module the 2sink device may receive the same AV file from the switching module as well.

According to another embodiment of the present invention described with reference to a TV situated in a bed room of one home and a TV situated in a living room thereof may simultaneously receive data from the same source device. Moreover if a monitoring function is added it may be advantageous in that a TV situated in a room mainly used by a child is controlled through another TV in another room.

First of all assume that 2 sink devices and are connected with a hardware including a switching module via an integrated wire interface as shown in and . Moreover the hardware including the switching module a 1source device e.g. PC a 2source device e.g. a game console and a 3source device e.g. a DVD player are connected together via the integrated wire interface.

Referring to the 1sink device transmits a baseball game activation signal to the 2source device via the hardware including the switching module S . In this case it may design the 1source device to be bypassed.

The 2source device transmits baseball game related data to the 1sink device via the hardware S . In doing so the hardware delivers the information which indicates that the baseball game related data has been transmitted to the 2sink device S .

Having checked the information the 2sink device transmits a baseball game activation request signal to the 2source device S . Subsequently the second source device transmits the baseball game related data to the 2sink device S .

Referring to using an integrated wire interface according to one embodiment of the present invention a 1sink device a 1source device a 2sink device a 2source device and a 3source device are sequentially connected with one another.

Yet in TV 1 is shown as one example of the 1sink device BD Blu ray disc player is shown as one example of the 2sink device a game console is shown as one example of the 2source device and a PC is shown as one example of the 3source device .

Compared to shows that a hardware including a switching module is unnecessary. Yet in order for a plurality of sink devices to use AV data saved in a source device it may be necessary to modify the above described integrated wire interface. This shall be described in detail with reference to as follows.

Like shows that a 1sink device a 1source device a 2sink device a 2source device and a 3source device are sequentially connected via an integrated wire interface.

In order to play a role as the switching module described in the former embodiment AV physical channel of the integrated wire interface should be increased. In particular although the bi directional data control channel may be maintained as one line shown in a plurality of physical AV channel lines and are necessary to deliver AV data to a plurality of sink devices without the switching module.

Referring to a 1sink device a 3source device a 2sink device a 2source device and a 1source device are connected with one another via an integrated wire interface. In particular the integrated wire interface shown in may correspond to the integrated wire interface having a plurality of AV channel lines shown in .

For instance the 1sink device receives specific AV data from the 1source device and then outputs the received specific AV data around 9 AM. After elapse of 1 hour the 2sink device receives the same AV data from the 1source device and then outputs the received AV data around 10 AM.

This is possible because of the following reason. Namely if the above described integrated wire interface shown in is equipped with a plurality of AV channel lines AV data can be received from the same source without channel interference.

Referring to a 1sink device a 3source device a 2sink device a 2source device and a 1source device are connected with one another via an integrated wire interface. In particular the integrated wire interface shown in may correspond to the integrated wire interface having a plurality of AV channel lines shown in .

For instance the 1sink device receives specific AV data from the 2source device and then outputs the received specific AV data around 7 PM. At the same time i.e. around 7 PM the 2sink device receives different AV data from the 3source device and then outputs the received AV data around 10.

This is possible because of the following reason. Namely if the above described integrated wire interface shown in is equipped with a plurality of AV channel lines AV data can be simultaneously received from different sources irrespective of whether AV channel is set for uni direction.

First of all assume that a 1sink device a 3source device a 2sink device a 2source device and a 1source device are sequentially connected via an integrated wire interface. Particularly the integrated wire interface physically includes a plurality of the AV channel lines shown in or .

Referring to the 1sink device makes a request for specific data to the 2source device at Time S . At time the 2sink device makes a request for specific data to the 3source device S .

At Time the 2source device transmits the requested AV data to the 1sink device S . At the same time i.e. Time the 3source device transmits the requested AV data to the 2sink device S .

Assume that a sink device shown in is connected with at least one or more source devices via the integrated wire interface described with reference to . In this case the sink device may correspond to one of a TV a DTV a smart TV an HBBTV an IPTV and the like.

Referring to the sink device makes a request for metadata of a content previously saved in each source device via a uni directional control line of the integrated wire interface according to one embodiment of the present invention. In particular the metadata may include a title of each content a file format of each content a created time and date of each content thumbnail image data of each content and the like for example.

Having received the thumbnail image data of the respective contents the sink device displays all contents previously saved in the source devices in a random manner as shown in the central part of . Yet a random content may not have the thumbnail image data. If so with reference to information on the file format of the metadata a 1icon previously saved in the sink device is displayed in case of a photo file. Moreover in case of a video file a 2icon previously saved in the sink device is displayed.

Meanwhile if the number of source devices connected via the integrated wire interface geometrically increases or the contents saved in each of the source devices are excessively large a user of the sink device may have difficulty in selecting and accessing a content desired by the user with ease.

In order to solve this problem a keyword search option may be provided. Since title information or tag information representing each content is contained in the content metadata received from the source device if a specific keyword is inputted via the keyword search option the content having the corresponding title or tag information is identifiably displayed. This may pertain to the scope of the appended claims and their equivalents.

Moreover the sink device additionally provides 4 kinds of subfunctions to raise the user s convenience. A 1subfunction is an option of identifiably displaying contents recently added to the source device which shall be described in detail with reference to and later.

A 2subfunction is an option of identifiably displaying a most frequently accessed content among a plurality of contents saved in the source device which shall be described in detail with reference to later. And a 3subfunction is an option of collecting and displaying contents per source device connected via an integrated wire interface which shall be described in detail with reference to and later.

Moreover a 4subfunction is an option of sorting and displaying contents saved in the source device connected via an integrated wire interface which shall be described in detail with reference to and later.

Compared to identically shows that a sink device has a 1subfunction a 2subfunction a 3subfunction and a 4subfunction .

Unlike the former sink device shown in the sink device shown in is designed to display a thumbnail image of a different format. In particular the thumbnail images shown in are displayed with 3D effect. For instance by predetermined priority a thumbnail image of a content having a highest priority is displayed in a manner of being enlarged in biggest size a thumbnail image of a content having a second highest priority is displayed in a manner of being enlarged in second biggest size and a thumbnail image of a content having a lowest priority is displayed in a manner of being enlarged in smallest size.

The predetermined priority is set to give an order in a manner of combining at least one of a source device saved date an accessed count a recently played date and the like together and a thumbnail image size is determined in the given order which pertains to the scope of the appended claims and their equivalents. Moreover the present embodiment may be implemented using a data table shown in .

Referring to assume that a sink device and source devices and are connected via the above mentioned integrated wire interface. The sink device is connected with an internet server via network and may be able to access a webpage or receive IP data. The sink device includes a separate host module to monitor data communications with each of the source devices and statuses of other sink devices. The components of the host module will be described in detail with reference to later.

The sink device makes a request for metadata of contents previously saved in the 1source device via bi directional data line of the integrated wire interface S . In this case the metadata may include thumbnail image data of each content. Meanwhile since the data transmitted in the step S contains rxID and txID for example as shown in or it is advantageous in that the sink device is able to easily check that the received metadata is received from which source device. Subsequently the 1source device transmits the metadata of the contents saved in the memory to the sink device in response to the request made in the step S S . As mentioned in the foregoing description the metadata may include the thumbnail image data. Yet occasionally some contents may include no thumbnail image data. A corresponding solution will be described in the steps S and the step S later.

As mentioned in the foregoing description the steps S and S of transmitting and receiving the data between the sink device and the 1source device may identically apply to the steps S and S of transmitting and receiving data between the sink device and the 2source device the steps S and S of transmitting and receiving data between the sink device and the 3source device and the steps S and S of transmitting and receiving data between the sink device and the 4source device . And the redundant description shall be omitted from the following description. Therefore the sink device may be designed to save a table configured with the data shown in in a memory using the metadata received from the respective source devices.

Meanwhile in case that thumbnail image data is not included in each content metadata received from the source device the sink device is designed to download related thumbnail image data by accessing a random internet server .

For instance suing the title information included in the metadata the sink device makes a request for the thumbnail image data corresponding to the title information to the server S . If the thumbnail image data corresponding to the title information exists the server is designed to transmit the corresponding thumbnail image data to the sink device S .

Therefore it is advantageous in that a user of the sink device does not need to separately search for contents saved in the source device having no thumbnail images.

First of all a sink device according to a 2embodiment of the present invention includes a host module and an OSD generating unit and further includes other modules in addition. In particular the host module includes a controller a receiving unit a request unit a network access unit a memory an icon generating unit and the like.

The receiving unit and the request unit are connected with an external 1source device source and an external 2source device source device via an integrated wire interface and are designed to enable bi directional data communications.

For instance if the command for activating the contents share function shown in or is inputted via a user interface the controller controls the request unit to make a request for metadata of each content to each of the source devices and . Meanwhile Contents Share used in this specification means a function of collecting and displaying contents saved in source devices. Contents Share may be substituted with such a terminology as all share simultaneous share and the like for example. And these terminologies may non limit the scope of the appended claims and their equivalents.

Meanwhile the user interface may include a motion remote controller for example which will be described in detail with reference to and later.

If the receiving unit receives the metadata from the source devices and the controller saves the received metadata in the memory . The controller may include a CPU or the like. And the memory may include at least one of a flash memory RAM ROM and the like for example.

The icon generating unit generates a unique icon using each content thumbnail image data saved in the memory . And the OSD generating unit generates an OSD by adjusting a size position and shape of the icon generated by the icon generating unit using the metadata saved in the memory .

Meanwhile if the thumbnail image data is not included in the metadata the controller is designed to control the network access unit to download the corresponding thumbnail image data from the internet server . For instance if a title of a content having not thumbnail image data is a professional baseball the network access unit accesses the internet server searches for the thumbnail image data having the title of the professional baseball and then receives the found thumbnail image data. Subsequently the received thumbnail image data may be saved in the memory .

First of all a sink device according to a 2embodiment of the present invention may be able to receive metadata from source devices via bi directional data line of an integrated wire interface. In this case the metadata may mean side information on contents saved in a memory of each of the source devices. In particular the metadata may include at least one of a title a file format a creation saved time and date and a thumbnail image data.

In the course of transmitting or receiving metadata between a sink device and a source device as shown in or since rxID information and txID information are included in the metadata the sink device may be able to identify that the metadata of a specific content is received from which source device. Meanwhile as mentioned in the foregoing description the metadata of some contents may not include the side information corresponding to thumbnail image data.

In this case two kinds of embodiments may be taken into consideration. A 1embodiment relates to a solution for giving a representative image of a specific icon previously saved in a sink device in accordance with a file format of a corresponding content. For instance an icon of representing a video is designated as a thumbnail image according to avi. file. For another instance an icon of representing a photo is designated as a thumbnail image according to jpg. file.

According to a 2embodiment a sink device connectible with an internet network accesses a server receives thumbnail image data corresponding to a tile and then saves the received thumbnail image data in a memory using metadata indicating the title of a corresponding content.

Information on the most recently accesses time and date is not received from a source device. Instead if a random content is outputted to a sink device a timing point of the output is added and saved in the table shown in .

Referring to if the above mentioned contents share function is activated a sink device is designed to display thumbnail images in metadata of contents received from source devices connected via an integrated wire interface . shows that a random thumbnail image data shown in is enlarged and displayed.

Referring to each thumbnail image data includes 2 kinds of side graphic data and . The 1side graphic data is generated by the icon generating unit or the OSD generating unit described with reference to . The 1side graphic data is designed as an option selectable by a user of the sink device . If the 1side graphic data is selected it may be deleted from the contents share screen. In particular according to this design it may be able to freely edit the excessive number of contents receivable from source devices or files not desired by the user.

The 2side graphic data is designed to vary in accordance with a file format of a content. For instance using the table saved in the memory shown in shown in a file format of each content may be identified. Hence the OSD generating unit shown in combines an identifier which identifies a video content a music content a photo content or the like with thumbnail image data with reference to the table saved in the memory shown in .

Referring to a sink device is designed to display thumbnail images in the metadata of contents received from source devices connected via an integrated wire interface.

Using a remote controller capable of outputting a pointing signal it may be able to select a random thumbnail image data . In order to give a feedback effect to a user a cross shape may be displayed at a point indicated by the remote controller . Of course the cross shape is just exemplary. And the present invention may basically cover the modifications and variations of the display shape provided they come within the scope of the appended claims and their equivalents. The remote controller capable of outputting the pointing signal will be described in detail with reference to and later.

In order to facilitate the identification of a number of contents displayed on a contents share screen it may be necessary to generate secondary feedback data. For instance assuming that a pointing signal of the remote controller is situated in a specific thumbnail image region a secondary feedback data may be designed to be displayed as shown in . In particular while an original thumbnail image is displayed only if the pointing signal of the remote controller is situated over predetermined duration a graphic data of side information is designed to be outputted as well as the original thumbnail image . In this case the side information is received from a source device or may be receivable via an internet server. The OSD generating unit shown in generates graphic data using the received side information.

Referring to a sink device is designed to display thumbnail images in the metadata of contents received from source devices connected via an integrated wire interface. As mentioned in the foregoing description if a remote controller capable of outputting a pointing signal is situated within a region of a specific thumbnail image side information e.g. Amanda 1album singer. Song etc. is displayed together.

Referring to if a cross indicator indicated by the pointing signal is situated within an option region for deleting the thumbnail image data a sink device substitutes a part of a region of the corresponding thumbnail image data with a black screen. Instead of the substitution with the black screen the corresponding thumbnail image data may be removed from the contents share screen only which may pertain to the scope of the appended claims and their equivalents.

Referring to a pointer corresponding to a remote controller is displayed on a display unit . In particular the display unit may correspond to one of a sink device a TV and the like for example.

A user may be able to move or rotate the remote controller up down right and left or back forth . The pointer displayed on the display unit of a display device corresponds to a motion of the remote controller . Since the corresponding pointer is displayed by moving in accordance with a motion in 3D space this remote controller may be named a space remote controller.

Referring to if a user moves the remote controller in left direction the pointer displayed on the display unit of the display device moves in left direction to correspond to a motion of the remote controller .

Information on the motion of the remote controller sensed via a sensor of the remote controller is transmitted to the display device. Subsequently the display device may be able to calculate coordinates of the pointer from the information on the motion of the remote controller . And the display device may be able to display the pointer to correspond to the calculated coordinates.

Referring to while a specific button within the remote controller is pressed a user shifts the remote controller in a manner of getting away from the display unit . If so a selected region within the display unit corresponding to the pointer may be enlarged and displayed by zoom in. On the contrary if a user shifts the remote controller in a manner of getting closer to the display unit a selected region within the display unit corresponding to the pointer may be reduced and displayed by zoom out. Alternatively if the remote controller gets away from the display unit the selected region may zoom out. If the remote controller gets closer to the display unit the selected region may zoom in.

Meanwhile while a specific button in the remote controller is pressed recognition of up down motion or right left motion may be excluded. In particular if the remote controller moves to get away from or get closer to the display unit both of the up down motion and the right left motion may not be recognized but the back forth motion may be recognized only. While a specific button in the remote controller is not pressed the pointer is shifted only in accordance with the up down motion or right left motion of the remote controller . And a moving speed direction of the pointer may correspond to a moving speed direction of the remote controller .

Meanwhile a pointer mentioned in this specification may mean an object display on the display unit in response to a motion of the remote controller . Hence the pointer may be displayed as objects in various shapes as well as the arrow shape shown in the drawing. For instance the various shapes may include a point a cursor a prompt a thick outline and the like. The pointer may be displayed to correspond to a prescribed point on a vertical or horizontal axis on the display unit . Alternatively the pointer may be displayed to correspond to a plurality of points including a line a surface and the like.

Moreover using the remote controller it may be able to control overall options of the above mentioned contents share. In particular it may be advantageous in facilitating selection and editing of specific thumbnail image data.

Referring to a remote controller may include a wires communication unit a user input unit a sensor unit an output unit a power supply unit a storage unit and a control unit .

The wireless communication unit transceives signals with a random one of the display devices according to the embodiments of the present invention mentioned in the foregoing description. As mentioned in the foregoing description the display devices may include a TV a DTV a smart TV and the like.

According to the present embodiment the remote controller may include an RF module capable of transceiving signals with the display device by RF communication specifications. And the remote controller may include an IR module capable of transceiving signals with the display device by IR communication specifications.

According to the present embodiment the remote controller may transmit a signal containing information on a motion of the remote controller and the like to the display device via the RF module .

And the remote controller may receive a signal transmitted by the display device via the RF module . If necessary the remote controller may transmit a command for power on off channel switching volume adjustment or the like to the display device via the IR module . Moreover the remote controller may receive a command signal for selecting or editing a thumbnail image of a specific content to the display device via the IR module .

The user input unit may include at least one of a keypad a button a touch pad a touchscreen and the like. A user may be able to input a command related to the display device to the remote controller by manipulating the user input unit . If the user input unit includes a hard key button a user may be able to input a command related to the display device to the remote controller by pushing the hard key button. If the user input unit includes the touchscreen a user may be able to input a command related to the display device to the remote controller by touching a soft key of the touchscreen. The user input unit may include various kinds of input means e.g. a scroll key a jog key etc. to be manipulated by a user by which the scope of the appended claims and their equivalents may be non limited.

The sensor unit may include a gyro sensor or an acceleration sensor . In particular the gyro sensor may sense information on a motion of the remote controller .

For instance the gyro sensor may be able to sense information on a motion of the remote controller with reference to x y and z axes. The acceleration sensor may be able to sense information on a moving speed of the remote controller and the like. The sensor unit may further include a distance measuring sensor to sense a distance from the display unit . Hence a plurality of the thumbnail image data displayed on the contents share screen as shown in may be edited with 3D effect.

The output unit may be able to output a video or audio signal to correspond to a manipulation of the user input unit or the signal transmitted by the display device . Through the output unit a user may be able to recognize whether the user input unit is manipulated or whether display device is controlled.

For instance the output unit may include an LED module turned on if the user input unit is manipulated or a signal is transceived with the display unit via the wireless communication unit . For instance the output unit may include a vibration module generating vibration if the user input unit is manipulated or a signal is transceived with the display unit via the wireless communication unit . For instance the output unit may include an audio output module outputting an audio if the user input unit is manipulated or a signal is transceived with the display unit via the wireless communication unit . For instance the output unit may include a display module outputting a video if the user input unit is manipulated or a signal is transceived with the display unit via the wireless communication unit .

The power supply unit supplies the remote controller with power. If the remote controller does not move for predetermined duration the power supply unit cuts off the power supply to save power consumption. If a prescribed key provided to the remote controller is manipulated the power supply unit may be able to resume the power supply.

The storage unit may store various kinds of programs required for controlling or operating the remote controller application data and the like. If the remote controller transceives signals with the display device by wireless via the RF module the remote controller and the display device transceive signals with each other on a prescribed frequency band. In particular the control unit of the remote controller saves information on a frequency band for transceiving signals by wireless with the display device paired with the remote controller and the like and may then refer to the saved information.

The control unit controls overall items related to the control of the remote controller . The controller may be able to transmit a signal corresponding to a prescribed key manipulation of the user input unit or a signal corresponding to a remote controller motion sensed by the sensing unit to the display device via the wireless communication unit .

Referring to if a contents share function is activated a sink device displays thumbnail image data included in metadata of a content received from a source device. Yet in case that the number of the thumbnail image data shown in reaches several tens or hundreds a user may have difficulty in checking a specific thumbnail image desired by the user.

If an option corresponding to a 1subfunction displayed on a left top end of a screen is selected referring to a sink device enlarges and displays a thumbnail image data corresponding to a most recently added content.

Meanwhile for example of a reference for detecting a recently added content two examples may be taken into consideration. According to a 1example a reference value is set with reference to a timing point of saving a random content in a source device. Hence contents currently saved in a source device may be collected within a prescribed time e.g. a day ago a week ago etc. from a timing point of activating a contents share function.

According to a 2example a memory status in a previous activation of a contents share function is compared with a memory status in a current activation of the contents share function. For instance after data of displaying 1content and a 2content only have been saved in the memory in the event of the previous activation of the contents share function if data of displaying a 3content and a 4content are saved in the memory in the event of the current activation of the contents share function as well the sink device sets the 3content and the 4content to be recognized as recently added contents.

Referring to if a contents share function is activated a sink device displays thumbnail image data included in metadata of contents received from a source device.

If an option corresponding to a 1subfunction displayed on a left top end of a screen is selected referring to a sink device displays a plurality of thumbnail image data corresponding to a plurality of most recently added contents respectively.

In particular if a plurality of contents are added within a preset time e.g. 1 hour ago 1 day ago etc. prioritization is adopted in order to specifically identify a plurality of the contents added within the preset time.

For instance the OSD generating unit displays a thumbnail image corresponding to a 1content which is most recently added in a largest size. And the OSD generating unit displays a thumbnail image corresponding to a 2content which is recently added in a 2largest size.

The OSD generating unit displays a thumbnail image corresponding to a 3content which is most recently added in a 3largest size. The OSD generating unit displays a thumbnail image corresponding to a 4content which is most recently added in a 4largest size. And the OSD generating unit displays a thumbnail image corresponding to a 5content which is most recently added in a 5largest size.

Referring to if a contents share function is activated a sink device displays thumbnail image data included in metadata of contents received from a source device.

If an option corresponding to a 2subfunction displayed on a left bottom end of a screen is selected referring to a sink device enlarges and displays a thumbnail image data corresponding to a most frequently accessed content. In doing so an OSD generating unit may be designed to reduce sizes of the rest of the thumbnail image data or delete the rest of the thumbnail image data from the screen.

A sink device according to a 2embodiment of the present invention counts the number of activation of each content the number of playing each content and the number of accesses of each content and then saves result values of the counted numbers in a memory. If a currently played specific content is stopped intentionally or due to malfunction a timing point of the stop is saved as a tag in the memory. Therefore it may be able to provide an option of calling a previously viewed final screen or viewing the specific content from the beginning .

If a user of the sink device selects a continuous viewing option the sink device may be designed to display the corresponding content from a scene previously stopped being played as shown in using tag information i.e. data indicating a timing point of the stop in the course of play of the corresponding content saved in the memory.

Referring to if a contents share function is activated a sink device randomly displays thumbnail image data included in metadata of contents received from a source device.

If an option corresponding to a 3subfunction displayed on a right bottom end of a screen is selected referring to a sink device is designed to display a list of source devices currently connected via an integrated wire interface.

Referring to if a specific source device e.g. USB is selected from a list displayed by a sink device according to a 2embodiment of the present invention the sink device is designed to display the screen shown in .

In particular the sink device enlarges and displays thumbnail images and corresponding to contents received from USB source device only and deletes the rest of thumbnails images corresponding to contents received from other source devices or outputs the rest of the thumbnail images by adjusting a contrast ratio as shown in for example. As mentioned in the foregoing description this design is available because the sink device can be aware that a corresponding content is received from which source. This is fully explained in the descriptions with reference to and and the redundant description will be omitted.

Referring to if a contents share function is activated a sink device randomly displays thumbnail image data included in metadata of contents received from a source device.

If an option corresponding to a 4subfunction displayed on a right top end of a screen is selected referring to a sink device displays OSDs and of 4 regions representing file formats respectively. The OSDs are generated by the OSD generating unit and may be designed using the data of the memory shown in .

Besides previous thumbnail image data are designed to overlap with each other in part or to be shifted in specific direction e.g. left direction of the screen which may pertain to the scope of the appended claims and their equivalents. This design may bring an advantage of maintaining user s visibility.

Referring to a sink device displays OSDs and of 4 regions representing file formats respectively. If a cross shape indicating a pointing signal is situated on the OSD representing a video file format using a remote controller the OSD shown in is displayed.

In particular the controller shown in access the memory and then determines file formats of the respective contents. In doing so assume that the memory stores the table shown in .

Therefore under the control of the controller the OSD generating unit shown in generates an OSD of enlarging and displaying contents and of the video file format only. The rest of the contents not in the video file format are displayed in relatively small size as shown in whereby the contents of the user specific format are emphatically displayed. Optionally according to another embodiment of the present invention the rest of the contents not in the video file format may be designed not to be displayed at all which pertains to the scope of the appended claims and their equivalents.

Although the above description is made using different drawings for clarity it may be able to implement a new embodiment by combining the embodiments described with reference to the drawings. And it is apparent to those skilled in the art to design a recoding medium readable by a computer in which programs for executing the above mentioned embodiments are recorded. This pertains to the scope of the rights of the present invention.

The display apparatus and operating method thereof according to the aforementioned embodiments of this invention may be achieved by combination of structural elements and features of this invention in a predetermined type. Each of the structural elements or features should be considered selectively unless specified separately. Each of the structural elements or features may be carried out without being combined with other structural elements or features. Also some structural elements and or features may be combined with one another to constitute the embodiments of this invention.

Meanwhile the display apparatus operating methods according to this invention may be implemented in a recording medium readable by a processor provided to a display apparatus with processor readable codes. The processor readable media may include all kinds of recording devices in which data readable by a processor are stored. The processor readable media may include ROM RAM CD ROM magnetic tapes floppy discs optical data storage devices and the like for example and may also include carrier wave type implementations e.g. transmission via Internet . Moreover the processor readable recording medium may be distributed on network connected computer systems to save and execute processor readable codes by distributed processing.

Although embodiments have been described with reference to a number of illustrative embodiments thereof it should be understood that numerous other modifications and embodiments can be devised by those skilled in the art that will fall within the spirit and scope of the principles of this disclosure. More particularly various variations and modifications are possible in the component parts and or arrangements of the subject combination arrangement within the scope of the disclosure the drawings and the appended claims. In addition to variations and modifications in the component parts and or arrangements alternative uses will also be apparent to those skilled in the art.

And both of the apparatus invention and the method invention are described in this specification. Moreover the description of both inventions may be supplemented with each other.

