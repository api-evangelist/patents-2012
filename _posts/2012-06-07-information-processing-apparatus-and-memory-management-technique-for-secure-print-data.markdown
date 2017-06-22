---

title: Information processing apparatus and memory management technique for secure print data
abstract: State information about whether a printing apparatus can store print data for confidential printing is acquired. When the print data can be stored, secure information and print data are transmitted, and when the print data cannot be stored, the print data is transmitted after performing authentication based on the secure information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08724137&OS=08724137&RS=08724137
owner: Canon Kabushiki Kaisha
number: 08724137
owner_city: Tokyo
owner_country: JP
publication_date: 20120607
---
The present invention relates to an information processing apparatus that instructs a printing apparatus to perform confidential printing.

Recently to shorten the time after a printing instruction until printing starts there has been a demand to mount a storage device with a capacity capable of storing a predetermined number of print jobs in a printing apparatus. Japanese Patent Application Laid Open No. 11 212744 discusses a printing apparatus including such a storage device which is configured so that to shorten the time after a printing instruction until printing starts print data for a secure job is transmitted to the printing apparatus from an information processing apparatus before user authentication.

However since a printing apparatus configured in this manner cannot store more print data than its capacity when the capacity is exceeded the information processing apparatus cannot transmit new print data which prevents confidential printing from being performed.

According to an aspect of the present invention an information processing apparatus is configured to instruct a printing apparatus to perform confidential printing in which print processing is started after authentication processing is performed by transmitting secure information to be used in the authentication processing to an authentication unit which performs the authentication processing and transmitting print data to be used in the print processing by the printing apparatus to the printing apparatus. The information processing apparatus includes a communication unit configured to communicate bidirectionally with the printing apparatus an acquisition unit configured to acquire state information indicating whether the print data can be stored in the printing apparatus until the print processing is performed from the printing apparatus by the communication unit and a transmission unit configured to if the state information indicates that the print data can be stored transmit the secure information to the authentication unit and transmit the print data to the printing apparatus before performing the authentication processing and if the state information indicates that the print data cannot be stored transmit the secure information to the authentication unit before performing the authentication processing and then transmit the print data to the printing apparatus after authentication by the authentication unit based on the secure information.

Further features and aspects of the present invention will become apparent from the following detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings.

Unless stated otherwise as long as the functions of the present invention can be executed the present invention may obviously be applied in a system configured from a single device or from a plurality of devices. Further unless stated otherwise as long as the functions of the present invention can be executed the present invention can also obviously be applied in a system configured so that processing is performed via a network such as a local area network LAN or a wide area network WAN connected to the system.

In a host computer includes a central processing unit CPU which executes document processing in which graphics images characters tables including spreadsheets etc. and the like are mixed based on a document processing program or the like which is stored in a program read only memory ROM in a ROM or in an external memory . The CPU comprehensively controls each of devices which are connected to a system bus .

An operating system program hereinafter OS which is a control program of the CPU is stored in the program ROM in the ROM or in the external memory . Font data used during the above document processing is stored in a font ROM in the ROM or in the external memory . Various kinds of data used during the above document processing are stored in a data ROM in the ROM or in the external memory .

A random access memory RAM functions as a main memory or a work area of the CPU . An input device interface I F controls inputs from an input device which is a keyboard or a pointing device. A display I F controls the display on a display . An external memory I F controls access to the external memory which is a hard disk HD a Floppy disk FD or the like. The external memory stores a boot program various applications font data user files editing files a printer driver and the like.

A printer I F is connected to a printer via a bidirectional communication pathway and executes communication control processing with the printer . The communication pathway may be a network connection a universal serial bus USB connection an infrared connection or the like via wired or wireless communication.

The CPU opens a program window for the program ROM in the ROM based on a mouse cursor input on a graphical user interface GUI displayed on the display or a key input from the keyboard and executes various types of data processing. Consequently when a user executes printing a window relating to the printing settings is opened so that the printer settings and the setting of the print processing method for the printer driver including selection of a printing mode can be performed.

In the printer communicating with the host computer a CPU outputs an image signal as output information to a printer unit printer engine connected to a system bus based on a control program.

Further a program ROM in a ROM stores a control program that the CPU controls the printer . A font ROM in the ROM stores font data for example that is used when generating the above output information. A data ROM in the ROM stores information that is used by the host computer if the printer does not include an external memory which is a storage device such as a hard disk HD .

The CPU can perform communication processing with the host computer via an input unit and can notify the host computer of information in the printer. A RAM functions as a main memory or a work area of the CPU . The RAM is configured so that its memory capacity can be expanded using an optional RAM connected to an expansion port. The RAM is used as an output information storage region for storing a raster which is output information an environment data storage region and the like. Access to the external memory is controlled by an external memory I F .

The software configuration of the host computer illustrated in or and the processing performed in each processing illustrated in flowcharts are realized by the CPU executing processing based on programs stored in the ROM or the external memory .

The external memory can be optionally connected for storing font data form data and the like. An operation panel is provided with a touch panel or a numerical keypad for operating the printer main body. Further the number of external memories is not limited to one. At least one or more thereof is included. The external memory can be configured so that a plurality of external memories storing an optional font card in addition to the built in fonts and a program for interpreting printer control languages of different language systems can be connected.

These files are executed by being called up by the OS or a program and loaded into the RAM . The application and the printer driver may be added to a FD a CD ROM in the external memory or a HD of the external memory via a network.

As described above the application is loaded into the RAM from the external memory and executed. When using the printer to perform printing from the application output drawing is performed utilizing the graphics engine which has similarly been loaded into the RAM and made ready for execution.

The graphics engine loads the printer driver which has been prepared for each printing apparatus from the external memory into the RAM . The printer driver converts the output document data of the application into a print job based on the print setting of the printer driver . The converted print job is output to the printer from the spooler which has been loaded into the RAM by the OS via the language monitor and then the communication pathway .

Print processing performed in the language monitor according to the present exemplary embodiment will be described below with reference to a flowchart illustrated in .

When document printing is executed from the application the printer driver is called via the graphics engine . Next the printer driver transmits a print job generated by converting document data into a print command which is referred to as a page description language PDL based on a print setting to the spooler .

Then in step S the spooler calls the language monitor designated by the printer driver and the reception determination unit receives the print job from the spooler . In step S the reception determination unit determines whether a personal identification number or a password is set in the print job received in step S.

In the print job the header region is stored as setting data. The setting data includes the secure information and a print setting other than the secure information. The print job is configured from setting data and print data in which the document region is stored as the print data. Unless stated otherwise in the present exemplary embodiment the print data is included in the print job.

In the present exemplary embodiment although the secure information is set by the printer driver the secure information can also be set by the application or the language monitor . Further the user name does not have to be set.

Examples of secure information other than a user name and a personal identification number may include a password a contact type or non contact type key or card biometrics and a combination of these. However the present exemplary embodiment will be described based on setting the user name and the personal identification number .

In step S if it is determined that a personal identification number is not set for the print job NO in step S the processing proceeds to step S. In step S the transmission processing unit transmits a normal print job in which a personal identification number is not set to the printer and a print product is output.

On the other hand if it is determined that a personal identification number is set for the print job YES in step S the processing proceeds to step S. In step S the device communication unit communicates with the printer and acquires information i.e. state information that will be necessary in step S. As described below the state information is information that indicates whether the print data can be stored until the printing apparatus performs print processing.

In the present exemplary embodiment the state information is information illustrated in about the free space in the external memory of the printer . In addition information illustrated in may also be acquired. The information indicates an upper limit for the number of print jobs that can be currently stored in the external memory by the printer and the number of print jobs that are actually stored at the moment.

Print job information as illustrated in for example can also be transmitted from the device communication unit in the host computer to the printer . Further information as illustrated in indicating whether a print job can be stored in the external memory by the printer can also be acquired from the printer . More specifically the information is information generated by calculating a secure job size and a total size A of the setting data and the print data. The information is information generated by comparing a size B of the print jobs that can be stored by the printer and the size A of the information . The information indicates that a print job can be stored when the size A does not exceed the size B and indicates that a print job cannot be stored when the size A exceeds the size B.

In step S the transmission determination unit determines whether to transmit the secure job to the printer based on the information acquired in step S. In the present exemplary embodiment whether to transmit the secure job to the printer is determined by comparing the information indicating the free space of the external memory in the printer acquired by the transmission determination unit in step S with the size of the print data or the print job. More specifically if the size of the print data or the print job does not exceed the size indicated by the information since the printing apparatus can store print data it is determined to transmit the secure job YES in step S . On the other hand if the size of the print data or the print job exceeds the size indicated by the information since the printing apparatus cannot store print data it is determined not to transmit the secure job NO in step S .

If acquiring the information in step S it is determined whether to transmit the secure job to the printer based on whether the printer upper limit will be exceeded when the next print job is transmitted. More specifically if the upper limited has been reached since print data cannot be stored the secure job is not transmitted. If the upper limited has not been reached since print data can be stored the secure job is transmitted. If the upper limit for the number of print jobs in the printer is uniquely determined by the printer model a local file or database that separately stores the print job upper limit may be referred to.

If acquiring the information from the printer it is determined whether to transmit the secure job to the printer based on the acquired information .

In step S if it is determined that the secure job can be transmitted to the printer YES in step S the processing proceeds to step S. In step S the secure job is transmitted to the printer . Then an authentication unit that performs user authentication i.e. authentication processing compares and determines whether the personal identification number input corresponding to the secure job selected on the panel of the printer and the personal identification number of the secure job match each other. If they do match i.e. after authentication processing is successful a print product is output based on the print data. If they do not match the printer stores the secure job until it is authenticated and confidential printing is not performed.

On the other hand if it is determined that the secure job cannot be transmitted to the printer NO in step S the processing proceeds to step S. In step S the transmission processing unit transmits only the secure information i.e. the user name and the personal identification number input in the header region of the secure job to the authentication unit in the printer and then the processing proceeds to step S. When a job name is displayed in a list of jobs in the printer the secure information and the job name can be transmitted to the authentication unit .

After the host computer transmitted the secure information to the printer if a job having only secure information is selected on the panel in the printer the personal identification number input information input for the job having only secure information is transmitted to the authentication unit . Then the authentication unit determines whether the input personal identification number matches the personal identification number in the secure information.

More specifically the printer determines whether the information input to the printer is correct. If the input information is correct the host computer receives authentication information indicating that user authentication was successful.

The user authentication is configured in the following manner in a case where both a user name and personal identification number are required to be input for the user authentication. More specifically the user name input to the printer and the user name in the secure information and the personal identification number input to the printer and the personal identification number in the secure information are respectively compared and determined whether they match. The similar processing is performed for user authentication based on biometrics a key or a card.

In step S if the transmission processing unit has not received the authentication information from the authentication unit in the printer NO in step S then in step S the transmission processing unit suspends the print data transmission until the authentication information is received from the printer . When the authentication information is received YES in step S the processing proceeds to step S.

In step S the transmission processing unit deletes the secure information in the header region of the secure job and converts the job into a normal print job that does not include a personal identification number or a password. Then the processing proceeds to step S.

Next in step S the transmission processing unit adds information indicating that the job is the secure job i.e. metadata to the header region of the print job. Consequently since an administrator of the printer can manage the print job as the secure job when looking at a print job log of the printer for example the administrator can retrieve the fact that the job is the secure job as metadata.

Then in step S the transmission processing unit transmits the normal print job that includes information in the header region indicating that the job is the secure job to the printer and a print product is output.

If processing is performed based on the flowchart illustrated in when there is a free space in the printer storage device confidential printing can be executed by transmitting the print data before user authentication. Even if there is no free space confidential printing can be executed by transmitting the print data after user authentication.

In the present exemplary embodiment although the printer includes the authentication unit an authentication server provided for the printer may include the authentication unit. In this case the personal identification number is input by the authentication server and the host computer receives the authentication information from the authentication server.

In this case the printer and the authentication server can be regarded as an integrated printing apparatus.

A second exemplary embodiment in which the authentication unit is on the host computer side will now be described. In the present exemplary embodiment as illustrated in an authentication unit is in the language monitor and exists between the transmission determination unit and the transmission processing unit . However the location of the authentication unit is not limited as long as it can receive the secure information included in the secure job and input information from the printer . Further the authentication unit may be a program or a module other than a printer driver a port monitor a print processor or a language monitor.

The printing flow according to the present exemplary embodiment will be described based on the flowchart illustrated in . In the processing in steps S to S and steps S to S are the same as in . Therefore only the steps other than those will be described.

In step S the transmission processing unit transmits a dummy job for performing confidential printing to the printer and the processing proceeds to a module S.

The dummy job is a print job that does not include print data or that is empty. If printing of the dummy job is selected by the printer input of the personal identification number to the input panel of the printer is requested just as with normal confidential printing. The printer transmits the personal identification number input by the user i.e. the input information to the host computer .

Although the dummy job does not include print data to distinguish the dummy job from other print jobs in the printer the dummy job may be transmitted including a job name or a user name. If a job name or a user name is included the printer displays the job name and the user name in the job list based on those names.

In step S the authentication unit receives the input information notified from the printer and the processing proceeds to step S. In step S the authentication unit determines whether the input information notified from the printer matches the personal identification number . If the input information matches the personal identification number YES in step S the processing proceeds to step S in . If the input information does not match the personal identification number NO in step S the processing proceeds to step S.

In step S the transmission processing unit stores the secure job in the host computer and the processing proceeds to step S. In step S the transmission processing unit issues a request to the printer for re input of the personal identification number and the processing returns to step S. The printer receives the request and requests the user to re input the personal identification number. Alternatively the printer displays an error message and keeps the dummy job in the job list. Consequently the user can input the personal identification number by again instructing printing of the dummy job.

After the processing in the module S has finished in step S the print data is transmitted to the printer and then the printer discards the dummy job and printing is performed based on the print data transmitted in step S

In step S if it is determined that the print data is transmitted to the printer YES in step S in step S the secure information is not transmitted to the printer . Instead the printer adds information requesting user authentication to the header region in the job similar to a dummy job and the processing proceeds to a module S. The module S executes the same processing as the module S so that confidential printing is executed.

The advantage of the second exemplary embodiment is that it is not necessary to transmit secure information to the printer. Consequently since the secure information is not transmitted via the communication pathway if an instruction is issued for confidential printing the secure information is not leaked externally even if the information is intercepted at the communication pathway for example.

In the print processing in the first and second exemplary embodiments there is an issue that when user authentication has not finished even though the secure information has already been transmitted to the authentication unit if the host computer is shutdown the print data is not transmitted to the printer so that printing is not performed.

In a third exemplary embodiment print processing will be described for a case in which if the host computer is shutdown before user authentication confidential printing is performed by having the host computer save print data in another computer.

In the present exemplary embodiment the processing performed during shutdown of the language monitor when the authentication unit is in the printer will be described with reference to the flowchart illustrated in .

In step S the reception determination unit instructs the OS to block shutdown by the host computer and the processing proceeds to step S. In step S the reception determination unit determines whether there are any secure jobs still stored in the language monitor . If it is determined that there are no secure jobs still stored in the language monitor NO in step S the processing proceeds to step S. In step S the reception determination unit instructs the OS to release the shutdown block placed on the host computer in step S and shutdown processing is finished.

On the other hand if it is determined that there is the secure job still stored in the language monitor YES in step S the processing proceeds to step S. In step S the transmission determination unit determines whether a job save setting is set.

In the present exemplary embodiment although the job save setting is set by the printer driver the job save setting can also be set by the printer . The job save setting can be set as a part of the initial settings when the printer is installed. Further when the job save setting is set in the printer the device communication unit acquires job save setting information from the printer .

In step S if it is determined that the job save setting is not set NO in step S the processing returns to step S. Consequently the instruction to shut down the host computer is blocked until either in step S the jobs still stored in the language monitor are all gone or in step S the job save setting is set.

On the other hand if it is determined that the job save setting is set YES in step S the processing proceeds to step S. In step S the transmission processing unit deletes the secure information in the header region of the secure job and converts the job into a normal print job that does not include a personal identification number or a password.

In step S the transmission processing unit adds information indicating that the job is the secure job to the header region of the print job. Then in step S the transmission processing unit transmits the normal print job in which the information indicating that the job is the secure job is included in the header region to an external information processing apparatus based on job save location information in the job save setting and the processing proceeds to step S.

In step S the device communication unit notifies the printer that the external information processing apparatus which is the job save destination is a new transmission destination for the authentication information. By transmitting information about the new authentication information transmission destination to the printer the authentication information is notified from the printer to the job save destination if the user authentication is executed by the authentication unit in the printer. When the job save destination receives the authentication information from the printer the normal print job in which the information indicating that the job is the secure job is included in the header region is transmitted to the printer .

In step S the reception determination unit instructs the OS to release the shutdown block placed on the host computer in step S and shutdown processing is finished.

The external information processing apparatus used in the present exemplary embodiment can have the same configuration as the host computer illustrated in or can be a file server such as a network attached storage NAS device.

Next the processing performed during shutdown of the language monitor when the authentication unit is in the host computer will be described with reference to the flowchart illustrated in .

In step S the reception determination unit instructs the OS to block shutdown by the host computer and the processing proceeds to step S.

In step S if shutdown is performed by the host computer the reception determination unit determines whether there are any secure jobs still stored in the language monitor . If it is determined that there are no secure jobs still stored in the language monitor NO in step S the processing proceeds to step S. In step S the reception determination unit instructs the OS to release the shutdown block placed on the host computer in step S and shutdown processing is finished.

On the other hand if it is determined that there is the secure job still stored in the language monitor YES in step S the processing proceeds to step S. In step S the transmission determination unit determines whether the job save setting is set.

In the present exemplary embodiment although the job save setting is set by the printer driver the job save setting can also be set by the printer . Further when the job save setting is set in the printer the device communication unit acquires the job save setting information from the printer .

In step S if it is determined that the job save setting is not set NO in step S the processing returns to step S. Consequently the instruction to shut down the host computer is blocked until either in step S the jobs still stored in the language monitor are all gone or in step S the job save setting is set.

On the other hand if it is determined that the job save setting is set YES in step S the processing proceeds to step S. In step S the transmission determination unit makes an inquiry to the save destination about whether the external information processing apparatus which is the job save destination in the job save setting can receive the save data and the processing proceeds to step S.

In step S the transmission determination unit waits for a predetermined period until there is a response to the inquiry made in step S. Next in step S the transmission determination unit determines whether there has been a response to the inquiry made in step S. If there has been a response YES in step S the processing proceeds to step S and if there has not been a response NO in step S the processing returns to step S.

In step S the transmission determination unit determines whether the save destination can receive the save data based on the response obtained in steps S to S. If it is determined that the save destination can receive the save data YES in step S the processing proceeds to step S. Whereas if it is determined that the save destination cannot receive the save data NO in step S the processing returns to step S.

In step S the transmission processing unit extracts the secure information included in the header region of the secure job and converts the job into a normal job that does not include a personal identification number or a password.

In step S the transmission processing unit adds information indicating that the job is the secure job to the header region of the normal print job converted in step S.

In step S the transmission processing unit transmits the secure information extracted in step S and the normal print job generated in step S based on the job save location information in the job save setting.

In step S the reception determination unit instructs the OS to release the shutdown block placed on the host computer in step S and shutdown processing is finished.

As described above the secure information is also transmitted to the job save destination so that user authentication can be performed at the job save destination. If the user authentication is executed by the authentication unit at the job save destination the job save destination transmits to the printer the normal print job in which information indicating that the job is the secure job is included.

A save personal computer PC service executed by the external information processing apparatus of the save destination to which the inquiry is made in step S in will now be described with reference to .

The configuration of the external information processing apparatus in this case is the same as that of the host computer illustrated in . The save PC service illustrated in and the user authentication illustrated in are read into the RAM from the program ROM in the external information processing apparatus and executed by the CPU.

In the following the device that makes an inquiry about the saving is a PC and the device that makes an inquiry about the user authentication is a printing apparatus.

In step S it is determined whether the external information processing apparatus has received an inquiry. If it is determined that the inquiry has been received YES in step S the processing proceeds to step S. Whereas if the inquiry has not been received NO in step S the external information processing apparatus waits until it does receive an inquiry.

In step S it is determined whether the source of the inquiry received in step S is the PC i.e. the host computer illustrated in .

The method for determining the inquiry source can be performed by reading a header of a protocol or by determining whether the inquiry source is a defined application programming interface API .

Further it can be determined that if an inquiry about the saving is made the inquiry source is the PC and if an inquiry about the user authentication is made the inquiry source is the printing apparatus.

In step S if it is determined that the inquiry source is the PC YES in step S the processing proceeds to step S. Whereas if it is determined that the inquiry source is not the PC NO in step S the processing proceeds to step S.

In step S it is determined whether the save data of the host computer can be received by the external information processing apparatus. If it is determined that the save data can be received YES in step S the processing proceeds to step S and if it is determined that the save data cannot be received NO in step S the processing proceeds to step S.

The external information processing apparatus determines whether it can receive the save data based on whether there is space in the external memory for storing the save data.

In step S the external information processing apparatus notifies the host computer that it can receive the save data and the processing proceeds to step S. Based on the processing in step S the transmission determination unit in the host computer grasps that the save data can be received by the external information processing apparatus and performs the determination in step S. In step S the external information processing apparatus receives the save data from the host computer .

In step S it is determined whether the printer made the inquiry. If it is determined that the printer made the inquiry YES in step S the processing proceeds to step S. Whereas if it is determined that the printer did not make the inquiry NO in step S the external information processing apparatus waits until it again receives an inquiry.

In step S the external information processing apparatus executes the user authentication illustrated in . When the user authentication has finished the processing proceeds to step S. In step S the print job is transmitted to the printer and the external information processing apparatus waits until it again receives an inquiry.

In step S the external information processing apparatus notifies the host computer of the fact that it cannot receive the save data and waits until it again receives an inquiry.

When the host computer is shutdown the host computer cannot be shutdown until the secure job in the language monitor has all gone based on the processing in the flowcharts illustrated in and . Therefore it can prevent a secure job from losing.

In a fourth exemplary embodiment secure information is generated by an encryption server. In the present exemplary embodiment if the authentication unit is in the printer the encryption server transmits the secure information to the authentication unit in the printer. If the authentication unit is in the encryption server a program in the encryption server transmits the secure information to the authentication unit. If the authentication unit is in the host computer the encryption server transmits the secure information to the host computer.

In the present exemplary embodiment the host computer and the encryption server can be regarded as an integrated information processing apparatus.

Although the above exemplary embodiment is described with reference to the language monitor any device can be employed as long as such device can store a print job. For example a port monitor and a print processor may be employed.

Further the printer driver may include a transmission control unit and a transmission determination unit for example and these units in the printer driver may execute the above described processing.

According to the exemplary embodiments of the present invention confidential printing can be performed regardless of whether print data from a printing apparatus can be received or not.

Aspects of the present invention can also be realized by a computer of a system or apparatus or devices such as a CPU or an MPU that reads out and executes a program recorded on a memory device to perform the functions of the above described embodiments and by a method the steps of which are performed by a computer of a system or apparatus by for example reading out and executing a program recorded on a memory device to perform the functions of the above described embodiments. For this purpose the program is provided to the computer for example via a network or from a recording medium of various types serving as the memory device e.g. computer readable medium .

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

This application claims priority from Japanese Patent Application No. 2011 139735 filed Jun. 23 2011 which is hereby incorporated by reference herein in its entirety.

