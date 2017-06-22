---

title: Encoding RFID tags of grouped items
abstract: Systems, methods of operation, and software are provided, for encoding RFID tags with which a predefined group of items is tagged. Encoding is by writing applicable Electronic Product Codes (EPCs) to the tags, so as to identify the individual items in the group. A base code can be read from each tag, and the applicable EPC is then written to it.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08810376&OS=08810376&RS=08810376
owner: Impinj, Inc.
number: 08810376
owner_city: Seattle
owner_country: US
publication_date: 20120919
---
This application is a Continuation of U.S. Utility application Ser. No. 12 196 428 filed on Aug. 22 2008 which is hereby incorporated by reference in its entirety.

This application claims priority from of U.S. Utility application Ser. No. 11 472 179 filed on Jun. 20 2006 which is hereby incorporated by reference in its entirety.

This application claims priority from U.S. Provisional Application Ser. No. 61 003 627 filed on Nov. 19 2007 the disclosure of which is hereby incorporated by reference for all purposes.

This application claims priority from U.S. Provisional Application Ser. No. 61 004 275 filed on Nov. 26 2007 the disclosure of which is hereby incorporated by reference for all purposes.

This application claims priority from U.S. Provisional Application Ser. No. 61 005 250 filed on Dec. 4 2007 the disclosure of which is hereby incorporated by reference for all purposes.

Radio Frequency IDentification RFID systems typically include RFID tags and RFID readers. RFID readers are also known as RFID reader writers or RFID interrogators. RFID systems can be used in many ways for locating and identifying objects to which the tags are attached. RFID systems are particularly useful in product related and service related industries for tracking objects being processed inventoried or handled. In such cases an RFID tag is usually attached to an individual item or to its package.

In principle RFID techniques entail using an RFID reader to interrogate one or more RFID tags. The reader transmitting a Radio Frequency RF wave performs the interrogation. The RF wave is typically electromagnetic at least in the far field. The RF wave can also be predominantly electric or magnetic in the near field. The RF wave may encode one or more commands that instruct the tags to perform one or more actions.

A tag that senses the interrogating RF wave responds by transmitting back another RF wave. The tag generates the transmitted back RF wave either originally or by reflecting back a portion of the interrogating RF wave in a process known as backscatter. Backscatter may take place in a number of ways.

The reflected back RF wave may further encode data stored internally in the tag such as a number. The response is demodulated and decoded by the reader which thereby identifies counts or otherwise interacts with the associated item. The decoded data can denote a serial number a price a date a destination other attribute s any combination of attributes and so on. Accordingly when a reader reads a tag code data can be learned about the associated item that hosts the tag and or about the tag itself.

An RFID tag typically includes an antenna system a radio section a power management section and frequently a logical section a memory or both. In earlier RFID tags the power management section included an energy storage device such as a battery. RFID tags with an energy storage device are known as active or semi active tags. Advances in semiconductor technology have miniaturized the electronics so much that an RFID tag can be powered solely by the RF signal it receives. Such RFID tags do not include an energy storage device and are called passive tags.

As mentioned above RFID tags can be used advantageously for carrying identifying data of items that they are attached to or otherwise associated with. A challenge however is that RFID tagging technology is arriving at a time when there already are established processes and machines for large scale quick packaging of such items. Even when such items already have RFID tags on them encoding the corresponding data would ordinarily require an expensive overhaul of such packaging processes and machines or slowing them down substantially.

Briefly the present invention provides systems methods of operation and software for encoding RFID tags with which a predefined group of items is tagged. Encoding is by writing applicable Electronic Product Codes EPCs to the tags so as to identify the individual items in the group. In some embodiments a base code is read from each tag and the applicable EPC is then written to it. Embodiments are especially useful for Item Level Tagging ILT in industries such as pharmaceuticals.

The invention offers the advantage that a number of its embodiments can be accommodated within established packaging processes and machines with little adjustment or disruption.

These and other features and advantages of the invention will be better understood from the specification of the invention which includes the following Detailed Description and accompanying Drawings.

The present invention is now described. While it is disclosed in its preferred form the specific embodiments of the invention as disclosed herein and illustrated in the drawings are not to be considered in a limiting sense. Rather these embodiments are provided so that this disclosure will be thorough and complete and will fully convey the scope of the invention to those skilled in the art. Indeed it should be readily apparent in view of the present description that the invention may be modified in numerous ways. Among other things the present invention may be embodied as devices methods software and so on. Accordingly the present invention may take the form of an entirely hardware embodiment an entirely software embodiment an entirely firmware embodiment or an embodiment combining aspects of the above. This description is therefore not to be taken in a limiting sense.

As has been mentioned the present invention provides systems methods of operation and software for encoding RFID tags of a predefined group of items with applicable EPCs. The invention is now described in more detail.

Reader and tag exchange data via wave and wave . In a session of such an exchange each encodes modulates and transmits data to the other and each receives demodulates and decodes data from the other. The data is modulated onto and demodulated from RF waveforms.

Encoding the data in waveforms can be performed in a number of different ways. For example protocols are devised to communicate in terms of symbols also called RFID symbols. A symbol for communicating can be a delimiter a calibration symbol and so on. Further symbols can be implemented for ultimately exchanging binary data such as 0 and 1 if that is desired. In turn when the waveforms are processed internally by reader and tag they can be equivalently considered and treated as numbers having corresponding values and so on.

RFID reader may communicate with one or more RFID tags in any number of ways. Some such ways are described in protocols. A protocol is a specification that calls for specific manners of signaling between the reader and the tags.

One such protocol is called the Specification for RFID Air Interface EPC Radio Frequency Identity Protocols Class 1 Generation 2 UHF RFID Protocol for Communications at 860 MHz 960 MHz which is also colloquially known as the Gen2 Spec . Version 1.1.0 of the Gen2 Spec has been ratified by EPCglobal which is an organization that maintains a website at http www.epcglobalinc.org at the time this document is initially filed with the USPTO. Version 1.1.0 of the Gen2 Spec is hereby incorporated by reference.

In addition a protocol can be a variant of a stated specification such as the Gen2 Spec for example including fewer or additional commands than the stated specification calls for and so on. In such instances additional commands are sometimes called custom commands.

Tag can be a passive tag or an active or semi active tag i.e. having its own power source. Where tag is a passive tag it is powered from wave .

Tag is formed on a substantially planar inlay which can be made in many ways known in the art. Tag includes an electrical circuit which is preferably implemented in an integrated circuit IC . IC is arranged on inlay .

Tag also includes an antenna for exchanging wireless signals with its environment. The antenna is usually flat and attached to inlay . IC is electrically coupled to the antenna via suitable antenna ports not shown in .

The antenna may be made in a number of ways as is well known in the art. In the example of the antenna is made from two distinct antenna segments which are shown here forming a dipole. Many other embodiments are possible using any number of antenna segments.

In some embodiments an antenna can be made with even a single segment. Different points of the segment can be coupled to one or more of the antenna ports of IC . For example the antenna can form a single loop with its ends coupled to the ports. It should be remembered that when the single segment has more complex shapes even a single segment could behave like multiple segments at the frequencies of RFID wireless communication.

In operation a signal is received by the antenna and communicated to IC . IC both harvests power and responds if appropriate based on the incoming signal and its internal state. In order to respond by replying IC modulates the reflectance of the antenna which generates the backscatter from a wave transmitted by the reader. Coupling together and uncoupling the antenna ports of IC can modulate the reflectance as can a variety of other means.

In the embodiment of antenna segments are separate from IC . In other embodiments antenna segments may alternately be formed on IC and so on.

A driver can send to its respective antenna a driving signal that is in the RF range which is why connector is typically but not necessarily a coaxial cable. The driving signal causes antenna to transmit an RF wave which is analogous to RF wave of . In addition RF wave can be backscattered from the RFID tags analogous to RF wave of . Backscattered RF wave is received by an antenna and ultimately becomes a signal sensed by unit .

Unit also has other components such as hardware and or software and or firmware which are described in more detail later in this document. Components control drivers and as such cause RF wave to be transmitted and the sensed backscattered RF wave to be interpreted. Optionally and preferably there is a communication link to other equipment such as computers and the like for remote operation of system .

Local block is responsible for communicating with the tags. Local block includes a block of an antenna and a driver of the antenna for communicating with the tags. Some readers like that shown in local block contain a single antenna and driver. Some readers contain multiple antennas and drivers and a method to switch signals among them including sometimes using different antennas for transmitting and for receiving. And some readers contain multiple antennas and drivers that can operate simultaneously. A demodulator decoder block demodulates and decodes backscattered waves received from the tags via antenna block . Modulator encoder block encodes and modulates an RF wave that is to be transmitted to the tags via antenna block .

Local block additionally includes an optional local processor . Processor may be implemented in any number of ways known in the art. Such ways include by way of examples and not of limitation digital and or analog processors such as microprocessors and digital signal processors DSPs controllers such as microcontrollers software running in a machine such as a general purpose computer programmable circuits such as Field Programmable Gate Arrays FPGAs Field Programmable Analog Arrays FPAAs Programmable Logic Devices PLDs Application Specific Integrated Circuits ASIC any combination of one or more of these and so on. In some cases some or all of the decoding function in block the encoding function in block or both may be performed instead by processor .

Local block additionally includes an optional local memory . Memory may be implemented in any number of ways known in the art. Such ways include by way of examples and not of limitation nonvolatile memories NVM read only memories ROM random access memories RAM any combination of one or more of these and so on. These can be implemented separately from processor or in a single chip with or without other components. Memory if provided can store programs for processor to run if needed.

In some embodiments memory stores data read from tags or data to be written to tags such as Electronic Product Codes EPCs Tag Identifiers TIDs and other data. Memory can also include reference data that is to be compared to the EPC codes instructions and or rules for how to encode commands for the tags modes for controlling antenna and so on. In some of these embodiments local memory is provided as a database.

Some components of local block typically treat the data as analog such as the antenna driver block . Other components such as memory typically treat the data as digital. At some point there is a conversion between analog and digital. Based on where this conversion occurs a whole reader may be characterized as analog or digital but most readers contain a mix of analog and digital functionality.

If remote components are indeed provided they are coupled to local block via an electronic communications network . Network can be a Local Area Network LAN a Metropolitan Area Network MAN a Wide Area Network WAN a network of networks such as the internet or a mere local communication link such as a USB PCI and so on. In turn local block then includes a local network connection for communicating with network .

There can be one or more remote component s . If more than one they can be located at the same location or in different locations. They can access each other and local block via network or via other similar networks and so on. Accordingly remote component s can use respective remote network connections. Only one such remote network connection is shown which is similar to local network connection etc.

Remote component s can also include a remote processor . Processor can be made in any way known in the art such as was described with reference to local processor .

Remote component s can also include a remote memory . Memory can be made in any way known in the art such as was described with reference to local memory . Memory may include a local database and a different database of a Standards Organization such as one that can reference EPCs.

Of the above described elements it is advantageous to consider a combination of these components designated as operational processing block . Block includes those components that are provided of the following local processor remote processor local network connection remote network connection and by extension an applicable portion of network that links connection with connection . The portion can be dynamically changeable etc. In addition block can receive and decode RF waves received via antenna and cause antenna to transmit RF waves according to what it has processed.

Block includes either local processor or remote processor or both. If both are provided remote processor can be made such that it operates in a way complementary with that of local processor . In fact the two can cooperate. It will be appreciated that block as defined this way is in communication with both local memory and remote memory if both are present.

Accordingly block is location agnostic in that its functions can be implemented either by local processor or by remote processor or by a combination of both. Some of these functions are preferably implemented by local processor and some by remote processor . Block accesses local memory or remote memory or both for storing and or retrieving data.

Reader system operates by block generating communications for RFID tags. These communications are ultimately transmitted by antenna block with modulator encoder block encoding and modulating the information on an RF wave. Then data is received from the tags via antenna block demodulated and decoded by demodulator decoder block and processed by processing block .

RFID reader system includes one or more antennas and an RF Front End for interfacing with antenna s . These can be made as described above. In addition Front End typically includes analog components.

System also includes a Signal Processing module . In this embodiment module exchanges waveforms with Front End such as I and Q waveform pairs. In some embodiments signal processing module is implemented by itself in an FPGA.

System also includes a Physical Driver module which is also known as Data Link. In this embodiment module exchanges bits with module . Data Link can be the stage associated with framing of data. In one embodiment module is implemented by a Digital Signal Processor.

System additionally includes a Media Access Control module which is also known as MAC layer. In this embodiment module exchanges packets of bits with module . MAC layer can be the stage for making decisions for sharing the medium of wireless communication which in this case is the air interface. Sharing can be between reader system and tags or between system with another reader or between tags or a combination. In one embodiment module is implemented by a Digital Signal Processor.

System moreover includes an Application Programming Interface module which is also known as API Modem API and MAPI. In some embodiments module is itself an interface for a user.

All of these functionalities can be supported by one or more processors. One of these processors can be considered a host processor. Such a processor would for example exchange signals with MAC layer via module . In some embodiments the processor can include applications for system . In some embodiments the processor is not considered as a separate module but one that includes some of the above mentioned modules of system .

A user interface may be coupled to API . User interface can be manual automatic or both. It can be supported by a separate processor than the above mentioned processor or implemented on it.

It will be observed that the modules of system form something of a chain. Adjacent modules in the chain can be coupled by the appropriate instrumentalities for exchanging signals. These instrumentalities include conductors buses interfaces and so on. These instrumentalities can be local e.g. to connect modules that are physically close to each other or over a network for remote communication.

The chain is used in opposite directions for receiving and transmitting. In a receiving mode wireless waves are received by antenna s as signals which are in turn processed successively by the various modules in the chain. Processing can terminate in any one of the modules. In a transmitting mode initiation can be in any one of these modules. Ultimately signals are routed internally for antenna s to transmit as wireless waves.

The architecture of system is presented for purposes of explanation and not of limitation. Its particular subdivision into modules need not be followed for creating embodiments according to the invention. Furthermore the features of the invention can be performed either within a single one of the modules or by a combination of them.

Elements include an RFID reader unit with a connected antenna . RFID reader unit can be coupled to a computer which may be connected to an enterprise database . These can work as described above for RFID reader systems and further in view of the needs of the host packaging system. In addition final EPCs can be stored in RFID reader unit or computer or enterprise database for encoding to tags .

Antenna defines a reading zone . This can be accomplished by the orientation of the antenna. Reading zone can be further confined by shielding and so on.

In the example of the host system includes a delivery system for group . Delivery system can deliver group to reading zone . Alternately delivery can be by a human.

In addition the host packaging system provides a main path for conveyance of group out of reading zone . Encoding operations can take place according to embodiments when group is within reading zone at least in part. In addition sensors can optionally detect when group is delivered into the reading zone and when group has been conveyed out of it. If such sensors are included reader can be triggered to operate responsive to signals from such sensors.

Components include an RFID encoding system that communicates with a host system and which in turn communicates with enterprise database . These can reside in suitable ones of the components of .

RFID tag includes a memory . Memory can include an EPC field where EPC stands for Electronic Product Code which can be the primary code for identifying an item via its RFID tag. This primary code is the first stored and specific code that a tag backscatters after it has been singulated. For tags that are consistent with the Gen2 Spec v.1.1.0 EPC field can be defined consistently with how an EPC Memory is defined in the Gen2 Spec v.1.1.0.

As a first example other field can be where a unique tag identifier code is stored which identifies a manufacturer of a circuit of the first tag. In the parlance of the Gen2 Spec v.1.1.0 such a code can be the TID code.

As a second example other field can be where more general data is stored in ways determined by the user of the tag. This is often called user memory. For some implementations this other memory can be a user memory defined consistently with how a User Memory is defined in the Gen2 Spec v.1.1.0.

According to a comment B an ending set B of identifiers is provided for the same item after encoding. Set B includes RFID tag after a portion of its memory has been written. In addition identification index may or may not have stayed the same.

In starting set A a base code is written in other field . Base code is planned by the user. Base code can be made from binary bits.

In ending set B base code can remain written in other field or be erased from there. In addition a final EPC has been written in EPC field . Final EPC can be derived in a number of ways. In some embodiments the final EPC is the same as base code . In other embodiments the final EPC is derived from base code . In yet other embodiments the final EPC is looked up from base code . Looking up can be from a suitable table in database which can reside in a suitable instrumentality such as reader unit computer or enterprise database . As will be appreciated later identification index may help create the table in database .

Moreover in starting set A optionally an initial EPC can be stored in EPC field . As can be seen from ending set B final EPC is written over initial EPC .

RFID tag includes a memory which can be similar to memory . Memory can include an EPC field which can be similar to EPC field . Memory can further optionally include additional fields. One such other field is shown which can be similar to other field .

According to a comment B an ending set B of identifiers is provided for the same item after encoding. Set B includes RFID tag after a portion of its memory has been written. In addition identification index may or may not have stayed the same.

In starting set A a base code is written in EPC field . In ending set B a final EPC has been written in EPC field . Accordingly base code is overwritten by final EPC .

There are advantages and disadvantages of each of the data schemes of and . Some will be discerned by a person having ordinary skill in the art in view of the present description and also in view of the needs and available capabilities in the particular implementation.

The invention also includes methods. Some are methods of operation of an RFID reader or RFID reader system. Others are methods for controlling an RFID reader or RFID reader system. For example computer and or RFID reader can operate according to methods of the invention. For another example host system and or RFID encoding system can operate according to methods of the invention.

These methods can be implemented in any number of ways including by the structures described in this document. One such way is by machine operations of devices of the type described in this document.

Another optional way is for one or more of the individual operations of the methods to be performed in conjunction with one or more human operators performing some of them. These human operators need not be collocated with each other but each can be only with a machine that performs a portion of the method.

The methods of flowchart can be used by an RFID reader system component to write final EPCs to RFID tags of a predefined group of tagged items such as group . Preferably this takes place when the group has been received into a reading zone defined by an antenna coupled to the RFID reader system component. Some of the operations of flowchart can take place while the group is in the reading zone and others while the group is outside of it. To assist in the illustration flowchart is also shown with an icon for a reading zone within which there are some of the operations of flowchart but not others. The coverage of icon in is only for example not for limitation.

At an optional operation base codes of the respective items in the group become associated with final Electronic Product Codes EPCs . This can take place before the group is received into a reading zone . A process for that is described later in this document. When performed the association is stored in a suitable memory if necessary.

At optional next operation the group is received into the reading zone. This can take place by delivery system or manually and so on.

At next operation a first one of the tags is singulated from the other tags. This can be performed by a reader in accordance to a tag inventorying algorithm. At this point the reader knows that it is talking only to that one tag while the others remain suspended.

At next operation a base code is read from the singulated tag. This can be performed in any number of ways depending on which data scheme is used for storing the base code. Two sample data schemes have been described with reference to and .

At next operation one of the final EPCs is written to an EPC memory of the singulated first tag. The final EPC is one that is associated with the base code read at operation . Association can be as described above and or as established at operation . In some embodiments the EPC memory of operation is EPC memory field or . In some embodiments this EPC memory is defined consistently with how an EPC Memory is defined in the Gen2 Spec v.1.1.0.

In conjunction with writing other operations may be performed. For example the written final EPC can also be locked in a memory of the first tag. The locking can be reversible or irreversible and so on.

At optional next operation it can be confirmed that the final EPC has been written successfully to the first tag. If not then a number of embodiments can be implemented. For a first example according to operation there can be a retry i.e. another attempt to write the final EPC via operation . For a second example according to operation an error flag can be set and the process can continue. In embodiments where a group RFID tag is provided with the group the error flag can be set as an error indication in data of the group RFID tag. For example in group tag can be encoded separately from the items. In addition it can have such an error indication so that the error can be fixed later.

At optional next operation it can be inquired whether there are any more tags for singulation. If so the remaining tags of the remaining items in the group are successively singulated and final EPCs can be written to their memories when each is singulated.

At optional next operation it can be inquired whether a number of the singulated tags disagrees with a preset group number which is the number of expected tags. In embodiments where a group RFID tag is provided with the group then the preset group number is determined from data of the group RFID tag.

If the number of the singulated tags disagrees with the preset group number then a number of embodiments can be implemented. For a first example according to operation there can be a retry to go through the tags.

For a second example according to operation an error flag can be set. In embodiments where a group RFID tag is provided with the group the error flag can be set as an error indication in data of the group RFID tag. This error indication can be the same or different as that set from operation .

At optional next operation it is inquired whether an error flag is set such as one of the ones described above. In embodiments where a group RFID tag is provided with the group then the inquiry can be from data of the group RFID tag.

If the flag is not set then according to operation the group proceeds along a main path. An example is now described.

Returning to if at operation an error flag is set then as per operation there can be a number of embodiments. In a first set of options the group can be slowed down. For example it can be conveyed at a chosen point in the reading zone at a first speed if the error flag is not set and at a second speed different from the first speed if the error flag is set. The second speed can be slower than the first speed or zero or negative i.e. in an opposite direction than the first speed. A second set of options is now described.

In a number of embodiments for a single group a number of base codes may be provided along with a number of associated final EPCs. This was first hinted at in operation of and in a table in database of . Operations are now described for how base codes can become associated with final EPCs.

In principle an item can be identified before it is grouped with the others. A challenge is that grouping makes it difficult to identify the item again. The challenge is harder if there are many items in the group and the ones near the center are not visible by a line of sight operation. The challenge is even harder if the entire group is placed in an opaque container in which none of the items are visible.

In embodiments of the invention an additional data carrier is used for at least some of the items. An example is now described.

Moreover sample item has an additional data carrier which may be used for identifying item before it is grouped with the others. Data carrier may be implemented in any way known in the art for carrying a machine readable identification index which is known according to association A3. As will be seen below data carrier can be implemented in many different ways. Accordingly from associations A3 and A1 first base code becomes associated with identification index with reference to item .

In some embodiments identification index is associated with intended final EPC according to association A4. Association A4 via associations A3 and A1 can establish association A5 which can be carried by database of . In association A5 base code becomes associated with final EPC with reference to item by the knowledge of the other associations. Association A5 can therefore be used for the writing or encoding of final EPC . Other arrangements of such associations are also possible.

Identification index can be associated with intended final EPC in any number of ways. For example final EPC can be the same as identification index . Or final EPC can be looked up from identification index . Alternately final EPC can be derived from identification index and so on.

RFID tag includes a memory into which a base code is stored. Base code can be stored in any field of memory as per the above.

According to a comment B an ending set B of identifiers is provided for the same item after encoding. Set B includes RFID tag whose memory has an EPC field that contains final EPC . Final EPC has been learned for the encoding from database which stores association A5 of . In ending set B data carrier and its stored identification index may be the same or different.

At operation an identification index is input for one of the tagged items. As will be described below this can be performed in a number of ways and at different times also in view of the nature of the data carrier and the nature of the packaging system.

At next operation a base code becomes associated with the input identification index for that tag as corresponding to that item per associations A3 and A1 of . This can be performed in a number of ways. For example the base code can become associated with the identification index by reading the base code from the tag or by writing the base code to the tag in conjunction with inputting the identification index of .

A result of operation can be that the base code becomes associated with its corresponding first final EPC for the item per association A4. As such the first final EPC is ready for the writing of operation .

At next operation it is inquired whether there are more items in the group. Flowchart can be repeated for each of them.

As mentioned above operation can be performed at different times for example while the whole group of items has been received into the reading zone or before. It can also be performed before the item becomes grouped with the others concurrently or after and so on.

A number of embodiments are possible for the data carrier and the identification index. In some embodiments the data carrier is a second RFID tag of the first item and the identification index can be stored in the second RFID tag. In operation the identification index can be input from a database. Plus for operation the first base code can be associated with the identification index as above. In conjunction the identification index can be input from the second RFID tag or written to it.

In other embodiments the data carrier stores the identification index in a manner that is visually readable by a line of sight reader. This can be implemented in any number of ways. Such ways include one dimensional bar codes and two dimensional bar codes which are readable by the appropriate bar code scanner. Another such way includes a label that is readable by humans and also by an Optical Character Recognition OCR scanner. In operation the identification index can be input from a database. Plus for operation the first base code can be associated with the identification index as above. In conjunction the identification index can be read from the data carrier or written to it. Alternately the data carrier can then be attached to the item.

Diagram includes elements of an RFID tag encoding station which are similar to those of . More particularly elements include a computer like computer a reader unit like unit and an antenna like antenna which defined a reading zone like reading zone . Associations that are looked up can be stored in a database or computer or reader unit .

A bar code reader is coupled to database or computer . A second RFID reader is also coupled to database or computer . An item has attached on it an RFID tag and a bar code label which serves as data carrier in this example.

According to an operation B1 bar code reader reads a bar code from bar code label . In addition RFID reader reads a base code RFID tag according to operation B2. Operations B1 and B2 are coordinated so as to associate with certainty the read bar code with the input base code. The associated numbers are input in database or computer .

Further according to an operation B3 item is placed in a container so as to form a group with other tagged items . Container also includes a group RFID tag .

According to a next operation B4 container is then sealed. According to a next operation B5 container is then delivered to reading zone by a delivery system not shown . According to a next operation B6 a final EPC is encoded on RFID tag and preferably also on the tags of all items . According to a next operation B7 container is then conveyed away from reading zone .

The actions in operations C1 through C7 are spelled out. In operation C2 it is a printer that generates the 2D bar code label which is then attached to the item. The remaining operations are as per the above.

The invention additionally includes programs and methods of operation of the programs. A program is generally defined as a group of steps or operations leading to a desired result due to the nature of the elements in the steps and their sequence. A program is usually advantageously implemented as a sequence of steps or operations for a processor such as the structures described above.

Performing the steps instructions or operations of a program requires manipulation of physical quantities. Usually though not necessarily these quantities may be transferred combined compared and otherwise manipulated or processed according to the steps or instructions and they may also be stored in a computer readable medium. These quantities include for example electrical magnetic and electromagnetic charges or particles states of matter and in the more general case can include the states of any physical devices or elements. It is convenient at times principally for reasons of common usage to refer to information represented by the states of these quantities as bits data bits samples values symbols characters terms numbers or the like. It should be borne in mind however that all of these and similar terms are associated with the appropriate physical quantities and that these terms are merely convenient labels applied to these physical quantities individually or in groups.

The invention furthermore includes storage media. Such media individually or in combination with others have stored thereon instructions of a program made according to the invention. A storage medium according to the invention is a computer readable medium such as a memory and is read by a processor of the type mentioned above. If a memory it can be implemented in a number of ways such as Read Only Memory ROM Random Access Memory RAM etc. some of which are volatile and some non volatile.

Even though it is said that the program may be stored in a computer readable medium it should be clear to a person skilled in the art that it need not be a single memory or even a single machine. Various portions modules or features of it may reside in separate memories or even separate machines. The separate machines may be connected directly or through a network such as a local access network LAN or a global network such as the Internet.

Often for the sake of convenience only it is desirable to implement and describe a program as software. The software can be unitary or thought in terms of various interconnected distinct software modules.

This detailed description is presented largely in terms of flowcharts algorithms and symbolic representations of operations on data bits on and or within at least one medium that allows computational operations such as a computer with memory. Indeed such descriptions and representations are the type of convenient labels used by those skilled in programming and or the data processing arts to effectively convey the substance of their work to others skilled in the art. A person skilled in the art of programming may use these descriptions to readily generate specific instructions for implementing a program according to the present invention.

Embodiments of an RFID reader system can be implemented as hardware software firmware or any combination. It is advantageous to consider such a system as subdivided into components or modules. A person skilled in the art will recognize that some of these components or modules can be implemented as hardware some as software some as firmware and some as a combination. An example of such a subdivision is now described.

An economy is achieved in the present document in that a single set of flowcharts is used to describe methods in and of themselves along with operations of hardware and or software and or firmware. This is regardless of how each element is implemented.

Numerous details have been set forth in this description which is to be taken as a whole to provide a more thorough understanding of the invention. In other instances well known features have not been described in detail so as to not obscure unnecessarily the invention.

The invention includes combinations and subcombinations of the various elements features functions and or properties disclosed herein. The following claims define certain combinations and subcombinations which are regarded as novel and non obvious. Additional claims for other combinations and subcombinations of features functions elements and or properties may be presented in this or a related document.

