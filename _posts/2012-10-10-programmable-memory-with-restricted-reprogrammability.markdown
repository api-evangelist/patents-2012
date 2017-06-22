---

title: Programmable memory with restricted reprogrammability
abstract: A reprogrammable memory, which can be, programmed a limited number of times. A plurality of one-time programmable elements are combined by a logic arrangement such that the output of that logic arrangement may be reprogrammed a limited number of times.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08913454&OS=08913454&RS=08913454
owner: Cambridge Silicon Radio Limited
number: 08913454
owner_city: Cambridge
owner_country: GB
publication_date: 20121010
---
The present application claims priority from UK Patent Application No. 1215650.1 filed on Sep. 3 2012 entitled PROGRAMMABLE MEMORY WITH RESTRICTED REPROGRAMMABILITY the contents of which are incorporated herein by reference.

This disclosure relates to non volatile memories and in particular to non volatile memories which can only be reprogrammed a limited number of times

Non volatile memories are commonly utilised to permanently store data in electronic devices. Non volatile memories which are one time programmable are utilised where there is a requirement to program data into the memory only once and thereafter for that data to be unchangeable. For example one time programmable memories may be used to store data that should then remain unchanged for the life of the device such as serial numbers IP addresses or features of the device. One time programmable memory may also be utilised to control access to certain features or functions of a device. For example a device may be configured such that a test mode can only be enabled when a memory is in an unprogrammed state. When testing has been completed by the manufacturer that memory is programmed thereby preventing the future enablement of the test mode.

One time programmable memories may be implemented using a number of different technologies. Common examples are fuses and anti fuses in which the conductivity of an electronic component is permanently altered or FLASH type memories without a reprogramming circuit.

There are scenarios where an ability to reprogram a memory a limited number of times may be desirable. For example where a memory is used to control access to a test mode it may be advantageous to be able to re activate that test mode should the device be returned to the manufacturer. Such an action is not possible with existing one time programmable memories.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used as an aid in determining the scope of the claimed subject matter.

There is provided a reprogrammable electronic memory comprising a logic device having a plurality of inputs and an output wherein a signal at the output changes each time a signal at one of the inputs changes and a one time programmable element connected to each of the inputs each element providing a first output signal prior to programming of that element and a second output signal after programming of that element.

The preferred features may be combined as appropriate as would be apparent to a skilled person and may be combined with any of the aspects of the invention.

Embodiments of the present invention are described below by way of example only. These examples represent the best ways of putting the invention into practice that are currently known to the Applicant although they are not the only ways in which this could be achieved. The description sets forth the functions of the example and the sequence of steps for constructing and operating the example. However the same or equivalent functions and sequences may be accomplished by different examples.

The present disclosure describes an arrangement of one time reprogrammable memory elements which allows the provision of a function with a limited number of reprogramming opportunities.

The FIGURE shows an arrangement for a providing a single bit non volatile memory the output of which may be changed three times. The arrangement comprises three one time programmable elements . For example each element may be a fuse or one time programmable FLASH cell. Each element is configured such that its output is a logic high signal when manufactured. For example if the elements are fuses their input may be tied to the logic high voltage rail. The output of each fuse is connected to an input of a logic device whose output signal reverses each time one of its input signals changes. For example the logic device may be a parity tree formed of exclusive OR XOR gates. The output of the logic device forms the value of the single bit non volatile memory.

In its initial state the value of the memory is high since all three elements are high. To reprogram the memory a first time one of the elements is changed to output a low value. For example if the element is a fuse it is blown. The output of the logic device and hence the value of the memory switches to low since two of the inputs are high. The value of the memory may be changed a further two times by changing the other two elements one at a time. The memory therefore provides a value which is initially high and which may then be set to be sequentially low high low. The final low value is permanent.

The memory of the FIGURE may be used in a system to control whether a test mode of the system can be accessed. The system is designed such that the test mode can only be accessed when the value of the memory is high. When initially manufactured the memory is high and thus initial testing can be performed by the manufacturer. Once the testing is complete the first element is altered such that the memory value goes low and the test mode cannot be accessed.

If the system is returned to the manufacturer the second element is altered such that the value of the memory goes high and the test mode is accessible again. The manufacturer can therefore perform testing. Once testing is complete the third element is altered to disable the test mode and the system can be returned to the customer without access to the test mode.

The combination of signals from a plurality of one time programmable elements thereby provides a memory which can be programmed a limited number of times. Since there is the possibility to reverse the settings of the memory it is suitable for the control of features that are not critical should a customer ascertain how to alter the elements and hence access the features. For example access to test modes by customers may be undesirable but not critical and therefore the memory would be appropriate. However the memory would not be suitable for restricting access to features not purchased by a customer in a particular model of the system.

A plurality of the memories of the FIGURE may be combined to provide a bank of re programmable memories for example where it is required to control more than one feature or to store a value.

As will be appreciated fuses anti fuses and one time programmable FLASH have been provided as examples of how the elements may be implemented but any one time programmable component may be utilised.

The example of the FIGURE provides three elements to allow the memory to be programmed three times but as will be appreciated any number of elements may be utilised to provide the required number of programming steps.

The device may be provided in any way depending on the particular system in which it is used. The logic device may be provided in hardware or software. For example the entire memory may be provided in part of an IC the elements may be dedicated components with the logic device provided by logic of the main parts of the IC or the elements and or logic device may be provided in a dedicated IC separate to the IC utilising the output of the memory.

In the above example the initial output of the one time programmable elements is high but this may be low depending on the technology utilised to manufacture the elements. The operation of the device is the same regardless of the starting state with the required modification to the logic design to provide the required outputs.

As will be appreciated the term fuse is used to indicate a component whose conductance is permanently changed when the device is blown but does not necessarily require a length of conductor that is physically destroyed when the fuse is blown.

The term programming is not used herein in the sense of computer software programming but rather in the sense of setting a value of the component to which the term refers.

It will be understood that the benefits and advantages described above may relate to one embodiment or may relate to several embodiments. The embodiments are not limited to those that solve any or all of the stated problems or those that have any or all of the stated benefits and advantages.

Any reference to an item refers to one or more of those items. The term comprising is used herein to mean including the method blocks or elements identified but that such blocks or elements do not comprise an exclusive list and a method or apparatus may contain additional blocks or elements.

