---

title: Method and apparatus for providing internet service carrying out fee payment in wireless communication network
abstract: The present disclosure relates to a method and an apparatus for an Internet service provider server providing a sponsored service, in which a service provider server pays a mobile communication usage fee in place of a user equipment, and the method for providing the sponsored service comprises: a connection step of selecting predetermined sponsored content so as to provide the sponsored service by means of the user equipment accessing the Internet service provider server; an authentication step of authenticating to the user equipment that the sponsor service is valid by a sponsorship manager, which is a device for managing the sponsor service, connecting with the user equipment on the mobile communication network; a step for the Internet transmitting to the user equipment the sponsored content that comprises in an IP packet either an IspCode, which is pre-allocated by the sponsorship manager for identifying the Internet provider server, or an IspTrfCode, which is pre-allocated by the sponsorship manager for identifying the sponsored service; and a ending step of ending the connection between the user equipment and the sponsorship manager, and the user equipment and the sponsorship manager collecting traffic information with regard to the sponsored service.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09350877&OS=09350877&RS=09350877
owner: Kyung Hee University Industry Academic
number: 09350877
owner_city: Yongin-si
owner_country: KR
publication_date: 20121206
---
The present application claims priority under 35 U.S.C. 365 to International Patent Application No. PCT KR2012 010564 filed Dec. 6 2012 entitled METHOD AND APPARATUS FOR PROVIDING INTERNET SERVICE CARRYING OUT FEE PAYMENT IN WIRELESS COMMUNICATION NETWORK . International Patent Application No. PCT KR2012 010564 claims priority under 35 U.S.C. 365 and or 35 U.S.C. 119 a to Korean Patent Application No. 10 2011 01299146 filed Dec. 6 2011 and which are incorporated herein by reference into the present disclosure as if fully set forth herein.

The present disclosure relates to a method and apparatus for an Internet service provider to pay the mobile communication network usage bill in the user s stead.

In more particular the present disclosure relates to a method and apparatus for the Internet service provider which provides a mobile subscriber with Internet service using the mobile communication network to pay the cellular network usage bill issued for the corresponding service in the mobile subscriber s instead.

As shown in when there is a plurality of mobile communication networks available for the User Equipment the User Equipment selects a certain mobile communication network to connect to the ISP server .

After completing the use of the Internet service provided by the ISP server the fee of using the mobile communication network for the corresponding service is charged to the owner of the User Equipment and in most cases the owner is an individual. In the case that the owner is an organization such as company the usage fee is charged to the organization.

In this case the mobile communication network usage fee is calculated based on the traffic amount flown exchanged through the mobile communication network in most but sometimes based on the mobile communication network usage time service type e.g. real time service such as voice and video .

In order to support Internet service the metering of the traffic amount and time and checking the service type is performed by the mobile communication network termination devices such as gateways.

As shown in the mobile communication networks have respective gateways and at their boundaries in view of the mobile communication network. For example Long Term Evolution LTE as the fourth generation mobile communication standard of the 3Generation Partnership Project 3GPP is provided with a PDN Gateway PGW .

The billing information collected by the gateway devices such as PGW is transferred to a billing server such as Authentication Authorization Account server AAA which calculates the fee to be charged and charges the finally determined to the owner of the User Equipment.

The conventional technology has a problem in that it is impossible for the ISP to pay the mobile communication network usage fee in the mobile subscriber s instead. For example the ISP may provide the mobile subscriber with the Internet service in exchange for viewing advertisement and want to pay the mobile communication network usage fee with the benefit from the advertisement but it is impossible.

The present disclosure aims to solve the above problem. In particular the present disclosure aims to provide a method and apparatus that is capable of allowing the ISP providing Internet service through the mobile communication network to pay the mobile communication network usage fees on behalf of the mobile subscribers who use its Internet service in a way of paying for viewing advertisements. Also the present disclosure aims to provide a method and apparatus of paying for mobile subscribers in association of various options such as usage time consumed traffic amount and individual files.

Furthermore the present disclosure aims to provide a method and apparatus of paying the mobile communication fee charged for use of the services of third party organizations such as enterprise university and public institution as well as the ISP in the mobile subscriber s instead.

In order to solve the above problem the payment method of the present disclosure includes selecting at the terminal a predetermined sponsored content for the sponsored service authenticating at a sponsorship manager as a device for managing the sponsored service on the mobile communication network validity of the sponsored service to the terminal transmitting the sponsored content including at least one of IspCode for identifying the internet service provider server and a IspTrfCode for identifying the sponsored service from the Internet service provider server to the terminal and releasing connection between the terminal and the sponsorship manager and collecting traffic information on the sponsored service.

The payment apparatus of the present disclosure includes a terminal which selects a predetermined sponsored content for the sponsored service a sponsorship manager which authenticates validity of the sponsored service to the terminal allocates IspCode for identifying an Internet service provider server or IspTrfCode for identifying the sponsored service and collects traffic information on the sponsored service when the connection with the terminal is released and an Internet service provider server which transmits the sponsored content with IP packets including the IspCode or IspTrfCode to the terminal.

According to the present disclosure when an ISP provides User Equipment UE with Internet service using a mobile communication network it is possible for the ISP to pay the mobile communication network usage fee on behalf of the mobile subscriber in exchange for viewing advertisements.

The first is the technique of managing mobile subscribers interested in use of sponsored services by means of a sponsorship manager as a novel device.

The second is the technique of managing the ISPs interested in providing sponsored services by means of the sponsorship manager as a novel device.

The third is the technique of managing mapping information between the mobile subscribers interested in use of sponsored services and the ISPs providing the sponsored services and executing verification and authentication on legality at the outset of the corresponding service by means of the sponsorship manager as a novel device.

The fourth is the technique of adding a sponsorship filter as a novel function to the legacy UE and PGS to detect illegal sponsored services and collecting statistical information for billing for the lawful services. Particularly the technique of fabricating filters of various combinations from simple to complex forms using IspTrfCode that are relatively simple in complexity as compared to legacy gateways low in flexibility of diverse combination and high in complexity with the use of combinations of IP addresses and layer ports informations of the transmission and reception terminals based on 5 tuple concept.

The fifth is the technique of allowing the terminal to participate in generating CDR along with PGW to make the billing policy diverse with flexibility.

The sixth is the technique notifying of the start and end of the sponsored service on the security guaranteed layers such as OS and device driver independently of the sponsored application to guarantee the secure use of the sponsored service with the UE.

According to an embodiment of the present disclosure it is possible to launch a new business model in which the mobile communication network operator charges the mobile communication network usage fee to the ISP in the mobile subscriber s stead. It is also possible for the ISP to make new benefit using mobile communication and create various types of sponsored service models using the various types of sponsorship filter policies. It is also possible to check the sponsored service related statistical information on the terminal using the sponsored application developed and distributed by the ISP so as to improve clarity of the billing information of the mobile communication network operator.

The present disclosure is not limited to the embodiments described below but may include various modifications without departing from the scope of the present disclosure. Detailed description of well known functions and structures incorporated herein may be omitted to avoid obscuring the subject matter of the present disclosure.

The same reference numbers are used throughout the drawings to refer to the same or like parts. Some of elements are exaggerated omitted or simplified in the drawings. This aims to omit unnecessary description so as to make the subject matter of the present disclosure clear. Exemplary embodiments of the present disclosure are described with reference to the accompanying drawings in detail.

Second new technologies called sponsorship Application Programming Interface API and sponsorship filter are defined in the UE.

Third the technology of sponsorship filter is defined in the mobile communication network gateway e.g. device in as a legacy device as in the UE.

Fourth a new interface for exchanging control information among the ISP server gateway billing server e.g. AAA server UE and sponsorship manager is defined.

The sponsorship manager as the first newly introduce mobile communication network device is the premises of the mobile communication network operator and responsible for managing the sponsored services in which the ISP pays for the use of the mobile communication network on behalf of the mobile subscriber e.g. payment based on time and or traffic amount .

Here the management means that the mobile communication network operator is capable of managing the mobile subscribers interested in the sponsored service by allocating logical IDs and passwords to the mobile subscribers. In an alternative view the mobile communication network operator is capable of managing the information on the ISPs interested in providing the mobile subscribers with the sponsored services for identifying the ISPs and charging the mobile communication network usage fee of the mobile subscribers.

In order to accomplish this the corresponding ISP like the UE has to register the unique ISP identifier and password with the sponsorship manager such that the sponsorship manager manages the identifier and password. The mobile subscriber and ISP interested in use of the sponsored service registered as above have to perform a service subscription authorization mutually through the service subscription procedure independently of the procedure of the present disclosure.

Afterward the sponsorship manager receives the information on the agreement for the service between the mobile subscriber and the ISP from the mobile subscriber or the ISP and performs the operations of 1 verifying the legality of the agreement between the mobile subscriber and the ISP and 2 determining the fee to be charged to the lawful sponsored service with the PGW based on the information.

That is if the sponsored service starts the mobile communication network operator does not accommodate the corresponding service immediately but determines whether the sponsored service has been agreed between the mobile subscriber and the ISP and if so checks the communication time or traffic amount of the agreed service through PGW.

Finally the mobile communication network operator generates the billing basis information based on the file check of the usage time or traffic amount with the assistant of the devices such as terminal and sends the billing basis information to the billing server.

Second a new function of calling the sponsored service to be provided by the ISP has to be added newly to the terminal this function being executed by calling a command called sponsorship API.

The corresponding function includes 1 an initial registration function of generating dedicated ID and password to the sponsorship manager in order for the mobile subscriber to use the sponsored service afterward 

2 a function in which the mobile subscriber completed initial registration with the sponsorship manager is aware of the ISP providing a specific service as the sponsored service connects to the ISP through the Internet and registers the corresponding ISP or specific service of the ISP with the sponsorship manager with the notification of being ready to receive the sponsored service 

3 a function in which the mobile subscriber notifies the sponsorship manager of the start of the service at the operation start time point of one of the subscribed sponsored services and authenticating the lawful access and validity of the sponsored service by taking notice of the property of the sponsored service of which support is restricted under the conditions of specific time specific duration and specific place 

4 a function of acquiring information on the traffic of the sponsored service or detecting the illegal sponsored service by executing the sponsorship filter additionally in the UE 

5 a function of reporting the information on the transmitted received traffic of the lawful sponsored service and the illegal sponsored service usage detection information to the sponsorship manager as auxiliary function 

6 a function in which the sponsorship filter monitors transmission reception traffic to detect the end of the sponsored service and if no traffic is detected for a predetermined duration ends the corresponding sponsored service and

finally 7 a function in which the UE notifies of the start and end of the sponsored service clearly with screen or audio reaction to resolve the anxiety about whether the ISP pays for the fee and how much the interknit service provider pay in the mobile subscriber s stead .

Fourth the legacy mobile communication network gateway such as PGW is provided with the sponsorship filter as in the UE. The sponsorship filter reads the IspTrfCode of the traffic transmitted received through the mobile communication network. This code is issued to the sponsorship manager when the ISP designates a specific service as the sponsored service and registering the sponsored service with the sponsorship manager.

The application service of the UE using the corresponding sponsored service and the server of the ISP insert the corresponding code into the Internet packets carrying the traffic. It may be considered to use a field of the IP packet for containing the code and description thereon is made later with reference to accompanying drawings.

If an IspTrfCode registered lawfully is detected in the packets transmitted received through the mobile communication network the gateway extracts the information on the number of packets transmitted received or time for use in generating the billing information afterward. If an illegal sponsored service is detected the gateway blocks the corresponding service and makes a contact to the ISP registered using the corresponding code to prepare for a situation such as illegal attack.

The reason for use of the IspTrfCode is because the code makes it possible to identify the sponsored service without checking the source and destination addresses and port number of protocol such as TCP UDP. Without this code it is necessary to transmit the preregistered ISP server IP address or use 5 tuples including all the informations of the ISP and UE which increases the size of the 5 tuple address list managed for the sponsored services in the PGW and processing complexity.

It is not prefer to use the IP address of the ISP since the physical information such as IP address is exposed to the mobile communication network operator irrationally and it is difficult to take an appropriate action such as increase of the number of dynamically in correspondence to the abrupt increase of the usage amount of the corresponding service. Recently in the case of using a plurality of TCP UDP or operator s own service ports dynamically in one service it is impossible to correspond those informations to 5 tuple format dynamically.

In the case of using IspTrfCode it is possible to operate the policy flexibly. That is it is possible of supporting all the cases of checking only IspTrfCode checking IspTrfCode and source or destination IP address checking source and destination IP addresses as if using 5 tuples checking UDP TCP port numbers in addition to the IP addresses. From the viewpoint of the mobile communication network operator this is advantageous in terms of minimizing the load of the mobile communication network and making new benefit.

The sponsorship filter embodied in the PGW may be removed from the PGW so as to be implemented as a separate device. That is the sponsorship filter may be removed from the PGW and then implemented as a new device arranged between the PGW and the ISP server to accomplish the same effect.

Fourth the sponsorship manager is provided with a control interface for communication with the UE the PGW and the ISP or ISP server to support above described functions.

In addition the sponsorship manager is also responsible for the function of transferring when a specific sponsorship service is required to guarantee a specific type of Quality of Service QoS the corresponding information to the PGW. In the case of complying with the 3GPP LTE standard the corresponding information is transferred to the PGW via a Policy and Charging Rules Function PCRF . Finally when the sponsored service ends the sponsorship manager collects billing information in conjunction with the UE PGW.

A description is made of the operation for supporting the sponsored service according to the present disclosure in detail with reference to an exemplary scenario.

In detail this procedure is performed independently of the service of a specific ISP in such a way that the mobile communication network operator checks whether there is any request for the sponsored service from a certain mobile subscriber and if so assigns a sponsorship ID such that the mobile subscriber registers the UE with the ISP using the sponsorship ID.

Using such an extra sponsorship ID it is possible for the mobile subscriber receive the free service without exposure of private information such as identity number of phone number. The sponsorship ID is a logical identifier that may have no time limit or updated on demand by the mobile subscriber.

As shown in the UE performs secure connection setup with the sponsorship manager for use of the sponsored service at operation . This procedure may be performed using the legacy protocol such as IPsec.

Afterward the UE is allocated a sponsorship ID for use of the sponsored service from the sponsorship manager and registers a password with the sponsorship manager . If it fails passing the authentication procedure between the UE and the ISP with the sponsorship ID and password the sponsorship manager reissues the sponsorship ID and otherwise notifies the mobile subscriber of the authentication completion at operation .

If there is no problem the sponsorship manager manages the sponsorship ID and password of the mobile subscriber in a database as shown in .

As shown in the UE subscribed to the sponsored service is managed with the sponsorship ID and password issued along with the information on the UE and mobile subscriber.

As shown in if it wants to provider a sponsored service the ISP or ISP server establishes a secure connection with the sponsorship manager at operation and sends the sponsorship manager sends the sponsorship manager the detailed information on the sponsored service at operation .

In this case the ISP generates an ISP registration ID identifier for management usage at operation and password password for management usage at operation to the sponsorship manager and for use in sponsorship service subscription and update afterward.

In the procedure of configuring the ISP ID and password the ISP notifies of the information on the account for the mobile communication network operator to charge the payment for the sponsored service serviced by the ISP billing account information at operation .

As shown in the detailed supplementary information managed by the sponsorship manager in association with the sponsorship service provided by the ISP may include IP information of the ISP providing the sponsored service IP address information of the UE receiving the sponsored service date and time available for the sponsored service physical location of the UE for receiving the sponsored service information on the coupon available for consuming the sponsored service and a ID list for designating UE having specific sponsorship ID.

Further supplementary informations may be singled out and applied. If an ISP is capable of providing sponsored services and if the requested sponsored service is valid. The sponsorship manager allocates an IspCode to the ISP in order for the UEs subscribed to the sponsored service to identify the ISP.

This is the code allocated at the level of ISP such as google and yahoo. The providers may allocate logical addresses for identification of the framework supporting the sponsored service. In addition the IspTrfCode as a separate code for identification of the sponsored service requested by the IPS.

As shown in the sponsorship manager stores and manages the aforementioned informations in a database as ISP sponsor record. The sponsorship manager sends the PGW PCRF the information indicating that the sponsorship service is provided through the PGW using IspTrfCode and specific IP domain at operation .

Particularly if the ISP transmits QoS information this information is also stored managed in the ISP sponsor record and transferred to the PGW PCRF . The PGW determines whether the lawful sponsored service is being provided inspect for illegal sponsored service and collect billing basis information such as traffic time of the consumed lawful sponsored service.

The mobile subscriber registers the sponsored service with the sponsorship manager of the mobile communication network operator as shown in while the ISP intending to provide the sponsored service registers the corresponding sponsored service with the sponsorship manager of the mobile communication network operator as shown in . A description is made of the procedure for the mobile subscriber to search the Internet for a target sponsored service and subscribe to the corresponding sponsored service.

The mobile subscriber connects to the ISP server to register a sponsored service. This procedure is identical with the registration procedure of a subscriber for current network service at operation .

If the corresponding procedure has completed the ISP providing the sponsored service sends the UE its IspCode and the IspTrfCode for the sponsored Service at operation .

The corresponding information is processed below the sponsorship API transparently of the applications. This means that the information is processed in a secure area such as inside of the operating system and device drive protected against the application programs. The UE stores the received IspCode and IspTrfCode in a database. That is the UE manages the IspCode and IspTrfCode associated with the subscribed sponsored service in the form of a database.

Afterward the UE registers the sponsored service information with the sponsorship manager through operations to .

The sponsorship manager manages the sponsored service to which the mobile subscriber identified with a specific sponsorship ID subscribes additionally with the newly added IspCode and IspTrfCode. is a diagram illustrating a structure of the database of the UE for use in managing a plurality of sponsored service.

Although not depicted in the drawing the mobile subscriber may connect to the sponsorship manager to delete any preregistered sponsored service at any time. The mobile subscriber may is prepared for use of the sponsored service of a specific ISP through the above procedure.

In the case that the mobile communication network operator intends to add the information on the individual users in addition to IspTrfCode in monitoring the sponsored service at PGW the sponsorship manager may send the PGW PCRF a UE server service session filter information including the information on the corresponding UE .

In this way The PGW is capable of supporting all the cases of checking only the IspTrfCode source and destination IP addresses along with IspTrfCode and source and destination IP addresses and UDP TCP port numbers like 5 tuples. Accordingly it is also advantageous in terms of traffic minimization of the mobile communication network and contribution of contribution to new benefit from the viewpoint of the mobile communication network operator.

The first scenario based on the sponsored service property is the scenario called sponsored content delivery in which the sponsored service usage feel is paid in unit of content. This is the case of transmission of specific music video data file. A scenario of the sponsored content delivery is depicted in .

As shown in the sponsored service application running on the UE may connect to the ISP server as a normal Internet service at operation . For example a web browser connects to the web server.

If the mobile subscriber selects a sponsored service content which is paid by the ISP in the subscriber s stead among the services the authentication procedure for the sponsored content is performed between the UE and the sponsorship manger by the sponsorship API function through operations to .

This procedure is performed transparently of applications sponsored service authentication and authorization procedure in such a way of establishing a secure communication path between the UE and the sponsorship manager at operation and transmitting the sponsorship IP password IspCode of the ISP as the owner of the sponsored content and IspTrfCode of the sponsored content user authentication request from the UE to the sponsorship manager at operation .

Although the IspTrfCode may be allocated per content in the case of the sponsored content typically it is preferred to allocate IspTrfCode to a plurality of contents. If the sponsorship ID and password of the UE is valid the sponsorship manager checks whether the requested IspCode and IspTrfCode are of the sponsored content for which the UE has lawfully requested through the procedure of .

If it is determined that the request is lawful the sponsorship manager transmits OK message in reply User authentication response at operation .

In the case of transmitting the response from the sponsorship manager to the UE if it is necessary to change the IspTrfCode allocated by the ISP previously for security the sponsorship manager stores the corresponding information as shown in and then sends the response including IspTrfCode as supplementary information to the UE as shown in .

If the supplementary IspTrfCode is received the UE updates the IspTrfCode of the sponsored service which is has manages with the newly received information. If it is checked that the mobile subscriber accesses the lawful content the UE notifies the user of the initiation of the sponsored service upon receipt of the OK response from the sponsorship manager at operation . This procedure is described in more detail with reference to .

This is performed as the operation in response to calling the sponsored API independently of application program. Accordingly the user may detect the malignant operation of the application program which is made as if a non sponsored service is a sponsored service. That is the all sponsored services is notified at their initiations with the reliability at the low level such as operating system and device drivel levels independently of the application programs.

Afterward the ISP server transfers the sponsored content to the UE at operation . The PGW monitors the traffic transmitted and generates statistical information based on the IspTrfCode and supplementary information by means of the sponsorship filter at operation .

If there is not traffic of sponsored content during a predetermined period the sponsorship filter of the UE detects this and ends the sponsored service independently of the application program at operations and .

Through the sponsored service release procedure the UE notifies the sponsorship manager of the end of the sponsored service as shown in . The information on the traffic amount and time collected by the sponsorship filter of the UE is transmitted to the sponsorship manager. The secure connection between the UE and the sponsorship manager is released. The termination of the service may be triggered by the PGW as well as the UE.

In order to accomplish this it is necessary to provide the PGW with the information for use in checking the individual session such as source and destination IP addresses in addition to IspTrfCode through the procedure of to complement for the lack of the procedure of . If the additional information is acquired the PGW is capable of monitoring the starts and ends of the sessions using the same IspTrfCode based on the additional information along with IspTrfCode. If the lawful content access is terminated the UE notifies the user of the termination of the sponsored service as shown in . This procedure follows the operation of calling the sponsored API independently of the application program.

As a consequence the user is capable of checking the information on the consumed benefit of the sponsored service as well as the situation where an application program operates a non sponsored service as if it is the sponsored service with malignant intention. As described above all the sponsored services notify of their termination at reliable low level such as operating system and device drive independently of application programs.

In the present disclosure the mobile subscriber using the sponsored service and the ISP providing the sponsored service may check the billing statistical information on the sponsored service provided anytime if necessary.

The second scenario based on the sponsored service property is the scenario called sponsored application in which the billing for the time traffic amount consumed by a specific application running on the UE through the mobile communication network is charged to the ISP supporting the corresponding application.

The operation procedure in the sponsored application mode is depicted in . It is similar to the case of with the exception that the application performs authentication with the sponsorship manage through the sponsorship API immediately upon start of the application as shown in . If the authentication is successful the ISP charges for all traffic transmitted received by the corresponding application. Unlike the procedure of the ISP manager notifies the sponsorship manager of the termination of the corresponding application at the termination time point.

A procedure following authentication failure at the initial start time point of the sponsored application is depicted in as a procedure corresponding to that of .

As shown in it is possible to apply the conditions for providing the sponsored service. That is it is possible to restrict the sponsored service with specific time specific location specific user or specific IP address. show the case where the mobile subscriber may use its own location information since the mobile subscriber has allowed for use of the location information to support the sponsored service at specific area. The sponsored service may be provided for use of a coupon issued by an ISP online or offline for a special event. In this case it is possible to provide the sponsored service based on the information corresponding to the coupon number acquired by means of the mobile subscriber and entered into the coupon section of .

The relationship and structure of the sponsorship API the sponsorship functions called by means of the API and sponsorship filter are depicted in . Although it is assumed that the sponsorship filter belongs to the IP layer the sponsorship filter may be implemented on a layer higher or lower than the IP layer. This may be implemented differently depending on the location of IspTrfCode and layer on which the filtering function is provided.

If the corresponding sponsored service is permitted by the sponsorship manager so as to use IspTrfCode or acquire new IspTrfCode the sponsored function transmits a positive response to the sponsored application in response to the permission request and the IspTrfCode corresponding to the sponsored service initiated to the sponsored filter so as to monitor the corresponding service.

The sponsored filter is running on the operating system and communication layer of the terminal that is capable of supporting the sponsored service regardless of the initiation of the sponsored service and if IspTrfCode is sent by the sponsored application through a lawful permission and if any traffic including illegal IspTrfCode arrives or generated by the UE detects and blocks the corresponding illegal service and notifies the sponsorship manager of the process result.

Also the sponsorship filter of the terminal performs the function of detecting no generation of traffic of the corresponding sponsored service during a predetermined period for the internet service of which connection release procedure is unclear and if there is no traffic during the predetermined period terminates the sponsored service internally.

Also the sponsorship filter collects the information on the traffic amount or traffic transmission reception time for the sponsored service through the lawful traffic monitoring function and sends collected information to the sponsorship manager upon completion of the sponsored service such that the billing server performs billing operation in detailed and flexible manner.

The operation at the end time point of the sponsored service is depicted briefly in . The detailed description on the message transmission reception procedure for the corresponding operation has been described already above and the sponsorship function detected the termination of the sponsored service according to the request of the sponsored application or its self determination sends the sponsorship manager the information indicating the termination of the corresponding sponsored service.

As described above the sponsorship filter receives the information on the traffic and time associated with the transmission of the corresponding sponsored service and transmits the received information to the sponsorship manager.

The sponsorship filter is implemented in the PGW identically. The sponsorship filter implemented in the PGW is based on the filter information of the sponsorship service which is received from the sponsorship manager and monitors to meter the traffic amount or time of the lawful service verified ty the sponsorship manager and detect illegal traffic. The sponsorship filter also collects the billing information for the lawful traffic and transmits the billing information to the billing server.

The detailed operation of the sponsorship manager of is depicted in more detail in . If a sponsored service subscription request registration is received from the UE the sponsorship manager determines whether the sponsored service is valid to the corresponding mobile subscriber based on the IspCode of the sponsored service and if so determines whether the supplementary conditions are fulfilled. If all the conditions are fulfilled the sponsorship manager accepts the sponsored service access request and if necessary in the case that IspTrfCode is changed sends the PGW the traffic information about the corresponding sponsored service so as to perform monitoring. The information transmitted at this time is generated by combining the source destination IP addresses and IspTrfCode as described above.

If the sponsorship manager allows for use of the sponsored service lawfully in the UE initializes the information related to the sponsorship filter through the procedure of .

That is the UE sends the IspTrfCode to notify of the filter of the sponsored service added generates transmitted received packet volume service start time StartTime service end time EndTime and service end time inspection timer IdleTimer record for the sponsored service as the supplementary information fields for the corresponding sponsored service initializes the values of the respective fields.

In the sponsorship filter of the PGW which has received the filter information for the sponsored service through the sponsorship manager procedure of also receive the IspTrfCode for lawful allowance and the ISP IP domain information identical with the source destination IP address information as supplementary informations and registers this as supplementary filter information of the sponsorship filter according to the procedure of .

Like the UE a filter including the UE and service server IP addresses may be generated in response to the request of the sponsorship manager the variable for storing start and end times and transmission reception traffic amount of the sponsored service s using the corresponding IspTrfCode are generated and managed for the case of the IspCode unit IspTrfCode unit or combination of IspTrfCode with the UE or service server information. The creation time of the corresponding information may be the time point when the record of the corresponding sponsored service is created at the PGW as shown in or the time point when the first packet of the sponsored service is detected at the PGW as shown in .

The operation of the sponsorship filter of PGW which monitors the traffic exchanged between the UE and the server for the sponsored service permitted by the sponsorship manager in is depicted in .

If an IP packet arrives at the PGW the sponsorship filter of the PGW extracts the IspTrfCode from the corresponding IP packet. If no IspTrfCode is detected the packet is processed as a normal IP packet. If the extracted IspTrfCode is a meaningful IspTrfCode by referencing the database and additional IP address exists the sponsorship filter verifies the lawfulness even with the corresponding address information. If the IspTrfCode and related information are lawful the PGW generates variables such as start and end times and termination detection timer and traffic amount as statistical information and updates the corresponding variables whenever the IP packet of the sponsored service is detected.

The sponsorship filter of the UE corresponding to the sponsorship filter of the PGW of which operation is depicted in detects IspTrfCode of the sponsored service and acquires the statistical information according to the procedure of .

The operation of the sponsorship filter of the PGW at the end time of the sponsored service is depicted in . If there is no transmission reception traffic during the IdleTimer the PGW determines the current time as the end time of the sponsored service and sends the sponsorship manager the collected sponsored service related statistical information to the sponsorship manager in the form of CDR. The information such as variable created for the corresponding sponsored service is deleted to improve memory efficiency. The UE performs the same procedure as shown in .

If the CDR informations are acquired from the UE and the PGW through the procedures of the sponsorship manager integrate the CDR informations received from the two devices and sends the integrated information to the billing server.

If an illegal sponsored service is detected by the sponsorship filter of the PGW or the UE it is reported to the sponsorship manager which stores the detailed information on the illegal use in the database and notifies the corresponding ISP of the detection of the illegal sponsored service through the procedure of .

Although various embodiments of the present disclosure have been described using specific terms the specification and drawings are to be regarded in an illustrative rather than a restrictive sense in order to help understand the present disclosure. It is obvious to those skilled in the art that various modifications and changes can be made thereto without departing from the broader spirit and scope of the disclosure.

