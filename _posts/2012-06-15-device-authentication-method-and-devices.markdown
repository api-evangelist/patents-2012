---

title: Device authentication method and devices
abstract: In a method for authenticating a device on a wireless local area network (WLAN) there is a once-off registration phase in which the device sends registration data in a MO SMS via the mobile network to the authentication system, and the authentication system performs a query to this mobile network to validate the subscriber and resolve the subscriber and device identifiers. The device receives network access information from the authentication system, allowing it to generate network access credentials on an on-going basis. This is permanent unless the registration is revoked due, for example, to the device being stolen. The network access information may be provided by the authentication system generating and signing a unique subscriber certificate during registration, and the device downloading it. The device uses the signed certificate to generate and encrypt the network access credentials for the network access.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09288671&OS=09288671&RS=09288671
owner: ACCURIS TECHNOLOGIES LIMITED
number: 09288671
owner_city: Dublin
owner_country: IE
publication_date: 20120615
---
There are various constraints which arise from use of some mobile devices including some smartphones. For example at present some mobile devices are not programmed to perform Extensible Authentication Protocol EAP authentication and indeed some Wi Fi networks also do not support EAP.

Also many devices do not permit third party software access to the SIM for the purpose of SIM authentication. In particular at least one type of device does not even allow access to the SIM to read parameters such as the IMSI.

Most public Wi Fi networks such as those run by WISPs do not support IEEE 802.1x. But most WISPs support capability which is best described as WBA s WISPr 1.0. WISPr allows smart clients running on mobile devices to automate the procedure of logging onto Wi Fi services. WISPr 1.0 enables this logging in as a HTTP procedure using username password as the end user identity.

WO2010 115455 Togewa Holding AG describes a method and system for authenticating a network node in a UAM based WLAN network.

The invention is directed towards achieving more versatile authentication of mobile devices including phones PDAs and laptops in wireless local area networks. Another object is to provide a technical architecture to enable more transparent and faster WLAN access as seen by the subscriber.

According to the invention there is provided a wireless network access method performed by a subscriber device subscribed to a mobile network a WLAN and an authentication system the method comprising the steps of 

By having a once off registration the process of logging on to WLANs is much simpler than heretofore as registration is not required every time. It is envisaged that the registration will last until there is a major event such as theft of the device and cancellation or re setting of a subscriber account or SIM.

In one embodiment the device downloads client software and said client software performs the device part of the registration phase and the device network access operations.

In one embodiment the authentication system generates and signs a unique subscriber certificate during registration and the device downloads it as part of said network access information.

In one embodiment the device uses said certificate to generate and encrypt the network access credentials during the network access phase. In one embodiment the registration data is sent in a MO SMS. In one embodiment the certificate includes both subscriber and device identifiers.

Preferably the method includes the step of the device sending a token to the authentication system the authentication system using the token to sign the certificate and the device using the token to subsequently retrieve the signed certificate. In one embodiment the token is a nonce with a globally unique identifier GUID unique reference number.

In one embodiment during the network access phase the device automatically discovers a preferred WLAN service.

In one embodiment the discovery is performed using network selection data included in the network access information. In one embodiment the network selection data includes service set identifiers SSIDs.

In one embodiment the device generates the network access credentials transparently to the subscriber.

In one embodiment the network access credentials are transported using the RADIUS or the DIAMETER protocols.

In one embodiment the network access credentials are not stored being algorithmically generated for every network access.

In one embodiment the method comprises the further step of an application on the device using the received network access information to communicate with a server in the same trusted domain.

In one embodiment the device includes a plurality of applications adapted to use the received network access information to authenticate itself to a server in the same trusted domain.

In another aspect the invention provides a subscriber mobile device comprising a processor a radiation transmitter and a radiation receiver wherein the processor is adapted to perform device registration and network access steps of a method as described in any embodiment.

In another aspect the invention provides an authentication system comprising a processor an interface for communication with wireless local area networks and an interface for communication with a subscriber mobile network wherein the processor is adapted to perform authentication system registration and network access steps of a method as described in any embodiment.

In another aspect the invention provides a computer readable medium comprising software code adapted to be read by a digital processor to perform the device registration and network access steps as described in any embodiment.

In another aspect the invention provides a computer readable medium comprising software code adapted to be read by a digital processor to perform the authentication system registration and network access steps as described in any embodiment.

Referring to for a wireless local area network WLAN access and authentication equipment includes a subscriber device having connectivity software client. Also there is an 802.11 wireless local area network WLAN with an access point an access gateway AGW and a proxy AAA server . Finally there is an authentication system with a short message gateway an AAA server and a PKI server .

The authorisation system also referred to in this specification as AccuROAM communicates with the subscriber s 3GPP 3GPP2 home mobile network having the conventional network elements namely an MSC a VLR an SMSC a HLR a billing server and a GGSN.

The device client software is designed to run as a smart Wi Fi connection manager to deliver seamless attachment to owned and roaming partner Wi Fi networks hotspots . It works with almost all currently available mobile devices phones tablets laptops etc. with operating systems such as Apple iOS Android 2.2 RIM and Windows .

The authorisation system is depicted as including physically separate servers however they may be logical blocks on a fewer number of items of hardware.

The invention allows a user to be identified and authenticated as if they were on a roaming partner 3GPP 3GPP2 network and the traffic usage generated by the user is cleared and settled in a wholesale process in the manner of GSMA CIBER data clearing. Roaming subscribers have an automated Wi Fi attachment to a partner WISP to provide the subscriber with the same automated roaming experience to 3GPP 3GPP2 mobile network roaming access. In the 3GPP 3GPP2 roaming experience the subscriber is automatically authenticated and attached to the roaming partner s visited network. and their usage is cleared and settled between their operator and their roaming partner.

Thus after initial service registration when a user enters a WLAN the device automatically logs on in a manner which is completely transparent to the user not requiring the user to enter any logon details such as username and password. This is analogous to 3GPP 3GPP2 roaming.

Moreover the device sends a username and password so that the WLAN equipment can handle the access request using RADIUS.

The client software generates the logon username password credentials each time and so they are not saved anywhere. Also when the credentials are sent they are encrypted. There is no session key and the credentials are derived from information elements within the certificate.

This ability to automatically generate the credentials using the stored certificate on an ongoing basis is very advantageous. It does not require manual input by the subscriber and so it may be used by an application on the device to perform mutual authentication with a server that is in the same trusted domain. An example is a VoIP server. The device may include a number of applications each adapted to use the received network access information to authenticate itself to a server in the same trusted domain.

The invention allows the subscribers and operators to exploit the large choice of open IEEE 802.11 compliant Wi Fi networks worldwide. It allows their subscribers to gain Wi Fi access to these networks but with authentication of those subscribers. It allows smartphones to automatically roam onto international partners Wi Fi networks for data offload from the partners cellular systems. The subscriber s experience should be as seamless and automatic as standard cellular roaming.

The authentication system utilizes existing IP and SS7 connectivity and includes a database of international roaming partners Wi Fi network information regarding access authentication and billing. The authentication system acts as a roaming hub for bi lateral operators.

Referring to the subscriber signs up for the service by downloading not shown a client from an application store. This can be done before or during registration.

There is a once off registration phase in which the device sends registration data in a MO SMS via the mobile network to the authentication system and the authentication system performs a query to the mobile network to validate the subscriber and resolve the subscriber and device identifiers. The device receives network access information from the authentication system allowing it to generate network access credentials on an on going basis. This is permanent unless the registration is revoked due for example to the device being stolen.

The network access information may be provided by the device sending a Certificate Signing Request CSR and the authentication system generating and signing a unique subscriber certificate and the device downloading it. The device uses the signed certificate to generate and encrypt the network access credentials for the network access.

An advantageous aspect is that the device sends a token to the authentication system and the authentication system uses the token to sign the certificate and the device uses the token to subsequently retrieve the signed certificate. Also the device automatically discovers a preferred WLAN service during roaming using network selection data service set identifiers SSIDs included in the network access information. Advantageously the device generates the network access credentials transparently to the subscriber.

The device then under control of the client sends an SMS message via its associated mobile network including its identifier the MSISDN MDN its public key and a nonce for the registration. The nonce is the token referred to above and is a globally unique identifier. GUID . The nonce is a randomly generated number or string of characters used for the purpose of registration as an additional security measure to ensure the SMS and the POST are from the same entity . There is an optional Registration Confirmation MT SMS issued by the server otherwise the Registration SMS is in one direction only and is used to ensure the client information is routed through the SS7 network which implies it was authenticated via its mobile authentication server.

The MO SMS is received by the short message gateway which resolves the IMSI MIN from the mobile network s HLR or HSS validates the subscriber and forms the MSISDN MDN to IMSI MIN association.

The server then generates a certificate with a key for encrypting the identifier information. The client performs a HTTPs POST to a URL hosted by the server to retrieve the signed certificate. As part of the response to the HTTPs POST the server returns the signed certificate for the authentication requests. This is stored by the device in its keychain vault which is secure. The device then fetches its Wi Fi profile from the server .

Referring to after initial registration the device roams into a Wi Fi network the network access server of which requests the device to logon. The client s response includes encrypted credentials which are passed to the authentication system via HTTP RADIUS interworking. The authentication system decrypts the credentials and checks its authenticity. If authentic the network access server grants access to the device and service begins.

Upon successful authentication the invention achieves Wi Fi hotspot roaming location management and list distribution to allow a mobile service provider MSP to control the Wi Fi partner network and locations to which the subscriber attaches. A WLAN roaming database installed with the device client. The WLAN roaming database is exchanged via HTTPs requests between client and server.

It will be appreciated from the above that the method relates authentication and encryption key data and X.509 certificate based authentication to mobile subscription MS by 

To recap WISPr LO is widely deployed in public Wi Fi networks. WISPr 1.0 is designed and intended to be implemented within a smart client that automatically conducts the username password login over the Wi Fi Access Service Network. Of course there is a known weakness in relying on the login credentials of username password MAC address or even just username password. Mobile service providers want to eliminate this weakness.

For devices that allow the client to read IMSI MIN the client will read and check the IMSI MIN against the IMSI MIN value in the MS Digital Certificate. If these do not agree the client will where possible on the device present a UI pop up informing the end user that they are using a different UICC to the one used in registration.

For devices that prohibit the client to read IMSI MIN there is a potential security issue whereby the end user can remove the UICC from a device but this device will continue to authenticate successfully for the AccuROAM service.

To mitigate this risk the IMSI MIN tracking capability in AccuROAM which keeps track through the mobile network of end users IMEI MEID and IMSI MIN pairings can be used to detect changes of IMEI MEID and IMSI MIN pairings and then trigger a Re registration process by the device client.

The invention is not limited to the embodiments described but may be varied in construction and detail.

