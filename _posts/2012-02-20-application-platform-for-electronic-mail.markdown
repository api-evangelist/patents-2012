---

title: Application platform for electronic mail
abstract: Methods and apparatus, including computer program products, for an application platform for electronic mail. A method includes, in a network of interconnected computers, receiving a request in an email server to start up an email client, initializing an app platform client residing in the email client, receiving a request in the email server to open an email message, determining if there is an app associated with the email message, and rendering the app within the email message.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08930473&OS=08930473&RS=08930473
owner: Powerinbox, Inc
number: 08930473
owner_city: Cambridge
owner_country: US
publication_date: 20120220
---
The invention generally relates to networks and network applications and more specifically to an application platform for electronic mail email .

In general email is an exchange of computer stored messages by telecommunication. email messages are usually encoded in American Standard Code for Information Interchange ASCII text. However one can also send non text files such as graphic images and sound files as attachments sent in binary streams. email can also be exchanged between online service provider users and in networks other than the Internet both public and private.

Email can be distributed to lists of people as well as to individuals. A shared distribution list can be managed by using an email reflector. Some mailing lists enable a user to subscribe by sending a request to a mailing list administrator. A mailing list that is administered automatically is called a list server.

Email is one of the protocols included with the Transport Control Protocol Internet Protocol TCP IP suite of protocols. A popular protocol for sending email is Simple Mail Transfer Protocol SMTP and a popular protocol for receiving it is Post Office Protocol 3 POP3 .

In general an email message includes three components a message envelope a message header and a message body. The message header contains control information including minimally an originator s email address and one or more recipient addresses. Usually descriptive information is also added such as a subject header field and a message submission date time stamp.

A conventional email system operates using a mail user client which is a software application program used to send and receive emails. Examples include Outlook messaging and collaboration client and Hotmail web based email service by Microsoft Corporation Redmond Wash. Conventional mail user client do not allow significant interactivity with web servers over the World Wide Web. While it is common to embed Universal Resource Locator URL addresses within an email once a URL is selected the user is taken from the mail user client and the user accesses the selected web server URL via the user s browser. Further interaction with the selected URL is then performed by the browser outside of the mail user client.

The following presents a simplified summary of the innovation in order to provide a basic understanding of some aspects of the invention. This summary is not an extensive overview of the invention. It is intended to neither identify key or critical elements of the invention nor delineate the scope of the invention. Its sole purpose is to present some concepts of the invention in a simplified form as a prelude to the more detailed description that is presented later.

The present invention provides methods and apparatus including computer program products for an application platform for electronic mail email .

In general in one aspect the invention features a method including in a network of interconnected computers receiving a request in an email server to start up an email client initializing an app platform client residing in the email client receiving a request in the email server to open an email message determining if there is an app associated with the email message and rendering the app within the email message.

In another aspect the invention features a system including a processor a memory the memory comprising an operating system and an application process the application process including receiving a request in an email server to start up an email client initializing an app platform client residing in the email client receiving a request in the email server to open an email message determining if there is an app associated with the email message and rendering the app within the email message.

Other features and advantages of the invention are apparent from the following description and from the claims.

The subject innovation is now described with reference to the drawings wherein like reference numerals are used to refer to like elements throughout. In the following description for purposes of explanation numerous specific details are set forth in order to provide a thorough understanding of the present invention. It may be evident however that the present invention may be practiced without these specific details. In other instances well known structures and devices are shown in block diagram form in order to facilitate describing the present invention.

As used in this application the terms component system platform module and the like can refer to a computer related entity or an entity related to an operational machine with one or more specific functionalities. The entities disclosed herein can be either hardware a combination of hardware and software software or software in execution. For example a component may be but is not limited to being a process running on a processor a processor an object an executable a thread of execution a program and or a computer. By way of illustration both an application running on a server and the server can be a component. One or more components may reside within a process and or thread of execution and a component may be localized on one computer and or distributed between two or more computers. Also these components can execute from various computer readable media having various data structures stored thereon. The components may communicate via local and or remote processes such as in accordance with a signal having one or more data packets e.g. data from one component interacting with another component in a local system distributed system and or across a network such as the Internet with other systems via the signal .

In addition the term or is intended to mean an inclusive or rather than an exclusive or. That is unless specified otherwise or clear from context X employs A or B is intended to mean any of the natural inclusive permutations. That is if X employs A X employs B or X employs both A and B then X employs A or B is satisfied under any of the foregoing instances. Moreover articles a and an as used in the subject specification and annexed drawings should generally be construed to mean one or more unless specified otherwise or clear from context to be directed to a singular form.

As shown in an exemplary network includes a user computing device linked to a network of interconnected computers e.g. Internet . Although the user computing device is shown to be linked to the Internet as a wired communication connection other linking mechanisms can employed such as wireless communication connections. The exemplary network also includes as email server and an application platform server .

Example user computing devices include a desktop personal computer PC a laptop computer a netbook computer a smartphone a personal data assistant a tablet PC a smart TV and so forth. The user computing device includes a processor and a memory . The memory includes an operating system OS such as Linux or Android and a browser process . In general the browser process is software that accesses and displays pages and files on the world wide web WWW . Example browsers include Mozilla Firefox Microsoft Internet Explorer and Apple Safari .

As shown in the email server includes a processor and a memory . The memory includes an operating system such as Linux or Windows and an electronic mail email application email client . Example email clients include Yahoo Gmail Hotmail Outlook and so forth. The browser process can load the email client for display on the user computing device . The email client includes an application platform app platform client that the enables applications apps to run within the email client and is adaptable to all web based desktop and mobile email clients. In general an app platform client is a software program that extends the capabilities of the email client by communicating with an application process residing in the application platform server and the email client . The app platform client may be implemented as an add in add on plug in code library and so forth.

The application platform server includes a processor and a memory . The memory includes an operating system the application process and an application toolkit . The application process executes any number of apps over an application programming interface API linked to the application platform app platform client . The API is the set of protocols that enable email clients to query the application platform server to determine if there are compatible apps for a given email. In general the application platform server serves as the central location for aggregating apps. In addition app developers can submit their apps to the application platform server over an app creation API which is a the set of protocols and tools that enable app developers to create modify and submit their apps to the application platform server .

The app platform client resides within the email client and anytime the email client is opened the app platform client queries the application process to determine whether there are any apps to execute within the email client. If there are apps available for a particular email each app including a base server path and a view path a list of those apps are displayed within the email client . The base server path provides a location e.g. URL of the app and the view path provides a default placement for the app within an email. An address of an app is a combination of the base server path and the view path. The email client takes the URL of the app and places it within the particular email as specified by the view path. Example apps include a Facebook app a Linkedin app a Twitter app a Southwest Airlines app and so forth. Other example apps can include email marketing services and or agencies apps. In implementations the apps reside or are hosted on third party servers such as a Facebook server not shown . In general an originator owner of an app e.g. Facebook is responsible for hosting the app.

If an app is available the app is displayed within the email client . If the app supports positional placement within the email client a position of the executing app within the email client may be adjusted i.e. the user may position the app within the email client to suit their preferences e.g. top bottom left or right. In addition the user may replace the app for the email client . The application platform app platform client is flexible enough to enable many varied placements and new placements can be added at any time. For example if the app supports maximization and minimization a user may choose to have the app execute in a minimized view at all times. And an app may be designed to execute in a minimized view at all times as a default.

In another example the user may want an app to be persistent and run all the time. In a specific example the user controls whether the app is pinned to run all the time or not pinned to run only when asked by the user.

Multiple apps may run in a single email these multiple apps may initially be displayed within the email as icons.

In summary each app can specify one or more placements within an email message. The placements are displayed to the user and the user can switch between them. Placements can include mini replace inline prepend append before after hover horizontal vertical persistent pinned minimize. Placement triggers include both static and hover. Placements also enable multiple email apps from different sources to be rendered at the same time.

As shown in an exemplary replacement illustrates an app placement when an app can fully replace the content of a legacy email without any loss of information. In this example the app is meant to replace the legacy email while providing additional dynamic interactive content. For example the replacement placement when a photo comment email from Facebook is replaced with an app that shows the photo along with a comment that a user can reply to.

As shown in an exemplary inline replacement illustrates when an app is used to replace certain parts of a legacy email with dynamic interactive content. For example this placement can be used when the app is providing only a few points of interaction that fit within the content of the legacy email. For example this placement can be used when replacing a picture of a YouTube video with the actual YouTube video.

As shown in an exemplary horizontal placement illustrates when an app the is not replacing the content of an email but instead is providing additional dynamic interactive content.

As shown in an exemplary vertical placement illustrates when an app is not replacing the content of an email but instead is providing accompanying functionality.

As described above an application toolkit SDK and the app creation API enables developers to create apps. The SDK executes a series of wysiwyg interfaces to enable app creation by prompting an app developer for information. An app developer can also create an app without the SDK .

The following is an example of code placed inside an email to indicate a Youtube app and its specification 

Basic information for an app includes an ID a Name a Version a Description an IconURL a LargeIconURL and a ServerURL. A main extractor includes input information filter information and pattern information. An example first view includes an ID path and default placement. An example placement includes a type a width and a height.

As shown in the application process includes receiving a request in an email server to start up an email client.

Process receives a request in the email server to open an email message and determines if there is a compatible app associated with the email message.

Determining can include looking for an app specification embedded inside the email message. Determining can include analyzing a body or header of the email message.

Rendering can include retrieving the app according to an app specification comprising view paths and associated placements and placing the app in the email message according to the app specification. An app creator may be required to submit the app for approval and available based on the permission settings for the app.

The app platform client can enable HTML4 HTML5 and its successor content herein referred to HTMLx to execute inside an email.

The apps can include video games shopping for goods services sharing with their social network music rental goods information retrieval learning surveys event scheduling advertisement interaction and so forth.

The app platform client further can include measuring time spent viewing an email and recording and analyzing actions performed in the email.

A view can contain a placement of the app within the email message. The placement can be miniaturization replacement inline horizontal vertical persistent minimized pinned and so forth.

Determining if there is an app can include searching a list of apps specifications residing in an app server.

The app specification can include an identification ID a name a version a description an IconURL a LargeIconURR and a ServerURL views paths placements manipulations heights and widths selectors wrappers extractors outputs parameters and so forth.

An input for the extractors output can be a sender HTML body plain text body subject links hrefs and so forth.

The app specification can be assembled from pre existing widgets and or generated automatically based on parameters.

The app can include different specifications viewable by different people based on their authentication.

The app can run in different emails by having different views be modified on static dynamic or hover triggers in a body of the email resize itself automatically based on the dimensions of the content changing or extract information from the email to pass as parameters to initialize itself.

In implementations the app specification can include a static version of the app that is displayed if the app is unavailable.

The email message can include an information button pertaining to the app platform client. The information button can be generated automatically based on parameters

Determining if there is one or more app associated with the email message can include displaying a list of the one or more apps and receiving an indications of which app to render.

An inline placement of the one or more apps may altered using append prepend replacewith after and or before.

As shown in an exemplary user interface UI illustrates generating an app specification from parameters. The UI includes static HTML for the app generated from parameters . The UI includes a section in which to specify text for an email button the parameters for the app and the app embedded code including the button and app specification. The button automatically generates the embedded code.

As shown in an exemplary UI displaying an app specification includes a section to provide general information about the app. This general information includes for example a name of the app a description of the app a small icon and a large icon for the app a base URL for a server that hosts the app and an indication if the app requires embedded code.

A setup for global extractors includes an input filter for the extractor a filter type for the input a pattern to match on an input and indication whether an extractor is required and an indication that the data extracted should be marked as output.

A setup for views includes a server path for the view an ID of the view and a default placement for the view . A setup for placement includes type height HTML wrapper width manipulation type and selector .

As shown in a UI illustrates an email button and includes text for the email button the embedded code for the email button and a button to generate the embedded code.

As shown in an exemplary UI illustrates an exemplary display of a list of apps including a list of apps that are only present on the local machine and a list of apps from the application server.

Various implementations of the systems and techniques described here can be realized in digital electronic circuitry integrated circuitry specially designed ASICs application specific integrated circuits computer hardware firmware software and or combinations thereof. These various implementations can include implementation in one or more computer programs that are executable and or interpretable on a programmable system including at least one programmable processor which may be special or general purpose coupled to receive data and instructions from and to transmit data and instructions to a storage system at least one input device and at least one output device.

These computer programs also known as programs software software applications or code include machine instructions for a programmable processor and can be implemented in a high level procedural and or object oriented programming language and or in assembly machine language. As used herein the terms machine readable medium computer readable medium refers to any computer program product apparatus and or device e.g. magnetic discs optical disks memory Programmable Logic Devices PLDs used to provide machine instructions and or data to a programmable processor including a machine readable medium that receives machine instructions as a machine readable signal. The term machine readable signal refers to any signal used to provide machine instructions and or data to a programmable processor.

To provide for interaction with a user the systems and techniques described here can be implemented on a computer having a display device e.g. a CRT cathode ray tube or LCD liquid crystal display monitor for displaying information to the user and a keyboard and a pointing device e.g. a mouse or a trackball by which the user can provide input to the computer. Other kinds of devices can be used to provide for interaction with a user as well for example feedback provided to the user can be any form of sensory feedback e.g. visual feedback auditory feedback or tactile feedback and input from the user can be received in any form including acoustic speech or tactile input.

The systems and techniques described here can be implemented in a computing system that includes a back end component e.g. a data server or that includes a middleware component e.g. an application server or that includes a front end component e.g. a client computer having a graphical user interface or a web browser through which a user can interact with an implementation of the systems and techniques described here or any combination of such back end middleware or front end components. The components of the system can be interconnected by any form or medium of digital data communication e.g. a communication network . Examples of communication networks include a local area network LAN a wide area network WAN and the Internet.

The computing system can include clients and servers. A client and server are generally remote from each other and typically interact through a communication network. The relationship of client and server arises by virtue of computer programs running on the respective computers and having a client server relationship to each other.

The foregoing description does not represent an exhaustive list of all possible implementations consistent with this disclosure or of all possible variations of the implementations described. A number of implementations have been described. Nevertheless it will be understood that various modifications may be made without departing from the spirit and scope of the systems devices methods and techniques described here. For example various forms of the flows shown above may be used with steps re ordered added or removed. Accordingly other implementations are within the scope of the following claims.

