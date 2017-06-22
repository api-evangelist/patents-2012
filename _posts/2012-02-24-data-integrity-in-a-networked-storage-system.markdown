---

title: Data integrity in a networked storage system
abstract: A method of writing data to a distributed file system including a file system client, a server and a storage resource target, includes generating, on the client, a write request including a byte stream to be written to the storage resource target; formatting, on the client, the byte stream into sectors in accordance with the T10 protocol, the sectors including a data field and a protection information field, the protection information field including a guard field, an application field and a reference field; computing, on the client, checksum data for the guard field; sending, across a network, the data and the protection information to the server; verifying, in T10-capable hardware on the server, the checksum data for the guard field; verifying, on the storage resource target, the checksum data for the guard field; and storing the data on the storage resource target.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09225780&OS=09225780&RS=09225780
owner: Xyratex Technology Limited
number: 09225780
owner_city: Havant
owner_country: GB
publication_date: 20120224
---
The primary field of use for the present method and apparatus is in the field of networked storage systems. Such systems may non exhaustively comprise distributed file systems cloud networks remote storage or other network addressable storage arrangements. The present invention relates more specifically to a method of and apparatus for end to end data integrity. In particular the present invention relates to a method of and apparatus for end to end data integrity using the T10 protocol.

Data integrity is a core requirement for a reliable storage system. The ability to prevent and if necessary identify and correct data errors and corruptions is essential for operation of storage systems ranging from a simple hard disk drive up to large mainframe storage arrays.

A typical hard disk drive comprises a number of addressable units known as sectors. A sector is the smallest externally addressable portion of a hard disk drive. Each sector typically comprises 512 bytes of usable data. However recent developments under the general term advanced format sectors enable support of sector sizes up to 4 k bytes. When data is written to a hard disk drive it is usually written as a block of data which comprises a plurality of contiguous sectors.

A hard disk drive is an electro mechanical device which may be prone to errors and or damage. Therefore it is important to detect and correct errors which occur on the hard disk drive during use. Commonly hard disk drives set aside a portion of the available storage in each sector for the storage of error correcting codes ECCs . This data is also known as protection information. The ECC can be used to detect corrupted or damaged data and in many cases such errors are recoverable through use of the ECC. However for many cases such as enterprise storage architectures the risks of such errors occurring are required to be reduced further.

One approach to improve the reliability of a hard disk drive storage system is to employ redundant arrays of inexpensive disk RAID . Indeed RAID arrays are the primary storage architecture for large networked computer storage systems.

The RAID architecture was first disclosed in A Case for Redundant Arrays of Inexpensive Disks RAID Patterson Gibson and Katz University of California Berkeley . RAID architecture combines multiple small inexpensive disk drives into an array of disk drives that yields performance exceeding that of a single large drive.

There are a number of different RAID architectures designated as RAID 1 through RAID 6. Each architecture offers disk fault tolerance and offers different trade offs in terms of features and performance. RAID controllers provide data integrity through redundant data mechanisms high speed through streamlined algorithms and accessibility to stored data for users and administrators.

RAID architecture provides data redundancy in two basic forms mirroring RAID 1 and parity RAID 3 4 5 and 6 . The implementation of mirroring in RAID 1 architectures involves creating an identical image of the data on a primary disk on a secondary disk. RAID 3 4 5 or 6 architectures generally utilise three or more disks of identical capacity. In these architectures two or more of the disks are utilised for reading writing of data and one or more of the disks store parity information. Data interleaving across the disks is usually in the form of data striping in which the data to be stored is broken down into blocks called stripe units . The stripe units are then distributed across the disks.

Therefore should one of the disks in a RAID group fail or become corrupted the missing data can be recreated from the data on the other disks. The data may be reconstructed through the use of the redundant stripe units stored on the remaining disks. However RAID architectures utilising parity configurations need to generate and write parity information during a write operation. This may reduce the performance of the system.

For a system with local storage the American National Standards Institute s ANSI T10 DIF Data Integrity Field specification format enables data protection. The T10 DIF format specifies data to be written in blocks or sectors of 520 bytes. This is shown schematically in . The 8 additional bytes in the data integrity field provide additional protection information PI some of which comprises a checksum that is stored on the storage device together with the data. The data integrity field is checked on every read and or write of each sector to verify data integrity between system memory and a host bus adapter HBA . This enables detection and identification of data corruption or errors. T10 DIF is hardware based where an I O controller adds the protection information PI that is then verified by the storage device hardware. Therefore T10 DIF is only suitable for localised hardware because it cannot protect across a network.

ANSI T10 DIF provides three types of data protection logical block guard GRD for comparing the actual data written to disk a logical block application tag APP and a logical block reference tag REF to ensure writing to the correct virtual block. The logical block application tag is not reserved for a specific purpose.

In general the operation of T10 DIF in a local storage system is shown in . A byte stream is generated by a client application. This is then formatted by an Operating System OS into a byte sector of 512 bytes. The I O controller or host bus adapter then appends 8 bit PI to the 512 byte sector to form a 520 byte sector. This is then sent via a storage area network SAN to the RAID array and eventually to the disk drive where the data is written as a 520 byte sector. The PI is checked at each of these stages.

A further extension to the T10 DIF format is the T 10 DIX data integrity extension format which enables 8 bytes of extension information to enable PI potentially to be piped from the client application directly to the storage device.

This process is illustrated in . The same data format of 520 byte sector is used in T10 DIX as for T10 DIF. However in this instance 8 bytes of PI is generated by the user application or OS along with the 512 byte sector. The 8 byte PI is then checked at every stage in the transfer of data to the storage disk drive.

Data protection measures such as RAID T10 DIF and T10 DIX are useful to prevent data corruption and errors occurring locally on a storage system. However storage solutions are now generally accessible across networks. For example distributed file systems are now common. A distributed file system or network file system is a file system that allows access to files from multiple hosts or clients sharing via a network such as an Ethernet or the internet. This makes it possible for multiple users on multiple machines to share files and storage resources. The most common arrangement is a client server architecture in which the server provides a service to requesting hosts.

A commonly used distributed file system is Lustre . Lustre is a parallel distributed file system generally used for large scale cluster computing. Lustre file systems are scalable and are able to support many thousands of clients and multiple servers. A Lustre file system generally comprises three units a metadata server MDS one or more object storage servers OSSs and one or more clients which access the OSSs.

The MDS generally comprises a single metadata target MDT per file system that is operable to store metadata such as filenames directories access permissions and file layout. The MDT data is generally stored in a single local disk file system.

The OSSs store file data on one or more object storage targets OSTs . Each OST manages a single local disk file system. Lustre presents all clients with a unified namespace for all of the files and data in the file system and allows read and write access to the files in the file system.

One of the challenges of a distributed file system such as Lustre is to provide efficient end to end data integrity. Therefore mechanisms are required to ensure that data sent by a client node e.g. client computer or application is stored on a respective OST correctly. In other words it is desirable for data written by a client application to be verified as correctly saved on a storage device. This is not possible using techniques such as RAID T10 DIF and T10 DIX. This is because these techniques act locally on a server whereas in a network file system data corruption may occur at other locations for example on the client or across the network before the data arrive at the server.

In order to address this issue many Lustre systems use an I O checksum which provides over the wire verification. The Lustre checksum uses a CRC 32 algorithm to detect single bit errors and swapped and or missing bytes. A Lustre network checksum is generally provided per 1 MB client remote procedure call RPC . However other checksum algorithms may also be used for example Adler32 or CRC 32c.

However whilst the Lustre checksum is able to provide over the wire verification of data these checksums are only able to provide protection over a network. They cannot provide protection locally on a server. In addition the Lustre checksum algorithm requires a significant amount of computational resources on the server side to execute the necessary checksums. This is particularly an issue since the number of checksums to be calculated scales with the number of clients and there are generally considerably more clients and therefore considerably more RPCs to execute than there are servers. Consequently storage system performance can be affected if the OSS and MDS server hardware is not powerful enough to handle both the I O file system administration and checksum services concurrently.

Therefore in summary the existing T10 DIF format is operable to provide data integrity locally. In addition the network checksum can only provide data integrity over the wire. Neither of these approaches can provide data integrity on the client itself let alone complete end to end data integrity. Furthermore T10 DIF and network checksums are not linked together in any way increasing complexity and computational loads on the servers.

Consequently to date known storage systems suffer from a technical problem that end to end data integrity cannot be achieved reliably on existing storage systems and without placing high demand on server resources.

According to a first aspect of the present invention there is provided a method of writing data to a distributed file system comprising at least one file system client at least one server and at least one storage resource target the method comprising a generating on said client a write request comprising a byte stream to be written to said storage resource target b formatting on said client said byte stream into sectors in accordance with the T10 protocol the sectors comprising a data field and a protection information field the protection information field comprising a guard field an application field and a reference field c computing on said client checksum data for said guard field d sending across a network said data and said protection information to said server e verifying in T10 capable hardware on said server said checksum data for said guard field and f verifying on said storage resource target said checksum data for said guard field and g storing said data on said storage resource target.

In one embodiment step b further comprises formatting said byte stream into sectors comprising 512 bytes of data and 8 bytes of protection information in accordance with the T10 protocol.

In one embodiment prior to step d the method further comprises h said data and protection information is formatted into an RPC format.

In one embodiment after step c the method further comprises i writing said checksum data to the client kernel and j recomputing said checksum data for said guard field.

According to a second aspect of the present invention there is provided a method of reading data from a distributed file system comprising at least one client at least one server and at least one storage resource target the method comprising a executing from said client a read request for reading of data from at least one data sector the or each data sector being in accordance with the T10 protocol and comprising a data field and a protection information field the protection information field comprising a guard field comprising checksum data an application field and a reference field b verifying on said storage resource target the protection information associated with the requested sector or sectors c verifying in T10 capable hardware on said server the checksum data in said guard field d sending across a network said data and said protection information to said client e verifying on said client said checksum data in said guard field and f if said steps of verification are successful reading the data from the or each data sector.

In one embodiment step b further comprises formatting said byte stream into sectors comprising 512 bytes of data and 8 bytes of protection information in accordance with the T10 protocol.

In one embodiment in step d the method further comprises h sending said data and protection information in a RPC format.

According to a third aspect of the present invention there is provided a distributed file system comprising at least one client at least one server and at least one storage resource target the distributed file system being configured to carry out the steps of the first or second aspects.

According to a fourth aspect of the present invention there is provided a computer program product executable by a programmable processing apparatus comprising one or more software portions for performing the steps of the first and or second aspects.

According to a fifth aspect of the present invention there is provided a computer usable storage medium having a computer program product according to the fourth aspect stored thereon.

The present invention is directed to a networked file system in which the T10 DIF and T10 DIX data integrity protocols can be extended to achieve end to end data integrity across the network from host application to storage device.

The networked storage resource comprises a distributed file system. A distributed file system consists of client to N and servers to N nodes connected by a network . The servers take the form of OSSes. Client applications running on client nodes make storage requests which may comprise file storage requests against the distributed file system. Some of these calls result in updates to the file system state.

The distributed networked storage resource comprises a plurality of hosts . The hosts are representative of any computer systems or terminals that are operable to communicate over a network. Any number of hosts or servers may be provided N hosts and N servers are shown in where N is an integer value.

The hosts are connected to a first communication network which couples the hosts to a plurality of servers . A metadata server MDS is also connected to the network . The MDS comprises local storage

The communication network may take any suitable form and may comprise any form of electronic network that uses a communication protocol for example a local network such as a LAN or Ethernet or any other suitable network such as a mobile network or the internet.

The servers are connected through device ports not shown to a second communication network which is also connected to a plurality of OSTs to N in the form of RAID arrays of storage devices . The second communication network may comprise any suitable type of storage controller network which is able to connect the servers to the storage devices . The second communication network may take the form of for example a SCSI network an iSCSI network or fibre channel.

The servers may comprise any storage controller devices that process commands from the hosts and based on those commands control the storage devices . The storage devices may take any suitable form for example tape drives disk drives non volatile memory or solid state devices.

Although most RAID architectures use hard disk drives as the main storage devices it will be clear to the person skilled in the art that the embodiments described herein apply to any type of suitable storage device. More than one drive may form a storage device for example a RAID array of drives may form a single storage device . The skilled person will be readily aware that the above features of the present embodiment could be implemented in a variety of suitable configurations and arrangements. Additionally each OST comprising a RAID array of devices appears to the hosts as a single logical storage unit LSU or drive. Any number of OSTs may be provided in N OSTs are shown where N is any integer value.

As an alternative variation a RAID array of drives is not necessarily required. Alternatively a single T10 DIF disk drive could function as an OST. Similarly parity declustered RAID PDRAID devices could be used including network striped PDRAID. The skilled person would be readily aware of variations which fall within the scope of the present invention.

The operation of the servers may be set at the Application Programming Interface API level. Typically Original Equipment Manufacturers OEMs provide RAID networks to end clients for network storage. OEMs generally customise a RAID network and tune the network performance through an API.

The servers and OSTs also provide data redundancy. The storage devices comprise RAID controllers described with reference to which provide data integrity through a built in redundancy which includes data mirroring. The storage devices are arranged such that should one of the drives in a group forming a RAID array fail or become corrupted the missing data can be recreated from the data on the other drives.

The host comprises a general purpose computer PC which is operated by a client and which has access to the storage resource . The OSS comprises a software application layer an operating system and a host bus adapter HBA .

The software application layer comprises software applications including the algorithms and logic necessary for the initialisation and run time operation of the server . The software application layer includes software functional blocks such as a system manager for fault management task scheduling and power management. The software application layer also receives commands from the host e.g. assigning new volumes read write commands and executes those commands. Commands that cannot be processed because of lack of space available for example are returned as error messages to the client of the host .

The operating system utilises an industry standard software platform such as for example Linux upon which the software applications forming part of the software application layer can run. The operating system comprises a Lustre file system which enables the HBA to store and transfer files to the OST via a RAID controller .

The HBA is the physical hardware interface between the RAID controller and the server that executes the software applications in the software application layer . The HBA comprises a microprocessor memory and all other electronic devices necessary for I O control with the RAID controller operable to control the storage devices of the OST . In this embodiment the HBA comprises the hardware necessary to utilise the T10 protocol i.e the HBA is configured to process the necessary checksums for data verification for each 520 byte sector as will be described below.

The HBA may take any suitable format. However it is required that the HBA has T10 DIX type 1 or 2 support which provides for checking of the GRD and REF fields of each sector.

Whilst in the HBA is shown as part of the server this need not be so. The skilled person would be readily aware of alternatives which fall within the scope of the present invention for example the HBA may be remote from the server .

The server is operable to receive storage requests which may comprise I O requests to the Lustre file system from hosts or clients and process said storage requests to the file system . The Lustre file system may comprise any suitable variant of the system and may be run on the server to provide access to the storage devices . Non exhaustive examples of suitable file systems may be NTFS HFS ext3 or ext4.

The Lustre file system enables the storage on the OST to be externally visible to the clients . Clients reference file offsets and ranges or extents presented by the file system. In order to do so file system structures on the MDS comprise tables related to device space management. Such table information includes for each file on the OST a set of device block numbers identifying blocks where file data is stored and a list of a set of free blocks which do not hold file data.

The format of the storage devices will now be described with reference to . illustrates an example of a RAID 6 array. However other arrangements may be used with the present invention for example RAID 5 RAID 10 or RAID 50.

As shown in data is stored on the RAID 6 array in the form of stripe units also known as RAID chunks . Each data stripe A B comprises ten separate stripe units distributed across the storage devices stripe A comprises stripes A A and parity stripe units Aand A. Stripe B comprises stripe units B to B and parity stripe unit Band B. Therefore the stripe units comprising each stripe A A or B B respectively are distributed across a plurality of disk drives together with parity information A A Band Brespectively. This provides data redundancy.

The size of a stripe unit can be selected based upon a number of criteria depending upon the demands placed upon the RAID array e.g. workload patterns or application specific criteria. Common stripe unit sizes generally range from 16K up to 256K. In this example 128K stripe units are used. The size of each stripe A B is then determined by the size of each stripe unit in the stripe multiplied by the number of non parity data storage devices in the array which in this example is eight . In this case if 128K stripe units are used each RAID stripe would comprise 8 data stripe units plus 2 parity stripe units and each RAID stripe A B would be 1 MB wide.

However the stripe size is not material to the present invention and the present example is given as a possible implementation only. Alternative arrangements may be used. Any number of drives or stripe unit sizes may be used.

Storage on a storage device comprises a plurality of sectors also known as logical blocks . A sector is the smallest unit of storage on the storage device . A stripe unit will typically comprise a plurality of sectors.

As set out above the term storage device in the context of the following description may refer to a logical drive which is formed on the RAID array. In this case a sector refers to a portion of the logical drive created on the RAID array. The following embodiment of the present invention is applicable to any of the above described arrangements.

The term sector used herein whilst described in an embodiment with particular reference to 520 byte sector sizes as specified by the T10 protocol is generally applicable to any sector sizes within the scope of the present invention. For example some modern storage devices comprise 4 KB data sectors and a 64 byte data integrity field. Therefore the term sector is merely intended to indicate a portion of the storage availability on a storage device within the defined storage protocols and is not intended to be limited to any of the disclosed examples. Additionally sector may be used to refer to a portion of a logical drive i.e. a virtual drive created from a plurality of physical hard drives linked together in a RAID configuration.

In this embodiment the storage device is formatted such that each sector comprises 520 bytes 4160 bits in accordance with the American National Standards Institute s ANSI T10 DIF Data Integrity Field specification format. The T10 DIF format specifies data to be written in blocks or sectors of 520 bytes. The 8 additional bytes in the data integrity field provide additional protection information PI some of which comprises a checksum that is stored on the storage device together with the data. The data integrity field is checked on every read and or write of each sector. This enables detection and identification of data corruption or errors.

As set out above the data field in this embodiment is 512 bytes 4096 bits long and the data integrity field is 8 bytes 64 bits long. The data field comprises user data to be stored on the storage device . This data may take any suitable form and as described with reference to may be divided into a plurality of stripe units spread across a plurality of storage devices . However for clarity the following description will focus on the data stored on a single storage device .

In a T10 based storage device the data integrity field comprises a guard GRD field an application APP field and a reference REF field . The GRD field comprises 16 bits of ECC CRC or parity data for verification by the T10 configured hardware. In other words sector checksums are included in the GRD field in accordance with the T10 standard. The format of the guard tag between initiator and target is specified as a CRC using a well defined polynomial. The guard tag type is required to be a per request property not a global setting.

The APP field comprises 16 bits reserved for application specific data. In practice this field is rarely used.

The REF field comprises 32 bits of location information that enables the T10 hardware to prevent misdirected writes. In other words the physical identity for the address of each sector is included in the REF field of that sector in accordance with the T10 standard.

The checksums in the GRD field and REF field are processed by the T10 compliant HBA . These CRC calculations are relatively processor intensive so by performing these tasks in specialist T10 hardware the HBA the central processing units CPUs of the server are freed from the task of checksum calculation and processing.

Since in general the number of hosts will be significantly greater than the number of servers in conventional Lustre file systems the server computational resources are the limiting factor is calculating and verifying data checksums.

Therefore an aspect of the present invention is that the client side application or OS is required to calculate the necessary GRD checksums under the T10 protocol. These checksums can then be analysed by the specialist T10 hardware in the HBA on the server . This frees the server CPUs from having to perform these calculations.

The operation of a T10 DIF DIX compliant distributed network system will now be described with reference to . shows a flow diagram of the method for writing data to the OST with end to end data integrity. shows a flow diagram of the method for reading data from the OST .

At step a client application running on host generates a write request for a specific volume e.g. OST to which it has been assigned access rights. A byte stream is generated.

At step the byte stream is formatted by a host side operating system OS into 512 byte data sectors. The method proceeds to step .

The client application computes the GRD checksum for each sector. This is in the form of a CRC checksum and is done utilising client side processor resources.

Alternatively the GRD checksum could be calculated by the client side OS. The method proceeds to step .

At step the GRD for each sector is recomputed by the client side application or OS after a kernel copy has been made. The recalculated GRD values are then saved in a private page area.

Note that this step is optional and costs additional client side processor resources. However inclusion of this step enables identification of the source of a corruption. Therefore it may be useful to include this step in high risk systems.

At step the calculated GRD information generated in steps and or is then added into a bulk I O descriptor. In other words the generated GRD PI is placed in a separate bulk I O buffer which is 1 64 of the total data size and a descriptor is added to the outbound RPC.

The request is sent via communication network to the host ports not shown of the server . The write command is then stored in a local cache not shown forming part of the HBA of the server . The write request is sent in the format of a standard Lustre RPC 1 MB 

At step the OSS receives the write request in the form of a bulk I O. At this stage there is no need for the OSS to recompute the GRD values prior to replying to the request from the host as would be required with conventional arrangements. This reduces the load on the server CPUs.

In general the OSS delays a reply to the host until the write returns successfully from the disk I O subsystem. This is in case an error is detected.

At step the OST maps the PI for each sector received in the write request. Whilst the above steps have only referred to the GRD field all 8 bits of PI under the T10 protocol are required to be transferred between the host and the OST otherwise memory copies would be required to interleave the data.

Once the PI for each sector has been mapped in step it is passed to the MD RAID layer. At this point the MDRAID layer maps the REF field of each sector and calculates any required RAID parity.

At step the HBA obtains the scatter gather SG lists of data and corresponding protection information. The HBA requires dual SG lists for data and PI to achieve this.

At step the HBA recalculates the GRD sector checksums. Since this is done using specialist T10 compliant hardware in this example the HBA the computational demands on the server processors is minimal.

The GRD is also checked at this point. If the GRD is verified as accurate the method proceeds directly to step . However if an error is returned this is reported to the last GRD recompute step. This may be step or on the client side. These steps are then repeated until the error is corrected.

At step the data is written to the storage device via the RAID controller . At this point the REF and GRD fields are checked and verified. If they are verified as correct the data is written in step . If an error is detected the method returns to step .

At step the data has been verified from client application through to storage device disk level and the data is written to an intended sector.

At step a client application running on host generates a read request for a specific volume e.g. OST to which it has been assigned access rights. At this point the host sets up data and PI buffers and then a bulk I O request is sent.

Once the read request generated in step is received by the OST corresponding data and PI buffers are generated thereon.

In step the storage device verifies the GRD and REF fields of the requested data sectors. The data once verified is then sent to the HBA .

At step the parity of the retrieved data sectors is verified. If an error is detected the data is reconstructed. If necessary once the data has been reconstructed the method proceeds to step .

At step the kernel on the host verifies the GRD field of the received data. The method proceeds to step .

As an optional step the client application and or OS on the host may also verify the GRD data . The method proceeds to step .

Variations of the above embodiments will be apparent to the skilled person. The precise configuration of hardware and software components may differ and still fall within the scope of the present invention.

For example the present invention has been described with reference to controllers in hardware. However the controllers and or the invention may be implemented in software. This can be done with a dedicated core in a multi core system.

Whilst the above examples have been illustrated with respect to T10 capable hardware such as a T10 DIF or T10 DIX compliant HBA other arrangements are possible. For example T10 capable hardware such as T10 compliant hard drives may be used.

Additionally whilst the present embodiment relates to arrangements operating predominantly in off host firmware or software an on host arrangement could be used.

Further alternative ECC methods could be used. The skilled person would be readily aware of variations which fall within the scope of the appended claims.

Embodiments of the present invention have been described with particular reference to the examples illustrated. While specific examples are shown in the drawings and are herein described in detail it should be understood however that the drawings and detailed description are not intended to limit the invention to the particular form disclosed. It will be appreciated that variations and modifications may be made to the examples described within the scope of the present invention.

