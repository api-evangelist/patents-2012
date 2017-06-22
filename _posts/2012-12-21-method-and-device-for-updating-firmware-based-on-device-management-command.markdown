---

title: Method and device for updating firmware based on device management command
abstract: An electronic device includes a memory including a first storage area in an active state and a second storage area in an inactive state, and a first controller configured to execute a first operating system stored in the first storage area, and execute a management command for firmware update on the first operating system, wherein the first controller receives the management command from a management serer, receives update data based on the management command, store the update data in the second storage area, activates the second storage area, deactivates the first storage area, and executes an updated first operating system within the update data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09198039&OS=09198039&RS=09198039
owner: LG Electronics Inc.
number: 09198039
owner_city: Seoul
owner_country: KR
publication_date: 20121221
---
Pursuant to 35 U.S.C. 119 a this application claims the benefit of earlier filing date and right of priority to Korean Application No. 10 2011 0141446 filed on Dec. 23 2011 the contents of which is incorporated by reference herein in its entirety.

This specification relates to a method and device for updating firmware and particularly to a method and device for updating firmware based on a device management command.

A device management refers to a technology of providing functions of user oriented settings remote management updating and the like for electronic devices. The device management technology may be used during fabrication of a product and for the purposes of an initial setting after purchase of a product collectively updating of errors and corrections remote management of a product and the like.

Techniques established by Open Mobile Alliance OMA are being used as application programs in a mobile communication field and standardization techniques in a service field. The OMA handles mobile web web browsing Digital Rights Management DRM solution Internet Protocol IP multimedia device management mobile broadcast mobile associated document standardization and the like in order to facilitate interoperability of mobile data services.

Especially the standardization for the device management technology in OMA allows for wireless execution of processes such as firmware updating software downloading new services error correcting and the like. It is thusly required to establish detailed procedures for updating firmware which includes a program in which an operation of performing a device management function is implemented an operation system for control of other devices and the like.

Therefore an aspect of the detailed description is to provide a method for updating firmware based on a device management message.

Another aspect of the detailed description is to provide a method for updating firmware by stably receiving the firmware using an area present in an inactive state.

Another aspect of the detailed description is to provide a method for updating firmware associated with home appliances based on an OMA device management standard.

To achieve these and other advantages and in accordance with the purpose of this specification as embodied and broadly described herein there is provided an electronic device including a memory including a first storage area in an active state and a second storage area in an inactive state and a first controller configured to execute a first operating system stored in the first storage area and execute a firmware update management command on the first operating system.

The one exemplary embodiment and other exemplary embodiments may include one of the following features.

The first controller may receive the management command from a management serer receive update data based on the management command store the update data in the second storage area activate the second storage area deactivate the first storage area and execute an updated first operating system within the update data. The update data may have a form of a firmware image including the updated first operating system. The update data may include data for an updated portion of the first operating system or the updated entire first operating system. The management command may be received through exchange of control messages based on an Open Mobile Alliance OMA device management standard. Also the management command may instruct execution of downloading and updating.

The electronic device may further include a second controller configured to execute a second operating system for controlling a home appliance function. Here the memory may further include a third storage area to store the second operating system and the first controller may store an updated second operating system within the update data in the third storage area. The first controller may store the updated second operating system in the third storage area by transmitting the updated second operating system through a Universal Asynchronous Receiver Transmitter UART . The first and second controllers may be implemented by using separate hardware. Also the first controller may be connected to a display module of the electronic device.

A firmware updating method may be disclosed in accordance with one exemplary embodiment. The method may include receiving address information related to update data from a management server through a device management session receiving the update data based on the address information storing the update data in a storage area present in an inactive state converting the storage area into an active state and executing an updated first operating system included in the update data the update data having stored in the storage area converted into the active state.

The one exemplary embodiment and other exemplary embodiments may include one of the following features.

The method may further include storing an updated second operating system in another accessible storage area accessible by a Micro controller Unit MCU the updated second operating system being included in the update data within the storage area.

Also the address information related to the update data may be received through a message exchanging based on an Open Mobile Alliance OMA device management standard.

An electronic device according to the exemplary embodiments may execute a firmware updating based on a device management message.

The electronic device may include a memory which is divided into an area where a currently executed operating system is stored and an area where an operating system to be updated is stored whereby the currently executed operating system may be less influenced by errors even if such errors are generated during a firmware updating process.

The firmware updating may be executed based on the device management message even if a plurality of operating systems of the electronic device are provided in different environments respectively.

Further scope of applicability of the present application will become more apparent from the detailed description given hereinafter. However it should be understood that the detailed description and specific examples while indicating preferred embodiments of the invention are given by way of illustration only since various changes and modifications within the spirit and scope of the invention will become apparent to those skilled in the art from the detailed description.

Technical terms used in this specification are used to merely illustrate specific embodiments and should be understood that they are not intended to limit the present disclosure. As far as not being defined differently all terms used herein including technical or scientific terms may have the same meaning as those generally understood by an ordinary person skilled in the art to which the present disclosure belongs and should not be construed in an excessively comprehensive meaning or an excessively restricted meaning.

A singular representation may include a plural representation as far as it represents a definitely different meaning from the context. Terms include or has used herein should be understood that they are intended to indicate an existence of several components or several steps disclosed in the specification and it may also be understood that part of the components or steps may not be included or additional components or steps may further be included.

It will be understood that although the terms first second etc. may be used herein to describe various elements these elements should not be limited by these terms. These terms are only used to distinguish one element from another. For example a first element could be termed a second element and similarly a second element could be termed a first element without departing from the scope of the present disclosure.

It will be understood that when an element is referred to as being connected with another element the element can be directly connected with the other element or intervening elements may also be present. In contrast when an element is referred to as being directly connected with another element there are no intervening elements present.

Embodiments of the present invention will be described below in detail with reference to the accompanying drawings where those components are rendered the same reference number that are the same or are in correspondence regardless of the figure number and redundant explanations are omitted. In describing the present invention if a detailed explanation for a related known function or construction is considered to unnecessarily divert the gist of the present invention such explanation has been omitted but would be understood by those skilled in the art. The accompanying drawings are used to help easily understood the technical idea of the present invention and it should be understood that the idea of the present invention is not limited by the accompanying drawings. The idea of the present invention should be construed to extend to any alterations equivalents and substitutes besides the accompanying drawings.

The term terminal used in this description may be replaced by User Equipment UE Mobile Equipment ME Mobile Station MS User Terminal UT Subscriber Station SS Mobile Subscriber Station MSS wireless device handheld device Access Terminal AT and the like.

Hereinafter description will be given of entities disposed in a device management system in accordance with the exemplary embodiments disclosed in this specification with reference to . is a view illustrating a device management system to which a technology according to this specification is applied and is a view illustrating an exemplary embodiment of an electronic device to which the technology according to this specification is applied.

As illustrated in the device management system may include an electronic device and a management server .

The electronic device is a target to be managed and corresponds to various types of home equipment communication equipment and the like. The electronic device may perform a management command requested by the management server . The electronic device may be an home appliance. The electronic device may include a home appliance module corresponding to hardware related a home appliance function. The electronic device may be an intelligent home appliance having application programs for utilizing the home appliance module according to various ways.

The management server may be a device for executing a management service for the electronic device . Especially the management server may include modules for transmitting a management command execution request to the electronic device and receiving the execution result of the management command from the electronic device to provide to a user. The configuration of the electronic device and the management server will now be described in detail with reference to .

The device management system may further include a management portal . The management portal is a server which provides user subscription and support services for the electronic device . The management portal may perform several functions such as managing a user of the electronic device and performing a product authentication of the electronic device . The management portal may be a device or a service system which is run by a manufacturer of the electronic device or a seller of the electronic device .

Meanwhile the device management system may further include a calculation unit . The calculation unit is a device for accessing a service provided by the management portal . The calculation unit for example may be a device which is provided with a networking function and user interfaces such as a personal computer and the like. The calculation device may be used for managing information related to the electronic device or user information.

The device management system may further include a terminal . The terminal is used to access a management service for the electronic device provided by the management server . The terminal may use the management service using an Application Programming Interface API module provided by the management server . The terminal described in this specification corresponds to a random electronic device capable of accessing the management server to use a management service for an electronic device including a DM client and should be construed as meaning including for example a portable phone a cellular phone a smart phone a Personal Digital Assistant PDA a Portable Multimedia Player PMP a tablet device a computer a multimedia device and the like.

Referring to the electronic device may include a communication unit an interface unit a memory and a processing unit .

The communication unit is a communication module for transmitting or receiving a control message for executing a management command data required to execute the management command an execution result of the management command and the like to or from the management server . The communication unit may include a wireless communication module or a wired communication module for communicating with the management server . Especially the wireless communication module is a module for communication with a device located within a short distance. For example the wireless communication module may be a module which supports short range communication techniques such as Bluetooth Radio Frequency Identification RFID Infrared Data Association IrDA Ultra Wideband UWB Zigbee Wireless LAN protocols such as Bluetooth 802.11n etc. and the like.

The interface unit may serve as a path connected to the home appliance module within the electronic device . The interface unit may allow the home appliance module to transmit and receive a control signal and status information based upon a management command. The interface unit may be implemented in the form of a library required for performing a management command between the home appliance module and a DM client or DM demon .

The home appliance module connected via the interface unit for example may be hardware which performs a washing function a cooking function a cleaning function or a keeping storing function for example. In detail the processing unit may control the home appliance module connected thereto via the interface unit according to a control method included in an application program stored in the memory .

The memory may store a program for operations of the processing unit and temporarily store input output data.

Also the memory may store various software components. In detail the memory may store an Operating System OS an application program and a management platform . The memory may further store software components which include a module operably connected to the communication unit and a module operably connected to the interface unit .

The operating system for example LINUX UNIX OS X WINDOWS Chrome Symbian WinCE Windows Mobile iOS Android Bada VxWorks pSOS or other embedded operating systems may include various types of software components and or drivers for controlling system tasks such as memory management power management and the like.

In the meantime the operating system of the electronic device may be implemented such that a plurality of operating systems can be cooperative with each other. That is the electronic device may be configured such that different operating systems can be executed according to a type of task executed a quantity of available resources under an execution environment and the like. Also the processing unit may be implemented to include a plurality of controllers and in this case the plurality of operating systems may serve as operating systems for operations of the respective controllers.

If it is assumed that the operating system includes a first OS and a second OS the first OS may be an OS to provide an operation environment of a hardware which executes a home appliance function of the electronic device and the second OS may be a common OS to provide an environment for executing a general application program of supporting an operation of a user interface or the communication unit of the electronic device . For example the first OS may be an OS which provides an environment with less resources such as a real time OS executed on a Micro Controller Unit MCU and the second OS may be a common OS in which various application programs are executable among embedded operating systems.

The memory may be configured to store a plurality of operating systems in different areas. For example the memory may be divided into a first area for storing the first OS and a second area for storing the second OS. The first and second areas may be divided using physically different hardware or logically different partitions.

When the memory is divided into a plurality of areas each area may be activated or deactivated. An area in an activated state within the memory may store a currently used application program or operating system and an area in a deactivated state may store an application program or operating system which is not currently used and especially an application program or operating system to be updated.

In the meantime the operating system may be varied through a firmware update process. The firmware update process may be executed based on a management command which the terminal transmits to the DM client via the DM server. The management command for the firmware updating may be a command for requesting for execution of an upgrade function.

The application program may include a program for a specific function of the home appliance module mounted in the electronic device . In detail the processing unit may control the home appliance module connected to the interface unit according to the application program .

For example when a hardware related to a washing function is mounted in the electronic device control signals and state collection signals for managing a washing module such as a washing drum control unit a washing water supply unit a sensing unit a detergent adjusting unit a vibration adjusting unit or a level adjusting unit may be transmitted and received via the interface unit . Here the control signals for managing the washing module may be processed according to the application program which indicates a washing method in response to a washing course which sets method order time and count of washing rinsing and dehydrating based on information related to a target to be washed such as a material of clothes texture and the like.

As another example when a hardware related to a cooking function is mounted in the electronic device control signals and state collection signals for managing a cooking module such as a cooking unit a power fuel control unit a lighting unit an air conditioning unit or a sensing unit may be transmitted and received via the interface unit . Here the control signals for managing the cooking module may be processed according to the application program which indicates a cooking method based on a driving mode a cooking course or a recipe.

As another example when a hardware related to a cleaning function is mounted in the electronic device control signals and state collection signals for managing a cleaning module such as a driving unit a cleaning unit an obstacle detecting unit a position recognizing unit or a sensing unit may be transmitted and received via the interface unit . Here the control signals for managing the cleaning module may be processed according to the application program which indicates a cleaning method.

As another example when a hardware related to a keeping function is mounted in the electronic device control signals and state collection signals for managing a storing module such as a cooling unit a temperature control unit a sensing unit or a power control unit may be transmitted and received via the interface unit . Here the control signals for managing the storing module may be processed according to the operating system which indicates a storing method based on a keeping mode a mature mode or a preserving mode.

Meanwhile the application program may be varied according to a software update process. The software update process may be executed based on a management command that the terminal transmits to the DM client via the DM server. The management command for the software updating may be a command for requesting for execution of an upgrade function.

The management platform may include a Device Management DM client . The DM client may transmit and receive management messages for managing the electronic device to and from the DM server.

The DM client may manage the home appliance module mounted in the electronic device for example performs functions such as monitoring diagnosis upgrade remote control and the like with respect to the home appliance module .

The monitoring function is to monitor a state of the home appliance module . The DM client may execute the monitoring function so as to collect events or log data generated in the home appliance module . For example when a hardware related to a washing function is mounted in the electronic device the DM client may allows the hardware related to the washing function to collect events or log data for items which include an operating state a remaining time an initially set time a washing course number a rinsing level a dehydration RPM temperature or a scheduled washing time.

The diagnosis function is to diagnose the state of the home appliance module . The DM client may execute the diagnosis function so as to acquire detection or diagnosis of errors generated in the home appliance module through an agent.

The upgrade function is to update a firmware a service or an application program of the electronic device . The DM client may execute the upgrade function so as to update the operating system the application program and the management platform stored in the memory . Besides the DM client may execute the upgrade function so as to update software components which include a module operably connected to the communication unit and a module operably connected to the interface unit .

The remote control function is to control the electronic device from a remote place. The DM client may execute the remote control function so as to control an operation of the home appliance module . For example when a hardware related to a storing function is mounted in the electronic device the DM client may instruct the hardware related to the storing function to perform a temperature control of a refrigerating chamber a freezing chamber or the like or perform a function such as an express freezing or the like.

The management platform may include a Device Management DM daemon . The DM daemon may receive a notification message which is transmitted from a notification module of the management server for the DM client . The DM daemon may perform a function of processing exceptions of the DM client .

The management platform may include a service agent . The service agent may be used by the DM client to control a hardware within the electronic device according to a management command or used by the processing unit to control the hardware by executing the application program.

The memory may include at least one of storage media including Random Access Memory RAM Static Random Access Memory SRAM Read Only Memory ROM Electrically Erasable Programmable Read Only Memory EEPROM Programmable Read Only Memory PROM a magnetic memory a magnetic disk an optical disk a flash memory type a hard disk type a multimedia card micro type a memory card type e.g. SD or DX memory and the like. Also the memory may be implemented in the form of a storage area by a storage function which is provided by a network storage or a cloud service connected via the communication unit .

The processing unit may control components of the electronic device to perform the exemplary methods disclosed in this specification. That is the processing unit may control the communication unit the interface unit and the memory .

The processing unit may be configured to execute software components stored in the memory . The controller may control the home appliance module connected to the interface unit according to the application program .

The processing unit may be implemented by individually including a plurality of controllers. For example the processing unit may be implemented to include individual controllers to execute corresponding operating systems. Also the processing unit may be implemented to separately include a Micro Control Unit MCU to control home appliance modules according to functions and a controller to execute various control operations by activating a common operating system.

When the processing unit is divided into a plurality of controllers unlike the MCU implemented on a separate board a controller which executes a common operating system may be connected to a display module or the like of the electronic device .

The processing unit may execute or update the application program to perform a management command received from the management server according to the exemplary embodiments of the present disclosure.

The memory may store a program for operations of the processing unit and temporarily store input output data. Especially the memory may store modules for transferring a request for executing a management command received from the terminal to the electronic device and receiving an execution result of the management command from the electronic device . In detail the memory may include at least one of an Application Programming Interface API module a connection module a download server module a Device Management DM server module and a notification module .

First the API module is an interface module for providing a DM service to an external terminal or an application program of the management server . More concretely the API module may include at least one of interface functions such as authenticating whether or not a terminal or application program desired to access a DM service is permitted remotely diagnosing the electronic device monitoring the electronic device controlling an application program of the electronic device and controlling the home appliance module of the electronic device . Here the functions for providing interfaces may be provided by an independent device such as the API server.

Next the connection module may perform a message transfer function for transferring a management command request message transmitted from an external terminal of the management server to the electronic device and transferring an execution result of the management command in response to the management command request message from the electronic device to the management server . Here the message transfer function may be executed by an independent device such as the connection server.

The download server module may perform a function of transmitting download data to the electronic device . The download server module may be a module for transmitting download data based upon an OMA download standard. Here the function of transmitting the download data may be performed by an independent device such as the download server.

The DM server module may perform a function of requesting for performing a management command and receiving an execution result of the management command through transmission and reception of control messages to and from a DM client which is disposed in the electronic device to perform a function associated with the device management. The DM server module may transmit and receive messages for the management command based on an OMA DM standard. The function of transmitting and receiving the control messages for the device management may be performed by an independent device such as the DM server.

The notification module may perform a notification function of transmitting and receiving notification messages for the device management to and from the electronic device . The notification module may allow for an exchange of messages between the electronic device and the DM server module in a pushing manner. Also the notification function may be performed by an independent device such as the notification server.

The processing unit may control components of the management server to perform the exemplary methods according to the present disclosure. That is the processing unit may control the communication unit and the memory . The processing unit may be configured to execute modules stored in the memory .

As illustrated in a DM server within the management server may perform management for the electronic device by exchanging control messages based on an OMA DM standard with the DM client within the electronic device .

The management server and the electronic device may perform a setup phase operation by transmitting and receiving a package Package package Package and a package Package . The setup phase indicates a step of exchanging authentication information and device information.

In detail the management server transmits the packet which corresponds to a trigger message for starting a management session to the electronic device . Upon reception of the package the electronic device transmits the package which includes authentication information credentials related to the DM client and device information to the management server . After reception of the package the management server inspects the authentication information related to the DM client . When the inspection result is valid the management server transmits the package which includes authentication information related to the DM server and a management command to the electronic device .

Next the management server and the electronic device may perform a management phase operation by transmitting and receiving a package Package and a package Package . The management phase indicates a step of transmitting the execution result of the management command which has been transmitted in the setup phase to the management server . The packages of the management phase may be continuously transmitted and received until the transmission of the management command execution result is completed.

In detail the electronic device transmits the package which includes a response to the management command to the management server . Upon reception of the package the management server transmits the package to the electronic device when an additional process for the management command is required.

As aforementioned in the exchange of the control messages based on the OMA DM standard the packages correspond to data written in a markup language such as a Synchronization Markup Language SyncML message. The packages are transmitted and received by being included in a body of request response according to Hypertext Transfer Protocol HTTP . Also for exchanging the packages the electronic device and the management server may use various types of transmission protocols. If the electronic device has a wireless communication function the electronic device may use Short Message Service SMS or Wireless Application Protocol WAP push for transmission of the packages. On the other hand if it has an Internet Protocol IP based network communication function the electronic device may use a connection via a general Transport Control Protocol TCP socket a connection via Secure Socket Layer SSL or the like.

Hereinafter description will be given of a method for updating firmware according to the present disclosure with reference to . is a flowchart schematically illustrating a method for updating firmware based on a firmware update command received from the management server.

Through the update start procedure S the management server notifies to the electronic device that a firmware of the electronic device is required to be updated.

Alternatively a user may transfer a management command for performing a firmware update to the management server via the terminal . Here an authentication procedure such as a login or the like may be performed between the terminal and the management server and the management command for the firmware update of the electronic device may be transmitted to the management server .

Afterwards the management server transfers a firmware update command to the electronic device by a first DM session S . The first DM session may be a control message based on the OMA DM standard. More concretely the management server may transfer to the electronic device address information required to download update data which includes a firmware to be updated according to the request of the electronic device .

Afterwards the electronic device performs a download process based on the address information related to the update data acquired by the firmware update command S . The update data received through the download process S may be stored in an area in an inactive state within the memory of the electronic device .

The electronic device then performs a firmware update process based on the downloaded update data S . The firmware update process S is to update a currently used firmware and corresponds to a control process for performing an operating system or application program which is to be updated within the update data. To this end the electronic device may convert the area in which the currently used firmware is stored within the memory into an inactive deactivated state and convert an area in which the operating system or application program to be updated into an active activated state. Also when an operating system or application program to be performed by another controller is present in the update data the electronic device may store the operating system or application program in a specific area within the memory so as for the another controller to perform it.

Afterwards the electronic device notifies a processed result of the firmware update command by a second DM session if necessary S .

Hereinafter description will be given of a detailed exemplary embodiment of the firmware updating method with reference to . and are flowcharts sequentially showing a method of updating firmware by an electronic device based on a firmware update command.

The start procedure S for the firmware update will be described in detail with reference to . When the firmware update start procedure S is started in response to a request of the terminal the management server may perform a process of inspecting whether or not the terminal is permitted to request for a management command with respect to the electronic device .

In detail the terminal transmits a login request message to the management server S . The login request message may include information for authenticating the terminal or an application program for a device management performed in the terminal . The management server may provide an API type interface formed to allow an application program which is being executed by an external device to perform the management command for the electronic device . The management server authenticates an application program a device or a user which or who calls the interface in order for a permitted application program or device to call the interface. The login request message may be an authentication message used to inform that the electronic device is allowed to use the interface.

The management server inspects authentication information included in the login request message and transmits a login response message to the terminal when it is confirmed based on the inspection result of the authentication information included in the login request message that the terminal or the application program for the device management performed in the terminal is allowed to request for the management command from the management server S .

The login response message may include access information which the terminal requires to request for the execution of the management command. The access information may be access information related to the management server for receiving the request for a real time type management command. For example the access information may be an IP address or TCP port of the management server .

Afterwards the terminal accesses the management server to request for performing the management command for the firmware update S .

The first DM session S will be described in detail with reference to . The management server may perform with the electronic device a process of transferring the management command for the firmware update based on a type of firmware update management command.

First the management server determines a type of the requested management command S . The type of management command may be distinguished according to a method of transmitting or receiving a control message for performing the management command between the management server and the electronic device . When the type of management command is a real time type command which should be performed within a predetermined time transmissions of the management command execution request and the execution result may be performed in a relay manner through a connection oriented session. When the type of management command is a non real time type command the transmissions of the management command execution request and the execution result may be performed by transmitting and receiving control messages based on the OMA DM standard. The management command for updating the firmware or software of the electronic device corresponds to performing the updating at a predetermined time so the management command may be determined to sufficiently have a non real time characteristic.

Afterwards a device management session for transferring the firmware update command may be performed. In detail the management server transmits a trigger message to the electronic device S . More concretely the trigger message for instructing reception of the management command may be a package generated based on the OMA DM standard. Next the management server transmits an acknowledgement ACK message with respect to the instruction message to the management server S .

Upon reception of the instruction message the electronic device transmits a message which includes authentication information related to the DM client to the management server S . The message including the authentication information related to the DM client may be a package generated based on the OMA DM standard.

After reception of the authentication information related to the DM client the management server verifies the authentication information related to the DM client . When the authentication information related to the DM client is valid the management server transmits a message including authentication information related to the DM server to the electronic device S . The message including the authentication information related to the DM server may be a package generated based on the OMA DM standard.

Upon reception of the authentication information related to the DM server the electronic device verifies the authentication information. When the authentication information related to the DM server is valid the DM client may inquire device information including a firmware version via the service agent S .

The electronic device then transmits a package which includes the firmware version to the management server S . The management server may thus determine whether or not it is necessary to update the firmware based on the firmware version.

When it is determined to update the firmware the management server transmits a package which includes address information related to update data including a firmware to be updated to the electronic device based on the firmware update command requested from the terminal S . The address information related to the update data may be URL PkgURL or Correlator information.

Upon reception of the package the electronic device stores the address information related to the update data S and transmits a package to inform that the update command through the package has been stored S . The management server then transmits a package in response to the package S .

The update command may be a command which instructs only downloading or a command which instructs both downloading and updating. When the update command is configured to instruct only the downloading the electronic device may separately perform the following update process.

Hereinafter a download session S will be described in detail with reference to . The electronic device may execute a downloading process based on the URL information PkgURL related to the stored update data according to the received firmware update command.

First the electronic device requests the management server to transmit a Download Descriptor DD for update data to be downloaded by using URL of DD extracted from the stored URL information S and downloads the DD for the update data to be downloaded from the management server S . Afterwards the electronic device requests the management server to transmit update data using the URL of the update data extracted from the stored URL information S and downloads the update data from the management server S .

Hereinafter a process S of processing the firmware management command by the service agent will be described in detail with reference to .

First the electronic device stores the update data in a waiting standby area S . The waiting area may indicate an area which is not being used by a controller in a memory for storing firmware namely an area in an inactive state within the memory. For example referring to the memory may be divided into a first area a second area and a third area . The first area and the second area may be areas used for a first operating system and the third area may be an area used for a second operating system. When the first area is in an active state and the second area is in an inactive state the electronic device may store the received update data in the second area as illustrated in .

Here the update data may be data in the form of a firmware image which includes a new first operating system to be updated based on the firmware update command.

Alternatively the update data may be a type of data which includes data for a portion to be updated of the first operating system.

Afterwards when the update data includes a second operating system the electronic device performs an updating operation by storing the second operating system in the third area S . The second operating system may be an operating system for controlling a home appliance module. The electronic device may separately include a controller for executing the second operating system. The controller may transmit an updated second operating system through a Universal Asynchronous Receiver Transmitter UART so as to store the updated second operating system in the third storage area. Referring to the second operating system transmitted through the UART is stored in the third area in an executable state.

The electronic device then converts the waiting area into an active state such that the updated first operating system included in the update data can be executable S .

The foregoing embodiments and advantages are merely exemplary and are not to be construed as limiting the present disclosure. The present teachings can be readily applied to other types of apparatuses. This description is intended to be illustrative and not to limit the scope of the claims. Many alternatives modifications and variations will be apparent to those skilled in the art. The features structures methods and other characteristics of the exemplary embodiments described herein may be combined in various ways to obtain additional and or alternative exemplary embodiments.

As the present features may be embodied in several forms without departing from the characteristics thereof it should also be understood that the above described embodiments are not limited by any of the details of the foregoing description unless otherwise specified but rather should be construed broadly within its scope as defined in the appended claims and therefore all changes and modifications that fall within the metes and bounds of the claims or equivalents of such metes and bounds are therefore intended to be embraced by the appended claims.

