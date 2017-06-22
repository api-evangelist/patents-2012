---

title: System and method for providing a rest-based management service in a traffic director environment
abstract: Described herein are systems and methods for providing software administration tools, for use in administering server configurations, such as in a traffic director or other type of server environment. In accordance with an embodiment, the system comprises a traffic director having one or more traffic director instances, which is configured to receive and communicate requests, from clients, to origin servers having one or more pools of servers. An administration server can be used to manage the traffic director, including a REpresentational State Transfer (REST) infrastructure and management service which maps REST calls to mbeans or other management components registered on the administration server, for use in managing the traffic director.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08782769&OS=08782769&RS=08782769
owner: Oracle International Corporation
number: 08782769
owner_city: Redwood Shores
owner_country: US
publication_date: 20120926
---
A portion of the disclosure of this document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the document or the disclosure as it appears in the and Trademark Office file or records but otherwise reserves all copyright rights whatsoever.

This application claims the benefit of priority to U.S. Provisional Application No. 61 539 886 titled SYSTEMS AND METHODS FOR USE WITH AN APPLICATION SERVER TRAFFIC DIRECTOR CORE FEATURES filed Sep. 27 2011 and U.S. Provisional Application No. 61 539 900 titled SYSTEMS AND METHODS FOR USE WITH AN APPLICATION SERVER TRAFFIC DIRECTOR ADMIN FEATURES filed Sep. 27 2011 each of which applications are herein incorporated by reference.

The invention is generally related to software administration tools for use in administering server configurations and is particularly related to a system and method for providing a rest based management service in a traffic director or other type of server environment.

A typical enterprise level computing environment can include many different types of computing resources e.g. web servers application servers database servers or other types of resource servers which are intended to be accessed over a network e.g. a company s internal Ethernet network or the Internet by other computers or by users operating various different types of computing devices. A familiar example is the use of a client computer such as a laptop equipped with a web browser application by which a user can access a web server via the Internet.

Today s organizations rely increasingly on their computing resources being readily available from almost any location at all times with a high level of performance. The task of ensuring that such resources are allocated efficiently often requires the use of a load balancing device to distribute requests from clients to target resources in a fair manner according to its distribution policies. These are the types of environments that embodiments of the invention can be used with.

Described herein are systems and methods for providing software administration tools for use in administering server configurations such as in a traffic director or other type of server environment. In accordance with an embodiment the traffic director referred to herein in some embodiments as Oracle Traffic Director OTD is provided as a software based load balancer that can be used to deliver a fast reliable scalable and secure platform for load balancing Internet and other traffic to back end origin servers such as web servers application servers or other resource servers.

In accordance with an embodiment the system comprises a traffic director having one or more traffic director instances which is configured to receive and communicate requests from clients to origin servers having one or more pools of servers. An administration server can be used to manage the traffic director including a REpresentational State Transfer REST infrastructure and management service which maps REST calls to mbeans or other management components registered on the administration server for use in managing the traffic director. Embodiments of the invention can also be used with other types of server environment.

As described above today s organizations rely increasingly on their computing resources being readily available from almost any location at all times with a high level of performance. The task of ensuring that such resources are allocated efficiently often requires the use of a load balancing device to distribute requests from clients to target resources in a fair manner according to its distribution policies. It is also desirable to be able to manage or administer such systems efficiently and securely.

Described herein are systems and methods for providing software administration tools for use in administering server configurations and in particular a system and method for providing a rest based management service. In accordance with an embodiment the systems and methods can be used with a server environment such as a traffic director referred to herein in some embodiments as Oracle Traffic Director OTD which is provided as a software based load balancer that can be used to deliver Internet and other traffic to back end origin servers such as web servers application servers or other resource servers.

In accordance with an embodiment the traffic director serves as an entry point for traffic such as hypertext transfer protocol HTTP and hypertext transfer protocol secure HTTPS requests which are received from clients or client devices for communication to a back end of resources or resource servers acting as origin servers. Each traffic director includes one or more traffic director instances defined by a configuration wherein the configuration provides information about various elements of that instance such as listeners origin servers failover groups and logs.

Examples of the types of clients that can be used with the system include computer servers laptop computers portable devices such as smartphones and other types of computing devices some of which may include e.g. a web browser application for accessing a web server.

Examples of the types of resources that can be used as origin servers include lightweight directory access protocol LDAP servers web servers multimedia servers application servers database servers and other types of resources.

From an administration perspective in accordance with an embodiment the traffic director is designed to be easy to install configure and use and can include a simple wizard driven graphical interface as well as a robust command line interface for use by an administrator in managing traffic director instances. For any particular organization depending on their business requirements such as the number of back end applications for which they want to use the traffic director to balance requests their internal requirements such as security and the traffic director features they wish to use the traffic director topology can be varied to address their needs.

In accordance with an embodiment the following terms are used herein. It will be evident that in accordance with other embodiments additional and or different terms can be used. Configuration A collection of configurable elements e.g. metadata that determines the run time behavior of a traffic director instance. In accordance with an embodiment a typical configuration contains definitions for listeners e.g. IP address and port combinations on which the traffic director should listen for requests together with information about servers at the back end to which the requests should be sent. The traffic director can read the configuration when a traffic director instance starts and while processing client requests.

Instance Traffic Director Instance A traffic director server that is instantiated from a configuration and deployed on an administration node or the administration server.

Cluster A collection of two or more traffic director instances that are created from the same configuration.

Administration Server A specially configured traffic director instance that hosts the interfaces including administration console and command line interface through which an administrator can create traffic director configurations deploy them as instances on administration nodes and manage the instances.

Administration Node A physical server that is designated as a host on which the administrator can deploy traffic director instances. In accordance with an embodiment on a given node the administrator can deploy only one instance of a configuration.

INSTANCE HOME A directory of the administrator s choice on the administration server or an administration node in which the configuration data and binary files pertaining to traffic director instances are stored.

ORACLE HOME A directory of the administrator s choice in which the administrator installs the traffic director binaries.

Administration Console A web based graphical interface on the administration server that the administrator can use to create deploy and manage traffic director instances.

Client In accordance with an embodiment an agent e.g. a web browser or an application that sends requests e.g. HTTP and HTTPS requests to traffic director instances. Examples of the types of clients that can be used with the system include computer servers laptop computers portable devices such as smartphones and other types of computing devices some of which may include e.g. a web browser application for accessing a web server.

Origin Server In accordance with an embodiment a resource or server at the back end to which the traffic director forwards the requests that it receives from clients and from which it receives responses to client requests. Examples of the types of resources that can be used as origin servers include lightweight directory access protocol LDAP servers web servers multimedia servers application servers database servers and other types of resources.

Origin server Pool A collection of origin servers that host the same application or service and that the administrator can load balance by using the traffic director. In accordance with an embodiment the traffic director distributes client requests to servers in the origin server pool based on the load distribution method s that are specified for that pool.

Virtual Server A virtual entity within a traffic director server instance that provides a unique IP address or host name and port combination through which the traffic director can serve requests for one or more domains. In accordance with an embodiment a traffic director instance on a node can contain multiple virtual servers. The administrator can configure settings such as the maximum number of incoming connections specifically for each virtual server and can also customize how each virtual server handles requests.

In accordance with an embodiment the back end can include one or more origin servers . Each of the origin servers can communicate with one another and with the traffic director via an internal network such as an Ethernet network. The traffic director can receive requests from clients via the Internet and in the case of many organizations a firewall .

In accordance with an embodiment from an administration perspective the server environment is designed to be easy to install configure and use and can include a simple wizard driven graphical interface as well as a robust command line interface for use by an administrator in managing server instances. At least one of the server instances can be designated an administration node . An administration server includes an administration interface which in turn includes one or more of an administration console GUI and or a command line interface that enables an administrator to configure or otherwise administer the server environment or its server instances.

In accordance with an embodiment a configuration is a collection of configurable elements that determines the run time behavior of a server instance. A typical configuration may contain e.g. definitions for listeners on which the traffic director should listen for requests together with information about servers at the back end to which the requests should be sent. The server environment e.g. traffic director can read the configuration when a server instance starts and while processing client requests. An administrator can define configurations for server instances which are stored in a configuration store on the administration server. The administrator can then instantiate a configuration by deploying it on one or more administration nodes.

It will be evident that the example shown in is provided for purposes of illustration and that in accordance with other embodiments different types of server environment and different deployment scenarios can be used.

In accordance with an embodiment the server environment e.g. traffic director environment includes a REpresentational State Transfer REST infrastructure and management service which enables management of the environment while at the same time allowing flexible evolution of the REST interfaces and the back end data model. The REST infrastructure maps HTTP REST calls to respective mbeans or other management components that are registered on the administration server. In accordance with an embodiment a Java web application or REST web service can be deployed on the administration server and can expose a set of REST APIs most of which finally map to their respective mbeans or management components registered on the administration server while others return web application specific data e.g. information about a session or information about a logged in user.

In accordance with an embodiment a HTTP request is handled by the REST infrastructure as follows GET POST JSON request RESTServlet RESTHandler JSON response wherein the REST URI space is of the format admin and wherein the action can be e.g. a login logout list configs get config prop or another action. In accordance with an embodiment a typical REST request response will then look similar to that shown below 

As further shown in an administration server includes an administration interface including one or more of an administration console GUI and or command line interface which allows an administrator to configure or manage the server environment.

In accordance with an embodiment the administration server includes a REST interface e.g. a Java web application or REST web service which provides a mapping between a REST URI space and respective mbean calls . When an administrator using the administration interface or another entity communicates a management request as a REST call to the REST interface the system maps that call to mbean calls for use in configuring or managing the server environment including e.g. the traffic director or instances therein.

In accordance with an embodiment the system can also support the use of customized HTTP headers to protect the REST web service API from potential Cross Site Request Forgery CSRF exploits. Through the use of customized HTTP headers conveying user specific tokens the administration server can assert the authenticity of clients invoking a management operation.

In accordance with an embodiment most of the REST APIs are protected and hence require authentication which can be provided through the use of a password based authentication. For example a REST API admin login can be provided to login using appropriate credentials e.g. a username and password or traffic director administration server credentials such as that shown below 

In accordance with an embodiment the response of the login action includes an X Auth Token which then must be passed with any subsequent requests. This allows the X Auth Token header to be used to prevent CSRF attacks 

In accordance with an embodiment the administration server includes a REST interface e.g. a Java web application or REST web service which provides a mapping between a REST URI space and respective mbean calls and also includes a security component .

When an administrator using the administration interface or another entity communicates a management request as a REST call to the REST interface they must first login or otherwise authenticate themselves with the security component. In response they receive a token which in accordance with an embodiment is an X Auth Token .

Thereafter with each management request REST call to the administrator server the token must be included as part of the request header . The security component can then verify the token prior to passing the management request as an mbean call to the traffic director environment.

At step a REST interface is provided e.g. as a web service which maps REST calls to mbean calls for use in configuring or managing the server environment.

At step depending on the particular embodiment the system can require that management requests received from clients include a customized header with one or more tokens as part of those management requests.

At step a security component can be provided at the REST interface to check for the presence of the token in the customized header and to verify the authenticity of the management request prior to allowing that request to be applied to the server environment or server instances therein.

The present invention may be conveniently implemented using one or more conventional general purpose or specialized digital computer computing device machine or microprocessor including one or more processors memory and or computer readable storage media programmed according to the teachings of the present disclosure. Appropriate software coding can readily be prepared by skilled programmers based on the teachings of the present disclosure as will be apparent to those skilled in the software art.

In some embodiments the present invention includes a computer program product which is a non transitory storage medium or computer readable medium media having instructions stored thereon in which can be used to program a computer to perform any of the processes of the present invention. The storage medium can include but is not limited to any type of disk including floppy disks optical discs DVD CD ROMs microdrive and magneto optical disks ROMs RAMs EPROMs EEPROMs DRAMs VRAMs flash memory devices magnetic or optical cards nanosystems including molecular memory ICs or any type of media or device suitable for storing instructions and or data.

The foregoing description of the present invention has been provided for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. Although some of the described embodiments describe features in the context of an Oracle Traffic Director environment the described features can also be used in the context of other computing environments. Many modifications and variations will be apparent to the practitioner skilled in the art. The embodiments were chosen and described in order to best explain the principles of the invention and its practical application thereby enabling others skilled in the art to understand the invention for various embodiments and with various modifications that are suited to the particular use contemplated. It is intended that the scope of the invention be defined by the following claims and their equivalence.

