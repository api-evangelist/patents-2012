---

title: File storage system and file cloning method
abstract: A file storage performs control to create a virtual parent file having an identifier capable of uniquely identifying a parent file among storage systems and volumes, and to acquire block layout information of the parent file using said identifier. The file storage creates a virtual parent file in the volume in which the clone file is created, and sets the file as a virtual parent file of the clone file so as to enable creation of a clone file of a parent file that exists in a different volume or a different storage system. Moreover, by combining creating the virtual parent file and switching the identifier of the parent file which is pointed by the virtual parent file, migration of clone files and parent files astride storage systems and volumes is enabled.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09116913&OS=09116913&RS=09116913
owner: Hitachi, Ltd.
number: 09116913
owner_city: Tokyo
owner_country: JP
publication_date: 20120425
---
Recently a file cloning technique in which a physical storage data of a replication source file stored in a file storage is shared with a file in a replication destination clone file is being utilized widely to enhance the speed of the file replication processing and the reduction of the storage device usage. Patent literature 1 discloses an art of creating a snapshot file that shares physical storage data with a replication source file and further creating a clone file for managing a difference data with respect to the snapshot file.

Further patent literature 2 discloses an art of migration of a replication source file which shares physical storage data with the snapshot file to an offline storage.

If a large number of clone files are created from a single replication source file a problem occurs in which accesses are concentrated on a physical storage data of the replication source file and the snapshot file. And the storage device which stores these physical storage data become a bottleneck of the performance of the system. That is there is a restriction according to the invention disclosed in patent literature 1 in that the clone file can only be created with respect to the replication source file stored within the same volume.

Therefore in order to create a large number of clone files with respect to a single replication source file it was necessary to use a high performance expensive storage device such as a SSD Solid State Drive as the storage device constituting the volume according to which the costs of the system become expensive.

By combining the teachings of patent literature 1 and patent literature 2 it becomes possible to migrate the physical storage data of the replication source files to the SSD. However since difference data between the snapshot files and the replication source files remain in the original volume an expensive storage device is still required as the original volume if there is a large difference between the replication source files and the snapshot files.

Further since the snapshot files can only be created within the same volume as the replication source files it is not possible to create clone files of replication source files stored in high performance volumes or storage systems for example.

Therefore it was not possible according to the prior art techniques to migrate parent files of a clone files corresponding to snapshot files of the prior art or the clone files in response to performance requirements and to create clone files of parent files stored in different volumes or different storage systems.

Therefore the object of the present invention is to provide a method and system for cloning files astride volumes and storage systems capable of cutting down a large amount of capacity used on the storage device.

In order to solve the problems mentioned above the present invention provides a means to create a clone file of a parent file stored in a different volume or different storage system and a means for migrating the clone file and the parent file astride volumes and storage systems.

Actually the present invention provides a file storage system capable of performing control to create a virtual parent file having an identifier capable of uniquely identifying the parent file among storage systems and volumes and to acquire block layout information of the parent file using the identifier.

That is the file storage system creates a virtual parent file in a volume in which a clone file is to be created and the virtual parent file is used as a reference pointer to the parent file so as to enable creation of clone files of a parent file existing in a different volume or different storage system. Furthermore by combining creating a virtual parent file and switching the parent file identifier which is pointed by the virtual parent file the file storage system enables the clone files and parent files to be migrated astride storage systems and volumes.

The present invention enables to reduce the storage device usage significantly since physical storage data of replication source files and clone files can be shared among different volumes storage systems.

Now the preferred embodiments of the present invention will be described with reference to the drawings. In the following description various information are referred to as management table and the like but the various information can be expressed via data structures other than tables. Further the management table can also be referred to as management information to show that the information does not depend on the data structure.

The processes are sometimes described using the term program as the subject. The program is executed by a processor such as a CPU Central Processing Unit for performing determined processes. A processor can also be the subject of the processes since the processes are performed using appropriate storage resources such as memories and communication interface devices such as communication ports . The processor can also use dedicated hardware in addition to the CPU. The computer program can be installed to each computer from a program source. The program source can be provided via a program distribution server or a storage media for example.

Each element such as a file block a disk block or an LU Logical Unit can be identified via numbers but other types of identification information such as names can be used as long as they are identifiable information. The equivalent elements are denoted with the same reference numbers in the drawings and the description of the present invention but the present invention is not restricted to the present embodiments and other modified examples in conformity with the idea of the present invention are included in the technical range of the present invention. The number of each component can be one or more than one unless defined otherwise.

Now a method for cloning files among different volumes within a single storage system according to a first embodiment of the present invention will be described with reference to .

The file storage is a computer for performing control of files generated by the client server . The file storage provides a means for storing data using a management unit called a file or a directory with respect to the client server . The file mentioned above is the management unit of data used commonly in the file storage and in the client server and the entity thereof is the physical storage data stored in a storage device described later.

Further a directory refers to a management structure used commonly in the file storage and the client server for collectively managing zero or more files or directories. The client server designates the file to be the access target of the file storage by using a file path which is a character string representing the directory and the file via a tree structure. The client server is a computer such as a personal computer a general purpose server or a mainframe which is used for the purpose of performing document creating operations in offices or as a mail server or a Web server.

The management server is also a computer such as a personal computer a general purpose server or a mainframe similar to the client server . The management server is equipped with an information input device not shown such as a keyboard a switch a pointing device and a microphone and an information output device not shown such as a monitor display and a speaker.

A local area network is a computer network to which the file storage the client server and the management server are coupled. One preferable example of the local area network is an Ethernet Registered Trademark . Preferable examples of the communication protocol of the local area network include a TCP IP Transmission Control Protocol Internet Protocol and a UDP IP User Datagram Protocol Internet Protocol .

Preferable examples of the protocol used for sending and receiving files and directories include an NFS Network File Storage a CIFS Common Internet File System an HTTP Hyper Transport Transfer Protocol and an iSCSI Internet Small Computer System Interface .

The file storage receives a data access request in file units sent from the client server via the local area network and sends a processing result regarding the data access request to the client server . Further a management server is also coupled to the local area network . The file storage receives a management access request sent from the management server via the local area network and sends a processing result regarding the management access request to the management server .

The file storage is composed of a file server for processing a file operation request from the client server and a disk subsystem for physically storing the data of the file. The file server is equipped with a CPU Central Processing Unit a main memory and an internal disk .

The file storage further comprises a network IF Interface for coupling to the local area network and a storage IF for coupling to the disk subsystem . The CPU realizes various functions of the file server according to the present embodiment by reading and executing various programs stored in the internal disk in the main memory .

The main memory is a storage device for storing various programs described later. The internal disk is a nonvolatile memory for storing various programs and management information described later. The network IF is composed of a network interface card such as an Ethernet interface card or a wireless LAN Local Area Network interface card.

The network IF functions as a data input and output adapter for enabling the file server to be coupled to the client server and the management server . The storage IF is composed for example of a SCSI Small Computer System Interface interface card or a fiber channel interface card. The storage IF functions as a data input and output adapter for coupling the file server to the disk subsystem .

The disk subsystem comprises a CPU a main memory one or more storage devices and and a disk IF . If the storage devices and are not distinguished the storage devices can be collectively referred to as a storage device .

The CPU realizes various functions of the disk subsystem according to the present embodiment by executing various programs read into the main memory . The main memory is a semiconductor memory for storing the above described various programs. The disk IF functions as a data input and output adapter for coupling the disk subsystem to the file server .

The storage device SSD and the storage device SAS are nonvolatile memory devices having different access properties. For example the storage devices and at least have different data reading speed and or data writing speed. The storage device SSD uses an SSD as the memory media which is capable of responding with relatively small delay to data access but the cost per capacity thereof is relatively expensive.

The storage device SAS uses an HDD Hard Disk Drive having a SAS Serial Attached SCSI interface as the memory media which has greater delay to data access but lower cost per capacity compared to the storage device SSD . These storage devices are used as a data storage system. Further other types of storage devices such as a SATA Serial ATA type HDDs optical disk devices magneto optical disk drives and magnetic tape devices can also be used.

The file server and the disk subsystem are coupled via a storage IF and a disk IF . The storage IF and the disk IF can be either coupled via a switch or coupled directly without a switch.

A communication protocol such as a SCSI or an iSCSI can be preferably used as the communication protocol of the storage IF and the disk IF . In the present embodiment the file server and the disk subsystem are composed of two different systems but the file server and the disk subsystem can also be formed as an integrated system.

The file server executes an operating system program a network file service program a file server management program a file move program and a network file client program . Further the file server stores a volume management table in an internal disk .

The operating system program has for example an input output control function and a read write control function for reading data from and writing data to the memory such as a disk or a memory and provides these functions to other programs. The operating system program includes therein a file system module and a volume management module .

The file system module has a function to manage the data stored in the storage device in file units or directory units and provides to an upper program an access IF to these files and directories. The file system module includes a file cloning module and a snapshot module performing access processing to files and directories and performing replication processing of files.

The file cloning module provides a file cloning function for creating a replication file called a clone file that shares physical storage data with a replication source file. The clone file refers to the physical storage data of the replication source file in all areas immediately after replication but when update occurs via a file write process the clone file refers to a physical storage area newly allocated for the update data regarding the updated portion.

The snapshot module provides a function to create a snapshot file having a quiesced image at a certain time of the replication source file. The snapshot file is similar to the clone file in that it shares the physical storage data with the replication source file but differs from the clone file in that when a file write occurs to the replication source file the data prior to update is replicated to the newly allocated physical storage area and not the update data.

The volume management module logically binds LUs Logical Units which will be described later provided by the disk subsystem as shown in and manages the same as a volume which is a single continuous logical memory area. Further the volume management module provides an access IF to the file system module for storing a disk block mentioned later to the volume . One preferable example of the volume management module is a LVM Logical Volume Manager included in a Linux Registered Trademark OS.

The network file service program provides to the client server an IF for accessing the data stored in the storage device in file units or in directory units. The network file service program having received from the client server the file operation request with respect to the file performs the reading and writing of data of the file stored in the disk subsystem via the file system module .

The file server management program cooperates with a management GUI program operated in the management server and provides an interface for the manager to manage the file server .

The file move program provides a function to replicate the file within the volume and astride volumes to the client server and the host server. The network file client program issues a file operation request to the network file serviced provided by the external file storage and provides an IF for receiving the response to another program.

The volume management table includes a management information of the volume managed by the volume management module . The details of the volume management table will be described with reference to .

The disk subsystem executes a disk control program . Further the disk subsystem stores a file system management information in the storage device .

The disk control program logically binds one or more storage devices as illustrated in and manages the same as an LU which is a single continuous memory area. The disk control program provides an IF for storing data in block units to the LU to the file server . The block refers to a logical unit for storing a data having a fixed length to a physical storage area of the storage device . Upon receiving an IO Input Output request designating the disk block number and the length from the file server the disk control program performs control to issue an IO request to the corresponding storage device and returns a response to the file server .

The file system management information is the management information used by the file system module for managing the files within the volume which has a one to one correspondence with the volume . The file system module reads the file system management information into the main memory and performs control to manage the file and the directory. The details of the file system management information will be described later with reference to .

The management server executes a management GUI program . Although not shown in the drawing the management GUI program is stored in the main memory of the management server and executed by the CPU. The management GUI program provides an IF to the manager for operating the file server . The contents of the operation that the manager performs to the file server is notified to the file server management program by the management GUI program and is reflected in the file server .

According to the present embodiment the file cloning module provides a means for creating a clone file to a parent file stored in a different volume .

Upon replicating a file in a different volume the file cloning module creates a virtual parent file having an identifier uuid for uniquely identifying the parent file within the file storage with respect to a quiesced image parent file of the replication source file and sets the file as a virtual parent file of the clone file .

Further when a file operation request to a clone file is received the file system module performs control to acquire a block layout table of the parent file from the uuid information that the virtual parent file has and accesses a physical storage data of the parent file . Further during migration of the parent file the switching control of a reference destination of the uuid of the virtual parent file is performed. As described by providing the virtual parent file the clone file can switch the parent file being referred to. Even when there are multiple clone files only the virtual parent file will be the target of update so that switching can be performed during a certain period of time regardless of the number of clone files.

Thereby it becomes possible to create a clone file with respect to a parent file stored in a different volume or to migrate parent files and clone files to different volumes. As a result the manager can select a storage device for storing the parent file and the clone file in response to the performance requirements. For example by storing a parent file having a large number of clone files in a high speed storage device SSD a larger number of clone files can be created.

According to the present embodiment it is possible to distribute the accesses of the parent file to a plurality of replication of the parent file stored in different volumes . As a result it becomes possible to enhance the access performance of the parent file . For example if it is not possible to ensure a sufficient performance by a single storage device SSD it becomes possible to create a larger number of clone files by creating a replication of the parent file in another storage device SSD .

According to the first embodiment the file system module manages in addition to normal files a parent file which is a quiesced image of a replication source file and a clone file sharing physical storage data with the parent file . Further a normal file according to the present invention is a generic term of files excluding the parent file the clone file the parent clone file described later and the virtual parent file described later . Further the management of difference data of the parent file and the replication source file is realized by replacing the replication source file itself with the cloned parent clone file . Now the file system management information used for managing these files will be described based on the prior art method and the implementation example of the present embodiment.

According to the prior art file cloning technique an inode is used to manage the reference relationship of the parent file the clone file and the parent clone file within the same volume. Further the file system module uses the block layout table to manage the physical storage data of each file. In this case the parent file manages the data of the original file and the clone file and the parent clone file manage the difference data from the parent file . Now we will describe the information managed by the inode . The block layout table will be described later with reference to .

The inode number is an identifier for uniquely identifying the inode within the volume managed by the file system. The file system module is capable of acquiring the inode corresponding to the inode number from the file system management information . A file flag is the flag indicating the classification of a file and includes three bits a clone file bit a parent file bit and a parent clone file bit.

The file system module is capable of distinguishing via the file flag whether the file is a parent file a virtual parent file or a parent clone file . A file attribute is the information indicating the access authority of a file. When a file operation request is received the file system module examines the file attribute and determines whether the access source has the authority to operate the operation target file.

A parent inode number is an inode number of an inode of the parent file which is set with respect to the clone file and the parent clone file . According to these settings as shown in it becomes possible for the clone file and the parent clone file to point to the parent file . A parent clone inode number is an inode number of an inode of the parent clone file which is set with respect to the parent file . According to this setting as shown in it becomes possible for the parent file to point to the parent clone file . A reference counter is the number of clone files and parent clone files referring to the parent file and is set with respect to the parent file . In a single clone file and a single parent clone file are referred to so the reference counter will be 2 .

As shown in the drawing the mutual relationship of the clone file the parent file and the parent clone file are managed by using the parent inode number and the parent clone inode number .

The file system management information of the present embodiment includes a management information of a virtual parent file in addition to the prior art file classifications. The virtual parent file stores information necessary for the file system module to use the same instead of the parent file . In this example the virtual parent file itself does not mange physical storage data so the block layout table is vacant.

The file flag of each inode includes a virtual parent file bit in addition to the prior art bits. The virtual parent file bit is set with respect to the virtual parent file . Further the inode includes a uuid table instead of the parent inode number .

A uuid of the virtual parent file is set in the uuid table of inode of the clone file and the parent clone file a uuid of one or more parent files is set in the uuid table of inode of the virtual parent file and a uuid of one or more virtual parent files is set in the uuid table of inode of the parent file . The details of the storage information of the uuid table will be described later with reference to . Further a uuid of the parent clone file is set as the parent clone uuid of inode of the parent file .

As shown in the mutual relationship of the clone file the parent file the parent clone file and the virtual parent file can be managed using the uuid table storing the uuid and the parent clone uuid number which is the characteristic feature of the present invention.

Strictly defined the physical storage position within the storage device of the disk block is determined after performing address conversion of the volume management module and the disk control program . For simplified description it is assumed that the physical storage areas of the storage device and the disk block are in one to one correspondence. Further it is assumed that the block length of the file block and the disk block is set to 4 KB.

The file system module provides one or more continuous file blocks as file data to an upper program. Each row of the block layout table corresponds to a file data and the file data includes a file offset A a disk start position B and a block length C.

The file offset A shows an initial number of the file block allocated to the file data . The disk start position B shows the initial number of the disk block allocated to the file data . The block length C shows the number of blocks included in the file data .

A hole having no file data can exist in the file block . In that case since the file block does not have a corresponding disk block the file can be composed of a smaller number of disk blocks compared to the number of file blocks. When the file system module receives a read request with respect to the hole it returns zero data in which all areas are filled with 0.

If the file block of the clone file is not in a hole the clone file data includes the file block of the clone file . In other cases if the file block of the parent file is not in a hole the clone file data includes the file block of the parent file . If the file block of the clone file and the file block of the parent file are in holes the corresponding areas are processed as holes. The file block of the clone file and the file block of the parent file are managed via the control described with reference to .

The volume ID B is an identifier for uniquely identifying a volume managed by the volume management module within the file storage . The file ID is an identifier for uniquely identifying the file within the volume which uses an inode number .

The volume ID A is an identifier for uniquely identifying a volume within the file storage . The mount point B is a file path to which the volume is mounted. The term mount refers to the operation of the operating system program recognizing the volume and the peripheral devices and enabling access thereto.

An upper program can access files within the volume by accessing the files of the mount point and below. The LU number C is an identifier of one or more LUs constituting the volume . The file system type D is the type of the file system created in the volume .

Upon receiving a file operation request to the clone file the file system module cooperates with the file cloning module and processes the request. Upon receiving a migration request of the clone file or the parent file the file move program executes the migration processing. In the following description the method for processing the respective file operation requests and the file migration requests will be described.

Upon receiving the clone file create command the file cloning module starts a process for creating a clone file S . The clone file create command includes a file path of the replication source file for creating the clone location in which the replication source file is stored and the file path of the created clone file location in which the created clone file is stored .

The file cloning module sends an inquiry to the file system module and acquires a process target file and the inode thereof corresponding to the file path of the replication source file S . Upon executing the step S when a process target file corresponding to the file path is not found the clone file create processing is ended.

The file cloning module examines the value of a file flag within the inode of the replication source file S . If the replication source file is a parent file or a parent clone file S Yes the processes of steps S and thereafter are performed.

The file cloning module performs a quiesce processing of the replication source file and sets the file as a parent file S . Upon executing step S the file name of the parent file is changed to a different arbitrary name. Thereafter a parent clone file having the same file path as the file path of the replication source file prior to quiesce processing is created from the parent file .

At this time the file cloning module records the uuid of the parent file to the uuid table of the parent clone file and the file attribute replicates the file attribute of the parent file and increments a reference counter of the parent file . Further a uuid of the parent clone file is set to the parent clone inode number of the inode of the parent file .

The file cloning module determines whether the process target file replication source file and the designated clone file are stored in the same volume based on the file path of the process target file replication source file the file path of the designated clone file and the volume management table S . If the process target file replication source file and the clone file are in the same volume S Yes the process of step S is performed.

If the process target file replication source file and the clone file are not stored in the same volume S No the file cloning module examines the uuid table of the parent file and determines whether the virtual parent file is already created within the same volume or not S . If the virtual parent file has already been created S Yes the processes of steps S and thereafter are performed. If it is recognized in step S that the process target file is not the parent file the determination process can be omitted.

If the virtual parent file is not created S No the file cloning module creates a virtual parent file with respect to the parent file S . The file cloning module examines a volume ID B of the parent file from the volume management module and creates a uuid.

Thereafter the file cloning module creates an empty file in the local volume and sets a virtual parent flag bit of the file flag as a virtual parent file .

Thereafter the file cloning module adds a uuid of the parent file to the uuid table of the virtual parent file and adds a uuid of the virtual parent file to the uuid table of the parent file . Thereafter the file cloning module replicates the file attribute of the parent file to the file attribute of the virtual parent file . Lastly the file cloning module increments a reference counter of the parent file and ends the virtual parent file creation process.

If the parent file is in the same volume the file cloning module creates a clone file with respect to a parent file and if not creates a clone file with respect to a virtual parent file S .

The uuid of a parent file is stored in the uuid table of the clone file if the parent file is in the same volume and if not the uuid of the virtual parent file is stored. As for the uuid of the parent file in the same volume it is possible to omit the device ID and to store only the inode number. Further a file attribute of a parent file or a virtual parent file is replicated by the file attribute of the clone file .

Lastly the reference counter of the parent file or the virtual parent file is incremented and the clone file create processing is ended.

Upon receiving a file read request with respect to the clone file the file system module starts the read processing of the clone file S . The file read request includes a file path of the clone file as the processing target and an initial position and length of a file block which is the read target.

The file system module examines a file flag of the inode parent candidate inode shown in uuid within the uuid table of the clone file and checks whether the clone file refers to the parent file or refers to the virtual parent file S . If the virtual parent file is referred to the inode of the real parent file is acquired from the uuid table of the virtual parent file .

If a plurality of parent files are registered in the uuid table the file system module acquires an inode of the parent file corresponding to the subsequent uuid of the previously accessed uuid. The uuid that differs from the previously accessed uuid is selected so as to distribute the access load of the parent file . Thereafter the file system module acquires a block layout table of the parent file from the inode of the parent file .

Next the file system module allocates a buffer area corresponding to the read size in the main memory and acquires an inode of the clone file as the read target from the file path S . Thereafter the processes of steps S through S are performed with respect to the file block included in the read target area.

Next the file system module examines the block layout table of the clone file and checks whether the file block being processed is in a hole or not S . If the file block is in a hole S No the processes of S and thereafter are performed and if not S Yes the processes of S and thereafter are performed.

Thereafter the file system module determines whether the file block of the parent file is in a hole or not based on the block layout table acquired in S S . If the file block of the parent file is in a hole S No zero data is stored in the buffer area and the process of step S is performed.

If the file block of the parent file is not in a hole S Yes the file system module reads a file block of the parent file from the storage device stores the same in the buffer area and performs the process of step S S .

Next the file system module reads the file block of the clone file from the storage device into the buffer area and performs the process of step S S .

Next if an unprocessed file block still remains the file system module returns to step S and processes the next file block S .

Finally the file system module responds the contents of the buffer area to the client server and ends the file read processing S .

When a file write request with respect to the clone file is received the file system module starts a write processing of the clone file S . The file write request includes a file path of the clone file as the processing target an initial position of the file block as the write target and the write data.

The file system module acquires a block layout table of the parent file S . Since the present processing is similar to step S the description thereof is omitted.

Next the file system module stores the write data of S to a reception buffer in the main memory and the processes shown in S through S are performed to each file block as the update target S .

Next the file system module determines whether the write data includes all the data corresponding to 4 KB of the file block S . This is because if the write data corresponds to only a portion of the file block the update must be performed after reading the remaining portion of the file block . If the write data corresponds to only a portion of the file block S Yes the process shown in step S is performed. If not S No the process of step S is performed.

Thereafter the file system module examines whether the file block of the parent file is in a hole or not S . This is a similar process as step S. If the parent file is in a hole S No the process of step S is performed.

Next the file system module reads the file block of the parent file from the storage device into the buffer area S . The present processing is similar to the processing of step S.

Next the file system module reads the write data for the process target file block into the storage device S . Further if the process of S is performed with respect to the process target file block the data having updated a portion of the file block in the buffer area is written.

If there still remains an unprocessed file block the file system module returns to S and processes the next file block S .

Lastly the file system module notifies the client server that the file write operation has completed and ends the file write processing S .

When the file system module receives the delete request of a clone file the module starts a clone file delete processing S . The delete request includes a file path of a clone file which is the processing target.

The file system module examines a uuid table of the clone file being the delete target and acquires an inode of the parent file or the virtual parent file S . Thereafter the file system module deletes a clone file by a similar method as deleting a normal file.

If the inode acquired in S is not a virtual parent file S No the file system module performs the processing of step S and thereafter S .

If the inode acquired in S is a virtual parent file S Yes the file system module decrements a reference counter of the virtual parent file S .

If the reference counter of the virtual parent file is not zero S No the file system module ends the delete processing of the clone file S .

If the reference counter of the virtual parent file is zero S Yes the file system module refers to the uuid table of the virtual parent file acquires the initial uuid as the uuid of the parent file and deletes the virtual parent file S .

If the reference counter of the parent file is not zero S No the file system module ends the delete processing of the clone file S .

If the reference counter of the parent file is zero S Yes the file system module deletes the parent file and ends the clone file delete processing S . The delete processing of the parent file is similar to that of a normal file. At this time the reference counter of the parent file is zero so it is ensured that the parent file does not have a clone file or a parent clone file .

The split processing is used when an access to a clone file completes with an access to another clone file and the performance requirements of the system could not be satisfied. The file cloning module executes the following split processing when a split request of a clone file is received from an upper program.

The file cloning module starts the split processing when a split request with respect to a clone file is received from an upper program S . The split request includes a file path of a clone file which is the target file to be processed.

The file cloning module acquires a block layout table of the parent file S . The present processing is equivalent to step S so the detailed description thereof is omitted.

The file cloning module executes the processing illustrated in steps S through S for all the file blocks including the hole section included in the clone file S .

The file cloning module examines whether the file block being the processing target is in a hole or not in the clone file S . This is a similar process as step S. If the file block being the target of processing is not in a hole S Yes the processing of step S is performed.

The file cloning module examines whether the file block being the target of processing is in a hole or not in the parent file S . This is a similar process as step S. If the parent file is in a hole the process of step S is performed.

The file cloning module reads the file block corresponding to the file block being the target of processing from the parent file and performs a writing process to the clone file S . Thus regarding the file block subjected to processing a file block having the same content as the parent file can be replicated in the clone file .

If an unprocessed file block remains the file cloning module returns to S and processes the next file block S .

Finally the file cloning module performs a subtraction processing of the reference counter of the parent file or the virtual parent file S . This processing is equivalent to steps S through S of the file delete processing illustrated in so the detailed description thereof is omitted.

When a migration command of a parent file is received the file move program performs migration processing of the parent file illustrated below if the parent file does not have a virtual parent file S . The migration command includes a file path of the parent file of the migration source and the file path of the migration destination. The file move program determines based on the file flag of the migration source file that the migration source file is a parent file and that the file does not have a virtual parent file from the uuid table .

The file move program creates a replication of the parent file of the migration source migration source parent file in the migration destination volume S . At this time all the file blocks excluding the hole of the parent file the file attribute and the uuid of the parent clone file set in the parent clone uuid become the target of replication.

The file move program registers a uuid of the replication file created in S in a uuid table of the migration source parent file S . Further a uuid of the migration source parent file is stored in the uuid table of the file replicated in the migration destination.

The file move program substitutes in a reference counter of the file replicated in the migration destination S .

The file move program sets a virtual parent file bit as a file flag of the migration source parent file and sets a parent file bit as a file flag of the file replicated in the migration destination. At this time the migration source parent file becomes a virtual parent file and the file replicated in the migration destination becomes a parent file S .

Finally the file move program performs a freeing process of the disk block with respect to the migration source parent file being set as the virtual parent file and ends the migration processing of the parent file S .

When a migration command of a parent file is received the file move program performs the migration processing of the parent file described below if the parent file has a virtual parent file S . The migration command includes a file path of the parent file of the migration source and the file path of the migration destination. The file move program determines that the file is a parent file having a virtual parent file based on the file flag and the uuid table of the file being migrated. The program also determines that the migration to a different volume is performed based on the migration destination file path.

The file move program creates a replication of the migration source parent file to be migrated to the migration destination volume S . At this time all the file blocks excluding the hole that the parent file has the file attribute the uuid of the parent clone file set in the parent clone uuid the uuid table and the reference counter are the target of replication.

Next the file move program checks the uuid table of the migration source parent file and performs the processes of steps S and S for all the virtual parent files of the parent file to be migrated S .

Next the file move program changes the uuid of the migration source parent file included in the uuid table of the virtual parent file being processed to the uuid of the replication file of the parent file created in S S .

Next if a virtual parent file remains the file move program returns to S and processes the next virtual parent file and if not performs the subsequent processes S .

Lastly the file move program performs a freeing process of the disk block regarding the migration source parent file and ends the migration processing of the parent file S . Further the present invention has illustrated an example in which the parent file of the migration source is deleted but this is merely an example.

By not deleting the parent file of the migration source and leaving the uuid of the parent file of the migration source in the uuid table of the virtual parent file via the control described with respect to it becomes possible to set a replication of one or more parent files in the reference destination of the virtual parent file .

When a migration command of the clone file to a different volume is received the file move program starts the migration processing of the clone file S . The migration command includes a file path of the migration file and a file path of the migration destination. Further whether the migration is to be performed to a different volume or not is determined based on the file path of the migration destination.

Next the file move program issues a clone file create command including a file path of the clone file of the migration source and the migration destination file path which becomes the destination for creating a clone to the file cloning module . Based on the clone file create processing shown in the file cloning module creates a clone file having the same parent file as the clone file of the migration source in the migration destination S . Further the migration destination clone file shares the physical storage data of the parent file in the whole file block and stores data that differs from the migration source clone file .

Next the file move program performs the processes of steps S through S with respect to all the file blocks of the migration source clone file S .

Next the file move program acquires a block layout table of the clone file of the migration source from the file cloning module and checks whether the clone file of the migration source has a file block being processed S . If the clone file of the migration source does not have a file block S No the processes of steps S and thereafter are performed.

Next if the clone file of the migration source has a file block S Yes the file move program reads a file block being processed from the migration source clone file and writes the same into the migration destination clone file S . As a result the file block of the migration source clone file is replicated into the file block of the migration destination clone file .

Next if an unprocessed file block still remains the file move program returns to S and processes the next file block S . If the processing of all the file blocks have been completed the migration source clone file and the migration destination clone file will store the same data.

Next the file move program reads the file attribute of the migration source clone file to change the content of the migration destination clone file to the same contents S .

Finally the file move program deletes the migration source clone file and ends the inter tier migration processing of the clone file S .

A clone management screen is a management GUI for the manager to create clone files and to migrate parent files and clone files .

A checkbox A is a checkbox showing that the operation is for creating a clone file . A textbox B and a textbox C are textboxes for designating a file path of a replication source file and a file path of a clone file to be newly created.

A checkbox D is a checkbox showing that the operation is for migrating a parent file or a clone file . A textbox E is a textbox showing a file path of a migration source parent file or a clone file and the textbox F is a textbox showing a file path of the migration destination.

When the manager clicks an OK button G if the checkbox A is marked the management GUI program issues a clone file create command including the file path of the replication source file and the clone file designated by the file server management program . If the checkbox D is marked the file migration command including the file path of the designated migration source file and the file path of the migration destination is issued to the file server management program .

As described according to the present embodiment creation of a clone file corresponding to different volumes and migration of a parent file and a clone file astride volumes becomes possible. Thereby the parent file and the clone file can be stored in a storage device meeting performance requirements.

Further it becomes possible to create a replication of the parent file and distribute the accesses to the parent file . When the access performance of the parent file becomes a problem the problem can be solved by creating a replication of the parent file . Further by applying the present embodiment a clone file can be created with respect to parent files of different volumes so that it becomes possible to cut down the usage capacity of the storage device .

Further the present embodiment is also applicable to snapshot volumes and backup volumes in addition to normal volumes . For example by designating a past parent file as the reference destination of a virtual parent file the file can be restored even if erroneous operation is performed to the parent file .

Next a file cloning method for cloning files among different storage systems according to a second embodiment of the present invention will be described with reference to .

The hardware configuration of the file storage according to the second embodiment is equivalent to that of the first embodiment so detailed description thereof is omitted. Further the hardware configuration of an external file storage is equivalent to the file storage . The external file storage can use hardware that differs from the file storage . Further the external file storage can be composed of multiple devices. For example a distributed file system such as Ceph can be adopted as the external file storage .

According to the present embodiment a file cloning module provides a means to create a clone file to a parent file existing in a different storage system. Similar to the first embodiment the file cloning module creates a virtual parent file having an identifier uuid for uniquely identifying a parent file with respect to the parent file in a local volume and uses a clone file as the virtual parent file.

Further according to the present embodiment in order to virtualize a parent file with respect to different storage systems a control to issue a quiesced image create command corresponding to the type of the storage system upon creating the virtual parent file a control to store a block layout of the parent file in a block layout table of a virtual parent file and a control to use the uuid astride storage systems are performed. Based on these control it becomes possible to create a clone file in a parent file stored in a different storage system.

Thereby the manager can freely select the storage system for storing the parent file in response to the performance requirements. For example a large number of clone files can be created by storing the parent file in a high performance external file storage . Further since the physical storage data of the parent file and the clone file can be shared astride storage systems it becomes possible to cut down the capacity consumption of the storage device .

The block layout table of the virtual parent file stores a file offset A and a block length C of each file data of the parent file to show the position of the file block of the parent file . In order to acquire the block layout the file system module performs an inquiry processing of the block layout to the external file storage when a clone file is created. A preferable example of the system to be used for the inquiry processing of the block layout is a xfs bmap command of a XFS file system.

A parent file and a parent clone file of the external file storage are created in a similar manner as the first embodiment illustrated with reference to . In the present embodiment a file cloning technique is utilized to create the parent file in the external file storage but this is merely an example. The parent file in the external file storage is merely required to be a quiesced file and it is not necessarily required to have a parent clone file . In addition it is possible to use the snapshot file of the source file being the replication target as the parent file . The other contents are equivalent to the first embodiment described in so the detailed descriptions thereof are omitted.

At this time whether a file block of the external file storage is in a hole or not is determined using a block layout table of the virtual parent file . The management method of file data of each file is equivalent to the management method according to embodiment 1 described with reference to so the detailed description thereof is omitted.

In the device ID A a host name or an IP address of the storage system storing the file is entered. If the file is stored in the same storage system as the storage system having the uuid table the value of the device ID A will be localhost . If the device ID A is not localhost a public path of volume is entered to the volume ID B and a file path within the volume is entered to the file ID.

The public path mentioned here is a character string for the network file service program to access the volume publicated to the access source such as the client server . If the device ID A is localhost contents equivalent to those of the first embodiment illustrated in are entered to the volume ID B and the file ID C.

The type of the storage system being the operation target of command C is entered in the device type A. A combination of vender name and mode number of the storage system can be used for example as the device type A. An operation B is the operation performed by the command C and either create for creating a quiesced file which becomes the parent file or remove for deleting a quiesced file is entered. A command C is a command for performing operation in each storage system. Further the contents being set in the API management table can be set by the developer or vender of the file storage for shipment or can be set by the manager via the management server .

A device ID A is an identifier for uniquely identifying a storage system in a network and stores a host name or an IP address of the external file storage . A user account name and a login password of the external storage are stored in the user ID B and the user password C. An account name and a login password of a manager are stored in the manager ID D and the manager password E.

Also according to the present embodiment the file system module the file cloning module and the file move program processes the file operation request and the migration request with respect to the clone file and the parent file . In the following description the differences of each process from those of embodiment 1 will be described.

The differences according to the present embodiment from the first embodiment in the process of creating a clone file will be described with reference to . Regarding steps S through S included in the clone file create processing of the first embodiment the present embodiment performs different processes for the parent file creation step S and the virtual parent file creation step S. The contents of each process will be described below.

If the replication source file exists in the external file storage the file cloning module uses a parent file create command stored in the API management table to create a quiesced image of the replication source file and sets the same as the parent file .

At first the file cloning module inquires the file server management program of the external file storage to acquire a device type A. If the device type A is entered in the API management table the file cloning module issues a parent file create command to the external file storage and creates a quiesced file of the process target file. The created quiesced file is used as the parent file .

The file cloning module creates a virtual parent file of the parent file created in S. The file cloning module creates a uuid from the volume path of the parent file and a file path within the volume . Thereafter the file cloning module creates an empty file in the volume for creating the clone file sets up a virtual parent file bit as the file flag and sets the file as a virtual parent file .

Next the file cloning module enters a uuid of the parent file in the uuid table of the virtual parent file . Lastly the file cloning module renames the virtual parent file to the uuid of the parent file and migrates the same to a directory dedicated to a virtual parent file such as .virtparent .

Based on the above processes it becomes possible for the file cloning module to create a clone file from the file in the external file storage . Further by checking whether the virtual parent file having the uuid of the parent file as the file name is stored in the directory dedicated for virtual parent files it becomes possible to determine whether the virtual parent file exists in the volume or not.

Next with reference to the difference of the clone file read processing according to the present embodiment from the first embodiment will be described. Regarding steps S to S included in the clone file read processing of the first embodiment the present embodiment performs different processes for the block layout table acquisition step S the hole determination step S and the file data reading step S. The contents of each process will be described below.

If the uuid table of the clone file indicates a virtual parent file having a parent file in the external file storage the file system module acquires the block layout table of the virtual parent file as the parent block layout table. In other case the process equivalent to the first embodiment is performed.

If the parent file is in the external file storage the file system module checks the block layout table of the virtual parent file and examines whether the file block being processed is in a hole of the parent file or not. If a file data including the file block being processed is not included in the block layout table the file system module determines that the file block of the parent file is in a hole and performs the process of S. In other case the process equivalent to the first embodiment is performed so the description thereof is omitted.

If the parent file is in the external file storage the file system module uses the network file client program to read the file data of the parent file corresponding to the file block being processed into a buffer area. At that time the external file storage to be set as the file read target and the file path are acquired from the value of the uuid of the parent file acquired in S. Further when accessing the external file storage the network file client program uses the user ID and the user password shown in the account management table as the user account.

According to the above process it becomes possible for the file system module to read the clone file data from the parent file of the external file storage . The write processing and the split processing of the clone file adds a similar change as the file read processing to the first embodiment so the description thereof is omitted. The delete processing of the clone file is equivalent to the delete processing of the clone file within the volume as illustrated in except for the point that the present embodiment does not include steps S and S and the point that the delete command stored in the API management table is used for deleting the parent file in S so the description thereof is omitted. Further according to the second embodiment a single parent file is created to correspond to a single virtual parent file so that the reference counter will not be operated and the parent file will be deleted when the virtual parent file is deleted.

The migration processing of the parent file not having the virtual parent file to the external file storage is equivalent to the first embodiment except for the points that the present embodiment does not perform the operation of the uuid table of the parent file performed in step S and the operation of the reference counter for the migration destination parent file performed in step S of so the descriptions thereof are omitted.

Further the migration processing of the parent file having the virtual parent file to the external file storage is realized by sending a parent file pointer change command to the file storage when the client server or the external file storage performs the migration processing of the parent file .

The file cloning module starts a parent file pointer change processing when a parent file pointer change command is received S . Further the parent file pointer change command includes a uuid of the parent file prior to migration and a uuid of the parent file of the migration destination.

Next the file cloning module checks whether the virtual parent file of the migration source parent file is stored in the file storage S . This is determined based on whether a virtual parent file having a uuid of the migration source parent file as the file name exists in the directory dedicated to the virtual parent file. If there is no virtual parent file the parent file pointer change processing is ended.

Next the file cloning module confirms that the contents of the migration destination parent file and the migration source parent file correspond based on the uuid of the migration source parent file by confirming the file data of both files S . This is performed so as to prevent the clone file from referring to a parent file having different data and storing a different data when the reference destination of the parent file is switched. If the data of the migration source parent file and the migration destination file do not correspond the parent file pointer change processing is ended.

Next the file cloning module acquires a virtual parent file using the file path checked in step S S .

Lastly the file cloning module rewrites the uuid table of the virtual parent file and changes the uuid of the migration source parent file to the uuid of the parent file of the migration destination. Thereafter the file cloning module performs processing to change the file name of the virtual parent file to the uuid of the migration file and ends the parent file pointer change processing S .

Next the difference of the present migration processing of the clone file with respect to the first embodiment will be described with reference to . In order to migrate a clone file to the external file storage the file move program issues a clone file create command of step S to the external file storage of the migration destination.

The file move program performs a write processing to a migration destination clone file in step S using the network file client program . By changing the above step the file move program realizes migration of the clone file to the external file storage .

A textbox A is a textbox for entering a host name of an external file storage being the edit target and corresponds to the device type A. A textbox B and a textbox C are textboxes for entering a user account and a password of the external file storage to be added which correspond to the user ID B and the user password C.

A textbox D and a textbox E are textboxes for entering a manager account and a password of the external file storage to be added which correspond to the manager ID D and E.

When the manager enters an OK button F the management GUI program notifies the setting contents to the file server management program and reflects the same in the account management table . When the manager clicks a Cancel button G the setting contents are cancelled.

As described the present embodiment enables to create a clone file in a different storage system and to migrate the parent file and the clone file astride storage systems. Thereby it becomes possible to store the parent file and the clone file in a storage system matching the performance requirements. Further since the physical storage data of the parent files and the clone files can be shared among storage systems the use capacity of the storage device can be reduced.

Next a file cloning method having a de duplication function according to a third embodiment of the present invention will be described with reference to .

The overall configuration of the third embodiment is equivalent to the first embodiment so the description thereof is omitted.

The hardware configuration of the third embodiment is equivalent to the first embodiment so the description thereof is omitted.

A file server executes a de duplication program . The de duplication program performs a process to find duplication files having corresponding file data shares the physical storage data between the duplication files and frees the physical storage area of the duplicated data.

The sharing of physical data between the duplication files is realized by creating a parent file and a parent clone file from one of the duplication files and setting the other duplicated file as the clone file of the parent file . By performing the de duplication processing of the de duplication file the physical storage data can be shared among files and the usage capacity of the storage device can be reduced.

The storage device has a file hash table for each volume . The file hash table stores a set of the file path and the hash value of the parent file within the volume which is used by the de duplication program for detecting duplicated files.

In the present embodiment a de duplication processing of the file duplicated astride volumes is performed. In contrast to the prior art de duplication processing that has been performed within a single volume the target of de duplication is expanded to a plurality of volumes by adding a file cloning technique astride volumes described in embodiment 1 and an inter volume duplication file detection processing. Compared to the prior art de duplication within a single volume the present embodiment enables a greater number of files to be de duplicated so the capacity reduction effect is enhanced.

The file management method and the file request processing method according to the present embodiment is similar to those of the first embodiment. Therefore only the newly added de duplication processing will be described.

If the file data of a certain file is the same as that of a different file the hash value thereof is also the same. Therefore by performing comparison processing of only the files having corresponding hash values during searching of duplication files the duplication files can be detected at high speed.

The de duplication program performs the processes shown in S through S with respect to a normal file matching a policy determined in advance within the volume S . One preferable example of a policy is that final update time has elapsed a certain period of time . Next the de duplication program calculates a hash value of the file being processed S .

The de duplication program checks whether a hash value corresponding to the hash value computed in S is stored in a file hash table or not. If a parent file having the same hash value exists the de duplication program performs comparison of file data such as size comparison and binary comparison and determines whether file data is duplicated or not S . If a parent file having a duplicated file data is found S Yes the de duplication program performs the processing of step S and if a parent file having a duplicated file data is not found S No the processes of steps S and thereafter is performed.

If a parent file having duplicated file data is found S Yes the de duplication program creates a clone file of the parent file found in S and replaces the file being processed. Thereafter the file being processed is deleted and the capacity used by the processed file is freed S . Thereafter the de duplication program performs the processing of S.

If a parent file having duplicated file data is not found S No the de duplication program creates a quiesced image of the file being processed as a parent file and migrates the same to a directory dedicated to parent files .master directory . Thereafter a clone file of the migrated parent file is created and the file is replaced with the file being processed. Then the de duplication program deletes the file being processed S .

Next the de duplication program registers a hash value calculated in step S and a file path of a parent file created in S to a file hash table S .

Finally if a process target file still remains the de duplication program returns to S and performs the processing of the next file and if not the de duplication processing is ended S .

The de duplication program compares the file hash table of two volumes and checks whether a parent file having duplicated hash value exists or not. If there is a parent file having the same hash value comparison of file data of the parent files is performed to determine whether the file data is duplicated or not S .

Next the de duplication program performs the processes illustrated in S through S to duplicated parent files among volumes found in S S .

Next the de duplication program selects one parent file out of the two duplicated parent files found in S as a target parent file and records the uuid of the other parent file in the uuid table of the target parent file S .

Thereafter the de duplication program sets a virtual parent file bit of the file flag of the target parent file and sets the same as a virtual parent file . At that time the reference counter of the other parent file is incremented S .

Lastly if a process target file still remains the de duplication program returns to S and performs the processing of the next file and if not the de duplication processing is ended S .

As described according to the present embodiment it becomes possible to eliminate duplicated files astride volumes. Thereby it becomes possible to share the physical storage data of the duplicated files among volumes and the effect of reducing the storage device usage can be enhanced compared to the de duplication processing performed within a single volume.

By combining the present embodiment and the second embodiment it becomes possible to perform de duplication astride storage systems. In that case the effect of reducing the storage device usage can be further enhanced.

As described the manager can store the parent file and the clone file in a storage device that meets the performance requirements. Further since the physical storage data of the replication source file and the clone file can be shared astride volumes and storage systems the storage device usage can be reduced further compared to the prior art cloning technique.

