---

title: Local processing of received RFID tag responses
abstract: Radio frequency identification (RFID) tags are selected for inventorying using a combination of preselect and/or post select criteria. The selection commands can be for selecting according to a tag memory content, by invoking the mask address or by comparing other tag characteristics. Selection criteria can be determined locally at a modem block of a reader or provided to the modem block by higher layers of the reader. Tags meeting the selection criteria are reported to the higher layers for further actions. Some tags may be held while waiting for instructions from the higher layer block(s). The instructions may involve one or more access operations, which may be performed using a higher transmit power than other operations.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08570157&OS=08570157&RS=08570157
owner: Impinj, Inc.
number: 08570157
owner_city: Seattle
owner_country: US
publication_date: 20120302
---
This utility patent application is a continuation in part of U.S. patent application Ser. No. 11 472 179 filed on Jun. 20 2006 which claims the benefit of U.S. Provisional Application Ser. No. 60 713 304 filed on Aug. 31 2005. The foregoing applications are hereby incorporated herein by reference.

Radio Frequency IDentification RFID systems typically include RFID tags and RFID readers the latter are also known as RFID reader writers or RFID interrogators . RFID systems can be used in many ways for locating and identifying objects to which the tags are attached. RFID systems are particularly useful in product related and service related industries for tracking large numbers of objects being processed inventoried or handled. In such cases an RFID tag is usually attached to an individual item or to its package.

In principle RFID techniques entail using an RFID reader to interrogate one or more RFID tags. The reader transmitting a Radio Frequency RF wave performs the interrogation. A tag that senses the interrogating RF wave responds by transmitting back another RF wave. The tag generates the transmitted back RF wave either originally or by reflecting back a portion of the interrogating RF wave in a process known as backscatter. Backscatter may take place in a number of ways.

The reflected back RF wave may further encode data stored internally in the tag such as a number. The response is demodulated and decoded by the reader which thereby identifies counts or otherwise interacts with the associated item. The decoded data can denote a serial number a price a date a destination other attribute s any combination of attributes and so on.

An RFID tag typically includes an antenna system a power management section a radio section and frequently a logical section a memory or both. In earlier RFID tags the power management section included an energy storage device such as a battery. RFID tags with an energy storage device are known as active tags. Advances in semiconductor technology have miniaturized the electronics so much that an RFID tag can be powered solely by the RF signal it receives. Such RFID tags do not include an energy storage device and are called passive tags.

In typical applications responses from the RFID tags may be forwarded to a remote processor such as a controller which processes the responses determines which actions are to be taken and directs the RFID reader accordingly. In a dynamic environment where tags enter and leave a field of view of the RFID reader respond with varying reliability and so on valuable processing time may be lost in transmitting tag responses to the remote processor and waiting for a decision.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used as an aid in determining the scope of the claimed subject matter.

Embodiments are directed to an RFID system comprising of layers such as a modem layer an application processor layer a server layer a controller layer and the like. An RFID reader is configured to start an inventory operation of tags including any set or combination of preselect and or post select operations. Individual or logic combinations of select commands may be transmitted to the tags for determining whether a tag meets a selection criterion or not.

A preselect criterion may be used to discard tags that do not meet the criterion. The post select criterion may be used to determine tags that are categorized as an exception and as such handled by higher levels for further operations. This eliminates the need to process each tag by the full reader system.

The selection process may be performed by comparing a tag memory content or a characteristic of a tag response to a list of mask values from a local database. The selection criteria may be provided to the modem layer from higher layers or generated by the modem layer in response to instructions from the higher layers.

According to some embodiments tags meeting the criterion may be held while the modem layer awaits instructions from the higher layers for further operations. An optional read operation may also be performed prior to determining whether or not the tag meets the criterion.

In some embodiments the further operations may include one or more access operations for accessing tags meeting the criterion. In response the modem layer and or higher layers may determine if reader transmit power should be increased to perform the access operation s . If so the modem layer may increase the reader transmit power perform the access operation s then decrease the transmit power.

This and other features and advantages of the invention will be better understood in view of the Detailed Description and the Drawings.

Various embodiments will be described in detail with reference to the drawings where like reference numerals represent like parts and assemblies throughout the several views. Reference to various embodiments does not limit the scope of the invention which is limited only by the scope of the claims attached hereto. Additionally any examples set forth in this specification are not intended to be limiting and merely set forth some of the many possible embodiments for the claimed subject matter.

Throughout the specification and claims the following terms take at least the meanings explicitly associated herein unless the context clearly dictates otherwise. The meanings identified below are not intended to limit the terms but merely provide illustrative examples for the terms. The meaning of a an and the includes plural reference the meaning of in includes in and on. The term connected means a direct electrical connection between the items connected without any intermediate devices. The term coupled means either a direct electrical connection between the items connected or an indirect connection through one or more passive or active intermediary devices. The term circuit means either a single component or a multiplicity of components either active and or passive that are coupled together to provide a desired function. The term signal means at least one current voltage charge temperature data or other measurable quantity. The terms RFID reader and RFID tag are used interchangeably with the terms reader and tag respectively throughout the text and claims. The terms command size and command length are used interchangeably throughout the text and claims. While this description is mostly in terms of commands that is only intended as an example and it is intended to apply also to more generalized words.

RFID reader has an antenna and may be in communication with database . Reader transmits an interrogating Radio Frequency RF wave which can be perceived by tags . . . K . . . N.

RFID tags X X here stands for 1 2 . . . K . . . N can be passive tags or active tags i.e. tags having their own power source. Where tags X are passive tags they are powered from wave . Each tag X includes an antenna X. Upon sensing interrogating RF wave each tag X may generate a wave X in response. RFID reader senses and interprets waves X.

In as in other figures interrogating RF wave is shown as larger than waves X. This is to signify that interrogating RF wave typically has a higher intensity than response wave X.

Reader and tag K thus exchange data via waves and K. In a session of such an exchange each encodes modulates and transmits data to the other and each receives demodulates and decodes data from the other. The data is modulated onto and decoded from RF waveforms as will be seen in more detail below.

Encoding the data can be performed in a number of different ways. For example protocols are devised to communicate in terms of symbols also called RFID symbols. A symbol for communicating can be a preamble a null symbol a symbol 0 a symbol 1 and so on. Further symbols can be implemented for ultimately exchanging binary data such as 0 and 1 if that is desired.

In addition groups of these bits and or symbols are named according to their function. For example it is customary to refer to such groups as commands data payload handle and so on.

RFID reader and RFID tags X talk and listen to each other by taking turns. As seen on axis TIME when reader talks to tag K the communication session is designated as R T and when tag K talks to reader the communication session is designated as T R . Along the TIME axis a sample R T communication session occurs during a time interval and a following sample T R communication session occurs during a time interval . Of course intervals can be of different durations here the durations are shown approximately equal only for purposes of illustration.

According to blocks and RFID reader talks during interval and listens during interval . According to blocks and RFID tag K listens while reader talks during interval and talks while reader listens during interval .

In terms of actual technical behavior during interval reader talks to tag K as follows. According to block reader transmits wave which was first described in . At the same time according to block tag K receives wave and processes it. Meanwhile according to block tag K does not backscatter with its antenna and according to block reader has no wave to receive from tag K.

During interval tag K talks to reader as follows. According to block reader transmits a Continuous Wave CW which can be thought of as a carrier signal that ideally encodes no information. As discussed before this carrier signal serves both to be harvested by tag K for its own internal power needs and also as a wave that tag K can backscatter. Indeed during interval according to block tag K does not receive a signal for processing. Instead according to block tag K modulates the CW emitted according to block so as to generate backscatter wave K. Concurrently according to block reader receives backscatter wave K and processes it.

In the above an RFID reader interrogator may communicate with one or more RFID tags in any number of ways. Some such ways are called protocols. A protocol is a specification that calls for specific manners of signaling between the reader and the tags.

One such protocol is called the Specification for RFID Air Interface EPC TM Radio Frequency Identity Protocols Class 1 Generation 2 UHF RFID Protocol for Communications at 860 MHz 960 MHz which is also colloquially known as the Gen2 Spec version 1.2.0 of which is hereby incorporated by reference in its entirety. The Gen2 Spec has been ratified by EPCglobal which is an organization that maintains a website at at the time this document is initially filed with the USPTO.

It was described above how reader and tag K communicate in terms of time. In addition communications between reader and tag K may be restricted according to frequency. One such restriction is that the available frequency spectrum may be partitioned into divisions that are called channels. Different partitioning manners may be specified by different regulatory jurisdictions and authorities e.g. FCC in North America CEPT in Europe etc. .

The reader typically transmits with a transmission spectrum that lies within one channel. In some regulatory jurisdictions the authorities permit aggregating multiple channels into one or more larger channels but for all practical purposes an aggregate channel can again be considered a single albeit larger individual channel.

Tag K can respond with a backscatter that is modulated directly onto the frequency of the reader s emitted CW also called baseband backscatter. Alternatively Tag K can respond with a backscatter that is modulated onto a frequency developed by Tag K that is different from the reader s emitter CW and this modulated tag frequency is then impressed upon the reader s emitted CW. This second type of backscatter is called subcarrier backscatter. The subcarrier frequency can be within the reader s channel can straddle the boundaries with the adjacent channel or can be wholly outside the reader s channel.

A number of jurisdictions require a reader to hop to a new channel on a regular basis. When a reader hops to a new channel it may encounter RF energy there that could interfere with communications.

Embodiments of the present disclosure can be useful in different RFID environments for example in the deployment of RFID readers in sparse or dense reader environments in environments with networked and disconnected readers such as where a hand held reader may enter the field of networked readers in environments with mobile readers or in environments with other interference sources. It will be understood that the present embodiments are not limited to operation in the above environments but may provide improved operation in such environments.

Many RFID protocols have a way to select individual tags or populations of tags prior to inventorying the tag or tags. For example the Gen2 spec has a Select command that a reader issues prior to starting an inventory round. Deterministic protocols such as Class 0 allow a reader to navigate only desired EPCs of the tag population.

Selecting allows a reader to choose which tags it wants to talk to and partitions a tag population before inventory thereby accelerating the inventory process typically unwanted tags do not respond . Selecting also allows readers to treat tags like records in a database. Multiple Select commands may be implemented using a Boolean operation on a tag population such as union U intersection and negation for partitioning of tag populations.

In one embodiment the criteria may be a flag being set by the tag in response to a comparison of a mask value received from the reader with sensor data stored at a mask address.

Reader has accomplished singulation by first issuing appropriate commands which have caused tags X to transition to appropriate internal states. In this example at least tag K is in a state where it can receive an access type command while the remaining tags are in states where generally they do not respond or take action until reader and singulated tag K complete their exchanges.

The term singulation as used for the present document generally means a process for distinguishing a tag from other tags. As such singulation may be unnecessary when a single reader is addressing a single tag or where there is no interference from or concern about any other RFID components such as other RFID tags. The term singulation as used here may by coincidence be functionally the same as a specific term singulation which means a process of a reader that can be performed with many or even a single tag.

The term accessing as used for the present document generally means a process for retrieving information stored at the tag and or causing information stored at the tag to be modified. This may include receiving an identifier symbol user specified data and the like from the tag as well as storing a new identifier symbol etc. at the tag. Accessing may further include causing one or more operational parameters of the tag to be changed such as a security mechanism.

Local block is responsible for communicating with the tags. Local block includes a block of an antenna and a driver of the antenna for communicating with the tags. Some readers like that shown in local block contain a single antenna and driver. Some readers contain multiple antennas and drivers and a method to switch signals among them including sometimes using different antennas for transmitting and for receiving. And some readers contain multiple antennas and drivers that can operate simultaneously. A demodulator decoder block demodulates and decodes backscattered waves received from the tags via antenna block . Modulator encoder block encodes and modulates an RF wave that is to be transmitted to the tags via antenna block .

Local block additionally includes an optional local processor . Processor may be implemented in any number of ways known in the art. Such ways include by way of examples and not of limitation digital and or analog processors such as microprocessors and digital signal processors DSPs controllers such as microcontrollers software running in a machine such as a general purpose computer programmable circuits such as Field Programmable Gate Arrays FPGAs Field Programmable Analog Arrays FPAAs Programmable Logic Devices PLDs Application Specific Integrated Circuits ASIC any combination of one or more of these and so on. In some cases some or all of the decoding function in block the encoding function in block or both may be performed instead by processor .

Local block additionally includes an optional local memory . Memory may be implemented in any number of ways known in the art. Such ways include by way of examples and not of limitation nonvolatile memories NVM read only memories ROM random access memories RAM any combination of one or more of these and so on. Memory if provided can include programs for processor to run if provided.

In some embodiments memory stores data read from tags or data to be written to tags such as Electronic Product Codes EPCs Tag Identifiers TIDs and other data. Memory can also include reference data that is to be compared to the EPC codes instructions and or rules for how to encode commands for the tags modes for controlling antenna and so on. In some of these embodiments local memory is provided as a database.

Some components of local block typically treat the data as analog such as the antenna driver block . Other components such as memory typically treat the data as digital. At some point there is a conversion between analog and digital. Based on where this conversion occurs a whole reader may be characterized as analog or digital but most readers contain a mix of analog and digital functionality.

If remote components are indeed provided they are coupled to local block via an electronic communications network . Network can be a Local Area Network LAN a Metropolitan Area Network MAN a Wide Area Network WAN a network of networks such as the internet and so on. In turn local block then includes a local network connection for communicating with network .

There can be one or more remote component s . If more than one they can be located at the same place with each other or in different places. They can access each other and local block via network or via other similar networks and so on. Accordingly remote component s can use respective remote network connections. Only one such remote network connection is shown which is similar to local network connection etc.

Remote component s can also include a remote processor . Processor can be made in any way known in the art such as was described with reference to local processor .

Remote component s can also include a remote memory . Memory can be made in any way known in the art such as was described with reference to local memory . Memory may include a local database and a different database of a Standards Organization such as one that can reference EPCs.

Of the above described elements it is advantageous to consider a combination of these components designated as operational processing block . Block includes those that are provided of the following local processor remote processor local network connection remote network connection and by extension an applicable portion of network that links connection with connection . The portion can be dynamically changeable etc. In addition block can receive and decode RF waves received via antenna and cause antenna to transmit RF waves according to what it has processed.

Block includes either local processor or remote processor or both. If both are provided remote processor can be made such that it operates in a way complementary with that of local processor . In fact the two can cooperate. It will be appreciated that block as defined this way is in communication with both local memory and remote memory if both are present.

Accordingly block is location agnostic in that its functions can be implemented either by local processor or by remote processor or by a combination of both. Some of these functions are preferably implemented by local processor and some by remote processor . Block accesses local memory or remote memory or both for storing and or retrieving data.

Reader system operates by block generating communications for RFID tags. These communications are ultimately transmitted by antenna block with modulator encoder block encoding and modulating the information on an RF wave. Then data is received from the tags via antenna block demodulated and decoded by demodulator decoder block and processed by processing block .

Embodiments additionally include programs and methods of operation of the programs. A program is generally defined as a group of steps or operations leading to a desired result due to the nature of the elements in the steps and their sequence. A program is usually advantageously implemented as a sequence of steps or operations for a processor such as the structures described above.

Performing the steps instructions or operations of a program requires manipulation of physical quantities. Usually though not necessarily these quantities may be transferred combined compared and otherwise manipulated or processed according to the steps or instructions and they may also be stored in a computer readable medium. These quantities include for example electrical magnetic and electromagnetic charges or particles states of matter and in the more general case can include the states of any physical devices or elements. It is convenient at times principally for reasons of common usage to refer to information represented by the states of these quantities as bits data bits samples values symbols characters terms numbers or the like. It should be borne in mind however that all of these and similar terms are associated with the appropriate physical quantities and that these terms are merely convenient labels applied to these physical quantities individually or in groups.

Embodiments furthermore include storage media. Such media individually or in combination with others have stored thereon instructions of a program made according to the invention. A storage medium according to the invention is a computer readable medium such as a memory and is read by a processor of the type mentioned above. If a memory it can be implemented in a number of ways such as Read Only Memory ROM Random Access Memory RAM etc. some of which are volatile and some non volatile.

Even though it is said that the program may be stored in a computer readable medium it should be clear to a person skilled in the art that it need not be a single memory or even a single machine. Various portions modules or features of it may reside in separate memories or even separate machines. The separate machines may be connected directly or through a network such as a local access network LAN or a global network such as the Internet.

Often for the sake of convenience only it is desirable to implement and describe a program as software. The software can be unitary or thought in terms of various interconnected distinct software modules.

This detailed description is presented largely in terms of flowcharts algorithms and symbolic representations of operations on data bits on and or within at least one medium that allows computational operations such as a computer with memory. Indeed such descriptions and representations are the type of convenient labels used by those skilled in programming and or the data processing arts to effectively convey the substance of their work to others skilled in the art. A person skilled in the art of programming may use these descriptions to readily generate specific instructions for implementing a program according to the embodiments.

Embodiments of an RFID reader system can be implemented as a combination of hardware and software. It is advantageous to consider such a system as subdivided into components or modules. A person skilled in the art will recognize that some of these components or modules can be implemented as hardware some as software some as firmware and some as a combination. An example of such a subdivision is now described.

RFID reader system includes one or more antennas and an RF Front End for interfacing with antenna s . These can be made as described above. In addition Front End typically includes analog components.

System also includes a Signal Processing module . In this embodiment module exchanges waveforms with Front End such as I and Q waveform pairs. In some embodiments signal processing module is implemented by itself in an FPGA.

System also includes a Physical Driver module which is also known as Data Link. In this embodiment module exchanges bits with module . Data Link can be the stage associated with framing of data. In one embodiment module is implemented by a Digital Signal Processor.

System additionally includes a Media Access Control module which is also known as MAC layer. In this embodiment module exchanges packets of bits with module . MAC layer can be the stage for making decisions for sharing the medium of wireless communication which in this case is the air interface. Sharing can be between reader system and tags or between system with another reader or between tags or a combination. In one embodiment module is implemented by a Digital Signal Processor.

System moreover includes an Application Programming Interface module which is also known as API Modem API Mach1 and MAPI. In some embodiments module is itself an interface for a user.

System further includes a host processor . Processor exchanges signals with MAC layer via module . In some embodiments host processor is not considered as a separate module but one that includes some of the above mentioned modules of system . A user interface is coupled to processor and it can be manual automatic or both.

Host processor can include applications for system . In some embodiments elements of module may be distributed between processor and MAC layer .

It will be observed that the modules of system form something of a chain. Adjacent modules in the chain can be coupled by the appropriate instrumentalities for exchanging signals. These instrumentalities include conductors buses interfaces and so on. These instrumentalities can be local e.g. to connect modules that are physically close to each other or over a network for remote communication.

The chain is used in opposite directions for receiving and transmitting. In a receiving mode wireless waves are received by antenna s as signals which are in turn processed successively by the various modules in the chain. Processing can terminate in any one of the modules. In a transmitting mode initiation can be in any one of these modules. That which is to be transmitted becomes ultimately signals for antenna s to transmit as wireless waves.

The architecture of system is presented for purposes of explanation and not of limitation. Its particular subdivision into modules need not be followed for creating embodiments according to the invention. Furthermore the features of the invention can be performed either within a single one of the modules or by a combination of them.

An RFID reader system according to embodiments includes a first layer and a second layer where the first layer is configured to receive a particular one of the responses determine whether the particular response meets a post select criterion and hand off control to the second layers if the criterion is met. The first layer then waits until control is returned to it and then receives a second one of the responses.

The first layer may be a modem that also includes a Media Access Control layer. Furthermore the second layer may be a host processor and the first layer and the second layer may communicate through a Modem Application Programming Interface MAPI .

The first layer may be a software implemented modem or a hardware implemented modem. Similarly the second layer may be a software implemented application processor or a hardware implemented application processor. In some embodiments the first layer and the second layer may be integrated. Moreover the first layer may also include an analog interface module.

According to other embodiments the first criterion may be a preselect criterion and include matching of a tag memory content to a local database content associated with the first layer. The second criterion may be a post select criterion and include matching of a tag memory content or a tag characteristic to a local database content associated with the second layer. The first layer may be further configured to report to the second layer at least a portion of the particular response always or only if it meets a reporting condition.

According to further embodiments the reporting condition may be a preselect criterion or a logic combination of criteria which may include comparing the particular response to a mask. The first layer may also be configured to read the RFID tag that provided the particular response before determining whether the post select criterion is met based on a characteristic of the post select criterion. The post select criterion may be received at the first layer from the second layer.

According to yet other embodiments the first layer may determine whether the particular response meets a preselect criterion or a logic combination of preselect criteria and apply the post select criterion only if the preselect criteria are met. The particular response may be discarded if it does not meet the preselect criteria.

Furthermore the first layer may perform a read operation on the RFID tag that provided the particular response before determining whether the preselect criterion is met as the preselect criterion may be in a memory area that can only be obtained via a direct read of the tag memory.

In some embodiments the first layer may set a reader transmit power level based on instructions from a higher layer or suitable reader tag and environmental parameters. Transmit power level selection is described in more detail below in relation to .

One of the typical RFID operations is inventorying of tags by a reader i.e. identifying a single tag from among many . A reader inventories tags one by one. Inventorying typically needs to be a fast operation. For example if 250 tags are on a pallet moving at 15 mph through a dock door the reader has less than a second to read all the tags. The reader operates quickly sending the data to a server or other network device as it reads. Commonly many tags are merely inventoried few are accessed.

According to embodiments policies that allow a layered RFID system architecture to perform typical tag operations locally are implemented sending only exceptions to a higher layer.

All layers manage anticipated tag responses locally without incurring handoff delays. Only exceptions require handoff between layers. Therefore only exceptions incur delays. First layer modem inventories tags quickly receiving tag responses e.g. EPC etc. and comparing them to a post select criterion operation . If the post select comparison produces a match control of the tag is handed off to second layer . Once the second layer completes its operations the control is returned to first layer . The second layer may be an AP a server a controller application and the like.

According to other embodiments tags that do not match a preselect criterion may be discarded prior to the post select comparison further saving processing time.

For example a server or an AP associated with the reader may download a database file to the modem containing information for all the tags the modem should see and what the modem should do with them. The modem may inventory and access tags locally batching inventory and access results to the server or the AP. The modem only hands off control to the server or the AP when a tag is not in the downloaded database file.

Modem performs radio functions such as transmitter signal processing transmitting receiving tag responses and receiver signal processing. According to some embodiments modem may include local database used to store a local list of tag data for identifying tags that are to be selected.

Application Processor AP processes tags and interfaces with higher levels of reader control such as server or a controller application not shown through a network. AP may also decide what the modem should do with tags choose the protocol e.g. Class 0 Class 1 Class 1 Gen2 etc. tell the modem which tags to select filter tag reads and identify tag capabilities prior to accessing it. AP may further match tag manufacturer ID to its internal tag manufacturers variants database issue appropriate commands for example AP may only read user memory if it exists on a particular tag receive and process server requests and send EPC data to server .

Local database is used to store list of tags for the select operations described herein. In some embodiments remote database may also be used to store part or all of the tag lists or other data associated with it. For example data stored in remote database or local database may be forwarded to modem for generation of selection criteria.

The Modem API MAPI is the interface between modem and AP . In a typical operation AP tells modem which selection criteria to implement via MAPI . Modem reports its results to AP via MAPI and the MAPI allows a handoff of control between the modem and the AP.

In a typical implementation once modem is inventorying the tags modem talks first while AP listens. Modem performs tag functions and AP receives results from the modem. This is followed by AP talking and modem listening where AP tells modem what to do next. Modem receives commands from AP and performs them on the tags.

Referring to typical commands that are exchanged over MAPI between AP and modem are inventory and access commands. As part of the inventorying process select commands may also be exchanged over MAPI .

Select is a global method that a reader uses to choose a priori which tags it wants to inventory. Inventory is a global procedure that a reader uses to count tags and identify the tag types one at a time until it counts them all. Access is a non global procedure that a reader uses to modify individual tags. Select operation uses preselect and or post select masks to compare tags to a local database and report exceptions to AP as part of the inventorying process.

Access includes read write lock kill and custom commands. A reader must associate an external parameter with the tag ID in order to perform the operation s . In the read operation the reader needs to know what data is on the tag and what subset of the data it needs to read. For the write operation the reader needs to know what to write to the specific tag and where to write it. For the lock operation the reader needs to know the current state of the tag s memory what to change and whether it needs a password. For the kill operation the reader must use the proper kill password.

Access operations may also include security and or file management commands. Security commands involve some aspect of reader tag security e.g. reader tag electronic signing of messages encryption decryption verification of tag reader authenticity transmitting receiving secure messages or any other security related aspect of reader tag communication . File management commands involve files stored on the reader and or tag and may include creating deleting opening closing and or modifying one or more files stored on the reader and or tag.

As shown in the data stored in tag memory may include identification information associated with tag K information associated with an item the tag is attached to communication parameters such as a password externally delivered data and the like. Data may be stored in tag memory during a production stage or during an operation. A tag processing block may access tag memory to store or retrieve one or more of a received command password and externally delivered data. The processing block may also access tag memory to change its contents based on a command received from reader .

Tag memory may be partitioned into user specific portion tag identification portion object identification portion EPC and reserved portion . In other embodiments tag memory may be partitioned in other ways with fewer or more portions or not partitioned at all.

User specific portion may be employed to store user specified information including sensor data if the tag is associated with a sensor whose data is mapped to user memory. Tag identification portion TID may be employed to store information associated with a tag identifier including sensor data if the sensor data is mapped to TID memory.

Object identification portion EPC memory can be arranged to store as convenient a protocol control PC parameter an EPC code and or a CRC16 cyclic redundancy check as shown in tag memory addresses . EPC memory may also contain sensor data if the sensor data is mapped into EPC memory.

Reserved memory portion may be used to store system parameters such as passwords. Tag memory addresses illustrate two such example parameters an access command password and a kill command password. Reserved memory may also contain sensor data if the tag is associated with a sensor whose data is mapped into reserved memory.

Any portion of memory may store data in a single group such as a single byte or word or may store data in multiple groups or words multiple bytes .

AP Local database shown in represents local data storage in the application processor block of the reader that may be utilized to store local list of TIDs for local decision making in selecting tag sub populations.

A post select criterion passed to the modem or generated by the modem based on received instructions may include a post select mask address in a number of ways such as by a post select mask address pointer and post select mask length. The post select mask address pointer may specify the start of the post select mask address and the post select mask length may specify the length of the post select mask value located at the starting address.

In example diagram of post select mask value has a mask length of nine bits. Post select mask address pointer indicates that the EPC data to be compared begins at the third bit of tag memory .

During operation the tag processing block reads tag memory beginning from the third bit as indicated by post select mask address pointer and reads the number of bits specified by the mask length parameter. The processing block compares the contents of that portion of memory to post select mask value .

In example diagram post select mask value matches the indicated portion of tag memory so the processing block sets a flag accordingly.

The example diagram of shows the same tag memory with a different EPC value and post select mask address pointer . The post select mask value is the same as in . During the comparison operation the processing block detects that the seventh bit of tag memory is different from the corresponding bit value in post select mask value . Therefore there is no match in example diagram of and the flag is set to a different value by the processing block.

Comparison operation may be performed by tag K which stores the preselect mask to a memory location then compares the preselect mask with the EPC value at memory address and determines whether they match. The tag may then respond to the reader reporting the match.

In another embodiment tag K may perform the comparison as it receives the preselect command without first saving the preselect mask value into a memory location. In yet another embodiment tag K may report its EPC value to the reader which performs the comparison operation .

Depending on a result of the comparison i.e. if there is a match or not a flag may be set in the tag or in the reader. The flag may be a value stored at another memory location may be a state machine value and the like.

At operation the modem block of the reader may report the tag to the application processor block or a server controlling the reader if there is a match. The AP block or the server may then determine additional operations to be performed with the tag and instruct the modem accordingly.

Differently from the operations in reader may send a read command performing a read operation for a selected location of tag memory in the example scenario memory location .

Comparison operation may then be performed using the preselect mask in preselect command and the data from memory location as described above. If there is a match tag K may be reported by the reader modem block to the AP block the server or a controller application.

If the reader detects a match it holds the tag i.e. the tag waits for further instructions from the reader until a decision and instructions are received from higher layers of the reader such as the AP block the controller and the like.

By holding the tag in response to a match with the post select mask value processing time is saved since the tag is not fully accessed until further instructions are received by the modem. At the same time the modem does not have to go through the complete selection process again having found a matching tag.

The claimed subject matter also includes methods. Some are methods of operation of an RFID reader or RFID reader system. Others are methods for controlling an RFID reader or RFID reader system.

These methods can be implemented in any number of ways including the structures described in this document. One such way is by machine operations of devices of the type described in this document.

Another optional way is for one or more of the individual operations of the methods to be performed in conjunction with one or more human operators performing some. These human operators need not be collocated with each other but each can be only with a machine that performs a portion of the program.

According to some embodiments a method for an RFID reader system with at least two layers to process received RFID tag responses includes receiving a particular one of the responses at a first layer determining whether the particular response meets at least one post select criterion still at the first layer and handing off control from the first layer to a second layer if the post select criterion is met. The reader may then wait until control is returned to the first layer and until a second response is received at the first layer.

The method may further include reporting to the second layer at least a portion of the particular response always or only if it meets a reporting condition such as a preselect criterion.

Applying the post select criterion may include comparing the particular response to a mask. Each response may be received by establishing communication with a respective individual tag and the established communication with the individual tag that originated the particular response may be maintained until control is received back from the second layer.

The method may also include reading the RFID tag that provided the particular response before determining whether the post select criterion is met. The reading may be based on a characteristic of the post select criterion. Moreover the post select criterion may be received at the first layer from the second layer.

According to other embodiments the method may include determining whether the particular response meets a preselect criterion where the post select criterion is applied only if the preselect criterion is met. The particular response may be discarded if it does not meet the preselect criterion.

In further embodiments associated data may be generated for the particular response and reported to the second layer along with the portion of the particular response. The associated data may include a time stamp an indication about a received signal strength of the particular response an RF channel used by the tag an antenna used by the tag and the like.

In some embodiments a reader transmit power may be adjusted for performing an access operation. The amount by which the transmit power is adjusted may be determined by the modem layer and or received from a higher layer and may be based on a tag response characteristic e.g. power level frequency phase tag type access operation type environmental noise level or any other suitable reader tag environmental parameter. The reader transmit power may be increased for the access operation and decreased for subsequent inventorying and the power levels used for access operations and inventorying may vary depending on the access operation and inventory cycle.

According to an operation one or more inventory commands are received. Before executing the inventory commands the reader may select a subpopulation of tags within its field of view.

According to a next operation a preselect criterion or mask is received by a modem block of the RFID reader. The preselect criterion mask is used to eliminate a portion of the tags before applying another criterion mask and further reducing the subpopulation. The preselect criterion or mask may be received from an AP block a server or a controller application associated with the reader or generated by the modem in response to receiving instructions from one of the listed components.

According to a next operation a post select criterion or mask is received by the modem block from one of the components listed above. The post select criterion may also be used to eliminate a portion of the tags. For example the post select criterion may include the tag EPC matching a list of EPC values in a local database in the reader. The matching tag s may be reported to higher levels such as the AP block while the non matching ones are discarded.

According to a next operation one or more select commands are transmitted to the tags. The select commands may include the received or generated preselect and or post select criteria. Furthermore the select commands may be combined using a Boolean logic operation. Tag responses to the select command s determine which tags meet the criteria. The tags meeting the criteria may be reported to higher levels as mentioned previously for further operations.

According to next optional operation inventory rounds are performed on the selected tags. By reducing the tag population to a smaller portion valuable processing time may be significantly saved.

The operations described in are high level example operations between a reader and tags. More detailed operations illustrating how embodiments may be implemented are described below.

According to a next optional operation a read operation may be performed to retrieve a memory content from the tag.

According to a next decision operation a determination is made whether a preselect criterion applies to the tag. The preselect criterion may be used to eliminate tags by the first layer of the RFID reader without reporting to the higher layers. If the tag does not meet the preselect criterion it is discarded at operation . Processing then returns to operation .

If the tag meets the preselect criterion another read may be performed at a next optional operation .

According to a next operation data associated with a response to the read operation may be generated. The data associated with the response may include a time stamp a received signal power level and the like.

According to a next operation one or more flags may be set depending on whether a post select criterion applies. The flags may be values stored at a memory location state machine values and the like.

According to a next operation the tag may be reported to a higher layer such as the AP block the server the controller application and the like.

According to a next decision operation a determination is made whether the post select criterion applies. If the post select criterion does not apply processing may return to operation . If the post select criterion applies processing may advance to operation .

At operation the modem layer may hand off control of the tag to the higher layer for further operations. As described previously the tag may be held in some embodiments until the determination is made to hand off control of the tag to the higher layer.

According to a next decision operation a determination is made whether the tag control is handed back to the modem layer. If the modem layer receives back the control processing returns to operation for receiving another tag code. Otherwise the modem layer continues to wait for the control to be handed back.

According to an optional operation an optional read is performed on the tag. The optional read operation may be performed on select tags where the reader needs to access tag memory content while inventorying the tag population.

According to a next decision operation a determination is made whether the post select mask matches the tag memory content such as the EPC data from the tag. If there is a match processing continues to operation of process where the tag is reported to a higher layer. Otherwise processing advances to optional operation .

According to next operation the tag memory content is compared to a local database. In one embodiment the local database may be maintained within the AP block.

According to a next decision operation a determination is made whether the tag information is included in the local database. If the tag is not found in the local database processing continues to operation of process where the tag is reported to a higher layer. Otherwise processing advances to optional operation .

According to a next operation a tag access command is received from a higher layer. Tag access commands may include read write lock kill security commands file management commands and or any custom command.

According to a next operation the results of the access operation are reported to the higher layer s . For example confirmation of a successful write operation may be reported to a server controlling the RFID reader.

According to a next decision operation a determination is made whether another access command is to be executed. If the first layer is to execute another command processing returns to operation . Otherwise processing moves to operation of process where flags are set depending on whether post select criterion applies.

In some embodiments an RFID reader may transmit at different power levels depending on the desired operation. For example a reader inventorying a group of tags may transmit at a relatively low power in order to limit the read range and thereby avoid inventorying stray tags. Upon singulating a particular tag the reader may increase its transmit power to perform an access operation on that particular tag. Access operations as described above may involve retrieving information stored at the tag and or causing information stored at the tag to be modified. Higher transmit powers may be desirable for certain access operations e.g. those that involve writing or modifying data on the tag in order to avoid incomplete tag writes and potential corruption of tag data. Since the reader is only communicating with a single tag to perform the access operation using a higher transmit power will not capture stray tags outside the desired read range.

The power levels at which a reader inventories tags and performs access operations may be determined by the reader at the first modem layer and or a higher layer. For example when instructions for an access operation are received from a higher layer the first layer may itself determine the appropriate transmit power level to use. In some embodiments the instructions from the higher layer may include the transmit power level to use for the access operation and or an amount to increase the transmit power level e.g. from the inventorying power level to the accessing power level . The first layer and or higher layers may determine the various transmit power levels to be used for inventorying and or accessing based on one or more reader tag operating parameters and environmental conditions. For example the power levels may be determined based on the power level frequency and or phase of a received tag response. The power levels may also be determined based on the tag type which may be determined during the inventorying singulation process the type of desired access operation the environmental noise level and or any other suitable reader tag or environmental parameter.

While shows only two power levels in some embodiments more transmit power levels may be used. For example instead of all access operations being performed at a single transmit power level e.g. power level different access operations may be performed at different transmit power levels. Similarly inventorying may also occur at different transmit power levels instead of only occurring at a single transmit power level e.g. power level . In some embodiments after performing an access operation e.g. at time instead of decreasing the transmit power back to the power level previously used for inventorying e.g. power level the reader may decrease the transmit power to a different power level. Similarly in some embodiments the reader may not increase its transmit power level for an access operation.

On the other hand if the tag does meet the preselect criterion in operation another read may be performed at optional operation . Subsequently in operation data associated with a response to the read operation or to a tag signal may be generated. The data may include a time stamp a received signal power level frequency phase noise level tag type or any other suitable data.

At operation one or more flags may be set depending on whether a post select criterion applies. The flag s may be values stored in memory state machine values or any other suitable stored value. The tag may be subsequently reported to a higher layer at operation similar to operation in .

At decision operation a determination is made whether the post select criterion applies. If not the process returns to operation . If the post select criterion does apply in step the first layer may hand off control to a higher layer for further operations. The tag may be held in some embodiments until the determination is made to hand off control to a higher layer.

The first layer may then determine a second power level and set the reader transmit power to the second power level at operations and . The first layer may determine the second power level or the amount to adjust the first power level itself or may receive it from a higher layer. The second power level may be determined by the first layer or a higher layer based on a tag response characteristic e.g. power level frequency phase a tag type the desired access operation the environmental noise level and or any other suitable reader tag or environmental parameter.

At operation a determination is made whether control has been handed back to the first layer. If so the process returns to operation where the reader transmit power level may be set back to the first level or to a different level. Otherwise the first layer continues to wait for control to be handed back.

In the above the order of operations is not constrained to what is shown and different orders may be possible. In addition actions within each operation can be modified deleted or new ones added without departing from the scope and spirit of the claimed subject matter. Plus other optional operations and actions can be implemented with these methods as will be inferred from the earlier description.

In this description numerous details have been set forth in order to provide a thorough understanding. In other instances well known features have not been described in detail in order to not obscure unnecessarily the description.

A person skilled in the art will be able to practice the embodiments in view of this description which is to be taken as a whole. The specific embodiments as disclosed and illustrated herein are not to be considered in a limiting sense. Indeed it should be readily apparent to those skilled in the art that what is described herein may be modified in numerous ways. Such ways can include equivalents to what is described herein.

The following claims define certain combinations and sub combinations of elements features steps and or functions which are regarded as novel and non obvious. Additional claims for other combinations and sub combinations may be presented in this or a related document.

