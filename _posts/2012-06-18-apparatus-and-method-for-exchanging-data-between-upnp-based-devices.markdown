---

title: Apparatus and method for exchanging data between UPnP based devices
abstract: An apparatus and method are provided for exchanging data between Universal Plug and Play (UPnP) based devices. The apparatus includes a controller that generates and transmits a request for a parameter to a controlled device, and receives a response to the request from the controlled device; and a fast event data bus module that establishes a fast event data transmission path, based on information included in the response, and receives fast event data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09135209&OS=09135209&RS=09135209
owner: Samsung Electronics Co., Ltd
number: 09135209
owner_city: 
owner_country: KR
publication_date: 20120618
---
This application claims priority under 35 U.S.C. 119 a to Korean Patent Application Serial Nos. 10 2011 0058971 and 10 2012 0064078 which were filed in the Korean Intellectual Property Office on Jun. 17 2011 and Jun. 15 2012 respectively the content of each of which is hereby incorporated by reference.

The present invention relates generally to an apparatus and a method for exchanging data and more particularly to an apparatus and a method for exchanging data between Universal Plug and Play UPnP based devices.

UPnP technology is used for exchanging data between devices. The UPnP technology expands upon Plug and Play PnP technology used in a conventional computer system to a dynamic service interworking technology based on a network.

Devices supporting UPnP technology are generally classified into a control point and a controlled device based on an ability to be a subject of the control. A control point searches for or controls other devices and a controlled device performs a service provided by the controlled device itself under a control of the control point. In general the control point and the controlled device perform networking including an addressing process a discovery process a description process a control process and an eventing process.

Referring to the UPnP protocol stack includes an Internet Protocol IP a Transmission Control Protocol TCP a Hypertext Transfer Protocol HTTP a Simple Object Access Protocol SOAP and a General Event Notification Architecture GENA and the control point and the controlled device exchange data based on the UPnP protocol stack .

More specifically the control point communicates with other devices on a network through the IP and the TCP and performs the address process and the discovery process of searching for and inquiring other devices on the network through IP addresses.

Further the control point requests a specification file service description eXtensible Markup Language XML file or device description XML file of a device through an IP address of the controlled device in order to recognize a service provided by the controlled device and receives the specification file of the device from the controlled device. The control point recognizes the service provided by the controlled device by analyzing the specification file of the device provided by the controlled device.

Further in order to execute a service through the controlled device the control point transmits a control action message requesting an execution of the service provided by the controlled device to the controlled device and receives a control response message from the controlled device having received the corresponding control action message. Here the control action message and the control response message are expressed using XML through the SOAP .

Additionally the control point performs the eventing process of identifying whether an event of the controlled device providing a predetermined service through the control action message is generated i.e. whether there is a change in a state of the controlled device. When the control point transmits a SOAP message for requesting a subscription to identify the change in the state of the controlled device to the controlled device the controlled device transmits an event message of a text type to the control point using the GENA in order to inform of the change in the state of the controlled device.

As described above when exchanging data based on the conventional UPnP protocol stack a control related message such as the control action message and the control response message are transmitted and received between the control point and the controlled device using the SOAP and the controlled device transmits the event message to the control point by using the GENA . Here the GENA is used for exchanging the event message between the devices and the SOAP refers to a protocol for transmitting the control command to the device using XML.

According to the method of exchanging the data based on the aforementioned conventional UPnP protocol stack because the UPnP protocol was developed mainly for a control network the UPnP is conveniently used for exchanging a one shot control related message between devices included in the network by using the protocol such as the SOAP of the UPnP but is not suitable for periodically transmitting and receiving two way data at a high speed.

More specifically although it is convenient to transmit and receive the control action message and the control response message between the control point and the controlled device using the SOAP the SOAP is not suitable for periodically transmitting and receiving binary data at a high speed because the SOAP uses an attachment method based on a base encoding in transmitting and receiving the binary data.

Further the controlled device transmits an event message to a control point using the GENA but the GENA supports only a one way transmission in which the event message is transmitted to all control points connected to the UPnP network in a multicast scheme. Accordingly the GENA is not suitable for periodically transmitting and receiving two way binary data between the control point and the controlled device at a high speed. Consequently exchanging two way data between the control point and the controlled device using the SOAP and the GENA is inefficient and not fast enough.

The present invention is designed to address at least the problems and or disadvantages described above and to provide at least the advantages described below.

Accordingly an aspect of the present invention is to provide an apparatus and a method for exchanging two way data between UPnP devices using a UPnP at a high speed in real time.

Another aspect of the present invention is to provide an apparatus and a method for exchanging data between a vehicle head unit and a mobile device using a UPnP at a high speed in real time.

In accordance with an aspect of the present invention an apparatus is provided for exchanging data between UPnP based devices. The apparatus includes a controller for generating and transmitting an action for requesting a particular parameter to a controlled device and controlling such that a fast event data transmission path is established using information contained in a return when the return in response to the action for requesting the particular parameter is received from the controlled device and a fast event data bus module for establishing the fast event data transmission path according to a control of the controller and receiving fast event data.

In accordance with another aspect of the present invention an apparatus is provided for exchanging data between UPnP based devices. The apparatus includes a controlled unit for transmitting a return in response to an action for requesting a particular parameter when the action for requesting the particular parameter is received from a control point and controlling such that a fast event data transmission path is established with the control point and a fast event data bus module for establishing the fast event data transmission path according to a control of the control point and transmitting the fast event data.

In accordance with another aspect of the present invention a method is provided for exchanging data between UPnP based devices. The method includes generating and transmitting an action for requesting a particular parameter to a controlled device by a control point receiving a return in response to the action for requesting the particular parameter from the controlled device establishing a fast event data transmission path by using information contained in the return and receiving fast event data through the fast event data transmission path.

Various embodiments of the present invention will now be described in detail with reference to the accompanying drawings. In the following description specific details such as detailed configuration and components are merely provided to assist the overall understanding of these embodiments of the present invention. Therefore it should be apparent to those skilled in the art that various changes and modifications of the embodiments described herein can be made without departing from the scope and spirit of the present invention. In addition descriptions of well known functions and constructions are omitted for clarity and conciseness.

According to an embodiment of the present invention an apparatus it provided for exchanging data between UPnP based devices including a control point and a controlled device. The control point and the controlled device included in the apparatus for exchanging the data between the UPnP based devices may include any device which can exchange data based on the UPnP.

In this specification a vehicle head unit is installed in the vehicle in order to provide various types of entertainment in the vehicle and a mobile device such as a smart phone are described as examples of the control point and the controlled device. According to an embodiment of the present invention the vehicle head unit may be operated as the control point and the mobile device may be operated as the controlled device or the mobile device may be operated as the control point and the vehicle head unit may be operated as the controlled device.

Referring to a vehicle head unit exchanges data based on UPnP through an interworking with a mobile device . The vehicle head unit includes a vehicle manager or vehicle manageable device a telephony controller and a first fast event bus module .

The vehicle manager performs various types of functions within the vehicle. For example the vehicle manager performs a navigation function by receiving a Global Positioning Satellite GPS signal outputs a Digital Multimedia Broadcasting DMB radio signal or a DMB TV signal or performs mobile communication through a mobile communication antenna not shown . Further the vehicle manager can also perform a car audio and video functions and other functions provided by the vehicle.

The vehicle manager includes a vehicle data model for performing various types of functions within the vehicle. The vehicle data model stores parameter values for performing the navigation function the DMB function the mobile communication function and the car audio and video function and parameter values corresponding to events generated while the navigation function the DMB function the mobile communication function and the car audio and video function are performed.

The vehicle manager is a controlled unit when the vehicle head unit is operated as the controlled device and receives an action for requesting a particular parameter among the parameter values stored in the vehicle data model from a vehicle management controller of the mobile device which is operated as the control point.

When the vehicle manager receives a request for a particular parameter from the vehicle management controller of the mobile device the vehicle manager analyzes parameters within the corresponding request calculates values that can be transmitted and transmits a return indicating information on the values that can be transmitted.

After the vehicle manager transmits the return when the first fast event bus module and a second fast event bus module are connected to each other the vehicle manager transmits the values that can be transmitted among the particular parameter to the mobile device through a fast event data transmission path between the first fast event bus module and the second fast event bus module .

Further when the vehicle manager receives a request for a parameter transmission stop from the vehicle management controller the vehicle manager transfers a result informing of the parameter transmission stop to the vehicle management controller .

The telephony controller controls the controlled device when the vehicle head unit is operated as the control point and performs a control for receiving a particular parameter from a telephony server of the mobile device i.e. the controlled device.

Specifically the telephony controller generates a request for a particular parameter that the telephony controller desires to receive from the telephony server of the mobile device and transmits the generated request to the telephony server of the mobile device . When the telephony controller receives a return in response to the request from the mobile device the telephony controller receives fast event data i.e. a value provided among the requested particular parameter through the fast event data transmission path between the first fast event bus module and the second fast event bus module using information included in the return.

Further the telephony controller transmits a request for a parameter transmission stop to the telephony server when the parameter transmission stop is desired and receives a result informing of the parameter transmission stop from the telephony server .

For example the request for the particular parameter may be a Start Fast Event Query Action including a parameter name a parameter reception period type a parameter reception period a parameter reception duration type parameter reception duration and a Uniform Resource Locator URL value corresponding to a parameter reception address. Further the return in response to the request may be a Return Start Fast Event Query Action including an IDentifier ID for distinguishing parameters a parameter transmission period and parameter transmission duration.

When the first fast event bus module receives a fast event transmission path call signal from the second fast event bus module as the vehicle manager transmits the return in response to the action for requesting the particular parameter to the vehicle management controller the first fast event bus module is connected to the second fast event bus module according to the call signal. Further the first fast event bus module receives a value that can be transmitted among the particular parameter through the fast event data transmission path between the first fast event bus module and the second fast event bus module and provides the received value to the vehicle management controller of the mobile device .

The mobile device exchanges data based on the UPnP through an interworking with the head unit included in the vehicle not shown .

The mobile device includes the telephony server the vehicle management controller and the second fast event bus module . The telephony server performs various types of functions within the mobile device . For example the telephony server performs a telephony function through mobile communication an Internet browsing function a function for providing one or more application services or a function for reproducing audio and video.

The telephony server includes the telephony data model for performing various types of functions within the mobile device . The telephony data model stores parameter values required for performing a telephony function a function of transmitting receiving a Short Message Service SMS an internet browsing function and a function of providing one or more application services through various types of applications or a function of reproducing audio and video and parameter values corresponding to an event generated while the telephony function the SMS transmission reception function the internet browsing function various application service function and the audio and video reproduction function are performed.

When the mobile device is operated as the controlled device the telephony server may be the controlled unit that receives a request for a particular parameter among the parameter values stored in the telephony data model from the telephony controller of the vehicle head unit which is operated as the controller. When the telephony server receives the request the telephony server calculates values which can be transmitted by analyzing parameters within the corresponding request and transmits a return indicating information on the values which can be transmitted.

After the telephony server transmits the return when the first fast event bus module and the second fast event bus module are connected to each other the telephony server transmits the values that can be transmitted among the particular parameter to the vehicle head unit through the fast event data transmission path between the first fast event bus module and the second fast event bus module . Further when the parameter transmission stop is required the vehicle management controller transmits a request for the parameter transmission stop to the vehicle manager and receives a result informing of the parameter transmission stop from the vehicle manager .

For example the request for the particular parameter may be a Start Fast Event Query Action including a parameter name a parameter reception period type a parameter reception period a parameter reception duration type parameter reception duration and a URL value corresponding to a parameter reception address. Further the return may be a Return Start Fast Event Query Action including an ID for distinguishing parameters a parameter transmission period and parameter transmission duration.

When the second fast event bus module receives a fast event transmission path call signal from the first fast event bus module as the telephony server transmits the return in response to the request for the particular parameter to the telephony controller the second fast event bus module is connected to the first fast event bus module according to the call signal. Further the second fast event bus module receives the fast event data i.e. the particular parameter value through the fast event data transmission path between the first fast event bus module and the second fast event bus module .

Referring to the vehicle head unit performs an infotainment service by receiving parameter values for performing a telephony function an SMS transmission reception function an internet browsing function a function for providing various application services and an audio and video reproduction function in the telephony server of the mobile device through the telephony controller or parameter values corresponding to the event generated while the above described functions are performed.

More particularly the telephony controller generates the Start Fast Event Query Action for requesting a parameter that the telephony controller desires to receive from the telephony server of the mobile device and transmits the Start Fast Event Query Action to the telephony server of the mobile device in step .

For example the Start Fast Event Query Action includes the parameter name ParameterName the parameter reception period type PeriodType the parameter reception period Period the parameter reception duration type the parameter reception duration Duration and the URL value corresponding to the parameter reception address as shown in Table 1 below.

When the Start Fast Event Query Action is received the telephony server analyzes the requested parameter based on the requested parameter value calculates parameter values that can be transmitted selects a parameter transmission period and parameter transmission duration for the transmission parameter and generates a query ID to identify the requested parameter value in step .

In step the telephony server transmits the return indicating transmission information on the parameter that can be transmitted i.e. the Return Start Fast Event Query Action to the telephony controller in response to the Start Fast Event Query Action.

For example the Return Start Fast Event Query Action includes the ID Query ID the parameter transmission period Period and the parameter transmission duration Duration as shown in Table 2 below.

The telephony controller identifies a transmission period and transmission duration during which the telephony server transmits a parameter from the received Return Start Fast Event Query Action.

In step after transmitting the Return Start Fast Event Query Action to the telephony controller the telephony server identifies the fast event data transmission path through which the parameter is to be transmitted. For example the telephony server identifies whether or not a fast event data path was pre connected between the vehicle head unit and the mobile device .

When there is no connected fast event data path in step the telephony server calls the Fast Event Bus URL included in the Start Fast Event Query Action through the second fast event bus module and connects the second fast event bus module with the first fast event bus module such that the fast event data path is established.

In step the telephony server transmits the fast event data i.e. a Query ID for distinguishing parameters and a Data Value corresponding to the corresponding parameter value to the vehicle head unit through the fast event data path.

In the data transmission a related stack may be configured such that a TCP or a User Datagram Protocol UDP packet is based on an IP and transmission data can be expressed using a string value such as binary values of the Query ID and the Data Value or the XML value as shown in Table 3.

When the telephony controller desires to stop fast event data communication while receiving the data value corresponding to the parameter through the fast event data path the telephony controller transmits a Stop Fast Event Query Action to the telephony server in step . For example the Stop Fast Event Query Action includes a Query ID value for the event desired to be stopped.

When the telephony server receives the Stop Fast Event Query Action the telephony server stops transmitting data and transmits a data transmission stop result to the telephony controller in step . Accordingly the data transmission is stopped.

Referring to the mobile device performs various types of infotainment services by periodically and quickly receiving a desired parameter among parameter values corresponding to an event generated while the navigation function the DMB function the mobile communication function and the car audio and video function in the vehicle manager of the vehicle head unit through the vehicle management controller .

Accordingly the vehicle management controller generates a Start Fast Event Query Action requesting a parameter desired to be received from the vehicle manager of the vehicle head unit and transmits the Start Fast Event Query Action to the vehicle manager in step .

For example the Start Fast Event Query Action includes the parameter name ParameterName the parameter reception period type PeriodType the parameter reception period Period the parameter reception duration type and the parameter reception duration Duration . The parameter reception address URL Fast Event Bus URL value may be included in the Return Start Fast Event Query Action. For example the Start Fast Event Query Action may include values as shown in Table 4 below.

When receiving the Start Fast Event Query Action the vehicle manager analyzes the requested parameter based on the requested parameter value calculates the parameter value that can be transmitted selects the parameter transmission period and the parameter transmission duration for the transmission parameter and generates the Query ID for identifying the requested parameter value in step .

In step the vehicle manager transmits the Return indicating transmission information on the parameter that can be transmitted in response to the Start Fast Event Query Action i.e. the Return Start Fast Event Query Action to the vehicle management controller .

For example the Return Start Fast Event Query Action includes the Query ID for distinguishing parameters the parameter transmission period Period the parameter transmission duration Duration and the parameter transmission address URL Fast Event Bus URL as shown in Table 5 below.

The vehicle management controller identifies a transmission period and transmission duration during which the vehicle manager transmits a parameter from the received Return Start Fast Event Query Action. Particularly the vehicle management controller identifies the URL address for connecting the Fast Event data path.

When the vehicle management controller receives the Return Start Fast Event Query Action the vehicle management controller identifies the Fast Event data transmission path through which the parameter is to be transmitted in step . For example the vehicle management controller identifies whether or not a Fast Event data path was pre connected between the vehicle head unit and the mobile device .

When there is no connected fast event data path the vehicle management controller calls the Fast Event Bus URL included in the Return Start Fast Event Query Action through the second fast event bus module and connects the second fast event bus module with the first fast event bus module so that the fast event data path is established in step .

When the fast event data path is established the vehicle manager transmits the fast event data i.e. the Query ID for distinguishing parameters and the Data Value corresponding to the corresponding parameter value to the vehicle head unit through the fast event data path in step .

Referring to a TCP or a UDP packet is based on an IP and transmission data is expressed using a string value such as a binary value of the Query ID and the Data Value or an XML value as shown in Table 6.

As described above when the vehicle management controller desires to stop fast event data communication while receiving the data value corresponding to the parameter through the fast event data path in step the vehicle management controller transmits the Stop Fast Event Query Action to the vehicle manager .

At this time the Stop Fast Event Query Action may contain a Query ID value for the event desired to be stopped.

When the Stop Fast Event Query Action is received the vehicle manager stops transmitting the data and transmits a result of the data transmission stop to the vehicle management controller . Accordingly the data transmission is stopped.

Based on the apparatus and the method for exchanging the data between the UPnP devices according to the above described embodiments of the present invention two way data exchange is provided between devices through a fast event transmission path by using the UPnP protocol at a high speed in real time thus providing a more convenient IT service through an interworking between different devices based on the UPnP.

Further according to the above described embodiments of the present invention data exchange between the vehicle head unit and the mobile device is provided through a fast event transmission path at a high speed in real time thus providing an efficient infotainment service.

While the present invention has been shown and described with reference to certain embodiments thereof various modifications can be implemented without departing the scope of the present invention. For example although the above described embodiments of the present invention refer to the vehicle head unit and the mobile device as examples of the devices any device supporting the UPnP can be applied to the present invention. Accordingly it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present invention as defined by the appended claims and their equivalents.

