---

title: Digital content display system and method for providing information during a channel zapping delay
abstract: A digital content display system and a method for providing information during a channel zapping delay are provided. The information providing method includes receiving information to be displayed during a channel zapping delay; displaying the information during the channel zapping delay, when performing a channel switching operation to a new channel; and outputting content corresponding to the new channel.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09100691&OS=09100691&RS=09100691
owner: Samsung Electronics Co., Ltd
number: 09100691
owner_city: 
owner_country: KR
publication_date: 20120705
---
This application claims priority under 35 U.S.C. 119 a to Korean Patent Application No. 10 2011 0066253 which was filed in the Korean Intellectual Property Office on Jul. 5 2011 the entire disclosure of which is hereby incorporated by reference.

The present invention relates generally to content display systems and more particularly to a system and method that provides information to a user during a channel zapping delay when channel is changed in a digital broadcast.

Switching channels by a receiver in a digital broadcasting system is performed by searching for a Program IDentification number PID of a switched to channel. However searching for a PID causes a delay in receiving content from the switched to channel. Further this delay increases while received data is converted to reproducible video audio signals. Additionally these processes are performed each time a user switches channels in a digital broadcasting system.

Consequently channel switching is slower in digital broadcasting system than in an analog broadcasting system. It is common for a conventional digital content display device to have a delay time of approximately 2 seconds before content from the switched to channel is displayed. In digital broadcasting systems the time required for channel switching is referred to as a channel zapping delay .

During the channel zapping delay conventional digital broadcast devices merely show a black screen via a display. Accordingly viewers who are accustomed to rapid channel switching as in an analogue broadcasting system often feel that the zapping delay is too long and dislike the black screen state.

Additionally a web browser may be installed in a digital broadcast receiving device which makes it possible for a user to surf web pages mapped to web channels similar to the switching of TV channels. However surfing web pages via a web browser also has a zapping delay time.

The present invention has been designed to address at least the above identified problems occurring in the prior art and to provide at least the advantages described below.

Accordingly an aspect of the present invention is to provide a digital content display system and method that provide user requested information to a user during a channel zapping delay.

Another aspect of the present invention is to provide a zapping method for searching for web pages via a web browser installed in a digital content display system and rapidly switching channels to find a corresponding broadcast program.

In accordance with an embodiment of the invention a method of providing information via a digital content display system is provided. The method includes receiving information to be displayed during a channel zapping delay displaying the information during the channel zapping delay when performing a channel switching operation to a new channel and outputting content corresponding to the new channel.

In accordance with another embodiment of the invention a digital content display system is provided which includes a digital broadcast receiver that receives digital broadcast signals a communication unit that transmits and receives data and the digital broadcast signals a browser engine that browses web pages according to a user browsing request a storage unit that stores an application program and data and a controller that receives information to be displayed during a channel zapping delay displays the information to be displayed during the channel zapping delay when performing a channel switching operation to a new channel and outputs content corresponding to the switched channel.

Various embodiments of the present invention are described in detail below with reference to the accompanying drawings. The same reference numbers are used throughout the drawings to refer to the same or like parts. Additionally detailed descriptions of well known functions and structures incorporated herein are omitted to avoid obscuring the subject matter of the present invention in unnecessary detail.

Herein the term channel refers to a channel that outputs digital broadcast content in a digital content display system and does not refer to a transmission channel. For example channel refers to a digital broadcast channel assigned to a broadcasting station or program and refers a content channel assigned to digital content web pages mapped to a web channel like a TV channel etc.

The phrase push server refers to a server that receives and updates web pages related to preset information and transmits corresponding information to the digital content display system.

In the following description information to be provided to a user during channel switching may be a preview for a next channel a user s set favorite information e.g. weather stock information fortune telling etc. a web page summarizing a web channel a web page set via Open Application Programming Interface API etc. a web page designated by a service provider etc. Further the information may be displayed in the digital content display system as text images Uniform Resource Locators URLs snapshots web pages etc.

The term snapshot refers to an information item that is created as acquired information is edited so that the user can quickly recognize the acquired information during the channel zapping delay.

Referring to the digital content display system includes a digital broadcast receiver a video processor a display unit an audio processing unit an input unit a storage unit a browser engine a controller a wired wireless communication unit . and a push server .

The digital broadcast receiver receives digital broadcast signals and separates them into audio and video signals which are output to the audio processing unit and the video processor respectively. The digital broadcast receiver receives digital broadcast signals corresponding to a user selected channel.

The display unit which may be a Liquid Crystal Display LCD an Organic Light Emitting Diode OLED an Active Matrix Organic Light Emitting Diodes AMOLED etc. displays the decoded video signals output from the video processor . For example the display unit displays video data related to icons animation videos images and texts received via the wired wireless communication unit . The display unit displays information regarding the states and operations of the digital content display system. The display unit receives and displays digital broadcast content corresponding to a user selected channel from the video processor . Additionally the display unit receives and displays information from the wired wireless communication unit .

The audio processing unit reproduces audio signals output from the digital broadcast receiver or the controller and transfers audio signals received via a microphone MIC to the controller . The audio processing unit converts voice audio data into audible sounds and outputs them via a speaker SPK according to the control of the controller . Further the audio processing unit receives audio signals via the microphone and converts them into audio data. The audio processing unit receives and outputs audio signals of digital broadcast content corresponding to the user selected channel. The audio processing unit converts audio data included in the information received via the wired wireless communication unit into audible signals and outputs the audible signals.

The input unit creates signals based on user key operations and transfers the created to the controller . For example the input unit may be implemented with a remote control device equipped with numeric keys direction keys function keys etc. Basically the input unit allows a user to input a channel switching command.

When information is displayed on the display unit the user can select it via the input unit thereby viewing corresponding web pages.

The storage unit stores data and programs for controlling the operation and functions of the digital content display system. The storage unit includes a program storage area and a data storage area. The program storage area stores programs for controlling the operation of the digital content display system and application programs. The data storage area stores data created when the digital content display system is used e.g. images videos audio data etc. For example the storage unit may be implemented with volatile storage media or non volatile storage media or a combination thereof. The volatile storage media may include a semiconductor memory such as a Random Access Memory RAM Dynamic RAM DRAM Static RAM SRAM etc. The non volatile storage media may include a hard disk a Flash NAND memory etc. The storage unit stores URLs of website servers from which the user acquires corresponding information or a URL of the push server that transmits user requested information. The storage unit stores information transmitted from the website servers or the push server and also digital broadcast content received via the digital broadcast receiver .

The browser engine browses websites and accesses user requested websites via the wired wireless communication unit . The browser engine downloads and parses markup data from a corresponding URL. The browser engine lays out and renders the parsed data. The browser engine loads a user set website URL or a URL of the push server from the storage unit while a channel switching command is being input via the controller . The browser engine accesses the loaded URL and acquires and manages corresponding information. When the user has input the channel switching command and then selects corresponding information the browser engine accesses the website and displays web pages. The browser engine communicates with the push server via the wired wireless communication unit and receives information from the push server while a channel switching command is being input.

The wired wireless communication unit receives digital broadcast signals and performs data communication in a wired wireless mode. The wired wireless communication unit includes a Radio Frequency RF transmitter for up converting the frequency of signals to be transmitted and amplifying the signals and an RF receiver for low noise amplifying received RF signals and down converting the frequency of the received RF signals. The wired wireless communication unit receives data from the Internet or the push server and outputs the data to the controller or vice versa.

The controller controls the overall operation of the components in the digital content display system. Specifically the controller identifies when the user inputs a command to set a channel to provide information and set information to be displayed and controls the display unit to display a user interface that allows the user to set a channel and information to be displayed via the input unit .

When the system operates in an idle state the controller controls the browser engine to access a website related to the user set information as a background via the wired wireless communication unit and to acquire information. Accessing a website as a background refers to the system accessing a corresponding website without a user s input and without displaying the accessing process.

When the system does not operate in an idle state the controller determines whether the user inputs a channel switching command via the input unit .

When the controller determines that the user does not input a channel switching command the controller performs a corresponding function. However when the controller determines that the user inputs a channel switching command the controller determines whether the channel to be switched to is a channel to provide information.

When the controller determines that the channel to be switched to is not a channel to provide information the controller controls the display unit to display a black screen during the channel zapping delay i.e. channels are switched in a conventional mode.

When the controller determines that the channel to be switched to is a channel to provide information the controller controls the display unit to display information acquired during the channel switching process.

The controller determines whether a selection command is input to the input unit when displaying information acquired during the channel switching process. When the controller determines that a selection command is not input the controller controls the display unit to display information acquired during the channel switching process for a period of time.

After the period of time has elapsed the controller controls the display unit to display content corresponding to the switched channel.

However when the controller determines that a selection command is input to the input unit the controller controls the browser engine to access a website via the wired wireless communication unit and controls the display unit to display web pages from the website.

In accordance with another embodiment of the present invention the controller controls the browser engine to access the push server via the wired wireless communication unit and to upload the user set channel and information to be displayed.

Additionally when the controller determines that the channel to be switched to is a channel to provide information the controller determines whether the storage unit has sufficient storage space for the information. When the controller determines that the storage unit has sufficient storage space the controller requests the user s set information from the push server via the wired wireless communication unit . When the push server receives the request the controller controls the browser engine to receive the information from the push server .

However when the controller determines that the storage unit does not have sufficient storage space the controller requests a source URL to the push server via the wired wireless communication unit . When the push server receives the request the controller controls the browser engine to access the URL.

The controller controls the display unit to display information acquired during the channel switching process. When the controller determines that a channel switching operation has been interrupted the controller determines whether a selection command is input to the input unit . When the controller determines that a selection command is not input to the input unit the controller controls the display unit to display information for a period of time.

After the period of time has elapsed the controller controls the display unit to display the content corresponding to the switched channel.

However when the controller determines that a selection command is input to the input unit the controller controls the browser engine to access a website via the wired wireless communication unit and controls the display unit to display the web pages from the website.

The push server provides information during the channel zapping delay in the digital content display system. The push server receives and updates web pages related to preset information and transmits corresponding information to the digital content display system.

Referring to in an idle mode a digital broadcast receiver accesses a website as a background operation in step and acquires a snapshot from the website in step .

The digital broadcast receiver receives a user input channel switching command in step and then displays the snapshot in step .

The digital broadcast receiver receives a selection command form the user in step accesses the website in step and displays web pages from the website in step .

Although illustrates a snapshot as the type of information being displayed during the channel switching process it should be understood that the present invention is not limited to this type of information.

Referring to a push server accesses a website in step and acquires a snapshot from the website in step .

The digital broadcast receiver receives a channel switching command in step and requests a snapshot from the push server in step . The push server transmits the snapshot or a URL to the digital broadcast receiver in step . The digital broadcast receiver displays the snapshot during the channel switching operation in step .

The digital broadcast receiver receives a selection command in step accesses the website in step and displays the web pages from the website in step .

Although illustrates a snapshot as the type of information being displayed during the channel switching process it should be understood that the present invention is not limited to this type of information.

Referring to in step the controller determines whether a user inputs a command to set a channel to provide information and information to be displayed. When the controller determines that the user inputs the command in step the controller controls the display unit to display a user interface through which the user sets a channel to provide information and information to be displayed. In step the controller receives a command for setting a channel and information to be displayed.

Specifically in step the user sets a channel and inputs information to be displayed during a channel switching operation. For example the information to be set may include a preview regarding a channel or information such as weather stock updates news horoscopes etc. When the set channel is a web channel information to be set may include web pages summarizing the web channel. Further when the user does not set information in the system information to be set may be web pages set by a service provider. The amount of information the user can set is based on the length of channel zapping delay.

When the controller determines that the user does not input a menu setting selection command in step the controller determines whether the system is operating in an idle state before in step . In an idle state the system does not execute a current job but has resources to process different operations. In accordance with an embodiment of the invention in the idle state the system receives digital broadcast signals and displays them on the display unit without switching channels.

When the controller determines that the system is operating in an idle state in step the controller accesses a website related to the user set information as a background operation via the wired wireless communication unit in step . Again when accessing a website as a background operation the system accesses a corresponding website without user input and without displaying the accessing process.

In step the controller controls the browser engine to acquire a snapshot from the accessed website. It should be understood that the browser engine may acquire other information that can be displayed during the channel switching operation other than or in addition to the snapshot in step .

However when the controller determines that the system does not operate in an idle state in step or after acquiring the snapshot the controller determines whether the user inputs a channel switching command via the input unit in step . When the controller determines that the user does not input a channel switching command in step the controller performs a corresponding function in step .

When the controller determines that the user inputs a channel switching command in step the controller determines whether the channel to be switched to is a channel to provide information in step . That is the controller determines whether to provide a snapshot during the channel switching operation in step .

When the controller determines that the channel to be switched to is not a channel to provide information in step the controller controls the display unit to display a screen when channels are switched as in a normal mode during the channel switching operation in step .

In step the controller controls the display unit to display the content corresponding to the switched channel.

When the controller determines that the channel to be switched to is a channel to provide information in step the controller controls the display unit to display a snapshot acquired during the channel switching operation in step . When one piece of information is set the display unit displays only one snapshot. When a number of pieces of information are set the display unit displays a number of snapshots.

When the controller determines that the user does not input a selection command in step the controller controls the display unit to display the snapshot for a period of time in step and to display the content corresponding to the switched channel in step after the period of time has elapsed. The period of time is a channel zapping delay.

When the controller determines that the user inputs a selection command in step the controller controls the browser engine to access a corresponding website via the wired wireless communication unit in step and controls the display unit to display the web pages from the website in step .

Although illustrates a snapshot as the type of information being displayed during the channel switching process it should be understood that the present invention is not limited to this type of information.

Referring to in step the controller determines whether the user inputs a command for setting a channel to provide information and information to be displayed. When the controller determines that the user inputs a command for setting a channel to provide information and information to be displayed in step the controller controls the display unit to display a user interface for setting a channel to provide information and information to be displayed in step . In step the controller receives a command for setting a channel and information to be displayed via the input unit in step .

When the controller determines that the user does not input the command in step the controller controls the browser engine to access the push server via the wired wireless communication unit and uploads user input information in step . When the user does not apply any setting to information the information can be set via the web pages that the server sets using Open API etc. The controller receives and updates web pages related to the information.

In step the controller receives a channel switching command and determines whether the channel to be switched to is a channel to provide information in step . That is the controller determines whether to provide a snapshot during the channel switching operation in step .

When the controller determines that the channel is not a channel to provide information in step the controller controls the display unit to display a screen where channels are switched in a normal mode during the channel switching operation in step .

In step the controller controls the display unit to display the content corresponding to the switched channel.

When the controller determines that the channel to be switched to is a channel to provide information in step the controller determines whether the storage unit has sufficient storage space to store a snapshot in step .

When the controller determines that the storage unit has sufficient storage space in step the controller requests a snapshot from the push server via the wired wireless communication unit in step . When the push server receives the request the controller controls the browser engine to receive the snapshot in step .

When the controller determines that the storage unit does not have sufficient storage space in step the controller requests a source URL from the push server via the wired wireless communication unit in step . When the push server receives the request the controller controls the browser engine to receive the source URL in step and to access the URL in step .

When the digital content display system does not have sufficient storage space for storing the snapshots it does not receive snapshots but instead receives and accesses an URL where the snapshots exists and downloads them. Therefore the information providing method according to the invention can be applied to digital content display systems with relatively low performance.

In step the controller controls the display unit to display a snapshot acquired during the channel switching operation or a snapshot via the access to the URL. When one piece of information is set the display unit displays only one snapshot. When a number of pieces of information are set the display unit displays a number of snapshots in order.

When the controller determines that the user does not input a selection command in step the controller controls the display unit to display the snapshot for a period of time in step and to display the content corresponding to the switched channel in step after the period of time has elapsed. The period of time is a channel zapping delay.

When the controller determines that the user inputs a selection command in step the controller controls the browser engine to access a corresponding website via the wired wireless communication unit in step and controls the display unit to display web pages from the website in step .

Although illustrates a snapshot as the type of information being displayed during the channel switching process it should be understood that the present invention is not limited to this type of information.

Referring to TV channel n 1 refers to a channel to provide information. Channel zapping occurs between TV channels n and n 1 and a number of snapshots are set to be displayed. There are three snapshots between TV channel n and n 1 and these are displayed on the display unit . When the user does not selects any snapshot Channel n is switched to Channel n 1.

A channel following TV channel n 1 is also set to provide information. When TV channel n 1 follows a web channel it may be switched to the web channel which is called a webpage zapping. There are three snapshots between TV channel n 1 and the following web channel and these are displayed on the display unit . When the user selects the third snapshot the browser engine connects to the selected website and thus web pages are displayed on the display unit .

As described above the digital content display systems and methods according to the above described embodiments of the present invention provide user requested information during a zapping delay created when channels are switched.

Although certain embodiments of the present invention have been described in detail hereinabove it should be understood that many variations and modifications of the basic inventive concept herein described which may be apparent to those skilled in the art will still fall within the spirit and scope of the present invention as defined in the appended claims and their equivalents.

