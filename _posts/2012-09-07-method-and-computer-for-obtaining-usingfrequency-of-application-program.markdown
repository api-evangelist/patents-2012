---

title: Method and computer for obtaining using-frequency of application program
abstract: The invention relates to a method or a device for obtaining a using-frequency of a specified application program. The method comprises: obtaining an installing route of the specified application program, according to a system-registering information list; calling an API to monitor operation of the specified application program; recording a last start-up time and the installing route of the specified application program; obtaining the last start-up time of the specified application program based on the installing route as an index; comparing the last start-up time and a current time, to determine the using-frequency of the specified application program. The present invention can intercept the process start functions of the Operation System, to easily and efficiently obtain the using-frequency of the specified application program, easily manage the application program installed in the computer, and provide the base for optimizing the Operation System of the computer.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08930970&OS=08930970&RS=08930970
owner: Tencent Technology (Shenzhen) Company Limited
number: 08930970
owner_city: Shenzhen, Guangdong Province
owner_country: CN
publication_date: 20120907
---
The present application claims the priority of a Chinese patent application which was filed on Sep. 27 2011 the application number of which is 201110296513.8. The present application is also a 35 U.S.C. 371 National Phase conversion of International PCT Patent Application No. PCT CN2012 081150 filed on Sep. 7 2012 the disclosure of which is incorporated by reference herein. The PCT International Patent Application was filed and published in English.

The present invention relates to the computer technology and more particularly to a method and a device for obtaining a using frequency of an application program.

With the development of the computer technology users may install various application programs in operation systems of computers for satisfying various using needs of the users. For the various application programs it is important to obtaining using frequencies of the various application programs such as to optimize the operation systems of the computers according to the using frequencies of the various application programs.

Currently install uninstall list the operation systems of the Windows comes with can judge the using frequencies of the application programs and the judgment thereof is performed according to easy algorithms. Thus the result thereof is not accurate and it is difficult to obtain the real using frequencies of the application programs thus it cannot further provide a system optimization scheme for the users.

The embodiments of the present invention provides a method or a device for obtaining a using frequency of an application program which can accurately count the using frequency of the application program installed in the Operation System of the computer to really report the status of the user using the application program for provide a system optimization scheme for the user.

An embodiment of the present invention provides a method for obtaining a using frequency of a specified application program comprising 

obtaining an installing route of the specified application program according to a system registering information list 

calling an application programming interface API to monitor operation of the specified application program 

obtaining the last start up time of the application program based on the installing route as an index 

comparing the last start up time of the application program and a current time to determine the using frequency of the application program.

Correspondingly another embodiment of the present invention provides a device for obtaining a using frequency of a specified application program comprising 

a route obtaining module configured for obtaining an installing route of the specified application program according to a system registering information list 

a program monitoring module configured for calling an application programming interface API to monitor operation of the specified application program 

an information recording module configured for recording a last start up time and the installing route of the specified application program 

a time obtaining module configured for obtaining the last start up time of the specified application program from the information recording module based on the installing route as an index 

a frequency calculating module configured for comparing the last start up time and a current time to determine the using frequency of the application program.

The present invention can intercept the process start functions of the Operation System to easily and efficiently obtain the using frequency of the specified application program installed in the Operation System of the computer. Therefore the present invention may easily manage the application program installed in the computer and provide the base for optimizing the Operation System of the computer.

The present invention will now be described more specifically with reference to the following embodiments. It is to be noted that the following descriptions of preferred embodiments of this invention are presented herein for purpose of illustration and description only. It is not intended to be exhaustive or to be limited to the precise form disclosed.

The present invention provides a technology for obtaining a using frequency of a specified application program which can accurately count the using frequency of the specified application program installed in the Operation System of the computer for really reporting the status of the user using the specified application program to provide a system optimization scheme for the user.

To clearly describe the exemplary embodiments of the present invention the following firstly introduce technical terms involved in the exemplary embodiments of the present invention.

API Application Programming Interface are some pre defined functions for providing a capability of accessing a group of routines for application programs and developers based on certain software or hardware without accessing source codes or understanding particulars of inner operating mechanism.

Process is the basis of the operation system is an application program which is processing is a program instance which is operating in the computer is able to be distributed to the processor the CPU and is an entity processed by the processor is an action unit which is performing to display in a single sequence and described by a current status and a group of related system resources.

Hook is a system mechanism provided by the Windows for replacing the interrupt under the DOS. After performing the hook for a specific system event if a hooked event occurs a program configured for hooking the event is informed by the system thus the application program can respond to the event in the first period of time.

Application Program is also called as Application Software and is software developed for a certain specific purpose. The application program may be a specific program such as a photo browser. Alternatively the application program also may be a set of a group of programs which are closely associated in function and cooperate with each other such as the Office software. Alternatively the application program also may be a large software system consisted of numerous independent programs such as a database management system.

The method for obtaining the using frequency of the specified application program provided in the exemplary embodiment of the present invention comprises 

Step obtaining an installing route of the specified application program according to a system registering information list 

Step obtaining the last start up time of the specified application program and a current time based on the installing route as an index 

Step comparing the last start up time and the current time to determine the using frequency of the specified application program.

The exemplary embodiment of the present invention uses the system registering information list to accurately obtain the installing route of the specified application program and monitor start up situations of the specified application program based on the installing route such as to judge the using frequency of the specified application program according to the recorded last start up time. The method for obtaining the using frequency of the specified application program provided in the exemplary embodiment of the present invention is real and effective impersonal and accurate such that the user can distinctly know about the using status of the application program installed in the operation system of the computer. Furthermore the user may further optimize the operation system of the computer according to the obtained using frequency of the application program.

The step of obtaining the installing route of the specified application program according to the system registering information list may be performed by following modes 

A first mode obtaining the installing route of the specified application program according to an entry of a key being InstallLocation in the system registering information list.

In detail a program is called to obtain the installing route of the specified application program from the entry of the key being InstallLocation which is under SOFTWARE Microsoft Windows Current Version Uninstall of the system registering information list.

For example is a schematic view for showing all entries of the application program of Autodesk Express Viewer under SOFTWARE Microsoft Windows Current Version Uninstall of the system registering information list. In from the entry of the key being InstallLocation it can be seen that the installing route is C Program Files Autodesk Autodesk Express Viewer .

A second mode obtaining the installing route of the specified application program according to an entry of a key being UnstallString in the system registering information list.

In detail some application programs do not have the entry of the key being InstallLocation in the system registering information list. Therefore the second mode is performed to call a program to read the entry of the key being UnstallString under SOFTWARE Microsoft Windows Current Version Uninstall of the system registering information list and then remove exe file name to obtain the installing route of the application program.

For example is a schematic view for showing all entries of the specified application program of Adobe Flash Player Activex under SOFTWARE Microsoft Windows Current Version Uninstall of the system registering information list. In the entry of the key being InstallLocation does not existed. Thus the entry of the key being UnstallString is found which is presented as C WINDOWS system32 Macromed Flash FlashUtil10w ActiveX.exe maintain activex . Then it removes the exe file name to obtain the installing route of C WINDOWS system32 Macromed Flash .

A third mode fuzzily matching names of shortcuts of application programs with the name of the specified application program recorded in the system registering information list and if successfully matching a name of a shortcut of an application program with the name of the specified application program recorded in the system registering information list obtaining a directing route of the shortcut as the installing route of the specified application program.

In detail some application programs not only do not have the entry of the key being InstallLocation but also do not have the entry of the key being UnstallString in the system registering information list. Therefore the present invention may further enumerate shortcuts of application programs which may be in user desktop start menu or start shortcut etc and then fuzzily matching names of the shortcuts of the application programs with the name of the specified application program in the system registering information list. If successfully matching the present invention may regard the directing route of the shortcut as the installing route of the specified application program.

For example an operation system of a computer has installed application programs such as Tencent TM2009 CHATM2010 Windstorm Image Sound etc and shortcuts of the application programs are located in the user desktop the start menu or the start shortcut etc. respectively. The exemplary embodiment will enumerate the shortcuts then matching the names of the shortcuts with the name of the application program in the system registering information. If a name of a shortcut is CHATM2010 and it successfully matches with CHATM trademark querying software in the system registering information list when they fuzzily matches the directing route of the shortcut is obtained which is as shown in and the directing route of the shortcut is Target T C Rabbit chatm exe Quety net.exe . Then the directing route thereof is regarded as the installing route of the application program of CHATM2010 .

A fourth mode fuzzily matching names of application programs of each project folder of each disk with the name of the specified application program recorded in the system registering information list and if a name of an application program of a project folder of a disk is successfully matched with the name of the specified application program in the system registering information list regarding a route of the application program of the project folder of the disk as the installing route of the specified application program.

In detail for some application programs all of the above three modes cannot obtain the installing route thereof. Thus the fourth mode is used to enumerate application programs of each folder under the project directory of Program Files of each disk and match names of the application programs of each fold under the project directory of Program Files of each disk with the name in the system registering information list. If a name of an application program of a fold under the project directory of Program Files of a disk is successfully matched with the name in the system registering information list the route of the application program of the project folder is regarded as the installing route of the specified application program.

For example a folder named as Movie Maker exists in the folder of Program Files of C disk. If the name of Movie Maker is successfully matched with the name of the specified application program in the system registering information list the route of the application program of Movie Maker is C Program Files Movie Maker and is regarded as the installing route of the specified application program.

For the software located in the directory of system such as Application Verifier Flash Player it needs to use the exepath to match and the method is similar with the above which is not described herein.

It should be noted that the exemplary embodiment may obtain the installing route in sequence from the first mode to the fourth mode. The exemplary embodiment of the present invention use the above four modes to obtain the installing route of the application program thus it can furthest accurately obtain the installing route of the specified application program for analyze the using frequency of the specified application program.

When or after obtaining the installing route of the specified application program the exemplary embodiment of the present invention will call an API to monitor the operation of the specified application program.

Refer to which is a flow chart of the method for obtaining the using frequency of the specified application program in accordance with a second exemplary embodiment of the present invention.

The second exemplary embodiment will describe the flow of calling the API to monitor the operation of the specified application program in detail which comprises 

In detail the monitor of the API Create Process is firstly open. When the Create Process is called the command line arguments in the Create Process are obtained.

Step inputting the command line arguments of the application programs into an independent processing thread.

In detail for not influencing the performance of calling the Create Process the command line arguments are inputted into an independent processing thread in the above Step .

Step monitoring the operation of the application programs corresponding to the command line arguments respectively.

The second exemplary embodiment provides the method for monitoring the various application programs and the above monitoring mode can accurately obtain the status of the operation of the various application programs to obtain the start up time of the various application programs.

Refer to which is a flow chart of the method for obtaining the using frequency of the specified application program in accordance with a third exemplary embodiment of the present invention.

The third exemplary embodiment will describe of the process of how to obtaining the last start up time of the application program and obtaining the using frequency thereof which is described in following 

Step obtaining the last start up time of the specified application program from the processing thread and recording it.

In detail the present invention monitors the various application programs in the processing thread thus it can obtain the start up time of any one specific application program. The exemplary embodiment only needs to record the last start up time of the application programs. Tools for recording the start up time thereof may be notepad or SQlite. It should be noted that the SQlite is a light duty database and complies with the ACID associated database managing system. The SQlite is embedded and occupies little resource and can support the main trend Operation System such as Windows or Linux or Unix etc.

In detail installing routes obtained in the above modes of the present invention may be different in form. Thus the exemplary embodiment needs to perform the standardization process for the installing routes thus they are quickly looked up and compared. The standardization process for the installing routes comprises unifying characters of the installing routes as lowercase characters unifying names of the installing routes to comprise short file names long file names environment variables standardizing the installing routes according to common name rules. For example the installing routes of system and C windows system32 should be uniformly standardized as c windows systems32 .

Step recording the standardized installing route. In detail the present invention may use the tools of Notepad or SQlite to build an application program information list for recording last start up time and installing routes of the various application programs which are shown in table one 

Step obtaining the last start up time of the specified application program according to the standardized installing routes as index.

In detail the present invention uses the standardized installing routes of the above list as the index to look up the last start up time of the application program.

Step comparing the last start up time and the current time to determine the using frequency of the specified application program.

In detail when obtaining the last start up time of the specified application program the exemplary embodiment compares it with the current time. If the period between the last start up time and the current time is less than three days it may determine the application program is often used. If the period between the last start up time and the current time is less than seven days and more than three days it may determine the application program is sometimes used. If the period between the last start up time and the current time is less than thirty days and more than seven days it may determine the application program is seldom used. If the period between the last start up time and the current time is more than thirty days it may determine the application program is never used.

It should be noted that some application programs such as the software of input method the plug in software etc. which should be specifically processed have not the exe files. For these application programs the present invention should call the API Create Process to monitor the using statuses of the dll files which is same with the above description for monitoring the exe files and not described in following.

The method for obtaining the using frequency of the application program of the present invention can intercept the process start function of the system to easily and efficiently obtain the using frequency of the application program installed in the operation system of the computer. Therefore the present invention may easily manage the application program installed in the computer and may provide the base for optimizing the operation system of the computer.

The device for obtaining the using frequency of the specified application program provided in the exemplary embodiment of the present invention comprises 

a route obtaining module configured for obtaining an installing route of the specified application program according to a system registering information list 

a program monitoring module configured for calling an API to monitor the operation of the specified application program 

an information recording module configured for recording a last start up time and the installing route of the specified application program 

a time obtaining module configured for obtaining the last start up time of the specified application program and the current time from the information recording module according to the installing route as an index 

a frequency calculating module configured for comparing the last start up time of the specified application program and the current time to determine the using frequency of the application program.

The device of the exemplary embodiment of the present invention accurately obtains the installing route of the specified application program according to the system registering information list and monitors the start up situations of the application program based on the installing route such as to judge the using frequency of the application program according to the recorded last start up time. The method for obtaining the using frequency of the application program provided in the exemplary embodiment of the present invention is real and effective impersonal and accurate such that the user can distinctly know about the using status of the application program installed in the operation system of the computer. Furthermore the user may further optimize the operation system of the computer according to the obtained using frequency of the application program.

The exemplary embodiment will describe components of the route obtaining module which comprises a directional obtaining unit .

The directional obtaining unit is configured for obtaining the installing route of the specified application program according to an entry of a key being InstallLocation in the system registering information list or obtaining the installing route of the specified application program according to an entry of a key being UnstallString in the system registering information list.

In detail a program is called to obtain the installing route of the application program from the entry of the key being InstallLocation which is under SOFTWARE Microsoft Windows Current Version Uninstall of the system registering information list.

For example as shown in which is a schematic view for showing all entries of the application program of Autodesk Express Viewer under SOFTWARE Microsoft Windows Current Version Uninstall of the system registering information list from the entries of the entry of the key being InstallLocation is found to show the installing route is C Program Files Autodesk Autodesk Express Viewer .

In addition some application programs do not have the entry of the key being InstallLocation in the system registering information list. Therefore the second mode is performed to call a program to read the entry of the key being UnstallString under SOFTWARE Microsoft Windows Current Version Uninstall of the system registering information list and then remove exe file name to obtain the installing route of the application program.

For example as shown in which is a schematic view for showing all entries of the application program of Adobe Flash Player Activex under SOFTWARE Microsoft Windows Current Version Uninstall of the system registering information list the entry of the key being InstallLocation does not existed. Thus the entry of the key being UnstallString is found which is presented as C WINDOWS system32 Macromed Flash FlashUtil10w ActiveX.exe maintain activex . Then it removes the exe file name to obtain the installing route of C WINDOWS system32 Macromed Flash .

The matching unit is configured for fuzzily matching names of shortcuts of application programs with the name of the specified application program recorded in the system registering information list or fuzzily matching names of application programs of each project folder of each disk with the name of the specified application program in the system registering information list.

The route obtaining unit is configured for if successfully matching a name of a shortcut of an application program with the name of the specified application program recorded in the system registering information list obtaining a directing route of the shortcut as the installing route of the specified application program or if successfully matching a name of an application program of a project folder of a disk with the name of the specified application program in the system registering information list regarding a route of the application program of the project folder of the disk as the installing route of the specified application program.

In detail some application programs not only do not have the entry of the key being InstallLocation but also do not have the entry of the key being UnstallString in the system registering information list. Therefore the present invention may further enumerate shortcuts of application programs which may be in user desktop start menu or start shortcut etc and then fuzzily matching names of the shortcuts of the application programs with the name of the specified application program in the system registering information list by the matching unit . If successfully matching the present invention may regard the directing route of the shortcut as the installing route of the specified application program.

For example an operation system of a computer has installed application programs such as Tencent TM2009 CHATM2010 Windstorm Image Sound etc and shortcuts of the application programs are located in the user desktop the start menu or the start shortcut etc. respectively. This step will enumerate the shortcuts then matching the names of the shortcuts with the names of the application programs in the system registering information. If a name of a shortcut is CHATM2010 and it successfully matches with CHATM trademark querying software in the system registering information list when they fuzzily matches the directing route of the shortcut is obtained which is as shown in and the directing route of the shortcut is Target T C Rabbit chatm exe Quety net.exe . Then the directing route thereof is regarded as the installing route of the application program of CHATM2010 .

In addition the matching unit further fuzzily matches names of application programs of each project folder of each disk with the name of the application program in the system registering information list and if a name of an application program of a project folder of a disk is successfully matched with the name of the application program in the system registering information list the route obtaining unit regards a route of the application program of the project folder of the disk as the installing route of the application program.

In detail for some application programs they should enumerate application programs of each folder under the project directory of Project Files of each disk. The matching unit should match names of the application programs with the name of the application program of the system registering information list. If successfully matching the route obtaining unit regards a route of an application program of a project folder which matching with the name of the application program of the system registering information list as the installing route of the application program.

For example a folder named as Movie Maker exists in the folder of Program Files of C disk. If the matching unit successfully matches the name of Movie Maker with the name of the application program in the system registering information list the route obtaining unit regards the route of C Program Files Movie Maker of the application program of Movie Maker as the installing route of the application program.

For the software located in the directory of system such as Application Verifier Flash Player it needs to use the exepath to match and the method is similar with the above which is not described herein.

The route obtaining module of the exemplary embodiment of the present invention may use the above four modes to obtain the installing route of the application program thus it can furthest accurately obtain the installing route of the application program for analyze the using frequency of the application program.

The exemplary embodiment will describe the program monitoring module of the present invention in detail which comprises an interface calling unit a command line processing unit and a program monitoring unit .

The interface calling unit is configured for calling the API to obtain command line arguments of application programs which are running

In detail the monitor of the API Create Process of the interface calling unit is open. When the Create Process is called the command line arguments in the Create Process are obtained.

The command line processing unit is configured for inputting the command line arguments of the application programs into an independent processing thread.

In detail for not influencing the performance of calling the Create Process the command line processing unit inputs the command line arguments into an independent processing thread.

The program monitoring unit is configured for monitoring the operation of the application programs corresponding to the command line arguments respectively.

The device of the exemplary embodiment may pre monitor the running statuses of the various application programs and the above monitoring mode can accurately obtain the status of the various application programs to obtain the start up time of the various application programs.

The exemplary embodiment will describe the components of the information recording module and the functions thereof which are described in following.

The information recording module comprises a time recording unit . The time recording unit is configured for obtaining the last start up time of the application program from the processing thread and recording it.

In detail the program monitoring unit monitors the various application programs in the processing thread and the time recording unit may obtain the start up time of any one specific application program. In the exemplary embodiment the time recording unit only needs to record the last start up time of the application programs. In detail the time recording unit may use notepad or SQlite to record the start up time of the various application programs. It should be noted that the SQlite is a light duty database and complies with the ACID associated database managing system. The SQlite is embedded and occupies little resource and can support the main trend Operation System such as Windows or Linux or Unix etc.

The information recording module may further comprise a route standardizing unit configured for performing a standardization process for the installing route.

In detail installing routes obtained in the above modes of the present invention may be different in form. In the exemplary embodiment the route standardizing unit needs to perform the standardization process for the installing routes thus they are quickly looked up and compared. The standardization process for the installing routes comprises unifying characters of the installing routes as lowercase characters unifying names of the installing routes to comprise short file names long file names environment variables standardizing the installing routes according to common name rules.

The information recording module may further comprise a route recording unit configured for recording the standardized installing route. In detail the route recording unit may use the tools of Notepad or SQlite to build an application program information list for recording the last start up time and the installing routes of the various application programs which are shown in table one.

The time obtaining module looks up the last start up time of the application program under the installing route according to the installing route as the index in the table one recorded by the route recording unit .

The frequency calculating module is configured for comparing the last start up time and the current time to determine the using frequency of the application program.

In detail when the time obtaining module obtains the last start up time of the application program the frequency calculating module compares it with the current time. If the period between the last start up time and the current time is less than three days it may determine the application program is often used. If the period between the last start up time and the current time is less than seven days and more than three days it may determine the application program is sometimes used. If the period between the last start up time and the current time is less than thirty days and more than seven days it may determine the application program is seldom used. If the period between the last start up time and the current time is more than thirty days it may determine the application program is never used.

It should be noted that some application programs such as the software of input method the plug in software etc. which should be specifically processed have not the exe files. For these application programs the present invention should call the API Create Process to monitor the using statuses of the dll files which is same with the above description for monitoring the exe files and not described in following.

The device for obtaining the using frequency of the application program of the present invention can intercept the process start function of the system to easily and efficiently obtain the using frequency of the application program installed in the operation system of the computer. Therefore the device of the present invention may easily manage the application program installed in the computer and may provide the base for optimizing the operation system of the computer.

Those skilled in the art may understand that all or part of the processes in the methods of above mentioned embodiments may be completed via related hardware instructed by the computer program. The program may be stored in a computer readable storage medium. When executing the program the processes of above mentioned method embodiments may be included. The storage medium may be disk Compact Disc CD Read Only Memory ROM or Random Access Memory RAM etc.

The aforementioned are only preferred embodiments of the present invention which are not used for limiting the present invention. Any modifications equivalent substitutions and improvements made within the spirit and principle of the present invention should be covered by the protection scope of the present invention.

