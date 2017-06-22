---

title: Method for transferring data between a first device and a second device
abstract: According to an aspect of this disclosure, a method for transferring data from a first device to a second device is described, the method comprising: writing data into a data-sharing application of an operating system of the first device; requesting a data-sharing application to select a physical layer data transmission technology; the data-sharing application selecting a physical layer data transmission technology; connecting a data-sharing of an operating system of the second device via the selected physical layer data transmission technology; and transferring the data from the data-sharing application of the first device to the data-sharing application of the second device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08725808&OS=08725808&RS=08725808
owner: Intel Mobile Communications GmbH
number: 08725808
owner_city: Neubiberg
owner_country: DE
publication_date: 20120510
---
The present invention relates generally to methods for transferring data from a first device to a second device and communication device.

With the increasing use of computing devices such as mobile phones e.g. smartphones tablet computers notebook computers desktop computers and the fact that a single user owns and uses a plurality of such devices the quick and simple transfer of information between such computing devices e.g. between any kind of applications running on two different computing devices is often needed or desired.

Typically software applications do not share a common communication interface or protocol. Thus it may not be possible to directly exchange information between software applications running on different computing devices if the software applications have not been specifically designed to support this.

For transferring data from a first application also referred to as source application running on a first computing device also referred to as source device to a second application also referred to as destination application running on a second computing device also referred to as destination device the following mechanisms may for example be used 

1 File export import Data is exported from the source application into a file in the source device the file is transferred from the source device to the destination device and the file is imported into the destination application in the destination device. The transfer of the file can for example be performed through a a physical storage device e.g. a USB Memory a Memory Card an external hard disk etc. or b through a data communication link USB cable Ethernet Cable Bluetooth WLAN Internet etc. using a file transfer application or a messaging application.

This however requires file storage availability Due to file storage limitations or permission constraints this might not be possible. Further this requires extra steps for the user find a location to create the file in the source device file system open a file transfer or messaging application finding the transferred file it in the destination device file system. Additionally this approach typically creates temporary files in source and destination device that the user has to take care of cleaning. The files created in the source device and the destination device may introduce security and privacy problems. Even if they are deleted by the user it is possible to recover deleted files from storage media.

2 Embedding the data into a message Email Chat or similar The user exports copies the data from the source application to the clipboard of the operating system of the source device. A communication application e.g. an email client is opened and the data is imported e.g. pasted into a message e.g. an email message . The message is sent e.g. to the user s own email address or to another address. The user opens the messaging application in the destination device and copies the data into the clipboard of the operating system of the destination device. Then in the destination application a paste operation may be used to supply the data to the destination application running on the destination device.

This approach requires connectivity to a central messaging server from both the source device and the destination device. If this server is remote this might incur extra costs for the user. Messaging Internet servers are typically operated by 3party companies and it is typically difficult to ensure the security and privacy of messages sent through them. Message encryption may thus be needed adding extra steps for the user. Additionally for example the user may have to delete later the message from their sent or inbox messaging application folders.

3 Cloud bulletin board The user copies data from a source application to a bulletin board desktop or web application. The data is stored in a cloud server e.g. typically a server in the Internet . The user opens the bulletin board application in the destination device and copies the data into the local clipboard of the operating system of the destination device.

This approach requires connectivity to the cloud server. Connectivity might not be available on remote or crowded areas e.g. in a stadium . Further this approach requires accepting a contract with a 3party cloud service provider. Additionally costs might be incurred for big data amounts. Further the security and privacy of the data may not be ensured such that the user may be required to take extra steps to encrypt and decrypt the data.

According to one aspect of this disclosure a method for transferring data between a first device and a second device is provided the method comprising writing data into a data sharing application of an operating system of the first device requesting a data sharing application to select a physical layer data transmission technology the data sharing application selecting a physical layer data transmission technology connecting a data sharing application of an operating system of the second device via the selected physical layer data transmission technology and transferring the data from the data sharing application of the first device to the data sharing application of the second device.

According to another aspect of this disclosure a communication device according to the above method for transferring data from a first device to a second device is provided.

The following detailed description refers to the accompanying drawings that show by way of illustration specific details and aspects of this disclosure in which the invention may be practiced.

The word exemplary is used herein to mean serving as an example instance or illustration . Any aspect of this disclosure or design described herein as exemplary is not necessarily to be construed as preferred or advantageous over other aspects of this disclosure or designs.

A circuit may be understood as any kind of a logic implementing entity which may be hardware software firmware or any combination thereof. Thus a circuit may be a hard wired logic circuit or a programmable logic circuit such as a programmable processor e.g. a microprocessor e.g. a Complex Instruction Set Computer CISC processor or a Reduced Instruction Set Computer RISC processor . A circuit may also be software being implemented or executed by a processor e.g. any kind of computer program e.g. a computer program using a virtual machine code such as e.g. Java. Any other kind of implementation of the respective functions which will be described in more detail below may also be understood as a circuit .

The terms coupling or connection are intended to include a direct coupling or direct connection as well as an indirect coupling or indirect connection respectively.

The term protocol is intended to include any piece of software and or hardware that is provided to implement part of any layer of the communication definition. Protocol may include the functionality of one or more of the following layers physical layer layer data link layer layer network layer layer or any other sub layer of the mentioned layers or any upper layer.

The communication protocol layers and its respective entities which will be described in the following may be implemented in hardware in software in firmware or partially in hardware and or partially in software and or partially in firmware. One or more communication protocol layers and its respective entities may be implemented by one or more circuits. At least two communication protocol layers may be commonly implemented by one or more circuits.

In order to better provide data sharing among devices a cross device data sharing application is provided which connects the data sharing applications of the operating systems of multiple computing devices. This for example allows the user of the devices to copy data in one device and paste it into an application of another device. It removes from the user the burden of importing and exporting data between applications. According to one aspect of this disclosure the cross device data sharing approach is based on an application referred to as data sharing application running in all devices whose Operating System clipboards should be connected.

The data sharing application uses the API Application Programming Interface of the data sharing application of the operating system of the devices to 1 read data 2 write data from the data sharing application of the operating system and 3 get notifications on the event of the user copying data in the operating system data sharing application.

A method for transferring data from a first device to a second device which may include the usage of a data sharing application is illustrated in .

In data is written into a data sharing application of an operating system of the first device e.g. a clipboard of the operating system of the first device e.g. by an application running on the first device.

In a data sharing application is requested e.g. by a controller of the first device to select a physical layer data transmission technology.

In a data sharing application of an operating system of the second device e.g. a clipboard of the operating system of the second device is connected via the selected physical layer data transmission technology e.g. by a communication middleware of the first device.

In the data is transferred e.g. by the communication middleware of the first device from the data sharing application of the first device to the data sharing application of the second device.

In other words an application referred to as data sharing application or shared clipboard application for example is provided in a first device source device which selects a transmission technology to transfer all or some of the operating system data sharing application content of the first device to a second device. According to the selection data from the operating system clipboard is transferred to the clipboard of the second device. In other words the clipboard between two devices is synchronized wherein a shared clipboard applications which is located in a higher communication layer than the operating system selects a physical layer transmission technology for the synchronization.

The architecture layer can for example be understood as an architecture layer according to the OSI Open Systems Interconnection reference model.

According to another aspect of this disclosure communication devices according to the above method for transferring data from a first device to a second device and a method for receiving data are provided.

It should be noted that aspects of this disclosure described in context of the transferring method are analogously valid for the devices and the receiving method and vice versa.

The operating system may for example be a Windows or Windows based operating system or a Unix Linux or Unix Linux based operating system or a MacOS. The operating system may for example be an operating system for handheld devices such as iOS Android Windows Mobile etc.

By way of example the physical layer data transmission technology may be the physical layer data transmission technology of one of the following communication technologies 

a Short Range radio communication technology which may include e.g. a Bluetooth radio communication technology an Ultra Wide Band UWB radio communication technology and or a Wireless Local Area Network radio communication technology e.g. according to an IEEE 802.11 e.g. IEEE 802.11n radio communication standard IrDA Infrared Data Association Z Wave and ZigBee HiperLAN 2 HIgh PErformance Radio LAN an alternative ATM like 5 GHz standardized technology IEEE 802.11a 5 GHz IEEE 802.11g 2.4 GHz IEEE 802.11n IEEE 802.11VHT VHT Very High Throughput 

a Metropolitan Area System radio communication technology which may include e.g. a Worldwide Interoperability for Microwave Access WiMax e.g. according to an IEEE 802.16 radio communication standard e.g. WiMax fixed or WiMax mobile WiPro HiperMAN High Performance Radio Metropolitan Area Network and or IEEE 802.16m Advanced Air Interface 

a Cellular Wide Area radio communication technology which may include e.g. a Global System for Mobile Communications GSM radio communication technology a General Packet Radio Service GPRS radio communication technology an Enhanced Data Rates for GSM Evolution EDGE radio communication technology and or a Third Generation Partnership Project 3GPP radio communication technology e.g. UMTS Universal Mobile Telecommunications System FOMA Freedom of Multimedia Access 3GPP LTE Long Term Evolution 3GPP LTE Advanced Long Term Evolution Advanced CDMA2000 Code division multiple access 2000 CDPD Cellular Digital Packet Data Mobitex 3G Third Generation CSD Circuit Switched Data HSCSD High Speed Circuit Switched Data UMTS 3G Universal Mobile Telecommunications System Third Generation W CDMA UMTS Wideband Code Division Multiple Access Universal Mobile Telecommunications System HSPA High Speed Packet Access HSDPA High Speed Downlink Packet Access HSUPA High Speed Uplink Packet Access HSPA High Speed Packet Access Plus UMTS TDD Universal Mobile Telecommunications System Time Division Duplex TD CDMA Time Division Code Division Multiple Access TD CDMA Time Division Synchronous Code Division Multiple Access 3GPP Rel. 8 Pre 4G 3rd Generation Partnership Project Release 8 Pre 4th Generation UTRA UMTS Terrestrial Radio Access E UTRA Evolved UMTS Terrestrial Radio Access LTE Advanced 4G Long Term Evolution Advanced 4th Generation cdmaOne 2G CDMA2000 3G Code division multiple access 2000 Third generation EV DO Evolution Data Optimized or Evolution Data Only AMPS 1G Advanced Mobile Phone System 1st Generation TACS ETACS Total Access Communication System Extended Total Access Communication System D AMPS 2G Digital AMPS 2nd Generation PTT Push to talk MTS Mobile Telephone System IMTS Improved Mobile Telephone System AMTS Advanced Mobile Telephone System OLT Norwegian for Offentlig Landmobil Telefoni Public Land Mobile Telephony MTD Swedish abbreviation for Mobiltelefonisystem D or Mobile telephony system D Autotel PALM Public Automated Land Mobile ARP Finnish for Autoradiopuhelin car radio phone NMT Nordic Mobile Telephony Hicap High capacity version of NTT Nippon Telegraph and Telephone CDPD Cellular Digital Packet Data Mobitex DataTAC iDEN Integrated Digital Enhanced Network PDC Personal Digital Cellular CSD Circuit Switched Data PHS Personal Handy phone System WiDEN Wideband Integrated Digital Enhanced Network iBurst Unlicensed Mobile Access UMA also referred to as also referred to as 3GPP Generic Access Network or GAN standard .

Short Range radio communication technologies may include the following Short Range radio communication technology sub families 

personal area networks Wireless PANs radio communication sub family which may include e.g. IrDA Infrared Data Association Bluetooth UWB Z Wave and ZigBee and

wireless local area networks W LANs radio communication sub family which may include e.g. HiperLAN 2 High PErformance Radio LAN an alternative ATM like 5 GHz standardized technology IEEE 802.11a 5 GHz IEEE 802.11g 2.4 GHz IEEE 802.11n IEEE 802.11VHT VHT Very High Throughput .

Metropolitan Area System radio communication technology families may include the following Metropolitan Area System radio communication technology sub families 

a Wireless campus area networks W CANs radio communication sub family which may be considered one form of a metropolitan area network specific to an academic setting and which may include e.g. WiMAX WiPro HiperMAN High Performance Radio Metropolitan Area Network or IEEE 802.16m Advanced Air Interface and

a Wireless metropolitan area networks W MANs radio communication sub family which may be limited to a room building campus or specific metropolitan area e.g. a city respectively and which may include e.g. WiMAX WiPro HiperMAN High Performance Radio Metropolitan Area Network or IEEE 802.16m Advanced Air Interface.

Cellular Wide Area radio communication technologies may also be considered as Wireless Wide Area Network Wireless WAN radio communication technologies.

The physical layer data transmission technology may also be a physical layer data transmission technology for wireline communication e.g. communication via a fixed line network e.g. according to Ethernet USB Universal Serial Bus Firewire etc.

According to one aspect of this disclosure the data is transferred from the data sharing application of the first device to the data sharing application of the second device by means of the selected physical layer data transmission technology.

According to one aspect of this disclosure the data sharing application includes a middleware component configured to select the physical layer data transmission technology.

The data sharing application may include a data sharing interface for receiving the data from the data sharing application of the operating system of the first device.

According to one aspect of this disclosure the data is written into the data sharing application of the operating system of the first device by a software application running on the first device.

The data is for example written into the data sharing application of the operating system of the first device in response to an operation or instruction by a user of the first device. For example the operation or instruction is a copy or a cut operation or instruction.

According to one aspect of this disclosure the first device and or the second device are mobile communication terminals.

According to one aspect of this disclosure the physical layer data transmission technology is selected from a plurality of physical layer data transmission technologies supported by the first device.

The physical layer data transmission technology may be selected as a physical layer data transmission technologies supported by the second device.

The physical layer data transmission technology may be selected as a physical layer data transmission technology according to which a communication connection between the first device and the second device can be established.

According to one aspect of this disclosure the physical layer data transmission technology is a wireless physical layer data transmission technology.

The physical layer data transmission technology is for example a wireline physical layer data transmission technology.

According to one aspect of this disclosure the data sharing application of the operating system of the second device is connected via a communication connection based on the selected physical layer data transmission technology.

The method may further include detecting whether the signal strength of a signal received from the second device is above a predetermined threshold and performing the connecting and the transferring if it has been detected that the signal strength of above the predetermined threshold.

According to one aspect of this disclosure the method further includes determining the second device from a list of second devices.

The method may include performing the requesting selecting connecting and transferring for each of a plurality of second devices.

The physical layer data transmission technology is for example a Personal Area Network physical layer data transmission technology a Local Area Network physical layer data transmission technology or a Wide Area Network physical layer data transmission technology.

The data sharing application may include a bulletin board shared between the first device and the second device.

The data sharing application is for example implemented in a device architecture layer above the operating system of the first device.

The communication arrangement includes a first computing device and a second computing device . The first computing device and the second computing device may for example be mobile communication terminals. The first computing device and the second computing device may be connected via a communication connection e.g. a wireless communication connection for example in case that the first computing device and the second computing device are mobile communication terminals. Examples for possible components and configurations of the first computing device and the second computing device are given in the following with reference to .

For example the first computing device is a mobile radio communication device configured in accordance with LTE and or other 3GPP mobile radio communication technologies.

In various aspects of the disclosure the communication device may include a processor such as e.g. a microprocessor e.g. a central processing unit CPU or any other type of programmable logic device which may for example act as controller . Furthermore the communication device may include a first memory e.g. a read only memory ROM and or a second memory e.g. a random access memory RAM . Moreover the communication device may include a display such as e.g. a touch sensitive display e.g. a liquid crystal display LCD display or a light emitting diode LED display or an organic light emitting diode OLED display. However any other type of display may be provided as the display . The communication device may in addition include any other suitable output device not shown such as e.g. a loudspeaker or a vibration actuator. The communication device may include one or more input devices such as keypad including a plurality of keys. The communication device may in addition include any other suitable input device not shown such as e.g. a microphone e.g. for speech control of the communication device . In case the display is implemented as a touch sensitive display the keypad may be implemented by the touch sensitive display . Moreover optionally the communication device may include a co processor to take processing load from the processor . Furthermore the communication device may include a first transceiver . The above described components may be coupled with each other via one or more lines e.g. implemented as a bus . The first memory and or the second memory may be a volatile memory for example a DRAM Dynamic Random Access Memory or a non volatile memory for example a PROM Programmable Read Only Memory an EPROM Erasable PROM EEPROM Electrically Erasable PROM or a flash memory e.g. a floating gate memory a charge trapping memory an MRAM Magnetoresistive Random Access Memory or a PCRAM Phase Change Random Access Memory or a CBRAM Conductive Bridging Random Access Memory . The program code used to be executed and thereby to control the processor and optionally the co processor may be stored in the first memory . Data e.g. the messages received or to be transmitted via the first transceiver to be processed by the processor and optionally the co processor may be stored in the second memory . The first transceiver may be configured such that it implements a Uu interface in accordance with LTE. The communication device and the first transceiver may also be configured to provide MIMO radio transmission.

Further the communication device may also include an additional second transceiver for example supporting a different communication technology than the one supported by the first transceiver e.g. a Wireless Local Area Network WLAN technology e.g. a Personal Area Network PAN technology or any other desired wireless communication technology or wireline communication technology. Moreover the communication device may include a still image and or video camera configured to provide a video conference via the communication device .

Furthermore the communication device may include a Subscriber Identity Module SIM e.g. a UMTS Subscriber Identity Module USIM identifying a user and subscriber of the communication device . The processor may include audio processing circuits such as e.g. audio decoding circuit and or audio encoding circuit configured to decode and or encode audio signals in accordance with one or more of the following audio encoding decoding technologies ITU G.711 Adaptive Multi Rate Narrowband AMR NB Adaptive Multi Rate Wideband AMR WB Advanced Multi Band Excitation AMBE etc.

In various aspects of the disclosure the communication device may include a processor such as e.g. a microprocessor e.g. a central processing unit CPU or any other type of programmable logic device which may for example act as controller . Furthermore the communication device may include a first memory e.g. a read only memory ROM and or a second memory e.g. a random access memory RAM . Moreover the communication device may include a display such as e.g. a touch sensitive display e.g. a liquid crystal display LCD display or a light emitting diode LED display or an organic light emitting diode OLED display. However any other type of display may be provided as the display . The communication device may in addition include any other suitable output device not shown such as e.g. a loudspeaker.

The communication device may further include one or more input television TV receiver circuits configured to receive and process TV signals. The one or more TV receiver circuits may include video processing circuits such as e.g. video decoding circuit configured to decode video signals in accordance with one or more of the following video encoding technologies Internation Telecommunication Union ITU H.261 ITU H.263 ITU H.264 Moving Pictures Experts Group MPEG e.g. MPEG 2 MPEG 4 and MPEG 7 etc. Sub Quarter Common Intermediate Format SQCIF Quarter Common Intermediate Format QCIF Common Intermediate Format CIF Video Graphics Array VGA 4 Common Intermediate Format 4CIF etc. The communication device may in addition include any other suitable input device not shown such as e.g. a microphone e.g. for speech control of the communication device . Moreover optionally the communication device may include a co processor to take processing load from the processor .

Furthermore the communication device may include a first transceiver . The above described components may be coupled with each other via one or more lines e.g. implemented as a bus . The first memory and or the second memory may be a volatile memory for example a DRAM Dynamic Random Access Memory or a non volatile memory for example a PROM Programmable Read Only Memory an EPROM Erasable PROM EEPROM Electrically Erasable PROM or a flash memory e.g. a floating gate memory a charge trapping memory an MRAM Magnetoresistive Random Access Memory or a PCRAM Phase Change Random Access Memory or a CBRAM Conductive Bridging Random Access Memory . The program code used to be executed and thereby to control the processor and optionally the co processor may be stored in the first memory . Data e.g. the messages received or to be transmitted via the first transceiver to be processed by the processor and optionally the co processor may be stored in the second memory . The first transceiver may be configured such that it implements a Uu interface in accordance with LTE. The communication device and the first transceiver may also be configured to provide MIMO radio transmission.

Further the communication device may also include an additional second transceiver which may be configured such that it supports a radio communication technology different from the one supported by the first transceiver e.g. a Wireless Local Area Network WLAN technology e.g. a Personal Area Network PAN technology or any other desired wireless communication technology or wireline communication technology. Moreover the communication device may include a still image and or video camera configured to provide a video conference via the second communication device . The one or more cameras may include video processing circuits such as e.g. video encoding circuit configured to encode video signals in accordance with one or more of the following video encoding technologies Internation Telecommunication Union ITU H.261 ITU H.263 ITU H.264 Moving Pictures Experts Group MPEG e.g. MPEG 2 MPEG 4 and MPEG 7 etc. Sub Quarter Common Intermediate Format SQCIF Quarter Common Intermediate Format QCIF Common Intermediate Format CIF Video Graphics Array VGA 4 Common Intermediate Format 4CIF etc. Furthermore the communication device may also include a Subscriber Identity Module SIM e.g. a UMTS Subscriber Identity Module USIM identifying a user and subscriber of the second communication device . The processor may include audio processing circuits such as e.g. audio decoding circuit and or audio encoding circuit configured to decode and or encode audio signals in accordance with one or more of the following audio encoding decoding technologies ITU G.711 Adaptive Multi Rate Narrowband AMR NB Adaptive Multi Rate Wideband AMR WB Advanced Multi Band Excitation AMBE etc.

According to various aspects of this disclosure a data sharing application running on both the source device e.g. the first computing device and the destination device e.g. the second computing device handles the transfer of shared data from the source device to the destination device. The underlying architecture of the source device and the destination device according to one aspect of this disclosure is illustrated in .

The first computing device for example corresponds to the first computing device and the second computing device for example corresponds to the second computing device . The first computing device and the second computing device are coupled via a communication connection for example corresponding to the communication connection .

Applications may run on the first computing device and the second computing device . For example the applications are executed by the CPUs of the first computing device and the second computing device . The applications include both on the first computing device also referred to as source device and the second computing device also referred to as destination device a shared clipboard application . The shared clipboard application includes a user interface an application logic a communication middleware and a clipboard interface . The clipboard interface is an interface between the shared clipboard application and the clipboard of the operating system of the respective computing device . The operating system clipboard of the first computing device may receive data from any application among the applications running on the first computing device and the operating system clipboard of the second computing device may receive data from any application among the applications running on the second computing device e.g. by a copy or cut operation carried out by the user in this application . Vice versa the operating system clipboard of the first computing device may provide data stored in the clipboard to any application among the applications running on the first computing device and the operating system clipboard of the second computing device may provide data stored in the clipboard to any application among the applications running on the first computing device e.g. by a paste operation carried out by the user in this application .

The first computing device and the second computing device further include communication hardware for example corresponding to the transceivers providing radio communication functionality e.g. a communication protocol stack including physical layer data transmission technologies according to various communication standards e.g. 3G LTE WLAN Bluetooth NFC Near Field Communication USB Ethernet etc. The communication hardware for example provides the communication connection .

According to one aspect of this disclosure the shared clipboard application running in both the source device and the destination device extracts the data from the source device operating system clipboard and transfers it to the destination device shared clipboard application which copies the data into the destination device operating system clipboard .

It should be noted that the second computing device may also act as the in this way and that the first computing device may also act as the destination device in this way i.e. the computing device may change their roles in the course of time. Further it should be noted that further computing devices may be present and connected to the first computing device and the second computing device which also include the shared clipboard application architecture as illustrated in and which may also act as source or destination devices.

According to various aspects of this disclosure different modes of operation may be supported by the shared clipboard application 

The shared clipboard application may use different communications mechanisms to transport the data from the source device to the destination device for example 

According to one aspect of this disclosure internally the shared clipboard application on a computing device uses the communication middleware component to abstract the connection details to the shared clipboard application running on another computing device . The middleware component of the first computing device and or of the second computing device may include a contact manager and a channel manager. It should be noted that in the examples described below if only the contact manager or the channel manager is involved the other one may be omitted for better simplicity. However even if one is omitted in the description of an example both the contact manager and the channel manager may be present in both the source device and the destination device such that the configuration is symmetrical.

The middleware component for example supports the above communication technologies as mentioned above e.g. PAN LAN WAN communication . According to one aspect of this disclosure the middleware component is responsible for encrypting and decrypting the data to ensure security and privacy.

The communication middleware component may for example offer one or more of the following functionalities 

A contact manager of the middleware of the destination device may for example verify that it is the right recipient for clipboard content or manage multiple requests for clipboard synchronization.

According to one aspect of this disclosure the middleware component of a computing device maintains a list of known computing devices for a given user and a list of user contacts using the same shared clipboard application.

The list of known computing devices of a user for example includes a plurality of entries specifying computing devices of the same user and also running the shared clipboard application. In other words the list of known computing devices of a user specifies other computing devices of the user to which the user might wish to send the clipboard content of the computing device or whose clipboard content should automatically be synchronized depending on the mode of operation of the shared clipboard application selected by the user .

The list of user contacts using the shared clipboard application for example includes a plurality of entries specifying known computing devices of other users running the shared clipboard application. In other words the list of user contacts using the shared clipboard application specifies computing devices of other users which the user might wish to send the content of his computing device s clipboard.

According to one aspect of this disclosure the middleware is responsible for the login of the user in a computing device and detects the availability and or proximity of computing devices e.g. a known device of other user in one of the contact lists . The user may log in simultaneously in multiple computing devices through the shared clipboard application user interface . The shared clipboard application can be used to exchange data between multiple devices belonging to a single user or between the devices of multiple users.

In an application running on the first computing device writes data into the operating system clipboard of the first computing device .

In the middleware component checks the list of known computing devices of the user and the list of user contacts using the shared clipboard application and detects whether a computing device corresponding to any of the entries of the lists is within communication range of the first computing device .

It is assumed that it is detected that the second communication device is specified on the list of known computing devices of the user and is detected as being in range.

As an example it is assumed that the user chose the automatic mode of operation of the shared clipboard application. Accordingly in the middleware component of the first computing device acting as source device selects a transmission technology to communicate with the second computing device e.g. a physical layer data transmission technology and establishes a communication connection to the second computing device based on the selected transmission technology.

In the second computing device stores the received clipboard contents in the operating system clipboard of the second computing device .

In the user may paste the clipboard contents into any application running on the second computing device .

According to various aspect of this disclosure the middleware can work in two different architectures Peer to Peer and Cloud based.

In the peer to peer architecture the middleware in the shared clipboard application supports the establishment of pairing associations between shared clipboard applications using for example PAN and LAN communication. When data from the shared clipboard application of the source device has to be transferred it is directly sent to the destination device via the PAN or LAN. No server is involved in the communication.

In the cloud architecture the middleware uses LAN or WAN mechanisms to connect to Internet servers. The shared clipboard application for example exchanges the clipboard data through a bulletin board that is hosted in the cloud servers. This architecture allows exchanging of clipboard data between devices without requiring both devices to be switched on at the same time.

In the following aspects of this disclosure according to possible modes of operation of the shared clipboard application are described.

In case of automatic synchronization any clipboard activity on any user device is replicated in other devices where this user is logged in.

A message flow according to an aspect of this disclosure for automatic synchronization is described in the following with reference to and

The message flow takes place between components of a source device for example corresponding to the first computing device and components of a destination device for example corresponding to the second computing device .

The message flow diagram is divided into a first part shown in including the message flow between the components of the source device and a second part shown in including the message flow between the components of the destination device.

In detail the message flow takes place between a source application of the source device e.g. corresponding to the application the operating system clipboard of the source device the shared clipboard application of the source device the middleware of the source device specifically the middleware contact manager and the middleware channel manager the communication hardware of the source device the communication hardware of the destination device the middleware channel manager of the destination device the shared clipboard application of the destination device the operating system clipboard of the destination device and a destination application running on the destination device e.g. corresponding to the application .

In the user issues a copy command to the source application . In the copied data is transferred to the source device clipboard . In the shared clipboard application of the source device is notified about the copying operation. In the shared clipboard application of the source device gets a list of possible destination devices i.e. devices with which the clipboard should be shared from the middleware contact manager which retrieves this information for example from one of the lists . When a device has been determined as destination device the shared clipboard application of the source device requests the establishment of a communication connection to the destination device from the middleware contact manager . The middleware contact manager forwards this request to the middleware channel manager in . In the middleware channel manager triggers the communication hardware to establish a communication connection to the destination device .

In the communication hardware of the source device sends a connection request message to the communication hardware of the destination device . The communication hardware of the destination device forwards the connection request message to the middleware channel manager of the destination device in .

In the middleware channel manager of the destination device sends an application connection request message to the shared clipboard application of the destination device .

A communication connection or communication channel is then established between the source device and the destination device . In the middleware contact manager of the source device sends an identifier of the communication connection or communication channel to the shared clipboard application of the source device .

In the shared clipboard application of the source device supplies the data to be sent to the destination device i.e. the clipboard content to the middleware channel manager together with the identifier of the communication connection. In the middleware channel manager supplies the data to the communication hardware of the source device . The communication hardware sends the data in to the communication hardware of the destination device .

In the communication hardware of the destination device forwards the received data i.e. clipboard content to the middleware channel manager of the destination device which supplies the received data in to the shared clipboard application of the destination device . The shared clipboard application in copies the received data into the operating system clipboard of the destination device. The destination application may upon a paste command by the user in the destination application in request the clipboard contents from the clipboard in . The clipboard contents as received from the source device are then supplied to the destination application in .

In case of semiautomatic synchronization the shared clipboard application of the destination device copies only the data from the last source device where a copy clipboard operation occurred.

A message flow according to an aspect of this disclosure for semiautomatic synchronization is described in the following with reference to .

The flow takes place between components of a source device e.g. corresponding to the first computing device components of a destination device e.g. corresponding to the second computing device and one or more other devices .

In more detail the message flow takes place between a source application on the source device for example corresponding to the application the operating system clipboard of the source device the shared clipboard application of the source device the shared clipboard application of the one or more other devices i.e. the respective shared clipboard application in the case of more than one other devices in the following the flow is described for the case of one other device the flow is extended analogously for more than one other devices the communication middleware of the destination device the shared clipboard application of the destination device the operating system clipboard of the destination device and a destination application on the destination device for example corresponding to the application .

In the user issues a copy command to the source application . In the copied data is transferred to the source device clipboard . In the shared clipboard application of the source device is notified about the copying operation.

In the users selects a Get Data command in the shared clipboard application on the destination device . In the shared clipboard application on the destination device requests the communication middleware to establish communication connections to all devices which are candidates for supplying clipboard data e.g. all known devices of the user as included in the list that are switched on into which the user is log in and which are within reception range of the destination device . In the shared clipboard application on the destination device requests a clipboard timestamp i.e. an indication of the last change of the operating system clipboard from the shared clipboard application of one of the one or more other devices and receives in a first clipboard timestamp in response.

Similarly in the shared clipboard application on the destination device requests a clipboard timestamp from the shared clipboard application of the source device and receives in a second clipboard timestamp in response.

It is assumed that the second timestamp is newer than the first timestamp i.e. that the source device is the device with the most recent clipboard change.

Accordingly in the shared clipboard application on the destination device requests the clipboard content of the source device from the shared clipboard application of the source device . In the shared clipboard application of the source device transmits its operating clipboard content to the shared clipboard application of the destination device .

The shared clipboard application in copies the received data into the operation system clipboard of the destination device . The destination application may upon a paste command by the user in the destination application in request the clipboard contents from the clipboard in . The clipboard contents as received from the source device are then supplied to the destination application in .

It should be noted that in the various communications the communication middleware of the source device and of the one or more other devices as well as the communication hardware are involved where applicable as described above . These are omitted for clarity.

According to one to multiple clipboard synchronization the user proactively identifies the users devices to which the data will be sent.

According to one aspect of this disclosure the user performs the following steps in one to multiple clipboard synchronization 

According to Bluetooth and or WLAN proximity triggered synchronization Bluetooth or WLAN signal levels are used by the destination device to detect the source device from which to copy the data from.

According to one aspect of this disclosure the user performs the following for Bluetooth WLAN proximity triggered synchronization 

A message flow according to an aspect of this disclosure for WLAN proximity triggered synchronization is described in the following with reference to .

The flow takes place between components of a source device e.g. corresponding to the first computing device and components of a destination device e.g. corresponding to the second computing device .

In more detail the message flow takes place between a source application on the source device for example corresponding to the application the operating system clipboard of the source device the shared clipboard application of the source device the communication middleware of the source device a WLAN communication hardware e.g. a WLAN transceiver of the source device a WLAN communication hardware e.g. a WLAN transceiver of the destination device the communication middleware of the destination device the shared clipboard application of the destination device the operating system clipboard of the destination device and a destination application on the destination device for example corresponding to the application .

In the user issues a copy command to the source application . In the copied data is transferred to the source device clipboard . In the shared clipboard application of the source device is notified about the copying operation.

In the shared clipboard application on the source device notifies the shared clipboard application on the destination device about the copying operation via the communication middleware and the WLAN communication hardware of the source device and the WLAN communication hardware and the communication middleware of the destination device .

In the shared clipboard application of the destination device requests the communication middleware of the destination device to be alerted when the reception strength of WLAN signals of the source device exceeds a threshold. The threshold and an identification of the source device are included in the request.

It is assumed that in the user brings the source device and the destination device closer together such that the reception strength of WLAN signals of the source device at the destination device exceeds the threshold.

In the communication middleware of the destination device requests the WLAN communication hardware of the destination device to provide information about the reception strength of WLAN signals from the source device . This is for example done periodically in accordance with the request by the shared clipboard application in . In the WLAN communication hardware of the destination device returns an indication of the reception strength in response. Since it exceeds the threshold the communication middleware alerts the shared clipboard application .

In the shared clipboard application on the destination device requests a clipboard timestamp from the shared clipboard application of the source device and receives in a clipboard timestamp in response.

It is assumed that in it is decided e.g. by the shared clipboard application of the destination device that the timestamp indicates that the clipboard change is recent enough to justify a copy of the clipboard content from the source device to the destination device . Accordingly in the shared clipboard application on the destination device requests the clipboard content of the source device from the shared clipboard application of the source device . In the shared clipboard application of the source device transmits its operating clipboard content to the shared clipboard application of the destination device .

The shared clipboard application in copies the received data into the operation system clipboard of the destination device . The destination application may upon a paste command by the user in the destination application in request the clipboard contents from the clipboard in . The clipboard contents as received from the source device are then supplied to the destination application in .

According to NFC connection detection clipboard synchronization a NFC connection operation to detect the source device from which to copy the data from. NFC devices can be working either in NFC read write mode or in NFC peer to peer modes.

According to one aspect of this disclosure the user performs the following in NFC connection detection clipboard synchronization 

A message flow according to an aspect of this disclosure for NFC connection detection clipboard synchronization is described in the following with reference to .

The flow takes place between components of a source device e.g. corresponding to the first computing device and components of a destination device e.g. corresponding to the second computing device .

In more detail the message flow takes place between a source application on the source device for example corresponding to the application the operating system clipboard of the source device the shared clipboard application of the source device the communication middleware of the source device NFC communication hardware e.g. a NFC transceiver of the source device NFC communication hardware e.g. a NFC transceiver of the destination device the communication middleware of the destination device the shared clipboard application of the destination device the operating system clipboard of the destination device and a destination application on the destination device for example corresponding to the application .

In the user issues a copy command to the source application . In the copied data is transferred to the source device clipboard . In the shared clipboard application of the source device is notified about the copying operation.

It is assumed that in the user brings the source device in NFC reception range of the destination device . In the NFC hardware of the source device initiates an NFC connection to the NFC hardware of the destination device which is established in e.g. by a corresponding response from the NFC hardware of the destination device .

In the NFC hardware of the source device informs the shared clipboard application of the source device about the connection establishment by means of the communication middleware of the source device . In the NFC hardware of the destination device informs the shared clipboard application of the destination device about the connection establishment by means of the communication middleware of the destination device .

In the shared clipboard application on the source device requests a clipboard timestamp i.e. an indication of the last change of the operating system clipboard from the shared clipboard application of the destination device and receives in a first clipboard timestamp in response.

It is assumed that in it is detected by the shared clipboard application on the source device based on the first timestamp that the last clipboard change by the destination device is not sufficiently recent to justify a transfer of the clipboard content from the destination device.

In the shared clipboard application on the destination device requests a clipboard timestamp from the shared clipboard application of the source device and receives in a second clipboard timestamp in response.

It is assumed that in it is detected by the shared clipboard application on the destination device based on the second timestamp that the last clipboard change by the destination device is sufficiently recent to justify a transfer of the clipboard content from the source device .

Accordingly in the shared clipboard application on the destination device requests the clipboard content of the source device from the shared clipboard application of the source device . In the shared clipboard application of the source device transmits its operating clipboard content to the shared clipboard application of the destination device .

The shared clipboard application in copies the received data into the operation system clipboard of the destination device . The destination application may upon a paste command by the user in the destination application in request the clipboard contents from the clipboard in . The clipboard contents as received from the source device are then supplied to the destination application in .

According to one aspect of this disclosure a shared bulletin board is used as a user interface belonging to the shared clipboard application. It enables two or more computing devices to cut and paste text and images into a virtual bulletin board such that the board contents are identical as viewed on multiple devices. The user can move URLs phone numbers email addresses text or pictures or any digital data among between their different devices. The shared bulletin board user interface is content aware and can locate actionable strings therein e.g. phone numbers URLs addresses GPS locations and link these items to appropriate applications e.g. opens Skype to handle a phone number . The user can set up multiple shared bulletin boards which are independent and only visible to certain devices or contacts. The bulletin board maintains a history of the last copied contents clips .

According to one aspect of this disclosure the user performs the following steps to setup a shared bulletin board 

According to one aspect of this disclosure the user performs the following to transfer data with the shared bulletin board user interface 

The user interfaces show a plurality of content items . The user interface as used for a mobile device in this example shows a pop up menu for actions based on metadata of a content item which may be selected for the content item google maps link in this example .

The same bulletin board application as described in the peer to peer shared bulletin board above can use a cloud architecture to transport the data and store the data for some period of time. The usage of a cloud allows that the devices using the bulletin board do not need to be switched on at the same time. It is possible to copy data from one device to the cloud then switch off the source device and several hours later on another device retrieve the data from the cloud.

An architecture for a cloud shared bulletin board may be as described with reference to wherein instead of the communication connection between the two computing devices the two computing device are each coupled by means of a communication connection to a computing cloud e.g. to one or more server computers also referred to as cloud servers e.g. in the Internet wherein the two computing devices do not need to be coupled to the computing cloud at the same time.

According to one aspect of this disclosure the user performs the following to transfer data using the cloud shared bulletin board 

Various aspects of this disclosure for exchanging clipboard data between two devices as for example described above may have the following features 

A mechanism for clipboard content transfer e.g. for clipboard synchronization is provided which is integrated with the operating system clipboard. The number of steps the user has to take to get the data from an application in the source device to the application in the destination device is reduced. Where automatic clipboard synchronization is used the mechanism only requires to copy the data into the operating system clipboard in the source device and paste it in the destination device application. The mechanism can work in a peer to peer setup without a need of a central server and ensure security and privacy encrypting the data. Further according to one aspect of this disclosure no temporary files or messages are created so the user does not need to delete them.

While the invention has been particularly shown and described with reference to specific aspects of this disclosure it should be understood by those skilled in the art that various changes in form and detail may be made therein without departing from the spirit and scope of the invention as defined by the appended claims. The scope of the invention is thus indicated by the appended claims and all changes which come within the meaning and range of equivalency of the claims are therefore intended to be embraced.

