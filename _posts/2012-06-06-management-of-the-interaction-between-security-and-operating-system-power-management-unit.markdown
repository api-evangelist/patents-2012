---

title: Management of the interaction between security and operating system power management unit
abstract: The present invention relates to a method of controlling the operation of a processing device in a first mode or in a second mode. The processing device has a first execution environment and a second execution environment. The method comprises, upon detection of a switch between said first and second modes, setting in the first execution environment a value of a shared variable to an initial value, upon detection of a request of execution of instructions in the second execution environment, updating the value of said shared variable to a value different from the initial value, and reading a current value of the shared variable and causing the processing device to operate in the first mode or in the second mode depending at least on the current value of the shared variable.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09383796&OS=09383796&RS=09383796
owner: ST-Ericsson SA
number: 09383796
owner_city: Plan-les-Ouates
owner_country: CH
publication_date: 20120606
---
The present invention generally relates to devices and methods for the management of interactions between a secure environment on a chip and the operating system power management unit. It concerns more particularly the decision of switching between an active mode and a low power mode of operation.

The approaches described in this section could be pursued but are not necessarily approaches that have been previously conceived or pursued. Therefore unless otherwise indicated herein the approaches described in this section are not prior art to the claims in this application and are not admitted to be prior art by inclusion in this section. Furthermore all embodiments are not necessarily intended to solve all or even any of the problems brought forward in this section.

A System on Chip SoC platform typically comprises at least one embedded Central Processing Unit CPU at least one embedded functional unit also called an IP in the jargon of the one with ordinary skills in the art which may be a memory for instance of the eSRAM type a Memory Management Unit MMU and or at least one register. The components of the SoC are typically interconnected through an internal bus matrix.

In operation the SoC platform may be led to manipulate sensitive data for instance cryptographic secret keys or unencoded secret data like passwords. To prevent unauthorized access to and or corruption of these sensitive data the architecture of the SoC platform may be split into two physically and functionally separated environments a secure environment for manipulating sensitive data and a public environment for processing non sensitive data. The secure environment comprises notably one or more dedicated secure memories and or one or more secure hardware registers to store sensitive data whereas the public environment may include its own dedicated memories and or hardware registers to store public data.

This separation is for example implemented by Advanced RISC Machine ARM SoC platforms with security extensions for example the TrustZone technology. A clear frontier between these two environments may be implemented with hardware HW and or software SW mechanisms embedded in the processor in the bus matrix and in the IPs themselves. This frontier ensures that secure data within the secure environment cannot be accessed by any public component belonging to the public environment. This may typically be the case for active modes of operation of the platform wherein memories IPs and processors are kept powered on or in retention. However some modes of operation are available wherein one or more of the secure components can be powered off meaning that at least some of their contents have to be saved during the particular mode and be restored thereafter. Such modes may be available for the purpose of optimizing the power strategy of the chip and decrease energy leakages.

A dedicated persistent secure memory included in the secure environment may be used to store securely sensitive data present in the secure environment before switching from an active mode to an energy saving mode low power mode . However there might be cases where not enough secure memory space is available to save all secure contents. Consequently in such cases it may be necessary to store sensitive data outside the secure environment in a non secure storage for example. It may be desirable that such storage can be made efficiently and securely.

One issue of switching from an active mode to a low power mode is linked to performances and integration inside the operating system OS . Indeed this switching could require a non negligible amount of time due to saving storing restoring sensitive information from or to the memory.

As the power driver usually enabled in the public environment is isolated from the secure environment the decision to go or not in low power mode is made independently from the knowledge of the estimated time to save restore sensitive data.

Thus this insufficient knowledge could be quite significant for the global power policy and could affect directly the efficiency of this policy.

To address these needs a first aspect of the present invention relates to a method of managing the operation of a processing device in a first mode or in a second mode the processing device having a first execution environment and a second execution environment. At least the second execution environment is configured to be requested to execute instructions and to execute the instructions.

The noun variable is a generic way to refer to storage of information. A variable could be for instance a memory space in a hard drive or in RAM for Random Access Memory or a register of a microprocessor or microchip or a memory mapped area.

For instance the first execution environment is a public environment whereas the second environment is a secure environment.

Additionally the first mode is for instance an active mode where as the second mode is a low power mode as detailed above.

The second environment is configured to dynamically load applications and or programs and thus being able to execute instructions i.e. binary codes interpretable script etc. .

This embodiment aims at ensuring that the first environment has all the information needed to decide if the switch to the other mode is relevant considering the power strategy of the processing device.

As the execution of instructions in the second environment is often closely related to the modification of a secure memory it is useful to only supervise the executions of instructions. This supervision is simpler to implement than the supervision of the modification of a secure memory.

According to another embodiment the updating of the value of the shared variable may be performed prior to any execution of instructions by the second environment.

Hence it is possible to modify a preexisting processing device to easily implement the present method. A single piece of code can be written in an application selector which receives all the execution requests in the second environment. Thus the code footprint can be minimal and it can be unnecessary to modify all possible loaded applications to be sure that the update of the shared variable can occur.

According to another embodiment the value of the shared variable can be set at least to a first and to a second value the first value being the initial value. The value of the shared variable can be updated to the second value upon detection of a request of execution of instructions in the second environment.

For instance its value can be set to true if previously it was false or to false if previously it was true . This embodiment aims at ensuring a very straight forward implementation of the present method. Consecutively if at least one execution is requested in the second environment the value of the shared variable can be set to true .

According to another embodiment the value of the shared variable may be an integer and may be incremented upon detection of a request of execution of instructions in the second environment.

This embodiment aims for instance at ensuring that the number of code execution requests can be known by the first environment. This information can ensure that the decision to switch is as relevant as possible.

According to another embodiment the value of the shared variable can be set to a plurality of possible values the number of the possible values being an integer. The value of the shared variable is updated with one of the possible values upon detection of a request of execution of instructions in the second environment.

For instance the initial value of the shared variable can be set to the string not called and the possible values are the set of strings called once called less than 5 times called more than 5 times .

Hence the public environment is able to determine an estimation of the modification of the secure memory and consecutively to determine the time needed to switch to a low power mode.

According to another embodiment the request of execution of instructions may comprise a synchronous call.

Hence a direct call by the operating system for instance can be supervised. For instance a synchronous call may be a simple function call with arguments and return value.

According to another embodiment the request of execution of instructions may comprise instead an asynchronous call.

Hence interruptions for instance can be supervised. For instance an asynchronous call may be generated by a secure timer or another secure hardware.

A second aspect relates to a processing device being able to be switched from a first mode of operation to a second mode. This processing device comprises a first execution environment and a second execution environment. The second execution environment is configured to 

A third aspect relates to an electronic apparatus comprising a processing device as described above. An electronic apparatus can be for instance a mobile phone a smart phone a PDA for Personal Digital Assistant a touch pad or a personal stereo.

A fourth aspect relates to a computer program product comprising a computer readable medium having thereon a computer program comprising program instructions. The computer program is loadable into a data processing unit and adapted to cause the data processing unit to carry out the method described above when the computer program is run by the data processing unit.

In order to optimize the communication between the public environment and the secure environment of a processing device the invention proposes for instance to identify all entries inside the secure environment i.e. the synchronous call and the asynchronous call and to communicate this information to public environment so that a power controller could have a precise information about how long the next power mode switching will last. This method enables to dynamically determine the cost in time and energy for instance of the low power mode entry exit versus a given budget. In order to illustrate this statement a processing device according to two possible modes of the invention is presented in and in .

These two environments are separated due to security reasons and only few interactions are allowed between these two environments in order to minimize the possibility of security leaks and of attacks.

Usually the public environment is formed at least by a public operating system in charge of the usual functionality of the device such as the interaction with the users the display etc. and a power controller . This power controller is designed to handle the transitions between a plurality of operational modes of the processing device. An example of possible enablement of a processor unit can be found in the application EP10191115. The power controller comprises also a shared variable located in the public memory. This memory and the variable is accessible from the public operating system .

The public operating system comprises a core program and several drivers to interact with other devices and interfaces such as the operating system power driver which interacts with the power controller .

The secure environment comprises at least an application selector and a plurality of programs and which can be loaded dynamically by the application selector depending on the context and needs.

In order to clarify the interactions between the previously introduced components it is proposed to consider that the operating system core system needs to perform a security process and thus make a synchronous call arrow APIC to the secure environment API for Application Programming Interface .

Synchronous calls can be for instance a call for a operating system program which needs to verify a password of a user by calling a function checkUserPassword pass for instance or to encrypt decrypt a file.

The application selector is arranged to decide which program is to be executed and load consequently the appropriate one in the example shown in the appropriate program is the PROG for execution arrow LOAP . In parallel the application selector is further arranged to inform the power controller that a code execution is occurring into the secure environment by modifying the shared variable arrow MODVAR . This modification can be 

In case of incrementing the higher the value of the shared variable is the higher the probability of the modification of the secure memory is.

It is also possible to modify the shared variable directly from the operating system code . The centralized modification by the application selector is advantageous as this modification can be reused in slightly similar cases such as the one presented in the .

Consecutively reading the shared variable allows the operating system power driver determining arrow INF at any time whether a code execution has occurred in the secure environment.

Instead of updating the shared variable whenever code execution occurred into the secure environment it is also possible to update this variable when the secure memory is modified. Nevertheless it is advantageous to monitor only the code execution since the code execution into the secure environment induces in most cases a secure memory modification and since it is straighter forward to implement this type of monitoring. In the present case of the the code footprint caused by updating the shared variable is only concentrated in the application selector and no code modification is needed in the plurality of program and . In addition the secure environment is often composed of one fixed framework which is embedded in the chip and from programs which might be dynamically loaded. The behaviour of these programs is unknown when designing the chip. Thus there is no knowledge about what will be done regarding secure memory modification and it could be impossible to modify them before integrating them into the secure environment.

At the end of the execution of the code into the secure environment a return value is sent back to the public operating system code arrow APIR .

Asynchronous calls can be for instance interruptions or exceptions triggered by a security hardware or a secure clock. It is stressed that the operating system code is not aware of these asynchronous calls as they are not originating from the operating system code.

The application selector decides upon reception of this asynchronous call which program is to be executed and load consequently the appropriate one for instance in the the appropriate program is the PROG for execution arrow LOAP .

The following execution is quasi identical to the execution described in the except that no return value is sent back to the operating system code as the execution is not initiated by it arrow APIR in .

Therefore by identifying all entries inside the secure environment asynchronous or synchronous calls it is possible to communicate information to the operating system power driver so that this driver has precise information about how long the next low power mode entry will last.

This flow chart can represent steps of an example of a computer program which may be executed by the application selector .

In step the application selector tests if the processing device has just entered the low power mode or the active mode. In such cases the shared variable is reset. This reset step is for instance the initialisation of the shared variable to the value 0 if the shared value is of numeric type or to the value false if the shared value is of Boolean type .

Then the application selector turns into an idle mode waiting for a synchronous call or an asynchronous call.

When the application selector is solicited by a synchronous call step or an asynchronous call step the application selector reads the shared variable step and depending on its value modifies it step . This modification comprises for instance the increment of the shared variable if the shared variable is of numeric type or the updating of the shared variable to the value true if the shared variable is of Boolean type .

It is noted that if the shared value is of Boolean type there is no need to read the shared variable before modifying it the shared value is only updated to true for instance.

While there has been illustrated and described what are presently considered to be the preferred embodiments of the present invention it will be understood by those skilled in the art that various other modifications may be made and equivalents may be substituted without departing from the true scope of the present invention. Additionally many modifications may be made to adapt a particular situation to the teachings of the present invention without departing from the central inventive concept described herein. Furthermore an embodiment of the present invention may not include all of the features described above. Therefore it is intended that the present invention not be limited to the particular embodiments disclosed but that the invention include all embodiments falling within the scope of the invention as broadly defined above.

Expressions such as comprise include incorporate contain is and have are to be construed in a non exclusive manner when interpreting the description and its associated claims namely construed to allow for other items or components which are not explicitly defined also to be present. Reference to the singular is also to be construed in be a reference to the plural and vice versa.

A person skilled in the art will readily appreciate that various parameters disclosed in the description may be modified and that various embodiments disclosed may be combined without departing from the scope of the invention.

