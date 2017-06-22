---

title: Method for calculating paths, method for obtaining paths as well as terminal for same
abstract: The present invention relates to a method for calculating trip paths determined by a departure point and a target point by using traffic information in a terminal. The method includes the steps of: requesting traffic information related to a trip from a server; receiving the traffic information related to the trip from the server; and calculating the paths by using the received traffic information, wherein the received traffic information includes traffic events corresponding to information on disturbances in the traffic flow in an area or the path related to the trip, and performance parameters corresponding to information on traffic flow in a road segment within a constant radius from the departure point, and wherein the performance parameters can be received from the server in the case where there is congestion heavier than a predetermined level within a constant radius from the departure point.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09638541&OS=09638541&RS=09638541
owner: LG ELECTRONICS INC.
number: 09638541
owner_city: Seoul
owner_country: KR
publication_date: 20121015
---
This non provisional application is a National Stage entry under U.S.C. 371 of International Application No. PCT KR2012 008366 filed on Oct. 15 2012 which claims the benefit of U.S. Provisional Application No. 61 577 079 filed on Dec. 18 2011 61 577 614 filed on Dec. 19 2011 61 599 943 filed on Feb. 17 2012 61 620 992 filed on Apr. 6 2012 61 623 577 filed on Apr. 13 2012. The entire contents of all of the above applications are hereby incorporated by reference.

The present invention relates to a method for calculating a route in a terminal a method for acquiring a route in a terminal or a terminal for the same and more particularly to a method for calculating a route using information received from a server or a terminal for the same and a method for acquiring a calculated route from a server or a terminal for the same.

Conventionally a navigation terminal detects its current location that is an origin of a trip through a Global Positioning System GPS connection receives information about a destination of the trip from a user and internally calculates a route based on the origin and the destination. Along with the recent proliferation and increased performance of smartphones services have become popular in which a traffic and route information providing server provides route information real time traffic information related to routes and other various information to Personal Navigation Devices PNDs over a mobile communication network.

Particularly in the situation where various navigation services are available the Open Mobile Alliance OMA standardization organization is working on standardization of Dynamic Navigation Enabler DynNav that provides real time traffic information by Peer to Peer P2P communication through an Internet Protocol IP based network of a mobile communication network or a wireless network rather than Traffic Protocol Expert Group TPEG information is transmitted over a Digital Multimedia Broadcasting DMB network that provides information in a broadcast signal. The standard considers a navigation terminal and a service type largely in two ways for a smartphone.

First a traffic and route information providing server performs complex route computation instead of a navigation application loaded in a smartphone and indicates a calculated route to the smartphone. Second owing to the improved performance of a smartphone an application loaded in the smartphone performs or a navigation terminal equipped with a mobile communication modem performs route computation. In this case the traffic and route information providing server does not provide route information. Rather once the terminal registers a calculated route to the server the terminal can receive from the server only real time traffic information related to the registered route in a customized manner by IP based P2P communication not in a conventional broadcast signal.

DynNav under standardization in the OMA LOC WG belongs to the type that provides IP based traffic information specifically by P2P communication. The following two types of NDs are defined in DynNav.

1. Smart ND a device that can calculate a route on its own and thus requests only real time traffic information to a DynNav server without receiving route information from the DynNav server.

2. Lightweight ND a device that cannot calculate a route on its own and thus requests all real time traffic information including route information to a DynNav server.

Since traffic information is requested and provided in a RESTful based manner in a conventional DynNav system the following route information formats are used and each information format can be defined by XML Schema Definition XSD .

1 Trip Structure a terminal initially acquires basic information such as an origin and a destination from a user for route setting and provides the acquired information to a server. The trip structure includes subsets corresponding to a plurality of route structures.

2 Route Structure a route structure is expressed as a plurality of segments as a way to represent total routes calculated using the trip structure.

3 Segment Structure it is a structure that represents each segment. The segment structure may define a real time traffic state corresponding to the segment as well as the length of the segment in TPEG.

1. The lightweight ND transmits trip information to the server for use in route calculation at the server.

2. The lightweight ND receives information about a set of routes including a recommended route calculated by the server from the server.

3. The lightweight ND subscribes to a notification service to receive real time traffic information from the server.

1. The user defines journey parameters and the application sends the parameters to the server the server calculates a set of proposed routes based on the received parameters with related traffic information. The server replies with the location of the created trip resource to the application.

a The server may reply with a representation of created trip resource which contains resources identifiers of the proposed routes. In this case message is no longer required.

2. The application uses the trip resource to access trip s information which contains resources identifiers of the proposed routes.

3. The application uses the Route Identifier to access information describing each single proposed route with links to traffic events and performance parameters.

4. The application accesses then to traffic events related to the route using links to traffic event resources provided in the route structure.

5. The user selects a route among the set of routes for which he is interested in receiving updated performance parameters and traffic events and alternative routes when available.

6. The application requests to the server to create a subscription to notification service for the trip and route s . The application is notified by the server of the following events 

7. Traffic events and or changes of performance parameters occur on the subscribed route s a notification resource is created.

8. The server delivers the notification resources to the application with links to modified resources including the trip and the route with the updated traffic information traffic events and performance parameters .

9. The application accesses the updated resources. The resources should be reflected in appropriate way.

10. The application request to modify the subscription setting adding notification for the new route. Just in case the updated resource is an alternative route in step 9.

2. The smart ND transmits information about the calculated route to the server and the server notifies the smart ND of a real time traffic state.

3. The smart ND subscribes to a notification service based on the transmitted route information in order to receive real time traffic information from the server.

1. The user defines journey parameters and the application sends parameters to the server. The server replies with the location of the created trip resources to the application.

a The server may replay with a representation of created trip resource. In this use case behaviors are equivalent.

2. The application uploads the calculated route under the resource tripId routes. The server replies with a representation of the route resource which contains performance parameters and links to traffic events.

a The server may reply with the traffic information performance parameters and traffic events . In this case an additional get operation is needed to retrieve content of resource.

4. Traffic events and or changes of performance parameters occur on the subscribed route s a notification resource is created.

5. The server delivers the notification resource to the application with links to the modified resources including the trip and the route with updated performance parameters and traffic information.

8. The application uploads the new calculated route under the resource tripId routes. The server replies with a representation of the route resources which contains route performances and links to vents. This step may be repeated many times until a route that satisfies performance constrains is found.

9. The application requests to modify the subscription setting adding notification for the newly subscribed route.

The lightweight ND and the smart ND in the conventional DynNav system as described with reference to suffer from some problems. These problems will be described below. Since the problems vary with the ND types lightweight or smart the problems will be described in relation to the individual ND types.

A When the Smart ND Calculates an Initial Route the Smart ND Cannot Apply Real Time Traffic Information.

A problem with the smart ND in the conventional technology is that the smart ND cannot use real time information appropriately in route calculation. The route calculated by the smart ND in step 2 of does not reflect real time traffic information at all. Since the smart ND cannot use real time traffic information as route information a high quality route guidance service cannot be provided to the user. Moreover an operation for tracking the route that does not reflect real time traffic information by the server subsequently to step 2 in which the smart ND transmits information about the calculated route to the server may be unnecessary.

Another problem that may be encountered with the smart ND is unnecessary consumption of network resources. As in step 8 of the ND transmits information about its calculated route a plurality of times in order to search for an optimal route. The above described operation for detecting an optimal route may be performed in various manners depending on methods and designs. When speaking of probability an optimal route may be detected by transmitting route information one or more times. Continuing a transmission operation with uncertain probability may lead to unnecessary consumption of network resources. From the perspective of the user using the ND this means excessive cost and a lengthened time for detection of an optimal route which may disturb safe traveling of the user.

In general information that the ND receives from the user is the location of a user intended destination. Without real time traffic information the terminal generally calculates a route in a shortest road first or express way first manner. As illustrated in since the smart ND does not reflect real time traffic information in calculating an initial route the smart ND calculates a shortest route running through S 4 A b D. However an actual optimal route is S 1 A a D in consideration of congestion roads marked in c denotes a congestion free road c denotes a normal congestion road and c denotes a severe congestion road . If the terminal travels in the corresponding route the user experiences congestion even from the start of the trip and then will pass through a road b under construction. This implies that in the case of severe traffic congestion within a reference radius of an origin as illustrated in there is a need for the server to provide corresponding traffic information.

This problem is common to both the lightweight ND and the smart ND. For simplicity of description the smart ND will be taken as an example. After calculating a route the smart ND transmits information about the calculated route to the server and the server continuously estimates the state of the route to provide a notification service for the route.

However the estimated overall route uploaded by the ND is effective only at the moment of the upload. Once a vehicle carrying the smart ND travels in the route for a certain distance estimation of the state of the route for the distance or delivery of information about the estimated route state to the smart ND is meaningless. That is in the case where the server does not know the current location of the serviced smart ND the server transmits unnecessary information to the smart ND. This means transmission of unnecessary information and the resulting power consumption on the part of the network and unnecessary resource consumption for the management of information transmission on the part of the server.

This problem occurs to the lightweight ND. When the server calculates routes based on real time traffic information and transmits information about the calculated routes to the lightweight ND the following operation is performed.

2. The server generates a plurality of routes based on the received origin and destination information.

3. The ND or its user subscribes to a traffic information notification service to select a route transmit information about the selected route and receive the traffic information notification service.

During the above procedure the server typically generates a plurality of routes and transmits information about the plurality of routes to the ND to increase the quality of a service experienced by the user and widen a selection range for the user. Then the ND or its user may select one of the plurality of routes. The problem herein is that the user should receive all of actually unnecessary route information and after selecting one of the routes the user deletes the remaining route information. As a consequence network resources may be wasted.

To overcome the problem encountered with steps 1 to 4 described above it has been proposed that only a summary of information about calculated routes is initially transmitted to an ND. In order to prevent network resource waste the server selectively transmits a part of the information about the calculated routes e.g. important segment information traveling times toll etc. to the ND. Then the ND or its user selects one of the calculated routes based on the received information i.e. a summary and or the user s preferences and notifies the server of the selected route. Thus the server transmits only full route information about the selected route from among the plurality of routes to the ND in response to the request.

Nonetheless the conventional technology still suffers from a problem. This problem occurs when the distance between an origin and a destination is short. If the distance between an origin and a destination is short the size of transmitted segment information is small. Thus a summarizing operation of the server to generate a summary of route information and interaction between the server and an ND may degrade the performance of a navigation system. In other words there is no need for transmitting summarized route information in this case. Rather it may be preferred to transmit full route information.

An object of the present invention devised to solve the conventional problem is to provide a method for when two types of services or terminal types are supported overcoming a problem encountered with a conventional service that is inefficiency of transmission of route information and real time traffic information.

In an aspect of the present invention a method for calculating a route for a trip identified by an origin and a destination using traffic information at a terminal includes requesting traffic information related to the trip to a server receiving the traffic information related to the trip from the server and calculating the route using the received traffic information. The received traffic information may include a traffic event corresponding to information on an obstacle to a traffic flow in an area or a route related to the origin and the destination and a performance parameter corresponding to information on a traffic flow in a road segment within a predetermined radius from the origin. The performance parameter may be received from the server if there is congestion at or above a predetermined level within the predetermined radius of the origin.

Preferably the traffic event may include an event comprising a road work or an accident related to the area or the route.

Preferably the performance parameter may include at least one of a speed congestion or a travel time of the road segment.

Preferably the requesting of the traffic information related to the trip may include requesting the traffic information to the server using boolean type data.

In another aspect of the present invention a terminal for calculating a route for a trip identified by an origin and a destination using traffic information received from a server includes a transceiver configured to communicate with the server and a processor configured to calculate the route using the traffic information received from the server. The processor may be configured to request traffic information related to the origin and the destination to the server control the transceiver to receive the traffic information related to the trip from the server and calculate the route using the received traffic information. The received traffic information may include a traffic event corresponding to information on an obstacle to a traffic flow in an area or a route related to the trip and a performance parameter corresponding to information on a traffic flow in a road segment within a predetermined radius from the origin of the trip. The performance parameter may be received from the server if there is congestion at or above a predetermined level within the predetermined radius of the origin.

Preferably the traffic event may include an event comprising a road work or an accident related to the area or the route.

Preferably the performance parameter may include at least one of a speed congestion and a travel time of the road segment.

Preferably the processor may be configured to request the traffic information to the server using boolean type data.

In another aspect of the present invention a method for acquiring a route for a trip identified by an origin and a destination from a server at a terminal includes requesting a set of routes for the trip calculated by the server to the server and receiving the requested set of routes from the server. The requested set of routes may be routes in a summarized format or routes in a full format.

Preferably the requested set of routes may be provided as the route in the summarized format or the route in the full format based on at least one of a length and complexity of the routes or quality of a network environment between the terminal and the server.

Preferably if the length and complexity of the routes are shorter and lower than a predetermined length and a predetermined complexity respectively and the quality of the network environment is better than a predetermined quality the routes in the full format may be received from the server.

Preferably the method may further include upon receipt of the routes in the summarized format for the requested set of routes from the server requesting a route in a full format for a route selected from the set of routes to the server.

In another aspect of the present invention a terminal for acquiring a route for a trip identified by an origin and a destination from a server includes a transceiver configured to communicate with the server and a processor configured to calculate the route using traffic information received from the server. The processor may be configured to request a set of routes for the trip calculated by the server to the server and control the transceiver to receive the requested set of routes from the server. The requested set of routes may be routes in a summarized format or routes in a full format.

Preferably the requested set of routes may be provided as the routes in the summarized format or the routes in the full format based on at least one of a length and complexity of the routes or quality of a network environment between the terminal and the server.

Preferably if the length and complexity of the routes are shorter and lower than a predetermined length and a predetermined complexity respectively and the quality of the network environment is better than a predetermined quality the routes in the full format may be received from the server.

Preferably upon receipt of the routes in the summarized format for the requested set of routes from the server the processor may be configured to request route in a full format about a route selected from the set of routes to the server.

The afore described aspects of the present invention are merely a part of preferred embodiments of the present invention. Those skilled in the art will derive and understand various embodiments reflecting the technical features of the present invention from the following detailed description of the present invention.

According to the embodiments of the present invention unnecessary data transmission between a navigation device or an application program and a server is reduced. Therefore the Quality of Experience QoE of a user can be increased.

Reference will now be made in detail to the preferred embodiments of the present invention with reference to the accompanying drawings. The detailed description which will be given below with reference to the accompanying drawings is intended to explain exemplary embodiments of the present invention rather than to show the only embodiments that can be implemented according to the invention. The following detailed description includes specific details in order to provide a thorough understanding of the present invention. However it will be apparent to those skilled in the art that the present invention may be practiced without such specific details.

In some instances known structures and devices are omitted or are shown in block diagram form focusing on important features of the structures and devices so as not to obscure the concept of the invention. The same reference numbers will be used throughout this specification to refer to the same or like parts.

An application is an implementation of a well defined but not standardized set of functions that perform work on behalf of a user. The application may include software and or hardware elements and associated user interfaces.

In general a server is an entity that provides resources to clients in response to requests in the technical field of the present invention.

In general a client is a device user agent or other entity that acts as a receiver of a service in the technical field of the present invention.

A DynNav application is an entity that is in charge of interacting with a DynNav server to get optimal route s real time and forecasted traffic information and complementary data. Therefore the DynNav application is loaded in a terminal such as a smartphone a mobile phone an ND etc. Accordingly the term DynNav application is interchangeably used with terminal. In this aspect the DynNav application is a kind of client.

A DynNav is an entity that is in charge of providing optimal route s real time and forecasted traffic information and complementary data to the application. In this aspect the DynNav server is a kind of server.

A lightweight ND is a navigation device that does not have a route calculation function requests a calculated route to a server and receives information about the calculated route from the server. The lightweight ND accesses the server for route estimation functionalities and for retrieving roads shape representation if not available in a local map database.

A location Uniform Resource Identifier URI is a URI that enables the current location of a device to be obtained from a particular location server using a particular dereferencing protocol.

An ND is an entity that assists a driver showing a correct route using a Global Navigation Satellite System GNSS service to reach a final destination. This entity may process real time and predicted traffic information and dynamically estimates the optimal route according to user preferences.

A POI describes information about locations such as name category unique identifier or civic address.

A segment is a unit into which a road is divided. For a general road a road running between intersections is a segment whereas for a highway a road is divided into segments according to a policy for the highway. Traffic congestion or a passing time may be determined on a segment basis. In the specification the term segment is interchangeably used with a road section.

A polyline is a continuous line used in graphic computing composed of one or more line segments defined by specifying the endpoints of each segment.

Route information is information about segment end points and complementary data from a defined origin and a destination.

A smart ND is a navigation device that is able to calculate a route s using a road network database available on the device itself.

Traffic information is information including traffic events and network performance parameters related to an area or a route. Further the traffic information may include current or upcoming that is future traffic information.

A traffic event is information about events related to an area or a route that are either imposed or planned by a road network operator i.e. road works leading to lane closures or events that occur outside the control of the road network operator i.e. accidents .

A network performance parameter is information regarding the performance i.e. speed delay and travel time of road segments related to an area or a route .

Route information in a full format is a type of route information including information about all segments from a origin to a destination. Unless specified otherwise route information is about a whole route.

Route information in a summarized format is a kind of route information including only information about segments selected for a summary of information from among all segments of a route between an origin and a destination how segments are to be selected is beyond the scope of the present invention .

The present invention relates to a navigation system method and apparatus for reflecting real time traffic information and more particularly to a navigation system method and apparatus for allowing a traffic information providing server to transmit real time traffic information to an ND using a minimal communication bandwidth when the ND is able to calculate a route on its own and has a modem connectable to a mobile communication network in a system for providing real time traffic information. The present invention relates to a navigation system method and apparatus for allowing a traffic information providing server to transmit information about an optimal route and real time traffic information to an ND even though the ND is not able to calculate a route on its own but is connectable to a mobile communication network.

Along with the recent proliferation of smartphones a navigation service of providing a travel route to a mobile communication terminal in a manner other than using a conventional Digital Multimedia Broadcasting DMB network is becoming popular. The OMA LOC WG calls this service Dynamic Navigation Enabler DynNav .

In the specification an ND refers to a device that can execute a route guidance function. The ND is any electronic device that can be carried like a smartphone a mobile phone a mobile device a laptop computer a tablet PC a smart pad etc. or that can be attached to a portable object.

For simplicity of description the traffic information and route information providing server or the DynNav server is referred to shortly as the server . The navigation device is referred to shortly as the ND. According to the capability of an ND the ND is referred to as the smart ND or lightweight ND .

In the present invention a terminal two terminal types are available as described before may be connected to a mobile communication network or an IP network such as a Wireless Fidelity Wi Fi network as illustrated in . A corresponding application may access the server receive route guidance data and real time traffic information and thus provide route guidance. While not shown a terminal capable of calculating a route on its own may selectively receive only real time traffic information without receiving route guidance data from the server.

The real time traffic information refers to optimal route information calculated and transmitted to the terminal by the server real time and forecasted traffic information and additional information related to traffic such as POI and weather. To avoid representational redundancy a navigation application or a terminal is collectively referred to as a terminal. Accordingly the terms terminal smart ND lightweight ND and navigation application may be referred to uniformly as terminal .

The afore mentioned real time traffic information may be represented in Transport Protocol Experts Group TPEG under consideration in the ISO standardization organization. TPEG is a standard protocol used to transmit traffic information and travel information over a digital broadcasting network. As illustrated in a TPEG layer stack corresponds to the network layer Layer 3 L3 to application layer Layer 7 L7 of the ISO OSI layer model. The network layer defines TPEG frame synchronization and routing. The packetization layer of Layers 4 5 6 L4 L5 and L6 combines components of applications into one stream. Each message format corresponds to the application layer L7. In DynNav real time traffic information may be provided to a terminal in a real time traffic information representation scheme of TPEG or any other representation scheme.

The terminal acquires trip structure information such as an origin and a destination from an initial navigation user. Before calculating a route based on the trip structure information the terminal transmits the trip structure information to the server and receives traffic information about related routes from the server. With reference to the operation of the terminal will be described below in greater detail.

A user of the terminal may input information about an origin and a destination to the terminal S . In general the origin information may be automatically detected and input through a Global Positioning System GPS receiver built in the terminal. The origin and the destination are elements that identify a trip. The terminal may transmit a traffic information request message including the input origin and destination information to the server S . That is the terminal may transmit the origin and destination information that identifies the trip and request traffic information a neighbor road traffic message about an area or route related to the origin and the destination to the server. Upon receipt of the request the server may determine whether traffic is heavily congested i.e. traffic congestion equal to or heavier than a predetermined level within a predetermined radius a of the origin S .

If traffic is heavily congested within the predetermined radius a of the origin in step S the server may transmit a performance parameter for a segment of the area or route within the radius to the terminal S . Otherwise the server may jump to step S. Then the server may determine whether a traffic event has occurred in the area or route between the origin and the destination S .

In the presence of a traffic event in the area or route between the origin and the destination in step S the server may transmit the traffic event to the terminal S . Otherwise the server may jump to step S skipping step S.

Upon receipt of traffic information related to the origin and the destination the terminal may calculate a route based on the received traffic information S .

In summary the server may transmit the traffic information related to the origin and the destination under the following conditions 

1 in the presence of heavy traffic congestion in an area near to the origin within a radius of am and

If condition 1 is satisfied the server transmits a performance parameter for the area near to the origin to the terminal. If condition 1 is not satisfied and a traffic event has occurred between the origin and the destination the server transmits the traffic event to the terminal. If none of conditions 1 and 2 are satisfied the server does not transmit any information to the terminal.

The order of steps S and S and the order of steps S and S may be exchanged in the flowchart of . Or the steps may be performed simultaneously. In other words while the time order of steps S through S illustrated in does not limit the scope of the present invention steps S through S should precede route calculation in step S. Since the terminal receives the traffic information before route calculation the terminal may calculate a route based on the received traffic information before route guidance. Thus the problem that real time traffic information is not reflected in calculating an initial route as described in A can be overcome. If real time traffic information is not reflected in calculating an initial route the terminal should transmit information about at least one route to the server until detecting a route satisfying a traffic flow constraint e.g. a travel time in a calculated route etc. . As described before route information is generally highly probable to be transmitted a plurality of times. In contrast if the terminal reflects real time traffic information in calculating an initial route the terminal may calculate an optimal route at one time and transmit information about the calculated optimal route to the server. Thus the necessary operation is completed just by one transmission.

The performance parameter included in the traffic information received for route calculation may be about an area or route within a predetermined radius of the origin of the trip not about a whole area or route. Since only a part of performance parameters occupying a larger amount of data than a traffic event related to the area or route within the same range is provided to the terminal the efficiency of network resources can be increased and a time taken for calculating a route at the terminal can be reduced. In addition since the terminal selectively receives only the performance parameter related to the vicinity of the origin and reflects the performance parameter in route calculation the terminal does not receive and reflect unnecessary performance information about an area beyond the vicinity of the origin which experiences a change along with the travel i.e. over time considering the nature of each segment experiencing a fluctuating change over time.

The terminal may create a trip description based on trip parameters defined by a user of the terminal that is information about an origin and a destination or other information using a POST command. The server may generate a trip corresponding to the trip description and transmit an Identifier ID of the trip and defined parameters to the terminal in response to the received trip description.

To request traffic information related to the trip identified by the origin and the destination the terminal may create an area description using a POST command. The server may reply with two types of traffic information for optimization of a bandwidth and an operation.

a In the presence of heavy traffic congestion in the vicinity of the origin the server may transmit a network performance parameter for the vicinity of the origin to the terminal. In other words the network performance parameter refers to information about the performance or traffic flow i.e. speed delay and travel time of segments forming an area or route in the specification. The performance parameter transmitted by the server in 2. POST create area description is for an area or route within a predetermined radius of the origin. In the presence of traffic congestion equal to or heavier than a predetermined level in the area or route within the predetermined radius the server may provide the performance parameter to the terminal.

The terminal may read the traffic information received from the server using a GET command. The terminal may use the traffic information in estimating or calculating a route for the defined trip trying to avoid important road segments affected by accidents road works or road congestion .

The terminal may upload the estimated route selected from among routes calculated by the terminal to the server using a POST command. The server may reply to the terminal with a representation of route resources including performance parameters and links to traffic events.

The terminal may subscribe to a notification service regarding the area selected in step 2 and the trip defined in step 3 using a POST command. The server may notify the terminal of performance parameters and new information about traffic events in regard to the selected area and all uploaded routes for the trip.

The terminal may periodically update its current location using a PUT command in order to amend an origin parameter of trip resources. This operation is triggered when a vehicle carrying the terminal moves for a predetermined distance from a previous reported position and the server may use this information to delete already traveled road segments from route s information.

If the server detects traffic events and or heavy traffic congestion along the proposed route the server may transmit updated traffic information about the current route to the terminal by transmitting a POST command to the address or URL CallBackNotifURL of the terminal.

The terminal may access the received updated traffic information traffic events and performance parameters related to the route using a GET command.

Depending on whether the terminal wants to maintain a previous route as valid the terminal may upload new calculated routes by generating or modifying an operation using a PUT command for the existing route or a POST command for route factory resources. The server may reply with a representation of route resources including performance parameters. This step may be repeated until a route satisfying traffic flow requirements is detected.

To release the notification service regarding resources using a DELTE command if a new route substitutes for an existing route by a modification operation in step 9 a deletion operation is not needed the terminal may delete a previous route that is not used any longer among a set of routes.

 Table 4 below illustrates a structure for representing an area description particularly in boolean type data tripAreaDesc . tripAreaDesc may indicate whether the server will provide traffic information to the terminal before the terminal calculates a route. Specifically this is opposite to definition of a user definition based area description during a service as is the case when a map of the terminal is changed by POI used in a general navigation service or the user of the terminal tripAreaDesc executes the POST command in 2. POST create area description . If tripAreaDesc is set to FALSE it is used when a user definition based area description is defined during a navigation service like the afore described POI case except for the reception time of traffic information before route calculation at the smart ND.

The specific condition is that a vehicle to which the terminal is attached or loaded has traveled for a predetermined distance in a calculated or determined route according to the characteristics of a navigation system. For example a condition that the terminal reports its location to the server every 2 km in a route may be imposed on the terminal.

The effects of the embodiment of the present disclosure may be described conceptually with reference to . define a procedure for receiving information based on the current location of an ND and summarizing server managed route information in the cases where the ND is a lightweight ND and a smart ND respectively.

The terminal may transmit information about an origin and a destination to the server S . A trip of the terminal or a vehicle carrying the terminal may be identified by the origin and destination information. The server may calculate a route based on the received information and transmit information about the calculated route to the terminal S . Upon receipt of the information about the calculated route the terminal may start a navigation service S . The terminal may determine whether the ongoing or serviced route is still to be covered S .

If the route is still to be covered in step S the terminal may determine whether the terminal has traveled for a predetermined distance a from the last location reported to the server S . On the other hand if the route has been completely covered which means that the navigation service is terminated the procedure end. If the terminal has traveled for the predetermined distance the terminal may transmit information about its current location to the server S . In this manner each time the terminal travels or runs for a predetermined distance in the ongoing or serviced route the terminal may report its location to the server in steps S and .

Upon receipt of the information about the current location of the terminal the server may determine whether the current location of the terminal is included in the ongoing or service route S . If determining that the current location of the terminal is included in the ongoing or service route in step S the server may delete the traveled route S . On the contrary if the server determines that the current location of the terminal is not included in the ongoing or service route in step S the server may recalculate a route using the destination information received in step S based on the current location S .

1 the current location of the terminal indicated to the server is included in a route segment managed by the server or

2 the current location of the terminal indicated to the server is not included in the route segment managed by the server.

If condition 1 is satisfied the server may delete the route managed traveled from the origin or the previous reported location to the current location determining that the terminal has traveled normally to the current location. Consequently transmission of unnecessary information traffic information about an already traveled route may be prevented during later notification of real time traffic information. If condition 2 is satisfied the server may recalculate a route based on the current location of the terminal determining that the terminal went off the route.

If the route is still to be covered in step S the terminal may determine whether the terminal has traveled for a predetermined distance a from the last location reported to the server S . On the other hand if the route has been completely covered which means that the navigation service is terminated the procedure ends. If the terminal has traveled for the predetermined distance in step S the terminal may transmit information about its current location to the server S . If the terminal has not traveled for the predetermined distance the procedure returns to step S.

In this manner each time the terminal travels or runs for a predetermined distance in the ongoing or serviced route the terminal may report its location to the server in steps S and .

Upon receipt of the information about the current location of the terminal the server may delete the traveled route S .

According to the above described methods illustrated in the current location of a terminal may be periodically updated and thus the range of traffic information needed to be provided to the terminal that is an area or route related to a trip is reduced. Therefore only traffic information that can be utilized in the terminal is provided to the terminal thereby saving the storage space of the server and conserving wireless transmission and reception resources.

The terminal may transmit information about an origin and a destination to the server S . The origin and destination information identifies a trip. The server may calculate a total route based on the received origin and destination information S . The server may compare the length of the total route with a threshold d S .

If the length of the total route is larger than the threshold d the server may compare a network reception environment of the terminal with a threshold q S . The network reception environment is related to the transmission rate of data that the server transmits to the terminal. The network reception environment may be called network quality. If the network reception environment is lower than the threshold q this means that the network reception environment is relatively poor. If the network reception environment is higher than the threshold q this means that the network reception environment is relatively good. When determining that the network reception environment of the terminal is lower than the threshold q the server may extract a route for a summary from the calculated total route S . Subsequently the server may transmit final route information i.e. route information in a full format or a summarized format to the terminal S .

When determining that the length of the total route is equal to or smaller than the threshold d the procedure may go to step S.

Steps S S and S may be performed for every route calculated by the server. In other words if the server calculates N routes based on the origin and destination information received from the terminal the server may extract N summarized routes for the N full routes in steps S S and S.

Then the terminal or its user may select one of a plurality of routes received from the server S . The route may be selected according to a subjective criterion user preferences an objective criterion e.g. a route length a travel time etc. or a combination of them.

If the route information transmitted by the server in step S is full route information S the procedure goes to step S. The terminal may perform a navigation service using the received full route information S .

In contrast if the route information transmitted by the server in step S is summarized route information S steps S and S are performed. The terminal may request full route information corresponding to the summarized route information to the server S and receive the requested full route information from the server S . Subsequently the terminal may perform the navigation service based on the full route information S .

In the embodiment of the present invention described with reference to the route information that the terminal receives from the server is one of two types i.e. summarized route information route information in a summarized format and full route information route information in a full format . As described before the conditions for determining one of the two types may include a route calculated by the server a trip length or the network reception environment of the terminal. Further the conditions may include the complexity of the route or the trip. The complexity of the route or the trip may be information including the number of roads roads identified by road numbers the number of road segments etc. included in the calculated route of the trip.

Accordingly the order of deciding the conditions described with reference to e.g. the length of the route is determined earlier than the reception environment of the terminal in is arbitrary. All conditions may be determined simultaneously or in an order other than the order illustrated in . For example if the length of a route is smaller than a threshold d the complexity of the route is lower than a threshold c and the network quality is higher than a threshold q the server may transmit full route information i.e. route information in a full format to the terminal.

The basis on which the above conditions are used is that if the length of the calculated route is smaller than the threshold d summarized route information may not be useful to the navigation service. For example if the length of the calculated route is smaller than the threshold d the number of routes that can be calculated by the server may be small and the calculated routes may be relatively simple. Therefore summarizing a small number of non useful short and simple routes may increase the route computation load of the server. Moreover transmission of the non useful summarized route information may cause network resource waste. The embodiment of the present invention illustrated in may overcome these problems.

The terminal may create a trip description based on trip parameters defined by a user of the terminal that is information about an origin and a destination using a POST command. The server may calculate a set of routes for a trip using related traffic information in response of the creation of the trip description and may reply to the terminal with a representation of trip resources including IDs of the calculated routes.

The terminal may access a set of summarized routes using a GET command based on performance parameters regarding main road segments of the routes. This step may be repeated for all routes calculated by the server. However if the length and complexity of the trip are limited and the network quality is appropriate full route information may have already been requested in this step.

The terminal or its user may select one of the calculated routes and access full route information about the selected route using a GET command. If full format routes are used this step is not performed.

The terminal may access traffic events under selected categories in relation to an ongoing route using links to traffic event resources provided by the route representation using a GET command. The access to the traffic events may be limited to the categories selected by the user. The categories refer to for example types of traffic events like traffic accident and road work.

The terminal may delete unnecessary routes that have been calculated by the server but not selected by the user using a DELETE command.

The terminal may subscribe to a notification service for the trip using a POST command. The server may notify the terminal of the following events 

a. updates of performance parameters and new traffic events limited to a selected category for all routes related to the trip 

If the vehicle carrying the terminal gets out of the current route s or bypasses the current route s the terminal may modify an origin parameter in the trip resources using a PUT operation. The server may calculate a new route based on a new origin determining that the current location of the terminal is not included in the current route. The server may delete the existing route and may respond to the PUT operation using the ID of the new route included in the trip representation. If the changed origin parameter used in the PUT operation is included in the route s the server uses this information to delete already traveled segments from the route s representation.

This step the PUT operation for the trip resources takes place when the vehicle carrying the terminal gets out of or bypasses a route the vehicle travels for a predetermined distance from a previous reported location and or the vehicle enters a segment for which the server has requested a location update.

Because the terminal subscribed to the notification service for the trip resource the subscription includes all routes related to the trip and the server will transmit a notification of new events affecting the new route the terminal may access the new calculated route along with performance parameters and traffic events by a GET operation.

Upon detection of traffic events and or heavy congestion and or a change in the location of a third party along the proposed routes the server may notify the terminal availability of updated information about the current route and an alternative route by a POST command

The subscription to the notification service includes all routes related to the trip and a notification will expand to the alternative route. Therefore the terminal may access updated information about the current route by a GET command and read the alternative route by a GET command. If the location of the third party has been changed the terminal may access new location information about the third party available in the trip resource and an updated route resource by a GET command.

In an embodiment of the present invention that will be described with reference to the terminal is a smart ND. In this embodiment the processor may be configured to request traffic information related to a trip to the server control the transceiver to receive the traffic information related to the trip from the server and calculate a route using the received traffic information. In an embodiment of the present invention before the terminal calculates a route the terminal may receive the traffic information from the server so that the terminal may use real time traffic information in calculating an initial route.

The received traffic information may include a traffic event corresponding information about obstacles to a traffic flow in an area or route related to the trip and a performance parameter corresponding to traffic flow information about road segments within a predetermined radius from the origin of the trip. The reason for requesting traffic information to the server by the terminal before route calculation is to provide real time traffic information for initial route calculation of the terminal. Without such prior traffic information the terminal has no choice but to check whether a plurality of routes initially calculated by the terminal are optimized by transmitting route information to the server a plurality of times. In addition a geographical range is limited only for a performance parameter for fast route calculation in light of a larger amount of data of the performance parameter than a traffic event. Considering the limit and rapidness of network resources real time traffic information changes over time. Therefore a performance parameter for a remote place from the origin may not be effective at the time when the vehicle carrying the terminal passes through an area or route related to the performance parameter. In this context the geographical range is confined for the performance parameter in order to prevent collection or transmission of unnecessary data.

In the presence of congestion equal to or heavier than a predetermined level within a predetermined radius from the origin the server may transmit the performance parameter to the terminal.

The traffic event may include an event such as a road work or an accident related to the area or router. The performance parameter may include at least one of the speed congestion and travel time of the road segment.

The processor may be configured to request the traffic information related to the trip to the server using boolean type data.

An embodiment in which the terminal is a lightweight ND will be described with reference to . In this embodiment the processor is configured to request a set of routes for the trip calculated by the server to the server and control the transceiver to receive information about the requested set of routes. The information about the requested set of routes may be summarized route information or full route information.

In the case where the server provides summarized route information to the terminal in the conventional technology the summarized route information is unnecessary under a specific condition. Thus two types of route information are provided to the terminal. The specific condition may be related to at least one of the length and complexity of a route and the quality of a network environment between the terminal and the server. For example if the length of the route is smaller than a predetermined length the route information has a small amount of data. Therefore if the server transmits summarized route information to the terminal network resources or the computation capability of the service is wasted.

Accordingly the information about the requested set of routes may be provided as summarized route information or full route information based on at least one of the length and complexity of the routes and the quality of the network environment between the terminal and the server.

If the length and complexity of the routes are smaller than a predetermined length and complexity and the network environment is better than a predetermined quality the terminal may receive full route information about the set of routes from the server.

Upon receipt of summarized route information about the set of routes from the server the processor may request full route information about a route selected from the set of routes to the server. Then the processor may control the transceiver to receive the full route information about the selected route from the server.

