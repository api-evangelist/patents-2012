---

title: Information processing apparatus, information processing system, and device linkage method
abstract: An information processing apparatus includes a user interface unit configured to receive a function execution request for processes, the function execution request containing designations of an input function and an output function; a search and linkage unit configured to acquire pieces of specifications information indicating functions of an input device and an output device from the respective devices, and generate, based on the pieces of specifications information, a linkage flow indicating an execution sequence and a combination of an input device and an output device which respectively have an input function and an output function designated in the function execution request, the devices executing the functions, respectively, in linkage with each other; and a flow executing unit configured to send process requests to the input device and the output device designated in the linkage flow, respectively.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09069516&OS=09069516&RS=09069516
owner: RICOH COMPANY, LIMITED
number: 09069516
owner_city: Tokyo
owner_country: JP
publication_date: 20120314
---
The present application claims priority to and incorporates by reference the entire contents of Japanese Patent Application No. 2011 061366 filed in Japan on Mar. 18 2011 and Japanese Patent Application No. 2012 040730 filed in Japan on Feb. 27 2012.

The present invention relates to an information processing apparatus an information processing system and a device linkage method.

Conventionally to enable linkage between an image forming apparatus and an input output device other than the image forming apparatus there is a method of developing an embedded application by using a software development kit SDK that is provided for developing applications to be installed in the image forming apparatus.

Japanese Patent No. 4403138 and Japanese Patent No. 4403139 disclose another method in which an interface that can control functions of an image forming apparatus is provided in advance in the image forming apparatus to configure an application that enables linkage between the image forming apparatus and the other input output devices by an external server or the like.

However in recent years there is a demand to enable linkage between an image forming apparatus and an input output device other than the image forming apparatus as well as linkage among an image forming apparatus an input output device and a service on a cloud computer. Furthermore a linkage object may be changed dynamically.

Therefore there is a need for a platform that enables not only linkage between an image forming apparatus and other devices but also linkage between various input output devices in offices or between input output devices and cloud services etc. and to easily enable linkage by developing an application on the platform.

It is an object of the present invention to at least partially solve the problems in the conventional technology.

According to an embodiment there is provided an information processing apparatus connected to at least one input device and at least one output device via a network. The information processing apparatus includes a user interface unit configured to receive a function execution request for a plurality of processes the function execution request containing designations of an input function and an output function a search and linkage unit configured to acquire pieces of specifications information indicating functions of the at least one input device and the at least one output device from the respective devices and generate based on the pieces of specifications information a linkage flow indicating an execution sequence and a combination of an input device having the input function designated in the function execution request and an output device having an output function designated in the function execution request among the at least one input device and the at least one output device the input device and the output device executing the input function and the output function respectively in linkage with each other and a flow executing unit configured to send process requests to the input device and the output device designated in the linkage flow respectively.

According to another embodiment there is provided an information processing system that includes the information processing apparatus according to the above embodiment the at least one input device the at least one output device and an operation terminal. The operation terminal includes a device searching unit configured to search for the input device and the output device to establish an ad hoc network connection with the input device and the output device obtained by search and to receive pieces of identification information for identifying the input device and the output device from the input device and the output device that have established the ad hoc network connection respectively and an execution requesting unit configured to send function execution requests for executing functions of the input device and the output device respectively to the information processing apparatus based on the pieces of designation information. The information processing apparatus receives the function execution requests and causes the input device and the output device corresponding respectively to the pieces of identification information designated in the function execution requests to execute the respective functions.

According to still another embodiment there is provided an information processing system that includes the information processing apparatus according to the above embodiment referred to as a first information processing apparatus the network being referred to as a first network and a second information processing apparatus connected to the first information processing apparatus in a second network. The first information processing apparatus includes a client unit configured to send the pieces of specifications information obtained by the specifications managing unit to the second information processing apparatus and a device operating unit configured to causes the input device to execute the corresponding input function and causes the output device to execute the corresponding input function in response to a request received from the second information processing apparatus. The second information processing apparatus includes a storage unit a managing unit configured to receive the pieces of specifications information and store the received pieces of specifications information in the storage unit a user interface unit configured to receive a function execution request for one or more processes the function execution request containing designations of an input function and an output function via an operation terminal connected to the second network and a linkage unit configured to generate based on the pieces of specifications information stored in the storage unit a linkage flow indicating an execution sequence and a combination of an input device having the input function designated in the function execution request and an output device having an output function designated in the function execution request among the at least one input device and the at least one output device the input device and the output device executing the input function and the output function respectively in linkage with each other. The managing unit of the second information processing apparatus sends process requests to the input device and the output device designated in the linkage flow respectively to the first information processing apparatus.

According to still another embodiment there is provided an information processing system that includes at least one input output device and an operation terminal. The operation terminal includes a device searching unit configured to search for the input output device to establish an ad hoc network connection with the input output device obtained by search and to receive a command to execute the function by the input output device from the input output device that has established the ad hoc network connection and an execution requesting unit configured to issue the command to the input output device. The input output device sends the command to the operation terminal when receiving a request to provide the command from the operation terminal and executes the function when receiving the command from the operation terminal.

According to still another embodiment there is provided a device linkage method implemented by an information processing apparatus connected to at least one input device and at least one output device via a network. The device linkage method includes receiving a function execution request for a plurality of processes the function execution request containing designations of an input function and an output function acquiring pieces of specifications information indicating functions of the at least one input device and the at least one output device from the respective devices generating based on the pieces of specifications information a linkage flow indicating an execution sequence and a combination of an input device having the input function designated in the function execution request and an output device having an output function designated in the function execution request among the at least one input device and the at least one output device the input device and the output device executing the input function and the output function respectively in linkage with each other and sending process requests to the input device and the output device designated in the linkage flow respectively.

The above and other objects features advantages and technical and industrial significance of this invention will be better understood by reading the following detailed description of presently preferred embodiments of the invention when considered in connection with the accompanying drawings.

Exemplary embodiments of an information processing apparatus an information processing system a device linkage method and a computer program product according to the present invention will be explained in detail below with reference to the accompanying drawings.

The operation terminal is a terminal that receives input of a function execution request for a desired input function and a desired output function from a user and transmits the request to the information processing apparatus via the network. Examples of the operation terminal include but not limited to a personal computer PC and a mobile terminal.

The information processing apparatus functions as a platform that receives the function execution request from the operation terminal generates a linkage flow in which a combination of an input device and an output device for executing the functions and an execution sequence are defined and causes the input device and the output device to execute the functions in accordance with the linkage flow. Examples of the information processing apparatus include but not limited to a computer including a server device a workstation and a PC an image forming apparatus including an MFP and a copier an information projecting apparatus including a projector and a mobile terminal including a mobile phone a personal data assistance PDA and a tablet terminal.

Each of the MFP and the projector serves as an input device or an output device executes own input function or output function receives a request from the information processing apparatus and transmits specifications information indicating own executable function to the information processing apparatus . Hereinafter the word of specifications is represented as SPECS in the drawings.

Examples of the specifications information include an input data format an output data format and resolution. The specifications information varies depending on the devices. Details of the specifications information will be described later. In the present embodiment each of the MFP and the projector can serve as an input device or an output device.

As illustrated in the information processing apparatus is partitioned into an upper layer and a lower layer by an application programming interface API as a boundary. The upper layer includes a user interface unit hereinafter described as the UI unit and a flow execution application .

The UI unit receives a function execution request for an input function and an output function from the operation terminal . In the present embodiment the function execution request contains designations of an input function an output function an input device that executes the input function and an output device that executes the output function as desired by a user. For example the function execution request may be scan the MFP projection the projector .

Specifically scan indicates the input function and the MFP indicates the input device that executes the input function scan . Similarly projection indicates the output function and the projector indicates the output device that executes the output function projection . To identify the input device that executes the input function and the output device that executes the output function IP addresses for identifying the respective devices are used however it is not limited to this.

The flow execution application receives the function execution request from the UI unit sends a linkage flow generation request to a service linkage unit of a device search service linkage unit by using the API and receives a linkage flow hereinafter also described as a flow generated by the service linkage unit .

The flow execution application sends a request for an input process to the input device and sends a request for an output process to the output device by using the API in accordance with the received linkage flow.

The API can receive the flow generation request the request for the input process and the request for the output process from the flow execution application by using a predefined function in which a parameter or the like is specified. When receiving the flow generation request by using the function the API sends the flow generation request to the service linkage unit to cause the service linkage unit to generate a flow. When receiving the requests for the input process and the output process by using the function the API sends a process execution request for each of the processes to a device operating unit to cause the device operating unit to control the input device and the output device.

On the upper layer above the API various applications not illustrated can be installed in addition to the flow execution application. The various applications can request execution of functions to enable linkage between services provided by the API by using a function call defined by the API.

In other words the API and the lower layer below the API serve as a platform for service linkage between applications including the flow execution application . Details of the API will be explained in a second embodiment to be described later.

The information processing apparatus mainly includes in the lower layer below the API the device search service linkage unit including the service linkage unit the device operating unit and a storage unit .

The service linkage unit requests the input device and the output device which are designated in the function execution request to provide pieces of specifications information and receives the pieces of specifications information from the input device and the output device. The service linkage unit generates based on the pieces of specifications information a linkage flow indicating an execution sequence and a combination of an input device and an output device that respectively have the input function and the output function designated in the function execution request and that can execute the input function and the output function in linkage with each other.

Specifically the service linkage unit generates based on the specifications information a linkage flow in which the input device and the output device designated in the function execution request sent by a user are identified and a parameter that is needed to execute the functions by linkage between the input device and the output device is also identified. Thereafter the service linkage unit sends the linkage flow as a response to the flow execution application .

Examples of the parameter needed to execute the functions by linkage of the input device and the output device include a data format that is commonly used as an output data format of the input device and an input data format of the output device and an execution sequence for the input device and the output device.

Therefore the flow execution application can execute the input function and the output function in a linkage manner by only sending the parameter of the linkage flow generated by the service linkage unit to the device operating unit by using the API without regard to a process of causing the devices to link each other.

A concrete example of a device linkage process of the present embodiment with the above configuration will be explained below. is a sequence diagram of the linkage process of the first embodiment. An example is explained in which a user inputs the function execution request for scan the MFP projection the projector in the operation terminal .

Referring back to the operation terminal transmits the function execution request for scan the MFP projection the projector which is specified by the user via the input screen to the information processing apparatus Step S .

The UI unit of the information processing apparatus receives the function execution request and sends to the flow execution application a flow generation request containing an input function scan an output function projection the IP address of the input device the MFP the IP address of the output device the projector and a parameter e.g. an input attribute such as monochrome color or a projection attribute as designated in the function execution request Step S . The flow execution application sends the flow generation request to the service linkage unit by using the API Step S .

When receiving the flow generation request from the flow execution application the service linkage unit sends a specifications information acquisition request to each of the MFP and the projector designated in the flow generation request Steps S and S and acquires specifications information from each of the devices Steps S and S .

The service linkage unit generates a linkage flow based on the specifications information Step S . In this example the specifications information of the MFP is denoted by in and the specifications information of the projector is denoted by in . illustrates a comparative table of the specifications information of the MFP and the projector .

In the example illustrated in and the specifications information of the MFP indicates that the output format is JPEG or TIFF while the specifications information of the projector indicates that the input format is JPEG . In this case the service linkage unit generates a linkage flow for the MFP and the projector by configuring a parameter so that the MFP outputs JPEG data through scanning. An exemplary linkage flow generated in this example is denoted by .

As denoted by the linkage flow contains a designated function call Scan for the input function provided with the IP address of the input device the MFP a scan attribute a designation of color monochrome fullcolor an output data format JPEG and a comment on the input device the MFP as parameters and contains a designated function call Projection for the output function provided with the IP address of the output device the projector a projection attribute and a comment on the output device the projector as parameters in an execution sequence.

Specifically the function Scan for the input function and the function Projection for the output function provided by the API are written in the linkage flow together with the parameters.

When the service linkage unit determines that the input device and the output device cannot link each other as a result of comparison of the specifications information the service linkage unit returns an error indicating the impossibility of linkage to the flow execution application . The flow execution application notifies the operation terminal of the error indicating the impossibility of linkage via the UI unit .

Subsequently the flow execution application calls the functions designated in the linkage flow by using the API. Therefore it becomes possible to enable linkage between the MFP and the projector without regard to a change in the parameters for a process of causing the MFP and the projector to link each other.

Specifically the flow execution application calls the function Scan for the input function with the specified parameters by referring to the received linkage flow and sends a request for an input process to the device operating unit by using the API Step S . The request for the input process contains scan as the input function parameters for specifying color monochrome fullcolor and the output data format JPEG and the IP address of the input device the MFP .

When receiving the request for the input process the device operating unit sends a process execution request to the input device the MFP designated in the request for the input process Step S . When receiving a notice of completion of the process from the input device the MFP Step S the device operating unit stores the notice of completion and the received scanned image data in the storage unit . The device operating unit then sends file information indicating a location of the scanned image data to the flow execution application Step S .

When receiving the file information the flow execution application calls the function Projection of the output function registered in the linkage flow by specifying the file information as a parameter and sends a request for an output process to the device operating unit by using the API Step S . The request for the output process contains projection as the output function a parameter such as the file information and the IP address of the output device the projector .

When receiving the request for the output process the device operating unit sends a process execution request to the output device the projector designated in the request for the output process Step S . When receiving a notice of completion of the process from the output device the projector Step S the device operating unit sends the notice of completion to the flow execution application Step S . The notice of completion is sent from the flow execution application to the UI unit and is subsequently sent from the UI unit to the operation terminal Steps S and S .

As described above according to the present embodiment when a function execution request relating to input and output is received from a user the service linkage unit acquires specifications information from the input device and the output device designated in the function execution request and when the linkage is possible based on the specifications information generates a linkage flow. Subsequently the flow execution application sends process execution requests to the input device and the output device based on the linkage flow. Therefore even if the user does not know the specifications of the input device and the output device it is possible to enable linkage between the input device and the output device to perform a desired input output process. It is also possible to easily cause the input device and the output device to link each other.

Furthermore according to the present embodiment the flow execution application sends the flow generation request to the service linkage unit by using the API and sends execution requests for the input process and the output process to the device operating unit by using the API. Therefore it is possible to easily enable linkage between the input device and the output device without regard to a change in the parameters for a process of causing the input device and the output device to link each other.

In the first embodiment the IP addresses of the input device and the output device are designated in the function execution request that is sent by a user via the operation terminal . In a second embodiment linkage becomes possible even when a user sends a function execution request without designations of an input device and an output device.

The operation terminal the MFP and the projector have the same functions as described in the first embodiment. The projector has different specifications functions from that of the projector .

As illustrated in the information processing apparatus includes the UI unit a flow execution application and an application in an upper layer above the API. The information processing apparatus mainly includes a device search service linkage unit the device operating unit and the storage unit in a lower layer below the API.

The UI unit the device operating unit and the storage unit have the same functions and configurations as described in the first embodiment.

In the present embodiment the UI unit receives a function execution request for an input function and an output function from the operation terminal however the function execution request contains designations of an input function and an output function as desired by a user but does not contain designations of an input device that executes the input function and an output device that executes the output function. For example the function execution request of the present embodiment may be scan projection . Here scan is a designation of the input function and projection is a designation of the output function.

The flow execution application receives the function execution request from the UI unit sends a linkage flow generation request to a service linkage unit of the device search service linkage unit by using the API and receives a linkage flow generated by the service linkage unit . The flow execution application sends a request for an input process to the input device and sends a request for an output process to the output device by using the API in accordance with the received linkage flow.

The device search service linkage unit mainly includes the service linkage unit and a device searching unit .

The device searching unit requests peripheral input devices and output devices connected to the network to provide specifications information and receives the specifications information from the input devices and the output devices.

The service linkage unit generates a linkage flow with designations of an input device and an output device that can link each other in accordance with the function execution request input by the user on the basis of the specifications information received from the device searching unit . The specifications information and the linkage flow are the same as described in the first embodiment.

For example when the UI unit receives a function execution request for scan projection from the operation terminal the flow execution application sends a flow generation request for scan projection to the service linkage unit by using the API.

When receiving the flow generation request the device searching unit searches for devices that can execute scan and projection in the example in the MFP the projector and the projector from among the peripheral input devices and output devices.

The service linkage unit performs matching of the specifications information on the basis of the specifications information acquired by the device searching unit generates a linkage flow and sends the linkage flow to the flow execution application .

The API will be described in detail below. In the present embodiment a function of flow generation a function of an input process a function of an output process and a function of a processing process are provided as the API.

Therefore the flow execution application calls the function of flow generation in which input parameters are specified and sends the flow generation request to the service linkage unit . Furthermore the flow execution application calls the function of the input process in which input parameters are specified and sends to the device operating unit a request for an input process to be performed by the input device designated by the IP address. Moreover the flow execution application calls the function of the output process in which input parameters are specified and sends to the device operating unit a request for an output process to be performed by the output device designated by the IP address. Furthermore the flow execution application calls the function of the processing process in which input parameters are specified and sends to the device operating unit a request for a processing process to be performed by a service designated by the IP address.

For example the flow execution application calls the function of an input process in which scan is specified so that image data scanned by the MFP is stored in the storage unit and location information is returned as a response. It is possible to return the image data itself as the response.

Subsequently the flow execution application calls the function of an output process in which projection and the location information of the image data are specified as parameters so that the image data stored in the storage unit is projected by the projector .

The device operating unit interprets the contents of the requests for the input process and the output process and executes operations of the input device and the output device.

As described above the flow execution application sends requests for processes by using the API. Therefore the flow execution application can execute each process without regard to differences between the devices.

A concrete example of a device linkage process of the present embodiment with the above configuration will be explained below. is a sequence diagram from a process of requesting execution of functions to a process of displaying a linkage flow in the linkage process of the second embodiment. An example is explained in which a user inputs the function execution request for scan projection in the operation terminal .

Referring back to the operation terminal transmits the function execution request for scan projection which is specified by the user via the input screen to the information processing apparatus Step S .

The UI unit of the information processing apparatus receives the function execution request and sends to the flow execution application a flow generation request containing an input function scan an output function projection and a parameter e.g. an input attribute such as monochrome color or a projection attribute as designated in the function execution request Step S . The flow execution application sends a flow generation request to the service linkage unit by using the API Step S .

When receiving the flow generation request from the flow execution application the service linkage unit instructs the device searching unit to send a specifications information acquisition request to the peripheral input devices and output devices i.e. the MFP the projector and the projector connected to the network Steps S S and S and acquires the specifications information from each of the devices Steps S S and S .

The service linkage unit compares the specifications information acquired by the device searching unit and generates a linkage flow indicating an execution sequence and a combination of an input device and an output device that can execute the input function and the output function designated in the function execution request Step S .

The specifications information of the MFP is denoted by in the specifications information of the projector is denoted by in and the specifications information of the projector is denoted by in . illustrates a comparative table of the specifications information of the MFP the projector and the projector .

In the example illustrated in and the flow generation request indicates scan projection and the MFP can execute scan and the projector and the projector can execute projection . The output format for the scan performed by the MFP is JPEG and the input format for the projection performed by the projector is JPEG. Therefore the service linkage unit generates a linkage flow the MFP to the projector . Here the input format for the projection performed by the projector is TIFF therefore the projector is eliminated from a candidate for linkage. If there are a plurality of combinations that enable linkage a plurality of linkage flows are generated.

As denoted by the linkage flow contains a designated function call Scan for the input function provided with the IP address of the input device the MFP a scan attribute designation of color monochrome fullcolor an output data format JPEG and a comment on the input device the MFP as parameters and contains a designated function call Projection for the output function provided with the IP address of the output device the projector a projection attribute and a comment on the output device the projector as parameters in an execution sequence.

In the present embodiment the function Scan for the input function and the function Projection for the output function provided by the API are written in the linkage flow together with the parameters.

The service linkage unit sends the generated linkage flow to the flow execution application Step S . The flow execution application sends the linkage flow to the UI unit Step S and the UI unit displays the linkage flow on the operation terminal used by the user Step S .

The UI unit sends an execution request for the selected linkage flow to the flow execution application Step S .

The flow execution application calls a function designated in the selected linkage flow by using the API. Therefore it becomes possible to enable linkage between the MFP and the projector without regard to a change in the parameters for a process of causing the MFP and the projector to link each other.

Specifically the flow execution application calls the function Scan for the input function with the specified parameters by referring to the received linkage flow and sends a request for an input process to the device operating unit by using the API Step S . The request for the input process contains the input function indicating scan parameters for a designation of color monochrome fullcolor and the output data format JPEG and the IP address of the input device the MFP .

When receiving the request for the input process the device operating unit sends a process execution request to the input device the MFP designated in the request for the input process Step S . When receiving a notice of completion of the process from the input device the MFP Step S the device operating unit stores the notice of completion and the received scanned image data in the storage unit . The device operating unit then sends file information indicating a location of the scanned image data to the flow execution application Step S .

When receiving the file information the flow execution application calls the function Projection of the output function registered in the linkage flow by specifying the file information as a parameter and sends a request for an output process to the device operating unit by using the API Step S . The request for the output process contains projection as the output function a parameter such as the file information and the IP address of the output device the projector .

When receiving the request for the output process the device operating unit sends a process execution request to the output device the projector designated in the request for the output process Step S . When receiving a notice of completion of the process from the output device the projector Step S the device operating unit sends the notice of completion to the flow execution application Step S . The notice of completion is sent from the flow execution application to the UI unit and is subsequently sent from the UI unit to the operation terminal Steps S and S .

As described above according to the present embodiment when a function execution request relating to input and output is received from a user without a designation of an input device and an output device the device searching unit acquires specifications information from input devices and output devices connected to the network the service linkage unit generates a linkage flow containing a combination of an input device and an output device that can link each other and an execution sequence based on the specifications information and the flow execution application sends a process execution request to the input device and the output device in accordance with the linkage flow. Therefore even when a user does not know presence or absence of the input device and the output device or the specifications of the input device and the output device it is possible to enable linkage between the input device and the output device to perform a desired input output process. It is also possible to easily cause the input device and the output device to link each other.

Furthermore according to the present embodiment the flow execution application sends the flow generation request to the service linkage unit by using the API and sends execution requests for the input process and the output process to the device operating unit by using the API. Therefore it is possible to easily enable linkage between the input device and the output device without regard to a change in the parameters for a process of causing the input device and the output device to link each other.

In the first and the second embodiments the specifications information is acquired from the input device and the output device every time the flow generation request is issued in accordance with the function execution request sent from a user. In a third embodiment the specifications information acquired from the input device and the output device are stored and when a next flow generation request is issued the stored specifications information is used to generate a linkage flow.

The operation terminal the MFP the projector and the projector have the same functions as described in the second embodiment. The specifications of the MFP the projector and the projector are the same as those of the MFP the projector and the projector of the second embodiment respectively.

As illustrated in the information processing apparatus includes the UI unit the flow execution application and the application in an upper layer above the API. The information processing apparatus mainly includes a device search service linkage unit the device operating unit and the storage unit in a lower layer below the API.

The UI unit the flow execution application the device operating unit and the storage unit have the same functions and configurations as described in the second embodiment.

In the present embodiment similarly to the second embodiment the UI unit receives a function execution request that contains designations of a desired input function and a desired output function but does not contain designations of an input device that executes the input function and an output device that executes the output function.

The device search service linkage unit mainly includes a service linkage unit the device searching unit and a specifications managing unit . The device searching unit has the same function and configuration as described in the second embodiment.

The specifications managing unit is a storage medium such as a hard disk drive HDD or a flash memory for storing specifications information received by the device searching unit .

The service linkage unit stores the specifications information received by the device searching unit in the specifications managing unit . The service linkage unit generates a linkage flow with designations of an input device and an output device that can link each other in accordance with the function execution request input by the user on the basis of the specifications information received by the device searching unit or the specifications information stored in the specifications managing unit .

Specifically when the specifications information is registered in the specifications managing unit the service linkage unit generates a linkage flow based on the specifications information stored in the specifications managing unit . On the other hand when the specifications information is not registered in the specifications managing unit or when the specifications information stored in the specifications managing unit does not match a current specifications of an input device or an output device the service linkage unit causes the device searching unit to acquire the specifications information of the input device and the output device and generates a linkage flow based on the specifications information received by the device searching unit . Details of the method for generating the linkage flow are the same as described in the second embodiment.

A concrete example of a device linkage process of the present embodiment with the above configuration will be explained below. is a sequence diagram from a process of requesting execution of functions to a process of displaying a linkage flow in a linkage process of the third embodiment. An example is explained in which a user inputs a function execution request for scan projection in the operation terminal .

The processes from inputting the function execution request in the operation terminal by a user to acquiring specifications information from the MFP the projector and the projector and generating a flow Steps S to S are the same as described in the second embodiment.

When acquiring the specifications information and generating the flow the service linkage unit stores the acquired specifications information in the specifications managing unit Step S . The specifications information is stored in the specifications managing unit in the format as illustrated in .

The service linkage unit generates a linkage flow in the same manner as described in the second embodiment based on the acquired specifications information Step S . Subsequently the generated linkage flow is displayed on the operation terminal in the same manner as described in the second embodiment Steps S to S .

The specifications information stored in the specifications managing unit can be used in the following manner. is a sequence diagram from a process of requesting execution of functions to a process of displaying a linkage flow using the specifications information stored in the specifications managing unit in the linkage process of the third embodiment.

The processes from inputting the function execution request in the operation terminal by a user to requesting flow generation by the flow execution application Steps S to S are the same as described in the second embodiment.

When receiving the flow generation request from the flow execution application the service linkage unit reads the specifications information of the input device and the output device from the specifications managing unit instead of causing the device searching unit to request the input device and the output device to provide the specifications information Step S . The service linkage unit generates a linkage flow in the same manner as described in the second embodiment based on the read specifications information Step S . Subsequently the generated linkage flow is displayed on the operation terminal in the same manner as described in the second embodiment Steps S to S .

As described above according to the present embodiment the specifications information acquired by the device searching unit is stored in the specifications managing unit and the specifications information stored in the specifications managing unit is used to generate a linkage flow in a next flow generation process. Therefore it is possible to speed up the linkage process performed by the input device and the output device.

In the first to the third embodiments the input device and the output device are caused to link each other. By contrast in a fourth embodiment a service on a cloud computer hereinafter referred to as a cloud service can link an input device and an output device.

Furthermore in the first to the third embodiments the device operating unit recognizes actual usage of the input device and the output device. When a cloud service is provided as an original product manufactured by the same provider as that of the information processing apparatus the device operating unit also recognizes the usage of the cloud service. However if a cloud service provided by a third vendor rather than the original product is to be connected because the number of cloud services provided by third vendors is rapidly increasing it may be difficult to continuously install a processing section to establish a connection to the cloud services of the third vendors onto the information processing apparatus.

Therefore in the fourth embodiment a custom application developed by a third vendor is installable on the API so that a connection to a cloud service provided by a third vendor can be established by the custom application.

The operation terminal the MFP the projector and the projector have the same functions as described in the second embodiment. The specifications of the MFP the projector and the projector are the same as those of the MFP the projector and the projector of the second embodiment respectively.

As illustrated in the information processing apparatus includes the UI unit the flow execution application the application and a custom application in an upper layer above the API. The information processing apparatus mainly includes a device search service linkage unit the device operating unit and the storage unit in a lower layer below the API.

The UI unit the flow execution application the device operating unit and the storage unit have the same functions and configurations as described in the second embodiment.

In the present embodiment similarly to the second embodiment the UI unit receives a function execution request that contains designations of a desired input function and a desired output function but does not contain designations of an input device that executes the input function and an output device that executes the output function.

A flow generation request sent from the flow execution application to a service linkage unit contains conversion indicating data conversion performed by the data conversion service as denoted by .

The custom application is an application for establishing a connection to the data conversion service that is a cloud service provided by a third vendor and that is not recognizable by the information processing apparatus . The custom application recognizes the way to connect to the data conversion service conversion . Therefore in the custom application and the cloud service enclosed by a dashed line are provided by the third vendor.

The custom application provides an interface for a processing process as concretely described in the second embodiment defined by the API in order to provide functions of the data conversion service . The API for the processing process is also used when the data conversion service that is the original cloud service is used.

The device search service linkage unit mainly includes the service linkage unit the device searching unit and the specifications managing unit . The device searching unit and the specifications managing unit have the same functions and configurations as described in the third embodiment.

In the present embodiment the device searching unit does not know an interface corresponding to the data conversion service provided by the third vendor therefore the device searching unit cannot request the data conversion service to provide specifications information. Therefore the API provides a function of registration of specifications information to access the specifications managing unit as described in the second embodiment. Accordingly the custom application calls the specifications registration function to use the API and stores the specifications information of the data conversion service in the specifications managing unit . An example of the specifications information of the data conversion service is denoted by .

The service linkage unit stores the specifications information of the cloud service which is the original service in the specifications managing unit . The service linkage unit has the same functions as described in the third embodiment.

As described above in the present embodiment it is possible to install the custom application developed by a third vendor onto the API. Therefore it becomes possible to easily link cloud services as well as with an input device and an output device.

In a fifth embodiment combinations of an input device and an output device that can link each other are displayed on an operation terminal to allow a user to determine a combination instead of causing a service linkage unit to generate a linkage flow. That is in the present embodiment the linkage flow is configured based on a designation of a user.

The information processing apparatus of the present embodiment has the same configuration as described in the fourth embodiment illustrated in .

The service linkage unit of the present embodiment generates a list of one or more input devices that have an input function designated in the function execution request and a list of one or more output devices that have an output function designated in the function execution request instead of generating a linkage flow.

The UI unit displays the list of one or more input devices and the list of one or more output devices on the operation terminal and receives a selection of one input device from the list of one or more input devices and one output device from the list of one or more output devices from a user.

The flow execution application generates a linkage flow based on the selected input device and the selected output device and sends a process request to each of the selected input device and the selected output device in accordance with the linkage flow.

When the input device and the output device that are selected by the user cannot link each other the UI unit selects a processing process performed by a data conversion service etc. which is connected to the network and which processes data output from the input device into data corresponding to the specifications information of the output device.

In this case the flow execution application generates a linkage flow containing the selected input device the selected processing process and the selected output device and sends a process request to each of the devices and the service.

For example when the service linkage unit receives a flow generation request for scan projection from the flow execution application the service linkage unit generates a response as illustrated in and sends the response to the flow execution application .

As illustrated in the response contains names of devices and services corresponding input output formats and corresponding input output functions where FIRST indicates an input function of the designated linkage flow in this example scan and LAST indicates an output function in the designated linkage flow in this example projection .

When the flow execution application receives the response illustrated in the UI unit displays a flow selection screen illustrated in on the operation terminal .

A user can select an input device and an output device via the flow selection screen. For example when the MFP and the projector are selected because the output of the MFP is JPEG and the input of the projector is JPEG as illustrated in the response in the flow execution application configures a linkage flow for scan projection and executes the flow.

However if the MFP and a projector are selected via the flow selection screen because the input of the projector is PDF in the response illustrated in linkage is impossible without any modification.

Therefore the flow execution application of the present embodiment displays on the flow selection screen a process and a process that enable conversion between JPEG used for the output of the MFP and PDF used for the input of the projector i.e. an input is JPEG and an output if PDF as a process needed to establish a connection and allows a user to select one of the processes.

In this case when the user selects the process the flow execution application configures and executes a linkage flow formed of the MFP JPEG the process PDF the projector .

As another example it is possible to allow a user to select devices and services in order from the input device side. In this case the data structure of a response that is sent from the service linkage unit to the flow execution application is configured as follows.

As described above according to the present embodiment devices and services that link one another are determined based on a selection by a user. Therefore it is possible to increase the flexibility of the linkage.

In a sixth embodiment the specifications information of the cloud service described in the fourth embodiment contains a processing time taken by the cloud service.

The operation terminal the MFP the projector the projector the cloud service and the cloud service have the same functions as described in the fourth embodiment.

As illustrated in the information processing apparatus includes the UI unit the flow execution application the application and a custom application in an upper layer above the API. The information processing apparatus mainly includes a device search service linkage unit the device operating unit and the storage unit in a lower layer below the API.

The UI unit the flow execution application the device operating unit the storage unit and the application have the same functions and configurations as described in the second embodiment.

The custom application of the present embodiment registers in the specifications information of the data conversion service an average processing time taken by the data conversion service in addition to the contents of the specifications information described in the fourth embodiment and thereafter stores the specifications information in a specifications managing unit by using the API. An example of the specifications information of the present embodiment is denoted by .

As illustrated in the device search service linkage unit mainly includes a service linkage unit the device searching unit and the specifications managing unit . The device searching unit and the specifications managing unit have the same functions and configurations as described in the fourth embodiment.

When generating a linkage flow using the data conversion service the service linkage unit causes the custom application to extract an average processing time from the specifications information stored in the specifications managing unit and generates a linkage flow containing conversion which indicates data conversion performed by the data conversion service similarly to the fourth embodiment and the average processing time. An example of the linkage flow is denoted by in which the processing time is registered. In this example it is indicated that the processing time of the linkage flow containing the data conversion service performed by the cloud service becomes 5 seconds longer than the processing time of the linkage flow that does not contain the data conversion service .

It may be possible to add the above information to the specifications information that is sent as a response to an inquiry when the device searching unit searches for an input device and an output device. Furthermore the linkage flow may contain a reference time taken to a series of processes performed in accordance with the linkage flow.

As described above according to the present embodiment a linkage flow contains a processing time. Therefore when a plurality of linkage flows are displayed a user can determine a linkage flow in consideration of a processing time in addition to the consideration of the device and the service as factors used to select a linkage flow.

In a seventh embodiment a function execution request from a user contains positional information of the operation terminal and a device is searched for by using the positional information.

The operation terminal the MFP the projector the projector and the cloud service have the same functions as described in the fourth embodiment.

As illustrated in the information processing apparatus includes the UI unit the flow execution application and the application in an upper layer above the API. The information processing apparatus mainly includes a device search service linkage unit the device operating unit and the storage unit in a lower layer below the API.

The UI unit the device operating unit the storage unit and the application have the same functions and configurations as described in the second embodiment.

In the present embodiment the UI unit receives a function execution request that contains a desired input function a desired output function and positional information of the operation terminal but does not contain designations of an input device that executes the input function and an output device that executes the output function from the operation terminal . Examples of the positional information include but not limited to a position coordinate based on the latitude and the altitude acquired by a GPS or the like.

The flow execution application sends to a service linkage unit a flow generation request with designations of the input function the output function and the positional information contained in the function execution request. Therefore the positional information can be specified as a parameter in each of functions provided by the API of the present embodiment.

As illustrated in the device search service linkage unit mainly includes the service linkage unit the device searching unit and the specifications managing unit . The device searching unit and the specifications managing unit have the same functions and configurations as described in the fourth embodiment.

However the specifications managing unit also stores the positional information of the input device and the output device contained in the specifications information. The positional information may be acquired by the device searching unit as a part of the specifications information or may be registered in advance by an administrator or the like.

The specifications information that is received by the device searching unit in response to a request for the specifications information contains the positional information of each of the devices.

The service linkage unit extracts a combination of an input device and an output device that can link each other and that have positional information within a predetermined range with respect to the positional information of the operation terminal and generates a linkage flow based on the extracted combination.

A concrete example of a device linkage process of the present embodiment with the above configuration will be explained below. is a sequence diagram from a process of requesting execution of functions to a process of displaying a linkage flow in the linkage process of the seventh embodiment. An example is explained in which a user inputs a function execution request for scan projection positional information in the operation terminal .

The operation terminal transmits the function execution request for scan projection positional information designated by a user to the information processing apparatus Step S .

The UI unit of the information processing apparatus receives the function execution request sends a flow generation request containing an input function scan an output function projection a parameter e.g. an input attribute such as monochrome color or a projection attribute and positional information as designated in the function execution request to the flow execution application Step S . The flow execution application sends the flow generation request to the service linkage unit by using the API Step S .

When receiving the flow generation request from the flow execution application the service linkage unit gives an instruction to the device searching unit and the device searching unit sends a specifications information acquisition request to the MFP the projector and the projector which are the peripheral input devices and output devices connected to the network Steps S S and S and then acquires the specifications information from each of the devices Steps S S and S . The specifications information contains the positional information of each of the devices see and in the figure .

The service linkage unit compares the specifications information acquired by the device searching unit obtains combinations of an input device and an output device that can realize the input function and the output function designated in the function execution request selects a combination of an input device and an output device that have positional information within a predetermined range with respect to the operation terminal and generates a linkage flow indicating an execution sequence Step S . The subsequent processes Steps S to S are the same processes Steps S to S as described in the second embodiment.

As described above according to the present embodiment the positional information of the operation terminal is specified in the function execution request and when the service linkage unit generates a linkage flow the service linkage unit extracts a combination of an input device and an output device that have positional information within a predetermined range with respect to the positional information of the operation terminal . Therefore a user can designate the input device and the output device that link each other to execute input output functions near the operation terminal so that the user can obtain a desired result at an earlier time.

In the seventh embodiment the device searching unit acquires the specifications information of the input device and the output device and when the service linkage unit generates a linkage flow the service linkage unit extracts a combination of devices that have positional information within a predetermined range with respect to the positional information of the operation terminal . By contrast if the positional information of the input device and the output device is already known and when the device searching unit sends a specifications information acquisition request the device searching unit may select an input device and an output device that have positional information within the predetermined range with respect to the positional information of the operation terminal and send a specifications information acquisition request to the selected devices.

The operation terminal sends the function execution request for scan projection IP address of an operation terminal designated by a user to the information processing apparatus Step S .

The UI unit of the information processing apparatus receives the function execution request and sends to the flow execution application a flow generation request containing an input function scan an output function projection a parameter e.g. an input attribute such as monochrome color or a projection attribute and the IP address of the operation terminal as designated in the function execution request Step S . The flow execution application sends a flow generation request to the service linkage unit by using the API Step S .

When receiving the flow generation request from the flow execution application the service linkage unit gives an instruction to the device searching unit and the device searching unit refers to the specifications managing unit to select a device having the IP address that satisfies a certain condition e.g. within the same segment or within a predetermined range with respect to the IP address of the operation terminal designated in the flow generation request from among the MFP the projector and the projector that are the peripheral input devices and output devices connected to the network. Thereafter the device searching unit sends a specifications information acquisition request to the selected device.

In the present example the device searching unit selects input devices and output devices with IP addresses of 192.168.11. . Specifically the device searching unit selects the MFP with an IP address of 192.168.11.2 and the projector with an IP address of 192.168.11.50 sends the specifications information acquisition request to each of the MFP and the projector Steps S and S and acquires the specifications information from each of the MFP and the projector Steps S and S .

The projector is not selected and the specifications information acquisition request is not sent to the projector because the IP address thereof is 192.168.12.200 .

Subsequently the service linkage unit generates a linkage flow based on the acquired specifications information in the same manner as described in the second embodiment Step S and the subsequent processes Steps S to S are performed in the same processes Steps S to S as described in the second embodiment.

As described above according to the present embodiment when the device searching unit sends the specifications information acquisition request the device searching unit selects an input device and an output device that have positional information within a predetermined range with respect to the positional information of the operation terminal sends the specifications information acquisition request to the selected devices and generates a linkage flow based on the selected devices. Therefore it is possible to achieve the same advantages as those of the seventh embodiment as well as to reduce network loads.

In an eighth embodiment when a user carrying an operation terminal enters a meeting room and directly connects the operation terminal to a device such as a projector installed in the meeting room the operation terminal acquires the ID of the device and sends a function execution request to an information processing apparatus with a designation of the ID to cause the device to execute an input function and an output function.

The operation terminal is a terminal that the user can carry. Examples of the operation terminal include but not limited to a mobile device including a smartphone and a mobile phone and a tablet. As illustrated in the operation terminal includes a UI unit a device searching unit and an execution requesting unit .

The UI unit displays thereon various screens for the user and receives various operations from the user.

The device searching unit searches for an input output device such as the MFP the projector or the projector within the network and establishes an ad hoc network connection to the input output device obtained by the search. The UI unit requests the input output device which has established the ad hoc network connection to provide an ID as identification information for identifying the device and receives the ID.

The execution requesting unit sends a function execution request with a designation of the ID to the information processing apparatus .

When receiving the request for the ID from the operation terminal the input output device such as the MFP the projector or the projector sends own ID to the operation terminal .

When receiving the function execution request from the operation terminal the information processing apparatus causes the input output device to execute a function by the same processes as described in the third embodiment.

A function execution process performed by the information processing system configured as above in the present embodiment will be explained below. is a sequence diagram of the function execution process according to the eighth embodiment. In the example in a case is explained that the projector is used as the input output device however the same process is performed when other device is used as the input output device.

The device searching unit of the operation terminal searches for a device within a network and establishes an ad hoc network connection to the projector Step S . Subsequently the device searching unit of the operation terminal requests the projector that has established the ad hoc network connection to provide the IP of the projector Step S .

When receiving the ID of the projector the operation terminal sends a function execution request with a designation of the ID to the information processing apparatus Step S . Therefore the information processing apparatus that has received the function execution request causes the projector to perform projection in the same manner as described in the third embodiment.

As described above according to the present embodiment the operation terminal establishes an ad hoc network connection to the projector to acquire an ID and sends a function execution request with a designation of the ID to the information processing apparatus . Therefore even when a user who has entered a meeting room wants to use the projector installed in the meeting room without knowing the IP address of the projector it is possible to cause the projector to project a desired image or document which is convenient for the user.

In a ninth embodiment when a user carrying an operation terminal enters a meeting room and directly connects the operation terminal to a device such as a projector installed in the meeting room the operation terminal directly causes the device to execute an input function and an output function.

The operation terminal is a terminal that the user can carry. Examples of the operation terminal include but not limited to a mobile device including a smartphone and a mobile phone and a tablet. As illustrated in the operation terminal includes the UI unit a device searching unit and an application . The UI unit has the same function as described in the eighth embodiment.

The device searching unit searches for an input output device such as the MFP the projector or the projector within the network and establishes an ad hoc network connection to the input output device obtained by the search in the same manner as described in the eighth embodiment. The device searching unit of the present embodiment receives a command to execute a function in the input output device from the input output device that has established the ad hoc network connection. The command contains a uniform resource identifier URI of the input output device.

The application issues a command containing the URI to the input output device such as the MFP the projector or the projector .

When receiving a request for the command from the device searching unit of the operation terminal the input output device such as the MFP the projector or the projector sends the command containing the URI to the operation terminal . When the application of the operation terminal issues the command the input output device executes functions.

A function execution process performed by the information processing system of the present embodiment with the above configuration will be explained below. is a sequence diagram of the function execution process of the ninth embodiment. In the example in a case is explained that the projector is used as the input output device however the same process is performed when other device is used as the input output device.

The device searching unit of the operation terminal searches for a device within the network and establishes an ad hoc network connection with the projector Step S . The device searching unit of the operation terminal requests the projector that has established the ad hoc network connection to provide a command containing a URI to execute a projection function of the projector Step S .

When receiving the request for the command the projector sends the command containing the URI to execute the projection function Step S .

When receiving the command from the projector the operation terminal issues a command with a designation of the URI to the projector Step S . Therefore the projector performs a projection process Step S .

As described above according to the present embodiment the operation terminal establishes an ad hoc network connection to the projector acquires a command to execute a function and issues the command to cause the projector to execute the projection function. Therefore even when a user who has entered a meeting room wants to use the projector installed in the meeting room without knowing the IP address of the projector it is possible to cause the projector to project a desired image or document which is convenient for the user.

As illustrated in the information processing apparatus and the input output devices such as the MFP the projector and the projector are connected to one another in a local network first network . The information processing apparatus is located in a public network second network . The information processing apparatus is located in a local network third network .

The information processing apparatus and the information processing apparatus are accessible to each other and the information processing apparatus and the information processing apparatus are accessible to each other. The information processing apparatus and the input output devices such as the MFP the projector and the projector are installed in a meeting room and connected to the local network . A user carrying the operation terminal enters the meeting room and uses the input output devices in the meeting room. In the present embodiment to use the input output devices in the meeting room via the operation terminal the operation terminal connects to the information processing apparatus in the public network. A detailed explanation will be given below.

The managing unit of the present embodiment receives specifications information of the input output devices connected to the information processing apparatus in the local network from the information processing apparatus in the local network and stores the specifications information in the storage unit via the specifications managing unit . The managing unit receives specifications information of a data conversion service from the information processing apparatus in the local network and stores the specifications information in the storage unit . The storage unit is a storage medium such as an HDD or a memory for storing the specifications information.

The managing unit temporarily stores a process registered in a linkage flow in the queue when executing the linkage flow generated by the service linkage unit . The managing unit reads the process stored in the queue and sends requests for an input process and an output process to the information processing apparatus in the local network or sends a request for a processing process to the information processing apparatus in the local network in accordance with the process.

The client unit sends specifications information of an input output device acquired by the specifications managing unit to the information processing apparatus in a public network at regular time intervals. The client unit receives a request for an input process and a request for an output process from the information processing apparatus in the public network and sends the requests to the device operating unit to execute the processes.

The projector can project image data in a JPEG format and the projector can project image data in a TIFF format similarly to the second embodiment.

The client unit sends specifications information of the data conversion service to the information processing apparatus in the public network. The client unit receives a request for a processing process from the information processing apparatus in the public network and sends the request to the device search service linkage unit .

The device search service linkage unit receives the request for the processing process from the client unit and causes the data conversion service to perform data conversion. The device search service linkage unit acquires specifications information from the data conversion service and sends the specifications information to the client unit .

A linkage flow generation process performed by the information processing system of the present embodiment with the above configuration will be explained below. is a sequence diagram of a flow of the linkage flow generation process of the tenth embodiment.

The device search service linkage unit of the information processing apparatus in the local network acquires specifications information from the input output devices such as the MFP the projector and the projector in the local network Steps S S and S . The device search service linkage unit of the information processing apparatus registers stores the acquired specifications information in the storage unit Step S .

The device search service linkage unit reads the specifications information stored in the storage unit at regular time intervals and sends the read specifications information to the client unit Step S . The client unit sends the specifications information received from the device search service linkage unit to the information processing apparatus in the public network at regular time intervals Step S .

The managing unit of the information processing apparatus in the public network receives the specifications information sent by the information processing apparatus in the local network and the specifications managing unit registers stores the received specifications information in the storage unit Step S .

The user who has entered the meeting room sends a function execution request to the information processing apparatus in the public network via the operation terminal Step S . An example is explained below in which the function execution request is a projection execution request with a designation of the ID of the projector . Specifically the operation terminal sends the function execution request for file projection the ID of the projector to the information processing apparatus . In this example the file is PDF image data to be projected. The operation terminal acquires the ID of the projector in the same manner as described in the eighth embodiment.

When receiving the function execution request the information processing apparatus performs the flow generation process in the same manner as described in the third embodiment. Specifically the UI unit of the information processing apparatus receives the function execution request and sends a flow generation request to the flow execution application Step S . The flow execution application sends the received flow generation request to the service linkage unit Step S .

When receiving the flow generation request the service linkage unit reads the specifications information from the storage unit Step S and generates a linkage flow based on the specifications information Step S . In this example in which the function execution request for file projection the ID of the projector is issued the file is PDF image data and the input format of the projector is JPEG according to the specifications information therefore it is needed to convert the file to the JPEG format. Therefore the service linkage unit refers to the specifications information of the data conversion service of the information processing apparatus in the local network and registers data conversion to be performed by the data conversion service as a processing process in the linkage flow in addition to a projection output process.

Consequently the service linkage unit generates a linkage flow of processing process conversion file conversion attribute PDF JPEG the data conversion service output process projection file the ID of the projector . In this case if there are a plurality of input output devices such as the projectors and data conversion services a plurality of available linkage flows may be generated based on the specifications information.

When one or more linkage flows are generated as described above the service linkage unit sends a response to the UI unit via the flow execution application Steps S and S . The UI unit sends the generated linkage flows to the operation terminal and the linkage flows are displayed on the operation terminal Step S .

The flow execution application analyzes the linkage flow and sends requests for the processes registered in the linkage flow to the service linkage unit in order of the processes registered. In this example the linkage flow of processing process conversion file conversion attribute PDF JPEG the data conversion service output process projection file the ID of the projector is registered. Therefore the flow execution application first sends a request for the processing process processing process conversion file conversion attribute PDF JPEG the data conversion service to the service linkage unit together with image data to be subjected to the processing process Step S . The service linkage unit sends the request for the processing process to the managing unit Step S . The managing unit acquires specifications information of the data conversion service from the storage unit Step S and registers the processing process conversion file conversion attribute PDF JPEG the data conversion service in the queue Step S .

The flow execution application sends a request for the output process output process projection file the ID of the projector which is registered subsequent to the processing process in the linkage flow to the service linkage unit Step S . The service linkage unit sends the request for the output process to the managing unit Step S . The managing unit acquires specifications information of the projector from the storage unit Step S and registers the output process projection file the ID of the projector in the queue Step S .

The managing unit acquires the registered processes from the queue Step S . The processing process is first registered in the queue therefore the managing unit sends a request for the processing process conversion file conversion attribute PDF JPEG the data conversion service to the information processing apparatus in the local network Step S .

The client unit of the information processing apparatus in the local network receives the request for the processing process and sends the request to the device search service linkage unit Step S . The device search service linkage unit sends a data conversion request to the data conversion service together with the image data indicated by the file designated in the request for the processing process Step S .

Accordingly the data conversion service performs data conversion of the file Step S . When the data conversion is complete the data conversion service sends a notice of completion and the converted file to the information processing apparatus in the public network Steps S S and S .

The managing unit of the information processing apparatus in the public network subsequently acquires the process that is subsequently registered in the queue Step S . The output process is registered subsequent to the processing process in the queue therefore the managing unit sends a request for the output process output process projection file the ID of the projector to the information processing apparatus in the local network together with the file that is obtained by the data conversion Step S .

The client unit of the information processing apparatus in the local network receives the request for the output process and sends the request to the device operating unit Step S . The device operating unit sends a projection request and the converted file to the projector that is designated by the ID Step S . The projector performs the projection process on the converted file as designated in the projection process Step S .

When completing the projection process the projector sends a notice of completion to the information processing apparatus Step S . The information processing apparatus sends the notice of completion to the information processing apparatus in the public network Steps S and S .

The managing unit of the information processing apparatus in the public network subsequently acquires the process that is subsequently registered in the queue Step S . The output process is registered subsequent to the processing process in the queue therefore the managing unit sends a request for the output process output process projection file the ID of the projector to the information processing apparatus in the local network together with the file that is obtained by the data conversion Step S .

As described above according to the present embodiment when a user enters a meeting room and uses an input output device in the local network in the meeting room and if the operation terminal used by the user is not connectable to the local network it is possible to execute the input output function of the input output device by sending a process request to the information processing apparatus in the public network via the access to the information processing apparatus which is convenient for the user.

As illustrated in the input output devices such as the MFP the projector and the projector are located in the local network first network . The information processing apparatus is located in the public network second network . The information processing apparatus is located in the local network third network .

The input output devices such as the MFP the projector and the projector and the information processing apparatus are accessible to one another. The information processing apparatus and the information processing apparatus are accessible to each other. The information processing apparatus in the local network has the same configuration as described in the tenth embodiment.

The input output devices such as the MFP the projector and the projector are installed in a meeting room and connected to the local network . The projector can project image data in a JPEG format and the projector can project image data in a TIFF format similarly to the second embodiment.

A user carrying the operation terminal enters the meeting room and uses the input output devices in the meeting room. In the present embodiment to use the input output devices in the meeting room via the operation terminal the operation terminal is connected to the information processing apparatus in the public network. A detailed explanation will be given below.

The managing unit of the present embodiment receives specifications information from each of the input output devices such as the MFP the projector and the projector in the local network at regular time intervals and stores the received specifications information in the storage unit via the specifications managing unit . The specifications managing unit sends a request for processes registered in the linkage flow registered in the storage unit to the input output devices such as the MFP the projector and the projector and causes each of the input output devices to execute functions. The managing unit has the same functions as described in the tenth embodiment.

A linkage flow generation process performed by the information processing system of the present embodiment with the above configuration will be explained below. is a sequence diagram of a flow of the linkage flow generation process of the eleventh embodiment.

The managing unit of the information processing apparatus in the public network receives specifications information from each of the input output devices such as the MFP the projector and the projector in the local network at regular time intervals Steps S and S . The managing unit receives the specifications information sent by the input output device in the local network and the specifications managing unit registers stores the received specifications information in the storage unit Step S .

The user who has entered the meeting room sends a function execution request to the information processing apparatus in the public network via the operation terminal Step S . Therefore a linkage flow is generated and displayed by the operation terminal in the same manner as the linkage flow generation process described in the tenth embodiment illustrated in Steps S to S .

The managing unit acquires the registered processes from the queue Step S . The processing process is first registered in the queue therefore the managing unit sends a request for the processing process conversion file conversion attribute PDF JPEG the data conversion service to the information processing apparatus in the local network Step S .

The client unit of the information processing apparatus in the local network receives the request for the processing process and sends the request to the device search service linkage unit Step S . The device search service linkage unit sends a data conversion request to the data conversion service together with the image data indicated by the file designated in the request for the processing process Step S .

Accordingly the data conversion service performs data conversion of the file Step S . When the data conversion is complete the data conversion service sends a notice of completion and the converted file to the information processing apparatus in the public network Steps S S and S .

The managing unit of the information processing apparatus in the public network subsequently acquires the process that is subsequently registered in the queue Step S . The output process is registered subsequent to the processing process in the queue therefore the managing unit sends a request for the output process output process projection file the ID of the projector to the projector in the local network together with the file that is subjected to the data conversion Step S . The projector performs a projection process on the data converted file as designated in the projection request Step S .

When the projection process is complete the projector sends a notice of completion to the information processing apparatus in the public network Step S . The managing unit of the information processing apparatus receives the notice of completion and the managing unit sends the notice of completion to the operation terminal via the device operating unit the flow execution application and the UI unit Steps S S S and S .

As described above according to the present embodiment when a user enters a meeting room and uses an input output device in the local network in the meeting room and if the operation terminal used by the user is not connectable to the local network it is possible to execute the input output function of the input output device by sending a process request to the information processing apparatus in the public network via the access to the information processing apparatus which is convenient for the user.

The information processing apparatus of each of the first to the eleventh embodiments and modifications has a hardware configuration including a control device such as a central processing unit CPU a storage device such as a read only memory ROM or a random access memory RAM an external storage device such as an HDD or a compact disc CD drive a display device such as a display and an input device such as a keyboard or a mouse.

A device linkage program executed by the information processing apparatus of each of the first to the eleventh embodiments and modifications is provided by being recorded in a computer readable recording medium such as a CD ROM a flexible disk FD a CD R or a digital versatile disk DVD in a computer installable or a computer executable format.

The device linkage program executed by the information processing apparatus of each of the first to the eleventh embodiments and modifications may be stored in a computer connected to a network such as the Internet and be provided by downloading via the network. The device linkage program executed by the information processing apparatus of each of the first to the eleventh embodiments and modifications may be provided or distributed via the network such as the Internet.

The device linkage program executed by the information processing apparatus of each of the first to the eleventh embodiments and modifications may be provided by being pre installed in a ROM or the like.

The device linkage program executed by the information processing apparatus of each of the first to the eleventh embodiments and modifications has a module structure including the above units the UI unit the flow execution application the device operating unit the device searching unit and the service linkage unit . As actual hardware a CPU processor reads and executes the device linkage program from the above mentioned storage medium to load the above units on a main storage device so that the UI unit the flow execution application the device operating unit the device searching unit and the service linkage unit are generated on the main storage device.

According to the embodiments it is possible to easily cause an input device an output device and other external devices to link each other.

Although the invention has been described with respect to specific embodiments for a complete and clear disclosure the appended claims are not to be thus limited but are to be construed as embodying all modifications and alternative constructions that may occur to one skilled in the art that fairly fall within the basic teaching herein set forth.

