---

title: System-initiated interactions and notifications in a chat information system on mobile devices
abstract: A method for push interaction with a mobile device using a chat interface includes establishing a chat protocol connection between a server and the mobile device, wherein the chat protocol format is used as a part of the push protocol; generating an event on the server; sending a push protocol command relating to the event from the server to the mobile device using the chat protocol connection; in the background, processing the chat protocol request that was packaged within the push protocol command; receiving the response from the mobile device through the chat protocol connection using the pull protocol mode; sending media contents from the server to the client using pull protocol mode; and displaying the media contents on the mobile device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09386113&OS=09386113&RS=09386113
owner: Speaktoit, Inc.
number: 09386113
owner_city: Palo Alto
owner_country: US
publication_date: 20121230
---
This application is a non provisional application of U.S. Provisional Patent Application No. 61 581 808 filed Dec. 30 2011 which is incorporated by reference herein in its entirety.

The present embodiments relate to the field of artificial intelligence. More particularly the present embodiments relate to chat information systems using natural language and in particular to chat information system activated interactions by using notifications for portable electronic devices that are connected to Internet via mobile or wireless networks.

Chat information systems also commonly called chatbots interacting with users in natural language typically operate in the pull mode where interactions are initiated by chat information system users. For example user may greet chatbot or ask chatbot a question.

Chatbots operating on network connected portable electronic devices such as smartphones could interact with users using a push approach. In the push approach interactions with users are initiated by chatbot.

Examples of push interactions include the following. First if chatbot is user profile aware and is connected to user s email and calendar systems it could remind the user about meetings appointments and incoming e mail messages. Second chatbot could also perform scheduled repetitive tasks such as wake user up every day at 7 00 AM or deliver daily news. Furthermore chatbot could use location of user s mobile device to modify conversation in a location specific way. For example by knowing user s time zone chatbot could suspend push messages during nighttime. Awareness about current location could allow chatbot to suggest interesting things to do or visit near the current location.

Standard system interfaces such as mobile OS push notifications user interfaces as well as chatbot application specific user interface could be used to notify users of incoming conversation requests from a chatbot.

Therefore there is a need for new types of user interfaces system architecture and functions to support system initiated user interaction with chat information systems working on portable electronic devices.

The task of implementing system initiated interactions on portable electronic devices faces problems related to embodiments of system architecture functions and user interfaces due to the limited space available on mobile devices screens unreliable network connectivity and availability of additional mobile device functions such as the Global Positioning System GPS .

Accordingly the present invention is related to a system and method for system initiated chat interactions using push mechanism that substantially obviates one or more of the disadvantages of the related art.

The present embodiments are a set of methods architecture processes scenarios and graphical user interfaces reducing or eliminating problems related to implementation of system initiated interactions and notifications functionality in chat information systems on portable electronic devices connected to Internet via mobile or wireless network.

In one embodiment there is provided a method for push interaction with a mobile device using a chat interface includes establishing a chat protocol connection between a server and the mobile device wherein the chat protocol format is used as a part of the push protocol generating an event on the server sending a push protocol command relating to the event from the server to the mobile device using the chat protocol connection in the background processing the chat protocol request that was packaged within the push protocol command receiving the response from the mobile device through the chat protocol connection using the pull protocol mode sending media contents from the server to the client using pull protocol mode and displaying the media contents on the mobile device.

Additional features and advantages of the invention will be set forth in the description that follows and in part will be apparent from the description or may be learned by practice of the invention. The advantages of the invention will be realized and attained by the structure particularly pointed out in the written description and claims hereof as well as the appended drawings.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are intended to provide further explanation of the invention as claimed.

Reference will now be made in detail to embodiments examples of which are illustrated in the accompanying drawings. In the following detailed description numerous specific details are set forth in order to provide a thorough understanding of the present invention. However it will be apparent to one of ordinary skill in the art that the present invention may be practiced without these specific details. In other instances well known methods procedures components and circuits have not been described in detail so as not to unnecessarily obscure aspects of the embodiments.

User interacts with the Chat Information System Client Interface with natural language typing of voice . Chat Information System maintains User Profiles to store user preferences and user specific information such as history of user s requests.

External Data and Service providers may supply notification information in the form of push or pull application programming interfaces APIs . In the case if the External Data or Service Provider Supports push mode of interactions the Server registers Notification Listener Web service or other application interface with the External Data or Service Provider . When there is an update notification the Provider invokes the Notification Listener . In term the Notification Listener schedules a Scheduled Task with the Scheduler to initiate delivery of the notification to the client via Internal or External Push Server . Alternatively the Notification Listener could interact directly with the Internal or External Push Server .

The Client notifies the user about the event e.g. new email or calendar appointment . When the user opens notification the Client Interface initiates conversational sequence to deliver notification details. For example the Client Interface notifies the user about the new email the user opens the notification. The client initiates the dialog with the Chat Information System Server to read the text of the email to the user and allow the user to respond to the email with the help of the chat information system.

If external data provider does not support push type interactions the Server schedules tasks in the Scheduler to check updates in the External System . The Scheduler initiates Scheduler Tasks based on the schedule. Scheduler Task connects to the External Data and Service Provider s and retrieves information updates new data. The Scheduled Task calculates if the user needs to be notified about the data update. The Scheduled Task initiates a push notification to the user using the Push Server . Notification is displayed to the user either using the portable electronic device s operating system capabilities or by the Chat Information System Client Interface . If the user opens the notification the Client may initiate a dialog between the system and the user to retrieve notification details.

In certain cases Scheduled Tasks could be running on the Client Interface and periodically check the Chat Information System Server for updates.

Push protocols typically have a payload field that could be used by application to transfer application specific format. In the case of the Client Interface Chat Information System Server interactions the push payload field contains data formatted using the pull chat protocol format. It could contain for example session identifier text response voice response data payload including new list of system variables and commands.

The system asks for the user s confirmation to enable push notifications for the connected service step . The user confirms step .

The server may deliver notifications based on user s profile and usage information. The following scenarios are possible 

1 The server uses user s location information obtained from the mobile device to trigger and or filter notifications. For example the user asks the system to remind him to buy milk. The system monitors user s location and delivers the notification when the user is close to a grocery store.

2 The server uses User s time zone local time information to deliver notifications at a particular time period. For example the user asks the system Wake me up at 8 AM tomorrow . By knowing user s time zone the system will push a notification at 8 AM tomorrow in user s time. Additionally time zone information could be used to deliver notifications only during specific time of the day. For example the user may choose to receive notifications from the system only from 8 AM to 8 PM.

3 User s profile information including but not limited to gender date of birth language contact list information about connected third party services could be used to customize notification scope timing triggers and content.

For example the user has connected the chat information system to an email system. The user identifies certain contacts in his contact list as important. The system will notify the user about new emails only from important contacts.

4 The System can use information about Chat Information Client usage such as installation date and time client usage frequency client usage patterns to deliver notifications. For example if the user has not launched the client in 10 days the system may send a reminder to the user.

5 The System can support one time and recurring scheduled notifications. In a one time notification the user will ask the system to deliver notification once. For example Wake me up at 8 AM tomorrow Remind me to pick up dry cleaning on the 19th . In a recurring notification the user asks the system to deliver notifications on schedule. For example Send me weather forecast and a digest of the latest news every morning at 9 AM .

6 The system may adjust notification frequency depending on user s reaction to notifications. For example if the user dismisses all notifications sent by the system the system may decrease the frequency of notifications.

7 The system may use combined information retrieved from multiple external services and data from the portable electronic device e.g. from device s GPS to trigger notifications. For example user s profile is connected to a calendaring system and the user has a meeting appointment at LOAM. Current time is 9.30 AM. Based on user s location obtained from portable electronic device s location service and traffic conditions it will take the user an estimated 45 minutes to get from the current location to the meeting location. The system could a notify the user that he may be late for the meeting b suggest rescheduling the meeting.

8 In example 7 by having access to the user calendar the system could notify other participants of the meeting that the user may be running late. If the other participants of the meeting do not have Chat Information System Client installed of their portable electronic devices notifications could be delivered via email instant message or other type of electronic communications.

9 Chat information system client could monitor various services of user s portable electronic devices including but not limited to location services GPS short message service SMS Bluetooth service e mail service and initiate interactions based on events from such services. For example the Client could read incoming email or short message service messages to the user using text to speech technology and allow the user to answer the messages.

10 Chat information system service could use notification mechanism to deliver information about system updates maintenance important notifications etc. to a broad range of users multiple users.

1 Push notification as supported by mobile platforms. The System server sends a notification to user s mobile device. Notification is shown by the device s operating system to the user. Notification may be accompanied by notification title notification text and notification sound. When the user chooses to open notification the Chat Information System Client Interface is launched.

If the Chat Information System Client Interface application is already running in foreground on user s mobile device the notification could be shown as 

3 Notification may be delivered as phone call to user s mobile device. After notification text is read to the user via Text to Speech user may continue interacting with the system via voice based chat interface in the scope of the same phone call.

4 If the user is already in the context of the Chat Information System Client Interface the interface is running in the foreground of the portable electronic device the notification is displayed in the context of the Chat Information System Client Interface.

Events that are raised by the external systems and the portable electronic device may have different priorities which could determine the method of notification delivery. For example if the chat information system urgently needs to initiate conversation with the user interactions could be initiated via a phone call SMS. If the notification is not urgent the notification could be shown next time the user opens the application.

During the user initiated interactions the System operates in a request response mode see . The Client Interface sends a request to the Chat Information System Server which contains 

 1 Session identifier session is established using a system dependent protocol for example HTTP based authentication .

 2 Request type. Types of request may include regular and background . Regular requests are sent to the Chat Information System Server when a user performs an explicit action in the Client Interface such as initiating a request to the Chat Information System Server via typing or voice. Background requests could be sent from the Client Interface to the Chat Information System Server automatically e.g. to periodically push client interface variables such as geolocation to the Chat Information System Server .

 3 Voice input and text input the request may contain either voice or text input. If the request contains voice input speech recognition is performed on the chat information system server directly or using a third party voice recognition service. The request contains text if voice recognition is performed on the Client Interface .

 a System variables the client could have a set of client interface specific variables that need to be communicated to the Chat Information System Server for example version of the client interface. A subset of such variables could be defined and re defined in server responses.

 b Data if Client Interface is responding to a command from the Chat Information System Server it could pass results of the command execution on the client interface to the server. An example of such command is the geolocation command. If the Chat Information System Server instructs the Client Interface determine geolocation the Client Interface performs geolocation operation using built in capabilities and passes results latitude longitude or an error code to the Chat Information System Server in the data field of the response.

 1 Session identifier session is established using a system dependent protocol for example HTTP based authentication . This parameter is optional.

 b A list of commands that need to be executed on the Client Interface with all required command parameters.

During the system initiated interaction a client specific push mechanism for example Google GCM Apple Push Notifications periodic pull from the client push via persistent network connection from the server to the client is used. The push message to the client interface contains 

1 Chat Information System Server initiates a push to the Client Interface with the command to send a background request to the server What is the weather like 

2 The Client Interface receives the push message in the background and activates itself on the device starts running in the foreground 

3 The Client Interface sends a background request to the Chat Information System Server with the question What is the weather like 

4 Chat Information System Server responds with a regular response format described above with the current weather conditions and weather forecast.

Use of server response format in the system initiated communications allows simplifying client implementation and access full set of client interface capabilities via client commands.

When the Chat Information System Server initiates an interaction with the user via the Client Interface it frequently needs to generate a human readable text response message that is tailored to the user s needs. When the message is generated the following needs to take into account 

 1 Knowledge of the user s profile language preferences location communication preferences e.g. user prefers not to be contacted at night time 

In order to leverage this information and context Scheduled Tasks executed on the Scheduler contain a command text and user account identification information that is used to initiate a request on the chat information system server . The sequence of interaction is as follows 

2 Scheduler schedules a Scheduled Task with an appropriate execution schedule user and context information.

5 The request is processed in the Chat Information System similar to processing of the regular request from Client Interface . Chat Information System uses user account and profile information including user preferences to execute the request and generate a response. Response contains major response fields described in including response text voice response new list of system variables and commands.

7 Scheduled Task retrieves Scheduled Task analyzes to which of user s device s the push should be sent to.

9 Internal or External Push Server delivers the push to one or more if the User has multiple Client Interfaces .

An example of push communications and Scheduler Chat information system interactions is shown below. One of the functionalities of the chat information system can be to provide daily briefings to the user which might contain current weather and weather forecast the user s agenda for the day and top news headlines. In this example it is assumed that the user is typing the input text in. Voice enabled interactions will behave in a similar way.

1. The user asks the system via the Client Interface to schedule a daily brief Please schedule a daily brief for me . Client interface sends a Request object contains 

4. After receiving this request Chat Information System Server instructs the Scheduler to schedule daily brief for the user. The Scheduler creates a Scheduled Task that contains 

6. The Scheduled Task establishes communication with the Chat Information System and sends a request on behalf of the user from the Scheduled Task . Scheduled Task uses Chat Information System to prepare push text which is tailored to the user.

The Scheduled task passes the user ID to the Chat Information System to process these requests on User s behalf. The Chat Information System provides a response object that needs to be sent to the user. Scheduled Task initiates push communication to the user via External or Internal Push Server . The push request contains 

The Client Interface displays response text Preparing your daily brief . . . and processes payload of the push request and executes the command to send background request to the server. The request is sent silently in the background to the Chat Information System Server without showing the request details to the user. The request contains 

Starting at this point the interactions moves from the push mode to the regular request response protocol.

9. The Chat Information System Server processes the request and first retrieves user s agenda. The Session ID or User ID if request is made directly from a Scheduled Task is used to retrieve user profile which contains keys sessions that enable Server s communications with External Data and Service Providers such as calendar services. The requests to calendar services are executed on user s behalf. The System retrieves calendar information and send it back to the user. The response contains 

10. The Client Interface receives and displays the result to the User. After waiting for 8 seconds as specified in the command Delay parameter Client Interface initiates a background request to the server with the text Show weather .

11. The Chat Information System Server processes the request and issues a response containing a command to determine user s location. The response contains 

12. The Client Interface receives the response and initiates geolocation determination. After geolocation is determined Client Interface sends a background request to the Chat Information System Server containing 

13. The Chat Information System Server processes the location data received in the client response and contacts External Data and Service Providers to get weather information for specified location. After obtaining weather information Chat Information System issues a response to the Client Interface containing 

14. The client interface displays the weather information from the response and after waiting 10 seconds issues a background request to retrieve top news. Processing of top news is analogous to prior examples.

With reference to an exemplary system for implementing the invention includes a general purpose computing device in the form of a personal computer or server or the like including a processing unit a system memory and a system bus that couples various system components including the system memory to the processing unit . The system bus may be any of several types of bus structures including a memory bus or memory controller a peripheral bus and a local bus using any variety of bus architectures. The system memory includes read only memory ROM and random access memory RAM . A basic input output system BIOS containing the basic routines that help to transfer information between elements within the personal computer such as during start up is stored in ROM .

The personal computer may further include a hard disk drive for reading from and writing to a hard disk not shown in the figure a magnetic disk drive for reading from or writing to a removable magnetic disk and an optical disk drive for reading from or writing to a removable optical disk such as a CD ROM DVD ROM or other optical media. The hard disk drive magnetic disk drive and optical disk drive are connected to the system bus by a hard disk drive interface a magnetic disk drive interface and an optical drive interface respectively.

The drives and their associated computer readable media provide a non volatile storage of computer readable instructions data structures program modules subroutines such that may be used to implement the steps of the method described herein and other data for the personal computer .

Although the exemplary environment described herein employs a hard disk a removable magnetic disk and a removable optical disk it should be appreciated by those skilled in the art that other types of computer readable media that can store data accessible by a computer such as magnetic cassettes flash memory cards digital video disks Bernoulli cartridges random access memories RAMs read only memories ROMs and the like may also be used in the exemplary operating environment.

A number of program modules may be stored on the hard disk magnetic disk optical disk ROM or RAM including an operating system e.g. Windows 2000 . The computer includes a file system associated with or included within the operating system such as the Windows NT File System NTFS one or more application programs other program modules and program data . A user may enter commands and information into the personal computer through input devices such as a keyboard and pointing device .

Other input devices not shown may include a microphone joystick game pad satellite dish scanner or the like. These and other input devices are often connected to the processing unit through a serial port interface that is coupled to the system bus but may be connected by other interfaces such as a parallel port game port or universal serial bus USB . A monitor or other type of display device is also connected to the system bus via an interface such as a video adapter . In addition to the monitor personal computers typically include other peripheral output devices such as speakers and printers.

The personal computer may operate in a networked environment using logical connections to one or more remote computers . The remote computer or computers may be represented by a personal computer a server a router a network PC a peer device or other common network node and it normally includes many or all of the elements described above relative to the personal computer although only a memory storage device is illustrated. The logical connections include a local area network LAN and a wide area network WAN . Such networking environments are commonplace in offices enterprise wide computer networks Intranets and the Internet.

When used in a LAN networking environment the personal computer is connected to the local network through a network interface or adapter . When used in a WAN networking environment the personal computer typically includes a modem or other means for establishing communications over the wide area network such as the Internet. The modem which may be internal or external is connected to the system bus via the serial port interface .

In a networked environment program modules depicted relative to the personal computer or portions thereof may be stored in the remote memory storage device. It will be appreciated that the network connections shown are exemplary and other means of establishing a communications link between the computers may be used. Such computers as described above can be used in conventional networks e.g. the Internet local area networks regional networks wide area networks and so forth. These networks can link various resources such as user computers servers Internet service providers telephones connected to the network and so on.

Having thus described a preferred embodiment it should be apparent to those skilled in the art that certain advantages of the described method and apparatus have been achieved. It should also be appreciated that various modifications adaptations and alternative embodiments thereof may be made within the scope and spirit of the present invention. The invention is further defined by the following claims.

