---

title: Secure password-based authentication for cloud computing services
abstract: Secure password-based authentication for cloud service computing. A request for cloud computing resource access includes a derivative password that contains a parameter that the recipient may extract in order to independently calculate the derivative password based on the parameter and a stored password which may then be verified against a known-to-be-correct password. Other systems and methods are disclosed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08959335&OS=08959335&RS=08959335
owner: Gemalto SA
number: 08959335
owner_city: Meudon
owner_country: FR
publication_date: 20120417
---
The present invention relates generally to cloud computing and more particularly to secure password based authentication for cloud computing resource access.

Cloud computing is becoming an increasingly popular mode for computerized access to both data and application programs. By using cloud computing users may provide a centralized depository for shared data a secure backup and file storage use of applications programs that can run on relatively higher speed cloud servers etc. By using cloud computing services users may increase the level of integrity of their data in that a third party with a dedicated focus on data processing is in charge of maintaining the security and integrity of data. Cloud computing users may feel relatively certain that their data is backed up and their security maintained by the cloud service provider CSP .

Another advantage for users of cloud computing services is the access to powerful application programs that may be prohibitively or unnecessarily expensive for a user to acquire and maintain. A cloud service provider may provide access to certain application programs either for a small fee or on some other revenue model that is advantageous to their users as compared to the users having the same or equivalent programs running locally on user machines.

One crucial aspect for the cloud computing model to work is that the data managed by the CSPs on behalf of their users must be secure and that only authorized individuals and entities may access application programs hosted in the cloud. Traditionally such user validation is performed using the username password model. The username passwords are transmitted to the API of the CSP by a client program executing on a client computer. Often the username passwords are embedded in requests made to the CSP by the client program.

The aforementioned authentication mechanism is prone to attack. Because client computers and client programs are used to formulate requests the client program is aware of the password and thus cannot be completely trusted. Furthermore the password is vulnerable to phishing attacks to snooping to poor user practices such as leaving passwords on notes to keystroke loggers etc.

However even with such vulnerabilities cloud service providers are reluctant to adopt more secure authentication methods such as digital signatures TLS mutual authentication or cryptographic hash that do not reveal passwords to the client programs because doing so would require expensive and cumbersome modifications to the cloud service infrastructure.

From the foregoing it will be apparent that there is still a need for an improved mechanism for secure password based cloud computing application programming interfaces without burdening cloud computing service providers with extensive modifications to cloud computing infrastructure.

In the following detailed description reference is made to the accompanying drawings that show by way of illustration specific embodiments in which the invention may be practiced. These embodiments are described in sufficient detail to enable those skilled in the art to practice the invention. It is to be understood that the various embodiments of the invention although different are not necessarily mutually exclusive. For example a particular feature structure or characteristic described herein in connection with one embodiment may be implemented within other embodiments without departing from the spirit and scope of the invention. In addition it is to be understood that the location or arrangement of individual elements within each disclosed embodiment may be modified without departing from the spirit and scope of the invention. The following detailed description is therefore not to be taken in a limiting sense and the scope of the present invention is defined only by the appended claims appropriately interpreted along with the full range of equivalents to which the claims are entitled. In the drawings like numerals refer to the same or similar functionality throughout the several views.

A technology is presented herein in which a mechanism is provided that enhances password security in cloud application interfaces without burdening cloud computing service providers with a requirement for extensive security modifications to cloud computing infrastructure.

While both the examples above and the discussion which follows discuss the presented technology in the context of personal computers e.g. the personal computer illustrated in the technology is equally applicable to other computing platforms such as but not limited to smart telephones and tablet computers.

Typically a web API such as API is defined in terms of request messages and associated response structures. Such requests must be authenticated. Therefore each API request includes a client authentication that proves to the cloud service provider that the client has been authorized to access the requested cloud resource .

In the scenarios of the user knows and enters the password on the personal computer for example in the client program or in a web browser that is interacting with the client program . The password is then transmitted to the cloud services with each API request for example in an HTTP request header and the cloud services verify the correctness of the password against a password database.

Because the client application forms and sends the request the client application has direct access to the password . Password based authentication is very weak and vulnerable to many forms of attack including phishing snooping user error such as leaving notes with passwords where visible keystroke logging etc.

The following steps are predicated on successful authentication of the user to the security device . This authentication is not shown in .

The client program determines the need for access to a cloud resource step . This may occur when a user makes a request to for example execute a software program residing in the cloud retrieve a computer file stored as a cloud resource or perform any certain task using the client program which needs to access a cloud resource .

The client program requests the security device to return the username and password of the user step . The request may be directed to a password applet of the security device .

The security device for example directed by instructions from the password applet computes a derivative password P derived from the user s password step . The user s password may be stored in NVM of the security device .

To compute the derivative password the password module uses a function F which takes the password and a parameter R as input Password 

Function F may be a pre specified one way cryptography function. R should change on each computation of the derived password. R could be a pseudo random number a time based number or any other number that is near guaranteed to not repeat. For example the derived password is a one way cryptographic hashing of R using the password as the key.

In an alternative embodiment multiple parameters are used in conjunction with the password to compute the value F. It is for example advantageous to combine a pseudo random number with a time stamp. Such a combination provides a powerful tool against replay attacks and brute force attacks attempting to foil a password based authentication mechanism.

P is a concatenation of R and F R Password Password wherein the word concatenation is used broadly to mean any method of combining R and F R Password such that R may be backed out of P . That could be a concatenation in a traditional sense where R is of some certain length. However it could be any other method of combining R and F in which R may be determined from the result.

Let s consider an example. If the password is loesenord and R is 333333 F R password F 333333 loesenord which for the purpose of the example could be A4FE337D. P would then be using strict concatenation 333333A4FE337D. If it is known that R is always the first 6 digits of a request the recipient may back out that R has the value 333333.

The client program then formulates the request including the username and the derived password P step .

The client computer then transmits the request to the cloud service executing on the cloud server step .

The cloud service determines R from the received request step . As in the example above if the received request contains the derivative password P and by convention R is the first 6 digits of the derivative password P the cloud service would determine that R equals 333333.

If multiple parameters are used to calculate the derivative password the cloud service determines each of the parameters by backing them out of the received request.

Having determined the value of the parameter s R the cloud service computes a derivative password P by applying the same parameter s R to the password for the user having the received username stored in a password database that the cloud service maintains step . The password database may be stored in the cloud server or as a separate network node.

If the password or password equivalent used by the client program to compute the derivative password is the same as the password or password equivalent stored on the cloud server the derivative password P computed by the cloud service would be the same as the received derivative password P .

The cloud service compares the received derivative password P and the computed derivative password P step . If the two passwords do not match access to the cloud resource is denied step . Some form of recovery from having an incorrect password maybe offered to the user e.g. to try using a different security device or inviting the user to use a password recovery mechanism.

As noted above in an alternative the cloud service may store the hash of the password in the password database . In that case the security device uses a one way hash of the password instead of the actual password as the basis for the derivative password. To compute the derivative password the client program would include the hash H P instead of P directly in the function F password A corresponding formula is used by the cloud service .

In yet another alternative the derivative password is computed using the public key of the cloud service Encr password A corresponding formula is used by the cloud service . The cloud service is further modified to compute the server side derivative password P by Decr In other regards this alternative operates in the same manner as previously discussed alternatives.

Alternatively the security device computes the derivative password P by encrypting the password and the timestamp using a secret key shared with the server. In this embodiment the security device is operated to compute the derivative password P by Encr password 

In yet another alternative the security device creates the derivative password P by encrypting the password using a secret key shared with the cloud service .

From the foregoing it will be apparent that a password based authentication mechanism has been provided. The described mechanism enhances security to password based authentication without adding a burden on cloud service providers to significantly redesign their authentication platforms.

Although specific embodiments of the invention have been described and illustrated the invention is not to be limited to the specific forms or arrangements of parts so described and illustrated herein. The invention is limited only by the claims.

