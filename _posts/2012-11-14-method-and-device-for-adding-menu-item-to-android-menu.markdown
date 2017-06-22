---

title: Method and device for adding menu item to android menu
abstract: A method and device for adding a menu item to an Android menu are provided. The method includes: receiving a request for opening a local menu, where the request carries a menu ID, and creating a local menu corresponding to the menu ID; obtaining according to the menu ID, in a stored correspondence between a menu item of a third-party application and the menu ID, a menu item of a corresponding third-party application; and adding the menu item of the third-party application to the local menu, and displaying the local menu to which the menu item of the third-party application is added. The device includes a first creating module, an obtaining module, and an adding module. The present invention is capable of adding a menu item of a third-party application to a local menu of a mobile phone without modifying an Android platform code.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09319508&OS=09319508&RS=09319508
owner: Huawei Device Co., Ltd.
number: 09319508
owner_city: Shenzhen
owner_country: CN
publication_date: 20121114
---
This application is a continuation of International Application No. PCT CN2011 073864 filed on May 10 2011 which claims priority to Chinese Patent Application No. 201010176312.X filed on May 14 2010 both of which are hereby incorporated by reference in their entireties.

The present invention relates to the computer field and in particular to a method and device for adding a menu item to an Android menu.

Android is a software platform and operating system based on the Linux kernel. Android provides multiple functions and multiple local menus where each local menu includes one or multiple menu items and each menu item corresponds to a function so that each function may be started from the local menus. Android may be used as a mobile operating system. A mobile phone manufacturer adds various third party applications to the Android platform to develop mobile phones with different functions. Each third party application includes one or multiple functions and each function corresponds to one menu item. The menu item corresponding to each function of a third party application is added to a local menu so that the functions included in the third party application may be started from the local menu.

The Android platform has a database for storing menu items. A mobile phone manufacturer adds a menu item included in a third party application to the database by modifying a code in the Android platform. When a local menu is created menu items are obtained from the database to make a local menu thereby adding the menu item included in the third party application to the local menu. Then the mobile phone manufacturer burns the Android platform and the third party application into the memory of the mobile phones.

When a mobile phone manufacturer adds a menu item of a third party application to a local menu the mobile phone manufacturer needs to modify an Android code. In addition after a mobile phone is delivered from a factory data burned into the mobile phone memory cannot be modified again. Therefore when downloading a third party application to the mobile phone the user cannot add a menu item in the third party application to the local menu of the mobile phone.

To add a menu item of a third party application to a local menu of a mobile phone without modifying an Android platform code embodiments of the present invention provide a method and device for adding a menu item to an Android menu. The technical solutions are as follows 

receiving a request for opening a local menu where the request carries a menu ID and creating a local menu corresponding to the menu ID 

obtaining according to the menu ID in a stored correspondence between a menu item of a third party application and a local menu ID a menu item of a corresponding third party application 

a first creating module configured to receive a request for opening a local menu where the request carries a menu ID and create a local menu corresponding to the menu ID 

an obtaining module configured to obtain according to the menu ID in a stored correspondence between the menu item of a third party application and a local menu ID a menu item of a corresponding third party application and

an adding module configured to add the menu item of the third party application to the local menu and display the local menu to which the menu item of the third party application is added.

When a local menu is opened a menu item to be added to the local menu is obtained from a stored correspondence between a menu item of a third party application and a local menu ID and the obtained menu item is directly added to the local menu. The menu item of the third party application is directly added to the local menu therefore without modifying an Android code the menu item of the third party application may be added to the database of an Android platform and the menu item of the third party application may be added to the local menu.

To make the objective technical solutions and advantages of the present invention clearer the following describes the present invention in detail with reference to embodiments and accompanying drawings. The illustrative embodiments of the present invention and description thereof are used to describe the present invention and are not intended to limit the present invention.

As shown in an embodiment of the present invention provides a method for adding a menu item to an Android menu including 

Step Receive a request for opening a local menu where the request carries a menu ID and create a local menu corresponding to the carried menu ID.

Step Obtain according to the carried menu ID in a stored correspondence between a menu item of a third party application and the local menu ID a menu item of a corresponding third party application.

Step Add the obtained menu item of the third party application to the local menu and display the local menu to which the menu item of the third party application is added.

In the embodiment of the present invention a menu item of a third party application and an ID of a local menu to which the menu item belongs are stored when the local menu is opened the menu item to be added to the local menu is obtained according to a stored correspondence between the menu item of the third party application and the local menu ID and the obtained menu item is directly added to the local menu. The menu item of the third party application is directly added to the local menu therefore without modifying an Android code the menu item of the third party application may be added to the database of an Android platform and the menu item of the third party application may be added to the local menu.

As shown in an embodiment of the present invention provides a method for adding a menu item to an Android menu including 

Step When a user installs a third party application in a mobile phone search a file set of the third party application for a configuration file.

The user may download the file set of the third party application from an application developer and store the file set of the third party application in the memory of the mobile phone. The third party application may include one or multiple functions where each function is implemented by a corresponding API Application Programming Interface function. Therefore the file set of the third party application stores the API function of each function for implementing the third party application.

The file set of the third party application has a configuration file where the configuration file exists as an XML Extensible Markup Language file. The configuration file includes at least the following information a menu item and an ID of a local menu to which the menu item belongs where the menu item includes at least a menu item name and identity information and the identity information includes at least a menu ID of a secondary menu or a function ID. In addition the identity information may further include an application ID. If the identity information includes a menu ID of a secondary menu the identity information may uniquely identify a secondary menu and if the identity information includes a function ID the identity information may uniquely identify a function. In addition the menu item may further include an icon ID and the like and correspondingly the file set of the third party application further has an icon. In addition the menu item name exists in the form of a character string. The configuration file may include multiple menu items and IDs of local menus to which each menu item belongs. A third party application developer knows each local menu in an Android platform in advance. If the third party application developer wants to add a menu item of a third party application to a local menu the third party application developer may directly define in the configuration file of the third party application the local menu ID to which the menu item of the third party application belongs to be the local menu ID.

For example a third party application is a mail system. A file set of the mail system has a configuration file where the configuration file includes information shown in Table 1. As shown in Table 1 the configuration file of the mail system includes two menu items and IDs of local menus to which each menu item belongs. A first menu item includes a menu item name which is Mail and identity information which includes a function ID ID an application ID ID and an icon ID ID . A second menu item includes a menu item named DirectMessage and identity information including a function ID ID and an application ID ID . A menu item may not include an icon ID. Therefore an icon ID recorded in a last line of Table 1 is left blank.

Step Obtain by parsing a found configuration file and from the configuration file at least information such as each menu item and the menu ID of the local menu to which each menu item belongs and store the obtained information in a configuration manager.

The configuration manager is stored in an unoccupied space area in the memory of a mobile phone and the configuration manager is configured to store a correspondence between a menu item of a third party application and a menu ID of a local menu to which the menu item belongs. For example the configuration file shown in is parsed to obtain from the configuration file shown in Table 1 two menu items and IDs of the local menus to which each menu item belongs and the obtained two menu items and the IDs of the local menus to which each menu item belongs are stored in a configuration manager shown in Table 2.

When producing a mobile phone a mobile phone manufacturer normally sets multiple local applications in the mobile phone where each local application includes multiple functions and sets a corresponding local primary menu for each local application where the local primary menu includes one or multiple menu items and identity information of each menu item includes at least a function ID or a menu ID of a local secondary menu. The structure of a local secondary menu is the same as the structure of a local primary menu and each local secondary menu may also include multiple menu items. In addition the mobile phone manufacturer further sets a unique ID for identifying each local secondary menu and local primary menu. For the convenience of description the local primary menu and the local secondary menu may be collectively referred to as a local menu.

The database in an Android platform of the mobile phone stores a correspondence between a menu ID of each local menu and each menu item included in the local menu. For example a mobile phone includes local applications such as Message Address Book and Setting and each local application corresponds to a local primary menu. Table 3 shows a correspondence between a menu ID of a local primary menu corresponding to the local application Message and each menu item in the local primary menu. Each line of records in Table 3 includes a menu ID and a menu item. In Table 3 the menu item in each line of records includes a menu item name identity information and an icon ID where the identity information may include two fields namely a function ID and a secondary menu ID. The identity information in each line of the records from line 2 to line 4 includes a function ID only and the secondary menu ID is left blank. The identity information in the record in line 5 includes a secondary menu ID only and the function ID is left blank.

In Table 3 the menu item of the record in line 5 includes a secondary menu ID ID indicating that the menu item corresponds to a local secondary menu whose ID is ID . The structure of the local secondary menu is the same as that of the local primary menu which also includes multiple menu items. As shown in Table 4 the mobile phone manufacturer also sets for the local secondary menu a correspondence between a menu ID and each menu item included in the local secondary menu.

The mobile phone manufacturer stores Table 3 and Table 4 in the database of the Android platform. When producing the mobile phone the mobile phone manufacturer burns the correspondences between the menu items and the menu IDs stored in the database of the Android platform together with each local application into the memory of the mobile phone. Therefore in the memory of the mobile phone the database of the Android platform and the configuration manager are located in different storage space respectively.

On a desktop of the mobile phone the mobile phone manufacturer creates an icon for each local application and binds an icon corresponding to each local application with a menu ID of the local primary menu corresponding to the local application. A user submits a request for opening a menu by selecting an icon where the request carries the menu ID which is bound with the icon. Then the following steps to are performed to create the local primary menu corresponding to the menu ID carried in the request.

Step Receive the request for opening the menu where the request carries the menu ID and create the local primary menu corresponding to the carried menu ID.

Specifically the request for opening the menu is received a menu list is created all corresponding menu items are obtained according to the menu ID carried in the request for opening the menu in the correspondence between the menu item and the menu ID stored in the database of the Android platform the menu item name included in each menu item is filled in the created menu list and in the menu list the menu item name and the identity information in each menu item are bound and thereby the local primary menu is obtained.

Further if a menu item further includes an icon ID a corresponding icon is obtained in the memory of the mobile phone according to the icon ID and correspondingly the obtained icon together with the menu item name in the menu item is filled in the created menu list.

For example a request for opening a menu is received where a menu ID carried in the request is ID a menu list is created and in the Table 3 stored in a database of an Android platform all corresponding menu items are obtained according to the ID carried in the request. As shown in Table 5 each menu item includes an icon ID.

In a memory of the mobile phone a corresponding icon is obtained according to an icon ID in each menu item the menu item name and corresponding icon in each menu item are filled in the menu list and in the menu list the menu item name and identity information included in each menu item are bound and thereby a local primary menu shown in is obtained. For example the menu item shown in line 3 in Table 5 includes the menu item name Write Message a function ID included in the identity information and an icon ID ID . The corresponding icon is obtained according to the icon ID the menu item name Write Message in the menu item and the obtained icon are filled in the menu list and the Write Message in the menu item is bound with the function ID .

The created menu list has only one blank table and each time a menu item name is filled in the blank table another blank table is automatically created for the menu list. Therefore the menu list always has one blank table. Alternatively two or more blank tables may be retained.

Step Search the configuration manager for a corresponding menu item according to the carried menu ID where a found menu item includes at least a menu item name and identity information.

All menu items found in the configuration manager are menu items of a third party application. For example the configuration manager shown in Table 2 is searched for a corresponding menu item according to a carried ID where the found menu item includes a menu item name Mail and identity information which includes an application ID ID and a function ID ID . The menu item is a menu item of the third party application Mail System .

Specifically in the menu list of the local primary menu the menu name included in the obtained menu item is filled in an unoccupied table respectively the menu item name and identity information in the obtained menu item are bound in the local primary menu and then the local primary menu is displayed. The unoccupied table refers to the preceding blank table.

Further if the obtained menu item further includes an icon ID a corresponding icon is obtained from a file set of a third party application installed on the mobile phone and correspondingly the icon and the menu item name of the menu item are filled in the unoccupied table in the menu list of the local primary menu.

For example according to an icon ID ID the file set of the third party application installed in the mobile phone is searched for the corresponding icon and the menu item name Mail in the menu item and the found icon are filled in the menu item list the identity information in the menu item and the menu item name Mail are bound in the menu list that is the application ID and the function ID are both bound to the menu item name Mail and thereby the local primary menu shown in is obtained.

In this embodiment unoccupied space is retained in the memory of the mobile phone where the space is used to store a menu item of a third party application and an ID of the local menu to which the menu item belongs. Therefore it is not necessary to modify an Android code to store the menu item of the third party application and the ID of the local menu to which the menu item belongs in the database of Android. When a user needs to open a local primary menu a local primary menu needs to be opened by the user is created first and then a menu item of a third party application is directly added to the local primary menu and thereby the menu item of the third party application is added to the local primary menu.

Further when the user selects a menu item in the displayed local primary menu the background color of the menu item selected by the user is changed to a specific background color.

For example the local primary menu shown in may be displayed for the user. When the user selects a menu item in the local primary menu the local primary menu obtains identity information of the menu item name which is bound in the menu item. If the obtained identity information includes a function ID only the memory of the mobile phone is searched for a corresponding function according to the obtained function ID that is an API function for implementing the function is searched for and then the found function is directly invoked. If the obtained identity information includes an application ID and a function ID the memory of the mobile phone is searched for a file set corresponding to the application according to the application ID and the found file set is searched for a corresponding function according to the function ID and then the found function in invoked. If the obtained identity information includes a secondary menu ID a request for opening a menu is generated where the request carries an obtained secondary menu ID the request for opening the menu is submitted and then according to the following steps to a secondary menu is created and displayed.

Step Receive a request for opening a menu where the request carries a menu ID of a secondary menu and create a local secondary menu corresponding to the carried secondary menu ID.

Specifically the request for opening the menu is received a menu list is created all corresponding menu items are obtained according to the menu ID carried in the request for opening the menu in the correspondence between the menu item and the menu ID in the Android database of the mobile phone the menu item name included in each menu item is filled in the created menu list and in the menu list the menu item name and the identity information in each menu item are bound and thereby the local secondary menu is obtained.

Further if a menu item further includes an icon ID a corresponding icon is obtained in the memory of the mobile phone according to the icon ID and the obtained icon together with the menu item name in the menu item is filled in the created menu list.

For example in the menu list shown in after a user selects Empty a request for opening a menu is received where the request for opening the menu carries a menu ID ID a menu list is created and the Table 4 stored in the database of Android is searched for all corresponding menu items according to the carried ID as shown in Table 6.

The menu item names Inbox Outbox and Draft shown in are filled in the created menu list in the menu list Inbox and ID are bound Outbox and ID are bound and Draft and ID are bound and thereby the local secondary menu shown in is obtained. Certainly when the secondary menu is created at least one blank table may always be retained in the created menu list as described in step .

Step The configuration manager is searched for a corresponding menu item according to the carried menu ID of the secondary menu where the found menu item includes at least a menu item name and identity information.

For example a configuration manager such as the one shown in Table 2 is searched for a corresponding menu item according to the carried ID where the menu item includes a menu item name DirectMessage and identity information which includes a function ID ID and an application ID ID. 

Specifically the menu name included in the obtained menu item is filled in an unoccupied table in the menu list of the local secondary menu the menu item name and identity information in the obtained menu item are bound in the local secondary menu and then the local secondary menu is displayed.

For example the obtained menu item name DirectMessage is filled in the unoccupied table of the menu list of the local secondary menu the menu item name of the menu item and the function ID ID are bound in the local secondary menu and thereby the local secondary menu shown in is obtained and then the local secondary menu shown in is displayed.

In the embodiment when a user needs to open a local secondary menu a local secondary menu needs to be opened by the user is created first and then a menu item of a third party application is directly added to the local secondary menu and thereby the menu item of the third party application is added to the local secondary menu.

The mobile phone manufacturer sets an XSD XML Schemas Definition specification in the mobile phone where the structure of each local menu in the mobile phone is defined in an XSD specification. Further after step is performed and before step is performed the found configuration file may be verified according to the XSD specification in the mobile phone if the verification is passed step is performed otherwise the operation ends. For example assume that a local menu is defined in the XSD and no new menu item is allowed to be added but a found configuration file has a menu item to be added to the local menu when the found configuration file is being verified by using the XSD specification a result of verification failure is obtained and the operation ends.

In this embodiment in the process of adding a menu item of a third party application the code in the Android platform of a mobile phone is not modified. Therefore every local application in the mobile phone is not damaged. When the third party application needs to communicate information to the local application the third party application needs to first submit to the Android platform the information to be communicated and the Android platform receives the information to be communicated and forwards to the local application the information to be communicated.

The method provided in this embodiment is capable of adding a menu item of a third party application to a local menu in any terminal device supporting an Android platform.

In the embodiment of the present invention a menu item of a third party application and an ID of a local menu to which the menu item belongs are stored in a configuration manager. When a local menu is created the menu item of the third party application to be added to the local menu is obtained from the configuration manager and the obtained menu item is added to the local menu. The menu item of the third party application and the ID of the local menu to which the menu item belongs are stored in the configuration manager therefore the menu item of the third party application may be added to the database of Android without modifying an Android code. The menu item of the third party application is directly added to the local menu and thereby the menu item of the third party application is added to the local menu.

As shown in an embodiment of the present invention provides a device for adding a menu item to an Android menu including 

a first creating module configured to receive a request for opening a local menu where the request carries a menu ID and create a local menu corresponding to the menu ID 

an obtaining module configured to obtain according to the menu ID in a stored correspondence between the menu item of a third party application and a local menu ID a menu item of a corresponding third party application and

an adding module configured to add the obtained menu item of the third party application to the local menu and display the local menu to which the menu item of the third party application is added 

where the obtained menu item of the third party application includes at least a menu item name and identity information and correspondingly 

a filling unit configured to in a menu list of local menus fill an unoccupied table in the menu list with the menu item name of the obtained menu item of the third party application 

a binding unit configured to bind the menu item name of the menu item of the third party application with the identity information where the identity information is used to identify a function or a secondary menu and

a first displaying unit configured to display the local menu to which the menu item of the third party application is added.

If the obtained menu item of the third party application further includes an icon ID the adding module further includes 

a searching unit configured to search a file set of the third party application for an icon corresponding to the icon ID.

the filling unit is specifically configured to fill an unoccupied table in the menu list with the menu item name of the menu item of the third party application and a found icon.

a storing module configured to search a file set of the third party application for a configuration file obtain by parsing the configuration file the menu item of the third party application and the local menu ID to which the menu item belongs and store the menu item of the third party application and the local menu ID to which the menu item belongs in unoccupied space.

a verifying module configured to after the storing module finds the configuration file verify the configuration file according to a defined structure of local menus.

a first obtaining module configured to when a user selects a menu item in the local menu to which the menu item of the third party application is added obtain the identity information bound with the menu item name in the selected menu item 

a second obtaining module configured to if the obtained identity information includes a function ID obtain a corresponding function according to the function ID and

a second creating module configured to if the obtained identity information includes a secondary menu ID create a secondary menu corresponding to the secondary menu ID.

an obtaining unit configured to obtain according to the secondary menu ID in the stored correspondence between the menu item of the third party application and the local menu ID a menu item of a corresponding third party application 

an adding unit configured to add the menu item of the third party application to the local secondary menu and

a second displaying unit configured to display the local secondary menu to which the menu item of the third party application is added.

The device may be a mobile phone where an Android platform is installed or a terminal device supporting the Android platform.

In the embodiment of the present invention a menu item of a third party application and an ID of a local menu to which the menu item belongs are stored in a configuration manager. When a local menu is created the menu item of the third party application that needs to be added to the local menu is obtained from the configuration manager and the obtained menu item is added to the local menu. The menu item of the third party application and the ID of the local menu to which the menu item belongs are stored in the configuration manager therefore the menu item of the third party application may be added to the database of Android without modifying an Android code. The menu item of the third party application is directly added to the local menu and thereby the menu item of the third party application is added to the local menu.

Persons skilled in the art may understand that all or part of the steps of the various methods according to the embodiments may be implemented by a program instructing relevant hardware. The program may be stored in a computer readable storage medium and the storage medium may include a ROM a RAM a magnetic disk or a CD ROM and so on.

The above specific embodiments further describe the objective technical solutions and benefits of the present invention in detail. It should be understood that the above are merely exemplary embodiments of the present invention and are not intended to limit the protection scope of the present invention. Any modifications equivalent replacements and improvements made without departing from the spirit and principle of the present invention shall fall within the protection scope of the present invention.

