---

title: Machine type communication gateway user equipment and machine type communication data relay method of the same
abstract: Provided are machine type communication (MTC) gateway user equipment (MGUE) and an MTC data relay method of the same. The MGUE includes a first radio matching unit configured to process a signal having a first frequency band characteristic and provide radio access matching with a base station, a second radio matching unit configured to process a signal having a second frequency band characteristic and provide radio access matching with at least one MTC device, a radio access switching processor configured to convert data respectively output by the first radio matching unit and the second radio matching unit and provide the converted data, and a controller configured to find an identifier of at least one MTC device related to MTC control information received from the first radio matching unit and control the second radio matching unit to transmit the MTC control information to the MTC device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09095000&OS=09095000&RS=09095000
owner: Electronics and Telecommunications Research Institute
number: 09095000
owner_city: Daejeon
owner_country: KR
publication_date: 20120914
---
This application claims priority to Korean Patent Application No. 10 2011 0107189 filed on Oct. 19 2011 and Korean Patent Application No. 10 2012 0061205 filed on Jun. 8 2012 in the Korean Intellectual Property Office KIPO the entire contents of which are hereby incorporated by reference.

Example embodiments of the present invention relate in general to machine type communication MTC gateway user equipment MGUE and an MTC data relay method of the same and more particularly to MGUE for performing Long Term Evolution LTE based MTC and an MTC data relay method in which the MGUE is employed.

With the quantum leap of technology mobile communication systems have become able to provide high speed data communication services in addition to voice communication services. As a next generation mobile communication system of Third Generation Partnership Project 3GPP universal mobile telecommunication system UMTS mobile communication system that is an existing mobile communication system standardization of a 3GPP LTE mobile communication system has recently been under way. The LTE system implements high speed packet based communication having a maximum transmission rate of about 300 Mbps which is higher than a currently provided data transmission rate.

Meanwhile there is a recent trend toward providing machine to machine M2M MTC technology which can be used in vehicle telematics the administration of physical distribution smart metering systems remote asset management systems point of sale POS systems and security related fields through LTE systems. Compared with existing cellular phones that are being used in mobile communication systems M2M MTC devices have low mobility and transmit receive low speed data. In general an MTC system is implemented by a plurality of MTC devices e.g. as in the case of a metering system .

Due to these characteristics of MTC there are too many problems for a mobile communication network which has been standardized for relatively high speed data and relatively high mobility of existing cellular phones to accommodate a plurality of MTC devices.

In addition to a structure in which an MTC device or user equipment UE currently under standardization through 3GPP technical specification TS 22.368 is directly connected to a 3GPP network without a gateway problems to be solved are as follows 

First a base station should efficiently accommodate MTC UE with low power consumption and low output. If this is not possible another method for efficiently accommodating MTC UE with low power consumption and low output should be provided. Also implementation of an MTC device with low power consumption and low output requires a relatively narrow band standard and thus an LTE modem standard for a narrow band e.g. 1.4 MHz is needed.

In addition MTC devices are implemented in different forms according to their application fields and are vast in number compared with existing general UE. Thus system complexity increases too much for an LTE network to manage all MTC devices. Furthermore there are necessities of communication activation deactivation triggering addressing and group management mobility data conversion authentication and authorization encryption etc. of MTC devices.

Accordingly example embodiments of the present invention are provided to substantially obviate one or more problems due to limitations and disadvantages of the related art.

Example embodiments of the present invention provide machine type communication MTC gateway user equipment UE MGUE that provides a machine to machine M2M service between an MTC server and an MTC device.

Example embodiments of the present invention also provide an MTC data relay method in which MGUE is employed.

In some example embodiments MGUE includes a first radio matching unit configured to process a signal having a first frequency band characteristic and provide radio access matching with a base station a second radio matching unit configured to process a signal having a second frequency band characteristic and provide radio access matching with at least one MTC device a radio access switching processor configured to convert data respectively output by the first radio matching unit and the second radio matching unit and provide the converted data and a controller configured to find an identifier ID of at least one MTC device related to MTC control information received from the first radio matching unit and control the second radio matching unit to transmit the MTC control information to the MTC device.

The controller may control MTC devices in units of at least one virtual cell VC and each VC may include at least one MTC device.

The MGUE may further include a storage configured to store at least one piece of data among an ID of at least one MTC device an authentication key activation or deactivation related data and a transmission reception triggering value of the MTC device.

The MGUE may further include an input output unit configured to receive MTC control information that is directly input without passing through the base station and provide the received MTC control information to the controller.

The controller may search the ID of the at least one MTC device stored in the storage to find the ID of the at least one MTC device related to the MTC control information.

The radio access switching processor may convert a signal output from the second radio matching unit into the signal having the first frequency band characteristic and provide the converted signal to the first radio matching unit.

A bandwidth or a center frequency of the first frequency band characteristic may differ from a bandwidth or a center frequency of the second frequency band characteristic.

In other example embodiments MGUE includes a radio matching unit configured to provide radio access matching with a base station and radio access matching with at lest one MTC device and a controller configured to find an ID of at least one MTC device related to MTC control information received from the radio matching unit and control the radio matching unit to transmit the MTC control information to the found at least one MTC device.

In other example embodiments an MTC data relay method includes receiving MTC control information for controlling at least one MTC device from a base station finding an ID of the at least one MTC device related to the MTC control information and performing a radio access matching process for data to be transmitted to the MTC device and transmitting the data subjected to the radio access switching process to the related at least one MTC device.

Receiving the MTC control information for controlling the at least one MTC device from the base station may include receiving the MTC control information through radio resources having a first frequency band characteristic.

Performing the radio access matching process for the data to be transmitted to the MTC device and transmitting the data subjected to the radio access switching process to the related at least one MTC device may include transmitting the data subjected to the radio access switching process to the at least one MTC device through radio resources having a second frequency band characteristic.

The MTC data relay method may further include receiving data from the at least one MTC device performing a radio access switching process so that the data received from the at least one MTC device has the first frequency band characteristic and transmitting the data subjected to the radio access switching process to the base station.

Example embodiments of the present invention are disclosed herein. However specific structural and functional details disclosed herein are merely representative for purposes of describing example embodiments of the present invention however example embodiments of the present invention may be embodied in many alternate forms and should not be construed as limited to example embodiments of the present invention set forth herein.

Accordingly while the invention is susceptible to various modifications and alternative forms specific embodiments thereof are shown by way of example in the drawings and will herein be described in detail. It should be understood however that there is no intent to limit the invention to the particular forms disclosed but on the contrary the invention is to cover all modifications equivalents and alternatives falling within the spirit and scope of the invention.

It will be understood that although the terms first second etc. may be used herein to describe various elements these elements should not be limited by these terms. These terms are only used to distinguish one element from another. For example a first element could be termed a second element and similarly a second element could be termed a first element without departing from the scope of the present invention. As used herein the term and or includes any and all combinations of one or more of the associated listed items.

It will be understood that when an element is referred to as being connected or coupled with another element it can be directly connected or coupled with the other element or intervening elements may be present. In contrast when an element is referred to as being directly connected or directly coupled with another element there are no intervening elements present. Other words used to describe the relationship between elements should be interpreted in a like fashion i.e. between versus directly between adjacent versus directly adjacent etc. .

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the invention. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises comprising includes and or including when used herein specify the presence of stated features integers steps operations elements and or components but do not preclude the presence or addition of one or more other features integers steps operations elements components and or groups thereof.

Unless otherwise defined all terms including technical and scientific terms used herein have the same meaning as commonly understood by one of ordinary skill in the art to which this invention belongs. It will be further understood that terms such as those defined in commonly used dictionaries should be interpreted as having a meaning that is consistent with their meaning in the context of the relevant art and will not be interpreted in an idealized or overly formal sense unless expressly so defined herein.

It should also be noted that in some alternative implementations the functions acts noted in the blocks may occur out of the order noted in the flowcharts. For example two blocks shown in succession may in fact be executed substantially concurrently or the blocks may sometimes be executed in the reverse order depending upon the functionality acts involved.

The term user equipment UE used herein may be referred to as a mobile station MS user terminal UT wireless terminal access terminal AT terminal subscriber unit subscriber station SS wireless device wireless communication device wireless transmit receive unit WTRU mobile node mobile or other terms. Various example embodiments of UE may include a cellular phone a smart phone having a wireless communication function a personal digital assistant PDA having a wireless communication function a wireless modem a portable computer having a wireless communication function a photographing apparatus such as a digital camera having a wireless communication function a gaming apparatus having a wireless communication function a music storing and playing appliance having a wireless communication function an Internet home appliance capable of wireless Internet access and browsing and also portable units or UE having a combination of such functions but are not limited to these.

The term base station used herein generally denotes a fixed point communicating with UE and may be referred to as other terms such as a Node B an evolved Node B eNB a base transceiver system BTS or an access point.

Hereinafter example embodiments of the present invention will be described in detail with reference to the appended drawings. To facilitate overall understanding of the present invention like numbers refer to like elements throughout the drawings and the description of the same component will not be reiterated.

The MME is a control plane node of the evolved packet core EPC . As an apparatus that takes on various control functions and performs mobility management of idle mode UE the MME is connected with at least one base station.

As a user plane node the S GW serves to connect the EPC with an LTE radio access network RAN . Thus the S GW provides a data bearer and generates or removes the data bearer under the control of the MME .

Meanwhile the S GW can be present as a single entity that serves as a packet data network PDN gateway PGW and so on. Here the PGW connects a user plane connected with the EPC to the Internet using an SGi interface.

UE can access an external network through the base station and the S GW and the base station communicates with the UE through a radio channel. In LTE all user traffic including real time services such as voice over Internet protocol VoIP through the IP is served through a shared channel. For this reason there is a need for an apparatus that collects status information on UE and performs scheduling and the base station takes on this role.

Also the base station serves to control radio resources of cells. In general one base station controls a plurality of cells. To implement a maximum transmission rate of 300 Mbps LTE employs orthogonal frequency division multiplexing OFDM as a radio access technique in a maximum bandwidth of 20 MHz. Also the base station employs an adaptive modulation and coding AMC scheme of determining a modulation scheme and a channel coding rate according to the channel state of the UE .

Through a 3GPP system shown in an end to end application between an MTC device and an MTC server is provided. The 3GPP system provides transmission and communication services 3GPP bearer service IP multimedia service IMS and short message service SMS optimized for MTC.

As shown in an MTC device accesses a 3GPP network universal terrestrial radio access network UTRAN evolved UTRAN E UTRAN global system for mobile communications GSM edge RAN GERAN etc. through an MTCu interface. The MTC device communicates with MTC service logic components using an MTC service abstraction layer that uses MTC functions 3GPP bearer services and SMS and IMS application servers provided by a public land mobile network PLMN .

The MTC server is an entity that is connected with a 3GPP network through a generic service layer application programming interface API . The MTC service abstraction layer has a unique capability of mapping to solid things provided by specific access. For example a communication capability in 3GPP access is provided using MTCi MTCsms interfaces and the MTC service abstraction layer communicates with MTC devices according to the capability. The MTC service logic components may be outside or inside of an operator domain.

Among interfaces shown in the MTCu interface provides access to a 3GPP network for transmission of user plane and control plane graphics. The MTCu interface may be based on Uu Um Ww and LTE Uu interfaces.

Among the interfaces the MTCi interface is a reference point that is used by the MTC server to connect to the 3GPP network and communicates with the MTC device through a 3GPP bearer service IMS. The MTCi interface may be based on Gi Sgi and Wi interfaces.

Among the interfaces the MTCsms interface is a reference point that is used by the MTC server to connect to the 3GPP network and communicates with the MTC device through a 3GPP SMS. The MTCsms interface provides transmission of user subscriber related data as well as service related data.

In an MTC user is provided with an MTC service through the MTC server. The MTC server may access the 3GPP network via a public data network PDN and perform a variety of MTC services. The 3GPP network may provide the MTC server with a communication network and perform a variety of control functions so that the MTC server can receive information on the MTC device that has accessed the 3GPP network. Also the 3GPP network includes a home PLMN HPLMN which is a home network and a visited PLMN VPLMN which is a visited network and provides service.

An MTC device employs OFDM as a radio access technique in a maximum bandwidth of 20 MHz according to for example 3GPP specifications TS36.211 to TS36.213. In this case an MTC device for a low speed and low mobility MTC service is generally implemented as a modem with low output and low power consumption and it is difficult for an MTC device having such characteristics to connect to a communication network.

According to the current standard a modem that operates at a maximum speed of 300 Mbps or more in a bandwidth of up to 20 MHz should be implemented and also the output of a radio frequency RF part is relatively high and thus consumes high power.

Meanwhile in order for a base station to conform to both 1.4 MHz and 5 MHz model standards which are suitable for low speed data a base station standard should be totally modified. Thus it is difficult to standardize a narrowband modem standard of a base station to support a 20 MHz bandwidth for a short time period.

For this reason the present invention proposes MTC gateway UE MGUE that can cause an MTC device having a low output narrowband MTC modem to effectively interoperate with a base station without substantially modifying the current base station standard.

A communication system shown in according to an example embodiment of the present invention may include an MME a wired network including an S GW at least one base station or eNB interoperating with the wired network and at least one MTC device communicating with the wired network through such a base station.

As shown in the MGUE is connected with the base station using radio access technology that supports up to a maximum of 20 MHz according to for example 3GPP specifications TS36.211 to TS36.213. For effective access of at least one low output narrowband MTC device the MGUE may also function as a base station having a relatively short cell radius.

The MGUE according to example embodiments of the present invention may be permanently stationed at one fixed location or may move into a cell radius of another base station as shown in .

In an application area in need of a continuous MTC service the MGUE may be permanently stationed i.e. fixed without mobility . On the other hand when occasional access is needed for reading electricity gas and water meters etc. the MGUE may be effectively accessed by MTC devices while moving.

In the present invention using the above described MGUE the MTC device can be implemented as UE having functions of a low output low speed narrowband modem. In other words the MGUE is used to perform relay between a base station and the MTC device and thus there is no problem for the MTC device to communicate with the base station even if the MTC device is implemented as low priced UE having functions of a low output low speed narrowband modem.

However in connection with a narrowband LTE modem standard LTE standardization may be performed to simplify 3GPP specifications TS36.211 to TS36.213 which are radio access technologies for existing OFDM having a maximum bandwidth of 20 MHz for low speed in order to implement the current maximum transmission rate of 300 Mbps.

The MGUE may switch its radio access standard between 20 MHz 5 MHz and 1.4 MHz to match various MTC devices. A cell formed by the MGUE according to an example embodiment of the present invention may be configured with a radius of about several hundred meters and low output.

MGUE according to an example embodiment of the present invention as shown in may receive a control message from an MTC server via a mobile communication network and perform an MTC function. Also the MGUE may perform an MTC function under its own control thereby transmitting collected data to a specific MTC server.

The MGUE according to the example embodiment shown in effectively accommodates a plurality of MTC devices that are classified into kinds of groups. Here the MGUE may be present in the form of a small base station that has a small cell radius and can move.

The present invention proposes the concept of a virtual cell VC in which one VC includes at least one MTC device. Also the one piece of MGUE may have a plurality of VCs and the MGUE may manage and control MTC devices according to groups of respective VC units by for example performing triggering of MTC devices in an MGUE cell using VCs.

MGUE according to example embodiments of the present invention may include a first radio matching unit that provides radio access matching with a base station a second radio matching unit that provides radio access matching with at least one MTC device a radio access switching processor that converts data respectively output by the first radio matching unit and the second radio matching unit and provides the converted data and a controller that finds an identifier ID of at least one MTC device related to MTC control information received from the first radio matching unit and controls the second radio matching unit to transmit the MTC control information to the MTC device. In addition the MGUE may further include a storage a display unit and an input output unit .

The MGUE is connected with a base station using radio access technology that supports up to a maximum of 20 MHz according to 3GPP specifications for example TS36.211 to TS36.213. The first radio matching unit performs access function matching with the base station and receives an MTC message from an MTC server. Meanwhile the MGUE may not only receive an MTC message through an MTC server but also receive an MTC related command from a user through the input output unit .

Here the user may be a manager in charge of metering for example in the case of smart metering and the input output unit may be connected with UE of the manager by wire through a cable or the like. More preferably the input output unit may be wirelessly connected with the UE of the manager using near field communication NFC and so on. Thus when a measuring instrument comes close to the MGUE within a predetermined distance the input output unit may be activated and data transmission may be performed.

The MGUE also performs radio access function matching with at least one MTC device through the second radio matching unit . For example the MGUE and a plurality of MTC devices which have 20 MHz 5 MHz and 1.4 MHz radio access functions respectively can wirelessly access each other.

The radio access switching processor performs a mutual conversion process between traffic of an MTC device conforming to a low speed 1.4 MHz or 5 MHz radio access standard and traffic of an MTC server operating in a 20 MHz band so that the MTC device and the MTC server can communicate with each other.

The controller interprets the MTC control information e.g. in the form of an SMS message received from the first radio matching unit and receives required IDs of MTC devices from the MTC server or acquires the IDs from the storage .

The controller controls the second radio matching unit to transmit a message for activating the MTC devices corresponding to the acquired MTC IDs. The second radio matching unit receives related information from MTC devices and the radio access switching processor converts the information received from the MTC devices and provides the converted information to the controller or the first radio matching unit .

The information received from the several MTC devices may be directly transmitted to the MTC server through the first radio matching unit via a mobile communication network or may be integrated stored and then transmitted to the MTC server through a base station at once.

The storage stores a variety of data required for managing a plurality of MTC devices such as IDs of the respective MTC devices that can be processed by the MGUE an authentication key activation deactivation data and transmission reception triggering values of the respective MTC devices. Here the IDs of the respective MTC devices may be managed as a group according to an application field.

The display unit displays state information on the MGUE and provides process results etc. to a screen when an administrator or a user directly inputs a control command.

Although the first radio matching unit the second radio matching unit and the radio access switching processor are shown as separate blocks in these three blocks may be combined into one radio matching block in which functions of the three blocks are integrated.

First MGUE receives MTC control information from a base station or directly receives MTC control information from an administrator or a user through an input output unit of the MGUE S . The MGUE finds an ID of an MTC device included in the MTC control information S and generates control information for the MTC device having the ID S . For communication with an MTC device operating in a narrowband the generated control information is subjected to a radio access matching process S and transmitted to at least one MTC device. Here the at least one MTC device may be devices belonging to the same group referred to as a VC in this specification .

Subsequently when the MGUE receives MTC data from the MTC devices that have received the MTC control information and have been activated S the MGUE performs a radio access switching process on the received data S and transmits the data to a network S .

Using the above described MGUE according to example embodiments of the present invention it is possible to implement a low power low output MTC device for providing an MTC service in a mobile communication system.

Also by accommodating a plurality of low speed low output devices in an LTE network a new market can be opened up.

While the example embodiments of the present invention and their advantages have been described in detail it should be understood that various changes substitutions and alterations may be made herein without departing from the scope of the invention.

