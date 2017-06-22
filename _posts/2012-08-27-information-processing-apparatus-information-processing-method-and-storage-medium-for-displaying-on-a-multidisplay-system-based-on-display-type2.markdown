---

title: Information processing apparatus, information processing method, and storage medium for displaying on a multi-display system based on display type
abstract: An information processing apparatus stores identification information of an output apparatus connected to the information processing apparatus, stores display state information indicating a display state at the time of a stop of a system of the information processing apparatus, and controls restoration of the display state based on identification information of an external output apparatus connected to the information processing apparatus and the stored identification information in a case where the system is restarted after the stop of the system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09535645&OS=09535645&RS=09535645
owner: Canon Kabushiki Kaisha
number: 09535645
owner_city: Tokyo
owner_country: JP
publication_date: 20120827
---
This application claims priority from Japanese Patent Application No. 2011 185967 filed Aug. 29 2011 which is hereby incorporated by reference herein in its entirety.

The present invention relates to an information processing apparatus an information processing method and a storage medium.

Some operation programs hereinafter referred to as OSs provided with graphical user interfaces configured to be driven on for example information processing apparatuses have a function of restoring a display state of an application program. According to this function an OS stores a display state of an application program running when the OS is shut down and restores the stored display state of the application when the OS is started up next time. This function for example saves user s trouble of reactivating the application program that was running at the time of shutdown when the information processing apparatus is started up and therefore is highly convenient for users.

Further some information processing apparatuses can be connected to a plurality of display apparatuses. This allows a user to work on a wider display area. Further even many of laptop type information processing apparatuses integrated with display units have connection units for further connection to external display apparatuses.

For example Japanese Patent Application Laid Open No. 2008 164988 discusses a multi display system in which an information processing apparatus is connected to a plurality of display apparatuses and has a function of assigning application programs running on the information processing apparatus to the plurality of display apparatuses thereby improving convenience for users.

However according to the technique discussed in Japanese Patent Application Laid Open No. 2008 164988 once an application program is set to be displayed on a connected display apparatus the application program is always displayed on that display apparatus no matter what kind of apparatus that display apparatus is. This feature leads to a problem in that the application program is displayed even on a display apparatus on which the user does not want the application program to be displayed.

According to an aspect of the present invention an information processing apparatus includes a first storing unit configured to store identification information of an output apparatus connected to the information processing apparatus a second storing unit configured to store information indicating a display state at the time of a stop of a system of the information processing apparatus a restoration unit configured to restore the display state of the information processing apparatus using the information stored by the second storing unit and an acquisition unit configured to acquire identification information of an external output apparatus connected to the information processing apparatus in a case where the system is restarted after the stop of the system. The restoration unit limits restoration of the display state based on the identification information stored by the first storing unit and the identification information acquired by the acquisition unit.

Further features and aspects of the present invention will become apparent from the following detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings.

The operation unit is a user interface such as a keyboard and a mouse pointer. The image display unit is a liquid crystal display provided to the notebook PC which displays an operation system hereinafter referred to as OS and an application program window hereinafter referred to as application window . The RAM serves as a work memory and also serves as an image RAM used by the CPU in drawing processing. The CPU reads out for example the OS and the application program from the HDD to execute them and draws the states of them on the image display unit .

The HDD stores the OS and the application program executed by the CPU and extended display identification data EDID which will be described below. The internal bus is a bus enabling transmission reception of data and commands within the notebook PC . The connection unit is an interface for connection with an external display apparatus such as the liquid crystal projector . The reading unit reads out the EDID which includes specification information such as resolution manufacturer information and other information of the external display apparatus from an electrically erasable programmable read only memory EEPROM of the external display apparatus which is connected to the notebook PC via the connection unit .

The OS stored in the HDD has a function of restoring the display state of an application window that was running at the time of the previous shutdown when the notebook PC is started up. The CPU performs processing based on the program thereby realizing processing according to the flowchart which will be described below.

Next a configuration of the liquid crystal projector will be described. The liquid crystal projector includes an image projection unit an image processing unit an EEPROM and a connection unit .

The image projection unit includes for example a light source a liquid crystal panel and a liquid crystal panel driver. The image projection unit projects an input image. The image processing unit performs image processing such as contrast processing and resolution conversion processing on an input image. The EEPROM stores the above described EDID. The connection unit is a connection interface allowing the liquid crystal projector to be connected to an information processing apparatus such as the notebook PC .

As illustrated in the present exemplary embodiment will be described as an example in which the image display unit of the notebook PC and the screen projected by the liquid crystal projector are connected to provide an extended display.

Next the control flow according to the present exemplary embodiment will be described with reference to a flowchart illustrated in . is a flowchart illustrating an example of display state restoration processing. First suppose that a user activates a plurality of applications after starting up the notebook PC and operates them. In step S when the notebook PC is started up the CPU reads out via the reading unit the EDID hereinafter referred to as PREV EDID stored in the EEPROM of the liquid crystal projector connected to the connection unit and saves this EDID in the RAM .

In step S when the user restarts the notebook PC after the shutdown of the notebook PC the CPU reads out the EDID hereinafter referred to as CURR EDID again from the EEPROM via the reading unit . This processing is performed by using functions of the OS. Subsequently in step S the CPU compares the CURR EDID with the PREV EDID stored in the HDD when the notebook PC was started up last time.

As a result of the comparison if the CURR EDID and the PREV EDID are the same YES in step S then in step S the CPU restores the display state of the application windows which was stored in the HDD at the time of the shutdown when the OS is started up. After the restoration display is performed the screen of the image display unit and the screen projected by the liquid crystal projector display applications as illustrated in . This is the same display state as the display state when the notebook PC was shut down.

As a result of the comparison in step S if the CURR EDID and the PREV EDID are different NO in step S then in step S the CPU limits the restoration of the display state of the application windows which were displayed at the time of the shutdown when the OS is started up. For example the CPU allows the applications to be displayed only on the image display unit as illustrated in

In this way the restoration display of the application windows is controlled according to the result of the comparison between the EDID of the externally connected display apparatus at the time of the shutdown of the notebook PC and the EDID of the externally connected display apparatus at the time of the restart of the notebook PC . Therefore it is possible to securely or safely restore the display state of the application windows.

Further illustrates an example displaying a plurality of application windows. Alternatively in a case where one application window is displayed across two display screens as illustrated in the application window may be displayed only on the image display unit as illustrated in

Further in the present exemplary embodiment as the result of the comparison in step S if the CURR EDID and the PREV EDID are different NO in step S the application windows are displayed only on the image display unit . Alternatively the application windows may be prevented from being displayed completely as illustrated in

Further in the present exemplary embodiment if the CURR EDID and the PREV EDID are different NO in step S the restoration display is not performed. Alternatively the OS may be provided with a function of allowing a user to select any of the settings of DISPLAY APPLICATION WINDOWS ONLY ON NOTEBOOK PC DO NOT RESTORE DISPLAY STATE and ALWAYS RESTORE DISPLAY STATE .

Further in the present exemplary embodiment the restoration display is performed when the notebook PC is shut down by way of example. Furthermore the same processing as the processing at the time of the shutdown may be also performed at the time of recovery from a sleep state a standby state and a hibernation state of the OS which enables the safe restoration of the display state of the application windows.

Further in the present exemplary embodiment the EDID read out in step S is stored in the HDD at the time of the shutdown. However the externally connected display apparatus may be changed during a period from a startup until a shutdown. Therefore the EDID may be read out at the time of a shutdown again to be stored in the HDD .

Further in the present exemplary embodiment in step S the application windows are displayed only on the image display unit . At this time as illustrated in a message window may be displayed to indicate to a user that all application windows are displayed only on the image display unit to prevent a leak of information.

The CPU may display a selection screen illustrated in before performing the processing in step S. In this case the CPU restores the display state when the user selects restoration on this selection screen when the user selects YES and displays the screens illustrated in . The CPU does not restore the display state of the application windows when the user does not select restoration when the user selects NO . In other words the CPU displays the screens illustrated in . Alternatively the CPU displays the screens where all application windows are displayed only on the image display unit as illustrated in

Next a second exemplary embodiment of the present invention will be described with reference to . The notebook PC and the liquid crystal projector according to the present exemplary embodiment are configured in a similar manner to those according to the first exemplary embodiment and therefore a description thereof is not repeated. The present exemplary embodiment will be described as an example in which the liquid crystal projector performs a mirror display of the image display unit of the notebook PC as illustrated in . The mirror display is a display to project the same screen as the image display unit on the liquid crystal projector .

The processing flow is similar to the flow illustrated in the flowchart in which has been described in the description of the first exemplary embodiment. In the present exemplary embodiment if the CPU determines that the EDID at the time of the restart is different from the EDID at the time of the shutdown the CPU stops the mirror display of the application windows. illustrates screens in this case. As illustrated in the CPU does not display the application windows on the liquid crystal projector and displays the application windows only on the image display unit .

In this way it is possible to safely restore the display state of the application windows by controlling the restoration display of the application windows according to the result of the comparison between the EDID of the externally connected display apparatus when the notebook PC is shut down and the EDID of the externally connected display apparatus when the notebook PC is restarted.

Further in the present exemplary embodiment the application windows are displayed only on the image display unit as illustrated in . However the present exemplary embodiment is not limited to this display state. For example as is the case with the first exemplary embodiment the display state may be prevented from being restored completely. Alternatively a selection screen may be displayed to ask a user whether the user wants to continue the mirror display.

Aspects of the present invention can also be realized by a computer of a system or apparatus or devices such as a CPU or MPU that reads out and executes a program recorded on a memory device to perform the functions of the above described embodiment s and by a method the steps of which are performed by a computer of a system or apparatus by for example reading out and executing a program recorded on a memory device to perform the functions of the above described embodiment s . For this purpose the program is provided to the computer for example via a network or from a recording medium of various types serving as the memory device e.g. computer readable medium .

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

