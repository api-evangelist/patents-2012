---

title: Managing a work product in a systems development lifecycle
abstract: An approach is provided for managing a work product. A data model is stored. A functional requirement is traced to an implemented service by displaying a sequence of displays: (1) details of the functional requirement; (2) details of a process element related to the functional requirement by the data model; (3) details of a business service related to the process element by the data model; (4) details of an information technology (IT) service design related to the business service by the data model; (5) details of a service component of the business service, the service component related to the IT service design by the data model; and (6) a document supporting the implemented service. Each of the displays (2) through (6) is displayed in response to a receipt of a selection of a hyperlink included in the previous display in the sequence.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08769481&OS=08769481&RS=08769481
owner: International Business Machines Corporation
number: 08769481
owner_city: Armonk
owner_country: US
publication_date: 20120906
---
This application is a divisional application claiming priority to Ser. No. 12 571 522 filed Oct. 1 2009.

The present invention relates to a data processing method and system that defines and utilizes a meta data model representing work products and deliverables and more particularly to a meta data model that provides traceability of business requirements to implemented services.

Conventional techniques for managing work products and deliverables focus on individual business requirements and the corresponding information technology IT that supports the business requirements without providing an overall business architecture context. Such conventional techniques result in inefficient duplicated services thereby failing to facilitate reusability of service oriented architecture SOA solutions. Furthermore the known techniques for managing work products and deliverables are deficient in identifying valuable types of SOA solution capabilities. Thus there exists a need to overcome at least one of the preceding deficiencies and limitations of the related art.

In first embodiments the present invention provides a computer program product comprising a computer readable storage medium. A computer readable program code is stored in the computer readable storage medium. The computer readable program code contains instructions executable by a processor of a computer system to implement a method of tracing a business requirement to an implemented service in a systems development lifecycle by processing data conforming to a data model. The data model comprises 

a sixth asset type service component type that represents a service component of the business service 

a first relationship between the functional requirement type and the process element type wherein the first relationship specifies that the functional requirement is represented as the process element 

a second relationship between the process element type and the business service type wherein the second relationship specifies that the process element identifies the business service 

a third relationship between the business service type and the standard type wherein the third relationship specifies that the business service conforms to the standard 

a fourth relationship between the business service type and the service design type wherein the fourth relationship specifies that the business service is designed as the IT service design 

a fifth relationship between the standard type and the service design type wherein the fifth relationship specifies that the standard is a design template for the IT service design and

a sixth relationship between the service design type and the service component type wherein the sixth relationship specifies that the service design provides design guidelines for the service component 

wherein the service component realizes a service interface represented by a service interface type wherein the service interface specifies the implemented service represented by a service implementation type 

wherein the functional requirement type the process element type the business service type the service design type the service component type the first relationship the second relationship the fourth relationship and the sixth relationship provide a tracing between the functional requirement and the implemented service and

wherein the first asset type the second asset type the third asset type the fourth asset type the fifth asset type and the sixth asset type are heterogeneous asset types.

In second embodiments the present invention provides a computer implemented method of managing a work product in a systems development lifecycle. The method comprises 

a computer system tracing a functional requirement to an implemented service wherein the tracing includes 

A process for supporting computing infrastructure corresponding to the above summarized method is also described and claimed herein.

The present invention provides a program product and method for managing work products by utilizing a meta data model that provides traceability between requirements and implemented services. Relationships e.g. dependencies between work products are enforced by the meta data model so that any missing work products along the development lifecycle are easily identified. The meta data model also captures reuse of services by highlighting which consumers are calling on the service. Furthermore the meta data model highlights the multiple capabilities that can be leveraged to fulfill an outcome.

One or more embodiments of the present invention provide a data model that represents meta data of work products a.k.a. assets and deliverables that are developed as a business initiative progresses along a systems development lifecycle. The data model also represents relationships between assets where the relationships provide traceability of a business requirement to an implemented service. Furthermore the data model indicates information of interest e.g. asset type artifact and common attributes as well as the role of each item of the information in the systems development lifecycle. Moreover a software application that utilizes the data model facilitates reuse of services by highlighting multiple consumers that are calling for the provision of a service. A software application using the data model may also highlight the multiple capabilities that can be leveraged to fulfill a business outcome. Hereinafter the data model for managing work products and deliverables and providing traceability between business requirements and implemented services is also simply referred to as the data model or the meta data model. 

Application Category Schema a category schema that specifies a system with a set of functional and data support packaged to provide an automated system to support a business need.

Artifact a.k.a. artefact a specification of a physical piece of information that is used or produced in a systems development lifecycle or by deployment and operation of a system. Examples of artifacts include model files source files scripts binary executable files tables in a database system development deliverables word processing document and mail messages.

Business Architecture see phase of a systems development lifecycle that captures the business model including business process and business data that supports the business.

Business Process Category Schema the set of activities that are performed to achieve a desired outcome.

Business Requirement a requirement that describes in business terms what must be delivered or accomplished to provide value.

Business Service Asset Type asset type that represents related business activities and supporting data where the business activities are performed to deliver business outcomes. A business service may satisfy a business outcome in an SOA environment. A business service is described in a Service Profile that documents purpose scope triggers and outcomes to enable solution teams to understand the business intent of the business service.

Business Service Architecture see phase of a systems development lifecycle in which the business services are defined including detail of dependencies and role of each service such as Consumer or Producer.

Consumer Category Schema a category schema that specifies the asset that consumes a service. A consumer specified by a consumer category schema may be a person or a computer system.

Customer Category Schema a category schema that specifies the primary stakeholder for which the system computer or other is being developed.

Data Requirement Asset Type asset type that specifies the data that is required by an organization to manage the business.

Deliverable a specialized type of work product used to define the primary outputs that represent value material or otherwise to the client customer or other stakeholders. Deliverables are typically the result of packaging other work products for sign off and delivery.

Entity Object Asset Type asset type that describes the data that is processed by a business service to deliver a business outcome.

Functional Requirement Asset Type asset type that specifies a necessary function result or capability of a delivered information technology system or of a component thereof. Functional requirements are also known as capabilities. A function specified by a functional requirement is a set of inputs behavior and outputs. Functional requirements may be calculations technical details data manipulation and processing and other specific functionality that define what a system is supposed to accomplish.

Generic Process Category Schema a common set of business activities that applies across a number of business scenarios that enables a common application of business process implementation.

Heritage Category Schema a classification of a system that is deemed to have strategic importance to an organization and that is also considered legacy .

Human Service Design Asset Type asset type that specifies the aspects of a solution that is being implemented using human technology.

IT Service Design Asset Type asset type that specifies the aspects of a solution that is being implemented using computer technology.

Legacy Category Schema a classification of a system that is deemed to have minimal strategic relevance to an organization and that will be considered for strategic replacement.

Non functional Requirement Asset Type asset type that specifies criteria for judging the operation of an information technology system i.e. how well the system performs its functions rather than specific behaviors of the system. Non functional requirements are also known as quality requirements qualities quality attributes quality goals constraints performance requirements or quality of service requirements. Examples of non functional requirements include requirements that specify usability availability reliability supportability testability maintainability scalability extensibility look and feel performance or ease of use of a system.

Process Asset Type asset type that represents either 1 a generic process that is used to identify generic business services or 2 an end to end process in operation.

Process Element Asset Type asset type that represents a business requirement and is used as input to identifying and defining business services.

Provider Category Schema a category schema that specifies the asset that provides or exposes a service. A provider specified by a provider category schema may be a person or a computer system.

P2P Service Design Category Schema a category schema that specifies point to point P2P interfacing between two or more software components.

Requirement a statement that identifies a necessary attribute capability characteristic or quality of an information technology system in order for the system to have value and utility to a user.

Requirements see phase of a systems development lifecycle in which an organization s business needs are specified.

Service a solution component that is designed to satisfy a business process element or activity with associated data in a business process.

 Service Component Asset Type asset type that specifies a reusable object or program that performs a specific function is designed to work with other components and applications and that is designed to implement an activity using computer technology.

Service Component Test Asset Type asset type that specifies the test required to ensure the service component fulfills the business requirements.

Service Design see phase of a systems development lifecycle in which the business service architecture is designed.

Service Development see phase of a systems development lifecycle in which components of the service design are developed.

Service Implementation see phase of a systems development lifecycle in which a service is implemented.

Service Interface Asset Type asset type that specifies how the interface is being implemented for the service.

SOA Solution describes the IT Architectural style in which a solution is being designed and implemented.

Supplier Category Schema a category schema that specifies the asset that can be described as a Supplier of goods and or services or an entity allied with the Customer based on a partnering arrangement that facilitates a sustainable competitive advantage.

Systems Development Lifecycle a.k.a. software development lifecycle any logical process used by a systems analyst to develop or alter an information technology system.

Test Case Asset Type asset type that specifies the test scenarios that validate that the business requirements are being met.

Test Data Asset Type asset type that specifies the test data that is used to validate the implemented solution.

Work Product defines and describes the items needed as input or created as output of one or more tasks that are the responsibility of a single role.

Components of the meta data model that are used during the requirements phase are illustrated in . Components of the meta data model that are used during the business architecture phase are illustrated in . Components of the meta data model that are used during the business service architecture phase are illustrated in . Components of the meta data model that are used during the service design phase are illustrated in and . Components of the meta data model that are used during the service development phase are illustrated in . Components of the meta data model that are used during the service implementation phase are illustrated in .

The portions of the meta data model shown in and include boxes where each box indicates an asset type or a category schema.

A box in the meta data model that indicates an asset type is divided into an upper portion and a lower portion. The upper portion of such a box designates the box as an asset type and includes the name of the asset type. The lower portion of the box includes zero or more attributes of the asset type indicated in the upper portion of the box.

Similarly a box i.e. category schema box in the meta data model that indicates a category schema has an upper portion and a lower portion. The upper portion of a category schema box designates the box as a category schema and includes the name of the category schema. The lower portion of a category schema box includes one or more attributes of the category schema indicated in the upper portion of the category schema box.

The asset types shown in the meta data model are heterogeneous asset types defined according to the Definitions section presented above. The category schemas shown in the meta data model are heterogeneous category schemas defined according to the Definitions section presented above. The names of asset types category schemas and attributes shown in the meta data model are examples and the present invention contemplates that other names may be used instead of the names shown in and .

It should be noted that the multiplicity values included in the discussions of and include 0 . . . 1 i.e. zero or one 1 i.e. one only 0 . . . i.e. zero or more and 1 . . . i.e. one or more .

A requirement specified by requirement asset type may be a functional requirement specified by asset type a non functional requirement specified by asset type or a data requirement specified by asset type .

As indicated by label A the meta data model includes a relationship between functional requirement asset type and a process element asset type see where the relationship indicates that a functional requirement specified by asset type is represented as a process element specified by the process element asset type see with a multiplicity value of 0 . . . .

As indicated by label B non functional requirement asset type is related to an entity asset type see in the meta data model so that a non functional requirement specified by asset type constrains an entity specified by entity asset type see with a multiplicity value of 0 . . . .

As indicated by label C the meta data model also includes a relationship between data requirement asset type and entity asset type see where the relationship indicates that a data requirement specified by asset type is represented as an entity specified by entity asset type see with a multiplicity value of 0 . . . .

A process specified by process asset type may be categorized as a business process specified by category schema or as a generic process specified by category schema .

As indicated by label D the meta data model includes a relationship between process asset type and process element asset type see where a process specified by process asset type references a process element specified by process element asset type see with a multiplicity value of 0 . . . .

Further as indicated by label E the meta data model includes a relationship between business process category schema and a service interface asset type see where the relationship indicates that a business process specified by category schema is fulfilled by a service interface specified by service interface asset type see with a multiplicity value of 0 . . . .

Still further as indicated by label F the meta data model includes a relationship between generic process category schema and a business service asset type see where the relationship indicates that a generic process specified by category schema involves a business service specified by business service asset type see with a multiplicity value of 0 . . . .

In portion of the meta data model includes process element asset type and entity asset type which are utilized in the business architecture phase of systems development lifecycle see .

The meta data model includes the relationship see label D between process element asset type and process asset type see where the relationship indicates that a process element specified by asset type is referenced in a process specified by the process asset type see with a multiplicity value of 0 . . . .

The meta data model also includes the relationship see label A between process element asset type and functional requirement asset type see where the relationship indicates that a process element specified by asset type represents in a functional requirement specified by functional requirement asset type see with a multiplicity value of 0 . . . .

Moreover as indicated by label G the meta data model includes a relationship between process element asset type and business service asset type see where the relationship indicates that a process element specified by asset type identifies a business service specified by business service asset type see with a multiplicity value of 0 . . . 1.

With respect to entity asset type the meta data model includes relationships between the entity asset type and non functional requirement asset type see data requirement asset type see business service asset type see and a test data asset type see .

The relationship see label B between the entity asset type and non functional requirement asset type see indicates that an entity specified by asset type is constrained by a non functional requirement specified by asset type see with a multiplicity value of 0 . . . .

Further the relationship see label C between entity asset type and data requirement asset type see indicates that an entity specified asset type represents a data requirement specified by asset type see with a multiplicity value of 0 . . . .

Still further the relationship see label H between entity asset type and business service asset type see indicates that an entity specified by asset type describes data of a business service specified by asset type see with a multiplicity value of 0 . . . .

Further yet the relationship see label I between entity asset type and test data asset type see indicates that an entity specified by asset type is required for test data specified by asset type see with a multiplicity value of 1 . . . .

A consumer specified by consumer category schema is a generalization of a customer specified by category schema and of a supplier specified by supplier category schema . As used herein a generalization is defined as an inheritance relationship of a UML class diagram. That is if type A is a generalization of type B then any instance of type B is also an instance of type A and an instance of type B inherits the behavior and functionality of type A. The consumer is also a generalization of an application specified by application category schema . As indicated by label K the consumer is a generalization of a business service specified by business service asset type see .

A provider specified by provider category schema is a generalization of an application specified by application category schema . The provider is also a generalization of a supplier specified by category schema . As indicated by label L the provider is a generalization of a business service specified by business service asset type see .

An application specified by application category schema is a generalization of a heritage specified by category schema a package specified by category schema and a legacy specified by category schema .

As indicated by label J the meta data model includes a relationship between consumer category schema and business service asset type see where the relationship indicates that a consumer specified by category schema is a consumer of a business service specified by business service asset type see with a multiplicity value of 0 . . . .

Further as indicated by label M the meta data model includes a relationship between provider category schema and business service asset type see where the relationship indicates that a provider specified by the category schema provides a business service specified by asset type see with a multiplicity value of 0 . . . .

Still further as indicated by label N the meta data model includes a relationship between application category schema and an API asset type see where the relationship indicates that an application specified by category schema provides an API specified by asset type see with a multiplicity value of 0 . . . .

In portion of the meta data model includes business service asset type and a standard asset type which are utilized in the business service architecture phase of systems development lifecycle see .

The meta data model includes a relationship between business service asset type and standard asset type where the relationship indicates that a business service specified by asset type conforms to one or more standards specified by asset type and a standard specified by asset type is a design template for zero or more business services specified by asset type .

The relationship designated by label F indicates that a business service specified by asset type is involved in a generic process specified by category schema see with a multiplicity value of 0 . . . .

The relationship designated by label G indicates that a business service specified by asset type is identified from a process element specified by asset type see with a multiplicity value of 1 . . . .

The relationship designated by label H indicates that a business service specified by asset type operates on data specified by asset type see with a multiplicity value of 1 . . . .

The relationship designated by label J indicates that a business service specified by asset type is consumed by a consumer specified by category schema see with a multiplicity value of 0 . . . .

The relationship designated by label M indicates that a business service specified by asset type is offered by a provider specified by category schema see with a multiplicity value of 0 . . . .

As indicated by label O the meta data model includes a relationship between business service asset type and a test case asset type see where the relationship indicates that a business service specified by asset type has needs met by a test case specified by asset type see with a multiplicity value of 1 . . . .

As indicated by label P the meta data model includes a relationship between business service asset type and an IT service design asset type see where the relationship indicates that a business service specified by asset type is designed as an IT service design specified by asset type see with a multiplicity value of 0 . . . .

As indicated by label Q the meta data model includes a relationship between business service asset type and a human service design asset type see where the relationship indicates that a business service specified by asset type is designed as a human service design specified by asset type see with a multiplicity value of 0 . . . .

The meta data model includes a reflexive association that indicates that a first instance of a business service specified by asset type is derived from zero or more other instances of the business service and a second instance of the business service is a composite of one or more other instances of the business service.

As indicated by label R the meta data model includes a relationship between standard asset type and IT service design asset type see where the relationship indicates that a standard specified by asset type is a design template for an IT service design specified by asset type see with a multiplicity value of 0 . . . .

An IT service design specified by asset type may be categorized as a P2P service design specified by category schema or as a SOA service design specified by category schema .

The relationship designated by label Q indicates that a human service design specified by asset type is designed for only one business service specified by asset type see .

The relationship designated by label P indicates that an IT service design specified by asset type is designed for only one business service specified by asset type see .

The relationship designated by label R indicates that an IT service design specified by asset type conforms to a standard specified by asset type see with a multiplicity value of 1 . . . .

As indicated by label S the meta data model includes a relationship between IT service design asset type and service interface asset type see where the relationship indicates that an IT service design specified by asset type provides design guidelines for a service interface specified by asset type see with a multiplicity value of 0 . . . .

As indicated by label T the meta data model includes a relationship between IT service design asset type and service component asset type see where the relationship indicates that an IT service design specified by asset type provides design guidelines for a service component specified by asset type see with a multiplicity value of 0 . . . .

The relationship designated by label N indicates that an API specified by asset type is owned by only one application specified by category schema see .

As indicated by label U the meta data model includes a relationship between API asset type and service component asset type see where the relationship indicates that an API specified by asset type calls a service adapter attribute of a service component specified by asset type see with a multiplicity value of 0 . . . .

The relationship designated by label S indicates that a service interface specified by asset type conforms to only one IT service design specified by asset type see .

The relationship designated by label E indicates that a service interface specified by asset type fulfills a business process specified by category schema see with a multiplicity value of 0 . . . .

As indicated by label V the meta data model includes a relationship between service interface asset type and service component asset type see where the relationship indicates that a service interface specified by asset type is realized by a service component specified by asset type see with a multiplicity value of 1 . . . .

The meta data model also includes a relationship between service interface asset type and service implementation asset type where the relationship indicates that a service interface specified by asset type specifies zero or more service implementations specified by asset type and that a service implementation specified by asset type is specified by only one service interface specified by asset type .

In portion of the meta data model includes service component asset type which is utilized in the service development phase of systems development lifecycle see .

The relationship designated by label T indicates that a service component specified by asset type conforms to only one IT service design specified by asset type see .

The relationship designated by label U indicates that an API specified by asset type see is called by only one service adapter attribute of a service component specified by asset type .

The relationship designated by label V indicates that a service component specified by asset type realizes only one service interface specified by asset type see .

As indicated by label W the meta data model includes a relationship between service component asset type and a service component test asset type see where the relationship indicates that a service component specified by asset type is a capability confirmed by a service component test specified by asset type see with a multiplicity value of 1 . . . .

As indicated by label X the meta data model includes a relationship between service component asset type and a service component test asset type see where the relationship indicates that a service component specified by asset type is tested using a service component test specified by asset type see with a multiplicity value of 1 . . . .

In portion of the meta data model includes test data asset type and a service test object . Test data asset type is utilized in the service design phase of systems development lifecycle see . Service test object is utilized in the service development phase of systems development lifecycle see . Service test object includes test case asset type and service component test asset type.

The relationship designated by label I indicates that test data specified by asset type confirms data requirements of an entity specified by asset type see with a multiplicity value of 1 . . . .

The relationship designated by label O indicates that a test case specified by asset type confirms a capability of only one business service specified by asset type see .

The relationship designated by label X indicates that a service component test specified by asset type is used to test a service component specified by asset type see with a multiplicity value of 0 . . . .

The relationship designated by label W indicates that a service component test specified by asset type is developed for only one service component specified by asset type see .

The meta data model includes a relationship between test data asset type and test case asset type where the relationship indicates that test data specified by asset type is used in zero or more test cases specified by asset type and that a test case specified by asset type uses zero or more test data specified by asset type .

The meta data model also includes a relationship between test case asset type and service component asset type where the relationship indicates that a test case specified by asset type applies to one or more service component tests specified by asset type and that a service component test specified by asset type is governed by only one test case specified by asset type .

An instance of the meta data model may be stored in a computer data storage device coupled to a computer system e.g. in a relational database stored on a data storage device . The computer system receives user provided selections e.g. selections of hyperlinks via a user interface such as graphical user interface GUI presented on a display unit coupled to the computer system. In response to receiving the selections the computer system presents a series of displays for viewing by the user. The series of displays presents a series of relationships between assets used in a systems development lifecycle where the series of relationships presents a tracing between a business requirement and an implemented service for viewing by the user.

In a first tracing between a business requirement and an implemented service the computer system presents a series of displays based on user provided selections where a first display in the series includes details of a functional requirement a second display in the series includes details of a process element related to the functional requirement a third display in the series includes details of a business service related to the process element a fourth display in the series includes details of an IT service design related to the business service and a fifth display in the series includes details of a service component related to the IT service design.

The service component realizes a service interface represented by a service interface asset type and the service interface specifies an implemented service associated with the service component. Thus the first tracing shows a relationship between the functional requirement in the first display and the implemented service associated with the service component in the fifth display.

In the aforementioned first tracing the computer system generates the first display after the computer system accesses a stored functional requirement specified by the functional requirement asset type see . The computer system generates the second display after the computer system accesses a stored process element specified by the process element asset type see . The computer system generates the third display after the computer system accesses a stored business service specified by the business service asset type see . The computer system generates the fourth display after the computer system accesses a stored IT service design specified by the IT service design asset type see . The computer system generates the fifth display after the computer system accesses a stored service component specified by the service component asset type see .

The aforementioned actions of accessing the stored functional requirement process element business service IT service design and service component are performed in response to the computer system receiving user provided selections of displayed hyperlinks.

In a second tracing between a business requirement and an implemented service the computer system presents a series of displays based on user provided selections where a first display in the series includes details of a data requirement specified by asset type see a second display in the series includes details of an entity specified by asset type see a third display in the series includes details of a business service specified by asset type see a fourth display in the series includes details of an IT service design specified by asset type see and a fifth display in the series includes details of a service component specified by asset type see .

The service component displayed in the second tracing realizes a service interface represented by a service interface asset type and the service interface specifies an implemented service associated with the service component. Thus the second tracing shows a relationship between the data requirement in the first display and the implemented service associated with the service component in the fifth display.

Similar to the first tracing each display in the series of displays is generated by the computer system after accessing a corresponding stored item in a database and the accessing is performed by the computer system in response to the computer system receiving user provided selections of displayed hyperlinks.

The traceability between functional requirement FR and service component SC is shown by the computer system performing the following actions 1 receiving an activation of hyperlink Process Element PE in display see 2 in response to 1 generating and displaying display see 3 receiving an activation of hyperlink Business Service BS in display see 4 in response to 3 generating and displaying display see 5 receiving an activation of hyperlink IT Service Design SD in display see 6 in response to 5 generating and displaying display see 7 receiving an activation of hyperlink Service Component SC in display see and 8 in response to 7 generating and displaying display see .

In step the computer system displays a traceability between a functional requirement and an implemented service. The details of step are included in .

In step the computer system identifies and displays multiple consumers that are calling upon the implemented service to provide an outcome. The identification of the multiple consumers in step facilitates the reuse of a service.

In step the computer system identifies and displays a solution that is provided by multiple capabilities that can be leveraged to fulfill an outcome.

The present invention contemplates versions of the process of that include any combination and any order of steps and .

In optional step step s and or are repeated for one or more other functional requirements and or one or more other implemented services. The process of ends at step .

In step the computer system receives a user provided selection of a hyperlink e.g. hyperlink Process Element PE in on the display generated in step .

In step the computer system generates a display e.g. display in of details of a process element related to the functional requirement by the meta data model whose instance is stored in step see . The process element is specified by asset type see .

In step the computer system receives a user provided selection of a hyperlink e.g. hyperlink Business Service BS in on the display generated in step .

In step the computer system generates a display e.g. display in of details of a business service related to the process element by the meta data model whose instance is stored in step see .

In step the computer system receives a user provided selection of a hyperlink e.g. hyperlink IT Service Design SD in on the display generated in step .

Step is followed by step in . In step the computer system generates a display e.g. display in of details of an IT service design related to the business service by the meta data model whose instance is stored in step see .

In step the computer system receives a user provided selection of a hyperlink e.g. hyperlink Service Component SC in on the display generated in step .

In step the computer system generates a display e.g. display in of details of a service component related to the IT service design by the meta data model whose instance is stored in step see .

In step the computer system displays one or more hyperlinks for displaying one or more documents that support the implemented service. The one or more hyperlinks are associated with the one or more documents in a one to one correspondence. In one embodiment the one or more hyperlinks include text that identifies the names of the one or more documents. The one or more hyperlinks may be displayed on the display generated in step or the one or more hyperlinks may be displayed on a different display resulting from selecting a hyperlink e.g. a Content hyperlink included in the display generated in step .

In step in response to receiving the selection in step the computer system displays the document corresponding to the hyperlink whose selection is received in step . The process of ends at step .

Memory may comprise any known computer readable storage medium which is described below. In one embodiment cache memory elements of memory provide temporary storage of at least some program code e.g. program code in order to reduce the number of times code must be retrieved from bulk storage while instructions of the program code are carried out. Moreover similar to CPU memory may reside at a single physical location comprising one or more types of data storage or be distributed across a plurality of physical systems in various forms. Further memory can include data distributed across for example a local area network LAN or a wide area network WAN .

I O interface comprises any system for exchanging information to or from an external source. I O devices comprise any known type of external device including a display device e.g. monitor for displaying the displays in and keyboard mouse printer speakers handheld device facsimile etc. Bus provides a communication link between each of the components in computer system and may comprise any type of transmission link including electrical optical wireless etc.

I O interface also allows computer system to store and retrieve information e.g. data or program instructions such as program code from an auxiliary storage device such as computer data storage unit or another computer data storage unit not shown . Computer data storage unit may comprise any known computer readable storage medium which is described below. For example computer data storage unit may be a non volatile data storage device such as a magnetic disk drive i.e. hard disk drive or an optical disc drive e.g. a CD ROM drive which receives a CD ROM disk .

Memory may include computer program code that provides the logic for managing work products by utilizing the meta data model that provides traceability between requirements and implemented services e.g. the process of . Further memory may include other systems not shown in such as an operating system e.g. Linux that runs on CPU and provides control of various components within and or connected to computer system .

Memory storage unit and or one or more other computer data storage units not shown that are coupled to computer system may store a database that includes one or more instances of the meta data model.

As will be appreciated by one skilled in the art the present invention may be embodied as a system method or computer program product. Accordingly aspects of the present invention may take the form of an entirely hardware embodiment an entirely software embodiment including firmware resident software micro code etc. or an embodiment combining software and hardware aspects that may all generally be referred to herein as a module or system e.g. computer system . Furthermore an embodiment of the present invention may take the form of a computer program product embodied in one or more computer readable medium s e.g. memory or computer data storage unit having computer readable program code e.g. program code embodied or stored thereon.

Any combination of one or more computer readable medium s e.g. memory and computer data storage unit may be utilized. The computer readable medium may be a computer readable signal medium or a computer readable storage medium. A computer readable storage medium may be for example but not limited to an electronic magnetic optical electromagnetic infrared or semiconductor system apparatus device or any suitable combination of the foregoing. A non exhaustive list of more specific examples of the computer readable storage medium includes an electrical connection having one or more wires a portable computer diskette a hard disk a random access memory RAM a read only memory ROM an erasable programmable read only memory EPROM or Flash memory an optical fiber a portable compact disc read only memory CD ROM an optical storage device a magnetic storage device or any suitable combination of the foregoing. In the context of this document a computer readable storage medium may be any tangible medium that can contain or store a program for use by or in connection with a system apparatus or device for carrying out instructions.

A computer readable signal medium may include a propagated data signal with computer readable program code embodied therein for example in baseband or as part of a carrier wave. Such a propagated signal may take any of a variety of forms including but not limited to electromagnetic optical or any suitable combination thereof. A computer readable signal medium may be any computer readable medium that is not a computer readable storage medium and that can communicate propagate or transport a program for use by or in connection with a system apparatus or device for carrying out instructions.

Program code e.g. program code embodied on a computer readable medium may be transmitted using any appropriate medium including but not limited to wireless wireline optical fiber cable RF etc. or any suitable combination of the foregoing.

Computer program code e.g. program code for carrying out operations for aspects of the present invention may be written in any combination of one or more programming languages including an object oriented programming language such as Java Smalltalk C or the like and conventional procedural programming languages such as the C programming language or similar programming languages. The program code may execute entirely on a user s computer partly on the user s computer as a stand alone software package partly on the user s computer and partly on a remote computer or entirely on the remote computer or server where the aforementioned user s computer remote computer and server may be for example computer system or another computer system not shown having components analogous to the components of computer system included in . In the latter scenario the remote computer may be connected to the user s computer through any type of network not shown including a LAN or a WAN or the connection may be made to an external computer e.g. through the Internet using an Internet Service Provider .

Aspects of the present invention are described herein with reference to flowchart illustrations e.g. and or block diagrams of methods apparatus systems e.g. and computer program products according to embodiments of the invention. It will be understood that each block of the flowchart illustrations and or block diagrams and combinations of blocks in the flowchart illustrations and or block diagrams can be implemented by computer program instructions e.g. program code . These computer program instructions may be provided to a processor e.g. CPU of a general purpose computer special purpose computer or other programmable data processing apparatus to produce a machine such that the instructions which execute via the processor of the computer or other programmable data processing apparatus create means for implementing the functions acts specified in the flowchart and or block diagram block or blocks.

These computer program instructions may also be stored in a computer readable medium e.g. memory or computer data storage unit that can direct a computer e.g. computer system other programmable data processing apparatus or other devices to function in a particular manner such that the instructions stored in the computer readable medium produce an article of manufacture including instructions which implement the function act specified in the flowchart and or block diagram block or blocks.

The computer program instructions may also be loaded onto a computer e.g. computer system other programmable data processing apparatus or other devices to cause a series of operational steps to be performed on the computer other programmable apparatus or other devices to produce a computer implemented process such that the instructions which execute on the computer other programmable apparatus or other devices provide processes for implementing the functions acts specified in the flowchart and or block diagram block or blocks.

Any of the components of an embodiment of the present invention can be deployed managed serviced etc. by a service provider that offers to deploy or integrate computing infrastructure with respect to the process of managing work products by utilizing the meta data model that provides traceability between requirements and implemented services. Thus an embodiment of the present invention discloses a process for supporting computer infrastructure comprising integrating hosting maintaining and deploying computer readable code e.g. program code into a computer system e.g. computer system wherein the code in combination with the computer system is capable of performing a process of managing work products by utilizing the meta data model that provides traceability between requirements and implemented services.

In another embodiment the invention provides a business method that performs the process steps of the invention on a subscription advertising and or fee basis. That is a service provider such as a Solution Integrator can offer to create maintain support etc. a process of managing work products by utilizing the meta data model that provides traceability between requirements and implemented services. In this case the service provider can create maintain support etc. a computer infrastructure that performs the process steps of the invention for one or more customers. In return the service provider can receive payment from the customer s under a subscription and or fee agreement and or the service provider can receive payment from the sale of advertising content to one or more third parties.

The flowcharts in and the block diagrams in A B A B A C and illustrate the architecture functionality and operation of possible implementations of systems methods and computer program products according to various embodiments of the present invention. In this regard each block in the flowchart or block diagrams may represent a module segment or portion of code e.g. program code which comprises one or more executable instructions for implementing the specified logical function s . It should also be noted that in some alternative implementations the functions noted in the block may occur out of the order noted in the figures. For example two blocks shown in succession may in fact be performed substantially concurrently or the blocks may sometimes be performed in reverse order depending upon the functionality involved. It will also be noted that each block of the block diagrams and or flowchart illustrations and combinations of blocks in the block diagrams and or flowchart illustrations can be implemented by special purpose hardware based systems that perform the specified functions or acts or combinations of special purpose hardware and computer instructions.

While embodiments of the present invention have been described herein for purposes of illustration many modifications and changes will become apparent to those skilled in the art. Accordingly the appended claims are intended to encompass all such modifications and changes as fall within the true spirit and scope of this invention.

