---

title: Method of improving efficiency of replication monitoring
abstract: Copy pair monitoring is provided for a storage system having plural host computers, at least one storage subsystem, and a management computer. The storage subsystem including volumes storing data requested by the host computer, the management computer being accessible to the host computer and the storage subsystem. The copy pair monitoring includes obtaining every piece of copy pair definition information that is stored in the host computer, removing duplicate copy pair definition information from the whole copy pair definition information obtained, and collecting the copy pair status based on the obtained copy pair definition information from which duplicate copy pair definition information has been removed. Each host computer is assigned a priority level, and, when more than one host computer includes the same copy pair, the host computer with the lowest priority obtains the copy pair information to reduce the load on the higher priority host computers.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08307179&OS=08307179&RS=08307179
owner: Hitachi, Ltd.
number: 08307179
owner_city: Tokyo
owner_country: JP
publication_date: 20120605
---
This application is a continuation application of U.S. application Ser. No. 13 243 551 filed Sep. 23 2011 now U.S. Pat. No. 8 195 902 which in turn is a continuation of U.S. application Ser. No. 11 599 299 filed Nov. 15 2006 now U.S. Pat. No. 8 078 814 the entire contents of which are hereby incorporated by reference.

The present application claims priority from Japanese patent application 2006 239929 filed on Sep. 5 2006 the content of which is hereby incorporated by reference into this application.

This invention relates to a storage system composed of a host computer a storage subsystem and a management computer and more specifically a technique of monitoring copy pairs.

The development of information oriented society has resulted in the introduction of computer systems everywhere and the amount of data processed by individual computer systems is growing at an explosive rate. Another result of the advance of information oriented society is the enhanced importance given to data that is handled by computer systems and data stored in computer systems is demanded to be high in reliability. Data stored in computer systems has to be protected against all kinds of disaster and it is a responsibility to society to prevent the loss of data stored in computer systems.

Such the computer systems ensure data reliability by storing the same data in multiple volumes. Data outputted from a host computer which executes processing is not only stored in a volume within a storage subsystem that is connected directly to the host computer but also copied to another volume to be duplicated.

Copy between a source volume and a target volume that are in the same storage subsystem is commonly called local copy whereas copy between a source volume and a target volume that are in different storage subsystems is called remote copy. Local copy and remote copy are employed in computer systems that are required to have high reliability.

Local copy and remote copy are collectively called replication. Replication enables a computer system to continue operating when a failure in one volume renders this volume inoperative with the use of data stored in the other volume.

Two volumes associated with each other by replication that is a source volume and a target volume are called a copy pair. The host computer stores definition information of volumes forming a copy pair to operate the copy pair and obtains information on the status of the copy pair based on the definition information.

For example US 2005 114467 A discloses techniques which allow a host computer to obtain replication status information of a remote site storage subsystem that is not directly connected to the host computer.

Monitoring of the copy pair status is important in order for the host computer to check whether replication operation is running properly.

For instance an application administrator such as a data base management system DBMS monitors copy pairs formed from volumes that are used by the application he she manages. A storage administrator monitors copy pairs constituted of volumes in storage subsystems he she manages.

It is common in this case that some copy pairs are monitored by the application administrator and the storage administrator both. Accordingly monitoring one storage system separately by an application administrator and a storage administrator results in an unnecessary workload on storage subsystems.

There are two types of copy pair monitoring method one in which information of every copy pair in a storage subsystem is obtained and one in which copy pair information is obtained according to copy pair definitions stored in the host computer or the like.

The former monitoring method puts unnecessary workload on storage subsystems since information of every copy pair in a storage subsystem is collected even when only a limited count of copy pairs need monitoring.

This invention has been made in view of the above and it is therefore an object of this invention to avoid an overlap in monitoring of copy pairs that are monitored by various administrators from different points of view.

According to a representative aspect of this invention there is provided a storage system including at least one host computer having a first processor for performing processing a first memory unit which is connected to the first processor a first interface connected to the first processor and a first interface connected to the first processor at least one storage subsystem having a second processor for performing processing a disk device which contains volumes storing data requested by the host computer to be written and a second interface connected to the second processor and a management computer having a third processor for performing processing a third memory unit connected to the third processor and a third interface connected to the third processor. The storage system being characterized in that a primary volume from which data is copied i.e. a source volume and a secondary volume to which data is copied i.e. a target volume create a copy pair the first memory unit of each host computer stores definition information of the copy pair which indicates an association between the primary volume and the secondary volume creating the copy pair and the third processor obtains every piece of copy pair definition information stored in the first memory unit removes duplicate copy pair definition information from the whole copy pair definition information obtained from the first memory unit collects the copy pair status based on the copy pair definition information from which the duplication copy pair definition information has been removed.

According to an aspect of this invention an overlap in monitoring of copy pairs is avoided and the monitoring workload on a storage system is thus lessened.

A first embodiment of this invention will be described with reference to to . It should be noted that this invention is not limited to the first and other embodiments described below.

The storage subsystem and the host computer are interconnected via a data network . The data network is a network for data communications in this embodiment a storage area network SAN . The data network can be other data communication networks than SANs for example an IP network.

The storage subsystem and the host computer are connected to the management computer via a management network . The management network is a network for data communications in this embodiment an IP network. The management network can be other data communication networks than IP networks for example a storage area network SAN .

The data network and the management network may be one same network. One computer may serve as the management computer and the host computer both.

The storage subsystem has a disk device and a disk controller . The disk device stores data requested by the host computer to be written. The disk controller controls processing of the storage subsystem .

The disk device has plural volumes here volumes A B C and D. The volumes A B C and D in the disk device are collectively and generically referred to as volume .

The volumes in this invention are not limited to a particular volume type and can be a hard disk drive HDD which is a physical storage area or a logical device which is a logical storage area. For convenience of explanation shows four volumes but the storage system can have as many volumes as necessary.

The volumes can form copy pairs. A copy pair includes one source volume and one target volume which stores a copy of data stored in the source volume .

The disk controller has a host I F a management I F a disk I F a main memory a CPU and a local disk .

The local disk is a disk device such as a hard disk that is connected to the disk controller . The local disk stores a storage microprogram and a copy pair definition table .

The storage microprogram is loaded onto the main memory of the disk controller and executed by the CPU . The storage microprogram controls copy pairs and collects the copy pair status as requested by the host computer .

Copy pair control exerted by the storage microprogram includes for example create synchronization and suspend . In create the storage microprogram creates a new copy pair. In synchronization the primary volume and the secondary volume are in sync with each other and data in the primary volume matches data in the secondary volume . In suspend the synchronization between the primary volume and the secondary volume is suspended. Create synchronization and suspend are terms used to indicate the status of a copy pair formed from the volumes and the copy pair status is fetched by the storage microprogram .

The copy pair definition table stores information on some of the volumes in the storage subsystem that form copy pairs. Details of the copy pair definition table will be described with reference to .

The storage microprogram and the copy pair definition table are stored in the local disk of the disk controller in this embodiment but this invention is not limited thereto. The storage microprogram and the copy pair definition table may be stored in for example a flash memory connected to the disk controller or the volumes in the disk device .

The host I F is a network interface that connects the storage subsystem to the data network . The host I F exchanges data and control commands with the host computer through the data network .

The management I F is a network interface that connects the storage subsystem to the management network . The management I F exchanges data and control commands with the host computer and with the management computer through the management network .

The host computer has a storage I F a display device a CPU an input device such as a keyboard and a mouse a management I F a memory and a local disk . The storage I F the display device the CPU the input device the management I F the memory and the local disk are connected to one another.

The storage I F is a network interface that connects the host computer to the data network . The storage I F exchanges data and control commands with the storage subsystem through the data network .

The management I F is a network interface that connects the host computer to the management network . The management I F exchanges data and control commands with the storage subsystem and with the management computer through the management network .

The local disk is a disk device such as a hard disk. The local disk stores an information collecting agent a recovery manager an application and a copy group definition table .

The copy group definition table shows information that defines a copy group obtained by grouping plural copy pairs together. The copy group will be described in detail with reference to .

One of reasons for defining copy group information in the host computer is security. In the case where plural corporations or the like use the storage subsystem in one storage system of for example an SSP Storage Service Provider and each corporation is allocated particular volumes the storage system unnecessarily collects information of copy pairs constituted of volumes that are used by other corporations when only copy pairs formed from the respectively allocated volumes need to be monitored. This poses a security problem.

It is therefore a common practice to define copy pair definition information in the host computer so that definition information of a copy pair to be monitored is retrieved from the host computer having this definition information and information on the copy pair is obtained based on the retrieved definition information. In this case when there is a change in copy pair configuration definition information is retrieved from the host computer and copy pairs are monitored periodically based on the retrieved definition information. A copy pair configuration change is for example an addition of a copy pair or a removal of a copy pair.

The information collecting agent the recovery manager and the application are loaded onto the memory in the host computer and executed by the CPU .

The application reads and writes data in the volumes in the storage subsystem . The application is for example a data base management system DBMS or a file system.

The recovery manager sends a request to the storage microprogram to control a copy pair or to collect the copy pair status. The function of the recovery manager to send requests to the storage microprogram to control a copy pair and to collect the copy pair status is provided by a command line interface an application programming interface or the like in order to allow an administrator or another program to execute the function.

The information collecting agent sends in response to a request made by a management program which is stored in the management computer information in the copy group definition table stored in the local disk to the management program .

The management computer has a management I F a display device a CPU an input device such as a keyboard and a mouse a memory and a local disk . The management I F the display device the CPU the input device the memory and the local disk are connected to one another.

The management I F is a network interface that connects the management computer to the management network . The management I F exchanges data and control commands with the storage subsystem and with the host computer through the management network in order to manage the storage subsystem .

The local disk is a disk device such as a hard disk connected to the management computer . The local disk stores a copy group definition table and the management program .

The copy group definition table is obtained from the host computer and is the same as the copy group definition table stored in the host computer . The copy group definition table may be stored in the memory of the management computer instead of the local disk .

The management program is loaded onto the memory in the management computer and executed by the CPU .

The management program obtains the copy group definition table from the host computer . The management program has a function of creating an information obtaining definition table a function of creating a copy group monitoring table and a function of displaying the status of a copy pair.

With the function of creating the information obtaining definition table the management program creates the information obtaining definition table in the memory from definition information of copy pairs that belong to a copy group registered in the obtained copy group definition table . With the function of creating the copy group monitoring table the management program creates the copy pair monitoring table in the memory based on the created information obtaining definition table . With the function of displaying the status of a copy pair the management program makes a graphical user interface GUI display the copy pair status to the administrator based on the created copy pair monitoring table .

The information obtaining definition table registers definition information of copy pairs that do not overlap and are registered in the copy group definition table . Details of the information obtaining definition table will be described with reference to . The management program fetches the status of a copy pair whose definition information is found in the information obtaining definition table .

The copy pair monitoring table registers the copy pair status collected by the management program . Details of the copy pair monitoring table will be described with reference to .

The copy pair definition table shows definition information of some of the volumes in the storage subsystem that form copy pairs. A copy pair includes one primary volume which is a source volume and one secondary volume which is a target volume and data stored in the primary volume is copied to the secondary volume .

The copy pair definition table contains in each row a volume ID a consistency group CTG ID a type a copy pair name a paired storage ID and a paired volume ID .

Registered as the volume ID is an identifier that is assigned to each volume in the storage subsystem . The identifier of each volume is unique throughout the storage subsystem where that particular volume is located.

Registered as the CTG ID is an identifier unique to each copy pair group in which data consistency has to be maintained. The storage subsystem assigns the same consistency group identifier to copy pairs that are not allowed to lose consistency through operation as members of the same group.

In this way when for instance a request to operate a copy pair belonging to a certain consistency group is sent from the host computer to the storage subsystem all other copy pairs included in this consistency group receive the same operation along with the copy pair that is designated by the received request. When a copy pair does not need to maintain consistency with other copy pairs nothing is registered as the CTG ID .

A copy group is similar to a consistency group in that copy pairs are grouped together. However copy pairs are grouped into a copy group by a unit that is specified by the administrator for example on a service application basis or on an operation basis such as a backup operation basis .

On the other hand copy pairs are grouped into a consistency group in order for the storage subsystem to operate copy pairs while maintaining the consistency among the copy pairs.

Consistency groups are created in the disk controller with the use of definition information registered in the copy group definition table which is stored in the host computer when the administrator defines the copy group definition table . Alternatively the creation of consistency groups may not be related to the defining of the copy group definition table .

Registered as the type is information that indicates whether the volume identified by the registered volume ID is the primary volume or the secondary volume .

Registered as the copy pair name is a name that is assigned to each copy pair. A copy pair is uniquely identified from the primary volume the storage subsystem that has this primary volume the secondary volume that constitutes this copy pair and the storage subsystem that has this secondary volume . However it is difficult for an administrator to manage a copy pair by its primary and secondary volumes and the storage subsystem having the primary and secondary volumes . It is therefore common for an administrator to assign a name to a copy pair and manage the copy pair by the assigned name.

In the case where the administrator manages copy pairs using the copy group definition table which is stored in the host computer there is no need for the administrator to refer to the copy pair definition table stored in the storage subsystem himself herself. Then copy pairs are not assigned names and the copy pair definition table does not contain the copy pair name .

Registered as the paired storage ID is an identifier unique to the storage subsystem having the volume that is identified by the registered paired volume ID .

Registered as the paired volume ID is an identifier unique to the volume that forms a copy pair with the volume identified by the registered volume ID .

Rows and of the copy pair definition table show copy pair definitions. In the case where the volume that is identified by the registered volume ID has plural paired volumes in other words when one volume is paired with plural volumes forming plural copy pairs definitions of the copy pairs constituted of the one volume are registered in plural rows of the copy pair definition table .

The storage system shown in has a two data center configuration which places data centers Site A and Site B in different sites. At least one storage subsystem is installed in each of the data centers.

For instance if a normal business operation or service is to be carried out in New York while data of the business operation is to be kept in New York and California a data center has to be placed in New York and California each.

In the data center Site A a storage subsystem A hereinafter referred to as SUB and a storage subsystem B hereinafter referred to as SUB are installed. Set in the data center Site B are a storage subsystem C hereinafter referred to as SUB and a storage subsystem D hereinafter referred to as SUB .

The SUB SUB SUB and SUB have the volumes . For example the SUB has a volume E and a volume F whereas the SUB has a volume G.

The volumes can form copy pairs. For instance the volume F in the SUB and the volume E in the SUB form a copy pair P. The volume F in the SUB and the volume G in the SUB form a copy pair P.

When a copy pair is formed from two volumes that are in the same storage subsystem data copy between these volumes forming the copy pair is called local copy. In the example of copy pairs between which local copy is executed are the copy pair P a copy pair P a copy pair P a copy pair P a copy pair P a copy pair P a copy pair P and a copy pair P.

When a copy pair is formed from two volumes that are in different storage subsystems data copy between these volumes forming the copy pair is called remote copy. In the example of copy pairs between which remote copy is executed are the copy pair P a copy pair P a copy pair P and a copy pair P.

Copy pairs are grouped into groups by for example service type in order to make them easier for the administrator to manage. Copy pairs grouped together because of having the same service type belong to the same copy group.

In a host computer A manages a copy group A and a copy group B . A host computer B manages a copy group C . A host computer C manages a copy group D .

The copy group A is constituted of the copy pair P the copy pair P and the copy pair P. The copy group B is constituted of the copy pair P the copy pair P the copy pair P the copy pair P the copy pair P and the copy pair P. The copy group C is constituted of the copy pair P the copy pair P the copy pair P and the copy pair P. The copy group D is constituted of the copy pair P the copy pair P the copy pair P the copy pair P the copy pair P the copy pair P the copy pair P the copy pair P and the copy pair P.

Each host computer stores for each copy group the copy group definition table which is definition information of copy pairs belonging to a copy group it manages.

Described next with reference to to are the copy group definition tables respectively stored in the host computer A the host computer B and the host computer C in . The copy group definition tables shown in to have the same configuration and the following description therefore takes the copy group definition table of as an example.

The copy group definition table contains in each row a host computer name a copy group name a copy pair name a primary storage subsystem name a primary volume ID a secondary storage subsystem name and a secondary volume ID .

Registered as the host computer name is the name of the host computer that stores the copy group definition table .

The name of a copy group is registered as the copy group name . Registered as the copy pair name is the name of a copy pair belonging to the copy group that is identified by the registered copy group name . The copy pair name may be omitted since each copy pair is uniquely identified from the primary storage subsystem name the primary volume ID the secondary storage subsystem name and the secondary volume ID . The copy pair name is contained in the copy group definition table commonly because it facilitates copy pair management for the administrator.

Registered as the primary storage subsystem name is the name of the storage subsystem having the volume that serves as the primary volume of the copy pair. Registered as the primary volume ID is the identifier of the volume that serves as the primary volume of the copy pair. Each volume is assigned an identifier unique throughout the storage subsystem that has the volume in question.

Registered as the secondary storage subsystem name is the name of the storage subsystem having the volume that serves as the secondary volume of the copy pair. Registered as the secondary volume ID is the identifier of the volume that serves as the secondary volume of the copy pair. Each volume is assigned an identifier unique throughout the storage subsystem that has the volume in question.

A row in the copy group definition table holds information that defines the copy pair P shown in a row holds information that defines the copy pair P shown in and a row holds information that defines the copy pair P shown in .

The copy group definition table of defines that the host computer A manages the copy group A constituted of the copy pair P the copy pair P and the copy pair P.

The copy group definition table that is shown in and stored in the host computer A defines that the host computer A manages the copy group B constituted of the copy pair P the copy pair P the copy pair P the copy pair P the copy pair P and the copy pair P.

The copy group definition table that is shown in and stored in the host computer B defines that the host computer B manages the copy group C constituted of the copy pair P the copy pair P the copy pair P and the copy pair P.

The copy group definition table that is shown in and stored in the host computer C defines that the host computer C manages the copy group D constituted of the copy pair P the copy pair P the copy pair P the copy pair P the copy pair P the copy pair P the copy pair P the copy pair P and the copy pair P.

In this embodiment definition information of one copy group is registered in one copy group definition table . Alternatively one copy group definition table may register definition information of copy pairs in all copy groups that are managed by the host computer that stores this copy group definition table .

The management program executes operation sequence shown in to create the information obtaining definition table and thereby deletes overlapping copy pairs from the copy group definition tables obtained from the respective host computers . The management program thus creates the information obtaining definition table in the memory of the management computer . When the management computer sends a request to collect the copy pair status to the host computers it is the status of copy pairs defined in the information obtaining definition table that is requested to be collected.

The information obtaining definition table contains in each row a host computer name a copy pair name a primary storage subsystem name a primary volume ID a secondary storage subsystem name and a secondary volume ID .

Registered as the host computer name is the name of the host computer that sends to the storage subsystem a request to fetch the status of a copy pair identified by the registered copy pair name .

The copy pair name the primary storage subsystem name the primary volume ID the secondary storage subsystem name and the secondary volume ID indicate the same names or IDs as in the copy group definition table and their descriptions will therefore be omitted.

The management program executes processing shown in to create the copy pair monitoring table and thereby creates the copy pair monitoring table in the memory of the management computer .

The copy pair monitoring table contains in each row a primary storage subsystem name a primary volume ID a secondary storage subsystem name a secondary volume ID and copy pair status .

The primary storage subsystem name the primary volume ID the secondary storage subsystem name and the secondary volume ID indicate the same names or IDs as in the copy group definition table and their descriptions will therefore be omitted.

Registered as the copy pair status is the status of a copy pair that is uniquely identified from the primary storage subsystem name the primary volume ID the secondary storage subsystem name and the secondary volume ID . For example PAIR SUSPEND or the like is registered as the copy pair status . PAIR indicates that the primary volume and the secondary volume are in sync with each other and that data in the primary volume matches data in the secondary volume . SUSPEND indicates that the synchronization between the primary volume and the secondary volume is in a suspended state.

The copy pair monitoring table in this embodiment contains the copy pair status but may hold other kinds of information such as the data matching ratio of volumes forming a copy pair.

Next a description will be given with reference to to on management screens used by the administrator to monitor copy pairs.

The host computer selecting screen is displayed on the display device of the management computer when the management program in the management computer is loaded onto the memory and executed by the CPU .

The host computer selecting screen contains checkboxes host computer name fields an execute button i.e. OK button and a cancel button .

The host computer selecting screen shows as many checkboxes and host computer name fields as the number of host computers registered in the copy group definition table by the host name .

When the host computer selecting screen is first displayed on the display device none of the checkboxes is checked. The administrator can check one or more checkboxes .

The execute button is enabled when the administrator checks one or more checkboxes . When enabled the execute button can be selected by the administrator. As the execute button is operated a copy group selecting screen shown in is displayed.

The copy group selecting screen is displayed on the display device when the management program stored in the management computer is loaded onto the memory and executed by the CPU .

The copy group selecting screen contains checkboxes host computer name fields copy group name fields an execute button i.e. OK button and a cancel button .

The copy group selecting screen shows as many checkboxes host computer name fields and copy group name fields as the number of copy groups that are registered in the copy group definition table by the copy group name and that are managed by the host computer chosen in the host computer selecting screen .

When the copy group selecting screen is first displayed on the display device none of the checkboxes is checked. The administrator can check one or more checkboxes .

The execute button is enabled when the administrator checks one or more checkboxes . When enabled the execute button can be operated clicked on by the administrator. As the execute button is operated a copy pair information displaying screen shown in is displayed.

The copy pair information displaying screen is displayed on the display device when the management program stored in the management computer is loaded onto the memory and executed by the CPU .

The copy pair information displaying screen contains a host computer name field a copy group name field a copy pair name field and a copy pair information field .

The copy pair information displaying screen displays the status of copy pairs that constitute a copy group chosen in the copy group selecting screen .

The copy pair information displaying screen in displays the status of copy pairs belonging to one copy group. When plural copy groups are chosen in the copy group selecting screen the copy pair information displaying screen displays the status of all copy pairs in the chosen copy groups.

Also the example of the copy pair information displaying screen shown in is of when only one host computer is chosen. When plural host computers are chosen on the other hand the copy pair information displaying screen displays the status of all copy pairs in copy groups that are managed by the chosen host computers .

The host computer name field displays the name of the host computer chosen in the host computer selecting screen . The host computer displayed in the host computer name field stores one or more copy group definition tables .

Displayed in the copy group name field is the name of the copy group chosen in the copy group selecting screen .

The copy pair name field displays the name of a copy pair belonging to a copy group that is displayed in the copy group name field .

Displayed in the copy pair information field is the status of a copy pair that is displayed in the copy pair name field .

The following description is about processing executed in the management computer from when the host computer selecting screen shown in is displayed until when the copy pair information displaying screen shown in is displayed.

As the host computer is chosen in the host computer selecting screen the management program refers to every copy group definition table to obtain the name of a copy group that is managed by the host computer chosen.

Specifically the management program selects from among all copy group definition tables ones whose host name matches the name of the chosen host computer . The management program next obtains the copy group name from each copy group definition table selected.

The management program displays the name of the chosen host computer in the host computer name field and displays each obtained copy group name i.e. copy group name in the copy group name field .

As copy groups are selected in the copy group selecting screen the management program obtains from the copy group definition table the copy pair name and copy pair definition information i.e. the primary storage subsystem name the primary volume ID the secondary storage subsystem name the secondary volume ID that are associated with each copy group selected.

Specifically the management program selects from among all of the selected copy group definition tables ones whose copy group name matches the name of any one of the chosen copy groups. The management program next obtains from each copy group definition table selected the copy pair name the primary storage subsystem name the primary volume ID the secondary storage subsystem name and the secondary volume ID .

The management program then chooses from the copy pair monitoring table every entry whose copy pair definition information matches the obtained copy pair definition information. From every chosen entry the management program extracts the copy pair status .

The management program displays the obtained copy pair name in the copy pair name field and displays the extracted copy pair status in the copy pair information field .

The display screens of to are in this embodiment displayed on the display device of the management computer but may be displayed on display devices of other computers. For instance the display device of the host computer may display the display screens shown in to .

The host computer selecting screen in this embodiment allows the administrator to choose one or more host computers out of all the host computers . Alternatively only a limited number of host computers may be chosen in the host computer selecting screen .

The administrator first accesses the management computer through one of the host computers in the storage system.

The assumption here is that the management computer stores a host computer IP address table which registers the IP addresses of the host computers .

When accessed by the host computer the management computer refers to the host computer IP address table to identify through which host computer the access has been made. The management computer then skips displaying the host computer selecting screen shown in and displays the names of copy groups managed by the host computer through which the access has been made in the copy group selecting screen shown in . The management computer next displays in the copy pair information displaying screen shown in the status of copy pairs belonging to copy groups that are selected in the copy group selecting screen .

The copy pair information displaying screen thus displays only the status of copy pairs belonging to copy groups that are managed by the host computer through which the access has been made. Since configuration information of these copy pairs and the copy pair status are not disclosed to the administrators of other host computers illicitly the security of the storage system is improved.

Instead of skipping displaying the host computer selecting screen of the management computer may fix the host computer selecting screen such that the administrator can only choose the host computer through which the access has been made.

The description given next is about processing in which the management computer obtains copy pair information.

The processing of obtaining copy pair information includes processing of creating the information obtaining definition table and processing of creating the copy pair monitoring table .

The processing in which the management computer creates the information obtaining definition table will be described in detail with reference to . The processing in which the management computer updates the copy pair monitoring table will be described in detail with reference to .

Processing in which the management computer creates the information obtaining definition table is described first.

The information collecting agent run in the host computer monitors the copy group definition table for a change. When there is a change in the copy group definition table the information collecting agent notifies the management program which is run in the management computer of the change in the copy group definition table .

Notified of the change in the copy group definition table the management program executes the processing of creating the information obtaining definition table . The processing of creating the information obtaining definition table may be executed upon instruction from the administrator to create the information obtaining definition table instead of upon notification from the information collecting agent .

First when notified of a change in the copy group definition table from the information collecting agent the management program collects the copy group definition table from every host computer . The management program stores each collected copy group definition table in the local disk Step . Instead of sending a notification of a change in the copy group definition table to the management program the information collecting agent may send the changed copy group definition table to the management program . The management program stores the received copy group definition table in the local disk .

Next the management program deletes information that has been registered in the information obtaining definition table stored in the memory thereby initializing the information obtaining definition table Step .

The management program then loads onto the memory every copy group definition table that has been stored in the local disk in the processing of Step Step 

For each copy group definition table loaded onto the memory the management program judges whether or not the table holds copy pair definition information i.e. the primary storage subsystem name the primary volume ID the secondary storage subsystem name and the secondary volume ID Step . Judging that the copy group definition table loaded onto the memory holds copy pair definition information the management program proceeds to processing of Step . On the other hand when it is judged that the copy group definition table loaded onto the memory does not hold copy pair definition information the processing of creating the information obtaining definition table is terminated.

In other words the management program executes the processing of Steps to as long as copy pair definition information is left in the copy group definition table loaded onto the memory .

When copy pair definition information is found in the copy group definition table loaded onto the memory the management program picks up definition information of one copy pair out of copy pair definition information that is held in the copy group definition table loaded onto the memory and deletes the picked up copy pair definition information from the copy group definition table Step .

The management program next creates a new entry in the information obtaining definition table . The management program registers the picked up copy pair definition information in the newly created entry Step .

Next the management program judges whether or not the same information as the copy pair definition information picked up through the processing of Step is held in other copy group definition tables than the one from which this copy pair definition information has been picked up Step . Judging that other copy group definition tables do not hold this copy pair definition information the management program returns to the processing of Step .

Judging that other copy group definition tables hold this copy pair definition information the management program deletes the copy pair information from those other copy group definition tables Step .

Copy pairs that have identical values in all of the primary storage subsystem name primary volume ID secondary storage subsystem name and secondary volume ID fields are deemed as the same copy pair irrespective of whether their copy pair names are the same or different.

The management program repeats the processing of Steps to until no copy pair definition information is left in the copy group definition table loaded onto the memory . When there is no more copy pair definition information left in the copy group definition table loaded onto the memory the management program ends the processing of creating the information obtaining definition table .

After the creation of the information obtaining definition table is completed the management program executes the processing of creating the copy pair monitoring table based on the created information obtaining definition table until a change occurs in the copy group definition table stored in the host computer .

The information obtaining definition table avoids registering information of the same copy pair more than once thereby preventing the management program from obtaining status information of the same copy pair twice or more in one round or cycle of information collecting. This makes it possible to provide a storage system that collects the copy pair status without burdening the storage subsystem with an excess load.

The processing in which the management computer updates the copy pair monitoring table is now described.

The processing of creating the copy pair monitoring table is processing in which the management program periodically collects the status of copy pairs registered in the information obtaining definition table and registers the collected copy pair status in the copy pair monitoring table . The cycle in which the management program collects the status of copy pairs registered in the information obtaining definition table may be set in the management program in advance or may be set by the administrator.

As the first step of this processing the management program secures an area in the memory to store a counter and initializes the counter to 0 Step . The counter is provided by a timer function of the management program .

Next the management program judges whether or not an instruction to end copy pair monitoring has been given from the administrator Step . Judging that the administrator has given an instruction to end copy pair monitoring the management program terminates the processing of creating the copy pair monitoring table .

On the other hand when it is judged that the administrator has not given an instruction to end copy pair monitoring the management program judges whether or not the counter has counted up the cycle for collecting the copy pair status Step . Judging that the counter has not finished counting up the cycle for collecting the copy pair status the management program returns to the processing of Step . In the processing of Step S the management program terminates the processing of creating the copy pair monitoring table when an instruction to end copy pair monitoring is given from the administrator within the cycle for collecting the copy pair status.

On the other hand when it is judged that the counter has counted up the cycle for collecting the copy pair status the management program collects the status of copy pairs registered in the information obtaining definition table Step .

Specifically the management program sends a request to collect the copy pair status to each host computer registered in the information obtaining definition table by the host computer name . This request contains copy pair definition information i.e. the primary storage subsystem name the primary volume ID the secondary storage subsystem name and the secondary volume ID .

Receiving the request the host computer implements the recovery manager . The recovery manager sends a request to collect the copy pair status to the storage subsystem that is specified in the request by the primary storage subsystem name and to the storage subsystem that is specified in the request by the secondary storage subsystem name .

Receiving the request the primary and secondary storage subsystems each execute their own storage microprograms . The storage microprogram that is executed in the primary storage subsystem fetches the status of the volume that is identified by the primary volume ID contained in the request. The storage microprogram that is executed in the secondary storage subsystem fetches the status of the volume that is identified by the secondary volume ID contained in the request.

The storage microprograms executed in the primary and secondary storage subsystems send the fetched status of the volumes to the host computer that has made the request. Receiving the status of the volumes the host computer identifies from the received status of the volumes the copy pair status of the copy pair definition information contained in the request. The host computer sends the identified copy pair status to the management computer .

The management computer thus collects the status of copy pairs registered in the information obtaining definition table .

The management program then makes the collected copy pair status reflected in the copy pair monitoring table Step and returns to Step .

A description will be given next with reference to to on a procedure that is employed by the administrator to monitor the copy pair status.

The description takes as an example a procedure in which the administrator of the application that is stored in the host computer A monitors copy pairs to be managed.

First the administrator calls up a monitoring function of the management program . The administrator can call up the monitoring function of the management program through for example the management computer .

As the monitoring function of the management program is called up the host computer selecting screen shown in is displayed. The administrator checks one or some of the checkboxes displayed on the host computer selecting screen that correspond to the host computers to be monitored in this example Host A and operates or clicks on the execute button i.e. OK button . As the execute button is operated the copy group selecting screen is displayed.

The administrator checks one or some of the checkboxes displayed on the copy group selecting screen that correspond to copy groups to be monitored in this example CG. A and operates the execute button . As the execute button is operated the management program collects from the copy pair monitoring table the status of copy pairs that belong to the selected copy groups and causes the copy pair information displaying screen to be displayed.

The copy pair information displaying screen displays the collected copy pair status. The administrator operates a close button to close the copy pair information displaying screen .

The copy pair information displaying screen in this embodiment displays the copy pair status only once and the displayed copy status information is not updated. However an update button may be added to the copy pair information displaying screen so that when the administrator operates the update button the management program again fetches the copy pair status from the copy pair monitoring table and makes the copy pair information displaying screen display the fetched copy pair status again.

Alternatively the management program may automatically update the copy pair information displaying screen at the intervals in which the copy pair monitoring table is created.

In this embodiment one host computer is chosen in the host computer selecting screen and one copy group is chosen in the copy group selecting screen . Alternatively plural host computers and copy groups may be chosen in the screens and respectively.

The information obtaining definition table is created in the first embodiment by deleting duplicate definition information of the same copy pair among copy pair definition information registered in the copy group definition tables . No two pieces of copy pair status information obtained from the thus created information obtaining definition table overlap.

In a second embodiment of this invention when every piece of copy pair definition information registered in one copy group definition table is found in any one of other copy group definition tables this copy group definition table whose every piece of copy pair definition information has a duplicate is deleted. Then the management program collects the status of copy pairs that are registered in the remaining copy group definition tables .

The second embodiment will be described with reference to and . In the second embodiment descriptions on the same components as those in the first embodiment will be omitted.

The configuration of a storage system according to the second embodiment of this invention is described with reference to .

The memory of the management computer in the second embodiment does not store the information obtaining definition table . The memory stores the copy group definition table and a definition count table instead.

The definition count table contains in each row a primary storage subsystem name a primary volume ID a secondary storage subsystem name a secondary volume ID and a definition count .

The primary storage subsystem name the primary volume ID the secondary storage subsystem name and the secondary volume ID indicate the same names or IDs as in the copy group definition tables of to and their descriptions will therefore be omitted.

Registered as the definition count is the number of times a copy pair is defined in the copy group definition tables . Specifically in the case where the same copy pair definition information is found in plural copy group definition tables loaded onto the memory a number indicating how many copy pairs have the identical copy pair information is registered as the definition count .

Processing in which the management computer obtains copy pair information consists of when every piece of copy pair definition information registered in one copy group definition table is found in any other copy group definition tables processing of deleting this copy group definition table and processing of updating the copy pair monitoring table .

The processing of updating the copy pair monitoring table in the second embodiment is the same as in the first embodiment and a description thereof will be omitted. Described here is processing that is employed by the management program to choose which copy group definition table is to be referred to in collecting the copy pair status.

The management program obtains the copy group definition table stored in the host computer and stores the obtained copy group definition table in the local disk . Stored in the memory of the management computer is a subset of the copy group definition tables after the management program executes processing shown in to choose which copy group definition table is to be referred to in collecting the copy pair status.

The management program first collects the copy group definition tables from the host computers through the information collecting agent and stores the obtained copy group definition tables in the local disk Step .

Next the management program deletes information that has been registered in the definition count table stored in the memory of the management computer thereby initializing the definition count table Step .

The management program then loads onto the memory every copy group definition table stored in the local disk Step 

The management program executes a processing of Step for every copy group definition table loaded onto the memory Steps and . After completion of the processing of Step for all copy group definition tables the management program proceeds to processing of Step Step .

The management program picks up copy pair definition information held in the copy group definition table loaded onto the memory and makes the picked up copy pair definition information reflected in the definition count table Step .

Specifically when the picked up copy pair information matches copy pair definition information registered in the definition count table the management program increments a value registered as the definition count in the definition count table . In the case where the picked up copy pair definition information matches none of the copy pair definition information registered in the definition count table the management program adds a new entry to the definition count table . The management program registers 1 as the definition count of the added entry and stores the picked up copy pair definition information in the added entry.

Through the processing of Steps to the management program creates the definition count table . The definition count table shows about each piece of copy pair definition information how many times in total the copy pair definition information in question has been defined in the copy group definition tables loaded onto the memory .

The management program next executes processing of Steps to to select from among the copy group definition tables loaded onto the memory ones that are necessary in collecting the copy pair status and to delete the copy group definition tables that are deemed unnecessary from the memory .

The management program executes the processing of Steps to for every copy group definition table loaded onto the memory Steps to . After completion of the processing of Steps to for all copy group definition tables the management program terminates the processing.

The management program chooses every entry of the definition count table that holds copy pair definition information identical with any piece of copy pair information registered in the picked up copy group definition table . From each chosen entry the management program extracts the definition count . The management program then judges whether or not the extracted definition count is equal to or larger than 2 Step .

Judging that the definition count is smaller than 2 i.e. when the definition count is 1 the management program returns to the processing of Step .

Judging that the definition count is 2 or larger the management program decrements the extracted definition count Step .

The duplicate copy group definition table is deleted from the memory by executing the processing of Steps to .

Thus the memory now stores a subset of the copy pair monitoring tables stored in the local disk . The management program collects the copy pair status based on copy pair definition information that is registered in the subset of the copy group definition tables stored in the memory . This enables the management program to collect the copy pair status without missing any copy pair. Further this causes the management program to generate less load while monitoring the storage subsystem than in the case where the copy pair status is collected with the use of every copy group definition table .

The storage systems according to the first embodiment and the second embodiment lessen the load on the storage subsystem by avoiding monitoring the same copy pair twice or more in one round of monitoring. However the storage systems according to the first embodiment and the second embodiment do not deal with a matter about which host computer is to be engaged in monitoring a copy pair when the copy pair is managed by more than one host computer .

In addition copy pair monitoring through the host computer burdens the host computer with the load of monitoring copy pairs. For instance when a copy pair is managed by the host computer where an application of a service is run and by the backup host computer the load of copy pair monitoring affects the service less if it is the backup host computer that collects the copy pair status.

In a third embodiment of this invention the administrator of the storage system sets an order of priority to the host computers . When the host computer that is given a high priority level and the host computer that is given a low priority level manage the same copy pair the host computer of low priority obtains copy pair information. A service is thus affected less by copy pair monitoring.

The third embodiment will be described with reference to and . In the third embodiment descriptions on the same components as those in the first embodiment will be omitted.

The memory of the management computer in a storage system according to the third embodiment of this invention stores a copy group priority table . The rest of the storage system according to the third embodiment is the same as the storage system according to the first embodiment of this invention and repetition of the same descriptions will be avoided.

The copy group priority determining screen is a graphical user interface GUI called up by the administrator.

The copy group priority determining screen contains a priority level input field a host computer name field a copy group name field an execute button i.e. OK button and a cancel button .

The priority level of a copy group is entered in the priority level input field . The priority level of a copy group is set by the administrator. For instance the administrator assigns a high priority level to a copy group that is used to provide a service and a low priority level to a copy group for uses that are not directly relevant to the service. The administrator may set a high priority level to a copy group to which only a few resources are available and a low priority level to a copy group to which a lot of resources are available. A larger value entered in the priority level input field means a lower priority level for the copy group whereas a smaller value entered in the priority level input field means a higher priority level for the copy group.

The priority level is entered on a copy group basis in the copy group priority determining screen shown in . Alternatively the priority level may be determined for each host computer so that copy groups that are managed by the same host computer are all given the same priority level.

The name of the host computer is entered in the host computer name field . The name of a copy group is entered in the copy group name field .

As the execute button is operated or clicked on the copy group priority table shown in is updated according to a priority level set in the copy group priority determining screen .

The copy group priority table contains a priority level a copy group name and a host computer name in each row.

A priority level is registered as the priority level . The name of a copy group is registered as the copy group name . Registered as the host computer name is the name of the host computer that manages the copy group identified by the registered copy group name . A larger value registered as the priority level means a lower priority level for the copy group whereas a smaller value registered as the priority level means a higher priority level for the copy group.

Processing of collecting the copy pair status according to the third embodiment consists of processing in which the management program creates the information obtaining definition table and processing in which the management program updates the copy pair monitoring table . The processing in which the management program updates the copy pair monitoring table is the same as in the first embodiment and a description thereof will be omitted.

Described here is a difference between the processing in which the management program creates the information obtaining definition table according to the third embodiment and the corresponding processing of the first embodiment.

The administrator calls up the copy group priority determining screen to set an order of priority to copy groups in advance. Once an order of priority is set to copy groups the copy group priority table is created in the memory .

Thereafter through the processing of Step in the processing of creating the information obtaining definition table shown in the management program loads the copy group definition tables onto the memory in descending order of values registered as the priority in the copy group priority table . In the case where the copy group priority table is as shown in the copy group definition table that is loaded onto the memory by the management program first is the copy group definition table that is associated with the copy group CG. 04 which is given a priority level 4 .

Next through the processing of Step the management program chooses the copy group definition tables one by one in an order in which the copy group definition tables have been loaded onto the memory . The management program repeatedly performs the following processing on the chosen copy group definition tables . From each chosen copy group definition table the management program extracts the host computer name the copy pair name and copy pair definition information.

The management program then creates a new entry in the information obtaining definition table through the processing of Step . The management program registers the extracted host computer name copy pair name and copy pair definition information in the newly created entry.

In this manner when a copy pair is managed by plural host computers definition information of copy pairs belonging to a low priority copy group is registered in the information obtaining definition table .

Accordingly when a copy pair is managed by plural host computers the host computer that manages a low priority copy group collects the copy pair status. A service application run in the host computer of high priority is thus less affected by copy pair monitoring.

While the administrator sets an order of priority to copy groups in the third embodiment a fourth embodiment of this invention has the management computer set an order of priority to copy groups according to a priority determining rule which is laid down in advance.

The copy group priority determining rule table contains a priority level high field and a priority level low field .

A rule for setting a high priority level is registered in the priority level high field . A rule for setting a low priority level is registered in the priority level low field .

The row holds a rule in which the priority level is determined by whether the volume constituting a copy pair is in the upstream or the downstream. Generally speaking an upstream volume is a source volume from which data is copied and a downstream volume is a target volume to which data is copied.

To give an example a volume A and a volume B form a copy pair with the volume A as the primary volume and the volume B as the secondary volume. The volume B is also paired with a volume C and the volume B serves as the primary volume of this copy pair while the volume C serves as the secondary volume.

In this case the volume A is an upstream volume to the volume B and the volume C. The volume B is a downstream volume to the volume A and an upstream volume to the volume C. The volume C is a downstream volume to the volume A and the volume B.

The most upstream volume the volume A is more often than not the volume that is directly related to a service application executed in the host computer . Accordingly when two volumes form a copy pair and have an upstream downstream relation the upstream volume is given a high priority level whereas a low priority level is assigned to the downstream volume .

The row holds a rule in which the priority level of a copy group constituted of copy pairs where remote copy is executed is set higher than that of a copy group constituted of copy pairs where local copy is executed.

In general a copy pair between which remote copy is executed is more likely to be affected by a failure than a copy pair between which local copy is executed. It is for this reason that the priority level of a copy group constituted of copy pairs where remote copy is executed is set higher than that of a copy group constituted of copy pairs where local copy is executed.

The rule held in the row may be modified such that the administrator sets the priority level of a copy group constituted of copy pairs where local copy is executed higher than that of a copy group constituted of copy pairs where remote copy is executed depending on the environment operation characteristics and other characteristics of the storage system.

The administrator can add an entry to the copy group priority determining rule table . The administrator can also remove an entry from the copy group priority determining rule table . This enables the administrator to add or delete a rule for determining the priority level to and from the copy group priority determining rule table .

In the processing of Step shown in when loading the copy group definition tables onto the memory the management program creates the copy group priority table according to the copy group priority determining rule table . Specifically the management program determines the priority level of a copy group according to rules registered in the copy group priority determining rule table .

The procedure of determining the priority level will be described taking as an example a case in which the copy group definition tables shown in to are respectively stored in the host computers of the storage system shown in . In the description A B indicates that the priority level of A is higher than that of B.

According to the rule of the row copy pairs where remote copy is executed i.e. P P P and P are assigned higher priority levels than those of copy pairs where local copy is executed i.e. P P P P P P P and P .

In the case of the storage system shown in not all of the copy groups are uniquely assigned a priority level by the rules held in the rows and . However copy pairs where remote copy is executed and that are the most upstream pairs P P P and P are given the highest priority level. Copy pairs where local copy is executed and that are the most upstream pairs P P P and P are given the second highest priority level. Copy pairs where local copy is executed and that are the most downstream pairs P P P and P are given the lowest priority level.

It is thus determined that the copy group constituted of the copy pairs P P and P is to have a higher priority level than that of the copy group constituted of the copy pairs P P P and P.

In the manner described above only definitions of copy pairs that would affect a service relatively little are registered in the information obtaining definition table without needing the administrator to set a priority level to each copy group. This means that when a copy pair is managed by plural host computers the host computer that manages a copy group of low priority collects the copy pair status. A service application run in the host computer that manages a copy group of high priority level is thus affected less by copy pair monitoring.

While the present invention has been described in detail and pictorially in the accompanying drawings the present invention is not limited to such detail but covers various obvious modifications and equivalent arrangements which fall within the purview of the appended claims.

