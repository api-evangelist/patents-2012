---

title: Method for avoiding interferences in frequency division duplex operating areas
abstract: The system comprises:


url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09369879&OS=09369879&RS=09369879
owner: Telefonica, S.A.
number: 09369879
owner_city: Madrid
owner_country: ES
publication_date: 20120307
---
This application is a National Stage of International Application No. PCT EP2012 053946 filed Mar. 7 2012 claiming priority based on Spanish Patent Application No. 201130338 filed Mar. 11 2011 the contents of all of which are incorporated herein by reference in their entirety.

The present invention generally relates in a first aspect to a method for avoiding interferences in Frequency Division Duplex FDD operating areas comprising coordinating the use of radio resources between different FDD network elements including macro base stations and short range coverage extension nodes SCENs and more particularly to a method which comprises using a synchronized Time Division Duplex TDD air interface for performing said coordination.

A second aspect of the invention comprises a system for avoiding interferences in FDD operating areas which is adapted for implementing the method of the first aspect.

This invention is focused on a novel mechanism for the coordination of RR Radio Resource usage among macro cellular FDD base stations namely NodeB and eNodeB in 3G 4G systems respectively and FDD SCEN Short range Coverage Extensions Nodes as Relays Picocells and Femtocells namely HeNodeB in LTE terminology providing also a novel mechanism for SCEN frequency and time synchronization.

The 4G systems trend to simplify the core network improving the latency capacity and throughput. This represents an important improvement for IP traffic and services.

It is important to note that the use of SCEN is foreseen as a must in the cellular network industry in order to fulfil the requirements of dynamic flexible and fair coverage in the full cellular area pursuing as main objectives 

On the other hand it is foreseen that these extension nodes SCEN use the same frequency of the macro base station in which coverage area these devices are deployed and therefore an interference problem could be present hindering somehow the compliance of the objectives pursued by the SCENs. In order to avoid these issues some strategies should be implemented to get the upmost benefit with the deployment of SCENs.

In the current state of the art of these technologies which can be consulted in current Release 9 Release 10 of 3GPP interference avoidance mechanisms among base station and SCENs since both devices operate in the same pair frequencies have three different approaches 

These approaches particularized for 4G systems are currently being implemented by SCEN vendors in commercial and laboratory prototypes with different specific variations. As shows in the first case there is not any interference avoidance mechanism and the probability that BS and SCEN use the same radio resources causing interferences increases according to the number of users in the coverage area. However the other two approaches contemplate certain coordination mechanism to interference avoidance by means of measurements done by SCEN on BS s signals B approach or by means of messages interchanged between BS and SCEN through backhaul communications such as X2 interface currently contemplated for 4G systems C approach .

As an example of the state of the art concerning the technologies origin of the proposed invention it might be interesting to describe the ICIC message which has been defined in 2 for load management through the backhaul interface X2 currently specified for LTE 4G system . This protocol provides among other things the management of the load in the area covered by several eNodeBs. The coordination is implemented by means of the load indication procedure which basically consists of sending LOAD INFORMATION message individually from the macro BS to each of its neighbouring cells so far till a maximum of 256 neighbour cells are contemplated indicating resource status overload and traffic load. The purpose of this procedure is to control the interferences between neighbouring cells and the following table shows the information elements IE related to interference coordination included in the LOAD INFORMATION message according to 2 .

Note that the State of the art simply provides indication of those PRBs where the base station has detected some problem reactive approach .

Related with SCEN synchronization the state of the art is based on the use of external references by air interface from in band signal from other cellular systems with best coverage or from GPS signals or the use of backhaul signals using techniques based on the standard IEEE 1588 6 or SynEthernet in case of no coverage on any of the mentioned air interface signals. Here backhaul network also called transport network means the portion of the hierarchical telecommunication network comprising the links between the core network backbone and the radio access network.

Next it will be introduced a brief definition of those technical terms which are fundamental for the correct understanding of the invention facilitating the reading of the present specification 

Traditional telecommunications research and education often dwell upon channel coding and source coding with a single user in mind although it may not be possible to achieve the maximum channel capacity when several users and adjacent base stations share the same frequency channel.

Efficient dynamic RRM schemes can increase system capacity by an order of magnitude which often is considerably more than what is possible by introducing advanced channel coding and source coding schemes.

RRM is especially important in systems limited by co channel interference rather than by noise for example cellular systems and broadcast networks homogeneously covering large areas and wireless networks consisting of many adjacent access points that may reuse the same channel frequencies.

The cost of deploying a wireless network is normally dominated by base station sites real estate costs planning maintenance distribution network energy etc and sometimes also by frequency license fees. The objective of radio resource management is therefore typically to maximize the system spectral efficiency in bit s Hz base station site or Erlang MHz site under constraint that the grade of service should be above a certain level. The latter involves covering a certain area and avoiding outage due to co channel interference noise attenuation caused by long distances fading caused by shadowing and multipath Doppler shift and other forms of distortion. The grade of service is also affected by blocking due to admission control scheduling starvation or inability to guarantee the quality of service demanded by the users.

Pico Femtocell Those are devices used to improve mobile network coverage in small areas. They connect locally to mobile phones and similar devices through their normal GSM UMTS or LTE connections and then route the connections over a fixed broadband connection back to the carrier bypassing the normal cell towers that are arrayed across the countryside. Pico Femtocells require no special hardware or software support on the mobile devices they connect to.

The key role of a proper radio network planning and optimization is to reduce any negative influence of interference and hence to achieve a maximum cell decoupling or isolation. One or more tools should assist the network planner in the whole planning process covering dimensioning detailed planning and finally pre launch network optimization. Planning of radio networks is a complex process. Typically planners are specialized to a few sub processes. Radio network planning is an important but only small part of network operations. Interaction with other software tools is crucial for efficiency.

Inter cell Interference Co ordination ICIC requires also communication between different network nodes in order to set and reconfigure these restrictions. Two cases are considered so far the static one where reconfiguration of the restrictions is done on a time scale corresponding to days and the semi static where the time scale is much smaller and corresponds to seconds.

The interference coordination solutions in SCEN deployments currently being used or under research have the following lacks from the interference avoidance point of view 

1. Statistical approaches lead to a collision among macro cells and SCEN diminishing the radio communication capabilities and creating de facto a hole in macro cell coverage area. This approach has also scalability problems since interference among several SCENs could also be present. In massive deployments of this kind of nodes there is more probability that the coverage areas of different SCENs are overlapped and also overlapping of users served by the base station.

2. Interference avoidance mechanisms based on macro cell signals measurements cannot guarantee an efficient use of the RR. There are several scenarios mainly for dynamic scheduling usually applied when the traffic is bursty and dynamic in rate in which this approach fails because the allocation of radio resources could change every radio frame 10 ms leading to interference problems since SCEN devices cannot be aware of the real interference level at macro cell or UEs. Besides it should be considered that the SCENs are deployed in areas with coverage problems and so the level of signal from the macro BS usually will be very weak decreasing the efficiency of the method.

3. The ICIC approach based on backhaul utilization lacks deployment flexibility since the deployment of a new SCEN requires to establish a new connection with the base station and cannot adapt on the air to the interference levels present in the coverage area. This is a semi static approach due to the asynchronous high level messages used and therefore waste available RR by static assignment of them independently of the real RR usage.

On the other hand the two previously mentioned mechanisms for providing synchronization to SCEN present the following implementation issues 

It is necessary to offer an alternative to the state of the art which covers the gaps found therein particularly those related to the lack of flexibility that known interference coordination procedures based on the use of ICIC messages have.

Note that said known procedures representative of the more advanced technology of State of the art simply provides indication of those PRBs where the base station has detected some problem i.e. constituting a reactive approach.

For that purpose the present invention provides in a first aspect a method for avoiding interferences in FDD operating areas comprising coordinating the use of radio resources between different network elements including at least one macro base station and SCENs deployed within the coverage area of said macro base station and operating in FDD mode by means of the sending of messages between at least part of said network elements.

Unlike the above described ICIC proposal where that sending of messages was done through a backhaul network in a reactive approach the method of the first aspect of the invention comprises in a characteristic manner performing said sending of messages by means of a synchronized Time Division Duplex or TDD air interface.

With the present invention the interference coordination procedure is implemented in the synchronous TDD air interface and so it provides a totally flexible solution for new deployments or changes in RR usage.

The method of the first aspect of the invention enables the use of time advanced pre schedule based on previous scheduling information analysis DL assignment messages and UL grant messages generated by the scheduler block of the base station. Therefore sending through a synchronized TDD air interface in broadcast or dedicated mode to the involved SCENs deployed in the coverage area of the base station the list of radio resources that could be used in the next radio frame 10 ms to avoid interferences in DL and UL proactive approach 

For an embodiment related to a multicast version of the proposed invention SCEN to SCEN interference is solved since the base station knowing the geographical position of each SCEN uses said information to indicate individually the most appropriate radio resources to be used by each of them in order to avoid interference with the neighbouring nodes. In the case of interference to users served by the base station the broadcast version of the invention would be enough to avoid the problem.

The proposed invention is based on the scheduling information produced during a certain period of time several radio frames and provides indication of those radio resources that can be used by the SCENs since the base station has the engagement of not use them in the next radio frame excluding the guaranteed resources to the SCENS in its dynamic scheduling process.

Further to the effect of avoiding interferences by means of the method of the first aspect of the invention the use of the added TDD air interface provides also the effect of achieving the synchronization of the SCEN with the base station. In addition to the frequency synchronism with the present invention the SCEN can also achieve time synchronism enabling a better control of the interferences as there is a perfect alignment between the radio frames of base station and SCENs.

Since TDD mode in this invention is used only for interference coordination of the FDD nodes the radio power of the TDD signal which uses a frequency different to the used by FDD system could be increased so that the communication through the TDD interface can be extended even for indoor installations.

Other embodiments of the method of the first aspect of the invention are described according to appended claims and in a subsequent section related to the detailed description of several embodiments.

It is to be noted that the implementation of this invention in one cell NodeB or eNodeB and all or part of the SCENS deployed under its coverage area does not require any modification on the rest of the network nodes nor in any of the user equipment

A second aspect of the invention concerns to a system for avoiding interferences in FDD operating areas comprising 

Unlike the known proposals in the system of the second aspect of the invention the coordination means comprise a synchronized TDD air interface through which perform said sending of messages.

The system of the second aspect of the invention is adapted to implement the method of the first aspect.

Other embodiments of the system of the second aspect of the invention are described according to appended claims and in a subsequent section related to the detailed description of several embodiments.

Next a description of the invention for several embodiments will be done referring the appended Figures.

It is necessary to clarify that for 3G systems such as WCDMA the frequency reuse pattern is using all the cells the same carrier and bandwidth 5 MHz for single carrier systems but with different scrambling codes. Therefore the counterpart for different subcarrier frequencies F F used in 4G systems for interference avoidance would be in 3G systems the different channelization codes for DL and different scrambling codes for UL since in DL channelization codes are used to distinguish different channels from same base station while in UL scrambling codes distinguish different users.

Besides the radio resources scheduler in 3G base stations NodeB is included in the external control node RNC common at several BSs and so the implementation of the present invention should interact with the allocation messages produced by the RNC making more difficult the understanding of the invention. However in 4G systems which access technology is based on the use of OFDMA for DL and SC FDMA for UL the resources scheduling are a function of the base station the eNodeB includes the functionality of the RNC allocating different time frequency slots PRBs for different users. For these two reasons although the invention is applied to both systems 3G and 4G depending on the embodiment the next described details of the implementation will be focused on LTE systems.

The main focus of the invention is to provide a method to perform a coordinated use of FDD systems radio resources among macrocell and SCENs. A method is sought for improving synchronization reference for SCEN devices. It is noted that the extrapolation of this invention could lead to a use of TDD radio transmission as a medium for the X2 interface.

The invention is applicable to any FDD cellular deployment namely 3G and 4G cellular systems in which relays or femtocells nodes are foreseen to increase system capacity or system coverage. Some of the terminologies used are from 4G systems only for clarity of the exposition but the same principle is applicable to 3G systems or any other cellular FDD system.

The invention consists on the use of TDD communications in order to coordinate the use of FDD RR among SCENs and between SCENs and macro cells as well as for the provision of synchronization reference for SCEN devices.

The invention empowers the system with a coordinated joint sharing of FDD RR between macro cells and SCENs enabling the transfer of unused macro RR to the SCENs on a radio frame by radio frame basis. It should be considered that macro cell capacity is usually planned to attend the traffic requirements foreseen in the busy hour. In the busy hour only a percentage of available RR is used in order to avoid system congestion. In example statistics of unused RR in different macro cells at the busy hour and for high number of samples are shown.

It has to be noted that even when a small portion of the sampled macro cells are using fully its RR in the graphic samples using more than 95 of its RR are included in the 0 unused RR column this is only due to the current lack of adequate QoS mechanisms in order to diminish the impact of P2P users on RR availability. Anyhow the graphic shows that currently more than 70 of the macro cells even in the busy hour have more than 50 of its RR unused and obviously in an average hour this number will be much higher.

Precisely the proposed invention takes great advantage of this fact enforcing to the SCENs camped in the coverage area of a given base station to use the radio resources unused or guaranteed by this base station so that the interference between users of macro cell and SCENs can be avoided.

The invention based on the information related to the allocation of radio resources by the base station for its own users estimates the portion of the resource grid e.g. in LTE frequencies and time slots which could be used in the next radio frame by the users of the SCENs. It should be noted that Almost Blank Subframes ABS is a specific case of this kind of assignments in which only time slots are assigned covering all frequency bandwidth. As shown in the DL resources grid in LTE represented by a group of physical resource blocks a PRB is the smallest element of resource allocation assigned by the BS scheduler for a signal of 1.4 MHz of bandwidth. The allocation of resources among the users of the cell is a function of the scheduler of the BS and in LTE may be dynamic when traffic is bursty and dynamic in rate or persistent when traffic is small periodic and semi static in size as VoIP . Regardless the type of scheduling according to data shown in in all the radio frames there are many free resources as illustrates. The aim of the proposed invention is to reserve part of the unused resources by the BS for the exclusive use of the users served by the SCENs in the coverage area of the BS avoiding possible interferences between the active UEs of the BS and the active UEs of the SCENs. With the dedicated version of the invention bidirectional communications between the base station and the SCENs it can be avoided even the possible interferences produced between FDD users of overlapped SCENs.

This invention takes advantage of the same frame duration among FDD and TDD protocols in cellular systems as specified for instance in 3GPP TS 36.211 5 for LTE standard and the great amount of identical component blocks among both protocols that will enable the use of synergies that simplifies radio access nodes SCENs and macro cells designs.

This enables the use of TDD protocol which is deployed in a third frequency different from FDD UL and DL frequencies to synchronously communicate to SCEN devices and eventually to the other macro cells the RR available that are not foreseen to be used in next radio frame by the macro cell.

TDD could also establish a P2P communication among macro cell and SCEN devices in its coverage area providing a two way mechanism for interchange of signalling information in a master slave way being the RR usage commanded by macro cells and reports on performance of assigned RR usage sent from SCENs to macro cell.

In a general cellular network architecture is shown on which TDD transmission is depicted to illustrate the invention concept i.e. use of TDD as control channel for RR coordinated usage between macro cells and SCENs. The figure indicates that the deployment of this invention requires that some nodes of the FDD deployed Network namely some macro cells and some SCENs be TDD capable to be established between them a control channel. TDD capable means that an additional TDD transceiver operating in a frequency band different from the FDD bands is included in the nodes together with appropriate signal processing HW and SW to take advantage of its capabilities.

It is worthy to note that the innovation deployment is flexible by that meaning that its deployment in one cell does not imply or preclude its deployment in other cells.

To better understand the added part of the invention on the general architecture of cellular networks shows in a particular case of 4G system the additional blocks referred as Extension TDD modules needed for the implementation of the interference avoidance mechanism proposed in the invention.

The idea is not to change the normal operation of the FDD users but rather to include new modules in both FDD nodes eNodeB and HeNodeBs to coordinate the resource usage of these nodes to avoid interferences between the users of the eNodeB and the users of the HeNodeB. The coordination will be done through the TDD air interface provided by these new modules and trough the interchange of messages using the own TDD protocol in a master module included in the BS slave module included in the SCEN way. Of course the definitive implementation and integration of the additional modules in the macro base station and in the SCEN will be a subject of the manufacturer of these equipments.

As said the invention consists of the use of TDD communications to coordinate the FDD RR among SCENs and between SCENs and macro cells as well as for the provision of synchronization reference for SCEN devices. The term TDD communications is defined as a standard TDD cellular system which payload capabilities are used for FDD system RR assignment. In the invention the TDD capacity usage is much smaller than that of the FDD system typically but not necessarily 100 times smaller.

The coordination consists of the interchange of private messages between the base station and the SCENs using the TDD air interface implemented precisely by the additional modules proposed in the invention. The modules to be included are shown in for the macro base station module A coordinator or master module and in for the SCEN module B coordinated or slave module respectively. As can be seen in these figures the additional modules have basically the following main blocks 

It is important to remark that the special TDD BS implemented in module A of the invention will not be connected to the core network and so will have a special cell identity as well as a particular initial configuration so that only the SCEN TDD users implemented in modules B will be able to access at this special TDD BS. Likewise the TDD block of the modules B will have some identities configured on their special USIMs known and accepted only for the special TDD BS implemented in module A. In other words the TDD interface included in our invention is devoted only exclusively for connections between the module A coordinator or master part and the modules B coordinated or slave part and not for normal cellular radio communications according to the TDD standard.

Therefore after switch on the module B of the HeNodeB or SCEN coordinated node this will subscribe to the module A of the eNodeB or macro BS coordinator node thus enabling the interchange of messages with information about RR usage and synchronization of the FDD users served by the macro BS and the SCEN.

The TDD signal from the macro cell is used as a synchronous same frame duration that FDD control channel in which priority RR available for SCEN utilization on next FDD radio frame is indicated. It is important to note that the initial establishment of the TDD connection between module A and modules B could follow the identical attach and activation procedures specified in 3GPP for TDD standard including all the necessary IEs cell identities user identities specific parameters of the TDD mode GPS position etc. in terms of the mode implemented in the invention broadcast or dedicated basis as will be explained hereinafter . Once the TDD link is established the module A will send the indication of the FDD resource blocks which can be used by the SCENs which will receive and analyze them in their module B.

Therefore for broadcast control channel macro cells module A only need to add TDD transmission capabilities and SCEN nodes modules B only need to add TDD reception capabilities and the information could be carried in any specified broadband way that do not need the SCEN nodes to be registered by the macro cell.

On the other hand for a complete control channel establishment both macro and SCEN nodes need to include a complete TDD transceiver synchronized with its current FDD transceiver. In this last case SCENs will be a classical UE from the macro point of view and therefore the SCEN needs to be identified and registered in the macro TDD system.

The broadcast approach is easier and therefore it lowers the cost of the invention deployment but with this approach only macro cell to SCEN coordination could be achieved. On the other hand the deployment of full TDD transceiver capabilities on both macro and SCEN nodes will enable full macro SCEN coordination and also a SCEN to SCEN coordination at the price of highest nodes cost.

The kind of indicator sent in TDD to the SCEN could be deployed with different approaches being as an example the most straightforward way in LTE to use something similar to the IE currently standardized Relative Narrowband Transmit Power RNTP . This indicator is used in the ICIC mechanisms under the X2 interface and could be made available in a synchronized way not only to neighbours macro cells eNodeBs but also to all SCENs deployed in the coverage area as has been previously detailed.

1. Avoid SCEN to macro cell interference. Macro cell will coordinate available RR in the coverage area by means of indicating in a broadcast way in each TDD frame the block of its RR that could be shared in the next FDD UL DL radio frames as shown in . This indication should be based on the traffic forecast on macro cell and will be obviously taken into account in the operation of the macro scheduler on the next frame in order to avoid interferences.

Of course this same idea could be used with different frame indication namely indicating in a given TDD frame the RR usage in a FDD frame different of the next but this will be more inefficient even when will provide advantage compared with the current state of the art.

It is worth to be noted that this TDD identification do not only enable the exposed ICIC mechanisms but all in all it is possible to use it as enabler for controlling the access to operator FDD bandwidth by SCEN nodes not always under operator s control . That means that based on SCEN TDD identification and operator security or commercial policies even not FDD radio resource could be assigned to unauthorized SCEN nodes avoiding them to use cellular operator radio resources on unauthorized form.

2. Avoid SCEN to SCEN interference. If the full TDD link is established among macro cell and different SCENs since the location of the SCEN could be known or can be estimated by different state of the art mechanism based on TDD received signals a personalized RR assignation to different SCEN devices could be signalled from the macro cell avoiding SCEN to SCEN interference and therefore improving the RR usage.

3. Implementable on current and future networks. The proposed invention is fully compatible with current state of the art of pure FDD networks deployment since no modification of the FDD standard is needed being therefore straightforward to deploy a mixed network in which the proposed mechanism is only implemented in the locations in which high density of SCEN is foreseen and therefore the probability of interferences is high.

4. High indoor coverage of control signals. Since TDD signals do not require a high communication bandwidth TDD transmission could be constrained to the smallest frequency bandwidth allowed by the TDD standard. This allows the TDD signal to be radiated with a spectral density higher than that of FDD for the same amount of total radiated power and therefore to control and synchronize some SCENs deployed out of FDD coverage.

5. Provides on the air synchronization. The radiated signal by TDD module of the macro cell will have as previously shown better coverage than current FDD signal providing therefore a more reliable source for on the air time and frequency synchronization for SCEN devices.

Concerning the amount of information bits needed for sending the indication of free resources from the module A this of course will depend on the bandwidth of the FDD signal and in definitive of the number of PRBs per radio frame that have to be indicated from 60 PRBs for a FDD signal of 1.4 MHz to 1000 PRBs for a FDD signal of 20 MHz and how they are clustered being one possible extreme to send only assignments of time slots in a ABS approach. However assuming that the TDD radio frame uses a DLJUL configuration as shown in and the lowest bandwidth 1.4 MHz around 4608 information bits QPSK modulation and coding rate will be available for transmitting the message with the indication of the PRBs which can be used.

Finally it is important to outline how to generate the message of RR usage which will be sent from the module A to the modules B indicating the free RR to be used by the SCENs. For example in the case of LTE system the indication of FDD RRs free to use will be elaborated analyzing as shows the DL allocation messages and UL grant messages produced by the scheduler of the eNodeB macro BS during a certain number of radio frames previous to the elaboration of the indication. Note that in LTE the resources scheduling is performed by sub frame basis and it is transmitted by the PDCCH Physical Downlink Control Channel in the first OFDM symbols of each sub frame.

The main benefit of this invention as it has been described so far is the provision of a coordinated advanced and synchronized ICIC mechanism that could be gradually deployed on current FDD cellular networks to coordinate RR usage avoiding interference in the coverage area among different radio network nodes macro cells and Short Range Coverage Extensions Nodes as picocells femtocells relays etc. .

1. Preventing interference with other network nodes by means of using of TDD communications for broadcasting of advanced information on RR usage on FDD UL DL by macro cells.

2. Mechanism for taking into account SCEN devices requirements characteristics and physical position as well as interference information reported by the SCEN nodes by means of using a special TDD control channel for RR coordination of several SCEN nodes sending the SCEN RR assignment for devices in the macro coverage area in a master slave way.

3. It is fully compatible with current state of the art of pure FDD networks deployment since no modification on the FDD standard is needed being therefore straightforward to deploy a mixed network in which the proposed mechanism is only implemented in the locations in which high density of SCEN is foreseen.

4. High indoor coverage of control signals. Since TDD signals do not require a high communication bandwidth TDD transmission should be constrained to the smallest frequency bandwidth allowed by the TDD standard. This allows the TDD signal to be radiated with a spectral density higher than that of FDD for the same amount of total radiated power and therefore to control and synchronize SCENs deployed out of FDD coverage.

5. Provides on the air synchronization. The macro cell TDD radiated signal will have as previously shown better coverage than current FDD signal providing therefore a more reliable source for on the air time and frequency synchronization of SCEN devices.

6. In addition to the frequency synchronism the invention enables the SCEN to obtain time synchronism improving interferences management since there is a perfect alignment between the radio frames of base station and SCENs. This way the interferences between the FDD users of the macro BS and the SCEN come only from the usage of the same frequency in the same time slot allowing perfect interference coordination among the macro BS and the SCENs.

7. It makes easier the power control algorithms in SCENs. Usually the power control in SCENs nodes is dynamically defined depending on the service required and the SINR. Therefore if the interferences are avoided the SINR will be higher and steadier facilitating the power control function.

8. Use of TDD signal to send paging messages for FDD users under SCENs coverages. Due to the high volume of SCENs deployment it is well known that paging messages are a big burden for the SCEN system which may cause a huge signalling redundancy for the large number of SCEN involved.

9. Use of TDD control signal like a control interface for handover among macro cell and SCEN. Cell handover enables the UE to transfer the service among its serving cell and the target cell without terminating the service. Currently this kind of handover is not possible among macro cells and SCENs for active communications. Therefore it is in fact a way to include all X2 alike information in a synchronized way.

A person skilled in the art could introduce changes and modifications in the embodiments described without departing from the scope of the invention as it is defined in the attached claims.

