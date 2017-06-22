---

title: Handling of data transfer in a LAN-free environment
abstract: There is disclosed a method, system and computer readable medium for transferring data in a LAN-free environment, in particular for a tape backup or restore operation. Data of a client partition of a first server is sent to a partition of a LAN-free server through the Local Area Network (LAN). The data sent is then converted from TCP/IP protocol to Fiber Channel protocol. The converted data is sent to a Storage Area Network (SAN) through a Fiber Channel card and finally to a tape library. An advantage is thus to mutualize and virtualize resources, in particular Fiber Channel cards. Storage Area Network tape drives are shared using such host bus adapter cards. Certain embodiments avoid the reconfiguration of Storage Area Network tape drives when the client partition moves to a new hardware.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09122640&OS=09122640&RS=09122640
owner: INTERNATIONAL BUSINESS MACHINES CORPORATION
number: 09122640
owner_city: Armonk
owner_country: US
publication_date: 20120524
---
This application is a continuation of U.S. patent application Ser. No. 12 969 329 filed Dec. 15 2010 which application is incorporated herein by reference in its entirety.

U.S. patent application Ser. No. 12 969 329 is a non provisional application that claims priority benefits under Title 35 United States Code Section 119 a d from European EP Patent Application entitled METHOD AND SYSTEM FOR HANDLING DATA TRANSFER IN A LAN FREE ENVIRONMENT by Alain Lentini and Jarl Theuwissen having Patent Application No. EP09306262.8 filed on Dec. 18 2009 which EP Patent Application is incorporated herein by reference in its entirety.

The disclosure relates to data processing and more particularly to the handling of data transfer in a LAN free environment.

Backup and restore operations pose various issues. In particular backup on storage tape drives pose specific issues. For example a same number of backup cards and of partitions may be required. Some existing approaches to solve these issues use particular communications systems between servers of the architecture other approaches mutualize resources and still other approaches leverage virtualization mechanisms.

US Patent application 20080091896 entitled Storage system and data management method for example discloses a storage system and a data management method which can reduce the load on a virtualization apparatus by executing backup processing or restoration processing within one apparatus in which an externally connected storage apparatus and a tape library apparatus are installed. The storage system includes a virtualization apparatus and an external storage apparatus wherein the virtualization apparatus comprises an actual volume for storing data sent from a host apparatus formed in a storage area provided by a physical disk. The virtualization apparatus further comprises a virtual volume paired with the actual volume for storing replicated data for the data. The external storage apparatus comprises a logical volume that functions as an actual storage area for the virtual volume and a tape associated with the logical volume for storing the replicated data wherein the external storage apparatus has a copy unit for copying the replicated data stored in the logical volume to the tape. Whereas this approach leverages a virtualization mechanism it still presents drawbacks.

During backup and restore operations the use of the Local Area Network LAN may also be highly solicited leading to a negative impact on the network traffic for existing and active users. For this reason LAN free backups are increasingly operated. A LAN free backup is a backup of the data of a server to a shared central storage device without sending the data over the local area network LAN .

There is a need for a system and method of efficiently managing backup or restore operations and in particular efficient handling of data transfer in a LAN free environment.

In order to address these and other problems embodiments for handling LAN free data transfer are provided.

Certain embodiments relate to the usage of tape drives by virtual environments and more particularly to the efficient connection of a tape drive from a storage area network to a logical partition by using a Virtual LAN provided by a virtual environment.

Certain embodiments provide for the sharing Storage Area Network tape drives using host bus adapter cards with several logical partitions.

Certain embodiments avoid the reconfiguration of Storage Area Network tape drives in the Operating System when the logical partition moves to a new hardware.

An advantage of certain embodiments relate to the sharing of Fibre Channel FC technology in the context of LAN free backup.

Further advantages of certain embodiments will become clear to the skilled person upon examination of the drawings and detailed description. It is intended that any additional advantages be incorporated therein.

To facilitate description any numeral identifying an element in one figure will represent the same element in any other figure.

The following text presents embodiments in the context of LAN free backup or restore but it is to be understood that it is not limited to this specific backup or restore context. In particular the figures and the description discuss a preferred embodiment with the use of IBM pSeries servers. Further embodiments of the invention are not restricted to these proprietary environments or products which are provided for exemplary purposes only.

A LAN free backup is a backup of data from a server to a shared and central storage device. The goal of a LAN free backup is to reduce the load on LAN and reduce the time required to complete the backup.

Therefore such a LAN free backup process often uses a Storage Area Network SAN . This type of backup offers an alternative way to backup data this is no more a simple data copy to network attached storage NAS over LAN. There may exist a central backup server arbitrating access to devices for all the other SAN servers which does not however handle data stream itself. Without such a backup server the storage facility usually a virtual tape library or VTL is adapted to handle multiple data accesses without intermediate components.

Fibre Channel FC is a gigabit speed network technology primarily used for storage networking. FC ensures the connection between a computing device and the associated storage device. Fibre Channel is standardized the ANSI working group X3T11 defines the Fibre Channel specifications. It has become the standard connection type for Storage Area Networks SAN in enterprise storage. Fibre Channel signaling can run on both twisted pair copper wire and fibre optic cables. The Fibre Channel Protocol FCP is a transport protocol which predominantly transports SCSI commands over Fibre Channel networks.

In a typical design of a virtualized architecture the physical server IBM pSeries for example hosts several partitions with operating systems used for production applications. These operating systems share the same physical resources owned by a specific partition. In this specific partition is named VIO server . In this architecture the shared resources are used for LAN and SAN data communication. Virtualized structures to the interface between client partitions and the physical interfaces hosted by the VIO partition are required.

Certain embodiments of the invention provide a similar virtualization but specifically for SAN tape sharing between client partitions . The virtualization consists in sharing fibre channel hardware cards connected to the SAN which is connected to the tape library. The advantage is thus to use few fibre channel hardware cards and share them instead of installing one or more fibre channel hardware cards on each client partition.

In operation in a first step data is transferred from the client partition to the LAN free server partition that owns the fibre channel cards and shares them with all client partitions. In certain embodiments this step is operated using a virtual Ethernet LAN provided by the IBM pSeries server for example. A virtual LAN commonly known as a vLAN has the same attributes as a physical LAN but defines a logical grouping of networking devices. Network reconfiguration can be operated through software instead of physically relocating devices . Alternatively to a vLAN it may be a physical LAN but according to an embodiment there is a sharing of hardware material instead of assignments of such material to particular tasks.

A second step is the conversion of data coming from virtual LAN to send it to the SAN fibre channel cards to go then to the tape library . This conversion is done by a tool currently named API LAN SAN . In IBM environments this API is named LAN free storage agent . The API LAN SAN enables the conversion from TCP in the TCP IP stack into the FC protocol acting as a gateway . When data are received by the tape library they are written on a set of tapes managed by the tape library. This mechanism can be initiated by a backup of the data owned by one of the client partitions or by a restore of the data of one of client partitions . In case of a data backup pieces of data come from the client partition toward the tape library and in case of a data restore pieces of data come from the tape library toward one of the client partitions .

A backup or a restore of the client data is initiated and managed by one of the backup server . To manage this backup or restore operation the backup server communicates with the client partition. It uses therefore a physical LAN network . As the LAN hardware cards are virtualized on the IBM pSeries server models they are hosted by the VIO partition which shares them between available client partitions via a virtual LAN provided by the IBM pSeries server . A virtual structure the virtual Ethernet server adapter is used to generate the interface between physical and virtual LAN. During backup or restore operations the backup server exchanges backup protocol information with the client partition.

In case of live partition mobility LPM any client partition can move online from its IBM pSeries 240 to the other IBM pSeries 250 dynamically. Certain embodiments include operations to perform the following 

At step the client exchanges Protocol Information with backup server via virtual Ethernet client adapter .

At step the virtual Ethernet client adapter transmits or receives Protocol Information through the virtual LAN .

At step the VIO server transmits receives Protocol Information to from virtual Ethernet server adapter .

At step the virtual Ethernet server adapter transmits receives Protocol Information to from Ethernet adapter of the backup server .

At step the Physical Ethernet adapter of the backup server transmits receives Protocol Information to backup server .

The LAN free client sends the data of the backup through the dedicated VLAN to the IP address dedicated to the LAN free servers . The LAN free servers are hosted on different physical servers in the figure as physical server A and physical server B .

LAN free servers are attached by Storage Area Network SAN to the Tape library. The LAN free clients LAN free servers and backup server are connected to a Local Area Network LAN providing the control and protocol information.

Alterations and modifications may be made to the above without departing from the scope of the invention. Naturally in order to satisfy local and specific requirements a person skilled in the art may apply to the solution described above many modifications and alterations. Particularly although the present invention has been described with a certain degree of particularity with reference to preferred embodiment s thereof it should be understood that various omissions substitutions and changes in the form and details as well as other embodiments are possible moreover it is expressly intended that specific elements and or method steps described in connection with any disclosed embodiment of the invention may be incorporated in any other embodiment as a general matter of design choice.

For example similar considerations apply if the computers have different structure or include equivalent units in any case it is possible to replace the computers with any code execution entity such as a PDA a mobile phone and the like .

Similar considerations apply if the program which may be used to implement each embodiment of the invention is structured in a different way or if additional modules or functions are provided likewise the memory structures may be of other types or may be replaced with equivalent entities not necessarily consisting of physical storage media . Moreover the proposed solution lends itself to be implemented with an equivalent method having similar or additional steps even in a different order . In any case the program may take any form suitable to be used by or in connection with any data processing system such as external or resident software firmware or microcode either in object code or in source code . Moreover the program may be provided on any computer usable medium the medium can be any element suitable to contain store communicate propagate or transfer the program. Examples of such medium are fixed disks where the program can be pre loaded removable disks tapes cards wires fibres wireless connections networks broadcast waves and the like for example the medium may be of the electronic magnetic optical electromagnetic infrared or semiconductor type.

In any case the solution according to the present invention lends itself to be carried out with a hardware structure for example integrated in a chip of semiconductor material or with a combination of software and hardware.

Embodiments can thus take form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. Certain embodiments are implemented in software which includes but is not limited to firmware resident software microcode etc. In a high performance system a hardware implementation of the virtualization mechanism bundled with image generation processing may prove advantageous for example.

Furthermore certain embodiments can take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium can be any apparatus that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

