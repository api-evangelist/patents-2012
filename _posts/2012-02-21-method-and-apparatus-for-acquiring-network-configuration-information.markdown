---

title: Method and apparatus for acquiring network configuration information
abstract: A method and an apparatus for acquiring network configuration information are disclosed. The method includes: when a terminal device dials up and needs to carry out network data services, delivering, by a NDIS driver layer of the terminal device, a Query Network Configuration Information message to a wireless modem; and acquiring, by the NDIS driver layer, the network configuration information returned from the wireless modem, and providing an application layer of the terminal device with the acquired network configuration information. In this way, when the terminal device does not provide the function of a DHCP client, the terminal device can effectively acquire needed network configuration information to implement dial-up successfully, and can carry out network data services online, so as to ensure that normal services can be carried out on the terminal device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08717937&OS=08717937&RS=08717937
owner: Huawei Device Co., Ltd.
number: 08717937
owner_city: Shenzhen
owner_country: CN
publication_date: 20120221
---
This application is a continuation of International Application No. PCT CN2010 075539 filed on Jul. 29 2010 which claims priority to Chinese Patent Application No. 200910091040.0 filed on Aug. 20 2009 both of which are hereby incorporated by reference in their entireties.

The present invention relates to the network communication field and in particular to a method and an apparatus for acquiring network configuration information.

Currently when a terminal device carries out network data services after the dial up Packet Data Protocol PDP Packet Data Protocol context is activated that is after a data service connection is set up the terminal device needs to acquire corresponding network configuration information namely IP address information and gateway information. Then the terminal device sets the IP address so that the dial up succeeds which guarantees the implementation of network data services. The foregoing terminal device may be a personal computer PC or any other computer processing device.

In the prior art static network configuration information may be set manually or the network configuration information may be acquired dynamically. In the prior art the network configuration information is acquired dynamically through a Dynamic Host Configuration Protocol client DHCP Client Dynamic Host Configuration Protocol Client . is a schematic diagram of a signaling interaction in which the network configuration information is acquired dynamically through the DHCP client in the prior art. As shown in after the terminal device initiates a dial up operation the DHCP client on the terminal device sets up a connection with the modem modem the modem initiates an Activate PDP request that is a data service call to the network after the network responds successfully that is after the data service call is set up successfully it returns corresponding network configuration information that is IP address information and gateway information to the modem after the terminal device receives an ACK signal sent from the modem the DHCP client delivers a DHCP Query request to the modem the modem returns to the terminal device the network configuration information allocated by the network when the terminal device confirms that the received network configuration information is correct and available the terminal device sets the IP address properly. The dial up process is complete and the terminal device can start to perform corresponding network data services.

According to the solution in the prior art the current solution of acquiring network configuration information is implemented on the basis that the terminal device can provide the DHCP client function. If the terminal device cannot provide the DHCP client function or disables corresponding DHCP client function the terminal device cannot dial up successfully and can only set up a connection at most. Thus the terminal device cannot carry out network data services online and normal services on the terminal device are affected.

Embodiments of the present invention provide a method and an apparatus for acquiring network configuration information so that when a terminal device does not provide the function of a DHCP client the terminal device can effectively acquire network configuration information to implement dial up successfully. In addition the terminal device can carry out network data services online which ensures that normal services can be carried out on the terminal device.

An embodiment of the present invention provides a method for acquiring network configuration information where the method includes 

when a terminal device dials up and needs to carry out network data services delivering by a Network Driver Interface Standard Network Driver Interface Standard NDIS driver layer of the terminal device a Query Network Configuration Information message to a wireless modem and

acquiring by the NDIS driver layer network configuration information returned by the wireless modem and providing an application layer of the terminal device with the acquired network configuration information.

An embodiment of the present invention provides an apparatus for acquiring network configuration information where the apparatus includes 

a message delivering unit disposed at a Network Driver Interface Standard NDIS driver layer of a terminal device and configured to deliver a Query Network Configuration Information message to a wireless modem when the terminal device dials up and needs to carry out network data services and

an information acquiring unit disposed at the Network Driver Interface Standard NDIS driver layer of the terminal device and configured to acquire network configuration information returned by the wireless modem and provide an application layer of the terminal device with the acquired network configuration information.

According to the foregoing technical solutions when a terminal device dials up and needs to carry out data services a Network Driver Interface Standard Network Driver Interface Standard NDIS driver layer of the terminal device may deliver a Query Network Configuration Information message to the wireless modem the NDIS driver layer acquires the network configuration information returned from the wireless modem and provides an application layer of the terminal device with the acquired network configuration information. In this way when the terminal device does not provide the function of the DHCP client the terminal device can effectively acquire needed network configuration information to implement dial up successfully. In addition the terminal device can perform network data services online which ensures that normal services can be carried out on the terminal device.

Embodiments of the present invention provide a method and an apparatus for acquiring network configuration information. When a terminal device does not provide the function of a DHCP client if the terminal device needs to implement dial up to carry out network data services an NDIS driver layer of the terminal device may deliver a Query Network Configuration Information command to a wireless modem modem where the network configuration information may be information such as IP address information and gateway configuration information after the wireless modem receives the query command the wireless modem may return corresponding network configuration information to the NDIS driver layer of the terminal device according to the query command the terminal device completes the setting of corresponding IP address and gateway according to the acquired network configuration information and implements dial up successfully so as to ensure that normal services can be carried out on the terminal device.

To better illustrate the embodiment of the present invention the specific embodiment of the present invention is described with reference to accompanying drawings. is a flow chart schematic of a method according to Embodiment 1 of the present invention. The method includes the following steps 

In step when a terminal device dials up and needs to carry out network data services a Network Driver Interface Standard NDIS driver layer of the terminal device may deliver a Query Network Configuration Information message to a wireless modem.

In the specific implementation process when the terminal device dials up the terminal device may first set up a connection with the wireless modem the wireless modem may send an Activate PDP request to a network after the activation is performed successfully the network returns corresponding network configuration information to the wireless modem the wireless modem returns a corresponding ACK signal to the terminal device again. At this time the Network Driver Interface Standard NDIS driver layer of the terminal device may deliver the Query Network Configuration Information message to the wireless modem.

The Query Network Configuration Information message may be delivered to the wireless modem via an NDIS port by using modem command language that is an AT command or may be delivered to the wireless modem via a serial port by using modem command language or may be delivered to the wireless modem via an NDIS port by using NDIS command language that is a customized command .

In step after the wireless modem receives the Query Network Configuration Information message sent from the NDIS driver layer the wireless modem may transmit to the NDIS driver layer the network configuration information acquired by the wireless modem from the network. In this way the NDIS driver layer in the terminal device can acquire the network configuration information returned by the wireless modem.

In the specific implementation process the way that the wireless modem transmits the network configuration information to the NDIS driver layer depends on the way that the wireless modem receives query request information. That is if the Query Network Configuration Information message is delivered via the NDIS port by using the modem command language the wireless modem may return the network configuration information to the NDIS driver layer of the terminal device via the NDIS port if the Query Network Configuration Information message is delivered via the serial port by using the modem command language the wireless modem may return the network configuration information to the NDIS driver layer via the serial port if the Query Network Configuration Information message is delivered via the NDIS port by using the NDIS command language the wireless modem may return the network configuration information to the NDIS driver layer of the terminal device via the NDIS port.

Step Provide an application layer of the terminal device with the acquired network configuration information.

In step after the NDIS driver layer of the terminal device acquires the network configuration information returned from the wireless modem the acquired network configuration information may be provided to the application layer of the terminal device so as to perform a subsequent configuration operation.

After the application layer of the terminal device receives the network configuration information the configuration of a network address may be completed by using the acquired network configuration information and dial up is implemented successfully so as to carry out network data services.

In the specific implementation process when the terminal device invokes the wireless wide area network application programming interface WWAN API to operate the wireless modem the wireless modem may be a wireless wide area network device WWAN device .

Through the implementation of the technical solution provided in Embodiment 1 when the terminal device does not provide the function of the DHCP client the terminal device can effectively acquire needed network configuration information to implement dial up successfully and can carry out network data services online so as to ensure that normal services can be carried out on the terminal device.

Then after PDP is activated that is after a data service connection is set up the driver layer WWAN miniport drivers receives an ACK signal sent from the WWAN device the driver layer may deliver an Acquire Network Configuration Information request to the WWAN device via the NDIS port by using the AT command the WWAN device returns a processing result of the AT command to the driver layer WWAN miniport drivers via the NDIS port the driver layer provides an application layer of the terminal device with returned network configuration information to complete the setting of the network address.

Through the implementation of the technical solution provided in Embodiment 2 when the terminal device does not provide the function of the DHCP client the terminal device can effectively acquire needed network configuration information to implement dial up successfully and can carry out network data services online so as to ensure that normal services can be carried out on the terminal device. In addition the message interaction is completed by using the AT command and the NDIS port flexibly and the AT command can be transmitted without adding a special port so as to save port resources and facilitate the information transfer.

Similarly through the implementation of the technical solution provided in Embodiment 3 when the terminal device does not provide the function of the DHCP client the terminal device can effectively acquire needed network configuration information to implement dial up successfully and can carry out network data services online so as to ensure that normal services can be carried out on the terminal device. In addition the message interaction is completed by using the AT command and the serial port flexibly and the AT command can be transmitted without adding a special port so as to save port resources and facilitates the information transfer.

Similarly through the implementation of the technical solution provided in Embodiment 4 when the terminal device does not provide the function of the DHCP client the terminal device can effectively acquire needed network configuration information to implement dial up successfully and can carry out network data services online so as to ensure that normal services can be carried out on the terminal device. In addition the message interaction is completed by using the NDIS command and the NDIS port flexibly and the AT command can be transmitted without adding a special port so as to save port resources and facilitates the information transfer.

Embodiment 5 of the present invention provides an apparatus for acquiring network configuration information. is a schematic structural diagram of the apparatus provided in Embodiment 5. The apparatus includes a message delivering unit and an information acquiring unit .

The message delivering unit is disposed at a Network Driver Interface Standard NDIS driver layer of a terminal device and is configured to deliver a Query Network Configuration Information message to a wireless modem when the terminal device dials up and needs to carry out network data services. The specific mode of sending a query message refers to the method provided in Embodiment 1 of the present invention.

The information acquiring unit is disposed at the Network Driver Interface Standard NDIS driver layer of the terminal device and is configured to acquire network configuration information returned by the wireless modem and provide an application layer of the terminal device with the acquired network configuration information.

a first delivering module configured to deliver the Query Network Configuration Information message to the wireless modem via an NDIS port by using modem command language and or

a second delivering module configured to deliver the Query Network Configuration Information message to the wireless modem via a serial port by using modem command language and or

a third delivering module configured to deliver the Query Network Configuration Information message to the wireless modem via an NDIS port by using NDIS command language.

In addition the apparatus may further include an address configuring unit . The address configuring unit is disposed at the application layer of the terminal device and is configured to complete network address configuration by using the acquired network configuration information.

The foregoing apparatus for acquiring network configuration information is disposed in the terminal device.

It should be noted that in the preceding apparatus embodiment units that are included are divided only according to function logics. However the division is not limited thereto as long as the units can implement corresponding functions. In addition each functional unit is named for the purpose of differentiation only and specific names are not intended to limit the protection scope of the present invention.

Persons of ordinary skills in the art should understand that all or part of the steps in the methods provided in the preceding embodiments may be performed by a program instructing relevant hardware. The program may be stored in a computer readable storage medium such as a read only memory random access memory ROM RAM a magnetic disk and a CD ROM.

In conclusion according to the embodiments of the present invention when the terminal device does not provide the function of the DHCP client the terminal device can effectively acquire needed network configuration information to implement dial up successfully and can carry out network data services online so as to ensure that normal services can be carried out on the terminal device.

Detailed above are merely exemplary embodiments of the present invention however the protection scope of the present invention is not limited thereto. Any modification or replacement readily derived by those skilled in the art without departing from the technical scope disclosed in the present invention should fall within the protection scope of the present invention. Therefore the protection scope of the present invention is subject to the appended claims.

