---

title: Method and apparatus for distributing video under multi-channel, and video management system using the same
abstract: The present disclosure provides a multi-channel video distribution method and apparatus, and a video management system using the same, including a client system to communicate with a standardized video providing apparatus or a non-standardized video providing apparatus, and to receive a video/sound signal from the standardized video providing apparatus or the non-standardized video providing apparatus; a transcode system to convert the video/sound signal, received by the client system, to a video/sound format that is requested in a client application; and a server system to communicate with the client application, and to transmit, to the client application, the video/sound signal that is converted by the transcode system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09100674&OS=09100674&RS=09100674
owner: LG CNS CO., LTD.
number: 09100674
owner_city: Seoul
owner_country: KR
publication_date: 20120321
---
This application is based on and claims priority under 35 U.S.C. 119 from Korean Patent Application No. 10 2011 0075291 filed on Jul. 28 2011 with the Korean Intellectual Property Office the disclosure of which is incorporated herein in its entirety by reference.

The present disclosure relates to a video management system and more particularly to a multi channel video distribution method and apparatus that may receive video sound signals from standardized video providing apparatuses or non standardized video providing apparatus of various companies and convert the received video sound signals to a standardized output format.

Recently in places such as banks government offices group houses and the like that require high security and need to centrally and intensively manage a large area there is an increasing necessity of a video management system to prevent the occurrence of an incident such as a criminal act or a state of emergency and to verify circumstances of an incident if an incident occurs.

As shown in the video management system in the related art includes at least one closed circuit television CCTV camera installed in remote places that are required to be monitored a video distribution apparatus connected to each CCTV camera in a wired manner and a client application connected to the video distribution apparatus over a communication network.

The CCTV camera transfers an obtained video sound signal to the video distribution apparatus through a wired cable and the video distribution apparatus transmits the received video sound signal to the client application over the communication network.

The client application is connected to the video distribution apparatus to perform search and playback of various types of video sound signals stored in the video distribution apparatus and controls an operation of the video distribution apparatus in a remote place using various types of control signals. In addition the client application may directly request the CCTV camera which the client application desires to manage for streaming and thereby receive a sound video signal obtained by the CCTV camera .

However when a different type of CCTV camera is added in the video management system of the related art all of client applications need to be corrected since a streaming scheme is different for each company. Further a video audio codec used for each company is different. Therefore unless a dedicated application is assigned for each company the added CCTV camera may not be readily compatible with the existing CCTV cameras.

In addition in the video management system of the related art the client application causes the waste of bandwidth by individually requesting each CCTV camera for streaming and when a size of a received video is not a size desired by each client application the received video is converted to a size required in an application end whereby load occurs in the client application.

Moreover a storage storing video signals uses a different scheme for each company which may become a single problematic factor in unifying a system. In addition two folds of bandwidth are used for storing video signals and thus system resources may be wasted.

The present disclosure has been made in an effort to provide a multi channel video distribution method and apparatus that may maintain the existing compatibility even though a different type of a video providing apparatus is added and a video management system using the same.

The present disclosure has been made in an effort to provide a multi channel video distribution method and apparatus that may maintain the compatibility with respect to a codec which is different for each company while not employing additional correction of a client application but using the existing client application and a video management system using the same.

The present disclosure has been made in an effort to provide a multi channel video distribution method and apparatus that may minimize the unnecessary waste of bandwidth and a video management system using the same.

The present disclosure has been made in an effort to provide a multi channel video distribution method and apparatus that may readily perform expansion and compatibility with another system by unifying a storage and a video management system using the same.

An exemplary embodiment of the present disclosure provides a multi channel video distribution apparatus including a client system to communicate with a standardized video providing apparatus or a non standardized video providing apparatus and to receive a video sound signal from the standardized video providing apparatus or the non standardized video providing apparatus a transcode system to convert the video sound signal received by the client system to a video sound format that is requested in a client application and a server system to communicate with the client application and to transmit to the client application the video sound signal that is converted by the transcode system.

Another exemplary embodiment of the present disclosure provides a multi channel video distribution method including communicating by a client system with a standardized video providing apparatus or a non standardized video providing apparatus receiving by the client system a video sound signal from the standardized video providing apparatus or the non standardized video providing apparatus converting by a transcode system the video sound signal received by the client system to a video sound format that is requested in a client application and transmitting by a server system to the client application the video sound signal that is converted by the transcode system.

Yet another exemplary embodiment of the present disclosure provides a video management system including a video providing apparatus including at least one of a standardized video providing apparatus and a non standardized video providing apparatus at least one client application to request a video photographed by the video providing apparatus and a multi channel video distribution apparatus to communicate with the video providing apparatus to convert a video sound signal received from the video providing apparatus to a video sound format that is requested in the client application and to thereby transmit the converted video sound signal to the client application.

According to the exemplary embodiments of the present disclosure there is provided a multi channel video distribution apparatus installed with an application programming interface API for each company. Therefore the compatibility with a different type of product is maintained and a video management system is readily modified.

According to the exemplary embodiments of the present disclosure there are provided a multi channel video distribution method and apparatus for converting a codec different for each company to a standard format. Therefore a product applied with a standard client application that follows an open network video interface forum ONVIF standard is compatible regardless of a manufacturer of the product.

According to the exemplary embodiments of the present disclosure there are provided a multi channel video distribution method and apparatus for resizing a video size to be suitable for each client application. Therefore it is possible to prevent the unnecessary waste of bandwidth and to expand the bandwidth to a broadband wider than an existing management scale.

According to the exemplary embodiments of the present disclosure there are provided a multi channel video distribution method and apparatus for streaming a video sound signal stored in a storage via a storage interface. Therefore a separate additional apparatus for storing the video sound signal is not required.

According to the exemplary embodiments of the present disclosure there are provided a video distribution method and apparatus including an analytics function. Therefore it is possible to decrease load in a client application.

The foregoing summary is illustrative only and is not intended to be in any way limiting. In addition to the illustrative aspects embodiments and features described above further aspects embodiments and features will become apparent by reference to the drawings and the following detailed description.

In the following detailed description reference is made to the accompanying drawing which form a part hereof. The illustrative embodiments described in the detailed description drawing and claims are not meant to be limiting. Other embodiments may be utilized and other changes may be made without departing from the spirit or scope of the subject matter presented here.

In the present disclosure an open network video interface ONVIF protocol indicates a standard protocol designated by an ONVIF working on a network video security equipment and international standard in order to solve a protocol incompatibility issue of an Internet protocol IP camera.

In the exemplary embodiments of the present disclosure a standardized video providing apparatus or a standardized client application refers to an apparatus that follows the ONVIF protocol and a non standardized video providing apparatus or a non standardized client application refers to an apparatus that does not follow the ONVIF protocol.

Referring to the video management system according to the present disclosure includes at least one video providing apparatus a multi channel video distribution apparatus at least one client application and the like.

The video providing apparatus includes a standardized video providing apparatus or a non standardized video providing apparatus and converts a provided photographed video to a video sound i.e. audio visual A V signal. Here the video providing apparatus may be a surveillance camera a broadcasting server providing a broadcasting service a content providing server providing video content and the like.

The multi channel video distribution apparatus communicates with the video providing apparatus converts the video sound signal received from the video providing apparatus to a video sound format that is requested in the client application and then transmits the converted video sound signal to the client application . Here the multi channel video distribution apparatus communicates with the non standardized video providing apparatus via an application programming interface API .

When the client application is a non standardized client application the multi channel video distribution apparatus provides the client application with a service address for providing the video sound signal that is requested in the client application . Here the multi channel video distribution apparatus provides the client application with a different service address based on a protocol scheme with the client application and a video providing apparatus and a video sound format that are requested in the client application .

The multi channel video distribution apparatus may store in a storage as a file format the video sound signal received from the video providing apparatus or may convert to a streaming the video sound signal that is stored in the storage and thereby transmit the converted video sound signal to the client application in response to a request of the client application .

The multi channel video distribution apparatus may detect an event from the video sound signal received from the video providing apparatus using a predetermined detection algorithm and may transmit the detected event to the client application .

Similar to the video providing apparatus the client application may be a standardized client application or a non standardized client application. The client application may be connected to the multi channel video distribution apparatus to request a video of a desired video providing apparatus and to receive a video sound signal of the corresponding video providing apparatus over the multi channel video distribution apparatus . Here the client application may request a video of the video providing apparatus by setting various resolutions based on the video sound format and the screen segmentation.

Referring to the multi channel video distribution apparatus according to the present disclosure includes a client system a server system a transcode system a storage system a server hub and the like.

The client system communicates with a standardized video providing apparatus or a non standardized video providing apparatus and receives a video sound signal from the video providing apparatus . Here the client system communicates with the non standardized video providing apparatus via an API.

The server system communicates with the client application and transmits to the client application the video sound signal converted by the transcode system in response to a request of the client application . Here when the client application is a non standardized client application the server system provides the client application with a service address for providing the video sound signal requested in the client application and thereby transmits to the client application the video sound signal converted by the transcode system .

In response to a request of an operating terminal not shown the server system performs setting and control of the multi channel video distribution apparatus . Specifically in response to the request of the operating terminal the server system may set an IP address of the video providing apparatus an IP address of the multi channel video distribution apparatus an IP address of an input output end a video conversion scheme and the like.

The transcode system converts the video sound signal received from the video providing apparatus over the client system to the video sound format that is requested in the client application . Here the transcode system may transmit the converted video sound signal to the client application over the server system or may directly transmit the converted video sound signal to the client application . Accordingly it is possible to prevent load from occurring in the server system due to excessive data transmission.

The transcode system may detect an event from the video sound signal received from the video providing apparatus using a predetermined detection algorithm such as motion recognition video recognition and the like and may transmit the detected event to the client application .

The storage system stores in the storage as a file format the video sound signal that is received from the video providing apparatus or reads the video sound signal stored in the storage . Here the storage may be a storage such as a storage area network SAN a network attached storage NAS and the like and is connected to the storage system via an external switch .

The storage system may store a list of video sound signals stored in the storage and may provide the list to the client application when a request of the client application is received.

The server hub functions to maintain a transmission control protocol Internet protocol TCP IP connection within the multi channel video distribution apparatus and to perform switching between apparatuses within the multi channel video distribution apparatus .

Referring to the client system according to the present disclosure includes a network video client NVC module an API module a streaming real time streaming protocol real time transport protocol RTSP RTP streaming module local area network LAN modules and and the like.

The NVC module is a standard client module defined in the ONVIF and functions to communicate with a standardized video providing apparatus that follows the ONVIF standard.

The API module includes an API that supports a variety of protocols including a transmission control protocol TCP a user datagram protocol UDP an RTP a real time transport control protocol RTCP an RTSP and the like and functions to communicate with the non standardized video providing apparatus via the API. Accordingly a video providing apparatus of a new company may be easily added via the API.

The streaming module functions to transmit to the inside using a predetermined protocol a video that is received using a protocol different for each company. Specifically the streaming module transmits to the inside using an RTSP RTP protocol the video that is received using the protocol different for each company.

The LAN modules and include an input end that is connected to the video providing apparatus and an output end that is connected to an internal apparatus. The LAN modules and may be used and expanded in various networks due to a free IP setting.

Referring to the server system according to the present disclosure includes a network video transmitter NVT module a common gateway interface CGI module a streaming RTSP RTP streaming module LAN modules and and the like.

The NVT module performs a functionality of a server that follows the ONVIF standard and communicates with the client application to thereby perform a video sound setting and other settings for example an IP address and the like . The NVT module performs a functionality of an event server that processes an internally occurring event for example preparation suspension and the like of the video providing apparatus and transmits the occurring event to the client application .

The CGI module functions to set and control the multi channel video distribution apparatus in response to a command of the operating terminal. Specifically in response to the command of the operating terminal the CGI module sets an IP address of the video providing apparatus an IP address of the multi channel video distribution apparatus an IP address of input output ends a video conversion scheme and the like.

The streaming module transmits the video sound signal to the client application to be suitable for the protocol of the client application .

The LAN modules and include an input end that is connected to an internal apparatus and an output end that is connected to the client application . The LAN modules and may be used and expanded in various networks due to a free IP setting.

Referring to the transcode system according to the present disclosure includes a transcoder module an analytics module a streaming RTSP RTP streaming module LAN modules and and the like.

The transcoder module converts a video sound signal received from the video providing apparatus over the client system to a video sound format that is requested in the client application . In response to a request of the client application the transcoder module may change a resolution of the video sound signal received from the video providing apparatus .

The analytics module detects an event from the video sound signal received from the video providing apparatus using a predetermined detection algorithm such as motion recognition video recognition and the like and transmits the detected event to the client application . Therefore the multi channel video distribution apparatus according to the present disclosure may perform monitoring of a loiterer detecting of an intruder facial recognition and the like.

The streaming module may transmit to the server system through an input end the video sound signal converted by the transcoder module and thereby transmit the converted video sound signal to the client application or may directly transmit to the client application through an output end the video sound signal that is converted by the transcoder module .

The LAN modules and include the input end that is connected to an internal apparatus and the output end that is connected to the client application . The LAN modules and may be used and expanded in various networks due to a free IP setting.

Referring to the storage system according to the present disclosure includes a file manager module a streaming RTSP RTP streaming module a database DB module a storage interface I F module a LAN module and the like.

The file manager module functions to store in the storage such as a SAN or a NAS as a file format a video sound signal received from the video providing apparatus or to read the video sound signal stored in the storage . Here the file manager module extracts a header from the video sound signal received from the video providing apparatus and stores the received video sound signal as a file format for each date and each time.

The streaming module converts to a streaming the video sound signal that is read from the storage and transmits the converted video sound signal to the transcode system .

The DB module manages a list of video sound signals stored in the storage as a DB and provides the DB when a request of the client application is received.

The storage I F module is connected to the external switch to mount a file system from the storage and thereby enable a read write function. Here the storage I F module may be a SAN I F module or a NAS I F module according to a type of the storage .

The LAN module is connected to an internal apparatus. The LAN module may be used and expanded in various networks due to a free IP setting.

Referring to in light of the client system communicates with the video providing apparatus including a standardized video providing apparatus or a non standardized video providing apparatus S . Here the client system communicates with the non standardized video providing apparatus via an API.

Next the server system determines whether the client application is a standardized client application or a non standardized client application S .

When the client application is the standardized client application the transcode system converts the sound video signal received from the video providing apparatus to a video sound format that is requested in the client application in response to a request of the client application S .

Next the server system transmits to the client application the video sound signal that is converted by the transcode system S .

When the client application is determined as the non standardized client application in operation S the server system provides to the client application a service address for providing the video sound signal that is requested in the client application S and then sequentially proceeds operations S and S through communication with the client application .

Additionally even though not illustrated in the figures the multi channel video distribution method may further include an operation of storing by the storage system in the storage as a file format the video sound signal that is received from the video providing apparatus .

The multi channel video distribution method may further include an operation of detecting by the transcode system an event from the video sound signal received from the video providing apparatus using a predetermined detection algorithm and transmitting the detected event to the client application .

From the foregoing it will be appreciated that various embodiments of the present disclosure have been described herein for purposes of illustration and that various modifications may be made without departing from the scope and spirit of the present disclosure. Accordingly the various embodiments disclosed herein are not intended to be limiting with the true scope and spirit being indicated by the following claims.

