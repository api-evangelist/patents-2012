---

title: Telecommunication networks
abstract: A mobile telecommunications network includes a core network and a radio access network. The radio access network has a network node that wirelessly communicates with a mobile terminal registered with the radio access network. The radio access network includes a controller that controls the use of network resources by the mobile terminal and processes control plane signaling. The controller includes an applicator that receives policy information and/or routing information from the core network and provides instructions to the network node to act in accordance with the received information. The network node includes an enforcer that enforces the instructions received from the controller so as to control whether the terminal uplink user plane traffic and control plane signalling messages are passed to the core network, routed to the controller, or duplicated and provided to both the core network and the controller.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09154994&OS=09154994&RS=09154994
owner: VODAFONE IP LICENSING LIMITED
number: 09154994
owner_city: Newbury, Bershire
owner_country: GB
publication_date: 20120625
---
United Kingdom Application No. 11 107 50.5 filed on Jun. 24 2011 United Kingdom Application No. 11 107 44.8 filed on Jun. 24 2011 United Kingdom Application No. 11 134 05.3 filed on Aug. 3 2011 United Kingdom Application No. 11 134 07.9 filed on Aug. 3 2011 and United Kingdom Application No. 11 13 859.1 filed on Aug. 11 2011 the entireties of which are incorporated herein by reference.

The present invention relates to a mobile telecommunications network including a core and a radio access network having radio means for wireless communication with mobile terminals registered with the network.

Recently a dramatic rise in sales of both smart phones and laptop data cards has resulted in a substantial increase in the amount of data communications passing through mobile telecommunications networks. This volumetric increase can also be attributed to enhancements made to the capabilities of the networks. In fact it has been reported that mobile data growth grew 30 percent over the course of the second quarter of 2009. The most popular use for mobile data was HTTP browsing although usage of HTTP streaming is growing considerably. Other mobile data uses include HTTP downloading and Peer to Peer P2P activities such as file sharing.

This ability to use the cellular networks for mobile data services such as Internet browsing is resulting in subscribers treating their mobile networks in much the same way as they treat their fixed networks. That is users are tending to expect the same service from the Internet irrespective of their access method. However mobile networks have a more restricted capacity and are more costly to operate as compared to fixed networks.

In this regard from the network operator s viewpoint as the mobile broadband traffic volume carried over 2G 3G and HSPA High Speed Packet Access networks continues to grow the cost of supporting this data volume is becoming more and more expensive based on the current network architecture and deployments. In fact access and data volumes are likely to rise faster than the revenue used to build and maintain the networks. This cost differential is exacerbated by one of the current business models being utilised whereby operators charge a flat rate for unlimited amounts of data.

The increased usage is also unfortunately likely to result in an increase of data traffic jams and hence a degradation of service for mobile users if not properly managed.

It has been proposed to control data heavy users by choking the bandwidth available to them when a maximum data volume limit is exceeded. Whilst this addresses the problem on an individual level it does not address the network capacity problem as a whole.

It is therefore apparent that mobile broadband is at a crossroads as networks and business models are strained by bandwidth demand that is unmatched by revenue generation.

These problems will only get worse with moves to position mobile data as a replacement for fixed DSL Digital Subscriber Line access and with the advent of higher radio access speeds with the proposed 4G LTE SAE Long Term Evolution System Architecture Evolution network. A large percentage of this traffic will consist of data which is destined for the public Internet a significant proportion of which mobile operators will not be able to add value to despite carrying the data on their own backhaul transport core transport or cellular core infrastructure.

In addition to the problems discussed above conventional mobile telephone communications networks have architectures that are hierarchical and expensive to scale. Many of the network elements such as the BTS routers BSC RNC etc are proprietary devices of one manufacturer often do not interface with devices from another manufacturer. This makes it difficult to introduce new capabilities into the network as a different interface will be required for devices from each manufacturer. Further conventional base stations are not capable of intelligent local routing or processing. Furthermore the capacity of existing networks is not always used effectively. For example many cell sites are under used whilst others are heavily used.

There is therefore a need to overcome or ameliorate at least one of the problems of the prior art. In particular there is a need to address the needs of both the network operators and the users in improving the provision of mobile broadband data services.

In one aspect the present invention provides a mobile telecommunications network including a network core and a radio access network having radio means for wireless communication with terminals registered with the network wherein the radio access network includes control means operable to control the use of network resources by said terminals wherein the control means is operable to process control plane signalling.

The control means may include an application programming interface API which provides a consistent interface to a multiplicity of applications hosted on the control means.

The control means may include an adapter e.g. another API operable to provide a consistent interface with the control means the adapter communicating with an element of the network core or radio means. The communications between the element of the core network and the radio means is generally proprietary. However the adapter enables standardised communications between the control means and the adapter so these communications can be of a standard form irrespective of the element type or manufacturer.

The radio means may comprise a base station and a controller thereof. In a UMTS 3G network the radio means may for example comprise a NodeB and RNC. In a GSM 2G network the radio means may comprise a BTS and a BSC. In a LTE 4G network the radio means may comprise an eNodeB.

The control means may include policy application means operable to receive policy and or routing information from the network core and to provide instructions to the radio means to act in accordance with the policy and or routing information.

At least one of radio means may include enforcement means for enforcing the instructions such that the enforcement means controls at least one of whether terminal uplink traffic is diverted from the radio means to the control means and duplicated to the control means. The mobile terminal traffic may be user plane traffic and or control plane traffic.

The control means may include means operable to interact with an element of the network core and or radio means to cause that element to route terminal downlink traffic to the control means. The downlink traffic may then be modified e.g. optimised by the control means before the downlink traffic is passed to the mobile terminal.

The control means may be operable to request and process radio resource information relating to a terminal from an element of the network core or radio means. The control means may configure interactions with a mobile terminal in dependence on the radio resource information. The control means may request that it is informed of the radio resource connected RRC state e.g. active state and idle state of a mobile terminal and or may cause the RRC state to be changed. The control means may use the radio resource information to cause the relocation of a mobile terminal to be delayed e.g. until a file download is completed.

The control means may be operable to request and process information from the network core relating to a terminal or bearer. The control means may request that the network core established modifies or remove radio bearers based on radio conditions of a mobile terminal. The control means may request that QoS profile associated with a user bearer is changed. The control means may request that the network core reports when a parameter is changed for a mobile terminal for example its IP address.

The control means may be operable to perform mobility management functions for a selected terminal registered therewith. These mobility management functions may be mobility management functions corresponding to those that are conventionally performed by the core network for example by a MME of the core. This may be advantageous for mobile terminals that are generally stationary such as mobile terminals forming part of a vending machine. Performing mobility management functions at the core network is unnecessary for stationary devices and is wasteful of communication resources. By moving the mobility management functions to the control means of the radio access network for selected devices some communications between the radio access network and the core are avoided.

According to a second aspect of the present invention there is provided a mobile telecommunications network including a network core and a radio access network having radio means for wireless communication with terminals registered with the network wherein the radio access network includes a plurality of control means operable to control the use of network resources by said terminals each associated with a respective other element of the radio access network and wherein when a terminal is handed over from a first of said elements to a second of said elements services provided by the control means associated with the first of said elements are selectively transferred so that they are provided by the control means associated with the second of said elements.

According to a third aspect of the present invention there is provided a mobile telecommunications network including a network core and a radio access network having radio means for wireless communication with terminals registered with the network wherein the radio access network includes control means operable to control the use of network resources by said terminals wherein when a terminal attaches to an element of the radio means the element is operable to advise the control means associated with element of the attachment of the terminal such that the control means is enabled to register with the network for providing services to the terminal. A user profile may be provided to the element as part of the attachment process. The user profile may indicate whether or not the control means is applicable to providing services to the user s mobile terminal.

According to a fourth aspect of the present invention there is provided a mobile telecommunications network including a network core and a radio access network having radio means for wireless communication with terminals registered with the network wherein the radio access network includes control means operable to control the use of network resources by said terminals and wherein the network further includes a gateway with which a plurality of the control means are registerable and which is operable to configure the control means registered therewith. For example the gateway may provide a list of applications and services which can be used by mobile terminals registered with a control means.

The control means may be registered as at least one of a controller for controlling the radio resources of a terminal served by the control means a traffic source on the user plane path and an information source for providing information relating to a terminal served by the control means. For example in a 3G network a control means located at the RNC may be a traffic source and a control means located at the NodeB may be an information source and in a 4G network a control means located at the eNodeB may be a traffic source and in information source.

The gateway may host an enterprise application which is operable to configure the control means registered therewith to provide specified information thereto. The requested information may include system load radio resource RR conditions mobile terminal location and mobility.

The gateway may be operable to store the provided information and to use this information to serve received requests for data. For example a plurality of received requests for data may all require the same information. The gateway may serve these plurality of requests by the stored information so that the information is only required to be obtained from the control means once thereby avoiding wasting network resources by transmitting identical information twice . The gateway may also process the information in order to serve requests for data. For example the gateway may calculate the arithmetical mean of a set of information to serve a request for data.

According to a fifth aspect of the present invention there is provided a mobile telecommunications network including a network core and a radio access network having radio means for wireless communication with terminals registered with the network wherein the radio access network includes control means operable to control the use of network resources by said terminals and wherein the control means is operable to receive a request for service from a terminal and to determine whether the control means should provide the requested service the control means being operable to return to the terminal an address which facilities access to the service at the control means or access to the service elsewhere in dependence upon the determination by the control means. The request for service may be a DNS lookup request. If the control means determines that it should provide the requested service it may return the IP address of the relevant application hosted on the control means. If the control means determines that is should not provide the service it may return an address that allows the service to be provided elsewhere such as via the network core. An element of the radio means does not need to analyse requests for service to determine how to route those requests the element may simply route the requests to the address provided and this routes the request to the appropriate destination. The determination of where a request should be serviced may depend of criteria discussed in the detailed embodiment such as whether content filtering or lawful interception functionality at the network core is necessary.

According to a sixth aspect of the present invention there is provided a mobile telecommunications network including a network core and a radio access network having radio means for wireless communication with terminals registered with the network wherein the radio access network includes control means operable to control the use of network resources by said terminals wherein the network core includes means operable to instruct the control means to selectively route received requests for service from a terminal to the core network without serving those requests for service. This is advantageous for example for a pre pay mobile terminal. If the user of the mobile terminal exhausts their credit the core network may instruct the control means via a gateway in the embodiment to no longer serve requests for service from that mobile terminal. Requests for service from that mobile terminal rather than being served by the control means are routed to the core network e.g. via a PDP context GGSN . This allows the core network to block the request for service or to divert the user to a credit top up server for example. If a user purchases further credit the core network will instruct the control means to again serve requests for service.

The control means may be operable to receive a copy of signalling messages sent between the radio means and a terminal and to forward information from the messages to the core network. The messages may be forwarded to an entity of the core network that performs Lawful Interception processing.

The control means may be operable to configure the forwarded information from the messages such that the core network can readily identify if the forwarded information should be analysed. The forwarded information may include a flag or field that enables filtering by the core network of information that require analysis for example Lawful interception processing . The forwarded information may be configured to include a header for this purpose.

According to a seventh aspect of the present invention there is provided a mobile telecommunications network including a network core and a radio access network having radio means for wireless communication with terminals registered with the network wherein the radio access network includes control means operable to control the use of network resources by said terminals and wherein the control means is operable to record details of content that it delivers to a terminal and to pass the details to the core network the details enabling the core network to access a copy of the content for analysis. This is advantageous when there is a central copy of content send by the control means. It avoids transmitting the content between the control means and the core unnecessarily. The analysis performed by the core may be Lawful Interception analysis.

According to an eighth aspect of the present invention there is provided a mobile telecommunications network including a network core and a radio access network having radio means for wireless communication with terminals registered with the network wherein the radio access network includes control means operable to control the use of network resources by said terminals and wherein the control means is operable to host an application and to selectively passes traffic relating to that application for analysis by the network core. The application may be classified according to the nature of traffic that is will produce. The analysis performed by the core may be Lawful Interception analysis. If an application is classified as likely to produce traffic that should be subject to Lawful Interception analysis the control means passes this traffic to the core network for such analysis. Applications which produce traffic that does not require lawful interception analysis include applications such as power utility meter gathering applications. For some applications such as games some of the data will require analysis such as voice and messaging data whereas other data such as video data will not require analysis.

According to a ninth aspect of the present invention there is provided a mobile telecommunications network including a network core and a radio access network having radio means for wireless communication with terminals registered with the network wherein the radio access network includes control means operable to control the use of network resources by said terminals and wherein the control means is operable to cache data relating to an application hosted thereby and includes means for temporarily restricting access to the cached data until the data has been analysed at the network core. The analysis performed by the core may be Lawful Interception analysis.

The present invention further provides a method of operating a mobile telecommunications network as discussed above and or below.

Key elements of a 3G mobile telecommunications network and its operation will now briefly be described with reference to .

Each base station e.g. Node B and Femto corresponds to a respective cell of the cellular or mobile telecommunications network and receives calls from and transmits calls to a mobile terminal not shown in that cell by wireless radio communication in one or both of the circuit switched or packet switched domains. The mobile terminal may be any portable telecommunications device including a handheld mobile telephone a personal digital assistant PDA or a laptop computer equipped with a network access datacard.

The nodeB or Femto can be considered to comprise two main parts a radio frequency part radio unit and a baseband part. The radio frequency part handles the transmission of radio frequency signals between the antenna of the nodeB or Femto and the mobile terminal and for converting radio frequency signals into digital baseband signals and vice versa . The baseband part is responsible for controlling and managing the transmission of the baseband signals to other components of the mobile telecommunications network.

In a macro 3G network the Radio Access Network RAN comprises Node Bs and Radio Network Controllers RNCs . The Node B is the function within the 3G network that provides the physical and transport radio link between the mobile terminal User Equipment UE and the network. The Node B performs the transmission and reception of data wirelessly across the radio interface and also applies the codes that are necessary to describe channels in a CDMA system. The RNC is responsible for control the Node Bs that are connected to it. The RNC performs Radio Resource Management RRM some of the mobility management functions and is the point where encryption is done before user data is sent to and from a mobile terminal. The RNC connects to the Circuit Switched Core Network through a Media Gateway MGW and to an SGSN Serving GPRS Support Node in the Packet Switched Core Network. In Node B is controlled by RNC across the lub interface. An RNC may control more than one node B.

The radio link between the Femto and the mobile terminal uses the same cellular telecommunication transport protocols as Node B but with a smaller range for example 25 m. The Femto appears to the mobile terminal as a conventional base station so no modification to the mobile terminal is required for it to operate with the Femto . The Femto performs a role corresponding to that of Node B in the macro 3G RAN.

The Femto would typically be configured to serve a Wireless Local Area Network WLAN located in a home or office in addition to GSM UMTS LTE networks. The WLAN could belong to the subscriber of the mobile terminal or be an independently operated WLAN. The owner of Femto can prescribe whether it is open or closed whereby an open AP is able to carry communications from any mobile device in the GSM UMTS LTE network and a closed AP is only able to carry communications from specific pre assigned mobile devices.

Conventionally in a 3G network macro or Femto the RANs are controlled by a mobile switching centre MSC and an SGSN Serving GPRS Support Node 5 of the core network. The MSC supports communications in the circuit switched domain whilst the SGSN supports communications in the packet switched domain such as GPRS data transmissions. The SGSN is responsible for the delivery of data packets from and to the mobile terminals within its geographical service area. It performs packet routing and transfer mobility management attach detach and location management logical link management and authentication and charging functions. A location register of the SGSN stores location information e.g. current cell current VLR and user profiles e.g. IMSI address es used in the packet data network of all mobile terminals registered with this SGSN. In since the embodiment is concerned with data transmission only the SGSN is illustrated as being in communication with RNC and AGW 4 across the lu interface. The RNC typically has a dedicated not shared connection to its SGSN such as a cable connection.

Communications between the AGW 4 and the SGSN are preferably IP based communications and may be for example transmitted over a broadband IP network. Further the connection between the Femto and the AGW 4 may use the PSTN Public Switched Telephone Network . Typically a DSL cable connects the AGW to the PSTN and data is transmitted there between by IP transport DSL transport. The Femto or AGW converts the cellular telecommunications transport protocols used between the mobile terminal and the Femto to the appropriate IP based signalling.

The femto may be connected to the AGW by means other than a DSL cable and the PSTN network. For example the femto may be connected to the AGW by a dedicated cable connection that is independent of the PSTN or by a satellite connection.

The SGSN is in communication with the GGSN Gateway GPRS Support Node across the Gn interface. The GGSN is responsible for the interworking between the GPRS network and external packet switched networks e.g. the Internet. The GGSN enables the mobility of mobile terminals in the networks. It maintains routing necessary to tunnel the Protocol Data Units PDUs to the SGSN that service a particular mobile terminal. The GGSN converts the GPRS packets coming from the SGSN into the appropriate packet data protocol PDP format e.g. IP or X.25 and sends them out on the corresponding packet data network. In the other direction PDP addresses of incoming data packets are converted to the mobile network address of the destination user. The readdressed packets are sent to the responsible SGSN. For this purpose the GGSN stores the current SGSN address of the user and their profile in its location register. The GGSN is responsible for IP address assignment and is the default router for the connected mobile terminal. The GGSN also performs authentication and charging functions. Other functions include IP Pool management and address mapping QoS and PDP context enforcement.

In turn the GGSN may route data via any applicable Value Added Service VAS equipment before data is forwarded towards its intended destination via the Internet . As an example of the functionality of the VAS equipment the traffic may be inspected for adult content before reaching the end user if this user is under 18 years of age.

For billing purposes in particular a PCRF Policy and Charging Rules Function apparatus is also provided in communication with both the SGSN and the GGSN .

The SGSN GGSN VAS and PCRF apparatus comprise the core network of the mobile telecommunications network.

Mobile telecommunications networks have an active state of communication with their mobile terminals and an inactive idle state of communication with their terminals. When in the active state as the mobile terminals move between different cells of the network the communication session is maintained by performing a handover operation between the cells. In the inactive idle state as a mobile terminal moves between different cells of the network the mobile terminal performs cell reselection to select the most appropriate cell on which to camp in order that the mobile terminal can be paged by the network when mobile terminating data is destined for that mobile terminal.

Conventionally the mobile terminal or network determines whether a handover cell reselection procedure should be triggered in dependence upon measurements of the radio signals of the cells in the region of the mobile terminal. A filter is applied to the signals either by the network or by the mobile terminal which calculates an average e.g. arithmetical mean value of these signals over a particular time period. This filtered average values of the cells are then compared with each other or with a threshold value. In dependence upon these comparisons cell reselection handover related procedures are triggered. This cell reselection handover process generally comprises taking radio signal measurements of neighbouring cells and comparing these to each other and to the radio signal of the current cell to determine which cell provides the best signal strength quality. Handover reselection to the best cell can then occur.

Generally calculations to determine whether to perform a handover from one base station to another base station are performed by the network whereas calculations whether to perform cell reselection are performed by the mobile terminal.

Data in a mobile telecommunications network can be considered to be separated into control plane and user plane . The control plane performs the required signalling and includes the relevant application protocol and signalling bearer for transporting the application protocol messages. Among other things the application protocol is used for setting up the radio access bearer and the radio network layer. The user plane transmits data traffic and includes data streams and data bearers for the data streams. The data streams are characterised by one or more frame protocols specific for a particular interface. Generally speaking the user plane carries data for use by a receiving terminal such as data that allow a voice or picture to be reproduced and the control plane controls how data are transmitted.

In addition to the elements and functions described above mobile telecommunications networks also include facilities for transmitting SMS messages. SMS messages are transmitted over the control plane only and not the user plane .

This architecture is what currently is being used to carry all packet data to and from mobile terminals. That is in today s implementation of the Packet data architecture user plane traffic traverses across all the network elements shown between the Node B or Femto on which the user is camped and the internet. That is all data is directed from the applicable RAN through the core network components SGSN GGSN and VAS before reaching the internet. All PS traffic accordingly follows the same path and therefore has the same network costs. All applications are processed on the client on the mobile device or on the server which is connected to the internet and the network core therefore acts like a bit pipe in the current architecture. For data where the mobile network operator cannot add any value by carrying it on its own backhaul transport core transport or cellular core infrastructure the core network such as data destined for the public internet without required intervention from the core network there is no benefit to routing this data via the core network.

However a large percentage of this traffic can be handled in a more intelligent manner for example through content optimisation Video Web content caching or locally routed or directly routing content to the public Internet. All these techniques reduce the investment required by a mobile operator to carry the data on its own backhaul and core transport or cellular core infrastructure.

In order to offer low cost packet data to support new services and to manage customer expectation a step change reduction in the end to end cost per bit is required.

Mobile operators want to reduce their packet data handling costs through alternate network architectures based on commoditised IT platforms breaking away from the traditional architecture based on their voice legacy. These new network architectures overcome the Access architecture issues of today

In order to successfully offer cheap packet data and be able to compete with the fixed broadband offers flat fee a solution is proposed which focuses on the reduction of the end to end cost per bit especially for Internet access service.

This enables mobile operators to reduce packet data handling costs by means of an alternative network cost model architecture which breaks out of the traditional network architecture and nodes and utilises lower cost transport networks to optimise the data flow.

In this regard shows a high level description of the architecture that may be adopted to deploy this on a 3G network.

According to this arrangement novel platforms control units means also referred to as SAVi for performing functions such as caching routing optimisation and offload return decision functionality are integrated into the network. This decision functionality may be incorporated in the radio architecture. In this regard the platforms may be incorporated into the NodeBs RNCs or exist as separate physical entities . It is these platforms that for example determine the path of communications originating from the mobile terminals.

The exact placement of the platform is not essential and for a macro 3G network it can be placed at or between the Node Bs and the RNCs and also between the RNCs and the SGSNs or any combination thereof . It would also be possible to place the platform at the GGSN although not the SGSN as this does not control user data only control data .

In the 3G Macro network the aim is to offload a high percentage of the macro network traffic from the core and transport IuPS Gn etc by diverting specific traffic type for certain user s class directly to the Internet.

Where the platform is located in the Node Bs or on the lub interface it may be possible to redirect the data from all the remaining mobile network elements e.g. the RNC SGSN GGSN and VAS for macro 3G and sending the data directly to the Internet . In a similar manner where the platform is located at the RNC or on the lu interface it becomes possible to redirect the data from the SGSN GGSN and the VAS . The alternative data route is preferably a DSL using ADSL.

It is also preferable to aggregate the alternative data routes for each cell where applicable. In this regard each cell will have at least one RNC and a plurality of Node Bs so where the decision blocks are situated at or in the vicinity of the Node Bs for instance there will be a plurality of links which should ideally be aggregated before being passed to the Internet . At the point of this aggregation there is preferably a further decision block which enables data to be returned to the legacy route. For instance a new policy rule may have been implemented which requires or enables previously offloaded data to be returned to the core network route. This new policy rule may be communicated to the return decision module by the core network policy module. In this returning of data is only shown to the VAS but the data may be returned to one or more of the other core network elements.

Each of the NodeBs is connected to the mobile network core through a Point of Concentration PoC . All traffic from the NodeBs which is to be routed through the core mobile network is routed to the PoC . This includes both user plane and control plane data. On the control plane level the PoC routes data to and from the SGSN and the GGSN . Control data is also sent to and from other core network components including the Lawful Interception Database LI DB DNS Server Policy Server including Charging rules and IT Network A and Home Location Register Home Subscriber Server HLR HSS which contains subscriber and device profile and state information .

User plane data is transmitted by the PoC to the SGSN and the GGSN . From the GGSN data is routed across a VAS node to the Internet . In 3G this is the standard data path from the mobile terminals to the Internet.

To implement an advantageous feature an alternative path on which to re route certain data to the internet is provided whereby each NodeB and Femto may be connected to a fixed line connection e.g xDSL which is directly connected to the internet . These xDSL connections may be made directly to the NodeB and or Femto or made to the NodeB Femto via other components such as the PoC . In the xDSL Network may be a third party network or may be a network owned or controlled by the owner of the mobile telecommunications network. By using such an alternative path radio capacity backhaul transport resource core transport resource cellular core network resources can be saved as well as improving performance and enhancing revenue for the mobile network operator.

As each Node B and or PoC is associated with a platform for each data packet request originating from a mobile terminal a decision at the platform is made as to whether the traffic may bypass the core mobile network entirely or may be passed into the core mobile network. The location at which the traffic is routed towards the internet is preferably at the platform however it may alternatively be routed out from the core network towards the internet at a different component. Traffic offloaded from the macro network is routed by the platform to the xDSL network by link the decision to offload this traffic may have been made at platform or although the decision is implemented at platform 

Preferably the Offload Return decision is dependent upon the type of data or user. To exemplify this feature of the embodiment is a flow diagram showing the steps taken when deciding how to route the traffic in the architecture of . For instance consider an NodeB receives a request to set up a data call from a user device which is camped on the NodeB at . Once the NodeB has identified the request as a data call and the type of traffic user rather than automatically routing the data traffic to the core network the data request is held at the NodeB at until a decision has been made as to how to route the data in particular whether to offload the traffic directly to the internet or whether to return the data through the core mobile network. Typically the signalling control plane for the connection will continue through the normal route but the user data traffic will be held at the NodeB this is possible by virtue of the separate user and control planes as shown in .

The decision as to whether or not to use the Core mobile Network to route the data traffic can be based on various aspects particularly relating to the properties of the data being routed and or status of the user routing the data.

The Mobile Network may add value to traffic by providing a number of services such as compressing the user data to speed up the data transfer while downloading if this functionality is not already supported by the platforms . These different services can be broken up into groups and provided by different entities e.g. this enables greater flexibility in the provision of the services such as the mandated Internet Watch Foundation IWF requirement which can only be supported by the mobile operator . The platforms therefore make a decision on whether to service the data locally through caching fetch the data from other node or from the internet via offload functionally or whether to route the traffic through the core network based on the applicability of one or more of the services to the traffic. That is platform decides when data traffic requires one or more of the services and when it can do without them.

It should also be noted that these services are ones that could be provided without using the core network. These are services that add value to the customer and which subscribers will pay for explicitly or implicitly .

Referring again to the platform decides at what to do with the traffic from coming for the network internet or orientated by the device . This decision may be made by interrogating certain servers or databases stored centrally within the core network which can compare the type of service type of user etc with criteria which identifies the type of action shall be considered e.g whether the traffic is suitable for offloading directly to the internet at from the NodeB or whether the traffic should be routed through the core at . Examples of some of the considerations used in influencing the decision of whether to offload the traffic are discussed below in more detail. The implementation of this data offload technique needs to be carefully considered as it places additional constraints on the network design.

The following is a non exhaustive list of examples of challenges that have to be considered when implementing the data offload technique 

Some specific examples of Customer Services that can be taken into account by the offload decision module include 

The Network Services that can be taken into account by the offload decision module are typically those that the network operator needs to manage its network. Some examples include 

Regulatory Services are services that are mandated by legislation and are typically provided to all traffic. Some specific examples of Regulatory Services that can be taken into consideration by the offload decision module include 

A further criterion that the platform module may consider is the priority of the customer. In this regard a network operator may wish to prioritise traffic across its network based on the priority level of the customer. For example a high value customer e.g. a corporate customer or a subscriber with on a high tariff contract may be given priority over a low value customer. In this situation a network may decide to offload lower value customers directly to the internet. This is related to the QoS criterion mentioned above although the QoS criterion is generally linked to traffic management to maintain a balanced network whereas the priority referred to can be used to ensure subscribers get a level of service commensurate with their service agreement.

The embodiment of is in relation to a 3G network. Embodiments of the invention are equally applicable to 4G LTE SAE networks.

The LTE SAE macro network includes eNode Bs which make up the RAN. The eNode Bs effectively combine the functionality of the node B and the RNC of the 3G network. These eNodeBs are the network components which communicate with the mobile communication devices. It is envisaged that the eNodeBs will be arranged in groups and each group controlled by a Mobility Management Entity MME and a User Plane Entity UPE .

The MME performs many of the mobility functions traditionally provided by the SGSN. The MME terminates the control plane with the mobile device. It is responsible for terminating NAS Non Access Stratum Signalling such as MM Mobility Management and SM Session Management information as well as coordinating Idle Mode procedures. Other responsibilities of the MME include gateway selection inter MME Mobility and authentication of the mobile device.

The UPE manages protocols on the user plane such as storing mobile terminal contexts terminating the Idle Mode on the user plane and PDP context encryption.

The platforms would operate in the same manner as described in relation to the 3G network. The platforms may be located at many different locations in the 4G network.

A more specific example of how the platform may be implemented is described in relation to . is a flow diagram illustrating a preferred method for deciding whether to offload data traffic to the internet. The decision structure is composed in a hierarchical form in order that certain types of user or data are always directed through the core network. The example of is described for a 3G network but it will be clear to those skilled in the art that these decisions could be applied to any type of radio access technology.

Once a PS HSPA data call or other connection is made and received at the Node B at a primary consideration by the platform at is whether the device is operating on its home network or whether it is roaming. If the device is roaming then all traffic is automatically routed through the core network. The reason for this is that the home network would want to guarantee the security and accurate billing due to different charging principle between home and visited operator of the user s traffic. The platform at will also consider other factors such as what application types running on the mobile terminal require connections. If the mobile device is operating on its home network at or if the applications do not require a connection to the core network the platform considers secondary offloading criteria at . Examples of secondary criteria may include the functions required by the device the radio bearer currently used by the device the APN or the priority level of the customer identified for example through IMSI IMEI or the target subscriber. If the offloading criteria are met at the decision moves to the tertiary criteria otherwise the traffic is not offloaded.

At the system checks the mobility of the user. If the user is moving he is considered not suitable for offload due to an expected interruption delay of the user data when moving between source and target cell.

Finally at the system conducts a contents and policy check to confirm whether the user is suitable for offload. If it is determined that the user is suitable for offload to the internet the eNodeB offloads the traffic to the internet at . If it is determined that the user is not suitable for offloading to the internet at then the procedure returns home at . A connection is provided by a network core in a conventional way and the tests of the flowchart shown in are repeated periodically to determine whether offloading directly to the internet becomes possible subsequently.

If the device is determined to be roaming at step then the device is not offloaded directly to the internet but remains connected via the network core in a conventional way at . Similarly if the offloading criteria are not met at steps the mobile device remains communicating via the network core in the conventional way again at .

The hierarchical decision method is useful because it reduces the number of challenges across the network. It will be evident to those skilled in the art that different hierarchical structures will be appropriate for different networks different conditions etc and that the example of is just one way the decision could be made.

For instance whilst arrangements have chiefly been described in relation to transmitting data traffic from a mobile terminal to a data network the principles may also be applied to transmissions from a data network towards a mobile terminal.

In the arrangements described above the decision regarding the route is said to be made at call set up. However it should be appreciated that a decision to change the routing of data may be made at the beginning of a communication session for example establishment of a PDP context or during a communication session. The routing of data may change several times during a single communication session. For example when a communication session is initiated it may be detected that the user is not moving in which case a decision will be made to offload the data over the alternative data route. Subsequently it may be detected that the user is moving and at this point a decision may be made to beginning routing data for the communication session via the mobile network. During the communication session the mobile terminal may become stationary for a prolonged period of time again and at this time a further decision may be made to send subsequent data during the communication session via the alternative data route. Subsequently again the user may then attempt to access age restricted content and it will be detected that parental control is required. In response for the requirement for parental control a decision may be made to redirect subsequent data during the Communication session via the core network so that core network parental controls can be applied.

It is to be appreciated that the present embodiments of the invention are to be distinguished from HSDPA offload a technique used on the lub interface between the Node B and the RNC. HSDPA offload which serves to separate data traffic from voice traffic so that non real time data traffic is sent down a less expensive backhaul to complement or replace the expensive E1 T1 TDM backhaul link between the two. Once this diverted traffic reaches the RNC however it is returned to the cellular and transport core networks and there is no differentiation made based upon data traffic type.

In the arrangement described above the platform primarily handles data offload decisions. As will be described below the platform can perform may other functions.

Embodiments of the invention in which the Radio Access Network controls the use of resources by mobile terminals will now be described.

As discussed above a mobile telecommunication network is modified by the introduction of a platform . Such a platform or control unit means also referred to as SAVi is shown in more detail at and which includes three principal parts soft nodes physical transport layer network functions and services application layer .

The platform communicates with the radio frequency RF part radio unit of a base station such as a NodeB . The soft nodes of the platform comprise components such as a soft NodeB soft BTS soft eNodeB and soft RNC and soft SGSN GGSN . The soft nodeB provides functions equivalent to the baseband part of a conventional NodeB in a 3G telecommunications network. The soft BTS provides baseband functions equivalent to the baseband functions of a BTS in a conventional 2G mobile telecommunications network. The soft enodeB provides baseband functions equivalent to the baseband functions provided by a conventional enodeB in a 4G mobile telecommunications network. The platform may therefore communicate with the radio frequency part of a 2G 3G or 4G base station and provide appropriate baseband services for 2G 3G or 4G technologies or indeed for other technologies . A 3G mobile terminal that wishes to obtain telecommunication services from the mobile telecommunications networks connects wirelessly to the radio frequency part of a NodeB. Baseband functions may be provided either by a baseband part of the conventional NodeB or by the soft NodeB forming an element of the soft node part of the platform . For example the soft NodeB may receive radio measurements from the radio frequency part of the NodeB to which it is connected and may provide these radio measurements to other elements of the platform .

The network functions part of the platform includes modules for performing functions similar to those performed by the core network of a mobile telecommunications network such as billing location tracking and the radio resource management RRM . The network functions may further comprise an offload decision module that performs a function similar to the offload decision modules and described above. The network functions part may further comprise a caching function and Content Delivery Network function .

The network functions parts of the platform provides an Application Programming Interface API framework to the services part of the platform . The services part of the platform supports a plurality of applications etc.

The network functions fall into three main categories those that enable the network operation e.g. charging O M those that support service operation e.g. Location and those that optimise the usage of the network by certain applications and services e.g. Caching Video Optimisation .

The applications supported on the Platform are the entities that supply or demand the flow of data on the network akin to a server on the internet e.g. gaming server navigation server.

The API is implemented by a software program running on the network function part which presents a novel standardised interface for the applications etc of the services part . The novel standardised API provides a consistent interface defining communication protocols ports etc. Full details of the API may be published to allow a multiplicity of applications to be developed for the platform by multiple developers. This should be contrasted with prior art arrangements where each component of a mobile telecommunications network such as BTS BSC RNC SGSN etc is proprietary and tends to have a unique interface meaning that a different application must be written for each node of a conventional network.

The applications etc may provide services to users of the telecommunications network by co operating with other parts of the platform .

The details of the use of each application used by the a user of the mobile telecommunications network is stored in an application context container. The Application context contains application names protocol used to carry such application their characteristics that are measured reported over period of time and some statistical information about these applications volume number of users using these applications etc. .

As shown in a platform may be provided at each base station of the mobile network where it is connected to the radio frequency part of the base station NodeB in forming an access node . Platform may also be provided at the RNC item in where it forms a gateway . The access node and the gateway are both configured to communicate directly with the network core for example comprising the SGSN GGSN and VAS as shown in . The access node and gateway may also be connected to the internet for direct internet access via direct links and respectively such that at least a portion of the core network is bypassed in the manner described above.

The steps performed when a mobile terminal is activated at a NodeB at the Femto or at the Access Point AP of the network which includes the novel platform will now be described with reference to . At step A the mobile terminal UE is activated within the coverage area of a particular NodeB at the Femto or at the AP. The access part of the NodeB at the Femto or at the AP communicates information from the mobile terminal to the platform associated with the NodeB at the Femto or at the AP. At step B the platform then allocates the baseband NodeB at the Femto or at the AP function and the RNC or BRAS Broadband Remote Access Server function either at access node at the NodeB at the Femto or at the AP site or at the gateway at the RNC or BRAS site of the network or even from neighbouring nodes that have spare resources to pull. The decision as to whether the RNC or BRAS function is allocated at the platform of access node or the gateway node may be made depending on various criteria including 

Upon allocating the baseband NodeB at the Femto or at the AP and the RNC or BRAS function the NodeB at the Femto or at the AP may allocate the mobile terminal to a particular carrier dedicated to the RNC or BRAS function.

Once the RNC or BRAS function is allocated to either the access node or the gateway at step C other functions performed by the platform at the access node or other access node and the gateway or other gateway are allocated to the mobile device. All other platform functions may be provided by the platform where the RNC or BRAS function is allocated to the mobile terminal. However a platform at a different location to that which provides the RNC or BRAS function to the mobile terminal may provide some or all other functions.

At step D the platform which is allocated the RNC or BRAS function is provided with a Common ID message from the core network .

At step E this message is used by the platform to look up the complete subscription information for the mobile terminal as well as the resource requirements QoS of the services required and negotiated PDP context this information being provided by the core network .

The subscription information relating to the device that is obtained from the central nodes e.g core network is used to allocate the other functions at access node and or the gateway in dependence upon various factors including 

As mentioned above a single mobile terminal may have platform functions applications allocated on a plurality of platforms. Generally when a mobile terminal is near stationary it is most efficient for its functions applications to be served from an access node i.e. distributed whereas mobile terminals with greater mobility or lower anticipated cell hold times will be most efficiently served by having fewer or no functions applications served from the access Node and more or all functions applications served from a gateway i.e. centralised . The assignment of functions applications to a mobile terminal between an access node and a gateway will also depend upon the characteristics of the service type provided by the application for example the average IP session duration the popularity of the particular application the average mobility of mobile terminal using the service provided by the application etc .

Traffic management may be performed at the access node where there is access to real time radio information from the radio frequency part of the NodeB the Femto or the AP serving the mobile device.

Centralised Radio Resource Management RRM may be provided at the gateway and maintains performance across different access modes which may have different radio access technologies frequency bands coverage etc. The RRM function of the platform of the gateway may obtain information regarding radio traffic management from each access node to dynamically position subscribers to particular radio technology. This technique will be used to allocate network resources based on the resource availability application used and user mobility For example the traffic management information may be provided by the soft NodeB Femto or AP of the platform at the access node . This soft NodeB obtains radio information relating to the mobile terminal from the radio frequency part of the NodeB to which the mobile terminal is wirelessly connected.

For a particular mobile terminal functions provided by an access node and gateway may be coordinated to work together in an advantageous manner i.e. a hybrid or distributed arrangement . For example the gateway may set operating limits or ranges within which functions performed by the access node may be performed without reference to the gateway . When the functions move outside the ranges set control of those functions may be passed to the gateway .

Further the access node and the gateway may cooperate to advantageously optimise content delivery to a mobile terminal.

The optimisation of content delivery will now be described with reference to of the drawings. Content may be optimised at gateway and at an access node . The gateway may serve multiple access nodes and my distribute content to those multiple access nodes for onward transmissions from each of those access nodes to a mobile terminal via the radio frequency part of NodeB the Femto or the AP serving that node. Radio quality measurements are reported by the mobile terminal to the access node at regular intervals such as 2 millisecond intervals. Radio quality measurement relating to that mobile terminal are transmitted between the radio frequency part of the NodeB the Femto or the AP serving the mobile terminal to the access node at regular intervals such as between 2 and 10 millisecond intervals. These radio measurements are received at the soft nodes and are passed to functions e.g. to QoS function for analysis . These radio frequency measurements from the mobile terminal and the NodeB are reported by the access node to the gateway e.g. to QoS function of the gateway for analysis at regular intervals such as intervals of between 1 and 10 seconds. The gateway may receive radio information from multiple access nodes . The radio measurements received by the gateway may be analysed over a relatively long period such as between 1 and 2 minutes. The radio quality measurements may be averaged for example the arithmetical mean of the radio quality maybe determined over this time period. The transmission of content from the gateway may then be optimised according to this calculation. Where the content is distributed by the gateway to a plurality of access nodes the content distribution will be based on the analysis of the radio quality indicators from all of the access nodes . The analysis may consider the maximum or peak radio performance over the time period of between 1 and 2 minutes.

When the content is received by each access node the access node then distributes the content to each mobile terminal. This distribution is optimised based on real time network mode and mobile terminal specific radio link quality as determined over a period of for example between 1 and 10 milliseconds. That is content delivered to a mobile terminal that has high radio link quality may be optimised in a different manner to a mobile terminal that had poor radio link quality.

The co operation between access nodes and gateways may further enhance the distribution of content in a manner now to be described with reference to .

When a mobile terminal requests a particular content item this request is transmitted to the access node serving that mobile terminal assuming that this is the first request for this content item to the access node the access node passes this request to the gateway serving the access node . Assuming that this is the first request for this content item from the gateway the gateway retrieves the content from a content server. The content is then provided by the content server to the gateway and from there is distributed to the access node and onwardly to the requesting mobile terminal. Advantageously the gateway maintains a record of content items that are requested frequently. When a content item is determined by the gateway to be requested frequently this is stored in a cache associated with the gateway which may be the cache of the platform . Subsequent requests for that content item from access nodes to the gateway can then be serviced by retrieving the content item from the cache and distributing the content item to the requesting access node and thus avoiding the need to request the content from the content server.

The gateway may be further configured to identify popular content items that are likely to be requested by a large number of access nodes . When it is determined that a content item is popular the gateway may push these content items to each of the access nodes associated therewith so that this content is hosted at the access node using Content Delivery Network CDN function of the network functions of the gateway and the access node . The content is then available at the access node for transmission to any mobile terminal that requests it without having to retrieve this content from the gateway or the content server. Advantageously the distribution of such content items is performed in a manner which takes into account the capacity or the congestion of the link between the mobile terminal and the gateway and the nature of the content. For example typically a link between a mobile terminal and the gateway may experience very little usage and congestion in the early hours of the morning. The content item can be advantageously transmitted in between the gateway and the access node at this time when there is spare capacity. The gateway will determine whether the content item is suitable for transmission on this basis for example by taking into account a number of times that the content item has been requested the size of the content item and the storage space at the access node . If a content item is relatively small and is time critical such as news headlines then such a content item may be distributed frequently throughout the day as such content is not suitable for transmission once a day at early hours of the morning as it becomes quickly out of date.

The procedures performed when a mobile terminal moves between cells in the mobile telecommunications network will now be described with reference to . In the conventional manner at step A when the mobile terminal moves to the edge of its current serving cell the radio measurements reported from the mobile terminal and the radio frequency part of the NodeB the Femto or the AP serving that mobile terminal are used by the core network to determine when to perform a handover and to which target cell the handover should be performed. When the best target cell has been identified handover to that target cell from the serving cell it is performed at B in a conventional manner.

At step C selected platform functions may be relocated from the source access node that served the old cell to the destination access node that serves the new target cell .

When the source and destination access nodes are served by the same gateway only base station function such as soft NodeB functions may be relocated to the destination access node.

The relocation of functions of the access nodes is performed independently to the radio handover so for some time after the radio handover the source access node continues to serve content to the mobile terminal through the destination access node. The routing of data packets for the 3G network between the destination and the source access nodes may be performed using an lu interface between the RNC or BRAS function of the destination access node and the SGSN GGSN function of the source access node. Alternatively the routing of data packets between the destination and the source access nodes can be completed by the SGSN GGSN function of the destination access node connecting directly to functions of the source access node through an IP interface.

After handover has been completed at step B the access node controlling the mobile terminal may be relocated from the source access node to the destination access node in coordination with the gateway. the standardised handover decisions mainly based on coverage quality power interference etc. for 2G 3G LTE fixed network are used to move the mobile from one node or system to another.

However the platform introduces new opportunity to make the handover decision based on type or characteristics of the certain application type of user and the QoS requirements.

The timing of the relocation of access node functions from the source to destination platform may be dependent on the following 

At step D optionally some functions will be reallocated from the access nodes to the gateway. For example if the destination access node is heavily loaded and is congested or has a lower capability then the source access node or the mobile terminal is determined to be very mobile it may be advantageous to transfer functions to the gateway. Functions are reallocated from the access node to the gateway by for example a Serving Radio Network Subsystem SRNS relocation between the RNC function of the access node and the gateway. Alternatively the functions may be reallocated by performing a radio reconfiguration of user connection to the mobile terminal.

The reallocation of functions from an access node to the gateway may be performed at call communication sessions set up. At call communication session set up further subscriber information will be provided which may be used by the access node or gateway to be determine whether it would be advantageous to reallocate functions from the access node to the gateway. Reallocation of functions from the access node to the gateway may be performed during an active connection when a requirement of the communication sessions has been modified or where the required resource is not available at the access node .

According to the same principles applications may be re located or distributed between access nodes and for gateways to provide optimised application delivery best use of the communication resources.

As mentioned above information about each application used by the user at the mobile terminal is stored in an application context. The application context is shared between each access node and gateway that control the user connection for that mobile terminal. One of the access nodes gateways will be the master for that particular application and that will also be the master of an application specific record in the application context. The application context is advantageously periodically synchronised between the access node and the gateway .

The application information is the application context specific to a particular mobile terminal and this is passed between access nodes and gateways during reallocation for a mobile terminal enabling the application to be seamlessly passed access nodes gateways avoiding impacts to the user experience.

Radio measurements received from the radio frequency part of the NodeB the Femto or the AP serving the mobile terminal are passed to the soft nodes of the platform of the access node or gateway serving the mobile terminal and are passed to the network functions of the platform which then distributes the measurements to where necessary within the platform . The platform has access to the subscriber information from the core network which allows the network functions to deliver data traffic in a manner that is optimised for radio conditions as indicated by the radio measurements. The data traffic may also be optimised according to the subscription of the user of the mobile terminal available radio resource mobile terminal capability and or for the class of the terminal e.g. access technologies used . This optimisation allows bandwidth usage to be balanced with customer experience. The subscriber information may include information about the price plan of the user of the mobile terminal. The mobile network operator may track the type of application used by the user the total data usage of the user and may differentially target radio resources the highest data value stream of users.

By hosting applications in the services part of the platform the access node or at least the gateway the point of the network that is aware of the application being used by the user of the mobile terminal closer in the link between the mobile terminal and the core network to the NodeB serving the mobile terminal. This enables the sharing of network resources to the most appropriate data streams such as the most profitable data streams. Such awareness of the application to which a request for data transmission relates allows the use of low value data streams such as peer to peer file sharing to be allocated only limited bandwidth so that remaining bandwidth can be targeted to particular users. In the uplink transmission of data can be controlled by the access node or gateway hosting the application to control data flow appropriately before data is onwardly transmitted towards the core of the network which was not possible with conventional arrangements .

As mentioned above a novel API is provided which defines the language that each of the software modules of the platform use to communicate to coordinate to optimise application delivery to users. The platform negotiates which each application the specific resource and performance requirements based on the application characteristics allowing the application to directly communicate the scheduling performance requirements rather than using a predefined set of quality of service parameters. This negotiation between the platform and the applications is facilitated by the API.

The API may also facilitate the provision of radio link quality information e.g. from QoS function to applications .

The API may further enable the platform to control use of the applications e.g. to allow disallow or adapt the applications.

By way of example the application may be a Voice over IP VoIP application. The nature of Voice over IP communications is that there is a virtually continuous succession of small data packets in which voice data is communicated. The voice data must be communicated with no or minimal latency in order that a two way conversation can be performed successfully. The Voice over IP application is able to compress voice data before transmission using a variety of techniques CODECS. The compression techniques CODECS may range from a relatively low compression technique which provides high quality voice reproduction but requires a large bandwidth to a much higher compression technique which provides reduced voice quality and which requires a much lower bandwidth.

The API is operable to provide details of the application characteristics to the network functions part of the platform . This makes the network functions part of the platform aware of the characteristics of the application. In the present example as the application is a Voice over IP application the network functions part may be made aware that the application will tend to transmit continuous successions of small data packets that require transmission with no or low latency. The network function may then be configured appropriately.

The API may further be operable to allow the network functions part to communicate radio link quality information to the application . For example when the network functions part received information regarding the application characteristics via the API it may allocate radio link resources to that application . This allocation of radio link resources may be communicated by the network functions part to the application via the API . The application may then select an appropriate compression technique CODEC in dependence upon the radio link quality available. During a Voice over IP call the available radio link quality may be communicated regularly from the network functions part to the application via the API to allow the application to vary the compression technique CODEC used in accordance with changes to the radio link quality.

The network functions part may control how the applications work via the API . The network functions part may allow disallow or adapt the applications hosted in the services part of the platform . For example the network functions part may require the Voice over IP application to use a particular compression technique CODEC if radio link bandwidth is restricted.

Another example of how the network functions part may advantageously provide radio link quality information to an application via the API is when the application is a gaming application used by several users. If the radio link quality information received by the application indicates that bandwidth is restricted the application may adapt is communications to the users such that latency of the communications is increased uniformly for all of the users so that they all experience the same delay in order that each of the users is provided with the same gaming experience.

In the embodiments described the devices that connect to the platforms are mobile devices that connect to the platforms via the radio access network of a mobile cellular telecommunications network. It should be appreciated that non mobile fixed devices may be connected to the platforms for example by a wired or cable connection.

The control means is responsible for allocating the service instance for each UE based on the UE locations and the control means capacity capability and available resources to host another instance of a service.

For certain low popularity services or where the available serving control means capacity or capability is limited the service can be hosted from a central control means or from a neighbouring distributed control means.

For some services functions where the source and destination client applications are in the same geographical region being served by the same site e.g. BTS location or site cluster e.g. finite number of sites the access node gateway ensures that the server for the service is located close to both users and the traffic is routed between the users within the site.

An alternative representation of the platform is shown in . The platform includes a platform core which communicates based on two sets of APIs 

The Platform includes common network functions Software such as Scheduling Routeing Billing accounting security and Policy functions which allow the architecture to offer seamless experience across the network. The Platform will provide capability to meet the Lawful Intercept LI requirements.

The Adaptors translate the Vendor specific implementation on the 3GPP LTE nodes such as eNB BBU RNC SGSN GGSN P GW and MME to common and open interface to the environment of platform .

The Adaptor for each 3GPP LTE node such as eNB BBU RNC SGSN GGSN P GW and MME is responsible for ensuring communication between the Network API and 3GPP node is secure.

The Platform provides the capability for some Applications hosted in the Platform to be contacted remotely from the platform .

Logically control and data traffic interfaces control plane and user plane between the physical manifestations of the platforms exist independent of the underlying 3GPP LTE network nodes . These interfaces will require to be made secure through functionality included within each platform .

The Platform also provides the capability for hosted Network and Service Applications on different platforms to communicate and pass data in a secure manner without mandating security to be provided by the application .

In contrast to the arrangements described above in this implementation the platform may handle both control and data traffic interfaces control plane and user plane rather than just the data traffic user plane. Further in contrast to the arrangements described above the nature of the gateway may be different. In the implementation described hereinafter the gateway may be located other than at the RNC. For example the gateway may be located at the SGSN GGSN VAS or PCRF apparatus or in any part of the network core or RAN. In the implementation described hereinafter the gateway may be considered to be an interface between the platforms at the access node and the core network rather than part of the control means .

When the platform environment is introduced into a mobile network it means that traffic can be inserted hosted or created in the data path between GGSN and UE potentially impacting the operation of existing core systems such as charging policy enforcement LI from other core network components Charging rules and IT Network A Policy Server and including the Lawful Interception Database LI DB see which need to be replicated.

The Network API between the platform and the 3GPP nodes has to perform certain functions which are important to the operation of the platform system. The basic set of functionality is described in this section.

When the UE transitions from PMM Idle to PMM Active state the 3GPP core network passes the UE IMSI to the Radio Access Network. The 3GPP system should treat this as a trigger to inform the platform system that a User has arrived on the 3GPP node.

In Rel 8 of 3GPP a new parameter called Subscriber Profile ID for RAT Frequency priority is included and passed to the Radio Access Network alongside the UE identity. The parameter is operator configurable and is stored in the HLR passed to the SGSN as part of the Subscriber context. The Access network is configured by the operator to understand how to act for each parameter.

It is proposed that the three most significant bits MSB of this parameter is used to determine whether the platform is enabled for a specific UE and provide a pointer to the default platform configuration to be used for this device before specific UE specific configuration is available.

If the three MSBs of the Subscriber Profile parameter are set to 000 then the 3GPP RAN understands that it should not inform platform of the presence of this UE if the three MSBs are any other value then the 3GPP passes the IMSI and the three MSBs of the Subscriber Profile to the platform the User Arrival Notification procedure on the Network API .

The RAB Radio Access Bearer establishment procedure for a PDP context includes the RAB parameters to the RAN. Within this set of parameters there are a series of QoS parameters for each of the active PDP contexts. It is proposed that one of these parameters is used as an indicator that the PDP context is allowed to be passed to the platform .

The 3GPP node communicates over the Network API to the core to inform the core that which PDP contexts the UE has established. The 3GPP node includes the RAB ID with the indication to the platform core .

The platform can instruct the 3GPP network entity to enforce specific data and signalling traffic routeing and policy rules for a specific User. The communication between platform and 3GPP is performed over the Network API .

Routeing and policy enforcement applies to both signalling and data traffic. As with the known existing mechanisms for control of Policy for data traffic Policy control is provided from a central location Policy DB and distributed to a Policy Application in the platform which directly controls the Routeing and Policy Enforcement functions at the Network Node and the platform .

For signalling the criteria would need to include Interface and or protocol identifier indicator of specific message s within protocol e.g. Handover Command and frequency measurement type e.g. for Measurement Reports .

The platform introduces the concept of a new Policy Function in the network for converged control of Signalling plane and Data traffic and is referred to as the Policy DB. The implementation of the platform may mean this functionality is realised as an extension to the existing PCRF 9 or as a separate physical entity.

The platform GW interfaces with the PCRF 9 and the Policy DB through the Network APIs Adaptors and retrieves customer specific policy information to be enforced in the network. The enforcement of the policy may be done either in the platform or in the 3GPP node depending on the Application. As a consequence the platform is responsible for filtering and distributing the relevant policy information and only enforcement actions relevant to the 3GPP node are passed to the Adaptors .

In general duplication of functionality has a negative impact on latency and therefore policy enforcement should be applied only once within the platform environment. As a consequence routeing needs to be performed before policy enforcement.

It is important to maintain the integrity of the data flow for each PDP context specifically for each UE as the UE may have multiple primary PDP contexts each with separate rules and charging information for each.

For example if the routeing decision from the platform indicates that traffic for a flow needs to be routed to the platform then the 3GPP Node should not apply any policy enforcement. Conversely for a flow for which the routeing action is to duplicate it is more appropriate to apply the policy enforcement in the 3GPP Node . It is worth remembering that both the routeing and policy decisions are being controlled by the platform and therefore care needs to be taken.

Referring to the downlink data of user services which are served from the Gi LAN or from the internet pass through the Traffic Management Function or Optimisation Functions of the Gi LAN this can either be a stand alone node or can be implemented as part of the GGSN .

The Traffic Management Function analyses the IP packets associated with the service and acts based on the policy defined by the operator. The Traffic Management Function has the ability to determine which service the IP packets relate.

The Optimisation Functions of the network perform certain actions on the content included within the packets understands the needs of the service and whether there is any benefit of further optimisation.

The Traffic Management Function and Optimisation Function can mark the packets to indicate the service category or Service Group they belong to. This marking could be the DiffSery code points of the IP packet.

When the 3GPP node receives the IP packet of a PDP context the node understands the Packet marking scheme used by the Traffic Management and Optimisation Functions . The 3GPP node can be configured over the Network API to intercept downlink packets for a PDP context with specific packet markings and pass them to the platform .

When a User is watching a video from a source off net at a time where the network has low utilisation. The central Optimisation Function is aware that the limitation for the delivery of the content is the radio and therefore it chooses not to optimise the content beyond targeting it to the device. The Optimisation Function marks the packets associated with the stream to indicate that further optimisation may be required.

The 3GPP node is configured to understand that any packets with that marking should be passed to the platform . An Optimisation Function runs on the platform and further optimises the content to radio conditions of the device to ensure that uninterrupted playback is achieved.

When a User is using P2P Filesharing application the packets associated to the application pass through the Traffic Management Function where they are identified. The Traffic Management Functions marks the downlink packets.

If the 3GPP node has not been configured to pass these packets to the platform the 3GPP node understands the packet marking and can use it for the radio scheduling.

If the 3GPP node has been configured to pass these packets to the platform the packets are passed to the platform . The platform can use these packets in a number of ways for example 

If the radio load is low these packets could be passed directly to the radio if the load is high and there are many users using this type of data on the cell the platform can change the packet marking before passing them to the 3GPP node to give these packets a lower priority on the radio .

They can be used to determine how to treat the uplink packets associated with this flow for example changing TCP window sizes to impact the downlink flow from the traffic source.

The platform may also request specific RRM functionality for a specific device over the Network API . A few examples of this control are as follows 

The platform may also communicate to Core Network 3GPP entities over the Network API to request information or specific CN handling for a specific device or bearer. A couple of examples of this control are as follows 

When the UE leaves the 3GPP node either because the UE has transitioned back to PMM Idle mode or because it has moved to a new 3GPP node the 3GPP node is responsible for informing the platform over the Network API that the UE has departed. The 3GPP node references the UE with its IMSI.

The different variants of the 3GPP network architecture will present different challenges when introducing the platform architecture. 3GPP architectures where user IP packets can be easily exposed present the quickest opportunity for realising the platform architecture.

In most markets today the 3G networks are deployed with Radio functions of the RNC deployed in central MTX Mobile Telephone exchange sites.

The framing protocols of the radio extent up to the RNC platform from the UE and it is at this point that IP packets are exposed. The RNC platform is also aware of radio performance of the UE and the load of the cell in which the UE is being provided service. The IP packets of the User are easily accessible on all nodes higher in the operator network.

It is possible to gain access to the IP packets of the User at the Node B radio site however extra functionality would be required to extract and insert packets potentially replicating some RNC like functions at the Node B .

The 3GPP access vendor may enable the platform to be hosted at the Radio Node B sites however additional breakout functionality would be required between the Node B and the RNC to enable the platform environment to be introduced. This is shown in .

The additional functionality would include mechanisms to at least manage the following aspect of the UTRAN design 

The platform access node at the Node B would treat its controlling RNC as the GW and conduct procedures with this entity. The platform Functions at the RNC would then be responsible for registering with a central GW .

In some markets the 3G HSPA networks have been enhanced to move RNC functions from central MTX sites to the Radio site as shown in .

The framing protocols of the radio therefore are terminated at the Radio site allowing IP packets to be exposed.

The IP packets of the User are therefore easily accessible on all nodes across the operator network without significant extra functionality.

The deployment of evolved HSPA network functionality poses some challenges to operators. They require inter radio site communication to ensure macro diversity gains are maintained in the uplink for HSUPA and some changes in the core network to allow large numbers of RNC enabled Node Bs to be controlled from the core network nodes.

The introduction of platform at the NodeB Radio site in the evolved HSPA network requires no extra functionality of the 3GPP network and therefore it is considered a particularly advantageous deployment option for the platform .

The lur interface within the Evolved HSPA mobile network is used to allow a user to be served on a neighbouring Node B whilst having traffic routed back to a serving RNC function of the anchor Node B site. In this architecture the Serving Node B may need to access information from neighbouring cells to identify the specific radio performance and load information for UE.

LTE networks as shown in share a similar functional architecture as Evolved HSPA with the framing protocols of the radio being terminated at the Radio site allowing IP packets to be exposed.

The IP packets of the User are therefore easily accessible on all user plane nodes across the operator network without significant extra functionality.

The deployment of LTE networks also require inter radio site communication for optimised mobility. The core network is upgraded as part of LTE deployment.

The LTE core network will be upgraded to include the IMSI in the Initial UE context which is sent to the eNB when the UE transitions to Active state and it will also need to be included in the inter eNB handover signalling.

The design of LTE included a new inter radio site interface called the X2 interface which includes some functionality for mobility whereby downlink packets are forwarded between radio sites from source site for delivery on a neighbour cell. One of the main differences between the X2 and the lur interface of the evolved HSPA is that for LTE the packets are forwarded when the RRM control has moved to the new radio site whereas for Evolved HSPA the RRM control for the UE does not transition between sites.

The LTE architecture also differs from other 3GPP systems in there is Ciphering and Integrity Protection of Mobility Management and Session Management signalling between the UE and the MME this means that the NAS messaging may not be modified or even viewed if Ciphering enabled by the Access Network.

The first packet systems deployed by 3GPP Mobile operators was GPRS as shown in . These networks are still in operation and their traffic is growing due to Smartphone data usage.

The framing protocols of the radio extend up to the SGSN platform from the UE and it is at this point that IP packets are exposed. The SGSN platforms however is not aware of radio performance of the UE this knowledge does not extend beyond the BSC platform .

As SGSNs and 2G Radio Access networks are typically from different vendors it may be difficult to offer that breakout functionality can be offered below the SGSN . To allow traffic breakout at the radio site would require the SGSN functions to be hosted at the BTS radio site .

When UEs are provided service via the 2G GPRS access network the platform environment at the base station site may still provide information useful to the service functions of the central network even if explicit operations on the data stream may not be possible from the base station site.

Option A is an overlay solution wherein a new Hardware module is added to radio site alongside existing 3GPP modules. Option B is where platform funcntionality is introduced by performing a hardware or software upgrade to an existing 3GPP Hardware Module. Option C is where the existing 3G Hardware Module is replaced with a new Hardware Module comprising the platform with 3GPP functions hosted in Software or Hardware.

It is envisaged that the implementation of the Radio site will evolve over time with initial deployments based on Options A or B and evolve to Option C at a later date. Option A would also be applicable when the platform environment was deployed on a Transmission PoC radio site.

When the platform at an access node is introduced to the network the platform registers its existence on the GW . The 3GPP Node and cell information of the cells which are controlled by the platform are provided to the GW . The control of a 3GPP node is determined by the platform having connectivity to the 3GPP node containing the RRC function of the Access Node .

The GW provides the generic rules configuration to the platform e.g. the list of applications and services which can be used by all platform users. The GW updates its DNS Domain Name System to include a record for the new platform and records for each of the cells that this Node B controls.

The 3GPP network may inform the platform environment that a new User has registered become active on the system and may also provide a pointer to the generic profile to be used by the platform until specific configuration details of the user are known.

When the platform becomes aware that a new user has arrived in the platform environment the platform registers on the Gateway . The platform can register that is playing one or more of the below roles for a specific UE 

As the platform starts to play an additional role for the UE the platform informs the GW of the additional roles.

If the platform indicates it is a Traffic Source or a Controller for a UE the GW provides the platform the SAVI UE context including policy and charging information to the platform environment as an increment to the generic rules configuration e.g. enabling additional applications to be offered to this specific UE.

The 3GPP network may indicate over the Network API that a user with a given IMSI is no longer available on the network node which can trigger the platform environment to indicate to the GW is no longer a Controller or Information Source for the UE however if there are on going applications for this UE then the platform environment may stay registered for this device as a Traffic Source. The GW or the platform environment at any time may trigger the UE to be deregistered for one or all of the above roles.

The platform provides an environment to host services and applications on the data path between the user and the internet . The platform services can broadly be split into two categories 

When the platform DNS service receives a DNS Lookup request 1 2 3 from a UE for a locally hosted application the DNS checks the UE profile to determines whether this UE is not allowed to use the local application if this application is allowed for the User a response is issued providing the IP address 4 of the local application however if the UE is not allowed to access the application then the DNS request is returned to the uplink GTP U tunnel of the PDP context.

The DNS service hosted in the platform Environment can be configured to provide a response to the DNS Lookup based on the User profile. For instance if the User is likely to be mobile the DNS response could be for a centrally hosted version of the Application whereas if the User is unlikely to be mobile the response would be the IP address of the locally hosted version of the Application .

The TTL Time to Live of the DNS response 5 would need to be configured to avoid caching of DNS responses in the User device for locally hosted applications as the IP address of the application could be different on a neighbouring cell. Steps 6 7 8 and 9 are then performed.

The platform passes the packets to the RNC BTS and they are inserted in the Downlink bearer to the User Device.

An important aspect of the platform system is the ability for remote service to retrieve real time user information from the platform environment such that it can be used to improve service quality and efficiency as well providing the enablers for new service creation. Steps 1 4 are shown in .

As the number of devices increases on mobile networks the control infrastructure will struggle to scale to meet the increased demand. Some devices do not benefit from having centrally hosted control infrastructure e.g. M2M and MBB Mobile Broadband devices therefore these devices could be handled more locally. describes steps 1 6 .

1. When the UE arrives on cell and sends the Initial L3 message which includes the P TMSI of the device.

4. MME App checks to see if the UE is known in MME UE DB if it is known the DB returns UE profile and MME App creates response for the UE else MME app sends request to Master MME App including the Initial UE message .

The Master MME App determines last cell UE came to active state and sends a purge message to the MME App on that BTS . The platform on this cell removes this UE from its local MME UE DB .

At the end of the session when the UE returns to Idle the MME APP at the platform sends the latest UE MME context to the Master MME App which updated the Master MME UE DB .

When determining whether the UE is allowed to use a local MME App the Central MME may assign a P TMSI to the UE in manner whereby the structure indicates whether local hosting is allowed e.g. if MSB of the P TMSI is 0 then always serve this UE centrally i.e. Do not pass to the platform whereas a MSB of 1 means the message should be passed to the platform .

When a user is active on a base station which has an access node platform deploy the user has been registered on the GW by the controlling platform. The Services Applications hosted by the platform will have different requirements and these can broadly be split into two categories 

The UTRAN network was designed based on the Serving RNC being an anchor point within the access network for user traffic hiding much of user mobility from the core network. If a User is using cells on Node Bs of a neighbouring RNC that RNC forwards the packets to the SRNC. The Serving RNC decides when the RNC anchor point should be changed through the SRNS relocation procedure.

In UTRAN when platform is co located with the RNC function the RNC function can ensure that platform mobility is minimised whilst the user has an active connection to a local hosted service application. If platform environment is hosted with a Node B in front of RNC functions then the 3GPP mobility of UTRAN cannot be relied on to support inter site mobility.

When platform is introduced to an evolved HSPA network where the RNC function is collapsed to the radio site the platform environment controlling the User will correspond to the Node B site which includes the Serving RNC function for a user. Due to the inefficiency on site backhaul of relaying data traffic over the lur between sites before platform was devised it could be assumed that the lur between the evolved HSPA Node Bs would be a short lived connection. However the introduction of platforms without adequate mobility support would mean that all traffic for a UE would need to be passed back to the Source Node B not just the State full applications or long lived Stateless applications.

For LTE a different approach was developed for mobility whereby some communication happens between radio sites however the duration for which downlink packets are forwarded from source site for delivery on a neighbour cell only occurs during or shortly after the handover procedure. Therefore unless the LTE system can be operated in a manner whereby the Data forwarding between sites is extended in both time and direction the mobility between platform environments would be more critical.

When a UE is in RRC connected state within 3GPP the access node platform has been made aware of the UE on the associated RAN node the platform has registered with the GW as a Controller or a Information Source for the UE and received the UE SAVi context for the UE.

The UE then starts using service where parts of the service functionality are provided an access node platform of the serving cell. The UE starts to move and the radio conditions dictates that the user needs to move to a new cell controlled by a new 3GPP Node.

The handover signalling in the network between 3GPP Nodes includes the IMSI of the UE such that the new 3GPP Node is informed that a new UE will be arriving shortly. The 3GPP Node is configured to inform the associated new platform environment that a UE is about to arrive passing IMSI of the device . The new platform can register as a Controller with the GW and receive the UE context. When a UE arrives on a new cell the new platform associated with the new data path needs to insert itself on the data flow to ensure service continuity.

When the Source 3GPP Node sends the handover messaging to the UE the 3GPP node informs the platform that the UE will be moving cell and the access node platform is informed of the Cell ID of the target cell.

The access node platform performs a DNS lookup for the new target platform using a defined format for example Cell ID.SAVi.Vodafone. The DNS of the access node platform operates in a normal manner verifying that the requesting application is authorised to make the request and then responds with the IP address of the new platform . If the DNS does not include the record it requests the DNS of the GW .

If the User has any open applications or ongoing TCP connections terminating at the access node platform the Source access node platform contacts the target new platform and establishes an IP connection. The Source access node platform informs the new target platform that specific traffic from the UE should be sent via the IP connection to the Source access node platform . The Source access node platform updates the default route for Data traffic the User to be the IP connection to the new target access node platform .

When the UE arrives on the new Target platform the Source access node platform subscribes to a Mobility Service for the UE hosted on the Target platform . The Mobility Service notifies other platforms subscribed to the Service of a change of Controller for the UE including the Cell Node ID of the new Controller. A platform which is hosting an on going application for a UE would trigger the establishment of a connection to the new Controller as discussed above.

When the Source platform indicates to the Target platform which uplink traffic should be forwarded it describes the traffic as follows 

For existing sessions of Hosted applications the UE is sending packets to the IP address of the Source access node platform and therefore routeing would not be a challenge.

However there are a number of areas where there are issues for the routeing of Uplink packets to the Source access node platform and these are 

When there are no longer any ongoing applications for a UE on a platform it can initiate the disconnection of the IP connection with the Controller which triggers the Controller to revert to the original handling for the UE.

An early implementation could avoid complexity by requesting that all traffic is routed via the platform whilst any application remains hosted by on the platform .

When the UE is operating in an enabled area served by a platform and the device moves outside of the area or moves to 2G the uplink traffic from the UE would pass to the GGSN .

For Applications Services hosted on the platform environment the UE the IP address would be that of a platform one of the platform Traffic Sources for the UE . If this IP address is routeable then it is possible to introduce a platform entity on the data path to avoid the service continuity problems this could be a function of the GW . Steps 1 4 as shown in .

1. When the UE communicating with an Application hosted on an access node platform and it changes cell to a cell outside of an area served by platforms the uplink packets to the application would be sent to the network in the normal manner.

2. The uplink packet would not be intercepted by the access node platform and would flow to the GGSN . The IP address of hosted apps would be routeable to the GW E.g. The range of IP addresses for platforms could be 192.168.x.x 16 

3. When the GW receives the packet it determines whether a Traffic Source exists for this user based on source IP address of the packet on the platform specified by the destination IP address of the IP packet otherwise the packets are dropped by the GW . 4. The GW passes the IP packets on an IP connection to an access node platform Downlink packets i.e. the Response are passed back from the application access node platform to the GW to deliver to GGSN .

For downlink packets when the access node platform loses connectivity to the UE the packets can be routed to the GW and it would be responsible for delivering the packets on the Gi LAN which would route the packets to GGSN and onto the PDP context of the UE.

Even in areas where a platform Controller is not available on the PDP Context data path e.g. because of encrypted data connections useful information of the service can still be provided by platform Information Sources for the UE. Steps 1 3 are shown in .

1. When the UE enters PMM Active State the BSC is provided the 3GPP UE context by the SGSN this context includes the IMSI of the UE.

2. The BSC is configured to inform the access node platform when a new UE has arrived on the 3GPP system and passes the IMSI to the access node platform . The access node platform is made aware that the 3GPP platform has no ability to control the User plane of the PDP context for this UE. The access node platform configures the 3GPP platform to provide measurements relating to User system to the access node platform . 3. The access node platform registers with the GW and indicates it is an Information Source for the UE. The GW updates the Registry allowing other Central Applications and service to request information regarding this UE from the access node platform . 7 SAVi Impact on Core Systems

Today the Policy Lawful Intercept Billing and Customer databases integrate into the Core Network nodes of the 3GPP network. The related functions of the 3GPP network including enforcement points are also part of the core network. Information from these core systems is very limited in the access networks with the only information flowing to the access typically is a sub set of QoS parameters for the customer data passing over the network.

In the traditional 3GPP architecture the GGSN is responsible for the creation of CDRs Call Data Records which are passed to the billing system for Non roaming customers whereas the SGSN creates the CDRs for Roaming customers.

Before platform are introduced the GGSN and SGSN for roaming customers had complete visibility of the traffic flowing to each customer with the User Plane passing transparently to the customer through intermediary network nodes. Platforms enable new network and service applications to be deployed which can change the total volume of traffic over the network and therefore some modifications are needed to the design of charging.

Network Applications such as Video optimisation cause the GGSN to overestimate whereas other Network Applications such as Caching CDN Content Delivery Network cause the GGSN to underestimate the quantity of traffic consumed by delivered to a customer. Service Applications hosted by the platforms will mean that the GGSN will have little or no visibility of the data consumed by a customer.

There are a number of solutions for the integration of platforms and 3GPP charging that are dependent on the charging mechanism applicable to the customer i.e. offline post pay and online prepay and these are to maintain the existing byte count model. shows a converged charging system in a network that includes access node platforms and GWs . The proposed solutions are 

Options A B require the Network API to allow charging information to be passed from GW to 3GPP node whereas Option C requires the GW to collate the GGSN charging records and interface into the Charging System in a consistent manner.

Responsible operators include functionality within networks to ensure inappropriate content is not delivered to users unless they have explicitly proved they are an adult.

In the future a greater granularity of content types are likely to be required to determine whether content may or may not be delivered to specific groups of UEs.

If the platforms are to host applications and serve content within the Access Network then they need to be informed as part of the user profile of any restrictions for that user.

When content is stored in the cache of the platform the GW provides an identifier for the content which is used by the platform to determine which groups of UEs can access a piece of stored content.

A similar scheme is provided for the hosted applications and services whereby the applications and services may also have an associated Adult content restriction.

When a UE is not allowed to receive content due to Adult Content Filtering rules the User request is forwarded back onto the Uplink GTP U tunnel to existing handling within the network is maintained.

In the 3GPP system each PDP context has associated Uplink and Downlink Maximum Bit Rate parameters. The Downlink maximum bit rate parameter for a specific PDP context is enforced by the GGSN whereas the uplink maximum bit rate parameter is enforced by the RAN .

When the platforms are is introduced on the data path of the PDP context the GGSN no longer can enforce the Maximum Bit rate for the PDP context and therefore this functionality will need to be replicated by the platform or the 3GPP node which provides connectivity between the platform and the PDP context of the UE. The Maximum Bit Rate of a PDP context can be included in the RAB parameters sent by the SGSN and this can these can either be enforced by the 3GPP node on the downstream of the platform or passed to the platform . However if the platform is performing the enforcement of Maximum Bit Rate then all data associated with the User in the downlink would need to pass through the platform .

For the uplink again either the platform or the 3GPP node can perform the enforcement of Maximum Bit Rate. If it is the platform all uplink traffic for that PDP context would need to be routed via the platform and if it is the 3GPP node enforcement would need to be completed on the node before the routeing of uplink packets to the platform .

The design of platforms aims to minimise the impact to Lawful Intercept LI within the network. Existing content routed through the GGSN in the uplink or downlink will continue to be handled by existing LI implementation.

Lawful Intercept in one platform implementation is designed to avoid Lawful Intercept information being known by the platform environment and further optimisations of the design to reduce the volumes of data required to be passed around the network may be provided in other implementations.

All Data of all users served by platforms is passed through a Passive LI Entity as shown in and this data would be encapsulated with at least User ID cell ID and Time of Transmission.

The Passive LI Entity has the capability and authority to see all data and is responsible for filtering based on the User information included in the encapsulation and data in an LI target list which identifies users subject to LI.

In one platform implementation GMM SM CPRS Mobility Management Session Management signalling messages to the SGSN MME will be maintained for all users and therefore the existing LI implementations would also remain.

In other implementations the access node platform may capture all LTE and 3G 3GPP GMM SM related signalling messages host 2G SGSN software allowing 2G GMM SM signalling messaging to be exposed to the access node platform and tunnel these to the network via GW as a uniform signalling related interface. shows steps 0 4 for such implementation.

During the Application certification integration process it will be identified how the Lawful Intercept should be applied for data from that application. For each application hosted at the access node platform none some or all traffic related to the application may be duplicated and passed to the Gateway platform . The Platform of the Gateway would be responsible for routeing the duplication of both uplink and downlink Application traffic. The access node platform at the base station would not be aware of any customer specific LI requirements and reporting is purely based on application service type. shows steps 0 2 .

An example of an application which has traffic of partial interest to LI may include Game servers which include traffic related to the internal operation of the game as well as an associated voice or messaging path for in game person to person communications. During Application certification integration it would be deemed that the communications aspects of the game need to be handled through LI therefore the access node platform would filter these packets and pass them to the Gateway . Other access node platform Customer specific information would also need to be passed with the Data e.g. customer identities of each of the locally served end points.

Where the access node platform is performing optimisation of the content it is assumed that the LI function does not need to be made aware of the created lower quality version of the data flow and therefore LI routing function of the access node platform is not invoked. shows steps 1 5 .

When content is spooled from the user device to the access node platform it may then delivered more slowly in the uplink over the backhaul transport to the Gateway . The access node platform is responsible for ensuring content stored at the access node platform cannot be accessed by other Applications nor by other Users until it has been passed to the GW and LI been enforced. The access node platform is also responsible for running timers associated to Content received and stored at the access node platform to ensure that it is delivered within a set period of time e.g. 30 mins. shows steps 1 to 4 .

For subscribers roaming onto platform enabled 3GPP network their signalling and traffic is assumed not to impact the functional requirements of the platforms . Certain functions and applications may need to be inhibited for these subscribers which would be handled through local configuration policy. Depending on the roaming configuration e.g. home routed traffic it may not be possible to retrieve information such a policy information from a PCRF 9 or may not be possible to control the actions of the GGSN since they reside in the home network of the subscriber.

Due the typical environment where platforms will be deployed the functionality of the platform and the information which is held on the platform security and integrity of the platform is an imperative.

The security architecture for communications between platforms should follow similar architecture principles as LTE whereby the site to site communications of the X2 interface is typically via a Security Gateway SeGW in the operator s network as shown in .

The communications between platform and the GW is secured between the platform and the SeGW and then the path of the communications between the SeGW and GW can be assumed to be over a trusted transmission network.

When platforms are introduced into a 3GPP network there may be significant cost and complexity integrating platforms into the Core systems. It is therefore envisaged that tactical solutions to enable platforms to be deployed whilst minimising complexity are required.

As the core systems are already integrated into SGSN and GGSNs 6 these nodes may need to be leveraged requiring these nodes to see all traffic for all users.

There are a number of possible solutions for the re use of the SGSN GGSN functions and the following description is based on just one example. The main aim of a tactical solution is to minimise the impact to legacy systems and as user data is dominated by the downlink and transmission networks are typically symmetric it should aim to minimise additional downlink data on the transmission network.

The GGSN is responsible for performing charging IP packet spoofing and some aspects of LI and the IP packet spoofing capability can be abused to perform charging and LI for packets that injected by the platform .

The solution needs to cope with applications services hosted in the platforms environment as well as services that are required to operate transparently on the data stream. For the early implementations it is assumed that all user traffic is maintained within the PDP context of the user therefore the platforms would not need to ensure that users presented the correct IP address this functionality could be maintained in the GGSN .

One of the challenges with maintaining the charging interfaces at the GGSN is that when content is being served by the platform on the data path of the PDP context the existing mechanisms to handle the scenario when a pre pay user runs out of credit is by passed by the platform . There are a number of solutions to solve this scenario. shows steps 1 to 5 .

The GW registers for top up events for this UE and is informed when the UE can again access the platform system. Once the UE has topped up the GW updates the UE context in the platform to indicate that the platform can serve traffic for this UE.

The early implementations of platforms may still require considerable traffic volumes to be passed over the 3GPP network and therefore it may require further capacity investment. It is therefore proposed that 3GPP Direct Tunnel is implemented in the network to limit total throughput of SGSN and Core transmission.

One of the challenges with direct tunnel is the devices that frequently transition between PMM Idle and Active states which requires core network signalling to toggle the downlink path between SGSN and RNC to maintain paging functionality of the SGSN when the device is in Idle. However this does not need to be completed for the uplink path it is therefore proposed that direct tunnel be introduced in the uplink even if the Idle Active signalling load prohibits its use in the downlink.

