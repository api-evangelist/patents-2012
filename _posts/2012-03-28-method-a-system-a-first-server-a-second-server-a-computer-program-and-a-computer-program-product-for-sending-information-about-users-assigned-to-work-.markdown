---

title: Method, a system, a first server, a second server, a computer program and a computer program product for sending information about users assigned to work on tasks in a computer network
abstract: The invention concerns a method for sending information about users assigned to work on tasks, wherein data sets comprising information about users and tasks the users are assigned to are stored in particular on a first server (), wherein a request for information about a user is received, in particular via a receiver (API) of said first server (), wherein said request comprises information about a predetermined task, wherein a test is performed, in particular by a processor () of said first server () to determine a data set comprising information about a user assigned to said predetermined task, wherein a reply is sent, in particular by a sender (API) of said first server (), depending on the result of said test, wherein said reply comprises information about said user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09438541&OS=09438541&RS=09438541
owner: Alcatel Lucent
number: 09438541
owner_city: Boulogne-Billancourt
owner_country: FR
publication_date: 20120328
---
The invention relates to a method a system a first server a second server a computer program and a computer program product for sending information about users assigned to work on tasks in a computer network.

Assigning tasks to users in a computer network is known for example from resource management computer programs. In such resource management computer programs typically projects are divided into tasks. Each task is assigned to one or more users. Datasets for example in databases are used to make such assignments. Said datasets for example comprise username and task name.

Typically the user of such resource management tool the users working on tasks and optionally managers supporting the users may access information about users and tasks via said resource management tool. However resource management systems are typically limited to provide static information about users working on tasks.

The object of the invention is thus to provide dynamic information about users working on tasks in said resource management system.

The main idea of the invention is thus to send information about users assigned to work on tasks wherein datasets comprising information about users and tasks the users are assigned to are stored in particular on a first server wherein a request for information about a user is received in particular via a receiver of said first server wherein said request comprises information about a predetermined task wherein a test is performed in particular by a processor of said first server to determine a dataset comprising information about a user assigned to said predetermined task wherein a reply is sent in particular by a sender of said first server depending on the result of said test wherein said reply comprises information about said user. This way dynamic information about said users is provided to said resource management system via said computer network.

Advantageously said reply is sent only if a dataset of a user assigned to said predetermined task is found. This avoids unnecessary network traffic.

Advantageously a request to assign a dataset comprising information about a predetermined user with a predetermined task is received in particular via said receiver of said first server. This way a storage storing said datasets is updated with the latest information about users and their assignments to tasks in said resource management system. This improves further the quality of the information sent.

Advantageously upon receipt of said request said dataset of said predetermined user is assigned with said predetermined task. This way a new task assignment is recorded in said dataset to improve reliability of the information sent.

Advantageously said request to assign said dataset is determined by a second server in particular during creation of a new task in a resource management computer program executing on said second server depending on input received upon prompting to select a user to be assigned to work on a predetermined task. This way any change to task assignments on said second server using said resource management computer program are provided to said first server for up to date information about users to be sent back to said second server.

Advantageously said reply is received and displayed by a second server. This way said resource management system integrates said user information sent by said first server.

Advantageously said information about said user comprises information about a geographical position of a device assigned to said user. This way dynamically additional information like the geographic position of a user is added to the information sent.

Advantageously said information about said user comprises information about an address of a device assigned to said user. This way said user may be reachable via said device using the address of said device.

Advantageously a communication connection request is sent do said address of said device assigned to said user. This way an easy way for connecting user assigned to the same task of said resource management computer program is provided.

Further developments of the invention can be gathered from dependent claims and the following description.

Said first server said second server and said device are connected for example via local area network LAN wireless local area network WLAN 802.11N or wide area network WAN .

Said connection is for example according to the well known internet protocol IP user datagram protocol UDP transmission control protocol TCP or a stream control transmission protocol SCTP .

Signaling is for example according to the well known simple object access protocol SOAP representational state transfer REST or session initiation protocol SIP or internet protocol multimedia subsystem IMS .

Addressing may be done using the well known uniform resource locators URL uniform resource identifiers URI names or namespaces of extensible markup language XML version 1.0 3rd edition W3C recommendation 8 December 2009 .

The connection can but must not be directly between the servers and the device. The typical use is on wide area networks with multiple intermediate devices where only said servers and said device are depicted in .

Said first server is adapted to store datasets comprising information about users. Furthermore said datasets comprise information about tasks the users are assigned to.

Said datasets for example comprise a user identifier for example a user name a task marker for example a string task . Said dataset optionally comprises an address of a device assigned to said user for example an IP address. Furthermore said dataset for example comprises a user information for example a GPS position from a device assigned to said user.

Furthermore said first server comprises a sender and receiver API for example an application programmable interface. Said sender and receiver API is adapted to send and receive messages according to any of the aforementioned protocols.

Said first server comprises a processor adapted to determine datasets comprising information about users assigned to predetermined tasks.

Said first server is for example adapted to upon receipt of a request for user information by said receiver determine said user information from said datasets via said processor and to send a reply comprising said information bout said user using said sender API.

Optionally said first server is adapted to receive frequent updates from devices of users having datasets stored on said first server . For example said first server is adapted to receive pushed or polled updates. For example said updates are regarding a GPS position of users having devices connected to said first server via said computer network . For example said updates are pushed or polled every minute.

Said first server is for example a server of an enterprise telecom system running a computer program providing said API and having a data base of telecommunication users.

Said second server is adapted to run a resource management computer program. Said resource management computer program is for example a computer program adapted to assign individual tasks of a project to individual users. To that end said second server may comprise a database storing information about tasks and users and the assignment of tasks and users.

Additionally said second server is adapted to send and receive messages to and from said first server for example using said application programmable interface of said first server.

Furthermore said second server is adapted to display replies received from said first server for example said information about said user. For example said second server is adapted to display said additional information like said GPS position next to said user s name in said resource management computer program.

Furthermore said second server may be adapted to establish a connection with a device assigned to a user. To that end said second server is for example adapted to receive said IP number from said first server as said information about said user and to send a request for a connection to said device of said user using said IP address.

Said second server is for example a server of a company who s worker use communication devices via said first server e.g. said enterprise telecom system.

Methods for resource management and computer programs for that are well known to the person skilled in the art and not explained further. Said device is adapted to connect to said first server via said computer network . For example said device is a mobile phone with a GPS sensor having an address for example an internet protocol address. Furthermore said device is adapted to send GPS data to said first server optionally. Said device may send said GPS data to said first server via pushing or polling mode.

Furthermore said device is adapted to receive connection requests for example using IP addresses. Said device is for example assigned by said company to said worker and registered with said enterprise telecom system.

Below methods for integrating resource management system and enterprise telecom system are explained. Goal is to create a way for participants of a task in said resource management system to access information about users of said device that is typically only available to the telecom system.

A first method for sending user information is described below making reference to . Goal of said first method is to create a link between a user of said resource management and said enterprise communication system preferably in real time.

Said message starts for example when a user of said resource management program adds a user to a task during creation of a new task or when modifying an existing task.

In said step a prompt for user input for example a window with a list of available users in order to select a user to be assigned to work on a predetermined task is displayed. Said task for example is identified by a task marker task . Said users are for example identified by said user identifier for example said user name.

In said step optionally a prompt for user input for example a checkbox is displayed next to said user to be assigned to work on said predetermined task. Said prompt for example requests confirmation to add said user to a communication group for said predetermined task.

Said step is optional. In said Step a test is performed to determine if said user input prompting confirmation for the addition of said user to said communication group is yes or no. For example said test determined via said checkbox is checked or not. In case said user shall be added to said communication group a step is executed. Otherwise the method ends. Ending in this context means that the regular resource management computer program continues with storing the information about said user and task assigned to without further information.

In said step a request to assign the dataset of the predetermined user with the predetermined task is sent to said first server . Said request for example comprises said task marker task and said user identifier for example said username. Afterwards a step is executed.

In said step a test is performed to determine whether a request to assign a dataset of a predetermined user with a predetermined task has been received for example via said receiver API. In case a request has been received a step is executed otherwise a step is executed.

In said step said dataset of said predetermined user is assigned to said predetermined user. For example said task marker task is stored in said dataset together with said user identifier for example said username. Afterwards the method ends.

In said step a timeout condition is monitored. In case said timeout condition is met said method ends. Otherwise said step is executed.

A second method for sending said user information is described making reference to . Goal of said second method is to use said link between a user of said resource management and said enterprise communication system to make updated information about said user from said telecom system available in said resource management system preferably in real time. This way ad hoc conferences with available workers of tasks can easily be scheduled workers tagged by said task marker may be found and communication may be routed by said enterprise telecom system automatically or position of users working on the task tagged with said task marker may be displayed in said resource management system.

Said method starts for example upon receipt of a request about information about a user assigned to a predetermined task. Said request for example contains said task marker task .

In said step a test is performed to determine if datasets containing said task marker for example task is available in said storage. In case a dataset containing said task marker is found a step is executed. Otherwise said method ends.

In said step said user information is determined for example said username is determined from said dataset.

In said optional step a test is performed to determine if said user information has been determined for all datasets containing said task marker. In case all user information from all datasets containing said task marker e.g. task have been determined a step is executed otherwise said step is executed.

Optionally said GPS data of one or all users are determined from said datasets and set in said steps and .

The methods described above may be implemented as computer programs and stored on computer program products.

The description and drawings merely illustrate the principles of the invention. It will thus be appreciated that those skilled in the art will be able to devise various arrangements that although not explicitly described or shown herein embody the principles of the invention and are included within its spirit and scope. Furthermore all examples recited herein are principally intended expressly to be only for pedagogical purposes to aid the reader in understanding the principles of the invention and the concepts contributed by the inventor s to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions. Moreover all statements herein reciting principles aspects and embodiments of the invention as well as specific examples thereof are intended to encompass equivalents thereof.

The functions of the various elements shown in the figures including any functional blocks labeled as processors may be provided through the use of dedicated hardware as well as hardware capable of executing software in association with appropriate software. When provided by a processor the functions may be provided by a single dedicated processor by a single shared processor or by a plurality of individual processors some of which may be shared. Moreover explicit use of the term processor or controller should not be construed to refer exclusively to hardware capable of executing software and may implicitly include without limitation digital signal processor DSP hardware network processor application specific integrated circuit ASIC field programmable gate array FPGA read only memory ROM for storing software random access memory RAM and non volatile storage. Other hardware conventional and or custom may also be included. Similarly any switches shown in the figures are conceptual only. Their function may be carried out through the operation of program logic through dedicated logic through the interaction of program control and dedicated logic or even manually the particular technique being selectable by the implementer as more specifically understood from the context.

It should be appreciated by those skilled in the art that any block diagrams herein represent conceptual views of illustrative circuitry embodying the principles of the invention. Similarly it will be appreciated that any flow charts flow diagrams state transition diagrams pseudo code and the like represent various processes which may be substantially represented in computer readable medium and so executed by a computer or processor whether or not such computer or processor is explicitly shown.

A person of skill in the art would readily recognize that steps of various above described methods can be performed by programmed computers. Herein some embodiments are also intended to cover program storage devices e.g. digital data storage media which are machine or computer readable and encode machine executable or computer executable programs of instructions wherein said instructions perform some or all of the steps of said above described methods. The program storage devices may be e.g. digital memories magnetic storage media such as a magnetic disks and magnetic tapes hard drives or optically readable digital data storage media. The embodiments are also intended to cover computers programmed to perform said steps of the above described methods.

