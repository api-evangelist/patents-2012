---

title: Method and system for personalized venue marketing
abstract: A method and system for personalized venue marketing is disclosed herein. An application that is resident on a mobile communication device of a patron sends personally identifiable information and the identifying device address to a server when the patron enters a venue. The server associates the identifying device address of the mobile device with the patron in a CRM database for the venue. The identifying device address allows for tracking of the patron by WiFi sensors positioned throughout the venue.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08433342&OS=08433342&RS=08433342
owner: Joingo, LLC
number: 08433342
owner_city: San Jose
owner_country: US
publication_date: 20121107
---
The present invention generally relates to personalized marketing to mobile communication devices. More specifically the present invention relates to a method and system for identifying a patron at a venue and transmitting personalized marketing to the patron s mobile communication device.

Venues such as casinos would like to know when a patron is onsite. One method is the use of player cards. However the patron usually needs to be playing a game for the card to be active. 

Code Division Multiple Access CDMA is a spread spectrum communication system used in second generation and third generation cellular networks and is described in U.S. Pat. No. 4 901 307.

Interactive voice response IVR is a telephone technology in which a user uses a phone to interact with a database to acquire information.

Short Message Service SMS is text messaging communication using a mobile phone or other device to send messages up to 160 characters in length.

Multimedia messaging service MMS communication is a communication transmitted to and from a mobile phone that includes a multimedia content such as a digital photograph JPEG videos and the like.

A SMS Gateway is used to send text messages with or without a mobile phone and is used by aggregators to forward text messages to mobile phones.

BLUETOOTH technology is a standard short range radio link that operates in the unlicensed 2.4 gigaHertz band.

MAC address is a media access control address which is a unique identifier on a network interface card and stored in the memory of a device such as a mobile phone.

Public Switch Telephone Network PSTN is a telecommunication system in which networks are inter connected to allow telephones to communicate with each other throughout the world.

Telephone Consumer Protection Act TCPA of 1991 restricts the use of SMS text messages received by mobile phones and SMS messages sent without a consumer s consent can violate the TCPA.

Hypertext Transfer Protocol HTTP is a set of conventions for controlling the transfer of information via the Internet from a web server computer to a client computer and also from a client computer to a web server.

Internet is the worldwide decentralized totality of server computers and data transmission paths which can supply information to a connected and browser equipped client computer and can receive and forward information entered from the client computer.

FTP or File Transfer Protocol is a protocol for moving files over the Internet from one computer to another.

Short message peer to peer SMPP is a telecommunications protocol for exchanging SMS messages between SMS peer entities.

A SMS aggregator is an entity that provides connectivity with a mobile phone carrier by offering a SMS gateway to send and receive messages and other digital content.

Application Programming Interface API is a collection of computer software code usually a set of class definitions that can perform a set of related complex tasks but has a limited set of controls that may be manipulated by other software code entities. The set of controls is deliberately limited for the sake of clarity and ease of use so that programmers do not have to work with the detail contained within the given API itself.

Direct Inward Dialing DID involves a carrier providing one or more trunk lines to a customer for connection to the customer s private branch exchange PBX and a range of telephone lines are allocated to this line.

Voice over Internet Protocol VoIP relates to voice communications e.g. telephone calls transmitted over the Internet such as SKYPE call.

User Interface or UI is the junction between a user and a computer program. An interface is a set of commands or menus through which a user communicates with a program. A command driven interface is one in which the user enter commands. A menu driven interface is one in which the user selects command choices from various menus displayed on the screen.

Web Browser is a complex software program resident in a client computer that is capable of loading and displaying text and images and exhibiting behaviors as encoded in HTML HyperText Markup Language from the Internet and also from the client computer s memory. Major browsers include MICROSOFT INTERNET EXPLORER NETSCAPE APPLE SAFARI MOZILLA FIREFOX and OPERA.

Web Server is a computer able to simultaneously manage many Internet information exchange processes at the same time. Normally server computers are more powerful than client computers and are administratively and or geographically centralized. An interactive form information collection process generally is controlled from a server computer to which the sponsor of the process has access.

CRM Customer Relationship Management is a widely implemented strategy for managing a company s interactions with customers clients and sales prospects. CRM involves using technology to organize automate and synchronize business processes and the like principally sales activities but also business processes and the like for marketing customer service and technical support.

Wireless Application Protocol WAP is an open global specification that empowers users with mobile wireless communication devices such as mobile phones to easily access data and to interact with Websites over the Internet through such mobile wireless communication device. WAP works with most wireless communication networks such as CDPD CDMA GSM PDC PHS TDMA FLEX reflex iDEN TETRA DECT DataTAC Mobitex and GRPS. WAP can be built on most operating systems including PalmOS WINDOWS CE FLEXOS OS 9 JavaOS and others.

WAP Push is defined as an encoded WAP content message delivered pushed to a mobile communication device which includes a link to a WAP address.

Wireless Access Point WAP is a device that allows wireless devices to connect to a wired network using WiFi Bluetooth or related standards.

The prior art has failed to provide an easy means for determining when a patron is onsite and for tracking the patron onsite.

The present invention is provides a solution to the problem. The present invention provides for detection of a patron at a venue and for tracking of the patron at the venue.

One aspect of the present invention is a method for personalized venue marketing. The method includes downloading a mobile application to a mobile device of an end user. The method also includes collecting personally identifiable information on the end user. The method also includes sending the personally identifiable information to a server. The server configured to extract the IP address from the message which was originated by the mobile device and map the IP address into its corresponding identifying device address and where the personally identifiable information is used to find the CRM entry for the user and associate the identifying device address with that user of the mobile device with the end user. The method also includes receiving a wireless communications protocol request from the mobile device at a wireless sensor within a venue the wireless communications protocol request comprising the identifying device address for the mobile device. The method also includes triggering a message comprising the identifying device address from the wireless sensor to the server which triggers a plurality of marketing activities to transmit to the end user.

Another aspect of the present invention is a method for personalized venue marketing. The method includes downloading a mobile application to a mobile device of an end user. The method also includes constructing an indentifying application address at the mobile application on the mobile device. The method also includes sending the indentifying application address to a server. The server is configured to extract the IP address from the message which was originated by the mobile device and map the IP address into its corresponding identifying device address and where the personally identifiable information is used to find the CRM entry for the user and associate the identifying device address with that end user of the mobile device with the end user. The method also includes receiving a wireless communications protocol request from the mobile device at a wireless sensor within a venue the wireless communications protocol request comprising the identifying device address for the mobile device. The method also includes triggering a message comprising the identifying device address from the wireless sensor to the server which triggers a plurality of marketing activities to transmit to the end user.

Yet another aspect of the present invention is a system configured to present personalized marketing to patrons as they enter and move around a venue. The system is comprised of a mobile device supporting wireless communication an access point designed to sense the presence and signature of the mobile device and report this information a service configured to request patron input to associate the signature of the device with the identify of the patron a service configured to translate the signature into a patron identity and a content server designed to deliver personalized content to the mobile device based upon the end user identity.

The venue marketing system can include the whole venue or a defined area in a large venue such as club pool or other areas. In venue sensors are utilized preferably WIFI POPs Point Of Presence . The accuracy is measured in tens of feet but it depends upon many parameters such as echos or dynamic parameters such as crowds or carts. The association between the mobile device and patron is what is desired by the venue tracking. A MAC Address PatronID. is triggered upon entrance to the venue. A WIFI OTA protocol senses the MAC address and forwards to the trigger message to a remote server.

Another aspect of the invention is marketing to a visitor in the venue. This aspect of the invention turns WIFI login pages into specials and offers from the venue. The can be offers within a native application on the mobile device. Personalized Offers to the patron are based upon MAC tracking and visit history if the end user of the mobile device is anonymous not known by the venue and the mobile device does not have a native application for the venue. The personalized marketing is alternatively based upon on a PlayerID loyalty account number if a MACPlayerID association has been made by the venue. Visit tracking reports on how many visits are made to the venue and who is in venue. The time is also recorded in each area of the venue.

For an unknown guest that enters the venue a MAC trigger will be received if a WIFI of the mobile device is on. For this situation specials are presented in the WIFI Login Page if auto connected or if a data fetch is made by the mobile device.

When a known guest enters the venue but the mobile device of the guest does not have a downloaded venue application a MAC Trigger will be received if WIFI of the mobile device is on. For this situation personalized offers are presented in the WIFI Login Page if auto connected or data fetch is made. Also SMS push registered SMS subscriber offers are made.

When a known guest enters the venue and the mobile device of the guest does have a downloaded venue application a MAC Trigger will be received if WIFI of the mobile device is on. Personalized offers are presented in the WIFI Login Page if auto connected or a data fetch is made. Push messaging is also sent to the patron through the application.

The remote server is preferably configured to perform the following receive a MAC SSID IP in header sent by a client add MAC address to a mobile device record add table MAC IP PID to a patron server listen for WIFI registrations at a patron server push WIFI Regs into JSB by a patron server return WIFI login marketing from the patron server translate WIFI Reg into a Push message.

Having briefly described the present invention the above and further objects features and advantages thereof will be recognized by those skilled in the pertinent art from the following detailed description of the invention when taken in conjunction with the accompanying drawings.

A preferred embodiment of a system for personalized venue marketing is shown in . As shown in a mobile communication device is capable of connecting to a local area network LAN through a wireless access point WAP or of a facility through an Ethernet of the facility and through a firewall of the facility. The facility has a server that connects to the Internet . An authentication service is configured to request patron input to associate the signature of the device with the identity of the patron and a marketing content service is configured to translate the signature into a patron identity PID . A third party server is accessible over the Internet . The mobile communication device has a resident mobile application for accessing the third party server . A content server is also shown.

As shown in a patron moves through the areas of a resort WAPs are able to track the mobile communication device of the patron allowing the facility to track his movements and monitor his time gambling or his time at a poolside bar.

The mobile communication devices utilized with the present invention preferably include mobile phones smartphones tablet computers PDAs and the like. Examples of smartphones include the IPHONE smartphone from Apple Inc. BLACKBERRY smartphones from Research In Motion the DROID smartphone from Motorola Mobility Inc. and many more. Examples of tablet computing devices include the IPAD tablet from Apple Inc. and the XOOM tablet from Motorola Mobility Inc.

Most of the interface descriptions preferably discloses use of at least one communication protocol to establish handshaking or bi directional communications. These protocols preferably include but are not limited to XML HTTP TCP IP Serial UDP FTP Web Services WAP SMTP SMPP DTS Stored Procedures Import Export Global Positioning Triangulation IM SMS MMS GPRS and Flash. The databases used with the system preferably include but are not limited to MSSQL Access MySQL Progress Oracle DB2 Open Source DBs and others. Operating system used with the system preferably include Microsoft 2010 XP Vista 200o Server 2003 Server 2008 Server Windows Mobile Linux Android Unix I series AS 400 and Apple OS.

The underlying protocol at a server is preferably Internet Protocol Suite Transfer Control Protocol Internet Protocol TCP IP and the transmission protocol to receive a file is preferably a file transfer protocol FTP Hypertext Transfer Protocol HTTP or other similar protocols. The transmission protocol ranges from SIP to MGCP to FTP and beyond. The protocol at the server is preferably HTTP.

A mobile communication service provider aka phone carrier of the customer such as VERIZON AT T SPRINT T MOBILE and the like mobile communication service providers provide the communication network for communication to the mobile communication device of the end user.

A typical mobile communication device includes an accelerometer a head phone a microphone a speaker a GPS chipset a Bluetooth component a WiFi component a 3G 4G component a BaseBand Processor for radio control an applications processor a JTAG debugger a SDRAM memory a Flash memory SIM card LCD display a camera a power management circuit and a battery or power source.

A system for personalized venue marketing is shown in . A mobile communication device is monitored by POPs point of presence . The POPs are on the LAN . A patron server and a patron database DB are also on the LAN . A WiFi server of a WiFi system is also on the LAN . The LAN is in communication with a WAN through a firewall . A remote server and a remote DB are in communication with the LAN through the WAN . In a preferred embodiment the WAN is the Internet.

The patron DB resolves the MAC address to the device to determine if the Guest is known or unknown. If an Unknown Guest enters the venue and the WiFi of the device is on specials will be presented to the guest in a WiFi Login Page if the device auto connects or there is a data fetch. If a Known Guest enters the venue but does not have the application installed on their device and the WiFi of the device is on there will be an SMS push through the cellular WAN for personalized offers presented to the guest in a WiFi Login Page if the device auto connects or there is a data fetch. If a Known Guest enters the venue with the application installed on their device and the WiFi of the device is on there will be a an application push for personalized offers presented to the guest in a WiFi Login Page if the device auto connects or there is a data fetch. In each case there will be a MAC Trigger if the device has the WiFi on.

From the foregoing it is believed that those skilled in the pertinent art will recognize the meritorious advancement of this invention and will readily understand that while the present invention has been described in association with a preferred embodiment thereof and other embodiments illustrated in the accompanying drawings numerous changes modification and substitutions of equivalents may be made therein without departing from the spirit and scope of this invention which is intended to be unlimited by the foregoing except as may appear in the following appended claim. Therefore the embodiments of the invention in which an exclusive property or privilege is claimed are defined in the following appended claims.

