---

title: Techniques for establishing virtual devices
abstract: Techniques for establishing virtual devices are presented. A legacy control system is encapsulated as a virtual device. The virtual device is isolated within a host hardware associate with a host OS and access to and from the virtual device is authenticated and controlled by the host OS. Legacy hardware used by the legacy control system is connected to the host hardware, thereby permitting the legacy control system to continue to access the legacy hardware when the virtual device processes.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08949861&OS=08949861&RS=08949861
owner: Novell, Inc.
number: 08949861
owner_city: Provo
owner_country: US
publication_date: 20120914
---
The present application is with is a Continuation of and claims priority to U.S. patent application Ser. No. 13 224 397 entitled Techniques for Establishing Virtual Devices tiled on Sep. 2 2011 now issued as U.S. Pat. No. 8 281 323 which is a continuation of U.S. patent application Ser. No. 12 271 247 entitled Techniques for Establishing Virtual Devices filed on Nov. 14 2008 now issued as U.S. Pat. No. 8 051 432 the disclosures all of which are incorporated by reference herein in their entireties.

Many industries have long implemented their core business processes in software systems. For example process oriented industries such as chemical plants and power plants are known to keep their core processes in software systems for many years. Also sometimes it is hard to stop the process control metrics and measurement methodologies within an enterprise. These plants are initially setup for years of operation but the control or software systems which utilize hardware like personal computers connecting to the systems through General Purpose interface Buses Analogue to Digital convertors or other logical circuits have to be designed with a particular computer Operating System OS in mind.

However software and hardware becomes outdated faster than the control or software systems of an enterprise. Moreover old software may not be designed to handle new and more frequent security threats that information systems are constantly exposed to in today s highly networked environment. Additionally support for older versions of OS s may be discontinued by an OS vendor. So with these modern realities any modern enterprise that continues to run legacy control or software systems is treading on dangerously thin ice which can be fatal to the enterprise depending upon the nature of the industry.

Consequently enterprises may expend huge sums of capital and large amounts of human resources to continue to support outdated hardware and OS s because to do otherwise could put the entire enterprise in jeopardy. The alternative is to undergo a large internal infrastructure project to port the control or software systems to modern hardware and modern versions of an OS. Yet with the alternative approach the enterprise can find itself in a perpetual cycle where as soon as one port ends another one has to begin because what was considered modern has since become outdated. it is apparent that many industries are faced with difficult choices and large expenditures to continue their existing operations and practices. These expenses are often passed onto the consumer such that eventually a smaller more nimble startup company can enter the market at a lower price point with a more modern internal infrastructure for its control and software systems this puts extreme and sometimes insurmountable pressure on the enterprise from a competitive standpoint.

Thus what are needed are techniques which allow for improved support integration and security of legacy control or software systems to allow enterprises to be more competitive in today s environment.

In various embodiments techniques for establishing virtual devices are presented. More specifically and in an embodiment a method is provided that establishes a virtual device to isolate and migrate a legacy control or software system in a different OS and machine architecture from its native OS and native machine architecture.

As used herein a virtual device refers to a virtual machine VM that processes its own version of a particular OS and mimics a particular machine architecture on another and entirely different machine architecture The VM is a logical machine that is independent of its physical process environment or physical machine Again the VM includes its own OS its own file system FS its own directory services etc. which may each be different from the physical processing environment of the host machine. As used herein virtual device and VM may be used interchangeably.

A legacy control system refers to a processing environment and suite of software services that was originally designed to process on one or more particular machine architectures and one or more particular OS s or versions of a particular OS. These machine architectures OS s and versions of a particular OS are referred to herein as native machine architectures OS s and versions of a particular OS native with respect to the legacy system. The legacy control system also relies at least in part on access to legacy hardware or legacy devices associated with its native machine architectures 

According to an embodiment the techniques presented herein are implemented in products associated and distributed by Novell Inc. of Provo Utah.

Of course the embodiments of the invention can be implemented in a variety of architectural platforms operating and server systems vices systems or applications. Any particular architectural layout or implementation presented herein is provided for purposes of illustration and comprehension only and is not intended to limit various aspects of the invention.

It is within this initial context that various embodiments of the invention are now presented with reference to the .

At the virtual device establishment service creates a virtual image of a legacy processing environment associated with a first or native OS. The virtual image includes a legacy control system that relies on the legacy processing environment the first native or legacy OS and access to legacy or native hardware. Any physical to virtual application or service can be used to create the virtual image such applications or services are available for purposes of backing up hardware and software systems.

At the virtual device establishment service connects native hardware that the legacy control system accesses during its operation to host hardware that also processes a second OS.

At the virtual device establishment service installs the virtual image in the host hardware such that the first or legacy OS of the virtual image is designated as a guest OS on the host hardware. The second OS is designated as a host or controlling OS for the host hardware.

At the virtual device establishment service establishes a secure trust communication relationship between the guest OS and the host OS. That is the host OS and the guest OS authenticate to one another during startup and initialization and perhaps periodically or even during each communication between the two. Any technique of combinations of techniques can be used to establish this secure trust relationship.

According to an embodiment at the virtual device establishment service permits the legacy control system via the guest OS to directly access the native or legacy hardware. This is permitted once the secure trust communication relationship has been established and the guest OS authenticated. The legacy control system may access a variety of legacy or native hardware that may be outdated or not supported by the host hardware and the host OS thus by connecting the native hardware to the host hardware and installing the guest OS with the legacy control system the legacy control system can still access this legacy hardware. This hardware can include a variety of things such as mechanical devices uses in an enterprise that have processor enabled capabilities outdated computers old storage devices etc. The legacy control system can continue to use its old device interfaces to directly access the devices associated with the legacy hardware. Thus the legacy control system is essentially encapsulated by the virtual device establishment service within host hardware which has a modem and updated host OS and yet the legacy control system can continue to process unabated using old device drivers to access that legacy hardware even while the legacy control system essentially processes on the host hardware.

At the virtual device establishment service exposes Via an application associated with either a service installed within the virtual image when it was created or associated with the legacy control system the native hardware for access and perhaps monitoring by the host OS. Thus the host OS can gain access to the native hardware. This can be achieved in a number of ways.

For example at the virtual device establishment service identifies the application as a generic device driver that exposes each device associated with the native hardware to the host OS as a particular device driver that is accessible to the host OS.

In another case at the virtual device establishment service identifies the application as a Remote Procedure Call RPC which permits the host OS to establish a remote connection. The remote connection exposes device drivers for devices of the native hardware back to the host OS. This can be done via software on the guest OS that exposes the device drivers for the native hardware devices as user level application objects. The host OS communicates with the guest OS through a user mode of operation.

In yet another situation at the virtual device establishment service identifies the application as an application connection layer that is provided for the native hardware and that includes an Application Programming Interface API for the host to connect to the devices of the native hardware This API can be supplied by the hardware vendor or other vendors with an interest in providing such an API. The API permits the host OS to connect to outdated or unsupported devices associated with the legacy or native hardware.

At the virtual device establishment service executes the legacy control system via the guest OS within or on the host hardware. So as stated. before the legacy control system is essentially encapsulated as a virtual device or virtual machine VM on the host hardware and installed and executed on the host hardware as a guest OS that is communicated with and controlled by a host OS. The legacy control system can still access its needed legacy hardware and its associated devices.

According to an embodiment at the virtual device establishment. service receives input data for the legacy control system via other applications that process within the host OS on the host hardware. These other applications can be used to verify the security of and validity of any input data before it is passed on to the legacy control system via the host OS to the guest OS. So essentially a legacy control system can benefit from more updated security mechanisms because the applications are running on an updated host OS. The legacy control system then benefits and is made more secure because input data is processed and validated before that data ever reaches the guest OS and the legacy control system. The applications can also be used to enhance features of the legacy control system. The enhancement are embodied on a more modern host OS such that enhancements to the legacy control system does not have to continue to occur via outdated technology.

In still another case at the virtual device establishment service is used to isolate the guest OS and its native hardware so that neither can connect to external networks or external resources. This is done to ensure that all input provided and output produced from the legacy control system are self contained within the confines of the guest OS or first filtered. through the host OS that can enforce modern security mechanisms against any attempted external accesses. The legacy control system via the guest OS is walled off from the outside world much like a firewall does an Intranet and yet as discussed above the legacy control system can still be enhanced via applications that are developed on modern architectures and can be interfaced to via security mechanisms associated with those modern architectures.

The legacy system encapsulation service represents another and in some cases an enhanced perspective to the virtual device establishment service represented by the method of the .

At the legacy system encapsulation service encapsulates a legacy control system and its native or legacy OS as a virtual device.

One technique for doing this was discussed above with reference to the method of the . Specifically at the legacy system encapsulation service creates a virtual image for the legacy control system that includes the native processing environment of the legacy control system the native OS and the legacy control system. When the virtual image is installed on the host hardware of a host OS the virtual image represents the virtual device or a virtual machine VM .

At the legacy system encapsulation service authenticates the virtual device before that virtual device is permitted to install and execute on host hardware. It is again noted that the host hardware includes more updated or modern host hardware from the native hardware associated with the legacy control system and includes a more updated or modern host OS from the native OS of the legacy control system. Any authentication technique can be used or combination of authentication techniques to authenticate the virtual device.

At the legacy system encapsulation service installs the virtual device within host hardware of the host OS. So now the legacy control system is set to execute on more modern and updated hardware and yet its native hardware is encapsulated within the virtual device so that the legacy control system believes that it is stilt processing on that native hardware. The legacy control system continues to process within the virtual device on its native OS but the virtual device executes on the host hardware.

According to an embodiment at the legacy system encapsulation service prevents external connections that are available to the virtual device within the host OS so that these external connections to external networks and or external resources have to first pass through the modern and updated host OS. The virtual device is walled off within the host hardware and the host OS.

At the legacy system encapsulation service permits the legacy control system via the virtual device to access some devices associated with its original native hardware using legacy native hardware device drivers that the legacy control system is configured to use.

In some cases at the legacy system encapsulation service facilitates connections between the host OS and the native hardware via one or more services provided within the virtual device. For example at the legacy system encapsulation service uses an interface from the virtual device that exposes the native hardware and its devices to the host OS and permits the host OS to access those devices of the native hardware This was discussed at length along with other mechanisms to achieve this above with reference to the method of the .

At the legacy system encapsulation service executes the virtual device within or on the host hardware.

At the legacy system encapsulation service also validates input data gathered on the host OS for the virtual device before that input data is passed through from the host OS to the virtual device and ultimately the legacy control system of the virtual device. Again this can be used to enforce modern or enhanced security that the legacy control system may not have been able to address given its legacy processing environment.

At the legacy system encapsulation service passes the validated input data from the host OS to the virtual device for processing by the legacy control system within its legacy processing environment which is encapsulated within the virtual device.

In an embodiment at the legacy system encapsulation service gathers input data manipulates the input data and or processes a number of enhanced input data services against that validated input data before the validated input data is passed from the host OS to the virtual device 

According to an embodiment at the legacy system encapsulation service processes enhancement services against output data produced by the legacy control system on the virtual device. This is done when the output data is received from the virtual device in response to the validated input data. The enhancement services are processed within the host OS. So not only can input to the legacy control system be enhanced and have added security but output produced by the legacy control system can be enhanced. The input output enhancements occur via services developed and executed within a modern host OS on modern host hardware.

The virtual device establishment system includes a host operating system A and a virtual device configuration service The virtual device establishment system may also include one or more applications . Each of these components and their interactions with one another will now be discussed in turn.

The host OS A is implemented as instructions within a computer readable storage medium that processes on host hardware B such as a modern computer etc. . Example aspects of the host OS A and its features were discussed in detail above with reference to the methods and of the respectively.

The virtual device configuration service is also implemented as instructions within a computer readable storage medium and processes on the host hardware B. Example aspects of the virtual device configuration service and its features were discussed in detail above with reference to the methods and of the respective.

The virtual device configuration service A creates a virtual image or virtual device A that processes as a guest OS A. The virtual device A is a virtual image for a legacy control system a legacy processing environment used by the legacy control system and a legacy OS used by the legacy processing environment. The virtual image or virtual device A is installed and isolated within the host hardware B and that virtual device A is executed as a guest OS A. External access to and from the virtual device A is validated and controlled by the host OS A.

Furthermore legacy hardware B is accessed by the legacy control system by connecting the legacy hardware B to the host hardware B so that the virtual device A can directly access that legacy hardware B.

In an embodiment a generic interface exposes the legacy hardware B to the host OS A and thereby permits the host OS A to also access the legacy hardware . Example techniques for achieving this were presented above with reference to the methods and of the respectively.

In an embodiment the host OS A can use the generic interface to also authenticate the legacy hardware B.

The application is implemented in a computer readable storage medium that processes within the host OS A on the host hardware B. The application gathers and supplies input data to the virtual device A for processing by the legacy control system. The input data is validated and verified for security purposes before that input data is passed from the host OS A to the virtual device A. So the application can service as a form of an enhanced preprocessor for the legacy control system.

In some cases the application can also be used as an enhanced post processor for the legacy control system. Here the application gathers and further alters output data received from the legacy control system via the virtual device A. The output data is produced by the legacy control system in response to the input data supplied by the application via the host OS A.

The virtual device establishment system is another and in some cases enhanced perspective to virtual device establishment system represented by the presented above.

The virtual device establishment system includes a legacy hardware connection service and a guest OS . Each of these will now be discussed in turn.

The legacy hardware connection service is implemented in a computer readable storage medium and processes on a host OS that executes on host hardware. Example aspects of the legacy hardware connection service were presented above with respect to the methods and of the respectively.

The legacy hardware connection service exposes legacy hardware accessed by a legacy control system to the host OS. The legacy control system is encapsulated and isolated for processing within the guest OS .

The legacy hardware connection service permits the legacy control system to access the legacy hardware while the legacy control system executes within the guest OS .

The guest OS is implemented in a computer readable storage medium and also processes on the host hardware. The guest OS may also be considered the virtual device discussed in detail above with reference to the .

In an embodiment the host OS validates and verities for security purposes all input passed from the host OS to the legacy control system via the guest OS

In another case the host OS executes an enhancement service that alters output data produced by the legacy control system via the guest OS .

Also in some situations direct connections to and emanating from the guest OS to external networks and or external resources are prohibited by the host OS.

It is now appreciated how a legacy control system can he executed on modern architectures that utilize modern OS S and still have access to legacy hardware Moreover the legacy control systems can be enhanced via applications developed on and processed from the modern OS S. Still further modern security mechanisms can be automatically and dynamically integrated into the legacy control systems via processing from the modern OS s.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

The Abstract is provided to comply with 37 C.F.R. 1.72 b and will allow the reader to quickly ascertain the nature and gist of the technical disclosure. It is submitted with the understanding that it will not be used to interpret or limit the scope or meaning of the claims.

In the foregoing description of the embodiments various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting that the claimed embodiments have more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Description of the Embodiments with each claim standing on its own as a separate exemplary embodiment.

