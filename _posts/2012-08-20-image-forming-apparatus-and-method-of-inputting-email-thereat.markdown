---

title: Image forming apparatus and method of inputting e-mail thereat
abstract: A method of inputting e-mail addresses at an image forming apparatus, the method including accessing a server storing member information about members who have contacted a user online, by using log-in information of the user; receiving the member information stored in the server from the server; generating a list of e-mail addresses of the members by using the received member information; and updating an address book stored in the image forming apparatus by using the list of generated e-mail addresses.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09137411&OS=09137411&RS=09137411
owner: SAMSUNG ELECTRONICS CO., LTD.
number: 09137411
owner_city: Suwon-Si
owner_country: KR
publication_date: 20120820
---
This application claims the priority benefit of Korean Patent Application No. 10 2011 0092223 filed on Sep. 9 2011 in the Korean Intellectual Property Office the disclosure of which is incorporated herein in its entirety by reference.

One or more embodiments of the following description relate to an image forming apparatus and a method of inputting e mails thereat.

Image forming apparatuses include office automation apparatuses e.g. multi function product MFP which are single apparatuses capable of performing a plurality of functions used at an office such as printing photocopying scanning faxing etc. An MFP may perform individual functions of various apparatuses such as a printer a scanner a photocopier and a facsimile or perform a combination of functions thereof. Recently image forming apparatuses having a network function to communicate with other terminals such as a PC are becoming popular.

Additional aspects and or advantages will be set forth in part in the description which follows and in part will be apparent from the description or may be learned by practice of the invention.

One or more embodiments provide an image forming apparatus and a method of inputting e mails thereat.

According to an aspect of one or more embodiments there is provided a method of inputting e mail addresses at an image forming apparatus the method including accessing a server storing member information about members who have contacted a user online by using log in information of the user receiving the member information stored in the server from the server generating a list of e mail addresses of the members by using the received member information and updating an address book stored in the image forming apparatus by using the list of generated e mail addresses.

According to another aspect of one or more embodiments there is provided at least one non transitory computer readable medium storing computer readable instructions to implement methods of one or more embodiments

According to another aspect of one or more embodiments there is provided an image forming apparatus including a network interface unit that accesses a server storing member information about members who have contacted a user online by using log in information of the user and receives the member information stored in the server from the server a list generating unit that generates a list of e mail addresses of the members by using the received member information and an updating unit that updates an address book stored in the image forming apparatus by using the list of generated e mail address.

As used herein the term and or includes any and all combinations of one or more of the associated listed items.

Hereinafter one or more embodiments will be described in detail with reference to the attached drawings.

The image forming apparatus refers to an apparatus that is connected to a host apparatus not shown and transfers and prints image signals onto a printing medium e.g. printing paper according to digital signals input by the host apparatus. The image forming apparatus may be a printer a scanner a multi function product MFP etc. Particularly an MFP refers to an office automation apparatus capable of simultaneously performing functions of various apparatuses such as a printer a photocopier a scanner and a facsimile. An MFP may perform individual functions of various apparatuses such as a printer a scanner a photocopier and a facsimile or perform those in combination of functions thereof.

Recently an MFP capable of solely performing a Scan To Email function which includes scanning a document by using a scanning function of the MFP attaching the scanned image to an e mail and transmitting the e mail to a desired user via a wired wireless or hybrid network has been introduced. Here one of ordinary skill in the art will understand that the term Scan To Email may be replaced with other terms having the same definition.

In the related art when transmitting a scanned image to members by using the Scan To Email function of the image forming apparatus it is generally necessary to input every character of e mail addresses of the members by using a user interface UI of the image forming apparatus .

For example e mail addresses may be input by using hardware buttons included in the image forming apparatus by using a software keyboard displayed on a graphic user interface GUI or a touch screen of the image forming apparatus or by browsing an address book stored in the image forming apparatus in advance.

In detail when inputting e mail addresses by using hardware buttons of the image forming apparatus for example if a number of characters in members is large a task of inputting of every e mail address one by one is cumbersome and repetitive. Furthermore even when using a software keyboard of a GUI or a touch screen of the image forming apparatus for example it is still necessary to input every e mail address one by one. Particularly it is very inconvenient to input e mail addresses where a size of a corresponding GUI screen is small. Furthermore even when using an address book stored in the image forming apparatus in advance a task of adding e mail addresses to the address book is necessary and thus it is still necessary to perform a cumbersome and repetitive task as described above.

However the image forming apparatus according to one or more embodiments directly acquires member information about the members from the server by communicating with the server and extracts e mail addresses from the received member information. The member information may include for example a list of friends stored in the server or e mail addresses about the members but not limited thereto. Therefore a cumbersome and repetitive task of inputting e mail addresses one by one as in the related art may be avoided.

In one or more embodiments the server refers to a server that provides a social network service SNS an e mail service and or a message service but not limited thereto. For example the server may correspond to a server that provides an SNS service via a website such as Facebook http www.facebook.com Twitter http twitter.com etc. Furthermore the server may correspond to a server that provides an e mail service via a website such as Naver http www.naver.com Google http www.google.com AOL http www.aol.com etc. However the server is not limited thereto and the server may include any server that provides an SNS an e mail service and or a message service and etc.

The server as described above stores member information about the members with whom a user has exchanged messages or e mails online. Here the members includes at least one member. In detail the server stores information about online personal connections of the user or member information about the members recorded in an e mail history of the user . Here the term of the personal connections may be called various terms such as friends or followers according to types of the server therefore the term of the personal connections are not limited. In other words the server stores member information about the members who have contacted or communicated with the user online.

In other words the image forming apparatus according to an embodiment communicates with the server as described above and directly receives information required to acquire e mail addresses of the members . Therefore the user is not inconvenienced with having to input every character of e mail addresses one by one as in the related art.

Hereinafter interactions between each of components of the image forming apparatus according to an embodiment and the server will be described in detail.

Here the authentication unit the requesting unit the list generating unit and the updating unit may correspond to a processor. Such a processor may be embodied as an array of a plurality of logic gates or a combination of a universal microprocessor and a memory storing programs that may be executed on the microprocessor. Furthermore one of ordinary skill in the art will understand that such a processor may be embodied as other types of hardware.

To prevent the subject matter of an embodiment from being obscured only hardware components related to an embodiment are shown in . However one of ordinary skill in the art will understand that the image forming apparatus may further include universal hardware components other than the hardware components shown in such as a storage unit not shown a printing unit not shown etc.

The UI unit receives various information from the user and reports a result of processing the information at the image forming apparatus by displaying the result of processing the information. In other words the UI unit includes an input unit not shown for receiving information from the user and a display unit not shown to show a result of processing the received information to the user .

The UI unit receives information from the user via an information input device such as a keyboard a mouse hardware buttons a touch screen e.g. a software keyboard of a GUI or a voice recognizing device. Furthermore the UI unit reports a result of processing received information at the image forming apparatus to the user by using a device for displaying visual data e.g. an LCD screen an LED screen a gradation displaying device etc. or a device for providing auditory information e.g. a speaker .

In detail the UI unit receives user input of various information necessary to receive e mail address information from the sever . For example when performing the Scan To Email function according to an embodiment the UI unit may receive e mail address information from the user .

Configurations of the screens displayed on the UI unit as shown in are merely examples and an embodiment is not limited thereto. Furthermore i where the Scan To Email function is initiated as shown in reception of e mail address information from the user may be initiated. However an embodiment is not limited thereto. One of ordinary skill in the art will understand that if the user only wants to add e mail address information to an address book a screen including the SNS button as shown in may be displayed without the selection of the Scan To Email function as shown in so that the user may start accessing the server .

Furthermore one of ordinary skill in the art will understand that any of various types of buttons or functions to start accessing of the server like the SNS button shown in may be arranged according to an embodiment.

Referring back to the UI unit receives selection of the server and log in information corresponding to the selected server from the user . Selection of a type of the server refers to selection of one of servers providing websites such as Facebook Twitter Naver Daum and Google as described above.

Referring back to when the user inputs a type of the server and log in information via the screen displayed on the UI unit as shown in the network interface unit accesses the selected server by using the input log in information. However before the network interface unit accesses the server authentication is performed as described below.

The authentication unit attempts authentication to the server by using the input log in information. If authentication is successful the network interface unit accesses the server .

Furthermore when authentication is successful and connection to the server is established the requesting unit requests member information about the members stored in the connected server . As a result of such request the network interface unit receives member information stored in the server .

The authentication unit attempts authentication to the server by using an authentication module that communicates via a protocol corresponding to the type of the server selected by the user . Furthermore the requesting unit requests member information from the server by using an authentication module that communicates via a request protocol corresponding to the type of the server selected by the user .

Each of the authentication modules and each of the request modules correspond to each of types of the server . For example the authentication module A and the request module A may correspond to a server providing an SNS such as Facebook whereas the authentication module C and the request module C may correspond to a server providing an e mail service such as Naver. Therefore types of the server that are accessible may vary according to types of authentication modules and request modules included in the authentication unit and the requesting unit .

The authentication modules and the request modules may be added by upgrading firmware of the image forming apparatus or via module installation. In other words a new authentication module may be added to an authentication module installation space of the authentication unit and a new request module may be added to a request module installation space of the requesting unit . When a new authentication module and a new request module are added as described above types of the server that may be selected by a user may increase. On the contrary if an authentication module and a request module are deleted types of the server that may be selected by a user may decrease.

The network interface unit provides information to the server by using an authentication module and a request module and receives information transmitted by the server . Detailed description thereof will be given below with reference to .

In an operation the UI unit of the image forming apparatus receives log in information that is a user ID and a password from the user .

Operations through correspond to operations performed between an authentication module of the authentication unit of the image forming apparatus and the server . Here the authentication module and the server may perform authentication by using open authorization OAuth which is a standard authentication method developed based on open application programming interface Open API . Although definition of an API for authentication to the server and definition of an API to receive member information vary according to a type of the server a representational state transfer REST based protocol is generally employed. Therefore authentication may be performed as shown in the operations through of . However the authentication shown in the operations through is only an example for convenience of explanation and one of ordinary skill in the art will understand that methods for authentication according to an embodiment are not limited thereto.

In the operation as the authentication module transmits the user ID and the password which are log in information of the user to the server . Here authentication of the user is performed at the server .

As described above when authentication is successful between the authentication module of the authentication unit and the server through the operations through the authentication module accesses the server by using the granted access token.

Operations through correspond to operations performed between a request module of the requesting unit of the image forming apparatus and the server .

In the operation the request module requests member information from the server . For example the member information may correspond to a list of friends stored in the server .

In the operation the request module receives member information such as a list of friends from the server .

As described above the request module of the requesting unit receives member information about the members who have contacted with the user stored in the server from the server .

The request module sends a request to the server by using a uniform resource locator URL https graph.facebook.com User ID friends access token access token for example. The server transmits a response as shown in to the request module.

Next based on the result as shown in the request module sends a request to the server by using a URL https graph.facebook.com Friend s User Id access token access token . The server responds by transmitting the result as shown in to the request module.

Referring to the response as shown in information about an e mail address of a friend such as email bigboy google.com is acquired as a result of the request of the request module. Here since a user ID of the friend is in the form of an e mail address in the server providing a Facebook website e mail address information may be directly acquired from the user ID of the friend.

In Facebook is used as an example for convenience of explanation and one of ordinary skill in the art will understand that member information may be received from other types of websites by using request methods corresponding to types of the server .

Referring back to the network interface unit accesses the server storing member information by performing operations as described above and receives member information stored in the server .

The list generating unit generates a list of e mail addresses of the members by using the received member information. The list generating unit generates the list by parsing e mail addresses of the members from the received member information.

In detail the list generating unit includes the parsing unit which parses e mail addresses of the members from member information received based on a format of an e mail addresses and the e mail address generating unit which generates e mail addresses of the members based on a result of the parsing. The list generating unit generates a list by using the e mail addresses generated by the e mail address generating unit .

The parsing unit parses the response received from the server as shown in . The response indicates member information. In other words the parsing unit operates together with the requesting unit parses a response received from the server as a result of a request of the requesting unit and extracts information to be used by the e mail address generating unit to generate e mail addresses.

In information about an e mail address of a friend such as email bigboy google.com is shown as a result of the final parsing. The e mail address generating unit generates e mail addresses of the members by using e mail addresses of friends such as email bigboy google.com which is acquired as a result of the parsing.

However according to types of the server the server may directly store information about e mail addresses of the members or instead of storing information about e mail addresses user IDs of the members to log into the server may be in the form of e mail addresses. Furthermore according to types of the server user IDs of the members to log into the server may not be in the form of e mail addresses. According to an embodiment a list of e mail addresses may be generated in any of the cases as stated above.

In detail the e mail address generating unit determines whether the parsed member information includes e mail addresses or not.

If it is determined that the member information includes e mail addresses the e mail address generating unit generates e mail addresses based on e mail addresses included in the member information.

However if it is determined that the member information does not include e mail addresses the e mail address generating unit generates e mail addresses by using user IDs of the members included in the received member information. In this case user IDs of the members are either in the form of e mail address or not in the form of e mail address.

In this case the parsing unit parses the response from the server which indicate member information again. In other words the parsing unit parses user IDs of the members . As a result of parsing the response if user IDs are in the form of e mail addresses the e mail address generating unit generates e mail addresses by using the user IDs. If user IDs are not in the form of e mail addresses the e mail address generating unit generates e mail addresses by using the user IDs and a host name or a domain name of a website provided by the server .

In an operation the parsing unit parses a response from the server that indicates received member information.

In an operation the e mail address generating unit determines whether parsed member information includes e mail addresses or not. If it is determined that the parsed member information includes e mail addresses the process proceeds to an operation in which the e mail address generating unit generates e mail addresses based on e mail addresses included in the member information and the list generating unit generates a list of e mail addresses by using the generated e mail addresses. If it is determined that parsed member information does not include e mail addresses the process proceeds to an operation .

In the operation the parsing unit parses the response from the server which indicates member information again. In other words the parsing unit parses user IDs of the members .

In an operation the e mail address generating unit determines whether the parsed user IDs are in the form of e mail addresses or not. If the parsed user IDs are in the form of e mail addresses the process proceeds to the operation in which the e mail address generating unit generates e mail addresses by using the user IDs and the list generating unit generates a list of e mail addresses by using the generated e mail addresses. If the parsed user IDs are not in the form of e mail addresses the process proceeds to an operation .

In the operation the e mail address generating unit generates e mail addresses by using user IDs and a host name or a domain name of a website provided by the server and the list generating unit generates a list of e mail addresses by using the generated e mail addresses. Here the e mail address generating unit generates e mail addresses in the form of User ID host.domain for example.

In the operation the list generating unit generates a list of e mail addresses by using the generated e mail addresses.

Referring back to the parsing unit also parses recent date information and favorite information from the response from the server . The list generating unit generates a list of e mail addresses by adding recent date information and favorite information to e mail addresses. Such recent date information and favorite information refer to information about recently contacted friends recent e mail transmission dates recorded in an e mail history friends added to a favorite list etc. and are included in received member information.

Referring back go the UI unit displays the list of e mail addresses generated by the list generating unit . The user may select and input desired e mail addresses in the list of e mail addresses displayed on the UI unit . In other words the user may select and input e mail addresses that the user desires to add to an address book stored in the image forming apparatus from the list of e mail addresses displayed on the UI unit .

Here since the list of e mail addresses includes recent date information and favorite information as described above the list of e mail addresses displayed on the UI unit may be displayed in a particular arrangement such as an all list a recent list a favorite list etc. according to selection by the user .

The updating unit updates the address book stored in the image forming apparatus by using the list of e mail addresses generated by the list generating unit . Here as described above the updating unit updates the address book by adding e mail addresses selected by the user to the address book.

Referring to the user may select desired e mail addresses by clicking a check button with respect to the desired e mail addresses and clicking an apply button . When the apply button is clicked the updating unit updates an address book by adding the selected e mail addresses to the address book. Here the e mail addresses desired by the user may refer to e mail addresses to which the user desires to transmit a scanned document by using the Scan To Email function or e mail addresses that the user wants to add to the address book.

Furthermore the user may select to display the list of e mail addresses in an arrangement such as an all list a recent list or a favorite list by using an arrangement button . Configuration of the screen displayed on the UI unit as shown in is merely an example and an embodiment is not limited thereto.

When the user wants to input e mail addresses by using member information stored in the server the user may input the e mail addresses by selecting the Scan To Email function operation selecting an SNS operation inputting log in information and a type of SNS operation and selecting desired e mail addresses operation on the screen displayed on the UI unit .

Referring back to the scanning unit generates a scanned image by scanning a document to be transmitted via e mail. The Scan To Email function is a function to transmit a document scanned by the scanning unit via e mail. The scanning unit is a device having the same functions as a general scanner. Since the process of generating a scanned image by scanning a document is obvious to one of ordinary skill in the art detailed description thereof will be omitted.

A storage unit not shown of the image forming apparatus stores results of processes performed by the components of the image forming apparatus . In other words the storage unit may store a list of generated e mail addresses. According to an embodiment a volatile memory may be used to store a list of generated e mail addresses so that the list of generated e mail addresses may be automatically deleted after the e mail addresses are used.

In an operation the network interface unit accesses the server which stores member information about members who have contacted the user online by using log in information of the user .

In an operation the network interface unit receives member information stored in the server from the server .

In an operation the list generating unit generates a list of e mail addresses of the members by using the received member information.

In an operation the updating unit updates an address book stored in the image forming apparatus by using the generated list of e mail addresses.

The above described embodiments may be recorded in computer readable media including program instructions to implement various operations embodied by a computer. The media may also include alone or in combination with the program instructions data files data structures and the like. The program instructions recorded on the media may be those specially designed and constructed for the purposes of embodiments or they may be of the kind well known and available to those having skill in the computer software arts. Examples of computer readable media include magnetic media such as hard disks floppy disks and magnetic tape optical media such as CD ROM disks and DVDs magneto optical media such as optical disks and hardware devices that are specially configured to store and perform program instructions such are read only memory ROM random access memory RAM flash memory and the like. The computer readable media may also be a distributed network so that the program instructions are stored and executed in a distributed fashion. The program instructions may be executed by one or more processors. The computer readable media may also be embodied in at least one application specific integrated circuit ASIC or Field Programmable Gate ARRAY FPGA which executes program instructions. Examples of program instructions include both machine code such as produced by a compiler and files containing higher level code that may be executed by the computer using an interpreter. The above described devices may be configured to act as one or more software modules in order to perform the operations of the above described embodiments or vice versa.

While this invention has been particularly shown and described with reference to one or more embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the invention as defined by the appended claims. One or more embodiments should be considered in descriptive sense only and not for purposes of limitation. Therefore the scope of the invention is defined not by the detailed description of the invention but by the appended claims and all differences within the scope will be construed as being included in the invention.

