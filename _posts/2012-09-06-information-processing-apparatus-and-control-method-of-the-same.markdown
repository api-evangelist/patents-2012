---

title: Information processing apparatus and control method of the same
abstract: A device function to be used by an application is specified, a risk level of the specified device function is acquired, and a risk level of the application is calculated based on the acquired risk level of the device function.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08955116&OS=08955116&RS=08955116
owner: Canon Kabushiki Kaisha
number: 08955116
owner_city: Tokyo
owner_country: JP
publication_date: 20120906
---
Aspects of the present invention generally relate to processing for setting an application security policy.

An application running on a personal computer PC especially on a Web browser may be configured from Hyper Text Markup Language HTML files and JavaScript files. These applications are also referred to as widgets or Web applications. These applications may be include Cascading Style Sheets CSS files image files Extensible Markup Language XML files and the like.

Applications configured from HTML files and JavaScript registered trademark files are now not only used on PCs but also on various devices as well. The framework for delivering applications to a device via an applications store has been set by the Wholesale Applications Community WAC as a standard specification.

Applications configured from HTML and JavaScript can contain functions that make a device specific function be called up from JavaScript code. The standard specification for calling up a device specific function from JavaScript code is set by the World Wide Web Consortium W3C standard setting organization. This function is also referred to as a Device application programming interface API . In addition a similar specification to device API has also been formulated by WAC.

There are many different types of device APIs. For example there is an API for managing personal information an API for acquiring position information about a device an API for external communication via a network and the like. The fact that an application can utilize a device specific function increases the scope of functions that can be realized by the application.

However the device API specification increases the security risk for device applications. For example if an application uses an API that externally communicates via a network with an API that accesses personal information there is a risk that the personal information of the device owner could be compromised.

Under the WAC framework management of the security of applications that use device APIs can be performed by employing a security policy. United States Patent Application Publication No. 2010 0077445 discusses a method that uses a dedicated application and a dedicated server as a method for managing the security of applications with use of the security policy. The method discussed in United States Patent Application Publication No. 2010 0077445 stores application evaluations in the dedicated server and a management application compares the application evaluation with a predetermined threshold to determine resources that an application can access.

However since the method discussed in United States Patent Application Publication No. 2010 0077445 performs the determination based on the application evaluation the resources that the application can access are determined even if the risk level of the device APIs device functions used by the application is dangerous.

Aspects of the present invention relate to a technique that determines a security policy of an application in consideration of a risk level of a device function used by the application.

According to an aspect of the present invention an information processing apparatus includes a specification unit configured to specify a device function to be used by an application an acquisition unit configured to acquire a risk level of the specified device function a calculation unit configured to calculate a risk level of the application from the acquired risk level of the device function and a control unit configured to control whether to install the application based on the risk level of the application and a threshold.

Further features and aspects of the present invention will become apparent from the following detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings.

Not all of the combinations of the characteristics described in the exemplary embodiments are essential for solving means of the present invention. Further structures having the similar configuration are denoted with the same reference numeral.

In a first exemplary embodiment an example will be described in which a user installs a widget application in a device.

The term widget used here refers to an application format defined by the W3C or the WAC. A widget has a package form and includes a setting file written in XML and an HTML file as content. In addition the widget may include JavaScript files CSS files image files and the like. The setting file written in XML is referred to by the W3C and WAC as config.xml .

The configuration of a computer apparatus that can be applied as an information processing apparatus according to the present exemplary embodiment will be described with reference to a block diagram in . As illustrated in an information processing apparatus includes a central processing unit CPU that controls the entire information processing apparatus a read only memory ROM for storing programs and parameters that do not need to be changed a random access memory RAM for temporarily storing programs and data to be supplied from an external device or the like. The information processing apparatus further includes an interface for displaying stored data and supplied data and a system bus that communicably connects the respective units from to .

The information processing apparatus may also include an interface with an input device such as a pointing device like a mouse or a keyboard for receiving operations from a user and inputting data. Further the information processing apparatus can also include a hard disk and a memory card fixedly installed therein. Alternatively the information processing apparatus may include a detachable external storage device that includes an optical disk such as a flexible disk or a compact disk CD a magnetic or optical card an integrated circuit IC card a memory card and the like. In addition the information processing apparatus can include a network interface for connecting to a network circuit such as the Internet.

In first in step S the user selects an application that the user wishes to install with an operation unit . A device API specification unit acquires a usage declaration for the device APIs device functions used by the application.

Then in step S the device API specification unit specifies the device APIs used by the application by acquiring a list of the device APIs that the application uses from the acquired usage declaration. In the W3C specification and the WAC specification a device API usage declaration is described in config.xml .

Next in step S the device API specification unit determines whether the application uses the device APIs. In step S if a device API is included in the list acquired in step S it is determined that the application uses that device API YES in step S .

In step S if it is determined that the application does not use the device API NO in step S the processing proceeds to step S. In step S a control unit determines that the application is safe and installs the application.

If it is determined in step S that the application uses the device API YES in step S the processing proceeds to step S. In step S a device API risk level acquisition unit acquires the risk level of the device APIs used by the application. In step S the risk level acquisition unit acquires the risk level of the device APIs specified in step S. A storage unit stores a risk level table in advance. The risk level acquisition unit acquires the device API risk levels from the risk level table stored in the storage unit .

In step S a calculation unit calculates the risk level of the application using the risk level of the device APIs acquired in step S and a calculation formula.

An example of a calculation formula according to the present exemplary embodiment is described as Formula 1 1. Formula 1 1 indicates a case in which among the device APIs the risk level of an API that communicates externally via a network is considered to be especially high. The calculation formulas are stored in the storage unit . In the present exemplary embodiment the storage unit stores the following Application risk level deviceapis risk level deviceapis risk level network risk level Formula 1 1 deviceapis risk level MAX accelerometer risk level orientation risk level camera risk level devicestatus risk level filesystem risk level messaging risk level geolocation risk level pim risk level deviceinteraction risk level Formula 1 2 pim risk level MAX contact risk level calendar risk level task risk level Formula 1 3 The deviceapis risk level in Formula 1 1 is derived from Formula 1 2. The pim risk level in Formula 1 2 is derived from Formula 1 3.

In the calculation formula of Formula 1 1 the network API risk level is treated as an independent item to increase the ratio of the network API risk level in the calculation result. Further the deviceapis API risk level in Formula 1 1 is a maximum value from the risk levels of nine device APIs. This is because in the WAC specification the deviceapis API and the accelerometer to deviceinteraction APIs are defined as a parent API and child APIs. Similarly the pim API and each of the contact API the calendar API and the task API have a parent child relationship in the WAC specification. Consequently the pim API risk level is taken as the maximum value of the contact API to task API risk levels.

In step S the control unit compares the application risk level calculated by the calculation unit with a predetermined threshold. The predetermined threshold indicates an application security limit value which is stored in advance in the storage unit . If it is determined in step S that the application risk level is less than the predetermined threshold NO in step S the processing proceeds to step S. In step S the control unit determines that the application is safe and installs the application.

On the other hand if it is determined in step S that the application risk level is greater than or equal to the predetermined threshold YES in step S the control unit determines that the application is dangerous and the processing proceeds to step S. In step S the control unit does not install the application and notifies the user that the application is dangerous. The notification is issued by displaying a message that the application is dangerous on a display unit .

First an example of an address book backup application will be considered. A function of an address book backup application is to store an address book recorded in a device on a server on a network. The necessary device APIs for the application function are specified as the contact API for accessing the address book and the network API for using the network. The risk level for the address book backup application is calculated based on Formula 1 1 from the contact API risk level and the network API risk level.

Next an example of an imaging application including position information will be considered. A function of an imaging application including position information is to provide a photograph with the position information of when the photograph was taken. The necessary device APIs for the application function are specified as the geolocation API for accessing position information and the camera API for using a camera. The risk level for the imaging application including position information is calculated based on Formula 1 1 from the geolocation API risk level and the camera API risk level.

In step S a usage declaration is utilized to acquire a list of the device APIs used by the application. The operation can also be performed without utilizing the usage declaration by searching a JavaScript code included in the application for a character string that matches a device API. In this case the search is performed by acquiring the JavaScript code from the application and searching the JavaScript code for whether there is a character string matching the device API. If there is a matching character string the device API used by the application can be acquired.

In the above described first exemplary embodiment whether to install the application is determined using a threshold. In a first modification of the first exemplary embodiment an example will be described in which a user determines whether to install the application after being notified about the application risk level.

In step S the control unit displays the application risk level calculated in step S on the display unit .

In step S the control unit determines whether the operation unit has received an instruction to install the application. If it is determined in step S that an instruction to install the application has been received YES in step S the processing proceeds to step S. In step S the control unit installs the application. If it is determined that an instruction to install the application has not been received NO in step S the control unit finishes the processing in flowchart.

In the first exemplary embodiment an example is described in which the risk level table the calculation formulae and the threshold are set in advance and stored in the storage unit . In a second exemplary embodiment a case will be described in which a user can change any of the risk level table the calculation formulae and the threshold via the operation unit . In the second exemplary embodiment information relating to the application security necessary for determining the application risk level such as the risk level table the calculation formulae and the threshold will be referred to as security items. illustrates a configuration according to the second exemplary embodiment.

More specifically an example will be described in which the user increases an influence degree of a device API that the user wishes to take particular care with in the determination of the risk of an application like the network API in the first exemplary embodiment. An example will be described in which the user increases the security strength of a device application.

The processing flow for determining the risk of an application in the second exemplary embodiment is the same as in . However before the processing in step S the user performs processing to change a security item for a device application.

An example of a user interface for determining a security priority item for an application is illustrated in . As illustrated in a security priority item is used for selecting the function whose security strength the user especially wishes to increase from among the application functions. illustrates network personal information file system E mail camera and current position information as examples of this function security priority item .

In step S the setting unit determines whether the operation performed by the user is a change of a security priority item. If it is determined that the user has changed a security priority item YES in step S the processing proceeds to step S. In step S the setting unit change unit changes the calculation formula.

An operation example will now be described with reference to . First the user selects the function security priority item whose security strength the user wishes to increase on the screen illustrated in . In the second exemplary embodiment a case will be considered in which in addition to network communication the user wishes to take particular care with management of personal information. In two items network communication and personal information are selected.

Before the user changes the security item i.e. with the initial device settings it is assumed that personal information is not checked on the user s security item setting screen. In such a case functions that access personal information are not considered to be important in the determination of how dangerous an application is. The calculation formula used by the calculation unit at this stage is the calculation formula represented by Formula 1 1.

In the example illustrated in the user selects the network and the personal information by placing a check mark next to these items on the security item setting screen. In this case the obtained added items are deviceapis network and deviceapis pim . As described in pim is acquired from the maximum value among contact calendar and task.

Next in step S the setting unit adds the added items obtained in step S to the basic items obtained in step S. The basic items illustrated in are deviceapis. Further the added items are deviceapis network and deviceapis pim . Thus the calculation formula used by the calculation unit changes as shown by Formula 2 1. Application risk level deviceapis risk level deviceapis risk level network risk level deviceapis risk level pim risk level Formula 2 1 deviceapis risk level MAX accelerometer risk level orientation risk level camera risk level devicestatus risk level filesystem risk level messaging risk level geolocation risk level pim risk level deviceinteraction risk level Formula 2 2 pim risk level MAX contact risk level calendar risk level task risk level Formula 2 3 The deviceapis risk level in Formula 2 1 is derived from Formula 2 2. Further the pim risk level in Formula 2 2 is derived from Formula 2 3.

The processing illustrated in is still applied when the user selects an item other than the network and the personal information for the security priority item. For example if file system is selected from the added item obtained in step S will be deviceapis file system .

There is a plurality of added items corresponding to the security priority items for sensor and device information in . In such a case all of the items are added to the basic item. For example if the user places a check next to the device information on the security item setting screen the obtained added items will be deviceapis deviceinteraction and deviceapis devicestatus . Consequently both of these two added items are added to the basic item.

In the first exemplary embodiment the network API risk level is treated as an independent item to increase the ratio of the network API risk level in the calculation result like in the calculation formula of Formula 1 1. In the second exemplary embodiment the contact API risk level is treated as an independent item to increase the ratio of the contact API risk level in addition to the network API risk level like in the formula of Formula 2 1.

In step S if it is determined that the user operation does not change a security priority item NO in step S the processing proceeds to step S. In step S the setting unit determines whether the user operation changes the security strength.

In step S if it is determined that the user operation changes the security strength YES in step S the processing proceeds to step S. In step S the setting unit acquires a value corresponding to the security strength from a threshold correspondence table. Then in step S the setting unit changes the threshold to the acquired value. In step S the setting unit stores the value changed in step S in the storage unit .

Steps S and S will now be described based on an example in which the user increases the security strength of a device application. An example of the interface the user uses to change the security strength of a device application is illustrated in .

In the security strength of a device application can be selected from low medium and high . In this example the user has selected high .

The setting unit acquires from the threshold correspondence table illustrated in the value corresponding to the low medium or high security strength selected by the user.

In the values for low medium and high security strengths are 30 20 and 10 respectively. If low is selected an application will be determined to be safe if the application risk level is relatively high. On the other hand if high is selected an application will be determined to be dangerous if the application risk level is relatively low. In the present exemplary embodiment since high is selected the threshold is 10.

Thus if the risk level table illustrated in and the calculation formula of Formula 2 1 are used the risk levels for applications handling the address book and applications performing network communication substantially increase. By applying the present exemplary embodiment the security check of an application can be strengthened for a security item whose security the user particularly wishes to increase as a priority.

In the above described second exemplary embodiment the calculation formula is changed to increase the influence degree of a device API whose security the user wishes to increase. As a first modification of the second exemplary embodiment a processing flow will now be described for changing the risk level table to increase the influence degree of a device API whose security the user wishes to increase. The specific operation examples in the first modification of the second exemplary embodiment are the same as described for the second exemplary embodiment. illustrates an example of the processing flow according to the first modification. In the processing illustrated in other than step S the processing is the same as that illustrated in and thus a description of those same steps is omitted herein.

The processing in step S for changing the risk level table will now be described. In step S the setting unit changes the risk level table. The setting unit reads the information from the operation unit and reflects the read information in the risk level table. An example of a method for changing the risk level table so that the risk level of an application using a network API and a pim API is increased will now be described.

In step S the setting unit acquires the names of the device APIs to be changed from a security priority item correspondence table. The security priority item correspondence table is the same as that illustrated in .

Next in step S the setting unit changes the risk level of the device API acquired in step S to the value acquired in step S. In the present exemplary embodiment the value obtained in step S is 5. Further in the present exemplary embodiment the device API names are network and pim.

Thus the risk level for the network API and the pim API are both 5. An example illustrating this change is illustrated in .

In the network API risk level has been changed to 5. Further the contact API the calendar API and the task API which are the child APIs of the pim API have also each been changed to 5.

Thus if the risk table illustrated in and the calculation formula of Formula 1 1 are used the risk level for applications handling the address book and applications performing network communication substantially increase. By applying the present exemplary embodiment the security check of an application can be strengthened for a security item whose security the user particularly wishes to increase as a priority.

In the above described first and second exemplary embodiments the maximum values of the respective device APIs are used in the calculation formula for calculating an application risk level. A second modification of the second exemplary embodiment will now be described in which the sum of the respective device APIs is used in the calculation formula for calculating an application risk level.

The processing flow for determining how dangerous an application in the second modification of the second exemplary embodiment is the same as in . In the present modification the calculation formula used by the calculation unit is different for the first exemplary embodiment. The calculation formula used in the second modification is shown in Formula 3 1. Application risk level deviceapis risk level deviceapis risk level network risk level Formula 3 1 deviceapis risk level SUM accelerometer risk level orientation risk level camera risk level devicestatus risk level filesystem risk level messaging risk level geolocation risk level pim risk level and deviceinteraction risk level Formula 3 2 pim risk level SUM contact risk level calendar risk level and task risk level Formula 3 3 The deviceapis risk level in Formula 3 1 is derived from Formula 3 2. Further the pim risk level in Formula 3 2 is derived from Formula 3 3. If the calculation formula of Formula 3 1 is used because the sum of the risk levels of the respective device APIs is obtained the more types of device API that the application uses the more dangerous that application is determined to be.

A third modification of the second exemplary embodiment will now be described in which the risk level for a specific security item is not included in the determination of how dangerous an application is.

Among the device APIs defined by the WAC specification there are APIs that can be considered as having a low danger if combined with any other device API. For example if the accelerometer API for acquiring acceleration sensor information and the orientation API for acquiring axis sensor information are used in combination with the network API or the content API the risk level does not increase.

Consequently in the determination of how dangerous an application is the user may not wish to consider whether the application uses an accelerometer API or an orientation API. Therefore a specific device API can be excluded from the determination of how dangerous an application is.

Formulas 4 1 and 5 1 are formulas that exclude the accelerometer API and the orientation API from the calculation formula used by the calculation unit . Application risk level deviceapis risk level deviceapis risk level network risk level Formula 4 1 deviceapis risk level MAX camera risk level devicestatus risk level filesystem risk level messaging risk level geolocation risk level pim risk level deviceinteraction risk level Formula 4 2 pim risk level MAX contact risk level calendar risk level task risk level Formula 4 3 The deviceapis risk level in Formula 4 1 is derived from Formula 4 2. Further the pim risk level in Formula 4 2 is derived from Formula 4 3. Application risk level deviceapis risk level deviceapis risk level network risk level Formula 5 1 deviceapis risk level SUM camera risk level devicestatus risk level filesystem risk level messaging risk level geolocation risk level pim risk level and deviceinteraction risk level Formula 5 2 pim risk level SUM contact risk level calendar risk level and task risk level Formula 5 3 The deviceapis risk level in Formula 5 1 is derived from Formula 5 2. Further the pim risk level in Formula 5 2 is derived from Formula 5 3.

Formula 4 1 is a case in which the maximum value is used in the calculation of the parent API risk level. Formula 5 1 is a case in which the sum value is used in the calculation of the parent API risk level. In Formulas 4 1 and 5 1 the risk level of the application does not increase if the accelerometer API and the orientation API are used.

A fourth modification of the second exemplary embodiment will now be described. If the camera API is combined with the messaging API an application can be created which activates the camera attaches a photograph taken by the camera to an E mail and then sends the E mail to an arbitrary user. Further if the filesystem API is combined with the messaging API an application can be created which attaches an arbitrary file stored on a device to an E mail and sends the E mail to an arbitrary user.

As described above an application having a high risk level can be created by combining a device API handling a file and the messaging API. Further the risk level may substantially increase for a device API by specific combinations such as the contact API and the network API.

A formula obtained by changing the calculation formula used by the calculation unit so that the risk level for a device API is substantially increased by a specific combination is shown in Formula 6 1. Application risk level MAX camera risk level filesystem risk level messaging risk level pim risk level network risk level Formula 6 1 pim risk level MAX contact risk level calendar risk level task risk level Formula 6 2 The pim risk level in Formula 6 1 is derived from Formula 6 2.

If the calculation formula of Formula 6 1 is used the risk level of an application in which two APIs the device API handling a file and the messaging API are simultaneously used increases because the risk level of the device API handling a file is multiplied by the risk level of the messaging API. Further the risk level of an application in which two APIs the contact API and the network API are simultaneously used increases because the risk level of the contact API is multiplied by the risk level of the network API.

In a third exemplary embodiment a case will be described in which when the user wishes to install an application determined to be dangerous the changes necessary for installing the application are presented to the user. including illustrates a flowchart illustrating processing according to the third exemplary embodiment. The configuration of the third exemplary embodiment is the same as illustrated in .

More specifically a case will be described in which when an application using the camera API and the network API is determined to be dangerous the changes necessary to install the application are presented to the user. In this example the user specifies in advance the camera risk level to 4 the network risk level to 5 and the security limit value to 15. In addition based on Formulae 1 1 to 1 3 the risk level of the application that the user wishes to install is 24.

The processing flow for determining how dangerous an application is in is similar to the processing flow in . In the processing from step S onwards is different from .

In the present exemplary embodiment it is assumed that after the user interface in has been presented to the user the user pressed the area . If the user selects the area in step S it is determined that the user wishes the installation method to be presented YES in step S .

Then in step S the calculation unit determines the device API to be changed. According to the present exemplary embodiment all of the device APIs used by the application are enumerated as changing targets. Next in step S the calculation unit calculates the risk level so that the application is not determined to be dangerous.

The specific processing procedure in steps S and S will now be described. First the device APIs used by the application to be installed are acquired. In the present exemplary embodiment these are the camera API and the network API.

First the change in the camera risk level will be considered. Since the security limit value is 15 the camera risk level is determined so that the application risk level is less than 15. If the determined camera risk level is Cd based on Formulae 1 2 and 1 3 the deviceapis risk level is also Cd. More specifically Cd is determined to a value that makes Cd Cd 5 less than 15. In this case the determined Cd is 2.

Next the change in the network risk level will be considered. Since the security limit value is 15 the network risk level is determined so that the application risk level is less than 15. If the determined network risk level is Nd based on Formulae 1 2 and 1 3 the deviceapis risk level is 4. In other words Nd is determined to a value that makes 4 4 Nd less than 15. In this case the determined Nd is 2.

Next in step S the display unit presents the device API types determined in step S to the user. An example of the user interface at this stage is illustrated in .

If the user selects an area after the user interface illustrated in is presented in step S the control unit determines that the user instructed the device API risk level to be changed YES in step S . Then in step S the calculation unit changes the device API determined in step S to the value calculated in step S. Finally in step S the control unit installs the application.

If the user selects an area after the user interface illustrated in is presented in step S the control unit does not determine that the user instructed the device API risk level to be changed NO in step S . Then in step S the control unit determines that the user instructed the security limit value to be changed YES in step S .

Next in step S the calculation unit determines the security limit value at which the application will not be determined to be dangerous.

The specific processing procedure in step S will now be described. Since the risk level of the application is 24 it should be sufficient to set the security limit value to 25. Therefore the determined security limit value is 25.

Next in step S the display unit presents the changed security limit value calculated in step S to the user.

After the processing in step S if the control unit determines in step S that the user instructed the security limit value to be changed YES in step S the processing proceeds to step S. In step S the setting unit changes the application security limit value to the value calculated in step S. Finally in step S the control unit installs the application.

If the determination in either of steps S or S is No the control unit does not install the application.

Although exemplary embodiments according to the present invention are described above as already stated the information processing apparatus may be a general purpose information processing apparatus such as a common personal computer that can realize the present invention with a computer program running on such a computer. Therefore it is clear that the scope of the present invention includes a computer program. Further generally a computer program is stored on a computer readable storage medium such as a CD ROM and can be executed by setting the storage medium in a drive of the computer and copying or installing the computer program onto the system. Therefore it is also clear that the scope of the present invention includes such a computer readable storage medium.

Aspects of the present invention can also be realized by a computer of a system or apparatus or devices such as a CPU or an MPU that reads out and executes a program recorded on a memory device to perform the functions of the above described embodiments and by a method the steps of which are performed by a computer of a system or apparatus by for example reading out and executing a program recorded on a memory device to perform the functions of the above described embodiments. For this purpose the program is provided to the computer for example via a network or from a recording medium of various types serving as the memory device e.g. computer readable storage medium .

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

This application claims priority from Japanese Patent Applications No. 2011 201863 filed Sep. 15 2011 and No. 2012 188787 filed Aug. 29 2012 which are hereby incorporated by reference herein in their entirety.

