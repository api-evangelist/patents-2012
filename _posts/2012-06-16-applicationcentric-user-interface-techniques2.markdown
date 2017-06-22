---

title: Application-centric user interface techniques
abstract: Various application-centric user interface techniques are described. A user can easily launch, add, or update applications. An application-centric activity center can be presented as part of a user interface for an operating system shell. A file defining metadata for an application can be defined. The techniques can be applied to game-related software.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09610498&OS=09610498&RS=09610498
owner: Microsoft Technology Licensing, LLC
number: 09610498
owner_city: Redmond
owner_country: US
publication_date: 20120616
---
This application is a continuation of and claims benefit from U.S. patent application Ser. No. 12 750 602 filed Mar. 30 2010 now U.S. Pat. No. 8 245 534 issued Aug. 21 2012 that is a continuation of and claims benefit from U.S. Pat. No. 7 846 023 filed Mar. 27 2003 each of which is incorporated herein in its entirety.

The technical field relates to human computer interaction such as when a computer user interacts with user interfaces presented by software.

A portion of the disclosure of this patent document contains material that is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent document or the patent disclosure as it appears in the Patent and Trademark Office patent file or records but otherwise reserves all copyright rights whatsoever.

Since the beginning of the computer age various techniques of human computer interaction have been developed and implemented to help make computers easier to use. For example the now common graphical user interface GUI paradigm has made selecting programs easier because a user can point to an icon related to a desired program rather than having to type in the program s name.

However with the advent of ever more complex computing machinery has come seemingly more complex graphical user interfaces offering many levels of choices. A user can be presented with so many levels of choices in a user interface that finding the desired option becomes an unwelcome chore. As a result a user may tend to avoid choices that may in fact be desirable. The large number of choices thus serves as a barrier for the user.

The described technologies can provide various user interface arrangements and related functionality. For example various application centric user interface techniques can be employed.

In some examples an application centric user interface is presented to a user. In some examples a user can add update or launch programs from the application centric portion.

In some examples the application centric user interface includes an activity center by which a user can perform various actions related to the applications.

In a described implementation the applications include game related software. For example a user can be presented with the available games and related information. In some examples multiplayer online games can be launched.

Additional features and advantages will be made apparent from the following detailed description of illustrated embodiments which proceeds with reference to the accompanying drawings.

Various of the examples described herein can make use of application centric user interface techniques. With the advent of ever more complex user interfaces application centric user interface techniques can avoid the frustration associated with being unable to easily find applications and perform tasks for the applications. For example application centric user interface techniques can treat applications in a special way and include an area of the user interface limited to applications e.g. other types of items such as files are not listed in the area . Such an approach can be an improvement over a system that merely presents applications as part of a file system that includes a myriad of other items such as files.

In addition various of the techniques described herein can lead to a more rich presentation of applications such as when presented by an operating system shell. In this way an application publisher can customize their application s shell presentation. The techniques can accommodate a variety of applications from different application publishers.

The most recently launched application pane can show tiles for one or more e.g. three of the most recently launched applications. Or some other mechanism can be used to denote the most recently launched application s .

The task pane presents one or more tasks that can be performed for the user interface such as navigating to different pages within the user interface. Some tasks may be application specific while others may not operate on a particular application. In the example a view wish list option is shown. When activated e.g. by clicking the view wish list option navigates to a page showing a list of one or more applications that a user has designated as being in a wish list. For example a user may be considering purchasing such applications or have already decided that such applications are desired and will be purchased upon release.

The information pane can present one or more links which when activated e.g. by clicking navigate to a detail page for the application indicated by the link. The links can be limited to those having fresh information such as new information made available in the past n days e.g. configurable by a user .

In any of the examples areas of the user interface shown as panes may or may not be a visual boundary between the panes. Thus the panes may alternatively be areas of the user interface without visual boundaries. Additional fewer or other items can be included. For example a menu bar can present additional features or options.

To facilitate a rich presence for applications in a user interface the exemplary tiles described herein can present a graphical representation of an application and other information related to the application. is a screen shot of an exemplary application tile for use in an application centric user interface such as the user interfaces of . In the example the application s name a graphical e.g. iconic photographic or artistic representation of the application and a publisher name are included in the tile . Alternatively fewer additional or different items can be shown.

In any of the examples activation e.g. clicking or double clicking of the graphical representation can launch e.g. execute the respective application.

In any of the examples activation e.g. click ng or double clicking of the graphical representation A B N can launch e.g. execute the respective application. The representations A B N of the applications can be accompanied by information about the application e.g. application name and the like . Alternatively fewer additional or different items can be shown.

Additional pages not shown but possibly implemented include an application wish list. Further few or different pages can be implemented. The welcome page can take the form of any of the application centric user interfaces shown above e.g. the interface of

In addition the detail page includes an installation details pane . For example the program s file location installation size date installed copyright information preferred operating system patch history or some combination thereof can be displayed. Alternatively fewer additional or different items can be shown. Application publishers can create additional custom categories which may or may not include publisher created object code modules that provide additional information relevant to the application for the user s benefit.

Also the detail page includes a saved documents pane which has representations A B and C of saved documents for the application. Activation of the representation opens the document e.g. and launches the application if appropriate .

Finally in the example the capability rating system details pane shows the recommended capability rating for the application the minimum capability rating for the application and the user computer s capability rating. The capability rating gives an easily understood rating roughly indicating the computing resources required to execute the application. In this way a user can be forewarned that an application will not run or will not run well on the user computer.

In any of the examples activation e.g. clicking or double clicking of the graphical representation can launch e.g. execute the respective application.

Any of the user interfaces shown in the examples can be presented as part of a user interface for an operating system shell. For example if the operating system shell depicts the file system of the computer the user interfaces can be presented as a part of the file system.

The other windows may be presented by the operating system shell or by applications. The operating system shell may present other windows such as those for navigating throughout the file system or configuring the operating system.

In practice the folders may be shown as iconic or list representations of the items in the folders or in the case of the application folder a more rich presentation can be presented as shown in any of the examples herein.

Thus the file can include the application s name a name of the application s publisher a location to find link data for presenting informational links capability rating system information references to graphical representations of the application numerous other items or some combination thereof.

If desired the file can follow mark up e.g. XML conventions. The file can be associated with a signature to authenticate origin and integrity of the file . Additionally the file can include information e.g. hyperlinks for previewing e.g. acquiring a demo version or purchasing the application.

Application metadata files can be acquired in a variety of ways. For example if an application is provided via a CD ROM the application metadata file can be stored thereon and copied therefrom. If an application is downloaded via a network connection the file can be downloaded as part of the installation package. Or as described herein the application metadata file can be acquired without installing the application such as when adding the application to a wish list or for an application hosted on a remote web site. In some cases the application metadata file can be incorporated into or referred to by an application manifest. Such a manifest can be provided to indicate the items within a software package.

The application metadata file can be identified by a special file extension e.g. ADF GDF or other mechanism. An HTML tag in the hyperlink can indicate that the file is to he added to a wish list. The file can be accompanied by a digital signature so that the origin and integrity of the file can be authenticated.

Any of the application metadata files described herein can be used to install software. shows an exemplary method for achieving application installation via an application metadata file.

At the application metadata file is acquired. As described herein the file can be acquired in a variety of ways.

At the application is evaluated. The operating system shell can facilitate evaluation by a user by providing links to information about the application or the online community even before the application has been purchased or installed.

At the application is purchased. Billing information for the application software purchase can be collected electronically and the purchase can be achieved by activating e.g. clicking on an item which can operate with reference to information in the respective application metadata file.

At the application is installed. Installation can proceed according to a variety of methods including standard ones offered by the operating system.

The method can also be applied to upgrades. For example an upgrade can be evaluated before purchasing. In some cases an upgrade may be of such a nature as to be considered a separate application e.g. a major upgrade .

The described method can also be described as a method for marketing software. By presenting the user with an easy way to add a representation of the application to the operating system shell before the software is purchased the user can more easily become part of the online community related to the application. In this way the user can collect relevant information when deciding whether or when to purchase the application or an upgrade. Further the application publisher can keep in contact with the user via informational links. In this way targeted online marketing can be achieved without deluging the online community with mass email campaigns.

Upon installation of an operating system shell supporting the described application centric user interface techniques e.g. when upgrading the operating system there may be one or more applications already present on the computer. Such applications may not be present in the interfaces unless manually added by the user.

Such applications are sometimes called legacy applications. The user may be very interested in such applications so if they do not appear in the proper user interfaces the user may be disappointed and not take advantage of the functionality described herein.

To facilitate accommodation of legacy application various methods can be used. shows one such method . The method can be performed by the operating system in the background as other applications are running. Over time the method can identify the applications on the computer. For example if the operating system contains a routine that scans the files in the file system the method can run as part of the operating system routine. Alternatively the method can be run all at once.

At a file is found during a scan. Files considered can be limited to executables. Then at it is determined whether the file matches a fingerprint stored as part of the operating system. A fingerprint ng technique can be used so that the application is verified to be a particular application without its being an exact copy. If a match is indicated details for the file e.g. location and associated application metadata file name can be stored in a list. Subsequently the list can be considered e.g. when an application activity center is launched or resumed and the application metadata files can be added e.g. after appropriate configuration if any to the database e.g. the database .

The described fingerprints and associated application metadata files can be provided as part of the operating system an operating system upgrade or provided on a remote Internet resource such as a web server. The latter case provides flexibility in providing ongoing updates to the database of information for legacy applications. For example application metadata files can be generated for the more popular application titles so that they eventually appear in the application activity center. Any number of other techniques can be used.

Any of the technologies described herein can be applied with advantage to games. An activity center limited to games e.g. not depicting other applications can be implemented. Games can be accommodated via a specialized application metadata file. Such a file can include additional information about the game such as how to achieve multiplayer online game scenarios.

Further when implemented as part of a user interface for the operating system shell a game activity center can provide an easy way for users to manage and launch games. For example the operating system shell can present a my games folder by which the game activity center is presented. Still further instant messaging functionality can be incorporated into the game activity center. And if the operating system supports contact objects multiplayer online games can be initiated via reference to the contact objects.

Various other game specific functionality can be incorporated. For example an application tile can include a link for playing the most recently saved game. In a detail page the n e.g. 3 most recently saved games can be portrayed graphically e.g. via a mini screen shot depicting the game situation when it was saved .

In addition the pane includes an information links pane which includes an information link which when activated e.g. by clicking navigates to the indicated information.

A task pane shows various tasks that can be achieved for the application e.g. by activating the task item . For example the game can be played by activating the button . Other tasks include continue the last saved game play multi player play with buddies review and install updates e.g. upgrades or updates to data files view saved games search for new games find similar games visit an online forum for the game visit an online community for the game join an online chat room for the game change or uninstall the game go to the game s official webpage check compatibility information for the game check security information for the game view usage history e.g. when played how long played how often played and show program files.

In practice additional fewer or different items may be shown. In any of the examples activation e.g. clicking or double clicking of the graphical representation can launch e.g. execute the respective application.

Contact information for the buddy computers A B N can be stored on a buddy list. When determining whether buddies are playing a particular game or any games the list can be consulted. If desired consent can be acquired before adding a contact to a buddy list.

Although multiplayer online games have become very popular they can still remain somewhat difficult to start. Various technologies described herein can simplify multiplayer online game user interface operation.

The operating system shell is operable to interface with a user e.g. via the operating system shell or an interface for the instant messaging functionality to receive directions regarding multiplayer game scenarios. The shell can then provide appropriate information to the game application to initiate or join the multiplayer online game.

In some cases a multiplayer online game can be initiated or joined via the contact object e.g. a user interface depicting information about an individual such as a friend or buddy .

The example also includes a chat pane whereby the user can hold an online chat session e.g. via messenger functionality with other potential players. Text can be entered into the box and the button activated to send a message via the chat session.

The invited buddies pane includes depictions e.g. photographs of those buddies e.g. remote users whom the user has invited to play. Also included is the buddy s name and a quality rating of the buddy s connection e.g. indicative of whether a dialup or broadband connection is available for the buddy . Additional buddies can be invited via the button . In the example the user is hosting the game e.g. controls who is invited to the game . Other scenarios are possible.

Finally a ready button can be activated by the user or buddies at their respective computers to indicate that they a e ready to begin playing. Upon pressing the launch button the game is begun with the displayed buddies in the buddy pane . Information in the game metadata file can be consulted to determine how to launch the game e.g. how to submit the buddies for the online game .

The user interface can be arrived at in a variety of ways. For example a game detail page can present a link e.g. play multiplayer or play with buddies which when activated presents the interface . Or the user may be chatting with a buddy via the messaging software and be presented with an option by which the user interface is presented. Finally an option can be presented when showing a list of buddies e.g. in a contact list represented by contact objects by which the user interface is presented. The associated players can be automatically listed in the buddy pane if desired.

Before the interface is presented another user interface can be presented e.g. Who do you want to play this game with by which a user selects buddies. Such a user interface can present various contact related options e.g. my contacts company directory family address book recent contacts cell phone contacts filters or some combination thereof .

In any of the game examples described herein games can be associated via content raking in a content rating system. For example a game can be rated as acceptable for all audiences or for mature audiences only. The system can accommodate various content rating conventions e.g. from different countries .

A user e.g. with an administrator password can configure the system so that certain users are designated as to play games of only certain specified content ratings. For example a parent can specify that a child can play only games rated for all audiences. 

In any of the examples described herein applications can be associated with a capability rating system CRS . For example a higher rating can indicate that greater computing resources are needed to run the game. A minimum as well as a recommended capability rating can be specified for the application. The rating can be compared with a rating of the user computer to see whether the application will run or run well on the user computer.

Further discrete system requirements can be specified for an application. For example certain applications may require specialized hardware e.g. a graphics tablet or a game controller .

Certain options can be not presented based on the requirements specified. In practice a user will be permitted to launch an application even if it only meets the minimum system requirements.

The capability system rating can be presented for the application when it is added on a wish list. In this way the user can easily determine whether or how well the application will run on the user computer.

In any of the examples described herein combinations of one or more of the following can be presented for the application e.g. as pa t of the tile for an application on the application s detail page or both System Requirements e.g. CRS installation details e.g. install folder size on disk date installed patch history e.g. filtered for the application and saved document summary.

When presenting games in any of the examples herein the following additional items can be presented online game s currently in progress saved game summary and preferred input device assignment.

When listing applications in any of the examples herein the lists can be ordered by any of a variety of criteria e.g. by name alphabetical by genre by publisher by most recently run size on disk .

When presenting application tiles the following can be included link s to new publisher content available link s to online forums link s to fan sites. When presenting games the following can be presented a content rating whether buddies are online a list of buddies online or some combination thereof. When presenting more than one game at a time a summary of games for which updated information is available can be presented.

For any of the application tiles shown herein the tiles can include various information. The tiles can include any combination of the following information date installed release date emphasize if on wish list last run hours run publisher name and logo developer name and logo installation path patch history CRS data update notification extended description screenshots saved documents.

The tiles can include various items which when activated perform a task e.g. the item behaves as a hyperlink or a command. Possible tasks include the following find a new application review and install updates view system capabilities check for updates view my wish list return to welcome page run continue last document view saved documents change remove find similar applications visit forum join chat room register application view usage history show installation folder check for updates for this application online email a friend about this application buy this application download the demo.

In addition or alternatively in implementations accommodating dames the following information can be included saved games last played hours played number of buddies playing. The following tasks can be included configure parental controls play continue last saved game play with buddies join an internet or LAN game session create a new Internet or LAN game find a new game view saved games find similar games register game online.

When a user chooses to update or upgrade software the functionality can be integrated with other update functionality on the computer. For example if the computer s software e.g. operating system includes a download manager the download manager can be invoked to acquire the update or upgrade.

A wide variety of functionality can be achieved via the technologies described herein. In addition to those shown a user can add an application see a patch history for an application and see upgrades or other applications.

An application metadata file can include any information appropriate for achieving the user interfaces described herein. Table 1 shows exemplary fields in an application metadata file.

For those items of the user interface involving information links e.g. the pane of the link of the information pane of the link of the pane in and the information link of the pane of the information links can be implemented according to the technologies described in U.S. patent application Ser. No. 10 401 520 Evans et al. PROVIDING INFORMATION LINKS VIA A NETWORK filed Mar. 27 2003 which is hereby incorporated herein by reference and filed concurrently with the present application.

With reference to an exemplary system for implementation includes a conventional computer such as personal computers laptops servers mainframes and other variety computers includes a processing unit a system memory and a system bus that couples various system components including the system memory to the processing unit . The processing unit may be any of various commercially available processors including Intel x86 Pentium and compatible microprocessors from Intel and others including Cyrix AMD and Nexgen Alpha from Digital MIPS from MIPS Technology NEC IDT Siemens and others and the PowerPC from IBM and Motorola. Dual microprocessors and other multi processor architectures also can be used as the processing unit .

The system bus may be any of several types of bus structure including a memory bus or memory controller a peripheral bus and a local bus using any of a variety of conventional bus architectures such as PCI VESA AGP Microchannel ISA and EISA to name a few. The system memory includes read only memory ROM and random access memory RAM . A basic input output system BIOS containing the basic routines that help to transfer information between elements within the computer such as during start up is stored in ROM .

The computer further includes a hard disk drive a magnetic disk drive e.g. to read from or write to a removable disk and an optical disk drive e.g. for reading a CD ROM disk or to read from or write to other optical media. The hard disk drive magnetic disk drive and optical disk drive are connected to the system bus by a hard disk drive interface a magnetic disk drive interface and an optical drive interface respectively. The drives and their associated computer readable media provide nonvolatile storage of data data structures computer executable instructions etc. for the computer . Although the description of computer readable media above refers to a hard disk a removable magnetic disk and a CD it should be appreciated by those skilled in the art that other types of media which are readable by a computer such as magnetic cassettes flash memory cards digital video disks Bernoulli cartridges and the like may also be used in the exemplary operating environment.

A number of program modules may be stored in the drives and RAM including an operating system one or more application programs other program modules and program data in addition to an implementation .

A user may enter commands and information into the computer through a keyboard and pointing device such as a mouse . These and other input devices are often connected to the processing unit through a serial port interface that is coupled to the system bus but may be connected by other interfaces such as a parallel port game port or a universal serial bus USB . A monitor or other type of display device is also connected to the system bus via an interface such as a video adapter . In addition to the monitor computers typically include other peripheral output devices not shown such as speakers and printers.

The computer operates in a networked environment using logical connections to one or more remote computers such as a remote computer . The remote computer may be a server a router a peer device or other common network node and typically includes many or all of the elements described relative to the computer although only a memory storage device has been illustrated. The logical connections depicted include a local area network LAN and a wide area network WAN . Such networking environments are commonplace in offices enterprise wide computer networks intranets and the Internet.

When used in a LAN networking environment the computer is connected to the local network through a network interface or adapter . When used in a WAN networking environment the computer typically includes a modem or other means for establishing communications e.g. via the LAN and a gateway or proxy server over the wide area network such as the Internet. The modem which may be internal or external is connected to the system bus via the serial port interface . In a networked environment program modules depicted relative to the computer or portions thereof may be stored in the remote memory storage device. It will be appreciated that the network connections shown are exemplary and other means of establishing a communications link between the computers may be used.

Also although the example code is in the C language any number of other programming languages can be used to implement an application programming interface. Further the example shows that the applications are incorporated into the operating system shell via a folder named My Games however other folder names or way of incorporating into the operating system shell can be used.

Table 2 shows exemplary families of functions for an API and Table 3 shows exemplary functions for an API. In the example a supported title is a non web non legacy title supported by the system the web and legacy titles are still supported by the system. Additional fewer or different functions can be implemented.

In the example the schema specifies that the metadata can include an application identifier identifying an application installable in an application activity center e.g. applicationid a displayable description of one or more tasks performable for the application when installed into the application activity center e.g. description for taskdata data indicating how to invoke the one or more tasks performable for the application when installed into the application activity center e.g. invokedata for taskdata and arguments for the one or more tasks performable for the application when installed in the application activity center e.g. arguments for taskdata . Additional fewer or different elements can be defined for the schema.

Having described and illustrated the principles of our invention with reference to various embodiments it will be recognized that the embodiments can be modified in arrangement and detail without departing from such principles. It should be understood that the programs processes or methods described herein are not related or limited to any particular type of computer apparatus unless indicated otherwise.

In any of the examples depicting user interfaces such interfaces can be implemented as graphical user interfaces GUIs . Although iconic representations of programs are shown in any of the examples box art e.g. an apparent photograph of the physical box for the software for the application can be used instead.

Although some examples are shown in general purpose computers the technologies can be alternatively applied to console game scenarios.

Various types of general purpose or specialized computer apparatus may be used with or perform operations in accordance with the teachings described herein. Elements of the illustrated embodiment shown in software may be implemented in hardware and vice versa.

In view of the many possible embodiments to which the principles of our invention may be applied it should be recognized that the detailed embodiments are illustrative only and should not be taken as limiting the scope of our invention. Rather we claim as our invention all such embodiments as may come within the scope and spirit of the following claims and equivalents thereto.

