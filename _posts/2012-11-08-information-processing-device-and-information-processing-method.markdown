---

title: Information processing device and information processing method
abstract: A non-transitory computer-readable recording medium storing a program that causes a computer to execute a process including receiving a setting of an anchor to a subject in an image included in a video; determining whether a movement amount between the subject to which the anchor has been set in a predetermined image in the video and the subject in another image included in the video is greater than or equal to a predetermined value; and storing, in a storage unit, an identifier of the another image that is a determination target, and position information of the anchor, when the movement amount is determined to be greater than or equal to the predetermined value.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09380259&OS=09380259&RS=09380259
owner: FUJITSU LIMITED
number: 09380259
owner_city: Kawasaki
owner_country: JP
publication_date: 20121108
---
This patent application is based upon and claims the benefit of priority of the prior Japanese Patent Application No. 2011 282403 filed on Dec. 22 2011 the entire contents of which are incorporated herein by reference.

The embodiments discussed herein are related to an information processing device and an information processing method.

Conventionally there is known a method of performing a link operation in a hyper media environment using videos where an anchor is displayed on a subject of the video a link is tied to the anchor and the anchor is specified in the video. In the following the subject is also referred to as an object.

For example there is a technology of setting an anchor in an arbitrary area moving in the video storing anchor information and link information and dynamically displaying the anchor based on display attributes of the video and the anchor.

An anchor may be set to an object in the video by a method of for example extracting the shape of the object by extracting edges in each frame in the video and furthermore extracting the error between frames to extract the movement of the object. An anchor is for example an element set in a hyperlink.

When an object that is the target for setting an anchor moves in the video in the conventional technology the position coordinates of the object in each frame are identified and the position of the anchor is defined by the frame number and the position coordinates of the object.

Meanwhile there may be cases of editing the anchor that has already been set in the object. For example it is assumed that an object is extracted by edge extraction and an anchor positioned at this object. Depending on the precision of edge extraction there may be a difference between the position or shape of the object in an image viewed by a person and the position or shape of the object recognized by the computer according to edge extraction. In this case there arises the operation of changing the position of the anchor in the frame so that the anchor is superposed on the object as viewed by a person. In the following this operation is also referred to as an editing operation.

However if the position coordinates of the object in each frame are identified and the position of the anchor is defined by a frame number and position coordinates there will be a number of definitions of anchor positions corresponding to the number of frames. Therefore the data amount relevant to anchor positions becomes large.

Assuming that an operation of editing the anchor position is performed for the definitions of anchor positions present in the respective frames changes will be made for the respective definition data items corresponding to the number of frames. This is a time consuming process for the editor.

According to an aspect of the embodiments a non transitory computer readable recording medium storing a program that causes a computer to execute a process including receiving a setting of an anchor to a subject in an image included in a video determining whether a movement amount between the subject to which the anchor has been set in a predetermined image in the video and the subject in another image included in the video is greater than or equal to a predetermined value and storing in a storage unit an identifier of the another image that is a determination target and position information of the anchor when the movement amount is determined to be greater than or equal to the predetermined value.

The object and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the appended claims. It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the invention as claimed.

Preferred embodiments of the present invention will be explained with reference to accompanying drawings.

The information processing device may have a function of editing a set anchor. The information processing device may have a function of displaying or reproducing a link destination associated with an anchor when the anchor is pressed or instructed while a video is being reproduced.

The information processing device illustrated in includes an anchor information generating unit an operation unit a link definition storage unit a video data storage unit an anchor information editing unit a reproduction control unit and a display unit .

The anchor information generating unit first reads and acquires a video from the video data storage unit and receives a frame for setting an anchor and a setting of the anchor position. The anchor information generating unit has a function of automatically extracting from a subsequent frame an object on which an anchor is set and causing the anchor to follow the object.

When the object is automatically extracted the anchor information generating unit determines whether to store the position of the anchor depending on the movement amount of the object or anchor. Accordingly the anchor information need not be stored for every frame and therefore the data amount of the anchor information is reduced.

For realizing the above functions the anchor information generating unit includes a setting unit an extracting unit and a determining unit . The setting unit receives from the operation unit a frame for setting an anchor among the frames included in a video and the position of the anchor in the received frame.

The position of the anchor is expressed by coordinates in a frame and is also referred to as anchor position information. The setting unit outputs an identifier indicating the received frame and anchor position information to the extracting unit . The identifier indicating the frame is also referred to as a frame identifier which may be a frame number or a time code or time stamp indicating the reproduction time from the beginning of the video.

The extracting unit automatically extracts from a frame in which an anchor is set the area of an object with the use of an image recognition technology around the position where the anchor is set. For example the extracting unit automatically extracts coordinates of the object area that is recognized by performing edge extraction. The coordinates of the object are for example the center coordinates of the object area.

The extracting unit tracks the extracted object in the subsequent frames and outputs the recognized object coordinates to the determining unit .

The determining unit determines whether the recognized object has moved by a movement amount that is greater than or equal to a predetermined length from the object inside another frame. For example the determining unit determines whether the movement amount between the object in the present frame and the object in a frame immediately before the present frame is greater than or equal to a predetermined value. Accordingly the determining unit may determine a case where the movement amount of the object is large within a short period of time.

The movement amount may be for example the difference in object coordinates between frames and the movement of the object area on which an inter frame error extraction process is performed. Furthermore the movement amount may be the movement amount of the center coordinates of the anchor.

The predetermined value is for example the size of one object extracted at the extracting unit . Furthermore the predetermined value may the size of the anchor and may be a value that is appropriately set according to experiments.

Furthermore the determining unit determines whether the movement amount between the object of the present frame and the object in a newest frame that is stored in the link definition storage unit described below or a newest frame that is a storage target is greater than or equal to a predetermined value. Accordingly the determining unit determines a case where the object has moved by a movement amount that is greater than or equal to a predetermined value from the position that is the determination reference as a result of moving by small amounts.

The newest frame that is stored in the link definition storage unit or a newest frame that is a storage target is a frame before the present frame and closest to the present frame.

Furthermore the determining unit may determine whether a negative determination result indicating that the movement amount of the object is less than a predetermined value has continued for more than or equal to a predetermined time period. Furthermore the determining unit may determine whether the frame is the final frame or the first frame in which an anchor is set by a user. A final frame means the last frame in which the subject having a set anchor is displayed or the final frame in the video.

The determining unit includes a generating unit . When the determining unit determines that the movement amount is greater than or equal to a predetermined value the generating unit generates a frame identifier and anchor position information of the determination target and stores the generated information in the link definition storage unit . The anchor position information is for example the center coordinates of the extracted object.

When the present frame and the frame immediately before the present frame are determination targets the generating unit associates the frame identifier of the present frame with the anchor position information of the present frame associates the frame identifier of the frame immediately before the present frame with the anchor position information of the frame immediately before the present frame and stores these in the link definition storage unit .

When the present frame and the newest frame stored in the link definition storage unit are the determination targets the generating unit associates the frame identifier of the present frame with the anchor position information of the present frame and stores these in the link definition storage unit . In the following information including the frame identifier and the anchor position information of the present frame is also referred to as anchor information. The generating unit is described as being included in the determining unit however the generating unit may be a different unit from the determining unit .

When the movement amount of less than a predetermined value continues for more than or equal to a predetermined time period or when the present frame is the final frame or when the present frame is the first frame having an anchor set the generating unit associates the frame identifier of the present frame with the anchor position information and stores these in the link definition storage unit .

Accordingly when setting an anchor the anchor information generating unit need not define anchor information for each frame. Furthermore the anchor information generating unit only stores anchor information for a frame where the movement amount of an object having an anchor set is large and therefore the data amount of anchor information is reduced.

The operation unit has a GUI Graphical User Interface operation function and sets the anchor position sets the link destination to be associated with the anchor edits the anchor position instructs reproduction of the video and selects an anchor. When the above operations are received from a user the operation unit reports the operation contents to the respective units.

The link definition storage unit stores the anchor information generated at the anchor information generating unit . The anchor information includes the anchor position information first set by the user and the frame identifier of this anchor position information. Furthermore the anchor information includes information of the link destination associated with the anchor. The anchor information is described below with reference to .

The video data storage unit stores video data. The video data is for example contents for setting an anchor associated with a link destination. Examples of the video data are an operation manual for a mobile terminal and a checkup manual for a private car.

The link definition storage unit and the video data storage unit are described as different storage units but may the same storage device. Examples of the link definition storage unit and the video data storage unit are a RAM Random Access Memory such as a VRAM Video Random Access Memory and a semiconductor memory device such as a ROM Read Only Memory and a flash memory. As the link definition storage unit and the video data storage unit a storage device such as a hard disk and an optical disk may be applied.

The anchor information editing unit edits the position information of an anchor set in a video. The anchor information generating unit automatically generates anchor position information and therefore the position may be different from the object in the actual video. Therefore in this case the editor has to edit the anchor position. The anchor information editing unit has a function of facilitating the operation of editing the anchor information.

The anchor information editing unit includes an editing unit and a changing unit . The editing unit uses a video stored in the video data storage unit and anchor information stored in the link definition storage unit to reproduce a video in which an anchor is displayed.

At this time the editing unit controls the operation of displaying on the display unit an edit screen in which it is possible to edit the anchor position and the link destination. When an anchor is edited with the use of an editing screen displayed on the display unit the editing unit receives an editing operation relevant to the anchor from the operation unit .

For example the editing unit receives changes in the anchor position and changes in the link destination associated with the anchor from the operation unit . The editing unit reports the contents of user operations received from the operation unit such as the frame identifier of an edited frame and changed anchor position information to the changing unit .

The changing unit changes the anchor information stored in the link definition storage unit based on operation contents acquired from the editing unit . For example the operation contents include a frame identifier and the edited anchor position information.

In this case the changing unit searches the anchor information stored in the link definition storage unit for a frame identifier matching the frame identifier included in the acquired operation contents. The changing unit changes the anchor position information associated with the matching frame identifier to the edited anchor position information.

Accordingly the editing operation only needs to be performed on the frame stored in the link definition storage unit and therefore the editing operation is facilitated.

The reproduction control unit performs a control operation to read and acquire video data from the video data storage unit read and acquire anchor information from the link definition storage unit and reproduce a video in which an anchor is superposed on the display unit .

The reproduction control unit includes a drawing unit and a link contents reproducing unit . When a frame indicated by the frame identifier stored in the anchor information is displayed on the display unit the drawing unit draws an anchor at a position indicated by the anchor position information and superposes the anchor on the video.

When a frame other than the frame indicated by the frame identifier stored in the link definition storage unit is displayed the drawing unit performs interpolation calculation and continuously displays the anchor. Interpolation calculation is performed by linearly interpolating the respective anchor position information items corresponding to two frames positioned before and after the frame that is the display target among the frames stored in the link definition storage unit . The drawing unit draws the anchor that has undergone linear interpolation by for example animation drawing.

Accordingly the drawing unit does not need to repeatedly draw all anchor pixels for every displayed frame. Only the anchor that has undergone linear interpolation is displayed. Therefore the drawing unit only needs to repeatedly draw the requisite minimum amount of pixels. The requisite minimum amount of pixels means the pixels that have been changed. Therefore it is possible to prevent the anchor image from flickering compared to the case of repeatedly drawing all anchor pixels.

When an anchor is pressed a report is received from the operation unit that an anchor has been selected and the link contents reproducing unit moves to the link destination associated with the anchor and reproduces for example video hyperlink contents on the display unit .

Various integrated circuits and electric circuits may be used as the anchor information generating unit the anchor information editing unit and the reproduction control unit . Examples of an integrated circuit are an ASIC Application Specific Integrated Circuit and a FPGA Field Programmable Gate Array . Examples of an electric circuit are a CPU Central Processing Unit and a MPU Micro Processing Unit .

Next a description is given of a data structure of anchor information stored in the link definition storage unit . illustrates an example of a data structure of anchor information. As illustrated in the anchor information includes an anchor identifying name name an anchor type type and anchor area size link destination information link the frame position or the elapsed time time used for synchronizing with video data indicating data data relevant to the anchor and anchor position information px py indicating coordinates of an anchor on a screen.

The anchor type indicates an icon or a link type. The anchor area indicates the size of a click range. Coordinates on the screen are indicated by using the original size of the video as a standard.

The data data has a hierarchal structure and may include plural items of time and px py . Either the frame position or elapsed time may be used as long as it is a value for identifying the frame in the video such as a frame number.

Next a description is given of an example of anchor information. illustrates an example of anchor information. In the example illustrated in the anchor information is expressed by XML Extensible Markup Language .

For example the anchor identifying name is sampleA the anchor type is LINK the anchor area is 60 and the link destination information is nextset . In the example of four sets of frame identifiers and anchor position information items are held. The frame identifiers and anchor position information items are information generated by the anchor information generating unit .

Next automatic generation of an anchor position is specifically described. is a diagram for describing automatic generation of an anchor position. In the example illustrated in frames t through t are displayed in order. Furthermore in the frame of t the user has specified an object subject for setting an anchor.

At this time the anchor information generating unit extracts the edges around the specified object and extracts the object area. The anchor information generating unit uses the center coordinates of the extracted object area as anchor position information associates an identifier for example a time code of the frame t with this anchor position information and stores this information in the link definition storage unit .

Next the anchor information generating unit extracting unit tracks the object in the frame t and obtains the movement amount of the object from the frame t by an inter frame error extraction process. The anchor information generating unit determining unit determines whether the movement amount is greater than or equal to a predetermined value and at this point it is determined that the movement amount is less than the predetermined value. The predetermined value is assumed to be the object size in this example.

Next the anchor information generating unit extracting unit tracks the object in the frame t and obtains the movement amount of the object from the frame t. The anchor information generating unit determining unit determines whether the movement amount is greater than or equal to the predetermined value and at this point it is determined that the movement amount is greater than or equal to the predetermined value.

The anchor information generating unit generating unit stores the frame identifiers of t and t and the anchor position information of the frames of t and t in the link definition storage unit . In this example the frame identifier is a time code and the anchor position information is the center coordinates of the object.

Next the anchor information generating unit extracting unit tracks the object in the frame and obtains the movement amount of the object from the frame t. The anchor information generating unit determining unit determines whether the movement amount is greater than or equal to the predetermined value and at this point it is determined that the movement amount is greater than or equal to the predetermined value. The frame identifier of t and the anchor position information are already stored in the link definition storage unit and therefore the anchor information generating unit generating unit stores the frame identifier of t and the anchor position information of the frame t in the link definition storage unit .

Accordingly there is no need to define the anchor in all frames after the frame in which the anchor is set and therefore the data amount of the anchor information is reduced.

Next a description is given of a specific example in which a battery pack of a mobile terminal is the object. are for describing an example of automatic generation and editing of the anchor position. In the example of a battery pack of a mobile terminal is set as the object.

The anchor information generating unit setting unit reads and acquires the target video from the video data storage unit . At this time the start frame of the displayed video is the image inside a screen d.

Next in screen d the user sets an anchor an at the position of the battery pack. For example the anchor an is set by pressing a link button so that the anchor an is displayed on the screen d and by moving the position of this anchor an.

First when an anchor is set the anchor information generating unit tracks the object in which the anchor is set to automatically generate an anchor position where the movement amount of the object is large.

The screen d is for previewing the anchor position information that has been automatically generated and for confirming the anchor position.

The screen d is a screen for editing the anchor position that has been automatically generated. The user identifies the frame for adjusting the position by frame by frame advance and moves an anchor an displayed in the identified frame to a desired position by a drag operation.

Accordingly the editor only needs to confirm the anchor position information in the frame indicated by the frame identifier stored in the link definition storage unit and does not need to confirm the position of the anchor in all of the frames. Therefore the editing operation is easy.

Next a description is given of a structure of the video and the drawing of the anchor. illustrates an example of drawing an anchor. In the example of a layer for drawing an anchor is superposed on a layer for reproducing a video. By this structure the anchor may be superposed on an object in a video that is being reproduced.

The drawing unit performs interpolation calculation based on the position of the anchor to be drawn for frames other than the frame indicated by the frame identifier stored in the link definition storage unit to draw the anchor by animation drawing for example.

For example the anchor of frame t is displayed in the middle of the anchor position of frame t and the anchor position of t. Furthermore the anchors of frames t through t are displayed at positions obtained by performing interpolation calculation on the anchor positions of frame t and the anchor position of frame t.

The anchors displayed in frames t t t and t of are the editing targets. In the general technology the anchor position information of frames t through t is stored and the anchors of frames t through t are editing targets.

Accordingly in the present embodiment the anchors are not drawn by repeatedly drawing all pixels of the anchor in every frame the anchors may be drawn by a drawing method based on the animation of coordinate movement. Therefore it is possible to smoothly display the anchor without flickering.

Next a description is given of a specific example in which a micro SD card of a mobile terminal is the object. is for describing the link destination display. The example of is a video for describing the operation of inserting a micro SD card in a mobile terminal. Furthermore in the example of an anchor is set at the micro SD card.

The screen d displays the mobile terminal in which the micro SD card is to be inserted. The reproduction control unit reads the target video from the video data storage unit reads the anchor information from the link definition storage unit and reproduces the image of a screen d. At this time an anchor is not set in the screen d.

In a screen d a hand holding a micro SD card is displayed and an anchor is superposed on the micro SD card. When a frame indicated by a frame identifier included in the anchor information is reproduced the drawing unit draws the anchor in the frame. In a screen d the anchor is drawn.

In a screen d the micro SD card is being inserted in the mobile terminal. At this time it is assumed that an anchor an in the image of the screen d is selected. The anchor an is drawn to follow the micro SD card while the video is being reproduced.

At this time for frames for which anchor information is not stored interpolation calculation for example linear interpolation of coordinates is performed and the anchor is continuously displayed. Selection of the anchor may be detected when the anchor is clicked with a mouse or when the anchor is pressed in a touch panel.

In a screen d one frame of the video that is the link destination associated with the anchor is displayed. When a report that the anchor an has been selected is received the link contents reproducing unit links to the link destination information included in the anchor information and reproduces the video of the link destination. In a screen d the position where the micro SD card is to be inserted is enlarged.

Accordingly even in frames for which anchor information is not stored the anchor is continuously displayed. When the anchor is selected it is possible to move to the link destination and reproduce the linked video.

Next a description is given of an operation of the information processing device . is a flowchart indicating an example of an anchor setting process. At step S of the anchor information generating unit reads and acquires the target video from the video data storage unit . Here the anchor information generating unit reproduces the target video regularly or reproduces the target video by frame by frame advance and waits for an object for setting an anchor to be specified.

At step S the setting unit receives from the operation unit an object for setting an anchor specified by a user. At this time the setting unit identifies a start frame in which position coordinates of an object and an anchor are set. The position coordinates of an object are for example the center coordinates of the anchor in a case where a specification is made as indicated in the screen d of .

At step S the extracting unit extracts object coordinates by performing image recognition for each frame after the start frame in the video. For example the extracting unit extracts the object area by edge extraction and uses the center coordinates of the object area as object coordinates.

At step S the determining unit identifies the frame for which anchor information is to be saved based on the movement amount of the object coordinates between the present frame and another past frame other than the present frame. The process of step S is described below with reference to .

In step S the anchor information generating unit additionally sets the attribute of the anchor information. The attribute of the anchor information is for example the display attribute and a name of a link destination.

In step S the generating unit stores as anchor information a frame identifier and anchor position information of a frame identified as a saving target in the link definition storage unit .

In step S the anchor information editing unit previews the set anchor and determines whether a position change request is reported from the operation unit . When there is a position change request YES at step S the process proceeds to step S and when there is no position change request NO at step S the process ends.

At step S the changing unit edits the anchor position information. For example the changing unit acquires the frame identifier of the frame that is the editing target and the anchor position information after being edited and changes the anchor position information of the frame that is the editing target stored in the link definition storage unit to the anchor position information after being edited.

Next a detailed description is given of the process of step S. is a flowchart of an example of a process of generating anchor information. At step S of the generating unit sets the start frame as the present frame and specific data. A present frame is a frame used as a standard of a determination target. Specific data is data that is a target for being stored in the link definition storage unit .

At step S the determining unit increments the present frame. By incrementing the present frame the present frame becomes the next frame in the display time order.

At step S the determining unit sets the object coordinates of the present frame and a previous frame as comparison targets. A previous frame is for example a frame immediately before the present frame.

At step S the determining unit determines whether the absolute value of the movement amount indicating the difference in the object coordinates is greater than or equal to a predetermined value object size . In the following the movement amount indicating the difference in object coordinates is also referred to as an object movement amount. When the absolute value of the object movement amount is greater than or equal to the object size YES at step S the process proceeds to step S and when the absolute value of the object movement amount is less than the object size NO at step S the process proceeds to step S. When the absolute value of the object movement amount is greater than or equal to the object size it means that the object has moved so that the object areas do not overlap each other between frames.

At step S the determining unit determines whether the absolute value of the object movement amount is greater than or equal to a predetermined value anchor size . When the absolute value of the object movement amount is greater than or equal to the anchor size YES at step S the process proceeds to step S and when the absolute value of the object movement amount is less than the anchor size NO at step S the process proceeds to step S. When the absolute value of the object movement amount is greater than or equal to the anchor size it means that the object has moved more than the length the width or the diagonal line of the anchor between frames.

The reason why the determination at step S is made is because when the size of the object is large the determination is rarely YES at step S. Therefore in a case where the object has moved by an amount greater than or equal to the anchor size this present frame is set as specific data.

At step S the generating unit sets the present frame and a previous frame as specific data. When the previous frame is already set as specific data the generating unit only sets the present frame as specific data.

The processes at steps S and S are for distinguishing a case where the movement amount between adjacent frames is large. Accordingly it is possible to identify a case where the object has moved by a large amount instantaneously and use the present data as specific data.

At step S the determining unit sets the object coordinates of the specific data immediately before the present frame and the present frame as comparison targets. The specific data immediately before the present frame means the frame that is displayed last newest among the specific data items.

At step S the determining unit determines whether the absolute value of the object movement amount is greater than or equal to a predetermined value object size . When the absolute value of the object movement amount is greater than or equal to the object size YES at step S the process proceeds to step S and when the absolute value of the object movement amount is less than the object size NO at step S the process proceeds to step S.

At step S the determining unit determines whether the absolute value of the object movement amount is greater than or equal to a predetermined value anchor size . When the absolute value of the object movement amount is greater than or equal to the anchor size YES at step S the process proceeds to step S and when the absolute value of the object movement amount is less than the anchor size NO at step S the process proceeds to step S.

The processes of steps S and S are for distinguishing cases where the object has slowly moved from the frame of the specific data and the movement amount from the object of the specific data is large. Accordingly it is possible to specify a case where the object has moved slowly and the object has moved by greater than or equal to a predetermined amount from the position of the object of the specific data and set present frame as the specific data.

At step S the determining unit determines whether the frame interval between the specific data immediately before the present frame and the present frame is greater than or equal to a set standard value threshold . The threshold is for example 3 seconds or 5 seconds however a more appropriate value may by set based on experiments. When the frame interval is greater than or equal to the threshold YES at step S the process proceeds to step S and when the frame interval is less than the threshold NO at step S the process proceeds to step S.

The reason for making the determination at step S is to cause the anchor to follow subtle movements of the object and to set the present frame as the specific data at predetermined intervals.

At step S the determining unit determines whether the present frame is the final frame. When the present frame is the final frame YES at step S the process proceeds to step S and when the present frame is not the final frame NO at step S the process returns to step S.

At step S the generating unit sets the final frame as the specific data. The reason why the final frame is the specific data is that the position of the anchor of the final frame is used for interpolation calculation.

By the above process there is no need to store the anchor information for all frames and therefore the data amount of the anchor information is reduced.

Next a description is given of a process of reproducing a video in which an anchor is set. is a flowchart indicating an example of a video reproduction process. At step S of the reproduction control unit reads the target video from the video data storage unit and reads anchor information from the link definition storage unit .

At step S the reproduction control unit reproduces the read video data. At step S the drawing unit determines whether to draw an anchor. For example the drawing unit determines whether a frame which is between a frame indicated by the first frame identifier included in the anchor information and a frame indicated by the last frame identifier included in the anchor information is reproduced. When an anchor is to be drawn YES at step S the process proceeds to step S and when an anchor is not to be drawn NO at step S the process returns to step S.

At step S the drawing unit determines whether there is anchor position information associated with the frame that is the reproduction target. When there is anchor position information YES at step S the process proceeds to step S and when there is no anchor position information NO at step S the process proceeds to step S.

At step S when the frame indicated by the frame identifier included in the anchor information is reproduced the drawing unit draws an anchor at a position indicated by the anchor position information in synchronization with the frame or the reproduction time of the video data. For example the anchor is a link icon.

At step S the drawing unit obtains the display position of the anchor by performing interpolation calculation on the anchor position information present before and after the frame that is the display target. The drawing unit moves the anchor to the obtained position and draws the anchor there.

At step S the link contents reproducing unit determines whether the anchor has been selected. When the anchor is selected YES at step S the process proceeds to step S and when the anchor is not selected NO at step S the process proceeds to step S.

At step S the link contents reproducing unit reproduces the video of the link destination associated with the anchor. The link destination may not be a video the link destination may be a still image or text.

At step S the link contents reproducing unit determines whether the button for returning from the link destination to the video has been pressed. When the button has been pressed to return to the video YES at step S the process returns to steps S and when the button has not been pressed to return to the video NO at step S the process returns to steps S.

At step S the reproduction control unit determines whether the target video has ended. When the video has ended YES at step S the reproduction process is ended and when the video has not ended NO at step S the process returns to step S.

By the above process it is possible to reproduce a video in which an anchor is set. Furthermore at step S by performing for example an animation drawing process it is possible to prevent the anchor from flickering.

According to the above embodiment the anchor is easily edited and the data amount of anchor information is reduced.

The control unit is a CPU for controlling the respective devices and performing calculation and processing on the data in a computer. Furthermore the control unit is an arithmetic device for executing programs stored in the main storage unit and the secondary storage unit . These programs are for executing information processing described in the above embodiment with reference to .

The control unit may realize the information processing described in the embodiment by executing these programs.

The main storage unit is a ROM Read Only Memory or a RAM Random Access Memory and is a storage device for storing or temporarily saving programs such as an OS that is the basic software and application software executed by the control unit and data.

The secondary storage unit is a HDD Hard Disk Drive and is a storage device for storing data relevant to application software.

The drive device reads programs from a recording medium such as a flexible disk and installs the programs in the storage device.

Furthermore a predetermined program is stored in the recording medium and the program stored in the recording medium is installed in the information processing device via the drive device . The predetermined program that has been installed may be executed by the information processing device .

The network I F unit is an interface between the information processing device and peripheral devices having communication functions that are connected via a network such as a LAN Local Area Network or a WAN Wide Area Network that are constituted by wired or wireless data transmission paths.

The input unit includes a keyboard having cursor keys a numeric keypad and various function keys and a mouse or a slice pad for selecting keys on the display screen of the display unit . Furthermore the input unit is a user interface for the user to give operation instructions to the control unit and to input data.

The display unit is a CRT Cathode Ray Tube or an LCD Liquid Crystal Display and displays information according to display data input from the control unit .

As described above the image processing described in the above embodiment may be implemented as programs to be executed by a computer. By installing these programs from a server and causing a computer to execute these programs the above information processing may be implemented.

Furthermore the programs may be recorded in the recording medium and a computer or a mobile terminal may be caused to read the recording medium recording these programs to implement the above information processing. Various types of recording media may be used as the recording medium including a recording medium for optically electrically or magnetically recording information such as a CD ROM a flexible disk and a magnetic optical disk and a semiconductor memory for electrically recording information such as a ROM and a flash memory. The recording medium does not include carrier waves. Furthermore the information processing described in the above embodiments may be implemented by one or more integrated circuits.

For example the above embodiment and modification may be applied to a device for creating a commentary document an operation manual and educational contents using videos.

According to an aspect of the embodiments the anchor is easily edited and the data amount of anchor information is reduced.

The present invention is not limited to the specific embodiments described herein and variations and modifications may be made without departing from the scope of the present invention.

All examples and conditional language recited herein are intended for pedagogical purposes to aid the reader in understanding the invention and the concepts contributed by the inventor to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although the embodiments of the present invention have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

