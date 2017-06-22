---

title: Methods and systems to convert a pulse power demand to a constant power draw
abstract: Methods and systems to translate a pulse power demand of a pulse load to a constant power draw, and to maintain a desired peak output voltage over time. A power converter (PC) provides power from a power source to a charge store, which provides pulse power to the load. A PC controller continuously monitors an output current of the PC and an output voltage of the charge store, and controls the PC to draw constant power from the source, at a level indicated by a power command. A peak voltage controller periodically adjusts the power command, such as to compensate for time-varying effects, based on a peak voltage reference and the output voltage of the charge store measured at times of synchronization pulses. The peak voltage controller generates the synchronization pulses based on rising edges of a pulse current, or receives the synchronization pulses from the radar system controller.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08878505&OS=08878505&RS=08878505
owner: The Johns Hopkins University
number: 08878505
owner_city: Baltimore
owner_country: US
publication_date: 20120626
---
This application claims the benefit of U.S. Provisional Patent Application Ser. No. 61 569 381 filed Dec. 12 2011 which is incorporated herein by reference in its entirety.

This invention was made with U.S. Government support under Naval Sea Systems Command NAVSEA contract number N00024 D 6606. The U.S. Government has certain rights in the invention.

Disclosed herein are methods and systems to regulate a power converter to draw a constant power level from a power source to a charge store which provides pulsed power to a pulse load such as a radar system and methods and systems to maintain a desired peak output voltage of the charge store such as to accommodate time varying effects.

A radar system presents periodic and instantaneously high current pulse loads to a power source or an upstream power bus.

The pulse load may result in large ripple currents on the power source or upstream power bus which may impact power quality for other loads. Where the power source includes a generator such as with ship based tactical or transportable radar large ripple currents may cause instability and mechanical stresses on the generator.

Disclosed herein are methods and systems to translate a pulse power demand of a pulse load such as a radar system to a constant power draw from a power source.

Also disclosed herein are methods and systems to maintain a desired peak output voltage to the pulse load over time such as to compensate for time varying effects that might otherwise alter the peak output voltage over time. Time varying effects may include temperature changes and or component aging.

A system may include a charge store to provide power to a pulse load such as a radar system. The system may further include a power converter PC to provide power from a power source to the charge store and a PC controller to continuously control the PC to draw constant power from the power source. The PC controller may control the PC based on a sensed output current of the PC a sensed output voltage of the charge store and a power command which may represent a desired average power level.

The system may further include a peak voltage controller to periodically adjust the power command to maintain a peak output voltage substantially equal to a peak voltage reference.

The peak voltage controller may determine the peak output voltage based on the sensed output voltage of the charge store in synchronization to the start of the load pulse. The synchronization pulse may be generated on the rising edges of the pulse load current or may be provided by the radar system controller.

The peak voltage controller may periodically adjust the power command at a frequency of the pulse load.

The peak voltage controller may vary an adjustment step size based on a magnitude of a difference between the peak output voltage and the peak voltage reference and may adjust the power command by one of multiple step sizes based on the magnitude of the difference.

The peak voltage controller may include a field programmable gate array FPGA to compare the peak output voltage to one or more reference values.

In the drawings the leftmost digit s of a reference number identifies the drawing in which the reference number first appears.

For illustrative purposes pulse load is described herein with reference to a radar system. Pulse load is not however limited to a radar system.

Power source may include an alternating current AC source and may include and AC DC converter to convert AC power to direct current DC power.

System includes a charge store to provide pulsed power to radar system . Charge store may include a capacitive storage system.

Pulse loading from radar system may impart a triangular ripple voltage on top of a DC voltage at having a ripple frequency equal to a pulse repetition frequency of a transmitted pulse train of radar system .

System further includes a PC controller including a constant power controller CPC to control PC to convert the pulse power demand of radar system to a constant power demand on power source . PC and PC controller may protect source from otherwise adverse effects of the pulsed loading of charge store .

In CPC provides a PC control based on a sensed voltage Vcap of charge store a sensed current Iout sensed output from PC and a desired or reference power level illustrated here as a power command Vpout  cmd .

CPC may adjust PC control to increase the output current of PC when Vcap decreases and to decrease the output current of PC when Vcap increases in order to maintain output power of PC substantially equal to Vpout  cmd.

Power command may be based on a power command Vpout  cmd which may represent a desired average power level. Power command may correspond to the average power level for the next set of transmitted pulses for the radar system and may be uploaded or received from a radar system controller.

Transmit pulses of radar system may have constant and or variable pulse widths. For both constant and variable pulse widths when duty cycle of the transmit pulses is maintained constant the power averaged over each pulse repetition interval is constant. When the power delivered by PC is constant the power drawn from power source is also constant. The duty cycle of repetitive transmit pulses may be expressed as 

Where the pulse width and or pulse repetition interval of radar system change power command Vpout  cmd may change as well such as described further below. When power command is changed a corresponding response time of system is determined by a control bandwidth of PC .

In PC controller further includes a peak voltage controller to generate an adjustment control Vpout adjust to maintain a desired peak output voltage of charge store . PC controller further includes a module to adjust Vpout  cmd based on Vpout adjust. Peak voltage controller is described further below with reference to .

In CPC includes a divider to determine a desired current command Iout cmd as out cmd out2 cmd cap EQ. 2 where Vpout  cmd is the desired power command represented by a voltage level.

CPC further includes a subtractor to provide an error or difference based on a difference between Iout cmd and Iout sensed.

CPC further includes a current compensator to adjust PC control to reduce difference to maintain the power of PC substantially equal to Vpout  cmd.

In peak voltage controller controls Vpout adjust 128 so that Vcap returns to a peak voltage reference value just prior to each new load pulse. When Vcap is too low Vpout adjust is increased. If Vcap is still too low at the next synch pulse Vpout adjust is further adjusted. This may be repeated until Vcap is at the peak voltage reference value. Conversely when Vcap is above the peak voltage reference value Vpout adjust may be reduced.

Peak voltage controller may compensate for time varying effects that may impact peak voltage of charge store . Time varying effects may result from environmental changes e.g. temperature change and or component aging. As a result of such effects the desired output power of PC may not correspond to power command .

Peak voltage controller may update adjustment control Vpout adjust once per transmit period of radar system . Vpout adjust may thus be corrected or adjusted more frequently for short pulse repetition intervals than for long pulse repetition intervals. For extremely short pulse repetition intervals it may be desirable to update adjustment control Vpout adjust less frequently due to bandwidth limitations of the controls. The determination of the adjustment should be performed in sync with the start of a new transmit pulse.

CPC may be implemented substantially with analog circuit components whereas peak voltage controller may include analog components digital components and or combinations thereof.

In peak voltage controller includes synchronizer circuitry to generate sync pulses to indicate times at which Vcap is at a peak voltage. Synchronizer circuitry generates sync pulses based on rising edges of a sensed pulse current Ipulse sensed . Synchronizer circuitry may for example include a limiter circuit to output an indication when Ipulse sensed exceeds a threshold value that corresponds to the beginning of a transmit pulse of radar system . Circuitry further includes a register such as a flip flop to register indication as synch pulse to a control system .

Alternatively sync pulses coincident with the start of the transmit pulse may be provided by radar system .

Control system determines a peak voltage of Vcap based on a value of Vcap coincident with a sync pulse compares the peak voltage to one or more reference values and selectively adjusts Vpout adjust based on a the comparison s .

Peak voltage controller may help to support long pulse operation for a variety of transmit intervals. For a long pulse the output voltage of charge store may droop before the end of the pulse. Peak voltage controller ensures that that charge store is always recharged to the same level which ensures that all consecutive long pulse profiles will be the same even if the output voltage droops. In other words regulation of the peak output voltage helps to maintain quality of pulses during long pulse width transmissions and provides consecutive long pulses with substantially identical energy.

Control system may vary an adjustment step size of Vpout adjust based on a magnitude of a difference between Vcap and a desired or peak voltage reference and may adjust Vpout adjust by one of multiple selectable step sizes based on the magnitude of the difference such as described below with reference to .

As described below logical operations maintain the peak voltage of Vcap between values of 32.75 and 33.25 i.e. for a peak voltage reference value of 33 . Methods and systems disclosed herein are not however limited to the examples of .

At out 0 Vpout adjust is initialized to 0. This may be performed upon a system initialization or power up.

At when in 1 sync pulse is below a sync pulse threshold value a value n is set to 1 to indicate an that sync pulse is inactive.

At when in 1 sync pulse is above the sync pulse threshold value n is set to 2 to indicate that sync pulse is active.

In the example of the synch pulse threshold value is set to 0.9. Methods and systems disclosed herein are not however limited to these examples.

At when Vcap is greater than a reference value of 33.25 Vpout adjust is decremented by a step size of 0.5.

At when Vcap is greater than a reference value of 34 Vpout adjust is decremented by a step size of 1.0.

At when Vcap is greater than a reference value of 35 Vpout adjust is decremented by a step size of 1.5.

At when Vcap is greater than a reference value of 36 and Vpout adjust is above zero Vpout adjust is reset to zero.

In other words when Vcap exceeds the peak voltage reference value of 33 and as the magnitude of the difference between Vcap and the peak voltage reference value of 33 increases Vpout adjust is decremented with increasing step sizes. When the magnitude of the difference exceeds a difference threshold of 36 33 3 Vpout adjust is reset to zero regardless of the existing value of Vpout adjust. The difference threshold may correspond to an over voltage condition such as described further below.

Similarly at through when Vcap is below the peak voltage reference value of 33 and as the magnitude of the difference between Vcap and the peak voltage reference value of 33 increases Vpout adjust is incremented with increasing step sizes i.e. 0.5 1.0 or 1.5 . When the magnitude of the difference exceeds a second difference threshold of 33 30 3 Vpout adjust is reset to zero regardless of the existing value of Vpout adjust. The second difference threshold may correspond to an under voltage condition.

Control system may be implemented with integrated circuit IC logic which may include a field programmable gate array FPGA an application specific integrated circuit ASIC and or other IC devices. Control system may further include an analog to digital converter ADC to quantize Vcap for comparison to one or more reference values and may include a digital to analog converter DAC to output Vpout adjust as an analog control.

As described further above with reference to pulsed loading from radar system may impart a ripple voltage on top of a DC voltage at having a frequency equal to a pulse repetition frequency of a transmitted pulse train of radar system . System may include a voltage regulator VR to reduce and or eliminate the ripple voltage from the pulsed power provided to radar system .

As further described above charge store serves as an energy reservoir to provide pulse energy or power to radar system . Where a larger triangle ripple is allowed on capacitors of charge store less capacitance is needed to provide the pulse energy. A maximum allowable ripple may be set based on a maximum voltage rating of the capacitors and an allowable input voltage range of VR to maintain a regulated output. Total capacitance of charge store may be determined based on the energy requirement of the longest anticipated pulse duration.

VR may include a linear voltage regulator and PC may include a switching based DC DC converter such as described below with reference to . Alternatively VR and PC may each include a switching based DC DC converter.

A switching frequency of a DC DC converter is typically much higher than the ripple frequency due to radar pulse repetition frequency.

A power draw from power source may be more stable where PC and VR are implemented as switching DC DC converters relative to a situation where VR is implemented as a linear regulator. A switching DC DC converter implementation of VR may provide greater overall system efficiency.

Where VR is implemented as a switching DC DC converter power command may remain constant when the pulse width of radar transmissions change provided that the duty cycle of the radar transmission is constant and an efficiency of the switching DC DC converter is constant.

In a linear voltage regulator average losses change with load pulse width. Thus where VR includes a linear regulator the average voltage into the linear regulator varies as the pulse width varies. In order to maintain a constant power draw from power source while maintaining a constant peak output voltage of charge store power command Vpout  cmd should change with changes in the load pulse width even where the duty cycle of the pulse load is constant.

In PC includes a switch circuit and a gate driver to control on and off times of switch circuit such as with a pulse width modulated PWM control . The output current of PC is determined by a duty cycle of PWM control which may be expressed as Duty Cycle 502 ON Time 502 ON time 502 OFF time . EQ. 3 

Gate driver is controllable with a gate driver control . In the example of system includes a comparator to generate gate driver control based on a difference a control and a sensed current of PC .

Control may correspond to PC control or may be generated from a combination of PC control and one or more other controls.

For example in system further includes an over voltage protection OVP loop which may be implemented as a relatively fast acting or instantaneously active loop. When Vcap reaches an OVP threshold OVP loop activates to provide an OVP control to reduce the current output of PC . In this example control is generated based on a combination of PC control and OVP control .

The OVP threshold may be set so that under normal operation with relatively small differences between the desired output power of PC and the actual output power of PC OVP loop is not activated. A voltage rating and hence a voltage derating requirement of capacitors of charge store may also be considered in setting the OVP threshold.

Where PC controller includes peak voltage controller and the OVP threshold may be set higher than the peak voltage reference. In this example OVP loop may be activated to prevent Vcap from exceeding the OVP threshold while peak voltage controller continues to adjust Vpout adjust to bring the peak value of Vcap to the peak voltage reference value.

Simulator model includes a current source in place of power source and PC . Simulator model further includes a linear voltage regulator and a pulse load . Current source may be implemented and or simulated as an ideal current source and pulse load may simulate a radar system. Pulse load is controllable with commands to provide variable and or multiple pulse loads or profiles.

The ideal and error curves of illustrate error in the current pulse provided to load when peak voltage controller is disabled.

It can be seen from that after about 1 second the power command has been adjusted to correct for peak voltage error and the corrected curves match the ideal curves.

It can further be seen from that at time 2.017 seconds when the second power command is issued with the 10 error the adjustment command is already at the correct value and no error is seen for the second set of pulses. The 10 instantaneous error is an exaggeration of real operational conditions because variations due to temperature or aging will typically occur relatively slowly over time rather than instantaneously. thus illustrate that methods and systems disclosed herein may be implemented to adjust

the power command in a time period of about one second to correct for an instantaneous application of a command with a 10 error.

 Vout corrected Ipulse corrected . Timing diagram further includes Power in determined as Vin linreg corrected Ideliver corrected .

At power is provided from a source to a charge store under control of a power converter PC such as described above with respect to charge store and PC .

At pulsed power is provided from the charge store to a load such as described above with respect to charge store and load .

At output power of the PC is continuously monitored relative to a power command and the PC is controlled as needed to maintain the output power at a level indicated by the power command such as described above with respect to CPC .

The continuous monitoring and controlling at may include dividing a sensed output voltage of the charge store by the power command to provide a current command determining a difference between the current command and a sensed output current of the power converter and adjusting an output current command to the power converter as needed to reduce and or minimize any difference.

At a peak output voltage of the charge store is periodically monitored relative to a peak voltage reference and the power command is selectively adjusted i.e. adjusted as needed to reduce and or minimize any difference between the peak output voltage and the peak voltage reference such as described above with respect to peak voltage controller .

The periodically adjusting at may include determining the peak output voltage of charge store based on the sensed output voltage of the charge store at times of synchronization pulses.

The synchronization pulses may be generated from the rising edges of a sensed pulse current provided to the load. Alternatively the synchronization pulses may be provided by a control system associated with the load.

The periodically monitoring and selective adjusting at may be performed at a frequency of the pulsed power provided to the load or a lower frequency.

The selective adjusting at may include varying an adjustment and or selecting one of multiple step sizes based on a magnitude of the difference between the peak output voltage and the peak voltage reference such as described above with reference to .

Returning to system may be implemented as a forward voltage mode converter with peak current mode control. System is not however limited to forward voltage mode converters. Rather system may be implemented with one or more of a variety of converter topologies and or with an average current mode control.

PC and VR represent corresponding first and second stages of a two stage power topology which may be similar to a power factor correction PFC design that utilizes two power stages. For a PFC function an input current is shaped to match a sinusoidal input voltage mimicking a current profile of a resistor thereby producing a high power factor. In order to achieve input characteristics of a resistor the output voltage of the first power stage has a high sinusoidal ripple component and the second power stage provides a regulated voltage to the load. Methods and systems disclosed herein may be implemented to provide similar characteristics as a PFC in that the current draw mimics that of a resistor. Since the radar system is powered by DC voltage the desired current is DC even though a load profile of radar system includes relatively large pulse currents. As with a PFC design the output voltage of charge store i.e. the voltage at may also be relatively large. For a radar application the delta voltage or delta charge provides an energy reservoir to support the pulse load.

A constant power draw from power source may also be achieved by replacing PC with a relatively large inductor and capacitor filter. In such a situation PC controller may permit the large inductor to be omitted without alteration of charge store provided that VR is not altered. Elimination of the inductor may provide weight and size savings. For high power radar systems with low pulse repetition frequencies the size of this inductor is typically very large and heavy elimination of which may provide significant savings in weight and size.

One or more features disclosed herein may be implemented in hardware software firmware and combinations thereof including discrete and integrated circuit logic field programmable gate arrays FPGAs application specific integrated circuit ASIC logic and microcontrollers and may be implemented as part of a domain specific integrated circuit package and or a combination of integrated circuit packages.

Software may include a computer readable medium encoded with a computer program including logic or instructions to cause a processor to perform one or more functions in response thereto. The computer readable medium may include a transitory and or non transitory medium. The processor may include a general purpose instruction processor a controller a microcontroller and or other instruction based processor.

Methods and systems are disclosed herein with the aid of functional building blocks illustrating functions features and relationships thereof. At least some of the boundaries of these functional building blocks have been arbitrarily defined herein for the convenience of the description. Alternate boundaries may be defined so long as the specified functions and relationships thereof are appropriately performed.

While various embodiments are disclosed herein it should be understood that they have been presented by way of example only and not limitation. It will be apparent to persons skilled in the relevant art that various changes in form and detail may be made therein without departing from the spirit and scope of the methods and systems disclosed herein. Thus the breadth and scope of the claims should not be limited by any of the examples disclosed herein.

