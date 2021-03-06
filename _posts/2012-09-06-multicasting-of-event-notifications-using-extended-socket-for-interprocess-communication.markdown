---

title: Multicasting of event notifications using extended socket for inter-process communication
abstract: A system is provided for multicasting an event notification from an event producer to multiple event listeners, where the event producer and event listeners exist within a computer operating system having a user space, a kernel space, a device space, and an event protocol handler located in the kernel space. The system generates an event indication from an event producer located in the user space, kernel space, or device space, and receiving the event indication in the event protocol handler and generating an event notification. The event producer and the event listeners interface with the event protocol handler to send the event indication and receive the event notification. The event listeners may be located in the user space, kernel space, or device space.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09524197&OS=09524197&RS=09524197
owner: Accedian Networks Inc.
number: 09524197
owner_city: Saint Laurent
owner_country: CA
publication_date: 20120906
---
The present invention relates to Inter Process Communication between user space Applications and Operating System kernel modules Device Drivers and Applications.

In computer science a thread of execution is the smallest unit of processing that can be scheduled by an operating system. In most cases a thread is contained inside a process. Inter process communication IPC is a set of methods for the exchange of data among multiple threads in one or more processes.

Conventional operating systems can be divided into two layers user space and kernel space. Application code resides in user space while the underlying facilities of the operating system reside in the kernel space. An IOCTL input output control is a single system call by which user space may communicate with device drivers. The kernel can then allow the user space to access a device driver without knowing anything about the facilities supported by the device and without needing a large collection of system calls.

When a computer program needs to connect to a local or wide area network such as the Internet it uses a software component called a socket. The socket opens the network connection for the program allowing data to be read and written over the network. The sockets allow the programs to use the operating system s built in commands and protocol stacks to handle networking functions. IPC flows use sockets.

Netlink is an existing full duplex communication link between the Linux Operating System s user space and Kernel. It makes use of the standard socket APIs for user space processes and a special kernel API for kernel modules. Netlink sockets provide the possibility of multicast inside the kernel. Netlink sockets provide a bidirectional communication channel a message transfer can be initiated by either the kernel or the user space application. They have less overhead header and processing compared to standard UDP sockets.

In order to meet the performance requirements of protocols operating at high speeds such as Ethernet at 10 Gbps or 100 Gbps it is necessary to rethink how popular Inter Process Communication IPC techniques can be used and implemented more efficiently while preserving the native services of an Operating System such as but not limited to Linux and more specifically the delineation of functions and rights for processes operating in the user space or application level and kernel level. Whenever an application reads or writes data to a socket it s using a system call. This call such as read or write crosses the boundary of the user space application to the kernel. Additionally prior to getting to the kernel the call goes through the C library to a common function in the kernel system call . From system call this call gets to the filesystem layer where the kernel determines what type of device it s dealing with.

Even with some of the most recent enhancements to OS s such as Linux the context switching overhead is still too high especially when building cost sensitive platforms using lower cost CPUs and other programmable devices. As such the embodiment shows that it can deliver the required performance improvements and overhead reduction without the need to modify the underlying hardware platform.

For instance the embodiment is used to handle recently developed protocols such as Y.1731 that require the ability to process Service OAM messages at exactly every 3.33 msec which is a much higher rate than what is permissible with a typical OS usually in the range of 10 20 msec .

In accordance with one embodiment a system is provided for multicasting an event notification from an event producer to multiple event listeners where the event producer and event listeners exist within a computer operating system having a user space a kernel space a device space and an event protocol handler located in the kernel space. The system generates an event indication from an event producer located in the user space kernel space or device space and receiving the event indication in the event protocol handler and generating an event notification. The event producer and the event listeners interface with the event protocol handler to send the event indication and receive the event notification. The event listeners may be located in the user space kernel space or device space.

In one implementation each event indication belongs to a single group of events and the event listeners register with the event protocol handler to receive event notifications for one or more groups of events in which the event listeners are interested. The event protocol handler may generate an event notification based on the event indication and multicasts the event notification to all event listeners that have registered to receive notifications for the group of events to which the event indication is assigned. The event protocol handler may use socket buffers to multicast the event notification to event listeners in the user space.

The interfacing with the event protocol handler may be achieved via an event management application programming interface containing primitives including opening and closing a kernel socket interface registering or deregistering an event listener for one or more event groups generating an event indication receiving an event notification via a call back function in the kernel space and receiving an event indication after being notified of an available event notification.

Although the invention will be described in connection with certain preferred embodiments it will be understood that the invention is not limited to those particular embodiments. On the contrary the invention is intended to cover all alternatives modifications and equivalent arrangements as may be included within the spirit and scope of the invention as defined by the appended claims.

Typical IPC services of the operating system available to applications in the user space are extended to the kernel space to reduce the overhead when an application needs to interface with services offered by the kernel. These enhanced socket based services also extend beyond the kernel to programmable devices such as but not limited to FPGA in the device space that do not operate under the same operating system.

Because of the sensitivity of the services performed in the kernel space and by programmable devices in the device space not running the same operating system it is imperative that while the native semantics of popular IPC mechanisms is preserved that it never results into a blocked or sleeping event while operating in kernel mode or inside a programmable device in the device space.

Referring to a new extended socket is defined to allow the use of sockets for non blocking communication between user process in user space and other user processes kernel modules and programmable devices . This includes an extended socket API in user space and extended socket family software in kernel space . An event notification API is added to the extended socket API and event notification software is added to the extended socket family software in the kernel space .

When an event indication from an event producer is received by the event protocol handler the event protocol handler is responsible for multicasting the resulting event notifications to a plurality of event listeners using socket buffers when the recipient of the event notification is located in the user space or the kernel space and using device specific techniques such as hardware registers memory interfaces and or input output i o pins or signals when the recipient is in the device space . A kernel module or a programmable device shall never block while waiting for an event notification . Therefore rather than wait for an event notification a callback routine is registered by each thread in kernel module or programmable device via a device driver in the kernel space interested in one or more events by doing a register and subscribe via the event management API and a callback routine will be called whenever an event notification is generated. Since the kernel callback function potentially operates in the context of an interrupt service routine the event should be handled as quickly as possible as per the typical OS guidelines.

An event indication can be multicast as event notifications to one or more event listeners part of the user process or kernel module or programmable device doing a register and subscribe for one or more event groups via the event management API . Whenever an event indication is sent from the user space the extended socket API is used. Otherwise event indications originating from the kernel space or the device space are handled directly by the events protocol handler in the kernel space .

The extended socket API can be used from the user space to interface to the events protocol handler while module in the kernel space and programmable device such as FPGAs in the device space interface to the events protocol handler via the event management API . It should be noted that programmable devices in the device space do not operate inside the operating system.

More specifically and unlike the Netlink Socket interface the embodiment adds support for event indications including the ability to multicast event notifications between any combinations of modules threads or applications 

As can be exemplified from an event indication originating from a programmable device is sent via registering with the event management API to the events protocol handler . The resulting event notifications are then multicast to kernel module programmable device and user process and registered for the corresponding event notification . The event notifications are asynchronous to avoid potential deadlock or blocked processes threads.

The event protocol handler offers an event management API to provide non blocking delivery of event indications originating from user processes kernel modules and from programmable device as event notifications . This is critical to allow event notifications to be generated toward kernel module threads programmable device and user space processes whether the execution context is inside a kernel thread that can be blocked or sleep or whether the event indication is generated from inside an IRQ or SOFT IRQ routine that simply cannot be blocked and needs to complete its processing as fast as possible.

This invention augments the real time capabilities of any OS that support the notion of user space and kernel space and the memory protection as well as other system resources whereby a user process in the user space cannot freely access resources memory file handlers etc. allocated to another user process . This level of protection requires relatively expensive context swapping when the OS schedules another user process or when an user process communicates with kernel modules . By reducing the overhead required to communicate between processes originating from the user space and or kernel space and or device space it becomes easier to support various real time constraints including but not limited to data communication platforms or applications for instance financial trading cloud computing etc. 

While particular embodiments and applications of the present invention have been illustrated and described it is to be understood that the invention is not limited to the precise construction and compositions disclosed herein and that various modifications changes and variations may be apparent from the foregoing descriptions without departing from the spirit and scope of the invention as defined in the appended claims.

