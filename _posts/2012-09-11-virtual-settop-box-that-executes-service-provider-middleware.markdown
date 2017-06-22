---

title: Virtual set-top box that executes service provider middleware
abstract: A virtual set-top box (vSTB) for executing a middleware component, designed originally for use with the physical STB, including emulating hardware capabilities of the physical STB to process IPTV content received over a connection for presenting the IPTV content on a display of the electronic device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08683543&OS=08683543&RS=08683543
owner: DISH Digital L.L.C.
number: 08683543
owner_city: Englewood
owner_country: US
publication_date: 20120911
---
This application is a continuation of U.S. application Ser. No. 12 556 443 now U.S. Pat. No. 8 222 905 filed on Sep. 9 2009 which claims the benefit of U.S. Provisional Application No. 61 095 738 filed Sep. 10 2008 and which is hereby incorporated by reference. This application is related to co pending U.S. application Ser. No. 12 556 347 entitled Dynamic Video Source Selection filed herewith.

This invention relates to Internet Protocol Television IPTV technology and specifically to a system and method for providing an IPTV service to a user such that the user may view programming content on a device such as a computer the presentation and functionality associated with traditional programming paradigms being maintained.

In the traditional television paradigm programming content is sent as an analogue or digital signal to a viewer s television set via cable satellite or through the air. The signals are then received processed and displayed for the viewer to watch on the screen of the television set.

However with the exoteric spread of portable electronic devices such as laptop computers viewers no longer wish to be restricted to watching television via a conventional television set which is more or less confined to use in one physical location. Given the desire or need for portability and the ubiquitous presence of Internet based technologies within modern computing equipment the ability to receive IPTV services via computing equipment is becoming increasingly important from both a consumer s i.e. viewer s perspective and from the perspective of the service providers who seek to commercialize the opportunities.

Thus the monopoly of the traditional television paradigm is being eroded and challenged by the development of Internet Television Internet TV and Internet Protocol Television IPTV technologies.

Internet TV enables a user to select programs from a list and is typically delivered over an IP network in the form of streaming video via a website. The content is embedded into a web page and accompanying text is typically wrapped around the streaming video which is presented to the viewer within a separate window. In some ways this presentation style is similar to a newspaper page wherein surrounding text flows around not over the image albeit that the static image is replaced by a video component.

By contrast a typical IPTV system enables delivery of a digital television service to a viewer over a closed network infrastructure. The delivery is performed using Internet Protocol and typically includes a broadband connection. The IPTV system receives and displays the video stream which has been encoded as a series of Internet Protocol data packets. IPTV can be in the form of live TV but also as stored video sometimes known as video on demand VOD .

Traditionally the viewer must use a device known as a set top box STB in conjunction with his her television set in order to receive and view IPTV. The set top box acts as an interface between the television and the network decoding the incoming video streaming media converting it into standard television signals and providing two way communications over the IP network. It also performs functional processing such as setting up the connection and quality of service QoS with the service node channel change functionality and user display control. This functionality is achieved via the use of software known as middleware .

 Middleware is a key component within the IPTV solutions architecture. It is the application software layer that acts as an interface between the user interface and the hardware operating system OS of the STB. Middleware vendors adopt abstraction based strategies to isolate themselves from the underlying hardware.

However service providers can find it challenging to make the IPTV business model commercially viable due to the often relatively high cost of STBs. This is compounded by the linear nature of the cost functionality line of STBs the more features or functions the STB is required to posses the higher the cost of the device. This has prompted IPTV service providers to investigate the possibilities of delivering their services to mass market end user devices such as personal computers where the cost of the hardware has already been borne by the end user viewer. Thus if standard computing components can be used to mirror and mimic their televisual counterparts e.g. monitor CPU disk used to replace TV STB VCR respectively then functionality can be maintained whilst eliminating the cost and inconvenience of a required STB.

In order to receive IPTV services and view them on other devices such as a personal or laptop computer there is a need therefore for the computer itself to perform the functional processing discussed above in relation to the STBs used with televisions.

Thus there is a need for a system which provides the seamless delivery of IPTV services to an alternative device such as a computer. Ideally such a system would be arranged and configured such that it can be integrated with existing IPTV technologies. This integration work is required primarily in 3 areas 

Both approaches suffer from the problem that the STB vendor provided APIs both ECMAScript and C C are not standardized and therefore each middleware vendor must perform a porting exercise each time a new STB is to be added to their portfolio of supported end user devices.

Another problematic area facing would be computer based IPTV systems is that most known IPTV systems are designed to deliver IP encapsulated MPEG 2 4 content at 2 to 4 Mbps to users on multicast enabled networks. To date the general lack of multicast support within large portions of the available networks restricts the number of potential target clients. There are several commercial and technical factors in existence which remain barriers to the effective delivery of these services.

End users of television services are typically unconcerned with the underlying delivery mechanism employed to deliver the picture to their device e.g. DTT IP etc. . However they are concerned about the quality of the content which they wish to view and the ease of use with which they access that optimal quality content.

Therefore a preferred solution should be capable of presenting a high quality service and consistent navigational paradigm to the viewer whilst behind the scenes detecting selecting and presenting the best quality programming possible based upon the current position of the viewer s device within the network regardless of multicast support .

In other words the solution should incorporate a dynamic video source selection DVSS mechanism such that the user is provided with a single experience of optimal quality on any network.

Known solutions attempt to address some of these difficulties although they typically involve considerable expense from the service provider to effectively create a parallel distribution mechanism encoding encryption delivery middleware integration device integration etc. and typically provide a different viewing experience in terms of presentation style and format navigational interfaces etc. from that which the viewer would expect from a traditional television based service.

In addition many proposed solutions focus on how to deliver IPTV content to an end user rather than how to process and or display that content once it has been received at the client end or how to improve replace the technology employed at the client end.

For example EP1895777 A1 discloses a method of providing an IPTV service to a subscriber and a network element for executing said method. This is achieved by introducing an additional tier an intertwine tier into the traditional tiered IPTV architecture. This intertwine tier comprises IPTV service routers and a communication network thus enabling provision of an IPTV service between different networks which may belong to different operators and or be installed in different countries. Thus the invention adds roaming functionality to the existing IPTV service.

However the method and element disclosed in EP1895777 A1 do not enable a subscriber to receive and display ITPV content on an alternative device such as a computer. Instead the disclosed invention provides an alternative architecture for delivery of the programming content to the subscriber and does not address the issues discussed above concerning the technology employed at the client end.

Similarly WO 2008 045384 A2 discloses an IPTV transport architecture with double layer encryption and bulk decryption. The disclosed invention is designed to operate in accordance with a client s traditional television STB combination and does not provide a means of presenting the programming content on an alternative device.

A number of systems are known in relation to STB simulation for the purpose of testing constrained isolated aspects of IPTV service delivery.

For example the invention disclosed in EP 1914940 A1 provides a test apparatus for assessing the quality of an IPTV service and to locate and repair malfunctions. The test apparatus accesses the IPTV network from a central office as a simulation of the user s STB receives and analyses channel information and media contents downloaded from the IPTV network and then generates test results. This obviates the need for an operator to enter the user s premises and perform the test routine using manual test apparatus. Thus the STB simulation performed by the disclosed invention is limited such that it only simulates the way in which the STB presents itself to the network and receives information from the network. It does not present a fully operable STB emulation system which could be used to replace a user s STB and television and present the received content to the viewer. Thus it does not provide a means of performing all the functions required and expected of a physical STB.

Similarly US 2002 0026637 A1 discloses a computer program which allows a personal computer to emulate the functions of various STBs so that a combined video and an enhanced content stream can be displayed and randomly accessed to ensure that a desired layout is achieved with respect to the displayed content. The program is designed to facilitate quick and easy checking of the quality of the content presentation with modification to the combined content stream being permitted during the checks if required. Thus only one aspect of a traditional STB functionality is addressed by the disclosed invention which does not provide a complete alternative system for use in presenting IPTV content to an end user. The disclosed invention provides a means of pre viewing video and interactive content by a producer rather than presenting a complete service to a user.

Neither US 2002 0026637 A1 nor EP 1914940 A1 address the problem of integrating different forms of existing middleware products with a STB emulation system. Neither do they include simulation components to support or emulate other traditionally required functions such as conditional access and other network management functions.

Thus it is an object of the invention to provide a means for receiving IPTV services on a user s device such as but not exclusively a personal computer and presenting the IPTV content on the device such that the viewer enjoys continuity of programming service regardless of his her physical location or the underlying hardware software platform of the device.

Thus it is an object of the invention to provide a system and method for the simulation of a physical STB and to enable standard computing components to mirror and mimic their televisual counterparts e.g. monitor CPU disk TV STB VCR .

It is an object of the invention to provide a solution which can be easily integrated with known IPTV technologies.

It is a further object of the invention to maintain substantially the same viewing experience as that experienced by a user when receiving and viewing televisual services via traditional i.e. television plus physical STB or alternative technologies. In other words the content navigational paradigm presentation and quality of service must be substantially the same as those enjoyed by users of traditional IPTV systems.

It is a further object of the invention to provide a means of receiving and presenting said IPTV service such that 3party category I or category II middleware designed for execution by a physical STB can execute in its usual manner and provide the same functionality on the viewer s computer without modification. The maintained functionality will typically include the ability to perform presentation layer rendering video blending and multi media control and the provision of User Interfaces.

Thus it is an object of the invention to provide a virtual STB application environment which not only emulates the underlying hardware capabilities of a physical STB e.g. video scaling video positioning chroma keying alpha blending UI layout Remote Control key handling etc. but also provides the same software environment in terms of available APIs and libraries such that 3party middleware is able to execute in this environment without modification.

It is a further object of the invention to provide a Conditional Access CA mechanism such that a service provider is able to control and manage the user s ability to access the programming content said mechanism being easy to deliver and manage from a network provider s perspective.

It is a further object of the invention to provide an IPTV system wherein the system is resource efficient especially in respect of CPU usage and memory .

It is a further object of the invention to provide an IPTV system for receiving and presenting IPTV services on a user s device such that dynamic video source selection DVSS is achieved wherein the system is able to determine and acquire the optimal quality programming possible based on the current position of the user s device within the network. It is preferred that this source selection is achieved dynamically without the need for explicit input from the user.

Thus the present invention provides a means of eliminating or alleviating at least one of the above identified problems and achieving at least one of the above identified objectives.

In accordance with a first aspect of the present invention there is provided a set top box emulation system for presenting IPTV content to a user on an electronic device said emulation system comprising 

ii a plurality of management components arranged and configured to emulate the capabilities of a physical set top box wherein the plurality of management components comprises at least one of a presentation manager a codec manager and or a conditional access manager and

iii a plurality of interfaces to enable communication between said plurality of management components and said middleware wherein the plurality of interfaces comprises at least one of a graphics interface a MUX interface a Conditional Access interface a Media interface and Events Interface a System Settings interface and or a Persistent Storage interface.

In a preferred embodiment of this first aspect an IPTV system is arranged and configured such that a viewer can receive and watch IPTV televisual content displayed on an electronic device said device acting as an alternative to a traditional television and STB combination. In a typical embodiment said device is a personal or laptop computer although other electronic devices may be used.

It is preferred that the televisual content is delivered from a service provider s head end in the same way that it would be delivered to a STB being used in conjunction with a television set. When viewing said televisual content in accordance with the present invention the navigational and presentation styles are maintained and the format of the content is the same or substantially the same as that experienced by a viewer using a physical STB and television set.

Essentially the invention provides a means for emulation of a traditional physical STB such that a virtual STB environment is created within the viewer s computer. The emulation is achieved by a software based system which creates a virtual STB environment for other known software to interact with such that the emulation system running on the computer presents itself to the network and service provider as if it were a physical STB connected to a television.

Preferably the present invention has 3party middleware embedded within it said middleware being appropriate to the viewer s chosen service provider. That is to say the virtual STB component acts as a wrapper around a vendor s middleware. Thus a STB emulation component is installed on the end user s i.e. viewer s device said emulation component encapsulating 3party middleware which is appropriate for and compatible with the delivery system deployed by the user s chosen IPTV service provider.

Thus in accordance with a first aspect of the invention there is provided an API based STB emulation environment within which known 3party middleware both category I and II is able to execute. The execution and performance of the middleware is preserved in its traditional form and the 3party middleware interacts with the virtual STB environment i.e. with the invention as it would with a traditional STB operating within a traditional IPTV system. No modification of the vendor s middleware is required.

Thus the viewer is able to view televisual content on an electronic device such as a personal or laptop computer or other electronic device by providing a virtual STB environment within the device said virtual environment being able interface and interact with known 3party middleware such that all aspects of functionality performance and presentation formats are substantially identical to those enjoyed by users of a traditional IPTV i.e. STB plus TV configuration.

In accordance with a second aspect of the invention the STB emulation component emulates the underlying hardware capabilities of a physical STB thus enabling the same functionality such as video scaling video positioning chroma keying alpha blending User Interface UI layout Remote Control key handling and so on . These functions are emulated by a plurality of sub components each sub component handling the emulation of a particular STB function. Each sub component may in turn comprise one or more further sub components.

In a preferred embodiment of the first aspect of the invention the sub components of the STB emulation component may include but are not restricted to a player component an embedded web browser a management component a decryption component and a set of one or more API libraries.

The STB emulation component may be configured or tailored to the viewer s or service provider s requirements via the use of configuration files which store settings to enable and facilitate the management and control of the behavior of the STB emulation component.

In addition to the STB emulation environment there is provided a set of core APIs which act as conduits into the 3party middleware executing within the virtual i.e. emulated STB environment. These APIs are essential to the performance of the claimed invention.

The APIs service requests made by external applications and expose the functionality of the middleware to those applications. Thus the STB emulation component operates in conjunction with the set of core APIs to enable the maintenance of connectivity between standard category I and II middleware and the IPTV service provider.

In other words in order to facilitate management from the network operator perspective there needs to be direct access into the embedded middleware by the service provider. If the middleware belongs to category I this is achieved by DOM connectivity. If however the middleware belongs to category II then connectivity is achieved via the middleware s APIs which connect to the set of core APIs provided in accordance with the invention.

Thus the emulated environment provided by the present invention is agnostic to 3party middleware connectivity.

In a preferred embodiment of a first aspect of the invention the APIs provide the following essential capabilities although other interfaces may be included so as to extend the set of capabilities or alternatively some may not be required in alternative embodiments a Graphics Interface a MUX interface a conditional Access CA Interface a Media Interface a Network Interface an Event interface a System Settings Interface and a Persistent Storage Interface.

In accordance with a second aspect of the invention the middleware selected for use with the arrangement described above is category II i.e. API based middleware. In a preferred embodiment the user interface is handled by the category II middleware. The APIs provided in accordance with the present invention plug into i.e. provide connectivity with the APIs provided within the 3party category II middleware.

Thus the category II middleware is able to operate within the emulated environment without any alteration or modification even though it was designed originally for use with a physical STB and television set rather than a computer system.

In accordance with a third aspect of the invention the arrangement described in relation to the first aspect is configured for use with category I i.e. browser based middleware. In accordance with the third aspect of the invention and in addition to the features listed in relation to the first aspect there is provided a proprietary web browser. Preferably the set of core interfaces described above graphics interface events interface etc. integrate or connect with the proprietary browser. In a preferred embodiment the user interface is handled by the proprietary browser working in conjunction with the category I middleware.

In accordance with the third aspect of the invention a set of STB emulation APIs written in ECMAScript is inserted into the DOM of the browser. Third party category I middleware is also inserted into the DOM of the browser. The STB emulation APIs emulate and or replace the APIs which would traditionally be provided by the STB vendor. They take DOM requests and translate them into API requests.

Thus the category I middleware is able to operate within the emulated environment without any alteration or modification even though it was designed originally for use with a physical STB rather than a computer system.

For the sake of clarity it should be noted that a typical embodiment of the emulation system described herein provides at least two sets of distinct APIs 

According to a fourth aspect of the invention there is provided a Dynamic Video Source Selection DVSS component arranged and configured for use with the present invention.

As previously stated viewers of IPTV programming content are not generally concerned with the underlying delivery mechanism s used to provide their viewing content. They do however care about the quality of that content and the ease with which they can access their desired programs.

Thus there is a need to provide for the viewer a consistent navigational paradigm whilst behind the scenes determining and acquiring the best quality programming available based upon the current position of the client device within the network. In summary the aim of the DVSS component is to provide a consistent viewing experience using any network whilst maintaining optimal quality of service.

In addition the provision of a DVSS component removes the need for a closed network and allows the client device to receive regular DVB based broadcast feeds typically via a USB based DVB T dongle and thus it is not mandatory that the video packets received via the network are encapsulated in IP. This approach is usually referred to as a hybrid approach.

These and other aspects of the present invention will be apparent from and elucidated with reference to the embodiment described herein.

With reference to the above listed Figures shows how in a traditional IPTV arrangement comprising a physical STB content is delivered to a viewer s television set such that the presentation style of the content is the same as that experienced by the viewer when using a non IPTV based delivery system. As shows signals are transmitted from the service provider over a network and are forwarded by a router to the viewer s STB. The STB which is connected to the viewer s television set processes the signals such that the content can be displayed on the television screen in a style and format identical to that experienced in the more traditional television broadcasting paradigms.

The present invention removes the need for a traditional i.e. physical STB or television set and provides a software based emulation environment such that the signals can be received processed and viewed on an alternative device such as a computer without loss or adaptation of service presentation style or functionality.

This maintenance of viewing experience is illustrated in which shows a laptop computer configured for use in accordance with the present invention and illustrates how the invention has been architected to deliver a rich multi media televisual experience akin to that traditionally associated with a physical STB and television set. The image shows the end result of how the 3party middleware has elected to render the user interface and video layers with respect to each other.

Thus the functional components of the invention best illustrated in coupled with the core APIs shown in allow the middleware to define the exact co ordinates of each visual element in all 3 planes X Y and Z . The Z plane also includes the ability to apply alpha blending techniques to vary the opacity of the User Interface UI layer with respect to the video layer.

As shown in operators are typically forced to consider an almost complete duplication of their television infrastructure when they decide to target devices such as PCs with services. This is generally because the protocols and technologies associated with web TV delivery as well as its navigational paradigms differ from those of IPTV implementations. This is largely a result of technological limitations than choice.

When considering WebTV services operators are usually forced to transrate or transcode their existing content into a more PC friendly format such as Windows Media and Flash. This then requires the employment of alternative Conditional Access and Digital rights Management DRM strategies and must finally re design their whole UI presentation layer to overcome the non TV nature of their target device.

This leads generally to implementations where text flows around not over the video. and emphasize the point by illustrating the result of each of the architectures on the services that can be delivered to the end user.

According to a first aspect of the invention a computing device is configured and arranged such that an operating system OS is able to execute on said computer and is connected to a network such that data may be received from external source s over the network and or sent to external source s over the network.

In addition it is preferred that the computing device is arranged and configured to include a plurality of hardware components such as those included in a typical personal laptop computing system. Such hardware components may include but not be limited to 

In a preferred embodiment said interfaces may provide the following essential capabilities although other interfaces may be included so as to extend the set of capabilities or alternatively some may not be required in alternative embodiments 

Turning to a preferred embodiment of the invention is shown and illustrates in greater detail the STB emulation component of the invention. Said emulation component comprises further subcomponents including 

Turning to a preferred embodiment of the fourth aspect of the invention a DVSS component is provided and is integrated with the emulation sub components described above. The DVSS component implements the concept of dynamic video source selection which is most clearly illustrated in .

Preferably the DVSS component further comprises sub components such as but not restricted to a PVR controller an IGMP client a RTSP client and a DVB T client. The DVSS component integrates with a controller which in turn is supported by an AV API contained within the afore said Javascript API libraries. In a preferred embodiment the DVSS component may also integrate with the decryption component.

In a typical embodiment a management component is provided which enables a network operator to manage the system as if it were a router or a physical STB. This further comprises a TR 135 client which allows the management according to standards based TR 069 based management servers.

In a typical embodiment a decryption component is provided and forms an interface between said DVSS component and said player component. The role of this component is to receive signals from a dynamically selected source decrypt said signals and pass them on to the player component for further processing and display.

In a typical embodiment API libraries implemented in a language such as Javascript are provided and may include a display API to provide connectivity with said player component an AV API to provide connectivity with a DVSS controller which in turn integrates with said DVSS component and an Event API which provides support for requests made by the management component .

It should be noted that the above mentioned embodiments illustrate rather than limit the invention and that those skilled in the art will be capable of designing many alternative embodiments without departing from the scope of the invention as defined by the appended claims. In the claims any reference signs placed in parentheses shall not be construed as limiting the claims. The word comprising and comprises and the like does not exclude the presence of elements or steps other than those listed in any claim or the specification as a whole. In the present specification comprises means includes or consists of and comprising means including or consisting of . The singular reference of an element does not exclude the plural reference of such elements and vice versa. The invention may be implemented by means of hardware comprising several distinct elements and by means of a suitably programmed computer. In a device claim enumerating several means several of these means may be embodied by one and the same item of hardware. The mere fact that certain measures are recited in mutually different dependent claims does not indicate that a combination of these measures cannot be used to advantage.

