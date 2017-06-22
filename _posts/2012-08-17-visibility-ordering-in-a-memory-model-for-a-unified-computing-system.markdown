---

title: Visibility ordering in a memory model for a unified computing system
abstract: Provided is a method of permitting the reordering of a visibility order of operations in a computer arrangement configured for permitting a first processor and a second processor threads to access a shared memory. The method includes receiving in a program order, a first and a second operation in a first thread and permitting the reordering of the visibility order for the operations in the shared memory based on the class of each operation. The visibility order determines the visibility in the shared memory, by a second thread, of stored results from the execution of the first and second operations.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08984511&OS=08984511&RS=08984511
owner: ATI Technologies ULC
number: 08984511
owner_city: Markham, Ontario
owner_country: CA
publication_date: 20120817
---
This application claims the benefit of U.S. Provisional Application No. 61 617 470 filed on Mar. 29 2012 which is incorporated herein by reference in its entirety.

The present invention is generally directed to computing systems. More particularly the present invention is directed towards an architecture for unifying the computational components within a computing system.

The desire to use a graphics processing unit GPU for general computation has become much more pronounced recently due to the GPU s exemplary performance per unit power and or cost. The computational capabilities for GPUs generally have grown at a rate exceeding that of the corresponding central processing unit CPU platforms. This growth coupled with the explosion of the mobile computing market e.g. notebooks mobile smart phones tablets etc. and its necessary supporting server enterprise systems has been used to provide a specified quality of desired user experience. Consequently the combined use of CPUs and GPUs for executing workloads with data parallel content is becoming a volume technology.

However GPUs have traditionally operated in a constrained programming environment available primarily for the acceleration of graphics. These constraints arose from the fact that GPUs did not have as rich a programming ecosystem as CPUs. Their use therefore has been mostly limited to two dimensional 2D and three dimensional 3D graphics and a few leading edge multimedia applications which are already accustomed to dealing with graphics and video application programming interfaces APIs .

With the advent of multi vendor supported OpenCL and DirectCompute standard APIs and supporting tools the limitations of the GPUs in traditional applications has been extended beyond traditional graphics. Although OpenCL and DirectCompute are a promising start there are many hurdles remaining to creating an environment and ecosystem that allows the combination of a CPU and a GPU to be used as fluidly as the CPU for most programming tasks.

Existing computing systems often include multiple processing devices. For example some computing systems include both a CPU and a GPU on separate chips e.g. the CPU might be located on a motherboard and the GPU might be located on a graphics card or in a single chip package. Both of these arrangements however still include significant challenges associated with i efficient scheduling ii providing quality of service QoS guarantees between processes iii programming model iv compiling to multiple target instruction set architectures ISAs and v separate memory systems all while minimizing power consumption.

These existing computing systems however rarely account for differences in classes of operations associated with multiple processors and separate memory systems configured for unified computing operations. As such these existing computing systems are also unable to create order between these different classes of operation. This inability to account for the differences and thus not create order between the classes of operations can hamper overall system performance.

What is needed therefore are methods and systems of permitting the reordering of a visibility order of operations in a computer arrangement having GPU and CPU threads that access a shared memory in accordance with a unified memory model.

Although GPUs accelerated processing units APUs and general purpose use of the graphics processing unit GPGPU are commonly used terms in this field the expression accelerated processing device APD is considered to be a broader expression. For example APD refers to any cooperating collection of hardware and or software that performs those functions and computations associated with accelerating graphics processing tasks data parallel tasks or nested data parallel tasks in an accelerated manner.

Embodiments of the present invention under certain circumstances provide a method of permitting the reordering of a visibility order of operations in a computer arrangement configured for permitting threads from different processors e.g. an APD and a CPU to access a shared memory. The processors may be of different types e.g. an APD and a CPU or of the same type e.g. two APD processors . The method includes receiving in a program order a first and a second operation in a first thread and determining a class for each of the first and second operations. The method also includes permitting the reordering of the visibility order for the operations in the shared memory based on the determined class of each operation. The visibility order determines the visibility in the shared memory by a second thread of stored results from the execution of the first and second operations.

Further features and advantages of the present invention as well as the structure and operation of various embodiments of the present invention are described in detail below with reference to the accompanying drawings. The present invention is not limited to the specific embodiments described herein. The embodiments are presented for illustrative purposes only and so that readers will have multiple views enabling better perception of the present invention which is broader than any particular embodiment. Additional embodiments will be apparent to persons skilled in the relevant art s based on the teachings set forth in this patent document.

The term embodiments of the present invention does not require that all embodiments of the present invention include the discussed feature advantage or mode of operation. Alternate embodiments may be devised without departing from the scope of the present invention and well known elements of the present invention may not be described in detail or may be omitted so as not to obscure the relevant details of the present invention. In addition the terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the present invention. For example as used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises comprising includes and or including when used herein specify the presence of stated features integers steps operations elements and or components but do not preclude the presence or addition of one or more other features integers steps operations elements components and or groups thereof.

In one example system also includes a system memory an operating system OS and a communication infrastructure . The OS and the communication infrastructure are described in greater detail below.

The system also includes a kernel mode driver KMD a software scheduler SWS and a memory management unit such as input output memory management unit IOMMU . CPU and APD can be implemented on a single integrated circuit chip or on multiple chips. A person skilled in the relevant art will appreciate that system may include one or more software hardware and firmware components in addition to or different from that shown in the embodiment shown in .

CPU can include not shown one or more of a control processor field programmable gate array FPGA application specific integrated circuit ASIC or digital signal processor DSP . CPU for example executes the control logic including the OS KMD SWS and applications that control the operation of computing system . In this illustrative embodiment CPU according to one embodiment initiates and controls the execution of applications by for example distributing the processing associated with that application across the CPU and other processing resources such as the APD . CPU can include one or more single or multi core CPUs.

APD includes its own compute units not shown such as but not limited to one or more single instruction multiple data SIMD processing cores. Each APD compute unit can include one or more of scalar and or vector floating point units and or arithmetic and logic units ALU . The APD compute unit can also include special purpose processing units not shown such as inverse square root units and sine cosine units. The APD compute units are referred to herein collectively as shader core .

Having one or more SIMD compute units in general makes APD ideally suited for execution of data parallel tasks such as are common in graphics processing.

A set of related operations executed on a compute unit can also be referred to as a compute kernel. In graphics pipeline operations such as pixel processing and other parallel computation operations can require that the same instruction stream or compute kernel can be performed on streams or collections of input data elements. Respective instantiations of the same compute kernel can be executed concurrently on multiple compute units in shader core in order to process such data elements in parallel. A single data item within a stream or collection to which a compute kernel is applied is referred to as a work item. A set of work items across which the instructions of a compute kernel are applied in lock step within a single SIMD processing core is referred to as a thread. Stated another way the term thread refers to a single instance of a program execution with a unique data state.

In an illustrative embodiment each compute unit e.g. SIMD processing core can execute a respective instantiation of a particular thread or process to process incoming data.

A group of threads that are processed under a shared instruction state in a SIMD style process are referred to as a wavefront. For example shader core can simultaneously execute a predetermined number of wavefronts each wavefront comprising a predetermined number of threads.

APD includes its own memory such as graphics memory . Graphics memory provides a local memory for use during computations in APD and each compute unit of the shader core may have its own local data store not shown . In one embodiment APD can include access to local graphics memory as well as access to the system memory . In another embodiment APD can also include access to dynamic random access memory DRAM or other such memories attached directly to the APD separately from system memory .

APD also includes a command processor CP . CP controls the processing within APD . CP also retrieves instructions to be executed from command buffers in system memory and coordinates the execution of those instructions on APD .

In one example CPU inputs commands based on applications into appropriate command buffers . A plurality of command buffers can be maintained with each process scheduled for execution on the APD having its own command buffer .

Command processor can be implemented in hardware firmware or software or a combination thereof. In one embodiment command processor is implemented as a RISC engine with microcode for implementing logic including scheduling logic.

APD may also include a dispatch controller . Dispatch controller includes logic to initiate threads and wavefronts in the shader core. In some embodiments dispatch controller can be implemented as part of command processor .

System also includes a hardware scheduler HWS for selecting a process from a run list for execution on APD . HWS can select processes from run list using round robin methodology based upon priority level or based on other scheduling policies. By way of example the priority level can be dynamically determined. HWS can also include functionality to manage the run list for example by adding new processes and by deleting existing processes from a run list. The run list management logic of HWS is sometimes referred to as a run list controller RLC .

In various embodiments of the present invention when HWS initiates the execution of a process from run list CP begins retrieving and executing instructions from the corresponding command buffer . In some instances command processor can generate one or more commands to be executed within APD which correspond with each command received from CPU . In one embodiment command processor together with other components implements a prioritizing and scheduling of commands on APD in a manner that improves or maximizes the utilization of the resources of APD resources and or system .

APD can have access to or may include an interrupt generator . Interrupt generator can be configured by APD to interrupt the OS when interrupt events such as page faults are encountered by APD . For example APD can rely on interrupt generation logic within IOMMU to create the page fault interrupts noted above.

APD can also include preemption and context switch logic which includes logic to preempt a process currently running within shader core . More specifically context switch logic can include functionality to coordinate the preemption for example by stopping the process and saving the current state of the process e.g. shader core state CP state .

Preemption and context switch logic can also include logic to context switch another process into the APD . The functionality to context switch another process into running on the APD may include instantiating the process for example through the command processor and dispatch controller to run on APD restoring any previously saved state for that process and starting its execution.

System memory includes non persistent memory such as DRAM. System memory can store e.g. processing logic instructions constant values and variable values during execution of portions of applications or other processing logic. For example in one embodiment parts of control logic to perform one or more operations on CPU can reside within system memory during execution of the respective portions of the operation by CPU . The term processing logic or logic as used herein refer to control flow instructions instructions for performing computations and instructions for associated access to resources.

During execution respective applications OS functions processing logic instructions and system software can reside in system memory . Control logic instructions fundamental to OS will generally reside in system memory during execution. Other software instructions including for example kernel mode driver and software scheduler can also reside in system memory during execution of system .

System memory includes command buffers that are used by CPU to send commands to APD . System memory also contains process lists and process information e.g. active list and process control blocks . These lists as well as the information are used by scheduling software executing on CPU to communicate scheduling information to APD and or related scheduling hardware. Access to system memory can be managed by a memory controller which is coupled to system memory . For example requests from CPU or from other devices for reading from or for writing to system memory are managed by the memory controller .

IOMMU is a multi context memory management unit. IOMMU includes logic to perform virtual to physical address translation for memory page access for devices including APD . IOMMU may also include logic to generate interrupts for example when a page access by a device such as APD results in a page fault. IOMMU may also include or have access to a translation lookaside buffer TLB . TLB as an example can be implemented in a content addressable memory CAM to accelerate translation of logical i.e. virtual memory addresses to physical memory addresses for requests made by APD for data in system memory .

Communication infrastructure interconnects the components of system as needed. Communication infrastructure can include not shown one or more of a Peripheral Component Interconnect PCI bus extended PCI PCI E bus advanced microcontroller bus architecture AMBA bus advanced graphics port AGP or such communication infrastructure. Communications infrastructure can also include an Ethernet or similar network or any suitable physical communications infrastructure that satisfies an application s data transfer rate requirements. Communication infrastructure includes the functionality to interconnect components including components of computing system .

OS includes components and software firmware providing functionality to manage the hardware components of system and to provide common services. In various embodiments processes defined by OS can execute on CPU and provide common services. These common services can include for example scheduling applications for execution within CPU fault management interrupt service as well as processing the input and output of other applications.

In various embodiments based on interrupts generated by an interrupt controller such as interrupt controller OS invokes an appropriate interrupt handling routine. For example upon detecting a page fault interrupt OS may invoke an interrupt handler to initiate loading of the relevant page into system memory and to update corresponding page tables.

OS is configured to have functionality to protect system by ensuring that access to hardware components is mediated through OS managed kernel functionality. In effect OS ensures that applications such as applications run on CPU in user space. OS also ensures that applications invoke kernel functionality provided by the OS to access hardware and or input output functionality.

KMD implements an application program interface API through which CPU or applications executing on CPU or other logic can invoke APD functionality. For example KMD can enqueue commands from CPU to command buffers from which APD will subsequently retrieve the commands. Additionally KMD can together with SWS perform scheduling of processes to be executed on APD . SWS for example can include logic to maintain a prioritized list of processes to be executed on the APD.

In other embodiments of the present invention applications executing on CPU can entirely bypass KMD when enqueuing commands.

In some embodiments SWS maintains an active list in system memory of processes to be executed on APD . SWS also selects a subset of the processes in active list to be managed by HWS in the hardware. In an illustrative embodiment this two level run list of processes increases the flexibility of managing processes and enables the hardware to rapidly respond to changes in the processing environment. In another embodiment information relevant for running each process on APD is communicated from CPU to APD through process control blocks PCB .

Processing logic for applications OS and system software can include instructions specified in a programming language such as C and or in a hardware description language such as Verilog RTL or netlists to enable ultimately configuring a manufacturing process through the generation of maskworks photomasks to generate a hardware device embodying aspects of the present invention described herein.

A person skilled in the relevant art will understand upon reading this description that computing system can include more or fewer components than shown in . For example computing system can include one or more input interfaces non volatile storage one or more output interfaces network interfaces and one or more displays or display interfaces.

In graphics pipeline can include a set of blocks referred to herein as ordered pipeline . As an example ordered pipeline includes a vertex group translator VGT a primitive assembler PA a scan converter SC and a shader export render back unit SX RB . Each block within ordered pipeline may represent a different stage of graphics processing within graphics pipeline . Ordered pipeline can be a fixed function hardware pipeline. Other implementations can be used that would also be within the spirit and scope of the present invention.

Although only a small amount of data may be provided as an input to graphics pipeline this data will be amplified by the time it is provided as an output from graphics pipeline . Graphics pipeline also includes DC for counting through ranges within work item groups received from CP pipeline . Compute work submitted through DC is semi synchronous with graphics pipeline .

Compute pipeline includes shader DCs and . Each of the DCs and is configured to count through compute ranges within work groups received from CP pipelines and

The DCs and illustrated in receive the input ranges break the ranges down into workgroups and then forward the workgroups to shader core .

Since graphics pipeline is generally a fixed function pipeline it is difficult to save and restore its state and as a result the graphics pipeline is difficult to context switch. Therefore in most cases context switching as discussed herein does not pertain to context switching among graphics processes. An exception is for graphics work in shader core which can be context switched.

After the processing of work within graphics pipeline has been completed the completed work is processed through a render back unit which does depth and color calculations and then writes its final results to memory .

Shader core can be shared by graphics pipeline and compute pipeline Shader core can be a general processor configured to run wavefronts. In one example all work within compute pipeline is processed within shader core . Shader core runs programmable software code and includes various forms of data such as state data.

Computer arrangement includes CPU APD visibility permission setter and shared memory . Shared memory includes system memory and graphics memory .

One aspect of the memory model for unified computing system described herein is the setting of a visibility order for operations executed by CPU and APD . As used typically herein visibility order of operations refers to the observable order of memory operations as viewed by other operations executing in the same or different threads on one or more processors. In an exemplary operation of an embodiment described herein the visibility order of operations determines the visibility of operations executed by a thread of results stored in a shared memory from the execution of operations in another thread.

Generally speaking in some embodiments two operations from a thread are received in program order by a visibility permission setter and a class for each received operation is determined. The visibility permission setter is configured to determine and set the visibility order for the received operations based on the determined class of each operation. When a second thread views the stored results of the two operations the determined visibility order determines the order that the results of the first thread are perceived by operations in the second thread.

In an example in accordance with UCS application can have two memory operations e.g. a first and a second memory operation in a first thread processed by a processing element either CPU or APD . As the first and second memory operations are processed by the processing element visibility permission setter receives information about the operations. In another embodiment visibility permission setter is part of the thread processing steps inside the processing element. In yet another embodiment visibility permission setter receives the first and second operations processes them and relays the results of the processing to an appropriate portion of shared memory .

Based on information about the two operations received by visibility permission setter the visibility order of the two operations is determined and set. The operation of visibility permission setter is described further below with the description of .

Continuing the example above the operation of visibility permission setter is further described in this section. In different embodiments operation receiver either receives information describing aspects of the first and second operations or receives the first and second operations for handling in a processing pipeline. Class determiner is configured to determine a class of the received operations. Using visibility rules visibility determiner uses the determined class for each operation to determine the visibility of each operation. Examples of different types of operation classes and visibility determining considerations are discussed further below with the descriptions of .

In an embodiment permitted reorders can be determined based on the properties of each memory operation. One approach to comparing the properties of memory operations is to group memory operations into classes and compare the classes. For a particular operation an operation class is determined for each instruction and these determined classes are compared to determine whether the visibility order of the operations can be reordered. It is important to note that shows when reordering of a visibility order is permitted not when it is mandated.

In an embodiment first operation is first operation in the program order of a thread and second operation is the second operation in the program order of the thread. The first and second operations in a thread are received in program order and a class for each operation is determined. The initial global visibility order of first operation and second operation is set to the program order.

In an example reading of table on when first operation in a program order is an unordered store Unordered St B and the second operation is a LoadOpStore LdOpSt C the yes at the intersection of the instructions indicated that visibility reordering is permitted by an embodiment. In another example when first operation in a program order is a load acquire LdAcq D and the second operation is any other listed operation A H the no at the intersection of the instructions indicates that visibility reordering is not permitted by an embodiment.

Example operations classes for an APD are listed on FIG. first operation classes and second operation classes . These example classes C C are shown on and discussed below along with example general principles.

Some embodiments of the unified memory model described herein have general characteristics that guide whether to permit the reordering of the visibility order of memory operations in a UCS such as UCS .

Aspects of write atomicity and value atomicity are discussed below. Some of the example visibility reordering rules set forth in the table of are based on general principles outlined below.

In an embodiment a global visibility order exists for all synchronizing loads and stores LoadOpStores and globally visible unordered stores to all addresses such that the loads return the value of the last store and the order of all synchronizing loads and stores is consistent with the program order of each thread.

Only synchronizing loads and stores are sequentially consistent. Other gore operations are included in this property because they may feed synchronizing loads. Synchronizing stores satisfying synchronizing loads should be the standard use model. For synchronizing operations the visibility order is just an interleaving of each thread s program order.

In an embodiment store operations performed by both the APD and the CPU are write atomic. As used typically herein write atomicity describes a visibility approach where the result of a store operation becomes visible to all reading processes simultaneously. Having write atomicity for store operations can beneficially avoid having two threads with different visibility orders for two respective stores whether to the same or different addresses. An approach used by an embodiment to achieve write atomicity is to maintain an order for different types of load operations.

Loads and stores aligned to their natural datatype are handled atomically Either all of the results of an operation are stored loaded or none of the results are stored loaded respectively. Partial results cannot be created by a stole or loaded by a load operation. Partial results cannot be combined into a result less than the whole. As used typically herein atomic Load plus Store LoadOpStore is used instead of the common term Atomic to identify operations that atomically act as both a load and store.

As discussed below in an embodiment all classes of loads have naturally aligned value atomicity. Value atomicity can also apply to each loaded fragment of an unaligned load operation.

As used typically herein a load operation class includes memory operations that load values from memory storage locations. Some embodiments address the visibility reordering of two classes of load operations an unordered load operation class and a load acquire operation class also termed a synchronizing load operation class and discussed below . Generally speaking in an embodiment with respect to value atomicity as described above loads and stores aligned to their natural data type complete atomically e.g. either all of the data stored is visible or none of it. Neither partial results created by a store nor results based on the merger of various partial results are visible.

Each load operation class has different memory semantics. Illustrative types of load operations used by embodiments of a UCS are described below.

As used typically herein an unordered load operation class is a memory operation that loads a value without having a specified order with respect to other memory operations in the same and different threads.

By way of example the following non limiting illustrative listing depicts unaligned loads UL UL. These unaligned loads UL UL broadly describes visibility ordering characteristics of an unordered load operation class in embodiments 

UL. Value atomicity is applied to the unordered load operation class when operation length is up to a preset maximum number of bits and in a naturally aligned window. Aligned unordered loads and stores aligned to their natural data type up to a preset number of bits have value atomicity but no implicit ordering between operations. In an embodiment the preset number of bits is 64 while in other embodiments a different preset number is used.

UL. Unaligned Loads or loads of more than a preset minimum number of bits can be fragmented into unordered naturally aligned chunks of a size equal to the preset minimum number of bits. In an embodiment the preset minimum number of bits is 64 while in another embodiment a different preset minimum number is used. Unaligned and unordered loads and stores have no value atomicity and no implicit ordering. Sub events for the unordered load operation class have value atomicity.

UL. Each chunk described in UL above is has value atomicity. No visibility ordering constraints are applied between unordered memory operations. An unordered load operation class operation is allowed to see the results of its own or a different thread s store early before the store is globally visible .

UL. Operations of the unordered load class can be reordered in the global visibility order earlier or later than the set program order. The allowed reorder is bounded by the limits of prior operations discussed below such as acquire fence sync thread barrier. The allowed reorder is also bounded by the limits of subsequent operations discussed below such as release fence Sync thread barrier and the same address single thread program order.

UL. Operations of the unordered load operation class are recognized by the UCS global visibility order discussed herein but are allowed to return the value of either the last prior globally visible store or a locally visible store. Generally speaking local visibility can only precede global visibility.

As used typically herein a load acquire operation is related to the store release operation described below and is a load operation that ensures that other operations complete only after it completes. A load acquire can also be termed a synchronizing load such load being a load operation directed to a synchronized variable.

In an embodiment the load acquire operation class has the same characteristics as the unordered load operation class with the following non limiting illustrative exceptions LA LA listed below 

LA. Load acquires are not allowed to see the result of their own or other memory operations on other thread s stores early before for example the corresponding store is globally visible .

LA. Aligned synchronizing loads and stores have value atomicity and implicit ordering between other synchronizing loads and stores as well as implicit order against prior and future unordered loads and stores see . Loads and stores to synchronizing variables are sequentially consistent.

LA. Load acquires create ordering constraints between themselves and other memory related operations e.g. as depicted on no reordering is permitted for any listed memory operation.

LA. An operation of the load acquire class or fence operation against future loads will guarantee that all prior globally visible stores are seen by future loads. Operations of the thread barrier and sync operation classes as discussed below provide the same guarantee to future loads while also forcing prior stores to be globally visible this being important for the operation of spin loops. In an embodiment a spin loop uses an operation of the load acquire class.

As used typically herein a store operation class is a memory operation that stores a value at a memory location. Some embodiments address the visibility reordering of two classes of store operations an unordered store operation class and a store release operation class. Each has different memory semantics. The following non limiting illustrative list S S broadly describes visibility ordering characteristics of store operation classes in embodiments 

S. All forms of stores have naturally aligned value atomicity of a predetermined bit length. In an embodiment this predetermined length is 64 bits. This property also applies to each fragment of an unaligned store discussed below.

S. Stores are only visible locally or globally after data and control dependencies are fully resolved. In an embodiment store visibility is not allowed to be speculative. This prohibition of speculative store visibility acts to define the bounds of local store visibility for unordered loads.

S. Generally speaking in addition to having local store visibility unordered store operations can be reordered.

S. UCSIL and native x86 Stores are eventually seen by all native x86 threads regardless of the load operation class of the operation used.

S. UCSIL and native x86 Stores are not guaranteed to be eventually seen by all UCSIL threads if those threads only use operations of the unordered loads class.

In addition notwithstanding the generalizations noted above with respect to embodiments of store operation classes it is important to note that other embodiments of the specific store operation classes noted below do not necessarily have these characteristics.

The following non limiting illustrative list US US broadly describes visibility ordering characteristics of an unordered store operation class in embodiments 

US. As with the unordered load class of operations described above value atomicity is applied to the unordered store operation class when operation length is up to a preset maximum number of bits and in a naturally aligned window. In an embodiment the preset number of bits is 64 while in another embodiment a different preset number is used.

US. As with the unordered load class of operations described above operations of the unordered store class can be reordered in the global visibility order earlier or later than the set program order. The allowed reorder is bounded by the limits of prior operations discussed below such as acquire fence sync thread barrier. The allowed reorder is also bounded by the limits of subsequent operations discussed below such as release fence sync thread barrier and the same address single thread program order.

US. As with the unordered load class of operations described above unaligned stores or stores of more than a preset minimum number of bits can be fragmented into unordered naturally aligned chunks of a size equal to the preset minimum number of bits. In an embodiment the preset minimum number of bits is 64 while in another embodiment a different preset minimum number is used. Unaligned and unordered loads and stores have no value atomicity and no implicit ordering. Sub events for the unordered load operation class have value atomicity.

US. Each chunk described in US above is has value atomicity. As noted above no visibility ordering constraints are applied between unordered memory operations.

US. An operation of the unordered store operation class is allowed to satisfy an operation of the unordered load operation class from its own or a different thread before the unordered store operation is globally visible .

US. An operation of the unordered store operation class is not allowed to fulfill an atomic load from its own thread before the store is globally visible .

As used typically herein a store release operation is related to the load acquire operation described above and is a store operation that ensures that other operations complete only after it completes. A store release can also be termed a synchronizing store such store being a store operation directed to a synchronized variable.

As with the general visibility order characteristics of the unordered load class of operations described above aligned synchronizing stores have value atomicity and implicit ordering between other synchronizing loads and stores as well as implicit order against prior and future unordered loads and stores see . Loads and stores to synchronizing variables are sequentially consistent.

In an embodiment the store release operation class has the same characteristics as the unordered store class described above with the following non limiting illustrative exceptions SR SR listed below 

SR. Store releases are not allowed to fulfill any loads from their own or other threads early before the store is globally visible .

SR. As shown on store releases create ordering constraints between themselves and other memory related operations.

SR. Operations of the store release class can be completed by being enqueued in a store buffer allowing itself or others memory operations to see its results early. If required a store buffer bypass can be applied to associated load operations before the store release is set to be globally visible.

SR. Both the load acquire and store release operations classes are atomic operations in terms of visibility to each other and any other load or store operation classes. Store release operation class operations are prevented from seeing their own write early. Other operations are also prevented from seeing store release operation class results stored early.

SR. No store load forwarding is applied to store release operation class results until an associated store release operation exits a store buffer just like CAS or XCHG or LoadOpStore.

As used typically herein LoadOpStore also termed load op store and atomic load store operations are operations that use a memory location as both a source and a target. Some embodiments address the visibility reordering of two classes of LoadOpStore operations an unordered LoadOpStore operation class and a LoadAcquireOpStoreRelease operation class.

The following non limiting illustrative list LOS LOS broadly describes visibility ordering characteristics shared by LoadOpStore operation classes in embodiments 

LOS. In an embodiment LoadOpStore operation class operations are generally executed atomically such that it is not possible for any thread in the system to observe or modify the memory location during the LoadOpStore execution sequence.

LOS. Load Operation Store Atomicity A load compute operation and store appear to complete as one atomic event in the context of all other memory model properties. In an embodiment of the LoadOpStore operation the above described properties load operations and store operations apply.

LOS. A LoadOpStore class operation does not allow any store to occur between its Load and Store. In an embodiment the load store pair of operations is indivisible The store portion of the operation can be conditional.

LOS. LoadOpStore can guarantee forward progress in an application. If multiple LoadOpStore are used some LoadOpStores will generally succeed even if all are conditional. Also there should be no spurious failures where a LoadOpStore returns a value inconsistent with a global visibility order regardless of whether it succeeds or fails.

LOS. A LoadOpStore does not see the writes of its thread or other thread s writes early. LoadOpStore is can be beneficially used for multi threaded atomic increments where a result is not needed until the completion of a process.

LOS. Generally speaking when executing a LoadOpStore class operation e.g. XCHG or CAS typical hardware cannot complete the operation until it gets the cache line in the M state with write invalidate protocols . Stated differently a LoadOpStore cannot complete while sitting in a store buffer with others seeing its write early before it gets the protocol s M state. Stated yet another way the combined atomicity requirement and globally visibility order requires no other loads or stores could be ordered between the load and store of the LoadOpStore local only visibility of the store portion is not allowed another load can t get between the two operations .

As used typically herein an unordered LoadOpStore operation class is an execution of a LoadOpStore operation without a visibility order set with respect to other program threads. The following non limiting illustrative list ULOS ULOS broadly describes visibility ordering characteristics of unordered LoadOpStore operation classes in embodiments 

ULOS. Unordered LoadOpStore operations that are unaligned are not allowed and can result in undefined behavior or an exception

ULOS. The load in the unordered LoadOpStore sequence can only be fulfilled from data written by globally visible stores.

As used typically herein a LoadAcquireOpStoreRelease operation class is a LoadOpStore operation that has aspects synchronized with other threads. A LoadAcquireOpStoreRelease can also be termed a synchronizing LoadOpStore such LoadOpStore being a LoadOpStore operation directed to a synchronized variable.

In an embodiment the LoadAcquireOpStoreRelease operation class has the same characteristics as the unordered LoadOpStore class described above with the following non limiting illustrative exceptions E E listed below 

E. Visibility ordering constraints are applied to synchronizing LoadOpStore operations between themselves and other memory related operations in the same thread and other threads.

E. The store portion of the synchronizing LoadOpStore sequence cannot fulfill any loads from the same or other threads early before the store is globally visible .

The following non limiting illustrative list F F broadly describes visibility ordering characteristics of operations of a fence operation class in embodiments 

F. The fence operation class has operations that have four individual ordering requirements attributes that can be combined LoadLoad LoadStore StoreLoad and StoreStore.

F. Generally operations of the fence operation class are non executable fences being used to create visibility ordering relationships between prior and subsequent memory operations. Operations of the fence operation class do not enforce visibility. In an embodiment as discussed below operations of the sync operation class can be used to enforce visibility.

F. Operations of the fence operation class can be predicated and used in conditional code. Ordering constraints imposed by operations in the fence operation class are the union of the specified behavior of each applied fence attribute. As discussed below specifies the fence ordering value for each attribute combination.

F. Reorder of operations of the fence operation class is limited to the program order bounds of prior and future operations specified by the fence operation.

F. The combined OR of a set of Fences is the OR of all pair wise no values for reordering loads and stores as shown in .

Returning to table depicts a table having prior operation class and future operation class . Table provides non limiting illustrative examples of fence operation attributes and how applied fence attributes can enforce an ordering constraint on future operation .

In table prior operation classes A C and future operation classes A C are arranged such that one having skill in the relevant art s given the description herein can determine whether some embodiments of fence operations described herein enforce a visibility ordering constraint on particular future operations .

In an embodiment prior operation class is the class of a prior operation in the program order of a thread and future operation class is a memory operation to be executed in the future. When a memory operation A C is used applying an attribute also termed prior future specifier listed in the operation row allows a visibility ordering constraint to be applied to the future operation class A C in the column associated with the attribute. In an example reading of table when prior operation is an unordered load Unordered Ld LdAcq A and future operation class to be visibility order constrained is a LoadOpStore LdOpSt LdAcqOpStRel C the specified attributes are shown at the intersection of the instructions as LoadLoad or LoadStore. 

Prior and future operations are visibility ordered with respect to the applied fence. The fence is created in program order and completes after guaranteeing its order rules will be followed for future visibility.

A fence completion rule guarantees events specified as first will be become globally visible before any future event specified as second becomes locally or globally visible. A fence completion does not necessarily mean that an associated operation has completed to become global visible.

Future or prior store ordering covers all local and global visibility for stores from the thread executing the fence. Using an operation with any combination of the attributes is valid specifying none of the attributes is a no operation NOP . The following non limiting illustrative list describes example global visibility characteristics the four fence attributes noted above 

As used typically herein a thread sync sync G operation class includes memory operations that are configured to stall the issue of operations from threads based on different criteria for example the visibility order of the operations. Some embodiments address the visibility reordering of two types of sync operation classes a local sync operation class and a global sync operation class. The following is a non limiting illustrative description of visibility ordering characteristics of operations of a sync operation class in embodiments.

Both the sync operation class and the thread barrier operation class are described below and have some properties of fence operations classes described above. In addition operations of the sync operation class stall operation issue for all affected threads until all prior stores have become globally visible and all prior loads have completed in all of those threads. Sync operations can be predicated and used in conditional code.

When applied a global sync forces a thread to wait until all of its prior loads and stores are globally visible acting with the effect of a fully specified fence as described above.

The operation also termed workgroup sync or sync.local is used in some circumstances to provide increased performance as compared to global sync local sync forces a thread to wait until all of its prior loads and stores meet the definitions of global visibility but only for threads within a work group. The effect of this operation can be described as a third intermediate level of visibility between the local visibility and the global visibility previously described. Stated another way with a local sync global visibility rules are used with a reduced group of operations and threads. It should be noted however that globally visible or locally visible stores from outside the workgroup may still be part of the visibility order.

As used typically herein a thread barrier operation class refers to a memory operation allowing the coordinating of memory operations across threads. Some embodiments address the visibility reordering of thread barrier operation classes.

In one embodiment of UCS there are two thread barriers implemented local thread barrier and global thread barrier. Both thread barriers vary in the scope of threads whose visibility they affect but the barrier behavior for both is constrained to a workgroup.

Initially as shown in stage in a first and a second operation are received in a program order in a first thread. For example in an embodiment a first and second operation are received at a visibility permission setter e.g. visibility permission setter from from an application e.g. application .

At stage a class for each of the first and second operations is determined. For example in an embodiment a class determiner e.g. class determiner in permission setter determines the class of the received operations.

At stage the reordering of the visibility order for the operations in the shared memory is permitted based on the determined class of each operation. For example in an embodiment in a computer arrangement e.g. computer arrangement visibility permission setter permits the reordering of received memory operations e.g. memory operations received from application noted above. After stage method ends.

The foregoing description of the specific embodiments will so fully reveal the general nature of the present invention that others may by applying knowledge within the skill of the art readily modify and or adapt for various applications such specific embodiments without undue experimentation without departing from the general concept of the present invention. Therefore such adaptations and modifications are intended to be within the meaning and range of equivalents of the disclosed embodiments based on the teaching and guidance presented herein. It is to be understood that the phraseology or terminology herein is for the purpose of description and not of limitation such that the terminology or phraseology of the present specification is to be interpreted by the skilled artisan in light of the teachings and guidance.

The breadth and scope of the present invention should not be limited by any of the above described exemplary embodiments but should be defined only in accordance with the claims and their equivalents.

