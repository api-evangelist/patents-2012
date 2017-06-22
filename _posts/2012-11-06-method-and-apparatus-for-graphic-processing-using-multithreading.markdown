---

title: Method and apparatus for graphic processing using multi-threading
abstract: A method and apparatus for graphic processing using multi-threading includes at least one context task, mediation task, and control task executed by a processor. The at least one context task sequentially generates graphic commands. The mediation task mediates processing of the graphic commands. The mediation task may process a particular graphic command on behalf of the at least one context task, and change a processing order of the graphic commands. The control task transmits the graphic commands to a graphic hardware.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09105208&OS=09105208&RS=09105208
owner: Samsung Electronics Co., Ltd.
number: 09105208
owner_city: Suwon-si
owner_country: KR
publication_date: 20121106
---
This application claims the priority benefit of Korean Patent Application No. 10 2012 0001594 filed on Jan. 5 2012 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference.

A computer system may include two computation units that is a central processing unit CPU and a graphics processing unit GPU .

Development of the CPU is progressing from a single type to a core type a multi core type or a multi processor type. Also demand for a multi core or a multi processor with respect to a CPU used in a mobile environment is rapidly increasing. In addition in a multi core or multi processor environment a technology for simultaneous execution of a plurality of applications is in increasing demand. Accordingly a device driver which enables a plurality of applications to manage a single CPU is now necessary.

The speed of the GPU is considerably increased in comparison to the speed of the CPU. Accordingly demand exists for a GPU device driver which is capable of minimizing a waiting time of a CPU by efficiently managing a plurality of applications.

According to an aspect of one or more embodiments there is provided an electronic apparatus including a central processing unit CPU to process a command and a graphic hardware to process a graphic command wherein the CPU includes at least one context task to sequentially generate graphic commands a mediation task to receive the graphic commands from each of the at least one context task and to mediate processing of the graphic commands and a control task to receive the graphic commands from each of the at least one context task or the mediation task and to transmit the graphic commands to the graphic hardware.

Each of the at least one context task may be requested from a general program task to process the graphic commands.

The mediation task may mediate processing of the graphic commands by processing a particular graphic command on behalf of the context task.

The particular graphic command may include at least one selected from mip map generation shader compiling and texture compression.

The mediation task may mediate processing of the graphic commands by changing a processing order of the graphic commands.

The mediation task may change the processing order of the graphic commands such that a plurality of graphic commands having the same context are performed in a sequential manner.

The CPU may include at least one core and the at least one context task the mediation task and the control task may be executed by one of the at least one core.

The at least one context task the mediation task and the control task may be executed each as a thread in parallel.

According to an aspect of one or more embodiments there is provided a graphic command processing method including sequentially generating graphic commands by each of at least one context task receiving the graphic commands from each of the at least one context task by a mediation task mediating processing of the graphic commands by the mediation task receiving the graphic commands from each of the at least one context task and the mediation task by a control task and transmitting the graphic commands to the graphic hardware by the control task wherein the at least one context task the mediation task and the control task are executed by a central processing unit CPU adapted to process a command.

The graphic command processing method may further include requesting each of the at least one context task to process the graphic commands from a general program task.

The mediating may include processing a particular graphic command by the mediation task on behalf of the context task.

The processing order of the graphic commands may be changed such that a plurality of graphic commands having the same context are performed in a sequential manner.

According to an aspect of one or more embodiments there is provided an electronic apparatus including a central processing unit CPU including cores to process commands and a graphic hardware to process a graphic command wherein the CPU includes at least one context task to sequentially generate graphic commands a mediation task to receive the graphic commands from each of the at least one context task and to mediate processing of the graphic commands and a control task to receive the graphic commands from each of the at least one context task or the mediation task and to transmit the graphic commands to the graphic hardware wherein the cores include a first core and a second core the first core executes the at least one context task the second core executes the control task.

Graphic commands may be executed by a native rendering interface NRI communication layer and may be executed using the second core which executes the control task.

Graphic commands which may be executed by the native rendering interface NRI include at least one stall at least one draw and a texture transmission.

Graphic commands which may be executed in accordance with a user code include at least one user code at least one draw a mip map generation and a flush.

According to another aspect of one or more embodiments there is provided at least one non transitory computer readable medium storing computer readable instructions to implement methods of one or more embodiments.

Reference will now be made in detail to embodiments examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to the like elements throughout. Embodiments are described below to explain the present disclosure by referring to the figures.

The CPU may be plural in number. In a plurality of CPUs including a first CPU a second CPU and a third CPU are illustrated.

The CPU may include at least one core. Also each of the plurality of CPUs may include at least one core.

The graphic hardware may process a command related to graphics. The graphic hardware may be a graphic processing unit GPU .

The CPU may execute at least one general program task at least one context task a mediation task and a control task .

A first general program task a second general program task and a third general program task are shown in as the at least one general program task. A first context task a second context task and a third context task are shown in as the at least one context task.

Each of the at least one context task may be requested to process graphic commands from the at least one general program task. For example the first general program task may request the first context task to sequentially process a series of graphic commands.

Each of the at least one context task may sequentially generate graphic commands. Each of the at least one context task may process a graphic command such as context parsing and shader compiling. Each of the at least one context task may provide graphic commands to the mediation task .

The mediation task may receive graphic commands from each of the at least one context task. In addition the mediation task may mediate processing of the graphic commands so that the graphic hardware efficiently processes the graphic commands received from the at least one context task. That is the mediation task may optimize processing of the graphic commands received from the at least one context task.

The control task may receive graphic commands from the at least one context task or the mediation task and transmit the received graphic commands to the graphic hardware . Here transmission of the graphic commands to the graphic hardware may refer to execution of the graphic commands on the graphic hardware .

The at least one general program task the at least one context task the mediation task and the control task may be device driver tasks related to a graphic library and a device driver. The graphic library may provide an application programming interface API to the at least one general program task. The general program task may request the at least one context task to process the graphic commands by calling the API. The device driver may actually control the graphic hardware . In addition the device driver may provide efficient synchronization and management with respect to each task. Also the device driver may control a multi application to be processed by a single graphic hardware based on multi threading.

The control task may transmit the graphic commands to the graphic hardware by making an access to the device driver. Alternatively the control task may be a device driver accessing the graphic hardware . The at least one general program task the at least one context task the mediation task and the control task may be executed by one of the at least one core included in the CPU .

The CPU may execute the at least one general program task the at least one context task the mediation task and the control task each as a thread in parallel. When the CPU includes at least one core the threads may be allocated to each of the at least one core included in the CPU . That is the at least one general program task the at least one context task the mediation task and the control task each as the thread may be executed by the at least one core in parallel.

In commands executed by a user code are shown along the time line. The commands include a user code a draw a mip map generation a user code a draw and a flush . The user code may indicate a first graphic library API context. In addition graphic commands executed by a native rendering interface NRI communication layer are illustrated along the time line. The graphic commands include a stall a draw a stall a texture transmission and a draw .

Among the graphic commands executed by the user code the user code and the user code may not be graphic commands. The draw commands may be commands for requesting rendering of a graphic hardware . The flush may be a command for awaiting completion of the draw and the draw . That is the flush may be a command executing synchronization between the user code and the NRI communication layer .

The stall and the stall may indicate that no commands are executed in the NRI communication layer . That is the stall and the stall may indicate an idle state of a control task .

The user code may indicate commands requested by a general program task. The general program task may request a context task to process the commands of the user code . Accordingly the user code may indicate the commands executed by the context task.

The NRI communication layer may indicate commands executed by a control task . The control task may receive the graphic commands from the context task and transmit the received graphic commands to the graphic hardware .

The commands executed by the user code may be executed by a first core that executes the context task among at least one core. The commands executed by the NRI communication layer may be executed by a second core that executes the control task among the at least one core.

The draw may correspond to the draw . That is the context task may perform processing on the user code for a first draw and request the control task to perform processing on the user code for the first draw. The control task may request the graphic hardware to process the first draw. In the same manner the second draw may correspond to the draw .

A texture generated by the mip map generation may be transmitted to the graphic hardware . The control task may transmit the texture to the graphic hardware . Data communication such as the texture transmission may be performed by a direct memory access DMA scheme. That is the data communication such as the texture transmission may not as a whole be directly processed by the CPU or the core. Therefore part of the texture transmission and the draw may be executed overlapped.

In commands executed by a user code are shown along the time line. The commands executed by the user code include a user code a draw a user code a draw and a flush . The user code may indicate a first graphic library API context. Also commands executed by a mediation layer are shown along the time line. A mip map generation is executed by the mediation layer . In addition graphic commands executed by an NRI communication layer are shown along the time line. The graphic commands include a stall a draw a stall a texture transmission and a draw .

The user code may indicate commands requested by a general program task. The general program task may request a context task to process the commands of the user code . Therefore the user code may indicate the commands executed by the context task.

The mediation layer may indicate commands executed by a mediation task . The mediation task may form a command chain for a graphic hardware and relay the command chain to the NRI communication layer that will be described hereinafter.

The NRI communication layer may indicate commands executed by a control task . The control task may receive graphic commands from the context task or the mediation task and transmit the received graphic commands to the graphic hardware . The control task may maintain native device queues with respect to all parts of the graphic hardware functioning in parallel. In addition the control task may launch NRI activities for removing the graphic hardware . Here the activities may correspond to the graphic commands received by the control task . The control task may notify the mediation layer of the mediation task that the activities are completed.

The commands executed by the user code may be executed by a first core that executes the context task among the at least one core. The commands executed by the mediation layer may be executed by a second core that executes the mediation task among the at least one core. The commands executed by the NRI communication layer may be executed by a third core that executes the control task among the at least one core.

The mediation task may process offload massive data and other miscellaneous tasks so as to reduce a load of at least one context task. That is the mediation task may perform a work offload for the at least one context task. For example the mediation layer may process the mip map generation that is processed by the context task in the embodiment of . The mediation task may mediate processing of the graphic commands by processing a particular graphic command on behalf of the context task. The particular graphic command may include at least one selected from mip map generation shader compiling and texture compression.

Since the at least one context task the mediation task and the control task are executed in parallel by the at least one core and since the mediation task processes the particular graphic command that is requested to the context task processing time for the graphic commands may be shortened. Comparing to since the mip map generation is processed by the mediation layer the draw may be executed more quickly than the draw . Accordingly the draw may be executed more quickly than the draw . Also as aforementioned the draw and part of the texture transmission may be redundantly executed.

As aforementioned the mediation task may mediate a load among the tasks executed as threads. Through the mediation data to be transmitted to the graphic hardware may be distributed and processed in the device driver. As a result parallel processing by an application and the device driver may be achieved.

Furthermore since data is processed quickly in the CPU data transmission from the CPU to the GPU may be continuously performed. Also efficiency of graphic command processing including rendering may be increased.

A first user code may indicate a first graphic library API context. In relation to the first graphic library API context the first user code may set a state and a state . In the state may refer to a rendering context. The commands executed by the first user code shown in include a set state to set state 1 a set state to set state 3 a draw a set state to set state 3 a draw and a flush .

A second user code may indicate a second graphic library API context. In relation to the second graphic library API context the second user code may set the state and the state . Therefore the state and the state may have particular values respectively by the first user code and the second user code . The commands executed by the second user code shown in include a set state to set state 1 a set state to set state 4 a draw a set state to set state 2 a draw and a flush .

The first user code and the second user code may indicate commands requested by a general program task. A first general program task may request a first context task to process the commands of the first user code . A second general program task may request a second context task to process the commands of the second user code . Therefore the first user code and the second user code may indicate the commands executed by the first context task and the commands executed by the second context task.

The state and the state may indicate whether a depth test or a stencil test is performed in each draw. Constants for example 1 2 3 and 4 set as values of the state or the state may indicate respectively different states. For example the constant may indicate that the depth test is performed while the constant indicates that the depth test is not performed. A command for setting the state may be regarded as a context change command.

A context communication layer may refer to any action that occupies time and that is actually executed by a control task . Here the action may refer to graphic processing for example rendering.

According to the graphic communication layer a draw with state a draw with state a draw with state a draw with state a context waiting mutex and a context waiting mutex may be executed. Here the draw with state may refer to a draw executed using a particular state value. For example the draw with state may indicate that the draw is performed with the state set to 1 and the state set to 4 according to the set state to and the set state to . The context waiting mutex may indicate execution of an object that provides synchronization requested from the flush. Therefore the draw with state the draw with state the draw with state the draw with state may correspond to the draw the draw the draw and the draw respectively.

Time may be consumed to set the state. Therefore when a plurality of graphic commands having the same context are executed sequentially the time consumed for setting the state of each graphic command may be removed. Here the same context denotes that the value of the state and the value of the state are equal. The graphic command may include the draw. In the draw and the draw are executed with the state set to 1 and the state set to 3. Therefore when the draw and the draw are executed subsequently the commands for setting the values of the state and the state for example the set state to may be removed.

The mediation layer may indicate commands executed by a mediation task . The commands executed by the mediation layer shown in include a set state to a set state to a draw a set state to a draw a draw a set state to and a draw . The commands executed by the mediation layer may indicate a command for setting a state for execution of actions indicated by a context communication layer and a draw command.

The draw and the draw may be executed with the state set to 1. Therefore the set state to and the set state to may be processed as a single set state to . The mediation task may mediate processing of graphic commands by processing a plurality of same context change commands commonly applied to a plurality of subsequent graphic commands as a single context change command. The plurality of same context change commands may be commands for setting a particular state to a particular value.

In addition the draw and the draw may be executed with the state set to 1 and the state set to 3. Therefore when the draw and the draw are processed in a sequential manner a command for setting a state for the draw may be removed. According to an order of actions illustrated in relation to the context communication layer the draw is issued prior to the draw . However in the mediation layer since the mediation task sequentially the draw and the draw having the same context a command for setting a state for the draw for example the set state to may be removed. As a result the draw may be processed prior to the draw .

As aforementioned the mediation task may mediate processing of the graphic commands by changing a processing order of a plurality of the graphic commands. The mediation task may change the processing order of the graphic commands such that graphic commands having the same context are subsequent to one another. That is the mediation task may change the processing order of the plurality of graphic commands having different contexts or the same context in a non overlapped 2 dimensional 2D bounding box.

Also the mediation task may remove a context change command related to a common state of the plurality of graphic commands by changing the processing order of the graphic commands. That is the mediation task may remove an unnecessary context for an NRI layer or state switches by changing the processing order of the plurality of graphic commands. The context change command may be a command for changing a particular state to a particular value. The mediation task may analyze whether contexts of the plurality of graphic commands are similar to one another to change the processing order.

According to the aforementioned mediation the graphic commands executed by the NRI communication layer are illustrated along the time line. The NRI communication layer may indicate commands executed by the control task . The control task may receive the graphic commands from the context task or the mediation task and transmit the received graphic commands to the graphic hardware .

A set state to a set state to a draw a set state to and draw a draw and a set state to and draw are shown as the commands executed by the NRI communication layer . In the NRI communication layer a draw command and a set x to y related to the draw command may be serially executed. For example according to the set state to and draw the state may be set to 3 while the draw is immediately processed.

The commands executed by a first user code may be executed by a first core that executes a first context task among at least one core. The commands executed by the second user code may be executed by a second core that executes a second context task among the at least one core. The commands executed by the mediation layer may be executed by a third core that executes the mediation task among the at least one core. The commands executed by the NRI communication layer may be executed by a fourth core that executes the control task among the at least one core.

As the at least one context task the mediation task and the control task are executed in parallel by at least one core and as the mediation task changes the processing order of the plurality of graphic commands time required for processing of the graphic commands may be reduced.

In operation each general program task . . . N may request each of at least one context task to process graphic commands.

In operation upon the request each of the at least one context task . . . N may sequentially generate graphic commands.

In operation a mediation task may receive the graphic commands from each of the at least one context task.

In operation the mediation task may mediate processing of the graphic commands such that a graphic hardware processes the graphic commands efficiently.

Operation may include processing a particular graphic command by the mediation task on behalf of the context task. The particular graphic command may include at least one selected from mip map generation shader compiling and texture compression.

Furthermore operation may include changing a processing order of a plurality of the graphic commands by the mediation task . The processing order may be changed by the mediation task such that a plurality of graphic commands having the same context are subsequent to one another.

In operation a control task may receive the graphic commands from the at least one context task or the mediation task .

The at least one context task the mediation task and the control task may be executed by a CPU for executing commands.

The CPU may include at least one core. The at least one context task the mediation task and the control task may be executed respectively by one core among the at least one core. Also the at least one context task the mediation task and the control task may be executed in parallel each as a thread.

Technical features according to embodiments described with reference to may be directly applied to embodiments in . Therefore a detailed description is omitted for conciseness.

Embodiments may be recorded in non transitory computer readable media including program instructions to implement various operations embodied by a computer. The media may also include alone or in combination with the program instructions data files data structures and the like. The program instructions recorded on the media may be those specially designed and constructed for the purposes of the example embodiments or they may be of the kind well known and available to those having skill in the computer software arts. Examples of non transitory computer readable media include magnetic media such as hard disks floppy disks and magnetic tape optical media such as CD ROM discs and DVDs magneto optical media such as optical discs and hardware devices that are specially configured to store and perform program instructions such as read only memory ROM random access memory RAM flash memory and the like. Examples of program instructions include both machine code such as produced by a compiler and files containing higher level code that may be executed by the computer using an interpreter. The described hardware devices may be configured to act as one or more software modules in order to perform the operations of the above described example embodiments or vice versa. The program instructions may be executed by one or more processors processing devices computer devices and or computer systems. In addition a non transitory computer readable media may be distributed among processors processing devices computer devices and or computer systems connected through a network and computer readable codes or program instructions may be stored and executed in a decentralized manner. In addition the computer readable storage media may also be embodied in at least one application specific integrated circuit ASIC or Field Programmable Gate Array FPGA .

Although embodiments have been shown and described it would be appreciated by those skilled in the art that changes may be made in these embodiments without departing from the principles and spirit of the disclosure the scope of which is defined in the claims and their equivalents.

