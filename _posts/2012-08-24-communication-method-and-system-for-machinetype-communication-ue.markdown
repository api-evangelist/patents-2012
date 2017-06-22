---

title: Communication method and system for machine-type communication UE
abstract: A communication method and system for a Machine-Type Communication (MTC) User Equipment (UE) are disclosed. The method includes that: at least one MTC UE in an MTC UE group receives, based on group paging information received, broadcast information carrying group trigger information from an MTC server, wherein the group trigger information is used for triggering the at least one MTC UE in the MTC UE group; and the at least one UE communicates with the MTC server based on the group trigger information. In the disclosure, the group trigger information is broadcast to the MTC UE group through the broadcast information, so that a plurality of MTC UE in one group is triggered simultaneously, thus optimizing group triggering process, and reducing network resources occupied in the group triggering process.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09467820&OS=09467820&RS=09467820
owner: ZTE CORPORATION
number: 09467820
owner_city: Shenzhen, Guangdong Province
owner_country: CN
publication_date: 20120824
---
The disclosure relates to the field of communications and more particularly to a communication method and system for a piece of Machine Type Communication MTC User Equipment UE .

The Machine to Machine M2M means all technologies and methods for establishing connection between machines. The M2M idea appeared in the 1990s but it just remained at theory stage. After 2000 with the development of mobile communication technology it is possible to use the mobile communication technology to implement networking of machines. The M2M service appeared on the market in about 2002 and developed rapidly in the following years the M2M service becomes the focus of many communication device suppliers and telecom operators. At present people are outnumbered by machines around the world so a good market prospect of the M2M technology may be foreseen.

Research on application scenarios of M2M communication shows that providing the M2M communication on a mobile network has a potential market prospect. However the M2M service presents many new requirements to the system for enhancing competitiveness of the mobile network in this aspect it is necessary to optimize the existing mobile network so as to support the M2M communication more effectively.

The existing mobile communication network is designed mainly aiming at the communication between human and human the communication between machine and machine and the communication between human and machine are optimized insufficiently. Besides how to provide the M2M communication service at a low cost by the operators is also the key to success of the M2M communication deployment.

Based on the situation above it is necessary to research a solution that the mobile network supports the M2M communication the solution is required to reuse the existing network to the greatest extent and reduce influence of a lot of M2M communication on network and the complexity of operation and maintenance.

At present the telecommunications market competition is increasingly fierce the charge keeps plummeting the profit margin of the operators is declining and the communication market based on people is getting saturated so the M2M is a brand new development opportunity for the operators.

For using mobile network resources effectively the 3rd Generation Partnership Project 3GPP presents the MTC namely service of Machine to Machine communication and Machine to Man communication whose scope is far beyond the past Human to Human H2H communication the MTC is greatly different from existing H2H communication mode in access control charge security Quality of Service QoS service mode and other aspects.

In a 3GPP Evolved Packet System EPS architecture the EPS includes a radio access network e.g. a UMTS Terrestrial Radio Access Network UTRAN an Evolved UTRAN E UTRAN a GSM EDGE Radio Access Network GERAN and a core network an Evolved Packet Core EPC includes a Mobility Management Entity MME a Serving Gateway a Packet Data Network Gateway PGW and other network elements a General Packet Radio Service GPRS core network includes a Service GPRS Support Node SGSN and other elements the E UTRAN includes an Evolved Node B eNB .

MTC UE trigger is one of basic requirements for an MTC system concerns of the requirement are that for controlling communication of a piece of MTC UE a way of initiating poll by an MTC server can be adopted to communicate for communication initiated by the MTC UE sometimes the MTC server is required to poll data from the MTC UE. If the MTC server fails to inquire or an IP address of the MTC UE is not available the MTC server can use the MTC UE trigger to establish communication with the MTC UE. If a network cannot trigger the MTC UE the network reports the MTC server that the MTC UE trigger is failed and the MTC UE trigger is implemented in the 3GPP through control plane signalling.

The MTC UE trigger includes Mobile Originated MO and Mobile Terminating MT namely includes that the MTC UE sends or receives information.

For implementing effective transmission of an MTC UE trigger request a solution presented includes sending MTC UE trigger information through a T4 interface or sending MTC UE trigger information through T5 interface control plane signalling or sending MTC trigger information through a Gi SGi interface user plane. For the way of sending the MTC UE trigger information through the control plane signalling the MTC server sends the control plane signalling including the MTC UE trigger information to a network node the network node parses the MTC UE trigger information in the control plane signalling and then sends the MTC UE trigger information to a piece of UE. An MTC architecture in the 3GPP is shown in in a user plane an MTC application connecting an MTC user communicates with the MTC server through an Application Programming Interface API or directly communicates with a Gateway GPRS Support Node GGSN PGW Evolved Packet Data Gateway EPDG in a 3GPP network through the Gi SGi interface the MTC server communicates with the GGSN PGW EPDG through an MTCi interface the GGSN PGW EPDG communicates with the UE through a Radio Access Network RAN in a control plane the MTC server sends the control plane signalling including the MTC UE trigger information to an MTC Inter Working Function MTC IWF through an MTCsp interface or sends the control plane signalling including the MTC UE trigger information to a Short Message Service Service Centre SMS SC IP Short Message Gateway IP SM GW through an MTCsms interface the MTC IWF or the SMS SC IP SM GW sends the control plane signalling to the MME SGSN or a Gateway MSC For Short Message Service SMS GMSC or an SMS router or a Mobile services Switching Centre MSC or a Visitor Location Register VLR and then sends to the UE through the RAN wherein the MME SGSN can also acquire through a Gr S6a S6d interface the control plane signalling from a Home Subscriber Server HSS or a Home Location Register HLR .

A requirement for the MTC UE group is made in the 3GPP TS22.368 for example the MTC server wants to collect status information of multiple pieces of MTC UE including the system relates a piece of MTC UE to a single MTC group each MTC function based on group is applicable to each member in the MTC group an identity of the MTC group in the 3GPP network is unique.

The disclosure provides a communication method and system for a piece of MTC UE for at least solving the problem that a solution on how to trigger a group of MTC UE has not been presented in related are.

According to one aspect of the disclosure a communication method for a piece of MTC UE is provided including that at least one MTC UE in an MTC UE group receives based on group paging information received broadcast information carrying group trigger information from an MTC server wherein the group trigger information is used for triggering the at least one MTC UE in the MTC UE group and the at least one UE communicates with the MTC server based on the group trigger information.

Preferably the at least one MTC UE in the MTC UE group receiving based on group paging information received the broadcast information carrying the group trigger information from the MTC server includes that the at least one MTC UE determines that the group paging information is received by itself wherein the group paging information is used for indicating change of the broadcast information the at least one MTC UE detects based on the group paging information whether the group trigger information carried in the broadcast information is the one needed by itself if so the at least one MTC UE acquires the group trigger information from the broadcast information if not the at least one MTC UE discards the group trigger information.

Preferably the at least one MTC UE detecting based on the group paging information whether the group trigger information carried in the broadcast information is the one needed by itself includes that the at least one MTC UE detects based on a group identity ID carried in the group paging information whether the group paging information corresponds to the MTC UE group if so the at least one MTC UE detects based on a group ID carried in the group trigger information whether the group trigger information is the one needed by itself if not the at least one MTC UE discards the group paging information.

Preferably before the at least one MTC UE in the MTC UE group receives based on the group paging information received the broadcast information carrying the group trigger information from the MTC server the method further includes that the MTC server sends the group trigger information to a piece of access network equipment through a service node of the MTC UE group and the access network equipment which receives the group trigger information broadcasts the group trigger information to an area where the MTC UE group is.

Preferably the MTC server sending the group trigger information to a piece of access network equipment through the service node of the MTC UE group includes that an MTC IWF receives the group trigger information sent by the MTC server wherein the group trigger information includes at least one of the followings a group ID of the MTC UE group and a physical area corresponding to the group trigger information the MTC IWF updates the physical area in the group trigger information to one of the following identifiers a Tracking Area Identifier TAI a Router Area Identifier RAI a Location Area Identifier LAI and a cell identifier the MTC IWF inquires based on the group ID of the MTC UE group subscription information of the MTC UE group and the service node of the MTC UE group and the MTC IWF sends through the service node the group trigger information to the access network equipment.

Preferably the MTC IWF sending through the service node the group trigger information to the access network equipment includes that the MTC IWF sends the group trigger information to the service node in one of the following ways a T4 interface a T5 interface a Cell Broadcast Centre CBC and a Broadcast Multicast Service Centre BMSC and the service node sends the group trigger information to the access network equipment and sends the group paging information to the MTC UE group through the access network equipment.

Preferably the MTC IWF sending the group trigger information to the service node in one of the following ways the T4 interface the T5 interface the CBC and the BMSC includes that the MTC IWF sends through the T4 interface the group trigger information to the service node in form of short message the MTC IWF sends through the T5 interface the group trigger information to the service node in form of short message or dedicated control signalling the MTC IWF sends through the CBC the group trigger information to the service node in form of Cell Broadcast Service CBS and the MTC IWF sends through the BMSC the group trigger information to the service node in form of Multimedia Broadcast Multicast Service MBMS .

Preferably before the at least one MTC UE in the MTC UE group receives based on the group paging information received the broadcast information carrying the group trigger information from the MTC server the method further includes that a Packet Data Network Gateway PGW Gateway General Packet Radio Service Support Node GGSN receives the group trigger information sent by the MTC server wherein the MTC server and the PGW GGSN are directly connected through a Gi SGi interface or connected through a Service Capability Server SCS the PGW GGSN sends a Downlink Data Notification DDN to the service node of the MTC UE group through a Signalling Gateway SGW the at least one MTC UE receives the group paging information and establishes a Public Data Network PDN connection with the PGW GGSN wherein the MTC UE in the MTC UE group shares the PDN connection and the SGW sends the group trigger information to the MTC UE group through the PDN connection.

Preferably the broadcast information can be sent in one of the following ways Multicast Control Channel MCCH information CBS information and System Information SI .

Preferably the SI is a System Information Block SIB designed for the MTC UE and only the MTC UE monitors and reads the SI.

Preferably the service node of the MTC UE group includes at least one of the followings a Mobility Management Entity MME a Service General Packet Radio Service Support Node SGSN and a Mobile Switching Centre MSC .

Preferably the access network equipment includes at least one of the followings an evolved node B eNB a NodeB a Radio Network Controller RNC a Base Station Controller BSC and a Base Transceiver Station BTS .

According to another aspect of the disclosure a piece of MTC UE is provided including a receiving entity configured to receive based on the group paging information received the broadcast information carrying the group trigger information from the MTC server wherein the group trigger information is used for triggering the MTC UE in the MTC UE group and a communication entity configured to communicate with the MTC server based on the group trigger information.

Preferably the receiving entity includes a determining unit configured to determine that the group paging information is received by it wherein the group paging information is used for indicating change of the broadcast information a detecting unit configured to detect based on the group paging information whether the group trigger information carried in the broadcast information is the one needed by itself an acquiring unit configured to acquire the group trigger information from the broadcast information based on a condition that a detecting result is positive and a discarding unit configured to discard the group trigger information based on a condition that the detecting result is negative.

Preferably the detecting unit includes a first detecting subunit configured to detect whether the group paging information corresponds to the MTC UE group based on the group ID carried in the group paging information a second detecting subunit configured to detect based on a condition that a detecting result is positive whether the group trigger information is the one needed by itself based on the group ID carried in the group trigger information and a discarding subunit configured to discard based on a condition that the detecting result is negative the group paging information.

According to yet another aspect of the disclosure a communication system for a piece of MTC UE is provided including an MTC server an MTC IWF a PGW GGSN an MTC UE group a service node of the MTC UE group and a piece of access network equipment wherein the MTC server is configured to generate group trigger information the MTC IWF is configured to send the group trigger information through a T4 interface or a T5 interface or a CBC or a BMSC the PGW GGSN is configured to send the group trigger information through a user plane the service node of the MTC UE group is configured to send group paging information to the MTC UE group and send the group trigger information to the access network equipment 

the MTC UE in the MTC UE group includes a receiving entity configured to receive based on the group paging information received broadcast information carrying the group trigger information from the MTC server wherein the group trigger information is used for triggering the MTC UE in the MTC UE group and a communication entity configured to communicate with the MTC server based on the group trigger information.

By utilizing the broadcast information to broadcast the group trigger information to the MTC UE group the disclosure implements simultaneous triggering of multiple pieces of MTC UE in one group optimizes group triggering process and reduces network resources occupied in the group triggering process.

The preferred embodiments are described in conjunction with the drawings as follows. It shall be understood that the preferred embodiments described herein are only used to describe and explain the disclosure and shall not be construed as improper limitations on the same. The embodiments of the present application and the features of the embodiments can be combined with each other if there is no conflict.

An embodiment of the disclosure provides a communication method for a piece of MTC UE is a flowchart of a communication method for a piece of MTC UE according to an embodiment of the disclosure as shown in the flow includes Step to Step as follows.

Step at least one MTC UE in an MTC UE group receives broadcast information carrying group trigger information from an MTC server based on group paging information received wherein the group trigger information is used for triggering the at least one MTC UE in the MTC UE group.

In the related art a solution on how to trigger a group of MTC UE has not been presented. In the embodiment of the disclosure the broadcast information is employed to broadcast the group trigger information to the MTC UE group so that multiple pieces of MTC UE in one group are triggered simultaneously thus optimizing group triggering process and reducing the network resources occupied in the group triggering process.

Before the MTC server triggers the at least one MTC UE it is needed to page the at least one MTC UE first and for ensuring that the group trigger information received really corresponds to the MTC UE group it is needed to detect whether the group trigger information received is the one needed by the at least one MTC UE itself. The Step includes that the at least one MTC UE determines that the group paging information is received by itself wherein the group paging information is used for indicating change of the broadcast information the at least one MTC UE detects based on the group paging information whether the group trigger information is the one needed by itself if so the at least one MTC UE acquires the group trigger information from the broadcast information if not the at least one MTC UE discards the group trigger information.

For ensuring that the group trigger information received really corresponds to the MTC UE group the at least one MTC UE detecting based on the group paging information whether the group trigger information is the one needed by itself includes the at least one MTC UE detects based on a group ID carried in the group paging information whether the group paging information corresponds to the MTC UE group if so the at least one MTC UE detects based on the group ID carried in the group trigger information whether the group trigger information is the one needed by itself if not the at least one MTC UE discards the group paging information.

Before Step the method further includes the MTC server sends the group trigger information to a piece of access network equipment through a service node of the MTC UE group and the access network equipment which receives the group trigger information broadcasts the group trigger information to an area where the MTC UE group is.

An MTC IWF receives the group trigger information sent by the MTC server wherein the group trigger information at least includes one of the followings a group ID of an MTC UE group and a physical area corresponding to the group trigger information the MTC IWF updates the physical area in the group trigger information to one of the following identifiers a TAI an RAI an LAI and a cell identifier the MTC IWF inquires based on the group ID of the MTC UE group subscription information of the MTC UE group and the service node of the MTC UE group and the MTC IWF sends through the service node the group trigger information to the access network equipment.

Preferably the MTC IWF sending through the service node the group trigger information to the access network equipment includes the MTC IWF sends the group trigger information to the service node in one of the following ways a T4 interface a T5 interface a CBC and a BMSC and the service node sends the group trigger information to the access network equipment and sends the group paging information to the MTC UE group through the access network equipment.

Preferably the MTC IWF sending the group trigger information to the service node in one of the following ways the T4 interface the T5 interface the CBC and the BMSC includes the MTC IWF sends through the T4 interface the group trigger information to the service node in form of short message the MTC IWF sends through the T5 interface the group trigger information to the service node in form of short message or dedicated control signalling the MTC IWF sends through the CBC the group trigger information to the service node in form of CBS and the MTC IWF sends through the BMSC the group trigger information to the service node in form of MBMS.

The service node of the MTC UE group includes at least one of the followings an MME an SGSN and an MSC.

A PGW GGSN receives the group trigger information sent by the MTC server wherein the MTC server and the PGW GGSN are directly connected through a Gi SGi interface or connected through an SCS the PGW GGSN sends a DDN to the service node of the MTC UE group through an SGW at least one MTC UE receives the group paging information and establish a PDN connection with the PGW GGSN wherein the at least one MTC UE in the MTC UE group shares the PDN connection and the SGW sends the group trigger information to the MTC UE group through the PDN connection.

Preferably the broadcast information may be sent in one of the following ways MCCH information CBS information and SI.

Preferably the SI is an SIB specially designed for the MTC UE and only the MTC UE monitors and reads the SIB information.

The service node of the MTC UE group at least includes one of the followings an MME an SGSN and an MSC.

The access network equipment includes at least one of the followings an eNB a NodeB an RNC a BSC and a BTS.

For making the technical solution and implementation method of the disclosure more clear the process of implementation is elaborated below in combination with the preferred embodiments. The broadcast information in the following preferred embodiments is the SI the process of utilizing the group trigger information to trigger a group of MTC UE is described.

It can be seen from the above embodiments that a group of MTC UE may be triggered through the control plane or the user plane in the embodiments of the disclosure specifically the MTC IWF sends through the T4 T5 interface the group trigger information for triggering a group of MTC UE to the MME SGSN MSC the MME SGSN MSC which receives the group trigger information sends the group trigger information to an RAN node and sends the group paging information to the MTC UE group through the RAN node the RAN node which receives the group trigger information broadcasts through the broadcast information the group trigger information to the MTC UE group the PGW GGSN receives the group trigger information and sends the DDN to the MME SGSN the MME SGSN sends the group paging information to the MTC UE group the MTC UE group establishes a PDN connection with the PGW GGSN and the SGW sends the group paging information to the MTC UE group through the connection. Therefore the group of MTC UE may be triggered through the broadcast information without need of respectively sending trigger information to each MTC UE in the MTC UE group thus reducing quantity of sent network information and not influencing wireless capacity.

In this step the MTC server sets content of the group trigger information and sends the group trigger information to the SCS wherein the SCS is outside or in the 3GPP network the group trigger information at least includes a group ID of an MTC UE group which is used for uniquely identifying the MTC UE group needing to be triggered.

The SCS sends the group trigger information to the MTC IWF after authenticating the group trigger information received the MTC IWF inquires through the HSS HLR the subscription information of the UE and the service node of the MTC UE such as MME SGSN and MSC.

Step The MME SGSN MSC which receives the group trigger information sends the group trigger information to an RAN node wherein the RAN node is at least one of the followings an eNB a NodeB an RNC a BSC and a BTS.

Step The MME SGSN MSC sends through the RAN node the group paging information to at least one MTC UE in the MTC UE group.

The group paging information includes the group ID the MTC UE detects according to the group ID whether the group paging information is the one needed by it if not discard the group paging information if so turn to other steps. The group paging information is used for indicating to the MTC UE group that the broadcast information which includes the group trigger information changes and values of Page Frame PF and Page Occasion PO of the group paging information are got by calculating through the group ID or a group International Mobile Subscriber Identity IMSI or notified by the broadcast information.

Step The RAN node broadcasts the trigger information to the at least one MTC UE through the broadcast information.

The broadcast information is dedicated broadcast information namely the broadcast information specially designed for triggering the MTC UE group the broadcast information includes content of the MTC UE group trigger for example the AS SCS expects the MTC UE group which receives the trigger information to respond e.g. sending a status report immediately or sending a status report after a time .

The group trigger information is sent periodically the above broadcast period is sent to a target MTC UE group by the existing broadcast information.

Step The at least one MTC UE which receives the group paging information receives the group trigger information. The at least one MTC UE reads the group trigger information in corresponding resources and communicates with the AS SCS according to content of the group trigger information.

The present preferred embodiment describes a scenario that the MTC IWF sends group trigger information through a T4 interface and utilizes broadcast information to implement triggering of a group of MTC UE is an interaction flowchart of a communication method for a piece of MTC UE according to a first preferred embodiment of the disclosure as shown in the method includes steps as follows.

Step The MTC AS sets group trigger indication information and sends the group trigger indication information to the MTC IWF through the SCS .

In this step the AS is outside the 3GPP carrier network the SCS is in or outside the 3GPP carrier network and the MTC IWF is in the 3GPP network. The MTC IWF needs to authenticate the group trigger information after receiving it. Note that the group trigger information sent to the MTC IWF by the SCS at least includes a group ID of an MTC UE group and a physical area corresponding to the group trigger information i.e. in which physical areas the group trigger information is sent .

Step The MTC IWF sends the group trigger information to a Short Message Service Centre SMSC through a T4 interface.

The MTC IWF inquires based on the group ID in the group trigger information the HSS HLR of subscription information of the MTC UE group and information about the service node of the MTC UE group and adds the information about the service node of the MTC UE group to the group trigger information.

The MTC IWF generally needs to update a physical area in the group trigger information to one of the following corresponding identifiers a TAI an RAI an LAI and a cell identifier.

In this step the SMSC sends the group trigger information to the MME SGSN MSC in form of short message the MME SGSN MSC is the service node of the target MTC UE group that is the target MTC UE group registers in the MME SGSN MSC. The group trigger information is a short message and a target MTC UE identity in the short message is the group ID.

In this step the MME SGSN MSC may inquire through the HSS HLR a cell corresponding to the group ID and sends the cell identifier to the corresponding RAN node. The RAN node is the eNB the NodeB the RNC the BSC or the BTS.

In this step the group paging information is sent through the RAN node and is used for indicating to the MTC UE group that the broadcast information including the group trigger information changes.

The group paging information at least includes the group ID at least one MTC UE detects based on the group ID in the group paging information whether the group paging information is the one needed if not discard the group paging information if so turn to other steps. The values of PF and PO Page subframe of the group paging information are got by calculating according to the group ID or the group IMSI.

Step The RAN node broadcasts the broadcast information including the group trigger information to the MTC UE group.

In this step the RAN node broadcasts through the broadcast information the group trigger information to a cell where the target MTC UE group is wherein the broadcast information is dedicated system broadcast information namely the broadcast information aiming at the MTC UE group the broadcast information is sent by the RAN node periodically the above period is sent to the least one MTC UE through the existing broadcast information. The broadcast information includes content of the MTC UE group trigger for example the AS SCS expects the MTC UE group which receives the group trigger information to respond e.g. the MTC UE sends a status report immediately or sends a status report after a time .

Step The at least one MTC UE which receives the group paging information receives the group trigger information.

In this step the at least one MTC UE detects based on the group ID in the group trigger information whether the group trigger information is the one needed if so the at least one MTC UE reads the group trigger information and communicates with the AS SCS according to the content of the group trigger information if not discard the group trigger information.

The present preferred embodiment describes a scenario that the MTC IWF sends group trigger information through a T5 interface and utilizes broadcast information to trigger a group of MTC UE is an interaction flowchart of a communication method for a piece of MTC UE according to a second preferred embodiment of the disclosure as shown in the method includes steps as follows.

Step an MTC AS sets group trigger indication information and sends the group trigger indication information to an MTC IWF through the SCS . Specifically this step is the same as Step so it will not be repeated here.

Step The MTC IWF sends the group trigger information to the MME SGSN MSC through the T5 interface. Specifically the MTC IWF inquires based on the group ID in the group trigger information the HSS HLR of the information about the service node of the target MTC UE group in the present preferred embodiment the service node of the MTC UE group is the MME SGSN MSC.

Note that the group trigger information may be sent to the MME SGSN MSC through a short message or dedicated control signalling at this point the group trigger information is a short message or control signalling.

In the present preferred embodiment Step and Step are the same as Step and Step respectively so they will not be repeated here.

Step The RAN node broadcasts the broadcast information including the group trigger information to the MTC UE group. This step is the same as Step so it will not be repeated here.

Step The MTC UE which receives the group paging information receives the group trigger information. This step is the same as Step so it will not be repeated here.

The present preferred embodiment describes a scenario that an AS SCS sends group trigger information through a user plane and uses the user plane to trigger a group of MTC UE is an interaction flowchart of a communication method for a piece of MTC UE according to a third preferred embodiment of the disclosure as shown in the method includes steps as follows.

Step a MTC AS sets group trigger indication information and sends the group trigger indication information to a PGW GGSN directly or through the SCS .

In this step the AS may be directly connected with the PGW GGSN through the Gi SGi interface or through the SCS.

Step The PGW GGSN sends the group trigger information to the SGW the SGW sends DDN information to the MME SGSN.

Note that the SGW may simultaneously send the DDN to the MME and the SGSN according to network configuration information or send the DDN to one of the MME SGSN.

In this step the MME SGSN is the service node which receives the DDN information. The group paging information at least includes the group ID and the value of PF PO of the group paging information is got by calculating through the group ID or the group IMSI.

Step at least one MTC UE which receives the group paging information initiates a service request process and establishes a PDN connection with the PGW GGSN wherein the PDN connection is a shared connection that is the PDN connection includes a plurality of PDN connections to multiple pieces of MTC UE and multiple pieces of MTC UE belonging to a group share a PDN connection the same IP address and port .

Step The SGW sends the group trigger information to the at least one MTC UE through the PDN connection.

It should be noted that these steps presented in the flowchart of the accompanying drawings can be executed in a computer system like a group of machine executable instructions besides although a logical sequence is presented in the flowchart in some cases the presented or described steps can be executed in an order different from that described here.

The embodiment of the disclosure also provides a piece of MTC UE the MTC UE can be used for implementing the above communication method for a piece of MTC UE. is a structure diagram of a piece of MTC UE according to an embodiment of the disclosure as shown in the MTC UE includes a receiving entity and a communication entity . The structure is described in detail below.

The receiving entity is configured to receive based on group paging information received the broadcast information carrying the group trigger information from the MTC server wherein the group trigger information is used for triggering at least one MTC UE in an MTC UE group the communication entity is connected to the receiving entity and is configured to communicate with the MTC server based on the group trigger information received by the receiving entity .

Preferably the receiving entity includes a determining unit configured to determine that the group paging information is received by it wherein the group paging information is used for indicating change of the broadcast information a detecting unit connected to the determining unit and configured to detect based on the group paging information whether the group trigger information carried in the broadcast information is the one needed by it an acquiring unit connected to the detecting unit and configured to acquire the group trigger information from the broadcast information based on a condition that the detecting result of the detecting unit is positive and a discarding unit connected to the detecting unit and configured to discard the group trigger information based on a condition that the detecting result of the detecting unit is negative.

Preferably the detecting unit further includes a first detecting subunit configured to detect whether the group paging information corresponds to the MTC UE group based on the group ID carried in the group paging information a second detecting subunit connected to the first detecting subunit and configured to detect based on a condition that the detecting result of the first detecting subunit is positive whether the group trigger information is the one needed by it based on the group ID carried in the group trigger information and a discarding subunit connected to the first detecting subunit and configured to discard based on a condition that the detecting result of the first detecting subunit is negative the group paging information.

The embodiment of the disclosure also provides a communication system for a piece of MTC UE the communication system for the MTC UE may be used for implementing the above communication method for the MTC UE. is a structure diagram of a communication system for a piece of MTC UE according to an embodiment of the disclosure as shown in the communication system for the MTC UE includes an MTC server an MTC IWF a PGW GGSN an MTC UE group a service node of the MTC UE group and a piece of access network equipment . The structure is described in detail below.

The MTC server is configured to generate group trigger information the MTC IWF is configured to send the group trigger information through a T4 interface or a T5 interface or a CBS or an MBMS the PGW GGSN is configured to send the group trigger information through a user plane the service node of the MTC UE group is configured to send group paging information to the MTC UE group and send the group trigger information to the access network equipment the MTC UE in the MTC UE group includes a receiving entity configured to receive based on the group paging information received the broadcast information carrying the group trigger information from the MTC server wherein the group trigger information is used for triggering at least one MTC UE in the MTC UE group and a communication entity connected to the receiving entity and configured to communicate with the MTC server based on the group trigger information received by the receiving entity.

It should be noted that the communication system for the MTC UE described in the embodiment of device corresponds to the embodiment of method its specific process of implementation has been elaborated in the embodiment of method so it will not be repeated here.

In a preferred embodiment the communication system for a piece of MTC UE can also include the following entities or devices as shown in the system includes an AS SCS an MTC IWF a PGW GGSN and SGW an SMSC an MME SGSN MSC a radio access network node and a piece of MTC UE .

The AS SCS implementing a function of the MTC server is configured to generate the MTC group trigger information wherein the group trigger information includes a group ID of the MTC UE group 

the MTC IWF implementing a function of the MTC IWF is configured to select a triggering route and send the received MTC UE group trigger information through the T4 T5 user plane 

the PGW GGSN and SGW implementing a function of the PGW GGSN are configured to receive the group trigger information sent by the AS SCS and send the group trigger information received to the MTC UE through the user plane 

the SMSC is configured to receive the short message group trigger information sent by the MTC IWF and send the group trigger information received to the MME SGSN MSC 

the MME SGSN MSC implementing a function of the service node of the MTC UE group is configured to receive the group trigger information sent by the MTC IWF or the SMSC and send the group trigger information to the radio access network node the MME SGSN MSC is further configured to send through the radio access network node the group paging information to the MTC UE 

the radio access network node implementing a function of the access network equipment is configured to receive the group trigger information sent by the PGW GGSN and SGW or the MME SGSN MSC and send the group trigger information to the target UE through the broadcast information or user plane data the radio access network node includes at least one of the followings the BSC the BTS the RNC the NodeB and the eNodeB and

the MTC UE implementing a function of the MTC UE group is configured to receive the group paging information and the group trigger information and to communicate with the AS SCS according to the content of the group trigger information. The MTC UE is a group of MTC UE namely two or more than two pieces of MTC UE a piece of MC equipment may be either an MTC UE gateway or a single piece of MTC UE.

To sum up according to the above embodiments of the disclosure a communication method and system for a piece of MTC UE are provided. By utilizing the broadcast information to broadcast the group trigger information to the MTC UE group the disclosure implements simultaneous triggering of multiple pieces of MTC UE in one group optimizes group triggering process and reduces network resources occupied in the group triggering process.

Obviously those skilled in the art should appreciate that above mentioned entities and steps of the disclosure can be realized by a general purpose computing device and they can be centralized in a single computing device or distributed on a network composed of multiple computing devices optionally they can be realized by program code which is capable of being executed by the computing device so that they can be stored in a storage device and executed by the computing device or they are made into integrated circuit entities respectively or multiple entities and steps of them are made into a single integrated circuit entity to realize. In this way the disclosure is not limited to any particular combination of hardware and software.

The above is only the preferred embodiment of the disclosure and not intended to limit the disclosure for those skilled in the art the disclosure may have various modifications and changes. Any modifications equivalent replacements improvements and the like within the spirit and principle of the disclosure shall fall within the scope of the claims of the disclosure.

