---

title: Runtime code replacement
abstract: Runtime code replacement at a client-side Web application is provided, and preferably comprises: determining that source code of a Web application has been updated at a server; retrieving the updated source code; and replacing existing runtime code at a running client-side Web application with the updated source code. Replacing existing runtime code may replace live objects in a memory of a Web browser on which the client-side Web application is running, without requiring a restart of the client-side application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08806469&OS=08806469&RS=08806469
owner: International Business Machines Corporation
number: 08806469
owner_city: Armonk
owner_country: US
publication_date: 20120124
---
The invention relates to the field of client side execution of Web applications. In particular the invention relates to runtime code replacement at client side Web applications.

A common debugging technique used with the Java language is Hot Code Replace HCR . HCR allows a debugger to transmit new code to a Java Virtual Machine VM allowing modification of the code in a running application. Restarting the application is not required and therefore this approach enables problems to be fixed quickly. Java and all Java based trademarks and logos are trademarks or registered trademarks of Oracle Corporation and or its affiliates in the United States other countries or both. 

A Java VM allows a debugger to connect directly to a known port over transmission control protocol TCP to the integrated development environment IDE and interact using a known application programming interface API . The direct relationship between the Java IDE and the VM and an associated API allows the IDE to directly control the VM resources and hence directly replace applicable bits of code.

HCR in Java works well because the language is strongly typed and so it is possible from within the VM to identify all objects in memory of a certain type and hence which need to have their functionality replaced.

In Web applications the model is usually different in that the application running in the client browser receives each script using a one time HTTP Hypertext Transfer Protocol request to the Web server which loads the script from disk.

As Web applications become more complex more code is executed on the client e.g. the browser application at the client . Reloading such an application after every minor client side code change can be tedious.

According to a first aspect of the present invention there is provided runtime code replacement at a client side Web application comprising determining that source code of a Web application has been updated at a server retrieving the updated source code and replacing existing runtime code at a running client side Web application with the updated source code. The client side Web application may be provided in JavaScript and the replaced runtime code may comprise live objects in a memory of a Web browser on which the client side Web application is running In a preferred embodiment no restart of the client side Web application or browser page refresh is required. Preferably the source files that produced the runtime code are tracked to determine which runtime code should be replaced. Embodiments of the present invention may be provided as one or more computer program stored on a computer readable medium system s and or method s .

It will be appreciated that for simplicity and clarity of illustration elements shown in the figures have not necessarily been drawn to scale. For example the dimensions of some of the elements may be exaggerated relative to other elements for clarity. Further where considered appropriate reference numbers may be repeated among the figures to indicate corresponding or analogous features.

In the following detailed description numerous specific details are set forth in order to provide a thorough understanding of the invention. However it will be understood by those skilled in the art that the present invention may be practiced without these specific details. In other instances well known methods procedures and components have not been described in detail so as not to obscure the present invention.

An embodiment of the present invention enables the live replacement of client side code in a running Web application without requiring a restart of the application or browser page refresh. The described approaches comprise determining that code needs to be updated retrieving the new code and replacing existing runtime code with the newly retrieved code.

Referring to a flow diagram shows an embodiment of a method carried out at a client running a Web application. The method may be carried out during development of the Web application.

Source code files at the server hosting the Web application are monitored . It is determined if the source code files have been updated . If they have not been updated the method continues to monitor the source code files.

If the source code files are updated the new code is retrieved from the server. The running code of the Web application at the client is replaced with the updated code.

A client system includes a browser running a client side Web application . The browser includes memory storing live objects of the client side Web application .

The client side Web application may be provided in Web application code such as JavaScript. JavaScript is an implementation of the ECMAScript language standard and is primarily used in the form of client side JavaScript implemented as part of a Web browser in order to provide enhanced user interfaces and dynamic websites. This enables programmatic access to computational objects within a host environment. It can be characterized as a prototype based object oriented scripting language that is dynamic weakly typed and has first class functions.

The source code of the Web application is hosted at a server system . The Web application includes source code updates provided at the server system . A code update component is provided for updating running code in the client side Web application on the client system . Running client side code of a Web application needs to be replaced when the source code files on the server system are updated by a developer. The code update component may be local to the client system and may execute from within the browser . As an alternative to the structure shown in the code update component may be part of the client side Web application .

The code update component includes an update detector component . The update detector component may use various different mechanisms for detecting source code updates.

A first mechanism for the update detection uses a manual request component which can be activated manually by a developer. For example the manual activation may occur by executing a particular JavaScript function using a debugger tool such as Firebug or through pre designed interaction with the Web application itself for example by pressing a button .

A second mechanism for the update detection is continuous client side polling of loaded JavaScript files with requests to the server. For example this may comprise using If Modified Since HTTP headers or HTTP HEAD requests to determine if the script file has been updated. This option would require network traffic that would increase with the number of scripts.

A third mechanism for the update detection is a server daemon constantly checking file modification timestamps of all scripts and communication between this daemon and the client side Web application code. This option would require minimal network traffic but requires a server side component to always be running plus client side code to facilitate the communication.

The code update component includes a code retriever component . The retrieval of the new code can be achieved using the same method that was used to retrieve it initially. For example the retrieval may be performed by adding a tag to the application s DOM document object model or an explicit Ajax request and JavaScript eval function.

The code update component includes a code replacement component . There are many ways of replacing the running code within the application with varying degrees of complexity reliability and development requirements. Two such approaches are discussed below with implemented code examples and are termed re running scripts and prototype replacing herein.

Re running scripts is the more basic approach simply involving the re evaluating executing of the new JavaScript. This requires very little code to enable this functionality but does require application scripts to be written with the anticipation that that they may be executed multiple times. This approach may be used for simple circumstances.

Example code for a Loader and a Module are shown at and respectively in . The meaning of this code will be readily understood by those of skill in the art.

The prototype replacing approach allows scripts to be reloaded if they conform to some kind of module specification and generic module loading mechanism such as that defined by CommonJS. Each relevant script is treated as a module and all modules are reloaded when required. In the most basic case such as that shown in the example code of the module provides a JavaScript object and when re loaded the previous object s prototype is replaced with the new one. This allows existing object instances to use new JavaScript code for their inherited functions.

Example code for a Loader Main function and MyObject function are shown at and respectively of . The meaning of this code will be readily understood by those of skill in the art.

In both approaches the example code demonstrates the functionality in the most basic of forms. More complexity may be incorporated.

The prior art use of JavaScript in Web applications has some problems that need to be overcome. There is limited notion of types and hence the more complex hot replacement code approach of prototype replacing works by tracking which source files produced which modules and hence which objects should be replaced when new code is retrieved.

Extra client side code is provided when using an embodiment of the present invention which will explicitly request the new code and then replace live objects in the memory of the browser. Rather than being driven by the IDE the code reload is driven by the application itself.

For performance network traffic and basic requirement reasons an embodiment of the present invention may be used during development and not included in a production application. This could be done with a debug flag a build option or simply removing the functionality before release.

A client side Web application live code replacement system may be provided as a service to a customer over a network.

Referring to an exemplary system for implementing aspects of the invention includes a data processing system suitable for storing and or executing program code including at least one processor coupled directly or indirectly to memory elements through a bus system . The memory elements can include local memory employed during actual execution of the program code bulk storage and cache memories which provide temporary storage of at least some program code in order to reduce the number of times code must be retrieved from bulk storage during execution.

The memory elements may include system memory in the form of read only memory ROM and random access memory RAM . A basic input output system BIOS may be stored in ROM . System software may be stored in RAM including operating system software . Software applications may also be stored in RAM .

The system may also include a primary storage means such as a magnetic hard disk drive and secondary storage means such as a magnetic disc drive and or an optical disc drive. The drives and their associated computer readable media provide non volatile storage of computer executable instructions data structures program modules and other data for the system . Software applications may be stored on the primary and secondary storage means as well as in the system memory .

The computing system may operate in a networked environment using logical connections to one or more remote computers via a network adapter .

Input output devices can be coupled to the system either directly or through intervening I O controllers. A user may enter commands and information into the system through input devices such as a keyboard pointing device or other input devices for example microphone joy stick game pad satellite dish scanner or the like . Output devices may include speakers printers etc. A display device is also connected to system bus via an interface such as video adapter .

The invention can take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. In a preferred embodiment the invention is implemented in software which includes but is not limited to firmware resident software microcode etc.

The invention can take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium can be any apparatus that can contain or store the program for use by or in connection with the instruction execution system apparatus or device.

The medium can be an electronic magnetic optical electromagnetic or semiconductor system or apparatus or device . Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

Improvements and modifications can be made to the foregoing without departing from the scope of the present invention.

