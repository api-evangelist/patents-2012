---

title: Method and a control node in an overlay network
abstract: A first control node and a method therein for selecting the first control node or a second control node to act as a server are provided. The first and second control nodes are comprised in an overlay network. The first control node obtains a first indication relating to a ranking of a suitability of the first control node to act as the server. Furthermore, the first control node receives a second indication from the second control node. The second indication relates to a ranking of a suitability of the second control node to act as the server. Then, the first control node selects, based on the first and second indications, one of the first and second control nodes to act as the server for managing a master representation of a distributed shared memory being accessible within the overlay network.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08849977&OS=08849977&RS=08849977
owner: Telefonaktiebolaget LM Ericsson (Publ)
number: 08849977
owner_city: Stockholm
owner_country: SE
publication_date: 20120309
---
Embodiments herein relate to a first control node and a method therein for selecting the first control node or a second control node to act as a server for a Distributed Shared Memory being accessible within an overlay network.

The Web is becoming more interactive than it has ever been before. It is now possible to implement synchronous video conferencing applications running in a web browser either using plug ins or new Hyper Text Markup Language 5 HTML5 Application Programming Interfaces APIs which will become widespread in a near future. Eventually this will make it possible to implement cost effective and highly customized solutions for various vertical markets for example e health rather than having to use a big generic one size fit all horizontal solution.

While video and audio conferencing running in a web browser makes it possible to communicate in new ways it essentially turns a web browser executing a customized collaboration application into a synchronous communication platform. This also leads users to expect that other user interface components managed by the collaboration application also form a part of the communication. For example in an e health application users may want to share items like diagrams pictures sensor data text documents or even run web applications together with peers e.g. other users in a conference session. A natural complement is therefore some kind of synchronization framework that allows the users to share the items managed by the collaboration applications with each other.

Distributed Shared Memory DSM framework. The DSM framework makes it possible to synchronously share data of a web application in real time with other users. This is possible since the DSM framework provides a memory or data storage that can be shared between web applications. In short the DSM is a distributed global addressable memory space where every memory space is assigned a unique address. By knowing this address it is possible to get a copy or reference to that memory.

In a schematic block diagram an exemplifying implementation of DSM is shown. In this example an exemplifying DSM Server manages a DSM Master referred to as memory or data storage above. Each of two DSM Clients manages a respective DSM Replica . Moreover each of the DSM Clients comprises a respective User interface for interaction by a user equipment with the respective DSM Replica . Hence in this example each DSM Client acquires the DSM Replica i.e. a local copy of the DSM Master and then synchronizes each of the DSM Replicas when needed. Synchronization is needed when contents of the DSM Replicas differs from contents of the DSM Master . Any modification to a particular DSM Replica is synchronized so that every DSM Replica converges to the same state after some time. At start up the DSM Server creates the DSM Master implicitly if requested by any DSM Client. Moreover when no DSM Client is connected to the DSM Master the DSM Master is automatically garbage collected. This means that any memory allocated by the DSM Master is no longer locked to the DSM Master.

As an example a developer may use Web Connectivity which is an API framework to create an overlay network in the application layer. In the overlay network applications running in any context have a uniquely addressable Unique Resource Identifier URI . These applications may act as servers in the overlay network. These URIs are uniform for the application regardless of whether it runs on a server or client native or browser. One use of the Web Connectivity API is to create on the fly a server in a web application which is executed in a runtime environment of a web browser. Once the session ends and the user navigates away from the current page the server is shut down and becomes inaccessible. It shall also be said that Web Connectivity is sometimes referred to as Warp.

An objective of at least some embodiments is to improve web collaborative frameworks such as the DSM framework mentioned above. This and other objectives may be achieved by one or more embodiments of the present invention disclosed herein.

According to an aspect a method is provided in a first control node for selecting the first control node or a second control node to act as a server. The first and second control nodes and a subscription managing node are comprised in an overlay network. The overlay network is overlaid onto an IP network. The subscription managing node is configured to provide a communication channel of the overlay network between the first and second control nodes. The first control node obtains a first indication relating to a ranking of a suitability of the first control node to act as the server. Furthermore the first control node receives over the communication channel a second indication from the second control node via the subscription managing node. The second indication relates to a ranking of a suitability of the second control node to act as the server. Then the first control node selects based on the first and second indications one of the first and second control nodes to act as the server for managing a master representation of a Distributed Shared Memory DSM being accessible within the overlay network.

According to another aspect a first control node is provided that is configured to select the first control node or a second control node to act as a server. The first and second control nodes are configured to be comprised in an overlay network. The overlay network is configured to be overlaid onto an IP network. Furthermore the overlay network is configured to comprise a subscription managing node. The subscription managing node is configured to provide a communication channel of the overlay network between the first and second control nodes. The first control node comprises a processing circuit configured to obtain a first indication relating to a ranking of a suitability of the first control node to act as the server. The processing circuit is further configured to select based on the first and second indications one of the first and second control nodes to act as the server for managing a master representation of a distributed shared memory being accessible within the overlay network. Moreover the first control node comprises a receiver configured to receive over the communication channel a second indication from the second control node via the subscription managing node. The second indication relates to a ranking of a suitability of the second control node to act as the server.

According to a still further aspect a computer program product is provided that is configured to perform one or more embodiments of the method in the first control node.

Since the first control node obtains the first and second indications relating to a ranking of a suitability of the first control node and the second control node respectively to act as the server the first control node is able to select or determine which one out of the first and second control nodes to be set as the server. In this manner the DSM is made less dependent on a permanent server for hosting of a master representation of the Distributed Shared Memory DSM also referred as a DSM Master. Thus the DSM has been improved in that it is less dependent on a permanent server. Consequently the above mentioned objective is achieved. Thanks to that the DSM is less dependence on a permanent server the DSM framework becomes more robust in terms of availability.

An advantage that may be provided by one or more embodiments herein is that logic involved in selection of control node to act as server is implemented in control nodes such as the first control node of the overlay network. Therefore it is preferred that all control nodes selects who to act as the server based on the same or similar criteria. However in a web based system an upgrade of a control node is obtained by a refresh of a web page comprising all or parts of the DSM.

Hence by leaving it to the control nodes to decide at each specific time which control node should act as the server the most suitable control node may at any time take the role to act as the server.

Moreover there is no need to wait for a specific server to come online before users may begin to work with a replica i.e. a copy of a master representation of the DSM.

Also a user or a developer using the DSM framework do not need to take into consideration which entity such as a computer or other node in the overlay network should act as the server.

Throughout the following description similar reference numerals have been used to denote similar elements network nodes parts items or features when applicable.

As part of describing embodiments herein a problem will be identified and discussed in the following.

By combining a framework like DSM with Web Connectivity it is possible to create a client server architecture in an overlay network. The overlay network is overlaid onto an IP network. The IP network comprises nodes such as Personal Computers pieces of hardware in a computer cluster or the like. In such client server architecture the server functionality may move around among the nodes. That is to say any node may host a DSM Master. Any DSM Master can then be addressed using a unified addressing schema.

In normal client server architecture the server is located at an address that normally does not change very often. Thus clients connect to the server while using the address. However as in the case with the client server architecture based on a combination of DSM and network overlay network framework such as the aforementioned Web Connectivity API all nodes can act as both a server and a client. Therefore the server address space becomes much more complex and how to find a server becomes a much more complicated task.

According to prior art a server is not always referenced directly by its address but rather by a domain name. In this case a Domain Name Server DNS is used to lookup the server address. If this approach is used in a system such as the DSM framework where servers come and go frequently it become quite problematic to keep the DNS up to date. If the DNS is not up to date clients will not be able to access the server by referring to its domain name.

In an exemplifying peer to peer context two clients are running the exact same software and would like to share something using DSM. Then it is not trivial to determine who should host the DSM server and how would the address for that sever be communicated between the peers.

The overlay network comprises a first control node a second control node a third control node . As used herein the expression control node may refer to a user equipment a mobile phone a cellular phone a Personal Digital Assistant PDA a smartphone a laptop equipped a portable electronic communication device a general purpose computer or the like.

The first second and third control nodes may be capable of acting as a server or a client within the overlay network . This means for example that the first control node may sometimes act as the server for managing a master representation of a DSM. In other occasions the first control node may act as the client managing a replica of the master representation of the DSM. In these occasions the second or third control node acts as the server.

Furthermore the overlay network comprises a subscription managing node such as a publish and subscribe publish subscribe service in the aforementioned Web connectivity API. The subscription managing node is configured to provide a communication channel A between the first second and third control nodes in the overlay network . Any information transferred in the communication channel A between the first second and third control nodes is passed through or via the subscription managing node .

The communication channel may be associated with an identifier such as a key which may be used for identification of the communication channel. The key may be referred to as a service key since the subscription managing node provides the publish and subscribe service.

As an example the publish and subscribe service is comprised in the subscription managing node . The subscription managing node may be responsible for relaying incoming messages to any other nodes such as one or more of the control nodes . The incoming messages refer to messages received by the subscription managing node . The subscription managing node relays any incoming message to all nodes which subscribe to messages published with the identifier. A message sent to the publish and subscribe service i.e. the subscription managing node with that identifier will be relayed to all other nodes which subscribe to that specific identifier.

In a schematic combined signalling and flow chart of an exemplifying method for selecting the first control node or the second control node to act as the server is shown. As mentioned the first and second control nodes and the subscription managing node are comprised in the overlay network which is overlaid onto an IP network . Again the subscription managing node is configured to provide the communication channel of the overlay network between the first and second control nodes .

The method may comprise the following actions which may be performed in any suitable order. For each of the actions below the action will be described and exemplified. Following the description and example purpose effects and the like may be discussed. In exemplifying actions that appear in only some embodiments are indicated by dashed lines.

The first control node may select the first control node to act as the server. As a result time for initializing and starting the functionality related to the DSM may be reduced.

When this action is performed before action i.e. the selecting of the first or second control node the first control node is allowed to directly act as the server. Moreover the first control node need not wait until indications relating to ranking of other control nodes have been received from one or more other control nodes via the subscription managing node when this action is performed.

In an exemplifying scenario the second control node may simultaneously act as the server. In this scenario multiple control nodes such as the first and second control nodes are allowed to act as the server simultaneously. How to deal with this is further described below in action and .

In some embodiments the first control node sends an identifier associated with the communication channel to the subscription managing node . In this manner the communication channel is established. As mentioned above the communication channel is dedicated for use of the Distributed Shared Memory.

The first control node may send a request for identifications of control nodes to the subscription managing node . In this manner the first control node obtains information about which control nodes are available to choose from when performing action .

According to some embodiments the first control node receives a set of identifications of control nodes from the subscription managing node . This action may be performed in response to the request sent in action .

The first control node obtains a first indication relating to a ranking of a suitability of the first control node to act as the server. In this manner the first control node is made aware of the first indication which will be used in action . The first indication will be described in more detail below.

The first indication may be obtained by that the first control node receives the first indication relating to ranking of the first control node from the subscription managing node .

Alternatively or additionally the first indication may be obtained by that the first control node obtains the first indication from a memory comprised in the first control node .

The first control node may send the first indication relating to ranking of the first control node as the server to the subscription managing node . The subscription managing node may forward the first indication to the second and or third control nodes which subscribes to the identifier mentioned in conjunction with .

The first control node receives over the communication channel a second indication from the second control node . The second indication is received via the subscription managing node . The second indication relates to a ranking of a suitability of the second control node to act as the server. In this manner the first control node is made aware of the second indication relating to ranking of the second control node . The second indication will be described below.

As mentioned above after this action and action above have been performed the first control node may compare the first and second indications in order to select which of the first and second control nodes to act as the server.

At this stage the first control node is aware of the first and second indications. Thus the first control node selects based on the first and second indications one of the first and second control node to act as the server for managing the master representation of the distributed shared memory being accessible within the overlay network . In this manner the most suitable node of the first and second control nodes may be selected to act as the server given the information provided by the first and second indications.

In some embodiments the first control node is selected to act as the server when one or more of the following conditions are fulfilled 

As a first example the first indication comprises the first start time and the second indication comprises the second start time. In this example the first control node receives indications such as the first and second start time.

The first control node may then calculate the first and second ranking values based on the first and second start time. Next the first control node is able to check if the condition that the first ranking value is greater than the second ranking value is fulfilled when selecting the first control node i.e. itself to act as the server.

Alternatively or even additionally the first control node may check if the condition that the first start time is before the second start time is fulfilled when selecting itself to act as the server. Hence the first control node checks the appropriate condition without calculating the first and second ranking values.

As a second example the first indication comprises the first ranking value and the second indication comprises the second ranking value. In this example the first control node receives indications such as the first and second ranking values.

The first control node may then directly check if the condition that the first ranking value is greater than the second ranking value is fulfilled when selecting itself to act as the server. By checking the condition directly it is meant that no calculation of the first and second ranking values are required as in one alternative of the first example directly above.

This action may be performed when the second control node acts as a further server for managing a further master representation of the distributed shared memory. Thus in this action multiple servers exist. For example the second control node may have performed an action similar to action . Thereby the second control node acts as the further server.

After the selecting of the first or second control node in action the first control node may merge the master representation and the further master representation. One of way to merge the data is to calculate a patch and then apply the patch on the other replica. A patch can for example be calculated using Meyers Diff algorithm. See http neil.fraser.name software diff match patch myers.pdf.

Since the first control node was selected to act as the server in action the first control node may act as the server for the merged master representation. The second control node is then configured to act as a client to the server.

Contrary to the scenario in action the second control node is the server or acts as the server in this scenario. As mentioned above the overlay network further comprises the third control node .

The first control node may detect lack of response or lack of responsiveness from the server. The server such as the second control node may have lost its connection to the subscription manager due overload or any other reason. In action and it is described how the first control node handles the detected lack of response or responsiveness.

The first control node may receive a third indication relating to ranking of the third control node from the third control node via the subscription managing node . The reception of the third indication may occur in response to that the first control node sends a request for indications to the subscription managing node .

The third control node has sent the identifier to the subscription managing node . As a result the third control node is hooked into the communication channel. In this manner the third control node may exchange information via the subscription managing node with the first and or second control node .

In some embodiments the first control node selects the first or third control node to act as the server based on the first and third indication. Similarly to action the first control node may select the most suitable node out of the first and third control nodes to act as the server for managing the DSM. Hence if a server crashes actions provides means for automatic recovery. In this manner most or all of the DSM may be reconstructed. Thereby loss of information is avoided.

The first indication relating to ranking may be indicative of probability that the first control node remains accessible within the overlay network . Furthermore the first indication relating to ranking may comprise information about one or more of 

The third indication relating to ranking may comprise information about parameters corresponding to those listed above for the first and second indication.

An advantage is that it is be possible to implement a user centric device cloud where server functionality may move around between different devices and do not need to reside on a continuously running server node. The clients do not need to know the address to any server. Instead the clients share the identifier which may be a common key.

In the overlay network is exemplified and further details of the nodes are shown. The first control node executes a first web browser client and the second control node executes a second web browser client . Each of the first and second web browser clients provides a runtime environment for JavaScript. When the first web browser client downloads a web page comprising JavaScript for activation of a web collaborative service utilizing DSM a first controller is executed within the runtime environment of the first web browser client . Similarly a second controller is executed within the second web browser client .

In other examples the web browser clients may be replaced by any clients providing runtime environments such as virtual machines executed in the control nodes. The control nodes may be provided with any known operation system such Windows iOS Android Unix or Java.

The first controller may manage a server within the first controller . In addition the first controller may manage a replica own by the first controller . Depending on whether the server or the replica is activated within the first controller the controller may act as either a server or a client within the overlay network . Similarly the second controller may manage a server or a replica within the second controller .

Moreover shows a dedicated server node providing a runtime environment for a third controller . Since the third controller is designated to act as a server only the third controller comprises no replica but a server for managing a master representation of the DSM. In all other aspects the third controller behaves in the same manner as the first and second controller .

When the first second and third controllers exchange information for being able to select which node to act as the server the publish subscribe service is utilized. See dashed arrows.

However when each of the first second and third controllers acts as servers or clients respectively the communication between the controllers is independent of the publish subscribe service. Instead the overlay network provides client to server communication. Hence the first second and third controllers are only dependent on the subscription managing node when selection of which controller to act as the server is performed. This is indicated by solid arrows.

With reference to a schematic signalling scheme of an exemplifying method for finding and selecting a controller to act as a server is shown. In this example the controller is a software module running within a runtime environment of for example a web browser. The web browser may be executed by the first control node . In other examples the web browser may be executed by the second or third control node . In the example described below the controller may be the first controller . In other examples the controller may be the second controller .

Moreover a publish subscribe module is shown. As an example the publish subscribe module is executed on a dedicated server not shown . See for example in .

In this example the following actions are performed. The actions may be performed in any suitable order.

The controller starts by creating a server resource. The server resource is simply an address in the overlay network hosted by the controller that at this point in time does not have any DSM master associated with it. This makes the server resource simple and fast to create and host. If it is asked by any client such as another controller it will on demand create a DSM master as a sub resource of the root server resource.

As soon as the controller has created the server resource it can notify the framework that it is setup and ready to be used.

At this point replicas with relative addresses may be created and the controller will direct the replicas to the server resource that is the best at this time.

Another possibility is that the controller waits for some time before it notifies the framework in order to also receive answers from others controllers and thus having a better understanding of what server resource would be the best to start with.

When the server resource is created or while the server resource is being created the controller also sends a subscribe message to the Publish Subscribe service to register for publications. Each controller registers to receive publications for a specific identifier and thus only other controllers subscribing to that identifier will receive publications. A controller can in this way publish e.g. send messages to all other controllers subscribing to that same identifier. This action corresponds to action of .

Once the subscription is set up the controller publishes a find servers message to all other controllers asking them for a list of all servers known to them. Since it is subscribing to the publications for this same identifier it will also receive its own message. This action corresponds to action of .

If there are other controllers subscribing to the same identifier they will receive the find servers message and will in response thereto publish information about servers known to them. Hence the controller may receiver a find servers response message. This action corresponds to action of .

In the simplest case however there are no other controllers subscribing to the same identifier and no other server resources will be known.

The controller may also send a publish server message comprising information about server resources it is aware of. At this point in time it is only its own server resource it is aware of. This action corresponds to action of .

The controller receives a publish servers notification message. This action corresponds to action of .

As described above the controller is subscribing and publishing to a service that will broadcast all messages sent by the controller to all other controllers subscribing to the service. It will also set up and publish information about a server resource that it is responsible for.

Once the controller has set up the subscription it will choose or select one of the controllers to act as the server. It is then possible to create replicas in the context of the controller and the controller acts as a proxy between the replica and the DSM master replica.

Moreover the controller may change which controller acts as the server if a better server candidate i.e. another controller which is more suitable to act as server than the current one is discovered. For example if a server with higher rank is discovered at any time the data will be migrated to this server without the user noticing it.

Moving data from one server to another is as simple as creating a controller with higher rank. The merge to the new server is then handled by the controllers.

With reference to a schematic block diagram of the first control node being configured to select the first control node or the second control node to act as a server is shown. The first control node is configured to perform the methods in and or .

As mentioned the first and second control nodes are configured to be comprised in an overlay network . The overlay network is configured to be overlaid onto an IP network and is further configured to comprise a subscription managing node . The subscription managing node is configured to provide a communication channel of the overlay network between the first and second control nodes .

The first control node comprises a processing circuit configured to obtain a first indication relating to a ranking of a suitability of the first control node to act as the server. The processing circuit is further configured to select based on the first and second indications one of the first and second control nodes to act as the server for managing a master representation of a distributed shared memory being accessible within the overlay network .

In some embodiments the overlay network is further configured to comprise a third control node and the second control node is selected to act as the server. In these embodiments the processing circuit further is configured to detect lack of response from the server receive a third indication relating to ranking of the third control node from the third control node via the subscription managing node . The third control node has sent the identifier to the subscription managing node . The processing circuit is further configured to select the first or third control node to act as the server based on the first and third indication.

In some embodiments the first control node is selected to act as the server when one or more of the following conditions are fulfilled 

The processing circuit may further be configured to obtain the first indication from a memory comprised in the first control node .

The processing circuit may be a processing unit a processor an application specific integrated circuit ASIC a field programmable gate array FPGA or the like. As an example a processor an ASIC an FPGA or the like may comprise one or more processor kernels.

The first control node further comprises a receiver configured to receive over the communication channel a second indication from the second control node via the subscription managing node . The second indication relates to a ranking of a suitability of the second control node to act as the server.

The receiver may further be configured to receive a set of identifications of control nodes from the subscription managing node .

The receiver may further be configured to receive the first indication relating to ranking of the first control node from the subscription managing node .

The first control node further comprises a transmitter configured to send an identifier associated with the communication channel to the subscription managing node . In this manner the communication channel is established. The communication channel is dedicated for use of the distributed shared memory.

The transmitter is further configured to send a request for identifications of control nodes to the subscription managing node .

The transmitter is further configured to send the first indication relating to ranking of the first control node as server host to the subscription managing node .

The first control node further comprises a memory which according to some embodiments is configured to store software to be executed by for example the processing circuit. The software may comprise instructions to enable the processing circuit to perform the method in the first control node as described above in conjunction with and or . The memory may be a hard disk a magnetic storage medium a portable computer diskette or disc flash memory random access memory RAM or the like. Furthermore the memory may be an internal register memory of a processor.

Even though embodiments of the various aspects have been described many different alterations modifications and the like thereof will become apparent for those skilled in the art. The described embodiments are therefore not intended to limit the scope of the present disclosure.

