---

title: Information processing system, control method for controlling the information processing system, and storage medium
abstract: A second information processing system to communicate with a first information processing system includes an acquisition unit, an acceptance unit, a confirmation unit, and a setting unit. The acquisition unit acquires authentication information from the first information processing system and from a memory of the second information processing system. The acceptance unit accepts correspondence information indicating correspondence between first authentication information and second authentication information. The confirmation unit confirms, as a condition, whether the acquired authentication information in the first information processing system is identical to the accepted first authentication information and confirms, as a condition, whether the acquired authentication information in the second information processing system is identical to the accepted second authentication information. The setting unit does not set the correspondence information as single sign-on setting information if a condition is not satisfied and sets the correspondence information as single sign-on setting information if both conditions are satisfied.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09077708&OS=09077708&RS=09077708
owner: Canon Kabushiki Kaisha
number: 09077708
owner_city: Tokyo
owner_country: JP
publication_date: 20120416
---
The present invention relates to an information processing system that supports single sign on a control method for controlling the information processing system and a storage medium.

Conventionally as a technology for authentication cooperation among a plurality of services there is a single sign on hereinafter referred to as SSO mechanism based on security assertion markup language hereinafter referred to as SAML .

In SAML based SSO the user has an ID both for the authentication service providing side identity provider hereinafter referred to as IdP and for the service providing side service provider hereinafter referred to as SP that provides services relying on the authentication result of the authentication service. For example when the user accesses the IdP first the user must be authenticated by the IdP. Therefore the user is authenticated by the IdP using the user s IdP ID and password.

The IdP can issue a SAML assertion to the authenticated user to prove that the user is authenticated. When the user uses this SAML assertion to access the SP the SP authenticates the access relying on the authentication result of the IdP. In this case once authenticated by the IdP the user who accesses the SP can be authenticated by the SP using the SAML assertion described above without using the user s SP ID and password.

SSO is implemented as described above. When accessing the SP via SSO the user does not pass the user s SP ID to the SP as described above. Therefore the correspondence relationship between an IdP ID authenticated by the IdP and an SP ID used for accessing the SP is to be solved.

In the description below the correspondence relationship between an IdP ID and an SP ID is called as single sign on mapping hereinafter referred to as SSO mapping . To implement SSO an appropriate SSO mapping must be set to solve the ID correspondence relationship.

Conventionally Japanese Patent Application Laid Open No. 2004 234329 discusses a system in which an SSO mapping server is used. This SSO mapping server creates an SP ID in advance and saves the created SP ID without assigning it to the user. When the user passes the ID and password to the IdP and the authentication is successful the SSO mapping server assigns the SP account newly to the user. This system implements SSO mapping when the IdP confirms user validity.

According to an aspect of the present invention a second information processing system capable of communicating with a first information processing system includes an acquisition unit configured to acquire authentication information in the first information processing system from the first information processing system and to acquire authentication information in the second information processing system from a memory of the second information processing system an acceptance unit configured to accept correspondence information indicating correspondence between first authentication information and second authentication information a confirmation unit configured to confirm as a first condition whether the acquired authentication information in the first information processing system is identical to the accepted first authentication information and to confirm as a second condition whether the acquired authentication information in the second information processing system is identical to the accepted second authentication information and a setting unit configured not to set the correspondence information as single sign on setting information in response to the confirmation unit confirming that at least any one of the conditions is not satisfied and to set the correspondence information as single sign on setting information in response to the confirmation unit confirming that both the first condition and the second condition are satisfied.

Further features and aspects of the present invention will become apparent from the following detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings.

The present invention is directed to the setting of SSO mapping between proper IDs among the services that support authentication cooperation.

The following describes exemplary embodiments with reference to the drawings. An authority transfer system in the present exemplary embodiment is implemented on a network with a configuration illustrated in .

In the embodiments the world wide web WWW system is used as a wide area network WAN . A local area network LAN connects various components to each other. The devices and systems can communicate with each other via the LAN.

The user operates a client personal computer PC . Service A and service B provide services after authenticating the user.

The client PC service A and service B are connected via the WAN network and the LAN . The client PC and the services may be configured on different LANs or on the same LAN. The client PC and the services may also be configured on the same PC.

The service A and service B are equivalent to a server A and a server B respectively. The service provided on each server is provided by a server computer described below. The provided service is for example a service for providing user information stored in a database and the print service.

The service A corresponds to a second information processing system and the service B corresponds to a first information processing system. Each of the service A and the service B may be a single server or a server group configured by a plurality of servers.

First the service A accepts a user login. Next when an SSO mapping setting request is accepted from the user the service A accesses the service B using service B authentication information included in the SSO mapping setting request. If the authentication information is valid the service B transfers a second ID list which can be acquired by the user authority identified by the authentication information to the service A .

In a first exemplary embodiment the user of a predetermined tenant who has administrator authority in the service A and service B accesses the service A to acquire the ID list from the service B . When acquiring the second ID list the service A uses the application programming interface API which is published by the service B to acquire a second ID list . Furthermore the service A acquires a first ID list that can be acquired with the authority of the login user.

The service A performs SSO mapping setting using the first ID list second ID list and SSO mapping setting information included in the SSO mapping setting request.

The authentication information received from the client includes at least the user ID. The service A acquires an ID list from other services based on this authentication information. Since the user ID is included also in the ID list the system is configured to acquire a plurality of pieces of authentication information from other services based on the authentication information received from the client.

The received authentication information according to the first exemplary embodiment includes the user ID and the password. The authentication information acquired from other services includes only the user ID. However there is no limit on the form of the received authentication information and acquired authentication information.

The hardware block diagram illustrated in corresponds to the hardware block diagram of a general information processing device. The client PC and the server computer in the present exemplary embodiment may have the hardware configuration of a general information processing device.

In a central processing unit CPU executes programs such as the operating system OS or applications stored in the program read only memory ROM of a ROM or loaded from a hard disk into a random access memory RAM .

The processing of each flowchart is implemented by executing these programs. The RAM functions as a main memory and a work area of the CPU . A keyboard controller KBC controls a key input from a keyboard KB or a pointing device not illustrated .

A cathode ray tube CRT controller controls the display of a CRT display . A disk controller DKC controls data access to the hard disk HD or a floppy registered trademark disk FD in which various types of data are stored. An NC connected to the network executes communication control processing with other devices connected to the network.

Unless otherwise stated the main component of the hardware for executing control is the CPU and the main component of the software is the application programs installed on the hard disk HD throughout the description below.

When the service B is an IdP the user once authenticated by the service B may access the service A without being authenticated by the service A . Therefore the user can receive the service without having to transmit the authentication information to the service A .

In the following example the flow will be described in which the user of client PC accesses the service B as a user access via a user access request and the service B user ID is first authenticated by the service B . After that the user receives the service of the service A via SSO. Another flow is also possible in which the user accesses the service A the user access is redirected to the service B and after receiving authentication by the service B the user receives the service of the service A .

In step S the service B checks whether the combination of the ID and the password of the service B accepted from the user in step S is valid. If the combination is valid YES in step S the processing proceeds to step S. If the combination is not valid NO in step S the service B ends the flow.

In step S the service B authenticates the user and redirects the user access to the service A . At that time the access information which has been passed at the redirect time includes the ID of the user the service B has authenticated. After the access is redirected by the service B the service B ends the flow. The access information corresponds to the authentication token.

In step S the service A accepts e.g. receives the user access redirected by the service B at step S. In step S the service A obtains from the access information received in step S the service B user ID of the user of client PC where the service B user ID has been authenticated by the service B .

In step S the service A performs SSO mapping service on the authenticated service B user ID obtained in step S to obtain an SSO mapping setting. The SSO mapping service is discussed in connection with B and C which are flowcharts illustrating the SSO mapping setting flow according to an exemplary embodiment. illustrates an SSO mapping setting between AX and BX and an SSO mapping setting between AX and BX. In step S of the service A determines whether the SSO mapping setting is obtained found in step S. If the SSO mapping setting is not found NO in step S the service A ends the flow. If the SSO mapping setting is found YES in step S the processing proceeds to step S. Here for example the SSO mapping setting between AX and BX of mapped the service B user ID of the user to the service A user ID of that same user such that the SSO mapping setting indicates the service A user ID of the service A .

In step S the service A authenticates the user of client PC using the service A user ID of the service A indicated by the SSO mapping setting found in step S. The service A then allows the user access request received in step S from the service B provides to the user of client PC the service requested by the user of client PC via the user access request received in step S from the service B and ends the FIG. A flow.

As described above when the user SSO mapping is set YES in step S the user of client PC can receive the service provided by the service A by first passing the service B user ID the service B user password of the service B and a request to use a service of the service A to the service B at step S.

The SSO mapping setting module compares the first authentication information included in the first ID list and the first authentication information included in the SSO mapping setting information and compares the second authentication information included in the second ID list and the second authentication information included in the SSO mapping setting information to perform SSO mapping setting. The details of the SSO mapping setting information will be described below. The SSO mapping setting information corresponds to the single sign on mapping table.

The second ID list generation module has the API that transfers the second ID list in response to an ID list generation request. When an ID list generation request is accepted from the SSO mapping service the second ID list generation module generates the second ID list as the list of IDs that can be acquired by the authority of the user authenticated by the second authentication module and transfers the generated second ID list .

The data example illustrates that the SSO mapping service for company A has two tenants i.e. TAX and TAY where company A group X users and e.g. AX AX and AX belong to the tenant T TAX and a company A group Y user e.g. AY belongs to the tenant TAY.

The data example illustrates that the SSO mapping object service has two tenants i.e. TBX and TBY where users BX BX and BX belong to the tenant TBX and a user BY belongs to the tenant TBY.

In a first exemplary embodiment it is assumed that the user of client PC is an administrator of a predetermined tenant and wants to perform single sign on setting collectively for the general users of the tenant e.g. for the general users of a group within a company to which the user of client PC belongs. In the first exemplary embodiment user BX is an administrator who has administrative authority to receive the service of the service A collectively on behalf of the general users BX BX and BX of group TBX to which administrator user BX belongs.

As described above specific information is related to each piece of authentication information i.e. a user ID that makes up authentication information e.g. an ID list. The specific information is tenant information. The user of client PC having administrator authority can acquire the user s own authentication information and other authentication information such as ID lists related to the same specific information as permitted by the authority.

The first ID list is a user ID list that the first ID list acquisition module of the service A has acquired from the service A by the authority of the user AX belonging to the tenant TAX. The second ID list is a user ID list that the second ID list acquisition module of the service A has acquired from the service B by the authority of the user BX belonging to the tenant TBX.

The SSO mapping setting information is SSO mapping setting information to perform a single sign on setting for AX and BX having administrator authority and for AX and BX a user in the same company and group as the user with the administrator authority.

In step S the first authentication module accepts the first ID and the first password which will be used for authentication by the SSO mapping service from the user who accesses the SSO mapping service .

In step S the first authentication module determines whether the combination of the first ID and the first password accepted in step S is valid. If the combination is valid YES in step S the processing proceeds to step S. If the combination is not valid NO in step S the first authentication module rejects the user access and ends the flow.

In step S the first authentication module allows login to the SSO mapping service as the first ID accepted from the user. In the description below it is assumed that the user ID is AX.

In step S the SSO setting information acceptance module accepts the second ID and the second password from the user. illustrates an example of the screen for the user to enter the second ID and the second password.

In step S the SSO setting information acceptance module accepts the SSO mapping setting information from the user. illustrates an example of the screen for the user to enter the SSO mapping setting information . In the description below it is assumed that as the SSO mapping setting information the SSO mapping setting information is described in each of the combination of AX and BX and the combination of AX and BX.

In step S the second ID list acquisition module uses the second ID and the second password accepted from the user in step S to request the second ID list generation API which is published by the SSO mapping object service to generate an ID list.

As the response the second ID list acquisition module receives the second ID list from the SSO mapping object service . The second ID list acquired in this step is an ID list in the range that can be acquired by the authority of the user indicated by the second ID. In the first exemplary embodiment it is assumed that this list is an ID list that can be acquired in the range of the administrator authority and that BX is used as the second ID to acquire the second ID list .

In step S the first ID list acquisition module acquires the first ID list . The first ID list acquired in this step is an ID list in the range that can be acquired by the authority of the first ID authenticated in step S. It is assumed that AX is used as the first ID to acquire the first ID list . In this case the list of IDs belonging to the tenant to which AX belongs is acquired. It is assumed that the acquired first ID list includes AX AX and AX.

In step S the SSO mapping setting module uses the first ID list second ID list and SSO mapping setting information to perform SSO mapping setting and then ends the SSO mapping setting flow.

In step S the SSO mapping setting module determines whether there is an unprocessed combination in the SSO mapping setting information acquired in step S. If there is no unprocessed combination NO in step S the SSO mapping setting module ends the detailed flow of SSO mapping setting. If there is an unprocessed combination YES in step S the processing proceeds to step S.

In step S the SSO mapping setting module obtains one combination of a first ID and a second ID which are related to each other from the SSO mapping setting information . In the description below it is assumed that the combination of AX and BX is obtained.

This combination corresponds to the correspondence information. The single sign on mapping table including a plurality of pieces of correspondence information is the SSO mapping setting information .

In step S the SSO mapping setting module determines whether the first ID which is included in the combination obtained in step S is included in the first ID list acquired in step S.

If it is determined that the first ID is included that is if it is determined that the same ID is included YES in step S the processing proceeds to step S. If it is determined that the first ID is not included that is if it is determined that the same ID is not included in the correspondence information NO in step S the SSO mapping setting module does not perform SSO mapping setting for the combination obtained in step S and the processing proceeds to step . In this example because AX included in the combination obtained in step S is included also in the first ID list the processing proceeds to step S.

In step S the SSO mapping setting module determines whether the second ID which is included in the combination obtained in step S is included in the second ID list acquired in step S.

If it is determined that the second ID is included YES in step S the processing proceeds to step S. If it is determined that the second ID is not included NO in step S the SSO mapping setting module does not perform SSO mapping setting for the combination obtained in step S and the processing proceeds to step S.

In this example because BX included in the combination obtained in step S is included also in the second ID list the processing proceeds to step S.

In step S the SSO mapping setting module sets SSO mapping for the combination of the first ID and the second ID obtained in step S. After that the processing proceeds to step S. In this example SSO mapping is set for the combination of AX and BX.

As described above the SSO mapping service checks whether the authentication information user ID acquired based on the authentication information received from a client matches one of authentication information described in the single sign on mapping table for each piece of the correspondence information.

Based on this confirmation the SSO mapping service determines whether the correspondence information in the single sign on mapping table is to be set as the single sign on setting information.

In step S the second authentication module of the SSO mapping object service accepts a second ID list generation request from the SSO mapping service .

In step S the second authentication module determines whether the combination of the second ID and the second password included in the second ID list generation request is valid. If it is determined that the combination is valid YES in step S the processing proceeds to step S. If it is determined that the combination is not valid NO in step S the SSO mapping object service does not transfer the second ID list to the SSO mapping service and ends the flow.

In step S the second ID list generation module generates the second ID list . The second ID list generated in this step is an ID list in the range that can be acquired by the authority of the second ID authenticated in step S. In the description below it is assumed that BX is used as the second ID to acquire the second ID list .

In this case the second ID list generation module acquires the list of IDs belonging to the tenant to which BX belongs and generates the second ID list that includes BX BX and BX. In step S the second ID list generation module returns the second ID list generated in step S to the SSO mapping service and ends the flow.

The tenant TAY includes user ID AY. The SSO mapping object service which is the SSO mapping object service includes a tenant TBX and a tenant TBY . The tenant TBX includes user IDs BX BX and BX.

The tenant TBY includes the user ID BY. A company X tenant group indicates the tenant group of company X in the service A and service B . A company Y tenant group indicates the tenant group of company Y in the service A and service B .

Executing the flows illustrated in B and C results in an SSO mapping setting between AX and BX and an SSO mapping setting between AX and BX. These SSO mapping settings are appropriate SSO mapping settings because these SSO mappings are those in the company X tenant group .

On the other hand an SSO mapping between the company X tenant group and the company Y tenant group such as AX and BY is an inappropriate SSO mapping setting. The flows illustrated in B and C prevent such an SSO mapping from being set.

Conventionally Japanese Patent Application Laid Open No. 2004 234329 discusses a system in which an SSO mapping server is used. This SSO mapping server creates an SP ID in advance and saves the created SP ID without assigning it to the user. When the user passes the ID and password to the IdP and the authentication is successful the SSO mapping server of JP 2004 234329 assigns the SP account newly to the user. In contrast the present exemplary embodiment allows an SSO mapping to be set for an SP ID that the user of client PC already has.

The present exemplary embodiment allows the administrator in the tenant of a company who sets an SSO mapping on behalf of the users to set an SSO mapping even if the administrator does not know the password of each user. In addition when setting an SSO mapping the present exemplary embodiment prevents an SSO mapping from being set mistakenly for IDs included in the tenants of different companies.

Next a second exemplary embodiment will be described with reference to the drawings. For the components identical to those in the first exemplary embodiment the descriptions are omitted. Only the different portions are described below.

If an SSO mapping setting for the same ID is already set when an SSO mapping is set the second SSO mapping setting module overwrites the old setting with a new SSO mapping setting to update the single sign on setting.

In step S the second SSO mapping setting module determines whether there is an unprocessed combination in the SSO mapping setting information acquired in step S. If there is no unprocessed combination NO in step S the second SSO mapping setting module ends the detailed flow of SSO mapping setting. If there is an unprocessed combination YES in step S the processing proceeds to step S.

In step S the second SSO mapping setting module obtains one combination of a first ID and a second ID which are related to each other from the SSO mapping setting information . In the description below it is assumed that the combination of AX and BX is obtained.

In step S the second SSO mapping setting module determines whether the first ID included in the combination obtained in step S is included in the first ID list acquired in step S.

If it is determined that the first ID is included YES in step S the processing proceeds to step S. If it is determined that the first ID is not included NO in step S the second SSO mapping setting module does not perform SSO mapping setting for the combination obtained in step S and the processing proceeds to step .

In this example because AX included in the combination obtained in step S is included also in the first ID list the processing proceeds to step S.

In step S the second SSO mapping setting module determines whether the second ID which is included in the combination obtained in step S is included in the second ID list acquired in step S.

If it is determined that the second ID is included YES in step S the processing proceeds to step S. If it is determined that the second ID is not included NO in step S the second SSO mapping setting module does not perform SSO mapping setting for the combination obtained in step S and the processing proceeds to step S. In this example because BX included in the combination obtained in step S is included also in the second ID list the processing proceeds to step S.

In step S the second SSO mapping setting module determines whether the SSO mapping for the combination of the first ID and the second ID which is obtained in step S is already set. In other words the second SSO mapping setting module checks whether the new correspondence information includes the authentication information already used for the single sign on setting information.

If it is determined as the result of the determination that SSO mapping is not set NO in step S the processing proceeds to step S. If the SSO mapping is set YES in step S the processing proceeds to step S.

In this example the second SSO mapping setting module checks whether the SSO mapping for the first ID is already set and overwrites the SSO mapping with a new setting. However the ID used for checking whether the SSO mapping is already set is not limited to the first ID. The second SSO mapping setting module may use the second ID or both the first ID and the second ID.

In step S the second SSO mapping setting module sets the new SSO mapping for the combination of the first ID and the second ID obtained in step S and the processing proceeds to step S. In this case the SSO mapping is set for the combination of AX and BX.

In step S the second SSO mapping setting module overwrites the SSO mapping setting which is determined in step S that it is already set with the combination of the first ID and the second ID obtained in step S. When the setting is finished the processing proceeds to step S.

In this example it is assumed that the SSO mapping is already set for AX and BX in step S. Because the SSO mapping setting information for the combination of the AX and BX is acquired in step S the second SSO mapping setting module releases the SSO mapping of AX and BX. Instead the second SSO mapping setting module sets the SSO mapping for the combination of AX and BX.

The present exemplary embodiment allows the user to overwrite an SSO mapping setting which is already set with a new SSO mapping setting. When setting SSO mappings collectively the administrator in the tenant of a company can set a new SSO mapping setting without worrying about an SSO mapping setting that is already set thereby increasing convenience. When overwriting SSO mappings collectively the user can easily overwrite the SSO mappings.

Next a third exemplary embodiment will be described with reference to the drawings. For the components identical to those in the first exemplary embodiment the descriptions are omitted. Only the different portions are described below.

If one of the first ID and the second ID of the combination thereof which are described in the SSO mapping setting information when performing SSO mapping setting is not described the third SSO mapping setting module releases the SSO mapping setting for the other.

In step S the third SSO mapping setting module determines whether there is an unprocessed combination in the SSO mapping setting information acquired in step S. If there is no unprocessed combination NO in step S the third SSO mapping setting module ends the detailed flow of SSO mapping setting. If there is an unprocessed combination YES in step S the processing proceeds to step S.

In step S the third SSO mapping setting module obtains one combination of a first ID and a second ID which are related to each other from the SSO mapping setting information . In the description below it is assumed that the combination of AX and BX is obtained.

In step S the third SSO mapping setting module determines whether both of the first ID and the second ID are included in the combination obtained in step S. If both are included YES in step S the processing proceeds to step S. If only one of them is included NO in step S the processing proceeds to step S.

A case in which only one of the first ID and the second ID is included means that information of one of the first authentication information and the second authentication information is left blank. Another case in which only one of the first ID and the second ID is included means that the second authentication information is not related to the first authentication information in the new correspondence information. Of course a case in which the first authentication information is not related to the second authentication information may be included in the above case.

In step S the third SSO mapping setting module determines whether the first ID which is included in the combination obtained in step S is included in the first ID list acquired in step S.

If it is determined that the first ID is included YES in step S the processing proceeds to step S. If it is determined that the first ID is not included NO in step S the third SSO mapping setting module does not perform SSO mapping setting for the combination obtained in step S and the processing proceeds to step . In this example because AX included in the combination obtained in step S is included also in the first ID list the processing proceeds to step S.

In step S the third SSO mapping setting module determines whether the second ID which is included in the combination obtained in step S is included in the second ID list acquired in step S.

If it is determined that the second ID is included YES in step S the processing proceeds to step S. If it is determined that the second ID is not included NO in step S the third SSO mapping setting module does not perform SSO mapping setting for the combination obtained in step S and the processing proceeds to step S. In this example because BX included in the combination obtained in step S is included also in the second ID list the processing proceeds to step S.

In step S the third SSO mapping setting module sets the SSO mapping for the combination of the first ID and the second ID obtained in step S and the processing proceeds to step S. In this case the SSO mapping is set for the combination of AX and BX.

In step S the third SSO mapping setting module determines whether the ID obtained in step S is included in the corresponding ID list that is one of the first ID list and the second ID list .

For example if the ID obtained in step S is the first ID the third SSO mapping setting module determines whether the ID is included in the first ID list .

On the other hand if the ID obtained in step S is the second ID the third SSO mapping setting module determines whether the ID is included in the second ID list . If it is determined that the ID is included YES in step the processing proceeds to step S. If it is determined that the ID is not included NO in step the processing proceeds to step S without performing any processing.

In step S the third SSO mapping setting module releases the SSO mapping setting that is set for the described ID either the first ID or the second ID of the combination obtained in step S. When the setting is released the processing proceeds to step S.

The release of a setting refers to the update so that the correspondence information which has been used for the single sign on setting information will no longer be used as the single sign on setting information.

When releasing an already set SSO mapping setting the present exemplary embodiment allows the user to release the setting if the user knows only one of the IDs of the SSO setting. Therefore even if the IDs used for the SSO mapping setting is already deleted and there is no way to know which ID was used the present exemplary embodiment allows the user to specify the other ID to release the SSO mapping thus increasing convenience.

Next a fourth exemplary embodiment will be described with reference to the drawings. For the components identical to those in the first exemplary embodiment the descriptions are omitted. Only the different portions are described.

The second SSO setting information acceptance module receives the authentication information on the SSO mapping object service from the user who is trying to log in and makes an authentication request to the SSO mapping object service for authentication.

After the authentication the fourth SSO mapping setting module sets an SSO mapping between the ID of the user who is trying to log in to the SSO mapping service and the ID of the SSO mapping object service received by the second SSO setting information acceptance module .

In step S the second SSO setting information acceptance module accepts the second ID and the second password from the user. illustrates an example of the screen for the user to enter the second ID and the second password.

In step S the fourth SSO mapping setting module uses the second ID and the second password which are accepted in step S to make an authentication request to the SSO mapping object service .

In step S the fourth SSO mapping setting module determines whether the authentication by the SSO mapping object service is successful in step S. If the authentication is successful YES in step S the processing proceeds to step S. If the authentication is not successful NO in step S the fourth SSO mapping setting module does not perform SSO mapping setting and ends the flow.

In step S the fourth SSO mapping setting module sets an SSO mapping between the first ID accepted in step S and the second ID accepted in step S. When the setting is completed the fourth SSO mapping setting module ends the flow.

In step S the second authentication module performs authentication using the combination of the second ID and the second password included in the authentication request. In step S the second authentication module transfers the authentication result of step S to the SSO mapping service and ends the flow.

The present exemplary embodiment allows a user who has not the administrator authority to set an SSO mapping for the user s own existing account thus reducing the load of the administrator.

Although IdP is included in the screen example because the SSO mapping object service is an IdP in this example the SSO mapping object service is not limited thereto. In addition the SSO mapping setting information may also be specified in a form other than a file. is a diagram illustrating an example of the screen in which the controls for receiving the second ID and the second passwords are included.

Although the exemplary embodiments have been described individually one system may execute the processing of the exemplary embodiments. For example one system may execute all exemplary embodiments from the first to the fourth or some of the exemplary embodiments from the first to the third. In such a case there is no problem because conflict among the processing is least likely to occur.

Aspects of the present invention can also be realized by a computer of a system or apparatus or devices such as a CPU or MPU that reads out and executes a program recorded on a memory device to perform the functions of the above described embodiments and by a method the steps of which are performed by a computer of a system or apparatus by for example reading out and executing a program recorded on a memory device to perform the functions of the above described embodiments. For this purpose the program is provided to the computer for example via a network or from a recording medium of various types serving as the memory device e.g. computer readable medium . In such a case the system or apparatus and the recording medium where the program is stored are included as being within the scope of the present invention. In an example a computer readable storage medium may store a program that causes a second information processing system to perform a method described herein. In another example a central processing unit CPU may be configured to control at least one unit utilized in a method or apparatus described herein.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

This application claims priority from Japanese Patent Application No. 2011 111586 filed May 18 2011 which is hereby incorporated by reference herein in its entirety.

