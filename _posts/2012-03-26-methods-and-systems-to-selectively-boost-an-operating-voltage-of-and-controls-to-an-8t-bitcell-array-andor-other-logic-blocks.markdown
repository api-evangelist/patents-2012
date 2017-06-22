---

title: Methods and systems to selectively boost an operating voltage of, and controls to an 8T bit-cell array and/or other logic blocks
abstract: Methods and systems to provide a multi-Vcc environment, such as to selectively boost an operating voltage of a logic block and/or provide a level-shifted control to the logic block. A multi-Vcc environment may be implemented to isolate a Vmin-limiting logic block from a single-Vcc environment, such as to reduce Vmin and/or improve energy efficiency in the single-Vcc environment. The logic block may include bit cells of a register file, a low-level processor cache, and/or other memory system. A cell Vcc may be boosted during a read mode and/or write wordlines (WWLs) and/or read wordlines (RWLs) may be asserted with boost. A wordline decoder may include a voltage level shifter with differential split-level logic, and a dynamic NAND, which may include NAND logic, a keeper circuit, and logic to delay a keeper control based on a delay of the level shifter to reduce contention during an initial NAND evaluation phase.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09299395&OS=09299395&RS=09299395
owner: Intel Corporation
number: 09299395
owner_city: Santa Clara
owner_country: US
publication_date: 20120326
---
This invention was made with U.S. Government support under contract number HR0011 10 3 0007 awarded by the Department of Defense. The Government has certain rights in this invention.

A processor may include multiple registers which may be implemented as an array of memory bit cells referred to as a register file. A register file may be implemented with static random access memory SRAM bit cells having dedicated or decoupled read and write ports which may be implemented 8 transistor devices also referred to as dual port or 8T bit cells. A dual port or 8T bit cell may provide faster read RD and write WR completion times and may permit a lower operating voltage than a single access port or 6T bit cell.

Integrated circuits are being implemented with increasingly smaller sizes which may tend to increase variations in die to die D2D and within die WID process parameters. The variations may be at least partially mitigated with larger size devices for read and write ports allowing the circuits to operate at low voltage but at the potential cost of a higher power at high performance mode with higher switching capacitance.

In the drawings the leftmost digit s of a reference number identifies the drawing in which the reference number first appears.

System may include multiple voltage rails illustrated here as Vcc and Vcc. Vcc may be shared amongst or provided to one or more circuits or logic blocks illustrated here as systems which may operate across a relatively wide dynamic voltage and or frequency DVFS range.

A lower limit of Vcc referred to herein as Vmin of Vcc may correspond to a minimum operating voltage of systems . Conventionally where the minimum voltage of one system is higher than the minimum voltage of one or more other systems Vmin may be limited to the higher voltage and the system may be referred to as a Vmin limiting system.

Power control system may be implemented to provide multi Vcc environment for one or more systems which might otherwise constitute a Vmin limiting system in a Vcc environment . In other words power control system may be implemented to remove or isolate Vmin limiting systems from Vcc environment . This may permit more aggressive core Vcc scaling of systems in Vcc environment which may improve overall energy efficiency. Implementations of power control system are not however limited to this example.

Vcc may be generated off die or on die and may be generated or regulated with a switched capacitor voltage regulator SCVR . A SCVR may provide a relatively low supply voltage with relatively high power efficiency.

Vcc may be generated on die and may be generated or regulated with a local low dropout regulator local LDO which may also be used as a pass transistor or power gate to place systems in a reduced power consumption state.

Vcc may be minimized based on systems and power control system may be implemented to provide a higher operating voltage to systems and or to provide level shifted control to systems .

System may include one or more memory bit cells illustrated here as a bit cell . Bit cell may include contention based storage circuitry to store a logic value and may include one or more access gates to write to and or read from the storage circuitry. Examples are provided herein with reference to a bit cell having dedicated or decoupled write and read ports such as an 8T bit cell. Examples are also provided herein with respect to multiple bit cells implemented as a register file and or a low level processor cache. Methods and systems disclosed herein are not however limited to memory bit cells 8T bit cells register files or processor cache.

Power control system may include a Vcc control system to control an operating voltage Vcc of systems . Vcc control system may be implemented for example to set Vcc of bit cell to Vcc during a retention mode and or a write mode to maintain contention of the storage circuitry with minimal power. Vcc control system may be further implemented to increase or switch Vcc to Vcc during a read mode which may help to overcome contention within a read or sense system and may improve a read completion time.

Power control system may include a level shift control generator LS control generator to generate level shift and assert a control to systems at Vcc. LS control generator may be implemented to generate control based on one or more controls clocks and or data controls having a voltage swing of Vcc defined as a difference between Vcc and a voltage reference Vss.

LS control generator may include a level shift wordline decoder to generate control as a write wordline WWL and or a read wordline RWL . Assertion of a WWL at Vcc may help to overcome contention within bit cell and may improve a write completion time. Assertion of a RWL at Vcc may help to help to overcome contention within a read or sense system and may improve the read completion time.

System may be implemented with an integrated circuit IC die and may include an array of bit cells which may be implemented for example as a processor register a register file and or a low level cache.

System may further include one or more systems within a Vcc environment illustrated here as including a memory controller timer circuitry write drivers and sense circuitry .

Bit cell may include contention based storage circuitry illustrated here as cross coupled inverters and to assert and maintain opposing logic values or states Bit and at nodes and . Opposing logic values or states may also be referred to as non inverted and inverted logic values and differential logic values.

For illustrative purposes a logic value 1 may correspond to an operating voltage cell Vcc and logic value 0 may correspond to a voltage reference Vss.

During a write operation or write mode write gates and may be closed or turned on with a WWL to write W Bit and W  to nodes and of bit cell as Bit and respectively. When overwriting existing logic states at nodes and write gates and may face contention from inverters and .

During a read operation or read mode a read gate may be closed or turned on with a RWL to couple node to a bit line BL . Alternatively or additionally bit cell may include another read gate to couple node to another bit line. During the read mode gate may face contention from circuitry within sense circuitry such as described below with reference to .

Bit cell includes 8 transistor devices P and P and N through N. Bit cell may be referred to as 8T bit cell.

Devices P and N and devices P and N are implemented as cross coupled inverters to assert opposing Bit and at nodes and .

Devices N and N provide a dedicated or decoupled single ended read port to read or sense Bit at node through a local bit line LBL . LBL may be implemented as a domino style hierarchal read bit line with a domino keeper circuit . A decoupled single ended RD port with a domino style hierarchal read bit line may provide a relatively fast read evaluation path with relatively little access disturbance which may permit bit cell to operate at a relatively low Vcc in read mode.

System may be implemented as a low level cache and or dual port register file array of a single Vcc processor. Memory system is not however limited to these examples.

System may include a power control system to provide a multi Vcc environment for bit cells . Power control system may be implemented for example to control the cell Vcc and or to provide read and or write assist at Vcc. Read and or write assist may include selective increase of the cell Vcc WWL boosting and or RWL boosting. Other systems such as sense circuitry write drivers memory controller and or timer circuitry may be implemented to operate within a Vcc environment.

A power control system as disclosed herein may be implemented in accordance with Table 1 below or portions thereof. Examples are provided below with reference to . Methods and systems disclosed herein are not however limited to these examples.

Bit cell includes a first inverter devices P and N and a second inverter devices P and N . The first and second inverters are cross coupled to assert inverted logic values as Bit and . For example a Vcc i.e. logic 1 at Bit turns P off and N on to couple to Vss or ground i.e. logic 0 . Conversely Vss logic 0 at Bit turns N off and P on to couple to Vcc i.e. logic 1 .

In standby mode WWL and RWL are at Vss to turn off write gates N and N and read gate N and Vcc is applied to a power supply node to maintain states at Bit and with a voltage difference or swing of Vss Vcc.

In read mode Vcc may be applied to power supply node to increase the voltage difference between nodes Bit and to Vcc. Where Bit is at logic 1 N turns on with Vcc rather than Vcc which may help overcome contention of sense circuitry on a local bit line LBL . Alternatively or additionally RWL may be asserted at Vcc rather than Vcc which may help to overcome contention of sense circuitry on LBL .

In write mode WWL may be asserted at Vcc rather than Vcc and Vcc may be applied to power supply node rather than Vcc which may help to overcome write contention at Bit and .

Vcc mux may include multiple gates or switch devices and each to couple a power supply node of bit cell to a corresponding one of voltage rails Vcc and Vcc.

Mux control logic may be implemented to control devices and with differential controls and based on one or more controls . Control s may include a read clock or a sector specific read clock which may be generated in a timer system. Control s may have a voltage swing of Vcc and differential controls and may have a voltage swing of Vcc.

Mux control logic may be implemented to switch differential controls and with substantially equal rise time delays and fall time delays such as described below with reference to .

WL decoder may include a voltage level shifter to level shift a control WL SEL from a voltage swing of Vcc to a voltage swing of Vcc. WL SEL may be generated based on a read and or write clock and a sector select control such as described below with reference to .

WL decoder may further include a NAND system to evaluate RD WR CLK and a wordline enable control WL En . WL En may have voltage swings of Vcc and may be generated based on a sector select control and a lower order address bit such as described below with reference to .

NAND logic may be implemented to pull node up towards Vcc through a device P when input is at Vss which may correspond to a pre charge mode.

NAND logic may be implemented to pull node down towards Vss through devices N and N when inputs and are at Vcc and Vcc respectively which may correspond to a write or read mode.

NAND system may include a wordline driver which may include an inverter to assert Vcc on R W WL in write or read mode when node is at Vss. In other words NAND system may be implemented to provide WWL boost and or RWL boost.

When NAND logic asserts Vcc at node a leakage current may flow from node to Vss through devices N and N.

NAND system may include a wordline keeper WL keeper to compensate for the leakage current. WL keeper may include a device K to pull up a node to Vcc. WL keeper may further include a device K to couple node to node when output is inactive at Vss and to de couple node from node when output is active at Vcc.

In a static implementation a gate of device K may be coupled to Vss to maintain WL keeper in an on state. The static implementation may result cause contention at node when NAND circuitry pulls node from Vcc to Vss. The contention may delay completion of the transition and may result in a corresponding assertion delay on output .

Alternatively WL keeper may be implemented as a dynamic keeper to reduce or eliminate contention at node during an initial part of the NAND evaluation phase. A dynamic implementation may reduce NAND evaluation time and may be implemented to recover a delay penalty of voltage level shifter . Dynamic control may be implemented in logic to generate a keeper control WL KPR . The dynamic control logic may be implemented to delay turn on of device K. Activation of WL KPR may be delayed for example by an amount of delay imparted by level shifter .

During the delay device K is off to isolate node from Vcc. After the delay WL KPR is pulled down to Vss to enable device K to pull up and hold node at Vcc depending upon a state of output .

WL decoder may include a second voltage level shifter to generate WL KPR which may be similar to voltage level shifter to provide substantially equal delay.

Where WL keeper is dynamically controlled NAND system may referred to as a dynamic NAND system. A dynamic NAND system or a portion thereof may be shared amongst multiple wordlines such as described below with reference to .

NAND systems may each be implemented to receive a clock RD WR CLK and a corresponding wordline enable .

NAND systems may be further implemented to share device N to couple nodes of NAND circuits to Vss when any one wordline controls is to be asserted. Sharing of device N may reduce NAND evaluation time.

NAND systems in combination with device N may each operate substantially as described above with reference to NAND system in .

A dynamic NAND system may be implemented in place of multiple per WWL or per RWL static NAND circuits.

Memory access control logic may include one or more of pre decoder logic timer logic and or bit cell input output I O logic which may include wordline drivers pre charge logic and or sense logic.

In the example of pre decoder logic includes logic to generate a wordline select control based on a read and or write clock illustrated here as R W CLK and a sector select control SEC SEL.

Timer logic includes logic to generate per wordline or wordline specific enable controls based on the SEC SEL control and corresponding wordline specific lower order address bit s .

In access control logic and WL decoder are illustrated with logic to support a set of j 1 wordlines. The illustrated logic may be replicated to support additional sets of j 1 wordlines.

When Vss is applied to an input a node is pulled up to Vcc by an inverter and a node is pulled down to Vss by an inverter .

In addition a device N turns off to isolate node from Vss and a device N turns on pull down node to Vss. When node is pulled down to Vss P turns on to pull up node to Vcc which turns P off to isolate node from Vcc.

Conversely when Vcc is applied to input node is pulled down to Vss and node is pulled up to Vcc. In addition N turns on to pull down node to Vss and N2 turns off to isolate node from Vss. When node is pulled down to Vss P turns on to pull up node to Vcc which turns P off to isolate node from Vcc.

Thus when Vss is applied to input nodes and are pulled down to Vss. When Vcc is applied to input nodes and are pulled up to Vcc and Vcc respectively.

Node represents an inverted version of input node represents delayed version of input and node represents a level shifted delayed version of input . A delay at node in terms of rise time and or fall time relative to input may be substantially equal to a delay at node .

Regarding output driver when nodes and are pulled down to Vss a device Nturns OFF to isolate an output from Vss and a device Pturns on to pull up output to Vcc. Conversely when nodes and are pulled up to Vcc and Vcc respectively Pturns off to isolate output from Vcc and Nturns on to pull down output to Vss. Output driver thus inverts the states at nodes and and drives the result a logic value 1 with Vcc.

Differential core may be referred to as a split level differential in view of node having a voltage swing of Vcc and node having a voltage swing of Vcc.

Similarly output driver may be referred to as a split level inverting output driver and LS may be referred to as an inverting split level level shifter.

Differential core may be similar to differential core in and output drivers and may be similar to output driver in .

As described above with reference to nodes and in opposing or differential logic states are asserted at nodes and in . Thus opposing or differential logic states are asserted at outputs and .

A delay at output in terms of rise time and or fall time relative to input may be substantially equal to a delay at output . The delay at outputs and may be substantially equal to the delay at output of level shifter in . Equal rise time and or fall time delay within and or amongst levels shifters may help to minimize effects of delay on critical races such as read wordline RWL to pre charge PCH race in read mode.

Vcc control system may be implemented to provide one of multiple selectable voltages to a power supply node of a system . System may include multiple bit cells such as described in one or more examples herein.

Vcc control system may be implemented to maintain power supply node at Vcc in standby mode and or write mode and to increase or switch the voltage at node to Vcc during read mode.

Vcc control system and or Vcc mux may be implemented to selectively increase or switch the operating voltage to Vcc for each of multiple subsets of bit cells such as described below with reference to .

Vcc mux may be implemented to independently control the operating voltage for each of half bundle and half bundle .

For example Vcc mux may be implemented to maintain operating voltages half bundle and half bundle at Vcc in retention mode and or write mode and to increase or switch the operating voltage to Vcc for one of half bundles and when a read operation is directed to a bit cell within the half bundle.

Vcc mux may be implemented to provide half bundle based Vcc control based on one or more clocks and or controls which may have voltage swings of Vcc may be generated in pre decoder logic and or timer logic and or may be functionally equivalent to local bit line LBL pre charge signals.

In example logic states provided for controls RD LF WR LF RD RT and WR RT corresponding to read mode for half bundle i.e. Vcc Vcc and write mode for half bundle i.e. Vcc Vcc . Final outputs of Vcc mux may be driven by a dual output split level level shifter such as described in one or more examples herein.

Vcc mux may be implemented on an integrated circuit IC die within local input output circuitry of half bundles and such as described below with reference to .

In Vcc mux circuitry is placed within local I O areas of corresponding bit cells. For example a dual output split level level shifter is placed with LBL pre charge logic in a decoder gap area associated with LBL merge logic.

Dynamic level shifting NANDs may be located in decoder areas as illustrated here at and may receive corresponding RD WL KPR and WR WL KPR controls from timer logic. As described further above dynamic level shifting NANDs may be implemented instead of static NANDs with little or no overall increase in area.

RWL drivers and WWL drivers may be located in corresponding RD and WR decoder areas as illustrated here with a RD WR Dry . Alternatively one or more write bit line drivers may be placed in a LBL merge area as illustrated here with a WR Dry .

Methods and systems disclosed herein may be implemented to provide bit cell Vcc boosting RWL boosting and or WWL boosting.

RWL boosting and bit cell Vcc boosting may enable a larger on current for the read port without necessitating a larger read port. Also an RWL only boosting mode may be enabled by boosting the RWL without increasing bit cell operating voltage.

WWL boosting may improve contention without necessitating a larger write access device and or without reducing a voltage threshold VTH of the write access device.

WWL boosting may be implemented without reducing a dynamic retention margin of unselected cells of the same column.

Dynamic boosting as disclosed herein may be implemented with a Vmax voltage while other circuitry such as a WL pre decoder sense circuits timer and or column I O may operate at a lower core Vcc or Vmin. Dynamic boosting may permit relatively aggressive core Vcc scaling or Vmin reduction which may improve overall energy efficiency.

Methods and systems disclosed herein may be implemented in hardware software firmware and combinations thereof including discrete and integrated circuit logic application specific integrated circuit ASIC logic and microcontrollers and may be implemented as part of a domain specific integrated circuit package and or a combination of integrated circuit packages.

Methods and systems disclosed herein may be implemented with respect to one or more of a variety of systems such as described below with reference to . Methods and systems disclosed herein are not however limited to the example of .

Power control system may be implemented to provide a multi Vcc environment for a portion of processor communication system and or user interface system such as described in one or more examples herein.

In the example of multi Vcc power control system is implemented as part of a memory system which may represent a register file or low level cache of processor system .

Communication system may be implemented to interface with a communication network which may include a wired and or wireless communication system.

User interface system may include a human interface device HID to provide user input to processor and or communication system . HID may include for example and without limitation one or more of a key board a cursor device a touch sensitive device and or a motion and or image sensor. HID may include a physical device and or a virtual device such as a monitor displayed or virtual keyboard.

System or portions thereof may be implemented within one or more integrated circuit dies and may be implemented as a system on a chip SoC .

System may correspond to for example and without limitation a computer system a personal communication device and or a television set top box.

System may include a housing and one or more of processor system communication system and user interface system or portions thereof may be positioned within the housing. The housing may include without limitation a rack mountable housing a desk top housing a lap top housing a notebook housing a net book housing a set top box housing a portable housing and or other conventional electronic housing and or future developed housing.

Methods and systems are disclosed herein with the aid of functional building blocks illustrating functions features and relationships thereof. At least some of the boundaries of these functional building blocks have been arbitrarily defined herein for the convenience of the description. Alternate boundaries may be defined so long as the specified functions and relationships thereof are appropriately performed.

While various embodiments are disclosed herein it should be understood that they have been presented by way of example only and not limitation. It will be apparent to persons skilled in the relevant art that various changes in form and detail may be made therein without departing from the spirit and scope of the methods and systems disclosed herein. Thus the breadth and scope of the claims should not be limited by any of the example embodiments disclosed herein.

