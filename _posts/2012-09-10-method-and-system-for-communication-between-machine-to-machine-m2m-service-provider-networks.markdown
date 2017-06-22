---

title: Method and system for communication between machine to machine M2M service provider networks
abstract: Machine-to-Machine (M2M) communication has been described for communication in a single network in among others publications from the European Telecommunications Standards Institute (ETSI). The publications describe a single network with defined entities, a resource structure and protocols. According to the invention, a solution is described for communication between entities residing in different M2M networks. Entities residing in a first M2M network requiring information of an entity in another second M2M network submit a request with a target ID pointing to the entity in the second M2M network. The request is forwarded to the network node of the first network. The network node of the first network checks whether the target ID matches with an announced resource in the network node of the first network. On a match the request is routed towards the network node of the second M2M network according to an address available in a REstful structure comprising the announced resource. The network node of the second network routes the request further towards the second entity. On reception of the request the second entity processes the request and returns a reply via the path created by the previous steps.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09439026&OS=09439026&RS=09439026
owner: Telefonaktiebolaget LM Ericsson (publ)
number: 09439026
owner_city: Stockholm
owner_country: SE
publication_date: 20120910
---
The present invention relates generally to enablement of a communication network comprising devices that communicate without human intervention. More particularly the present invention facilitates a method and system for initialising communication in a Machine to Machine M2M environment in an efficient way.

As network availability in devices spreads and network access coverage increases there is an increasing demand to create a network of connected things or devices. Where the first drive of the telecommunications industry was to connect locations to each other and ask users to travel to one of the connected locations and the second drive of the industry was creating mobile connections so that people could be connected regardless of locations a third phase of connectivity is being entered. In this third phase there is an interconnection of devices.

Whether these devices are mobile such as actuators in transportation systems or fixed in locations such as sensors on a utility meter devices are being connected to each other and to network applications or services.

However a problem is foreseen in that as the number of devices will increase the problem of managing these devices will also grow. Furthermore the manner in which the devices are connected to a network can affect how they are managed and communicate.

As among one of the recognized authorities on standardization of communication technology the European Telecommunications Standards Institute ETSI has taken the initiative to develop standards to support industry for enabling ease of connectivity between the devices i.e. sensors and actuators as well as applications and services.

By means of standards innovation across industry is facilitated enabling exposure of data and information as well of provision of services.

ETSI has defined a standard for machine to machine ETSI M2M communication where devices communicate and exchange information via a defined structure of database like resources. The standard is described in a.o. the following documents 

TS 102 690 Functional Architecture. The architecture which entities are required as to deploy device communication and management in an M2M network.

TS 102 921 mIa dIa and mId interfaces. The document provides the protocol specification for the three reference points mIa dIa and mId.

The ETSI M2M suite comprising the standards listed above provides a Machine to Machine M2M architecture with a generic set of capabilities for M2M services and provides a framework for developing services independently of the underlying network.

The ETSI M2M suite is generally based on a number of defined physical entities and a number of defined resources. The resources comprise information to be shared or exchanged and are organised in so called Service Capability Layers SCLs according to a REpresentational State Transfer RESTful architecture style.

The RESTful architecture style generally applied by ETSI M2M represents a tree wherein the SCL maintains a resource structure where the information to be shared or exchanged is stored and updated.

Communication to and from the resources comprised by the SCLs is defined by procedures over dedicated interfaces called reference points .

The entities forming a network are organised in a pyramid like structure where multiple devices sensors and actuators form the basis and a Network node network domain server comprising a Network Service Capability Layer NSCL forms the top of the pyramid.

The device might be a very simple device such as a contact switch sensor only able to provide on off data or an actuator such as a relay to turn on or off a heating element. On the other extreme a device can be a complex remote sensor with a local application that provides compressed and encrypted strings of data on e.g. received radiation units on request.

ETSI M2M has defined the concepts of an M2M application and an M2M Service Capability Layer SCL being processing units comprised by physical entities. The application has to register over a defined reference point with an SCL. The SCL to be registered with called the local SCL in ETSI M2M terms is either the SCL locally available in the same entity where the application resides or if not locally available in the first higher SCL in the pyramid.

The SCL enables an application to use the M2M communication suite. The ETSI M2M SCL can generally be seen as a database having a defined record structure using defined interfaces the reference points for communication with other SCLs and Applications and is arranged to perform functions such as relaying information to other SCLs store and forward functionality expiration time handling policy enforcement etc.

ETSI M2M had defined until now a number of different entities a Device D and D also known as D prime a Gateway G and a Network node N . The D entity comprises an Application only. The D G and N entities comprise an SCL an may further comprise an Application.

The G entity has been introduced to connect D entities in a local area level. The G entity enables M2M communication to other entities in the M2M network by means of its SCL.

Multiple G entities comprising Gateway SCLs GSCLs and optionally Gateway Applications GAs could be connected to an N entity such that a pyramid like structure is formed.

In this way a Network Application NA comprised by the N entity can communicate with or control the connected D and G entites.

ETSI M2M indicates that an address of a resource representing Device Application e.g. with identifier DA registered with the SCL of an NSCL e.g. with identifier NSCL has the identifier 

The pyramid like topological structure of the entity which hosts DA is not represented in this identifier. The sequence is independent from underlaying physical networks.

Device applications are generally understood as applications that in case of a sensor retrieve the data of the sensor and store or update in M2M terms the data into the resource of the one or more SCLs where the application has been registered to. In case of an actuator the application may e.g. read the resource of the SCL where the application has been registered with or reacts on a notification message and controls the actuator according to the value indicated in the resource read or notification received respectively.

Gateway and Network applications are understood as applications that process data received from Device Applications and submit requests to Device Applications to be executed.

There is a substantial demand to connect numerous devices which may connect via fixed and cellular data networks as well as wireless network interface such as WiFi IEEE 802.11 .

However not all devices can be expected to reside in a single network operated by a single M2M provider just as in the ETSI M2M standards listed above is presented.

A problem is raised in how devices can initialise and establish communication when different M2M networks are maintained by different M2M service providers having no D entities connected via the same G or N entities.

As an example of the problem stated a solution is required for a situation where an entity in a first M2M Service provider network has to retrieve information that is stored in a resource residing in one or more entities of a second M2M Service Provider network.

It is an object of the present invention to provide a method and system to enable communication between Machine to Machine M2M devices applications or services that do not belong to the same network M2M network.

A solution is presented below for allowing devices attached to a specific M2M Service Provider network to utilize service and communicate to devices from other M2M networks belonging to one or more other M2M Service Providers.

The invention is explained in an example according to a REpresentational State Transfer RESTful architecture style applied by the European Telecommunications Standards Institute ETSI for M2M communication.

The solution to the problem is discussed as a method where a first entity being an application or an entity residing in a first network needs to communicate e.g. retrieve or exchange information with a second entity residing a second different network.

Both networks are M2M networks having a topologically pyramid like structure with a single network node on top of the network. Each of the M2M networks comprise the network node and one or more entities and applications which are communicatively connected to eachother according to the topologically pyramid like structure.

The entities that support the communication comprise resources for exchanging information are arranged in a tree like structure.

All communication between both networks has to pass the network nodes of the M2M networks each having a link to the other network node.

Each resource has a determined location in the tree like structure and a determined meaning in the entity thereby enabling addressing.

Further as a condition which took already place before the solution is applied registration within the M2M networks was performed.

The applications and entities within each network have to register to each other in an upward direction in the pyramid like structure until the network node on the top has received registrations of the applications and entities risiding directly one step below under the network node. The remaining applications and entities in the M2M network that are not registered with the network node are registered with their superior entity.

When the first entity or application transmits a request addressed for the second entity in the direction of a first network node of the first network this first network node receives the request comprising an identifier identifying the addressed second entity.

The first network node checks its resources for a matching reference where this reference is stored in a resource of the first network node with the identified addressed of the second entity from the request.

When the first network node has found a match the first network node retrieves the network node of a second network indicated as the network node from which the request to the resource comprising the matched reference was received.

The first network node forwards the request to the retrieved second network node which subsequently forwards the request to the second entity.

The second entity receiving the request processes the request and responds to the first entity via a path created by the previous steps.

The first network node in the first M2M network as defined above with the pyramid like topology having resources for exchanging information arranged in a tree like structure receives a request from an application or entity in a first network where the request comprises an identifier identifying an addressed second entity of a second network wherein the second entity is not registered to the first network node.

The first network node checks its resources for a matching reference where the reference is comprised by the first network node s resources with the identified addressed second entity.

On a match the first network node subsequently routes the request to a network node of the second network indicated as the network node from which the request to the resource comprising the matched reference was received.

The first network node routes the request according to routing information stored in the resource of the first network node representing a registration from the second network node.

The term resource should generally be understood as one or more memory locations in an SCL enabled for being read and updated according to the setting of attributes defining which entity may read or update.

The elucidation for the method claims does also apply for the corresponding embodiment of the listed methods to the system entities as claimed.

The method node and system presented has the advantage of re using the concept of announcement for spreading the knowledge of remote resources.

These and other embodiments according to the present invention are now illustrated in more detail with reference to the enclosed drawings.

Without restrictions to the scope of the invention in order to provide a thorough understanding of the present invention the invention is presented against the background and within the scope of the current published standards suite of the European Telecommunications Standards Institute ETSI regarding Machine to Machine M2M communication referred here as ETSI M2M.

However the present invention may be applied in any context of a device to device or M2M communication deploying a RESTfull style architecture deployed in networks having a pyramid like topology. Apart from the ETSI M2M initiative the proposed solution can be applicable to the one M2M initiative or the M2M or Internet of things initiative by the Telecommunications Industry Association s TIA .

The architecture defined by ETSI M2M assumes that physical entities such as Devices Gateway and Network node belong to a single M2M service provider.

Applications and the Service Layer Capabilities DSCL GSCL and NSCL belong to a single M2M Service Provider. The ETSI M2M standard specification does not describe how an application or an SCL belonging to the M2M Service Provider can obtain information produced by an application or SCL that riside on a second different M2M Service Provider serving a different M2M network.

Reference point dIa and refers to the interface between a Device or Gateway Application DA GA and an SCL.

It should be regarded that Physical entities e.g. might comprise applications and or SCLs for other M2M providers.

For the explanation of the invention it is regarded that entities only comprise applications and or SCLs of one M2M service provider.

As to indicate in which network a certain entity Application or SCL according to resides the reference sign indicating the physical entity application or SCL for the remainder of this description is expressed as XXX Y wherein XXX represents the physical entity application or SCL corresponding to and Y represents a network indicator where 1 represents a first network and 2 represents a second network as indicated in .

A first M2M network provider maintains network and a second M2M network provider maintains network . A connecting interface is depicted connecting bidirectionally both NSCLs and hosted by the network nodes and respectively comprised by both networks.

The Invention proposes an interface and method to have devices or applications from the first network be enabled to communicate with devices or applications of network .

The Invention is explained with an example problem of how to have the application hosted by entity have retrieve information that is stored in resources comprised by GSCL comprised by Gateway .

Before any communication can be established ETSI M2M requires registration procedures as to create a structure of resources for exchanging data. Resources can be created in procedures according to attributes defining which entity may perform which action.

For illustrative simplicity the identifiers identifying SCLs and Applications and strings used in requests apply the name of the SCL according to XSLCY and for applications XAY wherein 

The address of the application resource DA where the structure has been created is indicated by applications DA .

The address of the scls resource DSCL where the structure has been created is indicated by scls DSCL .

The registration procedures at the second network provide equivalent results in the scls resources of the GSCL and NSCL . The addresses of the resources where the structures have been created in the GSCL and NSCL respectively are indicated by applications D A and scls GSCL . In ETSI M2M the SCL structure of a DSCL is equivalent to an SCL of a GSCL. As such the SCL structure of DSCL is equivalent to GSCL .

In both networks and registration procedures take place in principle without mutual interference to eachother. illustrates the registration sequence of the Device application via the dIa reference point .

The result of the procedures shown are the creation of the resource . . . applications DA in DSCL and the resource . . . scls DSCL in NSCL .

The result of the sequences as exploited in are presented in showing the created application and scls resource structures in the DSCL as well as in the scls resource of the NSCL showed in .

The registration sequences at the second network indicated by reference signs until map mutatis mutandis to the signal flow reference signs until .

The result of the procedures at the second provider s network are the resource . . . applications D A in GSCL and the resource . . . scls GSCL in NSCL 

Registration in ETSI M2M is by definition a registration to the local SCL. The address of the SCL is obtained either during a bootstrap procedure or being provisioned. The local SCL is to be understood as the SCL first met in the topological pyramid in the direction to the top of the pyramid.

Note that the other entities D A GSCL NA DA DSCL and NA in will also perform a registration procedure but the steps are not described since they are not relevant to the specific example. Also note that the steps above can independently of eachother.

As part of the application registration procedure the SCL where the resource is created also designated as local or hosting SCL will provide the Universal Resource Locator URI of the resources created.

The URI provided by the hosting SCL does not need to be public the SCL might provide a private URI which is only valid in the device domain M2M network or in the local area network of the gateway. The applications may just register locally to a DSCL or GSCL but the DSCL or GSCL is not registered to an NSCL yet.

DA and DSCL are not known in the M2M network of second M2M service provider of M2M network . Known methods to retrieve knowledge of their existence can only be obtained by so called out of band method meaning that other communication means e.g. like Short Message Service SMS e mail etc should be used.

Without the use of out of band methods DA and DSCL are not reachable from entities applications within the second M2M Service Provider s M2M network . The same hold for D A and GSCL for communication from within the first provider s network .

As to accomplish a communication between SCLs and or applications in ETSI M2M networks the following request routing rules are to be performed regarding requests generated by an application and requests received by an SCL 

Additional to these five rules listed above the rule stated below is suggested as to enable inter network announcing of SCLs and Applications.

The term announcing is to be understood as the creation of an announced resource in another SCL as where the original resource is created currently for the ease discovery resources.

The resources that can be announced have an announceTo attribute describing in which SCLs announced resources may be created. As an example if in a resource is created with the attribute announceTo GSCLA then in the resource scls NSCLX scls an announced resource referring to NSCLX is created as well.

The M2M inter service initialisation uses the announced resources to also make the remote resources both discoverable and reachable from the announcedTo SCL. Resources in the NSCL of the M2M network of the second M2M service provider are reachable if the NSCL in that M2M network registered with the NSCL in the M2M service provider M2M network. Resources in other SCLs residing in the M2M network of the second M2M service provider serving M2M network are now routable from M2M network of the first M2M service provider when announced in the M2M network of the first M2M service provider serving M2M network .

When an NSCL in M2M network needs to reach NSCL in M2M network it needs to perform a mutual registration procedure which can be executed by 

a Provision of the network i.e. statically the NSCL in M2M network registers with the NSCLs in all the M2M networks with which the first M2M service provider serving M2M network has an agreement. All the information for mutual registration addresses keys ids etc. can be preprovisioned or

b An on demand registration scenario when a request is received i.e. demanding that when an NSCL receives a request not targeting local resources or subordinate resources of local resources and for which there is no registered or announced resource as described in the routing rules listed above then the NSCL shall perform a DNS lookup on the Fully Qualified Domain Name FQDN in the targetID. The DNS lookup will have to give the address of the NSCL as resources in M2M network behind the remote NSCL are not supposed to be available as A or AAAA records in DNS. On demand can be applied as a first time that an address of an SCL or application residing in M2M network is requested or on demand basis.

Mutual authentication of the two endpoints NSCL and NSCL is required for secure authenticated connectivity.

In order for the registration to be mutual as a result of the registration procedure started by NSCL the NSCL will create a correspondent resource scls NSCL. This part of the procedure differs from the SCL registration procedure for a DSCL or GSCL registration the registering SCL NSCL does not create by itself a resource representing the registeringTo SCL NSCL but NSCL expects NSCL to register in response to the registration request of NSCL.

The order of NSCL initiating followed by NSCL as depicted in may as well be in the other sequence having NSCL initiating.

As to handle announcements to another M2M network current announcement procedures shall be enhanced. Specifically 

When a request is received in NSCL that is targeting where the announced resource exists in scls NSCL scls GSCL annc as shown. Since the link attribute in GSCL annc matches the request is forwarded to the entity representing NSCL. I.e. to based on the routing information associated with NSCL i.e. the m2mPoc information associated with NSCL .

It is suggested to indicate this announced resource by which can occur 0 or 1 time in an scls resource.

Introduced resource shall represent an active announcement of an SCL in another SCL that is not its registered to SCL or the SCL it registered from. The resource keeps a link to the original resource. That will also be the reference returned during discovery.

The resources contains sub resources for applications scls containers groups and accessRights collection resources. This allow the creation of these types of resources container group accessRight with a lifetime and scope that are linked to the announced resource. Resources created as descendants of the announced resource will automatically be deleted when the scl is de announced or when the announcement expires.

It shall be the responsibility of the announcing SCL to keep the accessRightID and the searchStrings in sync with the resource that is announced.

In the example of DA requesting to receive data from GSCL which has been sourced by Device D A NSCL comprises an announced resource scls NSCL scls GSCL annc applications D Aannc that represents in its resource collection the link to the original resource representing D A.

The ETSI M2M resource has been added with an attribute resource named announceTo with a multiplicity of 0 or 1.

The resource as defined in ETSI M2M TS 102 690 shall be extended with resources scls and applications as shown in table 1 below.

Please note that the schematic flow of shows a synchronous handling of the request. However in practice the SCLs may do the announce procedure in an asynchronous way first responding on the xxxUpdateRequestIndication message and then initiating the createxxxAcnncRequestIndication message where xxx denotes either application or scl depending whether an application or an SCL has to be announced.

Just as that GSCL can be announced in NSCL an application D A can as well announce. If DA only has knowledge of the identifier identifying D A so not knowing at which GSCL D A is registered a request to application D A can routed based on an announced resource in NSCL by the same method explaned above for GSCL. explaines how an application may announce in NSCL.

Application entity is communicatively connected to NSCL via interface reference point mIa . Application and NSCL can be housed in one node or housed in separate co located nodes albeit connected via interface mIa .

Network node is communicatively connected to its environment via interface mId typically to SCLs of other network entities within the same M2M network domain and mIn typically communicatively connected to one or more NSCLs.

As Devices and Gateways constitute generally the same structure these entities are explained in a single figure pointing out differences in the text below.

Optionally DSCL and GSCL entities further comprise a Device application and a Gateway application respectively the

Application and are communicatively connected to DSCL and GSCL respectively via interface reference point mIa and respectively. Application and DSCL GSCL can be housed in one node or housed in separate co located nodes albeit connected via interfaces mIa and respectively.

DSCL and GSCL are communicatively connected to the environment via interface mId typically to SCLs of other network entities within the same M2M network domain.

Difference between a Gateway and a Device node is that a Device node does not have to have an local SCL. Device node see is an example of a device with an application but without local SCL using the GSLC of a communicatively connected gateway node via interface or reference point dIa .

The solution as discussed has a number of conceivable advantages. The invention enabling M2M interservice communication and defining a new procedure for a mutual registration between NSCLs from different M2M Service Provider domains has the following advantages 

