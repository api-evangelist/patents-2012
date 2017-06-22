---

title: Authenticating an ephemeral Diffie-Hellman using a trusted third party
abstract: Authentication of parties through a trusted intermediary is described. The standard Ottway-Rees authentication protocol is modified to provide authentication between A and B using intermediary T such that T serves only as an authenticator, and does not participate in the generation of the key shared between A and B.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08750512&OS=08750512&RS=08750512
owner: Aruba Networks, Inc.
number: 08750512
owner_city: Sunnyvale
owner_country: US
publication_date: 20121026
---
This application claims the benefit of priority on U.S. Patent Application No. 61 552 810 filed Oct. 28 2011 the entire contents of which are incorporated by reference.

Embodiments of the disclosure relate to the field of network authentication and in particular a system and method for authenticating network devices and or their users using a trusted intermediary device.

When parties wish to communicate securely over a network these parties must authenticate each other to ensure that they are in fact participating in the communications. One type of authentication protocol involves the use of a third party trusted by both the parties involved in the secure communications. The trusted third party is responsible for authenticating the parties and generating a key which is used for encrypting data sent between these parties.

Another type of authentication protocol involves network access. As an example a client device wishes to access a network through behind a network gateway. Since the client device is not strictly speaking on the network yet it is incapable of communicating with a trusted third party residing on the network. But the client device can send data to the trusted third party through the network gateway and the network gateway cannot modify or unwrap them. After the authentication protocol has completed the client device and the network gateway are able to share a key that may be used to protect data communicated by users associated with their network devices.

One approach to such mutual authentication using a trusted third party may be found in Efficient and Timely Mutual Authentication 21 n.1 1987 pp. 8 10 by D. Otway and O. Rees discussed in by Bruce Schneier pp 59 60.

Otway Rees makes use of a trusted third party to distribute keys to two parties. While this protocol provides resistance to replay and cut and paste attacks the trusted third party provides the key used by the two parties which is considered by many to be a weakness in the networked system. Another weakness with the Otway Rees scheme is that it does not provide Perfect Forward Secrecy PFS namely if the secret either party shares with the trusted third party is compromised then all past traffic can be revealed.

For instance an example of standard Otway Rees authentication and key generation for a client device and a gateway server through use of an intermediary device is described below.

The client device generates a nonce Na and chooses a session identifier sess . Thereafter as represented immediately below the client device sends its identifier A an identifier B for the server session identifier sess and this data Na A B sess encrypted with a shared key K previously established between the client device A and the intermediary device T.

Similarly the server B generates a nonce Nb . Thereafter server B sends its identifier B along with the identifier for the client device A sess the encrypted data Na A B sessKand additional data Nb A B sess encrypted with a shared key K previously established between the server B and the intermediary device T as represented immediately below 

Based on this information the intermediary device T generates a shared key K for use by both client device A and server B. The shared key K is returned to the server B which subsequently provides Kback to the client device A. More specifically with the session identifier sess the shared key K is returned to the server B as part of i data Na K encrypted with K the shared key between Alice and Trent and ii data Nb K encrypted with K the shared key between the server B and the intermediary device T. This communication is represented immediately below 

Since the client device A and the intermediary device T are unable to communicate directly to each other for the client device A to receive K a portion of a message containing Kneeds to pass through the server B. Thereafter the server B sends the session identifier sess along with the encrypted data Na KKto client device A as represented immediately below 

Since the server B has access to key K it can decrypt Nb KK verify nonce Nb and retrieve shared key K. Similarly having access to key K the client device A can decrypt Na KK verify nonce Na and retrieve shared key K. Now both client device A and the server B share Kand can use Kto communicate securely.

A perceived weakness in this exchange is that the shared key K is generated and now also known by a third party Trent . Another weakness mentioned above is the lack of Perfect Forward Secrecy that would reveal all past conversation between A and B if either Kor Kis compromised.

What is needed is a way to use the trusted intermediary to authenticate the two parties to each other and not operate as a key generator.

In the following description several specific details are presented to provide a thorough understanding of the inventive aspects presented in the disclosure. While the context of the disclosure is directed to authentication of a party e.g. network device and or user operating in accordance with an Ephemeral Diffie Hellman based authentication protocol without the trusted third party performing key generation one skilled in the relevant art may recognize however that the concepts and techniques disclosed herein can be practiced without certain details such as the exclusion of one or more operations logic or the like.

Herein certain terminology is used to describe features and or operations described for various embodiments of the disclosure. For example the term network device generally refers to any device that includes a processor and supports wired or wireless network connectivity. Examples of network devices may include any of the following a computer such as a tablet a laptop a desktop a net book or a mainframe a server such as a web server an authentication server an authentication authorization accounting AAA server a Domain Name System DNS server a Dynamic Host Configuration Protocol DHCP server an Internet Protocol IP server a Virtual Private Network VPN server a network policy server or a Radius server a television a content receiver a set top box a video gaming console a television peripheral such as Apple TV a printer a mobile handset such as a cellular telephone supporting WiFi a smart phone or a personal digital assistant PDA a wireless receiver and or transmitter an access point a base station a communication management device a router a switch and or a controller.

It is contemplated that the network device may include logic such as one or more of the following i processing circuitry ii one or more communication interfaces such as a radio e.g. component that handles the wireless data transmission reception and or a physical connector to support wired connectivity and or iii a non transitory computer readable storage media e.g. a programmable circuit a semiconductor memory such as a volatile memory such as random access memory RAM or non volatile memory such as read only memory power backed RAM flash memory phase change memory or the like a hard disk drive an optical disc drive etc. or any connector for receiving a portable memory device such as a Universal Serial Bus USB flash drive portable hard disk drive or the like.

Herein the terms logic and logic unit are generally defined as hardware and or software. For example as hardware logic may include processing circuitry e.g. a microcontroller any type of processor a programmable gate array an application specific integrated circuit etc. semiconductor memory or the like. As software logic may be one or more software modules such as executable code in the form of an executable application an application programming interface API a subroutine a function a procedure an object method implementation an applet a servlet a routine source code object code a shared library dynamic load library or one or more instructions. These software modules may be stored in any type of a suitable non transitory storage medium or transitory computer readable transmission media e.g. electrical optical acoustical or other form of propagated signals such as carrier waves infrared signals or digital signals .

The term interconnect is a communication path between two or more network devices. The communication path may include wired and or wireless segments. Examples of wired and or wireless segments include electrical wiring optical fiber cable bus trace or a wireless channel using infrared radio frequency RF or any other wired wireless signaling mechanism.

The terms data package and message identify a collection of information placed in a prescribed format. As an illustrative example a data package may be part of a data transmission such as a packet a frame an Asynchronous Transfer Mode ATM cell a stream of data or the like. Similarly a message may be a portion of the data package such as part or all of header or payload of the data package. For instance one message type may be one or more bits of information placed in an encrypted format within the payload.

Lastly the terms or and and or as used herein are to be interpreted as inclusive or meaning any one or any combination. Therefore X Y or Z or X Y and or Z mean any of the following X Y Z X and Y X and Z Y and Z X Y and Z. An exception to this definition will occur only when a combination of elements functions steps or acts are in some way inherently mutually exclusive.

Certain details are set forth below in order to provide a thorough understanding of various embodiments of the disclosure albeit the invention may be practiced through many embodiments other that those illustrated. Well known logic and operations may not be set forth in detail in order to avoid unnecessarily obscuring this description. Moreover the illustrated embodiments of the disclosure and the description associated therewith should be considered as examples of the principles of the invention and not intended to limit the disclosure to those specific embodiments. It should be understood that this disclosure covers all modifications equivalents and alternatives falling within the spirit and scope of the disclosure.

To further describe embodiments of the disclosure the following terms are generally defined as the following 

 Alice represents a first party namely a first network device and or its user which is identified to other network devices and or users by an identifier. Examples of an identifier represented for Alice as A may include but is not limited or restricted to a binary string an alphanumeric value being a series of alphanumeric characters e.g. numbers 0 9 lower and upper case text A Z and a z or a combination thereof a non English characters or names one or more graphic images or the like. Herein according to this embodiment in the disclosure the first network device may be adapted to operate as a client device e.g. a mobile telephone such as a smart phone portable computer or tablet etc. by a first user.

 Bob represents a second party namely a second network device and or its user which is identified to other network devices and or users by an identifier. The identifier for Bob is represented herein as B . According to this embodiment in the disclosure the second network device may be adapted to regulate access to a network. Examples of the second network device may include but are not limited or restricted to a server an access point a controller a router or even firewall software operating within one of these devices.

 Trent represents a third party namely a third network device and or its user which is identified to other network devices and or users by an identifier. The identifier for Trent is represented herein as T . Herein according to this embodiment in the disclosure the third network device may be adapted to operate as a device that is trusted by the first and second network devices for authenticating communications by such devices.

The notation gmod P represents a public value namely a Diffie Hellman exponential of generator g raised to the power of x modulo a prime P. Herein x is a random or pseudo random value that is securely stored as a private value and generator g defines a finite cyclic group in the prime field formed by P.

The notation sess represents a session identifier that may be used to identify an instance of a communication protocol and the shared state that results.

Both Alice and Bob can use a symmetric encryption and authentication protocol to wrap and unwrap messages using the keys they share K K with Trent.

Embodiments of the disclosure relate to methods of authenticating users through a trusted intermediary.

As shown in a general block diagram of a first embodiment of a network operating in accordance with Ephemeral Diffie Hellman based authentication using a trusted third party Trent is shown. Herein a first party represented by a first network device and or its user hereinafter referred to as Alice having an identifier A wants access to resources on network . Such access requires Alice to initiate an access request through a second party represented by a second network device and or its user hereinafter referred to as Bob having an identifier B .

As shown Bob control communications with a trusted third party hereinafter referred to as Trent having an identifier T connected to network . Of course it is contemplated that Trent may be present outside of network in which both Alice and Bob have access to Trent . However Alice still cannot communicate with Trent directly but rather communications with Trent via Bob .

Alternatively Ephemeral Diffie Hellman based authentication may be used to control network access. For instance as shown in Alice may be a wireless network device requesting access to a network e.g. private network or a public network such as the Internet via Bob . The authentication is used to ensure that Bob is in communication with Alice before network access is provided. This may be performed for network security or perhaps for device user authentication for billing purposes.

As illustrated in an exemplary embodiment of a network device such as second network device for example is shown. Herein second network device comprises a processor a memory e.g. volatile and or non volatile memory and one or more communication interfaces . This logic is communicatively coupled by an interconnect . It is contemplated that interconnect may provide a common communication path for these logic units or separate dedicated communication paths between various logic units.

A type of processor used within a network device e.g. network device depends on device characteristics. For instance as illustrative embodiments an ARM processor may be used where network device is a smart phone a tablet or the like. An IA86 style processor may be used where network device is a laptop computer or a desktop computer or a MIPS class processor may be used in network devices such as access points switches controllers servers routers or the like.

Communication interface s comprises one or more wireless interfaces operating in accordance with a particular networking standard e.g. IEEE 802.3 IEEE 802.11 Internet Protocol IP etc. . Optionally in lieu of or in addition to wireless interface s network device may be implemented with one or more wired interfaces e.g. IEEE 802.3 wired Ethernet interface or one or more input output I O interfaces for receiving and or transmitting information from a peripheral device. Examples of the peripheral device may include but are not limited or restricted to an input device e.g. keyboard pointing device such as a touch screen touch pad mouse keypad etc. and or an output device e.g. a display device .

Memory includes non transitory computer readable medium such as read write memory for program data store and device initialization e.g. one or more types of random access memory RAM flash memory Electrically Erasable Programmable Read Only Memory EEPROM etc. and or bulk memory such as flash solid state disk SSD or disc drives. Network device operates under control of an operating system with purpose built programs providing functionality to the device. These programs are stored in portions of memory of network device .

Referring now to an exemplary flowchart of the authentication operations in accordance with an Ephemeral Diffie Hellman based authentication is shown. Herein a public value e.g. gmod P where b is device or user specific private information with the prime P and generator g previously agreed upon by the first and second parties is made available to a second party block . For instance the public value may be generated by the second party or uploaded to the second party by another source.

The second party also receives a first message with encrypted data from a first party Alice as shown in block . The encrypted data includes a public value associated with the first party that alone or with additional authentication information such as a session identifier and or nonce is encrypted with a key K that is shared between the first party Alice and a trusted third party Trent . According to one embodiment of the disclosure the first public value associated with the first party Alice is gmod P where a is a value private to the first network device and or its user.

After receipt of the first message as set forth in block at least the second public value gmod P and the encrypted data are encrypted by a key K that is shared between the second party Bob and the trusted third party Trent . This encrypted result is transmitted to the trusted third party Trent for authentication of the first party Alice and the second party Bob .

Thereafter the second party Bob receives public values associated with both the first party and the second party gmod P gmod P which are separately encrypted with K gmod P gmod PK and K gmod P gmod PK as set forth in block . These public values may be encrypted with other authentication information such as session identifiers and or nonces.

By having access to shared key K second party Bob is able to recover the first public value gmod P value and generate a key shared with the first party Alice as set forth in blocks and . This shared key K is computed by performing a modular exponentiation operation using the private value b of the second party and the first public value e.g. g mod P .

Second party Bob further sends the return message encrypted with K e.g. gmod P gmod PK to the first party as set forth in block . By having access to shared key K first party Alice will be able to recover the second public value gmod P from the encrypted message and generate the shared key Ktherefrom using the second public value and private value a e.g. gb mod P .

According to one embodiment of the disclosure as shown in an exemplary sequence diagram of a first embodiment of an Ephemeral Diffie Hellman based authentication protocol is shown. Initially this embodiment begins with Alice generating a private value a . Also session identifier sess may be used to identify a particular communication session that is being used for authentication sequence . Sess may be generated automatically upon generating a request for access to a network via Bob .

Alice sends to Bob a first message that comprises information including but not limited or restricted to i an identifier A for Alice and ii a first message that comprises at least identifier A an identifier B for Bob and a first public value. According to one embodiment of the disclosure the first public value is a generator g raised to the power of a modulo a selected prime number P gmod P . The information within first message is encrypted using a shared key K established between Alice and Trent .

It is contemplated that additional information such as a session identifier sess may be included within first message and or as part of a data package for better management of the communications and avoidance of various types of attacks. Therefore according to this embodiment of the disclosure data package comprises A sess and first message namely A B sess gmod P encrypted with the shared key K between Alice and Trent as represented immediately below.

Prior to or subsequent to receipt of data package Bob generates a private value b Sequence . Bob sends a second data package that comprises information including but not limited or restricted to B sess and a second message . Second message comprises B A sess a public value for Bob e.g. gmod P and the portion of the first message encrypted by K where this information is encrypted with the shared key K between Bob and Trent . Hence second data package provided from Bob may be represented as set forth below

Upon receiving data package Trent confirms that communications are during the same session and originate from Alice A and Bob B Sequence . For instance the same session may be confirmed by determining that the session identifiers sess within messages and match namely extracting the session identifiers sess from different messages and and comparing these identifiers. Confirmation that the two parties A B are involved in the communications may be accomplished by verifying identifiers A B encrypted within first message and second message .

If no confirmation Trent sends an error message or simply provides no return messages to Bob . However upon confirmation Trent returns a third data package that comprises sess and a third message that is encrypted with second shared key K . Third message comprises B A sess gmod P gmod P as well as a fourth message A B sess gmod P gmod P encrypted with first shared key K as represented below 

Upon receipt of data package Bob verifies the information returned from Trent Sequence . For instance Bob may decrypt third message using Kto determine that the session identifier sess in the clear within the data package matches the session identifier sess recovered from the third message . As another optional verification a comparison may be performed to determine whether Bob s public value gmod P matches the public value recovered from third message . As another optional verification Bob may determine that the communications are associated with Alice e.g. compare received identifier A with identifier A received from Alice .

In the event that the verification is not successful Bob returns an error message to Alice or simply halts communications. However upon successful verification by Bob at least one Diffie Hellman exponential gmod P is recovered for shared key generation between Bob and Alice Sequence .

Also a portion of data package is routed to Alice . This portion may include sess and a portion of third message namely fourth message encrypted with K as represented below 

Alice decrypts fourth message to determine that the session numbers match and that Diffie Hellman exponential gmod P within fourth message matches its public value. If so at least Diffie Hellman exponential gmod P with fourth message is recovered for use as or used to generate a shared key between Alice and Bob as set forth below Sequence .

For shared key generation between Alice and Bob it is noted that there is a symmetrical relationship between the Diffie Hellman exponentials where

Now Alice knows gmod P and a and can compute gmod P Gmod P. Bob knows gmod P and b and can compute gmob P gmod P. As a result both parties can produce gmod P which may be used in whole or in part as a shared key K between Alice and Bob or may be used in whole or in part to generate K.

According to another embodiment of the disclosure as shown in an exemplary sequence diagram of a second embodiment of the Ephemeral Diffie Hellman based authentication protocol is shown. This embodiment is similar to the Ephemeral Diffie Hellman based authentication protocol of except both Alice and Bob also generate nonces Na and Nb to further avoid replay attacks and to use a random inputs to a key derivation function KDF . These nonces are also included in first message second message third message and fourth message .

Furthermore Alice and Bob are adapted to use the nonces Na Nb and the Diffie Hellman shared secret gmod P as parameters into a shared key derivation function KDF to create a shared key between Alice and Bob namely K. As shown herein Kmay be a concatenation of the shared key derivation function KDF operating on at a minimum the shared secret gmod P and nonces Na and Nb to produce shared key K Sequences and . Any conventional key derivation function may be used as such for instance but not limited to any Key Derivation Function from Special Publication 8000 108 from the U.S. National Institute of Standards and Technology NIST or the Extract And Expand Key Derivation Function RFC 5869 . mod 

While Alice and Bob have not technically authenticated each other Alice knows that Bob created gmod P by Trent s assertion and only Bob can know gmod P. Similarly Bob knows that Alice created gmod P by Trent s assertion and only Alice can know gmod P. Therefore only the respective parties in this communication can know K. Alice and Bob may perform a proof of possession handshake with Kto finish authentication.

According to these authentication protocols Trent is removed from the role of key distributor and merely operates as an authenticator.

Referring now to another embodiment of the Ephemeral Diffie Hellman based authentication protocol involves the use of a hash of the Diffie Hellman exponential H gmod P . A generalized sequence of the authentication protocol is shown below.

Upon comparison of the authentication protocol set forth in with the authentication set forth in besides using the results of a one way hash function there are other noted differences. For instance upon receipt of data package Bob verifies the information returned from Trent Sequence . One optional verification scheme involves comparison of a result produced by conducting a hash operation on Alice s public value gmod P received and the hash result H gmod P of Alice s public value recovered from the third message B A . . . H gmod P A B . . . KK.

In particular as shown in an exemplary sequence diagram of a third embodiment of Ephemeral Diffie Hellman based authentication protocol is shown. Alice generating a private value a . Also session identifier sess may be used to identify a particular communication session that is being used for authentication Sequence .

Alice sends to Bob a first message that comprises information including but not limited or restricted to i an identifier A for Alice and ii a first message that comprises at least identifier A an identifier B for Bob and a hash result H gmod P produced by conducting a one way hash operation on the first public value gmod P . The information within first message is encrypted using the shared key K established between Alice and Trent .

It is contemplated that additional information such as a session identifier sess may be included within first message and or as part of data package . Therefore according to this embodiment of the disclosure data package comprises A sess gmod P and first message namely A B sess H gmod P encrypted with the shared key K between Alice and Trent as represented immediately below.

Prior to or subsequent to receipt of data package Bob generates a private value b Sequence . Bob sends a second data package that comprises information including but not limited or restricted to B sess and a second message . Second message comprises B A sess a hash result H gmod P produced by conducting a one way hash operation on the second public value gmod P and first message where this information is encrypted with the shared key K between Bob and Trent . Hence second data package provided from Bob may be represented as set forth below

Upon receiving data package Trent confirms that the two parties A B are involved in the communications and that the session identifiers sess within messages and match Sequence as described above.

Thereafter after confirmation Trent returns a third data package that comprises sess and a third message that is encrypted with second shared key K . Third message comprises B A sess H gmod P H gmod P as well as a fourth message A B sess H gmod P H gmod P encrypted with first shared key K as represented below 

Upon receipt of data package Bob verifies the information returned from Trent Sequence . For instance Bob may decrypt third message using Kto determine that the session identifier sess in the clear within the data package matches the session identifier sess recovered from the third message . As another optional verification a comparison may be performed to determine whether a hash of Alice s public value gmod P matches the hash result H gmod P recovered from third message . As another optional verification Bob may determine that the communications are associated with Alice e.g. compare received identifier A with identifier A received from Alice .

Upon successful verification at least one Diffie Hellman exponential gmod P is recovered for shared key generation between Bob and Alice Sequence .

Also a portion of data package is routed to Alice . This portion may include sess Bob s public value gmod P and a portion of third message namely fourth message encrypted with K as represented below 

Alice decrypts fourth message to determine that the session numbers match and that the hash result of Diffie Hellman exponential H gmod P within fourth message matches a hash result of Bob s public value. If so at least a hash result of the Diffie Hellman exponential H gmod P with fourth message is recovered for use as or used to generate a shared key between Alice and Bob as set forth below Sequence .

As previously mentioned for shared key generation between Alice and Bob it is noted that there is a symmetrical relationship between the Diffie Hellman exponentials where mod mod mod 

Now Alice knows gmod P and a and can compute gmod P gmod P. Bob knows gmod P and b and can compute gmod P gmod P. As a result both parties can produce gmod P which may be used in whole or in part as a shared key K between Alice and Bob or may be used in whole or in part to generate K.

Referring now to a fourth embodiment of the Ephemeral Diffie Hellman based authentication protocol involves the use of a hash of the Diffie Hellman exponential H gmod P along with nonces generated at Alice and Bob 

In the original Otway Rees protocol the nonce Na Nb is used for a liveness proof to ensure that Alice and Bob are on line and took part in this exchange and their messages are not replayed by an adversary from a previous run of the protocol. As described in the embodiments of the disclosure gmod P or H gmod P takes that place. There is still a liveness proof. The embodiments of the disclosure imbed Alice s wrapped messages into Bob s to further bind Bob to the exchange and prevent cut and paste attacks. Embodiments of the present invention use the trusted third party to provide authenticity to the peer s Diffie Hellman exponential instead of using it as a key distributor as the standard Otway Rees does.

The benefits of this are that the exchange generates an ephemeral key that both parties took part in generating and that no other party can know including the trusted third party. In addition the exchange accomplishes Perfect Forward Secrecy PFS because compromise of either or both of the shared secrets Kand Kwould not result in knowledge of the shared secret from earlier runs of the protocol.

These authentication protocols can be extended to use elliptic curve cryptography where a point on the elliptic curve acts as a generator and is multiplied by the value a and or b to generate the public values and each of the public values a G for Alice and b G for Bob are multiplied by the other party s private value b a G by Bob and a b G by Alice to produce a shared secret a b G.

It is to be understood that the above description is intended to be illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reading and understanding the above description. For instance multiple secondary network devices Bob may be deployed where each of these network devices has responsibility in controlling access to the network. The scope of the invention should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

