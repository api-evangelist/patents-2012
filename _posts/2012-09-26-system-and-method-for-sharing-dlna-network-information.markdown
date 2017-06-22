---

title: System and method for sharing DLNA network information
abstract: A system and method for sharing Digital Living Network Alliance (DLNA) network information is provided. The system includes a first mobile terminal that collects information about a DLNA network having a radio radius in which the first mobile terminal is located, and transmits the information about the DLNA network to a web server. The web server manages the information about the DLNA network received from the first mobile terminal, and shares the information about the DLNA network with a second mobile terminal, which is located outside of the radio radius of the DLNA network, via an Internet connection.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09112904&OS=09112904&RS=09112904
owner: Samsung Electronics Co., Ltd
number: 09112904
owner_city: 
owner_country: KR
publication_date: 20120926
---
This application claims priority under 35 U.S.C. 119 a to Korean Patent Application Serial No. 10 2011 0099822 which was filed in the Korean Intellectual Property Office on Sep. 30 2011 the entire content of which is incorporated herein by reference.

The present invention relates to a system and method for sharing information about a Digital Living Network Alliance DLNA network.

The DLNA is a non profit collaborative trade organization which is responsible for defining interoperability guidelines to enable sharing of digital media between consumer appliances such as Personal Computers PCs printers cameras cell phones Set Top Boxes STBs TeleVisions TVs and other multimedia devices. Basically the DLNA guidelines are used in order to achieve interoperability between appliances in a home network.

Generally DLNA network appliances share content via a Wireless Fidelity WiFi Access Point AP . The DLNA network appliances indicate appliances mounting DLNA middleware. The WiFi AP assigns an Internet Protocol IP address for each appliance based on Dynamic Host Configuration Protocol DHCP . The DLNA network appliances can communicate with one another through Universal Plug and Play UPnP protocol and can share content with other appliances over the Internet.

Generally after a terminal user searches an accessible WiFi AP the terminal user can access a Digital Media Server DMS of a corresponding DLNA network via the searched WiFi AP. The DMS stores and provides content.

However in a conventional system the terminal user must be positioned within a radio radius of the WiFi AP in order to identify and access the DMS of the DLNA network. As a result if the terminal user is positioned out of the radio radius of the WiFi AP the terminal user cannot identify the WiFi AP making it difficult to gain access to the DMS of the DLNA network.

The present invention is designed to addresses at least the above described problems and or disadvantages occurring in the prior art and to provide at least the advantages below.

Accordingly an aspect of the present invention is to provide a system and method that enable terminal users to share information about a corresponding DLNA network without geographical limits.

Another aspect of the present invention is to provide a system and method in which a terminal user who is positioned in an area where a DMS of a corresponding DLNA network cannot be directly identified receives information about the DMS of the DLNA network through the Internet.

Another aspect of the present invention is to provide a system and method for posting a DMS address of a DLNA network on the web thereby allowing other terminal users to access the DMS address.

Another aspect of the present invention is to provide a system and method for linking information of a corresponding DLNA network e.g. location information DMS information and content information and user opinions hereinafter social information about the DLNA network.

In accordance with an aspect of the present invention a system for sharing DLNA network information is provided. The system includes a first mobile terminal that collects information about a DLNA network having a radio radius in which the first mobile terminal is located and transmits the information about the DLNA network to a web server and the web server that manages the information about the DLNA network received from the first mobile terminal and shares the information about the DLNA network with a second mobile terminal which is located outside of the radio radius of the DLNA network via an Internet connection.

In accordance with another aspect of the present invention a system for sharing DLNA network information is provided. The system includes a first mobile terminal that uploads a post including information about a DLNA network having a radio radius in which the first mobile terminal is located to a web server and the web server that collects social information about the post received from the first mobile terminal and manages the post and the social information.

In accordance with another aspect of the present invention a method for sharing DLNA network information is provided. The method includes collecting by a first mobile terminal information about a DLNA network having a radio radius in which the first mobile terminal is located transmitting the information about the DLNA network to a web server and sharing by the web server the information about the DLNA network with a second mobile terminal which is located outside of the radio radius of the DLNA network via an Internet connection.

Various embodiments of the present invention will now be described in detail with reference to the accompanying drawings. In the following description specific details such as detailed configuration and components are merely provided to assist the overall understanding of these embodiments of the present invention. Therefore it should be apparent to those skilled in the art that various changes and modifications of the embodiments described herein can be made without departing from the scope and spirit of the present invention. In addition descriptions of well known functions and constructions are omitted for clarity and conciseness.

In accordance with an embodiment of the present invention a system is provided that enables terminal users to share information about a corresponding DLNA network over the Internet without geographical limits. Specifically the existence of a DMS of a DLNA network is shared over the Internet. For example if a DMS address of the DLNA network is posted on the web terminal users with Internet capabilities can access the posted DMS address.

Referring to the content sharing system includes a mobile terminal and a web server which wirelessly communicate with each other. Specifically the mobile terminal identifies an accessible WiFi AP of a DLNA network at a current location. The identified WiFi AP indicates that the mobile terminal is located within the radio radius of the WiFi AP. The mobile terminal participates in the DLNA network via the WiFi AP access.

The mobile terminal and appliances of the DLNA network are an IP addresses based on DHCP and communicate through UPnP protocol.

The DLNA network includes a DMS a Digital Media Player DMP a Digital Media Renderer DMR and a Digital Media Control DMC . The DMS stores and manages content and provides the content to connected terminals. The DMP receives content from the DMS or a DMS mount terminal and reproduces the content. The DMC uploads or downloads content to or from the DMS mount terminal. The DMR controls the DMC to receive content from the DMS and reproduce the content. The DMP may include the DMR and the DMC.

Each DLNA network can construct a plurality of DMSs and the mobile terminal can communicate with an opened i.e. access granted DMS. In DMS A DMS B DMS C and DMS D are opened DMSs granting access.

The mobile terminal is located within a radio radius of a DLNA B network such that the mobile terminal can identify the DMS B of the DLNA B network. The mobile terminal is also located within the radio radius of a DLNA C network such that the mobile terminal can also identify the DMS C of the DLNA C network. Basically the mobile terminal identifies DMS B and DMS C as access objects and may access both the DMS B and DMS C .

However when the mobile terminal is not located in the radio radius of a DLNA network i.e. DLNA A and DLNA D the mobile terminal cannot identify either of DMS A or DMS D and therefore cannot identify these DMSs as potential access objects.

The mobile terminal collects and stores information about a DLNA network in which the mobile terminal is participating in a current location and transmits this information to the web server . The information about the DLNA networks includes location information DMS information content information etc.

Referring to the mobile terminal or web server links location information of a DLNA network DMS information and content information and stores the linked information. Additionally the web server maps opinions hereinafter social information of terminal users about a DMS and content e.g. an online comment a grade to the DLNA network information and stores the mapping result.

The location information includes a street name cell IDentifier ID GPS information and the like. The DMS information links with the location information and includes an IP address an AP address and the like. Further the content information links with the DMS information and includes a content list not shown content names a detailed description of the content and the like. Furthermore the social information links with the DMS information or the content information and includes a social site type an online comment a grade etc. Additionally the location information the DMS information the content information and the social information are granted inherent IDs managed and linked with each other. Accordingly users of terminals can search the stored DLNA network information via the Internet.

For example the web server presents a DMS which is located in a corresponding area on a map with reference to the corresponding location information DMS information content information and social information. If different information about a corresponding DLNA network is uploaded the web server updates the stored information using the uploaded information.

As illustrated in in the DLNA network information sharing system a user of the mobile terminal may post information about the DLNA network to the web server . For example the web server sets up a web site capable of registering this posting. More specifically the web server receives a post after receiving a request for posting registration from the mobile terminal and then grants an identification number for the post creates an address for the post and registers the post to a posting board.

For example the post may be the introduction of a content of notifying a HyperText Transfer Protocol HTTP based Uniform Resource Locator URL address for the DMS or content.

The mobile terminal can acquire the URL address for the DMS by transmitting a physical address of the DMS to the web server . The web server assigns a URL address or an IP address mapped to the physical address and transmits the URL address to the mobile terminal .

The web server connects and manages the post and the corresponding DLNA network information and social information. The web server permits the users of the terminals to input the social information such as an online comment a grade etc. to the post. For example the social information may be an index showing a user s preference or satisfaction for the post or an index showing a preference or satisfaction for a corresponding DLNA network.

As described above the web server may set up one or more web sites e.g. Social Network Services SNSs that share the DLNA network information. Accordingly the DLNA network information sharing system supports communication between the mobile terminal and the web server through an access service such as a HyperText Markup Language HTML page an open Application Programming Interface API etc.

Referring to the mobile terminal includes an input unit for user input a display unit for outputting display data a storage unit for storing data a location information receiver for receiving location information a communication unit for exchanging wireless signals and a controller for controlling operation of the mobile terminal . The input unit includes hardware or software buttons and outputs an input signal received through these buttons to the controller . The display unit e.g. a Liquid Crystal Display LCD displays display data corresponding to an input signal according to the control of the controller . The storage unit i.e. a memory stores control programming and data input output when the mobile terminal is operated. The location information receiver receives GPS information and cell ID information and outputs the information to the controller . The controller identifies a position of the mobile terminal from the information. The controller provides information of a DLNA network accessible at a current location to a web server .

The web server includes a storage unit for data a communication unit for exchanging wireless signals and a controller for controlling the operation of the web server . The controller communicates with the mobile terminal through the communication unit and acquires and manages information about a corresponding DLNA network.

Referring to in step the mobile terminal searches for an accessible AP of a DLNA network. If an accessible AP is located the mobile terminal is assigned an IP address to participate in the DLNA network from the AP in step .

In step the mobile terminal searches for an accessible DMS in the DLNA network. If the accessible DMS granting is identified the mobile terminal collects information about the DLNA network in step . For example the information of the DLNA network includes location information DMS information content information etc. The mobile terminal can acquire the location information directly or acquire the location information from the DLNA network. If no accessible DMS is identified the mobile terminal performs step and its subsequent steps and attempts to participate in another DLNA network.

As described above while participating in the DLNA network the mobile terminal collects the DLNA network information and provides the collected DLNA network information to the web server . If the DLNA network information changes the mobile terminal transmits the changed DLNA network information to the web server and the web server updates the stored the DLNA network information.

Referring to in step the web server checks if received DLNA network information already exists in a st web site. When the received DLNA network information already exists in the st web site the web server registers the received DLNA network information to a nd web site in step . However when the received DLNA network information does not exist in the st web site the web server registers the received DLNA network information to the st web site in step .

Referring to one of the terminals which are not located in a radio radius of a DLNA network accesses a web site and requests to search for a DMS located in a corresponding area. With reference to DLNA network information stored in the web server the web site shows a search area with a map indicating DMS positions located on the map. The web site provides information of an address for each DMS content etc.

Further with reference to social information linked to the DLNA network information stored in the web server the web site provides social information e.g. an evaluation grade about the searched DMS.

Referring to in step the mobile terminal uploads a post including a URL address linking a corresponding DMS or content to the web server .

In step the web server connects the uploaded post and pre stored DLNA network information relating with the uploaded posting.

If social information about the posting is generated in step the web server links the social information and the connected DLNA network information and post and stores the linked information in step .

Using the social information the web server can provide an index of user satisfaction reliability and the like for a corresponding DLNA network and a post. For example if an average of evaluation grades put by users on a post is equal to or greater than a threshold value a web site adds a grade of a satisfaction or reliability for the post and a DLNA network connecting with the post. The grade of the satisfaction or reliability for the DLNA network is in line with a grade of a satisfaction or reliability for a corresponding DMS or content.

Further if a new post is registered the web server searches for a similar post to the new post. Because the new post contains information about a corresponding DLNA network the web server can search for a post containing similar content to the new posting. If a similar post exists the web server increases a grade of a satisfaction or reliability for a corresponding DLNA network.

As described above a DLNA network information sharing system according to an embodiment of the present invention can share information of a corresponding DLNA network on the web.

While the present invention has been shown and described with reference to certain embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present invention as defined by the appended claims and their equivalents.

