---

title: Multiple top level user interface displays
abstract: When a program invokes a synchronous user interface display, it is determined whether an asynchronous user interface (UI) display needs to be generated. If so, the user interface thread invoked by the synchronous program is blocked and the asynchronous UI display is generated and displayed so that it covers the synchronous display on the UI display screen. When the processing corresponding to the synchronous user interface display is complete, processing returns to the synchronous user interface display and the user interface thread invoked by the synchronous program is unblocked.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08990818&OS=08990818&RS=08990818
owner: Microsoft Technology Licensing, LLC
number: 08990818
owner_city: Redmond
owner_country: US
publication_date: 20120907
---
The present application is based on and claims the benefit of U.S. provisional patent application Ser. No. 61 654 127 filed Jun. 1 2012 the content of which is hereby incorporated by reference in its entirety.

Many computer programs generate user interface displays. The user interface displays generally display information on a display screen for observation by a user. Some of the user interface displays also include user input mechanisms that allow the user to interact with mechanisms on the user interface display to provide inputs to the computer program. Currently some programs generate user interface displays using a synchronous programming model while others generate the user interface displays using an asynchronous programming model.

In a synchronous system the program may generate a user interface UI display on a user interface programming thread. A user interface thread or user interface programming thread is a thread that can have a message queue and a message loop and that dispatches messages to windows. By way of example one such user interface display is referred to as a modal dialog display. A modal dialog display is a user interface display that requires user interaction before processing can proceed. For instance if the user desires to delete a file a synchronous program may generate a dialog box which states Do you want to delete this file and also display yes and no buttons for actuation by the user. In a synchronous system processing will not continue until the user interacts with that modal dialog display by either clicking the yes button or the no button. Therefore the program can be written in such a way that the programmer can assume that the user answered the question in the modal dialog box before the next line of program code is executed.

As another example in a synchronous system the synchronous program might generate a user interface display corresponding to a long running operation. For instance if the user has selected a large amount of text to be copied from one document and pasted to another this operation can take several seconds. During that time the synchronous program may inhibit other user inputs from taking place until the long running operation has been completed. By way of example the synchronous program can gray out the user interface display elements so that no user inputs are possible while the text is being copied from one document and pasted to the other document. Similarly if the user is launching an application or booting up the system itself these operations can take several seconds and might also be considered long running operations. During those long running operations the system often inhibits other user inputs from taking place until the operation is complete.

This is not the case in an asynchronous system. Asynchronous systems often simply invoke a modal dialog box or a long running operation in one line of code asynchronously so that the subsequent lines of code cannot assume that the program has received a response to the question in the modal dialog box or that the long running operation is complete. The user interface thread is asynchronous and processing continues in the program code regardless of whether the user has interacted with the modal dialog box or whether the operations corresponding to the UI are complete.

Asynchronous systems also operate to ensure that user interface display threads do not unnecessarily block user inputs. By way of example if an asynchronous user interface display is generated and it is blocking user inputs from being received by the program for a certain amount of time such as five seconds or ten seconds or another threshold amount of time then some asynchronous systems kills the user interface display thread that is blocking the user inputs or even the entire application . The asynchronous system assumes that the user interface display thread is not responding appropriately and therefore it should be killed.

This can make it difficult to run a program written using a synchronous programming model in a system that is generated using an asynchronous programming model. For instance if a synchronous program is conducting a long running operation that takes longer than five ten seconds by way of example the asynchronous system might kill the application or at least UI thread responsible for the long running operation. This can result in undesirable operation.

The discussion above is merely provided for general background information and is not intended to be used as an aid in determining the scope of the claimed subject matter.

When a program invokes a synchronous user interface display it is determined whether an asynchronous user interface UI display needs to be generated. If so the user interface thread invoked by the synchronous program is blocked and the asynchronous UI display is generated and displayed so that it covers the synchronous display on the UI display screen. When the processing corresponding to the synchronous user interface display is complete processing returns to the synchronous user interface display and the user interface thread invoked by the synchronous program is unblocked.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used as an aid in determining the scope of the claimed subject matter. The claimed subject matter is not limited to implementations that solve any or all disadvantages noted in the background.

In one embodiment processor is a computer processor with associated memory and timing circuitry not shown . Processor is a functional part of system and is activated by and facilitates functionality of other programs and components of system . Data store illustratively stores data that can be used by synchronous program asynchronous program or other programs. Synchronous program is illustratively a computer program or component that is authored using a synchronous programming model. Program can be an application or other program. Similarly asynchronous program is illustratively a program authored using an asynchronous programming model. It can be an application or other program as well.

User interface component illustratively generates user interface displays for display to user . User interface displays illustratively include user input mechanisms for receiving user inputs from user . The user input mechanisms can be any suitable user input mechanisms for receiving user inputs from a touch sensitive screen from a keyboard a point and click device e.g. a mouse a virtual keyboard or software keyboard voice inputs etc. In any case user illustratively interacts with system through user interface displays .

In one embodiment computing system can operate with both synchronous program and asynchronous program generating interface displays through user interface component without the risk of having a user interface UI display thread killed when it is generated by synchronous program . The synchronous UI thread is handled by component so it is not killed by the asynchronous system. show a flow diagram illustrating one embodiment of the operation of system in doing this.

However before describing the operation of system in processing user interface threads in more detail a brief description will be provided for the sake of overview only. It is first assumed that system illustratively operates according to an asynchronous programming model. Therefore under normal operation it expects to process asynchronous user interface threads. However it may be that a synchronous program such as program is also operating within system . In that case synchronous program is authored using a synchronous programming model in which user interface threads are processed in a synchronous way. That is certain user interface threads will block further execution of code in program until processing corresponding to the user interface thread is completed.

By way of example it may be that program generates a modal dialog box with which the user is to interact through the user interface display that comprises the modal dialog box prior to any further processing being conducted. Further where program is a boot program it may be that no user inputs will be received during the boot process. In addition where program is executing a long running operation it may be that it will not accept any user inputs until execution of the long running operation is completed. In any case when system operates according to an asynchronous programming model all of these user interface threads may be prematurely killed by system before their corresponding processing has been completed.

Thus when synchronous program invokes a user interface thread component determines whether the program invoking the user interface thread is synchronous or asynchronous. If it is synchronous then system determines whether the user interface thread might be prematurely killed. If so component using component generates an asynchronous user interface display and covers the synchronous user interface display generated by program . Component then blocks the code in program from further execution until the processing corresponding to the synchronous user interface thread has been completed. Then component removes the asynchronous user interface display uncovering the synchronous user interface display generated by program and component unblocks program so that it can continue processing. In this way since the asynchronous user interface display is generated and covers the synchronous user interface display system will not kill the synchronous user interface display since it is no longer precluding user inputs because the asynchronous user interface display is covering it. Thus the processing corresponding to the synchronous user interface display has been completed and the asynchronous user interface display is removed. Processing returns to the synchronous user interface display and program is unblocked so that it can continue its processing.

However if at block it is determined that the user is using a synchronous program then component determines whether the program is invoking a synchronous user interface thread. This is indicated by block in . If not then program simply continues processing as usual as indicated by block in .

However if at block it is determined that program is invoking a synchronous user interface thread then component determines whether an asynchronous user interface needs to be generated. This is indicated by block in .

In order to determine whether an asynchronous user interface display needs to be generated a variety of different things can be considered. In one embodiment every time a user interface thread is invoked by a program it is submitted to processing by synchronous UI thread handling component . Component can then determine whether the asynchronous UI display needs to be generated in a number of different ways. For instance if the UI thread corresponds to a modal dialog box then component determines that the asynchronous user interface display does need to be generated. Similarly if the program invoking the user interface thread is a boot program then component will determine that the asynchronous user interface display needs to be generated as well. In addition if the operation corresponding to the synchronous user interface is a long running operation the asynchronous user interface display can be generated under those circumstances as well. The dialog is indicated by block in while the boot program is indicated by block and the long running operation is indicated by block . Of course the asynchronous user interface display can be generated when the user interface invoked is another user interface as well. This is indicated by block .

If component determines that the asynchronous user interface display does not need to be generated then the program code is simply processed as usual at block . However if the asynchronous user interface display does need to be generated then component blocks the UI thread in program so that no further code can be executed until processing corresponding to the synchronous user interface thread has been completed. This is indicated by block in . Blocking the UI thread can be done in a variety of different ways. In one embodiment component calls an application programming interface API that can be used to block the processing of the UI thread. Of course the block can be performed in other ways as well.

Component then uses user interface component to generate the asynchronous user interface display and uses that display to cover the synchronous user interface display on user interface display . This is indicated by block in . For instance where the synchronous display is a modal dialog box component generates an asynchronous modal dialog box and covers the synchronous modal dialog box. The asynchronous user interface for the modal dialog box is indicated by block in .

Where the synchronous user interface display is a screen corresponding to a boot operation an asynchronous boot screen is generated as indicated by block in . Where the synchronous user interface display corresponds to a long running operation an asynchronous progress indicator is displayed as indicated by block . Of course other asynchronous displays can be used as well and this is indicated by block .

By way of example shows a user interface display screen that is an asynchronous modal dialog box. In one embodiment where synchronous program generates a synchronous modal dialog box asynchronous modal dialog box is generated and displayed over the top of the synchronous modal dialog box. Once the user interacts with the asynchronous modal dialog box processing returns to program and the synchronous modal dialog box generated by program with the result of the user interaction with asynchronous modal dialog box .

Once the asynchronous user interface display is generated and displayed over the top of the synchronous user interface display component simply monitors the processing corresponding to the synchronous user interface display to determine when it is complete. This is indicated by blocks and in . For example where the synchronous user interface display is a modal dialog display component monitors when the appropriate user interaction has been received. This is indicated by block . Where the synchronous user interface display corresponds to a boot operation component determines when the boot operation is complete. This is indicated by block . When the synchronous user interface display corresponds to a long running operation component determines when the long running operation is complete. This is indicated by block . Of course component can monitor other operations as well and this is indicated by block .

Once the processing that corresponds to the synchronous user interface display has been completed component returns to the synchronous user interface display along with the result if any of the processing and unblocks the user interface thread in program so that processing in program can continue. This is indicated by blocks and in . Unblocking the UI thread can be done by calling a suitable API or in any other desired way. System then continues to process the code in program as usual. This again is indicated by block .

It can thus be seen that even synchronous UI threads can be processed in an asynchronous computing environment. The synchronous program synchronously waits on asynchronous operations. This also makes it easier to transition single threaded conventional applications into multi threaded environments.

The description is intended to include both public cloud computing and private cloud computing. Cloud computing both public and private provides substantially seamless pooling of resources as well as a reduced need to manage and configure underlying hardware infrastructure.

A public cloud is managed by a vendor and typically supports multiple consumers using the same infrastructure. Also a public cloud as opposed to a private cloud can free up the end users from managing the hardware. A private cloud may be managed by the organization itself and the infrastructure is typically not shared with other organizations. The organization still maintains the hardware to some extent such as installations and repairs etc.

The embodiment shown in specifically shows that system is located in cloud which can be public private or a combination where portions are public while others are private . Therefore user uses a user device to access those systems through cloud .

It will also be noted that system or portions of it can be disposed on a wide variety of different devices. Some of those devices include servers desktop computers laptop computers tablet computers or other mobile devices such as palm top computers cell phones smart phones multimedia players personal digital assistants etc.

Under other embodiments applications or systems like system are received on a removable Secure Digital SD card that is connected to a SD card interface . SD card interface and communication links communicate with a processor which can also embody processors from along a bus that is also connected to memory and input output I O components as well as clock and location system .

I O components in one embodiment are provided to facilitate input and output operations. I O components for various embodiments of the device can include input components such as buttons touch sensors multi touch sensors optical or video sensors voice sensors touch screens proximity sensors microphones tilt sensors and gravity switches and output components such as a display device a speaker and or a printer port. Other I components can be used as well.

Clock illustratively comprises a real time clock component that outputs a time and date. It can also illustratively provide timing functions for processor .

Location system illustratively includes a component that outputs a current geographical location of device . This can include for instance a global positioning system GPS receiver a LORAN system a dead reckoning system a cellular triangulation system or other positioning system. It can also include for example mapping software or navigation software that generates desired maps navigation routes and other geographic functions.

Memory stores operating system network settings applications application configuration settings data store communication drivers and communication configuration settings . Memory can include all types of tangible volatile and non volatile computer readable memory devices. It can also include computer storage media described below . Memory stores computer readable instructions that when executed by processor cause the processor to perform computer implemented steps or functions according to the instructions. System or the items in data store for example can reside in memory . Similarly device can have a client business system which can run various business applications or embody parts or all of system . Processor can be activated by other components to facilitate their functionality as well.

Examples of the network settings include things such as proxy information Internet connection information and mappings. Application configuration settings include settings that tailor the application for a specific enterprise or user. Communication configuration settings provide parameters for communicating with other computers and include items such as GPRS parameters SMS parameters connection user names and passwords.

Applications can be applications that have previously been stored on the device or applications that are installed during use although these can be part of operating system or hosted external to device as well.

The mobile device of is a personal digital assistant PDA or a multimedia player or a tablet computing device etc. hereinafter referred to as PDA . PDA includes an inductive screen that senses the position of a stylus or other pointers such as a user s finger when the stylus is positioned over the screen. This allows the user to select highlight and move items on the screen as well as draw and write. PDA also includes a number of user input keys or buttons such as button which allow the user to scroll through menu options or other display options which are displayed on display and allow the user to change applications or select user input functions without contacting display . Although not shown PDA can include an internal antenna and an infrared transmitter receiver that allow for wireless communication with other computers as well as connection ports that allow for hardware connections to other computing devices. Such hardware connections are typically made through a cradle that connects to the other computer through a serial or USB port. As such these connections are non network connections. In one embodiment mobile device also includes a SD card slot that accepts a SD card .

Computer typically includes a variety of computer readable media. Computer readable media can be any available media that can be accessed by computer and includes both volatile and nonvolatile media removable and non removable media. By way of example and not limitation computer readable media may comprise computer storage media and communication media. Computer storage media is different from and does not include a modulated data signal or carrier wave. It includes hardware storage media including both volatile and nonvolatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. Computer storage media includes but is not limited to RAM ROM EEPROM flash memory or other memory technology CD ROM digital versatile disks DVD or other optical disk storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other medium which can be used to store the desired information and which can be accessed by computer . Communication media typically embodies computer readable instructions data structures program modules or other data in a transport mechanism and includes any information delivery media. The term modulated data signal means a signal that has one or more of its characteristics set or changed in such a manner as to encode information in the signal. By way of example and not limitation communication media includes wired media such as a wired network or direct wired connection and wireless media such as acoustic RF infrared and other wireless media. Combinations of any of the above should also be included within the scope of computer readable media.

The system memory includes computer storage media in the form of volatile and or nonvolatile memory such as read only memory ROM and random access memory RAM . A basic input output system BIOS containing the basic routines that help to transfer information between elements within computer such as during start up is typically stored in ROM . RAM typically contains data and or program modules that are immediately accessible to and or presently being operated on by processing unit . By way of example and not limitation illustrates operating system application programs other program modules and program data .

The computer may also include other removable non removable volatile nonvolatile computer storage media. By way of example only illustrates a hard disk drive that reads from or writes to non removable nonvolatile magnetic media a magnetic disk drive that reads from or writes to a removable nonvolatile magnetic disk and an optical disk drive that reads from or writes to a removable nonvolatile optical disk such as a CD ROM or other optical media. Other removable non removable volatile nonvolatile computer storage media that can be used in the exemplary operating environment include but are not limited to magnetic tape cassettes flash memory cards digital versatile disks digital video tape solid state RAM solid state ROM and the like. The hard disk drive is typically connected to the system bus through a non removable memory interface such as interface and magnetic disk drive and optical disk drive are typically connected to the system bus by a removable memory interface such as interface .

The drives and their associated computer storage media discussed above and illustrated in provide storage of computer readable instructions data structures program modules and other data for the computer . In for example hard disk drive is illustrated as storing operating system application programs other program modules and program data . Note that these components can either be the same as or different from operating system application programs other program modules and program data . Operating system application programs other program modules and program data are given different numbers here to illustrate that at a minimum they are different copies. These can be the programs and components shown in or others.

A user may enter commands and information into the computer through input devices such as a keyboard a microphone and a pointing device such as a mouse trackball or touch pad. Other input devices not shown may include a joystick game pad satellite dish scanner or the like. These and other input devices are often connected to the processing unit through a user input interface that is coupled to the system bus but may be connected by other interface and bus structures such as a parallel port game port or a universal serial bus USB . A visual display or other type of display device is also connected to the system bus via an interface such as a video interface . In addition to the monitor computers may also include other peripheral output devices such as speakers and printer which may be connected through an output peripheral interface .

The computer is operated in a networked environment using logical connections to one or more remote computers such as a remote computer . The remote computer may be a personal computer a hand held device a server a router a network PC a peer device or other common network node and typically includes many or all of the elements described above relative to the computer . The logical connections depicted in include a local area network LAN and a wide area network WAN but may also include other networks. Such networking environments are commonplace in offices enterprise wide computer networks intranets and the Internet.

When used in a LAN networking environment the computer is connected to the LAN through a network interface or adapter . When used in a WAN networking environment the computer typically includes a modem or other means for establishing communications over the WAN such as the Internet. The modem which may be internal or external may be connected to the system bus via the user input interface or other appropriate mechanism. In a networked environment program modules depicted relative to the computer or portions thereof may be stored in the remote memory storage device. By way of example and not limitation illustrates remote application programs as residing on remote computer . It will be appreciated that the network connections shown are exemplary and other means of establishing a communications link between the computers may be used.

Although the subject matter has been described in language specific to structural features and or methodological acts it is to be understood that the subject matter defined in the appended claims is not necessarily limited to the specific features or acts described above. Rather the specific features and acts described above are disclosed as example forms of implementing the claims.

