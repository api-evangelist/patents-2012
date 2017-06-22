---

title: Method for the generation of a code, and method and system for the authorization of an operation
abstract: The present invention relates to a method for generating a code and a method comprising the authorization of an operation carried out by a client on a first server. A second server generating an authorization code according to an encoding method is involved in the authorization. The operations can be transactions, access to a web page, user-to-user payments, user-to-business payments, online user-to-business payments, cash withdrawal in automated teller machines, etc.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08930694&OS=08930694&RS=08930694
owner: Banco Bilbao Vizcaya Argentaria, S.A.
number: 08930694
owner_city: Madrid
owner_country: ES
publication_date: 20120912
---
This application is filed under the provisions of 35 U.S.C. 119 a and claims priority to European Patent Application No. 12382313.0 filed on Aug. 2 2012 in the name of Francisco FERNANDEZ DE TORRES and entitled METHOD FOR THE GENERATION OF A CODE AND METHOD AND SYSTEM FOR THE AUTHORIZATION OF AN OPERATION which is incorporated herein by reference in its entirety.

The present invention relates to a method for generating a code and a method comprising the authorization of an operation carried out by a client on a first server. A second server generating an authorization code according to an encoding method is involved in the authorization. The operations can be transactions access to a web page user to user payments user to business payments online user to business payments cash withdrawal in automated teller machines signing operations etc.

The development and social impact of mobile devices have led to the development of applications for mobiles in the business environment such as those which make business transactions.

Some mobile devices include software applications which allow capturing QR codes or quick response codes. The application captures the code decodes it and transmits the decoded information to a remote server as a request for information about materials for example such as a purchase order etc. Such operations are merely an exchange of information and do not include any type of business transaction operation.

PayPal is a text only one way payment system that can be installed in mobile devices. The system works such that information about the payer and the amount to be paid is sent from the mobile device to a server. An operator calls the user of the mobile device after this information is sent so that the user can authorize the transaction.

Obopay is a mobile device application the use of which allows a transaction from an Obopay account to a business. The use depends on the proprietary software installed in the device with the drawback that not all devices are prepared to run Obopay software.

Other forms of payment using mobile devices comprise the use of barcodes communication with the merchant by means of wireless technology such as Bluetooth or infrared etc. The main drawback is the required use of additional hardware and software both in the client and in the merchant.

However there are no applications which allow the exchange of funds in a fast and comfortable manner for the user and assure 100 security in said operations and transactions. In addition the disclosure of this invention allows in addition to performing transactions identifying and signing operations in alternative channels that prevent the typical attacks using the means that have been widespread up until now.

The present invention solves the technical problems described above by means of a method for generating a code according to claim an authorization method for authorizing an operation according to claim and an authorization system for authorizing an operation according to claim . The dependent claims define preferred embodiments of the invention.

A first aspect of the invention is a method for generating a code characterized in that it comprises the steps of 

Encrypting or enciphering must be understood in the context of the present invention by its conventional meaning i.e. applying an algorithm for converting the original information into secret information. A message susceptible to being encrypted undergoes at least one transformation by means of a key. The original message is transformed into a binary string by means of the key. The decrypting entity must have the decryption key to obtain the original message.

Encoded or encoding must be understood in the context of the present invention by its conventional meaning i.e. applying an algorithm for representing information. The Base64 encoding system for example which takes groups containing 6 bits and forms characters can be used to represent a series of binary symbols in one character. It can be seen graphically as follows 

The method for generating a code generates a code from a character string of information such that it is secure in the sense that it does not contain sensitive or vulnerable information that can be used by a third party intercepting the code. This code can be used in an authorization method for authorizing an operation such as that described below in the second aspect of the invention.

In a second aspect of the invention the invention presents an authorization method for authorizing an operation implemented in a system comprising 

In the authorization method a user of a client agrees on an operation with a user of a first server. This operation can be a cash transaction between bank accounts of the users. The authorization process for authorizing the operation starts by means of requesting the second server a code after which the code is sent to the first server and from the latter it is transferred to the client by means of capturing a QR image or by means of sending via NFC near field communication technology.

A third aspect of the invention is an authorization system for authorizing an operation comprising the following entities 

A fourth aspect of the invention is a computer program or application characterized in that it comprises program code means for performing the steps of a method according to the first aspect of the invention when said program works in a computer or program code means for performing the steps of a method according to the second aspect of the invention implemented by the client or program code means for performing the steps of a method according to the second aspect of the invention implemented by the first server or program code means for performing the steps of a method according to the second aspect of the invention implemented by the second server.

A fifth aspect of the invention is a medium that can be read by a computer or processor of any type including a server processor smartphone mobile telephone tablet etc characterized in that it contains a computer program or application comprising program code means for performing the steps of a method according to the first aspect of the invention when said program works in a second server or a computer program or application comprising program code means for performing the steps of a method according to the second aspect of the invention when the steps are implemented by the client or a computer program or application comprising program code means for performing the steps of a method according to the second aspect of the invention implemented by the first server or a computer program or application comprising program code means for performing the steps of a method according to the second aspect of the invention implemented by the second server.

All the features and or steps of the methods described in this specification including the claims description and drawings can be combined in any manner with the exception of combinations of such mutually exclusive features.

The code is a set of signs and rules which allows formulating and comprehending a message. In the scope of the present invention the message is the character string of W characters that is to be encoded and the code can be a two dimensional code a barcode a hexadecimal code a code in the form of an image etc.

In a particular embodiment of the method for generating a code the encoding method of step f. is a method for generating a QR code quick response code which can advantageously be used to be captured by means of image capture for example by scanning from a device comprising an image sensor.

In one embodiment of a method for generating a code according to the invention the additional information in step e. comprises at least 

In one embodiment of the invention the method for generating a code comprises the following steps prior to step a. 

The information can be encrypted by means of a CBC encryption mode or any other encryption mode and can be encoded in Base32.

By using the CBC encryption mode a 128 bit block binary is obtained. When subsequently encoding in Base32 25 characters are obtained for every 128 bit block.

Therefore in a particular embodiment of the method for generating a code according to the invention in step d. relating to the action of splitting the string of Y characters into a public string of M characters and a private string of Y M characters the number M 26 is chosen which number advantageously separates a whole 25 bit block and a small part from the rest of the string which increases security and makes it impossible to decrypt the information without the public and private part of the information. If less than a whole block is taken a third party could decode and decrypt the information.

An authorization system for authorizing an operation according to the invention comprises the following entities depicted by way of example in 

In a particular embodiment the system is characterized in that the first server is in communication with the second server through a first communication network and the client is in communication with the second server through a second communication network .

In a particular embodiment the system is characterized in that the first server is in communication with the second server through a first communication network and the client is in communication with the second server through the same first communication network .

In a particular embodiment step g. the second server running the operation is implemented after step f. .

In one embodiment in step g. running the operation is performed if a single use key sent from the client to the second server is correct where a correct single use key is a single use key 

In a particular embodiment the string with data about the operation is the string which is provided in step a. relating to the action of providing a string of information of the method for generating a code according to the invention.

In a particular embodiment of the invention the authorization method comprises steps e1. and e2. between steps e. and f. . Steps e1 and e2 comprising 

In this particular embodiment security of the method advantageously increases because vulnerable information is not sent in the code and relevant information for carrying out the operation is only received in the client .

In a particular embodiment the method for generating a code stores the private string of Y M characters which together with the public string of Y characters represents information that allows the second server to obtain all the necessary data about the operation such that they are enough to provide the information about the operation to the client so that the latter ends the authorization of the operation.

The client transferring the code from the first server to the client is advantageously implemented by means of capture by the client which capture can be an image capture of a QR code or capture of a code by means of NFC technology.

In a particular embodiment the operation is a bank transfer operation from an account associated with the client to a bank account associated with the first server . In the particular embodiment in which steps e1 and e2 are implemented it is advantageously not necessary to send relevant information in the code . It is therefore possible to generate a code which by itself does not give interpretable information and such that the relevant information is sent only to the client in step e2.

In the particular embodiments of the invention the client the first server and the second server have the encoding tables and the encryption and decryption keys which prevents them from being sent over a communication channel.

In the particular examples described below the client can be any one of a tablet a robot a computer a smartphone or any other device with the capacity to communicate through a communication network. In different examples the device is suitable for browsing web pages communicating with the first server and communicating with the second server . The client can be used by a user or machine.

This embodiment corresponds for example to the example of a collector requesting a transfer to a payer. The payer and collector devices can be used by two users.

3.0. The first server collector mobile device starts the transaction and labels it as a payment operation with QR code.

3.1. The first server collector mobile device generates an XML Extensible Markup Language file comprising 

The method is performed in the client first server and second server as the result of an application running in each one. The internal identifier and the internal key correspond to the internal and proper identifier and key of each application running in each entity .

Advantageously the random number included allows the string to always be different from the rest even for operations of the same account holder and for the same amount and account. In a particular example the random number that is generated and added to the beginning of the string is 10 digits long.

3.8. The second server encrypts the string generated using an AES Advanced Encryption Standard encryption scheme in CBC cipher block chaining mode and the result is encoded in Base32 with its own conversion table which advantageously increases encoding security.

The public part will be sent in a QR code whereas the private part resides in the second server . Therefore advantageously even though a third party tries to decode and decrypt the content of the string of the QR code he she cannot do so because he she does not have the whole string to decode and decrypt only the first 30 characters.

3.10. The second server generates a database identifier used to locate the private information stored in the database.

In one embodiment this string is as follows bbvaqr bbva pp ADFKERORMVMOECALSPPORJWIDOLSKM id data base 329873 .

Advantageously since the prefix is recognized by the receiver of the QR code it directly accesses the application running in the client for the correct interpretation of the QR code .

In a case in which the code is read from the client using a standard BIDI code reading application and the application is installed the application is run in that moment.

Advantageously in this embodiment the QR code always contains the same amount of information and therefore the density thereof never changes regardless of the size of the complete information because the first 30 characters are always sent and the rest is stored in the database. The QR code therefore does not contain sensitive data about the transaction.

3.13. The second server sends the image of the QR code to the collector mobile device and the latter displays it on the screen. In this embodiment the QR has a validity for a predetermined time for example 48 hours which advantageously prevents being able to reuse the code. 3.14. The client or payer mobile device scans the image of the QR code using the image sensor. In an alternative embodiment instead of scanning the QR code it is sent to the e mail of a payer user handling the client or payer mobile device. 3.15. The client or payer mobile device obtains the content of the QR code. 3.16. The client or payer mobile device applies a URL encode method to the content and sends it as a parameter in a call to a web service for example a REST Representational State Transfer service for requesting validation in the second server with the following parameters 

The receiving mode is the manner in which the second server sends the data about the transaction to the device or client or payer entity once the QR code is validated.

The internal identifier and the internal key belong to the client and serve to uniquely identify the client. Similarly the first server or collector mobile device also comprises an internal identifier and an internal key for uniquely identifying it.

In this particular embodiment the method for generating a code stores the private string of Y M characters which together with the public string of Y characters represents information that allows the second server to obtain all the necessary data about the operation for providing the information about the transaction to the client so that the latter authorizes the operation.

The public part will be sent in a QR code whereas the private part resides in the second server . Therefore advantageously even though someone tries to decode and decrypt the content of the string of the QR code he she cannot do so because he she does not have the whole string to decode and decrypt only the first 30 characters.

4.7. The second server generates a database identifier used to locate the private information stored in the database.

In one embodiment this string is as follows bbvaqr bbva pp ADFKERORMVMOECSKDOOEIWUURMWKWJ id data base 329873 

Advantageously in this embodiment the QR code always contains the same amount of information and therefore the density thereof never changes regardless of the size of the complete information because the first 30 characters are always sent and the rest is stored in the database. The QR code therefore does not contain data about the transaction.

4.10. The second server sends the image of the QR code to the POS terminal of the business and the latter displays it on the screen. In this embodiment the QR has a validity for a predetermined time for example 5 minutes which advantageously prevents being able to reuse the code. The second server verifies whether payment has been made until it is made or at most until the predetermined time lapses. 4.11. The client or payer mobile device scans the image of the QR code using the image sensor. 4.12. The client or payer mobile device obtains the content of the QR code. 4.13. The client or payer mobile device applies a URL encode method to the content and sends it as a parameter in a call to a web service for example a REST Representational State Transfer service for requesting validation in the second server with the following parameters 

The method is performed in the client first server and second server as the result of an application running therein. The internal identifier and the internal key correspond to the internal and proper identifier and key of the application running in each entity .

The receiving mode is the manner in which the second server sends the data about the transaction to the device or client or payer entity once the QR code is validated.

In this particular embodiment the method for generating a code stores the private string of Y M characters which together with the public string of Y characters represents information that allows the second server to obtain all the necessary data about the operation for providing the information about the transaction to the client so that the latter authorizes the operation. Advantageously vulnerable information such as account number etc. is sent exclusively and directly to the client by means of the https protocol such that a possible third party seeking to intercept the information is not capable of reading it.

4.15. The client or payer mobile device receives the data about the transaction and checks that they are correct 

In this example the first server is a computer for connecting to internet and the client for example a smartphone mobile device accesses a web page hosted in the second server through the computer. The smartphone mobile device can be used by a user. The client can be any one of a tablet robot computer or any other device suitable for browsing on web pages. The client can be used by a user or machine.

In this example security of the client advantageously increases in the context of electronic operations conducted over internet.

The QR codes are used as means for transmitting sensitive or vulnerable information in the process of signing or authorizing operations and thereby preventing a user handling the first server from having to enter passwords with the risk of being intercepted and copied by a third party.

In this embodiment the authorization of the operation is closed and completed in an alternative device and the problems that may result from a situation in which the first server or computer being used to connect to internet and carry out the main relationship of a user of the computer or first server and of the client with the second server for example a bank is somehow comprised by a virus man in the middle etc. are advantageously prevented.

As an additional alternative for further security the user can enter a pin code in the smartphone mobile device to complete the signing in the system.

5.0. The first server computer starts an operation for signing operations and labels it as a signing operation with QR code.

The public part will be sent in a QR code whereas the private part resides in the second server . Therefore advantageously even though a third party tries to decode and decrypt the content of the string of the QR code he she cannot do so because he she does not have the whole string to decode and decrypt only the first 30 characters.

5.7. The second server generates a database identifier used to locate the private information stored in the database.

Advantageously in this embodiment the QR code always contains the same amount of information and therefore the density thereof never changes regardless of the size of the complete information because the first 30 characters are always sent and the rest is stored in the database. The QR code therefore does not contain data about the transaction.

5.10. The second server sends the image of the QR code to the first server computer and the latter displays it on the screen. In this embodiment the QR has a validity for a predetermined time for example 5 minutes which advantageously prevents being able to reuse the code. The second server verifies whether the operation has been signed until it is done or at most until the predetermined time lapses. 5.11. The client smartphone mobile device scans the image of the QR code using the image sensor. 5.12. The client smartphone mobile device obtains the content of the QR code. 5.13. The client smartphone mobile device applies a URL encode method to the content and sends it as a parameter in a call to a web service for example a REST Representational State Transfer service for requesting validation in the second server with the following parameters 

The method is performed in the client first server and second server as the result of an application running therein. The internal identifier and the internal key correspond to internal and proper identifier and key of the application running in each entity .

The receiving mode is the manner in which the second server sends the data about the operation for accessing the web page to the client smartphone mobile device once the QR code is validated.

In this particular embodiment the method for generating a code stores the private string of Y M characters which together with the public string of Y characters represents information that allows the second server to obtain all the necessary data about the operation such that they are enough for providing the information about the operation to the client so that the latter authorizes the operation. In this particular embodiment these data are all the details of the operation to be signed. Advantageously when receiving the data about the operation to be signed in the client the user of the client will be aware that a signing operation has started being able to not end the operation if said operation was not started by him her. Security therefore increases.

The advantage of this example of the method is to offer a user means for optimizing the time he she has available in transactions or operations which require a physical interaction such as cash withdrawals and deposits in automated teller machines.

The client registers operations that are ready and pending completion in the second server and once the client operates with a first server or automated teller machine the process of terminating the operation is triggered through a QR code.

The first server or automated teller machine must be suitable for displaying by some display means a QR code generated by the second server .

The following steps depicted in will therefore be performed for generating the QR of each second server or client 

In a particular embodiment this request . is sent from the automated teller machine in another particular and non limiting embodiment this request . is made from a central server not depicted in .

 Num 43252 identifier automated teller machine 11223344455 location Plaza Maria Soledad Torres Acosta coordinates 3453454564645 4565436456456 

At this point the code is visible in the automated teller machine either in display means or printed out in an external casing of the automated teller machine . From the time that the code is available and visible a client can scan or capture it without time restrictions.

6.4 At some time the client using the application starts a cash withdrawal operation that remains pending in the server .

6.5 At some time for example not more than two hours later the client captures the QR code of the automated teller machine with the image sensor. This action triggers the start of the process for terminating the operation that the client started in point 6.4 and remained pending. 6.6. The client obtains the content of the code . He she applies the URL encode method and sends it as a parameter in a call to the REST service for the corresponding validation in the second server with the following parameters 

Entering credentials into the automated teller machine that can be intercepted by a third party is advantageously prevented in this embodiment.

