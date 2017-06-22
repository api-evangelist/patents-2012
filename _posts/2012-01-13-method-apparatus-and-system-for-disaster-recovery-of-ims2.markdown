---

title: Method, apparatus, and system for disaster recovery of IMS
abstract: A method, apparatus, and system for disaster recovery of an IP Multimedia Subsystem (IMS) are provided. The method includes: triggering a redundant Call Session Control Function (CSCF); obtaining, by the redundant CSCF, user backup data of registered IMS Private User Identities (IMPIs) that are associated with IMPUs and user service configuration data of IMS Public User Identities (IMPUs) in an IMS subscription from a network storage entity of a user; and recovering, by the redundant CSCF, a corresponding service according to the obtained user backup data of the registered IMPIs and user service configuration data of the IMPUs in the IMS subscription. With the present invention, the one-IMPU multi-IMPI, one-IMPI multi-IMPU, or multi-IMPI multi-IMPU service can be recovered, and this enables the user to have better service continuity experiences.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09661028&OS=09661028&RS=09661028
owner: Huawei Technologies Co., Ltd.
number: 09661028
owner_city: Shenzhen
owner_country: CN
publication_date: 20120113
---
This application is a continuation of U.S. patent application Ser. No. 12 580 643 filed on Oct. 16 2009 which is a continuation of International Patent Application No. PCT CN2008 072583 filed on Sep. 28 2008. The International Application claims the priority of Chinese Patent Application No. 200710030717.0 and 200710167738.7 respectively filed on Sep. 28 2007 and Oct. 26 2007 the entire contents of all of which are incorporated herein by reference in their entireties.

The present invention relates to IP Multimedia Subsystem IMS network technologies and in particular to a method apparatus and system for disaster recovery of an IMS.

An IMS introduces an idea of separating control from bearer into an IP based communication network. The IMS is a core in service processing of the communication network. High reliability of the IMS is the basis of high reliability of the entire communication network.

To improve reliability of the IMS the network disaster recovery capability must be improved. An IMS network includes multiple network entities between which there is a strong association. The network disaster recovery capability means that when a network device fails the failure of the network device has the least impact on the entire IMS network and on users.

In the prior art after registering with an IMS network successfully a User Equipment UE starts a registration timer immediately according to a negotiated registration period when the registration timer expires re registration of the UE is triggered. If a Serving Call Session Control Function S CSCF that provides services for the user fails a new S CSCF may be assigned to the user through a mechanism of re registration triggered by a registration timer.

According to the foregoing descriptions when the S CSCF that provides services for the user fails the network service of the UE can be recovered after the registration timer of the user triggers re registration and an S CSCF is re selected. That is the service interruption duration of the UE depends on the registration period of the UE. The longer the registration period is the longer the service interruption duration will be. To meet the reliability requirements of a telecom network the registration period should be as short as possible. But if the registration period is set to a too small value re registration will occur frequently. With regard to the network frequent re registration increases the processing load of the network and especially frequent re registration occupies valuable air interface resources of a radio access network RAN . With regard to the UE frequent re registration consumes the limited energy of the UE and shortens the standby time of the UE.

A solution to the foregoing problems is available in the prior art. That is during registration the S CSCF backs up the registration related user data such as the IMS Private User Identity IMPI information IMS Public User Identity IMPU information registered Contact address and path information to a Home Subscriber Server HSS . When the S CSCF fails and a UE uses the network an Interrogating CSCF I CSCF may select another S CSCF to provide session services for the UE and the new S CSCF may obtain the user backup data of the IMPU that uses services so as to recover related services of the UE thus implementing disaster recovery of the S CSCF.

Currently user IDs used in an IMS network mainly include an IMPI and an IMPU that are saved in an HSS in subscription mode. When a user performs a related service operation the related entities in the network such as an I CSCF an S CSCF and an Application Server AS obtain the subscription data of the user through a user ID. In the IMS the relation between user IDs and the relation between user IDs and subscription data are complex. As shown in one IMS subscription includes all subscription information that may be transmitted by one UE on a Cx interface. One IMS subscription may include multiple IMPIs but one IMPI belongs to only one IMS subscription one IMPI may include multiple IMPUs and one IMPU may be shared by multiple IMPIs. That is the IMS subscription is in a one to many relation with the IMPI and the IMPI is in a many to many relation with the IMPU. Therefore the service logics such as one IMPI multi IMPU one IMPU multi IMPI and multi IMPI multi IMPU can be implemented flexibly.

When implementing the invention the inventor finds at least the following problem in the foregoing technical solution to IMS disaster recovery in the prior art no detailed recovery solution is worked out against the complex user data model in the IMS therefore when adopting the foregoing technical solution the one IMPU multi IMPI and multi IMPI multi IMPU services of users may be lost thus reducing service continuity experiences of the users. For example when the user data model shown in is taken as an example the processing of the IMS disaster recovery solution in the prior art is as follows 

Assuming that all IMPI and IMPU instances in the IMS subscription shown in are registered on an S CSCF1. If the S CSCF1 fails and if a UE IMPI1 and IMPU3 associated with the service performs periodic re registration a registration request is forwarded to an S CSCF2 according to the foregoing technical solution. The S CSCF2 registers the IMPI1 and IMPU3 successfully through a standard registration process and recovers user backup data of the IMPI1 and IMPU3 to the S CSCF2. In addition an HSS changes the server name saved for the IMS subscription from S CSCF1 to S CSCF2 and then may send a Registration Termination Answer RTA message to the original S CSCF S CSCF1 to notify that a UE migration process is optional and that even if the RTA message is sent the sending fails because of the failure of the original S CSCF. Up to now the disaster recovery process caused by UE IMPI1 and IMPU3 registration is complete. If the IMPU3 is called after receiving a call request an I CSCF searches the HSS for an S CSCF S SCCF2 that serves the IMPU3 in fact the IMS subscription the S CSCF2 is in the normal state and therefore the I CSCF does not add a disaster recovery flag to the call request but routes the request to the S CSCF2 directly after receiving the request the S CSCF2 determines that the IMPU3 has a registered terminal IMPI1 locally and that the call request does not contain a disaster recovery flag so the S CSCF2 does not perform disaster recovery but analyzes whether to send the call request to the IMPI1 as a result the one IMPU multi IMPI service IMPI1 and IMPI2 of the IMPU3 is lost.

Embodiments of the invention provide a method apparatus and system for disaster recovery of an IMS so as to prevent the one IMPU multi IMPI one IMPI multi IMPU or multi IMPI multi IMPU service that is associated with a complex user data model in the IMS from being lost during disaster recovery.

obtaining by the redundant CSCF user backup data of registered IMPIs that are associated with IMPUs and user service configuration data of the IMPUs in an IMS subscription from a network storage entity of a user and

recovering by the redundant CSCF a corresponding service according to the user backup data of the registered IMPIs and the user service configuration data of the IMPUs in the IMS subscription.

judging whether to back up registration subscription data and backing up the registration subscription data if a judgment result is to back up registration subscription data.

a judgment processing unit adapted to judge whether to back up registration subscription data after the start processing unit starts disaster recovery data backup and back up the registration subscription data if a judgment result is to back up registration subscription data.

a disaster recovery data obtaining unit adapted to obtain user backup data of registered IMPIs that are associated with IMPUs and user service configuration data of the IMPUs in an IMS subscription from a network storage entity of a user after a service triggers disaster discovery and

a disaster recovery processing unit adapted to recover a corresponding service according to the user backup data of the registered IMPIs and the user service configuration data of the IMPUs in the IMS subscription that are obtained by the disaster recovery data obtaining unit.

A network storage entity includes a user data storing unit adapted to store user service configuration data user backup data for recovering user services and information of a CSCF where a user is registered and a disaster recovery data transmitting unit adapted to transmit the user backup data to a CSCF. The network storage entity further includes 

a message encapsulating unit adapted to encapsulate a response that carries information of registered IMPIs or IMPUs and

a message sending unit adapted to send the response that carries the information of registered IMPIs or IMPUs to a CSCF.

A network storage entity includes a user data storing unit adapted to store user service configuration data user backup data for recovering user services and information of a CSCF where a user is registered and a disaster recovery processing unit. The disaster recovery processing unit includes 

a data transmitting unit adapted to transmit user backup data of registered IMPIs that are associated with the user and user service configuration data of the IMPUs in an IMS subscription to a redundant CSCF by interacting with the redundant CSCF once or many times if a judgment result of the judging unit is to perform disaster recovery for the CSCF.

a user data storing unit adapted to store user service configuration data user backup data for recovering user services and information of a CSCF where a user is registered.

The network storage entity further includes a disaster recovery processing unit. The disaster recovery processing unit includes 

a data transmitting unit adapted to transmit user backup data of registered IMPIs that are associated with the user and user service configuration data of the IMPUs in an IMS subscription to a redundant CSCF by interacting with the redundant CSCF once or many times if a judgment result of the judging unit is to perform disaster recovery for a CSCF.

a user data storing unit adapted to store user service configuration data user backup data for recovering user services and information of a CSCF where a user is registered and

a message encapsulating unit adapted to encapsulate a response that carries information of registered IMPIs or IMPUs and

a message sending unit adapted to send the response that carries the information of registered IMPIs or IMPUs to a CSCF.

a disaster recovery data obtaining unit adapted to obtain user backup data of registered IMPIs that are associated with IMPUs and user service configuration data of the IMPUs in an IMS subscription from a network storage entity of the user according to the information of registered IMPIs or IMPUs that is carried in the response returned by the network storage entity after a service triggers disaster recovery and

a disaster recovery processing unit adapted to recover a corresponding service of the user according to the user backup data of the registered IMPIs and the user service configuration data of the IMPUs in the IMS subscription that are obtained by the disaster recovery data obtaining unit.

In the foregoing solution after a CSCF fails or is restarted the user backup data of the registered IMPIs that are associated with the user and the user service configuration data of the IMPUs may be recovered by one time service triggering of the user. User service configuration data of other registered IMPUs and user backup data of the IMPIs of the user not covered in this service triggering are recovered in time. Thus the one IMPU multi IMPI one IMPI multi IMPU or multi IMPI multi IMPU service can be recovered and this enables the user to have better service continuity experiences.

User data required by disaster discovery must be backed up in advance. Multiple user data backup modes may be adopted. For example when a UE is registered normally an S CSCF that provides services for the user sends the user backup data to a network storage entity such as an HSS through an extended Attribute Value Pair AVP User Backup Data in a registration Server Assignment Request SAR . The network storage entity may store the user backup data for example may store the user backup data by using the index of an IMPI. Only one piece of backup data needs to be stored for each IMPI.

In the foregoing process of implementing user data backup the S CSCF may back up data associated with user registration including but not limited to a contact address and path information. In addition the S CSCF may back up the registration state subscription data of the UE including but not limited to Call ID From To Cseq and Record Route information.

The following describes a specific user data backup method required for disaster recovery provided in embodiments of the invention with reference to the accompanying drawings. In a disaster recovery data backup method provided in an embodiment of the invention shown in an S CSCF backs up the user backup data to a network storage entity HSS through a Cx interface message at appropriate time. The specific backup process includes the following steps 

Steps An S CSCF processes a registration request of a UE and accepts the registration request of the UE eventually.

A. If the UE has not created registration information locally registration information is created through this registration.

B. If the UE has created registration information locally but key registration data changes for example if either the registered Path information or the registered Contact information changes or both the registered Path information and the registered Contact information change the S CSCF needs to back up the key registration data Path information and Contact information to the HSS through an SAR message REGISTRATION or RE REGISTRATION in addition if key registration subscription data Call ID From To Cseq and Record Route information is available it also needs to be backed up.

If the HSS stores the backup data of the registered UE and the SAR message REGISTRATION or RE REGISTRATION does not carry backup data the HSS may check whether the S CSCF that originates a request is the same as the previously stored name of an S CSCF. If not the HSS may select to delete the stored backup data. This case may occur when the failed original S CSCF has the capability of sending backup data but the new S CSCF does not have such capability.

In addition the key registration subscription data may be backed up during registration subscription. The specific process is as follows 

Steps The S CSCF receives a registration subscription request from the UE and accepts the registration subscription request and then returns a subscription success message to the UE.

A. If the UE has not created subscription information locally registration subscription information is created through this registration subscription.

B. If the UE has created registration subscription information locally but the key registration subscription data changes for example if one or more pieces of the registration subscription information such as Call ID From To and Record Route information change the S CSCF backs up the foregoing key registration subscription data to the HSS through an SAR message REGISTRATION RE REGISTRATION or other newly extended service assignment type value in addition the S CSCF may back up the key registration data to the HSS. In the request the S CSCF may set User Data Already Available to USER DATA ALREADY AVAILABLE to prevent the service configuration data from being sent again.

After the disaster recovery data is backed up the new S CSCF may notify the UE of re registration by recovering the backup subscription data to recover all services of a specific UE when the original S CSCF fails or is restarted. Thus the one IMPU multi IMPI one IMPI multi IMPU or multi IMPI multi IMPU service can be recovered and this enables the user to have better service continuity experiences. For example a process of recovering UE services according to an embodiment of the present invention shown in includes the following steps 

Step The S CSCF analyzes the registration subscription data contained in the user backup data. According to the registration subscription data the S CSCF sends a NOTIFY message to a UE to notify the UE of immediate registration.

Step According to the network indication the UE originates registration immediately to recover network services.

In the foregoing process when the network notifies the UE of registration through the NOTIFY message in a given period of time the S CSCF may perform network deregistration for the UE including deregistration of the related data in the HSS if the UE does not originate registration to the network.

It should be noted that when the S CSCF requests the HSS to recover the service configuration data and backup data of an IMPU the HSS may return the backup data of multiple IMPIs because one IMPU may be associated with multiple IMPIs. The backup data may be transmitted via a new AVP Associated Back Info in an extended SAA or PPR message. For example by adding a new AVP named Associated Registered Identities to the SAA message the HSS returns the information of all registered IMPIs that are associated with the IMPU alternatively by adding a flag bit to the original AVP Associated Identities the HSS returns the information of the registered IMPIs that are associated with the IMPU.

During actual implementation the Associated Back Info may adopt a composite AVP structure. The composite AVP structure is as follows 

The foregoing AVP structure includes two AVPs namely User Name and User Backup Data. User Name carries IMPI information User Backup Data carries the backup data of the IMPI carried in User Name. When one IMPU is associated with multiple IMPIs the HSS may return a message carrying multiple Associated Back Info AVPs.

Or Associated Back Info may be defined as an AVP containing text information. The data model is shown in . Each Associated Back Info instance includes one to n User Back Info instances. Each User Back Info instance includes one UserName instance and at least one User Backup Data instance. Each User Backup Data instance includes the backup data of the IMPI carried in UserName at least the Path and Contact information associated with IMPI registration.

The method for disaster recovery is hereinafter described in detail with reference to exemplary embodiments and accompanying drawings.

As shown in which is a main flowchart of a method for disaster recovery in an embodiment of the invention the specific process of disaster recovery includes the following steps 

Step S A redundant CSCF such as an S CSCF is triggered. During actual implementation when data is unavailable after the CSCF that provides services for a user fails or is restarted disaster recovery may be triggered in each service process. For example the redundant CSCF is triggered when the user originates a call or registration through a UE or the redundant CSCF is triggered when the user terminates a call or when an AS originates a call in place of the UE in addition the redundant CSCF may be triggered in the short message service process or subscription service process.

Step S The redundant CSCF obtains user backup data of registered IMPIs that are associated with user IMPUs and user service configuration data of the IMPUs in an IMS subscription from a network storage entity of the user such as an HSS. In this embodiment during data recovery of a newly selected S CSCF or successfully restarted S CSCF not only the service configuration data of the IMPUs and the user backup data of the IMPIs that are associated with this call or registration but also the user backup data of all registered IMPIs that are associated with the user and the user service configuration data of the IMPUs in the IMS subscription are recovered.

Step S The redundant S CSCF recovers a corresponding service of the user according to the obtained user backup data of registered IMPIs and user service configuration data of the IMPUs in the IMS subscription.

The following describes a method for disaster recovery with reference to embodiments in various application scenarios.

In the first embodiment an HSS judges whether all user data in an IMS subscription is completely recovered to a new S CSCF S CSCF2 namely redundant CSCF . If not the HSS sends a PPR message to the new S CSCF to push the user backup data and the user service configuration data to the new S CSCF. The specific application scenario where a service triggers disaster recovery is as follows when the original S CSCF S CSCF1 where a UE is registered fails a user service origination process such as a call service origination process or a user service registration process triggers disaster recovery. Specifically if the original S CSCF of the UE is unavailable during the call origination process the UE may perform re registration.

As shown in the UE is registered from step . REGISTER to step . 200 OK . The specific registration process is the same as the IMS standard process where 

Step L According to the standard process the HSS may send a Registration Termination Request RTR message to the original S CSCF S CSCF1 of the UE after changing ServerName according to a Multimedia Authentication Request MAR message. In the first embodiment after the HSS sends the RTR SERVER CHANGE message to other associated registered UEs that are affected the HSS does not change the registration state of the UE if the original S CSCF S CSCF1 of the UE does not respond if the HSS knows that the original S CSCF S CSCF1 of the UE fails through a failure detection mechanism the HSS does not need to send the RTR message and does not need to change the UE registration state.

In the first embodiment when determining that the S CSCF1 fails for example the S CSCF1 does not respond to the RTR message or the S CSCF1 failure is detected through the failure detection mechanism the HSS sends a PPR message step . PPR to the S CSCF2 so as to recover the user data in an IMS subscription. Compared with the standard PPR message the sent PPR message contains an additional AVP User Backup Data which is used to carry user backup data and instruct the S CSCF2 to perform disaster recovery for the user information in the PPR message.

Generally one PPR message carries only one user profile which is encapsulated into one AVP User Data that is one PPR message carries only one User Data. When multiple IMPUs registered by one IMPI are in different implicit registration sets the HSS needs to send a PPR message carrying user backup data to different implicit registration sets.

To decrease message traffic on a Cx interface an embodiment of the invention provides another optional extension mode to reduce repeated transmission of backup data. That is in a PPR message multiple AVPs named User Data can be carried and each User Data contains the user service configuration data service profile of all IMPUs in one implicit registration set. Thus the user backup data of one IMPI and service profiles of all the registered IMPUs associated with the IMPI can be recovered by exchanging a PPR message once. The user service configuration data determines the type of a user application service.

After receiving the PPR message the S CSCF2 stores the user backup data and the user service configuration data carried in the PPR message and returns a Push Profile Answer PPA message step . PPA to the HSS. The S CSCF2 performs recovery operations for the user according to the user backup data and the user service configuration data carried in the PPR message for example the S CSCF2 sends a NOTIFY message to the UE to trigger immediate re registration step . recovery processing alternatively when a service request associated with the user is available the S CSCF2 judges the type of the user application service according to the user service configuration data and performs service recovery according to the user backup data.

If other registered IMPUs or IMPIs that are affected in the HSS need to be recovered repeat steps until the data of all registered IMPUs and IMPIs is recovered step . PPR to step . recovery processing .

It should be noted that a specific application scenario where a service triggers disaster recovery is as follows when the original S CSCF where a UE is registered is restarted the recovery processing caused by the call origination of a non migrated user on the S CSCF results in UE re registration. The process of recovering a user service through registration is similar to that in the first embodiment.

In the second embodiment an HSS judges whether all user backup data in an IMS subscription is completely recovered to a new S CSCF. If not the HSS sends a PPR message to the new S CSCF to push the user backup data and the user service configuration data to the new S CSCF. The specific application scenario where a service triggers disaster recovery is as follows the original S CSCF where a UE is registered fails or is restarted and call termination by the UE or call origination by an AS in place of the UE triggers disaster recovery.

Steps After receiving a service termination request from a UE or a service origination request from an AS in place of the UE an I CSCF sends a query message to an HSS to obtain the current S CSCF. If the current S CSCF fails the I CSCF interacts with the HSS to select another S CSCF and then forwards the service request with a disaster recovery flag to the new S CSCF if the current S CSCF indicated by the HSS is restarted successfully after it fails the I CSCF forwards the service request to the successfully restarted S CSCF.

The S CSCF redundant S CSCF that receives the service request determines that disaster recovery needs to be performed according to the disaster recovery flag in the received service request. Alternatively the service request may not carry a disaster recovery flag and when the redundant S CSCF finds that the UE is not registered locally the redundant S CSCF sends an SAR UNREGISTERED USER message to the HSS. After receiving the message the HSS finds that the UE is in the non UNREGISTERED state and then returns an SAA DIAMETER ERROR IN ASSIGNMENT TYPE message. The redundant S CSCF may perform disaster recovery after receiving the SAA DIAMETER ERROR IN ASSIGNMENT TYPE message.

Steps The HSS can determine that the redundant S CSCF needs to recover user data according to the RESTORE request originated by the redundant S CSCF in step and then send a PPR message to recover user data which is similar to steps and in the first embodiment .

When the AS originates a call in place of the UE the call may reach the S CSCF without passing through the I CSCF and disaster recovery may be performed in two cases.

 1 If the S CSCF obtained from the HSS cannot be contacted the AS may route a session to the I CSCF for subsequent routing. The disaster recovery process is the same as above.

 2 If the S CSCF obtained from the HSS can be contacted but the S CSCF is restarted user data may be lost. The S CSCF determines that user data needs to be recovered from the HSS according to the logic of a restart scenario. For other processing steps see steps and .

In the third embodiment an S CSCF determines that disaster recovery needs to be performed the mode of originating a user data request to an HSS for several times may be adopted to recover the user data in an IMS subscription and the index of the originated request is an IMPI. A specific application scenario where a service triggers disaster recovery is as follows the original S CSCF S CSCF1 where a UE is registered fails and call origination by the UE or registration of the UE triggers disaster recovery if the original S CSCF is unavailable when the UE originates a call the UE performs re registration.

Step L This step is the same as step L in the first embodiment. If an HSS does not detect that the S CSCF1 fails the HSS sends an RTR message if the HSS does not receive an RTA message the HSS does not change the registration state of the UE.

Steps The UE originates a registration request an I CSCF sends a registration request to the S CSCF2 by exchanging a UAR or UAA message with the HSS and the S CSCF2 sends an SAR message to the HSS after authenticating the UE.

Step The HSS sends an SAA message to the S CSCF2 carrying the information of all registered IMPIs in an IMS subscription in addition to Associated Identities all IMPIs in the IMS subscription in the third embodiment the information of the registered IMPIs can be returned by adding AVP Associated Registered Identities or adding a flag bit to the original AVP Associated Identities.

Step After obtaining the list of registered IMPIs the S CSCF2 checks the local registered UEs in the IMS subscription. If the registered UEs indicated in the registered IMPI user information that is provided by the HSS are not registered in the S CSCF2 the S CSCF2 may send a Service Restore Request SRR or SAR message carrying disaster recovery indication information to the HSS. The SRR or SAR message carries one IMPI that is not registered in the list of registered IMPIs so as to request the HSS to recover the user backup data of the IMPI.

Step After receiving the request for recovering the user data of the unregistered IMPI in the list of registered IMPIs the HSS returns a response carrying the user backup data of the IMPI and the user service configuration data of the IMPU associated with the IMPI.

In the third embodiment the SRA or SAA message can be extended so that it may carry multiple User Data AVPs thus returning the user service configuration data of the IMPUs that are associated with one IMPI but belong to different implicit registration sets.

After the S CSCF receives the response the S CSCF performs recovery operations according to the backup data in the response.

Steps If the list of registered IMPIs returned in step contains multiple IMPIs the recovery operations in steps and can be performed for each IMPI.

In the fourth embodiment an S CSCF determines that disaster recovery needs to be performed the mode of originating a user data request to an HSS for several times may be adopted to recover the user data in an IMS subscription and the index of the originated request is an IMPI. A specific application scenario where a service triggers disaster recovery is as follows the S CSCF is restarted and call origination by a UE or registration of the UE triggers disaster recovery if the S CSCF is restarted and the user data of the caller is unavailable when the UE originates a call the UE performs re registration.

Steps A UE originates a registration request after an S CSCF is successfully restarted an I CSCF sends a registration request to the restarted S CSCF by exchanging a UAR or UAA message with an HSS and the S CSCF sends an SAR message to the HSS after authenticating the UE.

Steps These steps are the same as steps in the third embodiment. The restarted S CSCF can completely recover all user data in an IMS subscription.

In the fifth embodiment an S CSCF determines that disaster recovery needs to be performed the mode of originating a user data request to an HSS for several times may be adopted to recover the user data in an IMS subscription and the index of the originated request is an IMPI. A specific application scenario where a service triggers disaster recovery is as follows the S CSCF fails or is restarted and call termination by the UE or call origination by an AS in place of the UE through an I CSCF triggers disaster recovery.

Steps After receiving a service termination request from a UE or a service origination request from an AS in place of the UE an I CSCF sends a query message to an HSS to obtain the current S CSCF. If the current S CSCF fails the I CSCF interacts with the HSS to select another S CSCF and then forwards the service request with a disaster recovery flag to the new S CSCF if the current S CSCF indicated by the HSS is restarted successfully after it fails the I CSCF forwards the service request to the successfully restarted S CSCF.

The S CSCF that receives the service request determines that disaster recovery needs to be performed according to the disaster recovery flag in the received service request. Alternatively the service request may not carry a disaster recovery flag and when the S CSCF finds that the UE is not registered locally the S CSCF sends an SAR UNREGISTERED USER message to the HSS. After receiving the message the HSS finds that the UE is in the non UNREGISTERED state and then returns an SAA DIAMETER ERROR IN ASSIGNMENT TYPE message. The S CSCF may perform disaster recovery after receiving the SAA DIAMETER ERROR IN ASSIGNMENT TYPE message.

Step In the disaster recovery response from the HSS in addition to the service profile of the IMPU or the service profiles of all IMPUs in the implicit registration set of the IMPU and the user backup data of IMPIs the information of the registered IMPIs in an IMS subscription needs to be returned. In the fifth embodiment for example AVP Associated Registered Identities may be added to the recovery response to carry the information of the registered IMPIs.

When the AS originates a call in place of the UE the call may reach the S CSCF without passing through the I CSCF and disaster recovery may be performed in two cases.

 1 If the S CSCF obtained from the HSS cannot be contacted the AS may route a session to the I CSCF for subsequent routing. The subsequent disaster recovery process is the same as above.

 2 If the S CSCF obtained from the HSS can be contacted but the S CSCF is restarted user data may be lost. The S CSCF determines that user data needs to be recovered from the HSS according to the logic of a restart scenario. For other processing steps see step and subsequent steps.

In addition a disaster recovery request can be originated with the index of an IMPU according to the method for disaster recovery according to a sixth embodiment of the invention shown in .

In the sixth embodiment an S CSCF determines that disaster recovery needs to be performed the mode of originating a disaster recovery user data request to an HSS for several times may be adopted to recover the user data in an IMS subscription and the index of the originated request is an IMPU. The sixth embodiment may be applicable to various service triggering processes such as a calling or called service triggering process originated by a UE or a calling recovery triggering process originated by an AS in place of the UE. The service triggering processes are not described in detail. Only the method for completely recovering IMS subscription data is described.

Step The HSS returns an SRA or SAA message carrying the backup data of all registered IMPIs that are directly associated with the IMPU carried in the SRR or SAR message through the AVP User Data the HSS returns the user service configuration data of all IMPUs in the UE or implicit registration set of the IMPU. In addition the HSS returns the list of other registered IMPUs in an IMS subscription.

After obtaining the list of registered IMPUs the S CSCF recovers the complete data of the IMPUs one by one through Server Assignment Type in the extended SAR message for example the S CSCF adds a new operation type RESTORE ONE to the SAR message so as to request the HSS to recover the complete data of the IMPUs one by one.

Step After receiving the SAR message of the RESTORE ONE type the HSS returns the backup data User Backup Data of all registered IMPIs that are directly associated with the IMPU carried in the SAR message. Through the User Data AVP the HSS returns the user profile of the UE of the IMPU or the UE in the implicit registration set of the IMPU. The S CSCF recovers user data according to the data.

If the IMPU list returned in step contains multiple IMPUs the recovery operations in steps and are performed for each IMPU.

The seventh embodiment is different from the foregoing embodiments. In this embodiment the S CSCF recovers all user backup data in an IMS subscription through one time disaster recovery. The seventh embodiment may be applicable to various service triggering processes. The service triggering processes are not described in detail.

As shown in the process of recovering all user backup data in an IMS subscription through one time disaster recovery may be implemented through the following steps 

Step The HSS queries for the registration instances of all IMPIs and IMPUs in an IMS subscription of the IMPU carried in the SRR or SAR message and then returns all user backup data and user service configuration data in the registration instances to the S CSCF through an SRA or SAA message.

In this embodiment the SRA or SAA message needs to be extended to support multiple AVPs with the name of User Data. The contents encapsulated in each User Data comply with the specified standard and the contents include Private Identity IMPUs in the related implicit registration set and service profiles of these IMPUs.

The eighth embodiment is different from the first to sixth embodiments. In the eighth embodiment the S CSCF recovers all data in an IMS subscription through one time disaster recovery and the HSS recovers all user backup data in an IMS subscription through a PPR or PPA message. The eighth embodiment may be applicable to various service triggering processes. The service triggering processes are not described in detail.

As shown in the process of recovering all user backup data in an IMS subscription through one time disaster recovery may be implemented through the following steps 

Step The HSS may change ServerName by exchanging an MAR or MAA message and determine that the original S CSCF fails for example no response is returned when an RTR message is sent . Then the HSS sends all user backup data and user service configuration data in an IMS subscription of the affected IMPU to a redundant S CSCF through a PPR message.

Alternatively the HSS may know that the current scenario is a disaster recovery scenario by exchanging an SRR or SRA or SAR or SAA message. Then the HSS sends all user backup data and user service configuration data in the IMS subscription of the affected IMPU to the redundant S CSCF through a PPR message.

It should be noted that in the foregoing implementation process the PPR message needs to be extended to support multiple AVPs with the name of User Data. The contents encapsulated in each User Data comply with the specified standard and the contents include Private Identity related IMPUs in the implicit registration set and service profiles of these IMPUs.

Therefore in the first to eighth embodiments when the method for recovering the user backup data and user service data in an IMS subscription once is adopted user service configuration data of other registered IMPUs and user backup data of IMPIs of the user not covered in this service triggering are recovered in time. Thus the one IMPU multi IMPI one IMPI multi IMPU or multi IMPI multi IMPU service can be recovered and this enables the user to have better service continuity experiences.

In the ninth embodiment an S CSCF determines that disaster recovery needs to be performed the service data of one IMPU service data of IMPUs in the implicit registration set of the IMPU and backup data of all registered IMPIs that are associated with the IMPU are recovered once. A specific application scenario where a service triggers disaster recovery is as follows the S CSCF fails and call origination by a UE or registration of the UE triggers disaster recovery if the original S CSCF is unavailable when the UE originates a call the UE performs re registration.

Step L This step is the same as step L in the first embodiment. If an HSS does not detect that the original S CSCF S CSCF1 where the UE is registered fails the HSS sends an RTR message to the original S CSCF of the UE if the HSS does not receive an RTA message the HSS does not change the registration state of the UE.

Steps The UE originates a registration request an I CSCF sends a registration request to the S CSCF2 by exchanging a UAR or UAA message with the HSS and the S CSCF2 originates an SAR message to the HSS after authenticating the UE.

Step The HSS returns an SAA message to the S CSCF2 carrying the information of the registered IMPIs that are directly associated with the IMPU carried in the SAR message. If no registered IMPIs are associated with the IMPU except the IMPIs carried in the SAR message the HSS does not need to return the information of the registered IMPIs. In the ninth embodiment the information of the registered IMPIs that are associated with the IMPU can be returned by adding an AVP Associated Registered Identities or adding a flag bit to the original AVP Associated Identities.

If the HSS does not return the information of the registered IMPIs that are associated with the IMPU step and the subsequent are not required.

Step After obtaining the list of registered IMPIs the S CSCF2 checks the registered IMPIs that are associated with the IMPU locally. If the registered IMPIs provided by the HSS are not registered in the S CSCF2 the S CSCF2 may send an SRR or SAR message carrying disaster recovery indication information to the HSS. The SRR or SAR message carries the IMPU of the registration request so as to request the HSS to recover the user backup data of the IMPU. The service configuration data of the IMPU may also be requested. If the user service configuration data service profile is already returned in the SAA message User Data Already Available in the request may be set to USER DATA ALREADY AVAILABLE so that the HSS does not send the service profile again but the user backup data is still sent.

Step After receiving the request for recovering the user data of the IMPU the HSS returns the user backup data of the IMPU or the user backup data of all IMPIs in the implicit registration set of the IMPU and the service profile of the IMPU or the service profiles of all IMPUs in the implicit registration set of the IMPU. If the S CSCF sets User Data Already Available to USER DATA ALREADY AVAILABLE the HSS may not return the service profile.

After receiving the response the S CSCF2 performs recovery operations according to the backup data in the response.

In the tenth embodiment an S CSCF determines that disaster recovery needs to be performed the service data of one IMPU service data of IMPUs in the implicit registration set of the IMPU and backup data of all registered IMPIs that are associated with the IMPU are recovered once. A specific application scenario where a service triggers disaster recovery is as follows the S CSCF is restarted and call origination by a UE or registration of the UE triggers disaster recovery if the S CSCF is restarted and the user data of the caller is unavailable when the UE originates a call the UE performs re registration.

Steps A UE originates a registration request after an S CSCF is successfully restarted an I CSCF sends a registration request to the restarted S CSCF by exchanging a UAR or UAA message with an HSS and the S CSCF originates an SAR message to the HSS after authenticating the UE.

Steps These steps are the same as steps in the ninth embodiment. The restarted S CSCF can completely recover all registration data and service data of an IMPU and of IMPUs in the implicit registration set of the IMPU in one operation.

In the eleventh embodiment an S CSCF determines that disaster recovery needs to be performed the service data of one IMPU service data of IMPUs in the implicit registration set of the IMPU and registration data of all registered IMPIs that are associated with the IMPU are recovered once. A specific application scenario where a service triggers disaster recovery is as follows the S CSCF fails or is restarted and call termination by a UE or call origination by an AS in place of the UE through an I CSCF triggers disaster recovery.

Steps An I CSCF receives a service termination request from a UE or a service origination request from an AS in place of the UE and then originates a query message to an HSS to obtain the current S CSCF. If the current S CSCF fails the I CSCF interacts with the HSS to select another S CSCF and then forwards the service request with a disaster recovery flag to the new S CSCF if the current S CSCF indicated by the HSS is restarted successfully after it fails the I CSCF forwards the service request to the successfully restarted S CSCF.

The S CSCF that receives the service request determines that disaster recovery needs to be performed according to the disaster recovery flag in the received service request. Alternatively the service request may not carry a disaster recovery flag and when the S CSCF finds that the UE is not registered locally the S CSCF originates an SAR UNREGISTERED USER request to the HSS. After receiving the request the HSS finds that the UE is in the REGISTERED state and then returns an SAA DIAMETER ERROR IN ASSIGNMENT TYPE message. The S CSCF may perform disaster recovery after receiving the SAA DIAMETER ERROR IN ASSIGNMENT TYPE message.

Step In the SAA message the HSS returns the service profile of the IMPU or the service profiles of all IMPUs in the implicit registration set of the IMPU and the user backup data of all IMPIs associated with the IMPU or the user backup data of all IMPIs in the implicit registration set of the IMPU. The HSS may return an SAA message carrying the service profile of the IMPU or the service profiles of all IMPUs in the implicit registration set of the IMPU and the user backup data of all IMPIs associated with the IMPU or the user backup data of all IMPIs associated with all IMPUs in the implicit registration set of the IMPU as well as DIAMETER ERROR IN ASSIGNMENT TYPE described in step to the S CSCF.

After receiving the response the S CSCF performs recovery operations according to the backup data in the response.

When the AS originates a call in place of the UE the call may reach the S CSCF without passing through the I CSCF and disaster recovery may be performed in two cases.

 1 If the S CSCF obtained from the HSS cannot be contacted the AS may route a session to the I CSCF for subsequent routing. The subsequent disaster recovery process is the same as above.

 2 If the S CSCF obtained from the HSS can be contacted but the S CSCF is restarted user data may be lost. The S CSCF determines that user data needs to be recovered from the HSS according to the logic of a restart scenario. For other processing steps see step and subsequent steps.

Therefore in the ninth to eleventh embodiments the user backup data and user service data that are associated with the affected IMPU are recovered completely in each service triggering operation. The complete user service data and user backup data can be obtained in each service triggering operation and the one IMPU multi IMPI one IMPI multi IMPU or multi IMPI multi IMPU service can also be recovered. Thus the user has better service continuity experiences.

To implement the foregoing processing methods provided in embodiments of the invention the existing network system and device functions need to be extended accordingly.

In this embodiment an IMS includes a CSCF1 such as an S CSCF and a network storage entity such as an HSS. The network storage entity includes a user data storing unit and a disaster recovery processing unit .

The user data storing unit is adapted to store user service configuration data user backup data for recovering user services and information of a CSCF where a user is registered.

The disaster recovery processing unit is adapted to perform disaster recovery. A specific structure of the disaster recovery processing unit is shown in . Specifically the disaster recovery processing unit includes a judging unit and a data transmitting unit .

The judging unit is adapted to judge whether to perform disaster recover for a CSCF. During specific implementation the judging unit may adopt various structures. For example one specific structure of the judging unit shown in includes 

a parsing unit adapted to parse an SAR message carrying a recovery indication that is sent by a CSCF so as to determine whether the SAR message carries recovery indication information and

a determining unit according to the parsing result of the parsing unit adapted to determine that disaster discovery needs to be performed for a CSCF if the SAR message carries recovery indication information.

a detecting unit adapted to detect whether a CSCF where a user is registered changes and whether a network storage entity of the user receives an RTA message returned by the CSCF after sending an RTR message to the original CSCF where the user is registered and

a determining unit adapted to determine that disaster recovery needs to be performed for the CSCF if the detection result of the detecting unit shows that the CSCF where the user is registered changes and that the network storage entity of the user does not receive the RTA message returned by the CSCF.

a detecting unit adapted to detect whether a CSCF where a user is registered changes and whether the original CSCF where the user is registered fails and

a determining unit adapted to determine that disaster recovery needs to be performed for the CSCF if the detection result of the detecting unit shows that the CSCF where the user is registered changes and that the original CSCF where the user is registered fails.

The data transmitting unit is adapted to transmit the user backup data of the registered IMPIs that are associated with the user and the user service configuration data of the IMPUs in an IMS subscription to a redundant CSCF by interacting with the redundant CSCF once or many times if the judgment result of the judging unit is yes.

In this embodiment an IMS includes a CSCF1 such as an S CSCF and a network storage entity such as an HSS. The network storage entity includes a disaster recovery data obtaining unit and a disaster recovery processing unit .

The disaster recovery data obtaining unit is adapted to obtain the user backup data of the registered IMPIs that are associated with user IMPUs and the user service configuration data of the IMPUs in an IMS subscription from a network storage entity of the user according to the information of registered IMPIs or IMPUs that is carried in a response returned by the network storage entity after a service triggers disaster recovery.

The disaster recovery processing unit is adapted to recover the corresponding service according to the user backup data of the registered IMPIs and the user service configuration data of the IMPUs in the IMS subscription that are obtained by the disaster recovery data obtaining unit .

In one specific structure of the disaster recovery data obtaining unit of the invention shown in the disaster recovery data obtaining unit may include 

a parsing unit adapted to parse the information of the registered IMPIs that are associated with user IMPUs in an IMS subscription transmitted from an HSS of the user 

a judging unit adapted to determine an IMPI to be recovered according to the received information of registered IMPIs 

a requesting unit adapted to request the user backup data of the IMPI and the user service configuration data of the IMPU associated with the IMPI determined by the judging unit from the HSS of the user and

a receiving unit adapted to receive the user backup data of the IMPI and the user service configuration data of the IMPU associated with the IMPI carried in the response returned by the HSS of the user.

In addition in another specific structure of the disaster recovery data obtaining unit of the invention shown in the disaster recovery data obtaining unit may include 

a parsing unit adapted to parse the information of the registered IMPUs that are associated with user IMPUs in an IMS subscription transmitted from an HSS of the user 

a judging unit adapted to determine an IMPU to be recovered according to the received information of registered IMPUs 

a requesting unit adapted to request the user backup data of the registered IMPI that is directly associated with the IMPU determined by the judging unit and the user service configuration data of the IMPU associated with the IMPI from the HSS of the user and

a receiving unit adapted to receive the user backup data of the registered IMPI that is directly associated with the IMPU and the user service configuration data of the IMPU carried in the response returned by the HSS of the user.

In another specific structure of the disaster recovery data obtaining unit of the invention shown in the disaster recovery data obtaining unit may include 

a parsing unit adapted to parse the information of the registered IMPIs that are associated with user IMPUs in an IMS subscription transmitted by a network storage entity of the user 

a judging unit adapted to determine an IMPU to be recovered according to the received information of registered IMPIs 

a requesting unit adapted to request the user backup data of the registered IMPI that is directly associated with the IMPU to be recovered which is determined by the judging unit and the user service configuration data of the IMPU from the network storage entity of the user and

a receiving unit adapted to receive the user backup data of the registered IMPI that is directly associated with the IMPU and the user service configuration data of the IMPU carried in the response returned by the network storage entity of the user.

a user data storing unit adapted to store user service configuration data user backup data for recovering user services and information of a CSCF where a user is registered and

a disaster recovery data transmitting unit adapted to transmit the user backup data for disaster recovery to a CSCF.

a message encapsulating unit adapted to encapsulate a response carrying the information of registered IMPIs or IMPUs where the response may be any message such as an SAA message which carries the information of registered IMPIs or IMPUs through an AVP Associated Registered Identities of the SAA message or by adding a flag bit to the AVP Associated Identities of the SAA message and

a message sending unit adapted to send the response that carries the information of registered IMPIs or IMPUs to a CSCF.

As shown in a CSCF about disaster recovery data backup may include the following functional units in a network structure of an IMS about disaster recovery in an embodiment of the invention 

a start processing unit adapted to start disaster recovery data backup which may start disaster recovery data backup after user registration subscription is complete during specific implementation and

a judgment processing unit adapted to judge whether to back up registration subscription data after the start processing unit starts disaster recovery data backup and back up the registration subscription data if the judgment result is to back up registration subscription data.

Although the invention has been described through several exemplary embodiments the invention is not limited to such embodiments. It is apparent that those skilled in the art can make various modifications and variations to the invention without departing from the spirit and scope of the invention. The invention is intended to cover the modifications and variations provided that they fall in the scope of protection defined by the following claims or their equivalents.

