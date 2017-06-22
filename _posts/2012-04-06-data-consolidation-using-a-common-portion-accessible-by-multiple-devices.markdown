---

title: Data consolidation using a common portion accessible by multiple devices
abstract: Multiple devices are provided access to a common, single instance of data and may use it without consuming resources beyond what would be required if only one device were using that data in a traditional configuration. In order to retain the device-specific differences, they are kept separate, but their relationship to the common data is maintained. All of this is done in a fashion that allows a given device to perceive and use its data as though it was its own separately accessible data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08706935&OS=08706935&RS=08706935
owner: DataCore Software Corporation
number: 08706935
owner_city: Fort Lauderdale
owner_country: US
publication_date: 20120406
---
The present invention relates to data consolidation and more specifically to data consolidation using a common portion that is accessible by multiple devices. At the same time device specific portions are maintained according to modifications to the common portion that are made by individual devices.

According to one example the present invention provides data consolidation using a common portion that is accessible by multiple devices while maintaining device specific portions according to modifications to the common portion that are respectively made by individual devices.

Multiple devices are provided access to a common single instance of data and may use it without consuming resources beyond what would be required if only one device were using that data in a traditional configuration. In order to retain the device specific differences they are kept separate but their relationship to the common data is maintained. All of this is done in a fashion that allows a given device to perceive and use its data common with device specific modifications as though it was its own separately accessible data.

For example in one embodiment a storage domain server presents storage to tens hundreds or even thousands of devices. The common portion can be retained in a cache layer of the storage domain server a single time rather than repeating the common portion for each device. The device specific portions may be retained in cache as well but their size will be relatively small as compared to the common data portion. This is efficient because it conserves cache resources. At the same time it allows the devices to access their data in a cache responsive fashion rather than requiring them to page underlying physical storage resources e.g. hard disks for storage requests.

The present invention can be embodied in various forms including business processes computer implemented methods computer program products computer systems and networks user interfaces application programming interfaces and the like.

In the following description for purposes of explanation numerous details are set forth such as flowcharts and system configurations in order to provide an understanding of one or more embodiments of the present invention. However it is and will be apparent to one skilled in the art that these specific details are not required in order to practice the present invention.

The present invention reduces the need for trading memory and storage capacity for bandwidth when managing multiple computing systems of identical or similar type by creating a single copy of data for the multiple computing systems. Notwithstanding this sharing the single copy is perceived by any of the individual computing systems as though it controls and accesses its very own unique copy of data. Modifications of the data by the individual computing systems are managed as unique to each system.

In one example the data is presentable to a given device as a definable discrete image such as a virtual disk. There the given device accesses the virtual disk as its own unique storage with the virtual disk representing the underlying common portion and device specific portion.

Accordingly one or more embodiments of the present invention provide data consolidation using a common portion that is accessible by multiple devices while also maintaining updatable device specific portions each representing modifications to the common portion made by individual devices. Multiple devices are provided access to a common single instance of data and may use it without consuming resources beyond what would be required if only one device were using that data in a traditional configuration. In order to retain the device specific differences they are kept separate but their relationship to the common data is maintained.

Operating systems such as Windows OS and business applications such MS Outlook and web browsing are some examples of data that does not change much from device to device. These cases are suitable examples wherein a single copy of the data may reside in cached memory to the benefit of multiple computing systems. The sets of changed data corresponding to the single copy of data would be potentially equal to the number of computing systems but these changes would be relatively small and require less usage of storage resources. It should also be noted that the common portion does not need to represent all of the possible data in any given example. For example with an OS there may be a smaller working set portion of the OS that is configured as the common portion of data rather than the entire OS.

For example in one embodiment a storage domain server presents storage to tens hundreds or even thousands of devices. The common portion can be retained in a cache layer of the storage domain server a single time rather than repeating the common portion for each device. The device specific portions may be retained in cache as well but their size will be relatively small as compared to the common data portion. This is efficient because it conserves cache resources. At the same time it allows the devices to access their data in a cache responsive fashion rather than requiring them to page underlying physical storage resources e.g. hard disks .

One example of maintaining the relationship between the common data and the device specific differences uses representations of the state of consolidated data. A given device perceives and accesses consolidated data that consists of the common data and a device specific portion i.e. the changes to the common data made by the given device . A representation of the state of the consolidated data maintains an association between the common data and the device specific data.

In one example the consolidated data may be presented as virtual disks. For any given device a particular virtual disk may be presented. The particular virtual disk the consolidated data presents the common data and the device specific data to the given device as one accessible unit. A representation of the state of the virtual disk maintains the relationship between the common data and the device specific data. In one example representation of the state of the virtual disk uses a snapshot of the virtual disk.

The person of ordinary skill in the art will readily recognize alternative implementations. Various alternative state representations may be used in lieu of snapshots. Additionally any copy on write scheme may be used to separately manage the common portion and device specific portions.

According to another aspect the common data may be predetermined meaning that it is known common data that will be used by various devices in a system. This common data may be represented as a predetermined common data image which may also be referred to as a golden image.

Normally the predetermined common data would be deployed and separately represented for each user i.e. in each of the numerous disks . In lieu of this numerous devices such as application servers can access the single predetermined common data image. Examples of the predetermined common data include but are not limited to an OS a boot sequence and applications.

According to another aspect Virtual Machines are represented with the common portion being a common Virtual Machine image. Thus for example a VM Image can be booted from the single common VM image.

Any conventional connections may be used between the SDS and the application servers as well as to the physical storage resources . Additionally any conventional computing platforms and processing resources may be used for the application servers as well as for the SDS . The SDS also includes its own memory resources e.g. RAM or flash memory that may be used to perform caching operations that are further described herein.

The data consolidation module contains instructions that are executed by the SDS to carry out the application data consolidation functionality described herein. Specifically in one embodiment the data consolidation module provides data consolidation wherein an instance of a common portion of data is accessible by multiple devices. The data consolidation module maintains a relationship between the common data and device specific portions of data that are respectively accessible by individual ones of the data devices. This provides access to the instance of the common portion of data by the data devices without requiring replication of the common portion of data while also facilitating modifications to the common portion of data maintained by the respective device specific portions.

The data consolidation module is preferably provided as software but may be alternatively provided as hardware firmware or any combination of hardware firmware and or software. Additionally the program code for the data consolidation module may be stored on a non transitory computer readable medium memory including but not limited to a hard disk an optical disk a flash memory or any computer readable memory in which the program code may be stored.

The data consolidation module further includes a representation layer and a data layer which in certain embodiments may be a cache layer.

The storage domain server may also be configured to include a virtualization layer for presenting virtual disks to the application servers and for providing corresponding functions such as thin provisioning of storage resources as well as any necessary access allocation and correlation to the physical storage resources. For example the virtualization layer may present virtual disk App1 to Application Server1 and virtual disk App2 to Application Server2.

The representation layer maintains representations associating device specific and common data portions in the context of the virtual disks. For example Rep App1 is a representation of a virtual disk App1 presented to Application Server 1 and Rep App2 is a representation of a virtual disk App2 presented to Application Server 2 and so on through Rep App N which corresponds to Application Server N. As noted these servers may number in the 1000s or more.

Each of these representations maintains an association between the common data and device specific portions. Rep App1 includes device specific portion and common data portion Rep App2 includes device specific portion and common portion and so on through Rep App N having common portion and device specific portion

Typically the representation layer does not store the data itself but instead maintains representations of the data such as metadata that organizes the data that is actually stored elsewhere.

The data layer stores the data. Specifically the data layer stores the Common Data which is the common data referenced in the representations and . The Common Data is stored once but is used numerous times. The device specific data are also stored in the data layer . Thus the data layer stores only one instance of the Common Data and the relatively small amounts of device specific data denoted Data App1 Data App2 and Data App N.

The data layer may be a cache layer with corresponding physical storage resources providing the underlying physical storage for the cache.

Although the device specific portions Data App1 Data App2 and Data App N appear to be of similar size in the figure it is noted that they will often have different sizes. For example there may be an instance where one device App1 uses most or all of the Common Data without making any changes whereas another device e.g. App2 makes a lot of changes to the Common Data . In that situation the device specific portions for the two devices will differ in size. This being the case one device may use less of the Common Data than another device. It is also noted that excessive modifications by one device would not defeat the overall efficiencies of the approach as there may still be many devices still using the most or all of the Common Data in unchanged form.

The storage domain server includes a data consolidation module with a virtualization layer a representation layer and a data layer e.g. a cache layer .

The virtualization layer includes instructions for presenting virtual disks to the application servers and for providing functions such as thin provisioning of storage resources as well as any necessary access allocation and correlation to the physical storage resources. Additional features such as interfaces for defining and assigning storage pools determining quality of service parameters and other features of the SDS may also be provided and need not be described herein.

The virtualization layer presents a virtual disk App1 to Application Server 1 a virtual disk App2 to Application Server 2 and a virtual disk App N to Application Server N.

The data consolidation module generates and manages representations corresponding to the virtual disks or other data presented to the application servers .

Although any type of data representation of the state of the virtual disks may be implemented in one example the representations are snapshots of the disks. Any number of snapshots may be created including more than one for a given application server but for ease of discussion Snap App1 is a snapshot of a virtual disk App1 presented to Application Server 1 and Snap App2 is a snapshot presented to Application Server 2 and so on through Snap App N which corresponds to Application Server N.

A snapshot may also be referred to as a point in time volume as a snapshot entails creation of a point in time representation of the data in the presented disk. A copy on write snapshot scheme may for example be implemented. There when the snapshot is created metadata about where original data is stored is copied. It is not necessary to physically copy the data for the snapshot when it is created so creating the snapshot can be done very quickly and efficiently.

For each snapshot the representation layer tracks changes following the snapshot s creation. When a write to a given chunk occurs the original data for that chunk is copied from the source and saved in association with the snapshot before the original source data is overwritten. Reads of the source are directed to the source or to a corresponding cache sitting above the source . Reads of the snapshot are directed either to the source if the corresponding chunk has not changed or to the copied chunks associated to the snapshot if those chunks have changed.

It should be noted that chunks is a unit amount of storage that will typically be an integer number of blocks i.e. 1 or more blocks . The size of the chunks may be made as desired noting that a smaller size definition e.g. one block may produce the least waste e.g. a write to a block causes just that one block to be moved to storage in association with the snapshot but also produce the most instances of computational overhead for moving chunks around.

In examples where snapshots are used they may also be updated to change the point in time to a current time and migration schemes may be used to migrate blocks to the original source.

Referring to along with in the representation layer each snapshot is shown as including a common data portion and a device specific portion. For example Snap App1 includes device specific portion and common data portion Snap App2 includes device specific portion and common data portion and so on through Snap App N having common data portion and device specific portion

When a snapshot is created it may just include metadata because no changes have yet been made. When changes are made they are tracked in the metadata as well which allows reads and writes to be appropriately directed such as to the original source or to the specific portion of the snapshot e.g. if the snapshot is being read and the read is to a block that has changed since the snapshot has taken the read is to the specific portion corresponding to the snapshot which is where the original source data is written . Thus although the common data portion is repeatedly shown in the representation layer it is not actually stored repeatedly.

In the data layer there are device specific caches as well as a cache for the common data Common Data .

The size of these caches may or may not be perfectly coincident with the corresponding storage in the physical storage resources . That is for a relatively small cache size there may be more data in the physical storage than can be maintained in the cache. Additionally in an initial instantiation of the consolidation technique the snapshots are just metadata and the cache may simply be reserved. As reads are performed the used portion of the cache can gradually build by pulling blocks up from the physical storage.

It should also be noted that the specific portions of each snapshot need not necessarily have a perfectly coincident storage in the cache as well. That is the device specific data may be stored in memory other than the cache memory or the device specific data may be represented somewhat but not entirely in the cache.

For the read operation it is determined whether the chunk corresponding to the read has already been written since the snapshot Snap App x was taken. If it has then a copy on write has already been performed so to obtain the current state of the data the source volume is simply read alternatively to access the original data aka reading the snapshot the read would be to the device specific data retained in Data App x step .

If on the other hand it is determined that the chunk corresponding to the read has not already been written since the snapshot was taken then the read may be made from the common data store Common Data . Where a cache of the common data is implemented this read may be made directly from the cache or the cache may be built if the chunk corresponding to the read is not yet resident in the cache. The cache Common Data is thus automatically populated to contain the data that is hot for the various individual volumes.

For the write operation it is determined whether the corresponding chunk of Snap App x has already been written since the snap was taken. If so then the original data has already been retained in the device specific store so the write can simply be made to App x source . If not then the original source chunk from the App x source is initially copied to the device specific store Data App x prior to writing to the App x source.

The SDS similarly includes a virtualization layer not shown in as well as a data consolidation module representation layer and data layer .

Here the virtualization layer again provides for virtual disk App1 with respect to Application Server 1 and virtual disk App2 with respect to Application Server2.

The data consolidation module implements the representation layer to generate and maintain representations of the consolidated data which may also be referred to as state representations. For ease of discussion Rep App1 is a representation of a virtual disk App1 presented to Application Server 1 and Rep App2 is a representation of a virtual disk App2 presented to Application Server 2 and so on through Rep App N for virtual disk App N which corresponds to Application Server N.

In one example the state representations may be generated and maintained using snapshot technology. When the snapshots are created metadata about where original data is stored is copied. It is not necessary to physically copy the data for the snapshot when it is created. Snapshots are not necessary though and any state representation may be used.

For each state representation the representation layer tracks changes following the state representation s creation. When a write to a given chunk occurs the original data for that chunk is copied from the source and saved in association with the state representation before the original source data is overwritten. Reads of the source are directed to the source or to a corresponding cache sitting above the source . Reads of the state representation are directed either to the source if the corresponding chunk has not changed or to the copied chunks associated to the state representation if those chunks have changed.

In the representation layer each representation of the virtual disks respectively includes the common portion and a device specific portion. However in this instance the common portion is a predetermined common data image. For example Rep App1 includes device specific portion and the predetermined common data image portion Rep App2 includes device specific portion and the predetermined common data image portion and so on through Rep App N having the predetermined common data image and device specific portion .

In the data layer cache layer there are device specific caches as well as a cache for the predetermined common data image .

In a fashion similar to the embodiment of in this embodiment at origination the state representations include only the necessary metadata according to their initial definition. As writes are made to the corresponding volumes the copy on write scheme is preferably used wherein the source data is written to the device specific portion prior to writing the data to the source. Similarly reads are passed straight to the consolidated portion.

In contrast to the embodiment of where the consolidated data Common Data is populated as a result of reads in this embodiment the predetermined common data image data Data Common Image may preferably be fully populated in the cache in the first instance. This is because the predetermined common data image may be a known data element that will be used repeatedly for the various application servers in the enterprise. This embodiment offers both the economy of storing one instance of the predetermined common data image while also preserving the flexibility of coherently defining and updating additional device specific data for any given application server.

An IO request is received and may correspond to any of the volumes presented by the SDS generically referenced as volume App x. The representation Rep App x and a corresponding device specific data store Data App x and the predetermined common data image data Data Common Image correspond to Application Server x.

For the read operation it is determined whether the chunk corresponding to the read has already been written since the representation Rep App x was instantiated. If it has then a copy on write has already been performed so to obtain the current state of the data the source volume is read . Again if it is desired to access the original data which is reading the state representation the read would be to the device specific data retained in Data App x. In this fashion the predetermined common data image may be invoked as needed with the associated additional application specific data being readily accessible as desired.

One example of a representation is a snapshot. In this example to return to a previous state i.e. when the snapshot was taken both the predetermined common data image data in Data Common Image and all of the application specific data are easily accessible using the snapshot. This allows both the predetermined common data image and additional particular aspects of the application server to be retained in economical and readily accessible fashion.

If in response to the read it is determined that the chunk corresponding to the read has not already been written since the state representation was taken then the read may be made from the predetermined common data image Data Common Image. Although as noted it is preferable to reside the predetermined common data image data in cache for fast access there may be embodiments where it is not in cache in whole or in part with the cache being populated as necessary.

For the write operation it is determined whether the corresponding chunk of Rep App x has already been written since the snap was taken. If so then the original data has already been retained in the device specific store so the write can simply be made to App x source . If not then the original source chunk from the App x source is initially copied to the device specific store Data App x prior to writing to the App x source.

It is noted that as introduced above the common and device specific data portions may correspond to various examples of data including an operating system applications and or application data of various types.

The SDS includes a consolidation module with a representation layer and a data layer and similarly implements physical storage resources .

The SDS further includes a Hypervisor HV module that offers virtual machine management allowing numerous Virtual Machines e.g. VM1 VM2 etc. through VMn to run in the SDS environment. Each VM may be represented such as Rep VM1 and Rep VM2 and Rep VMn as indicated. The representations indicate a common portion which correlates to VM Common in the data layer and device specific portions which respectively correlate to the machine specific instances VM1 Specific VM2 Specific and VMn Specific in the data layer.

Similar to the above described examples the individual VMs share a common portion VM Common for which only one instance is required with the additional device specific aspects readily represented and associated to the common portion. In one embodiment a representation of state such as a snapshot may be used to represent the common portion while also associating thereto the machine specific aspects.

Thus embodiments of the present invention produce and provide for data consolidation. Although the present invention has been described in considerable detail with reference to certain embodiments thereof the invention may be variously embodied without departing from the spirit or scope of the invention. Therefore the following claims should not be limited to the description of the embodiments contained herein in any way.

