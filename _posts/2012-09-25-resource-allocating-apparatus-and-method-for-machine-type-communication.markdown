---

title: Resource allocating apparatus and method for machine type communication
abstract: There are provided a resource allocating method for machine type communication (MTC), a data transmission and reception method for an MTC device, and an MTC device using the data transmission and reception method. The transmission and reception method for the MTC device includes: receiving a downlink frame from a base station; searching for a control information block in a downlink control resource area of the downlink frame; determining whether the control information block is for MTC service or includes control information whose destination is the MTC device, using an MTC device identifier or an identifier designated for MTC service scheduling; and extracting MTC service packet data included in a radio resource for transmission of MTC data, using the control information block, according to the results of the determination.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08937916&OS=08937916&RS=08937916
owner: Electronics and Telecommunications Research Institute
number: 08937916
owner_city: Daejeon
owner_country: KR
publication_date: 20120925
---
This application claims priority to Korean Patent Applications No. 10 2011 0097174 filed on Sep. 26 2011 and No. 10 2012 0102461 filed on Sep. 14 2012 in the Korean Intellectual Property Office KIPO the entire contents of which are hereby incorporated by reference.

Example embodiments of the present invention relate in general to a resource allocating apparatus and method for machine type communication MTC and more specifically to a resource allocating apparatus and method for MTC capable of improving service efficiency of MTC by allocating MTC device identifiers an MTC device using the resource allocating apparatus and method for MTC and a data transmission and reception method for the MTC device.

Machine type communication MTC or machine to machine M2M communication is a form of data communication which involves one or more entities that do not necessarily need human interaction. Service optimized for MTC differs from service optimized for human to human communication. In comparison with a current mobile network communication service MTC service can be characterized by a several market scenarios b data communication c lower cost and less effort d a potentially very large number of communicating terminals e a wide service area and f very small traffic per terminal.

MTC may appear in various service forms. An MTC scheme is a primary issue in the fields of Smart Metering Tracking Tracing Remote Maintenance Control eHealth etc.

Lately 3Generation Partnership Project 3GPP has been working on MTC standardization for intelligent communication between humans and objects and between objects.

MTC service is a service for information exchange between machines or between a machine and a user. Methods for providing MTC service for MTC devices has been based on mostly a wired network when the MTC devices exchange information with an MTC server through a wireless network.

Accordingly example embodiments of the present invention are provided to substantially obviate one or more problems due to limitations and disadvantages of the related art.

An example embodiment of the present invention provides a resource allocating method for machine type communication MTC capable of improving service efficiency of MTC by allocating MTC device identifiers.

Another example embodiment of the present invention also provides a data transmission and reception method for an MTC device.

Another example embodiment of the present invention also provides a resource allocation apparatus for MTC.

In an example embodiment there is provided a resource allocating method for machine type communication MTC including determining if MTC data that is to be transmitted to an MTC device is generated whether a location of a radio resource for transmission of MTC data is variable in a transmission period creating a control information block including MTC scheduling information if the location of the radio resource for transmission of MTC data is variable including the control information block in a first downlink control resource area or a second downlink control resource area configuring a frame including a radio resource area for transmission of MTC data and at least one area of the first downlink control resource area and the second downlink control resource area and transmitting the frame.

The first downlink control resource area may include control information for a general user terminal and further include control information for an MTC device.

The control information block may transmit the MTC scheduling information together with an MTC device identifier.

The control information block may transmit the MTC scheduling information using an identifier designated for MTC service scheduling.

The radio resource area for transmission of MTC data may include MTC data and the MTC data may include Cyclic Redundancy Check CRC bits masked with an MTC device identifier or a code block sequence of MTC traffic data scrambled with the MTC device identifier.

In another example embodiment there is provided a data transmission and reception method that is performed by a machine type communication MTC device including receiving a downlink frame from a base station searching for a control information block in a downlink control resource area of the downlink frame determining whether the control information block is for MTC service or includes control information whose destination is the MTC device using an MTC device identifier or an identifier designated for MTC service scheduling and extracting MTC service packet data included in a radio resource for transmission of MTC data using the control information block according to the results of the determination.

The extracting of the MTC service packet data included in the radio resource for transmission of MTC data using the control information block according to the results of the determination may include if the control information block is for MTC service acquiring scheduling information about the radio resource for transmission of MTC data using the identifier designated for MTC service scheduling and demodulating and decoding a MTC traffic data transmitted to the MTC device using the MTC device identifier.

The extracting of the MTC service packet data included in the radio resource for transmission of MTC data using the control information block according to the results of the determination may include demodulating and decoding MTC traffic data transmitted to the MTC device using the MTC device identifier if the control information block includes control information whose destination is the MTC device.

The data transmission and reception method may further include transmitting feedback information to the base station if a downlink packet transmitted from the base station has been successfully received.

In another example embodiment there is provided a data transmission and reception method including receiving location information of a radio resource for transmission of MTC data from a base station through system information or a control message searching for the location of the radio resource for transmission of MTC data in a downlink frame received from the base station and extracting MTC service packet data included in the radio resource for transmission of MTC data using an MTC device identifier.

In another example embodiment there is provided a resource allocating apparatus for machine type communication MTC including an MTC data storage unit configured to store at least one piece of information among software information for MTC service an identifier of at least one MTC device or at least one group of MTC devices and encoding information and an MTC controller configured to determine whether a location of a radio resource area for transmission of MTC data is variable in a transmission period if MTC data that is to be transmitted to an MTC device is generated to create a control information block including MTC scheduling information if the location of the radio resource area for transmission of MTC data is variable in the transmission period to include the control information block in a first downlink control resource area or a second downlink control resource area and to configure a downlink frame.

The resource allocating apparatus may further include a transceiver configured to transmit the downlink frame configured by the MTC controller and to receive a signal transmitted from at least one MTC device.

The first downlink control resource area may include control information for a general user terminal and further include control information for an MTC device.

The control information block may transmit the MTC scheduling information together with an MTC device identifier.

The control information block may transmit the MTC scheduling information using an identifier designated for MTC service scheduling.

The radio resource area for transmission of MTC data may include MTC data and the MTC data may include Cyclic Redundancy Check CRC bits masked with the MTC device identifier or a code block sequence of MTC traffic data scrambled with the MTC device identifier.

In another example embodiment there is provided a machine type communication MTC device including a receiver configured to receive a downlink frame from a base station and a controller configured to search for a control information block in a downlink control resource area of the downlink frame to determine whether the control information block is for MTC service or includes control information whose destination is the MTC device using an MTC device identifier or an identifier designated for MTC service scheduling and to extract MTC service packet data included in a radio resource for transmission of MTC data using the control information block according to the results of the determination.

If the control information block is for MTC service the controller may acquire scheduling information about the radio resource for transmission of MTC data using the identifier designated for MTC service scheduling and demodulate and decode MTC traffic data transmitted to the MTC device using the MTC device identifier.

If the control information block includes control information whose destination is the MTC device the controller may demodulate and decode MTC traffic data transmitted to the MTC device using the MTC device identifier.

The MTC device may further include a transmitter configured to transmit an uplink frame wherein the controller may control the transmitter to transmit feedback information to the base station only when a downlink packet transmitted from the base station has been successfully received.

In another example embodiment there is provided a machine type communication MTC device including a receiver configured to receive location information of a radio resource for transmission of MTC data from a base station through system information or a control message and a controller configured to search for the location of the radio resource for transmission of MTC data in a downlink frame received from the base station and to extract MTC packet data included in the radio resource for transmission of MTC data using an MTC device identifier.

Therefore according to the example embodiments described above it is possible to allocate identifiers to MTC devices separately from those allocated to user terminals and allocate resources using the MTC device identifiers.

Example embodiments of the present invention are described below in sufficient detail to enable those of ordinary skill in the art to embody and practice the present invention. It is important to understand that the present invention may be embodied in many alternate forms and should not be construed as limited to the example embodiments set forth herein.

Accordingly while the invention can be modified in various ways and take on various alternative forms specific embodiments thereof are shown in the drawings and described in detail below as examples. There is no intent to limit the invention to the particular forms disclosed. On the contrary the invention is to cover all modifications equivalents and alternatives falling within the spirit and scope of the appended claims.

The terminology used herein to describe embodiments of the invention is not intended to limit the scope of the invention. The articles a an and the are singular in that they have a single referent however the use of the singular form in the present document should not preclude the presence of more than one referent. In other words elements of the invention referred to in the singular may number one or more unless the context clearly indicates otherwise. It will be further understood that the terms comprises comprising includes and or including when used herein specify the presence of stated features items steps operations elements and or components but do not preclude the presence or addition of one or more other features items steps operations elements components and or groups thereof.

Unless otherwise defined all terms including technical and scientific terms used herein are to be interpreted as is customary in the art to which this invention belongs. It will be further understood that terms in common usage should also be interpreted as is customary in the relevant art and not in an idealized or overly formal sense unless expressly so defined herein.

The term terminal used in this specification may be referred to as User Equipment UE a User Terminal UT a wireless terminal an Access Terminal AT a Subscriber Unit SU a Subscriber Station SS a wireless device a wireless communication device a Wireless Transmit Receive Unit WTRU a mobile node a mobile or other words. The terminal may be a cellular phone a smart phone having a wireless communication function a Personal Digital Assistant PDA having a wireless communication function a wireless modem a portable computer having a wireless communication function a photographing device such as a digital camera having a wireless communication function a gaming device having a wireless communication function a music storing and playing appliance having a wireless communication function an Internet home appliance capable of wireless Internet access and browsing or also a portable unit or terminal having a combination of such functions. However the terminal is not limited to the above mentioned units.

Meanwhile in this specification in order to distinguish a terminal that is used for machine type communication MTC service from a terminal that is used mainly by a user a terminal that is used for MTC service will be referred to as a MTC device and a terminal for communication between users will be referred to as a user terminal . Also the term MTC device will be used as a comprehensive term such as an MTC terminal device a M2M terminal device etc. including various related terms regardless of International Organization for Standardization.

Also the term base station used in this specification means a fixed point that communicates with terminals and may be referred to as another word such as Node B eNode B a base transceiver system BTS an access point etc.

Hereinafter embodiments of the present invention will be described in detail with reference to the appended drawings. In the following description for easy understanding like numbers refer to like elements throughout the description of the figures and the same elements will not be described further.

The present invention is aiming at defining states for connection control and management required for packet transmission and reception of MTC devices in a wireless network such as a cellular based mobile communication system and providing a method and procedure for allocating identifiers for identifying devices and allocating a radio resource for packet transmission using the allocated identifiers in order to provide a service such as MTC service in which the density of subscriber devices or terminals per unit service area is significantly higher than in the mobile communication system in the wireless network thereby improving efficiency of a service having high device density per unit service area.

A terminal for MTC service may be allocated a scheduling identifier for example a Cell Radio Network Temporary Identifier C RNTI in a 3GPP LTE system for uniquely identifying a terminal in unit of a base station the scheduling identifier used in a conventional cellular system or allocated a newly defined identifier for uniquely identifying a terminal in unit of a base station or in unit of a predetermined area including a plurality of base stations. The identifier enables unique identification of an MTC service terminal or a group of MTC service terminals in the service area of a base station a predetermined area including a plurality of base stations or a system to which the terminal or the group belongs and the identifier may be used to allocate a radio resource for transmission and reception of MTC packet data.

In a packet based mobile communication system radio resources for transmitting packet data are 2 dimensionally represented in frequency and time domains and the radio resources are shared between terminals in the service area of a base station. Accordingly terminals that want to transmit packet data using shared radio resources check their allocated downlink or uplink radio resources using scheduling information and then can transmit or receive packet data to or from the allocated radio resources. The scheduling information is transmitted as downlink or uplink scheduling information from a base station through a radio resource for transmitting control information on downlink.

Referring to the mobile communication network includes an MTC server an MTC user and at least one MTC device in addition to components such as a base station a user terminal etc. of a conventional mobile communication network.

The MTC device is a terminal having an MTC function capable of communicating with the MTC server and other MTC devices through a Public Land Mobile Network PLMN .

The MTC server communicates with the MTC device through the PLMN. The MTC server has an interface that can be accessed by the MTC user and provides service for the MTC user . The MTC user uses the service that is provided by the MTC server .

In the configuration illustrated in the MTC server is controlled by a network operator the network operator provides an Application Programming Interface API on the MTC server and the MTC user accesses the MTC server of the network operator through the API.

Meanwhile shows the configuration in which the MTC server is placed in the service domain of the network operator however the MTC server may be placed outside the service domain of the network operator and in this case the MTC server is not under the control of the network operator.

Also the MTC device communicates with the MTC server etc. located in the network through the base station . It is expected that there are significantly more for example about 20 to 100 times MTC devices than the number of user terminals per unit service area considered in a conventional mobile communication system.

It is assumed that the MTC device transmits a small amount of data about 150 through 200 bytes at significantly long intervals or at aperiodic intervals for example at intervals of several seconds to dozens of days or at packet generation intervals corresponding to several seconds to dozens of days .

In order to provide MTC service in a mobile communication network or in a wireless network methods of efficiently allocating identifiers to MTC devices of efficiently allocating resources and of performing retransmission are needed. Also efficient management and control for connection establishment between MTC devices and end nodes for example base stations in a wireless network for packet transmission are required.

As shown in a base station transmits scheduling information which is allocation information for a downlink or uplink radio resource through a radio resource for transmission of downlink control information that is through a downlink control resource area . Here an example of the radio resource for transmission of downlink control information may be a control channel such as a Physical Downlink Control CHannel PDCCH that is used in a 3GPP mobile communication system.

Terminals located in the coverage of the base station search for a control information block in the downlink control resource area to check the scheduling information. The control information block configuring the downlink control information includes scheduling information for a downlink or uplink radio resource allocated to an arbitrary terminal.

Terminals that have received data transmitted from the base station use their allocated scheduling identifiers C RNTIs to detect control information blocks transmitting scheduling information allocated to themselves respectively. The terminals use the scheduling information to acquire location information modulation information encoding information etc. of downlink or uplink radio resources allocated to themselves.

Accordingly the terminals check which ones of radio resource areas in the downlink data resource area allocated to themselves correspond to their allocated radio resource areas and may demodulate and decode the corresponding radio resource areas using the modulation and encoding information in the scheduling information.

In order to support MTC service a mobile communication system may transmit scheduling information for a radio resource for transmission of MTC data for an arbitrary MTC device or an arbitrary group of MTC devices using the control information block in the downlink control resource area according to a resource allocation and scheduling method that has been used for existing mobile communication user terminals.

However in this case it may be difficult to accommodate a significantly large number of MTC devices since scheduling identifiers have to be allocated to non MTC devices as well as to the MTC devices.

In order to detect the control information block in the downlink control resource area it is possible to designate a part of scheduling identifiers C RNTIs for general user terminals non MTC devices as designated identifiers for MTC service scheduling.

In this case in order to provide MTC service the base station transmits scheduling information that is allocation information for a downlink or uplink radio resource through a radio resource that is the downlink control resource area for transmission of downlink control information.

MTC devices located in the service area of the base station search for the control information block in the downlink control resource area using the designated identifiers and detect scheduling information.

For substantial resource allocation to a specific MTC device or a specific group of MTC devices resource allocation methods using identifiers allocated to the MTC device or the group of MTC devices are needed. Three representative examples of such resource allocation methods are as follows 

The first resource allocation method is to transmit an identifier of an MTC device or a group of MTC devices through a control information block.

Referring to the first resource allocation method is to include an identifier allocated to an arbitrary MTC device or a group of MTC devices in the control information block configuring the downlink control resource area . That is the MTC device or the group of MTC devices searches for the control information block in the downlink control resource area using a designated identifier for MTC service scheduling and checks an information parameter in the control information block to determine whether the control information block includes control information scheduling information transmitted to the MTC device through an MTC device or group identifier allocated to the MTC device.

The MTC device may receive MTC information transmitted to a radio resource for transmission of MTC data using information for example radio resource location information information about a frequency band and a transmission time modulation information and encoding information for MTC service in the corresponding control information block .

The second resource allocation method is to allocate an MTC device or a group of MTC devices identifier to a radio resource for transmission of MTC data.

In other words the second resource allocation method is a method of writing an MTC device a group of MTC devices identifier in a radio resource for transmission of MTC data. That is the second resource allocation method is a method of transmitting an MTC device or a group of MTC devices identifier together with scheduling information about a downlink or uplink radio resource for the MTC device or the group of MTC devices through a radio resource for transmission of MTC data.

In other words the second resource allocation method is to transmit the control information block including scheduling information such as resource allocation information transport format information etc. through a second downlink control resource area which is a radio resource for transmission of download data. ANn MTC device or a group of MTC devices identifier is also included in the second downlink control resource area and transmitted.

According to another example of the second resource allocation method the control information block of the first downlink control resource area transmits scheduling information for a radio resource for transmission of MTC data using a designated identifier for MTC service scheduling.

When the base station encodes the radio resource for transmission of MTC data the base station may mask Cyclic Redundancy Check CRC bits with an identifier allocated to a specific MTC device or a specific group of MTC devices or scramble a code block sequence of MTC traffic data to be transmitted through the radio resource for transmission of MTC data using a specific MTC device or a specific group of MTC devices identifier.

The designated identifier for MTC service scheduling may be set by designating a part of C RNTIs as identifiers for MTC service and allocating the designated identifiers.

The scheduling information may include location information information about a frequency band and a transmission time modulation information encoding information etc. of the radio resource .

That is according to the current embodiment it is possible to demodulate and decode the MTC traffic data transmitted through the radio resource for transmission of MTC data using an identifier allocated to a specific MTC device or a specific group of MTC devices . The identifier allocated to the specific MTC device or the specific group of MTC devices may be different from a scheduling identifier for example a C RNTI for a general user terminal that is a non MTC device .

Accordingly when the base station masks CRC bits with an identifier allocated to a specific MTC device or a specific group of MTC devices or scrambles a codeword sequence of a transport block of traffic data to be transmitted through the radio resource for transmission of MTC data using the MTC device the group of MTC devices identifier in order to encode the radio resource for transmission of MTC data an identifier s designated and managed for the MTC device or the group of MTC devices can be used.

Another example of the second resource allocation method is a method of fixing the location of the radio resource for transmission of MTC data and allocating the radio resource .

That is when no information for MTC service needs to be transmitted a frequency band at a specific location is allocated to general user terminals that are non MTC devices and if there is packet data for MTC service the frequency band at the specific location is allocated as the radio resource for transmission of MTC data for MTC service.

For this a method of pre defining location information information about a frequency band and a transmission time modulation information and encoding information of the radio resource for transmission of MTC data may be used.

Also in order to provide MTC service throughout the service area of an arbitrary base station or the service areas of a plurality of base stations it is possible to notify system information to all MTC devices belonging to the service area of the base station or to notify a control message to a specific MTC device or a group of MTC devices .

In this case in order to inform of scheduling information about the radio resource for transmission of MTC data MTC service packet data may be transmitted through the radio resource for transmission of MTC data without having to transmit the control block information which is scheduling information through the first downlink control resource area or the second downlink control resource area which are radio resources for transmission of downlink control information.

In the current embodiment likewise when the radio resource for transmission of MTC data is encoded a method of masking the CRC bits for the code block sequence of traffic data to be transmitted with an identifier s allocated to a specific MTC device or a group of MTC devices may be used.

In the method illustrated in when a radio resource see for transmission of MTC data is encoded a method of masking CRC bits with an identifier s allocated to a specific MTC device or a group of MTC devices is used.

That is the method illustrated in is to encode MTC service information or configure a transmission block in such a manner to mask an identifier s allocated to an MTC device or a group of MTC devices in CRC bits added to a code block sequence of MTC traffic data . Accordingly when an MTC device receives an MTC packet the MTC device can recognize an MTC device a group of MTC devices to which the MTC packet has to be transmitted based on an identifier s masked in the CRC bits of the MTC packet.

Also a method of scrambling a code block sequence of MTC traffic data to be transmitted through the radio resource for transmission of MTC data using an MTC device or a group of MTC devices identifier can be used.

The third resource allocation method is to transmit uplink resource allocation information together with MTC downlink data packets.

In order to provide MTC service a base station may request an MTC device a group of MTC device to transmit MTC packet data through an uplink while transmitting downlink data for the purpose of notifying modification of related control information updating software for MTC service etc.

In this case the base station may transmit a control information block which is scheduling information of a uplink radio resource for the corresponding MTC device while transmitting packet data for MTC service through a radio resource see for transmission of MTC data. That is as shown in the base station may transmit both MTC control information for the MTC device and MTC data information for MTC service through the radio resource for transmission of MTC data.

Here the MTC control information may be control information that has to be transmitted to the MTC device receiving the MTC data information . Also by inserting an identifier s of a MTC device or a group of MTC devices into the MTC control information control information for another MTC device or another group of MTC devices may be transmitted.

The MTC control information may be generated and signaled in the form of a MAC Control Element MAC CE by a MAC layer.

The MTC control information may include control parameters such as resource allocation information a transport format transmission timing information a transmission time a transmission time interval a continuous discontinuous transmission period etc. an identifier s of an MTC device a group of MTC devices power control information uplink timing adjustment information retransmission related information etc. in the form of a field configuring a MAC CE.

As shown in the method of transmitting the MTC control information through the radio resource for transmission of MTC data also may be applied to the case of transmitting control information for general user terminals for example smart phones other than MTC devices if data is generated at relatively long time intervals and the amount of the generated data is relatively small.

By using this method it is possible to partially overcome the problem of a shortage of radio resources for transmission of downlink control information.

Several preferred embodiments of radio resource allocation methods according to the present invention have been described above with reference to however the present invention is not limited to the preferred embodiments. That is two or more of the method of transmitting scheduling information of a radio resource for transmission of MTC data for substantial resource allocation to a specific MTC device or a specific group of MTC devices the method of allocating an identifier s to an MTC device a group of MTC devices and the method of allocating a resource s to an MTC device or a group of MTC devices using an identifier allocated to the MTC device the group of MTC devices may be selectively combined.

Also the case where a re transmission mechanism using Hybrid Automatic Repeat reQuest H ARQ is applied to improve reliability of transmission of MTC packet data is considered.

In the case of a re transmission mechanism for MTC unlike a re transmission mechanism that is applied to the transmission and reception procedure of a general user terminal an MTC device a group of MTC devices may be set to transmit feedback information that is ACK information for H ARQ only when the MTC device the group of MTC devices has successfully received downlink or uplink packet data.

Thereby it is possible to lower a modulation error ratio of uplink or downlink feedback information informing successful reception of downlink or uplink MTC data or control information which leads to improvement of H ARQ performance and reduction of consumption power of the MTC device the group of MTC devices .

That is shows a method in which the MTC device registers itself in a network and transmits packet information through the base station .

The MTC device registers itself in a network through the base station S . A procedure in which the MTC device is connected to the base station for registration is the same as a procedure in which a general user terminal is connected to a base station. At this time the MTC device transmits control information including information about the MTC device MTC service type etc. to the base station for network registration.

The base station which has received a request for connection to the network from the MTC device sets a parameter for the MTC device and determines whether to establish connection to the network based on the control information including the information about the MTC device the MTC service type etc. received from the MTC device S .

That is the base station sets a parameter for setting MTC service for the MTC device and determines whether to set the MTC device to a connected state for exchanging packet information with the base station or to an idle state corresponding to a disconnected state.

In the connected state the base station stores the information about the MTC device or the information about the MTC service type and manages them or the base station maintains a signaling channel or a bearer for transmitting a control message for MTC service.

In the idle state the base station neither stores nor manages information about the MTC device or information about the MTC service type and does not manage connection to a channel. That is in the idle state the base station recognizes only the fact that the MTC device has registered itself in the network and is located in an arbitrary area.

After setting a parameter for the MTC device service and deciding a state of the MTC device the base station notifies control information regarding the parameter and the decided state to the MTC device S .

The control information may include the state of the MTC device the identifier of the MTC device device group information encryption information related to an encryption key and software version information.

The MTC device which has received information about the parameter for the MTC device service and the state of the MTC device from the base station sets control parameters according to the received information and performs operation according to the decided state S .

In regard of a plurality of MTC devices for each the MTC devices may perform different operations according to state information received from the base station. For example MTC devices in the connected state search for or measure a base station a serving base station to which they belong neighboring base stations or adjacent MTC devices at regular time intervals. Also the MTC devices monitor downlink control information periodically or every transmission period for example Tm of according to the parameter set by the base station to check system information transmitted from the base station thereby updating system information and related software for MTC service.

Meanwhile MTC devices in the idle state monitor a paging message transmitted from the base station periodically wherein the paging message informs of a change of downlink reception related or MTC related control information. Also the MTC devices may perform a procedure of periodically monitoring signals from a base station to which they belong and neighboring base stations in order to support a mobility function as necessary.

If the MTC device generates data that has to be transmitted to the base station S the MTC device requests the base station to allocate an uplink radio resource for transmitting the data S .

At this time the MTC device may request the base station to allocate a radio resource through an arbitrary connection procedure that is applied to a mobile communication system. Also the MTC device may request the base station to allocate a radio resource through a different connection procedure according to the state of the MTC device decided in operations S and S. That is MTC devices that are in the idle state may use the arbitrary connection procedure and MTC devices that are in the connected state may use a predetermined connection procedure only for the MTC devices that are in the connected state as well as the arbitrary connection procedure. For example the MTC devices that are in the connected state may perform a resource allocation request procedure through a uplink control channel for a resource request allocated by the base station for an arbitrary MTC device or an arbitrary group of MTC devices or through a uplink connection channel dedicated to an MTC device a group of MTC devices .

In response to the resource allocation request from the MTC device the base station may transmit scheduling information for the requested radio resource or information for MTC service to the MTC device S . The MTC device which has received the scheduling information for the requested radio resource transmits the data through the corresponding uplink radio resource S .

Operations through may be selectively performed according to a method of transmitting scheduling information about a radio resource for transmission of MTC data for substantial resource allocation to the MTC device or the group of MTC devices a method of allocating an identifier s to the MTC device or the group of MTC devices etc. For example the MTC device which has received MTC control information as shown in in operation may perform operation directly without performing operations and for resource allocation to transmit data to the base station .

According to the current example an identifier that is different from a scheduling identifier for example a C RNTI for a general user terminal that is a non MTC terminal may be allocated to the MTC device the group of MTC devices . As a result since a significantly large number of MTC devices can be managed in a connected state it is possible to efficiently provide MTC service without requiring connection establishment for transmission and reception of MTC packet data validation of an MTC device a group of MTC devices an encryption procedure etc.

Referring to the base station includes an MTC information storage unit an MTC controller and a transceiver .

The MTC information storage unit may store various information required for providing MTC service. For example the MTC information storage unit may store at least one piece of information among software information for MTC service an identifier of at least one MTC device or at least one group of MTC devices and encoding information.

The MTC controller determines if MTC data that is to be transmitted to an MTC device is generated whether the location of a radio resource area for transmission of MTC data is variable in a transmission period. If the location of a radio resource area for transmission of MTC data is variable in a transmission period the MTC controller creates a control information block including MTC scheduling information and includes the control information block in a first downlink control resource area or a second downlink control resource area to configure a downlink frame.

Also the transceiver transmits the downlink frame configured by the MTC controller and receives signals transmitted from at least one MTC device.

The receiver receives a downlink frame from a base station. The controller searches for a control information block in a downlink control resource area of the received downlink frame determines whether the control information block is for MTC service or includes control information whose destination is a corresponding MTC device using an MTC device identifier or an identifier designated for MTC service scheduling and extracts MTC service packet data included in a radio resource for transmission of MTC data using the control information block according to the results of the determination.

If the control information block is for MTC service the controller acquires a radio resource for transmission of MTC data using the identifier designated for MTC service scheduling and demodulates and decodes MCT traffic data transmitted to the corresponding MTC device using the MTC device identifier.

Meanwhile if the control information block includes control information whose destination is the corresponding MTC device the controller demodulates and decodes MTC traffic data transmitted to the corresponding MTC device using the MTC device identifier.

Also the transmitter transmits an uplink frame to the base station and the controller may control the transmitter to transmit feedback information to the base station only when downlink packets transmitted from the base station have been successfully received.

If the location of the radio resource for transmission of MTC data is fixed according to another embodiment of the present invention the controller and the receiver of the MTC device may operate as follows 

That is in this case the receiver receives information about a location of a radio resource for transmission of MTC data from the base station through system information or a control message and the controller detects the location of the radio resource for transmission of MTC data from a downlink frame received from the base station and extracts MTC service packet data included in the radio resource for transmission of MTC data using the MTC device identifier.

The resource allocating method illustrated in may be performed by a base station. The following description relates to the case where the resource allocating method is performed by a base station however it is also possible that the resource allocating method is performed by another entity located in a network in connection to a base station.

If data that is to be transmitted to at least one MTC device is generated S the base station determines whether the location of a radio resource for transmission of MTC data is variable in a transmission period based on MTC information stored therein S . A procedure of determining whether the location of a radio resource for transmission of MTC data is variable may be omitted when the base station knows information about a fixed location of a radio resource for transmission of MTC data. Also MTC data that is to be transmitted to at least one MTC device may be received from the network or created by the base station.

If the location of the radio resource for transmission of MTC data is variable the base station generates a control information block including MTC scheduling information S .

Then the base station includes the control information block in a first downlink control resource area or a second downlink control resource area S and generates a downlink frame including a radio resource area for transmission of MTC data and at least one of the first downlink control resource area and the second downlink control resource area S .

Meanwhile if it is determined in operation S that the location of the radio resource for transmission of MTC data is fixed operation S of generating the downlink frame is directly performed without performing operation S of generating the control information block and operation S of including the control information block in the first or second downlink control resource area.

If the MTC device receives a downlink frame from a base station S the MTC device searches for a control information block in a downlink control resource area of the downlink frame S .

Then the MTC device determines whether the control information block is for MTC service or includes control information whose destination is the corresponding MTC device using an MTC device identifier or an identifier designated for MTC service scheduling S . In detail operation S may be performed by checking an identifier for example a C RNTI masked in the CRC bits of the control information block using several identifiers for example C RNTIs for MTC allocated to the MTC device that is an MTC device identifier an identifier designated for MTC service scheduling etc.

The MTC device extracts MTC service packet data included in a radio resource for transmission of MTC data using the control information block according to the results of the check.

In detail if the control information block is for MTC service that is if the control information block has been transmitted together with an MTC scheduling identifier the MTC device acquires scheduling information about a radio resource for transmission of MTC data using the identifier designated for MTC service scheduling S and demodulates and decodes MTC traffic data transmitted to the corresponding MTC device using the MTC device identifier S .

Here operation S corresponds to a procedure of acquiring demodulation and decoding information by using the MTC device identifier to check CRC masking of MTC data CRC masked with the MTC device identifier or check a scrambling sequence of MTC data scrambled with the MTC device identifier.

Meanwhile if the control information block includes control information whose destination is the MTC device that is if the control information block has been transmitted together with the MTC device identifier operation S of demodulating and decoding MTC traffic data transmitted to the corresponding MTC device using the MTC device identifier is performed.

While the example embodiments of the present invention and their advantages have been described in detail it should be understood that various changes substitutions and alterations may be made herein without departing from the scope of the invention.

