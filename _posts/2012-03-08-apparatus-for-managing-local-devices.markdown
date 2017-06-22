---

title: Apparatus for managing local devices
abstract: An apparatus for managing local devices, wherein the apparatus is operatively connectable with a network to manage network traffic. The apparatus can include computer instructions to identify and track a Media Access Control identifier using the network. The apparatus can also include computer instructions to direct traffic to a path associated with the Media Access Control identifier, computer instructions to measure the bit rate passing through the path associated with the Media Access Control identifier; and computer instructions to adjust the bit rate allowed to pass through the path. The decision to adjust the bit rate allowed to pass through the path can be determined using rolling quotas.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09325514&OS=09325514&RS=09325514
owner: Mesh Networks, LLC
number: 09325514
owner_city: Houston
owner_country: US
publication_date: 20120308
---
A need exists for an apparatus that can function as an isolated system on a local area network in an efficient inexpensive way.

A further need exists for an apparatus that can function in an unobtrusive way and manages network traffic in an efficient manner.

Before explaining the present apparatus in detail it is to be understood that the apparatus is not limited to the particular embodiments and that it can be practiced or carried out in various ways.

The apparatus for managing local devices can be operatively connectable with a network to manage network traffic.

The apparatus can include computer instructions to identify and track a client of a network. The apparatus can be configured to sniff and filter portions of upstream traffic for the Media Access Control MAC identifier and Internet Protocol IP address are tracked against the Media Access Control identifier. The logic that the computer instruction to identify and track a client of the network is as follows network client interfaces are identified by MAC address the IP address is used to identify traffic for different levels of priority or bandwidth constraints. However the IP address associated with a network interface thus MAC address may change. This system tracks the changes so that statistics used in determining service levels are maintained across IP addresses changes.

Accordingly the Internet Protocol Addresses can be tracked and associated with the Media Access Control identifier.

The apparatus can include computer instructions to direct traffic to a path associated with the client. To direct traffic the computer instructions can perform a multi tier hashing algorithm to sort packets to quality of service queues for scalability to very large sites. The multi tier hashing algorithm can first sort the Internet Protocol addresses based on the first set of numbers before the first period and assign the Internet Protocol addresses to appropriate first stage queue. The multi tier hashing algorithm can perform a second sort of Internet Protocol addresses within each of the first stage queues based on the numbers of the Internet Protocol addresses that follow the first period and precede the second period and assign the Internet Protocol addresses to appropriate second stage queue. The multi tier hashing algorithm can perform a third sort of Internet Protocol addresses within each of the second stage queues based on the numbers of the Internet Protocol addresses that follow the second period and precede the third period and assign the Internet Protocol addresses to appropriate third stage queue. The multi tier hashing algorithm can perform a serial sort of the Internet Protocol addresses within each of the third stage queues based on the numbers of the Internet Protocol addresses that follow the third period and assign the Internet Protocol addresses to a traffic path associated with the Media Access Control identifier.

The apparatus can also include computer instructions to measure the bit rate traveling through the traffic paths associated with the Media Access Control identifier of the client. The measuring of bit rate traveling through the traffic paths can be accomplished using techniques that would be known to one skilled in the art with the aid of this disclosure. For example data transiting the system with a sliding time window is used to make decisions in the system. The bytes counts for a given IP address are sampled on a periodic basis. A fixed number of these samples constitute the time window. A new sample is added and one discarded per each sample period. The window total is then recalculated. The apparatus can also include computer instructions to adjust the bit rate and priority of traffic on the paths associated with the Media Access Control identifier. For example each path has queues associated on which Quality of Service algorithms supporting priorities and bit rate limits are implemented. The algorithms include but are not limited to Weighted Round Robin and Exponential Weighted Moving Average. The apparatus allows the ability to track network information and the ability to adjust the bit rate available to each Media Access Control identifier using rolling quotas thereby creating fairness and preventing system abuse.

Two paths can be associated with each Media Access Control identifier. A first path can be incoming traffic and a second path can be outgoing traffic. The apparatus can include computer instructions to sniff and filter traffic in the second path. For example outgoing data can be sniffed to provide notification of new client interfaces and their associated addresses and outgoing data can be also sniffed to track IP address changes on existing client interfaces.

The apparatus can also include computer instructions to compile reports on the traffic associated with each Media Access Control identifier. The reports can be compiled in Extensible Markup Language XML .

The apparatus can be configured to identify and track a plurality of Media Access Control identifiers.

The apparatus can include a management interface. The management interface can be a configuration software file that reads high limits low limits duration of window ingoing network interfaces outgoing network interfaces quota time windows quota threshold values. The management interface can provide a graphical representation of the high limits low limits duration of window ingoing network interfaces outgoing network interfaces quota time windows quota threshold values or combinations thereof.

Turning now to the Figures depicts a schematic of a communication system with an apparatus for managing network traffic in communication therewith.

The communication system can include a wide area network a router an apparatus a local access network and one or more client devices such as a first client device a second client device and a third client device .

The wide area network can be in communication with the router . The apparatus can be connected between the router and the local access network . The apparatus can manage the amount of traffic that the first client the second client device and the third client device are allowed to use.

The non volatile storage can also include computer instructions to direct traffic to a path associated with the Media Access Control identifier .

The non volatile storage can include computer instructions to measure the bit rate passing through the path associated with the Media Access Control identifier .

The non volatile storage can also include computer instructions to adjust the bit rate allowed to pass through the path .

The non volatile storage can also include computer instructions to sniff and filter traffic in the second path .

The non volatile storage can also include computer instructions to compile reports on the traffic associated with the Media Access Control identifier .

The non volatile storage can also include information . The information can be basic network identification normal and penalty limits and quota window period and thresholds.

The apparatus can also have volatile memory that can record information from the network . The information Media Control Identifiers IP addresses and samples get totaled to calculate the quota period counts.

The apparatus can also include a first bi directional port and a second bi directional port . The apparatus can use the network to acquire the information from the network . The apparatus can have additional hardware known to those skilled in the art which allows for control of the bit rate flowing therethrough.

The traffic control engine can include a first path and a second path . A first sorter can sort traffic in the first path . The traffic in the first path can be sorted into a first queue a second queue or a third queue based on the Internet Protocol addresses associated with the traffic. The first queue can be associated with a first Internet Protocol address and a second Internet Protocol address associated with a first Media Access Control identifier . The second queue can be associated with a third Internet Protocol address associated with a second Media Access Control identifier . The third queue can be associated with a fourth Internet Protocol address associated with a third Media Access Control identifier .

The traffic control engine can also include a second path . The second path can include a sniffer and a filter . The sniffer and filter can selectively inspect and filter data on Internet protocol addresses and Media Access Control identifiers associated with traffic transferred in the path. The sniffer checks the IP addresses against existing MAC in the new system or new clients and their associated MAC IPs.

A second sorter can be in communication with the second path . The second sorter can sort the traffic into a fourth queue a fifth queue and a sixth queue based on the Internet Protocol addresses associated with the traffic. The fourth queue can be associated with a first Internet Protocol address and a second Internet Protocol address associated with a first Media Access Control identifier . The fifth queue can be associated with a third Internet Protocol address associated with a second Media Access Control identifier . The sixth queue can be associated with a fourth Internet Protocol address associated with a third Media Access Control identifier .

A counter can monitor and count the traffic in the queues and . The counter can transfer the acquired data to a decision engine . The decision engine can determine if the traffic associated with the queues are above a data quota based on the data transferred thereto. The decision engine can issue command to decrease or increase the data allowed to be transferred through each queue and . The decision engine can make the decisions using a rolling quota.

A reporting engine can store data transferred to and sent from the decision engine . The reporting engine can send the information to a management interface . The information can be organized as XML or JSON and queried through a REST interface. The traffic control engine can also include non volatile storage .

The usage can be calculated in intervals. The intervals can be every 15 minutes one hour one day or other unit of time. Usage for a quota interval also called a window is recalculated frequently in comparison with the quota interval every minute for example. If the recalculated traffic count for the preceding interval exceeds the quota limit the traffic rate limit is set to the penalty value. If in a future recalculation the traffic for the preceding interval falls below the quota limit the traffic rate limit is set to the normal non penalty value.

The rolling quota is able to punish automated traffic that is often associated with file sharing or other automated usage of data. The rolling quota can control automated file sharing without having to identify of the file sharing software. It does so by selecting quota intervals that exceed the amount of time a human will engage or desire to engage in continuous high bandwidth activity. Humans that engage in high bandwidth activity for unusually long periods of time or automated software that engages in high or unlimited bandwidth activity for very long or unlimited periods of time are penalized. As the rolling quota uses only network statistics as opposed to deeper inspection of the network traffic the systems employed can be efficient and inexpensive.

While these embodiments have been described with emphasis on the embodiments it should be understood that within the scope of the appended claims the embodiments might be practiced other than as specifically described herein.

