---

title: Erasure coding scheme for deadlines
abstract: Error correction coding for streaming communication is provided. A streaming problem is modeled as a non-multicast network problem with a nested receiver structure. Each packet in the streaming problem corresponds to a link, and each deadline in the streaming problem corresponds to a receiver in the non-multicast network problem. For the non-multicast network problem, content to be transmitted in multiple packets to multiple receivers is obtained. Each of the receivers is required to decode specific independent messages from the content, at given time steps, and has access to a subset of the content received by another receiver. The content is allocated into multiple packets to be transmitted on multiple links. No coding occurs across information demanded by different receivers. A capacity region defines a set of information rate vectors that can be communicated to the receivers successfully. A rate vector is successfully communicated if it complies with various inequalities.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08914713&OS=08914713&RS=08914713
owner: California Institute of Technology
number: 08914713
owner_city: Pasadena
owner_country: US
publication_date: 20120924
---
This application claims the benefit under 35 U.S.C. Section 119 e of the following co pending and commonly assigned U.S. provisional patent application s which is are incorporated by reference herein 

Provisional Application Ser. No. 61 538 648 filed on Sep. 23 2011 by Svitlana Vyetrenko Tracey C. Ho Hongyi Yao and Omer Tekin entitled Erasure Coding Scheme for Deadlines .

This application further incorporates by reference Erasure Coding for Real Time Streaming by Derek Leong and Tracey Ho Conference Paper IEEE International Symposium on Information Theory ISIT July 2012 arXiv 1207.3582 cs.IT .

The invention was made with Government support under Grant No. CNS 0905615 awarded by the National Science Foundations and Grant No. FA9550 10 1 0166 awarded by the United States Air Force. The Government has certain rights in this invention.

The present invention relates generally to streaming packets of information and in particular to a method apparatus and article of manufacture for packet erasure error correction coding with a nested receiver structure.

 Note This application references a number of different publications as indicated throughout the specification by reference numbers enclosed in brackets e.g. x . A list of these different publications ordered according to these reference numbers can be found below in the section entitled References. Each of these publications is incorporated by reference herein. 

Embodiments of the invention evaluate packet erasure error correction coding with a nested receiver structure where the set of packets received by each receiver i is a subset of that received by the next receiver i 1. A natural setting in which this type of structure arises is with temporal demands each receiver corresponds to a particular deadline in the received packet stream by which a particular piece of information must be decoded and has access to all earlier observations. The protocol can specify an arbitrary set of deadlines and demands.

The prior art fails to provide the ability to construct codes that can correct any z packet erasures or errors for all feasible information rates without a priori knowledge of which packets will be erased erroneous . By making a connection with prior work of the inventors of the present application on non multicast network error correction one may characterize the capacity region of feasible demand vectors for any given nested structure set of deadlines and any z erasures errors . In particular embodiments of the invention provide a capacity achieving coding scheme where no coding occurs across information demanded by different receivers.

The network error correction problem where transmissions on an unknown set of z links are arbitrarily corrupted was introduced by Cai and Yeung 1 2 and 3 for single source multicast. They characterized the capacity region and showed a connection between network error correction and network erasure correction by generalizing classical coding theory to the network setting. Network coding for multicast packet erasure correction was considered in 4 and 5 . The problem of multicast non coherent error correction where the network topology and or network code are not known a priori was studied in 6 7 8 .

For non multicast networks finding the capacity region of a general network even without errors is an open problem. The error free capacity regions for some special cases such as single source two sink networks 9 10 11 and single source disjoint or nested demand networks 12 with multiple sinks are given by the cutset bounds. On the other hand examples of non multicast networks whose error free capacity regions are not given by cutset bounds appear in 13 and 14 .

For non multicast error correction prior work of the present inventors 15 has shown that unlike the error free case cutset bounds are loose in general for single source two sink networks with errors and refined bounds were developed for non multicast networks. Embodiments of the present invention build on some of the techniques developed in that work.

 16 17 has constructed streaming codes that minimize the delay required to correct burst errors of given length.

Embodiments of the invention provide a coding scheme to correct packet erasures in a streaming scenario where specific information must be decided by given deadlines. The spacing of the deadlines and the amount of information required at each deadline can be arbitrarily specified. Prior art methodologies have not established capacity optimal coding schemes for such a deadline model.

An erasure pattern is a collection of admissible sets of packet erasures such that the demanded information can be recovered by each deadline under any admissible set of erasures. The coding scheme is optimal for a fixed number of erasures in unknown locations and achieves within a constant ratio of the optimal performance for a family of practical erasure patterns.

The coding scheme of embodiments of the invention follows. For a given erasure pattern information from successive deadlines is sequentially allocated across packets such that the information from each deadline is spread as uniformly as possible over multiple packets subject to the packet capacities that remain after allocating information for previous deadlines and any constraints on when certain information is available to the encoder. Sufficient capacity is allocated for each deadline such that the capacity remaining after any admissible set of erasures is at least the amount demanded by that deadline. Coding is carried out only among information corresponding to the same deadline with a generic or maximum distance separable code e.g. random linear coding or Reed Solomon coding.

In the following description reference is made to the accompanying drawings which form a part hereof and which is shown by way of illustration several embodiments of the present invention. It is understood that other embodiments may be utilized and structural changes may be made without departing from the scope of the present invention.

In one embodiment the computer operates by the general purpose processor A performing instructions defined by the computer program under control of an operating system . The computer program and or the operating system may be stored in the memory and may interface with the user and or other devices to accept input and commands and based on such input and commands and the instructions defined by the computer program and operating system to provide output and results.

Output results may be presented on the display or provided to another device for presentation or further processing or action. In one embodiment the display comprises a liquid crystal display LCD having a plurality of separately addressable liquid crystals. Alternatively the display may comprise a light emitting diode LED display having clusters of red green and blue diodes driven together to form full color pixels. Each liquid crystal or pixel of the display changes to an opaque or translucent state to form a part of the image on the display in response to the data or information generated by the processor from the application of the instructions of the computer program and or operating system to the input and commands. The image may be provided through a graphical user interface GUI module . Although the GUI module is depicted as a separate module the instructions performing the GUI functions can be resident or distributed in the operating system the computer program or implemented with special purpose memory and processors.

In one or more embodiments the display is integrated with into the computer and comprises a multi touch device having a touch sensing surface e.g. track pod or touch screen with the ability to recognize the presence of two or more points of contact with the surface. Examples of multi touch devices include mobile devices e.g. iPhone Nexus S Droid devices etc. tablet computers e.g. iPad HP Touchpad portable handheld game music video player console devices e.g. iPod Touch MP3 players Nintendo 3DS PlayStation Portable etc. touch tables and walls e.g. where an image is projected through acrylic and or glass and the image is then backlit with LEDs .

Some or all of the operations performed by the computer according to the computer program instructions may be implemented in a special purpose processor B. In this embodiment the some or all of the computer program instructions may be implemented via firmware instructions stored in a read only memory ROM a programmable read only memory PROM or flash memory within the special purpose processor B or in memory . The special purpose processor B may also be hardwired through circuit design to perform some or all of the operations to implement the present invention. Further the special purpose processor B may be a hybrid processor which includes dedicated circuitry for performing a subset of functions and other circuits for performing more general functions such as responding to computer program instructions. In one embodiment the special purpose processor B is an application specific integrated circuit ASIC .

The computer may also implement a compiler that allows an application or computer program written in a programming language such as COBOL Pascal C FORTRAN or other language to be translated into processor readable code. Alternatively the compiler may be an interpreter that executes instructions source code directly translates source code into an intermediate representation that is executed or that executes stored precompiled code. Such source code may be written in a variety of programming languages such as Java Perl Basic etc. After completion the application or computer program accesses and manipulates data accepted from I O devices and stored in the memory of the computer using the relationships and logic that were generated using the compiler .

The computer also optionally comprises an external communication device such as a modem satellite link Ethernet card or other device for accepting input from and providing output to other computers .

In one embodiment instructions implementing the operating system the computer program and the compiler are tangibly embodied in a non transient computer readable medium e.g. data storage device which could include one or more fixed or removable data storage devices such as a zip drive floppy disc drive hard drive CD ROM drive tape drive etc. Further the operating system and the computer program are comprised of computer program instructions which when accessed read and executed by the computer cause the computer to perform the steps necessary to implement and or use the present invention or to load the program of instructions into a memory thus creating a special purpose data structure causing the computer to operate as a specially programmed computer executing the method steps described herein. Computer program and or operating instructions may also be tangibly embodied in memory and or data communications devices thereby making a computer program product or article of manufacture according to the invention. As such the terms article of manufacture program storage device and computer program product as used herein are intended to encompass a computer program accessible from any computer readable device or media.

Of course those skilled in the art will recognize that any combination of the above components or any number of different components peripherals and other devices may be used with the computer .

A network such as the Internet connects clients to server computers . Network may utilize ethernet coaxial cable wireless communications radio frequency RF etc. to connect and provide the communication between clients and servers . Clients may execute a client application or web browser and communicate with server computers executing web servers . Such a web browser is typically a program such as MICROSOFT INTERNET EXPLORER MOZILLA FIREFOX OPERA APPLE SAFARI etc. Further the software executing on clients may be downloaded from server computer to client computers and installed as a plug in or ACTIVEX control of a web browser. Accordingly clients may utilize ACTIVEX components component object model COM or distributed COM DCOM components to provide a user interface on a display of client . The web server is typically a program such as MICROSOFT S INTERNET INFORMATION SERVER .

Web server may host an Active Server Page ASP or Internet Server Application Programming Interface ISAPI application which may be executing scripts. The scripts invoke objects that execute business logic referred to as business objects . The business objects then manipulate data in database through a database management system DBMS . Alternatively database may be part of or connected directly to client instead of communicating obtaining the information from database across network . When a developer encapsulates the business functionality into objects the system may be referred to as a component object model COM system. Accordingly the scripts executing on web server and or application invoke COM objects that implement the business logic. Further server may utilize MICROSOFT S Transaction Server MTS to access required data stored in database via an interface such as ADO Active Data Objects OLE DB Object Linking and Embedding DataBase or ODBC Open DataBase Connectivity .

Generally these components all comprise logic and or data that is embodied in or retrievable from device medium signal or carrier e.g. a data storage device a data communications device a remote computer or device coupled to the computer via a network or via another data communications device etc. Moreover this logic and or data when read executed and or interpreted results in the steps necessary to implement and or use the present invention being performed.

Although the terms user computer client computer and or server computer are referred to herein it is understood that such computers and may be interchangeable and may further include thin client devices with limited or full processing capabilities portable devices such as cell phones notebook computers pocket computers multi touch devices and or any other devices with suitable processing communication and input output capability.

Of course those skilled in the art will recognize that any combination of the above components or any number of different components peripherals and other devices may be used with computers and .

Embodiments of the invention are implemented as a software application on a client or server computer and further are configured to stream information data packets etc. to from each other. Alternatively in a network one computer or other capable device may be transmitting multicasting anycasting broadcasting unicasting geocasting etc. information and data e.g. data packets to one or more recipients referred to as receivers across a network. Such receivers may be a computer set top box integrated receiver decoder IRD or any other device capable of receiving the transmitted information. Further the data may be transmitted using a variety of one or more networks e.g. satellite cellular radio frequency etc. .

In this regard in today s communication networks such as the Internet and wireless networks reliable data delivery is an important question to address. Traditional approaches to networking generally assume forwarding in the network with robustness to packet loss achieved by retransmissions of lost packets and or end to end forward error correction. Recently networking coding has been utilized where network packets are mixed at internal nodes.

In network error correction there are errors in some links packets at unknown locations. Some prior art systems code across links packets. However given a network and error model the question arises regarding what communication rates are feasible information theory and how to achieve such rates with practical codes coding theory .

As described above many network error correction systems work on single source multicast systems with uniform errors. In a multicast system all sinks demand the same information the network links packets have equal capacity and z can be erroneous.

Embodiments of the present invention address non multicast demands for streaming e.g. real time streaming or the streaming of stored content . In a non multicast system not all sinks demand the same information. As further described above the capacity of the transmission links is an open problem even without errors . Accordingly there may be a need to code across different sinks data inter session coding . Thus embodiments of the present invention develop error correction codes for streaming building on techniques developed for bounding network error correction capacity by analyzing three layer networks.

In the prior art packets that are streamed across a network may often need to be decoded by given deadlines. Embodiments of the invention provide a mechanism for allocating data packets among different messages while meeting such deadlines where the spacing of the deadlines and the amount of information required at each deadline can be arbitrarily specified.

Referring to consider a streaming system where at each time step one packet of unit size is transmitted and the receiver needs to decode specific independent messages M M . . . M at given time steps m m . . . m respectively under any z packet erasures. A goal is to find the erasure correction capacity region under any z packet erasures as well as a capacity achieving coding scheme. The problem can be viewed as a z erasure correction problem on a 3 layer nested network with one source and n sinks t t . . . t constructed as follows 

In this regard illustrates a 3 layer nested network topology with three sinks n 3 in accordance with one or more embodiments of the invention. To better understand the invention a detailed description of the coding scheme follows. Attached as appendix A are the definitions and proof of the coding schemes the erasure correction capacity the error correction capacity and an example in accordance with one or more embodiments of the invention.

An intra session coding scheme is one in which no coding occurs across information demanded by different receivers. For a given intra session coding scheme let ydenote the amount of information corresponding to message Mtransmitted on the link l. A rate vector u u . . . u is achievable under any z erasures the definition also extends to other erasure patterns by this intra session coding scheme if the inequalities 

An intra session coding scheme may also be defined that assigns rates for each successive receiver as uniformly as possible subject to capacity constraints imposed by assignments for previous receivers. For each receiver the process is similar to water filling with constraints from previous receivers. For a given rate vector u u . . . u a corresponding lower triangular n n rate allocation matrix T is defined along with auxiliary variables the algorithm that follows 

In this section a new erasure model to characterize a class of possible erased subsets of I the middle layer of a given 3 layer nested network is considered. This model bounds the long term erasure rate and constrains the burstiness of erasures which the code is designed to correct.

Appendix B sets forth the definitions and proof that the optimization and coding scheme described above may be utilized for a variety of erasure models including a sliding window erasure model in accordance with one or more embodiments of the invention.

At step a coding scheme is utilized. Such a coding scheme is defined in terms of a non multicast network problem with a nested receiver structure wherein each packet in the streaming problem corresponds to a link in the non multicast network problem and each deadline in the streaming problem corresponds to a receiver in the non multicast network problem. Each of the multiple receivers is required to decode specific messages M M . . . M from the content of received packets at given time steps m m . . . m respectively. Further each of the multiple receivers has access to a subset of the content received by another receiver.

At step the content is allocated into the multiple packets. Such transmission may be performed in a non multicast manner including via streaming to one or more of the receivers. As described above no coding occurs across information demanded by different receivers and a capacity region defines a set of information rate vectors u u . . . u that can be communicated to the multiple receivers successfully. In this regard a rate vector u u . . . u is successfully communicated if the sum of the amounts y of the information corresponding to a message Mtransmitted on unerased links l is greater than or equal to uper 

A code for the uniform erasure model ensures that the sums are satisfied for every unerased set of packets P where P m z.

As described above an As Uniform As Possible coding scheme may also be utilized. In such a coding scheme for a given rate vector u u . . . u a matrix and variables may be defined. The matrix consists of a triangular n n rate allocation matrix T that is used to assign rates for each successive receiver. Alternatively instead of a matrix T may be a vector. The auxiliary variables are

The matrix vector may be defined by the method set forth in algorithm 1 described above and by setting y T i m

In addition to the above a variety of erasure models may be utilized e.g. a uniform erasure model a sliding window erasure model or any other erasure model to characterize a class of possible erased subsets of the content. However embodiments of the invention are not limited to the erasure models described herein.

Further to the above for an arbitrary erasure model linear programming may be applied subject to the constraints inequalities described above for any arbitrary erasure model e.g. having an arbitrary set of erasure patterns .

This concludes the description of the preferred embodiment of the invention. The following describes some alternative embodiments for accomplishing the present invention. For example any type of computer such as a mainframe minicomputer or personal computer or computer configuration such as a timesharing mainframe local area network or standalone personal computer could be used with the present invention.

The foregoing description of the preferred embodiment of the invention has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise form disclosed. Many modifications and variations are possible in light of the above teaching. It is intended that the scope of the invention be limited not by this detailed description but rather by the claims appended hereto.

 2 R. W. Yeung and N. Cai Network error correction part I Basic concepts and upper bounds Commun. Inf. Syst. vol. 6 no. 1 pp. 19 36 2006.

 3 N. Cai and R. W. Yeung Network error correction part II Lower bounds Commun. Inf. Syst. vol. 6 no. 1 pp. 37 54 2006.

 4 A. F. Dana R. Gowaikar R. Palanki B. Hassibi and M. Effros Capacity of wireless erasure networks IEEE Transactions on Information Theory vol. 52 pp. 789 804 2006.

 5 R. K. D. S. Lun M. Medard and M. Effros On coding for reliable communication over packet networks Physical Communication vol. 1 no. 5 March 2008.

 6 S. Jaggi M. Langberg S. Katti T. Ho D. Katabi M. M edard and M. Effros Resilient network coding in the presence of byzantine adversaries Information Theory IEEE Transactions on vol. 54 no. 6 pp. 2596 2603 June 2008.

 7 R. Koetterand F. R. Kschischang Coding for errors and erasures in random network coding IEEE Transactions on Information Theory August 2008.

 8 D. Silva F. Kschischang and R. Kumlaut over otter A rank metric approach to error control in random network coding IEEE Transactions on Information Theory vol. 54 no. 9 pp. 3951 3967 September 2008.

 9 E. Erez and M. Feder Capacity region and network codes for two receivers multicast with private and common data in Proc. IEEE International Symposium on Information Theory 2003.

 10 C. Ngai and R. Yeung Multisource network coding with two sinks in Communications Circuits and Systems 2004. ICCCAS 2004. 2004 International Conference on vol. 1 June 2004 pp. 34 37.

 11 A. Ramamoorthy and R. D. Wesel The single source two terminal network with network coding in Canadian Workshop on Information Theory 2005.

 12 R. Koetter and M. M edard An algebraic approach to network coding IEEE ACM Transactions on Networking vol. 11 no. 5 pp. 782 795 October 2003.

 13 T. Chan and A. Grant Mission impossible Computing the network coding capacity region in Proc. IEEE International Symposium on Information Theory July 2008 pp. 320 324.

 14 N. Harvey and R. Kleinberg Tighter cut based bounds for k pairs communication problems in Proc. 43rd Allerton Conference on Communication Control and Computing Monticello Ill. September 2005.

 15 S. Vyetrenko T. Ho and T. Dikaliotis Outer bounds on the error correction capacity region for non multicast networks in Allerton conference on Communication Control and Computing September 2010.

 16 E. Martinian and C. E. Sundberg Burst erasure correction codes with low decoding delay IEEE Trans. Inf. Theory vol. 50 no. 10 pp. 2494 2502 October 2005.

 18 S. Vyetrenko T. Ho M. Effros J. Kliewer and E. Erez Rate regions for coherent and noncoherent multisource network error correction in Proc. IEEE International Symposium on Information Theory June 2009 pp. 1001 1005.

