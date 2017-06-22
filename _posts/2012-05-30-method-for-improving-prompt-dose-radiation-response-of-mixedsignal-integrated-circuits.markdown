---

title: Method for improving prompt dose radiation response of mixed-signal integrated circuits
abstract: A system and method for improving the prompt dose radiation response of mixed-signal integrated circuits is disclosed. An internal analog circuit inside a mixed-signal integrated circuit generates an internal analog reference voltage that has been used for various purposes in the integrated circuit. At least one external capacitor is added either internal or external to a device package of the integrated circuit. The external capacitor reduces any change in the internal reference voltage due to prompt dose radiation by stabilizing the internal reference voltage and thus improves prompt dose radiation response of mixed-signal integrated circuits. A much greater value of capacitance may be provided without increase in dielectric rupture suceptability or decrease in manufacturing yield which may be associated with added on-chip capacitance. This increased capacitance primarily reduce the amount of disturbance caused to the internal node during a prompt dose radiation event.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08815614&OS=08815614&RS=08815614
owner: BAE Systems Information and Electronic Systems Integration Inc.
number: 08815614
owner_city: Nashua
owner_country: US
publication_date: 20120530
---
This Application claims rights under 35 USC 119 e from U.S. Application Ser. No. 61 491 956 filed Jun. 1 2011 the contents of which are incorporated herein by reference.

This invention was made with United States Government support under Contract No. NRO000 08 C 0358 awarded by the Naval Research Laboratory. The United States Government has certain rights in this invention.

Embodiments are generally related to semiconductor devices. Embodiments are also related to radiation hardening semiconductor devices. Embodiments are additionally related to an apparatus and method of hardening mixed signal Integrated Circuits IC having internally generated analog voltages. Embodiments are additionally related to an apparatus and method of improving the prompt dose radiation response of mixed signal integrated circuits.

Radiation hardening is a method of designing and testing electronic components and systems to make them resistant to damage or malfunctions caused by ionizing radiation particle radiation and high energy electromagnetic radiation such as would be encountered in outer space high altitude flight around nuclear reactors particle accelerators during nuclear accidents or nuclear warfare. For example gamma rays are produced in fission and as a result of other neutron reactions and nuclear excitation of the weapon materials. These rays appear within a second or less after a nuclear explosion. The radiations from these sources are known either as prompt or instantaneous gamma rays. Such radiations cause damage or malfunctions to semiconductor devices.

An integrated circuit with both analog circuits and digital circuits on a single semiconductor die is known as a mixed signal integrated circuit. In a prompt dose radiation environment mixed signal integrated circuits are particularly susceptible to functional disruption due to signal level changes induced during the radiation pulse. Various radiation hardening techniques are in use today to harden the mixed signal integrated circuit.

Internally generated analog reference voltages however are more difficult to harden because there is a practical limit to the amount of in circuit capacitance that can be added to the chip without affecting die size. Also an increase in on chip capacitance typically also decreases defect driven yield and increases susceptibility to heavy ion induced dielectric rupture.

A need therefore exists for an improved way to radiation harden circuits having internally generated analog voltages.

The following summary is provided to facilitate an understanding of some of the innovative features unique to the disclosed embodiment and is not intended to be a full description. A full appreciation of the various aspects of the embodiments disclosed herein can be gained by taking the entire specification claims drawings and abstract as a whole.

It is another aspect of the disclosed embodiments to provide radiation hardening semiconductor devices.

It is yet another aspect of the disclosed embodiments to provide for an improved apparatus and method of hardening a mixed signal integrated Circuit IC having internally generated analog voltages.

It is a further aspect of the present invention to provide for an improved apparatus and method of improving the prompt dose radiation response of the mixed signal integrated circuit by adding at least one external capacitor within a device package.

It is another aspect of the present invention to provide for an improved apparatus and method of improving the prompt dose radiation response of the mixed signal integrated circuit by adding at least one external capacitor external to the device package.

It is a yet another aspect of the present invention to stabilize a change in a reference voltage generated by an internal analog circuit during prompt dose radiation.

The aforementioned aspects and other objectives and advantages can now be achieved as described herein. A system and method for improving the prompt dose radiation response of mixed signal integrated circuits is disclosed. An internal analog circuit in a mixed signal integrated circuit generates an internal analog reference voltage utilized for various purposes in the integrated circuit. At least one external capacitor is added either internal or external to a device package of the integrated circuit. The external capacitor reduces any change in the internal reference voltage due to prompt dose radiation by stabilizing the internal reference voltage. The stabilized reference voltage improves prompt dose radiation response of the mixed signal integrated circuits.

A much greater value of external capacitance may be provided without increase in dielectric rupture suceptability or decrease in manufacturing yield which may be associated with added on chip capacitance. This increased capacitance primarily reduces the amount of disturbance caused to the internal node during a prompt dose radiation event.

The particular values and configurations discussed in these non limiting examples can be varied and are cited merely to illustrate at least one embodiment and are not intended to limit the scope thereof.

Referring to a simplified block diagram of a radiation hardening apparatus utilized for improving the prompt dose radiation response of a mixed signal integrated circuit is disclosed. The package encloses the mixed signal Integrated Circuit IC . The IC includes at least one internal analog circuit and at least one internal digital circuit . The internal analog circuit generates a reference voltage for use within the integrated circuit . At least one capacitor is externally connected to the integrated circuit and mounted external to the package . The internal reference voltage of internal analog circuit is susceptible to upset in prompt dose radiation. The capacitor stabilizes the changes in the internal reference voltage and hence improves the prompt dose radiation response of the IC .

Referring to a schematic diagram of a radiation hardening apparatus depicted in is disclosed. The capacitor is mounted external to the package and connected to an external package connector . An internal package connection is made from an internal package connector to an internal IC connector . Then from the internal IC connector a connection to the internal analog circuit is made. An internal on chip capacitor limited in practical magnitude is also connected to the internal analog circuit as shown. Also such capacitor is susceptible to dielectric rupture due to heavy ion bombardment and decreases defect driven yield. Other internal package connections are also shown in .

Referring to a flow chart showing a method of testing the mixed signal integrated circuit in prompt dose radiation response is disclosed. As said at block the integrated circuit is exposed to test prompt dosage radiation. Then the change in the reference voltage is measured on the integrated circuit during prompt dose testing as said at block and as said at block the slow recovery time of the reference voltage is documented. Finally based on the change in reference voltage and recovery time the external capacitor value is calculated as illustrated at block . Note that the calculated external capacitor can be connected external to the integrated circuit to stabilize the change in reference voltage.

Note that a much greater value of the external capacitance may be provided without increase in the dielectric rupture suceptability or decrease in manufacturing yield which may be associated with added on chip capacitance. This increased capacitance is meant primarily to reduce the amount of disturbance caused to the internal node during the prompt dose radiation event. The capacitance can be of a much higher value for example 1 10 F and is not susceptible to dielectric rupture due to heavy ion bombardment and does not impact defect driven yield.

The internal analog circuit can be a band gap reference circuit and other circuit designs can also be used for similar purpose without limitation. The external package connections can include pins balls and columns without limitation. The internal package connections may include wire bond C4 ball solder bump without limitation. The device package may include interface wiring between integrated circuit and external package connection. The internal on chip capacitor is limited in practical magnitude susceptible to dielectric rupture due to heavy ion bombardment and decreases defect driven yield.

It will be appreciated that variations of the above disclosed and other features and functions or alternatives thereof may be desirably combined into many other different systems or applications. Also that various presently unforeseen or unanticipated alternatives modifications variations or improvements therein may be subsequently made by those skilled in the art which are also intended to be encompassed by the following claims.

