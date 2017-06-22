---

title: Secure transfer of credit card information
abstract: A method includes receiving, at a video service provider system, a security markup assertion language (SAML) token encrypted for a partner federated security token service (FSTS) device from a client device. The method includes submitting the SAML token to the partner FSTS device in exchange for a partner SAML token. The partner SAML token is encrypted for a partner account device. The method also includes receiving the partner SAML token, and sending the partner SAML token to the client device. The client device is configured to request an access token from the partner account device based on the partner SAML token and to submit an encrypted message including credit card information to the partner account device based on the access token.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09055314&OS=09055314&RS=09055314
owner: VERIZON PATENT AND LICENSING INC.
number: 09055314
owner_city: Basking Ridge
owner_country: US
publication_date: 20121004
---
Video service providers currently provide multiple services and programs including cable television network television and video on demand to their customers. In some instances individual customers may receive combinations of these multiple services from a single video service provider.

Video service providers may protect video services using security assertion markup language SAML which is a standard for exchanging authentication and authorization information between an identity provider such as a security token service and a service provider. Security token services are known to transfer security information in SAML assertions. SAML assertions may contain statements including authentication statements attribute statements and authorization decision statements that allow the service providers to make determinations with regard to a requesting party.

The following detailed description refers to the accompanying drawings. The same reference numbers in different drawings may identify the same or similar elements. Also the following detailed description is exemplary and explanatory only and is not restrictive of the invention as claimed.

Systems and or methods described herein may provide encryption of credit card information using a public key of a partner credit card database server PCCDB . The systems may enable client authentication and secure delivery i.e. transfer from a customer to the PCCDB of credit card information in an online video platform. The received message may only be decrypted by the PCCDB thereby providing end to end security.

User devices may enable a user to receive video content i.e. an online video session from video service provider system . User devices may include for example a gaming console a personal communications system PCS terminal e.g. a smartphone that may combine a cellular radiotelephone with data processing and data communications capabilities a tablet computer a personal computer a laptop computer an Internet television or other types of computation or communication devices.

Video service provider system may be part of a core network that provides online video service. Video service provider system may be affiliated with a service provider entity e.g. a commercial video service provider . Video service provider system may provide multiscreen support for the online video service e.g. for Internet protocol IP based video content to user devices in association with a partner entity i.e. a digital service reseller that acts as a partner of the video service provider entity .

VCMS may aggregate content process content and distribute content. In one implementation VCMS may include a content delivery server and a digital rights management DRM server . VCMS may aggregate content and transcode content into a digital format suitable for consumption on particular user devices . For example VCMS may include a transcoding device to convert an audio video multimedia or graphic file from one format to another e.g. from one bit rate to another bit rate from one resolution to another from one standard to another from one file size to another etc. . VCMS may also encrypt data and communicate with user devices through DRM server to enforce digital rights.

Content delivery server may deliver digital content from a backend server to user devices . In one implementation content delivery server may include a streaming server that provides streaming data packets e.g. via a streaming uniform resource locator URL to user devices e.g. via public network . In one implementation a streaming URL may be session based such that each URL can be used only once for one user device for security purposes.

DRM server may issue validate and or enforce DRM licenses to a mobile client such as an application running on one of user devices . In implementations herein DRM server may communicate with user device to validate an authorization token in issuing a license for an application residing on user device .

Data center may manage the authorization selection and or purchase of multimedia content by a user of user device i.e. based on input associated with the user received from user device . As shown in data center may include a catalog server and an application server . In one implementation data center may be accessed by user devices via public network .

Catalog server may provide a catalog of content for users e.g. of user devices to order consume e.g. buy rent or subscribe . In one implementation catalog server may collect and or present listings of content available to user devices . For example catalog server may receive digital content metadata such as lists or categories of content from VCMS . Catalog server may use the content metadata to provide currently available content options to user devices . Catalog server may provide the content metadata to user device directly or may communicate with user device via application server .

Application server may provide a backend support system for mobile applications residing on user devices . For example application server may permit user device to download an application that enables a user to find content of interest or play downloaded or streaming content. Application server may provide digital content in association with VCMS . In one implementation the interactions between application server and user device may be performed using hypertext transfer protocol HTTP or secure HTTP HTTPS via public network . In one implementation all HTTP transport may be over secure sockets layer SSL or transport layer security TLS . Application server may provide authentication of user devices and secure delivery of credit card information as described below with respect to signal flow and process .

Profile server may store user profile information for users e.g. users of user devices . The user profile information may include various information regarding a user such as login information e.g. a user identifier and a password billing information address information types of services to which the user has subscribed a list of content purchased by the user a list of video content rented by the user a list of video content to which the user has subscribed a user device identifier e.g. a media player identifier a mobile device identifier a set top box identifier a personal computer identifier for user device a video application identifier associated with the video application obtained from application server or the like. Application server may use the user profile information from profile server to authenticate a user and may update the user profile information based on the user s activity e.g. with a user s express permission .

Billing server may manage charging users for services provided via video service provider system . Billing server may include for example a payment processing component a billing component and or a settlement component. In some implementations billing services may be performed by servers external to video service provider system e.g. billing servers for a partner entity .

Physical content distribution system may track availability of physical content e.g. DVDs Blu ray discs memory cards etc. and provide metadata relating to the physical content for inclusion in catalog information provided to users of user devices . In one implementation physical content distribution system may also provide physical content information such as location information so that when a user wants to buy physical content the system may direct the user to the nearest location for purchasing the physical content. Additionally or alternatively physical content distribution system may generate or receive credit information for users e.g. for cross promotion purposes with a partner entity . For example after a user of user device has purchased digital content or a subscription rental of digital content the user may be entitled to credits for obtaining a corresponding physical asset or vice versa.

Customer support system may solicit and or receive user feedback questions or credit related requests.

Private network may include for example one or more private IP networks that use a private IP address space. Private network may include a local area network LAN an intranet a private wide area network WAN etc. In one implementation private network may implement one or more Virtual Private Networks VPNs for providing communication between for example any of VCMS data center profile server billing server physical content distribution system and or customer support system . Private network may be protected separated from other networks such as public network by a firewall. Although shown as a single element in private network may include a number of separate networks.

Public network may include a LAN a WAN such as a cellular network a satellite network a fiber optic network a private WAN or a combination of the Internet and a private WAN etc. that is used to transport data. Although shown as a single element in public network may include a number of separate networks that function to provide services to user devices .

In implementations described herein client authentication and secure delivery of credit card information may be provided to support billing of a recipient of video services from a provider network. The client authentication and secure delivery may be provided in an environment that includes a service provider entity and a partner entity.

Bus may permit communication among the components of device . Processing unit may include one or more processors or microprocessors that interpret and execute instructions. In other implementations processing unit may be implemented as or include one or more application specific integrated circuits ASICs field programmable gate arrays FPGAs or the like.

Memory may include a random access memory RAM or another type of dynamic storage device that stores information and instructions for execution by processing unit a read only memory ROM or another type of static storage device that stores static information and instructions for the processing unit and or some other type of magnetic or optical recording medium and its corresponding drive for storing information and or instructions.

Input device may include a device that permits an operator to input information to device such as a keyboard a keypad a mouse a pen a microphone one or more biometric mechanisms and the like. Output device may include a device that outputs information to the operator such as a display a speaker etc.

Communication interface may include a transceiver that enables device to communicate with other devices and or systems. For example communication interface may include mechanisms for communicating with other devices such as other devices of network .

As described herein device may perform certain operations in response to processing unit executing machine readable instructions contained in a computer readable medium such as memory . A computer readable medium may include a non transitory memory device. A memory device may include space within a single physical memory device or spread across multiple physical memory devices. The machine readable instructions may be read into memory from another computer readable medium or from another device via communication interface . The machine readable instructions contained in memory may cause processing unit to perform processes described herein. Alternatively hardwired circuitry may be used in place of or in combination with machine readable instructions to implement processes described herein. Thus implementations described herein are not limited to any specific combination of hardware circuitry and machine readable instructions.

Although shows exemplary components of device in other implementations device may include fewer components different components differently arranged components or additional components than depicted in . As an example in some implementations input device and or output device may not be implemented by device . In these situations device may be a headless device that does not explicitly include an input or an output device. Alternatively or additionally one or more components of device may perform one or more other tasks described as being performed by one or more other components of device .

Communication between components of online video platform i.e. content delivery server DRM server billing server web server application server partner account server partner STS system and or user device may be implemented to provide client authentication and secure delivery of credit card information such as described below with respect to and signal flow diagram . Communication in online video platform may be implemented using different security protocols such as HTTPS or auth HTTP based on particular information e.g. credit card information a video session customer information etc. that is transmitted between the components. Auth HTTP may include authentication information associated with components of online video platform e.g. communication between partner account server and billing server may be implemented using auth HTTP .

User device may include machine readable instructions such as a web client and a device client which enable user device to securely receive transmit information to content delivery server DRM server web server application server partner account server and or partner STS system .

Web client may enable user device to connect to content delivery server DRM server web server and or partner STS system via the Internet or other similar networks using HTTP .

Device client may be a consumer electronics client or a mobile client based on a particular device type of user device . Device client may enable user device to communicate with for example video service provider system and or present information received from video service provider system to a user. Device client may connect to content delivery server DRM server application server partner account server and or partner STS system to permit a user of user device to log into an account e.g. via application server or present authentication of an identity access catalog information e.g. from catalog server submit an order and or consume live streaming video content e.g. from VCMS .

Web server may provide access to components of online platform to web client via an Internet based interface. For example web server may communicate with application server .

Application server may manage customer service information associated with the service provider entity such as authorized devices entitlement rights of digital contents view preferences and history of digital asset viewing and purchase. The customer service information may be accessed as an extension of partner customer accounts i.e. the partner customer accounts may be viewed effectively as federated accounts in a federated database system. Application server may interface with components of online video platform that are external to video service provider system e.g. partner account server billing server device client etc. via an orchestration layer associated with video service provider system not shown . The orchestration layer is the external interface of the video service provider system . The orchestration layer may include orchestration devices not shown that may receive requests associated with particular components e.g. application server of video service provider system and direct responses from the components to addressed external entities e.g. partner STS system .

The partner entity may provide video services from video service provider system to customers on a reseller basis. Customers may interact with a partner entity to subscribe to video services e.g. the service provider entity may provide video services that are branded or co branded by the partner entity . Partner account server may provide access to partner customer accounts. Partner customer accounts may include customer account information such as contact names email addresses billing and subscription packages maintained by the partner entity.

Partner STS system may provide authentication services associated with the partner entity. Partner STS system may include partner identity provider IDP server and partner federated STS FSTS server .

Partner IDP server may be an identity provider device that issues and validates identities associated with the partner entity. For example partner IDP server may validate login credentials associated with the partner entity and encrypt a response for partner FSTS server .

Partner FSTS server may include or may provide access to partner customer accounts via partner account server by issuing tokens in a federated database system.

Billing server may provide billing services associated with or administered by the partner entity. Billing server may receive credit card information transferred from user device via applications associated with implemented by video service provider system and the service provider entity. The credit card information may be secured from entry at user device to receipt at billing server .

Video service provider account may store information associated with video service provider system . Video service provider account may include entries based on video services provided by video service provider system to user device including information indicating devices entitlement rights preferences and accounting associated with the particular customer.

Devices may include a listing of connected televisions TVs Blu ray players game consoles e.g. Xbox Wii PlayStation etc. and smart phones e.g. iOS Android etc. .

Entitlement rights may indicate video content available to including terms of access to the video content for the particular customer. Video content may include movies TV shows and games . Entitlement rights may indicate that the particular customer has access for video content based on a monthly subscription purchased or rented . Entitlement rights may also indicate whether video content is download permitted and or streaming permitted e.g. either on an item by item or for all video content associated with video service provider account and an asset quality of video content items e.g. whether the video content item is high definition HD standard definition SD etc. .

Preferences may indicate settings associated with the video content for the particular customer such as genres e.g. horror action comedy etc. ratings e.g. parental guidance 13 PG13 restricted R etc. bookmarks for particular video content parental controls e.g. password protection for content rated R etc.

Accounting may include information that may be used to determine charges applicable to the particular customer for video services received from video service provider system . Accounting may include a viewing history and a purchase rental history for the video content items.

Partner account is associated with a partner entity. The partner entity may offer video services provided by video service provider system and may interface directly with the customer. Partner account may include information associated with the customer including contact information info billing info login credentials subscription credits and billing history .

Contact info may include a name an address i.e. mailing address or residential address home phone i.e. a home phone number mobile phone i.e. a mobile phone number and an email associated with the particular customer. Partner entity may receive contact info at initial sign up for the video service in association with the partner entity.

Billing info may include payment methods e.g. credit cards checking accounts PayPal etc. a billing address and a billing phone which may be used to process billing for video services by the partner entity.

Login credentials may include login information for the particular customer that provides access to the video services. For example login credentials may include a login name and password.

Subscription credits may provide access to physical content such as DVDs or Blu ray discs that are offered by the partner entity.

Forwarding module may receive SAML tokens from external devices such as device client of user device and may forward the SAML tokens to other components of online platform such as partner FSTS server . Forwarding module may forward the SAML token based on information included in a message provided by the sending device e.g. partner FSTS server device client etc. .

Video application module may permit user device to download an application that enables a user to find content of interest or play downloaded or streaming content. Video application module may support video services for authenticated customers of video service provider system .

With reference now to device client of user device may not currently have a valid Simple Object Access Protocol SOAP response token R . SOAP is an Extensible Markup Language XML based protocol that specifies a format for exchanging structured information in the implementation of web services in computer networks. Device client may display a login screen and collect service provider login credential process . For example device client may generate a graphical user interface GUI for the user to enter service provider login credentials. The login screen may accept alphanumeric characters. The user may have previously signed up for a service provider user account or may sign up for the user account using web client .

Device client may send a request for an authentication token with service provider login credential as an input to partner IDP server .

Partner IDP server may validate the login credentials . Partner IDP server may send a SAML response token R to device client with SAML assertion signed by partner IDP server and encrypted for partner FSTS server . The authenticity and integrity of the SAML token is maintained by a digital signature of partner IDP server . The SAML token may have a predetermined lifetime e.g. the SAML token may only be valid for a predetermined number of hours . In instances in which device client has a valid token R device client may skip signal flows and and proceed to .

Device client may submit response token R as input to application server in exchange for a SAML token R that is encrypted for partner account server . Application server may forward response token R as input to partner FSTS server in exchange for a SAML token R issued to partner account server .

Partner FSTS server may decrypt the SAML token in response token R validate the SAML token transform the SAML token sign and encrypt the SAML token for partner account server . Partner FSTS server may send a SAML response token R to application server . Application server may send the SAML token R to device client .

Device client may send a request for an access token with an application ID open standard for authorization OAuth secret and SAML token R to partner account server . OAuth is a protocol that allows access via an application programming interface API often associated with an end user to protected resources from a web service based on the OAuth secret and an access token. The application ID and secret may be issued out of band by partner account server . Partner account server may receive the application ID secret and SAML token R and decrypt the message. Partner account server may validate SAML token R to determine whether an access token is to be provided to device client . For example partner account server may decrypt the assertion inside the response with the corresponding private key of partner account server . Partner account server may provide a response to device client that includes the access token.

Device client may encrypt credit card information received from the user . For example device client may prompt the user to enter the credit card information into a corresponding GUI . The credit card message may be encrypted as described below with respect to . Device client may submit the encrypted credit card information with the access token to partner account server .

Credit card information may include a credit card type e.g. VISA MasterCard etc. a credit card number i.e. a sixteen digit number a cardholder name an expiring date of the credit card a card validation value i.e. a three digit number that may be used to validate the credit card and a billing address .

Session key may be a random advanced encryption standard AES 128 bit session key. Session key may be encrypted by the public key of partner credit card database server a component of partner account server .

Digital certificate may be an X.509 public key infrastructure and privilege management infrastructure v3 certificate . Digital certificate may be a 2048 bit public key that is encrypted based on an RSA Rivest Shamir Adelmen secure hash algorithm version 1 SHA1 .

As shown in application server may receive a SAML token response token R from a device client block . The SAML token R may be signed by IDP server and encrypted. Device client may send R to application server in exchange for SAML token R which is issued to partner account server .

Application server may submit SAML token R to partner FSTS server block . Partner FSTS server may decrypt and validate R. Partner FSTS server may transform R into R and encrypt R for partner account server .

Application server may receive SAML token R encrypted for partner account server from partner FSTS server block .

Application server may send the SAML token R to device client block . Device client may receive SAML token R. Device client may send credit card information to partner account server based on SAML token R. The encrypted credit card information may include an application identifier and a client secret based on an open authorization protocol. The client secret may be received out of band and associated with the user of user device .

As shown in user device i.e. device client may identify that user device is not in possession of a valid SAML response token R i.e. an authentication token associated with partner FSTS server block .

User device may request R from partner IDP server if user device does not have a valid R block . The request may include login credentials that are input to a GUI of user device by a user. User device may receive R from partner IDP server block .

User device may submit R in exchange for SAML token R block . User device may have received R from partner IDP server block or may have previously stored R block yes . User device may receive SAML token R encrypted for partner account server block .

User device may send a request for an access token to partner account server block . The request may include an application ID and an OAuth secret. User device may receive the access token from partner account server block .

User device may submit encrypted credit card information e.g. as shown in to partner account server block .

Systems and or methods described herein may allow client authentication and secure delivery of credit card information in an online video platform. The credit card information is protected by encrypting with the public key of a partner credit card database server. The encrypted information may only be decrypted by the partner credit card database server.

In the preceding specification various preferred embodiments have been described with reference to the accompanying drawings. It will however be evident that various modifications and changes may be made thereto and additional embodiments may be implemented without departing from the broader scope of the invention as set forth in the claims that follow. The specification and drawings are accordingly to be regarded in an illustrative rather than restrictive sense. For example while series of blocks have been described with respect to the order of the blocks may be modified in other implementations. Further non dependent blocks may be performed in parallel.

It will be apparent that different aspects of the description provided above may be implemented in many different forms of machine readable instructions firmware and hardware in the implementations illustrated in the figures. The actual machine readable instructions or specialized control hardware used to implement these aspects is not limiting of the invention. Thus the operation and behavior of these aspects were described without reference to the specific machine readable instructions it being understood that machine readable instructions and control hardware can be designed to implement these aspects based on the description herein.

Further certain portions of the invention may be implemented as a component or system that performs one or more functions. These components systems may include hardware such as a processor an ASIC or a FPGA or a combination of hardware and machine readable instructions.

No element act or instruction used in the present application should be construed as critical or essential to the invention unless explicitly described as such. Also as used herein the article a and one of is intended to include one or more items. Further the phrase based on is intended to mean based at least in part on unless explicitly stated otherwise.

