---

title: Method, apparatus and system for rendering an object on a page
abstract: A method of rendering a graphical object (e.g., ) on a page (), is disclosed. A region of the page containing the graphical object () is marked as output incompatible based on the graphical object () being output incompatible. A bounding box comprising the marked region is determined. A proportion of a number of the regions marked as output incompatible are determined to a total number of regions in the bounding box. A further region within the bounding box is marked as output incompatible to increase the determined proportion above a threshold. The graphical object in the marked region and the further marked region is converted into an output compatible graphical object if the determined proportion is above the threshold. The output compatible graphical object is rendered.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09104352&OS=09104352&RS=09104352
owner: Canon Kabushiki Kaisha
number: 09104352
owner_city: Tokyo
owner_country: JP
publication_date: 20120626
---
This application claims priority under 35 U.S.C. 119 from Australian Patent Application No. 2011203173 filed Jun. 29 2011 which is hereby incorporated by reference in its entirety as if fully set forth herein.

The current invention relates to graphics processing and in particular to a method and apparatus for rendering an object on a page. The current invention also relates to a computer program product including a computer readable medium having recorded thereon a computer program for rendering an object on a page.

The printing process in modern operating systems typically involves steps of invoking drawing functions converting the drawing functions into a standardized format e.g. PDF or XPS and spooling the standardized format drawing functions to a printer driver. The printer driver may contain an interpreter which parses the standardized format drawing functions and converts the standardized format drawing functions into drawing instructions that are accepted by a printer driver rendering engine. The printer driver rendering engine typically renders the drawing instructions to pixels and sends the pixels to a printer which prints the pixels onto paper.

Some printers have limited rendering functionality. A printer driver used by such printers may contain an interpreter that parse the standardized format into certain printer recognizable graphical objects and drawing instructions that are accepted by the printer. The printer driver sends the generated graphical objects and drawing instructions to the printer. The printer then renders the graphical objects and drawing instructions into pixels.

Conventional methods for converting graphical objects and drawing instructions parsed from the standardized format into limited printer supported graphical objects typically include processes for translating any printer compatible graphical objects and drawing instructions directly into a printer recognizable format. Such methods typically also include processes for rendering any printer incompatible graphical objects and drawing instructions into pixels. The conventional methods for converting graphical objects and drawing instructions into limited printer supported graphical objects may result in a large amount of image data being sent to the printer especially when there is lots of overlap between printer compatible objects and printer incompatible objects. The large amount of image data often results in a slow printing speed.

Thus a need clearly exists for a better and more efficient printing method that will result in a faster printing speed.

It is an object of the present invention to substantially overcome or at least ameliorate one or more disadvantages of existing arrangements.

According to one aspect of the present disclosure there is provided a method of rendering a graphical object on a page the method including 

marking a region of the page containing the graphical object as output incompatible based on the graphical object being output incompatible 

determining a proportion of a number of the regions marked as output incompatible to a total number of regions in the bounding box 

marking a further region within the bounding box as output incompatible to increase the determined proportion above a threshold 

converting the graphical object in the marked region and the further marked region into an output compatible graphical object if the determined proportion is above the threshold and

According to another aspect of the present disclosure there is provided a method of rendering a graphical object on a page the method including 

marking a first region of the page containing the graphical object as output incompatible based on the graphical object being output incompatible 

According to still another aspect of the present disclosure there is provided a method of rendering a graphical object on a page the method including 

marking a region of the page as output incompatible if a the graphical object is output incompatible and b the determined size of the graphical object is larger than a threshold 

According to still another aspect of the present disclosure there is provided a system for rendering a graphical object on a page the system including 

a processor coupled to the memory for executing the computer program the computer program including instructions for 

According to still another aspect of the present disclosure there is provided a system for rendering a graphical object on a page the system including 

a processor coupled to the memory for executing the computer program the computer program including instructions for 

According to still another aspect of the present disclosure there is provided an apparatus for rendering a graphical object on a page the apparatus including 

means for marking a region of the page as output incompatible based on the mapped graphical object being output incompatible 

means for determining a proportion of a number of the regions marked as output incompatible to a total number of regions in the bounding box 

means for marking a further region within the bounding box as output incompatible to increase the determined proportion above a threshold 

means for converting the graphical object in the marked region and the further marked region into an output compatible graphical object if the determined proportion is above the threshold and

According to still another aspect of the present disclosure there is provided an apparatus for rendering a graphical object on a page the apparatus including 

means for marking a first region of the page containing the graphical object as output incompatible based on the graphical object being output incompatible 

means for marking the second region as output incompatible if the determined distance satisfies a threshold 

means for converting graphical objects within the first and the second region as output compatible and

According to still another aspect of the present disclosure there is provided a computer readable medium having a computer program recorded thereon for rendering a graphical object on a page the computer program including 

code for marking a region of the page containing the graphical object as output incompatible based on the graphical object being output incompatible 

code for determining a proportion of a number of the regions marked as output incompatible to a total number of regions in the bounding box 

code for marking a further region within the bounding box as output incompatible to increase the determined proportion above a threshold 

code for converting the graphical object in the marked region and the further marked region into an output compatible graphical object if the determined proportion is above the threshold and

According to still another aspect of the present disclosure there is provided a computer readable medium having a computer program recorded thereon for rendering a graphical object on a page the computer program including 

code for marking a first region of the page containing the graphical object as output incompatible based on the graphical object being output incompatible 

code for marking the second region as output incompatible if the determined distance satisfies a threshold 

code for converting graphical objects within the first and the second region as output compatible and

Where reference is made in any one or more of the accompanying drawings to steps and or features which have the same reference numerals those steps and or features have for the purposes of this description the same function s or operation s unless the contrary intention appears.

A method see of rendering a graphical object on a page is described below with reference to . The method takes into account a compatible incompatible property of the graphical object as well as other properties of the graphical object such as object type and size as well as overlap.

As seen in the computer system includes a computer module input devices such as a keyboard a mouse pointer device a scanner a camera and a microphone and output devices including a printer a display device and loudspeakers . An external Modulator Demodulator Modem transceiver device may be used by the computer module for communicating to and from a communications network via a connection . The communications network may be a wide area network WAN such as the Internet a cellular telecommunications network or a private WAN. Where the connection is a telephone line the modem may be a traditional dial up modem. Alternatively where the connection is a high capacity e.g. cable connection the modem may be a broadband modem. A wireless modem may also be used for wireless connection to the communications network .

The computer module typically includes at least one processor unit and a memory unit . For example the memory unit may have semiconductor random access memory RAM and semiconductor read only memory ROM . The computer module also includes a number of input output I O interfaces including an audio video interface that couples to the video display loudspeakers and microphone an I O interface that couples to the keyboard mouse scanner camera and optionally a joystick or other human interface device not illustrated and an interface for the external modem and printer . In some implementations the modem may be incorporated within the computer module for example within the interface . The computer module also has a local network interface which permits coupling of the computer system via a connection to a local area communications network known as a Local Area Network LAN . As illustrated in the local communications network may also couple to the wide network via a connection which would typically include a so called firewall device or device of similar functionality. The local network interface may comprise an Ethernet circuit card a Bluetooth wireless arrangement or an IEEE 802.11 wireless arrangement however numerous other types of interfaces may be practiced for the interface .

The I O interfaces and may afford either or both of serial and parallel connectivity the former typically being implemented according to the Universal Serial Bus USB standards and having corresponding USB connectors not illustrated . Storage devices are provided and typically include a hard disk drive HDD . Other storage devices such as a floppy disk drive and a magnetic tape drive not illustrated may also be used. An optical disk drive is typically provided to act as a non volatile source of data. Portable memory devices such optical disks e.g. CD ROM DVD Blu ray Disc USB RAM portable external hard drives and floppy disks for example may be used as appropriate sources of data to the system .

The components to of the computer module typically communicate via an interconnected bus and in a manner that results in a conventional mode of operation of the computer system known to those in the relevant art. For example the processor is coupled to the system bus using a connection . Likewise the memory and optical disk drive are coupled to the system bus by connections . Examples of computers on which the described arrangements can be practised include IBM PC s and compatibles Sun Sparcstations Apple Mac or a like computer systems.

The described methods including the method may be implemented using the computer system wherein the processes of to be described may be implemented as one or more software application programs executable within the computer system . In particular the steps of the described method are effected by instructions see in the software application program that are carried out within the computer system . The software instructions may be formed as one or more software code modules each for performing one or more particular tasks. The software application program may also be divided into two separate parts in which a first part and the corresponding software code modules performs the described methods and a second part and the corresponding software code modules manage a user interface between the first part and the user.

The software application program may be stored in a computer readable medium including the storage devices described below for example. The software application program is loaded into the computer system from the computer readable medium and is then executed by the computer system . A computer readable medium having such software or computer program recorded on the computer readable medium is a computer program product. The use of the computer program product in the computer system preferably effects an advantageous apparatus for implementing the described methods.

The software application program is typically stored in the HDD or the memory . The software application program is loaded into the computer system from a computer readable medium and executed by the computer system . Thus for example the software application program may be stored on an optically readable disk storage medium e.g. CD ROM that is read by the optical disk drive .

In some instances the software application program may be supplied to the user encoded on one or more CD ROMs and read via the corresponding drive or alternatively may be read by the user from the networks or . Still further the software application program can also be loaded into the computer system from other computer readable media. Computer readable storage media refers to any non transitory tangible storage medium that provides recorded instructions and or data to the computer system for execution and or processing. Examples of such storage media include floppy disks magnetic tape CD ROM DVD Blu ray Disc a hard disk drive a ROM or integrated circuit USB memory a magneto optical disk or a computer readable card such as a PCMCIA card and the like whether or not such devices are internal or external of the computer module . Examples of transitory or non tangible computer readable transmission media that may also participate in the provision of software application programs instructions and or data to the computer module include radio or infra red transmission channels as well as a network connection to another computer or networked device and the Internet or Intranets including e mail transmissions and information recorded on Websites and the like.

The second part of the software application program and the corresponding software code modules mentioned above may be executed to implement one or more graphical user interfaces GUIs to be rendered or otherwise represented upon the display . Through manipulation of typically the keyboard and the mouse a user of the computer system and the application may manipulate the interface in a functionally adaptable manner to provide controlling commands and or input to the applications associated with the GUI s . Other forms of functionally adaptable user interfaces may also be implemented such as an audio interface utilizing speech prompts output via the loudspeakers and user voice commands input via the microphone .

When the computer module is initially powered up a power on self test POST program executes. The POST program is typically stored in a ROM of the semiconductor memory of . A hardware device such as the ROM storing software is sometimes referred to as firmware. The POST program examines hardware within the computer module to ensure proper functioning and typically checks the processor the memory and a basic input output systems software BIOS module also typically stored in the ROM for correct operation. Once the POST program has run successfully the BIOS activates the hard disk drive of . Activation of the hard disk drive causes a bootstrap loader program that is resident on the hard disk drive to execute via the processor . This loads an operating system into the RAM memory upon which the operating system commences operation. The operating system is a system level application executable by the processor to fulfil various high level functions including processor management memory management device management storage management software application interface and generic user interface.

The operating system manages the memory to ensure that each process or application running on the computer module has sufficient memory in which to execute without colliding with memory allocated to another process. Furthermore the different types of memory available in the system of must be used properly so that each process can run effectively. Accordingly the aggregated memory is not intended to illustrate how particular segments of memory are allocated unless otherwise stated but rather to provide a general view of the memory accessible by the computer system and how such is used.

As shown in the processor includes a number of functional modules including a control unit an arithmetic logic unit ALU and a local or internal memory sometimes called a cache memory. The cache memory typically includes a number of storage registers in a register section. One or more internal busses functionally interconnect these functional modules. The processor typically also has one or more interfaces for communicating with external devices via the system bus using a connection . The memory is coupled to the bus using a connection .

The software application program includes a sequence of instructions that may include conditional branch and loop instructions. The software application program may also include data which is used in execution of the program . The instructions and the data are stored in memory locations and respectively. Depending upon the relative size of the instructions and the memory locations a particular instruction may be stored in a single memory location as depicted by the instruction shown in the memory location . Alternately an instruction may be segmented into a number of parts each of which is stored in a separate memory location as depicted by the instruction segments shown in the memory locations and .

In general the processor is given a set of instructions which are executed therein. The processor waits for a subsequent input to which the processor reacts to by executing another set of instructions. Each input may be provided from one or more of a number of sources including data generated by one or more of the input devices data received from an external source across one of the networks data retrieved from one of the storage devices or data retrieved from a storage medium inserted into the corresponding reader all depicted in . The execution of a set of the instructions may in some cases result in output of data. Execution may also involve storing data or variables to the memory .

The described methods use input variables which are stored in the memory in corresponding memory locations . The methods produce output variables which are stored in the memory in corresponding memory locations . Intermediate variables may be stored in memory locations and .

Referring to the processor of the registers the arithmetic logic unit ALU and the control unit work together to perform sequences of micro operations needed to perform fetch decode and execute cycles for every instruction in the instruction set making up the program . Each fetch decode and execute cycle comprises 

Thereafter a further fetch decode and execute cycle for the next instruction may be executed. Similarly a store cycle may be performed by which the control unit stores or writes a value to a memory location .

Each step or sub process in the processes of is associated with one or more segments of the software application program and is performed by the register section the ALU and the control unit in the processor working together to perform the fetch decode and execute cycles for every instruction in the instruction set for the noted segments of the software application program .

The method may alternatively be implemented in dedicated hardware such as one or more integrated circuits performing the functions or sub functions of the method . Such dedicated hardware may include graphic processors digital signal processors or one or more microprocessors and associated memories.

The method of rendering a graphical object on a page will now be described with reference to . The method may be implemented as one or more software code modules of the software application program resident on the hard disk drive and being controlled in its execution by the processor .

The method begins at drawing command receiving step where the processor receives one or more drawing commands which may be stored in memory . The drawing commands may be issued by another software application program resident on the hard disk drive and being controlled by the processor . Alternatively the drawing commands may be issued by a software application program resident on a remote server connected to the network .

In one implementation the drawing commands may be issued to an operating system spooler software module using an operating system supplied graphics application programming interface. Such an operating system spooler software module may be resident on the hard disk drive and be controlled in its execution by the processor . At converting step the processor or the operating system spooler software module under execution of the processor converts the drawing commands to a standardized file format such as the XPS file format or the Portable Document Format PDF .

Then at interpreting step the standardized file format is interpreted into an intermediate graphical object. The intermediate graphical object contains corresponding drawing instructions of how to draw the graphical object onto the page including graphics properties of the graphical object such as shape compositing method clipping information and possibly a bounding box. In one implementation step may be executed by a printer driver software module resident on the hard disk drive and being controlled in its execution by the processor .

At storing step the intermediate graphical object and corresponding drawing instructions are stored in a self retained display list SRDL configured within the memory . The self retained display list is an internal display list that is constructed and used for converting the intermediate graphical object into printer recognizable format. In one implementation step and following steps to may be executed by an object converter software module resident in the hard disk drive and being controlled in its execution by the processor . As described below in steps to the intermediate graphical objects are converted into printer compatible graphical objects in printer recognizable format.

Then at mapping step the processor performs the step of mapping the intermediate graphical object onto one or more corresponding regions of the page. In performing the mapping at step the processor determines which regions of the page are touched by the graphical object. A method of mapping the intermediate graphical object onto one or more corresponding regions of the page as executed at step will be described in detail below with reference to .

At marking step the processor performs the step of marking the corresponding regions of the page as output incompatible based on the mapped graphical object being output incompatible and any surrounding regions being classified as output incompatible i.e. associated with a corresponding output incompatible graphical object . In one implementation the corresponding regions of the page are marked as output incompatible based on a determined size of the graphical object satisfying a threshold as described below.

Each region of the page has a bounding box and an associated dirty status flag. The dirty status flag is used for marking the corresponding region so as to indicate if the graphical object corresponding to the region is output incompatible i.e. dirty and needs to be converted to output compatible in following step . A method of marking one or more regions of the page as output incompatible as executed at step will be described below with reference to .

Then at deciding step if the processor determines that there is a further intermediate graphical object to be processed e.g. the printer driver software module has interpreted a further intermediate graphical object in the standardized file format then the method returns to step to process the further intermediate graphical object. Otherwise the method proceeds to converting step . The further intermediate graphical object is stored in the self retained display list SRDL configured within the memory .

At converting step the processor performs the step of converting the regions marked as output incompatible i.e. as dirty to output compatible regions. As described in detail below at step the processor processes the dirty status flags of the regions and converts the dirty regions into printer compatible graphical objects. A method of converting regions marked as output incompatible to output compatible regions as executed at step will be described in detail below with reference to .

At rendering step the processor performs the step of rendering the graphical object on the page using any corresponding output compatible regions. In one implementation the processor may pass the printer compatible graphical object together with corresponding drawing instructions to a rendering engine software module residing on the printer . Such a rendering engine renders the printer recognizable graphical object into pixels and prints the pixels onto the page.

The method of mapping the intermediate graphical object onto one or more corresponding regions of the page as executed at step will now be described with reference to . In the method an intermediate graphical object is mapped onto corresponding regions of the page. Each region has a bounding box and an associated dirty status flag as described above. The method may be implemented as one or more software code modules of the software application program resident on the hard disk drive and being controlled in its execution by the processor . As described above in one implementation the method may be executed by the object converter software module.

At step the processor receives a bounding box of the intermediate graphical object if the bounding box is provided in graphics properties associated with the intermediate graphical object. If the bounding box is not provided with the graphical object then the processor determines a bounding box using shape and clipping information provided with graphics properties of the graphical object.

At step the processor uses the bounding box of the graphical object to determine which regions of the page are touched by the graphical object. In particular the processor determines intersections between the bounding box of the graphical object and bounding boxes of each of the regions. If intersections are determined then the region is determined to be touched by the graphical object.

The method of marking one or more regions of the page as output incompatible as executed at step of the method will now be described below with reference to . In the method the intermediate graphical objects parsed from standardised format and stored in the self retained display list are converted to printer compatible graphical objects. The page is divided into grids of a pre determined size. Each grid is a region as described above.

The method may be implemented as one or more software modules of the software application program and being controlled in its execution by the processor .

The method begins at dirty region determining step where if the processor determines that all the regions of the page that are touched by the intermediate graphical object have an associated dirty status flag then the method concludes. Otherwise the method proceeds to step .

A region that is marked as dirty means that the graphical object corresponding to the region is output incompatible i.e. the graphical object is not in a format recognizable to the printer and needs to be converted into a printer compatible graphical object. If all the touched regions already have the dirty flag on then the method skips further processing of the intermediate graphical object.

At printer compatible determining step the processor checks all graphics properties of the received intermediate graphical object including corresponding drawing instructions used to draw the graphical object onto the page the compositing method and the clipping information. If the processor determines at step that there are any graphics properties of the graphical object that are not compatible with the printer recognizable format used by the printer i.e. the graphical object is not printer compatible then the current graphical object is considered as a printer incompatible object and the method proceeds to marking step . Otherwise the method proceeds to step .

At marking step the processor performs the step of marking the touched regions by setting the dirty flag associated with each of the touched regions to be TRUE and the processor skips further processing of the current intermediate graphical object.

If all graphics properties of the current intermediate graphical object are printer compatible at step then the current graphical object is classified as a printer compatible object and the method proceeds to image determining step .

At image determining step if the processor determines that the current intermediate graphical object is a larger than a pre determined threshold opaque image that is not going to be scaled up too much on the page to be printed then the method proceeds to step . Otherwise the method proceeds to storing step .

A maximum threshold of scaling factor of the images big image max scaled factor and a minimum threshold of the image size big image min image size may be configured within the memory . Accordingly if the current graphical object is an opaque image that is larger than the big image min image size threshold and has a scaling factor less than the big image max scaled factor threshold then all regions touched by the current graphical object are marked as dirty at step .

At storing step the intermediate graphical object is stored within the memory for printing by the rendering engine for example in a printer recognizable format.

At step the processor determines if there are any regions of the page that are fully covered by the current printer compatible graphical object. Depending on the graphics properties of the graphical object including the clipping information if a region is fully covered by the graphical object then all previous contents in the region will not be shown on the printed page. The processor marks such a region as output compatible at step by setting the dirty status flag of such a region to FALSE. The method concludes following step .

The method of converting regions marked as output incompatible to output compatible regions will be described in detail below with reference to . The method processes the dirty status of all regions of the page and converts the dirty regions into printer compatible graphical objects.

The method may be implemented as one or more software code modules of the software application program resident on the hard disk drive and being controlled in its execution by the processor . As described above in one implementation the method may be executed by the object converter software module.

The method begins at bounding box determining step where the processor performs the step of determining bounding boxes each comprising a plurality of regions marked as output incompatible i.e. the dirty regions . In particular the processor processes the dirty regions marked in accordance with the method and merges the dirty regions into groups of region sets . The groups of region sets are stored within the memory .

A method of merging regions into groups of region sets as executed at step will be described below with reference to . In the method the processor scans regions horizontally starting at a first row of dirty tiles. In particular starting at a left most dirty tile of the first row the processor attempts to merge an adjacent tile to the right of the left most dirty tile. Merging of the tiles succeeds if the adjacent tile on the right is dirty. However if the adjacent tile is not dirty then the merging of the tiles may fail depending on an area threshold as described below. The method determines a set of one or more dirty tile regions for the first row. After completing processing of the first row of dirty tiles the processor horizontally scans and merges a second row of dirty tiles in a similar manner.

After completing processing of the second row of dirty tiles the processor attempts to merge the set of dirty tiles from the first and second rows again applying an area threshold to determine whether or not to carry out the merge. The result of merging the set of dirty tiles from the first and second rows is a set of one or more dirty tile regions. Processing then continues in a similar manner for each subsequent row of dirty tiles. At completion of processing of each row a set of dirty tile regions i.e. a region set in the processed row is merged with a previous combined set of dirty tile regions.

In one implementation the processor attempts to merge the set of dirty tiles from the first and the second rows by determining a distance between the first and the second rows. If the distance satisfies a predetermined distance threshold the result of merging the set of dirty tiles is a set of one or more dirty tile regions. Processing then continues in a similar manner for each subsequent row of dirty tiles. At completion of processing of each row a set of dirty tile regions i.e. a region set in the processed row is merged with a previously combined set of dirty tile regions.

Each region set contains a group of regions of the page that forms a rectangle shape and a bounding box of a region set is determined by co ordinates start x start y of a top left region of the page and co ordinates end x end y of a bottom right region of the page. Each region set also contains information of how many regions of the page in total the region set contains i.e. num total regions and out of which how many regions are dirty regions i.e. num dirty regions . Accordingly at step the processor also performs the step of determining a proportion of the number of output incompatible regions to total number of regions in the bounding box for a corresponding region set.

At accessing step the processor accesses a region set from the memory . Then at rendering step the processor renders an image representing an area indicated by the accessed region set using information stored in the self retained display list configured within the memory . As described above the self retained display list contains the intermediate graphical objects and corresponding drawing instructions. The rendered image of the region set may be stored within the memory and contains all graphical objects in the corresponding area.

At converting step the processor converts the rendered image into the printer recognizable format corresponding to the printer . In one implementation the printer recognizable formatted image is output to the rendering engine software module as described above. Then at decision step if the processor determines that there are more region sets within memory for processing then the method proceeds to step to get a next region set. Otherwise the method concludes.

The method of merging regions into groups of region sets as executed at step will be described below with reference to . The method may be implemented as one or more software code modules of the software application program resident on the hard disk drive and being controlled in its execution by the processor . As described above in one implementation the method may be executed by the object converter software module.

As described in detail below in the method the processor marks at least one output compatible region in the particular bounding box for a region set as output incompatible in order to increase the proportion of the number of the output incompatible regions to a total number of regions above a threshold i.e a predefined merge threshold . Once the proportion of the number of regions marked as output incompatible reaches a threshold the region in the bounding box is merged by processor .

In another implementation if a region set is within a predefined distance from another region set then both the region sets are merged.

In the method all dirty regions ie. regions associated with a printer incompatible graphical object marked in accordance with the method are merged into a group of region sets.

The method begins at processing step where the processor processes each row of the regions to form a group of region sets. A method of processing each row of regions as executed at step will be described below with reference to . In the following steps to the dirty regions in each row are merged into a group of region sets where each region set is also a shape of rectangle area. Each region set also contains a group of regions including dirty and clean regions.

At first row accessing step the processor accesses a first row of the region sets stored in memory . Then at decision step if the processor determines that there are no more rows of the region sets to be processed then the method concludes. Otherwise the method proceeds to next row accessing step .

At further row accessing step the processor accesses a second row of the region sets. At scanning step after accessing a first row and a second row of the region sets the processor scans from left to right finding a candidate region set from each row to form the first two candidate region sets. As each region set has a bounding box represented by the start x start y co ordinate and the end x end y co ordinate the candidate region set is determined based on the start x co ordinate of the region set. The candidate region set with the smallest start x co ordinate is selected for each row.

At merging step the processor merges the two candidate region sets from the first row and second row to form a merged region set by executing the comparison step . If the two region sets are merged the merged region set is a new rectangle shape of regions. The new rectangle shape of regions has a bounding box determined by the min x min y and max x max y co ordinates where the min x and min y represents minimum X and minimum Y values respectively from the bounding boxes of the two candidate region sets and max x and max y represents maximum X and minimum Y values from the bounding boxes of the two candidate region sets.

The merged region set formed at step contains all regions contained in the two candidate region sets as well as all the clean regions in between the two candidate region sets to form a new rectangle shape of regions. The num total regions and num dirty regions configured within the memory for the new rectangle shape are also updated.

As part of the merging step in comparing step if the processor determines that the ratio of the dirty region region marked as output incompatible to the total number of regions is greater than or equal to a predefined threshold that initiates merging merge threshold then the method proceeds to step . Otherwise the attempted merging is deemed to have failed and the method proceeds to step .

At merging step the merged region set is stored within the memory as one of two next candidate region sets. At step the candidate region set with the larger start x co ordinate is stored in memory as one of two next candidate region sets.

At determining step if the processor finds the other next candidate region set based on the start x co ordinate from the first row and second row of the region sets stored in the memory then the method returns to step to repeat the attempted merging steps until all region sets from both the first row and the second row are processed. Otherwise the method proceeds to step . Again the region set with the smallest start x co ordinate is selected at step .

At step the processor finishes processing all region sets from the first row and the second row of region sets. The result merged region sets are stored within the memory as a new row of region sets which will be the first row of the next round of processing. Then the method repeats the steps from step where a second row of region sets is selected and merged with the first row of region sets.

The method of processing each row of regions as executed at step will now be described with reference to . The method may be implemented as one or more software code modules of the software application program resident on the hard disk drive and being controlled in its execution by the processor . As described above in one implementation the method may be executed by the object converter software module.

The method processes each row of regions of the page stored in the memory and merges the dirty regions in each row i.e. as marked in accordance with the method into a group of region sets.

The method begins at determining step where a new row of unprocessed regions stored in the memory is selected by the processor as a current row. Otherwise if the processor determines at step that all rows of the regions stored in the memory are processed then the method concludes.

At scanning step the processor scans the regions selected at step for the current row from left to right. The processor selects a first dirty region and all adjacent dirty regions following the first dirty region and merges the first dirty region and all adjacent dirty regions into a merged region set. The bounding box of the merged region set is determined based on the start x start y co ordinate of the first dirty region and the end x end y co ordinate of the last adjacent dirty region. Both num total regions and num dirty regions are equal to the total number of the adjacent dirty regions merged together at step . The merged region set is stored in memory as the first candidate region set.

At decision step if the processor determines that all groups of adjacent dirty regions have been processed for the current row then the method proceeds to step . Otherwise the method returns to step .

At merging step the processor merges a next group of adjacent dirty regions into a new region set. The new region set is stored in the memory as the second candidate region set. Then at step the processor tries to merge the first candidate and second candidate region sets and all the clean regions in between the first candidate and second candidate region sets. By merging the first candidate and second candidate region sets the merged region set is a new rectangle shape of regions whose bounding box is determined by the min x min y max x max y co ordinates where the min x and min y are the minimum X and Y value from the bounding boxes of the two candidate region sets and max x and max y are the maximum X and Y value from the bounding boxes of the two candidate region sets.

The merged region set formed at step contains all regions that were contained in the first and second candidate region sets as well as all the clean regions in between the first and second candidate region sets to form a new rectangle shape of regions. The num dirty regions of the merged region set equals the num dirty regions of the first candidate region set plus the num dirty regions of the second candidate region set. The num total regions of the merged region set equals the num total regions of the first candidate region set plus the num total regions of the second candidate region set plus the number of the clean regions in between the first candidate region set and the second candidate region set.

At decision step if the processor determines that the ratio of number of dirty region region marked as output incompatible to the total number of regions in the merged region set is greater than or equal to a predefined threshold that initiates merging merge threshold then the method proceeds to step . Otherwise the method proceeds to step .

In one implementation at decision step if the processor determines that the distance between the clean region and a region marked as dirty containing output incompatible graphical objects satisfies a predefined threshold e.g. fifty 50 pixels the clean region is marked as dirty as well. The marking of the clean region as a dirty region initiates the merging process in merging step . Otherwise the method proceeds to step .

At step the merged region set is stored in the memory as a new region set in the current row as the first candidate region set. Otherwise the second candidate region set is stored in the memory as the first candidate region set of a next round at storing step .

Following steps and the method returns to step and processing steps are repeated from step until there are no more dirty regions to be found in the current row. The next row of regions are then processed from step as described above. When all rows of regions are processed the method concludes as described above.

The methods described above will now be described further by way of example with reference to . In accordance with the example intermediate graphical objects of the page are converted to printer compatible graphical objects in accordance with the described methods.

In the example of the objects are the graphical objects in the intermediate format sent from the printer driver software module and stored in the self retained display list as described above. The objects are drawn on the page in the same order as the objects are numbered. For example an object with a smaller number e.g. the object is rendered on the page below an object with a higher number e.g. the object . The objects e.g. are rendered using a suitable compositing algorithm and the smaller numbered object e.g. as compositing background. In the example of 

In accordance with the described methods the printer compatible graphical objects are not necessarily fully opaque. However the objects i.e. object and in the example of are set as fully opaque for ease of explanation.

The page has been assigned numbers and letters in both the X and Y co ordinate direction for the purpose of naming the grided regions as presented in . Starting from the left top corner of the page the names of the regions are r A r B . . . r N r A r B . . . r N . An example of a region set combined by regions r A r B r A r B is referred to as rs A B with num total regions 4 num dirty regions 0 .

The pre defined merge threshold in the example of is set to 80 . Regions of the page touched by each graphical object as determined at step of the method i.e. in accordance with the method are as follows 

Object r B to r M r B to r M r B to r M r B to r M r B to r M r B to r M r B to r M r B to r M r B to r M 

At the beginning of the method the dirty status flag of each of the regions of the page are set to FALSE. When the object is received by the processor at step of the method the touched regions determined at step are r B r C r D r E and r F . Since object is a printer incompatible object at step of the method i.e. at step of the method the dirty flags of regions r B r C r D r E and r F are set to be TRUE.

Then at step of the method the method returns to step to get the next intermediate graphical object from the self retained display list i.e. as sent from the printer driver software module .

When object is received by the processor the touched regions determined at step include region r D which was set to be dirty in the processing of object . At step of the method since object is not an image object the method proceeds to step where the processor stores the object in printer recognizable format in the memory for printing by the rendering engine software module for example. At step of the method since object is a fully opaque printer compatible object and region r D is fully covered by object the processor sets the dirty flag of region r D back to be FALSE. Then the method returns to step to get the next intermediate graphical object from the self retained display list i.e. as sent from the printer driver software module .

When the object is received by the processor since the object is a non image printer compatible object the processor stores the object in printer recognizable format in the memory as at step for printing by the rendering engine software module. The method then returns to step to get a next intermediate graphical object from the self retained display list i.e. as sent from the printer driver .

When the object and object are received by the processor at step of the method the touched regions determined at step are r K r J r K r L r L r M r N and r M . Since object is a printer incompatible object at step of the method i.e. at step of the method the dirty flags of the regions r K r J r K r L r L r M r N and r M are set to be TRUE. Then at step of the method the method returns to step to get the next intermediate graphical object from the self retained display list configured within the memory .

When object is received by the processor at step of the method since the object is a non image printer compatible object the processor stores the object at step in printer recognizable format in the memory for printing by the rendering engine software module for example. The dirty flags of the regions that are touched by object are not changed. The method then returns to step to get the next intermediate graphical object from the self retained display list configured in the memory .

When the object is received by the processor at step of the method the touched regions determined at step are r F r G r H r E r F r G r H r I r F r G and r H . Since object is a printer incompatible object at step of the method i.e. at step of the method the dirty flags of the regions r F r G r H r E r F r G r H r I r F r G and r H are set to be TRUE. Then at step of the method the method returns to step to get the next intermediate graphical object from the self retained display list configured within the memory .

When object is received by the processor the touched regions determined at step includes region r H which was set to be dirty in the processing of object . At step of the method since object is not an image object the method proceeds to step where the processor stores the object in printer recognizable format in the memory for printing by the rendering engine software module for example. At step of the method since object is a fully opaque printer compatible object and region r H is fully covered by object the processor sets the dirty flag of region r H back to be FALSE. Then the method returns to step to get the next intermediate graphical object sent from the self retained display list i.e. as sent from the printer driver .

When object is received by the processor at step of the method the touched regions determined at step are r B to r M r B to r M r B to r M r B to r M r B to r M r B to r M r B to r M r B to r M r B to r M . Since object is a non scaled printer compatible image object that is larger than a predefined big image max scaled size with zero 0 scaling factor the result of step is TRUE i.e. the yes arrow is followed at step . The method then proceeds to step and sets dirty status flag of the regions touched by object to be TRUE without storing the object in memory for subsequent rendering by the rendering engine software module even though the object is printer compatible. Then at step of the method the method returns to step to get the next intermediate graphical object from the self retained display list configured within the memory .

When objects and are received by the processor at step since the dirty status flags of the touched regions that are determined at step are all already set to TRUE during processing object the results of step of the method are always TRUE for the process of processing objects and . The method skips any further processing and the method returns to step to get the next intermediate graphical object from the self retained display list configured within the memory . Since there are no more objects on the page to be processed at step the method proceeds to step where any regions marked as output incompatible are converted to output compatible regions. At this stage of the example the dirty status of the regions on the page is as shown in . In accordance with the example of below is a list of the dirty regions from each row of the page 

At step of the method the processor first executes the method to merge the dirty regions of the page shown in to form region sets.

At step of the method the processor first executes the method to process each row of the regions of the page .

At step the processor first gets Row of the regions of the page . At step the processor merges regions r B and r C to region set rs B C with num total regions 2 num dirty regions 2 .

At step the processor merges regions r E and r F to region set rs E F with num total regions 2 num dirty regions 2 .

At steps and the processor tries to merge the region sets rs B C and rs E F to be rs B F with num total regions 5 num dirty regions 4 . Since num dirty regions num total regions 0.8 merge threshold 80 the processor goes to step and stores the rs B F in the memory to be the new region set for the current row.

At step the processor merges regions r K r L r M and r N to region set rs K N with num total regions 4 num dirty regions 4 . At step and the processor tries to merge the region sets rs B F and rs K N to be rs B N with num total regions 13 num dirty regions 8 . Since num dirty regions num total regions 0.61

At step since there are no more dirty regions on the current row the method proceeds to step and accesses Row of the regions. At this stage the result region sets for Row are rs B F rs K N .

When Row of the regions of page are processed in accordance with the method since there is only one group of adjacent dirty regions on the current row the result region sets for Row are rs J M .

Similar to Row after the other rows of the regions of page have been processed the result region sets for page are as follows 

After the last row Row of the page is processed in accordance with the method the method proceeds to step to get the region sets from Row and then gets the region sets from Row at step . At step the processor gets region sets rs B F from Row and rs J M from Row as two candidate region sets to be merged.

At step and of the method the processor tries to merge the two candidate region sets rs B F and rs J M to be rs B M with num total regions num dirty regions 11 . Since num dirty regions num total regions 0.46

At steps and the processor tries to merge the two candidate region sets rs K N and rs J M to be rs J N with num total regions 10 num dirty regions 8 . Because num dirty regions num total regions 0.8 merge threshold 80 the method proceeds to step merges the two candidate region sets to be the new candidate region set and proceeds to step to find the next unprocessed region set from Row and Row of the page . Since there are no more region sets on rows Row and Row the method goes to step where the processor merges the region sets from Row and Row to one row as 

The method then returns to step to get region sets on Row as the next row to be merged with the new Row described above. At step and the processor tries to merge the two candidate region sets rs B F and rs F H to be rs B H with num total regions num dirty regions 7 . Since num dirty regions num total regions 0.18

The method then returns to step to get region sets on Row as the next row to be merged with the Row . At steps and the processor tries to merge the two candidate region sets rs F H and rs E I to be rs E I with num total regions 10 num dirty regions 8 . Since num dirty regions num total regions 0.8 merge threshold 80 the method proceeds to step then to step with the result of the new Row as 

The method then returns to step to get region sets on Row as the next row to be merged with the new Row as described above. At steps and the processor tries to merge the two candidate region sets rs E I and rs F G to be rs E I with num total regions 15 num dirty regions 10 . Since num dirty regions num total regions 0.67

The method then returns to step to get region sets on Row as the next row to be merged with the Row described above. At step and the processor tries to merge the two candidate region sets rs F G and rs B M to be rs B M with num total regions 60 num dirty regions 14 . Because num dirty regions num total regions 0.23

The method then returns to step to get region sets on Row as the next row to be merged with the Row described above. At step and the processor tries to merge the two candidate region sets rs B M and rs B M to be rs B M with num total regions 24 num dirty regions 24 . Since num dirty regions numtotal regions 1 merge threshold 80 the method proceeds to step then with the result of the new Row as follows 

Similarly after processing the last row Row of region sets the processor merges all region sets from Row to Row to be a new Row as follows 

At step since there are no new rows to be processed the processor proceeds to step . The final result from method is as shown in . Below is a list of the merged region sets to be output after the method .

In another implementation instead of checking the num dirty regions num total regions against a predefined threshold the distance between a dirty region and a clean region is checked against a predetermined distance threshold. If the distance between the dirty candidate region set and the clean candidate region set is smaller than the predetermined threshold then the dirty region and clean region are merged into one region set.

The arrangements described are applicable to the computer and data processing industries and particularly for the image processing.

The foregoing describes only some embodiments of the present invention and modifications and or changes can be made thereto without departing from the scope and spirit of the invention the embodiments being illustrative and not restrictive.

In the context of this specification the word comprising means including principally but not necessarily solely or having or including and not consisting only of . Variations of the word comprising such as comprise and comprises have correspondingly varied meanings.

