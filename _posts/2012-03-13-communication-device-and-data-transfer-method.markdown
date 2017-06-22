---

title: Communication device and data transfer method
abstract: There is provided a communication device to transfer a received packet to a data terminal device, the communication device being coupled to the data terminal device in a wire or wireless system, the communication device including: a determining unit configured to determine whether or not a compression state of a compressed header added to the packet is a predetermined compression state; and a transfer unit configured to transfer the compressed header to the data terminal device and to transmit an activation request signal used on case of activating a routing module using an RoHC algorithm to the data terminal device including the routing module, when the compression state of the compressed header is the predetermined compression state, or to decompress the compressed header and to transmit the decompressed header to the data terminal device, when the compression state of the compressed header is not the predetermined compression state.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08897296&OS=08897296&RS=08897296
owner: Fujitsu Limited
number: 08897296
owner_city: Kawasaki
owner_country: JP
publication_date: 20120313
---
This application is based upon and claims the benefit of priority of the prior Japanese Patent Application No. 2011 060424 filed on Mar. 18 2011 the entire contents of which are incorporated herein by reference.

There is a communication mode for transferring data transferred from a base station side to a data terminal device such as a personal computer PC or the like using a communication terminal such as a cellular phone as a communication modem or router.

An optimal communication path can be built according to an Internet Protocol IP address by a communication terminal having a router function being connected to a personal digital assistant PDA or PC e.g. Japanese Laid open Patent Publication No. 2005 217994 .

The 3rd Generation Partnership Project 3GPP stipulates Long Term Evolution LTE for 3.9G. With the communication standard of LTE compression or decompression of an IP packet header can be performed at the layer 2 that is Packet Data Convergence Protocol PDCP . That is to say transmission or reception of a compressed header can be performed between a communication terminal and an LTE base station.

According to an aspect of the embodiment there is provided a communication device to transfer a received packet to a data terminal device the communication device being coupled to the data terminal device in a wire or wireless system the communication device including a determining unit configured to determine whether or not a compression state of a compressed header added to the packet is a predetermined compression state and a transfer unit configured to transfer the compressed header to the data terminal device and to transmit an activation request signal used on case of activating a routing module using a robust header compression RoHC algorithm to the data terminal device including the routing module when the compression state of the compressed header is the predetermined compression state or to decompress the compressed header and to transmit the decompressed header to the data terminal device when the compression state of the compressed header is not the predetermined compression state.

The object and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the invention as claimed.

In the event of employing a communication device as a communication modem a transfer protocol such as Universal Serial Bus USB that is one of serial bus standards is employed between a data terminal device such as a communication terminal or PC or the like and this communication terminal.

Therefore even in the event that communication using a compressed header can be performed between the communication terminal may be referred as a communication device and the LTE base station with regard to data transfer to a data terminal device to which the communication terminal is connected header information to be passed through the communication terminal has to be decompressed from a compressed packet to an uncompressed packet. That is to say a compressed packet is decompressed between the communication terminal and the data terminal device so as to agree with transmission or reception of an IP packet.

Therefore data transfer quantity increases depending on connection modes such as Point to Point Protocol PPP being used for connection between the communication terminal and the data terminal device and throughput deteriorates.

Therefore it has been found to be desirable to ease the data processing of the communication terminal connected to the data terminal device. Further it is desirable to improve throughput.

The communication system illustrated in is an example of the communication device and data transfer method according to the present disclosure. This communication system includes user equipment UE and external terminal equipment TE . With this communication system a packet is received at the UE and this packet is transferred to the external TE connected to the UE by cable or radio.

The UE is an example of communication terminals may be referred as communication devices and has a reception function a state determination function and a compressed header communication function . Accordingly cellular phones are an example thereof as long as the UE is equipment having these functions.

The reception function of the UE is a function for receiving data such as a packet having a compressed header to be transmitted from a base station BS in . The state determination function is an example of a state determination unit for determining the compressed state of header information and is a function for determining the compressed state of a compression header appended to a packet. The compressed header communication function is a function for communicating a packet to which a compressed header is appended and transferring the packet to the external TE .

The external TE is an example of data terminal devices and has a header restoration function for restoring a compressed header to the original header. This external TE is connected to the UE by cable or radio and restores the compressed header transmitted from the UE to the original header information. This external TE may be any kind of equipment as long as this equipment is equipment configured of for example a personal computer having the packet restoration function which can perform data processing of a modem or the like.

Next will be referenced regarding header processing of this communication system . illustrates an example of the processing procedure.

The processing procedure illustrated in is an example of the data transfer method according to the present disclosure. With this processing procedure a packet is received at the UE and this packet is transferred from the UE to the external TE .

With this processing procedure a packet is received Operation S and the compressed state of a compressed header appended to this packet is determined Operation S . In the event that this compressed state is a stable state the compressed header is communicated without change according to the determination result thereof and transferred to the external TE Operation S .

Decoding processing of the compressed header is performed at the external TE to which the compressed header has been transferred Operation S .

Advantages according to such header processing will be described below. 1 Restoration processing of the compressed packet received at the UE can be omitted and consequently the processing at the UE can be eased. 2 A compressed header is communicated to the UE and accordingly throughput at the UE can be improved. 3 A compressed header is transferred to the external TE connected to the UE and accordingly header decoding processing by the external TE can be simplified.

The communication system illustrated in is an example of the communication terminal may be referred as the communication device and data transfer method according to the present disclosure.

The UE has various types of control functions such as wireless and cable communication functions data processing function and the functions described in a state notification function and so forth. According to the wireless communication function this UE is connected to an LTE base station BS by radio. The BS is an LTE wireless base station conforming to the communication standard of LTE and is a node that is also referred to as an evolved node B eNode B . Accordingly the UE is connected to another communication terminal that is a subscriber station SS see having the common communication standard via the BS .

The UE includes an Long Term Evolution radio frequency LTE RF a central processing unit CPU core as the wireless side processing unit of a mobile terminal MT L2 and a CPU core as the cable side processing unit of the MT. The L2 is a layer 2. This L2 is a data link layer and is a protocol where with the Open Systems Internet connection OSI reference model representing protocol functions a method for a connected device performing communication is stipulated and methods such as the configuration of a transmission path data identification route selection and so forth are stipulated. The CPU core of this UE is cable connected to the external TE by a cable .

The BS illustrated in includes Robust Header Compression RoHC in an upper layer. Further the BS includes Radio Link Control RLC Medium Access Control MAC and LTE L1 physical layer . The RoHC is a header compression algorithm and has compression and decompression functions for an IP packet header.

The UE includes an LTE wireless function unit a Radio Resource Control RRC Terminal Adaptation function TAF function unit . The LTE wireless function unit is a function unit for controlling the data reception function transmission function and the state determination function of a compressed header and includes a RoHC a RLC a MAC and an LTE L1 in the same way as with the BS . Further the LTE wireless function unit includes a RoHC router an interface between CPUs and a PHY physical layer Bus IF . The PHY is a physical layer interface.

The RRC TAF function unit includes a RoHC router an interface between CPUs a PHY Bus IF a Point to Point Protocol PPP a USB Universal Serial Bus serial interface for peripheral equipment IF L2 and a PHY Bus IF .

The external TE includes an application function unit and this application function unit includes application data User Datagram Protocol UDP Transmission Control Protocol TCP . Further this application function unit includes an IPv4 v6464 a RoHC router termination a PPP a USB IF L2 and a PHY Bus IF .

In this way a communication route is formed from the UE to the external TE and the RoHC routers and which are IP header compression routers are installed in this communication route . In this case the RoHC router is functioned by downlink DL alone for passing data from the BS to the external TE . Thus the packet compression processing at the UE can be omitted by performing header compression using the function for LTE alone to be executed between the UE through the SS see .

The RoHC processing is closely related to wireless handshake. Various state transitions have to be recognized between the UE and the SS . The UE realizes the optimal function roles by compressing and communicating an IP header using the above mentioned downlink alone.

The RoHC routers and communicate a compressed IP packet without change at the time of RoHC execution at the time of header compression . Also in the event that a communication bearer supports data compression the RoHC routers and transfer the compressed IP packet to a transfer destination based on the stored IP header information i.e. the external TE .

The RoHC router terminal installed in the external TE restores the compressed IP packet header using the IP header stored at the time of session start.

The LTE wireless function unit then determines whether the state of IP header compression is stable and when the state is stable informs the RRC TAF function unit of the state thereof. Thus the RoHC router of the RRC TAF function unit communicates a compressed header i.e. an IP packet having a compressed IP packet header to the communication path . In order to realize such processing handshake for control has to be established from the UE side to the external TE i.e. between the RoHC routers and and from these to the RoHC router terminal on the external TE side at the communication route .

The SS includes a Real Time Protocol RTP a User Datagram Protocol UDP an Internet Protocol IP a RoHC a Long Term Evolution Media Access Control LTE MAC Radio Link Control RLC and an LTE PHY which are protocols along with an application software .

With downlink for passing a packet from the SS to the external TE a payload is generated on the SS side by the application software . An RTP header a UDP header and an IP header are appended by the processing of the RTP UDP and IP respectively. Such a complicated header portion is compressed to a RoHC header by the RoHC . That is to say with the IP stage the packet structures of the payload the RTP header UDP header and IP header which are headers are reduced in weight to the packet structure including the RoHC header converted by the compression processing and payload . The RoHC header and payload are structured to a compressed header packet downlink user packet .

The compressed header packet is transferred to the UE via the above mentioned BS by radio through the LTE MAC RLC and LTE PHY .

At the UE the received compressed header reaches the RoHC router through the LTE PHY LTE L1 LTE MAC RLC RoHC and IP routing . With the IP routing determination is made whether or not the compressed state of the compressed header packet is stable and in the event that the compressed state of the compressed header packet is stable performs processing for communicating the compressed header to the above mentioned communication route . This processing includes routing processing such as an activation request of the RoHC router as to the external TE . That is to say in the event that the compressed header is stable the compressed header packet is communicated to the RoHC router and transferred to the external TE from the RoHC router through the PPP USB IF L2 and USB PSY .

The compressed header packet transferred from the UE to the external TE where the header portion is in a compressed state is structured of the above mentioned RoHC header and payload .

With the TE to which this compressed header packet has been transferred the compressed header reaches the USB PHY USB IF L2 PPP RoHC router and reaches the IP UDP TCP stack RTP application data . The RoHC header of the compressed header packet is decompressed to the IP header UDP header and RTP header through such processing and the payload is decoded.

Against such downlink with uplink routing processing is performed so that the compressed header packet generated at the external TE is communicated to the communication route of the UE and reaches the SS via the BS .

This routing processing includes a notification function for informing that in the event that the compressed state of a compressed header is stabilized by the IP header compression function at the time of communicating to the RoHC router the compressed header packet is communicated from the LTE wireless function unit . This notification includes a notification from the LTE wireless function unit to the RRC TAF function unit and a notification from the RRC TAF function unit to the external TE .

A transfer Link Control Protocol LCP of the PPP includes a control function for informing the external TE from the UE of a state where IP header compression is stabilized.

The external TE side includes a restoration function for restoring the original IP header from the IP address information of the basic IP header and so forth in a state in which the handshake of header compression is completed.

According to such an arrangement the following advantages are obtained. 1 With downlink DL header restoration processing can be omitted at the L2 layer PDCP of LTE. 2 The data capacity of the header can be reduced and data increase after escape processing octet conversion by the PPP can be eased. 3 A compressed header packet can be communicated to a communication route from the L2 layer of LTE to the external TE and transferred in a header compressed state and accordingly throughput can be improved. 4 The decoding processing of an IP header can be simplified at the external TE . 5 The above mentioned advantages are obtained without accompanying significant increase in handshake control command . Throughput as to substantial data regions such as streaming data and so forth can be improved.

The UE illustrated in is an example of the communication terminal may be referred as the communication device according to the present disclosure and makes up a modem signal conversion device . This UE includes the CPU core CPU core shared memory and external TE interface . This UE includes an antenna for receiving a wireless signal of a predetermined frequency for example 2 GHz 3 GHz or 3.9 GHz to be transmitted from the BS see .

The CPU core is a function unit that takes care of various types of wireless portion side processing such as regeneration of packet data from radio signals and makes up the above mentioned LTE wireless function unit . With this LTE wireless function unit the functions of the RoHC router function control module master of the RoHC function unit RoHC and evRLC and evMAC are realized. A switch is configured on the output side of this CPU core . This switch is controlled by the RoHC router function control module and the output according to the RoHC and the output of the evRLC are provided from this switch to the shared memory . The RoHC router function control module determines the state of the compressed header and executes routing control. Specifically the RoHC router function control module switches the switch according to the determination result thereof and the switch communicates the compressed header or the restored header of the compressed header by the RoHC .

The shared memory is a storage unit that is shared by the CPU core and CPU core . This shared memory may be configured of a recording medium such as a hard disk drive HDD semiconductor memory or the like. The data received at the UE and packet data such as the above mentioned compressed header packet to be communicated to the external TE are stored in this shared memory . The data is transferred from the CPU core to the CPU core based on the handshake between the CPU cores and with the shared memory as a medium.

The CPU core takes care of cable side processing and makes up the above mentioned RRC TAF function unit . This RRC TAF function unit realizes the functions of a RoHC router function module slave a RoHC terminal function control module master of the user plane U Plane or user information transfer plane and a RoHC router . The RoHC router function control module has slave relationship as to the above mentioned RoHC router function control module that is the master. Based on the handshake between the CPU cores and the RoHC router function control modules and perform cooperative operations but the RoHC router function control module takes care of main driving and the RoHC router function control module is driven.

The RoHC terminal function control module controls the transmission and reception of user data between the UE and the external TE or BS .

The RoHC router makes up a transmission route that intervenes between the shared memory and the USB processing function module and performs data transfer to the external TE side.

The output of the RoHC router is passed to the USB processing function module and output from the CPU core to the external TE interface . The external TE interface is a relay unit for connecting the UE and the external TE by cable. A USB physical layer USB PHY including a switch is provided to this external TE interface . This USB PHY is connected to the external TE by a cable . Thus the data received at the CPU core side is transferred and provided to the external TE as illustrated with an arrow X.

The external TE is configured of a personal computer PC and receives the data transfer from the UE connected thereto by cable. This external TE includes USB memory driver RoHC terminal function control module slave of the U Plane and reception buffer .

Upon data transfer been received from the UE connected to the USB interface by cable the data thereof is stored in the memory .

The RoHC terminal function control module has slave relationship with the above mentioned RoHC router terminal function control module that is the master. Though the RoHC terminal function control modules and perform cooperative operations based on the handshake between the CPU core and the external TE the RoHC terminal function control module takes care of main driving and the RoHC terminal function control module is driven. According to such master and slave relationship the header packet stored in the memory is subjected to RoHC termination processing and the result thereof is provided to the driver .

The decoded IP header and payload in the reception buffer are provided from the memory to the TCP UDP IP stack . In this case Portable Operating System Interface Application Programming Interface POSIX API is employed as an interface for example.

With such a configuration U Plane route control is executed by the RoHC and RoHC router function control module implemented on the CPU core side and the RoHC router function control module and RoHC terminal function control module master implemented on the CPU core side. Thus the U Plane packet having the RoHC header see is transferred to the external TE .

With the UE making up the modem the RoHC router is activated and accordingly the data transferred from the evPDCP layer serves as transfer of the RoHC header compressed header packet and payload. Accordingly though the RoHC function to be used at the LTE wireless function unit is loaded to the PDCP layer decompression of the header of an IP packet does not have to be performed. A sequence for establishing such U Plane path is as described later and so forth .

Next will be referenced regarding the communication system and protocol stack. In the same portions as with are denoted with the same reference numerals.

With this communication system the UE makes up a modem for performing data reception from the BS and data transmission from the external TE and makes up a data card terminal for example.

The protocols of the RoHC routing processing of the RoHC router evPDCP RoHC evRLC evMAC LTE L1 interface and PHY Bus IF are loaded to the LTE wireless function unit of this UE .

The protocols of the RoHC routing processing of the RoHC router interface PHY Bus IF RFC 1661 1662 processing and USB IF are loaded to the RRC TAF function unit .

With the UE an input output unit I O is provided the external TE is connected thereto via this I O . The input output unit is configured of a USB connector or Peripheral Component Interconnect PCI .

The external TE is configured of a host PC or modem. The application data and the protocols of the UDP TCP IP v4 v6 simple RoHC terminal RFC 1661 1662 processing and USB IF are loaded to this external TE . The data provided by downlink is provided to an end user by the application data . The data provided from the end user to the application is appended with the UDP header and IP header and these headers are compressed to the RoHC header . The data appended to this compressed header is transferred from the external TE to the UE .

Next will be referenced regarding an activation sequence. illustrates an example of the activation sequence.

This activation sequence is an example of the data transfer method according to the present disclosure and includes processing for transmitting the compressed header packet according to the RoHC to the external TE using the RoHC routers and . The sequence activation includes a function for performing a message response included in the sequence. Within the UE an activation control message of the RoHC routers and between the LTE L2 wireless function unit and the RRC TAF function unit is employed. This RoHC router activation control message includes a RoHC activation or deactivation request and a RoHC activation or deactivation response.

With this routing control a message from the UE informing the driver of the external TE about the control thereof is employed. This message may be added to the LCP option of the PPP . This message includes a. Configuration Request RoHC router activation or deactivation request b. Configuration Ack RoHC router activation or deactivation response c. Configuration Request IP header reception request and d. Configuration Ack reception completion response .

With the activation sequence illustrated in the BS the LTE L2 wireless function unit and RRC TAF function unit of the UE and the driver and middleware of the external TE are employed. The middleware is software to be used for compression of a header or decompression of a compressed header and is positioned between the OS layer and the application layer.

The BS UE and external TE are in a connected state by communication Attach Operation S . This activation sequence is started. The BS has an initialized state IR State Initialization Refresh State a transition state FO State First Order State or a stable state SO State Second Order State according to communication situations.

With the IR State an IR Packet RoHC that is a compressed packet is transferred from the BS to the LTE L2 wireless function unit Operation S . With the IR State there is no context No Context and this state is a case where there is no valid header information. In this case an uncompressed IR packet is transferred from the LTE L2 wireless function unit to the driver of the external TE Operation S . The IP packet is transferred from this driver to the middleware of the external TE Operation S .

With the FO State the IR DYN packet RoHC is transferred to the LTE L2 wireless function unit Operation S . This case is the case of Static Context and is a case where updating of a dynamic Dynamic field has to be performed. In this case the IP packet uncompressed packet is transferred from the LTE L2 wireless function unit to the driver of the external TE Operation S and the IP packet is transferred from this driver to the middleware of the external TE Operation S .

With the SO State a UO 0 UO 1 or UOR 2 packet RoHC is transferred to the LTE L2 wireless function unit Operation S . This case is Full Context and is a case where the entire field information has correctly been decoded. In this case the IP packet uncompressed packet is transferred from the LTE L2 wireless function unit to the driver of the external TE Operation S . The IP packet is transferred from the driver to the middleware of the external TE Operation S .

RoHC control information is issued from the LTE L2 wireless function unit and the IP header is saved in the shared memory Operation . Upon proceeding to a transfer state in the IP header maximum compressed state Operation S a RoHC router activation request is issued from the LTE L2 to the RRC TAF Operation S and an LCP Configuration Request RoHC router activation request is transferred from the RRC TAF to the driver Operation S . In response to this an LCP Configuration Ack RoHC router activation response is transferred to the TAF Operation S .

The RoHC control information stored in the shard memory is issued from the LTE L2 wireless function unit to the RRC TAF Operation S . An LCP Configuration Request IP header reception request IP header is transferred from the TAF to the driver Operation S and the RoHC control information is stored in the memory of the external TE Operation S . A Configuration Ack reception completion response is transferred from the driver to the TAF Operation S and a RoHC router activation response is transferred from the RRC TAF to the LTE L2 wireless function unit Operation S .

A UO 0 UO 1 or UOR 2 packet RoHC is transferred from the BS to the LTE L2 wireless function unit Operation S and header confirmation is performed at the LTE L2 wireless function unit Operation S . If the result of the header confirmation is OK a UO 0 UO 1 or UOR 2 packet RoHC is transferred from the LTE L2 wireless function unit to the driver Operation S . At the driver header restoration is executed Operation S and the IP packet is passed to the middleware Operation S .

In this way at the L2 layer of the LTE function unit an IP packet to which an uncompressed header is appended is transmitted to the external TE until the RoHC becomes a Full Context state maximum compressed state . An activation request for the RoHC router is then transmitted to the external TE side in the maximally compressed state Full Context and handshake is started.

Next will be referenced regarding the release processing of compressed packet transfer. illustrates a processing sequence for releasing compressed packet transfer.

The processing sequence illustrated in is an example of the data transfer method according to the present disclosure and in the event of having detected an error such as NG in a cyclic redundancy check CRC function or the like the LTE function unit determines this to be NG in the RoHC processing and releases the RoHC processing of the BS at the L2 layer PDCP layer in the case of LTE . Simultaneously with release a RoHC router deactivation request is transmitted to the external TE side and RoHC restoration at the external TE is stopped. That is to say the LTE function unit executes a processing sequence for releasing compressed packet transfer.

With the processing sequence illustrated in in the event that the BS UE and external TE are in a transfer state in the IP header maximum compressed state Operation S a UO 0 UO 1 or UOR 2 packet RoHC is transferred from the BS to the LTE L2 wireless function unit Operation S . At the LTE L2 wireless function unit header confirmation is performed Operation S and in the event that the result of the header confirmation is OK a UO 0 UO 1 or UOR 2 packet RoHC is transferred from the LTE L2 wireless function unit to the driver Operation S . At the driver header restoration is executed Operation S and the IP packet is provided to the middleware Operation S .

On the other hand a UO 0 UO 1 or UOR 2 packet RoHC is transferred from the BS Operation S and as a result of the LTE L2 wireless function unit having performed header confirmation Operation S there may be a case of NG. In this case a NACK packet RoHC is transferred from the LTE L2 wireless function unit to the BS Operation S . Thus transition is made to a transfer state with a normal IP header even between the BS and the UE Operation S .

Upon proceeding to a transfer state with a normal IP header the LTE L2 wireless function unit discards the IP header in the shared memory where the RoHC control information is stored Operation S and issues a RoHC router deactivation request to the TAF Operation S . The TAF transfers an LCP Configuration Request RoHC router deactivation request to the driver Operation S . In response to this the driver discards the IP header in the memory where the RoHC control information is stored Operation S and transfers an LCP Configuration Ack RoHC router deactivation response to the RRC TAF function unit Operation S . The RRC TAF function unit which has received this transfers a RoHC deactivation response to the LTE L2 wireless function unit Operation S .

The BS side that has proceeded to the IR State transfers the IR packet RoHC to the LTE L2 wireless function unit of the UE Operation S . In the case of this no context an uncompressed IP packet is transferred from the LTE L2 wireless function unit to the driver of the external TE Operation S and the IP packet is transferred from the driver to the middleware of the external TE Operation S .

Next and will be referenced regarding function control modules such as the RoHC router and so forth. illustrates a flowchart of the RoHC routing control LTE processing side . illustrates a flowchart of the RoHC routing TAF side . illustrates a flowchart of the simple RoHC termination processing driver side .

The processing procedure illustrated in is an example of a data transfer method according to the preset disclosure and is processing on the LTE function unit side. Upon starting this processing procedure a RoHC transition state is obtained Operation S . This RoHC transition state is executed by polling from a finite state machine FSM in the RoHC router function control module . The RoHC transition state includes three states of no context No Context static context Static Context and full context Full Context and one state of these is obtained.

Determination is made whether the RoHC transition state is full context Operation S and if full context YES in Operation S determination is made whether or not a router activation flag is on ON Operation S . In the event that the router activation flag is not on NO in Operation S a RoHC router control sequence I is executed Operation S . This RoHC control sequence I Operation S is in conjunction with Operation S of the RoHC routing on the TAF side and is also in conjunction with Operations S and S of the RoHC routing on the TAF side.

After the processing of the RoHC router control sequence I Operation S determination is made whether or not activation of the RoHC router has succeeded Operation S . In the event that activation of the RoHC router has succeeded YES in Operation S IP header restoration is deactivated OFF and turning on of the router activation flag is performed Operation S . In this case the compressed packet transfer processing is executed Operation S .

In the event that the RoHC transition state is not full context in Operation S NO in Operation S IP header restoration is performed ON and the router activation flag is turned off Operation S . In this case though the IP packet transfer processing is executed Operation S the compressed packet transfer processing is not performed.

In the event that the router activation flag is on in Operation S YES in Operation S the compressed packet transfer processing is performed Operation S .

Also in the event that activation of the RoHC router has failed in Operation S NO in Operation S the sequence proceeds to Operation S and the same processing Operations S and S as with a case other than full context is executed.

After such processing determination is made whether or not the application has ended Operation S and in the event that the application has not ended NO in Operation S the sequence returns to Operation S. Accordingly such processing is repeatedly executed until the application has ended and according to the end of the application YES in Operation S this processing is ended.

The processing procedure illustrated in is an example of the data transfer method according to the present disclosure and is processing on the RRC TAF function unit side. Upon starting this processing procedure determination is made whether or not there has been a RoHC router activation deactivation request Operation S . In the event that there has been a RoHC router activation deactivation request YES in Operation S a RoHC router control sequence II is executed Operation S . In the event that there has been no RoHC router activation deactivation request NO in Operation S this processing is ended. This RoHC router control sequence II is in conjunction with Operations S S and S on the driver side.

In the event of having executed the RoHC router control sequence II determination is made whether or not the external TE has agreed with the request Operation S . In the event that the external TE has agreed with the request YES in Operation S an activation success notification of the RoHC router is issued Operation S and this processing is ended.

Also in the event that the external TE has not agreed with the request NO in Operation S an activation failure deactivation notification of the RoHC router is issued Operation S and this processing is ended.

The processing procedure illustrated in is an example of the data transfer method according to the present disclosure and is processing of the simple RoHC termination processing driver side . Upon starting this processing procedure determination is made whether or not there has been a RoHC termination activation deactivation request Operation S . In the event that there has been a RoHC termination activation deactivation request YES in Operation S a RoHC router control sequence III is executed Operation S . In the event that there has been no RoHC router termination activation deactivation request NO in Operation S the sequence proceeds to Operation S.

In the event of having executed the RoHC router control sequence III determination is made whether or not the RoHC information has been received Operation S . In the event that the RoHC information has been received YES in Operation S a RoHC termination activation success notification is issued Operation S IP header restoration processing ON is started Operation S and compressed packet decompression processing conforming to 3GPP is executed Operation S .

In the event that no RoHC information has been received NO in Operation S a RoHC termination activation failure deactivation notification is issued Operation S and the IP header restoration processing is deactivated OFF Operation S . In this case IP packet reception processing is performed Operation S .

After the compressed packet decompression processing Operation S or IP packet reception processing Operation S determination is made whether or not the application is completed Operation S . In the event that the application is not completed NO in Operation S the sequence returns to Operation S and the above mentioned processing is continued until the application is completed. In the event that the application is completed YES in Operation S this processing is ended.

With the RoHC router control sequence I in the event there has been no response from the RoHC router function control module slave side the RoHC router is not activated after elapse of a certain period of time and the processing is completed.

Upon starting this RoHC router control sequence I as illustrated in a RoHC router activation request message is transmitted Operation S and determination is made whether or not the RoHC router activation response message has been received Operation S .

In the event that no RoHC router activation response message has been received NO in Operation S the sequence proceeds to retry processing the RoHC router activation response message is monitored during a certain period of time and a retry timer is incremented Operation S . The time out of the retry timer is monitored Operation S and reception of the RoHC router activation response message is monitored until the retry timer times out Operation S . In the event that the retry timer times out YES in Operation S this processing is ended.

In the event that the RoHC router activation response message has been received YES in Operation S the transfer switch for RoHC router is turned on Operation S and this processing is ended.

With the RoHC router control sequence II the processing is ended in a stage where the timer lapses no response is transmitted to the RoHC control unit on the LTE side and the RoHC router is not activated.

Upon starting this RoHC router control sequence II as illustrated in determination is made whether or not the RoHC router deactivation request message has been received Operation S . In the event that the RoHC router deactivation request message has been received YES in Operation S the RoHC router is deactivated Operation S .

In the event that the RoHC router deactivation request message has not been received NO in Operation S determination is made whether or not the RoHC router activation request message has been received Operation S . In the event that the RoHC router activation request message has not been received NO in Operation S the sequence returns to Operation S monitoring of reception of the RoHC router deactivation request message Operation S and determination regarding reception of the RoHC router activation request message Operation S are performed.

In the event that the RoHC router activation request message has been received YES in Operation S the RoHC router activation request message is transmitted as LCP Configuration Ack RoHC router activation response Operation S . Determination is made whether or not LCP the RoHC router activation response message has been received Operation S and in the event that the RoHC router activation response message has not been received NO in Operation S the retry timer is incremented Operation S . The timeout of the retry timer is monitored Operation S and elapse of a predetermined period of time i.e. reception of the RoHC router activation response message is monitored until the retry timer times out Operation S . In the event that a predetermined period of time has elapsed and the RoHC router activation response message has not been received during the predetermined period of time thereof YES in Operation S this processing is ended.

In the event that the RoHC router activation response message has been received YES in Operation S LCP the IP header reception request message is transmitted Operation S . Determination is made whether or not LCP the reception completion response message has been received Operation S and in the event that the reception completion response message has not been received NO in Operation S the retry timer is incremented Operation S . The timeout of the retry timer is monitored Operation S and elapse of a predetermined period of time i.e. reception of the reception completion response message is monitored until the retry timer times out Operation S . In the event that a predetermined period of time has elapsed and the reception completion response message has not been received during the predetermined period of time thereof YES in Operation S this processing is ended.

In the event that the reception completion response message has been received YES in Operation S the RoHC router activation response message is transmitted Operation S and this processing is ended.

With the RoHC router control sequence III in the event that no response has been received the processing is ended in a stage where the timer lapses no response is transmitted to the RoHC routing unit on the TAF side and the RoHC router is not activated.

Upon starting this RoHC router control sequence III as illustrated in determination is made whether or not LCP the RoHC router deactivation request message has been received Operation S . In the event that the RoHC router deactivation request message has been received YES in Operation S the RoHC router is deactivated Operation S .

In the event that the RoHC router deactivation request message has not been received NO in Operation S determination is made whether or not LCP the RoHC router activation request message has been received Operation S . In the event that the RoHC router activation request message has not been received NO in Operation S the sequence returns to Operation S and reception of the RoHC router deactivation request message or RoHC router activation request message is monitored Operations S and S .

In the event that the RoHC router activation request message has been received YES in Operation S the RoHC router activation response message is transmitted Operation S . After this transmission determination is made whether or not LCP the IP header reception request message has been received Operation S .

In the event that LCP the IP header reception request message has not been received NO in Operation S the retry timer is incremented Operation S . The timeout of the retry timer is monitored Operation S and elapse of a predetermined period of time i.e. reception of the IP header reception request message is monitored until the retry timer times out Operation S . In the event that a predetermined period of time has elapsed and the IP header reception request message has not been received during the predetermined period of time thereof YES in Operation S this processing is ended.

In the event that LCP the IP header reception request message has been received YES in Operation S the IP header information is saved conforming to RoHC Operation S . The RoHC decompression function is activated conforming to RoHC Operation S reception completion response message is transmitted Operation S and this processing is ended. Data Transfer of RoHC Router In Case of RoHC Router Being off 

With downlink DL data is transferred from the UE to the external TE . At the CPU core of the UE the RoHC function control module master carries out status polling as to the RoHC function unit conforming to 3GPP standard and in a case other than full context the RoHC router is switched to deactivation off .

In the event that the RoHC router is off at the CPU core the RoHC header is subjected to compressed header decompression processing with PDCP SUD PDCP layer payload . That is to say the RoHC header that is a compressed header is decompressed to an IP header a UPD header and an RTP header. Therefore the decompressed RoHC header is structured of a payload to which the IP header UPD header and RTP header are appended. The payload is image data for example.

The switch communicates the payload image data to which the IP header UPD header and RTP header are appended since the RoHC router is off and transfers the payload to the CPU core . The RoHC router on the CPU core side is turned off in conjunction with turning off of the RoHC router on the CPU core side. Therefore the CPU core is in a through state as to data transfer and the image data to which the IP header UPD header and RTP header are appended is transferred to the driver of the external TE without change.

With downlink DL it is as described above that data is transferred from the UE to the external TE . At the CPU core of the UE the RoHC function control module master carries out status polling as to the RoHC function unit conforming to 3GPP standard and in the event of full context the RoHC router is turned on.

In the event that the RoHC router is on the CPU core deactivates the decompression processing of the RoHC header that is compressed header. That is to say the RoHC header is kept as it is. In this case the data is structured of the payload to which the RoHC header is appended. In this case the payload is image data for example.

The switch communicates the image data to which the RoHC header is appended since the RoHC router is on and transfers the image data to the CPU core . The RoHC router on the CPU core side is turned on in conjunction with turning on of the RoHC router on the CPU core side. Therefore the CPU core is in a through state as to data transfer and the image data payload to which the RoHC header is appended is transferred to the driver of the external TE without change.

At the driver to which the RoHC header and payload have been provided a RoHC decompression processing function unit decompresses the RoHC header to an IP header UPD header and RTP header.

In this way in the event that the RoHC router is on the switch is switched the RoHC function unit on the LTE function unit side deactivates decompression of the RoHC header that is a compressed header. The RoHC header that is a compressed header is transferred to the driver without change. The driver carries out only decompression with the full context of the RoHC header . The decompression processing of the RoHC header conforms to the RoHC standard. In this case the header information is the entire header information such as an IP header UDP header RTP header and so forth to be stored with normal RoHC.

With the communication system illustrated in the UE is configured of for example a cellular phone the external TE is configured of a PC and these are connected by cable using the USB cable .

The UE includes an LTE wireless RF unit a baseband processing BB unit a display unit an audio input output unit a processor a storage unit and an external TE interface unit and makes up a modem which transmits or receives the above mentioned packet data.

The RF unit includes an antenna for transmission and reception and performs transmission or reception of wireless waves as to the base stations such as the above mentioned BS and so forth. The BB unit is controlled by the processor modulates carrier signals using data signals and audio signals or demodulates the data signals and audio signals from the reception signals of the RF unit . The display unit is configured of for example an LCD Liquid Crystal Display and presents transmission data and reception data as information such as visible letters symbols and so forth. The audio input output unit performs input processing of the audio signals from a microphone and plays the audio signals demodulated from the reception signals as audio.

The processor executes an operating system OS or application program stored in the storage unit and realizes the above mentioned packet communication method. This processor is configured of the above mentioned CPU cores and . The storage unit includes a read only memory ROM and a random access memory RAM and makes up a program storage unit or data storage unit. The above mentioned OS and a program for realizing the packet communication method are stored in the program storage unit. The RAM is used for storage of received packet data and for a work area. The above mentioned shard memory is configured of this storage unit . This storage unit is configured of a recording medium such as semiconductor memory such as flash ROM or the like. A retry timer that monitors various processing time is connected to the processor .

The external TE interface unit is a connection unit as to an external device and includes for example the USB input output unit and this USB input output unit is connected to the external TE via the USB cable .

The external TE is an example of a data terminal device or packet processing device and is configured of a PC or modem. The external TE illustrated in includes an interface unit a processor and a storage unit .

The interface unit is a connection unit as to an external device and includes for example a USB input output unit and the UE is connected to this USB input output unit via the above mentioned USB cable .

The processor executes an OS or application program stored in the storage unit and realizes the above mentioned packet communication method. In the case of downlink DL the processor decodes an IP packet from compressed packets transferred from the UE .

The storage unit includes a HDD and RAM and makes up a program storage unit or data storage unit. The program storage unit is configured of the HDD . With this program storage unit the above mentioned OS a program that realizes the packet communication method and the above mentioned driver are stored. The RAM is used for storage of received packet data and for a work area. This storage unit is configured of a recording medium such as a HDD device or semiconductor memory such as a flash ROM or the like.

Next will be referenced regarding the configuration at the time of RoHC header compression. illustrates the above mentioned UO 0 packet illustrates the above mentioned UO 1 packet and illustrates the above mentioned UOR 2 packet.

With the UO 0 packet as illustrated in the header portion has sequence number SN bits and cyclic redundancy check CRC bits. The SN bits indicate the sequence of data. The CRC bits are used for a right or wrong check of the bit configuration. The SN bits are four bits the CRC bits are three bits which are configured of one octet. Also the payload is also 1 octet data.

With the UO 1 packet as illustrated in the header portion has 10 two bits timestamp TS bits and a marker M bit in addition to the configuration of the UO 0. The TS bits represent time information. Also the M bit represents the boundary of the data.

With the UOR 2 packet as illustrated in the header portion has 110 three bits SN six bits TS most significant bit MSB five bits and an extension X bit in addition to the configuration of the UO 1.

Next will be referenced regarding the ratio of header compression. illustrates the ratio of header compression at the time of the maximum compression.

In the event that the protocol header is IP TCP while a normal header size bytes is 40 bytes the size at the time of RoHC compression is compressed to 4 bytes . In this case the compression ratio 40 4 40 100 90 .

In the event that the protocol header is IP UDP while a normal header size bytes is 28 bytes the size at the time of RoHC compression is compressed to 1 byte . In this case the compression ratio 28 1 28 100 96.4 .

In the event that the protocol header is IP UDP RTP while a normal header size bytes is 40 bytes the size at the time of RoHC compression is compressed to 1 byte . In this case the compression ratio 40 1 40 100 97.5 .

As can be apparent from such compression ratios use of compressed packets can improve the transfer speed of data enable efficient communication and also contribute to effective use of network resources.

According to the above mentioned embodiments the following advantages are obtained. 1 A function for communicating compressed IP packets without change at the time of RoHC implementation is provided as the RoHC router and accordingly a compressed header packet can be communicated from the UE to the external TE data processing on the UE side can be eased and throughput can be improved. 2 The RoHC router termination function is provided into the external TE and accordingly the original packet can be restored from the compressed header packet transferred from the UE . 3 With the RoHC router termination a compressed header packet can readily be restored using the IP header saved at the time of compression operation negotiation completion by downlink DL and accordingly data processing on the external TE side can be eased. 4 In the event that the RoHC is supported by a communication bearer a compressed IP packet can be transmitted to a transfer destination based on the saved IP header information.

 1 With the above embodiments though the UE and external TE have been connected by cable using the cable these connection modes are not restricted to cable connection. Wireless connection may be employed and accordingly Bluetooth connection may be employed. With this Bluetooth connection as illustrated in the RRC TAF function unit of the UE includes Bluetooth L2 and Bluetooth L1 as interfaces. In response to this the application function unit of the external TE has to include Bluetooth L2 and Bluetooth L1 as interfaces. In this case an antenna for Bluetooth is provided to the UE side and a similar antenna is provided to the external TE side and transmission and reception of radio waves conforming to the Bluetooth standard are performed. According to even wireless connection the compressed header communicated through the UE can be transferred to the external TE and can be decompressed to the original header on the external TE side.

 2 With the above embodiments though the communication standard for LTE has been employed as the protocol of the wireless connection between the BS and the UE the communication standard for LTE is not restricted to this. For example WiMAX Worldwide Interoperability for Microwave Access may be employed. In this case as illustrated in a WiMAX RF unit is employed and MAC and MAC are employed as the protocols of the BS and LTE function unit respectively. An arrangement may be made wherein the BS includes a WiMAX L1 function unit and the LTE function unit of the UE includes a WiMAX L1 function unit and communication connection according to WiMAX is performed between both.

 3 With the above embodiments though the BS and UE has been connected by radio an arrangement may be made wherein communication is performed by another communication device standing between the BS and the UE .

The communication system illustrated in is configured to transmit or receive a compressed header packet between the UE and the BS in the same way as with the above mentioned communication system . illustrates a hardware configuration according to the communication standard of LTE and illustrates a protocol structure. Though these configuration and structure are the same as those in the above mentioned communication system these configuration and structure differ from those in the communication system in that the RoHC routers and are not provided.

With the communication system according to this comparative example header compression is performed between an SS and a UE by RoHC. Therefore with downlink DL from the BS toward the UE a compressed header packet is transmitted from the BS to the UE . This packet structure includes a RoHC header compressed from an IP header UDP header and RTP header and a payload.

This compressed header packet is decompressed and decoded into an actual size of IP packet by IP packet routing processing at the UE . This actual size of IP packet is transmitted or received between the UE and an external TE .

The RoHC employed in LTE and WiMAX is very effective for an IP packet of which the payload is not great. Examples of an IP packet of which the payload is not great include Voice over Internet Protocol VoIP .

The communication system according to this comparative example has the following problems. These problems have been solved in the above embodiments.

 1 In the event that a compressed header is decompressed to an IP header UDP header and RTP header and an actual size of IP packet is transmitted or received between the external TE and the UE the load of the UE and external TE increases. The UE has to have the LTE function for response to the BS and the modem function for the external TE and performs transfer of the header information between IP packet transfer accompanied with IP header compression and IP packet transfer. That is to say the UE has to perform compressed packet decompression processing in accordance with transmission or reception of an IP packet as to the external TE .

 2 With the UE in the event that Point to Point Protocol PPP is employed in the worst case the packet structure has as twice as many data transfer quantity as this structure which has a bad effect on throughput.

 3 In the event of employing the UE as a modem of the external TE a transfer protocol such as USB or the like has to be employed between the UE and the external TE and therefore IP packets over an upper layer are transferred without compression at the UE serving as a router.

 4 The UE transfers omissible header information between IP packet transfer according to IP header compression serving as an LTE function for base station response and IP packet transfer serving as a modem function for external TE. Therefore the UE decompresses compressed packets so as to agree with transmission or reception of IP packets at the external TE .

Also the above mentioned user equipment UE may include a program memory in which data is stored and a processor for executing a program and a part of the above mentioned functions of the UE may be realized by software.

All examples and conditional language recited herein are intended for pedagogical purposes to aid the reader in understanding the invention and the concepts contributed by the inventor to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although the embodiments of the present invention have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

