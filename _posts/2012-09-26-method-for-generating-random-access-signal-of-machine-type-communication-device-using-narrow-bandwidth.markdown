---

title: Method for generating random access signal of machine type communication device using narrow bandwidth
abstract: Disclosed are a method for generating a random access signal of a machine type communication (MTC) device using a narrow bandwidth, and an MTC device. The method generates a random access signal by allocating a position in a frequency domain of a random access signal dedicated to the MTC device, that is, a position of a frequency for transmission of a random access preamble, to a center position of a base station system bandwidth, or by shifting a center frequency of the MTC device to a position of a random access frequency allocated for a legacy LTE terminal by a base station.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09094987&OS=09094987&RS=09094987
owner: Electronics and Telecommunications Research Institute
number: 09094987
owner_city: Daejeon
owner_country: KR
publication_date: 20120926
---
This application claims priority to Korean Patent Application No. 10 2011 0097196 filed on Sep. 26 2011 Korean Patent Application No. 10 2011 0109842 filed on Oct. 26 2011 and Korean Patent Application No. 10 2012 0061215 filed on Jun. 8 2012 in the Korean Intellectual Property Office KIPO the entire contents of which are hereby incorporated by reference.

Example embodiments of the present invention relate in general to a method for generating a random access signal and more specifically to a method for generating a random access signal of a machine type communication device using a narrow bandwidth.

Machine type communication MTC or machine to machine communication means data communication related to one or more entities that does not require human intervention.

A service optimized for MTC is different from a service optimized for human to human communication. MTC is different from the existing mobile network communication relating to characteristics such as a various market scenarios b data communications c lower cost and effort d many potential communicating terminals e large range and f small traffic for each terminal.

Examples of the type of MTC service include smart metering tracking tracing remote maintenance control and e health.

Recently 3GPP 3rd Generation Partnership Project is standardizing machine type communication MTC for human to machine communication and machine to machine intelligent communication. Many MTC devices are arranged and operated for various MTC applications that have smart metering and remote control as main functions.

In a 3GPP 3rd Generation Partnership Project LTE Long Term Evolution system since an MTC device or a general user is treated as one user equipment UE it should be separately registered in an LTE network. The arrangement of many MTC devices causes scheduling contention for channel allocation depletion of wireless resources overload by signal generation and adversely affects the existing general terminals. 3GPP is performing standardization concentrating on minimizing the adverse effects caused by the arrangement of MTC devices. In addition effort is being made to provide low cost MTC devices to extend MTC service through LTE.

In this regard all LTE based UEs are standardized to support a transmission reception bandwidth of up to 20 MHz. Accordingly a general LTE UE which is a legacy terminal from the viewpoint of an MTC device can access a base station eNodeB having a 1.4 MHz 3 MHz 5 MHz 10 MHz 15 MHz or 20 MHz bandwidth. In general an MTC device or terminal transmits a very small amount of information. Therefore supporting a bandwidth up to 20 MHz for an MTC device as with a general UE may be a considerable waste of cost from the viewpoint of an MTC device aiming at low cost.

In order to solve this problem discussions are being held to have MTC devices operate with a narrow bandwidth. That is while a base station uses a wide bandwidth an MTC device uses a narrow bandwidth of up to 1.4 MHz or 5 MHz. To this end there is a need to provide a separate wireless transmission standard for supporting communication between a base station and an MTC device having a narrow bandwidth.

Accordingly example embodiments of the present invention are provided to substantially obviate one or more problems due to limitations and disadvantages of the related art.

Example embodiments of the present invention provide a method for generating a random access signal by a machine type communication device using a narrow bandwidth in a 3GPP LTE mobile communication system supporting a scalable system bandwidth of up to 20 MHz.

Example embodiments of the present invention also provide a machine type communication device using the method for generating a random access signal.

In some example embodiments a method for generating a random access signal of a machine type communication MTC device using a narrow bandwidth generates a random access signal by allocating a position in a frequency domain of a random access signal dedicated to the MTC device that is a position of a frequency for transmission of a random access preamble to a center position of a base station system bandwidth.

In other example embodiments a method for generating a random access signal of an MTC device using a narrow bandwidth generates a random access signal by shifting a center frequency of the MTC device to a position of a random access frequency allocated for a legacy LTE terminal by a base station.

In still other example embodiments a method for generating a random access signal of an MTC device using a narrow bandwidth includes receiving information on a random access preamble format and transmission time from an upper layer and generating a ransom access signal by using the information on the random access preamble format and the transmission time and predetermined frequency resource block related information for a random access signal according to the bandwidth of the MTC device.

In still other example embodiments a method for generating a random access signal of an MTC device using a narrow bandwidth includes receiving system information transmitted by a base station BS extracting random access related information from the system information received and generating a random access signal by using the random access related information extracted and predetermined frequency resource block related information for a random access signal.

The random access related information may include information on a preamble format and transmission time.

The predetermined frequency resource block related information for the random access signal may include information on a first physical resource block occupied by a physical random access channel resource.

A position of the first physical resource block occupied by the physical random access channel resource may be set to a fixed value according to the bandwidth of the MTC device.

The band used by the MTC device may be located at a center of the system bandwidth used by the base station.

The method may further include acquiring information on a band allocated for a random access signal of a general user equipment UE by the base station and when the band allocated for the random access signal of the general UE deviates from the band of the MTC device shifting a center of the band of the MTC device toward the band allocated for the random access signal of the general UE such that the band allocated for the random access signal of the general UE is included within the band of the MTC device.

In still other example embodiments an MTC device receives information on a random access preamble format and transmission time from an upper layer and generates a random access signal by using the information on the random access preamble format and the transmission time and frequency resource block related information for a random access signal according to the bandwidth of the MTC device.

In still other example embodiments an MTC device includes a transmitting receiving unit configured to receive system information transmitted by a base station BS and a control unit configured to extract random access related information from the system information received and generate a random access signal by using the random access related information received and predetermined frequency resource block related information for a random access signal.

The control unit may acquire information on a band allocated for a random access signal of a general user equipment UE by the base station from the system information received by the transmitting receiving unit and when the band allocated for the random access signal of the general UE deviates from the band of the MTC device shift a center of the band of the MTC device toward the band allocated for the random access signal of the general UE such that the band allocated for the random access signal of the general UE is included within the band of the MTC device.

The MTC device may further include a storage unit configured to store information on the bandwidth of the MTC device information on a random access preamble format and transmission time and information on a fixed value of a first physical resource block occupied by a physical random access channel resource.

Example embodiments of the present invention are described below in sufficient detail to enable those of ordinary skill in the art to embody and practice the present invention. It is important to understand that the present invention may be embodied in many alternate forms and should not be construed as limited to the example embodiments set forth herein.

Accordingly while the invention can be modified in various ways and take on various alternative forms specific embodiments thereof are shown in the drawings and described in detail below as examples. There is no intent to limit the invention to the particular forms disclosed. On the contrary the invention is to cover all modifications equivalents and alternatives falling within the spirit and scope of the appended claims. Elements of the example embodiments are consistently denoted by the same reference numerals throughout the drawings and detailed description.

The terminology used herein to describe embodiments of the invention is not intended to limit the scope of the invention. The articles a an and the are singular in that they have a single referent however the use of the singular form in the present document should not preclude the presence of more than one referent. In other words elements of the invention referred to in the singular may number one or more unless the context clearly indicates otherwise. It will be further understood that the terms comprises comprising includes and or including when used herein specify the presence of stated features items steps operations elements and or components but do not preclude the presence or addition of one or more other features items steps operations elements components and or groups thereof.

Unless otherwise defined all terms including technical and scientific terms used herein are to be interpreted as is customary in the art to which this invention belongs. It will be further understood that terms in common usage should also be interpreted as is customary in the relevant art and not in an idealized or overly formal sense unless expressly so defined herein.

The term terminal used herein may also be referred to as motion station MS user equipment UE user terminal UT wireless terminal access terminal AT subscriber unit subscriber station SS wireless device wireless communication device wireless transmit receive unit WTRU mobile node mobile or other terms. Examples of the terminal may include cellular phones smart phones having a wireless communication function personal digital assistants PDAs having a wireless communication function wireless modems portable computers having a wireless communication function photographing devices such as digital cameras having a wireless communication function gaming devices having a wireless communication function music storing reproducing home appliances having a wireless communication function Internet home appliances capable of wireless Internet connection and browsing and portable units or terminals having a combination of such functions however the present invention is not limited thereto.

The term base station BS used herein generally means a point communicating with a terminal and may also be referred to as Node B eNode B eNB base station transceiver system BTS access point or other terms.

Hereinafter example embodiments of the present invention will be described in detail with reference to the accompanying drawings. In describing the present invention for ease of overall understanding like elements refer to like reference numerals and like elements will not be described again.

As illustrated in a wireless network providing an MTC service includes an MTC server for providing an MTC service an MTC device and an MTC user in addition to the existing wireless network.

The MTC device is a terminal UE that has an MTC function of communicating with the MTC server and other MTC devices through a public land mobile network PLMN .

The MTC server communicates with the PLMN and communicates with the MTC device through the PLMN. The MTC server also has an interface accessible by an MTC user and provides a service for the MTC user . The MTC user uses a service provided by the MTC server .

In the configuration of the MTC server is controlled by a network operator. The network operator provides an application programming interface API on an MTC server and the MTC user accesses the MTC server of the network operator through the API.

In addition the MTC device communicates with the MTC server located in the network through a base station not illustrated .

The random access process is a process for connecting to a network of the terminal. The random access process is performed in the events of initial connection handover scheduling request uplink time synchronization acquisition or the like. That is all terminals perform random access for initial connection and data transmission.

The random access process illustrated in refers to a random access signal generating process in 3GPP TS 36.211 among 3GPP LTE wireless transmission standards.

When selecting a random access preamble the terminal uses information received through system information to determine a group to select by and randomly determines a value therein to connect to the base station. That is in order to perform a random access process the terminal receives system information from the base station S .

Herein in relation to system information including information related to selection of a random access preamble in a 3GPP LTE system a base station transmits system information including common channel related information and overall information about the system to terminals through a common broadcast channel.

Three types of RRC messages are used to transmit system information examples of which are an MIB message an SIBI message and a system information SI message.

System information includes system information blocks SIBs and each system information block includes a series of functionally related parameters. Herein depending on its characteristics the system information block may be classified into a master information block MIB including a limited number of most frequently transmitted parameters that are parameters necessary for initial connection of the terminal to the network a system information block type 1 SIB1 including parameters necessary to determine whether a relevant cell is suitable for cell selection and information related to time domain scheduling of other SIBs and a system information block type 2 SIB2 including shared common channel information.

The terminal sets a channel after receiving the system information. In order to perform initial random access the terminal analyzes information on a random access channel selects one preamble among available random access preambles and starts a random access process.

Specifically among the system information received from the base station the terminal acquires information on a preamble format for transmission of a random access signal and information on transmission time from a parameter related to a physical random access channel PRACH configuration index prach ConfigurationIndex S .

There are five types of preamble formats formats 0 to 4 and each format is controlled by an upper layer according to frame structure and random access configuration. For each format a cyclic prefix length T and a sequence length T are defined. In addition for each PRACH configuration index a preamble format for each frame structure a density in units of 10 ms and a version are defined.

Among the system information received from the base station the terminal acquires physical resource block PRB number information in a frequency domain for transmission of a random access signal from a parameter related to a PRACH frequency offset prach FrequencyOffset S .

The terminal generates a random access preamble signal by using the acquired information that is information on a preamble format for transmission of a random access signal and transmission time and a PRB number in a frequency domain for transmission of a random access preamble signal S .

Thereafter the terminal selects the generated random access preamble randomly and transmits the selected preamble to the base station S .

The base station receives the preamble transmitted by the terminal and transmits a random access response message to the terminal S . When receiving the random access response message for the preamble transmitted by the terminal the terminal performs scheduled uplink transmission by using an uplink wireless resource allocated from the base station in order to establish a radio resource control RRC connection S .

In this regard in the 3GPP LTE wireless transmission standard in a cell a base station allocates a 1.08 MHz frequency resource corresponding to six PRBs for reception of a random access signal and a position of the random access frequency resource may be allocated for any frequency resource within the entire frequency domain of a base station eNB system bandwidth.

Thus when a transmission bandwidth of an MTC device is smaller than a reception system bandwidth of a base station for example when a bandwidth of a base station system is 20 MHz and a transmission bandwidth of an MTC device is 1.4 MHz a position of a random access frequency resource allocated by the base station may deviate from a frequency domain used by the MTC device. Accordingly by the current standard there is a problem in that the MTC device cannot generate or transmit a random access signal.

Thus the present invention provides a method for generating a random access signal by an MTC device using a narrow bandwidth in a 3GPP LTE mobile communication system supporting a scalable system bandwidth of up to 20 MHz.

In addition the present invention provides a method for generating a random access signal of an MTC device by optimizing a random access signal generating method specified in the 3GPP LTE wireless transmission standard when the MTC device has a narrow bandwidth for example a 1.4 MHz dedicated bandwidth.

The 3GPP LTE standard prescribes that transmission bandwidths such as 1.4 MHz 3 MHz 5 MHz 10 MHz 15 MHz and 20 MHz are available. In addition the number of PRBs used for the respective transmission bandwidths are defined as 6 PRBs 15 PRBs 25 PRBs 50 PRBs 75 PRBs and 100 PRBs.

In addition the 3GPP LTE wireless transmission standard prescribes that a random access signal occupies six PRBs corresponding to a 1.4 MHz bandwidth an actually used frequency resource is 1.08 MHz and guard bands are present on both sides thereof .

Based on such an understanding of the 3GPP LTE mobile communication system a method for generating a random access signal of an MTC device using a narrow bandwidth according to the present invention may be divided into two methods as described below in detail.

A random access signal generating method according to a first method of the present invention allocates a position in a frequency domain of a random access signal dedicated to the MTC device that is a position of a frequency for transmission of a random access preamble to a center position of a base station system bandwidth.

A random access signal generating method according to a first method of the present invention shifts a center frequency of the MTC device to a position of a random access frequency allocated for a legacy LTE terminal by the base station.

That is is a conceptual diagram illustrating an example embodiment of allocating a random access frequency resource dedicated to an MTC device to a center frequency position of a base station eNB system bandwidth .

Herein a resource allocated for preamble reception and a random access signal occupy a resource corresponding to six PRBs 1.08 MHz .

In this case the MTC device may also use a random access resource such as transmission time and frequency position allocated for a legacy LTE terminal in a cell. However the present embodiment does not preclude allocating a random access resource dedicated to the MTC device.

As illustrated in the MTC device shifts a center frequency of the MTC device to a center of a random access frequency position for a legacy LTE terminal allocated in a base station system bandwidth.

In various example embodiments of a random access signal generating method according to the present invention illustrated in although the MTC device is described as using a narrow bandwidth such as 1.4 MHz or 5 MHz the present invention is not limited thereto and the MTC device may use bandwidths other than 1.4 MHz and 5 MHz bandwidths.

In addition when a transmission bandwidth of the MTC device is equal to or wider than a base station system bandwidth the MTC device may share a random access resource such as transmission time and frequency position for a legacy LTE terminal in a cell with the legacy LTE terminal or a random access resource dedicated to the MTC device may be allocated separately from a random access resource for the legacy LTE terminal.

Below a description will be given of a random access signal generating method according to the present invention which optimizes a random access signal generating method specified in the 3GPP LTE wireless transmission standard to an MTC device using a dedicated bandwidth of 1.4 MHz.

First a conventional random access generating process will be described. Among system information received from a base station a terminal acquires physical resource block PRB number information in a frequency domain for transmission of a random access signal from a parameter related to a PRACH frequency offset prach FrequencyOffset .

However in the case of an MTC device using a narrow bandwidth according to the present invention since it supports a predetermined bandwidth for example a 1.4 MHz bandwidth PRB number information may be considered as being predetermined. That is the present invention generates a random access signal by using a fixed parameter value for a PRB number in a frequency domain without the need to receive a parameter related to a PRACH frequency offset.

In addition the present invention optimizes an equation used to generate a random access signal in the 3GPP LTE wireless transmission standard to an equation for supporting an MTC device.

A UE acquires information on transmission time and a preamble format for transmission of a random access signal by receiving a parameter related to a PRACH configuration index prach ConfigurationIndex from an upper layer S .

Thereafter an MTC device generates a random access signal by using a fixed parameter value related to a PRB number in a frequency domain and information on transmission time and a preamble format for transmission of a random access signal which is acquired through the upper layer S .

Herein the difference of a random access signal generating method of the present invention from a conventional random access signal generating method specified in the standard will be described below.

In Equation 1 s t denotes a random access signal denotes an amplitude scaling factor and N denotes a Zadoff Chu sequence length. In addition 

Herein n denotes a first PRB occupied by a PRACH resource which may be acquired by receiving a parameter related to a PRACH frequency offset prach FrequencyOffset from an upper layer.

A random access signal generating method according to the present invention supporting an MTC device using a dedicated bandwidth of 1.4 MHz will be described below in comparison with Equation 1.

A parameter n has a fixed parameter value without separate reception from an upper layer for example n 0 . In Equation 1 N is changed into a fixed value

Accordingly the random access signal generating method according to the present invention may be expressed as Equation 2 below 

In Equation 2 s t denotes a random access signal denotes an amplitude scaling factor and N denotes a Zadoff Chu sequence length. K f f denotes a factor considering an interval between random access preamble transmission and uplink data transmission. In addition f denotes subcarrier spacing and f is a value representing subcarrier spacing for a random access preamble and has a value determined according to a preamble format. is an offset value determining a frequency domain position of a random access preamble in a PRB and has a value determined according to a preamble format.

Herein as a method for determining a n value for each frame structure type the present invention proposes the following three example embodiments 

First a first PRB occupied by a PRACH resource for a frame structure type 1 corresponding to FDD may be defined as Equation 3 below n n Fixed Constant Value Equation 3

Second a first PRB occupied by a PRACH resource for preamble formats 0 to 3 among a frame structure type 2 corresponding to TDD may be defined as Equation 4 below 

Third a first PRB occupied by a PRACH resource for a preamble format 4 among a frame structure type 2 corresponding to TDD may be defined as Equation 5 below 

The MTC device generates a random access preamble by using information on the first PRB occupied by the PRCH resource determined according to one of Equations 3 to 5 S .

Referring to the MTC device transmits the generated random access preamble to the base station S . The MTC device waits to receive a random access response from the base station S and performs scheduled uplink transmission S .

An MTC device according to the present invention may include a storage unit a control unit and a transmitting receiving unit .

The transmitting receiving unit receives system information transmitted by a base station transmits the received system information to the control unit and transmits a random access preamble generated by the control unit to the base station.

The storage unit stores information on a bandwidth of the MTC device information on a random access preamble format and transmission time and information on a fixed value of a first physical resource block occupied by physical random access channel resource.

The control unit extracts random access related information from the received system information and generates a random access signal by using the extracted random access related information and predetermined frequency resource block related information for a random access signal.

Herein the random access related information includes information on a preamble format and transmission time.

In addition the predetermined frequency resource block related information for the random access signal includes information on a first physical resource block occupied by a physical random access channel resource. A position of the first physical resource block occupied by the physical random access channel resource can be set to a fixed value according to the bandwidth of the MTC device.

In addition the control unit acquires information on a band allocated to a random access signal of a general user equipment UE by the base station from the system information received by the transmitting receiving unit and when the band allocated to the random access signal of the general UE deviates from the band of the MTC device shifts a center of the band of the MTC device toward the band allocated to the random access signal of the general UE such that the band allocated to the random access signal of the general UE is included within the band of the MTC device.

When the random access signal generating method described above is used it is possible to generate a random access signal that can be smoothly communicated between an MTC device using a narrow bandwidth and a 3GPP LTE mobile communication system supporting a scalable system bandwidth of up to 20 MHz.

In addition according to the present invention when the MTC device has a dedicated bandwidth of 1.4 MHz the random access signal generating method can be simplified.

In addition the existing wireless transmission standard can be changed into a wireless transmission standard optimized for MTC dedication and unnecessary upper layer parameters can be removed to reduce the total number of upper layer parameters.

While the example embodiments of the present invention and their advantages have been described in detail it should be understood that various changes substitutions and alterations may be made herein without departing from the scope of the invention.

