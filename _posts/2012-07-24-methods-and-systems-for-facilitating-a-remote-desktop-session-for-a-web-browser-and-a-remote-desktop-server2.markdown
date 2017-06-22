---

title: Methods and systems for facilitating a remote desktop session for a web browser and a remote desktop server
abstract: Examples of methods, systems, apparatus, and machine-readable storage media are provided to facilitate access and control of a remote desktop of a remote machine by a web browser of a client device through a web server without installing proprietary plug-ins or protocols on the client device. A web server may translate user input requests from a windows web browser into input calls compatible with a remote desktop display protocol. The web server may receive remote desktop drawing commands from the remote machine and translate the remote desktop drawing commands into web browser drawing updates compatible with the windows web browser. A web server may communicate with the windows web browser and a remote machine via HTTP and a remote desktop display protocol, accordingly.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09535560&OS=09535560&RS=09535560
owner: WYSE TECHNOLOGY L.L.C.
number: 09535560
owner_city: San Jose
owner_country: US
publication_date: 20120724
---
The present application claims the benefit of priority from U.S. Provisional Patent Application Ser. No. 61 669 639 entitled WEB SERVER FOR REMOTE DESKTOP DISPLAY PROTOCOL filed on Jul. 9 2012. The present application is also a continuation in part of U.S. patent application Ser. No. 12 965 820 entitled METHODS AND SYSTEMS FOR CONDUCTING A REMOTE DESKTOP SESSION VIA HTML THAT SUPPORTS A 2D CANVAS AND DYNAMIC DRAWING filed on Dec. 10 2010. All of the foregoing applications are hereby incorporated by reference in their entirety for all purposes.

The subject technology relates in general to communications and processing and for example to methods and systems for facilitating accessing and or controlling a remote desktop of a remote machine in real time by a web browser of a client device via HTTP.

Traditional implementations of remote desktop protocols enable a remote user to access his or her desktop or applications from a client device over a LAN or WAN network topology to a server.

The traditional approach is for a software infrastructure vendor to support a specific public or proprietary remote desktop display protocol which is native or installed on a server. To access the server using a remote desktop protocol a client typically needs to have a protocol specific software application that executes on the user s specific operating system and platform or plug in for a specific browser.

Conventional approaches are thus cumbersome to users. Accordingly there is a need for systems and methods that facilitate user interaction with an application running on a server from a client device and provide an improved experience for users at the client device.

Aspects of the present disclosure may provide utilizing a server that may provide one or more web browsers access to one or more remote machines through a remote desktop client. A server may include a module or functionality e.g. machine readable instructions to receive requests from a web browser. A sever may include a module or functionality e.g. machine readable instructions to translate user input requests received as HTTP requests from a web browser into corresponding input calls in a protocol language compatible with one or more remote desktop clients for accessing one or more remote machines. In one aspect a server can receive information data from e.g. drawing commands from one or more remote machines via the one or more remote desktop clients and translate the information data into a protocol language compatible with the associated web browser s . A server can include storage memory functionality for holding an image e.g. a Java or memory bitmap which can be modified in response to drawing commands received from the remote desktop server. A server may receive from the remote desktop server and store coordinates corresponding to the respective drawing commands. In certain aspects a server may comprise a web server e.g. a windows web server.

In some applications a server may facilitate accelerate rendering an image of the related remote desktop s at the related web browser by creating and modifying an image of the portion of the remote desktop that is affected by the user s input at the user device.

Aspects of the present disclosure may provide a web server with asynchronous request handling functionality to handle requests from a web browser.

Aspects of the present disclosure may provide a server with long polling functionality to handle requests from a web browser.

Aspects of the present disclosure may include or provide a web browser having a canvas or 2D rendering functionality.

It is understood that other configurations of the subject technology will become readily apparent to those skilled in the art from the following detailed description wherein various configurations of the subject technology are shown and described by way of illustration. As will be realized the subject technology is capable of other and different configurations and its several details are capable of modification in various other respects all without departing from the scope of the subject technology. Accordingly the drawings and detailed description are to be regarded as illustrative in nature and not as restrictive.

While certain embodiments are depicted in the drawings one skilled in the art will appreciate that the embodiments depicted are illustrative and that variations of those shown as well as other embodiments described herein may be envisioned and practiced within the scope of the present disclosure.

The detailed description set forth below is intended as a description of various configurations of the subject technology and is not intended to represent the only configurations in which the subject technology may be practiced. The appended drawings are incorporated herein and constitute a part of the detailed description. The detailed description includes specific details for the purpose of providing a thorough understanding of the subject technology. However it will be apparent to those skilled in the art that the subject technology may be practiced without these specific details. In some instances well known structures and components are shown in block diagram form in order to avoid obscuring the concepts of the subject technology. Like components are labeled with identical element numbers for ease of understanding.

Prior approaches using hypertext markup language HTML have required the use of browser specific plug ins as a method to create a better user experience by accelerating video and audio for example. Browser plug ins do not achieve HTML browser independence across the competing infrastructure vendors.

Infrastructure vendors are competing heavily in the proprietary remote desktop protocols and are focused on modest improvements over time to improve the user experience. The user experience while using a remote desktop protocol is a primary differentiator between the infrastructure vendors. There are however no known efforts to enable the user and customer to have a single unified method to have remote access to their home work or mobile Windows Mac or Linux environments.

In some aspects embodiments of the subject technology can eliminate or reduce the need for the installation of proprietary protocols on a user s device or a client device for accessing a remote machine during a remote desktop session. A remote machine or remotely accessed machine may include a remote desktop server. By enabling the user to use a single method to access their remote desktops with an open standard technology like HTML5 the requirements placed on a user s device e.g. a smart phone can be greatly reduced.

In some aspects embodiments of the subject technology can reduce or eliminate the need for installation of client software and or a browser plug in on the user s client device.

In some aspects embodiments of the subject technology can achieve a robust user experience that one would expect from a local executing application on a personal computing desktop.

In some aspects embodiments of the subject technology can advantageously utilize 2D rendering capability of suitable web browsers and replace proprietary rendering protocols with the 2D drawing capabilities of a browser running on the user s client device.

In some aspects embodiments of the subject technology can allow a user to easily access one or multiple open remote desktops across multiple servers and maintain their exact state from information stored in real time on an associated web server having protocol translation functionality that can function as a common interface between push type protocol employed by most remote desktop protocols and the pull type protocol employed by HTTP also referred to herein as a transcoding server which the user may access via a web browser having 2D rendering capability. Doing so can allow the user to render a remote display of a currently open session in a few seconds. Thus as the user switches from client device to client device the exact state of a particular remote desktop is preserved and is re rendered based on the capabilities of each display device. Effectively the user s multiple desktops can be configured to be always on and ready to be displayed on demand. The user s remote desktops can be configured to be accessed at any time and from any location.

Prior to the subject technology as described herein because HTTP a pull type protocol and most remote desktop display protocols push type protocols are incompatible it has generally been recognized by those skilled in the art that proprietary software and or downloadable plug ins were necessary for a web browser in order to have a remote desktop session using an HTTP on one end and a remote desktop display protocol on the other end.

In some aspects embodiments of the subject technology can enable a user of any endpoint device with a web browser having 2D rendering capabilities e.g. an HTML5 browser to display one or more remote desktop sessions in a single or multiple browser windows. Embodiments of the present disclosure can accordingly eliminate the need for installation on a client device of proprietary or open source client applications for remote desktop access. Embodiments of the present disclosure can establish and maintain simultaneous remote desktop connections to a single or multiple Windows Mac OS or Linux servers and enable all remote sessions to be displayed and interacted independently within the user s browser application. Embodiments of the present disclosure can be rendered in real time and be displayed as a web page on the remote client e.g. a user device such as a smart phone. All user mouse touch and keyboard input may be captured within the browser window and converted into the input format needed by the remote desktop machine which may utilize common desktop protocols e.g. independent computing architecture ICA by Citrix Systems remote desktop protocol RDP by Microsoft and PC over IP PCoIP by Taradici etc. Embodiments of the present disclosure can maintain open connections to the host servers at all times allowing single or multiple endpoint devices to be interactively connected and disconnected to the remote sessions instantly. Remote sessions never need to be disconnected from the servers as embodiments of the present disclosure can maintain active connections to the desktop. Active sessions can be resized and adjusted for best display and user experience to utilize the full capability of the user s access device.

In some aspects embodiments of the subject technology can reduce or eliminate the requirement for a local client application e.g. a web browser to support a vendor specific remote desktop protocol. Embodiments of the present disclosure can allow a browser with 2D rendering capability to run on any hardware any operating system and any form factor for the user to access her or his remote desktop or applications. A user can simply point the browser e.g. an HTML5 compatible browser such as Google Chrome to a respective predetermined uniform resource locator URL for one or more remote machines configured as remote desktop application servers. The browser can access a transcoding server that can translate or transcode between the protocol used for the browser and the protocol used for the remote machine s . The transcoding server can be public private cloud based and the access to the transcoding server can utilize HTTPS protocol. The transcoding server can authenticate the connection between the remote machine and a remote desktop client render the desktop of the remote machine s in real time and transmit that rendering to the browser via HTTP so that the browser can display the rendering in HTML5 canvas. Accordingly embodiments of the present disclosure can function as or provide a virtual desktop and application server that connects to one or multiple remote desktop servers e.g. Citrix XenDesktop with ICA Microsoft Windows Client and Server with RDP and VMware View with PCoIP etc.

Prior to HTML5 supporting canvas 2D real time drawing primitives HTML alone was not seen as a practical rendering technology due to the static nature of the rendered objects. As used according to the present disclosure HTML5 and similar browser languages can enable a new user robust experience due to the ability of rendering in 2D 3D and multimedia video audio objects on the client platform HTML5 can also in some cases utilize hardware acceleration for such rendering. Aspects of the subject technology can facilitate enhanced user experience for remote desktop sessions by providing platform independent techniques that allow real time access to remote machines and do not require the client device to have proprietary software or plug ins. Moreover the remote machines are not required to have HTTP or HTML compatibility for the remote desktop sessions.

As described herein aspects of the subject technology can reduce or minimize traffic between a browser and a transcoding server according the present disclosure. The reduction in traffic can be facilitated by various aspects of the subject technology including but not limited to implementation of long polling for drawing requests received from a web browser providing to a web browser only image portions from a remote desktop that have changed and need to be updated rather than the image of the entire remote desktop and placing coordinates for updated image portion s into a header of a single HTTP transmission response. The reduction of traffic to and from a browser can facilitate a remote desktop session that provides a real time user experience e.g. a user experience with few if any perceivable delays in the round trip time delay for user inputs to travel from a client device to the remote machine and a corresponding update of the remote desktop showing up on the client device. In exemplary embodiments such delay may be below e.g. 100 milliseconds so that most users will not perceive any delay at all.

As was noted previously aspects of the present disclosure can include or utilize a HTML5 compatible web browser having a 2D canvas e.g. in . The HTML5 specification provides for a 2D canvas which allows for dynamic real time scriptable rendering of 2D shapes and bitmap images. In one aspect being scriptable can mean or include reference to utilizing JavaScript for rendering a 2D image. The canvas consists of a drawable region defined in HTML code with height and width attributes. JavaScript code may access the area through a full set of drawing functions similar to other common 2D APIs thus allowing for dynamically generated graphics.

As shown in an overall architecture of exemplary embodiments of the present disclosure may contain three parts a client device or a user s device containing a browser e.g. an HTML5 compatible browser a server e.g. a Java web sever that is configured to function as a transcoding server translating between different protocols and a remote machine to which the client device is connecting. As shown and described for a transcoding server may include three main sections a remote desktop client wrapper or adapter a drawing commands queue and a web application container. The web application container can include various elements or components e.g. a hypertext transfer protocol HTTP handler a long polling handler and a drawing requests queue as shown and described with reference to . In an alternate embodiment a drawing commands queue may be a part of a web application container.

By way of illustration and not limitation in one aspect of the disclosure stated from a perspective of a remote machine side treating a remote machine as a local device and treating a client device as a remote device an application is executed or runs at a local device . While a client device may receive and display a view of the application on a display local to the client device the client device does not execute or run the application at the client device . Stated in another way from a perspective of the client side treating a remote machine as a remote device and treating a client device as a local device a remote application is executed or runs at a remote machine and while a client device may receive and display a view of the remote application the client device does not execute or run the remote application locally at the client device.

By way of illustration and not limitation a client device can represent a computer a mobile phone a laptop computer a thin client device a personal digital assistant PDA a portable computing device or a suitable device with a processor. In one example a client device may be a smartphone e.g. iPhone Android phone Blackberry etc. . In certain configurations a client device can represent an audio player a game console a camera a camcorder an audio device a video device a multimedia device or a device capable of supporting a connection to a remote server. In a preferred example a client device is mobile. In another example a client device can be stationary. According to one aspect of the disclosure a client device may be a device having at least a processor and memory where the total amount of memory of the client device could be less than the total amount of memory in a remote machine or a server . In one example a client device does not have a hard disk. In one aspect a client device has a display smaller than a display supported by a remote machine or a server . In one aspect a client device may include one or more client devices.

In one preferred aspect a server or a remote machine may represent a computer. In another aspect a server or a remote machine may represent a laptop computer a computing device a virtual machine e.g. VMware Virtual Machine a desktop session e.g. Microsoft Terminal Server a published application e.g. Microsoft Terminal Server or a suitable device with a processor. In one preferred example a server or a remote machine is stationary. In another aspect a server or a remote machine can be mobile. In certain configurations a server or a remote machine may be any device that can represent a client device. In one aspect a server may include one or more servers.

In one example a first device is remote to a second device when the first device is not directly connected to the second device. In one example a first remote device may be connected to a second device over a communication network such as a Local Area Network LAN a Wide Area Network WAN and or other network.

When a client device a server and a remote machine are remote with respect to one another a client device may connect to a server over a network and a remote machine may connect to a server over a network via a network connection for example a modem connection a LAN connection including the Ethernet or a broadband WAN connection including DSL Cable T1 T3 Fiber Optics Wi Fi or a mobile network connection including GSM GPRS 3G WiMax or other network connection. A network can be a LAN network a WAN network a wireless network the Internet an intranet or other network. A network may include one or more routers for routing data between client devices and or servers. A remote device e.g. client device server on a network may be addressed by a corresponding network address such as but not limited to an Internet protocol IP address an Internet name a Windows Internet name service WINS name a domain name or other system name. These illustrate some examples as to how one device may be remote to another device. However the subject technology is not limited to these examples.

According to certain aspects of the present disclosure the terms server and remote server are generally used synonymously in relation to a client device and the word remote may indicate that a server is in communication with other device s for example over a network connection s .

According to certain aspects of the present disclosure the terms client device and remote client device are generally used synonymously in relation to a server and or a remote machine and the word remote may indicate that a client device is in communication with a server s and or a remote machine s for example over a network connection s .

In one aspect of the disclosure a client device may be sometimes referred to as a client a user device a user s device or vice versa. Similarly a server may be sometimes referred to as a server device or vice versa. A server is sometimes referred to as a web server. Exemplary embodiments of the present disclosure include use of web servers with transcoding functionality e.g. transcoding servers.

In one aspect the terms local and remote are relative terms and a client device may be referred to as a local client device or a remote client device depending on whether a client device is described from a client side or from a server side or a remote machine s side respectively. A remote machine may be referred to as a local machine or a remote machine depending on whether a remote machine is described from the remote machine s side or from a client or server side. Similarly a server may be referred to as a local server or a remote server depending on whether a server is described from a server side or from a client side or a remote machine s side respectively. Furthermore an application running on a remote machine may be referred to as a local application if described from a remote machine s side and may be referred to as a remote application if described from a client side or a server side.

In one aspect devices placed on a client side e.g. devices connected directly to a client device s or to one another using wires or a short range wireless connection e.g. Bluetooth may be referred to as local devices with respect to a client device and remote devices with respect to a server. Similarly devices placed on a server side e.g. devices connected directly to a server s or to one another using wires or a short range wireless connection e.g. Bluetooth may be referred to as local devices with respect to a server and remote devices with respect to a client device.

Transcoding server can include three main functional blocks or modules a web application container a remote desktop client adapter and a drawing commands queue that includes a shared memory. The web application container can include an HTTP handler for handling HTTP requests from the web browser and HTTP responses to the web browser. In some embodiments the web application container may also include a long polling handler module as shown. The remote desktop client adapter can be configured to interface with a remote desktop client e.g. from a third party vendor for communication with remote machine which may include a remote desktop server as shown. Embodiments of a transcoding server can be configured to provide an application framework for hosting one or more web applications and or function as a Java web application container that can run Servlets. In some aspects a remote desktop client adapter may be referred to as a remote desktop client common interface.

The remote desktop client may function to communicate with the remote desktop server of the remote machine using a remote desktop display protocol. The remote desktop client sends a user s input to the remote machine and receives drawing data from the remote machine via its specific remote desktop display protocol.

In one aspect a remote desktop server may refer to a software installed on a remote machine and a remote desktop server may allow applications particularly those including graphical applications which run on the remote machine to be displayed at a machine that is separate and distinct from the remote machine e.g. client devices . Remote desktop server may allow drawing commands representing an image of a desktop of the remote machine to be transmitted to the separate machine e.g. transcoding server . In one aspect remote desktop client may refer to software installed on the machine that is separate and distinct from the remote machine e.g. transcoding server . Remote desktop client may send requests to remote desktop server via a remote desktop display protocol and in response receive the drawing commands representing the image of the desktop of the remote machine via the remote desktop display protocol.

In operation the web application container can function to receive and respond to the JavaScript client s HTTP requests. In one implementation a Servlet container can be used but the same result can be achieved using any similar web application framework such as Restlet for example. The remote desktop client adapter may provide a common interface between any remote desktop client and the drawing commands queue the web application container.

The remote desktop client adapter may receive a user s input information data or commands e.g. mouse keyboard and touch events from HTTP handler and translate the input information commands into respective remote desktop input calls which are sometimes referred to as remote desktop input commands. The remote desktop client adapter may also translate the drawing commands of the remote desktop e.g. GDI drawing commands received from remote desktop server via a remote desktop display protocol and remote desktop client into Java graphics application programming interface API commands. Java graphics API commands in themselves are not suitable for the web browser but they are an intermediary step towards achieving browser compatibility. The remote desktop client adapter may then execute those Java graphics API commands i.e. drawing into an off screen Java bitmap which can be stored in the drawing commands queue . In an alternative embodiment the drawing commands queue e.g. of of may receive the Java graphics API commands from the remote desktop client adapter and execute the Java graphics API commands to draw into an off screen Java bitmap. The HTTP handler e.g. of of or image conversion module e.g. of of can create an image such as a joint photographic experts group JPEG image or a portable network graphics PNG image or a bit image file BMP image or any other image file in an image format suitable for web browsers from the Java off screen bitmap and the resulting image is suitable for the browser . In one aspect a JPEG image may be referred to as a JPEG image file and a PNG image may be referred to as a PNG image file and BMP image may be referred to as a BMP image file. In one aspect as the image e.g. a JPEG or PNG image is created in real time when it is created it is simply sent to the web browser without being stored at the transcoding server.

In one aspect the drawing commands queue can serve two purposes holding or storing the off screen Java bitmap onto which drawing commands are executed and holding or serving as a drawing coordinates pool e.g. a queue of coordinates for drawing commands. The drawing commands queue can for example store GDI drawing command coordinates received from the remote desktop client adapter. In the event there are new drawing coordinates in the queue the drawing commands queue may send a notification to long polling handler module e.g. can be sent so that any pending request in the drawing requests queue can be served . The drawing requests queue e.g. in can function to store incoming long polling drawing requests from the client and respond to them when there are pending drawing commands from the drawing commands queue.

In some embodiments the web application container may include a long polling handler module which includes a long polling handler and a drawing requests queue . The long polling handler can operate with drawing requests queue . The drawing requests queue can function to store incoming long polling drawing requests received from the client e.g. HTML5 compatible web browser such as web browser in via the long polling handler and respond to them when there are pending drawing commands from the drawing commands queue . In one aspect pending drawing commands may include coordinates for the image in dirty coordinates pool and or an image e.g. Java bitmap in the drawing commands queue .

In operation the web application container may receive and respond to HTTP requests from a web browser on a user device e.g. in in . The web application container may provide user input requests to the remote desktop client adapter which provides a common interface between the web application container and the remote desktop client . The remote desktop client adapter may translate user input information e.g. mouse keyboard and touch events into respective remote desktop input calls for the remote desktop client . The remote desktop client adapter may translate the drawing commands e.g. GDI drawing commands of an image of a remote desktop received from a remote machine e.g. in in via a remote desktop display protocol and the remote desktop client into Java graphics drawing commands.

After receiving and translating the drawing commands from the remote desktop client the remote desktop client adapter may draw into an off screen Java bitmap stored in the drawings commands queue as shown. More specifically the remote desktop client adapter may provide as an image the portion also referred to as the dirty region s of the remote desktop affected by the user s input from the user device. Along with the drawing commands the remote desktop client adapter may extract from the drawing command s coordinates of the dirty region s from the remote desktop client and provide the drawing coordinates to the drawing commands queue e.g. dirty coordinates pool as indicated. As explained later the coordinates can be placed into an HTTP header section e.g. by HTTP handler to send dirty region coordinates e.g. as cookie along with an image to a browser e.g. in for display.

In the event there are new drawing coordinates in the drawing commands queue e.g. in the dirty coordinates pool drawing commands queue may send a notification to the drawing requests queue so that any pending request in the drawing requests queue can be forwarded to the HTTP handler for serving. The HTTP handler may then reach to the drawing commands queue e.g. dirty coordinates pool and obtain the dirty coordinates from the dirty coordinates pool . The HTTP handler may then place the dirty coordinates into an HTTP header section known as a cookie . In addition according to those coordinates the HTTP handler may obtain an image portion from the Java off screen bitmap . The HTTP handler may then send the image e.g. as a JPEG image or a PNG image as well as the coordinates which are stored in an HTTP response header section to the web browser e.g. in for display at the user device s display e.g. in . As a result the transcoding server A can facilitate a remote desktop session between a user device e.g. in in and a remote machine e.g. in in without the need for the user device to utilize proprietary plug ins or protocols.

In one aspect an image or an image file and drawing coordinates sent by a transcoding server to a web browser may be considered as an example of web browser drawing updates. In a preferred aspect web browser drawing updates are compatible with the web browser so that the web browser can recognize the web browser drawing updates and process them to display an image at the appropriate location on a display. Web browser drawing updates may be implemented with other types of drawing data and commands.

In one aspect an HTTP protocol the requests of which may be handled with an HTTP handler and a long polling handler between a client device and a transcoding server is a pull protocol and a remote desktop display protocol utilized between a transcoding server and a remote machine is a push protocol.

Long polling is a modification of the traditional polling technique and can allow emulation of an information push from a server to a client. With long polling the client requests information from the server in a similar way to a normal poll. In the event the server does not have any information available for the client instead of sending an empty response the server holds the request and waits for some information to be available. Once the information becomes available or after a suitable timeout a complete response is sent to the client. The client can then immediately re request information from the server allowing the server to almost always have an available waiting request that it can use to deliver data in response to an event.

The script client code can include an input listener responsive to user inputs such as mouse keyboard and touch events. The input listener can send HTTP requests with the user inputs to a transcoding server e.g. server in of . The script client code may also include a load image function or module that includes an image onload handler which may extract drawing coordinates from the HTTP header e.g. from the portion known as a cookie draw the received image onto canvas and call the load image function again passing it its unique identification ID . An image on error handler and or image on abort handler may also be included in the load image function to handle loading errors. The handler may call the load image function . For remote desktop sessions the canvas can hold an image of the remote desktop of the remote machine e.g. of and the user device may display the image onto a display e.g. in in the viewable window of the browser e.g. .

As mentioned previously an HTML5 compatible browser can be used for exemplary embodiments of the present disclosure. HTML5 includes or supports a canvas which allows for dynamic real time scriptable rendering of 2D shapes and bitmap images. In one aspect being scriptable can mean or include reference to utilizing JavaScript for rendering a 2D image. The canvas consists of a drawable region defined in HTML code with height and width attributes. JavaScript code may access the canvas region or area through a full set of drawing functions similar to other common 2D APIs thus allowing for dynamically generated graphics.

In operation such as accessing a remote machine e.g. in in during a remote desktop session the input listener may relay user inputs to the related transcoding server e.g. in in which interfaces with the remote machine by way of a remote desktop client and remote desktop client adapter e.g. in in . The script client code can also send a number of drawing requests as indicated by LoadImage LoadImage . As described previously the drawing requests can be handled by the related transcoding server as long polling requests.

When drawing commands are received from the remote desktop server via the remote desktop client the transcoding server may create modify an off screen image of the remote desktop and provide the actual image and related coordinates to the browser where the JavaScript client s image onload handler e.g. can then draw the image to the canvas in accordance with the coordinates extracted from the HTTP header e.g. cookie . In one aspect the image represents a portion of the entire image of the remote desktop that has been changed and thus the onload handler can receive and update a portion of the canvas based on the coordinates received instead of updating the entire canvas .

In one aspect a bitmap in a transcoding server e.g. Java off screen bitmap may include or represent a bitmap of an entire image of a remote desktop e.g. of . When a portion s of the image of the remote desktop is changed e.g. image portion in response to for example a user s input command or other changes by the remote machine the changed image portion s and its remote desktop coordinates may be provided as a remote desktop drawing command s to a remote desktop client adapter e.g. from a remote desktop server e.g. via a remote desktop client e.g. .

In one aspect the remote desktop client adapter may translate the remote desktop drawing command s into a graphics drawing command s generate coordinates corresponding to the remote desktop coordinates based on the graphics drawing commands and provide the coordinates into a pool e.g. . The remote desktop client adapter may execute the graphics drawing command s to draw into the bitmap or stated in another way to generate a bitmap portion s to update a portion s of the bitmap e.g. a portion s of according to the coordinates generated by the remote desktop client adapter. The updated portion s of the bitmap represents the changed image portion s of the remote desktop. In a preferred aspect the updated portion s of the bitmap is a portion of a Java off screen bitmap .

In one aspect an HTTP handler e.g. may form an image file corresponding to the updated portion s of the bitmap obtain the coordinates e.g. from for the image file and place the coordinates into a section of an HTTP header. The HTTP handler may then provide the image file and the coordinates to a web browser e.g. or more specifically to a script client code e.g. in a single HTTP response.

A canvas e.g. may store the entire image of a remote desktop e.g. of to be displayed on a display e.g. and then a portion s of the canvas may be updated when a portion s of the image of the remote desktop is changed during a remote desktop session. In this example when the script client code receives an image file and the coordinates corresponding to the changed portion s of the image of the remote desktop the script client code can update a portion of the canvas at canvas coordinates corresponding to the coordinates received from the HTTP handler so that the updated portion of the canvas represents the image contained in the image file.

Because drawing commands provided by a remote desktop client may include only those image portion s or region s of the remote desktop with corresponding coordinates that have been changed or updated relative to previous drawing commands the image provided to the canvas e.g. can accordingly be limited or minimized to include just the updated portion s of the remote desktop in exemplary embodiments. The updates on the remote desktop can be due to a user s input e.g. via a remote desktop session or caused by the remote machine itself e.g. a new indicated time from the system clock. Because the size of the image s provided to the canvas e.g. in response to drawing requests can be minimized the traffic for the remote session can be reduced or minimized facilitating a real time user experience for a remote desktop session.

In one example a remote desktop drawing command may comprise a drawing call such as gdi bitmap data top left width height 16 32 in which data may be a pointer to a memory location where the bitmap data is located. The parameters top left width height may represent the coordinates for the bitmap data. The parameter 16 may be the number of bits in red green blue RGB and the parameter 32 may be the number of bits in alpha red green blue ARGB . Thus this exemplary call indicates where the bitmap data for a portion of the image of the remote desktop e.g. the portion that has been changed is located the coordinates for the bitmap data and the number of bits used to convert from an RGB format to an ARGB format.

In another example a graphics drawing command may comprise a drawing call such as draw rect color top left width height . This drawing call can draw a rectangle at the coordinates specified by top left width height using the specified color. 

In one aspect when long polling is utilized between a client device and a transcoding server that uses HTTP a pull protocol traffic to the client device can be reduced to a level experienced by a push type protocol.

According to various aspects of the subject technology an adapter may include a remote desktop client manager which may be configured to receive a connection request e.g. an HTTP request specifying a particular remote machine indirectly from a web browser e.g. in via a web application container e.g. in in . In some aspects a connection request may be received from a web browser via a web application container that communicates with the web browser. For example the connection request can be received from a web browser via an HTTP handler e.g. or of a web application container. In some aspects a remote desktop client manager may manage or facilitate establishing a remote desktop session between a remote desktop client and a remote desktop server in response to the connection request. For example a remote desktop client manager may manage or facilitate starting the remote desktop session passing credentials settings preferences etc. to a remote desktop server e.g. via a remote desktop client and stopping the remote desktop session.

In one aspect a remote desktop client manager may receive a connection request e.g. a request originated from a web browser to establish a connection with remote desktop server e.g. or . In response to the connection request the remote desktop client manager may generate session control commands that are compatible with the remote desktop client remote desktop server and the remote desktop display protocol e.g. session control commands that can be understood and processed by remote desktop client and remote desktop server and that can be transmitted and received by remote desktop client and remote desktop server utilizing the remote desktop display protocol. These session control commands may include a command for starting a remote desktop session a command for stopping the remote desktop session. The session control commands may include one or more of credentials settings preferences etc. and command s for passing credentials settings preferences etc. to remote desktop server e.g. or . In response to the connection HTTP request the remote desktop client manager may provide the appropriate session control command s generated by the remote desktop client manager to the remote desktop client e.g. or . The remote desktop client may then use the session control commands received from the remote desktop client manager to start a remote desktop session with the remote desktop server pass credentials settings preferences etc. to remote desktop server and stop the remote desktop session.

In one aspect a remote desktop client manager can translate a connection request that is not compatible with a remote desktop client a remote desktop server or a remote desktop display protocol e.g. that cannot be understood or processed by a remote desktop client a remote desktop server or a remote desktop display protocol into session control commands that are compatible with the remote desktop client the remote desktop server and the remote desktop display protocol i.e. that can be understood and processed by remote desktop client and remote desktop server and that can be communicated between remote desktop client and remote desktop server utilizing the remote desktop display protocol .

In some aspects facilitating an establishment of a remote desktop session between a remote desktop client and a remote desktop server comprises generating a session control command based on the initial HTTP request. In some aspects facilitating an establishment of the remote desktop session comprises transmitting the session control command from a remote desktop client manager to a remote desktop client and then from the remote desktop client to a remote desktop server . For example the session control command may be transmitted to the remote desktop server via the remote desktop client that communicates with remote desktop server using a remote desktop display protocol. In some aspects the remote desktop display protocol comprises at least one of the Microsoft Remote Desktop Protocol RDP personal computer over internet protocol PCoIP remote FX RFX protocol remote framebuffer RFB protocol independent computing architecture ICA NX protocol and other suitable remote desktop display protocols. In some aspects the RFB protocol comprises virtual network computing VNC .

According to certain aspects of the subject technology a server such as server A B e.g. via a remote desktop client manager can maintain open connections between its remote desktop client and one or more remote desktop servers at all times allowing single or multiple client devices to be interactively connected and disconnected to remote desktop sessions instantly. In some aspects remote desktop sessions may never need to be disconnected from the one or more remote desktop servers as a server can maintain active connections to the one or more remote desktop servers. Of course a remote machine e.g. may go down for reasons that are outside of a related transcoding server s control however the connection can be maintained as long as the remote machine is available for remote access. For example a remote desktop client manager may continuously maintain the remote desktop session until the remote desktop server disconnects from the remote desktop session depending on the remote desktop server s idle remote connection settings. In some aspects remote desktop sessions established utilizing a remote desktop client manager may be resized and adjusted for best display and user experience to utilize the full capability of the client devices.

According to various aspects of the subject technology a user input handler may receive an input request indirectly from a web browser such as a server A B e.g. via an HTTP handler or and convert the input request into a format recognized by and or compatible with remote desktop client and remote desktop server . For example user input handler receives an input request that was transmitted utilizing a request response protocol from web browser. In preferred aspects the request response protocol may comprise hypertext transfer protocol HTTP . In another aspect the request response protocol may comprise other suitable request response protocols. In some aspects the input request is received from a web browser e.g. in via a web application container e.g. that communicates with the web browser. For example the input request is received via an HTTP handler e.g. or of a web application container. In some aspects the input request comprises at least one of a mouse event a keyboard event and a touch event. User input handler may translate the input request that is in a format suitable for or compatible with the request response protocol into an input command e.g. a remote desktop display protocol input command that is suitable for or compatible the remote desktop display protocol. The user input handler may transmit the input command to a remote desktop client which may transmit the input command to a remote desktop server . For example user input handler may facilitate transmitting the input command to remote desktop server via remote desktop client that communicates with remote desktop server using the remote desktop display protocol. In one aspect an input request is sometimes referred to as a user input command and vice versa. Please note however if an input request is referred to as an input command when it is received via HTTP it is a HTTP request rather than a command. In one aspect an input command is sometimes referred to as an input call or a remote desktop input command and vice versa.

A remote machine e.g. its remote desktop server may execute one or more actions based on the input command and send drawing data as a result of the executed one or more actions to a server such as a transcoding server A or B e.g. a remote desktop client of the server . According to various aspects a remote desktop client can receive a screen drawing command transmitted from a remote machine e.g. its remote desktop server utilizing the remote desktop display protocol in response to the input command transmitted to remote machine e.g. its remote desktop server . In one aspect a screen drawing command received from a remote machine may be sometimes referred to as a drawing command a remote machine drawing command or a remote desktop drawing command received from a remote machine and vice versa. The drawing command handler may then receive the screen drawing command from the remote desktop client connected to the remote machine . For example a drawing command handler can receive the screen drawing command from a remote machine e.g. its remote desktop server via a remote desktop client that communicates with the remote machine e.g. its remote desktop server using the remote desktop display protocol.

According to certain aspects a drawing command handler may convert a screen drawing command into a format recognized by and or compatible with a web browser e.g. in . For example a drawing command handler may translate a screen drawing command that is suitable for or compatible with a remote desktop client a remote desktop server and a remote desktop display protocol into a graphics drawing command that is compatible with the server A or B such as a Java graphics abstract window toolkit API command when the server is a Java transcoding server. In some aspects translating the screen drawing command can include calculating new and or adjusting received drawing command parameters and or making adjustments to the received bitmap data such as but not limited to converting the 16 bit red green blue RGB 5 6 5 color format into a 32 bit alpha red green blue ARGB 8 8 8 8 format. In some aspects drawing command handler may execute the graphics drawing command e.g. Java graphics API command to draw into an already created image bitmap e.g. the off screen Java bitmap of the drawing commands queue e.g. in or in at the transcoding server e.g. in in or B in . In one aspect Java graphics API command is sometimes referred to as Java graphics command or Java graphics drawing command. In one aspect the off screen bitmap may be a storage or memory location that is a part of a drawing commands queue e.g. or accessible by an application container e.g. or . In one aspect the size of an off screen bitmap may represent the size of a remote session. Stated in another way the size of an off screen bitmap may represent the size of the remote desktop or an off screen bitmap may be a bitmap representation of an entire image of a remote desktop.

Preferred embodiments of the present disclosure may in essence translate a request in HTTP to a command in a remote desktop display protocol and vice versa e.g. translate requests responses transmitted received via HTTP to commands transmitted received via a remote desktop display protocol and vice versa for a remote session between a client device and a remote machine. For example the input request from the web browser such as a server A B may be translated into the input command e.g. a remote desktop input command that is suitable for or compatible with the remote desktop display protocol and is received by remote desktop server via remote desktop client . The screen drawing command transmitted from the remote machine e.g. in response to the input command utilizing the remote desktop display protocol may be translated into the graphics drawing command that is compatible with the server A or B such as a Java graphics abstract window toolkit API command. In some aspects HTTP is a pull protocol while a remote desktop display protocol may be a push protocol. In some aspects a drawing command in push protocol may be translated into a drawing update or a drawing response in pull protocol during a remote session between a client device and a remote machine.

With continued reference to a drawing command handler when drawing into the off screen bitmap may transmit pixel data to the off screen bitmap. In some aspects the pixel data is used to update a portion of the off screen bitmap e.g. an off screen Java bitmap . In some aspects a drawing command handler may transmit the pixel data to the off screen bitmap so that the updated portion of the off screen bitmap may be stored and or converted to an image file.

According to certain aspects a drawing command handler can generate one or more coordinates corresponding to the updated portion of the off screen bitmap e.g. an image drawn into the off screen bitmap when the graphics drawing command is executed . For example the one or more coordinates may identify the locations where the corresponding image bitmap is to be executed on the canvas of a web browser. In one example the one or more coordinates may be extracted or copied from the graphics drawing command. A drawing command handler may also transmit the one or more coordinates to a dirty coordinates pool in that is a part of a drawing commands queue e.g. or . In some aspects a drawing command handler may transmit the one or more coordinates to the dirty coordinates pool so that the one or more coordinates may be stored in the dirty coordinates pool. Thus a drawing command handler may update dirty region coordinates in the drawing commands queue. In some aspects a drawing command handler may transmit a notification signal to a drawing requests queue e.g. in of a web application container e.g. . In some aspects the notification signal message may indicate that the image bitmap e.g. the off screen Java bitmap has been updated.

As shown at the bottom of the diagram e.g. at and the web browser can provide user input requests as HTTP requests to the transcoding server which in turn e.g. at and can provide the user input commands to the remote machine e.g. for control of the remote desktop of the remote machine. At the remote machine can provide drawing commands one command is shown to the drawing commands queue e.g. or in the transcoding server by way of the remote desktop client adapter e.g. or which draws a corresponding image of the remote desktop into the off screen bitmap in the drawing commands queue. In response to the drawing command the drawing commands queue can provide at notification to the drawing requests queue e.g. in the long polling handler module e.g. of the transcoding server. In response the first pending drawing request can be taken from the drawing requests queue and provided to the HTTP handler. In response at and the HTTP handler may obtain the image from the drawing commands queue. At the HTTP handler may provide the image and corresponding coordinates in a response sent to the script client e.g. or or more specifically of the web browser. The script client may then at draw the image e.g. to the canvas e.g. or using the appropriate coordinates extracted from the cookie for displaying the remote desktop in the web browser.

In one aspect an HTTP handler e.g. is a standard HTTP handler in that when it receives a request from a web browser it responds without waiting or storing the request. For example when an HTTP handler receives a user input request as a HTTP request at or from a web browser the HTTP handler responds immediately with a null response at and respectively while the request is sent to the remote machine via a remote desktop client adapter . In one aspect a long polling handler e.g. may be used to receive a request and respond to it based on an event and a long polling request may be stored. For example under one condition e.g. a drawing command is pending then the request is responded immediately e.g. the polling handler sends the drawing request to the HTTP handler so that the HTTP handler can send a response to the drawing request immediately. Under another condition e.g. a drawing command is not pending then the request may be stored away e.g. into a drawing requests queue until a condition is satisfied e.g. a new drawing command has arrived at a drawing commands queue .

In one aspect a remote desktop is a desktop of a remote machine. In one aspect during a remote desktop session with a remote machine a web browser of a client device may access control and or view any or all applications and files resident on the remote machine. In another aspect during a remote desktop session with a remote machine depending on the user s credentials and settings a web browser may be allowed to access control and or view some of the applications and files resident on the remote machine.

In one preferred aspect each of a client device a transcoding server and a remote machine is a separate and distinct machine that is remote from one another. In one aspect a transcoding server may be a machine that can communicate with one or more client devices and one or more remote machines and a transcoding server may be a machine that can communicate over a web. In one aspect a web browser may be an application that allows a user to retrieve present or communicate information over a web.

In high level description a web server can include two main functional blocks or modules a web application such as a model view controller MVC application of the ASP.NET framework and a remote desktop client wrapper . The web application can include an HTTP handler e.g. an asynchronous HTTP handler such as an HTTP controller of the ASP.NET MVC for handling HTTP requests e.g. HTTP initial connection requests HTTP input requests and HTTP drawing updates requests from the web browser and HTTP responses to the web browser . The HTTP handler may handle HTTP requests synchronously or asynchronously. A synchronous handling involves an immediate response that is provided in the order of receiving a request that needs immediate attention whereas the asynchronous handling may involve an immediate response or a delayed response depending on the nature of the request. For example the response to a synchronous request including an initial connection request or an input request e.g. user input events such as mouse keyboard or touch events is a synchronous response and a response to an asynchronous request including a drawing update request is an asynchronous response which may be immediate if there are changes in the remote desktop that needs immediate attention or delayed if there are no changes in the remote desktop. In the asynchronous case the browser after making the request may engage in other activities while waiting for the asynchronous response from the web server.

The remote desktop client wrapper can be configured to interface with a remote desktop client not shown in for simplicity e.g. from a third party vendor for communication with the remote machine which may include a remote desktop server as shown. Embodiments of the web server can be configured to provide an application framework for hosting one or more web applications and or function as a windows web application container that can run windows API. In some aspects a remote desktop client wrapper may be referred to as a remote desktop client common interface. The desktop client wrapper may function to communicate with the remote desktop server of the remote machine using a remote desktop display protocol. The remote desktop client may communicate remote desktop protocol data for example send a user s input to the remote machine and receive drawing data from the remote machine via its specific remote desktop display protocol.

In one aspect a remote desktop server may refer to a software installed on the remote machine and a remote desktop server may allow applications particularly those including graphical applications which run on the remote machine to be displayed at a machine that is separate and distinct from the remote machine e.g. on display of the client device using web browser . Remote desktop server may allow drawing commands representing an image of a desktop of the remote machine to be transmitted to the separate machine via the web server . In one aspect remote desktop client wrapper may refer to software installed on the machine that is separate and distinct from the remote machine e.g. web server . Remote desktop client wrapper may send requests to remote desktop server via a remote desktop display protocol and in response receive the drawing commands representing the image of the desktop of the remote machine via the remote desktop display protocol.

With regard to drawing requests if there are pending drawing commands the HTTP request switch may handle the request synchronously by passing the drawing request to the HTTP handler response ready module for completing the pending requests. Otherwise the drawing request may be handled asynchronously by adding the drawing request to the drawing requests queue . In one aspect pending drawing commands may include coordinates for the image in a drawing coordinates queue and or an image e.g. memory bitmap in the drawing commands buffer . In an aspect a windows bitmap may refer to a windows Graphics API memory bitmap which in one aspect may refer to a memory bitmap or an off screen bitmap. The HTTP handler response ready module can handle sending HTTP responses back to the client web browser e.g. in . In one aspect the HTTP handler response ready module is a standard HTTP handler. The drawing requests queue can function to store incoming HTTP drawing requests received by the HTTP request switch from the client e.g. HTML5 compatible web browser such as web browser in and respond to them when there are pending drawing commands from the drawing commands buffer . The drawing commands buffer can serve two purposes holding or storing an off screen image e.g. memory bitmap onto which drawing commands are executed and serving as the drawing coordinates queue e.g. a queue of coordinates for drawing commands. The coordinates can be those of regions or areas of an image of the remote desktop that need to be redrawn at the client device to reflect changes on the remote desktop. The areas or regions are sometimes referred to as drawing regions. The drawings commands buffer can function as memory or storage that is accessible by both the asynchronous HTTP handler and the remote desktop client wrapper .

The remote desktop client wrapper can be configured to interface with any suitable remote desktop client for communication with a remote machine e.g. in which may be configured to include a remote desktop server e.g. in . The remote desktop client wrapper may translate user input information e.g. mouse keyboard and touch events into respective remote desktop input calls for the remote desktop client . The remote desktop client wrapper may translate the drawing commands e.g. GDI drawing commands of an image of a remote desktop received from a remote machine e.g. in in via a remote desktop display protocol and the remote desktop client into windows graphics drawing commands.

After receiving and translating the drawing commands from the remote desktop client the remote desktop client wrapper may draw into an off screen memory bitmap stored in the drawings commands buffer as shown. More specifically the remote desktop client wrapper may provide as an image a portion of drawing regions of the remote desktop affected by the user s input from the user device. Along with the drawing commands the remote desktop client wrapper may extract from the drawing command s coordinates of the drawing region s from the remote desktop client and provide the drawing coordinates to the drawing commands buffer e.g. drawing coordinates queue as indicated. The coordinates can be placed into an HTTP header section e.g. by HTTP handler response ready module to send drawing region coordinates e.g. as cookie along with an image to a browser e.g. in for display.

In the event there are new drawing coordinates in the drawing commands buffer e.g. in the drawing coordinates queue drawing commands buffer may send a notification to the drawing requests queue so that any pending request in the drawing requests queue can be forwarded to the HTTP handler response ready module for serving. The HTTP handler response ready module may then reach to the drawing commands buffer e.g. drawing coordinates queue and obtain the drawing coordinates from the drawing coordinates queue . The HTTP handler response ready module may then place the drawing coordinates into an HTTP header section known as a cookie . In addition according to those coordinates the HTTP handler response ready module may obtain an image portion from the off screen memory bitmap . The HTTP handler response ready module may then send the image e.g. as a joint photographic experts group JPEG image or a portable network graphics PNG image as well as the coordinates which are stored in an HTTP response header section to the web browser e.g. in for display at the user device s display. As a result the web application can facilitate a remote desktop session between a user device e.g. in in and a remote machine e.g. in in . or in without the need for the user device to utilize proprietary plug ins or protocols.

In one aspect an image or an image file such as a windows image file and drawing coordinates sent by a web server e.g. a windows web server to a windows web browser may be considered as an example of web browser drawing updates. In a preferred aspect web browser drawing updates are compatible with the windows web browser so that the windows web browser can recognize the web browser drawing updates and process them to display an image at the appropriate location on a display. Web browser drawing updates may be implemented with other types of drawing data and commands.

In one aspect an HTTP protocol the requests of which may be handled with HTTP request switch and HTTP handler response ready module between a client device and a web server is a pull protocol and a remote desktop display protocol utilized between a web server and a remote machine is a push protocol.

The remote desktop client wrapper may receive a user s input information data or commands e.g. mouse keyboard and touch events from HTTP request switch and translate the input information commands into respective remote desktop input calls which are sometimes referred to as remote desktop input commands. The remote desktop client wrapper may also translate the drawing commands of the remote desktop e.g. GDI drawing commands received from a remote desktop server e.g. remote desktop server of via a remote desktop display protocol and remote desktop client into windows graphics application programming interface API commands. Windows graphics API commands in themselves are not suitable for the web browser but they are an intermediary step towards achieving browser compatibility. The remote desktop client wrapper may then execute those windows graphics API commands i.e. drawing into an off screen memory bitmap which can be stored in the drawing commands buffer . In an alternative embodiment the drawing commands buffer may receive the windows graphics API commands from the remote desktop client wrapper and execute the windows graphics API commands to draw into an off screen memory bitmap. The HTTP handler response ready module can create an image such as a JPEG image or PNG image or a bitmap file BMP image or any other image file in an image format suitable for a browser e.g. a windows web browsers from the memory off screen bitmap and the resulting image is suitable for the browser of . In one aspect as the image e.g. a JPEG or PNG image is created in real time when it is created it is simply sent to the web browser without being stored at the web server. In one aspect a web server may comprise a web application. In one aspect a web application may be a part of a web server. In one aspect a web application may refer to a web server. In one aspect an asynchronous HTTP handler may be a part of a web application. In one aspect an asynchronous HTTP handler may refer to a web application. In an aspect a web server may be a windows web server. In one aspect a browser may be a windows web browser.

The script client code can include an input listener responsive to user inputs such as mouse keyboard and touch events. The input listener can send HTTP requests with the user inputs to a web server e.g. a web server of web application in . The script client code may also include a load image function or module that can handle HTTP image requests asynchronously on the web server and includes an image onload handler which may extract drawing coordinates from the HTTP header e.g. from the portion known as a cookie draw the received image onto canvas and call the load image function again passing it its unique identification ID . An image on error handler and or image on abort handler may also be included in the load image function to handle loading errors. The on abort handler may call the load image function . For remote desktop sessions the canvas can hold an image of the remote desktop of the remote machine e.g. of and the user device may display the image onto a display e.g. in in the viewable window of a browser e.g. .

As mentioned previously an HTML5 compatible browser can be used for exemplary embodiments of the present disclosure. HTML5 includes or supports a canvas which allows for dynamic real time scriptable rendering of 2D shapes and bitmap images. In one aspect being scriptable can mean or include reference to utilizing a script for rendering a 2D image. The canvas consists of a drawable region defined in HTML code with height and width attributes. Script codes may access the canvas region or area through a full set of drawing functions similar to other common 2D APIs thus allowing for dynamically generated graphics.

In operation such as accessing a remote machine e.g. of during a remote desktop session the input listener may relay user inputs to the related web server e.g. or which interfaces with the remote machine by way of a remote desktop client and remote desktop client wrapper e.g. in . The script client code can also send a number of drawing requests as indicated by LoadImage LoadImage .

When drawing commands are received from the remote desktop server via the remote desktop client the web server may create modify an off screen image of the remote desktop and provide the actual image and related coordinates to the browser where the client s image onload handler e.g. can then draw the image to the canvas in accordance with the coordinates extracted from the HTTP header e.g. cookie . In one aspect the image represents a portion of the entire image of the remote desktop that has been changed and thus the onload handler can receive and update a portion of the canvas based on the coordinates received instead of updating the entire canvas .

In one aspect a bitmap in a web server e.g. memory bitmap may include or represent a bitmap of an entire image of a remote desktop e.g. of . When a portion s of the image of the remote desktop is changed e.g. image portion in response to for example a user s input command or other changes by the remote machine the changed image portion s and its remote desktop coordinates may be provided as a remote desktop drawing command s to a remote desktop client wrapper e.g. of from a remote desktop server e.g. via a remote desktop client.

In one aspect the remote desktop client wrapper may translate the remote desktop drawing command s into a graphics drawing command s generate coordinates corresponding to the remote desktop coordinates based on the graphics drawing commands and provide the coordinates into a queue e.g. of . The remote desktop client wrapper may execute the graphics drawing command s to draw into the bitmap or stated in another way to generate a bitmap portion s to update a portion s of the bitmap e.g. a portion s of according to the coordinates generated by the remote desktop client wrapper. The updated portion s of the bitmap represents the changed image portion s of the remote desktop. In a preferred aspect the updated portion s of the bitmap is a portion of memory bitmap .

In one aspect an HTTP handler response ready module e.g. of may form an image file corresponding to the updated portion s of the bitmap obtain the coordinates e.g. from for the image file and place the coordinates into a section of an HTTP header. The HTTP handler may then provide the image file and the coordinates to a web browser e.g. or more specifically to a script client code e.g. in a single HTTP response.

A canvas e.g. may store the entire image of a remote desktop e.g. of to be displayed on a display e.g. and then a portion s of the canvas may be updated when a portion s of the image of the remote desktop is changed during a remote desktop session. In this example when the script client code receives an image file and the coordinates corresponding to the changed portion s of the image of the remote desktop the script client code can update a portion of the canvas at canvas coordinates corresponding to the coordinates received from the HTTP handler so that the updated portion of the canvas represents the image contained in the image file.

Because drawing commands provided by a remote desktop client may include only those image portion s or region s of the remote desktop with corresponding coordinates that have been changed or updated relative to previous drawing commands the image provided to the canvas e.g. can accordingly be limited or minimized to include just the updated portion s of the remote desktop in exemplary embodiments. The updates on the remote desktop can be due to a user s input e.g. via a remote desktop session or caused by the remote machine itself e.g. a new indicated time from the system clock. Because the size of the image s provided to the canvas e.g. in response to drawing requests can be minimized the traffic for the remote session can be reduced or minimized facilitating a real time user experience for a remote desktop session.

As discussed above a remote desktop drawing command may comprise a drawing call such as gdi bitmap data top left width height 16 32 in which data may be a pointer to a memory location where the bitmap data is located. The parameters top left width height may represent the coordinates for the bitmap data. The parameter 16 may be the number of bits in red green blue RGB and the parameter 32 may be the number of bits in alpha red green blue ARGB . Thus this exemplary call indicates where the bitmap data for a portion of the image of the remote desktop e.g. the portion that has been changed is located the coordinates for the bitmap data and the number of bits used to convert from an RGB format to an ARGB format. In another example a graphics drawing command may comprise a drawing call such as draw rect color top left width height . This drawing call can draw a rectangle at the coordinates specified by top left width and height using the specified color. 

According to various aspects of the subject technology the remote desktop session module may be configured to receive a connection request e.g. an HTTP request specifying a particular remote machine indirectly from a web browser e.g. of via the asynchronous HTTP handler e.g. in . In some aspects a connection request may be received from a web browser via an HTTP request switch e.g. of that communicates with the web browser. In some aspects a remote desktop session module may manage or facilitate establishing a remote desktop session between a remote desktop client e.g. a remote desktop protocol client and a remote desktop server in response to the connection request. For example a remote desktop session module may manage or facilitate starting the remote desktop session passing credentials settings preferences etc. to a remote desktop server e.g. via a remote desktop client and stopping the remote desktop session.

In one aspect a remote desktop session module may receive a connection request e.g. a request originated from a web browser to establish a connection with remote desktop server e.g. or . In response to the connection request the remote desktop session module may generate session control commands that are compatible with the remote desktop client remote desktop server and the remote desktop display protocol e.g. session control commands that can be understood and processed by remote desktop client and remote desktop server and that can be transmitted and received by remote desktop client and remote desktop server utilizing the remote desktop display protocol. These session control commands may include a command for starting a remote desktop session a command for stopping the remote desktop session. The session control commands may include one or more of credentials settings preferences etc. and command s for passing credentials settings preferences etc. to remote desktop server e.g. . In response to the connection HTTP request the remote desktop session module may provide the appropriate session control command s generated by the remote desktop session module to the remote desktop client e.g. . The remote desktop client may then use the session control commands received from the remote desktop session module to start a remote desktop session with the remote desktop server pass credentials settings preferences etc. to remote desktop server and stop the remote desktop session.

In one aspect a remote desktop session module can translate a connection request that is not compatible with a remote desktop client a remote desktop server or a remote desktop display protocol e.g. that cannot be understood or processed by a remote desktop client a remote desktop server or a remote desktop display protocol into session control commands that are compatible with the remote desktop client the remote desktop server and the remote desktop display protocol i.e. that can be understood and processed by remote desktop client and remote desktop server and that can be communicated between remote desktop client and remote desktop server utilizing the remote desktop display protocol .

In some aspects facilitating an establishment of a remote desktop session between a remote desktop client and a remote desktop server comprises generating a session control command based on the initial HTTP request. In some aspects facilitating an establishment of the remote desktop session comprises transmitting the session control command from a remote desktop session module to a remote desktop client and then from the remote desktop client to a remote desktop server e.g. . For example the session control command may be transmitted to the remote desktop server via the remote desktop client that communicates with remote desktop server using a remote desktop display protocol. In some aspects the remote desktop display protocol comprises at least one of the Microsoft Remote Desktop Protocol RDP personal computer over internet protocol PCoIP remote FX RFX protocol remote framebuffer RFB protocol independent computing architecture ICA NX protocol and other suitable remote desktop display protocols. In some aspects the RFB protocol comprises virtual network computing VNC .

According to certain aspects of the subject technology a server such as server A B e.g. via a remote desktop session module can maintain open connections between its remote desktop client and one or more remote desktop servers at all times allowing single or multiple client devices to be interactively connected and disconnected to remote desktop sessions instantly. In some aspects remote desktop sessions may never need to be disconnected from the one or more remote desktop servers as a server can maintain active connections to the one or more remote desktop servers. Of course a remote machine e.g. may go down for reasons that are outside of a related web server s control however the connection can be maintained as long as the remote machine is available for remote access. For example a remote desktop session module may continuously maintain the remote desktop session until the remote desktop server disconnects from the remote desktop session depending on the remote desktop server s idle remote connection settings. In some aspects remote desktop sessions established utilizing a remote desktop session module may be resized and adjusted for best display and user experience to utilize the full capability of the client devices.

According to various aspects of the subject technology a user input module may receive an input request indirectly from a web browser such as a web browser e.g. via an HTTP request switch of and convert the input request into a format recognized by and or compatible with remote desktop client and remote desktop server . For example user input module receives an input request that was transmitted utilizing a request response protocol from a web browser. In preferred aspects the request response protocol may comprise hypertext transfer protocol HTTP . In another aspect the request response protocol may comprise other suitable request response protocols. In some aspects the input request is received from a web browser e.g. via an HTTP request switch e.g. that communicates with the web browser. In some aspects the input request comprises at least one of a mouse event a keyboard event and a touch event. User input module may translate the input request that is in a format suitable for or compatible with the request response protocol into an input command e.g. a remote desktop display protocol input command that is suitable for or compatible with the remote desktop display protocol. The user input module may transmit the input command to a remote desktop client which may transmit the input command to a remote desktop server . For example user input module may facilitate transmitting the input command to remote desktop server via remote desktop client that communicates with remote desktop server using the remote desktop display protocol. In one aspect an input request is sometimes referred to as a user input command and vice versa. Please note however if an input request is referred to as an input command when it is received via HTTP it is a HTTP request rather than a command. In one aspect an input command is sometimes referred to as an input call or a remote desktop input command and vice versa.

A remote machine e.g. its remote desktop server may execute one or more actions based on the input command and send drawing data as a result of the executed one or more actions to a server such as a web server e.g. a remote desktop client wrapper of the server . According to various aspects a remote desktop client can receive a screen drawing command transmitted from a remote machine e.g. its remote desktop server utilizing the remote desktop display protocol in response to the input command transmitted to remote machine e.g. its remote desktop server of . In one aspect a screen drawing command received from a remote machine may be sometimes referred to as a drawing command a remote machine drawing command or a remote desktop drawing command received from a remote machine and vice versa. The drawing command module may then receive the screen drawing command from the remote desktop client connected to the remote machine . For example a drawing command module can receive the screen drawing command from a remote machine e.g. its remote desktop server via a remote desktop client that communicates with the remote machine e.g. its remote desktop server using the remote desktop display protocol.

According to certain aspects a drawing command module may convert a screen drawing command into a format recognized by and or compatible with a web browser e.g. . For example a drawing command module may translate a screen drawing command that is suitable for or compatible with a remote desktop client a remote desktop server and a remote desktop display protocol into a graphics drawing command that is compatible with the web server such as a windows graphics abstract window toolkit API command. In some aspects translating the screen drawing command can include calculating new and or adjusting received drawing command parameters and or making adjustments to the received bitmap data such as but not limited to converting the 16 bit red green blue RGB 5 6 5 color format into a 32 bit alpha red green blue ARGB 8 8 8 8 format. In some aspects drawing command module may execute the graphics drawing command e.g. windows graphics API command to draw into an already created image bitmap e.g. the off screen memory bitmap of the drawing commands buffer e.g. in at the web server e.g. in . In one aspect windows graphics API command is sometimes referred to as windows graphics command or windows graphics drawing command. In one aspect the off screen bitmap may be a storage or memory location that is a part of a drawing commands buffer e.g. accessible by an asynchronous HTTP handler e.g. . In one aspect the size of an off screen bitmap may represent the size of a remote session. Stated in another way the size of an off screen bitmap may represent the size of the remote desktop or an off screen bitmap may be a bitmap representation of an entire image of a remote desktop.

Preferred embodiments of the present disclosure may in essence translate a request in HTTP to a command in a remote desktop display protocol and vice versa e.g. translate requests responses transmitted received via HTTP to commands transmitted received via a remote desktop display protocol and vice versa for a remote session between a client device and a remote machine. For example the input request from the web browser such as the windows web browser may be translated into the input command e.g. a remote desktop input command that is suitable for or compatible with the remote desktop display protocol and is received by remote desktop server via remote desktop client . The screen drawing command transmitted from the remote machine e.g. in response to the input command utilizing the remote desktop display protocol may be translated into the graphics drawing command that is compatible with the web server such as a windows graphics abstract window toolkit API command. In some aspects HTTP is a pull protocol while a remote desktop display protocol may be a push protocol. In some aspects a drawing command in push protocol may be translated into a drawing update or a drawing response in pull protocol during a remote session between a client device and a remote machine.

With continued reference to a drawing command module when drawing into the off screen bitmap may transmit pixel data to the off screen bitmap. In some aspects the pixel data is used to update a portion of the off screen bitmap e.g. an off screen memory bitmap . In some aspects a drawing command module may transmit the pixel data to the off screen bitmap so that the updated portion of the off screen bitmap may be stored and or converted to an image file.

According to certain aspects a drawing command module can generate one or more coordinates corresponding to the updated portion of the off screen bitmap e.g. an image drawn into the off screen bitmap when the graphics drawing command is executed . For example the one or more coordinates may identify the locations where the corresponding image bitmap is to be executed on the canvas of a web browser. In one example the one or more coordinates may be extracted or copied from the graphics drawing command. A drawing command module may also transmit the one or more coordinates to a drawing coordinates queue in that is a part of a drawing commands buffer e.g. . In some aspects a drawing command module may transmit the one or more coordinates to the drawing coordinates queue so that the one or more coordinates may be stored in the drawing coordinates queue. Thus a drawing command module may update drawing region coordinates in the drawing commands buffer. In some aspects a drawing command module may transmit a notification signal to a drawing requests buffer e.g. of an asynchronous HTTP handler e.g. . In some aspects the notification signal message may indicate that the image bitmap e.g. the off screen memory bitmap has been updated.

In one advantageous aspect a windows web server may comprise a Microsoft Windows web server. A Microsoft Windows web server may utilize Microsoft s operating system. In one advantageous aspect a web browser is a browser that is HTML5 compatible. In one advantageous aspect a windows web browser is a browser that is HTML5 compatible.

In another advantageous aspect a windows API may comprise a Microsoft Windows API. A Microsoft Windows web API may be operable in Microsoft s operating system.

In yet another advantageous aspect a windows web browser may comprise a Microsoft Windows web browser e.g. Windows Internet Explorer . A Microsoft Windows web browser may be operable in Microsoft s operating system.

In yet another advantageous aspect an MVC application may comprise an ASP.NET MVC application that may be executable in Microsoft s operating system.

In yet another advantageous aspect a windows graphics drawing command may comprise a Microsoft Windows graphics drawing command. A Microsoft Windows graphics drawing command may be executable in Microsoft s operating system.

In yet another advantageous aspect a windows image file may comprise a Microsoft Windows image file. A Microsoft Windows image file may be usable in Microsoft s operating system.

In yet another advantageous aspect a windows graphics API command may comprise a Microsoft Windows graphics API command. A Microsoft Windows graphics API command may be executable in Microsoft s operating system.

In yet another advantageous aspect a windows script client s image onload handler e.g. may comprise a JavaScript client s image onload handler.

In one aspect a windows application file command interface operating system or device e.g. a windows web server a windows API a windows graphics drawing command a windows image file a windows script client is adapted to provide windowing functionality. In one aspect windowing functionality may be adapted to provide an enclosed rectangular window area on a display screen. In one aspect windowing functionality may be adapted to provide a window that is a logical view of a file. This may allow a user to view different portions of a file when the user moves the window. In one aspect a windows operating system is an operating system adapted to provide windowing functionality. In one example a windows operating system comprises a Microsoft Windows operating system. In one aspect a windows application file command interface or device is adapted to utilize or is operable with a windows operating system.

In yet another advantageous aspect a client device e.g. client device of is a computing machine that utilizes Microsoft s operating system.

In one aspect each of a client device and a remote machine is an end machine for communication in that each is an end point of communication as shown in . A server may be also an end machine as shown in .

In one aspect a transcoding server may comprise a web server an HTTP handler may comprise an HTTP handler a long polling handler may comprise an asynchronous handler and or an HTTP request switch a web application container may comprise an ASP.NET MVC Application a remote desktop client adaptor may comprise a remote desktop client wrapper a drawing coordinates pool may comprise a drawing coordinated queue a drawing command handler may comprise a drawing command module a remote desktop client manager may comprise a remote desktop session module and a user input handler may comprise a user input module.

The processing system may include a general purpose processor or a specific purpose processor for executing instructions and may include a machine readable medium such as a volatile or non volatile memory for storing data and or instructions for software programs. The instructions which may be stored in a machine readable medium and or may be executed by the processing system to control and manage access to the various networks as well as provide other communication and processing functions. The instructions may also include instructions executed by the processing system for various user interface devices such as a display and a keypad . The processing system may include an input port and an output port . Each of the input port and the output port may include one or more ports. The input port and the output port may be the same port e.g. a bi directional port or may be different ports.

The processing system may be implemented using software hardware or a combination of both. By way of example the processing system may be implemented with one or more processors. A processor may be a general purpose microprocessor a microcontroller a digital signal processor DSP an application specific integrated circuit ASIC a field programmable gate array FPGA a programmable logic device PLD a controller a state machine gated logic discrete hardware components and or any other suitable device that can perform calculations or other manipulations of information.

A machine readable medium can be one or more machine readable media. Software shall be construed broadly to mean instructions data or any combination thereof whether referred to as software firmware middleware microcode hardware description language or otherwise. Instructions may include code e.g. in source code format binary code format executable code format or any other suitable format of code .

Machine readable media e.g. may include storage integrated into a processing system such as might be the case with an application specific integrated circuit ASIC . Machine readable media e.g. may also include storage external to a processing system such as a random access memory RAM a flash memory a read only memory ROM a programmable read only memory PROM an erasable PROM EPROM registers a hard disk a removable disk a CD ROM a DVD or any other suitable storage device. In addition machine readable media may include a transmission line or a carrier wave that encodes a data signal. Those skilled in the art will recognize how best to implement the described functionality for the processing system . According to one aspect of the disclosure a machine readable medium is a computer readable medium encoded or stored with instructions and is a computing element which defines structural and functional interrelationships between the instructions and the rest of the system which permit the instructions functionality to be realized. In one aspect a machine readable medium is a non transitory machine readable medium a machine readable storage medium or a non transitory machine readable storage medium. In one aspect a computer readable medium is a non transitory computer readable medium a computer readable storage medium or a non transitory computer readable storage medium. A non transitory machine readable medium or a non transitory computer readable medium may include for example one or more volatile memories and or one or more non volatile memories. Instructions may be executable for example by a client device a server a remote machine or by a processing system of a client device a server or a remote machine. Instructions can be for example a computer program including code.

An interface may be any type of interface and may reside between any of the components shown in . An interface may also be for example an interface to the outside world e.g. an Internet network interface . A transceiver block may represent one or more transceivers and each transceiver may include a receiver and a transmitter . A functionality implemented in a processing system may be implemented in a portion of a receiver a portion of a transmitter a portion of a machine readable medium a portion of a display a portion of a keypad or a portion of an interface and vice versa.

Referring to and continuing with the description of method drawing commands and coordinates e.g. of dirty regions can be received by the transcoding server from the remote desktop server as described at . In response the drawing commands and coordinates can be translated from the protocol of the remote desktop server to the protocol of the web browser as described at . The transcoding server can respond by drawing or generating an image of the remote desktop as described at . The image and the corresponding coordinates can be linked or unionized as described at . A drawing request from the web browser can be responded to as described at by sending the image and coordinates to the web browser for display as described at . Accordingly method may be used for controlling and accessing a remote desktop session via HTTP and such control can be in real time.

An exemplary embodiment of a method of accessing and controlling a remote desktop of a remote machine e.g. or from a web browser e.g. or via a transcoding server e.g. A or B may include the following three steps step one can happen once at the beginning of a session and steps two and three can continue interchangeably during the remote desktop session.

The first step can include an initial HTTP request by the web browser e.g. a connection request to connect to a remote machine . For example an initial HTTP request is sent by the web browser preferably an HTML5 compatible browser. The web browser receives back a response which can contain a script client such as or e.g. JavaScript Ajax client code. The transcoding server e.g. Java transcoding server can use the connection request to establish a connection to a remote machine via a remote desktop client. A remote desktop client on or used with the Java transcoding server can establish the connection to a remote machine which utilizes a remote desktop display protocol. The transcoding server can function to interface between the HTTP protocol and the remote desktop display protocol. In one aspect between the web browser and the transcoding server there is no connection as HTTP is a connectionless protocol. Instead there are only separate requests and responses in HTTP protocol.

The second step is remote session drawing at the web browser On the browser side the client JavaScript code can continuously re send a number of e.g. four asynchronous Ajax HTTP requests to find out if there are any dirty regions of the remote desktop of the remote machine to re draw. On the Java transcoding server these drawing requests are handled as long polling requests meaning that they will be responded to only if there is data to be drawn otherwise they hang in the drawing requests queue e.g. . In addition on the Java transcoding server the remote session is drawn into an off screen Java bitmap in a drawing commands queue of the transcoding server. In addition the coordinates of the drawing command are also appended or added to the drawing commands queue. This last part also sends a notification to the drawing requests queue of the transcoding server so that the first waiting request from the drawing requests queue can be served. In HTTP response to the browser the dirty drawing image is sent together with the drawing coordinates that are stored in one of the HTTP header sections known as a cookie . On the browser side the script client receives the dirty image and the coordinates and the script client draws the image into an HTML canvas e.g. using coordinates from the cookie. This allows the remote session from a remote machine e.g. an image of the remote desktop of the remote machine to be drawn via a Java transcoding server to the client s HTML5 browser.

The third step involves a user input such as a mouse click keystroke or touch event. On the browser side the script client detects e.g. a mouse event and sends an HTTP request to the transcoding server passing along the X and Y coordinates of the event. The Java transcoding server receives the request sends an empty reply see e.g. and in to close the HTTP request and then via remote desktop client adapter it forwards this request to the remote desktop client which sends it via its protocol to the remote machine. These user input requests can be handled in a standard way i.e. not as long polling events to receive and process user input. User input can then be sent to the remote machine.

In a preferred aspect a script client is not installed on the client device. In other words a script client does not exist and is not pre installed on the web browser or on the client device prior to the first step described above e.g. prior to the web browser connecting to or sending a request to connect to the transcoding server to initiate a remote session with a remote machine . In a preferred aspect a client device simply needs a web browser to initiate accessing and controlling a remote desktop of a remote machine or to initiate a remote desktop session with the remote machine. Thus the client device does not need software or a browser plug in for a remote desktop display protocol. The transcoding server provides the script client in real time to the web browser via HTTP once the web browser requests a connection to a remote machine for a remote desktop session. The web browser s connection to the remote machine is established through the transcoding server and the script client is deleted from the client device and the web browser when the remote desktop session is terminated or the browser is closed.

Illustration of Method Apparatus Machine Readable Storage Medium for facilitating accessing and controlling a remote desktop of a remote machine in real time by a web browser of a client device via a hypertext transfer protocol HTTP utilizing a transcoding server described as Clauses .

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 1 2 3 etc. for convenience. These are provided as examples and do not limit the subject technology. Clause 1 below is presented for example with reference to the figures of the present disclosure e.g. etc. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause e.g. clauses 1 11 and 22. The other clauses can be presented in a similar manner.

1. A method see e.g. method A of of facilitating accessing and controlling a remote desktop of a remote machine see e.g. of in real time by a web browser see e.g. of at a client device see e.g. in via a hypertext transfer protocol HTTP utilizing a transcoding server see e.g. of the method comprising 

receiving at the transcoding server a remote desktop drawing command based on an image of the remote desktop of the remote machine wherein the remote desktop drawing command is compatible with a remote desktop display protocol utilized by the remote machine see e.g. item A in 

translating at the transcoding server the remote desktop drawing command into a web browser drawing update that is compatible with the web browser see e.g. item A in and

facilitating providing the web browser drawing update from the transcoding server to the web browser of the client device utilizing HTTP during a remote desktop session between the client device and the remote machine see e.g. item A in 

2. The method of clause 1 wherein the web browser drawing update comprises an image file and drawing coordinates for the image file that are recognizable and processable by the web browser.

updating a portion of a Java bitmap using the Java graphics drawing command wherein the updated portion of the Java bitmap represents a portion of an entire image of the remote desktop 

wherein the web browser drawing update comprises the image file and the drawing coordinates for the image file 

wherein the transcoding server is a Java transcoding server that is configured to provide an application framework for hosting one or more web applications.

translating the remote desktop drawing command into a graphics drawing command that is compatible with the transcoding server wherein the graphics drawing command includes coordinates 

updating at least a portion of an off screen bitmap based on the graphics drawing command wherein the at least a portion of the off screen bitmap is associated with the coordinates 

translating the user input request into an input command compatible with the remote desktop display protocol and

providing the input command to the remote desktop client for accessing and controlling the remote desktop of the remote machine during the remote desktop session 

wherein the web browser drawing update comprises an image file and drawing coordinates for the image file that are recognizable and processable by the web browser 

wherein the image file and the drawing coordinates represent a portion of an entire image of the remote desktop that has been changed in response to the input command.

7. The method of clause 6 wherein the user input request comprises at least one of a mouse event a keyboard event and a touch event.

8. The method of clause 1 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from a remote desktop server of the remote machine 

wherein the translating comprises one or more of calculating new drawing command parameters based on the remote desktop drawing command parameters adjusting the remote desktop drawing command parameters and making adjustments to the bitmap data.

9. The method of clause 1 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from a remote desktop server of the remote machine 

wherein the making adjustments comprises converting a 16 bit red green blue RGB 5 6 5 color format into a 32 bit alpha red green blue ARGB 8 8 8 8 format.

10. The method of clause 1 wherein the transcoding server is an intermediary between the remote machine and the client device and wherein the transcoding server is physically separate from the remote machine.

11. A machine readable storage medium see e.g. machine readable storage medium B of encoded with instructions executable by a processing system to perform a method of facilitating accessing and controlling a remote desktop of a remote machine see e.g. of in real time by a web browser see e.g. of at a client device see e.g. of via a hypertext transfer protocol HTTP utilizing a transcoding server see e.g. of the instructions comprising code for 

receiving at the transcoding server a remote desktop drawing command based on an image of the remote desktop of the remote machine wherein the remote desktop drawing command is compatible with a remote desktop display protocol utilized by the remote machine see e.g. item B in 

translating at the transcoding server the remote desktop drawing command into a web browser drawing update that is compatible with the web browser see e.g. item A in and

facilitating providing the web browser drawing update from the transcoding server to the web browser of the client device using HTTP during a remote desktop session between the client device and the remote machine see e.g. item A in 

12. The machine readable storage medium of clause 11 wherein the web browser drawing update comprises an image file and drawing coordinates for the image file that are recognizable and processable by the web browser.

updating a portion of a Java bitmap using the Java graphics drawing command wherein the updated portion of the Java bitmap represents a portion of an entire image of the remote desktop 

wherein the web browser drawing update comprises the image file and the drawing coordinates for the image file 

wherein the transcoding server is a Java transcoding server that is configured to provide an application framework for hosting one or more web applications.

translating the remote desktop drawing command into a graphics drawing command that is compatible with the transcoding server wherein the graphics drawing command includes coordinates 

updating at least a portion of an off screen bitmap based on the graphics drawing command wherein the at least a portion of the off screen bitmap is associated with the coordinates 

15. The machine readable storage medium of clause 11 wherein the web browser is an HTML5 compatible web browser.

translating the user input request into an input command compatible with the remote desktop display protocol and

providing the input command to the remote desktop client for accessing and controlling the remote desktop of the remote machine during the remote desktop session 

wherein the web browser drawing update comprises an image file and drawing coordinates for the image file that are recognizable and processable by the web browser and

wherein the image file and the drawing coordinates represent a portion of an entire image of the remote desktop that has been changed in response to the input command.

17. The machine readable storage medium of clause 16 wherein the user input request comprises at least one of a mouse event a keyboard event and a touch event.

18. The machine readable storage medium of clause 11 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from a remote desktop server of the remote machine 

wherein the translating comprises one or more of calculating new drawing command parameters based on the remote desktop drawing command parameters adjusting the remote desktop drawing command parameters and making adjustments to the bitmap data.

19. The machine readable storage medium of clause 11 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from a remote desktop server of the remote machine 

wherein the making adjustments comprises converting a 16 bit red green blue RGB 5 6 5 color format into a 32 bit alpha red green blue ARGB 8 8 8 8 format.

20. The machine readable storage medium of clause 11 wherein the transcoding server is an intermediary between the remote machine and the client device and wherein the transcoding server is physically separate from the remote machine.

21. A computing machine comprising the machine readable storage medium of clause 11 wherein the computing machine is the transcoding server.

22. An apparatus for facilitating accessing and controlling a remote desktop of a remote machine see e.g. of in real time by a web browser see of at a client device see e.g. of via a hypertext transfer protocol HTTP utilizing a transcoding server see e.g. of the apparatus comprising 

means for receiving a remote desktop drawing command based on an image of the remote desktop of the remote machine wherein the remote desktop drawing command is compatible with a remote desktop display protocol utilized by the remote machine see e.g. item C in 

means for translating the remote desktop drawing command into a web browser drawing update that is compatible with the web browser see e.g. item C in and

means for facilitating providing the web browser drawing update from the transcoding server to the web browser of the client device utilizing HTTP during a remote desktop session between the client device and the remote machine see e.g. item C in 

23. The apparatus of clause 22 wherein the web browser drawing update comprises an image file and drawing coordinates for the image file that are recognizable and processable by the web browser.

means for updating a portion of a Java bitmap using the Java graphics drawing command wherein the updated portion of the Java bitmap represents a portion of an entire image of the remote desktop 

wherein the web browser drawing update comprises the image file and the drawing coordinates for the image file 

wherein the means for facilitating providing comprises means for placing the drawing coordinates into an HTTP header 

wherein the transcoding server is a Java transcoding server that is configured to provide an application framework for hosting one or more web applications.

means for translating the remote desktop drawing command into a graphics drawing command that is compatible with the transcoding server wherein the graphics drawing command includes coordinates 

means for updating at least a portion of an off screen bitmap based on the graphics drawing command wherein the at least a portion of the off screen bitmap is associated with the coordinates wherein the off screen bitmap is based on the image of the remote desktop and

means for translating the user input request into an input command compatible with the remote desktop display protocol and

means for providing the input command to the remote desktop client for accessing and controlling the remote desktop of the remote machine during the remote desktop session 

wherein the web browser drawing update comprises an image file and drawing coordinates for the image file that are recognizable and processable by the web browser and

wherein the image file and the drawing coordinates represent a portion of an entire image of the remote desktop that has been changed in response to the input command.

28. The apparatus of clause 27 wherein the user input request comprises at least one of a mouse event a keyboard event and a touch event.

29. The apparatus of clause 22 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from a remote desktop server of the remote machine 

wherein the means for translating comprises one or more of means for calculating new drawing command parameters based on the remote desktop drawing command parameters means for adjusting the remote desktop drawing command parameters and means for making adjustments to the bitmap data.

30. The apparatus of clause 22 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from a remote desktop server 

wherein the means for translating comprises means for making adjustments to the bitmap data of the remote machine 

wherein the means for making adjustments comprises means for converting a 16 bit red green blue RGB 5 6 5 color format into a 32 bit alpha red green blue ARGB 8 8 8 8 format.

31. The apparatus of clause 22 wherein the transcoding server is an intermediary between the remote machine and the client device and wherein the transcoding server is physically separate from the remote machine.

Illustration of Method Apparatus Machine Readable Storage Medium for facilitating conducting a remote desktop session between a web browser of a client device and a remote machine via a transcoding server in real time and utilizing hypertext markup language that supports a two dimensional 2D canvas and dynamic drawing described as Clauses .

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 1 2 3 etc. for convenience. These are provided as examples and do not limit the subject technology. Clause 1 below is presented for example with reference to . It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause e.g. clauses 1 11 and 22. The other clauses can be presented in a similar manner.

1. A method see e.g. item A in of facilitating conducting a remote desktop session between a web browser of a client device see e.g. in and a remote machine see e.g. via a transcoding server see e.g. in real time and utilizing hypertext markup language that supports a two dimensional 2D canvas and dynamic drawing the method comprising 

receiving at the transcoding server a user input request from the web browser of the client device for access and control of the remote machine wherein the web browser supports a 2D canvas and dynamic drawing see e.g. item A in 

translating at the transcoding server the user input request into an input command compatible with a remote desktop display protocol to be utilized by the transcoding server for facilitating communication with the remote machine see e.g. item A in 

receiving at the transcoding server a remote desktop drawing command from the remote machine in response to the input command see e.g. item A in 

translating at the transcoding server the remote desktop drawing command into a drawing update compatible with the hypertext markup language see e.g. item A in and

facilitating providing the drawing update from the transcoding server to the web browser see e.g. item A in 

wherein the transcoding server is an intermediary between the remote machine and the client device and wherein the transcoding server is physically separate from the remote machine.

wherein the web browser temporarily comprises JavaScript client code during the remote desktop session while the remote desktop session persists 

wherein the method comprises receiving at the transcoding server drawing requests from the JavaScript client code of the web browser 

wherein the facilitating providing the drawing update comprises facilitating providing the drawing update from the transcoding server to the JavaScript client code of the web browser in response to one of the drawing requests from the JavaScript client code of the web browser.

wherein the method comprises receiving at the transcoding server drawing requests from the web browser 

wherein the facilitating providing the drawing update comprises facilitating providing the drawing update from the transcoding server to the web browser in response to one of the drawing requests from the web browser.

4. The method of clause 1 wherein the transcoding server comprises a remote desktop client adapter configured to translate the user input request into the input command compatible with the remote desktop display protocol and to translate the remote desktop drawing command into the graphics drawing command.

5. The method of clause 1 comprising receiving long polling HTTP requests from the web browser wherein the long polling HTTP requests comprise drawing requests.

6. The method of clause 1 comprising receiving from the web browser an initial HTTP request comprising a uniform resource locator URL of the remote machine.

7. The method of clause 6 comprising facilitating providing a script client code to the web browser in response to the initial HTTP request for the URL of the remote machine wherein the script client code is compatible with HTML5.

8. The method of clause 1 wherein the remote desktop drawing command is compatible with the remote desktop display protocol wherein the remote desktop display protocol is a push protocol and wherein the facilitating providing the drawing update comprises facilitating providing the drawing update using HTTP that is a pull protocol.

9. The method of clause 1 wherein dynamic drawing comprises drawing in real time a portion of the 2D canvas rather than drawing the entire 2D canvas in response to one or more drawing requests of a script client of the web browser.

10. The method of clause 1 wherein the 2D canvas is updatable by a portion at a time according to a set of coordinates.

11. A machine readable storage medium see e.g. in encoded with instructions executable by a processing system see e.g. to perform a method of facilitating conducting a remote desktop session between a web browser of a client device see e.g. in and a remote machine see e.g. via a transcoding server see e.g. in real time and utilizing hypertext markup language that supports a two dimensional 2D canvas and dynamic drawing the instructions comprising code for 

receiving at the transcoding server a user input request from the web browser of the client device for access and control of the remote machine wherein the web browser supports a 2D canvas and dynamic drawing see e.g. item B in 

translating at the transcoding server the user input request into an input command compatible with a remote desktop display protocol to be utilized by the transcoding server for facilitating communication with the remote machine see e.g. item B in 

receiving at the transcoding server a remote desktop drawing command from the remote machine in response to the input command see e.g. item B in 

translating at the transcoding server the remote desktop drawing command into a drawing update compatible with the hypertext markup language see e.g. item B in and

facilitating providing the drawing update from the transcoding server to the web browser see e.g. item B in 

wherein the transcoding server is an intermediary between the remote machine and the client device and wherein the transcoding server is physically separate from the remote machine.

12. The machine readable storage medium of clause 11 wherein the translating the remote desktop drawing command comprises 

wherein the web browser temporarily comprises JavaScript client code during the remote desktop session while the remote desktop session persists 

wherein the method comprises receiving at the transcoding server drawing requests from the JavaScript client code of the web browser 

wherein the facilitating providing the drawing update comprises facilitating providing the drawing update from the transcoding server to the JavaScript client code of the web browser in response to one of the drawing requests from the JavaScript client code of the web browser.

13. The machine readable storage medium of clause 11 wherein the translating the remote desktop drawing command comprises 

wherein the method comprises receiving at the transcoding server drawing requests from the web browser and

wherein the facilitating providing the drawing update comprises facilitating providing the drawing update from the transcoding server to the web browser in response to one of the drawing requests from the web browser.

14. The machine readable storage medium of clause 11 wherein the transcoding server comprises a remote desktop client adapter configured to translate the user input request into the input command compatible with the remote desktop display protocol and to translate the remote desktop drawing command into the graphics drawing command.

15. The machine readable storage medium of clause 11 comprising code for receiving long polling HTTP requests from the web browser wherein the long polling HTTP requests comprise drawing requests.

16. The machine readable storage medium of clause 11 comprising code for receiving from the web browser an initial HTTP request comprising a uniform resource locator URL of the remote machine.

17. The machine readable storage medium of clause 16 comprising code for facilitating providing a script client code to the web browser in response to the initial HTTP request for the URL of the remote machine wherein the script client code is compatible with HTML5.

18. The machine readable storage medium of clause 11 wherein the remote desktop drawing command is compatible with the remote desktop display protocol wherein the remote desktop display protocol is a push protocol and wherein the facilitating providing the drawing update comprises facilitating providing the drawing update using HTTP that is a pull protocol.

19. The machine readable storage medium of clause 11 wherein dynamic drawing comprises drawing in real time a portion of the 2D canvas rather than drawing the entire 2D canvas in response to one or more drawing requests of a script client of the web browser.

20. The machine readable storage medium of clause 11 wherein the 2D canvas is updatable by a portion at a time according to a set of coordinates.

21. A computing machine comprising the machine readable storage medium of clause 11 wherein the computing machine is the transcoding server.

22. An apparatus see e.g. item C in for facilitating conducting a remote desktop session between a web browser of a client device see e.g. in and a remote machine see e.g. via a transcoding server see e.g. in real time and utilizing hypertext markup language that supports a two dimensional 2D canvas and dynamic drawing the apparatus comprising 

means for receiving a user input request from the web browser of the client device for access and control of the remote machine wherein the web browser supports a 2D canvas and dynamic drawing see e.g. item C in 

means for translating the user input request into an input command compatible with a remote desktop display protocol to be utilized by the transcoding server for facilitating communication with the remote machine see e.g. item C in 

means for receiving a remote desktop drawing command from the remote machine in response to the input command see e.g. item C in 

means for translating the remote desktop drawing command into a drawing update compatible with the hypertext markup language see e.g. item C in and

means for facilitating providing the drawing update from the transcoding server to the web browser see e.g. item C in 

wherein the transcoding server is an intermediary between the remote machine and the client device and wherein the transcoding server is physically separate from the remote machine.

23. The apparatus of clause 22 wherein the means for translating the remote desktop drawing command comprises 

wherein the web browser temporarily comprises JavaScript client code during the remote desktop session while the remote desktop session persists 

wherein the apparatus comprises means for receiving drawing requests from the JavaScript client code of the web browser 

wherein the means for facilitating providing the drawing update comprises means for facilitating providing the drawing update from the transcoding server to the JavaScript client code of the web browser in response to one of the drawing requests from the JavaScript client code of the web browser.

24. The apparatus of clause 22 wherein the means for translating the remote desktop drawing command comprises 

wherein the means for facilitating providing the drawing update comprises means for facilitating providing the drawing update from the transcoding server to the web browser in response to one of the drawing requests from the web browser.

25. The apparatus of clause 22 wherein the transcoding server comprises a remote desktop client adapter configured to translate the user input request into the input command compatible with the remote desktop display protocol and to translate the remote desktop drawing command into the graphics drawing command.

26. The apparatus of clause 22 comprising means for receiving long polling HTTP requests from the web browser wherein the long polling HTTP requests comprise drawing requests.

27. The apparatus of clause 22 comprising means for receiving from the web browser an initial HTTP request comprising a uniform resource locator URL of the remote machine.

28. The apparatus of clause 27 comprising means for facilitating providing a script client code to the web browser in response to the initial HTTP request for the URL of the remote machine wherein the script client code is compatible with HTML5.

29. The apparatus of clause 22 wherein the remote desktop drawing command is compatible with the remote desktop display protocol wherein the remote desktop display protocol is a push protocol and wherein the means for facilitating providing the drawing update comprises means for facilitating providing the drawing update using HTTP that is a pull protocol.

30. The apparatus of clause 22 wherein dynamic drawing comprises drawing in real time a portion of the 2D canvas rather than drawing the entire 2D canvas in response to one or more drawing requests of a script client of the web browser.

31. The apparatus of clause 22 wherein the 2D canvas is updatable by a portion at a time according to a set of coordinates.

Illustration of Method Apparatus Machine Readable Storage Medium for facilitating a remote desktop session between a web browser of a client device and a remote machine through a transcoding server utilizing hypertext transfer protocol HTTP headers of HTTP for remote desktop session drawing described as Clauses .

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 1 2 3 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause e.g. clauses 1 11 and 22. Clause 1 below is presented for example with reference to . The other clauses can be presented in a similar manner.

1. A method see e.g. item A in of facilitating a remote desktop session between a web browser of a client device see e.g. in and a remote machine see e.g. through a transcoding server see e.g. utilizing hypertext transfer protocol HTTP headers of HTTP for remote desktop session drawing the method comprising 

receiving at the transcoding server drawing requests from the web browser of the client device see e.g. item A in 

receiving at the transcoding server a remote desktop drawing command from the remote machine using a remote desktop display protocol wherein the remote desktop drawing command is based on an image of a remote desktop of the remote machine see e.g. item A in 

translating at the transcoding server the remote desktop drawing command into a display image and drawing coordinates for the display image see e.g. item A in 

placing at the transcoding server the drawing coordinates into an HTTP response header see e.g. item A in and

in response to at least one of the drawing requests facilitating providing the display image and the drawing coordinates together to the web browser in a single HTTP response for drawing the display image of the remote desktop at the web browser wherein the single HTTP response comprises the HTTP response header see e.g. item A in 

translating the remote desktop drawing command into a Java graphics drawing command wherein the transcoding server comprises a Java compatible web application container 

updating a portion of a Java graphics bitmap of the remote desktop in response to the Java graphics drawing command 

generating coordinates for the updated portion of the Java bitmap from the Java graphics drawing command 

generating the display image compatible with the web browser based on the updated portion of the Java bitmap and

obtaining the drawing coordinates for the display image based on the coordinates for the updated portion of the Java bitmap 

wherein the updated portion of the Java graphics bitmap represents a portion of an entire image of the remote desktop of the remote machine 

wherein the display image and the drawing coordinates represent the portion of the entire image of the remote desktop of the remote machine.

translating the remote desktop drawing command into a graphics drawing command compatible with the transcoding server 

generating the display image compatible with the web browser based on the updated portion of the bitmap and

4. The method of clause 1 wherein the display image and the drawing coordinates are compatible with HTML5.

5. The method of clause 1 wherein the transcoding server is an intermediary between the remote machine and the client device and wherein the transcoding server is physically separate from the remote machine.

6. The method of clause 1 wherein the remote desktop drawing command comprises coordinates of a region of the remote desktop that has changed relative to a previous remote desktop drawing command.

8. The method of clause 1 wherein the drawing coordinates are compatible with JavaScript client code of the web browser and wherein the display image is compatible with HTML of the web browser.

10. The method of clause 1 wherein the display image comprises an offset image of the remote desktop.

11. A machine readable storage medium see e.g. in encoded with instructions executable by a processing system see e.g. to perform a method of facilitating a remote desktop session between a web browser of a client device see e.g. in and a remote machine see e.g. through a transcoding server see e.g. utilizing hypertext transfer protocol HTTP headers of HTTP for remote desktop session drawing the instructions comprising code for 

receiving at the transcoding server drawing requests from the web browser of the client device see e.g. item B in 

receiving at the transcoding server a remote desktop drawing command from the remote machine using a remote desktop display protocol wherein the remote desktop drawing command is based on an image of a remote desktop of the remote machine see e.g. item B in 

translating at the transcoding server the remote desktop drawing command into a display image and drawing coordinates for the display image see e.g. item B in 

placing at the transcoding server the drawing coordinates into an HTTP response header see e.g. item B in and

in response to at least one of the drawing requests facilitating providing the display image and the drawing coordinates together to the web browser in a single HTTP response for drawing the display image of the remote desktop at the web browser wherein the single HTTP response comprises the HTTP response header see e.g. item B in 

updating a portion of a Java graphics bitmap of the remote desktop in response to the Java graphics drawing command 

generating coordinates for the updated portion of the Java bitmap from the Java graphics drawing command 

generating the display image compatible with the web browser based on the updated portion of the Java bitmap and

obtaining the drawing coordinates for the display image based on the coordinates for the updated portion of the Java bitmap 

wherein the updated portion of the Java graphics bitmap represents a portion of an entire image of the remote desktop of the remote machine 

wherein the display image and the drawing coordinates represent the portion of the entire image of the remote desktop of the remote machine.

translating the remote desktop drawing command into a graphics drawing command compatible with the transcoding server 

generating the display image compatible with the web browser based on the updated portion of the bitmap and

14. The machine readable storage medium of clause 11 wherein the display image and the drawing coordinates are compatible with HTML5.

15. The machine readable storage medium of clause 11 wherein the transcoding server is an intermediary between the remote machine and the client device and wherein the transcoding server is physically separate from the remote machine.

16. The machine readable storage medium of clause 11 wherein the remote desktop drawing command comprises coordinates of a region of the remote desktop that has changed relative to a previous remote desktop drawing command.

17. The machine readable storage medium of clause 16 wherein the coordinates specify a redrawing region.

18. The machine readable storage medium of clause 11 wherein the drawing coordinates are compatible with JavaScript client code of the web browser and wherein the display image is compatible with HTML of the web browser.

19. The machine readable storage medium of clause 11 wherein the display image comprises a scaled image of the remote desktop.

20. The machine readable storage medium of clause 11 wherein the display image comprises an offset image of the remote desktop.

21. A computing machine comprising the machine readable storage medium of clause 11 wherein the computing machine is the transcoding server.

22. An apparatus see e.g. item C in for facilitating a remote desktop session between a web browser of a client device see e.g. in and a remote machine see e.g. through a transcoding server see e.g. utilizing hypertext transfer protocol HTTP headers of HTTP for remote desktop session drawing the apparatus comprising 

means for receiving a remote desktop drawing command from the remote machine using a remote desktop display protocol wherein the remote desktop drawing command is based on an image of a remote desktop of the remote machine see e.g. item C in 

means for translating the remote desktop drawing command into a display image and drawing coordinates for the display image see e.g. item C in 

means for in response to at least one of the drawing requests facilitating providing the display image and the drawing coordinates together to the web browser in a single HTTP response for drawing the display image of the remote desktop at the web browser wherein the single HTTP response comprises the HTTP response header see e.g. item C in 

means for translating the remote desktop drawing command into a Java graphics drawing command wherein the transcoding server comprises a Java compatible web application container 

means for updating a portion of a Java graphics bitmap of the remote desktop in response to the Java graphics drawing command 

means for generating coordinates for the updated portion of the Java bitmap from the Java graphics drawing command 

means for generating the display image compatible with the web browser based on the updated portion of the Java bitmap and

means for obtaining the drawing coordinates for the display image based on the coordinates for the updated portion of the Java bitmap 

wherein the updated portion of the Java graphics bitmap represents a portion of an entire image of the remote desktop of the remote machine 

wherein the display image and the drawing coordinates represent the portion of the entire image of the remote desktop of the remote machine.

means for translating the remote desktop drawing command into a graphics drawing command compatible with the transcoding server 

means for updating a portion of a bitmap of the remote desktop based on the graphics drawing command 

means for generating the display image compatible with the web browser based on the updated portion of the bitmap and

25. The apparatus of clause 22 wherein the display image and the drawing coordinates are compatible with HTML5.

26. The apparatus of clause 22 wherein the transcoding server is an intermediary between the remote machine and the client device and wherein the transcoding server is physically separate from the remote machine.

27. The apparatus of clause 22 wherein the remote desktop drawing command comprises coordinates of a region of the remote desktop that has changed relative to a previous remote desktop drawing command.

29. The apparatus of clause 22 wherein the drawing coordinates are compatible with JavaScript client code of the web browser and wherein the display image is compatible with HTML of the web browser.

30. The apparatus of clause 22 wherein the display image comprises a scaled image of the remote desktop.

31. The apparatus of clause 22 wherein the display image comprises an offset image of the remote desktop.

Illustration of Method Apparatus Machine Readable Storage Medium for facilitating a remote desktop session between a web browser of a client device and a remote machine through a transcoding server utilizing long polling to reduce traffic to the client device described as Clauses .

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 1 2 3 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause e.g. clauses 1 11 and 22. Clause 1 below is presented for example with reference to . The other clauses can be presented in a similar manner.

1. A method see e.g. A of of facilitating a remote desktop session between a web browser see e.g. of of a client device see e.g. of and a remote machine see e.g. of through a transcoding server see e.g. of utilizing long polling to reduce traffic to the client device the method comprising 

receiving at the transcoding server a plurality of drawing requests from the web browser of the client device using HTTP wherein HTTP is a pull protocol see e.g. item A in 

handling at the transcoding server the plurality of drawing requests as long polling requests see e.g. item A in 

receiving at the transcoding server a remote desktop drawing command from the remote machine see e.g. item A in 

translating at the transcoding server the remote desktop drawing command into a web browser drawing update wherein the remote desktop drawing command is compatible with a push protocol wherein the web browser drawing update is compatible with HTTP wherein HTTP is a pull protocol see e.g. item A in and

facilitating providing the web browser drawing update from the transcoding server to the web browser of the client device utilizing HTTP as a response to at least one of the plurality of drawing requests from the web browser see e.g. item A in .

if there is no pending drawing command then storing the plurality of drawing requests in a drawing requests queue as long poling requests and if there is a pending drawing command then providing at least one of the plurality of drawing requests to an HTTP handler in the transcoding server to allow the HTTP handler to serve the pending drawing command in response to the at least one of the plurality of drawing requests.

3. The method of clause 1 wherein the remote desktop drawing command represents a portion of an entire image of a remote desktop of the remote machine 

if there is no pending drawing command then storing the plurality of drawing requests in a drawing requests queue as long poling requests and

if there is a pending drawing command then providing at least one of the plurality of drawing requests to an HTTP handler in the transcoding server to allow the HTTP handler to serve the pending drawing command in response to the at least one of the plurality of drawing requests.

placing at the HTTP handler the drawing coordinates into an HTTP header of a single HTTP transmission response to the web browser and

including at the HTTP handler the image file into the single HTTP transmission response to the web browser to facilitate providing the image file and the drawing coordinates together to the web browser in the single HTTP transmission response.

when a drawing commands queue has new coordinates sending a notification to the drawing requests queue to allow at least one of the plurality of drawing requests in the drawing requests queue to be forwarded to the HTTP handler.

receiving a new drawing request from the web browser in response to facilitating providing the web browser drawing update from the transcoding server to the web browser of the client device as a response to the at least one of the plurality of drawing requests from the web browser.

facilitating providing a JavaScript client code to the web browser in response to the request to connect to the remote machine 

wherein the receiving the plurality of drawing requests comprises receiving the plurality of drawing requests from the JavaScript client code 

wherein the facilitating providing the web browser drawing update comprises facilitating providing the web browser drawing update to the JavaScript client code.

9. The method of clause 8 comprising facilitating deleting the JavaScript client code from the web browser when the remote desktop session is terminated.

receiving at the transcoding server a user input request from the web browser for accessing or controlling a remote desktop of the remote machine 

translating at the transcoding server the user input request into an input command compatible with the push protocol 

wherein the receiving the remote desktop drawing command comprises receiving the remote desktop drawing command in response to the input command.

11. A machine readable storage medium see e.g. item B in encoded with instructions executable by a processing system to perform a method of facilitating a remote desktop session between a web browser see e.g. of of a client device see e.g. of and a remote machine see e.g. of through a transcoding server see e.g. of utilizing long polling to reduce traffic to the client device the instructions comprising code for 

receiving at the transcoding server a plurality of drawing requests from the web browser of the client device using HTTP wherein HTTP is a pull protocol see e.g. item B in 

handling at the transcoding server the plurality of drawing requests as long polling requests see e.g. item B in 

receiving at the transcoding server a remote desktop drawing command from the remote machine see e.g. item B in 

translating at the transcoding server the remote desktop drawing command into a web browser drawing update wherein the remote desktop drawing command is compatible with a push protocol wherein the web browser drawing update is compatible with HTTP wherein HTTP is a pull protocol see e.g. item B in and

facilitating providing the web browser drawing update from the transcoding server to the web browser of the client device utilizing HTTP as a response to at least one of the plurality of drawing requests from the web browser see e.g. item B in .

if there is no pending drawing command then storing the plurality of drawing requests in a drawing requests queue as long poling requests and

if there is a pending drawing command then providing at least one of the plurality of drawing requests to an HTTP handler in the transcoding server to allow the HTTP handler to serve the pending drawing command in response to the at least one of the plurality of drawing requests.

13. The machine readable storage medium of clause 11 wherein the remote desktop drawing command represents a portion of an entire image of a remote desktop of the remote machine 

if there is no pending drawing command then storing the plurality of drawing requests in a drawing requests queue as long poling requests and

if there is a pending drawing command then providing at least one of the plurality of drawing requests to an HTTP handler in the transcoding server to allow the HTTP handler to serve the pending drawing command in response to the at least one of the plurality of drawing requests.

placing at the HTTP handler the drawing coordinates into an HTTP header of a single HTTP transmission response to the web browser and

including at the HTTP handler the image file into the single HTTP transmission response to the web browser to facilitate providing the image file and the drawing coordinates together to the web browser in the single HTTP transmission response.

when a drawing commands queue has new coordinates sending a notification to the drawing requests queue to allow at least one of the plurality of drawing requests in the drawing requests queue to be forwarded to the HTTP handler.

receiving a new drawing request from the web browser in response to facilitating providing the web browser drawing update from the transcoding server to the web browser of the client device as a response to the at least one of the plurality of drawing requests from the web browser.

facilitating providing a JavaScript client code to the web browser in response to the request to connect to the remote machine 

wherein the receiving the plurality of drawing requests comprises receiving the plurality of drawing requests from the JavaScript client code 

wherein the facilitating providing the web browser drawing update comprises facilitating providing the web browser drawing update to the JavaScript client code.

19. The machine readable storage medium of clause 18 comprising code for facilitating deleting the JavaScript client code from the web browser when the remote desktop session is terminated.

receiving at the transcoding server a user input request from the web browser for accessing or controlling a remote desktop of the remote machine 

translating at the transcoding server the user input request into an input command compatible with the push protocol 

wherein the receiving the remote desktop drawing command comprises receiving the remote desktop drawing command in response to the input command.

21. A computing machine comprising the machine readable storage medium of clause 11 wherein the computing machine is the transcoding server.

22. An apparatus see e.g. item C in for facilitating a remote desktop session between a web browser see e.g. of of a client device see e.g. in and a remote machine see e.g. in through a transcoding server see e.g. in utilizing long polling to reduce traffic to the client device the apparatus comprising 

means for receiving a plurality of drawing requests from the web browser of the client device using HTTP wherein HTTP is a pull protocol see e.g. item C in 

means for translating the remote desktop drawing command into a web browser drawing update wherein the remote desktop drawing command is compatible with a push protocol wherein the web browser drawing update is compatible with HTTP wherein HTTP is a pull protocol see e.g. item C in and

means for facilitating providing the web browser drawing update from the transcoding server to the web browser of the client device utilizing HTTP as a response to at least one of the plurality of drawing requests from the web browser see e.g. item C in .

means for determining whether a drawing command is pending at the transcoding server for the web browser 

means for storing the plurality of drawing requests in a drawing requests queue as long poling requests if there is no pending drawing command and

means for providing at least one of the plurality of drawing requests to an HTTP handler in the transcoding server if there is a pending drawing command to allow the HTTP handler to serve the pending drawing command in response to the at least one of the plurality of drawing requests.

24. The apparatus of clause 22 wherein the remote desktop drawing command represents a portion of an entire image of a remote desktop of the remote machine 

means for determining whether a drawing command is pending at the transcoding server for the web browser 

means for storing the plurality of drawing requests in a drawing requests queue as long poling requests if there is no pending drawing command and

means for providing at least one of the plurality of drawing requests to an HTTP handler in the transcoding server if there is a pending drawing command to allow the HTTP handler to serve the pending drawing command in response to the at least one of the plurality of drawing requests.

means for placing at the HTTP handler the drawing coordinates into an HTTP header of a single HTTP transmission response to the web browser and

means for including at the HTTP handler the image file into the single HTTP transmission response to the web browser to facilitate providing the image file and the drawing coordinates together to the web browser in the single HTTP transmission response.

means for sending a notification to the drawing requests queue when a drawing commands queue has new coordinates to allow at least one of the plurality of drawing requests in the drawing requests queue to be forwarded to the HTTP handler.

means for receiving a new drawing request from the web browser in response to facilitating providing the web browser drawing update from the transcoding server to the web browser of the client device as a response to the at least one of the plurality of drawing requests from the web browser.

means for facilitating providing a JavaScript client code to the web browser in response to the request to connect to the remote machine 

wherein the means for receiving the plurality of drawing requests comprises means for receiving the plurality of drawing requests from the JavaScript client code 

wherein the means for facilitating providing the web browser drawing update comprises means for facilitating providing the web browser drawing update to the JavaScript client code.

30. The apparatus of clause 29 comprising means for facilitating deleting the JavaScript client code from the web browser when the remote desktop session is terminated.

means for receiving a user input request from the web browser for accessing or controlling a remote desktop of the remote machine 

means for translating the user input request into an input command compatible with the push protocol 

means for facilitating providing the input command to the remote machine utilizing the push protocol 

wherein the means for receiving the remote desktop drawing command comprises means for receiving the remote desktop drawing command in response to the input command.

Illustration of Method Apparatus Machine Readable Storage Medium for facilitating a remote desktop session between a web browser of a client device and a remote desktop server at a remote machine through a transcoding server utilizing an adapter at the transcoding server described as Clauses .

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 1 2 3 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause e.g. clauses 1 10 and 20. Clause 1 below is presented for example with reference to . The other clauses can be presented in a similar manner.

1. A method see e.g. item A in for facilitating a remote desktop session between a web browser of a client device see e.g. in and a remote desktop server at a remote machine see e.g. through a transcoding server see e.g. utilizing an adapter see e.g. in at the transcoding server the method comprising 

receiving at the adapter an input request from the web browser utilizing a request response protocol wherein the request response protocol is a pull protocol see e.g. item A in 

translating at the adapter the input request into an input command compatible with a remote desktop display protocol to be utilized by a remote desktop client at the transcoding server for facilitating communication with the remote desktop server at the remote machine wherein the remote desktop display protocol is a push protocol see e.g. item A in 

providing the input command to a remote desktop client at the transcoding server to facilitate providing the input command to the remote desktop server utilizing the remote desktop display protocol see e.g. item A in 

receiving at the adapter a remote desktop drawing command from the remote desktop server in response to the input command wherein the remote desktop drawing command is based on an image of a remote desktop of the remote machine see e.g. item A in and

translating at the adapter the remote desktop drawing command into a graphics drawing command compatible with the transcoding server to allow the transcoding server to facilitate providing a web browser drawing update to the web browser wherein the web browser drawing update is compatible with the web browser see e.g. item A in .

2. The method of clause 1 wherein the request response protocol comprises hypertext transfer protocol HTTP wherein the graphics drawing command is a Java graphics drawing command wherein the transcoding server is a Java transcoding server wherein the web browser is HTML5 compatible.

3. The method of clause 1 wherein the receiving the input request comprises receiving the input request from the web browser via an HTTP handler of a web application container at the transcoding server 

wherein the receiving the remote desktop drawing command comprises receiving the remote desktop drawing command via the remote desktop client using the remote desktop display protocol.

4. The method of clause 1 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from the remote desktop server 

wherein the translating the remote desktop drawing command comprises one or more of calculating new drawing command parameters based on the remote desktop drawing command parameters adjusting the remote desktop drawing command parameters and making adjustments to the bitmap data.

executing the graphics drawing command to generate and draw an image into a drawing commands queue at the transcoding server that is accessible by a web application container at the transcoding server for communicating with the web browser 

after generating the coordinates transmitting a notification to the web application container that a drawing command is ready to be served to the web browser 

receiving via an HTTP handler of the transcoding server a connection request from the web browser and

facilitating establishing controlling or terminating the remote desktop session between the remote desktop client and the remote desktop server in response to the connection request wherein the facilitating of the establishing controlling or terminating comprises 

8. The method of clause 7 wherein the session control command comprises at least one of a command for starting the remote desktop session a command for stopping the remote desktop session a credential a setting a preference and a command for passing at least one of a credential a setting and a preference.

wherein the at least a portion of the off screen bitmap is associated with the coordinates wherein the off screen bitmap represents an entire image of the remote desktop.

10. A machine readable storage medium see e.g. in encoded with instructions executable by a processing system see e.g. to perform a method for facilitating a remote desktop session between a web browser of a client device see e.g. in and a remote desktop server at a remote machine see e.g. through a transcoding server see e.g. utilizing an adapter see e.g. in at the transcoding server the instructions comprising code for 

receiving at the adapter an input request from the web browser utilizing a request response protocol wherein the request response protocol is a pull protocol see e.g. item B in 

translating at the adapter the input request into an input command compatible with a remote desktop display protocol to be utilized by a remote desktop client at the transcoding server for facilitating communication with the remote desktop server at the remote machine wherein the remote desktop display protocol is a push protocol see e.g. item B in 

providing the input command to a remote desktop client at the transcoding server to facilitate providing the input command to the remote desktop server utilizing the remote desktop display protocol see e.g. item B in 

receiving at the adapter a remote desktop drawing command from the remote desktop server in response to the input command wherein the remote desktop drawing command is based on an image of a remote desktop of the remote machine see e.g. item B in and

translating at the adapter the remote desktop drawing command into a graphics drawing command compatible with the transcoding server to allow the transcoding server to facilitate providing a web browser drawing update to the web browser wherein the web browser drawing update is compatible with the web browser see e.g. item B in .

11. The machine readable storage medium of clause 10 wherein the request response protocol comprises hypertext transfer protocol HTTP wherein the graphics drawing command is a Java graphics drawing command wherein the transcoding server is a Java transcoding server wherein the web browser is HTML5 compatible.

12. The machine readable storage medium of clause 10 wherein the receiving the input request comprises receiving the input request from the web browser via an HTTP handler of an application container at the transcoding server 

wherein the receiving the remote desktop drawing command comprises receiving the remote desktop drawing command via the remote desktop client using the remote desktop display protocol.

13. The machine readable storage medium of clause 10 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from the remote desktop server 

wherein the translating the remote desktop drawing command comprises one or more of calculating new drawing command parameters based on the remote desktop drawing command parameters adjusting the remote desktop drawing command parameters and making adjustments to the bitmap data.

executing the graphics drawing command to generate and draw an image into a drawing commands queue at the transcoding server that is accessible by a web application container at the transcoding server for communicating with the web browser 

after generating the coordinates transmitting a notification to the web application container that a drawing command is ready to be served to the web browser 

receiving via an HTTP handler of the transcoding server a connection request from the web browser and

facilitating establishing controlling or terminating the remote desktop session between the remote desktop client and the remote desktop server in response to the connection request wherein the facilitating of the establishing controlling or terminating comprises 

17. The machine readable storage medium of clause 16 wherein the session control command comprises at least one of a command for starting the remote desktop session a command for stopping the remote desktop session a credential a setting a preference and a command for passing at least one of a credential a setting and a preference.

updating at least a portion of an off screen bitmap based on the graphics drawing command wherein the at least a portion of the off screen bitmap is associated with the coordinates wherein the off screen bitmap represents an entire image of the remote desktop.

19. A computing machine comprising the machine readable storage medium of clause 10 wherein the computing machine is the transcoding server.

20. An apparatus see e.g. item C in for facilitating a remote desktop session between a web browser of a client device see e.g. in and a remote desktop server at a remote machine see e.g. through a transcoding server see e.g. utilizing an adapter see e.g. in at the transcoding server the apparatus comprising 

means for receiving an input request from the web browser utilizing a request response protocol wherein the request response protocol is a pull protocol see e.g. item C in 

means for translating the input request into an input command compatible with a remote desktop display protocol to be utilized by a remote desktop client at the transcoding server for facilitating communication with the remote desktop server at the remote machine wherein the remote desktop display protocol is a push protocol see e.g. item C in 

means for providing the input command to a remote desktop client at the transcoding server to facilitate providing the input command to the remote desktop server utilizing the remote desktop display protocol see e.g. item C in 

means for receiving a remote desktop drawing command from the remote desktop server in response to the input command wherein the remote desktop drawing command is based on an image of a remote desktop of the remote machine see e.g. item C in and

means for translating the remote desktop drawing command into a graphics drawing command compatible with the transcoding server to allow the transcoding server to facilitate providing a web browser drawing update to the web browser wherein the web browser drawing update is compatible with the web browser see e.g. item C in .

21. The apparatus of clause 20 wherein the request response protocol comprises hypertext transfer protocol HTTP wherein the graphics drawing command is a Java graphics drawing command wherein the transcoding server is a Java transcoding server wherein the web browser is HTML5 compatible.

22. The apparatus of clause 20 wherein the means for receiving the input request comprises means for receiving the input request from the web browser via an HTTP handler of a web application container at the transcoding server 

wherein the means for receiving the remote desktop drawing command comprises means for receiving the remote desktop drawing command via the remote desktop client using the remote desktop display protocol.

23. The apparatus of clause 20 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from the remote desktop server 

wherein the means for translating the remote desktop drawing command comprises one or more of means for calculating new drawing command parameters based on the remote desktop drawing command parameters means for adjusting the remote desktop drawing command parameters and means for making adjustments to the bitmap data.

means for executing the graphics drawing command to generate and draw an image into a drawing commands queue at the transcoding server that is accessible by a web application container at the transcoding server for communicating with the web browser 

means for transmitting after generating the coordinates a notification to the web application container that a drawing command is ready to be served to the web browser 

means for receiving via an HTTP handler of the transcoding server a connection request from the web browser and

means for facilitating establishing controlling or terminating the remote desktop session between the remote desktop client and the remote desktop server in response to the connection request wherein the means for facilitating of the establishing controlling or terminating comprises 

27. The apparatus of clause 26 wherein the session control command comprises at least one of a command for starting the remote desktop session a command for stopping the remote desktop session a credential a setting a preference and a command for passing at least one of a credential a setting and a preference.

means for updating at least a portion of an off screen bitmap based on the graphics drawing command wherein the at least a portion of the off screen bitmap is associated with the coordinates wherein the off screen bitmap represents an entire image of the remote desktop.

Illustration of Method Apparatus Machine Readable Storage Medium for facilitating accessing and controlling a remote desktop of a remote machine in real time from a web browser of a client device via a hypertext transfer protocol HTTP handler and a remote desktop client adapter for a transcoding server described as Clauses .

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 1 2 3 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause e.g. clauses 1 10 and 18. Clause 1 below is presented for example with reference to . The other clauses can be presented in a similar manner.

1. A machine readable storage medium see e.g. item A in comprising code for facilitating accessing and controlling a remote desktop of a remote machine see e.g. in in real time from a web browser see e.g. of at a client device see e.g. of via a hypertext transfer protocol HTTP handler see e.g. of and a remote desktop client adapter see e.g. of for a transcoding server see e.g. of the machine readable storage medium comprising 

wherein the HTTP handler is configured to facilitate receiving a connection request and a user input request from the web browser utilizing HTTP to facilitate providing the connection request and the user input request to the remote desktop client adapter and to facilitate providing a web browser drawing update to the web browser in response to a drawing request from the web browser wherein the web browser drawing update is compatible with the web browser 

wherein the remote desktop client adapter is configured to facilitate receiving the connection request and the user input request to translate the connection request into a session control command compatible with a remote desktop display protocol and to translate the user input request into a remote desktop input command compatible with the remote desktop display protocol 

wherein the remote desktop client adapter is configured to facilitate providing the session control command to a remote desktop client for providing the session control command to a remote desktop server of the remote machine and for establishing controlling or terminating a remote desktop session with the remote desktop server 

wherein the remote desktop client adapter is configured to facilitate providing the remote desktop input command to the remote desktop client for providing the remote desktop input command to the remote desktop server 

wherein the remote desktop client adapter is configured to facilitate receiving a remote desktop drawing command from the remote desktop server via the remote desktop client in response to the remote desktop input command wherein the remote desktop drawing command is compatible with the remote desktop display protocol 

wherein the remote desktop client adapter is configured to translate the remote desktop drawing command into a graphics drawing command compatible with the transcoding server and to update a portion of an image representing the entire remote desktop and coordinates based on the graphics drawing command and

wherein the HTTP handler is configured to generate an image file based on the updated portion of the image and to obtain drawing coordinates based on the coordinates in response to the drawing request wherein the web browser drawing update comprises the image file and the drawing coordinates 

2. The machine readable storage medium of clause 1 wherein the user input request comprises at least one of a mouse event a keyboard event and a touch event.

3. The machine readable storage medium of clause 1 wherein the session control command relates to establishing or controlling a connection between the remote desktop client and the remote desktop server and comprises at least one of a command for starting the remote desktop session a command for stopping the remote desktop session a credential a setting a preference and a command for passing at least one of a credential a setting and a preference.

4. The machine readable storage medium of clause 1 wherein the graphics drawing command is a Java graphics drawing command wherein the transcoding server is a Java transcoding server and wherein the web browser is HTML5 compatible.

5. The machine readable storage medium of clause 1 wherein the remote desktop client adapter is configured to place the image and the coordinates into a drawing commands queue 

wherein the long polling handler is configured to facilitate receiving the drawing request from the web browser utilizing HTTP to forward the drawing request to the HTTP handler if coordinates for an image are pending in the drawing commands queue to place the drawing request into a drawing requests queue if coordinates for an image are not pending in the drawing commands and

wherein the drawing commands queue is configured to send a notification to the drawing requests queue if the drawing commands queue receives a new drawing command comprising an image and coordinates for an image.

6. The machine readable storage medium of clause 1 comprising a drawing requests queue configured to forward the drawing request to the HTTP handler in response to a notification from a drawing commands queue that a drawing command is pending for the web browser.

7. The machine readable storage medium of clause 1 wherein the HTTP handler is configured to place the drawing coordinates into a section of an HTTP header wherein the HTTP handler is configured to facilitate providing the image file and the drawing coordinates together to the web browser in a single HTTP transmission response for drawing a display image at the web browser wherein the display image represents the updated portion of the image representing the entire remote desktop.

8. The machine readable storage medium of clause 1 wherein the HTTP handler is configured to facilitate providing script client code compatible with the web browser to the web browser if the connection request from the web browser comprises a request to connect to the remote machine.

9. A computing machine comprising the machine readable storage medium of clause 1 wherein the computing machine is the transcoding server.

10. A method see e.g. item B of and item C of for facilitating accessing and controlling a remote desktop of a remote machine see e.g. of in real time from a web browser see e.g. of at a client device see e.g. of utilizing a transcoding server see e.g. of the method comprising 

receiving at the transcoding server a connection request from the web browser utilizing HTTP see e.g. item B of 

translating at the transcoding server the connection request into a session control command compatible with a remote desktop display protocol see e.g. item B of 

providing the session control command to a remote desktop client of the transcoding server for providing the session control command to a remote desktop server of the remote machine and for establishing controlling or terminating a remote desktop session with the remote desktop server see e.g. item B of 

receiving at the transcoding server a user input request from the web browser utilizing HTTP see e.g. item B of 

translating at the transcoding server the user input request into a remote desktop input command compatible with the remote desktop display protocol see e.g. item B of 

providing the remote desktop input command to the remote desktop client for providing the remote desktop input command to the remote desktop server see e.g. item B of 

receiving at the transcoding server a remote desktop drawing command from the remote desktop server via the remote desktop client in response to the remote desktop input command wherein the remote desktop drawing command is compatible with the remote desktop display protocol and wherein the remote desktop drawing command represents a portion of an entire image of the remote desktop see e.g. item C of 

translating at the transcoding server the remote desktop drawing command into a graphics drawing command compatible with the transcoding server see e.g. item C of 

updating at the transcoding server a portion of an image and coordinates based on the graphics drawing command see e.g. item C of 

generating at the transcoding server an image file based on the updated portion of the image see e.g. item C of 

facilitating providing a web browser drawing update to the web browser in response to a drawing request from the web browser wherein the web browser drawing update comprises the image file and the drawing coordinates and wherein the web browser drawing update is compatible with the web browser see e.g. item C of 

wherein the remote desktop drawing command represents a portion of the entire remote desktop and the image represents the entire remote desktop 

11. The method of clause 10 wherein the user input request comprises at least one of a mouse event a keyboard event and a touch event.

12. The method of clause 10 wherein the session control command comprises at least one of a command for starting the remote desktop session a command for stopping the remote desktop session a credential a setting a preference and a command for passing at least one of a credential a setting and a preference.

13. The method of clause 10 wherein the graphics drawing command is a Java graphics drawing command wherein the transcoding server is a Java transcoding server and wherein the web browser is HTML5 compatible.

14. The method of clause 10 wherein the updating a portion of an image and coordinates comprises storing the portion of the image and the coordinates into a drawing commands queue 

wherein the method comprises receiving the drawing request from the web browser utilizing HTTP forwarding the drawing request to an HTTP handler if coordinates for an image are pending in the drawing commands queue placing the drawing request into a drawing requests queue if coordinates for an image are not pending in the drawing commands and

wherein the method comprises sending a notification to the drawing requests queue if the drawing commands queue receives a new drawing command comprising an image and coordinates for an image.

15. The method of clause 10 comprising forwarding the drawing request to an HTTP handler in response to a notification from a drawing commands queue that a drawing command is pending for the web browser.

16. The method of clause 10 comprising placing the drawing coordinates into a section of an HTTP header wherein the facilitating providing the web browser drawing update comprises facilitating providing the image file and the drawing coordinates together to the web browser in a single HTTP transmission response for drawing a display image at the web browser wherein the display image represents the updated portion of the image representing the entire remote desktop.

17. The method of clause 10 comprising facilitate providing script client code compatible with the web browser to the web browser if the connection request from the web browser comprises a request to connect to the remote machine.

18. A transcoding server see e.g. item D of and item E of for facilitating accessing and controlling a remote desktop of a remote machine see e.g. of in real time from a web browser see e.g. of at a client device see e.g. of the transcoding server comprising 

means for translating the connection request into a session control command compatible with a remote desktop display protocol see e.g. item D in 

means for providing the session control command to a remote desktop client of the transcoding server for providing the session control command to a remote desktop server of the remote machine and for establishing controlling or terminating a remote desktop session with the remote desktop server see e.g. item D in 

means for translating the user input request into a remote desktop input command compatible with the remote desktop display protocol see e.g. item D in 

means for providing the remote desktop input command to the remote desktop client for providing the remote desktop input command to the remote desktop server see e.g. item D in 

means for receiving a remote desktop drawing command from the remote desktop server via the remote desktop client in response to the remote desktop input command wherein the remote desktop drawing command is compatible with the remote desktop display protocol and wherein the remote desktop drawing command represents a portion of an entire image of the remote desktop see e.g. item E in 

means for translating the remote desktop drawing command into a graphics drawing command compatible with the transcoding server see e.g. item E in 

means for updating a portion of an image and coordinates based on the graphics drawing command see e.g. item E in 

means for facilitating providing a web browser drawing update to the web browser in response to a drawing request from the web browser wherein the web browser drawing update comprises the image file and the drawing coordinates and wherein the web browser drawing update is compatible with the web browser see e.g. item E in 

wherein the remote desktop drawing command represents a portion of the entire remote desktop and the image represents the entire remote desktop 

19. The transcoding server of clause 18 wherein the user input request comprises at least one of a mouse event a keyboard event and a touch event.

20. The transcoding server of clause 18 wherein the session control command comprises at least one of a command for starting the remote desktop session a command for stopping the remote desktop session a credential a setting a preference and a command for passing at least one of a credential a setting and a preference.

21. The transcoding server of clause 18 wherein the graphics drawing command is a Java graphics drawing command wherein the transcoding server is a Java transcoding server and wherein the web browser is HTML5 compatible.

22. The transcoding server of clause 18 wherein the means for updating a portion of an image and coordinates comprises means for storing the portion of the image and the coordinates into a drawing commands queue 

wherein the transcoding server comprises means for receiving the drawing request from the web browser utilizing HTTP means for forwarding the drawing request to an HTTP handler if coordinates for an image are pending in the drawing commands queue means for placing the drawing request into a drawing requests queue if coordinates for an image are not pending in the drawing commands and

wherein the transcoding server comprises means for sending a notification to the drawing requests queue if the drawing commands queue receives a new drawing command comprising an image and coordinates for an image.

23. The transcoding server of clause 18 comprising means for forwarding the drawing request to an HTTP handler in response to a notification from a drawing commands queue that a drawing command is pending for the web browser.

24. The transcoding server of clause 18 comprising means for placing the drawing coordinates into a section of an HTTP header wherein the means for facilitating providing the web browser drawing update comprises means for facilitating providing the image file and the drawing coordinates together to the web browser in a single HTTP transmission response for drawing a display image at the web browser wherein the display image represents the updated portion of the image representing the entire remote desktop.

25. The transcoding server of clause 18 comprising means for facilitate providing script client code compatible with the web browser to the web browser if the connection request from the web browser comprises a request to connect to the remote machine.

26. A processor comprising modules configured to perform the method of any one of the foregoing clauses.

27. A machine readable storage medium comprising code for causing the transcoding server to perform the method of any one of the foregoing clauses.

28. The machine readable storage medium of clause 27 wherein the transcoding server comprises the machine readable storage medium.

33. An apparatus comprising components operable to perform the method of any one of the foregoing clauses.

Illustration of Method Apparatus Machine Readable Storage Medium for facilitating a remote desktop session between a web browser at and a remote desktop server described as Clauses .

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 1 2 3 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause. Clause 1 below is presented for example with reference to . The other clauses can be presented in a similar manner.

1. A method see e.g. method A of of facilitating accessing and controlling a remote desktop of a remote machine see e.g. of in real time by a web browser of a client device see e.g. of via a hypertext transfer protocol HTTP utilizing a web server see e.g. of the method comprising 

receiving at the web server a remote desktop drawing command based on an image of the remote desktop of the remote machine wherein the remote desktop drawing command is compatible with a remote desktop display protocol utilized by the remote machine see e.g. A of 

translating at the web server the remote desktop drawing command into a web browser drawing update that is compatible with the web browser see e.g. A of and

facilitating providing the web browser drawing update from the web server to the web browser of the client device utilizing HTTP during a remote desktop session between the client device and the remote machine see e.g. A of 

wherein i the remote desktop display protocol is a push protocol ii HTTP is a pull protocol and iii the web browser comprises a windows web browser.

2. The method of clause 1 wherein the web browser drawing update comprises an image file and drawing coordinates for the image file that are recognizable and processable by the windows web browser.

updating a portion of a memory bitmap using the windows graphics drawing command wherein the updated portion of the memory bitmap represents a portion of an entire image of the remote desktop 

wherein the web browser drawing update comprises the image file and the drawing coordinates for the image file 

wherein the web server is configured to facilitate providing an application framework for hosting one or more web applications comprising an ASP.NET model view controller MVC 

wherein the one or more web applications comprise one or more HTTP handlers and wherein the one or more HTTP handlers comprise the HTTP controller of the ASP.NET MVC.

translating the remote desktop drawing command into a graphics drawing command that is compatible with the windows web server wherein the graphics drawing command includes coordinates 

updating at least a portion of an off screen bitmap based on the graphics drawing command wherein the at least a portion of the off screen bitmap is associated with the coordinates 

creating an image file including a windows image file based on the at least a portion of the off screen bitmap and

translating the user input request into an input command compatible with the remote desktop display protocol and

providing the input command to the remote desktop client for accessing and controlling the remote desktop of the remote machine during the remote desktop session 

wherein the web browser drawing update comprises an image file including a windows image file and drawing coordinates for the image file that are recognizable and processable by the windows web browser 

wherein the image file and the drawing coordinates represent a portion of an image of the remote desktop that has been changed in response to the input command.

7. The method of clause 6 wherein the user input request comprises at least one of a mouse event a keyboard event and a touch event.

8. The method of clause 1 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from a remote desktop server of the remote machine 

wherein the translating comprises one or more of calculating new drawing command parameters based on the remote desktop drawing command parameters adjusting the remote desktop drawing command parameters and making adjustments to the bitmap data.

9. The method of clause 1 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from a remote desktop server of the remote machine 

wherein the making adjustments comprises converting a 16 bit red green blue RGB 5 6 5 color format into a 32 bit alpha red green blue ARGB 8 8 8 8 format.

10. The method of clause 1 wherein the web server is an intermediary between the remote machine and the client device and wherein the web server is physically separate from the remote machine.

11. A machine readable storage medium see e.g. in B of comprising instructions stored therein the instructions executable by one or more processors see e.g. to perform one or more operations the instructions comprising 

code for causing one or more processors to facilitate receiving a remote desktop drawing command based on an image of a remote desktop of a remote machine wherein the remote desktop drawing command is compatible with a remote desktop display protocol of the remote machine see e.g. B of 

code for causing one or more processors to translate the remote desktop drawing command into a web browser drawing update that is compatible with a web browser see e.g. B of and

code for causing one or more processors to facilitate providing the web browser drawing update utilizing hypertext transfer protocol HTTP during a remote desktop session between a client device for the web browser and the remote machine see e.g. B of 

wherein i the remote desktop display protocol is a push protocol ii HTTP is a pull protocol and iii the web browser comprises a windows web browser.

12. The machine readable storage medium of clause 11 wherein the web browser drawing update comprises an image file and drawing coordinates for the image file that are recognizable and processable by the windows web browser.

13. The machine readable storage medium of clause 11 wherein the code for causing one or more processors to translate comprises 

code for causing one or more processors to translate at a web server the remote desktop drawing command into a windows graphics drawing command 

code for causing one or more processors to update a portion of a memory bitmap using the windows graphics drawing command wherein the updated portion of the memory bitmap represents a portion of an image of the remote desktop 

code for causing one or more processors to create an image file including a windows image file from the memory bitmap and

wherein the web browser drawing update comprises the image file and the drawing coordinates for the image file 

wherein the code for causing one or more processors to facilitate providing comprises code for causing one or more processors to place the drawing coordinates into an HTTP header 

wherein code for causing one or more processors to utilize HTTP comprises code for causing one or more processors to use an HTTP controller 

wherein the web server is configured to facilitate providing an application framework for hosting one or more web applications wherein the one or more web applications comprise one or more HTTP handlers and wherein the one or more HTTP handlers comprise the HTTP controller.

14. The machine readable storage medium of clause 11 wherein the code for causing one or more processors to translate comprises 

code for causing one or more processors to translate at a web server the remote desktop drawing command into a graphics drawing command that is compatible with the web server wherein the graphics drawing command includes coordinates 

code for causing one or more processors to extract the coordinates from the graphics drawing command 

code for causing one or more processors to update at least a portion of an off screen bitmap based on the graphics drawing command wherein the at least a portion of the off screen bitmap is associated with the coordinates 

code for causing one or more processors to create an image file including a windows image file based on the at least a portion of the off screen bitmap and

15. The machine readable storage medium of clause 11 wherein the web browser is an HTML5 compatible web browser.

code for causing one or more processors to facilitate receiving a user input request from the web browser using HTTP 

code for causing one or more processors to translate the user input request into an input command compatible with the remote desktop display protocol and

code for causing one or more processors to facilitate providing the input command to the remote desktop client for accessing and controlling the remote desktop of the remote machine during the remote desktop session 

wherein the web browser drawing update comprises an image file including a windows image file and drawing coordinates for the image file that are recognizable and processable by the windows web browser and

wherein the image file and the drawing coordinates represent a portion of an image of the remote desktop that has been changed in response to the input command.

17. The machine readable storage medium of clause 16 wherein the user input request comprises at least one of a mouse event a keyboard event and a touch event.

18. The machine readable storage medium of clause 11 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from a remote desktop server of the remote machine 

wherein the code for causing one or more processors to translate comprises one or more of code for causing one or more processors to calculate new drawing command parameters based on the remote desktop drawing command parameters code for causing one or more processors to adjust the remote desktop drawing command parameters and code for causing one or more processors to make adjustments to the bitmap data.

19. The machine readable storage medium of clause 11 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from a remote desktop server of the remote machine 

wherein the code for causing one or more processors to translate comprises code for causing one or more processors to make adjustments to the bitmap data 

wherein the code for causing one or more processors to make adjustments comprises code for causing one or more processors to convert a 16 bit red green blue RGB 5 6 5 color format into a 32 bit alpha red green blue ARGB 8 8 8 8 format.

20. The machine readable storage medium of clause 11 wherein the code for causing one or more processors to translate is to be executed at a web server and wherein the web server is an intermediary between the remote machine and the client device and wherein the web server is physically separate from the remote machine.

21. A computing machine comprising the machine readable storage medium of clause 11 wherein the computing machine is a web server.

22. An apparatus see e.g. C of for facilitating accessing and controlling a remote desktop of a remote machine see e.g. of in real time by a web browser see e.g. of at a client device see e.g. of via a hypertext transfer protocol HTTP utilizing a web server see e.g. of the apparatus comprising 

means for receiving a remote desktop drawing command based on an image of the remote desktop of the remote machine wherein the remote desktop drawing command is compatible with a remote desktop display protocol utilized by the remote machine see e.g. C of 

means for translating the remote desktop drawing command into a web browser drawing update that is compatible with the web browser see e.g. C of and

means for translating the remote desktop drawing command into a web browser drawing update that is compatible with the web browser see e.g. C of 

wherein i the remote desktop display protocol is a push protocol ii HTTP is a pull protocol and iii the web browser comprises a windows web browser.

23. The apparatus of clause 22 wherein the web browser drawing update comprises an image file including a windows image file and drawing coordinates for the image file that are recognizable and processable by the windows web browser.

means for updating a portion of a memory bitmap using the windows graphics drawing command wherein the updated portion of the memory bitmap represents a portion of an entire image of the remote desktop session 

wherein the web browser drawing update comprises the image file and the drawing coordinates for the image file 

wherein the means for facilitating providing comprises means for placing the drawing coordinates into an HTTP header 

wherein the web server is a windows web server that is configured to facilitate providing an application framework for hosting one or more web applications comprising an ASP.NET model view controller MVC wherein the one or more web applications comprise one or more HTTP handlers and wherein the one or more HTTP handlers comprise the HTTP controller of the ASP.NET MVC.

means for translating the remote desktop drawing command into a graphics drawing command that is compatible with the windows web server wherein the graphics drawing command includes coordinates 

means for updating at least a portion of an off screen bitmap based on the graphics drawing command wherein the at least a portion of the off screen bitmap is associated with the coordinates wherein the off screen bitmap is based on the image of the entire remote desktop and

means for creating an image file including a windows image file based on the at least a portion of the off screen bitmap 

means for translating the user input request into an input command compatible with the remote desktop display protocol and

means for providing the input command to the remote desktop client for accessing and controlling the remote desktop of the remote machine during the remote desktop session 

wherein the web browser drawing update comprises an image file including a windows image file and drawing coordinates for the image file that are recognizable and processable by the windows web browser and

wherein the image file and the drawing coordinates represent a portion of an image of the of the remote desktop that has been changed in response to the input command.

28. The apparatus of clause 27 wherein the user input request comprises at least one of a mouse event a keyboard event and a touch event.

29. The apparatus of clause 22 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from a remote desktop server of the remote machine 

wherein the means for translating comprises one or more of means for calculating new drawing command parameters based on the remote desktop drawing command parameters means for adjusting the remote desktop drawing command parameters and means for making adjustments to the bitmap data.

30. The apparatus of clause 22 wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from a remote desktop server 

wherein the means for translating comprises means for making adjustments to the bitmap data of the remote machine 

wherein the means for making adjustments comprises means for converting a 16 bit red green blue RGB 5 6 5 color format into a 32 bit alpha red green blue ARGB 8 8 8 8 format.

31. The apparatus of clause 22 wherein the web server is an intermediary between the remote machine and the client device and wherein the web server is physically separate from the remote machine.

Illustration of Method Apparatus Machine Readable Storage Medium for facilitating a remote desktop redrawing session utilizing HTML described as Clauses .

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 1 2 3 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause. Clause 1 below is presented for example with reference to . The other clauses can be presented in a similar manner.

1. A method see e.g. A of of facilitating conducting a remote desktop session between a web browser see e.g. of of a client device and a remote machine see e.g. of via a web server see e.g. of in real time and utilizing hypertext markup language HTML that supports a two dimensional 2D canvas and dynamic drawing the method comprising 

receiving at the web server a user input request from the web browser of the client device for access and control of the remote machine wherein the web browser supports a 2D canvas and dynamic drawing see e.g. A of 

translating at the web server the user input request into an input command compatible with a remote desktop display protocol to be utilized by the web server for facilitating communication with the remote machine see e.g. A of 

receiving at the web server a remote desktop drawing command from the remote machine in response to the input command see e.g. A of 

translating at the web server the remote desktop drawing command into a drawing update compatible with the hypertext markup language see e.g. A of and

wherein the web server is an intermediary between the remote machine and the client device and wherein the web server comprises a windows web server and is physically separate from the remote machine.

2. The method of clause 1 wherein the web browser comprises a windows web browser and wherein the translating the remote desktop drawing command comprises 

executing the windows graphics drawing command to update a portion of a memory bitmap wherein the memory bitmap represents an image of a remote desktop of the remote machine 

forming an image file including a windows image file based on the memory bitmap wherein the image file is compatible with HTML5 and

obtaining drawing coordinates for the image file based on the coordinates for the memory bitmap wherein the drawing coordinates are compatible with HTML5 

wherein the method comprises receiving at the web server drawing requests from the client script code of the web browser 

wherein the facilitating providing the drawing update comprises facilitating providing the drawing update from the web server to the client script code of the web browser in response to one of the drawing requests from the client script code of the web browser.

translating the remote desktop drawing command into a graphics drawing command compatible with the windows web server 

updating a portion of a bitmap based on the graphics drawing command wherein the updated portion of the bitmap represents a portion of an image of a remote desktop of the remote machine that has changed relative to a previous graphics drawing command 

forming an image file including a windows image file based on the bitmap wherein the image file is HTML5 compatible and

obtaining drawing coordinates for the image file wherein the drawing coordinates are compatible with HTML5 

wherein the facilitating providing the drawing update comprises facilitating providing the drawing update from the web server to the web browser in response to one of the drawing requests from the web browser.

4. The method of clause 1 wherein the web server comprises a remote desktop client wrapper configured to translate the user input request into the input command compatible with the remote desktop display protocol and to translate the remote desktop drawing command into the graphics drawing command compatible with a windows web browser.

5. The method of clause 1 comprising receiving long asynchronous HTTP requests from the web browser wherein the asynchronous HTTP requests comprise drawing requests and the web browser comprises a windows web browser.

6. The method of clause 1 comprising receiving from the web browser an initial HTTP request comprising a uniform resource locator URL of the remote machine.

7. The method of clause 6 comprising facilitating providing a script client code to the web browser in response to the initial HTTP request for the URL of the remote machine wherein the script client code is compatible with HTML5.

8. The method of clause 1 wherein the remote desktop drawing command is compatible with the remote desktop display protocol wherein the remote desktop display protocol is a push protocol and wherein the facilitating providing the drawing update comprises facilitating providing the drawing update using HTTP that is a pull protocol.

9. The method of clause 1 wherein dynamic drawing comprises drawing in real time a portion of the 2D canvas rather than drawing the entire 2D canvas in response to one or more drawing requests of a script client of the web browser.

10. The method of clause 1 wherein the 2D canvas is updatable by a portion at a time according to a set of coordinates.

11. A machine readable storage medium see e.g. in B of comprising instructions stored therein the instructions executable by one or more processors see e.g. the instructions comprising 

code for causing one or more processors to facilitate receiving a user input request from a web browser of a client device for access and control of a remote machine wherein the web browser supports a 2D canvas and dynamic drawing see e.g. B of 

code for causing one or more processors to translate the user input request into an input command compatible with a remote desktop display protocol to be utilized for facilitating communication with the remote machine see e.g. B of 

code for causing one or more processors to facilitate receiving a remote desktop drawing command from the remote machine in response to the input command see e.g. B of 

code for causing one or more processors to translate the remote desktop drawing command into a drawing update compatible with hypertext markup language see e.g. B of and

code for causing one or more processors to facilitate providing the drawing update to the web browser see e.g. B of .

12. The machine readable storage medium of clause 11 wherein the web browser comprises a windows web browser and wherein the code for causing one or more processors to translate the remote desktop drawing command comprises 

code for causing one or more processors to translate the remote desktop drawing command into a windows graphics drawing command 

code for causing one or more processors to execute the windows graphics drawing command to update a portion of a windows graphics application programming interface API memory bitmap wherein the windows graphics API memory bitmap represents an image of a remote desktop of the remote machine 

code for causing one or more processors to generate coordinates for the updated portion of the windows graphics API memory bitmap based on the windows graphics drawing command 

code for causing one or more processors to form an image file including a windows image file based on the updated portion of the windows graphics API memory bitmap wherein the image file is compatible with HTML5 and

code for causing one or more processors to obtain drawing coordinates for the image file based on the coordinates for the updated portion of the windows graphics API memory bitmap wherein the drawing coordinates are compatible with HTML5 

wherein the instructions comprise code for causing one or more processors to facilitate receiving at a web server drawing requests from the client script code of the web browser 

wherein the code for causing one or more processors to facilitate providing the drawing update comprises code for causing one or more processors to facilitate providing the drawing update from the web server to the client script code of the web browser in response to one of the drawing requests from the client script code of the web browser.

13. The machine readable storage medium of clause 11 wherein the code for causing one or more processors to translate the remote desktop drawing command comprises 

code for causing one or more processors to translate the remote desktop drawing command into a graphics drawing command compatible with the web server 

code for causing one or more processors to update a portion of a bitmap based on the graphics drawing command wherein the updated portion of the bitmap represents a portion of an image of a remote desktop of the remote machine that has changed relative to a previous graphics drawing command 

code for causing one or more processors to generate coordinates for the updated portion of the bitmap 

code for causing one or more processors to form an image file including a windows image file based on the updated portion of the bitmap wherein the image file is HTML5 compatible and

code for causing one or more processors to obtain drawing coordinates for the image file wherein the drawing coordinates are compatible with HTML5 

wherein the instructions comprise code for causing one or more processors to facilitate receiving at the web server drawing requests from the web browser and

wherein the code for causing one or more processors to facilitate providing the drawing update comprises code for causing one or more processors to facilitate providing the drawing update to the web browser in response to one of the drawing requests from the web browser.

14. The machine readable storage medium of clause 11 wherein the remote desktop display protocol is to be utilized by a web server wherein the web server is an intermediary between the remote machine and the client device and wherein the web server comprises a windows web server and is physically separate from the remote machine wherein the web server comprises a remote desktop client wrapper configured to translate the user input request into the input command compatible with the remote desktop display protocol and to translate the remote desktop drawing command into the graphics drawing command compatible with a windows web browser.

15. The machine readable storage medium of clause 11 wherein the instructions comprise code for causing one or more processors to facilitate receiving asynchronous HTTP requests from the web browser wherein the asynchronous HTTP requests comprise drawing requests and the web browser comprises a windows web browser.

16. The machine readable storage medium of clause 11 wherein the instructions comprise code for causing one or more processors to facilitate receiving from the web browser an initial HTTP request comprising a uniform resource locator URL of the remote machine.

17. The machine readable storage medium of clause 16 wherein the instructions comprise code for causing one or more processors to facilitate providing a script client code to the web browser in response to the initial HTTP request for the URL of the remote machine wherein the script client code is compatible with HTML5.

18. The machine readable storage medium of clause 11 wherein the remote desktop drawing command is compatible with the remote desktop display protocol wherein the remote desktop display protocol is a push protocol wherein the code for causing one or more processors to facilitate providing the drawing update comprises code for causing one or more processors to facilitate providing the drawing update using HTTP that is a pull protocol and wherein the drawing updates are compatible with a windows graphic protocol.

19. The machine readable storage medium of clause 11 wherein dynamic drawing comprises drawing in real time a portion of the 2D canvas rather than drawing the entire 2D canvas in response to one or more drawing requests of a script client of the web browser.

20. The machine readable storage medium of clause 11 wherein the 2D canvas is updatable by a portion at a time according to a set of coordinates.

21. A computing machine comprising the machine readable storage medium of clause 11 wherein the computing machine is a web server.

22. An apparatus see e.g. C of for facilitating conducting a remote desktop session between a web browser of a client device and a remote machine via a web server in real time and utilizing hypertext markup language that supports a two dimensional 2D canvas and dynamic drawing the apparatus comprising 

means for receiving a user input request from the web browser of the client device for access and control of the remote machine wherein the web browser supports a 2D canvas and dynamic drawing see e.g. C of 

means for translating the user input request into an input command compatible with a remote desktop display protocol to be utilized by the web server for facilitating communication with the remote machine see e.g. C of 

means for receiving a remote desktop drawing command from the remote machine in response to the input command see e.g. C of 

means for translating the remote desktop drawing command into a drawing update compatible with the hypertext markup language see e.g. C of and

means for facilitating providing the drawing update from the web server to the web browser see e.g. C of 

wherein the web server is an intermediary between the remote machine and the client device and wherein the web server comprises a windows web server and is physically separate from the remote machine.

23. The apparatus of clause 22 wherein the web browser comprises a windows web browser and means for translating the remote desktop drawing command comprises 

means for executing the windows graphics drawing command to update a portion of a memory bitmap wherein the memory bitmap represents an image of a remote desktop of the remote machine 

means for generating coordinates for the updated portion of the memory bitmap based on the windows graphics drawing command 

means for forming an image file including a windows image file based on the updated portion of the memory bitmap wherein the image file is compatible with HTML5 and

means for obtaining drawing coordinates for the image file based on the coordinates for the memory bitmap wherein the drawing coordinates are compatible with HTML5 

wherein the web browser temporarily comprises client script code during the remote desktop session while the remote desktop session persists 

wherein the apparatus comprises means for receiving drawing requests from the client script code of the web browser 

wherein the means for facilitating providing the drawing update comprises means for facilitating providing the drawing update from the web server to the client script code of the web browser in response to one of the drawing requests from the client script code of the web browser.

24. The apparatus of clause 22 wherein the means for translating the remote desktop drawing command comprises 

means for translating the remote desktop drawing command into a graphics drawing command compatible with the web server 

means for updating a portion of a bitmap based on the graphics drawing command wherein the updated portion of the bitmap represents a portion of an image of a remote desktop of the remote machine that has changed relative to a previous graphics drawing command 

means for obtaining drawing coordinates for the image file wherein the drawing coordinates are compatible with HTML5 

wherein the means for facilitating providing the drawing update comprises means for facilitating providing the drawing update from the web server to the web browser in response to one of the drawing requests from the web browser.

25. The apparatus of clause 22 wherein the web server comprises a remote desktop client wrapper configured to translate the user input request into the input command compatible with the remote desktop display protocol and to translate the remote desktop drawing command into the graphics drawing command compatible with a windows web browser.

26. The apparatus of clause 22 comprising means for receiving asynchronous HTTP requests from the web browser wherein the asynchronous HTTP requests comprise drawing requests and the web browser comprises a windows web browser.

27. The apparatus of clause 22 comprising means for receiving from the web browser an initial HTTP request comprising a uniform resource locator URL of the remote machine.

28. The apparatus of clause 27 comprising means for facilitating providing a script client code to the web browser in response to the initial HTTP request for the URL of the remote machine wherein the script client code is compatible with HTML5.

29. The apparatus of clause 22 wherein the remote desktop drawing command is compatible with the remote desktop display protocol wherein the remote desktop display protocol is a push protocol wherein the means for facilitating providing the drawing update comprises means for facilitating providing the drawing update using HTTP that is a pull protocol and wherein the drawing update is compatible with a windows web browser.

30. The apparatus of clause 22 wherein dynamic drawing comprises drawing in real time a portion of the 2D canvas rather than drawing the entire 2D canvas in response to one or more drawing requests of a script client of the web browser.

31. The apparatus of clause 22 wherein the 2D canvas is updatable by a portion at a time according to a set of coordinates.

Illustration of Method Apparatus Machine Readable Storage Medium for a remote desktop session utilizing HTTP header described as Clauses .

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 1 2 3 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause. Clause 1 below is presented for example with reference to . The other clauses can be presented in a similar manner.

1. A method see e.g. A of of facilitating a remote desktop session between a web browser see e.g. of of a client device see e.g. of and a remote machine see e.g. of through a web server utilizing hypertext transfer protocol HTTP headers for remote desktop session drawing the method comprising 

receiving at the web server drawing requests from the web browser of the client device see e.g. A of 

receiving at the web server a remote desktop drawing command from the remote machine using a remote desktop display protocol wherein the remote desktop drawing command is based on an image of a remote desktop of the remote machine see e.g. A of 

translating at the web server the remote desktop drawing command into a display image and drawing coordinates for the display image see e.g. A of 

in response to at least one of the drawing requests facilitating providing the display image and the drawing coordinates together to the web browser in a single HTTP response for drawing the display image of the remote desktop at the web browser wherein the single HTTP response comprises the HTTP response header see e.g. A of 

wherein i the remote desktop display protocol is a push protocol and ii HTTP is a pull protocol and iii the web browser comprises a windows web browser.

2. The method of clause 1 wherein the web server comprises a windows web server and wherein the translating comprises 

translating the remote desktop drawing command into a windows graphics drawing command wherein the web server comprises one or more web applications including one or more HTTP handlers 

updating a portion of a memory bitmap corresponding to the remote desktop in response to the windows graphics drawing command 

generating coordinates for the updated portion of the memory bitmap from the windows graphics drawing command 

obtaining the drawing coordinates for the display image based on the coordinates for the memory bitmap 

wherein the display image and the drawing coordinates are compatible with hypertext markup language HTML 

wherein the updated portion of the memory bitmap represents a portion of an image of the remote desktop of the remote machine 

wherein the display image and the drawing coordinates represent the portion of the image of the remote desktop of the remote machine.

3. The method of clause 1 wherein the web server is an intermediary between the remote machine and the client device and wherein the web server is physically separate from the remote machine.

4. The method of clause 1 wherein the remote desktop drawing command comprises coordinates of a region of the remote desktop that has changed relative to a previous remote desktop drawing command wherein the coordinates specify a redrawing region and wherein the display image and the drawing coordinates are compatible with windows graphic protocol and HTML5.

5. The method of clause 1 wherein the display image comprises at least one of a scaled image of the remote desktop or a display image comprising an offset image of the remote desktop.

6. A method of facilitating a remote desktop session between a web browser of a client device and a remote machine through a web server utilizing asynchronous handling of requests to reduce traffic to the client device the method comprising 

facilitating receiving at the web server a plurality of drawing requests from the web browser of the client device using HTTP wherein HTTP is a pull protocol 

translating at the web server the remote desktop drawing command into a web browser drawing update wherein the remote desktop drawing command is compatible with a push protocol 

wherein the web browser drawing update is compatible with HTTP and facilitating providing the web browser drawing update from the web server to the web browser of the client device utilizing HTTP as a response to at least one of the plurality of drawing requests from the web browser 

if there is no pending drawing command then storing the plurality of drawing requests in a drawing requests queue as asynchronous requests and

if there is a pending drawing command then providing at least one of the plurality of drawing requests to an HTTP handler module in the web server to allow the HTTP handler module to serve the pending drawing command in response to the at least one of the plurality of drawing requests.

8. The method of clause 6 wherein the remote desktop drawing command represents a portion of an image of a remote desktop of the remote machine 

placing at the HTTP handler module the drawing coordinates into an HTTP header of a single HTTP transmission response to the web browser 

including at the HTTP handler module the image file into the single HTTP transmission response to the web browser to facilitate providing the image file and the drawing coordinates together to the web browser in the single HTTP transmission response and

when a drawing commands queue has new coordinates sending a notification to the drawing requests queue to allow at least one of the plurality of drawing requests in the drawing requests queue to be forwarded to the HTTP handler module.

facilitating providing a client script code to the web browser in response to the request to connect to the remote machine 

wherein the receiving the plurality of drawing requests comprises receiving the plurality of drawing requests from the client script code 

wherein the facilitating providing the web browser drawing update comprises facilitating providing the web browser drawing update to the client script code and

facilitating deleting the client script code from the web browser when the remote desktop session is terminated.

receiving at the web server a user input request from the web browser for accessing or controlling a remote desktop of the remote machine 

translating at the web server the user input request into an input command compatible with the push protocol 

wherein the receiving the remote desktop drawing command comprises receiving the remote desktop drawing command in response to the input command.

12. A machine readable storage medium see e.g. in B of comprising instructions stored therein the instructions executable by one or more processors to perform one or more operations the instructions comprising 

code for causing one or more processors to facilitate receiving drawing requests from a web browser of a client device see e.g. B of 

code for causing one or more processors to facilitate receiving a remote desktop drawing command from a module of a remote machine using a remote desktop display protocol wherein the remote desktop drawing command is based on an image of a remote desktop of the remote machine see e.g. B of 

code for causing one or more processors to translate the remote desktop drawing command into a display image and drawing coordinates for the display image see e.g. B of 

code for causing one or more processors to place the drawing coordinates into a hypertext transfer protocol HTTP response header see e.g. B of and

code for causing one or more processors to facilitate providing the display image and the drawing coordinates together to the web browser in a single HTTP response to at least one of the drawing requests for drawing the display image of the remote desktop at the web browser wherein the single HTTP response comprises the HTTP response header see e.g. B of 

13. The machine readable storage medium of clause 12 wherein the code for causing one or more processors to translate is to be executed at a web server wherein the web server comprises a windows web server and wherein the code for causing one or more processors to translate comprises 

code for causing one or more processors to translate the remote desktop drawing command into a windows graphics drawing command 

code for causing one or more processors to update a portion of a memory bitmap of the remote desktop in response to the windows graphics drawing command 

code for causing one or more processors to generate coordinates for the updated portion of the memory bitmap from the windows graphics drawing command 

code for causing one or more processors to generate the display image compatible with the web browser based on the updated portion of the memory bitmap and

code for causing one or more processors to obtain the drawing coordinates for the display image based on the coordinates for the updated portion of the memory bitmap 

wherein the display image and the drawing coordinates are compatible with hypertext markup language HTML 

wherein the updated portion of the memory bitmap represents a portion of an image of the remote desktop of the remote machine 

wherein the display image and the drawing coordinates represent the portion of the image of the remote desktop of the remote machine.

14. The machine readable storage medium of clause 12 wherein the remote desktop drawing command comprises coordinates of a region of the remote desktop that has changed relative to a previous remote desktop drawing command wherein the coordinates specify a redrawing region and wherein the display image and the drawing coordinates are compatible with windows graphic protocol and HTML5.

15. The machine readable storage medium of clause 12 wherein the display image comprises at least one of a scaled image of the remote desktop or a display image comprising an offset image of the remote desktop.

16. A machine readable storage medium comprising instructions stored therein the instructions executable by one or more processors to perform one or more operations the instructions comprising 

code for causing one or more processors to facilitate receiving a plurality of drawing requests from a web browser of a client device using a hypertext transfer protocol HTTP wherein HTTP is a pull protocol 

code for causing one or more processors to handle the plurality of drawing requests as asynchronous requests 

code for causing one or more processors to facilitate receiving a remote desktop drawing command from a module of a remote machine 

code for causing one or more processors to translate the remote desktop drawing command into a web browser drawing update wherein the remote desktop drawing command is compatible with a push protocol wherein the web browser drawing update is compatible with HTTP and

code for causing one or more processors to facilitate providing the web browser drawing update to the web browser of the client device utilizing HTTP as a response to at least one of the plurality of drawing requests from the web browser.

17. The machine readable storage medium of clause 16 wherein the code for causing one or more processors to handle comprises 

code for causing one or more processors to determine whether a drawing command is pending at a web server for the web browser 

if there is no pending drawing command then code for causing one or more processors to store the plurality of drawing requests in a drawing requests queue as asynchronous requests and

if there is a pending drawing command then code for causing one or more processors to facilitate providing at least one of the plurality of drawing requests to an HTTP handler module in the web server to allow the HTTP handler module to serve the pending drawing command in response to the at least one of the plurality of drawing requests.

18. The machine readable storage medium of clause 16 wherein the remote desktop drawing command represents a portion of an image of a remote desktop of the remote machine 

19. The machine readable storage medium of clause 17 wherein the code for causing one or more processors to facilitate providing comprises 

code for causing one or more processors to place at the HTTP handler module the drawing coordinates into an HTTP header of a single HTTP transmission response to the web browser 

code for causing one or more processors to include at the HTTP handler module the image file into the single HTTP transmission response to the web browser to facilitate providing the image file and the drawing coordinates together to the web browser in the single HTTP transmission response and

code for causing one or more processors to when a drawing commands queue has new coordinates send a notification to the drawing requests queue to allow at least one of the plurality of drawing requests in the drawing requests queue to be forwarded to the HTTP handler module.

code for causing one or more processors to facilitate receiving a request from the web browser to connect to the remote machine 

code for causing one or more processors to facilitate providing a client script code to the web browser in response to the request to connect to the remote machine 

wherein the code for causing one or more processors to facilitate receiving the plurality of drawing requests comprises code for causing one or more processors to facilitate receiving the plurality of drawing requests from the client script code 

wherein the code for causing one or more processors to facilitate providing the web browser drawing update comprises code for causing one or more processors to facilitate providing the web browser drawing update to the client script code and

code for causing one or more processors to facilitate deleting the client script code from the web browser when the remote desktop session is terminated.

code for causing one or more processors to facilitate receiving at a web server a user input request from the web browser for accessing or controlling a remote desktop of the remote machine code for causing one or more processors to translate at the web server the user input request into an input command compatible with the push protocol 

code for causing one or more processors to facilitate providing the input command to the remote machine utilizing the push protocol 

wherein the code for causing one or more processors to facilitate receiving the remote desktop drawing command comprises code for causing one or more processors to facilitate receiving the remote desktop drawing command in response to the input command.

22. A computing machine comprising the machine readable storage medium of clause 12 wherein the computing machine is a web server.

23. An apparatus see e.g. C of for facilitating a remote desktop session between a web browser of a client device and a remote machine through a web server utilizing hypertext transfer protocol HTTP headers of HTTP for remote desktop session drawing the apparatus comprising 

means for receiving a remote desktop drawing command from the remote machine using a remote desktop display protocol wherein the remote desktop drawing command is based on an image of a remote desktop of the remote machine see e.g. C of 

means for translating the remote desktop drawing command into a display image and drawing coordinates for the display image see e.g. C of 

means for in response to at least one of the drawing requests facilitating providing the display image and the drawing coordinates together to the web browser in a single HTTP response for drawing the display image of the remote desktop at the web browser wherein the single HTTP response comprises the HTTP response header see e.g. C of 

wherein i the remote desktop display protocol is a push protocol and ii HTTP is a pull protocol and iii the web browser comprises a windows web browser.

means for translating the remote desktop drawing command into a windows graphics drawing command wherein the web server comprises one or more web applications including one or more HTTP handlers 

means for updating a portion of a memory bitmap of the remote desktop in response to the windows graphics drawing command 

means for generating coordinates for the updated portion of the memory bitmap from the windows graphics drawing command 

means for generating the display image compatible with the web browser based on the updated portion of the memory bitmap and

means for obtaining the drawing coordinates for the display image based on the coordinates for the updated portion of the memory bitmap 

wherein the updated portion of the memory bitmap represents a portion of an image of the remote desktop of the remote machine 

wherein the display image and the drawing coordinates represent the portion of the image of the remote desktop of the remote machine.

25. The apparatus of clause 23 wherein the remote desktop drawing command comprises coordinates of a region of the remote desktop that has changed relative to a previous remote desktop drawing command wherein the coordinates specify a redrawing region and wherein the display image and the drawing coordinates are compatible with windows graphic protocol and HTML5.

26. The apparatus of clause 23 wherein the display image comprises at least one of a scaled image of the remote desktop or a display image comprising an offset image of the remote desktop.

27. The apparatus of clause 23 wherein the web server is an intermediary between the remote machine and the client device and wherein the web server is physically separate from the remote machine.

28. An apparatus for facilitating a remote desktop session between a web browser of a client device and a remote machine through a web server utilizing asynchronous handling of requests to reduce traffic to the client device the apparatus comprising 

means for receiving a plurality of drawing requests from the web browser of the client device using HTTP wherein HTTP is a pull protocol 

means for translating the remote desktop drawing command into a web browser drawing update wherein the remote desktop drawing command is compatible with a push protocol wherein the web browser drawing update is compatible with HTTP and

means for facilitating providing the web browser drawing update from the web server to the web browser of the client device utilizing HTTP as a response to at least one of the plurality of drawing requests from the web browser 

means for storing the plurality of drawing requests in a drawing requests queue as asynchronous requests if there is no pending drawing command and

means for providing at least one of the plurality of drawing requests to an HTTP handler module in the web server to allow the HTTP handler module to serve the pending drawing command in response to the at least one of the plurality of drawing requests if there is a pending drawing command.

30. The apparatus of clause 28 wherein the remote desktop drawing command represents a portion of an image of a remote desktop of the remote machine 

means for placing the drawing coordinates into an HTTP header of a single HTTP transmission response to the web browser 

means for including the image file into the single HTTP transmission response to the web browser to facilitate providing the image file and the drawing coordinates together to the web browser in the single HTTP transmission response and

means for sending a notification to the drawing requests queue to allow at least one of the plurality of drawing requests in the drawing requests queue to be forwarded to the HTTP handler module when a drawing commands queue has new coordinates.

means for facilitating providing a client script code to the web browser in response to the request to connect to the remote machine 

wherein the means for receiving the plurality of drawing requests comprises means for receiving the plurality of drawing requests from the client script code 

wherein the means for facilitating providing the web browser drawing update comprises means for facilitating providing the web browser drawing update to the client script code and

means for facilitating deleting the client script code from the web browser when the remote desktop session is terminated.

means for receiving a user input request from the web browser for accessing or controlling a remote desktop of the remote machine 

means for translating the user input request into an input command compatible with the push protocol 

means for facilitating providing the input command to the remote machine utilizing the push protocol 

wherein the means for receiving the remote desktop drawing command comprises means for receiving the remote desktop drawing command in response to the input command.

Illustration of Method Apparatus Machine Readable Storage Medium for facilitating a remote desktop session for a web browser and a remote desktop server described as Clauses .

The subject technology is illustrated for example according to various aspects described below. Various examples of aspects of the subject technology are described as numbered clauses 1 2 3 etc. for convenience. These are provided as examples and do not limit the subject technology. It is noted that any of the dependent clauses may be combined in any combination and placed into a respective independent clause. Clause 1 below is presented for example with reference to . The other clauses can be presented in a similar manner.

1. A method see e.g. method A of for facilitating a remote desktop session between a web browser see e.g. of of a client device see e.g. of and a remote desktop server at a remote machine see e.g. of through a web server see e.g. of utilizing a wrapper see e.g. of of the web server see e.g. of the method comprising 

receiving at the wrapper an input request from the web browser utilizing a request response protocol wherein the request response protocol is a pull protocol see e.g. A of 

translating at the wrapper the input request into an input command compatible with a remote desktop display protocol to be utilized by a remote desktop client at the web server for facilitating communication with the remote desktop server at the remote machine wherein the remote desktop display protocol is a push protocol see e.g. A of 

providing the input command to the remote desktop client at the web server to facilitate providing the input command to the remote desktop server utilizing the remote desktop display protocol see e.g. A of 

receiving at the wrapper a remote desktop drawing command from the remote desktop server in response to the input command wherein the remote desktop drawing command is based on an image of a remote desktop of the remote machine see e.g. A of and

translating at the wrapper the remote desktop drawing command into a graphics drawing command compatible with the web server to allow the web server to facilitate providing a web browser drawing update to the web browser wherein the web browser comprises a windows web browser and the web browser drawing update is compatible with the windows web browser see e.g. A of .

2. The method of clause 1 wherein the request response protocol comprises hypertext transfer protocol HTTP wherein the graphics drawing command is a windows graphics drawing command wherein the web server is a windows web server wherein the web browser is hypertext markup language 5 HTML5 compatible.

3. The method of clause 1 wherein the receiving the input request comprises receiving the input request from the web browser via an HTTP handler of a web application including an ASP.NET model view controller MVC at the web server 

wherein the receiving the remote desktop drawing command comprises receiving the remote desktop drawing command via the remote desktop client using the remote desktop display protocol 

wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from the remote desktop server and

wherein the translating the remote desktop drawing command comprises one or more of calculating new drawing command parameters based on the remote desktop drawing command parameters adjusting the remote desktop drawing command parameters and making adjustments to the bitmap data.

executing the graphics drawing command to generate and draw an image into a drawing commands module at the web server that is accessible by an HTTP handler at the web server for communicating with the web browser 

after generating the coordinates transmitting a notification to the HTTP handler that a drawing command is ready to be served to the web browser 

wherein each of the image and the graphics drawing command represents a portion of an image of the remote desktop 

wherein the at least a portion of the off screen bitmap is associated with the coordinates wherein the off screen bitmap represents an image of the remote desktop.

facilitating establishing controlling or terminating the remote desktop session between the remote desktop client and the remote desktop server in response to the connection request wherein the facilitating of the establishing controlling or terminating comprises 

6. A method for facilitating accessing and controlling a remote desktop of a remote machine in real time from a web browser of a client device utilizing a web server the method comprising 

translating at the web server the connection request into a session control command compatible with a remote desktop display protocol 

providing the session control command to a remote desktop client of the web server for providing the session control command to a remote desktop server of the remote machine and for establishing controlling or terminating a remote desktop session with the remote desktop server 

translating at the web server the user input request into a remote desktop input command compatible with the remote desktop display protocol 

providing the remote desktop input command to the remote desktop client for providing the remote desktop input command to the remote desktop server 

receiving at the web server a remote desktop drawing command from the remote desktop server via the remote desktop client in response to the remote desktop input command wherein the remote desktop drawing command is compatible with the remote desktop display protocol and wherein the remote desktop drawing command represents a portion of an image of the remote desktop 

translating at the web server the remote desktop drawing command into a graphics drawing command compatible with the web server 

updating at the web server a portion of an image and coordinates based on the graphics drawing command 

facilitating providing a web browser drawing update to the web browser in response to a drawing request from the web browser wherein the web browser drawing update comprises the image file and the drawing coordinates and wherein the web browser drawing update is compatible with the web browser 

wherein the remote desktop drawing command represents a portion of the remote desktop and the image represents the remote desktop 

wherein i the web server comprises a windows web server ii the web browser is s windows web browser iii the remote desktop display protocol is a push protocol and iv HTTP is a pull protocol.

7. The method of clause 6 wherein the user input request comprises at least one of a mouse event a keyboard event and a touch event wherein the updating a portion of an image and coordinates comprises storing the portion of the image and the coordinates into a drawing commands queue wherein the graphics drawing command is a windows graphics drawing command and wherein the web browser is HTML5 compatible.

8. The method of clause 6 wherein the updating a portion of an image and coordinates comprises storing the portion of the image and the coordinates into a drawing commands buffer 

wherein the method comprises an asynchronous request handling comprising receiving the drawing request from the web browser utilizing HTTP forwarding the drawing request to an HTTP handler module if coordinates for an image are pending in the drawing commands buffer placing the drawing request into a drawing requests queue if coordinates for an image are not pending in the drawing commands buffer and

wherein the method comprises sending a notification to the drawing requests queue if the drawing commands buffer receives a new drawing command comprising an image and coordinates for an image.

forwarding the drawing request to an HTTP handler in response to a notification from a drawing commands buffer that a drawing command is pending for the web browser 

placing the drawing coordinates into a section of an HTTP header wherein the image file comprises a windows image file and the facilitating providing the web browser drawing update comprises facilitating providing the windows image file and the drawing coordinates together to the web browser in a single HTTP transmission response for drawing a display image at the web browser wherein the display image represents the updated portion of the image representing the remote desktop 

facilitating providing script client code compatible with the web browser to the web browser if the connection request from the web browser comprises a request to connect to the remote machine.

10. A machine readable storage medium see e.g. in B of comprising instructions stored therein the instructions executable by one or more processors see e.g. to perform a one or more operations the instructions comprising 

code for causing one or more processors to facilitate receiving an input request from a web browser utilizing a request response protocol wherein the request response protocol is a pull protocol see e.g. B of 

code for causing one or more processors to translate the input request into an input command compatible with a remote desktop display protocol to be utilized by a remote desktop client for facilitating communication with a remote desktop server wherein the remote desktop display protocol is a push protocol see e.g. B of 

code for causing one or more processors to facilitate providing the input command to the remote desktop client at the web server to facilitate providing the input command to the remote desktop server utilizing the remote desktop display protocol see e.g. B of 

code for causing one or more processors to facilitate receiving a remote desktop drawing command from the remote desktop server in response to the input command wherein the remote desktop drawing command is based on an image of a remote desktop of the remote machine see e.g. B of and

code for causing one or more processors to translate the remote desktop drawing command into a graphics drawing command to facilitate providing a web browser drawing update to the web browser wherein the web browser comprises a windows web browser and the web browser drawing update is compatible with the web browser see e.g. B of .

11. The machine readable storage medium of clause 10 wherein the request response protocol comprises hypertext transfer protocol HTTP wherein the graphics drawing command is a windows graphics drawing command wherein a web server is for the remote desktop client a windows web server wherein the web browser is HTML5 compatible.

12. The machine readable storage medium of clause 10 wherein the code for causing one or more processors to facilitate receiving the input request comprises code for causing one or more processors to facilitate receiving the input request from the web browser via an HTTP handler of a web application at a web server 

wherein the code for causing one or more processors to facilitate receiving the remote desktop drawing command comprises code for causing one or more processors to facilitate receiving the remote desktop drawing command via the remote desktop client using the remote desktop display protocol 

wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from the remote desktop server and

wherein the code for causing one or more processors to translate the remote desktop drawing command comprises one or more of code for causing one or more processors to calculate new drawing command parameters based on the remote desktop drawing command parameters code for causing one or more processors to adjust the remote desktop drawing command parameters and code for causing one or more processors to make adjustments to the bitmap data.

code for causing one or more processors to execute the graphics drawing command to generate and draw an image into a drawing commands module at the web server that is accessible by HTTP handler at the web server for communicating with the web browser 

code for causing one or more processors to generate coordinates for the image based on the graphics drawing command 

after generating the coordinates code for causing one or more processors to transmit a notification to the HTTP handler that a drawing command is ready to be served to the web browser 

wherein each of the image and the graphics drawing command represents a portion of an image of the remote desktop 

code for causing one or more processors to update at least a portion of an off screen bitmap based on the graphics drawing command wherein the at least a portion of the off screen bitmap is associated with the coordinates wherein the off screen bitmap represents an image of the remote desktop.

code for causing one or more processors to facilitate receiving via an HTTP handler of a web server a connection request from the web browser and

code for causing one or more processors to facilitate establishing controlling or terminating the remote desktop session between the remote desktop client and the remote desktop server in response to the connection request wherein the code for causing one or more processors to facilitate of the establishing controlling or terminating comprises 

15. A computing machine comprising the machine readable storage medium of clause 10 wherein the computing machine is a web server.

16. A machine readable storage medium comprising instructions stored therein the instructions executable by one or more processors to facilitate accessing and controlling a remote desktop of a remote machine in real time from a web browser of a client device via a hypertext transfer protocol HTTP handler and a remote desktop client wrapper for a web server the machine readable storage medium comprising 

wherein the HTTP handler is configured to facilitate receiving a connection request and a user input request from the web browser utilizing HTTP to facilitate providing the connection request and the user input request to the remote desktop client wrapper and to facilitate providing a web browser drawing update to the web browser in response to a drawing request from the web browser wherein the web browser drawing update is compatible with the web browser 

wherein the remote desktop client wrapper is configured to facilitate receiving the connection request and the user input request to translate the connection request into a session control command compatible with a remote desktop display protocol and to translate the user input request into a remote desktop input command compatible with the remote desktop display protocol 

wherein the remote desktop client wrapper is configured to facilitate providing the session control command to a remote desktop client for providing the session control command to a remote desktop server of the remote machine and for establishing controlling or terminating a remote desktop session with the remote desktop server 

wherein the remote desktop client wrapper is configured to facilitate providing the remote desktop input command to the remote desktop client for providing the remote desktop input command to the remote desktop server 

wherein the remote desktop client wrapper is configured to facilitate receiving a remote desktop drawing command from the remote desktop server via the remote desktop client in response to the remote desktop input command wherein the remote desktop drawing command is compatible with the remote desktop display protocol 

wherein the remote desktop client wrapper is configured to translate the remote desktop drawing command into a graphics drawing command compatible with the web server and to update a portion of an image representing the remote desktop and coordinates based on the graphics drawing command and

wherein the HTTP handler is configured to generate an image file based on the updated portion of the image and to obtain drawing coordinates based on the coordinates in response to the drawing request wherein the web browser drawing update comprises the image file and the drawing coordinates 

wherein the remote desktop drawing command represents a portion of the remote desktop and the image represents the remote desktop

wherein i the web server comprises a windows web server ii the web browser is s windows web browser iii the remote desktop display protocol is a push protocol and iv HTTP is a pull protocol.

17. The machine readable storage medium of clause 16 wherein the user input request comprises at least one of a mouse event a keyboard event and a touch event wherein the remote desktop client wrapper is configured to update a portion of an image and coordinates by storing the portion of the image and the coordinates into a drawing commands buffer wherein the graphics drawing command is a windows graphics drawing command and wherein the web browser is HTML5 compatible.

18. The machine readable storage medium of clause 16 comprising an asynchronous handler configured to handle requests asynchronously by facilitate receiving the drawing request from the web browser utilizing HTTP forwarding the drawing request to an HTTP handler module if coordinates for an image are pending in the drawing commands buffer placing the drawing request into a drawing requests queue if coordinates for an image are not pending in the drawing commands buffer and

wherein the HTTP handler is configured to send a notification to the drawing requests queue if the drawing commands buffer receives a new drawing command comprising an image and coordinates for an image.

19. The machine readable storage medium of clause 16 wherein the web server is configured to forward the drawing request to the HTTP handler in response to a notification from a drawing commands buffer that a drawing command is pending for the web browser 

wherein the HTTP handler is configured to place the drawing coordinates into a section of an HTTP header wherein the image file comprises a windows image file and to facilitate providing the windows image file and the drawing coordinates together to the web browser in a single HTTP transmission response for drawing a display image at the web browser wherein the display image represents the updated portion of the image representing the remote desktop and

wherein the HTTP handler is configured to facilitate providing script client code compatible with the web browser to the web browser if the connection request from the web browser comprises a request to connect to the remote machine.

20. An apparatus see e.g. C of for facilitating a remote desktop session between a web browser of a client device and a remote desktop server of a remote machine through a web server utilizing a wrapper at the web server the apparatus comprising 

means for receiving an input request from the web browser utilizing a request response protocol wherein the request response protocol is a pull protocol see e.g. C of 

means for translating the input request into an input command compatible with a remote desktop display protocol to be utilized by a remote desktop client at the web server for facilitating communication with the remote desktop server at the remote machine wherein the remote desktop display protocol is a push protocol see e.g. C of 

means for providing the input command to a remote desktop client at the web server to facilitate providing the input command to the remote desktop server utilizing the remote desktop display protocol see e.g. C of 

means for receiving a remote desktop drawing command from the remote desktop server in response to the input command wherein the remote desktop drawing command is based on an image of a remote desktop of the remote machine see e.g. C of and means for translating the remote desktop drawing command into a graphics drawing command compatible with the web server to allow the web server to facilitate providing a web browser drawing update to the web browser wherein the web browser comprises a windows web browser and the web browser drawing update is compatible with the windows web browser see e.g. C of .

21. The apparatus of clause 20 wherein the request response protocol comprises hypertext transfer protocol HTTP wherein the graphics drawing command is a windows graphics drawing command wherein the web server is a windows web server wherein the web browser is HTML5 compatible.

22. The apparatus of clause 20 wherein the means for receiving the input request comprises means for receiving the input request from the web browser via an HTTP handler of a web application at the web server 

wherein the means for receiving the remote desktop drawing command comprises means for receiving the remote desktop drawing command via the remote desktop client using the remote desktop display protocol 

wherein the remote desktop drawing command comprises remote desktop drawing command parameters and bitmap data received from the remote desktop server and

wherein the translating the remote desktop drawing command comprises one or more of calculating new drawing command parameters based on the remote desktop drawing command parameters adjusting the remote desktop drawing command parameters and making adjustments to the bitmap data.

means for executing the graphics drawing command to generate and draw an image into a drawing commands module at the web server that is accessible by an HTTP handler at the web server for communicating with the web browser 

means for transmitting a notification to the HTTP handler that a drawing command is ready to be served to the web browser after generating the coordinates 

wherein each of the image and the graphics drawing command represents a portion of an image of the remote desktop 

means for updating at least a portion of an off screen bitmap based on the graphics drawing command wherein the at least a portion of the off screen bitmap is associated with the coordinates wherein the off screen bitmap represents an image of the remote desktop.

means for receiving via an HTTP handler of the web server a connection request from the web browser and

means for facilitating establishing controlling or terminating the remote desktop session between the remote desktop client and the remote desktop server in response to the connection request wherein the means for facilitating of the establishing controlling or terminating comprises 

25. An apparatus for facilitating accessing and controlling a remote desktop of a remote machine in real time from a web browser of a client device utilizing a web server the apparatus comprising 

means for translating the connection request into a session control command compatible with a remote desktop display protocol 

means for providing the session control command to a remote desktop client of the web server for providing the session control command to a remote desktop server of the remote machine and for establishing controlling or terminating a remote desktop session with the remote desktop server 

means for translating the user input request into a remote desktop input command compatible with the remote desktop display protocol 

means for providing the remote desktop input command to the remote desktop client for providing the remote desktop input command to the remote desktop server 

means for receiving a remote desktop drawing command from the remote desktop server via the remote desktop client in response to the remote desktop input command wherein the remote desktop drawing command is compatible with the remote desktop display protocol and wherein the remote desktop drawing command represents a portion of an image of the remote desktop 

means for translating the remote desktop drawing command into a graphics drawing command compatible with the web server 

means for facilitating providing a web browser drawing update to the web browser in response to a drawing request from the web browser wherein the web browser drawing update comprises the image file and the drawing coordinates and wherein the web browser drawing update is compatible with the web browser 

wherein the remote desktop drawing command represents a portion of the remote desktop and the image represents the remote desktop 

wherein i the web server comprises a windows web server ii the web browser is s windows web browser iii the remote desktop display protocol is a push protocol and iv HTTP is a pull protocol.

26. The apparatus of clause 25 wherein the user input request comprises at least one of a mouse event a keyboard event and a touch event wherein the means for updating a portion of an image and coordinates comprises means for storing the portion of the image and the coordinates into a drawing commands queue wherein the graphics drawing command is a windows graphics drawing command and wherein the web browser is HTML5 compatible.

27. The apparatus of clause 25 wherein the means for updating a portion of an image and coordinates comprises means for storing the portion of the image and the coordinates into a drawing commands buffer 

wherein the apparatus comprises means for asynchronous request handling comprising means for receiving the drawing request from the web browser utilizing HTTP means for forwarding the drawing request to an HTTP handler module if coordinates for an image are pending in the drawing commands buffer means for placing the drawing request into a drawing requests queue if coordinates for an image are not pending in the drawing commands buffer and

wherein the apparatus comprises means for sending a notification to the drawing requests queue if the drawing commands buffer receives a new drawing command comprising an image and coordinates for an image.

means for forwarding the drawing request to an HTTP handler in response to a notification from a drawing commands buffer that a drawing command is pending for the web browser 

means for placing the drawing coordinates into a section of an HTTP header wherein the image file comprises a windows image file and the means for facilitating providing the web browser drawing update comprises means for facilitating providing the windows image file and the drawing coordinates together to the web browser in a single HTTP transmission response for drawing a display image at the web browser wherein the display image represents the updated portion of the image representing the remote desktop 

means for facilitating providing script client code compatible with the web browser to the web browser if the connection request from the web browser comprises a request to connect to the remote machine.

31. An Apparatus comprising modules configured to perform the method of any one of the forgoing clauses.

34. A machine readable storage medium comprising code for causing the web server to perform the method of any one of the forgoing clauses.

35. The machine readable storage medium of clause 34 wherein the web server comprises the machine readable storage medium.

39. An apparatus comprising components operable to perform the method of any one of the forgoing clauses.

Without limitation and without limiting the scope of the foregoing clauses or this disclosure in one aspect illustrations of the foregoing clauses may include with the corresponding description in the disclosure.

Without limitation and without limiting the scope of the foregoing clauses or this disclosure in one aspect the foregoing clauses are re stated herein and are re drawn herein with the phrase transcoding server replaced with the phrase web server e.g. in with the phrase long polling request replaced with the phrase asynchronous request and with the phrase adapter replaced with the phrase Wrapper. 

Without limitation and without limiting the scope of the foregoing clauses or this disclosure referring to the foregoing clauses and the previous paragraph in one aspect an example of a client device may be client device of an example of a remote machine may be an example of a web browser may be an example of a web application container may be . an example of a HTTP handler may be an example of a transcoder server may be an example of a HTTP handler may be and an example of a remote desktop client adaptor may be . an example of a HTTP handler may be . Referring to the foregoing clauses and the previous paragraph in one aspect an example of a transcoding server may be web server of an example of a HTTP handler may be and an example of a long polling handler may be .

In one aspect any of the clauses herein may depend from any one of the independent clauses or any one of the dependent clauses. In one aspect any of the clauses e.g. dependent or independent clauses may be combined with any other clauses e.g. dependent or independent clauses . In one aspect a claim may include some or all of the words e.g. steps operations means or components recited in a clause a sentence a phrase or a paragraph. In one aspect a claim may include some or all of the words recited in one or more clauses sentences phrases or paragraphs. In one aspect some of the words in each of the clauses sentences phrases or paragraphs may be removed. In one aspect additional words or elements may be added to a clause a sentence a phrase or a paragraph. In one aspect the subject technology may be implemented without utilizing some of the components elements functions or operations described herein. In one aspect the subject technology may be implemented utilizing additional components elements functions or operations.

Those of skill in the art would appreciate that the various illustrative blocks modules elements components methods and algorithms described herein may be implemented as electronic hardware computer software or combinations of both.

For example a module e.g. a web application container a long polling handler module a long polling handler a drawing requests queue an HTTP handler an image conversion module a drawing commands queue a remote desktop client adapter a remote desktop client a remote desktop server an input listener an image.onload handler an image.onerror image.on abort handler a drawing command handler a remote desktop client manager a user input handler an HTML canvas a script client an HTTP handler a remote desktop client wrapper an HTTP handler response ready an HTTP request switch a drawing coordinates queue a memory bitmap a drawing commands module a remote desktop session module a user input module or other modules or functions may be implemented as electronic hardware computer software or combinations of both. Modules may be considered in some aspects as means for accomplishing one or more functions or steps. In one aspect a module s may be an apparatus since a module s may include instructions encoded or stored on a machine readable medium on another device or on a portion thereof where an instruction s may be software an application s a subroutine s or a portion thereof where the instructions s may be for performing the function s or operation s . In one aspect a module s may be software e.g. an application a subroutine stored in a machine readable medium and executable by a processing system or a processor. In another aspect a module s may be hardware e.g. machine readable medium encoded with instructions a pre programmed general purpose computer with for example ASIC or FPGA or a special purpose electronic or optical device . In an aspect a module may be implemented as one or more circuits configured to perform the function s or operation s . A circuit may include one or more circuits and or logic. A circuit may be analog and or digital. A circuit may be electrical and or optical. A circuit may include transistors. In an example one or more modules may be implemented as a processing system e.g. a digital signal processor DSP an application specific integrated circuit ASIC a field programmable gate array FPGA etc. as a portion s of any of the foregoing or as a combination s of any of the foregoing. Those skilled in the art will recognize how to implement the instructions circuits and processing systems.

To illustrate this interchangeability of hardware and software various illustrative blocks modules elements components methods and algorithms have been described above generally in terms of their functionality. Whether such functionality is implemented as hardware or software depends upon the particular application and design constraints imposed on the overall system. Skilled artisans may implement the described functionality in varying ways for each particular application.

In one aspect of the disclosure when actions or functions e.g. receiving determining providing generating converting displaying notifying accepting selecting controlling transmitting reporting sending establishing building or any other action or function are described as being performed by an item e.g. one or more of blocks modules elements components or processors it is understood that such actions or functions may be performed for example by the item directly or indirectly. In an example when an item is described as performing an action the item may be understood to perform the action indirectly for example by facilitating such an action e.g. assisting allowing enabling causing or providing for such action to occur or performing a portion of such an action . For example determining can refer to facilitating determination attaching can refer to facilitating attaching and receiving can refer to facilitating receiving. For instance facilitating receiving an item may for example include providing a code to allow an entity to receive the item. For instance when a session is described as being established by a module it is understood that the module may establish the session indirectly by facilitating an establishment of the session. As yet another example when an image is described as being displayed or rendered by a module it is understood that the image may be displayed or rendered by the module either directly or indirectly. In one aspect performing an action may refer to performing a portion of the action e.g. performing a beginning part of the action performing an end part of the action or performing a middle portion of the action .

Various components and blocks may be arranged differently e.g. arranged in a different order or partitioned in a different way all without departing from the scope of the subject technology. In one aspect of the disclosure the modules or elements recited in the accompanying claims may be performed by one module or by a smaller number of modules and this arrangement is within the scope of the claims. In another aspect the modules or elements recited in the accompanying claims may be performed by a larger number of modules and this arrangement is within the scope of the claims. In yet another aspect a module or an element recited in the accompanying claims may be performed by multiple modules and this arrangement is within the scope of the claims.

It is understood that the specific order or hierarchy of steps in the processes disclosed is an illustration of exemplary approaches. Based upon design preferences it is understood that the specific order or hierarchy of steps in the processes may be rearranged. Some of the steps may be performed simultaneously. The accompanying method claims present elements of the various steps in a sample order and are not meant to be limited to the specific order or hierarchy presented.

The previous description is provided to enable any person skilled in the art to practice the various aspects described herein. The previous description provides various examples of the subject technology and the subject technology is not limited to these examples. Various modifications to these aspects will be readily apparent to those skilled in the art and the generic principles defined herein may be applied to other aspects. Thus the claims are not intended to be limited to the aspects shown herein but is to be accorded the full scope consistent with the language claims wherein reference to an element e.g. a command a call a handler a device a machine etc. in the singular is not intended to mean one and only one unless specifically so stated but rather one or more. Unless specifically stated otherwise the term some refers to one or more. Pronouns in the masculine e.g. his include the feminine and neuter gender e.g. her and its and vice versa. Headings and subheadings if any are used for convenience only and do not limit the invention.

A phrase such as an aspect does not imply that such aspect is essential to the subject technology or that such aspect applies to all configurations of the subject technology. A disclosure relating to an aspect may apply to all configurations or one or more configurations. An aspect may provide one or more examples of the disclosure. A phrase such as an aspect may refer to one or more aspects and vice versa. A phrase such as an embodiment does not imply that such embodiment is essential to the subject technology or that such embodiment applies to all configurations of the subject technology. A disclosure relating to an embodiment may apply to all embodiments or one or more embodiments. An embodiment may provide one or more examples of the disclosure. A phrase such an embodiment may refer to one or more embodiments and vice versa. A phrase such as a configuration does not imply that such configuration is essential to the subject technology or that such configuration applies to all configurations of the subject technology. A disclosure relating to a configuration may apply to all configurations or one or more configurations. A configuration may provide one or more examples of the disclosure. A phrase such a configuration may refer to one or more configurations and vice versa.

The word exemplary is used herein to mean serving as an example or illustration. Any aspect or design described herein as exemplary is not necessarily to be construed as preferred or advantageous over other aspects or designs.

In one aspect the term compatible may be used in a sense that a first element e.g. a drawing command an input call an input command a connection request a drawing request etc. is compatible with a second element e.g. a remote desktop display protocol a remote desktop client a remote desktop server a transcoding server a web browser a client device a remote machine HTML5 HTTP etc. so that the first element can be recognized or understood by the second element can be processed by the second element or can be utilized by or with the second element.

All structural and functional equivalents to the elements of the various aspects described throughout this disclosure that are known or later come to be known to those of ordinary skill in the art are expressly incorporated herein by reference and are intended to be encompassed by the claims. Moreover nothing disclosed herein is intended to be dedicated to the public regardless of whether such disclosure is explicitly recited in the claims. No claim element is to be construed under the provisions of 35 U.S.C. 112 sixth paragraph unless the element is expressly recited using the phrase means for or in the case of a method claim the element is recited using the phrase step for. Furthermore to the extent that the term include have or the like is used in the description or the claims such term is intended to be inclusive in a manner similar to the term comprise as comprise is interpreted when employed as a transitional word in a claim.

