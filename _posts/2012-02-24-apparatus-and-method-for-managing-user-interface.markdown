---

title: Apparatus and method for managing user interface
abstract: An apparatus for and method of managing a user interface. The apparatus for managing a user interface including: a packet generation unit that generates a notification packet indicating that one or more remote servers exist on a network, a web server that manages a command for storing a state of a user interface of a predetermined application transmitted through the network or an extract command received as a result of distributing the notification packet, a state storage unit that stores the state of the user interface according to the store command, and a communication unit that transmits the state of a predetermined user interface extracted according to the extract command from among the stored states of the user interface.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08521814&OS=08521814&RS=08521814
owner: Samsung Electronics Co., Ltd.
number: 08521814
owner_city: Suwon-si
owner_country: KR
publication_date: 20120224
---
This is a Continuation Application of U.S. application Ser. No. 11 600 878 now U.S. Pat. No. 8 150 978 filed Nov. 17 2006 in the U.S. Patent and Trademark Office which claims priority from Korean Patent Application No. 10 2006 0045849 filed on May 22 2006 in the Korean Intellectual Property Office and U.S. Provisional Patent Application No. 60 737 375 filed on Nov. 17 2005 in the United States Patent and Trademark Office the disclosures of which are incorporated herein by reference in their entirety.

The apparatuses and methods consistent with the present invention relate to managing a user interface and more particularly to managing a user interface in which a state of a user interface of an application provided by a server on a network is managed using a hypertext markup language HTML and a hypertext transfer protocol HTTP .

Technologies that provide an application by a remote server include Microsoft s remote desktop protocol RDP and Intel s extended remote protocol. These remote technologies are based on a binary bitmap transmission protocol and when providing an application they have a drawback of requiring a large network bandwidth. In particular when a user interface of a remote application uses audio and or video streaming the required bandwidth of a network becomes larger.

Meanwhile a user who performs a job using an application provided by a server through a predetermined client may later request a consistent user interface when the user performs a job using the application through another client. That is the user wants the same user interface which was used for a job that was finished through a first client to be displayed through a second client.

Networking operations of the UPnP environment include addressing discovery description control eventing and presentation. The remote control point confirms that a connection with the first remote client is operating. Then the remote control point makes the remote server maintain the state of a user interface for the currently operating connection for a predetermined time and makes the remote server store the state.

Then the remote control point terminates the connection between the remote server and the first remote client establishes a connection between the remote server and the second remote client and then commands the remote server to provide the stored user interface to the second remote client .

However among the various states of the user interface in addition to the user interface states managed by the remote server there are also states managed by the remote clients and . For example client cookies of a web browser a form input and an audio video object are all managed by remote clients. Accordingly the states of the user interface stored in the remote server according to the conventional technology do not include the states managed by the remote clients and .

When the remote server does not have a storage unit there is no method of storing and restoring the states of a user interface. Thus there is a need to solve this problem.

According to an aspect of the present invention there is provided an apparatus for managing a user interface including a packet generation unit that generates a notification packet indicating that one or more remote servers exist on a network a web server that manages a command for storing a state of a user interface of a predetermined application transmitted through the network or an extract command received as a result of distributing the notification packet a state storage unit that stores the state of the user interface according to the store command and a communication unit that transmits the state of a predetermined user interface extracted according to the extract command from among the stored states of the user interface.

According to another aspect of the present invention there is provided an apparatus for displaying a user interface including a server retrieval unit that searches a server storing a state of a user interface in relation to a provided application a state management request unit that generates a packet for a store command or an extract command in relation to the state of the user interface according to the searching result a communication unit that transmits the state of the user interface or the packet and a web browser that displays a predetermined user interface received in response to the transmission of the packet for the extract command.

According to still another aspect of the present invention there is provided a method of managing a user interface including generating a notification packet indicating that one or more remote servers exist on a network managing a store command of a state of a user interface of a predetermined application transmitted through the network or an extract command received as a result of distributing the notification packet storing the state of the user interface according to the store command and transmitting the state of a predetermined user interface extracted according to the extract command from among the stored states of the user interface.

According to a further aspect of the present invention there is provided a method of displaying a user interface including searching a server storing a state of a user interface in relation to a provided application generating a packet for a store command or an extract command in relation to the state of the user interface according to the result of the searching transmitting the state of the user interface or the packet and displaying a predetermined user interface received in response to the transmission of the packet for the extract command.

Advantages and features of the present invention and methods of accomplishing the same may be understood more readily by reference to the following detailed description of exemplary embodiments and the accompanying drawings. The present invention may however be embodied in many different forms and should not be construed as being limited to the exemplary embodiments set forth herein. Rather these exemplary embodiments are provided so that this disclosure will be thorough and complete and will fully convey the concept of the invention to those skilled in the art and the present invention will only be defined by the appended claims. Like reference numerals refer to like elements throughout the specification.

The present invention will now be described more fully with reference to the accompanying drawings in which exemplary embodiments of the invention are shown.

One or more remote servers may exist on the network . The remote server provides an application to the remote client . To achieve this each of remote servers through can have a web server and can periodically transmit a notification packet indicating that it is connected to the network .

Here the application may include an application program that can be executed in the remote client and may also include a web page.

Also the remote server can transmit its state according to a request of the remote client . The state of the remote server may include a uniform resource locator URL of an application being provided. The network may be a wired network or a wireless network. The network transfers data between respective devices using the HTTP.

The remote client displays an application provided by the remote server . To achieve this the remote client may include a web browser. In order to receive an application first the remote client searches for a remote server on the network . The searching for the remote server can be performed by receiving a notification packet. The remote client communicates with the remote server by referring to the address of the remote server included in the notification packet and requests a desired application.

While receiving an application through this process the remote client can stop reception of the application and the application being provided can be provided again later. To achieve this the remote client transmits the state of a user interface in relation to the application at the time when the reception is stopped so that the state can be stored.

Like the remote server the storage server also periodically transmits a notification packet indicating that the storage server is connected to the network and to achieve this the storage server may have a web server. The remote client receiving the notification packet of the storage server communicates with the storage server by referring to the address of the storage server included in the notification packet and transmits the state of a user interface in relation to the application being provided to the remote client to the storage server .

Here the state of the user interface includes the state of the remote server and the state of the remote client in relation to the application. The state of the remote server includes information on the URL of the application as described above and the state of the remote client includes web browser cookies a form input and an audio video object.

The state of the user interface can be provided to the storage server in an HTML format and may relate to an application provided by one or more remote servers .

For example a first remote client can receive an application from the first remote server and the second remote server at the same time. At this time the state of the user interface that the first remote client wants to store includes the state of the first remote server the state of the second remote server and cookies of a web browser of the first remote client a form input and an audio video object.

Meanwhile a user who operates the application provided by one or more remote servers through the first remote client can stop the operation and store the state of the user interface in the storage server and then can continue to operate the application through a second remote client .

In this case the second remote client receives a notification packet transmitted by the storage server confirms that the storage server exists on the network and then requests the storage server to transmit the state of the user interface.

According to the request of the remote client the storage server transmits the state of the user interface which may include the state of the user interface in relation to a plurality of applications provided by a plurality of remote servers .

The second remote client which receives the state of the user interface in relation to the plurality of applications can receive the plurality of applications included in the state of the user interface at the same time or can receive one or more applications selected by the user.

The application generation unit generates an application to be provided to the remote client . Here the application may include an application program that can be executed in the remote client and may also include a web page.

The packet generation unit generates a notification packet indicating that the remote server exists on a network. The notification packet includes an address of the remote server . By referring to this address the remote client can communicate with the remote server . The notification packet can be transmitted periodically through the communication unit .

The web server provides an application to the remote client by using a client server model and the HTTP. Apache Internet Information Server IIS Enterprise Server or Lotus Domino Server can be used as the web server according to an operating system operating on the remote server .

The state management unit provides to the remote client the state of the user interface in relation to an application being provided. Here the states managed by the state management unit indicate the states of only the remote server and can include a URL of an application.

If a request from the remote client to transmit the state of a user interface is received the state management unit confirms the state of the user interface in relation to the application currently being provided and then transmits the confirmation result through the communication unit .

The communication unit communicates with the remote client transmitting an application or the states of the user interface and receiving a packet requesting the state of the user interface.

The method of communication between the communication unit and the remote client can be a wired communication method such as Ethernet universal serial bus USB IEEE 1394 serial communication and parallel communication methods and can also be a wireless communication method such as infrared communication Bluetooth Home radio frequency RF and wireless LAN methods.

Packets transmitted and received through the communication unit may have an HTML format. As such loads to a network can be reduced compared to a method providing a user interface as image data.

The control unit determines the type of packet received through the communication unit and performs overall control of the application generation unit the packet generation unit the web server the state management unit the communication unit and the remote server .

The state storage unit stores the state of a user interface received from the remote client . Here the state of the user interface may include cookies of a web browser of the remote client a form input an audio video object and the state of the remote server providing an application. The state of the remote server may include the state of one or more remote servers .

When the state of a user interface is stored the state of each user interface can be given a predetermined name. Here the name may be input directly by the user of the remote client or may be generated by automatically combining a time when the state is stored the name of an application the name of a remote server or an address of a remote server.

The state storage unit includes a module capable of inputting and outputting information such as a hard disc a flash memory a compact flash CF card a secure digital SD card a smart media SM card a multimedia card MMC or a memory stick.

The web server provides to the remote client an interface for storing the state of a user interface by using a client server model and the HTTP. That is the user of the remote client can store and extract the state of the user interface through the interface provided by the web server .

The packet generation unit generates a notification packet indicating that the storage server exists on a network. The notification packet includes an address of the storage server . By referring to the address the remote client can communicate with the storage server . The notification packet can be periodically transmitted through the communication unit .

The communication unit transmits and receives a notification packet a store command an extract command or the state of a user interface through communication with the remote client . The method of communication between the communication unit and the remote client can be a wired communication method such as Ethernet universal serial bus USB IEEE 1394 serial communication and parallel communication methods and can also be a wireless communication method such as infrared communication Bluetooth Home radio frequency RF and wireless LAN methods. Packets transmitted and received through the communication unit may have an HTML format.

The control unit determines the type of packet received through the communication unit and performs overall control of the state storage unit the web server the packet generation unit the communication unit and the storage server .

Meanwhile the remote server and the storage server may be disposed in one apparatus hereinafter referred to as an integrated server . The integrated server provides an application to the remote client and can store the state of the user interface according to a request by the remote client .

The state of the user interface to be stored in the integrated server can include the state of a user interface in relation to an application provided by another remote server as well as the state of the user interface in relation to an application provided by the integrated server.

The state management request unit generates a request packet to request the state of the remote server a packet for a store command to store the state of a user interface hereinafter referred to as a store command packet and a packet for an extract command to extract the state of a user interface hereinafter referred to as an extract command packet .

Each packet is transmitted through the communication unit and the request packet is transmitted to the remote server and the store command packet and the extract command packet are transmitted to the storage server .

The web browser displays an application provided by the remote server or displays a user interface received from the storage server in response to an extract command packet.

Here the web browser displays names in relation to the states of a plurality of user interfaces provided by the storage server . At this time the user selects one of the displayed names so that the user can operate a desired application.

The server retrieval unit searches for the remote server or the storage server . The remote server and the storage server periodically distribute notification packets to indicate that they are connected to a network. The server retrieval unit analyzes a notification packet received through the communication unit and determines whether the remote server or the storage server exists on the network.

If it is determined by the server retrieval unit that the remote server or the storage server exists on the network an address of the remote server or the storage server included in the notification packet is transferred to the control unit .

By referring to the address transferred by the server retrieval unit the control unit enables the web browser and the web server of the remote server or the web server of the storage server to communicate with each other.

Also the control unit performs overall control of the state management request unit the storage unit the web browser the server retrieval unit the communication unit and the remote client .

The storage unit stores cache information on peripheral devices forming a network. The addresses of the remote server and the storage server retrieved by the server retrieval unit may be included in the cache information. Also in case of the storage server an additional flag may be added and stored. The storage unit may comprise a hard disk a flash memory a CF card a SD card a SM card a MMC a memory stick and other modules capable of inputting and outputting data.

The communication unit transmits and receives an application a request packet a store command packet and an extract command packet through communication with the remote server or the storage server .

Here the communication unit can transmit and receive an application the state of a user interface or a packet by using the HTTP and the state of the user interface and the packet may be formed using the HTML.

As described above the state of the user interface may include a URL of an application cookies of a web browser of a remote client a form input an audio video object and an address of a remote server. The HTML code may include the states of a plurality of user interfaces of an application.

In in  url   URLs in relation to one or more applications are input. For example in  url1  a URL URLForPageToBeSaved 1 of a first application can be input and in  url2  a URL URLForPageToBeSaved 2 of a second application can be input 

The state of each user interface may include one cookie url .cookie one or more form inputs url .form.formid an audio video object url.av.avobjid .state and the state of a remote server url .server .

In the form input formid indicates a unique number of a form input and the type is determined according to the type of an input value formid  value string . For example if the type of an input value is text the type of the form input becomes text.

In an audio video object avobjid indicates a unique number of an audio video object and state indicates URL or reproduction information in relation to an audio video object. For example if state indicates a URL of an audio video object it can be expressed as url.av.avobjid.data http 192.168.0.1 videos efg.mpg. If state indicates reproduction information of an audio video object it can be expressed as url.av.avobjid.playPosition 93847. Here playPosition indicates a predetermined reproduction position when the audio video object is reproduced.

The state of a remote server requested from the remote server by a remote client is input as the state of a remote server. For example when a remote clients is connected to a remote server and is receiving electronic program guide EPG information as an application the remote server can respond with a state progid 123 recordStartTime 09 00AM step 3. Accordingly it can be expressed as url.server progid 123 recordStartTime 09 00AM step 3.

Here the name of the user interface may be input directly by the user of the remote client or may be generated by automatically combining a time when the name is stored the name of an application the name of a remote server or an address of a remote server.

At this time if the name of a user interface included in the store command packet A is the same as the name of a user interface already stored in the storage server a different name may be specified by the user or an arbitrary name may be specified by the storage server . For example by adding a predetermined number to the name of the received user interface the storage server can distinguish the name from the already stored name of the user interface.

Meanwhile the remote client may transmit a store command packet A to store the states of a plurality of user interfaces in relation to respective applications provided by a plurality of remote servers . Accordingly the store command packet A may include states of the plurality of user interfaces.

As illustrated in the extract command packet B includes the name RESTORE  name of a user interface desired to be extracted and an HTML code in relation to the name HOST of a remote client.

The storage server receiving the extract command packet B extracts a state having the name of the user interface corresponding to the packet B among the states of user interfaces and transmits the state to the remote client .

A remote client receiving a notification packet from a remote server or a storage server transmits an HTTP request packet HTTP Request to the remote server or the storage server by referring to the address included in the notification packet.

First when the HTTP request packet is transmitted to the remote server having no storage unit in operation the remote server transmits an HTTP response packet to the remote client in operation . Here the header of the HTTP response packet does not include a flag indicating that the remote server has a storage unit.

Accordingly in operation if the remote client transmits an HTTP request packet to the storage server which is another server existing on the network the storage serer transmits an HTTP response packet to the remote client in operation . Here the header of the HTTP response packet includes a flag indicating that the storage server has a storage unit. For example a flag such as the one below can be inserted into the header 

Here RUIS indicates a remote user interface server such as the remote server and the storage server having web servers and respectively and an integrated server.

Then if the user inputs a store command in operation S the remote client collects the state of a user interface in relation to an application being currently operated in operation S. That is by requesting the URL of the application from the remote server providing the application the remote client receives the URL of the application and confirms cookies of a web browser a form input and an audio video object.

Then in operation S the remote client transmits to the storage server a store command packet A including the name of a user interface the name of a remote client the size of a packet the type of an HTML document and an HTML code in relation to the collected state of the user interface. The storage server stores the HTML code in relation to the state of the user interface included in the store command packet A.

The server retrieval unit of the remote controller performs the role of a control point of the UPnP and the control unit or and the packet generation unit or of the remote server or the storage server perform the role of a controlled device. By doing so UPnP communication between the remote client and the remote server or the storage server can be performed.

The remote client receives a notification packet through a discovery step with the remote server or the storage server . Then by referring to an address included in the notification packet the remote client transmits a device description document DDD request packet to the remote server or the storage server in an HTTM GET method.

First when the DDD request packet is transmitted to the remote server having no storage unit in operation S the remote server transmits a DDD response packet to the remote client in operation S. Here the header of the DDD response packet does not include information indicating that the remote server has a storage unit.

Accordingly the remote client analyzes the received DDD response packet and updates cache information on peripherals forming the network in operation S. Then after storing the updated cache in the storage unit the remote client transmits a DDD request packet to the storage server which is another server existing on the network in operation S.

The storage server receiving the DDD request packet transmits a DDD response packet to the remote client in operation S. Here the DDD response packet includes information indicating that the storage server has a storage unit. For example information such as the information shown below can be inserted into the DDD response packet.

Accordingly the remote client analyzes the received DDD response packet updates cache information in operation S and stores the updated cache information in the storage unit . Transmission of the DDD request packet and analysis of the DDD response packet are performed in relation to all devices existing on the network. Accordingly information on a plurality of storage servers having storage units can be included in the cache information.

Then if the user inputs a store command in operation S the remote client collects the state of a user interface in relation to an application being currently operated in operation S.

Then after selecting one in the list of storage servers included in the cache information the remote client transmits to the selected storage server a store command packet A including the state of the user interface in operation S. Here the selection of the storage server can be performed by the user.

When the server retrieval unit of a remote client performs the role of a control point of the UPnP and the control unit and the packet generation unit of a storage server perform the role of a controlled device UPnP communication between the remote client and the storage server can be performed.

A remote client receives a notification packet through a discovery step with the storage server . By referring to an address included in the notification packet the remote client transmits a DDD request packet to the storage server in operation S.

The storage server receiving the DDD request packet transmits a DDD response packet to the remote client in operation S. Here the DDD response packet includes a list of applications and may also include the URL of the user interface in relation to each of the applications.

Here http 192.168.0.2 SRH indicates a module of the storage server in which states of the user interface are stored. That is an address of the state storage unit is stored.

Accordingly the remote client analyzes the received DDD response packet updates cache information and stores the updated cache information in the storage unit .

Then according to a command input by the user to retrieve the state of a user interface the remote client extracts an address of the state storage unit of the storage server included in the cache information. By using the extracted address the remote client transmits an HTTP request packet in order to communicate with the storage server in operation S.

Accordingly the storage server transmits an HTTP response packet S into which is inserted a list on the state of the user interface in an HTML or extensible markup language XML format. That is to say the hyperlink for the state of each user interface is included in the HTTP ACK packet. An example of the hyperlink is as follows 

The HTML format list is output through the web browser of the remote client and the user selects a desired state of the user interface in the output list.

The packet that is the extract command packet B into which the selection result is inserted is transmitted to the storage server in operation S. The storage server extracts the state of the user interface included in the extract command packet B from the state storage unit and transmits the state to the remote client in operation S. The remote client restores the user interface in relation to the application according to the received state of the user interface.

In order to manage the state of a user interface the packet generation unit of a storage server generates a notification packet indicating that the storage server exists on a network. The notification packet is periodically transmitted through the communication unit in operation S and as the notification packet is transmitted the web server performs communication with a remote client through the communication unit .

Then the web server receives a store command packet A from the remote client in operation S. The state storage unit stores the state of the user interface included in the received store command packet A. Here the state of the user interface includes cookies of a web browser of the remote client a form input an audio video object and a URL of an application.

Then the web server receives an extract command packet B from the remote client in operation S. The control unit searches the state storage unit and extracts the state of the user interface included in the extract command packet B.

The extracted state of the user interface is transmitted to the remote client through the communication unit in operation S. Based on the extracted state the remote client displays the user interface in relation to the application desired to be restored.

In order to restore an application provided by a remote server the server retrieval unit of a remote client searches a storage server capable of storing the state of the user interface in relation to the provided application in operation S. The server retrieval unit analyzes a notification packet received through the communication unit and determines whether or not the storage server exists on the network.

If the retrieval result of the server retrieval unit indicates that the storage server exists on the network the state management request unit generates a store command packet A in relation to the state of the user interface according to the store command input of the user in operation S.

In order to generate the store command packet A the state management request unit collects the state of a user interface in relation to an application being currently operated. The state of the user interface includes a URL of the application cookies of a web browser a form input and an audio video object. The store command packet A is transmitted to the storage server through the communication unit in operation S.

Here the URL of the application may be supplied from the remote server . For example a HTTP request packet including the following HTTP code may be transmitted to the remote server . http 192.168.1.1 EPG record GETSTATE

In response to the HTTP request packet the remote server transmits a HTTP ACK packet to the remote client . The HTTP ACK packet may include the following HTTP code containing information regarding the application.

As the state of the remote server is received the state management requestor may generate a record command packet containing the following HTTP code.

As the user inputs a restore command to restore the state of the user interface in operation S the state management request unit generates an extract command packet B in operation S. The generated extract command packet B is transmitted to the storage server through the communication unit in operation S.

As the extract command packet B is transmitted the communication unit receives the state of the user interface from the storage server in operation S. The received state of the user interface is transferred to the web browser and the web browser displays the user interface in relation to a predetermined application according to the received state of the user interface in operation S.

As described above the apparatus and method of providing a user interface of the exemplary embodiments of the present invention may provide the following advantages.

First by storing the state of a user interface of an application provided by a server on a network in a separate device an identical user interface can be provided to a user who receives the application through different clients.

Furthermore user interfaces in relation to a plurality of applications provided by a plurality of servers existing on a network can be managed at the same time.

In concluding the detailed description those skilled in the art will appreciate that many variations and modifications can be made to the exemplary embodiments without substantially departing from the principles of the present invention. Therefore the disclosed exemplary embodiments of the invention are used in a generic and descriptive sense only and not for purposes of limitation.

