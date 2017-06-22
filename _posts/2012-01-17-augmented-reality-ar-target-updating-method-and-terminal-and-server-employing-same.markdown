---

title: Augmented reality (AR) target updating method, and terminal and server employing same
abstract: There is provided a method for updating an AR target of a terminal, the method comprises: receiving an AR target, a boundary distance for a coverage area of the AR target, and the at least one area ID list from a server; if precise positioning is possible, determining whether or not the location of the terminal satisfies a boundary condition on the basis of the boundary distance; if precise positioning is impossible, determining whether or not the serving cell ID of the terminal satisfies the boundary condition on the basis of said the at least one area ID list; and, if it is determined that the boundary condition is satisfied, transmitting an update request from the AR target to the server.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09271114&OS=09271114&RS=09271114
owner: LG Electronics Inc.
number: 09271114
owner_city: Seoul
owner_country: KR
publication_date: 20120117
---
This Application is a 35 U.S.C. 371 National Stage Entry of International Application No. PCT KR2012 000397 filed Jan. 17 2012 and claims the benefit of U.S. Provisional Application No. 61 433 266 filed Jan. 17 2011 all of which are incorporated by reference in their entirety herein.

This specification relates to a method of updating an AR target and a terminal and server adopting the same.

Augmented Reality AR service is service for reinforcing and providing pieces of additional information that are difficult to be obtained by only the real world by composing cyber things on the basis of the real world. In mobile AR service additional information is added to real things seen by the camera of a terminal through information about the current location and direction of the terminal and shown.

Common mobile AR service is a method in which a terminal requests from a server an AR target or AR content including contents necessary for a user in the current location of the terminal and provides the requested AR target or uses an AR target previously stored in the terminal. This method is disadvantageous in that seamless mobile AR service is not provided to a user who uses consecutive mobile AR service.

Embodiments disclosed in this specification have been made to solve the above described problem and there are provided a method of updating an AR target stored in the cache of a terminal in order to provide a user with seamless mobile AR service and a method of previously downloading an AR target of an area that is substantially necessary for a user and a terminal and server adopting the same.

A method of a terminal updating an AR target according to an embodiment disclosed in this specification includes the steps of receiving an AR target a boundary distance for a coverage area of the AR target and at least one area ID list from a server determining whether or not the location of the terminal satisfies a boundary condition based on the boundary distance if precise positioning is possible determining whether or not the serving cell ID of the terminal satisfies the boundary condition based on the at least one area ID list if the precise positioning is impossible and sending an update request for the AR target to the server if it is determined that the boundary condition is satisfied.

In an embodiment the at least one area ID list includes an entire area ID list included in the coverage area and a boundary area ID list corresponding to the boundary of the coverage area.

Furthermore in an embodiment the boundary condition is satisfied if the serving cell ID of the terminal is included in both the entire area ID list and the boundary area ID list.

Furthermore in an embodiment the at least one area ID list includes an outer area ID list corresponding to the boundary of the coverage area and an inner area ID list corresponding to the inside of the boundary of the coverage area.

Furthermore in an embodiment the boundary condition of the terminal is satisfied if the serving cell ID of the terminal is included in the outer area ID list and is not included in the inner area ID list.

Furthermore in an embodiment the at least one area ID list includes an area ID list corresponding to the inside of the coverage area.

Furthermore in an embodiment the boundary condition of the terminal is satisfied if the serving cell ID of the terminal is not included in the area ID list corresponding to the inside of the coverage area.

Furthermore in an embodiment the at least one area ID list includes a boundary area ID list corresponding to the coverage area.

Furthermore in an embodiment the boundary condition of the terminal is satisfied if the serving cell ID of the terminal is included in the boundary area ID list.

Furthermore in an embodiment the boundary condition of the terminal is satisfied if a distance between a location of the terminal at a point of time at which the AR target has been requested and a current location of the terminal is greater than or equal to the boundary distance.

Furthermore in an embodiment the boundary condition of the terminal is satisfied if a radius of the coverage area is greater than a sum of the distance between the location of the terminal at the point of time at which the AR target has been requested and the current location of the terminal and the boundary distance.

Meanwhile a method of a server updating an AR target according to another embodiment disclosed in this specification includes the steps of receiving an update request for the AR target from a terminal wherein the request includes a moving direction and motion state of the terminal determining whether or not the terminal substantially satisfies a boundary condition based on the moving direction of the terminal generating an AR target based on the moving direction and motion state of the terminal if the terminal substantially satisfies the boundary condition and sending the generated AR target to the terminal.

In an embodiment the step of generating the AR target includes the step of filtering the AR target determining the coverage area of the AR target or determining the resolution of the AR target based on the motion state of the terminal.

Furthermore in an embodiment the boundary condition is substantially satisfied if the moving direction of the terminal is a direction becoming distant from the center of a coverage area of the AR target.

Furthermore in an embodiment the step of generating the AR target includes the step of limiting a coverage area of the AR target based on the moving direction of the terminal.

The present invention provides an AR target in a predetermined area facilitates a method of a terminal itself providing a proper AR target according to a movement of a user and can increase efficiency of network resources and reduce a load of a server as compared with an existing method of a server on a network continuing to provide an AR target according to a movement of a user.

Furthermore seamless AR service can be provided to a user who uses AR service through mobile and thus user experiences can be increased because an AR target stored in a terminal is predicted in advance before the AR target gets out of an area where the AR target is covered and a necessary and new AR target is requested and received before an AR target gets out of a corresponding area.

The characteristics and preferred embodiments of the present invention are described in detail below with reference to the accompanying drawings.

In Augmented Reality AR interactive media is combined with the real world and points of time and experiences in the real physical world are augmented by cyber digital objects by an electronic device.

In AR a new paradigm of interactivity in which common experiences recognized by a user when the user obtains searches for information are suddenly changed. Since the augmentation of reality is real time and situational AR is practically interactive can be opened up digitally and is meaningful and available.

To use the location and direction of the camera of a mobile terminal enables various scenarios in which AR technology is determined by network locations of GPS and OMA SUPL and the locations of devices such as a compass and various sensors of a mobile terminal.

A service provider generates new and attractive mobile AR service and provides the generated mobile AR service to a user through a mobile AR enabler .

A user has a lot of experiences while moving and easily finds useful information about luxurious amenities and surrounding reality.

A content provider publisher has a new opportunity to provide content and information. Owing to information including phenomena affecting a new digital era it is necessary to classify pieces of content better and to filter and synthesize the pieces of content in order to simplify access to the content and the consumption of the content and to guarantee search for the content.

The mobile AR enabler can guarantee the exchange of pieces of AR content between cross platforms and common access to the AR content by proving a new mechanism for the generation publication transmission filtering and personalization of the AR content.

In the following description AR content refers to a multimedia object used to augment enhance the perception of a user for the real world such as a picture video text a 3 D model and audio.

Furthermore an AR marker refers to a digital object that is displayed on a screen indicative of the availability of AR content regarding an AR target.

Furthermore the AR target refers to an entity in the real world that may be associated with AR content such as Point Of Interest POI a product a person and a car.

Furthermore an AR view refers to a point of time provided by an application that supports AR content so that a user can see the AR content overlapped with a camera video stream on a screen.

Furthermore personalization refers to the processing of custom tailored AR content based on user information. Personalization can imply the use of estimation regarding a user which can be distributed over for example many static data and or a user profile and preference. Furthermore contextualization refers to the processing of custom tailored AR content based on specific user context. Contextualization can imply the use of estimation regarding user context such as many dynamic data and or for example a location and performance.

Furthermore user context refers to dynamic information set indicative of a current common state of a user and surrounding environments of the user. The information set can be searched for from various sources including an OMA enabler.

Furthermore an AR App. is an external entity residing in a device. The AR App. requests and receives AR content from a mobile AR client and provides the AR content to a user. Furthermore the AR App. reports AR metrics data to the mobile AR client.

Furthermore the mobile AR client is a device side function component of the mobile AR enabler and is installed in a terminal . The mobile AR client resides in the terminal .

Furthermore a mobile AR server is a network side function component of the mobile AR enabler and is installed in a server . The mobile AR server resides in the server .

Furthermore an API is an abbreviation of an Application Programming Interface AR is an abbreviation of Augmented Reality MobAR is an abbreviation of Mobile Augmented Reality POI is an abbreviation of Point Of Interest DM is an abbreviation of a Data Matrix and QR is an abbreviation of a Quick Response.

A MobAR 1 interface is an interface exposed to an AR App. by a mobile AR client. The AR App. requests and obtains AR content from the mobile AR client using this interface and reports AR metrics data to the mobile AR client.

A MobAR 2 interface is an interface exposed to the mobile AR client by a mobile AR server. The mobile AR client requests and obtains AR content from the mobile AR server using this interface and reports AR metrics data to the mobile AR server.

The MobAR 2 interface requests AR content an AR target based on filters such as a category location information a search range a direction a consumption method screen resolution and user preferences and various criteria such as detailed information about an AR target.

Furthermore the MobAR 2 interface subscribes to AR content push or terminates subscription based on filters such as a category location information a search range a direction a consumption method screen resolution and user preferences and various criteria such as detailed information about an AR target.

Furthermore the MobAR 2 interface sets updates user preferences such as a search range a category a push filter and metrics collection enable disable .

Furthermore the MobAR 2 interface sends proper AR metrics and user feedback e.g. a grade collected in order to take future AR content selection into consideration.

A MobAR 3 interface is an interface exposed to the mobile AR server by a mobile AR client. The mobile AR client receives AR content through this interface from the mobile AR server through a basic push transfer mechanism. The mobile AR server may inform the mobile AR client of information such as enable disable metrics and collection through this interface.

The MobAR 3 interface transfers the direct push of AR content for subscription and requests the indirect notice of AR content for subscription.

A MobAR 4 interface is an interface exposed to the content provider by the mobile AR server. The content provider provides AR content to the mobile AR server and uses this interface to access functions provided by the mobile AR server. In general this interface is exposed in the form of an API.

The MobAR 4 interface deploys AR targets and requests to establish or release an association between AR content and a specific AR target.

The MobAR 4 interface designates the deployment rules of AR content such as the start time and delay time of AR content deployment a different AR content association using a user or the same AR target based on time and access control over premium content including them but not limited thereto .

Furthermore the MobAR 4 interface accesses anonymous feedback related to a user interaction and metrics e.g. for AR content improvement .

The mobile AR client subscribes to the mobile AR server in order to use mobile AR service. When the subscription is performed for the first time this procedure is not necessary afterward. The mobile AR client requests the use of the mobile AR service from the mobile AR server i.e. service request . This request includes the type of service to be used by the mobile AR client. In order to be provided with content suitable for its device the mobile AR client informs the mobile AR server of device capabilities i.e. exchange of device capabilities . Capabilities that can be supported by the mobile AR server can also be provided to the mobile AR client if necessary. The mobile AR client requests and receives a real AR target necessary to use the service i.e. content request response . This step may be generated several times depending on the type of service. The requested service between the mobile AR client and the mobile AR server is terminated i.e. service termination .

In accordance with the process of providing an AR target according to an embodiment disclosed in this specification in order to provide seamless AR service to a user the terminal in which an AR target or also called AR content hereinafter is previously stored predicts a situation in which a user gets out of an area covered by the previously stored AR target before the user gets out of the area requests an AR target within an area where the user is expected to be placed from the server in advance and receives the requested AR target from the server . This process is described in more detail below.

First when providing an AR target to the terminal the server provides the terminal with a boundary condition along with information about an area covered by the AR target S .

Thus the terminal compares a current state with the boundary condition provided by the server and determines whether or not the current state is a situation in which the terminal can get out of the area covered by the AR target previously stored by a user S .

Furthermore if the terminal determines that the current state is a situation in which it can get out of the area covered by the AR target previously stored by the user the terminal requests a new AR target from the server S . Here the terminal sends information such as a moving direction or motion state of the terminal to the server .

The server selects an AR target to be provided to the terminal based on the information received from the terminal S .

The server provides the selected AR target to the terminal . Here the server provides a new boundary condition along with information about an area covered by the provided AR target S .

A method of determining various boundary conditions and determining whether or not a current state is a situation in which the terminal can get out of an area covered by an AR target previously stored by a user and a method information transmitted from the terminal to the server when the terminal requests an AR target and a method of the server using the information are described below.

Referring to to the terminal can determine a point of time at which an AR target will be updated using an area ID. Here the area ID is one of representation methods indicative of an area the area ID is the identity of an area in a wireless network and can be configured through information about the cell ID of a network. Cell IDs and area IDs for respective networks are shown in Tables 1 to 8 below.

The server also provides the terminal with the area ID of an area covered by an AR target when providing the AR target to the terminal . The terminal compares the received area ID and its own serving cell and determines a point of time at which the AR target will be updated. For example when providing an AR target to the terminal the server also provides the terminal with a list of area IDs of an area covered by the AR target. The area ID list can be configured as in Table 9 below.

Referring to the entire area ID list is a set of all area IDs of an area covered by a provided AR target and is C to C. The boundary area ID list is a set of area IDs near the boundary of the area covered by the provided AR target and it includes C C C C C C C C C C C C C and C. The terminal continue to compare its own serving cell ID with the area IDs provided by the server while mobile AR service is in progress. Operations according to the results of the area ID comparison are defined as in Table 10 below.

According to the operation shown in Table 10 the terminal can check a point of time at which a stored AR target will be updated.

Referring to the inner area ID list is a set of area IDs entering an area covered by a provided AR target and it includes C C C C C C C C C and C. An outer area ID list is a set of area IDs near at the boundary of the area covered by the provided AR target and it includes C C C C C C C C C C C C C and C. The terminal continues to compare its own serving cell ID with the area IDs provided by the server while mobile AR service is in progress. Operations according to the results of the area ID comparison are defined as in Table 12 below.

Referring to the area ID list is a set of area IDs entering an area covered by a provided AR target and it includes C to C. The terminal compares its own serving cell ID with the area IDs provided by the server while mobile AR service is in progress. Operations according to the results of the area ID comparison are defined as in Table 14 below.

Referring to the area ID list is a set of area IDs near the boundary of an area covered by a provided AR target and it includes C to C. The terminal compares its own serving cell ID with the area IDs provided by the server while mobile AR service is in progress. Operations according to the results of the area ID comparison are defined as in Table 16 below.

As shown in to the terminal may expect that a user will soon get out of an area covered by an AR target and receive a necessary AR target from the server in advance before the user gets out of the area covered by the AR target. In another embodiment the terminal may request an AR target when the terminal gets out of an area covered by an AR target. In this embodiment when providing an AR target to the terminal the server may provide a set of area IDs of all areas covered by the AR target to the terminal as the entire area ID list. Or as described with reference to when the server provides a set of area IDs entering an area covered by an AR target as the entire area ID list the terminal may compare its own serving cell ID with the provided area ID list and request a new AR target from the server when the own serving cell ID is not matched with the provided area ID list.

Referring to the terminal determines whether or not the terminal is in a situation in which the terminal can get out of an area covered by an AR target using a distance between the initial location and the current location of the terminal . Here the initial location of the terminal means the location of the terminal at a point of time when the terminal has requested the AR target.

Referring to the terminal requests the server from an AR target at a point A. Here the terminal provides the server with information about the location of the terminal i.e. information about the location of the point A . The server transfers an AR target which can cover a specific area to the terminal on the basis of the location i.e. point A of the terminal . The terminal shows AR targets within its own search range from among AR targets received from the server to a user.

Referring to the search range of the terminal is now within the area covered by an AR target. Referring to the search range of the terminal is now within the area covered by the AR target also near the area and it is expected that the search range of the terminal will soon get out of the boundary of the area covered by the AR target. Referring to the search range of the terminal has gotten out of the area covered by the AR target.

The terminal can check whether the terminal corresponds to any situation of to based on a distance between the initial location point A and the current location point B of the terminal . That is the terminal may determine when an AR target will be updated based on a distance between the initial location point A and the current location point B of the terminal . When the radius of the area covered by the AR target and the radius of the search range of the terminal are checked the terminal can update the AR target from the server according to a distance between the initial location point A and the current location point B of the terminal e.g. when the distance is threshold or higher . The radius of the area covered by the AR target can be checked by the server that generates the AR target and the terminal can transfer the radius of the search range of the terminal to the server . While mobile AR service is provided the terminal continues to calculate a distance between the initial location point A and the current location point B of the terminal and compares the calculated value with a boundary distance on which the AR target needs to be updated. If as a result of the comparison a condition is satisfied the terminal may request the update of the AR target from the server .

If the radius of the area covered by the AR target is defined to be R the search range of the terminal is defined to be r the boundary distance on which the AR target needs to be updated is defined to be C and a distance between the initial location and the current location of the terminal is defined to be c the operations of the terminal according to the results of the distance comparison are defined as in Table 17 below.

The terminal can request the update of the AR target from the server according to the values of R r and C at points of time defined in Table 18 below.

That is the terminal transfers the radius of its own search range to the server . The terminal can transfer a radius of its own search range to the server at a point of time at which the terminal requests the server to provide an AR target or at a point of time at which the terminal transfers its own capabilities to the server . Furthermore the terminal requests the AR target from the server . Here the terminal requests the AR target including its own current location i.e. the initial location . The terminal may transfer the radius of its own search range to the server and at the same time request the AR target from the server .

The server generates an AR target to be transferred to the terminal based on the current location of the terminal that has been received from the terminal . Here the server generates a boundary condition the boundary condition is represented by the length on which the AR target needs to be updated by taking the range of the area covered by the AR target and the radius of the search range of the terminal into consideration. The server transfers the generated AR target and the boundary condition to the terminal .

While mobile AR service is provided the terminal calculates a location of the terminal at a point of time at which the terminal has requested the AR target from the server that is a distance between the initial location and the current location and compares the calculated distance with the boundary condition received from the server . If the boundary condition received from the server is satisfied i.e. the calculated distance is matched with the boundary condition the terminal requests the update of the AR target from the server .

The method using an area ID described with reference to to and the method using a distance between the initial location and the current location of the terminal described with reference to have been described above as a method of determining a point of time at which an AR target stored in the terminal will be updated. The two methods have advantages and disadvantages. The method using an area ID can be used to directly determine a point of time at which an AR target will be updated without using additional precise positioning e.g. GPS and can be used irrespective of the interior and exterior of a room. In contrast the method using a distance between the initial location and the current location of the terminal has high precision because it is based on precise positioning GPS but the method requires precise positioning GPS and thus the method cannot be used in the interior of a room where precise positioning GPS is impossible.

Accordingly if the terminal supports both the two methods and a proper method of the two methods can be used according to circumstances a mutual supplementation effect is generated. For example when providing an AR target to the terminal the server provides the terminal with a boundary distance along with an area ID. When the terminal is placed in the interior of a room where precise positioning is impossible the terminal can determine a point of time at which an AR target will be updated according to the method using area ID. In an area where precise positioning is possible the terminal can perform precise positioning and determine a point of time at which an AR target will be updated based on a distance between the initial location and the current location of the terminal .

The terminal requests an AR target from the server S . The request message includes condition information about the AR target to be received by the terminal . In general when the terminal requests the AR target from the server information included in the message includes screen resolution a supported media type a search range a consumption style and location information.

The server generates an AR target to be provided to the terminal based on the condition information about the AR target that has been received from the terminal and provides the generated AR target to the terminal S .

A condition on which an AR target to be provided can be efficiently selected in a method of the terminal previously downloading the AR target in a necessary area from the server is described below.

A motion state described below indicates a current motion state of the terminal . The motion state can indicate any one of for example stationary pedestrian running cycling a car a train an aeroplane a boat and fidgeting refer to OMA LPPe v1.0 TS .

The motion state is not a value generated by a single function e.g. a single sensor within the terminal but is a value that can be inferred through the output values of various sensors such as an acceleration system a gyro sensor and a compass within the terminal . To this end there is a need for a method algorithm for inferring a motion state using values outputted from respective sensors and a different algorithm suitable for the characteristics of a sensor needs to be applied to a different terminal because the same sensor has different characteristics depending on a chip used therein or a state. This algorithm can be any one of a various known algorithms. As a result the terminal can obtain a motion state using various known algorithms and values outputted from various sensors within the terminal . As an alternative a user may directly input a motion state to the terminal a user application may directly generate a motion state or the terminal may generate and use the value.

Meanwhile when generating an AR target the server can determine an area covered by the AR target to be provided to the terminal through a motion state. If a motion state of a user is cycling or a car rather than stationary or pedestrian the server can provide the terminal with an AR target which can cover a wider area. If moving speed is faster the server can provide the terminal with AR targets having higher priority than many AR targets.

In order to use a motion state the terminal may include sensors an acceleration system a gyro sensor and a compass for providing information necessary to determine the motion state and an algorithm for determining a current motion state of a user based on values received from the sensors determine the motion state of a user in advance a point of time at which AR service is requested or a point of time at which an AR target is requested and include the results of the determination.

Furthermore in order to use a motion state the server needs to add a motion state category to each AR target. The motion state category is shown in Table 20 below as an example.

Furthermore the server can include a function of filtering AR targets to be provided based on a motion state provided by the terminal and a function of making different a cache area covered by an AR target depending on a motion state. For example when the terminal moves fast the server can provide the terminal with an AR target covering a wide area. When the terminal moves slowly the server can provide the terminal with an AR target covering a relatively narrow area. Furthermore the server can make different the resolution of an AR target depending on a motion state. For example when the terminal moves slowly the server can provide an AR target in more detail densely accordingly a user can view more visual objects in the same range . When the terminal moves fast the server provides an AR target simply relatively less densely accordingly a user can view less visual objects in the same range .

In an embodiment transport means such as a car a train an aeroplane and a boat may be taken into consideration in the above described motion state. In this case the server can provide the terminal with an AR target by taking transport means into consideration. For example since moving speed of a user using a car may be faster than moving speed by foot an area covered by an AR target may be widened or the resolution of the AR target may be increased as described above. However the server may check information about the destination of a user using various means e.g. the reception of destination information from the terminal and send an AR target for the destination to the terminal prior to departure or while moving.

Likewise if a user is in the airport a motion state may be set as an aeroplane the server may check information about the destination of the user using various means e.g. the reception of destination information from the terminal and send an AR target for the destination to the terminal prior to departure or while moving. Accordingly user convenience can be increased as compared with a conventional method in which after a user reaches a destination the terminal receives an AR target.

the heading information described below refers to information about the direction along which a user now moves. The server can determined that the terminal moves in which direction based on the heading information. Based on heading information the server can provide the terminal with an AR target having a better possibility frequency and may determine whether or not it is necessary to provide a new AR target.

Referring to and the current location of the terminal is placed insides near the boundary of an area covered by an AR target. If heading information is not taken into consideration the terminal will request an AR target from the server because the current location of the terminal is placed at the boundary of the area covered by the AR target. In response thereto the server will generate an AR target and provide the generated AR target to the terminal . If heading information is taken into consideration however whether or not to update the AR target is different in and .

That is referring to since a current moving direction of the terminal is a direction opposite to that of the area covered by the AR target that is a direction that becomes distant from the initial location i.e. the center of the area covered by the AR target of the terminal if the terminal requests an AR target from the server the server can generate an AR target and provide the generated AR target to the terminal . This is because there is a good possibility that the terminal will soon get out of the area covered by the AR target as it becomes far from the initial location.

In contrast referring to since a current moving direction of the terminal is the same direction as that of the area covered by the AR target that is a direction that becomes close to the initial location i.e. the center of the area covered by the AR target of the terminal the terminal may not request an AR target from the server or the server may not provide the terminal with an AR target although the terminal requests an AR target from the server . This is because there is a poor possibility that the terminal will soon get out of the area covered by the AR target as it becomes close to the initial location.

Referring to and the server may provide the terminal with an AR target that is expected to have high use frequency of the terminal based on heading information.

The method of using a motion state and heading information has been described above as a method of efficiently selecting an AR target to be provided when the server receiving a request to provide a new AR target from the terminal determines the new AR target to be provided to the terminal . In accordance with this method the server can efficiently provide an AR target to the terminal because it can determine whether or not the terminal actually needs a new AR target and also select an AR target according to a current situation of the terminal . This method may be used in a method of previously receiving AR targets within an area to which the terminal is expected to move but may be commonly used in a process in which the terminal requests an AR target from the server .

The terminal stores an AR target and a boundary condition previously received from the server and becomes a state in which the terminal can use the stored AR state S .

Furthermore the terminal determines whether or not the terminal will get out of an area covered by the AR target stored in the terminal and or whether or not it is expected that the terminal will get out of an area covered by the AR target stored in the terminal based on the boundary condition received from the server S . The terminal can determine the boundary condition using the method using an area ID and the method using a boundary distance as described above. If precise positioning using GPS is not available the terminal determines the boundary condition using a boundary distance. If precise positioning is impossible the terminal determines the boundary condition using an area ID.

When an event is generated at step S that is when the terminal gets out of the area covered by the stored AR target or if it is expected that the terminal will get out of the area covered by the stored AR target the terminal requests an AR target corresponding to an area to which the terminal will move from the server S . This request message can include the location search range screen resolution motion state and heading information of the terminal .

The server selects an AR target to be provided to the terminal based on information received from the terminal S . First the server determines whether or not the terminal will get out of the area covered by the stored AR target based on the location and heading information of the terminal S . If it is determined that the terminal will not get out of the area covered by the stored AR target the server does not provide the terminal with an AR target. If it is determined that the terminal will get out of the area covered by the stored AR target however the server selects a new AR target using the location search range screen resolution motion state and heading information of the terminal received from the terminal S . For example the server selects a new AR target in an area to which the terminal is expected to move using the location and heading information of the terminal . Furthermore the server determines an AR target capable of covering an area having what size or what shape based on the motion state and the heading information.

The server transfers the AR target determined at step S to the terminal S . Here the server also transfers a new boundary condition for the AR target transferred to the terminal .

A description of steps S S and S shown in is the same as the description of the steps S S and S shown in and thus the description is omitted.

At step S the terminal determines whether or not precise positioning using a GPS module is not possible S . For example the terminal determines whether or not the location of the terminal can be precisely measured using a GPS module although the GPS module is not activated or the intensity of a measured GPS signal is lower than a threshold although the GPS module is activated.

If precise positioning is possible the step S branches to step S in which the terminal determines a boundary condition using a boundary distance for a detailed description refer to the description of . This is because to determine the boundary condition using an area ID is much more precise than to determine the boundary condition using a boundary distance. At step S when an event satisfying the boundary condition is generated for example if it is expected that the terminal will get out of the area covered by the AR target the terminal requests a new AR target from the server S .

In contrast if precise positioning is impossible the step S branches to step S in which the terminal determines a boundary condition using an area ID for a detailed description refer to the description of to . This is because precise positioning is impossible to the extent that the boundary condition can be determined using a boundary distance. At step S when an event satisfying the boundary condition is generated for example if it is expected that the terminal will get out of the area covered by the AR target the terminal requests a new AR target from the server S .

Meanwhile at step S the server determines whether or not the terminal moves in a direction along which the terminal gets out of the area covered by the AR target based on the location and heading information of the terminal received from the terminal S . For a detailed description of the determination method based on the location and heading information of the terminal reference can be made to and .

At step S if it is determined that the terminal moves in the direction along which the terminal gets out of the area covered by the AR target the server generates an AR target to be provided to the terminal based on the heading information and the motion state S . A configuration for filtering AR targets to be provided by the server based on the motion state a configuration for differently configuring a cache area covered by an AR target according to a motion state and a configuration for making different the resolution of an AR target according to the motion state have already been described. Furthermore a configuration in which the server provides an AR target having a good possibility frequency in the terminal based on the heading information has already been described.

As shown in the terminal includes a storage means a controller and a transmission and reception unit . The storage means stores the methods according to the embodiments of . The controller controls the storage means and the transmission and the reception unit . In particular the controller executes each of the methods stored in the storage means . Furthermore the controller sends the above described signals through the transmission and reception unit .

Furthermore as shown in the server includes storage means a controller and a transmission and reception unit . The storage means stores the methods according to the embodiments of . The controller controls the storage means and the transmission and reception unit . In particular the controller executes each of the methods stored in the storage means . Furthermore the controller sends the above described signals through the transmission and reception unit .

As described above the aforementioned embodiments should be constructed as being only illustrative from all aspects not as being restrictive. The scope of the present invention is defined by the following claims rather than the detailed description and the meanings and scope of the claims and all changes or modified forms derived from their equivalents should be constructed as falling within the scope of the present invention.

