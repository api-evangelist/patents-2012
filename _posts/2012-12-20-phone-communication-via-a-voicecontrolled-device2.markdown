---

title: Phone communication via a voice-controlled device
abstract: A device that includes a microphone and a speaker may capture audio uttered by a user. The device, or another device, may then perform a particular operation in response to the captured audio. A user's cell phone number may be associated with the device. When an incoming call is directed to the user's cell phone, the device may generate a notification. The user may utter a command that causes the device to establish an audio connection with a cellular carrier network, thereby facilitating the phone conversation while bypassing the cell phone. Similarly, a user may make an outgoing call associated with the user's cell phone. The outgoing call is facilitated through an audio connection between the device and the cellular carrier network, bypassing the cell phone.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09641954&OS=09641954&RS=09641954
owner: Amazon Technologies, Inc.
number: 09641954
owner_city: Seattle
owner_country: US
publication_date: 20121220
---
This application claims priority to U.S. Provisional Patent Application Ser. No. 61 679 460 entitled Phone Communication Via a Voice Controlled Device which was filed on Aug. 3 2012 and which is incorporated by reference herein.

There are various means for voice communication between individuals including cell phones voice over IP VoIP services landline phones and so on. In addition homes are becoming more wired and connected with the proliferation of computing devices such as desktops tablets entertainment systems and portable communication devices. As computing devices evolve many different ways have been introduced to allow users to interact with these devices such as through mechanical means e.g. keyboards mice etc. touch screens motion and gesture. Another way to interact with computing devices is through speech.

This disclosure describes in part techniques for enabling phone communication using a voice controlled assistant VCA . For instance a VCA may be implemented as a device that includes a microphone and a speaker and that is communicatively distinct from a user s cell phone. The VCA may receive notification of an incoming call being received at a user s cell phone and enable a user to accept the call through the device. Similarly the device may initiate an outbound call in association with the user s cell phone. The device may utilize a network accessible or cloud based service to establish communication with a cellular carrier network to enable communication between the VCA and another user device. In an example implementation the VCA may communicate with the cellular carrier network via a voice over IP VoIP connection.

The devices and techniques described herein may be implemented in a variety of different architectures and contexts. One non limiting and illustrative implementation is described below.

Generally the voice controlled assistant has at least one microphone and at least one speaker to facilitate audio interactions with the user and or other users. In some instances the voice controlled assistant is implemented without a haptic input component e.g. keyboard keypad touch screen joystick control buttons etc. or a display. In certain implementations a limited set of one or more haptic input components may be employed e.g. a dedicated button to initiate a configuration power on off etc. . Nonetheless the primary and potentially only mode of user interaction with the electronic assistant may be through voice input and audible output. One example implementation of the voice controlled assistant is provided below in more detail with reference to .

The microphone of the voice controlled assistant detects audio from the environment such as sounds uttered from the user . As illustrated the voice controlled assistant includes a processor and memory which stores or otherwise has access to a speech recognition engine . As used herein a processor may include multiple processors and or a processor having multiple cores. The speech recognition engine performs speech recognition on audio captured by the microphone such as utterances spoken by the user . The voice controlled assistant may perform certain actions in response to recognizing different speech from the user . The user may speak predefined commands e.g. Awake Sleep or may use a more casual conversation style when interacting with the assistant e.g. I d like to go to a movie. Please tell me what s playing at the local cinema. .

In some instances the voice controlled assistant may operate in conjunction with or may otherwise utilize computing resources that are remote from the environment . For instance the voice controlled assistant may couple to the remote computing resources over a network . As illustrated the remote computing resources may be implemented as one or more servers . . . P and may in some instances form a portion of a network accessible computing platform implemented as a computing infrastructure of processors storage software data access and so forth that is maintained and accessible via a network such as the Internet. The remote computing resources do not require end user knowledge of the physical location and configuration of the system that delivers the services. Common expressions associated for these remote computing devices include on demand computing software as a service SaaS platform computing network accessible platform cloud services data centers and so forth.

The servers P include a processor and memory which may store or otherwise have access to some or all of the components described with reference to the memory of the voice controlled assistant . For instance the memory may have access to and utilize the speech recognition engine or another speech recognition engine for receiving audio signals from the assistant recognizing speech and potentially causing performance of an action in response. In some examples the voice controlled assistant may upload audio data to the remote computing resources for processing given that the remote computing resources may have a computational capacity that far exceeds the computational capacity of the voice controlled assistant . Therefore the voice controlled assistant may utilize the speech recognition engine at the remote computing resources for performing relatively complex analysis on audio captured from the environment .

Regardless of whether the speech recognition occurs locally or remotely from the environment the voice controlled assistant may receive vocal input from the user and the assistant and or the resources may perform speech recognition to interpret a user s operational request or command. The requests may be for essentially any type of operation such as database inquires requesting and consuming entertainment e.g. gaming finding and playing music movies or other content etc. personal management e.g. calendaring note taking etc. online shopping financial transactions telephone communication and so forth.

The voice controlled assistant and the remote computing resources may communicatively couple to the network via network interface and network interface respectively using wired technologies e.g. wires USB fiber optic cable etc. wireless technologies e.g. RF cellular satellite Bluetooth etc. or other connection technologies. The network is representative of any type of communication network including data and or voice network and may be implemented using wired infrastructure e.g. cable CAT5 fiber optic cable etc. a wireless infrastructure e.g. RF cellular microwave satellite Bluetooth etc. and or other connection technologies.

In addition to communicating with each other over the network the VCA and the computing resources may also each communicate with a cell carrier over the network to enable telephone communication using the VCA .

As illustrated the memory of the voice controlled assistant also stores or otherwise has access to a user identification engine which functions to identify a user that utters an audible command.

Upon receiving audio within the environment the speech recognition engine may first attempt to identify whether or not the audio contains speech such as speech from the user . If so then the speech recognition engine may perform automatic speech recognition ASR on the audio and may perform an action corresponding to any command from the audio. For instance in the illustrated example when an incoming call is being signaled by the user s cell phone and the VCA the user issues a command requesting that the voice controlled assistant answer the incoming phone call. As such the speech recognition engine may identify this command and the voice controlled assistant answers the incoming call.

In addition and as illustrated the voice controlled assistant may output a response after performing the speech recognition. For instance the voice controlled assistant may output an indication that the assistant will comply with the request with this indication being audible visual or the like. Here for instance the voice controlled assistant audibly outputs the response indicating that the voice controlled assistant will answer the phone call as requested. In the illustrated example the audible response also includes the caller s name which may be extracted from caller ID information.

In the illustrated implementation the voice controlled assistant includes the processor and memory . The memory may include computer readable storage media CRSM which may be any available physical media accessible by the processor to execute instructions stored on the memory. In one basic implementation CRSM may include random access memory RAM and Flash memory. In other implementations CRSM may include but is not limited to read only memory ROM electrically erasable programmable read only memory EEPROM or any other medium which can be used to store the desired information and which can be accessed by the processor .

The voice controlled assistant includes one or more microphones to receive audio input such as user voice input and one or more speakers to output audio sounds. A codec is coupled to the microphone and speaker to encode and or decode the audio signals. The codec may convert audio data between analog and digital formats. A user may interact with the assistant by speaking to it and the microphone captures the user speech. The codec encodes the user speech and transfers that audio data to other components. The assistant can communicate back to the user by emitting audible statements through the speaker . In this manner the user interacts with the voice controlled assistant simply through speech without use of a keyboard or display common to other types of devices.

In the illustrated example the voice controlled assistant includes a wireless interface coupled to an antenna to facilitate a wireless connection to a network. The wireless interface may implement one or more of various wireless technologies such as wifi Bluetooth RF and so on.

The assistant may also include one or more device interfaces to facilitate a wired connection to a network or a plug in network device that communicates with other wireless networks. The interfaces may comprise a USB port and or other forms of wired connections such as a broadband connection. A power unit is further provided to distribute power to the various components on the assistant .

The voice controlled assistant is designed to support audio interactions with the user in the form of receiving voice commands e.g. words phrase sentences etc. from the user and outputting audible feedback to the user. Accordingly in the illustrated implementation there are no haptic input devices such as navigation buttons keypads joysticks keyboards touch screens and the like. Further there is no display for text or graphical output. In one implementation the voice controlled assistant may include non input control mechanisms such as basic volume control button s for increasing decreasing volume as well as power and reset buttons. There may also be a simple light element e.g. LED to indicate a state such as for example when power is on. But otherwise the assistant does not use or need to use any input devices or displays in some instances.

Several modules such as instructions datastores and so forth may be stored within the memory and configured to execute on the processor . An operating system module is configured to manage hardware and services e.g. wireless unit USB Codec within and coupled to the assistant for the benefit of other modules.

In addition the memory may include the speech recognition engine the user identification engine and the network interface discussed above. Also as discussed above some or all of the engines data stores and components may reside additionally or alternatively at the remote computing resources .

As described below a voice controlled assistant e.g. the assistants described above may be used to conduct both inbound and outbound phone calls. In one example a user receives a call on his cell phone while at home or at any other location that includes a voice controlled assistant VCA . The user is able to answer the call from either the voice controlled assistant by issuing a voice command e.g. Assistant answer phone or by selecting the answer key on his cell phone. If the user answers via the voice controlled assistant the user is able to conduct the phone call on the voice controlled device . If the user answers the call on his cell phone the user is able to conduct the phone call on the cell phone.

Various methods may be used to control an audible ringing of the voice controlled assistant to indicate an incoming call. One approach is to have the voice controlled assistant audibly ring when the user s cell phone is in close proximity to the voice controlled assistant . Another approach involves silently ringing the voice controlled assistant regardless of whether the voice controlled assistant and cell phone are in close proximity of each other.

In another example the user may place an outbound call via the voice controlled assistant by speaking a voice command e.g. Assistant call Bob . The call is placed across a cellular carrier network and the caller ID on the receiving user s phone may show the user s cell phone number.

In order to support phone calls made or received via the voice controlled assistant the assistant may integrate with a cellular carrier . In an example implementation the cellular carrier includes functionality to simultaneously signal both the voice controlled assistant and the cell phone that there is an incoming call and enable the user to answer the call from either the voice controlled assistant or the cell phone.

For outbound calls the cellular carrier includes functionality to connect an outbound call from a voice controlled assistant to the dialed number. In an example implementation the cellular carrier includes the costs for the inbound or outbound call when billing for the user s cell phone. For example monthly minutes and charges for the call would appear in a user s monthly cell phone bill.

The provisioning interface enables a user to associate the voice controlled assistant with a cell phone number so that the voice controlled assistant can ring when the user s cell phone rings. For example as part of a setup process the user submits his or her cell phone number to a cloud based service which may be implemented as part of remote computing resources . The cloud based service in turn submits the phone number to the cell carrier via the provisioning interface . In an example implementation the cellular carrier will attempt to confirm the request directly with the user via the user s cell phone. When the user confirms or denies the request the cell carrier sends a response back to the cloud based service via the provisioning interface . The provisioning interface may be implemented as a REST HTTP based API which may be developed managed and maintained by the cellular carrier . Software residing in the cloud based service that communicates with the provisioning interface may be implemented by an entity providing the cloud based service .

The signaling interface enables notification of an incoming call to be signaled through both the cell phone and the voice controlled assistant . In an example implementation when a user who has also confirmed his provisioning request as described above receives a phone call on his cell phone the cellular carrier will simultaneously signal the cell phone and the cloud based service via the signaling interface . When the cloud based service receives this signal via the signaling interface the cloud based service will communicate directly with the specific voice controlled assistant corresponding to the user s cell phone number.

In an example implementation the user s cell phone number may be associated with multiple voice controlled assistants. In such a scenario each of the voice controlled assistants associated with the user s cell phone number may be notified of an incoming call. Alternatively notification will be sent to the voice controlled assistant associated with the cell phone that is nearest in proximity to the cell phone. If the user wants to answer via the voice controlled assistant the cloud based service will signal the cellular carrier via the signaling interface that the call should be routed to the voice controlled assistant .

For outbound calls requested via the user s voice controlled assistant the same signaling interface may be used to indicate from the cloud based service to the cell carrier that the user wants to place an outbound call. When the dialed party answers the request the cellular carrier will signal to the cloud based service that the call has been answered. In an example implementation the signaling interface may also pass along information to the voice controlled assistant via the cloud based service indicating an IP address where the voice controlled assistant is to connect to the cell carrier to enable the phone communication.

In an example implementation the signaling interface may be implemented using an open standards based protocol such as XMPP to enable signaling between the cloud based service and the cellular carrier . The cellular carrier may be responsible for implementing software to enable the cellular carrier to communicate via this interface. Similarly an entity associated with the cloud based service may be responsible for implementing software residing in the cloud based service and or the voice controlled assistant that communicates with the signaling interface .

The audio interface enables audio e.g. a phone conversation to be transmitted between the voice controlled assistant and the cellular carrier . In an example implementation once an inbound or outbound call has been signaled and either the voice controlled assistant answers for inbound or the dialed party answers for outbound calls the voice controlled assistant will directly connect to the IP address specified via the signaling interface as described above and begin to stream audio. Through the audio interface the actual audio conversation between the voice controlled assistant user and another party is transmitted.

When a call is established between the user and another user through the other user s phone the cell carrier may manage the call over various communication paths. For example the cell carrier acts as a middle man to manage the communication between the devices of the two users. Communication between the cell carrier and the other user s phone may be handled over any type of communication path for example a 3G or 4G cellular network . Alternatively depending on the type of device used by the other user other types of communication networks may be used.

Communication between the cell carrier and the devices of user may be carried over different communication paths depending on the device that is currently being used. For example if the user is using their cell phone the communication may be handled over a 3G or 4G cellular network . If the user is using their voice controlled assistant to participate in the telephone call the communication may be handled over a voice over IP network path .

In an example implementation the system may be configured to enable a single phone call to be handled simultaneously over both the cellular network and the VoIP network . In this scenario a first user can participate in the call using the user s cell phone while another user can participate in the same call using the voice controlled assistant .

In an example implementation the cell carrier further manages behavior of the user s devices during a call. For example while a phone call is being conducted via the VCA the user s cell phone to which the VCA is bound is configured to prevent the user from making an outbound call from the cell phone. In this way a single phone number which is associated with both the cell phone and VCA can only participate in a single phone call at any given time.

Similarly while a phone call is being conducted via the VCA if another incoming call directed to the same phone number is received even though the cell phone is not actively participating in the call the calling party will hear a busy signal and or will be routed to voicemail.

At a cloud based service receives a user request to bind a cell phone number to a voice controlled assistant. For example the user may complete and submit to the cloud based service a web based form through which the cell phone number and an ID associated with the voice controlled assistant are specified. Other techniques may also be used to request a binding including but not limited to for example the user submitting the request directly to the cellular carrier through a website via a phone call via a text message or the like or the user entering a voice command through the VCA specifying a cell phone number to which the VCA is to be bound.

In an example implementation the ID associated with the voice controlled assistant may be a device ID specific to the particular VCA. Alternatively the ID associated with the voice controlled assistant may be an IP address or some other type of device specific identifier.

At the cloud based service authenticates the request. For example the cloud based service may employ any of a number of techniques to confirm that the user entered the correct phone number. In one implementation the cloud based service may send an SMS message to the phone number entered on the form and wait for a reply. The reply may be in any of a variety of forms including but not limited to a reply SMS message or submission of another form with a code that was included in the SMS message from the cloud based service. Alternatively the cloud based service may place a call to the specified phone number and request that the user enter a security code that is specifically associated with the user of the cell phone. This level of authentication may be used to confirm that the user is in possession of the phone associated with the submitted cell phone number.

At a determination is made as to whether or not the authentication was successful. For example if an accurate response to the authentication SMS message or call is received then the authentication is deemed successful. On the other hand if an inaccurate response is received or no response is received within a threshold time limit then the authentication is deemed unsuccessful.

If the authentication at is deemed unsuccessful then the process terminates. If the authentication at is deemed successful then the process continues at .

At the cloud based service sends the binding request including the cell phone number and the VCA ID to the cell carrier . For example the binding request may be sent over the network from the remote computing resource to the cell carrier .

At the cell carrier authenticates the request. For example the cell carrier may employ any of a number of techniques to confirm that the phone number specified in the request belongs to the user and is authorized to be bound to the particular VCA. In one implementation the cell carrier may access a data store that maintains associations between VCAs and cell phone numbers to confirm that the specified VCA and cell phone number are associated with one another.

If the authentication at is deemed unsuccessful then the process terminates. If the authentication at is deemed successful then the process continues at .

At the cell carrier binds the cell phone number to the VCA ID. For example the cell carrier may maintain a data store that identifies for each of any number of cell phone numbers one or more VCAs to which the cell phone number is bound. In an example implementation the VCA ID that was submitted in the binding request is used by the cell carrier to bind the VCA to the cell phone number. In an alternate implementation the cell carrier may assign a different carrier specific device ID to the VCA for binding purposes.

In an example implementation any number of cell phone numbers may be bound to a single VCA and similarly any number of VCAs may be bound to a single cell phone.

At the cell carrier sends a bind confirmation to the cloud based service . For example the cell carrier may send a message to the cloud based service indicating that the bind was successful and specifying the cell phone number the VCA ID submitted in the bind request and if applicable a carrier specific ID assigned to the VCA for binding purposes.

At the cloud based service records the bind confirmation. For example the cloud based service may also maintain a data store that indicates which VCA devices are bound to which cell phone numbers. In addition the data store maintained by the cloud based service may maintain a mapping between the VCA identifier included in the initial bind request and a cell carrier specific identifier associated with the VCA.

At a cell carrier receives a call directed to a bound cell phone number. For example when the cell carrier receives an indication of an incoming call the cell carrier checks the binding data store and determines that the destination cell phone number is bound to at least one voice controlled assistant.

At the cell carrier signals the cell phone associated with the destination cell phone number to indicate the incoming call. For example the cell carrier sends a signal over a cellular network to the destination cell phone number.

At substantially simultaneous to the cell carrier notifies the cloud based service of the incoming call. For example the cell carrier may send a notification over the network to the cloud based service of computing resources . The notification may include for example the calling phone number the destination cell phone number and an identifier associated with at least one VCA to which the destination cell phone number is bound.

At the cloud based service receives the notification of the incoming call from the cell carrier . As described above the identifier associated with the VCA at the cell carrier may differ from an identifier of the VCA maintained by the cloud based service . The cloud based service may cross reference the VCA ID in a data store maintained by the cloud based service to determine how to communicate with the VCA.

At the cloud based service notifies the VCA of the incoming call. For example the cloud based service may send a message to the VCA over the network . The message may include for example the calling phone number and the destination cell phone number.

At after the VCA and the cell phone to which the VCA is bound have been notified of the incoming call cell carrier may receive an indication that the call has been answered via the cell phone.

At in response to receiving an indication that the call has been answered via the cell phone the cell carrier directs the cloud based service to stop indicating the incoming call.

At a voice controlled assistant receives notification of an incoming call. For example as described above with reference to of the cloud based service may send a notification of an incoming call to the VCA over the network .

At a determination is made as to whether or not the VCA should indicate the incoming call. In an example implementation the VCA may be configured to indicate the incoming call anytime a notice of an incoming call is received. However there may be times when signaling an incoming call may not be desired.

For example in an alternate implementation the VCA may determine that it should indicate the incoming call only if the cell phone to which the incoming call is directed is in a threshold proximity to the VCA. Proximity of the destination cell phone may be determined in a variety of ways. As one example proximity of a cell phone to the VCA may be based on geo fencing. In this example the carrier network may be aware of a physical address e.g. street address of the VCA and may determine a current location of the cell phone using location based services such as cell tower triangulation or cell tower ID. GPS coordinates of the cell phone location and the physical address of the VCA are then compared and the VCA is only notified of the incoming call if the cell phone is within a prescribed threshold distance from the VCA. Such proximity determination may also be used to determine whether or not outgoing calls can be initiated through the VCA.

In another example the VCA is only allowed to signal the incoming call if the VCA and the cell phone are both connected to the same network such as a local WIFI network. In an example implementation the cell phone includes an application that can detect the presence of the VCA unit when the VCA is on the same network as the cell phone. Alternatively the application may determine that the cell phone is connected to a network that the VCA is known to be associated with. After determining that the cell phone and VCA are on the same network the application notifies the carrier network that the VCA is allowed to receive incoming calls and or to place outgoing calls .

In yet another example the VCA and the cell phone may be paired using an active personal area network connection. In one instance when the personal area network connection is determined either the VCA or the cell phone may notify the carrier network to allow simultaneous signaling of inbound calls on both the cell phone and the VCA and or to allow outbound calls to be placed from the VCA. In another instance when the personal area network connection is determined the VCA may automatically transition from an off state whereby no communication are permitted through the VCA to an on state whereby the VCA can accept incoming calls for cell phones with which it is paired or allow outbound calls using the cell phone s number. A personal area network may be established using any of various technologies including but not limited to infrared data association IrDA Bluetooth wireless USB Z Wave ZigBee and so on.

In another alternate implementation the VCA may determine that it should indicate the incoming call based on detected proximity or likely proximity of a user associated with the destination cell phone. For example the cell phone may not be in proximity but the user may be e.g. the user may have left the phone in another location . Proximity of the user may be determined in a variety of ways including but not limited to any combination of the VCA may examine heuristic data based on the time of day and a calendar or schedule associated with the user to determine a location at which the user is likely to be located or the VCA may determine how recently the user interacted with the VCA to determine whether or not the user is likely proximate to the VCA at the current time.

The various techniques for determining proximity of the cell phone or the user to the VCA may be implemented in combination with different techniques having different confidence levels. For example triangulation data from the cell carrier may be given a relatively low confidence level while detection of the cell phone on a local wifi network may be given a relatively high confidence level. If proximity of a cell phone is detected through multiple techniques the confidence levels of each of those techniques may be analyzed in combination to determine an overall confidence level for the detected cell phone proximity.

In yet another alternate implementation the VCA may be configured by the user e.g. via a command or a manual switch to accept or not accept incoming phone calls.

If it is determined at that the VCA should not indicate the incoming call the No branch from block e.g. because the destination phone or the user is not in proximity or because a setting on the VCA indicates that the VCA should not indicate an incoming call then processing terminates and the incoming call is not indicated via the VCA.

On the other hand if it is determined at that the VCA should indicate the incoming call the Yes branch from block then at the VCA indicates the incoming call. In an example implementation the VCA may indicate the incoming call with any one or combination of a variety of audible or non audible signals. For example the VCA may make a sound similar to a telephone ringing. In another example the VCA may speak an audible notification indicating the phone number or other identifier associated with the caller. Furthermore if multiple cell phone numbers are bound to the same VCA the incoming call indication may also indicate to which of the cell phones bound to the VCA the call is directed. In another example the VCA may include lights that blink or otherwise indicate an incoming call.

While the VCA indicates the incoming call per at the VCA is configured to accept phone commands. For example the VCA may be configured to recognize a set of voice commands. When an incoming call is indicated the set of voice commands may be modified to include commands related to telephone communications. For example the available command list may be modified to include commands such as answer call hang up and so on.

At a determination is made as to whether or not an answer command has been received. For example the VCA is configured to detect a command of answer call from a user while the VCA is indicating the incoming call. In an example implementation a preliminary command e.g. wake may be used to direct the VCA to listen for an answer command. This implementation may be useful to prevent the VCA from answering a call prematurely based on detected words in a conversation between two users in the room. For example when the VCA begins indicating an incoming call one user in the room may ask another Are you going to answer that It would not be desirable for the VCA to answer the call based on detection of the word answer in that conversation.

If at it is determined that an answer command has not yet been received the No branch from block then at a determination is made as to whether or not the incoming call is still pending. For example as described above with reference to blocks of the VCA may receive an indication that the incoming call is no longer pending if a user of the cell phone that is bound to the VCA answers the incoming call via the cell phone.

If at it is determined that the incoming call is still pending the Yes branch from block then processing continues as described above with reference to .

On the other hand if at it is determined that the incoming call is no longer pending the No branch from block then at the VCA stops indicating the incoming call. In an example implementation when the incoming call indication is terminated any configuration done to the VCA to accept phone commands is also reversed.

Referring back to block if it is determined that an answer command has been received the Yes branch from block then at the VCA stops indicating the incoming call.

At the VCA notifies the cloud based service of the received answer command. For example the VCA sends an indication of the answer command to the cloud based service over the network .

Additional functionality to establish the phone call after the answer command is received is described below with reference to .

As described above at the voice controlled assistant notifies the cloud based service of an answer command received from a user of the VCA.

At the cloud based service receives notification of the answer command from the VCA . For example the notification is received over the network .

At the cloud based service notifies the cell carrier of the received answer command. For example the cloud based service sends a notification over the network .

At in response to receiving notification of the answer command received through the VCA bound to the destination cell phone number the cell carrier stops signaling the incoming call to the cell phone associated with the destination cell phone number. That is because the user has indicated a desire to answer the incoming call through the VCA the cell phone that is associated with the destination cell phone number is directed to stop ringing.

At also in response to receiving notification of the answer command received through the VCA the cell carrier sends an IP address for an audio stream to the cloud based service . The IP address is associated with an audio communication channel over which the incoming phone call will be transmitted between the VCA and the cell carrier. The cell carrier will use another communication channel e.g. over a 3G or 4G cellular network to communicate with the device e.g. a phone through which the call was initiated.

At the cloud based service receives the IP address for the audio stream from the cell carrier . For example the cloud based service receives the IP address over the network .

At the VCA connects to the IP address that is received from the cell carrier via the cloud based service . When the VCA connects to the IP address a connection is thus established between the VCA and the cell carrier via a network e.g. a VoIP network and a connection is established between the cell carrier and the caller via another connection e.g. over a cellular telephone network . The cell carrier acts as a middle man to facilitate the communication between the caller and the user of the VCA.

At the VCA receives a command to place a phone call. In an example implementation the command includes an indication of the destination phone number to be called. Alternatively the command may include an identity of a user to call and the VCA determines a phone number associated with the user to be called. In yet another example the VCA may perform speech recognition on the received command to identify the user and thereafter may map this identification to the cell phone associated with the user.

At the VCA notifies the cloud based service of the command to place a call. For example the VCA sends a voice command received from a user to the cloud based service over the network .

At in response to receiving notification of the call command received through the VCA the cell carrier sends an IP address for an audio stream to the cloud based service . The IP address is associated with an audio communication channel over which the requested outgoing phone call will be transmitted between the VCA and the cell carrier. The cell carrier will use another communication channel e.g. over a 3G or 4G cellular network to communicate with the device e.g. a phone to which the call will be placed.

At also in response to receiving notification of the call command received through the VCA the cell carrier places a call to the destination phone number specified in the call command as if the call originated from the cell phone number to which the VCA is bound.

At the cloud based service receives the IP address for the audio stream from the cell carrier . For example the cloud based service receives the IP address over the network .

At the VCA connects to the IP address that is received from the cell carrier via the cloud based service . When the VCA connects to the IP address a connection is thus established between the VCA and the cell carrier via a network e.g. a VoIP network and a connection is established between the cell carrier and the destination phone number via another connection e.g. over a cellular telephone network . The cell carrier acts as a middle man to facilitate the communication between the user of the VCA and the user being called.

At the VCA receives a command to disconnect a phone call. For example the user may direct a voice command to the VCA indicating a desire to hang up the call.

At in response to the received command to disconnect the call the VCA disconnects from the IP address of the audio stream associated with the call.

At the VCA returns to a non phone mode. For example as described above with reference to block of when a phone call is established through the VCA the VCA may be configured to accept phone commands. This configuration may be thought of as putting the VCA in a phone mode. When the call is disconnected the configuration may be reversed removing the VCA from phone mode. 

At in response to receiving the notification of the disconnect command the cell carrier closes the audio stream over which the VCA was receiving the phone call communications.

At the cell carrier closes the audio connection between the cell carrier and the other caller. For example referring to the connection over the cellular network is closed.

At the cell carrier receives an indication of a disconnect. For example referring to the cell carrier may detect that the connection over the cellular network has been lost.

At in response to receiving the indication of the disconnect the cell carrier closes the audio stream over which the VCA was receiving the phone call communications. For example referring to the connection over the VoIP network is closed.

At the cell carrier closes the audio connection between the cell carrier and the other caller. For example referring to the connection over the cellular network is closed.

At the VCA receives a command to transfer a phone call from the VCA to a cell phone. For example the user may direct a voice command to the VCA indicating a desire to continue the call through the user s cell phone instead of through the VCA.

At the VCA notifies the cloud based service of the command to transfer the call. The notification may include a variety of information including for example any combination of a user identifier a cell phone identifier a VCA identifier and so on.

At in response to receiving the notification of the transfer command the cell carrier establishes a connection between the cell carrier and the cell phone to which the VCA is bound. For example referring to the cell carrier establishes the cellular network connection between the carrier and the user s cell phone .

At also in response to receiving the notification of the transfer command and after the connection between the cell carrier and the cell phone is established the cell carrier closes the audio stream over which the VCA was receiving the phone call communications.

At the VCA detects the loss of the VoIP communication connection. Although not illustrated in in an example implementation the cell carrier may notify the cloud based service of the closed audio stream between the cell carrier and the VCA. The cloud based service may then direct the VCA to return to a non phone mode.

At the VCA returns to a non phone mode. For example as described above with reference to block of when a phone call is established through the VCA the VCA may be configured to accept phone commands. This configuration may be thought of as putting the VCA in a phone mode. When the call is disconnected the configuration may be reversed removing the VCA from phone mode. 

At the VCA receives a command to transfer a phone call from a cell phone to the VCA. For example the user may direct a voice command to the VCA indicating a desire to move the call that is currently occurring through the user s cell phone to continue the call through the VCA. Although not illustrated in any number of techniques may be used to verify that the user requesting to transfer the call is authorized to do so. Furthermore in example implementations a command to transfer a call from the cell phone to the VCA may only be allowed if the cell phone is in proximity to the VCA.

At the VCA notifies the cloud based service of the command to transfer the call. The notification may include a variety of information including for example any combination of a user identifier a cell phone identifier a VCA identifier and so on.

At in response to receiving the notification of the transfer command the cell carrier establishes an IP based audio stream for communicating the phone call with the VCA.

At the cell carrier sends an IP address associated with the IP based audio stream to the cloud based service .

At the cloud based service sends the IP address to the VCA directing the VCA to connect to the IP address.

At the VCA connects to the specified IP address thereby becoming a device to which the phone call communications are now being sent.

At upon detecting that the connection between the cell carrier and the VCA has been established the cell carrier disconnects the communication path between the cell carrier and the cell phone.

In an alternate implementation rather than a command to transfer the call the command may be a command to join the VCA to the call. In this scenario the processing may be the same as that illustrated in except that the call connection with the cell phone would not be disconnected at .

At the cell carrier receives a command from a cell phone to transfer a phone call from the VCA to a cell phone. For example the user may enter a menu command through the cell phone requesting the call transfer.

At in response to receiving the transfer command the cell carrier establishes a connection between the cell carrier and the cell phone to which the VCA currently responsible for the call is bound. For example referring to the cell carrier establishes the cellular network connection between the carrier and the user s cell phone .

At also in response to receiving the transfer command and after the connection between the cell carrier and the cell phone is established the cell carrier closes the audio stream over which the VCA was receiving the phone call communications.

At the VCA detects the loss of the VoIP communication connection. Although not illustrated in in an example implementation the cell carrier may notify the cloud based service of the closed audio stream between the cell carrier and the VCA. The cloud based service may then direct the VCA to return to a non phone mode.

At the VCA returns to a non phone mode. For example as described above with reference to block of when a phone call is established through the VCA the VCA may be configured to accept phone commands. This configuration may be thought of as putting the VCA in a phone mode. When the call is disconnected the configuration may be reversed removing the VCA from phone mode. 

At the cell carrier receives a command from a cell phone to transfer a phone call from the cell phone to a VCA. For example the user may enter a menu or voice command through the cell phone requesting the call transfer.

At in response to receiving the transfer command the cell carrier establishes an IP based audio stream for communicating the phone call with the VCA.

At the cell carrier sends a notification of the transfer command and an IP address associated with the IP based audio stream to the cloud based service .

At the cloud based service receives the transfer notification and the IP address for the audio stream from the cell carrier.

At the cloud based service sends the IP address to the VCA directing the VCA to connect to the IP address.

At the VCA connects to the specified IP address thereby becoming a device to which the phone call communications are now being sent.

At upon detecting that the connection between the cell carrier and the VCA has been established the cell carrier disconnects the communication path between the cell carrier and the cell phone.

In an alternate implementation rather than a command to transfer the call the command may be a command to join the VCA to the call. In this scenario the processing may be the same as that illustrated in except that the call connection with the cell phone would not be disconnected at .

Although the subject matter has been described in language specific to structural features it is to be understood that the subject matter defined in the appended claims is not necessarily limited to the specific features described. Rather the specific features are disclosed as illustrative forms of implementing the claims.

