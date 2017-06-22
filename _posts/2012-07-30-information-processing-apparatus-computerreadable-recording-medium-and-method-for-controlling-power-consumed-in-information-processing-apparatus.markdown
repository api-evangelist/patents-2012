---

title: Information processing apparatus, computer-readable recording medium, and method for controlling power consumed in information processing apparatus
abstract: An information processing apparatus includes a processor that executes a plurality of application programs, a display that displays results of the execution of the plurality of application programs, and a storage that stores a first table in which the plurality of application programs and a plurality of pieces of operation information corresponding to the plurality of application programs are associated with each other and recorded, and a second table in which the plurality of application programs and order determined on the basis of power to be consumed by the processing unit to execute the plurality of application programs are associated with each other and recorded.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08935552&OS=08935552&RS=08935552
owner: Fujitsu Limited
number: 08935552
owner_city: Kawasaki
owner_country: JP
publication_date: 20120730
---
This application is based upon and claims the benefit of priority of the prior Japanese Patent Application No. 2011 184194 filed on Aug. 25 2011 the entire contents of which are incorporated herein by reference.

The embodiments discussed herein are related to an information processing apparatus an information control program and a method for controlling information.

When a peripheral device such as wireless communication or a Global Positioning System GPS is used by a mobile terminal such as a mobile phone power consumption significantly increases. In order to extend the life of a battery of the mobile terminal for example a technique has been disclosed in which an Operating System OS and middleware have a function of permitting use of a peripheral device when an application prepares an Application Programming Interface API for declaring the beginning and the end of use of the peripheral device and uses the API. For example there has been a technique in which a system monitors the operation of an application and detects the beginning and the end of access to a peripheral device.

In the above described techniques because both the OS and the application are to be corrected it is difficult to additionally introduce the techniques to some of terminals that allow a user to freely download and install various applications such as smartphones. It is also difficult to revise the format of each application package in such a way as to add to each application package a definition as to which peripheral device is to be used by the application package. When the operation of an application is continuously monitored the application and an API are not corrected because the system detects use of a peripheral device by the application. However when the operation of an application is continuously monitored the system load increases due to the monitoring thereby increasing the power consumption of the terminal and deteriorating the response of the system.

Examples of the related art include Japanese Laid open Patent Publication No. 11 73255 and Japanese Laid open Patent Publication No. 2009 93295.

According to an aspect of the embodiments an information processing apparatus includes a processor that executes a plurality of application programs a display that displays results of the execution of the plurality of application programs and a storage that stores a first table in which the plurality of application programs and a plurality of pieces of operation information corresponding to the plurality of application programs are associated with each other and recorded and a second table in which the plurality of application programs and order determined on the basis of power to be consumed by the processing unit to execute the plurality of application programs are associated with each other and recorded wherein when the processor detects a certain piece of operation information the processor refers to the first table to detect an application program corresponding to the certain piece of operation information and refers to the second table to detect a place of the detected application program in the order and when the processor detects that a remaining amount of electric charge of a power supply that supplies power to the information processing apparatus has become lower than a threshold the processor terminates in accordance with the order application programs among the plurality of application programs that are being executed other than an application program whose result of execution is displayed on the display.

The object and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the invention as claimed.

The information processing apparatus includes a central processing unit CPU a main memory an auxiliary memory a clock supply circuit a voltage supply circuit a radio frequency RF unit an antenna and a battery as hardware modules. The information processing apparatus also includes a power supply circuit a camera module a Bluetooth registered trademark interface a GPS module a liquid crystal display LCD sensors and an external feeding unit as hardware modules. The hardware modules are coupled to one another by for example a bus .

The CPU controls the entirety of the information processing apparatus . The CPU is operated by a clock signal supplied from the clock supply circuit and voltage supplied from the voltage supply circuit . The main memory is for example a random access memory RAM . The main memory is used as a work area of the CPU .

The auxiliary memory is for example a non volatile memory such as a hard disk or a flash memory. The auxiliary memory stores various programs for operating the information processing apparatus . The programs stored in the auxiliary memory are loaded into the main memory and executed by the CPU . Thus various programs that will be described later are executed by the information processing apparatus .

The clock supply circuit supplies a clock signal of variable frequency to the CPU . The clock supply circuit may be realized for example by a crystal oscillator that generates a clock signal a real time clock RTC and the like. The voltage supply circuit supplies variable voltage to the CPU using power supplied from the power supply circuit . The voltage supply circuit may be realized for example by a voltage detector a voltage regulator and the like.

The RF unit is controlled by the CPU to realize a function of a transmitter that transmits a high frequency signal from the antenna to another wireless communication apparatus. The RF unit also has a function of a receiver that converts a high frequency signal received by the antenna into a baseband signal and outputs the baseband signal to the CPU .

The battery supplies power to the power supply circuit . The battery may be realized for example by a battery such as a lithium ion battery an integrated circuit IC for protecting the battery and the like. The power supply circuit supplies power supplied from the battery to each hardware module in the information processing apparatus . When an external power supply has been coupled to the external feeding unit the power supply circuit may supply power supplied from the external feeding unit to each hardware module in the information processing apparatus . The power supply circuit may be realized for example by a switching regulator and a voltage regulator.

The camera module is controlled by the CPU to capture an image of a subject and obtains image data generated by the capture. The Bluetooth interface is a communication interface that is controlled by the CPU to execute wireless communication with another communication apparatus through Bluetooth. In addition to the Bluetooth interface the information processing apparatus may include a wireless communication interface such as a wireless local area network LAN .

The GPS module is controlled by the CPU to obtain positional information indicating the current position of the information processing apparatus on the Earth by receiving a radio wave generated by an artificial satellite.

The LCD is an image display apparatus that is controlled by the CPU to display an image for a user. The LCD may be a touch panel having a function of inputting a position such as a touch pad.

The sensors are controlled by the CPU to obtain information indicating states of the inside of the information processing apparatus . The sensors may include for example an acceleration sensor a gyro sensor an illumination sensor a geomagnetic sensor an inclination sensor a pressure sensor an approach sensor and a temperature sensor.

Users of smartphones download from networks paid and free application packages provided by application developers around the world and use the application packages by installing the application packages on terminals. Therefore for security purposes access permission information indicating whether or not to execute data communication whether or not to use a wireless LAN whether or not to execute high accuracy location using a GPS whether or not to read personal information regarding a user and the like is attached to the application packages. The user refers to the access permission information and judges whether or not to actually use a particular application package and if the application package tries to execute an operation that is not permitted in the access permission information attached to the application package the system stops the execution. Therefore in the case of smartphones the access permission information attached to the application packages is saved to the terminals when the application packages are installed.

The application package includes an application program a setting file attached data and access permission information. An application management unit manages various applications. The application management unit stores the application program the setting file and the attached data in storage . The application management unit stores the name of an application the access permission information and program storage information in a package information database DB .

In step S the application management unit creates an entry of an application package to be installed in the package information DB . The application management unit then causes the process to proceed to step S.

In step S the application management unit obtains a program and data from the application package and writes the program and the data to a file system. The application management unit then causes the process to proceed to step S.

In step S the application management unit records the program the name of a data file and access permission information. The application management unit then terminates the process.

In step S the application management unit searches the package information DB using the name of an application and identifies a program and the name of a data file. The application management unit then causes the process to proceed to step S.

In step S the application management unit deletes the program and the data file. The application management unit then causes the process to proceed to step S.

In step S the application management unit obtains a program and data from the application package and writes the program and the data to the file system. The application management unit then causes the process to proceed to step S.

In step S the application management unit records the program the name of the data file and access permission information in the package information DB . The application management unit then terminates the process.

In step S the application management unit searches the package information DB using the name of an application and identifies a program and the name of a data file. The application management unit then causes the process to proceed to step S.

In step S the application management unit deletes the program and the data file. The application management unit then causes the process to proceed to step S.

In step S the application management unit deletes an entry of an application to be uninstalled from the package information DB . The application management unit then terminates the process.

In step S the application management unit searches the package information DB using the name of an application and obtains access permission information. The application management unit then causes the process to proceed to steps S.

In step S the application management unit overwrites the access permission information regarding an application to be corrected. The application management unit then terminates the process.

In smartphones power consumption is large when a particular peripheral device is accessed such as when data communication is performed using a wireless device such as a wireless LAN or a 3G network or when high accuracy location is performed using the GPS as well as when an application executes an operation for inhibiting a terminal whose LCD has been turned off from entering a sleep mode. There is already access permission information corresponding to these operations that cause power consumption to increase.

By reading access permission information regarding all applications that have been installed on a smartphone it is possible without executing applications to judge whether or not the individual applications execute any of the operations that cause power consumption to increase and if any of the operations is executed to identify which operation is executed.

A terminal manufacturer judges how much power a certain peripheral device consumes and how much power a CPU consumes when a terminal continues to operate without sleeping. The relationship between the amounts of power consumption when these operations are performed remains the same regardless of the types of terminals. Therefore a third party for example a developer of an application that terminates itself in accordance with the remaining amount of electric charge of a battery other than the terminal manufacturer also provides this information.

In the first embodiment by referring to the above described two types of information a group of applications created on the basis of the operations that cause power consumption to increase is arranged in order of the amount of power consumption.

In the first embodiment applications are classified in accordance with the amounts of power consumption when the CPU has executed the applications. It is seen from the class application type correspondence table that power consumed by the CPU to execute an application use of GPS or reproduction of music is larger than power consumed by the CPU to execute an application data communication . When the applications use of GPS reproduction of music and data communication are being executed at the same time the applications use of GPS and reproduction of music are to be terminated prior to the application data communication .

In the first embodiment an application telephone is not the target of forced termination. The user adds to change possible an application that the user does not wish to be a target of forced termination.

In step S the forced termination target application list maintenance unit judges whether or not there is a forced termination target application list reconstruction event. If there is a forced termination target application list reconstruction event the forced termination target application list maintenance unit causes the process to proceed to step S. On the other hand if there is no forced termination target application list reconstruction event the forced termination target application list maintenance unit causes the process to proceed to step S.

In step S the forced termination target application list maintenance unit waits for a certain period of time and then returns the process to step S.

In step S the forced termination target application list maintenance unit executes the procedure for processing a list. The forced termination target application list maintenance unit then returns the process to step S.

In step S the forced termination target application list maintenance unit judges whether or not all the applications that have been installed have been processed. If all the applications that have been installed have been processed the forced termination target application list maintenance unit terminates the process. On the other hand if not all the applications that have been installed have been processed the forced termination target application list maintenance unit causes the process to proceed to step S.

In step S the forced termination target application list maintenance unit obtains the names of applications that have been installed and the access permission information from the package information DB . The forced termination target application list maintenance unit then causes the process to proceed to steps S.

In step S the forced termination target application list maintenance unit reads the application type access permission information correspondence table . The forced termination target application list maintenance unit then causes the process to proceed to step S.

In step S the forced termination target application list maintenance unit identifies the type of application to which a target application belongs. The forced termination target application list maintenance unit then causes the process to proceed to step S.

In step S the forced termination target application list maintenance unit reads the class application type correspondence table . The forced termination target application list maintenance unit then causes the process to proceed to step S.

In step S the forced termination target application list maintenance unit identifies a class number to which the application belongs. The forced termination target application list maintenance unit then causes the process to proceed to step S.

In step S the forced termination target application list maintenance unit judges whether or not the application belongs to any class. If the application belongs to any class the forced termination target application list maintenance unit causes the process to proceed to step S. On the other hand if the application does not belong to any class the forced termination target application list maintenance unit returns the process to step S.

In step S the forced termination target application list maintenance unit registers the application to the forced termination target application list . The forced termination target application list maintenance unit then returns the process to step S.

By referring to the forced termination target application list created by the above process and the list of applications operating in the background obtained from an application judgment unit an application control unit instructs an OS to execute forced termination. A battery remaining amount monitoring unit monitors the remaining amount of electric charge of the battery. With respect to the timing of generation of an event the battery remaining amount monitoring unit notifies the application control unit of the name of the class of an application to be terminated when the remaining amount of electric charge of the battery has decreased to a certain threshold.

The battery remaining amount class correspondence table indicates that when the remaining amount of electric charge of the battery in the information processing apparatus has become 50 the applications navigation and music associated with a class name of 1 become the targets of forced termination. When the remaining amount of electric charge of the battery in the information processing apparatus has decreased to a certain threshold the battery remaining amount monitoring unit refers to the battery remaining amount class correspondence table and notifies the application control unit of the class name of an application to be terminated. The application control unit instructs the OS to execute forced termination by referring to the forced termination target application list and the list of applications operating in the background obtained from the application judgment unit . The OS terminates the application to be terminated on the basis of the instruction issued from the application control unit .

The application judgment unit obtains the list of applications operating in the background and transmits the list to the application control unit . The battery remaining amount monitoring unit monitors the remaining amount of electric charge of the battery . The application control unit refers to the forced termination target application list generated by the above described process and the list of applications operating in the background transmitted from the application judgment unit . If there is the name of an application operating in the background in the forced termination target application list the application control unit instructs the OS to execute forced termination to terminate the application. The OS terminates the application on the basis of the instruction issued from the application control unit .

In step S the application control unit judges whether or not an application forced termination event notification has been received from the battery remaining amount monitoring unit . If an application forced termination event notification has been received the application control unit causes the process to proceed to step S. On the other hand if an application forced termination event notification has not been received the application control unit repeats the processing in step S.

In step S the application control unit obtains the list of applications operating in the background from the application judgment unit . The application control unit then causes the process to proceed to step S.

In step S the application control unit reads a list of applications having a class number corresponding to the application forced termination event from the forced termination target application list . The application control unit then causes the process to proceed to step S.

In step S the application control unit detects an application that matches an application operating in the background in the read application list. The application control unit then causes the process to proceed to step S.

In step S the application control unit instructs the OS to terminate the matched application as a target. The application control unit then causes the process to proceed to step S.

In step S the application control unit waits for a certain period of time. The application control unit then returns the process to step S.

In step S the application judgment unit judges whether or not a notification has been received from the application control unit . If a notification has been received from the application control unit the application judgment unit causes the process to proceed to step S. On the other hand if a notification has not been received from the application control unit the application judgment unit causes the process to proceed to step S.

In step S the application judgment unit obtains the list of operating applications. The application judgment unit then causes the process to proceed to step S.

In step S the application judgment unit obtains the names of applications currently operating in the foreground. The application judgment unit then causes the process to proceed to step S.

In step S the application judgment unit excludes the applications operating in the foreground from the list of operating applications. The application judgment unit then causes the process to proceed to step S.

In step S the application judgment unit notifies the created list of applications to the application control unit . The application judgment unit then causes the process to proceed to step S.

In step S the application judgment unit waits for a certain period of time. The application judgment unit then returns the process to step S.

In step S the battery remaining amount monitoring unit sets the remaining amount of electric charge of the battery at the time of the previous check to 100. The battery remaining amount monitoring unit then causes the process to proceed to step S.

In step S the battery remaining amount monitoring unit reads the battery remaining amount class correspondence table . The battery remaining amount monitoring unit then causes the process to proceed to step S.

In step S the battery remaining amount monitoring unit reads the remaining amount of electric charge of the battery . The battery remaining amount monitoring unit then causes the process to proceed to step S.

In step S the battery remaining amount monitoring unit reads the remaining amount of electric charge of the battery at the time of the previous check. The battery remaining amount monitoring unit then causes the process to proceed to step S.

In step S the battery remaining amount monitoring unit judges whether or not the remaining amount of electric charge of the battery has decreased below the threshold. If the remaining amount of electric charge of the battery has decreased below the threshold the battery remaining amount monitoring unit causes the process to proceed to step S. On the other hand if the remaining amount of electric charge of the battery has not decreased below the threshold the battery remaining amount monitoring unit causes the process to proceed to step S.

In step S the battery remaining amount monitoring unit notifies the application control unit of an application forced termination event. The battery remaining amount monitoring unit then causes the process to proceed to step S.

In step S the battery remaining amount monitoring unit overwrites the remaining amount of electric charge of the battery at the time of the current check on the remaining amount of electric charge of the battery at the time of the previous check. The battery remaining amount monitoring unit then causes the process to proceed to step S.

In step S the battery remaining amount monitoring unit waits for a certain period of time. The battery remaining amount monitoring unit then returns the process to step S.

According to the first embodiment by utilizing the access permission information used for security purposes it is possible to classify applications into groups without correcting the existing applications or OSs analyzing the operation of the applications or measuring the power consumption. By terminating when the remaining amount of electric charge of a battery has decreased operating applications that belong to a group of applications whose power consumption is large in accordance with this classification it is possible to increase the life of the battery in a terminal.

In a second embodiment a timer is used for events. The timer is registered to a core kernel of an OS or the like so that events are generated at certain intervals and the access permission information regarding all the applications that have been installed is analyzed when an event is generated thereby completely revising the tables.

In step S the forced termination target application list maintenance unit executes a procedure for processing a list. The forced termination target application list maintenance unit then causes the process to proceed to step S.

In step S the forced termination target application list maintenance unit registers a next activation time. The forced termination target application list maintenance unit then causes the process to proceed to step S.

In step S the forced termination target application list maintenance unit sleeps. The forced termination target application list maintenance unit then causes the process to proceed to step S.

In step S the forced termination target application list maintenance unit receives a timer event. The forced termination target application list maintenance unit then returns the process to step S and executes the procedure for processing a list again.

In a third embodiment a function of generating an event is added to an installer used for maintenance of applications. Events for reconstructing the tables are generated after maintenance operations such as installation of a new application updating of an existing application and uninstallation of an existing application. Next upon receiving an event a table construction unit reads the access permission information regarding all the applications that have been installed thereby completely revising the tables.

In step S the forced termination target application list maintenance unit executes a procedure for processing a list. The forced termination target application list maintenance unit then causes the process to proceed to step S.

In step S the forced termination target application list maintenance unit waits for an instruction to reconstruct the forced termination target application list from the application management unit . The forced termination target application list maintenance unit then causes the process to proceed to step S.

In step S the forced termination target application list maintenance unit receives the instruction to reconstruct the forced termination target application list from the application management unit . The forced termination target application list maintenance unit returns the process to step S and executes the procedure for processing a list again.

In step S the application management unit identifies the content of processing. If the content of processing is a change to the access right the application management unit causes the process to proceed to step S. If the content of processing is uninstallation the application management unit causes the process to proceed to step S. If the content of processing is installation the application management unit causes the process to proceed to step S.

In step S the application management unit executes a process for changing the access right. The application management unit then causes the process to proceed to step S.

In step S the application management unit executes an uninstallation process. The application management unit then causes the process to proceed to step S.

In step S the application management unit identifies the content of the installation. If the content of the installation is new installation the application management unit causes the process to proceed to step S. On the other hand if the content of the installation is updating installation the application management unit causes the process to proceed to step S.

In step S the application management unit executes an installation process. The application management unit then causes the process to proceed to step S.

In step S the application management unit judges whether or not there is a change to the access permission information. If there is a change to the access permission information the application management unit causes the process to proceed to step S. On the other hand if there is no change to the access permission information the application management unit causes the process to proceed to step S.

In step S the application management unit executes an updating process. The application management unit then causes the process to proceed to step S.

In step S the application management unit executes an updating process. The application management unit then terminates the process.

In step S the application management unit transmits an instruction to reconstruct the forced termination target application list to the forced termination target application list maintenance unit . The application management unit then terminates the process.

In a fourth embodiment the function of the forced termination target application list maintenance unit is integrated into the installer. Instead of generating an event according to the third embodiment a range of the tables in which the tables are affected by maintenance operations is detected and corrected during the maintenance operations for the applications.

In step S the application management unit identifies the content of processing. If the content of processing is a change to the access right the application management unit causes the process to proceed to step S. If the content of processing is uninstallation the application management unit causes the process to proceed to step S. If the content of processing is installation the application management unit causes the process to proceed to step S.

In step S the application management unit executes a process for changing the access right. The application management unit then causes the process to proceed to step S.

In step S the application management unit executes a process for changing a forced termination target class. The application management unit then terminates the process.

In step S the application management unit executes an uninstallation process. The application management unit then causes the process to proceed to step S.

In step S the application management unit executes a process for deleting a forced termination target. The application management unit then terminates the process.

In step S the application management unit identifies the content of the installation. If the content of the installation is new installation the application management unit causes the process to proceed to step S. On the other hand if the content of the installation is updating installation the application management unit causes the process to proceed to step S.

In step S the application management unit executes an installation process. The application management unit then causes the process to proceed to step S.

In step S the application management unit executes a process for adding a forced termination target. The application management unit then terminates the process.

In step S the application management unit judges whether or not there is a change to the access permission information. If there is a change to the access permission information the application management unit causes the process to proceed to step S. On the other hand if there is no change to the access permission information the application management unit causes the process to proceed to step S.

In step S the application management unit executes an updating process. The application management unit then causes the process to proceed to step S.

In step S the application management unit executes a process for changing a forced termination target class. The application management unit then terminates the process.

In step S the application management unit executes an updating process. The application management unit then terminates the process.

In step S the forced termination target addition processing unit reads the name of an application package to be installed and the access permission information. The forced termination target addition processing unit then causes the process to proceed to step S.

In step S the forced termination target addition processing unit reads the application type access permission information correspondence table . The forced termination target addition processing unit then causes the process to proceed to step S.

In step S the forced termination target addition processing unit identifies the type of application to which the target application belongs. The forced termination target addition processing unit then causes the process to proceed to step S.

In step S the forced termination target addition processing unit reads the class application type correspondence table . The forced termination target addition processing unit then causes the process to proceed to step S.

In step S the forced termination target addition processing unit identifies the class number to which the application belongs. The forced termination target addition processing unit then causes the process to proceed to step S.

In step S the forced termination target addition processing unit judges whether or not the application belongs to any class. If the application belongs to any class the forced termination target addition processing unit causes the process to proceed to step S. On the other hand if the application does not belong to any class the forced termination target addition processing unit terminates the process.

In step S the forced termination target addition processing unit adds the application to the forced termination target application list . The forced termination target addition processing unit then terminates the process.

In step S the forced termination target deletion processing unit reads the name of an application to be deleted from the forced termination target application list . The forced termination target deletion processing unit then causes the process to proceed to step S.

In step S the forced termination target deletion processing unit judges whether or not the application has been registered to the forced termination target application list . If the application has been registered to the forced termination target application list the forced termination target deletion processing unit causes the process to proceed to step S. On the other hand if the application has not been registered to the forced termination target application list the forced termination target deletion processing unit terminates the process.

In step S the forced termination target deletion processing unit deletes the application to be uninstalled from the forced termination target application list . The forced termination target deletion processing unit then terminates the process.

In step S the forced termination target class change unit searches the package information DB using the name of an application and obtains the access permission information. The forced termination target class change unit then causes the process to proceed to step S.

In step S the forced termination target class change unit overwrites the access permission information regarding the application to be corrected. The forced termination target class change unit then terminates the process.

According to the above embodiments when the remaining amount of electric charge of the battery in the information processing apparatus becomes smaller than a certain value an application operating in the background is terminated in accordance with the power consumption of the CPU that is executing the application. Therefore since an application that causes the CPU to consume larger power is terminated first the power consumed by the CPU becomes small thereby extending the life of the battery.

Although the information processing systems according to the exemplary embodiments have been described the present disclosure is not limited to these concrete embodiments that have been disclosed and various modifications and alterations are possible without deviating from the scope of the claims.

All examples and conditional language recited herein are intended for pedagogical purposes to aid the reader in understanding the invention and the concepts contributed by the inventor to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although the embodiments of the present invention have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

All examples and conditional language recited herein are intended for pedagogical purposes to aid the reader in understanding the invention and the concepts contributed by the inventor to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although the embodiment of the present invention has been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

