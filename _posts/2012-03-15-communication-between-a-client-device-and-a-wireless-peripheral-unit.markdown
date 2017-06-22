---

title: Communication between a client device and a wireless peripheral unit
abstract: A communication between a client device () and a peripheral unit () uses tunneling over another communication mode. The other communication mode is implemented between the client device and a host device (), in addition to a communication mode implemented between the host device and the peripheral unit. The host device and the client device are each provided with additional communication modules (-), at application level and transport level. Security issues against intrusions into the communication may be implemented by the modules added to the host or client unit.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09426835&OS=09426835&RS=09426835
owner: KONINKLIJKE PHILIPS N.V.
number: 09426835
owner_city: Eindhoven
owner_country: NL
publication_date: 20120315
---
The present invention relates to communication between a client device and a wireless peripheral unit. This invention is for example relevant for Bluetooth communication with the peripheral unit.

The Bluetooth standard specifies a protocol for wireless short range communication between devices which is well known. It is typically used for connecting wireless peripheral units such as a keyboard a mouse a headset a printer etc. . . . to one or several devices thereby forming a set of peripheral units in a local area network which is called piconet in the Bluetooth standard.

But one device which is Bluetooth connected to a peripheral unit may also pertain to another network so that it may be useful to have the peripheral unit controlled not only by the Bluetooth connected device but also with an extra device of the another network. Put another way it may be useful to share the Bluetooth peripheral unit between the Bluetooth connected device and the extra device although the extra device does not pertain to the Bluetooth piconet of the peripheral unit. In the description below the Bluetooth connected device and the extra device are called respectively host device and client device.

There already exist handover mechanisms for extending the Bluetooth connection to the client device so that an operation of the peripheral unit can be controlled from the client device. But when the Bluetooth piconet contains several peripheral units pairings of the client device respectively with the peripheral units are required so that the sharing of the peripheral units is not easy to accomplish. In addition each time a new Bluetooth peripheral unit is added into the piconet an additional pairing of this new peripheral unit with the client device is required. Therefore the sharing process is complex and security matters arise with respect to uncontrolled access to the Bluetooth connected hardware and the Bluetooth transmitted data.

An object of the present invention is to provide simple access to peripheral units for a client device which is not connected with these peripheral units.

An additional object of the invention is to provide such access so that it is secure with respect to intrusive attempts directed to the set of peripheral units.

To this purpose the present invention proposes using a tunneling process for handing over the already connected peripheral units to the client device through the host device. Then it is sufficient that the host device is paired with several peripheral units for the client device to appear automatically paired with each one of these peripheral units. Such pairing translation from the host device to the client device is achieved without user intervention in a single step for all the initially connected peripheral units so that it is simple.

In addition the security of the tunneling process depends on the security of the communication between the client device and the host device which is used for implementing tunneling.

Furthermore the invention may be implemented completely in software i.e. by programming appropriately currently available host device and client device. Thus no additional hardware is required so that implementation of the invention is easy and may be inexpensive.

More precisely the present invention proposes a process for enabling communication between a client device and a peripheral unit the peripheral unit being arranged for communicating with a host device using packets of a first type transmitted between the peripheral unit and the host device according to a first communication mode this first communication mode being wireless the host device being further arranged for communicating with the client device using packets of a second type transmitted between the host device and the client device according to a second communication mode which process comprises 

Thus the server transport module and the client transport module form together a communication interface at transport level between the client device and the host device for communication between the client device and the peripheral unit.

In a particular implementation of the invention the server application module may also be suitable for exposing the peripheral unit to the client device.

In preferred implementations of the invention the following additional features may be used separately of in combination with one another 

The invention is now described in the particular case of Bluetooth communication used for the wireless communication mode between the host device and at least one peripheral unit.

The host device pertains to the Bluetooth piconet which further comprises Bluetooth connected peripheral units such as a keyboard a mouse a headset a printer etc. . . . . The host device may be a computer unit for example and the piconet may comprise additional devices and peripheral units. All the peripheral units and devices pertaining to the piconet are designed for Bluetooth communication with each other as commonly known.

The client device may be a mobile phone or a tablet which is connected to the host device using a communication channel separate from that operating within the Bluetooth piconet . This connection between the devices and may be wired or wireless. For example the devices and may be connected to each other in a peer to peer P2P mode.

For illustration purpose we describe now an implementation of the invention which aims at controlling the printer with the client device . We will also suppose that the communication mode between the host device and the client device is IP over Wi Fi connection for example a Wi Fi peer to peer P2P connection also known as Wi Fi DIRECT.

Because the host device pertains to the Bluetooth piconet it is provided with communication modules arranged according to the Bluetooth protocol stack. This stack comprises in particular from the application level to the base level an application layer input output I O libraries Bluetooth BT drivers a Host Controller Interface HCI driver a Bluetooth BT controller and a Bluetooth BT radio layer. Further intermediate communication layers may also be used. In a known manner the interface between the I O libraries and the Bluetooth drivers is the Application Programming Interface API and the interface between the HCI driver and the Bluetooth controller is the standardized Host Controller Interface.

For communicating with the client device the host device is also provided with communication modules arranged for IP communication. Again in a known manner these modules comprise in particular from the application level to the base level the application layer input output I O libraries a Transmission Control Protocol TCP or User Datagram Protocol UDP layer an Internet Protocol IP layer a Medium Access Control MAC layer and a physical PHY layer.

The client device is also designed for IP communication in a similar way and further at least partially designed for Bluetooth communication too.

Starting from this configuration the devices and are completed in the following manner for implementing the present invention 

The Bluetooth server module and the Bluetooth client module correspond respectively to the server application module and the client application module introduced in the general description of the invention.

As an example the server transport module and the client transport module may be added at the HCI interface in the Bluetooth stack but they may be added alternatively anywhere else in the Bluetooth stack between the API and the HCI interfaces including at the API interface. Therefore the server transport module is a HCI server module in the implementation represented and the client transport module is a HCI client module .

The curved line C in represents a process path for data produced by the application run in the client device and transmitted to the printer . The HCI client module transports the HCI packets over the TCP IP or UDP IP layers so that the content of the HCI packets is transmitted over the Wi Fi connection to the host device . Within the host device this content in reception processed through the IP TCP or IP UDP layers and then transmitted to the HCI server module . This latter recovers the HCI packets and then processes so that the data are Bluetooth transmitted to the printer . During such communication process the HCI packets of the Bluetooth communication mode are encapsulated within IP packets which are transmitted over the Wi Fi connection between the devices and . Reverse process is used for data transmitted from the printer to the client device corresponding to the same path C in the opposite direction. Thus the HCI server module and the HCI client module form with each other a new HCI transport interface in addition to the Bluetooth interfaces provided by the Bluetooth specification.

There are four different types of HCI packets as described in Vol. 2 part E clause 5.1 of the Bluetooth 2.1 EDR standard that need to be handled by the HCI server module and the HCI client module 

For still allowing normal Bluetooth operation of the host device with respect to the piconet the HCI server module is further provided with a bypass mode BP which drives the HCI packets directly between the Bluetooth controller and the HCI driver within the host device . Similarly the HCI client module may also be provided with a bypass mode BP if the client device is also able to operate complete Bluetooth transmission with other external devices not shown .

Path C shows that within the host device the Bluetooth drivers and the HCI driver of the Bluetooth stack are not required for the invention. It also shows that the Bluetooth controller and the Bluetooth radio facilities within the client device are not required either for implementing the invention. Therefore the invention provides access to the Bluetooth peripheral units for the client device even if this latter is devoid of Bluetooth radio facilities.

TCP IP or UDP IP processing within the devices and for implementing the invention may be selected depending on the type of the Bluetooth connection in the piconet . For example Bluetooth synchronous connections between the host device and one of the peripheral units may profit from UDP protocol layer characteristics whereas Bluetooth asynchronous connections better match characteristics of the TCP protocol layer.

The function of the Bluetooth server module may comprise exposing the peripheral units which are available in the piconet to the client device . Bluetooth server module also manages the virtual HCI connection which is provided by the invention between the devices and . Thus the Bluetooth pairings of the peripheral units with the host device when they are set prior to initiation of the communication between devices and can be handed over to the client device . If necessary the Bluetooth server module may also configure the peripheral units specifically so that these units can be Bluetooth controlled by the client device . Indeed it may be useful to change Bluetooth connection related parameters for the peripheral units to take into account network characteristics such as latency or error sensitivity. For example timeout parameters of the peripheral units may be adapted.

Optionally when a further peripheral unit appears available in the piconet after the devices and have been virtually HCI connected to each other the Bluetooth server module may allow the client device to initiate direct pairing with this further peripheral unit.

The function of the Bluetooth client module comprises managing the Bluetooth peripheral units and the HCI connection from the client device side.

Generally the Bluetooth server module initiates and terminates the Bluetooth connections between the client device and any one of the peripheral units but it is possible for the Bluetooth client module to do this as well.

According to a first improvement of the invention the Bluetooth server module may adapt the Bluetooth peripheral data format currently used within the piconet to a format supported by the client device .

According to a second improvement of the invention one of the modules to preferably the Bluetooth server module may have additional functions relating to communication security. In particular it may be adapted for one or more of the following functions 

 1 the Bluetooth server module may support a restricted subset of Bluetooth commands available to the client device in particular a restricted subset of HCI commands so as to limit to this subset the commands produced by the client device which are forwarded to the Bluetooth peripheral units . Then the Bluetooth commands which do not pertain to the subset but are produced by the client device are handled but not executed by the host device 

 2 the Bluetooth server module may disable discovery of some of the Bluetooth peripheral units by the client device using the server transport module . Such disabling controlled directly via the Bluetooth server module is easy to implement because it is controlled at application level 

 3 the Bluetooth server module may change or update a security link key of the Bluetooth connection between the client device and at least one of the peripheral units 

 4 the Bluetooth server module may change or update an encryption key of the Bluetooth connection between the client device and at least one of the peripheral units 

 5 the Bluetooth server module may prevent the client device from obtaining or changing security data of the Bluetooth communication mode used within the piconet and or used between the client device and one or several of the peripheral units and

 6 the Bluetooth server module may provide a secured communication mode between the host device and the client device for the Wi Fi transmitted packets which transport a content of Bluetooth packets flowing between the client device and one or several of the peripheral units .

Although these functions have been recited for Wi Fi connection between the host device and the client device and for Bluetooth communication between the host device and the peripheral unit they may be combined with any communication mode between devices and and any wireless communication mode between the host device and the peripheral unit and also any level for the server transport module and the client transport module within the protocol stack of the first communication mode.

Possibly some of these security functions 1 to 6 may be implemented on the client device side by the client application module and or the transport client module .

Changes may be introduced when implementing the invention with respect to the above description. As a general rule the communication mode between the host device and the client device may use any transmission medium known. This communication mode between the host device and the client device may also be other than IP protocol. In particular it may be Bluetooth protocol again then leading to tunneling of a first Bluetooth connection over a second Bluetooth connection.

