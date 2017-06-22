---

title: System and method for protecting certificate applications using a hardened proxy
abstract: A system for preventing computer software from communicating from a user computer in a network to untrusted remote computers. A host-based credential management agent is operably connected to a user computer for intercepting network traffic information from the user computer and transmitting a network request including credentials of the remote computer and the network traffic information. A trusted credential database contains information identifying trusted entities and corresponding cryptographic certificates. A server cooperates with the management agent for i) verifying whether the user computer in the network request should have network access, and ii) cryptographically signing the intercepted network traffic information with an authorization server key, to authorize network access for the intercepted information. A firewall is operably connected to the user computer and the authorization server. It is configured to inspect the traffic information from the user computer and reject any traffic information not signed with the key.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08661246&OS=08661246&RS=08661246
owner: Rockwell Collins, Inc.
number: 08661246
owner_city: Cedar Rapids
owner_country: US
publication_date: 20120409
---
The present invention relates generally to communication networks and more particularly to an enhanced system for protecting communication networks from communication with malicious remote entities.

Networked applications commonly use certificates to verify the integrity of remote entities and the integrity and confidentiality of communications to from the remote location. However vulnerability exists in that the local trust databases containing roots of trust chain may be subverted or modified by unwitting or malicious users or software. This may result in the insertion of trust roots which are not trustworthy with respect to enterprise policy. This results in the local user or software placing trust in non trustworthy communications documents or remote locations.

U.S. Publicn. No. 2005 0262558 entitled ON LINE CENTRALIZED AND LOCAL AUTHORIZATION OF EXECUTABLE FILES discloses a system and method for controlling the execution of executable files. The executables are identified by either a cryptographic digest or a digital certificate. The cryptographic digest is computed from the binary image of the executable. An executable that is attempting to execute is intercepted by a protection module that consults a database of stored rules over a secure channel to determine whether or not the executable can be identified as a permitted executable and whether or not it has permission to execute on a particular computer system under certain specified conditions. If a stored permission is available it is used to control the execution. Otherwise the user is consulted for permission.

U.S. Publicn. No. 2010 0077445 entitled GRADUATED ENFORCEMENT OF RESTRICTIONS ACCORDING TO AN APPLICATION S REPUTATION discloses security software on a client that observes a request for a resource from an application on the client and then determines the application s reputation. The application s reputation may be measured by a reputation score obtained from a remote reputation server. The security software determines an access policy from a graduated set of possible access policies for the application based on the application s reputation. The security software applies the access policy to the application s request for the resource. In this way the reputation based system uses a graduated trust scale and a policy enforcement mechanism that restricts or grants application functionality for resource interactivity along a graduated scale.

In a broad aspect the present invention is a system for preventing computer software from communicating from a user computer in a network to untrusted remote computers. A host based credential management agent is operably connected to a user computer and configured to intercept network traffic information from the user computer and transmit a network request including credentials of the remote computer and the network traffic information. A trusted credential database contains information identifying trusted entities and corresponding cryptographic certificates. An authorization server is operably connected to the host based credential management agent and connected to the trusted credential database. The authorization server is configured to cooperate with the host based credential management agent for i verifying whether the user computer in the network request should have network access and ii cryptographically signing the intercepted network traffic information with an authorization server key to authorize network access for the intercepted network traffic information. A firewall system is operably connected to the user computer and the authorization server. It is configured to inspect the network traffic information from the user computer and reject any traffic information not signed with the authorization server key.

The present invention prevents software from connecting to the outside world by adding connection level authentication and authorization to network traffic.

Referring now to the drawings and the characters of reference marked thereon illustrates the system for preventing computer software located on a user computer in a network from communicating with remote computers presenting untrusted credentials designated generally as 10. The system includes a host based credential management agent a trusted credential database an authorization server and a firewall system . The host based credential management agent is operably connected to a user computer and is configured to intercept network traffic information from the user computer and transmit a network request comprising credentials of the remote computer and the network traffic information. The trusted credential database contains information identifying trusted entities and corresponding credentials. The authorization server is operably connected to the host based credential management agent and connected to the trusted credential database . The authorization server is configured to cooperate with the host based credential management agent for i verifying whether the user computer in the network request should have network access to the remote computer and ii cryptographically signing the intercepted network traffic information with an authorization server key to authorize network access for the intercepted network traffic information. The firewall system is operably connected to the user computer and the authorization server and is configured to inspect the network traffic information from the user computer and reject any traffic information not signed with the authorization server key. A credential is typically a cryptographically signed certificate such as a X.509 certificate or a Kerberos ticket. The present system generally prevents computer software from communicating information from the host computer to an untrusted remote computer .

The host based credential management agent is a software component running on the user host computer. The authorization server can be a software component running on a common computer server or a standalone network appliance a specialized computer system . The firewall system can be a software component providing functionality to a commercially available firewall proxy system a standalone software component running on a computer server or a standalone specialized computer system. The host based credential management agent may be incorporated into the user computer or may be a specialized piece of computer hardware. Thus the phrase that the host based credential management agent is operably connected to the computer is deemed to be broadly construed to encompass both potential scenarios. Furthermore as defined herein the term internet is meant to broadly refer to any internet working between disparate computer networks including the commercial Internet NIPRNet and SIPRNet.

The authorization server may provide the cryptographic signing by signing individual network packets. This may be provided by for example applying internet protocol IP encapsulation by adding a cryptographic hash field to the intercepted network traffic information. Alternatively it may be accomplished by applying an Internet Protocol header field such as an IPv4 header option field or IPv6 header chain field to the intercepted network traffic information. Or such a signing may be accomplished by applying a transport layer wrapping protocol to the intercepted network traffic information.

The authorization server may provide the cryptographic signing by adding a token. This may be by adding a tag value pair to an application layer protocol.

Alternatively the authorization server may provide the cryptographic signing by a decision making technique. Referring now to an example decision making technique designated generally as 21 may be as follows 

a receiving cryptographic signatures of the application and the network traffic information to provide received cryptographic signature and network traffic information process block 

b identifying the credentials of the remote computer the received network traffic information and the received cryptographic signature to provide identified intercepted network information and cryptographic signature process block 

c computing a cryptographic signature of the identified traffic information including user authentication to provide computed cryptographic hash of the identified traffic information process block 

d comparing the credentials of the remote computer computed network traffic information and the cryptographic signature against a whitelist and or a blacklist database or comparing intercepted network information against a whitelist or backlist database to provide compared computed networked information and compared computed cryptographic signature process block and 

e digitally signing the network traffic information only if the credentials of said remote computer compared computed network information and compared computed cryptographic signature are contained in the whitelist and not contained in the blacklist process block .

Referring now to the host based credential management agent may provide monitoring of the network traffic information by the following process designated generally as 

a intercepting the transmit network request or the network traffic information to provide the intercepted transmit network request or the network traffic information process block 

b identifying the credentials of the remote computer of the intercepted network request or the network traffic information to provide identified credentials of said remote computer process block 

c computing a cryptographic hash of the identified information to provide computed cryptographic hash of the network traffic information process block and 

d forwarding the intercepted transmit network request or the network traffic information with the computed cryptographic hash of the identified information to the authorization server process block .

The firewall system of the present invention is designed to properly cooperate with the type of authorization server used. For example if individual network packets are signed by i applying internet protocol IP encapsulation by adding a cryptographic hash field to the intercepted network traffic information or ii by applying an IPv4 header option field or IPv6 header chain field to the intercepted network traffic information then the firewall system may provide inspection of the network traffic information by the process of 

c stripping the signature to restore the request to provide the original state prior to interception by the host based credential management agent and 

d forwarding the original intercepted network traffic information to an internet destination only if the signature is valid.

If the authorization server provides the cryptographic signing by signing individual network packets by applying a transport layer wrapping protocol to the intercepted network traffic information then the firewall system may operate as follows 

c stripping the token to restore the application layer request to provide the original state prior to interception by the host based credential management agent and 

d forwarding the original intercepted network traffic information to internet destination only if the signature is valid.

Other embodiments and configurations may be devised without departing from the spirit of the invention and the scope of the appended claims.

