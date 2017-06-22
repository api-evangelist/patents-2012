---

title: Navigation system with non-native dynamic navigator mechanism and method of operation thereof
abstract: A method of operation of a navigation system includes: receiving a destination; generating a route to the destination; and generating a non-native dynamic navigation based on the route for displaying on a device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09441982&OS=09441982&RS=09441982
owner: Telenav, Inc.
number: 09441982
owner_city: Santa Clara
owner_country: US
publication_date: 20121008
---
This application claims the benefit of U.S. Provisional Patent Application Ser. No. 61 546 920 filed Oct. 13 2011 and U.S. Provisional Patent Application Ser. No. 61 615 855 filed Mar. 26 2012 and the subject matter thereof is incorporated herein by reference thereto.

The present invention relates generally to a navigation system and more particularly to a system with non native dynamic navigator mechanism.

Modern portable consumer and industrial electronics especially client devices such as navigation systems cellular phones portable digital assistants and combination devices are providing increasing levels of functionality to support modern life including location based information services. Research and development in the existing technologies can take a myriad of different directions.

As users become more empowered with the growth of mobile location based service devices new and old paradigms begin to take advantage of this new device space. There are many technological solutions to take advantage of this new device location opportunity. One existing approach is to use location information to provide navigation services such as a global positioning system GPS for a car or on a mobile device such as a cell phone portable navigation device PND or a personal digital assistant PDA .

Location based services allow users to create transfer store and or consume information in order for users to create transfer store and consume in the real world . One such use of location based services is to efficiently transfer or route users to the desired destination or service.

Navigation systems and location based services enabled systems have been incorporated in automobiles notebooks handheld devices and other portable products. Today these systems aid users by incorporating available real time relevant information such as maps directions local businesses or other point of interest POI . The real time information provides invaluable relevant information. However a navigation system that cannot provide relevant notification that relates to the destination has become a paramount concern for the consumer.

Thus a need still remains for a navigation system with non native dynamic navigator mechanism that improves providing non native dynamic navigation to the destination. In view of the ever increasing commercial competitive pressures along with growing consumer expectations and the diminishing opportunities for meaningful product differentiation in the marketplace it is critical that answers be found for these problems. Additionally the need to reduce costs improve efficiencies and performance and meet competitive pressures adds an even greater urgency to the critical necessity for finding answers to these problems.

Solutions to these problems have been long sought but prior developments have not taught or suggested any solutions and thus solutions to these problems have long eluded those skilled in the art.

The present invention provides a method of operation of a navigation system including receiving a destination generating a route to the destination and generating a non native dynamic navigation based on the route for displaying on a device.

The present invention provides a navigation system including a destination selection module for receiving a destination a route generator module coupled to the destination selection module for generating a route to the destination and a non native dynamic navigation module coupled to the route generator module for generating a non native dynamic navigation based on the route for displaying on a device.

Certain embodiments of the invention have other steps or elements in addition to or in place of those mentioned above. The steps or elements will become apparent to those skilled in the art from a reading of the following detailed description when taken with reference to the accompanying drawings.

The following embodiments are described in sufficient detail to enable those skilled in the art to make and use the invention. It is to be understood that other embodiments would be evident based on the present disclosure and that system process or mechanical changes may be made without departing from the scope of the present invention.

In the following description numerous specific details are given to provide a thorough understanding of the invention. However it will be apparent that the invention may be practiced without these specific details. In order to avoid obscuring the present invention some well known circuits system configurations and process steps are not disclosed in detail.

The drawings showing embodiments of the system are semi diagrammatic and not to scale and particularly some of the dimensions are for the clarity of presentation and are shown exaggerated in the drawing FIGs. Similarly although the views in the drawings for ease of description generally show similar orientations this depiction in the FIGs. is arbitrary for the most part. Generally the invention can be operated in any orientation. The embodiments have been numbered first embodiment second embodiment etc. as a matter of descriptive convenience and are not intended to have any other significance or provide limitations for the present invention.

One skilled in the art would appreciate that the format with which navigation information is expressed is not critical to some embodiments of the invention. For example in some embodiments navigation information is presented in the format of X Y where X and Y are two ordinates that define the geographic location i.e. a position of a user.

In an alternative embodiment navigation information is presented by longitude and latitude related information. In a further embodiment of the present invention the navigation information also includes a velocity element including a speed component and a heading component.

The term relevant information referred to herein comprises the navigation information described as well as information relating to points of interest to the user such as local business hours of businesses types of businesses advertised specials traffic information maps local events and nearby community or personal information.

The term module referred to herein can include software hardware or a combination thereof in accordance with the context in which the term is used. For example the software can be machine code firmware embedded code and application software. Also for example the hardware can be circuitry processor computer integrated circuit integrated circuit cores a pressure sensor an inertial sensor a microelectromechanical system MEMS passive devices or a combination thereof.

Referring now to therein is shown a navigation system with non native dynamic navigator mechanism in an embodiment of the present invention. The navigation system includes a first device such as a client or a server connected to a second device such as a client or server with a communication path such as a wireless or wired network.

For example the first device can be of any of a variety of mobile devices such as a cellular phone personal digital assistant a notebook computer automotive telematic navigation system or other multi functional mobile communication or entertainment device. The first device can be a standalone device or can be incorporated with a vehicle for example a car truck bus or train. The first device can couple to the communication path to communicate with the second device .

For illustrative purposes the navigation system is described with the first device as a mobile computing device although it is understood that the first device can be different types of computing devices. For example the first device can also be a non mobile computing device such as a server a server farm or a desktop computer.

The second device can be any of a variety of centralized or decentralized computing devices. For example the second device can be a computer grid computing resources a virtualized computer resource cloud computing resource routers switches peer to peer distributed computing devices or a combination thereof.

The second device can be centralized in a single computer room distributed across different rooms distributed across different geographical locations embedded within a telecommunications network. The second device can have a means for coupling with the communication path to communicate with the first device . The second device can also be a client type device as described for the first device .

In another example the first device can be a particularized machine such as a mainframe a server a cluster server rack mounted server or a blade server or as more specific examples an IBM System z10 Business Class mainframe or a HP ProLiant ML server. Yet another example the second device can be a particularized machine such as a portable computing device a thin client a notebook a netbook a smartphone personal digital assistant or a cellular phone and as specific examples an Apple iPhone Palm Centro or Moto Q Global .

For illustrative purposes the navigation system is described with the second device as a non mobile computing device although it is understood that the second device can be different types of computing devices. For example the second device can also be a mobile computing device such as notebook computer another client device or a different type of client device. The second device can be a standalone device or can be incorporated with a vehicle for example a car truck bus or train.

Also for illustrative purposes the navigation system is shown with the second device and the first device as end points of the communication path although it is understood that the navigation system can have a different partition between the first device the second device and the communication path . For example the first device the second device or a combination thereof can also function as part of the communication path .

The communication path can be a variety of networks. For example the communication path can include wireless communication wired communication optical ultrasonic or the combination thereof. Satellite communication cellular communication Bluetooth Infrared Data Association standard IrDA wireless fidelity WiFi and worldwide interoperability for microwave access WiMAX are examples of wireless communication that can be included in the communication path . Ethernet digital subscriber line DSL fiber to the home FTTH and plain old telephone service POTS are examples of wired communication that can be included in the communication path .

Further the communication path can traverse a number of network topologies and distances. For example the communication path can include direct connection personal area network PAN local area network LAN metropolitan area network MAN wide area network WAN or any combination thereof.

Referring now to therein is shown an example of a display on a display interface of the first device . The display interface depicts a non native dynamic navigator in the context of a native application . The non native dynamic navigator makes a navigation session contained in a native application session possible which in turn let the user continue working with the native application without losing track of the native application session after the navigation session is done.

The non native dynamic navigator is defined as a zero install turn by turn navigation application architected to run in the native application . The non native dynamic navigator does not require interaction from the user to install and is not installed on the first device . Instead the non native dynamic navigator is delivered over to the first device and uses client side and server side processing to provide a non native dynamic navigation experience within a native application . The non native dynamic navigator is launched in the context of the native application at runtime without application installation for the non native dynamic navigator .

The native application is defined as an application that is either pre installed on device during manufacture or downloaded from various software distribution platforms and installed on the device. The native application can be a web browser a Microsoft Word and an Adobe Acrobat not originally designed for providing the navigation session . The computing system can run the non native dynamic navigator for providing the turn by turn navigation application through the native application without installing an instance of the turn by turn navigation application or without using an existing instance thereof.

The non native dynamic navigator receives a destination for representing a geographical location. This in turn initializes and loads navigation widget from a server and provides a navigation page after sufficient requirements for Authentication Authorization are met. The navigation system of having a non native dynamic navigator can be loaded in the context of many applications including Ads application publisher application and business review application. Staying within the native application session during the navigation session provides a good user experience that let user to go back to the original native application without losing track of it.

Once the user chooses to push start the navigation session the navigation system will guide the user to the destination by providing the non native dynamic navigation based on a current location and a route including a geographical route for providing real time guidance for the user in physically traversing along the geographical route to the destination the route calculated by the navigation system . Alerts are sent out for when configured geofence has been penetrated by the user.

Referring now to therein is shown example displays of the navigation system of on a display interface of the first device . depicts the non native dynamic navigator of in the context of an Ad Publisher context. In this context application developers can choose to display Mobile location sensitive Ad inside their mobile application or mobile web application.

The basic requirements of Turn by Turn navigation is the need to guide the user during the navigation session of using early warning signals with visual audio prompts prior to arriving at a location or ahead of time for performing a maneuver to follow the route of . The navigation system detects deviations from the route which in turn often guide users back to the destination of .

As an example the user that would intend to drive to the location of the Ad or event would be able to do so by clicking on the Drive To button or a link without leaving a browser session which is an example of the native application session of . This in turn initializes and loads navigation widget from a server provides a browser based dynamic navigation which is an example of the non native dynamic navigator after sufficient requirements for Authentication Authorization are met.

The browser based dynamic navigator can be loaded in the context of many applications including Ads application business review application. Staying within the browser session during the navigation session let user to go back to the original page in the browser which is an example of the native application of and can be using HTML5 technology.

Also for example the browser based dynamic navigator can be based on the HTML5 geolocation and Canvas using JavaScript as the dynamic scripting language. The browser based dynamic navigator is built to read a GPS location leverage an off board service to generate the route and provide the browser based dynamic navigation . By leveraging real time updates from the geolocation API the JavaScript based guidance engine running within the browser that is pre loaded into mobile platform can guide a user along a given path.

The client server communication between the first device and the second device of with the navigation system can be based on HTTP protocol REST and JSON technology. For example the Java Script Components of the browser based dynamic navigator can communicate with the server using HTTP protocol and REST based service invocations. JSON can be used for data interchange. The navigation system has the capability to switch between different interchange formats. The first device can have functionality to poll for data from the server or the second device and to be notified by the server or the second device .

Referring now to therein is shown an exemplary block diagram of the navigation system . The navigation system can include the first device the communication path and the second device . The first device can send information in a first device transmission over the communication path to the second device . The second device can send information in a second device transmission over the communication path to the first device .

For illustrative purposes the navigation system is shown with the first device as a client device although it is understood that the navigation system can have the first device as a different type of device. For example the first device can be a server.

Also for illustrative purposes the navigation system is shown with the second device as a server although it is understood that the navigation system can have the second device as a different type of device. For example the second device can be a client device.

For brevity of description in this embodiment of the present invention the first device will be described as a client device and the second device will be described as a server device. The present invention is not limited to this selection for the type of devices. The selection is an example of the present invention.

The first device can include a first control unit a first storage unit a first communication unit a first user interface and a location unit . The first device can be similarly described by the first device .

The first control unit can include a first control interface . The first control unit can execute a first software to provide the intelligence of the navigation system . The first control unit can be implemented in a number of different manners. For example the first control unit can be a processor an embedded processor a microprocessor a hardware control logic a hardware finite state machine FSM a digital signal processor DSP or a combination thereof. The first control interface can be used for communication between the first control unit and other functional units in the first device . The first control interface can also be used for communication that is external to the first device .

The first control interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the first device .

The first control interface can be implemented in different ways and can include different implementations depending on which functional units or external units are being interfaced with the first control interface . For example the first control interface can be implemented with a pressure sensor an inertial sensor a microelectromechanical system MEMS optical circuitry waveguides wireless circuitry wireline circuitry or a combination thereof.

The location unit can generate location information current heading and current speed of the first device as examples. The location unit can be implemented in many ways. For example the location unit can function as at least a part of a global positioning system GPS an inertial navigation system a cellular tower location system a pressure location system or any combination thereof.

The location unit can include a location interface . The location interface can be used for communication between the location unit and other functional units in the first device . The location interface can also be used for communication that is external to the first device .

The location interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the first device .

The location interface can include different implementations depending on which functional units or external units are being interfaced with the location unit . The location interface can be implemented with technologies and techniques similar to the implementation of the first control interface .

The first storage unit can store the first software . The first storage unit can also store the relevant information such as advertisements points of interest POI navigation routing entries or any combination thereof.

The first storage unit can be a volatile memory a nonvolatile memory an internal memory an external memory or a combination thereof. For example the first storage unit can be a nonvolatile storage such as non volatile random access memory NVRAM Flash memory disk storage or a volatile storage such as static random access memory SRAM .

The first storage unit can include a first storage interface . The first storage interface can be used for communication between the location unit and other functional units in the first device . The first storage interface can also be used for communication that is external to the first device .

The first storage interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the first device .

The first storage interface can include different implementations depending on which functional units or external units are being interfaced with the first storage unit . The first storage interface can be implemented with technologies and techniques similar to the implementation of the first control interface .

The first communication unit can enable external communication to and from the first device . For example the first communication unit can permit the first device to communicate with the second device of an attachment such as a peripheral device or a computer desktop and the communication path .

The first communication unit can also function as a communication hub allowing the first device to function as part of the communication path and not limited to be an end point or terminal unit to the communication path . The first communication unit can include active and passive components such as microelectronics or an antenna for interaction with the communication path .

The first communication unit can include a first communication interface . The first communication interface can be used for communication between the first communication unit and other functional units in the first device . The first communication interface can receive information from the other functional units or can transmit information to the other functional units.

The first communication interface can include different implementations depending on which functional units are being interfaced with the first communication unit . The first communication interface can be implemented with technologies and techniques similar to the implementation of the first control interface .

The first user interface allows a user not shown to interface and interact with the first device . The first user interface can include an input device and an output device. Examples of the input device of the first user interface can include a keypad a touchpad soft keys a keyboard a microphone or any combination thereof to provide data and communication inputs.

The first user interface can include a first display interface . The first display interface can include a display a projector a video screen a speaker or any combination thereof.

The first control unit can operate the first user interface to display information generated by the navigation system . The first control unit can also execute the first software for the other functions of the navigation system including receiving location information from the location unit . The first control unit can further execute the first software for interaction with the communication path via the first communication unit .

The second device can be optimized for implementing the present invention in a multiple device embodiment with the first device . The second device can provide the additional or higher performance processing power compared to the first device . The second device can include a second control unit a second communication unit and a second user interface .

The second user interface allows a user not shown to interface and interact with the second device . The second user interface can include an input device and an output device. Examples of the input device of the second user interface can include a keypad a touchpad soft keys a keyboard a microphone or any combination thereof to provide data and communication inputs. Examples of the output device of the second user interface can include a second display interface . The second display interface can include a display a projector a video screen a speaker or any combination thereof.

The second control unit can execute a second software to provide the intelligence of the second device of the navigation system . The second software can operate in conjunction with the first software . The second control unit can provide additional performance compared to the first control unit .

The second control unit can operate the second user interface to display information. The second control unit can also execute the second software for the other functions of the navigation system including operating the second communication unit to communicate with the first device over the communication path .

The second control unit can be implemented in a number of different manners. For example the second control unit can be a processor an embedded processor a microprocessor a hardware control logic a hardware finite state machine FSM a digital signal processor DSP or a combination thereof.

The second control unit can include a second controller interface . The second controller interface can be used for communication between the second control unit and other functional units in the second device . The second controller interface can also be used for communication that is external to the second device .

The second controller interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the second device .

The second controller interface can be implemented in different ways and can include different implementations depending on which functional units or external units are being interfaced with the second controller interface . For example the second controller interface can be implemented with a pressure sensor an inertial sensor a microelectromechanical system MEMS optical circuitry waveguides wireless circuitry wireline circuitry or a combination thereof.

A second storage unit can store the second software . The second storage unit can also store the relevant information such as advertisements points of interest POI navigation routing entries or any combination thereof. The second storage unit can be sized to provide the additional storage capacity to supplement the first storage unit .

For illustrative purposes the second storage unit is shown as a single element although it is understood that the second storage unit can be a distribution of storage elements. Also for illustrative purposes the navigation system is shown with the second storage unit as a single hierarchy storage system although it is understood that the navigation system can have the second storage unit in a different configuration. For example the second storage unit can be formed with different storage technologies forming a memory hierarchal system including different levels of caching main memory rotating media or off line storage.

The second storage unit can be a volatile memory a nonvolatile memory an internal memory an external memory or a combination thereof. For example the second storage unit can be a nonvolatile storage such as non volatile random access memory NVRAM Flash memory disk storage or a volatile storage such as static random access memory SRAM .

The second storage unit can include a second storage interface . The second storage interface can be used for communication between the location unit and other functional units in the second device . The second storage interface can also be used for communication that is external to the second device .

The second storage interface can receive information from the other functional units or from external sources or can transmit information to the other functional units or to external destinations. The external sources and the external destinations refer to sources and destinations external to the second device .

The second storage interface can include different implementations depending on which functional units or external units are being interfaced with the second storage unit . The second storage interface can be implemented with technologies and techniques similar to the implementation of the second controller interface .

The second communication unit can enable external communication to and from the second device . For example the second communication unit can permit the second device to communicate with the first device over the communication path .

The second communication unit can also function as a communication hub allowing the second device to function as part of the communication path and not limited to be an end point or terminal unit to the communication path . The second communication unit can include active and passive components such as microelectronics or an antenna for interaction with the communication path .

The second communication unit can include a second communication interface . The second communication interface can be used for communication between the second communication unit and other functional units in the second device . The second communication interface can receive information from the other functional units or can transmit information to the other functional units.

The second communication interface can include different implementations depending on which functional units are being interfaced with the second communication unit . The second communication interface can be implemented with technologies and techniques similar to the implementation of the second controller interface .

The first communication unit can couple with the communication path to send information to the second device in the first device transmission . The second device can receive information in the second communication unit from the first device transmission of the communication path .

The second communication unit can couple with the communication path to send information to the first device in the second device transmission . The first device can receive information in the first communication unit from the second device transmission of the communication path . The navigation system can be executed by the first control unit the second control unit or a combination thereof.

For illustrative purposes the second device is shown with the partition having the second user interface the second storage unit the second control unit and the second communication unit although it is understood that the second device can have a different partition. For example the second software can be partitioned differently such that some or all of its function can be in the second control unit and the second communication unit . Also the second device can include other functional units not shown in for clarity.

The functional units in the first device can work individually and independently of the other functional units. The first device can work individually and independently from the second device and the communication path .

The functional units in the second device can work individually and independently of the other functional units. The second device can work individually and independently from the first device and the communication path .

For illustrative purposes the navigation system is described by operation of the first device and the second device . It is understood that the first device and the second device can operate any of the modules and functions of the navigation system . For example the first device is described to operate the location unit although it is understood that the second device can also operate the location unit .

Referring now to therein is shown a control flow of the navigation system . The navigation system can include a destination selection module . The destination selection module receives the destination for the navigation session of .

The navigation system can also include a navigation sharing module coupled to the destination selection module . The navigation sharing module shares an embedded navigation for driving to the destination using the non native dynamic navigation . The embedded navigation is defined as an activation feature for invoking the navigation session with the non native dynamic navigation . Examples of the embedded navigation can be a link a browser widget or an activation button. The navigation sharing module can be coupled to the route generator module . The process of the navigation sharing module will be detailed later in the specification.

The navigation system can also include a route generator module coupled to the destination selection module . The route generator module generates the route to the destination selected and regenerates the route from a new origin to the destination when a deviation is detected.

The navigation system can also include a non native dynamic navigation module coupled to the route generator module . The non native dynamic navigation module generates the non native dynamic navigation including a visual guidance an audio guidance or a combination thereof based on the route from the route generator module or from the embedded navigation that can include the route .

The non native dynamic navigation module can include a navigation display generator module coupled to the route generator module . The navigation display generator module generates the visual guidance to guide user to the destination . The process of the navigation display generator module will be detailed later in the specification.

The non native dynamic navigation module can also include a navigation audio generator module coupled to the route generator module . The navigation audio generator module generates the audio guidance to guide user to the destination . The process of the navigation audio generator module will be detailed later in the specification.

The navigation system can also include a hybrid deviation detection module coupled to the non native dynamic navigation module . The hybrid deviation detection module detects the deviation from the route using the first device of and the second device of which can determine a new origin to re route to the destination . Otherwise the non native dynamic navigator of would continue guiding the user along the route to the destination . The process of the hybrid deviation detection module will be detailed later in the specification.

The destination selection module can be implemented by the navigation system . The destination selection module can be implemented with the first control unit of and can make use of the first software of the first storage unit of the first communication unit of or some combination thereof. For example the destination selection module can receive the destination and store the destination in the first storage unit by utilizing the first control unit .

For illustrative purposes the destination selection module is described as being implemented by the first control unit with values being stored in the first storage unit although it is understood that the destination selection module can be implemented differently. For example the destination selection module can be implemented by the second control unit of with the destination being stored in the second storage unit of . Also for example the second control unit can generate the destination and use the second communication unit of to send the destination to the first storage unit .

The navigation sharing module can be implemented by the navigation system . The navigation sharing module can be implemented with the first control unit and can make use of the first software the first storage unit the first communication unit or some combination thereof. For example the navigation sharing module can receive the destination and store them in the first storage unit by utilizing first control unit .

For illustrative purposes the navigation sharing module is described as being implemented by the first control unit although it is understood that the navigation sharing module can be implemented differently. For example the navigation sharing module can utilize the second control unit to operate the second software of FIG. to generate the embedded navigation . Also for example the second control unit can operate the second communication unit to transmit the embedded navigation to the second storage unit .

The route generator module can be implemented by the navigation system . The route generator module can be implemented by the second control unit and can make use of the second storage unit the second software the second communication unit or some combination thereof.

For example the route generator module can receive the destination from the second communication unit and store the destination in the second storage unit by utilizing the second control unit . The route generator module can also utilize the second control unit to operate the second software to generate the route and store the route in the second storage unit .

For illustrative purposes the route generator module is described as being implemented by the second control unit although it is understood that the route generator module can be implemented differently. For example the route generator module can utilize the first control unit retrieve the destination from the first storage unit . The route generator module can utilize the first control unit to control the first software to operate the first communication unit and transit the destination to the second storage unit .

The non native dynamic navigation module can be implemented by the navigation system . The non native dynamic navigation module can be implemented with the first control unit and can make use of the first software the first storage unit the first communication unit or some combination thereof. For example the non native dynamic navigation module can receive the route and store the route in the first storage unit by utilizing the first control unit .

The non native dynamic navigation module can use the first communication unit to receive the route from the second software which can be implemented by the second control unit and then store the route in the first storage unit . The non native dynamic navigation module can utilize the first control unit to operate the first software to generate the non native dynamic navigation including the visual guidance and the audio guidance for displaying on the first device of .

For illustrative purposes the non native dynamic navigation module is described as being implemented by the first control unit with values being stored in the first storage unit although it is understood that the non native dynamic navigation module can be implemented differently. For example the non native dynamic navigation module can be implemented by the second control unit with the route and the destination being stored in the second storage unit . Also for example the second control unit can generate the non native dynamic navigation and use the second communication unit to send the non native dynamic navigation to the first storage unit .

The hybrid deviation detection module can be implemented by the navigation system . The hybrid deviation detection module can be implemented with the first control unit and can make use of the first software the first storage unit the first communication unit or some combination thereof.

For example the hybrid deviation detection module can receive the route from the non native dynamic navigation module and store the route in the first storage unit by utilizing the first control unit . Also for example the hybrid deviation detection module can utilize the first control unit to operate the first software to determine the deviation based on the current location of and the route .

For illustrative purposes the hybrid deviation detection module is described as being implemented by the first control unit although it is understood that the hybrid deviation detection module can be implemented differently. For example the hybrid deviation detection module can utilize the second control unit to retrieve the route from the second storage unit . The hybrid deviation detection module can utilize the second control unit to control the second software to operate the second display interface of to display the deviation and prompt the user about re route.

It has been discovered that the non native dynamic navigation the visual guidance the audio guidance and the non native dynamic navigation module provide a zero install solution. There is no need for software version control or software compatibility with other applications and type of operating system the software is running on.

The modules can be implemented with hardware implementations including hardware acceleration units not shown in the first control unit or the second control unit or separate hardware blocks not shown functional units not shown in the first device or the second device of outside the first control unit and the second control unit .

Referring now to therein is shown a control flow of the navigation sharing module . The navigation sharing module generates the embedded navigation by embedding a shared navigation in a sharing format or within an application and shares the embedded navigation with other user. The navigation sharing module can be implemented with HTML5 JavaScript and Java technology.

The navigation sharing module shares the embedded navigation with the other user through internet. When the other user clicks the embedded navigation to invoke the shared navigation embedded in the sharing format or within the application the non native dynamic navigation of is launched in the context of the native application of at runtime without separate installation and the non native dynamic navigation is executed from within the native application session of . For example the sharing format can be a short message service SMS an electronic mail e mail a hyperlink or a combination thereof. Also for example the application can be Facebook Twitter or Linkedin .

The navigation sharing module can include a shared navigation generator module coupled to the destination selection module of . The shared navigation generator module generates the shared navigation based on the non native dynamic navigator of and the destination of .

The shared navigation is defined as a specific character string that constitutes information about the destination and the non native dynamic navigator . When the user clicks the shared navigation the non native dynamic navigation is launched in the native application . For example the shared navigation can include a uniform resource locator URL or a link to the non native dynamic navigator address of the destination latitude and longitude of the destination or a combination thereof.

The navigation sharing module can also include an embedded navigation module coupled to the shared navigation generator module . The embedded navigation module generates the embedded navigation by embedding the shared navigation in the sharing format or within the application .

The navigation sharing module can also include a share drive to module coupled to the embedded navigation module . The share drive to module shares the embedded navigation with the other user for driving to the destination using the non native dynamic navigation .

It has been discovered that the embedded navigation and the share drive to module provide faster communication time by sending only the activation feature for invoking the non native dynamic navigation . It has also been discovered that the sharing format the application the embedded navigation improve user experience by sharing the embedded navigation with friends in various way.

Referring now to therein is shown a control flow of the navigation display generator module . The navigation display generator module generates the visual guidance to guide the user during the navigation session of with visual prompts ahead of time. The navigation display generator module can be implemented with HTML5 geolocation and canvas JavaScript and Java technology.

The navigation display generator module can include a route drawing module coupled to the route generator module of . The route drawing module receives a map image generates a map view using a tile based scheme based on the map image and an image layer and dynamically draws the route on the top of the map view .

For example the HTML5 canvas element can be used by the non native dynamic navigator of to plot the map view on the browser screen or the native application of which in turn helps to plot the route and the current location on the top of the map view .

Also for example the map view can constitute the image layer and the map view can be imposed with a base maps layer a decoration layer a traffic layer and a controls layer. The process of drawing the base maps layer is based on the map image by using the tile based scheme . The map image is defined as an image without any map attributes roads coordinates point of interest information and retrieved based on the current zoom level from the second device of using communication mechanism.

It has been discovered that the map image provides faster communication time between the first device and the second device by using the map image which is light weighted and has no map attributes roads coordinates point of interest information. The map image also provides decreased storage space and faster execution time when loaded into the native application .

The navigation display generator module can include a position watch module coupled to the route drawing module . The position watch module determines the current location of the first device of by using a route matching based on the route and a location watch threshold .

For example the current location can be determined using HTML5 single point geolocation the route and the location watch threshold . The latitude and longitude can be available to JavaScript on the page displaying the map image and the route . The second device can provide other map attributes not found in the map image and examples of other map attributes include location aware items such as finding local businesses or showing location information. The geolocation can be a single point geolocation determined by HTML5 geolocation the location watch threshold can be a radius in meters.

The position watch module can include an initial location module . The initial location module generates an initial location that is the single point location using geolocation.

The initial location perhaps cannot be used directly for navigation due to inconsistencies with several measurements sent by the native application . The inconsistencies generated by the native application include accuracy of the geolocation heading to direction and speed of the first device .

The position watch module can also include a location watch module coupled to the initial location module . The location watch module generates the current location by using the route matching based on the route and the location watch threshold . The initial location is filtered and optimized through a number of different ways and the current location generated by the location watch module is sent to the respective components of the non native dynamic navigator of .

The location watch module can leverage a number of different elements in its context to deliver an accurate representation of the user s current location . The location sensors such as the location unit can have an inherent characteristic of error that may be significant especially in the context of a navigation solution. While the platform location applications themselves provide precision capabilities it does not necessarily reflect accuracy they may be inaccurate by upwards of several 100 meters. Several hundred meter inaccuracies can lead to a very poor navigation implementation including inaccurate positioning that may lead to false route deviations and rerouting invalid triggering of guidance events and inaccurate route generation.

To address these concerns the Location Watch Module leverages several unique insights to be able to leverage a low accuracy location position for a navigation solution that requires high precision. For example the location watch module can first filter the initial location based on the distance between two fixed locations and a logical speed at which a vehicle could travel between the two fixed locations. Second the location watch module can filter the initial location and heading of the navigation system by using multiple fixed locations. Third the location watch module can further filter the initial location by associating the initial location with the map image .

The route matching is defined as the mechanism that match the current location with single point geolocation to the route when the distance between the current location and the route is less than the location watch threshold . For example if the position change is detected the current location can be sent to components of the browser based dynamic navigator of or more generally the non native dynamic navigator such as a dead reckoning module a heading up module and the hybrid deviation detection module of .

The navigation display generator module can also include the dead reckoning module coupled to the position watch module . The dead reckoning module generates the visual guidance using a simulated dead reckoning for a poor positioning service location .

The poor positioning service location can include a position with a poor accuracy of the positioning service signal a position with infrequent position update or a combination thereof. For example the poor accuracy of the positioning service signal can be greater than 1000 meters which makes the location with poor accuracy of the positioning service signal a coarse range location. For another example typical position update is in every 1 second but the infrequent position update can be in a period as long as 2 minutes 10 minutes or even longer.

The simulated dead reckoning is defined as a process of determining a previous location by assigning the current location to the previous location and calculating the current location by using the previous location and advancing the previous location based on a driver speed or a road speed when the driver speed is not available over an elapsed time and the route . The non native dynamic navigator can predict where the user is on the road every 1 second using the simulated dead reckoning .

The navigation display generator module can also include the heading up module coupled to the position watch module . The heading up module generates the visual guidance with heading up by rotating the map image based on the current location and the route . For example the non native dynamic navigator can use Canvas to get map rotation and HTML5 geolocation to get the current location . The visual guidance with heading up let the user has a better driving experience than the traditional north up map.

Referring now to therein is shown a control flow of the navigation audio generator module . The navigation audio generator module generates the audio guidance at real time to play and orchestrates a series of events that need to happen before maneuvers to navigate the user to the destination . The navigation audio generator module can be implemented with HTML5 JavaScript and Java technology.

For example the HTML5 Specification has furnished a way for web applications to play media with video and audio tags. The Navigation client extends the use of this feature for various platforms. Some platforms for the first device of only allow the audio guidance to play once. The navigation system of has work around to support audio playback during the navigation session of .

The navigation audio generator module can include an audio guidance module coupled to the route generator module of . The audio guidance module generates the audio guidance by combining the information from an audio rule a timing rule the current location the map image and the route .

The audio rule is defined as a rule that concatenates a turn and a distance related audio bytes based on rules in many formats. For example the audio rule can be in MP3 or OGG format for efficient streaming and manipulation of high quality digital multimedia.

The timing rule is defined as the rule that controls when to play the audio guidance based on back and forth delay which is about a few seconds between first device and second device of the length of the audio guidance the position prediction the distance difference between highway and local road to have enough time to play the audio guidance .

The navigation audio generator module can also include an audio playback module coupled to the audio guidance module . The audio playback module updates an audio source multiple times by assigning the audio guidance frequently.

For example the audio playback module generates work round to fix the playing once problem from android based smartphone such as iPhone by frequently swapping the audio source and triggering audio event to play the audio guidance multiple times based on the current location and the timing rule . The playing once problem is caused by the issue that native audio tag in HTML5 can only play once.

The navigation audio generator module can also include an audio player module coupled to the audio playback module . The audio player module prompts the audio guidance multiple times by triggering the audio source ahead of time to navigate the user to the destination selected.

For example there can be three prompts including an information prompt a preparation prompt and a play prompt that happen before the user actually makes a turn. The information prompt can happen a few miles before the user next turn. The preparation prompt can happen 0.1 mile before the user next turn and is to warn the user that the turn is going to happen soon. The play prompt is for a turn happening right now.

Referring now to therein is shown a control flow of the hybrid deviation detection module . The hybrid deviation detection module determines the deviation from the route by using the first device of and the second device of and generates the new origin to re route to the destination of when the deviation is detected. Otherwise the navigation system of would guide the user to the destination through the navigation session of . The hybrid deviation detection module can be implemented with HTML5 JavaScript and Java technology.

The hybrid deviation detection module can include the position watch module coupled to the non native dynamic navigation module of . The position watch module generates the current location for the navigation system using the route matching and generates the new origin by assigning the current location when the deviation is detected.

The hybrid deviation detection module can also include an on board deviation detection module coupled to the position watch module . The on board deviation detection module monitors the current location and the route being overlaid onto the map image which is stored on board and detects an on board deviation when the distance from the current location to the route is more than the location watch threshold of . The map image stored on the first device can be retrieved from the second device but the map image does not contain as much information as a server map which includes map attributes roads coordinates point of interest information. It is understood that the error size of the on board deviation can be in meters.

The hybrid deviation detection module can also include an off board deviation detection module coupled to the on board deviation detection module . The off board deviation detection module detects the deviation using a map matching based on the server map which is off board the current location and the route when the on board deviation is detected.

The map matching is defined as a mechanism that determines the deviation when the current location is not on the correct road of the server map based on the route . For example if the on board deviation is detected which in turn can request the off board deviation detection module to further check using the map matching based on the server map because the on board information about the map image is incomplete. The off board deviation detection module can determine that the on board deviation is false because there is no road on the server map for the current location .

It has been discovered that the map image the on board deviation detection module the server map and the off board deviation detection module provide route reliability and accuracy for the navigation system by improving the accuracy of the deviation detected and re routing to the destination . This in turn provides safety for the user to drive.

It has also been discovered that the non native dynamic navigation of provides an efficient and easy mechanism that runs within the native application session of enabling the Drive To experience for end users by providing a unique low cost zero install and easy to integrate solution. This technology also improves user experience by running the navigation session within the native application session . The user can keep track of the native application after the navigation session is done.

The physical transformation from displaying the non native dynamic navigation results in movement in the physical world such as people using the first device the vehicle or a combination thereof based on the operation of the navigation system . As the movement in the physical world occurs the movement itself creates additional information that is converted back to the current location for the continued operation of the navigation system and to continue the movement in the physical world.

The navigation system describes the module functions or order as an example. The modules can be partitioned differently. For example the destination selection module of and the navigation sharing module of can be combined. Each of the modules can operate individually and independently of the other modules.

Furthermore data generated in one module can be used by another module without being directly coupled to each other. For example the hybrid deviation detection module can receive the route from the route generator module of .

Referring now to therein is shown a flow chart of a method of operation of the navigation system of in a further embodiment of the present invention. The method includes receiving a destination in a block generating a route to the destination in a block and generating a non native dynamic navigation based on the route for displaying on a device in a block .

The resulting method process apparatus device product and or system is straightforward cost effective uncomplicated highly versatile accurate sensitive and effective and can be implemented by adapting known components for ready efficient and economical manufacturing application and utilization. Another important aspect of the present invention is that it valuably supports and services the historical trend of reducing costs simplifying systems and increasing performance. These and other valuable aspects of the present invention consequently further the state of the technology to at least the next level.

While the invention has been described in conjunction with a specific best mode it is to be understood that many alternatives modifications and variations will be apparent to those skilled in the art in light of the foregoing description. Accordingly it is intended to embrace all such alternatives modifications and variations that fall within the scope of the included claims. All matters hithertofore set forth herein or shown in the accompanying drawings are to be interpreted in an illustrative and non limiting sense.

