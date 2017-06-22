---

title: Copy offload for disparate offload providers
abstract: Aspects of the subject matter described herein relate to offload technology. In aspects, a source offload provider may transfer bulk data to a destination offload provider even if the offload providers are different and independent from each other and have no prior knowledge of each other. In preparation for transferring bulk data, trust may be extended to the offload providers. After authentication, the offload providers may transfer all or a portion of the bulk data over a secure channel without the data traversing the initiator of the transfer.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09071585&OS=09071585&RS=09071585
owner: Microsoft Technology Licensing, LLC
number: 09071585
owner_city: Redmond
owner_country: US
publication_date: 20121212
---
One mechanism for transferring data is to read the data from a file of a source location into main memory and write the data from the main memory to a destination location. While in some environments this may work acceptably for relatively little data as the data increases the time it takes to read the data and transfer the data to another location increases. In addition if the data is accessed over a network the network may impose additional delays in transferring the data from the source location to the destination location. Furthermore security issues combined with the complexity of storage arrangements may complicate data transfer.

The subject matter claimed herein is not limited to embodiments that solve any disadvantages or that operate only in environments such as those described above. Rather this background is only provided to illustrate one exemplary technology area where some embodiments described herein may be practiced.

Briefly aspects of the subject matter described herein relate to offload technology. In aspects a source offload provider may transfer bulk data to a destination offload provider even if the offload providers are different and independent from each other and have no prior knowledge of each other. In preparation for transferring bulk data trust may be extended to the offload providers. After authentication the offload providers may transfer all or a portion of the bulk data over a secure channel without the data traversing the initiator of the transfer.

This Summary is provided to briefly identify some aspects of the subject matter that is further described below in the Detailed Description. This Summary is not intended to identify key or essential features of the claimed subject matter nor is it intended to be used to limit the scope of the claimed subject matter.

The phrase subject matter described herein refers to subject matter described in the Detailed Description unless the context clearly indicates otherwise. The term aspects should be read as at least one aspect. Identifying aspects of the subject matter described in the Detailed Description is not intended to identify key or essential features of the claimed subject matter.

The aspects described above and other aspects of the subject matter described herein are illustrated by way of example and not limited in the accompanying figures in which like reference numerals indicate similar elements and in which 

The phrase subject matter described herein refers to subject matter described in the Detailed Description unless the context clearly indicates otherwise. The term aspects should be read as at least one aspect. Identifying aspects of the subject matter described in the Detailed Description is not intended to identify key or essential features of the claimed subject matter.

As used herein the term includes and its variants are to be read as open ended terms that mean includes but is not limited to. The term or is to be read as and or unless the context clearly dictates otherwise. The term based on is to be read as based at least in part on. The terms one embodiment and an embodiment are to be read as at least one embodiment. The term another embodiment is to be read as at least one other embodiment. 

As used herein terms such as a an and the are inclusive of one or more of the indicated item or action. For example in the claims a reference to an item generally means at least one such item is present and a reference to an action means at least one instance of the action is performed.

Sometimes herein the terms first second third and so forth may be used. Without additional context the use of these terms in the claims is not intended to imply an ordering but is rather used for identification purposes. For example the phrases first version and second version do not necessarily mean that the first version is the very first version or was created before the second version or even that the first version is requested or operated on before the second version. Rather these phrases are used to identify different versions.

Headings are for convenience only information on a given topic may be found outside the section whose heading indicates that topic.

Aspects of the subject matter described herein are operational with numerous other general purpose or special purpose computing system environments or configurations. Examples of well known computing systems environments or configurations that may be suitable for use with aspects of the subject matter described herein comprise personal computers server computers whether on bare metal or as virtual machines hand held or laptop devices multiprocessor systems microcontroller based systems set top boxes programmable and non programmable consumer electronics network PCs minicomputers mainframe computers personal digital assistants PDAs gaming devices printers appliances including set top media center or other appliances automobile embedded or attached computing devices other mobile devices phone devices including cell phones wireless phones and wired phones distributed computing environments that include any of the above systems or devices and the like.

Aspects of the subject matter described herein may be described in the general context of computer executable instructions such as program modules being executed by a computer. Generally program modules include routines programs objects components data structures and so forth which perform particular tasks or implement particular abstract data types. Aspects of the subject matter described herein may also be practiced in distributed computing environments where tasks are performed by remote processing devices that are linked through a communications network. In a distributed computing environment program modules may be located in both local and remote computer storage media including memory storage devices.

Alternatively or in addition the functionality described herein may be performed at least in part by one or more hardware logic components. For example and without limitation illustrative types of hardware logic components that can be used include Field programmable Gate Arrays FPGAs Program specific Integrated Circuits ASICs Program specific Standard Products ASSPs System on a chip systems SOCs Complex Programmable Logic Devices CPLDs and the like.

With reference to an exemplary system for implementing aspects of the subject matter described herein includes a general purpose computing device in the form of a computer . A computer may include any electronic device that is capable of executing an instruction. Components of the computer may include a processing unit a system memory and a system bus that couples various system components including the system memory to the processing unit . The system bus may be any of several types of bus structures including a memory bus or memory controller a peripheral bus and a local bus using any of a variety of bus architectures. By way of example and not limitation such architectures include Industry Standard Architecture ISA bus Micro Channel Architecture MCA bus Enhanced ISA EISA bus Video Electronics Standards Association VESA local bus Peripheral Component Interconnect PCI bus also known as Mezzanine bus Peripheral Component Interconnect Extended PCI X bus Advanced Graphics Port AGP and PCI express PCIe .

The processing unit may be connected to a hardware security device . The security device may store and be able to generate cryptographic keys that may be used to secure various aspects of the computer . In one embodiment the security device may comprise a Trusted Platform Module TPM chip TPM Security Device or the like.

The computer typically includes a variety of computer readable media. Computer readable media can be any available media that can be accessed by the computer and includes both volatile and nonvolatile media and removable and non removable media. By way of example and not limitation computer readable media may comprise computer storage media and communication media.

Computer storage media includes both volatile and nonvolatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. Computer storage media includes RAM ROM EEPROM solid state storage flash memory or other memory technology CD ROM digital versatile discs DVDs or other optical disk storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other medium which can be used to store the desired information and which can be accessed by the computer . Computer storage media does not include communication media.

Communication media typically embodies computer readable instructions data structures program modules or other data in a modulated data signal such as a carrier wave or other transport mechanism and includes any information delivery media. The term modulated data signal means a signal that has one or more of its characteristics set or changed in such a manner as to encode information in the signal. By way of example and not limitation communication media includes wired media such as a wired network or direct wired connection and wireless media such as acoustic RF infrared and other wireless media. Combinations of any of the above should also be included within the scope of computer readable media.

The system memory includes computer storage media in the form of volatile and or nonvolatile memory such as read only memory ROM and random access memory RAM . A basic input output system BIOS containing the basic routines that help to transfer information between elements within computer such as during start up is typically stored in ROM . RAM typically contains data and or program modules that are immediately accessible to and or presently being operated on by processing unit . By way of example and not limitation illustrates operating system application programs other program modules and program data .

The computer may also include other removable non removable volatile nonvolatile computer storage media. By way of example only illustrates a hard disk drive that reads from or writes to non removable nonvolatile magnetic media a magnetic disk drive that reads from or writes to a removable nonvolatile magnetic disk and an optical disc drive that reads from or writes to a removable nonvolatile optical disc such as a CD ROM DVD or other optical media. Other removable non removable volatile nonvolatile computer storage media that can be used in the exemplary operating environment include magnetic tape cassettes flash memory cards and other solid state storage devices digital versatile discs other optical discs digital video tape solid state RAM solid state ROM and the like. The hard disk drive may be connected to the system bus through the interface and magnetic disk drive and optical disc drive may be connected to the system bus by an interface for removable nonvolatile memory such as the interface .

The drives and their associated computer storage media discussed above and illustrated in provide storage of computer readable instructions data structures program modules and other data for the computer . In for example hard disk drive is illustrated as storing operating system application programs other program modules and program data . Note that these components can either be the same as or different from operating system application programs other program modules and program data . Operating system application programs other program modules and program data are given different numbers herein to illustrate that at a minimum they are different copies.

A user may enter commands and information into the computer through input devices such as a keyboard and pointing device commonly referred to as a mouse trackball or touch pad. Other input devices not shown may include a microphone e.g. for inputting voice or other audio joystick game pad satellite dish scanner a touch sensitive screen a writing tablet a camera e.g. for inputting gestures or other visual input or the like. These and other input devices are often connected to the processing unit through a user input interface that is coupled to the system bus but may be connected by other interface and bus structures such as a parallel port game port or a universal serial bus USB .

Through the use of one or more of the above identified input devices a Natural User Interface NUI may be established. A NUI may rely on speech recognition touch and stylus recognition gesture recognition both on screen and adjacent to the screen air gestures head and eye tracking voice and speech vision touch gestures machine intelligence and the like. Some exemplary NUI technology that may be employed to interact with a user include touch sensitive displays voice and speech recognition intention and goal understanding motion gesture detection using depth cameras such as stereoscopic camera systems infrared camera systems RGB camera systems and combinations thereof motion gesture detection using accelerometers gyroscopes facial recognition 3D displays head eye and gaze tracking immersive augmented reality and virtual reality systems as well as technologies for sensing brain activity using electric field sensing electrodes EEG and related methods .

A monitor or other type of display device is also connected to the system bus via an interface such as a video interface . In addition to the monitor computers may also include other peripheral output devices such as speakers and printer which may be connected through an output peripheral interface .

The computer may operate in a networked environment using logical connections to one or more remote computers such as a remote computer . The remote computer may be a personal computer a server a router a network PC a peer device or other common network node and typically includes many or all of the elements described above relative to the computer although only a memory storage device has been illustrated in . The logical connections depicted in include a local area network LAN and a wide area network WAN but may also include phone networks near field networks and other networks. Such networking environments are commonplace in offices enterprise wide computer networks intranets and the Internet.

When used in a LAN networking environment the computer is connected to the LAN through a network interface or adapter . When used in a WAN networking environment the computer may include a modem or other means for establishing communications over the WAN such as the Internet. The modem which may be internal or external may be connected to the system bus via the user input interface or other appropriate mechanism. In a networked environment program modules depicted relative to the computer or portions thereof may be stored in the remote memory storage device. By way of example and not limitation illustrates remote application programs as residing on memory device . It will be appreciated that the network connections shown are exemplary and other means of establishing a communications link between the computers may be used.

As mentioned previously some traditional data transfer operations may not be efficient or even work in today s storage environments.

Turning to the system may include a initiator data access components token provider s a store and other components not shown . The system may be implemented via one or more computing devices. Such devices may include for example personal computers server computers hand held or laptop devices multiprocessor systems microcontroller based systems set top boxes programmable consumer electronics network PCs minicomputers mainframe computers cell phones personal digital assistants PDAs gaming devices printers appliances including set top media center or other appliances automobile embedded or attached computing devices other mobile devices distributed computing environments that include any of the above systems or devices and the like.

Where the system comprises a single device an exemplary device that may be configured to act as the system comprises the computer of . Where the system comprises multiple devices one or more of the multiple devices may comprise the computer of where the multiple devices may be configured similarly or differently.

The data access components may be used to transmit data to and from the store . The data access components may include for example one or more of I O managers filters drivers file server components components on a storage area network SAN or other storage device and other components not shown . As used herein a SAN may be implemented for example as a device that exposes logical storage targets as a communication network that includes such devices or the like.

In one embodiment a data access component may comprise any component that is given an opportunity to examine I O between the initiator and the store and that is capable of changing completing or failing the I O or performing other or no actions based thereon. For example where the system resides on a single device the data access components may include any object in an I O stack between the initiator and the store . Where the system is implemented by multiple devices the data access components may include components on a device that hosts the initiator components on a device that provides access to the store and or components on other devices and the like. In another embodiment the data access components may include any components e.g. such as a service database or the like used by a component through which the I O passes even if the data does not flow through the used components.

As used herein the term component is to be read to include hardware such as all or a portion of a device a collection of one or more software modules or portions thereof some combination of one or more software modules or portions thereof and one or more devices or portions thereof and the like. A component may include or be represented by code.

As used herein the term computer code is to be read to include instructions that dictate actions a computer is to take. These instructions may be included in any computer readable media volatile or nonvolatile.

In one embodiment the store is any storage media capable of storing data. The store may include volatile memory e.g. a cache and nonvolatile memory e.g. a persistent storage . The term data is to be read broadly to include anything that may be represented by one or more computer storage elements. Logically data may be represented as a series of 1 s and 0 s in volatile or nonvolatile memory. In computers that have a non binary storage medium data may be represented according to the capabilities of the storage medium. Data may be organized into different types of data structures including simple data types such as numbers letters and the like hierarchical linked or other related data types data structures that include multiple other data structures or simple data types and the like. Some examples of data include information program code program state program data commands other data or the like.

The store may comprise hard disk storage solid state or other nonvolatile storage volatile memory such as RAM other storage some combination of the above and the like and may be distributed across multiple devices e.g. multiple SANs multiple file servers a combination of heterogeneous devices and the like . The devices used to implement the store may be located physically together e.g. on a single device at a datacenter or the like or distributed geographically. The store may be arranged in a tiered storage arrangement or a non tiered storage arrangement. The store may be external internal or include components that are both internal and external to one or more devices that implement the system . The store may be formatted e.g. with a file system or non formatted e.g. raw .

In another embodiment the store may be implemented as a storage container rather than as direct physical storage. A storage container may include for example a file volume disk virtual disk logical unit logical disk writable clone volume snapshot logical disk snapshot physical disk solid state storage SSD hard disk data stream alternate data stream metadata stream or the like. For example the store may be implemented by a server having multiple physical storage devices. In this example the server may present an interface that allows a data access component to access data of a store that is implemented using one or more of the physical storage devices or portions thereof of the server.

The level of abstraction may be repeated to any arbitrary depth. For example the server providing a storage container to the data access components may also rely on a storage container to access data.

In another embodiment the store may include a component that provides a view into data that may be persisted in nonvolatile storage or not persisted in nonvolatile storage.

One or more of the data access components may reside on an apparatus that hosts the initiator while one or more other of the data access components may reside on an apparatus that hosts or provides access to the store . For example if the initiator is an application that executes on a personal computer one or more of the data access components may reside in an operating system hosted on the personal computer. An example of this is illustrated in .

As another example if the store is implemented by a storage area network SAN one or more of the data access components may implement a storage operating system that manages and or provides access to the store . When the initiator and the store are hosted in a single apparatus all or many of the data access components may also reside on the apparatus.

An offload read allows an initiator to obtain a token that represents data of a store. Using this token the initiator or another initiator may request an offload write. An offload write allows a initiator to cause an offload provider to write some or all of the data represented by the token.

In one embodiment a token is an unpredictable number that is obtained via a successful offload read. A token represents data that is immutable as long as the token is valid. The data a token represents is sometimes referred to as bulk data.

An offload provider is an entity possibly including multiple components spread across multiple devices that provides indirect access to data associated with a token. Logically an offload provider is capable of performing an offload read and or offload write. Physically an offload provider may be implemented by one or more of the data access components and a token provider.

In servicing an offload read or offload write an offload provider may logically perform operations on the data of the store and or on tokens associated with a token provider. For example for an offload read an offload provider may logically copy data from a logical storage container backed by data of a store into a token which may also be backed by data of the store while for an offload write the offload provider may logically copy data from a token to a logical storage container backed by data of the store.

An offload provider may transfer data from a source store write data to a destination store and maintain data to be provided upon receipt of a token associated with the data. In some implementations an offload provider may indicate that an offload write command is completed after the data has been logically written to the destination store. In addition an offload provider may indicate that an offload write command is completed but defer physically writing data associated with the offload write until convenient.

In some implementations an offload provider may share data between a first logical storage container and a second logical storage container and may share data between a token and a storage container. The offload provider may stop sharing data as part of performing a write to physical storage locations of the store which would otherwise cause more than one storage container to be modified or would otherwise cause the data represented by a token to change.

In some implementations an offload provider may perform a logical copy from a storage container to a token or a logical copy from a token to a storage container by initiating sharing of data between a token and a storage container. For example the offload provider may perform an offload read by logically copying the data from the source storage container to the token by initiating sharing of data between the source storage container and the token. In another example the offload provider may perform an offload write by logically copying the data from the token to the destination storage container by initiating sharing of data between the token and the destination storage container.

In some implementations an offload provider may invalidate a token to for example avoid sharing data and or avoid physically copying data. For example the offload provider may perform an offload write by logically copying data from the token to the destination storage container by updating the data structures of the destination storage container to refer to the physical storage locations of the store referenced by the token and in conjunction therewith logically invalidate at least a portion of the token. Note that this may still result in the source and destination storage containers sharing data.

In some implementations an offload provider may initiate sharing of data storage locations among all tokens and storage containers already sharing the data and in addition another storage container or token. For example to service an offload read an offload provider may initiate sharing between a source storage container and a token. Then to service an offload write using the token the offload provider may initiate sharing among the source storage container the token and the destination storage container. If the token is later invalidated sharing with the token is stopped but the sharing between source and destination storage containers may continue e.g. until a write is received that is directed at that data .

As used herein in one implementation a token provider is part of an offload provider. In this implementation where a token provider is described as performing actions it is to be understood that the offload provider that includes the token provider is performing those actions. In another implementation a token provider may be separate from the offload provider.

To initiate an offload read of data of the store the initiator may send a request to obtain a token representing the data using a predefined command e.g. via an API . In response one or more of the data access components may respond to the initiator by providing one or more tokens that represents the data or a subset thereof. A token may be represented by a sequence of bytes which are used to represent immutable data. The size of the immutable data may be larger smaller or the same size as the token.

With a token the initiator may request that all or portions of the data represented by the token be logically written. Sometimes herein this operation is called an offload write. The initiator may do this by sending the token together with one or more offsets and lengths to the data access components .

The data access components may be implemented as a storage stack where each layer of the stack may perform a different function. For example the data access components may partition data split offload read or write requests cache data verify data snapshot data and the like.

One or more layers of the stack may be associated with a token provider. A token provider may include one or more components that may generate or obtain tokens that represent portions of the data of the store and provide these tokens to an initiator.

For a portion of an offload write for a token involved a token relative offset may be indicated as well as a destination relative offset. Either or both offsets may be implicit or explicit. A token relative offset may represent a number of bytes or other units from the beginning of data represented by the token for example. A destination relative offset may represent the number of bytes or other units from the beginning of data on the destination. A length may indicate a number of bytes or other units starting at the offset.

If a data access component fails an offload read or write an error code may be returned that allows another data access component or the initiator to attempt another mechanism for reading or writing the data.

The device may be considered to be one example of an offload provider as this device includes components for performing offload reads and writes and managing tokens.

The token provider may generate validate and invalidate tokens. For example when the initiator asks for a token for data on the store the token provider may generate a token that represents the data. This token may then be sent back to the initiator via the data access components and .

In conjunction with generating a token the token provider may create an entry in the token store . This entry may associate the token with data that indicates where on the store the data represented by the token may be found. The entry may also include other data used in managing the token such as when to invalidate the token a time to live for the token other data and the like.

When the initiator or any other entity provides the token to the token provider the token provider may perform a lookup in the token store to determine whether the token exists. If the token exists and is valid the token provider may provide location information to the data access components so that these components may logically read or write or logically perform other operations with the data as requested.

In another exemplary arrangement similar to the token provider and token store may be included in the device and the data access components connected to token provider . For example an operating system OS of the device may include the token provider and the token store . In this example the initiator may assume the existence of a token provider and token store for all copying performed by the initiator . With this assumption the initiator may be implemented to omit code that falls back to normal read and write.

In the example above the OS may implement offload read by reading the requested data from the data access components and storing the data in storage volatile or non volatile of device creating a new token value and associating the newly created token value with the read data. The OS may implement offload write by copying e.g. writing the data associated with the token to the destination specified by initiator . In this example the initiator may need to re attempt a copy at the offload read step in some scenarios but this re attempt may be less burdensome for the initiator than falling back to normal read and write.

The source initiator and the destination initiator may be implemented similarly to the initiator of . The source initiator and the destination initiator may be two separate entities or a single entity.

If the source storage container and the destination storage container are implemented by a single system the offload provider may be implemented as one or more components of the system implementing the storage containers. If the source storage container and the destination storage container are implemented by different systems the offload provider may be implemented as one or more components that are distributed across the systems implementing the storage containers.

Furthermore there may be more than two instances of storage containers and physical stores. For example for a given token obtained from a source there may be more than one destination specified. For example multiple offload writes may be issued which refer to a single token and each offload write may successfully target any destination known to the offload provider .

The source physical store and the destination physical store may be the same store or different stores. These physical stores store physical data that backs the source and destination storage containers and may also back the data represented by the tokens.

Although illustrated as only having one storage container between the initiator and the physical store as mentioned previously in other embodiments there may be multiple layers of storage containers between the initiator and the physical store.

The source initiator may obtain a token by issuing an offload read. In response the offload provider may generate a token and provide it to the source initiator .

If the source initiator and the destination initiator are separate entities the source initiator may provide the token to the destination initiator . The destination initiator may then use the token to issue an offload write to the destination storage container .

In receiving the offload write request the offload provider may validate the token and logically write data to the destination storage container as indicated by the offload write request.

In accordance with aspects of the subject matter described herein the source offload provider hereinafter sometimes referred to as the source and the destination offload provider hereinafter sometimes referred to as the destination may be any two offload providers with a compatible offload provider protocol and a communications path between them e.g. valid network route via the Internet . No pre existing trust relationship between the source and the destination is required. The initiator of the offload read e.g. the offload read initiator and the initiator of the offload write e.g. the offload write initiator may or may not be the same entity.

The offload read initiator hereinafter sometimes referred to as the initiator trusts the source offload provider for purposes of being the source of the requested data. The offload write initiator trusts the destination for purposes of writing bulk data represented by the token to a requested destination storage container. The offload read initiator trusts the offload write initiator for purposes of having access to the bulk data and not divulging the bulk data to any inappropriate parties. The offload write initiator trusts the offload read initiator for purposes of reading data.

These trust relationships may be used extended to the source and the destination . The initiators may prove to the source that the destination is a correct destination for a particular transfer among potentially more than one correct destination . In one implementation trust relationships may be extended by sending trust data. Trust data may include a secret or perhaps non secret data. In other implementations trust relationships may be extended via other cryptographic means such as public private key cryptography or other cryptographic means.

The communication between the source and destination may be encrypted using a key provided by the initiators. This key may be unique to a particular transfer. The source validates that communication from the destination is from a valid e.g. trusted by the initiators destination offload provider. The destination validates that the communication is really from the source .

The network address of the source may be conveyed to the destination in a variety of ways including for example being embedded in the token as auxiliary data conveyed with or in conjunction with the token or the like. The network address may be any type of address relevant to any digital communications technology such as an IPV4 Internet address and port IPV6 address Ethernet address or the like. The network address may require translation or conversion on first use. For example the address may be an identifier that maps to a current IP address via a distributed hash table. Depending on the type of address and the reachability of the address the address may be relevant and usable at any size geographical scope from small to worldwide . In one implementation the network address of the destination may be transmitted to the source which may initiate the establishment of the communication channel between the source and the destination .

One exemplary mechanism for extending using the trust previously mentioned is described below. There is no intention however of limiting aspects of the subject matter only to the example described below. Indeed based on the teachings herein those skilled in the art may recognize other mechanisms that may be used without departing from the spirit or scope of aspects of the subject matter described herein.

The word transfer as used below is used to refer to an overall offload read offload write sequence wherein some bulk data is transferred from a source to a destination without the bulk data needing to transit the initiator s of the offload read and offload write.

In one implementation the token is not used as the only shared secret. A copy offload may have potentially multiple destinations that know the token value. In this implementation just knowing the token value may not allow an alleged source offload provider to prove to the destination offload provider that the alleged source offload provider is really the source offload provider rather than a different non cooperating destination offload provider.

1. In one example the offload read initiator sends a transfer specific key Ksecret to the source along with the offload read request. In another example the source generates and provides a key separate from the token value in the offload read response.

This establishes a shared secret Ksecret between the source and the offload read initiator with the shared secret as safe as the bulk data would have been e.g. conveyed via the same communication channel as the bulk data would have been if using normal read write instead of offload . In some implementations the Ksecret value may be the same for more than one transfer potentially across use of more than one token.

2. The offload read initiator may forward the token to the offload write initiator or they may be the same initiator . If the offload read initiator and the offload write initiator are separate initiators the offload write initiator may be treated as part of the destination storage stack. With this in mind below the offload read initiator and the offload write initiator are described as both being initiated by the offload read initiator hereinafter sometimes referred to simply as the initiator .

In an implementation round trip communications may be minimized to remove any communications that are not necessary. An offload write is an offload write regardless of form. For example forwarding a token to a different machine that in turn issues an offload write is really just a different way for an offload read initiator to initiate an offload write.

3. When performing an offload write the initiator sends the token as usual and in addition may also send . Note that Ksecret salt is a numeric value the salt encrypted with the secret key Ksecret which is known only to the source and initiator. The destination does not know Ksecret itself but the destination does know that Ksecret is only known by the initiator and source . The destination implicitly trusts the initiator to behave correctly with respect to this transfer since the initiator could just as well write anything the initiator wants to write.

The destination sends Ksecret salt to the source but does not send the salt value to the source and the source can then decrypt Ksecret salt to obtain the salt value and respond e.g. via data encrypted by the key shared between the source and destination to the destination with the salt value. The destination then knows that the source knows Ksecret and therefore that the source is really the source the initiator is already implicitly trusted with respect to the requested write up front but now the initiator has convinced the destination to trust the source with respect to the requested write without the destination ever knowing Ksecret.

In another implementation the source may send Kchannel timestamp or Kchannel to prove that the source was able to decrypt Ksecret proving to the destination that the source knows Ksecret and is therefore known to be the actual source .

4. The channel used for communication between the source and destination is a new channel. In terms of security in one implementation the channel is at least as secure as the channels between the initiator and the source and between the initiator and the destination . The at least as secure as part may change as computation capacity and decryption capabilities evolve. In one implementation the channel may be encrypted with a fairly long key suitable for highly sensitive data. For today s technology a 256 bit AES key may be sufficient. The length and type of this key may change with technology. Each of the source the destination and initiator may refuse to participate in a transfer if the key length is not long enough e.g. as specified by their respective configurations .

The key used to encrypt the channel between source and destination may be generated by the source the initiator or the destination . The key used to secure the channel is sometimes referred to herein as Kchannel to distinguish it from Ksecret . In one implementation Kchannel is generated at the source and the source sends Kchannel to the initiator in the offload read response.

In another implementation Kchannel is generated at the initiator. In this implementation sending the key from source to the initiator is not needed. In addition the initiator may generate a key per source destination pair and per transfer .

6. The destination extracts the network address of the source from the token or from information conveyed along with the token e.g. from the source to the initiator to the destination .

8. The source decrypts using Ksecret to get . The valid portion matching the expected value at the source proves to the source that the destination that sent the message is really a valid destination.

9. The source may send Kchannel timestamp or Kchannel to prove that the source was able to decrypt Ksecret proving to the destination that the source knows Ksecret and is therefore known to be the actual source.

10. From this point onward the source and destination may communicate using encrypted messages which are encrypted with Kchannel. Each message may include a validity check value and sequence number which will only match the expected value if the message has not been tampered with. No other entity may know Kchannel other than those entities which would have had access to the bulk data anyway had normal read write been used instead of offload operations.

For added security any layer of the destination storage stack that needs to process an offload write by sending two or more offload writes to two or more destinations may avoid using the same Kchannel key with two different destinations especially when there is any possibility that the two or more destinations might not be within precisely the same trust boundaries. This may be done for example to prevent one destination from snooping on the channel between the source and a different destination to determine that the different destination received some data from the same token. Instead such a layer may avoid this by limiting its handling of the offload write to a single destination per Kchannel key.

Note that trust relationships in the destination stack are such that all higher layers of the destination stack may have the Kchannel key used in a lower layer. Two separate forks of a lower layer may also have the same key as each other or may have different keys for added security.

Where truncation occurs during an offload operation the truncation may just be propagated back to the initiator of the offload read which may then generate a new Kchannel key and issue a new offload write using the same token.

If partial processing is too onerous the initiator may provide more than one Kchannel key in the initial offload write along with Ksecret Kchannel valid for each one and a stack layer may avoid using the same Kchannel key down two forks to lower layers.

If the initiator supports more than one token per transfer a separate Kchannel key per destination may suffice instead of a separate Kchannel per token .

In one implementation the channel between source and destination may be used to move bulk data for more than one token as long as all the tokens are for the same transfer and same source.

11. The destination sends the token s encrypted using Kchannel to the source along with an indication of which portions of the token s bulk data are being requested. The destination may refrain from telling the source where the data will be written. Sending the token to the source encrypted in this way does not divulge Kchannel to any entity that does not already know it and does not divulge the token to the recipient of the message unless the recipient of the message has Kchannel.

13. The destination writes at least some of the bulk data to the offsets of the destination requested in the offload write command.

14. The destination completes the offload write command which informs the initiator that the transfer is done.

The messages involved between initiator source and destination may be combined such that only one offload read request response is needed from the initiator to the source only one offload write is needed between initiator and destination and only one exchange from destination to the source and back is needed. This may be done for example to reduce the total latency e.g. one round trip from the initiator to the source one round trip from the initiator to the destination and one round trip from the destination to the source .

Multiple transfers may occur concurrently especially when a large amount of bulk data needs to be copied. Concurrent transfers may be done in such a way as to keep the network link from the source to the destination busy transferring bulk data.

At a request for an offload read token is sent. For example referring to the initiator sends an offload read request to the source storage stack . The source storage stack delivers the offload read request to the source .

At in response to the request a token is received from the source offload provider. For example referring to the source sends a token to the initiator . The token may be conveyed in the same message with or separately from other data such as a secret to extend trust and a channel secret as mentioned previously.

At a secret is generated obtained. If generated at the initiator the secret may be generated prior to the actions indicated by and sent in the request for the token. In an alternative the secret may also be generated after the request for the token is sent and may be sent after the request is sent.

As another alternative instead of generating the secret by the initiator the secret may be obtained from the source offload provider. In this alternative the secret may be obtained from the offload read response that conveys the token or in a separate message.

The actions of and may be combined or separate. In one implementation the secret may be provided together with the token in a single offload write command. In another implementation the secret may be provided in a separate message from the offload write command in which the token is sent.

At the secret is provided to the destination offload provider. For example referring to the offload read initiator provides the secret to the offload write initiator which provides the secret to the destination offload provider via the destination storage stack . The secret allows the extension of trust as previously indicated. In particular the secret allows the source offload provider to trust the destination offload provider as the source offload provider trusts the initiator and for the destination offload provider to trust the source offload provider as the destination offload provider trusts the initiator.

In one implementation the secret may be provided together with the token in a single offload write command. In another implementation the secret may be provided in a separate message from the offload write command in which the token is sent.

At the token is provided to the destination offload provider in an offload write command. For example referring to the offload read initiator may provide the token to the offload write initiator if they are separate entities which provides the token to the destination offload provider via the destination storage stack . The offload write command indicates an instruction to copy at least a portion of the immutable data from the source offload provider to the destination offload provider.

The source offload provider and the destination offload provider may be the same offload provider or they may be independent of each other. Independent means that they are different offload providers and are not the same offload provider. In one implementation independent offload providers may be backed by one or more of the same storage devices and or may share one or more components. In another implementation independent offload providers are not backed by any common storage and do not share any components.

An example where the source and destination offload providers are the same offload provider and hence not independent is illustrated in with offload provider .

At block other actions if any may be performed. Other actions may include for example providing a Kchannel key with which to secure a communications channel between the source offload provider and the destination offload provider. This Kchannel key may be generated by the initiator the source or the destination. There may be an additional Kchannel key for each additional destination offload provider to which data represented by the token is to be copied.

Other actions may also include for example providing a network address of the source offload provider to the destination offload provider by embedding the network address in the token.

Other actions may also include for example providing a network address of the source offload provider to the destination offload provider by embedding in the token a lookup key usable to find the network address.

Other actions may also include for example any other actions indicated herein as pertaining to the initiator.

At a token is received from the initiator. For example referring to the destination receives a token from the offload read initiator . The token is generated by a source offload provider that ensures immutability of the data as long as the token is valid.

At a secret is received from the initiator. For example referring to the destination receives a secret from the offload read initiator . The secret allows the extension of trust as previously mentioned.

At other data is received at the destination. This other data may include for example a Kchannel key with which to secure a communications channel between the destination offload provider and the source offload provider a network address or other data that has been mentioned herein.

At authentication occurs. For example referring to using the secret and or other data the destination may authenticate the source and vice versa.

At a secure channel is established with the source. For example referring to the destination establishes a secure communications channel with the source using a Kchannel key.

At the token is provided to the source. For example referring to the destination may provide the sourced with the token in conjunction with an instruction to copy bulk data represented by the token to the destination .

At the bulk data is received. For example referring to the destination receives the bulk data via the secure channel from the source .

At other actions if any may be performed. Other actions may include for example any other actions described herein as pertaining to the destination.

At an offload read request may be received from an initiator. For example referring to the source may receive an offload read request from the initiator . In one implementation the offload read request may include or be conveyed in conjunction with a secret usable to extend trust as previously indicated.

In another implementation at the source generates the secret. For example referring to the source may generate the secret to send back to the initiator .

At the token is sent potentially with a secret depending on implementation. For example referring to the source sends the token with the secret to the initiator .

At the secret is received from a destination. For example referring to the source receives the secret from the destination . Receiving the secret may include receiving something derived from the secret that provides evidence that the sender knows the secret.

At a secure channel is established with the destination. For example referring to the source establishes a secure connection with the destination .

At a token is received from the destination. For example referring to the source receives a token from the destination . The token may be conveyed with an instruction to send all or a portion of bulk data associated with the token.

At block the bulk data is provided. For example referring to the source provides at least some bulk data represented by the token to the destination .

At block other actions if any may be performed. Other actions may include for example receiving a network address of the destination and initiating by the source the establishment of a communication channel with the destination. Other actions may also include for example any other actions described herein as pertaining to the source.

As can be seen from the foregoing detailed description aspects have been described related to offload technology. While aspects of the subject matter described herein are susceptible to various modifications and alternative constructions certain illustrated embodiments thereof are shown in the drawings and have been described above in detail. It should be understood however that there is no intention to limit aspects of the claimed subject matter to the specific forms disclosed but on the contrary the intention is to cover all modifications alternative constructions and equivalents falling within the spirit and scope of various aspects of the subject matter described herein.

