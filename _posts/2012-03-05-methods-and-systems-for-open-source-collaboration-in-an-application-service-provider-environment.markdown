---

title: Methods and systems for open source collaboration in an application service provider environment
abstract: A system and method for integrating a plurality of web-based applications with a web-based file management system. The web-based application may provide a service to the users of the web-based file management system, such that the web-based application can interact with the files of said users. The integration of the service of the web-based application with the web-based file management system is achieved through a simple web interface to configure the service, without the developer of the web-based application having to change the application programming interface (API) of the application. The user of the web-based file management system may add services of a plurality of available web-based applications and use these services with one or more files that are stored on the web-based file management system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08583619&OS=08583619&RS=08583619
owner: Box, Inc.
number: 08583619
owner_city: Los Altos
owner_country: US
publication_date: 20120305
---
This application is a Continuation of and claims the benefit of priority under 35 U.S.C. 120 to U.S. patent application Ser. No. 13 030 090 filed on Feb. 17 2011 now U.S. Pat. No. 8 140 513 issued Mar. 20 2012 entitled METHODS AND SYSTEMS FOR OPEN SOURCE COLLABORATION IN AN APPLICATION SERVICE PROVIDER ENVIRONMENT filed by Sam Ghods et al. which application is a Continuation of and claims the benefit of U.S. patent application Ser. No. 12 260 533 filed on Oct. 29 2008 entitled WEB BASED FILE MANAGEMENT SYSTEM AND SERVICE filed by Sam Ghods et al. which application claims the benefit of U.S. Provisional Application No. 61 055 901 filed on May 23 2008 entitled METHODS AND SYSTEMS FOR OPEN SOURCE INTEGRATION by inventor Sam Ghods which application claims the benefit of U.S. Provisional Application No. 60 992 656 filed Dec. 5 2007 entitled METHODS AND SYSTEMS FOR OPEN SOURCE COLLABORATION IN AN APPLICATION SERVICE PROVIDER ENVIRONMENT by Florian Jourda et al all of which applications are incorporated herein by reference in their entirety.

A server or service class computing device may be used to store files and to provide a website interface for one or more users of this website to access the files. An application developer may wish to make a service available to users of the website. This would allow the users to use the developer s application with the users files.

In implementing a developer s service through an external website one approach taken has been for the developer to make alterations to the application programming interface API of the software providing the service in order to enable the external software to communicate with the API of the developer s service. Significant resources and time may be required to implement the service through the external website by changing the API of the application providing the service. The developer is typically required to modify the API in a specific way to enable the application to send and accept data to and from the external application.

A provider of a website for file storage sharing and collaboration may wish to make a plurality of services available to the users. Such users can then access the plurality of services from a single location to use with their files. The provider of the website may therefore wish to facilitate integration of services with its website.

The foregoing examples of the related art and limitations related therewith are intended to be illustrative and not exclusive. Other limitations of the related art will become apparent upon a reading of the specification and a study of the drawings.

The following examples and aspects thereof are described and illustrated in conjunction with systems tools and methods that are meant to be exemplary and illustrative not limiting in scope. In various examples one or more of the above described problems have been reduced or eliminated while other examples are directed to other improvements.

A technique provides an API agnostic method and system for integrating a web based file management system with one or more web based applications to allow users of the web based file management system to use the web based application with files stored on the web based file management system.

A system based on the technique may include a server storing one or more files of one or more users and providing a website for software developers to integrate their application with the website. This would make the application available to users of the website to use with the files stored on the web based file management system.

A method based on the technique may include transmitting files from the web based file management system to the web based application along with a command structure of the API of the web based application.

An integration engine allows a web based file management system to provide an interface for an application developer to integrate a service in the web based file management system advantageously without the developer having to alter an API of the application providing the service. The integration engine acts as an intermediate between the web based file management system and the web based application allowing them to communicate between each other.

A configuration interface on the web based file management system provides a way for the developer to set up a service that acts on one or more files of a user of a web based file management system upon request of the user. The configuration parameters are stored on the web based file management system and used whenever the service is requested by a user of the web based file management system to act on a file stored on the web based file management system.

A user interface allows a user of a web based file management system to send edit or view files that are stored on the web based file management system with an external application.

In the following description several specific details are presented to provide a thorough understanding. One skilled in the relevant art will recognize however that the concepts and techniques disclosed herein can be practiced without one or more of the specific details or in combination with other components etc. In other instances well known implementations or operations are not shown or described in detail to avoid obscuring aspects of various examples disclosed herein.

A technique provides integration between a computer system storing files a web based file management system WBFMS and a web based application WBA . The WBA is operable to modify a file perform another action with the file or provide some other service. An application developer configures the WBA through an interface to integrate a service into the WBFMS to use the WBA advantageously without the application developer having to alter an application programmer interface API of the WBA.

An application programming interface API may be defined as a set of instructions programmable to cause a WBA to respond to one or more commands. An application or an individual may provide commands in accordance with the API to cause the WBA to perform an action.

To send a file includes at least one of the following and may include a combination of the following send a copy of a file send an indirection link or pointer to the file send information about the file or send a part or parts of the file.

In the example of the user may be an individual or machine acting on behalf of an individual having access to the internet through a computing device. As an individual the user may use an internet browser window such as Internet Explorer or Mozilla Firefox to access the internet.

In the example of the WBFMS may provide online storage where users of the WBFMS can store their files. The WBFMS may also provide for file sharing and collaboration among users as well as application services provided locally. The WBFMS may include any computer readable medium capable of storing data. The WBFMS may provide a user interface through which users can access and manage files stored on the WBFMS .

In the example of the integration engine includes a processor executing instructions operable to provide commands to a WBA . The integration engine may include an interface for configuring one application to work with the other.

In the example of the WBA may be software providing services to users through the internet. These services may in a non limiting example include modifying or viewing a file or sending it via fax.

In the example of the developer s may be an individual organization or machine acting on behalf of an individual or organization involved in the development process of an application. The developer s may have knowledge of the API of the application.

The user may access the WBFMS via a computing device connected to the internet. The WBFMS may provide online storage wherein users can store files. The user may then upload files to the WBFMS or view files already stored on the WBFMS . Files stored on the WBFMS may be used with the WBA via an integration engine . The developer s are connected to the WBA and to the integration engine . The developer s may configure the integration engine such that the WBA can integrate with the WBFMS without having to change the API of the service provided by the WBA . Integration will be discussed in further detail below however as a limited introduction such configuration typically includes transmitting commands to the integration engine for the integration engine to provide to the WBA along with a file. Upon a request from the user of the WBFMS the integration engine sends the requested file along with a command structure of the API of the WBA to the WBA .

In the example of the flowchart starts at module with providing a web based file management system which provides users web based file management services. These services may include storing files and providing access to these files to users of the WBFMS.

In the example of the flowchart continues to module with providing the user of the web based file management system access to a plurality of web based applications each web based application having a specific API. These WBAs may be used on files stored on the WBFMS and may in a non limiting example include modifying or viewing the file.

In the example of the flowchart continues to module with providing an integration engine configurable for the web based application the integration engine providing a file from the file management system and one or more commands prepared using one or more well defined parameters.

In the example of the flowchart continues to module with providing a web based interface for configuring the integration engine by a developer entering values for the set of well defined parameters. Having provided a web based interface the flowchart terminates.

In the example of WBFMS includes service information action information and configuration interface .

In the example of the service information may include but is not limited to any combination of the following the name of the service a description email contact information for support a URL to the service description page access control parameters one or more pictures identifying the service and an API key.

The API key is generated by the WBFMS and is used for all actions of the WBA that access the API of the WBFMS . In a non limiting example the WBA can perform the following functions using the API of the WBFMS store and retrieve files from the WBFMS organize files into folders move rename or delete files and share files.

The access control parameters may define whether the service defined by the service information is visible to all users of the WBFMS e.g. via a user searchable service directory or whether it is only accessible to users that know the URL of the service description page.

In the example of the action information may include but is not limited to any combination of the following a name of the action a description a list of supported file extensions permission information a command language a command address a command response address one or more commands and a security parameter.

The permission information defines the availability of an action for shared files on the WBFMS . The command language may be specified and is the computer language in which the command of the API is transmitted from one program to another. The security parameters determine whether or not access authentication is required to access the WBA .

In the example of the configuration interface may be a web interface such as an extensible hypertext markup language XHTML hypertext markup language HTML form wherein data can be entered.

In the example of the application developer may be an individual organization or machine acting on behalf of an individual or organization involved in the development process of an application.

In the example of the WBA may be a computing device executing instructions to provide services to users through the internet. These services may in a non limiting example include modifying or viewing an image file or sending a file by fax.

In the example of the service information may be provided by the application developer through the configuration interface . This information may be stored on a server of the WBFMS . The application developer may use the configuration interface to provide the action information . This information is then stored on the WBFMS . To enable the WBA to accept data from the WBFMS the developer may use the configuration interface to define the commands that are sent and received to and from the WBFMS .

In the example of the flowchart starts at module with requesting action information used to enable the web based file management system to interact with the web based application. The WBFMS may send this request to a developer of a WBA wishing to set up a service of the WBA for users of the WBFMS.

In the example of the flowchart continues to module with receiving the action information to be performed on one or more files in response to the request. The developer of the WBA may provide the action information which may then be sent to the WBFMS.

In the example of the flowchart continues to module with creating an action incorporating the action information. This information may then be stored on the WBFMS. Having created the action the flowchart terminates.

In the example of web based file management system includes command structure file and interface . In the example of web based application includes command address command response address API and action .

In the example of the command structure may include code lines in the language of the API of the web based application . The code lines can that provides the functionality described by the API .

In the example of the file may be a sequence of binary digits that can be read by a computer program and can in a non limiting example be presented to a user as for example text an image a presentation or another known or convenient item.

In the example of the interface is a device that provides communication between information processing systems. The interface may send data to an information processing system and receive data from the information processing system.

In the example of the API is an interface enabling computer programs to interact between each other. The API may send commands to instruct a computer program to perform an action on a file.

In the example of the action may include a computer program acting on a file. In a non limiting example this may include modifying or displaying the file or sending the file to another computer program.

Upon request of a user of the WBFMS the WBFMS sends a file along with a command structure to the WBA through the interface . The specific location where the file and command structure are sent is given by the command address and the file and command structure are then forwarded to the API . The action is then applied to the file using the API of the WBA in accordance with the command structure . The file may be sent back to the WBFMS through the command response address and stored on the WBFMS . The user of the WBFMS may choose to either overwrite the original file when the modified file is received or create a new file which may be stored on the WBFMS . The WBFMS may impose constraints on the write privileges of the user on the files.

In the example of the flowchart continues to module with determining whether a response address is specified. The response address can be specified by a developer of a WBA and can determine how the file is sent back to the WBFMS.

If the decision at module is yes then the flowchart continues to module with determining whether to receive or to retrieve The WBA may be set up to send the file back to the WBFMS upon completion of the requested action on the file. If the WBA is set up to make the file available for download upon completion of the action on the file the WBFMS may retrieve it from the WBA.

If the decision at module is receive then the flowchart continues to module with waiting to receive file. The WBFMS waits until the file has been transmitted from the WBA.

In the example of the flowchart continues to module with storing the file. The file may be stored by the WBFMS on any computer readable medium capable of storing data.

If the decision at module is retrieve then the flowchart continues to module with waiting for notification of completion from the WBA.

In the example of the flowchart continues to module with retrieving the file from the WBA. The WBFMS may retrieve the file from the specified response address.

In the example of the flowchart continues to module with storing the file. Having stored the file on the WBFMS the flowchart terminates.

In the example of the user may be an individual or machine acting on behalf of an individual having access to the internet through a computing device. The user may use an internet browser window such as Internet Explorer available from Microsoft Corporation of Redmond Wash. or Firefox available from Mozilla Corporation of Mountain View Calif. to access the internet.

In the example of the configuration interface may be a web interface with an XHTML HTML form wherein data can be entered.

In the example of the service may include information on how the service will act on files. The service may include more than one option to modify or display files.

In the example of the action may include a computer program acting on a file. In a non limiting example this may include modifying or displaying the file or sending the file to another computer program.

In the example of the file may be a sequence of binary digits that can be read by a computer program and can in a non limiting example be presented to a user as text image or PowerPoint presentation.

In the example of the interface may include a website allowing the user to access files stored on the WBFMS. The user may be given the option to use the action determined by the service on the file .

In the example of the user may select a service and may receive a file without the action being requested by the user . An example of this would be a web based fax service uploading received faxes to the WBFMS.

In the example of the flowchart starts at module with presenting a file including an option to perform an action on the file with a WBA. The file may be graphically displayed to a user via for example a web browser. The option to perform the action could be graphically represented as a clickable selectable or otherwise chosen.

In the example of the flowchart continues to module with transmitting the file along with a set of commands specified by the action for the performance of the action on the file. The commands instruct an API of a WBA to perform an action on the file. Having transmitted the file along with a set of commands the flowchart terminates.

The device interfaces to external systems through the communications interface which may include a modem or network interface. It will be appreciated that the communications interface can be considered to be part of the system or a part of the device . The communications interface can be an analog modem ISDN modem or terminal adapter cable modem token ring IEEE 802.5 interface Ethernet IEEE 802.3 interface wireless 802.11 interface satellite transmission interface e.g. direct PC WiMAX IEEE 802.16 interface Bluetooth interface cellular mobile phone interface third generation 3G mobile phone interface code division multiple access CDMA interface Evolution Data Optimized EVDO interface general packet radio service GPRS interface Enhanced GPRS EDGE EGPRS High Speed Downlink Packet Access HSPDA interface or other interfaces for coupling a computer system to other computer systems.

The processor may be for example a conventional microprocessor such as an Intel Pentium microprocessor or Motorola power PC microprocessor. The memory is coupled to the processor by a bus . The memory can be Dynamic Random Access Memory DRAM and can also include Static RAM SRAM . The bus couples the processor to the memory also to the non volatile storage and to the display controller .

The display controller may control in the conventional manner a display on the display device which can be for example a cathode ray tube CRT or liquid crystal display LCD . The display controller can be implemented with conventional well known technology.

The non volatile storage is often a magnetic hard disk flash memory an optical disk or another form of storage for large amounts of data. Some of this data is often written by a direct memory access process into memory during execution of software in the device . One of skill in the art will immediately recognize that the terms machine readable medium or computer readable medium includes any type of storage device that is accessible by the processor .

Clock can be any kind of oscillating circuit creating an electrical signal with a precise frequency. In a non limiting example clock could be a crystal oscillator using the mechanical resonance of vibrating crystal to generate the electrical signal.

The system is one example of many possible computer systems which have different architectures. For example personal computers based on an Intel microprocessor often have multiple buses one of which can be an I O bus for the peripherals and one that directly connects the processor and the memory often referred to as a memory bus . The buses are connected together through bridge components that perform any necessary translation due to differing bus protocols.

Network computers are another type of computer system that can be used in conjunction with the teachings provided herein. Network computers do not usually include a hard disk or other mass storage and the executable programs are loaded from a network connection into the memory for execution by the processor . A Web TV system which is known in the art is also considered to be a computer system but it may lack some of the features shown in such as certain input or output devices. A typical computer system will usually include at least a processor memory and a bus coupling the memory to the processor.

In addition the system is controlled by operating system software which includes a file management system such as a disk operating system which is part of the operating system software. One example of operating system software with its associated file management system software is the family of operating systems known as Windows from Microsoft Corporation of Redmond Wash. and their associated file management systems. Another example of operating system software with its associated file management system software is the Linux operating system and its associated file management system. The file management system is typically stored in the non volatile storage and causes the processor to execute the various acts required by the operating system to input and output data and to store data in memory including storing files on the non volatile storage .

In the example of the WBFMS provides a web form wherein the developer may enter values for well defined parameters to create a service. Upon approval of the WBFMS the service is made available to users of the WBFMS and may be used with files stored on the WBFMS.

In the example of the parameters may include general information wherein the information provided by the developer may include the name of the service a description of the service an email address for support a URL to a detailed description of the service and an option to display the service in a public directory.

In the example of the parameters may include the option to upload images and screenshots defining the service.

In the example of the parameters may include the option to grant rights to other developers to edit the service.

In the example of the parameters may include the option to create an action associated with the service.

In the example of the parameters may include general information about the action including the name of action a description of action a list of extensions of supported files permission information defining the availability of an action for shared files on the WBFMS the category the action falls in and status information defining whether the action is visible to e.g. in a user searchable service directory and executable by the users of the WBFMS.

In the example of the parameters may include prompt parameters which define what is shown to the user when the user applies an action to a file stored on the WBFMS. These parameters may include a string a password prompt a text area a radio button and a drop down menu or any combination of the above.

In the example of the developer may configure callback options. These options may include an option to run the service in a new window the language in which the WBFMS communicates with the WBA a URL to the command address and a URL to the command response address.

In the example of the developer may define the parameters for the commands that are sent from the WBFMS to the WBA.

In the example of the developer may choose to require authentication from the user of the WBFMS when the action is requested by the user.

Some portions of the detailed description are presented in terms of algorithms and symbolic representations of operations on data bits within a computer memory. These algorithmic descriptions and representations are the means used by those skilled in the data processing arts to most effectively convey the substance of their work to others skilled in the art. An algorithm is here and generally conceived to be a self consistent sequence of operations leading to a desired result. The operations are those requiring physical manipulations of physical quantities. Usually though not necessarily these quantities take the form of electrical or magnetic signals capable of being stored transferred combined compared and otherwise manipulated. It has proven convenient at times principally for reasons of common usage to refer to these signals as bits values elements symbols characters terms numbers or the like.

It should be borne in mind however that all of these and similar terms are to be associated with the appropriate physical quantities and are merely convenient labels applied to these quantities. Unless specifically stated otherwise as apparent from the following discussion it is Appreciated that throughout the description discussions utilizing terms such as processing or computing or calculating or determining or displaying or the like refer to the action and processes of a computer system or similar electronic computing device that manipulates and transforms data represented as physical electronic quantities within the computer system s registers and memories into other data similarly represented as physical quantities within the computer system memories or registers or other such information storage transmission or display devices.

The present example also relates to apparatus for performing the operations herein. This Apparatus may be specially constructed for the required purposes or it may comprise a general purpose computer selectively activated or reconfigured by a computer program stored in the computer. Such a computer program may be stored in a computer readable storage medium such as but is not limited to read only memories ROMs random access memories RAMs EPROMs EEPROMs flash memory magnetic or optical cards any type of disk including floppy disks optical disks CD ROMs and magnetic optical disks or any type of media suitable for storing electronic instructions and each coupled to a computer system bus.

The algorithms and displays presented herein are not inherently related to any particular computer or other Apparatus. Various general purpose systems may be used with programs in accordance with the teachings herein or it may prove convenient to construct more specialized Apparatus to perform the required method steps. The required structure for a variety of these systems will appear from the description below. In addition the present example is not described with reference to any particular programming language and various examples may thus be implemented using a variety of programming languages.

