---

title: Dynamic printing system, apparatus and method
abstract: Improved techniques which enable a user of a terminal to select a printer, without a priori knowledge of available printers, for printing a print job are provided. A map indicating locations of available printing devices is retrieved from a back-end server based on user information or other information retrieved from the user, and provided to the user terminal for user selection of an appropriate printing device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08261259&OS=08261259&RS=08261259
owner: Ricoh Company, Ltd.
number: 08261259
owner_city: Tokyo
owner_country: JP
publication_date: 20120302
---
This application is a continuation in part of U.S. patent application Ser. No. 11 713 125 filed Mar. 1 2007 now U.S. Pat. No. 8 185 887 and entitled SYSTEM AND METHOD FOR PRINTER DRIVER DISTRIBUTION WITH SEARCHABLE MAP DATABASE .

This disclosure relates to apparatuses methodologies and systems for providing print services and in particular dynamically providing print services without a priori user knowledge of available print devices.

In the current information age there are often discussions of the desirableness of a paperless society. However notwithstanding such discussions there remains a great need by users of computers and other terminal devices including tablets and mobile phones for printing functionality. Therefore devices having printing functionality such as printers copiers multi function devices etc. continue to play a significant role in information technology IT at home and at work.

A computer or information terminal typically needs printer driver software in order to communicate properly with a printing device and a printer driver generally provides a software interface that allows the operating system and software applications running on the computer or other terminal devices to interface functionally with the printing device. For example the printer driver software may match standardized commands from the computer s operating system to specific capabilities of the printing device.

Printing devices typically provide users with a plurality of print options such as paper tray size color etc. which are accessible through user interfaces invoked by applications and the task of providing such print options is performed by the printer driver software installed on the computer or other terminal devices. For example conventional printer driver software may include a printer interface DLL dynamic link library i.e. a collection of resources shared by other programs as shown in to provide a user interface through which users can view and edit print options e.g. configuration parameters of the printer driver .

The set of printing devices and functionalities available to a user can change over time because printing devices can be replaced or updated. In addition the current trend is that more and more of the computers and other terminals devices which can access the peripherals are mobile. Therefore the number and functionality of printing devices available to a user can vary depending on the location of the computer or terminal device used by the user at that moment.

As a result the dynamic nature of modern day printing environments makes it difficult for a user at a terminal i.e. PC tablet mobile phone etc. to have prior knowledge of the printing devices that are available to the user at the moment when the user wishes to print a document.

However conventional IT systems often do not provide a user friendly system for a user at a terminal to find the appropriate or desired printer particularly when the terminal has been moved from its usual location to a new or different location. For example when a user invokes a print function the user interface of the conventional system may display a preconfigured list of printers as shown in and the user interface may allow the user to set basic print options. Further other printer specific options may be specified after the Properties button on the user interface screen is pressed in the example shown in .

However the list of printers displayed in the print user interface is fixed regardless of the location of the terminal and is not dynamically updated to include newly added printers or exclude printers that have been moved elsewhere or removed from the network altogether. Thus the user must have prior knowledge of the available printers i.e. that such printers are available to the user where the printers are located what kinds of printers they are and what kinds of settings are available on the printers before selecting a printer for printing a document. Even with such prior knowledge the user cannot be sure whether the list of printers displayed in the print user interface is up to date at the time of printing i.e. whether the printers displayed still exist and whether additional printers have become available because such a list of printers is static and not maintained dynamically.

An improved approach for dynamically providing print services which allows a user to select an appropriate printer to which a print job can be sent is needed.

This disclosure provides tools in the form of apparatuses methodologies and systems that allow a user to select without a priori knowledge of available print devices a printer to which a print job can be sent.

In an aspect of this disclosure a system for dynamically providing print services without a priori user knowledge of available print devices allows a user to select a print device from a map indicating locations of a plurality of print devices and sends a user specified print job to the print device selected by the user.

In another aspect a system for dynamically providing print services without a priori user knowledge of available print devices allows a user to specify basic print options through a user interface and then retrieves a list of available print devices that support such basic print options.

In another aspect a system for dynamically providing print services receives a print job from a user retrieves from a back end server a list of available print devices based on a location of the user receives user selection of a specific print device from the list of available print devices and sends the print job to the specific print device selected by the user.

In another aspect in a system for dynamically providing print services a device list query containing information regarding a user at a terminal is submitted to a back end server and a map or list of print devices compiled is retrieved based on the information contained in the device list query and then displayed for user selection of a destination print device.

In another aspect a system for dynamically providing print services without a priori user knowledge of available print devices displays a print user interface containing a search field through which a user at a terminal may specify keyword terms and retrieves and displays a map or list of print devices compiled based on the keyword terms for user selection of a destination print device.

In describing examples and exemplary embodiments illustrated in the drawings specific terminology is employed for the sake of clarity. However this disclosure is not intended to be limited to the specific terminology so selected and it is to be understood that each specific element includes all technical equivalents that operate in a similar manner.

In this disclosure tools are provided for dynamically providing print services without a priori user knowledge of available printers by providing a map or list of available printers and allowing a user to select an appropriate printer from the map or list of printers.

Referring now to the drawings wherein like reference numerals designate identical or corresponding parts throughout the several views a general workflow of a printing system according to an exemplary embodiment will now be discussed with reference to .

In the exemplary embodiment shown in system includes client server printer database map repository and printing device . In a typical workflow within the system a user enters via a print user interface or application on the client terminal selections of basic print options and or a location on a map image provided by the user interface as discussed infra and submits the entered selections. The selections are processed by connector part of the client to formulate a query and such query is output to server step S . The server processes the query step S to extract the pertinent terms to search the printer database step S . In the exemplary embodiment of location is one of the terms included in the query and the server utilizes the location term to formulate a request to the map repository to retrieve an appropriate map image step S . Based on results from the search of the printer database and the map image returned by the map repository the server generates a map indicating printers available to the user step S and outputs such map information to the client . The connector part of the client which is configured to receive such map data from the server forwards the received map data to the user interface through which the map is presented to the user for user selection of a destination printer.

The printer database stores printer properties information of a plurality of printers. For example many printers store printer data such as its attributes or printer properties information in a Management Information Base MIB . The MIB may conform to the SNMP Simple Network Management Protocol protocol and printer properties information can be obtained from the MIB through SNMP queries. As another example the printers on the network can be discovered by broadcast of SNMP messages over the network and then waiting for particular responses from printer devices.

The map repository stores a plurality of map images which are retrieved by the server and locations of the available printers are plotted on the retrieved map images.

The query information may include location information which may be used by the server to determine which map images to retrieve from the map repository and which of the available printers to plot on the map images. The user may manually specify a location for example a location on a map image a specific location at which the user desires to locate an appropriate printer etc. or the client may track its own location for example determined by a Global Positioning System receiver or another location determining device and provide such location information to the server . Alternatively location information may be extrapolated from locations of routers locations provided by wireless networks or other wireless technologies such as RFID etc.

Exemplary embodiments which build on the system are described below with reference to the examples of . In the following exemplary embodiments the client and the server correspond to terminal devices and back end servers of respectively.

In the example of office A includes multiple floors including floor A and floor A and can include many additional floors . On floor A a terminal A a printer A a copier A and a multi function device A are interconnected through a network . Similarly a terminal B a printer B a copier B and a multi function device B on floor A are interconnected through the network . Floor A further includes a back end server and a database .

The terminal A can access the printing devices on floor A e.g. the printer B the copier B and the multi function device B as well as the printing devices on floor A e.g. the printer A the copier A and the multi function device A . Similarly the terminal B can access the printing devices on floor A e.g. the printer A the copier A and the multi function device A as well as the printing devices on floor A e.g. the printer B the copier B and the multi function device B .

Office A can include many more terminals and printing devices other than those shown in . Indeed the printing system of this disclosure is preferably configured to be scalable such that terminals and printing devices can be added to the system as desired and needed.

The terminals A and B which correspond to the client shown in can be any computing device including but not limited to a personal notebook or workstation computer a tablet e.g. iPad a kiosk a personal digital assistant PDA a mobile phone or handset another terminal etc. that can communicate with other printing devices through the network . An exemplary configuration of the terminals A and B is further described infra with reference to the example of .

The network can be a local area network a wide area network or any type of network such as an intranet an extranet for example to provide controlled access to external users for example through the Internet the Internet etc. or a combination thereof. Further other communications links such as a virtual private network a wireless link etc. may be used as well for the network . In addition the network preferably uses TCP IP Transmission Control Protocol Internet Protocol but other protocols can also be used. How devices can connect to and communicate over the network is well known in the art and is discussed for example in How Networks Work by Frank J. Derfler Jr. and Les Freed Que Corporation 2000 and How Computers Work by Ron White Que Corporation 1999 the entire contents of each of which are incorporated herein by reference.

The back end server which corresponds to the server of may maintain via the database printer data for the printing devices connected via the network i.e. the printer A copier A multi function device A printer B copier B and multi function device B and map data which include a plurality of map images used for creating a map of available printing devices. The printer data and the map data are stored in the database . For example the printer data may include a list of printing devices available on the network detailed information regarding each printing device and a printer driver corresponding to each printing device. The map data may include text based location information regional maps campus maps and floor maps that may be utilized to find and plot available printing devices.

The terminals A and B may access the back end server via printer interface DLLs which is described in the Background section of the present disclosure or port monitors.

A port monitor as shown in provides a communication path between a user mode print spooler and a kernel mode port driver stack that accesses the port hardware. The print spooler stores print jobs and sends them to the port monitor when they are ready for printing. The port driver stack receives from the port monitor information regarding the network address of the destination printer and the type of the port to which the destination printer is connected and accesses the port hardware to transmit the print job to the destination printer.

A printer interface DLL via a connector service application a component which provides a communication link between the printer interface DLL and the back end server or a port monitor of the terminal A or B submits a query to the back end server for example by accessing a predetermined network address of the back end server such as http back end interface.html with user ID and password for a map indicating locations of a plurality of printers that are available on the network . In response the back end server accesses the database retrieves the printer data and map data stored in the database and relays the relevant printer information to the user terminal i.e. terminal A or B from which the query originated. A user at the user terminal may then select a destination printer from the map of available printers. In another embodiment instead of a map the back end server may return a list of available printers from which the user may select a destination printer.

The port monitor preferably accesses the back end server to retrieve a map or list of available printers only in a case that the print job received by the port monitor does not contain information regarding the destination printer i.e. the printer interface DLL did not access via a connector service application the back end server and allow the user to select a destination printer .

An exemplary configuration of the back end server is further discussed infra with reference to the example of .

Although the back end server and the database are shown to be separate units on floor A of Office A in the example of the system is not limited to such configuration and the back end server and the device may be located elsewhere and also be combined in a single device or implemented as software.

Although the enterprise environment of is explained supra as an example of an IT environment in which the subject matter of this disclosure can be applied it should be appreciated that the subject matter of this disclosure can also be applied in other network printing environments in which a plurality of printing devices are available for printing from a terminal.

Another exemplary configuration of a printing system is discussed below with reference to the example of .

In system includes a terminal A which is interconnected with a printer A a copier A and a multi function device A in a network environment A and a terminal B which is interconnected with a printer B a copier B and a multi function device B in a network environment B. In addition the system includes a back end server and a database which are accessible through a virtual private cloud .

The terminal A includes an application UI Aa a connector Ab and a printer interface Ac. Similarly the terminal B includes an application UI Ba a connector Bb and a printer interface Bc.

The terminals A and B interact with the back end server through the connectors Ab and Bb via a virtual private network which in part includes the Internet and interact with the printing devices i.e. the printers A and B the copiers A and B and the multi function devices A and B via the printer interfaces Ac and Bc.

The application UI allows the connector to communicate with a user at the terminals A and B. The connector is a component which provides a communication link between the printer interface and the back end server . The printer interface allows the terminals A and B to communicate with a printing device i.e. the printers A and B the copiers A and B and the multi function devices A and B .

The virtual private cloud is a private cloud existing within a shared or public cloud. The resources allocated to the virtual private cloud are not accessible by the public.

For example each of the network environments A and B may be an office of an enterprise. IT components of each of the offices are interconnected by a network within the network environments A and B respectively. Each of the network environments A and B can include one or a combination of wired or wireless networks. The network environments A and B as well as possibly other networks jointly constitute an enterprise network not identified in .

It should be understood that the offices of the enterprises need not be geographically near each other. Thus the offices can be in different continents countries states districts cities or towns or on the other hand they can be adjacent to each other . However the subject matter of this disclosure provides a user with a user interface including a map or list of printing resources proximate to a particular geographical location e.g. the location of the user terminal which does not necessarily have a fixed location from which a user is submitting a print job . Thus the user can select an appropriate or desired printer to which the print job is to be sent regardless of whether the user is at the user s home office or at an office the user is visiting.

The operations of the back end server and the database are otherwise similar to that described in connection with the system of .

Another exemplary configuration of a printing system is discussed below with reference to the example of .

In system includes a back end server a database which are accessible through public cloud . The system further includes a terminal which includes an application UI a connector and a printer interface a printer a copier and a multi function device .

The application UI allows the connector to communicate with a user at the terminal . The connector is a component which provides a communication link between the printer interface and the back end server . The printer interface allows the terminal to communicate with a printing device i.e. the printer the copier and the multi function device .

The terminal communicates with the back end server through the connector via the Internet through the public cloud .

A public cloud e.g. the public cloud allows the general public to access certain resources e.g. applications and storage over the Internet. That is dynamic print services provided by the system are accessible to the general public through various terminal devices e.g. PC tablet or mobile phone via the Internet.

For example the back end server maintains a list of publicly available printing devices as opposed to the back end server of which only maintains printing devices within the network and returns a map or list of such printing devices for user selection in response to a device list query submitted by the user terminal of .

In another exemplary embodiment a map service website that maintains a dynamic list of the locations of all printing devices available to the general public may be utilized to draw a map of available printers that are located near the terminal from which the user is submitting a print request.

The operations of the back end server and the database are otherwise similar to that described in connection with the system of .

Another exemplary configuration of a printing system is discussed below with reference to the example of .

In system includes a proxy server a back end server and a database all of which are interconnected by a network within the network environment .

The system also includes a printer a copier a multi function device and a terminal which includes an application UI a connector and a printer interface .

The application UI allows the connector to communicate with a user at the terminal . The connector is a component which provides a communication link between the printer interface and the back end server . The printer interface allows the terminal to communicate with a printing device i.e. the printer the copier and the multi function device .

The terminal communicates via the connector with the proxy server at least in part through the Internet .

The proxy server serves as a gateway to the network environment and allows a user to access resources in the otherwise private network environment . In the system of the terminal might access the back end server by using a proxy server address e.g. along with proxy user ID and password .

The operations of the back end server and the database are otherwise similar to that described in connection with the system of .

An exemplary configuration of the user terminals shown in for example as a computer is shown schematically in . In computer includes a controller or central processing unit that communicates with a number of other components including memory display application software print driver keyboard and or keypad other input output such as mouse touchpad stylus microphone and or speaker with voice speech interface and or recognition software etc. and network interface by way of an internal bus .

The memory can provide storage for program and data and may include a combination of assorted conventional storage devices such as buffers registers and memories for example read only memory ROM programmable ROM PROM erasable PROM EPROM electrically erasable PROM EEPROM static random access memory SRAM dynamic random access memory DRAM non volatile random access memory NOVRAM etc. .

The network interface provides a connection for example by way of an Ethernet connection or other network connection which supports any desired network protocol such as but not limited to TCP IP IPX IPX SPX or NetBEUI to network .

Print driver and application software are shown as components connected to the internal bus but in practice are typically stored in storage media such as a hard disk or portable media and or received through the network and loaded into memory as the need arises.

Depending on the type of the particular terminal device one or more of the components shown in may be missing. For example a particular mobile phone may be missing the print driver and the keyboard .

The computer terminal may be configured such as through the print driver or application to have a plurality of print modes such as PDL mode image mode etc. In the PDL mode the terminal communicates a print job to the printing device by utilizing a page description language PDL for example PostScript etc. and including one or more commands for example PCL PJL etc. in a format which can be processed by the printing device. In image mode the information terminal converts the print job into bitmap data and transmits the bitmap data to the printer device. In any event the print job is communicated from the terminal via one or more packets through the network. Each packet includes in its header the network address for example IP address Mac address etc. of the sending terminal.

Additional aspects or components of the computer are conventional unless otherwise discussed herein and in the interest of clarity and brevity are not discussed in detail herein. Such aspects and components are discussed for example in How Computers Work by Ron White Que Corporation 1999 and How Networks Work by Frank J. Derfler Jr. and Les Freed Que Corporation 2000 the entire contents of each of which are incorporated herein by reference.

Management of the back end server e.g. the back end servers of which communicates with a database storing map images and information regarding a plurality of printing devices can be provided as a web service and an example thereof will now be discussed with reference to .

A web service can include a database management component data import export component logging component printer search component an LDAP component installer package component and a map management . The database management component maintains data in the printer database including deleting searching and updating data in the database. In addition the database management component can periodically or when necessary connect to external databases to obtain updated data for example through ODBC Open Data Base Connectivity . The data import export component allows a user for example system administrator to import a data file for example a CSV file and save the data in the file to the database and may also allow the user to export data from the database. The logging component automatically logs activity on the system such as change to the database driver download invocation of the installation application invocation of configuration and management tools etc. The printer search component searches the network for printers using for example Simple Network Management Protocol SNMP . The LDAP component is provided for communications with an external printer management system such as by Lightweight Directory Access Protocol LDAP with the server of such a system or to access an active directory. The installer package component upon request loads a printer driver configuration and creates an installer of the printer driver. The installer and driver information are packaged for download to the information terminal. The map management component searches a map repository for appropriate map image based on location information. In addition as mentioned supra the map management component can communicate through ODBC or a Web service with external map databases.

Some methods which may be used for example with the systems of are described below with reference to .

A method for dynamically providing print services according to an exemplary embodiment is discussed below with reference to the example of .

Although the steps of are described as being performed by a port monitor previously discussed in connection with the system of similar steps may be carried out by a connector service application at the request of a printer interface DLL shown in .

First a user invokes a print function from an application running on a terminal e.g. by clicking on a print button without specifying a destination printer to which the print job is to be sent for example via a universal printer driver.

A universal printer driver is a printer driver that relies on the standard languages of printers rather than one that is coded specifically for a particular model of printer. The universal printer driver maybe used over a network for computer systems that do not use a standard operating system where it would be inconvenient for the network administrator to configure specific settings for each machine. Instead the universal printer driver can be installed on each machine to facilitate the printing process.

For example a printing system may allow basic print settings to be specified through a printer selection user interface via the universal printer driver and allow additional printer specific settings to be specified once a destination printer is selected. The printer driver for the selected destination printer may already be installed on the user terminal or may be downloaded and installed from a server e.g. the back end server discussed herein in connection with and .

In a case that the print job is submitted by the application without a specified destination printer the port monitor receives the print job step S and recognizing that a destination printer has not been specified formulates a device list query to be submitted to a back end server step S . The device list query may include a variety of information regarding the user submitting the print job. For example the device list query may include information regarding the location of the user terminal from which the user submitted the print job and such location information maybe used to filter the list of available printers returned by the back end server. Also the device list query may include the basic print options specified by the user through the printer selection user interface via the universal printer driver and the back end server may only return information regarding printers that support such print options. Further the device list query may include login credentials e.g. user ID and password of the user for determining which printers the user has access to from the plurality of printers available through the back end server.

The device list query may be submitted to the back end server using HyperText Transfer Protocol HTTP HyperText Transfer Protocol Secure HTTPS Simple Object Access Protocol SOAP or representational state transfer REST .

The formulated device list query is submitted to the back end server and the back end server returns a map or list of available printers drawn or compiled based on the information provided in the device list query step S . The returned device map list may be for example in Extensible HyperText Markup Language XHTML HyperText Markup Language HTML Extensible Markup Language XML Cascading Style Sheets CSS an image format or any combination thereof.

After retrieving the device map list the port monitor displays a destination printer selection dialog box through a user interface to the user terminal step S . The destination printer selection dialog box may be displayed in an XHTML or HTML viewer.

The destination printer selection dialog box may for example display the printers and the corresponding information in a list format as shown in . The drop down menu where it currently says Keyword can be used to search the printer database by keyword as shown in location available settings or any other relevant criteria. The user may click on the link that says Advanced Search in order to specify more detailed search criteria. The link that says MAP may display the available printers in a map and allow the user to select a printer by clicking on the map e.g. as shown in . The link that says My Record may display a history of printer usage by the particular user.

The destination printer selection dialog box can also display the printers on a map for example with printer icons indicating the locations of the printers as shown in . The map maybe retrieved from the back end server or drawn based on printer location information and map images retrieved from the back end server. The map may also be drawn based on the location information of the available printers retrieved from the back end server and a map retrieved from a generic map service such as Google Maps. The map preferably indicates where the user is located. The map may also indicate how far the printers are located from the user depending on the situation. For example if the user is selecting a printer from the numerous printers on the same floor of an office the distance information may not be as crucial as in a case where the user is looking for a public printer on a random street in Manhattan. The map may also include zoom in zoom out and other functionalities to improve user experience.

The examples shown in are mere examples and buttons fields and other options and features may be added or removed to create many different configurations of a screen for selecting a destination printer.

Upon selecting a destination printer the user may be able to specify additional settings such as image resolution or tray that may not have been available via the universal printer driver.

After the user selection of a destination printer is received the port monitor sets network information based on device data of the destination printer retrieved from the back end server step S . Based on the network information the port monitor sends the print job to the destination printer selected by the user step S .

As shown in a connector service application which is described in greater detail with reference to in an exemplary embodiment may access the back end server A to retrieve printer information and present a map or list of available printers to the user via the client terminal indicated by the dotted line . Upon user selection of a destination printer device data corresponding to the destination printer is sent along with the print job to the port monitor A and the port monitor A sends the print job to the destination printer i.e. the printing device A .

In another exemplary embodiment not shown in after user selection of a destination printer the back end server A may be queried again for a network address of the destination printer and the network address is used by the port monitor A to send the print job to the destination printer i.e. the printing device A .

As shown in a port monitor which is described in greater detail with reference to in an exemplary embodiment may access the back end server B to retrieve printer information and present a map or list of available printers to the user via the client terminal indicated by the dotted line . Upon user selection of a destination printer the port monitor A sends the print job to the destination printer i.e. the printing device A .

In another exemplary embodiment not shown in after user selection of a destination printer the back end server A may be queried again for a network address of the destination printer and the network address is used by the port monitor A to send the print job to the destination printer i.e. the printing device A .

The implementation of the steps shown in A and B are further discussed below with reference to the examples of .

In an exemplary embodiment the printer interface DLL discussed in the Background section of the present application provides in addition to printer configuration options such as paper tray and font selection a user interface for displaying a map or list of available printing devices via the connector service application as shown in . Such an embodiment is further discussed below with reference to .

When a user pushes a print button in an application e.g. Microsoft Word the application initiates a print request by displaying a printer selection screen to the user through the printer selection user interface step S . The printer selection user interface displays for example upon activation of a printer properties button a printer properties screen through the printer driver user interface step S . Upon activation of a search button on the printer properties screen the printer driver user interface sends a printer search request to a connector service application a component which provides a communication link between the printer interface DLL and a back end server step S . The connector service application then connects to the back end server and sends a query for printing device information step S .

As discussed herein with reference to such a device list query may be submitted to the back end server using HTTP HTTPS SOAP or REST.

In response to the submission of the device list query by the connector service application the back end server sends printing device information and or map images including location information of the printing devices back to the connector service application step S . For example the device map list sent back to the connector service application may be in XHTML HTML XML CSS image format or any combination thereof.

As discussed herein with reference to the request for printing device information can contain the location information of the user terminal e.g. plain text or GPS coordinates the network address of the user terminal print options specified by the user or the login profile information of the user and such information can be utilized to determine the type of printers to which the user might prefer to submit print requests. For example the map or list of printing devices provided to the user preferably contains only those printing devices that are accessible by the user as well as support the basic print options specified by the user. For example if the print options shown in are submitted the printing devices included in the map or list should at least be capable of printing in color.

Using the printing device information and the map images retrieved from the back end server the connector service application displays a map or list of available printing devices in a destination printer select dialog box to the user through a connector user interface step S . For example the destination printer select dialog box displayed through the connector user interface may be displayed in an XHTML or HTML viewer.

The user selects a destination printing device from the map or list of available printing devices and the connector service application receives the user selection of the printing device through the connector user interface step S .

As discussed herein with reference to the example of an exemplary configuration of a list of printing devices is shown in and an exemplary configuration of a map of printing devices is shown in . In addition to these examples the printer selections screen can display the available printing devices in other forms such as a tree view wherein the user can arrive at a desired printer by traversing down the tree.

After the user selection of a destination printing device is received the destination printing device information is sent back through the printer driver user interface step S and the printer selection user interface step S . Then the application sends the print request along with a print job to the destination printing device upon confirmation of the user via the printer selection screen step S . The port monitor receives the print job sent by the application and sends the print job to the specified destination printing device step S . The printing status is then reported back to the port monitor by the destination printing device step S .

The steps shown in are again illustrated in using a block diagram. The arrows in indicate a flow of information among the various elements shown in the example of . In the exemplary embodiment shown in the printer interface DLL connector service application and destination printer select dialog box all of which are part of a client terminal as indicated by the dotted line interact with the back end server in a manner similar to that between the client and the server of and that between the terminals and the back end servers of .

When a user pushes a print button in an application e.g. Microsoft Word the application initiates a print request by displaying a printer selection screen to the user through the printer selection user interface step S . The application submits a print job to the destination printing device upon confirmation of the user e.g. by pressing the OK button via the printer selection screen step S . The port monitor upon receiving the print job and recognizing that the destination printing device has not yet been specified connects to a back end server and sends a query for printing device information step S .

As discussed herein with reference to such a device list query may be submitted to the back end server using HTTP HTTPS SOAP or REST.

In response to the submission of the device list query by the port monitor the back end server sends printing device information and or map images including location information of the printing devices back to the port monitor step S . For example the device map list sent back to the port monitor may be in XHTML HTML XML CSS image format or any combination thereof.

As discussed herein with reference to the example of the request for printing device information can contain the location information of the user terminal e.g. plain text or GPS coordinates the network address of the user terminal print options specified by the user or the login profile information of the user and such information can be utilized to determine the type of printers to which the user would like to submit print requests. For example the map or list of printing devices provided to the user preferably contains only those printing devices that are accessible by the user as well as support the basic print options specified by the user. For example if the print options shown in are submitted the printing devices included in the map or list should at least be capable of printing in color.

Using the printing device information and or the map images retrieved from the back end server the port monitor displays a map or list of available printing devices in a destination printer select dialog box to the user through a port monitor user interface step S . For example the destination printer select dialog box displayed through the port monitor user interface may be displayed in an XHTML or HTML viewer.

The user selects a printing device from the map or list of available printing devices and the port monitor receives the user selection of the printing device through the port monitor user interface step S .

As discussed herein with reference to the example of an exemplary configuration of a list of printing devices is shown in and an exemplary configuration of a map of printing devices is shown in . In addition to these examples the printer selections screen can display the available printing devices in other forms such as a tree view wherein the user can arrive at a desired printer by traversing down the tree.

After the user selection of the printing device is received the port monitor sends the print job to the destination printing device step S . The printing status is then reported back to the port monitor by the destination printing device step S .

The steps shown in are again illustrated in using a block diagram. The arrows in indicate a flow of information among the various elements shown in the example of . In the exemplary embodiment shown in the port monitor DLL destination printer select dialog box and printer interface all of which are part of a client terminal as indicated by the dotted line interact with the back end server in a manner similar to that between the client and the server of and that between the terminals and the back end servers of . After the destination printer is selected by the user the print job is submitted to the destination printer i.e. printing device .

The printer interface e.g. the kernel mode port driver stack shown in receives information regarding the network address of the destination printer and the type of the port to which the destination printer is connected and accesses the port hardware to transmit the print job to the destination printer. Various network protocols such as Transmission Control Protocol Internet Protocol TCP IP Line Printer Remote LPR protocol Internet Printing Protocol IPP or Server Message Block SMB may be used e.g. by the port monitor DLL to submit a print job to the destination printer over a network or the Internet. Different network protocols may use different ports and port settings e.g. similar to those configured in Microsoft Windows .

The aforementioned embodiments and examples are illustrative and many variations can be introduced on these embodiments without departing from the spirit of the disclosure or from the scope of the appended claims. For example elements and or features of different illustrative embodiments may be combined with each other and or substituted for each other within the scope of this disclosure and appended claims.

Further it should be apparent to one skilled in the art that such elements can be implemented in a single device or distributed across a network or over a transmission channel or implemented as hardware or software or a combination.

Additional variations may be apparent to one of ordinary skill in the art from reading U.S. patent application Ser. No. 11 713 125 filed Mar. 1 2007 and entitled SYSTEM AND METHOD FOR PRINTER DRIVER DISTRIBUTION WITH SEARCHABLE MAP DATABASE the entire contents of which are incorporated herein by reference.

