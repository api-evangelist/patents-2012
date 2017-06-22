---

title: Method and system for abuse route aggregation and distribution
abstract: In one exemplary embodiment, a computer-implemented method includes receiving a request to block a host, wherein the host provides a prohibited content via a computer network. A spider program can verify that the host provides the prohibited content. An abuse route list can be generated. The abuse route list can include an internet protocol address of the host. The abuse route list is provided to a network operator with a computer networking protocol. A search engine of a database of infringing hosts can be provided. The database of infringing hosts can include the internet protocol address of the host. Whether the host provides the prohibited content can be reverified with a third-party review. The host from can be removed from the abuse route list if the third-party review determines that the host does not provide prohibited content.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09071575&OS=09071575&RS=09071575
owner: 
number: 09071575
owner_city: 
owner_country: 
publication_date: 20120420
---
This application claims priority from U.S. Provisional Application No. 61 478 058 entitled METHOD AND SYSTEM FOR ABUSE ROUTE AGGREGATION AND DISTRIBUTION filed Apr. 21 2011. The provisional application is hereby incorporated by reference in its entirety.

This application relates generally to computer networking and more specifically to a system and method for route aggregation and distribution.

As the Internet has grown it has become challenging to mitigate the downloading of illegal material e.g. copyright infringing materials trademark infringing materials child abuse images etc. . While there have been previous attempts at addressing this problem they have in large part been unsuccessful due to the additional overhead imposed by the solution. For example some solutions have lacked transparency and checks and balances added unnecessary latency to legitimate traffic added burdensome costs and architecture upgrades for network operators and have the potential to violate the privacy of the majority of users who are behaving in a legal manner.

Furthermore governments have become concerned about various cyber threats to critical computer infrastructure. For example the Congress of the United States has proposed options to give the United States Federal Government the ability to block sites or countries at the Tier 1 level of the Internet. There has been considerable controversy about this proposal often called The Kill Switch because members of the public are concerned about government control of the Internet.

As used herein the following definitions can be utilized to implement certain example embodiments however other embodiments are not limited in this context.

An application programming interface API can act as middleware between multiple independent systems. An API can also enable separate systems using different hardware and software to communicate with each other e.g. using an agreed upon language .

An autonomous system AS can include a network under the administrative control of one organization that has a standardized routing policy to the Internet. Generally an AS can include multiple links to upstream transit providers and can use border gateway protocol BGP to set routing policy. Autonomous systems can be identified by an autonomous system number ASN .

A black hole e.g. a null route can be an entry in the routing table e.g. a data table stored in a router or a networked computer that lists the routes to particular network destinations that tells a router to drop any traffic to a specified IP address. For example a black hole can be refer to traffic that is silently discarded or dropped without informing the source that the data did not reach its intended recipient.

Border gateway protocol BGP can be a standard routing protocol used for communication between a plurality of autonomous systems.

A botnet can include a collection e.g. many thousands of hosts i.e. a computer connected to the Internet or another IP based network that receive instructions from a central command and control server run by a bot herder e.g. a malicious user who uses automated techniques to scan specific network ranges and determines vulnerable systems such as machines without current security patches on which to install their bot program . Often hosts become bots without the knowledge or permission of their owner due to a virus infection. These bots can receive instructions from the bot herder to attack other sites send spam or are used as a launchpad for other malicious activity.

An end user or client may be an individual or a computer that is connecting outbound to another computer to receive services or download data.

An extranet can be a secured network or a web site that is available to certain specified organizations like between a vendor and the vendor s customers. For comparison purposes an Intranet is a network that is only available within a single organization.

Depending on the context used a host site or node can be any computer connected to a network. For the purposes of this document these terms are used to identify a computer that is being used to serve content to end users or clients.

An internet protocol IP address can be a numerical identifier of a computer connected to a TCP IP network like the Internet. This address can be used to route traffic to and from other computers on a network.

A network operator for the purposes of this document can be an organization that provides services to clients but this may not be their primary business. Examples may be a corporate wide area network WAN a university banking network federal interest computer network or an internet service provider ISP see service provider below .

Peering can be the logical BGP connection between routers on different autonomous systems. Peering can be used to exchange routing information.

A service provider such as an ISP for the purposes of this document can be a company that provides Internet access or hosting for their customers e.g. for a fee . Examples may be cable companies as of the date of the filing of this application like Comcast digital subscriber line DSL companies like Sonic.net or hosting providers like Rackspace.

A route server can be a type of server that acts similarly to an Internet router. A route server can be optimized to store and categorize routes instead of routing traffic. Because a route server can be optimized for route collection aggregation and distribution the route server can be a more efficient solution for our purposes than using an actual router. A route server can create a BGP peering session with routers to send and receive data.

A routing protocol can be a specified standard used by routers to communicate with other routers. Example protocols include routing information protocol RIP open shortest path first OSPF and Border Gateway Protocol BGP .

A spider program hereafter spider also known as a web crawler can be an automated program that follows hyperlinks to search or index hosts for the content contained on them. A spider can include a computer program that gathers and categorizes information on the Internet.

Structured Query Language SQL can be a database computer language for storing large amounts of data in a database. Various SQL database options are available from different vendors.

A uniform resource identifier URI can be a string of characters used to identify a name or a resource. Such identification enables interaction with representations of the resource over a network typically the World Wide Web using specific protocols.

A uniform resource locator URL can be a specific character string that constitutes a reference to an Internet resource. A URL can be a type of URI.

Disclosed are a system method and article of manufacture for aggregating and distributing abuse routes to networks in order to render illegal content e.g. copyright violations unavailable for download or distribution.

In one exemplary embodiment a computer implemented method includes receiving a request to block a host wherein the host provides a prohibited content via a computer network. A spider program is used to verify that the host provides the prohibited content. An abuse route list is generated. The abuse route list includes an internet protocol address of the host. The abuse route list is provided to a network operator with a computer networking protocol. A search engine of a database of infringing hosts is provided. The database of infringing hosts includes the Internet protocol address of the hosts. Whether the host provides the prohibited content is reverified with a third party review.

Optionally a routing table can be generated. The routing table can include an entry for the host. The entry can specify that a data packet addressed to the host be sent to a null route. The host from can be removed from the abuse route list if the third party review determines that the host does not provide prohibited content. The computer network can include the Internet.

Disclosed are a system method and article of manufacture of system and method for abuse route aggregation and distribution. Although the present embodiments have been described with reference to specific example embodiments it will be evident that various modifications and changes may be made to these embodiments without departing from the broader spirit and scope of the particular example embodiment.

Reference throughout this specification to one embodiment an embodiment or similar language means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the present invention. Thus appearances of the phrases in one embodiment in an embodiment and similar language throughout this specification may but do not necessarily all refer to the same embodiment.

Furthermore the described features structures or characteristics of the invention may be combined in any suitable manner in one or more embodiments. In the following description numerous specific details are provided such as examples of programming software modules user selections network transactions database queries database structures hardware modules hardware circuits hardware chips etc. to provide a thorough understanding of embodiments of the invention. One skilled in the relevant art will recognize however that the invention may be practiced without one or more of the specific details or with other methods components materials and so forth. In other instances well known structures materials or operations are not shown or described in detail to avoid obscuring aspects of the invention.

The schematic flow chart diagrams included herein are generally set forth as logical flow chart diagrams. As such the depicted order and labeled steps are indicative of one embodiment of the presented method. Other steps and methods may be conceived that are equivalent in function logic or effect to one or more steps or portions thereof of the illustrated method. Additionally the format and symbols employed are provided to explain the logical steps of the method and are understood not to limit the scope of the method. Although various arrow types and line types may be employed in the flow chart diagrams they are understood not to limit the scope of the corresponding method. Indeed some arrows or other connectors may be used to indicate only the logical flow of the method. For instance an arrow may indicate a waiting or monitoring period of unspecified duration between enumerated steps of the depicted method. Additionally the order in which a particular method occurs may or may not strictly adhere to the order of the corresponding steps shown.

In step the submission of the web site with prohibited content is verified. One or more validation operations can be performed to ensure that the request itself is valid the IP address is valid etc. For example a spider program can check to make sure that the content is in the location provided in step . If the submission request cannot be validated the request can be rejected. Other verification processes such as process of can be implemented as well. Such verification processes can allow for searches of infringing hosts on a database of infringing hosts.

For example an end user can be unable to access a web site. The end user can search a database of blocked websites e.g. by inputting the IP address as a search parameter and determine that the web site is indeed blocked. The end user can then initiate review process. A reviewing entity can be an attorney or other person or organization with knowledge of copyright law for example. The reviewing entity can make a determination as to whether the original reason for the block was valid. If the block is for an invalid reason e.g. there is no copyright violation determined the reviewing entity can request that the block be removed. Alternatively if the block is found to be for a valid reason then the block can be maintained. In some embodiments if an IP address is incorrectly classified then a relevant party e.g. a hosting provider an IP owner and or an end user can appeal to a court mediator arbitrator and or other appropriate authority.

In step a network operator of a relevant AS e.g. the AS that controls the web server where prohibited content is provided can be notified of the submission request. For example a network operator who owns the AS can be notified by an automated email sent to the public registered abuse email address listed for that AS. This email can include details of the complaint and the full location of the prohibited content. This can provide the network operator the ability to address the issue using their own internal process.

It is noted that a network operator with a demonstrated internal abuse protocol e.g. includes an internal abuse team can white listed and or provided a notification with a grace period. For example a grace period can allow a relevant host provider time to remedy the prohibited content issue using an internal process before a block is implemented. The relevant host provider can receive an email notifying the host provider of the prohibited content. The email can state a period by which the host provider can remove the prohibited content. A spider can verify if the internal process has not removed the prohibited content before the host s IP address is distributed to network operators for blocking. In cases where the host provider has an effective abuse team the IP address can be white listed . In this case the host s IP address may not be blocked rather the host provider can be sent email alerts that include information about the prohibited content.

In step the submission can be stored in a specified database e.g. such as the database of . The submission can then be provided to other relevant network operators. For example the submission and verification data can be added to a database of the system of and then distributed to participating network operators by using the route server running BGP. In step a block on the host identified in the submission can be implemented. Various methods e.g. black holing and the like can be utilized to implement the block. In step after a block has been implemented the spider program can periodically check the location of the illegal content targeted by the submission.

In step the block of the host can be removed if the illegal content is removed. For example the spider can automatically remove the block when the content is no longer available. After the black hole has been removed the spider program will continue to check for a specified amount of time and the system can add the black hole again automatically if the content becomes available at that location again.

It should be noted that is some embodiments the systems and functionalities of can also be utilized to implement the various steps of A B. The embodiments are not limited in this context.

It is noted that requests for re evaluation of blocked websites can be scored according to various factors such as the number of requests to re evaluate the blocking of a host etc. For example a host may be blocked according to process . A number of third party users may use the extranet functionality described herein for reviewing infringing hosts. The third party users may re evaluate the block. Consequently the host s re evaluation may be weighted greater than requests for the re evaluation of other websites. The hosts may then be placed in a higher priority status e.g. the website can be placed at the front a queue for re evaluation.

It is noted that the custom BGP feeds can be hierarchical. An example would be the headquarters of a nationwide bank could control the feeds delivered to subordinate banks. In another example a federal agency can determine the custom BGP feeds distributed to all relevant state offices.

It is noted that in some embodiments the above systems and processes can be configured in a manner that isolates an infringing host from the Internet such that the host does not affect other users. The infringing host itself can still access the Internet. Thus the lines of communication may generally remain open between a service provider and the user. A user may be allowed to remedy the issue without a break in service therefore reducing support calls and protecting the service provider s revenue.

At least some values based on the results of the above described processes can be saved for subsequent use. Additionally a computer readable medium can be used to store e.g. tangibly embody one or more computer programs for performing any one of the above described processes by means of a computer. The computer program may be written for example in a general purpose programming language e.g. Pascal C C Java Python or some specialized application specific language PHP Java Script .

Although the present embodiments have been described with reference to specific example embodiments various modifications and changes can be made to these embodiments without departing from the broader spirit and scope of the various embodiments. For example the various devices modules etc. described herein can be enabled and operated using hardware circuitry firmware software or any combination of hardware firmware and software e.g. embodied in a machine readable medium .

In addition it will be appreciated that the various operations processes and methods disclosed herein can be embodied in a machine readable medium and or a machine accessible medium compatible with a data processing system e.g. a computer system and can be performed in any order e.g. including using means for achieving the various operations . Accordingly the specification and drawings are to be regarded in an illustrative rather than a restrictive sense. In some embodiments the machine readable medium can be a non transitory form of machine readable medium.

