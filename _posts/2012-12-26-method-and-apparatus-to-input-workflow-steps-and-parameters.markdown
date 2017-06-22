---

title: Method and apparatus to input workflow steps and parameters
abstract: An image forming method and apparatus, and a host in which the image forming method includes setting a processing order of a plurality of operations of a same image data and detailed setup information of the plurality of operations, and executing the plurality of operations using the detailed setup information according to the set processing order.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09525788&OS=09525788&RS=09525788
owner: SAMSUNG ELECTRONICS CO., LTD.
number: 09525788
owner_city: Suwon-Si
owner_country: KR
publication_date: 20121226
---
This is a Divisional application of prior U.S. application Ser. No. 12 054 550 filed on Mar. 25 2008 in the U.S. Patent and Trademark Office which claims priority under 35 U.S.C. 119 a from Korean Patent Application No. 10 2007 0063813 filed on Jun. 27 2007 and Korean Patent Application No. 10 2007 0069356 filed on Jul. 10 2007 in the Korean Intellectual Property Office the disclosures of which are incorporated herein in their entirety by reference.

The present general inventive concept relates to an image forming apparatus and more particularly to image forming method and apparatus to allow a user to check progress states of a plurality of operations on a screen by using a user interface to dynamically create the plurality of operations and to determine setup information according to the user s intentions. The present general inventive concept also relates to an image forming method and apparatus and a host to allow a user to newly generate a desired application to execute operations.

Conventionally a user can select one of selectable operations e.g. copying scanning faxing printing etc. through a user interface of an image forming apparatus. If the user selects one operation the user can set only detailed setup information corresponding to the selected operation on the user interface. Thus when the user desires to e mail print and fax copied data the user cannot continuously execute such operations. Also if the user does not fully know about a multi functional peripheral MFP having multi functions the user cannot easily use the multi functions of the MFP due to complexity of the MFP.

Also when products such as printers or MFPs come out usable software functions are realized as firmware. Thus if products are sold functions of software of the products cannot be changed or added. In order to solve this problem open architectures have been developed in the MFP industry so as to add new functions or select and mount only software necessary for each user. Examples of the open architectures include an OSGi based architecture by Ricoh a java based Multifunctional Embedded Application Platform MEAP by Canon javascript based JScribe architecture by IBM etc. However open architectures of image forming apparatuses such as MFPs etc. which have recently been developed and come out to open objects application programming interfaces APIs of MFP platforms according to specifications developed by manufacturing companies and provide an integrated development environment IDE for developing new functions using the open objects APIs. Accordingly solution developers can develop solutions set to be suitable for additional functions of software and specific use environments and mount the solutions in products. This technology must be further developed. However for substantial development of this technology a large amount of time is required to thoroughly learn about object API specifications open to corresponding products and a method of using IDE. Also users not knowing about the technology cannot slightly change functions or realize desired functions. That is conventional open architecture technology can be used by only developers and not by general users.

The present general inventive concept provides an image forming method and apparatus to easily set and to continuously execute a plurality of operations of a same set of image data on a screen.

The present general inventive concept also provides an image forming method and apparatus and a host to allow a user to newly generate an application to execute operations according to settings of the user.

Additional aspects and utilities of the present general inventive concept will be set forth in part in the description which follows and in part will be obvious from the description or may be learned by practice of the general inventive concept.

The foregoing and or other aspects and utilities of the general inventive concept may be achieved by providing an image forming method including setting a processing order of a plurality of operations of a same image data and detailed setup information of the plurality of operations and executing the plurality of operations using the detailed setup information according to the set processing order.

The foregoing and or other aspects and utilities of the general inventive concept may also be achieved by providing an image forming apparatus including a user interface unit to set a processing order of a plurality of operations of a same image data and detailed setup information of the plurality of operations and a controller to control the plurality of operations to be executed using the detailed setup information according to the processing order.

The foregoing and or other aspects and utilities of the general inventive concept may also be achieved by providing an image forming method including generating a graphical user interface GUI webpage corresponding to a plurality of operations on an image forming apparatus generating an application profile corresponding to the plurality of operations using the GUI webpage and generating an application corresponding to the application profile to execute the plurality of operations on the image forming apparatus.

The foregoing and or other aspects and utilities of the general inventive concept may also be achieved by providing an image forming apparatus including an operation registration manager to register and manage information including types detailed setup information and execution information of a plurality of operations an internal web server to generate a graphical user interface GUI webpage corresponding to the plurality of operations and an operation executer to receive an application profile from a host to generate the application profile corresponding to the plurality of operations using the GUI webpage to generate an application corresponding to the application profile and to execute the plurality of operations.

The foregoing and or other aspects and utilities of the general inventive concept may also be achieved by providing a host including a generator to generate an application profile corresponding to a plurality of operations using a graphical user interface GUI webpage wherein the GUI webpage corresponds to the plurality of operations of an image forming apparatus.

The foregoing and or other aspects and utilities of the general inventive concept may also be achieved by providing an image forming apparatus including a user interface to allow a user to select a plurality of image forming operations to be performed on a same image data and to set a processing order of the selected image forming operations and a controller to process the selected image forming operations corresponding to at least the set processing order wherein the set plurality of image forming operations are continuously processed.

The selecting of the plurality of image forming operations may include selecting icons corresponding to the respective image forming operations.

The setting of the processing order includes arranging the selected icons corresponding to the respective image forming operations in an order.

The user interface may include a setup window to allow the user to set detailed setup information corresponding to the plurality of image forming operations wherein the controller processes the selected image forming operations corresponding to the respective detailed setup information.

The detailed setup information may include one or more of a size of a printing medium a number of printed pages and a resolution.

The plurality of image forming operations may include one or more of a copying operation a printing operation a faxing operation and a scanning operation.

The user interface may display icons corresponding to image forming operations in response to an arbitrary operation.

The user interface may not display non selected icons in response to a selection of an icon corresponding to a respective image forming operation.

The foregoing and or other aspects and utilities of the general inventive concept may also be achieved by providing a method of performing image forming operations with an image forming apparatus the method including selecting a plurality of image forming operations to be performed on a same image data setting a processing order of the selected image forming operations and processing the selected image forming operations corresponding to at least the set processing order such that the set plurality of image forming operations are continuously processed.

The method may further include setting detailed setup information corresponding to the plurality of image forming operations.

The processing of the selected image forming operations may further include processing the selected image forming operations corresponding to the respective detailed setup information.

Reference will now be made in detail to the embodiments of the present general inventive concept examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to the like elements throughout. The embodiments are described below in order to explain the present general inventive concept by referring to the figures.

In operation a processing order and detailed setup information of a plurality of operations of a same image data are set. The processing order refers to an order in which a plurality of image forming operations are continuously processed e.g. copying printing faxing scanning etc. The detailed setup information refers to information which is set to execute the plurality of image forming operations e.g. information regarding a size of a printing paper sheet a number of printed pages resolution etc. which are set for the printing operation.

The present general inventive concept uses the processing order and the detailed setup information to continuously execute the plurality of image forming operations of the same image data.

In particular in the present embodiment icons indicating the plurality of image forming operations are arranged on a user interface screen to set the processing order and the detailed setup information corresponding to each of the plurality of consecutive image forming operations is set. Processes of setting the processing order and detailed setup information will be described with reference to .

After the icons indicating the operations are arranged detailed setup information corresponding to the operations is set. The detailed setup information is set according to detailed setup information input through a setup window. An ID indicates detailed setup information for a scanning operation and an ID indicates a setup window to set detailed setup information using a drop down method. The detailed setup information of the scanning operation may be information regarding whether results of the scanning operation are to be transmitted to a host or transmitted through an e mail resolution a size of a printing paper sheet reports etc.

In the present general inventive concept icons indicating executable operations are displayed after an arbitrary operation and an operation processing order corresponding to an icon selected from the displayed icons is set. Also only the selected icon of the icons indicating the executable operations is displayed after an arbitrary operation and displays of the other icons are removed.

If the user desires to arrange an icon of a non executable operation on a user interface screen together with icons indicating a plurality of operations the user may not arrange the icon on the user interface screen but may display an error message. Thus the user can check on the display whether an error message that an operation corresponding to an icon selected by the user cannot be executed.

In operation the plurality of operations are executed according to the processing order using the detailed setup information. That is the corresponding operations are continuously executed using the processing order and the detailed setup information determined in operation . For example if the processing order is set to the order of a scanning operation a printing operation and fax forwarding as illustrated in the plurality of operations of the same image data are sequentially executed with reference to the set detailed setup information of each of the plurality of operations.

In operation the processing order and the detailed setup information are stored. That is information regarding the operation processing order and detailed setup information created by a user can be stored so as to be re used later. In the present embodiment the operation processing order and detailed setup information are stored after operations are completely executed. However the operation processing order and the detailed setup information may be stored during the executions of the operations.

The image forming method of operates during executions of operations or on standby for the operations. That is the operation processing order and the detailed setup information may be set to continuously execute additional operations even during the executions of the respective operations.

An image forming apparatus according to the present general inventive concept will now be described in detail with reference to the attached drawings.

The user interface unit sets the processing order and detailed setup information of a plurality of operations of the same image data and outputs set results to the controller . For this purpose the user interface unit includes a screen provider an operation processing order setter and a detailed information setter .

The screen provider provides a user interface screen to set the processing order. The ID illustrated in indicates such a user interface screen. The screen provider displays the user interface screen on which icons indicating the plurality of operations are arranged.

The operation processing order setter arranges the icons indicating the plurality of operations on the user interface screen to set the processing order and outputs the set results to the controller . The operation processing order setter arranges icons indicating a plurality of image forming operations on the user interface screen using a drag and drop method.

The operation processing order setter displays icons indicating executable operations after an arbitrary operation on the user interface screen and sets an operation processing order corresponding to an icon selected from the displayed icons. The operation processing order setter also displays only the selected icon and removes displays of the other icons.

The operation processing order setter displays an icon indicating a scanning operation and then an icon indicating a printing operation on the user interface screen as illustrated in . The operation processing order setter also displays icons corresponding to operations to be executed after the printing operation as illustrated in . A user can select one of icons of report printing fax forwarding and data storing. If the user selects fax forwarding the operation processing order setter displays only the icon of fax forwarding and removes the icons of report printing and data storing. That is if fax forwarding is selected as an operation to be executed after the printing operation the other icons disappear as illustrated in .

If the user desires to arrange non executable operations together with icons indicating the plurality of operations on the user interface screen the operation processing order setter displays an error message instead of icons of the non executable operations. The user can check through the display of the error message that an operation corresponding to an icon selected by the user is non executable.

The detailed information setter sets the detailed setup information of the plurality of operations and outputs the set results to the controller . The detailed information setter sets the detailed setup information according to detailed setup information input through a setup window using a drag and drop method. If the operation processing order setter arranges an icon indicating an operation on the user interface screen the detailed information setter sets detailed setup information corresponding to the arranged icon of the operation. The detailed information setter displays the setup window using the drag and drop method and sets information input through the setup window as detailed setup information.

The controller controls the plurality of operations to be continuously executed using the processing order set by the operation processing order setter and the detailed setup information set by the detailed information setter . For example if the processing order are set to the order of a scanning operation a printing operation and fax forwarding as illustrated in the controller sequentially executes the scanning operation the printing operation and fax forwarding of the same image data with reference to detailed setup information set for the scanning operation the printing operation and fax forwarding. The controller also controls the memory to store the set processing order and detailed setup information.

The memory is a non volatile memory and is controlled by the controller to store the processing order and the detailed setup information.

The above described image forming apparatus operates during executions of operations or on standby for the operations. Even when the operations are being executed the image forming apparatus can set the operation processing order and detailed setup information to continuously execute additional operations. When the operations are on standby the image forming apparatus can execute a plurality of operations.

An image forming method according to another embodiment of the present general inventive concept will now be described with reference to the drawings.

In operation a graphic user interface GUI webpage corresponding to a plurality of operations is generated on an image forming apparatus. Here the plurality of operations may be referred to as objects indicating functions of the image forming apparatus. The objects indicate the abstracted functions of the image forming apparatus and examples of the objects include objects Print Scan Fax Image Ftp client E mail etc.

In operation information including types detailed setup information and execution information of the operations is registered. When a power source is applied to the image forming apparatus the types of operations i.e. types of objects are registered together with detailed setup information and operation execution information regarding the objects. The registered information is managed as a database.

Examples of the types of operations include print scanner fax image protocol filter operations etc. The types of operations indicate what types of functions operations are in charge of. The detailed setup information indicates attributes or set information of the operations i.e. indicates the resolution in the scanner object an ftp server IP address in the ftp client object etc. The operation execution information indicates function information to be executed by a corresponding operation e.g. Start scanning Stop scanning etc. in the object Scan Log in a ftp server Start ftp transmission etc. in the object Ftp client. 

In operation the GUI webpage including a list menu of image forming operations and an edition menu of an application is generated using the registered information.

In operation an application profile corresponding to operations is generated on a host using the generated GUI webpage.

In operation the host receives the generated GUI webpage from the image forming apparatus. The received GUI is displayed on the web browser.

In operation the processing order and detailed setup information of the image forming operations are set using the list menu of the image forming operations and the edition menu of the application wherein the list and edition menus are included in the received GUI webpage. The list menu arranges and displays icons corresponding to operations i.e. objects according to the predetermined order. The edition menu of the application performs a function of setting the operation processing order and a function of generating an application profile corresponding to the operation processing order. The edition menu of the application is used to move the icons corresponding to the operations on the list menu onto the edition menu using a drag and drop method and to provide a user interface on which connection relations among the icons are created to set the operation processing order of the icons. The edition menu of the application is also used to generate the application profile corresponding to the set operation processing order.

An example of a GUI webpage displayed on a web browser is illustrated in . A user moves the icons corresponding to the operations on the list menu onto the edition menu using the drag and drop method and then creates the connection relations among the icons to set the operation processing order of the icons. For example if the user creates the connection relations among the icons as illustrated in the operation processing order of first and second objects are set. Also detailed setup information of the first and second objects is also set using the edition menu of the application.

In operation the application profile corresponding to the set operation processing order and detailed setup information is generated. The edition menu of the application generates a new application profile using the operation processing order and detailed setup information displayed on a screen. The application profile may be generated in an Extensible Markup Language XML format or a predetermined script format. The application profile includes information regarding types detailed information and the set processing order of operations.

In operation the application profile is interpreted on the image forming apparatus to execute image forming operations corresponding to the operation processing order.

In operation the image forming apparatus receives and stores the application profile generated by the host.

In operation the stored application profile is interpreted. Here the application profile is interpreted according to pre defined rules.

In operation an application corresponding to contents of the interpreted application profile is generated.

In operation the generated application is executed so as to execute operations. Detailed setup information of the operations may be changed according to contents of the interpreted application profile.

As described above an application profile created through a GUI webpage is transmitted to an image forming apparatus. The image forming apparatus interprets the application profile to generate an application to substantially perform a function of the application profile so as to execute operations according to the setting of a user.

An image forming apparatus and a host according to the present general inventive concept will now be described in detail with reference to the attached drawings.

The operation registration manager registers and manages information including types detailed setup information and execution information of a plurality of operations. As illustrated in the operation registration manager creates a database DB of a type detailed setup information and execution information of each of the plurality of operations stores and manages the DB and provides the DB to the internal web server . The operations indicate objects which indicate functions of the image forming apparatus . The types of the plurality of operations indicate what types of functions the operations are in charge of. The detailed setup information indicates attributes and set information of the operations and the execution information is function information which can be executed by corresponding operations.

The internal web server generates the GUI webpage corresponding to the operations and transmits the GUI webpage to a host . For this purpose the internal web server includes an icon information storage unit a GUI webpage generator and a first interface unit .

The icon information storage unit stores icon information corresponding to the operations and outputs the icon information to the GUI webpage generator .

The GUI webpage generator generates the GUI webpage using the registered information of the operations provided from the operation registration manager and outputs the generated GUI webpage to the first interface unit . The GUI webpage includes a list menu of the operations and an edition menu of an application corresponding to the processing order of the operations. The list menu arranges and displays icons indicating symbols of the operations i.e. objects according to the predetermined order. The edition menu of the application executes a function of setting the processing order and a function of generating an application profile corresponding to the processing order.

The host generates the application profile corresponding to the processing order of the operations using the GUI webpage corresponding to the operations of the image forming apparatus . For this purpose the host includes a second interface unit a setter and a profile generator .

The second interface unit logs in the image forming apparatus to receive the GUI webpage from the image forming apparatus and outputs the GUI webpage to the setter .

The setter sets the processing order and detailed setup information of the operations using the list menu of the operations and the edition menu of the application wherein the list and edition menus are in the GUI webpage and outputs the processing order and the detailed setup information to the profile generator .

The setter moves the icons corresponding to the symbols of the operations on the list menu onto the edition menu using a drag and drop method and then provides a user interface so as to set the processing order and the detailed setup information. The processing order and the detailed setup information are set using the list menu and the edition menu as illustrated in .

The profile generator generates the application profile corresponding to the processing order and the detailed setup information set by the setter and outputs the application profile to the second interface unit . The application profile includes information regarding types detailed setup information and the processing order of the operations. The profile generator may generate the application profile using an XML format or a predetermined script format.

The first interface unit receives the application profile generated by the host and outputs the application profile to the operation executer .

The operation executer interprets the application profile so as to execute image forming operations corresponding to the processing order. For this purpose the operation executer includes a profile storage unit a profile interpreter an application generator and an application executer .

The profile storage unit receives the application profile from the first interface unit stores the application profile and outputs the application profile to the profile interpreter .

The profile interpreter interprets the application profile provided from the profile storage unit and outputs contents of the interpreted application profile to the application generator and the operation registration manager .

The application generator generates an application corresponding to the contents of the interpreted application profile and outputs the generated application to the application executer .

The operation registration manager changes the detailed setup information of the operations according to the contents of the interpreted application profile.

As described above in an image forming method and apparatus and a host according to various embodiments of the present general inventive concept a user can execute a plurality of image forming operations with a one time action and simply perform setting of each of the plurality of image forming operations. Thus if the user is to scan fax and e mail a photograph and store the photograph in a storage medium of a multi functional peripheral MFP without repeating operations of the same image data the user can create image forming operations in the order of scanning faxing e mailing and storing so as to continuously execute the image forming operations without additional repeated operations.

Also the user can provide an execution list of next executable functions to easily use convenient functions of the image forming apparatus top perform various functions.

In addition if operations to be executed are non executable the user can select other executable operations or cancel the non executable operations.

Moreover the user can newly generate an application to execute desired operations. Thus even if the user is not very knowledgeable about a management program of the functions of the image forming apparatus the user can add and change the functions of the image forming apparatus.

The present general inventive concept can also be embodied as computer readable codes on a computer readable medium. The computer readable medium can include a computer readable recording medium and a computer readable transmission medium. The computer readable recording medium is any data storage device that can store data that can be thereafter read by a computer system. Examples of the computer readable recording medium include read only memory ROM random access memory RAM CD ROMs magnetic tapes floppy disks and optical data storage devices. The computer readable recording medium can also be distributed over network coupled computer systems so that the computer readable code is stored and executed in a distributed fashion. The computer readable transmission medium can transmit carrier waves or signals e.g. wired or wireless data transmission through the Internet . Also functional programs codes and code segments to accomplish the present general inventive concept can be easily construed by programmers skilled in the art to which the present general inventive concept pertains.

Although various embodiments of the present general inventive concept have been illustrated and described it will be appreciated by those skilled in the art that changes may be made in these embodiments without departing from the principles and spirit of the general inventive concept the scope of which is defined in the appended claims and their equivalents.

