---

title: System and method for dynamic throttling during bulk message delivery
abstract: An flexible, extensible, and dynamically configurable intelligent throttling capability that among other things can support the bulk processing of a wide range of information (including inter alia Short Message Service, Multimedia Message Service, IP Multimedia Subsystem, etc. messages; E-Mail messages; Instant Messaging communications; Session Initiation Protocol-addressed artifacts; signaling, command-and-control, application, etc. data; etc.) that may result following for example service interruptions, system outages, bursts of traffic (for example in response to a tele-voting initiative, from a mass broadcast of alert or information messages in response to a news item or an emergency situation, etc.), equipment failures, etc.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08751593&OS=08751593&RS=08751593
owner: Sybase 365, Inc.
number: 08751593
owner_city: Reston
owner_country: US
publication_date: 20120328
---
This patent application claims the benefit of U.S. Provisional Patent Application Ser. No. 61 469 296 filed on 30 Mar. 2011 which is herein incorporated by reference in its entirety.

The present invention relates generally to telecommunications services. More particularly the present invention relates to capabilities that enhance substantially the value and usefulness of various communication paradigms including inter alia Short Message Service SMS Multimedia Message Service MMS Unstructured Supplementary Service Data USSD Internet Protocol IP Multimedia Subsystem IMS Wireless Application Protocol WAP Session Initiation Protocol SIP addressed communications Electronic Mail E Mail Instant Messaging IM etc.

As the wireless revolution continues to march forward through various flavors of 2G 3G 4G and beyond the importance to a Mobile Subscriber MS for example a user of a Wireless Device WD that is serviced by possibly inter alia a Wireless Carrier WC of their WD grows substantially. Examples of WDs include inter alia mobile telephones handheld computers Internet enabled phones pagers radios TVs audio devices car audio navigation etc. systems recorders text to speech devices bar code scanners net appliances mini browsers Personal Data Assistants PDAs etc.

One consequence of such a growing importance is the resulting ubiquitous nature of WDs i.e. MSs have them available at almost all times and use them for an ever increasing range of activities. For example MSs employ their WDs to possibly inter alia 

1 Exchange e.g. SMS MMS etc. messages content such as inter alia pictures and other static images songs and other quanta of audio data movies streaming video and other quanta of video data data from software applications such as games etc. with other MSs e.g. Let s meet for dinner at 6 etc. through Peer to Peer or P2P messaging.

2 Secure information such as for example weather updates travel alerts news updates sports scores stock updates etc. participate in voting initiatives such as for example with the television show American Idol exchange content such as for example pictures and other static images songs and other quanta of audio data movies streaming video and other quanta of video data games and other software applications etc. interact with social networking sites etc. through various of the available Application to Peer or A2P based service offerings.

3 Engage in Mobile Commerce which broadly speaking encompasses the buying and selling of products goods services etc. through a WD and Mobile Banking which broadly speaking encompasses performing various banking activities through a WD .

The ubiquitous nature of WDs has among other things resulted in very high volumes of data traffic. As just one example around the world during 2009 there were over five trillion SMS messages exchanged and in North America during just the first half of 2010 over one trillion SMS messages were exchanged.

Under normal circumstances all of the traffic flows through the mobile ecosystem without issue. However perturbations do arise. For example service interruptions system outages bursts of traffic for example in response to a tele voting initiative from a mass broadcast of alert or information messages in response to a news item or an emergency situation etc. equipment failures etc. can all result in a pool of traffic including inter alia SMS MMS IMS etc. messages SIP addressed artifacts application data WAP based exchanges E Mail messages signaling command and control application etc. data IM messages etc. that needs to be bulk processed.

It would be desirable to have a way of efficiently managing such a pool of traffic including inter alia a way of dynamically throttling the sending of the traffic in the pool so as to among other things maximize a WD user s experience.

Aspects of the present invention fill the lacuna that was noted above by 1 providing within inter alia a Messaging Inter Carrier Vendor MICV an intelligent dynamic throttling capability that can accommodate a wide range of information including inter alia SMS MMS IMS etc. messages SIP addressed artifacts application data WAP based exchanges E Mail messages signaling command and control application etc. data IM messages etc. while 2 addressing in new and innovatory ways various of the not insubstantial challenges that are associated with same.

In one embodiment of the present invention there is provided a server based method for dynamic message throttling that can possibly among other things 1 identify a message pool to be processed where the message pool comprises a plurality of messages 2 partition the message pool into a plurality of subdivisions and 3 while a delivery window is open perform a plurality of processing steps including a opening a subdivision for processing yielding an open subdivision b selecting a message from the open subdivision yielding a selected message c performing one or more processing steps on the selected message d dispatching through a gateway aspects of the selected message for subsequent delivery to a message recipient and e pausing zero or more units of time.

In another embodiment of the present invention there is provided a processor based system on a server for dynamic message throttling that includes possibly among other things 1 workflow modules configured to perform a plurality of processing steps including at least a identifying a message pool to be processed where the message pool comprising a plurality of messages b partitioning the message pool into a plurality of subdivisions and c performing one or more processing steps while a delivery window is open including at least i opening a subdivision for processing yielding an open subdivision ii selecting a message from the open subdivision yielding a selected message iii performing a plurality of processing steps on the selected message and iv pausing zero or more units of time 2 a gateway configured to dispatch aspects of the selected message for subsequent delivery to a message recipient 3 a repository configured to preserve aspects of the results of the plurality of processing steps and 4 an administrator.

These and other features of the embodiments of the present invention along with their attendant advantages will be more fully appreciated upon a reading of the following detailed description in conjunction with the associated drawings.

Throughout the drawings a like reference numbers generally indicate identical or functionally similar elements and b the left most digit s of a reference number generally identify the drawing in which the reference number first appears. For example in reference numeral would direct the reader to for the first appearance of that element.

Further features and advantages of the present invention as well as the structure and operation of various embodiments thereof are described in detail below with reference to the accompanying drawings. It is noted that the invention is not limited to the specific embodiments described herein. Such embodiments are presented herein for illustrative purposes only. Additional embodiments will be apparent to persons skilled in the relevant art s based on the teachings contained herein.

Embodiments of the present invention are described herein in the context of a method and apparatus for dynamic throttling. Those of ordinary skill in the relevant art will realize that the following detailed description of the present invention is illustrative only and is not intended to be in any way limiting. Other embodiments of the present invention will readily suggest themselves to such skilled persons having the benefit of this disclosure. Reference will now be made in detail to implementations of the present invention as illustrated in the accompanying drawings.

In the interest of clarity not all of the routine features of the implementations described herein are shown and described. It will of course be appreciated that in the development of any such actual implementation numerous implementation specific decisions must be made in order to achieve the developer s specific goals such as compliance with application and business related constraints and that these specific goals will vary from one implementation to another and from one developer to another. Moreover it will be appreciated that such a development effort might be complex and time consuming but would nevertheless be a routine undertaking of engineering for those of ordinary skill in the art having the benefit of this disclosure.

Various aspects of the present invention may be implemented by software firmware hardware or any combination thereof. illustrates an example computer system in which the present invention or portions thereof can be implemented as computer readable code. Various embodiments of the invention are described in terms of this example computer system . After reading this description it will become apparent to a person skilled in the relevant art how to implement the invention using other computer systems and or computer architectures.

Computer system includes one or more processors such as processor . Processor can be a special purpose processor or a general purpose processor. Processor is connected to a communication infrastructure for example a bus or a network .

Computer system also includes a main memory preferably Random Access Memory RAM containing possibly inter alia computer software and or data .

Computer system may also include a secondary memory . Secondary memory may include for example a hard disk drive a removable storage drive a memory stick etc. A removable storage drive may comprise a floppy disk drive a magnetic tape drive an optical disk drive a flash memory or the like. A removable storage drive reads from and or writes to a removable storage unit in a well known manner. A removable storage unit may comprise a floppy disk magnetic tape optical disk etc. which is read by and written to by removable storage drive . As will be appreciated by persons skilled in the relevant art s removable storage unit includes a computer usable storage medium having stored therein possibly inter alia computer software and or data .

In alternative implementations secondary memory may include other similar means for allowing computer programs or other instructions to be loaded into computer system . Such means may include for example a removable storage unit and an interface . Examples of such means may include a program cartridge and cartridge interface such as that found in video game devices a removable memory chip such as an Erasable Programmable Read Only Memory EPROM or Programmable Read Only Memory PROM and associated socket and other removable storage units and interfaces which allow software and data to be transferred from the removable storage unit to computer system .

Computer system may also include an input interface and a range of input devices such as possibly inter alia a keyboard a mouse etc.

Computer system may also include an output interface and a range of output devices such as possibly inter alia a display one or more speakers etc.

Computer system may also include a communications interface . Communications interface allows software and or data to be transferred between computer system and external devices. Communications interface may include a modem a network interface such as an Ethernet card a communications port a Personal Computer Memory Card International Association PCMCIA slot and card or the like. Software and or data transferred via communications interface are in the form of signals which may be electronic electromagnetic optical or other signals capable of being received by communications interface . These signals are provided to communications interface via a communications path . Communications path carries signals and may be implemented using wire or cable fiber optics a phone line a cellular phone link a Radio Frequency RF link or other communications channels.

As used in this document the terms computer program medium computer usable medium and computer readable medium generally refer to media such as removable storage unit removable storage unit and a hard disk installed in hard disk drive . Signals carried over communications path can also embody the logic described herein. Computer program medium and computer usable medium can also refer to memories such as main memory and secondary memory which can be memory semiconductors e.g. Dynamic Random Access Memory DRAM elements etc. . These computer program products are means for providing software to computer system .

Computer programs also called computer control logic are stored in main memory and or secondary memory . Computer programs may also be received via communications interface . Such computer programs when executed enable computer system to implement the present invention as discussed herein. In particular the computer programs when executed enable processor to implement the processes of aspects of the present invention such as for example the steps discussed below. Accordingly such computer programs represent controllers of the computer system . Where the invention is implemented using software the software may be stored in a computer program product and loaded into computer system using removable storage drive interface hard drive or communications interface .

The invention is also directed to computer program products comprising software stored on any computer useable medium. Such software when executed in one or more data processing devices causes data processing device s to operate as described herein. Embodiments of the invention employ any computer useable or readable medium known now or in the future. Examples of computer useable mediums include but are not limited to primary storage devices e.g. any type of random access memory secondary storage devices e.g. hard drives floppy disks Compact Disc Read Only Memory CD ROM disks Zip disks tapes magnetic storage devices optical storage devices Microelectromechanical Systems MEMS nanotechnological storage device etc. and communication mediums e.g. wired and wireless communications networks local area networks wide area networks intranets etc. .

In the discussion below aspects of the present invention are described and illustrated as residing within a centrally located full featured MICV facility. Reference is made to U.S. Pat. No. 7 154 901 entitled INTERMEDIARY NETWORK SYSTEM AND METHOD FOR FACILITATING MESSAGE EXCHANGE BETWEEN WIRELESS NETWORKS and its associated continuations for a discussion of the concept of a MICV a summary of various of the services functions etc. that may be performed by a MICV and a discussion of the numerous advantages that may arise from same.

While portions of the discussion below will for clarity of exposition reference a MICV it will be readily apparent to one of ordinary skill in the relevant art that numerous other arrangements are equally possible and indeed are fully within the scope of the present invention. For example aspects of the present invention may be realized through any combination of possibly inter alia any one or more of 1 an element of a WC an element of a landline carrier an element of a MICV or multiple such elements working together 2 a Third Party 3P such as possibly inter alia a Content Provider CP such as for example a news organization an advertising agency a brand etc. or a Service Provider SP such as for example a X 3 multiple 3P entities working together 4 a 3P service bureau etc.

As illustrated in and reference numeral under one particular arrangement of aspects of the present invention a MICV may be disposed between possibly inter alia multiple WCs WC WC WC and multiple SPs SP SP and thus bridges all of the connected entities. A MICV thus as one simple example may offer various routing formatting delivery value add etc. capabilities that provide possibly inter alia 

1 A WC and by extension all of the MSs MS MS MS MS MS MS that are serviced by the WC with ubiquitous access to a broad universe of SPs and other entities that nay be connected to the MICV and

2 A SP and other entities that may be connected to the MICV with ubiquitous access to a broad universe of WCs and by extension to all of the MSs MS MS MS MS MS MS that are serviced by the WCs .

Generally speaking a MICV may have varying degrees of visibility e.g. access etc. to the MS MS MS SP etc. messaging traffic 

1 A WC may elect to route just their out of network messaging signaling data etc. traffic to a MICV. Under this approach the MICV would have visibility e.g. access etc. to just the portion of the WC s traffic that was directed to the MICV by the WC.

2 A WC may elect to route all of their messaging signaling data etc. traffic to a MICV. The MICV may possibly among other things subsequently return to the WC that portion of the traffic that belongs to i.e. that is destined for a MS of the WC. Under this approach the MICV would have visibility e.g. access etc. to all of the WC s traffic.

For purposes of illustration and reference numeral depict one specific logical implementation of aspects of a MICV that is possible under one particular arrangement of aspects of the present invention. and reference numeral depict among other things Gateways and that for example provide inter alia information data receipt and dispatch capabilities across among other things different application level and or physical level communication protocols Queues and that for example provide inter alia interim storage and buffering capabilities and a Message Highway MH that for example provides inter alia interconnection capabilities .

A dynamically updateable set of one or more Receivers Rx Rx in the diagram get input e.g. messages from a MICV MH and possibly inter alia deposit them on an intermediate or temporary Queue Q Q in the diagram for subsequent processing.

A dynamically updateable set of one or more Queues Q Q and Q Q in the diagram operate as intermediate or temporary buffers for incoming and outgoing data e.g. messages .

A dynamically updateable set of one or more WorkFlows WorkFlow WorkFlow in the diagram possibly inter alia a remove incoming messages from an intermediate or temporary Queue Q Q in the diagram b perform all of the required operations on the messages more about this below and c deposit the processed messages on an intermediate or temporary Queue Q Q in the diagram .

A dynamically updateable set of one or more Transmitters Tx Tx in the diagram possibly inter alia remove processed messages from an intermediate or temporary Queue Q Q in the diagram and put the messages on a MICV MH .

An Administrative Interface provides a linkage to all of the different components of a MPE so that a MPE along with each of the components of a MPE may be fully and completely administered or managed.

1 Scheduled e.g. daily weekly etc. and or on demand reporting with report results delivered through SMS MMS etc. messages through E Mail through a WWW based facility etc.

2 Scheduled and or on demand data mining initiatives possibly leveraging or otherwise incorporating one or more external data sources with the results of same presented through Geographic Information Systems GISs visualization etc. facilities and delivered through SMS MMS etc. messages through E Mail through a World Wide Web WWW based facility etc.

It is important to note that the depicted repositories DB DB are a logical representation of the possibly multiple physical repositories. The physical repositories may be implemented through any combination of conventional Relational Database Management Systems RDBMSs through Object Database Management Systems ODBMSs through in memory Database Management Systems DBMSs or through any other equivalent facilities.

It is important to note that depict illustrative logical implementations. It will be readily apparent to one of ordinary skill in the relevant art that numerous other components component arrangements etc. are easily possible and indeed are fully within the scope of the present invention.

For simplicity and identify various components as for example Message Highway and Message Processing Engine. It is important to note that such components are not limited to operating on processing handling etc. just e.g. SMS MMS IMS etc. messages. Rather as explained in detail below all of the various MICV components are natively capable of operating on processing handling etc. a more general quanta of data.

Central to the operation of a MICV is the unit of information within a MICV that is received manipulated or otherwise operated on dispatched etc. Unlike prior environments that might operate just on and thus potentially be limited just to an SMS message or a MMS message the unit of information within a MICV is a more general quanta of data. Accordingly a MICV is natively capable of operating on inter alia an SMS message a MMS message an IMS message an E Mail message a Voice Over IP VoIP data stream a video data stream e.g. a movie a video conference call etc. a voice telephone call signaling and other command and control data an audio data stream e.g. a song etc. a SIP addressed artifact IM data games and other software applications pictures and other static images data from software applications such as games etc.

Within a MICV a flexible extensible and dynamically configurable IMO see for example and reference numeral and reference numeral and and reference numeral may be employed as an internal representation of a received quanta of data. An IMO and may logically contain possibly inter alia one or more headers and a body and etc. within which for example aspects of a received quanta of data may be preserved. An IMO may physically be realized through any combination of possibly inter alia proprietary data structures Java Message Service JMS messages or objects flat files database entries in memory constructs etc.

For purposes of illustration within an SMS context a MICV may support the receipt and dispatch of information through possibly inter alia Short Message Peer to Peer SMPP via Transmission Control Protocol TCP IP and Mobile Application Part MAP via SS7. Under such a context 

1 and reference numeral depict an exemplary incoming SMS message received via for example SMPP with for example the data elements associated with the SMS message encapsulated within a SMPP Protocol Data Unit PDU encapsulated within a TCP Segment encapsulated within an IP Packet .

2 and reference numeral depict an exemplary incoming SMS message received via for example MAP with for example the data elements associated with the SMS message encapsulated within a Message Signal Unit MSU 

3 and reference numeral depict a hypothetical IMO that is possible in support of an SMS message received via for example SMPP and

4 and reference numeral depict a hypothetical IMO that is possible in support of an SMS message received via for example MAP.

It will be readily apparent to one of ordinary skill in the art that numerous alternative arrangements in connection with for example different contexts such as inter alia MMS VoIP a voice call signaling data command and control data software application data etc. and different communication protocols are easily possible.

For simplicity of exposition the balance of the present discussion will consider SMS messages. However it will be readily apparent to one of ordinary skill in the relevant art that as described above the more general unit of information a quanta of data is equally applicable.

Consider a pool of SMS messages Message Message see and reference numeral that has arisen from for example a disruption e.g. from a service interruption from a system outage etc. in a messaging ecosystem a burst of messages e.g. in response to a tele voting initiative from a mass broadcast of alert or information messages in response to a news item or an emergency situation etc.

Any number of constraints etc. may need to be considered as the messages in the pool are processed. As just one example various temporal factors e.g. the day of the week the time of the day etc. may contribute to define one or more windows. Within such a window i.e. when a window is open a message may be sent. Outside of such a window i.e. when a window is closed a message may need to be held and not sent until a sufficient amount of time passes so that a window re opens. and reference numeral depict a hypothetical window that opens at at after which messages may be sent and that closes at at after which messages may not be sent . Note that for simplicity of exposition no specific time reference point e.g. GMT a local time zone etc. is specified for .

It will be readily apparent to one of ordinary skill in the art that numerous alternative window arrangements are easily possible including inter alia the definition of multiple possibly discrete possibly overlapping windows during a given 24 hour period the definition of one or more quiet periods within a window during which messages may not be sent the association of a maximum message processing transmission etc. count to a particular period e.g. one minute three minutes five minutes 15 minutes one hour etc. within a window etc.

A pool of messages e.g. Message Message see and reference numeral may be divided into some number of segments Segment Segment through among other things a a range of parameters configuration values settings etc. and b any combination of one or more means including inter alia 

1 Uniform Means. For example given inter alia a specified number of segments a pool of messages may be evenly divided across the segments. As illustrated by and reference numeral a pool of 1740 messages may be divided into four segments with each segment containing 435 messages and as illustrated by and reference numeral the same pool of 1740 messages may be divided into six segments with each segment containing 290 messages.

2 Random Means. For example given inter alia a specified number of segments along with perhaps other constraints such as for example segment size maximums and or minimums etc. a pool of messages may be randomly divided across the segments. As illustrated by and reference numeral a pool of messages may be divided into four segments with each segment containing a different number of messages and as illustrated by and reference numeral the same pool of 1220 messages may be divided into six segments with each segment containing a different number of messages

3 Algorithmic Means. For example given inter alia a specified number of segments an algorithm or formula as supplied for example by a user by an intermediary by a WC etc. along with perhaps other constraints such as for example segment size maximums and or minimums etc. a pool of messages may be algorithmically divided across the segments.

The above identified means are illustrative only and it will be readily apparent to one of ordinary skill in the relevant art that numerous other means are easily possible.

Various of the parameters configuration values settings etc. and or the means uniform random etc. that were described above may be implemented through FIG. s WorkFlow component WorkFlow WorkFlow in the diagram .

1 A messagePool that comprises inter alia a the total number of messages in the pool noOfMessages b the number of segments into which the pool has been divided noOfSegments and c the segments themselves segment .

2 A segment that comprises inter alia a an indicator of the status of the segment perhaps for example CLOSED WORKING WORKED or DONE b the number of messages in the segment noOfMessages c the number of messages in the segment that have been sent noOfMessagesSent and d the messages themselves message .

3 A message that comprises inter alia a an indicator of the status of the message perhaps for example UNSENT or SENT and b the message itself message .

The sending of a message see Step 3 above may leverage inter alia aspects of the architecture e.g. queues gateways etc. as depicted in and the constructs e.g. an IMO that were described above.

The ProcessPool function may be enhanced extended etc. through any number of means including inter alia optionally pausing after a message is sent waiting for a positive or negative acknowledgement receipt etc. and then acting appropriately e.g. continuing on with processing after a positive indicator is received implementing a message send retry mechanism to inter alia support the case when a negative acknowledgement receipt etc. is received processing the message pool segments in some alternate order as opposed to the indicated order noOfSegments processing the messages in a segment in some alternate order as opposed to the indicated order noOfMessages etc.

Aspects of the ProcessPool function may among other things be implemented through FIG. s WorkFlow component WorkFlow WorkFlow in the diagram .

2 Iterate or step through each of the segments noOfSegments and a mark each segment as unprocessed CLOSED with no messages sent and b mark each message in the segment as unsent.

4 If the window is closed then halt any child segment processing threads and loop to wait until the window opens .

5 If the window is open then locate an unprocessed segment i.e. the status of the segment is CLOSED and if possible launch a child segment processing thread for the segment.

6 If a segment has been fully worked by a child segment processing thread then mark the segment as being DONE.

7 If a segment that is currently being worked i.e. the status of the segment is WORKING has reached a specified number of messages sent threshold e.g. perhaps 80 perhaps 50 etc. then another segment may be opened for processing.

8 If all of the segments have been fully processed i.e. every segment has a status of DONE then exit the loop.

The sending of a message see Step 1 above may leverage inter alia aspects of the architecture e.g. queues gateways etc. as depicted in and the constructs e.g. an IMO that were described above.

The ProcessPool function and or the ProcessSegment function may be enhanced extended etc. through any number of means including inter alia optionally pausing after a message is sent waiting for a positive or negative acknowledgement receipt etc. and then acting appropriately e.g. continuing on with processing after a positive indicator is received implementing a message send retry mechanism to inter alia support the case when a negative acknowledgement receipt etc. is received processing the messages in a segment in some alternate order as opposed to the indicated order noOfMessages breaking the ProcessPool function into some number of smaller functions and optionally tying various of those smaller functions to child worker threads etc.

Aspects of the ProcessPool function and or the ProcessSegment function may among other things be implemented through FIG. s WorkFlow component WorkFlow WorkFlow in the diagram .

As noted above in connection with both and after a message is sent it is possible to optionally pause wait for a positive or negative acknowledgement receipt etc. and then act appropriately e.g. continue on with processing after a positive indicator is received . Such an approach effectively makes the message transmission self moderating or self regulating i.e. as fast or as slow as a positive acknowledgement receipt etc. is received the next message may be processed. If for example a particular WC to whom a MICV is sending a message can accept messages quickly then messages will be sent quickly if the WC can only accept messages slowly then messages will be sent slowly.

It will be readily apparent to one of ordinary skill in the relevant art that numerous other ProcessPool functions beyond those that were illustrated by and are easily possible. For example a range of Quality of Service QoS metrics targets etc. for which in some cases a financial amount may be associated may be included as additional processing constraints.

In the discussion above a simple model of Message Pool Segments Messages was employed. That simple model was employed for ease of exposition and was inter alia in no way intended to be exhaustive or limiting. It will be readily apparent to one of ordinary skill in the relevant art that numerous other flat hierarchical etc. models of any size depth etc. such as for example Message Pool Segments Units Messages Message Pool Blocks Groups Parts Messages etc. may be employed.

In the discussion above reference was made on numerous occasions for purposes of illustration to SMS MMS etc. message traffic. Such references were not intended to be exhaustive or to limit the invention to the specific forms disclosed. It will be readily apparent to one of ordinary skill in the relevant art that numerous other quanta of data including inter alia IMS message an E Mail message a VoIP data stream a video data stream e.g. a movie a video conference call etc. a voice telephone call signaling and other command and control data an audio data stream e.g. a song etc. IM data games and other software applications pictures and other static images data from software applications such as games SIP addressed artifacts WAP based exchanges etc. are easily possible and indeed are fully within the scope of the present invention.

It is important to note that the hypothetical examples that were presented above which were described in the narrative and which were illustrated in the accompanying figures are exemplary only. They are not intended to be exhaustive or to limit the invention to the specific forms disclosed. It will be readily apparent to one of ordinary skill in the relevant art that numerous alternatives to the presented examples are easily possible and indeed are fully within the scope of the present invention.

