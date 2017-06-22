---

title: Voice over data telecommunications network architecture
abstract: The present invention describes a system and method for communicating voice and data over a packet-switched network that is adapted to coexist and communicate with a legacy PSTN. The system permits packet switching of voice calls and data calls through a data network from and to any of a LEC, a customer facility or a direct IP connection on the data network. The system includes soft switch sites, gateway sites, a data network, a provisioning component, a network event component and a network management component. The system interfaces with customer facilities (e.g., a PBX), carrier facilities (e.g., a LEC) and legacy signaling networks (e.g., SS7) to handle calls between any combination of on-network and off-network callers.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08693347&OS=08693347&RS=08693347
owner: Level 3 Communications, LLC
number: 08693347
owner_city: Broomfield
owner_country: US
publication_date: 20120914
---
This application is a continuation of co pending U.S. patent application Ser. No. 13 341 170 entitled Voice Over Data Telecommunications Network Architecture filed Dec. 30 2011 which is a continuation of U.S. patent application Ser. No. 11 781 098 entitled Voice Over Data Telecommunications Network Architecture filed Jul. 20 2007 now U.S. Pat. No. 8 089 958 which is a continuation of U.S. patent application Ser. No. 10 366 061 entitled Voice Over Data Telecommunication Network Architecture filed Feb. 12 2003 now U.S. Pat. No. 7 564 840 which is a continuation of U.S. patent application Ser. No. 09 197 203 now U.S. Pat. No. 6 614 781 entitled Voice Over Data Telecommunications Network Architecture filed Nov. 20 1998. This application of common assignee contains a related disclosure to U.S. Pat. No. 6 442 169 entitled System and Method for Bypassing Data From Egress Facilities. Both U.S. patent application Ser. No. 09 197 203 and U.S. Pat. No. 6 442 169 are incorporated herein by reference in their entirety. In addition this application is related to applications identified by U.S. patent application Ser. No. 11 781 067 now U.S. Pat. No. 8 036 214 and U.S. patent application Ser. No. 11 781 118 now U.S. Pat. No. 8 085 761 having common title and assignee.

The present invention relates generally to telecommunications networks and more particularly to a system and method for providing transmission for voice and data traffic over a data network including the signaling routing and manipulation of such traffic.

The present invention relates to telecommunications and in particular to voice and data communication operating over a data network. The Public Switched Telephone Network PSTN is a collection of different telephone networks owned by different companies which have for many years provided telephone communication between users of the network. Different parts of the PSTN network use different transmission media and compression techniques.

Most long distance calls are digitally coded and transmitted along a transmission line such as a T1 line or fiber optic cable using circuit switching technology to transmit the calls. Such calls are time division multiplexed TDM into separate channels which allow many calls to pass over the lines without interacting. The channels are directed independently through multiple circuit switches from an originating switch to a destination switch. Using conventional circuit switched communications a channel on each of the T1 lines along which a call is transmitted is dedicated for the duration of the call whether or not any information is actually being transmitted over the channel. The set of channels being used by the call is referred to as a circuit. 

Telecommunications networks were originally designed to connect one device such as a telephone to another device such as a telephone using switching services. As previously mentioned circuit switched networks provide a dedicated fixed amount of capacity a circuit between the two devices for the entire duration of a transmission session. Originally this was accomplished manually. A human operator would physically patch a wire between two sockets to form a direct connection from the calling party to the called party. More recently a circuit is set up between an originating switch and a destination switch using a process known as signaling.

Signaling sets up monitors and releases connections in a circuit switched system. Various signaling methods have been devised. Telephone systems formerly used in band signaling to set up and tear down calls. Signals of an in band signaling system are passed through the same channels as the information being transmitted. Early electromechanical switches used analog or multi frequency MF in band signaling. Thereafter conventional residential telephones used in band dual tone multiple frequency DTMF signaling to connect to an end office switch. Here the same wires and frequencies on the wires were used to dial a number using pulses or tones as are used to transmit voice information. However in band signaling permitted unscrupulous callers to use a device such as a whistle to mimic signaling sounds to commit fraud e.g. to prematurely discontinue billing by an interexchange carrier IXC also known as a long distance telephone company .

More recently to prevent such fraud out of band signaling systems were introduced. Out of band signaling uses a signaling network that is separate from the circuit switched network used for carrying the actual call information. For example integrated services digital network ISDN uses a separate channel a data D channel to pass signaling information out of band. Common Channel Interoffice Signaling CCIS is another network architecture for out of band signaling. A popular version of CCIS signaling is Signaling System 7 SS7 . SS7 is an internationally recognized system optimized for use in digital telecommunications networks.

SS7 out of band signaling provided additional benefits beyond fraud prevention. For example out of band signaling eased quick adoption of advanced features e.g. caller id by permitting modifications to the separate signaling network. In addition the SS7 network enabled long distance Equal Access i.e. 1 dialing for access to any long distance carrier as required under the terms of the modified final judgment MFJ requiring divestiture of the Regional Bell Operating Companies RBOCs from their parent company AT T.

An SS7 network is a packet switched signaling network formed from a variety of components including Service Switching Points SSPs Signaling Transfer Points STPs and Service Control Points SCPs . An SSP is a telephone switch which is directly connected to an SS7 network. All calls must originate in or be routed through an SSP. Calls are passed through connections between SSPs. An SCP is a special application computer which maintains information in a database required by users of the network. SCP databases may include for example a credit card database for verifying charge information or an 800 database for processing number translations for toll free calls. STPs pass or route signals between SSPs other STPs and SCPs. An STP is a special application packet switch which operates to pass signaling information.

The components in the SS7 network are connected together by links. Links between SSPs and STPs can be for example A B C D E or F links. Typically redundant links are also used for connecting an SSP to its adjacent STPs. Customer premises equipment CPE such as a telephone are connected to an SSP or an end office EO switch.

To initiate a call in an SS7 telecommunications network a calling party using a telephone connected to an originating EO switch dials a telephone number of a called party. The telephone number is passed from the telephone to the SSP at the originating EO referred to as the ingress EO of the calling party s local exchange carrier LEC . A LEC is commonly referred to as a local telephone company. First the SSP will process triggers and internal route rules based on satisfaction of certain criteria. Second the SSP will initiate further signaling messages to another EO or access tandem AT if necessary. The signaling information can be passed from the SSP to STPs which route the signals between the ingress EO and the terminating end office or egress EO. The egress EO has a port designated by the telephone number of the called party. The call is set up as a direct connection between the EOs through tandem switches if no direct trunking exists or if direct trunking is full. If the call is a long distance call i.e. between a calling party and a called party located in different local access transport areas LATAs then the call is connected through an inter exchange carrier IXC switch of any of a number of long distance telephone companies. Such a long distance call is commonly referred to as an inter LATA call. LECs and IXCs are collectively referred to as the previously mentioned public switched telephone network PSTN .

Emergence of competitive LECs CLECs was facilitated by passage of the Telecommunications Act of 1996 which authorized competition in the local phone service market. Traditional LECs or RBOCs are now also known as incumbent LECs ILECs . Thus CLECs compete with ILECs in providing local exchange services. This competition however has still not provided the bandwidth necessary to handle the large volume of voice and data communications. This is due to the limitations of circuit switching technology which limits the bandwidth of the equipment being used by the LECs and to the high costs of adding additional equipment.

Since circuit switching dedicates a channel to a call for the duration of the call a large amount of switching bandwidth is required to handle the high volume of voice calls. This problem is exacerbated by the fact that the LECs must also handle data communications over the same equipment that handle voice communications.

If the PSTN were converted to a packet switched network many of the congestion and limited bandwidth problems would be solved. However the LECs and IXCs have invested large amounts of capital in building upgrading and maintaining their circuit switched networks known as legacy networks and are unable or unwilling to jettison their legacy networks in favor of the newer more powerful technology of packet switching. Accordingly a party wanting to build a packet switched network to provide voice and data communications for customers must build a network that not only provides the desired functionality but also is fully compatible with the SS7 and other e.g. ISDN and MF switching networks of the legacy systems.

Currently internets intranets and similar public or private data networks that interconnect computers generally use packet switching technology. Packet switching provides for more efficient use of a communication channel as compared to circuit switching. With packet switching many different calls e.g. voice data video fax Internet etc. can share a communication channel rather than the channel being dedicated to a single call. For example during a voice call digitized voice information might be transferred between the callers only 50 of the time with the other 50 being silence. For a data call information might be transferred between two computers 10 of the time. With a circuit switched connection the voice call would tie up a communications channel that may have 50 of its bandwidth being unused. Similarly with the data call 90 of the channel s bandwidth may go unused. In contrast a packet switched connection would permit the voice call the data call and possibly other call information to all be sent over the same channel.

Packet switching breaks a media stream into pieces known as for example packets cells or frames. Each packet is then encoded with address information for delivery to the proper destination and is sent through the network. The packets are received at the destination and the media stream is reassembled into its original form for delivery to the recipient. This process is made possible using an important family of communications protocols commonly called the Internet Protocol IP .

In a packet switched network there is no single unbroken physical connection between sender and receiver. The packets from many different calls share network bandwidth with other transmissions. The packets are sent over many different routes at the same time toward the destination and then are reassembled at the receiving end. The result is much more efficient use of a telecommunications network than could be achieved with circuit switching.

Recognizing the inherent efficiency of packet switched data networks such as the Internet attention has focused on the transmission of voice information over packet switched networks. However such systems are not compatible with the legacy PSTN and therefore are not convenient to use.

One approach that implements voice communications over an IP network requires that a person dial a special access number to access an IP network. Once the IP network is accessed the destination or called number can be dialed. This type of call is known as a gateway type access call.

Another approach involves a user having a telephone that is dedicated to an IP network. This approach is inflexible since calls can only be made over the IP network without direct access to the PSTN.

What is needed is a system and method for implementing packet switched communications for both voice calls and data calls that do not require special access numbers or dedicated phones and permit full integration with the legacy PSTN.

The present invention is a system and method for communicating both voice and data over a packet switched network that is adapted to coexist and communicate with a PSTN. The system permits efficient packet switching of voice calls and data calls from a PSTN carrier such as for example a LEC IXC a customer facility or a direct IP connection on the data network to any other LEC IXC customer facility or direct IP connection. For calls from a PSTN carrier e.g. LEC or IXC the invention receives signaling from the legacy SS7 signaling network or the ISDN D channel or from inband signaling trunks. For calls from a customer facility data channel signaling or inband signaling is received. For calls from a direct IP connection on the data network signaling messages can travel over the data network. On the call destination side similar signaling schemes are used depending on whether the called party is on a PSTN carrier a customer facility or a direct IP connection to the data network.

The system includes soft switch sites gateway sites a data network a provisioning component a network event component and a network management component. The system of the invention interfaces with customer facilities e.g. a PBX carrier facilities e.g. a PSTN carrier a LEC e.g. ILECs and CLECs an independent telephone company ITC an IXC an intelligent peripheral or an enhanced service provider ESP and legacy signaling networks e.g. SS7 to handle calls between any combination of on network and off network callers.

The soft switch sites provide the core call processing for the voice network architecture. Each soft switch site can process multiple types of calls including calls originating from or terminating at off network customer facilities as well as calls originating from or terminating at on network customer facilities. Each soft switch site receives signaling messages from and sends signaling messages to the signaling network. The signaling messages can include for example SS7 integrated services digital network ISDN primary rate interface PRI and in band signaling messages. Each soft switch site processes these signaling messages for the purpose of establishing new calls through the data network and tearing down existing calls and in progress call control functions. Signaling messages can be transmitted between any combination of on network and off network callers.

Signaling messages for a call which either originates off network or terminates off network can be carried over the out of band signaling network of the PSTN via the soft switch sites. Signaling messages for a call which both originates on network and terminates on network can be carried over the data network rather than through the signaling network.

The gateway sites originate and terminate calls between calling parties and called parties through the data network. The soft switch sites control or manage the gateway sites. In a preferred embodiment the soft switch sites use a protocol such as for example the Internet Protocol Device Control IPDC protocol to manage network access devices in the gateway sites to request the set up and tear down of calls. However other protocols could be used including for example network access server messaging interface NMI and the ITU media gateway control protocol MGCP .

The gateway sites can also include network access devices to provide access to network resources i.e. the communication channels or circuits that provide the bandwidth of the data network . The network access devices can be referred to generally as access servers or media gateways. Exemplary access servers or media gateways are trunking gateways TGs access gateways AGs and network access servers NASs . The gateway sites provide for transmission of both voice and data traffic through the data network. The gateway sites also provide connectivity to other telecommunications carriers via trunk interfaces to carrier facilities for the handling of voice calls. The trunk interfaces can also be used for the termination of dial up modem data calls. The gateway sites can also provide connectivity via private lines and dedicated access lines DALs such as T1 or ISDN PRI facilities to customer facilities.

The data network connects one or more of the soft switch sites to one or more of the gateway sites. The data network routes data packets through routing devices e.g. routers to destination sites e.g. gateway sites and soft switch sites on the data network. For example the data network routes internet protocol IP packets for transmission of voice and data traffic from a first gateway site to a second gateway site. The data network represents any art recognized data network including the global Internet a private intranet or internet a frame relay network and an asynchronous transfer mode ATM network.

The network event component collects call events recorded at the soft switch sites. Call event records can be used for example for fraud detection and prevention and billing.

The provisioning event component receives provisioning requests from upstream operational support services OSS systems such as for example for order entry customer service and customer profile changes. The provisioning component distributes provisioning data to appropriate network elements and maintains data synchronization consistency and integrity across multiple soft switch sites.

The network management component includes a network operations center NOC for centralized network management. Each network element NE e.g. soft switch sites gateway sites provisioning and network event components etc. generates simple network management protocol SNMP events or alerts. The NOC uses the events generated by each network element to determine the health of the network and to perform other network management functions.

In a preferred embodiment the invention operates as follows to process for example a long distance call also known as a 1 call . First a soft switch site receives an incoming call signaling message from the signaling network. The soft switch site determines the type of call by performing initial digit analysis on the dialed number. Based upon the information in the signaling message the soft switch site analyzes the initial digit of the dialed number of the call and determines that it is a 1 call. The soft switch site then queries a customer profile database to retrieve the originating trigger plan associated with the calling customer. The query can be made using for example the calling party number provided in the signaling message from the signaling network. This look up in the customer profile database returns subscription information. For example the customer profile may indicate that the calling party has subscribed to an account code verification feature that requires entry of an account code before completion of the call. In this case the soft switch site will instruct the gateway site to collect the account code digits entered by the calling party. Assuming that the gateway site collects the correct number of digits the soft switch site can use the customer profile to determine how to process the received digits. For account code verification the soft switch site verifies the validity of the received digits.

Verification can result in the need to enforce a restriction such as a class of service COS restriction COSR . In this example the soft switch site can verify that the account code is valid but that it requires that an intrastate COSR should be enforced. This means that the call is required to be an intrastate call to be valid. The class of service restriction logic can be performed within the soft switch site using for example pre loaded local access and transport areas LATAs and state tables. The soft switch would then allow the call to proceed if the class of service requested matches the authorized class of service. For example if the LATA and state tables show that the LATA of the originating party and the LATA of the terminating party are in the same state then the call can be allowed to proceed. The soft switch site then completes customer service processing and prepares to terminate the call. At this point the soft switch site has finished executing all customer service logic and has a 10 digit dialed number that must be terminated. To accomplish the termination the soft switch site determines the terminating gateway. The dialed number i.e. the number of the called party dialed by the calling party is used to select a termination on the data network. This termination may be selected based on various performance availability or cost criteria. The soft switch site then communicates with a second soft switch site associated with the called party to request that the second soft switch site allocate a terminating circuit or trunk group in a gateway site associated with the called party. One of the two soft switch sites can then indicate to the other the connections that the second soft switch site must make to connect the call. The two soft switch sites then instruct the two gateway sites to make the appropriate connections to set up the call. The soft switch sites send messages to the gateway sites through the data network using for example IPDC protocol commands. Alternately a single soft switch can set up both the origination and termination.

The present invention provides a number of important features and advantages. First the invention uses application logic to identify and direct incoming data calls straight to a terminating device. This permits data calls to completely bypass the egress end office switch of a LEC. This results in significant cost savings for an entity such as an internet service provider ISP ILEC or CLEC. This decrease in cost results partially from bypass of the egress ILEC end office switch for data traffic.

A further advantage for ISPs is that they are provided data in the digital form used by data networks e.g. IP data packets rather than the digital signals conventionally used by switched voice networks e.g. PPP signals . Consequently the ISPs need not perform costly modem conversion processes that would otherwise be necessary. The elimination of many telecommunications processes frees up the functions that ISPs themselves would have to perform to provide Internet access.

Another advantage of the present invention is that voice traffic can be transmitted transparently over a packet switched data network to a destination on the PSTN.

Yet another advantage of the invention is that a very large number of modem calls can be passed over a single channel of the data network including calls carrying media such as voice bursty data fax audio video or any other data formats.

Further features and advantages of the invention as well as the structure and operation of various embodiments of the invention are described in detail below with reference to the accompanying figures.

In the figures like reference numbers generally indicate identical functionally similar and or structurally similar elements. The figure in which an element first appears is indicated by the leftmost digit s in the reference number.

This section provides a high level description of the voice over IP network architecture according to the present invention. In particular a structural implementation of the voice over IP VOIP network architecture is described at a high level. Also a functional implementation for this structure is described at a high level. This structural implementation is described herein for illustrative purposes and is not limiting. In particular the process described in this section can be achieved using any number of structural implementations one of which is described in this section. The details of such structural implementations will be apparent to persons skilled in the relevant arts based on the teachings contained herein.

Included in are calling parties and called parties . Calling parties are homed to gateway site . Calling parties are homed to gateway site . Called parties are homed to gateway site . Calling party can be connected to gateway site via trunks from carrier facility to gateway site . Similarly called party can be connected to gateway site via trunks from carrier facility to gateway site . Calling party can be connected to gateway site via a private line or dedicated access line DAL from customer facility to gateway site . Similarly called party can be connected to gateway site via a private line or a DAL from customer facility to gateway site .

Calling party and called party are off network meaning that they are connected to gateway sites via the Public Switched Telephone Network PSTN facilities. Calling party and called party are on network meaning that connect to gateway sites as direct customers.

Soft switch sites provide the core call processing for the voice network architecture. Soft switch sites can process multiple types of calls. First soft switch sites can process calls originating from or terminating at on network customer facilities . Second soft switch sites can process calls originating from or terminating at off network customer facilities .

Soft switch sites receive signaling messages from and send signaling messages to signaling network . For example these signaling messages can include SS7 primary rate interface PRI and in band signaling messages. Soft switch sites process these signaling messages for the purpose of establishing new calls from calling parties through data network to called parties . Soft switch sites also process these signaling messages for the purpose of tearing down existing calls established between calling parties and called parties through data network .

In one embodiment signaling messages for a call which either originates from an off network calling party or terminates to an off network called party can be carried over out of band signaling network from the PSTN to soft switches .

In another embodiment signaling messages for a call which either originates from an on network calling party or terminates to on network called party can be carried in band over data network or over a separate data network to soft switch sites rather than through signaling network .

Soft switches sites can be collocated or geographically diverse. Soft switch sites can also be connected by redundant connections to data network to enable communication between soft switches .

Soft switch sites use other voice network components to assist with the processing of the calls. For example gateway sites provide the means to originate and terminate calls on PSTN. In a preferred embodiment soft switch sites use the Internet Protocol Device Control IPDC protocol to control network access devices known as media gateways in gateway sites and to request for example the set up and tear down of calls. The IPDC protocol is described below with reference to Tables 144 185. Alternatively any protocol understood by those skilled in the art can be used to control gateway sites . One example of an alternative protocol is the Network Access Server NAS Messaging Interface NMI Protocol discussed in U.S. patent application entitled System and Method for Bypassing Data from Egress Facilities filed on Jul. 20 2007 application Ser. No. 12 781 801 the contents of which are incorporated herein by reference in their entirety. Another example of protocol is the Media Gateway Control Protocol MGCP from the Internet Engineering Task Force IETF .

Soft switch sites can include other network components such as a soft switch which more recently can also be known as a media gateway controller or other network devices.

Gateway sites provide the means to originate and terminate calls between calling parties and called parties through data network . For example calling party can originate a call terminated to off network called party which is homed to gateway site via carrier facility .

Gateway sites can include network access devices to provide access to network resources. An example of a network access device is an access server which is more recently commonly known as a media gateway. These devices can include trunking gateways access gateways and network access servers. Gateway sites provide for transmission of for example both voice and data traffic through data network .

Gateway sites are controlled or managed by one or more soft switch sites . As noted soft switch sites can communicate with gateway sites via the IPDC NMI MGCP or alternative protocols.

Gateway sites can provide trunk interfaces to other telecommunication carriers via carrier facilities for the handling of voice calls. The trunk interfaces can also be used for the termination of dial up modem data calls. Gateway sites can also provide private lines and dedicated access lines such as T1 or ISDN PRI facilities to customer facilities . Examples of customer facilities are customer premises equipment CPE such as for example a private branch exchange PBX .

Gateway sites can be collocated or geographically diverse from one another or from other network elements e.g. soft switch sites . Gateway sites can also be connected by redundant connections to data network to enable communication with and management by soft switches .

Data network connects one or more soft switch sites to one or more gateway sites . Data Network can provide for routing of data through routing devices to destination sites on data network . For example data network can provide for routing of internet protocol PP packets for transmission of voice and data traffic from gateway site to gateway site . Data Network represents any art recognized data network. One well known data network is the global Internet. Other examples include a private intranet a packet switched network a frame relay network and an asynchronous transfer mode ATM network.

Signaling network is an out of band signaling network providing for transmission of signaling messages between the PSTN and soft switch sites . For example signaling network can use Common Channel Interoffice Signaling CCIS which is a network architecture for out of band signaling. A popular version of CCIS signaling is Signaling System 7 SS7 . SS7 is an internationally recognized system optimized for use in digital telecommunications networks.

Network event component provides for collection of call events recorded at soft switch sites . Call event records can be used for example for fraud detection and prevention traffic reporting and billing.

Provisioning component provides several functions. First provisioning component receives provisioning requests from upstream operational support services OSS systems for such items as order entry customer service and customer profile changes. Second provisioning component distributes provisioning data to appropriate network elements. Third provisioning component maintains data synchronization consistency and integrity across multiple soft switch sites .

Network management component can include a network operations center NOC for centralized network management. Each network element NE of block diagram can generate simple network management protocol SNMP events or alerts. The NOC uses the events generated by a NE to determine the health of the network and to perform other network management functions.

The following operational flows describe an exemplary high level call scenario for soft switch sites and is intended to demonstrate at a high architectural level how soft switch sites process calls. The operational flow of the present invention is not to be viewed as limited to this exemplary illustration.

As an illustration depicts a simple operational call flow chart describing how soft switch sites can process a long distance call also known as a 1 call. The operational call flow of begins with step in which a soft switch site receives an incoming signaling message. The call starts by soft switch site receiving an incoming signaling message from carrier facility via signaling network indicating an incoming call from calling party .

In step the soft switch site determines the type of call by performing initial digit analysis. Based upon the information in the signaling message the soft switch site analyzes the initial digit of the dialed number of the call and determines that it is a 1 call.

In step soft switch site can select a route termination based on the dialed number i.e. the number of called party dialed by calling party using least cost routing. This route termination can involve termination off data network or off onto another data network. Soft switch site can then communicate with soft switch site to allocate a terminating circuit in gateway site for this call.

In step soft switch site can indicate connections to be made to complete the call. Soft switch site or soft switch site can return a termination that indicates the connections that must be made to connect the call.

In step soft switch sites instruct the gateway sites to make connections to set up the call. Soft switch sites can send messages through data network e.g. using IPDC protocol commands to gateway sites to instruct the gateway sites to make the necessary connections for setting up the call origination from calling party the call termination to called party and the connection between origination and termination.

In step soft switch sites generate and send network events to a repository. Soft switch sites can generate and send network events to network event component that are used for example in detecting and preventing fraud and in performing billing.

In step network management component monitors the telecommunications network . All network elements create network management events such as SNMP protocol alerts or events. Network management component can monitor SNMP events to enable management of network resources.

The operational call flow of begins with step in which a soft switch site receives an incoming signaling message. The call starts by soft switch site receiving an incoming signaling message from carrier facility via signaling network indicating an incoming call from calling party .

In step the soft switch site determines the type of call by performing initial digit analysis. Based upon the information in the signaling message the soft switch site analyzes the initial digit of the dialed number of the call and determines that it is a 1 call.

In step the soft switch site queries a customer profile database to retrieve the originating trigger plan associated with the calling customer. With a 1 type of call the logic within the soft switch knows to query the customer profile database within soft switch site to retrieve the originating trigger plan for the calling party. The step query can be made using the calling party number. The customer profile lookup is performed using as the lookup key the originating number i.e. the number of calling party provided in the signaling message from signaling network .

In step the lookup returns subscription information. For example the customer profile can require entry of an account code. In this example the customer profile lookup can return an indication that the customer i.e. calling party has subscribed to an account code verification feature. A class of service restriction can also be enforced but this will not be known until account code verification identifies an associated account code.

In step soft switch site completes customer service processing and prepares to terminate the call. At this point soft switch site has finished executing all customer service logic and has a 10 digit dialed number that must be terminated.

In step soft switch site can select a route termination based on the dialed number i.e. the number of called party dialed by calling party using least cost routing. This route termination can involve termination off data network or off onto another data network. Soft switch site can then communicate with soft switch site to allocate a terminating circuit in gateway site for this call.

In step soft switch site can indicate connections to be made to complete the call. Soft switch site or soft switch site can return a termination that indicates the connections that must be made to connect the call.

In step soft switch sites instruct the gateway sites to make connections to set up the call. Soft switch sites can send messages through data network e.g. using IPDC protocol commands to gateway sites to instruct the gateway sites to make the necessary connections for setting up the call origination from calling party the call termination to called party and the connection between origination and termination.

In step soft switch sites generate and send network events to a repository. Soft switch sites can generate and send network events to network event component that are used for example in detecting and preventing fraud and in performing billing.

In step network management component monitors the telecommunications network . All network elements create network management events such as SNMP protocol alerts or events. Network management component can monitor SNMP events to enable management of network resources.

The operational call flow of begins with step in which a soft switch site receives an incoming signaling message. The call starts by soft switch site receiving an incoming signaling message from carrier facility via signaling network indicating an incoming call from calling party .

In step the soft switch site determines the type of call by performing initial digit analysis. Based upon the information in the signaling message the soft switch site analyzes the initial digit of the dialed number of the call and determines that it is a 1 call.

In step the soft switch site queries a customer profile database to retrieve the originating trigger plan associated with the calling customer. With a 1 type of call the logic within the soft switch knows to query the customer profile database within soft switch site to retrieve the originating trigger plan for the calling party. The step query can be made using the calling party number. The customer profile lookup is performed using as the lookup key the originating number i.e. the number of calling party provided in the signaling message from signaling network .

In step the lookup returns subscription information. For example the customer profile can require entry of an account code. In this example the customer profile lookup can return an indication that the customer i.e. calling party has subscribed to an account code verification feature. A class of service restriction can also be enforced but this will not be known until account code verification identifies an associated account code.

In step soft switch site instructs gateway site to collect account codes. Using the information in the customer profile soft switch site can use the IPDC protocol to instruct gateway site to collect a specified number of digits from calling party .

In step soft switch site determines how to process received digits. Assuming gateway site collects the correct number of digits soft switch site can use the customer profile to determine how to process the received digits. For account code verification the customer profile can specify whether the account code needs to be validated.

In step soft switch site verifies the validity of the received digits. If the account code settings in the customer profile specify that the account code must be verified and forced to meet certain criteria soft switch site performs two functions. Because verify was specified soft switch site queries a database to verify that the collected digits meet such criteria i.e. that the collected digits are valid. Because forced was specified soft switch site also forces the calling customer to re enter the digits if the digits were not valid.

In step verification can result in the need to enforce a restriction such as a class of service COS restriction COSR . In this example soft switch site can verify that the code is valid but that it requires for example that an intrastate COSR should be enforced. This means that the call is required to be an intrastate call to be valid. The class of service restriction logic can be performed within soft switch site using for example pre loaded local access and transport areas LATAs and state tables.

If project account codes PACs are not used class of service COS restrictions can be applied based on originating ANI or ingress trunk group.

In step soft switch allows the call to proceed if the class of service requested is permitted. For example if the LATA and state tables show that the LATAs of originating party i.e. calling party and terminating party i.e. called party must be and are in the same state then the call can be allowed to proceed.

In step soft switch site completes customer service processing and prepares to terminate the call. At this point soft switch site has finished executing all customer service logic and has a 10 digit dialed number that must be terminated.

In step soft switch site can select a route termination based on the dialed number i.e. the number of called party dialed by calling party using least cost routing. This route termination can involve termination off data network or off onto another data network. Soft switch site can then communicate with soft switch site to allocate a terminating circuit in gateway site for this call.

In step soft switch site can indicate connections to be made to complete the call. Soft switch site or soft switch site can return a termination that indicates the connections that must be made to connect the call.

In step soft switch sites instruct the gateway sites to make connections to set up the call. Soft switch sites can send messages through data network e.g. using IPDC protocol commands to gateway sites to instruct the gateway sites to make the necessary connections for setting up the call origination from calling party the call termination to called party and the connection between origination and termination.

In step soft switch sites generate and send network events to a repository. Soft switch sites can generate and send network events to network event component that are used for example in detecting and preventing fraud and in performing billing.

In step network management component monitors the telecommunications network . All network elements create network management events such as SNMP protocol alerts or events. Network management component can monitor SNMP events to enable management of network resources.

The intermediate level description and specific implementation example embodiments sections below will describe additional details of operation of the invention. For example how soft switch site performs initial digit analysis to identify the type of call and how to process the call will be discussed further. The sections also provide details regarding how soft switch sites interact with the other components of the voice network architecture.

This section provides an intermediate level description of the VOIP network architecture according to the present invention. A structural implementation of the VOIP network architecture is described at an intermediate level. Also a functional implementation for this structure is described at an intermediate level. This structural implementation is described herein for illustrative purposes and is not limiting. In particular the process described in this section can be achieved using any number of structural implementations one of which is described in this section. The details of such structural implementations will be apparent to persons skilled in the relevant arts based on the teachings contained herein.

Soft switch site includes soft switch SS7 gateways service control point SCP configuration server configuration database CDB route server signal transfer points STPs and regional network event collection point RNECP . Table 1 below describes the functions of these network elements in detail.

Gateway site includes trunking gateway TG access gateway AG network access server NAS digital cross connect system DACS and announcement server ANS . TG AG and NAS are collectively known as access server . Similarly gateway site includes TG AG NAS DACS and ANS . TG AG and NAS are collectively known as access server . Gateway sites provide trunk private line and dedicated access line connectivity to the PSTN. Table 2 below describes the functions of these network elements in detail.

Data network provides the network bandwidth over which calls can be connected through the telecommunications system. Data network can be for example a packet switched data network including network routers for routing traffic through the network.

Signaling network includes signal transfer points STPs and signaling control points SCPs associated with each network node. Table 3 below describes the functions of these network elements in detail.

Network management component includes the means to manage a network. Network management component gathers events and alarms related to network events. For example event logs can be centrally managed from a network operations center NOC . Alerts and events can be communicated to the NOC via the simple network management protocol SNMP . Table 4 below describes the functions of these network elements in detail.

Network event component includes master network event database MNEDB . Table 5A below describes the functions of this network element in detail.

Provisioning component includes data distributor DD . Table 5B below describes the functions of this network element in detail.

The following operational flow describes an exemplary intermediate level call scenario intended to demonstrate at an intermediate architectural level how call processing is handled. The operational flow of the present invention is not to be viewed as limited to this exemplary illustration.

Included in call flow is a description of how soft switch can process a 1 long distance call that uses project account codes PACs with class of service COS restrictions. Call flow also assumes that the origination and termination for the call uses SS7 signaling i.e. that the call comes into network via trunks from carrier facilities to trunking gateways .

Exemplary call flow begins with step . In step soft switch receives an incoming IAM signaling message from an SS7 GW signaling an incoming call from calling party on carrier facility of a co carrier.

In step soft switch sends IPDC commands to trunking gateway to set up a connection e.g. a DS0 or DS1 circuit between carrier facility and TG described in the received IAM signaling message. In step trunking gateway sends an acknowledgement message to soft switch .

Based upon the information in the IAM message soft switch performs initial digit analysis on the dialed number i.e. the number of called party and determines that the incoming call is a 1 call.

In step application program logic within soft switch determines that with this type of call i.e. a 1 call soft switch should query a customer profile database within configuration server to retrieve the originating customer trigger plan for calling party .

The customer profile lookup is performed in configuration server using the originating automatic number identification ANI of calling party as the lookup key.

In step the customer profile lookup returns to soft switch an indication that the calling party has subscribed to project account codes PAC . Examples of PACs include billing codes. They provide a mechanism for a network customer such as a law firm to keep an accounting of which of their clients to bill. Example call flow will also perform a class of service COS restriction but this will not be known by soft switch until account code verification identifies an associated account code requiring the COS restriction. Alternatively the customer profile information can reside in route server enabling route server to perform the functions of configuration server in addition to its own functions.

In step using the information in the customer profile i.e. customer trigger plans of configuration server soft switch uses the IPDC protocol to instruct trunking gateway to collect the specified number of digits representing the project account code from calling party .

In step the digits are sent from trunking gateway to soft switch . Assuming that trunking gateway collected the correct number of digits soft switch uses the customer profile of configuration server to determine how to process the received digits. For project account codes PACs the customer profile in configuration server specifies whether the project account code needs to be validated.

If the project account code settings in the customer profile of configuration server specify that the project account code is verified and forced then soft switch in step can query SCP with the collected digits to verify that they are valid. Table 129 below provides alternative PAC settings.

In step SCP returns an indication that the project account code is valid and it requires that an intrastate class of service COS restriction should be enforced. The class of service COS restriction logic can be performed within soft switch using pre loaded LATA and state tables from configuration server .

If the LATA and state tables from configuration server show that the originating LATA i.e. the LATA of calling party and the terminating LATA i.e. the LATA of called party are in the same state then the call is allowed to proceed.

At this point soft switch has finished executing all customer service logic and has a 10 digit DDD number i.e. the phone number of called party that must be terminated.

In step soft switch queries route server to receive a call route and to allocate circuits to connect the call. Route server is responsible for using the DDD number to select a least cost route through data network and allocating a terminating circuit for this call.

Additional information on how soft switch interacts with route server and terminating soft switch is described in the Specific Implementation Example Embodiments Section below in the section entitled Route Server.

In step route server returns a route that indicates the connections that soft switch must make to connect the call.

In step soft switch communicates with soft switch to allocate ports in trunking gateway of gateway site for termination of the call. Soft switch is located in a central soft switch site . In step soft switch queries port status of route server to identify available ports in trunking gateway . In step route server returns an available port to soft switch . In steps and soft switch communicates with trunking gateway to allocate a port for termination of the call to called party .

In steps and soft switch communicates with trunking gateway in order to notify trunking gateway to set up an RTP session i.e. an RTP over UDP over IP session with trunking gateway and to permit call traffic to be passed over data network .

The Specific Implementation Example Embodiments Section in the next section describes additional information about for example how soft switch performs initial digit analysis to identify the type of call and how to process the call. The next section also describes how soft switch interacts with other components of the voice network architecture in transmitting the call.

Various embodiments related to structures and operations between these structures described above are presented in this section and its subsections . These embodiments are described herein for purposes of illustration and not limitation. The invention is not limited to these embodiments. Alternate embodiments including equivalents extensions variations deviations etc. of the embodiments described herein will be apparent to persons skilled in the relevant arts based on the teachings contained herein. The invention is intended and adapted to include such alternate embodiments.

Specifically this section provides a detailed description of the VOIP network architecture according to the present invention. A structural implementation of the VOIP network architecture is described at a low level. Also a functional implementation for this structure is described at a low level.

Telecommunications network also includes a plurality of gateway sites that may be collocated or geographically diverse. These gateway sites include gateway sites and

Data network can route both signaling and transport traffic between the regional soft switch sites and regional gateway sites. For example data network can be used to route traffic between western soft switch site and gateway site . Signaling and transport traffic can also be segregated and sent over separate data networks. As those skilled in the art will recognize data network can be used to establish a data or voice connection among any of the aforementioned gateway sites and under the control of any of the aforementioned soft switch sites and .

Western soft switch site includes soft switch soft switch and soft switch . Soft switches can be collocated or geographically diverse. Soft switches provide the features of redundancy and high availability.

Failover mechanisms are enabled via this architecture since the soft switches can act as one big switch. Soft switches can intercommunicate via the inter soft switch communication protocol permitting access servers to reconnect from one soft switch to another.

Western soft switch site includes SS7 gateway GW configuration server configuration database CS CDB and route server RS . To provide high availability and redundancy western soft switch site includes a redundant SS7 GW a redundant CS CDB and a redundant RS. Specifically western soft switch site includes SS7 GW CS CDB and RS

Soft switches and are connected to SS7 GWs CS CDBs and RSs via redundant ethernet switches ESs having multiple redundant paths. This architecture enables centralization of SS7 interconnection to gain economies of scale from use of a lesser number than conventionally required of links to signaling network to be shared by many access servers in gateway sites. ESs also provide connectivity to routers Rs . Routers respectively provide redundant connectivity between redundant ESs and data network . A s noted included in telecommunications network are central soft switch site and eastern soft switch site . Central soft switch site and eastern soft switch site respectively include identical configurations to the configuration of western soft switch site . Central soft switch site includes SS7 GWs CS CDBs RSs soft switches ESs and Rs . Similarly eastern soft switch site includes SS7 GWs CS CDBs RSs soft switches ESs and Rs and .

Gateway site includes TG NAS AG and DACS . Gateway sites and have similar configurations to gateway site . Gateway site includes TG NAS AG and DACS . Gateway site includes TG NAS AG and DACS . Finally gateway site includes TG NAS AG and DACS . The details of gateway site and will be further described below with reference to .

Referring back to soft switch provides the call processing function for telecommunications network . Call processing refers to the handling of voice and data calls. There are a number of important call processing functions handled by soft switch . Soft switch processes signaling messages used for call setup and call tear down. These signaling messages can be processed by in band of out of band signaling. For an example of out of band signaling SS7 signaling messages can be transmitted between signaling network and soft switch . Soft switch refers to soft switches and . 

Another call processing function performed by soft switch is preliminary digit analysis. Preliminary digit analysis is performed to determine the type of call arriving at soft switch . Examples of calls include toll free calls 1 calls 0 calls 011 calls and other calls recognized by those skilled in the art.

One important feature of soft switch is communicating with CS CDB to retrieve important customer information. Specifically soft switch queries CS CDB to retrieve a customer trigger plan. The customer trigger plan effectively identifies the service logic to be executed for a given customer. This trigger plan is similar to a decision tree pertaining to how a call is to be implemented. Subsequently soft switch executes the customer trigger plan. This includes the processing of special service calls requiring external call processing i.e. call processing that is external to the functions of telecommunications network .

Another important function soft switch is communicating with RS to provide network routing information for a customer call. For example soft switch can query RS to retrieve the route having the least cost from an off network calling party homed to gateway site to an off network called party homed to gateway site over data network . Upon finding the least cost route soft switch allocates ports on TGs . As described in detail below soft switch can also be used to identify the least cost route termination and allocate gateway ports over AGs between an on network calling party homed to gateway site and an on network called party homed to gateway site .

Soft switch also communicates with AGs TGs and NASs over data network . Although AGs TGs and NASs can communicate with a plurality of soft switches as illustrated in these network nodes referred to collectively as access servers and are respectively assigned to a primary soft switch. This primary soft switch e.g. soft switch assumes a primary responsibility or control of the access servers. In addition the access servers can be as respectively assigned to secondary switches which control the access servers in the event that the primary soft switch is unavailable.

Referring back to western soft switch site central soft switch site and eastern soft switch site are geographically diverse. For example western soft switch site can be a soft switch site located in San Diego Calif. Central soft switch site can be a soft switch site located in Denver Colo. Eastern soft switch site can be a soft switch site located in Boston Mass.

It is permissible that additional network nodes are provided at any of soft switch sites and . For example additional elements including e.g. SS7 GW CDB and RS can be collocated at western soft switch site . Examples of other supporting elements of western soft switch site are an announcement server ANS a network event collection point NECP an SCP and on network STPs. Referring to the more detailed implementation of telecommunications network includes ANSs NECP SCP and STPs .

Soft switch interfaces with RNECP over interface . In an example embodiment interface is a TCP IP connection.

Soft switch interfaces with route server over interface . In an example embodiment interface is a TCP IP connection.

Soft switch interfaces with SCP over interface . In an example embodiment interface is a TCP IP connection.

Soft switch interfaces with announcement servers over interface . In an example embodiment interface can include the IPDC protocol used over a TCP IP connection.

Soft switch interfaces with TGs over interface . In an example embodiment interface can include the IPDC protocol used over a TCP IP connection.

Soft switch interfaces with AGs over interface . In an example embodiment interface can include the IPDC protocol used over a TCP IP connection.

In one embodiment soft switch is an application software program running on a computer. The structure of this exemplary soft switch is an object oriented programming model discussed below with reference to .

Another interface to soft switch not shown is a man machine interface or maintenance and monitoring interface MMI . MMI can be used as a direct controller for management and machine actions. It should be noted that this is not intended to be the main control interface but is rather available to accommodate the need for on site emergency maintenance activities.

Yet another interface permits communication between soft switches . A soft switch to soft switch interface will be described further with reference to . A soft switch to soft switch interface permits communication between the soft switches that control the originating call half and terminating call half of call flow . The soft switch to soft switch interface allows soft switches to set up tear down and manage voice and data calls. Soft switch to soft switch interface can allow for a plurality of inbound and outbound signaling types including for example SS7 ISDN and in band E M signaling.

In telephony E M is a trunking arrangement generally used for two way i.e. either side may initiate actions switch to switch or switch to network connections. E M signaling refers to an arrangement that uses separate leads called respectively the E lead and the M lead for signaling and supervisory purposes. The near end signals the far end by applying 48 volts DC VDC to the M lead which results in a ground being applied to the far end s E lead. When 48 VDC is applied to the far end M lead the near end E lead is grounded. E lead originally stood for ear i.e. when the near end E lead was grounded the far end was calling and wanted your ear. M originally stood for mouth because when the near end wanted to call i.e. to speak to the far end 48 VDC was applied to that lead.

When a PBX wishes to connect to another PBX directly or to a remote PBX or to an extension telephone over a leased voice grade line e.g. a channel on a T 1 the PBX can use a special line interface. This special line interface is quite different from that which the PBX uses to interface to directly attached phones. The basic reason for the difference between a normal extension interface and a long distance interface is that the respective signaling requirements differ. This is true even if the voice signal parameter such as level and two wire four wire remain the same. When dealing with tie lines or trunks it is costly inefficient and too slow for a PBX to do what an extension telephone would do i.e. to go off hook wait for a dial tone dial wait for ringing to stop etc. The E M tie trunk interface device is a form of standard that exists in the PBX T 1 multiplexer voice digitizer telephone company world. E M signaling can take on a plurality of forms. At least five different versions exist. E M signaling is the most common interface signaling method used to interconnect switching signaling systems with transmission signaling systems.

The sample configuration depicted in can use a soft switch to soft switch protocol. In the access servers depicted are trunking gateways . TGs are connected to the switch circuit network SCN i.e. signaling network via SS7 trunks ISDN trunks and in band trunks. The originating soft switch can receive a call over any of these trunks. The signaling information from these SS7 ISDN and in band trunks is processed by soft switch to establish the originating call half. The signaling information processed by soft switch can be used to determine the identity of terminating soft switch . The identity of terminating soft switch is required to complete the call.

Originating soft switch can then communicate the necessary information to complete the call via an inter soft switch communication ISSC protocol. Terminating soft switch can be required to be able to establish the terminating call half on any of the supported trunk types. The ISSC protocol can use a message set that is structured similarly to the IPDC protocol message set. The messages can contain a header followed by a number of tag length value attributes. The incoming signaling message for the call being placed can be carried in a general data block of one of the attribute value pairs AVPs . The other AVPs can contain additional information necessary to establish a voice over IP connection between the originating and terminating ends of the call.

SS7 gateways GWs will now be described further with reference to and . In SS7 GWs receive signaling messages from signaling network and communicate these messages to soft switch . Specifically for SS7 signaled trunks SS7 GWs can receive SS7 ISUP messages and transfer them to soft switch . SS7 GWs can also receive signaling messages from soft switch and send SS7 ISUP messages out to signaling network .

In an example embodiment SS7 GWs can be deployed in a two 2 computing element CE cluster depicted in . SS7 GWs in two CE cluster can fully load share. SS7 GWs can intercommunicate as represented by connection to balance their loads. Load sharing results in a completely fault resilient hardware and software system with no single point of failure. Each SS7 GW can have for example six two port cards for a total of twelve links to signaling network .

In an example embodiment SS7 GWs are application programs running on a computer system. An exemplary application program providing SS7 GW functionality is OMNI SIGNALWARE OMNI available from DGM S of Mount Laurel N.J. OMNI is a telecommunications middleware product that runs on a UNIX operating system. An exemplary operating system is the SUN UNIX available from SUN Microsystems Inc. of Palo Alto Calif. The core of OMNI resides logically below the service applications providing a middleware layer upon which telecommunications applications can be efficiently deployed. Since the operating system is not encapsulated service applications have direct access to the entire operating environment. Because of OMNI s unique SIGNALWARE architecture OMNI has the ability to simultaneously support variants of SS7 signaling technology ITU T ANSI China and Japan .

The SIGNALWARE architecture core is composed of the Message Transfer Part MTP Layer 2 and Layer 3 and Service Connection Control Part SCCP . These core protocols are supplemented with a higher layer of protocols to meet the needs of a target application or service. OMNI supports multiple protocol stacks simultaneously each potentially with the point code format and protocol support of one of the major SS7 variants.

OMNI SIGNALWARE Application Programming Interfaces APIs are found on the higher layers of the SS7 protocol stack. OMNI APIs include ISDN User Part ISUP Telephony User Part TUP Transaction Capabilities Application Part TCAP Global System for Mobile Communications Mobile Application Part GSM MAP EIA TIA Interim Standard 41 IS 41 MAP Advanced Intelligent Network AIN and Intelligent Network Application Part INAP .

Based upon an SS7 network design a pair of SS7 gateways receive all signaling traffic for the trunking gateway TG circuits serviced by the soft switches at a single soft switch site. Specifically a pair of SS7 GWs receive all signaling traffic for circuits serviced by soft switch site . Signals serviced by soft switch site enter telecommunications network from gateway sites .

In an example embodiment 96 circuits are serviced by each gateway site . Gateway site includes TGs . Gateway site includes TGs . Gateway site includes TGs .

A circuit is identified by a circuit identification code CIC . TG includes line card access to a plurality of circuits including CICs of gateway site . TG provides line card access to CICs of gateway site . TG provides line card access to CICs . TG provides line card access to CICs of gateway site . TG provides line card access to CICs . TG provides line card access to CICs of gateway site . Thus CICs and CICs are the trunking gateway circuits serviced by soft switch site .

In an example embodiment soft switches are partitioned such that any single soft switch will only service a subset of circuits serviced at a given soft switch site. For example soft switch can service CICs while soft switch services CICs and CICs and soft switch services CICs . In order to assure that all signaling messages for a particular call get to the correct one of soft switches it is necessary to partition SS7 signaling across the available soft switches based upon the circuits that each soft switch services.

It is much more efficient to run SS7 links to soft switches than to each individual access server compare to the conventional approach requiring an SS7 link to each SSP . Centralization of SS7 signaling traffic interconnection enables benefits from economies of scale by requiring less SS7 interconnection links.

An exemplary technique for distributing circuits across soft switches is based upon the originating point code OPC destination point code DPC and CIC. OPC represents the originating point code for a circuit group i.e. the point code of a local exchange carrier LEC switch or signal point SP . For example the LEC providing CICs and CICs can have an OPC of value . The LEC providing CICs and CICs can have an OPC of value . The LEC switch providing CICs and CICs has an OPC of value . Similarly DPC represents the destination point code for a circuit group i.e. the point code of soft switch site . Soft switch site has a point code of value and an alternate point code of value . Soft switch site can act as one big switch using a flat network design of the present invention. This flat network design simplifies routing of calls.

To support distribution of circuits across soft switches SS7 GWs can include a lookup table that allows each signaling message to be routed to the correct soft switch . The lookup table can route signaling messages to the correct soft switch based upon the OPC DPC and CIC fields. This lookup table is built on SS7 GWs based upon registration messages coming from soft switches 

In an example embodiment each time a TG boots up the TG finds a soft switch to service its circuits. For example when TG is powered up TG must find a soft switch to service its circuits i.e. CICs . In an exemplary technique TG sends registration messages to soft switch to register circuits CICs . Upon receipt of these registration messages the soft switch registers these circuits with SS7 GWs at soft switch site . The circuit registration messages sent to the SS7 gateways are used to build the type of table shown in Table 6.

The format of a registration message is shown in Table 7. Table 7 includes the mapping of circuits to soft switches.

The messages used by soft switches to register their circuits with SS7 GWs contain information for the OPC DPC and circuit range i.e. the CICs that are being registered. Each message also contains information about the soft switch that will be servicing the signaling messages for the circuits being registered.

The soft switch information includes an indication of whether this soft switch is identified as the primary servicing point for calls to these circuits the secondary servicing point or the tertiary servicing point. The gateway uses this indicator in failure conditions when it cannot contact the Soft Switch that is currently servicing a set of circuits.

The IAM message can then be routed by signaling network i.e. the SS7 network to SS7 GWs at soft switch site having point code . SS7 GWs can perform a lookup to Table 7 to identify which of soft switches is handling the particular circuit described in the IAM message. In the example above the IAM message having OPC of value DPC of value and CIC can be routed to soft switch

SS7 GWs will now be discussed further with reference to . depicts an exemplary signaling network environment . includes signaling network Specifically signaling network can be an SS7 national signaling network. depicts three soft switch sites interfacing via a plurality of STPs to SS7 network .

Similarly central soft switch site includes soft switches redundantly connected to routers and SS7 GWs via ethernet switches . SS7 GW and SS7 GW communicate via TCP IP connection and serial link .

Finally eastern soft switch site includes soft switches redundantly connected to routers and SS7 GWs via ethernet switches . SS7 GW and SS7 GW communicate via TCP IP connection and serial link .

Out of band signaling such as e.g. SS7 signaling information is communicated to i.e. exchanged with soft switch sites via SS7 GWs SS7 GWs and SS7 GWs from signaling network .

SS7 signaling messages are transferred through signaling network from STP to STP until arriving at a final destination. Specifically signaling messages intended for soft switch sites are routed via packet switched SS7 signaling network to STPs which are part of the SS7 national signaling network . STP services i.e. STPs and A F links can be provided by an SS7 signaling services provider such as e.g. Transaction Network Services TNS .

Table 19 defines SS7 signaling links. Some of the SS7 links used are as follows. STPs are linked together by a C link. STPs are linked by redundant D links to STPs . STPs can also be linked by redundant D links to STPs though this is not shown.

STP pairs are linked together by one or more C links . Likewise STP pairs STP pairs STP pairs and STP pairs can be linked together by C links.

STPs and can be linked by one or more A links to SS7 GWs and . Thus signaling messages from anywhere in signaling network may be routed by STPs through STPs to SS7 GWs and of soft switch sites and . SS7 GWs and thus route messages through packet switched STPs to signaling network .

SS7 GWs and use a separate physical interface for all simple network management protocol SNMP messages and additional functions that may be defined. Exemplary functions that may be defined include provisioning updating and passing special alarms and performance parameters to the SS7 GW from the network operation center NOC of network management component .

Signal transfer points STPs are the packet switches of signaling network . More specifically STPs are the packet switches of the SS7 network. STPs are the STPs interfacing with SS7 GWs of soft switch site . STPs receive and route incoming signaling messages toward the proper destination.

STPs also perform specialized routing functions. STPs are customarily deployed in pairs. While elements of a pair are not generally collocated they work redundantly to perform the same logical function.

STPs have several interfaces. STP interfaces are now described with reference to . The interfaces can be described in terms of the links used. Table 19 shows links used in SS7 architectures.

The first interface comprises one or more D links from off network STPs as shown in to on network STPs . D links connect mated STPs at different hierarchical levels to one another. On network STPs as well as STPs and are part of the national SS7 signaling network . Additional D links can connect STPs to STPs STPs STPs and STPs and .

The second interface comprises C links. C links connect mated STPs together. An example are C links between STP and . C links enable STPs to be linked in such a manner that they need not be co located. Similarly STPs STPs STPs STPs and STPs can also be respectively linked via C links.

The third interfaces to STPs comprise A links and E links. A links connect STPs to SSPs and SCPs. B links are special links that connect SSPs to remote STPs and are used in the event that A links to home STPs are congested. The entire soft switch site is viewed as an SSP to a signaling network. A links or E links can be used to connect any of STPs and respectively to soft switch sites at SS7 GWs and . In an example embodiment each of SS7 GWs can have for example twelve 12 A links distributed among STPs and STPs . By using the plurality of A links the soft switch sites have a fully redundant fully meshed fault tolerant signaling architecture.

STPs use a separate physical interface for all SNMP messages and additional functions that can be defined. Additional functions that can be defined include provisioning updating and passing special alarms and performance parameters to and from STPs and network operation center NOC of network management component .

In another embodiment of the invention as illustrated in soft switch sites have additional soft switches and SS7 GWs. Additional soft switches and SS7 GWs can be used for example for handling additional traffic and for testing of alternative vendor soft switches and SS7 GWs.

Western soft switch site includes SS7 GWs which can communicate via a TCP IP connection and a serial link. SS7 GWs are connected to soft switches and . In addition western soft switch site includes soft switch and SS7 GW connected to STPs and . Also western soft switch site includes soft switch and SS7 GW connected to STPs 

Central soft switch site includes SS7 GWs B which can communicate via a TCP IP connection or a serial link. SS7 GWs connect soft switches and to STPs and . Central soft switch site also includes soft switch and SS7 GWs connected to STPs . Central soft switch site also includes soft switch connected to SS7 GW which is connected to STPs 

Eastern soft switch site includes SS7 GWs SS7 GW which can communicate over TCP IP and over a serial link. SS7 GWs connect soft switches and to STPs and . Eastern soft switch site also includes soft switch connected to SS7 GW which is connected to STPs . Eastern soft switch site also includes soft switch which is connected to SS7 GW which is in turn connected to STPs 

Alternative embodiment by including additional soft switches and SS7 gateways permits additional redundancy and enables testing of alternate devices for connection to signaling network via STPs and .

STPs in an example embodiment can be a TEKELEC Network Switching Division s EAGLE STP. An EAGLE STP available from TEKELEC of Calabasas Calif. is a high speed packet switch designed to support SS7 signaling. STPs can be equipped with a plurality of links. In an example embodiment STPs can support up to for example 84 links. For example in a preferred embodiment 14 links can be used initially and additional links can be added in the future. In a preferred embodiment several additional features can be added to STPs .

In a preferred embodiment STPs can have global title translation capability. Global title translation uses global title information. Global title information is information unrelated to signaling network address which can be used to determine the appropriate destination of a message. Global title translation can support translations from for example one to twenty one digits. For example translations can be assigned to translation types from 0 to 225. In a preferred embodiment STPs can support up to for example 1 000 global title translation requests per second per application service module ASM .

In a preferred embodiment STPs include a gateway screening software feature. EAGLE STP can support user definitions of up to 64 screen sets In this embodiment each screen set can accommodate up to 2 000 condition statements or rules with the gateway screening software. Gateway screening can be performed on all in bound messages from another network. Gateway screening can also be performed on all outgoing network management messages. Since gateway screening can occur on the link interface modules LIMs and the application service modules ASMs the deployment of the gateway screening feature does not impact link throughput capacity and can contribute to less than 5 milliseconds increase to cross STP delays.

In a preferred embodiment local number portability LNP can be integrated into the EAGLE architecture of STPs . An advantage of the integration of LNP functionality is that it eliminates the need for costly external LNP databases and associated transmission equipment. In one embodiment LNP portability can support complete scalabilty in configurations ranging from 500 000 translation entries and up to more than several million translation entries for very large metropolitan serving areas MSAs .

In a preferred embodiment the STP to LAN interface of the EAGLE architecture can allow the user to connect external data collection or processing systems directly to STPs via a TCP IP protocol. In this embodiment the STP to LAN interface could be used to carry SS7 signaling over IP packets.

In a preferred embodiment STPs can include a feature referred to as the ANSI ITU gateway feature. In a preferred embodiment the ANSI ITU feature of STPs allows STPs to interconnect three types of signaling networks i.e. ITU international ITU national and ANSI by means of three different message signaling unit MSU protocols. In a preferred embodiment of STPs the ANSI ITU feature can allow a smooth transition from an all ANSI network to a combined ANSI ITU network.

SS7 TCAP is connected to SCP an off network SCP via STP . IP TCAP is connected to SCP . SCP is connected to custom IP . SCP is an on network SCP and is connected via INAP IP .

Off switch call processing abstraction layer is intended to be a flexible interface similar to TCAP in function that allows interaction between any type of SCP or other call processing logic and soft switch . The abstraction layer is so designed that interfaces to a set of call processors supporting a specific function e.g. 800 service contain the same types of data and can all map arguments to data elements supported by off switch call processing abstraction layer . The field values for messages supplied by off switch call processing abstraction layer are identified in this section i.e. describing SCPs and also in the section describing route servers below.

The SCPs can be off switch call processing servers which support intelligent services within the telecommunications network SCPs and can support such services as for example account code verification and toll free 800 services local number portability LNP carrier ID identification and card services.

Other services and capabilities of SCPs and include basic toll free services project account code PAC services local number portability LNP services 800 carrier ID services calling name CNAM services advanced toll free network automatic call distribution ACD services customer premise toll free routing services one number or follow me services and SCP gateway for customer premises equipment CPE route selection services. These services are recognized by those skilled in the art.

Additional services and capabilities can include intelligent peripherals. Intelligent peripherals can include calling card debit card voicemail unified messaging conference calling and operator services. These peripherals are recognized by those skilled in the art.

Gateway site in intelligent network architecture is connected to multiple off network service providers. Off network service providers include local exchange carrier LEC inter exchange IXC carrier and operator services service bureau . Thus calls coming in from LEC or from IXC into gateway site if identified as an operator call may be routed to off network operator services .

Soft switch does not dictate any particular SCP interface but it is assumed that this interface will support the following types of interactions 1 route request 2 route response 3 call gapping and 4 connect to resource.

A route request is a message sent from soft switch to an external SCP . The route request is sent to request a translation service from SCP for example to translate disclosed digits to a destination number.

A route response is a message sent from SCP to soft switch in response to a route request. The route response includes a sequence of prioritized destinations for the call. SCPs that perform routing can return a list of prioritized destinations. These destinations can be for example any combination of destination numbers or circuit groups. If SCP returns a destinations number soft switch can attempt to route to that destination number using the least cost routing logic included in route server . If SCP returns a circuit group the soft switch can use route server to select an available circuit in that group. Soft switch can try to terminate to the specified destinations in the prioritized order that the destinations are returned from SCP .

The interface that can be used by soft switch in order to interact with SCPs and is called the off switch call processing OSCP interface. This interface is also used for route server and any other call processing engines. OSCP is represented in as off switch call processing abstraction layer . Tables 8 9 10 and 11 identify the fields in the OSCP route request and route response messages which are necessary for 800 and account code processing service calls.

A route response can also include an indication to initiate a call gapping for a congested call. Call gapping refers to a message sent from an SCP to a soft switch to control the number and frequency of requests sent to that SCP. The call gapping response can indicate a length of time for which gapping should be active as well as a gap interval at which the soft switch should space requests going to the SCP. Call gapping can be activated on the SCP for each individual service supported on the SCP. For example if SCP supports 800 and project account code queries it may gap on 800 but not on project account codes. Alternatively SCP can gap on project codes but not on 800 or can gap on both or neither.

A connect to resource is a response that is sent from the SCP to the soft switch in response to a route request for requests that require a call termination announcement to be played.

Advanced toll free SCP is in communication with soft switch via INAP IP protocol . Advanced toll free SCP is also in communication with computer telephony integration CTI server . CTI server can communicate with an automatic call distributor ACD .

The H.323 Recommendation will now be briefly overviewed with reference to The H.323 standard provides a foundation for for example audio video and data communications across IP based networks including the Internet. By complying with the H.323 Recommendation multimedia products and applications from multiple vendors can interoperate allowing users to communicate without concern for compatibility. H.323 will be the foundation of future LAN based products for consumer business entertainment and professional applications.

H.323 is an umbrella recommendation from the International Telecommunications Union ITU that sets standards for multimedia communications over Local Area Networks LANs that do not provide a guaranteed Quality of Service QoS . These networks dominate today s corporate desktops and include packet switched TCP IP and IPX over Ethernet Fast Ethernet and Token Ring network technologies. Therefore the H.323 standards are important building blocks for a broad new range of collaborative LAN based applications for multimedia communications.

The H.323 specification was approved in 1996 by the ITU s Study Group 16. Version 2 was approved in January 1998. The standard is broad in scope and includes both stand alone devices and embedded personal computer technology as well as point to point and multipoint conferences. H.323 also addresses call control multimedia management and bandwidth management as well as interfaces between LANs and other networks.

H.323 is part of a larger series of communications standards that enable videoconferencing across a range of networks. Known as H.32 this series includes H.320 and H.324 which address ISDN and PSTN communications respectively.

Terminals are the client endpoints on the LAN that provide real time two way communications. All terminals must support voice communications video and data are optional. H.323 specifies the modes of operation required for different audio video and or data terminals to work together. It is the dominant standard of the next generation of Internet phones audio conferencing terminals and video conferencing technologies.

All H.323 terminals must also support H.245 which is used to negotiate channel usage and capabilities. depicts an exemplary H.323 terminal . Three other components are required Q.931 for call signaling and call setup a component called Registration Admission Status RAS which is a protocol used to communicate with a gatekeeper and support for RTP RTCP for sequencing audio and video packets.

Optional components in an H.323 terminal are video codecs T.120 data conferencing protocols and MCU capabilities described further below .

Gateway is an optional element in an H.323 conference. depicts an example H.323 gateway. Gateways provide many services the most common being a translation function between H.323 conferencing endpoints and other terminal types. This function includes translation between transmission formats i.e. H.225.0 to H.221 and between communications procedures i.e. H.245 to H.242 . In addition gateway also translates between audio and video codecs and performs call setup and clearing on both the LAN side and the switched circuit network side. shows an H.323 PSTN Gateway .

In general the purpose of gateway is to reflect the characteristics of a LAN endpoint to an SCN endpoint and vice versa. The primary applications of gateways are likely to be 

Gateways are not required if connections to other networks are not needed since endpoints may directly communicate with other endpoints on the same LAN. Terminals communicate with gateways using the H.245 and Q.931 protocols.

With the appropriate transcoders H.323 gateways can support terminals that comply with H.310 H.321 H.322 and V.70.

Many gateway functions are left to the designer. For example the actual number of H.323 terminals that can communicate through the gateway is not subject to standardization. Similarly the number of SCN connections the number of simultaneous independent conferences supported the audio video data conversion functions and inclusion of multipoint functions are left to the manufacturer. By incorporating gateway technology into the H.323 specification the ITU has positioned H.323 as the glue that holds the world of standards based conferencing endpoints together.

Gatekeeper is the most important component of an H.323 enabled network. It acts as the central point for all calls within its zone and provides call control services to registered endpoints. In many ways an H.323 gatekeeper acts as a virtual switch.

Gatekeepers perform two important call control functions. The first is address translation from LAN aliases for terminals and gateways to IP or IPX addresses as defined in the RAS specification. The second function is bandwidth management which is also designated within RAS. For instance if a network manager has specified a threshold for the number of simultaneous conferences on the LAN the Gatekeeper can refuse to make any more connections once the threshold is reached. The effect is to limit the total conferencing bandwidth to some fraction of the total available the remaining capacity is left for e mail file transfers and other LAN protocols. depicts a collection of all terminals gateways and multipoint control units which can be managed by a single gatekeeper . This collection of elements is known as an H.323 Zone.

An optional but valuable feature of a gatekeeper is its ability to route H.323 calls. By routing a call through a gatekeeper it can be controlled more effectively. Service providers need this ability in order to bill for calls placed through their network. This service can also be used to re route a call to another endpoint if a called endpoint is unavailable. In addition a gatekeeper capable of routing H.323 calls can help make decisions involving balancing among multiple gateways. For instance if a call is routed through a gatekeeper that gatekeeper can then re route the call to one of many gateways based on some proprietary routing logic.

While a gatekeeper is logically separate from H.323 endpoints vendors can incorporate gatekeeper functionality into the physical implementation of gateways and MCUs .

Gatekeeper is not required in an H.323 system. However if a gatekeeper is present terminals must make use of the services offered by gatekeepers . RAS defines these as address translation admissions control bandwidth control and zone management.

Gatekeepers can also play a role in multipoint connections. To support multipoint conferences users would employ a Gatekeeper to receive H.245 Control Channels from two terminals in a point to point conference. When the conference switches to multipoint the gatekeeper can redirect the H.245 Control Channel to a multipoint controller the MC. Gatekeeper need not process the H.245 signaling it only needs to pass it between the terminals or the terminals and the MC.

LANs which contain Gateways could also contain a gatekeeper to translate incoming E.164 addresses into Transport Addresses. Because a Zone is defined by its gatekeeper H.323 entities that contain an internal gatekeeper require a mechanism to disable the internal function so that when there are multiple H.323 entities that contain a gatekeeper on a LAN the entities can be configured into the same Zone.

The Multipoint Control Unit MCU supports conferences between three or more endpoints. Under H.323 an MCU consists of a Multipoint Controller MC which is required and zero or more Multipoint Processors MP . The MC handles H.245 negotiations between all terminals to determine common capabilities for audio and video processing. The MC also controls conference resources by determining which if any of the audio and video streams will be multicast. MCU is depicted in .

The MC does not deal directly with any of the media streams. This is left to the MP which mixes switches and processes audio video and or data bits. MC and MP capabilities can exist in a dedicated component or be part of other H.323 components. A soft switch includes some functions of an MP. An access server also sometimes referred to as a media gateway controller includes some of the functions of the MC. MCs and MPs are discussed further below with respect to the IPDC protocol.

Approved in January of 1998 version 2 of the H.323 standard addresses deficiencies in version 1 and introduces new functionality within existing protocols such as Q.931 H.245 and H.225 as well as entirely new protocols. The most significant advances were in security fast call setup supplementary services and T.120 H.323 integration.

Project Account Codes can be used for tracking calls for billing invoicing and Class of Service COS restrictions. Project account code PAC verifications can include for example types Unverified Unforced Unverified Forced Verified Forced and Partially Verified Forced. A web interface can be provided for a business customer to manage its accounts. The business customer can use the web interface to make additions deletions changes and modifications to PAC translations without involvement of a carrier s customer service department.

An example of call processing using PACs follows. PAC SCP of can receive validation requests from Soft Switch after Soft Switch has requested and received PAC digits. The PAC digits can be forwarded to SCP for verification. When SCP receives this request SCP can compare the entire PAC if the PAC type is Verified Forced against a customer PAC table. SCP can compare only the verified portion of the PAC if the PAC type is Partially Verified Forced against the customer PAC table.

The PAC digits can be sent from Soft Switch to SCP in the Caller Entered Digits field. The indicated customer can be sent from Soft Switch to SCP in the Customer field.

Basic Toll Free Service SCP can translate a toll free e.g. 800 and 888 number to a final routing destination based on a flexible set of options selected by a subscriber. Basic toll free service supports e.g. 800 and 8XX Service Access Codes. Subscriber options can include for example 1 routing based on NPA or NPA NXX of calling party 2 routing based on time of day and day of week 3 routing based on percent distribution 4 emergency override routing and 5 blocking based on calling party s NPA or NPA NXX or ii digits.

An exemplary embodiment of basic toll free SCP is a GENESYS Network Interaction Router available from GENESYS of San Francisco Calif. The GENESYS Network Interaction Router product suite provides Basic Toll Free service. Soft Switch can send route requests to SCP for any Toll Free numbers that Soft Switch receives. SCP can then attempt to route the call using a route plan or trigger plan that has been defined for that Toll Free dialed number. SCP can have several possible responses to a soft switch routing request see Table 10 above. Using the subscriber routing option described in the previous paragraph SCP can return a number translation for the Toll Free number. For example SCP can receive a dialed number of 800 202 2020 and return a DDD such as 303 926 3000. Alternatively SCP can return a circuit identifier. SCP usually returns a circuit identifier when the termination is a dedicated trunk to a customer premise equipment CPE . Then if SCP determines that it can not route the call or has determined to block the call per the route plan SCP returns a route to resource response to Soft Switch with an announcement identifier. In this case Soft Switch can connect the calling party with Announcement Server for the playing of an announcement and then disconnect the caller.

SCP can store call events in CDR database tables on SCP . CDR database tables can then be replicated to Master Network Event Database using a data distributor such as for example the Oracle Replication Server.

The configuration server will now be described in greater detail with reference to . Configuration server supports transaction requests to a database containing information needed by network components. Configuration server supports queries by voice network components during initialization and call processing. The data contained within configuration server databases can be divided into two types. The first type of data is that used to initialize connections between components. Examples of such data used to initialize connections between network components include the following IP address and port numbers for all servers that soft switch must communicate with information indicating initial primary secondary tertiary configurations for server relationships configuration information for access gateways and trunking gateways number and configuration of bays modules lines and channels BMLC relationship of module line and channels to originating point code OPC destination point code DPC and circuit identification code CIC values relationship of module line and channels to trunk groups call processing decision trees for soft switch processing mapping of OPC DPC and CIC values soft switches mapping of access server ports to dedicated access line DAL identifiers and customer IDs tables necessary to support class of service COS restrictions local access transport area LATA tables state tables and blocked country code tables.

The second set of data can be categorized as that data needed by soft switch for use during call processing. This type of data includes customer and DAL profiles. These profiles define the services that a customer has associated with their ANIs or DALs. This information can include information describing class of service restrictions and account code settings.

The database of configuration server contains voice network topology information as well as basic data tables necessary for soft switch call processing logic. Configuration server is queried by soft switches at start up and upon changes to this information in order to set up the initial connections between elements of telecommunications network . Configuration server is also queried by soft switches in order to configure initial settings within soft switch .

Configuration server contains the following types of information LP address and port numbers for all servers that soft switch must communicate with information indicating initial primary secondary tertiary configurations for server relationships configuration information for AGs and TGs call processing decision trees for soft switch call processing mapping of OPC DPC and CIC values to soft switch mapping of access server ports to DALs and customer IDs and tables necessary to support COS restrictions.

Configuration information for AGs and TGs includes number and configuration of bays modules lines and channels relationship of modules line and channels to OPC DPC and CIC values and relationship of module line and channels to trunk groups.

Tables necessary to support class of service restrictions include LATA tables state tables and blocked country code tables.

Configuration server also contains information related to customer trigger plans and service options. Customer trigger plans provide call processing logic used in connecting a call. Configuration server information is queried during call processing to identify the service logic to be executed for each call.

The information that soft switch uses to look up customer profile data is the ANI trunk ID or destination number for the call. The information that will be returned defines the call processing logic that is associated with ANT trunk ID or destination number or trunk group.

Configuration server interfaces to components. Configuration server receives provisioning and reference data updates from data distributor of provisioning component . Configuration server also provides data to soft switch for call processing. Configuration server is used by soft switch to retrieve information necessary for initialization and call processing. Information that soft switch retrieves from configuration server during a query is primarily oriented towards customer service provisioning and gateway site port configuration. Configuration server database tables accessible to soft switch include the following toll free number to SCP type translation SCP type to SCP translation CICs profiles ANT profiles summary ANI profiles account code profiles NPA NXX customer profiles customer location profiles equipment service profiles trunk group service profile summaries trunk group services high risk countries and selected international destinations.

Configuration server uses a separate physical interface for all SNMP messages and additional functions that may be defined. Examples of additional functions that may be defined include provisioning updating and the passage of special alarms and performance parameters to configuration server from the NOC.

In an alternative embodiment the functionality of configuration server can be combined with that of route server in a single network component. In an additional embodiment of the invention the functions of either or both of CS and RS can be performed by application logic residing on soft switch .

Route server will now be described in further detail with reference to . Route server provides at least two functions. Route server performs the function of supporting the logic for routing calls based upon a phone number. This routing performed by route server results in the selection of one or more circuit groups for termination.

Another function of route server is the tracking and allocation of network ports. As shown in route server collocated with other components at soft switch site services routing requests for all soft switches at that site. Therefore route server tracks port resources for all TGs and and AGs and that are serviced by soft switches and at soft switch site .

The routing logic accepts translated phone numbers and uses anywhere from full digit routing to NPA based routing to identify a terminating circuit group. Routing logic selects the translation based upon the best match of digits in the routing tables. An exemplary routing table is illustrated as Table 14.

In Table 14 there are five entries that can match the dialed number 303 926 3000 . The first route choice is the one that has a full match of digits with priority one. Since there are two entries with full matching digits and which are marked as priority one the load should be distributed as shown in the load column i.e. 50 load share is distributed to the first and 50 load share is distributed to the second . The second route choice is the entry with a full digit match but marked with the lower priority of two. The third route match is the one that has a matching NPA NXX. The last route choice is the one that has a matching NPA only.

In situations where there are multiple route choices for a DDD number i.e. the number of called party route server must take into consideration several factors when selecting a terminating circuit group. The factors to be considered in selecting a terminating circuit group include 1 the percent loading of circuit groups as shown in the load column of Table 14 2 the throttling use of trunk groups to avoid overloaded networks 3 the fact that end office trunk groups should be selected before tandem office trunk groups and 4 routing based upon negotiated off network carrier agreements.

Agreements should be negotiated with off network carriers to provide the flexibility to route calls based upon benefits of one agreement another. The following types of agreements can be accounted for 1 commitments for the number of minutes given to a carrier per month or per year 2 the agreement that for specific NPA or NPA NXX sets one carrier may be preferred over another 3 the agreement that international calls to specific countries may have preferred carriers 4 the agreement that intra LATA or intra state calls originating for certain areas may have a preferred carrier in that area and 5 the agreement that extended area service calls may have a preferred carrier.

The logic for route server can include routing for international calls. In the example shown in Table 14 it is possible to have fully specified international numbers or simply specified routing for calls going to a particular country. As with domestic numbers the routing logic should select the table entry that matches the most digits within the dialed number i.e. the number of called party .

Once a terminating circuit group has been identified route server needs to allocate a terminating circuit within the trunk group. The selection of a terminating circuit is made by querying the port status table. Table 15A shows an exemplary port status table. The results of a query to port status Table 15A yields the location and allocation of a circuit. Route server can use algorithms to select circuits within the trunk group. Each circuit group can be tagged with the selected algorithm that should be used when selecting circuits within that group.

Example algorithms to select circuits within the group include 1 the most recently used circuit within a circuit group 2 the least recently used circuit within a circuit group 3 a circular search keeping track of the last used circuit and selecting the next available circuit 4 the random selection of an available circuit within a circuit group and 5 a sequential search of circuits within a circuit group selecting the lowest numbered available circuit. Table 15A illustrates the association between a circuit group and the selection algorithm that should be used to allocate ports from that group.

Table 15B includes the circuit group that a port is a member of a port identifier and the current status of that port. The port identifier shown in Table 15B assumes the type of port identification currently used in the IPDC protocol where the port is represented by a bay module line and channel BMLC . It would be apparent to persons skilled in the art that other methods of identifying a port can be used.

The function of route server is to provide least cost routing information to soft switch in order to route a call from calling party to called party . In addition to providing routing information route server allocates ports for terminating calls on the least cost routes e.g. allocating ports within TGs . Route server pair is located at each of soft switch sites and services all soft switches and at that site. Refer to . 

Route server interacts with at least two other voice network components. Route server interacts with configuration server . Configuration server is used to retrieve initial information on route server start up to set up the initial routing tables in preparation for receiving requests from soft switches and for example.

Route server also interfaces with soft switch . Soft switch can send route requests to route server that contain either a phone number or a circuit group. Route server can perform its least cost routing logic to first select a terminating circuit group for the call. Using that circuit group route server can then select and allocate a terminating circuit.

A description of the messages and model of interaction between route server and soft switch follows. Route server is used by soft switch to identify the possible network terminations for a call. Soft switch passes a DDD number an international DDD IDDD number or a circuit group to route server in a route request message. Using this information from soft switch route server can return the port on an AG or TG that should be used to terminate this call. Using this port information soft switch can then signal the originating and terminating TG or AG to connect the call through data network .

The route server will now be described further with reference to . depicts a sample call flow illustrating how soft switch interacts with route server to identify a terminating port for a call.

In exemplary call flow the call originates and terminates at different sites specifically gateway sites and . Since exemplary call flow originates and terminates at different sites the cooperation of the originating soft switch and terminating soft switch and route servers respectively to identify the terminating circuit. Portions of the call flow will now be described in greater detail.

As depicted in step for calls arriving on SS7 signal trunks soft switch receives call arrival notifications in the form of IAM messages. Upon receipt of the IAM message from SS7 GW soft switch performs some initial digit analysis to determine the type of the call.

In step for calls involving customer features soft switch can use the ANI of calling party i.e. the telephone number of calling party to query a customer profile database in configuration server . This is done to identify the originating customer s feature set. Each customer s feature set is known as a trigger plan for origination of the call. A trigger plan can be thought of as a flowchart which branches based on certain triggering events dependent on the caller s identity. Customer trigger plans reside in a customer profile on configuration server .

In step the customer profile database of configuration server returns the customer trigger plan to soft switch . Soft switch can perform any processing necessary to implement the customer s specified originating triggers.

Application logic in soft switch can then generate a translated number or an identification of the terminating circuit group for this call. For example in the case of an 800 call a translation may be requested as in step of an SCP . SCP converts the 800 number into a normal number for termination and in step returns the number to soft switch .

In step in order to translate the translated number or circuit group into an egress port soft switch makes a route request to route server . The routing logic uses the NPA NXX XXXX to identify the terminating circuit group. Upon identifying the terminating circuit group the route logic queries a circuit group to soft switch mapping table in route logic of route server to identify the target soft switch that handles the identified termination. For example the target soft switch may be soft switch . It is important to note that there can be multiple route choices and therefore there can be multiple soft switches supporting a single route request.

In step route server responds to soft switch with the terminating circuit group. In this example the terminating circuit group is included in trunks connected to trunking gateway which is serviced by a different soft switch namely soft switch than originating soft switch . Therefore route server responds with the terminating circuit group and identifies soft switch as the soft switch that handles that terminating circuit group.

In step originating soft switch initiates the connection from the origination to the termination by requesting a connection from the originating trunking gateway . Trunking gateway upon receipt of the set up request from soft switch allocates internal resources in trunking gateway .

TG manages its own ports. In an example embodiment TG uses real time protocol RTP over UDP and RTP sessions which are ports used to implement an RTP connection. In step TG returns to soft switch the IP address and listed RTP port.

In step originating soft switch issues a call setup command to terminating soft switch . This is the command identified by route server .

In step soft switch queries route server to determine the termination port for the call. Specifically soft switch queries port status of route server . The query in step passes in as a parameter the terminating circuit group.

In step route server allocates a termination port and returns the allocated termination port to terminating soft switch .

In step terminating soft switch instructs the identified end point i.e. trunking gateway to reserve resources and to connect the call. Terminating soft switch passes in an IP address and an RTP port corresponding to the port that was allocated by originating TG .

In step terminating TG returns the allocated resources for the call to soft switch . For voice over IP VOID connections this includes the listed port and IP address for the terminating TG .

In step originating soft switch communicates with originating TG in order to inform originating TG of the listed port that was allocated by terminating TG . At this point originating TG and terminating TG have enough information to exchange full duplex information.

In step originating TG acknowledges the receipt of the communication from soft switch to soft switch .

Table 16A shows fields that can be included in a route request sent from soft switch to route server . The route request can contain either a DDD number or a circuit group that requires routing. The route request message can also contain information about the call collected from the IAM message that is necessary to perform routing of this call. The route request message can also contain information about the call necessary to perform routing of the call which is obtained from the processing of the call. For example in the case of an 800 call this information can be a translated number.

Table 16B shows fields which can be included in a response corresponding to the route response sent from route server back to soft switch .

Alternatively each route response can include one route termination and multiple consecutive route terminations can be determined with multiple route request response transactions.

The route response message can contain a plurality of route terminations for the DDD or circuit group that was passed in as a parameter to route server . For example the route response message can include 1 to 5 route choices. Each of the route choices of the route response message can include various fields of information. For example each route choice can include the following information the circuit group the circuit the outpulse digits the destination number and the destination soft switch . Alternatively each route response can include one route termination and multiple consecutive route terminations can be determined with multiple route request route response transactions.

In situations where the selected circuit group is managed by the same route server that serviced the route request the response for that route can contain all the information about the destination. This is possible because route server can identify and allocate the circuit within the circuit group.

In situations where another route server services the selected circuit group the response for that route only contains the circuit group and the destination soft switch . Originating soft switch can then make a request to terminating soft switch to query the terminating route server for a circuit within the identified circuit group. The terminating soft switch can then control the termination of the call.

Referring back to regional network event collection points RNECPs serve as collection points for real time recorded call events that can be used by other systems. Soft switch generates call data. This call data can be collected during call processing. Call data can also be generated by capturing events from other network elements. These network elements include internal soft switch site components and external components. External components include SCPs intelligent peripherals IPs AGs TGs and signaling components such as STPs SSPs and off switch SCPs.

Soft switch provides call event data to RNECPs . Call data can be collected by a primary and secondary server at each RNECP using high availability redundancy to minimize the possibility of potential data loss. Data from RNECPs can then be transmitted in real time to a centralized server called the master network event database MNEDB . The MNEDB is discussed further below with reference to .

RNECPs can route network events through management virtual private network VPN to master network event data center . Network events come through management VPN and can be routed via redundant paths to MNEDB server and or MNEDB . MNEDBs and can communicate with one another. MNEDB uses disks as primary storage for its database. MNEDB also uses disks for secondary storage. Similarly MNEDB uses primary and secondary disks 

MNEDB and MNEDB can be collocated or can be geographically diverse. Thus master data center can be either in one geographical area or in multiple locations.

Management VPN also collects events from the other soft switch sites i.e. central soft switch site and eastern soft switch site . Central soft switch site includes soft switches redundantly connected via a LAN to RNECPs and . RNECP has disks and .

Eastern soft switch site includes soft switches redundantly connected via a LAN. RNECPs and RNECP can have disks and .

RNECPs and of central soft switch site and RNECPs and of eastern soft switch site can route network events for storage in disks of MNEDBs 

This is done by routing network events via management VPN to master data center . The soft switches generate event blocks and push event block data to the RNECPs. Event blocks are recorded call events that are created during call processing. 

Each RNECP and forwards collected event blocks EBs to MNEDBs which are centralized databases. RNECPs and use separate physical interfaces for all SNMP messages and additional functions that may be defined. Additional functions that can be defined include provisioning updating and passing special alarm and or performance parameters to RNECPs from the network operation center NOC .

RNECPs and are used by soft switches and to collect generated call events for use in such services as preparation of billing and reporting. At specific points throughout the duration of a call soft switches and take the information that the soft switches have collected during call processing and push that data to the RNECPs.

Multiple types of data are logged by the soft switches during call processing of a normal one plus 1 long distance call using account codes. Examples of data logged by an exemplary soft switch include a call origination record on the originating side call termination information on the terminating side an account code record egress routing information answer information on the originating side call disconnect information on the originating side call disconnect information on the terminating side and final event blocks with call statistics.

Exemplary soft switch can record data during call processing. Soft switch transfers call events from RNECP to MNEDB for storage. This call event data stored in MNEDB can be used by various downstream systems for post processing. These systems include for example mediation end user billing carrier access billing services CABS fraud detection prevention capacity management and marketing.

There are at least two types of EBs. Example Mandatory and Augmenting event blocks can be explained as follows.

Mandatory EBs are created by soft switch during the initial point in call analysis. Initial point in call analysis includes going off hook picking up the telephone set call setup initial digit analysis i.e. digit analysis prior to any external database transactions or route determinations .

Since other events such as for example session call answer and SCP transactions can occur during call processing soft switch can create augmenting EBs. Augmenting EBs are EBs which can augment the information found in a mandatory EB. Events such as for example route determination and answer indication can be recorded in an augmenting EBs.

Examples of mandatory and augmenting EBs follow. For a complete illustration of these EBs the reader is referred to Tables 20 143 and the corresponding discussions below. Specifically Tables 20 48 provide mandatory EBs Tables 49 60 provide augmenting EBs and Tables 61 143 provide the call event elements that comprise the Ebs.

In an example embodiment soft switch site comprises a plurality of object oriented programs OOPs running on a computer. As apparent to those skilled in the art soft switch site can alternatively be written in any form of software.

OOPs can be described at a high level by defining object oriented programming classes. For example in an embodiment of the present invention soft switch comprise an OOP written in an OOP language. Example languages include C and JAVA. An OOP model is enforced via fundamental mechanisms known as encapsulation inheritance and polymorphism.

Encapsulation may be thought of as placing a wrapper around the software code and data of a program. The basis of encapsulation is a structure known as a class. An object is a single instance of a class. A class describes general attributes of that object. A class includes a set of data attributes plus a set of allowable operations i.e. methods . The individual structure or data representation of a class is defined by a set of instance variables.

Inheritance is another feature of an OOP model. A class called a subclass may be derived from another class called a superclass wherein the subclass inherits the data attributes and methods of the superclass. The subclass may specialize the superclass by adding code which overrides the data and or methods of the superclass or which adds new data attributes and methods.

Thus inheritance represents a mechanism by which subclasses are more precisely specified. A new subclass includes all the behavior and specification of all of its ancestors. Inheritance is a major contributor to the increased programmer efficiency provided by the OOP. Inheritance makes it possible for developers to minimize the amount of new code they have to write to create applications. By providing the significant portion of the functionality needed for a particular task classes on the inheritance hierarchy give the programmer a head start to program design and creation.

Polymorphism refers to having one object and many shapes. It allows a method to have multiple implementations selected based on the type of object passed into a method and location. Methods are passed information as parameters. These are parameters passed as both a method and an invocation of a method. Parameters represent the input values to a function that the method must perform. The parameters are a list of typed values which comprise the input data to a particular message. The OOP model may require that the types of the values be exactly matched in order for the message to be understood.

Object oriented programming is comprised of software objects that interact and communicate with each other by sending one another messages. Software objects are often modeled from real world objects.

Object oriented programs of the present invention are hardware platform independent. Client computer in a preferred embodiment is a computer workstation e.g. a Sun UltraSPARC Workstation available from SUN Microsystems Inc. of Palo Alto Calif. running an operating system such as UNIX. Alternatively a system running on another operating system can be used as would be apparent to those skilled in the art. Other exemplary operating systems include Windows NT Windows98 OS 2 Mac OS and other UNIX based operating systems. Exemplary UNIX based operating systems include solaris IRIX LINUX HPUX and OSF. However the invention is not limited to these platforms and can be implemented on any appropriate computer systems or operating systems.

An exemplary computer system is shown in . Other network components of telecommunications network such as for example route server and configuration server can also be implemented using computer system shown in . Computer system includes one or more processors . Processor is connected to a communication bus .

Client computer also includes a main memory preferably random access memory RAM and a secondary memory . Secondary memory includes hard disk drive and or a removable storage drive . Removable storage drive reads from and or writes to a removable storage unit in a well known manner. Removable storage unit can be a floppy diskette drive a magnetic tape drive or a compact disk drive. Removable storage unit includes any computer usable storage medium having stored therein computer software and or data such as an object s methods and data.

Client computer has one or more input devices including but not limited to a mouse or other pointing device such as a digitizer a keyboard or any other data entry device.

Computer programs also called computer control logic including object oriented computer programs are stored in main memory and or the secondary memory and or removable storage units . Computer programs can also be called computer program products. Such computer programs when executed enable computer system to perform the features of the present invention as discussed herein. In particular the computer programs when executed enable the processor to perform the features of the present invention. Accordingly such computer programs represent controllers of computer system .

In another embodiment the invention is directed to a computer program product comprising a computer readable medium having control logic computer software stored therein. The control logic when executed by processor causes processor to perform the functions of the invention as described herein.

In yet another embodiment the invention is implemented primarily in hardware using for example one or more state machines. Implementation of these state machines so as to perform the functions described herein will be apparent to persons skilled in the relevant arts.

Prior to describing the class definitions in detail a description of an exemplary software object in an OOP environment is described.

In object oriented programming software objects are outgrowths or instances of a particular class. A class defines methods and variables that are included in a particular type of software object . Software objects that belong to a class are called instances of the class. A software object belonging to a particular class will contain specific values for the variables contained in the class. For example a software class of vehicles may contain objects that define a truck a car a trailer and a motorcycle.

In object oriented programming classes are arranged in a hierarchical structure. Objects that are defined as special cases of a more general class automatically inherit the method and variable definitions of the general class. As noted the general class is referred to as the superclass. The special case of the general class is referred to as the subclass of the general class. In the above example vehicles is the general class and is therefore referred to as the superclass. The objects i.e. truck car trailer and motorcycle are all special cases of the general class and are therefore referred to as subclasses of the vehicle class.

Example OOP class definitions are now described. The functions performed by the methods included in the class definitions and the type of information stored in and or passed as parameters in the variables of the classes depicted will be apparent to those skilled in the art.

Soft switch class includes variables and methods . Variables include information about a soft switch including soft switch s identifier ID error message information RNECP information alarm server information and run time parameters. Variables can be used to provide information to the methods included in soft switch class .

Methods can include a method to start a soft switch to receive information to receive a message to receive a response to a message and to perform updates. Methods also include the means to read configuration data to acknowledge messages to get call context information from a signaling message and to get call context information from an IPDC message. Methods also include the means to get call context information from a route response to get call context information from a route server message and to forward messages.

Variables can be used to store information about call context class objects . For example variables can include signaling message information for an incoming message signaling message information for an outgoing message a time stamp and the number of stored signaling messages.

Methods include various functions which can be performed by call context class . For example methods include a call context message which passes parameters identifying a call event and a signaling message. Other methods include a function to get an IAM message to get a call event identifier to get an originating network ID to get a terminating network ID to get a signaling message and to get a subroute. Methods also include the means to add an ACM message an ANM message an REL message an RLC message a connect message and a route response message. Methods also permit call context class to set various states as for example that an ACM was sent an IAM was received an RTP connect was sent a CONI was received a connect was sent an answer was sent an REL was sent that the system is idle that an ANM was sent or that an RLC was sent. Methods can also get a route.

Methods include various signaling message functions which can pass various parameters and receive various parameters. Parameters which can be sent by signaling message functions include the request response header Rhs the signaling message the network ID the port the route response the IPDC message and the soft switch information. Methods also include the function to set the originating ingress port to set the network identifier to get a message type and to get a network identifier.

Variables include for a respective route server an identifier ID a ten digit table a six digit table a three digit table a treatment table a potential term table an local serving area LSA table a circuit group CG table an destination AD table a runtime parameters and an alarm server.

Methods include several functions. For example methods include a start function a receive message function a receive request function an update function a process function and a digit analysis function.

Variables include the type of a route response and a version of the route response. Methods include several functions. For example methods include the route response function the get type of route response function the get call event identifier function the get originating out BMLC function the get originating IP function the get terminating out BMLC function the get terminating IP function and the get terminating network ID function.

Variables include the nature of address the dialed digits the ANT version and the jurisdiction information parameters of route request class .

Methods include multiple functions. Methods include the route request function the get dialed digits function the get nature of address function and the get network ID function. Network ID class is in communication with route request class . Potential term container class is in communication with route response class .

Route class is in communication with route response class . Route class includes methods . Methods include several functions. For example methods can include a route function a get next function a begin function an end function a get current function an add route node function and an end function. Route node class is in communication with route class .

Route node includes variables and methods . Variables include a BMLC an IP a location and a bay name for a particular route node. Methods include several functions. For example methods can include a get OPC function a get DPC function a get terminating CIC TCIC function a get IP function a reserve function a route node function a get type function a match function a get pool function and a get BMLC function.

Call event identifier class is in communication with route node class . Route node class has additional route node subclasses . Route node subclasses include MLC route node class modem route node class RTP route node class and treatment route node class . MLC route node class includes methods . Methods includes several functions. For example methods can include a match function an are you available function a get BMLC function and an unreserve function.

RTP route node class includes methods . Methods include several functions e.g. a get address port pair function. Treatment route node class includes variables e.g. an announcement to play variable. RTP route node class has two subclasses i.e. IP address class and IP port class .

Finally includes route node container class . Route node container class includes methods . Methods can include several functions e.g. a begin function a get current function and a next function.

Subpool classes include modem pool class real time transport protocol RTP pool class and chain pool class . RTP pool class includes methods .

Methods include several functions including a get originating route node function a get terminating out route node function and a get route node function. Chain pool class includes methods including a get function a get route node function a get chain pair function and a get route node function. In communication with modem pool class is modem route node class which is a subclass from route objects . In communication with chain pool class is chain pair class . Chain pair class includes methods including a match MLC route node function a match function and an are you available function. Chain pair class is in communication with MLC route node class i.e. a subclass of route objects class .

TG NAS and AG are connected via an IP interface connection to data network . TG NAS AG are connected via separate interface to network management component . Specifically TG is connected to network management component via interface . NAS is connected to network management component via interface . Also AG is connected to network management component via interface .

In addition includes ANS which as pictured is connected directly via the IP connection to data network . Alternatively the ANS can functionally exist in other areas of the telecommunications network. For example ANS can functionality exist in TG as depicted by ANS TG having ANS functionality . Similarly ANS functionality shown as ANS can be provided by AG .

A TG is a gateway enabling termination of PSTN co carrier trunks and feature group D FG D circuits. illustrates an exemplary TG . Gateway common media processing is illustrated in below. Gateway common media processing on the ingress side will be described with reference to . Gateway common media processing on the egress side will be described with reference to .

Specifically depicts a trunking gateway high level functional architecture for TG . includes calling party connected via carrier facility to DS3 trunks which in turn provide connection to TG . Signaling for a call from calling party is carried via out of band signaling network through SS7 gateway to soft switch . This is shown with signaling .

TG is controlled by soft switch via the IPDC protocol through data network . TG includes PSTN interface card connecting TG to the incoming DS3 trunks from the PSTN. PSTN interface card is connected to a time division multiplexed TDM bus .

TDM bus takes the incoming DS3 trunks and separates the trunks using time division multiplexing into separate DS1 signals . DS1 can be encoded decoded via for example DSP based encoder decoder . Encoder decoder typically performs a voice compression such as G.723.1 G.729 or simply breaks out G.711 64 kbps DS0 channels. Encoder decoder is connected to packet bus for packetizing the incoming digital signals. Packet bus in turn is connected to IP Interface cards . IP Interface cards provide connectivity to data network for transmission of VOIP packets to distant gateways and control messages to soft switch .

TG also includes network management IP interface for receiving and sending network management alarms and events via the simple network management protocol SNMP to network management component .

Trunks can handle switched voice traffic and data traffic. For example trunks can include digital signals DS1 DS4 transmitted over T1 T4 carriers. Table 17 provides typical carriers along with their respective digital signals number of channels and bandwidth capacities.

Alternatively trunks can include optical carriers OCs such as OC 1 OC 3 etc. Table 18 provides typical optical carriers along with their respective synchronous transport signals STSs ITU designations and bandwidth capacities.

With reference to TGs and can receive call control messages from and send messages to soft switch via the IPDC protocol. Soft switch site implements a signaling stack e.g. an SS7 signaling network stack for communications with legacy PSTN devices. On the ingress side of the telecommunications network ingress trunking gateway seizes a circuit as a call is initiated i.e. assuming calling party is placing a call to called party .

As the circuit is seized at call initiation SS7 signaling network begins the process of setting up a call by sending messages via SS7 GW to soft switch . As the call progresses ingress TG can receive commands from soft switch to complete the call through ingress TO and out through the virtual voice network via the IP interface to a destination gateway.

On the egress side of the network this process is reversed to complete the call through the interconnected network to egress trunking gateway and ultimately to called party .

The first process that takes place is data detection process . Data detection process attempts to detect the media type of the call traffic. The media type of the call traffic can include voice data and modem. The media type information can be passed via IPDC protocol to soft switch for process determination.

In one embodiment no additional processing is required. In another embodiment a compression decompression software component CODEC that is used in performing media processing can be selected based on data detection process . Specifically if the data is determined to be modem traffic and if a suitable CODEC exists for the data rate soft switch can choose to incorporate this CODEC on the stream. Alternatively if the call is a voice call soft switch can select the CODEC optimized for voice processing and current network conditions. In an embodiment of the invention data calls can always be processed with the default bit rate CODEC.

In silence detection and suppression process silence in a voice call can be detected and suppressed yielding potential decreases in the volume of transmission of packets carrying no digitized voice due to silence.

In encoding process once a CODEC has been chosen by soft switch or the decision is made to use the default CODEC the media stream passes through a digital signal processor DSP to apply an appropriate compression algorithm. This compression processing algorithm can take the media stream as a traditional stream from the traditional voice world and transform it into a stream suitable for digital packetization. Once these packets have been formed ingress TG can process the packets into IP packets and prepare the packets for transport through the IP backbone to egress TG .

On the egress side of the network packetized media is converted back to a digital stream. Specifically egress TG can take the packets from data network and decompress them and decode them with the same DSP process and algorithm used on the ingress side of the network.

Additional media stream processing functions internal to TGs can include for example the ancillary processes of silence detection and suppression voice activation and comfort noise insertion . The media stream processing functions include for example the major core functionality needed for TGs .

Other functional components needed in trunking gateways can also be included. Other functional components can include the provisioning and maintenance of trunking gateways .

TGs provide voice network connectivity to the traditional public switched telephone network PSTN . TGs can accept co carrier and feature group D FG D trunks. It would be apparent to those skilled in the art that TGs can accept other telecommunications trunks. TGs allow for termination of SS7 signaled calls to and from telecommunications network .

TGs can convert the media stream into packets for transmission over data network . TGs also provide a management interface for remote management control and configuration changes. TGs can interface to multiple components of telecommunications network . For example TGs can interface with for example the PSTN for carrying media soft switch for communication of control messages from soft switch the voice network interface of data network for carrying packetized voice media and network management component for sending SNMP alerts to the network operation center NOC .

TGs interface to the PSTN via co carrier or FG D trunks. These trunks are groomed via DACS to allow multiple two way 64 kilobits per second KPS circuits to pass the media stream into and out of TGs . The PSTN interface to TGs provides all low level hardware control for the individual circuits and allows the interface to look like another switch connection to the PSTN network.

TGs also interface with soft switch . Referring to the TG to soft switch interface is used to pass information needed to control the multiple media streams. Soft switch controls all available circuit channels that connect through TGs . TG to soft switch interface uses the physical EP network interface cards NICs to send and receive control information to and from soft switch using the IPDC protocol. The IPDC protocol will be described in greater detail below.

Referring to TGs interface with a voice virtual private network VPN that is overlaid on an IP data network . The TG to voice VPN interface sends or receives voice packets on the IP side of the network from TGs to other network components e.g. to another of TGs . TG to voice VPN interface in a preferred embodiment can physically be a 100 BaseT Ethernet interface but can be logically divided into virtual ports that can be addressable via soft switch . The media stream can be connected through this interface i.e. the TG to voice VPN interface to a distant connection with a real time transport protocol RTP connection.

TGs can also interface with network management component NMC for the purposes of communicating network management SNMP alerts. The TGs to SNMP interface is a management interface that can be connected to NMC of the network management network through a dedicated connection on TGs . SNMP messages that are generated at TGs can be passed to the network operations center NOC through the TG to SNMP interface. In addition messages and commands from the NOC can be passed to TGs through this interface for several purposes including for example network management configuration and control.

An AG is a gateway that enables customers to connect via a Direct Access Line DAL from their customer premise equipment CPE such as for example a private branch exchange PBX to the telecommunications network. The AG terminates outgoing and incoming calls between the CPE the telecommunications network and the PSTN.

A T1 DAL can be connected from the PSTN to a PSTN interface card supporting T1 in band channel associated signaling CAS . PSTN interface cards are connected to TDM bus . Using TDM bus incoming T1 and PRI signals are broken into separate DS1 signals .

DS1 is then encoded via DSP based encode decode . After encoding via DSP based encode decode the signal is packetized via packet bus to be transmitted via IP interface cards over data network . IP packets containing signaling information e.g. D channel are routed to soft switch . IP packets containing media are transmitted to other media gateways i.e. access servers such as an AG or TG

IP interface card includes both control and signaling information in its packets. This is illustrated showing IPDC protocol control information and signaling information .

AG delivers signaling information inband over data network to soft switch . Accordingly calling party need not have its customer facility have connectivity with SS7 signaling network .

AG is functionally equivalent to TG . AG differs from TG only in the circuit types and scale of the terminated circuits supported. The circuit types and scale of terminated circuits supported drives the line side cards and signaling that AG provides to a PBX or other customer facility . The circuit associated and in band signaling provided by the PBX or customer facility must be passed from AG to soft switch via the IPDC protocol. AG receives call processing information from soft switch .

AGs interface to several components of telecommunications network . The interfaces of AGs include interfaces facing the network i.e. data network and network management component as described for TGs above. AGs also interface on the line side through line side card interfaces which can be needed to support in band T1 and ISDN primary rate interface ISDN PRI circuits.

In band T1 and ISDN PRI interfaces can be provisioned on an as needed basis on AGs to support the equipment that can terminate the circuit on the far end. The ISDN PRI can support standard ISDN circuit associated D channel signaling in the 23B 1D NB 1D and NB 2D bearer B and data D channel configurations. For the in band signaling T1 configuration the circuit can support wink start or loop start signaling.

The next six paragraphs briefly introduce wink start loop start and ground start signaling as would be apparent to a person having ordinary skill in the relevant communications signaling art.

Wink start refers to seizing a circuit by using a short duration signal. The signal is typically of a 140 millisecond duration. The wink indicates the availability of an incoming register for receiving digital information from a calling switch. Wink starts are used in telephone systems which use address signaling.

Loop start refers to seizing a circuit using a supervisory signal. A loop start signal is typically generated by taking the phone off hook. With a loop start a line is seized by bridging a tip and ring i.e. the wires of the telephone line through a resistance. A loop start trunk is the most common type of trunk found in residential installations. The ring lead is connected to 48 V and the tip lead is connected to 0 V i.e. connected to ground . To initiate a call a loop ring can be formed through the telephone to the tip. A central office CO can ring a telephone by sending an AC voltage to the ringer within the telephone. When the telephone goes off hook the DC loop is formed. The CO detects the loop and the fact that it is drawing a DC current and stops sending the ringing voltage.

Ground starting refers to seizing a trunk where one side of a two wire trunk the ring conductor of the tip and ring is temporarily grounded to get a dial tone. Ground starts are typically used for CO to PBX connections. Ground starting is effectively a handshaking routine that is performed by the CO and PBX. The CO and PBX agree to dedicate a path so that incoming and outgoing calls cannot conflict so that glare cannot occur.

The PBX can check to see if a CO ground start trunk has been dedicated. In order to see if the trunk has been dedicated the PBX checks to see if the tip lead is grounded. An undedicated ground start trunk has an open relay between 0 V ground and the tip lead connected to the PBX. If the trunk has been dedicated the CO will close the relay and ground the tip lead.

In a ground start the PBX can also indicate to the CO that it requires a trunk. The PBX has a PBX CO caller circuit. The PBX CO caller circuit can call a CO ground start trunk. The PBX CO caller circuit briefly grounds the ring lead causing DC current to flow. The CO detects the current flow and interprets it as a request for service from the PBX.

 Glare occurs when both ends of a telephone line or trunk are seized at the same time for different purposes or by different users. Glare resolution refers to the ability of a system to ensure that if a trunk is seized by both ends simultaneously then one caller is given priority and the other is switched to another trunk.

AGs and interface to the PSTN via T1 CAS signaling and ISDN PRI trunks. ISDN PRI trunks are groomed via the DACS and to allow multiple two way 64 kps circuits to pass signaling information circuits to pass signaling information and the media stream into and out of AGs and . The AG to PSTN interface provides all low level hardware control for the individual circuits. The AG to PSTN interfaces specifically PSTN interface cards and also allow the interface to look like a switch connection to the PSTN network.

AG to soft switch interface can be used to pass information needed to control multiple media streams. Soft switch can control all available circuit channels that connect through AGs . AG to soft switch interface can use the physical voice network interface card to send and receive control information to and from soft switch using the IPDC protocol.

AGs can have a separate physical interface to network management component NMC . AG has network management IP interface which sends network management alarms and events in the SNMP protocol format to NMC . The AG to NMC interface can be used for delivery of SNMP messages and additional functions. Examples of additional functions that can be defined include for example functions for provisioning updating and passing special alarms and performance parameters to AGs from the network operation center NOC of NMC .

NASs accept control information from soft switch and process the media stream accordingly. Modem traffic is routed to the internal processes within NASs to terminate the call and route the data traffic out to data network . The reader is directed to U.S. patent application entitled System and Method for Bypassing Data from Egress Facilities filed concurrently herewith which is incorporated herein by reference in its entirety describing with greater details the interaction between NASs and control server soft switch .

NAS receives trunk interfaces from the PSTN at PSTN interface card . PSTN interface card is connected to TDM bus .

TDM bus in turn can break out separate DS1 signals . These DSI signals can be terminated to modems . Modem can convert the incoming data stream from a first format to a second format over packet bus to IP interface card or . It is important to note that IP interfaces and are the same.

Interface card carries media e.g. data voice traffic etc. over data network . The media can be sent over multiple routers in data network to the media s final destination. IP interface card transmits packets of information through data network to soft switch including control information in the IPDC protocol format. Interface cards and can also perform additional functions

NAS includes network management interface card NMIC for providing network management alarms and events in an SNMP protocol format to network management component .

Telecommunications network supports interaction with NASs via communication of control information from soft switch . The interfaces between NASs and the other network components of telecommunications network can be identical to those found on TGs with the exception of the FG D interface.

NASs can interface to the PSTN via co carrier trunks. The co carrier trunks can be groomed via the DACS to allow multiple two way 64 kps circuits to pass the media stream into and out of NASs . The NASs to PSTN interface provides all low level hardware control for the individual circuits. The NASs to PSTN interface looks like another switch connection to the PSTN network.

NASs interface with soft switch in order to pass information required to control the multiple media streams. Soft switch via the NASs to soft switch interface can control all available circuit channels that connect through NASs . The interface between NASs and soft switch uses the physical voice network interface card MC to send and receive control information to and from soft switch and NASs via the IPDC protocol.

NASs can interface with the backbone network of data network . The NASs to backbone interface of data network can allow the media stream to access the data network and to terminate to any termination with an IP address including public Internet and world wide web sites and other Internet service providers ISP . This modem traffic media stream can be separate from any voice data media stream that is carried over the backbone. Modem traffic can enter NASs in the form of serial line interface protocol SLIP or a point to point protocol PPP protocol and can be terminated to modems and can then be converted into another protocol such as for example an IPX an Apple Talk a DECNET protocol an RTP protocol an Internet protocol IP protocol a transmission control protocol user datagram protocol UDP or any other appropriate protocol for routing to for example another private network destination.

NASs can use a separate physical interface for communication of SNMP alerts and messages to NMC . The NAS to NMC interface can be used for additional functions. Examples of additional functions that can be defined include for example provisioning updating and passing special alarms and performance parameters to NASs from the network operations center NOC .

Referring to voice and data traffic comes into DACS from carrier facility on incoming trunks. DACS receives a signal from soft switch over data network indicating how DACS is to switch the traffic. Depending on the signal provided by soft switch DACS can switch the incoming traffic onto either circuits directed to TG or circuits directed to NAS .

More generally a DACS is a digital switching machine employed to manage or groom traffic at a variety of different traffic speeds. Grooming functions of DACS include the consolidation of traffic from partly filled incoming lines with a common destination and segregation of incoming traffic of differing types and destinations. A traditional DACS can have one of several available architectures. Example architectures which accommodate different data rates and total port counts include narrowband or 1 0 wideband or 3 1 and broadband or 3 3 .

As backbone traffic has grown with increased data traffic there is an emerging need for even higher capacity DACS having interface speeds of OC 48 and beyond as well as cell and packet switching capabilities to accommodate the increasing data traffic.

As data traffic continues to grow increasing the demands of telecommunications networks and as through put speeds increase DACS e.g. DACS are migrating to include higher speed switching matrices capable of terabit throughput. DACS can also include high speed optical interfaces.

Telecommunications network can also make use of virtual DACS VDACS . VDACS are conceptually the use of a computer software controlled circuit switch. For example a DACS can be built which is capable of intercommunicating with a soft switch via a protocol such as for example internet protocol device control IPDC to perform the functionality of a DACS.

In one embodiment of the invention a NAS is used to terminate co carrier or local trunks and a TG is used to terminate long distance trunks. In such a system if a voice call were to come in over a NAS then the voice call could be transmitted to the TG for termination. One approach that can be used to terminate this voice call includes occupying an outgoing channel to transmit the call out of the NAS and into the TG. Another approach uses a commandable DACS a VDACS. The VDACS can cross connect on command so as to act as a commandable circuit switch. In practice the soft switch can send a command down to the VDACS via IPDC for example. A VDACS can be built by using a traditional DACS with the addition of application program logic supporting control and communication with a soft switch.

Referring back to ANSs store pre recorded announcements on disk in an encoded format. ANSs provide telecommunications network with the ability to play pre recorded messages and announcements at the termination of a call. For example ANSs can play a message stating that all circuits are busy. 

In one embodiment the functionality of ANSs can be included in TG and or AG . The features of this embodiment are dependent on the amount of resources in TG and AG . This internal announcement server capability is shown in including for example ANS in TG and ANS in AG . It would be apparent to those skilled in the art that ANS functionality can be placed in other systems such as for example soft switch and NAS .

In another embodiment ANSs are applications running on one or more separate servers as shown in . depicts an announcement server ANS component interface design . includes ANS which is in communication with TG AG and soft switch over data network . ANS can be controlled by soft switch via the IPDC protocol. ANS can send network management alerts and events to network management component NMC . Data distributor can send announcement files to ANS .

A benefit of providing separate ANSs is that a more robust database of announcements can be stored and made available for use by the soft switch than is supported in conventional networks. Another benefit of a separate ANS is that less storage is required in TGs and AGs since the announcement functionality is supported by the server of ANSs server. ANSs can be controlled by one or more soft switches to play the voice messages via the IPDC protocol.

After determining that an announcement should be played Soft switch chooses an ANS or that is closest to the point of origination for the call if available. The ANS and gateway site establish a real time transport protocol RTP session for the transmission of the voice announcement. Then ANS or streams the file over RTP to the terminating gateway. When the message is complete ANSs can replay the message or disconnect the call.

ANSs can store the message files in each of the media coder decoders CODECs that the network supports. ANSs can send announcements stored in the format of the G.711 G.726 and G.728 and other standard CODECs. The soft switch can direct ANS to play announcements using other CODECS if the network enters a state of congestion. Soft switch can also direct ANS to play announcements using other CODECs if the gateway or end client is an IP client that only supports a given CODEC. In another embodiment the CODEC of an announcement can be modified while the announcement is playing.

ANS will now be described with greater detail with reference to . ANS has several interfaces. ANS interfaces include the provisioning control alarming and voice path interfaces. ANS also has several data paths. The path from ANS to TG or to AG have a common voice path interface i.e. which is the same for TG and AG . The voice path interface can use RTP and RTCP.

In a preferred embodiment ANS to soft switch interface provides for a data path using the internet protocol device control IPDC protocol to control announcement server .

The ANS to SNMP agent in network management component data path is used to send alarm and event information from ANS to SNMP agent via SNMP protocol.

Data distributor to announcement server data path carries announcement files between announcement server and data distributor . The provisioning interface downloads via a file transfer protocol FTP encoded voice announcement files to announcement server .

Announcement server uses a separate physical interface for all SNMP messages and additional functions that can be defined. Examples of additional functions that can be defined include provisioning updating and passing of special alarms and performance parameters to announcement servers from NOC .

In another embodiment announcement server is located in soft switch site . It would be apparent to those skilled in the art that announcement server could be placed in other parts of telecommunications network .

In an example embodiment data network can be a packet switched network. A packet switched network such as for example an ATM network unlike a circuit switch network does not require dedicated circuits between originating and terminating locations within the packet switch network. The packet switched network instead breaks a message into pieces known as packets of information. Such packets are then encapsulated with a header which designates a destination address to which the packet must be routed. The packet switched network then takes the packets and routes them to the destination designated by the destination address contained in the header of the packet.

Western soft switch site of includes soft switches SS7 GWs CSs RSs and RNECPs all interconnected by redundant connections to ethernet switches ESs . ESs are used to interconnect the host computers attached to them to create an ethernet switched local area network LAN . ESs are redundantly connected to routers . The host computers in the local area network included in western soft switch site can communicate with host computers in other local area networks e.g. at gateway sites via routers .

Gateway site of includes TGs AGs and NASs interconnected via redundant connections to ESs . ESs interconnect the multiple network devices to create a LAN. Information can be intercommunicated to and from host computers on other LANs via routers at gateway site . Routers are connected by redundant connections to ESs .

Gateway site of includes TGs AGs and NASs connected via redundant connections to ESs to form a local area network. Ethernet switches ESs can in turn intercommunicate information between the LAN in gateway site and LANs at other sites e.g. at western soft switch site and gateway site via routers . Routers are connected to ESs via redundant connections.

Routers of western soft switch site routers of gateway site and routers of gateway site can be connected via NICs such as for example asynchronous transfer mode ATM interface cards in routers and physical media such as for example optical fiber link connections and or copper wire connections. Routers transfer information between one another and intercommunicate according to routing protocols.

Data network can include a plurality of network routers. Network routers are used to route information between multiple networks. Routers act as an interface between two or more networks. Routers can find the best path between any two networks even if there are several different networks between the two networks.

Network routers can include tables describing various network domains. A domain can be thought of as a local area network LAN or wide area network WAN . Information can be transferred between a plurality of LANs and or WANs via network devices known as routers. Routers look at a packet and determine from the destination address in the header of the packet the destination domain of the packet. If the router is not directly connected to the destination domain then the router can route the packet to the router s default router i.e. a router higher in a hierarchy of routers. Since each router has a default router to which it is attached a packet can be transmitted through a series of routers to the destination domain and to the destination host bearing the packet s final destination address.

A local area network LAN can be thought of as a plurality of host computers interconnected via network interface cards NICs in the host computers. The NICs are connected via for example copper wires so as to permit communication between the host computers. Examples of LANs include an ethernet bus network an ethernet switch network a token ring network a fiber digital data interconnect FDDI network and an ATM network.

A wide area network WAN is a network connecting host computers over a wide area. In order for host computers on a particular LAN to communicate with a host computer on another LAN or on a WAN network interfaces interconnecting the LANs and WANs must exist. An example of a network interface is a router discussed above.

A network designed to interconnect multiple LANs and or WANs is known as an internet. An internet can transfer data between any of a plurality of networks including both LANs and WANs. Communication occurs between host computers on one LAN and host computers on another LAN via for example an internet protocol IP protocol. The IP protocol requires each host computer of a network to have a unique IP address enabling packets to be transferred over the internet to other host computers on other LANs and or WANs that are connected to the internet. An internet can comprise a router interconnecting two or more networks.

The Internet with a capital I is a global internet interconnecting networks all over the world. The Internet includes a global network of computers which intercommunicate via the internet protocol IP family of protocols.

An intranet is an internet which is a private network that uses internet software and internet standards such as the internet protocol IP . An intranet can be reserved for use by parties who have been given the authority necessary to use that network.

Data network includes a plurality of wires and routes making up its physical hardware infrastructure. Network protocols provide the software infrastructure of data network .

Early network protocols and architectures were designed to work with specific proprietary types of equipment. Early examples included IBM systems network architecture SNA and Digital Equipment Corporation s DECnet.

Telecommunications vendors have moved away from proprietary network protocols and technologies to multi vendor protocols. However it can be difficult for all necessary vendors to agree on how to add new features and services to a multi vendor protocol. This can be true because vendor specific protocols can in some cases offer a greater level of sophistication. For example initial versions of asynchronous transfer mode ATM completed by the ATM Forum did not have built in quality of service QoS capabilities. Recent releases of the specification added those features including parameters for cell transfer delay and cell loss ratio. However interoperability among equipment of different vendors and device performance still need improvement.

The IETF is working on defining certain Internet protocols IP classes of service . IP classes of service could provide a rough equivalent to ATMs QoS. IP classes of service is included as part of the IETF s integrated services architecture ISA . ISA s proposed elements include the resource reservation protocol RSVP a defined packet scheduler a call admission control module an admission control manager and a set of policies for implementing these features many of the same concepts already outlined in ATM QoS .

The Internet protocol IP has become the primary networking protocol used today. This success is largely a part of the Internet which is based on the transmission control protocol Internet protocol TCP IP family of protocols. TCP IP is the most common method of connecting PCs workstations and servers. TCP IP is included as part of many software products including desktop operating systems e.g. Microsoft s Windows 95 or Windows NT and LAN operating systems. To date however TCP IP has lacked some of the desired features needed for mission critical applications.

The most pervasive LAN protocol to date has been IPX SPX from Novell s NetWare network operating system NOS . However IPX SPX is losing ground to TCP IP. Novell has announced that it will incorporate native IP support into NetWare ending NetWare s need to encapsulate IPX packets when carrying them over TCP IP connections. Both UNIX and Windows NT servers can use TCP IP. Banyan s VINES IBM s OS 2 and other LAN server operating systems can also use TCP IP.

IPv6 previously called next generation IP or IPng is a backward compatible extension of the current version of the Internet protocol IPv4. IPv6 is designed to solve problems brought on by the success of the Internet such as running out of address space and router tables . IPv6 also adds needed features including circuiting security auto configuration and real time services similar to QoS. Increased Internet usage and the allocation of many of the available IP addresses has created an urgent need for increased addressing capacity. IPv4 uses a 32 byte number to form an address which can offer about 4 billion distinct network addresses. In comparison IPv6 uses 128 bytes per address which provides for a much larger number of available addresses.

Originally developed to enhance IPv4 with QoS features RSVP lets network managers allocate bandwidth based on the bandwidth requirements of an application. Basically RSVP is an emerging communications protocol that signals a router to reserve bandwidth for real time transmission of data video and audio traffic.

Resource reservation protocols that operate on a per connection basis can be used in a network to elevate the priority of a given user temporarily. RSVP runs end to end to communicate application requirements for special handling. RSVP identifies a session between a client and a server and asks the routers handling the session to give its communications a priority in accessing resources. When the session is completed the resources reserved for the session are freed for the use of others.

RSVP offers only two levels of priority in its signaling scheme. Packets are identified at each router hop as either low or high priority. However in crowded networks two level classification may not be sufficient. In addition packets prioritized at one router hop might be rejected at the next.

Accepted as an IETF standard in 1997 RSVP does not attempt to govern who should receive bandwidth and questions remain about what will happen when several users all demand a large block of bandwidth at the same time. Currently the technology outlines a first come first served response to this situation. The IETF has formed a task force to address the issue.

Because RSVP provides a special level of service many people equate QoS with the protocol. For example Cisco currently uses RSVP in its IPv4 based internetwork router operating system to deliver IPv6 type QoS features. However RSVP is only a small part of the QoS picture because it is effective only as far as it is supported within a given client server connection. Although RSVP allows an application to request latency and bandwidth RSVP does not provide for congestion control or network wide priority with the traffic flow management needed to integrate QoS across an enterprise.

RTP is an emerging protocol for the Internet championed by the audio video transport workgroup of the IETF. RTP supports real time transmission of interactive voice and video over packet switched networks. RTP is a thin protocol that provides content identification packet sequencing timing reconstruction loss detection and security. With RTP data can be delivered to one or more destinations with a limit on delay.

RTP and other Internet real time protocols such as the Internet stream protocol version 2 ST2 focus on the efficiency of data transport. RTP and other Internet real time protocols are designed for communications sessions that are persistent and that exchange large amounts of data. RTP does not handle resource reservation or QoS control. Instead RTP relies on resource reservation protocols such as RSVP communicating dynamically to allocate appropriate bandwidth.

RTP adds a time stamp and a header that distinguishes whether an IP packet is data or voice allowing prioritization of voice packets while RSVP allows networking devices to reserve bandwidth for carrying unbroken multimedia data streams.

Real time Control Protocol RTCP is a companion protocol to RTP that analyzes network conditions. RTCP operates in a multi cast fashion to provide feedback to RTP data sources as well as all session participants. RTCP can be adopted to circumvent datagram transport of voice over IP in private IP networks. With RTCP software can adjust to changing network loads by notifying applications of spikes or variations in network transmissions. Using RTCP network feedback telephony software can switch compression algorithms in response to degraded connections.

Digital voice and video comprise of large quantities of data that when broken up into packets must be delivered in a timely fashion and in the right order to preserve the qualities of the original content. Protocol developments have been focused on providing efficient ways to send content to multiple recipients transmission referred to as multi casting. Multi casting involves the broadcasting of a message from one host to many hosts in a one to many relationship. A network device broadcasts a message to a select group of other devices such as PCS or workstations on a LAN WAN or the Internet. For example a router might send information about a routing table update to other routers in a network.

Several protocols are being implemented for IP multi casting including upgrades to the Internet protocol itself. For example some of the changes in the newest version of IP IPv6 will support different forms of addressing for uni cast point to point communications any cast communications with the closest member of a device group and multi cast. Support for IP multi casting comes from several protocols including the Internet group management protocol IGMP protocol independent multi cast PIM and distance vector multi cast routing protocol DVMRP . Queuing algorithms can also be used to ensure that video or other multi cast data types arrive when they are supposed to without visible or audible distortion.

Real time transport protocol RTP is currently an IETF draft designed for end to end real time delivery of data such as video and voice. RTP works over the user datagram protocol UDP providing no guarantee of in time delivery quality of service QoS delivery or order of delivery. RTP works in conjunction with a mixer and translator and supports encryption and security. The real time control protocol RTCP is a part of the RTP definition that analyzes network conditions. RTCP provides mandatory monitoring of services and collects information on participants. RTP communicates with RSVP dynamically to allocate appropriate bandwidth.

Internet packets typically move on a first come first serve basis. When the network becomes congested Resource Reservation Protocol RSVP can enable certain types of traffic such as video conferences to be delivered before less time sensitive traffic such as E mail for potentially a premium price. RSVP could change the Internet s pricing structure by offering different QoS at different prices.

The RSVP protocol is used by a host on behalf of an application to request a specific QoS from the network for particular data streams or flows. Routers can use the RSVP protocol to deliver QoS control requests to all necessary network nodes to establish and maintain the state necessary to provide the requested service. RSVP requests can generally although not necessarily result in resources being reserved in each node along the data path.

RSVP is not itself a routing protocol. RSVP is designed to operate with current and future uni cast and multi cast routing protocols. An RSVP process consults the local routing database to obtain routes. In the multi cast case for example the host sends IGMP messages to join a multi cast group and then sends RSVP messages to reserve resources along the delivery paths of that group. Routing protocols determines where packets are forwarded. RSVP is concerned with only the QoS of those packets as they are forwarded in accordance with that routing.

A virtual private network VPN is a wide area communications network operated by a telecommunications carrier that provides what appears to be dedicated lines when used but that actually includes trunks shared among all customers as in a public network. A VPN allows a private network to be configured within a public network.

VPNs can be provided by telecommunications carriers to customers to provide secure guaranteed long distance bandwidth for their WANs. These VPNs generally use frame relay or switched multi megabyte data service SMDS as a protocol of choice because those protocols define groups of users logically on the network without regard to physical location. ATM has gained favor as a VPN protocol as companies require higher reliability and greater bandwidth to handle more complex applications. VPNs using ATM offer networks of companies with the same virtual security and QoS as WANs designed with dedicated circuits.

The Internet has created an alternative to VPNs at a much lower cost i.e. the virtual private Internet. The virtual private Internet VPI lets companies connect disparate LANs via the Internet. A user installs either a software only or a hardware software combination that creates a shared secure intranet with VPN style network authorizations and encryption capabilities. A VPI normally uses browser based administration interfaces.

A plurality of protocol standards exist today for VPNs. For example IP security IPsec point to point tunneling protocol PPTP layer 2 forwarding protocol L2F and layer 2 tunneling protocol L2TP . The IETF has proposed a security architecture for the Internet protocol IP that can be used for securing Internet based VPNs. IPsec facilitates secure private sessions across the Internet between organizational firewalls by encrypting traffic as it enters the Internet and decrypting it at the other end while allowing vendors to use many encryption algorithms key lengths and key escrow techniques. The goal of IPsec is to let companies mix and match the best firewall encryption and TCP IP protocol products.

Point to point tunneling protocol PPTP provides an alternate approach to VPN security than the use of IPsec. Unlike IPsec which is designed to link two LANs together via an encrypted data stream across the Internet PPTP allows users to connect to a network of an organization via the Internet by a PPTP server or by an ISP that supports PPTP. PPTP was proposed as a standard to the IETF in early 1996. Firewall vendors are expected to support PPTP.

PPTP was developed by Microsoft along with 3Com Ascend and US Robotics and is currently implemented in WINDOWS NT SERVER 4.0 WINDOWS NT WORKSTATION 4.0 WINDOWS 95 via an upgrade and WINDOWS 98 available from Microsoft Corporation of Redmond Wash.

The tunneling in PPTP refers to encapsulating a message so that the message can be encrypted and then transmitted over the Internet. PPTP by creating a tunnel between the server and the client can tie up processing resources.

Developed by Cisco layer 2 forwarding protocol L2F resembles PPTP in that it also encapsulates other protocols inside a TCP IP packet for transport across the Internet or any other TCP IP network such as data network . Unlike PPTP L2F requires a special L2F compliant router which can require changes to a LAN or WAN infrastructure runs at a lower level of the network protocol stack and does not require TCP IP routing to function. L2F also provides additional security for user names and passwords beyond that found in PPTP.

The layer 2 tunneling protocol L2TP combines specifications from L2F with PPTP. In November 1997 the IETF approved the L2TP standard. Cisco is putting L2TP into its Internet operating system software and Microsoft is incorporating it into WINDOWS NT 5.0. A key advantage of L2TP over IPsec which covers only TCP IP communications is that L2TP can carry multiple protocols. L2TP also offers transmission capability over non IP networks. L2TP however ignores data encryption an important security feature for network administrators to employ VPNs with confidence.

Data network will now be described in greater detail relating to example packet switched networks. It will be apparent to persons having skill in the art that multiple network types could be used to implement data network including for example ATM networks frame relay networks IP networks FDDI WAN networks SMDS networks X 25 networks and other kinds of LANs and WANs.

It would be apparent to those skilled in the art that other data networks could be used interchangeably for data network such as for example an ATM X.25 Frame relay FDDI Fast Ethernet or an SMDS packet switched network. Frame relay and ATM are connection oriented services. Switched multi megabyte data service SMDS is a connection oriented mass packet service that offers speeds up to 45 Mbps. Originally SMDS was intended to fill the gap for broadband services until broadband ISDN BISDN could be developed. Because the infrastructure for BISDN is not fully in place some users have chosen SMDS.

ATM is a high bandwidth low delay packet switching and multiplexing network technology. ATM packets are known as cells. Bandwidth capacity is segmented into 53 byte fixed sized cells having a header and payload fields. ATM is an evolution of earlier packet switching network methods such as X.25 and frame relay which used frames or cells that varied in size. Fixed length packets can be switched more easily in hardware than variable size packets and thus result in faster transmissions.

Each ATM cell contains a 48 byte payload field and a 5 byte header that identifies the so called virtual circuit of the cell. ATM can allocate bandwidth on demand making it suitable for high speed combinations of voice data and video services. Currently ATM access can perform at speeds as high as 622 Mbps or higher. ATM has recently been doubling its maximum speed every year.

In an example embodiment data network is an asynchronous transfer mode ATM network. An ATM cell of data network includes a header having addressing information and header error checking information and a payload having the data being carried by the cell .

ATM is a technology defined by a protocol standardized by the International Telecommunications Union ITU T American National Standards Institute ANSI ETSI and the ATM Forum. ATM comprises a number of building blocks including transmission paths virtual paths and virtual channels.

Asynchronous transfer mode ATM is a cell based switching and multiplexing technology designed to be a general purpose connection oriented transfer mode for a wide range of telecommunications services. ATM can also be applied to LAN and private network technologies as specified by the ATM Forum.

ATM handles both connection oriented traffic directly or through adaptation layers or connectionless traffic through the use of adaptation layers. ATM virtual connections may operate at either a constant bit rate CBR or a variable bit rate VBR . Each ATM cell sent into an ATM network contains addressing information that establishes a virtual connection from origination to destination. All cells are transferred in sequence over this virtual connection. ATM provides either permanent or switched virtual connections PVCs or SVCs . ATM is asynchronous because the transmitted cells need not be periodic as time slots of data are required to be in synchronous transfer mode STM .

ATM uses an approach by which a header field prefixes each fixed length payload. The ATM header identifies the virtual channel VC . Therefore time slots are available to any host which has data ready for transmission. If no hosts are ready to transmit then an empty or idle cell is sent.

ATM permits standardization on one network architecture defining a multiplexing and a switching method. Synchronous optical network SONET provides the basis for physical transmission at very high speed rates. ATM also supports multiple quality of service QoS classes for differing application requirements depending on delay and loss performance. ATM can also support LAN like access to available bandwidth.

The primary unit in ATM the cell defines a fixed size cell with a length of 53 octets or bytes comprised of a five octet header and 48 octet payload. Bits in the cells are transmitted over a transmission path in a continuous stream. Cells are mapped into a physical transmission path such as the North American DS1 DS3 and SONET European E1 E3 and E4 ITU T STM standards and various local fiber and electrical transmission payloads. All information is multiplexed and switched in an ATM network via these fixed length cells.

The ATM cell header field identifies the destination cell type and priority and includes six portions. An ATM cell header includes a generic flow control GFC a virtual path identifier VPI a virtual channel identifier VCI a payload type PT a call loss priority CLP and a header error check HEC . VPI and VCI hold local significance only and identify the destination. GFC allows a multiplexer to control the rate of an ATM terminal. PT indicates whether the cell contains user data signaling data or maintenance information. CLP indicates the relative priority of the cell i.e. lower priority cells are discarded before higher priority cells during congested intervals. HEC detects and corrects errors in the header.

The ATM cell payload field is passed through the network intact with no error checking or correction. ATM relies on higher layer protocols to perform error checking and correction on the payload. For example a transmission control protocol TCP can be used to perform error correction functions. The fixed cell size simplifies the implementation of ATM switches and multiplexers and enables implementations at high speeds.

When using ATM longer packets cannot delay shorter packets as in other packet switched networks because long packets are separated into many fixed length cells. This feature enables ATM to carry CBR traffic such as voice and video in conjunction with VBR data traffic potentially having very long packets within the same network.

ATM switches take traffic and segment it into the fixed length cells and multiplex the cells into a single bit stream for transmission across a physical medium. As an example different kinds of traffic can be transmitted over an ATM network including voice video and data traffic. Video and voice traffic are very time sensitive so delay cannot have significant variations. Data on the other hand can be sent in either connection oriented or connectionless mode. In either case data is not nearly as delay sensitive as voice or video traffic conventionally. Conventional however data traffic is very sensitive to loss. Therefore ATM conventionally must discriminate between voice video and data traffic. Voice and video traffic requires priority and guaranteed delivery with bounded delay while data traffic requires simultaneously assurance of low loss. According to the present invention data traffic can also carry voice traffic making it also time dependent. Using ATM in one embodiment multiple types of traffic can be combined over a single ATM virtual path VP with virtual circuits VCs being assigned to separate data voice and video traffic.

The capability of ATM to switch to a virtual channel level is similar to the operation of a private or public branch exchange PBX or telephone switch in the telephone world. In a PBX switch each channel within a trunk group can be switched. Devices which perform VC connections are commonly called VC switches because of the analogy to telephone switches. ATM devices which connect VPs are commonly referred to as VP cross connects by analogy with the transmission network. The analogies are intended for explanatory reasons but should not be taken literally. An ATM cell switching machine need not be restricted to switching only VCs and cross connection to only VPs.

At the ATM layer users are provided a choice of either a virtual path connection VPC or a virtual channel connection VCC . Virtual path connections VPCs are switched based upon the virtual path identifier VPI value only. Users of a VPC can assign VCCs within a VPI transparently since they follow the same route. Virtual channel connections VCCs are switched upon a combined VPI and virtual channel identifier VCI value.

Both VPIs and VCIs are used to route calls through a network. Note that VPI and VCI values must be unique on a specific transmission path TP .

It is important to note that data network can be any of a number of other data type networks including various packet switched data type networks in addition to an ATM network.

Alternatively data network can be a frame relay network. It would be apparent to persons having ordinary skill in the art that a frame relay network could be used as data network . Rather than transporting data in ATM cells data could be transported in frames.

Frame relay is a packet switching protocol used in WANs that has become popular for LAN to LAN connections between remote locations. Formerly frame relay access would top out at about 1.5 Mbps. Today so called high speed frame relay offers around 45 Mbps. This speed is still relatively slow as compared with other technology such as ATM.

Frame relay services employ a form of packet switching analogous to a streamlined version of X.25 networks. The packets are in the form of frames which are variable in length. The key advantage to this approach it that a frame relay network can accommodate data packets of various sizes associated with virtually any native data protocol. A frame relay network is completely protocol independent. A frame relay network embodiment of data network does not undertake a lengthy protocol conversion process and therefore offers faster and less expensive switching than some alternative networks. Frame relay also is faster than traditional X.25 networks because it was designed for the reliable circuits available today and performs less rigorous error detection.

In an embodiment data network can be an internet protocol IP network over an ATM network. It would be apparent to persons having ordinary skill in the art that an internet protocol IP network with any underlying data link network could be used as data network . Rather than transporting data in ATM cells data could be transported in IP datagram packets. The IP data network can lie above any of a number of physical networks such as for example a SONET optical network.

In SS7 signaling network SSPs and are the portions of the backbone switches providing SS7 functions. The SSPs and can be for example a combination of a voice switch and an SS7 switch or a computer connected to a voice switch. SSPs and communicate with the switches using primitives and create packets for transmission over SS7 signaling network .

Carrier facilities can be respectively represented in SS7 network as SSPs . Accordingly the connections between carrier facilities and and signaling network presented as dashed lines in can be represented by connections and . The types of these links are described below.

STPs and act as routers in the SS7 network typically being provided as adjuncts to in place switches. STPs and route messages from originating SSPs and to destination SSPs and . Architecturally STPs and can be and are typically provided in mated pairs to provide redundancy in the event of congestion or failure and to share resources i.e. load sharing is done automatically . As illustrated in B and C STPs and can be arranged in hierarchical levels to provide hierarchical routing of signaling messages. For example mated STPs and mated STPs are at a first hierarchical level while mated STPs are at a second hierarchical level.

SCP can provide database functions. SCP can be used to provide advanced features in SS7 signaling network including routing of special service numbers e.g. 800 and 900 numbers storing information regarding subscriber services providing calling card validation and fraud protection and offering advanced intelligent network AIN services. SCP is connected to mated STPs and .

In SS7 signaling network there are unique links between the different network elements. Table 19 provides definitions for common SS7 links.

Mated STP pairs are connected together by C links. For example STPs and mated STPs and and mated STPs and are connected together by C links and respectively. SSPs and and SSPs and are connected together by F links and respectively.

Mated STPs and and mated STPs and which are at the same hierarchical level are connected by B links and . Mated STPs and and mated STPs and which are at different hierarchical levels are connected by D links and . Similarly mated STPs and and mated STPs and which are at different hierarchical levels are connected by D links and

SSPs and and mated STPs and are connected by A links and . SSPs and and mated STPs and are connected by A links and

SSPs and can also be connected to mated STPs and by E links not shown . Finally mated STPs and are connected to SCP by A links and

For a more elaborate description of SS7 network topology the reader is referred to Russell Travis 7 McGraw Hill New York N.Y. 10020 ISBN 0 07 054991 5 which is incorporated herein by reference in its entirety.

Signal transfer points STPs are tandem switches which route SS7 signaling messages long the packet switched SS7 signaling network . See the description of STPs with reference to in the soft switch site section and with reference to above.

Service switching points SSPs create the packets which carry SS7 signaling messages through the SS7 signaling network . See the description of SSPs with reference to above.

Services control points SCPs can provide database features and advanced network features in the SS7 signaling network . See the description of SCPs with reference to in the soft switch site section and with reference to above.

The top elliptical portion of the spool shaped component illustrates an embodiment of provisioning component including operational support services OSS order entry O E component alternate order entry component and data distributors and . In an example embodiment data distributors and comprise application programs.

In a preferred embodiment data distributors and include ORACLE 8.0 relational databases from Oracle Corporation of Redwood Shores Calif. Tuxedo clients and a BEA M3 OBJECT MANAGEMENT SYSTEM CORBA compliant interface available from BEA Systems Inc. of San Francisco Calif. with offices in Golden Colo. BEA M3 is based on the CORBA distributed objects standard. BEA M3 is a combination of BEA OBJECTBROKER CORBA ORB including management monitoring and transactional features underlying. BEA TUXEDO and an object oriented transaction and state management system messaging and legacy access connectivity. BEA M3 is scalable high performance designed for high availability and reliability supports transactions includes CORBA IIOP ORB security MIB based management supports fault management dynamic load balancing gateways and adapters client support multi platform porting data integrity management reporting and TUXEDO Services.

In another embodiment data distributors and include an application program by the name of automated service activation process ASAP available from Architel Systems Corporation of Toronto Ontario.

Customer service request calls can be placed to a customer service office. Customer service operators can perform order entry of customer service requests via OSS order entry O E system. In the event of the unavailability of OSS O E customer service requests may be entered via alternate O E . Customer service requests are inputted into data distributors and for distribution and replication to configuration servers and which contain customer profile database entries. In addition provisioning requests can be performed. Replication facilities in data distributors and enable maintaining synchronization between the distributed network elements of telecommunications network .

Referring to data distributors and receive service requests from upstream provisioning components such as e.g. OSS systems. Data distributors and then translate the service requests and decompose the requests into updates to network component databases. Data distributors and then distribute the updates to voice network components in soft switch sites and gateway sites. depicts examples of both the upstream and downstream network components interfacing to data distributors and

Data distributor has a plurality of functions. Data distributor receives provisioning requests from upstream OSS systems distributes provisioning data to appropriate network elements and maintains data synchronization consistency and integrity across data centers i.e. soft switch sites .

A more detailed architectural representation of one embodiment of data distributor is provided in . Data distributor accepts various requests from multiple upstream OSS systems and APDE .

Services request processes SRPs manage the upstream interface between data distributor and OSS systems . SRPs are developed to support communication between individual OSS systems APDE and data distributor .

A common service description layer acts as an encapsulation layer for upstream applications. Common service description layer translates service requests from upstream OSS systems and APDE to a common format. Common service description layer buffers the distribution logic from any specific formats or representations of OSS and APDE .

Distribution layer includes the actual distribution application logic resident within data distributor . Distribution layer manages incoming requests performs database replications maintains logical work units manages application revisions performs roll backs when required maintains synchronization handles incoming priority schemes and priority queues and other data distribution functions. Distribution layer includes access to multiple redundant high availability database disks which can include a database of record.

Updates are distributed downstream through a network element description layer . Network element description layer is an encapsulation layer that insulates data distributor from the individual data formats required by specific network element types. A network element processor NEP performs a role analogous to SRP but instead for downstream elements rather than upstream elements. NEPs manage the physical interface between data distributor and heterogeneous network elements i.e. the down stream voice network elements to which data distributor distributes updates. Heterogeneous network elements include SCPs and configuration servers and route servers and TGs and AGs and and SS7 GWs and . Each NEP handles a particular type of heterogeneous network elements e.g. route servers.

In addition to upstream feeds to OSS systems and downstream feeds to heterogeneous network elements data distributor allows updates directly to distribution layer via APDE . APDE enables update of distribution layer and allows updates to the network in the unlikely event that an emergency update is required when interfacing OSS systems upstream application are out of service or down for maintenance activity. APDE the alternate provisioning order entry system can comprise a small local area network including several PCs and connectivity peripherals. APDE provides a backup for OSSs .

In a preferred example embodiment of data distributor data distributor is an application program BEA M3 available from BEA Systems Inc. of San Francisco Calif. In another example embodiment data distributor could be another application program capable of distributing replication rollback of software such as for example AUTOMATED SERVICE ACTIVATION PROCESS ASAP available from Architel of Toronto Canada. Example upstream operational support services OSS components include application programs which perform multiple functions. illustrates some example OSS applications including provisioning application customer profiles order entry application route administration application service activation triggers network administration application network inventory application alternate provisioning data entry application APDE and trouble ticketing application not shown . Browsing tools can also be used such as for example a browsing or query application programs.

DOR includes a plurality of relational database tables including each EO NPA NXX LATA and state. Each EO can home to 150 000 NPA NXXs. Multiple inputs must be replicated into DOR . For example Lockheed Martin Local Exchange and Routing Guide LERG includes twelve 12 tables maintained by the industry including flat files which are sent to a carrier each month. demonstrates an exemplary monthly reference data update process . Monthly a LERG compact disk CD is received by the carrier including changes to all of the 12 tables. Process includes merging an image snapshot of DOR with the LERG CD and storing the results in a temporary routing database shown to create a discrepancy report. This process can be used to yield a subset of the NPA NXXs which have changed which can then be audited and used to update the production DOR if found to be necessary. Once an updated version of the database is prepared the database update can be sent to data distributor for distribution to all the relevant network elements.

Operationally when a provisioning request comes in from OSS the request enters a queue. Priority queuing is enabled by BEA TUXEDO. Tuxedo creates a plurality of queues in order to protect database integrity e.g. a high medium and low priority queue. An example of the use of queues might be to place a higher priority on customer updates that to LERG updates which are less time sensitive. Requests can be categorized in queues based on dates such as for example the effective date of the request the effective deactivation date. Once categorized by date the updates can be stored with a timestamp placed on them and can then be placed in a TUXEDO queue.

TUXEDO permits the use of down word transaction in its multi level queuing architecture. This permits pulling back transactions also known as rolling back a replication update so updates will occur to all of or none of the databases. In some instances one network element can be removed from the network but this is done rarely. For an example in the event of RCDB crashing the NOC can remove the crashing RCDB from the network configuration and thus it might not be capable of being updated. However for normal situations of the network updates are either performed on all elements or no updates are performed.

Data distributor receives service requests from upstream OSS systems and . OSS service requests appear in the form of provisioning updates and administrative reference updates.

Provisioning updates include high level attributes required to provision a customer s telecommunications service. Example high level attributes required for provisioning include for example customer automatic number identification ANI and trunk profiles class of service restrictions COSR and project account codes PAC profiles AG and TG assignments and toll free number to SCP translation assignments.

Administrative reference updates include high level attributes required to support call processing. Example high level attributes required to perform administrative updates include for example 3 6 10 digit translation tables international translation tables and blocked country codes.

Alternate provisioning data entry APDE replicates OSS functionality supported at the interface with data distributor . APDE can provide an alternative mechanism to provide provisioning and reference data to data distributor in the event that an OSS is unavailable.

Referring to data distributor passes provisioning and configuration information from upstream OSS systems primarily the provisioning system to configuration servers and . A plurality of tables are distributed from data distributor to each configuration server. Exemplary tables distributed include for example toll free numbers to SCP type tables SCP type to SCP tables carrier identification code CIC profile tables ANI profile summary tables ANI profile tables account code profile tables NPA NXX tables customer profile tables customer location profile tables equipment service profile tables trunk group service profile summary tables trunk group service tables high risk country tables and selected international destinations tables.

Data distributor passes administrative and reference information from upstream OSS systems to route server . A plurality of tables are distributed from data distributor to route servers and . Exemplary tables distributed include country code routing tables NPA routing tables NPA NXX routing tables ten digit routing tables route group tables circuit group tables and circuit group status tables.

Data distributor passes administrative configuration information to SS7 gateways and . The administrative configuration information sent can be used in the routing of SS7 signaling messages throughout signaling network .

Data distributor uses a separate physical interface for all SNMP messages and additional functions that can be defined. Additional functions that can be defined include for example provisioning and passing special alarm and performance parameters to data distributor from the network operation center NOC .

The spindle portion of the spool shaped component includes western soft switch site . Western soft switch site includes configuration servers and route servers and soft switches and and network event collection points i.e. RNECPs and . also includes central soft switch site including configuration servers and route servers and soft switches and and RNECPs and .

As depicted in network call events are collected at regional network event collection points via RNECPs and at the regional soft switch sites and which are like FIFO buffers. A call record can be created by the ingress soft switch. The ingress soft switch can generate a unique identifier UID for the call based for example on the time of origination of the call. Ingress related call event blocks can be generated throughout the call and are forwarded on to the RNECPs for inclusion in a call event record identified by the MD. The call event records can be sent from the RNECPs to master network event data base NEDB and for storage in database disks and for further processing using application programs such as for example fraud DB client browser statistics DB client and mediation DB client . In one embodiment a version of the call record including all call event blocks as of that time can be forwarded from the RNECPs to the NEDB on a periodic basis to permit real time mid call call event statistics to be analyzed. The call records can be indexed by the UID associated with the call. In one embodiment a copy of a call event record for a call including ingress call event blocks remains in the RNECP until completion of the phone call. In completing a phone call the ingress soft switch and egress soft switch can communicate using inter soft switch communication identifying the call by means of the UID. A load balancing scheme can be used to balance storage and capacity requirements of the RNECPs. For example in one embodiment calls can be assigned based on origination time i.e. a UID can be assigned to a specific RNECP based e.g. on time of origination of the call for buffered storage. The egress soft switch can similarly generate and forward call event blocks to the same or another RNECP for inclusion in the call event record. In one embodiment all the call event blocks for the call record for a given call are sent to one RNECP which maintains a copy throughout the call i.e. even if interim copies are transmitted for storage . In one embodiment the call event record is removed from the RNECP upon completion of the call to free up space for additional calls.

The bottom elliptical portion of spool shaped component illustrates an embodiment of network event component including master NEDBs and having database disks and . MNEDBs and can be in communication with a plurality of applications which process network call event blocks. For example a fraud DB client a browser a statistics DB client and a mediation DB client can process call event blocks EBs . MNEDBs and can be in set up in a primary and secondary mode.

The master network event database MNEDB is a centralized server which acts as a repository for storing call event records. MNEDB collects data from each of RNECPs which transmit information real time to MNEDB . MNEDB can also be implemented in a primary and secondary server strategy wherein RNECPs are connected to a primary and a secondary MNEDB for high availability redundancy. MNEDB can store call event blocks EBs received from RNECPs organized based on a unique call event identifier as the primary key and a directional flag element as the secondary key. MNEDB can serve as the database of record for downstream systems to be the database of record. Downstream systems include for example an accounting billing system a network management system a cost analysis system a call performance statistics system a carrier access billing system CABS fraud analysis system margin analysis system and others. MNEDB in a preferred embodiment has enough disk space to store up to 60 days of call event records locally.

MNEDBs can create and feed real time call event data to downstream systems. Real time call event data provides significant advantages over call event data available in conventional circuit switched networks. Conventional circuit switched networks can only provide call records for completed calls to downstream systems. The advantages of real time call event data include for example fraud identification and prevention and enablement of real time customized customer reporting and billing e.g. billing based on packets sent .

MNEDBs collect recorded call event blocks EBs from RNECPs . MNEDB correlates the EBs and forwards the data to various downstream systems.

MNEDBs and are in communication via multiple redundant connections with a plurality of downstream application systems. Downstream application systems include for example browser system fraud DB client system carrier access billing system CABS DB client statistics DB client and mediation DB client .

MNEDBs and provide recorded call event record data to fraud database client in real time. Real time call event data allows fraud DB client to detect fraudulent activities at the time of their occurrence rather than after the fact. Traditional circuit switched networks can only identify fraud after completion of a call since event records are cut at that time. Real time fraud detection permits operations personnel to take immediate action against fraudulent perpetrators. MNEDBs and provide recorded call event data to CABS DB client . CABS DB client uses the recorded call event data to bill other LECs and IXCs for their usage of telecommunications network using reciprocal billing.

MNEDBs and provide recorded call data to statistics DB client . Statistics DB client uses the recorded call event data to assist in traffic engineering and capacity forecasting.

MNEDBs and can provide recorded call event data to mediation DB client in one embodiment. Mediation DB client normalizes the recorded call data it receives from MNEDBs and and provides a data feed to a billing system at approximately real time.

MNEDBs and use a separate physical interface for all SNMP messages and additional functions that can be defined to communicate with network management component . Additional functions can include for example provisioning updating and passing special alarm and performance parameters to MNEDBs and from the network operation center NOC of network management component .

Definitions of the Event Blocks EBs that can be recorded during call processing are detailed in this section.

Table 20 below provides a definition of event block EB 0001. EB 0001 defines a Domestic Toll TG origination which can be the logical data set generated for all Domestic Long Distance calls originating via a Trunking Gateway i.e. from facilities of the PSTN. Typically these calls can be PIC calls originating over featuring group D FGD facilities.

Table 21 below provides a definition of event block EB 0002. EB 0002 defines Domestic Toll TG termination which can be the logical data set generated for all Domestic Long Distance calls terminating via a Trunking Gateway to the PSTN.

Table 22 below provides a definition of event block BB 0003. EB 0003 defines Domestic Toll AG origination which can be the logical data set generated for all Domestic Long Distance calls originating via an Access Gateway i.e. entering via a DAL or ISDN PRI line.

Table 23 below provides a definition of event block EB 0004. EB 0004 defines Domestic Toll AG termination which can be the logical data set generated for all Domestic Long Distance calls terminating via an Access Gateway to a DAL or PRI

Table 24 below provides a definition of event block EB 0005. EB 0005 defines Local TG origination which can be the logical data set generated for all local calls originating via a Trunking Gateway from a facility on the PSTN.

Table 25 below provides a definition of event block EB 0006. EB 0006 defines Local TG termination which can be the logical data set generated for all local calls terminating via a Trunking Gateway to facilities of the PSTN.

Table 26 below provides a definition of event block EB 0007. EB 0007 defines Local AG origination which can be the logical data set generated for all local calls originating via an Access Gateway.

Table 27 below provides a definition of event block EB 0008. EB 0008 defines Local AG termination which can be the logical data set generated for all local calls terminating via an Access Gateway.

Table 28 below provides a definition of event block EB 0009. EB 0009 defines 8XX Toll Free TG origination which can be the logical data set generated for Toll Free 8XX calls originating via a Trunking Gateway from facilities of the PSTN.

Table 29 below provides a definition of event block EB 0010 EB 0010 defines 8XX Toll Free TG termination which can be the logical data set generated for Toll Free 8XX s calls terminating via a Trunking Gateway to the facilities of the PSTN.

Table 30 below provides a definition of event block EB 0011. EB 0011 defines 8XX Toll Free AG origination which can be the logical data set generated for Toll Free 8XX calls originating via an Access Gateway.

Table 31 below provides a definition of event block EB 0012. EB 0012 defines DOC Toll Free AG termination which can be the logical data set generated for Toll Free 8XX s calls terminating via an Access Gateway.

Table 32 below provides a definition of event block EB 0013. EB 0013 defines Domestic Operator Services TG origination which can be the logical data set generated for all Domestic Operator Assisted calls originating via a TG. The actual billing information which can include the services utilized on the operator services platform OSP 3rd party billing collect etc. can be derived from the OSP.

Table 33 below provides a definition of event block EB 0014. EB 0014 defines Domestic Operator Services AG origination which can be the logical data set generated for all Domestic Operator Assisted calls originating via an AG. The actual billing information which can include the services utilized on the OSP can be derived from the OSP.

Table 34 below provides a definition of event block EB 0015. EB 0015 defines Domestic Operator Services OSP termination which can be the logical data set generated for all Domestic Operator Assisted calls terminating to the OSP. The actual billing information which can include the services utilized on the OSP can be derived from the OSP.

Table 35 below provides a definition of event block EB 0016. EB 0016 defines International Operator Services TG origination which can be the logical data set generated for all International Operator Assisted calls originated via a TG. The actual billing information which can include the services utilized on the OSP can be derived from the OSP.

Table 36 below provides a definition of event block EB 0017. EB 0017 defines International Operator Services AG origination which can be the logical data set generated for all International Operator Assisted calls originated via an AG. The actual billing information which will include the services utilized on the OSP can be derived from the OSP.

Table 37 below provides a definition of event block EB 0018. EB 0018 defines International Operator Services OSP termination which can be the logical data set generated for all International Operator Assisted calls terminating to the OSP. The actual billing information which will include the services utilized on the OSP can be derived from the OSP.

Table 38 below provides a definition of event block EB 0019. EB 0019 defines Directory Assistance 555 1212 TG origination which can be the logical data set generated for 555 1212 calls originating via a TG from the PSTN.

Table 39 below provides a definition of event block EB 0020. EB 0020 defines Directory Assistance 555 1212 AG origination which can be the logical data set generated for 555 1212 calls originating via an AG on a DAL.

Table 40 below provides a definition of event block EB 0021. EB 0021 defines Directory Assistance 555 1212 Directory Assistance Services Platform DASP termination which can be the logical data set generated for 555 1212 calls terminating to the DASP.

Table 41 below provides a definition of event block EB 0022. EB 0022 defines OSP DASP Extended Calls Domestic which can be the logical data set generated for all Domestic Operator and Directory Assisted calls that are extended back to telecommunications network for termination.

Table 42 below provides a definition of event block EB 0023. EB 0023 defines OSP DASP Extended Calls International which can be the logical data set generated for all International Operator and Directory Assisted calls that are extended back to the telecommunications network for termination.

Table 43 below provides a definition of event block EB 0024. EB 0024 defines International Toll TG Origination which can be the logical data set generated for all International Long Distance calls originating via a Trunking Gateway from facilities of the PSTN. Typically these calls can be PIC calls originating over FGD facilities.

Table 44 below provides a definition of event block EB 0025. EB 0025 defines International Toll AG Origination which can be the logical data set generated for all International Long Distance calls originating via an Access Gateway.

Table 45 below provides a definition of event block EB 0026. EB 0026 defines International Toll TG Termination which can be the logical data set generated for all International Long Distance calls terminating via a Trunking Gateway to facilities of the PSTN.

Table 46 below provides a definition of event block EB 0027. EB 0027 defines International Toll AG Termination which can be the logical data set generated for all International Long Distance calls terminating via an Access Gateway to a DPL or PRI.

Table 47 below provides a definition of event block EB 0040. EB 0040 defines IP Origination which can be the logical data set generated for ALL IP originations.

Table 48 below provides a definition of event block EB 0041. EB 0041 defines IP Termination which can be the logical data set generated for ALL IP terminations.

Table 49 below provides a definition of event block EB 0050. EB 0050 defines a Final Event Block which can be used as the FINAL Event Block for ALL calls events. It signifies the closure of a call event.

Table 50 below provides a definition of event block EB 0051. EB 0051 defines Answer Indication which can be used as to indicate whether or not a call session was answered or unanswered. If the call was unanswered the Answer Indicator element will indicate that the call was not answered and the Answer Time element will contain the time that the originating party went on hook.

Table 51 below provides a definition of event block EB 0052. EB 0052 defines Ingress Trunking Disconnect Information which can contain Ingress Trunking Disconnect information. The release date and time of the ingress circuit used in the call can be recorded. This EB can be extremely important to downstream systems i.e. cost analysis CABS analysis that may need to audit the bills coming from LECs CLECs Carriers.

Table 52 below provides a definition of event block EB 0053. EB 0053 defines Egress Trunking Disconnect Information which can contain Egress Trunking Disconnect information. The release date and time of the egress circuit used in the call can be recorded. This EB can be extremely important to downstream systems i.e. cost analysis CABS analysis that can need to audit the bills coming from LECs CLECs Carriers.

Table 53 below provides a definition of event block EB 0054. EB 0054 defines Basic 8XX Toll Free SCP Transaction Information which can be used for all basic toll free 8XX SCP transactions.

Table 54 below provides a definition of event block EB 0055. EB 0055 defines Calling Party Ported Information which can be used to record information in regards to a Calling Party Number that has been ported.

Table 55 below provides a definition of event block EB 0056 EB 0056 defines Called Party Ported Information which can be used to record information in regards to a Called Party Number that has been ported.

Table 56 below provides a definition of event block EB 0057. EB 0057 defines Egress Routing Information TG termination which can be used to record the egress routing information i.e. terminating via the PSTN .

Table 57 below provides a definition of event block EB 0058. EB 0058 defines Routing Congestion Information which can be used to record routes trunks that were unavailable e.g. due to congestion failure etc. during the route selection process in soft switch . EB 0057 for TG termination and EB 0060 for AG termination can be used to record the ACTUAL route trunk used to terminate the call. This information can be extremely valuable to for example traffic engineering network management cost analysis.

Table 58 below provides a definition of event block EB 0059 EB 0059 defines Account Code Information which can be used for all calls requiring account codes.

Table 59 below provides a definition of event block EB 0060. EB 0060 defines Egress Routing Information for AG termination which can be used to record the egress routing information i.e. terminating via an AG .

Table 60 below provides a definition of event block EB 0061. EB 0061 defines Long Duration Call Information which can be used to record a timestamp of long duration calls. Soft switch can generate this block when a call has been up for a duration that spans over two midnights. Subsequent LDCI EBs can be generated after each additional traverse of a single midnight. As an example if a call has been up from 11 52 pm on Monday through 4 17 pm on Thursday of the same week then TWO EB 0061s can be generated for the call. One can be generated at midnight on Tuesday the other can be generated at midnight on Wednesday.

Elements are the building blocks of Event Blocks EBs . Event Blocks are logical groupings of elements. Each element can contain information that is collected during call event processing whether from for example signaling messages external databases SCPs and intelligent peripherals IPs Access GTGs customer attributes or derived by a soft switch. All of the elements contain information that is used by various downstream systems. Downstream systems include for example billing mediation traffic engineering carrier access billing statistical engines cost analysis engines and marketing tools.

Table 61 below provides a definition of element 0. Element 0 defines an Event Block Code element which contains a code that can be mapped correlated to a type of call event. The EB code can be used for parsing and data definition for downstream systems.

Table 62 below provides a definition of element 1. Element 1 defines an Unique Call Event Identifier UCEI which can be used to correlate all events EBs for a particular call session. The correlation can be done in the MNEDB.

Table 63 below provides a definition of element 2. Element 2 defines a Soft Switch ID element which contains the soft switch identification number. This can indicate which soft switch recorded the call event data.

Table 64 below provides a definition of element 3. Element 3 defines a Connect Date element which contains the date when the call was originated.

Table 65 below provides a definition of element 4. Element 4 defines a Connect Time element which contains the time when the soft switch received an IAM.

Table 66 below provides a definition of element 5. Element 5 defines an Answer Indicator element which states whether or not a call session was answered unanswered.

Table 67 below provides a definition of element 6. Element 6 defines a Calling Party Category element which contains whether a call was originated from for example a Hotel a Prison a Cell Phone a pay phone a PVIPS and an inward wide area telephone service INWATS based on the Calling Party Category received in the Initial Address Message IAM derived from a soft switch or received from a database external from the soft switch.

Table 68 below provides a definition of element 7. Element 7 defines an Originating Number element which contains the NPA NXX XXXX DN that originated the call.

Table 69A below provides a definition of element 8. Element 8 defines an Overseas Indicator element which provides the digit length of an overseas call as well as whether or not an NPA was dialed or implied derived from the soft switch. This element is crucial to downstream systems i.e. billing mediation which need to differentiate between NPAs and CCs.

Table 69B below provides a definition of element 9. Element 9 defines a Terminating Numbering Plan Area Country Code NPA CC element which contains either the NPA of the dialed number for domestic calls or up to five characters of the overseas number dialed. Today country codes CCs can be up to 3 digits and the national significant number can be up to 14 digits since Dec. 31 1996 for a total of no more than 15 digits. If the call is domestic the first two characters can be 00 padding the next three characters can be the NPA and the last character can be the delimiter.

Table 69C below provides a definition of element 10. Element 10 defines a Terminating Number North American Numbering Plan NANP element which contains the NXX LINE of the dialed number for domestic calls. The terminating number element should be populated for ALL calls that require a terminating number for billing.

Table 70 below provides a definition of element 11. Element 11 defines an Elapsed Time element which contains the elapsed time duration of a completed call session. The time can be GMT.

Table 71 below provides a definition of element 12. Element 12 defines a Carrier Identification Code element which contains the toll carrier s identification code. This can be an extremely useful element for downstream systems i.e. billing that need to parse records for wholesale customers 

Table 72 below provides a definition of element 13. Element 13 defines an Ingress Carrier Connect Time element which contains the time that the ingress trunk circuit was seized for a call that is when an ACM was sent towards the PSTN. This element can be important to downstream systems i.e. cost analysis CABS analysis that may need to audit the bills coming from LECs CLECs Carriers.

Table 73 below provides a definition of element 14. Element 14 defines an Ingress Carrier Elapsed Time element which contains the elapsed time duration that the ingress trunk circuit was in use from seizure to release for both answered and unanswered calls sessions. This element can be important to downstream systems i.e. cost analysis CABS analysis that may need to audit the bills coming from LECs CLECs Carriers.

Table 74 below provides a definition of element 15. Element 15 defines an Ingress Trunk Group Number element which contains the Trunk Number on the originating ingress side of a call. The information can be derived from either TG or AG or from a correlation table using Element 16 Ingress Circuit Identification Code Element 17 Ingress Originating Point Code and Element 18 Ingress Destination Point Code to correlate to a specific trunk group. This element can be important to downstream systems i.e. cost analysis CABS analysis that may need to audit the bills coming from LECs CLECs Carriers. This can also assist traffic engineers in trunk sizing.

Table 75 below provides a definition of element 16. Element 16 defines an Ingress Circuit Identification Code element which contains the circuit number id of the circuit used on the originating ingress side of a call. The information can be derived from either TG or AG or from the Circuit Identification Code CIC field in the IAM.

Table 76 below provides a definition of element 17. Element 17 defines an Ingress Originating Point Code IOPC element which contains the ingress OPC.

Table 77 below provides a definition of element 18. Element 18 defines an Ingress Destination Point IDC Code.

Table 78 below provides a definition of element 19. Element 19 defines an Egress Carrier Connect Time element which contains the time that the egress trunk circuit was seized for a call. The time can be derived from the Access or Trunking Gateways or from the Initial Address Message. This element can be important to downstream systems i.e. CABS that need this information to BILL other LECs CLECs Carriers.

Table 79 below provides a definition of element 20. Element 20 defines an Egress Carrier Elapsed Time element which contains the elapsed time duration that the egress trunk circuit was in use from seizure to release for both answered and unanswered calls sessions. This element can be important to downstream systems i.e. CABS that need this information to BILL other LECs CLECs Carriers.

Table 80 below provides a definition of element 21. Element 21 defines an Egress Trunk Group Number element which contains the Trunk Number on the terminating egress side of a call. The information can be derived from either TG or AG or from a correlation table using Element 22 Egress Circuit Identification Code Element 23 Egress Originating Point Code and Element 24 Egress Destination Point Code to correlate to a specific trunk group. This element can be important to downstream systems i.e. cost analysis CABS analysis that may need to audit the bills coming from LECs CLECs Carriers.

Table 81 below provides a definition of element 22. Element 22 defines an Egress Circuit Identification Code element which contains the circuit number id of the circuit used on the terminating egress side of a call. The information can be derived from either TG or AG or from the Circuit Identification Code CIC field in the IAM message.

Table 82 below provides a definition of element 23. Element 23 defines an Egress Originating Point EOP Code.

Table 83 below provides a definition of element 24. Element 24 defines an Egress Destination Point EDP Code.

Table 84 below provides a definition of element 25. Element 25 defines a Dialed NPA element which contains the 8XX code for a toll free call.

Table 85 below provides a definition of element 26. Element 26 defines a Dialed Number element which contains the NXX LINE of the dialed number for domestic toll free calls. The terminating number element has seven significant characters and a sign delimiter character.

Table 86 below provides a definition of element 27. Element 27 defines a Destination NPA CC element which contains the Numbering Plan Area NPA for domestic calls and the Country Code CC for international calls. This information is SCP derived for 8XX calls. The element is right justified and padded with 0s if necessary.

Table 87 below provides a definition of element 28. Element 28 defines a Destination Number element which contains the NXX LINE of the destination number for domestic toll free calls. This number is the routing number returned from a SCP query. The terminating number element has seven significant characters and a sign delimiter character. The terminating number element should be populated for ALL calls that require a terminating number for billing.

Table 88 below provides a definition of element 29. Element 29 defines an Alternate Billing Number field element which contains the billing number obtained from the optional billing number data received from SCP.

Table 89 below provides a definition of element 30. Element 30 defines a Jurisdiction Information element which contains the NPA NXX of the originating Switch. This information can be contained in the Initial Address Message.

Table 90 below provides a definition of element 31. Element 31 defines a Transaction Identification element which contains a unique identification number for each external request to a SCP an Intelligent Peripheral IP or some other database.

Table 91 below provides a definition of element 32. Element 32 defines a Transaction Start Time element which contains the time that the Soft Switch sent an external request to an SOP an Intelligent Peripheral IP or some other database.

Table 92 below provides a definition of element 33. Element 33 defines a Transaction End Time element which contains the time that the Soft Switch received a response from an external request to a SCP an Intelligent Peripheral IP or some other database.

Table 93 below provides a definition of element 34. Element 34 defines a Database Identification element which contains the SCP Intelligent Peripheral IP or some other database s identification number that a transaction was performed.

Table 94 below provides a definition of element 36. Element 36 defines an Ingress Access Gateway element which contains the AG identification number.

Table 95 below provides a definition of element 37. Element 37 defines an Egress Access Gateway element which contains the AG identification number.

Table 96 below provides a definition of element 38. Element 38 defines an Account Code element which contains the length of the account code as well as the actual account code digits that were entered.

Table 97 below provides a definition of element 39. Element 39 defines an End Time element which contains the time when the call completed. The time should be recorded after both parties originating and terminating go on hook.

Table 98 below provides a definition of element 40. Element 40 defines an End Date element which contains the date when the call was completed.

Table 99 below provides a definition of element 41. Element 41 defines an Answer Date element which contains the date when the call was answered.

Table 100 below provides a definition of element 42. Element 42 defines an Answer Time element which contains the time when the terminating station went off hook. The timer could start when the Soft Switch receives an answer message. If the call was unanswered the Answer Time will contain the time that the originating party went on hook.

Table 101 below provides a definition of element 43. Element 43 defines an Ingress Carrier Disconnect Time element which contains the time that the ingress trunk circuit was released for a call. The time will either be derived from the Access or Trunking Gateways or from the Release Message. This element can be important to downstream systems i.e. cost analysis CABS analysis that may need to audit the bills coming from LECs CLECs Carriers.

Table 102 below provides a definition of element 44. Element 44 defines an Ingress Carrier Disconnect Date Disconnect Date element which contains the date when the ingress trunk circuit was released for a call.

Table 103 below provides a definition of element 45. Element 45 defines an Egress Carrier Disconnect Time element which contains the time that the egress trunk circuit was released for a call. The time will either be derived from the Access or Trunking Gateways or from the Release Message. This element can be extremely important to downstream systems i.e. CABS that need this information to BILL other LECs CLECs Carriers.

Table 104 below provides a definition of element 46. Element 46 defines an Egress Carrier Disconnect Date element which contains the date when the egress trunk circuit was released for a call.

Table 105 below provides a definition of element 47. Element 47 defines an Announcement Identification element which contains the announcement number correlating to an announcement that was invoked during call processing.

Table 106 below provides a definition of element 48. Element 48 defines a Location Routing Number LRN element which contains the Location Routing Number. Depending on the EB being created EB 0055 or EB 0056 this field contains the LRN for the Calling Party Number if ported or the LRN for the Called Party Number if ported .

Table 107 below provides a definition of element 49. Element 49 defines a LRN Supporting Information element which contains the source system where the LRN was derived.

Table 108 below provides a definition of element 50. Element 50 defines a Soft Switch Version element which contains the current software version that is operating on the soft switch.

Table 109 below provides a definition of element 51. Element 51 defines a Carrier Selection Information element which contains the toll carrier selection method. This allows downstream systems such as end user billing and fraud to parse records based on carrier selection methods e.g. pre subscription dial around casual calling. 

Table 110 below provides a definition of element 52. Element 52 defines an Ingress Trunking Gateway element which contains the TG identification number.

Table 111 below provides a definition of element 53. Element 53 defines an Egress Trunking Gateway element which contains the TG identification number.

Table 112 below provides a definition of element 55. Element 55 defines an Egress Route Congestion Code element which contains the reason for congestion on a trunk.

Table 114 below provides a definition of element 56. Element 56 defines an Account Code Validation Flag element which contains a flag that specifies whether or not the account code validation was successful.

Table 115 below provides a definition of element 57. Element 57 defines a Routing Attempt Time element which contains the time that an unsuccessful routing attempt was made on a trunk. This information can be useful to downstream Network Management and Traffic Engineering systems.

Table 116 below provides a definition of element 58. Element 58 defines a Routing Attempt Date element which contains the date that an unsuccessful routing attempt was made on a trunk. This information can be useful to downstream Network Management and Traffic Engineering systems.

Table 117 below provides a definition of element 59. Element 59 defines an Audio Packets Sent element which contains the number of audio packets that were sent from an AG or TG during a session.

Table 118 below provides a definition of element 60. Element 60 defines an Audio Packets Received element which contains the number of audio packets that were received by an AG or TG during a session.

Table 119 below provides a definition of element 61. Element 61 defines an Audio Packets Lost element which contains the number of audio packets that were lost during a session.

Table 120 below provides a definition of element 62. Element 62 defines an Audio Bytes Transferred element which contains the total number of audio packets that were transferred sent from an AG or TG during a session.

Table 121 below provides a definition of element 63. Element 63 defines an Originating IP Address element which contains the Internet Protocol IP address of the originator.

Table 122 below provides a definition of element 64. Element 64 defines a Terminating IP Address element which contains the Internet Protocol IP address of the termination.

Table 123 below provides a definition of element 65. Element 65 defines an Ingress Security Gateway IP Address element which contains the Internet Protocol IP address of the security gateway on the ingress portion of a call session.

Table 124 below provides a definition of element 66. Element 66 defines an Egress Security Gateway IP Address element which contains the Internet Protocol IP address of the security gateway on the egress portion of a call session.

Table 125 below provides a definition of element 67. Element 67 defines an Ingress Firewall IP Address element which contains the Internet Protocol IP address of the security gateway on the ingress portion of a call session.

Table 126 below provides a definition of element 68. Element 68 defines an Egress Firewall IP Address element which contains the Internet Protocol IP address of the security gateway on the egress portion of a call session.

Table 127 below provides a definition of element 69. Element 69 defines an Operator Trunk Group Number element which contains the trunk group number for the trunk selected to the Operator Services Platform OSP .

Table 128 below provides a definition of element 70. Element 70 defines an Operator Circuit Identification Code CIC element which contains the circuit number id of the circuit used for an Operator service call.

Table 129 below provides a definition of element 71. Element 71 defines an Account Code Type element which contains a value associated with the type of account used in the call.

Table 130 below provides a definition of element 72. Element 72 defines an Ingress Carrier Connect Date element which contains the date when the ingress trunk circuit was seized.

Table 131 below provides a definition of element 73. Element 73 defines an Egress Carrier Connect Date element which contains the date when the egress trunk circuit was seized.

Table 132 below provides a definition of element 74. Element 74 defines a Terminating Number International element which contains the overseas number that was dialed for domestic calls. The terminating number element should be populated for ALL calls that require a terminating number for billing. This field can be right justified padded with 0s.

Table 133 below provides a definition of element 75. Element 75 defines a DA Trunk Group Number element which contains the trunk group number for the trunk selected to the directory assistance DA service provider.

Table 134 below provides a definition of element 76. Element 76 defines a DA Circuit Identification Code element which contains the circuit number id. of the circuit used for a DA service call.

Table 135 below provides a definition of element 77. Element 77 defines a Directional Flag element which contains a flag that specifies whether a call event block is an ingress or an egress generated block.

Table 136 below provides a definition of element 78. Element 78 defines a Trunk Group Type element which contains a type identification number which maps to a type use of a trunk. The element can be useful to downstream systems such as mediation billing fraud etc. This element can also be used in call processing.

Table 137 below provides a definition of element 79. Element 79 defines a Call Type Identification element which contains a call type identification number which maps to a type of a call. The element can be useful to downstream systems such as for example mediation billing fraud. This element can also be used in call processing. This element can be derived during LSA analysis.

Table 138 below provides a definition of element 80. Element 80 defines a Customer Identification element which contains a customer account number.

Table 139 below provides a definition of element 81. Element 81 defines a Customer Location Identification element which contains a customer location identification number.

Table 140 below provides a definition of element 82. Element 82 defines a Call Event Block Sequence Number element which contains a sequence number for each event block created by the soft switch for a particular call.

Table 141 below provides a definition of element 83. Element 83 defines a Long Duration Sequence Number element which contains a sequence number for each long duration call LDC event block created by the soft switch for a particular call.

Table 142 below provides a definition of element 84. Element 84 defines a Long Duration Event Time element which contains the time when the soft switch generated the LDC Event Block.

Table 143 below provides a definition of element 85. Element 85 defines a Long Duration Event Date element which contains the date when the soft switch generated the LDC Event Block.

Telecommunications network includes network management component which can use a simple network management protocol SNMP to trap alarm conditions within and receive network alerts from hardware and software elements of the network. illustrates in detail SNMP network management architecture . SNMP network management architecture is organized into a plurality of tiers and layers not shown .

Tier 1 addresses hardware specific events that are generated on each respective hardware and software system. Generally hardware vendors provide tier 1 functionality in the form of a management information base MIB .

Tier 2 is designed to capture operating system specific events and is also available as a commercially sold product in the form of an MIB from a software vendor.

In one embodiment of the invention tiers 1 and 2 are provided by a hardware vendor for example from Sun Microsystems of Palo Alto Calif. Tier 1 and 2 MIBs are designed to provision update and pass special event and performance parameters to a network operations center NOC pictured as NOC in .

Tier 3 can support alarm transmission from software applications and can be designed and implemented via a customized software solution from a third party vendor. Software applications can call a standardized alarm transport application programming interface API to signal events and alarms within the software code. The vendor supplied alarm API can redirect events to a local alarm manager application. There can be one instance of a local alarm manager application on each customized platform or computer in the network. The local alarm manager can log events to a disk based database. The local alarm manager can also log events to a disk based log file and can then forward the events from the database or log file to a specialized MIB component. The specialized MIB component can then divert this information to a regional SNMP agent at each geographical location i.e. at each soft switch site and or gateway site C D E D and E. Regional SNMP agents can then route all incoming network management events or alarms to master SNMP managers and at the NOC .

Gateway sites and include multiple gateway site components which can each have their SNMP agents. For example gateway site can include TGs and which have SNMP agents . Gateway site can also include AGs and having SNMP agents . Gateway sites can also include ESs and and routers and having their own SNMP agents. Gateway site can also have one or more SNMP servers and for gathering SNMP alerts events and alarms at gateway site from SNMP agents such as for example SNMP agents and . SNMP servers and can then forward network management events and alarms to NOC for centralized network management processing.

Simple network management protocol SNMP events generated by network elements can enable NOC to determine the health of the voice network components and the rest of telecommunications network . Tier 1 and tier 2 MIBs can be purchased as commercially off the shelf COTS components or are provided with computer hardware and operating systems. Events generated within the customized third tier can be prioritized according to multiple levels of severity. Prioritization can allow a programmer to determine the level of severity of each event generated and sent to NOC . Customized alarm managers resident in each computer system can serve as alarm logging components and transport mechanisms for transport to downstream SNMP agents. Personnel working at NOC can log into a computer system to analyze special alarm conditions and to focus on the cause of the SNMP alarms. Multiple alarm conditions can be registered at NOC . A local log file can store all events processed by a local alarm manager application. For example local alarm manager applications can reside in SNMP servers and at gateway site and at SNMP servers and of soft switch site . The local log files can serve as a trace mechanism to identify key network and system event conditions generated on the computer systems.

Assuming a fiber cut occurs or excessive latency or packet loss failure occurs in data network outage recovery scenario routes the call over backup call path of . Backup call path takes a call which originated from carrier facility through DACS to TG and connects the call back out through DACS to an off network carrier which connects the call traffic for termination at carrier facility . By using off network routing via off network carrier service level agreements SLA can be maintained providing for a higher percentage of network uptime and a higher level of audio quality.

Outage recovery scenario would cover any failure or degradation in a network device which falls after TG including IP media processes within TG in normal call path route assuming that TG can still be controlled so as to route the call out over DACS over backup call path to off network carrier .

Anticipating the possibility of a failure of a soft switch of soft switch site it is important that existing calls i.e. those placed through an associated gateway device e.g. TGs and of gateway sites and respectively not be impacted by the failure. In one embodiment of the invention it is possible that some calls that are in the process of being established might be lost such that a calling party might have to re dial to connect. In order to preserve calls set up and managed by failed soft switch back up soft switch has access to the states of the stable calls managed by failed soft switch . Once the back up soft switch initiates fail over it notifies the primary and secondary SS7 GWs and that the back up soft switches and are now the contact points for signaling messages that had previously been targeted for failed soft switch .

Western soft switch site thus is responsible for controlling access servers and not shown in gateway sites and

Central soft switch site is responsible for controlling access servers and not shown in gateway sites and

Eastern soft switch site is responsible for controlling access servers and not shown which are located in gateway sites and

The IPDC base protocol described below provides the basis for the LP device control family of protocols. The IPDC protocols include a protocol suite. The components of the IPDC protocol suite can be used individually or together to perform multiple functions. Functions which can be performed by the IPDC protocol suite include for example connection control media control and signaling transport for environments where the control logic is separated from the access server and . The IPDC protocol suite operates between the media gateway controller and the media gateway. The media gateway controller can be thought of as soft switch . The media gateway can be thought of as access servers and including for example TGs and AGs and and NASs and . The corresponding entities of media gateway controller and the media gateway are the call control and media control portions of the H.323 gateway.

IPDC acts to fulfill a need for protocols to control gateway devices which sit at the boundary between the circuit switched telephone network and the Internet and to terminate circuit switched trunks. Examples of such devices include NASs and and voice over IP gateways also known as access servers and including TGs and and AGs and . This need for a control protocol separate from call signaling arises when the service control logic needed to process calls lies partly or wholly outside the gateway devices. The protocols implement the interface between soft switch and access servers . IPDC views access servers and also known as media gateways as applications which may control one or more physical devices. In addition to its primary mandate IPDC can be used to control devices which do not meet the strict definition of a media gateway such as DACS and and ANSs and . IPDC builds on a base provided by DIAMETER. DIAMETER has a number of advantages as a starting point including for example built in provision for control security facilities for starting up the control relation and ready extensibility both in modular increments and at the individual command and attribute level. DIAMETER is specifically written for authentication authorization and accounting applications. Calhoun Rubins DIAMETER based protocol July 1998. The DIAMETER based protocol specification was written by Pat Calhoun of Sun Microsystems Inc. and Alan C. Rubins of Ascend Communications.

The IPDC protocol includes a message header followed by attribute value pairs AVPs an IPDC command is a specialized data object which indicates the purpose and structure of the message which contains the IPDC command. The command name can be used to denote the message format.

A DIAMETER device can be a client or server system that supports the DIAMETER based protocol. Alternatively a DIAMETER device can support extensions in addition to the DIAMETER based protocol.

An IPDC entity can be any object logical or physical which is subject to control through IPDC or whose status IPDC must report. Every IPDC entity has a type. Types of IPDC entities include for example a media gateway type a physical gateway type a station type an equipment holder type a transport termination type an access termination type a trunk termination type a signaling termination type a device type a modem type a conference port type a fax port type a stream source type a stream recorder type an RTP port type an ATM spec type an H323 spec type and a SIP spec type.

An IPDC protocol endpoint can be used to refer to either of the two parties to an IPDC control session i.e. the media gateway controller e.g. soft switch or the media gateway e.g. access servers and . To the extent that IPDC can be viewed as providing extensions to DIAMETER an IPDC protocol endpoint can also be a DIAMETER device.

A transaction can be a sequence of messages pre defined as part of the definition of IPDC commands which constitute that sequence. Every message in the sequence can carry the same identifier value in the header and the same transaction originator value identifying the originator of the transaction.

DIAMETER packets or IPDC messages can be transmitted over UDP or TCP. Each DIAMETER service extensions draft can specify the transport layer. For UDP when a reply is generated the source and destination ports are reversed. IPDC requires a reliable order preserving transport protocol with minimal latency so that IPDC control can be responsive to the demands of call processing. UDP combined with a protocol description satisfies these requirements and is therefore the default transport protocol for IPDC. It would apparent to those skilled in the art that network operators can choose to implement transmission control program TCP instead for greater security or for other reasons.

The IPDC base protocol is a publically available document published on the Internet. It is important to note that the IPDC based protocol is a document in a so called Internet draft as of the time of the writing of this publication. Internet drafts are working documents of the internet engineering task force IETF its areas and its working groups. Other groups can also distribute working documents as Internet drafts. Internet drafts can be updated replaced or obsoleted by other documents at any time.

Command AVPs include a plurality of DIAMETER based commands and additional IPDC commands. For example DIAMETER base commands include for example command unrecognized IND device reboot IND device watchdog IND device feature query device feature reply device config REQ and device config answer. Additional IPDC commands include for example command ACK and message reject.

In addition to command AVPs a plurality of other AVPs exist including for example DIAMETER base AVPs and additional IPDC AVPs. DIAMETER base AVPs include host IP address host name version number extension ID integrity check vector digital signature initialization vector time stamp session ID X509 certificate X509 certificate URL vendor name firmware revision result code error code unknown command code reboot type reboot timer message timer message in progress timer message retry count message forward count and receive window. Additional IPDC AVPs include for example transaction originator and failed AVP code.

Protection of data integrity is enabled using the integrity check vector digital signatures and mixed data integrity AVPs.

AVP data encryption is supported including for example shared secrets and public keys. Public key cryptography support includes for example X509 certificate X509 certificate URL and static public key configuration.

The IPDC is a control protocol that facilitates the delivery of voice and data services requiring interconnection with an IP network. The IPDC protocol permits a soft switch control server to control a media gateway or access server. IPDC includes signaling transport connection control media control and device management functionality. These control functions include creation modification and deletion of connections detection and generation of media and bearer channel events detection of resource availability state changes in media gateways and signal transport.

Alternatively other protocols can be used to provide this control. For example the network access server messaging interface NMI protocol or the media gateway control protocol MGCP . The MGCP protocol from the Internet engineering task force IETF supports a subset of the functionality of the IPDC protocol plus the simple gateway control protocol SGCP from Bellcore and CISCO. SGCP includes connection control and media control i.e. a subset of IPDC media control functionality.

IPDC protocol allows a call control server i.e. a soft switch to command a circuit network to packet network gateway a media gateway i.e. an access server provides the control mechanism to for setting up tearing down and managing voice and data calls. The term packet network gateway is intended to allow support for multiple network types including for example an IP network and an ATM network data network . In addition the IPDC protocol supports the management and configuration of the access server . The following types of messages are described in this document start up messages describing access server start up and shut down configuration messages describing access server soft switch and telco interface query and configuration maintenance messages describing status and test messages and call control messages describing call set up tear down and query for data TDM and packet switched calls.

The architecture in which IPDC operates incorporates existing protocols wherever possible to achieve a full interconnection of IP based networks with the global switched telephone network GSTN . The architecture accommodates any GSTN signaling style including for example SS7 signaling ISDN signaling and in band signaling. The architecture also accommodates an interface with H.323 voice over IP networks.

A modification to the H.323 architecture can allow H.323 networks to be seamlessly integrated with SS7 networks.

Until now H.323 protocols have been defined assuming that an H.323 to GSTN gateway uses an access signaling technique such as ISDN or in band access signaling for call set up signaling on the GSTN. The H.323 architecture did not readily accommodate the use of SS7 signaling for call set up via H.323 gateways creating a gap in the standards. Until now H.323 standards have distinguished between multi point processor MP functions and multi point controller MC functions only in the definition of multi point control units MCUs . Recent international telecommunications union ITU work on H.323 version III has considered extending the concept of MC MP separation to H.323 gateways as well as MCUs. Separation of the MC function from the H.323 gateway can allow SS7 to be properly interconnected with an H.323 network. By separating the MC function from the MP function a separate SS7 signaling gateway such as for example SS7 GW can be created to interconnect the SS7 network with the H.323 network. Such an SS7 gateway can implement the H.323 gateway MC function as a signaling interface shared among multiple H.323 gateway MP functions.

At least five functions must be performed in order to interface an H.323 network to a GSTN network. The functions include for example a packet network interface H.323 signal intelligence GSTN signaling intelligence a media processing function and a GSTN circuit interface.

In an H.323 gateway which interfaces with an in band signaled or ISDN signaled GSTN trunk all of these five functions could be performed with a H.323 gateway. However in a H.323 gateway which interfaces with a SS7 signaled trunk the functionality could be more optimally partitioned to allow for a group of SS7 links to be shared among multiple H.323 gateway MP functions. For example an H.323 gateway MC function could include for example a packet network interface H.323 signaling intelligence and GSTN SS7 signaling intelligence. In addition an H.323 gateway MP function could include a packet network interface a media processing function and a GSTN circuit interface. Thus the H.323 gateway functionality could be separated into the H.323 gateway MC function and the H.323 gateway MP function.

In another embodiment the MC function could be further partitioned. For example H.323 gateway MC function could include a packet network interface H.323 signaling intelligence and a packet network interface. An SS7 gateway could include additional MC functions such as for example a packet network interface and a GSTN SS7 signaling intelligence. The physical separation of the H.323 gateway MC function from the SS7 gateway provides several advantages including for example more than one SS7 gateway can be interfaced to one or more MC functions allowing highly reliable geographically redundant configurations service logic implemented at the H.323 gateway MC function or at an associated gatekeeper can be provisioned at a smaller number of more centralized sites reducing the amount of data replication needed for large scale service implementation across an H.323 network and SS7 gateway to H.323 gateway MC functional interface could be a model for other signaling gateways such as for example an ISDN NFAS gateway a channel associated C7 signaling gateway and a DPNSS gateway. In fact once service providers have implemented service logic at the H.323 gateway MC function for their SS7 signaled trunks the following anomalies become apparent for example service providers will likely want to exercise the same or similar service logic for their ISDN and in band signal trunks as well as their SS7 signaled trunks and service providers will want to incorporate media processing events into the service logic implemented at the H.323 gateway MC function or at an associated gatekeeper .

The IPDC protocol is intended to interface the MC function with the MP function in H.323 to GSTN gateways. Based upon events detected in the signaling stream the H.323 gateway MC function must be able to create delete and modify connections in the H.323 gateway MP function. Also the H.323 gateway MC function must be able to create or detect events in the media stream which only the H.323 gateway MP function has access to. A standardized protocol is needed to allow an H.323 gateway MC function to remotely control one or more H.323 gateway MP functions. Therefore IPDC was created to allow H.323 gateway MC function to remotely control one or more H.323 gateway MP functions. Specifically soft switch can remotely control one or more access servers .

The IPDC protocol uses the terminology of bay module line and channel. A bay is one unit or set of modules and interfaces within an access server . A stand alone access server or a multi shelf access server can constitute a single bay. A module is a sub unit that sits within a bay. The module is typically a slot card that implements one or more network line interfaces e.g. a dual span T1 card. A line is a sub unit that sits within a module. The line is typically a physical line interface that plugs into a line card e.g. a T1. A channel is a sub unit within a line. The channel is typically a channel within a channelized line interface e.g. one of the 24 channels in a channelized T1.

All numbers in the IPDC protocol should be in binary and coded in network byte order big endian or motorola format . The format for date time fields is a 4 bytes integer expressing the number of seconds elapsed since Jan. 1 1990 at 0 00.

The soft switches and e.g. primary secondary tertiary etc. are completely hot swappable. Switching to a backup soft switch does not require fall back in call processing states or other IPDC level operation on access server . Both soft switches and follow the operations of the other soft switch precisely.

The message exchange as defined in IPDC can be implemented over any IP base protocol. Suggested protocols include e.g. TCP and UDP.

Access server can include the following configuration items IP addresses and TCP or UDP ports of any number of soft switches to which access server should connect bay number 8 bytes in alpha numeric characters system type 9 bytes in alpha numeric characters and protocol version supported.

An IPDC packet can have the following components included in its format for example a protocol ID a packet length a data field tag a data field length data flags an optional vendor ID data and padding. For example a protocol ID may exist in a first byte. Packet length can be a 2 byte field appearing second a single byte reserved field can then occur followed by a 4 byte data field tag. Next a 2 byte data field length can be used followed by a single byte data flag and a single byte reserved field. Next a 4 byte optional vendor ID can exist. Next the data included in the body of the message can contain a variable number of 4 byte aligned tag length value combinations. Finally a 3 byte data and single byte padding field can be placed in the IPDC packet. For all IPDC messages the message type and transaction ID are required attribute value pairs.

The message code must be the first tag following the header. This tag is used in order to communicate the message type associated with the message. There must only be a single message code tag within a given message. The value of this tag for each message type may be found below.

The transaction ID is assigned by the originator of a transaction. The transaction ID must remain the same for all messages exchanged within a transaction. The transaction ID is a 12 byte value with the following tag length value format the first 4 bytes can contain a data field tag the next two bytes can include the data field length the next byte can contain flags the next byte is reserved the next 4 bytes can contain an originator ID the following 4 bytes can contain originator ID and in the last 4 bytes there can exist in the first bit the originator and in the remaining bytes the transaction correlator 31 bits.

Table 144 below provides a listing of the names and corresponding codes for control messages transmitted between Soft Switch and Access Servers and . Also included are the source of each message and the description for each message. For example the NSUP message is transmitted from Access Server to Soft Switch informing Soft Switch that Access Server is coming up.

The following section provides a more detailed view of the control messages transmitted between Soft Switch and Access Server .

Table 145 below provides the Startup messages the parameter tags the parameter descriptions associated with these messages and the R O status.

Table 146 below provides the Protocol error messages the parameter tags the parameter descriptions associated with these messages and the R O status.

Table 147 below provides the System configuration messages the parameter tags the parameter descriptions associated with these messages the R O status and any notes associated with the message.

Table 148 below provides the Telephone Company Telco interface configuration messages the parameter tags the parameter descriptions associated with these messages the R O status and any notes associated with the message.

Table 149 below provides the Soft Switch configuration messages the parameter tags the parameter descriptions associated with these messages the R O status and any notes associated with the message.

Table 150A below provides the Maintenance Status messages the parameter tags the parameter descriptions associated with these messages the R O status and any notes associated with the message.

Table 151 below provides the Continuity test messages the parameter tags the parameter descriptions associated with these messages the R O status and any notes associated with the message.

Table 152 below provides the Keepalive test messages the parameter tags the parameter descriptions associated with these messages the R O status and any notes associated with the message.

Table 153 below provides the LAN test messages the parameter tags the parameter descriptions associated with these messages the R O status and any notes associated with the message.

Table 154 below provides the Tone function messages the parameter tags the parameter descriptions associated with these messages the R O status and any notes associated with the message.

Table 162 below provides a listing of the control message parameters and the control messages which use these message parameters. More specifically Table 162 provides the tags associated with the parameters the size in bytes of the parameters the type of the parameters e.g. ASCII the parameter descriptions the values and the control messages which use the parameters.

The following section provides a detailed view of the flow of control messages between Soft Switch and Access Server . Included are the source either Soft Switch or Access Server and relevant comments describing the message flow.

Table 163 below provides the Startup flow including the step the control message source either Soft Switch or Access Server and relevant comments.

Table 164 below provides the Module status notification flow including the step the control message source either Soft Switch or Access Server and relevant comments.

Table 165 below provides the Line status notification flow including the step the control message source either Soft Switch or Access Server and relevant comments.

Table 166 below provides the Blocking of channels flow including the step the control message source either Soft Switch or Access Server and relevant comments.

Table 167 below provides the Unblocking of channels flow including the step the control message source either Soft Switch or Access Server and relevant comments.

Tables 168A and 168B below provides the Keep alive test flow including the step the control message source either Soft Switch or Access Server and relevant comments. Table 168A shows the Access Server verifying that the Soft Switch is still operational. Table 168B shows the Soft Switch verifying that the Access Server is still operational.

Table 169 below provides the Reset request flow including the step the control message source either Soft Switch or Access Server and relevant comments.

The Data Call Services Scenarios that follow can be used to deliver internet and intranet access services through NASs and . The scenarios assume that access servers and provide modem termination for inbound calls.

Table 170 below provides an Inbound data call flow via SS7 signaling including the step the control message source Soft Switch SS7 signaling network or Access Server and relevant comments. The reader is directed to the text below further detailing a data call on NASs and described with reference to and . The reader is also directed to which depicts a flowchart state diagram of Access Servers and inbound call handling.

Table 171 below provides an Inbound data call flow via Access Serving signaling including the step the control message source either Soft Switch or Access Server and relevant comments. The incoming data call could arrive at AGs and from a customer facility via a DAL or ISDN PRI connection. The reader is directed to which depicts a flowchart state diagram of Access Servers and inbound call handling. The reader is also directed to which depicts an exemplary call path flow.

Table 172 below provides an Inbound data call flow via SS7 signaling with call back including the step the control message source Soft Switch SS7 signaling network or Access Server and relevant comments. The reader is also directed to which depicts an exemplary call path flow.

The call scenario in Table 172 includes a call flow where the intranet service provider does not want to accept direct inbound calls to the network. The intranet service provider accepts inbound calls only for authentication of calling party and then drops the line and dials back to calling party at the registered location of calling party .

Table 173 below provides an Inbound data call flow with loopback continuity testing including the step the control message source either Soft Switch or Access Server and relevant comments.

Table 174 below provides an Outbound data call flow via SS7 signaling including the step the control message source either Soft Switch SS7 signaling network or Access Server and relevant comments. The reader is also directed to which depicts an exemplary call path flow.

Table 175 below provides an Outbound data call flow via Access Server signaling including the step the control message source either Soft Switch or Access Server and relevant comments. The reader is also directed to which illustrates a flowchart depicting an Access Server outbound call handling initiated by Soft Switch state diagram. The reader is also directed to which depicts an exemplary call path flow.

Table 176 below provides an Outbound data call flow initiated from the Access Server with continuity testing including the step the control message source either Soft Switch or Access Server and relevant comments. The reader is also directed to which illustrate a flowchart depicting an Access Server continuity test handling state diagram and to which illustrate a flowchart depicting an Access Server outbound call handling initiated by an Access Server state diagram.

The following call scenarios can be used to control a device that is used for TDM circuit switching. TDM circuit switching can be necessary in configurations where a single set of access trunks are used for calls that must terminate on different access server devices. Soft switch can make the determination of where to send the call based upon the information in the signaling message TDM switching can be used to route voice traffic to one device and data to another. TDM switching can also be used to connect different inbound calls to different access servers connected to different intranets. The reader is also directed to which depicts a flowchart of a stated diagram of Access Server TDM connection handling.

Table 177 below provides a basic interaction sequence for establishing a connection within a TDM switching device including the step the control message source either soft switch or Access Server and relevant comments. The sequence includes a RCST request from soft switch and an ACST response from access servers and .

Table 178 below illustrates the routing of calls to the appropriate Access Server using TDM connections including the step the control message source including soft switch TDM switching device e.g. DACs and SS7 signaling network and Data Access Server e.g. NASs and . In this call flow a data call can arrive via the SS7 signaling network . Soft switch must identify the call as a data call and make a TDM connection to connect the call to the appropriate data server. Soft switch can look at information in the IAM message such as the dialed number to determine the type of call and therefore the destination of the TDM connection. This call flow can be used to separate data and voice calls as well as separate data calls destined for different data networks. The reader is also directed to which depicts an exemplary call path flow.

The following message flows show how to connect calls that originate and terminate on a Switched Circuit Network SCN but pass through a data network .

 a Voice Over Packet Services Call Flow Inbound SS7 Signaling Outbound Access Server Signaling Soft Switch Managed RTP Ports 

Table 179 below provides an illustration of a Voice over packet call flow having Inbound SS7 signaling Outbound access server signaling Soft Switch managed RTP ports including the step the control message source i.e. the soft switch originating access server SS7 signaling network and terminating access server and relevant comments. The reader is also directed to depicting a flowchart illustrating an Access Server inbound call handling state diagram. The reader is also directed to which depicts an exemplary call path flow.

 b Voice Over Packet Call Flow Inbound Access Server Signaling Outbound Access Server Signaling Soft Switch Managed RTP Ports 

Table 180 below provides an illustration of a Voice over packet call services flow having Inbound access server signaling Outbound access server signaling Soft switch managed RTP ports including the step the control message source i.e. the soft switch originating access server and terminating access server and relevant comments. The reader is also directed to illustrating a flowchart depicting an Access Server inbound call handling state diagram. The reader is also directed to which depicts an exemplary call path flow.

 c Voice Over Packet Call Flow Inbound SS7 Signaling Outbound SS7 Signaling IP Network with Access Server Managed RTP Ports 

Table 181 below provides an illustration of a Voice over packet call flow having inbound SS7 signaling outbound SS7 signaling IP network with access server managed RTP ports including the step the control message source i.e. soft switch originating access server SS7 signaling network and terminating access server and relevant comments. The reader is also directed to depicting a flowchart illustrating an Access Server inbound call handling state diagram. The reader is also directed to which depicts an exemplary call path flow.

Table 183 below provides an unattended call transfer call flow including the step the control message source i.e. soft switch originating access server operator services access server e.g. operator services platform SS7 signaling network and terminating access server and relevant comments.

The call flow in Table 183 shows the IPDC protocol can be used to transfer a call to another destination. The example call flow assumes that the person performing the transfer is at an operator services workstation that has the ability to signal soft switch to perform the transfer. The operator services platform interaction is not shown since this would be covered in another protocol but the resulting messages to access servers and are shown. The operator services platform is connected with dedicated access trunks such as for example a DAL or ISDN PRI or dedicated SS7 signaled trunk.

Note that throughout this call flow the same transaction ID can be used to indicate that the new RCCP commands to ports that are already in use indicates a re connection or a call transfer. In this example call flow the originating caller i.e. calling party is serviced by an SS7 signaled trunk the operator services platform is on a dedicated trunk and the termination is accessed via an access server and signaled trunk. The reader is also directed to illustrating a flowchart depicting an access server inbound call handling state diagram. The reader is also directed to depicting an operator services platform .

Table 184 below provides an illustration of an Attended Call Transfer call flow including a step a control message source i.e. soft switch originating access server operator services access server SS7 signaling network and terminating access server and relevant comments.

The call flow of Table 184 is similar to the unattended call flow of Table 183 except that rather than blindly transferring the call the original caller is placed on hold and the operator services workstations connected to the termination. Once the operator services workstation announces the caller the two parties are connected. As with Table 183 the message interaction with the operator services platform is not shown.

Note that throughout this call flow the same transaction ID is used to indicate that the new RCCP commands to ports that are already in use indicates a re connection or a call transfer.

In the example call flow of Table 184 the originating caller is serviced by an SS7 signaled trunk the operator services platform is on a dedicated trunk and the termination is accessed via an access server signaled trunk.

Table 185 below provides an illustration of a Call termination with a message announcement including a step a control message source i.e. soft switch originating access server SS7 signaling network and one of announcement servers and and relevant comments

The call flow of Table 185 shows the use of announcement servers ANSs and to play call termination announcements as final treatment to a call.

The call flow assumes announcement server ANSs and have pre recorded announcements. Soft switch signals ANSs and with the appropriate announcement ID using the fields in the RCCP command. One of ANSs and plays the announcement and notifies soft switch that it has completed its task.

In the example call flow the originating caller is connected via SS7 signaled trunks and one of ANSs and is connected to soft switch via IP data network .

Table 186 below provides an illustration of a wiretap call for listening to a call including the step the control message source i.e. soft switch originating access server wiretap server a specialized access server SS7 signaling network and a terminating access server and relevant comments.

The example call flow of Table 186 shows the use of a wiretap server to listen to a call. The wiretap server allows the originator and the intended terminator to participate in a normal call with a third party listening to the conversation but not transmitting the third party s voice. The wiretap server can be an IPDC specialized access server similar to a conference bridge but that does not permit transmission of voice from a connected wiretap workstation.

Soft switch can communicate with TG via the IPDC protocol to determine if an incoming DS0 circuit on a DS1 port on a telephone PSTN interface is free and if so to allocate that circuit to set up a connection .

Depending on the contents of customer trigger plan soft switch may require other call processing such as for example an 800 call translation table lookup from SCP based on information in signaling message .

SCP can then provide to soft switch a translated destination number i.e. the number of called party .

Soft switch can then query RS to perform further processing. Route logic of RS can be processed to determine a termination using least cost routing. The termination can be through data network .

Soft switch i.e. the originating soft switch can then communicate with terminating soft switch to set up the other half of the call.

Terminating soft switch can then communicate with port status PS of RS to determine whether a DS0 circuit is available for termination and in which TG.

Having determined a free circuit is available on TG soft switch can allocate a connection between TG and carrier facility for termination to called party .

Soft switch can then communicate with soft switch to establish connection between TG and TG . Soft switch can provide the IP address for TG to soft switch . Soft switch provides this address to TG . TG sets up a real time transport protocol RTP connection with TG to complete the call path.

Soft switch can communicate with TG via the IPDC protocol to determine if an incoming DS0 circuit on a DS1 port on a telephone PSTN interface is free and if so to allocate that circuit to set up a connection .

Depending on the contents of customer trigger plan soft switch may require other call processing such as for example an 800 call translation table lookup from SCP based on information in the signaling message.

SCP can then provide to soft switch a translated destination number i.e. the number of called party .

As part of the query performed on CS soft switch can determine that the called party corresponds to a data modem representing a data call.

Soft switch can then communicate with network access server NAS to determine whether a modem is available for termination in NAS .

If soft switch determines that a terminating modem is available then soft switch can set up connections and via TDM switching to terminate the data call in a modem included in NAS . Connections and are DS0 circuits. Connection represents a TDM bus. TDM pass through switching is described further with respect to Tables 177 and 178 above.

If soft switch determines that a terminating modem is available then soft switch terminates the call to that modem.

3. Voice Call Originating on an SS7 Trunk on a Trunking Gateway and Terminating Via Access Server Signaling on an Access Gateway

Soft switch can communicate with TG via the IPDC protocol to determine if an incoming DS0 circuit on a DS1 port on a telephone PSTN interface is free and if so to allocate that circuit to set up a connection from carrier facility .

Depending on the contents of customer trigger plan soft switch can require other call processing such as for example an 800 call translation table lookup from SCP based on information in signaling message.

SCP can then provide to soft switch a translated destination number i.e. the number of called party .

Soft switch can then query RS to perform further processing. Route logic of RS can be processed to determine a least cost routing termination. The termination can be through data network .

Soft switch i.e. the originating soft switch can then communicate with terminating soft switch to set up the other half of the call.

Terminating soft switch can then communicate with port status PS of RS to determine whether a DS0 or DS1 circuit is available for termination and in which AG.

Having determined a free circuit is available on AG soft switch can allocate a connection between AG and customer facility for termination to called party .

Soft switch can then communicate with soft switch to establish connection between TG and AG . Soft switch can provide the IP address for TG to soft switch . Soft switch provides this address to TG . TG sets up a real time transport protocol RTP connection with AG based upon the IP addresses provided by the soft switch to complete the call path.

4. Voice Call Originating on an SS7 Trunk on a Trunking Gateway and Terminating on an Announcement Server

Soft switch can communicate with TG via the IPDC protocol to determine if an incoming DS0 circuit on a DS 1 port on a telephone PSTN interface is free and if so to allocate that circuit to set up a connection between customer facility and TG .

Depending on the contents of customer trigger plan soft switch may require other call processing such as for example an 800 call translation table lookup from SCP based on information in signaling message .

SCP can then provide to soft switch a translated destination number i.e. the number of called party .

Soft switch can then query RS to perform further processing. Route logic of RS can be processed to determine a least cost routing termination. RS determines an optimal termination from data network or least cost routing with data network terminations as exemplary choices. Off network routing can be considered as well. The termination can be through data network .

If a route termination cannot be found the call is treated by the announcement server . Treating refers to processing done on a call.

For example assuming a TG to TG call the soft switches can communicate and soft switch can check port status of RS to determine whether a DS0 circuit is available for termination on a TG and the IP address of the TG.

Assuming for this call flow that no DS0 circuits are determined to be free on TG soft switch communicates with TG including providing the IP address of ANS too TG . Soft switch can also communicate with ANS via the IPDC protocol to cause ANS to perform functions. TG can set up an RTP connection with ANS to perform announcement processing and to deliver an announcement to calling party .

5. Voice Call Originating on an SS7 Trunk on a Network Access Server and Terminating on a Trunking Gateway Via SS7 Signaling

Soft switch can communicate with NAS via the IPDC protocol to determine if an incoming DS0 circuit on a DS1 port on a telephone PSTN interface is free and if so to allocate that circuit to set up a connection between carrier facility of calling party and NAS .

Depending on the contents of customer trigger plan soft switch may require other call processing such as for example an 800 call translation table lookup from SCP based on information in signaling message .

SCP can then provide to soft switch a translated destination number i.e. the number of called party .

In one embodiment soft switch determines from the dialed number in the IAM message that the call is a voice or VPOP call and thus needs a trunking gateway to handle the voice call. Soft switch sends an IPDC message to the NAS to TDM pass through the call to the TG.

To determine the type of call soft switch can also perform further processing to determine e.g. whether the call is to a destination known as a data modem termination dialed number. If the dialed number is not to a data number then soft switch determines that the call is a voice call.

Soft switch can now determine whether a TG has any ports available for termination by querying port status of route server and if so can allocate the available port and set up a TDM bus connection in the NAS via TDM switching and DS0 circuit to TG . Soft switch can also query routing logic of RS to determine a least cost route termination to the called destination.

Soft switch i.e. the originating soft switch can then communicate with terminating soft switch to set up the other half of the call.

Terminating soft switch can then communicate with port status PS of RS to determine whether a port is available for termination and in which TG.

Having determined a free circuit is available on TG soft switch can allocate a connection between TG and carrier facility for termination to called party .

Soft switch can then communicate with soft switch to establish connection between TG and TG . Soft switch can provide the IP address for TG to soft switch . Soft switch provides this address to TG . TG sets up an real time transport protocol RTP connection with TG to complete the call path.

6. Voice Call Originating on an SS7 Trunk on a NAS and Terminating Via Access Server Signaling on an Access Gateway

Soft switch can communicate with NAS via the IPDC protocol to determine if an incoming DS0 circuit on a DS1 port on a telephone PSTN interface is free and if so to allocate that circuit to set up a connection from carrier facility .

Depending on the contents of customer trigger plan soft switch can require other call processing such as for example an 800 call translation table lookup from SCP based on information in signaling message.

SCP can then provide to soft switch a translated destination number i.e. the number of called party to soft switch .

In one embodiment soft switch determines from the dialed number in the IAM message that the call is a voice or virtual point of presence VPOP call and in this scenario needs an access gateway to handle the voice call. Soft switch sends an IPDC message to the NAS to TDM pass through the call to the AG.

To determine the type of call soft switch can also perform further processing to determine e.g. whether the call is to a destination known as a data modem termination dialed number. If the dialed number is not to a data number then soft switch determines that the call is a voice call.

Soft switch can now determine whether an AG has any circuits available for termination by querying port status of route server and if so can allocate the available port and set up a TDM bus connection in the NAS via TDM switching and DS0 circuit to AG . Soft switch can also query routing logic of RS to determine a least cost route termination.

Soft switch i.e. the originating soft switch can then communicate with terminating soft switch to set up the other half of the call.

Terminating soft switch can then communicate with port status PS of RS to determine whether a port is available for termination and in which AG.

Having determined a free circuit is available on AG soft switch can allocate a connection between AG and customer facility for termination to called party .

Soft switch can then communicate with soft switch to establish connection between AG and AG . Soft switch can provide the IP address for AG to soft switch . Soft switch provides this address to AG . AG sets up a real time transport protocol RTP connection with AG to complete the call path.

Soft switch can communicate with NAS via the IPDC protocol to determine if an incoming DS0 circuit on a DS1 port on a telephone PSTN interface is free and if so to allocate that circuit to set up a connection .

Depending on the contents of customer trigger plan soft switch may require other call processing such as for example an 800 call translation table lookup from SCP based on information in the signaling message.

SCP can then provide a translated destination number i.e. the number of called party to soft switch .

As part of the query performed on CS or based on a query to RS soft switch can determine that the called party corresponds to a data modem representing a data call.

Soft switch can then communicate with network access server NAS to determine whether a modem is available for termination in NAS .

If soft switch determines that a terminating modem is available then soft switch terminates the call to that modern.

Soft switch can communicate with NAS via the IPDC protocol to determine if an incoming DS0 circuit on a DS1 port on a telephone PSTN interface is free and if so to allocate that circuit to set up a connection for the purpose of authenticating calling party .

Depending on the contents of customer trigger plan soft switch may require other call processing such as for example an 800 call translation table lookup from SOP based on information in the signaling message.

SOP can then provide a translated destination number i.e. the number of called party to soft switch .

As part of the query performed on CS soft switch can determine that the called party Corresponds to a data modem representing a data call and that calling party gains access to network resources via an outbound call back following authentication.

Soft switch can then request that authenticating information from calling party be entered at NAS . Upon verification of the authentication information soft switch can release the call and reoriginate an outbound callback from NAS .

Soft switch communicates with network access server NAS to determine whether a modem is available for termination of a data call on NAS .

If soft switch determines that a terminating modem is available then soft switch can call calling party via signaling through SS7 GW to carrier facility of calling party to set up connection between carrier facility and NAS . Soft switch terminates the call to a modem in NAS .

9. Voice Call Originating on Access Server Dedicated Line on an Access Gateway and Terminating on an Access Server Dedicated Line on an Access Gateway

Soft switch can communicate with AG via the IPDC protocol to determine if an incoming DS0 circuit on a DS1 port on a telephone PSTN interface is free and if so to allocate that circuit to set up a connection from carrier facility .

Depending on the contents of customer trigger plan soft switch can require other call processing such as for example an 800 call translation table lookup from SCP based on information in signaling message.

SCP can then provide a translated destination number i.e. the number of called party to soft switch .

Soft switch can then query RS to perform further processing. Route logic of RS can be processed to determine least cost routing. The termination can be through data network .

Soft switch i.e. the originating soft switch can then communicate with terminating soft switch to set up the other half of the call.

Terminating soft switch can then communicate with port status PS of RS to determine whether a DS0 circuit is available for termination and in which AG.

Having determined a free circuit is available on AG soft switch can allocate a connection between AG and customer facility for termination to called party .

AG and AG establish an RTP connection based on IP addresses provided by soft switches and . Soft switch can then communicate with soft switch to establish connection between AG and AG . Soft switch provides the IP address for AG to soft switch . Soft switch provides this address to AG . AG can set up a real time transport protocol RTP connection with AG to complete the call path.

10. Voice Call Originating on Access Server Signaled Private Line on an Access Gateway and Terminating on SS7 Signaled Trunks on a Trunking Gateway

Soft switch can communicate with AG via the IPDC protocol to determine if an incoming DS0 circuit on a DS1 port on a telephone PSTN interface is free and if so to allocate that circuit to set up a connection from carrier facility .

Depending on the contents of customer trigger plan soft switch can require other call processing such as for example an 800 call translation table lookup from SCP based on information in signaling message.

SCP can then provide a translated destination number i.e. the number of called party to soft switch .

Soft switch can then query RS to perform further processing. Route logic of RS can be processed to determine least cost routing. The termination can be through data network .

Soft switch i.e. the originating soft switch can then communicate with terminating soft switch to set up the other half of the call.

Terminating soft switch can then communicate with port status PS of RS to determine whether a DS0 circuit is available for termination and in which TG.

Having determined a free circuit is available on TG soft switch can allocate a connection between TG and customer facility for termination to called party .

Soft switch can then communicate with soft switch to have AG establish connection between AG and TG . Soft switch can provide the IP address for TG to soft switch . Soft switch provides this address to AG . AG can set up a real time transport protocol RTP connection with TG to complete the call path.

Soft switch can communicate with AG via the IPDC protocol to determine if an incoming DS0 circuit on a DS1 port on a telephone PSTN interface is free and if so to allocate that circuit to set up a connection from customer facility .

Depending on the contents of customer trigger plan soft switch can require other call processing such as for example an 800 call translation table lookup from SCP based on information in signaling message.

SCP can then provide a translated destination number i.e. the number of called party to soft switch .

As part of the query performed on CS or to RS soft switch can determine that the called party corresponds to a data modem representing a data call.

If the incoming call is determined to be a data call then the incoming circuit is connected to TDM bus which is in turn connected to circuit which terminates the data call to a modem in NAS .

Soft switch can then communicate with network access server NAS to determine whether a modem is available for termination in NAS .

If soft switch determines that a terminating modem is available then soft switch can terminate the call to the modem.

Soft switch can then determine whether via communication with AG via IPDC protocol communication whether a circuit is available for the outbound data call. If AG has an available circuit then soft switch can use TDM bus to connect circuit to circuit which is in turn terminated to a modem in NAS .

TDM bus can then be connected to circuit i.e. an access server signaled dedicated access line to carrier facility using for example D channel signaling of an ISDN PRI line. TDM pass through switching is described further with respect to Tables 177 and 178 above.

Telecommunications voice network services supported by the present invention include for example origination and termination of intralata interlata and international calls seamlessly between the PSTN and Telecommunications network . Access can be achieved by switched or dedicated access lines. Call origination can be provided via Feature Group D FGD and direct access line DAL T 1 PRI access to access servers . Local access can be provisioned via the PSTN with FGD and co carrier termination to trunking gateways . Dedicated DS0s T 1s and T 3s can connect an end user s CPE directly to AGs . In one embodiment a standard unit of measurement for usage charges can be a rate per minute RPM . Where telecommunications network provides the DS0s T 1s and T 3s there can be an additional monthly recurring charge MRC for access.

In one embodiment ingress and egress can be via the PSTN. In another embodiment native IP devices can originate and terminate calls over data network over the IP protocol. In such an environment flat rated calling plans are possible.

Private voice network PVN services can be a customer defined calling network that allows companies to communicate on net at discounted prices. The backbone of the product can be dedicated access connectivity such as for example using a DAL or ISDN PRI for access to telecommunications network . Using a capability called dedicated termination service DTS calls that originate either by PIC or a dedicated access method can terminate on dedicated facilities when possible. For example assume a customer with five locations across the country e.g. in on net cities has T 1s deployed at each site. Calls between those five sites can be significantly discounted due to the fact that the carrier owning telecommunications network originates and terminates the calls on dedicated facilities at little cost. Additionally customers will be able to add others to their PVN such as for example business partners vendors and customers enabling the customer as well as the others to further reduce their communications costs.

In one embodiment service can be provided to customers for a MRC with no additional charge for on net calls and with a charge on a rate per minute basis for all other types of calls. In another embodiment no MRC can be required and all calls can be charged on a RPM basis. In another embodiment the RPM may vary according to the type of call placed.

Network requirements can include use of dedicated termination service DTS . DTS can allow long distance calls that originate from a FGD or DAL to terminate on a DAL. Traditionally these calls are routed to POTS lines. This functionality can enable the network to determine if the call can be terminated over its own facilities and if so rate it appropriately. DTS is the backbone functionality of PVN. A routing table can allow the network to identify calls that originate from either an ANT or Trunk Group that has been assigned an associated terminating Trunk Group. In one embodiment 700 800 and 900 type calls can not originate over DALs.

Customer premises equipment CPE requirements can include a CSU DSU with a router for Multiple Service T 1 with dedicated access and a customer can have an option to lease or buy them.

Long distance 1 service can allow a customer to place long distance calls to anywhere in the U.S. Canada USVI and Puerto Rico by dialing 1 plus an area code NPA plus a 7 digit phone number. International calls can be placed by dialing 011 plus a country code CC plus a city code plus a number. Both switched and dedicated access can be available from on net cities or from off net cities i.e. through a designated off net carrier .

Project Access Codes PACs can be for example two to twelve digits. PACs can be end user defined or predefined codes that are assigned to for example employees projects teams and departments. PACs can be used for example by a customer to track such things as intralata interlata and international calls.

An example benefit to a customer of using PACs is that PACs can allow businesses to allocate and track costs of specific projects. Additionally they can be used to track employee or department calls and expenditures. PACs can also be used to prevent unauthorized long distance calling. In one embodiment an invoice can track account codes individually and can then group the codes in a hierarchical fashion as well.

Operationally PACS can be entered by a calling party after dialing e.g. a local long distance or international phone number. The calling party can hear a network generated tone prompting the calling party to enter the PAC code. Once the PAC code has been entered and authorized the call can be connected as usual.

All types of PACs can be translated on the invoice from code to text i.e. PAC number 1234 could be translated to a Marketing Department and PAC number 4567 could be translated to John Doe. An example invoice could show call detail records CDR and total expenditures for each PAC.

If an invalid code is entered a voice prompt can immediately respond with a message such as for example Invalid code please try again. A second invalid entry can prompt the same message. A third can prompt another message such as e.g. Goodbye. PAC Translation would not occur in this instance.

If a user fails to enter any account code the same prompting for receipt of an incorrect account code entry can take place. A time out can occur after for example 3.5 seconds of no activity. PAC Translation would not occur in this instance.

Customers with PIC access can be required to wait for a tone before entering a PAC. Customers with dedicated access can complete the entire dialing sequence phone number and PAC without waiting for the tone and be connected without even hearing the tone. If however the customer using dedicated access pauses after dialing the phone number the network can still generate a tone prompting the user for the PAC.

Business customers can have the ability to modify their PAC tables via a world wide web Internet interface. The modification functions can include for example additions deletions changes and modifications of verbal translations. These changes can take effect within e.g. 60 minutes or less.

Customers that choose PAC Translation can have the translation not the actual account code presented on an invoice. Customers that do not use PAC Translation can have the account code presented on the invoice.

PAC tables can be associated to any type of resource e.g. Master Account ANI Trunk Group Location Account and or Authcode . Multiple PAC tables in one embodiment cannot be associated with a single resource.

Verified Forced PACs enable a customer to assign PACs to e.g. employees teams and departments that force the end user to enter the PAC prior to completing a long distance call.

Unverified Forced PACs can require that a PAC of the chosen digit length e.g. four digits be entered to complete a call however the digits are not pre determined and the customer can have the ability to use all PACs in a given digit length. For example with four digit PACs the customer could use any code from 0001 9999.

Unverified Unforced PACs are the same as Unverified Forced PACs but do not require a caller to enter the PAC to complete the long distance call. Unforced PACs can have for example a override feature allowing calls to be connected quickly without relying on a network timeout to connect the call. If after e.g. 3.5 seconds a PAC is not entered the call can connect as usual. If a user enters a lower number of digits than the PAC table indicates a prompt Invalid code please try again can be announced. At this point the pound override feature can be used or the user can try again. A second wrong entry can produce the same prompt and a third can prompt Goodbye. If a user enters more digits than has been setup on the PAC table the first digits that comprise the correct PAC length can be used and the remaining digits ignored. Translation can occur if activated for the digits that correspond to the PAC table only. Billing presentation can also show the correct digit length.

Partially Verified Forced PACs can range from for example 4 to 12 digits. A portion of the PAC can be verified while the remaining portion is not however the entire digit stream can be forced. The customer can choose the digit length for user authentication as well as determine the digit length project accounting portion. A minimum of e.g. 2 digits can be verified and can occur before the unverified portion of the digit stream. For example a customer can choose a 5 digit PAC and the first two digits would authenticate the user and the remaining digits would be used for accounting purposes. Additionally each portion of the PAC can have the option to be translated by the customer for invoice and web presentation i.e. PAC 12345 could be translated to 12 John Doe and 345 could translate to Project X. 

Department summary by PAC group enables a customer to choose any given set of PACs associated with a single table and group them under a customer chosen heading. For example the header Marketing can contain codes and and the header Customer Care can contain codes and . The invoice can present summaries under each header.

Class of Service Restrictions COSR can allow a customer to restrict outbound calling by certain jurisdictions. Restrictions can be set at e.g. the account ANI Trunk Group Authcode or PAC level. The customer can be able to modify the COSR through e.g. a web interface. Alternatively some destinations such as e.g. international destinations could not be modified by a customer directly and the customer could be required to contact customer care for approval.

Exemplary COSRs include for example interlata COSRs restricting calls to a customer s LATA only intrastate calls restricting calls to the customer s originating state interstate calls allowing end users to place domestic calls only anywhere in the U.S. whether local intralata intrastate or interstate domestic and dedicated international destinations allowing domestic calling as well as international calling to selected countries based on country code as determined by the customer and domestic and selected international i.e. can exclude high risk countries that allows callers to place all types of domestic and international calls.

Domestic and international can be the default unless otherwise specified by the customer. A list of high risk countries can be unavailable unless otherwise requested by the customer. These high risk countries can have an increased probability of fraud and can require proper credit and sales approval.

In an example embodiment PACs can be the first service restriction look up followed by restrictions set up at the account level. High risk countries can always be blocked unless otherwise requested by the customer.

A plurality of forms of access ban be provided including for example primary interexchange carrier PIC dedicated T 1 T 3 PRI and 101 XXXX.

Customers pre subscribed to the telecommunications carrier owning telecommunications network can have PIC access to the network via FGD trunks from an LEC. This access method can allow for e.g. intralata intrastate interstate and international calling.

Dedicated customers can originate calls using local facilities such as T 1 T 3 on telecommunications network .

101 XXXX customers with an established account and ANIs loaded into the billing system can access telecommunications network . In this instance customers do not have to have PIC access. If an end user dials 101 XXXX without first establishing an account with the respective ANIs calls can be blocked at the network level and the end user can hear a recording explaining the call cannot be completed and to contact the operator for further assistance.

The order entry OE portion of the order management system OSS supports non PICd ANIs. This system can load the ANIs into a soft switch e.g. as subscribed non PICd ANIs which allows calls to be placed via 101 XXXX. These ANIs can stay non PICd until the customer has requested a change to the PIC. Regular system maintenance does not NC these designated ANIs to telecommunications network carrier and identifies these ANIs as Subscribed Non PICd. Because 101 XXXX can only allowed for customers of telecommunications network LEC billing CABS will not be necessary for direct customers.

Casual calling can be allowed through resale and wholesale customers if requested. The customer can be required to have its own CIC code to do so. Call treatment discrimination can be necessary for Resale and Wholesale customers in this instance. The network can identify the customer type by the CIC and allow or disallow casual access. In this instance LEC billing arrangements can be necessary. CIC code billing can be available as an option for wholesale and resale customers.

For domestic calls example call ratings of 1 second increments with for example 18 second minimums per call can be supported.

For international calls example call ratings of 1 second increments with 1 minute minimums per call can be supported.

Example times of day TOD and days of week DOW etc. can be rated differently. For example 8 am 5 pm Monday through Friday can be rated differently than 5 01 pm 7 59 am Monday through Friday and all day Saturday and Sunday.

1 toll free internet access private line and dedicated access lines can be provisioned over the same multiple service T 1. Multiple service T 1 can support two way trunks.

MRCs can be charged for any combination of enhanced or basic services either as a group or stand alone.

A 3 way conferencing bridge can be created by the end user by choosing the conferencing feature from the enhanced services menu. The end user enters up to e.g. two additional phone numbers and is then connected by a bridge.

A service which places the caller on hold while playing an announcement message can be offered as a service to customers.

Toll free service can allow calling parties to dial an 8XX number and terminate the call to either a POTS line or DAL. The person or company receiving the call is responsible for the cost of the transaction.

Termination can be available to both on net and off net areas in the U.S. Off net can be handled CB. Calls can originate anywhere in the U.S. plus e.g. Canada USVI and Puerto Rico.

Real time ANI network based feature can pass the originating ANI to the customer answering the call. The number is viewed by the operator of the answering end using CPE. This can be used by call centers wishing to pull customer records based on the customer s phone number. This can be a DAL only service. Default delivery can provide an entire ANI. Customers can add up to 2 delimiters.

Dialed Number Identification Service DNIS is a network based feature that can provide the answering party with the toll free or customer delivered number dialed. Customer owned computer telephony equipment can provide the display. DNIS allows multiple toll free numbers to be used on a single trunk group in a call center setting because of its ability to display which number has been dialed enabling the calls to be handled uniquely. This can be a DAL only service. Customers can order DNIS in a variety of numbering format schemes from for example 4 10 digits. DNIS can be the entire toll free number. DNIS can be any portion of the toll free number. DNIS can be any customer defined number from for example 4 10 digits. Default delivery can include the entire toll free number. Customer can define the number with up to two delimiters.

Time of Day TOD routing routes toll free calls to alternate customer defined destinations based on the time of day. Routing can be determined by the customer in one minute increments. The time of day can be determined by the terminating location s time zone. A day can be equal to 12 00 am to 11 59 pm.

Day of Week DOW routing routes toll free calls to alternate customer defined destinations based on the day of week. The time of day is determined by the terminating location s time zone. A day can be equal to 12 00 am to 11 59 pm.

Area Code NPA routing routes toll free calls to alternate customer defined destinations based on the area code the originating phone call came from.

NPA NXX routing routes toll free calls to alternate customer defined destinations based on the area code and prefix of the originating ANI.

Geographic routing routes toll free calls to alternate customer defined destinations based on the state the originating phone call came from.

Multi carrier routing routes pre determined percentages of toll free calls over a single toll free number to alternate carriers defined by the customer. This is a function of the SMS database.

Percentage Allocation routing routes toll free calls to alternate customer defined destinations based on call distribution percentages. Percentages can be defined down to the nearest 1 .

Day of Year DOY routing routes callsed based on days of the year that are determined by the customer.

Extension routing routes calls based on end user DTMF input. These extensions are pre defined by the customer and can range from 2 to 12 digits. A table can be built that associates a terminating point e.g. an ANI or Trunk Group with an extension. A network prompt such as for example a bong tone can be used. A time out of for example 3.5 seconds can be used. An invalid entry prompt such as Invalid Code Please Try Again can be used. A two invalid entry maximum and then a Goodbye and a network disconnect can be used. A no entry warning such as Invalid Code Please Try Again can be used. A two no entry maximum and then a Goodbye and a network disconnect can be used. An Invoice Presentation including a summary of calls minutes taxes and total cost can be the standard when customer utilizes Extension Routing. An extension translation can be used such that each extension can be translated to text with a maximum character length of for example 35.

Call blocking does not allow toll free calls to originate from a state an area code including Canada USVI Puerto Rico NPA NXX and or an ANI as defined by the customer. Blocked calls by default can hear a network busy signal. In another embodiment a call blocking announcement can be used. This is a customer option that enables blocked calls to hear either a network generated or a custom customer defined prompt. The network prompt can read Your call cannot be completed from your calling area. The customer can define its own prompt to last no more than for example 10 seconds. Additional charges can apply to this service.

Direct Termination Overflow DTO allows a customer to pre define termination points for calls that exceed the capacity of the customer s network. Terminating points can include ANIs and or Trunk Groups. Overflow traffic can be sent to any customer site whether or out of a serving area. The customer can assign up to five terminating points that can hunt in a sequence as defined by the customer.

Routing Feature Combination allows the customer to route calls based on any grouping of routing features listed above.

Info Digit Blocking selectively blocks calls based on the info digit that is passed through. Examples of info digits that include 07 27 29 and 70 calls can be blocked at a customer s request. The default can permit calls to pass regardless of info digit. Payphone Blocking can be an option to a customer. In one embodiment calls that originate from payphones can be blocked. Payphone originated calls that are not blocked can incur a per pall surcharge that can be marked up and passed to the customer.

Toll Free Number Portability TFNP allows customers to change RespOrg on their toll free number and port the number to a different carrier. Toll Free Reservation allows reservation of vanity or customer requested toll free numbers for later use. This is a function of the national SMS database.

Toll free 1 internet access private line and dedicated access line services can be able to be provisioned over the same T 1. The service also supports two way trunks.

Different call rates can be charged to a customer based upon criteria such as for example the type of call placed i.e. the type of origination and termination.

Time of day and day of week pricing can permit calls placed 8 am 5 pm Monday through Friday and all day Saturday and Sunday.

Cross contribution permits volume from other services to contribute to monthly commitment levels for toll free and vice versa.

A customer can commit to monthly revenue levels based upon volume thresholds. Rates can be set according to the thresholds.

Term discounts can permit customers committing to service contracts such as for example 1 2 and 3 year terms to achieve higher discounts than those customers which are scheduled on monthly terms. Term discounts can effect net rates after all other discounts are applied.

Monthly recurring charges MRCs can be charged for any individual or combination of enhanced or basic services either as a group or stand alone.

A directory listing in the toll free information service provided by AT T can be provided at a customer s request. This service may or may not require a one time or monthly service charge.

Interactive voice response IVR routing services can be offered to customers over telecommunications network .

Automatic call distribution ACD services can be offered to customers over telecommunications network .

Quota Routing can allow the customer to define a minimum and maximum number of calls that are routed to a particular termination point. The call thresholds can be based on e.g. 15 minute half hour one hour and 24 hour increments.

Toll free valet call parking services can hold calls in network queue until the customer has an open Trunk for the call to terminate to. This benefits a customer in that it does not have to over trunk for busy periods. Music on hold can be available as a standard feature of toll free valet.

A custom greeting or announcement is an enhanced feature of Toll Free Valet allowing callers to hear a customized greeting developed by the customer. Additional charges can apply for a custom greeting.

Operator Services are services which can handle a customer request for for example collect calls third party billed calls directory assistance DA and person to person calls.

Operator Services can be available to any customer using for example 1 long distance service calling card service and prepaid calling card service of the carrier of telecommunications network .

An operator can be accessed by dialing 00 or 101 XXXX 0. Access to an operator can be accomplished through switched or dedicated access.

A plurality of operator services are supported including for example collect calling service by this the caller requests that the called party be billed for the call third party billing service allowing the caller to bill calls to another number other than the originating phone number directory assistance DA service allowing customer to retrieve phone number outside of its area code by 1 Area Code 555 1212 and making the requests through an operator person to person calling service allowing a customer to contact an operator and request that the operator call a specific number and complete the call for the user i.e. an operator connects the call by creating a bridge ensuring a connection and then bowing out of the connection credit for call service by which in instances where line quality is poor or a connection is lost an operator can give an appropriate credit branded service by which reseal and wholesale customer s can opt to use carrier owned Operator Services and have the services branded to their preference and service performance levels can be promised and enforced by which operators answer a call within a given number of rings such as for example four.

Non Published Numbers service allows customers to keep their ANI s and toll free numbers non published.

Billed Number Screening allows a customer to establish who and who cannot charge calls to their phone number.

Charge Quotation Service permits an operator to quote the customer the cost of service being provided before the service is complete.

Line Status Verification service permits an operator to check the status of a line idle busy off hook per customer request.

Busy Line Interrupt service permits an operator to interrupt the called party s call in progress and request an emergency connection with the calling party.

Telephone Relay Service TRS is a service provided for the hearing impaired. An operator assists the caller by typing the message and sends the message to the terminating party via TTD.

International operator services can be provided which provide similar features to domestic operator services with the addition of multiple language support. Internation operator services can be reached by dialing 00. 

Calling card service can include a credit card issued by a carrier that can allow a customer to place for example local long distance and international calls. The calling card can act as a stand alone service or as part of the PVN product.

Calling card service can be available anywhere in the US Puerto Rico USVI and Canada via toll free origination. Additionally access can be from foreign countries via ITFS service through an off net provider. A customer can have a domestic physical address and billing location to obtain a calling card.

Operationally a customer can dial a toll free access number or and ITFS access number that prompts the user to enter an authorization and pin number. The customer can then be prompted to enter a ten digit phone number the customer is attempting to call. The call is then connected.

Calling cards can allow customers to make long distance international and local calls while away from their home or office. These calls are billed monthly on the same invoice with other telecommunications services.

Calling card services can include a plurality of features such as for example universal toll free access number UAN UAN authorization code class of service COS restrictions reorigination usage cap authorization code authcode translation invoice presentation project account codes PACs dial correction 3 way conferencing and dedicated termination service.

Universal Toll Free Access Number UAN is the toll free number that accesses the calling card platform from anywhere in the US Puerto Rico USVI and Canada. The UAN serves all customers that choose the UAN.

UAN Authorization Code authenticates the end user. For UAN customers the code consist for example of 10 digits followed by a PIN number totaling 14 digits in length. The 10 digits can either be randomly generated or can be requested by the customer as the customers Billing Telephone Number or any other phone or number sequence . The PIN can also either be randomly generated or can be requested by the customer. The default can be random generation for both Authcode and PIN numbers. No more than 10 PIN numbers can be assigned to a single Authcode. An additional 6 digit international PIN can be generated for customer use when originating calls from an international destination. This PIN can be entered in lieu of the 4 digit domestic PIN.

The customer can limit calling card use based on Class of Service Restrictions COS restrictions. Cards can as a default have domestic all 50 states Canada USVI PR origination and termination only. International origination and termination can be made available upon request by the customer.

Re Origination will allow customers to place multiple calling card calls without having to hang up dial the access number and enter the authorization code again. The feature can be initiated by depressing for 2 full seconds.

Usage Cap limits any given authcode to a customer determined usage limit. Once the maximum dollar limit is hit the card ceases working and prompts the customer to contact customer service. Usage limits can be set in 10 increments and at daily weekly or monthly thresholds. When a customer is approaching its maximum a prompt can be announced stating your usage limit is near its maximum you have X minutes remaining please contact customer service. The prompt can begin when the user reaches 90 of its allowance based on dollars. In the even the customer is in the middle of a connection only the card owner will hear the prompt. If a new call is placed and the en user is already within the 90 threshold a prompt will notify the customer of the number of minutes that are available after the terminating number is entered. The number of minutes will be based on the termination point and the rating associated with it.

Authcode translation allows a customer to translate authorization codes to for example a user name or department name up to a 25 character maximum.

An invoice can by default show 10 digits of the 14 digits and associate each authcode with expenditures. If the customer chooses Authcode Translation the invoice can automatically present the translation and not the authcode.

A customer can associate a PAC Table with the customer s Authcodes. PAC table rules apply. An end user can be prompted as usual after entering in the authcode and terminating ANI. The prompts apply to PACs on calling card as an long distance service.

If a phone number is mis dialed dial correction allows the user to hit the key to delete the current entry and being to re enter the phone number in its entirety.

Personal Toll Free Access Number PAN service provides a toll free number that accesses the calling card platform from anywhere in the US Puerto Rico USVI and Canada. A PAN can be unique to individual users.

PAN Authorization Code authenticates the end user. For PAN customers the code can consist of e.g. 4 digits either defined by the customer or randomly generated.

Corporate Toll Free Access Number CAN service provides a toll free number that accesses the calling card platform from anywhere in the US Puerto Rico USVI and Canada. This number can be unique to a corporate customer and can only be used by those end users with the corporate customer.

CAN Authorization Code authenticates the end user. For CAN customers the code can consist of e.g. 7 digits either defined by the customer or randomly generated.

Customized Greeting service allows a customer to customize the network generated greeting at the time of provisioning. This service can be available to CAN customers only.

Call Transfer service allows the calling card customer to connect two parties and attend the conference or drop the bridge and establish the connection between the two called parties.

Domestic Calls can be priced using for example 1 second increments with for example an 18 second minimum per call.

International Calls can be priced using for example 1 second increments with for example a 1 minute minimum per call. The first minute can be rated differently than additional minutes.

PVN Gold and Platinum Calls can be rated based on discounts associated with the PVN product group. Rating can be based on originating and terminating points. On PVN Calls can be identified and rated appropriately.

A connection surcharge can be charged per call. The charge can differ based on the originating and terminating point of the call. These combinations include Domestic to Domestic Domestic to International and International to International.

Time of Day and Day of Week pricing can permit calls placed 8 am 5 pm Monday through Friday to be rated differently than those placed 5 01 pm 7 59 am Monday through Friday and all day Saturday and Sunday.

Cross Contribution permits volume from other services to contribute to volume discounts for calling card and vice versa.

A customer can commit to monthly revenue levels based upon Volume Thresholds. Rates can be set according to the thresholds.

Term Discounts can permit customers committing to service contracts such as for example 1 2 and 3 year terms to achieve higher discounts than those customers who have subscribed on monthly terms. Term discounts can effect net rates after all other discounts are applied.

Monthly Recurring Charges MRCs can be charged for any combination of enhanced or basic services either as a group or stand alone.

One Number service is an enhanced call forwarding service that uses the intelligence of telecommunications network network to re route calls from a customers POTS DID to an alternate termination point. One Number allows customers to receive calls regardless of where they are located. A simple WEB interface enables customers to define which phone number they want to receive calls on and for which days and what periods of time.

One Number can be available to any customer telecommunications network local and long distance voice services. The service allows the customer to choose termination points anywhere in the world. Security can be necessary to prevent fraud and authenticate users. Calls or faces can terminate to multiple services including e.g. POTS lines fax machines voice mail pagers e mail fax and cellular phones.

Forwarded calls can be filtered e.g. by soft switch and can be forwarded to the appropriate terminating number. Multiple termination points can be specified by the customer enabling calls to follow them.

When a call is forwarded to the next number a network prompt could inform the caller that their call is being forwarded. The caller could hear e.g. Please hold while we attempt to locate John Doe Subscriber s Name . If you would like to leave a voice message please press the pound sign now. 

Selective Forward allows the customer to forward only selected calls by originating ANI. All other calls could terminate normally.

 Override service allows a caller to out to the subscriber s main number which can have voice messaging capability.

Fax Detect allows the customer to have all calls including fax calls come in to a single number only to be forwarded to an actual fax machine ANI. The network could be required to detect T.30 protocol and respond appropriately.

Call Statistics allows a customer to enter a WEB interface and look at all calls that have terminated to their ANI and which have been forwarded to corresponding termination points.

Termination Preferences Lists allow a customer to define up to three terminating numbers. If the first is busy for example the call would be sent to the next number in the list. If the call reached the end of the list the call could disconnect or terminate into whatever type of messaging service that might be available. These lists can be toggled on or off via a web or IVR interface. Up to 5 lists can be created.

Busy Detection re routes busy calls to an alternate destination. In the case of fax the web interface shows when and where the fax was delivered.

IVR Interface permits a customer to change termination points and toggle on or off Termination preference lists via DTMF tones. A customer could be prompted for a pass code for security purposes.

Dedicated Termination Service DTS allows forwarded calls to terminate On PVN over dedicated facilities.

User Authentication ensures that a user authorized routing modifications by e.g. entry of a code or PIN.

Debit card and credit card calls are permitted and are similar to calling card services calls with the addition of third party credit check processing.

Customers have access to a web interface that manages e.g. names phone numbers e mail addresses company names addresses and scheduling. Customers can enter and maintain their own contacts. By selecting names and a meeting time customers can easily administer their own conference from the desktop. Additionally the moderator can view the participants that have and have not connected.

Participants can be notified of e.g. the conference time dial in number if applicable subject and participants by e.g. e mail pager fax or voice message.

Network Dial Out service allows the conference moderator to direct dial each participant at the phone number of choice. When a participant answers the phone a bridge is created. The moderator is always bridged to the call by being dialed directly.

800 Dial In allows the conference moderator to offer a means for participants unable to be dialed directly to participate via a toll free number.

Music On Hold permits a selection of music to be available for the moderator to choose while participants join the bridge. Once all participants have joined the music can automatically turn off.

Selective Caller Mute allows a moderator to mute any participant at any time. Other attendees could e.g. not be able to hear the muted person nor e.g. could the muted person be able to hear other participants in the conference.

Customized Greeting permits customers to generate and load their own greeting that a caller will hear before being connected to the bridge.

Code Access permits a participant to hear a prompt asking for a code determined by moderator that could allow access to the conference. The code can be entered e.g. via dual tone multiple frequencies DTMF tones.

Local Voice can comprise two separate elements. The first element of Local Voice which is also the foundation of the service is commonly referred to as Dial Tone . The other element is referred to as Local Calling Traffic which is the usage that is generated on the Dial Tone. Each element is addressed separately below.

Local Services deliver services comparable to what incumbent ILECs provide. LV DT provides in its basic form 10 digits phone numbers and or services that can access the Public Switched Telephone Network PSTN . LV DT provides the customer the ability to place and receive calls on their LV DT whether the calls are local long distance international toll free or service 611 411 911 0 00 types of calls. Call types can be from an on network customer or from an off network caller.

Two types of digital trunking protocols currently in use today are PBX Digital Trunking and ISDN PRI. Analog services can be provided as well. Digital trunks interface with Hybrid and PBX CPE equipment.

LD VT adheres to the tariffs and regulations that govern Local Service providers in each market that the service is launched. For example federal state and local taxes can apply where applicable.

Local access can be available in those cities where the owner of telecommunications network has co carrier status and a POP within the serving wire center.

The two prevalent protocols that LD VT emulates are Digital PBX Trunking and ISDN PRI. Only one Rate Center that is generic to the customers physical address is allowed with each delivery. Foreign Exchange service is another option but not in combination with a customer s designated Rate Center.

Digital PBX Trunking Digital PBX or DPbx trunking uses a DS 1 4 wire 1.544 Mbit for the underlying transmission facility. Line Code options of AMI or B8ZS and framing options of Super Frame SF or Extended SuperFrame ESF can be offered. Service provides 24 digital channels at 56K per DSO. Fractional DS 1s can also be available with a minimum of 12 DSOs ordered. Each DSO channel carries the signaling overhead. DPbx can be channelized as one way inbound one way outbound or two way trunk groups. Incoming calls hunt to an idle channel within a trunk group low to high while the customer hunts high to low. Customer must yield to a carrier under glare conditions. Calls are initiated with trunk seizure and confirmed by a receiving end via wink signaling. Addressing can be selected as e.g. Dual Tone Multi Frequency DTMF or Multi Frequency typically used for interoffice communications . Answer Supervision is provided on outbound calls.

ISDN also can use a DS 1 4 wire transmission facility. Configurations of PRI can be 23B D or 24B channels. Each B bearer channel transmission is at 64 kpbs clear channel since the signaling is handled on the D or data channel for the circuit. In order for a customer to order a 24B circuit they must have at a minimum one 23B D configuration. In a preferred embodiment customers can have a back up D channel when ordering multiple PRIs with a 24B configuration. Customers can also preferably order PRI with a line coding of B8ZS and framing of ESF. ANI delivery can be standard with PRI service.

When customers order either a DPBX or ISDN PRI service each inbound only or two way trunk group can automatically be provisioned with one phone number. If more than one phone number is needed per trunk group DID services can be ordered.

Direct Inward Dial DID service can be delivered to a customer s CPE equipment via inbound only or two way trunks. The switch can deliver the dialed telephone number up to 7 digits sometimes referred to as DNIS to the premise switch. Number blocks are ordered in blocks of 20 consecutive numbers i.e. 555 1230 thru 555 1249.

There are several different forms of line hunting. There is no additional charge regardless of which hunting method is utilized. The form a customer selects will depend on their business application.

Series completion hunting allows calls made to a busy directory number to be routed to another specified directory number. Series completion hunting begins with the originally dialed member of the series completion group and searches sequential for an idle directory number from the list of directory numbers. A telephone number is assigned to each member of the series completion hunt. When hunting reaches the last number in the group without finding an idle station a busy signal can occur.

Multi line hunting provides a sequential hunt over the members in the multi line hunt group. A phone number is assigned to the main number but each line in the hunt group can have a phone number or a Ter Terminal identifier assigned to it.

Circular hunting allows all lines in a multi line hunt group to be tested for busy regardless of the point of entry into the group. When a call is made to a line in a multi line hunt group a regular hunt is performed starting at the station associated with the dialed number. The hunt continues to the last station in the group then proceeds to the first station in the group and continues sequentially through the remaining lines in the group. Busy tone can be returned if hunting returns to the called station without finding an alternative station that is idle. Usually in this situation all members of the multi line hunt group can be identified with a phone number.

Uniform Call Distribution UCD hunting an enhanced form has specific uses for customers. UCD is not to be confused with Automatic Call Distribution ACD which is an enhanced version of UCD. The UCD feature is a hunting arrangement that provides uniform distribution of terminated calls to members of a multi line hunt group. UCD does a pre hunt for the next call searches for the next idle member and can set the member as the start hunt position for the next call. If no idle member is found the start hunt position can be the last called member plus 1.

Call Forwarding Busy Line can automatically redirect incoming calls to a pre designated telephone number when the line is busy. This service can establish a fixed forward to telephone number. In one embodiment it is not a customer changeable number. An order is issued by a carrier to change the forward to number. When Call Forward Busy line is activated the customer can pay for the local and or toll usage charges. This feature can carry a flat monthly rate.

Call Forwarding Don t Answer can automatically redirect all calls to another telephone number when a telephone is not answered within a specified amount of time. This service can establish a fixed forward to telephone number. In one embodiment it is not a customer changeable number. An order can be issued to change the forward to number. The customer can choose the number of rings before the line forwards the call. When Call Forwarding Don t Answer is activated the customer can pay for the local and or toll usage charges. This feature can carry a flat monthly rate.

Call Forwarding Variable allows the user to redirect all incoming calls to another telephone number. This service can use a courtesy call that allows the customer to notify a party at the forward to number that the customer s calls will be forwarded to the second party s number. Activating the service also returns a confirmation tone to the originator. Call Forwarding Variable can take precedence over other features and services such as Call Forwarding Busy Don t Answer Call Waiting and Hunting. When this feature is activated the customer can pay for any local and or toll usage charges. This feature can carry a flat monthly rate.

Call Hold can enable a user to put any in progress call on hold by flashing the switchhook and dialing a code. This frees the line to originate another call. Only one call per line can be held at a time. The held call cannot be added to the originated call. This feature is not to be confused with the hold button on a telephone set. The party placed on hold will not hear anything unless customer subscribes to Music On Hold service . This feature carries a flat monthly rate.

Three way Calling service can allow a line in the talking state to add a third party to the call without operator assistance. To add a third party the user flashes the switchhook once to place the first party an hold receives recall dial tone dials the second party s telephone number then flashes the switchhook again to establish the three way connection. The second switchhook flash can occur any time after the completion of dialing i.e. when the second party answers a two way conversation can be held before adding the original party for a three way conference.

Call Transfer can conference and transfer an established inbound call to another number. When this feature is used to transfer a call to a local or toll number the customer initiating the feature can pay for the resulting call charges. Call Transfer can be used in conjunction with Three way calling.

Call Waiting Terminating service can alert the user to an incoming call while the phone is already in use. The service signals the customer with two separate tones or tone patterns. The calling party can hear ringing or a tone ring combination. Call Waiting Terminating can take precedence over Call Forwarding Busy Line. Call Waiting Terminating service can be canceled on a per call basis. This can be done by entering a code prior to placing a call or during a call.

Call Waiting Originating service can allow a customer to send to another line within a group a Call Waiting tone if the other line is busy.

Station to Station or abbreviated dialing can allow one station line to call another station line without having to go through the public network. Calls of this nature are usually classified as an intercom call. Intercom calls do not carry any type of local or toll charges because they occur within a common group of numbers. A station to station call can be dialed by using 2 6 digits. An example would be placing a call to an internal station having the phone number 667 2345. If the dialing sequence is set at 4 digits the call could be completed simply by dialing 2 3 4 5. If the common group is set for 3 digit station to station dialing all other station lines can also then set to 3 digit dialing.

Direct Connect service automatically dials a pre selected number. Simply taking the receiver off hook can activate this service. No access codes or telephone numbers need to be dialed. The Direct Connect number can be selected when service is ordered and can be changed by placement of an order such as for example via a web interface. The Direct Connect number can be e.g. an internal line number a local number or a long distance number. If the call is sent to another local or long distance number the customer can pay for the usage charges.

Message Waiting Indication can come in two forms and is used primarily with Voice Mail. A first form of this feature can provide the station line user with an audible indication that Voice Mail has been activated. The stutter tone can be heard when the user goes off hook alerting the user that a message has been left in the voice mailbox. When the message has been retrieved the stutter tone can disappear.

A second form of message waiting indication can be a visual prompt. The visual prompt can operate the same way as the stutter dial tone except that it can use a signal to light a lamp on the customer s phone.

This feature can enable a user to determine the source of an incoming call from a distinctive ring. The pattern can be based on whether the call 1 originates from within a group 2 originates external to the group 3 is forwarded from the attendant position or 4 originates from a line with a Call Waiting Originating feature.

Distinctive Ringing can comprise two call processing components Party Filtering and Calling Party Filtering. The distinctive ringing components can provide for distinctive ringing patterns to be applied to a terminating line based on the originating line. Each component can have a list of multiple options that can be chosen from to customize the distinctive ringing. When Distinctive Ringing is assigned to a line it can be immediately active. The station user cannot deactivate the feature in one embodiment. An order can be placed to have Distinctive Ringing deactivated.

Six way conference calling can allow a non attendant station to sequentially call up to five 5 other parties after dialing the access code. The non attendant station can add parties together to make an e.g. six way call. The originator of the six way call can be billed for the usage charges. There are no limitations on the number of stations that can be assigned a Six way Conference calling group.

Speed calling can allow a user to dial selected numbers using fewer digits than are normally required. One and two digit abbreviated dialing codes can be offered. Speed calling can be e.g. available as an eight number list Speed Calling 8 and a thirty number list Speed Calling 30 . Speed Calling 8 can use codes 2 through 9. Speed Calling 30 can use codes 20 through 49. Customers can order both options on one station line for a total of 38 speed calling codes. Any combination of local and long distance numbers service access codes and 3 digit numbers such a 9 1 1 can be entered into the Speed Calling list. The number of digits stored within each code can be limited to e.g. 16.

Call Rejection can allow a customer to pre select up to a set number of phone numbers to reject any incoming calls from those numbers. If the number is not known this feature can also be activated via a code after the call has been completed. A code can be entered to cancel Call Rejection at any time.

This feature can enable a customer to activate or deactivate Call Forwarding Variable from a remote site. To activate or deactivate the feature from a remote site a Touch Tone service and a Pin Code can be used for example. The Pin Code can be required for security reasons.

Remote Call Forward RCF service can allow a business to establish a local presence in other areas without having to invest in a hardwired solution. RCF can create a virtual inbound only service e.g. via software programming. A customer can make a request from the local service provider for a phone number that can be with a rate center that is not associated with the address to where the calls are to terminate. The RCF can be provisioned to forward all incoming calls to a customer specific phone number. This can in one embodiment be a non customer changeable number except via an order. Depending upon the locality of the service the forwarding of calls can generate a local call a local toll call or a long distance call which can be invoiced to the RCF customer. Calls can be forwarded to a toll free service and in one embodiment do not carry a per call charge. RCF can carry a flat MRC.

When a customer requests multiple calls to be terminated at one time RCF paths can be ordered. Depending upon the number of paths ordered the number of calls that can be terminated simultaneously can be determined. Each path can carry a flat MRC.

Voice Messaging services can provide a customer the control of determining how communications are to be handled at their business. Voice messaging combined with local service can create a total business solution. Voice messaging can provide the customer with flexibility and total call coverage.

The foundation of voice messaging can be the voice mailbox which can provide for the repository of messages. These messages can be for example voice or fax. The voice mailbox can be configured according to the customer s needs with various levels or grades of service. Retrieval of messages can be performed through various methods that can range e.g. from a local to a remote and toll free access.

Voice messaging components take a basic voice mailbox and enhances it. Enhancements can include such features as for example broadcast services one number location services pseudo auto attendant dial out capabilities revert to operator fax on demand and informational services.

Voice messaging services can be broken down into three categories. The categories of voice messaging services can include integrated voice messaging stand alone voice messaging and enhanced voice messaging.

Integrated voice messaging can tie the customer s phone number with the voice messaging platform. The customer s caller needs to dial only one number in order to contact the customer. The integration can be accomplished via call handling features to the voice messaging platform such as call forwarding busy call forwarding no answer call forwarding variable and message waiting indication. Basic applications for this type of service can include private individual lines and multi lines and multi line hunt arrangements that can require call coverage. By using an integrated version of voice messaging the customer can also receive a revert to operator feature as part of the package.

This type of service can be application specific. A customer gives out only one number to its customers for them to reach it. If a customer does not what to answer the phone when a call is transferred it can still ring according to parameters set up by the call handling features in one embodiment.

Stand alone yoke messaging can provide customers with individual voice mailboxes. These mailboxes can be set up with their own phone numbers and need not be tied to a customer s phone number. Therefore in one embodiment they do not have revert to operator services and message waiting indication. These mailboxes can be useful to e.g. a sales organization which has employees which do not have an office with phone services.

Depending upon the application a pseudo integration type of service can be set up. By using call handling features calls can be forwarded to the phone number assigned to a voice mailbox.

An automatic call back ring again service can allow automatic return of the last incoming call i.e. whether answered or missed . If the number called back is busy automatic call back service can alert the user with a special ring when the user s line and the line the user is calling back are both idle. This feature can be assigned on an individual line basis. The ringback alerting interval can be varied from e.g. 24 to 48 seconds inclusive in e.g. 6 second increments. Automatic callback service can be activated before receiving another incoming call. Outgoing calls can be placed before activating automatic callback on the last incoming call. This service can work well with call waiting.

This second segment of Local voice is referred to as local calling. Local calling is the traffic that is within a LATA but does not constitute a long distance call. Depending upon the market that the service is being provided in local calling can be a for fee or free service.

A 3 way conferencing bridge can be created by the end user by choosing the conferencing feature from the enhanced services menu. The end user enters up to e.g. two additional phone numbers and is then connected by the bridge.

Dedicated Termination Service DTS allows long distance calls from the calling card to terminate to a Dedicated PVN site if applicable. Non PVN calls could terminate regularly over FGD trunks. The network can determine if the call can be terminated over its own facilities and if so rate it appropriately. DTS calls can be priced less than calls that terminate over FGD. A routing table allows the network to identify calls that originate from a calling card that has been assigned an associated terminating Trunk Group.

Audio conferencing can allow a customer to setup a call with two or more participants. The customer through an easy to use web interface can create a conferencing bridge.

This service can be available to all customers who sign up for the service. Because the call is being setup through a web interface conferences can be setup anywhere access to the Internet is available.

Internet hosting services can be provided over the network of the claimed invention. An Internet Services Provider ISP can use server and communications services including Internet access from the telecommunications network and can be billed for the usage. High speed connectivity can be provided as well as World Wide Web File Transfer Protocol FTP Gopher and other Internet hosting services.

Managed modem service is a service provided to users of communications services such as an ISP. Managed modem services provide modem services to subscribers of the ISP. As an ISP signs up new subscribers access can be provided to the subscriber over modems provided by a networking services provider NSP . Modems can be shared by a plurality of ISPs and economies of scale can be obtained by requiring a lower overall number of modems and associated communications network hardware. Other dialing services can be made available over the data network of the invention.

Network services can be provided co located with a customer. For example the telecommunications network carrier can provide TG AG and NAS access at the customer premises for such purposes as high speed modem access. By placing telecommunications network components on site at a customer location various advantages can be gained by the telecommunications provider and subscriber.

Access to IBM Systems Network Architecture SNA services can be made available over data network of the invention.

Telecommunications network can be used to deliver a plurality of new product and service offerings. For example new services include services can be configured via Internet worldwide web connection to telecommunications network . Additional service offerings include that billing options can be announced at the beginning of a call. Another new service enables the announcement of the cost of a call to be read at the conclusion of a telephone call. Telecommunications network also supports connectivity of native IP devices such as for example a SELSIUS phone. Additional new products and services include integration of native IP and unified PBX file server devices into telecommunications network . See for example customer net shown in . Attached to network are a variety or native IP devices . For example IP Client can be a personal computer capable of VOIP telephony communication including voice digitizing network interface card and transmission hardware and software. PBX File Server is a native IP device with hybrid data voice functionality such as for example PBX functionality with optionally collocated access gateway AG functionality for telephony access by phones and data services functionality such as for example file server functionality. Another new service enables messaging joined with find me type services.

In addition to the new services just described enabled by telecommunications network it should be noted that telephone calls over telecommunications network deliver call quality which is better than the standard PSTN. Telecommunications network also permits read reporting of call statistics and call volumes and billing information to commercial clients for example. Telecommunications network also permits dynamic modification over the route traversed by traffic via worldwide web access.

While various embodiments of the present invention have been described above it should be understood that they have been presented by way of example only and not limitation. Thus the breadth and scope of the present invention should not be limited by any of the above described exemplary embodiments but should be defined only in accordance with the following claims and their equivalents.

