---

title: System, method, and computer program product for identifying vulnerabilities associated with data loaded in memory
abstract: By way of example, a system, method, and computer program product are provided for identifying vulnerabilities associated with data loaded in memory. In operation, a subset of data that is loaded in memory is identified, including for example by name and version number. The subset of data is compared to a known minimal version known to be good. Furthermore, there is a reaction based on the comparison, such as reporting a vulnerability.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08898778&OS=08898778&RS=08898778
owner: McAfee, Inc.
number: 08898778
owner_city: Santa Clara
owner_country: US
publication_date: 20120118
---
This application is a continuation and claims the benefit of priority under 35 U.S.C. 120 of U.S. application Ser. No. 12 248 550 filed Oct. 9 2008 now U.S. Pat. No. 8 127 354 entitled SYSTEM METHOD AND COMPUTER PROGRAM PRODUCT FOR IDENTIFYING VULNERABILITIES ASSOCIATED WITH DATA LOADED IN MEMORY Inventor s Anthony J. Bettini et al. The disclosure of the prior application is considered part of and is incorporated by reference in the disclosure of this application.

The present invention relates to vulnerability assessment and more particularly to identifying vulnerabilities for remediation purposes.

In computer security the term vulnerability refers to a weakness in a computer system that allows an attacker to violate the integrity of that system. Vulnerabilities may result from software bugs a computer virus or other malware a script code injection a structured query language SQL injection and or other techniques. A vulnerability may exist in theory or may have a known instance of an exploit.

Traditional vulnerability scanning assessment and management software has been implemented in a network centric fashion. Although host based vulnerability scanning assessment and management software exists these host based implementations are typically managed implementations. Additionally these host based implementations typically have a patch management or policy violation focus.

Such managed implementations often require regular updating and maintenance. Furthermore these implementations often evaluate dormant unused applications without considering the possibility of these applications never opening an attack vector to exploit a vulnerability of the host system. There is thus a need for overcoming these and or other issues associated with the prior art.

A system method and computer program product are provided for identifying vulnerabilities associated with data loaded in memory. In operation a subset of data that is loaded in memory is identified. Additionally the subset of data is compared to a list of known data. Furthermore there is a reaction based on the comparison.

In this case the subset of data loaded in memory may include any data loaded into memory as a result of opening or executing a software application computer program and or file. For example in various embodiments the subset of data may include one or more libraries e.g. dynamic link library DLL files etc. loaded into memory as a result of opening or executing an application one or more files loaded into memory as a result of opening or executing an application one or more executables loaded into memory as a result of opening or executing an application and or any other subset of data that meets the above definition.

In these cases the application computer program and or file may include any items that load data into memory as a result of being executed or opened. For example in various embodiments the application may include a word processor application a spread sheet generation application a media player application and or any other application computer program and or file.

Once the subset of data is identified the subset of data is compared to a list of known data. See operation . In one embodiment the list of known data may include known data that is known to be safe.

In this case the comparison may include comparing at least one name of the subset of data with at least one name of the known data to determine if a match exists. Subsequently if it is determined that the match exists the comparison may further include comparing a version of the subset of data with a minimum version of the known data that is known to be safe.

In another embodiment the known data may be data that is known to be unsafe. In this case if it is determined that the match exists the comparison may further include comparing a version of the subset of data with a version of the known data that is known to be unsafe. As an option the subset of data and the list of known data may be identified utilizing a plurality of file names and or version identifiers.

Once the subset of data is compared to the list of known data there is a reaction based on the comparison. See operation . The reaction may include any number of actions.

For example in one embodiment the reaction may include reporting a vulnerability. In another embodiment the reaction may include blocking access to the subset of data. In still another embodiment the reaction may include replacing or updating the subset of data.

As an option the reaction may be carried out if the version of the subset of data is less than the minimum version of the known data that is known to be safe. In this case the reaction may include replacing the subset of data with data that is of a version that is known to be safe. In this case the reacting may also include prompting a user to initiate such replacement.

More illustrative information will now be set forth regarding various optional architectures and features with which the foregoing technique may or may not be implemented per the desires of the user. It should be strongly noted that the following information is set forth for illustrative purposes and should not be construed as limiting in any manner. Any of the following features may be optionally incorporated with or without the exclusion of other features described.

In operation a host device loads a subset of data into memory as a result of executing an associated software application. Logic is then utilized to identify the subset of data in memory . In this case the subset of data may be identified by identifying at least one running process associated with the application. As an option the subset of data may be identified by identifying at least one imported library associated with the at least one running process.

Although the logic is illustrated in as being located on the host device the logic is not limited to being located on the host device . In various embodiments the logic may include host based logic i.e. located on the host device or network based logic. For example the logic may include logic provided by a server over a network .

It should be noted that the host device may include any device capable of executing an application. For example in various embodiments the host device may include a desktop computer lap top computer hand held computer mobile phone personal digital assistant PDA peripheral e.g. printer etc. any component of a computer and or any other type of logic. Additionally the network may include a local area network LAN a wireless network a wide area network WAN such as the Internet peer to peer network etc.

Once the subset of data stored in the memory is identified the subset of data is compared to a list of known data utilizing the logic . In various embodiments the comparison may be initiated utilizing different techniques. For example in one embodiment the comparison may be performed in response to the subset of data being loaded in the memory .

In another embodiment the comparison may be performed on demand. In still another embodiment the comparison may be performed in accordance with a schedule. In either case the list of known data may be a list stored on the host device or on the server .

In one embodiment the list of known data may be provided to the host device from the server . As an option the list of known data may be provided to the host device periodically. For example the list of known data may be provided to the host device at predetermined time intervals. In this case the time intervals may be user configurable e.g. by a user of the host device or by a user at the server etc. .

As another option the list of known data may be provided to the host device upon an update to the list . For example when data in the list of known data is updated the server may send the list to the host device . As yet another option the list may be automatically sent to the host device upon the execution of an application.

In another embodiment the list of known data may be stored on the server and any processing may be implemented on the server . For example the server may identify the subset of data in the memory of the host device . In this case the subset of data may be communicated to the server from the host device .

The server may then compare the subset of data to the list of known data utilizing the logic located on the server . Regardless of whether the comparison is implemented on the server or the host device the result of the comparison is formulated into an output . This output may then be utilized to determine a reaction based on the comparison.

As an example implementation of the system a software patch may be released by a software provider. In this case the patch may resolve a vulnerability that is present in one or more files e.g. a DLL etc. loaded in the memory . Thus the patch may provide a new or updated version of those files.

The logic may include a vulnerability assessment tool either host based or network based that determines the location of the files in the memory based on enumerating processes then enumerating loaded libraries and may determine a version number of the files loaded in the memory . If the files in the memory have a version that is lower than the files deployed by the patch the host device may be assessed as vulnerable due to having the vulnerable code actively loaded in the memory .

In addition the logic may be utilized to determine the location of the files on a disk not shown from a registry and may determine if the version of the file on the disk is older than the patched file based on the version. If the file version of the file on the disk is lower than the file deployed by the patch the system may also be assessed as vulnerable due to having the vulnerable code on the disk.

In this way the logic will be able to determine whether a vulnerable process is actively running as well as whether a vulnerable file is stored on a disk. Furthermore in one embodiment vulnerabilities may be detected in systems utilizing a side by side assembly implementation e.g. Microsoft Windows Side by Side etc. .

A side by side application compatibility framework may allow different versions of libraries to co exist on the same system. In these cases the different versions may contain different security vulnerabilities. Thus the security vulnerabilities for each of the different versions may be determined and remedied utilizing data loaded in memory as a result of running these different versions.

For example the subset of data may include a first subset of data and a second subset of data. In this case the first subset set of data may be loaded into the memory as a result of executing a first application. Additionally the second subset of data may be loaded into the memory as a result of executing a second application.

Subsequently the first and the second subset of data may be assessed for vulnerabilities. In other words the first subset of data and the second subset of data may both be compared to the list of known data. An appropriate reaction may then be implemented based on this comparison.

As shown a list of known vulnerabilities is loaded. See operation . In this case the list may include name information and or version information. For example the list may include one or more names of files applications and or other data.

Furthermore the list may include version information associated with such files applications and or other data. In this case the version information may include version numbers for outdated or vulnerable items version numbers for updated items a range of version numbers for vulnerable items a range of version numbers for non vulnerable items and or any other version information.

In one embodiment the list may include names version numbers default locations sizes e.g. a 32 bit library a 64 bit library etc. types language information hashes and or metadata information for all files that may be vulnerable. In this case the list may be loaded onto a host system from a server. Furthermore the list may be updated continuously periodically on demand etc.

Once the list of known vulnerabilities is loaded to a host system a list of imported libraries is obtained for every process running on the host system. See operation . In this case the imported libraries may include any library file and or executable that is imported into memory as a result of an associated process running on the host system.

The imported libraries may be obtained utilizing an operating system application programming interface API and or other logic. For example the imported libraries may be obtained utilizing an API for determining all processes running on the host system. For every running process an import table may be utilized to determine the list of imported libraries.

Each of these imported libraries e.g. each list of imported libraries etc. may then be compared to the list of known vulnerabilities. Thus for each imported library it is determined whether the library name is in the list of known vulnerable libraries. See operations .

If it is determined that a library name in the list of imported libraries is in the list of known vulnerable libraries a library version is obtained from a resource section of that library. See operation . It is then determined whether the imported library version is greater than a minimum known non vulnerable version and less than or equal to a known vulnerable version. See operation .

If it is determined that the imported library version is greater than a minimum known non vulnerable version and less than or equal to a known vulnerable version the imported library may be deemed vulnerable. In this case the vulnerability may be reported. See operation .

In one embodiment the reporting may include notifying a user of the host system. In another embodiment the reporting may include notifying a server associated with the host system. In still another embodiment a system administrator may be notified. The vulnerability may be logged as part of the reporting.

In addition to reporting the vulnerability further reactions may be implemented by the host system and or a server associated with the host system. In this case the reaction may include prohibiting use of an application associated with the vulnerability. As another option the vulnerable library may be updated.

It should be noted that in various embodiments different techniques may be utilized in operation to determine whether the imported libraries are vulnerable. For example in one embodiment it may be determined whether the version of the imported library is different than a version of a known vulnerable version. In another embodiment it may be determined whether the version of the imported library is an unknown version.

Furthermore in one embodiment the method may be implemented in conjunction with a vulnerability scan of a disk e.g. a hard drive etc. of the host system. For example data e.g. dynamic link library files etc. that is stored on a disk may be identified. This data may then be compared to the list of known data.

Furthermore there may be a reaction based on the comparison of the data stored on the disk to the list of known data. In this case the reaction may include any appropriate action. For example in various embodiments the reaction may include updating the vulnerable data prohibiting the use of the vulnerable data and or any other appropriate action

Coupled to the networks are servers which are capable of communicating over the networks . Also coupled to the networks and the servers is a plurality of clients . Such servers and or clients may each include a desktop computer lap top computer hand held computer mobile phone personal digital assistant peripheral e.g. printer etc. any component of a computer and or any other type of logic. In order to facilitate communication among the networks at least one gateway is optionally coupled therebetween.

The workstation shown in includes a Random Access Memory RAM Read Only Memory ROM an I O adapter for connecting peripheral devices such as disk storage units to the bus a user interface adapter for connecting a keyboard a mouse a speaker a microphone and or other user interface devices such as a touch screen not shown to the bus communication adapter for connecting the workstation to a communication network e.g. a data processing network and a display adapter for connecting the bus to a display device .

The workstation may have resident thereon any desired operating system. It will be appreciated that an embodiment may also be implemented on platforms and operating systems other than those mentioned. One embodiment may be written using JAVA C and or C language or other programming languages along with an object oriented programming methodology. Object oriented programming OOP has become increasingly used to develop complex applications.

Of course the various embodiments set forth herein may be implemented utilizing hardware software or any desired combination thereof. For that matter any type of logic may be utilized which is capable of implementing the various functionality set forth above.

While various embodiments have been described above it should be understood that they have been presented by way of example only and not limitation. Thus the breadth and scope of a preferred embodiment should not be limited by any of the above described exemplary embodiments but should be defined only in accordance with the following claims and their equivalents.

