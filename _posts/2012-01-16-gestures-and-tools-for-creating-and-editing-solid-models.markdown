---

title: Gestures and tools for creating and editing solid models
abstract: A modeling tool is activated in a 3D modeling application executing on a multi-touch device. A visual representation of a grid system tool is displayed in an active modeling plane and has three separate regions that determine the type of operation to be performed. An existing 3D form is displayed on the tool. A starting touch event of a gesture is received over the existing 3D form within one of the regions. As the gesture is received in the computer, the 3D form may be dynamically extended by adding 3D geometry to the 3D form (thereby adding faces to the 3D form). Alternatively, the 3D form may be scaled (i.e., if the starting touch event occurs over a visual scale grip. Alternatively, if the gesture consists of two taps, a bridge may be created joining the two tapped locations.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08947429&OS=08947429&RS=08947429
owner: Autodesk, Inc.
number: 08947429
owner_city: San Rafael
owner_country: US
publication_date: 20120116
---
This application is related to the following and commonly assigned patent application which application is incorporated by reference herein 

U.S. patent application Ser. No. 13 085 195 filed on Apr. 12 2011 now U.S. Pat. No. 8 860 726 issued on Oct. 14 2014 entitled Transform Manipulator Control by Gregory W. Fowler Jason Bellenger and Hans Frederick Brown 

U.S. patent application Ser. No. 13 351 116 filed on Jan. 16 2012 entitled THREE DIMENSIONAL CONTRIVER TOOL FOR MODELING WITH MULTI TOUCH DEVICES by Gregory W. Fowler Jason Vincent Ma and Hans Frederick Brown and

U.S. patent application Ser. No. 13 351 128 filed on Jan. 16 2012 entitled DYNAMIC CREATION AND MODELING OF SOLID MODELS by Gregory W. Fowler Jason Vincent Ma and Hans Frederick Brown.

The present invention relates generally to three dimensional 3D modeling and in particular to a method apparatus and article of manufacture for dynamically creating and modeling editing a solid model e.g. on a multi touch device .

 Note This application references a number of different publications as indicated throughout the specification by reference numbers enclosed in brackets e.g. x . A list of these different publications ordered according to these reference numbers can be found below in the section entitled References. Each of these publications is incorporated by reference herein. 

Many 3D modeling and drawing applications are used in both desktop and multi touch devices. However none of the existing multi touch 3D modeling or drawing applications provide a comprehensive 3D modeling system that take advantage of the multi touch capabilities available across multiple mobile devices without interfering with basic 3D navigation or requiring proficiency in the art of 3D modeling. Further none of the prior art modeling systems provide the ability to dynamically create and dynamically modify edit a 3D solid model e.g. via user gestures . To better understand the problems and deficiencies of the prior art a description of prior art modeling applications and activities may be useful.

Some prior art modeling applications e.g. the Spaceclaim Engineering application have explored multi touch interactions in the context of 3D modeling tasks. However such prior art applications mimic the interaction available via a mouse pointer. These interactions are not tailored for laymen to use without 3D modeling experience. Many of the operations also require two hand interactions that may not be adequate for smaller devices and require more muscle memory. Further prior art applications involve multiple steps in which 3D solid models are not created dynamically in real time consistent with the user s gestures.

In some cases specific creation tools e.g. extrude revolve offset etc. may have been implemented for multi touch use. However such creation tools are all static modality tools or commands that require proper selection. The tools are detached from the 3D navigation experience and do not fully take advantage of the multi touch input devices.

In view of the above it may be understood that 3D modeling activities and tasks generally imply and require an understanding mastering of concepts such as coordinate systems tool operations tool selection sequence and validity of selections. Accordingly what is needed is the capability to easily perform a variety of modeling operations including creation modification and navigation on a multi touch input device in a dynamic manner without multiple steps or selection requirements.

Embodiments of the invention provide a 3D contriver tool that provides the ability for a user to dynamically in real time create and reshape a 3D geometric form on a multi touch device based on a finger input gesture. Further embodiments of the invention introduce new multi touch gestures and interactions that combine multiple concepts into a simple predictable workflow that mimics how brushes are used on an empty canvas. By simply touching a designated space the user can rapidly and dynamically create forms without having to worry about tool sequencing profiles selection direction etc.

Additionally once a form is laid down in space the user can continue to dynamically adjust the form geometry without having to launch an edit tool or invoke a special mode. By simply re stroking the form the system detects a modification operation automatically switches to that operational mode and allows the user to dynamically reshape the form.

Furthermore embodiments of the invention introduce a soft 3D navigation tumbling activation deactivation method that does not require the usage of multi finger gestures or special modes. This transient navigation consists of tracking multi touch inputs outside a virtual modeling box plane that provides a 3D modeling environment that flows naturally without enforcing mode tool switching or difficult clutch gestures to learn.

Embodiments of the invention enable a tool to perform the above described functionality. Such a tool may also be loaded with more complex geometry to help assemble intricate forms. The tool can automatically recognize connection conditions and blends the stroked geometry onto an existing form in a natural manner. In this interaction the user can also continue adjusting the shape and scaling its outline. Further when complex geometries are used to assemble sophisticated forms the original geometries can be pre defined with a simple rigging system that the user can adjust during the creation interaction.

All of the above functionality is presented to the user as a single tool that is highly context sensitive and used in a dynamic manner to both create and modify a solid model. The tool exposes all of the above interactions without interfering with 3D navigational activities e.g. pan zoom tumble .

In the following description reference is made to the accompanying drawings which form a part hereof and which is shown by way of illustration several embodiments of the present invention. It is understood that other embodiments may be utilized and structural changes may be made without departing from the scope of the present invention.

Embodiments of the invention provide a multi touch 3D modeling system that is based on the idea of using life like drawing tools on a blank canvas. A single tool provides the ability to automatically control creating positioning editing scaling and posing based on the view direction and multi touch events. All of these operations are provided within the same context and without exiting the tool for 3D navigation operations.

Accordingly a user is provided with access to a number of modeling interactions e.g. creating editing that dynamically create base geometry that can be refined and later dynamically sculpted using 3D modeling tools. With the single tool referred to herein as a 3D contriver tool the user can explore new 3D creations without requiring special commands or modes. Such an approach maintains the artistic flow that users appreciate from prior art brushing and stroking systems.

In one embodiment the computer operates by the general purpose processor A performing instructions defined by the computer program under control of an operating system . The computer program and or the operating system may be stored in the memory and may interface with the user and or other devices to accept input and commands and based on such input and commands and the instructions defined by the computer program and operating system to provide output and results.

Output results may be presented on the display or provided to another device for presentation or further processing or action. In one embodiment the display comprises a liquid crystal display LCD having a plurality of separately addressable liquid crystals. Alternatively the display may comprise a light emitting diode LED display having clusters of red green and blue diodes driven together to form full color pixels. Each liquid crystal or pixel of the display changes to an opaque or translucent state to form a part of the image on the display in response to the data or information generated by the processor from the application of the instructions of the computer program and or operating system to the input and commands. The image may be provided through a graphical user interface GUI module A. Although the GUI module A is depicted as a separate module the instructions performing the GUI functions can be resident or distributed in the operating system the computer program or implemented with special purpose memory and processors.

In one or more embodiments the display is integrated with into the computer and comprises a multi touch device having a touch sensing surface e.g. track pod or touch screen with the ability to recognize the presence of two or more points of contact with the surface. Examples of multi touch devices include mobile devices e.g. iPhone Nexus S Droid devices etc. tablet computers e.g. iPad HP Touchpad portable handheld game music video player console devices e.g. iPod Touch MP3 players Nintendo 3DS PlayStation Portable etc. touch tables and walls e.g. where an image is projected through acrylic and or glass and the image is then backlit with LEDs .

Some or all of the operations performed by the computer according to the computer program instructions may be implemented in a special purpose processor B. In this embodiment the some or all of the computer program instructions may be implemented via firmware instructions stored in a read only memory ROM a programmable read only memory PROM or flash memory within the special purpose processor B or in memory . The special purpose processor B may also be hardwired through circuit design to perform some or all of the operations to implement the present invention. Further the special purpose processor B may be a hybrid processor which includes dedicated circuitry for performing a subset of functions and other circuits for performing more general functions such as responding to computer program instructions. In one embodiment the special purpose processor is an application specific integrated circuit ASIC .

The computer may also implement a compiler which allows an application program written in a programming language such as COBOL Pascal C FORTRAN or other language to be translated into processor readable code. Alternatively the compiler may be an interpreter that executes instructions source code directly translates source code into an intermediate representation that is executed or that executes stored precompiled code. Such source code may be written in a variety of programming languages such as Java Perl Basic etc. After completion the application or computer program accesses and manipulates data accepted from I O devices and stored in the memory of the computer using the relationships and logic that was generated using the compiler .

The computer also optionally comprises an external communication device such as a modem satellite link Ethernet card or other device for accepting input from and providing output to other computers .

In one embodiment instructions implementing the operating system the computer program and the compiler are tangibly embodied in a non transient computer readable medium e.g. data storage device which could include one or more fixed or removable data storage devices such as a zip drive floppy disc drive hard drive CD ROM drive tape drive etc. Further the operating system and the computer program are comprised of computer program instructions which when accessed read and executed by the computer causes the computer to perform the steps necessary to implement and or use the present invention or to load the program of instructions into a memory thus creating a special purpose data structure causing the computer to operate as a specially programmed computer executing the method steps described herein. Computer program and or operating instructions may also be tangibly embodied in memory and or data communications devices thereby making a computer program product or article of manufacture according to the invention. As such the terms article of manufacture program storage device and computer program product as used herein are intended to encompass a computer program accessible from any computer readable device or media.

Of course those skilled in the art will recognize that any combination of the above components or any number of different components peripherals and other devices may be used with the computer .

A network such as the Internet connects clients to server computers . Network may utilize ethernet coaxial cable wireless communications radio frequency RF etc. to connect and provide the communication between clients and servers . Clients may execute a client application or web browser and communicate with server computers executing web servers . Such a web browser is typically a program such as MICROSOFT INTERNET EXPLORER MOZILLA FIREFOX OPERA APPLE SAFARI etc. Further the software executing on clients may be downloaded from server computer to client computers and installed as a plug in or ACTIVEX control of a web browser. Accordingly clients may utilize ACTIVEX components component object model COM or distributed COM DCOM components to provide a user interface on a display of client . The web server is typically a program such as MICROSOFT S INTERNET INFORMATION SERVER 

Web server may host an Active Server Page ASP or Internet Server Application Programming Interface ISAPI application which may be executing scripts. The scripts invoke objects that execute business logic referred to as business objects . The business objects then manipulate data in database through a database management system DBMS . Alternatively database may be part of or connected directly to client instead of communicating obtaining the information from database across network . When a developer encapsulates the business functionality into objects the system may be referred to as a component object model COM system. Accordingly the scripts executing on web server and or application invoke COM objects that implement the business logic. Further server may utilize MICROSOFT S Transaction Server MTS to access required data stored in database via an interface such as ADO Active Data Objects OLE DB Object Linking and Embedding DataBase or ODBC Open DataBase Connectivity .

Generally these components all comprise logic and or data that is embodied in or retrievable from device medium signal or carrier e.g. a data storage device a data communications device a remote computer or device coupled to the computer via a network or via another data communications device etc. Moreover this logic and or data when read executed and or interpreted results in the steps necessary to implement and or use the present invention being performed.

Although the term user computer client computer and or server computer is referred to herein it is understood that such computers and may include thin client devices with limited or full processing capabilities portable devices such as cell phones notebook computers pocket computers multi touch devices and or any other devices with suitable processing communication and input output capability.

Of course those skilled in the art will recognize that any combination of the above components or any number of different components peripherals and other devices may be used with computers and .

Embodiments of the invention are implemented as a software application 3D contriver tool on a client or server computer . Further as described above the client or server computer may comprise a thin client device or a portable device that has a multi touch based display.

The 3D contriver tool for multi touch devices can be grouped in different clusters of functionality that are described in the present application and or the related applications identified and cross referenced above as follows 

Embodiments of the invention e.g. system will provide a single tool that permits multiple dynamic modeling operations and navigation within the same context without requiring complex gestures or modes.

The center region represents an area that will generate geometry if a touch event is detected see below for more detail regarding modeling operations .

The first outer region represents an area that will either trigger a re stocking operation re brushing the geometry after the initial creation when a form is active or trigger a tumbling orbit navigation if no form is active see below for more details on re stroking modeling operations .

The second outer region fall off grid represents an area that will always trigger a tumbling orbit navigation if a touch event is detected. Any other touch event detected outside of the fall off grid will also trigger tumbling orbit navigation.

Embodiments of the invention perform the desired operation based on where the touch event commences and not where the gesture following the touch event proceeds. Thus merely by commencing a touch event gesture at a particular location with respect to the grid a particular operation is performed. The FIGs. and description that follow illustrate examples of the different operations that may be performed based on the grid .

To respond to the user tumbling orbiting in space embodiments of the invention dynamically switch to one of the dominant planes XY XZ YZ and update the graphical representation of the grid accordingly.

In view of it may be noted that embodiments of the invention evaluate the action that is to be executed based on where the touch event begins commences rather than where the touch event proceeds or ends. Accordingly in since the touch event gesture begins in area a navigation e.g. tumbling orbiting operation is performed.

The user starts brushing from a position inside the modeling grid . As the user drags a finger along any path the system dynamically creates a 3D form . The form shaping is interactive and updates the form every time it samples the gesture . Such form shaping is performed dynamically in real time as the user performs the stroke gesture. Accordingly as the user is moving a finger the model is changing. In the prior art the ability to dynamically create a model in such a manner was not provided. Instead prior art users were required to draw a curve select the drawn curve and select a profile. Thereafter the user would perform a sweep jigging operation process. Such a sweep operation is not dynamically created as the user inputs a gesture but instead is based on an already drawn curve that is selected by the user.

Once the user finishes brushing i.e. at describing the path the system finishes the shaping of the 3D form . The user can then tumble orbit e.g. as described above with respect to or re stroke the 3D form e.g. as described below .

Thus since the gesture commenced in region a creation modeling operation is performed based on the user s gesture . As illustrated a 3D form is dynamically created and conforms to the shape of the gesture stroke . To perform the modeling creation operation the user did not need to select a creation operation e.g. from a menu or otherwise . Instead the user simply began the gesture within region . In response a 3D form is displayed on the grid and is dynamically updated to conform to the stroke while the stroke is drawn. Again since the gesture stroke began inside of region it doesn t matter if the stroke proceeds outside of region . Instead what enables the modeling operation is where the stroke commences.

Accordingly the grid system of the invention enables the user to perform a desired operation merely by beginning a gesture in a particular area region of the grid system .

To create the 3D form in real time a pair of curves may be created and used to produce a generalized tube surface that interpolates both curves simultaneously. Embodiments of the invention may utilize a Catmull Clark subdivision surface as the tube surface. With such a subdivision surface the problem reduces to building an appropriate base mesh whose limit surface shall be the tube surface that interpolates the given curves.

Embodiments of the invention assume that such curves are already in a form ready to use and that the curves have compatible lengths orientation and structure. Further both curves may be required to be uniform cubic b splines that have the same number of spans. Having such a requirement may be necessary because the CV control vertex hulls of the curves may be used to guide the building of the base mesh.

Many works of curve interpolating subdivision surfaces can be found in academia. Generally they fall into the following categories those that build the base mesh specifically for the curve to be interpolated 1 8 5 6 those that tag edges of an existing base mesh and have enhanced rules of subdivision 2 or those that provide entirely new schemes 3 .

In view of the above the first step is that of building the base mesh that encompasses two polygonal complexes so that the final subdivision surface will interpolate both curves at once e.g. see 5 and 6 for details regarding polygonal complexes . To configure the polygonal complex for one curve embodiments of the invention build a section of a polygonal complex that interpolates a CV of the curve cas 

In other words one must determine where to put the points tand bin order to place m. illustrates a polygonal complex in accordance with one or more embodiments of the invention. can be constructed such that 1 2 3 

Let o t p a c p and right arrow over c i.e. right arrow over c is unit length . An expression of o may be found in terms of a.

By construction the vector m cis parallel right arrow over c . Also the restriction that tand bare symmetric across right arrow over c implies that the projections of c tand c bonto right arrow over c are equivalent to c p . Therefore to proceed onwards from 5 one only needs to consider the aforementioned projections 

Making the profile a regular hexagon is the next step. Having figured out the value of o in terms of the single variable a one may proceed to express the value of a in terms of the only known values of cand c. illustrates both sides of polygonal complex in accordance with one or more embodiments of the invention. From not drawn to scale it is easy to see that 2 8 

If the base mesh profile is to be a regular hexagon the sides must have the same length. In particular 9 

If you substitute equation 11 into equation 8 and apply the knowledge that in a regular hexagon 60 cos the equation for a can be had 

Thus both o and a are now expressed purely by the distance between cand c which are the only inputs with which processing began. It is now a trivial exercise to construct the points t b and mfor the CV c and similarly for c e.g. see .

It may be noted that the hexagonal profile need not be regular. Using equations 7 and 12 one can vary o and a within limits to obtain variations of the shape of the tube. The limits on the length a is 0 c c . When a c c the profile turns into a 4 sided profile as described below. Furthermore the polygonal complexes for both sides need not be symmetric the restriction c p c p can be relaxed so long as c p c p 

One can also imagine using a square as the profile of the polygonal complex base mesh as illustrated in . In this case tand tare now the same point same for b s and p s . In they are now t b and p respectively. Now because 45 tan 1 equation 7 simplifies to 3 2 14 

Again just like the case of the hexagonal profile the 4 sided profile need not be a square. The point p can be located anywhere between cand c and then oand ocan be different even. However this construction method can only yield a rhombic profile and is not able to create a rectangular profile. A rectangular profile where the angles at m m t and b of the profile are 90 can be created but the derivation may have many variations depending on the constraints at hand.

To ensure end point interpolation various additional processing may be required. If both curve were closed then simply creating the base mesh via polygonal complexes is sufficient to create a subdivision surface that interpolates the two closed curves. However if the curves were open then there needs to be extra work done to the polygonal complexes such that the subdivision surface would interpolate the open ends of the curves.

Some literature on the subject of curve interpolating subdivision surfaces gloss over the case of the curve being open instead choosing to focus on interpolating either closed boundary curves or networks of curves the open ends of all curves are coincident with at least one other curve e.g. see 4 which describes subdivision surfaces interpolating open curves but is limited to Doo Sabin quadratic surfaces .

In one or more embodiments of the invention the CV hull of a cubic b spline can be used as the base polygon for a Catmull Clark subdivision curve. However if the b spline has full multiplicity knots for the end CVs the respective Catmull Clark subdivision curve will ignore this and the resulting subdivision curve will not interpolate the end CVs as expected. Therefore if one were to use the CVs of an open curve to generate the polygonal complex as described above the resulting subdivision surface may also fail to interpolate the endpoints of the input curves.

Embodiments of the invention may apply the techniques described in 7 to modify the CV hull of the input open curves. Four techniques may be used to modify the end CVs of the cubic b spline curve e.g. see 7 . After experimentation embodiments of the invention utilize a method that modifies the last two 2 CVs on either end of the hull to satisfy the so called Bezier end constraint 

In view of the above embodiments of the invention dynamically create the curves as such curves are generated via user gesture that are used to dynamically create a base mesh which in turn are dynamically used to create a tube surface that interpolates the given curves. Thus the first step in such a process is to build a base mesh from the curves. illustrate the generation of a base mesh in accordance with one or more embodiments of the invention. In the user begins the gesture at point from within grid region . Since the user is within grid region a creation operation is performed. As the user drags his finger the system dynamically creates the base mesh . The shape of the base mesh conforms to and is consistent with the user s gesture . As illustrated in C and D the base mesh is continuously and dynamically created in real time as the gesture is input by the user and sampled. As illustrated in the CV hulls of the curves i.e. dynamically created based on the user s gesture in real time are used to guide the building of the base mesh .

Once the base mesh is created the limit surface of the base mesh is used as the tube surface that interpolates the given curves. As used herein the limit surface is referred to as the sub division surface. illustrate a subdivision surface that is created dynamically consistent with a base mesh. In the user begins the gesture at point and the system dynamically creates the subdivision 3D surface in real time based on a base mesh . further illustrate the dynamic creation of the subdivision surface in real time as the gesture is input by the user.

In view of the above it may be seen that the interpolation to create the subdivision surface is performed in real time. In this regard the system utilizes the base mesh and as the gesture is input the system determines the faces that should be added interpolated based on the base mesh. Such interpolation and 3D subdivision surface creation is performed dynamically as the gesture is input as illustrated in .

The user starts re stroking from a position A inside the modeling grid . As the user drags his her finger along any path A the system dynamically re shapes the 3D form . The form re shaping is dynamic interactive and updates the form every time it samples the gesture i.e. dynamically in real time .

In the re stroking modifies the 3D form in relationship to the current XY grid. Once the user finishes re stroking i.e. at A thereby describing the path A the system finishes re shaping the 3D form and the user can then either tumble orbit or re stroke the 3D form .

Accordingly as described above since the operation gesture A is commenced at a location A within area region a re stroking operation is performed i.e. since form is active . If the operation were conducted outside of region i.e. in region an orbit tumbling operation would be conducted.

In the user continues interacting with the modeling tool and the model of . The image shows the final state of the grid system while the modeling tool is active . The captured gesture F occurs commences at point F outside of the grid system i.e. in region thus invoking a tumble orbit. The resulting viewing angle based on the gesture F that stops at point F determines that the YZ plane is dominant and all re stroking operation will be projected to the YZ plane.

The re stroking modifies the 3D form in relationship to the current YZ grid. Once the user has finished the re stroking gesture at point G describing the path G the system finishes the re shaping of the 3D form and the user can then either tumble orbit or re stroke the 3D form .

Thus as described above since the stroke G begins at a point G within region a reshaping operation is performed. Further the operation is performed in the YZ plane due to the rotation tumbling that was performed as described above with respect to . In addition similar to re stroking on the same plane described above the re stroking operation in a different plane is performed dynamically as the gesture is drawn by the user.

The user starts brushing from two positions A and B inside the modeling grid . This can be done using two hands or two fingers on the same hand. As the user drags his her fingers along any paths A and B the system dynamically creates a 3D form . The form shaping is interactive and updates the form every time it samples the gesture.

Once the user has finished brushing at points A and B thereby describing the paths A and B the system finishes shaping the 3D form . The user can then either tumble orbit or re stroke the 3D form .

Heuristics may also be in place to differentiate these creation driven dual touch events from other similar multi touch gestures like pinching. Pinching may be used in the prior art for zooming and panning

The modeling tool and interaction described above may also be used to add shapes to newly created 3D forms. In this regard a tool may be used to modify and add 3D geometry to an already existing form e.g. based on direction .

The user starts brushing from a position on the existing 3D form . As the user drags his her finger along any path the system dynamically adds to the existing 3D form . The form shaping is interactive and updates the form every time the gesture is sampled. The additional shape added to the 3D form is relative to the current XY grid. In other words based on the view direction and the dynamic stroking from to an extrusion comes out of the face . As the user moves his her finger the model is dynamically changing.

Once the user finishes brushing describing the path the system finishes shaping the 3D form i.e. by adding geometry . The user can then either tumble orbit or re stroke the 3D form e.g. see above for details regarding re stroke modeling operations .

In the prior art to modify the geometry of form the user was required to first select create draw a profile then select a process to create the geometry e.g. jigging e.g. drawing a curve selecting a geometry selecting a profile and then sweeping the curve in a non dynamic manner . In this regard the prior art fails to provide a mechanism for dynamically creating and displaying a shape as an arbitrary gesture is created.

As described above with respect to the creation of the geometry a base mesh may be used created as the gesture is performed. As the user is extruding with the finger the system is calibrating how many additional faces should be interjected. In other words new faces and a new base mesh are created by the user dynamically as an arbitrary gesture is drawn.

In the user continues interaction with the modeling tool of . The user starts re stroking from a position inside the modeling grid. As the user drags his her finger along any path the system dynamically re shapes the 3D form . The form re shaping is interactive and updates the form every time the gesture is sampled. The re stroking modifies the 3D form relative to the current XY grid.

Once the user finishes re stroking describing the path the system finishes the re shaping of the 3D form . The user can then either tumble orbit or re stroke the 3D form . Thus similar to that described above since the user commences the operation from within area a re stroking operation is performed rather than an orbit creation operation. The re stroking operation is performed with respect to the existing geometry and serves to modify a face of the existing geometry .

In the user begins the gesture at point outside of the grid area and hence an orbit operation is performed thereby orbiting the geometry from the XY plane to the XZ plane. Similar to that described above both the geometry and the underlying grid are orbited and displayed in the new orientation.

In the user continues interaction with the modeling tool and has tumbled orbited thereby updating the plane to the XZ grid as described with respect to . The user starts re stroking from a position inside the first outer grid i.e. area . As the user drags his her finger along the path the system dynamically re shapes the 3D form . The form re shaping is interactive and updates the form every time the gesture is sampled. The re stroking modifies the 3D form in relationship to the current XZ grid.

Once the user finishes re stroking describing the path the system finishes re shaping the 3D form . The user can then either tumble orbit or re stroke the 3D form .

To utilize the bridging operation and to create a bridge the user must have the modeling tool active. The user taps a given position on the 3D form . The system highlights a section of the form under the original tap . Such highlighting may display the section in a different color may highlight the section or display the section in a visually distinguishable manner from the remainder of the form . The user then taps again on another position . Immediately after the system captures the second position a connecting shape is generated from the inverted region and is appended to the 3D form .

Once the system captures the two tap gestures and describing the new appended shape the user can then either tumble orbit or re stroke the new 3D form .

In view of the above if a user performs a tap operation the system will wait for another tap operation. If a second tap is detected a bridging operation is dynamically performed. Further such a bridging operation is performed using the same base 3D contriver tool that is used to perform all of the other operations described herein.

The user starts re stroking from a position inside the first outer grid i.e. in area thereby invoking a re stroking operation. As the user drags his her finger along any path the system dynamically re shapes the 3D form . The form re shaping is interactive and updates the form every time the gesture is sampled. Further the re stroking modifies the 3D form relative to the current XZ grid.

Once the user finishes re stroking thereby describing the path the system finishes re shaping the 3D form . The user can then either tumble orbit or re stroke the 3D form .

The user starts a brushing gesture from a position A on the existing 3D form . As the user drags his her finger along any path the system dynamically adds to both sides of the original 3D form . A line plane of symmetry is used to determine where how the mirroring is performed. Such a line plane of symmetry may be determined based on a variety of methods e.g. based on the base mesh automatically determined by the system drawn by the user etc. . In this regard the creation editing of the 3D form may be driven by a pre defined mirror plane or a plane that is perpendicular to the current modeling plane.

Further when the gesture begins i.e. at area A the starting point B of the corresponding mirrored face is also displayed e.g. in a visually distinguishable manner such as highlighting or different coloring . The form shaping is interactive and updates the form every time the gesture is sampled. The additional shape to the 3D forms is done relative to the current XY grid. Once the user finishes brushing describing the path the system finishes shaping the 3D form . The user can then either tumble orbit or re stroke the 3D form .

In view of the above embodiments of the invention provide a 3D contriver tool system for multi touch devices that enables the creation orbiting and modification of 3D forms. In other words a unique set of gestures and transient graphic manipulators are provided that are closely related to a 2D brushing workflow and can build up complex forms with little to no 3D modeling expertise. The tool is tightly integrated with 3D navigation and manages the coordinate system in a way that lets the user create geometry and edit geometry without changing modes or running specific tools commands.

 2 3D modeling tools that are activated and deactivated using a modeling plane and tumbling operation and are always available outside of the plane without having to change modes 

 3 when a gesture is detected in the modeling plane the system generates a corresponding form based on the stroke direction and the active modeling plane 

 4 when a gesture is detected over an existing shape the system extends the form following the stroke direction and the active modeling plane 

 5 the stroking and selection model in the 3D contriver tool are aware of symmetry and can drive creation editing over a pre defined mirror plane or a plane that is perpendicular to the current modeling plane.

Regardless of whether a 2 finger drag 1 finger drag or taps are detected the multi touch device via the contriver tool determines the zone in which the touch event is detected. Zone B is also known as area zone C is area and zone D is area of . The different zones are used to determine whether a creation modification or orbiting operation are performed.

If a 2 finger drag occurs in zone B a determination is made regarding whether geometry exists under the touch event at . If no geometry exists under the touch event a two finger modeling operation is performed at e.g. as described above with respect to .

If no geometry is detected under the touch event at or if the touch event occurs in zone C or zone D a navigation pan or zoom operation is performed based on the gesture at i.e. as described above .

If a 1 finger drag event is detected in zone B a determination is made regarding whether there is geometry under the touch event at . If no geometry is detected a 1 finger modeling operation is performed at e.g. as described above . However if geometry is detected the system determines that a modeling operation from the face is to be performed. A determination is then made if the symmetry modeling tool is also active at . If the mirror symmetry tool is not active modeling from the face is performed without mirroring at . Alternatively if the mirror symmetry tool is active modeling from the face is performed with mirroring at .

If a 1 finger drag operation is detected in zone C the system again determines if there is geometry under the touch event at . If geometry exists under the touch event a re stroking operation is to be performed and the system determines if an orbit tumbling operation has been performed to change the plane from which the 3D geometry was created at . In other words determination determines if the re stroking is to be performed on the same original plane as which the geometry was originally created. If a tumble orbit operation has been performed i.e. the plane on which the 3D geometry is displayed is different the re stroking is performed on the different plane at step . If the plane has not been modified the re stroking is performed on the original plane at .

Returning to determination if there is no geometry under the touch or if the 1 finger drag touch event occurred in zone D a navigation pan or zoom operation is performed at .

If a 1 finger tap followed by a 2 finger tap touch event is detected in zone B a determination is again made regarding whether there is geometry under the touch event at step . If geometry exists under the touch event a 2 face bridging operation is performed. However if no geometry exists under the touch event or if the tap operations occurred in zone C and or zone D no action is performed at .

In view of the above it may be noted that all of the various operations including the creation of a 3D form the modeling from the face including a mirroring operation the re stroking of the 3D form on the same or different planes the creating of a bridge between two faces i.e. from one tap location to a second tap location and the tumbling orbiting are all performed using the single 3D contriver tool without switching modes or requiring a complex set of user actions. Further all of the actions described are performed dynamically as the user performs a gesture.

This concludes the description of the preferred embodiment of the invention. The following describes some alternative embodiments for accomplishing the present invention. For example any type of computer such as a multi touch device mainframe minicomputer personal computer or computer configuration such as a timesharing mainframe local area network or standalone personal computer could be used with the present invention.

In summary embodiments of the invention provide a single tool that is displayed with different regions. The single tool provides the ability for the user to perform a variety of operations simply by beginning a touch event or cursor click event within a particular region. The tool may be used to navigate tumble a 3D model create a 3D geometric form e.g. on a blank canvas or otherwise and or edit an existing 3D geometric form. The operation selected performed is based on where the touch event begins and not where the gesture associated with the touch event progresses. Nonetheless once an operation is selected the operation is based on the user s gesture.

The foregoing description of the preferred embodiment of the invention has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise form disclosed. Many modifications and variations are possible in light of the above teaching. It is intended that the scope of the invention be limited not by this detailed description but rather by the claims appended hereto.

 1 A. M. Abbas. A Subdivision Surface Interpolating Arbitrarily Intersecting Network of Curves under Minimal Constraints. cgi2010.miralab.unige.ch 0 0 3.

 2 H. Biermann I. M. Martin D. Zorin and F. Bernardini. Sharp features on multiresolution subdivision surfaces. Proceedings Ninth Pacific Conference on Computer Graphics and Applications. Pacific Graphics 2001 pages 140 149.

 3 Adi Levin. Interpolating Nets of Curves by Smooth Subdivision Surfaces. Proceedings of SIGGRAPH 99 Computer Graphics Proceedings Annual Conference Series pages 57 64 1999.

 4 a. Nasri. Interpolation of Open Curves by Recursive Subdivision Surfaces. Mathematics of Surfaces VII pages 173 188 1997.

 5 a. Nasri W. Bou Karam and F. Samavati. Sketch based subdivision models. In Proceedings of the 6th Eurographics Symposium on Sketch Based Interfaces and Modeling SBIM 09 volume 1 page 53 New York N.Y. USA 2009. ACM Press.

 6 A. H. Nasri. Constructing polygonal complexes with shape handles for curve interpolation by subdivision surfaces. 1. Computer Aided Design 33 11 753 765 September 2001.

 7 Ahmad H. Nasri and Malcolm A. Sabin Taxonomy of Interpolation Constraints on Recursive Subdivision Curves The Visual Computer Volume 18 Issue 5 6 Pages 382 403 14 May 2002.

 8 S Schaefer J Warren and D Zorin. Lofting curve networks using subdivision surfaces. SGP 04 Proc of the 2004 EurographicsACM SIGGRAPH symposium on Geometry processing pages 103 114 2004.

