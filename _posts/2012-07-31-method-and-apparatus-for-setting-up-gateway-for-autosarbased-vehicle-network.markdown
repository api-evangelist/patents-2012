---

title: Method and apparatus for setting up gateway for AUTOSAR-based vehicle network
abstract: The present invention provides a method and apparatus for setting up a gateway for an AUTOSAR-based vehicle network. The apparatus for setting up the gateway includes a candidate selection unit for selecting an Electronic Control Unit (ECU) connected to at least two communication clusters, from among a plurality of ECUs, as a gateway candidate, and a gateway generation unit for generating a gateway instance with reference to the ECU selected by the candidate selection unit, and generating a gateway meta-model including the gateway instance based on instance generation input values entered by a user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09237196&OS=09237196&RS=09237196
owner: ELECTRONICS AND TELECOMMUNICATIONS RESEARCH INSTITUTE
number: 09237196
owner_city: Daejeon
owner_country: KR
publication_date: 20120731
---
This application claims the benefit of Korean Patent Application No. 10 2011 0117723 filed on Nov. 11 2011 which is hereby incorporated by reference in its entirety into this application.

The present invention relates generally to a method and apparatus for setting up a gateway for an AUTomotive Open System ARchitecture AUTOSAR based vehicle network. More particularly the present invention relates to a method and apparatus for setting up a gateway for an AUTOSAR based vehicle network which can more easily set up the gateway for the vehicle network based on AUTOSAR.

An automotive electronics software platform standard AUTomotive Open System Architecture hereinafter referred to as AUTOSAR is a standard pertaining to an automotive electronics software architecture which was established by a partnership between vehicle manufacturers and manufacturers for related parts and electronics application development tools.

AUTOSAR provides an architecture and development methodology for automotive electronics software and Application Programming Interfaces APIs for electronics applications.

The automotive electronics software architecture provided by AUTOSAR includes coverage of the structures of applications network structures communication data between Electronic Control Units ECUs on which applications are to be mounted the structure of lower layer platform modules that support application software to be loaded onto respective ECUs and methods of setting up the platform modules.

In order to implement such standards with actual software AUTOSAR defines and provides meta models required to describe products obtained by respective development methodologies.

However the provided meta models may be important information to persons who design AUTOSAR related platforms or tools but the actual information to which the meta models are to be applied is important to persons who develop electronics applications by using actual tools and platforms of AUTOSAR. Therefore how intuitive or easily understandable a provided interface is when setting up meta models may be a performance index of AUTOSAR development tools that is important.

In this way the current AUTOSAR properly defines and provides meta models but a guide for indicating how to properly configure such meta models in practice has not yet been proposed.

Accordingly the present invention has been made keeping in mind the above problems occurring in the prior art and an object of the present invention is to provide a method and apparatus for setting up a gateway for an AUTOSAR based vehicle network which can more easily set up a gateway model for a vehicle network by using an AUTOSAR based development tool.

In accordance with an aspect of the present invention to accomplish the above object there is provided an apparatus for setting up a gateway for an AUTomotive Open System ARchitecture AUTOSAR based vehicle network including a candidate selection unit for selecting an Electronic Control Unit ECU connected to at least two communication clusters from among a plurality of ECUs as a gateway candidate and a gateway generation unit for generating a gateway instance with reference to the ECU selected by the candidate selection unit and generating a gateway meta model including the gateway instance based on instance generation input values entered by a user.

Preferably the gateway generation unit may include an instance generation unit for generating the gateway instance based on a context menu of the ECU.

Preferably the instance generation unit may be configured to generate a frame mapping instance for performing mapping between frames including source Interaction layer Protocol Data Units IPdus and target IPdus based on the instance generation input values generate an IPdu mapping instance for establishing a mapping relationship between IPdus by mapping a source IPdu and a target IPdu contained in an identical frame to each other and generate a signal mapping instance for setting up locations at which signals are to be transferred to a communication cluster of the target IPdu when the source IPdu and the target IPdu contained in the identical frame are mapped to each other.

Preferably the gateway generation unit may include a frame mapping unit for establishing a mapping relationship between the frames including the source IPdus and the target IPdus by referring to a previously generated frame triggering instance based on the frame mapping instance.

Preferably the IPdu mapping instance may include a source IPdu reference instance corresponding to the source IPdu contained in the identical frame and a target IPdu reference instance corresponding to the target IPdu contained in the identical frame and the gateway generation unit comprises an IPdu mapping unit for establishing a mapping relationship between the source IPdu and the target IPdu by referring to a previously generated IPdu triggering instance based on the source IPdu reference instance and the target IPdu reference instance.

Preferably the gateway generation unit may include a signal mapping unit for setting up locations of signals that are to be transferred to the communication cluster of the target IPdu by referring to a previously generated signal triggering instance based on the signal mapping instance.

Preferably the instance generation unit may include an instance generation screen having a plurality of input blocks for receiving the instance generation input values entered by the user.

Preferably the plurality of ECUs may be generated during a procedure of setting up a vehicle network structure model and a communication data structure model in advance before the gateway meta model is generated.

In accordance with another aspect of the present invention to accomplish the above object there is provided a method of setting up a gateway for an AUTomotive Open System ARchitecture AUTOSAR based vehicle network including selecting an Electronic Control Unit ECU connected to at least two communication clusters from among a plurality of ECUs as a gateway candidate generating a gateway instance with reference to the ECU and generating a gateway meta model including the gateway instance based on instance generation input values entered by a user.

Preferably the generating the gateway instance may include generating the gateway instance based on a context menu of the ECU.

Preferably the generating the gateway meta model may include generating a frame mapping instance for performing mapping between frames including source Interaction layer Protocol Data Units IPdus and target IPdus based on the instance generation input values generating an IPdu mapping instance for establishing a mapping relationship between IPdus by mapping a source IPdu and a target IPdu contained in an identical frame to each other and generating a signal mapping instance for setting up locations at which signals are to be transferred to a communication cluster of the target IPdu when the source IPdu and the target IPdu contained in the identical frame are mapped to each other.

Preferably the generating the frame mapping instance may include referring to a previously generated frame triggering instance based on the frame mapping instance and establishing a mapping relationship between the frames including source IPdus and target IPdus which will be used in different communication clusters.

Preferably the generating the IPdu mapping instance may include generating a source IPdu reference instance corresponding to the source IPdu generating a target IPdu reference instance corresponding to the target IPdu and establishing a mapping relationship between the source IPdu and the target IPdu by referring to a previously generated IPdu triggering instance based on the source IPdu reference instance and the target IPdu reference instance.

Preferably the generating the signal mapping instance may include setting up locations of signals that are to be transferred to the communication cluster of the target IPdu by referring to a previously generated triggering instance based on the signal mapping instance.

In accordance with embodiments of the present invention the method and apparatus for setting up the gateway for the AUTOSAR based vehicle network allow an electronics application developer to more easily set up the gateway model of the vehicle network even if the developer does not know the configuration of a complicated network architecture model based on AUTOSAR.

The present invention will be described in detail below with reference to the accompanying drawings. In the following description redundant descriptions and detailed descriptions of known functions and elements that may unnecessarily make the gist of the present invention obscure will be omitted. Embodiments of the present invention are provided to fully describe the present invention to those having ordinary knowledge in the art to which the present invention pertains. Accordingly in the drawings the shapes and sizes of elements may be exaggerated for the sake of clearer description.

Hereinafter a method and apparatus for setting up a gateway for an AUTOSAR based vehicle network according to an embodiment of the present invention will be described in detail with reference to the attached drawings. The method and apparatus for setting up a gateway for an AUTOSAR based vehicle network according to the embodiment of the present invention are based on a software platform standard for automotive electronics automotive open system architecture hereinafter referred to as AUTOSAR but the present invention is not limited thereto.

Referring to the gateway setup apparatus for the AUTOSAR based vehicle network according to the embodiment of the present invention includes a structure setup unit a data setup unit and a gateway setup unit .

The structure setup unit receives structure setup input values from a user generates electronic control units hereinafter referred to as ECUs corresponding to the components of vehicle network communication and allocates communication channels between the ECUs. That is the structure setup unit sets up Unified Modeling Language UML code corresponding to a network structure model based on the allocated communication channels between the ECUs.

A network model based on AUTOSAR according to an embodiment of the present invention may have the forms shown in but the form of the network model is not limited thereto.

Referring to the structure of the network model includes ECU instances EcuInstance communication controller blocks CommunicationController communication connector blocks CommunicationConnector physical channels PhysicalChannel connector port blocks CommConnectorPort communication cluster blocks CommunicationCluster and Transport layer Tp channel blocks TpChannel .

The ECU instances correspond to instances included in the ECUs with one ECU instance included in each ECU and operate in conjunction with the plurality of communication controller blocks and communication connector blocks .

The communication controller blocks are controller blocks corresponding to the interfaces of a vehicle network for example FlexRay or Controller Area Network CAN .

The communication connector blocks are generated when the ECU intends to perform communication by using a specific physical channel . That is such a communication connector block corresponds to a connection node between the ECU and the specific physical channel . Here the physical channel includes a FlexRay physical channel . Further each communication connector block has a corresponding connector port block .

Each connector port block includes the directionality of reception in and transmission out with respect to the physical channel .

Each communication cluster block includes a FlexRay cluster FlexrayCluster and a CAN cluster CanCluster 

Each TP channel block includes a CanTp connection channel CanTpConnectionChannel and a FlexRayTp channel FlexrayTpChannel . Here the FlexRayTp channel includes a FlexRayTp connection block FlexrayTpConnection 

The above described network model based on AUTOSAR shown in is disclosed in detail in the specification of the System Template V3.1.0 of AUTOSAR and thus a detailed description thereof is omitted here.

Referring back to the data setup unit sets up the data that is to be transmitted via a communication channel between the ECUs using a specific wizard. Here the wizard corresponds to software for easily and conveniently executing complicated software or hardware operations using an interrogatory method and includes a system signal wizard SystemSignal Wizard by an Interaction layer Protocol Data Unit IPdu wizard a frame wizard etc.

A communication data model based on AUTOSAR according to an embodiment of the present invention has the forms shown in . are diagrams showing a single communication data model .

Referring to the communication data model includes a physical channel PhysicalChannel which is generated during the procedure of setting up a network structure.

The physical channel in the communication data model includes triggering instances or objects corresponding to instances that are to be transmitted through the physical channel . Here the triggering instances include a signal interaction signal triggering instance ISignalTriggering an IPdu triggering instance IPduTriggering and a frame triggering instance FrameTriggering .

The IPdu triggering instance includes information about a channel through which a specific IPdu is being transmitted.

The frame triggering instance includes information about a frame which is to be transmitted through a specific channel.

The signal triggering instance and the IPdu triggering instance are used when a specific ECU functions as a gateway. However the frame triggering instance is generally used for data transmission. In an embodiment of the present invention the step of setting up the gateway will be described in detail later.

For example data that is transmitted or received in an electronics application program is represented by signals as shown in . Referring to system signals hereinafter used together with signal are transferred to the communication module of the ECU with the system signals included in the IPdu . The IPdu transferred in this way is finally generated in the format of frames for respective bus types and the generated frames are transmitted to the corresponding buses. That is the system signals are referred to by the IPdu via an Interaction I signal to IPdu mapping instance ISignalTolPduMapping . The IPdu is referred to by a frame via a Pdu to frame mapping instant PduToFrameMapping . Then the frame is referred to by the frame triggering instance . As shown in in the frame the final source and destination are determined by referring to ports possessed by the communication connector block generated by the structure setup unit .

The above described communication data model based on AUTOSAR as shown in is disclosed in detail in the specification of the System Template V3.1.0 of AUTOSAR and thus a detailed description thereof will be omitted.

Referring back to the gateway setup unit sets up an ECU gateway based on the information set up during the procedure of setting up the network and communication data. In this case since the ECU functions as the gateway the gateway refers to an ECU instance which will function as the gateway and which is generated during the procedure of setting up the network structure.

A gateway model based on AUTOSAR according to an embodiment of the present invention has the form shown in .

Referring to the gateway model is implemented on the assumption that an ECU instance generated during the above procedure of setting up the network structure functions as a gateway. That is a gateway instance is generated by referring to the ECU instance functioning as the gateway. A mapping relationship with the gateway instance is established by a frame mapping instance FrameMapping an IPdu mapping instance IPduMapping and a signal mapping instance SignalMapping .

The frame mapping instance indicates a mapping relationship between frames to be used on different networks that are connected via the gateway. Here the frame mapping instance refers to frames that are set up by using the frame triggering instance in the above described communication data setup step.

The IPdu mapping instance indicates a mapping relationship between IPdus contained in the frames mapped to each other. In other words the IPdu mapping instance includes a source IPdu reference instance SourcelPduRef and a target IPdu reference instance TargetlPduRef corresponding to IPdus mapped to each other that is a source IPdu and a target IPdu. In an automotive communication protocol such as that for a Controller Area Network CAN only a single IPdu is contained in a single frame but in a protocol such as FlexRay one or more IPdus may be mapped to a single frame so that mapping between IPdus is required.

For example referring to the system signals are referred to by the IPdu via an I Signal to IPdu mapping instance ISignalTolPduMapping and the IPdu triggering instance refers to the information about frames mapped to each other by referring to the IPdu . Then the IPdu mapping instance detects a frame to which the source IPdu belongs by referring to the source IPdu reference instance . Further the IPdu mapping instance detects a frame to which the target IPdu belongs by referring to the target IPdu reference instance . The IPdu mapping instance establishes a mapping relationship between the IPdus by mapping a source IPdu and a target IPdu which are contained in the same frame to each other.

The signal mapping instance is configured to when signals included in the IPdus between which the mapping relationship has been established via the IPdu mapping instance are mapped to another IPdu via the gateway instance set locations to which the signals are to be transferred.

For example referring to system signals are referred to by the IPdu via the I Signal to IPdu mapping instance ISignalTolPduMapping and the triggering instance detects signals included in a communication cluster to which the source IPdu belongs by referring to the I Signal to IPdu mapping instance . Further the signal triggering instance detects signals included in a communication cluster to which the target IPdu belongs by referring to the I Signal to IPdu mapping instance . Then the signal mapping instance sets the locations of signals that are to be transferred to the communication cluster of the target IPdu when the source IPdu and the target IPdu contained in the same frame are mapped to each other by referring to the signal triggering instance .

Since the above described gateway model based on AUTOSAR shown in is disclosed in detail in the specification of the System Template V3.1.0 of AUTOSAR a detailed description thereof will be omitted.

Next the gateway setup unit for setting up the structure of the gateway model as shown in will be described in detail with reference to .

Referring to the gateway setup unit according to an embodiment of the present invention includes a candidate selection unit and a gateway generation unit .

The candidate selection unit selects a specific ECU as a gateway candidate when the specific ECU is connected to at least two communication clusters during the above procedure of setting up the network structure. For example as shown in the candidate selection unit selects an ECU instance as a gateway candidate because the ECU instance is connected to a CAN2 communication cluster and a High Speed CAN HSCAN communication cluster during the procedure of setting up the network structure.

Referring back to the gateway generation unit includes an instance generation unit a frame mapping unit an IPdu mapping unit and a signal mapping unit .

The instance generation unit selects the corresponding ECU as a gateway by using the context menu of the ECU selected as the candidate by the candidate selection unit and then generates a gateway instance . In this case the gateway instance refers to the ECU instance which will function as the gateway. Further the instance generation unit generates a frame mapping instance an IPdu mapping instance and a signal mapping instance which correspond to the lower layer instances of the gateway instance .

The instance generation unit includes an instance generation screen provided with a plurality of input blocks capable of receiving instance generation input values required to generate instances from the user and an example of the instance generation screen is depicted in . The instance generation screen is represented as shown in in which a Graphical User Interface GUI is used but is not limited to this example. The instance generation unit generates instances in such a way that when the user adds an entry by using the button of the instance generation screen or deletes an entry by using a button an entry is added to or deleted from the instance generation screen.

In detail referring to the instance generation unit receives instance generation input values required to generate instances. In other words when the user adds an entry by using the button the instance generation unit generates an IPdu list belonging to the corresponding communication cluster in a source cluster block on the basis of the instance generation input values. Further the instance generation unit displays a source IPdu selected by the user from the IPdu list on a source IPdu block . The instance generation unit generates an IPdu list belonging to the corresponding communication cluster in a target cluster block on the basis of the instance generation input values. Further the instance generation unit displays a target IPdu selected by the user from the IPdu list on a target IPdu block . In this case a list of signals included in the source IPdu is displayed in the procedure of selecting the target IPdu. When the user selects relevant signals storage locations of the target IPdu where the selected signals are to be stored are selected.

Further the instance generation unit generates a frame mapping instance which will perform mapping between frames including source IPdus and target IPdus on the basis of information selected by the user on the instance generation screen. Furthermore the instance generation unit generates an IPdu mapping instance including a source IPdu reference instance corresponding to the source IPdus and a target IPdu reference instance corresponding to the target IPdus. The instance generation unit generates a signal mapping instance for setting up locations at which signals are to be transferred to the communication cluster when signals of a source IPdu and the signals of a target IPdu are mapped to each other.

The frame mapping unit maps frames including source IPdus to frames including target IPdus by using the frame mapping instance generated by the instance generation unit . That is the frame mapping unit establishes a mapping relationship between the frames including the source IPdus and the frames including the target IPdus by referring to the frame triggering instance including information about frames to be transmitted through a specific channel on the basis of the frame mapping instance .

The IPdu mapping unit establishes a mapping relationship between IPdus by mapping a source IPdu and a target IPdu contained in the same frame to each other by using the IPdu mapping instance generated by the instance generation unit . That is the IPdu mapping unit establishes a mapping relationship between the IPdus by mapping a source IPdu and a target IPdu contained in the same frame to each other by referring to the IPdu triggering instance based on the source IPdu reference instance and the target IPdu reference instance of the IPdu mapping instance .

The signal mapping unit maps signals included in the source IPdu and the target IPdu between which the mapping relationship has been established to each other by using the signal mapping instance generated by the instance generation unit . That is the signal mapping unit sets up locations at which signals selected by the user from among the signals included in the source IPdu are to be transferred to the communication cluster of the target IPdu when the source IPdu and the target IPdu contained in the same frame are mapped to each other by referring to the signal triggering instance based on the signal mapping instance .

Next a method of setting up a gateway for an AUTOSAR based vehicle network will be described in detail with reference to .

Referring to in the gateway setup apparatus for the AUTOSAR based vehicle network according to the embodiment of the present invention the candidate selection unit of the gateway setup unit determines whether a specific ECU is connected to one or more communication clusters during the procedure of generating a network structure based on AUTOSAR. During the procedure if a specific ECU instance is connected to one or more communication clusters the candidate selection unit selects the corresponding ECU instance as a gateway candidate at step S.

The instance generation unit selects the corresponding ECU instance selected as the candidate as the gateway by using the context menu of the ECU instance and then generates a gateway instance . On the basis of instance generation input values entered by the user to generate instances the instance generation unit displays a relevant communication cluster on the source cluster block of the instance generation screen displays a relevant source IPdu on the source IPdu block displays a relevant communication cluster on the target cluster block and displays a relevant target IPdu on the target IPdu block see . The instance generation unit generates a frame mapping instance an IPdu mapping instance and a signal mapping instance based on information selected by the user from the instance generation screen at step S.

When the generation of all the instances for setting up the gateway has been completed the frame mapping unit establishes a mapping relationship between a frame containing the source IPdu and a frame containing the target IPdu by referring to the frame triggering instance based on the frame mapping instance at step S.

If the establishment of the mapping relationship between the frames has been completed the IPdu mapping unit establishes a mapping relationship between IPdus by mapping the source IPdu and the target IPdu contained in the same frame to each other by referring to the IPdu triggering instance based on a source IPdu reference instance and a target IPdu reference instance included in the IPdu mapping instance at step S.

If the establishment of the mapping relationship between IPdus has been completed the signal mapping unit sets up locations at which signals selected by the user from among signals included in the source IPdu are to be transferred to the communication cluster of the target IPdu when the source IPdu and the target IPdu contained in the same frame are mapped to each other by referring to the signal triggering instance based on the signal mapping instance at step S.

As described above the method of setting up the gateway for the AUTOSAR based vehicle network according to the embodiment of the present invention allows an electronics application developer to more easily set up the gateway model of the vehicle network even if the developer does not know the configuration of a complicated network architecture model based on AUTOSAR.

As described above optimal embodiments of the present invention have been disclosed in the drawings and the present specification. In this case although specific terms have been used those terms are merely intended to describe the present invention and are not intended to limit the meanings and the scope of the present invention as disclosed in the accompanying claims. Therefore those skilled in the art will appreciate that various modifications and other equivalent embodiments are also possible given the above description. Therefore the technical scope of the present invention should be defined by the technical spirit of the accompanying claims.

