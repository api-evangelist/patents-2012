---

title: System for monitoring state information in a multiplex system
abstract: A multiplex system includes physical machines, and data communication cards respectively installed in the physical machines. If one of the physical machines equipped with an own data communication card is a physical machine of an own system and another one of the physical machines is a physical machine of another system, the data communication cards connect the physical machine of the own system and the physical machine of the other system communicably with each other over a communication network. Further, the data communication cards autonomously monitor the states of the physical machine of the own system and the physical machine of the other system and detect an abnormal state.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08990632&OS=08990632&RS=08990632
owner: NEC Corporation
number: 08990632
owner_city: Tokyo
owner_country: JP
publication_date: 20120911
---
This application is based upon and claims the benefit of priority from Japanese patent application No. 2011 210049 filed on Sep. 27 2011 the disclosure of which is incorporated herein in its entirety by reference.

The present invention relates to a multiplex system and in particular to a multiplex system implementing a fault tolerant system or a cluster system a data communication card and an abnormal state detection method.

In recent years computers have established the foundation of society and service outages due to a failure may cause a heavy loss. Accordingly it is required to continue services even if a failure occurs. As such a fault tolerant technology using a multiplex system has drawn attention.

For example a fault tolerant system at a hardware HW level has been known conventionally. In such a system a lock step operation is performed via dedicated hardware HW and the operation is continued by performing switching between multiplex usually duplex hardware main components without any delay when a failure occurs.

Further a fault tolerant system at a software SW level has been studied in recent years. In such a system if a failure occurs due to a fault or the like in the hardware HW on a physical machine where a virtual machine operates the processing performed by the virtual machine is continuously performed by a virtual machine standing by on another physical machine.

It should be noted that a virtual machine is a virtually implemented machine realized by operating a plurality of operating systems OS on a physical machine by the virtualization technology. With the virtualization technology a plurality of virtual machines of low utilization can be integrated on one physical machine whereby the utilization efficiency per physical machine can be improved and also power consumption can be suppressed by reducing the number of physical machines. The virtualization technology includes a model in which a layer allowing a virtual machine to operate is provided above the host OS running on the physical machine and a guest OS is allowed to run on such a layer and a model in which a hypervisor allowing a virtual machine to operate is provided on the hardware HW without a host OS and a guest OS is allowed to run on the hypervisor.

For example as first related art of the present invention a technique of implementing duplexing by combining virtual computers respectively operating on two independent computers has been proposed see JP 4468426 B Patent Document 1 for example . To be more specific an acquisition unit included in a first hypervisor managing a first virtual computer acquires synchronization information associated with an event accompanying an input to the first virtual computer. Further in accordance with the synchronization information a control unit included in a second hypervisor managing a second virtual computer performs control to match an execution state pertaining to an input to the second virtual computer with an execution state pertaining to an input to the first virtual computer. Thereby duplexing is implemented by combining the virtual computers respectively operating on the two independent computers.

Further as second related art of the present invention a service taking over control method in a virtual machine system has been proposed see JP 2009 080692 A Patent Document 2 for example . To be more specific when a failure occurs in a physical computer in which a virtual machine is operating a virtual machine monitor regenerates the virtual machine in which the failure has occurred as another virtual machine on another physical computer based on a snap shot taken by a disk device at a point of time closest to the failure occurrence time. Further based on the communication history associated with the virtual machine in which the failure has occurred a state reproduction section of a communication recording unit makes the regenerated virtual machine to reproduce the state of the virtual machine during the period from the time when the snap shot was taken to the failure occurrence time. Further if reproduction of the state of the virtual machine fails a restart section restarts the virtual machine on the server computer. Thereby when a failure occurs in the physical computer on which the virtual machine is operating the service is taken over by the virtual machine regenerated or restarted on another physical computer.

Further as third related art of the present invention a method of transferring a computer operation environment has been proposed see JP 2008 033483 A Patent Document 3 for example . To be more specific first an operation of a first computer is suspended. Next a list of files included in a copy image on a first disk is created. Then execution context of the first computer is copied to the second computer. Then the operation is restarted in the second computer. Then with reference to the list the copy image is copied from the first disk to the second disk. Thereby the service suspended time when transferring the operation environment of the first computer using the first disk to the second computer using the second disk is reduced.

Further in a multiplex system implementing the above described fault tolerant system or the cluster system detection of a failure of a physical machine is realized by a function of server vital checking by heartbeat of cluster software operation management software or the like see paragraph 0038 of Patent Document 2 for example . Further as an error detection mechanism of general purpose hardware HW a mechanism of detecting a memory failure using error checking and correcting codes has been known.

However a method of monitoring the state of a physical machine by software running on the physical machine constituting a multiplex system and detecting an abnormal state such as server vital checking by heartbeat and a method of detecting a failure by an error detection mechanism of hardware implemented on a physical machine such as error checking and correcting codes are directly affected by the state of the physical machine. As such those methods may fail to detect an abnormal state. For example if a hardware failure occurs in a physical machine which causes a stop of the software monitoring the state of the physical machine it is difficult to detect an abnormal state. Further in a device not operating usually such as a device of a standby system subsystem in a multiplex system as an error detection mechanism of hardware implemented therein has no opportunity to function practically it is difficult to detect a failure.

An exemplary object of the present invention is to provide a multiplex system capable of solving the above described problem that is a problem that a method of monitoring the state of a physical machine using software running on the physical machine or using an error detection mechanism implemented on the physical machine and detecting an abnormal state is likely to be affected by the state of the physical machine so that such a method may fail to detect an abnormal state.

a plurality of data communication cards respectively installed in the plurality of the physical machines wherein

if one of the physical machines equipped with an own data communication card is a physical machine of an own system and another one of the physical machines is a physical machine of another system the data communication cards connect the physical machine of the own system and the physical machine of the other system communicably with each other over a communication network and autonomously monitor the states of the physical machine of the own system and the physical machine of the other system and detect an abnormal state.

Further a data communication card according to another aspect of the present invention is a data communication card installed in each of physical machines including if one of the physical machines equipped with an own data communication card is a physical machine of an own system and another one of the physical machines is a physical machine of another system a unit that connects the physical machine of the own system and the physical machine of the other system communicably with each other over a communication network and autonomously monitors the states of the physical machine of the own system and the physical machine of the other system and detects an abnormal state.

Further an abnormal state detection method according to another aspect of the present invention is a method of detecting an abnormal state of a multiplex system including a plurality of physical machines including

by a plurality of data communication cards respectively installed in the plurality of the physical machines if one of the physical machines equipped with an own data communication card is a physical machine of an own system and another one of the physical machines is a physical machine of another system connecting the physical machine of the own system and the physical machine of the other system communicably with each other over a communication network and autonomously monitoring the states of the physical machine of the own system and the physical machine of the other system and detecting an abnormal state.

As the present invention is configured as described above the present invention is able to monitor the states of physical machines and detect an abnormal state irrespective of the states of the physical machines.

Hereinafter an exemplary embodiment of the present invention will be described with reference to the accompanying drawings.

As shown in a multiplex system according to the present embodiment includes a plurality of physical machines i 1 n n represents the number of machines .

In this embodiment examples of the respective physical machines i 1 n include computers such as PCs personal computers appliances thin client servers workstations mainframes and super computers. It should be noted that the physical machines i 1 n may be relay devices rather than terminals or servers. Examples of the relay devices include network switches routers proxies gateways firewalls load balancers packet shapers SCADA Supervisory Control And Data Acquisition gatekeepers base stations access points AP and computers having communication ports.

Although not shown the above mentioned computers relay devices and the like are implemented by processors which are driven based on programs and perform predetermined processing memories storing such programs and various kinds of data and interfaces.

Examples of the above mentioned processors include CPU Central Processing Unit network processors NP microprocessors microcontrollers and semiconductor integrated circuits IC having dedicated functions.

Examples of the above mentioned memories include semiconductor memory units such as RAM Random Access Memory ROM Read Only Memory EEPROM Electrically Erasable and Programmable Read Only Memory and flash memories. Other examples of the above mentioned memories include auxiliary storage units such as HDD Hard Disk Drive and SSD Solid State Drive removable disks such as DVD Digital Versatile Disk and storage media such as SD Secure Digital memory cards. Further the above mentioned memories may be buffers or registers. Further the above mentioned memories may be storage devices using DAS Direct Attached Storage FC SAN Fibre Channel Storage Area Network NAS Network Attached Storage IP SAN IP Storage Area Network and the like.

It should be noted that the processor and the memory may be integrally formed. For example a one chip microcomputer is increasingly used in recent years. As such there is a case where a one chip microcomputer installed in an electronic device is equipped with the processor and the memory.

Examples of the above mentioned network interfaces include semiconductor integrated circuits such as circuit boards mother boards I O boards and chips compatible with network communications network adapters such as NIC Network Interface Card and similar expansion cards communication devices such as antennas and communication ports.

Further examples of the networks include the Internet LAN Local Area Network wireless LAN WAN Wide Area Network backbones Cable Television CATV networks fixed line telephone networks mobile telephone networks WiMAX IEEE 802.16a 3G 3Generation lease lines IrDA Infrared Data Association Bluetooth registered trademark serial communication networks and data buses.

In the present embodiment each physical machine i 1 n is equipped with a data communication card which may be inserted built in embedded connected or the like. However the method of installing the card is not limited to these examples in practice.

The data communication card is a highly functional extension card which can be installed in the physical machine i 1 n . The data communication card may have a function of a network interface as described above. The data communication card incorporates an LSI Large Scale Integration . The data communication card connects to another data communication card over a communication network to transmit and receive data with each other. Further the data communication card has a fault detection function and autonomously detects a fault in the physical machine in which the card is installed or a fault in another physical machine in which the other data communication card is installed. Autonomously detecting a fault in a physical machine means detecting a fault in the physical machine by the hardware of the data communication card without depending on the software of the physical machine. A fault in the other physical machine may be recognized by a notification from the other data communication card.

It should be noted that the form of the data communication card is not limited to a card form. For example the data communication card may be integrated with the circuit board of the physical machine i 1 n . However it is not limited to these examples in practice.

If an environment in which the data communication card can be used has been set on the physical machine i 1 n and capable software has been introduced or can be introduced the physical machine i 1 n may serve as an FT Fault Tolerant server or a cluster server by only inserting the data communication card into the physical machine i 1 n . In the case of implementing a fault tolerant system or a cluster system at a software level the data communication card may have setting information image files and the like for a virtual machine and provide the physical machine i 1 n with them. In that case the data communication card may be called as an FT card or a cluster card .

With reference to the internal configuration of each physical machine i 1 n will be described in detail.

Each physical machine i 1 n includes the data communication card hardware HW software SW a driver an I O Input Output chip and a BMC Baseboard Management Controller . It should be noted that the power of the physical machine has two systems including main power and standby power. During the time that the AC power code of the physical machine is connected with an AC outlet the standby power is ON. In the state where the standby power is ON the main power can be switched from OFF to ON or vice versa. Both the main power and the standby power are DC power.

In the present embodiment an example will be given using two physical machines physical machine and physical machine . For example the physical machine includes a data communication card hardware HW software SW a driver a BMC and an I O chip . Further the physical machine includes a data communication card hardware HW software SW a driver a BMC and an I O chip .

The hardware HW is hardware HW inside the physical machine i 1 n . In general the hardware HW is driven by the power supplied from the DC power. As an example the hardware HW may be a processor a memory an auxiliary storage unit a network interface a PCI Peripheral Components Interconnect bus slot or a power supply unit or a combination thereof. It should be noted that the hardware HW may be multiplexed in the same physical machine.

The software SW is software which operates on the physical machine i 1 n using the hardware HW . As an example the software SW may be an OS application software or middleware. It should be noted that the software SW may be a virtual machine VM constructed on the physical machine.

The driver is a software SW device driver for controlling and operating devices installed in the physical machine i 1 n and equipment connected externally. The driver serves as an intermediary for the OS to control the equipment as described above. The driver may be built in the OS and act as a part of the function of the OS. As such the driver may be a part of the software SW . The driver works such that when the software SW uses an external device connected with the I O chip the driver is in charge of the correspondence between the abstracted API and the device by allowing the software SW to utilize the function of the device by means of the shared API Application Programming Interface provided by the OS.

The I O chip is a connection port physical port provided to the physical machine i 1 n connecting to the main unit of the physical machine and to various kinds of peripheral equipment and serving as an input output interface for exchanging data with such equipment. As main standards of input output interfaces PS 2 for connecting a keyboard and a mouse RS232C of a serial interface for bidirectional communications with a modem and a printer SCSI of a parallel interface for bidirectional connections with a hard disk drive HDD or the like IDE of a parallel interface for bidirectional connections mainly with a built in HDD or the like USB of a serial interface for bidirectional connections between the main unit and the peripheral equipment and IEEE1394 which is a next generation high speed SCSI standard have been known. It should be noted that the I O chip may be a super I O Input Output chip or an ICH I O Controller Hub .

The BMC is a controller provided inside the physical machine i 1 n . The BMC regularly monitors the state of the hardware HW and notifies the OS and the like of an occurrence of a hardware HW error. Specifically the BMC regularly monitors the supply voltage from the power supply unit the number of rotation of the cooling fan the temperatures of various kinds of components including processors the power supply voltage of the SCSI terminator and the like. The BMC is driven by power supplied from the standby power. Accordingly even if the main power of the main unit is OFF if the power supply code from an outlet is connected with the power supply unit power is supplied to the BMC . As such even if the main power of the main unit is OFF the BMC continues monitoring of the state of the hardware HW .

Some exemplary system configurations for implementing the data communication card on a physical machine will be shown below.

Referring to a system configuration 1 in which the data communication card is provided independent of the circuit board of the physical machine i 1 n will be described.

In this example the data communication card is an extension card inserted in a card slot of the physical machine i 1 n . It should be noted that the form of the data communication card is not limited to a card form.

The data communication card connects to the I O chip via a processor CPU or the like which is one of the hardware HW components.

For example the data communication card connects to a processor CPU or the like which is one of the hardware HW components inside the physical machine i 1 n via the PCI Express bus. This processor CPU or the like connects to the I O chip via the PCI Express bus.

Referring to a system configuration 2 in which the data communication card is integrated with the circuit board of the physical machine i 1 n will be described.

In this example the data communication card is a chip mounted on the circuit board of the physical machine i 1 n . In this case the circuit board of the physical machine i 1 n has a function as the data communication card . As such the circuit board of the physical machine i 1 n corresponds to the data communication card .

The data communication card is present between a processor CPU or the like which is one of the hardware HW components and the I O chip and monitors communications between the processor CPU or the like and the I O chip .

For example a processor CPU or the like which is one of the hardware HW components inside the physical machine i 1 n connects to the data communication card via the PCI Express bus. The data communication card connects to the PO chip via the PCI Express bus.

Here description will be given using an FPGA Field Programmable Gate Array and a CPLD Complex Programmable Logic Device as examples of LSIs installed in the data communication card . It should be noted that the FPGA and the CPLD are just examples and other LSIs may be used in practice.

For example the data communication card includes an FPGA and a CPLD . The data communication card includes an FPGA and a CPLD .

The FPGA is a first LSI. The FPGA monitors the states of the hardware HW the software SW and the I O chip . To the FPGA the main power DC power received by the data communication card is supplied.

The CPLD is a second LSI. The CPLD monitors the states of the BMC and the power supply unit. To the CPLD the standby power DC power generated from the AC power received by the data communication card is supplied. It should be noted that the standby power is an output for supplying a regular constant output for performing power supply management. The circuit for outputting the standby power operates even if the main power is turned off.

The FPGA includes a processor a SW state acquisition unit a PCI controller and a communication controller .

The processor performs control of the respective units inside the data communication card and calculation and processing arithmetic processing of data. For example the processor is driven based on the program stored in the RAM or the like inside the data communication card and performs predetermined processing. The processor is not a processor such as a CPU included in the hardware HW inside the physical machine i 1 n but a processor disposed on the FPGA inside the data communication card . Further the processor is able to change the operation of the SW state acquisition unit the PCI controller and the communication controller .

The SW state acquisition unit acquires the state of the software SW . The SW state acquisition unit may acquire the state of the software SW by directly receiving a notification from the driver or acquire the state of the software SW set on the memory by the driver via the PCI controller .

The PCI controller connects to the hardware HW and the I O chip inside the physical machine i 1 n via the PCI Express bus and monitors the states of the hardware HW and the I O chip .

The communication controller connects to the FPGA and the CPLD . Accordingly the communication controller is able to notify the CPLD of an error detection result abnormal state detection result by the FPGA . Further the communication controller establishes a remote connection with an FPGA installed in another data communication card via at least one cable. In this example it is assumed that they are connected via two cables. If a plurality of cables are used it is possible to bundle them into one physically logically. By bundling a plurality of cables into one the communication speed can be doubled according to the bundled number of cables. Further by bundling a plurality of cables into one even if any of the cables fails communications can be continued using the remaining cables. The communication controller notifies the other data communication card of the error detection result by the FPGA via the two cables.

The CPLD includes a power supply monitoring unit a power supply controller an SMBus System Management Bus controller and a communication controller .

The power supply monitoring unit monitors the power supply states of the physical machine of the local machine local system and the remotely connected physical machine remote system . The power supply monitoring unit may directly monitor the power supply state of the local physical machine or acquire a monitoring result by the BMC via the SMBus controller . It should be noted that the power supply monitoring unit may monitor the power supply state of the local physical machine regarding whether or not the main power is ON whether or not the main power is OFF whether or not the main power is switched from ON to OFF or switched from OFF to ON and the like. Further the power supply monitoring unit may directly monitor the power supply state of the remote physical machine via the communication controller or acquire a monitoring result by the BMC of the remote physical machine via the SMBus controller of the remote physical machine.

The power supply controller controls the power supply states of the local physical machine and the remote physical machine. The power supply controller may directly control the power supply state of the local physical machine or control it via the SMBus controller and the BMC . Further the power supply controller may directly control the power supply state of the remote physical machine via the communication controller or control it via the SMBus controller and the BMC of the remote physical machine.

The SMBus controller connects to the BMC inside the physical machine i 1 n via the SMBus and acquires a monitoring result from the BMC . Further the SMBus controller is also able to instruct the BMC to control.

The communication controller connects to the FPGA and the CPLD . Accordingly the communication controller is able to notify the FPGA of an error detection result abnormality detection result by the CPLD . It should be noted that the communication controller of the FPGA and the communication controller of the CPLD may be the same device circuit. Further the communication controller establishes a remote connection with a CPLD installed in another data communication card via at least one cable. In this example it is assumed that they are connected via one cable. If a plurality of cables are used the cables may be bundled into one physically logically. The communication controller notifies the other data communication card of an error detection result by the CPLD via the one cable. Further the communication controller may receive power supply from the remote physical machine via the one cable. For example the communication controller uses a part of the line constituting the one cable for receiving power supply from the remote physical machine. In that case even if the CPLD is not able to receive power supply from the local physical machine the CPLD is able to continue operation by receiving power supply from the remote physical machine.

Here as an example of hardware HW state monitoring an operation of memory state monitoring will be described. It should be noted that memory state monitoring is performed only when the main power is ON both the main power and the standby power are ON .

The PCI controller monitors whether the memory operates normally by issuing a memory read request via the PCI Express bus reading data in the memory via the CPU or the like and checking whether a completion response is returned normally from the CPU or the like.

For example the PCI controller sequentially issues a read request to each of the memory addresses periodically at regular intervals.

It should be noted that the operation of the PCI controller may be changed by the processor . For example the cycle that the PCI controller issues the read request may be changed by the processor .

Conventionally it has been required to actually read the memory. As such it is impossible to detect an error until a memory read request is issued from the CPU or the like.

In the present embodiment however as the data communication card autonomously issues a memory read request periodically irrespective of presence or absence of memory readout to thereby constantly monitor the state of the memory an error can be detected at an early stage. Further it is also possible to detect an error in devices which do not operate usually such as devices of a standby system subsystem in the multiplex system.

The SW state acquisition unit acquires the state of the software SW to thereby monitor whether the software SW operates normally. As a state of the software SW a count value if the software regularly counts the value of a particular memory address for example may be used. However the state is not limited to such a value.

The SW state acquisition unit may acquire the state of the software SW by directly receiving a notification from the driver or acquire the state of the software SW set on the memory by the driver via the PCI controller .

In general it is difficult to detect an abnormality in software SW using the software SW monitoring a failure.

In the present embodiment however as the data communication card monitors the state of the software SW it is possible to detect an error in the software SW monitoring a failure.

It should be noted that I O chip state monitoring is performed only when the main power is ON both the main power and the standby power are ON .

The PCI controller monitors whether the I O chip operates normally by issuing a read request of setting information config of the I O chip via the PCI Express bus reading the setting information of the I O chip directly or via the CPU or the like and checking whether a completion response is returned normally from the I O chip or the CPU or the like.

For example the PCI controller sequentially issues a read request to each of the I O chips periodically at regular intervals.

It should be noted that the operation of the PCI controller may be changed by the processor . For example the cycle that the PCI controller issues the read request may be changed by the processor .

Conventionally it has been required to actually read the I O chip . As such it is impossible to detect an error until a read request of the I O chip is issued from the CPU or the like.

In the present embodiment however as the data communication card autonomously issues a read request of the I O chip periodically irrespective of presence or absence of readout of the I O chip to constantly monitor the state of the I O chip an error can be detected at an early stage.

Further it is also possible to detect an error in devices which do not operate usually such as devices of a standby system subsystem in the multiplex system.

It should be noted that BMC state monitoring is performed in either that the main power is ON both the main power and the standby power are ON or that the main power is OFF the main power is OFF and only the standby power is ON .

The SMBus controller monitors whether the BMC operates normally by issuing an SMBus read request to the BMC via the SMBus reading the value of a register provided to the BMC and checking whether a completion response is returned normally from the BMC .

For example the SMBus controller autonomously issues an SMBus read request to the BMC periodically at regular intervals.

The BMC is able to issue an SMBus write request to the SMBus controller and write data into a register in the data communication card . The SMBus controller may monitor whether the BMC operates normally by checking whether an SMBus write request is issued from the BMC at regular intervals.

It should be noted that if the main power is ON the processor is able to change the operation of the SMBus controller . For example the processor is able to change the cycle that the SMBus controller issues the SMBus read request. Further the processor is able to control which monitoring method that is a method of monitoring by issuing an SMBus read request or a method of monitoring by checking an issuance of an SMBus write request is to be used.

In the present embodiment as the data communication card issues an SMBus read request periodically to constantly monitor the state of the BMC an error can be detected at an early stage.

It should be noted that power supply state monitoring of the local machine is performed in either that the main power is ON both the main power and the standby power are ON or that the main power is OFF the main power is OFF and only the standby power is ON .

The power supply monitoring unit monitors the power supply state of the local physical machine. The power supply monitoring unit is driven by the power supplied from the standby power.

The power supply monitoring unit detects that the main power of the local physical machine is ON. The power supply monitoring unit also detects that the main power of the remote physical machine is ON via the communication controller .

If the power supply controller detects that the main power of the remote physical machine is OFF the power supply controller turns on the main power of the remote physical machine via the communication controller .

It should be noted that when detecting that the main power of the local physical machine is ON the power supply controller is able to turn on the main power of the remote physical machine via the communication controller . Whether or not to turn on the main power of the remote physical machine can be changed by the setting. This is effective when both the local physical machine and the remote physical machine are activated simultaneously.

For example in the case of operating a fault tolerant system at a software SW level the DC power of the two physical machines active system and standby system must be ON. As such when the power switch of one machine is turned on there is an advantage merit if the DC power of the other machine is also turned on in conjunction with the one machine. On the contrary when the one machine is shut down so that the DC power thereof is turned off there is an advantage if the DC power of the other machine is also turned off in conjunction with the one machine. Whether or not the two physical machines are in conjunction with each other is not fixed but selectable.

Further when the power supply controller detects that the main power of the local physical machine is ON the power supply controller is also able to turn off the main power of the remote physical machine. Whether or not to turn off the main power of the remote physical machine can be changed by the setting. This is effective when the active system main system and the standby system subsystem are switched between the local physical machine and the remote physical machine.

The power supply monitoring unit detects that the main power of the local physical machine is OFF. Further the power supply monitoring unit detects that the main power of the remote physical machine is OFF via the communication controller .

When the power supply controller detects that the main power of the remote physical machine is ON the power supply controller turns off the main power of the remote physical machine via the communication controller .

It should be noted that when detecting that the main power of the local physical machine is OFF the power supply controller is able to turn off the main power of the remote physical machine via the communication controller . Whether or not to turn off the main power of the remote physical machine can be changed by the setting. This is effective when both the local physical machine and the remote physical machine are shut down simultaneously.

Further when the power supply controller detects that the main power of the local physical machine is OFF the power supply controller is also able to turn on the main power of the remote physical machine. Whether or not to turn on the main power of the remote physical machine can be changed by the setting. This is effective when the active system main system and the standby system subsystem are switched between the local physical machine and the remote physical machine.

In general it is difficult to detect a power failure of a physical machine by software SW . The reason that it is difficult to detect a failure of the main power of the local physical machine by the software SW of the local physical machine is that if the main power of the local physical machine failed it is highly likely that the software SW of the local physical machine stops.

In the present embodiment however as the data communication card monitors the power supply states of the local physical machine and the remote physical machine by the power supplied from the standby power it is possible to detect a failure of the main power in the respective physical machines and to determine and specify in which physical machine the failure of the main power has occurred.

Hereinafter an operation of power supply state monitoring of the remote machine will be described in detail.

It should be noted that power supply state monitoring of the remote machine is performed in either that the main power is ON both the main power and the standby power are ON or that the main power is OFF the main power is OFF and only the standby power is ON .

The power supply monitoring unit monitors the power supply state of the remote physical machine. It should be noted that the power supply monitoring unit is driven by the power supplied from the standby power.

The power supply monitoring unit detects that the main power of the remote physical machine is ON via the communication controller . The power supply monitoring unit also detects that the main power of the local physical machine is ON.

If the power supply controller detects that the main power of the local physical machine is OFF the power supply controller turns on the main power of the local physical machine.

It should be noted that when detecting that the main power of the remote physical machine is ON the power supply controller is able to turn on the main power of the local physical machine via the communication controller . Whether or not to turn on the main power of the local physical machine can be changed by the setting. This is effective when both the local physical machine and the remote physical machine are activated simultaneously.

Further when the power supply controller detects that the main power of the remote physical machine is ON the power supply controller is also able to turn off the main power of the local physical machine. Whether or not to turn off the main power of the local physical machine can be changed by the setting. This is effective when the active system main system and the standby system subsystem are switched between the local physical machine and the remote physical machine.

The power supply monitoring unit detects that the main power of the remote physical machine is OFF via the communication controller . Further the power supply monitoring unit detects that the main power of the local physical machine is OFF.

When the power supply controller detects that the main power of the local physical machine is ON the power supply controller turns off the main power of the local physical machine.

It should be noted that when detecting that the main power of the remote physical machine is OFF the power supply controller is able to turn off the main power of the local physical machine via the communication controller . Whether or not to turn off the main power of the local physical machine can be changed by the setting. This is effective when both the local physical machine and the remote physical machine are shut down simultaneously.

Further when the power supply controller detects that the main power of the remote physical machine is OFF the power supply controller is also able to turn on the main power of the local physical machine. Whether or not to turn on the main power of the local physical machine can be changed by the setting. This is effective when the active system main system and the standby system subsystem are switched between the local physical machine and the remote physical machine.

In general it is difficult to detect a power failure of a physical machine by software SW . The reason that it is difficult to detect a failure of the main power of the local physical machine by the software SW of the local physical machine is that if the main power of the local physical machine failed it is highly likely that the software SW of the local physical machine stops.

The reason that it is difficult to detect a failure of the main power of the remote physical machine by the software SW of the local physical machine is that it is difficult to determine whether the main power of the remote physical machine failed or communications of the software SW of the remote physical machine stopped.

In the present embodiment however as the data communication card monitors the power supply states of the local physical machine and the remote physical machine by the power supplied from the standby power it is possible to detect an error at an early stage.

Hereinafter an operation of turning off the main power by autonomous control will be described in detail.

When the data communication card detects any failure as a result of any state monitoring result of hardware state monitoring software state monitoring I O chip state monitoring or BMC state monitoring described above the data communication card autonomously turns off the main power of the device in which the failure has occurred without an interference of the software SW . In this step the data communication card may turn off the main power of the local physical machine or the remote physical machine.

For example when the power supply controller detects a failure of the local physical machine by the data communication card of the local system the power supply controller turns off the main power of the local physical machine.

Further when the power supply controller detects a failure of the remote physical machine by the data communication card of the local system the power supply controller turns off the main power of the remote physical machine via the communication controller .

In the present embodiment as the data communication card autonomously performs control to turn off the main power it is possible to turn off the main power of the physical machine after the error has been detected without an interference of software SW .

Hereinafter an operation of turning on the main power by autonomous control will be described in detail.

When the data communication card detects a failure of the remote physical machine if the main power of the local physical machine is OFF the data communication card turns on the main power of the local physical machine.

The data communication card detects a failure of the remote physical machine via the communication controller .

When a failure occurs in the remote physical machine the power supply controller turns on the main power of the local physical machine.

In the present embodiment as the data communication card autonomously detects a failure of the remote physical machine it is possible to turn on the main power of the local physical machine after an error in the remote physical machine has been detected without an interference of software SW .

Thereby in a duplex system including an active system and a standby system the main power of the standby system subsystem devices can stand by in an OFF state until the main power is required to be turned on. Accordingly the standby system subsystem devices are not required to stand by in a state where the main power is ON whereby the power consumption of the entire system can be reduced significantly.

As described above the present embodiment realizes early failure detection failover and cold standby by adding a function of monitoring the states of the devices a function of notifying the devices of the remote system of the states and a function of controlling power supply which are operable by the standby power to a data communication card to be used for constructing a fault tolerant system or a cluster system at a software level in a general purpose IA server.

By inserting a data communication card having the above described functions into a general purpose IA server the data communication card autonomously and regularly checks whether the main components of the IA server operate normally which enables early failure detection. Further the data communication card is able to notify the devices of the remote system of the detected failure and allow the devices of the remote system to immediately transfer to failover processing.

Further in the case where a multiplex system of an active standby configuration using the data communication card the standby side devices can monitor the states of the devices of another system even if the main power is OFF and when detecting a failure of the devices of the other system the standby side devices can turn on the main power autonomously.

As described above the data communication card implements early failure detection and failover and also implements autonomous cold standby without an interference of a third party.

In a conventional multiplex system in which failure detection has performed using a general purpose device the failure detection capability of a general purpose device is low. For example as it is able to detect a failure only when the failure detection function is operated in a case where the device or the failure detection function does not run in the standby system or the like a failure cannot be detected. Further as it is impossible to notify the outside devices of a failure without an interference of the OS for multiplexing the OS of each of the multiplex devices must be active. Further the failure detection function of the OS for multiplexing does not work either until the OS for multiplexing starts operation. In general as failure detection by software SW is performed by detecting a failure according to time out it takes time until a failure is detected. The present embodiment is able to solve these problems.

While the embodiment of the present invention has been described in detail the present invention is not limited to the above described embodiment. It will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the scope of the present invention.

