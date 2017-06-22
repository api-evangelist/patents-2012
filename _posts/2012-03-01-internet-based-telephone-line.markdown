---

title: Internet based telephone line
abstract: In one embodiment, a telephone service method that provides subscribers with the functionality of an extra telephone line during data/Internet sessions is disclosed. Each subscriber has a unique telephone number Dns that can be dialed by anyone with access to the PSTN. When the Dns is dialed the call will be routed via the PSTN to the ILTD server. The ILTD server upon receiving the call attempt from the Dnc will analyze the dialed number (Dns) and determine if the subscriber's computer is able to receive the telephone call. If the subscriber's computer is actively engaged in an Internet Protocol session, with the ILTD client software running, the ILTD server will connect the call over the Internet to the ILTD client software.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09025588&OS=09025588&RS=09025588
owner: Inpointeractive Corp.
number: 09025588
owner_city: Bedford, Nova Scotia
owner_country: CA
publication_date: 20120301
---
This application is a continuation of and claims priority to U.S. application Ser. No. 12 186 350 filed on Aug. 5 2008 now U.S. Pat. No. 8 149 822 which is a continuation of and claims priority to U.S. application Ser. No. 09 567 758 filed on May 9 2000 now U.S. Pat. No. 7 408 919 which claims priority to Canadian Application No. 2 271 828 titled INTERNET BASED TELEPHONE LINE filed on May 11 1999 the entire contents of each of which is incorporated by reference in its entirety.

This invention relates to the field of providing telephone service over an Internet Protocol IP network and more particularly to the provision of full duplex local telephone service and call management features over an IP based network terminating to a personal computer.

Currently the only practical and affordable method to provide local voice telephone service and associated call management features is to rent a physical copper circuit from the local telephone company. The copper circuit would connect the customer premise equipment CPE to a central switching office CO of a Public Switched Telephone Network PSTN . The CO is responsible for hosting the subscriber s public dial number and routing the calls to the subscriber s line when the number is dialed. Additionally the CO is responsible for providing some call management features such as Caller ID and Call Waiting type services.

Consequently there is a need for a system and method for providing local telephone services over an IP based network to mitigate the requirement of renting a copper circuit from a telephone company.

An object of the present invention is to provide a system and method for establishing the equivalent of local telephone service over an IP based network.

In accordance with one aspect of the present invention there is provided a method for providing notification and support for incoming calls having a dialed number identifier associated with a computer in communication with an Internet Protocol based data communications network wherein the data communications network is connected to a public switched telephone network PSTN via a call direction server said method comprising the steps of notifying the computer when an incoming call is detected on the call direction server receiving an indication of a selected response action from the computer and processing the incoming call according to the selected response action.

In accordance with another aspect of the present invention there is provided a method for providing notification and support for incoming calls having a dialed number identifier associated with a computer in communication with an Internet Protocol based data communications network wherein the data communications network is connected to a public switched telephone network PSTN via a call direction server having a database of all valid subscriber dialed number identifiers said method comprising the steps of obtaining dialed number information about the call from the PSTN comparing the dialed number information to valid subscriber dialed number identifiers in the database and providing a message to the computer having a computer address corresponding to the dialed number identifier.

In accordance with a further aspect of the present invention there is provided a method for providing notification and support for incoming calls having a dialed number identifier associated with a computer in communication with an Internet Protocol based data communications network wherein the data communications network is connected to a public switched telephone network PSTN via a call direction server said method comprising the steps of receiving notification of an incoming call providing a list of response actions for the incoming call and sending an indication of a selected response action for the incoming call.

The details of one or more embodiments of the invention are set forth in the accompanying drawings and the description below. Other features objects and advantages of the invention will be apparent from the description and drawings and from the claims.

The present invention is based on exploiting the growth of affordable high speed Internet access services such as Asynchronous Digital Subscriber Line ADSL and Data over Cable DOC . These high speed services establish a permanent always on connection to an IP based network. The present invention provides a system and method for providing existing and new voice telephone service delivery in the form of digital packet data over a logical circuit.

Referring to there is provided a system of the network components and interfaces required by the present invention. An Internet Line Two Director ILTD server is connected to a switching point e.g. a DMS host switch by an Integrated Services Digital Network ISDN Private Rate Interface PRI link .

The ILTD server is also connected to the Internet through standard TCP IP lines . Customer Premise Equipment CPE including a computer having a soundcard A a microphone B ILTD client software and a modem and a telephone is connected to the Internet through another switching point . The ILTD server is also connected to a PSTN public switched telephone network domain having a DMS switch through ISDN PRI links . A calling telephone is connected to the switch for placing calls to for example the telephone .

In the present description the links and are standard ISDN trunks consisting of 23 B channels and one D signaling channel . In a configuration where there are multiple PRI trunks there may be a shared D channel which is used by multiple links. Subsequent links which depend on the initial D channel have 24 B channels. Further traditional call processing functions are based on the well known Advanced Intelligent Network MN using standard out of band signaling such as the Signaling System 7 SS7 protocol.

The above components can be implemented in various ways. A single component can be implemented as stand alone network equipment multiple components can be combined in a single item of network equipment or a given component can be partitioned over two or more items of network equipment.

The method of the present invention is a subscription based telephone service that provides subscribers with the functionality of an extra telephone line. Each subscriber has a unique telephone number Dns associated with their telephone that can be dialed by anyone with access to the PSTN . When the Dns is dialed e.g. by a user of telephone the call is routed to the ILTD server through the PSTN using standard AIN SS7 signaling.

The ILTD server upon receiving the call attempt from the Dnc will analyze the dialed number Dns and determine if the subscriber s computer is able to receive the telephone call. If the subscriber s computer is actively engaged in a data communications session over the Internet with the ILTD client software running the ILTD server will connect the call over the Internet to the ILTD client software .

The ILTD client software will activate the subscriber s sound card A and the microphone B to play audio and receive input from the microphone B to allow the subscriber and the calling party to have a full duplex telephone conversation.

Each subscriber typically has a subscription to an Internet access service either a dialup service or a dedicated access service. It is preferable that the subscribers use a high speed access service to enable a high level of throughput for the digitally compressed voice stream.

In each local calling area covered by a typical Local Exchange Carrier LEC at least one computer telephony server for example an industrial Pentium rack mounted computer running the Solaris operating system is required.

As discussed above the ILTD server is connected to the Internet via one or more high speed dedicated connections to an Internet service provider. To enable high throughput and faster communication with customers multiple high speed links could be connected to the ILTD server .

The PRI ISDN trunks offer the ability to have an unlimited number of direct inward dial DID numbers that route to the ILTD server . These DID numbers will be assigned to individual subscribers. When calls are routed to the ILTD server via the PRI trunks the DID number is identified to the ILTD server by the switch . This notifies the ILTD server which subscriber is being called. In addition to identifying the dialed number Dns the PRI trunk carries the calling party number Dnc and name name c information as well as other standard call setup data according to the standard AIN call model and SS7 signaling.

The ILTD server includes a number of components as illustrated in . Each component has a different responsibility in enabling the IP based telephone line of the present invention. The components of the ILTD server work in conjunction with industry standard digital signal processing hardware which is installed in the ILTD server . In a typical configuration the ILTD server includes one or more PRI or T1 network interface cards such as the Dialogic D240SCT1 one or more voice processing boards such as the Natural Microsystems AG48 one or more voice over IP encoding decoding vocoder boards such as the Natural Microsystems Fusion board and one or more Ethernet interface boards . Each of these components includes an Application Programming Interface API well known to those skilled in the art.

PSTN Network Interface PNI module The PNI module operates the PSTN network interface cards and enables the termination telephone calls offered by the serving switch of the PSTN . The PNI module is responsible for capturing the Dns Dnc and name c that are delivered to the ILTD server over a PRI or equivalent trunk. Alternatively the PSTN Network Interface module functions can be implemented using an SS7 interface.

Voice Processing VP module The VP module operates the voicing processing board and the vocoder to perform all voice processing related functions such as the playback of audio prompts and the like.

State Management SM module The SM module is responsible for tracking the presence of subscribers. When a subscriber s computer is active and connected to the Internet the ILTD client software will notify the ILTD server by sending a login request to the ILTD server . The login request contains the subscriber s IP address along with their DN password and other service related parameters such as version of the service to which they subscribe . When the SM module receives the login request it validates or denies the request.

If the request is validated the subscriber is considered and able to receive or make telephone calls over the Internet . The SM module continues to monitor the presence of the subscriber throughout the life of their connection. The ILTD client software will periodically send a confirmation message to the ILTD server notifying it that it is still connected. If the SM module does not receive a confirmation message from the ILTD client software within a predetermined time such as every minutes it will attempt to communicate with the subscriber at the previously recorded IP address to determine if they are still connected.

The ILTD client software is a compiled software application residing on the subscriber s computer . The ILTD software acts as the soft telephone for the subscriber. Its function is to monitor for the presence of an Internet connection on the subscriber s computer and once found attempt to authenticate itself with the appropriate ILTD server . The authentication process involves the transmission of the subscriber s telephone number Dns a password an IP Internet Protocol address and other subscriber profile data.

The ILTD client software also has the responsibility of communicating with multimedia hardware software sound card microphone and operating systems on the computer . This enables the subscriber to communicate via

voice through the computer back to the ILTD server and ultimately back to the calling party Dnc and name c .

A call processing method according to an embodiment of the present invention is illustrated in the flow chart of .

Step The subscriber s computer is activated and connected to the Internet using any one of many well known methods including dialup over a standard POTS line ISDN cable modem ADSL or 1Meg modem type service.

Step The ILTD client software sends an authentication request message to the ILTD server via the Internet .

Steps and The ILTD server either authenticates or denies the request proceed to step if authenticates terminated at step if ILTD server denies the request .

Step Call is routed via the PSTN and offered to the ILTD server . Call setup message containing the subscriber number Dns calling party number Dnc calling party name name c is delivered to the ILTD server .

Steps and The ILTD server verifies that the subscriber is a valid subscriber and whether or not they are authenticated meaning they are connected to the Internet proceed to step if yes Internet based telephone line is inactive at stage .

Step ILTD server sends the call request notification via the Internet to the ILTD client software . This notification contains the calling party number Dnc and name name c .

Step and ILTD client software initiates a popup window on the computer screen indicating that someone is calling. The subscriber can select to answer proceed to step or perform other call processing functions at step such as transfer call ignore call acknowledge call by playing a prescribed message or send the call to voice mail .

Step The ILTD server negotiates with the ILTD client software or appropriate voice software communications packages via standard H.323 protocol to establish a voice telephone call using Internet Protocol i.e. voice over Internet Protocol VOIP between the ILTD server and the subscriber s computer .

The subscriber can also use telephone to make outgoing calls using VOIP when an Internet session is activated on the computer following the basic principles outlined in . In particular when the subscriber has an active Internet connection the computer is used to establish a VOIP call through the Internet using the ILTD server .

In summary the IP based telephone line service of the present invention does not merely redirect a call from the subscriber s POTS line. The DID number is actually hosted on the ILTD server and when it is dialed the call is connected to the ILTD server then converted to VOIP to get to the subscriber .

