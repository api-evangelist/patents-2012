---

title: Method and apparatus for operating system event notification mechanism using file system interface
abstract: A method and structure for OS event notification, including a central processing unit (CPU) and a memory including instructions for an event notification mechanism for monitoring operating system events in an operating system (OS) being executed by the CPU. The OS includes a kernel having a plurality of kernel subcomponents that provide services to one or more applications executing in the OS in a user mode, using system calls to the kernel. The OS event notification mechanism is capable of monitoring events within the kernel, at a level below the user mode level. The OS event notification mechanism includes Application Program Interfaces (APIs) that are standard for the OS.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08935579&OS=08935579&RS=08935579
owner: International Business Machines Corporation
number: 08935579
owner_city: Armonk
owner_country: US
publication_date: 20120411
---
This Application is a Continuation Application of U.S. patent application Ser. No. 12 023 185 filed on Jan. 31 2008 now U.S. Pat. No. 8 201 029.

The present invention generally relates to a system for monitoring an operating system. More specifically a monitor mechanism based on a pseudo filesystem using standard filesystem interfaces and a file tree representation takes event requests from event consumers and forwards them to the producers receives event occurrence information from the event producers and notifies the event consumers of this information eliminating the need for periodic polling and specialized monitoring APIs.

System administrators in large data centers typically monitor the health of an operating system OS running on a computer server with centralized monitoring applications. Such a centralized monitoring application typically has an agent that runs in each OS instance and typically does periodic polling to collect OS health related data. This data is then analyzed by either the central application or by the agent in the monitored OS itself which typically relays the information to the central application. Whenever had health in a monitored OS is detected the central monitoring application generates an event to the system administrator. In the simple case this event can cause a notification e.g. email to be sent to the administrator or in a more sophisticated case a corrective action can be taken e.g. the execution of a specified program .

There are two major problems with the periodic polling approach of existing OS health monitoring applications 

To address the above problems several non polling event notification methods have been proposed in the past each requiring the application to use a specialized monitoring API Application Programming Interface to register its interest in being notified of an event and to get more details on an event after the event has occurred.

The problem with specialized monitoring APIs are that language bindings have to be developed and maintained for most of the predominant languages used for system management applications and there are many of these languages e.g. Perl C C Java Python etc. The complexity of having to maintain a specialized API over multiple versions of the OS and over multiple languages in an OS version and over multiple versions of each language that are supported within one OS version often deters the use of these specialized APIs by existing systems management tools.

Thus in view of these problems with polling and specialized APIs a need exists for a more efficient method of monitoring the health of operating systems preferably using a method that does not require polling and does not use specialized APIs.

In view of the foregoing and other exemplary problems drawbacks and disadvantages of the conventional systems it is an exemplary feature of the present invention to provide a method and structure for monitoring the health of an operating system without using periodic polling.

It is another exemplary feature of the present invention to provide OS monitoring without using a specialized monitoring API.

Therefore an exemplary objective of this invention is to provide an event notification mechanism that is efficient and flexible and does not require polling.

Another exemplary objective of the invention is to provide an event notification mechanism that can be used by a wide variety of applications using standard filesystem APIs and without introducing a new and additional set of specialized APIs.

To achieve the above exemplary features and objectives in a first exemplary aspect of the present invention described herein is an apparatus including a central processing unit CPU and a memory including instructions for an event notification mechanism in an operating system OS being executed by the CPU the OS event notification mechanism including a standard filesystem interfaces for event consumers to use for one or more of registering for an event notification receiving an event notification when each event occurs and getting details of an event that has occurred.

In a second exemplary aspect of the present invention also described herein is a method of notifying operating system events including providing standard filesystem interfaces for event consumers to use for one or more of registering for an event notification receiving an event notification when each event occurs and getting details of an event that has occurred.

In a third exemplary aspect of the present invention also described herein is a machine readable medium tangibly embodying a program of machine readable instructions executable by a digital processing apparatus to perform the above described method of notifying operating system events.

In a fourth exemplary aspect of the present invention also described herein is a network including a first computer operating an operating system including a method of notifying operating system events by the above described method and a second computer receiving the event notifications.

In a fifth exemplary aspect of the present invention also described herein is a service including at least one of monitoring a health of an operating system of a computer debugging a problem of said computer and developing software solutions for the operating system or a program executed by the operating system wherein the monitoring debugging or developing includes receiving event notifications of said operating system using the notification mechanism based on the above described method.

As will be clearer from the following description the present invention provides a number of advantages including that of providing far more useful information than existing software and being directly usable by any monitoring software that supports fileSystem interfaces e.g. open write select read close . . . . It also more effectively monitors time critical events so that prompt response actions can be taken before the system is doomed.

The present invention also achieves low overhead by using select call notification instead of periodic polling by all the users as well as providing flexibility because multiple consumers can monitor the same event each with a different threshold value without linearly increasing the overhead on the OS. Moreover multiple applications can benefit from the present invention including the integration into debugging tools to provide more sophisticated debugging capabilities to software developers.

Referring now to the drawings and more particularly to exemplary embodiments of the method and structures according to the present invention will now be described.

As mentioned above this disclosure describes a novel efficient and flexible mechanism and infrastructure to monitor OS events and to notify users asynchronously upon occurrences of their registered events without requiring polling and without requiring the need to create a new specialized API. This mechanism is intended to be used in monitoring applications that are written in any of the current predominant system management languages such as Perl PHP Python Java C C etc.

To eliminate the problems associated with periodic polling and those associated developing a new specialized API the present invention describes a novel efficient and flexible mechanism and infrastructure to monitor OS events and to notify users asynchronously upon occurrences of their registered events without requiring polling and without requiring the need to create a new specialized API. This mechanism can be used in monitoring applications that are written in any of the predominant monitoring languages as listed above.

Specifically the mechanism of the present invention is exemplarily based on the ubiquitous and standard filesystem APIs e.g. open write select read close etc. that are used for accessing files and filesystems.

It is noted that the standard file system interfaces are well defined and well known. For example they are part of the POSIX.1 specification POSIX stands for Portable Operating Systems Interface developed by the Open Group consortium whose members include IBM HP and SUN. This specification is also known as IEEE standard 1003.1 although it is noted that this standard covers a lot more Operating System services than just file system related services. One can see this standard at the single unix specification website.

However it is also noted that the present invention is not intended as confined to this one operating system specification or the exemplary embodiments described herein. Rather it is intended that the terminology standard filesystem interface refers to filesystem interfaces that are commonly available in the operating system environment of interest without resorting to specialized interfaces developed specifically for the purpose of OS monitoring.

In more details this invention includes a FileSystem FS which is herein referred to as the aha filesystem AHAFS for short to be used by monitoring applications. AHAFS is an acronym for Autonomic Health Advisor FileSystem.

This filesystem will present various system event producers in the Operating System OS as special directories referred to herein as monitor factory directories under the root directory aha e.g. see . The individual event instances served by the event producers are presented as leaf level file nodes referred to herein as monitor nodes. Each monitor node will be under one and only one monitor factory node.

The following sequence of actions describes how the event notification exemplarily occurs at a high level 

Major components in an exemplary typical operating system OS are depicted in the schematic of . An OS instance typically contains several applications . . . executing in user mode. The kernel comprises the core of the OS. The kernel itself consists of multiple subcomponents such as a process and thread Scheduler a Virtual Memory Manager VMM an I O subsystem a Logical Filesystem LFS layer multiple Physical Filesystems PFS a Networking subsystem and so on. The applications . . . access the services provided by the kernel via a set of interfaces called system calls .

These system calls will change the privilege level of the applications from user mode lower privilege level to kernel mode higher privilege level when they execute the services provided by the kernel. The FS system calls are a set of system calls that are provided by the LFS layer . Examples of FS system calls are open close read write select seek etc. It is noted that these FS system calls are well known in the art.

In the present invention when an application issues a FS system call on a file the LFS layer will identify the Physical Filesystem PFS corresponding to that file and invokes operations on that PFS. The operations are provided by the called virtual node vnode operations and Virtual FileSystem VFS operations.

It is noted that the terms vnode operations and vfs operations are part of the standard file system terminology in the Unix operating systems. The term virtual in this context implies that there is a level of indirection between the applications accessing the physical file system and the kernel kernel extensions that provide the physical file system. The present invention as implemented on Unix and like any other file system will also be accessed via the vnode and vfs operations. The present invention AHAFS appears to the operating system as a PFS and presents itself as a file tree to the monitoring applications as illustrated in .

This exemplary implementation is flexible and enables enhanced organization or house keeping by allowing several intermediate subdirectories to be created between the aha directory and the monitor factory nodes. Underneath each monitor factory node there can be one or more monitor nodes. Each monitor node represents a unique event that can be monitored by the event producer which can send notifications to the consumers.

Referring to the AHAFS framework spans both user and kernel layers of the OS. In the user layer reside one or more system management system monitoring applications . . . etc. within user space . Within the kernel layer the AHAFS can be implemented either inside the kernel or as a kernel extension . It is noted that the terminology kernel extension is specific to AIX which is a UNIX operating system in which an exemplary embodiment of this invention has been implemented. Other operating systems may have different terminologies for similar concepts. Of course the present invention is not Limited to the UNIX operating system or the exemplary terminologies shown herein as will be understood by one having ordinary skill in the art taking the discussion herein as a whole. In the exemplary embodiment shown in the AHAFS module is shown as installed in the Kernel Extension . This location arises from a choice to keep the Kernel to be as small as possible but there is no reason that the AHAFS module could not alternatively be installed in the Kernel .

The event producers reside in any of various subsystems of the kernel Scheduler VMM I O subsystem Logical Filesystem etc. Thus each subsystem can contain zero or more event producers. Though it is not discussed in the current embodiment the event producers can reside in a kernel extension also. When a kernel extension contains an event producer it informs the availability of that event producer to the kernel when it is initialized.

The monitoring applications . . . in the user space will communicate with the AHAFS module via the standard filesystem interfaces available in the form of system call services . The system call services will in turn invoke the AHAFS services via virtual node vnode operations and virtual filesystem vfs operations . The order of the invocation of services and the specific service invoked in each stage are given in later figures as exemplary flow charts and described in more detail in the following paragraphs.

The AHAFS module communicates with the Event Producers using a separate registration function for each event producer determined at the time of initializing the AHAFS module. The event producers communicate with the AHAFS module via callback functions given in the registration functions. The details of what information is exchanged between the AHAFS module and the event producers are specific to each event producer.

In step AHAFS vmount service will check the correctness of the parameters and performs the initialization of the AHAFS. This initialization involves identifying the event producers in the kernel allocating memory for the data structures and setting the function pointers and fields in several data structures. Once the mount operation is successfully completed the event consumers can use the AHAFS to register for event notifications.

In step a monitoring application registers for an event by issuing an open on the corresponding .mon file.

In step the OS s logical filesystem layer will notify AHAFS about the open request via a vnode operation interface.

In step the system call of the logical filesystem will return a file descriptor corresponding to the opened file to the consumer application.

The event consumer then writes an event specific value into the file using the write system call in step . This value can be an integer floating point string or a combination depending on the type of the event.

In step AHAFS gets the contents of the write buffer and interprets the contents according to the event type. For example if the event is to notify the event consumer whenever a filesystem utilization crosses a threshold then the value in the write buffer is interpreted as an integer. Once the write buffer is parsed AHAFS stores the contents into its internal data structures. AHAFS does not pass on the event request to the event producer until the event consumer makes the select system call.

In step the event consumer calls the select interface with the file descriptor it received from the previous open call to inform AHAFS to start monitoring the event.

In step AHAFS receives the select call and decides whether to forward the event request step immediately or to keep it in its inventory of event notification requests. AHAFS will not forward the request immediately if it has already sent an event request from another consumer to the event producer. In this exemplary embodiment at any given point in time an event producer has at most one event request for a given event instance.

When AHAFS sends an event request to the event producer it will also pass a callback function address along with the event request so that when the event occurs the event producer can inform AHAFS by invoking the callback function. Some event producers can inform AHAFS if the event condition has already been met using the return value. If the event condition is already met then the event consumers will be notified step .

In step the event producer informs AHAFS of the event details using the callback function provided earlier.

When AHAFS receives the event details it identifies the list of event consumers that need to be notified in step . Note that there may be more than one event consumer that needs to be notified. AHAFS forwards only one request to the event producer and keeps the remaining consumers in its own queue. Also depending on the event type not all event consumers that have registered for an event need to get notification for a given event occurrence.

As an illustration if the event producer is utilFs i.e. triggering an event whenever the utilization of a filesystem crosses a consumer specified threshold and the current utilization is 90 then only those event consumers which have registered for thresholds greater than or equal to 90 should be notified. So when the event producer invokes the callback function AHAFS will search through its queue to identify all the consumers that need to be notified as a result of this event occurrence 90 full . For each of the identified consumers AHAFS prepares the data area so that the next read operation by those consumers will provide them with the event s details.

In step AHAFS checks its queue to see if there are remaining event consumers and if there are AHAFS will re register the event at the event producer.

Another advantage of using filesystem interfaces between the event consumers and AHAFS is that the cleanup is easy in case of abnormal termination of the event consumers as exemplarily shown in the flowchart of .

When an event consumer terminates abnormally as shown in step the OS notifies AHAFS via the close vnode operation in step that a file descriptor needs to be closed

In step AHAFS will identify the consumer process and will check if this consumer process has an event registration at the event producer. If it has and if this process is the only event consumer then AHAFS will recall that registration. If there are one or more other consumers registered for the event after the current consumer has closed the file descriptor then AHAFS will re register the event with the event producer with appropriate parameters.

In step if there are no remaining event consumers for this event after removing the current consumer then AHAFS will free up its own data areas maintained for the monitor node.

Taking the above descriptions as guidelines an exemplary embodiment of the present invention might include a method of monitoring an operating system by providing standard filesystem interfaces for event consumers to use for one or more of registering for event notifications of a set of events receiving vent notification when each event occurs and getting details of events that have occurred. The embodiment could also include a file tree representation of a list of events available for the event notifications as illustrated in . The embodiment could also include providing a pseudo filesystem for taking event requests from event consumers and forwarding them to producers receiving event occurrence information from the event producers and notifying the event consumers of this information.

The exemplary embodiment could further include providing a registration function and a callback function to the pseudo filesystem from an event producer for event consumers to get notifications when an event occurs.

As shown in the Unix based example of the file tree representation could include predetermined naming conventions to explicitly identify the event producers and event instances and predetermined special nodes in the tree to help event consumers identify the file pathname of a specific event instance they are interested in monitoring. The naming conventions could identify event producers by adding a predetermined extension to a directory name and identify event instances by adding a predetermined extension to a filename.

In the Unix based example the predetermined directory name extension is .monFactory and the predetermined filename extension is .mon but other conventions could be used.

In an exemplary embodiment the standard filesystem interfaces could include one or more of an interface to obtain a handle to a monitor node corresponding to an event instance an interface to indicate event triggering criteria specific to an event type an interface to wait until an event occurs an interface to read an event s specific details after the event has occurred and an interface to release a handle to the monitor node corresponding to an event instance.

As examples the interface to obtain a handle to a monitor node corresponding to an event instance could be the open interface the interface to indicate event triggering criteria specific to an event type could be the write interface the interface to wait until an event occurs could be the select interface the interface to read an event s specific details after the event has occurred could be the read interface and the interface to release a handle to the monitor node corresponding to an event instance could be the close interface.

Even though the system has exemplarily been implemented using the file system interfaces exemplary listed above this listing and examples are not limiting. Other examples of standard file system interfaces might include for example poll instead of select or ioctl instead of read write to achieve the same result. Other file system interfaces might include setattr getattr etc.

The pseudo filesystem could also include one or more of a facility to aggregate multiple event requests from multiple event consumers into one request to the event producer a mechanism to provide non destructive reads to the event consumers and a mechanism to provide a stack trace of a program that caused an event to be triggered.

The CPUs in are interconnected via a system bus to a random access memory RAM read only memory ROM input output I O adapter for connecting peripheral devices such as disk units and tape drives to the bus user interface adapter for connecting a keyboard mouse speaker microphone and or other user interface device to the bus a communication adapter for connecting an information handling system to a data processing network the Internet an Intranet a personal area network PAN etc. and a display adapter for connecting the bus to a display device and or printer e.g. a digital printer or the like .

In addition to the hardware software environment described above a different aspect of the invention includes a computer implemented method for performing the above method. As an example this method may be implemented in the particular environment discussed above.

Such a method may be implemented for example by operating a computer as embodied by a digital data processing apparatus to execute a sequence of machine readable instructions. These instructions may reside in various types of signal bearing media.

Thus this aspect of the present invention is directed to a programmed product comprising signal bearing media tangibly embodying a program of machine readable instructions executable by a digital data processor incorporating the CPU and hardware above to perform the method of the invention.

This signal bearing media may include for example a RAM contained within the CPU as represented by the fast access storage for example. Alternatively the instructions may be contained in another signal bearing media such as a magnetic data storage diskette directly or indirectly accessible by the CPU .

Whether contained in the diskette the computer CPU or elsewhere the instructions may be stored on a variety of machine readable data storage media or other computer program products such as DASD storage e.g. a conventional hard drive or a RAID array magnetic tape electronic read only memory e.g. ROM EPROM or EEPROM an optical storage device e.g. CD ROM WORM DVD digital optical tape etc. paper punch cards or other suitable signal bearing media including storage devices for transmission by digital and analog and communication links and wireless. In an illustrative embodiment of the invention the machine readable instructions may comprise software object code.

The file system part of this invention can be either pre implemented into the OS or can be added on later after the OS has booted. As mentioned above currently this invention has been implemented as a kernel extension in the IBM AIX operating system. Kernel extension in AIX is analogous to a dynamically loadable module in other OSs. The event producers part of this invention have to be built into the OS. If there are no event producers available then adding a file system to expose the OS events to the applications is of no use.

If not already incorporated into an OS from original development the present invention has to be implemented for each OS that will be using it. It is noted at this point that although the above exemplary description has been restricted to kernel mode event producers one who is skilled in the art particularly in operating systems can easily extend this embodiment to also monitor events occurring in the user space. Therefore this exemplary embodiment is not intended as limiting the scope of the invention.

However the invention can also be distributed as a software package that a system administrator can install so that the monitoring applications can use it thereafter. Alternatively the present invention could be incorporated into debugging tools to provide more sophisticated debugging capabilities to software developers.

It is noted that the software package exemplarily shown in is intended as representing software wherein either the entire OS is stored and the OS has pre implemented therein the monitoring system of the present invention or the software contains an administrator s tool so that the present invention can be installed similar to that shown exemplarily in in block diagram format .

In yet another aspect of the present invention since the method permits a monitoring of an operating system or debugging of either the operating system or an application program riding on top of the operating system or developing software wherein monitoring of the operating system provides a development tool there is also the opportunity to utilize the present invention as a component in business or providing a service to other entities. Non limiting examples include for example providing an operating system monitoring service on a network including the potential to intervene in a timely manner by receiving the event notifications discussed above.

From the above description it should be clear that there are a number of benefits of the present invention AHAFS . Several exemplary and non limiting advantages of AHAFS include 

While the invention has been described in terms of exemplary embodiments those skilled in the art will recognize that the invention can be practiced with modification within the spirit and scope of the appended claims.

Further it is noted that Applicants intent is to encompass equivalents of all claim elements even if amended later during prosecution.

