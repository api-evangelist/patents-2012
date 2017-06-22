---

title: Method for secure storing of a data file via a computer communication network
abstract: A computer implemented method, server computer and computer program for securely storing a data file via a computer communication network. The method includes: providing a computer device of a user with code for providing a unique user name for the user; asking the user for a password; generating an asymmetric key pair for the user having one public key and one private key; encrypting the private key via the hash of the password; generating a file-specific symmetric key specific for the data file; encrypting the data file via the file-specific symmetric key; encrypting the file-specific symmetric key via the public key of the user; where the code is executed by a web browser on the computer device. The server is then receiving the encrypted data file, the encrypted file-specific symmetric key, the encrypted private key of the user and the public key of the user from the computer device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09582678&OS=09582678&RS=09582678
owner: INVENIA AS
number: 09582678
owner_city: Tromso
owner_country: NO
publication_date: 20120419
---
The present invention relates to a method for secure storing of a data file via a computer communication network and a server computer and a computer program implementing the method.

There are several known technologies for online storing and sharing of data files. For example a service may provide server capacity where registered users can transfer data files between their personal work computer device and the server via internet for backup of data files for sharing data files for collaboration on data files for synchronisation of data files etc. Some service providers use encryption methods when transferring files between the server and the computer device of the user.

The encrypted transfer of a file between the computer device and the server often uses a protocol like the Hypertext Transfer Protocol Secure HTTPS to encrypt the transfer of a data file from the computer device to the server. Hence the server receives an encrypted file but when received the data file is decrypted and the data file is stored unencrypted. A person with administration privileges on the server will easily have access to the data file.

This type of technology has several disadvantages. First of all many service providers require that an application has to be downloaded and installed on each computer device used to connect to the servers. This may be cumbersome in addition the user may not have privileges on the computer device to install applications.

Some service providers also offer a system with the possibility of encrypting the data file before transferring the file to the server and storing of the data file encrypted on the server. In order to share the data file the encryption key must be stored together with the encrypted data file. Again a person with administrator privileges may then access the file. Alternatively no encryption key is stored on the server however no sharing of the data file is then possible.

One object of the present invention is to provide a method and system for secure storing of a data file via a computer communication network which can be used even if the user does not have administrator privileges on his computer and without the need for installation of a separate application. Moreover one object is to provide that the data files are kept continuously encrypted from the time when the data file is leaving the computer device of the user and to the time when the same or another computer device is receiving the data file from the server. In this way it is avoided that a person with administration privileges has access or can get access to the unencrypted data file. Moreover if a hacker breaks into the server he she will not get access to the data files as well.

Another object is to provide a method and system where the user can give access to the data file to other users.

The present invention relates to a computer implemented method for secure storing of a data file via a computer communication network comprising the steps of 

In one aspect the information about the data file comprises at least one of the following elements a file creation date a file name a unique file identifier created timestamp modified timestamp and a file size.

In one aspect the method comprises the steps upon receiving a login request comprising the unique user name from the computer device 

In one aspect the method comprises the steps of upon receiving a data file request from the computer device 

In one aspect the method comprises the steps of upon receiving a data file request from the computer device of the further user 

In one aspect the password is sent to the non registered user by means of an e mail application installed on the computer device of the user.

In one aspect the password is sent to the non registered user by means of a SMS MMS or similar service.

The invention also relates to a computer program comprising processing instructions which enables a server computer to perform a method as set above.

The term computer device is here used to denote any type of electronic device which can be connected to Internet and which can read open change or store a data file. This would typically be a stationary or portable computer a laptop a notebook a mobile phone a smart phone an internet tablet a smart TV or similar type of device.

The term data file is here used to denote any type of electronic information which can be stored on a computer device and a server for example text documents spreadsheets presentations multimedia files images music movies etc computer source code etc. It should be noted that a folder can also be considered as a data file.

The term web browser is here used to denote a computer application which is installed on the computer device and which the user can use to retrieve present and traverse information resources on the World Wide Web internet. The web browser would typically be Internet Explorer Mozilla FireFox Safari Opera Google Chrome Chromium or other web browsers.

The term server is here used to denote a computer server which the user can interact with by using the web browser installed on the computer device. The server comprises a web service and a file handling service for storing and organizing data files as will be apparent from the description below. The server may comprise one physical computer server but may also comprise several servers connected to each other.

It is now referred to illustrating a first embodiment of a computer implemented method for secure storing of a data file on a server via a computer communication network typically the internet. In it is shown communication via internet between the server and a web browser installed on a computer device .

In the description below the embodiment is viewed from the server . In an aspect the disclosed computer implemented method is performed by the server e.g. by a processing device included in the server .

Initially the user is opening the web browser on the computer device and is directing the web browser to the domain name or IP address of the server for example http www.example.com.

In return of the request the server is providing the computer device with code by sending the code to the web browser via internet after which the code is executed by the web browser on the computer device . The code comprises some information typically in the form of information files html xml files and or appearance controlling files css stylesheets . Moreover the code comprises code that can be executed by the web browser for example ECMA script code commonly known as JavaScript or Jscript. Today JavaScript code is the only option for cross browser support. However it could also be possible to implement the code as VBScript code that can be executed in Internet Explorer by Microsoft. There could be other alternatives as well. Hence it is possible to perform the computer implemented method without installing a separate software application on the computer device. Alternatively the code could be provided as a plug in for the web browser by using an API Application Programming Interface for the web browser. Such APIs are known for web browsers like Google Chrome Internet Explorer Mozilla Firefox and others. Such plug ins can most often be installed on the computer device without administrator privileges.

The code executed by the web browser first provides a unique user name for the user. The unique user name may be the e mail address of the user which per se is unique. Alternatively the user name can be automatically generated by the code itself random functions. In yet an alternative the user may suggest his her own user name.

The code executed by the web browser may then perform a check whether the user name is unique by sending a request to the server to check if the user name already has been registered or not. If the user name has already been registered it is per se not unique and the user is required to provide another user name.

The code executed by the web browser is then asking the user for a password. The password is not transferred to the server .

The code executed by the web browser is then generating an asymmetric key pair for the user having one public key and one private key. The algorithm for generating such asymmetric key pairs is considered known for the skilled person. For example the open source project GNU PGP http www.gnupg.org provides source code for such key generation in the C programming language.

The code executed by the web browser is then encrypting the private key of the user by means of a hash of the password and produces an encrypted private key. Hence the private key is only accessible from the encrypted private key by knowing the password. Hash functions are commonly used to generate a hash of a string such as a password. Such hash functions are considered known for a person skilled in the art for example SHA1 MD5 etc.

The code executed by the web browser is initiating and performing the transfer of files to the server. Hence the server is receiving the encrypted private key of the user and the public key of the user from the computer device.

The encrypted private key of the user and the public key of the user are then stored in a user management system of the server.

Thereafter a data file transferring process will be described. Often the first data file transferring process will be performed together with the registration process above.

The code executed by the web browser is then requesting the user for the data file which is to be securely stored on the server via the computer communication network .

The code executed by the web browser is then generating a file specific symmetric key which is specific for the data file. The file specific key is hence unique. The process of generation of a symmetric key is also known for a person skilled in the art. Known algorithms for the generation of a symmetric key are Blowfish AES Triple DES etc. The probability of generating two identical symmetric keys is very low so there is no need to check for other symmetric keys. Of course such a check could be performed.

The code executed by the web browser is then encrypting the data file by means of the file specific symmetric key. Hence the result is an encrypted data file.

The code executed by the web browser is then encrypting the file specific symmetric key by means of the public key of the user. Hence the result is an encrypted file specific symmetric key which can only be decrypted with the private key of the user.

The server is then receiving the encrypted data file and the encrypted file specific symmetric key. If this data transfer process is performed together with the registration process also the encrypted private key of the user and the public key of the user will be transferred to the server from the computer device in order to transfer all files and keys at the same time. It should be noted that in the description above the keys themselves may be considered as files stored on the computer device either in the memory RAM or on a hard disc etc.

Hence the code executed by the web browser is initiating and performing the transfer of these files data files and encrypted non encrypted key files from the computer device to the server.

The encrypted data file and the encrypted file specific symmetric key is then stored in a file management system. Again if this data transfer process is performed together with the registration process the he encrypted private key of the user and the public key of the user are then stored in the user management system.

Since many of the above steps related to the key generation and encryption are performed by executing the code in the web browser on the computer device the server itself will only contain encrypted data files private keys of the users and the file specific symmetric keys. Hence a person having access to the server does not have access to the content of these files.

It should be noted that the registration process of a user and data file transfer process of transferring a data file from the computer device to the server do not have to be performed simultaneously. The user may use the web browser on the computer device to register at the server in a first operation before the user logs out. The user may then in a second subsequent operation log in and then select and transfer the data from the computer device to the server.

According to the embodiment described above the user may now use a web browser on a further computer device which is different from the computer device used for the registration process and the data file transfer process above and direct the web browser on the further computer device to the domain name or IP address of the server and perform a login and transfer data files from the further computer device to the server or to transfer data files from the server to the computer device.

The login process will now be described. Upon receiving a login request comprising the unique user name from a computer device the following steps are performed on the server.

First the user is identified by means of the unique user name. Then a unique session ID is generated. The session ID is for example generated by means of random function alternatively a check may be performed with respect to other session IDs. As described above the public key and the encrypted private key have been stored in the user management system of the server. The session ID is also stored in the user management system of the server.

The session ID is encrypted by means of the public key of the user. Then the encrypted private key of the user and the encrypted session ID are sent to the computer device.

Together with these files the server is providing the computer device with code by sending the code to the web browser via internet where after the code is executed by the web browser on the computer device .

The code executed by the web browser is then asking the user for the password. If the password is correct the encrypted private key is decrypted by means of a hash of the password and the encrypted session ID is decrypted by means of the private key.

The code executed by the web browser is now sending the session ID to the server. Hence the server is receiving the session ID from the computer device. The server is then comparing the received session ID with the generated session ID stored in the user management system and the login request is accepted if the received session ID is identical to the generated session ID. When the login has been accepted the server is sending information files and code that can be executed by the web browser to the computer device for the web browser to show a user interface. In the user interface the files and folders on the server belonging to the user or being shared with the user are shown. Moreover there are possibilities to select files stored on the server and transferring them to the computer device and there are also possibilities to select files on the computer device and transferring them to the server.

A data file transfer process for transferring a file from the server to the computer device will now be described. Upon receiving a data file request from the computer device the server performs the following steps. First the encrypted data file and the encrypted file specific symmetric key are sent to the computer device. Then the server is providing the computer device with code that can be executed by the web browser on the computer device.

The code executed by the web browser is decrypting the file specific symmetric key by means of the private key. The private key was obtained by the login process described above. Then the data file is decrypted by means of the decrypted file specific symmetric key. The user may then be asked whether the data file should be opened or stored on the computer device.

In the description above there are two options with respect to the name of the data file. The code executed by the web browser may give the encrypted data file a name equal to or similar to the data file itself. It would then be relatively easy for the user to recognise the correct file on the server when the user wants to transferring it back from the server to the computer device or to a further computer device. However this file name will be viewable on the server by a person having administrator privileges and sometimes the name of a data file itself may contain sensitive or secret information. Hence an alternative would be to change the name of the data file during the encryption. The disadvantage would then be that it is difficult for the user to separate the different files from each other.

An information file with information about the data file can be used for this purpose. During the data file transferring process of transferring a data file from the computer device to the server the computer device is provided with code that can be executed by the web browser on the computer device.

The code executed by the web browser is first generating an information file with information about the data file. Then the information file is encrypted by means of the file specific symmetric key as described above with respect to the data file transfer process.

The code executed by the web browser is then sending the encrypted information file to the server. Hence the server is receiving the encrypted information file together with the encrypted data file and the encrypted file specific symmetric key. If this is performed during the registration process also the encrypted private key of the user and the public key of the user are received by the server. The encrypted information file is also stored in the file management system.

The information file may comprise information about the data file such as a file creation date a file name a unique file identifier created timestamp modified timestamp size etc. Hence the file name is stored encrypted on the server as a part of the encrypted information file.

After a login process the server is sending the encrypted information file to the computer device together with the other files as described above. Moreover in addition to the code described above with respect to the login process the computer device is also provided with code for execution by the web browser on the computer device for decrypting the encrypted information file by means of the decrypted file specific symmetric key.

Hence the file name can be shown to the user in the user interface in the web browser and it is easy for the user to separate the data files from each other.

Above it has been described how a user can use web browsers on different computer devices to access encrypted data files on a server where a person having administrator privileges on the server cannot access the encrypted data files.

It is further possible to share files between different users which will be described further in detail below. Here additional functions are provided as a part of the user interface of the web browser after a login has been performed.

The server is as described above providing the computer device with code that can be executed by the web browser on the computer device.

The code executed by the web browser is providing the possibility for the user to provide an indication of which data file the user wants to share. Moreover the user may provide an indication of a further user i.e. a user different from himself herself to share the data file with. The further user may for example be selected from a list or there may be a search option to search for names etc.

The code executed by the web browser is then sending these indications to the server. Hence the server is receiving the indication of which data file to share and the indication of the further user to share the data file with.

The server is then sending the public key of the further user and the encrypted file specific symmetric key for the data file to the computer device.

The code executed by the web browser is then decrypting the file specific symmetric key by means of the private key. As described above the private key was transferred to the computer device as part of the login process. Then the decrypted file specific symmetric key is encrypted again as a further file specific symmetric key by means of the public key of the further user. Hence it is possible for the further user to access the further file specific symmetric key by using the private key of the further user as will be described below.

The code executed by the web browser is then sending the encrypted further file specific symmetric key to the server. Hence the server is receiving the encrypted further file specific symmetric key and is storing the encrypted further file specific symmetric key in the file management system.

When a further user uses the web browser on his her computer device to login the further user receives as described above encrypted private key of the further user which is decrypted by using the further user s password.

Upon receiving a data file request from the computer device of the further user related to the data file shared above the server performs the following steps. First the server is sending the encrypted data file and the encrypted further file specific symmetric key to the computer device. Then the server provides the computer device with code for execution by the browser on the computer device.

The code executed by the web browser is decrypting the encrypted further file specific symmetric key by means of the private key. Then the encrypted data file is decrypted by means of the decrypted further file specific symmetric key. Hence the further user has access to the shared data file from the user.

There are several ways the further user can be selected. However it is not always desired that all users registered in the user management system are listed for sharing of data files. Hence the sharing of files can be restricted to users that have established contact with each other.

The user interface of the web browser may therefore comprise a possibility to establish contact with other users. One requirement can for example be that you are only allowed to establish contacts with someone you know the user name or e mail address of.

The server is then receiving a contact request from the computer device of the user for establishing contact between the user and a further user. The server is then sending a confirmation request to the further user. The further user will then receive a notice via e mail and via the user interface upon login and may choose to accept or not accept the contact request. If the server receives an acceptance of the confirmation request from the further user the server is storing contact information about the contact between the user and the further user in the user management system. The users may then only share data files with their own contacts.

It should be noted that it is possible to share a data file with more than one further user. The process described above will then be repeated for these further users.

In addition the user which is sharing the data file may grant different access to the shared data file for example read only access read and write access and read write and delete access.

In a first embodiment using the methods above is illustrated. A user or first user U1 has a data file and when registering according to the method described above a private key and a public key are generated. The file management system of the server is storing the encrypted data file the encrypted information file and the encrypted file specific symmetric key for the user U1. The user management system is storing the public key for the user U1 and the encrypted private key for the user U1 of course together with the user name for the user U1.

In a second embodiment using the methods above is illustrated. Here a second user U2 is also registered. In addition to the files described above the file management system is storing a further or second encrypted file specific key U2 for the second user U2. And in addition to the files described above the user management system is storing the public key for the user U2 and the encrypted private key for the user U2 of course together with the user name for the user U2. As illustrated the second user 2 can get access to the data file via the server but without any possibility for the server to get access to the data file.

It is also possible for a user to share a data file with a non registered user. In the user interface of the users web browser for example after the registration process of the user or after a login process the user selects a data file and selects to share this file with a non registered user. Consequently the code executed by the web browser is providing the user with code for providing an indication of which data file to share.

The code executed by the web browser is then asking the user for an e mail address of a non registered user to share the data file with.

The code executed by the web browser is then generating a password for the non registered user and is sending the password to the non registered user. The sending of the password would normally take place at the end of this data file sharing process. The password may be sent to the non registered user by means of an e mail application installed on the computer device of the user to avoid that the e mail containing the password is sent through e mail servers administrated by the same organization as the server defined above. Alternatively the password is sent to the non registered user by means of a SMS MMS or similar service. In such an alternative the phone number of the non registered user should be given together with the email address.

The code executed by the web browser is then providing a hash of the password of the non registered user by means of a hash function.

The code executed by the web browser is then generating a file specific symmetric key specific for the data file and is encrypting the file specific symmetric key by means of the password in similar way as described above.

The server is then receiving the indication of which data file to share the e mail address the hash of the password and the encrypted file specific symmetric key. Thereafter the server is sending an e mail to the e mail address of the non registered user containing a link or URL to a page on the server.

When the non registered user is opening the link in the web browser a request is sent to the server. As an answer to the request the server is providing the non registered user with code for asking the non registered user for the email address and the password. This would typically be an input form of the user interface in the browser. It would of course be possible to provide the link in such a way that the email address is filled in advance i.e. the non registered user does only have to write is password. It should be noted that as above the password itself is not sent to the server.

The code executed by the web browser is then providing a hash of the password of the non registered user by means of the hash function. The hash function is the same as the one above.

The server is then receiving the email address and the hash of the password from the non registered user.

The server is then generating a unique session ID and is encrypting the session ID by means of the hash of the password of the non registered user. Then the server is sending the encrypted session ID to the computer device of the non registered user.

Moreover the server is providing the non registered user with code for being executed by the web browser on the computer device.

The code executed by the web browser is then decrypting the encrypted session ID by means of the hash of the password. The decrypted session ID is then sent to the server.

The server is receiving the session ID from the computer device of the non registered user and is then comparing the received session ID with the generated session ID.

If the received session ID is identical to the generated session ID the server is sending the encrypted file specific symmetric key and the encrypted data file to the computer device of the non registered.

Again the server is providing the non registered user with code for being executed by the web browser on the computer device.

The code executed by the web browser is decrypting the encrypted file specific symmetric key by means of the password and is decrypting the encrypted data file by means of the decrypted file specific symmetric key. Finally the non registered user has access to the data file shared by the registered user.

It should be noted that an information file may also be used when sharing a file with a non registered user. As described above the information file has been encrypted by means of the file specific symmetric key and the encrypted information file is stored in the file management system.

The non registered user may receive the encrypted information file together with the encrypted data file from the server.

The code executed by the web browser is here decrypting the encrypted information file by means of the password.

In order to further exemplify the process of secure authentication of a user further user and a non registered user and the process of exchanging information file data file encryption file key password and hashed password to respective parties involved in the process of storing and sharing said information the is provided and discussed. The process described in the following does not define error situation faulty input or other similar incidents. Implementation of the invention will in most practical cases also comprise such features. When the words file data file information file file key encrypted file key password password hash and the like is used in singular form it is to be understood that the invention also comprise the handling of the same in plurality form.

These shows the information flow when a user has opened a web browser and connected to the server. A number of components are downloaded from the web application server upon start up of the web application. These components comprise but are not limited to 

The user s browser client may offer the interface as a web browser interface and the operations concerned with creation of a user are shown in frame . in . Frame . in represents the operations executed on and by the server in communication with the user on the browser client.

This scenario is executed once when the user registers to the service. When the user browser connects to the server and the components of the invention are downloaded to the browser client the user is asked to input a user name . . The server then verifies if this user name is a valid user name and if the user name is available . .

When the user name is approved the user will be asked to input additional information regarding the authorization process. This information typically includes Authorization code Name Password Secret Question Answer to Secret Question and other.

The Password is then handled by the component for Hash resulting in a hashed password . . The component for Hash can comprise one or more hash functions of any type for example SHA1.

Once the password is hashed and stored the component for public private key generation . is executed. This results in a key pair comprising a public key and a private key. These keys can optionally be of 2048 bit length and intended for use in an algorithm like the RSA Algorithm.

The private key then is encrypted . with a symmetric algorithm using password as input. The hashed password is then stored in a file on the server. Optionally the private key can also be encrypted with the answer to the secret question and stored in a database for use if the user forgets the password.

Although the above scenario is explained as a create new user scenario it is similarly executed if a user needs to modify the stored information. For such operations the user must first log in as explained below and then repeat step . to .. Default values may be presented alternatively as stored previously.

In an embodiment of the invention a previously registered user will when browser navigates to the inventions server application and the components of the invention is downloaded to the browser client enter the login sequence as defined in . The frames . and . represent the communication on the user s browser client and the server respectively.

The user is prompted for user name and password . and the password is then hashed . an operation executed on the Browser client computer. The username and the hashed password are validated . by the server. The server validates this information with previously stored password hash and username . . If the password hash and the username are valid the server will generate a unique session ID . which will be encrypted with the user s public key . . The public key encrypted session ID will be sent to the browser client optionally together with the password encrypted private key to be stored by the server.

Browser client then decrypts the password encrypted private key . using the password if the private key was received from the server. Authentication of the user is ensured when the user public key encrypted . session ID is decrypted with the user private key . and returned in clear text to the server. The server then verifies and ensures . that the session ID is correctly decrypted by the user by comparing it with the generated session ID . . Correct received session ID verifies that the user is authenticated and the user is considered to be logged in and the user is allowed to use the services offered by the server to the user through the invention components running on the browser client.

The user may follow a scheme as described in to select and store data file and associated information. The frames . and . represent the communication on the user s browser client and the server respectively.

The browser client component presents in an embodiment of the invention functionality to the user for choosing a file . from the users file system to be imported to the server. When file is selected a unique id for the file is generated . and a file key is generated . . This file key is preferably a symmetric encryption key for example a 256 bit AES Advanced Encryption Standard key. An information file is created . comprising metadata from the chosen file . . These metadata may comprise information such as file name file creation data file size date of last change and more. The information file may also comprise specific information generated by the user and or the invention application either by the browser client or the server. Such information may comprise file ID parent folder id of the chosen file . description of the chosen file in readable text and other.

The information file is encrypted . with the file key generated . for the chosen file. The chosen file . hereafter called the data file is then encrypted . with the same file key.

The file key gets encrypted . with the user s public key. The encrypted data file . the encrypted information file . and the encrypted file key . are stored . on the server.

The browser client receives an acknowledgement of successful operation of storing . the encrypted data file . the encrypted information file . and the encrypted file key . on the server.

The user may follow a scheme as described in to select download and access a data file and associated information stored on the server. The frames . and . represent the communication on the user s browser client and the server respectively.

In one embodiment of the invention when user has logged in as described above and illustrated in the available data files stored on the server is presented to the user through the browser client. The user then selects . what file to get file key and information file from the server for. This request is then handled by the server . which transfer the encrypted information file and the encrypted file key to the browser client. The browser client in turn decrypt . the file key with the private key of the key pair . . Once the file key is available the file key is used to decrypt the information file . containing the meta data of the data file. These metadata from the information file may then be displayed . to the user. The user may then be able to view the displayed information and is able to select . which data file to download and open. Upon selecting data file to download and open the request is handled by the server by locating . the stored encrypted data file which is in turn sent to the browser client which in turn will decrypt the data file . with the file key. The user may then be able to view the data file content.

The user may follow a scheme as described in to identify select a further user with whom the user wants to share specific file with. The frames . . and . represent the communication on the user s browser client the server and the further user s browser client respectively.

In one embodiment of the invention there are one or several further users prequalified to be selectable identified by user to be allowed to get access to selected encrypted files on the server. When a user needs to share one or more files the user will use the user s browser client function for selecting a further user of the prequalified selectable further users to select further user . to share with. The server then provides . the further user s public profile which is sent to the user s browser client. The user s browser client creates a copy . of the file key associated with the selected file and then the user s browser client encrypts the file key . with the further user s public key comprised in the further user s public profile. The user then selects to create a share request . . The user may now be allowed to include some descriptive information about the file intended to be shared with the further user. These metadata may also comprise other information such as a more descriptive name of the shared file instead of only the file name. The metadata is encrypted with the further user s public key . . The request is then sent to the server which store the encrypted file key . and the share request comprising the metadata . . A status report is sent to the user s browser client identifying and displaying the share request as unanswered . .

In this embodiment nothing happens with the share request until the further user logs in to the invention application at the server optionally following the logic explained in and . Upon successful login the further user s browser client sends a request for changes from the server . . When the server receives the request for changes . from the further user s browser client the server responds with sending the share request from the user. The share request is then displayed . by the further user s browser client. Only the acceptance of such request is exemplified by the but it may be an option to deny the share request whereupon such denial is shared with the user and subsequently logged and or deleted in the server. The server stores the acceptance of the share response . . When user next time is connected to the server the share request response is transferred . to the user s browser client for handling.

When share is accepted by the further user the component running on the further user s browser client may request the information file . from the server. The server provides . the encrypted . metadata and the encrypted . file key and thus the further user browser client can decrypt . the file key using the further user s private key and decrypt . the information file . with the decrypted file key . . The further user s browser client now displays the metadata describing the data file that is shared by the user. The further user can now access and download selected data file and information file using the same procedure as described in frames . and . where the select download and access data file and information file are described. The further user replaces the role of the user in and the further user s browser client replaces the user s browser client.

The user may follow a scheme as described in to define a non registered user with whom the user wants to share specific file with. The frames . . and . represent the communication on the user s browser client the server and the non registered user s browser client respectively.

In one embodiment of the invention when a user needs to share one or more files with non registered users the user will use the user s browser client function for selecting non registered user to select non registered user . to share with. Prior to the selection of non registered user to share with the user has logged in to the server application and chosen file to share with the non registered user. The non registered user may be identified by the user inputting the non registered users e mail address. Other identification mechanisms may be chosen such as for example selecting non registered user from a third party register. The user s browser client creates a password . alternatively let the user input a user defined password. The user s browser client makes a copy of the file key and encrypts this . with the newly generated password . . The password is then hashed . by the user s browser client and sent to the server together with the encrypted . file key and the email address . of the non registered user. The server responds to the user by sending . a link to the non registered user to which the non registered user shall connect for further proceeding of accessing shared file. The server may optionally send the password hash associated with the link identifying the chosen file to share.

The user now sends the password which is unencrypted to the non registered user. This can be done by e mail or other communication procedure. Examples of such might be a message by telephone SMS by letter by orally presenting the password and or link or others. A safe communication line for transmission of the password to the non registered user e.g. a secure e mail service may be used.

When the non registered user receives the login link the non registered user will when connecting . to the server receive the web interface together with appropriate components for communication and operation of the services of authentication and download of file. The first operation of the non registered user when connected is to log in . to the server. The server then verifies the email address of the non registered user and compares . this with the address received . from the user followed by an optional check of the password hash that is transmitted from the non registered user to the server in the login sequence that is used to identify the file selected for share. Upon successful comparison the server generates a session ID . which is encrypted . with the password hash that was received . from the user. The session ID is sent to the non registered user. The non registered user s browser client performs a hash . of the password received from the user . . The non registered user s browser client use the hashed password to decrypt . the session ID received . from the server. The non registered user may now request information file and the encrypted . file key by sending a request for this together with the decrypted . session ID. When the server receives this request . the server perform the second stage of the authentication operation by verifying . the received session ID and compare it with the generated . session ID. If the comparison is successful the server transmits . the shared encrypted information file and the file key. The encrypted file key is then decrypted . by the non registered user with the password received from the user . . When the file key is decrypted the file key is used to decrypt . the information file. Now the non registered user s browser client can display the metadata of the information file and the non registered user is able to download decrypt and access the shared data files. The non registered user can now access and download selected data file using the same procedure as described in frames . and . where the select download and access data file and information file are described. The non registered user replaces the role of the user in and the non registered user s browser client replaces the user s browser client.

The communication and exchange of information between user and server and Further user Non registered user and server in current invention are defined by several components. shows some of these components that may be downloaded to client for execution on the client computer when associated information is to be provided by the client.

It will be understood that the sequence or order of method steps described above has been presented for explanatory purposes and that the same result in certain cases may be achieved with sequences that depart from what has been specifically described. For instance any steps that are performed independent of each other may be performed in any order or even simultaneously or concurrently.

Although the invention has been specified in the above as relating to a computer implemented method the skilled person will readily realize that the invention may also be embodied in the form of a computer program which may be loaded into a memory in the server . Such a computer program includes processing instructions which enables the server to perform the disclosed method when the instructions are executed by a processing device in the server . It will also be understood that the invention may be embodied as the server when the server is configured to e.g. programmed to perform the disclosed method.

It should be understood that the described method server and computer program technically correspond to each other and that any feature that has been described specifically for the method should be considered as also being disclosed with its counterpart in the description of the server or computer program and vice versa.

