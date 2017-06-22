---

title: Controlling the state of duplexing of coupling facility structures
abstract: A coupling facility is coupled to one or more other coupling facilities via one or more peer links. The coupling of the facilities enables various functions to be supported, including the duplexing of structures of the coupling facilities. Duplexing is performed on a structure basis, and thus, a coupling facility may include duplexed structures, as well as non-duplexed or simplexed structures.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09253046&OS=09253046&RS=09253046
owner: INTERNATIONAL BUSINESS MACHINES CORPORATION
number: 09253046
owner_city: Armonk
owner_country: US
publication_date: 20121221
---
This application is a continuation of U.S. Pat. No. 8 341 188 issued Dec. 25 2012 entitled CONTROLLING THE STATE OF DUPLEXING OF COUPLING FACILITY STRUCTURES which is a continuation of U.S. Pat. No. 7 940 706 issued May 10 2011 entitled CONTROLLING THE STATE OF DUPLEXING OF COUPLING FACILITY STRUCTURES which is a continuation of U.S. Pat. No. 7 257 091 issued Aug. 14 2007 entitled CONTROLLING THE STATE OF DUPLEXING OF COUPLING FACILITY STRUCTURES which is a divisional of U.S. Pat. No. 7 013 305 issued Mar. 14 2006 entitled MANAGING THE STATE OF COUPLING FACILITY STRUCTURES DETECTING BY ONE OR MORE SYSTEMS COUPLED TO THE COUPLING FACILITY THE SUSPENDED STATE OF THE DUPLEXED COMMAND DETECTING BEING INDEPENDENT OF MESSAGE EXCHANGE each of which is hereby incorporated herein by reference in its entirety.

This application contains subject matter which is related to the subject matter of the following applications patents each of which is assigned to the same assignee as this application. Each of the below listed applications patents is hereby incorporated herein by reference in its entirety 

 TEST TOOL AND METHODS FOR FACILITATING TESTING OF DUPLEXED COMPUTER FUNCTIONS Jones et al. U.S. Pat. No. 6 910 158 B2 issued Jun. 21 2005 

 RESTARTING A COUPLING FACILITY COMMAND USING A TOKEN FROM ANOTHER COUPLING FACILITY COMMAND Elko et al. U.S. Pat. No. 6 813 726 B2 issued Nov. 2 2004 

 DYNAMICALLY DETERMINING WHETHER TO PROCESS REQUESTS SYNCHRONOUSLY OR ASYNCHRONOUSLY Jordan et al. U.S. Pat. No. 7 099 935 issued Aug. 29 2006 

 COUPLING OF A PLURALITY OF COUPLING FACILITIES USING PEER LINKS Brooks et al. U.S. Pat. No. 6 954 817 issued Oct. 11 2005 

 SYNCHRONIZING PROCESSING OF COMMANDS INVOKED AGAINST DUPLEXED COUPLING FACILITY STRUCTURES Elko et al. U.S. Pat. No. 6 859 866 B2 issued Feb. 22 2005 

 SYSTEM MANAGED DUPLEXING OF COUPLING FACILITY STRUCTURES Allen et al. U.S. Pat. No. 6 944 787 issued Sep. 13 2005 

 METHOD SYSTEM AND PROGRAM PRODUCTS FOR PROVIDING USER MANAGED DUPLEXING OF COUPLING FACILITY CACHE STRUCTURES Elko et al. U.S. Pat. No. 6 539 495 B1 issued Mar. 25 2003 

 CASTOUT PROCESSING FOR DUPLEXED CACHE STRUCTURES Elko et al. U.S. Pat. No. 6 438 654 B1 issued Aug. 20 2002 

 SYSTEM MANAGED REBUILD OF COUPLING FACILITY STRUCTURES Allen et al. U.S. Pat. No. 6 266 783 issued Jul. 24 2001 

 METHOD SYSTEM AND PROGRAM PRODUCTS FOR COPYING COUPLING FACILITY STRUCTURES Dahlen et al. U.S. Pat. No. 6 609 214 B1 issued Aug. 19 2003 

 METHOD SYSTEM AND PROGRAM PRODUCTS FOR MODIFYING COUPLING FACILITY STRUCTURES Dahlen et al. U.S. Pat. No. 6 594 667 B2 issued Jul. 15 2003 

 DIRECTED ALLOCATION OF COUPLING FACILITY STRUCTURES Dahlen et al. U.S. Pat. No. 6 584 554 B1 issued Jun. 24 2003 

 METHOD SYSTEM AND PROGRAM PRODUCTS FOR COPYING COUPLING FACILITY LOCK STRUCTURES Dahlen et al. U.S. Pat. No. 6 546 414 B1 issued Apr. 8 2003 

 METHOD OF CONTROLLING THE FLOW OF INFORMATION BETWEEN SENDERS AND RECEIVERS ACROSS LINKS BEING USED AS CHANNELS Gregg et al. U.S. Pat. No. 6 681 254 issued Jan. 20 2004 

 SYSTEM OF CONTROLLING THE FLOW OF INFORMATION BETWEEN SENDERS AND RECEIVERS ACROSS LINKS BEING USED AS CHANNELS Gregg et al. Ser. No. 09 150 942 filed Sep. 10 1998 Abandoned Apr. 21 2003 

 SYSTEM OF PERFORMING PARALLEL CLEANUP OF SEGMENTS OF A LOCK STRUCTURE LOCATED WITHIN A COUPLING FACILITY Dahlen et al. U.S. Pat. No. 6 233 644 B1 issued May 15 2001 

 MULTI CHANNEL INTER PROCESSOR COUPLING FACILITY PROCESSING RECEIVED COMMANDS STORED IN MEMORY ABSENT STATUS ERROR OF CHANNELS Elko et al. U.S. Pat. No. 5 574 945 issued Nov. 12 1996 

 METHOD SYSTEM AND PROGRAM PRODUCTS FOR MANAGING CHANGED DATA OF CASTOUT CLASSES Elko et al. U.S. Pat. No. 6 230 243 B1 issued May 8 2001 

 METHOD AND SYSTEM FOR CAPTURING AND CONTROLLING ACCESS TO INFORMATION IN A COUPLING FACILITY Neuhard et al. U.S. Pat. No. 5 630 050 issued May 13 1997 

 DYNAMICALLY ASSIGNING A DUMP SPACE IN A SHARED DATA FACILITY TO RECEIVE DUMPING INFORMATION TO BE CAPTURED Elko et al. U.S. Pat. No. 5 664 155 issued Sep. 2 1997 

 METHOD AND APPARATUS FOR DISTRIBUTED LOCKING OF SHARED DATA EMPLOYING A CENTRAL COUPLING FACILITY Elko et al. U.S. Pat. No. 5 339 427 issued Aug. 16 1994 

 METHOD AND SYSTEM FOR LOG MANAGEMENT IN A COUPLED DATA PROCESSING SYSTEM Geiner et al. U.S. Pat. No. 5 737 600 issued Apr. 7 1998 

 METHOD OF PERFORMING PARALLEL CLEANUP OF SEGMENTS OF A LOCK STRUCTURE Dahlen et al. U.S. Pat. No. 6 178 421 B1 issued Jan. 23 2001 

 SPEEDING UP COMMUNICATION RATES ON LINKS TRANSFERRING DATA STRUCTURES BY A METHOD OF HANDING SCATTER GATHER OF STORAGE BLOCKS IN COMMANDED COMPUTER SYSTEMS Gregg et al. U.S. Pat. No. 5 948 060 issued Sep. 7 1999 

 METHOD OF MANAGING RESOURCES IN ONE OR MORE COUPLING FACILITIES COUPLED TO ONE OR MORE OPERATING SYSTEMS IN ONE OR MORE CENTRAL PROGRAMMING COMPLEXES USING A POLICY Allen et al. U.S. Pat. No. 5 634 072 issued May 27 1997 

 METHOD AND APPARATUS FOR OPTIMIZING THE HANDLING OF SYNCHRONOUS REQUESTS TO A COUPLING FACILITY IN A SYSPLEX CONFIGURATION Kubala et al. U.S. Pat. No. 5 923 890 issued Jul. 13 1999 

 METHOD FOR RECEIVING MESSAGES AT A COUPLING FACILITY Elko et al. U.S. Pat. No. 5 706 432 issued Jan. 6 1998 

 COMMAND EXECUTION SYSTEM FOR USING FIRST AND SECOND COMMANDS TO RESERVE AND STORE SECOND COMMAND RELATED STATUS INFORMATION IN MEMORY PORTION RESPECTIVELY Elko et al. U.S. Pat. No. 5 392 397 issued Feb. 21 1995 

 SOFTWARE CACHE MANAGEMENT OF A SHARED ELECTRONIC STORE IN A SUPPLEX Elko et al. U.S. Pat. No. 5 457 793 issued Oct. 10 1995 

 REQUESTING A DUMP OF INFORMATION STORED WITHIN A COUPLING FACILITY IN WHICH THE DUMP INCLUDES SERVICEABILITY INFORMATION FROM AN OPERATING SYSTEM THAT LOST COMMUNICATION WITH THE COUPLING FACILITY Neuhard et al U.S. Pat. No. 5 860 115 issued Jan. 12 1999 

 AUTHORIZATION METHOD FOR CONDITIONAL COMMAND EXECUTION Elko et al U.S. Pat. No. 5 450 590 issued Sep. 12 1995 

 IN A MULTIPROCESSING SYSTEM HAVING A COUPLING FACILITY COMMUNICATING MESSAGES BETWEEN THE PROCESSORS AND THE COUPLING FACILITY IN EITHER A SYNCHRONOUS OPERATION OR AN ASYNCHRONOUS OPERATION Elko et al. U.S. Pat. No. 5 561 809 issued Oct. 1 1996 

 COUPLING FACILITY FOR RECEIVING COMMANDS FROM PLURALITY OF HOSTS FOR ACTIVATING SELECTED CONNECTION PATHS TO I O DEVICES AND MAINTAINING STATUS THEREOF Elko et al. U.S. Pat. No. 5 463 736 issued Oct. 31 1995 

 METHOD AND SYSTEM FOR MANAGING DATA AND USERS OF DATA IN A DATA PROCESSING SYSTEM Allen et al. U.S. Pat. No. 5 465 359 issued Nov. 7 1995 

 METHODS AND SYSTEMS FOR CREATING A STORAGE DUMP WITHIN A COUPLING FACILITY OF A MULTISYSTEM ENVIRONMENT Elko et al. U.S. Pat. No. 5 761 739 issued Jun. 2 1998 

 METHOD AND APPARATUS FOR COUPLING DATA PROCESSING SYSTEMS Elko et al. U.S. Pat. No. 5 317 739 issued May 31 1994 

 METHOD AND APPARATUS FOR EXPANSION CONTRACTION AND REAPPORTIONMENT OF STRUCTURED EXTERNAL STORAGE STRUCTURES Dahlen et al. U.S. Pat. No. 5 581 737 issued Dec. 3 1996 

 MULTIPLE PROCESSOR SYSTEM HAVING SOFTWARE FOR SELECTING SHARED CACHE ENTRIES ON AN ASSOCIATED CASTOUT CLASS FOR TRANSFER TO A DASD WITH ONE I O OPERATION Elko et al. U.S. Pat. No. 5 493 668 issued Feb. 20 1996 

 INTEGRITY OF DATA OBJECTS USED TO MAINTAIN STATE INFORMATION FOR SHARED DATA AT A LOCAL COMPLEX Elko et al. U.S. Pat. No. 5 331 673 issued Jul. 19 1994 

 METHOD AND APPARATUS FOR PERFORMING CONDITIONAL OPERATIONS ON EXTERNALLY SHARED DATA Elko et al. U.S. Pat. No. 5 742 830 issued Apr. 21 1998 

 METHOD AND SYSTEM FOR RECONFIGURING A STORAGE STRUCTURE WITHIN A STRUCTURE PROCESSING FACILITY Allen et al. U.S. Pat. No. 5 515 499 issued May 7 1996 

 METHOD FOR COORDINATING EXECUTING PROGRAMS IN A DATA PROCESSING SYSTEM Allen et al. U.S. Pat. No. 5 604 863 issued Feb. 18 1997 and

 SYSTEM AND METHOD FOR MANAGEMENT OF OBJECT TRANSITIONS IN AN EXTERNAL STORAGE FACILITY ACCESSED BY ONE OR MORE PROCESSORS Dahlen et al. U.S. Pat. No. 5 887 135 issued Mar. 23 1999.

This invention relates in general to data processing within a distributed computing environment and in particular to the duplexing of structures such as structures of one or more coupling facilities.

Some distributed computing environments such as Parallel Sysplexes today provide a non volatile shared storage device called the coupling facility that includes multiple storage structures of either the cache or list type. These structures provide unique functions for the operating system and middleware products employed for the efficient operation of a Parallel Sysplex. For example the cache structures provide directory structures and cross invalidation mechanisms to maintain buffer coherency for multisystem databases as well as a fast write medium for database updates. These are used by for instance the data sharing versions of DB2 and IMS offered by International Business Machines Corporation Armonk N.Y.

The list structures provide many diverse functions. One such list structure function is to provide for high performance global locking and this function is exploited by such products as the IMS Resource Lock Manager IRLM and the Global Resource Serialization GRS function in OS 390 offered by International Business Machines Corporation Armonk N.Y. Another list structure function is to provide a message passing mechanism with storage for maintaining multiple messages on a per system basis and a mechanism for notifying a system of the arrival of new messages. This function is exploited by the XCF component of OS 390 which in turn is exploited by numerous multisystem applications for providing a capability to pass messages between their various instances. A third list structure function is to provide for shared queue structures that can be ordered and accessed by LIFO FIFO ordering by key or by name. Workload Manager WLM IMS Shared Message Queues and MQ Series all offered by International Business Machines Corporation Armonk N.Y. are examples of exploiters of this feature. While these functions provide examples of the list structure uses other uses exist.

Various components of a Parallel Sysplex have been documented in numerous applications patents which are listed above and hereby incorporated herein by reference in their entirety. The capabilities defined in some of those patents provide the basic system structure to create and manage cache and list structure instances. Additionally various of the applications patents listed above provide extensions to the base functions of the Parallel Sysplex.

In many situations a failure of the coupling facility that contains various structures requires significant recovery actions to be taken by the owning applications. For example for database caches and queues this may require using backup log data sets and or tapes. This is a time consuming process that results in a loss of access to the application during the recovery operation. Other structures such as lock tables may require reconstruction of partial lock tables from in storage copies along with failures of in flight transactions. Still other structures such as message passing structures may lose all data and require re entry from the application. So there is a proliferation of diverse recovery schemes with different recovery times and impacts. Moreover since the failure of a coupling facility results in all resident structures failing the diverse recovery actions are occurring concurrently which can cause serious disruptions in the Parallel Sysplex.

Thus a need exists for a configuration of a Parallel Sysplex that provides less disruptions. In particular a need exists for a high availability coupling facility which improves on the recovery times and impacts of existing recovery techniques while also provides for a consistent recovery design across various structure types. As a particular example a need exists for one or more capabilities that facilitate duplexing of structures in separate coupling facilities coupled to one another.

The shortcomings of the prior art are overcome and additional advantages are provided through the provision of a method of managing duplexing of coupling facility structures. The method includes for instance initiating activation of duplexing of a coupling facility structure wherein an instance of the coupling facility structure is located within one coupling facility and wherein the coupling facility structure is a coupling facility cache structure or a coupling facility list structure determining whether another coupling facility in which another instance of the coupling facility structure is to reside is connected to the one coupling facility and activating duplexing based on the determining indicating that the another coupling facility is connected to the one coupling facility.

Systems and computer program products corresponding to the above summarized computer program products are also described and may be claimed herein.

Additional features and advantages are realized through the techniques of the present invention. Other embodiments and aspects of the invention are described in detail herein and are considered a part of the claimed invention.

In accordance with an aspect of the present invention at least one coupling facility is coupled to one or more other coupling facilities using one or more peer connections. The coupling of the coupling facilities enables a variety of capabilities to be performed including but not limited to the duplexing of coupling facility structures.

The duplexing of the structures is performed in a manner that is transparent to the users of the structures. That is when a user of a structure issues a command against the structure the user is unaware that the structure and thus the command are duplexed.

In one aspect of the present invention a high availability design of coupling facility structures is provided by duplexing a desired structure in two separate coupling facilities. This design improves on the recovery times and impacts of existing recovery techniques while also provides for a consistent recovery design across the various structure types.

In one embodiment various aspects of duplexing are accomplished by extending the architecture and physical configuration of components of the Parallel Sysplex. For instance a coupling facility to coupling facility peer connection is provided that allows for protocol flows between the coupling facilities through a signaling mechanism. As a further example a mechanism is provided for the operating system component of z OS the Locking Facility Support Services LFSS component to create a duplexed copy of a given structure in two separate coupling facilities and to then split commands into two separate commands each sent in parallel to the two structure instances. This provides for parallel execution of the commands and for efficient re execution of the commands on congested links. Moreover in a further aspect of the present invention a protocol extension to the command concurrency mechanism in the coupling facility is provided which exchanges signals on the peer connection in a way that maintains synchronization of the structure contents for each command that is executed. These functions are provided in a manner which has optimal Sysplex performance in one example.

The duplexing state of a cache or list structure is maintained in a global control referred to as the duplexing vector which is indexed by a Structure Identifier SID . When the bit corresponding to a SID value is B 1 duplexing is active and the duplexing controls in the structure are valid. The duplexing controls include a duplexing system identifier and a duplexing system signaling vector token as described below. These controls are used in conjunction with information provided in a message command block MCB of a duplexed command to construct a duplexing signal.

In one embodiment structures are not differentiated as primary or secondary within the structure. Primary or secondary structures are determined by how they are used. In some cases new request operands are defined to allow certain actions in the secondary to be suppressed but these are done on a command basis and do not create new states in the structure. This simplifies recovery when a primary structure fails since no state changes are needed in the secondary to make it act as a primary.

While a secondary structure may be promoted to a primary structure the opposite is not true in this example. That is a primary structure is not demoted to a secondary structure.

Three architectural models of structure duplexing are possible that meet the attributes of application transparency failure isolation and command concurrency across two structures. These models include for instance 

 1 A model that includes a coupling facility to coupling facility signaling protocol that coordinates command completion across the coupling facilities during command execution .

 2 A model that includes an external locking protocol that serializes command execution explicitly . A variation of this protocol that satisfies the desired attributes of failure isolation and command concurrency for a certain type of structure but is not application transparent is described in co pending U.S. patent application Ser. No. 09 255 382 entitled Method System and Program for Providing a User Managed Duplexing of Coupling Facility Cache Structures filed Feb. 22 1999 which is hereby incorporated herein by reference in its entirety. 

 3 A store and forward model where the primary coupling facility forwards each command on a standard ISC channel connected to a remote coupling facility. The remote coupling facility then executes the command and returns the result to the primary coupling facility which then completes the command to the operating system. This model is depicted in .

Two instances of the coupling facility structure are maintained in separate coupling facilities referred to as the primary coupling facility and the secondary coupling facility. A peer connection such as an Intersystem Channel ISC link couples the two coupling facilities. The peer ISC link can transmit both primary message commands and secondary message commands in either direction. This may be physically represented by either two unidirectional links one with a sender channel on the primary coupling facility and a receiver channel on the secondary coupling facility and the second link oppositely configured. This may also be represented by a single physical link where the channel interface in each coupling facility supports both sender and receiver functionality. This latter capability exists in ISC3 links and their variants ICB3 and IC3 all of which are offered by International Business Machines Corporation Armonk N.Y.

The peer ISC link between the coupling facilities is used for instance to exchange message path commands on the primary message command interface to configure and couple the two coupling facilities. Once configured and coupled the peer ISC link is also used to send secondary commands of the list notification type to exchange signals as part of a signaling protocol for command execution. The sending and receiving of these secondary commands is managed by a coupling facility component called a signaling protocol engine . Requests by the cache and list component of the coupling facility for sending and receiving duplexing signals flow through the signaling protocol engine.

One embodiment of the steps in a normal command execution for the coupling facility to coupling facility duplexing model are shown in in numeric sequence that approximates the time sequence of the command. In these steps various components of the signaling protocol are described. A more complete description of the signaling protocol is provided in a following section. The extensions to the protocol described later are used to enhance the performance and reliability of the basic protocol described here.

Step 1. The user application generates a command and communicates this command to the LFSS through a system macro interface.

Step 2. The LFSS creates two copies of the command sending one to the primary coupling facility and the second to the secondary coupling facility. The LFSS uses an asynchronous SEND MESSAGE interface without notification to allow the two commands to be initiated in parallel. The LFSS also sets a synchronous completion on initial status SCIS bit of the SEND MESSAGE to minimize the effects of any busy conditions encountered on the channel interface. A link subsystem LSS component of the coupling facility control code CFCC in the primary coupling facility receives the command and transfers control to the cache or list component as appropriate. Likewise the link subsystem LSS component in the secondary coupling facility receives the command and transfers control to the cache or list component as appropriate.

Step 3. The cache list component of the primary coupling facility executes the command to the point where a message response block MRB would be returned to the application. But before sending the MRB and while the internal latches are held for the objects referenced by the command a request is made to the signaling protocol engine in the primary coupling facility to send a completion signal on the peer ISC link to the secondary coupling facility. Likewise the cache list component of the secondary coupling facility executes the command to the point where the MRB would be returned to the application. But before sending the MRB and while the internal latches are held for the objects referenced by the command a request is made to the signaling protocol engine in the secondary coupling facility to send a completion signal on the peer ISC link to the primary coupling facility.

Step 4. The signaling protocol engine in the primary coupling facility sends the completion signal to the secondary coupling facility and then waits for the reception of the completion signal from the secondary coupling facility. Likewise the signaling protocol engine in the secondary coupling facility sends the completion signal to the primary coupling facility and then waits for the reception of the completion signal from the primary coupling facility.

Step 5. When the primary coupling facility recognizes the reception of the completion signal from the secondary coupling facility the primary coupling facility sends the MRB and releases the latches. Likewise when the secondary coupling facility recognizes the reception of the completion signal from the primary coupling facility it also sends the MRB and releases the latches. If a failure occurs during this period of time and either the primary coupling facility or the secondary coupling facility fails to recognize the reception of a completion signal then duplexing is broken by the coupling facility by resetting the duplexing active indicator for the structure. This is described in more detail in a subsequent section. 

Step 6. Assuming no errors have occurred the LFSS receives both MRBs from the two coupling facilities and constructs a single message response block by reconciling the results of the two MRBs and gives this response to the application. If on the other hand duplexing has been broken by one of the two coupling facilities then the operating system will invoke fail over recovery and one of the two structures will be selected as the surviving instance. Once the error is corrected duplexing can be reestablished.

User transparency is satisfied because the duplexing functions are performed by the LFSS without awareness by the user application.

Failure isolation is satisfied by creating two copies of the structure in separate facilities each of which can continue as the surviving structure in a situation involving the failure of the other.

Command atomicity is satisfied by maintaining latches on both structures until both commands complete.

Performance is optimized in several ways. First sending the commands in parallel allows for maximum overlap of data transfer and command execution. Second by exchanging completion signals immediately upon reaching the MRB send point in the command the completion can be detected with minimal intervening latency. Third the amount of data sent in the signal itself is small relative to the amount of data sent on the primary link for the command. So a single peer ISC link can handle the combined signal traffic generated by commands sent on a significant number of primary ISC links. In fact for small distances a single ISC link can handle the combined traffic of the commands generated in a 32 system Parallel Sysplex. Fourth by using list notification as the signaling transport mechanism the signal can be processed by the receiver channel engine without needing to interrupt the coupling facility control code CFCC to process the signal. Fifth by using the SCIS facility contention detected by a SEND MESSAGE can be minimized by causing redrives to be performed substantially immediately.

Although in the embodiment described above an ISC link is used to couple the two coupling facilities this is only one example. Other links may be used including for instance an ICB or IC link. Further more than two coupling facilities may be coupled to one another. However it is not necessary for all coupling facilities to be coupled to each other. For instance a third coupling facility may be coupled to Coupling Facility 2 via a peer connection but not to Coupling Facility 1.

In addition to the above the coupling facilities that are coupled may be in separate Central Processing Complexes CPC in separate partitions of one CPC or a combination thereof. In the situation that the facilities are in separate partitions of one CPC the same links can be used for both duplexing and command traffic.

In a further embodiment multiple peer links can be configured as redundant connections. In this scenario the process for sending duplexing signals on the peer links described herein recognizes a link failure and maintains signal exchanges on surviving links.

Two instances of the coupling facility structure are maintained in separate coupling facilities referred to as the primary coupling facility and the secondary coupling facility. In addition a locking structure owned and managed by LFSS is maintained in the primary coupling facility.

One embodiment of the steps in a normal command execution for the explicit locking alternative are shown in in numeric sequence that approximate the time sequence of the command. Each of these steps is described below.

Step 1. The user application generates a command and communicates this command to the LFSS through the system macro interface.

Step 2. A lock and record command is generated by LFSS and sent to the locking structure in the primary coupling facility. A link subsystem LSS component in the primary coupling facility receives the command and transfers control to the list component which controls the locking function. Information recorded in the locking structure includes the MCB for the user command. The lock set by the command serializes access by other commands to the primary structure. A modification would allow for a partitioning of the structure and the lock to cover the partition of the structure impacted by the user command. 

Step 3. The lock and record command is executed by the primary coupling facility and the MRB is returned to the LFSS. In this path the lock is successfully obtained by the LFSS.

Step 4. The LFSS creates two copies of the command sending one to the primary coupling facility and the second to the secondary coupling facility. The LFSS uses the asynchronous SEND MESSAGE interface without notification to allow the two commands to be initiated in parallel. The protection provided by the lock in the locking structure enables the two commands to be executed independently in the two coupling facilities. Parallel execution is preferred to minimize the elapsed time for executing the commands. The link subsystem LSS component in the primary coupling facility receives the command and transfers control to the cache or list component as appropriate. Likewise the link subsystem LSS component in the secondary coupling facility receives the command and transfers control to the cache or list component as appropriate.

Step 5. Each coupling facility independently executes its copy of the user command and returns the result in the MRB. The two MRBs returned are identical. Any differences that cannot be corrected by retrying the commands result in loss of duplexing mode. 

Step 6. The MRB is returned to the user application. From the user s perspective the command has been completed.

Step 7. The LFSS generates an unlock and clear command to the locking structure to free the lock and delete the recorded information.

Step 8. The primary coupling facility executes the locking command and returns the MRB indicating success.

This ends the normal path for this alternative duplexing design. However in step 3 the lock may already be held when the locking command is executed. In this case the lock operation fails with a non zero response code and the record operation is suppressed. The following sequence of steps occurs beginning at step 3.

Step 3 . The locking command is executed unsuccessfully by the primary coupling facility. The lock is already held by another system. In this case the record operation is not performed and a response code is generated that indicates lock held . The MRB containing this response is returned to the LFSS.

Step 5 . The primary coupling facility executes the locking command either successfully or unsuccessfully. The result is returned in the MRB with a response code. If execution is successful the processing resumes at step 4 above. If execution is unsuccessful the locking command is reissued at step 4 . This continues for a model dependent time period by the LFSS after which duplexing is broken.

User transparency is satisfied because the locking and duplexing functions are performed by the LFSS without awareness by the user application.

Failure isolation is satisfied by creating two copies of the structure in separate facilities each of which can continue as the surviving structure in a situation involving the failure of the other. The locking structure is only used for duplexing purposes and so it can be discarded by the recovery program performing structure fail over.

Command atomicity is satisfied because all accesses to the primary and secondary structures are serialized by the explicit lock operation.

One shortcoming of this approach is the performance cost of the additional lock and unlock commands. These are not overlapped with the mainline commands. In addition to this shortcoming there are several other performance concerns. First there is a significant additional load placed on the links to the coupling facility containing the lock structure due to the generation of a pair of lock and record and unlock and clear commands for each user generated command. Also the explicit serialization introduced at the structure level or at a partition of the structure introduces new contention that will block command execution. The current design of using internal latching in the coupling facility which optimizes concurrent execution is defeated by this approach.

One embodiment of the steps in a normal command execution for the store and forward alternative are shown in in numeric sequence that approximates the time sequence of the command.

Step 1. The user application generates a command and communicates this command to the LFSS through the system macro interface.

Step 2. The LFSS issues the command to the primary coupling facility. A link subsystem LSS component in the primary coupling facility receives the command and transfers control to the cache or list component as appropriate.

Step 3. The cache list component of the primary coupling facility executes the command to the point where the MRB would be returned to the application. However before sending the MRB and while internal latches are held for the objects referenced by the command a request is made to a command forwarding subsystem to forward the user command to the secondary coupling facility.

Step 4. The command forwarding subsystem in the primary coupling facility issues a standard SEND MESSAGE instruction to send the command on the ISC link connected to the secondary coupling facility and waits on the MRB.

Step 5. The command forwarding component in the secondary coupling facility receives the command from the primary facility and transfers control to the cache or list component as appropriate.

Step 6. The cache list component of the secondary coupling facility executes the command against the secondary structure and hands the MRB to the command forwarding component.

Step 7. The command forwarding component in the secondary coupling facility sends the MRB to the command forwarding component in the primary coupling facility. Command execution is complete in the secondary coupling facility.

Step 8. The command forwarding component in the primary coupling facility receives the MRB from the secondary coupling facility and transfers control to the cache list component.

Step 9. The cache list component determines the command execution in the secondary coupling facility is successful and returns the primary MRB to the LFSS.

User transparency is satisfied because the duplexing functions are performed by the coupling facilities without awareness by the user application.

Failure isolation is satisfied by creating two copies of the structure in separate facilities each of which can continue as the surviving structure in a situation involving the failure of the other.

Command atomicity is satisfied because accesses to the primary structure are serialized while the command is forwarded to the secondary coupling facility.

There are shortcomings with this model however. For instance commands to the secondary structure are to pass over the peer ISC link including the data transfers. This creates a funneling effect between the set of primary ISC links connected to the primary coupling facility from the systems in the Sysplex to the single peer ISC link which creates a bottleneck in the system design. To overcome this multiple links are to be established as peer ISC links to handle this combined traffic. This raises the expense of the configuration and reduces the connectivity of the coupling facilities to systems. Another problem is that the primary and secondary commands execute serially with little opportunity for overlapping either command execution or data transfer. A third problem is that the peer ISC link is to be fully functional including data transfers and timeouts. The peer ISC link for the coupling facility to coupling facility model only transfers simple message exchanges during the configuration phase and only transfers secondary commands during command processing. This significantly lowers the complexity of the link support in the CFCC compared to the full function support needed in the store and forward model.

A coupling facility is attached to a second coupling facility when a coupling facility link exists from the first facility to the second facility and the second facility is in the managed state. In this case we say that the second coupling facility is remotely attached to the first coupling facility. A coupling facility may have any number of remotely attached coupling facilities and may have multiple coupling facility links to the same coupling facility.

The attachment to a remote facility is active when at least one message path to the remote facility is placed in the active state by an Activate Message Path AMP command described hereinafter . In one example attachments are not activated unless the coupling facility is in the managed state and a signaling vector is defined.

Two coupling facilities are connected if each coupling facility is remotely attached to the other by active attachments.

Connected coupling facilities can be used to support many functions including for instance the duplexing of structures. The coupling facility links that enable the connection are used to transport signals to remote signaling vectors described hereinafter in the attached facilities. The program e.g. LFSS issues commands to the coupling facilities containing the two structures and a sequence of signals are exchanged between the two coupling facilities as part of command execution. The sequence of signals referred to as the signaling protocol is used to coordinate the updates to the structure objects so that the pair of structures can be synchronized. The signaling protocol extends the command atomicity rules across the pair of structures ensuring that updates to the set of objects referenced by the command are either applied or suppressed as a single atomic operation in both coupling facilities.

A pair of structures that is synchronized across a coupling facility connection is called a duplexed pair of structures and each of the two structures is in the duplexing active state. An error condition or configuration action may cause the duplexing state to be broken. When duplexing is broken one of the two structures is chosen to continue to support command execution against the objects in the structure. The surviving structure is said to be executing in the simplex state. The other structure no longer accepts commands and is deallocated by the program. If a copy of the structure running in simplex state is created on a connected coupling facility the duplexing state can be reestablished between the active structure and the copied structure.

In addition the coupling facilities are attached to each other but they are not fully interconnected. Coupling Facility x is attached to Coupling Facility z by sender ISC Channel 2 but Coupling Facility x is not attached to Coupling Facility y in this example. This is reflected in the coupling facility x configuration table which shows a single active A attachment for sender ISC 2 to Coupling Facility z. Likewise Coupling Facility y is attached to Coupling Facility z by sender ISC 7. Coupling Facility z is attached to Coupling Facility y but not to Coupling Facility x. In fact Coupling Facility z has two attachments to Coupling Facility y sender ISC 3 and 6. However while sender ISC 3 is an active attachment the attachment via sender ISC 6 has not yet been activated I .

This collection of attachments generates one pair of connected coupling facilities. Namely the pair of ISC links represented by sender ISC 7 in Coupling Facility y and sender ISC 3 in Coupling Facility z are active attachments in each direction and therefore form a peer ISC link between Coupling Facility y and Coupling Facility z. Therefore Coupling Facility y and Coupling Facility z are connected coupling facilities. No such connection exists between Coupling Facility x and Coupling Facility y or between Coupling Facility x and Coupling Facility z. So a structure is duplexed by placing one structure in Coupling Facility y and the other structure in Coupling Facility z.

A program running on System A can allocate a duplexed pair of structures one in Coupling Facility y and one in Coupling Facility z. If at some point in time Coupling Facility y fails or one of the ISC links in the peer ISC link attaching Coupling Facility z to Coupling Facility y fails the duplexing active state can be broken by the program and the surviving structure on one of Coupling Facility y or Coupling Facility z can be selected and accessed as a single structure and the structure executes in a simplex state. The change from duplex state to simplex state is done without loss of data and with minimal recovery time required for switching states. Assuming the surviving structure is on Coupling Facility z and later a second copy of the structure is created on Coupling Facility y the structure can reenter the duplexed state. If in the interim an ISC link is established from Coupling Facility z to Coupling Facility x and attachments in both directions are activated the second copy of the structure could be placed on Coupling Facility x and the signaling protocol would flow between Coupling Facility z and Coupling Facility x. Likewise if Coupling Facility z or it s corresponding ISC link fails then the structure in Coupling Facility y is the surviving structure and is accessed in simplex mode. In this case however the lack of a signaling channel between Coupling Facility x and Coupling Facility y prevents reentering the duplexed state until Coupling Facility z is repaired or until ISC links are configured between Coupling Facility x and Coupling Facility y in both directions.

The coupling facility configuration tables reflect the states of each of the ISC links associated with the sender ISC channels. A similar table exists for the receiver ISC channel called the Message Path Status Vector MPSV . This is an architected table in the coupling facility that is extended for duplexing connections. The MPSV and its extensions are described in the next section. The CFCC determines the collection of connected coupling facilities from information in both the configuration table and the MPSV. A source node descriptor in the MPSV is the information that links the sender and receiver ISC channels.

In general several processors issue coupling facility commands and several links may connect each processor to the coupling facility. The coupling facility assigns message path identifiers that distinguish among the different sources of commands. Further associated with a message path are various objects which are used to for instance define the path provide status etc.

Examples of message path objects are summarized in the following table and described below. There may be more less or different message path objects.

Image Identification Code IID A value that specifies the image associated with the message path. The object is initialized to zero and is set to the value of the IID field in the message header when an Activate Message Path command described hereinafter is processed.

Message Path Identifier MPID A value that is used to identify a message path at the coupling facility. There is a unique message path identifier for each source of direct or intermediate commands. The values of the message path identifiers are set by an installation procedure. They are not modified by any command.

Message Path Request Level MPRL A value associated with each message path that indicates the maximum number of commands that may be processed concurrently for the message path. The value is initialized when the message path becomes operational and remains unchanged while the path is in the operational state.

Message Path State MPS A value that specifies the state of the message path. A value of X 00 indicates the path is in the inactive state and a value of X 01 indicates the path is in the active state.

Source Node Descriptor SRCND An optional value that is designated by the program when the message path is activated which contains the node descriptor object of the message path source. When a message path is activated and a source node descriptor is not provided the source node descriptor object is in the empty state.

Path Group The set of message paths with the same system identifier SYID value for message paths that do not have source node descriptors. For the message paths that have source node descriptors the path group includes the set of message paths with the same system identifier value and source node descriptor value.

Message Path Status Vector A message path status vector object includes state information for each message path in the coupling facility. The message path status vector includes for instance the following objects for each message path 

One example of a message path status vector is depicted in . As shown the fields include for instance MPS MPRL SYID and the IID field. It also includes a column for the source node descriptor which is a field used for duplexing. The field is set by an Activate Message Path command under control of the SRCNDC operand. See the section on message path operands and message path commands below. The source node descriptor field is marked as empty for message paths originating within an operating system partition and is set to the value of the node descriptor object for paths originating in remote coupling facilities. The source node descriptor object is used by the CFCC to match coupling facility receiver chpids CFR and coupling facility sender chpids CFS . Activating a message path to a remote coupling facility indicates that the remote coupling facility is attached. If there is also an active message path in the MPSV for the same remote coupling facility i.e. the source node descriptor is equal to the remote coupling facility node descriptor then the two coupling facilities are connected.

In addition to message path objects global objects resident within the coupling facility are used to identify the coupling facility describe its state define its model dependent limitations and summarize the status of its resources. Global objects include for instance fixed global controls which are set at coupling facility power on reset and are not modified by any command or coupling facility process and program modifiable global controls which are initialized at coupling facility power on reset and may be modified by subsequent commands or coupling facility processes. Although various global objects are described below more less or different objects may exist.

One embodiment of a fixed global control used for duplexing is summarized in the following table and described below.

Signaling Vector Token SVT A value that identifies the signaling vector. When the signaling vector token is zero a signaling vector is not provided in the coupling facility.

Likewise examples of program modifiable global controls are summarized in the following table and described below.

Authority AU A program designated coupling facility state value. When the value is non zero the coupling facility commands are executed normally. When the value is zero the execution of certain coupling facility commands is suppressed. The authority value is initialized to zeros. The authority contains a sub object called the system identifier SYID .

Channel Connection Controls One set of channel connection controls exists for a coupling facility. Examples of channel connection controls are summarized in the following table and described below.

Count of Installed and Not Operational Intersystem Channels CINOPC A value that includes the number of channel path identifiers assigned to intersystem channels that are installed in the coupling facility and are in the not operational state. The value of the count of installed and not operational intersystem channels is for instance between zero and sixty four.

Installed and Not Operational Channel Path Descriptors INOPCP An ordered collection of values that include the channel path identifier CHPID values that are installed in the coupling facility and are not operational. The number of installed and not operational channel path descriptors is included in the CINOPC control. The installed and not operational channel paths are ordered by type and by value. The sender channel paths are listed first followed by the receiver channel paths. Within each type the channel path identifiers are ordered from lowest to highest. When the number of installed and not operational channel paths exceeds 64 then the list is truncated and the first 64 channel path identifiers are returned.

Duplexing Vector DV A bit string with an initial value of zero. The bit positions start at 0 and increase sequentially to the SID limit. The bit at position i in the string is set to one when a structure is made duplexing active with a SID value of i . The bit at position i is reset to zero when duplexing is broken by the CFCC or explicitly deactivated by the OS or the structure is deallocated. All bits in the duplexing vector are reset to zero when the authority object is changed by a Set Facility Authority command and a preserve duplexing indicator described hereinafter is zero or when a coupling facility power on reset occurs. A bit in the duplexing vector is referred to as the duplexing active bit for the associated structure.

In one aspect the obtaining of this vector includes but is not limited to defining the vector receiving the vector or otherwise being provided the vector.

Remote Facilities Table RFT Information that is returned as a result of a Read Connected Facility Controls command described hereinafter .

Remote Facilities Access Counter RFAC A value that is incremented whenever a remote coupling facility s accessibility level changes either from not connected to connected or from connected to not connected. The value is set to zero when a coupling facility power on reset occurs.

One or more remote coupling facilities may be accessible by message paths between the facilities. There are two possible levels of accessibility to a remote facility 

The remote facility is connected when at least one message path to the remote facility is in the active state and at least one message path from the remote facility is in the active state as recorded in the message path status vector. Otherwise the remote facility is not connected.

The remote facility controls are created when an Identify Message Path command described hereinafter completes and the node descriptor and system identifier that are returned do not match any existing remote facilities.

Remote Facility Accessibility Level RFAL A value that describes the current level of accessibility to the remote coupling facility. It has the following encoding 

Remote Facility Channel Path Identifiers RFCHP An ordered collection of values that include the channel path identifier CHPID values assigned to the message paths in the remote facility path group. There is a remote facility channel path identifier for each active message path in the path group and therefore the number of remote facility channel path identifiers is equal to the remote facility path group size RFPGS . The ordering of the remote facility channel path identifiers matches the ordering of the remote facility path descriptors i.e. the ith remote facility path descriptor includes the value of the descriptor field returned by the store channel path descriptor command of the Channel Subsystem Call CHSC instruction when the ith remote facility channel is specified as the input operand.

Remote Facility Controls Time of Creation RFCTOC A time of day TOD value indicating the time when the remote facility controls are created.

Remote Facility Disconnect Time RFDT A value that includes the elapsed time that has occurred since the remote facility changed from connected to not connected. The format of the remote facility disconnect time matches the S 390 time of day clock. For example bit corresponds to 1 millisecond.

Remote Facility Disconnect Time Validity Indicator RFDTVI A value that determines the validity of the remote facility disconnect time object. It has the following encoding 

Remote Facility Node Descriptor RFND A value that includes the node descriptor object of the remote coupling facility.

Remote Facility Path Descriptors RFPD A collection of values that define the channel path types for the channel paths in the path group associated with the remote facility. There is a remote facility path descriptor for each active message path in the path group and thereby the number of remote facility path descriptors is equal to the remote facility path group size RFPGS .

Remote Facility Path Group Size RFPGS A value that includes the number of active message paths in the path group associated with the remote facility. The value of the remote facility path group size is between zero and eight as one example.

Remote Facility Sender Channel Path Identifiers RFSCHP An ordered collection of values that include the channel path identifier CHPID values of the sender intersystem channels that are connected to the remote facility. A sender intersystem channel is connected to a remote facility when the channel is operational and an Identify Message Path command issued on the channel path returns the node descriptor object associated with the remote facility. There is a remote facility sender channel path for each connected sender intersystem channel and therefore the number of remote facility sender channel path identifiers is equal to the remote facility sender path group size RFSPGS . The ordering of the remote facility sender channel path identifiers matches the ordering of the remote facility sender path descriptors i.e. the ith remote facility path descriptor contains the value of the descriptor field returned by the store channel path description CHSC command when the ith remote facility sender channel path identifier is specified as the input operand.

Remote Facility Sender Path Descriptors RFSPD An ordered collection of values that define the channel path types for the sender intersystem channels that are connected to the remote facility. There is a remote facility sender path descriptor for each sender intersystem channel that is connected to the remote facility and thus the number of remote facility sender path descriptors is equal to the remote facility sender path group size RFSPGS . The value of the remote facility sender path descriptor is set to the value of the descriptor field DESC for the associated channel path type returned by the store channel path description CHSC command.

Remote Facility Sender Path Group Size RFSPGS A value that includes the number of sender intersystem channel that are operational and connected to the remote facility. The value of the remote facility sender path group size is between for instance zero and eight.

Remote Facility Signaling Vector Token RFSVT A value used to identify the signaling vector in the remote coupling facility.

Remote Facility System Identifier RFSYID A value that is designated by the program when the remote coupling facility is placed in the managed state.

Remote Facility Signal Counters A set of remote facility signal counters is associated with each remote facility. The signal counters are initialized to zero when the remote facility controls are created. The signal counters are defined as substantially accurate.

Examples of remote facility signal counters are summarized in the following table and described below.

Delayed Signal Counter DSC A value that indicates the number of signals delayed in being sent to the remote facility.

Halt Execution Signal Counter HESC A value that indicates the number of halt execution signals sent to the remote facility.

Ready to Complete Signal Counter RTCSC A value that indicates the number of ready to complete signals sent to the remote facility.

Ready to Execute Signal Counter RTXSC A value that indicates the number of ready to execute signals sent to the remote facility.

Request for Suppression Signal Counter RFSSC A value that indicates the number of request for suppression signals sent to the remote facility.

Request for Suppression Accepted Signal Counter RFSASC A value that indicates the number of request for suppression accepted signals sent to the remote facility.

Signal Delay Time First Moment SDTFM A value that includes the accumulated delay time in for instance microseconds for signals delayed in being sent to the remote facility.

Signal Delay Time Second Moment SDTSM A value that includes the accumulated squares of delay time in squared microsecond units for signals delayed in being sent to the remote facility.

Signal Redrives Signal Counter SRDSC A value that indicates the total number of redrives of signals to the remote facility.

Signal Service Time First Moment SSTFM A value that includes the accumulated service time excluding delay time in microseconds for signals sent to the remote facility.

Signal Service Time Second Moment SSTSM A value that contains the accumulated squares of service time excluding delay time in squared microsecond units for signals sent to the remote facility.

Referring back to the program modifiable global controls table above additional controls exist which are described below.

Retry Vector A vector that includes retry index RX values for the retry buffers of a coupling facility.

SID Vector A vector that includes structure identifier SID values for the structures of a coupling facility.

Signal Group SGP A collection of signal values associated with the execution of a command or a portion of a command. Each signal group includes for instance the following signals 

When a signal is received for a signal group the signal is set to one and remains in this state until the signal group is reset. When the signal group is reset each signal is set to zero.

Command Sequence Number CSN A number associated with a currently executing duplexed command. The initial value is zero.

Current Signal Group Index CSGX A value that identifies the currently active signal group in a signaling vector entry described below . The initial value is B 01 as one example.

Signaling Vector SGNLV The signaling vector object includes a linear array of signaling vector entries where each entry includes signaling controls and a plurality of e.g. three signal groups as depicted in . Each entry is associated with a retry index RX which is the index into the signaling vector and each entry includes two signaling controls the command sequence number and the current signal group index and three signal groups . The reset and initial state of a signaling vector entry are the same. When an entry is reset the command sequence number is set to zero the current signal group index is set to one and each signal group is reset. After coupling facility initialization is complete or after the authority object is changed by for instance a Set Facility Authority command described hereinafter and the preserve duplexing indicator is zero each signaling vector entry is in the reset state.

In one example the signaling vector is to be large enough to map each retry buffer available in the coupling facility. If a vector of sufficient size cannot be created then no signaling vector is established and no remote facility connections are made.

This completes a description of one embodiment of various global objects. One or more global objects are used in one example along with one or more message path objects to define a configuration. One such configuration is described in .

As depicted in a configuration includes two coupling facilities coupled to a single system running the z OS operating system. In this configuration the z OS image has two sender channels CFS 2 and CFS 3. CFS 2 is connected to receiver channel CFR 5 on CF 1 and CFS 3 is connected to receiver channel CFR 6 on CF 2. In this implementation the MPID is set equal to the chpid number for the receiver chpid. In CF 1 the message path originating in the z OS image is reflected in row 5 of the MPSV . The state of the message path is active A the MPRL is 2 the system id SYID is the system id for z OS the image id is the partition number of the z OS image and the source node descriptor is empty. The entry in the MPSV in CF 2 for the message path originating in CFS 3 is similar.

There are two additional message paths defined between the two coupling facilities. The first originates in CF 1 in CFS 11 and is connected to CFR 9 in CF 2. Row 9 in the MPSV in CF 2 reflects the state of this message path. The path is active which shows that CF 1 is attached to CF 2. The MPRL is 2 the system identifier is set to the value of the high order doubleword of the authority in CF 1 the IID is set to the partition number for the logical partition that is running CF 1 and the source node descriptor is set to the node descriptor for the system containing CF 1. These fields are all established by the AMP command issued by CF 1 to CF 2 over CFS 11.

A similar set of fields is set in the MPSV on CF 1 for the message path originating in CFS 10 on CF 2 and connected to CFR 8 on CF 1. The two coupling facilities are in the connected state and are eligible to contain a duplexed pair of structures. Duplexing signals sent from CF 1 to CF 2 use the secondary message buffers on CFR 8 via list notification commands. Likewise CF 2 sends duplexing signals to CF 1 using the secondary message buffers on CFR 9. The MPRL value of 2 indicates that two duplexing signals may be sent in parallel in each direction. The CFCC monitors the state of the connection to allow duplexing to be maintained by monitoring the state of both the CFR link and the CFS link. In the case of CF 1 that means both CFR 8 and CFS 11 are to be operational and active. Likewise CF 2 monitors CFR 9 and CFS 10.

Other objects are also employed to support coupling facility processing. These objects include for instance retry buffer objects which are described below.

A retry buffer is an area of coupling facility storage that includes information relevant to command recovery. The retry buffers are assigned by the LFSS component of z OS when a coupling facility is initially connected. The LFSS assigns a retry index within the range of retry indexes assigned to that system to a message subchannel that contains a sender ISC channel which is connected to the coupling facility. The retry index identifies a unique collection of objects in the coupling facility that constitute the retry buffer. These include for instance the retry authority the retry information the retry data block and a signaling vector entry.

As depicted in a retry buffer includes a retry information portion which is assigned from an area of coupling facility storage that is not available for structure allocation and a retry data block portion which is assigned from the structure storage area associated with the retry data.

Each command that uses a retry buffer specifies a retry index RX as a request operand. The coupling facility places the retry data into the specified retry buffer as part of command execution. The retry information is returned in the message response block and the retry data block is returned to the location specified by the data block address in the message command block.

When the size of the data stored in the retry data block is less than the maximum data size the data is left justified in the retry data block. The length of the retry data is placed in the data count field of the response header.

Examples of retry buffer objects are summarized in the following table and described below with reference to .

Command Recovery Information An area that includes command specific recovery information used for command retry.

Previous Response Code PRC The resulting response code for the last command to execute with the specified retry index. The object contains zeros when the retry index is assigned but not in use.

Previous Status Conditions PSC The resulting status conditions for the last command to execute with the specified retry index when the previous response code is a preferred value e.g. 254 or 255 . Otherwise the object contains zeros.

Previous Duplexing Deactivated Indicator PDDI The resulting duplexing deactivated indicator for the last command to execute with the specified retry index. The object is zero when the retry index is assigned but not in use.

Retry Version Number RVN A value provided by the program and stored in the retry buffer as part of the retry data. The retry version number indicates command execution status. When the retry version number matches the value in the message command block the command has completed and the completion status is indicated by the values of the PRC and PSC fields. The retry version number is initialized to the value X 00 in one example when the retry buffer is placed in the assigned but not in use state.

Retry Buffer Authority RBAU A value set by the program when a retry buffer is assigned. The initial value of the retry buffer authority is zero. In this example RBAU is a separate component of the Retry Buffer.

In addition to global objects and retry objects various objects are associated with individual types of structures of the coupling facility such as for instance cache and list structures. Various of these objects are described below. Again more less or different objects may exist.

Examples of cache structure objects located within a cache structure that are associated with duplexing include for instance 

Duplexing State DPLXST A value that indicates the duplexing state for the cache structure. It has the following encoding 

The duplexing state is set to the simplex state or the duplexing active state in correspondence with the duplexing vector bit located at the offset in the duplexing vector equal to the value of the structure identifier SID . The structure is in the simplex state when the duplexing vector bit is zero and the structure is in the duplexing active state when the duplexing vector bit is one.

Remote Facility Node Descriptor RFND A value that includes the node descriptor object of the remote coupling facility that has the duplexed copy of the cache structure. The remote facility node descriptor is set when duplexing is activated and may be updated while duplexing is active by an Activate Duplexing command described hereinafter . The initial state is zero.

Remote Facility Structure Authority RFSAU A value that includes the structure authority of the duplexed copy of the cache structure. The remote facility structure authority is set when duplexing is activated and may be updated while duplexing is active by the Activate Duplexing command. The initial state is zero.

Remote Facility Structure Identifier RFSID A value that includes the structure identifier of the duplexed copy of the cache structure. The remote facility structure identifier is set when duplexing is activated and may be updated while duplexing is active by the Activate Duplexing command. The initial state is zero.

Remote Facility System Identifier RFSYID A value that includes the system identifier of the remote coupling facility that has the duplexed copy of the cache structure. The remote facility system identifier is set when duplexing is activated and may be updated while duplexing is active by the Activate Duplexing command. The initial state is zero.

Examples of list structure objects located within a list structure that are associated with duplexing include for instance 

Duplexing State DPLXST A value the indicates the duplexing state for the list structure. It has the following encoding 

The duplexing state is set to the simplex state or the duplexing active state in correspondence with the duplexing vector bit located at the offset in the duplexing vector equal to the value of the structure identifier SID . The structure is in the simplex state when the duplexing vector bit is zero and the structure is in the duplexing active state when the duplexing vector bit is one.

Remote Facility Node Descriptor RFND A value that includes the node descriptor object of the remote coupling facility that has the duplexed copy of the list structure. The remote facility node descriptor is set when duplexing is activated and may be updated while duplexing is active by the Activate Duplexing command. The initial state is zero.

Remote Facility Structure Authority RFSAU A value that includes the structure authority of the duplexed copy of the list structure. The remote facility structure authority is set when duplexing is activated and may be updated while duplexing is active by the Activate Duplexing command. The initial state is zero.

Remote Facility Structure Identifier RFSID A value that includes the structure identifier of the duplexed copy of the list structure. The remote facility structure identifier is set when duplexing is activated and may be updated while duplexing is active by the Activate Duplexing command. The initial state is zero.

Remote Facility System Identifier RFSYID A value that includes the system identifier of the remote coupling facility that has the duplexed copy of the list structure. The remote facility system identifier is set when duplexing is activated and may be updated while duplexing is active by the Activate Duplexing command. The initial state is zero.

Messages are communicated between a system such as system and one or more coupling facilities via a message command response block. In one example a message command response block has a message command block which includes a command block and a plurality of request operands a message response block which includes a response descriptor and a plurality of response operands and an optional data block.

The message command response blocks are employed by commands used for messaging. Examples of such commands include an Activate Message Path AMP command and an Identify Message Path IMP command which are described below. The commands are issued by an operating system and executed by a coupling facility.

One example of the request operands provided in the message command block for the AMP command are summarized in the following table.

In the above table a source node descriptor control is listed. Since this operand has been added for duplexing it is described below.

Source Node Descriptor Control SRCNDC A value that controls the setting of the contents of the source node descriptor object in the message path status vector for the message path designated by the Activate Message Path command. It has the following encoding 

In execution of one embodiment of the Activate Message Path command the node descriptor operand is compared to the node descriptor object and the designated message path is compared to the message path used for communication. If both are the same the message path enters the active state the system identifier is placed in the message path status vector the source node descriptor is placed in the SRCND object when the SRCNDC operand is B 1 the SRCND object is placed in the empty state when the SRCNDC operand is B 0 the message path request level is placed in the MPRL operand and response code 0 is stored in the response code operand. Otherwise the message path state is not changed and response code 1 is stored.

One example of the request operands provided in the message command block for the IMP command are summarized in the following table and described herein.

In execution of one embodiment of the Identify Message Path the node descriptor for the coupling facility is stored in the ND operand the identifier of the message path used for communication is stored in the MPID operand the message path state is placed in the MPS operand the message path request level is stored in the MPRL operand the system identifier is moved from the authority object to the SYID operand the signaling vector token is stored in the SVT operand the contents are placed in the SRCND operand when the source node descriptor object is not empty and zeros are stored in the SRCND operand when the source node descriptor object is empty.

The response operands provided in the message response block for the IMP command are summarized in the following table.

In addition to the messaging commands described above there are other types of commands that are employed for processing associated with coupling facilities. One type of commands is global commands for duplexing which are used to control the duplexing of coupling facility structures e.g. activate duplexing deactivate duplexing etc. . These commands are described below but before describing the commands various global operands are described which are employed by the duplexing commands as well as other coupling facility commands.

Examples of global operands used as request response operands for commands associated with coupling facility processing are described below 

Comparative Structure Authority CSAU A value that is compared with the value of the structure authority control.

Comparative Remote Facility Structure Authority CRFSAU A value that is compared with the value of the remote facility structure authority control.

Connection Operation Request Type COPRT A value that determines the type of connection operation that is requested on a Probe Remote Facility Connection PRFC command described hereinafter . It has the following encoding 

Data Block Size DBS A value that specifies the size of the data block as an integral multiple of for instance 4096 byte units. Valid values range from 1 to 16 in this example.

Preserve Duplexing Indicator PDI A value that indicates whether the duplexing vector and the signaling vector should be preserved when a Set Facility Authority command updates the authority control. It has the following encoding 

Read CFIB Type RCFIBT A value that determines the type of coupling facility information block returned by a Read Connected Facility Controls RCFC command described hereinafter . It has the following encoding 

Remote Facility Node Descriptor RFND A value that includes the node descriptor object of the remote coupling facility that has the duplexed copy of the structure. The remote facility node descriptor is to be different from the local node descriptor object.

Remote Facility Structure Authority RFSAU A value that includes the structure authority of the duplexed copy of the structure.

Remote Facility Structure Identifier RFSID A value that includes the structure identifier of the duplexed copy of the structure.

Remote Facility System Identifier RFSYID A value that includes the system identifier of the remote coupling facility that has the duplexed copy of the structure.

Examples of duplexing commands include an Activate Duplexing Command a Deactivate Duplexing Command a Probe Remote Facility Connection command a Read Connected Facility Controls command a Read Duplexing Vector command a Test Remote Facility Access command and a Set Retry Buffer Authority command each of which is issued by an operating system and executed by a coupling facility and described below.

One embodiment of various request operands provided in the message command block for the ADPLX command are summarized in the following table and described herein.

Moreover one embodiment of the logic associated with the ADPLX command is described below with reference to .

Initially a determination is made as to whether the structure type permits duplexing INQUIRY . For instance if the structure is a list structure that includes a list set and a Programmable List Entry Identifier PLEIDI control is B 0 the structure type does not permit duplexing to be activated. In this case the command is completed without updating any objects and a response code e.g. 3 is returned STEP .

When the structure type permits duplexing to be activated the structure authority is compared with the CSAU operand STEP . If the comparison succeeds INQUIRY the remote facility node descriptor the remote facility structure authority the remote facility structure identifier and the remote facility system identifier request operands are placed in the structure controls STEP and the accessibility of the remote facility is determined INQUIRY .

If the structure authority comparison succeeds and the designated remote facility is connected the duplexing active bit in the duplexing vector is set to one STEP and a response code e.g. 0 is returned STEP .

If the structure authority comparison succeeds but the designated remote facility is not connected INQUIRY then the duplexing active bit in the duplexing vector is not updated and a response code e.g. 1 is returned STEP .

If the structure authority is not equal to the CSAU operand INQUIRY then the command is completed without updating any objects. The value of the structure authority and a response code e.g. 2 are returned STEP .

The extension of the command atomicity rules to a duplexed command pair is accomplished by the implementation of latches on structure objects or internal control structures. Latches are obtained and held in both structures until the ready to complete signal is exchanged. Reception of a ready to complete signal confirms that latches have been obtained in the remote facility. However if the structure is a list structure that has a list set but where LEIDs are internally generated PLEIDI B 0 then it may be possible to violate the command atomicity rules as the following example demonstrates.

Suppose that a duplexed pair of list structures located on coupling facilities CF0 and CF1 with internally generated LEIDs concurrently process a Write List Entry WLE command pair with an unconditional create request and a Delete List Entry DLE command pair with a request to locate by LEID. Further suppose that the DLE command specifies an LEID value of X that is identical to the internally generated LEID for the WLE command. Finally assume the commands are processed out of order by the two facilities where the WLE command is processed first by CF0 and the DLE command is processed first by CF1.

The WLE command succeeds in processing the create request generates a list entry with LEID X issues a ready to complete signal and maintains the latch on the list entry until a read to complete signal is received from the duplexed WLE command. The DLE command is delayed by the latch in CF0.

The DLE command executes in CF1 and does not find a list entry with the specified LEID. The DLE command completes with a RC 8 condition issues a ready to complete signal and waits until a ready to complete signal is received from the duplexed DLE command. No latches are held and the WLE command is free to execute.

The WLE command on CF1 succeeds in processing the create request generates a list entry with LEID X and issues a ready to complete signal. Both WLE commands recognize the reception of a ready to complete signal and both complete with RC 0 and the latches on the list entry are released in both structures.

The DLE command in CF0 is now free to execute finds the newly created list entry with LEID X deletes the entry and sends a ready to complete signal. Both DLE commands recognize the reception of a ready to complete signal and complete processing. However the DLE command from CF0 returns a RC 0 condition and the DLE command from CF1 returns an RC 8 condition entry not found. More importantly the list structures are no longer synchronized a list entry with LEID X exists in CF1 but not in CF0.

This problem is avoided if PLEIDs are used the PLEID collision list in the list structure controls provides the required object for serialization.

One solution to this problem is to disallow duplexing to be activated for structures of this type. In this case the Activate Duplexing command ends with a response code e.g. 3 condition. For list structures with list sets assignment of LEIDs are to be under the control of the operating system and the PLEIDI control is to be b 1 in the list structure type 

One embodiment of the request operands provided in the message command block for a DDPLX command are summarized in the following table and described herein.

Initially the CSAU operand is compared with the structure authority object and the CRFSAU operand is compared with the remote facility structure authority object STEP . If both comparisons are successful INQUIRY the duplexing active bit specified by the SID operand is set to zero STEP and a response code e.g. 0 is returned STEP . The remote facility node descriptor the remote facility system identifier the remote facility structure identifier and the remote facility structure authority objects are not updated.

If the structure authority is not equal to the CSAU operand or if the remote facility structure authority is not equal to the CRFSAU operand INQUIRY then the structure authority and remote facility structure authority are placed in the MRB STEP . The MRB and a response code e.g. 2 are returned STEP .

One embodiment of the request operands provided in the message command block for the PRFC command are summarized in the following table and described herein.

Further one embodiment of the logic associated with the PRFC command is described with reference to .

An operation is performed for the specified remote facility connection and the results of the operation are returned in the response block.

The operation that is performed depends on the connection operation request type. When the COPRT operand is zero INQUIRY the remote facility attachment is verified STEP as follows 

When the COPRT operand is one INQUIRY the remote facility connection is dropped STEP by initiating a coupling facility link initialization operation for each coupling facility link with an available sender CHPID at the local coupling facility and an available receiver CHPID at the remote coupling facility. In one example this step is performed by a channel subsystem. Model dependent means are used to initiate the coupling facility link initialization procedure. When the coupling facility link initializations have been successfully initiated the command completes and a response code e.g. 0 is returned. After the link initialization operations have completed the remote facility connection may be reestablished at any time.

One embodiment of various request operands provided in the message command block for the RCFC command are summarized in the following table and described herein.

In execution of one embodiment of the RCFC command when sufficient message buffer space is provided a connected facility information block CFIB is added to the data block and the processed count is increased by one for each connected coupling facility.

When the RCFIBT operand is for instance B 0 a 128 byte CFIB including the remote facility controls is stored in the data block. One example of a CFIB when the RCFIBT is B 0 is as follows 

When the RCFIBT operand is for instance B 1 a 256 byte CFIB including the remote facility controls and signal counters is stored in the data block. One example of the CFIB when the RCFIBT is B 1 is as follows 

When all connected coupling facility controls have been placed in a CFIB list the CFIB list the processed count and a response code e.g. 0 are returned to the program.

When the data block is full and additional connected facility controls are to be added to the list the CFIB list the processed count and a response code e.g. 4 are returned to the program.

When the product of the value of the DBS operand and 4096 is larger than the message buffer size there is insufficient message buffer space to contain the data block. In this case the command is completed and a response code e.g. 11 is returned.

The request operands provided in the message command block for the RDV command are summarized in the following table and described herein.

In execution of one embodiment of the RDV command when sufficient message buffer space is provided the duplexing vector is placed in the data block the SID limit is placed in the Sid Limit SL operand and a response code e.g. 0 is placed in the Response Code RC operand.

When the product of the value of the DBS operand and 4096 is larger than the message buffer size there is insufficient message buffer space to contain the data block. In this case the command is completed and a response code e.g. 11 is returned.

The request operands provided in the message command block for the TRFA command are summarized in the following table and described herein.

In execution of one embodiment of the TRFA command when the remote facility accessibility level is connected a response code e.g. 0 is returned. When the remote facility is not connected the remote facility disconnect time the remote facility disconnect time validity indicator and a response code e.g. 1 are returned.

The request operands provided in the message command block for the SRBA command are summarized in the following table and described herein.

Initially a determination is made as to whether the RBAU control and CRBAU and RBAU operands are zero INQUIRY . If not then processing continues with a comparison of the retry buffer authority control value to the CRBAU operand STEP . When they compare as equal INQUIRY the value of the RBAU operand is stored in the retry buffer authority the signaling vector entry associated with the retry index is reset and the retry buffer state is updated STEP .

When the retry buffer authority control is changed from zero to a non zero value INQUIRY the retry buffer state is changed from unassigned to assigned and not in use STEP the bit in the retry vector addressed by the retry index is set to one STEP and a response code e.g. 0 is returned STEP .

When the retry buffer authority control is changed from a non zero value to zero the retry buffer state is changed to the unassigned state STEP the bit in the retry vector addressed by the retry index is set to zero STEP and a response code e.g. 1 is returned STEP .

When the retry buffer authority control is changed from a non zero value to a non zero value the retry buffer state is set to assigned and not in use STEP and a response code e.g. 2 is returned STEP .

When the compare fails INQUIRY the retry buffer state is not changed. The value of the retry buffer authority is placed in the RBAU operand STEP . The RBAU operand and a response code e.g. 4 are returned STEP .

When the retry buffer authority control is initially zero and both the CRBAU and RBAU operands are zero INQUIRY the retry buffer remains in the unassigned state and a response code e.g. 3 is returned STEP .

One embodiment of the recovery flow is described next. If the primary operation ended with an IFCC INQUIRY then the connection to the primary coupling facility is tested by issuing an IMP command STEP . Successful completion of the IMP command implies two things. First the connection itself is verified. Second the command quiescing rules dictate that execution of the IMP command indicates that the command being recovered has completed. So in particular no signals are being issued by CF 1 on behalf of that command.

Should the primary coupling facility be connected or if the primary operation did not end with an IFCC then a similar check is made of the secondary command INQUIRY . If the secondary command ended with an IFCC then the connection to the secondary coupling facility is tested INQUIRY . If the secondary command succeeded successfully or if the secondary command had an IFCC and the subsequent IMP command succeeded then all signals are guaranteed to have stopped flowing and the signal group index in each signaling vector can be reset by issuing an SRBA command to each coupling facility STEP . If however the secondary command had an IFCC and the IMP command fails then a Probe Remote Facility command PRFC is issued to the primary coupling facility STEP . This is described further with reference to

Initially the PRFC command is issued with the verify option STEP . If unsuccessful INQUIRY the OS escalates to the function of dropping the remote facility connection STEP . In one example this is done by redriving the PRFC. Forcing this connection to be dropped ensures that the remote coupling facility recognizes a state change in the peer ISC link which stops any signals from being issued once the connection is dropped. It should be noted that the connection can be immediately reestablished so long as the state transition is made in the connection. 

Subsequent to redriving the PRFC or if the initial PRFC is successful then the SRBA command is issued to reset the primary DSGX value STEP .

Returning to INQUIRY if there is no connection to the primary coupling facility then there is a further determination is made as to whether there is a connection to the secondary coupling facility INQUIRY . If there is no connection to either facility then no further action is required STEP .

However if there is connectivity to the secondary facility then a Probe Remote Facility command is issued to the secondary coupling facility STEP as described further with reference to

Similar to the logic described above the PRFC command is issued with the verify option STEP . If the PRFC command is unsuccessful INQUIRY then the operating system escalates to the function of dropping the remote facility connection STEP . Thereafter or if the initial PRFC is successful then an SRBA command is driven to reset the secondary DSGX value STEP .

Once the SRBA command has been successfully completed to each coupling facility that had an IFCC the DSGX value associated with the subchannel is set to one and the subchannels are made available for reuse. In this case they will most likely be reused for retrying the failed duplexed operation. But other subchannels may also be selected.

Duplex command pairs when they execute in the coupling facilities exchange duplex signals between the coupling facilities. In one embodiment the list notification command is used to exchange the duplex signals. Further to facilitate exchanges of duplex signals each coupling facility has one or more sender channels and one or more receiver channels that connect the two coupling facilities. See e.g. . The duplex signals are used to extend the object and command concurrency rules across the synchronized objects in each coupling facility. The set of duplex signals and their protocols are described next.

In one embodiment the duplex signaling protocol employs a signaling vector which has a plurality of entries. In one example there is a signaling vector entry for each retry buffer.

The duplex commands use signal groups in the signaling vector to coordinate the progress of the first and subsequent entries in a command. In a duplex command there is a signal group index value which indicates which of the signal groups is the current signal group in the duplex coupling facility. The current signal group index value designates the current signal group in the recipient coupling facility. The value of this index points to the signal group that is to be used for the entry of the command in the respective coupling facility s signaling vector. The signal group indexes are incremented as part of the process of committing an entry or completing the command. When the signal group index object reaches three and increments the value wraps to one.

The Set Retry Buffer Authority command described above is used to set the signal group values for all signal group indexes to zero and reset the signal group index to one.

Duplex commands return the incremented signal group index value in the MRB. This value is used in subsequent duplex commands as the current signal group index value.

This section defines the signaling operands. Request operand validity is checked by the receiving coupling facility. Detection of invalid values results in the command failing.

One embodiment of duplex signaling operands used in accordance with an aspect of the invention include for instance 

Duplex Retry Index DRX A value that designates the duplex retry buffer. The duplex retry index is provided as a request operand on the duplexing command.

Duplex Signal Group Index DSGX A value that identifies the duplex signal group to be updated in the signaling vector. Valid DSGXs are assigned DSGX values within the range of one to three as an example. An invalid DSGX does not update the signal vector.

Duplex Signal DS A value that indicates the duplex signal to be set in the signaling vector. Valid values are for instance one through five. An invalid value results in a signal vector bit not being set. It has the following encoding as example 

Duplex signals coordinate the execution of duplex commands in each of the two coupling facilities. In one embodiment the halt execution signal has precedence over the other duplex signals.

Duplex signals are communicated for instance by using list notification commands which are generated secondary message commands. For example the duplex signals are sent using the list notification command with a nonempty state change operand value of zero a summary update operand value of zero the signal vector token for the remote coupling facility and a list notification entry number operand. One embodiment of a format of the duplex signal command block of a list notification command is shown in .

A successful MRB returned for a duplex signal indicates that the signal was received in the signal vector. However it does not indicate in this example that the signal was recognized by the duplex command at the duplex coupling facility.

Signals are used by the duplex command pair to communicate the progress of the command in the respective coupling facility.

The association of retry buffers to signaling vector entries is a one to one correspondence and the partitioning of the retry buffers by a system defines a corresponding partitioning of the signaling vector entries. The retry index then becomes the index for both the retry buffer and the signaling vector entry. For instance a retry index value of 14 points to both a retry buffer and a signaling vector entry as depicted in .

Each of the duplex commands in the duplex command pair designates a retry buffer and a signal group to coordinate the signaling between the two coupling facilities. Each duplex command includes the retry index for the coupling facility that is receiving the command and the retry index and signal group index for the coupling facility that has the duplexed structure. The current signal group index is used for the coupling facility receiving the command. The retry index and signal group index value may not be the same in both coupling facilities. The set of retry index and signal group index values are mirrored in the commands of the duplex command pair.

The commands of a duplex command pair are associated by the retry index values in the MCB. The signal group index values used to do signaling for these retry buffers are associated by the signal group index values in the MCBs.

The execution of duplex commands is divided into three phases each of which is executed in a coupling facility command decode command execution and command completion phases. The first phase is command decode. In this phase the command starts execution and sends a ready to execute command to the other coupling facility. The ready to execute signal is sent to determine if the command has been command suppressed at the other coupling facility. If no ready to execute or ready to complete signal is recognized the command does not proceed beyond the command decode phase and the command can be terminated without breaking duplexing. The ready to execute signal is sent when for instance the following conditions are met 1 a path to the duplex coupling facility is active 2 the SID is active 3 duplexing is active 4 a path in the duplex class path group is active 5 dumping serialization is not active. The ready to complete signal is used as command decode completion indication due to the fact that the ready to execute and ready to complete signals can be sent in parallel on different channel paths.

The execution phase of the command is different for single entry commands and list form commands i.e. commands that process multiple entries one at a time . For single entry commands other than Write And Register and Write When Registered after the command decode phase is completed a single ready to complete signal is sent. When the ready to complete signal has been sent and a ready to complete signal has been recognized the entry is committed and the command enters the command completion phase. For the Write And Register and Write When Registered commands the execution phase is dependent on the setting of the WRTCI request operand described below . When the WRTCI request operand is B 0 the execution phase is substantially identical to the execution phase for any single entry command. When the WRTCI request operand is B 1 the sending of the ready to complete signal is delayed until both the command decode phase is complete and a ready to complete signal or a halt execution signal is recognized. When a ready to complete signal is recognized and the command decode phase is complete a ready to complete signal is sent and the command enters the command completion phase. When a halt execution signal is recognized the command execution is halted.

For list form commands after the command decode phase is completed a ready to complete signal is sent. When the ready to complete signal has been sent and a ready to complete signal has been recognized the entry is committed and another ready to complete signal is sent. This exchange of ready to complete signals continues until the last entry is committed or a halt execution signal is recognized then the command enters the command completion phase.

In the command completion phase the current signal index is incremented and the MRB for the command is returned with the appropriate response code.

During the various phases of duplex command execution one or more duplexing processes may be invoked. Examples of processes that may be executed are described below.

Since a duplex command pair is issued on two separate coupling facilities and each of the coupling facilities services these commands at differing rates it is possible for a coupling facility to receive signals for a duplex command that has not yet started at the receiving coupling facility. For example the ready to execute signal can be received by a coupling facility that has not yet started command execution of a duplex command.

The duplex command when it executes examines the signals in the current signal group to see if any have been received prior to command execution and continues execution based on the received signals for the command. The duplex command may also time out and be invalidated prior to the command being executed at the coupling facility after receiving these signals.

An entry is committed when the entry object is updated in the coupling facility and can be observed by subsequent accesses of the entry. Prior to an entry being committed the entry remains unchanged as observed by subsequent accesses of the entry.

The current signal group index and the duplex signal group index are incremented by one when an entry is committed.

When a duplex command executes and it is ready to start processing for an entry a ready to execute signal is sent. The ready to execute signal is sent when for instance the following conditions are met 1 a path to the duplex coupling facility is active 2 the SID is active 3 duplexing is active 4 a path in the duplex class path group is active 5 dumping serialization is not active. The ready to execute signal when it is recognized indicates that the duplex command at the other coupling facility has started execution of the command and a ready to complete signal can be sent. A ready to complete signal cannot be sent until a ready to execute or ready to complete signal has been recognized. The ready to complete signal may be recognized before the ready to execute due to the fact that they both may be sent in parallel and the ready to complete may arrive and be recognized first.

The ready to complete signal is sent when the command is ready to commit completion status or a request exception condition exists for the command. When the ready to complete signal has been sent the MRB for the ready to complete signal has been recognized and the ready to complete signal from the other coupling facility has been recognized the entry is committed and the command completes or command execution stops at the completion of command decode and the request exception is presented for the command.

If a halt execution or request for suppression signal is received the entry is not committed and command execution stops at the completion of command decode.

If a command has received a ready to execute command is ready to commit the entry and has sent a ready to execute command but not received an MRB in response the command may send a ready to complete command on another message path. The command cannot send a halt execution request for suppression or request for suppression accepted signal until the ready to execute and ready to complete MRBs have been received. Note that a halt cannot be sent after a ready to complete has been sent for single entry commands.

The ready to complete signal cannot be sent before the ready to execute signal has been sent. The ready to complete signal may be sent on a separate message path in parallel with the ready to execute signal.

When a duplex command executes and it is ready to start processing for an entry a ready to execute signal is sent. The ready to execute signal is sent when for instance the following conditions are met 1 a path to the duplex coupling facility is active 2 the SID is active 3 duplexing is active 4 a path in the duplex class path group is active 5 dumping serialization is not active. The ready to execute signal when it is recognized indicates that the duplex command at the other coupling facility has started execution of the command and a ready to complete signal can be sent. A ready to complete signal cannot be sent until a ready to execute or ready to complete signal has been received. The ready to complete signal may be recognized before the ready to execute due to the fact that they both may be sent in parallel and the ready to complete may arrive and be recognized first.

The ready to complete signal is sent when the command entry is ready to commit completion status for the entry or a request exception condition exists for the command. When the ready to complete signal has been sent and a ready to complete signal has been recognized the entry is committed or command execution stops at the completion of command decode and the request exception is presented for the command. Subsequent entries then send and receive ready to complete signal pairs. The ready to execute signal is exchanged only once prior to the first entry.

If one or more entries have been committed and a halt execution or request for suppression signal is received the entry is not committed and command execution stops at the previous entry and a timeout response code is returned. If no entries have been committed and a halt execution or request for suppression signal is received the entry is not committed and command execution stops at the completion of command decode and a halt response code is returned.

If a command has recognized a ready to execute signal is ready to commit the entry and has sent a ready to execute signal but not received an MRB in response the command may send a ready to complete signal on another message path. The command cannot send a halt execution request for suppression or request for suppression accepted signal until the ready to execute and ready to complete MRBs have been received.

When the ready to complete signal has been sent the MRB for the ready to complete signal has been recognized and the ready to complete signal from the other coupling facility has been recognized the entry is committed and the command completes or advances to the next entry if additional entries exist. Note that a halt cannot be sent after a ready to complete has been sent without first advancing to the next entry. If a ready to complete has been sent for the last entry in the list then no halt signal can be sent.

The ready to complete signal cannot be sent before the ready to execute signal has been sent. The ready to complete signal may be sent on a separate message path in parallel with the ready to execute signal.

When a command that is waiting on resources held by other commands recognizes a ready to complete signal for itself or for a command of lower priority the command sequence numbers of the other commands holding resources desired by this command are examined. For each such command one of three cases can occur as examples 

If the command sequence number of the waiting command and the selected resource owning command are equal then the system identifier associated with each system that sent the command is used as a tie breaker. If the system identifier of the waiting command is less than the system identifier of the selected resource owning command then the waiting command is of higher priority and case 1 applies. Otherwise cases 2 and 3 apply.

The request for suppression signal when received causes the receiving command to either suppress the command or to allow the command to continue if the resources are available. If the command is suppressed a request for suppression accepted signal is sent and the command is suppressed. If the command does not need to be suppressed then the ready to complete or halt execution signal is sent as is appropriate.

The request for suppression signal can only be sent in this example after a ready to execute signal and ready to complete signal have been sent and their respective MRBs have been recognized.

Request for suppression accepted can only be sent in this example after a ready to execute signal has been sent and the MRB has been recognized.

A halt execution signal can be sent by a coupling facility once all outstanding signals have received an MRB. A halt execution signal can be sent or received after any other signal once the ready to execute signal exchange has taken place.

When a halt execution signal is recognized command execution stops at the completion of command decode or at the previous entry for list form commands after the first entry has been committed. The receiving command completes any outstanding signals for the entry being processed.

Any time one of these conditions occurs a halt execution signal is sent if a duplex command is being executed.

When a halt execution signal is sent and the MRB for the halt execution signal is recognized the command is suppressed and the response code defined for the halt condition in the command is returned with these exceptions 

When a halt signal is recognized the command is backed out and if it is a list form command and at least one list item was executed to completion the entry is backed out and the current object index is set to the entry that was backed out and then the response code is set. If both a command suppression condition and halt execution signal occur the command suppression response code is returned. If only the halt execution signal occurs and the command is either a single list entry command or a list form command where no list items have completed execution the command execution is halted and a response code e.g. 18 is returned.

The duplex signal group index and duplex retry index values are sent as part of the LNEN operands in the list notification command. The signal vector bit in the signaling vector is set based on the LNEN value. Each duplex signal list notification command sets only a single bit in the signal group. The MRB for the list notification command is returned once the bit has been set. The recognition of the MRB for the list notification command is not used as an indication that the signal has been recognized at the receiver of the signal it only indicates that the bit has been set.

When any of the following conditions exist the signal group with an index value that is one greater than the current signal group index value is set to zero 

For signals sent the signal group is cleared prior to the signal being sent. When the current signal group index value reaches three and an incremented value is needed the index value wraps to a value of one.

The duplex commands have a retry index duplex retry index and duplex signal group index value as operands. The retry index and current signal group index values are used to determine the signaling vector entry and signal group in the signaling vector that are to be used in the coupling facility. The current signal group index indicates which set of signaling bits is the initial set of duplex signals to be used for the command. The duplex retry index and duplex signal group index are used as part of the LNEN operand in the list notification command to be sent to the duplex coupling facility.

In one embodiment three signal groups are employed for list form commands. In the case of list form commands the three signal groups are employed for the following reasons 

The duplex signal list notification command provides the information used by the designated system to update one signaling vector entry bit.

Execution of a list notification command involves first selecting a message path from the set of message paths that form an active connection with the remote coupling facility and making the list notification command pending on this path.

When a pending list notification command is executed the command is issued to the duplex coupling facility.

Execution of a duplex signal list notification command is completed when a message response block is received at the coupling facility in response to the command. Duplexing is broken when for instance 1 all message paths in the path group are inactive at the time of path selection or 2 the state of all of the active message paths to the associated system is made error state pending by the system and inactive by the coupling facility.

When the duplex command times out and an invalidate request is received at the coupling facility if 1 the ready to execute signal has not been sent then the response code is set to for instance 253 and the invalidate response is sent and the command is suppressed if 2 the ready to execute signal has been sent and the ready to execute or ready to complete has not been recognized then a halt execution signal is sent the response code is set to for instance 253 and the invalidate response is sent and the command is suppressed if 3 the ready to execute signal has been sent and the ready to execute or ready to complete has been recognized the invalidate response is sent and the command is allowed for example 300 milliseconds after the ready to execute or the first ready to complete signal was recognized to complete. Otherwise the command is suppressed when the 300 milliseconds expires setting the duplexing inactive bit and a response code of for instance 20 duplexing inactive . During the 300 millisecond window no new commands are executed at the coupling facility and the duplex command continues to execute. After the additional 300 milliseconds has transpired the command is command suppressed and new commands can then be executed in the coupling facility.

When a duplexing command is executing and the command ends in a coupling facility a ready to complete signal has been sent and the entry is not committed or backed out then the duplex active bit for the SID in the duplexing vector is set to zero. If the command is a single list entry command the command is completed and the MRB is returned. If the command is a list form command processing of the current list item is completed processing of the command is completed at the current list item and the MRB is returned. In either case the duplexing deactivated indicator is set to B 1 in the response descriptor.

If a duplex command attempts to execute and there are no paths available between the two coupling facilities then the duplex active bit for the SID in the duplexing vector is set to zero the command is suppressed and a response code e.g. 20 is returned.

When a duplex command is executed and the duplex active bit for the SID in the duplexing vector is zero the command is suppressed and a response code e.g. 20 is returned.

Commands that are duplexed between coupling facility structures use peer signaling in accordance with an aspect of the present invention to keep the commands in synchronization. There are three steps that the signals keep in synch 

The latching of resources step presents a problem since many commands both simplex and duplex may be competing for the same resources. For one coupling facility structure Command A may win the race to latch a resource but for the duplexed structure Command B may win the race for the same resource. This implementation resolves conflicts in latching resources by using a combination of techniques all of which include communications between tasks within a structure. A Task Control Block TCB is used as a communications medium. Each task has its own Task Control Block and is able to access and update the Task Control Block of the other tasks. Each update of an item in the TCB is done atomically so that no partial updates occur.

Further details regarding the signaling protocols employed in one or more aspects of the present invention are described with reference to . In particular provide an overview control flow of duplexed commands and provide embodiments of control flows for various functions invoked in the overview and or used by the protocol. provides an extension of latch management for simplex commands which intersects with this control flow. In one example the logic of are executed by the coupling facility.

Referring to initially a command is received by the CFCC and a task control block TCB is assigned to the command STEP . Also the CSN for the task is zeroed. Next a duplex command decode checking function is invoked STEP . This is described further below with reference to . Should one of the checks of the decode checking function fail INQUIRY the command is suppressed and the appropriate response code is returned STEP . If however all of the checks are successful then an RTE exchange function is invoked STEP . This is described further below with reference to . Should the RTE exchange fail INQUIRY the command is suppressed and a response code e.g. 253 is returned STEP . If however the RTE exchange is successful then the command is executed STEP . During execution a check is made as to whether any halting conditions have been recognized STEP .

If any halting conditions are encountered during command execution INQUIRY then a halt signal is sent STEP and the command completes with the response code appropriate for the halting condition that was encountered STEP . Otherwise a duplex latch resource function is invoked for each resource that needs to be latched by the command for processing of the current list item STEP . This is described in further detail with reference to . If all latch obtains are successful INQUIRIES then the command completes processing of the current list item and the RTC exchange function is invoked STEP . This is described in further detail with reference to . However if a latch is not successfully obtained then the command ends and a response code is returned STEP .

Returning to should the RTC exchange function end without receiving an RTC signal INQUIRY the command is completed and a response code is returned step . If however an RTC signal is received the processing of the current list item is completed STEP . If the command is a single list entry command INQUIRY the MRB is returned and the latches are released. In this case processing is complete STEP . If the command is a list form command and either a model dependent timeout is exceeded or the last list item is processed INQUIRY then the command is completed with either an RC 1 or RC 0 as appropriate the MRB is returned and the latches are released. Again processing for the command is completed STEP . If the command is a list form command the current list item is not the last list item and a model dependent timeout has not been reached the latches are released and the next list item is processed STEP . This completes a description of one embodiment of an overview of duplex signal processing.

If the CSN is zero the command is not executed as a duplexed command. It may be executed as a simplex command or not executed at all based on the setting of the DUPAI indicator and the current state of the structure. For instance if the DUPAI indicator is B 0 INQUIRY the command is executed as a simplex command no matter the structure state STEP . If the DUPAI indicator is B 1 and the structure is in the duplexing active state the command is also executed as a simplex command STEP . However if the DUPAI indicator is B 1 and the structure state is duplexing inactive the command is suppressed and a response code e.g. 20 is returned STEP .

 Notes on CSN and DUPAI Setting the CSN indicator to zero is a means for the operating system to execute a command in simplex mode when the structure is duplexing active. This is done for instance for a Read and Register command where the storage class is not being changed by the command. Since the data is only returned from the primary cache structure and since the registrations are only made in the primary structure there is no reason to send the command to the secondary structure. So the command is issued with the CSN indicator set to B 0 . This is done for various commands that are reading data or controls in the primary structure but do not update any control objects that are duplexed.

However a window exists for read commands that set the CSN to zero and are issued after duplexing has failed but before the structure has entered simplex mode. During the recovery window the structure objects may be out of synchronization. So a read command sent to one structure with CSN 0 may execute successfully and observe object states that may not exist after the simplex mode is resolved. For instance a Move List Entry command may move a list entry in the secondary structure but not the primary structure. If a Read List Entry command is issued to the secondary structure during structure failover with CSN 0 the moving of the list entry may be observed. However if the primary structure is selected the moving may be suppressed by the failover. The observing of a moved list entry that is not in fact moved is a violation of command concurrency. This problem is avoided by setting the DUPAI indicator to B 1 along with setting the CSN to zero. Then if the structure has become duplexing not active the read command is suppressed.

Continuing with if the command sequence number is non zero a request is made to execute the command using the duplexed command processes. So the structure state is checked to see if duplexing is active for the structure INQUIRY . If duplexing is not active the command is suppressed and a response code e.g. 20 is returned STEP . If duplexing is active a test is made to see if the remote facility is connected STEP . If the remote facility is not connected the command is suppressed and a response code e.g. 253 is returned STEP .

If the remote facility is connected the state of the structure is again tested to see if dumping serialization is held STEP . If so the command is suppressed and the dumping serialization held response is returned STEP . If dumping serialization is not held all the tests are successfully completed and the processing of the duplexed command continues STEP .

Next there is a check to see if an RTE signal has been received from the remote coupling facility in the signaling vector entry associated with the command INQUIRY . If an RTE signal has been received the command timer is started and the return code for the function is set to success STEP . On the other hand if an RTE signal has not been received the primary and secondary links are tested to see if any errors have occurred that would have deactivated the links INQUIRY . The primary link is the link where the RTE signal from the remote coupling facility is received and the secondary link is the link where the RTE signal is sent. If there are no active primary or secondary links the signal exchange is aborted and the function ends with return code of failure STEP . If there are still active links the function loops back to the check of reception of the RTE signal INQUIRY .

 Note on RTE exchange. The RTE signal is employed to improve both performance and reliability of the protocol. By delaying the start of command execution until both commands have been received and recognized by their respective coupling facilities the latch hold times and any resulting contention are minimized. This is especially desirable if the distances between the coupling facilities are large and the commands are skewed in time by the propagation delays involved. Therefore including the RTE exchange in the protocol improves the performance of the protocol by minimizing the latch hold times.

A second reason for including the RTE exchange is for improved availability. The protocol indicates that duplexing is to be broken by the coupling facility if a completion signal RTC has been sent to the remote coupling facility but no completion signal has been received before the command times out. But this rule does not apply to the RTE exchange since no object updates have yet occurred. A failure condition in the RTE exchange results in the command being suppressed and a response code e.g. 253 being returned. In this case the duplexing state does not change. If the failure is temporary in nature then the command can be redriven by the operating system for a relatively short duration of say a few seconds and the temporary condition may be rectified in that period of time. If the RTE exchange is not made then any temporary error detected by the RTC exchange causes duplexing to be broken. By requiring a successful exchange of signals prior to sending a completion signal the chances of duplexing being broken are greatly minimized and the resulting protocol is more robust.

 Notes on duplexing command deadlocks. A basic deadlock scenario with duplexed commands can occur as follows. Suppose Command A is issued by OS 1 and Command B is issued by OS 2 and the two commands attempt to latch the same resources. A deadlock occurs if Command A is executed on CF 1 obtains the latch on the resource and issues an RTC signal. Command B on CF 1 now waits for Command A to complete before getting the latch. Command A is waiting on an RTC from its duplexed instance running on CF 2. However the situation on CF 2 is reversed and Command B has obtained the latch and sent the RTC signal and Command A is delayed. This is the deadlock. The deadlock is resolved by comparing the command sequence numbers for the two commands. If Command A has a lower i.e. higher priority CSN than Command B then the latch manager which is a component of CFCC on CF 2 forces Command B to be suppressed. This causes Command B to issue a request for suppression to CF 1. This will be accepted in this circumstance and a request for suppression accepted RFSA will be sent by CF 1. Command B then backs out on CF 1 and Command A can then obtain the resource and the duplexed pair for Command A completes. Meanwhile OS 2 sees the suppression of Command B and reissues the command with the same CSN. Since the CSN is an increasing value across all the commands the priority of Command B will eventually exceed the priority of all other commands and be assured to complete.

In a further aspect the latch manager also detects deadlocks that can occur when intervening commands including simplex commands hold latches. In this case the proxy controls in the TCB are used to recognize chain conditions and impose the above protocol even when intervening commands are present. This is described in . Two more complex scenarios are described below after is described.

If a proxy RTC signal was not received INQUIRY processing loops back to reattempt to latch the resource STEP . If on the other hand a proxy RTC signal was received then a comparison is made between the task proxy CSN and the CSN of the latch holder STEP . If the task proxy CSN is a higher priority lower value than the latch holder CSN INQUIRY then the suppress command flag is set in the latch holder s TCB STEP and processing loops back to reattempt to latch the resource STEP . Setting the suppress command flag causes the latch holder to release the latches when it detects the flag has been set.

If on the other hand the task proxy CSN is not of a higher priority then a test is made to see if the latch holder received a proxy RTC signal INQUIRY . If not then the latch holder task s TCB is updated by storing this task s CSN as the proxy CSN and by setting the proxy RTC flag STEPS . Then processing loops back to reattempt to latch the resource STEP .

However if the latch holder did receive a proxy RTC signal then a comparison is made between this task s proxy CSN and the latch holder s proxy CSN INQUIRY . If this task s proxy CSN has priority INQUIRY then the latch holder s proxy CSN is replaced with this task s proxy CSN STEP and processing loops back to reattempt to latch the resource STEP . If this task s proxy CSN does not have priority no updates are made and processing loops back to reattempt to latch the resource STEP .

If a request for suppression signal was received INQUIRY then a request for suppression accepted signal is sent and the function ends with request for suppression STEP . The command will be suppressed in this case.

If a halt signal was received INQUIRY then the function ends with an execution halted condition STEP . Again the command will be suppressed but no signals need to be sent in this case.

If on the other hand an RTC signal was received INQUIRY a comparison is made of this task s CSN with the latch holder s CSN STEP . If this task has priority INQUIRY then the suppress command flag is set in the latch holder s TCB STEP and processing continues in at label A . If this task does not have priority but the latch holder has received a proxy RTC signal INQUIRY then this task s CSN is compared to the latch holder s proxy CSN STEP and processing continues in at label B .

If the latch holder did not receive a proxy RTC signal then the latch holder s TCB is updated by storing this task s CSN in the proxy CSN field and setting the proxy flag STEP . Processing then continues in at label A . If no RTC signal has been received INQUIRY then processing continues in at label A .

Label B in completes the tests for when an RTC signal has been received. At label B a test is performed to see if this task s CSN has priority over the proxy CSN of the latch holder s task INQUIRY . If not then processing continues at label A . If so then the latch holder s proxy CSN is replaced with this task s CSN STEP and processing continues at label A .

Label A in resumes the duplex command function. First a test is made to see if the suppress command flag has been set in this task s TCB INQUIRY . If so then a Halt signal is sent to the remote coupling facility and the function ends with a response that a halt signal was sent STEP . However if the suppress command flag is not set then the proxy flag is tested INQUIRY . If no proxy signal was received then processing loops back to the top of at label C where a reattempt is made to latch the resource. If on the other hand a proxy RTC signal was received then a comparison is made of this task s proxy CSN with the CSN of the latch holder STEP . If this task s proxy CSN has priority INQUIRY then the suppress command flag is set in the latch holder s TCB STEP and processing resumes at label C . If this task s proxy CSN does not have priority over the latch holder s CSN a test is made to see if the latch holder received a proxy RTC signal INQUIRY . If not then the latch holder s TCB is updated by storing this task s CSN as the proxy CSN and setting the proxy flag STEP . Processing then resumes at label C . However if the latch holder did receive a proxy RTC signal then a comparison is made to see if this task s proxy CSN has priority of the latch holder s proxy CSN INQUIRY . If so then the proxy CSN in the latch holder is replaced with this task s proxy CSN STEP and processing continues at label C . If not no updates are made and processing resumes at label C .

If the flag is not set the checks for the signal reception is continued until either a signal is received or the command timer expires INQUIRY . If the suppress command flag is set then the latch manager has determined that a latch held by this command may be creating a deadlock situation and the priority decision is for this command to back out. This is done as follows. First a request for suppression signal is sent to the remote coupling facility to inform that coupling facility of the potential deadlock and the need to suppress this command STEP . The function then waits on reception of a signal up to the point when the timer expires. If an RTC signal is received INQUIRY then the command can complete normally. No deadlock exists and normal completion will free the necessary latches. So the function ends with a success indication STEP . If an RTC signal is not received but a halt signal is received INQUIRY then the function ends with an indication that execution was halted STEP .

If a request for suppression accepted signal is received INQUIRY then the other coupling facility has acknowledged the request for suppression signal and the function ends with this indication STEP . If no signal of any kind is received and the command timer expires INQUIRY duplexing is broken STEP . The duplexing active indicator for the structure in the duplexing vector is set to B 0 and the function ends with a duplexing inactive indication STEP .

 Note on breaking duplexing. Once an RTC signal has been set the coupling facility has committed to completing the command. If it receives an RTC signal or an RFS signal then it can safely complete the command. It can also back out the command if it receives a halt signal or if it sends an RFS signal and receives an RFSA signal. In either case the protocol rules ensure that both sides suppress the command. However if no signal of any kind is received and the command timer expires duplexing is to be broken since there is no positive indication from the other coupling facility that it has either completed the command or suspended the command. Ending the command without this positive acknowledgment is not allowed without also breaking duplexing. Otherwise the structure states may be different once the latches are dropped. This violates the desire to keep the two structures in complete synchronization.

In the follow scenarios Command n has a command sequence number with value n. So Command 1 is a higher priority than Command 2 and Command 2 has a higher priority than Command 3. The latch manager detects the potential deadlock situations and uses a combination of signals RFA RFSA and Halt and TCB flags suppress command and proxy RTC to resolve these deadlocks. The logic is described in the and and the following examples serve only to illuminate this logic with explicit examples. Each case can be reduced to either the basic deadlock scenario described above or one of these three cases.

In this scenario three commands Commands 1 2 and 3 are issued by three separate systems to a pair of duplexed structures one residing on CF 1 and the second residing on CF 2. Commands 1 and 3 need to latch Resources x and y and Command 2 only needs to latch Resource x. The hierarchy of latching rules in the coupling facility requires if both x and y need to be obtained y is obtained first.

The order of arrival and subsequent execution is as follows On CF 1 Command 1 obtains latches for both x and y and sends an RTC signal to CF 2. Commands 2 and 3 both wait in the latch manager on CF 1. Command 2 waits on latch x and Command 3 waits on latch y. On CF 2 Command 2 executes first and obtains the latch on Resource x and sends an RTC signal to CF 1. Command 3 obtains the latch on Resource y and waits on the latch on Resource x. Command 1 waits on latch y in the latch manager on CF 2.

A deadlock exists between Commands 1 and 2. Command 1 has obtained all its latches on CF 1 including the latch on x that Command 2 needs. Meanwhile Command 2 has obtained the latch on x which Command 1 needs on CF 2. Also Command 1 on CF 2 has received an RTC signal from CF 1. However this differs from the basic deadlock case since a third command Command 3 owns the latch that Command 1 is requesting first. Command 3 is an intervening command of lower priority than Command 1.

This more complex scenario is resolved as follows The latch manager servicing the request for the latch on y by Command 1 determines that the latch holder has lower priority and sets the suppress command flag in the TCB for Command 3. Next when the latch manager services the request by Command 3 for latch x the latch manager detects that the suppress command flag is set for Command 3. But no RTC signal has yet been sent for Command 3 since not all latches have been obtained. So the latch manager issues a Halt signal to CF 1 and Command 3 completes with a command halted response. Likewise when the latch manager on CF 1 services Command 3 s request for the latch on y it detects the reception of a halt signal and ends the command with a command halted response.

Once Command 3 has been halted Command 1 can obtain the latch on y on CF 2 and then detect contention with Command 2 on latch x. The situation has reduced to the basic deadlock and is resolved as described above.

In this scenario three commands Commands 1 2 and 3 are issued by three separate systems to a pair of duplexed structures one residing on CF 1 and the second residing on CF 2. Commands 1 and 2 need to latch resources x and y and Command 3 only needs to latch resource x. The hierarchy of latching rules in the coupling facility requires if both x and y need to be obtained y is obtained first.

The order of arrival and subsequent execution is as follows On CF 1 Command 2 obtains latches for both x and y and sends an RTC signal to CF 2. Commands 1 and 3 both wait in the latch manager on CF 1. Command 1 waits on latch y and Command 3 waits on latch x. On CF 2 Command 3 executes first and obtains the latch on Resource x and sends an RTC signal to CF 1. Command 1 obtains the latch on Resource y and waits on the latch on Resource x. Command 3 waits on latch y in the latch manager on CF 2.

A deadlock exists between Commands 2 and 3. Command 2 has obtained all its latches on CF 1 including the latch on x that Command 3 needs. Meanwhile Command 3 has obtained the latch on x which Command 2 needs on CF 2. Also Command 2 on CF 2 has received an RTC signal from CF 1. However this differs from the basic deadlock case since a third command Command 1 owns the latch that Command 2 is requesting first. Command 1 is an intervening command of higher priority than Command 2. Also while Command 1 has higher priority than Command 3 it does not suppress Command 3 to obtain latch x because no RTC signal has been received by Command 1.

This more complex scenario is resolved as follows The latch manager servicing the request for the latch on y by Command 2 determines that the latch holder has higher priority and sets the proxy RTC flag and the proxy CSN in the TCB for Command 1. Next when the latch manager services the request by Command 1 for latch x the latch manager detects that the proxy RTC flag is set for Command 1. It then compares the proxy CSN 2 in the TCB for Command 1 against the CSN for Command 3 3 . It determines that the proxy task has priority and sets the suppress command flag in the TCB for Command 3. Command 3 is waiting on the RTC signal from CF 1 and in this function detects that the suppress command flag is set. It then sends a request for suppression signal to CF 1 and waits for the RFSA or RTC or Halt to be received. CF 1 sees the request for suppression of Command 2 and since Command 2 is waiting on a resource a request for suppression accepted signal is sent and Command 2 is suppressed on CF 1 with a command suppressed response. When the RFSA signal is received on CF 2 for Command 3 Command 3 releases the latches on x and y and completes the command with a command suppressed response. Command 1 then obtains the latches on y and x and sends an RTC signal. There is now a deadlock between Commands 1 and 2 which is the basic deadlock scenario which is resolved as described above. It is interesting to note that the basic deadlock is resolved by the latch manager on CF 1. That is the first deadlock is resolved on CF 2 and the second deadlock is resolved on CF 1.

This third example is a more complicated version of the previous example and shows how the proxy RTC is passed across a chain of commands. In this scenario n 1 commands Commands 1 2 . . . n 1 are issued by n 1 separate systems to a pair of duplexed structures one residing on CF 1 and the second residing on CF 2. All the commands need a command latch on Resource x. Moreover there is a sequence of resources labeled y1 . . . yn. Command 1 needs just y1. Command 2 needs both y1 and y2. This pattern continues with Command i needing y i 1 and y i . The hierarchy rules are that for each pair of integers i

The execution sequence is as follows On CF 1 Command n has obtained latches y n 1 yn and x and has sent an RTC signal. All the other commands are waiting on latches. On CF 2 Command n 1 has obtained latch x and has sent an RTC signal. So the deadlock is between Commands n and n 1. But the latching in CF 2 is as follows Command 1 has obtained y1 and is waiting on x. Command 2 has obtained y2 and is waiting on y1. This sequence continues until Command n is reached which has obtained yn and is waiting on y n 1 . Command n is the only command that has received an RTC signal so it starts the proxy sequence by setting the proxy flag and proxy CSN in the TCB for Command n 1 which in turn propagates these values to Command n 2 etc. In each case command suppression is not set because the current command is of a higher priority than Command n. That is until Command 1 tests Command n 1. In this case the proxy CSN n is higher priority than the CSN for Command n 1 n 1 and so processing for Command 1 sets the suppress command flag in the TCB for Command n 1 and Command n 1 sends an RFS signal. Once Command n 1 has been suppressed and releases the latch on x Command 1 now obtains Resource x and sends an RTC signal. This now creates a deadlock between Command 1 and Command n which is detected and resolved by the latch manager on CF 1. Once that deadlock is resolved the commands can complete in priority order.

The duplexing signaling protocol described above is invoked when commands such as cache and list commands are executed as duplexed commands. Examples of commands that can be invoked as duplexed commands are described below.

For each of the commands an MRB is returned which has a response descriptor. One embodiment of the response descriptor fields returned for a duplexed command is described below.

Two fields in the response descriptor the response count and the data count define the number of meaningful bytes of information that are returned in the MRB and the data block respectively. Two additional fields are associated with structure duplexing the current signal group index is used to coordinate the signaling protocol between coupling facilities that contain duplexed structures and the duplexing deactivated indicator is used to alert the program that the duplexing state was changed from active to inactive during command execution. Each of these fields is further described below.

Response Count The value of the response count is the number of meaningful bytes returned in the MRB as described in the MRB format for each command. Reserved or unused bytes at the end of the MRB may be excluded.

Data Count When a data block is returned to the program the data count is set to the number of for instance 256 byte increments returned by the coupling facility. Reserved or unused bytes at the end of the data block may be excluded. The value of the data count times 256 is to be smaller than or equal to the message buffer size in bytes.

Current Signal Group Index CSGX When duplexing signals are issued for a command the value of the current signal group index object in the signaling vector entry associated with the retry index is stored in for instance bits of word 2. If duplexing signals are not generated for the command zeros are stored in bits of word 2.

Duplexing Deactivated Indicator DDI The value of the duplexing deactivated indicator describes the result of the single entry or list form duplexing process for duplexed commands. When the duplexing deactivated indicator is e.g. B 1 duplexing was broken during command execution and the duplexing active bit was reset in the duplexing vector. When the duplexing deactivated indicator is B 0 either the duplexing process completed successfully or no duplexing process was executed for the command. The duplexing process completes successfully when the duplexing signaling protocol is completed and the required signals are received. The value of the duplexing deactivated indicator is set to B 0 when the duplexing command completes with a response code 20 as one example.

In addition to the operands described above. Each cache structure has its own operands that are associated with the cache when it is created. Examples of these operands are described below.

Comparative Structure Authority CSAU A value used as a comparison value to the structure authority when the structure is allocated and deallocated or when castout locks are reset the detachment emulation control described below is B 1 and duplexing is active.

This operand is ignored on an Unlock Castout Locks command when duplexing is inactive or when the detachment emulation control is B 0 .

Comparative Remote Facility Structure Authority CRFSAU A value used as a comparison value to the remote facility structure authority when castout locks are reset the detachment emulation control is B 1 and duplexing is active.

This operand is ignored when duplexing is not active or when the detachment emulation control is B 0 .

Command Sequence Number CSN A value associated with a command that is duplexed. Cache structure commands that specify a non zero value in the CSN request operand cause the invocation of the duplexing command process when duplexing is active for the structure. Commands that do not have the CSN request operand defined or which specify a zero value in the CSN request operand do not invoke the duplexing command process.

Detachment Emulation Control DTEMC A value that controls the processing of the Unlock Castout Locks command. The two possible values are 

When the detachment emulation control is B 1 the change bit overindication CBO castout parity bits indicator CP and user data field UDF operands in the unlock castout locks UCL items and the castout process identifier request operand are not used and are ignored.

Duplexing Active Indicator DUPAI A value that controls execution of the command based on the duplexing state of the structure. It has the following encoding 

Duplexing Signal Group Index DSGX A value that identifies the target signal group in the signaling vector entry identified by the duplexing retry index and the remote facility controls. If duplexing is active and the command sequence number is non zero the duplexing signal group index is non zero. If duplexing is not active for the structure or if the command sequence number is zero the operand is ignored.

Duplexing Retry Index DRX A value that designates a signaling vector entry for the signaling vector identified by the remote facility controls. If duplexing is active and the command sequence number is non zero the duplexing retry index is non zero. If duplexing is not active for the structure or if the command sequence number is zero the operand is ignored.

Failed Structure Indicator FSI A value that controls the state change for the structure that occurs when a Deallocate Cache Structure command is executed and the structure is in the allocated state. It has the following encoding 

Immediate Reclaim Control IMMRC A value that determines what reclaim action should occur when the castout lock is reset. It has the following encoding 

List Form Duplexing Completion Code LFDCC The list form duplexing completion code is a value that specifies the reason a list form duplexing process was stopped with a model dependent timeout when one or more list items have been processed. It has the following encoding as an example 

Local Cache Entry Deregistration Control LCEDC A value that controls the deregistration process for a Read Directory command. It has the following encoding 

Locked For Castout Selection Control LFCSC The locked for castout selection control is a value that further controls the selection of directory entries when the change state selection control is B 1 . The two possible values are 

Name Block Format Control NBFC The name block format control is a two bit value that determines the set of request operands returned in the name block by a Read Directory command. It has the following encoding 

Retry Index RX A value that designates a signaling vector entry. Valid RXs are zero and assigned RXs within the range of one to the RX limit. If duplexing is active and the command sequence number is non zero the retry index is non zero. If duplexing is not active for the structure or if the command sequence number is zero the operand is ignored.

Skip Nonexistent Entries Control SNEC A value that controls the halting of an Unlock Castout Locks command when a list item specifies a directory entry that does not exist. It has the following encoding 

Storage Class Change Control STCCC A value that controls the processing of a reference signal when the storage class is changed. It has the following encoding 

Suppress Detachment Scan SDS A value that controls the directory scan in the Detach Local Cache command. It has the following encoding 

Suppress Read SR A value that indicates the data transfer for a Read And Register or Read For Castout command is suppressed.

Suppress Registration Test SREGT A value that controls the testing of the LCEN registration for the Write When Registered command. It has the following encoding 

Test Message Buffer Size Indicator TMBSI A value that controls the testing of the message buffer size for the Read And Register command. It has the following encoding 

Wait on Ready to Complete Indicator WRTCI The wait on ready to complete indicator is a value that determines the signaling protocol to follow during the command execution phase of the Write And Register or Write When Register command. It has the following encoding 

The following processes may be invoked by the coupling facility cache structure commands. The set of processes invoked by a command are listed in the command description.

The signaling protocol for synchronizing command execution across a duplexed pair of cache structures is defined via the following set of processes for duplexed command execution 

These processes are described above in the section on Duplexing Processes and are managed by the signaling protocol engine . In contrast the description of the processes that follows is the view from the structure itself.

A single entry or list form duplexed command process is halted or equivalently completes with a halted condition when a halt signal is recognized but a halt signal has not been issued. If a halt signal has been issued then the duplexed command process completes with the condition that generated the halt signal and any halt signal that may have been received is ignored.

The directory is scanned when a Detach Local Cache Invalidate Complement Copies Invalidate Name or Read Directory command is executed.

The directory scan is controlled by the detachment restart token for the Detach Local Cache command and by the restart token request operand for the Invalidate Complement Copies Invalidate Name and Read Directory commands. A token value of zero starts the processing and a non zero token value restarts the processing from the place designated by the token. Processing is completed when the entire directory has been processed when a model dependent timeout has been exceeded or when the command forces the scan to halt execution. When the end of the directory is reached response code 0 is returned. When a model dependent timeout occurs before the end of the directory is reached the directory position is generated and response code e.g. 1 is returned. When the scan is halted the directory position is generated and the response code determined by the halting condition is returned.

A directory position is a value that designates the location of a directory entry in the cache directory. A directory position is generated when one of the following commands completes with a model dependent timeout or is halted.

When a Detach Local Cache command completes with a model dependent timeout the directory position of the next directory entry to be processed by the directory scan is placed in the detachment restart token in the local cache controls for the local cache that is being detached.

When an Invalidate Complement Copies Invalidate Name or Read Directory command completes with a model dependent timeout or is halted the directory position of the next directory entry to be processed by the directory scan is placed in the restart token response operand.

When the Invalidate Name List or Unlock Castout Locks command completes with a model dependent timeout or is halted the directory position of the directory entry identified by the current list item response operand is placed in the directory position response operand.

When an Invalidate Name List or Unlock Castout Locks command completes processing and the current list item designates a name that is not assigned to the directory and the directory position cannot be determined the directory position is set to zero.

A version number may be updated when a Write And Register or Write When Registered command is executed with the action taken depending on the version request type specified the duplexing state of the structure and the changed state of the data.

When a version request type of B 000 is specified or a version request type of B 100 is specified and version number comparison is successful the version number is updated as follows 

When any of the following conditions holds 1 duplexing is not active for the structure 2 duplexing is active but the command sequence number is zero or 3 duplexing is active the command sequence number is non zero and the data is in the changed state then the version number is not changed. Otherwise the version number is set to the value zero.

When a version request type of B 001 is specified or a version request type of B 101 is specified and version number comparison is successful the version number is updated as follows 

When any of the following conditions holds 1 duplexing is not active for the structure 2 duplexing is active but the command sequence number is zero or 3 duplexing is active the command sequence number is non zero and the data is in the changed state then the version number is decremented by one. Otherwise the version number is set to the value minus one.

When a version request type of B 010 is specified or a version request type of B 110 is specified and version number comparison is successful the version number is updated as follows 

When any of the following conditions holds 1 duplexing is not active for the structure 2 duplexing is active but the command sequence number is zero or 3 duplexing is active the command sequence number is non zero and the data is in the changed state then the version number is incremented by one. Otherwise the version number is set to the value plus one.

When a version request type of B 011 is specified or a version request type of B 111 is specified and version number comparison is successful the version number object is set to the version number request operand.

When duplexing is active for the structure unchanged data is not cached in both structures. However the increment and decrement functions for version numbers rely on the presence of the version number object in the directory entry as preexisting state information. If the data is subsequently written as changed or the castout lock is set the version number object is to be consistent between the two structures when the write operation is performed. Zeroing out the version number before performing the increment or decrement function ensures that the duplexed pair of write commands produce the same value for the version number. It may appear that this defeats the purpose of the version number. However a directory entry with no data or unchanged data may be reclaimed at any time and the reclaim operation destroys the version number. A subsequent write command assigns a new directory entry and performs the increment or decrement operation with an initial object value of zero. This results in a plus one for increment and a minus one for decrement. This is the case whether or not duplexing is active for the structure. So the program i.e. the application owning the structure such as DB2 assumes that version numbers set in directory entries that may be reclaimed may appear to be reset to zero at any time. Forcing the version number to be zero when a duplexed write command is executed for an unchanged directory entry emulates the effect of a reclaim operation.

The data transfer of the data area in the Read For Castout or Read And Register commands is suppressed when the suppress read SR request operand is set to 1. For the Read For Castout command the message buffer size is tested and for the Read And Register command testing of the message buffer size is controlled by the TMBSI request operand. When the TMBSI operand is B 0 no testing is performed. When the TMBSI operand is B 1 the message buffer size is tested. When testing is performed and there is insufficient message buffer space provided the command completes with a response code e.g. 11 .

Using the above assumption for the secondary cache structure the following extensions are made to the behavior of known cache commands. This is described further below.

Allocate Cache Structure Directed allocation which is described in U.S. Patent Applications entitled Method System and Program Products For Modifying Coupling Facility Structure Dahlen et al. Ser. No. 09 379 435 filed Aug. 23 1999 and Directed Allocation Coupling Facility Structures Dahlen et al. Ser. No. 09 378 861 filed Aug. 23 1999 each of which is hereby incorporated herein by reference in its entirety is used to create a secondary structure matching the primary when possible. When the secondary structure is created with less resources than the primary structure the primary structure is altered to match the secondary by trimming the total count objects and releasing any free segments.

Attach Local Cache New connectors are attached in parallel to both structures. When a secondary cache structure is created existing connectors are attached as individual operations. The operating system serializes the connect process so command synchronization is not required. The values of the LCT and LCID are the same in the two structures.

Deallocate Cache Structure When the application requests structure deletion both the primary and secondary caches are deallocated with deallocation occurring in parallel. The operating system serializes the deallocation process so command synchronization is not required. Transitions from duplex mode to simplex mode causes individual Deallocate Cache Structure commands to be issued.

Detach Local Cache The detach is done as a two step process. In the first step a Read Directory command is issued to the primary cache to return all the directory entries which are locked for castout and the LCID in the castout lock is the same as the target of the detach. A UCL command is then issued to both structures using the list form protocol with the returned list from the RD command. The second step is to issue a detach command to each structure as independent processes.

Invalidate Complement Copies The Invalidate Complement Copies ICC command is only issued to the primary structure. The ICC command does not update any objects in the cache structure except for the local cache register and the XICIC STC counter neither of which is maintained in the secondary structure.

Invalidate Name IN The Invalidate Name command is not issued directly using the duplexing protocol. The Invalidate Name command scans the directory and deletes directory entries as they are encountered for a model dependent time period. If duplexed the commands would be the two separate directories in an independent fashion and there is no method to ensure that the directory updates are coordinated. So it would be inevitable that the two directories would be out of synchronization for periods of time. This is not permitted by the design and therefore the IN command is converted into a Read Directory command issued to the primary followed by an Invalidate Name List command issued to both structures using the list form duplexing protocol. On completion the restart token generated by the Read Directory command is returned to the issuer for use on redrive of the IN command.

Invalidate Name List The Invalidate Name List is sent to both structures and the multi command protocol is used to synchronize execution on a list item basis. The command may be a direct request from the list structure user or may be the conversion of an invalidate name request. When the command is a converted Invalidate Name IN command the message buffer address list MBAL for the Send Message instruction associated with the INL command designates the data block returned by the Read Directory RD command. The formats of the list entries are identical between the commands and do not need to be reformatted. When a halting condition is requested it is set on the command sent to the primary and not set on the command sent to the secondary. The list form protocol halts both commands when a proper halting event is encountered.

Process Reference List The process reference list command is only issued to the primary structure. Reference ordering is not maintained in the secondary.

Read and Register Normal read and register requests are only sent to the primary cache structure since the only directory objects that are updated are registration controls reference bits and storage class counters that are not maintained in the secondary cache. However in some circumstances the storage class which is maintained in the secondary cache can be changed by the Read And Register RAR command. So the processing for RAR is optimistically sent to the primary only but the Read And Register RAR command is issued with a new request operand that tests the storage class. If the storage class would be changed by the command the command is completed with a new response code and no other action occurs. The program then reissues the RAR command to both the primary and secondary structures using a single entry duplexing protocol to control the execution.

Read Castout Class Information Castout operations are driven off of information in the primary structure.

Read Directory The reference bit does not need to be set in the secondary since the reference order is not maintained. A new control is added that requests that only directory entries that are locked for castout with a specified LCID value are returned. A new control is added that modifies the output of a name block so that it is compatible with the input list on a UCL command.

Read For Castout Castout locks are set in both the primary and secondary structures. The local cache entry registration control LCERC and name replacement control NRC are set to zero in the command sent to the secondary cache. The only objects updated in the secondary cache are the castout lock the castout count COC storage class STC counter and the castout class controls.

Register Name List Since registrations are not maintained in the secondary cache structure the Register Name List command is only sent to the primary cache structure.

Set Reclaiming Vector The reclaiming vector remains inactive in the secondary cache until it is promoted to being the primary. At this point the reclaiming vector may be activated. However the contents of the old reclaiming vector in the primary structure has little meaning in the secondary structure. There is a period of time where the references to the secondary cache structure stabilize anyway since they do not contain unchanged data until the structure is promoted.

Unlock Castout Lock Entry The Unlock Castout Lock Entry command is issued to both structures using the single entry duplexing protocol. A new control is added that requests immediate reclaim when the change bit is zero. The control is set on the command sent to the secondary.

Unlock Castout Locks The Unlock Castout Locks command is issued to both structures using the list form duplexing protocol. A new control is added that requests immediate reclaim when the change bit is zero. The control is set on the command sent to the secondary.

Write and Register WAR When the change control is one or the operation is write with castout the Write And Register command is issued to both structures using the single entry duplexing protocol. When the change control is zero and the operation is not write with castout the WAR command is only issued to the primary structure. The command sent to the secondary structure has the NRC set to zero. When either the primary or secondary structure encounters a target storage class full condition a halt signal is sent. This occurs in the secondary structure when either free list is exhausted and the write cannot complete. Since registrations are not maintained in the secondary no XI signals are generated.

Write When Registered WWR When the change control is one or the operation is write with castout the Write When Registered command is issued to both structures using the single entry duplexing protocol. When the change control is zero and the operation is not write with castout the WWR command is only issued to the primary structure. A new option is added to the WWR command to suppress the registration check. When either the primary or secondary structure encounters a target storage class full condition a halt signal is sent. This occurs in the secondary structure when either free list is exhausted and the write cannot complete. Since registrations are not maintained in the secondary no XI signals are generated.

Similar to cache structures each list structure has its own operands that are associated with the list when it is created. Examples of these operands are described below.

Comparative Structure Authority CSAU A value used as a comparison value to the structure authority when the structure is allocated and deallocated or when lock table entries are written or list entries are deleted and the compare structure authorities control is one. This operand is ignored on a Delete List or Write Lock Table Entry command when duplexing is inactive.

Comparative Remote Facility Structure Authority CRFSAU A value used as a comparison value to the remote facility structure authority when lock table entries are written or list entries are deleted and the compare structure authorities control is one. This operand is ignored on a Delete List or Write Lock Table Entry command when duplexing is inactive.

Compare Structure Authorities Control CSAUC A value that controls the comparison of the structure authority and remote structure authority controls to the CSAU and CRFSAU operands on a Delete List Entries or Write Lock Table Entry command. It has the following encoding 

Command Sequence Number CSN A value associated with a command that is duplexed. List structure commands that specify a non zero value in the CSN request operand cause the invocation of the duplexing command process when duplexing is active for the structure. Commands that do not have the CSN request operand defined or which specify a zero value in the CSN request operand do not invoke the duplexing command process.

Duplexing Active Indicator DUPAI A value that controls execution of the command based on the duplexing state of the structure. It has the following encoding 

Duplexing Signal Group Index DSGX A value that identifies the target signal group in the signaling vector entry identified by the duplexing retry index and the remote facility controls. If duplexing is active and the command sequence number is non zero the duplexing signal group index is non zero. If duplexing is not active for the structure or if the command sequence number is zero the operand is ignored.

Duplexing Retry Index DRX A value that designates a signaling vector entry for the signaling vector identified by the remote facility controls. If duplexing is active and the command sequence number is non zero the duplexing retry index is non zero. If duplexing is not active for the structure or if the command sequence number is zero the operand is ignored.

Failed Structure Indicator FSI A value that controls the state change for the structure that occurs when a Deallocate List Structure command is executed and the structure is in the allocated state. It has the following encoding 

EMC Restart Token ERT A value that determines at which EMC the Read Event Monitor Control List command restarts reading or the Queue Pending EMCs QPE command described hereinafter restarts scanning. Invalid values for the EMC restart token are model dependent.

Starting List Number SLN A value that specifies the starting list number for the Read Event Monitor Controls List or Queue Pending EMCs command. The SLN is invalid if it is greater than or equal to the list count or greater than the ending list number.

Ending list number ELN A value that specifies the ending list number for the Read Event Monitor Controls List REMCL or Queue Pending EMCs QPE command. For the REMCL command the ELN is invalid if it is greater than or equal to the list count or less than the starting list number. For the QPE command any value for the ELN operand is valid.

Intermediate Controls Returned on Timeout Control ICRTOC A value that controls the completion processing of a Delete List Entries command when a model dependent timeout is recognized. The two possible values are 

This operand is ignored unless the skip nonexistent entries control SNEC described below and list number comparison type LNCT operands are both B 1 .

List Form Duplexing Completion Code LFDCC The list form duplexing completion code is a value that specifies the reason a list form duplexing process was stopped with a model dependent timeout when one or more list items have been processed. It has the following encoding 

Read LEIDs Indicator RLEIDI A value that indicates whether the data block contains a list of LEIDs or contains the information specified by the RLT request operand. It has the following encoding 

Retry Index RX A value that designates a retry buffer and a signaling vector entry. An RX of zero indicates that the retry buffer should not be written. If the retry index is non zero and the command is among the list of commands in the process for writing the retry buffer the retry buffer is written. Valid RXs are zero and assigned RXs within the range of one to the RX limit. If duplexing is active and the command sequence number is non zero the retry index is non zero.

Skip Nonexistent Entries Control SNEC A value that controls the halting of a Delete List Entries command when a list item specifies a list entry that does not exist. It has the following encoding 

Suppress Notification Control SNC A value that controls the sending of list notification commands when a list state transition key range transition or event queue state transition occurs and controls both the queuing and withdrawing of EMCs when a subsidiary list state transition occurs. It has the following encoding 

Suppress Read SR A value that indicates the data transfer for a read command is suppressed but the data list entry is written to the retry buffer.

The following processes may be invoked by the list structure commands. The set of processes invoked by a command are listed in the command description.

The signaling protocol for synchronizing command execution across a duplexed pair of list structures is defined via the following set of processes for duplexed command execution 

These processes are described in the section on duplexing signals and are managed by the signaling protocol engine . In contrast the description of the processes that follows is the view from the structure itself.

Writing the Retry Buffer The following commands update the contents of the specified retry buffer when the retry buffer is assigned 

When the retry index is zero no retry buffer is updated. When the retry index is non zero the retry version number request operand and the response operands except for the response descriptor are stored in the retry information portion of the retry buffer specified by the retry index. When the retry index is non zero and a data list entry is read or when the list entry type specifies reading the data list entry but the suppress read operand is b 1 the data list entry is also stored in the retry data block portion of the retry buffer specified by the retry index.

The duplexing deactivated indicator is copied from bit of word 2 in the response descriptor to bit of word 1 of the retry information.

When the command is terminated suppressed or completed such that the completion appears the same as suppression except that an MRB may be returned the retry buffer may or may not be updated.

Halting a Duplexed Command Process A single entry or list form duplexed command process is halted or equivalently completes with a halted condition when a halt signal is recognized but a halt signal has not been issued. If a halt signal has been issued then the duplexed command process completes with the condition that generated the halt signal and any halt signal that may have been received is ignored.

Scanning a List Set The list set is scanned when a Delete List Set or Read List Set command is executed. The list set scan is controlled by the restart token request operand. A token value of zero starts the processing and a non zero token value restarts the processing from the place designated by the token. Processing is completed when the entire list set has been processed when a model dependent timeout has been exceeded or when the command forces the scan to halt execution. When the end of the list set is reached response code 0 is returned. When a model dependent timeout occurs before the end of the directory is reached the list set position is generated and response code 1 is returned. When the scan is halted the list set position is generated and the response code determined by the halting condition is returned.

Generating a List Set Position A list set position is a value that designates the location of a list entry in the list set. A list set position is generated when one of the following commands completes with a model dependent timeout or is halted 

When a Delete List Set or Read List Set command completes with a model dependent timeout or is halted the list set position of the next list entry to be processed by the list set scan is placed in the restart token response operand.

When the Delete List Entries command completes with a model dependent timeout or is halted the list set position of the list entry identified by the current data index response operand is placed in the list set position response operand.

When a Delete List Entries command completes processing and the current data index designates a list entry that does not exist and the list set position cannot be determined the list set position is set to zero.

The data transfer of the data area in the Read List Entry Move And Read List Entry Read And Delete List Entry commands is suppressed when the SR request operand is set to 1. However the message buffer size is still tested to see if sufficient message buffer space is provided for returning the data area. If there is insufficient message buffer space provided the command completes with a response code e.g. 11 . Additionally the data list entry is moved to the retry data block portion of the retry buffer specified by the retry index.

In one embodiment the primary and secondary list structure are kept in synchronization with the exception of the event queues. The secondary list appears to be a duplicate of the primary list except for event queues . This requires that virtually every command be duplexed and synchronized including some read commands.

The event queues are only maintained in this example in the primary structure. However the key structures in the secondary list include all the state information employed to restore the event queues on failover. This is done by the LFSS issuing a QPE command described herein to the secondary during the failover process.

Allocate List Structure Directed allocation which is described in U.S. Patent Applications entitled Method System and Program Products For Modifying Coupling Facility Structure Dahlen et al. Ser. No. 09 379 435 filed Aug. 23 1999 and Directed Allocation Coupling Facility Structures Dahlen et al. Ser. No. 09 378 861 filed Aug. 23 1999 each of which is hereby incorporate herein by reference in its entirety is used to create a secondary structure matching the primary when possible. When the secondary structure is created with less resources than the primary structure the primary structure is altered to match the secondary by trimming the total count objects and releasing any free segments.

Attach List Structure User New connectors are attached in parallel to both structures. When a secondary list structure is created existing connectors are attached as individual operations. The operating system serializes the connect process so command synchronization is not required. The values of the LNT and UID are the same in the two structures.

Cleanup Lock Table Entries A disconnect causes Cleanup Lock Table Entries commands to be issued in parallel to both structures. The operating system serializes the disconnect process so a duplexing protocol to ensure synchronization is not required. Issuing the cleanup separately implies that the resetting of the lock table entries is not synchronized between the structures. This is acceptable since the user connection has been invalidated and thus no new lock commands will be processed for this UID.

The following commands are issued to both structures using the single entry duplexing protocol to control their execution 

The following commands are issued to both structures using the list form duplexing protocol to control their execution 

Clear Lock Table This command is used when the last connector disconnects and the structure is persistent. Since all activity to the structure has ceased the command can be issued independently to the two structures without duplexing controls.

Deallocate List Structure When the application requests structure deletion both the primary and secondary lists are deallocated with deallocation occurring in parallel. The operating system serializes the deallocation process so command synchronization is not required. Transitions from duplex mode to simplex mode will cause individual Deallocate List Structure commands to be issued.

Delete List Delete list DL is converted into a Read List command issued to the primary followed by a Delete List Entries command issued to both structures with the list form duplexing protocol. On completion the restart token generated by the Read List command is returned to the issuer for use on redrive of the DL command.

Delete List Entries The command may be a direct list structure user request or may be the conversion of a delete list set request. A control suppresses LNs in the secondary. The format of the data block matches the format for the Read List Set command.

Delete List Set The DLS command is converted into a Read List Set command issued to the primary followed by a Delete List Entries command issued to both structures with the list form duplexing protocol. On completion the restart token generated by the Read List Set command is returned to the issuer for use on redrive of the DLS command.

Dequeue Event Monitor Controls DEMC The DEMC command is converted into a Read EMC List command issued to the primary followed by a Dequeue EMC List command issued to both structures with the list form duplexing protocol.

Dequeue Event Monitor Controls List A list form of the DEMC command is used to synchronize the dequeue operations. The data block format matches the format for the Read EMC List command.

One example of the request operands provided in the message command block for the QPE command are summarized in the following table.

In execution of one embodiment of the QPE command if the value of the event monitor controls count object is zero the command is completed and a response code e.g. 0 is returned. Otherwise the event monitor controls within the list set are scanned starting with the starting list number or the EMC restart token until a model dependent time period elapses or the last event monitor control is scanned. A zero EMC restart token causes the entire list to be processed starting at the start list number operand. A valid non zero EMC restart token starts the processing at the event monitor control object designated by the EMC restart token.

The EMCs are scanned starting with the starting list number then in ascending order by LN up to either the ending list number or to one less than the list count whichever is smaller. The EMCs in a list number are scanned in an unpredictable ordering for keys and an unpredictable ordering for UIDs within a key value.

The event monitor controls in the list set are processed by queueing each EMC that is queue pending to the corresponding event queue and by withdrawing each EMC that is withdrawal pending from the corresponding event queue. If this causes event queue transitions the event queue monitors are notified. The queueing or withdrawing of event monitor controls and the generated list notification commands are primary processes.

The list set scan ensures that any EMC that is queue pending or withdraw pending when the scan is initiated and remains queue pending or withdraw pending throughout the scan is queued to or withdrawn from the event queue as appropriate.

When a model dependent time period has elapsed the list set position for the next EMC to be processed is generated and placed in the EMC restart token response operand. The EMC restart token and a response code e.g. 1 are returned.

Detach List Structure User A disconnect causes Detach List Structure User commands to be issued in parallel to both structures. The operating system serializes the disconnect process so command synchronization is not required. Issuing the detach separately implies that the dequeuing of the EMCs is not synchronized between the structures. This is acceptable since the user connection has been invalidated and thus no new EMCs will be queued for this UID.

Read List Structure Controls Depending on how structure information is reported the information may only be obtained from the primary structure or obtained in an independent fashion.

Read User Controls While the LNT US and SYID are the same between the structures the User Authority UAU and user attachment control UAC may be different.

Described in detail above is a capability that allows coupling facilities to be coupled to one another via for instance a peer link. The coupling of the facilities allows many functions to be employed including the duplexing of structures. Although duplexing is described above the coupling of the facilities can be for reasons other than duplexing.

The duplexing of structures results in two structures being created in two different coupling facilities. In one example the coupling facilities are failure isolated so that the failure of one does not affect the other.

While both cache and list including lock structures can be duplexed the information that is duplexed is different for the different types of structures as described herein. In other embodiments however other information may or may not be duplexed.

Although in the embodiments described herein the duplexing results in two structures of two coupling facilities this can be extended to a plurality of structures in a plurality of coupling facilities.

In the embodiments described above various objects controls and operands are described. These are only examples. There may be more less or different objects controls and or operands. Further in some examples the values of a bit or response code may be provided. Again these values are only examples. Any other values may be used. Moreover in the various control flows various tests are performed. These are only examples. Tests may be added or deleted depending on the Sysplex. For example if dumping serialization is not a part of the Sysplex then the tests associated with dumping serialization can be eliminated. The same is true for other tests.

Many advantages are provided by the various aspects of the present invention. Examples of these advantages are described below 

In addition to the above advantages the following is provided as a summary of various aspects of the present invention.

In order to duplex coupling facility structures and commands against those structures an efficient means for the two coupling facilities participating in duplexing is provided to synchronize their command processing for a particular duplexed operation against a particular duplexed structure. Duplexed coupling facility commands execute in harmony between the two coupling facilities in a way which preserves properties of command atomicity concurrency guaranteed by the coupling facility command architecture for simplex structures. Both commands either complete or back out in the two coupling facilities. In this context a highly efficient means of signaling between the two coupling facilities to communicate status of processing of the request is employed.

In one example the mechanism is based on an application of the existing List Notification LN mechanism that coupling facilities use today to communicate status information to the attached operating systems. Here this mechanism is used for coupling facility to coupling facility communication.

An architected encoding of the list notification entry number LNEN for use in coupling facility to coupling facility signaling provides five signal types 

As described herein in one embodiment the use of three entries per vector index in a round robin pattern CSGX cursor reduces the serialization and recovery design of lost or delayed signals.

Use of the retry index provides for an automatic mechanism for assigning signaling vector entries. A second serialization protocol among the Sysplex members is avoided.

Use of existing message facility mechanisms simplifies the design and does not require a new storage allocation process for the vectors.

In a further aspect read secondary processing is provided which allows the software to retrieve the data on a read command from the secondary structure after an IFCC results in the data not being read from the primary structure. Even though the read of the data was suppressed on the duplexed read command to the secondary the data was staged into a retry buffer so that it could be retrieved in the event of such a failure.

A new global coupling facility object the Duplexing Active vector is defined. It is a parallel structure to the SID vector and is likewise indexed by the Structure Identifier SID operand. Each bit in the Duplexing Active vector corresponds to the current duplexing state of the corresponding structure the state of the bit therefore serves to control command execution in duplex versus simplex mode for each structure in the coupling facility of course at a finer level of granularity individual coupling facility commands executed against a duplexed structure may be executed either as simplex commands or duplexed commands .

This structure provides a number of functions employed by the duplexing architecture model and it provides a number of distinct advantages for the overall duplexing framework 

In further aspects of the invention other architectural extensions and processing optimizations have been added to the coupling facility command architecture in support of coupling facility duplexing. Many of these are intrinsic to the basic single entry and list form duplexing processes themselves in order to enable the duplexed structure objects to be updated consistently and maintained in a synchronized state indefinitely. Many others enhance the support by contributing to the robustness transparency manageability and performance efficiency of the coupling facility duplexing processes and protocols.

The present invention can be included in an article of manufacture e.g. one or more computer program products having for instance computer usable media. The media has embodied therein for instance computer readable program code means for providing and facilitating the capabilities of the present invention. The article of manufacture can be included as a part of a computer system or sold separately.

Additionally at least one program storage device readable by a machine tangibly embodying at least one program of instructions executable by the machine to perform the capabilities of the present invention can be provided.

The flow diagrams depicted herein are just examples. There may be many variations to these diagrams or the steps or operations described therein without departing from the spirit of the invention. For instance the steps may be performed in a differing order or steps may be added deleted or modified. All of these variations are considered a part of the claimed invention.

Although preferred embodiments have been depicted and described in detail herein it will be apparent to those skilled in the relevant art that various modifications additions substitutions and the like can be made without departing from the spirit of the invention and these are therefore considered to be within the scope of the invention as defined in the following claims.

