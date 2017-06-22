---

title: Methods for generating visual data from nodes containing identify data for individuals from a set view point
abstract: Computer implemented methods for constructing dynamic relationships between data for presentation on a display are provided. The data is obtained from one or more data sources and managed as a plurality of nodes. The nodes increase or decrease in number over time. One method includes setting a point of view from one of the nodes of the plurality of nodes, and the setting of the point of view acting to order certain ones of the plurality of nodes to produce a representation from the point of view. The method generates visual data that illustrates the representation of the plurality of nodes from the set point of view and provides the visual data for rendering on a display of a device. Certain ones of the nodes contain unique identity data for individuals, and the nodes are associated with other nodes based on relationships between the individuals.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09547923&OS=09547923&RS=09547923
owner: GOOGLE INC.
number: 09547923
owner_city: Mountain View
owner_country: US
publication_date: 20120914
---
This application is a continuation of U.S. patent application Ser. No. 13 397 535 filed on Feb. 15 2012 which is a continuation of U.S. patent application Ser. No. 13 198 301 filed on Aug. 4 2011 which is a continuation of U.S. patent application Ser. No. 10 810 407 issued as U.S. Pat. No. 8 019 786 filed on Mar. 26 2004 which is a continuation of U.S. patent application Ser. No. 09 578 127 filed on May 24 2000 issued as U.S. Pat. No. 6 714 936 and claims the benefit of U.S. Provisional Application No. 60 135 740 filed May 25 1999. All above listed applications are herein incorporated by reference.

The invention is a computer implemented method of storing manipulating accessing and displaying data and its relationships and a computer system with memory containing data programmed to implement such method.

Today s GUI graphical user interface software requires a great deal of training for proficiency. They rarely show their context and rarely show internal data and control points. The actions of applications should be fast and easy to use not confusing and restrictive.

Navigating a current GUI is to learn how the programmers have organized the data and the control points. Today s UI user interface relies on windows and pull down menus which hide prior ones as the user makes selections and an often complex series of mouse selections to navigate to the desired control point. In performing an action after traversing a path of pull down menus and button selections on different sub windows the user may be returned to the beginning forced to retrace their steps if they wish to apply an action repeatedly. The UI does not shift from one state to another in a smooth way.

Current GUI s with pop up menus and layers of text based windows. Today s GUI s suffer from a list mentality rows of icons with little or no meaning in their position no relationships readily visible between themselves or to concepts which the user may be interested in or have knowledge of.

The standard GUI concept of a canvas with buttons and pull downs require reading and thinking about the meaning of text to hopefully grasp the model of control flow. Virtually no information is given outside of static text to help the user understand relationships and control points.

Gaining access to fields or parameters in current applications can also be a challenge. For example the Microsoft POP mail retrieval service uses a configuration profile defined by the user to access the mail server and displays the name of that configuration when logging. Although one sees evidence of the existence of this configuration how does one change it The answer may not be obvious. An object oriented system that implemented all actions on an object could also provide the mechanism of self deletion but this helps only if the object itself is visible and accessible via the GUI. This is what DataSea does. Windows technology is moving in this direction by having many words in menus modifiable but DataSea achieves this automatically by virtue of its design.

A complex GUI such as a presentation and control system for database administration today consists of many canvases and widgets which hopefully present through multiple mouse clicks all information that is available. Any data can be changed by any part of the program and this leads to bugs if the programmer can not easily see these interactions. A DataSea presentation of data and control shows all the objects and their relationships and thus shows immediately what nodes can affect changes to the data reducing bugs. To turn a DataSea view into an application means to set internal parameters create and link together application nodes and add programmatic instructions to these nodes. DataSea will implement a means to invoke these instructions.

DataSea can serve as the single source of data for any application. Any RDBMS relational database management system can do this but DataSea is completely flexible in its data storage and linkage guaranteeing forward compatibility by eliminating the risk of changes to database structure and entity relationships of RDBs Relational Databases .

Two separate DataSea databases can be joined and automatic linkage routines will merge them without programmer effort. This is generally impossible in RDBs. This joining can occur by simply adding nodes and links from the two data sets and adding together the contents of the master index NameListObj. Or the two data sets can be blended merging their contents taking two nodes with the same name from the two separate data sets creating one node which has all the links from the two separate nodes.

In most storage systems especially RDBMS s the user must know how information is stored in the computer and which parameter or parameters that the computer is using to store the data as well as the proper range of values. This is often non intuitive and may seem somewhat arbitrary for a non technical user. Ideally the computer would better mimic human associative memory allowing the user to look for new information associated with that which is better known such as a particular context or a range of values without regard to parameterization to specify the target of interest.

OLAP online analytical processing and data mining require both analytical models and custom code to apply these models to particular database structures. These customizations may be hard coded non portable and irrelevant to the model. The DataSea API application programming interface provides access to all data while eliminating the need to worry about database structure such as tables columns and foreign keys.

Up coming non linear presentation tools such as fish eye or hyperbolic views do not address the difficult problem of how to lay out the data and their relationships before the viewing method is applied. These may be useful but do not address the difficult issue of how the graph is laid out initially. Nor are they appropriate for highly linked data sets because the plethora of links resembles a cobweb from a psychotic spider.

VR takes advantage of visual clues and spatial awareness but only for data sets that may be appropriately mapped to a 3 dimensional space. Generally data is N dimensional and thus in general virtual reality which models information as physical objects in 3D space is inappropriate for viewing arbitrary data.

Even more than a GUI voice control needs a smooth transition from state to state in response to commands so that the user can follow what is happening. GUIs hide previous states with new windows while the present invention moves objects gradually and continuously in response to programmatic or user events.

The inventive method referred to as DataSea is a method for storing accessing and visualizing information. Data is stored into nodes and visualized as a sea of linked nodes. Nodes can contain anything such as documents movies telephone numbers applications or words containing concepts. Interactions with the user organize the data from a defined and then refined point of view with relevant data brought to their attention by smooth changes in the data s appearance.

Essentially a handful of nodes which are typically selected by value are linked to the point of view turning the web of data into a hierarchical network. Further order is imposed by the use of two types of commands one which relies on the data values the other on the links and types of the data nodes.

The user typically enters words into a computer programmed in accordance with DataSea and watches DataSea s response. Individual nodes are rendered according to the sequence of nodes between themselves and the point of view allowing different presentations of data. Applications may be stored into nodes and can be located and executed by DataSea. These applications can operate on and present information from DataSea in the conventional manner with windows and menus or by using the DataSea mechanisms of visualization including the so called virtual reality mode VR mode which supports deterministic data placement as needed in such things as forms and spread sheets.

This is a disclosure of computer implemented methods for storing manipulating accessing and displaying data and its relationships and of computer systems programmed to implement such methods.

These methods are flexible applicable to any kind of data and are useful to diverse groups of users. A prototype is implemented in the Java programming language.

Data is stored into nodes which are linked together. All nodes contain variables including descriptions types magnitudes and timestamps. Links also contain information about themselves including connection strength of the link and descriptive information.

Data is accessed and modified based on the values of data their relationships the values of DataSea parameters and links between nodes rather than pre determined locations in memory as is done in most programming models.

Any existing application can be emulated in DataSea by creating and linking appropriate nodes. Positions of nodes as displayed on the screen are a result of processing force parameters rather than pre determined positions.

This approach to the command interface and the smooth changes of state in visual feedback lends DataSea to voice input and thus wireless PDA personal digital assistant type devices.

 Target data set is an ideal collection of nodes representing the information the user is searching for.

 Traveling downstream means going from node A to node B only if A.getPol B is . The polarization of the link between A and B can be set on entering the link between A and B the order of A and B determining the polarization 

A.getPol B is . Typically nodes A and B are linked such that node B is downstream from node A when node A is more general than node B so that by traveling downstream from node A to Node B a user encounters more specific rather than less specific information . In characterizing a node a user usually wants to see progressively more general broader information about it.

A Recently visited node denotes a node being used in an operation which traverses the network. The node s TimeStamp is updated on a visit.

As shown in each node has a link to at least one other node. Each link is defined by three values CS which is Connection Strength of a link initially set to 1.0 Description which is a free form String describing the node and Type For example DN data node and AN abstract node .

A candy factory supervisor performs the following tasks there are many different commands and choices of values which will give similar results 

DataSea is a comprehensive program that stores manipulates and visualizes all forms of data. Visually animated objects or nodes represent data or abstract concepts. Interactive commands which something like verbs operate on nodes and the links between them which act something like nouns . These commands change internal parameters of the nodes and links. These parameters are visualized by qualities such as position and size. Certain nodes are emphasized presenting information. The user finds the data or resource needed without knowledge of the data structure.

Unusual features of DataSea include relatively natural commands robustness to imprecise queries ability to generalize absence of restrictive structure use of semantic information and smooth transitions between visual states of the user interface. The simple commands and feedback from smooth visual transitions is key in integration DataSea with a voice interface.

The front end of DataSea is a query interpreter and visualization system and on the back end is a database and API application programming interface . Briefly one sees a Sea of Data and after each of a series of commands one sees increasingly relevant data more prominently.

DataSea nodes act something like nouns of a natural language and DataSea commands something like verbs. Here are the principal steps involved in a user query 

In a preferred embodiment DataSea is a pure Java application that can serve in a range of roles. It can view and control existing and legacy data such as email documents file directories and system utilities. It can ultimately serve as the principal UI to a system managing all data and system resources of a personal computer or workstation.

The natural ability of people to recognize visual patterns can be leveraged to convey information rapidly to the user. For instance certain algorithms which depend on particular node and link configurations can render and position those nodes for rapid recognition. For example if a target DN is surrounded by intermediate DNs which are themselves linked each to a distal AN then those intermediate DNs are probably describing the target DN. The number of intermediates is then a measure of how much information is known about the target DN.

Its ability to gracefully reduce the complexity of the visual output means that a wireless hand held client can be used to quickly browse and retrieve information from a remote server.

The simplicity of commands and accessibility of DataSea to the novice user lends itself to voice commands that can be used to navigate and control the display of DataSea.

The simplicity of DataSea s data structure allows easy acquisition and integration of legacy data into DataSea. Because new data is integrated with old the acquisition of new data not only allows its retrieval by the user but also enhances the user s retrieval of older data. Thus as DataSea matures in its data content queries are more robust to imprecise terms from the user. Since DataSea captures the information in the data and its structure from legacy databases applications in DataSea can emulate legacy applications while of course making this information available to broader use within DataSea.

While DataSea can emulate a RDBMS without the complications of tables and foreign keys the rich connections of DataSea and its ability to insert abstract nodes opens the way for neural type processing. Learning by example is one example of that new capability. Learning by example refers to adjusting mag and CS values by voting via more or less for example on DNs without relying on ANs. This selects DNs which the user especially likes or dislikes. Applying commands to DNs such as files or URLs changes not only the mag of each DN but changes the CS and mag in its neighborhood typically spreading through related ANs thereby changing the mag of other DNs in the neighborhood i.e. having similar qualities as the DNs that the user liked. A different point of view applied to DataSea by virtue of different connections and connection strengths changes the presentation of data as fundamentally as changing the database design in a relational database but much more easily.

DataSea can be used to perform simple web history viewing data mining and can be used as the principal Desktop UI for a computer showing all of the computer resources.

Viewing domains such as file systems web history or HTML documents and computer networks are obvious uses of DataSea and are early targets of DataSea. Applied to a web browser the text of links to the current URL can be retrieved and parsed into DataSea in effect pre digesting it for the user.

The GUI Graphical User Interface of DataSea is important but the underlying structure of DataSea queries and input methods are curiously appropriate for voice and natural language interfacing. Since queries input and control of DataSea rely on simple words DataSea current voice recognition software can be used instead of text input and would significantly improve the uniqueness and general usability of DataSea. No other UI uses voice or is as appropriate for voice control. Since the results of many queries may be a short answer voice generation is an appropriate output method in addition to or instead of graphic output. For instance the query show John Smith and address is precise enough to generate one value significantly stronger than others and therefore amenable to a programmatic decision for selecting which results to submit to voice output. In this way voice can be a complete communications method opening the door to remote access via telephone or wireless device.

Another opportunity involves selling server time for web searches giving away client software initially. A typical interaction might involve throwing a number of search terms asking for a display of abstraction categories or examples of URL s followed by the user judging prominent nodes repeating as the search narrows.

DataSea s data structure and tools lend themselves naturally to data warehousing and mining each with an estimated worldwide budget in 1999 of nearly 2 billion. DataSea intrinsically provides data mining and warehouse support. DataSea supports any type of data without specifying in advance the fields or tables to use. This is good for arbitrary user input such as free form notes or machine generated input such as received data from automated test equipment. DataSea therefore is a completely flexible data warehouse.

Data mining is supported by DataSea s ability to reorganize any data based on user defined point of views the ability to link any and all data and the ability to store the processing of data and applications into DataSea itself.

DataSea can serve as the Desktop screen the principal interface to all system services independent of operating system. It can do this on demand without locking the user into a particular operating system.

Most methods have three versions of arguments String s and Node n1 Node n2 . . . . If null then lastNode is used if String then matching nodes are looked for both pass one or more nodes to the third version which takes explicit Nodes.

Custom programs can translate legacy formats into DataSea linked nodes e.g. to load information about a file system the names of files and directories are stored into a tree representation first then suffix and name can be used to create ANs then content can be analyzed e.g. by putting it through the Notes processor.

A RDB Relational Database would be loaded by storing the names of databases tables and columns into ANs and then values into DNs and keys into links. All these would be linked appropriately e.g. table name linked to column names linked to all DNs having the values in those columns

A dictionary or synonym list can be loaded. The Type and Desc of links between synonyms or nodes with similar meaning are set. E.g. Type synonym Desc from Webster s 10Ed. 

The user need not know about the data structure such as database tables and their entity relationships in a relational database or the directory structure of a file system. Nor does the user need to parameterize and decide how to store data but may rather simply stuff it into DataSea. DataSea will parse the textual data and create links to representing abstract nodes. Abstract nodes are typically single words representing simple or complex concepts and are linked to data nodes related to them. These nodes typically are massively linked.

DataSea is accessible from external programs via its API. More interestingly though Java code may be stored into a node fully integrating data and methods. The Java code can then act from within DataSea for instance modifying the rendering of objects or analyzing data and creating new nodes and links.

The sequence of positioning and rendering flows through the network of nodes from the POV distally. Typically an application will start from one node specified by name pointing device or other means and will search the neighborhood of that node for certain relationships or values and types. For example invoking Phone Jim can find the nearest DN Jim then present the nearest DN which is linked to AN phone number . Thus commands like Phone emergency can work since emergency can be linked to 911 which can have a large default CS which allows it to dominate and Phone 123 Main St can work since the address 123 Main St can be linked to a phone number through a DN of a person s name.

In addition to the DataSea commands such as show abs and sim new applications can be written to extend the base command set of DataSea.

All nodes have the capacity to store a VRObject which contains position and rendering information. It includes a triplet of numbers describing the relative position of a child to its parent if the rendering mode of DataSea is set to VR mode .

Typically computer applications use or set values at specific locations of memory and may or may not check their values by some means or rules or comparisons.

DataSea looks for information by nearness a fuzzy metric and or characteristics of its links and or characteristics of nodes directly or indirectly linked and or their values.

Besides looking for DNs which are linked to specific ANs an application in DataSea can query the distance or conceptual distance from a node to one or more values of values such as data values TimeStamps or other parameters . Decisions can be based on complex functions of environment checking.

The visual tools of DataSea are based on a visual language which is completely different from today s standard GUI s and gives the user easier access to relevant data and inhibits irrelevant data. DataSea can visually present large amounts of data and the relationships amongst them emphasizing that which is relevant while keeping the larger context. The user sees exactly the data that is needed as well as related data a form of look ahead albeit at lower resolution.

The data presentation changes as the user interacts with DataSea. Data moves smoothly from the background to the foreground bringing it to the users attention in response to the user. The gradual shift in visual states helps the user to understand what is happening as the query progresses.

The scene begins with a sea of objects representing nodes. Ordering of this sea begins as a result of commands to set a POV or by changing the mode to VRmode on some or all nodes. Typically one sees the sea of data in the background with the POV in the foreground and a TimeLine along an edge such as the bottom. Nodes move and change their appearance with interactions. These interactions can be with the user or with programs inside DataSea or externally.

The positions of nodes are changed by iterative calculations of forces on them thus they move visibly between positions rather than jumping suddenly. In this way changes in state and thus appearance can be followed by the user better than by sudden changes of appearance.

Nodes are positioned dependent a set of pressures from sources each pressure from a source e.g. POV parent neighbors being a function of that source s preferred position or distance between the child and the source the child s mag dist etc. The optimum distance to point of view is proportional to dist f mag .

Point of view is either a new temporary node set at a specific position on screen or is an existing node.

The visual tools of DataSea are based on a visual language which is completely different from today s standard GUI s and gives the user easier access to relevant data and inhibits irrelevant data. DataSea can visually present large amounts of data and the relationships amongst them emphasizing that which is relevant while keeping the larger context. The user sees exactly the data that is needed as well as related data a form of look ahead albeit at lower resolution.

The data presentation changes as the user interacts with DataSea. Data moves smoothly from the background to the foreground bringing it to the users attention in response to the user. The gradual shift in visual states helps the user to understand what is happening as the query progresses. For example compare the ease of understanding either of these two scenarios First watching five animated objects which represent five words in alphabetical order reverse their order representing reverse alphabetical ordering Second watching five words on a line change from ascending alphabetical order to descending. In the first case reversal is apparent. In the second the simple operation of reversal is far less apparent seeing the reversal requires re analyzing the words and then trying out one or more possible explanations. In DataSea nodes cluster and move individually and in groups in response to queries. Internal parameters inherent in each node and link change in response to queries. These internal parameters are mapped to visual behavior and appearances such as size position color and shape. These visual cues are used to enhance certain nodes or groups of nodes and their links. The internal parameters are changed by typically recursive commands that start at one node and spread through links to others. Commands adjust connection strength and magnitude of nodes based on their programmed algorithms and local node and link information such as node type and the distance from the point of view. The point of view distance parameters are associated with each node and are functions of the shortest path from that node to the point of view. Recursive commands are self terminating typically but not always acting distal to the point of view where the value of the next nodes distance is greater than or equal to the current distance and often but not always producing less effect further away from the point of view.

A new query is begun by entering words similar to a web search or manipulating regions of the background with the mouse. One or more data nodes are directly hit increasing their magnitude and secondary nodes those distal to a primary and their links are affected exactly how depends on the spread mode of the operation. Nearness to the point of view is usually a function of link distance and magnitude but other methods are possible e.g. link distance alone which display data in a simple hierarchical set of levels . Details of nodes are normally suppressed but with the magnifier mode turned on any node under the cursor presents more information. Another mode is warp mode which acts like a large magnifying lens on a region of the screen. This is similar to hyperbolic viewing of networks of nodes.

Which nodes are enhanced depends on the command and the spread mode which is the way in which it traverses the linked nodes. The simplest spread mode is radial this modifies the node at distance n 1 based on the strongest node directly connected to it of distance n in effect being influenced by the node which is on the strongest path back to the point of view. Another spread mode is sum which adds up all the contributions of nodes of distance n to directly connected nodes of distance n 1. In sum mode a single data node distal to a large number of nodes will sum all their contributions. This is especially useful in the Similarity and Abstractions operations. If a specific node is specified in the query it is enhanced by for instance growing in size and moving towards the point of view from the background blur of nodes. If an operation of an abstraction type is used the abstract nodes are enhanced. The relative positioning of higher or lower levels of abstraction depends on the specific command. If an operation of a similarity type is used data nodes predominate by approaching the point of view and by being enhanced.

Rather than connecting the hits immediately and directly to the point of view abstract nodes in common are first drawn near the point of view. These more abstract nodes are then followed by more detailed ones receding back to the backdrop positioned to give the sense of their being pulled out of the DataSea. Qualities like time since an event or distance to one or more chosen abstract nodes can act as a secondary force or wind acting to influence the position of nodes along one of the 3 dimensions of the visualization.

Data in DataSea is heavily linked without restrictions on what can be linked. DataSea solves the cobweb visual problem by establishing a point of view for the users queries. The problem of following links that are loops is solved by calculating on the fly the shortest number of links from the point of view to the nodes. This turns a series of self referencing loops into a temporary hierarchy based on the current point of view.

The user can browse raw data in DataSea but meaningful structure comes from the interaction between the point of view and raw data. This is analogous to the quantum physics effect of forcing a wave function into a specific physical state by applying an observation to the wave function interaction with the user that forces data into its useful visible state.

A point of view is one form of an abstract node. Once the user finishes a query the point of view that has been created can be absorbed into DataSea and used later a form of checkpoint used in calculations.

Links can occur rather mindlessly for instance simply by association to part or all of an inputted document in a way which captures relationships for instance field definitions from legacy databases or semantic meaning from for example some level of natural language processing.

Postprocessing inside DataSea creates abstract nodes. These represent abstractions of the data inside DataSea representing concepts or the results of analysis. A mature DataSea will contain a large proportion of these abstract nodes.

Each event which links data within DataSea stores a link ID along with it. Thus any two nodes can be linked together more than once each link having a different ID to differentiate the context of their being linked. A single link ID can be used between many nodes as long as that particular subset of nodes has a meaningful context. This context is stored in an abstract node which linked of course to the subset with that link ID and contains the reason for the links.

Data is user defined and customizable whatever the user puts into DataSea it merely needs to be in a computer representation. Data is held inside so called nodes which may be linked together. A data node can be a specific value text such as a web page or free form entry or an object representing something as complex as a virtual reality view of a manufacturing facility. Text in any language is broken up into words and stored. All of the different forms of data share identical mechanisms of storage linkage search presentation and access. The database contains highly linked data but differs in significant ways from RDBMS s relational database management systems including the ability to create links between any data and the elimination of structured tables. Rather than using pre defined fields to capture relationships DataSea uses nodes with appropriate links. As new data is introduced and linked to the existing nodes alternate paths are created between points. This allows data to be found which contains no keywords contained in the query relying on associations contained in the new data. A simple example would be loading a dictionary into DataSea there are few related concepts that are not linked through only even two or three definitions of either. Thus a user may enter a query containing no keywords of a document and be presented with that document albeit emphasized less than documents that contain more direct links to the query terms. AI or manual digestion of information and linkage to abstract concepts is of course possible as is done by those who compile databases for search engines today.

The user need not know about the data structure such as database tables and their entity relationships in a relational database or the directory structure of a file system. Nor does the user need to parameterize and decide how to store data but may rather simply stuff it into DataSea. DataSea will parse the textual data and create links to representing abstract nodes. Abstract nodes are typically single words representing simple or complex concepts and are linked to data nodes related to them. These nodes typically are massively linked.

DataSea is accessible from external programs via its API. More interestingly though Java code may be stored into a node fully integrating data and methods. The Java code can then act from within DataSea for instance modifying the rendering of objects or analyzing data and creating new nodes and links.

A fully integrated application in DataSea uses the DataSea linkage and VR mechanisms to provide the functionality of typical window menu systems. The program of the application is stored in a DataSea application node.

All nodes have the capacity to store a 3 D vector called a VR position . This is a triplet of numbers describing the relative position of a child to its parent if the rendering mode of DataSea is set to VR mode . Any child having non zero a VR position variable will position itself relative to the calling parent based on the VR position values.

In a preferred implementation DataSea is a pure Java application. Once loaded user defined data nodes and links are used to visualize information from a range of sources in an interactive or programmatic way. Data node sources can be email web sites databases or whatever is required. is a block diagram of an embodiment of the invention. All data is contained in objects called nodes. Information describing the data is held in the data node. A complex data node may be broken into smaller ones. A data node has a set of standard fields describing itself and any number of links to other data nodes.

The DataSea database is a highly linked structure of nodes. A link contains information describing itself and how it relates the linked data nodes. It therefore contains semantic information adding a new dimension to interactive or programmed processing of data. That is DataSea supports not just parametric searches which find the values at certain storage locations specified by parameters or content based analysis which find particular values and their relations anywhere in the database but the meaning of a collection of nodes. An example of this could be a link with the description located near relating a computer with a person s name.

Processing of data occurs not only on values of certain parameters but on any value independent of what it is describing. For instance one may search for all information related to an individual s name without specifying which table and column of the database to search and in which tables and columns to look for foreign keys.

Applications can run inside DataSea in fact these applications are themselves held inside a node. Current applications such as automatic report generators and data formatters know which pre defined data fields to place just where and how to order the values. This functionality is served by DataSea s mechanism of node and link descriptors which can act as the column names of RDBMS s. The DataSea link description however also provides semantic information about those relationships.

Objects are positioned and rendered strongly dependent on their content and their links. That is features of the rendering of nodes and the relative positions of nodes depend on content and links. Thus DataSea is unique because the presentation is strongly dependent on the data itself.

Below is a scenario of events with comparisons between two different application approaches The user routinely stores information and calls it up later when faced with a decision as to repair a new printer or buy an old one. This example shows the simplicity and time saved with DataSea. It compares 

Event The user gets a phone call and makes a note to himself that repairman Bob Smith says that printer A will cost 300 to repair and that it is in Joe Baker s office.

Event The user now wonders if he should replace printer A with a new one. He remembers seeing a reference in a recent email for an HP printer and also an HP ad on the web but can t remember exactly where he filed this information.

User marks timeline over the past week and says show printer and email and Hewlett Packard which shows an abstract node Printer linked to email message about printers and a web page of HP printers

User says input John Smith telephone 848 1234 which creates a node holding the entire message and parses it into smaller data nodes.

To demonstrate abstract nodes and learning have processed 50 URLs from cat web search. See all 50 around the abstract nodes surrounding the point of view named show cat . User deselects URLs not related to technical descriptions the abstract nodes change bringing forward URLs with more technical information.

Variation 1 Voice integration. Front end routines take either keyboard input or voice input submitting word strings from either to handler functions. Voice word go acts as keyboard Enter .

DataSea can be used to visualize the DataSea program itself. Besides visualizing nodes which represent data for the user as described elsewhere in this document in so called dataset nodes the nodes that are visualized in DataSea can represent internal programming objects methods or elements of DataSea itself providing a sort of built in debugger .

Code can be inserted into the program which will visualize each methods invocation and its modifications of user data.

DataSea separates the two tasks of modifying the values of node variables and rendering of those nodes. Thus DataSea can redraw the entire scene not only after traversing the linked nodes and re calculating their internal parameters but the entire scene can be re drawn at any time during these calculations even once every time a dataset node variable such as mag is changed.

Thus a self node can indicate to the user its own activity by redrawing the entire scene normally and then highlighting itself or drawing lines to a dataset node or its elements that it is operating on.

For instance if a user commands DataSea to increase the variable mag of a node the method which does that e.g. spread can draw a line from the self node representing spread to the dataset node it is modifying. A simple implementation could be as follows 

If the method spread recursively calls the method spread recursive insert a conditional call to touch after spread recursive 

a method and apparatus for creating nodes containing data linking the nodes into a network setting parameters of the nodes node variables and maintaining information specific to each node e.g. mag CS direction of the link polarization . Each node preferably has a name associated with which it can be searched from a master list 

a method and apparatus using context nodes to modulate link connection strength CS and establish context for groups of nodes. For example a method for associating a set of links and establishing a context node which can modulate the CS of those links thereby sensitizing or desensitizing them to further operations. The context node can also magnify the nodes linked by each link it modulates 

a method and apparatus for loading data from free form notes. For example a method of taking text input text from user or application or text resulting from voice translation and establishing a set of linked nodes therefrom by 

creating a new node for the full text called the full text node discarding selected words e.g. articles 

linking the full text node to individual nodes representing each remaining word in the full text creating new nodes as needed.

For another example a method of converting tabular data i.e. text organized into rows and columns with column headings or RDMBS data with additional links for the keys of the RDBMS into a set of linked nodes in which 

each column heading is represented by an AN the column heading AN each cell of data is represented by a DN

links are established between each column heading AN representing a particular column and those nodes corresponding to the cells in that column

For another example a method of converting files from a computer file system or a set of files linked by HTML references into a set of linked nodes in which 

links from each node are established to terms found in the file content e.g. as is done in the parsing of notes. The procedure can filter the content looking for only certain tag values such as meta tags or heading values e.g. Title Here has Title Here as heading level 1 in HTML 

Another set of links can be made to ANs representing the suffix of files or such ANs can be used as ContextNodes for all links to those files.

For HTML files links are to be established between nodes representing HTML files and other nodes representing HTML files that are referenced by the first HTML file.

For another example a method of converting files from a computer file system in which links are established between DNs representing file directory with DNs representing files or sub directories in that directory a method and apparatus for defining a POV either a particular node or a new node linked to a particular node 

a method and apparatus for defining distance as a function of the number of links between nodes and the node type and hierarchy from the POV and determining distal and proximal directions in which once a POV is set and distances calculated from it a hierarchical tree is defined from what was an arbitrarily complex cross linked network of nodes. Thus if any node x has had its distance set by this routine one is guaranteed to find a path from that node x back to the POV by traveling on a path between nodes of ever decreasing distance values 

a method and apparatus for retrieving data which is linked into a network of nodes interacting with the user to better present the desired data.

a method for emphasizing nodes and paths by tracing backwards from a target node to a POV by following all links to nodes whereby the next node has magnitude less than that of the prior node. Emphasizing those nodes on the path s shows nodes between the target and POV. By traveling backwards from the target node to the POV there may be more than one node having a distance less than the target. This is fine and if all paths backwards with the requirement that they are consistently proximal are emphasized it is fine. For example with Bob being the POV and traveling backwards from the node representing January 1999 all nodes such as notes and events related to Bob will be emphasized 

a method for assigning position to each node which is dependent on the node s parameter values including distance CS and magnitude. Rather than setting the node at the calculated position immediately it moves there gradually thereby showing the transition between states. One way to do this is to calculate forces on a node which are related to the difference between the node s current position and an ideal calculated position.

a Relations Mode Most suitable for narrow queries where we wish to see all the links between nodes in the target data set. Nodes fan out from their parent the angle dependent on the number of children their parent has their distance dependent either on mag or 1 mag or

a Levels Mode Most suitable for broad queries where there are too many links between nodes in the target data set. Starting in the center of the screen fanning out to the left dependent on their distance from the POV ANs are rendered. Starting in the center and belonging to the right half of the screen are the DNs whose position moves further to the right the lower their mag 

a method and apparatus for visualizing data by appearance on a screen. For example a method of assigning visual emphasis color size to each node dependent on the nodes distance CS and magnitude.

Examples of operations performed on nodes of the inventive set of linked nodes or on a sea of displayed representations of such nodes include ABS for characterizing and understanding the environment of nodes and their ANs from a target node traveling distally and upstream find the first AN and emphasize it. This abstracts the target node in terms of linked ANs. To abstract it at a higher level go from those ANs to directly linked ANs which are both distal and upstream. This can continue to arbitrary level until we run out of nodes realistically not very far a handful of levels 

 XABS for emphasizing ANs from a group of nodes those ANs not having been recently visited by query operations emphasizing distally from these ANs will result in a relatively large number of DNs being modified. The user may find ANs which are obviously related or not related to their interest and thereby significantly change the presented data set. Since these ANs haven t been used recently we in effect triangulate the target data set from more vantage points. Determining categories which when evaluated by the user as good or bad have a large effect on narrowing the presented data set that is helping the user find the target data set 

 SIM a method of emphasizing magnifying nodes based on their similarity to a chosen node without specifying values of any node using the sim command which emphasizes DNs linked to any or all of the ANs which are linked to the chosen node s 

 POTMAG a method of modifying the variable Potentiation of a node and using that value to influence the degree of change to the variable mag from a subsequent operation. Thus one operation on the first set of nodes may call Node1.setPotentiationValue and a subsequent operation on the second set of nodes may set the value of Node1.mag based on Node1.getPotentiationValue . This primes a set of nodes and can operate approximately as a soft or non binary AND operation.

Another aspect of the invention is structuring of a set of linked nodes a network including application nodes sometimes referred to as applications . Applications are nodes containing code which get the information they operate on from traversing the network. E.g. an email node application is linked to or given a reference to the node Bob Smith and upon being invoked by the action function inherent in each node or otherwise searches the neighborhood of the Bob Smith node for a DN linked to an AN representing email address. If more than one is found the user is presented with the selection to choose from. Thus any node application can be applied to any node.

One aspect of the invention is a method of accessing data wherein the data is structured as a set of linked nodes and each of the nodes includes at least one link to another one of the nodes. The method includes the steps of 

preliminary to displaying representations of the nodes on a screen in a screen space having N dimensions where N is an integer dividing a display space having dimension N 1 into an array of cells wherein the dimension of the display space includes a size dimension 

implementing a user interface which displays representations of at least some of the nodes on the screen having sizes determined by the cells to which said at least some of the nodes are linked wherein the user interface rapidly accesses individual ones or groups of the nodes in response to selection of at least one of said representations.

The computer program listing appendix filed herewith is incorporated herein by reference. This appendix is a source code listing in the Java programming language of a computer program for programming a computer to implement an embodiment of the invention. In the listing which consists of parts labeled TL.java Timer.java ColorObj.java Link.java Mode.java Node.java Force.java GetURLInfo.java Input.java Populate.java GUI.java DataSea.java LinkObj.java VRObj.java and nsr.java the object gui of class GUI is the top level object and instantiates the object datasea of class DataSea and other objects .

