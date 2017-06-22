---

title: Circuit including a negative differential resistance (NDR) device having a graphene channel, and method of operating the circuit
abstract: A circuit includes a negative differential resistance (NDR) device which includes a gate and a graphene channel, and a gate voltage source which modulates a gate voltage on the gate such that an electric current through the graphene channel exhibits negative differential resistance.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08593180&OS=08593180&RS=08593180
owner: International Business Machines Corporation
number: 08593180
owner_city: Armonk
owner_country: US
publication_date: 20120312
---
This invention was made with Government support under Contract No. FA8650 08 C 7838 awarded by Defense Advanced Research Projects Agency DARPA . The Government has certain rights in this invention.

The present invention relates generally to a circuit including a negative differential resistance NDR device and more particularly to a circuit including an NDR device which includes a graphene channel.

Negative differential resistance NDR is a unique property of some electrical circuits where an increase in the current entering a port results in a decreased voltage across the same port. This is in contrast to most electrical components with a positive resistance which exhibit monotonically increasing electrical currents when the voltage is raised across the electrical ports.

Devices exhibiting negative resistance are particularly useful for applications at microwave frequencies. Negative resistivity is also essential and important in modern electrical applications such as amplifiers oscillators mixers and impedance cancellation.

In contrast to a normally positive resistive device that dissipates energy an element with negative resistance would generate energy when passing electrical currents. Therefore absolute negative resistance does not theoretically exist as a discrete component.

In practice NDR can be achieved in some diodes e.g. tunneling diodes in some part of their operating range. NDR can also be obtained in a sophisticated and controlled circuitry such as an operational amplifier with properly designed feedback.

However such NDR devices or circuits are typically built as standalone or independent components and cannot be easily integrated with the rest of the circuits using wafer scale fabrication processes. This is a problem because such on chip circuit integration is advantageous and important in order to improve the operating performance e.g. frequency and lower the manufacturing cost.

In view of the foregoing and other problems disadvantages and drawbacks of the aforementioned conventional systems and methods an exemplary aspect of the present invention is directed to a circuit which includes a negative differential resistance NDR device which includes a gate and a graphene channel.

Conventional NDR devices or circuits are typically built as standalone or independent components and cannot be easily integrated with the rest of the circuits using wafer scale fabrication processes. This is a problem because such on chip circuit integration is advantageous and important in order to improve the operating performance e.g. frequency and lower the manufacturing cost.

An exemplary aspect of the present invention is directed to a circuit which includes a negative differential resistance NDR device which includes a gate and a graphene channel and a gate voltage source which modulates a gate voltage on the gate such that an electric current through the graphene channel exhibits negative differential resistance.

Another exemplary aspect of the present invention is directed to a method of operating a circuit which includes a negative differential resistance NDR device which includes a gate and a graphene channel and a gate voltage source. The method includes modulating a gate voltage on the gate such that an electric current through the graphene channel exhibits negative differential resistance.

Another exemplary aspect of the present invention is directed to a circuit including a negative differential resistance NDR device including a gate a graphene channel including a carrier mobility in a range from 100 cm Vs to 1 million cm Vs a gate dielectric contacting the gate and including a thickness in a range from 0.5 nm to 50 nm and a dielectric constant in a range from 2 to 50 the graphene channel contacting the gate dielectric and source and drain electrodes contacting the gate dielectric and the graphene channel. The circuit also includes a gate voltage source which modulates a gate voltage on the gate such that an electric current through the graphene channel exhibits negative differential resistance and a bias voltage source which modulates a bias voltage between the source and drain electrodes. The bias voltage includes a range of bias voltages and the gate voltage source modulates the gate voltage on the gate such that the electric current through the graphene channel exhibits negative differential resistance over the range of bias voltages and the gate voltage source modulates the gate voltage such that the gate voltage satisfies the following 

Another exemplary aspect of the present invention is directed to a method of operating a circuit which includes a negative differential resistance NDR device which includes a gate and a graphene channel and a gate voltage source. The method includes modulating a gate voltage on the gate such that an electric current through the graphene channel exhibits negative differential resistance. The NDR device further includes a gate dielectric contacting the gate the graphene channel contacting the gate dielectric and source and drain electrodes contacting the gate dielectric and the graphene channel a thickness of the gate dielectric is in a range from 0.5 nm to 50 nm a dielectric constant of the gate dielectric is in a range from 2 to 50 and a carrier mobility of the graphene channel is in a range from 100 cm Vs to 1 million cm Vs the circuit further includes a bias voltage source which modulates a bias voltage between the source and drain electrodes the bias voltage includes a range of bias voltages and the gate voltage source modulates the gate voltage on the gate such that the electric current through the graphene channel exhibits negative differential resistance over the range of bias voltages and the gate voltage source modulates the gate voltage such that the gate voltage satisfies the following 

With its unique and novel features the present invention may provide a circuit which can more easily integrate an NDR device using wafer scale fabrication processes than conventional circuits.

As illustrated in the circuit may also include a bias voltage source which modulates a bias voltage between source and drain electrodes of the NDR device . In particular the bias voltage may include a range of bias voltages and the gate voltage source may modulate the gate voltage on the gate of the NDR device such that the electric current through the graphene channel of the NDR device exhibits negative differential resistance over the range of bias voltages.

In an exemplary aspect the gate voltage source may modulate the gate voltage on the gate to be in a range from 10V to 10V and the bias voltage source may modulate the bias voltage between the source and drain electrodes to be in a range from 10V to 10V.

The circuit may also include e.g. be electrically coupled to an operating portion having features e.g. characteristics which are to be affected by the NDR device . In particular the operating portion may be connected to the source and drain electrodes of the NDR device .

For example if the circuit is an oscillator circuit then the operating portion may include a load is connected to the NDR device e.g. connected to source and drain electrodes of the NDR device . As a result a resistance of the load may be canceled out by the NDR device so that there is substantially no resistance in the circuit so that the circuit can sustain a resonant frequency.

As illustrated in the NDR device having a back gate configuration includes a gate a gate dielectric contacting the gate e.g. formed on an upper surface of the gate a graphene channel contacting the gate dielectric e.g. formed on an upper surface of the gate dielectric and source and drain electrodes e.g. metal contacts contacting the gate dielectric e.g. formed on a surface of the gate dielectric and the graphene channel e.g. contacting a side surface of the graphene channel .

As illustrated in the NDR device having a front gate configuration includes a graphene channel formed on a substrate e.g. formed on an upper surface of the substrate such as an SiC substrate a gate dielectric formed on the graphene channel e.g. formed on an upper surface of the graphene channel source and drain electrodes e.g. metal contacts formed on the substrate and contacting the graphene channel and the gate dielectric e.g. contacting a side surface of the graphene channel and a side surface of the gate dielectric and a gate formed on the gate dielectric e.g. formed on an upper surface of the gate dielectric .

It should be noted that are merely illustrative and should not be considered as limiting the NDR device of the present invention to any particular structure or configuration.

The circuit includes an NDR device which may be based on graphene which can allow the NDR device to be readily integrated with existing microelectronics e.g. semiconductor microelectronics . In principle the NDR device can achieve better performance and higher operating frequencies e.g. microwave frequencies .

Graphene is layer of carbon atoms arranged in a hexagonal network where carbon atoms are bonded by sp2 hybridization. Graphene possesses great potential for high speed electronics because of its high carrier mobility and the ultra thin body thickness which is only one atom layer thin.

High frequency operation of graphene based field effect transistors beyond 100 GHz has been recently demonstrated. However conventional circuits do not include graphene based NDR devices e.g. NDR devices including graphene channels .

In view of the excellent electrical properties of graphene and minimal parasitics associated with a relatively simple design a circuit according to the exemplary aspects of the present invention includes a graphene based NDR device which is may be expected to possess superior performance at very high frequencies compared to conventional circuits including other types of NDR devices.

The exemplary aspects of the present invention may include an optimum e.g. preferred operating range and an optimum e.g. preferred operating condition for the NDR device .

As noted above with respect to the NDR device may include a field effect device having three terminals a gate and source and drain electrodes . The source and drain electrodes may be contacted directly with graphene and the gate may be separated from the graphene channel by a thin layer of insulating dielectrics .

The graphene channel may include one or more layers of graphene and the conduction of the graphene layer s can be modulated by the gate . Therefore the circuit may modulate the voltage e.g. gate voltage on the gate such that the electrical current through the graphene channel may exhibit negative differential resistance for a range of source drain biases. That is the circuit may be able to tune the characteristics of the NDR device by modulating the gate voltage on the gate and by modulating the bias voltage on the source and drain electrodes 

The circuit including the NDR device may provide several advantages. First compared to conventional NDR circuits that employ sophisticated feedback circuits the circuit may include only one basic component may possess much smaller parasitics and thus may allow for higher performance than conventional circuits. Second the planar structure of graphene makes it compatible with wafer scale processes and may help to facilitate integration with existing semiconductor e.g. silicon microelectronics. Third the circuit may conveniently control the characteristics of the NDR device can using the gate voltage e.g. gate voltage and bias voltage which may provide flexibility in design of the circuit .

The NDR device may be fabricated by a method which is similar to a method of fabricating a graphene field effect transistor. For example the graphene channel in the NDR device may include one or more graphene layers which can be epitaxially grown on a substrate e.g. SiC substrate or grown by chemical vapor deposition or produced elsewhere and transferred to the desired substrate. The channel defined by lithography where excess graphene are removed by oxygen plasma. In the top gate configuration shown in a layer of insulator is deposited as the gate dielectrics followed by the formation of gate electrodes.

The source and drain electrodes may include a layer of metal which may be deposited on a substrate e.g. the back gate in or the substrate in using lithography and lift off techniques.

In an exemplary aspect the gate dielectrics may include at least one of aluminum oxide hafnium oxide silicon oxide yttrium oxide zirconium oxide SrO CaO HfSiOand ZrSiO. Different from graphene field effect transistors the use of high k and thin gate dielectrics is essential and advantageous for the operation of graphene NDR devices.

Referring again to the drawings illustrates a method of making a circuit according to an exemplary aspect of the present invention.

As illustrated in the method includes forming a negative differential resistance NDR device which includes a gate and a graphene channel and forming a gate voltage source which modulates a gate voltage on the gate such that an electric current through the graphene channel exhibits negative differential resistance. In particular the method may include a wafer scale process in which the forming of the NDR device includes integrally forming the NDR device with other features on a silicon wafer. In particular the forming of the NDR device may include one or more lithographic steps e.g. steps such as masking and etching a silicon wafer and or layers formed on the silicon wafer which are also used to form other features e.g. microelectronic features of the circuit.

For example if the circuit includes an operating portion e.g. operating portion in having features e.g. characteristics which are to be affected by the NDR device then the forming of the NDR device may include one or more lithographic steps which are also used to form the operating portion. Thus if the circuit is an oscillator circuit then the forming of the NDR device may include one or more lithographic steps which are also used to form the load having a resistance which is canceled out by the NDR device.

Referring again to the drawings provides a graph illustrating characteristics of the NDR device according to an exemplary aspect of the present invention. In particular the graph includes plot of gate voltage on the gate vs. conductivity of the graphene channel . As illustrated in the plot may include ambipolar characteristics which result from the fact that graphene has zero band gap and possesses symmetric band structures for electrons and holes.

Important features of the plot of graphene channel conductivity as a function of gate voltage in include 1 the minimum conductivity 2 the gate voltage VNP corresponding to the minimum conductivity and 3 the slope factor K which is proportional to the capacitance of the gate and the carrier mobility of the graphene channel .

Using these three parameters the dependence of the conductivity of the graphene channel on the gate can be phenomenologically described by Equation 1 below 

Further Vis the gate voltage corresponding to the minimum conductivity of the graphene channel and is given by V V V 2 where Vis bias voltage on the source and drain electrodes and Vis a gate voltage of minimal current when Vapproaches zero. That is for a well behaved graphene field effect NDR device where the graphene channel is controlled by gate electrostatics Vmay be dependent on the bias voltage V of the source drain electrodes . This is because the electron and hole currents are always equal at the current minimum and this condition is met only when the change of Vis equal to half of the increased bias voltage V. This drain dependent Vis unique to graphene field effect devices e.g. NDR device .

In the region from the vertical line marked i in the graph to the vertical line marked ii is the negative differential resistance region in which the graphene channel exhibits a negative differential resistance.

Further in the NDR region i.e. the region from the vertical line marked i in the graph to the vertical line marked ii is characterized by a negative output conductance g which may be defined as a derivative of drain current I with respect to bias voltage V. That is in the NDR region it may be said that

In particular illustrates the drain current I as a function of gate voltage V for two different bias voltages e.g. drain voltages V and V where V V. As discussed above the point of minimum current e.g. the point of minimum conductivity of the graphene channel will shift by V V 2 i.e. V V V 2 when Vincreases. Therefore there exists a region where the current I for V V becomes less than the current I for V V yielding a negative differential resistance region which is the shaded region between the two curves in .

A more quantitative analysis of the behavior of the NDR device is given in Equations 3 4 and 5 below.

In particular an explicit expression of the output conductance g is derived as Equation 3 where W is channel width for the graphene channel and L is channel length for the graphene channel. Equation 4 shows the bias conditions for negative differential resistance where the output conductance g become negative.

Equation 5 provides some conditions e.g. preferred conditions for NDR device according to an exemplary aspect of the present invention. From Equation 5 it can be seen that it may be advantageous to have 1 a small minimum conductivity 2 a large gate capacitance for the gate and 3 a high mobility in the graphene channel so that the NDR device can operate in a smaller range of gate voltages V.

In an exemplary aspect the gate dielectric may include high dielectric materials such as aluminum oxide hafnium oxide silicon oxide yttrium oxide and zirconium oxide SrO CaO HfSiOand ZrSiO. In another exemplary aspect the preferred range of the dielectric constant for the gate dielectric is in a range from 2 to 50. In another exemplary aspect the preferred range of dielectric constant for the gate dielectric is in a range from 11 to 15.

In an exemplary aspect of the present invention the preferred range of carrier mobility is in a range from 100 cm Vs to 1 million cm Vs . In another exemplary aspect the preferred range of carrier mobility is in a range from 1000 cm Vs to 1 million cm Vs . In another exemplary aspect the preferred range of carrier mobility is in a range from 10000 cm Vs to 1 million cm Vs .

In the NDR device the range of operating gate voltages on the gate may be determined largely by the thickness of the dielectric material e.g. high k gate dielectric material in the gate dielectric . For the NDR device to operate in the range of NDR the output conductivity g must be less than 0. The gate voltage required to achieve such a condition increases with increasing thickness of the gate dielectric .

Therefore for the NDR device to be operationally practical the thickness of the gate dielectric should be small. For example in an exemplary aspect of the present invention the preferred range of gate dielectric thickness is 0.5 nm to 50 nm. In another exemplary aspect the preferred range of gate dielectric thickness is 4 nm to 20 nm.

The results of and show that negative differential resistance in the NDR device can be obtained and tuned by controlling the gate voltage V on the gate and by controlling the bias voltage V e.g. drain voltage on the source and drain electrodes 

As illustrated in the circuit includes the NDR device which may be similar in structure and function to NDR device described above. The circuit may also include inductors L and L which may include the parasitics from the cables and interconnects. The circuit may also include a capacitance C and load resistance Rwhich may also include a contribution from the parasitics.

The circuit may also include gate voltage source which is connected to the gate of the NDR device and applies a gate voltage V to the gate.

The circuit may also include voltage source which is connected to the source and drain electrodes of the NDR device and applies a bias voltage Vto the source and drain electrodes of the NDR device .

As illustrated in the load resistance R is connected to the NDR device e.g. connected to source and drain electrodes of the NDR device . As a result the load resistance R may be canceled out by the NDR device so that there is substantially no resistance in the circuit so that the circuit can sustain a resonant frequency.

As noted above with respect to the NDR device in the method the NDR device may also include a gate dielectric contacting the gate the graphene channel contacting the gate dielectric and source and drain electrodes contacting the gate dielectric and the graphene channel. Further the circuit may further include a bias voltage source and the method may further include modulating a bias voltage between the source and drain electrodes by using the bias voltage source.

With its unique and novel features the present invention may provide a circuit which can more easily integrate an NDR device using wafer scale fabrication processes than conventional circuits.

While the invention has been described in terms of one or more embodiments those skilled in the art will recognize that the invention can be practiced with modification within the spirit and scope of the appended claims. Specifically one of ordinary skill in the art will understand that the drawings herein are meant to be illustrative and the design of the inventive method and system is not limited to that disclosed herein but may be modified within the spirit and scope of the present invention.

Further Applicant s intent is to encompass the equivalents of all claim elements and no amendment to any claim the present application should be construed as a disclaimer of any interest in or right to an equivalent of any element or feature of the amended claim.

