---

title: System to assist a mobile device subscriber to perform self-diagnosis of the mobile device
abstract: The instant invention is a process for a Self-Care system that allows mobile device subscribers to manage their own devices without making a trip or a phone call to the customer care center. Subscribers can view service issues and repair and update settings, check the status of their devices, and manage device security minimizing customer service calls. Dynamic workflow navigates the subscriber to easily find a solution to their problem which will substantially reduce frequent calls to customer care. Dynamic menus avoid the unnecessary information that the subscriber might enter about the device and leads the subscriber towards the path of solving the issue. The system is scalable to include diagnostics tools as part of self-care and customer care, where the subscribers can benefit from these tools to reset their device to a normal state.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08934866&OS=08934866&RS=08934866
owner: AetherPal Inc.
number: 08934866
owner_city: South Plainfield
owner_country: US
publication_date: 20120504
---
The present application is based upon U.S. Provisional Patent Application Ser. No. 61 483 293 filed May 6 2011 and is related to U.S. application Ser. No. 12 426 555 filed Apr. 20 2009 and entitled Virtual Mobile and AD Alert management for Mobile Devices the contents of the applications are incorporated herein by reference.

The present invention relates to mobile wireless communication devices systems networks and methods of operation. This invention describes the process of Self Care for mobile devices through a dynamic workflow management system.

Remote management of devices and applications is now extremely important in controlling costs in mobile service operations. Automatic updates to applications drivers network and device configuration can save a significant amount of time and cost in decreasing the no fault found device returns.

Customer Care representatives can send emails or SMS to the device and query the status of the device but there is no built in remote diagnostics capability. As a result if the device fails to perform a task it becomes difficult to get it working again until the root cause is known. Delays in getting or entering information often result in delays to business processes that lead to an inferior customer experience. Mobility empowers workers with access to information at the point of customer contact helping them to answer questions resolve issues or input orders on the spot.

What is needed in the art is a system that will help a subscriber self diagnose and manage their mobile device without making a trip or a phone call to the customer care center or login to a customer care portal.

The instant invention sets forth a Self Care system that allows subscribers to self diagnose and manage their mobile device without making a trip or a phone call to the customer care center or login to the customer care portal. Based on mobile device capabilities subscribers can view service issues and repair and update settings check the status of their devices and manage device security minimizing customer service calls. The framework provides flexibility to update the workflow periodically.

Thus an objective of the invention is to provide a dynamic workflow that navigates a subscriber to easily find a solution to their problem which will substantially reduce frequent calls to customer care.

Another objective of the invention is to provide a scalable system to include diagnostics tools as part of self care and customer care where the subscribers can benefit from these tools to reset their device to a normal state.

Still another objective of the invention is to provide a dynamic workflow menu for Self Care to help subscribers proactively self diagnose their devices faster and more economically than was possible in the past.

Yet another objective of the invention is to provide a Self Care tool available on the device helps the subscriber to avoid going to the customer care portal every time thereby reducing the amount of time the subscriber has to spend on the web.

An advantage of the system is to provide a flexible framework to update the workflow periodically. Dynamic workflow navigates the subscribers to easily find a solution to their problem which will substantially reduce frequent calls to customer care. The system is scalable to include diagnostic tools as part of self care and customer care where the subscribers can benefit from these tools to reset their device to a normal state.

The invention provides a dynamic workflow menu for self care to help subscribers proactively self diagnose their devices faster and more economically than was possible in the past.

The invention provides a self care tool on the device that helps the subscriber to avoid going to the customer care portal every time thereby reducing the amount of time the subscriber has to spend on the web.

The invention provides dynamic menus that avoid the unnecessary information that the subscriber might enter about the device and instead leads the subscriber towards the path of solving the issue.

The invention provides a self care tool can help the subscriber to perform health checks on the device locally without need for a customer care representative in just one click.

The invention provides dynamic workflows that can be easily created and managed by the Administrators.

The invention provides periodic updates to workflow and diagnostic tools as part of self care and customer care where the subscribers can benefit from these tools to reset their device to a normal state.

The invention provides a dynamic workflow that allows a subscriber to find a solution to their problem.

The invention provides a remote diagnostics capability so if the device fails the subscriber can perform a remote wipe of applications and data.

Other objectives and advantages of this invention will become apparent from the following description taken in conjunction with any accompanying drawings wherein are set forth by way of illustration and example certain embodiments of this invention. Any drawings contained herein constitute a part of this specification and include exemplary embodiments of the present invention and illustrate various objects and features thereof.

Referring now to the instant invention uses a client server model which communicates using a proprietary protocol. The client residing on the device helps the subscriber to login to the Self Care system that remotely interacts with the server allowing the subscribers to self diagnose their devices. Based on the selection made from the menu the subscriber is guided through a series of choices that leads to the specific problem. The current invention focuses on the process of managing the dynamic information workflow for Self Care since the workflows and policies that need to be enforced for Self Care differs depending on the sensitivity of information managed.

Dynamic workflow navigates the subscribers to easily find a solution to their problem which will substantially reduce frequent calls to customer care. The system is scalable to include diagnostic tools as part of self care and customer care where the subscribers can benefit from these tools to reset their device to a normal state. The framework provides flexibility to update and manage the workflow as needed.

The workflows and policies that need to be enforced for Self Care differs depending on the sensitivity of information managed. Hence the current invention focuses on the process of managing the dynamic information workflow for Self Care.

Referring to set forth is an example of wherein a subscriber has a hardware problem on a mobile device. The following sets for the dynamic call flow for Self Care 

Step 5 Once the hardware option is chosen the server will dynamically provide options for the subscriber to choose based on the features that the device supports 

Step 6 Finally once the subscriber chooses the right option the script is pushed on to the device to troubleshoot the problem 

Referring to the current invention allows for a client server model for Self Care device management. The system is scalable to support functionalities like diagnostics and Analytics as part of subscriber care solution. The model consists of a client application on the device and the server module controlling the device by performing various operations as per the workflow.

Self Care is used by device owners to manage their own devices. The device owner manages the device by using a graphical user interface GUI on the client. Self Care operates in the context of a single device. The owner logs into the application and can manage only their device. If the owner has more than one device a device is selected from a list.

Scripting Engine serves as a database and execution engine for collection of scripts under Self Care Customer Care Diagnostics and Analytics. Scripts allows Admin to write and share simple scripts to automate a wide variety of device management tasks to meet custom needs.

Workflow ManagerWorkflow Manager is a computer system that manages and defines a series of tasks to produce a final outcome or outcomes including collection of WorkFlowBlocks each block consists of collection of scripts each script is a collection of cmdlets and the scripts will be executed by the Scripting Engine.

Communication Module is responsible for establishing a session between the server and the client using proprietary communication protocol.

Self Care menu on client UI will have dynamic content based on the type of device and also how the System Administrator wants to provide access to the subscriber. Based on the item the subscriber chooses the menu on the device will pull the information from the WorkFlowManager on the server and displays information accordingly.

Communication End Point Gateway CEG The primary responsibility of the Communication End Point Gateway is to manage the device connections within the system. The following are the key functions 

The server provides communication endpoints between Control Center Technician Console Admin and Control Function and the device 

Provides a consistent manner of device connection and tool service in a system with heterogeneous devices running different operating systems 

Provides load balancing across multiple Connection Handlers on each Communication End Point Gateway Server in order to minimize single point of failure.

Admin and Control Function Primary responsibility is to administer and manage all types of communication between the Control Center and the client devices.

Workflow Management Entity The workflow management entity is responsible for the management and execution of workflows on behalf of the devices.

Data Repository This stores all the information about the VMM RC Mobile devices server configuration tasks and status settings. These databases are pivotal to configure and update managed devices and server components. It is also responsible to maintain the user login information as well as device authentication information.

Admin DB The Admin DB maintains all the system configurations tenant configuration and management information system administration and server instrumentation data. This database is accessed by the AetherPal System Admin Service.

Ops DB The Ops DB maintains data that is required for the operations of the system such as device enrollment Access Control List ACL groups users zones etc. This database is accessed by the AetherPal Management Service and the Service Coordinator.

Reports DB The Reports DB contains historical data of device enrollment session audit report views etc.

Registration and Authentication Function This component provides a single point of entry for all devices for enrollment and authentication services during VMM RC session. Registration and Authentication function comprises of the following components 

Registration Service During Auto Enrollment devices are required to register themselves with this service prior to enrolling themselves.

Enrollment Service This service is responsible to enroll registered devices with the system. Enrollment process is defined in detail in the later sections of the document.

Software Update This service manages the various client packages in the system. Devices connect to this service to request for client update. If an update is available the service will provide the appropriate client download link.

Device Management This service provides the enrolled devices an interface to update its parameters in the system such as MDN when the device detects a change.

The Technician Console provides a graphical user interface to manage and control the Mobile Devices. The following provides list of functions that can be performed using the console 

Referring to the Self Diagnosis Interface Module provides a consistent and standard Application Programming Interface or API to the User Interface. The Self Diagnosis Interface module exposes synchronous as well as asynchronous function calls by which the User Interface interacts with the application stack. It also provides a callback mechanism to the Self Diagnosis user interface for asynchronous communication.

VMM Manager includes the following VMM Modules VMM modules provide a multitude of tool services. Tool Services are grouped together that exhibit common functionality such as Remote Control File Manager Device Management Diagnostics etc.

State Machine Each tool service maintains an instance of the state machine. A State Machine defines a set of shared states that the tool service on the device application shares with the server.

Tool Service Coordinator The Tool Service Coordinator maintains a collection of active tool service instances that are currently being serviced by the VMM application. This entity maintains the lifetime of all Tool Services and is responsible in creating and destroying Tool Services.

NV Data Repository Authentication and authorization specific data that is shared between the VMM application and the server is maintained within the NV data repository. This data repository also serves the purpose of maintaining Tool Service configuration as well as VMM configuration data.

Access Control Entity Access Control Entity layer provides a set of functions to the Tool Services to communicate with the Control Center. It provides in the encapsulation of messages before forwarding it to the Communication Core. This layer is responsible to invoke an instance of the Communication Core layer and provides a state machine that defines the state of the VMM application.

Access Control Interface Access Control Interface provides a set of standard Application Programmer Interface or API to the Tool Services. These APIs provide a consistent communication platform to facilitate both synchronous as well as asynchronous communication.

State Machine The ACI State Machine identifies the overall state of the VMM application. State transitions within the ACE State Machine triggers events that are handled by the VMM layer. The states are Open and Closed. Traffic flows through the ACI layer only in the Open State.

Authentication Entity The authentication Entity is responsible in ensuring that the device receives connection and processes requests from the server with which it is enrolled. This entity ensures data integrity security and authentication.

CommandLet Processing Entity Referring to the CommandLet processing entity executes individual cmdlets or atomic commands on behalf of the server. The commands are pre processed and passed onto the command invocation function which is responsible in translating the abstract cmdlet into a device specific command.

Commands could be executed synchronously or asynchronously. Asynchronous commands take longer time to execute. Hence the Asynchronous Callback handler provides a mechanism to trap and route the execution of asynchronous commands.

Message Processing Entity Referring to set for is the Message Processing Function is a signal message pre processor. This entity receives signal messages from the Session Layer destined towards Tool Services. It de frames these messages prior to forwarding it to the Message Routing Entity to apply routing rules. Messages that are destined to the server from Tool Services are encapsulated here.

Communication Core The Communication Core Layer is responsible to setup and maintain a dedicated communication channel with the Control Center. This layer provides the necessary framework to transport messages between the upper layers and the Control Center. It provides message encapsulation framing fragmentation and packet re construction of Tool Service messages.

While detailed embodiments of the instant invention are disclosed herein it is to be understood that the disclosed embodiments are merely exemplary of the invention which may be embodied in various forms. Therefore specific functional and structural details disclosed herein are not to be interpreted as limiting but merely as a basis for the claims and as a representation basis for teaching one skilled in the technology to variously employ the present invention in virtually any appropriately detailed structure.

One skilled in the technology will readily appreciate that the present invention is well adapted to carry out the objectives and obtain the ends and advantages mentioned as well as those inherent therein. The embodiments methods procedures and techniques described herein are presently representative of the preferred embodiments are intended to be exemplary and are not intended as limitations on the scope. Changes therein and other uses will occur to those skilled in the art which are encompassed within the spirit of the invention and are defined by the scope of the appended claims. Although the invention has been described in connection with specific preferred embodiments it should be understood that the invention as claimed should not be unduly limited to such specific embodiments. Indeed various modifications of the described modes for carrying out the invention which are obvious to those skilled in the technology are intended to be within the scope of the following claims.

