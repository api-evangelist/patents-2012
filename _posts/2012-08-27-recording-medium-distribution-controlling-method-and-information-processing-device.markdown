---

title: Recording medium, distribution controlling method, and information processing device
abstract: A computer acquires a particular entry(ies) from a database that includes plural entries for each of which a key is determined; stores the particular entry(ies) into a memory provided in the computer and used as one of memories that store the database in a distributed manner; and associates a particular piece of communication endpoint information with a network interface of the computer. Each key for each particular entry belongs to a particular subset among mutually disjoint subsets of a domain of keys. The particular piece of the communication endpoint information is one of a predetermined number of pieces of the communication endpoint information and is associated with the particular subset. Each piece of the communication endpoint information logically identifies one communication endpoint, is dynamically associated with one network interface which provides access to one of the memories, and is statically associated with one of the subsets.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09424325&OS=09424325&RS=09424325
owner: FUJITSU LIMITED
number: 09424325
owner_city: Kawasaki
owner_country: JP
publication_date: 20120827
---
This application is based upon and claims the benefit of priority of the prior Japanese Patent Application No. 2011 191957 filed on Sep. 2 2011 the entire contents of which are incorporated herein by reference.

A database may be a traditional relational database RDB or may be any of other types such as a key value store KVS etc. Both of the RDB and KVS are compatible with distribution to a plurality of nodes. For example Oracle RAC Oracle real application cluster etc. are known as examples of a distributed RDB and Dynamo Cassandra etc. are known as examples of a distributed KVS.

In addition there are various types of distributed database systems. For example some distributed database systems use a distributed hash table DHT . The DHT is a technique also used in a peer to peer P2P data delivery system and various studies have been made on the DHT.

For example the following distributed data management system is proposed to equally distribute the loads to nodes in a DHT data management mechanism shared among many users.

In the distributed data management system a management unit sets up virtual nodes and allocates the process of accessing data stored in the data management system to each virtual node. Furthermore a mapping unit associates the virtual node with a node in the data management system. It is possible to adjust the load of each node by adjusting the number of virtual nodes and adjusting the mapping between a virtual node and a node.

Although the distributed database system and the network attached storage NAS are different techniques they are similar in that pieces of data are stored in nodes which are connected over a network. Furthermore a system including a plurality of nodes such as a distributed database system NAS etc. may be configured redundantly in preparation for a failure in any node. One of the themes of the study on a redundant system is a failover function.

For example relating to the NAS the following computer system is proposed to realize the optimum failover.

The computer system includes first through third computers and a storage device connected to a plurality of computers including the first through third computers over a network. When receiving from a client computer connected to the plurality of computers a request for access to the storage device the first computer executes the requested access and transmits a response to the access request to the client computer. The second computer judges whether or not a failure has occurred in the first computer acquires the load information about the second computer and acquires from the third computer the load information about the third computer. When the acquired load information fulfills a prescribed condition the second computer transmits a change request to the third computer. When the third computer receives the change request from the second computer the third computer judges whether or not a failure has occurred in the first computer.

According to an aspect of an embodiment a computer readable recording medium having stored therein a program for causing a computer to execute a distribution controlling process is provided.

The distribution controlling process includes acquiring one or more particular entries from a database that includes a plurality of entries for each of which a key is determined. The distribution controlling process also includes storing the acquired one or more particular entries into a memory that is provided in the computer and that is used as one of a plurality of memories that store the database in a distributed manner. The distribution controlling process further includes associating a particular piece of communication endpoint information with a network interface of the computer.

Each key for each of the one or more particular entries belongs to a particular subset among a plurality of mutually disjoint subsets of a domain of keys. Each key for each of the plurality of entries belongs to the domain. The particular piece of the communication endpoint information is one of a predetermined number of pieces of the communication endpoint information and is associated with the particular subset. The predetermined number is two or more.

Each piece of the predetermined number of pieces of communication endpoint information logically identifies one of communication endpoints which are as many as the predetermined number. In addition each piece of the predetermined number of pieces of communication endpoint information is dynamically associated with one network interface which provides access to one of the plurality of memories. Furthermore each piece of the predetermined number of pieces of communication endpoint information is statically associated with one of the plurality of subsets.

The object and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the invention.

The embodiments are described below with reference to the attached drawings. Specifically the outline of the present embodiment is first described with reference to . Next examples of a configuration of a network to which the present embodiment is applied are described with reference to . Then the configurations of the devices used according to the present embodiment are described with reference to and examples of data used according to the present embodiment are described with reference to . Then some processes performed by individual devices are described with reference to the flowcharts in and examples of a system operation are described with reference to the sequence diagrams in . Finally some modifications are described.

When a DB is distributed to a plurality of nodes there may arise any change in state while the DB is in service. For example any of the plurality of nodes may become faulty or the number of nodes may be changed by adding a new node.

In a distributed DB system of a certain type in which a DB is distributed to and stored in memories each of which is included in each of a plurality of nodes the nodes may exchange a kind of control information with one another to follow i.e. to track the change in state. A protocol used in exchanging the control information tends to be complicated in particular when the protocol is designed with the scalability taken into account so that a large number of nodes are allowed.

In addition a protocol used in exchanging the control information among nodes for following the change in state tends to be implemented in the application layer depending on the design of a distributed DB system. Thus implementation of the above mentioned protocol may call for complicated programming in the application layer thereby imposing a heavy load on a programmer.

On the other hand most devices having a communication function are implemented with a communication protocol for enabling communications to be appropriately performed even when the association between a communication endpoint and a network interface dynamically changes. Since a device having a communication function may be used for various purposes the communication protocol tends to be implemented in a layer lower than the application layer.

As described below in detail according to the present embodiment the mechanism in the application layer for following the change in state that may occur in a case where a DB is distributed to a plurality of nodes is simplified by using the existence of a communication protocol implemented in a layer lower than the application layer.

In the example in computers and are two nodes in a plurality of nodes and a computer is a client. The computers and are connected to one another over a network not illustrated in .

The computer includes a memory and a network interface Ia. The computer has a memory and a network interface Ib. Each of the memories and may be primary storage such as a RAM random access memory or may be secondary storage such as a hard disk device. Due to space limitations the words interface communication and endpoint may be respectively abbreviated to I F comm. and EP in some figures.

It is preferable that each of the memories and is specifically a RAM to which high speed access is enabled. However in an embodiment having no problem even when the latency in DB access is somewhat long each of the memories and may be an external storage device such as a hard disk device.

Each of the network interfaces Ia and Ib may be for example an on board network adapter or a NIC network interface card attached externally. Each of the network interfaces Ia and Ib may be realized by hardware circuits such as a processing circuit of the physical layer and a processing circuit of the MAC media access control sublayer. The physical layer and the MAC sublayer herein are those in the OSI Open Systems Interconnection reference model.

In for convenience of explanation pieces of information for respectively identifying the network interfaces Ia and Ib are expressed as Ia and Ib using the respective reference signs of the network interfaces Ia and Ib themselves. A specific example of each piece of the information for identifying each of the network interfaces Ia and Ib is a physical address also referred to as a hardware address such as a MAC address.

The DB in the distributed DB system in includes a plurality of entries and is distributed to and stored in the memories of the plurality of nodes. For each entry a key corresponding to the entry itself is determined.

For example the DB may specifically be a KVS. An entry in the KVS is a pair of a key and a value. That is the key corresponding to the entry is the key included in the entry.

Otherwise the DB may be an RDB. The RDB includes one or more tables and an entry of each table is a tuple of one or more fields. One particular field in each table is predetermined to be a field used as a key for the table. That is the key corresponding to an entry is the data of the particular field in the entry itself.

When a key corresponding to each entry is determined as described above distribution of the DB is possible based on the horizontal partitioning according to the value of the key. That is the distribution based on the horizontal partitioning is applicable to both of the KVS and the RDB. In addition when a hash value is used as a key it is possible to regard the DB as a DHT.

Let K be the domain of keys. For example when 16 bit unsigned integers are used as keys the domain K is a set of integers from 0 to 2 1. As another example when any character strings each of whose length is one or longer are allowed to be used as keys the domain K is a set of any character strings each of whose length is one or longer.

Let M be a predetermined integer being two or larger and assume that a subset Kof the domain K is appropriately defined for each j where 0 j M 1. Also assume that each subset is defined so that subsets Kand Kare mutually disjoint for any i and j where i j. In other words assume that each subset is defined so that K Kis the empty set for any i and j where i j.

The details of how each subset Kis defined are arbitrary depending on the embodiments. The value of M is also arbitrary depending on the embodiments. That is so far as the domain K is partitioned into M subsets Kto Kthat are mutually exclusive and collectively exhaustive it does not matter how the subsets Kto Kare specifically defined.

For example when the domain K is a set whose elements are integers each subset Kmay be defined by formula 2 . The function mod x y in formula 2 is a modulo function for calculating a remainder obtained when dividing x by y. 01 mod 2 

As another example using an appropriate hash function hash x for calculation of the hash value of an argument x each subset Kmay be defined by formula 3 . The definition of formula 3 is applicable regardless of which kind of a set the domain K is. 01 mod hash 3 

As the hash function hash x in formula 3 any hash function is available but it is preferable that the hash function hash x is a cryptographic hash function because the cryptographic hash function results in a highly uniform distribution of hash values.

If the uniformity of distribution of hash values is high it is expected that the horizontal partitioning according to the value of the key is well balanced. The well balanced partitioning means efficient distribution. Therefore it is preferable that the hash function hash x is a cryptographic hash function. For example an example of a cryptographic hash function is SHA 1 secure hash algorithm 1 which outputs a 160 bit hash value.

As another example each subset Kmay be defined by formula 4 or 5 if M 2holds true where B is an integer equal to or larger than one. The function ext x y z in formulas 4 and 5 is a function to extract the y th through the z th bits in the bit string x. It is assumed that the 0 th bit is the most significant bit. 02 1 ext 1 4 02 1 ext hash 1 5 

For example according to formula 4 B bits namely the L th through the L B 1 th bits in the bit string that indicates the key k are extracted. Then the key region to which the key k belongs is determined by the number expressed by the extracted B bits namely the number equal to or exceeding zero and equal to or less than 2 1 . Instead of extracting B bits from the bit string itself expressing the key k as in formula 4 formula 5 indicates extracting B bits from the bit string itself expressing the hash value of the key k.

The function ext x y z is an example of a function to extract bits at plural particular positions from the input bit string. Instead of the function to extract consecutive z y 1 bits such as the function ext x y z a function to extract bits at plural inconsecutive positions such as the second fifth and eighth bits may be used.

Each subset Kmay be defined as indicated by formula 6 . The function f in formula 6 is any mapping from the set K to a set X which satisfies formula 7 . In formulas 6 and 7 let Tbe a threshold that is an appropriately selected real number for any j where 0 j M and assume that T

According to formula 7 the function f is any mapping from the domain K of the keys to the set X that includes as its elements at least some of the real numbers equal to or larger than the threshold Tand smaller than the threshold T. Depending on the domain K of the keys the function f may be for example an identity mapping or a hash function. Depending on the embodiments the function f may be of course a particular mapping that uses at least one of a hash function especially a cryptographic hash function a modulo function and a function to extract bits at a plurality of particular positions from an input bit string.

As exemplified by formulas 2 through 7 the subsets Kto Kmay be defined based on the image of the key under a particular mapping. Note that formula 6 is a generalized formula that covers formulas 2 through 5 as described below.

Let SHA1 k be a function for obtaining a hash value from the key k according to SHA 1. When using SHA1 k as the hash function hash k in the example of formula 5 where L 0 and B 7 each subset Kis defined by formula 8 .

From another viewpoint the example of formula 8 is also an example in which the threshold Tin formula 6 is defined so that T 2 j holds true for any j where 0 j M and in which the function SHA1 k is used as the function f k in formula 6 .

The example of formula 2 is also an example in which the modulo function mod k M is used as the function f k in formula 6 and in which the threshold Tis defined so that T j holds true for any j where 0 j M. Similarly the example of formula 3 is also an example in which the function mod hash k M is used as the function f k in formula 6 and in which the threshold Tis defined so that T j holds true for any j where 0 j M. It is also obvious that each of formulas 4 and 5 is one of the specific examples of formula 6 .

Let Ka be a particular one of the subsets Kto K. All entries whose keys belong to the subset Ka are stored in the memory of the computer in step S in while the entries are stored in the memory of the computer in step S. The number of entries may be one or may be larger than one.

When the computer intends to access at least one of the entries the computer transmits a DB access request. Specifically in step S in which the entries are stored in the memory the computer transmits a DB access request to the computer . In step S in which the entries are stored in the memory the computer transmits a DB access request to the computer . The reason why the computer is able to transmit the DB access request to the computer in step S and is able to transmit the DB access request to the computer in step S is described later.

The DB access request is received by the network interface Ia of the computer . The computer accesses the memory at the DB access request and returns a DB access reply to the computer .

The DB access request is received by the network interface Ib of the computer . The computer accesses the memory at the DB access request and returns a DB access reply to the computer .

As described above a node that responds to a DB access request to an entry whose key belongs to the subset Ka is a node that stores the entry. In the description below the node storing in its local memory the entries each of whose key belongs to the subset K where 0 j M 1 is referred to a node responsible for the subset K a node in charge of the subset K or a node which takes charge of the subset K .

One node may take charge of only one subset or a plurality of subsets. Thus depending on the number of subset s covered by each node the loads may become unbalanced among nodes.

Furthermore there may be a case in which there are a large number of DB access requests to entries each of whose key belongs a certain subset and in which there are a small number of DB access requests to entries each of whose key belongs to another subset. In this case the loads may become unbalanced among nodes depending on the amount of DB access requests.

For example if the load of the computer is high and the load of the computer is low it is preferable that part of the load of the computer is transferred to the computer in order to achieve load balancing. For example for the purpose of the load balancing as described above the node responsible for the subset Ka may be changed from the computer to the computer and thereby a change in state from step S to step S may be made.

It is obvious that the change in state from step S to step S may be caused by other factors. For example the following case may arise.

In the computer is drawn in the upper part indicating step S. However in the stage in step S it is not necessary that the computer exists as a node of the distributed DB system. A change in state may be made from step S to step S by adding the computer as a new node.

In the computer is also drawn in the lower part indicating step S. However in the stage in step S it is not necessary that the computer exists as a node of the distributed DB system. That is there may be a case in which the computer takes over the charge of the subset Ka and thereby the state is changed from step S to step S. Such a case may arise for example when the computer becomes faulty immediately after step S.

As described above the takeover may be failover triggered by an occurrence of a failure or may be independent of a failure. However whatever the cause of the change in state is the computer acquires the entries from the DB when the state changes from step S to step S and stores the acquired entries in the memory

In the description above it is mentioned the computer acquires the entries from the DB . To be more specific the computer may acquire the entries from the computer . Otherwise if a certain computer which is other than the computer and is not illustrated in that is another node in the plurality of nodes has a backup copy of the entries the computer may acquire the entries from the certain computer not illustrated in .

In addition the computer which has acquired the entries further associates a particular piece of communication endpoint information with the network interface Ib of the computer . The association enables other computers for example the computer and another node in the plurality of nodes but not illustrated in to recognize that the node responsible for the subset Ka has been changed from the computer to the computer . The details of the reason are described below.

The communication endpoint information is a kind of information to logically identify a communication endpoint. For example in the communication according to the TCP IP Transmission Control Protocol Internet Protocol protocol suite the communication endpoint is logically identified by a combination of an IP address and a port number. Although not specifically described below such a port number is a port number in a transport layer protocol such as the TCP the UDP User Datagram Protocol etc. in the TCP IP protocol suite.

However it is not always necessary for a computer which intends to perform communications with a communication endpoint to acquire as the communication endpoint information both of an IP address and a port number. It may be sufficient that a computer acquires only an IP address as the communication endpoint information.

For example in a DB application for the distributed DB system illustrated in the port number may be a fixed value. When a port number is a predetermined constant any computer is able to logically recognize i.e. identify a target communication endpoint so long as the computer is able to acquire the IP address of the target communication endpoint. That is the computer is able to logically recognize the target communication endpoint by the acquired IP address and the fixed known port number.

The port number used in one application is not always limited to one specific port number. For example any port numbers being equal to or more than 7000 and equal to or less than 7020 may be used in the same single DB application. In this case any computer is able to logically identify a target communication endpoint so far as the computer is able to acquire the IP address of the target communication endpoint. That is the computer is able to logically identify the target communication endpoint by the acquired IP address and a port number appropriately selected from the range from 7000 to 7020.

Therefore the communication endpoint information may be for example only an IP address or a pair of an IP address and a port number. Anyway the communication endpoint information is a kind of information for logically identifying a communication endpoint but is not physical identification information. Accordingly it is possible to dynamically change the correspondence between the communication endpoint which is logically identified by the communication endpoint information and a physical entity.

In the present embodiment at least M pieces of communication endpoint information in the context of the M subsets Kto Kindicated by formula 1 are used to logically identify M communication endpoints. Although the details are described later with reference to etc. two or more pieces of communication endpoint information may be associated with each subset K. For example when three pieces of communication endpoint information are associated with each subset K 3M pieces of communication endpoint information for logically identifying 3M communication endpoints are used.

Each piece of communication endpoint information is statically associated with one of the M subsets Kto K. For example in the example in the communication endpoint information Pa is statically associated with the subset Ka.

Hereafter for convenience of explanation the domain K of keys is also referred to as a key space . Each of the subsets Kto Kin formula 1 is also referred to as a key region . The key region is a subspace of the key space.

The static association between the communication endpoint information and the subset of keys is stored as static association information in the computer as illustrated in in the present embodiment. Although only the computer includes the static association information in the computers and similarly may store the static association information .

In due to space limitations only the association between the key region Ka that is the subset Ka and the communication endpoint information Pa is illustrated as an example of the static association information . However the static association information statically associates each of a predetermined number of pieces for example 3M pieces when each subset Kis associated with three pieces of communication endpoint information of communication endpoint information with one of the M key regions Kto K.

In addition each piece of communication endpoint information is dynamically associated with a network interface which provides access to one of a plurality of memories that store the DB in a distributed manner.

For example in step S every entry whose key belongs to the key region Ka is stored in the memory . Therefore in step S the communication endpoint information Pa which is statically associated with the key region Ka is associated with the network interface Ia which provides access to the memory

In step S the entries are stored in the memory . Therefore in step S the communication endpoint information Pa is associated with the network interface Ib which provides access to the memory

The above mentioned dynamic association between the communication endpoint information and the network interface is stored as dynamic association information in the computer according to the present embodiment as illustrated in . In only the computer includes the dynamic association information but the computers and may also store the dynamic association information .

In due to space limitations only the association between the communication endpoint information Pa and a network interface is illustrated as an example of the dynamic association information . Specifically the dynamic association information in step S associates the communication endpoint information Pa and the network interface Ia. However since the dynamic association information is dynamically rewritable the dynamic association information in step S associates the communication endpoint information Pa with the network interface Ib. It is obvious that the dynamic association information further associates another piece of communication endpoint information with another network interface too.

As described above the communication endpoint information includes an IP address and a network interface is identified by a MAC address. Therefore for example an entry of an ARP Address Resolution Protocol table may be used as the dynamic association information which dynamically associates the communication endpoint information with a network interface.

The ARP table is also referred to as ARP cache and includes one or more entries each of which associates an IP address and a MAC address with each other. Each entry of the ARP table is created and updated based on an ARP request and an ARP reply and is deleted when it is not accessed for a predetermined time. Thus each entry of the ARP table is a preferable example of the dynamic association information for dynamically associating the IP address and the MAC address.

The entries which are acquired by the computer when the state changes from step S to step S are all entries each of whose key belongs to the subset Ka as described above. Thus upon transition from step S to step S the computer associates the communication endpoint information Pa which is statically associated with the subset Ka of which the computer is to newly take charge with the network interface Ib of the computer itself. That is the above mentioned particular piece of communication endpoint information is the communication endpoint information Pa in the example in .

As described above the network interface Ib is identified by for example a MAC address and the communication endpoint information Pa includes an IP address. Therefore the association between the communication endpoint information Pa and the network interface Ib made by the computer is able to be realized by for example the technique called IP aliasing specifically.

The IP aliasing function is implemented in some OSs operating systems . The IP aliasing function is a function to assign a plurality of IP addresses to one network interface. That is the IP aliasing function enables one MAC address to be associated with a plurality of IP addresses.

When the computer associates the communication endpoint information Pa with the network interface Ib the computer is able to recognize that the communication endpoint information Pa has been associated with the network interface Ib. That is the computer is enabled to update the dynamic association information for the following reason.

In the actual communications a message whose destination is specified by logical information such as the communication endpoint information Pa is encapsulated and included in the payload of a frame in a lower layer. Then the frame in the lower layer is transmitted. For example an IP datagram is included in the payload of an Ethernet frame and the Ethernet frame is transmitted.

Therefore before transmitting a message addressed to the communication endpoint logically identified by the communication endpoint information Pa the computer checks the physical identification information for physically identifying a network interface that serves as the communication endpoint that is logically identified by the communication endpoint information Pa. Specifically the computer refers to the dynamic association information and thereby checks the physical identification information corresponding to the communication endpoint information Pa.

If the communication endpoint information Pa is associated with any physical identification information by the dynamic association information the computer specifies the physical identification information associated with the communication endpoint information Pa as the destination of the frame in the lower layer.

On the other hand if the dynamic association information does not associate the communication endpoint information Pa with any physical identification information the computer inquires about the network interface corresponding to the communication endpoint information Pa by broadcasting. Then a computer that includes the network interface associated with the communication endpoint information Pa replies to the inquiry.

For example if an inquiry from the computer is broadcast after the computer associates the communication endpoint information Pa with the network interface Ib the computer replies to the inquiry. Then the computer receives the reply and acquires the identification information for identification of the network interface Ib as the physical identification information corresponding to the communication endpoint information Pa.

Furthermore the computer updates the dynamic association information based on the received reply. That is the computer updates the dynamic association information so as to associate the communication endpoint information Pa with the network interface Ib. Then the computer specifies the identification information physically identifying the network interface Ib as the destination of the frame according to the updated dynamic association information .

As described above the actual communication involves the process of resolving the logical identification information into the physical identification information. For the resolution an inquiry is broadcast as described above as necessary and the dynamic association information is updated based on the reply. Thus even if the association between the logical identification information and the physical identification information dynamically changes the dynamic association information is appropriately updated according to the change.

Even if the dynamic association information incidentally stays in the state in step S when the computer refers to the dynamic association information there is no problem so long as the computer performs an appropriate process es . The appropriate process es may be a timeout process and a retry process which are common in communications an aging process which is common in management of dynamic information or a combination of these processes.

For example the computer may refer to the dynamic association information to transmit the DB access request and may acquire from the dynamic association information obsolete information i.e. old information that the communication endpoint information Pa is associated with the network interface Ia. As a result the computer may specify the information for physically identifying the network interface Ia as the destination of the frame of the DB access request

However at the time when the process in step S is performed the association between the network interface Ia and the communication endpoint information Pa is already dissolved. Accordingly even if the frame of the DB access request is received at the network interface Ia of the computer the DB access request is discarded in the computer . Thus the reply to the DB access request is not returned.

That is if the computer transmits the frame of the DB access request based on the wrong resolution result according to the obsolete dynamic association information the computer is unable to obtain a reply and therefore times out. The computer is able to update the dynamic association information by performing an appropriate retry process in response to the timeout.

For example the computer may forcibly delete the association between the communication endpoint information Pa which logically identifies the destination of the DB access request for which the timeout has occurred because of the absence of a reply and the network interface Ia from the dynamic association information . Then the computer may retry the transmission of the DB access request

In this case since the dynamic association information after the forcible deletion does not associate the communication endpoint information Pa with any physical identification information the computer broadcasts an inquiry as mentioned above. As a result the dynamic association information is correctly updated. That is a new state in which the communication endpoint information Pa is associated with the network interface Ib is reflected in the dynamic association information .

When the computer determines the destination of the frame of the DB access request according to the updated dynamic association information the DB access request is then correctly received by the computer . Then the computer is able to receive from the computer a reply to the DB access request

Otherwise it is possible that the computer performs neither the above mentioned explicit timeout process nor the above mentioned explicit retry process. Instead the computer may perform the aging process on the dynamic association information thereby forcibly deleting the dynamic association information if the dynamic association information becomes obsolete.

Thus the obsolete dynamic association information which associates the communication endpoint information Pa with the network interface Ia is to be deleted in time in the aging process. Therefore when the computer intends to transmit any message which may be for example the DB access request for which the communication endpoint information Pa is specified as the destination after the deletion of the obsolete dynamic association information an inquiry is also broadcast in this case similarly to the above described case.

As a result the dynamic association information is correctly updated. Then the computer transmits the message according to the correctly updated dynamic association information . Therefore the message is received appropriately by the network interface Ib in accordance with the new state in which the communication endpoint information Pa is associated with the network interface Ib.

As described above when the computer associates the communication endpoint information Pa with the network interface Ib the computer is enabled to recognize that the communication endpoint information Pa has been associated with the network interface Ib. That is the computer is able to update the dynamic association information according to the recognized result.

Therefore while there may be a time lag from when the state changes from step S to step S to when the dynamic association information is updated the computer is able to appropriately update the dynamic association information according to the state change. Then the computer is able to transmit any message such as the DB access request to an appropriate destination according to the appropriately updated dynamic association information .

Namely by dynamically updating the dynamic association information the computer is able to correctly specify the identification information which identifies the network interface Ia as the destination of the frame of the DB access request in step S. In addition by dynamically updating the dynamic association information the computer is able to correctly specify the identification information which identifies the network interface Ib as the destination of the frame of the DB access request in step S.

As a result the DB access request is correctly received by the computer and the DB access request is correctly received by the computer . That is even if the node responsible for the key region Ka changes from the computer to the computer the computer is still able to transmit a DB access request to the node responsible for the key region Ka according to the change.

Each of the DB access requests and includes at least the fields for the following items 1 1 through 1 3 .

 1 1 Communication endpoint information for identifying the communication endpoint at the destination of the DB access request.

 1 3 The content of a request i.e. a request body indicating the content of the operation to be performed on the DB.

Specifically the communication endpoint information Pa a key k belonging to the key region Ka and appropriate request content are specified in the DB access request . Meanwhile the communication endpoint information Pa a key k belonging to the key region Ka and appropriate request content are specified in the DB access request

As clearly understood from the examples of the DB access requests and above the communication endpoint information that is specified in the DB access request is the communication endpoint information that is associated with the key region to which the key specified in the DB access request belongs by the static association information . Therefore the computer first determines the key region to which the key belongs from the key of the entry that the computer intends to access. Then by referring to the static association information the computer acquires the communication endpoint information corresponding to the determined key region and specifies the acquired communication endpoint information in the DB access request.

The computer is able to appropriately determine the key region from the key depending on how the key regions are defined. For example assume that the key regions are defined by formula 2 . In this case the constant M is known to the computer . Therefore if the key of the entry that the computer intends to access is for example the key k the computer is able to calculate the mod k M according to formula 2 and to determine the key region Ka to which the key k belongs according to the calculated result. The same holds true with the case in which the key regions are defined by any other formula.

The request content described in item 1 3 is expressed by an appropriate format depending on the specifications of the DB application used for the distributed DB system. For example as the operations to be performed on the DB the DB application may define only two types of operations that is a reading operation for reading an entry and a writing operation for writing data to an entry. In this case the request content may include a field indicating the type of operation and an optional field expressing the data to be written by the writing operation.

Depending on the DB application an inserting operation for adding a new entry and an updating operation for rewriting an existing entry may be defined instead of the writing operation. Also in this case the request content may include a field indicating the type of operation and an optional field expressing the data to be written by the inserting operation or the updating operation. Furthermore a deleting operation for deleting the existing entry may be specifiable as the request content.

Since the DB access request includes communication endpoint information a key and request content as described above a node which receives the DB access request is able to identify the entry to be accessed according to the DB access request and to perform the requested operation on the identified entry. As a result the node that receives the DB access request is able to return the result of the DB access as a DB access reply to the computer which is the sender of the DB access request.

The format of the DB access reply is arbitrary depending on an embodiment. For example the DB access reply in a case where the reading operation is requested includes the data of the entry corresponding to the key specified in the DB access request. In addition the DB access reply for the operation other than the reading operation may include for example the information indicating whether or not the operation has been successfully performed.

As understood from the explanation about according to the present embodiment the association in other words the correspondence that indicates which subset of the domain of the keys each of the plurality of memories which store the DB in a distributed manner corresponds to is not managed by direct and dynamic association. The association i.e. the correspondence is managed by indirect association.

That is a subset and a piece of the communication endpoint information are statically associated with each other. The piece of the communication endpoint information thus statically associated with the subset is dynamically associated with a network interface which provides access to a memory. Thus the subset and the memory are indirectly associated with each other.

A state change which may occur in a case where a DB is distributed to a plurality of memories is namely a change in the above described indirect association between a memory and a subset. In addition the association that is between a subset and a piece of the communication endpoint information and that is used for the indirect association between a memory and a subset is static regardless of the state change and therefore does not have to be followed. Therefore following the state change is realized by following the change in the association that is between the communication endpoint information and the network interface and that is used in indirectly associating the memory and the subset.

It is possible to follow the change in the association between the communication endpoint information and the network interface by using a communication protocol implemented in a layer lower than the application layer. Therefore according to the present embodiment it is possible to follow the state change by using the communication protocol implemented in the layer lower than the application layer. That is according to the present embodiment a complicated protocol for exchange of control information between the nodes is not required and the mechanism in the application layer for following the state change is simplified by using the existence of the communication protocol.

Next the association using the static association information and the dynamic association information is further described below in detail with reference to . illustrates an example of the association among a key region a communication endpoint and a node.

In a donut shaped gray portion indicates the key space K that is the domain K of the keys . The key space K is partitioned into 16 mutually disjoint key regions Kto K that is mutually disjoint subsets Kto Kof the domain K in the example in . In the example in the value of M in formula 1 is 16.

As described above the static association information statically associates for each key region K where 0 j M 1 the key region Kand the communication endpoint information Pwith each other. The association between the key region Kand the communication endpoint information Pis in other words the association between the key region Kand the communication endpoint identified by the communication endpoint information P.

In pieces of the communication endpoint information Pto Pare expressed by black circles. The static association between the key region Kand the communication endpoint information P associated by the static association information is indicated by the solid line between the black circle and the gray block.

On the other hand the dynamic association information dynamically associates the communication endpoint information with the network interface. That is the dynamic association information dynamically associates the key region which is statically associated with the communication endpoint information with the network interface through the communication endpoint information.

In addition each individual network interface statically corresponds to one of a plurality of nodes. Therefore the dynamic association information also associates a key region and a node with each other through the association between the communication endpoint information and the network interface. That is according to the association between the communication endpoint information which is statically associated with a key region and the network interface included in a node the dynamic association information also indicates that this node takes charge of this key region.

The oval in broken line indicates a node in . That is in the example in the distributed DB system includes five nodes Nto N. Furthermore the dynamic association by the dynamic association information corresponds to the association between the oval and the gray block s in .

Specifically in the example in the node Ntakes charge of the key regions K K and K. That is the node Nassociates each of three pieces of the communication endpoint information P P and Pcorresponding to the three key regions K K and Kwith the network interface included in the node Nitself. In addition the node Nstores every entry whose key belongs to any of the key regions K K and Kin the memory included in the node Nitself.

Furthermore in the example in the node Ntakes charge of the key regions K K K and K. That is the node Nassociates each of four pieces of the communication endpoint information P P P and Pcorresponding to the four key regions K K K and Kwith the network interface included in the node Nitself. In addition the node Nstores every entry whose key belongs to any of the key regions KK K and Kin the memory included in the node Nitself.

In addition in the example in the node Ntakes charge of the key regions K K K and K. That is the node Nassociates each of four pieces of the communication endpoint information P P P and Pcorresponding to the four key regions K K K and Kwith the network interface included in the node Nitself. In addition the node Nstores every entry whose key belongs to any of the key regions K K K and Kin the memory included in the node Nitself.

Furthermore in the example in the node Ntakes charge of the key regions K K and K. That is the node Nassociates each of three pieces of the communication endpoint information P P and Pcorresponding to the three key regions K K and Kwith the network interface included in the node Nitself. In addition the node Nstores every entry whose key belongs to any of the key regions K K and Kin the memory included in the node Nitself.

In the example in the node Ntakes charge of the key regions Kand K. That is the node Nassociates each of two pieces of the communication endpoint information Pand Pcorresponding to the two key regions Kand Kwith the network interface included in the node Nitself. In addition the node Nstores every entry whose key belongs to any of the key regions Kand Kin the memory included in the node Nitself.

For convenience of illustration in illustrates an example in which each node is responsible for a plurality of consecutive key regions. However the key regions for which an individual node is responsible may be inconsecutive. For example as a result of a dynamic change in the configuration of nodes the node Nmay be responsible for the key regions K K K and Kat a certain time point.

The client C in may be for example the computer illustrated in the computer or the computer . Therefore the client C stores the static association information in .

Therefore the client C is able to statically determine the communication endpoint at the destination of a DB access request from the key corresponding to the entry that the client C intends to access. That is one of the merits of the present embodiment lies in that the client C is able to directly determine the communication endpoint at the destination of the DB access request.

That is it is not necessary for the client C to transmit an inquiry to another computer such as a gateway server etc. in order to determine from the key the communication endpoint at the destination of the DB access request. That is according to the present embodiment it is not necessary to provide a computer such as a gateway server etc. for managing which node takes charge of which key region. Therefore in the present embodiment various problems which may occur in other distributed DB systems as described below are avoidable.

In a distributed DB system including a gateway server for determining the destination of a DB access request from a key the gateway server is a single point of failure SPoF of the entire distributed DB system. In addition the gateway server is also a bottleneck of the performance of the entire distributed DB system. Even if there are two or more gateway servers it is certain that these gateway servers are bottlenecks. That is the gateway server s may cause problems in both fault tolerance and performance.

Furthermore in the above mentioned distributed DB system including the gateway server s a client transmits an inquiry about the node at the destination of a DB access request to the gateway server and the gateway server returns a reply to the client. Then the client specifies the node described in the reply from the gateway server as the destination of the DB access request and transmits the DB access request to the destination. Therefore the latency of the DB access is prolonged due to the time taken in transmitting the inquiry from the client to the gateway server and the time taken in transmitting the reply from the gateway server to the client.

Even if the gateway server does not return a reply to the client upon receipt of the inquiry from the client but operates as follows the unpreferable effect on the latency is not avoidable. That is even if the gateway server receives the DB access request from the client determines a node from the DB access request and forwards the DB access request to the determined node the latency of the DB access becomes worse by using the gateway server because the communication from the client to the gateway server still remains.

However according to the present embodiment without the gateway server the client itself is able to determine the communication endpoint at the destination of the DB access request from the key and some pieces of known information only. For example when each key region Kis defined by formula 3 the pieces of known information include the value of the constant M and the definition of the function mod hash k M for determining a key region from the key. Therefore according to the present embodiment the above described various problems which are caused by a gateway server are avoidable.

In addition there may be a distributed DB system in which a large number of clients hold the information for direct and dynamic association between a node and a key region instead of a small number of gateway servers holding such information as described above. However in the system in which a large number of clients hold the dynamic information it is necessary to provide a complicated protocol for maintaining the information held by each of a large number of clients in the latest state and to exchange a large number of control messages according to the protocol. Therefore especially when the number of exchanged control messages is much larger than the number of nodes the overhead due to the exchange of control messages may have an unpreferable effect on the performance of the entire distributed DB system. Therefore it is practically very difficult for a large number of clients to each hold dynamic information while maintaining it in the latest state.

As described above various problems may occur in other distributed DB systems. However according to the present embodiment described with reference to the key region and the communication endpoint are statically associated with each other by the static association information . Therefore the above mentioned various problems are avoidable. That is according to the present embodiment the maintenance cost of the static association information is zero and deterioration such as that in the fault tolerance the performance the latency etc. that may be caused by introducing the gateway server does not arise.

Next examples of a network to which the present embodiment is applied are described with reference to .

The deployment server initializes the nodes Nthrough Nwhen deploying the distributed DB system. The initialization includes some processes such as the installation of an OS and the installation of a program for causing a computer to operate as a node of the distributed DB system. In addition the deployment server may further set the association between each node and the key region in the initial state. Furthermore the deployment server may perform various processes such as monitoring the load balance among the nodes Nthrough Netc. However the deployment server may be omitted.

For example the computer in may be one of the nodes Nthrough N. The computer in may be another one of the nodes Nthrough N.

In addition the computer in may be the client . As another example the computer as a client at the source of the DB access request may be one of the nodes Nthrough Nother than the computers and

For example when a node responsible for a key region is changed a certain node may request entries from another node and this request is also a kind of the DB access request. Therefore the computer in may be one of the nodes Nthrough N.

Additionally the router is connected to the Internet and another client is also connected to the Internet . The computer in may be the client external to the broadcast domain to which the nodes Nthrough Nbelong.

The broadcast domain includes a router and the broadcast domain includes a router and an application server . The routers and are connected to each other.

The routers and are each connected to the Internet . A client PC personal computer is also connected to the Internet .

For example the computer in may be one of the nodes Nthrough N. The computer in may be another one of the nodes Nthrough N.

Furthermore the computer in may be the client PC . It is obvious that as described with reference to each of the nodes Nthrough Nmay also operate as a client for other nodes as with the computer in .

As another example the application server may accept a request from the client PC through the Internet and the router . The distributed DB system may be used as a back end of a Web application provided by the application server .

In this case the application server may transmit the DB access request to any node at a request from the client PC . That is the computer in may be the application server . Depending on the content of the DB access reply received from the node the application server may return a reply for example a page written in HTML hypertext markup language to the client PC .

Next the configurations of the node and the client according to the present embodiment are described below with reference to .

The node includes a local store a network interface and a communication processing unit . The communication processing unit holds an ARP table and an interface configuration file . Due to space limitations the abbreviation I F config file is used for the interface configuration file in . The node further holds a correspondence table .

The node includes one key region management unit for each key region for which the node is responsible. That is the node includes one key region management unit for each communication endpoint for which the node is responsible. In more detail the node includes one key region management unit for each IP address dynamically assigned to the network interface .

In the example in for convenience of explanation it is assumed that the node takes charge of three key regions corresponding to three pieces of communication endpoint information. Therefore the node includes three key region management units through

Since the key region management units through are similarly configured only the detailed inside of the key region management unit is illustrated in . Specifically the key region management unit includes a read write processing unit an acquisition control unit a supply control unit an association unit and a monitoring request unit . The monitoring request unit holds a requested node list .

Each block in the node above is described in detail as follows. Unless specifically described the reference to layers is as in RFC request for comments based on a model in which four layers that is the link layer the Internet layer the transport layer and the application layer are included.

The local store stores entries each corresponding to one of one or more key regions for which the node is responsible. That is the local store corresponds to the memories and in . The local store is preferably a RAM but may also be secondary storage such as a hard disk device etc.

The network interface is similar to the network interfaces Ia and Ib in . That is the network interface performs processes in the link layer. The node communicates with other devices through the network interface and the communication processing unit .

The communication processing unit may be realized by using part of an OS. For example the communication processing unit may be implemented using a standard library of a TCP IP protocol stack. To realize the communication processing unit an Ethernet driver may be further used. That is the communication processing unit performs processes in the transport layer and the Internet layer and also performs processes for interfacing the Internet layer and the link layer.

In the description below for convenience of explanation it is assumed that the communication through the communication processing unit and the network interface is a communication according to the TCP IP protocol suite and that the Ethernet is used in the link layer.

The communication processing unit not only provides the infrastructure of the communication according to the TCP IP protocol suite as described above but also sorts messages received from other devices and forwards each message to an appropriate module. That is the communication processing unit also performs the sorting forwarding process in the application layer.

The message received by the node from another device may be for example any of the massages listed in items 2 1 through 2 6 below.

Depending on the type specified in the header of a received message the communication processing unit may judge which type of the above listed messages 2 1 through 2 6 a received message falls under. The communication processing unit may then sort the received message and forward it to an appropriate block. For example when the type indicates an ACK the communication processing unit outputs the received message to the monitoring unit .

The DB access requests include for example read requests for reading data from the DB and write requests for writing data to the DB.

According to the present embodiment a copy request for copying all entries corresponding to a certain key region is one of the DB access requests. Furthermore a takeover request for obtaining data of all entries corresponding to a certain key region in order to take over this key region to be more specific in order to take over a communication endpoint corresponding to this key region from the node at the destination of this takeover request is also one of the DB access requests. The copy request is a request for obtaining only a copy of a set of the entries without taking over the communication endpoint from the node at the destination of the copy request.

As described later in detail a copy request and a takeover request are used when the node responsible for a certain key region is changed. The DB access reply listed in item 2 2 above is specifically a reply to a copy request or a reply to a takeover request hereafter these replies are referred to as a copy reply and a takeover reply .

As illustrated in a key is specified for a read request and also for a write request. For a copy request and a takeover request information capable of identifying a key region is specified. For example this information may be an index such as the subscript j in formulas 1 through 6 and 8 for identifying a key region or may be communication endpoint information statically associated with a key region.

A pair of the destination IP address and the destination port number of a read request or a write request in which a certain key is specified is a pair of an IP address and a port number that identifies a communication endpoint corresponding to the key region to which the specified key belongs. Similarly a pair of the destination IP address and the destination port number of a copy request or a takeover request in which a certain key region is specified is a pair of an IP address and a port number that identifies a communication endpoint corresponding to the specified key region.

The key region management units through correspond to different pieces of communication endpoint information. For example the key region management unit may initialize a TCP socket by calling i.e. invoking the function of the communication processing unit while specifying the communication endpoint identified by the communication endpoint information to be more specific a pair of an IP address and a port number corresponding to the key region management unit . As described later for details the monitoring unit uses a fixed IP address not associated with any key region.

Therefore the communication processing unit is able to sort a received message which is one of the messages 2 1 through 2 6 and forward it to an appropriate one of the key region management units through or to the monitoring unit depending on the destination IP address and the destination port number.

Furthermore the communication processing unit may judge the subtype of the received DB access request. If the subtype indicates a read request or a write request the communication processing unit outputs the read request or the write request to the read write processing unit in the key region management unit that corresponds to the destination IP address. If the subtype indicates a copy request or a takeover request the communication processing unit outputs the copy request or the takeover request to the supply control unit in the key region management unit that corresponds to the destination IP address.

As a result for example a read request or a write request in which a key which belongs to the key region corresponding to the key region management unit is specified is outputted to the read write processing unit in the key region management unit . Similarly a copy request or a takeover request in which the key region corresponding to the key region management unit is specified is outputted to the supply control unit in the key region management unit

In addition the communication processing unit includes the ARP table and the interface configuration file .

The ARP table is used as the dynamic association information illustrated in . The ARP table includes an entry hereafter referred to also as an ARP entry for each IP address of another device. Each ARP entry associates an IP address with a MAC address that identifies the network interface to which this IP address is assigned i.e. allocated .

The interface configuration file associates the MAC address that identifies the network interface of the node itself with the IP address assigned to the network interface . By the IP aliasing function a plurality of IP addresses may be associated with one network interface . The interface configuration file is for example a configuration file located at a particular path such as etc sysconfig network scripts ifcfg eth0 which is predetermined by the OS.

The correspondence table is a specific example of the static association information in . The detailed data example of the correspondence table is described later with reference to . All of the key region management units through and the monitoring unit are allowed to refer to the correspondence table .

The key region management units through may be realized by for example different threads or different processes. The key region management units through operate in the application layer. The operation of each unit in the key region management unit is described below.

The read write processing unit receives a DB access request from another device through the network interface and the communication processing unit and accesses the local store according to the DB access request. Then the read write processing unit returns a result of the DB access as a DB access reply to the source device of the DB access request through the communication processing unit and the network interface .

Since the communication processing unit performs the sorting forwarding process as described above what is processed by the read write processing unit in the key region management unit is limited to the read request or the write request in which a key belonging to the key region corresponding to the key region management unit is specified.

When the received DB access request is a read request the read write processing unit reads the content of an entry stored in the local store . When the received DB access request is a write request the read write processing unit performs a writing operation for example creation of a new entry or rewriting of an existing entry to the local store according to the DB access request. Then the read write processing unit returns the result of the reading operation or the writing operation as a DB access reply.

The acquisition control unit transmits a copy request or a takeover request to another node through the communication processing unit and the network interface . Then the acquisition control unit acquires every entry that is included in the distributed DB and that corresponds to a certain key region as a reply to the copy request or the takeover request from the above mentioned other node through the communication processing unit and the network interface . Then the acquisition control unit adds the all acquired entries to the local store .

For example if it is determined that the node newly takes charge of a certain key region K the node may generate a thread for a new key region management unit corresponding to the key region K. For convenience of explanation it is assumed that the thread for the key region management unit is newly generated. Then the acquisition control unit of the key region management unit transmits the copy request or the takeover request in which the key region Kis specified acquires all entries corresponding to the key region K and adds the all acquired entries to the local store .

In contrast the supply control unit replies to the copy request or the takeover request from another node and thereby supplies a copy of a set of the entries in the DB to the above mentioned other node. That is the supply control unit receives the copy request or the takeover request through the network interface and the communication processing unit . Then the supply control unit reads from the local store all entries corresponding to the key region specified in the copy request or the takeover request. Furthermore the supply control unit transmits all the read entries to the source node of the copy request or the takeover request through the communication processing unit and the network interface .

In addition the association unit performs the process for updating the interface configuration file . That is the association unit directly rewrites the interface configuration file or instructs the communication processing unit to rewrite the interface configuration file .

When the node is determined to take charge of a new key region or when the node is released from the responsibility for the key region which the node has taken charge of the association i.e. the correspondence between the network interface and the communication endpoint changes. If the association between the network interface and the communication endpoint changes the association unit performs the process for updating the interface configuration file . As a result the change in the association is reflected in the interface configuration file .

Specifically if the node is determined to take charge of a new key region the acquisition control unit specifies to the association unit the IP address included in the communication endpoint information corresponding to the new key region. Then the association unit updates the interface configuration file so as to associate the IP address specified from the acquisition control unit with the MAC address of the network interface . The update of the interface configuration file may be directly performed by the association unit or may be indirectly performed through the communication processing unit .

In addition after the reply to the takeover request the supply control unit instructs the association unit to release i.e. to dissolve the association between the IP address corresponding to the key region management unit including the supply control unit itself and the network interface . Then the association unit updates the interface configuration file so as to release the association between the IP address specified by the supply control unit and the MAC address of the network interface . The update of the interface configuration file may be directly performed by the association unit or may be indirectly performed through the communication processing unit .

As described above the association unit directly or indirectly updates the interface configuration file according to the instruction from the acquisition control unit or the supply control unit . That is the association unit performs control to update the association between the network interface and the communication endpoint.

In the present embodiment alive monitoring is performed among nodes. The monitoring request unit and the monitoring unit are modules for the alive monitoring. The monitoring unit also operates in the application layer.

Specifically the monitoring request unit in the key region management unit requests one or more other nodes to monitor the communication endpoint corresponding to the key region management unit . The monitoring request is transmitted from the monitoring request unit through the communication processing unit and the network interface .

In addition the monitoring request unit holds in the requested node list the information for identifying each of the one or more other nodes to each of which the monitoring request unit has transmitted the monitoring request. A specific example of the requested node list is described later with reference to .

On the other hand the monitoring unit receives a monitoring request from another node through the network interface and the communication processing unit . The monitoring request includes the communication endpoint information for example a pair of an IP address and a port number that identifies the communication endpoint to be monitored. That is the monitoring request includes the communication endpoint information that identifies the communication endpoint statically associated with the key region for which the node that requests the monitoring is responsible.

Upon receipt of the monitoring request the monitoring unit registers i.e. enters the communication endpoint information that identifies the communication endpoint to be monitored in the target node list . Then according to the monitoring request the monitoring unit transmits a keep alive message which is a control message for monitoring. The keep alive message is addressed to the communication endpoint to be monitored and is transmitted through the communication processing unit and the network interface . The keep alive message is transmitted repeatedly at appropriate intervals.

Each time the keep alive message is transmitted the monitoring unit monitors whether or not a reply that is an ACK to the keep alive message is received through the network interface and the communication processing unit within a predetermined time. Then if the ACK is not received within the predetermined time the monitoring unit recognizes that a failure has occurred in the node that is monitored.

If the monitoring unit recognizes that a failure has occurred in the node that is monitored the monitoring unit determines that the node newly takes charge of the key region corresponding to the communication endpoint that is monitored. Then the monitoring unit generates a thread for a new key region management unit corresponding to this key region.

For convenience of explanation for example assume that the key region Kcorresponds to the communication endpoint that is monitored and also assume that a thread for the key region management unit is newly generated corresponding to the key region K. In this case the monitoring unit notifies the acquisition control unit in the key region management unit that it is determined that the node newly takes charge of the key region K. Upon receipt of the notification the acquisition control unit transmits a copy request or a takeover request as described above and notifies the association unit of the IP address included in the communication endpoint information corresponding to the key region K.

The client includes a network interface and a communication processing unit and the communication processing unit holds an ARP table . Furthermore the client includes a DB request processing unit and the DB request processing unit holds a correspondence table . The client executes an application .

The network interface is similar to the network interfaces Ia and Ib in . That is the network interface performs processes in the link layer. The client communicates with other devices through the network interface and the communication processing unit .

The communication processing unit may be part of an OS and may be implemented by a standard library of a TCP IP protocol stack for example. To realize the communication processing unit an Ethernet driver may be further used. That is the communication processing unit performs processes in the transport layer and the Internet layer and also performs processes for interfacing the Internet layer and the link layer.

In the description below for convenience of explanation it is assumed that the communication through the communication processing unit and the network interface is a communication according to the TCP IP protocol suite and that the Ethernet is used in the link layer.

The ARP table is used as the dynamic association information in . The ARP table includes an entry for each network interface of another device and each entry associates an IP address and a MAC address with each other.

The DB request processing unit may be implemented as a library or middleware for providing the application with an interface for DB access. The DB request processing unit and the application operate in the application layer.

The DB request processing unit receives the DB access request from the application and transmits the DB access request through the communication processing unit and the network interface . Then the DB request processing unit receives the DB access reply to the DB access request through the network interface and the communication processing unit and returns the content of the DB access reply to the application .

The correspondence table is a specific example of the static association information in and is identical to the correspondence table in . The DB request processing unit uses the correspondence table in determining the destination of the DB access request.

Specifically the DB request processing unit acquires the communication endpoint information by referring to the correspondence table based on the key region to which the key specified in the DB access request received from the application belongs. For example when the communication endpoint information is expressed by a pair of an IP address and a port number the DB request processing unit transmits as a DB access request a packet in which the acquired IP address is set as its destination IP address and the acquired port number is set as its destination port number.

The computer in includes a CPU central processing unit a ROM read only memory a RAM and a network interface . The computer further includes an input device an output device a storage device and a drive device of a portable storage medium . The above mentioned components of the computer are connected to one another through a bus .

The CPU loads a program into the RAM and executes the program using the RAM as a work area. Depending on some embodiments the general purpose CPU may be replaced with or may be used in combination with a dedicated hardware circuit such as an ASIC application specific integrated circuit . The RAM is more specifically a DRAM dynamic random access memory for example.

The program executed by the CPU may be stored in advance in the ROM or in the storage device . As another example the program may be downloaded from a network through the network interface and then may be copied to the storage device .

As another example the program may be stored in the portable storage medium . The stored program may be provided and then may be read by the drive device . The program read from the portable storage medium by the drive device may be loaded directly into the RAM or may be temporarily copied to the storage device followed by being loaded from the storage device into the RAM .

The portable storage medium may be any of an optical disc such as a CD compact disc a DVD digital versatile disc etc. a magneto optical disk a magnetic disc a non volatile semiconductor memory card etc. A node or a client may be a computer without the drive device .

In addition the network interface is a communication interface device for communication over a network. The network interface may be an on board network adapter or a NIC attached externally. The network interface provides a communication function through for example a wired LAN a wireless LAN or both. The network interface includes for example one or more hardware circuits e.g. circuits so called a PHY chip a MAC chip etc. .

Although illustrates only one network interface the computer may include a plurality of network interfaces . For example the computer including two network interfaces may be used as a node. In this case one or more IP addresses may be dynamically assigned to each of the two network interfaces .

The input device is for example a keyboard a pointing device such as a mouse a touch screen etc. a microphone or a combination of them. The output device is for example a display a speaker or a combination of them. The display may be the touch screen. The input device and the output device may be omitted. For example the input device and the output device may be omitted in a case where the computer is used as a node and where a human administrator performs operations on the node through the console of the deployment server .

The storage device is a non volatile storage device and may be for example a semiconductor memory such as a flash memory etc. a hard disk device or a combination of them. The ROM the RAM the storage device and the portable storage medium are examples of a computer readable storage medium i.e. a computer readable recording medium . These computer readable storage media are tangible storage media and not transitory media such as a signal carrier.

When the computer is used as the node illustrated in each block in is realized by the hardware in as follows for example.

The local store may preferably be the RAM but there may also be a case in which the local store is the storage device . The network interface may be the network interface . The communication processing unit may be realized by the CPU that executes a program the RAM that holds the ARP table and the storage device that holds the interface configuration file . The correspondence table may be stored in advance in the ROM or the storage device then may be read out to the RAM and may be held therein.

Each of the key region management units through may be realized by the CPU and the RAM . That is the read write processing unit the acquisition control unit the supply control unit and the association unit may be realized by the CPU that executes a program. The monitoring request unit may be realized by the CPU that executes a program and the RAM that holds the requested node list .

In addition the monitoring unit may also be realized by the CPU that executes a program and the RAM that holds the target node list .

When the computer is used as the client in each block in is realized by the hardware in as follows for example.

The network interface may be the network interface . The communication processing unit may be realized by the CPU that executes a program and the RAM that holds the ARP table .

The correspondence table may be stored in advance in the ROM or the storage device then may be read out to the RAM and may be held therein. The DB request processing unit may be realized by the CPU that executes a program and the RAM that holds the correspondence table .

Described next is various types of data used in the distributed DB system according to the present embodiment. illustrates examples of various types of data. Due to space limitations some abbreviations are used in .

A correspondence table is a specific example of the static association information in . Each of the correspondence table in and the correspondence table in may be specifically the correspondence table in .

Each entry of the correspondence table corresponds to one key region. Each entry includes fields named a key region index a first communication endpoint a second communication endpoint and a third communication endpoint .

The correspondence table is an example for a case where the domain K of the keys is partitioned into 16 key regions Kthrough Kas in the example in that is a case where M 16 . Therefore the key region index exemplified in the correspondence table ranges from 0 to 15. For example the entry whose key region index is j where 0 j 15 corresponds to the key region K.

According to the present embodiment the data corresponding to one key region Kis held by each of three nodes. Therefore each entry of the correspondence table includes the fields of the first communication endpoint through the third communication endpoint each of which indicates a piece of the communication endpoint information corresponding to the key region Kin each of the three nodes. The reason for holding the same data corresponding to one key region Kin each of the three nodes is described as follows.

Assume that entries corresponding to a certain key region Kare held by only one node. Such a situation is not preferable because the entries corresponding to the key region Kmay be lost when the one node becomes faulty. Therefore it is preferable that two or more nodes each hold the entries corresponding to the key region K.

In addition when the entries corresponding to the key region Kare held by each of only two nodes there is the possibility of a secondary failure. To enhance the fault tolerance of the entire distributed DB system to the secondary failure the entries corresponding to the key region Kare held by each of three nodes according to the present embodiment.

For example assume that the nodes Nand Neach hold the entries corresponding to the key region K and that a failure occurs in the node Nat a certain time point. As a result of the failover accompanying the failure occurred in the node N for example the node Nmay newly hold the entries corresponding to the key region K. In this case since the node Nis unable to acquire the entries corresponding to the key region Kfrom the faulty node N the node Ntries to acquire the entries corresponding to the key region Kfrom the node N which is normal.

However for example if the hardware of the node Nand that of the node Nare substantially of the same model and have been released around the same time the service life of the node Nand that of the Nare substantially the same. Therefore it is considered that when the probability of a failure in the node Nbecomes high the probability of a failure in the node Nalso becomes high. Meanwhile the load of the process of transmitting all entries corresponding to the key region Kto the node Nis not small if the DB is large. That is there is the possibility that a heavy load due to the process for the failover may be applied to the node N whose service life is expected to expire soon. As a result there may occur a secondary failure namely another failure may occur in the node Nbefore the completion of the failover.

Therefore according to the present embodiment three nodes each hold the same data corresponding to one key region K. For example assume that the three nodes N N and Neach hold the entries corresponding to the same key region K. Under this assumption data is recoverable in most cases even if a secondary failure occurs i.e. even if a failure occurs in the node Nduring the failover accompanying a failure in the node N .

The reason why the data is recoverable is because it is rare that the three nodes N N and Nbecome faulty simultaneously. That is even if the above exemplified secondary failure occurs in the node N the node Nstill remains normal in most cases. Therefore the node Nis able to acquire all entries corresponding to the key region Kfrom the node N thereby completing the failover.

As with the failover from the node Nto the node N the failover from the node Nto the node Nis also feasible. Alternatively the node Nmay acquire all entries corresponding to the key region Kfrom the node N which has completed the failover from the node N.

Anyway the entire distributed DB system is able to recover to the state in which three nodes specifically the node N N and N each hold the entries corresponding to the same key region K. Thus excellent fault tolerance is realized by three nodes holding the same data corresponding to one key region K.

For example in the example of the correspondence table in in the entry whose key region index is 1 the first communication endpoint is identified by a pair of an IP address and a port number namely 192.168.254.1 7000 the second communication endpoint is identified by a pair of an IP address and a port number namely 192.168.254.17 7000 and the third communication endpoint is identified by a pair of an IP address and a port number namely 192.168.254.33 7000 .

 4 1 The first node for holding the entries corresponding to the key region Kis a node logically identified by the communication endpoint information of 192.168.254.1 7000 .

 4 2 The second node for holding the entries corresponding to the key region Kis a node logically identified by the communication endpoint information of 192.168.254.17 7000 .

 4 3 The third node for holding the entries corresponding to the key region Kis a node logically identified by the communication endpoint information of 192.168.254.33 7000 .

There may be priorities among the three nodes each holding the entries corresponding to the same key region K. Alternatively it is possible that such priorities are not set. According to the present embodiment it is assumed that the node at the communication endpoint identified by the communication endpoint information in the first communication endpoint field has the highest priority and the node at the communication endpoint identified by the communication endpoint information in the third communication endpoint field has the lowest priority. In the flowchart in described later access is performed in the order from the first communication endpoint according to the above mentioned priorities.

The example of the correspondence table is an example for the case in which all nodes belong to one broadcast domain as illustrated in and the client also belong to the same broadcast domain. Therefore each IP address included in each piece of the communication endpoint information in the correspondence table is a private IP address. However it is obvious that a global IP address may be used in identifying a communication endpoint depending on some embodiments.

In addition in the example of the correspondence table the port number in each of 48 3 16 pieces of the communication endpoint information is the same value 7000 . However depending on some embodiments p where 2 p 48 different port numbers may be used for the 48 pieces of the communication endpoint information.

As another example when the port number is a constant as in the case of the correspondence table pieces of the communication endpoint information held by the correspondence table may be expressed by IP addresses only. When the port number is a constant a pair of an IP address and the constant port number is capable of uniquely identifying a communication endpoint. Thus it is acceptable that only the IP addresses are stored in the correspondence table .

An ARP table is a specific example of the dynamic association information in . The ARP table in and the ARP table in are tables in a format that is illustrated with the ARP table . Each entry of the ARP table associates an IP address and a MAC address with each other.

Although omitted in with each entry a counter for counting down the lifetime or the last modified time of this entry is associated. The counter or the last modified time is used for the aging process. For example each entry of the ARP table is cleared i.e. deleted if this entry is not used at all within a predetermined time period for example two minutes . When an entry is used that is referenced or updated the counter is reset to indicate the predetermined time period or the current time is set again as the last modified time.

Furthermore each entry of the ARP table may be held for a predetermined time period for example ten minutes at most regardless of whether this entry is used or not. That is with each entry a counter for counting down the lifetime left until the maximum time period for holding this entry may be further associated or the creation time of this entry may be further associated.

For example for the first entry in the IP address of 192.168.254.1 and the MAC address of 00 23 26 6A C2 4C are associated with each other. Therefore with the correspondence table taken into consideration the first entry indicates that the node including the network interface identified by the MAC address of 00 23 26 6A C2 4C currently takes charge of the key region K.

The distributed DB which is distributed to and stored in individual memories of a plurality of nodes may be an RDB or a KVS. For convenience of explanation it is assumed that the distributed DB of the present embodiment is a KVS. A KVS in illustrates some entries extracted from the entries that a certain node which is one of all nodes for the KVS being a distributed DB stores in its local store corresponding to a certain key region.

Each entry of the KVS is a pair of a key and a value and two entries are exemplified in . In the first entry the key is def and the value is DEF . In the second entry the key is ghi and the value is GHI .

A target node list in is a specific example of the target node list in . That is each element of the target node list is the information for identifying a node to be monitored by the monitoring unit of the node . Each element of the target node list is specifically a piece of the communication endpoint information for identifying the communication endpoint to be monitored.

Furthermore a requested node list in is a specific example of the requested node list in . That is each element of the requested node list is the information for identifying another node that has been requested by the monitoring request unit to monitor the communication endpoint assigned to the node . Each element of the requested node list is specifically a piece of the communication endpoint information for identifying the communication endpoint.

According to the present embodiment in addition to the IP address whose assignment is dynamically changed that is the IP address appearing on the correspondence table a fixed IP address for maintenance is assigned to each node. For example when the distributed DB system includes eight nodes as illustrated in eight fixed IP addresses of 192.168.254.128 through 192.168.254.135 not appearing on the correspondence table may be used.

A frame is an example of the frame used for a DB access request a DB access reply etc. in the present embodiment. To be more specific the frame is an Ethernet frame.

The frame includes a MAC header a frame payload and an FCS frame check sequence for error detection. The frame payload includes an IP datagram and the IP datagram includes an IP header and an IP payload.

In the example in the IP payload includes a TCP segment. In some embodiments the IP payload may include a PDU protocol data unit of a protocol other than the TCP in the transport layer such as a UDP segment etc.

The TCP segment includes a TCP header and a TCP payload. The TCP payload includes a PDU in the application layer.

In the present embodiment the PDU in the application layer is specifically a PDU used in the communication between nodes or the communication between a node and a client in the DB application for the distributed DB system. The DB application specifically corresponds to the portions listed in the following items 5 1 and 5 2 .

 5 1 The correspondence table the key region management units through and the monitoring unit all of which are included in the node in .

 5 2 The application and the DB request processing unit both of which are included in the client in .

In the description below for convenience of explanation the PDU in the application layer is referred to as a DB packet. The DB packet includes a header and a payload. In the following descriptions for convenience of explanation the header of the DB packet and the payload of the DB packet are respectively referred to as a DB header and a DB payload.

For example the DB header may include fields of a type a subtype etc. and may further include a field of an identification number assigned to each request which may be a DB access request for example. In the DB header of a reply to a certain request the identification number of the certain request may be set. This enables the source device of requests to judge to which request the received reply corresponds. If the frame is a frame for the DB access request in the DB payload includes the fields of the key and the request content in .

As described above the frame includes encapsulated PDUs of upper layers. Therefore the frame is specifically formatted so as to arrange the MAC header the IP header the TCP header the DB header the DB payload and the FCS in this order as illustrated in .

It is obvious that when the DB payload is long one DB packet may be fragmented into a plurality of IP datagrams by IP fragmentation and thereby a plurality of frames may be transmitted. However exemplifies the unfragmented frame for simple explanation.

The details of the MAC header the IP header and the TCP header are well known. Therefore the detailed explanation of the MAC header the IP header and the TCP header is omitted here but some points related to the present embodiment are described below.

The MAC header includes a source MAC address and a destination MAC address. The IP header includes a source IP address and a destination IP address. The TCP header includes a source port number and a destination port number. Some embodiments may use the UDP instead of the TCP. The UDP header similarly includes a source port number and a destination port number.

The communication endpoint at the destination of a DB packet is identified by a pair of a destination IP address and a destination port number. For example when the frame is a frame for the DB access request in the communication endpoint specified in the DB access request is specifically expressed by a destination IP address field in the IP header and a destination port number field in the TCP header.

For simple explanation it is assumed that all nodes and a client s belong to the same broadcast domain. In this case the destination MAC address is a value acquired from the destination IP address by address resolution according to the ARP and the source MAC address is a MAC address that identifies a network interface from which the frame is transmitted. On the other hand when the frame is relayed by one or more routers the MAC header is rewritten by each router.

The source port number is determined by the DB application. The source IP address is one of one or more IP addresses assigned to a network interface from which the frame is transmitted.

Next the processes performed by individual devices included in the distributed DB system are described with reference to the flowchart in .

Specifically the processes that are related to the ARP and that are common to the node and the client are described below with reference to . In the present embodiment since the ARP table is used as the dynamic association information in the processes in are related to the dynamic update of the dynamic association information . Then the processes performed by the client are described with reference to . Furthermore the processes performed by the node are described with reference to .

The process in is called i.e. invoked from some steps in which are referenced later. For example the process in is performed in the following cases 6 1 through 6 6 etc.

 6 1 A case where the communication processing unit receives an instruction from the read write processing unit to transmit a reply to a read request or a reply to a write request.

 6 2 A case where the communication processing unit receives an instruction from the acquisition control unit to transmit a copy request or a takeover request.

 6 3 A case where the communication processing unit receives an instruction from the supply control unit to transmit a reply to a copy request or a reply to a takeover request.

 6 4 A case where the communication processing unit receives an instruction from the monitoring request unit to transmit a monitoring request or to transmit an ACK to a keep alive message.

 6 5 A case where the communication processing unit receives an instruction from the monitoring unit to transmit a keep alive message for monitoring.

 6 6 A case where the communication processing unit receives an instruction from the DB request processing unit to transmit a DB access request specifically a read request or a write request .

When the communication processing unit or receives an instruction to transmit a certain message the communication processing unit or acquires a forwarding IP address from the specified destination IP address in step S. The examples of the message include for example a DB access reply a monitoring request a keep alive message a DB access request other control messages etc. as described above.

For example assume that the client in is attempting to transmit a message to the node N. In the example in the client and the node Nbelongs to the same broadcast domain . Therefore the communication processing unit of the client acquires as the forwarding IP address the destination IP address itself that is the IP address of the communication endpoint corresponding to the key region for which the node Nis currently responsible in step S.

The same holds true with the case in which the communication is performed between the nodes belonging to the same broadcast domain . That is the communication processing unit of the node acquires the destination IP address itself as the forwarding IP address in step S.

On the other hand when the application server in is as a client attempting to transmit a message to the node N the forwarding IP address is not the destination IP address itself because the application server and the node Nbelong to different broadcast domains.

In this case for example by using a subnet mask the communication processing unit of the application server recognizes that the destination IP address is not an IP address of a machine in the broadcast domain to which the application server belongs. Then the communication processing unit of the application server acquires as the forwarding IP address the IP address of the router which belongs to the same broadcast domain as the application server in step S.

The same holds true with the case in which communication is performed between the nodes belonging to the different broadcast domains and . For example when the node Nis attempting to transmit a certain message to the node N the communication processing unit of the node Nacquires the IP address of the router as the forwarding IP address in step S.

After acquiring the forwarding IP address as described above the communication processing unit or searches the ARP table or for an entry having the forwarding IP address in the next step S.

Then in step S the communication processing unit or judges whether or not an entry is found as a result of the search in step S. When an entry is found the communication processing unit or sets again the lifetime of the found entry to a predetermined value for example two minutes etc. then the process proceeds to step S. On the other hand if no entry is found the process proceeds to step S.

In step S the communication processing unit or assembles i.e. constructs a frame to transmit a message. Specifically the communication processing unit or assembles the frame based on the message specified for transmission the specified destination IP address the MAC address registered in the found entry etc. The particular destination IP address is set in the destination IP address field in the IP header and the MAC address registered in the found entry is set in the destination MAC address field in the MAC header.

Then the communication processing unit or transmits the frame through the network interface or . When the frame is transmitted the process in is normally terminated.

On the other hand in step S the communication processing unit or generates an ARP request in which the forwarding IP address is specified as the TPA target protocol address . Then the communication processing unit or broadcasts the generated ARP request through the network interface or .

In the next step S the communication processing unit or judges whether or not an ARP reply has been received through the network interface or within a predetermined time period hereafter referred to as TO arp . If no ARP reply is received within the predetermined time period TO arp the communication processing unit or returns an error code to the caller which has instructed the communication processing unit or to transmit the message thereby abnormally terminating the process in .

On the other hand if an ARP reply is received within the predetermined time period TO arp the communication processing unit or updates the ARP table or according to the received ARP reply in step S.

That is the communication processing unit or adds a new entry which associates the IP address 7 1 and the MAC address 7 2 with each other to the ARP table or .

Furthermore the communication processing unit or sets the lifetime of the newly added entry to a predetermined value for example two minutes etc. .

After the above mentioned update of the ARP table or the process returns to step S. As a result of the search in step S after step S an entry is found. Therefore a frame is then transmitted in step S. The update of the ARP table or in step S provides an example of a case where the dynamic association information in is updated.

Next with reference to the process performed by a device which receives an ARP request transmitted in step S in is described below. is a flowchart of the ARP reply. The process in is also common to the node and the client .

The process in is performed for each Ethernet port that is for each MAC address . For example when the network interface of the node includes two Ethernet ports the process in is performed independently for each of the two Ethernet ports. For convenience in the explanation in the Ethernet port to which the process in is targeted is referred to as a target Ethernet port .

When the ARP request is received the communication processing unit or updates the ARP table or as necessary in step S.

Specifically the communication processing unit or searches the ARP table or for an entry having the IP address that is specified as the SPA in the ARP request. If the entry is found the communication processing unit or updates the MAC address of the found entry to the MAC address that is specified as the SHA in the ARP request and sets again the lifetime of the found entry to a predetermined value for example two minutes etc. . Then the process proceeds to step S.

On the other hand if no entry is found the communication processing unit or judges whether or not the IP address specified as the TPA in the received ARP request is an IP address assigned to the target Ethernet port. The communication processing unit may make the judgment above by referring to the interface configuration file . Although omitted in the communication processing unit also includes an interface configuration file similar to the interface configuration file in . Therefore like the communication processing unit the communication processing unit is also able to make the above mentioned judgment.

If the IP address specified as the TPA is the IP address assigned to the target Ethernet port then the communication processing unit or adds a new entry to the ARP table or . The newly added entry is specifically an entry that associates the IP address specified as the SPA in the ARP request and the MAC address specified as the SHA in the ARP request with each other. Then the communication processing unit or sets the lifetime of the newly added entry to a predetermined value for example two minutes etc. . Then the process proceeds to step S.

On the other hand if the IP address specified as the TPA is different from the IP address assigned to the target Ethernet port the communication processing unit or does not add an entry in step S. In this case the process proceeds from step S to step S without updating the ARP table or .

The dynamic association information in may be updated by updating the ARP table or that is by updating an ARP entry or by adding an ARP entry in step S as described above.

In the next step S the communication processing unit or judges whether or not the IP address specified as the TPA in the received ARP request is the IP address assigned to the target Ethernet port. This judgment may be performed in the method described with reference to step S.

When the IP address specified as the TPA in the received ARP request is different from the IP address assigned to the target Ethernet port the process returns to step S.

On the other hand when the IP address specified as the TPA in the received ARP request is the IP address assigned to the target Ethernet port the communication processing unit or returns an ARP reply in step S. Specifically the communication processing unit or generates an ARP reply that includes as the SPA the IP address specified as the TPA in the received ARP request and that includes the MAC address of the target Ethernet port as the SHA. Then the communication processing unit or transmits the generated ARP reply through the network interface or .

Then after the transmission of the ARP reply the process returns to step S. The transmitted ARP reply is received as described above in step S in .

In step S the DB request processing unit identifies three communication endpoints using the key specified by the application and the correspondence table .

Specifically the DB request processing unit first judges to which key region the specified key belongs. For example it is assumed that each key region Kis defined by formula 3 . In addition let x be the specified key. In this case the DB request processing unit calculates the value of mod hash x M and identifies the key region to which the specified key belongs based on the calculation result. It is obvious that the DB request processing unit is still able to identify the key region to which the specified key belongs even when each key region Kis defined by any other formula.

In addition the correspondence table of the present embodiment associates three communication endpoints with each key region as specifically illustrated in the correspondence table in . Therefore the DB request processing unit searches the correspondence table for an entry corresponding to the identified key region and reads from the found entry three pieces of the communication endpoint information for respectively identifying the first through third communication endpoints.

Then in the next step S the DB request processing unit transmits the read request to the first communication endpoint which is identified in step S through the communication processing unit and the network interface . That is the DB request processing unit specifies the content of the read request and the communication endpoint information about the first communication endpoint and instructs the communication processing unit to transmit the read request. Then the communication processing unit assembles a frame according to the instruction in a way as illustrated in and transmits the frame.

After instructing the communication processing unit to transmit the read request the DB request processing unit waits for the reception of a reply from the first communication endpoint hereafter a reply to a read request is referred to as a read reply . As illustrated in step S if the DB request processing unit receives a read reply within a predetermined time period hereafter referred to as TO db the process proceeds to step S. On the other hand if the DB request processing unit fails to receive a read reply after the passage of the predetermined time period TO db the process proceeds to step S.

In step S the DB request processing unit returns the content of the received read reply to the application . Then the reading operation in normally terminates. The details of step S are described below.

If the entry corresponding to the key specified by the application exists in the KVS the received read reply includes the value associated with this key by this entry. Therefore the DB request processing unit returns this value to the application in step S.

On the other hand if the entry corresponding to the key specified by the application does not exist in the KVS the received read reply indicates that there is no value corresponding to the specified key. Therefore in step S the DB request processing unit notifies the application that no value has been detected.

On the other hand in step S the DB request processing unit transmits a read request to the second communication endpoint through the communication processing unit and the network interface . Since step S is the same as step S except the destination of the read request the detailed explanation is omitted here.

Then after instructing the communication processing unit to transmit the read request the DB request processing unit waits for the reception of a read reply from the second communication endpoint. As illustrated in step S if the DB request processing unit receives the read reply within the predetermined time period TO db the process proceeds to step S. On the other hand if the DB request processing unit fails to receive a read reply after the passage of the predetermined time period TO db the process proceeds to step S.

Then in step S the DB request processing unit returns the content of the received read reply to the application . Then the reading operation in normally terminates. Since step S is the same as step S the detailed explanation is omitted here.

On the other hand in step S the DB request processing unit transmits a read request to the third communication endpoint through the communication processing unit and the network interface . Since step S is also the same as step S except the destination of the read request the detailed explanation is omitted here.

After instructing the communication processing unit to transmit the read request the DB request processing unit waits for the reception of a read reply from the third communication endpoint. Then as illustrated in step S if the DB request processing unit receives a read reply within the predetermined time period TO db the process proceeds to step S. On the other hand if the DB request processing unit fails to receive a read reply after the passage of the predetermined time period TO db the process proceeds to step S.

In step S the DB request processing unit returns the content of the received read reply to the application . Then the reading operation in normally terminates. Since step S is the same as step S the detailed explanation is omitted here.

On the other hand in step S the DB request processing unit notifies the application of an error. Then the reading operation in abnormally terminates.

The description about above mainly relates to the DB request processing unit which operates in the application layer. Next supplementary explanation on the behaviors in the network layer and the link layer is given below using an example of transmitting a read request and receiving a read reply in steps S and S. The following supplementary explanation is also similarly applicable to steps S and S as well as applicable to steps S and S.

In some cases triggered by an instruction issued from the DB request processing unit to the communication processing unit in step S the communication processing unit may first perform the process for establishing a TCP connection. That is if a TCP connection has not yet been established between the first communication endpoint and the client the communication processing unit attempts to establish a TCP connection. Specifically the communication processing unit transmits a SYN synchronize segment waits for the reception of a SYN ACK segment and transmits an ACK segment after the reception of the SYN ACK segment. Thus the communication processing unit establishes a TCP connection between the first communication endpoint and the client .

Once the TCP connection has been established the communication processing unit transmits the read request which the DB request processing unit instructs the communication processing unit to transmit on the established TCP connection. In some cases an ARP request may be broadcast in the process in that is invoked in the context of transmitting the SYN segment. It is obvious that the process in may be invoked not only in the context of transmitting a SYN segment but also in the context of transmitting an ACK segment and in the context of transmitting a read request.

On the other hand if a TCP connection has already been established between the first communication endpoint and the client the communication processing unit simply transmits the read request which the DB request processing unit instructs the communication processing unit to transmit on the established TCP connection. The process in is of course invoked in the context of thus transmitting the read request.

The transmission of the read request is not always succeeds on the first try. This fact does not depend on whether the process for establishing a TCP connection is performed or not when the DB request processing unit issues an instruction in step S. For example there may be various cases as follows.

A read request transmitted on the first try may successfully reach a node responsible for the first communication endpoint. As a result the DB request processing unit may receive a read reply within the predetermined time period TO db.

Otherwise the first transmission of a read request may fail. However since the communication processing unit performs retransmission control according to the TCP the read request may successfully reach a node responsible for the first communication endpoint within a predetermined number of retries for example three retries . As a result the DB request processing unit may receive a read reply within the predetermined time period TO db.

Otherwise there may be a case where no ACK segment to a read request specifically a data segment of the read request is received by the client even if the retransmission of the read request is repeated up to the predetermined number of retries. The ACK segment to the read request may be a piggy back ACK segment that is the ACK flag in the TCP header in a read reply may be set to 1 .

There may be some reasons why the ACK segment to the read request is not received by the client after the retransmission of the read request is repeated up to the predetermined number of retries.

For example there may be a case where the client does not recognize the change of a node responsible for the first communication endpoint even after the change of the node actually occurs. In this case the MAC address of the network interface of the node that is no longer responsible for the first communication endpoint may be associated with the IP address of the first communication endpoint by the ARP table . That is a frame may be transmitted based on an obsolete ARP entry which does not reflect the current state.

As another example there may be a case where a failure incidentally occurs in the node that is responsible for the first communication endpoint and where the takeover of the first communication endpoint accompanying the occurrence of the failure has not yet been completed. Also in this case the MAC address of the network interface of the node which is currently faulty may be used in transmission of a frame.

As described above there may be a case where the ACK segment to the read request is not received by the client for any reason even if the retransmission of the read request is repeated up to the predetermined number of retries. The implementation of error handling for such a case may vary from embodiment to embodiment.

For example the communication processing unit may be implemented by a standard library of a TCP IP protocol stack as described above and may specifically include a TCP module an IP module an ARP module etc. If the ACK segment to the read request is not received by the client even if the retransmission of the read request is repeated up to the predetermined number of retries the TCP module in the transport layer may operate as follows.

That is the TCP module recognizes that the TCP connection has been disconnected due to the occurrence of abnormality and closes the TCP connection. In addition the TCP module may notify the ARP module of the abnormality directly or indirectly through the IP module. The notification of the abnormality includes the destination IP address used in the disconnected TCP connection.

Upon receipt of the notification of the abnormality the ARP module deletes from the ARP table a particular entry that corresponds to the notified destination IP address. On the other hand the TCP module attempts re establishment of the TCP connection.

For example assume that the re establishment of a connection is attempted relating to the transmission of a read request to the first communication endpoint in step S in . In this case the TCP module of the communication processing unit transmits a SYN segment waits for the reception of a SYN ACK segment and transmits an ACK segment after the reception of the SYN ACK segment.

When the process in is called in the context of transmitting the SYN segment no entry is found as a result of the search in step S in because the particular entry of the ARP table has already been forcibly deleted as described above. As a result an ARP request is broadcast in step S and a new entry is added to the ARP table in step S.

In some cases the problem is solved by forcibly clearing an ARP entry and creating another ARP entry as described above. Therefore the TCP module of the communication processing unit may transmit a read request again on the re established TCP connection.

For example in a case where the client has failed to recognize the change of the node responsible for the first communication endpoint according to the above mentioned process of re establishing the connection a new connection is established with a node physically different from the node with which the TCP connection has been established so far. Then the read request transmitted on the newly established connection successfully reaches the node currently in charge of the first communication endpoint and therefore the read reply is returned to the client .

For example the time long enough for the communication processing unit to perform the above mentioned retransmission control and re establishment of the connection may be determined in advance as the predetermined time period TO db which is referred to in step S. In this case the DB request processing unit which operates in the application layer simply judges in step S that the read reply is received within the predetermined time period TO db without recognizing the retransmission the deletion of the particular ARP entry or the creation of another ARP entry.

On the other hand depending on some embodiments the implementation may be adopted so that the DB request processing unit in the application layer is responsible for the deletion of an ARP entry and the creation of another ARP entry. That is the TCP module of the communication processing unit may be implemented so as to report the abnormality to the application layer instead of reporting the abnormality to the ARP module as described above. In other words the TCP module may notify the application layer that no ACK segment is received even after repeating the retransmission of the data segment for the predetermined number of times.

Then the DB request processing unit invokes a close instruction to a socket for the TCP connection about which the abnormality is reported. The close instruction may be for example a system call or an API application programming interface function.

In addition the DB request processing unit specifies the destination IP address which has been used in the TCP connection about which the abnormality is reported and instructs the ARP module to forcibly delete the entry from the ARP table . For example the DB request processing unit may call the arp command and may thereby instruct the ARP module to forcibly delete the entry.

The operation of the DB request processing unit after the instruction to forcibly delete the entry may be one of the following two operations.

The first example is an example in which the DB request processing unit performs retransmission control. That is if the DB request processing unit receives the above mentioned notification of the abnormality while waiting for the reception of a read reply in step S and accordingly instructs the ARP module to forcibly delete an entry the DB request processing unit may perform another process that is similar to the process in step S. Then the communication processing unit receives an instruction from the DB request processing unit to transmit a read request to the first communication endpoint and attempts the establishment of a TCP connection starting with the transmission of a new SYN segment.

Additionally in the context of transmitting the SYN segment the process in is called and an ARP request is broadcast. If the establishment of a TCP connection succeeds the communication processing unit transmits the data segment of the read request which the DB request processing unit instructs the communication processing unit to transmit on the established TCP connection.

In this case it is preferable that the time sufficiently long for the DB request processing unit to perform the above mentioned retransmission control is determined in advance as the predetermined time period TO db which is referred to in step S. Thus the DB request processing unit may be enabled to receive a read reply within the predetermined time period TO db from the first execution of step S.

Meanwhile the second example is an example in which the DB request processing unit does not perform the retransmission control. That is if the DB request processing unit receives the above mentioned notification of the abnormality while waiting for the reception of a read reply in step S and accordingly instructs the ARP module to forcibly delete an entry the DB request processing unit may perform the process in step S without waiting until the predetermined time period TO db passes.

In this case for example when another new DB access request in which a key belonging to the same key region as the key specified in the currently concerned DB access request is specified occurs in the application after the currently concerned DB access request an ARP request may be broadcast upon the new DB access request. Then as a result a new entry may be added to the ARP table in step S in .

Various implementation examples are described above in each of which the following processes 8 1 through 8 3 are performed when the TCP connection is abnormally disconnected due to a failure etc.

 8 2 After the forcible deletion of the entry a TCP connection is established again although there is a difference of whether the TCP connection is established again immediately after the forcible deletion or whether the TCP connection is established again when another new DB access request occurs .

 8 3 Before transmitting a SYN segment for re establishment of a TCP connection an ARP request is broadcast and a new entry about the same IP address as that in the forcibly deleted entry is added to the ARP table .

Therefore the dynamic update of the dynamic association information in is realized regardless of whether each of the forcible deletion of an entry of the ARP table the retransmission control and the re establishment of a TCP connection is controlled by the DB request processing unit or by the communication processing unit .

In step S the DB request processing unit identifies three communication endpoints using the key specified by the application and also using the correspondence table . Since step S is similar to step S in the detailed explanation is omitted here.

In the next step S the DB request processing unit transmits a write request to the first communication endpoint which is identified in step S through the communication processing unit and the network interface . That is the DB request processing unit specifies the content of the write request and the communication endpoint information of the first communication endpoint and instructs the communication processing unit to transmit the write request. Step S is similar to step S in except the content of the transmitted DB access request. Therefore the detailed explanation is omitted here.

In the next step S the DB request processing unit transmits a write request to the second communication endpoint which is identified in step S through the communication processing unit and the network interface . Step S is similar to step S except the destination of the write request. Therefore the detailed explanation is omitted here.

Furthermore in the next step S the DB request processing unit transmits a write request to the third communication endpoint which is identified in step S through the communication processing unit and the network interface . Step S is also similar to step S except the destination of the write request. Therefore the detailed explanation is omitted here.

After the transmission in steps S through S the DB request processing unit waits for the reception of replies from the three communication endpoints hereafter the reply to a write request is referred to as a write reply . As illustrated in step S if the DB request processing unit receives the write reply from every one of the three communication endpoints within the predetermined time period TO db the process proceeds to step S. On the other hand in a case where the number of communication endpoints from which a write reply is received is zero one or two even after the passage of the predetermined time period TO db the process proceeds to step S.

In step S the DB request processing unit notifies the application of the normal termination of the writing operation. Then the writing operation in normally terminates.

On the other hand in step S the DB request processing unit notifies the application of an error. Then the writing operation in abnormally terminates. Upon notification of the error the application may execute some kind of control for rollback in order to remove the inconsistency of data among the three nodes which are expected to hold the same copies and the application may also issue a specific DB access request for rollback to the DB request processing unit .

In each of the steps S through S as in step S in the process in is called. Furthermore situations and operations similar to those explained in the supplementary explanation about are also applicable to steps S through S in .

In some cases the process for establishment of a TCP connection is performed prior to the transmission of a data segment of a write request.

In addition depending on the implementation the retransmission control is performed by the communication processing unit during the predetermined time period TO db in which the DB request processing unit waits for the reception of a write reply. Then an entry in the ARP table is forcibly deleted in a case where no ACK segment to a write request is received by the client even when the retransmission of the write request is repeated up to the predetermined number of retries. As described above in the supplementary explanation relating to the forcible deletion of the entry may be performed under the control of the communication processing unit or may be performed under the control of the DB request processing unit .

Then an attempt to establish a TCP connection may be made again and a write request may be retransmitted on the newly established TCP connection. Then an ARP request is broadcast in the context of for example transmitting a SYN segment for re establishment of a TCP connection and a new entry is created on the ARP table as a result of the broadcasting.

The operation of the client is described above with reference to . Next the operation of the node is described below with reference to .

The node waits in step S until the node receives a DB access request to a communication endpoint on the local node that is a communication endpoint corresponding to a key region that the node itself is responsible for . When the DB access request to the communication endpoint on the local node is received the process proceeds to step S. The details of step S are specifically described as follows.

The communication endpoint corresponding to the key region that the node itself is responsible for is identified by a pair of an IP address and a port number wherein the IP address is associated with the MAC address of the network interface by the interface configuration file . Meanwhile a frame received by the network interface is sorted and forwarded by the communication processing unit depending on the destination IP address the destination port number and the subtype in the DB header.

For example as illustrated in assume that the node includes the three key region management units through . In this case the communication processing unit waits in step S until the communication processing unit receives a read request or a write request in which the communication endpoint information corresponding to one of the key region management units through is specified in the destination IP address and the destination port number.

When the communication processing unit receives the read request or the write request in which the communication endpoint information corresponding to one of the key region management units through is specified the communication processing unit outputs the received read request or write request. That is the read request or the write request is outputted to the read write processing unit in one of the key region management units through depending on the destination IP address.

Then in step S the read write processing unit judges whether the DB access request outputted from the communication processing unit is a read request or a write request. When the read request is outputted from the communication processing unit the process proceeds to step S. On the other hand if the write request is outputted from the communication processing unit the process proceeds to step S.

In step S the read write processing unit reads from the local store the value corresponding to the key specified in the read request.

For example assume that the key def is specified in the read request and that the key def belongs to the key region corresponding to the key region management unit in . In the example in the value corresponding to the key def is DEF . In this case in step S the read write processing unit in the key region management unit reads the value DEF from the local store .

Then in the next step S the read write processing unit returns the value read from the local store as a reply to the client . That is the read write processing unit generates a DB access reply in which the read value is included in the DB payload and returns the generated DB access reply to the client through the communication processing unit and the network interface . Then the process returns to step S.

In step S the read write processing unit rewrites the value that is stored on the local store in correspondence with the key specified in the write request into the value specified by the write request.

For example assume that the key def and the value XYZ are specified in the write request and that the key def belongs to the key region corresponding to the key region management unit in . In this case in step S the read write processing unit in the key region management unit overwrites the value DEF which is stored in the local store in association with the key def as illustrated in with the value XYZ .

Then in the next step S the read write processing unit notifies the client of the normal termination of the write request. That is the read write processing unit generates a DB access reply including the data indicating the normal termination of the write request in the DB payload or in the DB header and returns the generated DB access reply to the client . Afterwards the process returns to step S.

In the present embodiment as described above a TCP connection is established between the client and the node before the node receives the DB access request. Then the DB access request is received on the established TCP connection in step S and the transmission of the DB access reply in step S or S is performed also on the established TCP connection.

In addition the transmission of the DB access reply in step S or S is performed through the communication processing unit as described above. Therefore when the read write processing unit instructs the communication processing unit to transmit a DB access reply in step S or S the communication processing unit calls the process in .

In step S the node selects one of the communication endpoints from the correspondence table . Specifically the node selects one of the communication endpoints identified by an IP address not assigned to the network interface from the correspondence table . To be more preferable the node selects one of the communication endpoints from among the communication endpoints corresponding to other key regions than the key region s each corresponding to one of the IP address es that is are assigned to the network interface . The selection in step S may be random selection or may be selection based on the hash value of the information that is unique to the node . For example the information may be the host name or the FQDN fully qualified domain name of the node .

For example assume that the network interface is assigned three IP addresses that is 192.168.254.15 192.168.254.17 and 192.168.254.36 . In this case the node may select at random one communication endpoint from among the communication endpoints corresponding to other key regions than the key regions K K and K which respectively correspond to the three IP addresses above. In the following description for convenience of explanation the communication endpoint selected in step S is called a selected communication endpoint .

For example assume that the correspondence table is specifically the correspondence table in and that the node has selected in step S the communication endpoint identified by the communication endpoint information 192.168.254.36 7000 . According to the node currently assigned the IP address 192.168.254.36 is the node that is responsible for the key region K which is identified by the index 4 as the third communication endpoint .

In this case the node which performs the process in generates in step S a control message hereafter referred to as a takeover proposition for convenience of explanation in which 192.168.254.36 is specified as the destination IP address and 7000 is specified as the destination port number.

As the source IP address of the takeover proposition a fixed IP address which is described above relating to the requested node list in is used. For example assuming that the IP address 192.168.254.130 is fixedly assigned to the node which is performing the process in the source IP address of the takeover proposition is 192.168.254.130 .

Hereafter for convenience of explanation the node currently assigned the selected communication endpoint is referred to as a current responsible node . For example assuming that the selected communication endpoint is identified by the communication endpoint information 192.168.254.36 7000 as described above the current responsible node is a node that is responsible for the key region K which is identified by the index 4 as the third communication endpoint .

The takeover proposition generated in step S is a message designed to be used when the node identified by the source IP address proposes to the current responsible node taking over from the current responsible node the communication endpoint identified by the destination IP address and the destination port number. The node transmits the generated takeover proposition through the communication processing unit and the network interface in step S.

Then the node waits for the reception of a reply to the takeover proposition from the selected communication endpoint in step S. If the reply is received from the selected communication endpoint that is from the current responsible node within a predetermined time period hereafter referred to as TO prop the process proceeds to step S. On the other hand if the reply from the selected communication endpoint is not received within the predetermined time period TO prop the process proceeds to step S.

Then in step S the node judges whether the content of the reply indicates an ACK or a NACK negative acknowledgement . The ACK reply indicates that the current responsible node accepts the proposition that is the current responsible node desires the takeover . On the other hand the NACK reply indicates that the current responsible node does not accept the proposition that is the takeover is not necessary .

For example any node which has received the takeover proposition may return the ACK reply when the load of the node itself exceeds a predetermined criterion and may return the NACK reply when the load of the node itself is equal to or falls below the predetermined criterion. The load may be measured by any of the indices 9 1 through 9 3 above for example.

When the ACK reply is received the node generates a new key region management unit corresponding to the selected communication endpoint that is the communication endpoint to be taken over by the node from the current responsible node . Then the process proceeds to step S. In the description below for convenience of explanation it is assumed that the key region management unit is newly generated herein.

Then in step S the acquisition control unit in the key region management unit which is generated upon receipt of the ACK reply transmits a takeover request to the selected communication endpoint. The takeover request is specifically transmitted through the communication processing unit and the network interface . The destination IP address the destination port number and the source IP address of the takeover request are the same as those of the takeover proposition.

Then in step S the acquisition control unit waits for the reception of a takeover reply to the transmitted takeover request from the selected communication endpoint. If the takeover reply is not received from the selected communication endpoint that is from the current responsible node within a predetermined time period hereafter referred to as TO bulk then the process in abnormally terminates. On the other hand if the takeover reply is received from the selected communication endpoint within the predetermined time period TO bulk the process proceeds to step S.

For example when assuming that the selected communication endpoint is identified by the communication endpoint information 192.168.254.36 7000 as described above the takeover reply includes all entries whose keys belong to the key region K which is identified by the index 4 . Therefore when a large number of keys belong to the key region to be taken over it is desirable that the time period TO bulk is set to be long enough. For example when the current responsible node which has received the takeover proposition returns the ACK reply the current responsible node may specify the value of the time period TO bulk in the ACK reply depending on the number of keys belonging to the key region to be taken over.

The takeover reply is received by the network interface and then outputted through the communication processing unit to the acquisition control unit in the key region management unit that is the sender of the takeover request. In the takeover reply its source IP address is the IP address of the selected communication endpoint and its destination IP address is the source IP address of the takeover request that is the fixed IP address .

The acquisition control unit stores the received data that is all entries included in the takeover reply in the local store in step S. For example in the example above the acquisition control unit newly adds every entry whose key belongs to the key region K which is identified by the index 4 to the local store .

Then the acquisition control unit waits for the reception of an assignment instruction in step S. The assignment instruction is a control message for instructing the node which is performing the process in to assign the IP address of the selected communication endpoint to the network interface of the node .

 10 1 The selected communication endpoint is identified by the communication endpoint information 192.168.254.36 7000 .

 10 3 The IP address fixedly assigned to the node which is performing the process in is 192.168.254.130 .

In the case where the situations 10 1 through 10 3 hold true the assignment instruction is a control message for allowing the current responsible node to instruct the node which is performing the process in to assign the IP address 192.168.254.36 . In the assignment instruction its source IP address is the fixed IP address 192.168.254.133 and its destination IP address is the fixed IP address 192.168.254.130 .

If no assignment instruction is received within a predetermined time period hereafter referred to as TO assign the process in abnormally terminates. On the other hand if the assignment instruction is received within the predetermined time period TO assign the process proceeds to step S.

Then in step S the acquisition control unit instructs the association unit to assign the IP address of the selected communication endpoint to the network interface . Then the association unit performs the process for assigning the IP address of the selected communication endpoint to the network interface .

For example the association unit may directly rewrite the interface configuration file in the communication processing unit to associate the IP address of the selected communication endpoint with the network interface . Otherwise the association unit may invoke the function of the communication processing unit by issuing an appropriate command such as the ifconfig command so as to cause the communication processing unit to rewrite the interface configuration file .

For example in the case where the above situations 10 1 through 10 3 hold true the IP address 192.168.254.36 is anyway assigned to the network interface of the node which is performing the process in as a result of step S.

Then in step S the monitoring request unit selects one or more other nodes and registers them in the requested node list . Then the monitoring request unit requests each node registered in the requested node list to monitor the selected communication endpoint.

For example assume that the distributed DB system includes eight nodes and the eight IP addresses 192.168.254.128 through 192.168.254.135 are fixedly assigned to the eight nodes. In addition assume that as described above with respect to the situation 10 2 the IP address 192.168.254.130 is fixedly assigned to the node which is performing the process in . Further assume that the IP address 192.168.254.36 is assigned in step S as described above.

In this case the monitoring request unit recognizes in advance the eight fixed IP addresses by performing for example the process of reading a configuration file not illustrated in the attached drawings and also recognizes the fixed IP address of the node itself.

As another example for each individual IP address not assigned to the network interface of the node among the IP addresses appearing on the correspondence table the monitoring request unit may transmit an inquiry whose destination IP address is the individual IP address concerned. When each node which has received the inquiry returns a reply including the fixed IP address of the node itself the monitoring request unit is enabled to recognize a set of fixed IP addresses used for the nodes in the distributed DB system.

Anyway the monitoring request unit recognizes the eight fixed IP addresses in advance. Therefore in step S the monitoring request unit selects one or more arbitrary IP addresses from among the seven fixed IP addresses other than 192.168.254.130 and registers each selected IP address in the requested node list . For example the monitoring request unit may select 192.168.254.128 and 192.168.254.133 and may register them in the requested node list .

When the above two IP addresses are selected the monitoring request unit generates pieces of data for the following monitoring requests 11 1 and 11 2 and transmits the generated data of each monitoring request through the communication processing unit and the network interface .

 11 1 A monitoring request in which the source IP address is 192.168.254.130 the destination IP address is 192.168.254.128 and the pair of the IP address and the port number for indicating the communication endpoint as a monitoring target is 192.168.254.36 7000 .

 11 2 A monitoring request in which the source IP address is 192.168.254.130 the destination IP address is 192.168.254.133 and the pair of the IP address and the port number for indicating the communication endpoint as a monitoring target is 192.168.254.36 7000 .

It is obvious that the IP address such as 192.168.254.36 dynamically assigned depending on the key region may be used as the source IP address of the monitoring request in some embodiments. In addition the port number of the communication endpoint to be monitored may be specified as the source port number of the monitoring request. That is in the packet of the monitoring request the monitoring target may be specified by its source IP address and its source port number.

In another node which has received the monitoring request the communication processing unit outputs the monitoring request to the monitoring unit . Then the monitoring unit adds the communication endpoint information about the monitoring target specified in the monitoring request to the target node list .

When the transmission of the monitoring request to each of the one or more other nodes is completed in step S the node judges in the next step S whether or not a particular condition hereafter referred to as a termination condition for terminating the process in is satisfied.

The termination condition may be for example one of the following conditions 12 1 through 12 3 or may be another condition.

 12 1 The load of the node exceeds the criterion referenced by the node to judge whether or not the process in is to be started.

 12 2 The node has already performed the selection in step S for a predetermined number of times for example three times after the start of the process in .

If the termination condition is satisfied the node terminates the process in . On the other hand if the termination condition is not satisfied the process returns to step S.

In the present embodiment the takeover proposition the ACK reply or the NACK reply to the takeover proposition the takeover request and the takeover reply are transmitted and received on an established TCP connection. That is in some cases to transmit the takeover proposition in step S the node first performs a series of processes to establish the TCP connection that is the transmission of a SYN segment the reception of a SYN ACK segment and the transmission of an ACK segment .

Although omitted in a series of processes to close the TCP connection used in the transmission and reception of the takeover reply etc. is performed before the current responsible node transmits the assignment instruction. This is because the node assigned the IP address used in this TCP connection changes.

Specifically the current responsible node transmits a FIN ACK segment after the transmission of the takeover reply. Upon receipt of the FIN ACK segment the node which is performing the process in transmits an ACK segment to the FIN ACK segment. In addition since the TCP connection is bidirectional the node further transmits a FIN ACK segment. Upon receipt of the FIN ACK segment the current responsible node transmits an ACK segment to the FIN ACK segment. The TCP connection is thus closed by the processes above.

In the present embodiment the assignment instruction is also transmitted and received on a TCP connection. The IP addresses of the communication endpoints on both ends of the TCP connection used in the transmission and reception of the assignment instruction are the fixed IP addresses as exemplified in the situations 10 2 and 10 3 . That is the TCP connection used in the transmission and reception of the assignment instruction is different from the TCP connection used in the transmission and reception of the takeover reply etc.

Thus if there is no TCP connection between the communication endpoints identified by the fixed IP addresses the current responsible node transmits a SYN segment for establishing a TCP connection before transmitting the assignment instruction. Then the communication processing unit of the node which is performing the process in transmits a SYN ACK segment and the current responsible node further transmits an ACK segment. The assignment instruction is transmitted and received on the TCP connection newly established as described above or already and incidentally established for any other use .

Furthermore according to the present embodiment a monitoring request is also transmitted on an established TCP connection. That is in some cases the communication processing unit may first perform a series of processes to establish a TCP connection to transmit a monitoring request in step S.

The timeout process in each of steps S S and S may include the processes such as forcible deletion of an entry from the ARP table the retransmission control the re establishment of a TCP connection etc. like the process in step S in . As with the above explanation about the client specific implementation may vary from some viewpoints such as a viewpoint as to whether the retransmission control is performed by the monitoring unit in the application layer or by the communication processing unit in the transport layer.

Next described is the process performed by a node which has been requested to perform monitoring. is a flowchart of a process in which the node monitors another node and performs a takeover when the monitoring target becomes faulty.

For example assume that the node Nin performs the process in . Also assume that the node Nrequests the nodes Nand Nin step S to monitor a certain communication endpoint that the node Nhas dynamically assigned to the node Nin step S. In this case the nodes Nand Neach perform the process in . Then if a failure occurs in the node Nafterwards one of the nodes Nand Nwhichever recognizes according to the process in the failure in the node Nearlier than the other recognizes it turns into a node to which the communication endpoint to be monitored is newly assigned.

For each communication endpoint registered in the target node list to be more specific the target node list in for example in the monitoring unit the process in is separately performed and continues while the node is in operation. In the following description for convenience of explanation the communication endpoint as a target of the process in is referred to as a target communication endpoint .

In step S the monitoring unit transmits a keep alive message to a target communication endpoint. For example when the target communication endpoint is the communication endpoint that is first listed in the target node list in the monitoring unit generates a keep alive message in which 192.168.254.9 is specified as the destination IP address and 7000 is specified as the destination port number. The source IP address of the keep alive message is an IP address fixedly assigned to the node which is performing the process in . The monitoring unit transmits the generated keep alive message to the target communication endpoint through the communication processing unit and the network interface .

Then in step S the monitoring unit waits for the reception of a reply to the keep alive message from the target communication endpoint.

If the reply to the keep alive message is received from the target communication endpoint within a predetermined time period hereafter referred to as TO keepalive the monitoring unit judges that the node assigned the target communication endpoint is normal. Then the process proceeds to step S.

On the other hand if no reply to the keep alive message is received from the target communication endpoint within the predetermined time period TO keepalive the monitoring unit judges that there has occurred a failure in the node assigned the target communication endpoint. Then the process proceeds to step S for failover.

In step S the monitoring unit reads the content of the reply to the keep alive message. According to the present embodiment the reply to the keep alive message includes the information for example a flag etc. indicating whether monitoring is required or not. If the reply specifies that monitoring is not required the process proceeds to step S. On the other hand if the reply specifies that monitoring is required the process proceeds to step S.

The reason why the reply to the keep alive message includes the information indicating whether monitoring is required or not is described as follows.

In the present embodiment if the communication endpoint that has been assigned to a first node is taken over by a second node for any reason the second node selects one or more nodes arbitrarily regardless of which node s the first node has requested to monitor the first node. Then the second node requests each selected node to monitor the communication endpoint newly assigned to the second node. Then there is the possibility that the second node receives a keep alive message from a third node which has monitored the first node at the request from the first node.

The reason is that the destination of the keep alive message is determined by the IP address and the port number which logically identify the communication endpoint. That is there is the possibility that the second node receives the keep alive message from the third node when the ARP table is updated in the third node.

On the other hand unless the second node happens to select the third node and requests the third node to monitor the second node the third node for the second node is not the node which the second node has requested to monitor the second node. That is there is the possibility that the second node receives the keep alive message from the node not registered in the requested node list .

Thus according to the present embodiment the reply to the keep alive message includes the information indicating whether monitoring is required or not. As understood from the explanation below with reference to this information makes it feasible to maintain the consistency between the requested node list held by the node at the destination of the keep alive message and the node s each actually transmitting the keep alive message.

Back to the explanation of the branch in step S when the reply to the keep alive message specifies that monitoring is not required the monitoring unit excludes the target communication endpoint from its monitoring target s in step S. That is the monitoring unit deletes the communication endpoint information identifying the target communication endpoint from the target node list . Then the process in terminates. As a result the monitoring of the communication endpoint identified by the communication endpoint information deleted from the target node list is no longer performed.

On the other hand in step S the monitoring unit waits until a predetermined time period hereafter referred to as I keepalive has passed from the transmission in step S. The predetermined time period I keepalive is a time period determined as a transmission interval of the keep alive message. If the predetermined time period I keepalive has passed since the transmission in step S the process returns to step S. Therefore even if a failure occurs in the node at the target communication endpoint the failure is detectable within the maximum time period I keepalive TO keepalive from the occurrence of the failure.

The processes in steps S through S indicate the takeover process performed for failover when a failure at the communication endpoint that is the monitoring target is detected.

First in step S the monitoring unit newly generates one key region management unit. For example the key region management units through in may be realized by three different threads as described above and the monitoring unit may generate a new key region management unit by generating a new thread. The generated new key region management unit specifically corresponds to the target communication endpoint and therefore corresponds to the key region statically associated with the target communication endpoint. In the following description for convenience of explanation it is assumed that the key region management unit is generated in step S.

Furthermore in step S the acquisition control unit in the newly generated key region management unit searches the correspondence table for other communication endpoints each responsible for the key region corresponding to the target communication endpoint.

For example it is assumed that the correspondence table is specifically the same as the correspondence table in and that the target communication endpoint is identified by the communication endpoint information 192.168.254.9 7000 . In this case the target communication endpoint is the first communication endpoint for the key region Kidentified by the index 9.

Therefore the acquisition control unit in the newly generated key region management unit searches for the second communication endpoint and the third communication endpoint for the key region K. As a result the acquisition control unit acquires the communication endpoint information 192.168.254.25 7000 corresponding to the second communication endpoint and the communication endpoint information 192.168.254.41 7000 corresponding to the third communication endpoint .

In the next step S the acquisition control unit judges whether or not there remains a communication endpoint not selected as the target of the process in and after step S in the communication endpoints found in the search in step S. If there remains a communication endpoint not selected yet the process proceeds to step S.

On the other hand the case in which the process in step S is performed even after all communication endpoints found in step S have been selected is an abnormal case such as the case in which all three nodes responsible for the same key region are faulty. Therefore if there remains no unselected communication endpoint the process in abnormally terminates.

In step S the acquisition control unit selects one unselected communication endpoint in the communication endpoints found in step S. In the following description for convenience of explanation the communication endpoint selected in step S is referred to as a selected communication endpoint .

Then the acquisition control unit requests the selected communication endpoint for all data of the key region corresponding to the selected communication endpoint. The key region corresponding to the selected communication endpoint is the same as the key region corresponding to the target communication endpoint.

 13 1 As described above the pieces of the communication endpoint information 192.168.254.25 7000 and 192.168.254.41 7000 are acquired in step S.

 13 2 In step S the communication endpoint identified by the communication endpoint information 192.168.254.25 7000 is selected.

In the case where the situations 13 1 and 13 2 hold true the acquisition control unit in the newly generated key region management unit requests the selected communication endpoint for the data of all entries whose keys belong to the key region K. The request thus transmitted in step S is a copy request described above. The copy request is transmitted through the communication processing unit and the network interface at an instruction of the acquisition control unit .

In the copy request used in the above example where the situations 13 1 and 13 2 hold true the destination IP address is 192.168.254.25 and the destination port number is 7000 . The source IP address of the copy request is an IP address fixedly assigned to the node which is performing the process in as with the takeover request in step S in .

After the transmission of the copy request the acquisition control unit waits for the reception of a copy reply in step S.

If no normal copy reply is received from the selected communication endpoint within a predetermined time period which may be for example the same as the predetermined time period TO bulk referred to in step S in the process returns to step S. On the other hand if the reply to the copy request is received by the acquisition control unit within the predetermined time period TO bulk the process proceeds to step S.

Although the explanation is omitted above the acquisition control unit may transmit a control message to the selected communication endpoint in order to inquire about the predetermined time period TO bulk before transmitting the copy request in step S. The node at the selected communication endpoint may reply to the acquisition control unit with an appropriate time period depending on the number of entries whose keys belong to the key region corresponding to the selected communication endpoint. The acquisition control unit may set the predetermined time period TO bulk based on the reply to the control message and may then transmit the copy request in step S as described above.

For more details the copy reply is received by the network interface and outputted to the acquisition control unit in the key region management unit as the source of the copy request through the communication processing unit . In the copy reply its source IP address is the IP address of the selected communication endpoint and its destination IP address is the source IP address of the copy request that is the fixed IP address used in the copy request .

Then upon receipt of the copy reply the acquisition control unit stores the received data that is all entries included in the copy reply into the local store in step S.

For example the selected communication endpoint in the example of the above situation 13 2 is the second communication endpoint for the key region K. Therefore the copy reply includes every entry whose key belongs to the key region K. Accordingly the acquisition control unit newly adds every entry whose key belongs to the key region Kto the local store in step S.

In addition in the next step S the acquisition control unit instructs the association unit to assign the IP address of the target communication endpoint to the network interface . Then the association unit performs the process for assigning the IP address of the target communication endpoint to the network interface . For example in a case where the target communication endpoint is identified by the communication endpoint information 192.168.254.9 7000 the IP address 192.168.254.9 is associated with the network interface of the node itself.

As in step S in the association unit may directly rewrite the interface configuration file in the communication processing unit in step S. Otherwise the association unit may invoke the function of the communication processing unit by issuing a command so as to instruct the communication processing unit to rewrite the interface configuration file .

Then in the next step S the monitoring request unit included in the same key region management unit as the acquisition control unit which has transmitted the copy request selects one or more other nodes and registers them in the requested node list . Then the monitoring request unit requests each node registered in the requested node list to monitor the target communication endpoint.

Step S is the same as step S in except which communication endpoint is a target of the request for monitoring. Therefore the explanation of the details of step S is omitted.

In the next step S the acquisition control unit reports the completion of the failover to the monitoring unit . Then the monitoring unit excludes the target communication endpoint from the monitoring target s of the local node that is the monitoring target s of the node . That is the monitoring unit deletes the communication endpoint information that identifies the target communication endpoint from the target node list because the physical node corresponding to the target communication endpoint is currently the node itself and is no longer a remote node.

After the deletion in step S the process in also terminates. In some embodiments the monitoring unit may perform the process in step S concurrently with the acquisition control unit performing the processes in steps S through S. As another example the process in step S may be performed before the processes in steps S through S.

In the process illustrated in and described above the transmission of the keep alive message in step S the transmission of the copy request in step S and the transmission of the monitoring request in step S each include the process in . Accordingly depending on the state of the ARP table an ARP request may be broadcast and the ARP table may be updated in step S S or S.

In some cases the transmission in step S S or S may include the establishment of a TCP connection performed by the communication processing unit .

That is the keep alive message and the reply to the keep alive message are transmitted and received on a TCP connection established in advance according to the present embodiment. Similarly the copy request and the reply to the copy request are also transmitted and received on a TCP connection established in advance. The monitoring request is also transmitted and received on a TCP connection established in advance.

Therefore if the TCP connection corresponding to a message to be transmitted has not been established yet the communication processing unit performs the process for establishing the TCP connection in response to the instruction that is regarding the transmission of the message and that is issued in step S S or S. Specifically the communication processing unit establishes a TCP connection by transmitting a SYN segment receiving a SYN ACK segment and transmitting an ACK segment.

When the communication processing unit attempts to transmit the SYN segment the communication processing unit refers to the ARP table . As a result of such reference to the ARP table the broadcasting of an ARP request as described above may be performed prior to the actual transmission of the SYN segment. As another example depending on the timing when an ARP entry is deleted in the aging process an ARP request may be broadcast when the communication processing unit attempts to transmit a data segment on the established TCP connection.

In addition the timeout processes in steps S and S may each include the processes such as the forcible deletion of an entry from the ARP table the retransmission control the re establishment of the TCP connection etc. as with the process in step S of performed by the client . Thus as explained above relating to the client specific implementation may vary from some viewpoints such as a viewpoint as to whether the retransmission control is performed by the monitoring unit in the application layer or by the communication processing unit in the transport layer. Therefore the details of the timeout process are described later with reference to .

Next a process performed by the node that is monitored is described below with reference to the flowchart in . That is the node which has transmitted the monitoring request in step S in or step S in then performs the process in . To be more specific the monitoring request unit in each key region management unit of the node performs the process in .

In step S the monitoring request unit judges whether or not the number of entries in the requested node list is less than a predetermined number hereafter referred to as E req .

It is preferable that the predetermined number E req is two or more because there may be the case rarely but at a frequency which is not negligible in which both of the monitoring node and the monitored node happen to be faulty. In this state if the predetermined number E req is one the failure in the monitored node is not detectable.

However if the predetermined number E req is larger than one the probability of the situation that one monitored node and the predetermined number E req of monitoring nodes are all faulty is almost zero. Therefore the failure in the monitored node is surely detectable by at least one normal node among the predetermined number E req of monitoring nodes. Therefore it is preferable that the predetermined number E req is larger than one.

If the number of entries in the requested node list is the predetermined number E req or more the process proceeds to step S. On the other hand if the number of entries in the requested node list is less than the predetermined number E req the process proceeds to step S.

In step S the monitoring request unit judges whether or not there is a requested node which has not transmitted a keep alive message within a predetermined time period hereafter referred to as P keepalive in the past. In the explanation below each node identified by each element of the requested node list is referred to as a requested node .

The length of the predetermined time period P keepalive in step S is for example the sum of an appropriate margin and the transmission interval I keepalive of the keep alive message. For example the predetermined time period P keepalive may be approximately double the transmission interval I keepalive.

If there is no requested node which has not transmitted the keep alive message within the predetermined time period P keepalive the process proceeds to step S. That is if each requested node registered in the requested node list has transmitted the keep alive message at least once within the predetermined time period P keepalive this means that all requested nodes normally continue the monitoring. Therefore the process proceeds to step S.

On the other hand if there is a requested node which has not transmitted the keep alive message within the predetermined time period P keepalive the process proceeds to step S. For example if a certain requested node becomes faulty the transmission of the keep alive messages from the faulty requested node stops. Therefore the process may proceed from step S to step S for example when a failure occurs in any of the requested nodes.

In step S the monitoring request unit waits for the reception of the keep alive message from any node. When the monitoring request unit receives the keep alive message from any node through the network interface and the communication processing unit the process proceeds to step S.

As described above relating to step S in the source IP address of the keep alive message is a fixed IP address for administrative purposes. The destination IP address of the keep alive message is an IP address dynamically assigned depending on the correspondence between the key region and the node.

In step S the monitoring request unit judges whether or not the source node i.e. the sender node of the received keep alive message is found in the requested node list .

As described above with reference to each element of the requested node list is also a fixed IP address.

Therefore if the source IP address of the received keep alive message is included in the requested node list the monitoring request unit judges that the source node of the received keep alive message is found in the requested node list . Then the process proceeds to step S.

On the other hand if the source IP address of the received keep alive message is not included in the requested node list the monitoring request unit judges that the source node of the received keep alive message is not found in the requested node list . Then the process proceeds to step S.

In step S the monitoring request unit returns a normal reply indicating that the node more specifically the key region management unit including the monitoring request unit concerned is alive.

Specifically the monitoring request unit generates the reply whose details are listed in the following items 14 1 through 14 4 .

 14 1 The source IP address of the reply is an IP address corresponding to the key region management unit including the monitoring request unit concerned.

 14 3 The type or subtype in the DB header of the reply indicates being a reply to the keep alive message.

 14 4 The DB header or the DB payload of the reply includes the information indicating that the monitoring is still required afterwards.

Then the monitoring request unit transmits the generated reply to the source node i.e. the sender of the keep alive message through the communication processing unit and the network interface . After the transmission the process returns to step S. The reply transmitted in step S is received in step S by the requested node which performs the process in .

When the keep alive message from a node not registered in the requested node list is received the monitoring request unit returns in step S a reply specifying that monitoring is not required hereafter. The reply returned in step S is the same as the reply returned in step S in terms of 14 1 through 14 3 . The difference lies in that the reply returned in step S includes the information indicating that monitoring is not required instead of the information described in item 14 4 .

Also in step S the reply generated by the monitoring request unit is transmitted through the communication processing unit and the network interface . Then after the transmission the process returns to step S. The transmitted reply is received in step S by the requested node which performs the process in .

Meanwhile the process in step S is performed when there is a requested node which has not transmitted the keep alive message within the predetermined time period P keepalive. In step S the monitoring request unit deletes the IP address of each requested node which has not transmitted the keep alive message within the predetermined time period P keepalive from the requested node list . Then the process returns to step S.

When the number of entries in the requested node list is less than the predetermined number E req the monitoring request unit selects a new node s depending on the shortage in step S. For example when the predetermined number E req is three and the number of entries in the requested node list is one the monitoring request unit newly selects two 3 1 nodes.

As described above with reference to step S illustrated in the monitoring request unit recognizes in advance a set of fixed IP addresses used in the distributed DB system and also recognizes in advance the IP address fixedly assigned to the node itself. Therefore in step S the monitoring request unit is able to select one or more IP addresses each assigned to one or more other nodes than the local node from among the set of fixed IP addresses.

When the monitoring request unit selects a new node s depending on the shortage that is when the monitoring request unit selects the fixed IP address es of the new node s the monitoring request unit then in step S requests each selected node to monitor the node . To be more specific the monitoring request unit generates a monitoring request in which the communication endpoint corresponding to the key region management unit including the monitoring request unit itself is specified as a monitoring target. Then the monitoring request unit transmits the generated monitoring request through the communication processing unit and the network interface .

 15 2 The monitoring request unit that is performing the process in is the monitoring request unit in the key region management unit

 15 3 The key region management unit corresponds to the third communication endpoint for the key region K which is identified by the index 4 .

In the case where the assumptions 15 1 through 15 3 hold true the monitoring request unit of the key region management unit specifies the monitoring target i.e. the communication endpoint to be monitored using the communication endpoint information 192.168.254.36 7000 . As with step S in the fixed IP address may be used as the source IP address of the monitoring request transmitted in step S or the IP address of the communication endpoint to be monitored may be used as the source IP address of the monitoring request transmitted in step S.

In the next step S the monitoring request unit adds each node selected in step S to the requested node list . That is the monitoring request unit adds each fixed IP address selected in step S to the requested node list . Then the process returns to step S.

In the present embodiment the keep alive message and the reply to the keep alive message are transmitted on an established TCP connection. That is in each of steps S and S the reply is transmitted on the TCP connection that has been established and used in transmitting the keep alive message received in step S.

According to the present embodiment a monitoring request is also transmitted on an established TCP connection. Therefore in step S the communication processing unit may first perform the process for establishing a TCP connection in some cases when receiving from the monitoring request unit which has generated a monitoring request an instruction to transmit the monitoring request. That is to transmit the monitoring request in step S a series of processes may be performed starting with the transmission of a SYN segment.

When the IP address of the communication endpoint to be monitored is used as the source IP address of the monitoring request all of the monitoring request the keep alive messages in response to the monitoring request and the replies to the keep alive messages may be transmitted and received on the same TCP connection.

In addition each of steps S S and S includes calling the process in . Therefore depending on the state of the ARP table the transmission in step S S or S may be accompanied by broadcasting of an ARP request and update of the ARP table .

Next with reference to the sequence diagrams in some examples of the operation sequences of the distributed DB system in are described below. As understood from the examples in the entire distributed DB system works well when the nodes Nthrough Nin each operate according to the flowcharts in .

 16 3 The correspondence table of the node and the correspondence table of the client are the same as the correspondence table in .

First the application of the client specifies the key abc and instructs the DB request processing unit to perform the reading operation. Then the DB request processing unit starts the process in .

For convenience of explanation in the following description assume that the key region to which the key abc belongs is the key region K which is identified by the index 1 . Thus according to the first communication endpoint specified in step S in is specifically the communication endpoint identified by the communication endpoint information 192.168.254.1 7000 .

The DB request processing unit instructs the communication processing unit to transmit a read request to the above mentioned first communication endpoint in step S in . Then the communication processing unit confirms whether or not there is a TCP connection between the client and the communication endpoint specified from the DB request processing unit . However in the example in there is no TCP connection existing.

Then the communication processing unit tries to establish a TCP connection between the communication endpoint identified by the communication endpoint information 192.168.254.1 7000 and the client . Specifically the communication processing unit tries to transmit a SYN segment. Then the process in is called to transmit the SYN segment.

The example in is an example of the case in which no entry is found in the search in step S in . Therefore in step S in specifically as indicated in step S in an ARP request in which the IP address 192.168.254.1 is specified as the TPA target protocol address is broadcast from the client .

The ARP request is received by each device in the broadcast domain in . Then each device which has received the ARP request operates according to .

Assume that when the ARP request is broadcast the IP address 192.168.254.1 is assigned to the network interface of the node N. In this case as indicated by step S in the node Nreturns an ARP reply to the client in step S in .

In the ARP reply the MAC address of the network interface of the node Nis specified as the SHA sender hardware address . In the following description for convenience of explanation it is assumed that the MAC address of the network interface of the node Nis 00 23 26 6A C2 4C as exemplified in .

In addition the client receives the ARP reply . The reception of the ARP reply corresponds to step S in . Therefore as illustrated in step S in the ARP table is updated in the client which has received the ARP reply .

Specifically as indicated by step S in a new ARP entry is added to the ARP table of the client . The ARP entry associates the IP address 192.168.254.1 and the MAC address 00 23 26 6A C2 4C with each other.

When the ARP entry is thus added in step S in corresponding to step S in the client searches the ARP table in step S in again. As a result in step S the newly added ARP entry is found.

Therefore in step S in the communication processing unit of the client generates a SYN segment having the destination IP address 192.168.254.1 and the destination port number 7000 . Then the communication processing unit transmits the generated SYN segment through the network interface .

The destination MAC address of this SYN segment is 00 23 26 6A C2 4C . Therefore the SYN segment is received by the network interface of the node N and outputted to the communication processing unit of the node N.

As a result the communication processing unit of the node Ngenerates a SYN ACK segment and transmits the SYN ACK segment to the client through the network interface . Then the SYN ACK segment is received by the network interface of the client and outputted to the communication processing unit .

As a result the communication processing unit of the client generates an ACK segment and transmits the ACK segment to the node Nthrough the network interface . Then the ACK segment is received by the network interface of the node N and outputted to the communication processing unit .

The establishment of the TCP connection according to the above mentioned three way handshake is indicated by the bidirectional arrow of step S in . Meanwhile as described above the establishment of the TCP connection is performed in order to transmit the read request in step S in .

Therefore when the TCP connection is established in step S the DB request processing unit of the client transmits a read request on the TCP connection as indicated by the next step S. The read request has the format of the frame in but only some fields are extracted and illustrated in .

The destination MAC address of the read request is a MAC address determined by the ARP reply that is the MAC address of the network interface of the node N and is specifically 00 23 26 6A C2 4C . The destination IP address and the destination port number of the read request are the IP address and the port number for identifying the first communication endpoint which is identified in step S in by the client and are specifically 192.168.254.1 and 7000 .

The subtype specified in the DB header of the read request has the value indicating a read request . In the DB payload of the read request the key specified by the application that is the key abc is specified.

Then the read request is received by the node N. When the read request is received the node Nis responsible for i.e. is in charge of the communication endpoint identified by the communication endpoint information 192.168.254.1 7000 . That is all entries of the key region Kcorresponding to the communication endpoint information 192.168.254.1 7000 are stored in the local store of the node N and a key region management unit corresponding to the key region Kexists in the node N.

Therefore the node N which has received the read request performs the process in . Then in step S in the read write processing unit reads from the local store the value ABC corresponding to the key abc specified in the read request .

In step S in corresponding to step S in a read reply including the value ABC is transmitted to the client from the node N. It is obvious that the read reply is also transmitted on the TCP connection established in step S.

In the example of it is assumed that the time period from when the DB request processing unit instructs the communication processing unit to transmit the read request in step S in to when the DB request processing unit receives the read reply in step S is shorter than or equal to the predetermined time period TO db in step S in . Therefore the process in proceeds from step S to step S. As a result the DB request processing unit of the client returns the value ABC which is acquired from the read reply to the application in step S.

Next with reference to an example case regarding a failure in anode and a takeover is described below. The operation sequence of is based on the following assumptions 17 1 through 17 7 .

 17 2 As a result of the execution of the process in the node Nnewly takes charge of the key region K which is identified by the index 3 as the first communication endpoint at a certain time point hereafter referred to as time point T . That is at the time point T the network interface of the node Nis assigned the IP address 192.168.254.3 .

 17 3 When the node Ntakes charge of the key region Kas the first communication endpoint the node Nrequests at least the node Nto monitor the communication endpoint identified by the communication endpoint information 192.168.254.3 7000 .

 17 4 The time point Tmay be the time before step S in the time after step S or any time between step S and step S. The time point Tprecedes the starting time point of the operation sequence in .

 17 5 After the time point T an ARP entry in is registered in the ARP table of the node Nfor any reason. The ARP entry associates the IP address 192.168.254.3 and the MAC address 00 23 26 02 C6 D7 with each other.

 17 6 At the starting time point of the operation sequence in the ARP entry is not deleted namely the ARP entry still remains on the ARP table of the node N.

 17 7 Also at the starting time point of the operation sequence in the node Nis still in charge of the key region Kas the first communication endpoint .

With the assumptions 17 1 through 17 7 assume that a failure occurs in the node N i.e. the node Nbecomes faulty at a certain time point as indicated by step S.

Meanwhile according to the assumption 17 3 the monitoring unit of the node Nperforms the process in . That is the monitoring unit of the node Nmonitors the communication endpoint identified by the communication endpoint information 192.168.254.3 7000 . Then in step S in the monitoring unit of the node Nperforms the process in step S in . Thus a keep alive message whose destination IP address is 192.168.254.3 and whose destination port number is 7000 is transmitted from the node Nin step S.

Described below are the details of the operation in step S. The monitoring unit of the node Ninstructs the communication processing unit to transmit the keep alive message in step S in . Then the communication processing unit judges whether or not a TCP connection is established between the communication endpoint identified by the communication endpoint information 192.168.254.3 7000 and the communication endpoint identified by the fixed IP address of the node Nand a predetermined port number.

For simple explanation assume that the TCP connection has already been established. In this case the communication processing unit tries to transmit the keep alive message on the established TCP connection. That is the communication processing unit starts the process in to transmit the keep alive message .

Then in the search in step S of the ARP entry in is found. As a result in step S in the keep alive message in is transmitted.

If the node Nat the destination of the keep alive message normally operates the node Nperforms the process in and is to transmit a reply to the keep alive message in step in . However the node Nhas already become faulty in step S as described above. Therefore no reply to the keep alive message is transmitted from the node N.

Meanwhile the monitoring unit of the node Nwaits for the reception of the reply to the keep alive message as indicated in step S in . The example in is one of the specific examples of the timeout process in step S.

In the example in the communication processing unit is implemented by for example the standard library of the TCP IP protocol stack and specifically includes a TCP module an IP module an ARP module etc. When instructed to transmit a data segment by the monitoring unit or any one of other modules for example the acquisition control unit etc. the TCP module of the communication processing unit transmits the data segment. Afterwards the TCP module of the communication processing unit waits for the reception of an ACK segment to the transmitted data segment.

If no ACK segment is received within a predetermined time period the TCP module of the communication processing unit tries to retransmit the data segment. Specifically the predetermined time period in this example may be shorter than any one of the time period TO prop in the time period TO bulk in the time period TO assign in and the time period TO keepalive in . The ACK segment may be the piggyback ACK segment obviously.

The TCP module of the communication processing unit may try to retransmit the data segment as described above up to the predetermined number of retries for example three times . The monitoring unit or any other module in the application layer does not have to be involved in the retransmission control performed in the transport layer as described above by the TCP module of the communication processing unit . Due to space limitations the retransmission performed by the TCP module is omitted in .

If no ACK segment is received even after the TCP module of the communication processing unit performs the retransmission for the above mentioned predetermined number of retries the TCP module of the communication processing unit may operate as follows and the operation described below is exemplified in .

That is the TCP module recognizes that the TCP connection has been disconnected and closes the TCP connection. In addition the TCP module notifies the ARP module of the abnormality indirectly through the IP module or directly. The notification of the abnormality includes the destination IP address used in the disconnected TCP connection that is 192.168.254.3 in the example in .

Upon receipt of the notification of the abnormality the ARP module forcibly deletes the entry corresponding to the notified destination IP address that is the ARP entry in the example in from the ARP table . On the other hand the TCP module tries to re establish the TCP connection.

In the example in the TCP module of the communication processing unit of the node Ntries to re establish the TCP connection between the communication endpoints listed in the following items 18 1 and 18 2 .

 18 1 The communication endpoint used by the monitoring unit of the node Nin performing the monitoring that is the communication endpoint identified by the fixed IP address of the node Nand the predetermined port number .

 18 2 The communication endpoint identified by the communication endpoint information 192.168.254.3 7000 .

Specifically the TCP module first tries to transmit a SYN segment. The destination IP address of the SYN segment is 192.168.254.3 as described in item 18 2 . In addition as described above the ARP entry has already been forcibly deleted upon receipt of the notification of the abnormality.

Therefore when the process in is called to transmit the SYN segment no entry is found as a result of the search in step S. Therefore an ARP request is broadcast in step S.

This broadcasting in step S is indicated as step S in . That is the IP address 192.168.254.3 is specified as the TPA in an ARP request that is broadcast in step S.

For example when the failure in step S is only a temporary state such as a state in which communication is temporarily disabled due to replacement of the network interface the IP address may be resolved by broadcasting the ARP request . This is because there may be a case in which the replacement of the network interface of the node Nis completed before step S.

However in the example in it is assumed that the node Nhas really become faulty in step S. It is also assumed that the node Nis unrecoverable or the recovery is not completed before step S. The type of failure may be for example an abnormality in hardware e.g. in a CPU or may be a defect in software e.g. in an OS or in an application . In any case in the example in the faulty node Nis unable to return an ARP reply to the ARP request .

Therefore the ARP module of the communication processing unit of the node Nis unable to receive the ARP reply within the predetermined time period TO arp in step S in . As a result the process in abnormally terminates. That is the communication processing unit fails to transmit the SYN segment and thus fails to re establish the TCP connection.

Accordingly the communication processing unit reports the abnormal termination to the monitoring unit which has issued an instruction to transmit the keep alive message in step S in . The predetermined time period TO keepalive in step S in is set to an appropriate value in advance depending on one or more parameters such as the retransmission interval and the number of retries used in the TCP module of the communication processing unit .

That is it is assumed that the predetermined time period TO keepalive is preset to be equal to or longer than the time taken from the time point 19 1 to the time point 19 2 .

 19 1 The time point at which the monitoring unit instructs the communication processing unit to transmit the keep alive message in step S in .

 19 2 The time point at which the communication processing unit reports the abnormal termination to the monitoring unit in the series of processes described above.

Even if the predetermined time period TO keepalive has not passed from the time point 19 1 the process in FIG. proceeds from step S to step S when the monitoring unit receives the report of the abnormal termination from the communication processing unit . This is because it is expected that when the abnormal termination is reported from the communication processing unit the monitoring unit is unable to receive a reply to the keep alive message even if the monitoring unit waits until the predetermined time period TO keepalive has passed.

Then the acquisition control unit of the node Nsearches the correspondence table for the other two communication endpoints that correspond to the key region K which corresponds to the communication endpoint identified by the communication endpoint information 192.168.254.3 7000 in step S in . According to the assumption 16 3 the correspondence table is the same as the correspondence table in . Therefore as a result of the search the communication endpoints identified by pieces of the communication endpoint information 192.168.254.19 7000 and 192.168.254.35 7000 are found.

 20 1 In the node N the key region management unit corresponding to the key region Kis the key region management unit in . The acquisition control unit of the key region management unit of the node Nselects the communication endpoint identified by the communication endpoint information 192.168.254.19 7000 in step S in .

 20 2 When the selection described in item 20 1 is performed the IP address 192.168.254.19 is assigned to the network interface of the node N.

 20 3 When the selection described in item 20 1 is performed there is no TCP connection between the selected communication endpoint and the communication endpoint 18 1 used for the monitoring performed by the monitoring unit of the node N.

 20 4 When the selection described in item 20 1 is performed there is no entry about the IP address 192.168.254.19 in the ARP table of the node N.

According to the assumptions described in items 20 1 through 20 4 above the acquisition control unit of the key region management unit of the node Nrequests the communication endpoint selected as described in item 20 1 for all data of the key region Kin step S in . That is in step S the acquisition control unit generates a copy request and instructs the communication processing unit to transmit the generated copy request.

Then the communication processing unit tries to transmit a data segment of the copy request. However according to the assumption in item 20 3 there is no TCP connection. Thus the communication processing unit first attempts to transmit a SYN segment to establish a TCP connection.

Then the communication processing unit starts the process in to transmit the SYN segment. According to the assumption in item 20 4 no entry is found in step S in . Therefore an ARP request is broadcast in step S.

Each device belonging to the broadcast domain in operates according to the flowchart in upon receipt of the ARP request . Therefore according to the assumption in item 20 2 an ARP reply is returned in step S in from the node N.

The time period from step S to step S is equal to or shorter than the predetermined time period TO arp in . Therefore the communication processing unit of the node N which has received the ARP reply updates the ARP table in step S in . That is the communication processing unit of the node Nadds an ARP entry to the ARP table as indicated by step S in . The ARP entry associates the IP address 192.168.254.19 and the MAC address 00 23 26 17 F3 B9 with each other.

Then the communication processing unit of the node Nsearches again the ARP table in step S in . As a result the ARP entry is found this time and accordingly the SYN segment is transmitted in step S.

For simple explanation assume that the node Nnormally operates. Under this assumption the communication processing unit of the node N which has received the SYN segment transmits a SYN ACK segment. As a result the communication processing unit of the node Nreceives the SYN ACK segment and transmits an ACK segment. Then the communication processing unit of the node Nreceives the ACK segment.

According to the above mentioned three way handshake a TCP connection is established between the selected communication endpoint identified by the communication endpoint information 192.168.254.19 7000 and the above mentioned communication endpoint 18 1 on the node N. In the above mentioned three way handshake is indicated as step S.

Afterwards the communication processing unit of the node Ntransmits the data segment of the copy request which the acquisition control unit has instructed the communication processing unit to transmit in step S in on the established TCP connection. This transmission of the copy request corresponds to step S in and is indicated as step S in .

That is as illustrated in the index 3 is specified in a copy request that is transmitted in step S. The index 3 identifies the key region K data of which is requested by the node N. In the copy request the destination IP address itself may be used instead of the index as the information for identification of the key region Kbecause the destination IP address 192.168.254.19 is statically associated with the key region K.

The acquisition control unit of the key region management unit which corresponds to the key region K namely which corresponds to the communication endpoint information 192.168.254.19 7000 in the node Nwaits for the reception of a reply to the copy request . In the example in as indicated by step S a copy reply to the copy request is transmitted. To be more specific the acquisition control unit of the key region management unit of the node Nreceives the copy reply within the predetermined time period TO bulk from the transmission instruction in step S in . The copy reply includes the data of all entries whose keys belong to the key region K which is specified in the copy request .

After the reception of the copy reply the acquisition control unit of the key region management unit of the node Nstores the data of the copy reply in the local store in step S in .

Then in the next step S the acquisition control unit of the key region management unit of the node Ninstructs the association unit to assign the IP address of the target communication endpoint to the network interface of the node N. As a result the IP address 192.168.254.3 that has been assigned up to now to the node N whose failure has been detected by the monitoring unit of the node N is newly assigned to the network interface of the node N. This assignment in step S is indicated as step S in .

In step S in the monitoring request unit of the key region management unit of the node Nrequests one or more other nodes to monitor the target communication endpoint identified by the communication endpoint information 192.168.254.3 7000 . Then in step S the monitoring unit of the node Nexcludes the target communication endpoint from the target node list .

Therefore even when the node N which has been in charge of i.e. responsible for the key region Kas the first communication endpoint becomes faulty as in step S in the node Ntakes over the function of the node Nabout the key region K. That is the node Nnewly takes charge of the key region Kas the first communication endpoint . Accordingly the failover function is realized within the entire distributed DB system.

In addition the faulty node Nmay also have been responsible for one or more other key regions than the key region K. For example when the failure occurs in step S the node Nmay be responsible for the key region Kas the first communication endpoint and may be also responsible for the key region Kas the second communication endpoint .

In this case the function of the node Nabout the key region Kis taken over by another node that monitors the second communication endpoint of the key region K i.e. taken over by a node that monitors the communication endpoint identified by the communication endpoint information 192.168.254.31 7000 . Therefore even if anode responsible for a plurality of key regions becomes faulty the failover is successfully performed on each key region.

Next the DB access performed after the takeover in is described below with reference to . Since adopt different suppositions their operation sequences are also different. However in any case when the client transmits a DB access request in which a key belonging to the key region Kis specified the client is able to receive a DB access reply from the node N which has taken over the key region K.

 21 1 Before the node Nbecomes faulty in step S in the client transmits a DB access request in which a key belonging to the key region Kis specified to the node N and then the client receives a DB access reply from the node N. In addition the transmission and the reception of this DB access request and this DB access reply are performed on an established TCP connection.

 21 2 The TCP connection described in item 21 1 has not yet been disconnected i.e. has not yet been shut down in a normal procedure at the starting point of the operation sequence in . The normal procedure herein means the procedure in which a FIN ACK segment and an ACK segment are transmitted and received for each of two pipes in opposite directions.

 21 3 Before the communication described in item 21 1 an ARP entry in is created on the ARP table of the client . Note that the ARP entry is the same as the ARP entry which is held by the node Nin before the node Nbecomes faulty.

 21 4 At the starting point of the operation sequence of the ARP entry has not yet been deleted namely still remains on the ARP table of the client .

Under the assumptions described in items 21 1 through 21 5 in step S the client transmits a DB access request such as a read request or a certain administrative message on the existing TCP connection described in item 21 2 .

Assume that the key specified in the read request is def . In this case according to the assumption in item 21 5 the first communication endpoint detected by the DB request processing unit of the client in step S in is identified by the communication endpoint information 192.168.254.3 7000 according to the correspondence table in . Therefore in the read request the destination IP address is 192.168.254.3 and the destination port number is 7000 .

In addition although the content of the administrative message is arbitrary the destination IP address of the administrative message is also 192.168.254.3 . According to the assumption in item 21 2 at the starting point of the process in the communication processing unit of the client does not recognize that the TCP connection described in item 21 1 has been disconnected. Therefore the communication processing unit tries to transmit the data segment of the read request or that of the administrative message on the TCP connection described in item 21 1 without performing the process of transmitting a SYN segment again. As a result the process in is called.

Then when the communication processing unit of the client searches the ARP table in step S in the ARP entry is found because of the assumption in item 21 4 . As a result the MAC address 00 23 26 02 C6 D7 is specified as the destination MAC address in the read request or the administrative message .

Thus the frame of the read request or that of the administrative message is transmitted from the communication processing unit of the client in step S in corresponding to step S in . However the node Nis faulty at the time point in step S. Therefore no reply to the read request or to the administrative message is returned.

Even when someone e.g. an administrator restores the node Nfrom the failure and the node Nthus restored to its normal state receives the read request or the administrative message no reply is returned for the following reason.

The communication processing unit of the restored node Nmay receive the frame in which the MAC address of the network interface of the node Nis specified as the destination MAC address. However as indicated in step S in the IP address 192.168.254.3 has already been assigned to the network interface of the node N. In addition no dynamic IP address appearing on the correspondence table in is assigned to the node Nwhen the node Nis just restored. Only after the node Nperforms the process in a dynamic IP address is assigned to the node N.

Therefore the read request or the administrative message is discarded by the communication processing unit of the node Neven if it is received by the network interface of the restored node N. This is because the destination IP address of the read request or the administrative message is not assigned to the network interface of the node N.

Therefore regardless of whether the node Nstill remains faulty or whether the node Nhas already been restored the client is unable to receive the reply to the read request or to the administrative message .

As described above with reference to the TCP module of the communication processing unit of the client may transmit again the data segment if no ACK segment is received after the passage of a predetermined time period note that the arrow indicating the retransmission is omitted in . However in the example in since the destination MAC address specified in the frame and the destination IP address specified in the frame correspond to the different network interfaces the problem is not solved by the retransmission in the transport layer.

As a result no ACK segment is received even if the TCP module of the communication processing unit of the client repeats the retransmission for a predetermined number of times for example three times . Therefore the TCP module recognizes that the TCP connection which has previously existed as described in item 21 2 has been disconnected. Then the TCP module performs an appropriate process for shutting down the connection for example freeing an area on the RAM used for the TCP connection etc. .

Furthermore the TCP module notifies the ARP module of an abnormality directly or indirectly through the IP module. Upon receipt of the notification of the abnormality the ARP module forcibly deletes the ARP entry from the ARP table as indicated by step S in .

Meanwhile the TCP module attempts a re establishment of the TCP connection. That is the TCP module first tries to transmit a SYN segment for the re establishment of the TCP connection. The destination IP address of the SYN segment is 192.168.254.3 as with the read request and the administrative message .

Therefore the process in is started to transmit the SYN segment. Then as a result of the deletion in step S in no entry is found in the search in step S of . Therefore an ARP request is broadcast in step S in . The thus performed step S is indicated as step S in . That is the IP address 192.168.254.3 is specified as the TPA in an ARP request that is transmitted in step S.

When each device in the broadcast domain in receives the ARP request each device operates according to . As a result as indicated in step S in an ARP reply is transmitted from the node Nbecause the IP address 192.168.254.3 is currently assigned to the network interface of the node Nas a result of step S in .

The MAC address 00 23 26 9B 35 EF of the network interface of the node Nis specified as the SHA in the ARP reply . In addition the ARP reply is received by the client .

The reception of the ARP reply corresponds to step S in . Therefore as indicated by step S in the ARP table is updated in the client which has received the ARP reply .

Specifically as in step S in a new ARP entry is added to the ARP table of the client . The ARP entry associates the IP address 192.168.254.3 and the MAC address 00 23 26 9B 35 EF with each other.

When the ARP entry is thus added in step S in corresponding to step S in the client searches again the ARP table in step S in . As a result the newly added ARP entry is found.

Therefore in step S in the communication processing unit of the client generates a SYN segment whose destination IP address is 192.168.254.3 and whose destination port number is 7000 . Then the communication processing unit transmits the generated SYN segment through the network interface .

The destination MAC address of the SYN segment is 00 23 26 9B 35 EF . Therefore the SYN segment is received by the node N. Next the node Ntransmits a SYN ACK segment. Then the client receives the SYN ACK segment and transmits an ACK segment.

As described above a TCP connection is established by the three way handshake between the communication endpoint on the node Nidentified by the communication endpoint information 192.168.254.3 7000 and the communication endpoint on the client . This three way handshake is indicated by the bidirectional arrow of step S in .

Then on the TCP connection established in step S a read request or an administrative message is retransmitted. Due to space limitations in illustrates only the retransmission performed in the case where the data segment transmitted in step S is the read request .

Specifically the communication processing unit of the client starts the process in in order to transmit a data segment of the read request which has been specified by the DB request processing unit and has triggered the transmission in step S. Then as a result of the search in step S in the added ARP entry is found.

Therefore a frame of a read request is transmitted in step S. The thus performed step S is indicated as step S in .

The frame of the read request is different from the frame of the read request in its destination MAC address. That is the destination MAC address of the read request is 00 23 26 9B 35 EF . However the destination IP address the destination port number the subtype the key etc. are the same between the read requests and .

Next the read request is received by the node N. Then the node Noperates according to . As a result in step S in corresponding to step S in a read reply including the value DEF corresponding to the specified key def is transmitted from the node Nto the client .

The read reply is received by the network interface of the client and outputted to the DB request processing unit . In addition the predetermined time period TO db in is determined in advance so that the predetermined time period TO db in may be equal to or longer than the time taken from the following time point 22 1 to the following time point 22 2 .

 22 1 The time point when the DB request processing unit instructs the communication processing unit to transmit the read request .

 22 2 The time point when the DB request processing unit receives the read reply through the communication processing unit .

That is the time taken from the time point 22 1 to the time point 22 2 when the process as illustrated in is performed is estimated in advance based on the following constants 23 1 23 2 etc. The predetermined time period TO db is appropriately determined based on the result of the estimate.

 23 1 Some constants such as the retransmission interval the number of retries etc. that are defined in the TCP module of the communication processing unit for each of the SYN segment and the data segment.

 23 2 The predetermined time period TO arp which is illustrated in and defined in the ARP module of the communication processing unit .

Therefore when the DB request processing unit of the client receives the read reply through the communication processing unit the process in proceeds from step S to step S. Then the DB request processing unit returns the value DEF obtained from the read reply to the application .

In addition although the illustration is omitted in the case in which an administrative message is retransmitted is similar to the case that is illustrated in steps S and S. That is the administrative message is transmitted from the client to the node N and a reply to the administrative message is transmitted from the node Nto the client .

Next the operation sequence of the DB access performed after the takeover in with the suppositions different from those adopted in is described below with reference to . is a sequence diagram that illustrates DB access performed after the ARP table is updated in the client after the takeover in .

The suppositions for the operation sequence in are described in the following items 24 1 through 24 5 .

 24 1 Before the node Nbecomes faulty in step S in the client transmits a DB access request in which a key belonging to the key region Kis specified to the node N and then the client receives a DB access reply from the node N. In addition the transmission and reception of this DB access request and this DB access reply are performed on an established TCP connection.

 24 2 However for any reason the TCP connection described in item 24 1 has been closed in the normal procedure before step S in . For example when the application is once terminated the DB request processing unit may perform the process of closing the TCP connection which has been used for the application .

 24 3 Before the communication described in item 24 1 the ARP entry which is the same as the ARP entry in is created in the ARP table of the client .

 24 4 At the starting time point of the operation sequence in the ARP entry has not yet been deleted namely still remains on the ARP table of the client .

As described in item 24 4 above the ARP table of the client includes the ARP entry . However if the ARP entry is not used for some period of time for any reason such as the termination of the application the ARP entry is deleted as indicated in step S in because the communication processing unit performs the aging process on each entry in the ARP table .

Then after the deletion of the ARP entry the application of the client may be activated i.e. invoked again. Furthermore the application may instruct the DB request processing unit to perform the reading operation while specifying the key def . Then the DB request processing unit starts the process in .

The flow of the subsequent processes is similar to that in steps S through S in . That is the differences between steps S through S in and steps S through S in lie only in the key specified by the application and specific values of pieces of information that depend on the key.

Described simply below are steps S through S. First when the process in starts the first communication endpoint identified by the communication endpoint information 192.168.254.3 7000 is found out i.e. identified in step S.

Then in step S the DB request processing unit instructs the communication processing unit to transmit a read request. However according to the assumption in item 24 2 there is no TCP connection. Therefore the communication processing unit first tries to transmit a SYN segment.

Then the process in is called to transmit the SYN segment. Since the ARP entry has already been deleted in step S in no entry is found in the search in step S in . Therefore an ARP request is broadcast in step S.

The thus performed step S corresponds to step S in . In addition the IP address 192.168.254.3 is specified as the TPA in an ARP request that is broadcast in step S.

Meanwhile the IP address 192.168.254.3 is currently assigned to the network interface of the node Nas a result of the process in . Therefore as indicated in step S in an ARP reply is returned from the node N. In the ARP reply the MAC address 00 23 26 9B 35 EF of the node Nis specified as the SHA.

Then the client receives the ARP reply and updates the ARP table as indicated by step S in . The thus performed step S is indicated as step S in and specifically an ARP entry is added to the ARP table . The ARP entry associates the IP address 192.168.254.3 and the MAC address 00 23 26 9B 35 EF with each other.

The communication processing unit refers to the ARP entry and transmits a SYN segment through the network interface . Afterwards the node Ntransmits a SYN ACK segment and the client transmits an ACK segment. The three way handshake as described above is indicated by the bidirectional arrow of step S in .

Then as indicated in the next step S the DB request processing unit of the client transmits a read request on the TCP connection established in step S. The content of the read request is the same as that of the read request in .

The node N which receives the read request then operates according to and returns a read reply as indicated by step S in . The read reply includes the value DEF corresponding to the key def specified in the read request . The DB request processing unit which receives the read reply then returns the value DEF to the application in step S in .

As described above with reference to even after the physical node corresponding to a certain communication endpoint has changed the client is still able to communicate with this certain communication endpoint regardless of whether or not there is an old i.e. obsolete ARP entry still remaining in the ARP table .

Next the operations performed in the case where a new node Nis added to the broadcast domain in after the takeover in are described below with reference to .

First in step S a new node Nis added. The node Nmay be specifically realized by for example the computer in . In step S not only the hardware of the node Nis added to the distributed DB system but also the following operations 25 1 through 25 3 are performed.

 25 2 Installation of one or more programs and some pieces of data for enabling the computer as hardware to serve as the node N which is provided in the distributed DB system and configured as the node in .

 25 3 Assignment of a fixed IP address for maintenance to the network interface hereafter this fixed IP address is referred to as 192.168.254.136 for convenience of explanation .

The OS installed in the operation 25 1 may include one or more program modules for enabling the CPU to execute the processes in namely to function as the communication processing unit . Not only the OS but also one or more device drivers such as the Ethernet driver etc. are installed as necessary.

An example of the data to be installed in the operation 25 2 is the correspondence table in . An example of the program to be installed in the operation 25 2 is a program for enabling the CPU to execute the processes in namely to function as the key region management units through and the monitoring unit .

The operations 25 1 through 25 3 may be manually performed by the system administrator or may be automatically performed by the deployment server in . Anyway in step S the node Nis responsible for no key region. Therefore any IP address appearing on the correspondence table in has not been assigned to the network interface of the node N.

The node Nadded in step S starts the process in . In the example in assume that the node Nselects the communication endpoint identified by the communication endpoint information 192.168.254.3 7000 at random in step S in . Then in step S the node Ntries to transmit a takeover proposition.

However since the node Nhas just been added there are no TCP connections between the node Nand other devices. In addition in the ARP table of the node N there are no entries about the IP addresses appearing on the correspondence table .

Therefore the communication processing unit of the node Nfirst tries to establish a TCP connection between the following communication endpoints 26 1 and 26 2 .

 26 1 The communication endpoint on the node Nidentified by the communication endpoint information 192.168.254.136 7000 including the fixed IP address 192.168.254.136 described in relation to the operation 25 3 .

 26 2 The selected communication endpoint identified by the communication endpoint information 192.168.254.3 7000 .

The communication processing unit of the node Ntries to transmit a SYN segment in order to establish a TCP connection specifically it starts the process in . However as described above there is no entry about the IP address 192.168.254.3 in the ARP table of the node N. Therefore no entry is found in the search in step S in .

Then the communication processing unit broadcasts an ARP request in step S. The thus performed step S is indicated as step S in . The IP address 192.168.254.3 is specified as the TPA in an ARP request that is broadcast in step S.

When each device in the broadcast domain in receives the ARP request each device operates according to . Meanwhile the IP address 192.168.254.3 is being assigned to the network interface of the node Nat the time point in step S as a result of the takeover in .

Therefore as indicated by step S in an ARP reply is transmitted from the node N. In the ARP reply the MAC address 00 23 26 9B 35 EF of the network interface of the node Nis specified as the SHA.

When the communication processing unit of the node Nreceives the ARP reply the communication processing unit of the node Nupdates the ARP table in step S in . Specifically the communication processing unit of the node Nadds an ARP entry to the ARP table as indicated by step S in . The ARP entry associates the IP address 192.168.254.3 and the MAC address 00 23 26 9B 35 EF with each other.

Then the communication processing unit of the node Nsearches again the ARP table in step S in and finds the added ARP entry . Therefore a frame of a SYN segment is transmitted in step S.

Then the communication processing unit of the node Nreceives the SYN segment and transmits a SYN ACK segment. Then the communication processing unit of the node Nreceives the SYN ACK segment and transmits an ACK segment. As a result of the three way handshake above a TCP connection is established between the communication endpoint 26 1 on the node Nand the communication endpoint 26 2 on the node N.

Then the takeover proposition in step S in is transmitted on the TCP connection established in step S. Specifically as indicated by step S in a takeover proposition is transmitted from the node Nto the node N. The node Ntransmits the takeover proposition thereby proposing to the node Nthat the node Ntake over from the node Nthe communication endpoint identified by the destination IP address 192.168.254.3 and the destination port number 7000 .

Then in the example in when the node Nreceives the takeover proposition the node Nreturns an ACK reply in step S in response to the takeover proposition . For more details in the node N the supply control unit in the key region management unit corresponding to the IP address 192.168.254.3 which is the IP address of the first communication endpoint for the key region K returns the ACK reply .

Then the communication processing unit of the node Nreceives the ACK reply . Thus the node Nnewly generates a key region management unit corresponding to the key region K for more details corresponding to the IP address 192.168.254.3 . The process in then proceeds to step S.

In the description below for convenience of explanation it is assumed that the key region management unit in is newly generated in the node Nas described above. There is only one key region management unit in the node N.

The acquisition control unit of the key region management unit generated in the node Nthen transmits a takeover request to the communication endpoint 26 2 on the node Nin step S in . The thus performed step S is indicated as step S in .

As illustrated in a takeover request transmitted in step S may include for example the index 3 for identification of the key region Kto be taken over. Otherwise since the key region Kis identifiable by the destination IP address 192.168.254.3 itself of the takeover request it is not necessary for the takeover request to include the index.

Anyway upon receipt of the takeover request the node Nreturns a takeover reply as indicated in step S in . The takeover reply includes data of all entries whose keys belong to the key region Kand which are read and copied from the local store of the node N.

The above mentioned takeover proposition ACK reply takeover request and takeover reply are all transmitted and received on the TCP connection established in step S.

Upon receipt of the takeover reply through the communication processing unit the acquisition control unit of the key region management unit of the node Nstores into the local store the data of all entries included in the takeover reply . This is done in step S in .

Meanwhile upon completion of the transmission of the takeover reply the node Nstarts the process for closing the TCP connection. In the description below as with the assumption in item 20 1 relating to it is assumed for convenience that the key region management unit corresponding to the key region K that is corresponding to the IP address 192.168.254.3 in the node Nis the key region management unit in .

The supply control unit of the key region management unit of the node Ninstructs the communication processing unit to close the TCP connection used in the transmission of the takeover reply . Then the communication processing unit of the node Ntransmits a FIN ACK segment. Upon receipt of the FIN ACK segment the communication processing unit of the node Nreturns an ACK segment to the node N.

In addition after the node Nhas taken over the key region Kfrom the node N in more detail after the node Nhas taken over the first communication endpoint for the key region Kfrom the node N there is no particular data to be transmitted from the node Nto the node N. Therefore the communication processing unit of the node Nalso transmits a FIN ACK segment. Then upon receipt of the FIN ACK segment the communication processing unit of the node Nreturns an ACK segment to the node N. The TCP connection established in step S is closed in step S as described above.

In addition in step S the key region management unit of the node Nperforms the process for releasing the assignment of the IP address 192.168.254.3 to the network interface of the node N i.e. the process for dissociating the IP address 192.168.254.3 from the network interface of the node N .

Specifically the supply control unit of the key region management unit instructs the association unit to release the assignment. Then the association unit directly rewrites the interface configuration file or invokes the function of the communication processing unit by issuing a command such as the ifconfig command thereby indirectly rewriting the interface configuration file .

In any case the association between the following addresses 27 1 and 27 2 is deleted from the interface configuration file .

When the assignment of the IP address 192.168.254.3 to the network interface is released the supply control unit of the key region management unit of the node Nthen transmits an assignment instruction in the next step S. Specifically the assignment instruction is also transmitted through the communication processing unit and the network interface . In addition although omitted due to space limitations in the process in step S may further include the establishment of a TCP connection between two communication endpoints identified by using two fixed IP addresses.

The source IP address of the assignment instruction is the IP address 192.168.254.129 which is fixedly assigned to the node N. In addition the destination IP address of the assignment instruction is the IP address 192.168.254.136 which is fixedly assigned to the node N. Furthermore the source port number is for example 7000 and the destination port number is for example 7000 .

The TCP connection identified by the above mentioned source IP address source port number destination IP address and destination port number may be first established and the assignment instruction may be transmitted on this TCP connection.

The assignment instruction includes the IP address 192.168.254.3 to be newly assigned to the node N which is identified by the destination IP address of the assignment instruction . In the node N the assignment instruction is received by the acquisition control unit of the key region management unit through the communication processing unit .

Then the acquisition control unit performs the process for assigning the IP address 192.168.254.3 to the network interface in step S in according to the assignment instruction . That is the acquisition control unit instructs the association unit to perform the assignment. Then the association unit directly rewrites the interface configuration file or indirectly rewrites the interface configuration file through the communication processing unit .

As a result the MAC address of the network interface of the node Nand the IP address 192.168.254.3 are associated with each other in the interface configuration file . That is the IP address 192.168.254.3 is assigned to the network interface of the node N.

The above described process in step S in is indicated as step S in . Although omitted in the monitoring request unit of the key region management unit of the node Nthen performs the process in step S in . In addition if the termination condition is not satisfied in step S the node Nrepeats again the processes in from step S.

On the other hand in the node N the key region management unit corresponding to the key region Kdeletes the entries corresponding to the key region Kfrom the local store after the assignment of the IP address 192.168.254.3 is released in step S. Then the key region management unit deletes the key region management unit itself by for example terminating the thread of the key region management unit itself.

According to the operation sequence above illustrated in the IP address 192.168.254.3 is not assigned to any node in a very short time period from step S to step S. Therefore if a packet whose destination IP address is 192.168.254.3 is transmitted during this time period the packet is discarded and disappears.

However for example in the course of a certain process such as the timeout process with respect to a reply to this packet the forcible deletion of an ARP entry the broadcasting of an ARP request etc. are performed. Since the time period from step S to step S is very short it is expected that the assignment in step S is completed by the time for example the ARP request is broadcast. That is even if there is a time period in which the IP address 192.168.254.3 is not assigned to any node the substantial availability of the distributed DB system is hardly degraded.

In addition according to the procedure of steps S through S in the conflict in which the IP address 192.168.254.3 is simultaneously assigned to two nodes Nand Nis avoided without fail. It is generally more undesired that a certain IP address is assigned simultaneously to a plurality of devices than that the certain IP address is not assigned to any device. Therefore the procedure in steps S through S is preferable to avoid a problem.

Described below with reference to is the operation sequence in which the new node Nreplies to a DB access request from the client after the IP address 192.168.254.3 is assigned to the new node Nas described above.

 28 1 When the operation sequence in is started the ARP table of the client includes the ARP entry created in step S in or the ARP entry created in step S in . As illustrated in the ARP entries and are the same in content.

 28 2 The TCP connection established in step S in or in step S in has actually been disconnected by releasing the assignment of the IP address in step S in . Nevertheless when the operation sequence in is started the communication processing unit of the client recognizes that the TCP connection established in step S in or in step S in is still being established. This is because neither the client nor the node Nhas transmitted a FIN ACK segment and the keep alive operation at the TCP level is not performed in the present embodiment. Therefore when the operation sequence in is started the communication processing unit of the client does not recognize the disconnection of the TCP connection.

 28 3 The key region to which the key ghi belongs is the key region K which is identified by the index 3 .

Under the assumptions i.e. suppositions 28 1 through 28 3 the application of the client first instructs the DB request processing unit to perform the reading operation while specifying the key ghi . Then the DB request processing unit starts the process illustrated in . According to the assumption 28 3 and the first communication endpoint specified in step S in FIG. is specifically the communication endpoint identified by the communication endpoint information 192.168.254.3 7000 .

The DB request processing unit instructs the communication processing unit to transmit a read request to the first communication endpoint in step S in . Then the communication processing unit confirms whether or not there is a TCP connection. According to the assumption 28 2 the communication processing unit recognizes that there is a TCP connection and tries to transmit a read request on the established TCP connection. The transmission of the read request is indicated as step S in .

In the context of transmitting a data segment of the read request the process in is called. According to the assumption 28 1 an entry corresponding to the IP address 192.168.254.3 is found in the search in step S in . Therefore in step S the MAC address 00 23 26 9B 35 EF registered in the found entry is specified as the destination MAC address of the frame of the read request as illustrated in .

The frame of the read request is received by the network interface of the node Naccording to the destination MAC address and outputted to the communication processing unit of the node N. However the assignment of the IP address 192.168.254.3 to the network interface of the node Nidentified by the MAC address 00 23 26 9B 35 EF has already been released i.e. cancelled in step S in .

Therefore the communication processing unit of the node Njudges that the destination IP address of the read request is not an IP address of the node N and thus discards the read request . Therefore no reply to the read request is returned to the client .

On the other hand the DB request processing unit of the client waits for the reception of a reply to the read request as indicated by step S in . Note that the situation in which no reply to the read request is returned to the client is similar to the situation in which no reply to the read request transmitted in step S in is returned to the client .

Therefore although the detailed explanation is omitted an ARP request is broadcast also in step S in as with the flow of the processes in steps S through S in . In the retransmission performed by the TCP module of the communication processing unit of the client and the forcible deletion of the ARP entry or the ARP entry are omitted.

The IP address 192.168.254.3 is specified as the TPA in the ARP request which is transmitted in step S. Upon receipt of the ARP request each device in the broadcast domain in operates according to .

As a result as indicated by step S in an ARP reply is transmitted from the node Nbecause the IP address 192.168.254.3 is currently assigned to the network interface of the node Nas indicated in step S in .

The MAC address 00 24 D2 F0 94 3A of the network interface of the node Nis specified as the SHA in the ARP reply . The ARP reply is received by the client .

The reception of the ARP reply corresponds to step S in . Therefore as indicated by step S in the ARP table is updated in the client which has received the ARP reply .

Specifically as indicated by step S in a new ARP entry is added to the ARP table of the client . The ARP entry associates the IP address 192.168.254.3 and the MAC address 00 24 D2 F0 94 3A with each other. As described above the old ARP entry or is replaced with the new ARP entry .

When the ARP entry is added in step S in corresponding to step S in as described above the client then searches the ARP table in step S in again. As a result the newly added ARP entry is found.

The details of the course from step S to step S are omitted above but they are similar to those of the flow of the processes in steps S through S in . Therefore as well as the TCP connection is established in step S after the ARP entry is added in step S in a TCP connection is established also in step S in .

Specifically after the ARP entry is added in step S the TCP module of the communication processing unit of the client transmits a SYN segment whose destination IP address is the IP address 192.168.254.3 . Then the SYN segment is received by the node N and the node Ntransmits a SYN ACK segment. The client receives the SYN ACK segment and transmits an ACK segment.

As described above the TCP connection is established by the three way handshake between the communication endpoint on the client and the communication endpoint that is on the node Nand is identified by the communication endpoint information 192.168.254.3 7000 . Then a read request is retransmitted on the TCP connection thus established in step S.

Specifically the communication processing unit of the client starts the process in in order to transmit a data segment of the read request which has been specified by the DB request processing unit and has triggered the transmission in step S. Then as a result of the search in step S in the added ARP entry is found.

Therefore a frame of a read request is transmitted in step S. The thus performed step S is indicated as step S in .

The frame of the read request is different in its destination MAC address from the frame of the read request . That is the destination MAC address of the read request is 00 24 D2 F0 94 3A . However the destination IP address destination port number subtype key etc. are the same between the read requests and .

Then the read request is received by the node N. Then the node Noperates according to . As a result in step S in corresponding to step S in a read reply including the value GHI corresponding to the specified key ghi is transmitted from the node Nto the client .

The read reply is received by the network interface of the client and outputted to the DB request processing unit through the communication processing unit . In addition the length of the predetermined time period TO db in is appropriately determined in advance based on some constants such as the constants 23 1 and 23 2 as described above relating to . Therefore the DB request processing unit of the client is able to receive the read reply within the predetermined time period TO db. Therefore the process in performed by the client proceeds from step S to step S. Then the DB request processing unit returns the value GHI obtained from the read reply to the application .

The behavior of the entire distributed DB system under some specific conditions has been described above with reference to . According to the flowcharts in it is obvious that the distributed DB system also works well under other conditions.

For example when the client transmits a write request not a read request the distributed DB system also works well. In addition not the node Nnewly added as illustrated in but the existing node for example the node N may take over the key region K to be more specific the communication endpoint identified by the IP address 192.168.254.3 from the node N. Also in this case the takeover is successfully performed as in .

The flowcharts in include the processes of judging whether or not a reply is received within a predetermined time period. The length of the predetermined time period may be arbitrarily defined depending on the embodiments. In addition it also depends on the embodiments whether the transport layer or the application layer is responsible for controlling the retransmission and the forcible deletion of an ARP entry and thereby triggering the re establishment of a TCP connection. The explanation of indicates a mere example of the implementation.

Specifically for example transmission and reception of a request and a reply to it may be repeated plural times on a once established TCP connection. By so doing the influence of the overhead due to the establishment of a TCP connection is reduced for example when the client transmits many DB access requests.

However depending on the embodiments a TCP connection between two communication endpoints may be established only for one request and the reply to the request and may be closed in the normal procedure after the transmission of the reply.

Furthermore in the example in the TCP connection between the node Nand the node Nis closed in step S before the assignment of the IP address is released i.e. cancelled in step S. However depending on the embodiments one or more other TCP connections may also be closed before step S. That is the node Nmay close every TCP connection between the communication endpoint on another device and the communication endpoint that is on the node Nand that is identified by the communication endpoint information including the IP address 192.168.254.3 to be taken over by the node N.

The process i.e. the transition from step S to step S in corresponds to the takeover according to the flowchart in . That is the operation sequence sequentially illustrated in the operation sequence sequentially illustrated in and the operation sequence sequentially illustrated in are examples of the change from step S to step S in . Described below is the relationship between and .

The target communication endpoint in is a communication endpoint identified by one of two or more pieces of the communication endpoint information that are associated with a target subset which is one of the mutually disjoint plural subsets Kto Kof the domain K of the keys. In addition the process in includes transmitting a keep alive message in which the communication endpoint information that identifies the target communication endpoint is specified as the destination and monitoring the reply to the keep alive message. Furthermore the process in includes recognizing the occurrence of a failure in a first other computer when no reply is returned within the predetermined time period TO keepalive. The first other computer is specifically a computer provided with a network interface associated with the communication endpoint information specified as the destination of the keep alive message.

Assume that the process in is executed by the computer in . Under this assumption the change from step S to step S in corresponds to the takeover that is in accordance with the flowchart in and that is performed in the case where the above mentioned target subset is the particular subset Ka illustrated in and the computer recognizes the occurrence of the failure.

That is the destination of the keep alive message is the communication endpoint information Pa in . Therefore the above mentioned first other computer is the computer in as a monitoring target. In the following description let a second other computer be a computer provided with a network interface that is associated with a certain piece of the communication endpoint information where the certain piece of the communication endpoint information is one of two or more pieces of the communication endpoint information that are associated with the subset Ka and the certain piece of the communication endpoint information is not specified as the destination of the keep alive message.

Upon recognition of the occurrence of a failure in the computer the computer in acquires the entries in whose keys belong to the subset Ka as in steps S through S in . That is the computer requests the second other computer to read and transmit the entries and receives the entries from the second other computer . For example in the example in the node Ncorresponds to the first other computer that is the computer in the node Ncorresponds to the computer in and the node Ncorresponds to the second other computer .

Meanwhile indicates an example of the case in which the computer does not exist at the time point of step S in . That is when the computer is newly added and performs the process in the situation changes from step S to step S in .

Step S in corresponds to a step in which the computer determines the particular communication endpoint information Pa by selecting one of a predetermined number of pieces of the communication endpoint information as the particular communication endpoint information Pa which is associated with the particular subset Ka in . However depending on some embodiments the computer that performs the process in may receive an instruction that specifies the communication endpoint information Pa thereby determining the communication endpoint information Pa.

For example the deployment server in may further collect the information about the load of each node from each node in the distributed DB system. Then the deployment server may issue to the computer in an instruction that specifies the communication endpoint information Pa according to the collected information. For example if the load of the computer is heavy the deployment server may specify the communication endpoint information Pa which is being associated with the network interface Ia of the computer by the dynamic association information at the time of step S in .

In any case in as an example of the computer not existing in step S in is first newly added and then the computer in determines the communication endpoint information Pa in step S in . Then the computer acquires the entries by receiving the entries from a third other computer provided with the network interface Ia associated with the communication endpoint information Pa.

That is the above mentioned third other computer corresponds to the computer in . Specifically the computer requests the computer to read the entries from the memory included in the computer and to transmit the entries . As a result the computer receives the entries as described above.

In the example in the node Ncorresponds to the computer in that performs the process in and the node Ncorresponds to the computer in as the above described third other computer .

After step S in the computer may transmit the entries to a fourth other computer in response to a request from the fourth other computer . The fourth other computer is specifically a computer provided with one of the plurality of memories that store the DB in a distributed manner. Then the computer may further release i.e. cancel the association between the communication endpoint information Pa and the network interface Ib of the computer

For example in the example in the node Ncorresponds to the computer in as described above. In this context also in let s regard the node Nas corresponding to the computer in . Thus the fourth other computer in the example in is the node N. In addition the process in step S in corresponds to the transmission of the entries and step S corresponds to the release of the association between the communication endpoint information Pa and the network interface Ib.

Furthermore the computer may notify the fourth other computer that the association is released. The transmission of the assignment instruction in step S in also serves as a notification that the association is released. This is because the assignment of the IP address 192.168.254.3 to the network interface of the node Nis allowed only after the association between the IP address 192.168.254.3 and the network interface of the node Nis released in the node N. Accordingly the assignment instruction implies that the association has been released in the node N.

The present invention is not limited to the embodiments above. Some modifications have been described above but the embodiments above may be further modified from the following viewpoints for example. In addition each of the modifications described above and below may be arbitrarily combined with another of them unless they are inconsistent with one another.

Some processes in the embodiments above include the comparison with a threshold. For example in step S in the time period in which the node performing the process of waits for a reply is compared with the predetermined time period TO bulk. Depending on the embodiments the comparison with the threshold may be the process of judging whether or not the value to be compared exceeds the threshold or may be the process of judging whether or not the value to be compared is equal to or exceeds the threshold.

In addition in the explanation above some specific values are exemplified relating to the thresholds the IP addresses the port numbers the MAC addresses etc. but these specific values are provided only for convenience of explanation.

Furthermore the value of M which appears in formula 1 etc. and means the number of key regions is also arbitrary depending on the embodiments. In the correspondence table in for convenience of illustration a relatively small value of M namely 16 is exemplified. However there may be a case where M 128 as indicated by formula 8 for example. A further larger value may also be used as M.

However it is preferable that the number M of the key regions is about three through ten times larger than the number of physical nodes. This is because the load may possibly be too unbalanced among the nodes if the number M of the key regions is too small.

For example assume that the number of nodes is 16 and that each key region is associated with three communication endpoints as in the correspondence table in . In addition for simple explanation it is assumed that the number of entries and the access frequency are well balanced among the key regions. Under the assumptions above the comparison between the case where M 16 and the case where M 128 is described below.

For example when M 16 a total of 48 3M communication endpoints are dynamically assigned to 16 nodes. Therefore each node is responsible for 3 48 16 key regions on average.

Assume that a certain node becomes faulty and that another node which has been responsible for three key regions takes over one communication endpoint from the faulty node. In this case the load of the latter node which is responsible for four communication endpoints as a result of the takeover is 4 3 times that is about 1.33 times larger than the load of any one of other nodes which are each responsible for three communication endpoints on average.

On the other hand when M 128 a total of 384 3M communication endpoints are dynamically assigned to 16 nodes. Therefore each node is responsible for 24 384 16 key regions on average.

Assume that a certain node becomes faulty and that another node which has been responsible for 24 key regions takes over one communication endpoint from the faulty node. In this case the load of the latter node which is responsible for 25 communication endpoints as a result of the takeover is 25 24 times that is about 1.04 times larger than the load of any one of other nodes which are each responsible for 24 communication endpoints on average.

As well understood from the examples above the smaller the number M of the key regions is at the coarser granularity the loads are distributed to the nodes. Therefore the smaller the number M of the key regions is the larger the load imbalance among the nodes tends to be. Therefore to reduce the load imbalance it is preferable that the number M of the key regions is for example about three through ten times larger than the number of physical nodes.

In the embodiments above the keep alive message is a control message that is different from the DB access request. However there may be an embodiment in which a DB access request is used as a keep alive message.

For example when the node Nmonitors the node Nas in the node Nmay transmit to the node N a write request in which a pair of appropriately selected key and value is specified. The node Nmay then monitor a reply from the node N. Then the node Nmay recognize that the node Nis faulty if no reply is received from the node Nwithin a predetermined time period.

Upon receipt of a reply from the node Nwithin the predetermined time period the node Nmay further transmit to the node N a read request in which the same key as that specified in the write request above. The node Nmay then monitor a reply from the node N. If no reply is received within the predetermined time period from the node N the node Nmay recognize that the node Nis faulty.

When the node Nreceives a reply from the node Nwithin the predetermined time period the node Nmay compare the value included in the reply to the read request with the value specified in the write request. Then the node Nmay recognize that the node Nis normal if the two values are equal to each other and may recognize that the node Nis faulty if the two values are different.

A failure that occurs for example only within the read write processing unit is also detectable according to the embodiment in which the write request and the read request in both of which the same key is specified are used instead of the keep alive message as described above.

Furthermore in the process in two types of control messages that is the takeover proposition and the takeover request are used. However according to some embodiments one type of control message serving as both a takeover proposition and a takeover request may be used. In this case the following reply 29 1 or 29 2 is returned.

 29 1 A reply serving as an ACK reply to a takeover proposition and also serving as a takeover reply to a takeover request.

Incidentally the correspondence table is exemplified in as a specific example of the correspondence table in and also as a specific example of the correspondence table in . The IP addresses exemplified in the correspondence table are all private IP addresses. However global IP addresses are also available.

For example when a plurality of nodes are distributed to different network segments as illustrated in global IP addresses may be used. For example for convenience of explanation the following assumptions 30 1 through 30 4 are used.

 30 1 The range of global IP addresses to be assigned to the devices in the broadcast domain in is 200.1.2.0 24 .

 30 2 In this range 24 IP addresses 200.1.2.1 through 200.1.2.24 are available as the IP addresses used for the communication endpoint information appearing in the correspondence tables and .

 30 3 The range of global IP addresses to be assigned to the devices in the broadcast domain is 200.1.3.0 24 .

 30 4 In this range 24 IP addresses 200.1.3.1 through 200.1.3.24 are available as the IP addresses used for the communication endpoint information appearing in the correspondence tables and .

Under the assumptions 30 2 and 30 4 48 communication endpoints are defined using a total of 48 IP addresses. Therefore according to the assumptions 30 2 and 30 4 it is possible to associate three communication endpoints with each of the 16 key regions as with the correspondence table .

It is only a coincidence that the same number of IP addresses are defined in the assumptions 30 2 and 30 4 . Depending on the environment for example 30 IP addresses in the range 200.1.2.0 24 and 18 IP addresses in the range 200.1.3.0 24 may be used.

In the example in where the correspondence table is used the 48 IP addresses appearing in the correspondence table are assignable to any of the nodes Nthrough Nin the broadcast domain in . However under the assumptions 30 1 through 30 4 the assignment of the IP addresses is restricted.

Specifically under the assumptions 30 1 and 30 3 the 24 IP addresses described in the assumption 30 2 are assignable to the nodes Nthrough Nin but are not allowed to be assigned to the nodes Nand N. In addition under the assumptions 30 1 and 30 3 the 24 IP addresses described in the assumption 30 4 are assignable to the nodes Nand N but are not allowed to be assigned to the nodes Nthrough N.

In the embodiment in which the assignment of the IP addresses is thus restricted the processes in are modified to satisfy the restriction.

Specifically step S in is modified so as to select one of the communication endpoints each identified by an IP address assignable to the node that performs the process in . For example when the node Nperforms the process in a communication endpoint identified by one of the IP addresses described in the assumption 30 2 is selected in step S.

In addition the processes in may be modified so as to satisfy the condition that the IP address of the target communication endpoint in is an IP address assignable to the node that performs the process in .

Specifically the processes in may be modified as indicated in the following items 31 1 through 31 3 .

 31 1 Step S in is modified so as to select the destination of a monitoring request from among other nodes to which an IP address assignable to the node that performs the process in is also assignable. For example when the node Nperforms the process in the destination of the monitoring request is selected from between the node Nand the node N.

 31 2 Step S in is modified so as to select the destination of a monitoring request from among other nodes to which an IP address assignable to the node that performs the process in is also assignable. For example when the node Nperforms the process in the destination of the monitoring request is selected from between the node Nand the node N.

 31 3 Step S in is modified so as to select the destination of a monitoring request from among other nodes to which an IP address assignable to the node that performs the process in is also assignable. For example when the node Nperforms the process in the destination of the monitoring request is selected from between the node Nand the node N.

Otherwise instead of the modifications as described in the above items 31 1 through 31 3 the processes in and after step S in may be modified as indicated in the following items 32 1 through 32 3 below.

 32 1 The step of judging whether or not the IP address of the target communication endpoint is assignable to the node that performs the process in is added before step S.

 32 2 When it is judged in the added step described in the item 32 1 that the IP address of the target communication endpoint is assignable to the node that performs the process in the processes in and after step S are performed.

 32 3 If it is judged in the added step described in the item 32 1 that the IP address of the target communication endpoint is not allowed to be assigned to the node that performs the process in the processes in and after step S are not performed. Instead the node selects another node to which the IP address of the target communication endpoint is assignable and notifies the selected node that a failure has occurred in the target communication endpoint. Then instead of the node the notified node performs the processes in steps S through S.

Provided below is further detailed description about access to the node from the client such as the client in and the client PC in that belongs to a broadcast domain different from the broadcast domain to which the node belongs.

In the embodiment in which there may occur access from the client that belongs to a broadcast domain different from the broadcast domain to which the node belongs global IP addresses are used as IP addresses included in pieces of the communication endpoint information dynamically assigned to the nodes. That is the IP addresses appearing in the correspondence table in the node as well as appearing in the correspondence table in the client are global IP addresses. Therefore the destination IP address of a DB access request transmitted by the client is a global IP address.

For example assume that the assumptions 30 1 through 30 4 hold true and also assume that the global IP address 200.1.2.10 is assigned to the network interface of the node Nin at a certain time point. In addition assume that the client PC in transmit a DB access request in which a key belonging to the key region corresponding to this global IP address 200.1.2.10 is specified. Then the DB access request is transmitted to the node Nthrough the Internet and the router .

Specifically the DB access request is transmitted to the router through the Internet based on the network address part of the IP address 200.1.2.10 . Then unless there is still an obsolete entry which is inconsistent with the current situation in the ARP table of the router the DB access request is transmitted from the router to the node Ncorrectly.

The router may update its ARP table by transmitting an ARP request from the router itself and receiving an ARP reply to the ARP request. In addition the router may also update its ARP table by receiving an ARP request transmitted by another device in the broadcast domain .

Therefore in many cases the ARP table of the router reflects the situation how the IP addresses described in the assumption 30 2 namely the IP addresses to be dynamically assigned are currently assigned to the nodes Nthrough Nin the broadcast domain .

However there may occasionally be a case in which an obsolete entry inconsistent with the current situation remains in the ARP table of the router . In this case the DB access request is discarded in the broadcast domain and thus the client PC is unable to receive a DB access reply. However the obsolete entry disappears some time from the ARP table of the router . Therefore the client PC may time out may then wait for an appropriate time period and may retransmit the DB access request.

As another example each of the nodes Nthrough N that is the node in may operate as follows in order to enable the ARP table of the router to be surely updated each time the assignment of the IP addresses to the nodes Nthrough Nchanges. That is each time the association unit performs the process of associating a new IP address with the network interface the communication processing unit may transmit an ARP request.

Specifically the communication processing unit may set the new IP address in both the TPA target protocol address and the SPA sender protocol address set the MAC address of the network interface in both the THA target hardware address and the SHA sender hardware address and transmit the ARP request. For example the association unit may instruct the communication processing unit to transmit the above mentioned ARP request. For more details the association unit may instruct the communication processing unit to transmit the above mentioned ARP request each time the association unit performs the process in step S in or the process in step S in .

If a device for example the router which has received the above mentioned ARP request has an entry corresponding to the IP address specified in the SPA in its ARP table the device update the entry. Therefore by each of the nodes Nthrough Noperating as described above an obsolete entry in the ARP table of the router is surely updated each time the assignment of the IP addresses to the nodes Nthrough Nchanges.

As a result the DB access request transmitted by the client PC is correctly forwarded to the destination node for example the node Nin the example above by the router . Consequently the destination node replies to the DB access request and therefore the client PC is able to receive a DB access reply.

Obviously the ARP request in which the same new IP address is specified in both the TPA and the SPA as described above may be similarly transmitted also in the embodiment of the network environment illustrated in . The above mentioned ARP request enables the change in the association between the network interface and the communication endpoint to be quickly reflected in the ARP table. Therefore the transmission of the above mentioned ARP request has the effect of shortening the average latency of the DB access.

In addition in the embodiment above it is mainly assumed that the Ethernet is used in the link layer the IP is used in the Internet layer and the TCP is used in the transport layer. However a communication protocol s may be changed according to an embodiment.

For example the UDP may be used in the transport layer. In this case the modules operating in the application layer for example the key region management units through and the monitoring unit in the DB request processing unit in etc. may be modified as described in the following items 33 1 and 33 2 .

 33 1 The modules may be modified so as to realize a connection based session management function similar to that provided by the TCP.

 33 2 The modules may be modified so as to be responsible for clearing the ARP cache when an IP address is dynamically re assigned.

In addition the standards other than the Ethernet standard are also available. For example InfiniBand the VI architecture virtual interface architecture etc. which are used as the interconnect between servers in a server cluster may be used in the communications between the nodes and the communications between the node and the client. That is any protocol or any protocol suite other than those exemplified above is available so far as it provides a mechanism to associate a physical network interface and a logical communication endpoint with each other. The communication processing unit of the node and the communication processing unit of the client may be appropriately implemented depending on the actually used protocol or protocol suite .

Various embodiments are described above each of them has the effect of simplifying the mechanism in the application layer for tracking i.e. following the change in state that may arise when a DB is distributed to and stored in memories each of which is included in each of a plurality of nodes.

The reason for such an effect is that not direct and dynamic association but indirect association is used to manage which of the subsets Kto Kin the domain K of the keys each node that is the memory of each node corresponds to. To be more specific the explanation is given as follows.

In the embodiments above a subset and communication endpoint information are statically associated with each other. Furthermore the communication endpoint information thus statically associated with the subset is further dynamically associated with a network interface that is the network interface of a node for providing access to a memory storing entries of a DB. As a result the subset and the memory are indirectly associated with each other.

A change in state that may arise in the distributed DB system is a change in node configuration that is a change in the above mentioned indirect association between the memory of an individual node and a subset in the domain of keys. In addition the association between the subset and the communication endpoint information is used in indirectly associating the memory and the subset with each other but does not have to be tracked because it is static as indicated by the static association information regardless of the change in state. Accordingly so far as tracking the change of the association between the communication endpoint information and the network interface is realized n.b. this association is used in the indirect association between the memory and the subset tracking the change in state in the distributed DB system is also realized.

In addition the use of a certain communication protocol for example the ARP implemented in the layer lower than the application layer makes it possible to track the change of the association between the communication endpoint information and the network interface. For example the dynamic association information in may be realized by the ARP table and tracking the change of the dynamic association information may be realized by the ARP.

Thus according to the embodiments above the process for tracking i.e. following the dynamic change in the node configuration is mostly encapsulated i.e. hidden in the layer s lower than the application layer. That is according to the embodiments above a complicated protocol etc. in the application layer for exchange of control information among the nodes is not required.

Therefore according to the embodiments above the use of a certain communication protocol such as the ARP etc. implemented in the layer lower than the application layer makes it possible to track the change in state in the distributed DB system. In addition according to the embodiments above the use of the existing communication protocol in the lower layer such as the ARP etc. makes it possible to greatly simplify the mechanism in the application layer for tracking the change in state in the distributed DB system.

Furthermore the various embodiments above each have the effect of reducing the cost for tracking the change in state that may arise when a DB is distributed to a plurality of memories. There are various types of costs for tracking the change of the node configuration in the distributed DB system due to the addition deletion etc. of the node. For example there are various types of costs such as the processing load in each node the communication load between the nodes the communication load between the node and the client the complexity of the communication protocol the amount of pieces of information that are held by individual nodes and the clients for administrative purposes etc. According to the embodiments above these various costs are reduced for the following reasons.

First the range of entries that a node stores in its memory i.e. the key region for which the node is responsible and a communication endpoint are statically associated with each other by the static association information in to be more specific by the correspondence tables and . The cost of the static association is very low because it costs very little to once store the static association information for example to copy the correspondence table in from the deployment server in to the node in and no maintenance cost is required.

In addition as understood from the example of the correspondence table in the data amount of the static association information is of linear order with respect to the number M of the key regions and the number M of the key regions is a constant which is not very large. Therefore relating to the static association information the cost in the sense of the data amount is also low.

Second since the consistent hashing is realized the processing load due to the change in node configuration is also reduced.

Generally in a large distributed DB system including a large number of nodes it is not rare that at least one node is faulty. This is because the number of nodes is large. In addition one of the great merits of the distributed DB system is the scalability that increasing the number of nodes i.e. scaling out makes it possible to cope with the increase in the data amount. Therefore in the distributed DB system a change in node configuration due to the increase or decrease in the number of nodes may frequently arise.

On the other hand the processing load for changing a key region for which a node is responsible that is the processing load for the redistribution of data among the nodes is not light if the data amount is large. This is because there arises the process of reading a large amount of data from a memory and transmitting the read data and there also arises the process of receiving such a large amount of data and writing the received data to a memory.

Therefore the performance of the entire distributed DB system may be largely degraded if each change in node configuration always causes multiple nodes which are not directly involved in this change to alter the key regions in their charge. Therefore it is preferable to provide a mechanism to prevent most nodes from altering the key regions in their charge even if the node configuration changes. Specifically it is preferable to realize the consistent hashing.

In the distributed DB system according to the present embodiment the consistent hashing is realized as clearly illustrated particularly in . That is even if the number of nodes changes e.g. even if a new node is added or an existing node is isolated from the distributed DB system for any reason such as a failure etc. it is sufficient that only a few of all the nodes in the distributed DB system change the key regions in their charge. In addition when the correspondence between nodes and key regions changes for any purpose such as the correction of the load imbalance among the nodes etc. only a few of all the nodes in the distributed DB system change the key regions in their charge.

Thus according to the embodiments above a preferable condition for the distributed DB system that is the consistent hashing is satisfied. Therefore the processing load for the redistribution of the data among the nodes is low.

Third since tracking a change in node configuration is realized by using a relatively simple protocol such as the ARP etc. the cost in the sense of the complexity of the protocol is also low.

Without a complicated and dedicated protocol which requires the exchange of a large number of control messages a change in node configuration is trackable i.e. followable according to the embodiments above. That is the use of the ARP tables and as the dynamic association information in to realize tracking the change in node configuration makes it possible to reduce the cost in the sense of the complexity of the protocol.

Since no complicated protocol is required in the application layer the embodiments above each have the effect of reducing the burden of programming and debugging imposed on a programmer who develops a distributed DB system. That is according to the embodiments above part of the mechanism to realize tracking the change in node configuration in the distributed DB system is encapsulated i.e. hidden in the layer lower than the application layer. As a result a burden imposed on the programmer to develop the application of the distributed DB system according to any embodiment above is lighter than that imposed on him her to develop a system in which a complicated protocol is used in the application layer.

Fourth relating to the dynamic association information the cost in the sense of the data amount is also low.

The number of entries held in each of the ARP tables and only for the distributed DB system according to the embodiments above is at most the number of IP addresses dynamically assigned depending on the correspondence between the key regions and the nodes. Specifically the data amount increased in each of the ARP tables and only for the distributed DB system according to the embodiments above is of linear order with respect to the number M of the key regions and the number M of the key regions is the constant not exceedingly large. Therefore relating to the dynamic association information the cost in the sense of the data amount is also low.

Fifth part of the cost for tracking i.e. following the change in node configuration is absorbed by a process performed regardless of whether the node configuration changes or not. Therefore the cost reduction for the absorbed cost is realized. The details are described as follows.

In the embodiments above the change in node configuration is tracked by dynamically associating a node for more details the network interface of the node and a communication endpoint with each other. In addition the dynamic association between the node and the communication endpoint is performed by any computer with the network communication function regardless of whether the node configuration changes or not. That is the correspondence between the network interface of the node and the communication endpoint is repeatedly confirmed and memorized regardless of whether the node configuration changes or not.

For example since a lifetime is set for each ARP entry an ARP request is transmitted again and again regardless of whether the node configuration changes or not. As a result the correspondence between the MAC address and the IP address is repeatedly confirmed and stored in the ARP table again.

That is according to the embodiments above the process routinely performed even if the node configuration is not changed is also used as the mechanism for making it possible to track i.e. to follow the change in node configuration. Therefore the processing load newly caused only for making it possible to track the change in node configuration is relatively light. To be more specific refer to the following description.

According to the embodiments above there is obviously a case where a load of the transmission of an ARP request is caused directly by the change in node configuration. However an ARP request may also be transmitted when there is no change in node configuration.

For example there is a case where an old ARP entry is deleted and consequently an ARP request is transmitted. Such a case may arise due to the mere passage of time namely may arise even if the node configuration is not changed. To be more specific for example when keep alive messages and or other administrative messages are periodically transmitted between the nodes an ARP request is transmitted in response to the deletion of an ARP entry due to the lapse of time. As another example when there is a long interval between instances of DB access an ARP request may be transmitted in response to the deletion of an ARP entry due to the lapse of time.

Therefore when the ARP tables and are updated in response to an ARP request which is transmitted due to the cause other than the change in node configuration for example a cause such as the lapse of time etc. the change in node configuration may be reflected in the ARP tables and in this opportunity. That is the process performed regardless of whether the node configuration changes or not may sometimes realize tracking the change in node configuration. The thus realized tracking is exemplified in the transmission of the ARP request in step S in and the resultant addition of the ARP entry in step S.

That is the process performed regardless of whether the node configuration changes or not also serves as part of the process to realize tracking the change in node configuration namely substitutes for part of the process to realize tracking the change in node configuration. For the substituted part of the process the cost to realize tracking the change in node configuration is reduced.

For the first through fifth reasons described above various costs are able to be reduced according to the embodiments above. In addition since a device such as a gateway server which may be a SPoF and also may be the bottleneck of the performance is not required according to the embodiments above the embodiments above are excellent in fault tolerance and performance.

In the embodiments above a pair of an IP address and a port number is used as the communication endpoint information or an IP address is used as the communication endpoint information. Such communication endpoint information is more excellent than an FQDN which is more logical than such communication endpoint information in the following points.

A DNS server is required to resolve an FQDN to an IP address. Therefore the DNS server may be a SPoF and also may be the bottleneck of the performance of the entire distributed DB system. On the other hand no central managing server which may be a SPoF and also may be a bottleneck is required to resolve an IP address to a MAC address by using an ARP request and an ARP reply to it.

In addition when a computer performs a communication an FQDN is resolved to an IP address. Therefore if an FQDN which is statically associated with an individual key region is used as communication endpoint information it is necessary to re register the association between the FQDN and the IP address in the DNS server each time the correspondence between the key region and the node changes. In addition each time the FQDN of a certain key region is taken over from one node to another node a device i.e. a client or some node which attempts to perform the communication using this FQDN is forced to issue an inquiry to the DNS server. Unlike the broadcasting of an ARP request the above mentioned re registration in the DNS server and the above mentioned inquiry to the DNS server are not absorbed by the process performed regardless of whether the node configuration changes or not. Therefore the use of the FQDN does not lead to a reduction in the cost.

Accordingly the communication endpoint information expressed by a pair of an IP address and a port number or that expressed by an IP address is more preferable as the communication endpoint information according to the embodiments above than more logical information such as an FQDN.

All examples and conditional language provided herein are intended for the pedagogical purposes of aiding the reader in understanding the invention and the concepts contributed by the inventor to further the art and are not to be construed as limitations to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although one or more embodiments of the present invention have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

