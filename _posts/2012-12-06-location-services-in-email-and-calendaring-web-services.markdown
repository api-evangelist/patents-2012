---

title: Location services in email and calendaring web services
abstract: An application programming interface (API) method for providing location related search capability to clients of an email and calendaring service is disclosed. In response to a request message from a client, a find place method defined in an API provided by an API service is invoked. The find place method parses the request message for parameters such as a query string or source-related identifier indicating a place name or address of a location to be searched, the culture/format for the search and results, a maximum number of results to be provided, the source of the location to search, and geo-coordinates of the place and/or the user. The parameters are used to query specified source(s). The results of the search are filtered and formatted to provide location information to the client.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09355385&OS=09355385&RS=09355385
owner: Microsoft Technology Licensing
number: 09355385
owner_city: Redmond
owner_country: US
publication_date: 20121206
---
In recent years web services have been growing in popularity. In addition as email and calendaring software evolve to provide more features to end users there is a push to provide new features for email and calendaring in a manner that can be deployed via web services. Currently the location field for a meeting or scheduling request is an underutilized component in calendaring and scheduling software. In order to provide opportunities for client applications to provide enhanced location field functionality an email and calendaring software server will need to be extended to support this functionality and an application programming interface API for an email and calendaring web service will need to expose this functionality.

In order to expose a particular functionality an API method is created along with a corresponding namespace and the structure for the response from the web service is defined. When a particular functionality is exposed a client application can then take advantage of the functionality and present enhanced features to a user of a client device on which the client application is run.

An application programming interface API for email and calendaring web services is disclosed. The API enables client applications to search and retrieve location related data about a place. The location related data includes but is not limited to geo coordinates address website and other business related information.

In some cases by providing a method for searching and retrieving location related data about a place enhanced location fields can be surfaced within client email and calendaring applications. The enhanced location fields can facilitate data entry for users on mobile devices as well as reduce ambiguity in where an appointment or meeting is to take place.

According to an embodiment when an email and calendaring server receives a request from a client application for finding places the server performs a search and retrieves location related data about the place s requested by the client application. The server then sends a response to the client application.

The API method enables users to search for locations based on names street addresses and or a source related identifier.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used to limit the scope of the claimed subject matter.

An application programming interface API method for an email and calendaring web service to provide location related search capability is disclosed. A web services API involves a set of request messages available to a client or server along with a definition of the structure of response messages sent to the client or server . The response messages may be in a markup language such as Extensible Markup Language XML or JavaScript Object Notation JSON .

According to one aspect services are presented to provide enhanced location fields in meeting items. A meeting item includes but is not limited to a meeting request form appointment email calendar entry contact entry and the like. The services include an application programming interface API for email and calendaring web services that enables client applications to search and retrieve location related data about a place. The location related data includes but is not limited to geo coordinates address website and other business related information.

Client applications that benefit from APIs of embodiments of the invention include personal information management PIM software. Some commonly commercially available PIMs include those sold under the brand name MICROSOFT OUTLOOK a registered trademark of Microsoft Corp. and IBM LOTUS NOTES a registered trademark of International Business Machines Corp. For purposes of this discussion PIMs also include separate electronic mail applications such as that available under the brand name MICROSOFT EXCHANGE a registered trademark of Microsoft Corp.

An example email and calendaring web service is the EXCHANGE Web Services EWS which provides an API for clients to be able to create retrieve email items calendar items and contacts as well as access many other functionalities.

According to an embodiment a find places API method is presented for EWS and other email and calendaring web services. A web server or an enterprise email and calendaring server can invoke a find places method in response to a find places request. By surfacing the ability to find places within an email and calendaring software enhanced location fields can be supported for meeting items. The enhancements to the location fields can include but are not limited to providing context supplemental information and suggestions for locations of a meeting item.

The network can include but is not limited to a cellular network e.g. wireless phone a point to point dial up connection a satellite network the Internet a local area network LAN a wide area network WAN a WiFi network an ad hoc network or a combination thereof. Such networks are widely used to connect various types of network elements such as hubs bridges routers switches servers and gateways. The network may include one or more connected networks e.g. a multi network environment including public networks such as the Internet and or private networks such as a secure enterprise private network. Access to the network may be provided via one or more wired or wireless access networks as will be understood by those skilled in the art.

As will also be appreciated by those skilled in the art communication networks can take several different forms and can use several different communication protocols. Certain embodiments of the invention can be practiced in distributed computing environments where tasks are performed by remote processing devices that are linked through a communications network. In a distributed computing environment program modules can be located in both local and remote computer readable storage media.

The web services referenced generally as number are programmable application components that can interact programmatically over the network typically through industry standard Web protocols such as but not limited to extensible markup language XML JavaScript Object Notation JSON Hypertext Transfer Protocol HTTP Representational State Transfer REST and Simple Object Access Protocol SOAP .

Each web service may include one or more servers that execute software to handle requests for particular services. Web services may be configured to perform any one of a variety of different services. Examples of web services include login verification notification database storage stock quoting location directories mapping music electronic wallet calendar scheduler telephone listings news and information games ticketing and so on. The web services can be combined with each other and with other applications to build variably complex systems and intelligent interactive experiences.

Web services may be requested directly by a client device such as device . Web services may also be accessed directly by other servers. According to an embodiment server can access the web services on behalf of a client device such as devices . . . M and even device .

The client devices referenced generally as can be implemented many different ways. For example the client devices can be but are not limited to a personal computer e.g. desktop computer laptop personal digital assistant PDA mobile phone or smart phone tablet slate terminal set top box or gaming console which may be used to access a server such as server over the network . The server may be an enterprise server cloud based server dedicated server host server or the like.

Certain embodiments of the invention are directed to exposing additional capabilities of an email and calendaring server as part of web services supporting scheduling capabilities including email and calendaring functions. To provide the enhanced location capabilities for meeting items the server can be configured to provide an API for location related search capabilities.

According to an embodiment the server can provide an email and calendaring service for client devices . The email and calendaring service can receive email messages and meeting requests addressed to an account associated with a user and can enable the user to retrieve and view such email messages and meeting requests. The email service can also send email messages and meeting requests from the account associated with the user.

A computing device can have hardware including one or more central processing units CPUs memory mass storage e.g. hard drive and I O devices e.g. network interface user input devices . Elements of the computer system hardware can communicate with each other via a bus. Computer system hardware can be configured according to any suitable computer architectures such as a Symmetric Multi Processing SMP architecture or a Non Uniform Memory Access NUMA architecture. The one or more CPUs may include multiprocessors or multi core processors and may operate according to one or more suitable instruction sets including but not limited to a Reduced Instruction Set Computing RISC instruction set a Complex Instruction Set Computing CISC instruction set or a combination thereof. In certain embodiments one or more digital signal processors DSPs may be included as part of the computer hardware of the system in place of or in addition to a general purpose CPU.

In embodiments where the server includes multiple computing devices the server can include one or more communications networks that facilitate communication among the computing devices.

For example the one or more communications networks can include a local or wide area network that facilitates communication among the computing devices. One or more direct communication links can be included between the computing devices. In addition in some cases the computing devices can be installed at geographically distributed locations. In other cases the multiple computing devices can be installed at a single geographic location such as a server farm or an office.

As illustrated in the example of the server includes an API server an email server and database . In various embodiments the API server and the email server can be implemented in various ways. For example the API server and the email server can be implemented as application software utility software or another type of software executed by one or more processing units of computing devices in the server system . Furthermore in some embodiments the API server and the email server can be implemented using one or more application specific integrated circuits ASICs .

The API server can be used to expose functionality available through the email server . The database can store email messages for example in a mailbox contact information and other related information. A mailbox is a type of data repository that represents a storage area for email messages. The user can use a web browser or other application operating on a client device to check and send email messages using an email service provided by the server . Other services that may be available through the server include but are not limited to scheduling and calendaring services contact management services task management services document management services and other types of web services.

The API server provides an API service for server . The API service enables clients such as client device s to invoke methods in an API. The API can include a locations method for an email and calendaring service as described herein.

When a user interacts with a location field via a user interface displayed at a client device the client device provides a request message to the API server . The request message is a request to invoke the location method of the API. When the API server receives the request message the API server invokes a locations method such as described with respect to .

When the API server receives the incoming message the API server determines whether the incoming message includes a find places request . The find places request includes a query that specifies a name or address of a place or a source related identifier of a place. If the incoming message does not include the find places request No of the API server continues to other process es .

If the incoming message includes the find places request Yes of the API server parses the message for location name street address or source related identifier and uses the location name street address or source related identifier to query defined information sources including but not limited to specified web service s mailbox and managed database s .

Once the API server receives the results from the information sources the API server filters the results and generates a response message in an appropriate format . In various embodiments the filtered results e.g. the response data can be formatted in various ways. For example the response data can be formatted as a set of XML elements. In another example the response data can be formatted as a series of comma separated values or name value pairs.

The response message can conform to various communications protocols. For example the response message can conform to the SOAP protocol the RPC protocol the HTTP protocol JSON or another communications protocol. After preparing the outgoing message the API server sends the response message to the client device . For an email application communication between the client device and the API server may be carried out at least in part according to a Simple Mail Transfer Protocol SMTP .

An example process carried out by an email and calendaring server and operating environment are shown in .

A find places method can begin in response to receiving a request message e.g. request message from a client application . The request message received from the client application can be parsed for particular parameters .

In various embodiments the request message is formatted in various ways and may be implemented using XML or JSON for example. In some embodiments the request message is formatted as a SOAP request but other protocols may be used. In an example embodiment the request message is formatted using JSON. According to certain embodiments of the invention a request message e.g. request message invoking the find places method can include a defined FindPlacesType that includes one or more of the following parameters 

The schema for a request to FindPlaces can call a particular mail server or other server providing the email and calendaring services.

The sources parameter is used to indicate the source of the location to search and can be provided as a name or code of the source of the location to search. For example the sources parameter can include a request to search a phonebook service map service a user s mailbox and the like.

The request can indicate the maximum number of results to be provided in the response. This parameter can be set according to screen size of the user s device or by some other constraint.

The culture parameter can be used to indicate the culture specific formatting of a result and can be based on the market being searched. Examples of culture code include en US American English en GB British English ja JP Japanese es MX Spanish Mexico and de DE German .

The request can include a query string to search. The query string may be zero one two or more characters and can be used for example to facilitate an autocomplete or location suggestion within a location field of a meeting item displayed at a client device.

The id parameter can be used to indicate a look up source related identifier of a place. The id may be used in addition to or in place of a query string. A client application can reference a stored identifier the id for locations and use the id to request up to date information regarding the location.

The particular id associated with a location may depend on the source with which the location is associated. That is the id may correspond to the source of the information and be used by the source to provide the most recent information about the location. For example when the location source is a phonebook service the location URI e.g. a uniform resource identifier for a geographic location can be a string of characters providing a unique identification for the location that is understood by the phonebook service. This URI can be stored as the location s id which is used in the look up operation e.g. the find places method on the server for additional information. One example of such an id is a YPID from BING phonebook services. BING is a registered trademark of Microsoft Corp.

The latitude geo coordinate associated with a location or user upon permission of the user can be indicated using the Latitude parameter.

The longitude geo coordinate associated with a location or user upon permission of the user can be indicated using the Longitude parameter.

When the server receives the request message indicating the defined FindPlacesType and the corresponding parameters parsed the server can use the parsed parameters to obtain location information from available sources. For example the location information for the meeting item can be requested by performing a call or calls to the web service s relevant to the query as well as in some embodiments a search of databases associated with the email and calendaring server e.g. database associated with server of .

It should be understood that although web services are illustrated and described with respect to embodiments are not limited to using only web services as sources of location information see e.g. .

An example of web services that may be used in accordance with an embodiment of the invention includes the BING Application Programming Interface API source types including the phonebook source type through the BING Phonebook service and location source type through the BING location service.

For RESTful services the email and calendaring server can perform an HTTP GET request for SOAP services the email and calendaring server can perform an appropriately configured request. The HTTP GET request retrieves whatever information in the form of an entity is identified by the Request URI which may be obtained as part of the request message received by the server and may be the identifier associated with the location being searched .

Returning to other processes may be carried out while waiting for the result response s from the web service call s . Once the results are received the results can be filtered and a response message such as response message of can be generated in an appropriate format . The email and calendaring web service can format the reply obtained from the web services into a manner suitable for transmission to the client application.

For example the reply to the client e.g. response message can be formatted as a SOAP response or other appropriate protocol. The response message may be provided for example in XML or JSON. According to certain embodiments of the invention a response message e.g. response message can include a defined FindLocationResultsType element that includes one or more of the following parameters and or conforms to the following schema 

The DisplayName parameter provides the display name of the place. Example display names include Coffee Shop or Seattle Tacoma International Airport or 123 Main Street .

The LocationSource parameter indicates source of the location information. Examples of sources include but are not limited to the BING Phonebook services the BING Location services and a user s history.

A secondary web site url can be provided from an aggregator site that provides an information page about the place and included in the results through the PersonalHomePages parameter.

Once the appropriate information is filtered and formatted using the defined parameters the generated response message can be transmitted to the client application .

As shown in a user computing device such as a personal computer A laptop B smart phone C tablet D and the like can send a request message to a server . Server can provide an email and calendaring service. The server can also provide a find places API that queries sources of location information in order to facilitate an enhanced location field within a meeting item of a PIM application being operated on a user computing device.

When the server receives the query of the request message the server can request location information from a variety of sources including a mailbox server or mailbox associated with the user managed database or directory service or various web services . The results from the various sources are filtered and formatted to provide a response message to the user computing device.

The results can provide additional information related to a place indicated as part of the location field for a meeting item. By providing the location services client applications can look up location information from sources having up to date information and provide more accurate information about the location of an event or meeting to recipients of a meeting or event request as well as resolving ambiguities for the user choosing the meeting location. For example the user can ensure the right location is being referred to by checking the address within the meeting item user interface. Additionally outdated contact information can be avoided or minimized by dynamically retrieving the most current information from a server in real time.

The location services can also provide additional functionality for client applications including the ability upon receiving permission to search for locations near the user or some other specified location or that the user has used before through a location field of a meeting item. The location search can be based on names or street addresses and search for locations based on a source related identifier for a place such as a YPID.

The following are a few examples of a request and response utilizing some of the available parameters of an API method for providing location related search capability of client applications of an email and calendaring server. The following examples are illustrative of some of the methods applications embodiments and variants of the present invention. They are of course not to be considered in any way limitative of the invention. Numerous changes and modifications can be made with respect to the invention.

By providing the location services as part of an email and calendaring service the physical address and other information regarding a location can be retrieved as needed for the client application instead of being stored locally in a storage media associated with the client device or as part of the email and calendaring server. Upon receiving the response from the server such as via the transmitted response the data is displayed to the user.

In one example case a user may be operating a PIM application through a browser such as available by the webmail service OUTLOOK Web App OWA available from Microsoft Corp. The webmail service enables the user to connect remotely to a mail server such as a MICROSOFT EXCHANGE Server.

The server may be implemented as described with respect to for example. The operating environment shown in may be used in carrying out one or more of the examples described below.

As a user interacts with a location input field of a meeting item the client application can send a request e.g. to server of for the top 8 locations most frequency used by the user by sending in a request message an indication that the message includes a find places request along with a query as follows 

The API server can receive the request message and parse the message for the query id culture maxresults sources latitude and longitude. Here the message includes information regarding the sources to query the maximum results to return the culture format of the information and the particular string to search for i.e. query . The empty string provided for the query facilitates the return of the frequently used strings. In addition the sources are specified in this example using a code however in some embodiments a specific source or URL may be provided in the request message.

For this example embodiment the sources searched can be all sources previously searched in the user s history or all available sources. In this example the searched sources include the BING Phonebook Service the BING Location Service and the user s mailbox.

Once the API server receives the results from the search of the defined sources the results can be filtered and formatted to provide an example response as follows with 3 results 

A user may interact with a location field of a received meeting item in a manner that the client application would present a contact card or other information about a meeting location. When such an interaction occurs the client application can send a request for information about the location by sending in a request message an indication that the message includes a find places request along with a query as follows 

The API server can receive the request message and parse the message for the query id culture maxresults sources latitude and longitude. Here the message includes information regarding the sources to query the maximum results to return the culture format of the information and the particular string to search for i.e. query . In this example a place name Coffee Shop is provided as the query string. It should be understood that in various embodiments a place name may be an actual business name a category or an alias. In some cases the place name can be resolved with geo coordinates and or other information before or after a user sends a meeting item to a recipient.

In this example the sources are specified using a code understood by the API server. Of course in some embodiments a specific source or URL may be provided in the request message.

Once the API server receives the results from the search of the defined sources the results can be filtered and formatted to provide an example response as follows with the combined results from multiple sources about the location 

As a user interacts with a location input field of a meeting item the client application can send a request for the top 8 results for locations previously used by the user by sending in a request message an indication that the message includes a find places request along with a query as follows 

The API server can receive the request message and parse the message for the query id culture maxresults sources latitude and longitude. Here the message includes information regarding the sources to query the maximum results to return the culture format of the information and the particular string to search for i.e. the query .

Once the API server receives the results from the search of the defined sources the results can be filtered and formatted to provide an example response with 2 results as follows 

Certain techniques set forth herein may be described in the general context of computer executable instructions such as program modules executed by one or more computing devices. Generally program modules include routines programs objects components and data structures that perform particular tasks or implement particular abstract data types.

Embodiments may be implemented as a computer process a computing system or as an article of manufacture such as a computer program product or computer readable medium. Certain methods and processes described herein can be embodied as code and or data which may be stored on one or more computer readable media. Certain embodiments of the invention contemplate the use of a machine in the form of a computer system within which a set of instructions when executed can cause the system to perform any one or more of the methodologies discussed above. Certain computer program products may be one or more computer readable storage media readable by a computer system and encoding a computer program of instructions for executing a computer process.

In accordance with embodiments of the invention computer readable media can be any available computer readable storage media or communication media that can be accessed by the computer system.

Communication media includes computer readable instructions data structures program modules or other data in a modulated data signal such as a carrier wave or other transport mechanism and includes any delivery media. The term modulated data signal means a signal that has one or more of its characteristics changed or set in a manner as to encode information in the signal. By way of example and not limitation communication media includes wired media such as a wired network or direct wired connection and wireless media such as acoustic RF infrared and other wireless media. Combinations of any of the above should also be included within the scope of computer readable media.

By way of example and not limitation computer readable storage media may include volatile and non volatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. For example a computer readable storage medium includes but is not limited to volatile memory such as random access memories RAM DRAM SRAM and non volatile memory such as flash memory various read only memories ROM PROM EPROM EEPROM magnetic and ferromagnetic ferroelectric memories MRAM FeRAM and magnetic and optical storage devices hard drives magnetic tape CDs DVDs or other media now known or later developed that is capable of storing computer readable information data for use by a computer system. Computer readable storage media should not be construed or interpreted to include any carrier waves or propagating signals.

In addition the methods and processes described herein can be implemented in hardware modules. For example the hardware modules can include but are not limited to application specific integrated circuit ASIC chips field programmable gate arrays FPGAs and other programmable logic devices now known or later developed. When the hardware modules are activated the hardware modules perform the methods and processes included within the hardware modules.

Any reference in this specification to one embodiment an embodiment example embodiment etc. means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the invention. The appearances of such phrases in various places in the specification are not necessarily all referring to the same embodiment. In addition any elements or limitations of any invention or embodiment thereof disclosed herein can be combined with any and or all other elements or limitations individually or in any combination or any other invention or embodiment thereof disclosed herein and all such combinations are contemplated with the scope of the invention without limitation thereto.

It should be understood that the examples and embodiments described herein are for illustrative purposes only and that various modifications or changes in light thereof will be suggested to persons skilled in the art and are to be included within the spirit and purview of this application.

