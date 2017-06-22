---

title: Method and system to provide user-level multithreading
abstract: A method and system to provide user-level multithreading are disclosed. The method according to the present techniques comprises receiving programming instructions to execute one or more shared resource threads (shreds) via an instruction set architecture (ISA). One or more instruction pointers are configured via the ISA; and the one or more shreds are executed simultaneously with a microprocessor, wherein the microprocessor includes multiple instruction sequencers.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09442721&OS=09442721&RS=09442721
owner: Intel Corporation
number: 09442721
owner_city: Santa Clara
owner_country: US
publication_date: 20121220
---
The present embodiments of the invention relate to the field of computer systems. In particular the present embodiments relate to a method and system to provide user level multithreading.

Multithreading is the ability of a program or an operating system to execute more than one sequence of instructions at a time. Each user request for a program or system service and here a user can also be another program is kept track of as a thread with a separate identity. As programs work on behalf of the initial request for that thread and are interrupted by other requests the status of work on behalf of that thread is kept track of until the work is completed.

Types of computer processing include single instruction stream single data stream which is the conventional serial von Neumann computer that includes a single stream of instructions. A second processing type is the single instruction stream multiple data streams process SIMD . This processing scheme may include multiple arithmetic logic processors and a single control processor. Each of the arithmetic logic processors performs operations on the data in lock step and are synchronized by the control processor. A third type is multiple instruction streams single data stream MISD processing which involves processing the same data stream flows through a linear array of processors executing different instruction streams. A fourth processing type is multiple instruction streams multiple data streams MIMD processing which uses multiple processors each executing its own instruction stream to process a data stream fed to each of the processors. MIMD processors may have several instruction processing units multiple instruction sequencers and therefore several data streams.

The programming model adopted by today s multithreaded microprocessors is the same as the traditional shared memory multiprocessor multiple threads are programmed as though they run on independent CPUs. Communication between threads is performed through main memory and thread creation destruction scheduling is performed by the operating system. Multithreading has not been provided in an architecturally visible manner in which programmers can directly access threads.

A method and system to provide user level multithreading are disclosed. The method according to the present techniques comprises receiving programming instructions to execute one or more shared resource threads shreds via an instruction set architecture ISA . One or more instruction pointers are configured via the ISA and the one or more shreds are executed simultaneously with a microprocessor wherein the microprocessor includes multiple instruction sequencers.

In the following description for purposes of explanation specific nomenclature is set forth. However it will be apparent to one skilled in the art that these specific details are not required. Some portions of the detailed descriptions which follow are presented in terms of algorithms and symbolic representations of operations on data bits within a computer memory. These algorithmic descriptions and representations are the means used by those skilled in the data processing arts to most effectively convey the substance of their work to others skilled in the art. An algorithm is here and generally conceived to be a self consistent sequence of operations leading to a desired result. The operations are those requiring physical manipulations of physical quantities. Usually though not necessarily these quantities take the form of electrical or magnetic signals capable of being stored transferred combined compared and otherwise manipulated. It has proven convenient at times principally for reasons of common usage to refer to these signals as bits values elements symbols characters terms numbers or the like.

It should be borne in mind however that all of these and similar terms are to be associated with the appropriate physical quantities and are merely convenient labels applied to these quantities. Unless specifically stated otherwise as apparent from the following discussion it is appreciated that throughout the description discussions utilizing terms such as processing or computing or calculating or determining or displaying or the like refer to the action and processes of a computer system or similar electronic computing device that manipulates and transforms data represented as physical electronic quantities within the computer system s registers and memories into other data similarly represented as physical quantities within the computer system memories or registers or other such information storage transmission or display devices.

The embodiments of the invention provided also relate to an apparatus for performing the operations herein. This apparatus may be specially constructed for the required purposes or it may comprise a general purpose computer selectively activated or reconfigured by a computer program stored in the computer. Such a computer program may be stored in a computer readable storage medium such as but is not limited to any type of disk including floppy disks optical disks CD ROMs and magnetic optical disks read only memories ROMs random access memories RAMs EPROMs EEPROMs magnetic or optical cards or any type of media suitable for storing electronic instructions and each coupled to a computer system bus.

The algorithms and displays presented herein are not inherently related to any particular computer or other apparatus. Various general purpose systems may be used with programs in accordance with the teachings herein or it may prove convenient to construct more specialized apparatus to perform the required method. The required structure for a variety of these systems will appear from the description below. In addition one embodiment of the present invention is not described with reference to any particular programming language. It will be appreciated that a variety of programming languages may be used to implement the teachings of embodiments of the invention as described herein.

 Users as used throughout this specification describe user level software such as application programs non privileged code and similar software. User level software is distinguished from an operating system or similar privileged software. According to one embodiment of the present invention the following description applies to MIMD processors as described above.

ICH is coupled to a Peripheral Component Interconnect PCI bus . A super I O SID controller is coupled to ICH to provide connectivity to input devices such as a keyboard and mouse . A general purpose I O GPIO bus is coupled to ICH . USB ports are coupled to ICH as shown. USB devices such as printers scanners joysticks etc. can be added to the system configuration on this bus. An integrated drive electronics IDE bus is coupled to ICH to connect IDE drives to the computer system. Logically ICH appears as multiple PCI devices within a single physical component.

Included in processor is an instruction set architecture. Instruction set architecture ISA is an abstract model of a microprocessor such as processor that consists of state elements registers and instructions that operate on those state elements. The instruction set architecture serves as a boundary between software and hardware by providing an abstract specification of the microprocessor s behavior to both the programmer and the microprocessor designer.

Advances in the number of transistors available on a silicon chip have enabled the introduction of multithreading into general purpose microprocessors. Multithreading may be implemented in two different manners chip level multiprocessor CMP and simultaneous multithreaded processor SMT both of which may be used as processor .

Prior multithreaded microprocessors adopt the same programming model as prior shared memory multiprocessor systems. The programming model is as follows. A microprocessor provides multiple threads of execution to the operating system. The operating system uses these threads to run multiple applications processes concurrently and or run multiple threads from a single application multithreaded concurrently. In both cases the threads appear to software as independent CPUs. Main memory is shared by all threads and communication between threads is carried out through main memory. Hardware resources within the CPU may also be shared but the sharing is hidden from software by the microarchitecture.

While the traditional shared memory multiprocessor programming model is widely understood and supported by many operating systems and application programs the model has a number of disadvantages. They are 

For the reasons stated above regarding prior systems the present method and system extend processor architectures to include architecturally visible multithreading through multithreading architecture extensions. Multiple simultaneous threads of execution multiple instruction pointers and multiple copies of certain application state registers within a single processing element are provided. Multiple threads of execution are distinguishable from existing shared memory threads and are referred to as shreds or shared resource threads.

The present multithreading architecture extensions an example of which is hereafter referred to as MAX would include existing architecture capabilities and in addition support multiple simultaneous shreds each with its own instruction pointer general registers FP registers branch registers predicate registers and certain application registers. Non privileged instructions are created to create and destroy shreds. Communication between shreds are carried out through shared registers in addition to shared memory. The need for semaphores would be reduced because the present multithreading architecture extensions would guarantee atomic access to shared registers. Additionally the present multithreading architecture extensions can be used with 32 bit architectures such as the 32 bit architecture by Intel or 64 bit architectures such as 64 bit architecture also by Intel or even 16 bit architectures.

A comparison between the conventional shared memory multiprocessor thread and a shred is shown in the following table according to one embodiment of the present invention.

It should be noted that the present multithreading architecture extension is fundamentally different from prior architecture extensions. While prior architecture extensions provided more instructions and more registers state the multithreading architecture extension provides more units of execution.

Programmer visible CPU state may be divided into two categories application state and system state. The application state is used and controlled by both application programs and the operating system while the system state is controlled exclusively by the operating system.

For each shred the application state is divided into two categories per shred application state and shared application state. The MAX programming model described herein provides a unique instance of the per shred application state while the shared application state is shared among multiple shreds. There is only one copy of the system state and all shreds corresponding to a given thread share the same system state. An approximate division of application and state is presented in the following table 

The present multithreading architecture extension offers programmable sharing or privacy of most application state so that software can select the best partitioning. The programming is performed with a bit vector so that individual registers can be selected as either shared or private. A hardware re namer can allocate registers from either a shared pool or a private pool as specified by the bit vector.

The overall storage requirements of MAX are smaller than those of prior simultaneous multithreaded processors and chip level multiprocessors. In MAX only the per shred private application state is replicated whereas in a simultaneously multithreaded processor or chip level multiprocessor that implements the traditional shared memory multiprocessor programming model the entire application and system state must be replicated.

Each shared memory thread consists of multiple shreds. The shreds and shared memory threads form a two level hierarchy. In an alternate embodiment a three level hierarchy can be built from clusters of shared memory MAX processors. The clusters communicate using message passing. The operating system handles the scheduling of threads whereas the application program handles the scheduling of shreds. The shreds are non uniform in the sense that any given shred sees other shreds as either local or remote. Per shred application state is replicated for each shred. The shared application and system state is common to the local shreds and replicated for each shared memory thread. The memory state has only one copy.

Because the system state is shared between multiple shreds in the MAX programming model the multiple shreds belong to the same process. The present multithreading architecture extensions are intended to be used by multithreaded applications libraries and virtual machines. The MAX programming model gives this type of software an unprecedented degree of control over its shreds and a performance potential that is not achievable with the shared memory multiprocessor programming model discussed above.

No protection checking is required between shreds since they all run at the same privilege level and share the same address translation. Thus the traditional protection mechanisms may be avoided during inter shred communication.

The MAX programming model cannot be used to run different processes on the same thread due to the shared system state. For this reason the MAX and prior shared memory programming models coexist within the same system.

Since a given CPU offers a finite number of physical shreds software virtualizes the number of available shreds in a similar manner to the virtualization of hardware threads. The virtualization results in a finite number of currently running physical shreds along with a potentially unbounded number of virtual shreds.

Operating system calls may be processed in the conventional manner by transferring control from the application program to the operating system and performing a context switch. With the MAX architecture one key difference is that calling the operating system on any shred will suspend the execution of all shreds associated with a given thread. The operating system is responsible for saving and restoring the state of all shreds belonging to the same thread.

Due to the additional state the context switch overhead increases. The context switch memory footprint grows in proportion to the number of shreds. However the context switch time does not increase by much because each shred can save restore its state in parallel with other shreds. The context switch mechanism allows parallel state save restore using multiple sequencers. The operating system itself makes use of multiple shreds.

Because the cost of calling the operating system increases certain functionality that was performed by the operating system to be migrated to the application program. This functionality includes thread maintenance and processing of certain exceptions and interrupts.

An alternative embodiment of performing system calls is based on the observation that threads are becoming cheap while context switches are becoming expensive. In this embodiment a thread is dedicated to running the operating system and a second thread is dedicated to running the application program. When the application program shred performs a system call it sends a message to an operating system shred via shared memory and waits for a response message. In this manner the message passing and wait mechanism replaces the conventional control transfer and context switch mechanism. No change to the address translation of either thread is required. The benefit is that a message sent by one shred to the operating system does not disturb other local shreds.

In prior architectures exceptions suspend execution of the application program and invoke an operating system exception handler. Under the MAX programming model this behavior is undesirable because suspending one shred to invoke the operating system causes all shreds associated with a given thread also to be suspended.

To solve this problem we introduce a new user level exception mechanism that gives the application program the first opportunity to service many types of exceptions. The user level exception mechanism is based on the observation that a few existing exception types are ultimately serviced by the application itself.

For the user level exception mechanism how an exception is reported versus is distinguished from how an exception is serviced. Exceptions may be divided into three categories as follows.

The following table illustrates the exceptions in each of the three categories. The Load exception on cache miss and Fine grained timer exception types are provided as exception types related to one embodiment of the present invention.

Exceptions reported to the application program are selectively processed within the application or passed to the operating system for processing. In the latter case the application program performs a system call to explicitly request service from the operating system in response to an exception such as a page fault . This contrasts with the traditional approach of the operating system implicitly performing such services on behalf of the application. To avoid nested exceptions special provisions are provided to ensure that the application code that relays exceptions to the operating system does not itself incur additional exceptions. The user level exception mechanism saves a minimum number of CPU registers in a shadow register set and the processor vectors to a fixed location.

Virtual machines and the present embodiments of multithreading architecture extensions impose constraints on each other because virtual machines raise exceptions whenever software attempts to access a resource that is being virtualized and exception processing has significant performance consequences to the shreds.

In a virtual machine the execution of privileged instructions or access to privileged processor state raises an exception. The exception must be reported to and serviced by the virtual machine monitor. In MAX exceptions serviced by the operating system and virtual machine monitor cause all shreds associated with a given thread to be suspended. The virtual machine monitor comprehends the presence of multiple shreds. The virtual machine architecture minimizes the number of exceptions raised on non privileged instructions and processor resources.

Deadlock avoidance is complicated in the MAX architecture because shreds can be suspended by other local shreds. The application software ensures that deadlock will not occur if one shred incurs an OS serviced exception or system call causing all local shreds to be suspended.

Local inter shred communication and synchronization is distinguished from remote inter thread communication and synchronization. Local communication is performed using either shared registers illustrated in or shared memory. Remote communication is performed using shared memory. Local data synchronization is performed using atomic register updates register semaphores or memory semaphores. Remote data synchronization is performed using memory semaphores.

Both local and remote shred control creation destruction are performed using the MAX instructions. Shred control does not call the operating system for wait or yield because this can have the unintentional effect of suspending all shreds on a given thread. The operating system calls used for thread maintenance are replaced by calls to a user level shred library. The shred library in turn calls the operating system to create and destroy threads as needed.

Shreds differ from fibers implemented in prior operating systems. The differences are summarized in the table below 

The implementation of a microprocessor supporting the multithreading architecture extensions can take the form of chip level multiprocessors CMP and simultaneous multithreaded processors SMT . The prior CMP and SMT processors try to hide the sharing of CPU resources from software whereas when implemented with the present embodiments of multithreading architecture extensions a processor exposes sharing as part of the architecture.

To implement a MAX processor as a chip level multiprocessor a broadcast mechanism is used to keep multiple copies of the system state in synchronization between the CPU cores. Fast communication busses are introduced for shared application and system state. Because on chip communication is fast relative to off chip memory these communication busses give the MAX processor its performance advantage over a shared memory multiprocessor.

Implementing a MAX processor as a simultaneous multithreaded processor is possible since the hardware already provides the necessary sharing of resources. It is possible to implement MAX almost entirely in microcode on a multithreaded 32 bit processor.

According to one embodiment the present method and system permits the prioritization of system calls and exceptions reported to the OS among multiple shreds such that only one shred s request is serviced at any instant in time. Prioritization and selection of one request is necessary because the system state is capable of handing only one OS service request at a time. For example assume that shred 1 and shred 2 simultaneously perform system calls. The prioritizer would ensure that only shred 1 s system call was executed and shred 2 s system call had not yet begun execution. For fairness considerations the prioritizer employs a round robin selection algorithm although other selection algorithms may be used.

As the number of shreds increases the amount of state that must be saved restored on a context switch increases and the potential parallelism that is lost as a result of suspending all shreds increases. These two factors will limit the practical number of shreds.

Inter shred communication will also limit scalability since this communication is performed using on chip resources. In contrast the scalability of the traditional shared memory multiprocessor model is limited by off chip communication.

A taxonomy of the various degrees of freedom in architecture implementation and software usage of shreds is presented in the following table 

Two different types of MAX architecture are distinguished homogeneous and heterogeneous. Homogeneous shreds are similar to homogeneous multiprocessors in that all shreds execute the same instruction set. Heterogeneous shreds are also possible in a similar manner as heterogeneous multiprocessors. For example heterogeneous shreds may be constructed between 

Similarly the underlying microarchitecture may be either symmetric or asymmetric. An example of the latter case would be a chip level multiprocessor containing a few large high performance CPU cores and many small low power CPU cores such as illustrated in .

The following table summarizes a number of usage models for embodiments of the present multithreading architecture extensions 

In the prefetch usage model a main thread spawns one or more helper threads which are used to prefetch cache lines from main memory. The helper threads are spawned in response to a cache miss on the main thread. Since a main memory access requires several hundred to a thousand CPU clocks to complete execution of scalar code will effectively stop during a main memory access unless architectural provisions are made to fault on loads that miss the caches and proceed to main memory.

Shreds may be used as a high performance replacement for conventional threads by multithreaded applications. A user level software library is provided to perform shred management functions create destroy etc that were formerly performed by the operating system. The library makes use of the shred instructions as well as call the operating system as needed to request additional threads. Calling a software library is much faster than calling the operating system because no context switch is necessary.

The compiler may use the shreds in the same manner that it uses other processor resources such as registers. For example the compiler may view the processor as having 8 integer registers 8 floating point registers 8 SSE registers and 4 shreds. By treating shreds as a resource the compiler allocates shreds in an analogous manner to register allocation. As with registers some mechanism is needed to spill fill shreds to a backing store in the event that the application program requires more virtual shreds than hardware provides. In prior architectures the flow of control is usually not regarded as a processor resource because there is only one.

In a managed runtime environment shreds are dedicated to functions such as garbage collection just in time compilation and profiling. The shreds perform such functions essentially for free since the shreds are provided as part of the instruction set architecture ISA . The ISA is the part of the processor that is visible to the programmer or compiler writer. The ISA serves as the boundary between software and hardware.

MAX directly supports parallel programming languages and hardware description languages. For example an iHDL or Verilog compiler directly generates code for multiple shreds because the source code is explicitly parallel.

The proliferation of threads made possible by chip level multiprocessors lead to language support for multithreading. Such support is provided through calls to the operating system and run time library. Language support for multithreading is migrated into mainstream general purpose programming languages.

The shreds are used to implement I O functions such as a network coprocessor. One important difference between a network coprocessor implemented as a shred is that it appears as part of the CPU rather than as an I O device.

In prior systems when an application program requires I O the application program calls the operating system using an API application program interface . The operating system in turn calls a device driver which sends the request to the I O device. The operating system is responsible for queuing or serializing I O requests from multiple application programs ensuring that the I O device processes only one or a finite number of requests at a time. This is necessary since the I O device s state is global to the system whereas the CPU state is time multiplexed between multiple applications.

In an I O device implemented as a heterogeneous shred the I O device s state is treated as an extension of the CPU s application state. The application program directly controls both the CPU s application state and the I O devices state. Both the application state and I O state is saved restored by the operating system on a context switch. The I O device is architected so that its state can be time multiplexed between several applications without adverse effects.

The 64 bit architecture is defined to include the 32 bit architecture application architecture as well as the new 64 bit instruction set through a mechanism known as seamless . Compatibility with the 32 bit architecture instruction set enables 64 bit architecture processors to run both existing 32 bit architecture applications as well as new 64 bit architecture applications.

Under the current definition a 64 bit architecture CPU runs either a 64 bit architecture thread or a 32 bit architecture thread at any instant in time. Switching between the two ISAs is accomplished via the 64 bit architecture br.ia branch to 32 bit architecture and 32 bit architecture jmpe jump to 64 bit architecture instructions. The 32 bit architecture registers are mapped onto the 64 bit architecture registers so that only one copy of the state is needed.

It is possible to create a multi ISA CPU in which more than one instruction set architecture is running at any instant in time. This may be accomplished by using a shred for the 64 bit architecture ISA and a second shred for the 32 bit architecture ISA. As with homogeneous shreds distinct application state must be provided for both the 64 bit architecture shred and the 32 bit architecture shred. The 64 bit architecture shred and 32 bit architecture shred run simultaneously.

Having described the features of the present method and system to provide user level multithreading through the multithreading architecture extensions described above an embodiment for 32 bit systems is provided below.

Although described with reference to the IA 32 architecture the reader understands that the methods and systems described herein may be applied to other architectures such as the IA 64 architecture. Additionally the reader is directed back to to understand an exemplary execution environment according to one embodiment of the present invention. A small number of instructions are added to the IA 32 ISA along with a number of registers to bring the capability of user level multithreading to IA 32.

A model specific register MSR is used to enable the multithreading architecture extension. The MSR is described below.

Model specific registers such as shred MSR are written and read only at privilege level 0. If the multithreading architecture extensions are not enabled execution of legacy code is restricted to shred number 0.

The IA 32 CPUID instruction is modified to return an indication that the processor supports the multithreading architecture extension along with a count of the number of physical shreds provided. This is done by adding three bits NSHRED to the extended feature information returned in ECX. The information returned by the CPUID Instruction is provided in the following table 

If the multithreading architecture extension is not enabled through the MAX SHRED ENABLE MSR the extended feature information returns a value of 000 for NSHRED.

A breakdown of the IA 32 state into each of the categories is shown above in Table 2. The shred s private state is replicated once per shred. The shred private state is completely private to each shred. Specifically the architecture does not provide any instructions that individually read or write one shred s private registers from another shred. The architecture does provide the shsave and shrestore instructions to collectively write and read all shred s private state to memory but these instructions are executed only in single shredded mode. The shred s shared state is shown in Table 3 above.

A set of shared registers SH SH are used for communication and synchronization between shreds. These registers are written and read through the MOV to shared register and MOV from shared register instructions. The SH SH registers store 32 bit integer values. According to one embodiment 80 bit floating point and 128 bit SSE data are shared through main memory.

The memory state is shared by all shreds. The breakdown of the EFLAGS register is shown in the table below.

Flags marked Y are replicated on a per shred basis. Flags marked N have one copy shared by all shreds.

The 32 bit EFLAGS register contains a group of status flags a control flag and a group of system flags. Following initialization of the processor either by asserting the RESET pin or the INIT pin the state of the EFLAGS register is 00000002H. Bits and through of this register are reserved. Software should not use or depend on the states of any of these bits.

Some of the flags in the EFLAGS register can be modified directly using special purpose instructions. There are no instructions that allow the whole register to be examined or modified directly. However the following instructions can be used to move groups of flags to and from the procedure stack or the EAX register LAHF SAHF PUSHF PUSHFD POPF and POPFD. After the contents of the EFLAGS register have been transferred to the procedure stack or EAX register the flags can be examined and modified using the processor s bit manipulation instructions BT BTS BTR and BTC .

When suspending a task using the processor s multitasking facilities the processor automatically saves the state of the EFLAGS register in the task state segment TSS for the task being suspended. When binding itself to a new task the processor loads the EFLAGS register with data from the new task s TSS.

When a call is made to an interrupt or exception handler procedure the processor automatically saves the state of the EFLAGS registers on the procedure stack. When an interrupt or exception is handled with a task switch the state of the EFLAGS register is saved in the TSS for the task being suspended.

Two forms are provided one with the shred number as an immediate operand and a second with the shred number as a register operand. For both forms the target IP is specified as an immediate operand whose value is relative to the beginning of the code segment nominally 0 not relative to the current IP.

The forkshred imm16 target IP encoding is similar to the far jump instruction with the shred number replacing the 16 bit selector and the target IP replacing the 16 32 bit offset.

The forkshred instruction sets the appropriate run bit in SC and begins execution at the specified address. Unlike the Unix fork system call the forkshred instruction does not copy the state of the parent shred. A new shred begins execution with an updated EIP along with the current values of all other private registers. It is expected that the new shred should initialize its stack by loading ESP and retrieve incoming parameters from shared registers or memory. The forkshred instruction does not automatically pass parameters.

If the target shred is already running forkshred raises a SNA shred not available exception. This is a user level exception as described below. Software either ensures that it is not trying to start an already running shred or alternatively provide a SNA handler that halts the existing shred and returns to re execute the forkshred. A GP 0 exception is raised if the shred number is greater than the maximum number of shreds supported by hardware.

To terminate execution of the current shred the haltshred instruction is used. Haltshred clears the current shred s run bit in SC and terminates execution of the current shred. The shred s private state is retained even while halted. Since no mechanism exists for one shred to access another shred s private state a halted shred s private state cannot be seen. However the state persists and becomes visible when the shred again begins execution via forkshred.

To prematurely terminate execution of another shred the killshred instruction is introduced. The format is

According to one embodiment the shred number is a 16 bit register or immediate operand. Killshred clears the specified shred s run bit in SC and terminates the shred s execution. While halted the shred s private state is retained.

If the target shred is not running killshred is silently ignored. This behavior is necessary to avoid a race between killshred and a normally terminating shred. After executing killshred software is guaranteed the target shred is no longer running. A shred is allowed to kill itself instead of performing a haltshred. A GP 0 exception is raised if the shred number is greater than the maximum number of shreds supported by the hardware.

To wait until a specified shred has terminated as indicated by the SC bit being clear the joinshred instruction is introduced. The format is 

If the target shred is not running joinshred returns immediately. This behavior avoids a race between joinshred and a normally terminating shred. After executing joinshred software is guaranteed the target shred is no longer running. It is legal but useless for a shred to do a joinshred on itself. A GP 0 exception is raised if the shred number is greater than the maximum number of shreds supported by the hardware. The joinshred instruction does not automatically pass a return value. To allow a shred to determine its own shred number the getshred instruction is introduced. The format is 

Getshred returns the number of the current shred. Getshred may be used to access memory arrays indexed by shred number. Getshred zero extends the 16 bit shred number to write to all bits of the destination register.

For all shred creation destruction instructions the shred number may be specified as either a register or immediate operand. It is expected that the execution of the immediate form may be faster than execution of the register form because the shred number will be available at decode time rather than execute time. With the immediate form the compiler assigns the shred numbers. With the register form run time assignment is used.

The forkshred haltshred killshred joinshred and getshred instructions may be executed at any privilege level. Haltshred is a non privileged instruction whereas the existing IA 32 hlt instruction is privileged.

It is possible that the execution of a killshred or haltshred results in zero running shreds. This state with 0 in SC is different than the existing IA 32 halt state. SC 0 is a legal state but not useful until a user level timer interrupt is created.

Shreds communicate with each other through existing shared memory and through a set of registers introduced specifically for this purpose. Shared registers SH SH are accessible by all local shreds belonging to the same thread. The SH SH registers may be used to pass incoming parameters to a shred communicate return values from a shred and perform semaphore operations. A software convention assigns specific shared registers to each purpose.

Each shared register has a corresponding empty full bit in SC. To write and read the shared registers MOV to shared register and MOV from shared register instructions are used. These are summarized as follows 

The instruction encodings are similar to the existing MOV to from control register and MOV to from debug register instructions. The MOV to from shared register instructions may be executed at any privilege level. These instructions assume that software explicitly performs synchronization using additional instructions. The mov to from shared register instructions neither examine nor modify the state of the empty full bits in SC.

It is expected that the latency of MOV to shared register and MOV from shared register will be lower than the latency of loads and stores to shared memory. The hardware implementation is likely to speculatively read the shared registers and snoop for other shreds writes. Hardware must ensure the equivalent of strong ordering when writing to the shared registers . In an alternate embodiment barrier instructions can be created for accessing the shared registers .

One architecture feature keeps shared register ordering and memory ordering separate from each other. Thus if a shred writes to a shared register and then writes to memory there is no guarantee that the shared register contents will be visible before the shared memory contents. The reason for this definition is to enable high speed access update of loop counters in the shared registers without creating unnecessary memory barriers. If software requires barriers on both shared registers and memory software should perform both a shared register semaphore along with a memory semaphore. The memory semaphore is redundant except for acting as a barrier.

To provide rapid communication as well as synchronization the synchronous mov to from shared register instructions are used. These instructions are summarized as follows 

The instruction encodings parallel the existing MOV to from control register and MOV to from debug register instructions. The synchronous mov to shared register is similar to its asynchronous counterpart except that it waits until the empty full bit indicates empty before writing to the shared register . After writing to the shared register the empty full bit is set to full. The synchronous mov from shared register is similar to its asynchronous counterpart except that it waits until the empty full bit indicates full before reading from the shared register . After reading from the shared register the empty full bit is cleared to empty.

The empty full bits may be initialized with a move to SC as described below. The synchronous MOV to from shared register instructions may be executed at any privilege level. The shared register communication instructions are summarized below 

A set of synchronization primitives operate on the shared registers . The synchronization primitives are similar to existing semaphore instructions except that they operate on the shared registers rather than memory. The instructions are as follows.

The synchronization primitives are executed at any privilege level. These instructions neither examine nor modify the state of the empty full bits in SC.

The MAX architecture provides a mechanism to switch between multi shredded and single shredded modes. Single shredded mode enables the processor to perform context switches in an orderly fashion by halting the execution of all but one shred. SC indicates the current operating mode as follows 

The entermsm and exitmsm instructions are used to switch to multi shredded and single shredded modes respectively. Entermsm is used to enter multi shredded mode. The state of all shreds must be loaded prior to execution of this instruction. Entermsm copies the new shred run vector in SC into SC. Entermsm then starts the specified shreds.

It is possible that the contents of SC result in no additional shreds being run after execution of entermsm. In this case the processor remains in single shredded mode. It is also possible that as a result of executing entermsm the shred on which entermsm was executed is no longer running Exitmsm is used to exit multi shredded mode. Exitmsm copies the present shred execution vector in SC into SC. All SC run bits other than the one corresponding to the shred executing exitmsm are cleared. All shreds other than the shred executing exitmsm are halted. These operations are performed as an atomic sequence. The SC state indicates single shredded mode. Entermsm and exitmsm may be executed at any privilege level.

The instructions shsave and shrestore are used to save and restore the collective shred state to write the contents of all shreds private state to memory and read the contents of all shreds private state from memory respectively. The format is

The address of the memory save area is specified as a displacement in the instruction. The address is aligned on a 16 byte boundary. The memory save area is 16 KBytes to allow for future expansion. The memory save area extends the existing FXSAVE FXRESTOR format by adding the integer registers. The memory save area for each shred is defined as follows 

The contents of all shreds are saved restored at an address given by address 512 shred number base address 

The memory save area includes the EIP and ESP of the currently running shred. Shsave writes the current EIP and ESP to the memory. To avoid branching the shrestore instruction does not overwrite the current shred s EIP or ESP. The shrestore function when executed as part of an IRET does overwrite the current shred s EIP and ESP.

Shsave and shrestore may by executed at any privilege level but only while in single shredded mode. A GP 0 exception is raised if shsave or shrestore are attempted when in multi shredded mode. Implementations are free to use all available hardware resources to execute the shsave shrestore store load operations in parallel.

Shrestore unconditionally loads the state of all shreds from memory. This behavior is necessary to ensure that a shred s private state does not leak from one task to the next. Shsave may unconditionally or conditionally store the state of all shreds to memory. An implementation may maintain non architecturally visible dirty bits to skip some or all of the shsave store operations if the private state was not modified.

The shsave and shrestore instructions save and restore only the shred s private state. The operating system is responsible for saving and restoring the shared registers .

Instructions are provided to write and read the shred control registers SC SC . These are summarized as follows 

The instruction encodings are similar to the existing MOV to from control register and MOV to from debug register instructions. The MOV to from shred control register instructions may be executed at any privilege level. Safeguards are provided to ensure that a malicious application program cannot affect any processes other than itself by writing to the shred control registers.

The application program uses forkshred and joinshred rather than manipulating the contents of SC directly. Exitmsm can transition from multi shredded mode to single shredded mode in an atomic manner. Using mov from SC to read the present shred run status and then using mov to SC to write a shred run status will not give the desired results because the shred run status may change between the read and the write.

MAX has several implications for the IA 32 exception mechanism. First a user level exception mechanism enables several types of exceptions to be reported directly to the shred that raised them. This mechanism is described below.

Next the IA 32 exception mechanism is modified to properly handle multiple shreds in the presence of exceptions that require a context switch. One problem with prior IA 32 exception mechanism is that it is defined to automatically save and restore CS EIP SS ESP and EFLAGS for exactly one running thread.

The existing IA 32 exception mechanism is extended to include the functionality of the entermsm exitmsm shsave and shrestore instructions. When an interrupt or exception is raised that requires a context switch the exception mechanism does the following 

The operating system is required to set up the shred state save restore area in memory and load its address into SC prior to performing the IRET. The operating system is also required to save restore the state of SC SC and SC.

It is possible for multiple shreds to simultaneously encounter exceptions that require operating system service. Because the MAX architecture can report only one OS exception at a time hardware must prioritize OS exceptions across multiple shreds report exactly one and set the state of all other shreds to the point where the instruction that raised the exception has not yet been executed.

MAX introduces a user level exception mechanism that enables certain types of exceptions to be processed completely within the application program. No operating system involvement privilege level transition or context switches are necessary.

When a user level exception occurs the EIP of the next yet to be executed instruction is pushed onto the stack and the processor vectors to the specified handler. The user level exception handler performs its task and then returns via the existing RET instruction. According to one embodiment no mechanism is provided for masking user level exceptions since it is assumed that the application will raise user level exceptions only when the application is prepared to service them.

Two instructions are provided to create the first two user level exceptions signalshred and forkshred. These are described in the following sections.

The target shred may be specified as either a register or an immediate operand. The signalshred imm16 target IP instruction encoding is similar to the existing far jump instruction with the shred number replacing the 16 bit selector and the target IP replacing the 16 32 bit offset. As with the far jump the signalshred target IP is specified relative to the beginning of the code segment nominally 0 not relative to the current IP.

In response to a signalshred the target shred pushes the EIP of the next yet to be executed instruction onto the stack and vectors to the specified address. A shred may send a signal to itself in which case the effects are the same as executing the near call instruction. If the target shred is not running signalshred is silently ignored. A GP 0 exception is raised if the shred number is greater than the maximum number of shreds supported by the hardware.

The signalshred instruction may be executed at any privilege level. The signalshred instruction does not automatically pass parameters to the target shred. No mechanism is provided to block a signalshred. Thus software may need to either implement a blocking mechanism before issuing a signalshred or provide a signalshred handler that can nest.

Forkshred raises a SNA exception if the program attempts to start a shred that is already running. A software SNA handler may perform a killshred on the existing shred and return to the forkshred instruction.

The SNA exception is processed by pushing the EIP of the forkshred instruction onto the stack and vectoring to an address given by SC 0. The code at SC 0 should branch to the actual handler. Exception vectors are placed at SC 16 SC 32 etc. Software reserves memory up to SC 4095 to cover 256 possible user level exceptions. The interrupt table in memory SC mechanism is replaced with a cleaner mechanism at a subsequent time.

The multithreading architecture extension allows user level software to suspend or resume shreds using the instructions as follows. To suspend a shred 

It is possible that the shred may already be halted at the time of the suspend action. In this case the signalshred is ignored the suspend handler is never invoked and the joinshred does not wait. The shred state save area in memory retains its initial value which must point to a dummy shred that immediately performs a haltshred. To resume a shred the reverse operations are performed 

When resuming to a thread that was already halted the resume handler will RET to a dummy shred that immediately performs a haltshred. The suspend resume capability opens up the possibility of shred virtualization. Before performing a forkshred software may choose to suspend any existing shred with the same shred number. After performing a joinshred software may choose to resume any existing shred with the same shred number. Because the suspend resume sequences are not re entrant a software critical section is necessary to ensure that only one suspend resume is executed for any given shred at any given time. Using these mechanisms it is possible for the application program to create its own pre emptive shred scheduler.

In alternate embodiments of MAX an instruction exists to fork using the first available shred allocforkshred r32 where r32 is written with the shred number allocated in forkshred r32 specifies the shred number to fork . Allocforkshred also returns a flag indicating if there are any available hardware shreds.

In another embodiment a wait shred instruction provides wait synchronization using shared registers waitshred sh0 sh7 imm . The wait instruction provides wait functionality as an instruction. Without this instruction a loop must be used such as 

In another embodiment joinshred is given a bitmask to wait on multiple shreds. Without the bitmask joinshred waits for one shred to terminate. Multiple joinshreds are required to wait on multiple shreds.

In an alternate embodiment the killshred is not used. Signalshred followed by joinshred may be used instead of killshred. The signalshred handler consists of the haltshred instruction.

In yet another embodiment it is possible to combine forkshred and signalshred. Forkshred and signalshred differ only in their behavior with regard to whether a shred is currently running or halted. If signalshred is allowed to start a halted shred signalshred can potentially replace forkshred.

A method and system to provide user level multithreading are disclosed. Although the present embodiments of the invention have been described with respect to specific examples and subsystems it will be apparent to those of ordinary skill in the art that the present embodiments of the invention are not limited to these specific examples or subsystems but extends to other embodiments as well. The present embodiments of the invention include all of these other embodiments as specified in the claims that follow.

