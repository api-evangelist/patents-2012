---

title: Advanced system and method for automated-context-aware-dialog with human users
abstract: Apparatus for conducting a dialog with a user of at least one computerized enterprise system, the apparatus comprising an ontological topic definer using at least one ontological entity to define user dialog topics, each topic including an item, a block identifying executable computer code operative to resolve the item; and at least one input parameter passed to the block; and a dialog server operative for conducting a dialog with a user of at least one computerized enterprise system about an individual topic from among said user dialog topics.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09495331&OS=09495331&RS=09495331
owner: PERSONETICS TECHNOLOGIES LTD.
number: 09495331
owner_city: Tel Aviv
owner_country: IL
publication_date: 20120919
---
Priority is claimed from U.S. Provisional Patent Application No. 61 536 142 entitled Method and system for automated context aware dialog with human users and filed Sep. 19 2011.

The present invention relates generally to computerized systems and more particularly to computerized systems conducting dialog with a human user.

In computer science and information science an ontology formally represents knowledge as a set of concepts within a domain and the relationships among those concepts . . . . The creation of domain ontologies is . . . fundamental to the definition and use of an enterprise architecture framework . . . . Most ontologies describe individuals instances classes concepts attributes and relations. . . . Common components of ontologies include 

Backward chaining works backward from the goal s . Backward chaining systems usually employ a depth first search strategy e.g. Prolog. 1 

Backward chaining starts with a list of goals and works backwards from the consequent to the antecedent by searching inference rules until it finds one which has a consequent then clause that matches a desired goal.

According to Wikipedia Predictive analytics encompasses a variety of statistical techniques from modeling machine learning data mining and game theory that analyze current and historical facts to make predictions about future events. . . .

Predictive analytics is an area of statistical analysis that deals with extracting information from data and using it to predict future trends and behavior patterns. The core of predictive analytics relies on capturing relationships between explanatory variables and the predicted variables from past occurrences and exploiting it to predict future outcomes . . . . Generally the term predictive analytics is used to mean predictive modeling scoring data with predictive models and forecasting. However people are increasingly using the term to describe . . . descriptive modeling and decision modeling or optimization . . . . Predictive models analyze past performance to assess how likely a customer is to exhibit a specific behavior in the future . . .

Descriptive models quantify relationships in data in a way that is often used to classify customers or prospects into groups . . . .

Decision models describe the relationship between all the elements of a decision the known data including results of predictive models the decision and the forecast results of the decision in order to predict the results of decisions involving many variables . . . . Analytical Customer Relationship Management is a frequent commercial application of predictive analysis . . . . The approaches and techniques used to conduct predictive analytics may broadly be grouped into regression techniques and machine learning techniques regression models such as the linear regression model discrete choice models multivariate regression logistic regression multinomial logistic regression probit regression logit versus probit time series models survival or duration analysis classification and regression trees and multivariate adaptive regression splines and machine learning techniques such as neural networks radial basis functions support vector machines Na ve Bayes k nearest neighbours and geospatial predictive modeling. 

Wikipedia describes that in computer science a closure also lexical closure or function closure is a function together with a referencing environment for the non local variables of that function. A closure allows a function to access variables outside its immediate lexical scope. An upvalue is a free variable that has been bound closed over with a closure. The closure is said to close over its upvalues. The referencing environment binds the nonlocal names to the corresponding variables in scope at the time the closure is created additionally extending their lifetime to at least as long as the lifetime of the closure itself. When the closure is entered at a later time possibly from a different scope the function is executed with its non local variables referring to the ones captured by the closure. 

US Patent Application 20120016678 assigned to Apple is entitled Intelligent Automated Assistant published Jan. 19 2012 and filed Jan. 10 2011. This published application describes an intelligent automated assistant system which engages with the user in an integrated conversational manner using natural language dialog and invokes external services when appropriate to obtain information or perform various actions. The system may be implemented using any of a number of different platforms such as the web email smartphone and the like or any combination thereof. In one embodiment the system is based on sets of interrelated domains and tasks .

The disclosures of all publications and patent documents mentioned in the specification and of the publications and patent documents cited therein directly or indirectly are hereby incorporated by reference. Materiality of such publications and patent documents to patentability is not conceded.

Certain embodiments of the present invention seek to provide an Advanced System and Method For Automated Context Aware Dialog With Human Users.

In accordance with an aspect of the presently disclosed subject matter there is provided apparatus for conducting a dialog with a user of at least one computerized enterprise system the apparatus comprising 

an ontological topic definer including a processor using at least one ontological entity to define user dialog topics each topic including 

a computerized dialog server operative for conducting a dialog with a user of at least one computerized enterprise system about an individual topic from among the user dialog topics.

In accordance with an aspect of the presently disclosed subject matter there is provided a computer program product comprising a non transitory tangible computer readable medium having computer readable program code embodied therein the computer readable program code adapted to be executed to implement a method for conducting a dialog with a user of at least one computerized enterprise system the method comprising 

conducting a dialog with a user of at least one computerized enterprise system about an individual topic from among the user dialog topics.

In accordance with an embodiment of the presently disclosed subject matter there is provided an apparatus wherein the dialog server interacts with an Intent Scoring functionality for scoring various intents on the part of a user approaching a virtual agent the functionality s operation comprising 

predicting priority topics including gathering first data and employing the first data to discern and seek user confirmation of at least one possible intent on the part of the user and

subsequent to receipt of the confirmation gathering second data and employing the second data to provide service to the user to suit the user s confirmed intent.

In accordance with an embodiment of the presently disclosed subject matter there is further provided apparatus wherein the dialog server interacts with a data gathering system comprising 

a data retrieval decision making processor operative when an individual data element is sought to be retrieved to determine whether or not to retrieve the data element by comparing at least one parameter representing need for the data element with at least one parameter retrieved from the data aware knowledge base which represents relative cost of obtaining the data element.

In accordance with an aspect of the presently disclosed subject matter there is provided a method for conducting a dialog with a user of at least one computerized enterprise system the method comprising 

conducting a dialog with a user of at least one computerized enterprise system about an individual topic from among the user dialog topics.

In accordance with an embodiment of the presently disclosed subject matter there is provided a method wherein at least one logic code segment is used for a plurality of different discussion entry points.

In accordance with an embodiment of the presently disclosed subject matter there is further provided a method wherein the conducting comprises conducting at least first and second dialogs with at least first and second users respectively of at least first and second corresponding computerized enterprise systems respectively including using a single logic code segment for at least first and second dialog portions of the first and second dialogs respectively which pertain to first and second products respectively of the first and second corresponding computerized enterprise systems respectively.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein the data lookup comprises looking up data about the user which is stored in the enterprise system.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein the data lookup comprises looking up statistical data about at least one population of users to which the user belongs.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein the first and second enterprise systems comprise first and second banks respectively and wherein the first and second products comprise first and second financial services offered by the first and second banks respectively.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein a directed graph is generated from links between items wherein each link has the following form 

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein the item block and at least one parameter are stored as an ordered list.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein at least one item includes a segment of interactive dialog to be presented to a user.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein at least one item includes a computation to be performed.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein at least one item includes a query to be presented to an external computerized system.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein at least one item includes at least one action to be executed on an external computerized system.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein at least one parameter comprises at least one ItemReference including a reference to at least one other item referenced item to be used as an input for the block.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein each item includes an autoResolve flag indicating whether or not the item is to be resolved.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein each item includes a condition indicating whether or not an item is to be executed based on the item s input parameters.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein at least one parameter comprises a logical expression valueExpression which generates a result value of the parameter by combining an itemReference with at least one of 

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein at least one ItemReference includes an isRequired flag indicating whether the item is an optional input for the block or a required input for the block.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein at least one ItemReference includes a quantification of the referenced item s business value to the item which includes owns the parameter.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein at least one topic includes an indication of a level of user authentication required to execute the topic.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein the block comprises a reference to at least one of a procedure class and rule base thereby to identify executable computer code operative to resolve the item.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein closure based variable scoping is applied to the directed graph.

In accordance with an embodiment of the presently disclosed subject matter there is yet further provided a method wherein backward chaining based logic is applied to the directed graph.

Also provided excluding signals is a computer program comprising computer program code means for performing any of the methods shown and described herein when said program is run on a computer and a computer program product comprising a typically non transitory computer usable or readable medium e.g. non transitory computer usable or readable storage medium typically tangible having a computer readable program code embodied therein said computer readable program code adapted to be executed to implement any or all of the methods shown and described herein. It is appreciated that any or all of the computational steps shown and described herein may be computer implemented. The operations in accordance with the teachings herein may be performed by a computer specially constructed for the desired purposes or by a general purpose computer specially configured for the desired purpose by a computer program stored in a typically non transitory computer readable storage medium.

Any suitable processor display and input means may be used to process display e.g. on a computer screen or other computer output device store and accept information such as information used by or generated by any of the methods and apparatus shown and described herein the above processor display and input means include computer programs in accordance with some or all of the embodiments of the present invention. Any or all functionalities of the invention shown and described herein such as but not limited to steps of flowcharts may be performed by a conventional personal computer processor workstation or other programmable device or computer or electronic computing device or processor either general purpose or specifically constructed used for processing a computer display screen and or printer and or speaker for displaying machine readable memory such as optical disks CDROMs magnetic optical discs or other discs RAMs ROMs EPROMs EEPROMs magnetic or optical or other cards for storing and keyboard or mouse for accepting. The term process as used above is intended to include any type of computation or manipulation or transformation of data represented as physical e.g. electronic phenomena which may occur or reside e.g. within registers and or memories of a computer or processor. The term processor includes a single processing unit or a plurality of distributed or remote such units.

The above devices may communicate via any conventional wired or wireless digital communication means e.g. via a wired or cellular telephone network or a computer network such as the Internet.

The apparatus of the present invention may include according to certain embodiments of the invention machine readable memory containing or otherwise storing a program of instructions which when executed by the machine implements some or all of the apparatus methods features and functionalities of the invention shown and described herein. Alternatively or in addition the apparatus of the present invention may include according to certain embodiments of the invention a program as above which may be written in any conventional programming language and optionally a machine for executing the program such as but not limited to a general purpose computer which may optionally be configured or activated in accordance with the teachings of the present invention. Any of the teachings incorporated herein may wherever suitable operate on signals representative of physical objects or substances.

Any trademark occurring in the text or drawings is the property of its owner and occurs herein merely to explain or illustrate one example of how an embodiment of the invention may be implemented.

Unless specifically stated otherwise as apparent from the following discussions it is appreciated that throughout the specification discussions terms such as processing computing estimating selecting ranking grading calculating determining generating reassessing classifying generating producing stereo matching registering detecting associating superimposing obtaining or the like refer to the action and or processes of a computer or computing system or processor or similar electronic computing device that manipulate and or transform data represented as physical such as electronic quantities within the computing system s registers and or memories into other data similarly represented as physical quantities within the computing system s memories registers or other such information storage transmission or display devices. The term computer should be broadly construed to cover any kind of electronic device with data processing capabilities including by way of non limiting example personal computers servers computing system communication devices processors e.g. digital signal processor DSP microcontrollers field programmable gate array FPGA application specific integrated circuit ASIC etc. and other electronic computing devices.

The present invention may be described merely for clarity in terms of terminology specific to particular programming languages operating systems browsers system versions individual products and the like. It will be appreciated that this terminology is intended to convey general principles of operation clearly and briefly by way of example and is not intended to limit the scope of the invention to any particular programming language operating system browser system version or individual product.

Elements separately listed herein need not be distinct components and alternatively may be the same structure.

Any suitable input device such as but not limited to a sensor may be used to generate or otherwise provide information received by the apparatus and methods shown and described herein. Any suitable output device or display may be used to display or output information generated by the apparatus and methods shown and described herein. Any suitable processor may be employed to compute or generate information as described herein e.g. by providing one or more modules in the processor to perform functionalities described herein. Any suitable computerized data storage e.g. computer memory may be used to store information received by or generated by the systems shown and described herein. Functionalities shown and described herein may be divided between a server computer and a plurality of client computers. These or any other computerized components shown and described herein may communicate between themselves via a suitable computer network.

Computational components described and illustrated herein can be implemented in various forms for example as hardware circuits such as but not limited to custom VLSI circuits or gate arrays or programmable hardware devices such as but not limited to FPGAs or as software program code stored on at least one tangible or intangible computer readable medium and executable by at least one processor or any suitable combination thereof. A specific functional component may be formed by one particular sequence of software code or by a plurality of such which collectively act or behave or act as described herein with reference to the functional component in question. For example the component may be distributed over several code sequences such as but not limited to objects procedures functions routines and programs and may originate from several computer files which typically operate synergistically.

Data can be stored on one or more tangible or intangible computer readable media stored at one or more different locations different network nodes or different storage devices at a single node or location.

It is appreciated that any computer data storage technology including any type of storage or memory and any type of computer components and recording media that retain digital data used for computing for an interval of time and any type of information retention technology may be used to store the various data provided and employed herein. Suitable computer data storage or information retention apparatus may include apparatus which is primary secondary tertiary or off line which is of any type or level or amount or category of volatility differentiation mutability accessibility addressability capacity performance and energy use and which is based on any suitable technologies such as semiconductor magnetic optical paper and others.

Tables herein may according to certain embodiments include only some of the fields and or records shown.

Various embodiments of an example mobile banking system including a smart reasoning subsystem also termed herein a smart reasoner are first described in detail with reference to . It is appreciated that some or all of the characteristics and functional units of each embodiment may be provided and others omitted as desired and that embodiments or some characteristics and functional units thereof may be combined with one another as suitable.

An advanced system for automated context aware dialog with human users is next described with reference to . It is appreciated that the system may facilitate dialog pertaining to the user s interactions with any suitable enterprise or computerized complex data system of which computerized banks are merely one example for simplicity for enterprises other than banks suitable modifications may be employed mutatis mutandis as would readily occur to the ordinarily skilled man of the art. It is appreciated that some or all of the characteristics and functional units of the system may be provided and others omitted as desired. Also some or all of the characteristics and functional units of the system of may be provided in conjunction with or may be used to implement functionalities of the system of .

According to one embodiment an Intent Scoring Method and system are provided for predicting priority events and topics when a user is approaching a virtual agent robot. A diagram of an example intent scoring functionality is provided in . Intent Scoring functionality typically enhances the accuracy of natural language understanding and improves the reasoning process by creating factoring key indicators derived from profiling internal bank data and additional external sources.

In intent scoring typically each solution contains a set of a few or a few dozen or a few hundred Key Indicators KIs that may perform one or more of the following functionalities 

According to one embodiment the system deploys a prediction model typically having intent scoring functionality as described herein which uses key indicators e.g. derived from historical customer transactional activity for example credit card transaction or billing information. The model generates a list of topics or events which the customer is likely to raise. The system generates priority topics for prompting the customer before he inputs his request and a combined score which includes the input of the customer for improving the accuracy of a text retrieval system.

According to one embodiment data aware agents are provided having a data retrieval functionality which connects a virtual robot agent to the enterprise systems.

Virtual robots typically require external data from the enterprise systems to answer questions and to generate a dialog with the customer. Virtual agents are conventionally preloaded with vast amounts of data to be able to perform. According to one embodiment the system includes data aware agent s which imitate human agent activity by accessing the systems only when needed e.g. by using a knowledge representation of data and reasoning process which computes the necessity or utility and cost for retrieving certain data elements. Typically a mechanism is provided which is able to playback human generated queries which are executed in real time to capture additional information which may be useful or necessary to the continuation of the process.

According to one embodiment a Smart Reasoning system is provided which typically uses a domain specific artificial intelligence computerized process which improves the limitation of current goal driven expert systems.

Certain traditional goal driven systems use many rules cannot easily adapt to new situations do not learn by experience and are not good at representing spatial knowledge. The system shown and described herein typically implements a conceptual learning capability which organizes knowledge in a generalized and abstract form while at the same time making the system more useful and robust when coping with environmental changes. For example actions acquired for one subject may be available for similar but non identical subjects. The system typically prioritizes asserted and or inferred relations and or deploys reinforced learning when selections set s are empty.

According to one embodiment 1 or 2 or 3 of the Intent Scoring data aware agents and Smart Reasoning subsystems are provided having a synergistic relationship therebetween.

According to one embodiment an automated chat functionality is provided which is operative to understand the user intent and to decide what should be the best response dialog to the user.

Conventional automated chat systems use Natural Language Processing NLP to classify the user input and a script or decision tree to define different paths which may decide the next dialog in the process. This approach is often limited in terms of flexibility and does not allow incorporation of artificial intelligence into the process.

Features of the above described invention which are described in the context of separate embodiments may also be provided in combination in a single embodiment. Conversely features of the invention including method steps which are described for brevity in the context of a single embodiment or in a certain order may be provided separately or in any suitable sub combination or in a different order. Any or all of computerized sensors output devices or displays processors data storage and networks may be used as appropriate to implement any of the methods and apparatus shown and described herein.

According to certain embodiments computerized experts are provided e.g. experts on some or all of the following bill pay product credit product transfer product fees lost stolen transaction dispute sign in card usage. Example screenshots for a transaction dispute expert are provided in . An example screenshot for a marketing product expert is provided in

According to certain embodiments there is an advance from a generic technology to a domain specific solution by formalizing an ontology of customer service in the financial industry and by providing banking specific high level building blocks. The system may employ data analysis of bank records and real time profiles to improve the system understanding and reasoning capabilities and to achieve a meaningful and personalized customer experience.

The training algorithm may include some or all of the following functionalities performed in a suitable order e.g. as follows 

NLP functionality e.g. as shown in the screenshot of or the implementation of may be characterized by some or all of 

Goals Classification of input sentence to a representing topic rank the topics according to their likelihood reason class for an input sentence. Find a list of supportive hints Entities.

Referring again to the statistical consolidation of instance based learning and a probabilistic generative model also termed herein classifiers once scores from both classifiers are available a consolidation process may be followed to yield one ranked list of reasons. Consolidation may include some or all of the following operations suitably ordered e.g. as follows 

An example knowledge representation including inter alia a banking domain ontology a banking service ontology a dynamic dialog ontology and a banking terminology subsystem is diagrammed in . Example screenshots generated by a banking domain ontology are shown in . Example screenshots showing a user view of a banking domain ontology are shown in . An example diagram of a banking servicing ontology is shown in . Example diagrams and screenshots showing a dynamic dialog ontology are shown in 

Banking domain ontology may be based on Semantic Web standards e.g. RDF OWL Triple store quads Jena and Sparql. Generalization may use OWL reasoners and classifiers. Assertions and queries may use high level classes.

Banking servicing ontology typically comprises formal representation of banking service knowledge as a set of concepts within a domain and the relationships between those concepts. Inferred and asserted relations may be provided e.g. 

Dynamic reasoning is a functionality typically including data structure optimized for dynamic data collection and reasoning which supports rapid queries and ad hoc sub structures. Typically dynamic reasoning is based on semantic quads where 

The Smart Reasoner is typically operative to drive dialog to a satisfactory resolution of servicing request in a minimum number of steps. For example a customer complains s he could not complete a purchase. There are many different root causes Card has expired An issue with the customer address Customer did not swipe his card correctly . Each root cause may require different data elements or questions Query rejected authorizations for a card date Ask customer if he was able to complete other purchases with card .

Smart Reasoner may optionally use Required Information to satisfy information requirements present in some embodiments to support the selected solution s next steps. Typically the Reasoner analyzes the different variables which are included in all selected next steps and tries to retrieve them using a goal driven approach. Example Customer complains about unrecognized TX. Solution set includes a process which is dependent on the amount of the complaint. Reasoner may try to identify the amount of the TX and if it does not have facts identifying the TX it may define a new goal identify the TX. It may then attempt to first identify the TX.

The Smart Reasoner is typically operative to select best next step. Typically Reasoner selects best next step based on one or more of a score combining a generalized form of similar cases cost of obtaining information and additional considerations. For example The system evaluates past history for a subject and discovers that in all cases which had certain similar features the most successful next step is to identify the TX early in the dialog.

Smart Reasoner is typically operative for reinforced learning. An advisor may be prompted to select a recommended next step. A transcript of the dialog all the collected variables and applicable general knowledge is presented. If the dialog results in an ability to manually identify a recommended root cause control is returned to the Reasoner.

Smart Reasoner is typically operative for reinforced learning. Each recommendation represents a connection between a set of variables and relevant next step. A generalization service typically aggregates the relations to detect strong and weak relationships probability based . This allows the system to constantly improve its accuracy and also generates actions to new instances based on selections of relevant historical relations.

The Data Access Layer of may have a Banking Service Data model which defines the data elements required for servicing customer requests e.g. Purchase MCC or Authorization reject code . There may also be a Mapping Layer which for each element and access type defines the connector details where that data is found action is taken e.g. Find authorizations for card or Cancel a card .

CSR Desktop Connectors may be provided to the system e.g. a human less CSR Desktop may be assigned to the system which conducts dialog with customer. As dialog evolves the system runs scripts on the human less CSR Desktop to access CSR screens. Screen scraping technology is used to convert the screen into data elements.

Screen scraping technology may include some or all of the following script reorder which automates data extraction without any programming scraping compatibility with Win Apps web pages terminal emulators extraction tools e.g. rich text pattern matching capabilities and or OCR tailored for graphics screens and embedded toolset by Automation Anywhere .

As shown in the example system architecture diagram of the system may include clients e.g. mobile iPhone Android web a network typically behind bank firewall authentication and load balancer PServer nodes typically scalable multi tiers on same node with sticky sessions and a central database typically with high availability and clustered.

The system may be implemented as an app launched by mobile banking supporting iOS iPHONE iPOD iPAD Android etc. Native iOS app leverage Smartphone hardware may be provided using webkit to display HTML content. A first time launch may prompt to install app. Login may be done by mobile banking app.

Mobile banking deployment may be as shown in . In web banking use cases the system may comprise a browser window launched by web banking may also use iFrame . FLASH HTML 5 may be used to access microphone. Typically no installation is required and login is done by web banking

Web banking deployment may be as shown in . Bank policy function may provide an application to force an action in specific situations or to limit what the Reasoner is allowed to offer and a method having business rules using financial terms and logic which has access to customer data and intent.

When Digital Personal Banker cannot address the customer s request the case may be transferred to a live agent e.g. as per some or all of the following considerations 

An offline process for capturing user input useful in conjunction with the mobile banking system or other dialog conducting systems shown and described herein is now described with reference to 

The system of the present invention may operate an offline process supported by tools which capture user input and incorporate the captured input into the system e.g. some or all of the following 

To manage and edit the ontology knowledge an existing ontology editor may be used which may be customized to support specific requirements. Add ins may be incorporated which express process knowledge including priorities data requirements and other elements some or all of which may be included in a customer service ontology.

Knowledge import Banks maintain and publish detailed documents regarding the fees and the products that they are offering. The system may employ an easy import process which allows collecting data from documents and sheets which are controlled by the bank into an ontology structure. This process may conserve much implementation time and may use and or reuse general available knowledge sources which are already maintained and updated by the banks e.g. Excel based documents.

Most financial institutions implement a very similar service process to support their customers. Still there are differences which may need to be implemented by the bank. To support this a user interface may be provided to allow a bank to add their own logic and rules into the system. The logic may be a simple rule for escalation or a complete new step based on a unique business requirement e.g. as shown in which is an example in which the bank wants to offer an account upgrade for wealthy customers.

Human advisor it is desired to be able to transfer the process to a human agent. Such a requirement may be derived from a failure of the system to retrieve any next step or from a business policy which escalates a discussion or dialog for example for cases related to a large amount or which require an expert agent review. The transfer process may collect all relevant information e.g. some or all of the history of the dialog collected variables and knowledge to a view. The agent may use the view screen and may be able to alter the progress of the process or to take over completely e.g. as shown in which is an example of an advisor screen which supports both view and manual intervention by the agent.

A Data Access Layer may provide an interface between a server serving a system according to an embodiment of the present invention and external data sources such as but not limited to existing banking core systems banking web services and databases. The module may use conventional screen scraping techniques to access banking information through a graphical user interface used by human service agents. This capability may give the system access to the virtual agent desktop which exists today in most banks and contains relevant information which may be required for the agent and the system of the present invention to execute decisions.

To support the screen scraping which may comprise data mapping a GUI interface may be provided which facilitates mapping a set of screens used by call center agents and graphically describes an automation task to retrieve data.

A second embodiment of a mobile banking system is now described with reference to . Intent Scoring according to this embodiment is operative for achieving accurate level of understanding in the specific context of customer requests overcoming limitations of Natural Language Understanding using predictive analytics.

Conventional predictive analytics in data rich environments such as banks has reached a level where it is possible to accurately predict the probability of each customer activity. Such probability scores are already used in critical business decisions such as credit scoring customer will will not pay their balance and fraud scoring the customer is is not the person making the request . It is possible to enhance the accuracy of the understanding in data rich environments by factoring in key indicators described herein which are derived from profiling data. The key indicators are derived from transactional data house holding data click stream peer groups bank wide events and more.

Smart Reasoner according to certain embodiments operates a hybrid reasoning algorithm which adds continuance learning capability to the classic goal driven approach. Conventional goal driven systems often cannot easily adapt to new unusual situations do not learn by experience and are not good at representing spatial knowledge. Typically the Smart Reasoner has conceptual learning capability operative to review knowledge in a generalized and abstract form e.g. actions acquired for one subject are available for similar but non identical subjects while at the same time making the system more useful and robust when coping with environmental changes. Typically the Smart Reasoner utilizes relevant context information represented in an ontology to appropriately tailor its responses to each specific situation. Smart Reasoner may take into account recent actions and events current goals and priorities.

An intent scoring module is typically operative to accurately classify the customer request to the different classifiers subject action type source relations together representing the user intent. An ontology is typically operative to collect and represent knowledge about the domain e.g. products and rates problem solving issues and potential resolutions track the progress of the conversation .

The Smart Reasoner may use a hybrid of goal driven reasoning continuance learning capability and context based information to drive the next set of sequence of actions.

The customer service banking ontology module is typically used to capture knowledge about customer service in retail banking and may comprise some or all of knowledge about financial products knowledge about customer service issues and potential solutions short term memory of the current conversation and lexicon ontology. The ontology is typically used as the foundation to perform different types of reasoning. Typically the ontology describes some or all of the concepts in the domain the relationships between them and constraints. Ontology languages e.g. OWL 2 from the World Wide Web Consortium W3C may be employed. OWL 2 makes it possible to describe concepts using such operators as intersection union negation and facilitates derivation of complex concepts from definitions of simpler concepts. Furthermore the formal ontology constraints allows the use of a Reasoner which may check whether or not all of the statements and definitions in the ontology are mutually consistent and may also recognize which concepts fit under which definitions. This is particularly useful when dealing with cases where classes may have more than one parent.

Domain ontology may include knowledge about financial products e.g. definitions business terms fees product features etc.

Customer servicing ontology typically stores knowledge about typical customer service issues and potential solutions main categories input sources information required according to certain embodiments suggested explanations bank policy.

Short term memory ontology typically captures information about a party which is currently engaged with the system. When the session starts the ontology is loaded with knowledge from the historical database including customer profile activity and service history so typically the ontology contains some LTM knowledge. During the conversation more facts and hints are added supported by a probability score.

Lexicon ontology typically is a combination of domain dependent lexicon e.g. obtained through the use of a learning process and generic lexical resources such as but not limited to WordNet.

Different portions of the ontology may be used for different tasks and may be merged into a full ontology e.g. for the use of the Smart Reasoner. In order to coordinate between the different ontology portions cross ontology classes and relations may be employed for connecting the different portions of the ontology and to facilitate performing advanced reasoning. Example During a conversation or dialog hints facts may be collected as instances of the short term memory each hint is assigned into classes which are included in the service ontology. If reasonhasFact short term memory and also type merchant service then the Reasoner may filter available transactions which contain relevant merchant instances and confirm these transactions with the user.

Ontology maintenance The system typically employs support for information and knowledge which is bank specific while creating a methodology and tools for separation between the system s knowledge and that of its banking clients. Typically a generic ontology is maintained and individual banks update to specific needs e.g. in the following areas specific bank related constraints e.g. This bank does not support wires from the ATM new subclasses e.g. premium ACH Product and bank instances fees and waivers for transferring funds.

Some of the bank specific knowledge may be generated automatically by mining text resources and representing the information held in departmental databases in terms of the ontology. For example US banks are required to publish a standard fee schedule which contains information on all fee types and waiver rules.

In the example of the screen shot of domestic wire is defined as a subclass part of the transfers hierarchy. Also defined are alternatives and constraints for currency destinations and available channel types.

An example NLP module is now described. GATE Version 5.2 may be employed as a framework for language processing. Within Gates an embedded GATE ANNIE system may be utilized for basic information extraction and GATE plug ins may be leveraged as a framework for integrating multiple advanced language processing algorithms such as but not limited to Stanford Parser and Open NLP. Using GATE an NLP pipeline may be created incorporating key functions such as but not limited to some or all of tokenization root gazetteer name and entity extraction part of speech identification and sentence splitters.

The existing system may be extended with bank specific entities such as but not limited to financial products merchants ATM locations. A probabilistic parser may be used for chunking e.g. nouns and verbs and or to identify grammatical relationships and or to provide a representation of grammatical relations between words and chunks in a sentence.

Suitable conventional means such as WEKA may be employed to develop a classification module which attempts to classify the customer request by different dimensions e.g. some or all of 

The profile analytics of may be operative to profile multiple dimensions at varying time spans and to compute key indicators. In certain cases profiling is performed at multi dimensional levels e.g. device and time set or customer and geolocation profiles. Profiling is typically performed at three different time spans real time recent history and real history. Typically profiling occurs at some or all of the following key dimensions 

Next key indicators may be computed from above profiles. Further enhancement of the key indicators may be achieved by computerized analysis of recent user activity e.g. web clicks and or screen content and providing insight into the customer s current frame of mind e.g. what bank information the customer is looking at. Key indicators may be created in some or all of the following groups 

Still referring to typically intent analytics enhances the accuracy of natural language understanding by factoring in specially generated key indicators derived from profiling bank data. The key indicators may then be used to adjust the NLP score and then typically subsequently to rank results and convert hints into facts. For example Customer calls the system regarding a certain issue I have a problem using my bank card . . . . The system finds a declined transaction from the last two hours and hence adds more weight to the decline issues dimension.

Typically one or both of the following methods are employed for combining the raw NLP features with key indicators in order to produce the most accurate understanding 

Example Customer language refers to an unexpected fee. Using profiling customer history reveals two fees in the customer statement one of the charges is a first time for this customer whereas the other has been occurring regularly.

Model self trailing Typically the system records every classification attempt conversion of hints to facts including successful and unsuccessful results. Each attempt is maintained including all hints information and the outcome. The system typically uses the information to constantly adjust its selection and improve its understanding capability.

The Smart Reasoner is typically operative to evaluate all facts collected and using combined ontology knowledge to derive a decision regarding next steps. The Smart Reasoner typically uses a hybrid of goal driven reasoning continuance learning capability and context based information to drive the next set of sequence of actions. In each step of dialog the Reasoner may evaluate its short term memory which may include some or all of facts hints and customer profile all of which typically include a probability score.

Suitable conventional means e.g. Drools may be used as a foundation and its capabilities may be enhanced with a set of functions to allow execution of more sophisticated strategies. Drools provides not only rules management but other capabilities like a strong workflow layer extendibility and integration with Java Objects.

Example If the short term memory contains a confirmed subject then the Reasoner may retrieve a set of available actions which are connected using the relevantAction property. It is assumed that the specific instance actually has a relation which connects potential actions. To execute a functionality to invoke SPARQL queries may be employed.

b. Decision using generalization If the Smart Reasoner does not find a direct relation to actions then the Smart Reasoner may use its capability to ask more generalized questions to retrieve potential solutions. Example The Reasoner attempts to retrieve a set of available actions which are connected using the relevantAction property but gets nothing. The Reasoner then looks at subject hierarchy which classes contain this subject and tries to retrieve available actions. This means that the knowledge may be expressed in general terms and would be relevant to every individual which is included. For example All issues which are related part of class statement may require identification of the trigger.

Decision using unsupervised learning In cases where no actions are identified either using a direct relation or generalization the Reasoner may attempt to retrieve the set of actions by examining confidence of relations which are captured using past experience. Each relation represents a connection between a set of variables and relevant action. Using the generalization service the relations may be aggregated to represent strong and weak relationships e.g. probability based .

Examining more generalized historical relations typically highlights the correct associations those whose noise has faded beyond some detection threshold.

This allows the system to constantly improve its accuracy but also generate actions to new instances based on selections of relevant historical relations assuming it is possible to find enough relations when applying generalization.

Manual escalation The Reasoner typically has a failsafe mechanism which escalates to a human advisor as per predefined criteria of need for human intervention.

When none of the automated functions produce any meaningful actions the system may perform an escalation e.g. to the human advisor.

Any suitable dialog with client to implement some or all of the embodiments shown and described herein may be provided. An example dialog manager design is now described. Any or all of the characteristics shown and described herein may be provided.

Typically the dialog manager comprises a server side module that manages the communications with the client module. Based on high level dialog instructions the dialog manager may create a detailed set of messages to send to the client module. In addition to handling generation of messages the same or another module may be operative for parsing the message received from the client module. The dialog manager may be invoked to parse messages arriving from client module or to generate messages to client module.

The module may generate English or other natural language sentences forming an instruction question to the end user and may format them into messages in a format expected by the client module. The messages may be sent returned back to the calling module.

Typically a dialog ID may be used to specify what idea to convey . The sentences may be generated using dialog templates. Each dialog template typically corresponds to a dialog code or ID. The dialog templates are typically defined in a configuration table which defines what to tell the end user how to format and what response is expected. Example Asking the user to select which of his several bank cards is involved in her or his complaint.

For some dialog codes the module employs parameters that further enhance the message. These parameters may be passed in log records of type DIALOG. In addition to explicit parameters the module may make use of information in the current state e.g. the user s name and or information about the party. Input may include some or all of the following 

An action code specifying what is the next step e.g. Send response to client module or Run NLP or Run logic analytics log record with the chat screen messages sent to the client module e.g. text on behalf of end user or text said by system . Dialog types may include some or all of 

Example implementations of various of the above are now described in detail. Standard options may be available for some or all dialog types e.g. as described below. If the module supports certain dialog types each dialog ID is typically defined to use one of the dialog types provided.

On type it client module may display a keyboard input screen when typing is over the client module may call the server.

Once text response arrives at server the dialog manager may send back instruction to insert text typed into conversation screen as user said and return back to server with echo yes. Once echo yes response arrives at server the dialog manager may send text to NLP for next step.

Configurable elements may be provided such as but not limited to Allow voice input flag No Jump directly to text input screen Main text.

If configured to use generic selection screen Change label to configured current state Apply progress message Scroll all the way up Insert main text into conversation screen typically without the options as system said Invoke generic selection screen with main text and options and prompt the user to select one and press submit optionally None of the above Apply Help message.

Once response arrives at server the dialog manager may send back instruction to client module to insert into conversation screen Username option selected message as user said and return back to server with echo yes. Once echo yes arrives at server the dialog manager may insert response record to log and instruct the PSERVER to call Drools.

If configured to use conversation screen Change label to configured current state Apply progress message Scroll all the way up Insert main text and options into conversation screen as system said Display options inside conversation screen screen and prompt the user to select one and press submit optionally None of the above Apply Help message .

Once response arrives at server the dialog manager may send back instruction to client module to remove last system said bubble Insert main text into conversation screen without the options as system said Insert into conversation screen Username option selected message as user said and return back to server with echo yes. Once echo yes arrives at server the dialog manager may insert response record to log and instruct the PSERVER to call Drools. It is appreciated that all references herein to Drools may alternatively be replaced by any other suitable business rule management system.

Instructions to client module may be same as SEL ONE P except that options are buttons placed horizontally with mandatory options YES NO and optional OTHER.

After sentence the user may be prompted to take a picture of receipt or ATM. slip or to select an already taken picture.

c. Progress message A progress screen that shows before the real screen it presented. It may include some or all of a conversation text an in progress text not logged artificial wait time a completion text not logged 

d. Help message A message explaining to user what a screen is about and what s he is expected to do. It may be either 1 A screen pop up or 2 a full screen with a next button. If a pop up screen than may disappear by itself after a few seconds configurable may have an extra info button to replace it with a larger pop up with a longer text. If a full screen with next button then next may have automatic countdown configuring . If a Help message is provided then input dialog may have a small i button on the actual screen to display Help message again.

Dialog Configuration Table Typically a dialog configuration table is provided which defines the many typically dozens hundreds or thousands of possible dialogs the module may generate. Each record in the table may store some or all of the following fields 

A dialog variations configuration table may be provided which provides variations for saying the same sentences. Example Singular vs. plural or male vs. female. Each record in the table may store some or all of the following fields 

Multiple variations selection logic may be provided. For example if there are multiple variations matching the criteria the module may pick a variation with highest priority. If multiple variations matching criteria have the same priority then a variation may be selected randomly. P2 If multiple variations then toggle though variation within a conversation. For example if it is desired to ask the user to provide more details as the user may say utterances slightly differently each time.

Template sentences may include variables which may be replaced with values. For example the following variables may be replaced if found inside the template 

Parsing a client module message The module may receive an XML message that arrived from the client module and parse the message.

The first time a client response message is received the dialog manager may generate an immediate response message back to the client module echoing back into the display log the end user input and telling the client module to make an immediate echo back call with the same message.

The second time a client response message is received the client response message may have an echoed back YES flag. The dialog manager may create log records of type dialog specifying the end user response for the NLP and or logic analytics module.

Echoing back what the user said may be based on combination of dialog type and class name and is typically not specific to the dialog code that was asked. Alternatively however echoing back may be sensitive to specific dialog code which was asked.

A dialog echo configuration table may specify what to say. An example dialog type echo configuration table is provided in the table of

Coding the end user responses may be based on the original dialog log records that triggered this dialog. Same type records may be created with the response values.

The dialog manager may optionally be involved to any suitable degree in other client module commands such as but not limited to 

An example dialog manager work flow is shown in and . The flow may include some or all of the following operations shown in and suitably ordered e.g. as shown.

The extent of movement back and forth to from conversation screen may be controllable. For example shift back to conversation screen after input may be a server decision e.g. may be a parameter of the input dialog command. When entering a new screen user may get to see the text inserted into the conversation screen prior to opening new screen.

Help message A flag may be provided to make Help message a stand by whereby it is not presented until user explicitly presses an info button in the input screen.

According to certain embodiments context knowledge is collected during dialog in addition to enterprise data which may already be available thereby to enhance reasoning functionality.

According to certain embodiments each root cause may be regarded as a Step rather than a solution or resolution.

According to certain embodiments context is managed at the reason level and each item has a name which is typically assigned by the developer. If a name is repeated in the same context reason the system typically assigns the value from context.

According to certain embodiments all dialogs are concentrated in a single location. For example an ADD DIALOG window may be added to an R C Block screen so as to create a new dialog manager entry automatically. The user may select TEMPLATE and based on template select values of parameters including text. Should the user confirm say that a card is lost system typically knows later that this fact is related to card ABC or card GHJ because the dialog answer is typically converted to a fact with context e.g. in the illustrated embodiment a specific card is lost . For example in each dialog an expression may be defined which is a set based on the answer. e.g. start with yes no dialogs and write an expression confirmedcard.Lost which means that if the dialog is confirmed then the confirmed card a specific instance. property lost true. Next time a dialog is used check the expression and if it is the same confirmed card bring back the value from memory and do not execute the dialog. confirmedcard.Lost may then be used as a precondition to another item instead of the dialog name. This may for example be implemented by adding more properties to existing objects such as card transaction case.

According to certain embodiments the number of items root causes is reduced by allowing greater reusability of steps and or reasons e.g. use of the same steps multiple times e. g. calling various steps like a subroutine and then going back and continuing the process. According to certain embodiments a step may be called even if it is not previously connected to the reason calling it. For example some steps may be designated as global and may be called from any reason. To continue when the call ends the system may run from start and because the item is marked as done may go back to the same point. A reason may be called so as to reuse a combination of multiple steps with all their relationships and connections e.g. shipment of card which may include more than one step .

According to certain embodiments internal reasons are defined that are never identified by the NLP system and are only used as groups of steps. Examples The combination of card trigger merchant may be deemed a step confirmed address and or cancelation of card may also respectively be deemed steps.

According to certain embodiments a new item which selects to execute a new step or reason first executes the step or reason. Once the execution is complete the item is marked as done and control is naturally returned to the following item. The step reason may be called by name or by using a context based item. For example global step s may be defined which perform a confirmed address e.g. call a goSub step confirm address then call a party.confirmAddress step which implements the appropriate operations.

According to certain embodiments a Global step 0 is provided. In each reason or across all reasons a step 0 may be defined which is evaluated every time and is never marked as done. This allows triggers to be added to invoke logic which overrules the regular flow. Examples 

a. If at any point of the reason the system suspects fraud the conversation is sent immediately to a fraud specialist.

According to certain embodiments support is provided for out of flow occurrences e.g. the ability to call different reasons in different places I also need to change my address . Typically support is provided for a context based question e.g. The user is presented with a dialog Do you want to cancel the card and responds with a question What s my balance . Switching from a topic and returning may be enabled e.g. by adding a GoSub for reason.

According to certain embodiments dialogs are aligned with instances and properties e.g. confirmedcard.Lost and common context based questions are connected to a suitable class and or the property.

According to certain embodiments when adding a new root cause to a reason all the root causes that are called by that root cause are also added recursively for each root cause.

According to certain embodiments the same root cause may be added twice in the same reason e.g. when the root cause is called from two different branches. Typically a local ID is assigned to each root cause within the reason.

According to certain embodiments semantic representation of logic is used to reduce the number and complexity of rules. Preferably rules use only high level terminology and do not use values or set values. Instead all values to be used by rules are saved in ontology structure or instances.

According to certain embodiments an exist function is provided which is operative to scan a log and generate true or false based on the existence of the object.

According to certain embodiments for at least some reasons a trigger is defined to start and solve the problem. Example For unrecognized purchase the trigger may comprise a purchase transaction.

Some or all of the following phases or operations may be performed in a suitable order e.g. as per below 

An advanced system for automated context aware dialog with human users is next described with reference to . is a simplified functional block diagram of an advanced system for automated context aware dialog with human users constructed and operative in accordance with certain embodiments of the present invention. The system of may include some or all of the following modules which may for example be implemented in software 

The system of typically uses a domain specific artificial intelligence computerized process to overcome limitations of conventional goal driven expert systems which typically use many rules cannot easily adapt to new situations do not learn by experience and are not good at representing spatial knowledge. The system of is typically operative to implement a conceptual learning capability which organizes knowledge such that actions acquired for one subject are available for similar but non identical subjects. The system of is typically robust when coping with environmental changes. The system typically prioritizes asserted and inferred relations and deploys reinforced learning when selections set s are empty.

The system of typically is advantageous vis vis current dialog systems in one or more of the following aspects 

In the AIML bubble represents systems that use the Artificial Intelligence Markup Language AIML dialect for creating natural language software. AIML agents produce a fairly natural dialog experience but suffer from several drawbacks. First the use of textual pattern matching rules and blind replication of user inputs limits the problem solving capabilities of such systems. Second the forward chaining process used to resolve pattern matching rules is prone to cyclic dependency issues and unexpected dialog flows. Finally limited by simple pattern matching capabilities these systems require an implementer to define a huge number of rules and reduction to cover new discussion domains.

The State Machines bubble represents systems that use a finite state machine based modeling such as UML state charts . These provide a solution for predictable problems with narrow scope e.g. technical help wizards and enterprise workflows . However the finite state machine model fails when dealing with multidimensional issues requiring implementer to assign states to each combination of possible dimension values. While concepts such as nested states and event help to alleviate this problem it is often found that the number of states tends to grow exponentially as problem complexity increases. In addition the dialog flow defined with such system tends to be rigid and pre defined and does not exhibit the flexibility required by natural conversation.

The Expert Systems bubble represents expert systems which focus on emulating the decision making ability of human experts. Such systems exhibit robust problem solving capabilities but lack the ability to mimic natural human dialog.

It is appreciated that conventional deduction systems that rely on forward chaining algorithms that process when than rule bases are difficult to maintain and exhibit problems of cyclic dependency and unexpected dialog flows. In contrast conventional goal driven systems that use backward chaining algorithms such as Prolog provide a closer approximation of human conversational thinking but often rely on formal logic reductions for processing and fail to produce predictable dialog as the number of rules expands.

Natural Modeling of Service Dialogs The system of is typically operative for maintaining a one to one relationship between discussion topics as they are perceived by humans and knowledge expressed using the Topic Definition Ontology. Discourse topics may be deemed a key component of the knowledge definition framework. Dialog implementers may interrogate domain experts about topics encountered in the domain experts daily discourse and directly model these topics using the Topic Definition Ontology. Built in support for sub topic invocation at runtime may be provided to help implementers encapsulate and reuse topics and to naturally expand system capabilities as the implementation evolves.

Efficient Context Awareness The system of is typically operative to use the same topic definitions to conduct dialogs in different settings. It is appreciated that human dialog is very context dependent. Conversation about a given topic may take on different forms when initiated in different situations. In the case of professional service dialog the customer may initiate a focused complaint about an exact business context or a general statement that needs to be investigated by the service provider. Typically the system of combines goal driven reasoning with variable closures to accommodate for dependency on context. In focused settings contextual closures provide concrete facts that the reasoning process may utilize when solving a topic. In more general settings the reasoning process may not find readily available facts and may have to obtain information from the user through interactive dialog or using external information systems.

Item closures are important inter alia when context is derived from natural language input. In such cases entity extraction techniques may be used to obtain factual information from analyzed text. Extracted information is often noisy and unpredictable due to the open quality of natural language. Contextual closures provide a strong and flexible mechanism to communicate extracted entities to the reasoning process.

Typically implementers may define topics that may be used in many settings and allow context closures to provide the factual context for topic resolution thereby to improve the cost effectiveness of implementation efforts.

In order to support multiple parallel topics in the same conversation a system level discussion thread topic may be employed and all implementation topics may be run under the topic context of a discussion thread. The first thread is created when the conversation begins subsequent threads are created when the customer digresses to a new context without completing an old one. System level flow control topics handle the user interface and data pluming involved in switching between these threads.

Data structures and processes some or all of which may be employed in the system of and possible interrelationships therebetween are now described in detail.

Topic Definition Ontology The Smart Reasoner uses service ontology entities to define user dialog topics. is a simplified block diagram illustration of an example data structure for a service ontology e.g. Topic Definition Ontology. Referring now to 

These links collectively create a directed graph that enables the Smart Reasoner process to employ backward chaining based logic and closure based variable scoping.

The Topic Runtime Ontology of is typically employed by the Smart Reasoner of as a central data structure to resolve topics defined using the Topic Definition Ontology. is a simplified block diagram illustration of an example data structure for a Topic Runtime Ontology.

Three Value Logic In order to provide extra robustness to defined topics principles of operation of many value logic systems such as Kleene K3 and Priest logic P3 may be employed. Such logic systems add a third truth value undefined or indeterminate on top of the standard true false. Extended truth tables for standard logic operators e.g. Kleene and Priest logic truth tables by way of example are presented in .

Throughout the reasoning process of concrete facts that emerge as topic items get resolved. Each unresolved item typically receives the indeterminate by default. At this point all logic expressions in the definition ontology may be evaluated using the truth tables presented in . This provides much needed tolerance for missing data which is prevalent in real work enterprise environments.

The runtime topic context tree created by the reasoning process is typically employed for predicting the possibility and likelihood of context switches e.g. in mid dialog fork prediction.

The prediction process typically uses the context tree generated by the method of to identify all the topics and all the entities that occurred in the discussion up to the current discussion state and their relevance for the current context greater distance in the tree less relevance . For each discussed topic and entity meta data is used to find relevant fork topics and assign a probability score to each fork. The system computes the prediction value for each fork topic as max context relevance X fork probability .

An example flow for the reasoning process of is now described in detail with reference to a service ontology example comprising two topics HelloStart and HelloLogic as per . Running the reasoning process on this example service ontology yields a topic context tree structure as described in .

Methods for mid dialog fork prediction according to certain embodiments are now described in detail with reference to . Generally human dialog is a multi step process where each step creates a new context for understanding. Throughout a conversation a customer or user often desires to steer discussion to one of several possible forks such as but not limited to some or all of 

A runtime topic context tree created by the reasoning process shown and described herein is a powerful tool for predicting the possibility and likelihood of such context switches.

A fork prediction process may include some or all of the steps illustrated in suitably ordered e.g. as shown. Fork prediction typically starts from the currently discussed topic at the bottom of the topic context tree step i and climbs to the root of the tree while visiting each nested topic on its way steps vi vii . The process assigns the bottom topic a maximum context score of 1 giving each topic a smaller context score as the process moves up the tree.

For each visited topic the process may employ a Topic to Topic table e.g. as illustrated in to map the visited topic to a collection of related topics assigning each one a relevance score step ii . The process adds the related topics to its results computing the relevance score for each topic as the multiplication of their relevance score and the current context score step iii .

For each reasoning item in the visited topic the process checks if the item refers to a business entity such as a bank account or a financial transaction. If a business entity is identified the process uses the Entity to Topic table e.g. that of to map the entity to a collection of relevant topics step iv . In one embodiment expressions are used to check the relevance of the entity to the topics e.g. is the entity s type equal to GoldAccount . In another embodiment named classes can be used for relevance checks e.g. is the entity and Online Transaction. In this embodiment the use of the named class is decoupled from the implementation of the class that may use compiled code expressions rule based deduction table based lookups and more.

The process typically adds the identified related topics to its results computing the relevance score for each topic as the multiplication of their relevance score and the current context score step v . The process typically terminates when it reaches the top of the topic context tree and returns its results. In a more involved embodiment the process may not limit its search to the currently discussed topic branch from the current topic to the root but may instead visit the whole tree representing all previously discussed topics using a suitable tree searching process such as but not limited to DFS or BFS.

The system of the present invention may for example reside wholly or in part within and or conduct dialog with a mobile communication device such as but not limited to any of the following mobile telephone smart phone playstation iPad TV remote desktop computer game console tablet mobile e.g. laptop or other computer terminal embedded remote unit.

The system may be implemented as a web based system including computers routers and telecommunications equipment.

The methods shown and described herein are particularly useful in processing or analyzing or searching enterprise or generally available bodies of knowledge including hundreds thousands tens of thousands or hundreds of thousands of electronic records. This is because practically speaking such large bodies of knowledge can only be processed analyzed sorted or searched using computerized technology.

It is appreciated that terminology such as mandatory required need and must refer to implementation choices made within the context of a particular implementation or application described herewithin for clarity and are not intended to be limiting since in an alternative implantation the same elements might be defined as not mandatory and not required or might even be eliminated altogether.

It is appreciated that software components of the present invention including programs and data may if desired be implemented in ROM read only memory form including CD ROMs EPROMs and EEPROMs or may be stored in any other suitable typically non transitory computer readable medium such as but not limited to disks of various kinds cards of various kinds and RAMs. Components described herein as software may alternatively be implemented wholly or partly in hardware if desired using conventional techniques. Conversely components described herein as hardware may alternatively be implemented wholly or partly in software if desired using conventional techniques.

Included in the scope of the present invention inter alia are electromagnetic signals carrying computer readable instructions for performing any or all of the steps of any of the methods shown and described herein in any suitable order machine readable instructions for performing any or all of the steps of any of the methods shown and described herein in any suitable order program storage devices readable by machine tangibly embodying a program of instructions executable by the machine to perform any or all of the steps of any of the methods shown and described herein in any suitable order a computer program product comprising a computer useable medium having computer readable program code such as executable code having embodied therein and or including computer readable program code for performing any or all of the steps of any of the methods shown and described herein in any suitable order any technical effects brought about by any or all of the steps of any of the methods shown and described herein when performed in any suitable order any suitable apparatus or device or combination of such programmed to perform alone or in combination any or all of the steps of any of the methods shown and described herein in any suitable order electronic devices each including a processor and a cooperating input device and or output device and operative to perform in software any steps shown and described herein information storage devices or physical records such as disks or hard drives causing a computer or other device to be configured so as to carry out any or all of the steps of any of the methods shown and described herein in any suitable order a program pre stored e.g. in memory or on an information network such as the Internet before or after being downloaded which embodies any or all of the steps of any of the methods shown and described herein in any suitable order and the method of uploading or downloading such and a system including server s and or client s for using such and hardware which performs any or all of the steps of any of the methods shown and described herein in any suitable order either alone or in conjunction with software. Any computer readable or machine readable media described herein is intended to include non transitory computer or machine readable media.

Any computations or other forms of analysis described herein may be performed by a suitable computerized method. Any step described herein may be computer implemented. The invention shown and described herein may include a using a computerized method to identify a solution to any of the problems or for any of the objectives described herein the solution optionally including at least one of a decision an action a product a service or any other information described herein that impacts in a positive manner a problem or objectives described herein and b outputting the solution.

The scope of the present invention is not limited to structures and functions specifically described herein and is also intended to include devices which have the capacity to yield a structure or perform a function described herein such that even though users of the device may not use the capacity they are if they so desire able to modify the device to obtain the structure or function.

Features of the present invention which are described in the context of separate embodiments may also be provided in combination in a single embodiment.

For example a system embodiment is intended to include a corresponding process embodiment. Also each system embodiment is intended to include a server centered view or client centered view or view from any other node of the system of the entire functionality of the system computer readable medium apparatus including only those functionalities performed at that server or client or node.

Conversely features of the invention including method steps which are described for brevity in the context of a single embodiment or in a certain order may be provided separately or in any suitable subcombination or in a different order. The term e.g. is used herein in the sense of a specific example which is not intended to be limiting. Devices apparatuses or systems shown coupled in any of the drawings may in fact be integrated into a single platform in certain embodiments or may be coupled via any appropriate wired or wireless coupling such as but not limited to optical fiber Ethernet Wireless LAN HomePNA power line communication cell phone PDA Blackberry GPRS Satellite including GPS or other mobile delivery. It is appreciated that in the description and drawings shown and described herein functionalities described or illustrated as systems and sub units thereof can also be provided as methods and steps therewithin and functionalities described or illustrated as methods and steps therewithin can also be provided as systems and sub units thereof. The scale used to illustrate various elements in the drawings is merely exemplary and or appropriate for clarity of presentation and is not intended to be limiting.

