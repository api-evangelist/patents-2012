---

title: Communication system, terminal, communication method and communication program for terminals while communicating with each other to identify the opposite party
abstract: There is provided a relay server  relaying communications between terminals using an application. Each terminal  includes a voice call means  which performs a voice call process, and a voice call information transmission means  which, when the voice call process is performed by the voice call means , transmits to the relay server  a voice call status change notice inclusive of information for identifying the terminal  and indicative of voice call status having been changed, the transmission being performed by communication using the application. Upon receipt of communication data through communication using the application from a communication source terminal , the relay server  identifies a communication destination terminal based on the voice call status change notice and transmits the communication data to the identified communication destination terminal.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09432795&OS=09432795&RS=09432795
owner: NEC Corporation
number: 09432795
owner_city: Tokyo
owner_country: JP
publication_date: 20120808
---
This application is a national stage application of International Application No. PCT JP2012 005027 entitled COMMUNICATION SYSTEM TERMINAL COMMUNICATION METHOD AND COMMUNICATION PROGRAM filed on Aug. 8 2012 which claims the benefit of the priority of Japanese Patent Application No. 2011 206344 filed Sep. 21 2011 the disclosures of each of which are hereby incorporated by reference in their entirety.

The present invention relates to a communication system a terminal a communication method and a communication program for terminals while communicating with each other to identify the opposite party.

With advances in cellular telephony it has become possible for the users of mobile terminals such as smartphones to install desired applications in their devices for application usage. These mobile terminals are equipped with the function to acquire an application by recognizing a terminal status change such as the start or end of a communication as an event.

There have been proposed remote collaboration systems whereby remotely located users collaborate on a task via a network. Also there have been proposed teleconferencing systems whereby such users refer to materials draw diagrams or exchange files at the same time.

With these teleconferencing systems users form a group for a certain period of time in advance or for the moment. The users belonging to the group exchange messages between them and the users terminals carry out processes corresponding to the exchanged messages to implement a teleconference. The members participating in the group and the period of time in which the group is being formed are managed as a session. Control is performed so that as long as the session is continued the members taking part in the session are allowed to exchange messages therebetween. A program running on the terminals operated by users of such a remote collaboration system has the function to transmit as data the operations carried out on each terminal to the other terminals so that the program having received the data executes what is described by the receive data on its own terminal.

In connection with these teleconferencing systems there have been proposed methods for designating a collaborative partner in linkage with a telephone.

Patent Literature 1 cited below describes a system that permits messages to be exchanged between client terminals in linkage with voice call connection status of their telephones.

Patent Literature 2 cited below describes a system that allows a private branch exchange to manage personal computers PCs linked with telephone numbers. With the system disclosed by Patent Literature 2 telephones having specific telephone numbers may initiate a voice call with each other via the private branch exchange. In turn the PCs corresponding to the telephones communicating with each other are notified of the start of an application by the private branch exchange. The notification causes the application to be started on the PCs corresponding to the telephones.

Patent Literature 3 cited below describes a system that offers a file sharing space to the users engaged in a voice call with each other via an exchange. The PCs utilized by these users are then used to store and acquire files to and from the file sharing space.

Patent Literature 4 cited below describes a system that generates a browser to browser session. With the system disclosed by Patent Literature 4 the home gateways HGW of the caller and receiver of each voice call send their own terminals telephone numbers and their call session IDs to a service server as voice call session information. The system uses a correspondence server to associate browser accesses with the voice call session information to generate a browser to browser session.

Patent Literature 5 describes a system in which Web browsers installed in a plurality of terminals exchange messages via a message relay server incorporated in a Web server whereby the individual Web browsers are synchronized.

The systems described in the above cited Patent Literature 1 2 and 3 require that in order to acquire voice call status of voice call terminals such as telephones an exchange controlling a voice call between these terminals transmit signals indicative of voice call status to another equipment. Generally the exchange controlling voice call terminals such as telephones handles complicated processes and is not prone to being additionally furnished with the function to provide voice call status notification. Furthermore there exist numerous exchanges that will incur high costs if they are to be furnished with such a function.

It is therefore an exemplary object of the present invention to provide a communication system a terminal a communication method and a communication program capable of implementing application to application communications in linkage with voice calls on terminals without the need for call status notification from circuit switching equipment.

According to the present invention there is provided a communication system including a relay server relaying communications between terminals using applications. Each of the terminals includes voice call means which performs a voice call process and voice call information transmission means which when the voice call process is performed by the voice call means transmits to the relay server a voice call status change notice inclusive of information for identifying the terminal and indicative of voice call status having been changed the transmission being performed by communication using the application. The relay server includes inter application communication means which upon receipt of communication data through communication using the application from a communication source terminal identifies a communication destination terminal based on the voice call status change notice and transmits the communication data to the identified communication destination terminal.

According to the present invention there is provided a communication system including a terminal which has functionality to make a voice call through user operation and to execute an application a terminal for use by a user as an opposite party circuit switching equipment which performs voice call control for terminals to make a voice call therebetween and a relay server which relays communications between applications on terminals. Each of the terminals includes voice call means which controls a voice call between users a voice call information linkage unit which acquires information indicative of voice call status from the voice call means and which transmits information indicative of the voice call status to the relay server and own ID storage means which stores a terminal identifier for identifying the terminal on which a voice call linkage application runs the voice call linkage application communicating with the application on the terminal of the opposite party via the relay server. The relay server includes voice call status reception means which receives a voice call status change notice giving notification of a change in the voice call status of a terminal voice call status storage means which stores information indicative of the voice call status of each of the terminals and inter application communication means which communicates with the voice call linkage application running on the terminals so as to relay communications between the applications.

According to the present invention there is provided a terminal including voice call means which controls a voice call between users a voice call information linkage unit which acquires information indicative of voice call status from the voice call means and which transmits the information indicative of the voice call status to a relay server and own ID storage means which stores a terminal identifier for identifying the terminal on which a voice call linkage application runs the voice call linkage application communicating with the application on the terminal of an opposite party via the relay server.

According to the present invention there is provided a communication method including when a voice call process is performed causing a terminal to transmit to a relay server a voice call status change notice inclusive of information for identifying the terminal and indicative of voice call status having been changed through communication using an application and upon receipt of communication data through communication using the application from a communication source terminal causing the relay server to identify a communication destination terminal based on the voice call status change notice and to transmit the communication data to the identified communication destination terminal.

According to the present invention there is provided a communication program causing a computer to execute when a voice call process is performed transmitting to a relay server a voice call status change notice inclusive of information for identifying terminals and indicative of voice call status having been changed through communication using an application.

According to the present invention it is possible to implement inter application communications in linkage with a voice call on terminals with no need for voice call status notification being sent from circuit switching equipment.

The first exemplary embodiment of the present invention is explained below with reference to the accompanying drawings.

As depicted in the communication system according to the invention includes a terminal another terminal and a relay server . The terminals and are connected in a manner communicable with each other via the relay server .

The terminals and are connected to the relay server via a network such as the Internet. Also the terminals and are connected to circuit switching equipment via a network such as a wired or wireless telephone network.

When a voice call is made between terminals a communication is performed therebetween via the telephone network that includes circuit switching equipment. When an inter application communication is performed between terminals the communication is carried out therebetween over the network.

The circuit switching equipment holds the ID or telephone number of each of the terminals. Upon receipt of a voice call start request or a voice call end request from one terminal to another the circuit switching equipment performs a process for establishing the voice call between the terminals. The circuit switching equipment is implemented using existing methods that are common knowledge and thus will not be explained further. Alternatively the circuit switching equipment may be included in the communication system.

The terminals and may be mobile phones or the like and are each equipped with functions to make voice calls and perform applications.

The terminal includes a voice call unit a voice call information linkage unit and an identification information storage unit . A voice call linkage application is an application that can be run on the terminal . The voice call unit and voice call information linkage unit are implemented by a CPU provided in the terminal .

The voice call unit performs a voice call process. The voice call unit is a common voice call device e.g. voice call circuit unit furnished in mobile phones and like terminals.

The voice call unit transmits a user s voice input through a microphone mounted on the terminal to the terminal of the opposite party via a wireless network or the like. Also the voice call unit receives a voice signal received from another terminal via the wireless network or the like and outputs the received voice signal to a speaker mounted on the terminal . This allows the user of the terminal to make a voce call with the user of another terminal. This voice call method is common knowledge and thus will not be explained in detail.

The voice call information linkage unit transmits voice call status of the voice call unit . Specifically the voice call information linkage unit transmits to the relay server a voice call status change notice indicative of a change that has occurred in the voice call status of the voice call unit .

The voice call information linkage unit includes voice call start detection means voice call end detection means and voice call status notification means .

The voice call start detection means detects the point in time at which a voice call is started by the voice call unit .

The voice call end detection means detects the point in time at which the voice call is terminated by the voice call unit .

It is assumed that the voice call start detection means and the voice call end detection means may be implemented using say an event detection method provided by API Application Programming Interface provided in the terminal .

The voice call status notification means transmits to the relay server a voice call status change detected by the voice call start detection means or by the voice call end detection means as a voice call status change notice. With this embodiment the voice call status notification means detects two points in time the start and the end of a voice call. However if it is possible to acquire voice call status other than the start or end of a voice call detection means for acquiring such voice call status may be added to the voice call status notification means so that the voice call status notification means may transmit that voice call status to the relay server .

The voice call linkage application transmits and receives communication data through the relay server to and from an application running on another terminal that is the opposite party. It should be noted that the wording the voice call linkage application transmits and receives actually means that the CPU performs the process in accordance with the application.

The identification information storage unit stores an identifier terminal identifier for identifying the terminal on which the voice call linkage application runs. Specifically the identification information storage unit is implemented by a memory or the like provided in the terminal .

The terminal includes a voice call unit and an identification information storage unit . A voice call linkage application is an application that can be run on the terminal .

The voice call unit and identification information storage unit in the terminal are structured the same as the communication unit and identification information storage unit in the terminal and thus will not be explained further. Also the voice call linkage application includes the same functionality as the voice cal linkage application .

Incidentally in the terminal may also include a voice call information linkage unit as with the terminal . Whereas depicts only two terminals and three or more terminals may operate at the same time.

The relay server mediates communications between applications running on terminals. The relay server may be implemented specifically by an information processing apparatus such as a PC.

The relay server includes voice call status reception means a voice call status storage device and inter application communication means . The voice call status reception means and the inter application communication means are implemented by the CPU furnished in the relay server .

The voice call status storage device holds the voice call status of each of the terminals. Specifically the voice call status storage device retains voice call status information indicative of voice call status of each terminal. The voice call status storage device is implemented specifically by a database device such as a magnetic disk device provided in the relay server .

The inter application communication means communicates with the voice call linkage applications running on the terminals and and mediates communications between the applications.

The user of the terminal operates it to start a voice call with the user of another terminal opposite party . In turn the voice call unit of the terminal carries out a voice call starting process step S in keeping with the user s operations. For example the user of the terminal operates a numeric keypad or other keys provided on the terminal or a numeric keypad or an address book display on the touch panel of the terminal to designate the telephone number of the opposite party s terminal before starting a voice call. Alternatively some other suitable method may be used to initiate a voice call. At this point the voice call unit transmits a voice call start request together with the telephone number to the circuit switching equipment . For this embodiment an example is used in which the user of the terminal makes a voice call with the user of the terminal .

Upon receipt of the voice call start request from the voice call unit of the terminal the circuit switching equipment calls up the terminal corresponding to the telephone number terminal designated in the voice call start request step S .

Where terminal users utilize an IP telephone service invoking and cutting off a voice call between terminals and responding to a voice call are performed using SIP Session Initial Protocol protocol H.323 protocol or the like. The procedures for invoking responding to and cutting off the voice call between terminals are well known and thus will not be explained further.

After step S the voice call start detection means in the voice call information linkage unit detects starting of the voice call by the communication unit as a voice call start event Yes in step S .

For example if the identifier telephone number of the terminal is 1001 and that of the terminal is 1002. what is detected here is a voice call start event indicating that a voice call has been initiated from 1001 to 1002. 

The voice call start detection means hands the voice call start event over to the voice call status notification means . In turn the voice call status notification means transmits a voice call start notification message indicative of the start of a voice call to the voice call status reception means in the relay server step S .

The data above indicates that a voice call has been initiated from the terminal having the identifier 1001 to the terminal with the identifier 1002. The identifier of the terminal having initiated the voice call is placed immediately after FROM and the identifier of the terminal of the opposite party is set immediately after TO . Alternatively the voice call start notification message may be in some other suitable format.

Upon receipt of the voice call start notification message step S the voice call status reception means in the relay server acquires the identifiers 1001 and 1002 of the terminals currently in a voice call with each other step S . And the voice call status reception means stores into the voice call status storage device voice call status information indicating that the terminals having the identifiers 1001 and 1002 are currently in a voice call with each other step S .

If the terminal is furnished with the voice call information linkage unit then the process of steps S through S is performed at the start of a voice call as with the terminal with preparations made for a communication between the voice call linkage applications. In this case the voice call start notification message in step S will be made of the following data 

When the user of the terminal operates it to start the voice call linkage application the terminal starts the voice call linkage application step S . For example the user of the terminal may start the voice call linkage application by clicking on an image indicative of the voice call linkage application on a display device attached to the terminal or by performing operations to select the item of the voice call linkage application from a menu screen displayed on the display device.

After getting started the voice call linkage application acquires from the identification information storage unit the identifier of the terminal terminal on which it runs step S . The voice call linkage application then transmits data to the relay server along with the acquired identifier step S . For example the identifier may be one described in a file or the like or the telephone number held in the voice call unit .

The data above indicates that a message Hello is transmitted from the terminal having the identifier 1001. The identifier of the transmission source terminal is set immediately after ID and the message is placed immediately after MESSAGE . Alternatively the data transmitted by the voice call linkage application may be in some other suitable format.

Upon receipt of the data transmitted by the voice call linkage application step S the inter application communication means of the relay server acquires the identifier 1001 included in the receive data.

The inter application communication means determines whether or not the voice call status information including the identifier acquired in step S exists in the voice call status storage device step S .

If there exists the voice call status information including the identifier acquired in step S Yes in step S the inter application communication means transmits the data received in step S to the terminal identified by another identifier included in that voice call status information step S . For example in the case of what is shown in the identifier 1001 is stored in the voice call status storage device in relation to the identifier 1002 so that the data is transmitted to the terminal identified by the identifier 1002. 

Alternatively the inter application communication means may at this point determine the address of the transmission destination terminal terminal based on correspondence information in which the identifiers of terminals are associated with their addresses. The correspondence information may be stored in advance in a storage unit not shown furnished in the relay server .

If there exists no voice call status information that includes the identifier acquired in step S No in step S the inter application communication means rejects transmission of the data step S .

Every time data is received from the voice call linkage application the inter application communication means repeats the process of steps S through S.

The preceding paragraphs explained the case where the voice call linkage application is started on the terminal . In like manner if the voice call linkage application is started on the terminal the terminal carries out the process of steps S through S and the relay server performs the process of steps S through S.

The user of the terminal performs operations to end the voice call by pressing a voice call end button furnished on the terminal for example. In response to the user s operations the voice call unit of the terminal carries out the process of terminating the voice call step S . At this point the voice call unit transmits a voice call end request to the circuit switching equipment .

Upon receipt of the voice call end request from the terminal the circuit switching equipment terminates the voice call with the terminal terminal corresponding to the telephone number designated by the voice call end request step S .

If the termination of the voice call by the voice call unit is detected as a voice call end event Yes in step S the voice call end detection means of the voice call information linkage unit hands the voice call end event over to the voice call status notification means . In turn the voice call status notification means transmits a voice call end notification message indicative of the end of the voice call to the voice call information reception means of the relay server step S .

The data above indicates that the voice call from the terminal having the identifier 1001 has ended. Alternatively the voice call end notification message may be in some other suitable format.

Upon receipt of the voice call end notification message step S the voice call information reception means of the relay server acquires the identifier 1001 of the terminal from the voice call end notification message step S . The voice call information reception means notifies the inter application communication means that the terminal terminal having the identifier 1001 has terminated the voice call.

Based on the notification received in step S the inter application communication means acquires the voice call status information including the identifier 1001 from the voice call status storage device step S . The inter application communication means then severs the connection between the terminals identified by the identifiers included in the acquired voice call status information i.e. between the terminal having terminated the voice call terminal and the terminal of the opposite party terminal step S . At this point the connection between the terminals may alternatively be cut off not immediately but after each of the terminals is notified of the end of the voice call.

After step S the inter application communication means deletes the voice call status information that includes the identifier 1001 from the voice call status storage device step S .

With this embodiment as explained above the voice call information linkage unit of the terminal acquires the voice call status of the terminal and transmits the acquired voice call status to the relay server whereby the relay server can acquire the voice call status of the terminals involved. This eliminates the need for getting the voice call status notification from the circuit switching equipment and allows the terminals and to implement inter application communication therebetween in linkage with the voice call. That is because terminal voice call status can be acquired between the applications there is no need to acquire voice call status by way of the circuit switching equipment .

Also with this embodiment the voice call linkage application running on the terminal currently in a voice call with another terminal requests the relay server to communicate with the opposite party and the relay server mediates communication with the application running on the terminal of the opposite party. As a result the applications of the terminals in a voice call with each other can communicate with each other.

Since there is no need to set up equipment such as HGW for acquiring voice call status the present invention can also be applied to the systems of users who have yet to install HGW or like equipment.

Furthermore because terminal voice call status can be acquired between the applications the costs required for modifying the circuit switching equipment or installing HGW can be saved.

Although the inter application communication means of this embodiment transmits data to the address of the transmission destination terminal based on the correspondence information the data may be transmitted alternatively using the connection established by the voice call linkage application for data reception. To implement such a configuration involves the voice call linkage application causing the inter application communication means to establish connection for data reception. Then the inter application communication means may transmit the data to the voice call linkage application through that connection. Where this configuration is in place there is no need to store the correspondence information beforehand in the relay server .

Also whereas this embodiment has been explained in connection with the case where the terminal transmits the voice call status change notice if the terminal is equipped with the voice call information linkage unit then the terminals and transmit a voice call status change notice each. In this case the relay server receives voice call status change notices from a plurality of terminals.

The relay sever may store voice call status information into the voice call status storage device only if the voice call start notification messages received from a plurality of terminals are the same in content. At this point if the voice call start notification messages are different in content then the relay server may reject subsequently received voice call start notification messages and delete the voice call status information stored in the voice call status storage device .

Alternatively regardless of the voice call start notification messages being the same or different in content the voice call status corresponding to each of the voice call start notification messages may be stored into the voice call status storage device as an independent item voice call status information .

If voice call end notification messages are received from a plurality of terminals and if the voice call status storage device does not store voice call status information corresponding to any of the voice call end notification messages i.e. if the information is already deleted the relay server may terminate its processing without doing anything.

The second exemplary embodiment of the present invention is explained below with reference to the accompanying drawings.

The voice call information linkage unit includes a status information storage unit in addition to the voice call start detection means voice call end detection means and voice call status notification means .

The status information storage unit retains information indicative of the voice call status of the voice call unit . Specifically the status information storage unit is implemented using a memory furnished in the terminal for example.

The other structures of the terminal in the second exemplary embodiment are the same as those of the terminal in the first exemplary embodiment.

The process of steps S through S is the same as that of steps S through S with the first exemplary embodiment and thus will not be discussed further.

Upon detecting a voice call start event the voice call start detection means stores the event into the status information storage unit as information indicative of the voice call status of the voice call unit step S and does not transmit a voice call start message for the moment.

When the user of the terminal operates it to start the voice call linkage application the terminal starts the voice call linkage application step S .

The voice call linkage application orders the voice call status notification means to transmit a voice call start notification message step S .

After step S the voice call status notification means transmits the information stored in the status information storage unit in step S to the relay server as the voice call start notification message step S .

Also upon receipt of the voice call start notification message after step S the voice call status reception means of the relay server carries out the process of steps S through S.

The process performed by the terminal at the end of a voice call is the same as the process of steps S through S in the first exemplary embodiment.

However upon detecting a voice call end event during the process of step S the voice call end detection means of the voice call information linkage unit deletes the information stored in the status information storage unit in step S. Alternatively step S and the subsequent steps may be arranged to be performed only while the voice call linkage application is being started.

This embodiment as explained above offers the same effects as those of the first exemplary embodiment. Also the embodiment allows the voice call start notification message to be transmitted to the relay server only if the voice call linkage application is started. This makes it possible to reduce the number of accesses during communication between the relay server and the terminals for example.

The above described exemplary embodiments also embrace the communication systems and terminals disclosed as follows 

 1 A communication system including a terminal which has functionality to make a voice call through user operation and to execute an application a terminal corresponding to the terminal in for use by a user as an opposite party circuit switching equipment corresponding to the circuit switching equipment in which performs voice call control for terminals to make a voice call therebetween and a relay server which relays communications between applications on terminals. The terminal includes voice call means which controls a voice call between users a voice call information linkage unit corresponding to the voice call information linkage unit of the terminal in which acquires information indicative of voice call status from the voice call means and which transmits the information indicative of voice call status to the relay server and own ID storage means corresponding to the identification information storage unit of the terminal in which stores a terminal identifier for identifying the terminal on which a voice call linkage application corresponding to the voice call linkage application in runs the voice call linkage application communicating with the application on the terminal of the opposite party via the relay server . The relay server includes voice call status reception means corresponding to the voice call status reception means of the relay server in which receives a voice call status change notice giving notification of a change in the voice call status of a terminal voice call status storage means corresponding to the voice call status storage device of the relay server in which stores the information indicative of the voice call status of each of the terminals and inter application communication means which communicates with the voice call linkage application running on the terminals so as to relay communications between the applications.

 2 A communication system in which the voice call information linkage unit includes voice call start detection means corresponding to the voice call start detection means of the voice call information linkage unit in which detects a point in time at which a voice call is started by the voice call means voice call end detection means corresponding to the voice call end detection means of the voice call information linkage unit in which detects a point in time at which the voice call is terminated by the voice call means and voice call information transmission means which transmits to the relay server a detected change in voice call status as the voice call status change notice.

 3 A communication system in which when a voice call is established by the voice call means with the terminal of the opposite party the voice call information linkage unit allows the voice call start detection means to detect the start of the voice call as a voice call start event using an application interface furnished in the terminal and output the voice call start event to the voice call information transmission means in which the voice call information transmission means transmits the as a voice call start notification message to the voice call information reception means of the relay server and in which the voice call status storage means of the relay server stores information indicative of voice call status.

 4 A communication system in which when a voice call is terminated by the voice call means the voice call information linkage unit allows the voice call end detection means to detect the end of the voice call as a voice call end event using an application interface furnished in the terminal in which the communication end detection means outputs the voice call end event to the voice call information transmission means in which the voice call information transmission means transmits the event as a voice call end notification message indicative of the end of the voice call to the voice call status reception means of the relay server and in which the voice call status storage means of the relay server deletes the information indicative of the voice call status.

 5 A communication system in which the voice call information linkage unit includes voice call information storage means corresponding to the status information storage unit of the terminal in which stores information indicative of voice call status of the terminal .

 6 A communication system in which when a voice call is established by the voice call means with the terminal of the opposite party the voice call information linkage unit allows the voice call start detection means to detect the start of the voice call as a voice call start event using an application interface furnished in the terminal in which the communication start detection means outputs the voice call start event to the voice call information storage means as information indicative of voice call status and in which the voice call information storage means stores information indicative of voice call status.

 7 A terminal including voice call means which controls a voice call between users a voice call information linkage unit which acquires information indicative of voice call status from the voice call means and which transmits the information indicative of the voice call status to a relay server and own ID storage means which stores a terminal identifier for identifying the terminal on which a voice call linkage application runs the voice call linkage application communicating with the application on the terminal of an opposite party via the relay server .

The above described exemplary embodiments further embrace the communication systems and terminals disclosed as follows 

A communication system in which when the voice call linkage application is started on the terminal the voice call information linkage unit allows the voice call information transmission means to transmit the information indicative of voice call status stored in the voice call information storage means to the voice call information reception means of the relay server as a voice call start notification message and in which the voice call status storage means of the relay server stores the information indicative of voice call status.

A communication system in which when a voice call is terminated by the voice call means the voice call information linkage unit allows the voice call end detection means to detect the termination of the voice call as a voice call end event using an application interface furnished in the terminal delete the information indicative of the voice call status stored in the voice call information storage means and output the voice call end event to the voice call information transmission means in which the voice call information transmission means transmits a voice call end notification message indicative of the end of the voice call to the voice call status reception means of the relay server and in which the voice call status storage means of the relay server deletes the information indicative of the voice call status.

A terminal in which the voice call information linkage unit includes voice call start detection means which detects a point in time at which a voice call is started by the voice call means voice call end detection means which detects a point in time at which the voice call is terminated by the voice call means and voice call information transmission means which transmits to the relay server a detected change in voice call status as a voice call status change notice.

A terminal in which when a voice call is established by the voice call means of the terminal with the terminal of the opposite party the voice call information linkage unit allows the voice call start detection means to detect the start of the voice call as a voice call start event using an application interface furnished in the terminal and transmit the voice call start event to the voice call information transmission means in which the voice call information transmission means transmits the event as a voice call start notification message to the voice call information reception means of the relay server and in which the voice call status storage means of the relay server stores information indicative of voice call status.

A terminal in which when a voice call is terminated by the voice call means the voice call information linkage unit allows the voice call end detection means to detect the end of the voice call as a voice call end event using an application interface furnished in the terminal in which the communication end detection means outputs the voice call end event to the voice call information transmission means in which the voice call information transmission means transmits the event as a voice call end notification message indicative of the end of the voice call to the voice call status reception means of the relay server and in which the voice call status storage means of the relay server deletes the information indicative of voice call status.

A terminal in which the voice call information linkage unit includes voice call information storage means which stores information indicative of the voice call status of the terminal .

A terminal in which when a voice call is established by the voice call means of the terminal with the terminal of the opposite party the voice call information linkage unit allows the voice call start detection means to detect the start of the voice call as a voice call start event using an application interface furnished in the terminal in which the communication start detection means outputs the voice call start event to the voice call information storage means as information indicative of voice call status and in which the voice call information storage means stores the information indicative of voice call status.

A terminal in which when the voice call linkage application is started on the terminal the voice call information linkage unit allows the voice call information transmission means to transmit the information indicative of voice call status stored in the voice call information storage means to the voice call information reception means of the relay server as a voice call start notification message and in which the voice call status storage means of the relay server stores the information indicative of voice call status.

A terminal in which when a voice call is terminated by the voice call means the voice call information linkage unit allows the voice call end detection means to detect the termination of the voice call as a voice call end event using an application interface furnished in the terminal delete the information indicative of voice call status stored in the voice call information storage means and output the voice call end event to the voice call information transmission means in which the voice call information transmission means transmits a voice call end notification message indicative of the end of the voice call to the voice call status reception means of the relay server and in which the voice call status storage means of the relay server deletes the information indicative of voice call status.

Whereas the present invention has been explained above in reference to some exemplary embodiments and execution examples these are not limitative of this invention. Various changes that can be understood by those skilled in the art may be made to the structures and details of the invention within the scope thereof.

This patent application claims priority to Japanese Patent Application No. 2011 206344 filed on Sep. 21 2011 the entire content of which is hereby incorporated by reference.

