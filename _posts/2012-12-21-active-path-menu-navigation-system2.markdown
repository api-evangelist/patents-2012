---

title: Active path menu navigation system
abstract: Disclosed is a method of navigating an information structure comprising: providing a graphical menu interface displaying the items of a given level of the information structure and enabling selection thereof; dynamically constructing an active path as a sequence of active links after an item of the information structure has been selected; said active links allowing the display of one or more items on a given level of the information structure; and said active links allowing a user to access an item in the information structure by selecting from the one or more items displayed by one of the active links on the active path.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09606699&OS=09606699&RS=09606699
owner: CADDO Systems, LLC
number: 09606699
owner_city: Marshall
owner_country: US
publication_date: 20121221
---
This application is a continuation of U.S. application Ser. No. 12 538 151 filed Aug. 9 2009 issued as U.S. Pat. No. 8 352 880 which is a continuation of U.S. application Ser. No. 11 687 646 filed Mar. 17 2007 issued as U.S. Pat. No. 7 725 836 which is a continuation of U.S. application Ser. No. 10 444 359 filed May 23 2003 issued as U.S. Pat. No. 7 216 301 which is a continuation in part CIP of U.S. application Ser. No. 10 164 520 entitled Active Path Menu Navigation System filed Jun. 6 2002 issued as U.S. Pat. No. 7 191 411.

The present invention generally relates to a navigation system used to find enter or edit data or launch an application within a hierarchical information system. The navigation system of the present invention may be implemented in software executing on a standalone software program or on a client server application. More particularly the navigation system of the present invention allows a user to access different levels in a hierarchical information system without retracing back to the top level of the hierarchy.

Hierarchical information systems are used to organize items by function or theme in order to facilitate efficient locating of functions or locations. Hierarchical systems are used to organize documents into directories or folders and to organize functions into pull down menus.

Conventionally one of two navigation systems are used to navigate through the various levels of a menu tree. By far the most popular menu navigation system is the so called collapsing menu system which for example is used by many traditional personal computer applications. The distinguishing characteristics of this system are that the navigation always commences from the initial or root level and that the menu collapses back to the root level after a selection is made.

Computer software frequently includes dozens of functions. The sheer number of features makes it desirable to organize the functions into a hierarchy of categories to facilitate efficient searching. In a collapsing menu system each level in the hierarchy is presented as a level in the pull down menu.

FIG. IB shows the pull down menu of with several levels of the hierarchical menu expanded. The menu structure of collapses back to the root level shown in once an end node is selected. The defining characteristic of such a conventional navigation system is that navigation is one way and always starts from the root level to an end node. This method of navigation becomes cumbersome if the desired function or destination is buried several levels down from the root directory.

To address this shortcoming conventional operating systems such as Microsoft Windows provide short cuts in the form of pre defined function keys or icons. Such short cuts enable the user to directly access the desired function associated with the short cut.

In the absence of a pre defined short cut the user must resort to navigating the menu structure. The problem with the collapsing menu system is that navigation must always commence from the root level. Consequently more experienced users are unable to take advantage of their knowledge of the hierarchical structure to directly access a given level.

Navigation using the path menu system requires the user to memorize and enter complex hierarchical sequences. This method of navigation is time consuming not suitable for users who have not memorized the path. Moreover this method becomes extremely cumbersome as the number of levels increases.

Accordingly one object of the present invention is to provide a more efficient way of navigating hierarchical menu systems.

A method for navigating within a multi level hierarchical collapsing menu structure is disclosed. Each level in the menu structure contains plural items each item representing a function such as the function of launching an application accessing a database location or pointing to a subordinate level.

The method of the present invention includes a step of providing a graphical user menu system displaying the items of a given level and enabling selection thereof wherein access of the given level requires sequential access of each of the levels preceding the given level in the hierarchy. An Active Path is dynamically constructed as a sequence of active links as items are selected using the graphical user menu system with one active link correspond to each of the items selected. The active links provide direct access to a function corresponding level or menu item without the need to navigate using the graphical user menu system.

According to a further aspect of the invention pre defined short cuts are provided which enable direct access to a given menu item. The Active Path is dynamically constructed and displayed when one of the pre defined short cuts are executed with one active link corresponding to each of the menu items necessary to access the given menu item using the graphical user menu system.

Navigation using the Active Path is accomplished by rolling over an active link with a pointing device or selecting an active link using a pointing device. Rolling over a given active link triggers the display of sibling menu items on the level associated with the given active link. Selecting a given active link triggers the execution of a function associated with the given active link.

The processing logic generally represented by processor is connected by a bus structure to the various other components of the computer . The schematic representation of bus is shown in as a simple and unitary structure but in conventional practice as is known to those in the art there usually are several buses and communication pathways operating at different speeds and having different purposes. Further bus may be segmented and controlled by respective bus controllers as is also known in the art.

Computer will also have a random access memory unit or units connected to the bus . RAM which may be DRAM SDRAM or other known types typically has loaded into it the operating system of the computer and executable instructions for one or more special applications designed to carry out the invention. Computer also has electronic read only memory for storing those programs such as the BIOS which are non volatile and persist after the computer is shut down.

In alternative embodiments of the invention one or more components of the invention s logic may be hard wired into the ROM instead of loaded as software instructions into RAM . ROM can consist of or comprise electrically programmable read only memory EPROM electrically erasable and programmable read only memory EEPROM of either flash or nonflash varieties or other sorts of read only memory such as programmable fuse or antifuse arrays.

In a typical architecture a computer program suitable for carrying out the invention will be stored on a mass storage device such as an optical disk or magnetic hard drive. Bus connects mass storage device to RAM . The computer is connected to various peripheral devices used to communicate with an operator such as display keyboard and pointing device mouse .

In operation operating system software such as Microsoft Windows executes on the computer and the user interacts with the operating system using the display keyboard and pointing device mouse .

The Active Path consists of a sequential listing of active links each active link providing direct access to a corresponding level in the hierarchical structure and to all of the menu items on the same hierarchical level sibling menu items .

It should be noted that whereas the conventional DOS path is merely a passive display of the hierarchical levels the Active Path is an interactive graphical user interface. As will become evident the Active Path has several significant advantages over conventional menu trees used to navigate hierarchical information structures.

The Active Path has distinct browsing and selection processes. The user browses by rolling over provisionally selecting an element with a pointing device such as a mouse causing the children to be displayed without hiding the siblings of the parent and siblings of the grandparents etc . This quality of navigation supports the user s sense of orientation and is maintained until the user makes a selection.

As used herein the term selecting IS distinguished from the term browsing . Selecting means actively choosing a menu item. Using a conventional pointing device such as a mouse selection of a menu item or active link is accomplished when the user depresses and releases the mouse key mouse up operation .

Browsing means that the user has rolled over a menu item or active link in order to view the siblings of the menu item or active link i.e. all of the menu items on the same hierarchical level as the browsed link. The user may continue browsing the hierarchical data structure by browsing rolling over the sibling menu items. The Active Path is not affected by the user s browsing. The displayed Active Path changes only when the user selects a menu item or active link .

The present invention is not limited to any particular pointing device and may be implemented in various ways without affecting the functionality of the invention. For example separate mouse keys could be used for browsing and navigating.

The user may directly access any hierarchically superior level in the hierarchical data structure by selecting the corresponding active link . In other words the user directly jumps to a given hierarchical level and is not forced to sequentially navigate through each of the hierarchical levels of data structure to reach a desired level.

When the user selects any active link the Active Path responds by executing a function. Functions may include the launch of a software application or the display of the subordinate links with a detailed description.

The user may alternatively browse the Active Path and any of the sibling menu items along a given branch in the data hierarchy. Browsing does not affect the active patch which continues to be displayed until the user selects an active link or one of the sibling menu items of an active link.

Moreover the Active Path enables the user to directly re execute the last function without the need to navigate to the function through the menu system and without the need for a pre defined short cut. This is accomplished by selecting the last active link end link .

In operation the Active Path starts with a special active link termed a root link displayed . No other elements on the same or subordinate hierarchical level are displayed until the root link is browsed rolling over or the expert user enters a shortcut to any point in the hierarchy.

According to a preferred embodiment there is a slight distinction between browsing an active link and browsing a menu item. In browsing an active link it is desirable to initially display only the siblings of the active link and display the children after a slight time delay . The time delay in displaying the children of the browsed active link facilitates the user s sense of orientation.

Another aspect of the invention relates to the user s ability to immediately re execute the last executed function by selecting the end link . In this manner the Active Path defines on the fly a short cut to the last function.

In contrast conventional short cuts such as a function keys icons or the like are static in that it only provides access to a single pre defined item function database location .

As described above each of the active links in the Active Path may be browsed by rolling over the active link with the pointer of the pointing device or accessed by selecting the active link . As shown in rolling over the active link simply entails manipulating the mouse to position the software pointer over the active link . Rolling over an active link causes the sibling menu items on the level corresponding the active link to be displayed. It should be noted that simply rolling over an active link does not alter the Active Path it merely causes the sibling menu items to be displayed.

Selection of an active link is accomplished by for example positioning the software pointer over the active link and actuating and releasing one of the mouse buttons . Selection of an active link causes different results depending on whether or not the selected active link is the end link in the Active Path . If the selected active link is not the end link then selection will cause a folder with subordinate levels and content to be displayed. For example the folder may contain a list of the sibling menu items subordinate levels or links on a given level of the hierarchical data structure and a brief description content of each of the menu items. Moreover if the selected active link is not the end link then selection will trigger the construction of a new Active Path . shows a user selecting active link .. . As shown the last executed function end link was .... After selecting the Active Path is truncated and .. becomes the end link .

Selection of an end link will cause the immediate re execution of the associated function last function executed . Thus the last executed function may be re executed by simply selecting the end link in the Active Path . Moreover selection of an end link will not affect the Active Path .

According to a further aspect of the present invention the Active Path may be used to define a short cut on the fly. Once the Active Path has been constructed the user may store the end link as a shortcut within a lookup table . According to a presently preferred embodiment this is accomplished by a combination of commands. Thus for example the user could be prompted to define a short cut identifier by clicking mouse button over end link . The Active Path then stores the association between the function or location and the user selected shortcut in the rewriteable table

The Active Path of the present invention may similarly be used to navigate to a location such as a location in a database or a web page. Notably the Active Path is created in the same manner regardless of whether the menu items represent functions or locations. In the case of navigating to a location selecting an active link other than the end link triggers the access of the associated database location. In contrast when navigating to a class of functions selection of an active link other than the end link merely triggers the display of the sibling menu items on the associated level. One of ordinary skill in the art will appreciate that the Active Path of the present invention may be used in standalone applications such as operating systems word processors spreadsheets or the like. Moreover the Active Path may also be used in a client server environment. Notably the Active Path may be used to navigate functions provided on a web site or to navigate between different web addresses.

In standalone applications a range of Microsoft Windows Application Programming Interface functions such as CreateWindow and other graphics library function calls may be used to create the graphic components of the Active Path. Any combination of mainstream programming languages such as Visual Basic Java C or Delphi may be used to create the dynamic components and rollover effects.

In client server applications the code for the Active Path may be part of the initial HTML file in form of a JavaScript DHTML combination or separate JavaScript files .js containing the arrays describing the Active Path and Cascading Style Sheets files .css containing the graphic attributes of the Active Path . This data may be cached locally after the initial server call.

For internet browser applications such as Internet Explorer or Mozilla the preferred embodiment foresees a replacement of the address bar with the Active Path to avoid redundancy allow the user to focus on the content and make browsing more efficient. For Microsoft Internet Explorer this would involve utilizing its custom Explorer Bars integration feature.

In standalone applications a range of Windows Application Programming Interface functions such as CreateWindow and other graphics library function calls may be used to create the graphic components of the Active Path. Any combination of mainstream programming languages such as Visual Basic Java C or Delphi may be used to create the dynamic components and rollover effects.

Windows Explorer may replace the Address Bar with the Active Path . This could make the display of the folder window redundant. The user may better take advantage of the screen real estate by rolling over and browsing through the levels of the collapsing menu system.

The Active Path of the present invention may also be used to navigate audio interfaces. A preferred embodiment for audio interfaces would allow users to navigate to the end point of a path. A certain input command such as pressing a certain key would read the sequence and level of the selected path. Users can then select any level of the path and navigate to a new endpoint.

The Active Path may also be used in conjunction with a conventional navigation system such as the above described collapsing menu system or path menu system.

The Active Path is dynamically assembled and displayed as the user navigates using the conventional menu screens. The Active Path is assembled automatically without the need for any additional user interaction as the user navigates using the collapsing menu system.

It should be noted that the menu system pull down menu tree collapses when the user selects end node ... whereupon the Active Path appears. The user may directly access different hierarchical levels simply by selecting different active links .

As described above the Active Path is dynamically constructed as the user navigates the collapsing menu system and is subsequently retained after the menu tree collapses back to the root level. In addition the Active Path may optionally be constructed each time a short cut such as a function key or the like is used. It should be noted that a shortcut may be defined for any point in the hierarchical structure. This requires the use of a look up table stored in RAM . The look up table stores each of the pre defined shortcuts and the associated data necessary to create the Active Path . According to a presently preferred embodiment the Active Path constructed is the same as would be constructed by accessing the function through the collapsing menu system.

In operation the look up table would originally be created by the software developer during initial definition of each of the pre defined short cuts function keys . Moreover as will be explained the look up table may be updated by the user to reference newly created short cuts.

A further aspect of the invention will now be described with reference to . Each menu item may contain additional pointers to functions such as a search entry field used for searching folders files or content of the subordinate information hierarchy.

The functionality of the search entry field may also be implemented by for example using a special button on the pointing device or special key stroke on the keyboard.

As noted above the Active Path of the present invention may be used to navigate directories with the internet being just one example of a directory.

Moreover the Active Path may be used to enhance the functionality of the address bar in an internet browser such as Internet Explorer or Mozilla.

If a data file representing the information hierarchy of the location is not located the Active Path Menu Navigation System will dynamically create the file from the directory structure and the hypertext markup language HTML available on the server and client files.

According to another aspect of the invention the Active Path may be used to as a method for navigating web sites including a plurality of hierarchically organized web pages. The method of the present invention eliminates the need for providing hyperlinks and navigational elements on the individual web pages.

According to the present invention a data file representing the hierarchical structure of the multi level hierarchical website is either constructed or retrieved from the server. As noted above the data file representing the information hierarchy of the location may be dynamically created from the directory structure and the hypertext markup language HTML available on the server and client files.

Using the Active Path the user browses the data file representing the information hierarchy of the location and selects a desired location. This eliminates the need to provide hyperlinks and navigational elements on the individual web pages.

A new Active Path is dynamically constructed each time the user navigates to a new location web page within the hierarchical website. Again each active link corresponds to a level in the hierarchical structure and a user may directly access any given level of the hierarchical structure by selecting a given active link. Moreover the active links provide the user the ability to directly browse all items on any given level of the hierarchical menu structure including all hierarchically subordinate items without affecting the Active Path.

Although a preferred embodiment of the Active Path navigation system of the present invention has been specifically described and illustrated it is to be understood that variations or alternative embodiments apparent to those skilled in the art are within the scope of this invention. Since many such variations may be made it is to be understood that within the scope of the following claims this invention may be practiced otherwise than specifically described.

