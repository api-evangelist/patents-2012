---

title: Service opening method and system, and service opening server
abstract: Embodiments of the present invention relate to a service opening method and system, and a service opening server. The method includes: receiving a service request from a third-party application, where the service request carries type and parameter information of the requested service; querying, according to the type information of the service, a service directory to obtain an access address and authentication type information of the requested service; when it is determined that the invoking of the service needs an authorization of an end user, obtaining an authorization notification message of the end user according to the type information of the service and the parameter information of the service; and forwarding, the service request to a capability server, and forwarding, to the third-party application, a service response message returned by the capability server. The control of the end user on the authorized service is ensured to the greatest extent.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08584231&OS=08584231&RS=08584231
owner: Huawei Technologies Co., Ltd.
number: 08584231
owner_city: Shenzhen
owner_country: CN
publication_date: 20120917
---
This application is a continuation of International Patent Application No. PCT CN2011 071071 filed on Feb. 18 2011 which claims priority to Chinese Patent Application No. 201010136980.X filed on Mar. 17 2010 both of which are hereby incorporated by reference in their entireties.

Embodiments of the present invention relate to the field of network technologies and in particular to a service opening method and system and a service opening server.

With the flourishing development of telecommunications and the Internet as well as the great abundance of information resources openness of various services has become a research focus. Internet vendors open valuable service resources and telecommunication operators also open telecommunication services in multiple manners so that the network ecological chain flourishes to achieve an all win purpose. Certainly an application programming interface API cannot conveniently open all services to third party applications and moreover in the current environment it is reasonable that many service resources are opened after an end user at the client side authorizes the resources or after a user identity verification is performed. For example when opening private information of users the API needs to directly charge at the terminal side for services opened by the telecommunication operators verifies and authorizes private information of users.

In the conventional art telecommunication operators open telecommunications services for example SMS message WAP PUSH and multimedia message to the third party applications through an integrated service access gateway ISAG . The ISAG application provides a Parlay X2.0 interface which is in compliance with the international standards enhances the interface properly and provides richer service resources. The ISAG hides the complexity of the underlying network and achieves high abstraction of services such as mobile data mobile voice personal handy phone system PHS and encapsulates the services into an open unified and standard application development interface which is then provided to content providers service providers CPs SPs and supports accesses of telecommunication operators self run value added services accesses of third party CP SP value added services or accesses of enterprise applications. The ISAG provides CPs SPs with integrated development and test environment for unified value added applications and implements functions such as verification authentication charging and management in the service application process in coordination and combination with an integrated services management platform ISMP .

The ISAG application can solve the authentication problem between service developers that is users of capability APIs and the operators but still cannot solve the problem that exists when end users authenticate requested services.

The objective of embodiments of the present invention is to provide a service opening method and system and a service opening server so as to ensure an end user s control and processing capabilities on services requiring authorization and ensure interests of the end user.

receiving a service request from a third party application where the service request carries type information of a requested service and parameter information of the requested service 

according to the type information of the service querying a service directory to obtain an access address and authentication type information of the requested service and

when it is determined according to the authentication type information that the invoking of the service needs an authorization of an end user 

according to the type information of the service and the parameter information of the service obtaining an authorization notification message of the end user and according to the access address forwarding the service request to a capability server and forwarding to the third party application a service response message returned by the capability server.

a receiving module configured to receive a service request from a third party application where the service request carries type information of a requested service and parameter information of the requested service 

a first obtaining module configured to query according to the type information of the service a service directory to obtain an access address and authentication type information of the service 

a second obtaining module configured to when it is determined according to the authentication type information that the invoking of the service needs an authorization of an end user obtain an authorization notification message of the end user according to the type information of the service and the parameter information of the service and

a forwarding module configured to forward according to the access address the service request to a capability server and forward to the third party application a service response message returned by the capability server.

An embodiment of the present invention provides a service opening system where the system includes a first server and a second server on which a third party application is set where the first server is the service opening server described in the foregoing technical solutions.

The first server receives a service request from the third party application set on the second server where the service request carries type information of a requested service and parameter information of the requested service the first server queries according to the type information of the service a service directory to obtain an access address and authentication type information of the service when it is determined according to the authentication type information that the invoking of the service needs an authorization of an end user the first server obtains an authorization notification message of the end user according to the type information of the service and the parameter information of the service and the first server forwards according to the access address the service request to a capability server and forwards to the third party application a service response message returned by the capability server.

In the service opening method and system and the service opening server provided by the embodiments of this present invention if it is determined according to the authentication type information that the invoking of the requested service needs an authorization of an end user an authorization notification message of the end user is obtained according to the type information of the service and the parameter information of the service. In this manner the control of the end user on the authorized service is ensured to the greatest extent and an untrusted third party application is effectively prevented from violating interests of the end user thereby ensuring the interests of the end user.

The technical solutions according to the embodiments of the present invention are clearly and completely described in the following with reference to the accompanying drawings. Apparently the embodiments in the following description are merely a part rather than all of the embodiments of the present invention. All other embodiments obtained by persons of ordinary skill in the art based on the embodiments of the present invention without creative efforts shall fall within the protection scope of the present invention.

Because a lot of service resources are closely associated with an end user corresponding to a client in a service opening scenario for example personal information and friends list of a user and a service which is intended to directly charge the end user corresponding to the client. The opening of the service resources need to be authenticated and authorized by the end user corresponding to the client.

In addition in the embodiment shown in the system architecture further includes a third party application a capability server and a client Client . The third party application is configured to subscribe to a service provided by the embodiment of the present invention and provide a service for an end user that uses the client where the third party application may specifically be an application provided by a service provider the capability server is configured to serve as a capability server registered in the system environment described in the embodiment of the present invention where the capability server may specifically be a location server of the service provider and the end user uses the third party application through the client .

Step Receive a service request from a third party application where the service request carries type information of a requested service and parameter information of the service.

Step Query according to the type information of the service a service directory to obtain an access address and authentication type information of the service.

Step When it is determined according to the authentication type information that the service needs an authorization of an end user obtain an authorization notification message of the end user according to the type information of the service and the parameter information of the service.

Step Forward according to the access address the service request to a capability server and forward to the third party application a service response message returned by the capability server.

In the service opening method provided by the embodiment of the present invention when it is determined according to the authentication type information that the invoking of the requested service needs an authorization of an end user an authorization notification message from the end user is obtained according to the type information of the requested service and the parameter information of the requested service. In this manner the control of the end user on the authorized service is ensured to the greatest extent and an untrusted third party application is prevented from violating interests of the end user effectively thereby ensuring the interests of the end user.

Step Receive a service request from a third party application where the service request carries type information of a requested service and parameter information of the requested service.

The third party application may be hosted on a server and is capable of subscribing to a service provided by a service provider Service Provider SP for short the type information of the service may specifically be services indicated by ordinary strings such as weather SMS message and or stock information query the parameter information of the service may further include an end user s identity ID through which a server device related to this embodiment of the present invention is enabled to identify identity information of the end user.

Step Query according to the type information of the service a service directory unit to obtain an access address and authentication type information of the service.

The authentication type information may specifically include a service may be invoked from the SP without an authorization of an end user a service may be invoked from the SP with an authorization of the end user and a service may be invoked with an authorization of the SP. Certainly for different services different authentication types may be set according to a security level designated by the end user.

Step When it is determined according to the authentication type information that the invoking of the service needs an authorization of an end user generate according to the parameter information a parameter identity ID corresponding to the parameter information.

Because the parameter information includes specific parameters for accessing a service for example if a picture is uploaded the parameter information includes picture content of the picture. For the generation of a parameter identity corresponding to parameter information according to the parameter information reference may be made to an implementation scheme in the prior art where the parameter identity may be a simple string. Furthermore because information amount of the parameter information is greater than that of the parameter identity during the process that a server device transmits information the load of information transmission over a network may be decreased by using the parameter identity.

Step Send an authentication address carrying the type information and the parameter identity to a client through the third party application.

The authentication address may specifically be a uniform universal resource locator Uniform Universal Resource Locator URL for short for authentication. Because the URL is generated according to the type information and the parameter identity the URL carries the type information and the parameter identity ID . In addition the URL may further carry token TOKEN information where the token TOKEN information is used to perform token encryption on other information except the token TOKEN part in the URL so as to prevent a third party application from tampering with the URL during the transfer of the URL for authentication and the other information may be at least one of an authentication address a parameter identity and a service type.

Step A client uses a browser to access an identity management unit through the authentication address and the identity management unit determines whether the authentication address is modified and if yes it indicates that the authentication address has been modified terminate the invoking process if no it indicates that the authentication address has not been modified perform step .

Step Obtain user password information input by the end user through a web page corresponding to the authentication address.

Step If the password information is successfully verified send description information and the parameter information of the requested service to the client.

The description information and the parameter information which is carried in a service request need to be obtained. The description information of the service to be requested may be obtained through the following procedure for example querying according to a service type a service directory to obtain the description information obtaining according to the parameter identity the parameter information carried in the service request and then sending the description information and the parameter information to the client.

Step The identity management unit obtains an authorization notification message where the authorization notification message is sent by the end user according to the description information and the parameter information and sends the authorization notification message to a capability opening management and control unit.

Step The capability opening management and control unit forwards the service request to a capability server according to the access address and forwards to the third party application a service response message returned by the capability server.

In the service opening method provided by the embodiment of the present invention if it is determined according to the authentication type information that the service corresponding to the service request needs an authorization of an end user at the client side an authorization notification message of the client is obtained according to the parameter information of the service. In this manner the control of the client on the authorized service is ensured to the greatest extent and an untrusted third party application is effectively prevented from violating interests of the end user thereby ensuring the interests of the end user.

Furthermore based on the embodiments shown in and if the service request of the third party application carries a callback address the forwarding to the third party application the service response message returned by the capability server may specifically be 

forwarding to the third party application corresponding to the callback address the service response message returned by the capability server specifically if the callback address indicates the third party application which initially sends the service request sending the service response message to a third party application which initially sends the service request if the callback address indicates a third party application which does not initially send the service request sending the service response message to other third party applications. The callback address may specifically be an Internet protocol Internet Protocol IP for short address of a server where the third party application is located and a port number corresponding to the IP address or an full qualified domain name and a port corresponding to the full qualified domain name but is not limited to the foregoing listed cases provided that the service response message returned by the capability server can be forwarded to the third party application corresponding to the callback address according to the callback address.

The third party application may be hosted on a server and is capable of subscribing to a service provided by a service provider Service Provider SP for short .

Step The third party application sends a service request to the capability opening management and control unit where the service request carries type information of a requested service parameter information of the service and a callback address.

The type information of the service may specifically be services indicated by ordinary strings such as weather SMS message and stock information query the parameter information of the service may further include an identity ID of an end user. The callback address may specifically be an Internet protocol Internet Protocol IP for short address of a server where the third party application is located and a port number corresponding to the IP address or an full qualified domain name and a port corresponding to the full qualified domain name but is not limited to the foregoing listed cases provided that the service response message returned by the capability server can be forwarded according to the callback address to the third party application corresponding to the callback address.

Step The capability opening management and control unit sends according to the type information a query request to the service directory functional unit.

The query request may specifically be a hypertext transfer protocol Hypertext Transfer Protocol HTTP for short query request.

Step The service directory functional unit queries according to the query request an access address and the authentication type information that correspond to the type information and returns the access address and the authentication type information of the service to the capability opening management and control unit.

The authentication type information may specifically include a service may be invoked from the SP without an authorization of an end user a service may be invoked from the SP with an authorization of the end user and a service may be invoked from the SP with an authorization of the service provider. For different services different authentication types may be set according to a security level designated by the end user.

Step The capability opening management and control unit determines according to the authentication type information returned by the service directory functional unit whether the service request needs an authorization of the end user at a client side.

Step If it is determined that the service request needs the authorization of the end user the capability opening management and control unit stores parameter information generates a parameter identity ID corresponding to the parameter information and returns an authentication address generated according to the type information and the parameter identity to the third party application.

For the generation of the parameter identity corresponding to the parameter information according to the parameter information reference may be made to an implementation scheme in the prior art where the parameter identity may specifically be a simple string. The authentication address may be a URL for authentication. Because the URL is generated according to the type information and the parameter identity the URL carries both the type information and the parameter identity ID . In addition the URL may further carry token TOKEN information where the token TOKEN information is used to perform token encryption on other information for example at least one of the authentication address the parameter identity and the service type except the token TOKEN part in the URL so as to prevent the third party application from tampering with the URL during the transfer of the URL for authentication. Specifically a hash hash algorithm may be used to perform the token encryption on the information.

Step After determining according to the token TOKEN information in the URL that the URL is not modified during the process the identity management unit queries the service directory unit for description information corresponding to the type information.

Step The identity management unit queries the capability opening management and control unit for a service parameter value param value corresponding to the parameter identity ID .

Step The capability opening management and control unit returns the service parameter value to the identity management unit.

Step The identity management unit returns a user authentication page to the client so that the end user can log in through the user authentication page of the client.

Step After obtaining through the client password information input by the user the identity management unit presents the description information and the service parameter value of the service to the client and sends to the client a request for querying whether to authorize the service for this time.

Step If the client receives the end user s an authorization notification message of agreeing to grant authorization the client sends to the identity management unit the authorization notification message of agreeing to grant authorization and the identity management unit returns to the client a response page indicating successful authentication.

Step The identity management unit sends to the capability opening management and control unit a message indicating that the user authentication succeeds.

Step The capability opening management and control unit returns a response message to the identity management unit.

Through the process of step to step the end user implements the procedure of authorizing a service requested. After the authorization performed by the end user the process of the following step to step may be used to access a service provided by a capability provider according to the service request or when the third party application sends the service request again the process of the following step to step may also be used to access a service provided by the capability provider.

Step The capability opening management and control unit requests according to the access address of the service the capability server where the capability provider is located to provide the service corresponding to the parameter information.

Step The capability opening management and control unit receives a service response message returned by the capability server.

Step The capability opening management and control unit sends according to the callback address carried in the service request the service response message to a server corresponding to the callback address.

Step The capability opening management and control unit receives a service response message from the server corresponding to the callback address.

For example if the service requested by the service request is weather forecast weather in an area A the service response message may request a service corresponding to the service request for this time that is the specific content of the weather forecast in the area A for example weather conditions in the last three days. The specific content corresponding to the service may be determined by the SP.

In the service opening method provided by the embodiment of the present invention if it is determined according to the authentication type information that the invoking of the requested service needs an authorization of an end user an authorization notification message of the end user is obtained according to the type information of the service and the parameter information of the service. In this manner the control of the end user on the authorized service is ensured to the greatest extent and an untrusted third party application is effectively prevented from violating interests of the end user thereby ensuring the interests of the end user. In addition the opening scale of the service capability is enriched and richer service capabilities are provided to the third party application so that the whole ecological chain flourishes.

Parameter information of the service includes the end user s identity ID through which a server device related to this embodiment of the present invention is enabled to identify identity information of the end user.

Step The third party application sends a service request to a capability opening management and control unit where the service request carries type information of a service to be requested and parameter information of the service to be requested.

The type information of the service may specifically be services indicated by ordinary strings such as weather SMS message and stock information query the parameter information of the service may further include an identity ID of the end user.

Step The capability opening management and control unit sends according to the type information a query request to the service directory functional unit.

The query request may specifically be a hypertext transfer protocol Hypertext Transfer Protocol HTTP for short query request.

Step The service directory functional unit queries according to the query request an access address and the authentication type information that correspond to the type information and returns the access address and the authentication type information of the service to the capability opening management and control unit.

The authentication type information may specifically include a service may be invoked from an SP without an authorization of an end user a service may be invoked from the SP with an authorization of the end user and a service may be invoked from the SP with an authorization of the service provider. For different services different authentication types may be set according to a security level designated by the end user.

Step The capability opening management and control unit determines according to the authentication type information returned by the service directory functional unit whether the service request needs to use an authorization of the end user of a terminal.

Step If it is determined that the service request needs the authorization of the end user the capability opening management and control unit stores the parameter information of the service generates a parameter identity ID corresponding to the parameter information of the service and returns an authentication address generated according to the type information and the parameter identity to the third party application.

For the generation of the parameter identity corresponding to the parameter information according to the parameter information reference may be made to an implementation scheme in the prior art where the parameter identity may specifically be a simple string. The authentication address may be a URL for authentication. Because the URL is generated according to the type information and the parameter identity the URL carries both the type information and the parameter identity ID . In addition the URL may further carry token TOKEN information where the token TOKEN information is used to perform token encryption on other information for example at least one of the authentication address the parameter identity and the service type except the token TOKEN part in the URL so as to prevent the third party application from tampering with the URL during the transfer of the URL for authentication. Specifically a hash hash algorithm may be used to perform the token encryption on the information.

Step After determining according to the token TOKEN information in the URL that the URL is not modified during the process the identity management unit queries the service directory unit for description information corresponding to the service type.

Step The identity management unit queries the capability opening management and control unit for a service parameter value param value corresponding to the service parameter identity ID .

Step The capability opening management and control unit returns the service parameter value to the identity management unit.

Step The identity management unit returns a user authentication page to the terminal so that the end user can log in through the user authentication page on the terminal.

Step After the terminal obtains user password input by the user the identity management unit presents the service description and the service parameter value of the service to the terminal and sends to the terminal a request for querying whether to authorize the service for this time.

Step If the client receives an authorization notification message of agreeing to grant authorization of the end user the client sends the authorization notification message to the identity management unit and the identity management unit returns to the client a response page indicating successful authentication.

The response page further includes an access token Access Token for the service which has been authorized and may be invoked.

Step The identity management unit sends to the capability opening management and control unit a message indicating that the user authentication succeeds and a corresponding access token Access Token .

Step The capability opening management and control unit returns a response message to the identity management unit.

Through the process of step to step the end user implements the procedure of authorizing a requested service. After the authorization performed by the end user the process of the following step to step may be used to access a service provided by a capability provider according to the service request or when the third party application sends the service request again the process of the following step to step may also be used to access a service provided by the capability provider.

Step Through the third party application hosted on the terminal the end user initiates a service request to the capability opening functional unit where the service request carries an access token Access Token .

Step After confirming that the access token Access Token is the access token in step the capability opening functional unit initiates a service request to a capability server where a registered capability provider is located.

Step The capability opening management and control unit receives a service response message returned by the capability server.

Step The capability opening management and control unit sends the service response message to the terminal where the third party application is located.

For example if the service requested by the service request is weather forecast weather in an area A the service response message may request a service corresponding to the service request for this time that is the specific content of the weather forecast in the area A for example weather conditions in the last three days. The specific content corresponding to the service may be determined by the SP.

In the service opening method provided by the embodiment of the present invention if it is determined according to the authentication type information that the server corresponding to the service request needs an authorization of an end user at the client side an authorization notification message of the client is obtained according to the parameter information of the service. In this manner the control of the client on the authorized service is ensured to the greatest extent and an untrusted third party application is effectively prevented from violating interests of the end user thereby ensuring the interests of the end user. In addition the opening scale of the service capability is enriched and richer service capabilities are provided to the third party application so that the whole ecological chain flourishes.

The receiving module receives a service request from a third party application where the service request carries type information of a requested service and parameter information of the requested service the first obtaining module queries according to the type information of the service a service directory to obtain an access address and authentication type information of the service when it is determined according to the authentication type information that the service needs to be requested with an authorization of the end user the second obtaining module obtains an authorization notification message of the end user according to the type information of the service and the parameter information of the service and the forwarding module forwards according to the access address the service request to a capability server and forwards to the third party application a service response message returned by the capability server.

In the service opening server provided by the embodiment of the present invention when it is determined according to the authentication type information that the invoking of a requested service needs an authorization of an end user the second obtaining module obtains an authorization notification message of the end user according to the type information of the requested service and the parameter information of the requested service. In this manner the control of the client on the authorized service is ensured to the greatest extent and an untrusted third party application is effectively prevented from violating interests of the end user thereby ensuring the interests of the end user.

The receiving module receives a service request from a third party application where the service request carries type information of a requested service and parameter information of the requested service the first obtaining module queries according to the type information of the service a service directory to obtain an access address and authentication type information of the service when it is determined according to the authentication type information that the invoking of the service needs an authorization of the end user the second obtaining module obtains an authorization notification message of the end user according to the type information of the service and the parameter information of the service and the forwarding module forwards according to the access address the service request to a capability server and forwards to the third party application a service response message returned by the capability server.

Furthermore the second obtaining module may further include an identity generating unit a first sending unit and an obtaining unit . The identity generating unit generates according to the parameter information a parameter identity corresponding to the parameter information the first sending unit sends an authentication address carrying the type information and the parameter identity to a client through the third party application and the obtaining unit obtains an authorization notification message where the authorization notification message is confirmed by the end user through the authentication address.

Furthermore the obtaining unit may further include a determination subunit a first obtaining subunit a sending subunit and a second obtaining subunit . The determination subunit determines whether the authentication address is modified if it is determined that the authentication address is not modified the first obtaining subunit obtains password information that is sent by the end user through the authentication address and if the password information is successfully verified the sending subunit sends description information and parameter information of the requested service to the client and the second obtaining subunit obtains an authorization notification message where the authorization notification message is sent by the end user according to the description information and the parameter information.

Furthermore the second obtaining subunit may further include a first obtaining device a second obtaining device and a sending device. The first obtaining device queries according to the type information the service directory to obtain the description information the second obtaining device obtains according to the parameter identity the parameter information carried in the service request and the sending device sends the description information and parameter information to the client.

Furthermore if the service request carries a callback address the forwarding module may further include a second sending unit configured to forward to a third party application corresponding to the callback address a service response message returned by the capability server.

In the service opening server provided by the embodiment of the present invention when it is determined according to the authentication type information that the invoking of a requested service needs an authorization of an end user the second obtaining module obtains an authorization notification message of the end user according to the type information of the requested service and the parameter information of the requested service. In this manner the control of the client on the authorized service is ensured to the greatest extent and an untrusted third party application is effectively prevented from violating interests of the end user thereby ensuring the interests of the end user.

The first server receives a service request from the third party application hosted on the second server where the service request carries type information of a requested service and parameter information of the request service the first server queries according to the type information of the service a service directory to obtain an access address and authentication type information of the service if it is determined according to the authentication type information that the invoking of the service needs an authorization of an end user the first server obtains an authorization notification message of the end user according to the type information of the service and the parameter information of the service and the first server forwards according to the access address the service request to a capability server and forwards to the third party application on the second server a service response message returned by the capability server.

In the service opening system provided by the embodiment of the present invention when it is determined according to the authentication type information that the invoking of a requested service needs an authorization of an end user the first server obtains an authorization notification message of the end user according to the type information of the requested service and the parameter information of the requested service. In this manner the control of the client on the authorized service is ensured to the greatest extent and an untrusted third party application is effectively prevented from violating interests of the end user thereby ensuring the interests of the end user.

Through the technical solutions according to the embodiments of the present invention the problem of service opening which needs an authorization of an end user is ensured and solved. Furthermore the embodiments of the present invention show details such as service parameter of operations on authorized service resources to an end user. Therefore the control of the end user on authorized resources is ensured to the greatest extent and technically an untrusted third party application is effectively prevented from violating interests of the end user thereby ensuring the interests of the end user. In addition the opening scale of the service capability is enriched and richer service capabilities are provided to the third party application so that the whole ecological chain flourishes.

It can be clearly understood by persons skilled in the art that for the purpose of convenient and brief description for a detailed working process of the foregoing systems devices modules and units reference may be made to the corresponding process in the method embodiments and the details are not be described herein again.

Persons of ordinary skill in the art should understand that all or a part of the steps according to the embodiments of the present invention may be implemented by a program instructing relevant hardware. The program may be stored in a computer readable storage medium. When the program is run the steps of the method according to the embodiments of the present invention are performed. The storage medium may be any medium that is capable of storing program codes such as a ROM a RAM a magnetic disk or an optical disk.

Finally it should be noted that the above embodiments are merely provided for describing the technical solutions of the present invention but not intended to limit the present invention. It should be understood by persons of ordinary skill in the art that although the present invention has been described in detail with reference to the embodiments modifications can be made to the technical solutions described in the embodiments or equivalent replacements can be made to some technical features in the technical solutions as long as such modifications or replacements do not cause the essence of corresponding technical solutions to depart from the spirit and scope of the present invention.

