---

title: Storage device including software development kit that includes web service interface and terminal apparatus including the software development kit
abstract: A storage device including a software development kit that includes a Web service interface includes a communication unit, a conversion table, a reverse conversion unit, and a conversion unit. The communication unit transmits a request message to a Web service and receives a response message from the Web service. The conversion table stores a pre-conversion side service method name of the Web service that is corresponded with a post-conversion side service method name. The reverse conversion unit, when data regarding the request message includes the post-conversion side service method name stored in the conversion table, converts the post-conversion side service method name into the corresponding pre-conversion side service method name. The conversion unit, when data regarding the response message includes the pre-conversion side service method name stored in the conversion table, converts the pre-conversion side service method name into the corresponding post-conversion side service method name.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09026588&OS=09026588&RS=09026588
owner: KYOCERA Document Solutions Inc.
number: 09026588
owner_city: 
owner_country: JP
publication_date: 20121105
---
This application is based upon and claims the benefit of priority from corresponding Japanese Patent Application No. 2011 242938 filed in the Japan Patent Office on Nov. 5 2011 and European Patent Application No. EP12191292.9 filed on Nov. 5 2012 the entire contents of both of which are incorporated herein by reference.

The present disclosure relates to a storage device including a software development kit SDK that includes a client side Web service interface coupled between a communication unit for transmitting a request message to a Web service and receiving a response message from the Web service and an extended application. The present disclosure also relates to a terminal apparatus that includes the SDK.

However in view of the widespread use of mobile terminal apparatuses such as smart phones attempts are being made to increase the efficiency with which business is carried out by removing this prohibition under specified conditions.

On the other hand there is a case in which a user utilizes a plurality of cloud services since the types and fees of services of cloud servers are different from one another.

When a user or a third party develops an extended application for remotely controlling an image forming apparatus in the office and for reading and changing the setting information thereof through a Web service for the apparatus using a smart phone or develops an extended application for utilizing a cloud service using a smart phone smooth development of extended applications is difficult since the rules of naming service methods of Web service providers are generally different from one another. This leads to increased programming errors and longer development periods of the extended applications.

Such a phenomenon is seen also in the development of extended applications which are installed in terminal apparatuses such as desktop computers other than smart phones.

The present disclosure relates to a storage device including an SDK that includes a client side Web service interface that may allow smoother development of an extended application that utilizes Web services provided by a plurality of Web service providers. The present disclosure also relates to a terminal apparatus including the SDK.

A storage device including an SDK that includes a Web service interface according to an embodiment of the present disclosure includes a communication unit a conversion table a reverse conversion unit and a conversion unit. The communication unit transmits a request message to a Web service and receives a response message from the Web service. The conversion table stores a pre conversion side service method name of the Web service that is corresponded with a post conversion side service method name. The reverse conversion unit when data regarding the request message includes the post conversion side service method name stored in the conversion table converts the post conversion side service method name into the corresponding pre conversion side service method name. The conversion unit when data regarding the response message includes the pre conversion side service method name stored in the conversion table converts the pre conversion side service method name into the corresponding post conversion side service method name.

A terminal apparatus that includes a Web service interface according to an embodiment of the present disclosure includes a communication unit a conversion table a reverse conversion unit and a conversion unit. The communication unit transmits a request message to a Web service and receives a response message from the Web service. The conversion table stores a pre conversion side service method name of the Web service that is corresponded with a post conversion side service method name. The reverse conversion unit when data regarding the request message includes the post conversion side service method name stored in the conversion table converts the post conversion side service method name into the corresponding pre conversion side service method name. The conversion unit when data regarding the response message includes the pre conversion side service method name stored in the conversion table converts the pre conversion side service method name into the corresponding post conversion side service method name.

Additional features and advantages are described herein and will be apparent from the following Detailed Description and the figures.

In the image forming system an image forming apparatus a personal computer PC as a terminal apparatus and an access point of a wireless local area network LAN are coupled to an intranet . A smart phone as a mobile terminal apparatus is coupled to the intranet via the access point . The intranet is coupled to the Internet via a router not illustrated . A plurality of cloud servers are coupled to the Internet . A base station is coupled to the Internet and smart phone is coupled to the Internet via the base station .

The plurality of cloud servers may respectively provide the cloud services to the PC and the smart phones and .

By installing an extended application on the PC and the smart phones and a user may perform from these apparatuses at least one of the services of the image forming apparatus such as copying printing and faxing the cloud services and any combination of these services as a Web service. Similarly a user may obtain setting information of the image forming apparatus and modify the setting information.

Referring to a plurality of terminal apparatuses are represented by the PC a plurality of mobile terminal apparatuses for the access point are represented by the smart phone and a plurality of mobile terminal apparatuses for the base station are represented by the smart phone .

The image forming apparatus includes a scanner a printer a FAX an operation panel and a network interface card NIC as hardware components. The input output control of the hardware components is performed via a platform .

The platform includes an operating system OS that performs the input output control power supply management communication using for example the Transmission Control Protocol Internet Protocol TCP IP various device drivers in a layer below the OS virtual machines as class libraries on the OS such as a Java registered trademark virtual machine and the Common Language Runtime CLR and a development environment such as one consisting of standard libraries and compilers.

A control module as a class library controls the hardware components via an application interface API of the platform . A basic application controls the hardware components via an API of the control module on the basis of functions such as copying printing and faxing.

The setting information for the hardware components is stored in a setting information database by the control module in response to operation of the operation panel . The stored setting information is displayed on the operation panel by the control module in response to operation of the operation panel .

A system management unit performs process for for example authentication and or authorization for a user error management and power saving management via the API or the API .

A request for service from at least one of the PC and the smart phones and to the image forming apparatus is transmitted to a Web service provider via the NIC and the platform . In response to the request the Web service provider by making the basic application operate via an API reads setting information from the setting information database via the API and or changes the settings in the setting information database . Then the Web service provider replies with the results.

The smart phone includes a camera an inclination sensor a Bluetooth communication unit BT an operation panel a communication adapter CA and the like as hardware components. An antenna is coupled to the communication adapter . The input output control of the hardware components is performed via a platform .

The platform includes an OS that performs the input output control power supply management communication using the TCP IP and the like various device drivers in a layer below the OS a virtual machine as a class library on the OS and standard libraries.

A control module controls the hardware components via an API of the platform . A basic application controls the hardware components via an API of the control module on the basis of functions.

The setting information for the hardware components is stored in a setting information database by the control module in response to operation of the operation panel . The stored setting information is displayed on the operation panel by the control module in response to operation of the operation panel .

A system management unit performs process for for example authentication and or authorization for a user error management and power saving management via the API or the API .

In response to operation of the operation panel a Web client transmits a request to a specified URL via the API and makes the operation panel display the content received in the response.

An extended application via an API of the basic application makes a single function or a combination of a plurality of functions be performed reads the setting information in the setting information database via the API and makes the information be displayed on the operation panel or makes the setting information in the setting information database be changed.

The extended application sends a request to the Web service provider of the image forming apparatus or the cloud services of the cloud servers via a Web service interface A and the Web client . The extended application receives the results via the Web client and the Web service interface A and makes the content of the results be displayed on the operation panel .

The Web client in response to input of the URL of a Web Service Description Language WSDL file by a developer transmits a request to this URL via a TCP IP communication unit of the platform . A response to the request is received via the TCP IP communication unit and the Web client and stored as a WSDL file .

In the related art a service proxy is generated by a WSDL tool on the basis of the WSDL file . In the present embodiment the Web service interface A includes a converter CNV . The WSDL file is copied and a WSDL file is created from this copy such that specific service method names among the service method names included in the copied WSDL file have been converted into other service method names while the rest of the service method names are left as they are. The service proxy is generated by the WSDL tool on the basis of the content of the WSDL file .

Referring back to the service proxy makes a request to an external Web service and a response thereto is seen as a call of an internal method and a return of a return value thereto from the viewpoint of the extended application .

A call of a service method from the extended application to the service proxy is converted by a serializer into Extensible Markup Language XML code which conforms to the Simple Object Access Protocol SOAP . The CNV further includes a reverse conversion unit . When a service method name included in the XML code includes a service method name on the extended application side post conversion side service method name the service method name is converted reverse conversion into a service method name defined on the service provider side pre conversion side service method name .

Referring to the element name of the first child element of the BODY element represents a service method name and hence countWord is the service method name. The child element of the element with the service method name countWord is an argument of this method. The element names html and word are the argument names where the argument values are respectively http abx.com copy.html and copy . The service method name countWord refers to a service method that counts the number of times the word copy appears in a page http abx.com copy.html .

Referring back to the Web client by making the XML code after conversion be the body of a Hyper Text Transfer Protocol HTTP message performs communication based on the HTTP with a Web server that is included in a Web service provider on the Web service side.

As a processing result on the Web service side the processing result in XML is provided to a conversion unit of the CNV via the TCP IP communication unit and the Web client . When a Web service response name included in the XML code includes a pre conversion side service method name stored in the conversion table the conversion unit converts the Web service response name into a method name on the extended application side post conversion side service method name .

Referring to the element name of the first child element of the BODY element represents a service method name Response and hence the element name is wordCountResponse . The child element of the element with this element name is a return value of this method the element name count is the name of the return value and the value is . Since wordCountResponse includes the pre conversion side service method name wordCount stored in the conversion table wordCountResponse is converted into countWordResponse by the conversion unit .

Referring back to the XML code after the conversion is converted into a return value for the service method call by a deserializer . The service proxy returns the return value to the extended application .

A service proxy A is generated by the WSDL tool on the basis of the content of the WSDL file and replaces the service proxy .

The extended application after a piece of the source code thereof including a post conversion service method stored in the conversion table has been replaced by a corresponding pre conversion side service method name is converted to an extended application A.

The CNV in is omitted and the serializer and the deserializer are directly logically combined with the Web client whereby the Web service interface A is made to be the Web service interface B.

In the terminal apparatus PC a CPU is coupled to a memory a hard disk drive HDD an input output apparatus and a network interface card NIC via an interface . In a plurality of interfaces is represented by a single block for simplicity.

The memory includes for example a flash memory storing a BIOS and a DRAM used as a main memory. The HDD which is example of a storage device stores an OS various device drivers libraries and virtual machines as a platform PF and further an SDK. The NIC is coupled to the intranet .

The software development apparatus illustrated in supports the development of the extended application illustrated in . Components A to and illustrated in respectively correspond to the components to and illustrated in . Regarding the components A to and only components among the corresponding components to and necessary for developing the extended application need to be provided. Wrapper APIs and A are used to disguise an API respectively as the API and the API through wrapping. The WSDL tool is included in a standard library within a platform .

The software development apparatus similarly to a representative SDK development apparatus includes a text editor a designer a debugger a builder and an application development integrated management unit which performs process for calling one of these components in response to an operation performed by a user process for generating a project and the like. The designer supports the development of an application for designing the screen of the operation panel and automatically generates a program on the basis of a visual design.

The software development apparatus further includes a simulator simulating the hardware HW of the smart phone . An input apparatus and a display apparatus form the input output apparatus illustrated in . The components other than the extended application and the service proxy in the Web service interface A illustrated in are provided in advance as the components of a development environment.

According to the first embodiment the conversion table is provided which stores pre conversion side service method names of a Web service and corresponding post conversion side service method names. When a request message for the Web service includes a post conversion side service method name stored in the conversion table the reverse conversion unit converts the post conversion side service method name into a corresponding pre conversion side service method name. When a response message includes a pre conversion side service method name stored in the conversion table the conversion unit converts the pre conversion side service method name into a corresponding post conversion side service method name. Hence in the case of developing an application that uses the Web services of a plurality of Web service providers even when naming rules are different among the providers the naming rules are made the same whereby the application may be more smoothly developed without causing confusion.

Further since only conversion process on serialized text data is required the general purpose CNV may be used independent of the types of Web service or platform.

The service proxy in the case of using the CNV is easily generated using the general purpose CNV and the WSDL tool .

In addition after an extended application has been developed using the CNV the CNV may be omitted leading to an increase in processing speed.

The second embodiment has a configuration in which a wrapper generation tool and a conversion table have been added to the block configuration illustrated in . The wrapper generation tool generates a service proxy wrapper . Further the extended application illustrated in is used instead of the extended application A illustrated in .

Among the service methods called by the extended application a service method whose service method name is not the same as any of the pre conversion side service method names in the conversion table exists in the service proxy A and hence a service method within the service proxy A is directly called. In the case of a service method whose service method name is the same as a service method name in the conversion table among the service methods called by the extended application a corresponding service method in the service proxy wrapper is called and this service method calls a corresponding service method in the service proxy A.

The service proxy wrapper is generated by the wrapper generation tool with reference to the conversion table and is provided in advance in the PC illustrated in .

The post process illustrated in may be also performed in the second embodiment. In other words after the development of the extended application has been completed among the pieces of the source code of the extended application a piece of the source code that is the same as a post conversion side service method name included in the conversion table is replaced by a corresponding pre conversion side service method name. Thus the extended application A is created and by omitting the service proxy wrapper the block configuration illustrated in may be obtained. This produces a result which is the same as that obtained when the extended application A is created without using the wrapper generation tool and the service proxy wrapper .

The present disclosure of the embodiment includes various other embodiments. For example other designs may be used in which the above described components are each present.

In the first and second embodiments for example SOAP over HTTP is used. However a protocol for transmitting a SOAP message other than HTTP may be used and the Representational State Transfer REST protocol or the XML Remote Procedure Call XML RPC protocol may be used instead of SOAP.

For example although a processing speed is increased by the post process described above the post process may not be performed in the first and second embodiments.

It should be understood that various changes and modifications to the embodiments described herein will be apparent to those skilled in the art. Such changes and modifications may be made without departing from the spirit and scope of the present subject matter and without diminishing its intended advantages. It is therefore intended that such changes and modifications be covered by the appended claims.

