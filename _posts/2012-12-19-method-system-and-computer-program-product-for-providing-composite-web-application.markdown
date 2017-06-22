---

title: Method, system and computer program product for providing composite web application
abstract: A method and system for providing composite web application is provided. The method operates at a server computer to receive a client request in the form of an API language request, having a plurality of CLI commands for querying Web services. The process allows generating an Abstract Syntax Tree (AST) from the client request and sequentially executing each node of the AST to query the Web services. All web data received are combined into a composite data structure send back in the form of an API language response to the originator.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09344524&OS=09344524&RS=09344524
owner: 
number: 09344524
owner_city: Orsay
owner_country: FR
publication_date: 20121219
---
This application is a National Stage of International patent application PCT EP2012 076084 filed on Dec. 19 2012 which claims priority to foreign European patent application No. EP 11368029.2 filed on Dec. 22 2011 the disclosures of which are incorporated by reference in their entirety.

The present invention relates to Web Servers and more particularly to a method and system for providing composite Web Application.

The common function of a Web server is to deliver web pages on a request to client computers. A client generally through a web browser or web crawler initiates a communication by sending a request for a specific resource to the Web server and the latter sends back a response with the content of the resource or eventually with an error message if unable to do so.

The World Wide Web Consortium W3C defines a Web service or Web application as a software system designed to support interoperable machine to machine interaction over a network. It has an interface described in a machine processable format specifically Web Services Description Language known by the acronym WSDL . Other systems interact with the Web service in a manner prescribed by its description using SOAP standard messages typically conveyed using HTTP protocol with an Extensible Markup Language XML serialization in conjunction with other Web related standards.

A Web Application Programming Interface API is an interface between a Web service or Web application and a Web server that allows redirecting a request towards the Uniform Resource Locators URL of the requested Web services.

When used in the context of Web development a Web API is typically a defined set of Hypertext Transfer Protocol HTTP request messages along with a definition of the structure of response messages usually expressed in an Extensible Markup Language XML or JavaScript Object Notation JSON format.

Nowadays Web API allows combining multiple Web services and applications into new applications known as mashups.

However when running composite Web services the requesting Web server must send as much as requests than the requested Web services before consolidating information and sending back the mashup result. This is time consuming and cumbersome.

In language programming the well known Command Line Interface CLI is the appropriate tool for interfacing with a computer operating system such as UNIX or Windows. CLI users enter commands in a text mode to define one or several operations to be executed by the computer system. Upon completion the result is provided in the form of text lines on the Command Line Interface. There exists today some users interface for using CLI which are named CLI shell that allow to have various commands to be executed by a respective operating system. Most popular are the UNIX shell the cmd.exe shell or the COMMAND.COM shell to name a few.

Whereas CLI offer interface with extensive dialog possibilities and consequently CLI are mainly used by programmers developers and system administrators as it requires knowledge of language queries their use is limited to execution of operating system commands.

So there is not today any interface whether CLI API or any other one that allows entering one request to address several web services or applications. And there is a need for a Web server that does not require running successive requests to Web services and Web applications to provide a composite application.

Finally there is a need for a solution that removes the aforementioned drawbacks. The present invention offers such solution.

According to a first aspect of the present invention there is provided a method as further described in the appended independent claim .

According to a second aspect of the present invention there is provided an apparatus comprising means adapted for carrying out each step of the method according to the first aspect of the invention.

According to a third aspect of the present invention there is provided a computer readable medium having encoded thereon a computer program comprising instructions for carrying out the steps of the method when the computer program is executed on a computer.

Further advantages of the present invention will become clear to the skilled person upon examination of the drawings and detailed description. It is intended that any additional advantages be incorporated therein.

With reference to a block diagram of a web environment for operating the present invention is depicted in accordance with a preferred embodiment.

The web environment includes a client computer . The client computer may be any general purpose user computer laptop personal digital assistants cellular phones or the like from which a user may access a network . For sake of clarity only one client computer is described but the skilled person will appreciate that the description is illustrative and will easily devise that the invention may run for a plurality of client computers 

The client computer may access the network either directly or through a client server . The network may be the internet or an intranet network. In the rest of the description the network is intended to be the internet or World Wide Web network and the client server a client web server.

The web server may access the internet either directly or through a webshell server to execute web services or web applications to for a user request received from client computer .

The functionalities of the webshell server of the present invention may be implemented on a general purpose server whether private or virtual one and may operate on well known operating systems.

In a preferred implementation the webshell server of the present invention operates on an Apache Debian LINUX server using the MySQL database with PHP v5.3 .

The webshell server comprises a parsing module to receive a complex request having both API language syntax and CLI language commands into.

Another example of the structure of a request is proposed at the end of the description to illustrate the characteristic of mixing both API language syntax and CLI commands in a unique request to be processed by the system of the present invention. It is important to note that the script language used for the CLI commands may be a Javascript language or any variation such as Coffeescript or Typescript language.

The person skilled in the art will appreciate that some variations are applied to the process of the invention described below depending on the language used whether the language is an interpreted language Javascript Ruby Python php a compiled language C C . . . or a semi complied language Java c . Particularly the webshell server may run a different routine to execute the code receives according to the language used. For an interpreted language the code is executed by the language interpreter nodejs ruby tec . For a complied language the code is compiled at the webshell server and the resulting binary code is executed. For a semi compiled language the code is complied in a byte code which is executed by a Virtual Machine VM such as a jvm for Java for example.

In a preferred implementation the Webshell API is a Representational State Transfer REST API allowing using a Request parameter to execute script code.

The REST API may be executed from any navigator such as Internet Explorer Firefox Chrome Safari to name a few.

The webshell server further comprises an interpreter module to transform the complex request into an Abstract Syntax Tree AST and to execute each node of the tree.

The AST can be build by interpreters like the node.js or php ones or with other ones known by those skilled in the art.

An abstract syntax tree which is a well known structure for programmers is a tree representation of the abstract syntactic structure of source code written in a programming language. Each node of the tree denotes a construct occurring in the source code. The syntax is abstract in the sense that it does not represent every detail that appears in the real syntax. For instance grouping parentheses are implicit in the tree structure and a syntactic construct such as an if condition then expression may be denoted by a single node with two branches.

An exemplary of the AST structure of the present invention will be detailed below with reference to .

The webshell server further comprises a storage module allowing storing script command of the received complex request and storing data received back from the requested web services.

The webshell server is further equipped with an encoding module to combine all data stored into a global data structure to be sent to the originated client computer as the response to the original request.

Whereas the webshell server is shown and described as a remote server from the client server it is to be appreciated that the webshell server may be implemented as part of a client server without departing from the scope of the present invention.

As said the invention offers new functionalities for a server herein called webshell server allowing communicating in one request having command line interface commands with multiple web services and web applications. The webshell server of the present invention allows executing and combining a plurality of web services from a unique request.

Going to a component level flow diagram illustrating Web server s interoperability in accordance with an embodiment of the present invention is now described.

As shown the request contains the standard API language of Hypertext Transfer Protocol HTTP request for declaring the webshell server plus CLI language script to list all the web services to be requested and data required for this request.

The request includes commands in script language to execute web services either at the server side and or at the user side by the user web navigator. For request in object language the commands are objects.

In the example four web services are listed Foursquare Google Maps Wikipedia and Google. It is to be appreciated that those services are used for purpose of illustration but are not intended to limit the number and kind of web services to be requested by the webshell server of the present invention. Moreover the web services herein listed are property of their authors.

At the webshell server side the request is assigned to a dedicated process to execute the global request including all the services.

The request is parsed in a parsing module and the script included in the request is stored in memory storage .

Simultaneously the code contained in the request is used by the interpreter to generate the Abstract Syntax Tree having nodes corresponding to the web services.

The command node may run for any APIs and Web services to generate composite web services web applications or mash ups. The resulting mash ups may be used as new commands to be executed in command nodes and generate new and more advanced web services and mash ups.

For purpose of the example two nodes have been illustrated with a content set as variables a and b . It is one advantage of the present invention to temporary set the value of a variable to the web data received in response to a previous web service request and to combine the value of the variable with a next web service request.

Coming back to the web service corresponding to a first command node in the AST herein foursquare is queried to search for Paris . The query is in the form of an API web request as follows 

In return the web service sends back to the webshell server the appropriate respective response herein the locations in Paris.

The memory storage allows storing the first response as first variable a . For sake of clarity the memory storage is illustrated as single zone storage within the webshell server but alternatively two or more memories may be used to store the script and the content of the variables.

Simultaneously the content of the first response is stored as parts of the encoding module to build a global data structure along the execution of the AST to provide a final response to the web server.

Next the AST declares execution of the next gmaps command a corresponding request is sent to web service Google Maps as follow 

The content of the Google Maps response is stored as variable b . Simultaneously the content of the second response is stored as part of the encoding module .

As can be seen on the next AST execution runs a loop process foreach to search for each location identified by Google Maps .

As the next web service to be queried is Google a request in the form of an API request is sent to Google as follows 

The content of the Google response is stored only as part of the encoding module as no variable has been declared for this command.

The content of the Wikipedia response is stored only as part of the global data structure as no variable has been declared with this command.

Finally the encoding module allows encapsulating the data stored from all responses during the AST execution process.

The process allows applying the appropriate action to each response collected. For example if a jsClient Api object its initialization is executed instantiated loaded and then all calls from this object are executed such as for example zooming a map.

Preferably the global data structure is built during the execution of the AST as a table having one or several entries each entry pointing to one response to a web service request.

Each entry contains one or more attributes such as errors view to be displayed data table title identifier process and so. Each attribute further contains an associated value which may be either a simple value such as an integer a string a float or a complex value such as a table or an object.

Turning to a flow diagram describing a process for providing composite web applications is now described.

Process begins when a complex request is received at the webshell server on step . The complex request is received through an API and contains all the calls to the requested web services under script CLI language.

It is one advantage of the present invention to include easily in the originating request any specific CLI command corresponding to any respective Web service or web application. When a new CLI command is added to a request a XML file is generated having information relative to the specific command to simplify the command processing and to process errors.

On next step the request is parsed and all script code is stored in memory storage . The request is executed simultaneously to the execution of the script code as follow.

At step an Abstract Syntax Tree is generated from the code of the request. The AST comprises nodes and branches to be interpreted in a loop mode .

In an alternate embodiment during the AST generation the process allows checking if a token value is defined as an alias and if so the token is set to the corresponding value. webshell server

The token g is defined as an alias pointing to google and during the AST execution each time token g is encountered the value is directly replaced by google . Those skilled in the art will appreciate that a link command as above allows declaring an URL to an API and so to replace it dynamically during the AST execution.

A first node of the AST is executed on step and the received response step is stored step as a first response within a global data structure. The response may also be stored as a variable to be later used during the AST execution.

On step a test is performed to determine if all nodes of the AST have been executed and if not the process checks for the next node step and returns to step .

When all nodes have been run branch Yes of step the process continues with step where all data corresponding to the execution of all the APIs and stored in a global data structure on step are encapsulated in a final data structure.

It is appreciated that the process run at the webshell server of the present invention either for a web service request or for an internal API request allows sending back a result in a form that is directly to be used by the user navigator.

Particularly the process of the present invention allows building a final data structure that contains all information necessary to execute an API such as the initialization information the loading information the building information and the interface including the various calls. Each call within the final data structure is executed when the request is executed and each result is added to the final data structure with the corresponding call information.

Additionally the process may include an authentication step before processing a client request. The authentication may be in the form of using an API secret key at the client server side and sending the client request to the webshell server through a Secure Socket Layer SSL connection. Authentication requests are processed at the webshell server and key access such as the Open Authorization OAuth one may be exchanged securely between the client server and the web services providers.

To recall the present invention take advantage of using requests mixing both API language and CLI language. The request processing is partially executed on the webshell server on the client server and on the end user computer. This allows monitoring transparently asynchronous as well as synchronous calls request.

For the purpose of illustration another example of a request as used by the present invention is provided. A user wants to display from Google Maps the railway stations SNCF gares plus having from Foursquare all the coffee bars around the fifth railway station.

The Webshell server run the API apis.google.maps . The latter sends back a view having javascript language jsClientApi allowing to further execute functions such as center zoom addmarker . The Google maps is stored for the final answer .

The Webshell server allows executing synchronously the request to get the list of the railway stations and stores the list as a variable gare . Then for each railway station a marker is added on the Google Maps by adding a addmarker call within the final data structure.

Then the process allows searching with Foursquare for the coffee bars around the fifth railway station by executing an API request. The answer is stored in the bars variable.

For each coffee bar found a addmarker call is added within the final data structure to allow identifying the coffee localization.

The final answer is a file in a JSON JavaScript Object Notation format including all the html data from the map creation plus all the javascript calls to be executed to get the answer to the initial request.

Finally it is to be appreciated that the invention can take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. In a preferred embodiment the invention is implemented in software which includes but is not limited to firmware resident software microcode etc.

Furthermore the invention can take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium can be any apparatus that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The medium can be an electronic magnetic optical electromagnetic infrared or semiconductor system or apparatus or device or a propagation medium. Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

To recall the present invention offers an innovative and major advance in Web services environment by allowing a combination of successive executions of Web services or applications. To achieve the method of the present invention allows to store the results of web requests and to later use those results for subsequent web service requests. The particular combination of API and CLI languages allows declaring as new variables both simple variables and complex variables. To summarize the present invention allows processing composite web requests from one client request including CLI commands that are interpreted and executed using an Abstract Syntax Tree AST . The method described allows thus executing Web services with request having CLI commands. The proposed novel approach is a basis for a web operating system or a cloud operating system.

