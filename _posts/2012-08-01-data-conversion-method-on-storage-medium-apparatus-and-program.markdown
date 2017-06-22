---

title: Data conversion method on storage medium, apparatus and program
abstract: In a data conversion auxiliary module which is at a higher level than a file system in a disk management hierarchy, data stored in a storage medium, which becomes an object, is successively accessed. Then, a data conversion module captures a sector-unit access request to a device driver from the file system, converts data of a sector which is returned from the device driver, and writes the conversion data in the sector. Thereby, data conversion can be executed on a specific region of the storage medium, which is associated with the data in the storage medium.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09330712&OS=09330712&RS=09330712
owner: Humming Heads Inc.
number: 09330712
owner_city: Tokyo
owner_country: JP
publication_date: 20120801
---
This application is a continuation of U.S. application Ser. No. 12 491 865 filed Jun. 25 2009 which is a Continuation Application of PCT Application No. PCT JP2008 050907 filed Jan. 23 2008 which was published under PCT Article 21 2 in Japanese. The entire disclosures of these applications are hereby incorporated by reference herein.

This application is based upon and claims the benefit of priority from prior Japanese Patent Application No. 2007 039969 filed Jan. 24 2007 the entire contents of which are incorporated herein by reference.

The present invention relates to data conversion of a storage medium and more particularly to a data conversion method of a specific area of a storage medium which is associated with data in the storage medium an apparatus and a program.

Methods for converting data in a storage medium in a decryptable format in anticipation of e.g. a theft of a storage medium such as a hard disk include a method of encrypting data by using an encryption algorism or the like. The encryption generally falls into two categories i.e. file encryption and disk encryption.

In the file encryption encryption is executed in units of a file or a folder in an application layer on an operating system OS .

On the other hand in the disk encryption encryption is executed in units of a sector at a lower level than a file system. In general the entire disk is encrypted. The disk encryption is more advantageous than the file encryption in the case where the data in the disk is to be encrypted regardless of an operation user s intension or in the case where the processing speed is taken into account.

As described above in the conventional disk encryption the object of encryption is the entire disk. Consequently a long time about several hours is needed when initial encryption is executed from a non encrypted state and in a case where the disk has a defect there is such a problem that the initial encryption fails to be finished. In addition while the initial encryption is being executed there is such inconvenience that the associated computer terminal is not usable for work.

As a measure for avoiding such problems it is thinkable that only a necessary region which is used by data in the storage medium that meets a specific target condition is set as an object of encryption while making use of the advantage of the disk encryption for example by encrypting only an actually used region. However since the disk encryption is executed in the process at the lower level than the file system at which level there is no concept of files the conventional disk encryption is unable to selectively encrypt the region which is associated with data in the storage medium such as a file.

In general disk management in the OS is conceptually hierarchized and a data access request which is conceptually at a higher level than the file system such as data access to the storage medium from an application is decomposed into sector unit requests at a lower level than the file system.

In the present invention in addition to a module which executes data conversion at a lower level than the file system in the concept of hierarchy of disk management a data conversion auxiliary module for specifying a disk region which becomes an object of data conversion is provided at a higher level than the file system.

If the data conversion auxiliary module has accessed and read data in the storage medium in a region in which data conversion is to be executed the file system which has received the data access request refers to disk management information decomposes the read request for reading the data in the storage medium into requests in units of a sector that is used by the data in the storage medium and sends the request to a device driver.

The data conversion module captures the sector unit read request from the file system to the device driver stores the read destination sector number and transfers the process to the device driver. The data conversion module converts the data of the sector which is returned from the device driver in a decryptable format by using an encryption algorithm or the like writes the conversion data in the sector and returns the process to the file system.

By successively accessing and reading the data in the storage medium that is the object of data conversion in the data conversion auxiliary module it becomes possible to execute data conversion of a specific region of the storage medium which is associated with the data in the storage medium.

In addition by setting the degree of operation priority of the process of the data conversion auxiliary module in the OS the degrees of operation priority between the data conversion process and the process of some other application can be balanced.

Specifically according to a first aspect of the present invention there is provided an information processing apparatus comprising data access means provided at a higher level than a file system in a disk management hierarchy for executing data read access for reading out data stored in a storage medium capturing means provided at a lower level than the file system for capturing data of a sector which is read out by a sector unit data read access request to a device driver the data read access request being generated from the file system by the data read access data conversion means for encrypting the captured data of the sector and data write means for writing the encrypted data of the sector in the sector of the encrypted data.

As shown in in the information processing apparatus a CPU a memory an input unit and a storage medium are connected to a bus .

The CPU cooperates with a first encryption decryption program and a second encryption decryption program which are stored in the storage medium thereby executing a data conversion process according to the embodiment of the invention and executing overall control of the information processing apparatus .

The memory is used as a work area which is needed at the time of executing the first encryption decryption program and the second encryption decryption program .

The input unit is an interface for inputting data for specifying data which is to be subjected to the data conversion process and is for instance a keyboard or a touch panel.

The storage medium stores programs and data which are needed in the data conversion process according to the embodiment of the invention and is for instance a hard disk drive HDD or a USB memory.

The storage medium stores the first encryption decryption program an OS operating system the second encryption decryption program and a device driver .

The first encryption decryption program is a program at an application level which is higher than a file system and controls the data conversion process at the application level according to the embodiment of the invention.

The first encryption decryption program includes a data conversion auxiliary module . The data conversion auxiliary module operates at a higher level than the file system in the disk management hierarchy specifies a storage medium region that is an object of data conversion and executes data read access for reading data in the storage medium and data write access for writing data in the storage medium.

The OS includes an API Application Programming Interface which is an interface with the file system for file management of the storage medium and with application programs. These file system and API are publicly known art.

The second encryption decryption program is a driver of a lower level concept than the file system and controls the data conversion process according to the embodiment of the invention at a lower concept level than the file system.

The data conversion module operates at a lower level than the file system and executes processes such as data conversion and write of write data in the storage medium .

The data conversion module includes a data conversion information table . The data conversion information table stores in a correlated fashion sector numbers of the storage medium data conversion object flags which indicate whether sectors are objects of data conversion or not and data conversion flags which indicate whether data is encrypted or not.

The setting read in unit reads in the setting of objects and conditions of data conversion. The methods of the setting include for example a method in which setting is executed by a setting file and the setting file is read in a method in which setting is input from a user interface and a method in which setting is executed by another machine such as a server machine by communication and is read in.

Examples of the object of setting are as follows. As regards the selection of object regions of data conversion examples of the object regions include a region which is used by data in the entire storage medium a region of data in the storage medium which is used or not used by the OS a region of data in the storage medium which is used or not used by a specific application a region of specific data in the storage medium or a region of a storage location of the data and a region of data in the storage medium in a specific drive. Examples of the conditions include the kind of storage medium such as a computer terminal a built in hard disk a USB memory or a USB hard disk which is discriminated by a machine name a MAC address or an IP address the kind of disk management method e.g. FAT File Allocation Table and the distinction as to whether the apparatus is a mobile PC or not.

The disk management information acquisition unit scans disk management information such as file system information and partition information and selects according to the setting data in the storage medium which becomes the object of data conversion. In addition where necessary for example in the case where an additional data conversion region is designated sector numbers which are used by the data in the storage medium are acquired on the basis of the disk management information.

The data access unit accesses via the API Application Programming Interface and file system of the OS the data in the storage medium which is set to be the object of data conversion by the disk management information acquisition unit and reads in the data stored in the storage medium. The access to the device driver from the file system is executed in units of a sector.

The data conversion region transmission unit where necessary for example in the case where an additional data conversion region is designated transmits the sector number which is acquired by the disk management information acquisition unit and is used by the data in the storage medium to the data conversion module via the API and file system of the OS .

The access request capturing unit captures a sector unit or cluster unit access request to the device driver from the file system . In the case where the access request is a data read access request the data that is read out by the data read request is captured.

The object sector memory unit stores the sector number of an access destination when the access request from the file system to the device driver has been captured.

The data conversion unit executes data conversion encryption on the read out data which is sent from the device driver back to the file system . In addition in the case where the read out data is encrypted a decryption process of the data is also executed.

The data write unit issues to the device driver an instruction to write conversion data encrypted data to the sector that is stored in the object sector memory unit . In addition at the time of data decryption of the storage medium the data write unit similarly issues to the device driver an instruction to write decryption data.

The data conversion information table as shown in is a table for managing with respect to each sector number whether the associated sector is an object of data conversion and whether data of the associated sector has been subjected to data conversion. In as regards data conversion object information 1 indicates an object and 0 indicates a non object. As regards data conversion information 1 indicates a data converted state and 0 indicates a non data converted state.

The data conversion region reception unit where necessary for example in the case where an additional data conversion region is designated receives sector number information of a data conversion object which is transmitted from the data conversion auxiliary module and reflects this information on the data conversion object flag of the data conversion information table . Specifically 1 is set in the case of the object of encryption.

The data conversion unit sets 1 which indicates the object of encryption in the data conversion object flag corresponding to the sector number which has been accessed. In addition in the case where the data which has been encrypted by the data write unit is written at the sector number which is accessed the data conversion unit sets 1 which indicates the encrypted state of data in the data flag corresponding to this sector number.

In the case where decryption of the storage medium is executed the data conversion unit sets 0 in the data conversion flag corresponding to the sector in which the decrypted data is written.

Next referring to flow charts of and a description is given of the operation at the time of executing initial data conversion from the state in which no data conversion is executed in the storage medium.

If the initial data conversion process is started the data conversion auxiliary module first reads in the settings of e.g. the data conversion object and condition by the setting read in unit .

Subsequently the disk management information is scanned and with respect to all data in the storage medium it is determined whether the data is the data conversion object which meets the setting condition that has been read in by the setting read in unit . In the case where the data in the storage medium meets the setting condition object condition of data conversion the data access unit executes data access read access to the storage medium. If the data in the storage medium fails to meet the setting condition object condition of data conversion no data access is executed to the storage medium.

In this process in S it is determined whether the data is the last data of scan of the disk management information.

In the case of the last data in S the process ends in S and thus the initial data conversion process is finished.

In the case of not the last data in S the information of the next data in the storage medium is acquired in S.

In S the information of the data in the storage medium which is acquired in S is compared with the setting condition that is read in by the setting read in unit and it is determined whether the data is the object of data conversion.

If it is determined in S that the data in the storage medium is the object of data conversion the API is used in S to access the data in the storage medium and executes read in of the data in the storage medium.

If it is determined in S that the data in the storage medium is not the object of data conversion data access to the storage medium is not executed and the process returns to S.

In the case where the data conversion region information is transmitted to the data conversion module where necessary for example in the case where an additional data conversion region is designated the data conversion region transmission unit transmits the sector number which is used by the data in the storage medium to the data conversion module via the API instead of executing data access to the storage medium in S of the above described process.

The transmission of the data conversion region information to the data conversion module is executed in the case where it is more advantageous for the data conversion module to execute data conversion or decryption of conversion data on the basis of the pre transmitted data conversion object information .

Instead of transmitting the data conversion region information each time as described above the information may be stored in the memory and the information may be transmitted at a time to the data conversion module

In the case where the data conversion auxiliary module has executed data access to the storage medium in the above described process the file system driver which has received the data access request for data access to the storage medium refers to the disk management information decomposes the access request to the data in the storage medium into sector units that are used by the data in the storage medium and sends the access request to the device driver .

The data conversion module captures the sector unit access request from the file system to the device driver stores the access destination sector in the object sector memory unit and transfers the process to the device driver . The data conversion module further captures the data that is read out from the device driver converts encrypts the captured data of the sector and issues to the device driver a request for writing the conversion data in the sector. Furthermore the flag relating to the sector of the data conversion information table is set to 1 data converted state and the process is returned to the file system

In the above described process in S the access request capturing unit captures the sector unit access request from the file system to the device driver .

In S the access destination sector is stored in the object sector memory unit . The data conversion unit sets 1 which is indicative of the object of conversion in the data conversion object flag corresponding to the accessed sector number in the data conversion information table .

In S the data conversion unit converts encrypts the data of the sector which has been returned. As the data conversion method use may be made of an encryption algorithm which is generally made public.

In S the data write unit issues to the device driver a request for writing the converted data into the sector that is stored.

In S the data conversion unit sets 1 data converted state in the flag corresponding to the sector in the data conversion information table .

As has been described above by the cooperation of the data conversion auxiliary module and data conversion module the initial conversion process from the state of the storage medium in which data conversion is not executed can be executed.

Instead of the process method illustrated in use may be made of a method of successively executing data conversion on the sectors with respect to which the data conversion object flag is 1 data conversion object .

In the case of decrypting the converted data on the storage medium the data conversion information table is referred to in the data conversion module . If the flag of the data conversion information is 1 the data of the associated sector number is decrypted and the decrypted data is written in the storage medium. By successively executing this operation by scanning the sector numbers of the data conversion information table data decryption on the storage medium can be executed.

In the meantime if the degree of priority of the process of the data conversion auxiliary module is set in the OS the degree of priority of the initial data conversion process can be adjusted. In the case where the initial data conversion process is to be completed in a shortest possible time the degree of priority of the process of the data conversion auxiliary module is set at a high level and the degree of priority of the initial data conversion process is increased.

Conversely in the case where the initial data conversion is to be executed while some other application is being executed even if a longer time is consumed the degree of priority of the process of the data conversion auxiliary module is set at a low level and the degree of priority of the initial data conversion process is lowered.

The present invention is not limited to the above described embodiments. At the stage of practicing the invention various modifications may be made without departing from the spirit of the invention. The embodiments may properly be combined and implemented as much as possible and in such cases advantageous effects as combined can be obtained. Further the embodiments include various inventions at various stages and various inventions may be derived by properly combining structural elements disclosed in the embodiments. For example in the case where an invention is derived by omitting some structural elements from all the structural elements disclosed in the embodiments and the derived invention is implemented the omitted parts are properly supplemented by well known art.

By the above described invention data conversion can be executed on a specific region of a storage medium which is associated with data in the storage medium. Thereby data conversion of a necessary region of the storage medium can be executed at high speed without being affected by for example a defect of a disk and the security of the storage medium can be made stronger.

In addition by making adjustable the degree of operation priority of the process for executing data conversion it becomes easier to make use of some other application while executing the data conversion.

