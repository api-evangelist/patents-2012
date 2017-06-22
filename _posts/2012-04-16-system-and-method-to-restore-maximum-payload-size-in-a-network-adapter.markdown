---

title: System and method to restore maximum payload size in a network adapter
abstract: Method and system for managing a maximum payload size (MPS) between a host system and an adapter is provided. The method includes storing a host maximum payload size (MPS) value of the host system as an adapter MPS value for the adapter operationally coupled to the host system; storing a host identifier at the adapter for identifying the host system; setting an adapter MPS value to the host MPS value; resetting the adapter MPS value to a default value after an event; and restoring the adapter MPS value to the host MPS value when the host identifier stored at the adapter matches with a host identifier value stored by the host system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08996730&OS=08996730&RS=08996730
owner: QLOGIC, Corporation
number: 08996730
owner_city: Aliso Viejo
owner_country: US
publication_date: 20120416
---
This patent application is a continuation of application Ser. No. 12 817 707 filed on Jun. 17 2010 which claims priority under 35 USC 119 e to U.S. provisional application Ser. No. 61 187 906 filed on Jun. 17 2009 entitled SYSTEM AND METHOD TO RESTORE MAXIMUM PAYLOAD SIZE IN A NETWORK ADAPTER the disclosures of which are incorporated herein in their entireties.

Computing systems communicate with other devices using adapters e.g. host bus adapters network interface cards or adapters that can handle both network and storage traffic. During initialization for example during a boot process a computing system may also be referred to as host system sets up various parameters for transfer of data between the host system and other devices via the adapter. One such parameter is a maximum payload size MPS . The MPS defines a maximum size of a payload typically in bytes that can be transmitted between the host system and the adapter. The adapter typically uses a default MPS value. The default MPS value may be different from the MPS value that is used by the host system to transfer data. To avoid conflict the host system may change the default MPS value of the adapter to the value that is used by the host system.

For various operational and functional reasons for example power saving modes like hibernation the host system may switch to a mode when minimal functionality of the host system is maintained. In some of these modes the host system may disable the adapter for example to conserve energy. When the host system is instructed to be switched back to normal operation the host system instructs the adapter to be enabled.

When the adapter is disabled the host system performs a reset operation. During the reset operation the adapter MPS value may be reset to the default MPS value. When the adapter is enabled the host MPS value and the adapter MPS value will be different. The mismatch in the host MPS value and adapter MPS value may cause errors during data transfer between the host system and the adapter. Continuous efforts are being made to reduce errors during data transfer.

The various embodiments of the present system and methods have several features no single one of which is solely responsible for their desirable attributes. Without limiting the scope of the present embodiments as expressed by the claims that follow their more prominent features now will be discussed briefly. After considering this discussion and particularly after reading the section entitled Detailed Description one will understand how the features of the present embodiments provide advantages which include using a same maximum payload size for a computing system and an adapter.

In one embodiment a machine implemented method is provided. The method includes storing a host maximum payload size MPS value of a host system as an adapter MPS value for an adapter operationally coupled to the host system storing a host identifier at the adapter for identifying the host system setting an adapter MPS value to the host MPS value resetting the adapter MPS value to a default value after an event and restoring the adapter MPS value to the host MPS value when the host identifier stored at the adapter matches with a host identifier value stored by the host system.

In another embodiment a machine implemented method is provided. The method includes comparing if a host system identifier for a host system matches with a host system identifier stored at an adapter operationally coupled to the host system for sending and receiving information storing a host maximum payload size MPS value of a host system as an adapter MPS value for the adapter and restoring the adapter MPS value to the host MPS value after an event that resets the adapter MPS value to a default value that is different from the host identifier MPS value.

In yet another embodiment a system is provided. The system includes a host system having a first memory location for storing a host maximum payload size MPS value and a second memory location for storing a host identifier for uniquely identifying the host system.

The system further includes an adapter operationally coupled to the host system and having a first adapter memory location for storing the host identifier value that identifies the host system a second adapter memory location for storing an adapter MPS value that matches the host MPS value and a third memory location that stores an adapter MPS value when the adapter is initialized. After the adapter is reset due to an event the third memory location value is set to the host MPS value when the host identifier stored at the first adapter memory location matches with the host identifier stored at the second memory location of the host system.

This brief summary has been provided so that the nature of the disclosure may be understood quickly. A more complete understanding of the disclosure can be obtained by reference to the following detailed description of the preferred embodiments thereof concerning the attached drawings.

In one aspect a device and method is provided to maintain a consistent maximum payload size MPS value for both an adapter and a computing system. As described below this enables robust design and reliable operations involving peripheral devices.

As a preliminary note any of the embodiments described with reference to the figures may be implemented using software firmware hardware e.g. fixed logic circuitry manual processing or a combination of these implementations. The terms logic module component system and functionality as used herein generally represent software firmware hardware or a combination of these elements. For instance in the case of a software implementation the terms logic module component system and functionality represent program code that performs specified tasks when executed on a processing device or devices e.g. CPU or CPUs . The program code can be stored in one or more computer readable memory devices.

More generally the illustrated separation of logic modules components systems and functionality into distinct units may reflect an actual physical grouping and allocation of software firmware and or hardware or can correspond to a conceptual allocation of different tasks performed by a single software program firmware program and or hardware unit. The illustrated logic modules components systems and functionality may be located at a single site e.g. as implemented by a processing device or may be distributed over a plurality of locations.

The term machine readable media and the like refers to any kind of medium for retaining information in any form including various kinds of storage devices magnetic optical static etc. . Machine readable media also encompasses transitory forms for representing information including various hardwired and or wireless links for transmitting the information from one point to another.

The embodiments disclosed herein may be implemented as a computer process method a computing system or as an article of manufacture such as a computer program product or computer readable media. The computer program product may be computer storage media readable by a computer device and encoding a computer program of instructions for executing a computer process. The computer program product may also be a propagated signal on a carrier readable by a computing system and encoding a computer program of instructions for executing a computer process.

To facilitate an understanding of the various aspects of this disclosure the general architecture and operation of a PCI Express system will be described. The specific architecture and operation of the various aspects will then be described with reference to the general architecture of the host system and the adapter.

PCI Express links A and B comply with the PCI Express standard that defines a standard interface incorporating PCI transaction protocols developed to offer better performance than the PCI or PCI X bus standards. PCI Peripheral Component Interconnect is a commonly used local bus standard used for connecting peripherals. PCI X is another standard bus that is compatible with existing PCI cards using the PCI bus. It is noteworthy that the various embodiments disclosed herein are not limited to any particular industry standard or specification.

Downstream PCI Express device communicates with a storage system via link . Link may be any link for example a Fibre Channel link.

Upstream device may be a computing system may also be referred to as a host system and downstream PCI Express device may be an adapter may also be referred to as a host bus adapter HBA and or controller as described below. Although the examples below are based on host computing systems and adapters operating in a storage area network SAN the various adaptive aspects of the present invention as described in the appended claims are not limited to the SAN environment.

Host system may include one or more processors jointly referred to as processor also known as a central processing unit CPU interfacing with other components via a bus . Bus may be for example a system bus a Peripheral Component Interconnect PCI bus or PCI Express bus a HyperTransport or industry standard architecture ISA bus a SCSI bus a universal serial bus USB an Institute of Electrical and Electronics Engineers IEEE standard 1394 bus sometimes referred to as Firewire or any other kind of bus.

Host system may include or may have access to a mass storage device which may be for example a hard disk a CD ROM a non volatile memory device flash or memory stick or any other device. Storage may store processor executable instructions and data for example operating system program files application program files and other files.

Host system interfaces with memory that may include random access main memory RAM and or read only memory ROM . When executing stored computer executable process steps from storage the processor may store and execute the process steps out of memory . ROM may store invariant instruction sequences such as start up instruction sequences or basic input output operating system BIOS sequences for operation of a keyboard not shown .

The host system may also include other devices and interfaces which may include a display device interface a keyboard interface a pointing device interface and others.

Host system also interfaces with a peripheral interface via bus . The peripheral interface is coupled to a root complex . Root complex as defined by the PCI Express standard is an entity that includes a Host Bridge and one or more Root Ports. The Host Bridge connects a CPU to a Hierarchy where a Hierarchy is a tree structure based on a PCI Express topology. The Root complex connects to a standard PCI Express switch that couples to adapter via a bus or link which in this case may be a PCI Express bus.

Host processor may communicate with adapter via switch . It is noteworthy that the path between root complex and adapter can also be a direct path with no switch or can include multiple cascaded switches.

The root complex may include a host MPS Maximum Payload Size register or any other type of storage location. The host MPS register stores a host MPS value that indicates the MPS size used by host system to send information to adapter .

The host system is uniquely identified by using a host identifier host Id . The host Id can vary in formation for example host Id may be a unique host name a unique identification value a system serial number or any other format that can be used to uniquely identify host system . In one embodiment host Id may be coded and stored in a register not shown and is readable by processor . In another embodiment the host Id is stored in memory . In yet another embodiment the host Id can be programmed by programmable instructions for example by an operating system.

Adapter includes a processor a host interface a memory an adapter MPS register or storage location and a port . The host interface is configured to interface with the host system via bus . The structure and logic used by host interface is designed to handle the protocol used by bus . For example if bus is a PCI Express link then host interface is able to handle PCI Express protocol requirements when communicating with host system . The adapter MPS register port and memory are accessible to adapter processor .

Memory is used to store programmable instructions for example adapter firmware . Adapter processor executes firmware to control the overall functionality of adapter .

Memory may also include a storage location that may be referred to as an adapter MPS store to store an adapter MPS value . In one embodiment the adapter MPS value is set to be the same as the host MPS value stored in host MPS register .

Memory may also include another storage location that may be referred to as a host Id store that is used to store a host Id value . In one embodiment the host Id value is set so that it is the same as host Id stored at host system .

The adapter MPS register can be used to store the adapter MPS register value that is used by the adapter processor to determine the payload size used by adapter to transfer information. The use of adapter MPS value is described below in more detail with respect to the process flow diagrams.

Port is used to send information to and receive information from other devices via link . In an exemplary implementation adapter may be similar to a host bus adapter available from Qlogic Corporation. In some embodiments the adapter may interface with fibre channel devices via link . In another embodiment adapter may be a Fibre Channel over Ethernet FCOE adapter that can handle both network and storage traffic.

The adapter driver may be executed by the host processor and initiates communication with the adapter via bus . The communication received from the host system is decoded by the adapter processor or any other module and appropriate instructions are executed by the adapter processor or any other module affected by the instructions. The functionality of the various modules is described below with respect to the process flow diagrams shown in .

In block S processor executing BIOS Basic Input Output System instructions reads the host MPS value from host MPS register for example the host MPS value may be X1. The adapter default MPS value is also read and may be X2 i.e. the adapter default MPS value may be different from the host MPS value X1.

In block the adapter MPS value is set to host MPS value i.e. X1 at adapter MPS register . In block S operating system is loaded and host system starts functioning.

In block S adapter is disabled. Adapter may be disabled for various reasons for example adapter may be disabled when operating system instructs the host system to switch to a hibernation mode. During hibernation mode to save power and resources host system may disable adapter with other modules. In some embodiments adapter may simply be turned off.

In block adapter is enabled. The operating system may instruct host system to resume normal operations and enable adapter . In block adapter resets the adapter MPS value to its default value of X2. Because of the reset the host MPS value and the adapter MPS value become different again.

In block an error may occur during data transfer between the host system and adapter . The error may occur due to a mismatch in the host MPS value which is set to X1 and adapter MPS value which is set to X2. The adaptive embodiments disclosed herein reduce these errors by using the same MPS value for both the adapter and the host system as described below in more detail.

In block S driver is loaded and system information is read from a registry not shown . Driver may also issue commands to adapter to read and retrieve configuration information from one or more memory locations of adapter . For example driver may read host Id value and adapter MPS register value .

If there is no match then driver stores the host Id value as a new host Id value in adapter memory in block S.

In block S adapter also saves the host MPS value as adapter MPS value . The driver also stores the host MPS value at adapter MPS register as adapter MPS register value . The process then moves to block .

If in block S there is a match or after block S then in block S driver determines if the host MPS value and the adapter MPS register value are the same.

If they are not the same in block S driver restores the adapter MPS register value to the adapter MPS value which is the same as host MPS value . For example driver instructs the adapter to read the adapter MPS value and write it at the adapter MPS register . Because the adapter MPS value is the same as the host MPS value the adapter MPS register value is restored to the host MPS value .

If the values in block are the same or after block the driver continues to execute other steps in block S to complete driver installation and configuration.

In block S adapter driver determines if the host Id matches with the host Id that is stored at adapter memory . If the host Id does not match with host Id then the host Id value is replaced by the host Id value maintained by host system in block S. In addition the host MPS value is stored as adapter MPS value in adapter memory . The host MPS value is also stored as adapter MPS register value at register . Thereafter the process moves to block S.

In block S if the host Ids stored by the adapter and the host system match then adapter is used to transfer information until the process reaches block S when adapter is disabled. In one embodiment adapter may be disabled due to an event for example hibernation that is managed by operating system . During hibernation the host system powers down various modules including adapter . Thereafter in block S the adapter is enabled. In one embodiment adapter is enabled by an operating system event for example after hibernation.

In block S the adapter MPS register is reset as part of adapter initialization. In one embodiment adapter resets the adapter MPS register value to a default value for example X2.

In block S the adapter MPS register value is restored to the host MPS value stored at memory location . Thereafter in block S adapter begins data transfer. Because the host MPS value and the adapter MPS values are the same data transfer proceeds without any errors.

In one embodiment robust data transfer occurs between a host system and an adapter even if the adapter is disabled and then enabled by an external event for example an operating system initiated hibernation. In another embodiment an adapter with a first MPS value can be swapped with another adapter that may have a different MPS value. The system and method disclosed herein recognizes the change by detecting a mismatch in the host Id and then setting the proper MPS values that match with the host MPS value. These features may be beneficial for example in systems where hot swapping of adapters is commonly used.

Although the present disclosure has been described with reference to specific embodiments these embodiments are illustrative only and not limiting. Many other applications and embodiments of the present invention will be apparent in light of this disclosure and the following claims. References throughout this specification to one embodiment or an embodiment means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the present invention. Therefore it is emphasized and should be appreciated that two or more references to an embodiment or one embodiment or an alternative embodiment in various portions of this specification are not necessarily all referring to the same embodiment. Furthermore the particular features structures or characteristics being referred to may be combined as suitable in one or more embodiments of the invention as will be recognized by those of ordinary skill in the art.

