---

title: Thread management in parallel processes
abstract: A method and system are provided for thread management in parallel processes in a multi-core or multi-node system. The method includes receiving monitored hardware metrics information from the multiple cores or multiple nodes on which processes are executed, receiving monitored process and thread information; and globally monitoring the processing across the multiple cores or multiple nodes. The method further includes analyzing the monitored information to minimize imbalances between the multiple cores and/or to improve core or node exploitation and dynamically adjusting the number of threads per process based on the analysis.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08990830&OS=08990830&RS=08990830
owner: International Business Machines Corporation
number: 08990830
owner_city: Armonk
owner_country: US
publication_date: 20120710
---
This invention relates to the field of thread management in parallel processes. In particular the invention relates to thread management in a parallel processes in a multi core or multi node systems.

Coarse grained distributed parallelism using message passing libraries is the traditional method to implement High Performance Computing HPC applications and to exploit clustered architectures. The single thread approach consists of having one process per core. This approach can no longer tackle the multi level parallelism and complexity of new processor architectures.

Computer systems on which parallel processes are executed may include multiple core processors including virtual and or physical cores in a single computing component referred to herein as multi core systems or multiple processor nodes in distributed computing components with inter node communication via a network referred to herein as multi node systems or a combination of multi core and multi node systems. The term process is used to define a process or process carried out on a node or core which may include multiple threads within the process.

The mixed multi process multi threads method is one of the main and most popular solutions to take advantage of the steady increase of the number of physical and virtual Simultaneous Multi Threading SMT feature cores per processor as well as the serial sustained performance per core.

The most common parallel method of using a multi levels implementation for HPC applications is to use a Message Passing Interface MPI over the processes and a fixed number of threads within the processes with a single thread per physical or virtual core. For example using OpenMP Open Multi Processing OpenMP is a trade mark of OpenMP Architecture Review Board implementation and POSIX Portable Operating System Interface for Unix POSIX is a trade mark of IEEE threads. OpenMP is an Application Programming Interface API that supports multi platform shared memory multi processing programming in C C and Fortran on most processor architectures and operating systems. POSIX Portable Operating System Interface for Unix Unix is a trade mark of The Open Group is a family of related standards specified by the IEEE to define the APIs along with shell and utilities interfaces for software compatible with variants of the Unix operating system although the standard can apply to any operating system.

Based on a pool of dedicated resources there are several dynamic techniques to optimize the number of threads per process. All these techniques are generally static and only perform a local optimization on the performance per process

A parallel application is launched on a dedicated set of allocated resources made of a set of computer nodes with physical or virtual cores. The nodes are interconnected with a high performance network for inter node communications. Depending on the user requirements a scheduling system allocates one or more cores per process. The number of threads per process is generally statically defined at the beginning of the execution.

According to a first aspect of the present invention there is provided a method for thread management in parallel processes comprising receiving monitored hardware metrics information from the multiple cores or multiple nodes on which processes are executed receiving monitored process and thread information globally monitoring the processing across the multiple cores or multiple nodes analyzing the monitored information to minimize imbalances between the multiple cores and or to improve core or node exploitation and dynamically adjusting the number of threads per process based on the analysis.

According to a second aspect of the present invention there is provided a system for thread management in parallel processes in a multi core and multi node system comprising multiple processor cores or nodes hardware metrics monitoring agents for monitoring hardware metrics on each of the multiple processor cores or nodes process and thread monitoring agents for monitoring the process and threads running on the multiple processor cores or nodes a global monitoring agent for globally monitoring the processing across the multiple cores or multiple nodes a thread management system including an analyzer component for analyzing the monitored information to minimize imbalances between the multiple cores or nodes and or to improve core or node exploitation and a thread adjustment component for dynamically adjusting the number of threads per process based on the analysis.

According to a third aspect of the present invention there is provided a computer program stored on a computer readable medium and loadable into the internal memory of a digital computer comprising software code portions when said program is run on a computer for performing the method of the first aspect of the present invention.

It will be appreciated that for simplicity and clarity of illustration elements shown in the figures have not necessarily been drawn to scale. For example the dimensions of some of the elements may be exaggerated relative to other elements for clarity. Further where considered appropriate reference numbers may be repeated among the figures to indicate corresponding or analogous features.

In the following detailed description numerous specific details are set forth in order to provide a thorough understanding of the invention. However it will be understood by those skilled in the art that the present invention may be practiced without these specific details. In other instances well known methods procedures and components have not been described in detail so as not to obscure the present invention.

A runtime method and system are described to monitor dynamically and adapt the number of threads per distributed process in a multi core and or multi node environment. The described method and system may combine hardware metrics monitoring compiler analysis and runtime profiling in accordance with a defined pool of resources cores.

Most HPC applications use a SPMD Single Program Multiple Data model where the threaded parallel constructions are generally repetitively executed. The solution of the described method and system is to use hardware counters to monitor the performance of each thread process at the execution time and to gather derived metrics to determine dynamically the performance per process in and out of the multi threaded parallel sections. In addition compiler analysis and runtime profiling may be used.

The number of threads per process on the locally allocated cores or across system nodes may be dynamically adjusted globally. The number of threads may be adjusted by correlating the individual metric per thread in order to optimize the overall performance of the multi core or multi node parallel application. The number of threads per process may be adjusted to reduce the imbalance of the parallel execution and or to improve the serial efficiency per node or core.

Based on a predefined policy some performance derived metrics may be evenly collected and centralized on every node or core and used to define the optimal number of threads per threaded parallel constructions within each process. The described method and system adjust dynamically the number of threads per process from a global view of the behaviour of all the processes. This is done by hardware monitoring capabilities and optionally compiler analysis in order to reduce the imbalance between the processes and increase the performance per core or node.

The described system may also have the capability to modify system parameters to maximize the hardware resources utilization. Depending on the analysis of the hardware resources utilization the system may increase or decrease the number of threads per core or node by enabling or disabling the hardware multi threading mechanism allowing several simultaneous threads per physical core or node. The system may also adapt the frequency of the hardware components the memory configuration and policy process and thread scheduling. The described system may also generate an output monitoring file for the compiler to do profile feedback directed optimization.

Application processes may each have multiple threads which run in parallel on multiple physical or virtual processor cores or nodes . The system may include multiple cores which may be physical or virtual cores in a computer system. Alternatively or additionally the system may have multiple nodes in the form of processor nodes distributed across multiple computer systems with inter node communication .

Monitoring agents may be provided. There may be a global monitoring agent which may be part of a thread management system which may gather the data and communicate with a global accent gathering all the data from the different cores or nodes . There may also be process monitoring agents each in charge of monitoring one or more processes mainly metrics from hardware counters parallel section identification and indexation with one or several processes per agent depending on the size of the system i.e. the number of physical virtual cores . There may also be hardware metrics monitoring agents with normally one agent per physical core or node to get the hardware counters.

The hardware metrics monitoring agents may be provided on each of the physical or virtual processor cores or nodes . The hardware metrics monitoring agents together with the global monitoring agent may identify and index the parallel sections. This may be triggered by the system code using Application Programming Interfaces APIs . The hardware monitoring agents may then monitor hardware metrics using hardware counts on each core . Hardware performance counters are a set of special purpose registers built into modem microprocessors to store the counts of hardware related activities within computer systems. The hardware monitoring agents may be configured to monitor some specific hardware counters based on a global policy and metrics to adjust the number of threads per process.

The described system may include process and thread monitoring and control components for monitoring and controlling the application processes . The process and thread monitoring and control components may use information from process monitoring agents as well as the gathered hardware metrics from the agents .

A compiler analysis component may optionally be provided which may analyze the process and thread monitoring components outputs and provide analyzed information for the compiler. For example the outputs may include the time spend in each parallel construction the overhead to manage the threads the imbalance between the threads which can be due to different workloads per thread use of the hardware units source etc. . This information may be used by the compiler to generate potentially better optimized codes by for instance changing some optimizations techniques. However this aspect is not dynamic. It is an added feature of the system knowing that the system may be strongly coupled with the multi threaded runtime part of the compiler runtime at least for OpenMP approach .

A thread management system may receive monitored information from the process and thread monitoring and control components including the hardware metrics monitored information and optionally the compiler analysis from the compiler analysis component .

The thread management system may build derived metrics and determine an optimal number of threads per process in each parallel construction based on the monitored information and the compiler analysis. Parameters of the system may then be configured and the threads adjusted via the process and thread monitoring and control components . The parameters may include the SMT configuration including the number of simultaneous threads per physical core i.e. virtual cores frequency process thread scheduling policy memory etc.

Referring to an example embodiment of the thread management system is described. The thread management system may include a global monitoring component including a process and thread monitoring receiver and a hardware metrics receiver for receiving the monitored data. Optionally a compiler analysis receiver may be provided for receiving information from a compiler analysis component analyzing process and thread monitoring of application processes.

The thread management system may include an initializing component for initializing and identification of data on each system node. The initializing component may include a parallel construction identifier component for each process a synchronizer component for synchronizing steps between threads and processes and a correlation component for determining potential correlation between processes.

An analyzer component may be provided for analyzing the monitored and input data. The analyzer component may include an input component for inputting defined resources of a system node scheduling policies monitored data from the performance monitoring component and initialization data from the initializing component . The scheduling policies may include for example thread process priority thread binding thread versus core for example binding all the threads of a process to the same physical core or each thread on a different physical core scheduling the threads based on the numbering of the physical or virtual core consecutively or in a round robin manner etc.

The analyzer component may also include an analysis trigger component for triggering the analysis and thread adjustment in a system node. The analysis trigger component may include a defined trigger component for identifying when a trigger event occurs for example at a time interval at a synchronization point at the end of a parallel construction or according to a user API etc. A centralizing component may be provided for centralizing the data performance per node or system at the trigger event.

The analyzer component may also include a performance analysis component including an imbalance minimizing component for minimizing imbalance between processes and threaded parallel construction and a hardware optimization component for optimizing the hardware resource utilization and parameters including the utilization rate of the hardware components of the cores or nodes for example memory subsystem branch unit Integer unit Load and Store units Float point using instruction decoding etc. .

An output component may use the output of the analyzer component and may provide adjustments to the system. A thread adjustment component may be provided to adjust the threads for each process on a node. A hardware adjustment component may be provided to adjust the resource utilization and parameters. A runtime adjustment component may be provided to adjust the runtime.

Referring to an exemplary system for implementing aspects of the invention includes a data processing system suitable for storing and or executing program code including at least one processor coupled directly or indirectly to memory elements through a bus system . The memory elements can include local memory employed during actual execution of the program code bulk storage and cache memories which provide temporary storage of at least some program code in order to reduce the number of times code must be retrieved from bulk storage during execution.

The memory elements may include system memory in the form of read only memory ROM and random access memory RAM . A basic input output system BIOS may be stored in ROM . System software may be stored in RAM including operating system software . Software applications may also be stored in RAM .

The system may also include a primary storage means such as a magnetic hard disk drive and secondary storage means such as a magnetic disc drive and an optical disc drive. The drives and their associated computer readable media provide non volatile storage of computer executable instructions data structures program modules and other data for the system . Software applications may be stored on the primary and secondary storage means as well as the system memory .

The computing system may operate in a networked environment using logical connections to one or more remote computers via a network adapter .

Input output devices can be coupled to the system either directly or through intervening I O controllers. A user may enter commands and information into the system through input devices such as a keyboard pointing device or other input devices for example microphone joy stick game pad satellite dish scanner or the like . Output devices may include speakers printers etc. A display device is also connected to system bus via an interface such as video adapter .

Parallel mixed multi process multi thread applications may be started . The application may be started with a defined number of threads per process. This number may be defined by the user at the runtime and is the same for all the processes. In other systems the processes may be launched with a larger pool of threads even if some are keep idle by the thread runtime.

The monitoring system is started using monitoring agents which may include a global agent A process monitoring agents B and hardware metrics monitoring agents C.

An initialization step may be carried out in which parallel constructions may be identified synchronization steps between threads and processes identified and potential correlations between processes and synchronization steps undertaken.

Optionally the monitoring information may be used for compiler analysis to gather data for the compiler for the next compilation.

The performance and behaviour of each process and its threads may be continuously monitored and characterized using derived information.

Most of the HPC applications are a partner where the functions parts i.e. parallel section are executed a large number of times. These parallel sections may be identified and indexed by the system by itself or using Application Programming Interfaces API in the code . Each parallel section may execute with an amount of threads and globally monitored with the system.

At a defined event such as a timestep sample or synchronisation point end of a parallel construction or user APIs the data performance per node or per system may be centralized and analyzed .

Based on the behaviour and the user admin policy it may be determined per node whether or not to change the number of threads of some processes knowing the total number of processes per node. This total number of threads per node can be defined by the user and by the system hardware parameters for example the max number of virtual cores for a standard HPC environment.

If it is not determined to change the number of threads then the monitoring may continue. If it is determined to change the number of threads then the system hardware parameters may be adjusted for example by reducing or increasing the number of virtual cores and implicitly the total of threads on the node . For example if it is assessed that more simultaneous threads should be run per physical core the system will potentially adjust the system parameters the thread binding or memory policy if possible on the system .

Before entering a parallel section the runtime may contact the system to identify the parallel section or request the number of threads to activate in his pool as well as on which physical or virtual cores to execute the threads.

Based of the defined resources allocated to the job and a resource optimization and scheduling policy data is gathered and analyzed to adjust the number of threads for each process on the node to reduce the imbalance between processes and threaded parallel constructions as well as optimize the hardware resource utilization optimal number of SMT per core .

During the first pass the multi threaded runtime may contact the local agent to identify the sections . These sections may be monitored and the global performance may be analysed. The length of the arrows indicates the times. As with many parallel sections there is a synchronisation between the threads.

The thread system management may identify for instance an imbalanced between the processes 0 and 1 for the parallel constructions 0 and 2 and may estimate that the global time can be reduced by adjusting the number of threads between process 0 and 1. This may be done in the next pass by setting five threads in parallel construction 0 and 2 for process 1 and respectively three threads for process 0 always with a total of eight threads on the node in this example .

This is a simple example scenario for an HPC SPMD application with an imbalance between the processes. Other scenarios may include increasing the number of threads for all the processes and enabling SMT features more virtual cores to improve serial efficiency.

An API may allow the targeting of parts of the code to reduce the potential overhead. The gathering and thread tuning phase triggers can be defined by the user using API in the codes or at the beginning of the executions. There is a wide range of possible triggers at regular time steps after a repetitive series of parallel constructions 

A thread tuning policy may address an imbalance between the distributed processes or between similar threaded parallel constructions locally in each node or globally for the system SMT tuning type of hardware counters and derived metrics timers number of cycles per instructions Flops cache misses IO etc. .

The overall performance and the parallel scalability strongly depend on the balance between processes. The number of threads per process is dynamically monitored and adapted to balance the processes and therefore optimize the entire application at any given time.

The invention can take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. In a preferred embodiment the invention is implemented in software which includes but is not limited to firmware resident software microcode etc.

The invention can take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium can be any apparatus that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The medium can be an electronic magnetic optical electromagnetic infrared or semiconductor system or apparatus or device or a propagation medium. Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

Improvements and modifications can be made to the foregoing without departing from the scope of the present invention.

