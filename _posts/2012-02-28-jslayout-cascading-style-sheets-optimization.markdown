---

title: Jslayout cascading style sheets optimization
abstract: A system, method and a computer-readable medium for optimizing cascading style sheet (CSS) rules. The system includes a parser, an optimizer and a compiler. The parser is configured to generate a template tree and a CSS tree. The template tree is associated with a template file that includes one or more templates. The CSS tree is associated with a CSS file that includes one or more CSS rules. The optimizer is configured to traverse the template tree and the CSS tree, and identify each node in the template tree that has a reference to a CSS node in the CSS tree. When the reference exists, optimizer retrieves a CSS rule from the CSS node and appends the CSS rule to the node in the template tree. The compiler compiles the appended template tree.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08745027&OS=08745027&RS=08745027
owner: Google Inc.
number: 08745027
owner_city: Mountain View
owner_country: US
publication_date: 20120228
---
This application claims the benefit of U.S. Provisional Application No. 61 474 046 filed on Apr. 11 2011 and is incorporated by reference in its entirety.

The emergence and development of computer networks and protocols such as the Internet and the World Wide Web or simply web or Web allow a user to use their computing devices to download and display a webpage. When a webpage includes many different sections or identical sections are included in different webpages those sections may be represented using templates.

Often each template accesses a unique cascading style sheets CSS file that includes CSS rules. Conventional template processing systems link the contents of the CSS file in the HTML output stream even when only a subset of the CSS rules included in the CSS file are used.

A system method and a computer readable medium for optimizing cascading style sheet CSS rules. The system includes a parser an optimizer and a compiler. The parser is configured to generate a template tree and a CSS tree. The template tree is associated with a template file that includes one or more templates. The CSS tree is associated with a CSS file that includes one or more CSS rules. The optimizer is configured to traverse the template tree and the CSS tree and identify each node in the template tree that has a reference to one or more CSS nodes in the CSS tree. When the reference exists the optimizer reconstructs a CSS rule from the one or more CSS nodes and appends the CSS rule to the node in the template tree. The compiler compiles the appended template tree.

In another embodiment a system method and a computer readable medium for optimizing cascading style sheet CSS rules are provided. The system includes a communication interface and interpreter. The communication interface receives a message requesting a webpage and sends a response message the response message including an output stream that is displayed as the webpage. The interpreter collects CSS rules included in a compiled template tree into a style element. The interpreter also excludes CSS rules from the style element according to predefined criteria. The interpreter also inserts the style element in the output stream and communicates the output stream to the communication interface.

Further features and advantages of the present invention as well as the structure and operation of various embodiments thereof are described in detail below with reference to the accompanying drawings. It is noted that the invention is not limited to the specific embodiments described herein. Such embodiments are presented herein for illustrative purposes only. Additional embodiments will be apparent to persons skilled in the relevant art s based on the teachings contained herein.

While the present invention is described herein with reference to illustrative embodiments for particular applications it should be understood that the invention is not limited thereto. Those skilled in the art with access to the teachings herein will recognize additional modifications applications and embodiments within the scope thereof and additional fields in which the invention would be of significant utility.

Unlike conventional template processing systems that link the contents of the CSS file in the HTML output stream even when only a subset of the CSS rules included in the CSS file is used the template processing system described herein includes only the CSS rules required for rendering the webpage. As a result the template processing system described herein reduces the amount of data included in the output stream and increases the efficiency of transferring the data stream across the network and the speed for rendering a webpage.

Network may be any network or combination of networks that can carry data communication. Such a network may include but is not limited to a local area network metropolitan area network and or wide area network such as the Internet. Network can support protocols and technology including but not limited to World Wide Web protocols and or services. Intermediate web servers gateways or other servers may be provided between components of the system shown in depending upon a particular application or environment.

Web server is an electronic device capable of sending receiving and storing resources. Resources can be provided over network . Resources include data inserted into hypertext markup language HTML pages word processing documents portable document format PDF documents images video and feed sources to name only a few. Web server also includes input data . Input data is data content that client requests from web server .

In an embodiment web server includes an interpreter . Interpreter executes templates compiled and template tree that are built by the template building module described below . When web server receives a hypertext transfer protocol HTTP request from client web server uses interpreter to generate an output stream that includes the layout of webpage and input data . In an embodiment output stream is an HTML output stream.

Backend server is a database or a storage repository that stores input data . In an embodiment web server retrieves input data from web server when it receives an HTTP request from client . Web server may use network to retrieve input data from backend server .

Client is an electronic computing device capable of requesting and receiving resources over network . Example clients are personal computers mobile communication devices e.g. smart phones tablet computing devices notebooks set top boxes game console embedded systems and other devices that can send and receive input data included in an output stream over network . To display input data client may execute an application such as a browser .

Template building module accesses template files and CSS files . Template files include templates . Template typically includes formatted code such as HTML markup code processing instructions expressions and custom attributes that are interpreted by template building module . Template may be statically modified by being loaded into an HTML editor or browser prior to the building and compilation process.

CSS files include CSS rules and may also include other data. CSS rules communicate to browser the format for displaying webpages . For example CSS rules may indicate the size and the type of a font the margins etc. of template included in webpage . Example CCS file such as stylesheets.css is below 

Example CCS rules included in stylesheets.css are .snippet textfont weight bold h1font size 24pt and divmargin 12px 

CSS rule includes a declaration and a selector. In an embodiment a declaration is included inside the curly brackets and defines the behavior of the HTML element in template that applies CSS rule . A selector identifies CSS rule in template . Example selectors included in stylesheets.css are .snippet text h1 and div .

In an embodiment the . included in the selector such as .snippet text is an identifier for CSS rule . The identifier indicates that CSS rule is triggered by a class attribute in template file that has the same name as the selector. For example element in template file Result.html triggers CSS rule .snippet text font weight bold 

In an embodiment a link element in each template file included in template file declares CSS file . In another embodiment a link element may reference a CSS file for all templates in template file . For example a element included in template file Results.html includes CSS file stylesheets.css. After template file declares CSS file templates in template file may access CSS rules included in CSS file .

Template building module includes a parser an optimizer and compiler . Parser parses the HTML syntax in each template included in template file verifies data types of the input parameters and paths to external files declared in template such as for example CSS file .

Parser also determines whether template is a transcluding template. Template transclusion occurs when a content of an element such as an HTML element in one template replaces content of an element from another template. When parser identifies a transcluding template parser verifies that the transcluded template file exists and is accessible to the transcluding template. Parser also determines whether the data type of the parameter in the transcluding template that receives the transcluded template matches the data type of the transcluded template. Template transclusion is described in detail in a non provisional U.S. patent application Ser. No. 13 253 780 and in a non provisional U.S. patent application Ser. No. 13 253 696 and is incorporated by reference in its entirety.

In an embodiment the tree representation is an abstract syntax tree AST . In one embodiment AST may be represented in a text file. In another embodiment AST may be a compiled binary representation. In an embodiment AST may be represented as a protocol buffer message. A person skilled in the art will appreciate that protocol buffer messages are structures that serialize structured data. Abstract template tree representation of the templates and protocol buffer messages are described in detail in a non provisional U.S. patent application Ser. No. 13 253 780 which is incorporated by reference in its entirety.

When parser identifies that transclusion occurs in template files parser generates a template AST for the transcluding template and the transcluded template.

Parser also parses CSS files . For example parser parses CSS rules in CCS file into a CSS AST. In a non limiting embodiment the edges of CSS tree represent selectors of a particular CSS rule . The nodes in CSS tree represent declarations of particular CSS rules as property value pairs. In an embodiment the nodes in CSS AST are associated with the nodes in template AST .

In an embodiment optimizer optimizes expressions and processing instructions in templates . Optimizer determines CSS rules that are included in template and attaches CSS rules to template AST . For example optimizer traverses template AST and CSS AST in parallel. When optimizer identifies a node in template AST that references CSS rule optimizer traverses CSS AST and identifies the node that includes a CSS rule . Once the node with CSS rule is identified optimizer attaches CSS rule to template AST . In one embodiment optimizer may create a node in template AST that includes the associated CSS rule . In another embodiment optimizer may copy CSS rule into a node in template AST that includes a reference to CSS rule .

In an embodiment optimizer traverses template AST and CSS AST in parallel. Each time optimizer accesses a node in template AST optimizer marks its position in the CSS AST. When optimizer returns to traversing CSS AST optimizer begins the traversal from the marked position. As a result optimizer reduces the number of times it needs to traverse template AST and the CSS AST to identify CSS rules that are included in template .

For example template file results.html described above includes two CSS rules declared in CSS file stylesheet.css. As described herein CSS file stylesheets.css includes three CSS rules . After optimizer traverses template AST of the template file results.html and CSS AST of stylesheets.css optimizer appends the CSS rules div and snippet.text to template AST .

Because CSS rules are attached to template AST each template includes CSS rules associated with that template and does not require the complete CSS file . For example in transclusion where the content of the transcluded template is inserted into the content of the transcluding template each template is displayed with its own set of CSS rules .

Compiler compiles the AST template into a binary template AST . Binary template AST includes template AST and appended CSS rules .

When web server receives HTTP request for webpage web server passes HTTP request to interpreter . Interpreter begins to generate output stream . Output stream is included in the HTTP response message that web server sends to client . In an embodiment output stream includes HTML that browser uses to display templates and input data .

Interpreter requests input data . In one embodiment interpreter requests input data stored on web server . In another embodiment interpreter requests input data from backend server . Interpreter traverses AST template and generates output stream by combining HTML syntax stored in the nodes of AST template with input data .

When interpreter traverses AST template interpreter aggregates CSS rules attached to AST template into one HTML element such as for example an HTML element. In an embodiment there is one element for each template . After interpreter generates the element interpreter inserts the element into output stream so that CSS rules included in element apply to the content displayed by the HTML included in template .

In an embodiment interpreter excludes repetitive CSS rales from the element. The exclusion reduces the amount of repetitive HTML parameters included in output stream . For example when interpreter determines that two CSS rules such as h1font size 24pt described above are included a element interpreter eliminates one of the CSS rules .

When interpreter processes transclusions interpreter includes CSS rules associated with the transcluded template inside the transcluding template. This allows browser to display the transcluded and transcluding template with their respective CSS rules . For example interpreter inserts the element into the sections of output stream for transcluding and transcluded template such that CSS rules apply to the respective template.

When generating output stream for transclusions interpreter excludes CSS rules included in template AST of the transcluded template using predetermined criteria. In one embodiment interpreter excludes CSS rules from the element associated with the transcluded template when CSS rules apply to the HTML elements that are outside of the transcluded template. In another embodiment interpreter excludes CSS rules that are applied to the transcluded template by the HTML selectors that are included in another section of template file .

Moreover interpreter eliminates the duplicates of CSS rules that are generated by multiple transclusions. For example identical CSS rules from different transclusions are inserted once into the element. In one example if the same transcluded template is inserted into the transcluding template multiple times interpreter generates a single set of CSS rules in the element and applies the element to the multiple transcluded template instances. In another example when CSS rules associated with multiple transcluded templates either in the same or different template files overlap interpreter includes one set of the overlapping CSS rules in the element.

After interpreter determines CSS rules that are included in the element interpreter generates output stream that includes templates filled with input data . Interpreter also inserts the element with included CSS rules in output stream such that template conforms to the layout specified by CSS rules . When interpreter completes generating output stream web server sends output stream to client .

Client receives output stream and generates webpage . In an embodiment browser translates output stream into webpage and displays webpage to a user.

At stage a template AST is generated. For example template building module accesses template file . Parser accesses templates included in template file and builds template AST from templates .

At stage a CSS AST is generated. For example parser accesses CSS file and builds CSS AST. As described herein the nodes of CSS AST include CSS rules . In an embodiment parser generates CSS AST that matches the structure of template AST .

At stage a template AST and CSS AST are traversed. For example optimizer traverses template AST and CSS AST.

At stage optimizer identifies a node in a template AST that includes a reference to a CSS rule. For example optimizer identifies a node in template AST that includes a reference to CSS rule . Once optimizer identifies the relevant node in template AST optimizer accesses the CSS AST and identifies the node in CSS AST that includes CSS rule associated with the relevant node.

At stage a CSS rule is attached to a template AST. For example optimizer attaches CSS rule to a node in template AST that includes a reference to CSS rule .

At stage optimizer determines whether the traversal is complete. For example optimizer determines whether it completed traversing nodes in template AST. If additional nodes exist the method proceeds to step . Otherwise to step .

At stage a template AST is compiled. For example compiler compiles template AST into a binary that may be processed on web server .

At stage a web server receives a request for a webpage. For example web server receives an HTTP message for client that requests webpage .

At stage web server retrieves input data. For example web server retrieves input data stored on web server or from backend server .

At stage interpreter generates a element for each template that includes CSS rules. For example interpreter generates a element for each template included in the requested webpage from AST template . As described herein each element includes CSS rules attached to template AST .

At stage interpreter excludes CSS rules according to predetermined criteria. For example interpreter eliminates duplicate CSS rules and overlapping CSS rules from each element as described herein.

At stage interpreter inserts the element into an output steam. For example interpreter generates output stream that includes templates and input data that is included in templates . Interpreter also inserts a element into output stream at a position such that CSS rules included in the element control the layout of associated template .

At stage a web server sends an output stream for display to a client. For example after interpreter completes generating output stream web server sends output stream for display on client .

At stage duplicate CSS rules are excluded. For example interpreter excludes duplicate CSS rules from the element associated with template .

At stage CSS rules that apply to elements outside of the transcluded template are excluded. For example interpreter does not include CSS rules into the element that exist in template file but apply to elements that are external to the transcluded template.

At stage CSS rules that apply to the transcluded template by external selectors are excluded. For example interpreter does not include CSS rules in the element that apply to a transcluded template by the HTML selectors external to the transcluded template.

At stage CSS rules that are generated by a repeated transclusion of the same template are excluded. For example interpreter does not include CSS rules in the element multiple times when the same template is transcluded multiple times.

At stage overlapping CSS rules are excluded. For example interpreter includes a single set of CSS rules in the element that overlap among multiple transcluded templates.

Web server and client can include one or more computing devices. According to an embodiment web server and client can include one or more processors one or more non volatile storage mediums one or more memory devices a communication infrastructure a display screen and a communication interface . Processors can include any conventional or special purpose processor including but not limited to digital signal processor DSP field programmable gate array FPGA and application specific integrated circuit ASIC . Non volatile storage can include one or more of a hard disk drive flash memory and like devices that can store computer program instructions and data on computer readable media. One or more of non volatile storage device can be a removable storage device. Memory devices can include one or more volatile memory devices such as but not limited to random access memory. Communication infrastructure can include one or more device interconnection buses such as Ethernet Peripheral Component Interconnect PCI and the like.

Typically computer instructions executing on web server or client are executed using one or more processors and can be stored in non volatile storage medium or memory devices .

Display screen allows results of the computer operations to be displayed to a user or an application developer.

Communication interface allows software and data to be transferred between computer system and external devices. Communication interface may include a modem a network interface such as an Ethernet card a communications port a PCMCIA slot and card or the like. Software and data transferred via communication interface may be in the form of signals which may be electronic electromagnetic optical or other signals capable of being received by communication interface . These signals may be provided to communication interface via a communications path. Communications path carries signals and may be implemented using wire or cable fiber optics a phone line a cellular phone link an RF link or other communications channels.

Embodiments also may be directed to computer program products comprising software stored on any computer useable medium. Such software when executed in one or more data processing device causes a data processing device s to operate as described herein. Embodiments of the invention employ any computer useable or readable medium. Examples of computer useable mediums include but are not limited to primary storage devices e.g. any type of random access memory secondary storage devices e.g. hard drives floppy disks CD ROMS ZIP disks tapes magnetic storage devices and optical storage devices MEMS nanotechnological storage device etc. .

The embodiments have been described above with the aid of functional building blocks illustrating the implementation of specified functions and relationships thereof. The boundaries of these functional building blocks have been arbitrarily defined herein for the convenience of the description. Alternate boundaries can be defined so long as the specified functions and relationships thereof are appropriately performed.

The foregoing description of the specific embodiments will so fully reveal the general nature of the invention that others can by applying knowledge within the skill of the art readily modify and or adapt for various applications such specific embodiments without undue experimentation without departing from the general concept of the present invention. Therefore such adaptations and modifications are intended to be within the meaning and range of equivalents of the disclosed embodiments based on the teaching and guidance presented herein. It is to be understood that the phraseology or terminology herein is for the purpose of description and not of limitation such that the terminology or phraseology of the present specification is to be interpreted by the skilled artisan in light of the teachings and guidance.

The Summary section may set forth one or more but not all exemplary embodiments as contemplated by the inventor s and thus are not intended to limit the present invention and the appended claims in any way.

The breadth and scope of the present invention should not be limited by any of the above described exemplary embodiments but should be defined only in accordance with the following claims and their equivalents.

