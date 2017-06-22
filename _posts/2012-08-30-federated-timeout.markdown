---

title: Federated timeout
abstract: Techniques for workload federated timeout are presented. A federated service manages communications between service components of a system. Each component queries the federated service to determine a last activity time by the other components of the system before timing out during a session. Each component can update its last activity time based on the discovered last activity time of one of the components to prevent a premature time out from the session.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09497270&OS=09497270&RS=09497270
owner: Novell, Inc.
number: 09497270
owner_city: Provo
owner_country: US
publication_date: 20120830
---
Remote access to services over the Internet has provided consumers with access to theft desired services from virtually any location 24 hours a day and 365 days a year. Additionally the service providers often outsource many of theft features to other remote third party providers. In fact the location of any particular service and the provider s of that service have now become transparent issues that are of little concern to end users. Users can also now access these remote services from mobile devices such as phones from even the remotest of geographical locations.

One problem with omnipresent access to services that may be provided from all over the globe is security. Of particular concern is the time lapse during which no activity is detected on the part of the user when accessing a service. Another problem associated with inactivity is that if the user is truly done accessing a service then unnecessary resources are being consumed by the service providers in keeping a user s session active.

In fact it is a common security practice to use a setting called activity timeout to help secure systems against unauthorized tampering and to free up system resources by closing the users session if there is no activity for some configurable period of time. Use of timeout settings is critical for web based solutions because many times the user does not log out he she just close his her browser application. While most web based solutions routinely set inactivity timeouts this is usually accomplished using the container timeout in products such as Tomcat.

Many customer solutions built today are complete user solutions that include many component services existing in different containers which may run on many computers from a variety of locations. For maximum usability the end user should not be aware of the fragmented nature of the solution. Authentication can be performed via federation so the user continues to experience a true single sign on experience.

In a federated authentication system each service component receives an authentication token such as a Security Assertion Markup Language SAML token and uses that token to build its own session. This means that if a solution has 4 service components there could be up to 5 sessions in 5 containers on 5 servers one for the identity provider the token builder and one for each of the service components the token consumer . However each component service times out at a different rate across the multi component system. Furthermore a single service component can only know about its own activity and not the activity of other service components within the overall system. So components services time out at different rates across a multi component system. This means that one service component of a customer solution can time out while another service component is active with the customer creating system instability poor integration and customer solution failure. Synchronization of per system activity timeouts across multi component service solutions become problematic as more and more of these complex software and information services move to the web and to virtual environments which as discussed above they are .

Various embodiments of the invention provide techniques for federating timeouts. In an embodiment a method for managing a federated timeout is presented.

Specifically and in an embodiment a last recorded activity time is maintained for a session which reflects an up to date time for a most recent activity occurring in the session between a principal and second principals. The last recorded activity time is dynamically communicated to a requesting principal before the requesting principal times out the session due to inactivity for a predefined amount of time as noted by the requesting principal.

A resource includes a user service system device directory data store groups of users combinations and or collections of these things etc. A principal is a specific type of resource such as an automated service or user that acquires an identity. A designation as to what is a resource and what is a principal can change depending upon the context of any given network transaction. Thus if one resource attempts to access another resource the actor of the transaction may be viewed as a principal.

An identity is something that is formulated from one or more identifiers and secrets that provide a statement of roles and or permissions that the identity has in relation to resources. An identifier is information which may be private and permits an identity to be formed and some portions of an identifier may be public information such as a user identifier name etc. Some examples of identifiers include social security number SSN user identifier and password pair account number retina scan fingerprint face scan etc.

A service provider as discussed herein refers to a network based service that may or may not be part of an overall system and which provides some feature or function to a principal which may itself be a service or which may be an end user . Moreover the phrase service component may be used interchangeably and synonymously herein with the phrase service provider. 

A processing environment defines a set of cooperating computing resources such as machines processor and memory enabled devices storage software libraries software systems etc. that form a logical computing infrastructure. A logical computing infrastructure means that computing resources can be geographically distributed across a network such as the Internet. So one computing resource at network site X and be logically combined with another computing resource at network site Y to form a logical processing environment.

The phrases processing environment cloud processing environment and the term cloud may be used interchangeably and synonymously herein.

Moreover it is noted that a cloud refers to a logical and or physical processing environment as discussed above.

Also the techniques presented herein are implemented in machines such as processor or processor enabled devices hardware processors . These machines are configured and programmed to specifically perform the processing of the methods and systems presented herein. Moreover the methods and systems are implemented and reside within a non transitory computer readable storage media or machine readable storage medium and are processed on the machines configured to perform the methods.

Of course the embodiments of the invention can be implemented in a variety of architectural platforms devices operating and server systems and or applications. Any particular architectural layout or implementation presented herein is provided for purposes of illustration and comprehension only and is not intended to limit aspects of the invention.

It is within this context that embodiments of the invention are now discussed within the context of the .

The components of the are implemented in non transitory and processor readable storage medium and are executed on physical processors on one or more networks. Each processor specifically configured to execute the components.

The techniques herein solve the timeout problems discussed above by creating a Federated Timeout Service FTS . The FTS provides the ability to securely update activity from a service component and allows other service components to securely query the activity of the other components. Activity information can be shared between any web service that has the required tokens or credentials. This information can then be used to update session life based on activity from another federated service.

The techniques taught herein and below are described within the context of an example use case scenario. It is to be noted that the various embodiments of the invention are not to be restricted to the use case scenario as others are foreseeable as well without departing from the provided teachings. The scenario described below and within the context of the starts with an example of standard SAML federated authentication and begins with the user John 

Event C John is authenticated by the IDP. This authentication can be done via a cookie from a previous authentication Name and Password SAML Kerberos NTLM Windows NT Local Area Network LAN Manager NTLM or any other accepted authentication mechanism.

The token generated by the IDP and sent to the SPA in event D contains new fields to allow it to interact with the FTS.

The information described above that is contained in the Authentication Token is used to interact with the FTS and enables a secure connection. It can be obtained in a few ways 

Once the SPA has validated the SAML token it uses the information above to update the FTS with session activity. In this example REpresentational State Transfer REST is used but other mechanisms can be used as well including Simple Access Protocol SOAP Hyper Text Transfer Protocol HTTP WS Trust carrier pigeon etc. . The connection from the FTS is authenticated using the information from the IDP authentication secrets or the trust relationship that it has with the FTS.

Event E A REST call to the FTS is made to the URL using the information given by the IDP including the User Session ID and other data to indicate the time of its last activity.

The response from the FTS is an update of the most recent time of any activity by other validated services. The SPA uses this data to update its activity timeout. An example in REST may look like this 

Events H I and J The flows shown in H I and J happens at intervals of time to update the time out. If any activity has occurred at that service point that is newer than what is at the FTS then the FTS is updated.

If the time at the FTS is newer then the new time is returned to the service and the service updates its time out.

If any one of the services or the IDP itself is about to time out because of no activity the service about to time out makes a call to the FTS via Events H J with that service s last activity time and if there is other activity time returned it will update its time out and not time out. If there is no other activity it times out and kills its session.

Any service or the IDP can also make a call to the FTS to logout of the session on the FTS. When this is done all other calls to the FTS receive a timed out response when they update or query the FTS.

The shows a specific interaction for the techniques presented herein and well as the timing of those interactions. The FIGS. that follow expand on these mechanisms.

At the federated timeout controller maintains a last recorded activity time for a session reflecting an up to date time for a most recent activity occurring in the session between a principal and second principals. Here the principal may be viewed as an identity provider or in some instances an end user and the second principals may be viewed as services that comprise a network based service that the identity provider and user are engaged in during the session. Also the establishment of the session and the initial authentication of the principals to one another were discussed above in detail with reference to the .

According to an embodiment at the federated timeout controller interacts with the principal and the second principals during the session via or using assertions.

Continuing with the embodiment of and at the federated timeout controller identifying in each assertion a reporting domain an activity domain a session identifier for the session a principal identifier for a particular one of the principals that initiates the session and a particular activity time for activity within the session. The details and format of these elements within the assertion and variations were presented above in detail with reference to the .

Still continuing with the embodiment of and at the federated timeout controller includes a reporting domain authentication token for authentication with the reporting domain and an activity domain authentication token for authentication with the activity domain. Again the structure and variations of the authentication tokens were presented above in detail with reference to the .

Continuing with the embodiment of and at the federated timeout controller represents each assertion as a modified and extended version of a SAML assertion. Thus new fields can be used as discussed above with reference to the .

In an embodiment at the federated timeout controller receives at different intervals communications from the principal and each of the second principals. Each communication identifies the session via the session identifier a particular principal via a principal identifier or user identifier user being a type of principal can also be an identity for the principal making the communication and a value for an activity time for that particular principal within the session.

Continuing with the embodiment of and at the federated timeout controller authenticates each communication before updating a particular value as the last recorded activity time.

At the federated timeout controller communicates the last recorded activity time to a requesting principal before the requesting principal times out of the session due to inactivity for a predefined amount of time as noted by the requesting principal. That is each requesting principal engaged in the session dynamically queries the federated timeout controller before that requesting principal times out of the session for the last recorded activity time noted by the federated timeout controller. So as was discussed above with reference to the a principal that is about to time out because that principal has last had activity that warrants a time out based on a session defined policy for a length of inactivity time will not time out when the federated timeout controller reports an activity time from another principal in the session that is less than the session defined policy length. Such principal updates its own activity time to comport with the time reported by the federated timeout controller.

According to an embodiment at the federated timeout controller provides an authentication token to an identity provider that is acting as the principal for the session. The authentication token provides an authentication mechanism for the principal and for the second principals when interacting with the federated timeout controller the method . Moreover the identity provider distributes the authentication token to the second principals as part of the session initialization processing.

In an embodiment at the federated timeout controller acquires a time out instruction that is received from the principal or one of the second principals. In response the federated timeout controller returns a timed out response to any particular requesting principals when those requesting principals asks for the last recorded activity time being maintained and managed by the federated timeout controller.

The identity provider is one type of principal that participates in a communication session the identity provider interacts with the principals of the session and the FTS in the manners discussed above with reference to the and as additionally described below with reference to the processing of the .

At the identity provider authenticates a principal during login to a session between the principal and a second principal. It is noted that the identity provider is also a participant in the session.

According to an embodiment at the identity provider intercepts the login directed by the principal to the second principal to perform the authentication. So the identity provider may be operating as a transparent proxy to at least the principal. Some approaches to achieving this interception were discussed above with reference to the which discusses and uses browser redirection.

In an embodiment at the identity provider recognizes the principal as an end user and the second principal as a network based service that includes other third principals as other services that are part of or available to the second principal network based service .

At the identity provider generates an assertion that identifies a federated timeout controller which the second principal and other third principals interact with during the session. The second principal and the other third principals use the federated timeout controller to report last activity times to and use the federated timeout controller to request a most recent activity time before timing out during the session.

According to an embodiment at the identity provider sends authentication credentials to the second principal and or the other third principals for the second principal and or other third principals to use when authenticating with the federated timeout controller during the session. This scenario was discussed at length above with reference to the .

Continuing with the embodiment of and at the identity provider instructs the second principal and or the other third principals to sign the authentication credentials before those credentials for authentication with the federated timeout controller.

In another case at the identity provider instructs the second principal and or other third principals to build their own independent credentials for use when authenticating with the federated timeout controller during the session.

At the identity provider establishes the session and communicates the assertion to the second principal and the other third principals.

According to an embodiment at the identity provider instructs the second principal and or the other third principals to report activity times to the federated timeout controller during the session using the assertion and to also query the federated timeout controller before timing out of the session.

In an embodiment at the identity provider queries the federated timeout controller to obtain an authentication token for the second principal and or the other third principals to use for authentication to the federated timeout controller when interacting with the federated timeout controller during the session.

In an embodiment the federated timeout system implements inter alia the processing associated with the methods and of the respectively and the processing associated with the .

The federated timeout system includes an identity provider and a federated timeout controller . Each of these and their interactions with one another will now be discussed in turn.

The federated timeout system includes a first processing device that includes the identity provider which is programmed within memory of the first processing device and or that is implemented and resides within a non transitory computer readable storage medium as executable instructions that execute on the first processing device. Example processing associated with the identity provider was presented above in detail with reference to the .

The identity provider is configured to configure the principals to report activity times to the federated timeout controller during a session. Moreover the identity provider is configured to principals to check for a most recent activity time with the federated timeout controller before timing out the session. Again it is to be noted that the principals can include an end user that establishes the session and the services to which the end user is going to communicate with during that session. As was noted above as well the identity provider may also be considered as a type of principal. For that matter the federated timeout controller may also be considered as a type of principal. Furthermore the principal establishing the session does not have to be an end user as in some instances the principal is an automated service.

The identity provider is also configured to authenticate the principals to establish the session. This was discussed in detail above with reference to the .

The identity provider is further configured to configure the principals for authentication with the federated timeout controller during interactions of the principals with the federated timeout controller .

The federated timeout system also includes a second processing device that includes the federated timeout controller which is programmed within memory of the second processing device and or that is implemented and resides within a non transitory computer readable storage medium as executable instructions that execute on the second processing device. Example processing associated with the federated timeout controller was presented above in detail with reference to the .

The federated timeout controller is configured to maintain the most recent activity time for the principals for the session that the principals are engaged in . Moreover the federated timeout controller is configured to dynamically deliver the most recent activity time upon request received from one of the principals requesting principal during the session.

It is also be noted that the first and second devices may each be or just one of them a Virtual Machine VM such that the two devices are both part of a same physical machine or same machine architecture. In other cases the devices may be on different physical machines and in some cases may even be remote from one another across a wide area network WAN accessible via the Internet for communication with one another.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

