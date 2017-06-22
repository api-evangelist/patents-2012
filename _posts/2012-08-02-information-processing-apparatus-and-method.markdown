---

title: Information processing apparatus and method
abstract: A computer determines whether destination information is included in permission target information. The destination information indicates a destination to which a file stored in a storage device is transferred. The permission target information includes information indicating a target permitted to access the file. The computer prompts before the file is transferred, upon determining that the destination information is not included in the permission target information, a user to input whether to permit the transfer. The computer adds the destination information to the permission target information upon receiving, via an input device, a permission input for permitting the transfer. The computer transfers the file upon receiving the permission input.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09141941&OS=09141941&RS=09141941
owner: FUJITSU LIMITED
number: 09141941
owner_city: Kawasaki
owner_country: JP
publication_date: 20120802
---
This application is based upon and claims the benefit of priority of the prior Japanese Patent Application No. 2011 217795 filed on Sep. 30 2011 the entire contents of which are incorporated herein by reference.

With the increased computerization of society protection technologies for suppressing leakage of information have become increasingly important. Various protection technologies for information leakage suppression have been hitherto proposed.

For example in some cases a recipient of an electronic mail with a Uniform Resource Locator URL included may transfer the electronic mail to a third party. In order to increase convenient access to the destination referred to by the URL without reducing information leakage security the following technology has been proposed.

Specifically this technology is one of shared file access management methods in shared file access management systems that manage access to shared files. According to this shared file access management method a processing apparatus stores in a storage device a shared file access privileges granting condition indicating a condition for granting access privileges to a shared file to be accessed via a URL in an electronic mail. According to this shared file access management method furthermore when transferring an electronic mail the processing apparatus reads from the storage device a shared file access privileges granting condition for granting access privileges to a shared file to be accessed via a URL in the electronic mail. When the destination to which the electronic mail is to be transferred is a user who satisfies the read shared file access privileges granting condition the user is granted access privileges to the shared file.

According to an aspect of the present invention a computer determines whether destination information is included in permission target information. The destination information indicates a destination to which a file stored in a storage device is transferred. The permission target information includes information indicating a target permitted to access the file. The computer prompts before the file is transferred upon determining that the destination information is not included in the permission target information a user to input whether to permit the transfer. The computer adds the destination information to the permission target information upon receiving via an input device a permission input for permitting the transfer. The computer transfers the file upon receiving the permission input.

The object and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the invention as claimed.

Excessive constraints of operations performed by users to address information leakage due to carelessness may impair the convenience of users resulting in a risk of users operation efficiency being reduced. In addition when a mechanism for setting an information leakage suppression policy in advance is employed a considerable burden may be placed on an administrator or any other user for setting the policy. That is depending on the situation users may suffer some detriment such as reduced convenience or having the burden of setting the policy in exchange for suppression of information leakage due to carelessness.

Embodiments will be described in detail hereinafter with reference to the drawings. The description will be given in the following order.

First features common to first to third embodiments will be described with reference to . Then the first embodiment regarding suppression of information leakage through attached files in electronic mails will be described with reference to . Further the second embodiment for also suppressing information leakage through shared folders will be described with reference to . In addition the third embodiment for reducing processing loads by narrowing down the targets to be monitored to files for which information leakage is likely to occur due to careless mistake will be described with reference to . Finally several other modifications will further be discussed.

A non third party regarding a file is in other words a user or computer that is authorized to access the file. The origin of a file is of course a non third party regarding the file. Thus in S the origin is automatically registered as a non third party.

For example for a new file created in a personal computer PC that a user uses the user may be regarded as the origin of the file. The origin may be represented by information for example account name identifying the user.

When a PC is used only by one specific user the PC may be regarded as the origin. The origin may be represented by information identifying the PC. Examples of information identifying a PC within an intranet include a host name a Media Access Control MAC address and a fixedly i.e. statically assigned Internet Protocol IP address.

Further for an attached file in a received electronic mail the sender of the electronic mail may be regarded as the origin of the file. The origin may be represented by the sender s electronic mail address.

For a file downloaded from a server such as a File Transfer Protocol FTP server or a Hypertext Transfer Protocol HTTP server the server may be regarded as the origin of the file. The origin may be represented by information for example a Fully Qualified Domain Name FQDN or an IP address identifying the server.

After the registration in S the computer waits for an input to be received from the user for instructing to execute a certain process on the file. Upon receiving an input from the user the computer proceeds to a decision node S through a merge node S that follows S and in the decision node S the computer determines the type of the received input.

When the input received by the computer is an input for instructing execution of a process of deleting the file in S the computer deletes the file. Then the life cycle of the file ends and the process illustrated in also ends.

When the input received by the computer is an input for instructing execution of a process of providing access to the file the control of the process flow in proceeds to a decision node S. Alternatively when the input received by the computer is an input for instructing execution of any other process for example a process of editing the content of the file the control of the process flow in proceeds to S through a merge node S.

In S the computer executes the process instructed by the input received from the user. Then the control of the process flow in returns to the merge node S.

In the decision node S the computer determines whether or not the process instructed by the input received from the user is to provide access to the file from a third party .

A third party regarding a file is a user or computer that is not authorized to access the file. In other words a user or computer that has not been registered as a non third party regarding the file is a third party regarding the file.

Here the determination of the decision node S is executed when an input from the user is an input for instructing execution of a process of providing access to the file. Examples of the process of providing access to the file include the following processes 1 1 to 1 4 

 1 4 A process of moving or copying the file to a recording medium such as a Universal Serial Bus USB memory.

Thus in the decision node S the computer determines which of the following processes 2 1 and 2 2 the process instructed by the input from the user is 

 2 1 A process of providing access to the file only to one or a plurality of registered non third parties regarding the file.

 2 2 A process of providing access to the file to one or a plurality of third parties that have not been registered as non third parties regarding the file.

When the process instructed by the input from the user is the process 2 1 the control of the process flow in proceeds to S through the merge node S. That is when execution of a process of giving access permission only to a non third party has been instructed from the user the execution of the instructed process is permitted and consequently the instructed process is executed. Then the control of the process flow in returns to the merge node S.

Conversely when the process instructed by the input from the user is the process 2 2 then in S the computer issues a warning. By issuing a warning the computer notifies the user that the process instructed by the input from the user involves a risk of information leakage to a third party . By issuing a warning furthermore the computer prompts the user to check whether or not to actually execute the process instructed by the input from the user .

For example the input from the user may be an input for instructing the computer to execute a process of attaching the file to an electronic mail including a third party as a destination and sending the electronic mail. In this case in S the computer may display a dialog such as A third party has been specified as a destination. Do you really want to send this electronic mail 

Then the computer waits for an input to be given from the user in response to the warning and in S the computer accepts the input from the user. The input accepted in S is specifically a permission input for permitting the instructed process or a prohibition input for prohibiting the instructed process.

Then in a decision node S the computer determines which of the permission input and the prohibition input has been given.

When the prohibition input has been given the control of the process flow in returns to the merge node S. That is even when an input for instructing execution of a process of providing access to the file from a third party has been carelessly given from the user the user is able to be aware of their carelessness by receiving the warning in S. Thus the user is able to cause the computer to stop execution of the process by giving a prohibition input to the computer. Consequently information leakage due to carelessness may be avoided.

Conversely when the permission input has been given then in S the computer registers the one or a plurality of third parties in the process 2 2 as new non third parties. Then the control of the process flow in proceeds to S through the merge node S. Consequently the process whose execution is permitted by the permission input is executed in S and the control of the process flow in returns to the merge node S.

According to the process in described above various advantages such as the following advantages 3 1 to 3 5 may be achieved. That is according to the process in the advantage 3 1 of information leakage suppression and the advantages 3 2 to 3 5 of reduction in the burden placed on users and therefore suppression of reduced operation efficiency may be achieved.

 3 2 The preliminary settings of an information leakage suppression policy are not involved. Therefore a large burden is not placed on users system administrators or the like for setting the policy.

 3 3 A warning is issued only when execution of a process of providing access to a third party is actually instructed by a user. Therefore users are not bothered about excessive generation of warnings.

 3 4 The origin of the file is automatically registered as a non third party. In addition the registration of a new non third party which is triggered by a permission input is also performed automatically. Therefore users do not have to go through any particular procedures to register a non third party.

 3 5 There are no constraints on or no warnings regarding the exchange of a file between non third parties. Therefore users do not feel bothered or inconvenienced during the exchange of a file between non third parties.

Subsequently an exemplary network configuration will be described with reference to . illustrates by way of example a local area network LAN and an external network for example the Internet to which the LAN is connected.

Depending on the embodiment the management server may be omitted. A database DB for registering a non third party in association with a file may be managed by the management server .

The client PCs to in the LAN may access the DB via the management server . When the management server is omitted each of the client PCs to may locally hold a DB.

Alternatively copies of some of entries included in the DB held in the management server may be held in the client PCs to . For example the client PC may hold a copy of an entry regarding a file saved in the client PC and a copy of an entry regarding an electronic mail sent or received by the client PC .

Further a mail server different from the mail server an HTTP server and an FTP server are connected to the network . A client PC is also connected to the mail server via a network such as another LAN not illustrated .

 4 1 A file newly created in the client PC includes confidential information. It is assumed that the user of the client PC is in a position to know the confidential information with authorization.

 4 2 The user of the client PC in the LAN is not allowed to access the confidential information. A specific example of the situation 4 2 is a situation where the LAN is an intranet of a company and the user of the client PC is not allowed to view the confidential information under the rules of the company .

 4 3 Also the user of the client PC outside the LAN is not allowed to access the confidential information.

 4 4 A shared folder that the user of the client PC also has the privilege to access exists on the file server .

In the above situations 4 1 to 4 6 for example when a process such as the following processes 5 1 to 5 5 is executed carelessly by the user of the client PC the confidential information may be leaked.

 5 1 A process of attaching the file including confidential information in the situation 4 1 to an electronic mail addressed to the user of the client PC and sending the electronic mail.

 5 2 A process of attaching the file including confidential information in the situation 4 1 to an electronic mail addressed to the user of the client PC and sending the electronic mail.

 5 3 A process of moving or copying the file including confidential information in the situation 4 1 to the shared folder in the situation 4 4 .

 5 4 A process of uploading the file including confidential information in the situation 4 1 to the HTTP server .

 5 5 A process of uploading the file including confidential information in the situation 4 1 to the FTP server .

That is the processes 5 1 to 5 5 are processes that provide access to a third party and that may cause information leakage to occur. However according to the process in a warning is issued for the processes 5 1 to 5 5 . Therefore information leakage due to carelessness may be avoided.

Subsequently a functional configuration of a system will be described with reference to a block diagram in . A system in may be a client server system whose components are distributed to the client PCs to and the management server in the details of which will be described below. Alternatively each of the client PCs to may implement the system as a stand alone system.

The system includes a registration management unit an execution control unit a storage device and an input device . The registration management unit includes an origin recognition unit a registration unit a detection unit and a determination unit and the execution control unit includes a warning unit an input accepting unit a permission unit and a prohibition unit . The storage device stores in association with file identification information identifying a file non third party identification information identifying each of one or more non third parties regarding the file.

The registration management unit registers as non third party identification information information identifying the origin of a file into the storage device in association with file identification information concerning the file.

Incidentally a certain type of process provides access to a file from one or more third parties which are not the non third parties identified by the non third party identification information stored in the storage device in association with file identification information concerning the file. For convenience of description a process that provides access to a file from a third party is referred to as a specific process . The processes 5 1 to 5 5 are specific examples of the specific process.

When a specific input for instructing execution of a specific process and a permission input for permitting access to the file from the one or more third parties described above are given the registration management unit registers each of the one or more third parties described above into the storage device as a non third party regarding the file. The specific input and the permission input are inputs given from the user via the input device .

When both the specific input and the permission input are given the execution control unit permits execution of the specific process. However when the specific input is given and the permission input is not given the execution control unit prohibits execution of the specific process.

The operations of the registration management unit and the execution control unit will be described in more detail hereinafter.

The origin recognition unit recognizes the origin of the file. For example the origin recognition unit may recognize the origin based on an input from the input device .

In accordance with recognition of the origin by the origin recognition unit in S in the registration unit registers as the non third party identification information information identifying the origin into the storage device in association with file identification information concerning the file. The storage device may also hold a DB including other pieces of information in addition to the file identification information and the non third party identification information . The registration unit may also perform various processes for updating the DB such as adding an entry to the DB updating each individual entry in the DB and deleting an entry from the DB.

The detection unit detects an input from the user via the input device . Inputs from the user include a specific input for instructing execution of the specific process described above and inputs for instructing execution of other processes. That is the detection unit detects an input to be determined in the decision node S in . In accordance with the input detected by the detection unit the determination unit determines whether or not the input detected by the detection unit is the specific input described above.

Specifically the determination unit refers to the storage device to determine whether or not the input detected by the detection unit is the specific input described above . The determination of the determination unit corresponds to the decision node S in .

When the process whose execution is instructed by the input detected by the detection unit is not a process of providing access to a file it is apparent that the process instructed by the user is not the specific process described above. Thus as illustrated in the process instructed by the user is executed.

On the other hand when the process whose execution is instructed by the input detected by the detection unit is a process of providing access to a file it is probable that the process whose execution has been instructed by the user is the specific process described above. Therefore the determination unit performs the following operation.

The determination unit searches the storage device using as a search key the file identification information identifying a file on which the process whose execution is instructed by the input detected by the detection unit is to be performed. Then the determination unit extracts the non third party identification information stored in association with the search key. As a consequence no non third party identification information may be extracted or non third party identification information concerning only one non third party may be extracted. Alternatively non third party identification information concerning a plurality of non third parties may be extracted.

Here for convenience of description a target provided with access through the process whose execution is instructed by the input detected by the detection unit is referred to as an access provided target . The number of access provided targets is one or multiple. For example the access provided target may be a destination of an electronic mail a user who is granted access privileges to a shared folder on the file server in or the HTTP server or FTP server in .

The determination unit determines for each of one or a plurality of access provided targets whether or not the access provided target is a non third party identified by the extracted non third party identification information . When the access provided targets include one or more third parties the determination unit determines that the input detected by the detection unit is the specific input described above . On the other hand when the access provided targets include only non third parties the determination unit determines that the input detected by the detection unit is not the specific input described above .

When the determination unit determines that the input detected by the detection unit is the specific input described above the determination unit notifies the warning unit that the specific input has been given. Then as in S in the warning unit issues a warning.

Then as in S in the input accepting unit accepts a permission input or a prohibition input as an input in response to the warning. The permission input and the prohibition input are inputs given from the user via the input device .

Further the permission input is an input for permitting execution of the specific process and is in other words an input for permitting all the third parties included in the access provided targets where the number of the third parties is one or multiple to access the file on which the specific process is to be performed. On the other hand the prohibition input is an input for prohibiting execution of the specific process and is in other words an input for prohibiting all the third parties included in the access provided targets from accessing the file on which the specific process is to be performed.

When the input accepting unit accepts a permission input the input accepting unit notifies the registration unit that the permission input has been given.

The permission input as used here not only means that execution of the specific process has been permitted but also means that each of the third parties included in the access provided targets may be regarded from now on as a non third party regarding the file on which the specific process is to be performed . Therefore as in S in the registration unit registers one or a plurality of new non third parties into the storage device .

That is the registration unit registers non third party identification information identifying a new non third party into the storage device in association with file identification information identifying the file on which the specific process is to be performed. Each new non third party has been a third party so far and specifically a third parry found from the access provided targets by the determination unit in the manner described above. Therefore the registration unit may acquire the non third party identification information identifying a non third party to be newly registered from the determination unit .

When the input accepting unit accepts a permission input the input accepting unit sends a notification to the permission unit . In addition when the determination unit determines that the input detected by the detection unit is not the specific input described above the determination unit also sends a notification to the permission unit .

Upon receiving a notification from the determination unit or the input accepting unit the permission unit permits execution of the process whose execution is instructed by the input detected by the detection unit . Consequently as in S or S in the process instructed by the user is executed.

On the other hand when the input accepting unit accepts a prohibition input the input accepting unit sends a notification to the prohibition unit . Thus the prohibition unit prohibits execution of the specific process. Therefore as illustrated in the process flow from the decision node S to the merge node S in the specific process is not executed. Consequently information leakage due to carelessness of the user may be avoided.

As described above the system in that performs the above operation may be a stand alone system or a client server system.

When the system is a stand alone system for example the client PC in includes all the registration management unit the execution control unit the storage device and the input device . The client PCs and also have configurations similar to the client PC . An example of the stand alone system will be described in detail below in conjunction with the third embodiment.

When the system is a client server system for example the storage device may be included in the management server . Each of the client PCs to may include the execution control unit and the input device .

The components of the registration management unit may be distributed to the management server and the client PCs to . For example the management server may include the registration unit and the determination unit and each of the client PCs to may include the origin recognition unit and the detection unit .

Alternatively the management server may only provide the storage device and a DB interface regarding a DB in the storage device . Each of the client PCs to may include the registration management unit . The registration unit and the determination unit in the registration management unit access the DB in the storage device via the DB interface provided by the management server and perform operations such as adding an entry deleting an entry updating an entry and referring to an entry.

Accordingly the embodiment in which the management server provides a DB interface while the registration unit and the determination unit are off loaded into the client PCs to has an advantage that because of the reduction in the processing load on the management server the management server may easily manage a large number of clients . This advantage will be described in detail hereinafter.

Client PCs in the LAN are in other words client PCs to be managed by the management server for information leakage suppression. Therefore in a situation where a large number of client PCs exist in the LAN in when one management server serves as the registration unit and the determination unit and performs processes for each client PC such as registration and determination a large load is placed on the management server .

Thus when the LAN includes a large number of client PCs the functions of the registration unit and the determination unit are preferably off loaded into each client PC. In this case the management server may merely provide a DB interface and no problems occur when a large number of client PCs exist. In the first and second embodiments described in detail below a description will be made mainly of a case where the system is configured as a client server system in which the management server provides only a DB interface.

Subsequently a hardware configuration of a computer will be described with reference to . Each of the client PCs to the file server the mail server the management server the mail server the HTTP server the FTP server and the client PC in may be a computer such as that illustrated in .

A computer in includes a central processing unit CPU a read only memory ROM a random access memory RAM and a communication interface . The computer further includes an input device an output device a storage device and a drive device for a recording medium . The components in the computer are connected to one another via a bus . Further the computer is connected to a network via the communication interface .

In the input device the output device the storage device and the drive device are illustrated to be included in the block of the computer . However it is to be understood that the input device the output device the storage device and the drive device may be external devices which are connected to the computer .

The CPU loads a program into the RAM and executes the program while also using the RAM as a working area. The program may be stored in the ROM or the storage device in advance. The storage device may be for example a hard disk device.

Alternatively the program may also be provided by a program provider downloaded into the computer via the network and the communication interface and stored in the storage device . The program provider is for example a computer other than the computer .

The program may also be stored in a computer readable portable recording medium and provided. The program is read by the drive device from the recording medium set in the drive device . The read program may be loaded into the RAM after being copied first into the storage device or may be loaded directly into the RAM . An optical disc such as a compact disc CD or a digital versatile disc DVD a magneto optical disc a magnetic disc or a non volatile semiconductor memory card may be available as the recording medium by way of example.

The communication interface may be a wired LAN interface device a wireless LAN interface device or a combination thereof. The input device may be for example a keyboard a pointing device such as a mouse or a touch screen a microphone or a combination thereof. The output device may be for example a display a speaker or a combination thereof. The display may be a touch screen.

The ROM the RAM the storage device and the recording medium are examples of computer readable recording media. Such computer readable recording media are tangible recording media and are not a transitory media such as signal carriers.

The registration management unit illustrated in may be implemented by the CPU that executes a program. When the system is a client server system the communication interface may further be used to implement the registration management unit .

For example the origin recognition unit and the detection unit may be implemented by the CPU of each of the client PCs to .

In addition the registration unit and the determination unit access the storage device via the DB interface provided by the management server . Thus the registration unit and the determination unit may be implemented by the CPU and the communication interface of each of the client PCs to . The CPU executes a program for implementing the registration unit and the determination unit and the communication interface communicates with the management server under control of the CPU .

The warning unit may be implemented by the CPU that executes a program and the output device that outputs either of or both a visual warning and an audio warning in each of the client PCs to .

In addition the input accepting unit may be implemented by the CPU that accepts an input from the input device and that operates in accordance with a program. When the system in is not a stand alone system the input accepting unit may be implemented by further using the communication interface of each of the client PCs to .

The permission unit and the prohibition unit may be implemented by the CPU that executes a program in each of the client PCs to .

When the storage device is included in the management server the storage device may be the storage device in the management server . On the contrary for example when the storage device is included in the client PC the storage device may be the storage device in the client PC . The input device in which is included in each of the client PCs to may be the input device in which is included in the corresponding one of the client PCs to .

Subsequently the first embodiment regarding suppression of information leakage through attached files in electronic mails will be described with reference to . The first embodiment is an example when the system in is a client server system. Specifically in the first embodiment the management server in includes the following components 6 1 to 6 2 

 6 1 The storage device in more specifically the storage device in that holds a management DB in described below .

 6 2 A DB interface that accepts a DB access request to the DB on the storage device from the registration unit and the determination unit in and that responds to the DB access request.

For example the DB interface 6 2 may be implemented by the CPU that executes a program and by the communication interface . The CPU that operates in accordance with a program accepts a DB access request via the communication interface accesses the DB on the storage device in accordance with the DB access request and returns a DB access result via the communication interface .

In the first embodiment each of the client PCs to in includes the following components 7 1 to 7 6 among the blocks illustrated in .

 7 4 The determination unit that refers to the DB on the storage device via the DB interface 6 2 to perform determination.

In the following for convenience of description each flowchart will be described in the context of one of the client PCs to selected in accordance with the situation. However it is to be understood that the other two client PCs perform similar processing as desired.

The origin registration process in is a process in which the origin recognition unit recognizes as the origin of a generated file a user who is currently logged in to the client PC and in which the registration unit registers the origin into the storage device in accordance with the recognition of the origin recognition unit . That is the origin registration process in is an example of the processing of S in .

Specifically the origin registration process in is executed when a new file is generated on the client PC . For example when the following operations 8 1 to 8 2 are performed the origin recognition unit detects the saving operation 8 2 as a trigger to start the origin registration process. Upon detecting the trigger the origin recognition unit starts the origin registration process.

 8 1 It is assumed that the user of the client PC creates a new file using a process according to certain application software and edits the new file as appropriate.

 8 2 It is assumed that after that the user selects a save menu and saves the new file in the storage device of the client PC .

Depending on the application software the generation of a file on the storage device using the saving operation 8 2 is performed via for example an Application Programming Interface API function provided by an operating system OS . In this case the origin recognition unit may detect a trigger to start the process in by hooking a call to a predetermined API function that is used to generate a file.

When the process in starts first in S the origin recognition unit acquires the following pieces of information 9 1 to 9 3 

 9 1 The account name of a user who has instructed generation of a file. That is the account name of a user who is currently logged in to the client PC .

 9 2 The fully qualified path name i.e. absolute path name of the generated file. For convenience of description it is assumed that a notation that starts with the drive letter such as C dir1 dir2 file.txt is used although notation of a fully qualified path name differs depending on the OS.

 9 3 The host name of a machine in which the file has been generated. That is the host name uniquely identifying the client PC in the LAN . Other identification information may be used instead of the host name for example when the client PC is to be assigned a fixed IP address the IP address of the client PC may be used instead of the host name .

Then in S the origin recognition unit issues a file identifier ID corresponding to the generated file. The file ID is unique in the LAN to be managed by the management server . For example the origin recognition unit of the client PC may generate a file ID unique in the LAN by using the host name of the client PC in combination with a sequence number unique in the client PC . It is to be understood that depending on the embodiment the origin recognition unit may request the management server to issue a file ID unique in the LAN and acquire the file ID from the management server .

Subsequently in S an entry that associates the file ID generated in S with the location of the file represented by the pair of pieces of information 9 3 and 9 2 is added to a file location table in . In S an entry that associates the file ID generated in S with the account name 9 1 is added to a member table in . Thus the origin registration process in ends.

Here a specific example of the tables used in S and S will be described with reference to . Subsequently the details of S and S will be described with reference again to .

The content of each table in the management DB changes as an event occurs. In and reference numerals with suffixes such as and distinctly represent the same DB or the same table at different times. Specifically management DBs to are distinct examples of the management DB . Member tables to are distinct examples of the member table . File location tables to are distinct examples of the file location table . Electronic mail management tables to are distinct examples of the electronic mail management table . In the management DB at five different times is illustrated by way of example and the details of the five examples will be described below in conjunction with flowcharts. Here a description will be first given of the configuration of each table in the management DB .

Each entry in the member table associates a file ID with information i.e. the non third party identification information in identifying a non third party regarding the file identified by the file ID. In the header name non third party member is given to a column indicating the non third party identification information . The file ID is an example of the file identification information in .

Each entry in the file location table associates a file ID with location information indicating the location of the file identified by the file ID. The location information is a combination of for example a host name and a fully qualified path name of the file within the machine identified by the host name. In the header name location is given to a column indicating the location information.

Each entry in the electronic mail management table associates a message ID uniquely identifying an electronic mail a file ID of a file attached to the electronic mail and a file name of the attached file with one another. The message ID may be for example the value of the Message ID header field of the electronic mail.

Referring again to the details of S and S in will be described in conjunction with the specific example in .

For example it is assumed that before the origin registration process in is started each of the member table the file location table and the electronic mail management table is in an initial state where no entries are included. It is also assumed that the account name name A the fully qualified path name C path A Z.txt and the host name PC A have been obtained in S.

The file ID issued in S may be represented using a combination of for example as described above a host name and a sequence number. In the following however for convenience of description it is assumed that a file ID F000103 has been issued.

Then in S specifically the origin recognition unit in the client PC requests the registration unit in the client PC to add an entry to the file location table . Along with the request the origin recognition unit sends the file ID F000103 the host name PC A and the fully qualified path name C path A Z.txt to the registration unit .

Thus the registration unit in the client PC adds an entry to the file location table via the DB interface in the management server . Specifically the registration unit adds a new entry that associates location information indicated by a pair of the host name PC A and the fully qualified path name C path A Z.txt with the file ID F000103 to the file location table .

In this way the location of the generated new file is registered in the file location table . The file location table in includes one entry added in S in the above way.

In S specifically the origin recognition unit in the client PC requests the registration unit in the client PC to add an entry to the member table . Along with the request the origin recognition unit sends the file ID F000103 and the account name name A to the registration unit .

The registration unit in the client PC adds an entry to the member table via the DB interface in the management server . Specifically the registration unit adds a new entry that associates the account name name A with the file ID F000103 to the member table .

That is in S in the above manner the registration unit of the client PC registers the user who has instructed generation of a file as a non third party regarding the generated file. The member table in includes one entry added in S in the above way.

A management DB in is an example of the management DB at the time when the origin registration process in is completed in the above way. As is apparent from the foregoing description in S and S may be executed in reverse order or S and S may be executed in parallel. Further S and S may be executed in reverse order and S and S may be executed in parallel.

Subsequently a process corresponding to a specific example of the processing of S to S in will be described with reference to . is a flowchart of a sending confirmation process executed when a new electronic mail with an attached file is sent or when a received electronic mail with an attached file is forwarded.

Also in for convenience of description a process performed in the client PC will be described by way of example. Specifically the sending confirmation process in is started in the following case 10 1 or 10 2 

 10 1 The user of the client PC performs an operation for creating a new electronic mail with one or more attached files on a mail user agent which is implemented by executing an electronic mail client software and sending the created new electronic mail. For example the user clicks a send button.

 10 2 The user of the client PC performs an operation for forwarding a received electronic mail with an attached file on a mail user agent. For example the user clicks a forward button.

For example when the detection unit detects an input for clicking the send button the determination unit determines whether or not an electronic mail to be newly sent has one or more files attached. When one or more files are attached the determination unit starts the sending confirmation process in . When no files are attached the determination unit sends a notification to the permission unit and the permission unit permits the new electronic mail to be sent.

When the detection unit detects an input for clicking the forward button the determination unit determines whether or not an electronic mail to be forwarded has one or more files attached. When one or more files are attached the determination unit starts the sending confirmation process in . When no files are attached the determination unit sends a notification to the permission unit and the permission unit permits the electronic mail to be forwarded.

The detection unit may perform detection by using for example a hook prepared in advance in the mail user agent. The detection of a trigger to start the process in by the detection unit corresponds to the transition from S to S in .

When the process in starts first in S the determination unit acquires the following pieces of information 11 1 to 11 4 

 11 1 The account name of the user who has instructed the new sending or forwarding of an electronic mail.

The determination unit may acquire the account name 11 1 i.e. the account name of a user who is currently logged in to the client PC via for example the system function prepared in advance by the OS.

In the process in in addition to the address specified in the To header field of the electronic mail the electronic mail address specified in the CC Carbon Copy header field is also a destination electronic mail address. Additionally the electronic mail address specified in the BCC Blind Carbon Copy header field is also a destination electronic mail address. Therefore the determination unit acquires one or more destination electronic mail addresses.

The determination unit further acquires the file ID 11 4 of each attached file specifically in the following way 

As in the case 10 1 described above when a new electronic mail is to be sent the determination unit searches the file location table using as search keys the host name of the client PC and the fully qualified path name indicating the location of the attached file in the client PC . The determination unit may acquire the host name via for example the system function or the like provided by the OS. The determination unit may acquire the fully qualified path name via the mail user agent.

As a result of search one entry is found. This is because when a file generated on the client PC is attached the entry of the file has already been added to the file location table through the process in .

In addition an entry is also found when a file attached to another electronic mail previously received by the client PC is first saved locally in the client PC and is attached to the new electronic mail later. This is because the entry of the file has already been added to the file location table through a process in described below.

Accordingly the determination unit may acquire the file ID by reading the file ID from the found entry. Further the determination unit stores a correspondence relationship between the file name and the file ID for the processing of S described below.

In contrast as in the case 10 2 when an electronic mail is to be forwarded the determination unit searches the electronic mail management table using as search keys the message ID of the electronic mail to be forwarded by the user and the file name of the attached file. The determination unit may acquire the message ID and the file name via the mail user agent.

As a result of search one entry is found. This is because when the electronic mail to be forwarded by the user is an electronic mail sent from within the LAN the entry of the file has been added to the electronic mail management table through the process in executed by the sender client PC. When the sender of the electronic mail to be forwarded by the user is outside the LAN the client PC has executed a process in described below in response to the electronic mail previously received at the client PC . The entry of the file has already been added to the electronic mail management table through the process in .

In this way regardless of whether the sender of the electronic mail to be forwarded by the user is inside or outside the LAN the determination unit finds one entry from the electronic mail management table as a result of search. Therefore in the case 10 2 as in the case 10 1 the determination unit may acquire the file ID by reading the file ID from the found entry. Further the determination unit stores a correspondence relationship between the file name and the file ID for the processing of S described below.

When the determination unit acquires the pieces of information 11 1 to 11 4 in S in the above way then in S the determination unit initializes a warning list to empty. The warning list is an example of information to be used by the determination unit to perform determination in S in .

Then in S the determination unit determines whether or not each of the following pairs 12 1 and each of the following pairs 12 2 have been registered in the member table .

For convenience of description it is assumed that N files N 1 are attached to the electronic mail. In this case there are N pairs of a file ID and a sender s electronic mail address and N pairs of a file ID and an account name. Thus the determination unit determines whether or not all of 2N pairs in total have been registered in the member table .

When there is a pair that has not been registered in the member table the process proceeds to S. Conversely when all the 2N pairs have been registered in the member table the process proceeds to S.

In S the determination unit registers each unregistered pair into the member table . The processing of S is a process of registering an apparent non third party to suppress the wasteful generation of warnings to consequently reduce the burden placed on the user.

For example it is assumed that there is one attached file and that the file ID of the attached file is F000103 given in the file location table in . It is also assumed that the account name and the sender s electronic mail address obtained in S are name A and a foo.com respectively.

In this case according to the member table in the pair of the file ID F000103 and the account name name A has been registered. However the pair of the file ID F000103 and the sender s electronic mail address a foo.com has not been registered. Thus in S the determination unit adds an entry corresponding to the pair of the file ID F000103 and the sender s electronic mail address a foo.com to the member table .

When there are two or more unregistered pairs the determination unit adds an entry corresponding to each pair to the member table in a similar manner. Then the process proceeds to S.

In S the determination unit determines whether or not a yet to be focused pair of a file ID and a destination electronic mail address remains.

Here for convenience of description it is assumed that the number of destination electronic mail addresses 11 3 acquired in S is M M 1 . Since N 1 and M 1 MN 1. That is there are MN pairs of a file ID and a destination electronic mail address.

Therefore in S the determination unit determines whether or not a pair that has not been focused on as a target to be processed in S to S remains among the MN pairs.

When a yet to be focused pair remains the process proceeds to S. Conversely when all the MN pairs have been focused on the process proceeds to S.

In S the determination unit focuses on one yet to be focused pair of a file ID and a destination electronic mail address. Hereinafter for convenience of description a file ID and a destination electronic mail address in the pair focused on in S are referred to as the file ID of interest and the electronic mail address of interest respectively.

Then in S the determination unit determines whether or not the electronic mail address of interest is a third party electronic mail address for the file identified by the file ID of interest. Specifically the determination unit searches the member table for an entry that associates the file ID of interest with the electronic mail address of interest.

When an entry is found as a result of search the electronic mail address of interest is a non third party electronic mail address for the file identified by the file ID of interest. That is no information leakage occurs through the file sent to the electronic mail address of interest. Thus the process returns to S.

Conversely when no entries are found as a result of search in S the electronic mail address of interest is a third parry electronic mail address for the file identified by the file ID of interest. That is it is probable that information leakage will occur through the file sent to the electronic mail address of interest. Thus the process proceeds to S to provide a warning.

In S the determination unit updates the warning list. Specifically the determination unit adds to the warning list a set of three items including the file ID of interest the file name corresponding to the file ID of interest and the electronic mail address of interest. As described above in S the determination unit stores a correspondence relationship between the file name of an attached file and the file ID of the attached file during the acquisition of the file ID. Thus the determination unit has recognized the file name corresponding to the file ID of interest and in S the determination unit may therefore add an item to the warning list in the manner described above. After the warning list has been updated the process returns to S.

On the other hand after all the MN pairs of a file ID and a destination electronic mail address have been focused on in S the determination unit determines whether or not the warning list is empty.

When the warning list is empty that is when each of the M destination electronic mail addresses is a non third party electronic mail address for all the N attached files there is no risk of information leakage. In other words even when a new electronic mail is sent or when a received electronic mail is forwarded access to any attached file is not provided to a third party.

Thus the determination unit notifies the permission unit and the registration unit that there is no information leakage to third parties and then the process proceeds to S. The transition from S to S corresponds to the link from S to S in .

Conversely when the warning list is non empty that is when sending a new electronic mail or forwarding a received electronic mail makes at least one attached file in the electronic mail accessible from a third party there is a risk of information leakage.

Thus the determination unit outputs the warning list to the warning unit and the process proceeds to S. The transition from S to S corresponds to the link from S to S in .

In S the permission unit permits an electronic mail to be sent i.e. a new electronic mail to be sent or a received electronic mail to be forwarded . Thus the electronic mail is sent via the mail user agent.

Further when sending the electronic mail the mail user agent assigns a new message ID to the electronic mail. Thus in S the registration unit reads the assigned new message ID.

Then the registration unit registers for each attached file a set of three items including the message ID the file ID and the file name into the electronic mail management table . The registration unit may acquire information indicating a correspondence relationship between the file name and the file ID of an attached file from the determination unit . Then the process in ends.

Meanwhile in S the warning unit issues a warning in accordance with the warning list received from the determination unit . For example when the warning list includes four sets of three items including a file ID a file name and a destination electronic mail address the warning unit may display dialogs including the following dialogs 13 1 to 13 3 on a screen of the client PC 

 13 1 A warning message such as Information leakage to a third party may occur with the following four sets. Do you really want to send this electronic mail 

 13 2 A pair of a file name and a destination electronic mail address that are associated with each other in each set of three items included in the warning list.

The dialogs 13 1 to 13 3 given above are merely examples of a graphical user interface GUI for a warning. Any other GUI may be used. It is to be understood that the warning unit may issue an audio warning.

In addition to the issuance of a warning the warning unit instructs the input accepting unit to accept an input from the input device in response to the warning. Then in S the input accepting unit waits for an input for example a click of the Yes button or the No button in the example of the dialog 13 3 to be received from the input device .

When the input accepting unit accepts an input from the input device in response to the warning the process proceeds to S. Then in S the input accepting unit determines whether the accepted input is a permission input or a prohibition input.

When the input accepting unit accepts a prohibition input the input accepting unit sends a notification to the prohibition unit . Then the process proceeds to S.

Conversely when the input accepting unit accepts a permission input the input accepting unit notifies the permission unit and the registration unit that there is no information leakage to third parties. Then the process proceeds to S.

In S the prohibition unit stops sending an electronic mail specifically sending a new electronic mail or forwarding a received electronic mail . That is the prohibition unit prohibits an electronic mail from being sent via the mail user agent. Specifically the prohibition unit may prohibit an electronic mail from being sent by for example canceling the input given from the user to the mail user agent. Then the process in ends.

On the other hand in S the registration unit acquires a warning list from the determination unit and adds entries to the member table in accordance with the warning list. Specifically the registration unit registers for each set of three items included in the warning list i.e. each set of three items including a file ID a file name and a destination electronic mail address a pair of a file ID and a destination electronic mail address that are associated with each other in the set of three items into the member table . The registration of a new non third party into the member table in S is a specific example of registration in S in .

For example when the warning list includes four sets of three items in S the registration unit adds the four entries to the member table . After the member table has been updated the process proceeds to S.

According to the process in a situation where a file is attached to an electronic mail addressed to a third party due to the carelessness of a user and the electronic mail is sent resulting in information leakage occurring may be avoided. According to the process in furthermore no warnings are issued for an electronic mail to be sent to only one or a plurality of non third parties. Therefore a situation where excessive generation of warnings reduces users operation efficiency may also be avoided.

A management DB in is an example of the management DB after the process in has been completed in a case under the following assumptions 14 1 to 14 9 

 14 1 It is assumed that the process in starts in response to a trigger event that the user having the account name name A is to send a new electronic mail.

 14 2 It is assumed that the management DB is in the state of the management DB in when the process in is started.

 14 3 It is assumed that a new electronic mail has only a file attached whose location is given in the file location table in but no other files attached.

 14 4 It is assumed that the new electronic mail has the sender s electronic mail address a foo.com .

 14 5 It is assumed that the new electronic mail has only one destination electronic mail address b foo.com .

 14 6 From 14 1 to 14 4 described above in S in an entry that associates a file ID F000103 with the sender s electronic mail address a foo.com is added to the member table .

 14 7 From 14 2 14 3 and 14 5 described above in S in a warning is issued for a combination of the attached file having a file name Z.txt and the destination electronic mail address b foo.com .

 14 8 It is assumed that a permission input is given in response to the warning. As a result in S an entry that associates the file ID F000103 with the destination electronic mail address b foo.com is added to the member table .

 14 9 It is assumed that in S an electronic mail permitted to be sent is assigned the message ID M000015 . As a result in S an entry that associates the message ID M000015 with the file ID F000103 is added to the electronic mail management table . Then the process in ends.

In the case under the assumptions 14 1 to 14 9 described above the management DB changes from the state of the management DB in to the state of the management DB in .

Next an attached file registration process performed when an electronic mail with an attached file is received will be described with reference to . The process in is a process for automatically registering a user who has received an electronic mail as a non third party regarding the attached file in the electronic mail.

For example it is assumed that an electronic mail with an attached file has been received at the client PC from the client PC via the mail server the network and the mail server in . Alternatively it is assumed that an electronic mail with an attached file is received at the client PC from the client PC via the mail server .

In either case the user of the client PC is a non third party regarding the attached file in the received electronic mail. Thus the process in is performed when the electronic mail is received at the client PC and a non third party is registered.

For example when the user of the client PC performs an operation for receiving an electronic mail such as clicking a receive button on the mail user agent the detection unit detects the operation performed by the user. Then the detection unit notifies the registration unit that the operation for receiving an electronic mail has been performed.

When a received electronic mail box of the mail server is empty no electronic mail is to be received. In this case therefore the process in is useless and is not executed.

Conversely when one or more electronic mails have been received the registration unit that has received a notification from the detection unit checks whether or not each received electronic mail has a file attached. When one or more attached files are found the process in is started. In the following it is assumed that for convenience of description a received electronic mail has N files attached N 1 .

Specifically first in S the registration unit acquires the following pieces of information 15 1 to 15 4 

The registration unit may acquire the account name 15 1 via for example the system function or the like prepared in advance by the OS.

Further the registration unit acquires the received electronic mail address 15 2 via the mail user agent. For example the registration unit may read the received electronic mail address from the property of the electronic mail box on which a receiving operation is to be performed.

The received electronic mail address may be specified in the To header field or the CC header field of the received electronic mail. Alternatively when the received electronic mail address is the address specified in the BCC header field when the electronic mail is sent the received electronic mail address is not included in the received electronic mail itself.

Further the registration unit reads the message ID 15 3 from the Message ID header field of the received electronic mail.

Further the received electronic mail includes N Content Disposition header fields corresponding to the N attached files. Thus the registration unit reads the file names of the respective attached files from the corresponding Content Disposition header fields.

When the registration unit acquires the pieces of information 15 1 to 15 4 in S in the above way then in S the registration unit determines whether or not the acquired message ID has been registered in the electronic mail management table . When the message ID has been registered in the electronic mail management table the process proceeds to S. Conversely when the message ID has not been registered in the electronic mail management table the process proceeds to S.

The processing of S is executed when an electronic mail is received from another client for example the client PC managed by the management server that manages the client for example the client PC in that executes the process in . In other words the processing of S is executed when the registration of the origin in S in has been performed.

For example it is assumed that an electronic mail has been sent from the client PC to the client PC . In this case as a result of the process in by the client PC an entry regarding the electronic mail is added to the electronic mail management table included in the management DB of the management server . Therefore when the client PC that receives an electronic mail performs the process in an entry is found in the electronic mail management table in S.

Thus in S the registration unit acquires from the electronic mail management table the file ID of each file attached to the received electronic mail. The registration unit searches the electronic mail management table for the file ID of each attached file using as search keys the file name of the file acquired in S and the message ID acquired in S. When the registration unit has acquired the file IDs of all the N attached files the process proceeds to S.

On the other hand the processing of S is executed when an electronic mail is received from a host outside an intranet which is not managed by the management server that manages the client for example the client PC in that executes the process in .

For example it is assumed that an electronic mail has been sent from the client PC to the client PC via the mail server the network and the mail server .

In this case the client PC is a host outside the LAN managed by the management server . Therefore the management DB in the management server is not changed merely by sending an electronic mail from the client PC .

That is the management DB includes no data concerning the electronic mail sent from the client PC . Therefore when the client PC that receives the electronic mail performs the process in no entries are found in S.

Thus in S the registration unit performs the following processes 16 1 and 16 2 on each file attached to the received electronic mail 

 16 2 A process of adding to the electronic mail management table a new entry that associates the message ID acquired in S the new file ID issued in the process 16 1 and the file name of the file acquired in S with one another.

The issuance of a file ID by the registration unit in the process 16 1 is similar to the issuance of a file ID by the origin recognition unit in S in . That is the registration unit generates a file ID unique in the LAN . Alternatively depending on the embodiment the registration unit may request the management server to issue a file ID unique in the LAN and may acquire the file ID from the management server .

The issuance of a file ID in S is also a pre processing operation for registering the origin in S in . In addition when the received electronic mail has N files attached N new entries are added to the electronic mail management table through the process 16 2 . After the processes 16 1 and 16 2 are completed in S the processing of S is executed.

In S the registration unit determines whether or not of the N attached files in the received electronic mail an attached file remains that has not been focused on as a target to be subjected to the processing of S and the subsequent processing. When a yet to be focused attached file remains the process proceeds to S. Conversely when the registration unit has focused on all the N attached files the process in ends.

In S the registration unit focuses on one yet to be focused attached file. In the following for convenience of description the attached file focused on in S is referred to as the attached file of interest .

Then in S the registration unit determines whether or not the account name acquired in S has been associated with the file ID of the attached file of interest . That is the registration unit determines whether or not the acquired account name has been registered in the member table as a non third party regarding the attached file of interest . Specifically the registration unit searches the member table using as search keys the file ID of the attached file of interest and the account name acquired in S.

When an entry is found as a result of search the acquired account name has been registered in the member table as a non third party regarding the attached file of interest. Thus the process proceeds to S.

Conversely when no entries are found as a result of search the acquired account name has not yet been registered as a non third party regarding the attached file of interest. Thus the process proceeds to S for registration.

Then in S the registration unit registers a pair of the file ID of the attached file of interest and the acquired account name into the member table . That is the registration unit adds a new entry corresponding to the pair to the member table . Then the process proceeds to S.

In S the registration unit determines whether or not the received electronic mail address acquired in S has been associated with the file ID of the attached file of interest . That is the registration unit determines whether or not the received electronic mail address has been registered in the member table as a non third party regarding the attached file of interest . Specifically the registration unit searches the member table using as search keys the file ID of the attached file of interest and the received electronic mail address.

When an entry is found as a result of search the received electronic mail address has been registered in the member table as a non third party regarding the attached file of interest. Thus the process returns to S.

Conversely when no entries are found as a result of search the received electronic mail address has not yet been registered as a non third party regarding the attached file of interest. Thus the process proceeds to S for registration.

Then in S the registration unit registers a pair of the file ID of the attached file of interest and the received electronic mail address into the member table . That is the registration unit adds a new entry corresponding to the pair to the member table . Then the process returns to S.

According to the process in described above therefore a recipient of an electronic mail is automatically registered as a non third party regarding each file attached to the electronic mail. The account name of the recipient is registered and the electronic mail address of the recipient is also registered.

It is to be noted that electronic mails may not necessarily be read and attached files may not necessarily be saved. For example a user or a recipient may locally save an attached file in an electronic mail immediately upon receiving the electronic mail may locally save the attached file later as appropriate or may not save the attached file. The process in is executed when an electronic mail is received regardless of whether an attached file will be saved in the future.

Further a management DB in is an example of the management DB in a case under the following assumptions 17 1 to 17 8 after the process in has been completed 

 17 1 It is assumed that a user who uses the client PC under the account name name B performs an operation for receiving an electronic mail.

 17 2 It is assumed that only one electronic mail is received as a result of the operation in 17 1 . Thus the process in is started for the received electronic mail.

 17 3 It is assumed that the received electronic mail is specifically the electronic mail described with reference to 14 1 to 14 9 regarding the management DB in .

 17 4 It is assumed that the management DB is in the state of the management DB in when the process in is started.

 17 6 From 17 4 and 17 5 described above and from an electronic mail management table in an entry is found in S. As a consequence in S the file ID F000103 is acquired from the electronic mail management table

 17 7 From 17 4 and 17 5 described above and from the member table in it is determined that in S the account name name B has not yet been associated with the file ID F000103 as a non third party. As a consequence in S an entry that associates the account name name B with the file ID F000103 is added to the member table .

 17 8 From 17 4 and 17 5 described above and from the member table in it is determined in S that the received electronic mail address b foo.com has already been associated with the file ID F000103 as a non third party. As a consequence the processing of S is not executed and the process returns from S to S. Then the process in ends.

In a case under the assumptions 17 1 to 17 8 described above the management DB changes from the state of the management DB in to the state of the management DB in .

Next a location registration process performed when an attached file in an electronic mail is locally saved will be described with reference to . As described with reference to an attached file in an electronic mail may not necessarily be saved immediately when the electronic mail is received and may be saved at an arbitrary timing. Thus the process in may be executed for any received electronic mail at an arbitrary timing.

Similarly to the process in the process in will be described in the context of the client PC for convenience of description. When the user of the client PC performs an attached file saving operation for saving one or more attached files in an electronic mail via the mail user agent the detection unit detects the operation performed by the user. Specifically the attached file saving operation may include a plurality of operations such as the following operations 18 1 to 18 4 

 18 2 An operation of selecting L attached files 1 L N to be saved from among N attached files 1 N in an electronic mail.

Upon detecting the attached file saving operation the detection unit notifies the registration unit that the attached file saving operation has been detected. Then the registration unit starts the process in . In the following for convenience of description it is assumed that as in the example of the operation 18 2 described above the electronic mail has N files 1 N attached and that an instruction to save L attached files among the N attached files 1 L N is given from the user.

In S the registration unit determines whether or not an attached file that has not been focused on as a target to be subjected to the processing of S to S remains among the L attached files instructed to be saved. When a yet to be focused attached file remains the process proceeds to S. Conversely when the registration unit has already focused on all the L attached files the process in ends.

In S the registration unit focuses on one yet to be focused attached file. In the following for convenience of description the attached file focused on in S is referred to as the attached file of interest .

 19 2 The host name of a machine in which the L attached files are to be saved i.e. a machine that executes the process in .

The registration unit acquires the file ID 19 1 by searching the electronic mail management table using as search keys the message ID of the electronic mail to be subjected to the process in and the file name of the attached file of interest. The details will be described below.

The registration unit may read the message ID from the Message ID header field of the electronic mail and may read the file name of an attached file from the Content Disposition header field of the electronic mail. That is the registration unit may acquire search keys for searching the electronic mail management table from the electronic mail.

As a result of search an entry is found. This is because an entry has already been added in S in when the electronic mail is sent or an entry has already been added in S in when the electronic mail is received. Thus the registration unit may acquire the file ID 19 1 from the electronic mail management table .

The registration unit further acquires the host name 19 2 via for example the system function or the like prepared in advance by the OS. Further the registration unit acquires the fully qualified path name 19 3 by concatenating the file name of the attached file of interest with the fully qualified path name of the save destination folder specified on the mail user agent.

Then in S the registration unit registers location information concerning the attached file of interest into the file location table in accordance with the information acquired in S. That is the registration unit adds a new entry that associates the pieces of information 19 1 to 19 3 with one another to the file location table . Then the process returns to S.

A management DB in is an example of the management DB in a case under the following assumptions 20 1 to 20 6 after the process in has been completed.

 20 1 It is assumed that the user of the client PC performs the attached file saving operation for the electronic mail received at the client PC described with reference to the case under the assumptions 17 1 to 17 8 regarding the management DB in . In response to the attached file saving operation as a trigger the process in is started. From the assumptions 17 3 and 14 3 the electronic mail has one file attached.

 20 2 It is assumed that the management DB is in the state of the management DB in when the process in is started.

 20 4 It is assumed that the client PC has the host name PC B . Thus in S the host name PC B is acquired.

 20 5 It is assumed that in the attached file saving operation in the assumption 20 1 described above the user specifies a folder identified by the fully qualified path name C path B as a save destination folder. In addition from the assumptions 20 1 and 20 2 the attached file has the file name Z.txt . Thus in S C path B Z.txt is acquired as the fully qualified path name of the save destination of the attached file.

 20 6 Thus in S a new entry that associates the file ID in the assumption 20 3 the host name in the assumption 20 4 and the fully qualified path name in the assumption 20 5 with one another is added to the file location table .

In the case under the assumptions 20 1 to 20 6 described above the management DB changes from the state of the management DB in to the state of the management DB in . For example as in the assumption 20 6 the addition of an entry through the process in has the advantage of avoiding excessive generation of warnings when a file is edited and is exchanged between non third parties many times. The reason will be described hereinafter with reference to a specific example.

After the addition of an entry in the assumption 20 6 described above the user of the client PC may edit the attached file saved in C path B Z.txt and overwrite to save the edited file. The user of the client PC may further attach the edited file to a new electronic mail and may wish to send the electronic mail to the user of the client PC i.e. to the electronic mail address a foo.com .

Thus the client PC performs the process in . In this case in S in the file ID F000103 is obtained from the entry previously added to the file location table in the assumption 20 6 through the process in performed by the client PC .

Therefore according to the process in it is determined that also for the edited file overwritten and saved in C path B Z.txt the destination electronic mail address a foo.com is a non third party electronic mail address. Thus even when only the destination electronic mail address a foo.com is included no warnings are generated.

That is in a case where the file described above is exchanged via electronic mail between two non third parties identified by the electronic mail addresses a foo.com and b foo.com no warnings are generated when the file is sent second and more times. According to the first embodiment therefore in addition to information leakage due to carelessness being avoided a situation where excessive generation of warnings impedes information from being exchanged between non third parties may also be avoided.

Furthermore non third parties regarding a file may include for example a non third party that exists outside the LAN i.e. outside the range of management of the management server such as the client PC . As is apparent from the description with reference to also in a case where a file is exchanged via electronic mail between such an out of network non third party and an in network non third party excessive generation of warnings is suppressed as in a case where a file is exchanged between non third parties within the LAN .

In addition to the file described above being exchanged via electronic mail between the two non third parties identified by the electronic mail addresses a foo.com and b foo.com as in the example described above the electronic mail may also be forwarded or transferred. For example a management DB in is an example of the management DB when such forwarding is performed. More specifically in the following case under assumptions 21 1 to 21 8 the management DB changes to the management DB in .

 21 1 It is assumed that the user of the client PC performs an operation for forwarding the electronic mail described with reference to the assumptions 17 1 to 17 8 i.e. an electronic mail received at the client PC .

 21 2 It is assumed that the operation in the assumption 21 1 described above is performed when the management DB is in the state of the management DB in .

 21 3 It is assumed that the electronic mail address of the transfer destination is c bar.org . Here it is assumed that the bar.org domain is outside the LAN managed by the management server in . It is also assumed that an electronic mail addressed to the address c bar.org is specifically received at the client PC in .

 21 4 The process in is performed in the client PC in accordance with the detection of the operation performed by the user in the assumption 21 1 . Thus from the assumptions 21 1 to 21 2 and a warning regarding the combination of the electronic mail address c bar.org and the attached file having the file name Z.txt is issued in S in .

 21 5 It is assumed that the user of the client PC gives a permission input in response to the warning in the assumption 21 4 described above.

 21 6 As a result of the permission input in the assumption 21 5 described above in S an entry that associates the file ID F000103 corresponding to the file name Z.txt with the electronic mail address c bar.org is added to the member table .

 21 7 Further in S this electronic mail is forwarded to the electronic mail address c bar.org . It is assumed that the message ID assigned to the electronic mail when forwarded is M000021 .

 21 8 In S furthermore an entry that associates the message ID M000021 the file ID F000103 and the file name Z.txt with one another is added to the electronic mail management table .

In the case under the assumptions 21 1 to 21 8 described above the management DB changes from the state of the management DB in to the state of the management DB in . Thus the user outside the LAN specifically the user identified by the electronic mail address c bar.org is also newly registered as a non third party of the file described above.

As described above in the first embodiment the file ID is used as a specific example of the file identification information in .

In terms of appropriateness of the file identification information for example the mere use of file name is not appropriate. This is because it is not possible to distinguish different files having the same name from each other only by file name.

In contrast a fully qualified path name representing the location of a file would enable different files having the same name that are in different folders in a single host to be distinguished from each other. Therefore when the system in is implemented as a stand alone system for example a third embodiment described below the fully qualified path name of a file may be used as the file identification information .

In the first embodiment in which the system is implemented as a client server system however a file ID rather than a fully qualified path name is used as the file identification information . As described above a file ID is unique in the LAN managed by the management server . That is using file IDs enables different files on the same fully qualified path name in different hosts to be distinguished from each other.

Another advantage of using a file ID as described above is the capability of managing continuity of a file attached to an electronic mail that is exchanged. The capability of managing continuity of a file may avoid excessive generation of warnings and would not disturb the operation of users.

For example a file newly generated in the client PC may be attached to an electronic mail and sent to the client PCs and and may be individually edited in the client PCs and . After that electronic mails having edited files attached may be sent to the client PC from the client PCs and .

For example in the above situation the same file may have different forms such as the following states 22 1 to 22 10 . The management server is not able to detect the file states 22 7 and 22 8 but identifies the file states 22 1 to 22 6 and 22 9 to 22 10 with a single file ID.

 22 2 A file that is attached to an electronic mail to be sent from the client PC to the client PCs and .

 22 3 A file that is extracted from the electronic mail in 22 2 received at the client PC and that is locally saved in the client PC .

 22 5 A file that is attached to an electronic mail to be sent from the client PC to the client PC after the file is overwritten and saved in 22 4 .

 22 6 A file that is extracted from the electronic mail in 22 5 received at the client PC and that is locally saved in the client PC . When the file 22 6 is saved the file 22 1 may be overwritten or the file 22 6 may be saved in a location different from the file 22 1 .

 22 7 A file that is extracted from the electronic mail in 22 2 received at the client PC and that is locally saved in the client PC .

 22 9 A file that is attached to an electronic mail to be sent from the client PC to the client PC after the file is overwritten and saved in 22 8 .

 22 10 A file that is extracted from the electronic mail in 22 9 received at the client PC and locally saved in the client PC . When the file 22 10 is saved the file 22 1 may be overwritten or the file 22 10 may be saved in a location different from the file 22 1 .

As in the above examples in the first embodiment even when a single file is subjected to several operations such as locally saving the file editing the file and attaching the file to an electronic mail and sending the electronic mail one after another the file is continuously managed with the same file ID. In general furthermore a non third party regarding a file is still a non third party regarding the file even when the file undergoes some operation. When the file is continuously managed with the same file ID as a result the non third party is also continuously recognized as a non third party. Therefore even when the file is subjected to operations one after another excessive generation of warnings such as generation of a warning each time an operation is performed is avoidable. In this manner using a file ID as the file identification information is advantageous for avoiding excessive generation of warnings.

As described above using a file ID as the file identification information is advantageous. In addition a process in described below allows a file to be kept track of by using a file ID. That is the function of keeping track of a file and managing continuity of the file even when the file is copied moved or renamed may be implemented by performing the process in and using a file ID.

The process in is started when the detection unit detects an operation for copying moving or renaming a file. Specific examples of an operation detected by the detection unit as a trigger of the process in include for example the following operations 23 1 to 23 7 

 23 1 Copying a file in response to a command provided by an OS for example copying a file in response to a copy command .

 23 2 Copying a file via a GUI provided by an OS for example copying a file by performing an operation for copying and pasting the icon of the file .

 23 3 Moving a file in response to a command provided by an OS for example moving a file in response to a move command .

 23 4 Moving a file via a GUI provided by an OS for example moving a file by performing an operation for dragging and dropping the icon of the file or an operation for cutting and pasting the icon of the file .

 23 5 Renaming a file in response to a command provided by an OS for example renaming a file in response to a rename command .

 23 6 Renaming a file via a GUI provided by an OS for example renaming a file by performing an operation of selecting the icon of the file and changing the file name in the property .

 23 7 Copying moving or renaming a file using a process according to application software for example copying a file by performing an operation of opening an existing file using a process according to application software and by saving the file as a different name .

The detection unit may detect an operation such as any of the operations 23 1 to 23 7 for copying moving or renaming a file by for example hooking a call to a command or a call to an API function. Regardless of the specific method of detection upon detecting an operation for copying moving or renaming a file the detection unit notifies the registration unit of the content of the detected operation. Thus the registration unit starts the process in .

 24 1 The host name of a machine on which a copying moving or renaming operation is performed i.e. the host name of a machine to which an input for copying moving or renaming is given .

 24 4 The new fully qualified path name of the file i.e. the fully qualified path name in the copy destination the fully qualified path name in the move destination or the fully qualified path name of a renamed file .

The registration unit acquires the host name 24 1 via for example the system function or the like prepared in advance by the OS. For example when the process in is performed on the client PC having the host name PC A the registration unit acquires the host name PC A .

In addition as described above the detection unit notifies the registration unit of the content of the operation detected by the detection unit as a trigger to start the process in . Therefore the registration unit may recognize the pieces of information 24 2 and 24 4 in accordance with the notification from the detection unit .

The detection unit itself may acquire the pieces of information 24 2 and 24 4 in for example the following way. Therefore the detection unit may notify the registration unit of the pieces of information 24 2 and 24 4 .

For example when a file is copied moved or renamed in response to a command provided by an OS the detection unit may acquire the pieces of information 24 2 and 24 4 from an argument of the command and the fully qualified path name of the current folder. Alternatively the detection unit may acquire the pieces of information 24 2 and 24 4 from an argument of an API function that is called to copy move or rename the file.

Further the registration unit acquires the file ID 24 3 by searching the file location table using the host name 24 1 and the fully qualified path name 24 2 as search keys.

For example it is assumed that a file whose location is identified by the fully qualified path name C path B Z.txt is copied to C path B tmp Z2.txt in the client PC having the host name PC B . It is also assumed that the file location table is specifically in the state of the file location table in .

In this case the host name 24 1 is PC B and the fully qualified path name 24 2 is C path B Z.txt . Further the file ID 24 3 is F000103 and the fully qualified path name 24 4 is C path B tmp Z2.txt .

In S for example the registration unit acquires the pieces of information 24 1 to 24 4 in the above way.

Then in S the registration unit determines the type of the operation. When the type of the operation is moving or renaming the process proceeds to S. When the type of the operation is copying the process proceeds to S.

In S the registration unit deletes the entry that associates the file ID with the location information concerning the original file from the file location table .

Here the location information concerning the original file is specifically represented by a combination of the host name 24 1 and the fully qualified path name 24 2 obtained in S. Thus the registration unit searches the file location table using the file ID 24 3 the host name 24 1 and the fully qualified path name 24 2 as search keys. The registration unit deletes one entry found as a result of search. After that the process proceeds to S.

In S the registration unit adds an entry that associates the file ID with the new location information to the file location table . Here the new location information is specifically represented by a combination of the host name 24 1 and the fully qualified path name 24 4 obtained in S. Thus the registration unit adds a new entry that associates the file ID 24 3 the host name 24 1 and the fully qualified path name 24 4 with one another to the file location table . Then the process in ends.

For efficient use of the storage device in an unnecessary entry in the management DB may be deleted. Specifically a process in may be performed.

An OS provides a command such as a del command a menu for emptying the trash box or the like to delete a file. Thus upon detecting a call to the above command or menu provided to delete a file the detection unit notifies the registration unit of the content of the detected call. Then the registration unit starts the process in . The detection unit may detect a call to the above command or menu using for example a hook.

For example the registration unit of the client PC may acquire the host name 25 1 i.e. the host name of the client PC namely name A via the system function or the like prepared in advance by the OS.

Further the registration unit acquires the fully qualified path name 25 2 from the content notified by the detection unit .

The detection unit may recognize the fully qualified path name 25 2 from for example an argument of a command for deleting the file and the fully qualified path name of the current folder. According to a certain type of OS furthermore a file in the trash box is associated with information indicating the fully qualified path name of a folder in which the file is originally placed. Thus the detection unit may acquire the fully qualified path name 25 2 via for example the OS. Accordingly the detection unit may recognize the fully qualified path name 25 2 and may notify the registration unit of the fully qualified path name 25 2 .

Further the registration unit may acquire the file ID 25 3 by searching the file location table using the host name 25 1 and the fully qualified path name 25 2 as search keys.

In the above manner the registration unit acquires the pieces of information 25 1 to 25 3 in S. Then in S the registration unit deletes an entry regarding the file to be deleted from the file location table . That is the registration unit deletes an entry that associates the file ID 25 3 the host name 25 1 and the fully qualified path name 25 2 with one another from the file location table .

Then in S the registration unit determines whether or not the file ID 25 3 is included in the file location table or the electronic mail management table .

Specifically the registration unit searches the file location table using the file ID 25 3 as a search key. When a client machine different from the client machine that executes the process in locally saves a file having the same file ID an entry is found in the file location table .

Further the registration unit searches the electronic mail management table using the file ID 25 3 as a search key. When an electronic mail previously sent or received between the client machine that executes the process in and another client machine is attached a file having the file ID 25 3 an entry is found in the electronic mail management table .

When no entries are found in the file location table and the electronic mail management table as a result of search the process proceeds to S. When an entry is found in at least one of the file location table and the electronic mail management table the process proceeds to S.

In S the registration unit deletes all the entries including the file ID 25 3 from the member table . As a consequence no entry including the file ID 25 3 exists in the member table the file location table and the electronic mail management table . After the deletion of the entries the process proceeds to S.

In S the detection unit performs control for permitting deletion of the file. For example the detection unit causes the execution of a hook function to be completed to return the control to the command or menu for deleting a file and may thereby permit deletion of the file. As a result of the processing of S the file whose deletion has been instructed by the user is deleted.

According to the process in described above an entry that is apparently unnecessary is deleted from the member table . That is according to the process in the member table is managed so as not to have an entry regarding a file meeting both the following conditions 26 1 and 26 2 

 26 2 Having no possibility to be extracted in the future from an electronic mail currently saved in any of the client PCs to and to be locally saved on any of the client PCs to .

Further according to the process in an unnecessary entry is deleted from the file location table in accordance with the deletion of a file. Therefore wasteful consumption of a storage area may be avoided by the process in .

Subsequently a second embodiment for suppressing information leakage through shared folders will be described with reference to . In the second embodiment in addition to processes similar to those in the first embodiment a process for suppressing information leakage through a shared folder is further performed.

For example as in the LAN may include the file server a shared folder may be created on the file server and a file may be shared between users via the shared folder. Depending on the access privilege set in the shared folder however unintended information leakage via the shared folder may occur.

 27 2 The users of the client PCs and are staff members of a first department in the company. The user of the client PC is a staff member of a second department in the company.

 27 3 According to the rules of the company staff members of the second department are not allowed to view internal documents of the first department.

 27 4 Meanwhile a shared folder is created on the file server to share information between departments. All the users of the client PCs to are permitted to read and write the shared folder.

In the situations 27 1 to 27 4 described above when the user of the client PC saves a file of an internal document of the first department in the shared folder created in the situation 27 4 the internal document of the first department may be accessed from staff members of the second department. In the second embodiment for example a process in is performed in order to suppress such information leakage due to carelessness of users.

In the following for convenience of description the process in is performed in the client PC by way of example.

In the following furthermore for simplicity of description a description will be made mainly of a case where a certain file is to be written to a shared folder. In a case where a plurality of files are to be collectively written to a shared folder the process in is performed for each file.

 28 1 A user of the client PC performs an operation of copying or moving a file locally saved in the client PC to a shared folder.

 28 2 A user of the client PC performs an operation of copying or moving a file saved in a first shared folder to a second shared folder.

 28 3 A user of the client PC performs an operation of saving an attached file in an electronic mail received at the client PC into a shared folder.

An example of the case 28 1 is that an input for copying or moving a file to a shared folder in response to a command or GUI provided by the OS is given from the input device of the client PC . Another example is that an input for saving a file locally saved in the client PC into a shared folder via a save as . . . menu of application software is given from the input device of the client PC .

In the case 28 2 the process in is started for the second shared folder. The copying or moving in the case 28 2 may be an operation performed in response to a command or GUI provided by the OS or may be an operation performed by a process according to application software.

The operation performed in the case 28 3 is an operation performed on the mail user agent. Specifically a series of operations of for example selecting the save attached file menu selecting one attached file selecting a shared folder as a save destination and clicking the save button may be included.

The detection unit may detect an input operation in any of the cases 28 1 to 28 3 by for example using a hook. Upon detecting an input operation in any of the cases 28 1 to 28 3 the detection unit notifies the determination unit of the content of the detected input operation. Thus the determination unit starts the process in .

The detection of a trigger to start the process in by the detection unit corresponds to the transition from S to S in .

Upon detecting the input operation in the case 28 1 the detection unit notifies the determination unit of the fully qualified path name of the file in the client PC in which the file is locally saved and the host name of the client PC as part of information indicating the content of the input operation. Thus the determination unit searches the file location table using the notified host name and the notified fully qualified path name as search keys to acquire the file ID 29 1 .

Alternatively upon detecting the input operation in the case 28 2 the detection unit notifies the determination unit of the fully qualified path name of the file in the first shared folder as part of information indicating the content of the input operation. Thus the determination unit searches the file location table using the fully qualified path name of the file in the first shared folder as a search key to acquire the file ID 29 1 .

As will become apparent from the following description with reference to an entry is added to the file location table through the previous writing of the file to the first shared folder. Thus when the determination unit searches the file location table using the fully qualified path name of the file in the first shared folder as a search key in the above manner an entry is found. Therefore the determination unit may acquire the file ID.

Upon detecting the input operation in the case 28 3 the detection unit acquires the message ID of an electronic mail having attached thereto a file to be saved in the shared folder and the file name of the file via for example the mail user agent. Further the detection unit notifies the determination unit of the message ID and the file name as part of information indicating the content of the input operation.

The determination unit may acquire the file ID 29 1 by searching the electronic mail management table using the notified message ID and the notified file name as search keys. This is because the process in has been performed in a manner similar to that in the first embodiment in response to the previous reception of the electronic mail at the client PC . For this reason an entry is found by the search through the electronic mail management table and the determination unit may acquire the file ID from the found entry.

The detection unit also notifies the determination unit of the fully qualified path name 29 2 i.e. the fully qualified path name of the shared folder to which the file is to be written as part of information indicating the content of the input operation. Therefore the determination unit may also acquire the fully qualified path name 29 2 . In the following for convenience of description the fully qualified path name of the shared folder is represented by for example srv shared Z.txt in Universal Naming Convention UNC format.

In addition the determination unit reads the access privilege settings of the shared folder identified by the acquired fully qualified path name 29 2 thereby acquiring the list 29 3 . Although a specific method of access control depends upon the OS the determination unit may acquire the list 29 3 from the property of the shared folder for example.

In the following for convenience of description the list 29 3 is specifically a list of account names of user accounts given read permission for the shared folder. For convenience of description furthermore the list 29 3 is referred to as an account list .

Then in S the determination unit initializes a warning list to empty. The warning list in the process in is also an example of information to be used by the determination unit to perform determination in S in .

Then in S the determination unit determines whether or not an account name that has not been focused on as a target to be subjected to the processing of S to S remains in the account list. When a yet to be focused account name remains the process proceeds to S. Conversely when all the account names have been focused on the process proceeds to S.

In S the determination unit focuses on one yet to be focused account name in the account list. Hereinafter the account name focused on in S is referred to as the account name of interest .

Then in S the determination unit determines whether or not the account name of interest has been registered as a non third party regarding a file to be written to a shared folder. Specifically the determination unit searches the member table using as search keys the file ID and the account name of interest acquired in S.

When an entry is found as a result of search the account name of interest has been registered as a non third party. Thus the process returns to S.

Conversely when no entries are found as a result of search the account name of interest has not been registered as a non third party. That is the account name of interest represents a third party for which a warning is to be issued. Thus the process proceeds to S.

In S the determination unit adds the account name of interest to the warning list. Then the process returns to S.

When all the account names in the account list have been focused on in S the determination unit determines whether or not the warning list is empty.

When the warning list is empty that is when all the users who may access a shared folder to which the file is to be written are non third parties for the file writing the file to the shared folder would not allow access to the file to be provided to a third party. That is there is no risk of information leakage.

Thus the determination unit notifies the permission unit and the registration unit that there is no information leakage to third parties and the process proceeds to S. The transition from S to S corresponds to the link from S to S in .

Conversely when the warning list is non empty that is when a file is made accessible from a third party by writing the file to the shared folder there is a risk of information leakage.

Thus the determination unit outputs the warning list to the warning unit and the process proceeds to S. The transition from S to S corresponds to the link from S to S in .

In S the permission unit permits the file to be written to a shared folder. That is the permission unit permits writing in accordance with the operation detected by the detection unit specifically any of the operations in the cases 28 1 to 28 3 .

In S furthermore the registration unit receives the file ID 29 1 and the fully qualified path name of the file written to the shared folder from the determination unit . The registration unit registers a pair of the received file ID and fully qualified path name into the file location table .

As described above the determination unit receives as part of the information used to acquire the file ID 29 1 the file name of the file to be written or the fully qualified path name including the file name that is the fully qualified path name of the original location from the detection unit . Therefore the determination unit may recognize the file name of the file to be written.

Accordingly the determination unit may acquire the fully qualified path name of the file written to the shared folder by concatenating the path delimiter and the file name with the fully qualified path name of the shared folder 29 2 acquired in S. The registration unit receives the fully qualified path name acquired by the determination unit in the above manner from the determination unit .

Then the registration unit adds a new entry that associates the file ID 29 1 with the fully qualified path name of the file in the shared folder to the file location table . Thus the registration unit registers the new location information concerning the file into the file location table . Then the process in ends.

On the other hand in S the warning unit issues a warning in accordance with the warning list received from the determination unit . For example when the warning list includes two account names the warning unit may display dialogs including the following dialogs 30 1 to 30 3 on a screen of the client PC .

 30 1 A warning message such as The users with the following two account names may access this shared folder but have not been registered as non third parties. There is a risk of information leakage to these two third party users. Do you really want to write the file to this shared folder 

The dialogs 30 1 to 30 3 given above are merely examples of a GUI for providing a warning. Any other GUI may be used. It is to be understood that the warning unit may issue an audio warning.

In addition to the issuance of a warning the warning unit instructs the input accepting unit to accept an input from the input device in response to the warning. Then in S the input accepting unit waits for an input for example a click of the Yes button or the No button in the example of the dialog 30 3 to be received from the input device .

When the input accepting unit accepts an input from the input device in response to the warning the process proceeds to S. Then in S the input accepting unit determines whether the accepted input is a permission input or a prohibition input.

When the input accepting unit accepts a prohibition input the input accepting unit sends a notification to the prohibition unit . Then the process proceeds to S.

Conversely when the input accepting unit accepts a permission input the input accepting unit notifies the permission unit and the registration unit that there is no information leakage to third parties. Then the process proceeds to S.

In S the prohibition unit stops writing a file to a shared folder. That is the prohibition unit prohibits a file from being written to a shared folder via a process according to the OS or application software. Specifically the prohibition unit may prohibit a file from being written to a shared folder by for example canceling the input given from the user to a process according to the OS or application software. Then the process in ends. It is to be understood that the mail user agent is also an example of a process according to application software.

On the other hand in S the registration unit acquires the file ID 29 1 and the warning list from the determination unit . Then the registration unit registers each account name in the warning list as a non third party. That is the registration unit adds an entry that associates for each account name in the warning list the file ID received from the determination unit with the account name to the member table .

After the member table has been updated the process proceeds to S. The registration of a new non third party into the member table in S is a specific example of the registration in S in .

According to the process in a situation where a file is written to a shared folder that may be accessed from a third party due to carelessness of a user resulting in information leakage occurring may be avoided. According to the process in furthermore no warnings are issued for the writing of a file to a shared folder that may be accessed only from a non third party. Therefore a situation where excessive generation of warnings reduces users operation efficiency may also be avoided.

As described above in the second embodiment a process similar to the process in the first embodiment is also performed. In the following a specific example of the management DB when a process similar to the process in the first embodiment and the process in are performed in certain order will be described with reference to .

 31 1 It is assumed that the host name of the file server is srv . Further it is assumed that a shared folder indicated by the fully qualified path name srv shared exists on the file server .

 31 2 It is assumed that a read permission for the shared folder indicated by the fully qualified path name srv shared is assigned to three user accounts respectively identified by the account names name A name B and name D . It is assumed that the account names name A name B and name D are the account names of the users of the client PCs and respectively.

 31 3 It is assumed that a user of the client PC performs an operation for writing a file identified by a file ID F000103 to the shared folder indicated by the fully qualified path name srv shared when the management DB is in the state of the management DB in . As indicated by the file location table in the management DB the client PC having the host name PC A locally saves the file identified by the file ID F000103 .

 31 4 The detection unit of the client PC detects the operation in the assumption 31 3 and the determination unit of the client PC starts the process in . Thus from the management DB in and from the assumption 31 2 the account name name D is added to the warning list and in S a warning is issued.

 31 6 As a result of the input in the assumption 31 5 described above in S an entry that associates the file ID F000103 with the account name name D is added to the member table .

 31 7 In S that follows S an entry that associates the file ID F000103 with location information indicated by the fully qualified path name srv shared Z.txt is added to the file location table . Then the process in ends.

In the case under the assumptions 31 1 to 31 7 described above the management DB changes from the state of the management DB in to the state of the management DB in .

As indicated in the file location table illustrated in the client PC having the host name PC B also locally saves the file identified by the file ID F000103 . Thus even when the file is written to the shared folder from the client PC rather than the client PC the management DB changes from the state of the management DB to the state of the management DB in a manner similar to the assumptions 31 4 to 31 7 .

Further the management DB in is specifically an example in a case under the following assumptions 32 1 to 32 6 

 32 2 It is assumed that a user of the client PC performs an operation for copying a file indicated by the fully qualified path name srv shared Z.txt to the client PC when the management DB is in the state of the management DB in . Specifically it is assumed that the fully qualified path name in the client PC at the copy destination is C path D Z copy.txt .

 32 3 In the first embodiment the process in is executed in response to as a trigger the copying moving or renaming performed locally in one host. In the second embodiment not only an operation similar to that of the first embodiment but also writing of a file to a local storage device from the shared folder which is performed by the copying moving or renaming operation becomes a trigger to start the process in . Thus the process in is started by the copying operation in the assumption 32 2 .

 32 4 In the assumption 32 2 described above an input of an instruction for performing the copying operation is given to the client PC . In S in thus the host name of the client PC i.e. PC D is acquired. In addition from the assumption 32 2 in S C path D Z copy.txt is acquired as the fully qualified path name in the copy destination.

 32 5 From the assumption 32 2 described above and the file location table in in S F000103 is acquired as the file ID of the file to be copied.

 32 6 From the assumptions 32 4 and 32 5 described above in S new location information indicated by a pair of the host name PC D and the fully qualified path name C path D Z copy.txt is associated with the file ID F000103 . That is a new entry that associates the file ID with the new location information is added to the file location table .

In the case under the assumptions 32 1 to 32 6 described above the management DB changes from the state of the management DB in to the state of the management DB in .

In the second embodiment in addition to in the assumption 32 3 when a file in a shared folder is renamed in the shared folder the process in is started. In the second embodiment furthermore the process in is started also when a file in a shared folder is copied or moved to another shared folder.

According to the second embodiment described above advantages similar to those in the first embodiment may be obtained. That is with regard to exchange of information via electronic mail a third party and a non third party are distinguished from each other regardless of whether the third party and the non third party are inside or outside the LAN managed by the management server . When there is a risk of information leakage to a third party a warning is issued.

In the second embodiment furthermore also with regard to exchange of information via shared folders within the LAN it is determined whether a user in the LAN who is able to access the shared folder is a third party or a non third party. When there is a risk of information leakage to a third party within the LAN via the shared folder a warning is issued. In the second embodiment therefore more excellent information protection performance than that in the first embodiment may be achieved.

Subsequently a third embodiment for reducing processing loads by narrowing down the targets to be monitored to files for which information leakage is likely to occur due to careless mistake will be described with reference to .

In the third embodiment the system in is implemented as a stand alone system. That is the management server in is not used in the third embodiment. Further each of the client PCs to in includes the system in .

In the following for convenience of description a description will be made mainly of the operation of the system in the client PC . However the client PCs and also perform processes similar to those in the client PC .

In either of the first embodiment and the second embodiment it is possible to suppress information leakage due to careless mistake. In the first embodiment and the second embodiment however the processing load on the management server and the processing load on the client PCs to are relatively high. The following reasons 33 1 to 33 7 are considered 

 33 1 In either of the first embodiment and the second embodiment the process in is performed each time a file is locally generated.

 33 2 In either of the first embodiment and the second embodiment the process in is performed each time an electronic mail with a file attached is received.

 33 3 In either of the first embodiment and the second embodiment the process in is performed each time an attached file is locally saved.

 33 4 In either of the first embodiment and the second embodiment the process in is performed each time a file is locally copied moved or renamed in a certain host.

 33 5 In the second embodiment in addition the process in is performed each time a file is copied or moved to a local storage device from a shared folder.

 33 6 In the second embodiment in addition the process in is performed each time a file in a shared folder is renamed in the shared folder.

 33 7 In the second embodiment in addition the process in is performed each time a file is copied or moved between two shared folders.

However for example a file locally generated in the client PC may be merely locally referred to in the client PC by the user of the client PC . That is all the generated files may not necessarily be attached to electronic mails to be sent from the client PC or may not necessarily be copied to shared folders.

Further the user of the client PC may merely read an attached file in a received electronic mail. That is all the electronic mails with files attached may not necessarily be forwarded. In addition an attached file in an electronic mail may not necessarily be attached to another electronic mail and sent to someone after the file is edited or directly attached to another electronic without being edited .

Further a file copied or moved from a shared folder to the client PC may not necessarily be copied or moved to another shared folder later or may not necessarily be attached to an electronic mail and sent to someone.

In the first embodiment and the second embodiment therefore while suppression of information leakage due to carelessness is ensured the processes in and are also performed for a file that is not sent outside from the client PC . Therefore the above processes place a large load on the client PC and the management server .

Of course it is not determined in advance whether or not there is a possibility of each individual file being sent outside from the client PC . In the first embodiment and the second embodiment therefore the processes in and are performed in the way described above in order to ensure suppression of information leakage due to carelessness. That is in the first embodiment and the second embodiment all the locally generated files are targets to be monitored and all the files to be locally saved via electronic mail or shared folders are targets to be monitored.

On the other hand for some reason it may be desirable that the processing load on the client PCs to and the management server be reduced. In the third embodiment therefore files to be monitored are narrowed down to reduce processing loads.

Specifically in the third embodiment the targets to be monitored are narrowed down to only files for which information leakage is predicted to be likely to occur due to careless mistake. In other words in the third embodiment files with a high risk of information leakage are monitored while files with a low risk of information leakage are not monitored.

In general it is expected that users are familiar with the content of files created by them. Therefore it is expected that users generally know who is a non third party and who is a third party for files created by them. Thus the risk of such users allowing leakage of their created files to third parties to occur due to their carelessness is relatively low.

On the other hand users are not necessarily familiar with the content of files created by other users and may not be aware of how sensitive the information included in the files is. When users are not familiar with the content of files they may not accurately recognize who is a non third party and who is a third party. As a consequence such users may allow leakage of information to occur due to their carelessness.

That is for a certain user a file for which information leakage is predicted to be likely to occur due to careless mistake is a file other than a file created by the user. In the third embodiment accordingly files to be monitored are narrowed down to files for which information leakage is predicted to be likely to occur due to careless mistake.

As described above the system according to the third embodiment is a stand alone system and is implemented in for example a single computer . Therefore a file for which information leakage is predicted to be likely to occur due to careless mistake is a file that has been generated outside the computer in which the system is implemented and that has been provided to the computer via the network . In the following for convenience of description such an externally originating file that has been externally provided is referred to as a foreign file .

Incidentally it is to be understood from the definition of the foreign file that information indicating the origin of a foreign file is not information for example IP address identifying the computer in which the system is implemented. It is also to be understood that information indicating the origin of a foreign file is not information for example electronic mail address or account name identifying the user of the computer .

Specifically information indicating the origin of a foreign file has different types depending on the origin of the foreign file. The information indicating the origin is also used as information indicating a non third parry that is the non third party identification information in .

Next a specific example of information used as the file identification information and the non third party identification information in according to the third embodiment will be described with reference to . In the third embodiment a foreign file management table illustrated in is a table used in place of the management DB according to the first and second embodiments.

Each entry in the foreign file management table associates a file with a non third party. Specifically each entry in the foreign file management table includes three fields that is file attribute type and attribute value .

The file field indicates the fully qualified path name of a file. In the third embodiment since the system in is a stand alone system each file included in a single host in which the system is implemented for example the client PC may be uniquely identified by the fully qualified path name of the file. That is the fully qualified path name in the file field is a specific example of the file identification information in .

The attribute type field indicates the type of the value in the attribute value field. The attribute value field indicates a non third party. That is the value in the attribute value field is a specific example of the non third party identification information in .

As described above in the third embodiment there are various types of information indicating the origin depending on the origin. In the third embodiment there are also various types of information indicating the non third party other than the origin. Thus the attribute type field indicates which type of information is registered in the attribute value field in the foreign file management table as the non third party identification information .

As specific examples illustrates by way of example six entries in the foreign file management table .

A first entry indicates that a non third party of a file identified by a fully qualified path name C path A1 Z1.txt is identified by an electronic mail address b foo.com .

That is the file indicated by the first entry is exchanged via electronic mail between the user identified by the above electronic mail address and the user of the host that stores the foreign file management table . Thus the attribute type field of the first entry stores a value representing electronic mail .

A second entry indicates that a non third party of a file identified by a fully qualified path name C path A2 Z2.txt is identified by a fully qualified path name in the UNC format srv shared X . That is according to the second entry all the users who may access the shared folder identified by the fully qualified path name srv shared X are non third parties of the file identified by the fully qualified path name C path A2 Z2.txt .

Further the file indicated by the second entry is exchanged via the shared folder between a user who may access the shared folder and the user of the host that stores the foreign file management table . The exchange of the file via the shared folder is specifically implemented by the copying moving or renaming operation of the file between the shared folder and the local storage device of the host that stores the foreign file management table . Thus the attribute type field of the second entry stores a value representing copy move rename .

A third entry indicates that a non third party of the file identified by the fully qualified path name C path A3 Z3.txt is identified by the identification information 123 456 7890 . In the example in it is assumed that the identification information 123 456 7890 is information identifying a recording medium such as a USB memory.

Some recording media are assigned identification information uniquely identifying the recording media and store the assigned identification information. The identification information may be read via for example a system tool or the like provided by the OS.

For example identification information concerning a certain type of USB memory is a combination of a vendor ID a product ID and a serial number. The identification information may be read as a Plug and Play PnP device ID via a system tool.

In the third entry as described above a non third party is indicated by identification information concerning a recording medium. In other words according to the third entry all the users who are expected to obtain the recording medium with authorization are non third parties.

The file of the third entry is exchanged between non third parties via the recording medium. The exchange of the file via the recording medium is specifically implemented by the copying moving or renaming operation of the file between the recording medium and a local storage device of the host that stores the foreign file management table . Thus the attribute type field of the third entry also stores the value representing copy move rename .

A fourth entry indicates that a non third party of a file identified by a fully qualified path name C path A4 Z4.txt is identified by a Fully Qualified Domain Name FQDN ftp.abcd.org . In the example in it is assumed that the host identified by the FQDN ftp.abcd.org is specifically the FTP server in .

In the fourth entry therefore a non third party is indicated by the FQDN identifying the FTP server . In other words according to the fourth entry all the users who may access the FTP server that is at least users who are authorized to download a file from the FTP server are non third parties.

The file indicated by the fourth entry is exchanged via the FTP server between a user who may access the FTP server and the user of the host for example the client PC that stores the foreign file management table . Thus the attribute type field of the fourth entry stores a value representing FTP .

A fifth entry indicates that a non third party of the file identified by the fully qualified path name C path A5 Z5.txt is identified by the FQDN www.efgh.com . In the example in it is assumed that the host identified by the FQDN www.efgh.com is specifically the HTTP server in .

In the fifth entry therefore a non third party is indicated by the FQDN identifying the HTTP server . In other words all the users who may access the HTTP server that is at least users who are authorized to download a file from the HTTP server are non third parties.

The file indicated by the fifth entry is exchanged via the HTTP server between a user who may access the HTTP server and the user of the host for example the client PC that stores the foreign file management table . Thus the attribute type field of the fifth entry stores a value representing HTTP .

A sixth entry indicates that a non third party of a file identified by a fully qualified path name C path A1 Z1.txt is identified by a fully qualified path name in the UNC format srv shared Y . As in the second entry also in the sixth entry the attribute value field indicates the fully qualified path name of the shared folder. Thus the attribute type field has the value representing copy move rename .

Here the fully qualified path names in the file fields of the sixth and first entries are the same. Thus not only the user having the electronic mail address b foo.com but also all the users who may access the shared folder indicated by the fully qualified path name srv shared Y are non third parties regarding the file indicated by the fully qualified path name C path A1 Z1.txt .

Therefore when a plurality of non third parties regarding a certain file are identified by different attribute values the foreign file management table includes a plurality of entries having equal values in the file fields.

In the fourth and fifth entries FQDNs are used as the non third party identification information . However it is to be understood that IP addresses may be used instead of FQDNs. Alternatively when access privilege settings differ depending on the folder in the FTP server information obtained by concatenating a path in the FTP server with an FQDN such as ftp.abcd.org aa bb may be used. The same applies to the HTTP server .

Subsequently processes performed in the third embodiment will be described with reference to . While for convenience of description a description will be given in the context of the operation of the system in that is implemented in the client PC in the client PCs and also perform similar operations.

The process in is specifically executed when a foreign file is saved in the client PC . For example the process in is executed in one of the following cases 34 1 to 34 5 

 34 2 A file is written to the client PC from a shared folder on the file server or the like through the copying moving or renaming operation.

 34 3 The recording medium is set in the drive device of the computer serving as the client PC and a file is written to the storage device from the recording medium through the copying moving or renaming operation.

More specifically in the case 34 1 similarly to the detection unit that detects the attached file saving operation as a trigger to start the process in according to the first embodiment the origin recognition unit detects a trigger to start the process in . For example upon detecting an attached file saving operation including a series of operations such as the operations 18 1 to 18 4 described with reference to the origin recognition unit starts the process in .

In some cases a plurality of attached files may be simultaneously specified as targets to be saved by the user. That is in the operation 18 2 1

In addition in the case 34 2 similarly to the detection performed by the detection unit which has been described with reference to the assumption 32 3 regarding the management DB in the origin recognition unit detects a trigger to start the process in . That is upon detecting the writing of a file from a shared folder to the client PC that is the writing of a file through the copying moving or renaming operation the origin recognition unit starts the process in .

In some cases a user may perform an operation for simultaneously writing a plurality of files from a shared folder to the client PC . In such cases the process in is performed for each of the files to be written.

In addition in the case 34 3 the origin recognition unit detects the writing of a file from the recording medium to the storage device of the client PC . That is the origin recognition unit detects the writing of a file from the recording medium to the storage device by using a method such as hooking a call to a command for copying moving or renaming or a call to an API function. Upon detecting the writing of a file from the recording medium the origin recognition unit starts the process in .

In some cases a user may perform an operation for simultaneously writing a plurality of files from the recording medium to the client PC . In such cases the process in is performed for each of the files to be written.

In addition in the case 34 4 the origin recognition unit detects a download of a file from the HTTP server to the client PC . Upon detecting a download of a file the origin recognition unit starts the process in .

For example the origin recognition unit may monitor the operation of a process according to an HTTP client software such as a web browser operating on the client PC and may detect a download of a file via HTTP from the HTTP server . In some cases a user may perform an operation for simultaneously downloading a plurality of files. In such cases the process in is performed for each of the files to be downloaded.

In addition in the case 34 5 the origin recognition unit detects a download of a file from the FTP server to the client PC . Upon detecting a download of a file the origin recognition unit starts the process in .

For example the origin recognition unit may monitor the operation of a process according to an FTP client software operating on the client PC and may detect a download of a file via FTP from the FTP server . In some cases a user may perform an operation for simultaneously downloading a plurality of files. In such cases the process in is performed for each of the files to be downloaded.

When the process in is started in the above manner in S the origin recognition unit acquires the following pieces of information 35 1 and 35 2 

 35 1 The fully qualified path name of the save destination of a file in the local storage device of the client PC .

For example in the case 34 1 the origin recognition unit may detect a trigger to start the process in by hooking the attached file saving operation performed on the mail user agent.

Then the origin recognition unit may acquire the fully qualified path name 35 1 from the content of the input operation performed by the user on the mail user agent. Further the origin recognition unit acquires the sender s electronic mail address as the external origin information 35 2 from the From header field of an electronic mail having attached thereto a file to be saved. The origin recognition unit further recognizes that the attribute type is electronic mail .

As given in the operations 23 1 to 23 7 by way of example the writing of a file through the copying moving or renaming operation is specifically performed via a command provided by the OS a GUI provided by the OS or a process according to application software.

In the case 34 2 therefore the origin recognition unit may detect an operation for copying moving or renaming a file by for example hooking a call to a command or a call to an API function. Further the origin recognition unit acquires the fully qualified path name 35 1 in the client PC from an argument of a command for copying moving or renaming or from an argument of the API function and the fully qualified path name of the shared folder serving as the external origin information 35 2 . The origin recognition unit further recognizes that the attribute type is copy move rename .

Similarly in the case 34 3 the origin recognition unit may detect an operation for copying moving or renaming a file by for example hooking a call to a command or a call to an API function. Further the origin recognition unit acquires the fully qualified path name 35 1 in the client PC from an argument of a command for copying moving or renaming or from an argument of the API function.

Further the origin recognition unit recognizes from an argument of the above command or API function that a file is written from the recording medium to the client PC . Therefore the origin recognition unit reads the identification number for example the PnP device ID of the recording medium serving as the external origin information 35 2 by using the system tool or the like provided by the OS. Further the origin recognition unit recognizes that the attribute type is copy move rename .

In the case 34 4 the origin recognition unit may acquire the content of the instruction given by the user to a process according to the HTTP client software by for example monitoring the operation of the process according to the HTTP client software. That is the origin recognition unit may acquire the fully qualified path name of the download destination of the file which is specified in the instruction given by the user to the process according to the HTTP client software as the fully qualified path name 35 1 . The origin recognition unit may monitor the operation of the process according to the HTTP client software by specifically hooking a call to an API function from the process according to the HTTP client software.

Further the origin recognition unit may extract from the Uniform Resource Identifier URI of a file that the user has instructed the process according to the HTTP client software to download the FQDN of the HTTP server that stores the file. The extracted FQDN is used as the external origin information 35 2 . Further the origin recognition unit recognizes that the attribute type is HTTP .

Further in the case 34 5 the origin recognition unit may acquire the content of the instruction given by the user to a process according to the FTP client software by for example monitoring the operation of the process according to the FTP client software. That is the origin recognition unit may acquire as the fully qualified path name 35 1 the fully qualified path name of the download destination of the file that the user has instructed the process according to the FTP client software to download. The origin recognition unit may specifically monitor the operation of the process according to the FTP client software by hooking a call to the API function from the process according to the FTP client software.

Further the origin recognition unit may extract from the URI of a file that the user has instructed the process according to the FTP client software to download the FQDN of the FTP server that stores the file. The extracted FQDN is used as the external origin information 35 2 . Further the origin recognition unit recognizes that the attribute type is FTP .

Accordingly in any of the cases 34 1 to 34 5 in S the origin recognition unit acquires the fully qualified path name 35 1 and the external origin information 35 2 . As described above furthermore the origin recognition unit also recognizes the attribute type. Then the origin recognition unit notifies the registration unit of the acquired fully qualified path name 35 1 the acquired external origin information 35 2 and the recognized attribute type.

Then in S the registration unit determines whether or not the information acquired by the origin recognition unit in S has already been registered in the foreign file management table . That is the registration unit searches the foreign file management table for an entry in which the value of the file field is the fully qualified path name 35 1 and in which the value of the attribute value field is the external origin information 35 2 .

When an entry is found as a result of search the information acquired in S has already been registered in the foreign file management table . Therefore the process in ends.

Conversely when no entries are found as a result of search the information acquired in S has not yet been registered in the foreign file management table . Therefore the process proceeds to S.

In S the registration unit registers the external origin information into the foreign file management table in association with the fully qualified path name in the file save destination and the attribute type. That is the registration unit adds a new entry to the foreign file management table . The registration unit sets the fully qualified path name 35 1 in the file field of the new entry the value of the attribute type notified from the origin recognition unit in the attribute type field of the new entry and the external origin information 35 2 in the attribute value field of the new entry. Then the process in ends.

Subsequently an output confirmation process performed when a file is to be output to a remote machine will be described with reference to . The process in corresponds to a specific example of the process in S to S in .

Here similarly to the above description a description will be given of a case where the system in is implemented in the client PC in by way of example. A file is specifically to be output to a remote machine in for example any of the following cases 36 1 to 36 5 . Thus the process in is started in any of the cases 36 1 to 36 5 

 36 1 One or more files locally saved in the client PC are attached to an electronic mail and the electronic mail is to be sent from the client PC .

 36 2 One or more files locally saved in the client PC are to be written to a shared folder on the file server or the like through the copying moving or renaming operation.

 36 3 One or more files locally saved in the client PC are to be written to the recording medium through the copying moving or renaming operation.

For example in the case 36 1 the process in is started in a manner similar to the case where the process in is started. Specifically when a user of the client PC performs an input operation for sending an electronic mail such as clicking the send button on the mail user agent the detection unit in the system on the client PC detects the input operation.

Upon detecting an input operation for sending an electronic mail the detection unit notifies the determination unit of information indicating the content of the detected input operation. Then the determination unit determines whether or not an electronic mail to be sent has a file attached. When one or more files are attached the determination unit starts the process in .

In the case 36 2 the process in is started in a manner similar to when the process in is started. That is when the user performs on the client PC an input operation for writing a file to a shared folder the detection unit detects the input operation.

The cases 28 1 to 28 3 where by way of example the process in is started are examples regarding the client PC . However it is to be understood that the detection unit of the client PC may also detect an input operation similar to those in the cases 28 1 to 28 3 performed in the client PC .

Upon detecting an input operation for writing a file to a shared folder the detection unit notifies the determination unit of information indicating the content of the detected input operation. Then the determination unit starts the process in .

In addition also in the case 36 3 the detection unit may detect an input operation for writing a file to the recording medium using a method similar to that in the case 36 2 . That is the detection unit detects an input operation for writing a file to the recording medium from the storage device of the client PC using a method such as hooking a call to a command for copying moving or renaming or a call to an API function.

Upon detecting an input operation for writing a file to the recording medium the detection unit notifies the determination unit of information indicating the content of the detected input operation. Then the determination unit starts the process in .

In addition in the case 36 4 the detection unit may detect an input operation for uploading a file to the HTTP server by monitoring the operation of a process according to the HTTP client software operating on the client PC .

For example in order to upload a file the user may perform a series of input operations such as clicking an upload button specifying the location of the file via a dialog and clicking an OK button. The detection unit may monitor the operation of the process according to the HTTP client software to detect that the above series of input operations has been performed. For example the detection unit may detect the above input operations by hooking a call to an API function for generating an HTTP request in which a POST method or a PUT method is specified.

Upon detecting an input operation for uploading a file to the HTTP server the detection unit notifies the determination unit of information indicating the content of the detected input operation. Then the determination unit starts the process in .

In addition in the case 36 5 the detection unit may also detect an input operation for uploading a file to the FTP server by monitoring the operation of a process according to the FTP client software operating on the client PC .

For example in order to upload a file the user may input a command. Alternatively the user may perform a series of input operations such as selecting the icon of the file via a GUI and clicking the upload button. The detection unit may monitor the operation of the process according to the FTP client software to detect that an input operation for uploading a file has been performed.

For example the detection unit may detect the above input operations by monitoring a key input from a command line. Alternatively the detection unit may detect the above input operations by hooking a call to an API function for generating an FTP request.

Upon detecting an input operation for uploading a file to the FTP server the detection unit notifies the determination unit of information indicating the content of the detected input operation. Then the determination unit starts the process in .

Accordingly in any of the cases 36 1 to 36 5 the detection unit detects an input operation of a user who wishes to output a file to a remote machine and the determination unit starts the process in .

Then in S the determination unit acquires the fully qualified path name of each file to be subjected to an operation and output destination information indicating an external output destination of the file. As described above the determination unit receives from the detection unit information indicating the content of the input operation detected by the detection unit . Thus the determination unit may acquire the fully qualified path name and the output destination information from the information received from the detection unit .

Specifically in the case 36 1 the fully qualified path name of each attached file in an electronic mail which resides on the client PC is acquired. Further all the electronic mail addresses specified in the To header field the CC header field and the BCC header field of the electronic mail are acquired as output destination information.

In the case 36 2 the fully qualified path name of each file to be written to a shared folder which resides on the client PC is acquired. Further the fully qualified path name of the shared folder is acquired as output destination information.

Further in the case 36 3 the fully qualified path name of each file to be written to the recording medium which resides on the client PC is acquired. In addition identification information such as the PnP device ID concerning the recording medium is acquired as output destination information.

Further in the case 36 4 the fully qualified path name of each file to be uploaded to the HTTP server which resides on the client PC is acquired. In addition the FQDN or IP address of the HTTP server is acquired as output destination information.

Further in the case 36 5 the fully qualified path name of each file to be uploaded to the FTP server which resides on the client PC is acquired. In addition the FQDN or IP address of the FTP server is acquired as output destination information.

Accordingly in S the determination unit acquires the fully qualified path name of each of one or more files to be subjected to an operation and one or more pieces of output destination information.

Then in S the determination unit determines whether or not a foreign file is to be output to a third party through an operation instructed by the user. The processing of S is a specific example of the processing of S in .

Specifically the determination unit determines whether or not each fully qualified path name acquired in S is stored in the file field of any entry in the foreign file management table . For example when N 1 N fully qualified path names have been acquired in S the determination unit performs the following process on each fully qualified path name j where 1 j N.

When the acquired j th fully qualified path name is not stored in any of the entries in the foreign file management table the file identified by the j th fully qualified path name is not a foreign file. Therefore the output of the file identified by the j th fully qualified path name to a remote machine is not to be subjected to warning.

Conversely when one or more entries in which the j th fully qualified path name is stored in the file field are found the file identified by the j th fully qualified path name is a foreign file. Thus the determination unit further determines whether or not each piece of output destination information obtained in S is stored in the attribute value field of any of the found one or more entries.

When there is a piece of output destination information that is not stored in the attribute value field of any of the found one or more entries the determination unit determines that the piece of output destination information indicates a third party . In this case the determination unit further determines that at least one foreign file is to be output to a third party through an operation instructed by the user .

Conversely when each piece of output destination information is stored in the attribute value field of some of the found one or more entries the determination unit determines that the foreign file identified by the j th fully qualified path name is to be output only to a non third party but is not to be output to a third party .

The determination unit performs determination for each of the acquired N fully qualified path names in a manner described above thereby determining whether or not there is a foreign file to be output to a third party .

When a foreign file to be output to a third party is found the process proceeds to S. In this case for each foreign file determined to be output to a third party the determination unit notifies the warning unit of a pair of the fully qualified path name of the foreign file and the output destination information that is determined to be a third party concerning the foreign file.

Conversely when there is found no foreign files to be output to a third party the determination unit notifies the permission unit that there is no information leakage to third parties. Then the process proceeds to S.

For example it is assumed that an electronic mail with two files attached is to be sent and that one electronic mail address is specified in each of the To header field the CC header field and the BCC header field of the electronic mail. In this case in S two fully qualified path names and three electronic mail addresses are acquired.

For example it is assumed that the fully qualified path name of a first attached file out of the two attached files has not yet been registered in the foreign file management table and the fully qualified path name of a second attached file out of the two attached files has been registered in the foreign file management table . In this case the determination unit determines for each of the three electronic mail addresses acquired as output destination information whether the electronic mail address indicates a third party or a non third party regarding the second attached file which is a foreign file. That is when an entry that associates the fully qualified path name of the second attached file with the electronic mail address is included in the foreign file management table the electronic mail address indicates a non third party when such an entry is not included the electronic mail address indicates a third party.

When all the three electronic mail addresses have been registered in the foreign file management table as non third parties of the second attached file the process proceeds to S. However when at least one of the three electronic mail addresses has not been registered as a non third party the process proceeds to S.

The above example is an example of sending an electronic mail in the case 36 1 . However it is to be understood that also in the cases 36 2 to 36 5 the determination unit may perform the determination of S by searching the foreign file management table using the fully qualified path name and the output destination information acquired in S.

In S the warning unit issues a warning in accordance with the information notified by the determination unit .

For example in an example of sending an electronic mail in the case 36 1 the warning unit may issue a warning similar to that in S in .

Further in the case 36 2 the warning unit may display for example a dialog including a warning message the Yes button and the No button. Examples of the warning message may include A file is to be written to a shared folder but this shared folder has not been registered as a non third party. There is a risk of information leakage to third parties through the writing of the file. Do you give a permission to write the file 

In addition the warning unit may acquire a list of account names of users who may access a shared folder from the property of the shared folder. Further the warning unit may display the acquired list together with the warning message.

Also in the cases 36 3 to 36 5 the warning unit may change the text of the warning message as appropriate and display a dialog similar to that in the case 36 2 .

It is to be understood that in any of the cases 36 1 to 36 5 the warning unit may display for the purpose of the reference of the user the fully qualified path name of each file determined by the determination unit to be a foreign file and to be output to a third party in accordance with the information notified by the determination unit . The warning unit may also issue an audio warning.

In any case in S the warning unit issues a warning. Then the warning unit instructs the input accepting unit to accept an input from the input device in response to the warning. Then in S the input accepting unit waits for an input for example a click of the Yes button or the No button to be received from the input device .

When the input accepting unit accepts an input from the input device in response to the warning the process proceeds to S. Then in S the input accepting unit determines whether the accepted input is a permission input or a prohibition input.

When the input accepting unit accepts a prohibition input the input accepting unit sends a notification to the prohibition unit . Then the process proceeds to S.

Conversely when the input accepting unit accepts a permission input the input accepting unit notifies the permission unit and the registration unit that there is no information leakage to third parties. Then the process proceeds to S.

In S the prohibition unit stops the operation instructed by the user. The prohibition unit may prohibit the operation instructed by the user and stop the operation by canceling the input operation from the user detected by the detection unit .

For example in the case 36 1 the prohibition unit may cancel an input given from the user via the mail user agent to prohibit an electronic mail from being sent.

Alternatively in the case 36 2 the prohibition unit may cancel an input for writing a file to a shared folder which has been given from the user via a process according to the OS or application software to prohibit the file from being written to the shared folder. Also in the case 36 3 the prohibition unit may cancel an input for writing a file to the recording medium which has been given from the user via a process according to the OS or application software to prohibit the file from being written to the recording medium .

In addition in the case 36 4 the prohibition unit may cancel an input given from the user via a process according to the HTTP client software to prohibit a file from being uploaded to the HTTP server . Further in the case 36 5 the prohibition unit may cancel an input given from the user via a process according to the FTP client software to prohibit a file from being uploaded to the FTP server .

When the prohibition unit stops the operation instructed by the user in S in the manner described above the process in also ends.

Further in S the registration unit acquires from the determination unit information indicating a target for which a warning is to be issued. Then the registration unit registers a new non third party into the foreign file management table in accordance with the information received from the determination unit .

Specifically the information received by the registration unit includes one or a plurality of pairs of the fully qualified path name of a foreign file that is permitted to be output to a remote machine and output destination information indicating a third party that has not yet been registered as a non third party. Thus the registration unit adds a new entry corresponding to each pair to the foreign file management table .

The registration unit sets a value as appropriate in the attribute type field of the added entry. For example the registration unit may query the detection unit about the type of the input operation detected by the detection unit .

For example when the detection unit has detected the input operation in the case 36 1 the registration unit sets the attribute type electronic mail . Further when the detection unit has detected the input operation in the case 36 2 or 36 3 the registration unit sets the attribute type copy move rename . In addition when the detection unit has detected the input operation in the case 36 4 the registration unit sets the attribute type HTTP . When the detection unit has detected the input operation in the case 36 5 the registration unit sets the attribute type FTP .

When a new non third party is registered in the foreign file management table in S in the above manner the process proceeds to S.

In S the permission unit gives a permission to execute the operation instructed by the user. Then the process in ends.

As a result of the processing of S the operation instructed by the user is executed via a process according to the OS or application software. Consequently a file is output to a remote machine. For example an electronic mail with an attached file is sent a file is written to a shared folder a file is written to the recording medium a file is uploaded to the HTTP server or a file is uploaded to the FTP server .

However according to the process in a file is output to a remote machine only when the file is not a foreign file when one or a plurality of output destinations have all been registered as non third parties or when a previous third party output destination has been newly specified as a non third party. According to the process in therefore a situation where a user unintentionally provides access to a foreign file to a third party due to carelessness may be avoided.

For efficient use of the storage device of the client PC an unnecessary entry in the foreign file management table may be deleted. Specifically the process in may be performed.

An OS provides a command such as a del command a menu for emptying the trash box or the like to delete a file. Thus upon detecting a call to the above command or menu provided to delete a file the detection unit notifies the registration unit of the content of the detected call. Then the registration unit starts the process in . The detection unit may detect a call to the above command or menu using for example a hook.

In S the registration unit acquires the fully qualified path name of a file to be deleted. The registration unit may acquire the fully qualified path name of a file to be deleted from the content notified by the detection unit .

The detection unit may recognize the fully qualified path name of a file to be deleted based on for example an argument of the command and the fully qualified path name of the current folder. Further a file in the trash box is associated with information indicating the fully qualified path name of a folder in which the file is originally placed. Thus the detection unit may recognize via for example the OS the fully qualified path name of the location of the file to be deleted before the file is moved to the trash box .

Then in S the registration unit determines whether or not the fully qualified path name notified by the detection unit has been registered in the foreign file management table . That is the registration unit searches the foreign file management table for an entry in which the notified fully qualified path name is stored in the file field.

When no entries are found as a result of search the file to be deleted is not a foreign file and information regarding the file to be deleted is not originally included in the foreign file management table . Thus the process in ends.

Conversely when an entry is found as a result of search the file to be deleted is a foreign file. Thus the process proceeds to S. As a result of search a plurality of entries may be found as in a case where for example the file identified by the fully qualified path name C path A1 Z1.txt is deleted in the example in .

In S the registration unit deletes all the entries registered in the foreign file management table regarding the file to be deleted i.e. all the entries found in the search in S from the foreign file management table . Then the process in ends.

In the third embodiment although not illustrated in the drawings when a file is locally copied moved or renamed in the client PC a process similar to the process in according to the first embodiment is performed.

Specifically the operations 23 1 to 23 7 described with reference to are detected by the detection unit . Further the detection unit acquires the fully qualified path name of the original file to be copied moved or renamed and a new fully qualified path name of the file i.e. the fully qualified path name in the copy destination the fully qualified path name in the move destination or the fully qualified path name of a renamed file . Then the detection unit notifies the registration unit of the acquired information.

Then the registration unit searches the foreign file management table using the fully qualified path name of the original file as a search key. When no entries are found as a result of search the registration unit does not update the foreign file management table . Conversely when one or more entries are found as a result of search the registration unit performs the following process on each found entry.

When the detected operation is a copying operation the registration unit adds a new entry in which the acquired new fully qualified path name is set in the file field and in which the same values as those in the entry found in the above search are set in the attribute type and attribute value fields. When the detected operation is a moving operation or a renaming operation the registration unit changes the value of the file field of the entry found in the above search to the acquired new fully qualified path name.

The registration unit updates the foreign file management table in the manner described above. Thus advantages similar to those in the process in according to the first embodiment may be obtained. That is even when a file is copied moved or renamed the system may keep track of the file and may manage the continuity of the file.

The embodiments discussed herein are not limited to the foregoing embodiments. While several modifications also have been described a variety of modifications may also be made to the foregoing embodiments in terms of for example the following points. The foregoing embodiments and the following modifications may be used in combination as desired unless a conflict occurs.

A first modification relates to the order in which processes are executed. The operations in each of the flowcharts described above may be reordered as desired unless a conflict occurs. In addition a plurality of operations that may be reordered may be executed in parallel. For example operations may be reordered in the following manner.

For example in S and S may be reordered. S and S may also be reordered. In addition in S may be executed prior to S or may be executed subsequent to S.

Moreover in the registration in S to S and the registration in S to S may be reordered. Further in S may be executed prior to S. In S and S may be reordered.

A second modification relates to the format and value of data. and to illustrate specific examples of various tables. Depending on the embodiment the tables may have configurations different from those in the examples described above. For example in and the number of columns differs between when location information is represented by a combination of a host name and a fully qualified path name in a host and when location information is represented by a fully qualified path name in the UNC format including a host name. Such a difference in the number of columns is also merely for convenience of illustration. In addition various pieces of data may not necessarily be managed using a table format.

For example in the member table includes three entries and the three entries have the same file ID. Thus the member table may be replaced with a table in which a list of non third party members is associated with a file ID.

Alternatively an associative array having a file ID as a key and a list of non third party members as data may be used instead of the member table . Alternatively in place of the management DB of the table format a DB having any other format such as an Extensible Markup Language XML DB may also be used.

The values illustrated in and to by way of example are merely for the purpose of illustration. For example the format of the file ID may differ depending on the embodiment. Further the format of the message ID also differs depending on the mail user agent or the like. The path notation also differs depending on the OS.

A third modification relates to the use of the account name. Specifically the first embodiment may be modified such that account names are not used.

For example in some cases such as when no shared folders are used in the LAN or when every user in the LAN has equivalent privileges for any kind of information no consideration may be given of information leakage via shared folders. Therefore account names may not necessarily be used. Specifically for example the first embodiment may be modified in the following manner.

In S in the origin recognition unit reads instead of the account name a sending electronic mail address from information set in a mail user agent installed on a machine in which the file has been generated. Then in S instead of the account name the sending electronic mail address is registered in the member table .

Further in S in the acquisition of the account name is omitted. Then in S the determination of whether or not a pair of a file ID and an account name has been registered in the member table is omitted.

Further in S in the acquisition of the account name is omitted. In addition S and S are also omitted.

A fourth modification relates to the determination of which electronic mail address is to be automatically registered as a non third party when sending or receiving an electronic mail.

In order to increase user convenience while reducing the number of times a warning is generated it is advantageous to automatically register as a non third party an electronic mail address indicating a user who is apparently considered to be a non third party. However even when the automatic registration of a non third party is omitted the generation of a warning merely involves a user performing a slightly time consuming operation while the risk of information leakage does not increase. This is in contrast to the risk of information leakage increasing once a third party is incorrectly registered as a non third party.

Therefore an electronic mail address satisfying a certain condition may be automatically registered as a non third party or automatic registration of such an electronic mail address may be omitted.

For example it is assumed that an electronic mail sent from the electronic mail address c bar.org by the client PC outside the LAN is received at the client PC within the LAN . It is also assumed that the electronic mail has a file attached. In this case according to the process illustrated in the sender s electronic mail address c bar.org is not automatically registered as a non third party.

In the above case however the sender of the electronic mail is apparently a non third party regarding the attached file. Thus in S which is executed when an electronic mail from outside the LAN managed by the management server is received the registration unit may also perform the following process.

That is the registration unit reads the sender s electronic mail address from the received electronic mail. Then the registration unit adds for each attached file an entry that associates the file ID issued in S with the read sender s electronic mail address to the member table . As a consequence for example in the above case the sender s electronic mail address c bar.org is automatically registered as a non third party.

Meanwhile as described above in the To and CC header fields of an electronic mail sent from the electronic mail address c bar.org one or more electronic mail addresses of an external domain of the LAN may be specified. Recipients in external domains indicated by the one or more electronic mail addresses of the external domain may be regarded as being permitted by the sender to access the attached file and may actually access the attached file. Thus such recipients may be regarded as non third parties. However according to the processes illustrated in when the sender s electronic mail address is an external domain address such as c bar.org electronic mail addresses in external domains included in the To and CC header fields are not automatically registered as non third parties.

Therefore in order to automatically register as non third parties electronic mail addresses in external domains included in the To and CC header fields the processing of S in may further be modified as follows. According to the following modification the occurrence of a warning in the future may further be suppressed.

That is the registration unit further reads all the electronic mail addresses included in the To and CC header fields of a received electronic mail. As a consequence one or a plurality of electronic mail addresses are obtained. Then the registration unit adds for each combination of an attached file and an electronic mail an entry that associates the file ID issued in S with the read electronic mail address to the member table .

Further conversely to the modification of S described above a modification may also be made in such a manner that automatic registration as a non third party is omitted. That is in the process in the electronic mail address in the BCC header field is also handled as a destination electronic mail address . However the electronic mail address in the BCC header field may not necessarily be handled as a destination electronic mail address .

That is according to the process in when the BCC header field includes an electronic mail address that has not been registered as a non third party in S a warning is issued. When a permission input is given from the user in response to the warning in S the electronic mail address is automatically registered as a non third party. However even when a permission input is given the electronic mail address specified in the BCC header field may be excluded from the target to be automatically registered as a non third party.

This is because in a certain specific situation the electronic mail address hidden with the use of the BCC header field may be made apparent due to the electronic mail address being automatically registered. Thus in order to respect the purpose of the BCC header field that the electronic mail address is hidden from other recipients the electronic mail address specified in the BCC header field may be excluded from the target to be automatically registered in S.

For example as described above it is assumed that the electronic mail addresses used for the client PCs to are a foo.com b foo.com and d foo.com respectively. It is also assumed that the values of the From To and BCC header fields of a certain electronic mail with a file attached are a foo.com b foo.com and d foo.com respectively.

In this case the user of the client PC is not able to recognize that the same electronic mail has also been sent to the user of the client PC even when the user refers to the header of the received electronic mail. However according to the process in in the following situation the user of the client PC may figure that the electronic mail address d foo.com may have been specified in the BCC header field of the received electronic mail .

For example it is assumed that the user of the client PC is to forward a received electronic mail to the electronic mail address d foo.com i.e. to the user of the client PC . Thus the process in is executed in the client PC . According to the process in however no warnings are issued. This is because the electronic mail address d foo.com has already been registered as a non third party through the process in previously executed in the client PC in response to the client PC sending an electronic mail.

The user of the client PC may understand that the electronic mail address of the transfer destination or d foo.com is a non third party electronic mail address because no warnings have been issued. On the basis of this understanding the user of the client PC may figure that the electronic mail address d foo.com may have been specified in the BCC header field of the received electronic mail . That is the electronic mail address hidden with the use of the BCC header field may be made apparent.

In order to respect the purpose of the BCC header field therefore the electronic mail address specified in the BCC header field may be excluded from the target to be automatically registered in S in .

In the above example a warning is issued when the user of the client PC is to forward an electronic mail to the electronic mail address d foo.com . Thus the user of the client PC is not able to figure that the electronic mail address d foo.com is specified in the BCC header field of the electronic mail received at the client PC . Accordingly the foregoing embodiments may be modified in a manner more suitable for the purpose of the BCC header field that is intended to hide an electronic mail address.

A fifth modification relates to an opportunity that various kinds of data are deleted in the first embodiment or the second embodiment. The process in is executed when a locally saved file is to be deleted and consequently an entry is deleted from the management DB . However an entry may be deleted from the management DB using as a trigger the deletion of a file from a shared folder or the deletion of an electronic mail.

For example in the second embodiment when a file is to be deleted from a shared folder by calling a command or menu for deleting a file the detection unit may detect a call to such a command or menu.

In this case the detection unit acquires as location information concerning a file to be deleted the fully qualified path name in the UNC format of a shared folder instead of the host name 25 1 and the fully qualified path name 25 2 in a host. Further the detection unit searches the file location table using the acquired fully qualified path name of the shared folder as a search key to acquire the file ID of a file to be deleted.

Then the detection unit notifies the registration unit of the fully qualified path name of the shared folder and the file ID. Thus the registration unit deletes the entry regarding the file to be deleted from the file location table . Subsequently processing similar to the processing of S to S in is performed.

Further when an electronic mail locally saved in a mailbox is to be deleted on a mail user agent the detection unit may perform a process similar to the process in . In this case the configuration of the electronic mail management table is also modified and the processes in are also modified. Specifically the following modifications are made.

First a counter field is added to each entry in the electronic mail management table . For example the value of the counter field of an entry including the message ID M000015 indicates the number of client machines in the LAN in which an electronic mail having the message ID M000015 is saved.

Thus in S in the value 1 is set in the counter field of each entry to be newly added to the electronic mail management table .

Similarly in S in the value 1 is set in the counter field of each entry to be newly added to the electronic mail management table . Further in S the value of the counter field is incremented by 1 in all the entries in the electronic mail management table which include the same message ID as the message ID acquired in S.

When an input for deleting a locally saved electronic mail is given from the user on a mail user agent the detection unit may detect the input. Then the registration unit may start a process similar to the process in using the detection performed by the detection unit as a trigger.

Specifically the detection unit reads from the Message ID header field the message ID of an electronic mail to be deleted. When an electronic mail to be deleted has one or more files attached the detection unit reads the file name of each attached file from the Content Disposition header field. Then the detection unit notifies the registration unit of the read information.

Thus the registration unit searches the electronic mail management table using the notified message ID as a search key. As a result of search one or more entries are found. Then the registration unit decrements the value of the counter field of each found entry by 1.

As a result of decrement when the value of the counter field of each entry found as a result of search becomes 0 the registration unit further performs the following operations 37 1 to 37 3 

 37 1 The registration unit reads the file ID of an attached file from each entry for which the value of the counter field is updated to 0 by the above decrement.

 37 2 The registration unit deletes from the electronic mail management table each entry for which the value of the counter field is updated to 0 by the above decrement.

 37 3 The registration unit searches for each file ID read in the operation 37 1 the file location table using the file ID as a search key in a manner similar to that in S in . When no entries are found in the file location table as a result of search similarly to that in S in the registration unit deletes the entries from the member table .

In the manner described above after the value of the counter field is decremented and after the operations 37 1 to 37 3 are performed depending on the situation the electronic mail is deleted in accordance with an instruction given from the user.

The fifth modification described above allows an unnecessary entry to be deleted from the management DB to more efficiently use a storage area.

A sixth modification relates to output of a file to a remote machine in the third embodiment. While the cases 36 1 to 36 5 are given as examples of the case where a file is output from the client PC to a remote machine in connection with other cases where a foreign file is output to a remote machine may also be given for example as the following 38 1 to 38 9 .

 38 1 An electronic mail with an attached file which has been received at the client PC is forwarded.

 38 2 An attached file in an electronic mail received at the client PC is directly saved in a shared folder on the file server .

 38 3 An attached file in an electronic mail received at the client PC is directly saved in the recording medium .

 38 4 A file in a shared folder is attached to an electronic mail and the electronic mail is sent from the client PC .

 38 5 A file in the recording medium is attached to an electronic mail and the electronic mail is sent from the client PC .

In the cases 38 1 to 38 9 described above when an operation instructed by the user is directly executed there is a risk of providing access to a foreign file to a third party due to carelessness of the user. According to the process in however no warnings are issued in the above cases 38 1 to 38 9 . The reasons are as follows.

In the third embodiment the system is a stand alone system. Thus a fully qualified path name in a host is used as the file identification information . In the above cases 38 1 to 38 9 however a foreign file to be output to a remote machine is not associated with the fully qualified path name thereof in the client PC as the file identification information . According to the process in therefore no warnings are issued in the above cases 38 1 to 38 9 .

Therefore the third embodiment may be modified as follows The detection unit may further detect an input operation by a user who is to output a foreign file directly to a remote machine without locally saving the foreign file temporarily as in the cases 38 1 to 38 9 . A specific example for detection will become apparent from the foregoing description of the first to third embodiments. For example the detection unit may detect an input operation in the cases 38 1 to 38 9 using a hook.

Upon detecting an input operation for outputting a foreign file directly to a remote machine the detection unit notifies the determination unit of the content of the detected input operation. Here when a foreign file is to be output directly to a remote machine an event for which a warning is to be issued has apparently occurred without even searching the foreign file management table by the determination unit .

Therefore upon receiving a notification from the detection unit notifying that an input corresponding to any of the cases 38 1 to 38 9 has been detected the determination unit outputs the content of the notification to the warning unit . Thus the warning unit issues a warning. For example the warning unit may display a dialog including a warning message such as A foreign file is to be output directly to a third party and there is a risk of information leakage. Do you want to continue this operation 

Further the warning unit instructs the input accepting unit to accept an input in response to the warning from the input device . Thus as in S in the input accepting unit waits for an input to be received from the input device .

When the input accepting unit accepts a prohibition input in response to the warning the input accepting unit sends a notification to the prohibition unit . Thus the prohibition unit stops the operation instructed by the user.

Conversely when the input accepting unit accepts a permission input in response to the warning the input accepting unit notifies the permission unit that there is no information leakage to third parties. Thus as in S in the permission unit permits execution of the operation instructed by the user.

According to the sixth modification described above even when a foreign file is to be output directly to a remote machine a warning is issued to suppress information leakage to any third party due to carelessness.

A seventh modification relates to whether the system in is a client server system or a stand alone system.

The first and second embodiments are examples of a client server system and the management server in is used as a server. Further the third embodiment is an example of a stand alone system and the management server is not used.

However in a modification of the third embodiment the system may be implemented as a client server system. That is the management server may hold three foreign file management tables corresponding to the client PCs to .

Further the management server may provide a DB interface to the registration unit and the determination unit of each of the client PCs to . Alternatively the third embodiment may be modified such that the registration unit and the determination unit are included in the management server .

Alternatively in other words from a different perspective the first embodiment or the second embodiment may be modified such that as in the third embodiment a file for which a warning is to be issued is limited to a foreign file.

Furthermore when the system is implemented as a client server system some information in the management DB may be backed up in the client PCs to . For example a file regarding an entry locally saved in the client PC among entries in the management DB may be backed up in the client PC .

In this case the determination unit of the client PC refers to a local backup copy in the client PC . Further the registration unit of the client PC updates both the management DB in the management server and the backup copy of the management DB in the client PC .

Alternatively each entry in the file location table other than entries indicating locations on a shared folder may be stored in a client machine indicated by the host name of the location information. That is the file location table may be distributed to the client PCs to and the management server .

Meanwhile an overview of various embodiments in terms of the common and different features between a client server system and a stand alone system will be discussed hereinafter.

In the following overview similarly to the description with reference to a process for providing access to a file from one or more third parties that are not non third parties registered in the storage device regarding the file is referred to as a specific process . Further an input for instructing execution of a specific process is referred to as a specific input . That is a permission input is an input for permitting the file to be accessed from the above one or more third parties and a prohibition input is an input for prohibiting the above access.

While the client PCs to may have similar configurations for convenience of description the client PC will be described. The client PC operates as a client machine when the system is a client server system and operates as the overall system when the system is a stand alone system. In either case the client PC executes the following protection process.

That is the client PC registers the origin of a file as a non third party regarding the file into the storage device . When both a specific input and a permission input are given the client PC registers each of the above one or more third parties as a non third party regarding the file into the storage device and further permits the specific process to be executed.

When both a specific input and a prohibition input are given the client PC prohibits the specific process from being executed. More specifically when a specific input is given the client PC may issue a warning and may accept a permission input or prohibition input as an input from the user in response to the warning. When a prohibition input is given in response to the warning the client PC may prohibit the specific process from being executed.

Here a specific example of the specific process is for example a process for sending an electronic mail in which the above one or more third parties are specified as destinations and to which the above file is attached. This process is more specifically a process for newly creating an electronic mail and sending the electronic mail or a process for forwarding a received electronic mail.

Another specific example of the specific process is for example a process for saving the above file in a folder such as a shared folder on the file server that the above one or more third parties are granted access privileges.

Still another specific example of the specific process is for example a process for when the origin of the above file is a first other computer transferring the above file to a second other computer different from the first other computer. For example the first other computer may be the HTTP server or the FTP server and the second other computer may be another HTTP server not illustrated or another FTP server not illustrated .

The non third party identification information is in other words permission target information indicating a target permitted to access the file. Thus the protection process performed by the client PC may be regarded as in other words a process including the following processes 39 1 and 39 2 

 39 1 A process of when transfer destination information indicating a transfer destination of a file stored in a storage device is not included in the permission target information prompting a user to input whether or not to permit the execution of transfer prior to the transfer of the file.

 39 2 A process of when an input indicating permission is performed using the input device of the client PC adding the transfer destination information to the permission target information and transferring the file.

For example a first controller that executes the process 39 1 may be implemented by the detection unit the determination unit and the warning unit . Further a second controller that executes the process 39 2 may be implemented by the input accepting unit the permission unit and the registration unit .

As may be understood from the specific examples of the specific process described above the transferring of the file described in the processes 39 1 and 39 2 may be specifically transferring performed through for example any of the processes 40 1 to 40 3 .

 40 2 Transferring a file to another computer for example the file server having a shared folder which is performed when a file is to be written to the shared folder.

In addition in the protection process the client PC may specifically recognize an origin to be registered as a non third party in the following way.

For example the client PC detects an operation of newly creating the above file and saving the file and may recognize as an origin the user who performs the creation operation. Alternatively when the file is an attached file in an electronic mail received at the client PC the client PC may recognize as an origin the sender of the received electronic mail.

In addition when the above file is a file copied from a shared folder the client PC may recognize an origin by detecting an operation of copying the above file from the shared folder and saving the copied file in the client PC . That is the client PC may recognize the shared folder as the origin of the file or may recognize as the origin each user who is granted access privileges to the shared folder.

The above file may also be a file downloaded from another computer for example the HTTP server or the FTP server . In this case the client PC may detect an operation of downloading the above file and saving the downloaded file in the client PC . Then the client PC may recognize the other computer as an origin.

In addition the above file may also be a file read from the recording medium to which unique identification information is assigned in advance. In this case the client PC may detect an operation of reading the above file from the recording medium such as an copying moving or renaming operation and may recognize the recording medium as an origin.

As a result of the recognition of the origin as described above by way of example the non third party identification information indicating an origin is registered in the storage device . In other words some information is added to the permission target information described in the processes 39 1 and 39 2 as a result of the recognition of an origin. Specifically for example the following processes 41 1 to 41 5 may be performed.

 41 1 When a new file is created information for example an account name identifying a user who performs an operation of creating a new file and saving the file in a storage device is added to permission target information concerning the new file.

 41 2 When an electronic mail with an attached file is received information i.e. electronic mail address identifying the sender of the electronic mail is added to permission target information concerning the attached file.

 41 3 In some cases a shared file stored in a shared folder for example a shared folder on the file server may be copied or moved to a storage device for example the storage device of the client PC . In these cases the information identifying the shared folder for example a path name in the UNC format may be added to permission target information concerning the shared file copied or moved to the storage device. Alternatively information for example an account name identifying each of one or more users who are granted access privileges to the shared folder may be added to permission target information concerning the shared file copied or moved to the storage device.

 41 4 In some cases a remote file on another computer for example the HTTP server or the FTP server may be downloaded and saved in a storage device for example the storage device of the client PC . In these cases information for example an FQDN or IP address identifying the other computer on a network is added to permission target information concerning the downloaded remote file.

 41 5 In some cases an existing file stored in a recording medium assigned unique identification information for example a PnP device ID may be read from the recording medium and may be saved in a storage device for example the storage device of the client PC . In these cases the unique identification information is added to permission target information concerning the existing file saved in the storage device.

As may also be understood from the foregoing description a non third party may be identified by various kinds of information. For example a non third party may be identified by either of or both the electronic mail address and the account name of a user serving as a non third party. Alternatively a non third party may be identified by computer identification information such as a host name a MAC address an IP address or an FQDN for identifying in an intranet or on the Internet a computer serving as a non third party. Alternatively a non third party may be identified by recording medium identification information such as a PnP device ID assigned to the recording medium serving as a non third party and stored in the recording medium .

That is transfer destination information to be added to permission target information in the process 39 2 may also be represented using as described above information identifying a non third party. Further the permission target information is stored in the management server in a client server system or in the client PC or the like in a stand alone system.

In addition the above file which is managed in association with a non third party is specifically a file that the client PC saves locally that is in the storage device of the client PC . Further the specific input the permission input and the prohibition input are specifically inputs given to the client PC from the input device that is the input device connected to the client PC .

The foregoing overview is the same regardless of whether the client PC operates as a client machine in a client server system or operates as a stand alone system. The different features between the above two cases are for example as follows.

In a case where the client PC operates as a client machine in a client server system the client PC itself may generate the file identification information . Alternatively the client PC may request the management server to generate the file identification information and may acquire the file identification information from the management server .

In contrast in a case where the client PC operates as a stand alone system the client PC may generate the file identification information by itself or may acquire the fully qualified path name of the file in the client PC as the file identification information .

In a case where the client PC operates as a client machine in a client server system furthermore the storage device in is the storage device of the management server that is specifically a computer different from the client PC . In this case the client PC determines whether or not the input given from the input device is a specific input by sending a query to the management server . Sending a query to the management server is specifically a process for referring to the management DB or the foreign file management table on the management server via the DB interface of the management server .

In a case where the client PC operates as a stand alone system in contrast the client PC uses the storage device which is locally provided in the client PC as the storage device in . For example the foreign file management table is stored in the storage device of the client PC .

Also in a case where the system is a client server system the registration management unit in may be implemented in a different manner in accordance with the embodiment. For example when the system is a client server system including the client PC and the management server the client PC includes the execution control unit and the input device and the management server includes the storage device . However the registration management unit is distributed to the client PC and the management server as desired in accordance with the embodiment.

For example in an embodiment all the components of the registration management unit may be included in the client PC and the management server may merely provide a DB interface for the registration unit and the determination unit . In another embodiment however the origin recognition unit and the detection unit may be included in the client PC and the registration unit and the determination unit may be included in the management server . In the latter case the management server may operate as the registration unit and the determination unit by specifically executing the following protection process in accordance with a program.

The management server registers the origin of a file that the client PC locally saves into the storage device as a non third party regarding the file. The management server may be notified of the origin by for example the origin recognition unit of the client PC .

Further the management server receives from the client PC a first notification for notifying the management server of the content of the input given to the client PC . Then the management server specifically the determination unit implemented on the management server determines whether or not the specific input has been given to the client PC in accordance with the received first notification. The management server refers to the storage device to perform the determination.

When the management server determines that the specific input has been given to the client PC the management server notifies the client PC that the specific input has been given to the client PC . This notification may be specifically sent to the warning unit of the client PC in form of for example a warning list.

Then the management server specifically the registration unit implemented on the management server receives from the client PC a second notification indicating whether or not a permission input has been given to the client PC .

When the management server determines that the specific input has been given to the client PC and the second notification indicates that a permission input has been given to the client PC the management server performs the following operation The management server specifically the registration unit implemented on the management server registers each of one or more third parties that are permitted to access the file by the permission input into the storage device as a non third party regarding the file.

That is since the preliminary settings of various policies such as an electronic mail policy and a shared folder policy are not made individually the burden placed on a user an administrator or the like is small. In addition since the execution of the specific process is not prohibited as a whole operation efficiency is not considerably reduced or users do not significantly feel inconvenienced. Moreover automatic registration of a non third party may suppress excessive generation of warnings and may reduce labor and time for a user to give an input in response to a warning.

Accordingly a user only suffers a small amount of detriment. Nevertheless according to the various embodiments described above information leakage due to carelessness of a user may be suppressed. This is because a user may be given an opportunity to intentionally consider whether or not to give a permission input before a file becomes actually accessible from a third party.

All examples and conditional language recited herein are intended for pedagogical purposes to aid the reader in understanding the invention and the concepts contributed by the inventor to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although the embodiments of the present invention have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

