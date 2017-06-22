---

title: Playback apparatus for performing application-synchronized playback
abstract: A playback apparatus includes a package management unit operable to generate package information by merging files recorded on a first recording medium and a second recording medium, in accordance with merge management information. A selection unit is operable to detect a plurality of playable titles from the package information and select one of the detected titles as a current title. A processing unit is operable to execute an application specified in the current title and that is included in the package information. A playback control engine is operable to control playback of a digital stream in the current title and that is included in the package information. Status registers each store a parameter relating to a playback status of the digital stream, and backup registers each save one of the status registers.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08660406&OS=08660406&RS=08660406
owner: Panasonic Corporation
number: 08660406
owner_city: Osaka
owner_country: JP
publication_date: 20121120
---
The present application is a continuation of co pending U.S. patent application Ser. No. 12 609 109 filed on Oct. 30 2009 which is a continuation of U.S. patent application Ser. No. 10 596 109 filed on May 31 2006 and now U.S. Pat. No. 7 616 864 issued on Nov. 10 2009 which is a National Stage of International Patent Application No. PCT JP05 13785 filed Jul. 21 2005 which claims priority under 35 U.S.C. 119 of Japanese Application No. 2004 214916 filed on Jul. 22 2004 Japanese Application No. 2004 268512 filed on Sep. 15 2004 Japanese Application No. 2004 293043 filed on Oct. 5 2004 Japanese Application No. 2004 369701 filed on Dec. 21 2004 and Japanese Application No. 2005 099410 filed on Mar. 30 2005 the disclosures of which are expressly incorporated by reference herein in their entireties.

The present invention belongs to the technical field of digital streams and application synchronized playback.

Application synchronized playback is technology for playing digital streams while at the same time running Java registered trademark applications in a playback apparatus or the like for playing video and belongs to a technical field that will attract a great deal of attention in consumer device manufacturing from now on. Applications and digital streams for synchronizing are associated with one another in units of playback called titles . The following describes a conventional playback apparatus. A conventional playback apparatus is constituted from a virtual filesystem unit a module manager a playback unit and a platform unit.

The virtual filesystem unit manages a plurality of recording media accessible by the playback apparatus such as optical recording media e.g. DVD ROM BD ROM the latter of which is described later by way of example and magnetic recording media e.g. hard disk and generates package information integrally showing the recorded content of these recording media.

Each piece of package information called a virtual package is submitted in the playback execution of digital streams and application programs hereinafter simply applications recorded on these recording media just as if they were actually recorded in a single package.

The playback unit plays a digital stream i.e. recorded on an optical or magnetic recording medium constituting the current title from digital streams shown by the package information.

The platform unit runs an application i.e. recorded on an optical or magnetic recording medium constituting the current title from applications shown by the package information.

According to the above structure digital streams and applications recorded on different recording media such as BD ROM and hard disk can be treated as a single virtual package and the playback apparatus is able to realize playback controls in units of titles.

Titles in the above structure target not only digital streams recorded on BD ROM for playback but also digital streams recorded on hard disk. Since hard disk is a rewritable recording medium the compositional elements of a title may possibly be replaced partway through playback in cases such as when package information is newly generated using a newly acquired digital stream.

Such a replacement is largely thought to bring about situations that are difficult to restore such as video blackout during playback resulting from abnormal operation of the playback unit.

The replacement of the playback object partway through playback can be anticipated if the playback unit in the playback apparatus sequentially checks the sameness of elements such as streams and playback control information targeted for playback. However given the diverse types of information that require checking this places a great burden on the playback unit.

To be absolutely sure of the device s stable operation it is desirable to reboot the device itself when there has been a change in the recorded content on hard disk as you would when installing software. However given that rebooting the device takes anywhere from a few seconds to a few minutes processing time this is not something that the user undertakes lightly.

An object of the present invention is to provide a playback apparatus capable of realizing stable playback even if there is a change in the playback object.

To resolve the above problems the present invention is a playback apparatus that plays a digital stream in conjunction with an application and includes a package management unit operable to generate package information by merging files recorded on a first recording medium and a second recording medium in accordance with merge management information and a selection unit operable to detect a plurality of playable titles from the package information and select one of the detected titles as a current title. After the application requests the package management unit to update the merge management information by specifying new merge management information the package management unit changes a file referenced from the newly specified merge management information to read only before updating the package information and at a point at which digital stream playback stops due to a current title change by the selection unit the package management unit generates new package information by combining files recorded on the first and second recording media in accordance with the newly specified merge management information.

The present invention as a result of having the above structure guarantees that in the case of an application requesting the package management unit to update the merge management information by specifying new merge management information the content of a file referenced from the newly specified merge management information is not altered from the time the update request is made until the when the current title is changed since the package management unit sets the file referenced from the newly specified merge management information to read only before updating the package information. Also by updating package information at the point at which digital stream playback is stopped due to a current title change abnormal operation of the playback apparatus is not brought about even when for instance the digital stream or application targeted for playback execution is replaced as a result of updating.

Thus the breadth of expression with movie works is expanded since playback controls can be realized by dynamically merging files recorded on both first and second recording media while securing the stable operation of the playback apparatus.

Here the package management unit may be configured to update package information if information in a permission tag of an application that requested the updating indicates that the application has been assigned the right to update the package information and to reject the update request and perform exception processing if this information indicates that the right to update has not been assigned.

This structure enables the updating of package information requested by unauthorized applications to be prevented.

The following describes embodiments of recording media pertaining to the present invention. Firstly a form of use out of the forms of the implementation of a playback apparatus pertaining to the present invention is described. shows an exemplary form of use of a playback apparatus pertaining to the present invention. In a playback apparatus pertaining to the present invention is a playback apparatus . Playback apparatus is submitted for use in supplying movie works in a home theater system composed of a playback apparatus a remote control and a television for example.

An exemplary form of use of a playback apparatus pertaining to the present invention is as described above. Described next is a recording medium targeted for playback by a playback apparatus pertaining to the present invention. In the given example the recording medium played by a playback apparatus pertaining to the present invention is a BD ROM optical recording medium . shows an internal structure of BD ROM .

BD ROM is shown at the 4th tier in while a track on the BD ROM is shown at the 3rd tier. The track depicted in results from a track spiraling from the inner circumference to the outer circumference of the BD ROM having been drawn out to the sides. This track consists of a lead in area a volume area and a lead out area. The volume area in has a layered structure made up of a physical layer a filesystem layer and an application layer. Expressing the application format of the BD ROM using a directory structure gives the 1st tier in . A BDMV directory is placed under a ROOT directory at the 1st tier in the BD ROM.

An INDEX.BDMV file is disposed in the BDMV directory and under the BDMV directory exist five subdirectories known as a PLAYLIST directory a CLIPINF directory a STREAM directory a BDJA directory and a BDBJ directory.

The STREAM directory stores a file forming the main digital stream the extension m2ts being assigned to this file 00001.m2ts .

The file with the extension m2ts 00001.m2ts is described firstly. systematically shows how a file with the extension m2ts is structured. This file stores an AVClip. The AVClip middle tier is constituted by multiplexing TS packets resulting from the conversion of a video stream composed of a plurality of video frames pictures pj pj pj and an audio stream composed of a plurality of audio frames upper 1tier firstly to PES packets upper 2tier and then to TS packets upper 3tier and the conversion of a subtitle presentation graphics P graphics or PG stream lower 1tier and a dialogue interactive graphics I graphics or IG stream lower 1tier to TS packets lower 3tier in the same manner.

Apart from the AVClip obtained through multiplexing as shown in there also exist AVClips that do not result from multiplexing. These are called SubClips and include AVClips constituting an audio stream a graphics stream or a text subtitle stream TextST stream etc.

The file with the extension clpi 00001. clpi is a piece of clip information corresponding to an AVClip. Clip information being management information contains an EP map showing the head location of a GOP and information such as the encoding format frame rate bit rate and resolution etc. of streams in the AVClip.

The file with the extension mpls 00001. mpls stores PlayList PL information. PL information defines a playlist by referring to AVClips. shows the structure of PL information which as shown on the left side of the diagram is constituted from MainPath information PLMark information and SubPath information.

MainPath information MainPath is composed of PlayItem information PlayItem as indicated by the arrows mp. A playitem is a playback interval defined by specifying an In time and an Out time on one or more AVClip time axes. A playlist composed of a plurality of playback intervals is defined by the placement of plural pieces of PlayItem information. The arrows mp in shows a close up of the internal structure of PlayItem information. As shown in PlayItem information is composed of an In time an Out time and a Clip Information file name showing a corresponding AVClip. shows the relation between an AVClip and a PL. The 1tier shows the time axis of the AVClip while the 2tier shows the time axis of the PL. The PL information includes three pieces of PlayItem information PlayItems 1 3 with three playback intervals being defined by the In times and Out times of PlayItems 1 2 and 3. A different time axis to the AVClip is defined when these playback intervals are arranged in line. This is the PL time axis shown at the 2tier. Defining a different time axis to the AVClip is thus enabled by the definitions in the PlayItem information.

As a rule one AVClip is specified at anyone time though batch specification of a plurality of AVClips is also possible. Batch specification of AVClips is performed using Clip Information file names in PlayItem information. shows the batch specification of AVClips using four Clip Information file names. The 1to 4tiers in the diagram show four AVClip time axes time axes of AVClips 1 4 while the 5tiers show the PL time axis. Four time axes are specified with these four Clip Information file names included in PlayItem information. This allows four alternatively playable playback intervals to be defined by In times and Out times. As a result an interval composed of plural piece of switchable angle video so called multi angle interval is defined on the PL time axis.

PLMark information PLMark specifies an arbitrary interval on a PL time axis as a chapter. shows the internal structure of PLMark information which includes a ref to PlayItem Id and a Mark time stamp as indicated by the arrows pmt. shows the definition of chapters using PLMarks. The 1tier in shows the AVClip time axis while the 2tier shows the PL time axis. The arrows pk and pk in show the specification of a playitem ref to PlayItem Id and a point in time Mark time stamp in PLMarks. Three chapters Chapters 1 3 are defined on the PL time axis as a result of these specifications. This completes description of PLMarks.

SubPath information SubPath defines one or more playback intervals by specifying an In time and an Out time on a SubClip time axis and has the internal structure shown in . SubPath information is composed of SubPlayItem information SubPlayItem as indicated by the arrows sh. In the close up marked by the arrows sh SubPlayItem information is composed of a Clip Information file name an In time an Out time a Sync PlayItem Id and a Sync Start PTS of PlayItem. In times and Out times on the SubClip time axis are specified using Clip information file name In time and Out time included in SubPlayItem information. Sync PlayItem Id and Sync Start PTS of PlayItem are for synchronizing playback intervals on the SubClip time axis with the PL time axis. This allows processing on both the SubClip time axis and the PL time axis to proceed in sync with one another.

A feature of PL information in BD ROM is that it makes possible the definition of multi angle intervals that enable AVClips to be switched and sync intervals that enable AVClips and SubClips to be synchronized. Clip information and PL information are classified as static scenarios .

The following describes dynamic scenarios . Here dynamic refers to the fact that the content of playback controls changes due to user key events and status changes in playback apparatus etc. With BD ROM playback controls can be described using the same description as Java applications. That is with BD ROM Java applications act as dynamic scenarios.

The following describes Java applications. A Java application is composed of a one or more xlet programs loaded ID in a heap area also called working memory of a virtual machine. An application is constituted from the xlet programs loaded in working memory as well as data. The Java application structure is as described above.

An actual Java application is the Java archive file 00001.jar stored in the BDJA directory under the BDMV directory in . Java archive files are described below with reference to .

The Java archive file 00001.jar in is a collection of one or more class files and data files etc. shows programs and data collected in the archive file. The data in is a plurality of files collected by a Java archiver and arranged into the directory structure shown within the frame. This directory structure consists of a Root directory a Java directory and an image directory with a common.pkg file class files aaa.class bbb.class and a menu.jpg file being placed within respective directories. The Java archive file is the result of the Java archiver having collected these files together. The class files and data are expanded when read from BD ROM to a cache and treated in the cache as a plurality of files existing in directories. The five digit numerical value 00001 in the filename of the Java archive file shows the identifier ID of the Java archive file and the BD J object uses this value to refer to the Java archive file. By referring to this numerical value in the filename when a Java archive file has been read to the cache it is possible to extract data as well as programs constituting arbitrary Java applications.

The class files aaa.class bbb.class in correspond to the above xlet programs. Playback procedures in an operating mode BD J supported by the Java platform are defined using xlet programs i.e. instances of these class files. An xlet program is a Java program capable of using a Java media framework JMF interface and performs processing based on key events in accordance with JMF etc.

Furthermore xlet programs can also execute procedures for accessing websites and downloading contents. This enables playback of original works created by mixing downloaded contents with playlists.

The class file of an xlet program is described next. shows the internal structure of a class file. As shown in this class file similar to a normal class file is composed of a constant pool an interface and methods 1 2 3 . . . n. The methods in a class file include those EventListeners that are triggered by preregistered key events and those for calling Application Programming Interface API functions in playback apparatus . Computation procedures and the like in these methods are described by employing local variables allocated to a given method and arguments occurring when the method is called. A Java archive file is as described above.

The file with the extension bdbj is described next. This file 00001.bdbj stores a BD J object. A BD J object is information defining a title by associating AVClips defined in PL information with applications. shows the internal structure of a BD J object. The BD J object shows an application management table and a PL information reference value. The application management table shows Java applications whose lifecycle is the title defined by the BD J object through enumerating the ID of individual Java applications application IDs and the IDs of the Java archive files belonging to particular applications. In other words each application is constituted from one or more Java archive files.

INDEX.BDMV is management information relating to the entire BD ROM. This file contains information such as organization IDs identifying the providers of movie works and disc IDs allocated to individual BD ROMs provided by the providers. A disc is uniquely recognized in the playback apparatus by firstly reading INDEX.BDMV after the disc has been loaded. INDEX.BDMV may additionally include a table that maps a plurality of playable titles in BD ROM to BD J objects defining individual titles. The following describes the types of titles recordable to BD ROM which include a FirstPlayTitle a Top menuTitle and Titles 1 3.

FirstPlayTitle is charged with playing a dynamic trademark of a BD ROM when the BD ROM is loaded before doing anything else. FirstPlayTitle thus realizes the practice of playing a dynamic trademark symbolizing the creator and or distributor of a movie work when a BD ROM is loaded.

Top menuTitle is composed of AVClips and applications for playing the menu positioned at the very top of the menu hierarchy in a BD ROM.

In other words INDEX.BDMV shows the correspondence of FirstPlayTitle Top menuTitle and Titles 1 3 with individual BD J objects.

BD ROM is not the only recording media targeted by a playback apparatus pertaining to the present invention.

A hard disk local storage integral to the playback apparatus is also targeted during playback. The following describes data recorded in local storage.

Providing directories that correspond to BD ROMs in directories corresponding to specific providers allows downloaded data relating to individual BD ROMs to be stored separately. Under these subdirectories are stored PL information clip information and AVClips similar to what is stored on BD ROM. There also additionally exist a Java archive file a BD J object a merge management information file and a signature information file.

In comparison to PL information on a BD ROM which refers only to AVClips on the BD ROM PL information in local storage includes information that refers to both AVClips on BD ROM and in local storage that is PL information newly added as a virtual package a specific example of which is PL INFO 2 in .

Here PL information in local storage is constituted from four pieces of PlayItem information PlayItem information 1 4 . This PL information can in the case of the head piece PlayItem information 1 referring to clip information on BD ROM and the remaining three pieces PlayItem information 2 4 referring to clip information in local storage define a single stream sequence from the AVClips on BD ROM and in local storage as shown in .

In the case of PlayItem information 2 3 and 4 specifying AVClips 2 3 and 4 as playback intervals the PL information in local storage is able to define both AVClips on BD ROM and in local storage as a single stream sequence.

As illustrated above AVClips on BD ROM and in local storage can be defined as a single stream sequence and by merging this stream sequence with applications on BD ROM or in local storage a single title can be constituted from AVClips and from applications recorded on BD ROM or in local storage. In the case of AVClip 1 being recorded on BD ROM and AVClips 2 to 4 and a Java application being recorded in local storage as shown in these AVClips and the Java application can as shown in be treated as a single title.

Merge management information is described next. Merge management information uniquely shows all of files in the discs 1 and 2 directories in local storage that constitute a virtual package and is stored in a prescribed file hereinafter merge management information file . shows an exemplary internal structure of a merge management information file. A merge management information file is composed of storage location information for each file in local storage constituting a virtual package. Storage location information is composed of identifiers for accessing respective files as a virtual package and file paths indicating the storage locations of respective files in local storage.

Signature information files are described next. A signature information file shows the electronic signature of a provider on a merge management information file. The electronic signature generally employed is obtained by computing a hash value for information that requires tamper proofing and encrypting the hash value using some sort of secret key.

The following describes an embodiment of a playback apparatus pertaining to the present invention. shows a hardware configuration of the playback apparatus. The playback apparatus is constituted from a BD ROM drive a read buffer a demultiplexer demux a video decoder a video plane a presentation graphics P graphics decoder presentation graphics P graphics plane a composition unit a font generator an interactive graphics I graphics decoder a switch an interactive graphics I graphics plane a composition unit a color lookup table CLUT unit a color lookup table CLUT unit an audio decoder a network device a local storage a read buffer a demultiplexer demux an instruction ROM a user event UE processing unit a player status register PSR set a central processing unit CPU a scenario memory a local memory and a switch .

The elements BD ROM drive audio decoder pertaining to playback of AVClips recorded on BD ROM are described firstly.

Read buffer is a first in first out FIFO memory in which transport stream TS packets read from BD ROM or local storage are stored on a first in first out basis.

Demux reads TS packets from read buffer and converts these TS packets to packetized elementary stream PES packets. PES packets having packet identifiers PIDs set by CPU are then output to one of video decoder P graphics decoder I graphics decoder and audio decoder .

Video decoder decodes PES packets output from demux to obtain pictures in uncompressed format and writes these pictures to video plane .

Video plane is for storing uncompressed pictures. A plane is a memory area in a playback apparatus for storing one screen worth of pixel data. Video plane has a 1920 1080 resolution with stored picture data being constituted from pixel data expressed by 16 bit YUV. In video plane playback video in a video stream can be scaled per frame. Scaling involves changing playback video per frame to either quarter or 1 1 full scale of the entire video plane . Scaling is executed in BD J mode in accordance with instructions from CPU enabling screen production whereby the playback images of video streams are relegated to a corner of the screen or projected over the whole screen.

P graphics decoder decodes P graphics streams read from BD ROM and writes the uncompressed graphics to P graphics plane . Subtitles appear on screen as the result of a graphics stream being decoded.

P graphics plane being a memory with room for one screen worth of data is able to store one screen worth of uncompressed graphics. This plane has a 1920 1080 resolution with pixels of the uncompressed graphics in P graphics plane being expressed by 8 bit index color. Uncompressed graphics stored in P graphics plane are submitted for display by converting the index colors using a CLOT.

Composition unit composites uncompressed picture data stored in video plane with the stored content of P graphics plane .

Font generator uses a character font to expand text code included in TextST streams in a bitmap and writes the expanded code to P graphics plane .

I graphics decoder decodes I graphics streams read from BD ROM or local storage in DVD like mode and writes the uncompressed graphics to I graphics plane .

Switch selectively writes one of a font sequence generated by font generator and graphics resulting from the decoding by P graphics decoder to P graphics plane .

I graphics plane is written with uncompressed graphics resulting from the decoding by I graphics decoder . Characters and graphics drawn by an application are written into I graphics plane in BD J mode using RGB full color.

Composition unit composites the storage content of I graphics plane with composite images output from composition unit i.e. composition of uncompressed picture data and storage content of P graphics plane . This compositing enables characters and graphics written to I graphics decoder by an application to be overlaid on uncompressed picture data and displayed.

CLUT unit converts index colors in uncompressed graphics stored in I graphics plane to Y Cr Cb when operating in DVD like mode i.e. mode for playing digital streams like conventional DVD . When operating in BD J mode i.e. mode for playing digital streams in sync with Java application CLUT unit converts RGB full color to Y Cr Cb. Note that a Java application may be bound or unbound to a title as well as being bound or unbound to a disc.

The elements pertaining to AVClip playback are as described above. The following describes elements pertaining to operations in BD J mode network device demux .

Network device realizes communication functions in the playback apparatus. In the case of an application specifying an URL in BD J mode network device establishes a transmission control protocol TCP or file transfer protocol FTP connection etc. with the website indicated by the URL. Java applications are made to download from the website as the result of a connection being established.

Local storage is a hard disk for storing contents downloaded from a website via a connection established by network device and contents supplied from communication and recording media other than BD ROM together with metadata. Metadata is information for binding and managing downloaded contents in local storage . By accessing local storage applications in BD J mode can perform a variety of processing using downloaded contents. Local storage also holds merge management information files.

Read buffer is a FIFO memory that stores TS packets constituting SubClips on a first in first out basis in the case of SubClips being included in downloaded contents stored on BD ROM or in local storage .

Demux reads TS packets from read buffer and converts the read TS packets to PES packets. PES packets having specific PIDs are then output to P graphics decoder font generator and audio decoder .

The above elements to enable contents downloaded by a Java application via a network to be played in a similar manner to contents recorded on BD ROM. The following describes elements instruction ROM switch for realizing collective controls in the playback apparatus.

UE processing unit in response to key operations of a remote controller or the front panel of the playback apparatus outputs user events for per forming these operations to CPU .

PSR set is a set of resisters internal to the playback apparatus composed of 64 player status registers PSRs and 4096 general purpose registers GPRs . PSRs are used to express the current playback point.

PSR indicates the title of the current playback point as a result of having been set to a value from 1 100. Setting PSR to 0 indicates that the current playback point is the top menu.

PSR indicates the chapter number of the current playback point as a result of having been set to a value from 1 999. Setting PSR to 0xFFFF indicates a null chapter number in the playback apparatus.

PSR indicates the number of the PL current PL to which the current playback point belongs as a result of having been set to a value from 0 999.

PSR indicates the number of the playitem current playitem to which the current playback point belongs as a result of having been set to a value from 0 255.

PSR indicates the current playback point current presentation time or PTM using 45 KHz time accuracy as a result of having been set to a value from 0 0xFFFFFFFF. PSRs enable the current playback point to be identified on a time axis for the entire BD ROM shown in .

CPU runs software stored in instruction ROM to execute controls relating to the entire playback apparatus. These controls change dynamically depending on user events output from UE processing unit and the PSR values in PSR set .

Scenario memory is for storing current PL information and current clip information. Current PL information is the piece of PL information recorded on BD ROM that is currently targeted for processing. Current clip information is the piece of clip information recorded on BD ROM that is currently targeted for processing.

Local memory is a cache memory for temporarily storing the recorded content of BD ROM given the slow reading speed from BD ROM. The provision of local memory allows applications in BD J mode to run efficiently.

Switch selectively delivers data read from BD ROM and local storage to one of read buffer read buffer scenario memory and local memory .

The hardware configuration of a playback apparatus pertaining to the present embodiment is as described above. The following describes the software structure in a playback apparatus pertaining to the present embodiment.

The hardware configuration of the playback apparatus shown in belongs to the 1st layer. Of this hardware configuration the BD player at the 1st layer in includes a decoder composed of video decoder P graphics decoder I graphics decoder and audio decoder a plane composed of video plane P graphics plane and I graphics plane BD ROM and relating filesystem local storage and relating filesystem and network device .

The BD player model at the 2nd layer is composed of a lower layer for a presentation engine and a virtual filesystem unit and an upper layer for a playback control engine with API functions being provided in relation to higher levels.

The application runtime environment at the 3rd layer is composed of a layer that includes a module manager stacked on a layer that includes a DVD like module and a Java platform

DVD like module decodes navigation commands and executes function calls in relation to playback control engine based on the decoding result.

Java platform is a so called Java platform having a hierarchical structure composed of a Java virtual machine and middleware for the Java virtual machine to operate not depicted .

Java virtual machine loads xlet programs constituting applications into a work memory decodes the xlet programs and performs controls on lower layers in accordance with the decoding results. To perform these controls Java virtual machine issues a method to the middleware has the middleware replace the method with a function call corresponding to a BD playback apparatus and issues the function call to playback control engine .

The following describes the internal structure of Java virtual machine . shows the internal structure of Java virtual machine . As shown in Java virtual machine is constituted from CPU a user class loader a method area a work memory threads . . . and Java stacks . . .

User class loader reads class files in Java archive files in the BDJA directory from local memory or the like and stores the read class files in method area . The reading of a class file by user class loader is performed as a result of module manager sending a read instruction specifying a file path to user class loader . If the file path indicates local memory user class loader reads a class file in a Java archive file constituting an application from local memory to work memory . If the file path indicates a directory in a filesystem user class loader reads a class file in a Java archive file constituting an application from BD ROM or local storage to work memory .

Work memory is a so called heap area storing the instances of various class files. Work memory stores instances corresponding to resident applications and class files read to method area . An instance is an xlet program constituting an application that is made executable by placing the xlet program in work memory .

Threads . . . are logical execution entities for executing methods stored in work memory . They perform calculations using local variables and arguments stored in operand stacks as operands and store calculation results in local variables or operand stacks. The arrows ky ky and kyn in symbolically indicate the supply of methods from work memory to threads . . . . Whereas the CPU is the sole physical execution entity there may be up to 64 logical execution entities or threads in Java virtual machine . Threads can be newly created and existing threads deleted within this numerical limit and the number of operational threads can be varied while Java virtual machine is operating. Being able to appropriately increase the number of threads also makes it possible to run instances in parallel using a plurality of threads for each instance and thereby speed up the execution of instances.

Java stacks . . . exist in a one to one ratio with threads . . . and each has a program counter PC in and one or more frames. The program counters show which part of an instance is currently being executed. A frame is a stack type area allocated to each call for a method and is composed of an operand stack for storing arguments occurring at the time of the call and a local variable stack local variable in for use by the called method. Since frames are stacked on Java stacks . . . whenever a call is made the frames of a method that calls itself recursively also get stacked one on top of the other.

The internal structure of the Java virtual machine is as described above. A Java virtual machine having the above structure serves as an event driven execution entity. This completes description of the Java virtual machine.

Presentation engine executes AV playback functions. The AV playback functions of a playback apparatus are a traditional group of functions inherited from DVD players and CD players including PLAY STOP PAUSE ON PAUSE OFF STILL OFF FAST FORWARD PLAY 2 4etc. FAST BACKWARD PLAY 2 4 etc. AUDIO CHANGE SUBTITLE CHANGE and ANGLE CHANGE. To realize these AV playback functions presentation engine controls video decoder P graphics decoder I graphics decoder and audio decoder to decode the portion of an AVClip read to read buffer that corresponds to a desired time. By having the place indicated by PSR current PTM decoded as the desired time arbitrary points in an AVClip can be rendered playable.

Playback control engine executes various functions including i playback controls on playlists and ii acquiring setting the status of PSR set . The playback control function involves having presentation engine execute PLAY and STOP out of the above AV playback functions in accordance with current PL information and clip information. Functions i and ii are executed according to function calls from DVD like module and Java platform

Synchronization of the processing by playback control engine with the processing by the Java virtual machine is described next. Playback control engine executes processing based on PL information when a function is called. This processing is performed for the duration of the AVClip for playback whether the playback time is 15 minutes or 30 minutes. A problem here is the time lag between when Java virtual machine returns a success response and when playback control engine actually ends the processing. Java virtual machine being an event driven execution entity returns a response indicating whether playback was successful or not immediately after the call whereas playback control engine ends playback of the AVClip and playitems after the 15 or 30 minute playback duration has elapsed. Thus the time at which a success response is returned to an application cannot be used as a basis for gauging the end of processing 15 or 30 minutes later. Gauging the end of processing becomes all the more difficult when fast forwarding or rewinding is performed during PL playback since the playback time of 15 or 30 minutes is then subject to change. In view of this playback control engine outputs events indicating the end of playitem and AVClip playback to an application when playback of a respective playitem or AVClip ends. This output enables the application to know the points at which playback control engine concluded playitem and AVClip playback.

Module manager reads INDEX.BDMV and chooses one of the pieces of title information in INDEX.BDMV as current title information. Module manager reads a BD J object indicated by the current title information and controls playback control engine to perform playback controls based on PL information described in the BD J object. Module manager also controls Java virtual machine to read and execute Java archive files described in the BD J object.

If playback of a digital stream based on PL information and execution of the applications ends or if the user calls a menu module manager reads title information defining another title and chooses this piece of title information as the current title information. The choosing of another piece of title information as the current title information according to digital stream playback or a user menu call is called a title change .

The status transition shown in can be realized by repeatedly performing title changes. The oval windows in represent titles.

The titles include a FirstPlayTitle for playback when a BD ROM is first loaded a Top menuTitle constituting a top menu and other general titles. The arrows jh jh jh jh jh jh jh and jh in symbolically indicate branching between titles.

The status transition shown in involves playing FirstPlayTitle when the BD ROM is loaded and then branching to Top menuTitle and waiting for a selection from the top menu.

When the user selects from the menu the respective title is played in accordance with the selection before again returning to Top menuTitle. The endless repetition of this processing until the disc is ejected is a status transition peculiar to disc contents. This status transition is realized under the control of module manager described above.

This completes description of Java virtual machine presentation engine playback control engine and module manager . The controls on playback control engine by Java virtual machine are performed via a virtual package. To realize controls on playback control engine via a virtual package the playback apparatus includes a network management module and a virtual filesystem unit . These elements are describes next.

Network management module downloads data required for creating virtual packages from websites administrated by the providers of movie works in accordance with method calls from applications. This data includes files PL information clip information AVClips Java archive files etc. that either replace or add to merge management information files signature information files and files on BD ROM. When download requests are made by applications in work memory network management module downloads data required for creating virtual packages via a network and writes the downloaded data to local storage .

Virtual filesystem unit is an element belonging to the 2nd layer in that creates virtual packages in accordance with method calls from applications. The creation of a virtual package includes processing to manage the status of AVClips constituting the virtual package and processing to generate virtual package information.

Virtual package information expands the volume management information on BD ROM. The volume management information referred to here defines the directory structure existing on recording media and is composed of directory management information relating to directories and file management information relating to files.

Virtual package information expands the directory structure on BD ROM by adding new file management information to the volume management information showing the directory structure. The file management information added to the volume management information relates to PL information clip information AVClips and Java archive files existing in local storage . Creating virtual package information to which this file management information has been added and providing this virtual package information to playback control engine enables the playback control engine to recognize PL information clip information AVClips and Java archive files stored in local storage as existing on BD ROM. shows an exemplary creation of virtual package information by virtual filesystem unit . At the top left of is the directory structure on BD ROM this being the same as . At the bottom left is the directory structure in local storage this being the same as . File management information relating to PL information clip information AVClips and Java archive files in local storage are added to the volume management information on BD ROM.

i file management information relating to playlist information 2 00002.mpls in local storage is added to the directory management information in the PLAYLIST directory 

ii file management information relating to clip information 2 3 and 4 00002.clip 00003.clip 00004.clip in local storage is added to the directory management information in the CLIPINF directory 

iii file management information relating to AVClips 2 3 and 4 00002.m2ts 00003.m2ts 00004.m2ts in local storage is added to the directory management information in the STREAM directory and

iv file management information relating to the Java archive file 00002.jar in local storage is added to the directory management information for the BDJA directory.

Virtual package information is thus obtained. In other words virtual package information is volume management information that has been added to in the above manner.

This virtual package information is then provided to playback control engine which is thereby able to treat PL information clip information AV clips and Java archive files in local storage on an equal basis with PL information clip information AVClips and Java archive files on BD ROM. The generation of virtual package information is as described above.

Assume that the BD ROM is ejected after branching performed in the numerical order of the reference signs indicated by the arrows jh jh jh jh etc. in . This enables the contiguous timeslot from the loading to the ejecting of the BD ROM to be viewed as a single time axis. This time axis is taken as the time axis for the entire disc. shows the time axis for the entire disc while shows the structure of this time axis. As shown in the time axis for the entire disc is composed of intervals during which FirstPlayTitle is played intervals during which Top menuTitle is played and intervals during which general titles Title 1 etc. are played. As for the manner in which the playback intervals of these titles are defined since each title is constituted from only one BD J object the period during which any given BD J object is valid can be regarded as the playback interval of a title. The space between these playback intervals or rather the interval for changing from one title to another i.e. title change is when the virtual package information is updated.

A procedure for downloading new merge management and signature information files and content files by a Java application is described next using .

The Java application firstly sends the current merge management information file to the server step S thereby requesting a download and judges whether data has been received from the server step S . When data is downloaded the Java application creates a new directory in a corresponding disc directory and writes the downloaded merge management information file and signature information file to the new directory step S . Note that if the filenames of the downloaded merge management and signature information files do not coincide with the existing merge management and signature information files in the disc directory the downloaded files may be placed directly under the existing directory disc 1 directory without creating a new directory. Downloaded AVClips clip information PL information and Java archive files are written to the corresponding directory step S . The Java application then calls an update request method using the file paths of the new merge management and signature information files as arguments Step S . The Java application judges whether the return value is false step S and terminates the processing if false. If the return value is not false the Java application executes processing using the updated virtual package information step S .

Note that while the above processing is described in terms of the Java application sending the current merge management information file to the server when requesting a download the Java application may send only the ID of the merge management information file.

An update preparing procedure performed by virtual filesystem unit upon receipt of an update request is described next using .

Virtual filesystem unit firstly reads the new merge management and signature information files using the file paths that serve as arguments when calling a method step S and verifies the signature in order to check whether the new merge management information file has been tampered with step S . Exceptional termination is carried out if the signature cannot be verified. If the signature is verified virtual filesystem unit checks the authority of the calling application step S . Exceptional termination is carried out if the calling application is unauthorized. If the calling application is authorized virtual filesystem unit judges whether files specified by the new merge management information file actually existing in local storage step S . Exceptional termination is carried out if these files do not exist. If these files do exist virtual filesystem unit changes the new merge management and signature information files and all the files in local storage referenced from the new merge management information file to read only step S .

Module manager firstly chooses FirstPlayTitle as the current title step S specifies the BD J object corresponding to the current title as the current BD J object step S and has playback control engine execute PL playback based on PL information described in the current BD J object step S . Module manager then has Java platform run Java applications whose lifecycle is the current title in the application management table of the current BD J object step S and has Java platform terminate Java applications whose lifecycle is not the current title step S . Module manager then judges whether PL playback based on the current PL information has been completed step S and if completed module manager identifies the next title step S and chooses this title as the current title step S . If current PL playback is not yet completed module manager judges whether a title call has occurred step S and moves to step S if this is the case. If a title call has not occurred module manager judges whether a title jump has occurred step S and moves to step S if this is the case. If a title jump has not occurred module manager judges whether a main application of the current title has ended step S and moves to step S if this is the case. If the main application has not yet ended module manager returns to step S.

Steps S to S are described next. Playback control engine sets the AVClip described in Clip information file name in PlayItem i as AVClip j step S and instructs the drive device and decoder to play AVClip j from the PlayItem.In time to PlayItem.Out time step S . Playback control engine judges whether there exists a SubPlayItem k specifying PlayItem i in Sync PlayItem Id step S and moves directly to step S if this SubPlayItem does not exist. If SubPlayItem k does exist playback control engine sets the AVClip described by Clip information file name of SubPlayItem k as AVClip h step S instructs the drive device and decoder to playback AVClip h from Sync Start PTS of PlayItem to Out time step S and moves to step S.

A stream sequence defined by the PL information is played as a result of this processing being repeated for all of the PlayItem information constituting the PL information.

The 1st tier in shows title playback intervals on the time axis the 2nd tier shows a Java application whose lifecycle is Title 1 the 3rd tier shows a digital stream and the 4th tier shows the status of virtual filesystem unit .

Virtual filesystem unit is placed in a preparing state upon receipt of an update request from the Java application and performs the processing shown in .

After performing this processing virtual filesystem unit waits in a prepared state for a title change. When a title change occurs virtual filesystem unit is placed in an updating state and executes the processing shown in to update the virtual package before reverting back to a stable state. If Title 1 is again selected from Top menuTitle after virtual filesystem unit has reverted back to a stable state Title 1 is played using the updated virtual package.

Here a title change occurs when module manager chooses a different title as the current title due for instance to playback of a stream sequence ending or a menu being called by a user.

Note that the read only attribute of files referenced from the old merge management information but not from the new merge management information is removed making these files writable by a Java application.

The merge management information file includes information indicating the location of contents added to local storage. Information indicating the location of additional contents includes content IDs the directory paths of directories in which the contents are stored or the file paths of individual content files. Filename mapping information may be described in the merge management information file when mapping these files to a virtual package so as to enable these files to be accessed under different filenames in the virtual package. Here filename mapping information maps filenames including file path in a virtual package with filenames including file path in local storage.

In this case virtual packages are created by virtual filesystem unit as virtual package media constituted from files whose filenames in the virtual package described in the filename mapping information have been added to the file structure on BD ROM. Files in a virtual package accessed by a Java application are specified as files in the virtual package rather than as files on BD ROM or in local storage. When a Java application requests access to a file in a virtual package virtual filesystem unit switches the access destination to either local storage or BD ROM based on the filename mapping information. If the desired file is described in the filename mapping information the access destination is changed to a corresponding file in local storage. If the desired file is not described in the filename mapping information the access destination is changed to a corresponding file on BD ROM.

In other words the creator of a Java application need not be aware of the medium BD ROM or local storage on which individual files are stored since virtual filesystem unit switches the access destination of a file specified in a virtual package by a Java application to the medium actually storing the file thereby lightening the burden of program creation.

According to the present embodiment a virtual package is updated during a title change meaning that the replacement of a playback object will not cause abnormal operation of the playback apparatus.

The present embodiment relates to an improvement when title calls are performed. A title call results in the called title being played after firstly suspending the current title and the original title then being resumed after playback of the called title has ended. Since title calls are premised on playback being resumed playback control engine saves system parameters for playback controls stored in PSRs to backup PSRs when a title is called and restores the saved parameters to the PSRs after playback of the called title has ended.

The following is a list of system parameters stored in PSRs. PSR to PSR store system parameters showing playback status PSR to PSR store system parameters set by the player as preferences and PSR to PSR are backup PSRs.

Updating virtual package information during a title call result indifferences in the virtual package information before and after the call.

Since the virtual package information will have changed when the original title is restored errors may arise if playback control engine attempts to play the original title using the backup values. This problem is avoided by clearing the backup PSRs when a Java application has requested updating. However given that the change may have no effect depending on the content of the merge management information file the decision as to whether to clear the system parameter values can be left up to the Java application.

When original title playback is resumed after playback of the called title has ended playback control engine firstly judges whether the virtual package information has been updated step S . PSRs are restored to PSRs step S if not updated while PSRs are initialized step S before performing step S if the virtual package information has been updated.

According to the present embodiment backup PSRs are initialized when the virtual package information has been updated during a title call thereby removing the danger of playback errors occurring when original title playback is resumed. The stable operation of playback control engine is thus enabled.

Note that system parameter values in the PSRs may be mandatorily cleared when virtual package information is updated rather than leaving this decision up the Java application.

The present embodiment relates to a method for managing the version of merge management information and specifying additional contents for merging from a resident application in the playback apparatus. shows an exemplary content of a merge management information file pertaining to the present embodiment. In embodiment 1 the merge management information file or rather the merge management information stored therein is updated by overwriting the old merge management information resulting in the old information being erased. In the present embodiment new merge management information is continually added to the file without overwriting the old information even for the same disc ID. Thus if virtual filesystem unit cancels creation of a virtual package and reverts back to the original BD ROM information that reflects this state is retained in the merge management information file. In this case the corresponding cell in the merge target directory of the merge management information file is either left blank or inscribed with a character string indicating the original BD ROM.

Retaining a history of previous merge management information in the merge management information file is enabled by not overwriting old merge management information when updating is performed and then if the user wants an old version of a virtual package the old version can be created with reference to previous merge management information. Furthermore virtual packages previously created by the user can be created with reference to the merge management information file or rather the old merge management information stored therein from not only a Java application but also from a resident application in the playback apparatus.

Another example of the use of previous merge management information by a resident application involves displaying an additional contents list so that the user can delete unwanted additional contents from the resident application. Since the merge management information file can be used to distinguish directories storing additional contents additional contents can also be retrieved and deleted from an application i.e. a resident application other than the Java application that stored the additional contents.

Rather than having the Java application specify content synopses meta information showing what specific contents are about may be appended to the contents themselves and a resident application may read this information and display synopses based on the read information.

The ADDED ON column in shows the dates on which respective additional contents were first merged with the BD ROM. This information may also be read from the merge management information.

Note that the dates on which additional contents were first merged may be held separately to the merge management information. These dates may also be determined from the dates on which directories for storing the additional contents were created. When one of the select buttons displayed in the additional contents list is depressed the resident application writes the directory path disc ID of the selected content and the selection date to the merge management information file as corresponding merge management information. In other words the additional content most recently selected becomes the latest merge management information. If the original BD ROM is selected either a Value indicating the original BD ROM or a blank cell is inserted in the merge target directory of the merge management information file. When one of the delete buttons displayed in the additional contents list is depressed the resident application reads the directory of the additional content for deletion with reference to the merge management information file and deletes this directory. Merge management information corresponding to the content ID of this content is also deleted from the merge management information file.

According to the present embodiment virtual packages can be created from a resident application in the playback apparatus using old versions of merge management information with reference to the content history of the merge management information file by holding previous merge management information in the merge management information file. If an error occurs during the creation of a virtual package the problem can be avoided by creating an old version of a virtual package as an alternative course of action.

The present embodiment relates to a method for specifying the valid period of a virtual package when a virtual package update is requested by a Java application and using the virtual package to perform playback only within the valid period.

Note that a pattern in which Java mode only virtual packages are created is also conceivable as an application of the present embodiment. If Java mode only is specified when virtual package creation is requested from a Java application virtual filesystem unit creates a virtual package when there is a transition from DVD like mode to Java mode and then shifts to Java mode. Conversely when there is a transition from Java mode to DVD like mode virtual filesystem unit shifts to DVD like mode after canceling the virtual package and reverting back to the original BD ROM.

According to the present embodiment it is possible to specify a valid period for playback using a virtual package thereby enabling playback using once only virtual packages i.e. virtual packages that are disabled once the BD ROM is ejected and creation of virtual packages with use period limitations.

Note that while in the present embodiment a valid period is specified when a virtual package update is requested a valid period may also be specified when virtual package creation is requested after loading a BD ROM.

The following is a detailed description regarding the authority of the calling application at step S in of embodiment 1. Specifically the present embodiment relates to a method of denying virtual package update requests from unauthorized Java applications.

According to the present embodiment unauthorized Java applications can be prevented from having virtual packages updated and changing the content of directories in local storage.

The following is a specific example of the use of permission request files to restrict virtual package updating. Consider an example in which directories are allocated in local storage to specific providers of movie works. Specifically assume that contents provided by A Studios B Studios and C Inc. are stored both in local storage and on BD ROM. Here C Inc. is the provider of digital magazines. It would be problematic when merging contents in local storage with BD ROM if for instance contents provided by B Studios were merged with contents provided by A Studios. In view of this updating permission is only granted to C Inc. i.e. update attribute value in permission request file set to true thereby enabling various services to be made available. A Studios and B Studios are only able to merge their own contents.

The present embodiment relates to a method for updating a virtual package during a title change in the case of Java applications that operate across a plurality of titles.

In the application management information shown in for example Java application 1 is bound and Java application 2 is unbound in title 1. Module manager terminates bound Java application 1 together with the end of title 1. On the other hand unbound Java application 2 is allowed to live past the end of title 1 with the decision of whether or not to terminate this application being made according to the application management information of the next title. Since the application management information in the example shows that Java application 2 can exist in both title 1 and title 2 this application is allowed to live through the transition from title 1 to title 2. Because Java application 2 is title bound in title 2 however module manager terminates the application together with the end of this title.

Since the present embodiment ensures that all applications are terminated during the updating of virtual packages it is possible to prevent any loss of consistency after the completion of virtual package updating in terms of references to old pre update files remaining or new files existing along side old files still in cache.

Note that if a Java application capable of existing over a plurality of discs disc unbound application is operating when a title change occurs after virtual package updating has been requested the disc unbound application can continue operating without being forcibly terminated by treating the virtual package update in the same manner as a disc changing operation.

Note also that module manager may manage the start and end of a title unbound application after a title change has occurred in accordance with application management information updated after the completion of virtual package updating without terminating the title unbound application during the update. In this case the title unbound application is made to reference the pre update virtual package until the updating is completed.

The present embodiment relates to virtual package updating following a change in an INDEX.BDMV file. Upon receiving a virtual package update request from a Java application virtual filesystem unit confirms that an INDEX.BDMV file exists in the directory targeted for merging. If an INDEX.BDMV file exists virtual filesystem unit reads the INDEX.BDMV file in preparation for the updating. The existing INDEX.BDMV file is then invalidated and a new INDEX.BDMV file is validated. This new INDEX.BDMV file is then used prior to a title change if for example a resident application of the BD player performs a title search or a Java application acquires title information. In other words informing Java applications and users beforehand of the post updating title structure makes it possible to prevent title changes to titles that will cease to exist after the update or title changes to unexpected titles.

Thus while virtual package updating is not performed until a title change occurs after an update request the new INDEX.BDMV file is made available prior to the title change. This means that after an update request the title list displayed during a title search will have changed prior to a title change occurring.

Since the user then selects titles based on the altered title list errors resulting from the selection of a title that will cease to exist after updating can be prevented. The virtual package can thus be updated without a problem during a title change even if the title structure is altered due to the updating.

Note that virtual package updating following a change in an INDEX.BDMV file may be performed when the BD player is rebooted.

A playback apparatus pertaining to the present invention is described above based on the preferred embodiments although the present invention is of course not limited to these embodiments.

The above embodiments are described in relation to a playback apparatus whose only function is to play recording media although the present invention is not limited to this. For example the present invention may be a recording playback apparatus with recording and playback functions.

Files can be placed in local storage using any kind of structure provided that the correspondence with files on BD ROM targeted for merging is clearly shown.

In the above embodiments Java registered trademark is used as the programming language of the virtual machine although programming languages other than Java may be used examples of which include Perl Script ECMA Script and B Shell which is used with UNIX registered trademark operating systems and the like.

The above embodiments are described in relation to a playback apparatus that plays BD ROM although of course the same effects as above are achieved in the case of requisite data on BD ROM as described in the above embodiments being recorded on a writable optical recording medium.

Furthermore the same effects as above are of course achieved in the case of requisite data on BD ROM as described in the above embodiments being recorded on a portable recording medium other than an optical recording medium e.g. SD card compact flash etc .

A playback apparatus constituting the present invention can be administratively as well as continuously and repeatedly manufactured and retailed in manufacturing industries. This playback apparatus is particularly applicable in movie and consumer appliance industries that pertain to the production of video contents.

