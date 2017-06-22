---

title: Method for registering communication terminals with base station devices by using virtual appliances
abstract: A method for the registration of a communication terminal is provided. In some embodiments of the present invention, a communication terminal is registered with a base station by searching and executing a virtual appliance that contains base station software with which the communication terminal pre-subscribed. In some embodiments of the present invention, a communication terminal is registered as an endpoint device for a Session Initiation Protocol (SIP) uniform resource identifier (URI) when the communication terminal registers with the base station.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08380202&OS=08380202&RS=08380202
owner: Avaya Inc.
number: 08380202
owner_city: Basking Ridge
owner_country: US
publication_date: 20120731
---
The present application is a divisional of U.S. patent application Ser. No. 12 814 771 filed Jun. 14 2010 the content of which is incorporated herein by reference in its entirety.

The present invention relates to telecommunications in general and more particularly to a method for registering communication terminals with base station devices.

A cordless telephone is a telephone that communicates via radio waves with a base station connected to a fixed telephone line. The base station is located in the subscriber s premises and attaches to the telephone line in the same way a regular wired telephone receiver does. When a person uses a cordless telephone he or she can take the handset and go anywhere in his or her house without being constrained by a wire. Cordless telephones have been manufactured since the 1980s.

Digital Enhanced Cordless Telecommunications DECT is a standard specification for cordless telephone receivers. DECT fully specifies the means for a cordless handset to access a fixed network via radio. It specifies signal frequencies to be used as well as protocols for communication between handsets and base station devices. The first DECT standard was published in 1991.

The rapid development of the Internet throughout the 1990s saw the development of another standard. The Cordless Advanced Technology Internet and quality CAT iq standard was specified to bring together broadband Internet and telephony. CAT iq is intended to coexist with DECT.

CAT iq specifies the means for delivery of additional services on DECT compliant handsets. CAT iq handsets can make both calls over the telephone network PSTN and calls over the Internet e.g. VoIP etc. . Furthermore CAT iq handsets have the ability to receive data services such as Internet radio for example. CAT iq is an enhancement to the DECT standard because it enables the delivery of advanced services that are not available in DECT.

DECT and CAT iq are designed to promote interoperability. Devices that implement the DECT CAT iq standards are expected to be compatible with one another regardless of their implementation details. From a practical standpoint that means that a user can buy a handset from one manufacturer and expect it to interact successfully with any other manufacturer s base station device.

Notwithstanding interoperability goals the extent to which DECT CAT iq devices can interact with each other varies. DECT and CAT iq are standard specifications that specify the implementation of different services. The actual implementation of these services is completed by the manufacturers of DECT CAT iq devices. Variations in the implementations of different manufacturers sometimes cause devices to experience difficulties when interacting with one another.

The software implementation of the DECT CAT iq standards is sometimes referred to as DECT CAT iq stack. A DECT CAT iq is an application programming interface API for implementing services. For the purposes of this disclosure the term service is a communication functionality that can be made available to a communication terminal. Exemplary services include voice mail control voice service capability e.g. PSTN telephone calls data service e.g. Internet access voice over Internet Protocol VoIP and others.

In a DECT CAT iq system comprising a base station and a handset each of the two devices executes its own DECT CAT iq stack. The number of different services implemented by each stack can vary. For example the manufacturer of a base station may implement only a voice telephony service while the manufacturer of a cordless device may implement both the voice telephony and answering machine control services. In this scenario when the cordless device is coupled with the base station the cordless device would be able to use only the voice telephony service i.e. the device would be able to make telephone calls etc. .

In order for a service to be available to the user the DECT CAT iq stacks of the base station and the user s handset must both implement that service. Therefore to maximize the number of services that a user can access on his or her DECT CAT iq handset a base station device that executes a DECT CAT iq stack possessing a desirable characteristic has to be selected. Desirable characteristics include but are not limited to availability of a certain service i.e. the stack of the base station implements the service support for a specific version of a standard specification e.g. DECT CAT iq v. 4.0 etc. and having the same manufacturer as the handset.

The present invention uses virtualization to address compatibility issues that are caused by variations in the implementation of different DECT CAT iq stacks. Virtualization is a technology that enables the execution of multiple system software instances on a hardware device. Virtualization makes possible the use of virtual appliances. Virtual appliances are software packages that are designed to run on a virtualization platform. Virtual appliances comprise system software services as well as higher level applications such as base station software for example. The use of virtual appliances reduces the installation configuration and maintenance costs associated with deploying software stacks such as the DECT CAT iq stacks discussed.

In some embodiments a virtual appliance is selected and started when a DECT CAT iq terminal registers with a DECT CAT iq base station. The virtual appliance comprises base station software. The base station software comprises a DECT CAT iq stack that possesses a desirable characteristic. Desirable characteristics include but are not limited to availability of a certain service i.e. the stack implements the service support for a specific version of a standard specification e.g. DECT CAT iq v. 4.0 etc. and having the same manufacturer as the handset. Thus when a CAT iq terminal registers with a base station the present invention locates and downloads a virtual appliance that comprises a DECT CAT iq stack that is deemed desirable for the registering terminal.

The present invention also uses virtualization to improve the way in which terminals subscribe to base stations. In some embodiments a virtual appliance is selected and started when a DECT CAT iq handset registers with a DECT CAT iq base station. The virtual appliance comprises base station software. The base station software is configured so that the terminal is pre subscribed with the base station software. Because the terminal is pre subscribed both the terminal and the base station need not execute a registration handshake to exchange registration information. For the purposes of this disclosure the term registration information is information that at least one of a base station and a terminal must possess in order to recognize and or communicate with each other. Examples of registration information items which are discussed in the Detailed Description section include subscribed device identifier service identifier and service identity.

Furthermore in some embodiments the present invention improves the ease with which terminal devices take advantage of VoIP telephony services provided by the CAT iq standard. In some of these embodiments the present invention registers terminals as endpoint devices in a Session Initiation Protocol SIP network when the devices register with a base station. In particular the embodiments identify a SIP uniform resource identifier URI associated with a terminal or the user of the terminal. After the SIP URI is identified the embodiments register the terminal as an endpoint device for the SIP URI.

Although the present invention and its embodiments are discussed in the context of DECT and CAT iq it is to be understood that the applications of the present invention are not limited to those two standards only. The methods principles and concepts described by this disclosure can be applied in equal force to any technology for wired or wireless communication between communication terminals and base station devices. It is to be understood that the above embodiments and their instances are provided to better illustrate different aspects of the present invention. They are in no way exhaustive of the full scope of the invention. The following disclosure teaches examples of some embodiments of the present invention in detail.

Server is a Session Initiation Protocol Server. In accordance with the illustrative embodiment of the present invention server is a SIP registrar server. In alternative embodiments of the present invention however server is a redirect server proxy server or any other type of SIP server.

Repository is a server for storing virtual appliances. Repository permits the searching for and retrieving of virtual appliances by base station . The virtual appliances in repository comprise base station software that matches specific communication terminals. For instance one virtual appliance with may contain base station software that is compatible with cordless devices that are manufactured by Avaya Inc. of Basking Ridge N.J. while another virtual appliance may contain base station software that is better suited for communication terminals made by another manufacturer.

The virtual appliances in repository comprise base station software. For the purposes of this disclosure the term base station software is defined as a body of machine executable code that enables a hardware device to operate as a base station. A hardware device is an electronic device that comprises a processor memory and network interface.

In some embodiments repository comprises a database that relates one or more of the virtual appliances stored in it to one or more characteristics of their base station software. That is repository permits the searching or its virtual appliances according to the characteristics of base station software that is contained in this appliance. Repository allows base station to search for and retrieve virtual appliances whose base station software possesses a specified characteristic. Exemplary characteristics of base station software include 

Database is a server which executes database software. The database software stores information records which relate a Session Initiation Protocol SIP uniform resource identifier URI to an identity datum. Examples of identity data are provided in the discussion with respect to .

Base station is a DECT CAT iq base station. It will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention in which base station uses another technology for wireless communications.

In the illustrative embodiment base station is a telephone receiver base station combination it is a device that doubles as a telephone receiver and a base station. In alternative embodiment of the present invention however base station is just a base station.

Base station or more precisely base station software that executes on base station provides service s to terminals and . As noted exemplary services include voice mail control voice service capability e.g. PSTN telephone calls data service e.g. Internet access voice over Internet Protocol VoIP and others. A subset of the service s which base station provide are communication services. For the purposes of this disclosure the term communication service is a service that pertains to the transmission or receiving of communications by terminals and or . Examples of communication services include 

Terminal is a handset that complies with both the CAT iq and DECT standards. Terminal connects to base station . In accordance with the illustrative embodiment of the present invention base station provides terminal with data services. Terminal uses the data services to send and receive data over network . It will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention in which terminal is any other communication terminal e.g. wired telephone receiver wireless desk set telephone receiver personal computer cellular telephone GSM cellular telephone etc. .

Terminal like terminal is a DECT CAT iq compliant handset that connects to base station . In accordance with the illustrative embodiment of the present invention base station provides terminal with data services. Terminal uses the data services to send and receive data over network . It will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention in which terminal is any other communication terminal e.g. wired telephone receiver wireless desk set telephone receiver personal computer cellular telephone GSM cellular telephone etc. .

Network is a communications network that transports signals between base station server repository and database . In accordance with the illustrative embodiment of the present invention network is a cellular network but it will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention in which network is another type of communication network e.g. a local area network the Public Switched Telephone Network the Internet wide area network etc. .

Processor is a central processing unit CPU configured to execute software code. It will be clear to those skilled in the art how to make and use processor .

Memory is a storage device that is addressable by processor . In accordance with the illustrative embodiment of the present invention memory is random access memory RAM . It will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention in which memory is any type of volatile or non volatile storage device.

Network interface is hardware e.g. radio transceiver Ethernet interface etc. that enables base station to exchange wireless communications with terminals and . Additionally network interface enables base station to exchange communications over network .

Virtualization Layer is a software layer that facilitates the sharing of the hardware resources of base station by multiple system software images. In accordance with the illustrative embodiment of the present invention virtualization layer is an OKL4 microkernel but it will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention in which virtualization layer is any other virtual machine e.g. Type 1 hypervisor hosted virtual machine etc. .

System software is an image of an operating system that is running on virtualization layer . It will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention in which system software is any type of system software firmware or software platform that is capable of executing on top of virtualization layer .

Telephony application is a software application for conducting telephone conversations. In the illustrative embodiment telephony application is capable of conducting voice calls. In alternative embodiments of the present invention however telephony application is capable of conducting communication sessions in other media e.g. video text etc. .

Registration module is software that operates to register terminal onto a Session Initiation Protocol SIP network. The operation of registration module is further described in the discussion with respect to .

System software is an image of an operating system that is running on virtualization layer . It will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention in which system software is any type of system software firmware or software platform that is capable of executing on top of virtualization layer .

SIP gateway is software that enables terminal to direct SIP session invitations to devices in external domains e.g. network etc. . In the illustrative embodiment SIP gateway provides terminal with services that are characteristic of SIP proxy servers.

Base station software is the body of machine executable code that enables base station to fulfill its functions as a DECT CAT iq base station i.e. base station that complies with both the CAT iq and DECT standards . Base station software is further described in the discussion with respect to .

Subscribed device identifier is a set of one or more identifiers that serve to distinguish a device that is allowed to use one or more of the communication services that are provided by base station software from one or more devices that are not allowed. In the illustrative embodiment subscribed device identifier is an international portable user identity IPUI it is an identifier assigned on a per user basis possibly after an authentication procedure is executed . In alternative embodiments of the present invention however subscribed device identifier is an identifier that is assigned on a per device basis e.g. MAC number of terminal international portable equipment etc IPEI . The present invention is not limited to any specific type of subscribed device identifier.

Service identifier is a set of one or more identifiers that are used to mark one or more messages that are transmitted by base station . Terminal uses the marking to recognize the source of the messages. In some embodiments the marking is performed by including service identifier or parts of it inside messages that are transmitted by base station . It will be clear to those skilled in the art how to use service identifier in a variety of ways in order to distinguish communications that are transmitted by base station . The present invention is not limited to any specific way of using service identifier to distinguish communications by base station .

In the illustrative embodiment service identifier comprises a portable access rights key PARK . It will be clear to those skilled in the art after reading this disclosure that alternative embodiments can be devised in which service identifier is any other type of identifier. Examples of such identifiers include serial number of base station IP address that is assigned to base station for the purposes of exchanging data over network number of the telephone line to which base station is connected an identifier that is assigned to base station by an administrator and others.

In summary service identifier is used by embodiments of the present invention to accomplish the following functions 

Stack is an application programming interface API for the sending and receiving of communications. In the illustrative embodiment stack is a DECT CAT iq stack. Nevertheless it will be clear to those skilled in the art after reading this disclosure that alternative embodiments of the present invention can be devised in which stack operates according to another communication standard specification.

Stack provides an application programming interface API for implementing a plurality of operations. The operations when combined enable different services. In the illustrative embodiment stack enables the following services 

Connector is software code that is responsible for establishing communication sessions between devices between communication terminals. The operation of connector is further described in the discussion with respect to .

Processor is a central processing unit CPU configured to execute software code. It will be clear to those skilled in the art how to make and use processor .

Memory is a storage device that is addressable by processor . In accordance with the illustrative embodiment of the present invention memory is random access memory RAM . It will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention in which memory is any type of volatile or non volatile storage device.

Network interface is hardware e.g. radio transceiver etc. that enables terminal to exchange communications with base station . It will be clear to those skilled in the art how to make and use network interface .

Stack is an application programming interface API for the sending and receiving of communications. In the illustrative embodiment stack is a DECT CAT iq stack. Nevertheless it will be clear to those skilled in the art after reading this disclosure that alternative embodiments of the present invention can be devised in which stack operates according to another communication standard specification.

Stack provides applications on terminal with an application programming interface API that enables them to access services that are made available by base station . For instance it provides the necessary routines for telephony applications make telephone calls over the Public Switched Telephone Network. In the illustrative embodiment stack provides the following services 

In order for the services provided by stack to be available to the user of terminal they must be also supported by stack . That is a services such as answering machine controls is available to the user of terminal only when 1 it is implemented by both stack and stack and 2 the implementation of stack is compatible with the implementation of stack . Common sources of incompatibility are use of different message lengths different treatment of reserved bit fields different treatment of reserved values etc.

Service identity is a set of one or more identifiers that serve to identify a base station or base station service which terminal is allowed to use. In the illustrative embodiment service identity comprises a public access rights key PARK and an international portable user identity IPUI . It will be clear to those skilled in the art however that alternative embodiments of the present invention can be devised in which service identity is any type of identifier e.g. user name MAC address of base station etc. .

Signaling protocol stack is a Session Initiation Protocol SIP stack. It provides applications that execute on terminal with an application programming interface API for the creating and transmitting of Session Initiation Protocol SIP messages. As is well known SIP ordinarily uses data services such as TCP and UDP for the transmission of SIP messages. In the illustrative embodiment signaling protocol stack uses data services that are provided by stack and base station for the transmission of SIP messages.

In accordance with the illustrative embodiment stack is a SIP stack. Nevertheless it will be clear to those skilled in the art after reading this disclosure that alternative embodiments of the present invention can be devised in which signaling protocol stack is another communication protocol stack e.g. H.323 Skype etc. .

At task registration module receives a request to subscribe terminal to base station . Subscribing terminal to base station enables the terminal to receive incoming communications from base station as well as use base station to place outgoing communications to devices that are connected to network . In the illustrative embodiment the request is a LOCATE REQUEST message. In alternative embodiments however the request can be any type of indication that terminal is attempting to subscribe to base station . The LOCATE REQUEST message contains a user identity datum which identifies the user of terminal .

In the illustrative embodiment the user identity datum is an international portable user identity IPUI . In alternative embodiments of the present invention the identity of the user of terminal is communicated to base station by using another identifier e.g. user name password etc. .

It will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention in which the user identity datum is not received with the subscription request. In some alternative embodiments a procedure to obtain the user identity datum is initiated in response to receiving the subscription request e.g. authentication handshake etc. . In these embodiments terminal provides the user identity datum in response to a prompt from base station .

At task registration module registers terminal to base station . When the registration is completed terminal can use base station to make telephone calls send data over network and so forth. Task is described in further detail in the discussion of .

At task SIP gateway registers terminal on a SIP network. Task is further described in the discussion with respect to .

At task registration module subscribes terminal to base station . Also at task SIP gateway registers terminal on the SIP network. Task is executed according to the methods and principles disclosed with respect to tasks .

In the illustrative embodiment terminal is registered with the base station software that is executing inside the user space of system software . In alternative embodiments however a third system software instance is instantiated. In the alternative embodiments terminal is registered with base station software that is executing inside the user space of the third system software instance.

At task base station software establishes a communication session that uses the SIP network to which terminal is registered at task in response to a request to establish a communication session that uses the Public Switched Telephone Network PSTN . Task is further described in the discussion with respect to .

Tasks are described for illustrative purposes. It will be clear to those skilled in the art after reading this disclosure how to perform the tasks associated with in a different order than represented or to perform one or more of the tasks concurrently. Furthermore it will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention that omit one or more of the tasks.

At task registration module obtains a terminal identity datum for terminal . The terminal identity datum is an identifier e.g. an alphanumerical string etc. that is used to distinguish terminal from other terminals. In the illustrative embodiment the terminal identity datum is based on 

In some embodiments of the present invention a procedure to obtain the terminal identity datum is initiated in response to receiving the subscription request at task . In these embodiments terminal provides the terminal identity datum to base station following a prompt from base station . In other embodiments the terminal identity datum is received as part of the subscription request.

At task registration module searches and locates in repository a preferred virtual appliance. The search is performed according to a search key that is based on the terminal identity datum obtained at task .

In the illustrative embodiment of the present invention the preferred virtual appliance is an appliance which contains base station software with which terminal is pre subscribed. That is the base station software of the virtual appliance is configured to be recognized by terminal as a base station device or service with which terminal is subscribed or registered .

Base station recognizes terminal as a device which is allowed to use a service e.g. telephony service Internet access etc. provided by bases station when one or more of the following is true 

Terminal recognizes base station as a base station whose service s terminal is allowed to use if one or more of the following is true 

Ordinarily the base station will assign an identification number IPUI etc. when the terminal is registered with it. After the IPUI is assigned the base station will transmit it to the terminal. When the terminal receives the IPUI it will store it in memory and use it to send and receive communications from the base station. The IPUI is used as a proof by the terminal that the terminal is allowed access services offered by the base station e.g. make telephone calls using the PSTN make VoIP calls receive data etc. .

In some embodiments of the present invention however terminal comes with an identifier such as the IPUI that has been stored in the memory of terminal prior to the beginning of the registration. Instead of altering the identifier that is already stored in the memory of terminal or storing a new one the present invention locates a preferred virtual appliance which contains base station software that is configured to recognize the identifier that has been stored in the memory of terminal as an identifier of a device that has already been granted access rights by base station software . In this way terminal is subjected to a simplified registration procedure.

In the illustrative embodiment the identification of the network that terminal is allowed to access is an IPUI. The IPUI is part of the set identifier s that constitute service identity . A a virtual appliance with which terminal is pre subscribed thus is a virtual appliance in which the IPUI stored in the memory of terminal is also part of the set of identifier s which constitute subscribed device identifier of the base station software of the virtual appliance.

In alternative embodiments of the present invention another type of identifier is used to identify a network or base station or base station service which terminal is registered with. The identifier is for example and without limitation a Public Access Rights Key PARK a MAC address IP address etc.

In one alternative embodiment terminal comes with a personal access registration key PARK stored in memory prior to the terminal beginning the registration procedure. Unlike the IPUI the PARK is base station or base station service specific. That is the IPUI is an identifier that is ordinarily assigned to communication terminals and the PARK is an identifier ordinarily assigned to base stations.

Terminal uses the PARK to recognize messages that are associated with a base station or base station service s which the terminal is allowed to access. The PARK is contained in messages that are broadcast by base station . In the alternative embodiment the base station software of the preferred virtual appliance is configured to identify itself with one of its services with the PARK which is pre loaded on terminal . In some embodiments the PARK is part of the set of identifiers that constitute service identifier .

Although in the illustrative embodiment the preferred virtual appliance is a virtual appliances is a virtual appliance with which terminal is pre subscribed it will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention in which the preferred virtual appliance possesses other characteristic s . More precisely in some alternative embodiments of the present invention the preferred virtual appliance is a virtual appliance which comprises a communication protocol stack i.e. stack that exhibits one or more of the following characteristics 

At task registration module executes the preferred virtual appliance to instantiate system software . I

In short the execution of tasks results in the location and execution of a preferred virtual appliance. depicts base station before and after the execution of tasks . Before the execution only system software is executing on base station . After the execution of tasks two system software instances are running system software and system software .

Tasks are described for illustrative purposes. It will be clear to those skilled in the art after reading this disclosure how to perform the tasks associated with in a different order than represented or to perform one or more of the tasks concurrently. Furthermore it will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention that omit one or more of the tasks.

At task registration module locates an information record e.g. user profile etc. which contains a Session Initiation Protocol SIP uniform resource identifier URI . In the illustrative embodiment of the present invention the record is associated with the user identity datum obtained at task . In an alternative embodiment of the present invention the information record is associated with the terminal identity datum.

In the illustrative embodiment the information record is identified by searching a database of information records with a search key that is based on the user identity datum. The database can be located on the base station or it can be located a device that is external to base station . It will be clear to those skilled in the art how to search a database for an information record.

At task registration module associates the SIP URI with subscribed device identifier . In the illustrative embodiment the association is performed by means of a table that relates subscribed device identities to SIP URIs. The table is stored in memory .

At task registration module registers terminal as an endpoint device for the SIP URI that is contained in the record identified at task . The registration is completed by exchanging signaling with server .

In some embodiments of the present invention base station is registered as an endpoint device for the SIP URI. In these embodiments base station forwards all incoming signaling for the SIP URI to terminal .

Furthermore in some embodiments of the present invention more than one terminal from the internal network of base station is associated with the same SIP URI e.g. both terminal and are associated with the URI . In these embodiments base station registration module registers base station as an endpoint for the SIP URI while assigning local extension numbers to the different terminals.

Tasks are described for illustrative purposes. It will be clear to those skilled in the art after reading this disclosure how to perform the tasks associated with in a different order than represented or to perform one or more of the tasks concurrently. Furthermore it will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention that omit one or more of the tasks.

Terminal has the capability to make two kinds of calls. It can make Public Switched Telephone Network PSTN calls by using the voice call service that is provided by stack . And it also can use stack to make voice over Internet Protocol VoIP calls.

When a PSTN call is made the user of terminal dials a PSTN number. In response to the dialing of the PSTN number signaling is exchanged with base station instructing it to set a telephone call over the public switched telephone network PSTN . The signaling is exchanged by using stack .

When a VoIP call is made the user of terminal enters a SIP URI. In response to the entering of the SIP URI signaling protocol stack exchanges SIP signaling with server . The SIP signaling is transmitted by using a data service that is provided by stack .

The illustrative embodiment takes advantage of the capability of terminal to establish both PSTN and VoIP calls to reduce the cost of calls made by terminal . In particular the illustrative embodiment establishes a communication session that uses the SIP network of server in response to a request to establish a call that uses the Public Switched Telephone Network PSTN . Calls that use SIP are often less expensive than calls that use the Public Switched Telephone Network. The manner in which the present invention establishes VoIP calls is described in the discussion with respect to tasks .

At task base station receives from terminal a request to establish a communication session with a far end terminal. The far end terminal is identified by at least one of a Public Switched Telephone Network PSTN number and a local extension number.

At task connector determines whether the far end terminal is a device that is subscribed to base station . For instance when the PSTN number corresponds to a telephone line terminating at base station base station determines that the far end terminal is a terminal that is subscribed to base station . If the far end terminal is subscribed to base station like terminal for example connector proceeds to execute task . Otherwise connector executes task .

At task connector establishes a communication session between terminal and terminal . Task is further described in the discussion with respect to .

At task connector determines whether the far end terminal is associated with a SIIP URI. Connector searches a table that relates PSTN numbers and or extension numbers to SIP URIs. When the PSTN number of the far end terminal is found in the table connector executes task .

At task connector establishes a communication session between terminal and the far end terminal. In the illustrative embodiment connector establishes a first RTP connection with terminal and a second RTP connection with terminal and bridges the two connections. In this way media e.g. voice video text etc. from terminal is forwarded by connector to terminal and vice versa.

In alternative embodiments of the present invention connector establishes a the connection according to different method e.g. establish a SIP communication session with the far end device and then transfer the call to terminal etc. . It will be clear to those skilled in the art how to configure terminal and in order to be able to communicate with each other directly upon an instruction from base station .

Tasks are described for illustrative purposes. It will be clear to those skilled in the art after reading this disclosure how to perform the tasks associated with in a different order than represented or to perform one or more of the tasks concurrently. Furthermore it will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention that omit one or more of the tasks.

At task connector establishes a SIP communication session between terminal and . In the illustrative embodiment connector establishes a first RTP connection with terminal and a second RTP connection with terminal and bridges the two connections. In this way media e.g. voice video text etc. from terminal is forwarded by connector to terminal and vice versa.

In alternative embodiments of the present invention connector establishes a the connection according to different method e.g. establish a SIP communication session with the far end device and then transfer the call to terminal etc. . It will be clear to those skilled in the art how to establish a SIP session between terminal and the far end terminal.

At task base station instructs terminal and terminal to establish a direct radio link with each other. It will be clear to those skilled in the art how to configure terminal and in order to be able to communicate with each other directly upon an instruction from base station .

Tasks are described for illustrative purposes. It will be clear to those skilled in the art after reading this disclosure how to perform the tasks associated with in a different order than represented or to perform one or more of the tasks concurrently. Furthermore it will be clear to those skilled in the art after reading this disclosure how to make and use alternative embodiments of the present invention that omit one or more of the tasks.

It is to be understood that the disclosure teaches just one example of the illustrative embodiment and that many variations of the invention can easily be devised by those skilled in the art after reading this disclosure and that the scope of the present invention is to be determined by the following claims.

