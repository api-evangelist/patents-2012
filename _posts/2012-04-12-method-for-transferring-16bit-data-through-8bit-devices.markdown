---

title: Method for transferring 16-bit data through 8-bit devices
abstract: A computer program product corrects a detonation time from a ballistic table, based on the actual velocity of a projectile measured upon exit of the projectile from the gun tube. The computer program product transfers a 16-bit data stream, through a 16-bit to an 8-bit encoder, to a fuze controller implemented as an 8-bit platform, to provide precise timing adjustment to a fuze controller. The computer program product significantly improves the accuracy of detonation times for air burst mode. The encoder calculates the absolute truncated, square rooted, X, of the input time delay number, as well as the error correction number, Y. The encoder then transmits both numbers X and Y as an 8-bit data stream, optionally along with the parity data to the fuze controller.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09317477&OS=09317477&RS=09317477
owner: The United States of America as Represented by the Secretary of the Army
number: 09317477
owner_city: Washington
owner_country: US
publication_date: 20120412
---
The invention described herein may be manufactured and used by or for the Government of the United States for governmental purposes without the payment of any royalties thereon.

The present invention relates in general to the field of munitions. More specifically this invention relates to a method and associated computer program product for encoding and transmitting a digital 16 bit data stream through 8 bit modules. The present invention may be used for example in a new velocity correction circuitry in a fuze to provide adjustment of detonation times issued from fire control.

Serial communication is one of the functions often required in the development of integrated microsystems. In most applications when data is exchanged a serial interface unit sends and receives bit sequences on the status of these bits to and from another unit that processes the bit sequence.

The serial input output SIO unit is a serial interface used for communicating with other units. It is also important for low power consumption in portable applications.

The amount of serial data is fixed in the conventional SIO. Generally the width of the data is fixed at 8 bits or 16 bits. An operator selects either the 8 bit or the 16 bit serial interface depending on the design. However such manual selection between the 8 bit and the 16 bit may hamper the use of new technological advancements in connection with existing or vintage devices.

More specifically ordnance systems such as artillery shells rocket propelled munitions mortar shells and the like are becoming increasingly technologically sophisticated with communication and accuracy playing a fundamental role. The main problem with communications lies in transferring a 16 bit data stream by using a 16 bit platform in ordnance systems that are either incapable or that do not adequately support the 16 bit platform. Conventional methods have been proposed to address this concern.

One such conventional method proposes updating the electronic circuitry to a platform that can handle the size of the data being transferred. In this case it would be the expansion of an 8 bit processor to a 16 bit processor. However the complexity of such expansion significantly increases the cost space constraint complexity and power consumption of the system.

What is therefore needed is a method and associated computer program product for encoding and transmitting a 16 bit data through 8 bit modules without hardware conversion. Prior to the advent of the present invention the need for such a method and associated computer program product has heretofore remained unsatisfied.

The present invention satisfies this need and describes a new method and associated computer program product collectively referred to herein as the invention the present invention the computer program product or the product for encoding and transmitting 16 bit data through 8 bit modules without hardware modifications to the ordnance systems. The present invention may be used for example in a new velocity correction circuitry of a fuze controller to provide adjustment of detonation times issued from fire control.

For the current application as it pertains to fuzing a specific number is to be transferred between two modules such as for example only a velocity correction module and a fuze controller. In this example the velocity correction module computes the actual exit velocity of the projectile and stores this figure in the form of a number that is to be transferred and loaded into the fuze controller.

The purpose of this uploaded data is to provide the fuze with a live exit velocity so the fuze can more accurately predict an airburst time delay. It is therefore critical that once a number is determined in the velocity correction module there is no loss of precision and that the data is transferred as fast as possible to minimize any error. Once the data is transferred from module to module the fuze is able to update the time delay accordingly and detonate at the correct time.

In one embodiment the velocity correction circuitry requires a 16 bit architecture to perform complex calculations based on sensor data. The present invention corrects the detonation time from a ballistic table based on the actual velocity of a projectile measured upon exit of the projectile from the gun tube or muzzle. The present invention provides precise timing adjustment to the currently existing fuze built upon an 8 bit architecture. It significantly improves the accuracy of detonation times for air burst mode.

The present computer program product solves the problem of transferring the 16 bit data stream between modules by reducing or encoding the 16 bit data stream into a two part 8 bit data stream. The computer program product may optionally expand or decode the two part 8 bit data stream back into the original 16 bit data stream without significant loss of precision or error into the computation. The present invention becomes of particular importance when transferring large data sizes on a reduced processor platform.

The present invention includes an encoder or encoding module that converts the inputted 16 bit data stream T into a two part 8 bit data stream X and Y. The encoder calculates the truncate square root X of the input number e.g. time delay T and transmits the calculated square root as an 8 bit data stream. The encoder further calculates an error correction number Y and transmits it as an 8 bit data stream.

In a preferred embodiment the error correction number Y is calculated by subtracting the square number X from the original number T. The original time delay number T can now be viewed as a composite of two 8 bit numbers X and Y. The two 8 bit numbers X and Y are then transferred to a fuze and optionally though not necessarily expanded or decoded to provide the actual time delay T.

Similar numerals refer to similar elements in the drawings. It should be understood that the sizes of the different components in the figures are not necessarily in exact proportion or to scale and are shown for visual clarity and for the purpose of explanation.

With reference to it illustrates a preferred embodiment of a computer program product according to a preferred embodiment of the present invention. In a preferred embodiment the computer program product is embedded within or programmed onto a 16 bit to 8 bit encoder or encoding module that receives an input 16 bit data stream containing a number T from a sensor or sensors for transmission to an 8 bit platform such as a fuze controller . The fuze controller reconstructs the original 16 bit input data stream as an 8 bit representation of the 16 bit number T with minimal errors.

As an initial stage which is illustrated in the fuze controller is fed or programmed with an approximate timing value T that is based on an estimated exit velocity of the projectile from the gun barrel the proximity of the gun system from the intended target and other parameters that affect the flight path of the projectile .

The fuze controller will be initiated i.e. detonate at the expiration of the approximate timing value T. However as soon as the projectile exits the gun barrel the sensor measures for example the actual exit velocity of the projectile forward section .

In turn the encoder or another processor calculates a new accurate timing value T and transmits this accurate value T to the fuze controller . For simplicity of illustration it will be assumed that a 16 bit accurate timing value T is being transmitted.

In the context of the present invention it is assumed that the fuze controller is an 8 bit unit that is incapable of directly processing the 16 bit accurate timing value T. To this end the encoder divides the 16 bit accurate timing value T into a two part 8 bit data stream X and Y as it will be described later in greater detail by the examples to follow.

The encoder transmits the 8 bit data stream X Y to the fuze controller . The fuze controller uses the 8 bit values X Y to reconstruct the accurate timing value T as an 8 bit data stream and to use this accurate timing value T for detonation thus achieving a very highly accurate adjustment of the detonation time.

For the current application as it pertains to fuzing a specific number T is to be transferred between two generally incompatible modules the 16 bit sensor and the 8 bit fuze controller . If the fuze controller is capable of processing 16 bit data streams then the encoder will be bypassed. If the fuze controller is capable of processing only 8 bit data streams then the 16 bit to 8 bit encoder is needed to convert the accurate timing value T to two 8 bit values X Y . The computer program product will reconstruct the original accurate timing value T by calculating T as follows T X Y.

It should be clearly understood that while specific examples are provided there is no intention to limit the present invention to the specific embodiments or examples described herein.

In this specific example the number T to be transmitted represents an accurate fuzing time that has been provided by or processed from a reading secured by the sensor . In this example the sensor is a velocity correction module also referenced herein as .

The velocity correction module or sensor computes the actual exit velocity of the projectile and stores this figure in the form of a number T that is to be transferred and loaded into the fuze controller . The purpose of this input number T is to provide the fuze controller capability to accurately predict an airburst time delay using a live exit velocity.

It is therefore critical that once the number T is determined in the velocity correction module there is no loss of precision and that the data is transferred as fast as possible e.g. within a few milliseconds to approximately 25 milliseconds to minimize any error. Once the data T is transferred to the fuze controller the fuze controller will update the time delay accordingly to cause detonation at the accurate time.

In this example and in order to eliminate the need for the larger processor the velocity correction module senses or computes the 16 bit time delay number T and transfers it to the computer program product . As shown at step of the process the encoder module receives the 16 bit time delay number T from the sensor module .

In turn the encoder module divides at step the time delay number T into a two part 8 bit data stream that includes an integer whole number X and an error value Y. At steps the encoder module transmits the two values X and Y to the fuze controller . Depending on the application and the devices used therein at step the fuze controller can either use the two 8 bit data X Y decodes the two received numbers X Y or it can alternatively reconstruct the original time delay number T as a single 16 bit data stream using the received numbers X Y.

The encoder module calculates the two 8 bit numbers X and Y by first calculating the square root of the 16 bit time delay number T and then by truncating the square rooted number to an integer as illustrated in the following equations 1 and 2 Time Delay 1 Truncate Value 2 

The encoder then subtracts the value of the truncated square rooted number X from the original time delay number T to provide an error value as illustrated in the following equation 3 Square root Error Value 3 

In summary the encoder calculates the truncated square rooted X of the input time delay number as well as the error correction number Y. The encoder then transmits both numbers X and Y as an 8 bit data stream to the fuze controller .

The algorithm used by the encoder to encode the input 16 bit data stream into a two part 8 bit data stream ensures fast and reliable data transfer and timing accuracy that is preserved across two different architectures. This helps to limit the redesign of the fuze circuitry while enhancing its capability by placing the design burden on a module or system outside of the fuze controller .

In this embodiment the fuze controller may either be an 8 bit platform or a 16 bit platform. If the fuze controller were a 16 bit platform the computer program product will be provided with an 8 bit to a 16 bit decoder or decoding module which reconstructs the original input 16 bit data stream X Y with minimal errors.

Alternatively the 16 bit fuze controller instructs the encoder to bypass the decoder entirely and to directly transmit the 16 bit data stream to the fuze controller as shown by the arrow .

If on the other hand the fuze controller were an 8 bit platform then the encoder transmits the two 8 bit data stream to the fuze controller as described earlier as shown by the arrow .

At step the process determines whether the fuze controller is an 8 bit or a 16 bit platform. If it is determined that the fuze controller is a 16 bit platform then process makes another determination at step as to whether it is desired to bypass the decoder . If so then the encoder does not encode the 16 bit input data stream but rather transmits it directly to the fuze controller along the arrow at step .

If however it is optionally desired to decode the 16 bit input data stream then as explained earlier the encoder module divides at step the time delay number T into a two part 8 bit data stream that includes an integer whole number X and an error value Y.

At steps the encoder module transmits the two values X and Y to an optional 8 bit to 16 bit decoder . At step the decoder decodes the two part 8 bit data stream and reconstructs the original single input 16 bit data stream using for example the following equation Time Delay 

If at decision step it is determined that the fuze controller is an 8 bit platform then process uses process as described earlier in connection with .

The embodiments described herein are included for the purposes of illustration and are not intended to be the exclusive rather they can be modified within the scope of the invention. For example while the present invention has been described in terms of 8 bit and 16 bit data streams it should be understood that the concepts of the present invention are not limited to these values. As an illustration only 16 bit and 32 bit data streams could be used. In addition while the present invention has been described in terms of a fuzing system for military applications it should be abundantly clear that the present invention may be implemented in other applications whether military or commercial.

