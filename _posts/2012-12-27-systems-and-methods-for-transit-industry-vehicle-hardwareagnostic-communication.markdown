---

title: Systems and methods for transit industry vehicle hardware-agnostic communication
abstract: Systems and methods for hardware-agnostic communication between one or more mobile data terminals and one or more vehicle logic units, where a vehicle logic unit can communicate with one or more inputs from a transit industry vehicle and create an abstraction interface capable of being processed by multiple mobile data terminal hardware platforms—meaning that each vehicle logic unit can communicate with multiple mobile data terminals, and each mobile data terminal can communicate with multiple vehicle logic units.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09424692&OS=09424692&RS=09424692
owner: TRAPEZE SOFTWARE ULC
number: 09424692
owner_city: Mississauga
owner_country: CA
publication_date: 20121227
---
A portion of the disclosure of this patent document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent files or records but otherwise reserves all copyright rights whatsoever.

Transit industry vehicles TIV typically have many systems running thereon such as engines breaks audio announcement technology signage and the like. Many TIVs have monitors that keep track of and set the status of such systems. A familiar technology solution is to have various inputs and outputs from the systems provided to a vehicle logic unit VLU such VLU remains on the vehicle in normal operation. Operators of the TIV often then interact with the VLU and its data via a mobile data terminal MDT .

MDTs are continuously evolving and are varied across hardware manufacturers and the transit agencies that purchase and deploy those MDTs in their fleets. As with other general purpose computing devices the trend is for MDTs to become smaller more powerful and flexible and to communicate in many different ways.

VLUs although typically less dynamic than MDTs are also continuously evolving and frequently interact with newer systems more systems and different inputs outputs for those systems.

While VLUs typically reside and remain on vehicles until they are replaced it may be desirable for MDTs to be removed from the TIV for example by the operator and employed on another TIV at a later time. Each VLU may thus interact with multiple MDTs and the reverse.

Unfortunately the applications running on these varied and evolving MDTs and VLUs have historically needed to be continuously changed both to operate on the devices to communicate with each other and to communicate with the systems on a TIV. This is undesirable time consuming and expensive.

There is a method for hardware agnostic communication between one or more mobile data terminals MDT used for monitoring and controlling one or more TIV inputs or outputs TIVIO of transit industry vehicles and one or more vehicle logic units VLU located on transit industry vehicles TIV that are capable of communicating with one or more TIVIO comprising requesting by an MDT application executed by a processor on a first MDT communication with a first VLU on a first TIV accepting by a VLU application executed by a processor on the first VLU the request to communicate from the first MDT providing by the VLU application executed by a processor on the first VLU a first abstraction interface to the first MDT processing by the MDT application executed by a processor on the first MDT the provided abstraction interface and monitoring by the MDT application executed by a processor on the first MDT the first TIV.

The abstraction interface may comprise an XML file having one or more components each component representative of one of one or more TIVIO of the first TIV and the processing may further comprise receiving the XML file determining the first VLU s components and adjusting an application on the first MDT responsive to the results of determining.

The adjusting may further comprise adding to a monitoring screen of the application a user interface element for each one or more TIVIO that can be monitored by the first MDT inserting on a controlling screen of the application a user interface element for each one or more TIVIO that can be controlled by the first MDT.

The accepting may further comprise granting an access level to the first MDT and the one or more components that can be monitored and the one or more components that can be controlled are based on the access level granted.

The providing may further comprise polling the TIV for TIVIO on the TIV inserting a component into the XML file for each TIVIO on the TIV and obtaining one or more TIVIO values for each component having at least one value.

The method may further comprise selecting a first MDT from one or more MDT hardware platforms such hardware platforms comprising Blackberry Android or iPhone smartphones and Windows and iOS computing devices.

There is further provided a method for hardware agnostic communication between one or more mobile data terminals MDT used for monitoring and controlling one or more TIV inputs or outputs TIVIO of transit industry vehicles and one or more vehicle logic units VLU located on transit industry vehicles TIV that are capable of communicating with one or more TIVIO comprising requesting by an MDT application executed by a processor on an MDT communication with a VLU on a TIV accepting by a VLU application executed by a processor on the VLU the request to communicate from the MDT providing by the VLU application executed by a processor on the VLU an abstraction interface to the MDT processing by the MDT application executed by a processor on the MDT the provided abstraction interface and monitoring by the MDT application executed by a processor on the MDT the TIV.

The requesting processing and monitoring may be done by a first MDT and the accepting and providing may be done by a first VLU.

The requesting processing and monitoring may be done concurrently by a first MDT and a second MDT communicating with a first VLU and the accepting and providing may be done by the first VLU.

The requesting processing and monitoring may be done by a first MDT communicating with a first VLU and a second VLU and the accepting and providing may both be done by both the first VLU and the second VLU.

There is further a system for hardware agnostic communication between one or more mobile data terminals MDT used for monitoring and controlling one or more TIV inputs or outputs TIVIO of transit industry vehicles TIV and one or more vehicle logic units VLU located on TIVs that are capable of communicating with one or more TIVIO comprising a vehicle logic unit VLU further comprising one or more TIVIO jacks connected to one or more TIVIO a VLU application configured to poll the TIV for its one or more TIVIO and TIVIO values for each polled TIVIO and create an abstraction interface for communicating the TIVIO and TIVIO values to one or more MDTs upon receiving a communication request.

The system may further comprise one or more MDTs further comprising an MDT application configured to request communication with one or more VLUs receive one or more abstraction interfaces from the one or more VLUs processing the one or more abstraction interfaces and monitoring the one or more TIVs. The abstraction interface may comprise an XML file having one or more components each component representative of one of one or more TIVIO of the first TIV. The processing the one or more abstraction interfaces further comprises receiving the XML file determining the first VLU s components and adjusting the MDT application responsive to the results of determining.

TIV is a vehicle that provides or relates to the provision of transit services. TIV may include buses para transit vehicles maintenance vehicles supervisory vehicles such as cars or vans driven by supervisors or a light rail TRAM vehicles. TIV has many systems running thereon as known in the art such as engines brakes audio announcement technology signage passenger counting and the like each a TIV System not shown .

Vehicle includes TIVs but also includes vehicles operated by anyone that may have an MDT . Exemplary vehicles may include police emergency and vehicles driven by operators such as prior to or after a run route or service.

Control center may be at a transit agency and may have further systems that form part of the overall system enabling one or more forms of transportation for a transit agency. Control center may be considered an MDT despite possibly having greater systems as well.

Vehicle and control center may have MDTs that are not physically connected to TIV . As such MDTs are able to communicate wirelessly as is WVLU they may still perform control and monitoring functions for TIV .

MDT is a computing device that may take user input such as keystrokes clicks touch inputs and the like and provides the user interface to functionality relating to the provision of transit services. MDT may often be located on TIV but may be removable therefrom. Exemplary MDTs include mobile phones tablets laptops that may be running Windows or iOS operating systems for example ruggedized laptops vendor specific MDTs such as Android . Blackberry or Apple products . Each of these combinations of vendor and product type laptop versus smartphone for example may be considered a hardware platform for MDT and each of these hardware platforms may be able to communicate and function with any VLU using the abstraction interface. Operators of TIV or supervisors may be some of the primary users of MDTs .

VLU is an embedded computing device in TIV that communicates with VAN one or more TIV IO and MDT . Communication by VLU may be via wireless or wired communication such as via a serial port and or VGA connection but has typically been wired between VLU and MDT . An exemplary VLU is Trapeze s IVLU .

Wireless Vehicle Logic Unit WVLU is a type of VLU . WVLU is a computing device that communicates with one or more TIV I O router which may be a VAN or part of a VAN and further communicates with one or more MDTs optionally via VAN . As such WVLU may be referred to interchangeably herein as mobile platform . Communication between WVLU and TIV I O may be to read values from systems or set values in systems. As described herein exemplary communication may include reading a longitude and latitude from a GPS receiver or to enable a passenger counting system to start counting passenger entries and exits. As described herein exemplary communication between WVLU and MDT may include requesting information by MDT of one or more TIV I O or setting parameters or values in systems or WVLU itself. TIV I O may be plugged into jacks not shown on VLU . Each jack may be implemented using different hardware to accommodate different TIV I O as would be known to those of skill in the art.

Communication between WVLU and TIV I O and between WVLU and MDT may be wired such as Ethernet RS232 and the like or wireless such as infrared Bluetooth WLAN cellular and the like and may be via VAN and or router . WVLU communication may be accomplished via an abstraction interface such as a REST interface as described herein.

TIV IO may be any inputs and or outputs that communicate with or form part of any systems that are part of or incorporated with TIV . TIV IO are able to communicate with other systems and or computing devices such as via wired or wireless communication paths or communication networks. TIV IO may be wired into a VLU or may communicate wirelessly to one or more VLU WVLU . Exemplary TIV IO may include an odometer GPS modem for TDMA or CDMA communications engine controllers automated passenger counters APC American Disability Act ADA signs and head signs fare collection systems traffic signal priority TSP systems audio and video systems or discrete inputs that may or may not be part of one or more of the above TIV IO . Discrete inputs may require an on or off signal such as limit switches selector switches or relay contacts. TIV IO may have values numeric discrete etc that may be polled by VLU and may be set by VLU such as via MDT .

Communication network may be substantially any public or private network wired or wireless and may be substantially comprised of one or more networks that may be able to facilitate communication between themselves. VAN may be a form of communication network that exists on a vehicle. Other than being geographically restricted as it may extend only a certain distance from where a vehicle may be at a particular time VAN may be substantially similar to communication network . Router may form part of VAN and may allow WVLU to communicate with it so that communication can then continue. For example router may be a 4G router such that WVLU may then communicate as widely as any cellular device including to control center or vehicle .

The term REST refers to REpresentational State Transfer a type of software architecture for distributed systems as known by those of skill in the art. REST allows remote procedure calls RPC via a web service interface from a WLAN LAN or local connection between a client end point such as MDT in embodiments of the present invention and a host mobile platform such as VLU or WVLU in embodiments of the present invention .

The REST interface as contemplated in aspects of the present invention comprises three parts REST H which resides on VLU and REST C which resides on one or more MDT and REST client server interface or abstraction client server interface or abstraction interface REST CSI . REST H may act as a web server allowing one or more REST C connections to communicate with VLU such as via TCP IP. REST C interacts with REST H to communicate information between MDT and VLU . With REST H on VLU or WVLU any MDT with any underlying hardware software or operating system can communicate with WVLU providing REST C is present. As such and because WVLU can accommodate multiple sessions multiple MDTs such as and can all communicate with a particular WVLU

REST CSI facilitates and provides formatting and structure for communications within system . REST CSI may be one or more files data streams or communications exchanged at various times or intervals between REST C and REST H. REST CSI may be used to provide a standardized data stream to provide communications for example asynchronous communication between MDT and VLU . The file may be created and the entries may be populated with current status and or command information. Typically VLU may create the file once and then update the data entries on a predetermined duty cycle for example twice per second and broadcast this at that same rate. This broadcast may allow one or more MDTs that are interested to receive REST IM and use its contents to perform various functions. When MDT issues a command to VLU it may create an XML file for that transaction command for example to display text data to an ADA sign inside TIV .

REST CSI may be implemented for example via one or more XML interfaces files. An exemplary REST CSI is shown below 

In reference to the above XML file REST CSI TIV IO may be abstracted into adapters labeled components above. Details about TIV IO and other aspects of VLU or TIV may also be inserted in REST CSI . MDT A may then probe VLU for its REST IM allowing it to find out how and of what type of adapters are installed on a VLU and other features of VLU and TIV as described herein. Following this approach any particular VLU can communicate with one or more MDT A by providing REST CSI thereto. Similarly any particular MDT can communicate with any VLU having REST CSI by probing for REST CSI and interpreting the TIV IO and other features of VLU .

The ComponentStream presents a standard interface for a component or TIVIO regardless of the make and manufacturer of any of TIV I O MDT and VLU . This allows many applications including multiple MDT A and VLU A to share the standardized data provided by the DeviceStream. The DeviceStream may be dynamic in nature only assembling and or presenting communicating to a particular MDT the data items available on a particular VLU or TIV or that are available based on the access level granted to the particular MDT .

VLU A is an application residing on VLU . VLU A largely controls VLU including its operation and communication with other aspects of system . VLU A may have application programming interfaces API VLU API associated therewith or exposed that provide access to functionality.

MDT A is an application residing on MDT . MDT A largely controls MDT including its operation and communication with other aspects of system . MDT A may have application programming interfaces API MDT API associated therewith or exposed that provide access to functionality. MDT A may be configured to present one or more screens to a user of MDT to enable to functionality described herein. For example MDT A may process an XML file to determine what components from TIV should be displayed on one or more screens showing all TIV IO such as monitoring screens to monitor TIV IO or controlling screens to control one or more TIV IO .

VLU HP is a hardware system that communicates with TIV IO . VLU HP may poll TIV IO listen for communications thereto or therefrom and the like as described herein. Such may allow for determining what TIV I O may be present and may involve polling or pinging one or more jacks of VLU . Communication may be wired or wireless. Communication may allow TIV IO to be controlled monitored and the like such as by reading values associated with TIV IO receiving statistics or system information therefrom or setting values or otherwise controlling TIV IO .

If MDT is to communicate with VLU MDT A may make a function call to VLU A via the MDT A and MDT API. The function call and parameters are then serialized by REST C and transmitted to REST H un serialized by REST H and then VLU A determines which API call to make to the corresponding software component hardware or TIV IO connected to the VLU HP .

Once VLU API returns to the VLU A the desired information such as a status and any associated parameters this information is serialized and returned to MDT via the REST interface to the associated REST C . This REST C then un serializes this returned information and it is returned to the MDT A via MDT API.

If VLU is to communicate with MDT a similar process would occur but in reverse. VLU A may make a function call via the VLU A and VLU API . The function call and parameters may then be serialized by REST H and transmitted to REST C un serialized by REST C and then MDT A determines which API call to make or other step to perform on MDT to realize the desired functionality.

It is to be understood that communication between MDT and VLU may occur for many reasons and at various frequencies. MDT A and VLU A may have particular functionalities or users thereof may desire functionalities that require communication to occur potentially on a periodic basis ie check the engine temperature every 30 seconds . There may be triggers for one time communications such as speed warnings probing for current number of passengers and the like.

These addresses may be a private or public address and may be part of and known to the Internet at large or a smaller network such as VAN a private wide area network or the like .

FLO may be an address for VLU . As shown in that may be 169.254.1.0. The 169 may represent an agency the 254 VLU or a bus. Similarly FLO may be an address for MDT . As shown in that may be 169.252.0.0. The 252 may represent MDT .

SLO may be an address for a subsystem of a bus such as an engine odometer or passenger counter system. As shown in that may be 169.254.1.1. The 1 may represent the engine and the 0 representing that it is the engine itself as opposed to a subsystem.

TLO may be an address for an aspect characteristic sensor etc of a subsystem or a further subsystem or a subsystem. As shown in that may be 169.254.1.1. The 1 may represent the temperature of the engine.

In many cases VLU may be hardwired to the subsystems in . In such case IP addresses may not be required.

Although many addressing schemes are within the scope of the present invention that shown in may allow VLU to uniquely address all subsystems and their components both for its internal control and monitoring and for that of any MDTs that desire to communicate with VLU and it subsystems. Similarly addresses of MDTs may allow one or more VLU to communicate with MDTs . Addressing schemes may also indicate other characteristics about TIV IO such as whether TIV IO can be controlled or simply read for example.

In Scenario a communication begins with an event at TIV IO and ends with TIV IO being sent a communication TIV IO receiving the communication may either be the same one or another one.

In Scenario a communication begins with an action at MDT and ends with a response back to MDT . The response back may be received by the same MDT .

In a first example a covert alarm TIV IO changes states at . At VLU detects the change of state and reports the change of state to MDT and MDT A via REST H on VLU communicating with REST C .

At MDT A issues a command to set the video camera discrete output to On to VLU via the REST interface.

At VLU receives the command to set the video camera discrete output to On via REST H Interface from the MDT A .

At VLU sets the video camera discrete output to an On state enabling the camera. The camera signal can then be viewed to determine what action should be taken for example an action by a driver of the bus having the alarm condition .

In a second example a passenger counter system is being used. At a door open event occurs detected by either a discrete input or J1708 message . At VLU A detects the change of door open state and issues a command via the J1708 port to the passenger counter device that the door is open which triggers the passenger counter to start counting the number of passengers boarding getting on the vehicle or bus and alighting getting off the vehicle or bus . Still at VLU A detects the change of door open state and reports the current state to MDT A via the REST interface.

At MDT A executes based on the current configuration a variety of pre defined tasks related to the door open event.

At VLU A waits for the door close state to occur. At the door close state is detected by either a Discrete Input or J1708 Message .

At VLU A detects the change of door close state and issues a command via the J1708 port to the passenger counter device that the door is closed which triggers the passenger counter to stop counting passengers. Finally VLU A reports the current state to MDT A via the REST Interface.

Method begins at where MDT initiates communication with VLU . This initiation may be accomplished in many ways some of which may be akin to selecting WiFi networks for example. Of course it is to be understood that VLU may actually initiate the communication for example by broadcasting itself to MDT and a particular MDT being able to receive or understand the broadcast based on one or more criteria of MDT or VLU . Initiating the communication may include requesting by MDT or a processor thereon access to VLU .

At VLU determines whether to accept or reject communication. This may be determined for example by knowing what MDT is making the request such as by an MDT identifier being provided and VLU determining whether it is valid by receiving a user name and password from MDT or other approaches as would be known to those of skill in the art.

Of course it is to be understood that different MDTs may have different access levels. For example some may be able to read and write TIV IO values. Others may only be able to read such values. Such abilities may relate to the user of MDT for example where a rider of TIV may be allowed to read simple values such as a GPS location while operators of TIV transit supervisors or emergency crews may have different abilities. Other different access levels or motivations therefore are within the scope of the present invention.

If communication is accepted at then method continues at where an interface may be provided to MDT by VLU . This may substantially comprise for example VLU providing REST IM to MDT .

At MDT receives the interface and processes the interface. Processing may involve reading the interface to determine characteristics and information about VLU . For example processing may include determining TIV IO associated with VLU determining attributes of TIV and obtaining other features of VLU .

Processing may also involve setting up MDT to an initial state such as a state that an operator may desire to be in prior to starting a run in TIV . This may involve reading certain values from TIV IO so that MDT can present an initial state to a user of MDT . This may further involve adding or removing user interface elements for monitoring or controlling the TIV IO that are possible given the combination of the particular TIV and user of MDT . User interface elements not shown may include text boxes toggles slides or bars or other features as are known in the art to view and set parameters of software applications.

Determining such features and characteristics or other processing at may result in configuration changes to MDT and in particular MDT A at . For example if TIV does not have a passenger counter system then MDT A may disable or remove the feature that would allow a user of MDT A to query for the passenger count. Of course other adjustments to MDT A may occur for example to match the route driver date and other aspects of the present circumstance in which the particular MDT is communicating with the particular VLU .

Method proceeds to where both MDT and VLU may wait for operational communication as such operational communication is described herein.

It will be apparent to one of skill in the art that other configurations hardware etc may be used in any of the foregoing embodiments of the products methods and systems of this invention. It will be understood that the specification is illustrative of the present invention and that other embodiments within the spirit and scope of the invention will suggest themselves to those skilled in the art. All references cited herein are incorporated by reference.

