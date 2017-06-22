---

title: System and method for access control and usage monitoring
abstract: A system () for providing access control and usage monitoring of a plurality of electronic devices or applications (-) enables efficient access control. The system () includes a control server () having: a reception interface, for receiving usage information relating to an account and a request to use the account, wherein each request includes an account identifier, and the account is associated with one or more of the plurality of electronic devices or applications (-) and at least one user; a data store, including a first set of usage rules for the account and a second set of usage rules for a second account; a processor and memory including program code, for: determining, using the rules stored on the data store associated with the account identifier in combination with the usage information, an outcome of the request; and a transmission interface, for communicating the outcome of the request, wherein the outcome is for controlling access to one or more of the plurality of electronic devices or applications (-) by the at least one user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09450962&OS=09450962&RS=09450962
owner: Allow2PtyLtd
number: 09450962
owner_city: 
owner_country: AU
publication_date: 20120730
---
This application claims the benefit of PCT Application Serial No. PCT AU2012 000899 Jul. 30 2012 and Australian Patent Application Serial No. 2011903068 filed Aug. 1 2011.

The present invention relates to access control and usage monitoring. In particular although not exclusively the invention relates to centralised access control and usage monitoring of a plurality of electronic devices.

Various access control systems for devices are presently available often marketed as parental control systems. Access control systems of the prior art include an interface often as part of a menu system of a device that is to be controlled. Devices of the prior art including access control systems include televisions internet routers and gaming devices. Access control systems of the prior art often use a personal identification number PIN as access control means.

A disadvantage of access control systems of the prior art is that there is no synchronization between devices. A plurality of similar devices must be configured separately and usage of such devices is measured separately. Access control systems of the prior art in other words generally are not used to set total limits for a plurality of devices.

A second disadvantage of access control systems of the prior art is that modification of the access control is typically similar to reconfiguring the access control system. This is particularly burdensome for example when a child is sick for a day or during school holidays and the default access control settings need to be modified.

A third disadvantage of access control systems of the prior art is that the access control systems are generally all or nothing . For example blocking internet access for a user will typically also block internet based applications such as backup or system update applications.

It is an object of some embodiments of the present invention to provide consumers with improvements and advantages over the above described prior art and or overcome and alleviate one or more of the above described disadvantages of the prior art and or provide a useful commercial choice.

According to one aspect the invention resides in a system for providing access control and usage monitoring of a plurality of electronic devices or applications including 

Preferably the rules include at least one of a time of day based restriction a time based limit and a resource based limit.

Preferably the rules include at least one rule that applies to more than one of the plurality of devices.

Preferably the account identifier comprises a combination of a user identifier identifying a user of one or more of the plurality of electronic devices or applications and a device identifier identifying one or more of the plurality of electronic devices or applications.

Preferably the plurality of electronic devices or applications include at least one of a television a personal computer a printer a router a games console a telephone a micro blogging application and a social networking application.

Preferably the rules include a plurality of rules applicable to the account identifier wherein each rule is individually assessed.

Preferably the control server includes a reporting module that generates a report including usage statistics.

Preferably the day types include at least one of a weekday a weekend a school day a school night a school holiday a public holiday and a sick day.

Preferably the control server includes an administration interface which enables addition or deletion of rules and setting of day types.

Preferably the rules may be modified through tokens where tokens may be redeemed for a change in a rule.

Preferably the change in the rule is adapted to encourage usage of a first device over usage of a second device.

According to another aspect the invention resides in a method of providing access control and usage monitoring of a plurality of electronic devices or applications by a centralized server including 

receiving usage information relating to an account wherein the account is associated with one or more of the plurality of electronic devices or applications and one or more users 

determining using rules stored on a data store and the usage information an outcome of the request wherein the rules include time or resource based restricted access to the account and

sending a notification of the outcome of the request to the one or more electronic devices or applications.

Those skilled in the art will appreciate that minor deviations from the layout of components as illustrated in the drawings will not detract from the proper functioning of the disclosed embodiments of the present invention.

Embodiments of the present invention comprise access control and usage monitoring systems and methods. Elements of the invention are illustrated in concise outline form in the drawings showing only those specific details that are necessary to the understanding of the embodiments of the present invention but so as not to clutter the disclosure with excessive detail that will be obvious to those of ordinary skill in the art in light of the present description.

In this patent specification adjectives such as first and second left and right front and back top and bottom etc. are used solely to define one element or method step from another element or method step without necessarily requiring a specific relative position or sequence that is described by the adjectives. Words such as comprises or includes are not used to define an exclusive set of elements or method steps. Rather such words merely define a minimum set of elements or method steps included in a particular embodiment of the present invention.

According to one aspect the invention resides in a system for providing access control and usage monitoring of a plurality of electronic devices including a control server including a reception interface for receiving usage information relating to an account and a request to use the account wherein each request includes an account identifier and the account is associated with one or more of the plurality of electronic devices a data store including a first set of usage rules for the account and a second set of usage rules for a second account a processor and memory including program code for determining using the rules stored on the data store associated with the account identifier in combination with the usage information an outcome of the request and a transmission interface for communicating the outcome of the request wherein the outcome is for one or more of the plurality of electronic devices to control access to the account.

Advantages of some embodiments of the present invention include an ability to efficiently provide access control to a plurality of devices and or applications. By applying rules and usage information across the plurality of devices and or applications convenient and centralised control such as by parents can be achieved. According to some embodiments rules can be easily structured to achieve usage rewards incentives or punishments associated with chores or other daily activities.

The access control system includes a centralized access control server and a plurality of devices and applications . The plurality of devices and applications may include a computer a tablet a telephone a micro blogging application a router a printer a gaming device and a social network application

An Application Programming Interface API is used to configure each device and application by the access control server .

The access control system additionally includes a web interface which may be used to configure the centralized access control server .

As is understood by a person skilled in the art not all the devices and applications of need be present in a real system and a system may include multiple devices or applications of a single type. For example the access control system may be used to control a plurality of computers

Similarly the access control system may be used with other types of applications including access to a bank account a debit or credit card or any other type of application that may be associated with an electronic device in some manner.

The system enables children for example to use a credit or debit card instead of cash. A parent then may be able to control a total amount of money spent or an amount of money spent on particular categories of products and services such as movies junk food cosmetics and the like by controlling a bank account through a banking application.

The centralized access control server may be located for example in a home an office a school at a third party location or run using a cloud based architecture.

The centralized access control server includes a reception interface for receiving both usage information relating to a user account and requests to use the user account. The user account may comprise a user identifier and device combination an account identifier for an external application or an access control account used on multiple devices for example. The applications are associated with one or more of the plurality of electronic devices either directly or indirectly. For example a social networking application may be associated with all devices having computer access and a browser.

The centralized access control server typically includes a moderator account and a plurality of user accounts. The moderator account is used to control access to devices through the plurality of user accounts. The moderator account may create user accounts or invite users to join for example. The system may comprise multiple moderator accounts.

The system may comprise a combination of administration accounts and moderator accounts. An administration account may be provided to a teacher or other trusted third party in other to allow the trusted third party to help administer a user account. For example an administration account may recommend a reward or punishment but a moderator account may approve or deny the recommended reward or punishment.

Additionally a moderator or administration account may for example also be a user account. For example an older child may be able to help a parent administer a younger child s account while at the same time being moderated by the parent. In this case the older child s account is both a user account and an administration account.

A user identifier may comprise for example a personal identification number a username and password a smart card or similar device or any other type of identifications means. A user identifier may have global scope for example through an email address or have a local scope limited to an access control network such as where a user identifier is a personal identification number.

Accounts including user accounts moderator accounts and administration accounts of the centralized access control server are advantageously associated with an email address or other type of communications means. The user identifier may include for example an email address phone number or other type of communications address. Associating an account with a communications address enables the system to send information to the moderators or users relating to their accounts. Accounts may be associated with an email address or other communications means at any time. For example a young child may initially have a user account without an email address. Later when the child gets older an email address may be added to the child s user account.

The centralized access control server and the plurality of devices and applications are advantageously paired. Pairing is a process that links a device or application to the centralized access control server and is typically performed a single time either on initialisation of the system or when a new device is purchased. For any device or application to correctly apply access control it must first be paired with the centralized access control server .

Each device or application may have its own legacy access control system but when a device or application is paired with the centralized access control server the device or application should ignore any legacy control settings and instead use settings of the centralised access control server .

Pairing may be performed on devices that are used by a group of people where access to the devices is controlled by a single moderator account. Examples of such devices include a family computer such as the device or a television.

In order to pair a shared device such as the game device a moderator may access the access controls of the device through its manufacturer supplied interface and enter an identifier associated with the device and the centralized access control server . Alternatively a device identifier may be created one on the spot over a suitable interface. The device then contacts the centralized access control server and authenticates the pairing request. If authenticated the device is added to the system and part of a paired key or other suitable authentication means is shared with the device

After pairing a device may periodically reconnect in order to check limits for the device identifier using the authentication means.

Alternatively per user pairing can be performed on devices or applications shared by many users. Examples of such devices or applications include social networking applications and school devices which are used by multiple students. Thus devices can be variously controlled by multiple accounts regarding for example various cloud based services such as those defined by the registered trademarks Facebook Twitter iCloud Club Penguin Dropbox and Skype.

Upon creation of a user account a user may additionally enter a moderator account identifier. The moderator account identifier is used to identify and access the centralized access control server to which a request is sent. The centralized access control server sends a request to a moderator which may accept or rejects the request. If accepted the pairing is considered complete and the service is controlled by the centralized access control server .

An application provider or device manufacturer may decide that only partial or no access to the application or device is allowed until the moderator has accepted the pairing.

Once a device is paired it appears in a device list screen of the centralized access control server .

A user may send a request to a moderator as described above or get invited by a moderator to create a user account. An invitation from a moderator may include for example creation of a user account on a new device.

The centralized access control server includes a data store including usage rules for user accounts. The usage rules include at least a first set of usage rules for a first user account and a second set of usage rules for a second user account.

The centralized access control server determines using the rules stored on the data store associated with the relevant user account identifier in combination with the usage information whether further usage should be granted or denied. This outcome is communicated to the user through one or more devices or applications 

A device or application may allow access to the device or application by a user without a connection to the control server . This may be based on last known available remaining time and last known bans for example. The device or application or an entity between the device or application and the control server may store requests for later reporting.

When a connection with the control server is available the device or application may then report usage relating to the request to the server. The device or application may report the usage in a similar way to the request described above but with a flag or similar signalling mechanism in order to indicate that the time has already been used. This is advantageous as a server should not deny a request for time that has already been allocated and used even if insufficient time is available for an account. That will enable an account to go into debt if a user uses more time than allocated when a device or application is not connected to the control server . Any further time allocated to the account will then first be applied to reducing such debt.

A transmission interface of the control server is used for communicating the outcome of the request. The outcome is for one or more of the plurality of electronic devices or applications to control access to the user account. The outcome may be sent directly to one or more of the plurality of electronic devices. Alternatively the outcome may be sent to a server which indirectly controls the plurality of electronic devices or applications through a user account. For example an outcome may be sent to a social network application server which in turn grants or denies access to a user account.

The calendar is a Gregorian calendar and includes date information relating to the month and year that is being displayed. The calendar includes navigation buttons that allow for month by month navigation forwards and backwards in time respectively. The calendar is arranged in a table arranged according to day of the week. As is understood by a person skilled in the art any other suitable calendar or date presentation means may be used without departing from the invention.

Each day shown as a cell in the calendar may be given a day category . Day categories may include public holiday school holiday or special day for example. A special day is a day which may be configured additionally such as a sick day for a specific person. Normal days i.e. days without a particular day category are shown without marking. Day categories may however include default day types such as work day school day weekend and all days may be shown as having a day category .

A popup information balloon may be used to provide extra information about day configuration. For example a special day may include extra information in the popup information balloon indicating that a person is sick including details of that person. A special day may apply to a single person only or to a group of people. For example a public holiday may be applied to all people wherein a sick day may be applied only to one person who is sick.

Each day may be associated with default day types. For example Monday to Friday may be associated with school days and Saturday and Sunday with days off. The default day type may then be modified when needed such as when a person is sick or on school holidays.

The device list includes a name of the device a manufacturer of the device a description of the device and information relating to when the device was last used or last paired with the access control system . The device list may include a delete button for each device which may be used to remove a device from control of the system . As is understood by a person skilled in the art other information and buttons may be present including an add device button and not all of the information shown in need be present.

The name of a device may double as an access control configuration button. This enables access control of a device to be configured. As is understood by a person skilled in the art devices may be configured as groups for example televisions or internet access may be controlled together for a plurality of devices. According to some embodiments the control server can also provide a directory that lists compatible products that have incorporated the services of the present invention such as in the same way the App Store of Apple Computer Inc. lists all apps that are usable on iPhones Registered Trademark .

The rules generation page includes a plurality of day category tabs which are used to specify when a rule is valid. The rules generation page includes menus to select users to which a rule is valid the activity to which a rule applies and the devices to which a rule applies.

As is understood by a person skilled in the art the users activity and device selection menus may include group creation and group selection functionality. This allows for a rule to be applied to multiple people on multiple devices or for multiple activities.

Users may be drag and dropped to create a new group of users. Rules for the new group may be blank and thus need to be added or rules from one or more existing groups may be imported. If a user is dragged to an existing group the rules of the existing group apply for the user. As is understood by a person skilled in the art the above mentioned default application of rules are simply examples and the default rule settings may be changed at any time.

The rules generation page includes a timeline which may be used to specify when a rule is valid. The timeline specifies when usage of a device is allowed but as is understood by a person skilled in the art the timeline may also specify when usage of a device is forbidden. The rules generation page includes a break specification which may specify if and how often breaks are required during use of a device.

The rules generation page additionally includes functionality to specify timelines and break specifications dependant on the category of the following day .

Rules may take any suitable form but are typically implemented through limits. A limit may apply to many devices such as total internet time allowed or could be very specific to a device or application such as a total number of social network postings allowed. According to some embodiments users may also specify extensions on an ad hoc basis. For example additional allowance and or additional time periods can be provided on an ad hoc basis e.g. 30 minutes extra time now or 5 additional printouts this afternoon .

As is understood by a person skilled in the art limits need not be time specific and may include limits such as total expenditure for a bank account or category specific such as total expenditure for a product or service category such as entertainment food etc.

The rules generation page shows time limits for the selected day category tab . The limits show the times during which an activity is allowed but the allowed times may vary for a day category depending on the day category of the following day. For example a child may be allowed to watch television later on an evening if the following day is a holiday or weekend.

Rules may be additionally enhanced through tokens. Tokens may be issued as part of an allowance or as a type reward. According to one embodiment tokens may be redeemed for time on devices wherein the time redeemable is adapted to encourage a certain type of use. For example a token may be redeemed for 15 minutes of television or 30 minutes of educational gaming thus encouraging educational gaming over television.

According to some embodiments an online shop is integrated into the access control system where the shop allows parents or guardians for example to set up their own rewards catalogue from which their kids can choose items on which to spend tokens. For example the catalogue items can be of three types 

a Vouchers for specific prizes. For example a parent may simply go out and purchase a catalogue item for which an appropriate number of vouchers has been redeemed or a prize may be for an extra piece of cake or an hour to play with dad 

c Real products from other vendors such as a book or game from an online store such as Amazon.com . In this case the platform may act as an agent for the vendor and process a transaction automatically based on the child selecting a product.

Bans are similar to rules in that they specify a time during which a device or group of devices may not be used. Bans are however used together with regular rules such that when a ban expires the regular rules come into action again.

The ban page includes a ban type a limit a user list and an expiry setting . Ban type may include a limit of a feature present in multiple devices or a device limit. Examples of feature limits include TV or Internet usage and a device limit limits access to a specific device that is specified in the limit .

The user list includes the users or the group of users to which a ban applies. The expiry includes the date and time when the ban expires. Upon expiry of a ban any previous rules for the device and user applies.

Bans of the present invention can be programmed to lapse after a specified period of time e.g. no internet for 3 hours at a certain time e.g. no internet until 5 pm Monday 23 Mar. 2011 or until one or more criteria are met. Such criteria may comprise tasks such as have a shower dress for school have breakfast put dishes in dishwasher make lunch and pack bag. The completion of such criteria is advantageously updated by a moderator for example a parent.

Bans can be created on the fly in response to a bad behaviour or pre created as a list to quickly select from. Bans may be programmed to auto apply at certain times of certain days such as a get ready for school style ban which would ban all use of all devices until a child is ready for school.

Bans may be presented to a user as a checklist displaying what is necessary for the user to lift the ban. Once all items are completed a request may be posted to a moderator in order to approve the ban being lifted. Additionally users may be trusted to self administer bans checking off items themselves. Further bans may be designed to always allow designated exceptions such as the ability to always call emergency services e.g. dialing 000 or 911 or call or message particular individuals such as a mother or father.

The user status view includes time usage status and unit usage status . Time usage status may include how much time is left for a device or a group of devices for a usage period or multiple usage periods. Unit usage status includes how many units are left for a device such as a device or multiple devices. Units may include text messages emails pages on a printer etc.

The user status view includes a ban overview detailing any bans applicable to the user. The ban overview may include the device or devices a ban is applicable to and the time when the ban expires.

The user status view includes a request button where a user may request more time for a time based limit or more units for a unit based limit. The request for time or units is sent to a moderator for approval.

The access control system is similar to the access control system and includes a centralized access control server and the plurality of devices .

The access control system additionally includes a local server . The local server acts as a proxy between the plurality of devices and the centralized access control server . The local server reduces data traffic exiting for example a home network. Preferably the local server is embedded in a router or other consumer product.

The computer system includes a central processor a system memory and a system bus that couples various system components including coupling the system memory to the central processor . The system bus may be any of several types of bus structures including a memory bus or memory controller a peripheral bus and a local bus using any of a variety of bus architectures. The structure of system memory is well known to those skilled in the art and may include a basic input output system BIOS stored in a read only memory ROM and one or more program modules such as operating systems application programs and program data stored in random access memory. RAM .

The computer system may also include a variety of interface units and drives for reading and writing data. In particular the computer system includes a hard disk interface and a removable memory interface respectively coupling a hard disk drive and a removable memory drive to the system bus . Examples of removable memory drives include magnetic disk drives and optical disk drives. The drives and their associated computer readable media such as a Digital Versatile Disc DVD provide non volatile storage of computer readable instructions data structures program modules and other data for the computer system . A single hard disk drive and a single removable memory drive are shown for illustration purposes only and with the understanding that the computer system may include several similar drives. Furthermore the computer system may include drives for interfacing with other types of computer readable media.

The computer system may include additional interfaces for connecting devices to the system bus . shows a universal serial bus USB interface which may be used to couple a device to the system bus . For example an IEEE 1394 interface may be used to couple additional devices to the computer system .

The computer system can operate in a networked environment using logical connections to one or more remote computers or other devices such as a server a router a network personal computer a peer device or other common network node a wireless telephone or wireless personal digital assistant. The computer includes a network interface that couples the system bus to a local area network LAN . Networking environments are commonplace in offices enterprise wide computer networks and home computer systems.

A wide area network WAN such as the Internet can also be accessed by the computer system for example via a modem unit connected to a serial port interface or via the LAN .

It will be appreciated that the network connections shown and described are exemplary and other ways of establishing a communications link between the computers can be used. The existence of any of various well known protocols such as TCP IP Frame Relay Ethernet FTP HTTP and the like is presumed and the computer system can be operated in a client server configuration to permit a user to retrieve web pages from a web based server. Furthermore any of various conventional web browsers can be used to display and manipulate data on web pages.

The operation of the computer system can be controlled by a variety of different program modules. Examples of program modules are routines programs objects components and data structures that perform particular tasks or implement particular abstract data types. The present invention may also be practiced with other computer system configurations including hand held devices multiprocessor systems microprocessor based or programmable consumer electronics network PCS minicomputers mainframe computers personal digital assistants and the like. Furthermore the invention may also be practiced in distributed computing environments where tasks are performed by remote processing devices that are linked through a communications network. In a distributed computing environment program modules may be located in both local and remote memory storage devices.

At step the centralised server receives usage information relating to an account. The account is associated with one or more electronic devices or applications. The account may comprise a social networking account for example which resides on a plurality of electronic devices on the Internet. Alternatively the account may be associated with a local device and a user of the local device.

At step a request to use the account is received from a user. The request may comprise for example a time request or a unit request. A time request may comprise a request to use a device for a certain period of time for example. A unit request may comprise for example a request to send a text message or a request to print a page on a printer.

At step an outcome of the request is determined using rules stored on a data store and the usage information.

At step notification of the outcome of the request is sent to the one or more electronic devices. The one or more electronic devices may then grant or deny access to the devices based upon this notification.

In summary advantages of some embodiments of the present invention include an ability to efficiently provide access control to a plurality of devices and or accounts. By applying rules and usage information across the plurality of devices and or accounts convenient and centralised control such as by parents can be achieved. According to some embodiments rules can be easily structured to achieve usage rewards incentives or punishments associated with chores or other daily activities.

The above description of various embodiments of the present invention is provided for purposes of description to one of ordinary skill in the related art. It is not intended to be exhaustive or to limit the invention to a single disclosed embodiment. As mentioned above numerous alternatives and variations to the present invention will be apparent to those skilled in the art of the above teaching. Accordingly while some alternative embodiments have been discussed specifically other embodiments will be apparent or relatively easily developed by those of ordinary skill in the art. Accordingly this patent specification is intended to embrace all alternatives modifications and variations of the present invention that have been discussed herein and other embodiments that fall within the spirit and scope of the above described invention.

