---

title: System and method for intelligent caching
abstract: As mobile subscribers increasingly employ their wireless devices to perform an ever expanding range of activities, it has become more and more important for all of the different entities in a wireless ecosystem (e.g., wireless carriers, intermediaries, service providers, etc.) to complete their processing activities in the most efficient, expeditious, flexible, etc. manner possible. An intelligent caching mechanism, through which for example various of the results of a preparatory step may be preserved for subsequent reuse, can inter alia incrementally reduce processing time, reduce system and network resource consumption, save money, etc.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09071557&OS=09071557&RS=09071557
owner: Sybase 356, Inc.
number: 09071557
owner_city: Reston
owner_country: US
publication_date: 20121130
---
This application claims the benefit of U.S. Provisional Application No. 61 566 140 filed Dec. 2 2011 which is incorporated herein by reference in its entirety.

The present invention relates generally to telecommunications services. More particularly the present invention relates to capabilities that can enhance substantially the value and usefulness of various communication paradigms including inter alia Short Message Service SMS Multimedia Message Service MMS Internet Protocol IP Multimedia Subsystem IMS Wireless Application Protocol WAP Electronic Mail E Mail Instant Messaging IM streaming audio video etc. data etc.

As the wireless revolution continues to march forward through various flavors of 2G 3G 4G and beyond the importance to a Mobile Subscriber MS for example a user of a Wireless Device WD such as a mobile telephone a portable computing device a BlackBerry a computer etc. that is serviced in some way by a Wireless Carrier WC of their WD grows substantially.

One consequence of the growing importance of WDs is the resulting ubiquitous nature of WDs i.e. MSs carry them at almost all times and use them for an ever increasing range of activities.

 Note While portions of the discussion below will for simplicity of exposition refer to messaging generally and certain types of messaging including inter alia SMS MMS etc. specifically it will be readily apparent to one of ordinary skill in the relevant art that application of aspects of the present invention to numerous other communication paradigms including inter alia a Voice Over IP VoIP data stream software application e.g. game etc. data a Session Initiation Protocol SIP addressed artifact a video data stream e.g. a movie a video conference call etc. a voice telephone call an audio data stream e.g. a song etc. signaling and other command and control data etc. is easily possible and indeed is fully within the scope of the present invention. 

Over the past many years various factors including the ubiquitous nature of WDs have driven a steady annual increase year over year in among other things the number of SMS MMS etc. messages that have been exchanged by and between WDs. That steady increase shows no sign of abating. For example as reported by the industry group CTIA see ctia.org on the World Wide Web in the U.S. there were over 2.1 trillion SMS messages sent during 2010 up from approximately 363 billion SMS messages sent during 2007 approximately 158 billion SMS messages sent during 2006 and approximately 81 billion SMS messages sent during 2005 and there were over 56.6 billion MMS messages sent during 2010 up from approximately 34.0 billion MMS messages sent during 2009 and approximately 2.7 billion MMS messages sent during 2006 .

As the volume of SMS MMS etc. messaging has increased in the past and at present continues to increase it has become more and more important for all of the different entities that process messages e.g. WCs intermediaries enterprises Content Providers CPs Service Providers SPs etc. to deliver messages in the most efficient expeditious flexible etc. manner possible.

A message may contain among other things a destination address i.e. the address to where the message should be delivered e.g. for a Peer to Peer P2P SMS message perhaps the Telephone Number TN of the recipient MS WD for an Application to Peer A2P SMS message perhaps a Short Code SC that is associated with a particular service such as for example an advertising campaign etc.

The delivery of a message may involve a number of operations including possibly inter alia 1 one or more preparatory steps e.g. the resolution of the message s destination address i.e. the authoritative identification of the entity e.g. WC landline carrier etc. that at the moment that the message is being routed services or that is otherwise associated with the address the identification of the current physical location of the recipient obtaining an identifying value such as for example an International Mobile Subscriber Identity IMSI value etc. and 2 one or more conveyance steps e.g. the actual delivery of possibly among other things the body or the content of the message etc. .

Under certain circumstances various of the preparatory steps may become duplicative. For example in the case where 1 MSsends an SMS message to MS 2 MSreplies to MS s message resulting in an SMS message going from MSback to MS and 3 MSreplies to MS s reply message resulting in an SMS message going from MSback to MS various of the preparatory steps associated with sending the second SMS message from MSto MS including inter alia resolving a destination MS s address securing an IMSI value etc. may be duplicative and consequently may unnecessarily consume precious resources including inter alia time money system resources network resources etc. .

To among other things address the effort duplication issues noted above it would be desirable to intelligently cache selected of the results of various of the preparatory steps for subsequent reuse. Such intelligent caching would inter alia incrementally reduce message processing time reduce system and network resource consumption by for example reducing Signaling System Number 7 SS7 Message Signal Unit MSU counts save money etc. Given the staggering message volumes that were summarized above such intelligent caching would inter alia result in significant benefits.

The present invention provides a generalized infrastructure that offers among other things such intelligent caching capabilities and addresses various of the not insubstantial challenges that are associated with same in new and innovatory ways.

One embodiment of aspects of the present invention offers a server based method for directing a quanta of data that includes at least 1 receiving a quanta of data at a gateway the quanta of data comprising an originating address a destination address and a content 2 performing a plurality of processing steps including at least a creating an Internal Message Object IMO from at least aspects of the quanta of data b characterizing aspects of the quanta of data including at least by a type c resolving the destination address and d obviating the need to complete a preparatory step by retrieving at least an identifying value from a cache and 3 utilizing the identifying value to complete a conveyance step through a gateway configured to select aspects of the IMO for dispatch via a delivery route.

An alternative embodiment of aspects of the present invention offers a processor based system that is configured to direct a quanta of data and which includes at least 1 a gateway configured to receive a quanta of data the quanta of data comprising an originating address a destination address and a content 2 workflow modules configured to perform a plurality of processing steps including at least a create an Internal Message Object IMO from at least aspects of the quanta of data b characterize aspects of the quanta of data including at least by a type c resolve the destination address and d obviate the need to complete a preparatory step by retrieving an identifying value from a cache and 3 a gateway configured to utilize the identifying value to complete a conveyance step by selecting aspects of the IMO for dispatch via a delivery route.

These and other features of the embodiments of the present invention along with their attendant advantages will be more fully appreciated upon a reading of the following detailed description in conjunction with the associated drawings.

The present invention will now be described with reference to the accompanying drawings. In the drawings generally like reference numbers indicate identical or functionally similar elements. Additionally generally the left most digit s of a reference number identifies the drawing in which the reference number first appears. For example in the reference numeral would direct the reader to for the first appearance of that reference numeral.

The following detailed description of the present invention refers to the accompanying drawings that illustrate exemplary embodiments consistent with this invention. Other embodiments are possible and modifications can be made to the embodiments within the spirit and scope of the invention. Therefore the detailed description is not meant to limit the invention.

Note that in this description references to one embodiment or an embodiment mean that the feature being referred to is included in at least one embodiment of the present invention. Further separate references to one embodiment in this description do not necessarily refer to the same embodiment however neither are such embodiments mutually exclusive unless so stated and except as will be readily apparent to those skilled in the art.

In the discussion below aspects of the present invention are described and illustrated as residing within a centrally located full featured MICV facility. Reference is made to U.S. Pat. No. 7 154 901 entitled INTERMEDIARY NETWORK SYSTEM AND METHOD FOR FACILITATING MESSAGE EXCHANGE BETWEEN WIRELESS NETWORKS and its associated continuations for a discussion of the concept of a MICV a summary of various of the services functions etc. that may be performed by a MICV and a discussion of various of the advantages that may arise from same. A MICV may for example be realized through any combination of possibly inter alia any one or more of 1 an element of a WC an element of a landline carrier or multiple such elements working together 2 a Third Party 3P such as possibly inter alia a merchant a CP such as for example a news organization an advertising agency a brand etc. a financial institution a SP such as for example a provider of mobile services etc. 3 multiple 3P entities working together 4 a service bureau 5 a message service provider and or 6 other entities.

As illustrated in and reference numeral a MICV is disposed between possibly inter alia multiple WCs WC WC WC on one side and multiple SPs SP SP on the other side and is in effect a horizontally and vertically scalable hub that may among other things bridge all of the connected entities. A MICV thus as one simple example may offer various routing formatting delivery value add etc. capabilities that provide possibly inter alia 

1 A WC WC WC and by extension all of the MSs MS MS MS MS MS MS that are serviced by the WC WC WC with ubiquitous access to a broad universe of SPs SP SP and

2 A SP SP SP with ubiquitous access to a broad universe of WCs WC WC and by extension to all of the MSs MS MS MS MS MS MS that are serviced by the WCs WC WC .

Generally speaking a MICV may have varying degrees of visibility e.g. access etc. to the MS MS MS SP etc. messaging traffic 

1 A WC may elect to route just their out of network messaging traffic to a MICV. Under this approach the MICV would have visibility e.g. access etc. to just the portion of the WC s messaging traffic that was directed to the MICV by the WC.

2 A WC may elect to route all of their messaging traffic to a MICV. The MICV may possibly among other things subsequently return to the WC that portion of the messaging traffic that belongs to i.e. that is destined for a MS of the WC. Under this approach the MICV would have visibility e.g. access etc. to all of the WC s messaging traffic.

While the discussion below will include a MICV it will be readily apparent to one of ordinary skill in the relevant art that numerous other arrangements are equally applicable and indeed are fully within the scope of the present invention.

As just one example of an alternative arrangement aspects of the present invention may be offered by a SP. A SP may for example be realized through any combination of possibly inter alia any one or more of 1 an element of a WC an element of a landline carrier an element of a MICV or multiple such elements working together 2 a 3P such as possibly inter alia a merchant a CP such as for example a news organization an advertising agency a brand etc. a financial institution etc. 3 multiple 3P entities working together 4 a service bureau 5 a message service provider and or 6 other entities.

While the discussion above referred to one specific alternative arrangement it will be readily apparent to one of ordinary skill in the relevant art that numerous other alternative arrangements including inter alia the use of multiple SPs the sharing blending etc. of functionality between a MICV and one or more SPs etc. are equally applicable and indeed are fully within the scope of the present invention.

For variety completeness etc. of exposition portions of the discussion below will include a MICV and a SP. As noted above it will be readily apparent to one of ordinary skill in the relevant art that numerous other arrangements are easily possible e.g. any combination of one or more of inter alia a single MICV multiple MICVs a single SP multiple SPs etc. .

In the discussion below reference is made to messages that may be sent for example between a MS and a SP. As set forth below a given message sent between a MS and a SP may actually comprise a series of steps in which the message is received forwarded and routed between different entities including possibly inter alia a MS a WC a MICV and a SP. Thus unless otherwise indicated it will be understood that reference to a particular message generally includes that particular message as conveyed at any stage between an origination source such as for example a MS and an end receiver such as for example a SP. As such reference to a particular message generally includes a series of related communications between for example a MS and a WC a WC and a MICV a MICV and a SP etc. The series of related communications may in general contain substantially the same information or information may be added or subtracted in different communications that nevertheless may be generally referred to as a same message. To aid in clarity a particular message whether undergoing changes or not is referred to by different reference numbers at different stages between a source and an endpoint of the message.

For purposes of illustration and reference numeral depict one possible logical implementation of aspects of a MICV under one particular arrangement interposed between WCs WC WC on one side and SP SP on the other side . The figure depicts among other things Gateways and that for example provide information data receipt and dispatch capabilities from to WCs SPs and possibly other entities across possibly inter alia different application level communication protocols Queues and that for example provide interim storage and buffering capabilities a Data Highway DH that for example provides interconnection capabilities and DPEs .

A dynamically updateable set of one or more Receivers Rx Rx in the diagram get messages from a MICV DH and deposit them on an intermediate or temporary Queue Q Q in the diagram for subsequent processing.

A dynamically updateable set of one or more Queues Q Q and Q Q in the diagram operate as intermediate or temporary buffers for incoming and outgoing messages.

A dynamically updateable set of one or more WorkFlows WorkFlow WorkFlow in the diagram remove incoming messages from an intermediate or temporary Queue Q Q in the diagram perform all of the required operations on the messages and deposit the processed messages on an intermediate or temporary Queue Q Q in the diagram . The WorkFlow component will be described more fully below.

A dynamically updateable set of one or more Transmitters Tx Tx in the diagram remove processed messages from an intermediate or temporary Queue Q Q in the diagram and put the messages on a MICV DH.

An Administrative Engine provides a linkage to all of the different components of a DPE so that a DPE along with all of the different components of a DPE may be fully and completely administered or managed .

Aspects of a MICV may plug into different layers levels etc. of legacy current and or future technology of inter alia WCs SPs etc. and among other things may for example facilitate interoperation between such technologies.

For example from a traditional messaging context an entity such as for example a WC a 3P such as a CP etc. may direct their Short Message Service Center SMSC complexes their Multimedia Message Service Center MMSC complexes etc. to connect to a single simple consolidated etc. interface mechanism that is exposed by a MICV and subsequently seamlessly exchange message traffic.

For example from a traditional wireless context an entity such as for a WC etc. may direct aspects of their infrastructure to connect to a single simple consolidated etc. interface mechanism that is exposed by a MICV and subsequently seamlessly exchange SS7 based and or IP based signaling data General Packet Radio Service GPRS Roaming Exchange GRX data location and presence data etc.

Central to the operation of a MICV is the unit of information within a MICV that is received manipulated or otherwise operated on dispatched etc. Unlike prior environments that might operate just on and thus potentially be limited just to an SMS message or a MMS message the unit of information within a MICV is a more general quanta of data. Accordingly a MICV is natively capable of operating on inter alia an SMS message a MMS message an IMS message an E Mail message a VoIP data stream a video data stream e.g. a movie a video conference call etc. a voice telephone call signaling and other command and control data an audio data stream e.g. a song etc. IM data games and other software applications pictures and other static images data from software applications such as games etc.

Within a MICV a flexible extensible and dynamically configurable IMO see for example and reference numeral and and reference numeral may be employed as an internal representation of aspects of a received quanta of data. An IMO and may logically contain possibly inter alia one or more headers and properties a body and etc. within which for example aspects of a received quanta of data may be preserved and . An IMO may physically be realized through any combination of possibly inter alia proprietary data structures Java Message Service JMS messages or objects flat files database entries in memory constructs etc.

For purposes of illustration within an SMS context a MICV may support the receipt and dispatch of information through possibly inter alia Short Message Peer to Peer SMPP via Transmission Control Protocol TCP IP and Mobile Application Part MAP via SS7. Under such a context 

1 and reference numeral depict an exemplary incoming SMS message received via for example SMPP with for example the data elements associated with the SMS message encapsulated within a SMPP Protocol Data Unit PDU encapsulated within a TCP Segment encapsulated within an IP Packet .

2 and reference numeral depict an exemplary incoming SMS message received via for example MAP with for example the data elements associated with the SMS message encapsulated within a MSU .

3 and reference numeral depict a hypothetical IMO that is possible in support of an SMS message received via for example SMPP and

4 and reference numeral depict a hypothetical IMO that is possible in support of an SMS message received via for example MAP.

The artifacts that are depicted by FIGS. are illustrative only and it will be readily apparent to one of ordinary skill in the art that among other things numerous alternative IMO arrangements in connection with for example different contexts such as inter alia MMS VoIP a voice call signaling data command and control data software application data etc. different communication protocols etc. are easily possible. For example information on the identity location capabilities etc. of an originating party and or a destination party may be captured preserved etc. in any number of ways.

As noted above a WorkFlow component see for example WorkFlow WorkFlow in may perform a range of processing operations on inter alia a message.

Among other things a WorkFlow component may leverage a comprehensive flexible scalable etc. address resolution facility to support possibly inter alia its routing operations. Such a facility may provide authoritative answers to inquiries like At this moment in time what carrier services the TN 1 703 555 1212 What entity services the SIP address sip john.doe bigcompany.com etc. Among other things such a facility may address 1 the complexities that are associated with all of the different TN numbering plans schemes etc. that exist around the world 2 the complexities that arise with worldwide Mobile Number Portability MNP regimes etc.

A depiction of an illustrative address resolution facility is presented in and reference numeral . Such a facility may consist of possibly inter alia 

A An Electronic Numbering ENUM fa ade through which possibly inter alia various elements of a WorkFlow component E E E E in may connect submit routing inquiries receive routing responses etc.

B A dynamically updateable set of one or more In Memory Databases In Memory Database In Memory Database in the diagram that optionally house or host selected data including possibly inter alia data from a Composite Routing Database CRD to provide as one example optimal performance.

C A Real Time Query Facility RTQF through which inquiries may be dispatched real time to authoritative bodies such as for example TN assignment administrators around the world. A RTQF may support multiple communication channels paradigms protocols etc. such as possibly inter alia SS7 TCP IP User Datagram Protocol UDP IP SMPP etc. .

D A CRD containing comprehensive routing information for possibly inter alia TNs within all of the different TN numbering plans schemes etc. that exist around the world. A CRD may receive updates e.g. dynamically on a scheduled basis etc. from any number of sources or feeds including possibly inter alia domestic such as for example from a Local Exchange Routing Guide LERG from one or more Number Portability Administration Centers NPACs etc. and international such as for example from Hong Kong from the United Kingdom etc. .

An address resolution facility as described above may support a wide range of address types including among others a TN such as 703 555 1234 a SC such as 46625 a SIP Uniform Resource Identifier URI such as sip mark mydomain.com a Tel URI such as tel 19257652333 a Uniform Resource Locator URL etc.

A WorkFlow component may be implemented or realized in any number of ways. For example and reference numeral depict aspects of a hypothetical implementation of a WorkFlow environment wherein possibly inter alia 

1 A dynamically adjustable number of threads Thread Thread Thread Thread may be inter alia created started allowed to operate or execute quiesced stopped destroyed etc. under control of for example the WorkFlow environment . Among other things one or more threads may for example realize aspects of one or more elements of a MICV such as for example routing operations protocol conversion operations message transmission operations etc. and or a single thread may for example realize aspects of one or more elements of a MICV such as for example routing operations protocol conversion operations message transmission operations etc. .

2 Different elements of a MICV such as for example routing operations protocol conversion operations message transmission operations etc. may communicate interact etc. with various of the threads Thread Thread see for example and .

3 Various of the threads Thread Thread may among themselves communicate interact etc. see for example .

4 Various of the threads Thread Thread may communicate interact etc. with inter alia a Shared Memory Region see for example .

To help illustrate the operation of aspects of the present invention and depict various of the exchanges that might take place during the delivery of an SMS message. As noted above 

1 While portions of the present discussion do for simplicity of exposition refer to messaging generally and certain types of messaging including inter alia SMS MMS etc. specifically it will be readily apparent to one of ordinary skill in the relevant art that application of aspects of the present invention to numerous other communication paradigms including inter alia a VoIP data stream software application e.g. game etc. data a SIP addressed artifact a video data stream e.g. a movie a video conference call etc. a voice telephone call an audio data stream e.g. a song etc. signaling and other command and control data etc. is easily possible and indeed is fully within the scope of the present invention.

2 For variety completeness etc. of exposition the discussion below will include a MICV and a SP. It will be readily apparent to one of ordinary skill in the relevant art that numerous other arrangements are easily possible e.g. any combination of one or more of inter alia a single MICV multiple MICVs a single SP multiple SPs etc. .

For simplicity capture various of the exchanges that might take place during the delivery of an SMS message from one MS i.e. MS to another MS i.e. MS . It will be understood that a reply by MS to the received SMS message will encompass an equivalent set of exchanges traveling from MS to MS .

In the exchanges that are captured under the designation Set represent various of the activities that might take place as a MS MS of WC WC dispatches an SMS message to another MS MS of WC WC.

As illustrated in the diagram the message travels from MS to WC see to a MICV see and on to a SP see .

In the exchanges that are captured under the designation Set represent various of the e.g. possibly WorkFlow based activities that might take place as SP completes inter alia a number of preparatory steps processing activities etc. including for example 

1 Resolving the destination address of the message using for example aspects of an address resolution facility such as depicted in .

2 Constructing and dispatching a SendRoutingInfo inquiry see comprising inter alia a Mobile Subscriber Integrated Services Digital Network Number MSISDN . Such an inquiry may take any number of forms including inter alia a MAP sendRoutingInfoForSM etc. may include any number of communication protocols including inter alia an IP national variants of SS7 such as an American National Standards Institute ANSI variant or an International Telecommunication Union ITU variant SS7 variants or extensions such as SIGTRAN etc. and may be sent using for example any number of interfaces including inter alia a TCP IP interface such as reference numeral in an SS7 interface reference such as reference numeral in etc. . It will be readily apparent to one of ordinary skill in the relevant art that other communication interfaces gateways such as for example reference numerals and in etc. are easily possible any of which may leverage among other things protocol converters software stacks etc.

3 Receiving a SendRoutingInfo response see comprising inter alia different values such as for example an IMSI value a MSC value etc. . Such a response may take any number of forms including inter alia a MAP sendRoutingInfoForSMResponse etc. may include any number of communication protocols including inter alia an IP national variants of SS7 such as an ANSI variant or an ITU variant SS7 variants or extensions such as SIGTRAN etc. and may be received using for example any number of interfaces including inter alia a TCP IP interface such as reference numeral in an SS7 interface reference such as reference numeral in etc. . It will be readily apparent to one of ordinary skill in the relevant art that other communication interfaces gateways such as for example reference numerals and in etc. are easily possible any of which may leverage among other things protocol converters software stacks etc.

Among other things a SP may extract elements such as for example an IMSI value a MSC value etc. from a received SendRoutingInfo response using for example a dynamic configurable mapping mechanism optionally complete any number of processing steps to inter alia augment transform etc. any extracted elements and inter alia preserve various pieces of information in a cache.

4 Possibly performing other lookup operations processing steps e.g. the creation population etc. of an IMO data manipulation actions etc.

In the exchanges that are captured under the designation Set represent various of the e.g. possibly WorkFlow based activities that might take place as SP completes inter alia various conveyance steps including for example 

1 Possibly performing various processing steps e.g. the leveraging of the contents of an IMO data manipulation actions etc.

2 Constructing and dispatching an SMS message. Such a message may take any number of forms including inter alia a SMPP PDU an SS7 based ForwardShortMessage etc. may include any number of pieces of information including inter alia an IMSI value a MSC value etc. may leverage any number of communication protocols including inter alia an IP national variants of SS7 such as an ANSI variant or an ITU variant SS7 variants or extensions such as SIGTRAN etc. and may be sent using for example any number of interfaces including inter alia a TCP IP interface such as reference numeral in an SS7 interface reference such as reference numeral in etc. . It will be readily apparent to one of ordinary skill in the relevant art that other communication interfaces gateways such as for example reference numerals and in etc. are easily possible any of which may leverage among other things protocol converters software stacks etc.

The Set exchanges that were described above may be augmented in any number of ways to include various message delivery error recovery retry etc. capabilities.

As noted above it will be understood that a reply by MS to the received SMS message will encompass an equivalent set of exchanges traveling from MS to MS.

In the exchanges that are captured under the designation Set represent various of the activities that might take place as MS dispatches another SMS message to MS.

As illustrated in the diagram the message travels from MS to WC see to a MICV see and on to a SP see .

In the exchanges that are captured under the designation Set represent various of the e.g. possibly WorkFlow based activities that might take place as SP completes inter alia a number of preparatory steps processing activities etc. see including for example 

1 Resolving the destination address of the message using for example aspects of an address resolution facility such as depicted in .

2 Retrieving one or more pieces of information such as inter alia an IMSI value a MSC value etc. from a cache. Note that this operation obviates the need for inter alia the SendRoutingInfo inquiry see in and response see in that were discussed above. 

3 Possibly performing other lookup operations processing steps e.g. the creation population etc. of an IMO data manipulation actions etc.

In the exchanges that are captured under the designation Set represent various of the e.g. possibly WorkFlow based activities that might take place as SP completes inter alia various conveyance steps including for example 

1 Possibly performing various processing steps e.g. the leveraging of the contents of an IMO data manipulation actions etc.

2 Constructing and dispatching an SMS message. Such a message may take any number of forms including inter alia a SMPP PDU an SS7 based ForwardShortMessage etc. may include any number of pieces of information including inter alia an IMSI value a MSC value etc. may leverage any number of communication protocols including inter alia an IP national variants of SS7 such as an ANSI variant or an ITU variant SS7 variants or extensions such as SIGTRAN etc. and may be sent using for example any number of interfaces including inter alia a TCP IP interface such as reference numeral in an SS7 interface reference such as reference numeral in etc. . It will be readily apparent to one of ordinary skill in the relevant art that other communication interfaces gateways such as for example reference numerals and in etc. are easily possible any of which may leverage among other things protocol converters software stacks etc.

The Set exchanges that were described above may be augmented in any number of ways to include various message delivery error recovery retry etc. capabilities. For example if an issued ForwardShortMessage is rejected then inter alia various of the Set activities may be invoked e.g. a SendRoutingInfo inquiry and response followed by a cache update and a new ForwardShortMessage may be issued.

As noted above it will be understood that a reply by MS to the received SMS message will encompass an equivalent set of exchanges traveling from MS to MS.

In the exchanges that are captured under the designation Set represent various of the activities that might take place as MS dispatches yet another SMS message to MS.

As illustrated in the diagram the message travels from MS to WC see to a MICV see and on to a SP see .

In the exchanges that are captured under the designation Set represent various of the e.g. possibly WorkFlow based activities that might take place as SP completes inter alia a number of preparatory steps processing activities etc. see including for example 

1 Resolving the destination address of the message using for example aspects of an address resolution facility such as depicted in .

2 Retrieving one or more pieces of information such as inter alia an IMSI value a MSC value etc. from a cache. As noted above in connection with this operation obviates the need for inter alia the SendRoutingInfo inquiry see in and response see in . 

3 Possibly performing other lookup operations processing steps e.g. the creation population etc. of an IMO data manipulation actions etc.

In the exchanges that are captured under the designation Set represent various of the e.g. possibly WorkFlow based activities that might take place as SP completes inter alia various conveyance steps including for example 

1 Possibly performing various processing steps e.g. the leveraging of the contents of an IMO data manipulation actions etc.

2 Constructing and dispatching multiple SMS messages necessitated by for example message body or content segmentation etc. . Each message may take any number of forms including inter alia a SMPP PDU an SS7 based ForwardShortMessage etc. may include any number of pieces of information including inter alia an IMSI value a MSC value etc. may leverage any number of communication protocols including inter alia an IP national variants of SS7 such as an ANSI variant or an ITU variant SS7 variants or extensions such as SIGTRAN etc. and may be sent using for example any number of interfaces including inter alia a TCP IP interface such as reference numeral in an SS7 interface reference such as reference numeral in etc. . It will be readily apparent to one of ordinary skill in the relevant art that other communication interfaces gateways such as for example reference numerals and in etc. are easily possible any of which may leverage among other things protocol converters software stacks etc.

The Set exchanges that were described above may be augmented in any number of ways to include various message delivery error recovery retry etc. capabilities. For example if an issued ForwardShortMessage is rejected then inter alia various of the Set activities may be invoked e.g. a SendRoutingInfo inquiry and response followed by a cache update and a new ForwardShortMessage may be issued.

As noted above it will be understood that a reply by MS to any of the received SMS messages will encompass an equivalent set of exchanges traveling from MS to MS.

The Set Set exchanges that were described above are illustrative only and it will be readily apparent to one of ordinary skill in the relevant art that numerous other exchanges exchange sequences activities etc. are easily possible and indeed are fully within the scope of the present invention. For example and inter alia 

1 Various of the depicted exchanges may be repeated any number of times as possibly inter alia the MSs i.e. MS and MS carry on for example a message based conversation.

2 A cache as described above may be implemented through any number of means including inter alia memory e.g. raw and or structured disk or other storage medium e.g. raw and or structured etc. and may leverage among other things conventional Relational Database Management Systems RDBMSs Object Database Management Systems ODBMSs in memory Database Management Systems DBMSs or any other equivalent facilities. Caches are shown diagrammatically in . A single instance of a cache may be implemented or two or more instances as depicted may be deployed. One instance could be used as a backup of another instance. As shown cache may be integrated with a main memory and or with a secondary memory which are described more fully in connection with .

3 Access to a cache as described above may encompass an Application Programming Interface API direct memory read and write operations wrapper functions etc. any of which may employ inter alia security control etc. mechanisms.

4 Retrieval of information from a cache as describe above may encompass any combination of one or more of iteration through the contents of the cache hash functions algorithmic search capabilities etc.

5 An entry in a cache as described above may contain a range of values including inter alia identifying values such as for example a MSISDN an IMSI value a MSC value etc. timestamps location information such as for example information on the current physical location of a MS WD an indicator e.g. extracted derived etc. from a response received during a preparatory step as to whether the MS WD is on its home network or if it is roaming etc. counters e.g. tracking access to or usage of an entry etc.

6 Management of a cache as described above may encompass among other things garbage collection e.g. periodic sweeps through the contents of the cache to recover entries space etc. aging of the contents of the cache e.g. removing refreshing altering etc. various entries of the cache based on different criteria such as for example date time usage frequency etc. periodic integrity checks etc. Among other things if a cache entry identifies a MS WD as roaming then that cache entry s management particulars including inter alia expiration time refresh rate etc. may be appropriately modified.

7 A cache as described above may be initially periodically etc. seeded with certain predefined dynamically constructed etc. real sentinel etc. entries.

During various of the processing steps that were described above one or more billing transactions may optionally be completed e.g. for various of the processing steps that are performed for each response returned etc. A billing transaction may take any number of forms and may involve different external entities e.g. a WC s billing system a carrier billing system service bureau a credit or debit card clearinghouse etc. . A billing transaction may include possibly inter alia 

1 The appearance of a line item charge on the bill or statement that for example an entity may receive from their WC. Exemplary mechanics and logistics associated with this approach are described in for example U.S. Pat. No. 7 640 211 entitled SYSTEM AND METHOD FOR BILLING AUGMENTATION and its associated continuations. Other ways of completing or performing line item billing are easily implemented by those skilled in the art.

Various of the messages that were described above may optionally contain an informational element e.g. a relevant or applicable factoid etc. The informational element may be selected statically e.g. all generated messages are injected with the same informational text randomly e.g. a generated message is injected with informational text that is randomly selected from a pool of available informational text or location based i.e. a generated message is injected with informational text that is selected from a pool of available informational text based on the current physical location of the recipient of the message as derived from as one example a Location Based Service LBS facility .

Various of the messages that were described above may optionally contain advertising e.g. textual material if a simple paradigm such as SMS is being utilized or multimedia images of brand logos sound video snippets etc. material if a more capable paradigm such as MMS is being utilized. The advertising material may be selected statically e.g. all generated messages are injected with the same advertising material randomly e.g. a generated message is injected with advertising material that is randomly selected from a pool of available material or location based i.e. a generated message is injected with advertising material that is selected from a pool of available material based on the current physical location of the recipient of the message as derived from as one example a LBS facility .

Various of the messages that were described above may optionally contain promotional materials e.g. still images video clips etc. .

The discussion that was presented above included TNs. However it is to be understood that it would be readily apparent to one of ordinary skill in the relevant art that numerous other addresses or identifiers such as possibly inter alia SCs IP addresses E Mail addresses IM handles SIP addresses etc. are easily possible and indeed are fully within the scope of the present invention.

The discussion that was presented above referenced messaging generally and two specific messaging paradigms SMS and MMS specifically. However as was noted previously it will be readily apparent to one of ordinary skill in the relevant art that application of aspects of the present invention to numerous other communication paradigms including inter alia a VoIP data stream software application e.g. game etc. data a SIP addressed artifact a video data stream e.g. a movie a video conference call etc. a voice telephone call an audio data stream e.g. a song etc. signaling and other command and control data etc. is easily possible and indeed is fully within the scope of the present invention.

For purposes of illustration aspects of the discussion that was presented above employed a specific vehicle consisting of a SendRoutingInfo inquiry and a SendRoutingInfo response but it will be readily apparent to one of ordinary skill in the relevant art that aspects of the present invention are easily generalized to any data delivery paradigm that employs inter alia 1 one or more preparatory steps and 2 a one or more conveyance steps.

Various aspects of the present invention can be implemented by software firmware hardware or any combination thereof. illustrates an example computer system in which the present invention or portions thereof such as described above under paragraphs 00031 00139 can be implemented as computer readable code. Various embodiments of the invention are described in terms of this example computer system . After reading this description it will become apparent to a person skilled in the relevant art how to implement the invention using other computer systems and or computer architectures. Computer system may be a server or other electronic device or appliance configured to operate in accordance with the functionality described herein.

Computer system includes one or more processors such as processor . Processor can be a special purpose processor or a general purpose processor. Processor is connected to a communication infrastructure for example a bus or a network .

Computer system also includes a main memory preferably Random Access Memory RAM containing possibly inter alia computer software and or data .

Computer system may also include a secondary memory . Secondary memory may include for example a hard disk drive a removable storage drive a memory stick etc. A removable storage drive may comprise a floppy disk drive a magnetic tape drive an optical disk drive a flash memory or the like. A removable storage drive reads from and or writes to a removable storage unit in a well known manner. A removable storage unit may comprise a floppy disk magnetic tape optical disk etc. which is read by and written to by removable storage drive . As will be appreciated by persons skilled in the relevant art s removable storage unit includes a computer usable storage medium having stored therein possibly inter alia computer software and or data .

In alternative implementations secondary memory may include other similar means for allowing computer programs or other instructions to be loaded into computer system . Such means may include for example a removable storage unit and an interface . Examples of such means may include a program cartridge and cartridge interface such as that found in video game devices a removable memory chip such as an Erasable Programmable Read Only Memory EPROM or Programmable Read Only Memory PROM and associated socket and other removable storage units and interfaces which allow software and data to be transferred from the removable storage unit to computer system .

Computer system may also include an input interface and a range of input devices such as possibly inter alia a keyboard a mouse etc.

Computer system may also include an output interface and a range of output devices such as possibly inter alia a display one or more speakers etc.

Computer system may also include a communications interface . Communications interface allows software and or data to be transferred between computer system and external devices. Communications interface may include a modem a network interface such as an Ethernet card a communications port a Personal Computer Memory Card International Association PCMCIA slot and card or the like. Software and or data transferred via communications interface are in the form of signals which may be electronic electromagnetic optical or other signals capable of being received by communications interface . These signals are provided to communications interface via a communications path . Communications path carries signals and may be implemented using wire or cable fiber optics a phone line a cellular phone link a Radio Frequency RF link or other communications channels.

As used in this document the terms computer program medium computer usable medium and computer readable medium generally refer to media such as removable storage unit removable storage unit and a hard disk installed in hard disk drive . Signals carried over communications path can also embody the logic described herein. Computer program medium and computer usable medium can also refer to memories such as main memory and secondary memory which can be memory semiconductors e.g. Dynamic Random Access Memory DRAM elements etc. . These computer program products are means for providing software to computer system .

Computer programs also called computer control logic are stored in main memory and or secondary memory . Computer programs may also be received via communications interface . Such computer programs when executed enable computer system to implement the present invention as discussed herein. In particular the computer programs when executed enable processor to implement the processes of aspects of the present invention such as the steps discussed above under paragraphs 00031 00139. Accordingly such computer programs represent controllers of the computer system . Where the invention is implemented using software the software may be stored in a computer program product and loaded into computer system using removable storage drive interface hard drive or communications interface .

The invention is also directed to computer program products comprising software stored on any computer useable medium. Such software when executed in one or more data processing devices causes data processing device s to operate as described herein. Embodiments of the invention employ any computer useable or readable medium known now or in the future. Examples of computer useable mediums include but are not limited to primary storage devices e.g. any type of random access memory secondary storage devices e.g. hard drives floppy disks Compact Disc Read Only Memory CD ROM disks Zip disks tapes magnetic storage devices optical storage devices Microelectromechanical Systems MEMS nanotechnological storage device etc. and communication mediums e.g. wired and wireless communications networks local area networks wide area networks intranets etc. .

It is important to note that the hypothetical examples that were presented above which were described in the narrative and which were illustrated in the accompanying figures are exemplary only. They are not intended to be exhaustive or to limit the invention to the specific forms disclosed. It will be readily apparent to one of ordinary skill in the relevant art that numerous alternatives to the presented examples are easily possible and indeed are fully within the scope of the present invention.

