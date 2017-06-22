---

title: Method and apparatus for using unspecialized software micro-containers for building complex dynamic business processes
abstract: One embodiment of the present invention provides a system that facilitates using unspecialized software micro-containers to build complex dynamic business processes. During operation, the system receives a command to execute a business logic at a computer system. In response to the command, the system initializes an unspecialized software micro-container from a pool of unspecialized software micro-containers. Next, the system retrieves the business logic from a business logic repository. The system then loads the business logic into the unspecialized software micro-container. Finally, the system executes the business logic in the unspecialized software micro-container. Note that the requestor publishes the desired business process in the repository, and the system, represented by the unspecialized containers, self-organizes to execute the job without additional management.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09047157&OS=09047157&RS=09047157
owner: INTUIT INC.
number: 09047157
owner_city: Mountain View
owner_country: US
publication_date: 20120127
---
Many organizations utilize multiple computing systems to manage their information and processes. For example it is not uncommon for an organization to have a customer resource application an accounting application a personal information management system etc. While each one of these systems adds value to the organization it can be difficult for the organization to manage multiple disparate systems especially when they may contain overlapping datasets. Because of this many organizations deploy integration solutions that connect these disparate systems and allow for seamless workflows and reporting across these systems. However this integration is not without its problems.

The integration processes built with conventional tools i.e. Business Process Execution Language BPEL Enterprise Service Bus ESB integration Java solutions etc. are static by nature. Extensive development and testing is required when a new process is developed and deployed or an existing process is modified. In addition such processes are difficult to scale because the resources allocated for the execution of such processes are again static and incapable of addressing sudden surges in demand.

One embodiment of the present invention provides a system that facilitates using unspecialized software micro containers to build complex dynamic business processes. During operation the system receives a command to execute a business logic at a computer system. In response to the command the system initializes an unspecialized software micro container from a pool of unspecialized software micro containers. Next the system retrieves the business logic from a business logic repository. The system then loads the business logic into the unspecialized software micro container. Finally the system executes the business logic in the unspecialized software micro container.

For example in one embodiment the system receives a request to execute a business process. The system then publishes the required business process steps into a repository. The available unspecialized micro containers as part of the system proactively reading the repository looking for a specialization identify an available step in a business process get the business logic required for this step again from the repository and execute this step.

Note that the requestor publishes the desired business process in the repository and the system represented by the unspecialized containers self organizes to execute the job without additional management.

In some embodiments of the present invention retrieving the business logic from the business logic repository involves retrieving the business logic from a predetermined Uniform Resource Locator URL .

In some embodiments of the present invention the system unloads the business logic and returns the unspecialized software micro container to the pool of unspecialized software micro containers.

In some embodiments of the present invention the operations of unloading the business logic and returning the unspecialized software micro container to the pool of unspecialized software micro containers are performed when a pre determined criterion is met.

In some embodiments of the present invention the operations of unloading the business logic and returning the unspecialized software micro container to the pool of unspecialized software micro containers are performed at a pre determined time.

In some embodiments of the present invention receiving the command to execute the business logic involves receiving the command from a user.

In some embodiments of the present invention receiving the command to execute the business logic involves receiving the command from a computer implemented controller.

In some embodiments of the present invention receiving the command from the computer implemented controller involves receiving the command when a pre determined criterion is met.

In some embodiments of the present invention receiving the command from the computer implemented controller involves receiving the command at a pre determined time.

In some embodiments of the present invention the unspecialized software micro container is an Extensible Stylesheet Language Transformations XSLT container.

In some embodiments of the present invention the unspecialized software micro container is a scripting language container.

The following description is presented to enable any person skilled in the art to make and use the invention and is provided in the context of a particular application and its requirements. Various modifications to the disclosed embodiments will be readily apparent to those skilled in the art and the general principles defined herein may be applied to other embodiments and applications without departing from the spirit and scope of the present invention. Thus the present invention is not limited to the embodiments shown but is to be accorded the widest scope consistent with the principles and features disclosed herein.

The data structures and code described in this detailed description are typically stored on a non transitory computer readable storage medium which may be any device or medium that can store code and or data for use by a computer system. The non transitory computer readable storage medium includes but is not limited to volatile memory non volatile memory magnetic and optical storage devices such as disk drives magnetic tape CDs compact discs DVDs digital versatile discs or digital video discs or other media capable of storing code and or data now known or later developed. Note that the term non transitory computer readable storage medium comprises all computer readable media with the sole exception of a propagating electromagnetic signal.

The methods and processes described in the detailed description section can be embodied as code and or data which can be stored on a non transitory computer readable storage medium as described above. When a computer system reads and executes the code and or data stored on the non transitory computer readable storage medium the computer system performs the methods and processes embodied as data structures and code and stored within the non transitory computer readable storage medium.

Furthermore the methods and processes described below can be included in hardware modules. For example the hardware modules can include but are not limited to application specific integrated circuit ASIC chips field programmable gate arrays FPGAs and other programmable logic devices now known or later developed. When the hardware modules are activated the hardware modules perform the methods and processes included within the hardware modules.

One embodiment of the present invention provides a system that facilitates using unspecialized software micro containers to build complex dynamic business processes. During operation the system receives a command to execute a business logic at a computer system. In response to the command the system initializes an unspecialized software micro container from a pool of unspecialized software micro containers. Next the system retrieves the business logic from a business logic repository. The system then loads the business logic into the unspecialized software micro container. Finally the system executes the business logic in the unspecialized software micro container.

The unspecialized software micro containers have a behavior similar to that of stem cells in biology. The unspecialized software micro containers have no specific function initially. However they are capable of interpreting signals from the environment and fulfilling specific functions when required. This may include becoming a component in a new business process or helping when more resources are needed for an existing business process. Essentially an unspecialized software micro container can become a content based router transformer content enricher content filter etc.

In some embodiments of the present invention retrieving the business logic from the business logic repository involves retrieving the business logic from a predetermined Uniform Resource Locator URL . Note that while some of the examples below discuss retrieving the business logic from a predetermined URL other methods of identifying a location for the business logic may be used.

In some embodiments of the present invention the system unloads the business logic and returns the unspecialized software micro container to the pool of unspecialized software micro containers. Once the business logic is unloaded the unspecialized software micro container is available for a subsequent use.

In some embodiments of the present invention the operations of unloading the business logic and returning the unspecialized software micro container to the pool of unspecialized software micro containers are performed when a pre determined criterion is met. For example if the unspecialized software micro container was initialized with business logic to help alleviate a transaction bottleneck in a sales system once the number of transactions per minute fall below a certain threshold the unspecialized software micro container may no longer be needed and may be returned to the unspecialized software micro container pool.

In some embodiments of the present invention the operations of unloading the business logic and returning the unspecialized software micro container to the pool of unspecialized software micro containers are performed at a pre determined time. For example the unspecialized software micro container may be unloaded and returned to the unspecialized software micro container pool at a specific time such as at the end of a business day or after a certain amount of time has elapsed since the unspecialized software micro container s initialization.

In some embodiments of the present invention receiving the command to execute the business logic involves receiving the command from a user. In many instances users manipulate the business processes either adding or removing processes or changing the resources available to the business processes. For example in anticipation of an event or product rollout additional business processes may be initiated to handle the anticipated increase in demand.

In some embodiments of the present invention receiving the command to execute the business logic involves receiving the command from a computer implemented controller. For example a computer implemented controller that is monitoring system resources and existing business processes can activate additional business processes to cope with shifting demands on the computer system. This is described in more detail below.

In some embodiments of the present invention receiving the command from the computer implemented controller involves receiving the command when a pre determined criterion is met such as when a CPU utilization is too high or there is a sufficiently large backlog in a transaction queue.

In some embodiments of the present invention receiving the command from the computer implemented controller involves receiving the command at a pre determined time for example just prior to the release of a new product or service or at the beginning of a work day .

In some embodiments of the present invention the unspecialized software micro container is an Extensible Stylesheet Language Transformations XSLT container while in other embodiments the unspecialized software micro container is a scripting language container. Note that while the examples herein refer to XSLT any programming or scripting language may be used to implement embodiments of the present invention.

In a set of containers form a business process in a first use case. In this use case a new transformation enrichment action needs to be added to this existing business process.

In the resource management process replaces the configuration of one of the non specialized containers in the micro containers set. If required the resource management process makes changes to the configuration of the containers participating in the process so they can accommodate the new member and enhance the process sequence and logic.

In a second use case is presented wherein a new non existing business process is required. illustrates the second use case as the system exists prior to adding the new non existing business process.

In the resource management process replaces the configuration of the unspecialized micro containers in the repository and forms the new business process.

The techniques utilized to implement both of these use cases are described in more detail below. In the exemplary embodiment the system comprises the following components each of which will be described in more detail below A pool of unspecialized software micro containers proactively looking for specialization a repository component that stores configuration resources and a resource management process that manages the configuration in the repository thereby controlling the specialization of the software micro containers.

The unspecialized software micro container is the main component and has the following characteristics the ability to interpret and execute a relatively simple business logic and perform a relatively simple business function and the ability to proactively search for and interpret specializing configuration and business logic from a dedicated resource URL. Note that the specialization happens when the configuration resource referenced by the dedicated URL is modified with specialization instructions that can be interpreted and followed by the software micro container.

In terms of complexity the software micro containers are somewhere between a completely generic container solution such as a Linux or Solaris virtual container and a completely specialized container solution such as a specific application deployed in a container. A software micro container can fulfill a more generic role or a role within a category. For example the software micro container may be defined as a generic transformer that receives a message from a queue transforms or enriches the message and sends the message to another queue. The sequence of actions can be defined however the source queue the transformation file and the destination queue can be provided in the REST configuration and injected through the repository.

After fulfilling a specialization role the software micro containers can be released and become unspecialized again and can continue to look proactively for a new task.

In one embodiment of the present invention an unspecialized software micro container developed in XSLT for use in a DataPower device might have the following configuration resource 

The repository component holds the configuration of the individual software micro containers and provides the configuration when requested. A URL uniquely identifies each configuration. The repository provides a REST type of interface to the managed resources. Note that the repository can be implemented with a simple Web Apache cluster or with a more sophisticated repository solution as long as the repository provides a REST interface.

The resource management process takes care of managing the configuration in the repository and subsequently controls the specialization of the software micro containers. The resource management can be a human process of building the right sequence of steps or an automatic process that watches for certain threshold values i.e. too many messages in a queue CPU utilization is too high etc. and instructs the specialization of more containers. In some embodiments the resource management process is a combination of an automatic process and human input to account for unusual or unexpected events.

In another exemplary embodiment the system also includes a work distribution message board. The work distribution message board by intent resembles a plain job posting board. In human society when an individual applies for a job usually her background and past experience are considered for a certain position. With the work distribution message board a worker container goes to a special location message board URL and presents a current specialization identified by a resource URL . Based on the current container specialization the message board returns a new specialization resource to the container or declares that there is no proper assignment at the moment and orders the worker container to check again later.

Note that in this embodiment a worker container is an unspecialized software micro container that has both the ability to interpret and execute a relatively simple business logic and perform a relatively simple business function and the ability to proactively search for and interpret specializing configuration and business logic from a work distribution message board identified by a dedicated resource URL.

Clients can include any node on a network including computational capability and including a mechanism for communicating across the network. Additionally clients may comprise a tier in an n tier application architecture wherein clients perform as servers servicing requests from lower tiers or users and wherein clients perform as clients forwarding the requests to a higher tier .

Similarly servers can generally include any node on a network including a mechanism for servicing requests from a client for computational and or data storage resources. Servers can participate in an advanced computing cluster or can act as stand alone servers. In one embodiment of the present invention server is an online hot spare of server .

Users and can include an individual a group of individuals an organization a group of organizations a computing system a group of computing systems or any other entity that can interact with computing environment .

Network can include any type of wired or wireless communication channel capable of coupling together computing nodes. This includes but is not limited to a local area network a wide area network or a combination of networks. In one embodiment of the present invention network includes the Internet. In some embodiments of the present invention network includes phone and cellular phone networks.

Database can include any type of system for storing data in non volatile storage. This includes but is not limited to systems based upon magnetic optical or magneto optical storage devices as well as storage devices based on flash memory and or battery backed up memory. Note that database can be coupled to a server such as server to a client or directly to a network.

Devices can include any type of electronic device that can be coupled to a client such as client . This includes but is not limited to cell phones personal digital assistants PDAs smartphones personal music players such as MP3 players gaming systems digital cameras video cameras portable storage media or any other device that can be coupled to the client. Note that in some embodiments of the present invention devices can be coupled directly to network and can function in the same manner as clients .

Appliance can include any type of appliance that can be coupled to network . This includes but is not limited to routers switches load balancers network accelerators and specialty processors. Appliance may act as a gateway a proxy or a translator between server and network .

Note that different embodiments of the present invention may use different system configurations and are not limited to the system configuration illustrated in computing environment . In general any device that is capable of communicating via network may incorporate elements of the present invention.

During operation receiving mechanism receives a command to execute a business logic operation . Note that this command can be received from an automated process executing on system or may come from a user such as user . In response to the command initialization mechanism initializes an unspecialized software micro container from a pool of unspecialized software micro containers operation . Next retrieval mechanism retrieves the business logic from a business logic repository operation . Loading mechanism then loads the business logic into the unspecialized software micro container operation . Next execution mechanism executes the business logic in the unspecialized software micro container operation . Note that the business logic may be executed until a specified amount of time has elapsed until a detectable condition is met until execution is cancelled by user or until the business logic has reached a natural execution endpoint. Finally initialization mechanism unloads the business logic and returns the now unspecialized software micro container to the unspecialized software micro container pool operation .

The foregoing descriptions of embodiments of the present invention have been presented only for purposes of illustration and description. They are not intended to be exhaustive or to limit the present invention to the forms disclosed. Accordingly many modifications and variations will be apparent to practitioners skilled in the art. Additionally the above disclosure is not intended to limit the present invention. The scope of the present invention is defined by the appended claims.

