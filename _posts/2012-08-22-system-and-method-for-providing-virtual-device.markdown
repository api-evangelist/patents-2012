---

title: System and method for providing virtual device
abstract: Disclosed is a system and method for providing a virtual terminal. A virtual cloud server may configure a plurality of virtual terminals by employing a virtual machine in a cloud environment. The virtual cloud server may provide an application of a heterogeneous platform to a terminal that accesses the virtual cloud server. A cooperative middleware apparatus may determine a cloud server suitable for a mobile terminal among a plurality of cloud servers, based on content information of content and virtual terminal information stored in the plurality of cloud servers.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09207989&OS=09207989&RS=09207989
owner: INTELLECTUAL DISCOVERY CO., LTD.
number: 09207989
owner_city: Seoul
owner_country: KR
publication_date: 20120822
---
The following embodiments relate to virtualization technology and more particularly to a system and method for providing a virtual terminal.

With advancement of information society access to information has been further accelerated and an amount of access to the information has been increasing. Also enhancement of hardware performance and an increase in a degree of integration of an electronic circuit have made it possible to produce further smaller hardware.

With such development in technology small and high performance terminals such as a smart phone a tablet and a personal computer PC that enable computing and the Internet have been widely distributed. Such terminal enables a user to access information without restrictions on a time and an occasion by providing access to a computing environment and the Internet.

In order to provide a service a terminal may use a variety of applications App based on a service to be provided. An application may not be independently executed in the terminal. The application may be executed on a platform that is an operating system OS of the terminal. Accordingly the application needs to be developed based on a development interface and a development language that are provided by a supplier of a predetermined platform. The developed application may be executed only on the predetermined platform.

Currently commercialized representative platforms may be iOS of Apple Android of Google and Windows Mobile of Microsoft. The above platforms have been produced based on a personal PC environment having OSs such as Mac Linux and Windows respectively. An application of each platform has been developed using a computer programming language that is provided based on an OS corresponding to a platform. Accordingly each of applications may use a different development language and a different application programming interface API .

It is very complex and inconvenient to configure a single application environment by unifying different application languages and APIs. Also when configuring the single application environment it may not make the most of characteristics of each platform of a terminal.

High tech mobile terminals such as a smart phone a tablet and a PC may use high performance computing resources through cloud computing without restrictions on a time and an occasion. Also a personal cloud service for using a variety of services such as synchronization storage and restoration of personal data and contents has been developed.

As cloud computing can be expected to be in the mainstream of future mobile computing a variety of cloud services may be integrated into a mobile terminal. A mobile cloud indicates combination of a cloud service and mobile computing. In response to providing of a mobile cloud environment research on a zero client and thin client model using a mobile terminal is ongoing in order to overcome platform dependency of the mobile terminal functional constraints and constraints of performance by employing the mobile cloud environment.

Unlike an existing computing environment depending on independent hardware performance of each terminal cloud computing refers to technology that integrates resources of computers present in different physical locations using virtualization technology and provides the integrated resource. As clouding computing is used a program or a document individually stored in a PC and a server of a company may be stored in a large scale computer accessible through the Internet. In order to use a cloud service such as a web browser of a mobile terminal a user may execute a required application and may perform a desired work through the executed application.

A thin client system is a concept in which 1 a user terminal includes a minimum required number of apparatuses and 2 a central server is in charge of storing and processing data and executing software. Currently the thin client system may realize desktop virtualization that is representative cloud computing technology generally.

In desktop virtualization technology a client may be managed through session management technology of a server or a virtual machine that is driven in the server and the like. Execution of software may be completely performed in a server or a virtual machine of the server. A result screen that is generated in response to execution of software may be transmitted to a terminal of the client.

By applying thin client technology based on cloud computing it is possible to overcome a disadvantage of a mobile terminal having a relatively short amount of resources.

However since a variety of services are provided at the same time in which a concept of a mobile cloud has been established platform dependency such as mutual compatibility between services portability and security becomes an issue.

An aspect of the present invention provides technology of providing a variety of application services by configuring a platform dependent application on a cloud and by executing the configured application on a personalized heterogeneous platform.

Another aspect of the present invention also provides technology of enabling an inter cloud service and enhancing mutual compatibility between content and a mobile operating system OS and portability.

According to an aspect of the present invention there is provided a system for providing a virtual terminal service the system including a virtual cloud server to configure a plurality of virtual terminals by employing a virtual machine in a cloud environment. The virtual cloud server may provide an application of a heterogeneous platform to a terminal that accesses the virtual cloud server and the heterogeneous platform may be a virtual platform of a virtual terminal in which the application requested by the terminal is present among the plurality of virtual terminals and may be a platform of a heterogeneous terminal having a type different from a type of the terminal.

The virtual terminal service providing system may further include a managing server to authenticate the terminal and to transfer to the terminal a location address of a virtual gateway of the virtual cloud server in which the application of the heterogeneous platform is present.

The managing server may identify the virtual terminal in which the application requested by the terminal is present from among the plurality of virtual terminals based on information received from the terminal.

The virtual cloud server may enable the terminal to access the platform of the heterogeneous terminal by employing a thin client technology.

The virtual terminal service providing system may further include a personal cloud storage to provide sharing and synchronization of data between a platform of the terminal and the heterogeneous platform.

The virtual terminal service providing system may further include a market server to provide applications of a plurality of virtual platforms of the plurality of virtual terminals.

According to another aspect of the present invention there is provided a method of providing an application of a heterogeneous platform to a terminal the method including configuring a plurality of virtual terminals by employing a virtual machine in a cloud environment and providing the application of the heterogeneous platform to the terminal.

The heterogeneous platform may be a virtual platform of a virtual terminal in which the application requested by the terminal is present among the plurality of virtual terminals and may be a platform of a heterogeneous terminal having a type different from a type of the terminal.

According to still another aspect of the present invention there is provided a cooperative middleware apparatus including a connection relay module to receive a request for content from a mobile terminal and to transfer an access link to the mobile terminal and a resource managing module to determine a cloud server suitable for the mobile terminal among a plurality of cloud servers based on content information of the content and virtual terminal information stored in the plurality of cloud servers to generate the access link that enables an access to a virtual terminal of the determined cloud server and to transfer the generated access link to the connection relay module.

When the content is absent in the determined cloud server the resource managing module may determine migration of the content to the determined cloud server from another cloud server in which the content is present among the plurality of cloud servers.

The resource managing module may request the determined cloud server for the migration of the content.

The resource managing module may verify an allocation state of virtual terminals of the determined cloud server and may determine whether to allocate a new virtual terminal based on the verified allocation state.

The resource managing module may request the determined cloud server to allocate the new virtual terminal.

The resource managing module may monitor quality of a service of content that is provided by the determined cloud server to the mobile terminal.

The connection relay module may authenticate the mobile terminal based on personal information of a user of the mobile terminal that is stored in the connection relay module.

The connection relay module may monitor a communication state between the mobile terminal and the determined cloud server.

The virtual terminal of the determined cloud server may be capable of executing the content among virtual terminals allocated within the determined cloud server.

According to a further another aspect of the present invention there is provided a content providing method including receiving a request for content from a mobile terminal determining a cloud server suitable for the mobile terminal among a plurality of cloud servers based on content information of the content and virtual terminal information stored in the plurality of cloud servers generating the access link that enables an access to a virtual terminal of the determined cloud server and transferring the generated access link to the mobile terminal.

The content providing method may further include determining migration of the content to the determined cloud server from another cloud server in which the content is present among the plurality of cloud servers when the content is absent in the determined cloud server.

The content providing method may further include verifying an allocation state of virtual terminals of the determined cloud server and determining whether to allocate a new virtual terminal based on the verified allocation state.

According to embodiments a user may use an application of a different platform using a platform of a terminal being used by the user.

Also according to embodiments a user may use an application of a platform of a heterogeneous terminal through configuration of an application market that does not apply constraint of a platform with respect to all of the terminals.

Also according to embodiments a user may share and synchronize data which is generated when using an application of a platform of a heterogeneous terminal in real time with a platform of a terminal of the user. Accordingly the user may be provided with the same data regardless of an application of a platform used by the user.

Also according to embodiments a platform market may provide an integrated application market in which different platforms are integrated and thus further various applications may be provided to a user.

Also according to embodiments content migration between a plurality of cloud servers is enabled using cooperative middleware.

Also according to embodiments by enhancing mutual compatibility between content and a mobile operating system OS and portability content may be provided regardless of a type of content and an OS of a mobile terminal.

Also according to embodiments cooperative middleware may be employed as a required element to construct an open cloud environment and an in company cloud environment and to manage resources.

Reference will now be made in detail to embodiments of the present invention examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to the like elements throughout. The embodiments are described below in order to explain the present invention by referring to the figures. When it is determined detailed description related to a related known function or configuration they may make the purpose of the present invention unnecessarily ambiguous in describing the present invention the detailed description will be omitted here. Also terminologies used herein are defined to appropriately describe the exemplary embodiments of the present invention and thus may be changed depending on a user the intent of an operator or a custom. Accordingly the terminologies must be defined based on the following overall description of this specification.

Referring to the virtual terminal service providing system may include a terminal a managing server a market server a virtual cloud server and a personal cloud storage .

The managing server may be a server configured to provide an authentication service and a virtual mobile platform service. The market server may be a server configured to provide a platform integrated application.

The virtual cloud server may be a set of at least one server. The virtual cloud server may be a virtual cloud network to which the at least one server is connected.

The terminal may be a terminal that is used by a user. The terminal may be a mobile terminal including a smart phone. The terminal may include a cloud client a platform and firmware .

The cloud client of the terminal may access a virtual gateway of the virtual cloud server and may receive an application of a heterogeneous platform from the virtual gateway of the virtual cloud server . Here the heterogeneous platform may be a platform of a heterogeneous terminal having a type different from a type of the terminal . A heterogeneous platform and a platform of a terminal may indicate platforms in which an application and the like is incompatible.

The managing server may receive terminal information and user information from the terminal and may authenticate the terminal and the user of the terminal based on the received terminal information and user information. The managing server may transfer to the terminal a location address of the virtual gateway in which an application of a heterogeneous platform desired by the terminal is present. Through the above transfer the managing server may control the cloud client of the terminal to be accessible to the virtual gateway .

The virtual cloud server may configure a plurality of virtual terminals by employing a virtual machine in a cloud environment. The aforementioned heterogeneous platform may be a virtual platform of a virtual terminal in which an application requested by a terminal is present among the plurality of virtual terminals.

Each of the plurality of virtual terminals may include or execute an application App a virtual platform the virtual gateway a cloud user interface UI server an operating system OS and a virtual machine VM . Each of the plurality of virtual terminals may include or execute a common hypervisor . Each of the plurality of virtual terminals may further include an emulator to execute a virtual platform. The application may operate on the virtual platform . Each of the plurality of virtual terminals may include common hardware . Here the common hypervisor may indicate that a single hypervisor executed in the virtual cloud server is shared between the plurality of virtual terminals. The common hardware may indicate that hardware of the virtual cloud server is shared between the plurality of virtual terminals and thereby is used.

The virtual gateway of the virtual terminal may transfer a screen of the virtual terminal to the cloud server . The virtual gateway may configure an application that is purchased by the terminal through the market server . The hypervisor as thin layer software may perform virtualization of the common hardware and provide virtualized hardware to the VM .

The virtual cloud serer may perform virtualization of the hardware using cloud technology and may configure an environment of the platform of the terminal on the virtualized hardware . Cloud network technology may be communication network technology of providing a variety of applications to the user based on an on demand scheme by integrating the plurality of virtual terminals using the virtualization technology. The virtual cloud server may employ thin client technology that enables the terminal to access platforms of different environments through a network. The virtual cloud server enables the terminal to access a platform of a virtual terminal having a type different from a type of an actual platform of the terminal . Here the platform of the virtual terminal having the different type may be a platform of a heterogeneous terminal.

The thin client technology may indicate a scheme in which a terminal depends on a central server in using an application and data. For example referring to through the thin client technology the terminal may download all of the application programs from a central server and may obtain all of the data. The terminal may store in the central server all of the modified matters such as data modified in response to an operation of the terminal and the like.

To provide a variety of applications the market server to provide an integrated application of different platforms may be configured. Here the different platforms may be a plurality of virtual platforms of the plurality of virtual terminals. An application of each of the plurality of platforms may be provided to the terminal through the virtual gateway .

The market server may be a store for providing applications of the plurality of platforms. The cloud client of the terminal may access the market server and may purchase an application of a heterogeneous platform from the market server . Here the application of the heterogeneous platform may be an application that operates on the heterogeneous platform instead of operating on the platform of the terminal . The market server may transfer to the plurality of platforms or the plurality of virtual platforms an execution file of the application purchased by the cloud client of the terminal .

According to an embodiment the market server for providing an integrated application market may be configured through the aforementioned operations. In addition an environment in which an application of a heterogeneous platform may be used may be provided and sharing and synchronization of data between the plurality of platforms may be provided.

The personal cloud storage may provide sharing and synchronization of data between the platform of the terminal and the platform of the virtual terminal. Here the platform of the virtual terminal may be the aforementioned heterogeneous platform. The personal cloud storage may store data using a common standard data type of the plurality of virtual terminals or the plurality of virtual platforms. A description related to the personal cloud storage will be further described with reference to .

In the cloud client of the terminal may transmit terminal information user information and application information to the managing server . The terminal information may include information associated with a platform of a terminal a type of the terminal hardware performance of the terminal and a telephone number of the terminal. The telephone number of the terminal may be information used to identify a user. The user information may include information associated with an identifier ID of the user a password of the user and the like. The application information may include information associated with a platform of an application an identification name of the application and the like.

In the managing server may identify a virtual terminal in which an application desired by the terminal is present among the plurality of virtual terminals configured by the virtual cloud server based on the terminal information the user information and the application information that is received from the terminal . The managing server may transmit virtual terminal address information to the terminal . The virtual terminal address information may be information associated with an address of the identified virtual terminal. Here the application desired by the terminal may be an application that is requested by the terminal as an application indicated by the application information received in .

In the managing server may configure a cloud in the virtual cloud server so that the virtual terminal in which the application requested by the terminal is present may be executed. For the above configuration the managing server may transmit virtual platform configuration information to the virtual cloud server . The virtual platform configuration information may be information associated with a configuration of a virtual platform. The managing server enables the application requested by the terminal to be executed in the virtual gateway of the virtual cloud server .

In the cloud client of the terminal may access the cloud UI server of the virtual terminal in which the application requested by the terminal is present. The cloud UI server of the virtual cloud server may transfer a screen of the virtual gateway to the terminal . The virtual gateway may provide to the terminal an actual screen of the application requested by the terminal that is executed in the virtual terminal. Through providing of the screen the terminal may display the actual screen of the application requested by the terminal for the user of the terminal .

Referring to and the terminal and the virtual cloud server may share and synchronize in real time data that is used or generated when executing an application of a heterogeneous platform.

The personal cloud storage may include a data type analyzer a data converter a data read write R W unit and a data storing unit .

To store data that is used and generated when executing an application of a platform of the virtual terminal and an application of a platform of the terminal the data type analyzer of the personal cloud storage may verify and analyze a type of data of the personal cloud storage . The data converter may convert data to data of a standard data type. Next the data R W unit may store data of the standard data type in the data storing unit . An address directory a file and an e mail are illustrated as data of the standard data type. To read data the data converter may read data of the standard data type from the data R W unit and may convert the data of the standard data type to data of a data type of a platform to be used. Application data may be data of the platform to use the data. Here the platform to use the data may be a platform of the terminal or a platform of a virtual machine. Data that is converted to the data type of the platform to use the data may be transferred to the application.

In the market server may transfer application list information to the cloud client of the terminal . The application list information may be information associated with a list of applications.

The terminal may select an application requested by a user from among the list of applications that is transferred through the cloud client . The terminal may transfer to the market server application purchase information requested by the user. The application purchase information may be information associated with an application purchased by a user. The application purchase information may include information such as a platform of an application and an identification name of the application that is to be transferred through the cloud client when executing the application.

The market server may transfer to the virtual terminal of the virtual cloud server information associated with an application purchased by the user and an execution file of the application suitable for a platform of the virtual terminal. That is the market server may configure the application in the virtual gateway of the virtual cloud server and may transfer the execution file of the application to the virtual platform.

In operation the terminal may receive from the market server information associated with an application desired to be purchased.

In operation the market server may provide information associated with the application and an execution file of the application to the virtual cloud server .

In operation the terminal may provide terminal information user information and application information to the managing server .

In operation the terminal may receive information associated with an address of the virtual terminal from the managing server in response to the above providing.

In operation the managing server may provide information associated with a configuration of the virtual platform to the virtual cloud server .

In operation the terminal may access a platform of the virtual terminal of the virtual cloud server .

In operations and the virtual cloud server and the terminal may write application data in the personal cloud storage respectively. Here the application data may be data of the application that is provided to the terminal .

In operations and the virtual cloud server and the terminal may read the application data from the personal cloud storage respectively.

The following embodiments relate to a cooperative middleware apparatus and service method for operating a plurality of different cloud servers with mutual compatibility and interoperability and thereby providing a cloud computing service to a mobile terminal in such a manner that the plurality of different cloud servers may not depend on a service type of each cloud server an OS and a service provider.

Referring to a cooperative middleware apparatus for an open mobile cloud environment may include a connection relay module and a resource managing module .

The management resource module may store content information and virtual terminal information that is stored in each of a plurality of cloud servers . The virtual terminal information may be information associated with a virtual terminal . The resource managing module may determine a cloud server suitable for a user among the plurality of cloud servers based on the stored content information and virtual terminal information. Here the user may be a mobile terminal .

The resource managing module may verify an allocation state of virtual terminals of the determined cloud server and may determine whether to allocate a new virtual terminal based on the verified allocation state.

The resource managing module may verify a location of content to be provided to the user. When the content to be provided to the user is absent in the determined cloud server the resource managing module may determine migration of the content to the determined cloud server from another cloud server in which the content is present among the plurality of cloud servers . Based on whether the new virtual terminal is determined to be allocated and whether the content is determined to be migrated the resource managing module may select the cloud server and may request the selected cloud server for allocating of the new virtual terminal and migration of the content.

Also the resource managing module may generate an access link that enables an access to the virtual terminal of the finally determined cloud server and may transfer the generated access link to the connection relay module .

The resource managing module may monitor quality of a service of content that is provided by the determined cloud server to the user.

In response to a content request from the mobile terminal the connection relay module may perform authentication of the mobile terminal .

The connection relay module may transfer content call information to the resource managing module . The content call information may include the content request of the mobile terminal communication network connection information of the mobile terminal and personal information pre stored by the user.

The connection relay module may receive the access link from the resource managing module and may transfer the received access link to the mobile terminal . Also the connection relay module may monitor a communication state between the mobile terminal and the cloud server providing the content.

The connection relay module may include an access control unit a user profile managing unit a virtual terminal relay unit and a session monitoring unit .

The access control unit may control connection between the mobile terminal and the cooperative middleware apparatus . When the mobile terminal accesses the cooperative middleware apparatus the access control unit may authenticate a user and the mobile terminal based on personal information of the user that is stored in the user profile managing unit . Also the access control unit may verify communication network connection information including information such as a current location of the mobile terminal a type of a communication network being used by the mobile terminal and a current communication state of the mobile terminal by analyzing communication of the mobile terminal .

The user profile managing unit may receive personal information of the user of the mobile terminal from the mobile terminal and may store the personal information in advance. When the mobile terminal makes a request for content the user profile managing unit may generate content call information. The content call information may include personal information of the user of the mobile terminal communication network connection information of the mobile terminal and the content request. The user profile managing unit may transfer the generated content call information to the resource managing module .

The virtual terminal relay unit may transfer to the mobile terminal an access link that is transmitted from the resource managing module . The mobile terminal may access the cloud server that services content through the connection link and may receive a service from the accessed cloud server .

The session monitoring unit enables a service to be smoothly provided by continuously monitoring a communication environment between the mobile terminal and the cloud server providing the content.

The resource managing module may include a provisioning managing unit a service managing unit a QoS managing unit a security managing unit and a virtual terminal managing unit .

The service managing unit may receive from each of the plurality of client servers content information associated with content maintained by a user and content that is currently stored and executed by each of the plurality of client servers . The service managing unit may store the received content information. Also the service managing unit may determine content to be provided to the mobile terminal based on content call information. When a request for content information is received the service managing unit may provide content information of the requested content.

The virtual terminal managing unit may receive virtual terminal information from each of the plurality of cloud servers . The virtual terminal information may include information associated with the virtual terminals currently allocated to each of the plurality of cloud servers and information associated with an OS of each of the virtual terminals . The virtual terminal managing unit may store the received virtual terminal information. When a request for the virtual terminal information is received the virtual terminal managing unit may provide the requested virtual terminal information.

The provisioning managing unit may select a single cloud server from among the plurality of cloud servers based on content call information received from the connection relay module content information provided from the service managing unit and virtual terminal information provided from the virtual terminal managing unit . The provisioning managing unit may verify the virtual terminals allocated to the selected cloud server and may search for a virtual terminal capable of executing the content requested by the mobile terminal from among the virtual terminals allocated to the selected cloud server . When the virtual terminal capable of executing the content requested by the mobile terminal is absent the provisioning managing unit may determine that a new virtual terminal is to be allocated. Also when the content requested by the mobile terminal is not stored in the selected cloud server the provisioning managing unit may determine that the content is to be migrated from the cloud server storing the content to the selected cloud server . Based on the above determination the provisioning managing unit may request the selected cloud server for allocating of the virtual terminal and migration of the content.

The security managing unit may be in charge of security over the cooperative middleware apparatus . The security managing unit may protect personal information of the user stored in the user profile managing unit and content maintained by the user from an external attack such as a hacking attack and the like.

The QoS monitoring unit may check QoS by continuously monitoring content that is executed in the cloud server and is provided to the mobile terminal .

In operation a mobile terminal may request the cooperative middleware apparatus for content desired by a user.

In operation a connection relay module may generate content call information including a request for the received content personal information of the user of the mobile terminal and communication network connection information of the mobile terminal. The connection relay module may transfer the generated content call information to a resource managing module.

In operation the resource managing module may select a single cloud server from among a plurality of cloud servers by using virtual terminal information in which the resource managing module is stored and content information based on content call information received from the connection relay module. The resource managing module may determine allocation of a new virtual terminal and migration of content with respect to the selected cloud server.

In operation the resource managing module may request the selected cloud server for allocating of the virtual terminal and migration of the content based on the above determination.

In operation the resource managing module may generate an access link that enables an access to a virtual terminal of the selected cloud sever. The resource managing module may transfer the generated access link to the connection relay module.

In operation the connection relay module may transfer to the user terminal the access link that is received from the resource managing module.

In operation the cloud server may transfer content information and virtual terminal information to the resource managing module. The resource managing module may store the content information and the virtual terminal information.

An access control unit of the connection relay module may receive a content request from the mobile terminal and may perform an authentication process based on personal information of a user that is stored in a user profile managing unit. The access control unit may transfer communication network connection information and a request for the content to the user profile managing unit by analyzing a current location of the mobile terminal a type of a communication network being used by the mobile terminal and a current communication state of the mobile terminal.

The user profile managing unit may generate content call information by integrating the communication network connection information received from the access control unit the request for content and personal information of the user stored in the user profile managing unit. The user profile managing unit may transfer the generated content call information to a service managing unit of the resource managing module.

The service managing unit may determine content to be provided by comparing the content call information received from the user profile managing unit and the stored content information. The service managing unit may transfer the determined content information and content call information to the provisioning managing unit.

The provisioning managing unit may request the virtual terminal managing unit for virtual terminal information based on the content information and content call information that is received from the service managing unit.

In response to the request of the provisioning managing unit the virtual terminal managing unit may transfer the stored virtual terminal information to the provisioning managing unit.

The provisioning managing unit may select from among a plurality of cloud servers a cloud server suitable to provide a service to the mobile terminal based on virtual terminal information received from the virtual terminal managing unit and content information and content call information received from the service managing unit. The provisioning managing unit may select the cloud server based on a current location of the mobile terminal a type of a communication network of the mobile terminal and a communication state of the mobile terminal. The provisioning managing unit may verify an allocation state of virtual terminals of the selected cloud server. When a suitable virtual terminal is absent as a result of comparing an OS required by the content requested by the mobile terminal and an amount of resources of the virtual terminal with a virtual terminal of the selected cloud server the provisioning managing unit may determine that a new virtual terminal is to be allocated. The provisioning managing unit may verify whether the requested content is present within the selected cloud server and if required may determine that the content is to be migrated from another cloud server. The provisioning managing unit enables the content to be executed in the selected cloud server by requesting the selected cloud server for allocation of the new virtual terminal and the migration of the content based on the determination with respect to the selected cloud server. Also the provisioning managing unit may generate an access link that enables an access to the virtual terminal of the cloud server in which the content is executed and may transfer the access link to a virtual terminal relay unit of the connection relay module.

The virtual terminal relay unit may provide to the mobile terminal through the access control unit the access link received from the provisioning managing unit.

The mobile terminal may access the cloud server through the access link received from the connection relay module and may receive a service from the accessed cloud server. The connection relay module enables the mobile module to smoothly receive a service by continuously monitoring a communication state between the mobile terminal and the cloud server. Also the resource managing module may guarantee excellent QoS by monitoring content provided to the mobile terminal.

The networking unit may be a hardware module such as a network interface card a network interface chip and a networking interface port and may also be a software module such as a network device driver or a networking program.

The processing unit may be at least one processor or at least one core within a processor. The processing unit may perform a function required for operation of the apparatus .

The apparatus may be a terminal a server or middleware described above with reference to through . For example the apparatus may be configured as at least one of the terminal the managing server the market server the virtual cloud server the personal cloud storage the cooperative middleware apparatus the mobile terminal and the cloud server .

The networking unit may perform transmission reception and transfer of data or information of the aforementioned terminal server or middleware.

The processing unit may perform functionalities of constituent elements of the aforementioned terminal server or middleware. The constituent elements of the aforementioned terminal server or middleware may indicate a code a function a library a service a process a thread or a module performed by the processing unit .

For example the hardware may perform the networking unit and the processing unit . The processing unit may execute the hypervisor the VP the OS the cloud UI server the virtual gateway the emulator the virtual platform and the application . The processing unit may execute the cloud client the platform and the firmware . The processing unit may execute the connection relay module and the resource managing module .

Although a few embodiments of the present invention have been shown and described the present invention is not limited to the described embodiments. Instead it would be appreciated by those skilled in the art that changes may be made to these embodiments without departing from the principles and spirit of the invention the scope of which is defined by the claims and their equivalents.

