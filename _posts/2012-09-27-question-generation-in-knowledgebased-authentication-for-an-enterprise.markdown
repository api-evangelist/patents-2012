---

title: Question generation in knowledge-based authentication for an enterprise
abstract: An improved technique involves generating KBA questions from facts obtained from a personal information management (PIM) server under the control of an organization. Along these lines, such an organization acquires facts from documents such as emails, meeting notices, presentations, and spreadsheets that are stored on a PIM server such as a Microsoft® Exchange server or IBM Lotus® Domino server. A KBA server then generates KBA questions from the acquired facts and stores the KBA questions on a question server. In some arrangements, the KBA server filters out KBA questions based on the nature of the facts from which the KBA questions were derived. The remaining KBA questions are ranked based on historical question data; the KBA server provides the most highly ranked KBA questions to a user claiming to be a member of the organization.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09152775&OS=09152775&RS=09152775
owner: EMC Corporation
number: 09152775
owner_city: Hopkinton
owner_country: US
publication_date: 20120927
---
Conventional knowledge based authentication KBA involves deriving questions regarding a particular user from facts in a publicly available database and asking that user one or more of the derived questions to verify the authenticity of the user. For example conventional KBA accesses facts such as addresses mortgage payments and driving records from a LexisNexis server a credit bureau or a motor vehicle registry.

Suppose that a user wishes to make a purchase at a store using a store account. In conventional KBA the store may ask the user a set of questions derived from a set of facts concerning the user in order to complete the purchase. Such questions may include when were you married what was the make and model of your first car and what was the name of your first pet . If the user answers the questions correctly the store completes the purchase. On the other hand if the user answers questions incorrectly the store may take remedial steps to verify the authenticity of the user. For example the store may ask for further proof of identity such as a driver s license.

Unfortunately there are deficiencies with the above described conventional KBA. For example facts obtained from a publicly available database may be known by members of the public. Consequently KBA questions derived from such facts may be insecure because an imposter may have examined facts relevant to a particular legitimate user.

Further it should be understood that a common purpose of providing KBA questions is to authenticate users within an organization. For example suppose that an employee of a corporation wishes to access sensitive files stored in a database under the control of the corporation. In using conventional KBA to authenticate the employee the corporation has little control over the security of the KBA questions because the corporation does not control the source of the facts.

In contrast to conventional KBA in which an organization may be unsure about the security of KBA questions due to the possibility of an imposter gaining access to facts used to derive the KBA questions an improved technique involves generating KBA questions from facts obtained from a personal information management PIM server under the control of an organization. Along these lines such an organization acquires facts from documents such as emails meeting notices presentations and spreadsheets that are stored on a PIM server such as a Microsoft Exchange server or IBM Lotus Domino server. A KBA server then generates KBA questions from the acquired facts and stores the KBA questions on a question server. In some arrangements the KBA server filters out KBA questions based on the nature of the facts from which the KBA questions were derived. The remaining KBA questions are ranked based on historical question data the KBA server provides the most highly ranked KBA questions to a user claiming to be a member of the organization.

For example suppose that the KBA server obtains emails from a Microsoft Exchange server for generating KBA questions. The KBA server may filter out questions derived from emails that have more than two recipients because the number of people that know the subject matter of the facts extracted from such an email is large enough to pose a risk of an imposter being able to answer KBA questions derived from such facts. Further the KBA server may rank KBA questions that have not been previously asked higher than those that have been previously asked. In such a scenario the KBA server may only present new questions rather than questions that have a history.

Advantageously the improved technique allows an organization to be confident in the security of the KBA questions used to authenticate users attempting to access resources belonging to the organization. The PIM servers from which facts used to derive KBA questions are not available to the public because the information stored on the PIM servers is confidential. Consequently an organization may have control over the security of the KBA questions because the source of facts for those questions is under the control of the organization.

One embodiment of the improved technique is directed to a method of performing KBA. The method includes obtaining a set of user facts from a personal information management PIM server that is under the control of an organization each user fact of the set of user facts including a reference to a user identifier of a user that is a member of the organization. The method also includes generating a set of KBA questions from the set of user facts. The method further includes providing selected KBA questions of the set of KBA questions to a person that has submitted a request to access resources of the organization the request including the user identifier.

Additionally some embodiments of the improved technique are directed to a system constructed and arranged to perform KBA. The system includes a network interface memory and a controller including controlling circuitry constructed and arranged to carry out the method of performing KBA.

Furthermore some embodiments of the improved technique are directed to a computer program product having a non transitory computer readable storage medium which stores code including a set of instructions to carry the method of performing KBA.

An improved technique involves generating KBA questions from facts obtained from a personal information management PIM server under the control of an organization. Along these lines such an organization acquires facts from documents such as emails meeting notices presentations and spreadsheets that are stored on a PIM server such as a Microsoft Exchange server or IBM Lotus Domino server. A KBA server then generates KBA questions from the acquired facts and stores the KBA questions on a question server. In some arrangements the KBA server filters out KBA questions based on the nature of the facts from which the KBA questions were derived. The remaining KBA questions are ranked based on historical question data the KBA server provides the most highly ranked KBA questions to a user claiming to be a member of the organization.

Advantageously the improved technique allows an organization to be confident in the security of the KBA questions used to authenticate users attempting to access resources belonging to the organization. The PIM servers from which facts used to derive KBA questions are not available to the public because the information stored on the PIM servers is confidential. Consequently an organization may have control over the security of the KBA questions because the source of facts for those questions is under the control of the organization.

Communication medium provides network connections between enterprise KBA system personal information management PIM server enterprise app server and authentication terminal . Communications medium may implement a variety of protocols such as TCP IP UDP ATM Ethernet Fibre Channel combinations thereof and the like. Furthermore communications media may include various components e.g. cables switches routers gateways bridges NAS SAN appliances nodes interfaces etc. . Moreover the communications medium are capable of having a variety of topologies e.g. queue manager and spoke ring backbone multi drop point to point irregular combinations thereof and so on .

PIM server stores applications and data concerning personal information including email calendar and shared documents for members of an enterprise. For example the enterprise may be a corporation whose members are employees. Data stored in PIM server takes the form of various documents such as email messages meeting notices and documents on which members have collaborated.

Enterprise KBA system obtains facts from PIM server stores facts on fact server generates KBA questions from facts and provides selected KBA questions to authentication terminal via enterprise app server . KBA system includes a fact server a question server a question generator and a question picker .

Fact server is an electronic system in communication with question generator . Fact server acquires facts from PIM server and stores facts within a fact database see . In some arrangements fact server generates facts from documents stored on PIM server .

Question generator is an electronic system in communication with fact server and question server that generates KBA questions from facts . In some arrangements question generator computes a generation score for a generated KBA question based on facts in order to determine whether to send the KBA question to question server .

Question server is an electronic system in communication with question generator and question picker . Question server stores KBA questions and sends KBA questions to question picker for question selection.

Question picker is an electronic system in communication with question server . Question picker selects questions from KBA questions stored on KBA server based on certain criteria. For example question picker filters out KBA questions that have already been provided to users such as user . In some arrangements question server is also in communication with external systems such as enterprise app server . Question picker may also in communication with authentication terminal at which a service representative provides questions to user .

Enterprise app server provides an application programming interface API for providing questions to user .

Authentication terminal receives questions from enterprise app server and presents them to user in some cases through a service representative. In some arrangements authentication terminal is a Netview terminal.

During operation enterprise KBA eKBA system extracts a set of facts from documents stored on PIM server . In some arrangements eKBA system performs the extraction on a periodic basis e.g. a nightly run. In other arrangements however eKBA system performs the extraction in response to an event.

It should be understood that as a consequence of facts being derived from documents stored on PIM server each fact includes a reference to at least one user identifier of a member of the organization that controls PIM server . In this way facts are in many cases expressions of a relationship between members of the organization. For example one fact derived from an email states that Member A sent Member B an email on Day C at Time D. 

In some arrangements eKBA system extracts a single fact from an aggregation of documents . For example suppose that Member B sent Member A ten emails over a two week period. eKBA system would then lump these emails into a single aggregate fact such as Member B sent Member A ten emails between Day C and Day D. 

eKBA system then generates KBA questions from extracted facts using question generator . In some arrangements question generator generates KBA questions in a similar manner as that known from question generation from publicly available facts. In this way for each member of the organization eKBA system stores a set of KBA questions on question server . In other arrangements however question generator scores a particular KBA question based on facts from which the particular KBA question was derived. Such a score may determine whether the particular KBA question will be included in the set of KBA questions stored on question server . Further details of the role of question generator in such scoring of KBA questions will be provided below with respect to .

User sends to eKBA system a request to access resources . Request includes a user identifier associated with a member of the organization.

Upon receipt of request eKBA system provides user with selected KBA questions from KBA questions stored on question server . In some arrangements eKBA system uses question picker to provide a ranking of KBA questions and selects the highest ranked questions to user . Further details of question picker will be provided below with respect to .

User provides eKBA system with answers not pictured to selected KBA questions and based on the answers eKBA system authenticates user .

Network interface takes the form of an Ethernet card in some arrangements network interface takes other forms including a wireless receiver and a token ring card.

Memory is configured to store code which includes question code configured to generate a set of KBA questions from facts see stored in facts database on storage device . KBA questions in turn are stored in questions database on storage device . Memory is also configured to store selection code for selecting KBA questions to send to user see as well as fact code for extracting facts from documents see . Memory generally takes the form of e.g. random access memory flash memory or a non volatile memory.

Processor takes the form of but is not limited to Intel or AMD based MPUs and can include a single or multi cores each running single or multiple threads. Processor is coupled to memory and is configured to execute instructions from question code selection code and fact code . Processor includes question engine fact engine and selection engine .

During operation processor accesses documents see over network interface . For example PIM server may include a database not pictured on which documents are stored. Processor would then perform lookup operations on the database to find documents that had been stored in the database since the previous lookup operation.

Fact engine forms facts from documents accessed on PIM server . Along these lines fact engine parses documents for particular keywords such as user identifiers fact type identifiers such as meeting and dates and times. Fact engine then forms facts by storing values of attributes defined by fact type identifiers in facts database . In some arrangements facts database stores fact scores associated with the attribute values.

Question engine derives KBA questions from facts and stores derived KBA questions in question database . In some arrangements question engine causes question generator see to use the fact scores stored in facts database to filter KBA questions derived from facts stored in facts database . Further details of such filtering will be discussed below with respect to .

Question engine then engages question generator to compute a generation score that determines whether a question derived from fact will be stored in question server see on question server . Along these lines question generator includes a predetermined set of attributes from which an attribute of a fact is associated with a fact score

Question generator matches an attribute of fact to an attribute stored in the set of predetermined attributes . For example an attribute of fact may be that the email from which fact was extracted included only a single recipient. Question generator matches such an attribute to an attribute in the set and determines a fact score from the match. It should be understood that a given fact may have more than one attribute each attribute and would then have corresponding fact scores and . Moreover a KBA question may be derived from more than one fact question generator derives fact scores for each attribute of each fact.

Question generator then combines fact scores and into a question generation score that corresponds to a KBA question derived from fact having attributes and . For example question generator may add scores and to form generation score .

Question generator compares generation score to a threshold generation score . If generation score is greater than threshold generation score then question generator stores KBA question derived from fact in question database on question server . Alternatively if generation score is greater than threshold generation score then question generator does not store KBA question in question database .

Referring back to at some later point in time processor receives via network interface request see to access resources see . As request includes a user identifier processor accesses KBA questions stored in question database that were derived from facts having a reference to the user identifier. Selection engine then applies selection criteria to select KBA questions from question database . Such a selection process is described below with respect to .

History database includes information concerning previous questions that were presented to users. In some arrangements history database also includes responses to these questions from the users. History database may take the form of a RDBMS but also may be a NoSQL database.

Question picker accesses KBA questions from question database see that are associated with the user identifier. For each KBA question question picker performs a query operation on history database to match that KBA question with an entry on history database . In some arrangements question picker is able to match questions that do not have the exact same wording but are semantically equivalent.

Based on whether there is a match between the KBA question and an entry of history database and if so when an equivalent previous question was presented question picker assigns a ranking value to the KBA question . For example a KBA question for which no entry was found in history database may have a high ranking value while another KBA question for which a matched question was recently presented may have a low ranking value.

Question picker selects the KBA questions having the largest ranking values as selected KBA questions and presents the selected KBA questions to user .

While various embodiments of the invention have been particularly shown and described it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the invention as defined by the appended claims.

For example history database is a special case of a type of policy server. Such a policy server stores policies that provide rules for selecting KBA questions from question database . Another example of a policy server would provide rules questions derived from multiple fact sources e.g. human resources travel etc. .

Furthermore it should be understood that some embodiments are directed to eKBA system which is constructed and arranged to perform KBA. Some embodiments are directed to a process of performing KBA. Also some embodiments are directed to a computer program product which enables computer logic to perform KBA.

In some arrangements eKBA system is implemented by a set of processors or other types of control processing circuitry running software. In such arrangements the software instructions can be delivered within eKBA system respectively see in the form of a computer program product each computer program product having a computer readable storage medium which stores the instructions in a non volatile manner. Alternative examples of suitable computer readable storage media include tangible articles of manufacture and apparatus such as CD ROM flash memory disk memory tape memory and the like.

