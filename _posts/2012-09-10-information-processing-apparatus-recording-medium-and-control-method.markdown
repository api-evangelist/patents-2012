---

title: Information processing apparatus, recording medium, and control method
abstract: An information processing apparatus is configured to change a name of a print setting item and a display method of an option depending on application, or change display control depending on an execution environment in which the application is running.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09223521&OS=09223521&RS=09223521
owner: Canon Kabushiki Kaisha
number: 09223521
owner_city: Tokyo
owner_country: JP
publication_date: 20120910
---
A printer driver is provided with a dedicated user interface to perform detailed print setting. In printing with use of an application a user presses a button for performing detailed setting and in response to the operation the user interface of the printer driver is invoked through an operating system. If the operation varies depending on manufacturers or models the user has difficulty using the user interfaces. To solve the problem a tab format property sheet is provided. The printer driver adds a page to the individual tabs according to the operating system to create a user interface.

In recent years in addition to conventional user interfaces for pointing devices operating systems capable of changing the user interface to a user interface that can be easily operated on a touch panel have been provided. The change of the user interfaces of the operating system requires change of user interfaces of the printer driver. This requires a new printer driver.

However the creation of the new printer driver for all existing printers is troublesome and the users cannot use the printers until the creation is completed. To maintain the compatibility with the conventional printer driver which is currently running an operating system capable of switching the screen from a new user interface and invoking the conventional user interface is provided.

Further a new user interface may be dynamically established without displaying the conventional user interface. Further Japanese Patent Application Laid Open No. 2006 331339 discusses a method of providing a plurality of layout definition files and selecting a layout depending on a displaying device.

According to an aspect of the present invention an information processing apparatus comprising a control unit configured to simultaneously display a name of a print setting item and an option of the print setting item if first application instructs to display a print setting screen of a printer driver erase a name of a second print setting item and display an option of the first print setting item in response to an indication of a name of a first print setting item if second application instructs to display the print setting screen of the printer driver and erase the name of the first print setting item and further display an option of the second print setting item in response to an indication of the name of the second print setting item if second application instructs to display the print setting screen of the printer driver 

a control unit configured to receive layout information containing a type of a control and an ID of a function corresponding to the control from a printer driver 

the control unit further configured to determine whether the application that invoked the printer driver is being executed in a first execution environment or in a second execution environment and

the control unit further configured to display a user interface according to the layout information if the application is being executed in the first execution environment and replace the control described in the layout information with a control of a user interface in the second execution environment and display the control if the application is being executed in the second execution environment 

Further features and aspects of the present invention will become apparent from the following detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings.

In the method of switching a screen to display a conventional user interface the screen that is not suitable for a touch panel is displayed and this suddenly makes the operation troublesome for the user. In the method of selecting a screen from a plurality of layouts since the plurality of layouts are to be provided for the printer driver a conventional printer driver cannot be used as it is. Further if the method of rearranging scaling and moving parts is performed on a user interface in a case where the parts are not suitable for the touch panel the operability decreases even though the layout is changed. Hereinafter a program for an operating system is described which lays out a user interface of a printer driver in a form suitable for a terminal that displays the user interface.

A central processing unit CPU corresponding to a control unit performs overall control of the device according to a program stored in a read only memory ROM or a random access memory RAM in a main storage unit or an auxiliary storage unit . The RAM is also used as a work area for the CPU in performing various kinds of processing. The auxiliary storage unit stores an operating system OS application software and the like. Input devices such as a keyboard a pointing device represented by a mouse and a touch panel are used when a user gives various instructions to the computer via an input interface I F . An output I F is an interface used to output data to an output device such as a monitor and a printer . The output I F can be connected not only directly to a printer via a local I O but also to a network via a communication I F . A common system bus is used to transmit or receive data among the I F and modules.

With the above described configuration the CPU executes processing according to a program stored in the auxiliary storage unit and thereby the software configuration of the computer illustrated in and the processing in each step in the flowcharts described below can be implemented.

The size of the network can range from a small network to a large network such as a personal area network PAN a local area network LAN a metropolitan area network MAN and a wide area network WAN and all of the devices are connected to the network. The servers and the printers can be connected to the network over the Internet such as a case of cloud computing.

First to select a printer the printer driver corresponding to the printer implementing the printing is selected. Next print settings are created. A configuration module in the printer driver creates initial values of the print settings of the document. The user can change and fix the created print settings such that a final print result the user is expecting can be obtained using the application or the user interface of the printer driver . For example the user can change the output paper size and set two sided printing and monochrome printing. The configuration module provides the user interface of the printer driver .

The printer driver includes two types of drivers that is a driver for a first environment and a driver for a second environment described below. The flow of the print processing is changed depending on the selected driver. In this description a flow of printing commonly performed by both drivers is described.

The print settings are saved on the RAM . The storage format can be a binary data structure an extensible markup language XML that is a markup language or the like. The format varies depending on the specifications of the printer driver and the operating system . The print settings are created in each document printing.

In a case where the user wants to save settings such as an optional device configuration of the printer and environmental settings for each user the printer driver stores the settings in a registry database in the operating system . A print manager in the operating system stores default values of the print settings for each user in the registry database . Lastly the printer driver converts the rendering data.

After the creation of the print settings the user executes the print processing and the application notifies the operating system of the execution of the print processing. The operating system performs rendering on the specified printer driver via the graphics engine .

In a case where layout processing is specified by the print settings before the processing proceeds to a rendering module in the printer driver a temporary spool file is created and a layout module is activated. In the layout processing the order of sheets is switched or a plurality of pages are pasted in one sheet. The layout module changes the layout and performs the rendering on the printer driver again. The printer driver which received the rendering data converts the data by using the rendering module into a data language that can be interpreted by the printer that is a printer control language.

In this processing the print settings are also converted into the printer control language. In many cases both of the rendering module and the configuration module are common to a plurality of types of the printers and differences unique to the models are described in a model dependent data file . The rendering module and the configuration module refer to the model dependent data file as needed. The converted data is sequentially stored as a spool file .

The print manager acquires the spool file and manages the schedule of the print processing as a print job file. When the printer is ready to print the print manager sequentially transmit the print job data to the printer via the I O module . The print job data is a content of the print job file. The print data from the application is thus converted into the printer control language and the printing is implemented according to the above described processing. The print data includes the rendering data and the print settings.

To create the print settings of the document the print settings are directly rewritten with the application or a user interface provided from the configuration module in the printer driver is used.

In the Microsoft registered trademark Windows registered trademark operating systems the print settings have the structure referred to as the DEVMODE structure illustrated in . The DEVMODE structure is divided into a standard setting area and a setting area . The standard setting area is publicly defined by the operating system and the setting area is an area extended by the printer driver. The standard setting area includes basic setting values in printing such as page sizes switching of a paper feed stage and switching of color and monochrome. The extended setting area includes values such as discharge functions corresponding to printer options and a fine color adjustment function. The application cannot recognize the extended settings in each printer driver . Consequently the application can directly rewrite only the standard setting area that is defined by the system.

Accordingly the application generally displays the user interface of the printer driver and the user sets the extended print settings . The configuration module provides an application programming interface API in addition to the user interface.

Consequently the user can externally set the extended print settings without displaying the user interface. However to use the API of the configuration module the application is required to handle each printer driver . Consequently general application changes only the standard setting area .

Another printing system to which the exemplary embodiment of the present invention can be applied is described. The printing system illustrated in is referred to as a GDI printing system. Meanwhile is a block diagram illustrating an XPS printing system.

In the XPS printing system printing is performed using a document file format called an XML paper specification as spool data. Similarly to the GDI printing system the XPS printing system runs on the operating system . The print manager a GDI to XPS conversion module and a filter pipeline manager are modules included in the operating system . The printer driver and the individual filters in the filter pipeline manager are stored in the auxiliary storage unit in as the printer driver . The filter pipeline manager is included in the operating system. However the individual filters are modules of the printer driver .

The GDI print application and the XPS print application are stored in the auxiliary storage unit in as the application . The user executes the print processing using the input devices such as the keyboard and the mouse via the GDI print application program hereinafter referred to as GDI application or the XPS print application program hereinafter referred to as XPS application appearing on the monitor of the output device. The print processing is implemented by performing three processes that is selection of a printer creation of print settings and conversion of rendering data in this order.

First the printer to be used for the printing is selected. This means to select the printer driver corresponding to the printer that executes the printing. Next print settings are created. To set the print settings the application reserves a memory for the print settings and the application or the configuration module of the printer driver fills the setting data using the model dependent data file .

In the GDI application a binary DEVMODE structure is used as the print setting data. In the XPS application a print ticket described in XML that is a markup language is used as the print setting data. The DEVMODE structure and the print ticket include as the structure illustrated in the standard area defined by the operating system and the extended area uniquely defined by the printer driver.

The print ticket is print setting information described in an XML format for example as illustrated in and descriptions of the standard area and the extended area are separated by namespaces. The namespaces are the descriptions such as psf psk and xsd in . The specification is open to the public and accordingly its detailed description is omitted. In the parts described as SKIP the definitions of the namespaces are described.

The DEVMODE structure or the print ticket stores the print settings. The application directly performs rewrite to change the print settings. Dedicated settings depending on the printer are made by displaying the user interface of the printer driver stored in the configuration module . According to the settings input by the user via the user interface the printer driver changes the settings depending on the printer in the DEVMODE structure or the print ticket .

The print settings are specifically data necessary to perform the printing such as the output size of the sheet to A4 two sided printing switching between color and monochrome and a specified paper feed stage.

Since the print settings in the print ticket are described in the XML format it is easy to directly change and rewrite all setting values with the XPS application . However the setting values can also be changed using the conventional user interface of the printer driver .

The print settings are created in each document printing. In a case where the user wants to save the settings such as an optional device of the printer or environmental settings for each user the user interface stores the settings in the registry database in the operating system. The print manager in the operating system stores default values of the print settings for each user in the registry database . Lastly the printer driver converts the rendering data. After the print settings are fixed the user executes the print processing via the application.

When the printing is performed via the GDI application the rendering data is transmitted to the GDI to XPS conversion module that functions as the printer driver and an XPS spool file is created. At this time the GDI to XPS conversion module invokes the configuration module and converts the print settings from the DEVMODE structure into the print ticket .

When the printing is performed via the XPS application two methods can be provided that is the XPS application itself creates the XPS file or the operating system creates the XPS file according to a rendering instruction from the XPS application. In either method the XPS spool file is created in the middle of the printing. As described above in the XPS printing system as its feature the XPS spool file is always created in printing.

After the creation of the XPS spool file is completed the processing proceeds to a print filter pipeline process. In the print filter pipeline process printing is performed using a plurality of filters. A filter configuration file controls the number of the filters and the order of the filters. A filter pipeline manager running in the print filter pipeline process performs the processing according to the filter configuration file in this exemplary embodiment in the order of a setting filter a layout filter and a renderer filter . The number and types of the filters differ depending on the configuration of the printer driver .

The print processing is implemented by transmitting the XPS spool file to the filters. The filters respectively process the XPS spool file to advance the processing to the next filter and thus the processing proceeds. Lastly the data is output in a printer control language hereinafter referred to as page description language PDL that is a data language the printer can interpret.

In a case where the printer is an XPS direct printer that can directly read the XPS spool file and print the data all filters can be skipped in carrying out the printing.

The setting filter reads the print ticket and writes data necessary for the printing in the print ticket . The layout filter performs processing relating to the layout for example scaling imposition layout in bookbinding and stamping. The layout filter operates according to the print setting print ticket contained in the XPS spool file . Consequently for example in a case where a setting of imposition is not contained in the print ticket the layout filter passes the XPS spool file without performing any operation and directly transmits the XPS spool file to the next filter.

Lastly in the renderer filter the filter performs rendering processing on the XPS spool file to convert the data into a PDL. The print manager managing the schedule of the print processing manages the PDL data and sequentially registers the print jobs in a queue. When the printer is ready to print the PDL data is transmitted in the order recorded in the queue via the I O monitor .

As described above the main role of the printer driver is to convert the print data from the application into the printer control language to perform the print processing.

The new user interface is implemented in a first execution environment WinRT and the conventional user interface is implemented in a second execution environment Win32 . In other words the execution environments which provide the new user interface and the conventional user interface are different.

In a driver UI for the first environment is software for providing a user interface print setting screen for setting a driver for the first environment that is a printer driver for the first environment. Similarly a driver UI for the second environment provides a user interface print setting screen for setting a driver for the second environment that is a printer driver for the second environment. Application for the first environment and application for the second environment are general application such as a word processor which issues a print instruction to the printer drivers.

The application for the first environment and the driver for the first environment run on first environment execution basic software . Thus the first execution environment WinRT is configured. The application for the second environment and the driver for the second environment and the driver UI for the second environment run on second environment execution basic software . Thus the second execution environment Win32 is configured. The two execution environments run on an operating system kernel .

The driver UI for the first environment runs on the operating system kernel . In that operation while the driver UI for the first environment is running on the first execution environment WinRT a user interface for touch panel is provided. While the driver UI for the first environment is running on the second execution environment Win32 a user interface for keyboard and mouse is provided.

The operating system is composed of the first environment execution basic software the second environment execution basic software and the operating system kernel . In the following flowcharts where the operating system performs the processing one of the software programs is operated to implement the processing.

The flow of the processing in selecting the driver for the second environment from the application for the first environment and performing the printing is described. First the user selects the driver for the second environment from the application for the first environment and instructs to execute the printing. The first environment execution basic software receives the rendering data created by the application for the first environment.

Points in the processing which are different from the print flow described with reference to are described. The first environment execution basic software transmits the received rendering data to the second environment execution basic software . Thus the processing transmits the rendering data from the first execution environment WinRT to the second execution environment Win32 . The second environment execution basic software starts the driver for the second environment selected by the user the rendering data is transmitted to the driver for the second environment and thereby print data is created.

In another printing method the application for the second environment selects the driver for the second environment and performs the printing. In this method the application for the second environment transmits rendering data to the driver for the second environment via the second environment execution basic software . The print flow in this method is similar to that described with reference to and consequently the description of the flow is omitted.

As illustrated in the driver UI for the second environment does not run on the first execution environment WinRT . In such an environment the present specification describes a method of converting setting items that can be set using the driver UI for the second environment into setting items for the first execution environment WinRT to provide a user interface print setting screen of the driver for the second environment.

In the above description made with reference to to facilitate the understanding the drivers and the driver UIs are separately described. In the description below the drivers and the driver UIs are not specifically separated and software implemented by one of or both of the driver and the driver UI is referred to as a printer driver.

Processing for performing print setting using the user interface of the printer driver is described with reference to the block diagram in and the flowchart in .

In step S the operating system invokes an API for using the printer driver from the application . In step S the operating system transmits the DEVMODE structure transmitted from the application via the print manager to the configuration module of the printer driver . In step S the operating system checks whether a flag for displaying the user interface of the printer driver is transmitted via the API from the application .

In displaying the user interface the operating system invokes the printer driver and prepares to establish a user interface.

The print manager of the operating system invokes a Common Property Sheet User Interface CPSUI . The CPSUI creates a platform to be a base in user interface referred to as a property sheet having tabs . The plat form is in the part where the OK button and the cancel button are disposed.

In step S to create a property sheet page in each tab the CPSUI of the operating system receives a dialogue resource template from the configuration module of the printer driver .

The dialogue resource template is a binary file for creating a dialogue that is also used in general application other than the print setting. Generally at the same time when or after the configuration module is read the configuration module reads the dialogue resource template from the auxiliary storage unit to the RAM . The CPU performs the following processing according to the dialogue resource template. The configuration module includes the dialogue resource template such that the configuration module can transmit the dialogue resource template when the configuration module is invoked via the API or the like from the operating system . The operating system reads the dialogue resource template as layout information and creates a graphical user interface GUI .

The operating system can display a new user interface for touch panel simultaneously with the display of the conventional UI using the keyboard and mouse. This processing can be implemented with for example vertically divided screens of the new user interface for touch panel displayed on the left and the conventional user interface displayed on the right.

Consequently the application is required to determine by itself whether the application is started by the conventional user interface for mouse or by the new user interface for touch panel. To make the determination when the application is started the operating system can transmit information indicating a user interface which starts the application to the application. Alternatively the application itself can make an inquiry about the user interface which has started the application to the operating system .

In this exemplary embodiment in step S the operating system determines whether the application that invoked the printer driver is running on the new user interface.

In other words the operating system determines whether the application is the application for the first environment or the application for the second environment.

If the invoked application is running on the conventional user interface NO in step S in step S according to the received dialogue resource template the operating system arranges the described controls as it is to create a user interface.

If the invoked application is running on the new user interface YES in step S in step S the operating system determines whether the printer driver is the printer driver that is compliant with the new user interface for touch panel.

In other words the operating system determines whether the printer driver is the driver for the first environment or the driver for the second environment.

Alternatively the determination can be made depending on whether the new user interface for touch panel is being displayed without determining whether the application that invoked the printer driver is running on the new user interface. Alternatively in a case where only one of the new screen for touch panel and the conventional screen using the keyboard and mouse can be displayed the determination can be made depending on which screen is being used.

When the printer driver is installed the printer driver registers in advance whether the user interface is for mouse or for touch panel in the operating system . Consequently the operating system can determine whether the user interface is registered for the new interface for touch panel in the printer driver.

In the present specification as described above whether the printer driver is the printer driver complying with the new user interface for touch panel is determined. However the processing after step S can be always performed. For example a mode for always executing the processing after step S such as a forcible execution mode can be provided. In the forcible execution mode the processing after step S is always implemented.

Advantages of the determination whether the printer driver is the printer driver that is compliant with the new user interface for touch panel are described. In this case print settings can be performed using the user interface for touch panel even if the printer driver complying with the new user interface for touch panel has a dialogue resource template for a conventional screen. Consequently the user can use the user interface without recognizing whether the print settings are converted from the dialogue resource template into settings for the new user interface for touch panel or settings made by the printer driver .

Since the dialogue resource template is for the conventional screen if the printer driver has the new user interface for touch panel YES in step S in step S the operating system starts the user interface. In other words if the printer driver includes the driver UI for the first environment the operating system starts the driver UI for the first environment.

If the printer driver the driver for the second environment includes only the dialogue resource template NO in step S in step S the operating system converts the controls described in the dialogue resource template and establishes a user interface. Detailed description will be made below with reference to .

In step S the operating system invokes the initialization program of the user interface of the printer driver .

In step S after the completion of the initialization the operating system invokes a window message of the user interface of the printer driver . In response to the operation of the user the operating system transmits each window message to the printer driver . The printer driver processes the window message and returns the processing to the operating system again. In step S if an instruction of ending the user interface is transmitted by the operation of the user the operating system receives the window end message and ends the processing of the user interface.

In step S the operating system acquires the DEVMODE structure of the print settings changed by the operation of the user interface from the printer driver . In step S the operating system returns the changed DEVMODE structure to the application and thereby the print settings changed via the user interface can be reflected.

The dialogue resource template describes an ID associated with the type attributes location and program of the control arranged on the property sheet page. For example the sixth line in indicates that the type of the control is COMBOBOX the ID is IDC CB PROFILE and the location is 60 4 90 and 100 and the others indicate the attributes.

The ID is assigned to a control to specify the control. For example using the ID the configuration module adds a candidate of the COMBOBOX and acquires the value currently being selected.

The controls are parts in the user interface included in the operating system . Typical parts are described below.

A TEXT displays a character string and includes three types depending on the arrangement of the characters that is a LTEXT a RTEXT and a CTEXT. illustrates the COMBOBOX. The use of the COMBOBOX enables selection of one option from the list of mutually exclusive options. illustrates a CHECKBOX. The use of the CHECKBOX enables selection of one option from two obviously distinct options. illustrates an EDITTEXT. The use of the EDITTEXT enables display input and edition of texts and values.

With reference to the flowchart in that is within the processing in step S it is described how the operating system converts the dialogue resource template transmitted from the printer driver into the user interface for touch panel.

As described above the configuration module of the printer driver includes the dialogue resource template. In step S the operating system reads the dialogue resource template transmitted from the printer driver one line at a time and acquires one control. In step S the operating system continues the processing until all controls are read.

In step S if the read control is a TEXT YES in step S the operating system reads the next control and analyzes the control.

In step S if the next control is also a TEXT YES in step S the operating system reads the RAM and determines that the TEXT is not associated with other controls. In step S the operating system arranges the control as a TEXT to be displayed as information.

In the following processing when association of a control is performed the operating system stores the association in the RAM . The association is determined by the operating system by reading the information in the RAM .

If the control next to the TEXT is another control NO in step S in step S the operating system determines that the TEXT is one of options in a first hierarchy and lists the options. The first hierarchy is a page displayed first when the user opens the user interface. When the screens are switched in response to pressing operation of an option item or a button a second hierarchy a third hierarchy and subsequent hierarchies are sequentially displayed. The first hierarchy is laid out with the lined up options of the TEXT .

In the user selects a TEXT the name of the print setting item in the first hierarchy and the screen proceeds to the screen in for fixing the individual setting. At that time the screen in is replaced with the screen in and displayed. The replacement means that the same area as the screen of is overwritten by the screen of and after the screen of is displayed the screen of is not displayed and thus the screen transition is performed. Specifically on the screen of the TEXTs the names of the print setting items displayed in are erased hidden from the screen. Instead of the TEXTs in the RADIOBUTTONs are arranged and the options of the print setting item are displayed.

In the names of the print setting items are displayed without displaying the options of the print setting items. In the options of the print setting item are displayed without displaying the names of the print setting items. By this processing even if the monitor is a small device the information to be displayed can be reduced and the font sizes of the name of the print setting item and the options of the print setting item can be increased. As a result an easily viewable user interface can be provided. If the options of the print setting item are displayed using a COMBOBOX or a LISTBOX all of the options are not simultaneously displayed.

In step S the operating system associates the next control found in step S as an option of the arranged TEXT.

In step S if the read control is a COMBOBOX or a LISTBOX in step S the operating system sets the control as a change candidate of control as a RADIOBUTTON.

In step S the operating system determines whether the acquired control is associated with the TEXT in step S.

If the control is associated with the TEXT YES in step S in step S the operating system arranges the control in the second hierarchy. If the control is not associated with the TEXT NO in step S in step S the operating system arranges the control in the first hierarchy.

With the above described processing the controls in the dialogue resource template are converted and the user interface is established.

In the user interface for touch panel the positional coordinates for locations the type and size of the font described in the dialogue resource template are ignored. With respect to the locations the space for arranging the conventional controls is small and the same layout cannot be achieved. Consequently even if a scroll bar or the like is used to maintain the same layout the operability is significantly decreased.

With respect to the type and size of the font if the font is directly used the display is too small. In such a case on a small monitor such as a touch panel the recognition of the characters is difficult. To solve the problem the default font and size used on the user interface for touch panel are used as it is. In the user interface for touch panel the property sheet page is displayed on the entire of the screen and the font size is large. Consequently if the functional name and the control are arranged at the same time the operability is decreased.

To solve the problem in the first hierarchy only the functional names are listed. The user clicks a name and selection can be made using the control corresponding to the function. If the user uses a COMBOBOX or a LISTBOX it is hard for the user to recognize an area where the user can select the individual items by touching the touch panel. Consequently the COMBOBOX and the LISTBOX are changed to RADIOBUTTONs to facilitate the recognition of the touch position.

In the present specification the COMBOBOX and the LISTBOX are changed to the RADIOBUTTONs. Alternatively the COMBOBOX and the LISTBOX can be directly displayed.

Alternatively a control referred to as OWNERDRAW which performs rendering by a program can be used. According to the OWNERDRAW the printer driver the driver for the second environment performs the rendering and consequently replacement with another control or font cannot be performed. To solve the problem a control is arranged only in the secured rendering area and the rendering is performed.

With reference to the flowchart in that is within the processing in step S the flow of actually converting the control set as a candidate to be converted into a RADIOBUTTON in step S into the RADIOBUTTON is described below.

In step S the operating system invokes the initialization program of the user interface of the printer driver .

In step S the operating system determines whether the printer driver has invoked an instruction for adding an item of an option to the COMBOBOX or the LISTBOX during the initialization processing. If the instruction for adding the item of the option is invoked YES in step S the operating system arranges the RADIOBUTTONs.

The operating system determines that the order of the arrangement of the RADIOBUTTONs is the order that the instructions for adding the items of the options are received from the printer driver .

The operating system analyzes the character strings of the items and determines that three or more character strings determined to be page sizes are added the operating system determines that the items are RADIOBUTTONs for selecting a page size.

The character strings for determining the page sizes include A3 A4 A5 B3 B4 B5 LETTER LEDGER 11 17 EXECUTIVE POSTCARD and ENVELOPE . The three or more character strings are required because it should be determined whether the control is different from a control for selecting a default sheet in which only A4 and LETTER are listed.

If the operating system determines that the items are for the page sizes the operating system rearranges the items such that the TEXT in the first hierarchy associated with the RADIOBUTTON is located at the top. Since the control for selecting a page size has a high priority for the user the TEXT is moved to the conspicuous position at the top.

With reference to the flowchart in that is within the processing in step S the flow for opening the second hierarchy and the third hierarchy of the conventional user interface screen included in the user interface of the printer driver is described.

The second hierarchy and the third hierarchy of the conventional user interface screen are screens invoked using a button such as the page option in .

After the PUSHBUTTON is pressed in step S the operating system determines whether to receive the dialogue resource template from the printer driver . The operating system can determine whether to receive the dialogue resource template depending on whether the API for receiving the dialogue resource template is invoked.

If the operating system receives the dialogue resource template YES in step S in step S similarly to the case of the first hierarchy the operating system analyzes the dialogue resource template and establishes a new user interface for touch panel. In this processing for the ID of the control of the established new user interface the ID of the control specified in the dialogue resource template is directly used. Therefore the configuration module can specify the control even if the UI is changed.

If the operating system does not receive the dialogue resource template NO in step S in step S the operating system determines whether an instruction for creating a window is transmitted from the printer driver .

If the instruction for creating a window is transmitted from the printer driver YES in step S the operating system determines that an instruction is given to open the second hierarchy. In step S the operating system switches the screen to the conventional user interface for keyboard and mouse from the user interface for touch panel.

By switching the screen to the conventional screen the operating system can display a conventional window created by the printer driver other than the dialogue.

In step S the operating system invokes the initialization program of the user interface of the printer driver . In step S the operating system invokes a window message and starts the processing of the second hierarchy.

The DEVMODE structure that indicates the print settings has already been transmitted to the printer driver S and the printer driver is not unloaded. Consequently the print settings can be directly used.

In step S if the operating system receives a window end message from the user interface of the printer driver YES in step S the operating system starts the end processing of the user interface.

In step S the operating system determines whether the current screen is the conventional user interface screen for keyboard and mouse. If the screen is the conventional user interface screen YES in step S in step S the operating system switches the screen to the new user interface screen for touch panel.

As described above the operating system uses the dialogue resource template for the conventional user interface included in the printer driver to establish the new user interface screen for touch panel.

Accordingly the user can use the user interface optimized for touch panel irrespective of the type of the printer driver.

Further the user interfaces uniquely created by the printer driver such as the second hierarchy and the third hierarchy can be properly displayed with the switching operation to the conventional screen.

Further the establishment of the user interface with the controls and the layout suitable for touch panel can achieve a unified operational feeling.

In the description of step S in the control is performed depending on whether the application is executed in the first execution environment or the second execution environment. Alternatively two applications can be used in the first execution environment or in the second execution environment and in step S the user interface to be displayed can be changed depending on a determination which of the two applications is running.

According to the exemplary embodiment of the present invention the new user interface suitable for touch panel can be displayed even if the conventional printer driver is used and consequently operational difficulty in the processing can be reduced. Further the easy to use user interface can be displayed without a new printer driver.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

This application claims priority from Japanese Patent Applications No. 2011 198164 filed Sep. 12 2011 and No. 2012 143141 filed Jun. 26 2012 which are hereby incorporated by reference herein in their entirety.

