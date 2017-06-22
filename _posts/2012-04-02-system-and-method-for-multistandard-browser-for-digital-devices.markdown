---

title: System and method for multi-standard browser for digital devices
abstract: The present invention provides a method of rendering a thin client application in a network device, for parsing the internet data so as convert the internet data into a common data format which can be rendered in set-top box using any type of middleware. The invention would be equipped to handle any type of application and also would be cost-efficient to be developed in a middleware layer of a network device like set-top box.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08799974&OS=08799974&RS=08799974
owner: Infosys Limited
number: 08799974
owner_city: Bangalore
owner_country: IN
publication_date: 20120402
---
This application claims priority to Indian Patent Application No. 4312 CHE 2011 filed Dec. 12 2011 which is hereby incorporated by reference in its entirety.

The present invention relates to an application streaming technique in a network device and more particularly to a method and a system for effectively rendering an application in a set top box STB which can be extended to support middleware layer standards in network devices.

Internet browsing can be experienced in many digital devices now a days moving away from the conventional method of browsing internet through a computer. Though the extension of Internet browsing to digital devices is fast paced rendering a browsing technique in such digital devices becomes cumbersome since Internet browsing is not the primary functionality of the digital devices.

A middleware layer in a network device such as set top box STB provides a conducive platform for developing applications that can be displayed on a broadcasting receiving apparatus such as a television. The network device can exist standalone like STB or be a part of the television. In one instance an application for the television is deployed in the STB. The application may be a thick client application or a thin client application. Typically thick client applications may be developed in two ways viz. by means of a development STB provided by middleware vendors or by means of an emulator on a computer which can emulate similar environmental conditions as that of the STB. The traditional method of developing an application using the development STB provided by the middleware vendor is expensive due to the cost incurred for buying the development STB. The latter method of emulating the STB environment in the computer to develop applications is a more viable option.

Commercial emulators available for the purpose of emulating the STB environment are priced at par with the development STB offered by the middleware vendors. Although emulating STB environment in the computer and developing the application is easy for the developer the available emulators offer a spectrum of functionalities that may be exclusive.

In light of the discussion above a browser that can help in migrating applications from being thick client to thin client would be desirable. This would in turn provide more flexibility such as enabling any type of existing application to be rendered in the STB. Also existing browsers have inherent problems in developing an application supporting different input types such as Hypertext Markup Language HTML Extensible Hypertext Markup Language XHTML along with displaying the corresponding elements in different output toolkits.

Thus existing mechanisms used for rendering browsing techniques in a network device which is displayed on a broadcasting receiving apparatus have inherent problems as discussed above. Further developing and deploying the digital application with all the advantages increases the costs. Accordingly there is a need for developing and deploying the digital application in network devices which should be supported by any type of middleware.

The present invention provides a method of developing a multi standard compatible browser in a network device which parses the Internet data and converts the data into a common data format that can be rendered in a set top box STB using any type of middleware.

In one embodiment of the present invention a computer implemented method for streaming data in the network device is detailed. The method comprises sending a request to the server for obtaining data and parsing the received data so as to break the received data into individual components. The individual components are mapped into a common data format. Subsequently the data is mapped into components of middleware in the network device so that it can be displayed in a broadcasting receiving apparatus.

In another embodiment of the present invention as a part of rendering the browser in the network device the received data is mapped into a format that can be understood by middleware employed in the network device.

The invention proposes rendering of the thin client application in the network device thereby reducing the workload on the client. This is desirable for streaming applications in the network device. Also the invention can be provided as an independent service which can be utilized by other applications.

The following description is full and informative description of the best method and system presently contemplated for carrying out the present invention which is known to the inventors at the time of filing the patent application. Of course many modifications and adaptations will be apparent to those skilled in the relevant arts in view of the following description in view of the accompanying drawings and the appended claims. While the system and method described herein are provided with a certain degree of specificity the present technique may be implemented with either greater or lesser specificity depending on the needs of the user. Further some of the features of the present technique may be used to advantage without the corresponding use of other features described in the following paragraphs. As such the present description should be considered as merely illustrative of the principles of the present technique and not in limitation thereof since the present technique is defined solely by the claims.

In accordance with an embodiment network device contains a middleware not shown in the figure which is used for developing interactive applications such as web browser application which can be displayed in the broadcasting receiving apparatus such as a television. Deployment module is placed within the middleware which in turn is present in network device . The middleware in network device enables the interactivity of system .

Fetcher sends a request for data through network . In an embodiment fetcher may also monitor network for data without explicitly sending a request. Server may be employed to pass the data whenever requested by fetcher through network . It should be noted that server may also send data to the fetcher without receiving a request from the fetcher. Network may be one of a public a private and a hybrid network as per one embodiment of the present invention. As will be understood the public network is a network which can be configured with public Internet Protocol and is visible to devices in another network such as the Internet. The private network is a network in which devices are not visible to any outside network. The hybrid network is a combination of the public and private networks. Further the network may belong to a medium consisting at least one of a satellite terrestrial wired or an Internet broadcasting medium.

Component navigator is used for the purpose of navigating between the components rendered in the user interface of the application. In an embodiment an algorithm is used for linear navigation of the components which is managed by component navigator .

Application programming interface API processes the received declaratives. API hosts the middleware not shown in the figure . It should be noted that API is capable of exposing the functionality of every component of the present invention individually. Exposing the functionalities allows the invention to use other services to enhance system . Additionally API facilitates the integration of other mapping mechanisms such as an independent mapping system which may prove useful to existing systems.

Broadcasting receiving apparatus receives a broadcasted signal from connection . The connection may be one of Composite Video Component Video High Definition Multimedia Interface HDMI Video Graphics Array VGA or any such similar connection.

Event processor maps the application or user events from one communication protocol to another. In an embodiment the application or the user events of any user interface components in an Internet browser format such as Hypertext Markup Language HTML are mapped to corresponding Home Audio Video Interoperability HAVi event using a mapping table not shown which may be referred to as browser callback .

Network device receives data from server through network . It should be noted that this data may be either synchronous or asynchronous. The declaratives in the received data are split into components. The components are usually tags of Extensible Hypertext Markup Language XHTML . Parser converts these XHTML tags into a common data format. This data in common data format components is mapped to corresponding components in HAVi protocol and displayed in broadcasting receiving apparatus . Network device receives the user response for the displayed interface. The received user input is again converted back into declaratives and received at server . The converted declaratives in the specific format is sent to server and the cycle continues for every interaction.

In accordance with an embodiment the user input may be received as a text input when the user is provided with input devices such as keyboard. Similarly the user input may be received as a binary input when the user is provided with an input device such as a remote for the network device.

As used in this disclosure the term native STB refers to an STB that conforms to the standards mentioned by the specifications of the STB vendor. It should be noted that the above mentioned steps can be extended to any STB that follows middleware specifications such as MHP EBIF and so forth.

In one embodiment of the invention the functionality of a component navigator such as component navigator not shown in the figure is detailed so that the browser callback can be handled for another network device or a combination of two or more devices.

In one embodiment of the invention an application programming interface API such as API not shown in the figure is detailed to other devices so that a combination of functionalities of the parser and component navigator can be depicted to other devices.

One or more of the above described techniques can be implemented in or involve one or more computer systems. illustrates a generalized example of a computing environment . The computing environment is not intended to suggest any limitation as to scope of use or functionality of described embodiments.

With reference to the computing environment includes at least one processing unit and memory . The processing unit executes computer executable instructions and may be a real or a virtual processor. In a multi processing system multiple processing units execute computer executable instructions to increase processing power. The memory may be volatile memory e.g. registers cache RAM non volatile memory e.g. ROM EEPROM flash memory etc. or some combination of the two. In some embodiments the memory stores software implementing described techniques.

A computing environment may have additional features. For example the computing environment includes storage one or more input devices one or more output devices and one or more communication connections . An interconnection mechanism not shown such as a bus controller or network interconnects the components of the computing environment . Typically operating system software not shown provides an operating environment for other software executing in the computing environment and coordinates activities of the components of the computing environment .

The storage may be removable or non removable and includes magnetic disks magnetic tapes or cassettes CD ROMs CD RWs DVDs or any other medium which can be used to store information and which can be accessed within the computing environment . In some embodiments the storage stores instructions for the software .

The input device s may be a touch input device such as a keyboard mouse pen trackball touch screen or game controller a voice input device a scanning device a digital camera or another device that provides input to the computing environment . The output device s may be a display printer speaker or another device that provides output from the computing environment .

The communication connection s enable communication over a communication medium to another computing entity. The communication medium conveys information such as computer executable instructions audio or video information or other data in a modulated data signal. A modulated data signal is a signal that has one or more of its characteristics set or changed in such a manner as to encode information in the signal. By way of example and not limitation communication media include wired or wireless techniques implemented with an electrical optical RF infrared acoustic or other carrier.

Implementations can be described in the general context of computer readable media. Computer readable media are any available media that can be accessed within a computing environment. By way of example and not limitation within the computing environment computer readable media include memory storage communication media and combinations of any of the above.

Having described and illustrated the principles of our invention with reference to described embodiments it will be recognized that the described embodiments can be modified in arrangement and detail without departing from such principles. It should be understood that the programs processes or methods described herein are not related or limited to any particular type of computing environment unless indicated otherwise. Various types of general purpose or specialized computing environments may be used with or perform operations in accordance with the teachings described herein. Elements of the described embodiments shown in software may be implemented in hardware and vice versa.

In view of the many possible embodiments to which the principles of our invention may be applied we claim as our invention all such embodiments as may come within the scope and spirit of the following claims and equivalents thereto.

