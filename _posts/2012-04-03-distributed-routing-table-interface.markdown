---

title: Distributed routing table interface
abstract: Application programming interface (API) for starting and accessing distributed routing table (DRT) functionality. The API facilitates bootstrapping into the DRT by one or more devices of a group of devices (a mesh) seeking to collaborate over a serverless connection, establishing a node of the DRT, where each node is an instance of an application that is participating in the mesh, and node participation by allowing the application to search for keys published by other nodes in the mesh, or by becoming part of the mesh by publishing a key. The API facilitates optimization of the routing table for quickly finding a root of a specific key in the mesh by finding the key directly in a cache or by asking a root node of the key that is in the local routing table that is closest numerically to the key being searched.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08977686&OS=08977686&RS=08977686
owner: Microsoft Corporation
number: 08977686
owner_city: Redmond
owner_country: US
publication_date: 20120403
---
This application is a Divisional application of pending U.S. patent application Ser. No. 11 716 896 entitled DISTRIBUTED ROUTING TABLE INTERFACE and filed Mar. 12 2007 the entirety of which is incorporated by reference herein.

Technological advances in computing devices and networking facilitate access to a wide variety of information and services allowing access from virtually anywhere in the world. Collaboration can be an effective means by which employees of a corporate enterprise for example or people in general can communicate to exchange data and information on certain topics of interest. However given the location and connection capabilities at any point in time participants may want to join independent of the need to rely on server or network systems.

With the advances in storage and computing power of computing systems users now are capable of interacting with many different data types such as images video clips audio data and textual data for example. Moreover the users can typically communicate using several types of devices with which to connect to a session. For example one user can participate by audio video from a conference room another by voice via a desktop computer and yet another by text input using a cell phone.

Collaboration while using such disparate media capabilities has traditionally been addressed at the server level by consolidating media processing capabilities locally. However this is problematic in that more resources are required to administer such systems and these systems are more difficult to scale to meet conferencing demands. Advances in operating system behavior and capabilities for example now obviate the need to collaborate through servers thereby requiring new and more efficient APIs for accessing these capabilities for resolving device location providing security and the like in a serverless communications environment.

The following presents a simplified summary in order to provide a basic understanding of novel embodiments described herein. This summary is not an extensive overview and it is not intended to identify key critical elements or to delineate the scope thereof. Its sole purpose is to present some concepts in a simplified form as a prelude to the more detailed description that is presented later.

The disclosed architecture includes an application programming interface API for starting and accessing distributed routing table DRT functionality in a serverless environment. The API facilitates bootstrapping into the DRT by one or more devices of a group of devices a mesh seeking to collaborate over a serverless connection. The API further provides for establishing a node of the DRT where each node is an instance of an application that is participating in the collaborative mesh.

The DRT forms an overlay mesh on top of underlying transport e.g. an IPv4 or IPv6 Network . The API facilitates node participation by allowing the application to search for keys published by other nodes in the mesh or by becoming part of the mesh by publishing a key. When publishing a key the node maintains a local routing table of other nodes in the mesh with the selection of which nodes to include in the table being based on the key the node is locally publishing.

The API facilitates optimization of the routing table for quickly finding a root of a specific key in the mesh by finding the key directly in a cache or by asking a root node of the key that is in the local routing table that is closest numerically to the key being searched the neighbor device in turn looks in its own local routing table and returns either the addresses of the required node or the addresses of the node publishing the key numerically closest in the local routing table.

The DRT API includes enumerations related to scope security mode status match type leaf set key change and event type. API structures are related to a security provider bootstrap provider imposed settings on a local instance registration search information and results and event data.

To the accomplishment of the foregoing and related ends certain illustrative aspects are described herein in connection with the following description and the annexed drawings. These aspects are indicative however of but a few of the various ways in which the principles disclosed herein can be employed and is intended to include all such aspects and their equivalents. Other advantages and novel features will become apparent from the following detailed description when considered in conjunction with the drawings.

Disclosed herein is a distributed routing table DRT application programming interface API for accessing the capabilities of the DRT. The DRT API is described in terms of behavior which includes life cycle and state transitions key registering and unregistering and searching. The API enumerations structures and functions are also described in detail.

The DRT is a serverless means whereby a collection of devices can collaborate. The DRT is a set of nodes that collaborate to construct an overlay routing table which is stored in a distributed fashion that can be used to determine a route from one node to another node e.g. using a numeric ID to identify the destination node . Routes can be identified as a set of hops involving participating nodes. The DRT comprises local instances which reside on separate devices but which are used by one device to find another device. In other words each device uses a portion of the DRT for finding other devices.

The DRT is designed around a highly componentized model. The heart of the system is a node component which contains the protocol handlers and the core APIs. The node component references pluggable modules for separable subsystems that include routing table management transport bootstrap security and logging. Each module can be instantiated by an application e.g. word processing and a reference is passed to the node component.

Note that modules may be reused between multiple logical node instances if the module itself supports that behavior. For example a transport can multiplex a listening port and handle multiple nodes from one module. Conversely a given security module might not support multiplexing for isolation and simplicity reasons.

Following are definitions of terms that may be used throughout the description. A distributed hash table DHT is a DRT with the added semantics of being able to insert a key value pair into the distributed system such that the pair can later be retrieved by the publisher or another node possibly subject to access control lists ACLs . The data is distributed amongst nodes based on an algorithm to ensure some level of reliability.

Peer name resolution protocol PNRP is a name resolution system that resolves names using routes generated by an underlying DRT platform.

A mesh is a group of nodes participating in a DRT. The term mesh can be used to scope the breadth of operations for example the node participates in routing only within a site or for the entire Internet or for all applications or for a single application.

A key is an integer of variable length used for routing and conceptually is equivalent to an IP address in IP routing.

A node is a particular instance of the DRT software running on a machine in a given mesh. Note that there can be multiple logical nodes on a single physical machine.

A routing entry is a small data structure containing a key and the endpoint information for the root of the key.

A local routing table is a collection of routing entries maintained on a single node to allow routing to next hops.

Reference is now made to the drawings wherein like reference numerals are used to refer to like elements throughout. In the following description for purposes of explanation numerous specific details are set forth in order to provide a thorough understanding thereof. It may be evident however that the novel architecture can be practiced without these specific details. In other instances well known structures and devices are shown in block diagram form in order to facilitate a description thereof.

In this serverless environment each of the devices includes a separate node instance N I of the DRT . Each node instance includes table entries of one or more other mesh devices or node instances thereof . For example if the first application of the first device communicates with the third application of third device this occurs via the node instances which as described above include modules for supporting routing table management transport bootstrap security and logging. The DRT architecture is extensible in that other modules e.g. customized can be plugged in as developed by third party vendors for example.

An interface component I C facilitates access to the corresponding node instances and determination of a route to a destination device. For example the first device includes a first interface component I C for starting and accessing the local instance N I the second device includes a second interface component I C for starting and accessing a second local instance N I and the third device includes a third interface component I C for starting and accessing a third local instance N I .

In operation the first application can find the same type of application the second application by communicating with the third device . In other words the first DRT node instance may not include routing information for the second device such that the first device can communicate with the second device directly. However the third DRT node instance of the third device includes routing information that can direct the information of the first device application to the second device application . As shown there can be more devices than are illustrated as well as node instances for the DRT .

Once a node instance successfully bootstraps into a DRT the node instance moves into the DRT ACTIVE state . Once in this state the node instance is participating in the DRT. The node instance can move into multiple states from the DRT ACTIVE state depending on one or more conditions. If the network goes away the node instance moves to a DRT NO NETWORK state . If for some reason the node is considered the last node in the DRT the node will move into a DRT ALONE state . Finally if a cataclysmic event occurs the DRT will move into a DRT FAULTED state .

More specifically if a node successfully discovers that no other node is currently in the DRT the node moves into the DRT ALONE state . Once in the alone state the node listens for other nodes to connect to the DRT. A node can move into multiple states from the alone state depending on the condition. If the network goes away the node can moves into the DRT NO NETWORK state . Additionally a new node or node instance in the device can be started and join the DRT in which case the new node will move into the DRT ACTIVE state . Again if cataclysmic event occurs the DRT local instance will move into the DRT FAULTED state .

If a node loses network connectivity and moves into the DRT NO NETWORK state the node can wait and if network connectivity is restored the infrastructure will restart the bootstrapping process and the node will move into the DRT BOOTSTRAPPING state . If the node moves into the fault state a cataclysmic event has occurred on the local node instance e.g. the device running out of memory . At this point the node calls a DrtClose method to shut down the node instance.

For example a first application e.g. of a device or server can start and access a first DRT local instance via first interface component e.g. a DRT API . The first node instance is illustrated as part of a first DRT mesh . Similarly the first application can start and access a second DRT local instance via a second interface component the second local instance also part of the first DRT mesh .

The first application can also be associated with a third DRT local node instance on a different mesh for example a second mesh denoted DRT . The third node instance can be started and accessed by the first application via a third interface component . A second application e.g. of the same device starts and accesses a fourth DRT local instance on the second mesh via a fourth interface component . Accordingly an application e.g. application can start multiple different DRT node instances e.g. instances and of which the instances can be associated with different groups of nodes e.g. DRT mesh and DRT mesh . Moreover a single device can include multiple applications e.g. and each communicating over different mesh e.g. and or a same mesh e.g. . In an alternative implementation it is to be understood that the interface components and can be a single interface component for starting and accessing the individual node instances e.g. and for one application e.g. . In yet another alternative implementation the interface components and associated with the first application can be a single interface component for starting and accessing local node instances of the different mesh and .

A search operation finds the root for a given key in the mesh. This is implemented via the searching node iteratively performing lookup operations with other nodes until the target of the search is found. However it should be noted that a recursive design could also be used in the implementation with the searcher contacting a first hop the first hop contacting a second hop and so on.

The DRT forms an overlay mesh on top of underlying transport normally an IPv4 or IPv6 network . Nodes can either participate by searching for keys published by nodes in the mesh or by becoming part of the mesh by publishing keys. When publishing a key the node maintains a local routing table of other nodes in the mesh with the selection of which nodes to include in the table being based on the key the node is locally publishing.

The routing table is optimized in such a manner that it is possible to quickly find the root of a specific key in the mesh either by finding the key directly in the cache or by asking the root of the key that is in the local routing table that that is closest numerically to the key being searched for the neighbor in turn looks in its own local routing table and returns either the addresses of the required node or the addresses of the node publishing the key numerically closest in the local routing table. This is repeated until either the required key is found or it has been determined that no such key exists. An example of such a routing scheme is implemented by PNRP.

The DRT can consist of nodes running in applications or services on a mix of servers PCs or devices. The DRT runs in proc with the owning application e.g. spreadsheet . All threads are spawned using the same token as the application thread which calls the DRT. As such the DRT can be used in a service with or without impersonation without issue.

Additionally note that a given process can host multiple logical node instances. These instances can be for multiple different meshes that the application wishes to access e.g. PNRP can access a global cloud mesh and a link local cloud mesh at the same time . A single process could have two instances of the same mesh but the only reason an application might wish to do that is if the application has multiple credentials and is creating an instance for each credential.

At an application of a device is launched in furtherance of collaborating with a serverless group of devices. At a local node instance of a distributed routing table is opened based on a call from the application. At state of the local node instance transitions based on conditions related to connectivity to the group of devices. At the device can detach from the group of de vices by closing the local node instance.

To search the DRT the application creates a search query. This query can include several pieces of information for the application the key to search the DRT for specified through the search API whether or not the infrastructure should search the local DRT instance for the key or just remote nodes whether the search returns the path to a result the number of results to return within a particular min max range and whether the search should return only an exact match or the closest result s .

An exact search instructs the infrastructure to look for the key that exactly matches the key being searched. If the infrastructure can find key the result is returned otherwise no results are returned. A closest search instructs the infrastructure to look for the key that exactly matches the key being searched. If the infrastructure can find the key the result is returned otherwise the closest result is returned. If the application chooses to get the closest n results the application specifies a MaxEndpoint 1 which further instructs the infrastructure to return the exact match plus n 1 closest results or n closest results if no exact match is found.

By specifying fiterative TRUE for a search the application chooses to be called back for each hop during the search. In other words anytime the infrastructure communicates with a node during the search the application will be able to obtain the key endpoint pair of that node. The following table illustrates fIterative TRUE search behavior.

The last result from every search will be a final callback with a failed hr DRT E NO MORE . This assumes the application is returning true from the result callback to allow the search process to run its full course. If the callback returns false no more callbacks will happen.

Following is a description of type definitions enumerations structures and functions of the DRT API. These are the types used throughout the DRT API.

Following are DRT specific return codes returned by the API. See the functions section for what error codes are returned by which API specifically.

Following are enumerations employed by the DRT API. The DRT SCOPE enumeration specifies the IPv6 scope in which the DRT will operate if when using an IPv6 UDP transport created by DrtCreateIpv6UdpTransport. The enumeration also indirectly specifies the scope a PNRP bootstrap resolver created by DrtCreatePnrpBootstrapResolver will use to find other participating nodes.

The DRT SECURITY MODE is a DRT SETTINGS field that specifies the security mode the DRT should operate under. By default 10 of the cache and the final node in a search are authenticated.

The different status a DRT can have is captured in DRT STATUS. DRT STATUS reflects status of the local node.

DRT LEAFSET KEY CHANGE TYPE is the type of change that occurs to a leaf set node in the local DRT cache.

DRT EVENT TYPE is an event has occurred in the DRT. The event handle passed into DrtOpen is signaled with one of the following events.

Following is a summary of structures included as part of the DRT API. DRT DATA is a data blob used throughout the DRT API.

DRT SECURITY PROVIDER. The following structure defines the interface that can be implemented by a security provider 

RegisterKey. When an application attempts to register a key the key is passed to this interface for validation by the security provider before completing the registration.

UnregisterKey. When an application attempts to unregister a key the key is passed to this interface for validation by the security provider before completing the unregister call.

ValidateAndUnpackPayload. This function is called when an authority message is received on the wire. The function is responsible for validating the data received and for unpacking the service addresses revoked flag and nonce from a secured address payload.

SecureAndPackPayload. This function is called when an Authority message is about to be sent on the wire. It is responsible for securing the data that will be sent and for packing the service addresses revoked flag nonce and possibly other application data into the Secured Address Payload. Following is a table of parameters.

The FreeData function is called to free data that the security provider allocated in calls to ValidateAndUnpackPayload and SecureAndPackPayload.SecureAndPackPayload. The following table indicates parameters for this function.

The Register function registers an endpoint with the bootstrapping mechanism that other nodes can use resolve to find.

The Unregister function unregisters an endpoint with the bootstrapping mechanism. As a result other nodes will not be able to find the local node through a resolve.

DRT REGISTRATION is for a key registration found via a search issued by DrtStartSearch. This structure is contained in an overall DRT SEARCH RESULT.

DRT SEARCH RESULT is a search result found by a search issued via DrtStartSearch. It contains the actual registration entry and the type of match.

DRT EVENT DATA. After an application receives an event signal the application calls the DrtGetEventData to get the data associated with that event. This structure contains the data returned based on the event.

Based on the DRT EVENT TYPE the union will contain a field structure specific to that event type. If the DRT EVENT TYPE is a status change it will contain the following 

A leaf set key is a key that is contained in the cache of a DRT locally. By paying attention to these events an application can know the contents of the local DRT cache for use. If the DRT EVENT TYPE is a leaf set key change the union contains the following 

The following functions can be included in the DRT API. A DrtCreatePnrpBootstrapResolver function creates a generic bootstrap resolver based on the PNRP protocol. The returned pointer is passed to DrtOpen via the DRT SETTINGS structure.

A DrtDeletePnrpBootstrapResolver function deletes a generic bootstrap resolver based on the PNRP protocol.

A DrtCreateIpv6UdpTransport function creates a generic transport based on the IPv6 UDP protocol. The returned pointer is passed to DrtOpen via the DRT SETTINGS structure.

HRESULT Values DRT E INVALID PORT one of the fields is invalid for example the port is in use and the DRT cannot use that port.

A DrtCreateDerivedKeySecurityProvider function creates a Derived Key Security Provider based on the IPv6 UDP protocol. The returned pointer is passed to DrtOpen via the DRT SETTINGS structure.

A DrtCreateDerivedKey function creates a key that can be registered with the DRT. The key will be generated from the passed in credential and must have the same root chain as what was passed in to DrtCreateDerivedKeySecurityProvider.

A DrtOpen function opens or creates a new local DRT instance specified by the DRT SETTINGS structure passed in.

A DrtRegisterKey function registers a given key in the DRT. If the API is called with a key that has already been registered it updates the key.

A DrtStartSearch function starts a search for a given key through the DRT using the criteria specified in the DRT SEARCH INFO. The handle specified is signaled when a search result is found. The application then calls DrtGetSearchResult to get the search result.

A DrtContinueSearch function continues a DRT SEARCH RETURN PATH search for a particular key in a DRT. This API can be called anytime after a search has been issued. It will cause the search to continue and results will continue being returned via the DRT SEARCH RESULT event.

After the search event is signaled this DrtGetSearchResult API allows the caller to retrieve the search result. While the queue has search results the API will return S OK. The application should continue to loop using this API while receiving S OK. When the queue is empty the API will return DRT E SEARCH IN PROGRESS or DRT E NO MORE. If DRT E SEARCH IN PROGRESS is returned the search is not complete and the application should continue to wait on the event handle. If DRT E NO MORE is returned the search is complete and the application should no longer continue to wait on the event handle.

A DrtEndSearch function ends a search for a particular key in a DRT. This API can be called anytime after a search has been issued. It will cause the search to be cancelled and results will stop being returned via the DRT SEARCH RESULT event. This API is called after the application receives the DRT E NO MORE hresult from the search event.

A DrtFreeData function frees data returned to the caller via a DRT API such as DrtGetEventData. An application only has to call DrtFreeData once with the pointer given back by the GetEventData. The application does not have to call it for each contained pointer in the structure that is returned.

As used in this application the terms component and system are intended to refer to a computer related entity either hardware a combination of hardware and software software or software in execution. For example a component can be but is not limited to being a process running on a processor a processor a hard disk drive multiple storage drives of optical and or magnetic storage medium an object an executable a thread of execution a program and or a computer. By way of illustration both an application running on a server and the server can be a component. One or more components can reside within a process and or thread of execution and a component can be localized on one computer and or distributed between two or more computers.

Referring now to there is illustrated a block diagram of a computing system operable to execute the disclosed DRT architecture. In order to provide additional context for various aspects thereof and the following discussion are intended to provide a brief general description of a suitable computing system in which the various aspects can be implemented. While the description above is in the general context of computer executable instructions that may run on one or more computers those skilled in the art will recognize that the novel architecture also can be implemented in combination with other program modules and or as a combination of hardware and software.

Generally program modules include routines programs components data structures etc. that perform particular tasks or implement particular abstract data types. Moreover those skilled in the art will appreciate that the inventive methods can be practiced with other computer system configurations including single processor or multiprocessor computer systems minicomputers mainframe computers as well as personal computers hand held computing devices microprocessor based or programmable consumer electronics and the like each of which can be operatively coupled to one or more associated devices.

The illustrated aspects may also be practiced in distributed computing environments where certain tasks are performed by remote processing devices that are linked through a communications network. In a distributed computing environment program modules can be located in both local and remote memory storage devices.

A computer typically includes a variety of computer readable media. Computer readable media can be any available media that can be accessed by the computer and includes volatile and non volatile media removable and non removable media. By way of example and not limitation computer readable media can comprise computer storage media and communication media. Computer storage media includes volatile and non volatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. Computer storage media includes but is not limited to RAM ROM EEPROM flash memory or other memory technology CD ROM digital video disk DVD or other optical disk storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other medium which can be used to store the desired information and which can be accessed by the computer.

With reference again to the exemplary computing system for implementing various aspects includes a computer the computer including a processing unit a system memory and a system bus . The system bus provides an interface for system components including but not limited to the system memory to the processing unit . The processing unit can be any of various commercially available processors. Dual microprocessors and other multi processor architectures may also be employed as the processing unit .

The system bus can be any of several types of bus structure that may further interconnect to a memory bus with or without a memory controller a peripheral bus and a local bus using any of a variety of commercially available bus architectures. The system memory includes read only memory ROM and random access memory RAM . A basic input output system BIOS is stored in a non volatile memory such as ROM EPROM EEPROM which BIOS contains the basic routines that help to transfer information between elements within the computer such as during start up. The RAM can also include a high speed RAM such as static RAM for caching data.

The computer further includes an internal hard disk drive HDD e.g. EIDE SATA which internal hard disk drive may also be configured for external use in a suitable chassis not shown a magnetic floppy disk drive FDD e.g. to read from or write to a removable diskette and an optical disk drive e.g. reading a CD ROM disk or to read from or write to other high capacity optical media such as the DVD . The hard disk drive magnetic disk drive and optical disk drive can be connected to the system bus by a hard disk drive interface a magnetic disk drive interface and an optical drive interface respectively. The interface for external drive implementations includes at least one or both of Universal Serial Bus USB and IEEE 1394 interface technologies.

The drives and their associated computer readable media provide nonvolatile storage of data data structures computer executable instructions and so forth. For the computer the drives and media accommodate the storage of any data in a suitable digital format. Although the description of computer readable media above refers to a HDD a removable magnetic diskette and a removable optical media such as a CD or DVD it should be appreciated by those skilled in the art that other types of media which are readable by a computer such as zip drives magnetic cassettes flash memory cards cartridges and the like may also be used in the exemplary operating environment and further that any such media may contain computer executable instructions for performing the methods of the disclosed architecture.

A number of program modules can be stored in the drives and RAM including an operating system one or more application programs other program modules and program data . All or portions of the operating system applications modules and or data can also be cached in the RAM . It is to be appreciated that the disclosed architecture can be implemented with various commercially available operating systems or combinations of operating systems. The modules and or programs can include the API and DRT functionality for serverless collaboration.

A user can enter commands and information into the computer through one or more wired wireless input devices for example a keyboard and a pointing device such as a mouse . Other input devices not shown may include a microphone an IR remote control a joystick a game pad a stylus pen touch screen or the like. These and other input devices are often connected to the processing unit through an input device interface that is coupled to the system bus but can be connected by other interfaces such as a parallel port an IEEE 1394 serial port a game port a USB port an IR interface etc.

A monitor or other type of display device is also connected to the system bus via an interface such as a video adapter . In addition to the monitor a computer typically includes other peripheral output devices not shown such as speakers printers etc.

The computer may operate in a networked environment using logical connections via wired and or wireless communications to one or more remote computers such as a remote computer s . The remote computer s can be a workstation a server computer a router a personal computer portable computer microprocessor based entertainment appliance a peer device or other common network node and typically includes many or all of the elements described relative to the computer although for purposes of brevity only a memory storage device is illustrated. The logical connections depicted include wired wireless connectivity to a local area network LAN and or larger networks for example a wide area network WAN . Such LAN and WAN networking environments are commonplace in offices and companies and facilitate enterprise wide computer networks such as intranets all of which may connect to a global communications network for example the Internet.

When used in a LAN networking environment the computer is connected to the local network through a wired and or wireless communication network interface or adapter . The adaptor may facilitate wired or wireless communication to the LAN which may also include a wireless access point disposed thereon for communicating with the wireless adaptor .

When used in a WAN networking environment the computer can include a modem or is connected to a communications server on the WAN or has other means for establishing communications over the WAN such as by way of the Internet. The modem which can be internal or external and a wired or wireless device is connected to the system bus via the serial port interface . In a networked environment program modules depicted relative to the computer or portions thereof can be stored in the remote memory storage device . It will be appreciated that the network connections shown are exemplary and other means of establishing a communications link between the computers can be used.

The computer is operable to communicate with any wireless devices or entities operatively disposed in wireless communication for example a printer scanner desktop and or portable computer portable data assistant communications satellite any piece of equipment or location associated with a wirelessly detectable tag e.g. a kiosk news stand restroom and telephone. This includes at least Wi Fi and Bluetooth wireless technologies. Thus the communication can be a predefined structure as with a conventional network or simply an ad hoc communication between at least two devices.

Referring now to there is illustrated a schematic block diagram of an exemplary computing environment that facilitates mesh node access via the disclosed DRT API. The system includes one or more client s . The client s can be hardware and or software e.g. threads processes computing devices . The client s can house cookie s and or associated contextual information for example.

The system also includes one or more server s . The server s can also be hardware and or software e.g. threads processes computing devices . The servers can house threads to perform transformations by employing the architecture for example. One possible communication between a client and a server can be in the form of a data packet adapted to be transmitted between two or more computer processes. The data packet may include a cookie and or associated contextual information for example. The system includes a communication framework e.g. a global communication network such as the Internet that can be employed to facilitate communications between the client s and the server s .

Communications can be facilitated via a wired including optical fiber and or wireless technology. The client s are operatively connected to one or more client data store s that can be employed to store information local to the client s e.g. cookie s and or associated contextual information . Similarly the server s are operatively connected to one or more server data store s that can be employed to store information local to the servers .

Although illustrated as a client server environment the clients can be associated with the devices illustrated in including but limited to the desktop computers laptop computer s portable terminal device and servers. In other words collaboration can be obtained with server systems e.g. servers independent of a need for a service in order for the collaboration over the mesh.

What has been described above includes examples of the disclosed architecture. It is of course not possible to describe every conceivable combination of components and or methodologies but one of ordinary skill in the art may recognize that many further combinations and permutations are possible. Accordingly the novel architecture is intended to embrace all such alterations modifications and variations that fall within the spirit and scope of the appended claims. Furthermore to the extent that the term includes is used in either the detailed description or the claims such term is intended to be inclusive in a manner similar to the term comprising as comprising is interpreted when employed as a transitional word in a claim.

