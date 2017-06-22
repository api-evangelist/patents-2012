---

title: Braking system
abstract: A brake control unit for a railway vehicle having first and second cores. The first core is responsible for brake control functions and the second core is responsible for communications. A switch controls communication between the second core and a communication bus on the railway vehicle to safeguard the braking function of the first core. The second core only has write access to the communication bus when enabled by the first core, which first core determines whether the system is in a defined safe state to safeguard the braking function. This reduces the testing requirements for new communications software.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09434391&OS=09434391&RS=09434391
owner: KNORR-BREMSE RAIL SYSTEMS (UK) LIMITED
number: 09434391
owner_city: Melksham
owner_country: GB
publication_date: 20120704
---
This patent application is a U.S. National Phase of International Patent Application No. PCT GB2012 000570 filed 4 Jul. 2012 which claims priority to British Patent Application No. 1111366.9 filed 4 Jul. 2011 the disclosures of which are incorporated herein by reference in their entirety.

The current standard communications design in a railway vehicle comprises a CAN bus which enables data to be communicated along the train between devices including the brake control units.

The CAN communication protocols have proven themselves over several decades of use. It is now conventional to use standard laptop computers to operate diagnostic software and the like which laptops can be plugged into the CAN bus and be used to communicate with the brake control units. The standard interfaces currently used in Train Management Systems TMS such as RS 485 MVB and FIP are regarded as being too slow by users who want to use faster standards such as Ethernet.

Ethernet in this context describes the lower level communications system i.e. the physical layer and simplest data packet transfer. Users require higher level protocols to be supported that sit on top of Ethernet e.g. Profinet CIP TCP UDP Web server maintenance.

As brake systems are safety critical it is necessary that any executable software code that runs on the brake control unit and any modules associated with the brake control unit such as wheel slide protection is tested and validated to SIL2 Safety Integrity Level 2 . The problem that this causes is that each new module fitted to the system would need to be validated to SIL2. However this requires several man years work and is too expensive and time consuming for most projects.

GB 2395241 discloses a trailer brake electronic control unit. The ECU has non volatile storage memory means for storing braking related control parameters particular to the vehicle and discretely programmable storage means to carry operating data for one or more auxiliary functions of the vehicle. This is operable to check one or more incoming and outgoing variables and control algorithms against a predefined list such as to safeguard the braking function against error modes. This approach suffers from the drawback that it does not meet users requirements for new APIs application programming interface to support new protocols and interface cards as the functionality in the control unit is limited.

The present disclosure provides a brake control unit for a railway vehicle having first and second cores wherein the first core is responsible for brake control functions and the second core is responsible for communications the arrangement further comprising a switch adapted to control communication between the second core and a communication bus on the railway vehicle so as to safeguard the braking function of the first core wherein the second core only has write access to the communication bus when enabled by the first core which first core determines whether the system is in a defined safe state to thereby safeguard the braking function.

The main Control processor provides all standard Brake Control Algorithm processing as before but the TMS communications are moved to a second Communications processor. The Communications processor is SIL0 compliant which reduces the requirement for testing.

Moreover all communications CPU performance is provided by the Communications processor allowing more performance for the control processor for Brake Control Algorithms.

A laptop running standard diagnostic software is also connected to the bus via a USB CAN bus dongle . This arrangement allows the laptop to communicate safely with the brake control unit .

The brake control unit core is responsible for the braking function and is connected to the bus. The core is responsible for communication functions and is connected to the bus by way of a CAN switch the operation of which switch is controlled by the brake control unit core . The communication core can receive data directly from the CAN bus but cannot write data to the CAN bus unless permitted to do so by the brake control unit core . The communication core comprises a web server and enables web based applications to be installed and run on the core. The communication core and any applications or software running on the core need not be validated to SIL2. Typically the communications core will only write to the bus when there is a software update or maintenance to the brake system which will require communication along the brakes layer of the bus. The communications core can monitor the data on the brake databus and this can either be logged in the core or sent back to a driver. The separation of the monitoring function from the brake control function will also result in a performance enhancement to the brake core as there is no extra loading. The arrangement also eases interaction with different level 2 buses.

The SIL0 processor only has write access to the Level 1 network when enabled by the SIL2 processor which determines whether the system is in a defined safe state so as to safeguard the braking function.

The bus is provided with several levels of security with communication on level 1 being the most secure as this is used for safety critical data such as that relating to the operation of the railway vehicle brakes. The communication core can receive data directly from the CAN bus but cannot write data to the CAN bus unless permitted to do so by the brake control unit core when the core has determined that the brake system is in a safe state. Typically such a safe state can include when the vehicle is stationary but it may include further variables such as ensuring that the emergency brake is applied or ensuring that the vehicle has been stationary for a predetermined period of time.

