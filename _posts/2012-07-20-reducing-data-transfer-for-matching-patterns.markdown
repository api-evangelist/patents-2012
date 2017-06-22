---

title: Reducing data transfer for matching patterns
abstract: A device may receive a packet, obtain data from the packet, store the data in a memory, and send a request to match a portion of the data to a set of patterns, the request identifying the portion in the memory. In addition, the device may access the portion in the memory based on the request, compare the accessed portion to the set of patterns, generate a result by comparing the accessed portion to the set of patterns, and output the result.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08521701&OS=08521701&RS=08521701
owner: Juniper Networks, Inc.
number: 08521701
owner_city: Sunnyvale
owner_country: US
publication_date: 20120720
---
This application is a continuation of co pending U.S. patent application Ser. No. 12 194 712 filed on Aug. 20 2008 the disclosure of which is hereby incorporated by reference herein.

When a network device receives a packet the network device typically examines one or more portions of the packet e.g. header payload etc. to ensure that the packet does not pose a security threat. In examining the portions the network device matches the portions against known patterns e.g. a virus pattern a software vulnerability pattern etc. based on a user configured policy. If the portions contain one of the patterns the device extracts a flow signature e.g. a tuple including a source address a destination address a source port number a destination port number a protocol name etc. from the packet. Henceforth the device may drop packets that bear the same flow signature and or sample the packets for further analysis.

According to one aspect a method may include receiving a packet obtaining data from the packet storing the data in a memory sending a request to match a portion of the data to a set of patterns the request identifying the portion in the memory accessing the portion in the memory based on the request comparing the accessed portion to the set of patterns generating a result by comparing the accessed portion to the set of patterns and outputting the result.

According to another aspect a device may include a shared memory a patterns memory to store a set of patterns a client and a server. The client may be configured to receive a packet extract data from the packet store the data in the shared memory output a first request for matching a first portion of the data to the set of patterns in the patterns memory and output a second request for matching a second portion of the data to the set of patterns in the patterns memory. The server may be configured to access the first portion from the shared memory based on the first request match the first portion to the set of patterns in the patterns memory to obtain a first result access the second portion from the shared memory based on the second request match the second portion to the set of patterns in the patterns memory to obtain the second result and send the first result and the second result to the client.

According to yet another aspect a device may include means for loading a set of patterns for a pattern matching service into a first memory means for receiving a packet means for storing data from the packet in a second memory means for receiving requests for matching patterns each of the requests identifying a location of a corresponding portion of the data in the second memory and asking for the corresponding portion to be matched to the set of patterns in the first memory and means for providing to the client for each of the requests a result of matching the corresponding portion to the set of patterns.

The following detailed description refers to the accompanying drawings. The same reference numbers in different drawings may identify the same or similar elements. The term packet as used herein may refer to a packet a datagram or a cell a fragment of a packet a datagram or a cell or other types of data. As used herein a request may include a message. Depending on context the term pattern match request or request as used herein may refer to a message requesting a component or a device to provide a list of patterns that match data.

As described below a device may reduce transfer of data within the device for matching patterns. is a block diagram of a data portion of an exemplary packet. Data portion may include any part or all of the packet. As shown in portion may include portion and portion . Each of portions and may include a common portion .

As further shown in to match portions and to the specified set of patterns PMC may send requests and to PME . Although shows requests and as including portions and respectively requests and may include additional information data than that depicted in . In because each of portions and includes common portion common portion may be sent twice once in request and once in request .

In the implementation illustrated in request may instruct PME to match portion in portion of the exemplar packet to the specified patterns. Similarly request may instruct PME to match portion within portion to the known patterns.

In the above PME in may produce the same result in response to requests and as PME in to requests and . However in the device may transfer common portion once e.g. copy portion to shared memory whereas in the device may transfer common portion twice e.g. in requests and .

By reducing the transfer of data within the device the device may reduce average bandwidth use of internal communication data paths and or may save processing cycles per pattern match request. Such reduction in resource utilization may enable the device to avoid performance degradations and or process additional packets in a high traffic environment.

As shown in network may include devices through N individually referred to herein as a device . Device may include for example a router a switch a gateway a server a personal computer etc. Although device may be implemented as any network device in the following description device will be described in terms of a router or a switch.

Controller may include one or more components for managing routes and or types of information that may require centralized processing. For example controller may manage routes e.g. may accept or disseminate routes to other devices in accordance with routing signaling protocols may receive and process statistics related to packets and or may process packet samples from other components of device e.g. from line interfaces .

Line interface may include one or more components for receiving packets from devices in network and for transmitting the packets to other devices in network . In addition line interface may forward packets classify packets redirect packets to other components in device manage a table of packet statistics and or sample packets.

Service module may include one or more components for rendering a particular service for a received packet. In processing the packet service module may select one or more portions of the packet and perform a pattern match to detect one or more attacks e.g. a virus . After processing the packet service module may drop the packet or direct the packet to another of service modules or one of line interfaces . Examples of service module may include an anti virus service module a firewall service module an intrusion detection service module an encryption decryption service module a data loss prevention module e.g. an information leak prevention module an extrusion prevention system etc. and or other types of service modules.

Switch fabric may include one or more switches for conveying packets from one of line interfaces and or service modules to another of line interfaces and or service modules .

Processor may include a processor a microprocessor an Application Specific Integrated Circuit ASIC a Field Programmable Gate Array FPGA and or other processing logic capable of controlling component . In some implementations processor may include hardware such as a co processor for matching data to patterns.

Memory may include content addressable memory CAM static memory such as read only memory ROM and or dynamic memory such as random access memory RAM or onboard cache for storing data e.g. patterns and machine readable instructions. Memory may also include storage devices such as a hard disk a flash memory as well as other types of storage devices. Depending on the implementation portions of memory may be directly addressable by processor or components in processor e.g. a co processor for matching patterns to data .

Communication interface may include any transceiver like mechanism that enables device to communicate with other components and or devices. Communication data path may provide an interface through which components of component and or device can communicate with one another.

PMC may include a hardware and or software component that may be associated with sending pattern match requests to PMS receiving a result of matching patterns from PMS and processing the result. In one implementation PMC may perform these functions by providing support for procedures e.g. threads programs subroutines methods scripts etc. that may be invoked via a set of pattern match application programming interfaces APIs .

As shown pattern match APIs may include REGISTER UNREGISTER INITIALIZE SHUTDOWN LOAD PATTERNS UNLOAD PATTERNS CREATE MATCH CONTEXT DESTROY MATCH CONTEXT REQUEST MATCH and STOP SESSION . In for each API an argument list may be presented as denoted by e.g. an argument list of INITIALIZE is shown by .

REGISTER may include an interface for invoking a procedure e.g. a method a function a subroutine a thread a script a program etc. for PMC to identify itself to PMS . In addition PMC may receive in response to calling REGISTER one of more identifiers that are associated with registration of PMC from PMS . When PMC invokes REGISTER PMS may allocate system resources e.g. locks memory etc. for PMC .

UNREGISTER may include an interface for invoking a procedure for deallocating system resources that may have been allocated by PMS via an invocation of REGISTER . INITIALIZE may include an interface for invoking a procedure for allocating system resources and or setting values for parameters e.g. a maximum number of requests that may wait in a queue before PMS relays one or more of the requests to PME that are related to processing pattern match requests at PMS .

SHUTDOWN may include an interface for invoking a procedure for deallocating system resources e.g. memory that may have been allocated via INITIALIZE . In some implementations when PMC calls SHUTDOWN PMS or PME may finish processing pending requests from PMC before PMS deallocates the resources. In a different implementation PMC may cancel the pending requests.

LOAD PATTERNS may include an interface for invoking a procedure for causing PME to transfer a set of patterns from a pattern database to a dynamic memory e.g. RAM . Once loaded in the dynamic memory PME may match data to the set of patterns. UNLOAD PATTERNS may include an interface for invoking a procedure for causing PME to remove a set of patterns that are loaded in a dynamic memory.

CREATE MATCH CONTEXT may include an interface for invoking a procedure for creating a context e.g. a block of memory for storing information related to a series of pattern match requests . The context may be used in issuing a series of related pattern match requests. For example if PMC issues two pattern match requests e.g. requests and in to PMS the same context may be used to issue both requests.

The context may include for example a session identifier that may be assigned to the pattern match requests an identifier associated with PMC and or any other bookkeeping information. In one implementation the bookkeeping information may indicate what part of a packet already has been matched to patterns and such information may be used as a seed to continue to match data in subsequent packets.

DESTROY MATCH CONTEXT may include an interface for invoking a procedure for deallocating a context e.g. returning the context to a heap that has been created via CREATE MATCH CONTEXT .

REQUEST MATCH may include an interface for invoking a procedure for requesting PME to perform a pattern match. In invoking REQUEST MATCH PMC may pass in its argument list parameters such as for example a context e.g. created by invoking CREATE MATCH CONTEXT an identifier associated with PMC an address of memory at which data to be matched is stored a set of patterns to match etc. When PMC invokes REQUEST MATCH PMS may temporarily place the pattern match request on a queue before relaying the request to PME .

STOP SESSION may include an interface for invoking a procedure for requesting PMS to deallocate system resources that are associated with a pattern matching session. As used herein pattern matching session or session may refer to a series of pattern match requests and responses that are interrelated by state information e.g. what portions of data have been matched against sets of patterns . and or common data. When a pattern match session starts data that may be referred by pattern match requests during the session may be temporarily stored in PME . When the pattern match session terminates the data may be removed from PME .

When PMC invokes one of the interfaces listed in PMC may pass information to PMS via an argument list of the interface. The information may include different parameters. For illustrative purposes two lists of parameters are described below.

NAME may include the name of PMC that invokes REGISTER e.g. Intrusion Detection and Prevention System . WEIGHT may include a numerical value that PMS may use in load balancing pattern match requests from two or more PMCs . COOKIE may include data that reflects states of pattern matching sessions e.g. what portion of data has been used for a pattern match in the prior pattern match request . RESULT HANDLER may include a reference and or address of a procedure that PMS may invoke when PMS obtains a result of a pattern match. EVENT HANDLER may include a reference and or address of a procedure that PMS may invoke when PMS generates an event e.g. occurrence of an error while PMS performs a task related to matching patterns.

DATABASE UNLOAD THRESHOLD may indicate a number of pattern databases e.g. a set of patterns to which data may be compared that PME may retain in dynamic memory e.g. RAM for matching patterns. If PMC requests PME to store more than DATABASE UNLOAD THRESHOLD pattern databases in its dynamic memory PME may swap out the oldest database or the least used database in the dynamic memory. MAX MATCH REQUSTS may indicate the maximum number of pattern match requests that may be placed in a waiting queue at PMS . The queue will be described below in greater detail. MAX MATCH RESULTS may indicate the maximum number of pattern matching results that PMS may provide to PMC in response to a pattern match request.

HIGH MATCH REQUEST THRESHOLD may indicate a threshold that indicates when the waiting queue is nearly full. LOW MATCH REQUEST THRESHOLD may indicate a value below which PMS may generate an event e.g. for notifying PMC after HIGH MATCH REQUEST THRESHOLD has been reached. TIMEOUT may indicate an amount of time for which a pattern match request may be placed in the waiting queue before PMS generates an event to notify PMC that the pattern match request has timed out.

Returning to PMS may include hardware and or software components for queuing pattern match requests from PMC relaying the pattern match requests to PME receiving responses to the pattern match requests from PME and distributing the responses to PMC . Further details of PMS are provided below.

PME may receive pattern match requests that are relayed by PMS from PMC and may provide results of matching patterns to PMS which may relay the results to PMC . In addition to responding to pattern match requests PME may respond to control commands from PMC programs and or scripts that are external to PMC etc.

In one implementation PME may accept at least two types of pattern match requests. One type of pattern match requests may be independent of other pattern match requests and therefore may be described as being stateless. Another type of pattern match requests may depend on information data provided by other pattern match requests and therefore may be described as being stateful. In a pattern matching session PME may receive a set of inter dependent stateful pattern match requests via PMS from PMC .

When PME receives a stateful pattern match request during a pattern matching session PME may temporarily save information that is provided by with the request. For example assume that PME receives a request to match a portion of data e.g. a character string John within John Doe to a known set of patterns. After or while processing the data PME may temporarily store state information e.g. what portion of the data has been matched . When PME receives another pattern match request that references a different portion of the data e.g. Doe in John Doe PME may use the state information to perform another pattern match. In one implementation the state information may be stored in a cookie that may be passed between PMC and PMS .

In order to perform pattern matching PME may store patterns in a memory that is local to PME or in a memory that is shared by PME and other components such as PMC and PMS .

Pattern database may include one or more sets of patterns. The set of patterns in pattern database may be used to detect patterns in data. For example assume that pattern database includes the pattern 10111000101111110000. Presence of the pattern in data e.g. 000011111010111000101111110000000000 may indicate that the data carries a computer virus.

To compare data against a set of patterns in pattern database PMC may request via PMS PME to load the set of patterns from pattern database in a dynamic memory. In one implementation PMC may invoke LOAD PATTERNS to cause via PMS PME to load in the set of patterns.

PME driver may include one or more components that may allow PMS to interact with PME . For example PME driver may relay a pattern match request from PMS to PME . In some implementations PME driver may control PME via communication data paths to which specialized hardware components of PME are connected.

Send thread may include one or more components for removing pattern match requests from queues and sending the removed pattern match requests to PME . In removing the pattern match requests from queues send thread may balance loads on queues in accordance with a specific policy or strategy. For example send thread may remove requests from queues such that each queue contains approximately an equal number of pattern match requests. To send the pattern match requests to PME send thread may interact with PME driver .

PMS queue may provide a buffer for receiving from PME results of processing pattern match requests. When PME driver relays a result of processing a pattern match request from PME PME driver may temporarily place the result in PMS queue . Each result may identify patterns that match data. Without PMS queue if a PMC that requested the pattern match is unable to receive the result PMS may drop the result or wait for PMC to finish its current task and receive the result.

PMS thread may include software for transferring results of matching patterns from PMS queue to PMCs that sent corresponding pattern matching requests.

Queue may receive and or buffer a pattern match request from a corresponding PMC illustrated as PMC in . The pattern match request may wait in queue until send thread delivers the pattern match request to PME via PME driver .

Control service module may include one or more components for configuring PMS e.g. initializing values of parameters loading sets of patterns from pattern database . For example when PMC invokes interfaces REGISTER UNREGISTER INITIALIZE SHUTDOWN LOAD PATTERNS UNLOAD PATTERNS CREATE MATCH CONTEXT and or DESTROY MATCH CONTEXT control service module may perform procedures that are associated with each of the interfaces. For instance as described above when PMC invokes REGISTER PMS may allocate system resources for PMC via control service module .

In some implementations if control service module allocates a block of memory for configuring PMS the block may be allocated in a dynamic memory that is shared between PMC and PME . When control service module allocates the block in a shared memory a reference e.g. an address a pointer etc. to the block may be provided to PMC .

For the following description assume that after service module powers up PMS allocates system resources e.g. locks memory semaphores etc. instantiates objects e.g. PMS queue and or starts threads e.g. send thread PMS thread etc. .

Process may start at block where PMS may be configured to provide a pattern matching service to a PMC block . Depending on the implementation PMS may be configured in different ways. For example in one implementation PMS may be configured when PMC invokes REGISTER and or INITIALIZE . In another implementation PMS may obtain information that is stored in a persistent storage e.g. a hard disk and use the information to configure PMS e.g. allocate system resources create objects etc. .

Patterns may be loaded block . For example PMC may invoke LOAD PATTERNS . In response PMS may cause via PME driver PME to read one or more sets of patterns from pattern database into memory . PMS may associate the loaded sets of patterns with PMC .

Data may be obtained for matching patterns block . In one implementation service module may select a portion of a received packet as data that may be matched against the loaded patterns.

A pattern matching session may be started block . In one implementation PMC may start a pattern matching session by invoking CREATE MATCH CONTEXT or REQUEST MATCH . In response to the invocation PME may maintain state information that is associated with a pattern matching session e.g. what portion of data that is in a shared memory has been matched to the loaded patterns .

A pattern match may be requested block . To request a pattern match PMC may copy the data see the above description of block to a shared memory location. In addition PMC may request PME to provide a list of patterns that match the data for example by invoking REQUEST MATCH . The request may indicate what portion of the data in the shared memory is to be matched to the loaded patterns.

A response to pattern match request may be obtained from PME block . Upon receiving pattern match request PME may generate a response e.g. a list of zero or more patterns that match the data in shared memory . In addition PME may send the response to PMS which may temporarily place the response in PMS queue . Subsequently PMS thread may send the response to PMC .

In a different implementation when PMS queue receives the response PMS thread may invoke a result handler that has been provided by PMC . When PMC receives a notification from the result handler that a response has been received PMC may process the response e.g. cause device to drop packets that bear the same source IP address and port number as the packet whose data matches the patterns send the data to another module for further analysis etc. .

The pattern matching session may be terminated block . For example when PMC has no additional pattern match requests for the data in shared memory PMC may terminate the session by invoking STOP SESSION . In some implementations terminating the pattern matching session may not prevent pending results from arriving at PMS from PME . Once the results have been received at PMS and notifications have been sent to PMC PMC may determine how or whether to use the results.

Patterns may be unloaded block . For example PMC may unload a set of patterns from PME e.g. remove the set of patterns from a dynamic memory by invoking UNLOAD PATTERNS . The set of patterns may have been loaded at block . Unloading the set of patterns may render the patterns unavailable for matching patterns.

In some instances the set of patterns may be unloaded when PMC requests PME to load in a new set of patterns and PME does not have sufficient memory to load the new set of patterns. In such an instance PME may bump off one of loaded sets of patterns based on the age of the loaded set e.g. the oldest set of patterns is bumped and or based on use e.g. the least often accessed set of patterns is bumped . In other instances the set of patterns may be automatically unloaded when PMC PME and or service module shuts down.

System resources that are associated with PMC may be deallocated block . When PMC no longer requires pattern matching services e.g. service module and or PMC shuts down PMC may invoke procedures such as SHUTDOWN and UNREGISTER deallocating the system resources.

Assume that device includes a service module and that service module includes Intrusion Detection System IDS module and Anti virus AV module as shown in . In addition assume that PMS includes at least two queues PMS queue and queue . Further assume that device is processing packets in network .

Each of IDS module and AV module invokes REGISTER INITIALIZE and LOAD PATTERNS . PMS allocates system resources sets parameter values and causes PME to load a set of patterns for IDS module and another set of patterns for AV module .

When a packet arrives at device device sends the packet to IDS module . IDS module extracts a portion of the packet and copies the portion into a shared memory . As shown in IDS module dispatches pattern match requests and by invoking REQUEST MATCH . Consequently PMS may place pattern match requests and in queue .

When IDS module receives the notifications IDS module requests PMS to send results and . IDS module receives and processes results and from PMS . illustrates PMS sending results and . PMS queue is empty after results and are sent to IDS module .

In the above example by reducing transfer of data within device e.g. copying the data to a shared memory once for a pattern matching session the device may reduce average bandwidth use of internal communication data paths and or may save processing cycles per pattern match request. Such reduction in resource utilization may enable device to avoid performance degradations and or process additional packets in a high traffic environment.

The foregoing description of implementations provides illustration but is not intended to be exhaustive or to limit the implementations to the precise form disclosed. Modifications and variations are possible in light of the above teachings or may be acquired from practice of the teachings.

For example pattern match APIs may be implemented differently from those illustrated in For example in one implementation invoking an API may explicitly identify the start of a packet via a packet identifier causing PME to store the packet in its memory. Subsequently one or more pattern match requests that follow the API invocation may refer to the packet via the same packet identifier. The packet may be removed from the memory when an end of packet API is invoked. In another implementation a pattern match request carrying a packet identifier that is different from a prior packet identifier in an earlier pattern match request may cause PME to remove a packet identified by the earlier packet identifier from PME s memory. In yet another implementation a single API call may result in multiple pattern match requests to PME .

In another example while series of blocks have been described with regard to exemplary processes illustrated in the order of the blocks may be modified in other implementations. In addition non dependent blocks may represent acts that can be performed in parallel to other blocks.

It will be apparent that aspects described herein may be implemented in many different forms of software firmware and hardware in the implementations illustrated in the figures. The actual software code or specialized control hardware used to implement aspects does not limit the invention. Thus the operation and behavior of the aspects were described without reference to the specific software code it being understood that software and control hardware can be designed to implement the aspects based on the description herein.

Even though particular combinations of features are recited in the claims and or disclosed in the specification these combinations are not intended to limit the invention. In fact many of these features may be combined in ways not specifically recited in the claims and or disclosed in the specification.

No element act or instruction used in the present application should be construed as critical or essential to the implementations described herein unless explicitly described as such. Also as used herein the article a is intended to include one or more items. Where one item is intended the term one or similar language is used. Further the phrase based on is intended to mean based at least in part on unless explicitly stated otherwise.

