---

title: Information processing apparatus and control method thereof
abstract: An apparatus having an OS to perform exclusive control among programs that are based on a predetermined API on a channel for communicating with a peripheral, a first driver for the peripheral to startup based on a request that is based on the predetermined API and communicate with the peripheral via the channel, a second driver for the peripheral to startup based on a request that is not based on the predetermined API and communicate with the peripheral via the channel, a program to communicate with the peripheral via the channel, and a controller to, when the second driver is started up based on a request that is not based on the predetermined API, if the program is using the channel, close the channel that the program is using based on exclusive control by the OS by starting the first driver.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08869175&OS=08869175&RS=08869175
owner: Canon Kabushiki Kaisha
number: 08869175
owner_city: Tokyo
owner_country: JP
publication_date: 20121114
---
This application is a continuation of application Ser. No. 13 093 639 filed Apr. 25 2011 that claims the benefit of Japanese Patent Application No. 2010 102525 filed Apr. 27 2010 both of which are hereby incorporated by reference in their entirety.

The present invention relates to an information processing apparatus for controlling a peripheral apparatus and a control method thereof.

Conventionally an image reading apparatus e.g. a dedicated scanner and a multifunction peripheral that includes a printer etc. is one example of a peripheral apparatus. An image reading apparatus operating as such a peripheral apparatus reads an image based on an instruction from a scanner driver that is installed in an information processing apparatus such as a computer.

Further for such an image reading apparatus a technology is known in which an operation unit provided in the image reading apparatus issues a read instruction to start image reading and the read image is transferred to the information processing apparatus see Japanese Patent Application Laid Open No. 11 355481 .

To detect on the information processing apparatus side the fact that a user has issued a read instruction from the operation unit of the image reading apparatus a button monitoring program can be used to monitor a button event of an image input apparatus such as the scanner in the information processing apparatus. If the button monitoring program detects an event indicating that the button for instructing the image reading apparatus to start reading has been operated image reading is executed in the following manner and the information processing apparatus acquires the image data obtained by reading the image.

If the button monitoring program detects an event first a predetermined application is called up. This application is registered as an application to be started when the button is pressed. Then the application calls up a scanner driver e.g. a tool without an interesting name TWAIN driver based on the TWAIN standard and causes the image reading apparatus to read an image. Next the application acquires the image data obtained by the reading performed by this TWAIN driver.

In this case communication to detect an event and communication of image data are performed between the image reading apparatus and the information processing apparatus. However depending on the operating system OS of the information processing apparatus the system may lack a mechanism for simultaneously securing a communication channel for the button monitoring program and for the scanner driver.

Consequently it is necessary to perform exclusive control of the communication channel between the button monitoring program and the scanner driver. More specifically before the scanner driver is to acquire the image data the OS closes the communication channel used by the button monitoring program and then opens the communication channel for the scanner driver.

During this process the OS refers to information device information which is recorded in a predetermined location specifying the image reading apparatus associated with the button monitoring program and device information associated with the scanner driver. If these pieces of information match the OS then performs the above exclusive control. Further in addition to the above described startup method in which the scanner driver is started via a button monitoring program the user can also directly operate the scanner driver to execute image reading in the image reading apparatus.

However for example in some cases a scanner driver may be newly installed into an information processing apparatus in which a scanner driver and a button monitoring program are already present and the image reading may be executed in the image reading apparatus by starting this new scanner driver. If image reading is executed in the image reading apparatus by starting this new scanner driver the communication channel used by the already running button monitoring program needs to be closed.

However if the OS cannot specify the device information for example if the new scanner driver is not based on a predetermined application programming interface API standard such as TWAIN the OS cannot perform the above exclusive control. More specifically even if a new scanner driver is started if the device information is not recorded in a predetermined location the OS cannot close the communication channel used by the already running button monitoring program. Therefore a scanner driver that has been started according to a procedure not based on a predetermined API cannot execute reading processing.

This problem not only occurs in image reading apparatuses but in other peripheral apparatuses as well. Specifically the same problem can occur in a situation which requires exclusive control of the communication channel used among a plurality of programs when there is no mechanism for closing a communication channel that is being used by another program based on the startup of the device driver.

The present invention is directed to an information processing apparatus and a control method thereof capable of suitably closing a communication channel that is being used by another program even when that channel cannot be closed just by starting a device driver.

According to an aspect of the present invention an information processing apparatus having an operating system OS configured to perform non exclusive control among a plurality of programs that are based on a predetermined application program interface API on a communication channel for communicating with a peripheral apparatus the information processing apparatus including a first device driver for the peripheral apparatus configured to startup based on a request that is based on the predetermined API and communicate with the peripheral apparatus via the communication channel a second device driver for the peripheral apparatus configured to startup based on a request that is not based on the predetermined API and communicate with the peripheral apparatus via the communication channel a communication program configured to communicate with the peripheral apparatus via the communication channel and a control unit configured to when the second device driver is issued with a startup instruction based on a request that is not based on the predetermined API if the communication program is using the communication channel close the communication channel that the communication program is using based on non exclusive control by the OS by starting the first device driver to enable the second device driver to use the communication channel.

Further features and aspects of the present invention will become apparent from the following detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings.

Not all of the constituent elements of the apparatus used in the present exemplary embodiment are essential to the present invention. Further various modifications and applications of these constituent elements are possible. More specifically the present invention is not limited to the specific configuration described in the following exemplary embodiments.

The scanner includes as hardware resources a universal serial bus USB interface a central processing unit CPU a read only memory ROM a random access memory RAM a scanner engine and an operation panel . The USB interface transmits and receives data to and from the computer based on a USB standard.

The CPU loads into the RAM a scanner control program that is stored in the ROM and controls the operation of the scanner by executing that control program. In addition to the control program the ROM stores the parameters that are required for operation of the scanner . The RAM is used as a CPU work area and also as a temporary storage area for state information about the scanner and image data.

The scanner engine includes a light source which irradiates light onto a document and a charge coupled device CCD color image sensor for reading reflected light and photoelectrically converting the read light. The scanner engine reads an image of the document by scanning the document which is placed on a platen of the scanner and produces image data based on the read image. The operation panel includes a display unit that displays a state of the scanner and a menu that allows the user to perform operations and hard keys that allow the user to perform various operations including the instruction to start reading. The operation panel may have some other configuration such as a touch panel.

Further although the scanner is used here as an example of a dedicated scanner the scanner may be configured as a multifunctional device that also includes other additional functions such as a printer. In addition when reading the document image although the document is placed on the platen and then scanned a document conveyance mechanism may be provided so that scanning is performed by fixing the scanner engine and conveying the document.

Moreover as the operation for starting the reading performed by the scanner instead of using the operation panel when the reading target document is detected to have been set in the scanner that fact may be notified to the computer .

Still further the scanner may be configured without the CPU so that the scanner engine is operated based on a control from the computer . In addition instead of a color scanner a monochrome scanner or a film scanner that reads film may be employed.

The computer includes as hardware resources a USB interface a display device an input device an auxiliary storage device a CPU a ROM and a RAM . As the computer a general purpose personal computer may be employed.

The USB interface transmits and receives data to and from a peripheral apparatus based on a USB standard. The display device displays various information such as various user interfaces UI for operating the scanner based on software installed in the computer .

The input device is realized by a keyboard a pointing device and the like and is for inputting information indicating an operation from the user. The auxiliary storage device is realized by an internal or an external hard disk for example and stores various information relating to operation of the scanner such as the scanner control program.

The CPU loads into the RAM various programs stored in the auxiliary storage device and the ROM and controls the operations of the computer by executing those programs. The ROM stores various programs and various pieces of information for operating the computer . The RAM is used as a CPU work area and also stores various information.

Next referring to the configuration of the functions that are realized by the software in the computer illustrated in will be described. The respective functions illustrated in are realized by for example the CPU reading and executing the programs stored installed in the ROM and the auxiliary storage device while using the RAM as a work area.

The functions of the computer can be broadly separated into an OS an application a TWAIN driver a button monitoring program a device control program and a USB interface control unit .

The OS includes functions such as control of the basic units for operation of the computer control of output to the display device and input from the input device and management of the various memories such as the auxiliary storage device . Further the OS includes a TWAIN data source manager TWAIN DSM a button monitoring program control unit and an application startup control unit .

The TWAIN DSM controls the application and the TWAIN driver . The TWAIN DSM is an API that realizes communication between the application and the TWAIN driver based on a TWAIN standard. If an instruction is issued to startup the TWAIN driver the TWAIN DSM issues a close request to the button monitoring program .

When a monitoring program for monitoring whether a peripheral apparatus such as the scanner has been operated is present in the computer the button monitoring program control unit starts up and shuts down that monitoring program. The application startup control unit is realized by an API that provides a function for starting a specified application.

The application is a software program for processing input image data. The application can acquire image data from a data source scanner driver by issuing an instruction to that data source based on the TWAIN standard via the TWAIN DSM .

The application can also edit or correct the acquired image data display the resultant data on the display device and store the data as an image file in the auxiliary storage device . Further examples of the application include character recognition software which recognizes character information included in input image data and converts the recognized character information into a character code.

The TWAIN driver is a driver that performs controls such as the transmission of a command for controlling the scanner and the reception of image data from the scanner . The transmission of a command and the reception of image data by the TWAIN driver are performed via the USB interface control unit .

Although the TWAIN driver is associated with device information for specifying the image reading apparatus in the present exemplary embodiment the TWAIN driver is associated with device information indicating the scanner . This device information indicating the scanner is recorded in a predetermined file associated with the TWAIN driver . Further the TWAIN driver includes a TWAIN communication control unit and an image data acquisition unit .

The TWAIN communication control unit exchanges a command group based on the TWAIN standard of the application with the TWAIN driver . The TWAIN communication control unit receives a reading setting from the application such as a reading resolution a color mode and a document size and sets the received reading setting in the TWAIN driver .

Further in response to an image transfer request from the application the TWAIN communication control unit performs control so that the image data read by the scanner is transferred to the application . The transfer of the reading setting information and the image data is performed via the TWAIN DSM . The image data acquisition unit acquires the image data read by the scanner via the USB interface control unit .

The image data acquired by the image data acquisition unit is stored in the RAM and then transferred to the application based on a control by the TWAIN communication control unit . In addition to startup based on an instruction from a TWAIN compatible application the TWAIN driver can also be started based on a direct operation from the user and even when a read instruction is made by the user issue a read instruction.

The button monitoring program transmits a command for controlling the scanner and receives data indicating the state of the scanner . This transmission of a command and reception of data indicating a state is performed via the USB interface control unit .

Further although the button monitoring program is associated with device information for specifying a peripheral apparatus in the present exemplary embodiment the button monitoring program will be associated with device information indicating the scanner . This device information indicating the scanner is recorded in a predetermined file associated with the button monitoring program . The state of the scanner at this stage is not limited to whether a button is pressed or not. This state may be in any form as long as the fact that some kind of operation is performed by the user can be acquired.

Further in the present exemplary embodiment a plurality of button monitoring programs may simultaneously be present in the computer the auxiliary storage device . However the OS in the present exemplary embodiment only starts up one of the button monitoring programs as a button monitoring program for monitoring the state of the scanner connected via the USB interface .

The present exemplary embodiment will be described below with only an arbitrary one button monitoring program being started. The button monitoring program has an OS communication control unit and a button event monitoring unit .

If the OS detects that the scanner is connected via the USB interface the OS communication control unit opens a USB port according to a procedure based on a predetermined communication standard plug play . The term USB port refers to a logical channel for communication via the USB interface .

By opening the USB port a transfer pipe for exchanging information with the scanner connected via the USB interface is secured. Further the USB port for communicating with the scanner is used exclusively by one scanner driver or one button monitoring program.

When the connection with the scanner starts first the button monitoring program uses the USB port to monitor for a button event from the scanner . If there is a plurality of button monitoring programs one of these is selected and started based on a predetermined condition.

Further if the connection via the USB interface is disconnected and if the TWAIN driver has been started the OS communication control unit closes the USB port according to a procedure based on a predetermined communication standard.

The button event monitoring unit periodically monitors whether a button event has occurred due to a user operation on the operation panel of the scanner . Although this operation performed by the user of the monitoring target will be described using the pressing of a button as an example as described above the present invention is not limited to the pressing of a button . Any operation may be employed as long as the operation is performed by the user for the purpose of reading the document.

When a button event such as an instruction from the operation panel to start reading is detected the button event monitoring unit instructs a predetermined application to startup via the application startup control unit of the OS . For example the image data can be acquired in a desired format from the TWAIN driver in conjunction with detection of the button event by transferring a prepared file relating to the reading setting of the scanner to the started up application.

The device control program has a function as a scanner driver for performing controls such as transmission of commands which control the scanner and reception of image data from the scanner and a function as an application for processing input image data based on a user instruction.

Further the device control program can also perform processing e.g. acquisition of read image data as RAW data not based on the TWAIN standard which cannot be performed by the TWAIN driver . The device control program can be selectively utilized by the user as a program that enables the image data to be subjected to different processing from that of the TWAIN driver .

When an instruction is issued to startup the TWAIN driver the OS closes the button monitoring program that is associated with the same device information as the device information associated with the TWAIN driver . The OS refers to device information recorded in the predetermined file associated with the above programs and executes exclusive control of the USB port.

However even if an instruction is issued to startup the device control program the OS cannot close the currently running button monitoring program based only on that. This is because the device control program does not record device information in the predetermined file like that described above.

Further the device control program has a TWAIN communication setting unit a UI display unit and a scanner control unit .

The TWAIN communication control unit exchanges a command group based on the TWAIN standard with the TWAIN driver via the TWAIN DSM . To perform exclusive control of the USB port for the scanner the TWAIN communication setting unit performs a vender customization setting in the TWAIN driver in order to release the USB port for a predetermined duration.

The UI display unit provides display information for displaying on the display device a UI screen which allows a user to perform a reading setting and a setting for editing image data. The UI display unit also provides a screen for performing a version upgrade of the device control program and the scanner firmware.

The scanner control unit transmits commands for controlling the scanner and receives image data from the scanner via the USB interface control unit . The device control program may be started based on either an instruction from the button monitoring program or an instruction from the user via the UI screen provided by the UI display unit .

Next a typical processing flow performed when an operation for instructing the scanner to start reading is performed and based on this the application acquires image data via the TWAIN driver will be described. illustrates a sequence flow of the processing performed by the computer in this case.

The following sequence illustrates a processing flow performed by the CPU of the computer loading programs stored in the ROM and the auxiliary storage device into the RAM and executing those programs. This processing is an example of a case in which the OS performs exclusive control of a USB port a data transfer pipe with the scanner during processing for reading an image based on a TWAIN standard by recognizing the startup and shut down of the scanner driver.

First when the scanner is connected to the computer via the USB interface one button monitoring program is started by the OS . Next in step A the button monitoring program opens a USB port which is a logical channel for communication with the scanner and repeatedly performs polling to monitor the occurrence of a button event in the scanner .

When an operation button pressing for issuing a read instruction is performed by the user from the operation panel of the scanner the button monitoring program detects a signal indicating the occurrence of a button event via the opened USB port.

The data transfer during the exchange with the scanner in steps A to A is performed based on interrupt transfer. At this stage the button monitoring program occupies the USB port.

When the button monitoring program detects a button event in step A in step A the button monitoring program starts a predetermined application. The application started in this step is preregistered in the OS . If there is only one registered application that application is started.

If two or more applications are registered a screen prompting the user to make a selection among those plurality of registered applications is displayed by the OS on the display device and the application specified by the user from among the displayed applications is started. In this example the application is started.

In step A the application started based on an instruction from the button monitoring program issues an open request command based on the TWAIN standard to the TWAIN driver and instructs the TWAIN driver to startup. This open request command is not transmitted directly to the TWAIN driver from the application but is transmitted via the TWAIN DSM of the OS .

When the TWAIN DSM receives the TWAIN driver open request command transmitted in step A in step A before starting the TWAIN driver the TWAIN DSM transmits a close request event to the button monitoring program that is already running.

In step A the button monitoring program which has received this close request event closes the already open USB port that is occupied. In this example since the device information associated with the TWAIN driver and the device information associated with the button monitoring program match exclusive control is performed by the OS .

More specifically the TWAIN DSM of the OS refers to the above predetermined files associated with the TWAIN driver and the TWAIN driver determines that the same device information is recorded in both files and based on that determination performs exclusive control of the USB port.

If the USB port is successfully closed in step A in step A the button monitoring program transmits information indicating a successful close as a response to the event transmitted in step A. When the TWAIN DSM confirms the response from step A the TWAIN DSM starts up the TWAIN driver .

In step A the TWAIN driver opens the USB port bulk transfer pipe for performing communication with the scanner during the startup processing. Consequently the USB port is in the possession of the TWAIN driver . When the USB port is successfully opened in step A the TWAIN driver transmits to the TWAIN DSM information indicating a successful open as a response to the open request transmitted in step A. The TWAIN DSM receives this response and in step A notifies the application of the successful open.

In step A the application which has received the notification that the USB port has been successfully opened issues an image transfer request command based on the TWAIN standard and this command is transmitted to the TWAIN driver via the TWAIN DSM . Then the TWAIN driver which has received this command makes the scanner read a document image based on a reading setting specified from the application and acquires the resultant read image data.

In step A the TWAIN driver optionally performs processing such as correction on the acquired image data read image data and transfers the resultant data to the application . The transfer of the image data between the TWAIN driver and the scanner is performed based on bulk transfer.

In step A when the application has finished receiving the read image data from the TWAIN driver the application issues a close request command based on the TWAIN standard to the TWAIN driver . This command is transmitted to the TWAIN driver via the TWAIN DSM . When the TWAIN driver receives this command it performs shut down processing.

In step A the TWAIN driver closes the already opened USB port that it possesses. Then if the USB port is successfully closed in step A the TWAIN driver transmits information indicating a successful close to the TWAIN DSM as a response to the close request transmitted in step A.

In step A the TWAIN DSM which has received this response notifies the application of the successful close. Once the TWAIN driver transmits the information indicating the successful close transmitted in step A the TWAIN driver is ended.

The TWAIN DSM of the OS which has received information indicating the TWAIN driver has successfully closed the USB port makes the button monitoring program open the USB port in order to monitor the occurrence of a new read request event by the scanner . More specifically in step A the TWAIN DSM transmits an open request event to the button monitoring program and in step A the button monitoring program which has received this request opens the USB port.

Then in step A when the USB port is successfully opened by the button monitoring program the button monitoring program transmits information indicating that the USB port has been successfully opened as a response to the transmission of the open request event. When the button monitoring program has opened the USB port and occupied the USB port the button monitoring program restarts the polling which monitors for events in the scanner and performs the same processing as the above described processing that is performed at startup.

The application which has received the read image data from the TWAIN driver performs for example processing for storing this image data in the auxiliary storage device as an image file based on an instruction from the user and then the application is ended.

This processing executed by the application may also be performed before the TWAIN driver is ended. Further this image data processing is not limited to the file storage. Other types of processing may also be performed. In addition the processing contents may be pre specified or may be the one specified based on an instruction from the user after the read image data was received.

Moreover in the above processing although interrupt transfer is used for the button event communication and bulk transfer is used for the read image data communication bulk transfer may be used for either communication. Even in such a case the communication channel is controlled in an exclusive manner between the scanner driver and the button monitoring program. This also applies in the following description.

Thus when the TWAIN driver is used to make the scanner perform reading processing the TWAIN DSM of the OS can control the USB port in an exclusive manner between the TWAIN driver and the button monitoring program that are associated with the same device information.

Therefore exclusive control can be similarly performed not only when the TWAIN driver detects a button event in the scanner but even when the TWAIN driver is directly started by the user and when the TWAIN driver is started based on a command based on the TWAIN standard from the application .

Next the processing flow when the device control program is used to make the scanner perform reading processing will be described. Here the device control program makes the scanner execute reading processing without using a command based on the TWAIN standard.

First when the scanner is connected with the computer via the USB interface one button monitoring program is started by the OS . Next in step B the button monitoring program opens a USB port which is a logical channel for communication with the scanner and repeatedly performs polling to monitor the occurrence of a button event in the scanner . The processing is the same as that illustrated in .

When the device control program is started based on an instruction from the user a screen like that illustrated in provided by the UI display unit is displayed on the display device . In a main dialog box is a main screen that displays read image data and receives a reading setting from the user.

A read setting region is a region in which the user performs a reading setting. Examples of reading settings include a reading mode a document type an output resolution a filter and high dynamic range. Examples of the reading mode include paper photograph and film document.

The type of document that can be selected depends on the specified reading mode. For paper photograph examples include a color document a monochrome document a color photograph a monochrome photograph a color document photograph and a monochrome document photograph. For film examples include a color film positive a color film negative a monochrome film positive and a monochrome film negative .

The output resolution can be selected from any of 75 150 300 600 and 1 200 dpi. The filter can be selected from automatic no filter strong sharpness and weak sharpness. If the high dynamic range box is checked the difference between the brightest portion and the darkest portion of the acquired data the dynamic range is widened.

A preview button makes the scanner read an image at a low resolution regardless of the output resolution setting of the read setting region and display the result in a preview region . The user can specify a desired region within the image displayed in the preview region.

A scan button makes the scanner read an image based on the settings specified by the read setting region main scanning to acquire read image data. If a region is specified after a preview only the image data for the specified region is acquired. Further if the pre specified processing performed during the main scanning is only the acquisition of image data an image of the main scanning result is displayed in the preview region .

If the scan button is specified by the user the read image data is converted into an image file which is given a predetermined name and stored in the auxiliary storage device .

In addition during the period that the button monitoring program secures the USB port the device control program is started and the scan button is specified. More specifically the device control program issues a startup instruction based on a request that is not based on the TWAIN standard.

Since the reading processing is not performed using the TWAIN driver exclusive control of the USB port by the OS TWAIN DSM is not performed just based on the starting up of the device control program . This is because the device control program can directly control the scanner so that here device information is not recorded in the predetermined file that enables exclusive control by the OS .

Thus here despite the fact that reading processing is not performed using the TWAIN driver the TWAIN driver is started in order to close the USB port being used by the button monitoring program . More specifically in step B when a reading instruction is issued by the device control program based on the user specifying the scan button an open request command for the TWAIN driver is issued to the TWAIN DSM .

In step B the TWAIN DSM which has received this open request command transmits a close request event to the button monitoring program that is associated with the same device information as the TWAIN driver device information. Here device information indicating the scanner is recorded in the predetermined files for both the TWAIN driver and the button monitoring program .

In step B the button monitoring program which has received this close request event closes the already opened USB port that is being used thereby. Then when the USB port is successfully closed in step B the button monitoring program transmits information indicating a successful close as a response to the close request transmitted in step B. When the TWAIN DSM confirms that the USB port has been successfully closed the TWAIN DSM starts up the TWAIN driver based on the open request transmitted in step B.

In step B the TWAIN driver opens the USB port for performing communication with the scanner during the startup processing. When the USB port is successfully opened the TWAIN driver notifies the TWAIN DSM of that fact. Then the TWAIN DSM which has received this notification notifies the device control program that the USB port has been successfully opened by the TWAIN driver .

When the device control program confirms that the TWAIN driver has started and that the USB port has been successfully opened in step B the device control program issues a command instructing the setting of a vender unique customization setting.

This command is a command based on the TWAIN standard and is notified to the TWAIN driver via the TWAIN DSM . The vender unique setting that is notified is for requesting the closure of the temporarily opened USB port.

Here the reading processing is not performed by the TWAIN driver but rather is performed by starting the TWAIN driver and closing the USB port being used by another program by utilizing the exclusive control function of the OS .

Further for the reading processing to use the device control program the USB port needs to be closed by the TWAIN driver . Therefore the vender unique setting is employed. However if the USB port can be closed by the TWAIN driver it is not limited to the vender unique setting. Some other method may also be employed.

By closing the open request used by the button monitoring program and the TWAIN driver as described above the device control program can use the USB port.

In step B the TWAIN driver which has received the command transmitted in step B from the device control program closes the already opened USB port that is being used thereby. Then when the USB port is successfully closed in step B the TWAIN driver transmits information indicating a successful close as a response to the command transmitted in step B.

During the period that the device control program is performing the reading processing to prevent the OS from trying to startup the button monitoring program the TWAIN driver itself is not closed at this stage.

In step B when the device control program confirms that the USB port has been closed the device control program opens the USB port. Then the device control program makes the scanner execute image reading based on the reading setting set in the read setting region and acquires the resultant read image data. When the acquisition of the read image data from the scanner is finished in step B the device control program closes the USB port.

Based on a specification by the user the device control program performs processing such as storing the image data in the auxiliary storage device as an image file. The processing for producing and storing the image file may also be performed before closing the USB port.

In step B when the reading processing in this example acquisition of the read image data and file storage is finished the device control program issues a close request command based on the TWAIN standard to the TWAIN driver . This command is transmitted to the TWAIN driver via the TWAIN DSM . When the TWAIN driver receives this command in step B it performs end processing and transmits information indicating a successful close as a response to the close request transmitted in step B.

In step B the TWAIN DSM which has confirmed that the TWAIN driver is closed transmits an open request event to the button monitoring program . Then in step B upon receiving the open request event the button monitoring program opens the USB port.

Then in step B when the USB port is successfully opened by the button monitoring program the button monitoring program transmits information indicating that the USB port was successfully opened as a response to the transmission of the open request event. When the button monitoring program has opened the USB port and occupied the USB port the button monitoring program restarts the polling which monitors events in the scanner and performs the same processing as the above described processing that is performed at startup.

Based on the processing illustrated in just by simply starting up and issuing a read instruction the OS can be made to perform exclusive control even when a scanner driver that does not perform exclusive control of a communication channel is used to make the TWAIN DSM of the OS perform reading processing. More specifically when the scanner driver performs reading processing starting the TWAIN driver enables a communication channel used by another program to be closed by using the exclusive control function of the OS.

The scanner driver can close the communication channel if the exclusive control of the OS is used even if the scanner driver cannot identify the program that is using the communication channel. This is because the exclusive control function of the OS closes the communication channel being used by another program associated with the same device information when a program that will use the communication channel is started.

Therefore for example even if there is a plurality of button monitoring programs in the computer and the device control program cannot identify which of the button monitoring programs is currently using the communication channel the button monitoring program using the communication channel can be closed.

Next a second exemplary embodiment of the processing performed when the device control program is used to make the scanner perform reading processing will be described. In this case too the device control program makes the scanner execute reading processing without using a command based on the TWAIN standard. Further the fact that the OS performs exclusive control among a plurality of programs scanner drivers and button monitoring programs on a USB port which is a logical channel is the same as the first exemplary embodiment.

Similar to the configuration in the application can instruct the TWAIN driver which is a data source based on the TWAIN standard to open and close via the TWAIN DSM . However the application according to the second exemplary embodiment is as is described below only for assisting exclusive control of the USB port in order to perform communication with the scanner .

Therefore the application according to the second exemplary embodiment does not necessarily have to have a UI screen. Further when started the application can be operated in the background. However the application does not have to be only for assisting the exclusive control of the USB port. The application may combine this function with another function.

The application has an event reception unit . This event reception unit is realized by an interprocess communication API provided by the OS . The event reception unit performs different processing based on the type of event that is received.

Similar to the configuration in the TWAIN driver transmits commands for controlling the scanner and receives image data based on the TWAIN standard. In addition to the configuration illustrated in the TWAIN driver according to the second exemplary embodiment has an application ID identification unit and an application ID determination unit .

The application ID identification unit identifies the application that has instructed the TWAIN driver to startup. An application that is based on the TWAIN standard possesses a unique ID which can be identified by the application ID identification unit .

The application ID determination unit determines whether the application corresponding to the ID identified by the application ID identification unit is a predetermined application. The application ID determination unit performs this determination based on whether the ID identified by the application ID identification unit matches the ID of a specific application stored in the auxiliary storage device .

Similar to the configuration in the device control program is a program having a function as a scanner driver and a function as an application and can perform processing that is not based on the TWAIN standard. In addition to the configuration illustrated in the device control program according to the second exemplary embodiment has an application startup unit and an event transmission unit .

The application startup unit instructs a predetermined application to startup using the API provided by the OS . The event transmission unit transmits information indicating a predetermined event based on the interprocess communication API provided by the OS .

Next a sequence flow of the processing performed according to the second exemplary embodiment by the computer including the configuration illustrated in will be described referring to . The following sequence illustrates a processing flow performed by the CPU of the computer loading programs stored in the ROM and the auxiliary storage device into the RAM and executing those programs.

First the operations that in step C in a state in which the button monitoring program is started and the USB port is open the device control program is started and a reading instruction is made from the UI screen of are the same as those of the first exemplary embodiment illustrated in .

In step C when a reading instruction is issued by the device control program a startup instruction is issued to the application . In step C when the application is started the device control program transmits an open request event to the application by the event transmission unit .

In step C when the event reception unit receives the open request event transmitted in step C the application issues an open request command based on the TWAIN standard and instructs the TWAIN driver to startup.

In step C when the TWAIN DSM of the OS receives the open request transmitted in step C before the TWAIN driver is started the TWAIN DSM transmits a close request command to the button monitoring program . Then in step C the button monitoring program which has received the close request event transmitted in step C closes the already opened USB port that is being used thereby.

Then when the USB port is successfully closed in step C the button monitoring program transmits information indicating a successful close as a response to the close request transmitted in step C. Closing the USB port that is being used by the button monitoring program enables the device control program to use the USB port.

When the TWAIN DSM confirms that the USB port has been successfully closed the TWAIN DSM starts up the TWAIN driver based on the open request transmitted in step C.

During the startup processing the TWAIN driver identifies the ID of the application that made the startup instruction using the application ID identification unit and determines whether this ID matches a predetermined ID using the application ID determination unit . Further since this is a startup instruction from the application it is determined that the identified ID matches the predetermined ID and thus the TWAIN driver does not open the USB port. Consequently the processing efficiency can be increased by omitting the processing for opening and closing the USB port by the TWAIN driver which in this example does not perform reading processing. This processing will be described in more detail below.

Then in step C the TWAIN driver transmits information indicating a successful open to the application via the TWAIN DSM as a response to the open request transmitted in step C.

In step C the application which has received the information indicating a successful open from the TWAIN driver transmits an event indicating that fact to the device control program . In step C when the device control program has received the event transmitted in step C the USB port is opened.

In step C the device control program makes the scanner execute reading based on the reading setting set in the read setting region and acquires the resultant read image data. When the acquisition of the read image data from the scanner is finished in step BC the device control program closes the USB port. Then based on a specification by the user the device control program performs processing such as storing the image data in the auxiliary storage device as an image file. The processing for producing and storing the image file may also be performed before closing the USB port.

In step C when the reading processing in this example acquisition of the read image data and file storage is finished the device control program transmits a close request event to the application . In step C when the event reception unit of the application has received this close request event the application issues a close request command based on the TWAIN standard.

This command is transmitted to the TWAIN driver via the TWAIN DSM . When the TWAIN driver has received this command in step C it performs end processing and transmits information indicating a successful close as a response to the close request transmitted in step C. Then the application which has received this information transmits an event indicating a successful close to the device control program .

The device control program which has received this event ends itself. The reason why the TWAIN driver is not ended while the device control program is performing the reading processing is to prevent the OS from trying to startup the button monitoring program while the device control program is performing the reading processing.

In step C the TWAIN DSM which has received the information indicating a successful close transmitted in step C transmits an open request to the button monitoring program . In step C the button monitoring program which has received this request opens the USB port. Then in step C when the USB port is successfully opened by the button monitoring program the button monitoring program transmits information indicating that the USB port has been successfully opened as a response to the transmission of the open request event.

When the button monitoring program has opened the USB port and occupied the USB port the button monitoring program restarts the polling which monitors for events in the scanner and performs the same processing as the above described processing that is performed at startup.

A part of the processing performed when the TWAIN driver has received the TWAIN open request will now be described. is a flowchart illustrating the flow of the processing performed in this case. This flowchart illustrates a processing flow performed by the CPU of the computer loading programs stored in the ROM and the auxiliary storage device into the RAM and executing those programs.

The processing performed in this flowchart is started when the TWAIN driver receives an open request command based on the TWAIN standard. In step S the application ID identification unit identifies the ID of the application that has transmitted the received open request command.

Then in step S the application ID determination unit determines whether the ID identified in step S is a predetermined ID. This predetermined ID refers to the ID of an application that assists exclusive control of the USB port. In the present exemplary embodiment this refers to the ID of the application .

Further this predetermined ID is pre stored in a predetermined region of the auxiliary storage device . The TWAIN driver can refer to the predetermined ID when it performs the processing of this flowchart. This predetermined ID is not limited to one ID. A plurality of IDs may exist. Here the TWAIN driver determines the transmission source of the instruction to start it up.

If it is determined in step S that the identified ID is the predetermined ID YES in step S the processing proceeds to step S. If it is determined in step S that the identified ID is not the predetermined ID NO in step S the processing proceeds to step S. Proceeding to step S corresponds to a case in which the command from step C is received in the sequence in .

In step S the TWAIN driver determines that the USB port that enables itself to communicate with the scanner is not open. This is because as described above the TWAIN driver is started so that the application in closes the USB port that is currently being used by using the exclusive control function of the OS to prevent the TWAIN driver from performing reading processing. Consequently the processing for opening and closing the USB port by the TWAIN driver becomes unnecessary so that the processing efficiency can be increased.

In step S the TWAIN driver opens the USB port for communication with the scanner . This is when the application based on the TWAIN standard makes the scanner execute image reading using the TWAIN driver and acquires the read image data to enable thereof. This step is executed based on processing like that illustrated in step A and subsequent steps illustrated in . Thus a description will be omitted here.

Next in step S the TWAIN driver waits for the reception of a command based on the TWAIN standard. In step S if it is determined that a close request command based on the TWAIN standard is received YES in step S the processing proceeds to step S.

In step S the TWAIN driver determines whether the USB port is open. If it is determined that the USB port is open YES in step S the processing proceeds to step S. In step S the TWAIN driver closes the USB port that is open and then shuts itself down. If it is determined that the USB port is not open NO in step S the TWAIN driver is ended without performing the processing for closing the USB port.

Based on the processing illustrated in just by simply starting up and issuing a read instruction the OS can be made to perform exclusive control even when a scanner driver that does not perform exclusive control of a communication channel is used to make the TWAIN DSM of the OS perform reading processing. The scanner driver can close the communication channel if the exclusive control of the OS is used even if the scanner driver cannot identify the program using the communication channel. Above described processing is the same as that according to the first exemplary embodiment illustrated in .

Further in the second exemplary embodiment when the TWAIN driver is started only to perform e exclusive control by the OS the TWAIN driver does not open the USB port. Consequently the processing for opening and closing the USB port by the TWAIN driver can be omitted whereby the processing load is reduced.

In addition usually when a USB port is opened by a TWAIN driver initialization processing is executed to perform the reading processing that uses the scanner . Since this is not performed in the second exemplary embodiment the reading processing performed by the device control program can be promptly started.

In the above described exemplary embodiments although an example is described in which a USB is used as an interface with the scanner some other interface may also be used as long as it allows the OS to perform exclusive control of the communication channel among a plurality of programs. This can be either a local interface or a network interface.

Moreover the scanner and the computer are not limited to those that are externally connected. A function corresponding to the scanner and a function corresponding to the computer in the above exemplary embodiments may be internally connected and integrated with each other.

Further in the above described exemplary embodiments although a program for causing the OS to perform the exclusive control of the communication channel by starting is based on the TWAIN standard the same processing can be performed by starting a program based on the predetermined API other than the TWAIN standard.

Further the peripheral apparatus is not limited to a scanner. For example a printer may be used as the peripheral apparatus. In this case exclusive control of communication channels may be performed when a printer driver performs print image data communication and when a program monitoring events in the printer performs event communication.

In other words the exclusive control performed between a device driver which performs image data communication with a peripheral apparatus and another communication program which performs communication with the peripheral apparatus may use the exclusive control function of the OS as described above.

According to the above described exemplary embodiments when a device driver is instructed to startup according to a procedure not based on a predetermined API a communication channel can be closed utilizing exclusive control performed by the OS by starting another device driver that is based on a predetermined API.

Further the present invention can also be realized by supplying software a program for realizing the functions of the above exemplary embodiments to a system or an apparatus via a network or via various storage media and having a computer or a central processing unit CPU or a micro processing unit MPU of the system or apparatus read and execute the program. In this case this program and the storage media on which the program is recorded constitute the present invention. In addition the program may be executed by one computer or by a plurality of computers linked together. Still further the above described processing does not all have to be realized by software. A part or all of the processing can be realized by hardware.

The present invention is not limited to the above described exemplary embodiments and various modifications including application to other exemplary embodiments or combination with other exemplary embodiments based on the spirit of the present invention are possible.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

