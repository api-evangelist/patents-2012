---

title: System and method for distributed multi-processing security gateway
abstract: A system and method for a distributed multi-processing security gateway establishes a host side session, selects a proxy network address for a server, uses the proxy network address to establish a server side session, receives a data packet, assigns a central processing unit core from a plurality of central processing unit cores in a multi-core processor of the security gateway to process the data packet, processes the data packet according to security policies, and sends the processed data packet. The proxy network address is selected such that a same central processing unit core is assigned to process data packets from the server side session and the host side session. By assigning central processing unit cores in this manner, higher capable security gateways are provided.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08464333&OS=08464333&RS=08464333
owner: A10 Networks, Inc.
number: 08464333
owner_city: San Jose
owner_country: US
publication_date: 20120110
---
This application is a continuation of co pending U.S. patent application entitled System and Method for Distributed Multi Processing Security Gateway Ser. No. 13 284 869 filed on Oct. 29 2011 which in turn is a continuation of U.S. patent application Ser. No. 11 947 755 filed on Nov. 29 2007 now U.S. Pat. No. 8 079 077 which in turn is a continuation in part of U.S. patent application Ser. No. 11 501 607 filed on Aug. 8 2006 now U.S. Pat. No. 8 332 925.

This invention relates generally to data networking and more specifically to a system and method for a distributed multi processing security gateway.

Data network activities increase as more and more computers are connected through data networks and more and more applications utilize the data networks for their functions. Therefore it becomes more important to protect the data network against security breaches.

There are currently many security gateways such as firewalls VPN firewalls parental control appliances email virus detection gateways special gateways for phishing and spyware intrusion detection and prevention appliances access control gateways identity management gateways and many other types of security gateways. These products are typically implemented using a general purpose micro processor such as Intel Pentium an AMD processor or a SPARC processor or an embedded micro processor based on RISC architecture such as MIPS architecture PowerPC architecture or ARM architecture.

Micro processor architectures are limited in their processing capability. Typically they are capable of handling up to a gigabit per second of bandwidth. In the past few years data network bandwidth utilization increases at a pace faster than improvements of micro processor capabilities. Today it is not uncommon to see multi gigabit per second of data network bandwidth utilization in many medium and large secure corporate data networks. It is expected such scenarios to become more prevailing in most data networks including small business data network residential networks and service provider data networks.

The trend in the increasing usage of data networks illustrates a need for better and higher capable security gateways particularly in using multiple processing elements each being a micro processor or based on micro processing architecture to work in tandem to protect the data networks.

A system and method for a distributed multi processing security gateway establishes a host side session selects a proxy network address for a server uses the proxy network address to establish a server side session receives a data packet assigns a central processing unit core from a plurality of central processing unit cores in a multi core processor of the security gateway to process the data packet processes the data packet according to security policies and sends the processed data packet. The proxy network address is selected such that a same central processing unit core is assigned to process data packets from the server side session and the host side session. By assigning central processing unit cores in this manner higher capable security gateways are provided.

System and computer program products corresponding to the above summarized methods are also described and claimed herein.

In one embodiment secure data network is a residential data network. In one embodiment secure data network is a corporate network. In one embodiment secure data network is a regional corporate network. In one embodiment secure data network is a service provider network.

In one embodiment security gateway is a residential broadband gateway. In one embodiment security gateway is a corporate firewall. In one embodiment security gateway is a regional office firewall or a department firewall. In one embodiment security gateway is a corporate virtual private network VPN firewall. In one embodiment security gateway is an Internet gateway of a service provider network.

When host inside secure data network accesses a server outside secure data network host establishes a session with server through security gateway . Data packets exchanged within the session between host and server pass through security gateway . Security gateway applies a plurality of security policies during processing of the data packets within the session. Examples of security policies include network address protection content filtering virus detection and infestation prevention spyware or phishing blocking network intrusion or denial of service prevention data traffic monitoring or data traffic interception.

In one embodiment a security policy is to protect network address of host . Host uses a host network address in a session between host and server . In one embodiment the host network address includes an IP address of host . In another embodiment the host network address includes a session port address of host .

Security gateway protects host by not revealing the host network address . When host sends a session request for session to security gateway the session request includes host network address .

Security gateway establishes host side session with host . Host uses host network address in host side session .

Security gateway selects a proxy network address . Security gateway uses proxy network address to establish server side session with server .

Server side session is the session between security gateway and server . Host side session is the session between security gateway and host . Session includes server side session and host side session .

Security gateway performs network address translation NAT process on session . Security gateway performs network address translation process on data packets received on server side session by substituting proxy network address with host network address . Security gateway transmits the translated data packets onto host side session . Similarly security gateway performs network address translation process on data packets received on host side session by substituting host network address with proxy network address . Security gateway transmits the translated data packets onto server side session .

In one embodiment session is a transmission control protocol TCP session. In one embodiment session is a user datagram protocol UDP session. In one embodiment session is an internet control messaging protocol ICMP session. In one embodiment session is based on a transport session protocol on top of IP protocol. In one embodiment session is based on an application session protocol on top of IP protocol.

Host sends a session request for establishing a session with server . Session is a TCP session. Session request includes host network address and server network address . Security gateway receives session request . Security gateway extracts host network address from session request . Security gateway determines a proxy network address . In one embodiment host network address includes a host s IP address and security gateway determines a proxy IP address to substitute host s IP address. In one embodiment host network address includes a host s TCP port number and security gateway determines a proxy TCP port number to substitute host s TCP port number. Security gateway extracts server network address from session request . Security gateway establishes a server side session with server based on server network address and proxy network address . Server side session is a TCP session.

After establishing server side session and host side session security gateway processes data packets from server side session and host side session .

In one embodiment security gateway receives a data packet from server side session . Data packet includes server network address and proxy network address . Security gateway extracts server network address and proxy network address . Security gateway determines host side session based on the extracted network addresses. Security gateway further determines host network address from host side session . Security gateway modifies data packet by first substituting proxy network address with host network address . Security gateway modifies other parts of data packet such as TCP checksum IP header checksum. In one embodiment security gateway modifies payload of data packet by substituting any usage of proxy network address with host network address .

After security gateway completes modifying data packet security gateway transmits the modified data packet onto host side session .

In a similar fashion security gateway receives a data packet from host side session . Data packet includes server network address and host network address . Security gateway extracts server network address and host network address . Security gateway determines server side session based on the extracted network addresses. Security gateway further determines proxy network address from server side session . Security gateway modifies data packet by first substituting host network address with proxy network address . Security gateway modifies other parts of data packet such as TCP checksum IP header checksum. In one embodiment security gateway modifies payload of data packet by substituting any usage of host network address with proxy network address .

After security gateway completes modifying data packet security gateway transmits the modified data packet onto server side session .

In one embodiment security gateway is a distributed multi processing system. Security gateway includes a plurality of processing elements. A processing element includes a memory module. The memory module stores host network addresses proxy network addresses and other information for processing element to apply security policies as described in . Processing element has a processing element identity .

In one embodiment illustrated in processing element is a central processing unit CPU core in a multi core processor which combines two or more independent cores. In one embodiment multi core processor is a dual core processor such as Intel s Core 2 Duo processor or AMD s Athlon dual core processor. In one embodiment multi core processor is a quad core processor such as Intel s quad core Xeon series processor or AMD s Opteron Quad Core processor.

In one embodiment security gateway includes a plurality of multi core processors wherein processing element is a multi core processor.

In one embodiment processing element is a packet processing module within a network processor such as Intel s IXP2855 or IXP2805 network processor. AMD s Au1500 processor or Cavium s Octeon MIPS64 network processor.

Security gateway includes a dispatcher . Dispatcher receives a data packet and determines a processing element to process the data packet. Dispatcher typically calculates a processing element identity based on the data packet. Based on the calculated processing element identity security gateway assigns the data packet to the identified processing element for processing.

In one embodiment dispatcher receives a data packet from host side session and calculates a first processing element identity based on the host network address and server network address in data packet . In another embodiment dispatcher receives a data packet from server side session and calculates a second processing element identity based on the proxy network address and server network address in data packet .

Security gateway includes a network address selector . Network address selector selects a proxy network address based on network information. The network information includes a host network address obtained in a session request for session and a security gateway network address. Other types of network information may also be used. The proxy network address is used to establish server side session . The proxy network address is selected such that the first processing element identity and the second processing element identity calculated by dispatcher are the same. In other words a same processing element is assigned to process data packet from server side session and data packet from host side session .

In one embodiment the proxy network address is selected such that the first processing element identity calculated by dispatcher identifies a processing element that has the lightest load among the plurality of processing elements. In one embodiment the load is based on processor idle time of the processing element. In one embodiment the load is based on active sessions for the processing element. In one embodiment network address selector obtains load from a processing element over an Application Programming Interface API . In one embodiment network address selector obtains load from the memory module of a processing element. In one embodiment the proxy network address is selected such that the second processing element identity calculated by dispatcher identifies a processing element that has the lightest load among the plurality of processing elements.

In one embodiment the proxy network address is selected such that the first processing element identity calculated by dispatcher identifies a processing element with a functional role. In one embodiment the function role includes the processing of a security policy. In one embodiment network address selector obtains the function role of a processing element through a registration process or an Application Programming Interface API . In one embodiment network address selector obtains the functional role from the memory module of the processing element.

Dispatcher calculates a processing element identity based on two network addresses obtained from a data packet of session . Session includes host side session and server side session . The two network addresses of host side session are server network address and host network address. The two network addresses of server side session are proxy network address and server network address. Dispatcher calculates to the same processing element identity for host side session and server side session .

In one embodiment dispatcher computes a sum by adding the two network addresses. In one example dispatcher computes a sum by performing a binary operation such as an exclusive or XOR binary operation or an and AND binary operation onto the two network addresses in binary number representation. In one example dispatcher computes a sum by first extracting portions of the two network addresses such as the first 4 bits of a network address and applies an operation such as a binary operation to the extracted portions. In one example dispatcher computes a sum by first multiplying the two network addresses by a number and by applying an operation such as addition to the multiple.

In one embodiment dispatcher computes a processing element identity by processing on the sum. In one embodiment there are 4 processing elements in security gateway . In one example dispatcher extracts the first two bits of the sum and interprets the extracted two bits as a numeric number between 0 and 3. In one example dispatcher extracts the first and last bit of the sum and interprets the extracted two bits as a numeric number between 0 and 3. In one example dispatcher divides the sum by 4 and determines the remainder of the division. The remainder is a number between 0 and 3.

In one embodiment security gateway includes 8 processing elements. Dispatcher extracts 3 bits of the sum and interprets the extracted three bits as a numeric number between 0 and 7. In one example dispatcher divides the sum by 8 and determines the remainder of the division. The remainder is a number between 0 and 7.

In one embodiment a network address includes an IP address and a session port address. Dispatcher computes a sum of the IP addresses and the session port addresses of the two network addresses.

Though the teaching is based on the above description of hashing functions it should be obvious to the skilled in the art to implement a different hashing function for dispatcher .

Network address selector selects a proxy network address for a host network address . In one embodiment host network address includes a host IP address and a host session port address proxy network address includes a proxy IP address and a proxy session port address . Proxy network address is selected such that dispatcher calculates to the same processing element identity on host side session and server side session .

In one embodiment the selection process is based on the dispatching process illustrated in . In one example dispatcher uses the method of computing the sum of two IP addresses and two session port addresses and then divides the sum by 4. In one embodiment network address selector first selects proxy IP address . Network address selector then selects proxy session port address such that when using the method on server network address and host network address dispatcher calculates the same processing element identity as when using the method on server network address and proxy network address .

In one example dispatcher computes a sum from a binary operator XOR of the two network addresses and extracts the last 3 digits of the sum. Network address selector selects a proxy session port address that has the same last 3 digits of the host session port address .

In one embodiment security gateway performs network address translation process for a plurality of existing sessions. Network address selector checks if the selected proxy network address is not used in the plurality of existing sessions. In one embodiment security gateway includes a datastore . Datastore stores a plurality of proxy network addresses used in a plurality of existing sessions. Network address selector determines the selected proxy network address is not used by comparing the selected proxy network address against the stored plurality of proxy network addresses and not finding a match.

In one embodiment a processing element includes network address selector. A processing element receives a data packet assigned by security gateway based on a processing element identity calculated by dispatcher. In one embodiment the processing element determines that the data packet includes a session request. The network address selector in the processing element selects a proxy network address based on the host network address in the session request as illustrated in .

In one embodiment a particular first processing element includes network address selector. A second processing element without network address selector receives a data packet and determines that the data packet includes a session request. The second processing element sends the data packet to the first processing element using for example a remote function call. The first processing element receives the data packet. The network address selector selects a proxy network address based on the host network address in the session request.

In one embodiment datastore is implemented in the memory module of a processing element. In one embodiment the plurality of proxy network addresses in datastore are stored in each of the memory modules of each of the processing elements. In one embodiment the plurality of proxy network addresses in datastore are stored in the memory modules in a distributive manner with the proxy network addresses used in the sessions processed by a processing element stored in the memory module of the processing element.

In one embodiment security gateway includes a memory shared by the plurality of processing elements. Security gateway partitions the shared memory into memory regions. A processing element has access to a dedicated memory region and does not have access to other memory regions.

In one embodiment security gateway includes a central processing unit. In one embodiment the central process unit includes a plurality of processing threads such as hyper thread micro engine or other processing threads implemented in circuitry such as application specific integrated circuit ASIC or field programmable gate array FPGA . A processing element is a processing thread.

In one embodiment a central processing unit includes a plurality of micro processor cores. A processing thread is a micro processor core.

In one embodiment a security policy is for virus detection or blocking. In one embodiment a security policy is for phishing detection or blocking. In one embodiment a security policy is for traffic quota enforcement. In one embodiment a security policy is for lawful data interception.

In one embodiment the NAT process is for a UDP session. In one embodiment security gateway receives a UDP packet. In one embodiment security gateway determines that the UDP packet is not from an existing session. Security gateway processes the UDP packet as a session request.

In one embodiment the NAT process is for an ICMP session. In a similar fashion security gateway processes an ICMP packet from a non existing session as a session request.

Although the present invention has been described in accordance with the embodiments shown one of ordinary skill in the art will readily recognize that there could be variations to the embodiments and those variations would be within the spirit and scope of the present invention. Accordingly many modifications may be made by one of ordinary skill in the art without departing from the spirit and scope of the appended claims.

