---

title: Multi-RPO data protection
abstract: A system for disaster recovery including a controller (i) for controlling bandwidth usage of a disaster recovery system in accordance with a plurality of recovery point objectives (RPOs), each RPO designating a maximal time loss constraint for data recovery for an enterprise production system, and a corresponding bandwidth allocation for the disaster recovery system to use in replicating data for the enterprise production system, wherein the RPOs are applied in accordance with a calendar-based schedule of dates and times, and (ii) for issuing an RPO alert when the RPO maximal time loss constraint for a current date and time is not satisfied.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09442748&OS=09442748&RS=09442748
owner: ZERTO, LTD.
number: 09442748
owner_city: Herzilya
owner_country: IL
publication_date: 20120207
---
This application is a continuation in part of U.S. application Ser. No. 13 175 898 entitled METHODS AND APPARATUS FOR PROVIDING HYPERVISOR LEVEL DATA SERVICES FOR SERVER VIRTUALIZATION filed on Jul. 4 2011 by inventors Ziv Kedem Gil Levonai Yair Kuszpet and Chen Burshan which is a continuation in part of U.S. application Ser. No. 13 039 446 entitled METHODS AND APPARATUS FOR PROVIDING HYPERVISOR LEVEL DATA SERVICES FOR SERVER VIRTUALIZATION filed on Mar. 3 2011 by inventor Ziv Kedem which claims priority benefit of U.S. Provisional Application No. 61 314 589 entitled METHODS AND APPARATUS FOR PROVIDING HYPERVISOR LEVEL DATA SERVICES FOR SERVER VIRTUALIZATION filed on Mar. 17 2010 by inventor Ziv Kedem.

Data is at the heart of every enterprise and a core component of data center infrastructure. As data applications become more and more critical there is a growing need to ensure complete business continuity.

Disaster recovery systems provide data protection and application recovery. Some disaster recovery systems use virtual data replication within a hypervisor architecture and are able to recover any point in time.

Objectives of disaster recovery plans are generally formulated in terms of recovery point objective RPO and recovery time objective RTO .

RPO is a point in time to which data must be recovered. RPO indicates an amount of data that an enterprise determines is an acceptable loss in a disaster situation. RPO allows an enterprise to define a window of time before a disaster during which data may be lost. The value of the data in this window of time may be weighed against the cost of the additional disaster prevention measures that would be necessary to shorten the window.

RTO is the time it takes to get a non functional system back on line and indicates how fast the enterprise will be up and running after a disaster. Specifically RTO is the duration of time within which a business process must be restored after a disaster in order to avoid unacceptable consequences associated with a break in business continuity. Most disaster recovery systems provide RTOs on the order of several hours.

RPO is independent of RTO. If the RPO of an enterprise is two hours then when a system is brought back on line after a disaster all data must be restored to a point within two hours before the disaster. But the enterprise has acknowledged that data in the two hours immediately preceding the disaster may be lost i.e. the acceptable loss window is two hours.

Conventional disaster recovery systems are single RPO systems i.e. a single RPO objective applies. In this regard reference is made to which is a screen shot of a prior art single RPO console for a disaster recovery application. As shown in a single RPO objective designates an RPO threshold time of 2 minutes and a maintenance history of 4 hours.

An enterprise may share its overall bandwidth between its actual production system and its disaster recovery system. A RPO may be controlled by the amount of bandwidth of the overall enterprise system allocated to the disaster recovery system. By allocating more bandwidth to the disaster recovery system the RPO may be improved to reduce the window of data loss in case of disaster but less bandwidth is then available for the enterprise production system. Conversely by allocating less bandwidth to the disaster recovery system the RPO is degraded to increase the window of data loss in case of disaster and more bandwidth is then available for the enterprise production system.

When a disaster recovery system falls short of its RPO objective it issues an RPO alert. If an administrator receives a series of RPO alerts it generally means that the bandwidth allocated to the disaster recovery system is insufficient for the RPO objective and the RPO objective must be relaxed or additional bandwidth must be allocated. Generally allocating additional bandwidth to the disaster recovery system entails the expense of obtaining additional bandwidth for the overall enterprise system in order not to degrade the enterprise production system.

Enterprise production systems generate data at varying rates according to peaks times and off peak times. Peak times and off peak times may be different for different applications. E.g. a customer relationship management CRM application may have peak times during normal working hours and off peak times during nights and weekends whereas a fast food ordering system may have peak hours during nights and weekends. Maintaining a low RPO at all times requires a WAN link with a bandwidth that accommodates the peak rates. Such lines are expensive and are fully utilized only during relatively short time periods.

Cloud service disaster recovery systems support multiple enterprises. Maintaining high bandwidth lines for all enterprises is expensive and does not fully utilize the lines most of the time. Reducing the bandwidth results in system alerts when the RPO is exceeded alerts that the system administrator wants to avoid. Increasing the RPO results in missing alerts that should be issued.

It would thus be of advantage to enable a disaster recovery system to designate different RPO objectives based on the day and the time of day with different respective bandwidths allocated to the disaster recovery system.

Aspects of the present invention overcome drawbacks with conventional single RPO disaster recovery systems and provide multi RPO disaster recovery systems for designating multiple RPO objectives based on day and time of day with multiple respective bandwidths allocated to the disaster recovery systems. Aspects of the present invention provide disaster recovery systems with calendar based or date and time based RPO objectives and bandwidth allocations thereby achieving greater flexibility and cost effectiveness vis vis conventional single RPO systems.

Using the present invention a disaster recovery system may share a link between sites for replication and applications. The disaster recovery system may set a higher RPO objective during peak times and a lower RPO objective during off peal times limit replication bandwidth during peak times and relax replication bandwidth during off peak times. The disaster recovery system may use the different RPO objectives to advantage for allowing as much bandwidth as possible taking into account that a higher RPO objective is met during peak times while catching up afterwards during off peak times when the RPO objective is lower.

Conversely the disaster recovery system may set a lower RPO objective during peak times and a higher RPO objective during off peak times to enable sharing the link with other systems during off peak times.

In accordance with an embodiment of the present invention a control element is installed to control bandwidth at a site level protection group level. The control element monitors RPO objective and corresponding allocated bandwidth in accordance with a calendar based or a date and time based schedule.

In accordance with an embodiment of the present invention a disaster recovery system may set different limits for data seeding traffic vs. data replication traffic over a WAN.

There is thus provided in accordance with an embodiment of the present invention a system for disaster recovery including a controller i for controlling bandwidth usage of a disaster recovery system in accordance with a plurality of recovery point objectives RPOs each RPO designating a maximal time loss constraint for data recovery for an enterprise production system and a corresponding bandwidth allocation for the disaster recovery system to use in replicating data for the enterprise production system wherein the RPOs are applied in accordance with a calendar based schedule of dates and times and ii for issuing an RPO alert when the RPO maximal time loss constraint for a current date and time is not satisfied.

There is additionally provided in accordance with an embodiment of the present invention a method for disaster recovery including accessing a calendar based schedule of recovery point objectives RPOs and corresponding bandwidth allocations for a disaster recovery system each RPO designating a maximal time loss constraint for data recovery for an enterprise production system and each bandwidth allocation constraining bandwidth usage for replicating data for the enterprise production system retrieving by the disaster recovery system at any given date and time the recovery point objective RPO and the corresponding bandwidth allocation for the given date and time from the calendar based schedule limiting by the disaster recovery system at the given date and time bandwidth usage of the disaster recovery system in accordance with the retrieved bandwidth allocation determining by the disaster recovery system a current RPO and if the current RPO exceeds the retrieved RPO then issuing by the disaster recovery system an RPO alert.

Appendix I is an application programming interface for virtual replication site controller web services in accordance with an embodiment of the present invention 

Appendix II is an application programming interface for virtual replication host controller web services in accordance with an embodiment of the present invention 

Appendix III is an application programming interface for virtual replication protection group controller web services in accordance with an embodiment of the present invention 

Appendix IV is an application programming interface for virtual replication command tracker web services in accordance with an embodiment of the present invention and

Appendix V is an application programming interface for virtual replication log collector web services in accordance with an embodiment of the present invention.

Aspects of the present invention relate to disaster recovery with multiple RPOs that are applied in accordance with a schedule of dates and times.

Reference is made to which is a simplified block diagram of a hypervisor architecture that includes a tapping driver and a VDSA in accordance with an embodiment of the present invention. Shown in is a hypervisor with three virtual servers three virtual disks an I O backend and a physical storage array . Hypervisor uses a single physical server but runs multiple virtual servers . Virtual disks are a storage emulation layer that provide storage for virtual servers . Virtual disks are implemented by hypervisor via I O backend which connects to physical disk .

Hypervisor also includes a tapping driver installed within the hypervisor kernel. As shown in tapping driver resides in a software layer between virtual servers and virtual disks . As such tapping driver is able to access I O requests performed by virtual servers on virtual disks . Tapping driver has visibility to I O requests made by virtual servers .

Hypervisor also includes a VDSA . In accordance with an embodiment of the present invention a VDSA runs on a separate virtual server within each physical hypervisor. VDSA is a dedicated virtual server that provides data services via one or more data services engines . However VDSA does not reside in the actual I O data path between I O backend and physical disk . Instead VDSA resides in a virtual I O data path.

Whenever a virtual server performs I O on a virtual disk tapping driver identifies the I O requests that the virtual server makes. Tapping driver copies the I O requests forwards one copy via the conventional path to I O backend and forwards another copy to VDSA . In turn VDSA enables the one or more data services engines to provide data services based on these I O requests.

Reference is made to which is a simplified data flow chart for a VDSA in accordance with an embodiment of the present invention. Shown in are an I O receiver a hash generator a TCP transmitter a data analyzer and reporter a journal manager and a remote VDSA . Remote VDSA resides on different physical hardware at a possibly different location.

As shown in I O receiver receives an intercepted I O request from tapping driver . VDSA makes up to three copies of the received I O requests in order to perform a set of actions which enable the one or more data services engines to provide various services.

A first copy is stored in persistent storage and used to provide continuous data protection. Specifically VDSA sends the first copy to journal manager for storage in a dedicated virtual disk . Since all I O requests are journaled on virtual disk journal manager provides recovery data services for virtual servers such as restoring virtual servers to an historical image. In order to conserve disk space hash generator derives a one way hash from the I O requests. Use of a hash ensures that only a single copy of any I O request data is stored on disk.

An optional second copy is used for disaster recovery. It is sent via TCP transmitter to remote VDSA . As such access to all data is ensured even when the production hardware is not available thus enabling disaster recovery data services.

An optional third copy is sent to data analyzer and reporter which generates a report with information about the content of the data. Data analyzer and reporter analyzes data content of the I O requests and infers information regarding the data state of virtual servers . E.g. data analyzer and reporter may infer the operating system level and the status of a virtual server .

Reference is made to which is a simplified block diagram of a virtual replication system in accordance with an embodiment of the present invention. Shown in is a protected site designated Site A and a recovery site designated Site B. Site A includes a hypervisor A with three virtual servers A A and A and a VDSA A. Site A includes two physical disks A and A . Site B includes a hypervisor B with a VDSA B. Site B includes two physical disks B and B . All or some of virtual servers A A and A may be designated as protected. Once a virtual server is designated as protected all changes made on the virtual server are replicated at the recovery site.

In accordance with an embodiment of the present invention every write command from a protected virtual server in hypervisor A is intercepted by tapping driver and sent asynchronously by VDSA A to VDSA B for replication via a wide area network WAN while the write command continues to be processed by the protected server.

At Site B the write command is passed to a journal manager for journaling on a Site B virtual disk . After every few seconds a checkpoint is written to the Site B journal and during a recovery one of the checkpoints may be selected for recovering to that point. Additionally checkpoints may be manually added to the Site B journal by an administrator along with a description of the checkpoint. E.g. a checkpoint may be added immediately prior to an event taking place that may result in the need to perform a recovery such as a planned switch over to an emergency generator.

In addition to write commands being written to the Site B journal mirrors B B and B of the respective protected virtual servers A A and A at Site A are created at Site B. The mirrors at Site B are updated at each checkpoint so that they are mirrors of the corresponding virtual servers at Site A at the point of the last checkpoint. During a failover an administrator can specify that he wants to recover the virtual servers using the latest data sent from the Site A. Alternatively the administrator can specify an earlier checkpoint in which case the mirrors on the virtual servers B B and B are rolled back to the earlier checkpoint and then the virtual servers are recovered to Site B. As such the administrator can recover the environment to the point before any corruption such as a crash or a virus occurred and ignore the write commands in the journal that were corrupted.

VDSAs A and B ensure write order fidelity i.e. data at Site B is maintained in the same sequence as it was written at Site A. Write commands are kept in sequence by assigning a tinnestanrip or a sequence number to each write at Site A. The write commands are sequenced at Site A then transmitted to Site B asynchronously then reordered at Site B to the proper time sequence and then written to the Site B journal.

The journal file is cyclic i.e. after a pre designated time period the earliest entries in the journal are overwritten by the newest entries.

It will be appreciated by those skilled in the art that the virtual replication appliance of the present invention operates at the hypervisor level and thus obviates the need to consider physical disks. In distinction conventional replication systems operate at the physical disk level. Embodiments of the present invention recover write commands at the application level. Conventional replication systems recover write commands at the SCSI level. As such conventional replication systems are not fully application aware whereas embodiment of the present invention are full application aware and replicate write commands from an application in a consistent manner.

As indicated hereinabove the architecture of scales to multiple sites having multiple hypervisors. Reference is made to which is a simplified block diagram of a cross host multiple hypervisor system that includes data services managers for multiple sites that have multiple hypervisors in accordance with an embodiment of the present invention. The architecture of includes three sites designated Site A Site B and Site C the three sites being communicatively coupled via a network . Each site includes one or more hypervisors . Specifically Site A includes three hypervisors A A and A Site B includes two hypervisors B and B and Site C includes one hypervisor C . The sites have respective one or more physical disks A B and C.

The hypervisors are shown in system with their respective VDSA s A A . . . and the other components of the hypervisors such as the virtual servers and virtual disks are not shown for the sake of clarity. An example system with virtual servers is shown in and described hereinbelow.

The sites include respective data services managers A B and C that coordinate hypervisors in the sites and coordinate hypervisors across the sites.

The system of may be used for data replication whereby data at one site is replicated at one or more other sites for protection. The solid communication lines in are used for in site traffic the dashed communication lines are used for replication traffic between sites and the dotted communication lines are used for control traffic between data services managers.

Data services managers A B and C are control elements. The data services managers at each site communicate with one another to coordinate state and instructions. The data services managers track the hypervisors in the environment and track health and status of the VDSAs A A . . . .

It will be appreciated by those skilled in the art that the environment shown in may be re configured by moving one or more virtual servers from one hypervisor to another by moving one or more virtual disks from one hypervisor to another and by adding one or more additional virtual servers to a hypervisor .

In accordance with an embodiment of the present invention the data services managers enable designating groups of specific virtual servers referred to as virtual protection groups to be protected. For virtual protection groups write order fidelity is maintained. The data services managers enable designating a replication target for each virtual protection group i.e. one or more sites and one or more hypervisors in the one or more sites at which the virtual protection group is replicated. A virtual protection group may have more than one replication target. The number of hypervisors and virtual servers within a virtual protection group and its replication target are not required to be the same.

Reference is made to which is a user interface screenshot of bi directional replication of virtual protection groups in accordance with an embodiment of the present invention. Shown in are virtual protection groups Exchange WebApp Dummy R1 Windows 2003 and Dummies L . Arrows indicate direction of replication.

Reference is made to which is a user interface screenshot of assignment of a replication target for a virtual protection group in accordance with an embodiment of the present invention. Shown in is an entry for designating a recovery host and an entry for designating a recovery datastore for virtual protection group Windows 2003 of . Respective source and target datastores SAN ZeRTO 30 A and datastore1 B are shown as being paired.

More generally the recovery host may be assigned to a cluster instead of to a single hypervisor and the recovery datastore may be assigned to a pool of resources instead of to a single datastore. Such assignments are of particular advantage when different enterprises share the same physical infrastructure for target replication as such assignments mask the virtual infrastructure between the different enterprises.

The data services managers synchronize site topology information. As such a target site s hypervisors and datastores may be configured from a source site.

Virtual protection groups enable protection of applications that run on multiple virtual servers and disks as a single unit. E.g. an application that runs on virtual servers many require a web server and a database each of which run on a different virtual server than the virtual server that runs the application. These virtual servers may be bundled together using a virtual protection group.

Referring back to data services managers A B and C monitor changes in the environment and automatically update virtual protection group settings accordingly. Such changes in the environment include inter alia moving a virtual server from one hypervisor to another moving a virtual disk from one hypervisor to another and adding a virtual server to a hypervisor .

For each virtual server and its target host each VDSA A A . . . replicates IOs to its corresponding replication target. The VDSA can replicate all virtual servers to the same hypervisor or to different hypervisors. Each VDSA maintains write order fidelity for the IOs passing through it and the data services manager coordinates the writes among the VDSAs.

Since the replication target hypervisor for each virtual server in a virtual protection group may be specified arbitrarily all virtual servers in the virtual protection group may be replicated at a single hypervisor or at multiple hypervisors. Moreover the virtual servers in the source site may migrate across hosts during replication and the data services manager tracks the migration and accounts for it seamlessly.

Reference is made to which is an example an environment for system in accordance with an embodiment of the present invention. As shown in system includes the following components.

As further shown in system includes the following virtual protection groups. Each virtual protection group is shown with a different hatching for clarity.

As such it will be appreciated by those skilled in the art that the hypervisor architecture of scales to multiple host sites each of which hosts multiple hypervisors. The scaling flexibly allows for different numbers of hypervisors at different sites and different numbers of virtual services and virtual disks within different hypervisors.

The scaling flexibility of the present invention also allows extension to cloud based data services provided by a cloud provider on a shared infrastructure as explained hereinbelow.

Cloud based data services enable data center providers to service multiple enterprises at data centers that are remote from the enterprises. Cloud based data services offer many advantages. Enterprises that use cloud based data services obviate the needs for servers SAN NAS networks communication lines installation configuration and ongoing maintenance of information technology systems and overhead expenses for electricity cooling and space. However conventional cloud based data suffer from weakness of security due to multiple enterprises sharing the same physical infrastructure and due to multiple enterprises using the same networks and IPs for their services.

Cloud based systems of the present invention overcome these weaknesses. Reference is made to which is a simplified block diagram of a system for mufti tenant and mufti site cloud based data services in accordance with an embodiment of the present invention. Shown in are three enterprises designated A B and C and a remote cloud based facility with two data centers designated and . Enterprise A uses a NETAPP data management system Enterprise B uses an IBM data management system and Enterprise C uses an EMC data management system. Data Center uses an EMC data management system and services Enterprise A. Data Center uses a NETAPP data management system and services Enterprises B and C.

System has many advantages over conventional data service systems. Inter alia system enables protection of heterogenic environments enables remote control of enterprise sites enables economies of scale enables complete workload mobility enables a complete web services API for seamless integration and enables integration with other cloud based management systems.

Reference is made to which is a simplified block diagram of a first architecture of system for providing hypervisor level mufti tenant cloud based data services in accordance with an embodiment of the present invention. The architecture shown in includes two enterprises namely a smaller enterprise A and a larger enterprise B. Enterprise A infrastructure includes a single hypervisor A with five virtual servers A A A A and A and a VDSA A includes two physical disks A and A and includes a data services manager A. Enterprise B infrastructure includes two hypervisors B and B includes three physical disks B B and B and a data services manager B. Hypervisor B includes five virtual servers B B B B and B and a VDSA B and hypervisor B includes five virtual servers B B B B and B and a VDSA B .

Cloud based facility infrastructure includes two hypervisors and and four physical disks and . Hypervisor includes six virtual servers and and hypervisor includes two virtual servers and . Hypervisor services Enterprises A and B and hypervisor services Enterprise B. As such the infrastructure of cloud based facility is shared between Enterprises A and B.

The architecture of allocates one data services manager per enterprise and one VDSA per hypervisor. Specifically hypervisor includes a VDSA and hypervisor includes a VDSA . A data services manager A services Enterprise A and a data services manager services Enterprise B.

Reference is made to which is a simplified block diagram of a second architecture of system for providing hypervisor level mufti tenant cloud based data services in accordance with an embodiment of the present invention. The architecture of allocates one data services manager per enterprise and one VDSA per enterprise per hypervisor. Specifically hypervisor includes a VDSA A for Enterprise A and a VDSA B for Enterprise B and hypervisor includes a VDSA B for Enterprise B.

Reference is made to which is a simplified block diagram of a third architecture of system for providing hypervisor level mufti tenant cloud based data services in accordance with an embodiment of the present invention. The architecture of allocates one data services manager in the cloud and one VDSA per hypervisor. In addition one enterprise connector is allocated per enterprise. Specifically a connector A is allocated to Enterprise A and a connector B is allocated to Enterprise B. Connector A is connected to both VDSA and VDSA and to a cloud data services manager on the cloud side and is connected to Enterprise A data services manager A and VDSA A on the enterprise side. Similarly connector B is connected to VDSA VDSA and cloud data services manager on the cloud side and is connected to Enterprise B data services manager B VDSA and VDSA B on the enterprise side. As such each enterprise is connected to the entire infrastructure on the cloud side via its own connector.

Reference is made to which is a simplified block diagram of a fourth architecture of system for providing hypervisor level mufti tenant cloud based data services in accordance with an embodiment of the present invention. The architecture of also allocates one data services manager in the cloud and one VDSA per hypervisor. In addition one enterprise connector is allocated per enterprise. Connectors A and B on the cloud side are paired with respective connectors A and B on the enterprise side. Use of connectors A and B eliminates the need for a virtual private network VPN and enables installation of system behind network address translators NATs .

The different architectures in offer different advantages. The architecture of minimizes the cloud footprint of the VDSA by using a shared VDSA per hypervisor and only one data services manager per enterprise. Specifically the VDSA is shared between enterprises and security is enforced via the data services managers. In this architecture the data services manager is duplicated per enterprise and centralized cloud management is lacking.

The architecture of maximizes data path security for enterprises but the cloud footprint is larger since multiple data services managers may be required per hypervisor.

The architectures of provides data security network security minimal cloud footprint and single point of control for cloud vendors. In this architecture there is only one centralized data service manager on the cloud side and only one VDSA per hypervisor. One cloud connector element is deployed on the cloud side per enterprise. The cloud connector securely routes enterprise traffic from the enterprise network to the cloud infrastructure replication network thus providing full network security and deployment features including inter alia duplicate IP range utilization for different enterprises while maintaining unique network deployment on the cloud infrastructure side. The data services manager and VDSA s perform secure site authentication and data security for end to end secure multi tenant service.

As such it will be appreciated by those skilled in the art that the cloud based hypervisor level data services systems of the present invention enable multi tenancy and multi site services. I.e. multiple enterprises and multiple sites may be serviced by the same physical infrastructure including inter alia the same hypervisors and storage with minimized footprint on the cloud side allowing for centralized cloud management. By providing each enterprise with its own data services manager on the clod side as in or alternatively with its own connector and a centralized data services manager on the cloud side as in the systems of the present invention provide path separation between enterprises thus ensuring that each enterprise is only able to view and access his own virtual servers and storage and each enterprise can only control its own data replication.

By deploying additional cloud connectors on the enterprise side as in the systems of the present invention may be installed behind NATs and do not require a VPN. As such these systems may obviate VPN setups for enterprises and obviate use of dedicated public IPs. For additional security the cloud connectors encrypt traffic thus eliminating the need for additional network security elements.

The systems of the present invention provide bi directional cloud based data replication services i.e. from an enterprise to the cloud and from the cloud to an enterprise for the same enterprise or for different enterprises simultaneously using the same shared infrastructure. Moreover replication targets may be set as resources that do not expose the enterprise infrastructure thus providing an additional layer of security and privacy between enterprises.

It will be appreciated by those skilled in the art that systems of the present invention may be used to enforce jurisdictional data export regulations. Specifically cloud based facility infrastructure is partitioned according to jurisdictions and data recovery and failover for an enterprise is limited to one or more specific partitions according to jurisdictional regulations.

Reference is made to which is a simplified block diagram of a system for mufti tenant and mufti site cloud based data services with jurisdictional data separation in accordance with an embodiment of the present invention. Shown in are three jurisdictional enterprises namely a USA Enterprise A a UK Enterprise B and an APAC Enterprise C. Also shown in are four data centers namely Data Center and Data Center in the USA Data Center in the UK and Data Center in APAC.

Privacy and data security regulations prevent data from being exported from one jurisdiction to another. In order to enforce these regulations system includes a rights manager that blocks access to a data center by an enterprise if data export is regulations restrict data transfer between their respective jurisdictions. Thus rights manager blocks access by Enterprise A to Data Centers and blocks access by Enterprise B to Data Centers and and blocks access by Enterprise C to Data Centers and . Enterprises A B and C may be commonly owned but access of the data centers by the enterprises is nevertheless blocked in order to comply with data export regulations.

In accordance with an embodiment of the present invention when configuring a virtual protection group an administrator may set a territory data center restriction. When the administrator subsequently selects a destination resource for data replication for a virtual protection group system verifies that the resource is located in a geography that does not violate a territory data center restriction.

The present invention may be implemented through an application programming interface API exposed as web service operations. Reference is made to Appendices I V which define an API for virtual replication web services in accordance with an embodiment of the present invention.

It will thus be appreciated that the present invention provides many advantages including inter alia 

Aspects of the present invention provide disaster recovery systems with calendar based or date and time based RPO objectives and bandwidth allocations thereby achieving greater flexibility and cost effectiveness vis vis conventional single RPO systems.

Using the present invention a disaster recovery system may share a link between sites for replication and applications and effectively cope with varying application change rates. The disaster recovery system may set a higher RPO objective during peak times and a lower RPO objective during off peal times limit data replication bandwidth during peak times and relax data replication bandwidth during off peak times. The disaster recovery system may use the different RPO objectives to advantage for allowing as much bandwidth as possible for production taking into account that a higher RPO objective is met during peak times while catching up afterwards during off peak times when the RPO objective is lower.

Conversely the disaster recovery system may set a lower RPO objective during peak times and a higher RPO objective during off peak times to enable sharing the link with other systems during off peak times.

In accordance with an embodiment of the present invention a control element is installed to control bandwidth at a site level protection group level. The control element monitors RPO objective in accordance with a calendar based or a date and time based schedule.

In accordance with an embodiment of the present invention a disaster recovery system may set different limits for data seeding traffics vs. data replication traffic over a WAN.

Reference is made to which is a screen shot of a multi RPO console for a disaster recovery application in accordance with an embodiment of the present invention. The data recovery policy shown in designates four timeframes each timeframe having its own RPO objective and bandwidth limitation. The timeframes are scheduled using a weekly calendar. Timeframe corresponds to 12 00 AM 4 00 AM Mon. Sun. Timeframe corresponds to 4 00 AM 8 00 AM Mon. Thurs. Timeframe corresponds to 8 00 AM 2 00 PM Mon. Fri. and 2 00 PM 6 00 PM Mon. Thurs. Timeframe corresponds to the remainder of the week.

Reference is made to which is a simplified block diagram of an exemplary multi RPO data protection system in accordance with an embodiment of the present invention. Shown in are a protected site and a replication site . Protected site includes a vCenter server ESX ESXi hypervisors and and physical disks and . Server includes a virtual manager . Hypervisor includes virtual machines and and hypervisor includes virtual machines and . Hypervisors and also include respective virtual replication appliances and . Physical disk includes virtual disks and physical disk includes virtual disks and and physical disk includes virtual disks and . Physical disks and may be heterogeneous e.g. physical disk may be a NETAPP disk physical disk may be an IBM disk and physical disk may be an EMC disk.

Replication site includes a vCenter server an ESX ESXi hypervisor and physical disks and . Server includes a virtual manager . Hypervisor includes virtual machines and . Hypervisor also includes a virtual replication appliance . Physical disk includes virtual disks and and physical disk includes virtual disks and . Physical disks and may be heterogeneous e.g. physical disk may be a NETAPP disk and physical disk may be an EMC disk.

Reference is made to which is a simplified flow diagram of a method for multi RPO data protection in accordance with an embodiment of the present invention. At operation virtual manager accesses a calendar based schedule of RPO objectives and corresponding bandwidth allocations. At operation virtual manager retrieves the designated RPO for a virtual protection group and the designated bandwidth allocation for a given date and time in accordance with the schedule. At operation virtual manager limits bandwidth usage of a disaster recovery system for replicating data for the virtual protection group based on the retrieved designated bandwidth allocation. At operation virtual manager determines the current RPO for the virtual protection group.

At operation virtual manager determines whether or not the current RPO determined at operation exceeds the designated RPO retrieved at operation . If so then at operation virtual manager issues a virtual protection group RPO alert. Otherwise at operation virtual manager turns off the virtual protection group RPO alert.

In an embodiment of the present invention virtual manager is operative to adjust the schedule of RPO objectives and corresponding bandwidth allocations in response to having issued multiple RPO alerts at operation .

An RPO alert is a notification to an operator generally indicating a data replication write rate that is too high relative to a bandwidth constraint which in turn means that there is a service level agreement issue or risk to be addressed. For conventional disaster recovery systems because of the difference between peak and off peak data write demands some RPO alerts are expected and represent warnings that can be ignored and other RPO alerts are not expected and represent serious concerns which is generally confusing to the operator.

By using the present invention to schedule RPO objectives in accordance with peak and off peak write demand times ignorable RPO alerts are avoided and the operator knows that the RPO alerts that are issued represent serious concerns that need to be addressed.

In the foregoing specification the invention has been described with reference to specific exemplary embodiments thereof. It will however be evident that various modifications and changes may be made to the specific exemplary embodiments without departing from the broader spirit and scope of the invention as set forth in the appended claims. Accordingly the specification and drawings are to be regarded in an illustrative rather than a restrictive sense.

These web services include methods and properties for pairing and un pairing sites and for managing site details.

This method retrieves site details including inter alia the IP address and port of a designated server.

This method retrieves the name location and contact information specified by an administrator for a designated site.

This method retrieves the TCP port to access the virtual data services application for a designated site.

This method sets the TCP port used to access the virtual data services appliances at a designated site.

These web services include methods and properties to identify hypervisors and to deploy virtual data services appliances on hypervisors.

This method retrieves a list of hypervisors where a virtual data services appliance is in the process of being installed at a designated site.

This method retrieves a list of hypervisors where a virtual data services appliance is in the process of being un deployed at a designated site.

This method retrieves a list of hypervisors where a virtual data services appliance is installed at a designated site.

This method retrieves a list of hypervisors where a virtual data services appliance is not installed at a designated site.

This method deploys a virtual data services appliance on a specified hypervisor at a designated site in accordance with a specified datastore a specified type of network and access details including inter alia an IP a subnet mask and gateway for the VDSA.

This method un deploys a virtual data services appliance from a specified hypervisor at a designated site.

This property indicates the status of a virtual protection group from among Protecting NeedReverseConfiguration Promoting PromotingAndNeedReverseConfiguration Test Failover PromotionCompleteMirrorsNotYetActivated MissingConfiguration PromotingAndMissingConfiguration RemoveInProgress.

This method performs a failover of the virtual servers in a designated virtual protection group to a designated checkpoint instance or to the latest checkpoint.

This method performs a failover of the virtual servers in a designated virtual protection group to a designated checkpoint or to the latest checkpoint without creating reverse replication and without stopping protection of the virtual servers in the designated virtual protection group.

This method removes a virtual protection group irrespective of the state of the group. This method is used if the RemoveProtectionGroup method is unable to complete successfully.

This method updates virtual protection group settings including removal of virtual servers and disks that should have been removed using the RemoveProtectionGroup method. This method is used if the UpdateProtectionGroup method is unable to complete successfully.

This method retrieves the virtual protection group settings for a specified virtual protection group for use as default values for reverse replication.

This method retrieves the state of a specified virtual protection group the state being protected or recovered . If the group is protected 0 is returned and if the group is recovered 1 is returned.

This method retrieves the status of a specified virtual protection group the status being inter alia protecting testing or promoting .

This method inserts a named checkpoint for a designated virtual protection group. The method returns immediately without verifying whether or not the checkpoint was successfully written to the journal in the peer site.

This method adds a designated virtual server to a virtual protection group in accordance with designated settings.

This method removes a virtual protection group unless the group is being replicated during a test failover or an actual failover and unless the group is being migrated to the peer site. If this method does not return a Success completion code the ForceRemoveProtectionGroup method may be used to force removal of the group.

This method discards information about a specified number of old failover tests for a designated virtual protection group from the oldest test to the most recent test.

This method updates settings of a specified virtual protection group. If the method does not return a Success completion code the ForceUpdateProtectionGroup method can be used to force the update.

This method waits for a checkpoint to be written to a journal on the peer site after it was inserted or times out if it takes too long.

This method returns the completion code of a specified task. Completion codes include Success Aborted Failed or HadException. If the task is still running NotAvailable is returned.

This method returns the command type the completion code input parameters and the virtual protection group identifier of a designated task.

This method returns the string associated with an exception for a designated task that had an exception. The method GetCompletionCode returns HadException if a task had an exception.

This method returns the identifier of a task currently being performed on a designated protection group.

This method returns the identifier of a task currently being performed on a specified protection group at a local site.

This commend returns the result for a designated task. The returned result may be one of the following 

This method retrieves the current status of a specified task. The status may be Active Running Aborted or Completed.

This method waits for a specified task to complete by polling the task at specified time intervals until a specified time out.

This property indicates details of a log request including a level of detail of information indicating whether information about a virtual data service appliance and core information should be included and including start and end times for the information.

