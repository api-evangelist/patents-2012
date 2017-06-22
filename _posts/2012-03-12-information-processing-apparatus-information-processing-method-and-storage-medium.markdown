---

title: Information processing apparatus, information processing method, and storage medium
abstract: When receiving an access request to a resource of a first application from a second application, a resource management unit transfers an authentication result for the first application included in the access request to the first application, and when receiving a determination result on whether access of the second application to the resource is permitted from the first application, the resource management unit returns the determination result to the second application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08613076&OS=08613076&RS=08613076
owner: Canon Kabushiki Kaisha
number: 08613076
owner_city: Tokyo
owner_country: JP
publication_date: 20120312
---
The present invention relates to an information processing apparatus an information processing method and a storage medium.

Conventionally each application manages a resource of the application. For example a first application can receive an access request to a resource managed by the first application from a second application. In such a case conventionally the first application itself determines whether the second application is an application which is permitted to access the resource.

A service A intends to control access to a resource possessed by a service B in a security domain X in Japanese Patent Application Laid Open No. 2000 148469. In a technique discussed in Japanese Patent Application Laid Open No. 2000 148469 the service B itself which is a management source of the resource determines availability from the service A .

According to an aspect of the present invention an information processing apparatus including an application execution environment in which a first application belongs to a first security domain and a second application belongs to the first security domain and a second security domain includes a resource management unit that does not belong to either the first security domain or the second security domain and is configured to manage resources of a plurality of applications including the first application wherein if the resource management unit receives an access request to a resource of the first application from the second application the resource management unit transfers an authentication result for the first application included in the access request to the first application and if the resource management unit receives a determination result on whether access of the second application to the resource is permitted from the first application the resource management unit returns the determination result to the second application.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings .

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings.

A program is stored in the HDD . The CPU reads and executes the program from the HDD . The CPU executes the program and thereby processing of a software module and a flow chart is realized which will be described below. The software module can receive a user s operation input from the operation unit and can utilize and control the printer unit the RAM the network interface and the HDD .

All the software modules described below utilize and control a hardware module illustrated in via an application programming interface API provided by the OS directly or indirectly via a Java execution environment . Because a substance of the API is provided with the substance included in the OS the API is not particularly illustrated in .

The Java execution environment provides the API equalized by software operated on the OS without depending on the OS and a type or hardware configuration of the API provided by the OS . Accordingly a virtual execution environment virtual machine is provided which can enhance the development efficiency and reutilization possibility of the software module.

An application execution framework provides a structure which integrally controls the entire software execution environment such as management of installation and uninstallation of an application control of an execution sequence of the application and a communication function via the API between the applications and the software modules on the framework. The application execution framework is a collective term of a software module group which provides the above described function.

The Java execution environment and or the application execution framework are an example of an application execution environment.

A log service is a software module existing in the software execution environment . The log service provides a function of recording and managing a log of an application as described below with respect to . The log is a collective term of various behaviors of the application and histories of processing recorded as a file on a recording medium such as a hard disk or a flash memory. In the present exemplary embodiment the log is recorded as a file on the HDD . The log service is an example of a resource management unit.

When an application accesses the application log the application needs to acquire in advance a permission for the application to access and user authority for reading out the log of the application . More specifically the application uses the API provided by the application to acquire permission for acquiring a log from the application and user authority that is under the control of the application . After the application acquires the permission and the user authority the application can acquire the application log .

The application not only includes an authentication function for the application and an access control function of the application log but also possesses the application log that can be accessed from other applications. In other words the application log is located in an area managed by the application itself.

On the other hand in an arbitrary application can utilize a function of the log service via the API registered to the application execution framework by the log service . In the example in the application includes the application log . However in the example in as illustrated in the log service includes a plurality of application logs. In other words the log service can provide a log area to a plurality of applications such as an application .

The configurations as illustrated in provide for consolidation of the log areas i.e. the log service . By consolidating the log areas a form of the log an acquisition method of the log and the API recording and acquiring the log and the acquisition method are unified for each application. Therefore each application can also follow the unified log form as the entire system. If the log of the log area consolidated from only the log service can be extracted the logs of all the applications existing in the system can be extracted at once in a unified manner. As a result this causes the processing load for performing a user s log extraction and production of an application writer s log record and acquisition can be reduced.

In the log service provides the following functions to an arbitrary application via the API. A first function produces and secures a dedicated log area on which only the application records as a file log file on the HDD to which only the log service can directly access. A second function records the log via the API to the application. A third function reads the log via the API to the application. The details of each of these functions are described in more detail below with respect to .

The log service can produce a plurality of log areas. However for description purposes the entire log area managed by the log service is illustrated in . In the entire log area the application produces and secures a log area . A log area of the other application is expressed as a log area of the other application.

The executed application requests the log service to secure the log area dedicated for the application via the above described API. In step S the application registers API for confirming user authority and an application permission defined as an application permission A in the log area .

The application permission is a security mechanism of a code level applied to an execution body of the application introduced in Java . The definition and behavior of the application permission are prescribed by internal processing of the API. On the other hand whether the permission is included or not is mounted in a form where certain definition is declared on a file in the execution body for each application.

When a function or processing is required to be executed via a certain API the application calling up the API should include the permission. A different permission according to the function and processing of the API can be generally defined. If the application tries to utilize the API without having the permission required for utilization thereof the permission is considered to be insufficient. The utilization of the API is thus interrupted and fails.

If the application includes the application permission A as described below the application permission A is considered to have a process prescribed by the application permission A that is authority to access to the log area via the API.

The API for confirming user authority is utilized in order that the log service confirms the user authority of the application in the following description. The detail thereof is described below. The API for confirming user authority is not indispensably registered.

The registration of the application permission A means that an arbitrary application accessing to the log area secured in step S is included among the permissions that the application can include. In other words only the application including the application permission A among the arbitrary applications has authority to access to the log area secured in step S.

The registration of the application permission is determined by the provision of the application serving as a holder of the log area . The registration must be not necessarily set. it is not clear whether the registration must be set or does not need to be set The user authority and the application permission are independently defined by the provision of the application and are independently controlled by the log service . The details thereof are described below.

The application permission is described in a substance installation package of the arbitrary application when the application is installed. The application permission is interpreted by the application execution framework during installing. While the application is executed the Java execution environment verifies whether the permission is included.

According to the present exemplary embodiment when the arbitrary application utilizes the log service via the API the log service can verify whether the application permission A is included via a permission check mechanism of the Java execution environment .

Next in step S the log service records the application permission A and the API for confirming user authority with the log area as a file on the HDD .

Next processing when an application which is different from the application as the holder of the log area accesses to the log area after step S is described. In step S the application requests the log service via the API to read the log recorded on the log area . The substance of this API is different from that of the above described API. However the API is provided to the application to access the log area by the log service via the same mechanism.

In response to the request in step S the log service verifies whether the application permission is set to the log area . The log service can perform the verification based on information stored in the file with the log area as described above.

If the log service can verify that the log area stores the application permission A permission is set in step S then in step S the log service verifies whether the application includes the application permission A based on the information. In step S if the application permission is not set to the log area the processing proceeds to step S without performing the verification in step S. Also if the application permission A is set to the log area and the application includes the application permission A the processing proceeds to step S.

If the application does not include the application permission A then in step S the log service does not respond to the read request of the application and returns the result to the application .

In step S the log service confirms whether the API for confirming user authority is registered from the application to the log area . If the API for confirming user authority is not registered in the log area then in step S the log service permits access to the log area of the application and returns the result to the application .

On the other hand in step S if the API for confirming user authority is registered the log service inquires the application whether the user authority for the log area is appropriate with use of the API. It is assumed that the application preliminarily completes user authentication to the application without the log service .

The user authentication is authentication in which a user who operates for example the application to access the log area of the application via the application performs via the predetermined API to the application .

In other words the application is provided with an API uniquely performing user authentication to another application. The application can perform the user authentication under the control of the application according to the API and can further obtain the authentication result from the application . In other words the application does not need to request the log service to perform the user authentication.

The user authentication may be executed by a user name including a domain name to which the application belongs or a combination of a user name excluding the domain name and a password. The user authentication may be performed by authentication according to an integrated circuit IC card via an external authentication device installed to the apparatus and biometrics such as a fingerprint and iris authentication.

The authentication result may be transferred to the API via which the application requests the access from the log service . The authentication result may be transferred via another API. In any case in step S the log service transfers the authentication result to the application via the API for confirming user authority. In step S the application determines whether the access authority to the log area exists in the user indicated in the authentication result and returns the determination result to the log service .

In step S the log service determines whether the authentication result of the user operating the application includes authority to access to the log area according to the determination result.

If the access to the log area is not permitted then in step S the log service returns the result refusing the access to the application . If the access to the log area is permitted then in step S the log service returns the result of the access permission to the application .

The result shown herein determines whether the access to the log area is permitted by the authenticated user via the application and results in the following process. More specifically if the user authenticated to the application is determined to be an administrator in the application the user is considered to have administrator authority. For the user considered to be the administrator by the application the access to the log area stored by the application is accepted. However if the authenticated user is a general user for the application the access is not accepted. The result thus returned is succeedingly required to be specified as a parameter via the log area to the log service via the API. In other words only when an argument of the API includes authentication result information the API permits the access to the log area and performs processing.

As described above the log service can perform the following access control according to processing from step S to step S. More specifically the log service can cause the application to perform access control according to the permission of the application previously set to the log area for the access request from the application to the log area stored under the control of the log service .

That is the log service can completely entrust the application with determination of access to the log area based on the user authority managed by the application . In other words although the log service manages the log area of the application the access control to the log area can follow the access control method set by the application .

In event SQ the log service receives a securement request of the log area via the API from the application belonging to a security domain A for example. The log service also receives a registration request including the API for confirming the user authority of the log area and the application permission A from the application belonging to the security domain A. The security domain A is an example of a first security domain. A security domain B is an example of a second security domain.

Then in event SQ the log service secures the log area in the entire managed log area and records the application permission A and the API for confirming user authority as the file on the HDD in association with the log area .

In event SQ the log service receives an access request to the log or log area recorded on the log area from the application belonging to the security domain A and the security domain B for example.

In event SQ the log service verifies whether the application permission is set to the log area based on the information recorded on the file.

When the application permission is set in event SQ the log service verifies whether the application transmitting the access request includes the application permission A set to the log area . The log service performs the verification via the permission check mechanism of the Java execution environment as described above.

When the application includes the application permission A in event SQ the log service confirms whether the API for confirming user authority is registered in the file in association with the log area .

When the API for confirming user authority is registered in the file in association with the log area in event SQ the log service transfers the above described authentication result to the application via the API for confirming user authority.

In event SQ the log service receives the determination result on whether the access authority to the log area exists in the user indicated in the authentication result from the application .

In event SQ the log service verifies the determination result received from the application and confirms whether the access to the log area is permitted. For example when the determination result received from the application indicates the existence of the access authority to the log area in the user indicated in the authentication result the log service permits the access to the log area . On the other hand when the determination result received from the application indicates the nonexistence of the access authority to the log area in the user indicated in the authentication result the log service does not accept the access to the log area .

In event SQ the log service returns the result indicating whether the access to the log area is permitted to the application . Although the log service returns the result indicating whether the access is permitted in the present exemplary embodiment the log service may transmit the log of the log area to the application at the timing of the response in event SQ according to the confirmation of the acceptance of the access.

As described above because the log service does not belong to the security domain to which the application and the application belong the log service cannot determine whether to permit the application to access the log area of the application . However processing illustrated in enables the log service to control the access to the log area of the application from the application .

The above described exemplary embodiments enable the access control from the second application to the resource of the first application by the service which manages the resources of the plurality of applications in an integrated fashion. In the above described exemplary embodiments the log or the log area is described as an example of the resource. However the description does not limit the exemplary embodiment.

Aspects of the present invention can also be realized by a computer of a system or apparatus or devices such as a CPU or an MPU that reads out and executes a program recorded on a memory device to perform the functions of the above described embodiments and by a method the steps of which are performed by a computer of a system or apparatus by for example reading out and executing a program recorded on a memory device to perform the functions of the above described embodiments. For this purpose the program is provided to the computer for example via a network or from a recording medium of various types serving as the memory device e.g. computer readable medium .

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

This application claims priority from Japanese Patent Application No. 2011 055299 filed Mar. 14 2011 which is hereby incorporated by reference herein in its entirety.

