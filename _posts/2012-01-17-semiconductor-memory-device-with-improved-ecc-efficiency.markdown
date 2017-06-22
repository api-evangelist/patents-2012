---

title: Semiconductor memory device with improved ECC efficiency
abstract: Memory cells store k bits of data (k is a natural number not less than 2) into a single cell. A number n of data storage circuits store externally supplied k bits of data to write data into the memory cells. A control circuit inputs the data on a first page, a second page, . . . , a k-th page to every h (h≦n) of the data storage circuits and then writes the data in the n data storage circuits into the memory cells.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08406054&OS=08406054&RS=08406054
owner: Kabushiki Kaisha Toshiba
number: 08406054
owner_city: Tokyo
owner_country: JP
publication_date: 20120117
---
This application is a continuation application of U.S. application Ser. No. 12 342 297 filed Dec. 23 2008 which is based upon and claims the benefit of priority from prior Japanese Patent Application No. 2007 338241 filed Dec. 27 2007 the entire contents of both of which are incorporated herein by reference.

This invention relates to a semiconductor memory device and more particularly to a NAND flash memory capable of storing multilevel data into a single memory cell using a plurality of bits.

In a NAND flash memory a plurality of cells arranged in the column direction are connected in series thereby constituting a NAND cell. The drain side of the NAND cell is connected via a select gate to the corresponding bit line. Each bit line is connected to a write latch circuit and a read latch circuit. A read operation or a write operation is performed on all or half of the cells e.g. 2 to 4 kB of cells arranged in the row direction. The writing or reading unit is termed a page. In an erase operation the threshold voltage of a memory cell is set to a negative voltage and electrons are injected into for example the floating gate of the memory cell by a write operation thereby setting the threshold voltage to a positive voltage.

With the recent increase in the storage capacity a multilevel memory which sets a plurality of threshold levels threshold voltages in a single cell and stores a plurality of bits of data has been developed e.g. Jpn. Pat. Appln. KOKAI Publication No. 2004 192789 . For example when 4 threshold levels have been provided 2 bits of data can be stored in one cell. When 8 threshold levels have been provided 3 bits of data can be stored in one cell. When 16 threshold levels have been provided 4 bits of data can be stored in one cell. When multilevel data is stored a cell is composed of a plurality of pages. For example when 4 threshold levels are provided in one cell the cell is composed of 2 pages. When 8 threshold levels are provided in one cell the cell is composed of 3 pages. When 16 threshold levels are provided in one cell the cell is composed of 4 pages. Each page is specified by an address. The memory cell is written into beginning with the first page.

When data is stored in a memory cell the threshold level of a cell already written into might vary due to the influence of erroneous writing or the writing of data into an adjacent cell. As a result of a variation in the threshold level the accuracy of the read out data goes down. To improve the accuracy of the data an Error Correcting Code ECC is added to the data and a write operation or a read operation is carried out. Previously when an ECC was stored pages or sets of bits into which a page was divided were used as ECC processing units hereinafter referred to as ECC units .

The relationship between the threshold levels in a memory cell which stores 4 level 8 level and 16 level data and data written into the memory cell is as follows. For example in a 4 level memory 4LC which stores 2 bits in a cell on the first page if the threshold level is lower than read level R Level 2 its data is 1 and if the threshold level is higher than read level 2 its data is 0. However on the second page if the threshold level is lower than read level 1 or higher than read level 3 its data is 1 and if the threshold level is higher than read level 1 and lower than read level 3 its data is 0. Accordingly the defect percentage of the second page is greater than that of the first page second page first page .

Furthermore in an 8 level memory 8LC which stores 3 bits in a cell the defect percentage of the third page is greater than that of the second page and the defect percentage of the second page is greater than that of the first page third page second page first page meaning that the defect percentage of the third page is much greater than that of the first page. Moreover in a 16 level memory 16LC which stores 4 bits in a cell the defect percentage of the fourth page is greater than that of the third page the defect percentage of the third page is greater than that of the second page and the defect percentage of the second page is greater than that of the first page fourth page third page second page first page meaning that the defect percentage of the fourth page is much greater than that of the first page.

Accordingly when a plurality of bits stored in a single cell are used as one ECC unit this increases the ECC efficiency. However the specifications of a conventional NAND flash memory are as follows data is input to or read from cells page by page starting with the beginning column address toward the end column address. Therefore writing or reading data into or from the memory cells in ECC units has been desired.

According to a first aspect of the invention there is provided a semiconductor memory device comprising a plurality of memory cells which store k bits of data k is a natural number not less than 2 into a single cell a number n n is a natural number not less than 2 of data storage circuits which store externally supplied k bits of data temporarily to write data into the memory cells and a control circuit which selects the k bits of data bit by bit as a first page a second page . . . a k th page and which when inputting first data externally inputs the data on the first page second page . . . the k th page to h h n of the data storage circuits when inputting second data externally inputs the data on the first page second page . . . the k th page to h h n of the data storage circuits and when inputting i th data externally inputs the data on the first page second page . . . the k th page to hi hi n of the data storage circuits and which stores data into the memory cells on the basis of the k bits of data stored in the n data storage circuits.

According to a second aspect of the invention there is provided a semiconductor memory device comprising a plurality of memory cells each of which stores k bits of data k is a natural number not less than 2 data storage circuits which temporarily store k bits of data read from the memory cells and a control circuit which in a read operation reads data from n of the memory cells simultaneously stores the data into n of the data storage circuits temporarily selects data bit by bit from the k bits as a first page a second page . . . a k th page and outputs data at the data storage circuits to the outside and which when outputting first data outputs the data on the first page second page . . . k th page at h h n of the data storage circuits to the outside when outputting second data outputs the data on the first page second page . . . k th page at h h n of the data storage circuits to the outside and when outputting i th data outputs the data on the first page second page . . . k th page at hi hi n of the data storage circuits to the outside.

According to a third aspect of the invention there is provided a semiconductor memory device comprising a number n n is a natural number not less than 2 of memory cells connected to the same word line m m n of the n memory cells constitute one ECC unit the n memory cells include a number i n m of ECC groups and in each of the i ECC groups memory cells having column addresses near one end of the word line and memory cells having column addresses near the other end of the word line exist uniformly.

According to a fourth aspect of the invention there is provided a semiconductor memory device comprising a first memory which stores k bits k is a natural number equal to 1 or more and a second memory cell which is adjacent to the first memory cell and into which dummy data is written when no data is written into the second memory cell.

A memory cell array includes a plurality of bit lines a plurality of word lines and a common source line. In the memory cell array electrically rewritable memory cells made up of for example EEPROM cells are arranged in a matrix. A bit line control circuit for controlling bit lines and a word line control circuit are connected to the memory cell array .

The bit line control circuit reads the data in a memory cell of the memory cell array via a bit line detects the state of a memory cell of the memory cell array via a bit line and writes data into a memory cell of the memory cell array by applying a write control voltage to the memory cell via a bit line. A column decoder and a data input output buffer are connected to the bit line control circuit . A data storage circuit in the bit line control circuit is selected by the column decoder . The data in the memory cell read into the data storage circuit is output via the data input output buffer at a data input output terminal to the outside. The data input output terminal is connected to for example a controller outside the memory chip. The controller which is composed of for example a microcomputer receives the data output from the data input output terminal . The controller outputs various commands CMD for controlling the operation of the NAND flash memory addresses ADD and data DT. The write data input to the data input output terminal from the controller is supplied via the data input output buffer to the data storage circuit selected by the column decoder . The commands and addresses are supplied to a control signal and control voltage generator circuit .

The controller has an ECC circuit . The ECC circuit is configured to correct the error and output the correct data if erroneous data is read from a memory cell. The ECC circuit may be provided not only in the controller but also in for example the NAND flash memory.

The word line control circuit is connected to the memory cell array . The word line control circuit selects a word line in the memory cell array and applies to the selected word line a voltage necessary for a read write or erase operation.

The memory cell array bit line control circuit column decoder data input output buffer and word line control circuit are connected to and controlled by the control signal and control voltage generator circuit . The control signal and control voltage generator circuit is connected to a control signal input terminal and is controlled by Address Latch Enable ALE Command Latch Enable CLE Write Enable WE and Read Enable RE control signals input from the controller via the control signal input terminal .

The bit line control circuit column decoder word line control circuit and control signal and control voltage generator circuit constitute a write circuit and a read circuit.

The bit line control circuit has a plurality of data storage circuits . Bit line pairs BL BL BL BL . . . BLie BLio . . . BL BL are connected to the individual data storage circuits in a one to one correspondence.

The memory cell array includes a plurality of blocks as shown by a broken line. Each block is composed of a plurality of NAND cells. In the memory cell array data is erased in for example blocks. An erase operation is performed simultaneously on the two bit lines connected to the data storage circuit .

A plurality of memory cells which are arranged on every other bit line and are connected to a single word line or the memory cells enclosed by a broken line constitute for example two pages. In the case of 8 levels a plurality of memory cells constitute three pages. In the case of 16 levels they constitute four pages. Data is written or read in pages.

In a read operation a program verify operation and a program operation one of the two bit lines BLie BLio connected to the data storage circuit is selected according to the address signals YA YA . . . YAi . . . YA externally supplied. Moreover according to an external address a single word line is selected.

Furthermore a single word line is selected according to an external address with the result that two pages enclosed by a dotted line in are selected. Switching between two pages is done by an address a first page a second page . When 2 bits are stored in one cell two pages are selected when 3 bits are stored in one cell a selection is made by a 3 page address a first page a second page a third page and when 4 bits are stored in one cell a selection is made by a 4 page address a first page a second page a third page a fourth page . An erase operation is carried out using a block unit shown by the dotted line in .

In the explanation below the first page second page third page and fourth page may also be referred to as the lower page upper page higher page and top page.

In the sense amplifier unit is composed of a plurality of n channel MOS transistors hereinafter referred to as NMOSs to a plurality of p channel MOS transistors hereinafter referred to as PMOSs and transfer gates a latch circuit composed of for example a clocked inverter circuit and a capacitor .

One end of the current path of NMOS is connected to a node to which a power supply Vdd is supplied. The other end of the current path is connected to the ground via the transfer gate NMOS and transfer gate . One end of the current path of NMOS is connected to the connection node of NMOS and transfer gate . The other end of NMOS is connected to a bit line BL arranged in the memory cell array. A series circuit of NMOS and NMOS is connected in parallel to NMOS .

One end of the current path of PMOS is connected to a node to which the power supply Vdd is supplied. The other end of the current path is connected not only to the input end of an inverter circuit constituting the latch circuit via PMOS but also to the ground via NMOS . The input end of a clocked inverter circuit cross coupled with the inverter circuit is connected to a data control unit DCU via NMOS . The gate of PMOS is connected to the connection node of NMOS and NMOS . One end of the capacitor is connected to the connection node. Clock signal CLK is supplied to the other end of the capacitor .

Signal BLK is supplied to the gate of NMOS . Signal LAT at the output end of the inverter circuit constituting the latch circuit is supplied to the gate of the NMOS constituting the transfer gate . Signal INV at the input end of the inverter circuit is supplied to the gate of the PMOS transistor. Signal BLC is supplied to the gate of NMOS and signal BLS is supplied to the gate of NMOS .

Signal STB is supplied to the gate of PMOS and reset signal RST is supplied to the gate of NMOS . Signal NCO is supplied to the gate of NMOS .

When data is written into a memory cell first signal STB is set at the high level hereinafter referred to as the level H and reset signal RST is set temporarily at the H level thereby resetting the latch circuit . Thus it follows that LAT H level and INV low level hereinafter referred to as the level L .

Thereafter when signal NCO is set to the level H level the data is taken in from the data control unit . If the data is the level L level 0 indicating writing it follows that LAT level L level and INV level H level. If the data is the level H level 1 indicating non writing the data in the latch circuit remain unchanged LAT level H level and INV level L level.

Next when signal BLX signal BLC and signal BLS are set to the level H level if the latch circuit is in the following state LAT level L level and INV level H level writing then the transfer gate goes off and the transfer gate goes on setting the bit line BL to Vss. In this state when a word line has reached a program voltage Vpgm data is written into the memory cell.

In the latch circuit when LAT level H and INV level L non writing the transfer gate is on and the transfer gate is off causing the bit line bL to be charged to Vdd. Therefore when the word line has reached Vpgm the channel of the cell is boosted to a higher potential preventing data from being written into the memory cell.

When the data is read from a memory cell first set signal RST is set to level H temporarily resetting the latch circuit . Thus it follows that LAT level H and INV level L. Thereafter signal BLS signal BLC signal BLX signal HLL and signal XXL are set to level H thereby charging the bit line BL. In parallel with this Node of the capacitor is charged to Vdd. Here if the threshold voltage of the memory cell is higher than the read level the memory cell is in the off state maintaining the bit line at the high level. That is Node remains at level H. If the threshold voltage of the memory cell is lower than the read level the memory cell goes into the on state causing the charge on the bit line to be discharged which brings the bit line BL into level L. Consequently Node goes into level L.

Next when signal STB is set to level L if the memory cell is on Node is at the high level turning PMOS on. Thus it follows that INV level H and LAT level L in the latch circuit . If the memory cell is off INV and LAT in the latch circuit remain unchanged as follows INV level L and LAT level H.

Thereafter when signal NCO is set to level H NMOS goes on causing the data in the latch circuit to be transferred to the data control unit

After the write operation a program verify operation to verify the threshold voltage of the memory cell is carried out almost in the same manner as the read operation.

The data control unit of is composed of an arithmetic circuit and a plurality of data latch circuits ADL BDL CDL DDL XDL NMOS and NMOS .

The arithmetic circuit is composed of a bus hereinafter referred to as IBUS transfer gates which are connected to both ends of the IBUS and operate complementarily a latch circuit which latches data on the IBUS and s setting circuit which sets the levels of the data latch circuits ADL BDL CDL DDL according to the data in the latch circuit .

The transfer gate which operates on the basis of complementary signals COND and CONS connects the bus of sense amplifier unit SAU referred to as SBUS and the IBUS. The transfer gate which operates on the basis of complementary signals CONS and COND connects the IBUS and the bus to which the data latch circuits ADL BDL CDL DDL XDL are connected hereinafter referred to as DBUS . If the transfer gate is on the transfer gate is off. If the transfer gate is off the transfer gate is on.

The latch circuit is composed of a plurality of PMOSs to and a plurality of NMOSs to . Set signal SET is supplied to the gates of PMOS and NMOS . Reset signal REST is supplied to the gate of PMOS . Signal IFH is supplied to the gate of NMOS and signal IFL is supplied to the gate of NMOS . The gates of NMOSs are connected to the IBUS.

The setting circuit is composed of PMOSs to and NMOS to . Signal FAIL at the connection node of PMOS and NMOS serving as one output end of the latch circuit is supplied to the gates of PMOS and NMOS . Signal MTC at the connection node of PMOS and NMOS serving as the other output end of the latch circuit is supplied to the gates of PMOS and NMOS . Moreover signal MHB is supplied to the gate of PMOS . Signal FHB is supplied to the gate of PMOS . Signal FL is supplied to the gate of NMOS . Signal ML is supplied to the gate of NMOS .

Each of data latch circuits ADL BDL CDL DDL and XDL which have the same configuration is composed of a latch circuit and a transfer gate that connects the latch circuit to the DBUS. The individual transfer gates are controlled by signal BLCQ signal BLCA signal BLCB signal BLCC and signal BLCD respectively. A data latch circuit XDL is connected via NMOS to an external IO. Signal CSL is supplied to the gate of NMOS . NMOS is connected between the data latch circuits DDL and XDL. A signal XSW is supplied to the gate of the NMOS . When at least one of data latch circuits is unused for program operation the data latch circuit is used as a cache of following write data. At this time since the data from the outside is asynchronously inputted the NMOS is turned off according to the signal XSW. Therefore the data latch circuit XDL is separated from the data latch circuits ADL to DDL and can receive data asynchronously supplied from the outside to sequence of the program operation.

As described above the data control unit not only holds write data but also holds the data read from a memory cell in a read operation.

The 4 bit write data supplied from the data input output buffer is latched in the data latch circuits ADL BDL CDL and DDL via the data latch circuit XDL in such a manner that each of the data latch circuits holds one bit.

The arithmetic circuit of can perform AND or OR operations on the data in the data latch circuits ADL BDL CDL and DDL. When the data as shown in are input to the data latch circuits ADL BDL CDL and DDL the AND of them gives 1 only in a non writing operation. If the data is in the range of level 1 to level F the output is 0. The resulting data is transferred to the sense amplifier unit of thereby performing writing.

After a verify read operation if the cell has reached the threshold level level H is set in the LAT of the latch circuit of the sense amplifier unit of . If the cell has not reached the threshold level level L is set in the LAT. When the data is verified at level 3 since ADL 1 BDL 0 CDL 1 and DDL 1 the data in ADL the inversion of the data in BDL the data in CDL and the data in DDC are ANDed. Then data 1 remains in the arithmetic circuit only when data has been written to level 3. Thereafter this result and the data in the LAT of the latch circuit are ANDed. Then the result of the arithmetic circuit goes to level H only when the threshold level has been reached at level 3 otherwise it goes to level L. Here the data in the ADL BDL CDL and DDL are set to 1 only when the arithmetic circuit is at the H level. As a result the ADL BDL CDL and DDL hold non writing data.

When reading is done as shown in the data read from the memory cell at the individual levels are saved temporarily in the ADL BDL CDL and DDL. The arithmetic circuit performs arithmetic operations on these data items and the data in the LAT of the latch circuit of the sense amplifier and transfers the operation result to the ADL BDL CDL and DDL. Since the operation of the arithmetic circuit is not an essential part of the embodiment a detailed description of the operation will be omitted for convenience of explanation.

Here an explanation will be given about a case where for example 16 levels are set in a single cell as shown in with the page length being 4 kB and the ECC unit being 2 kB.

First the controller prepares 2 kB of data similar to the ECC unit shown by A in . Using this unit data is transferred to the NAND flash memory while calculating ECC.

First on the basis of a data input command and a lower page address Add L the data in columns to on the first page are supplied to the data latch circuit XDL of . Next on the basis of a transfer command Ah the data in the data latch circuit XDL is transferred to the data latch circuit ADL.

Thereafter on the basis of a data input command and an upper page address Add U the data in columns to on the second page are supplied to the data latch circuit XDL. Next on the basis of a transfer command Ah the data in the data latch circuit XDL is transferred to the data latch circuit BDL.

Thereafter on the basis of a data input command and a higher page address Add H the data in columns to on the third page are supplied to the data latch circuit XDL. Next on the basis of a transfer command Ah the data in the data latch circuit XDL is transferred to the data latch circuit CDL.

Thereafter on the basis of a data input command and a top page address Add T the data in columns to on the fourth page are supplied to the data latch circuit XDL. Next on the basis of a transfer command Ah the data in the data latch circuit XDL is transferred to the data latch circuit DDL.

When the data on the first to fourth pages are stored into the data latch circuit XDL since 2 kB of data have been prepared as an ECC unit the controller also performs arithmetic operations on parity bits.

Next the controller prepares 2 kB of data as an ECC unit shown by B in . The controller transfers data to the NAND flash memory while calculating ECC in ECC units.

Then on the basis of a command AAh the data on the first page held in the data latch circuit ADL is returned to the data latch circuit XDL. Thereafter on the basis of a command and a lower page address Add L the data in columns to on the first page are supplied to the data latch circuit XDL. Next on the basis of a transfer command Ah the data in the data latch circuit XDL is transferred to the data latch circuit ADL.

Then on the basis of a command ABh the data on the second page held in the data latch circuit BDL is returned to the data latch circuit XDL. Thereafter on the basis of a command and an upper page address Add U the data in columns to on the second page are supplied to the data latch circuit XDL. Next on the basis of a transfer command Ah the data in the data latch circuit XDL is transferred to the data latch circuit BDL.

Then on the basis of a command ACh the data on the third page held in the data latch circuit CDL is returned to the data latch circuit XDL. Thereafter on the basis of a command and a higher page address Add H the data in columns to on the third page are supplied to the data latch circuit XDL. Next on the basis of a transfer command Ah the data in the data latch circuit XDL is transferred to the data latch circuit CDL.

Then on the basis of a command ADh the data on the fourth page held in the data latch circuit DDL is returned to the data latch circuit XDL. Thereafter on the basis of a command and a top page address Add T the data in columns to on the fourth page are supplied to the data latch circuit XDL. Next on the basis of a transfer command Ah the data in the data latch circuit XDL is transferred to the data latch circuit DDL.

At this time since 2 kB of data have been prepared as an ECC unit the controller also performs arithmetic operations on parity bits.

Next the controller prepares 2 kB of data as an ECC unit shown by C in . The controller transfers data to the NAND flash memory while calculating ECC in ECC units.

Then on the basis of a command AAh the data on the first page held in the data latch circuit ADL is returned to the data latch circuit XDL. Thereafter on the basis of a command and a lower page address Add L the data in columns to on the first page are supplied to the data latch circuit XDL. Next on the basis of a transfer command Ah the data in the data latch circuit XDL is transferred to the data latch circuit ADL.

Similarly the data in columns to on the first second third and fourth pages shown in are transferred to the data latch circuits ADL BDL CDL and DDL sequentially.

In the state where all the data on the first to fourth pages have been stored in the data latch circuits ADL BDL CDL and DDL in this way a write command is supplied. Then on the data on the first second third and fourth pages 4 bits of data are written into one cell simultaneously.

Since the program operation and the verify operation are not an essential part of the embodiment a detailed description of them will be omitted for convenience of explanation. In addition the program and verify operations are not limited to the aforementioned method and may be modified or embodied suitably.

When the program and verify operations have been completed in this way a threshold level is set in each memory cell according to the input data.

On the selected word line and unselected word lines the level is raised from the low level to high level progressively as shown in thereby carrying out a read operation at each level.

In a read operation when a read command is supplied a Busy signal is output outside the chip and at the same time 4 bit data stored in one cell is read. A read operation is carried out in this order the first page second page third page and fourth page the lower page upper page higher page and top page .

In a read operation reading is performed beginning with the low level upward and the data is transferred to the ADL to DDL. When reading has been done up to level 8 the data on the first page is determined and therefore the data stored in the ADL is copied into the XDL. Then the signal supplied to the controller is changed from the busy state to the ready state the controller supplies a read signal RE to the NAND flash memory. This causes the data in columns to on the first page to be output from the data latch circuit XDL to the outside.

Next when the controller supplies a transfer command to the NAND flash memory the NAND flash memory outputs a busy signal to the controller . Here if the data on the second page has been read into the data latch BDL the data in the data latch circuit BDL is copied into the data latch circuit XDL. If the data on the second page has not been read into the data latch circuit BDL the controller waits for the data on the second page to be read into the data latch circuit BDL. Thereafter if the busy signal is switched to a ready signal the controller supplies a read signal RE to the NAND flash memory. This causes the data in column to on the second page to be output from the data latch circuit XDL to the outside.

Next when the controller has supplied a transfer command to the NAND flash memory the NAND flash memory outputs a busy signal to the controller . Here if the data on the third page has been written in the data latch CDL the data in the data latch circuit CDL is copied into data latch circuit XDL. If the data on the third page has not been read into the data latch circuit CDL the controller waists for the data on the third page to be read into the data latch circuit CDL. Thereafter if the busy signal is changed to a ready signal the controller supplies a read signal RE to the NAND flash memory. This causes the data in columns to on the third page to be output from the data latch circuit XDL to the outside.

Next when the controller has supplied a transfer command to the NAND flash memory the NAND flash memory outputs a busy signal to the controller . Here if the data on the fourth page has been read in the data latch circuit DDL the data in the data latch circuit DDL is copied into the data latch circuit XDL. If the data on the fourth page has not been read into the data latch circuit DDL the controller waits for the data on the fourth page to be read into the data latch circuit DDL. Thereafter when the busy signal is switched to a ready signal the controller supplies a read signal RE to the NAND flash memory. As a result when the data in columns to on the fourth page are output from the data latch circuit XDL to the outside since 2 kB of data are prepared as an ECC unit the controller can carry out an ECC correction process.

Next when the controller has supplied a transfer command to the NAND flash memory the NAND flash memory outputs a busy signal to the controller . At the same time the data in the data latch circuit ADL is copied into the data latch circuit XDL. Thereafter when the busy signal is switched to a ready signal the controller supplies a read signal RE to the NAND flash memory. As a result the data in columns to on the first page are output from the data latch circuit XDL to the outside.

Next when the controller has supplied a transfer command to the NAND flash memory the NAND flash memory outputs a busy signal to the controller . At the same time the data in the data latch circuit BDL is copied into the data latch circuit XDL. Thereafter when the busy signal is switched to a ready signal the controller supplies a read signal RE to the NAND flash memory. As a result the data in columns to on the second page are output from the data latch circuit XDL to the outside.

Next when the controller has supplied a transfer command to the NAND flash memory the NAND flash memory outputs a busy signal to the controller . At the same time the data in the data latch circuit CDL is copied into the data latch circuit XDL. Thereafter when the busy signal is switched to a ready signal the controller supplies a read signal RE to the NAND flash memory. As a result the data in columns to on the third page are output from the data latch circuit XDL to the outside.

Next when the controller has supplied a transfer command to the NAND flash memory the NAND flash memory outputs a busy signal to the controller . At the same time the data in the data latch circuit DDL is copied into the data latch circuit XDL. Thereafter when the busy signal is switched to a ready signal the controller supplies a read signal RE to the NAND flash memory. As a result the data in columns to on the fourth page are output from the data latch circuit XDL to the outside. At this time since 2 kB of data are prepared as an ECC unit the controller can carry out an ECC correction process.

Next when the controller has supplied a transfer command to the NAND flash memory the NAND flash memory outputs a busy signal to the controller . At the same time the data in the data latch circuit ADL is copied into the data latch circuit XDL. Thereafter when the busy signal is switched to a ready signal the controller supplies a read signal RE to the NAND flash memory. As a result the data in columns to on the first page are output from the data latch circuit XDL to the outside.

Similarly the data in columns to on the fourth page are output from the data latch circuit XDL to the outside. At this time since 2 kB of data are prepared as an ECC unit the controller can carry out an ECC correction process.

In a memory which stores a plurality of bits in a cell when a plurality of bits to be stored in a cell are stored on the first second third and fourth pages the defect percentage differs from page to page. Therefore when the data on the first second third and fourth pages are treated as one ECC the ECC efficiency increases. However this makes the ECC unit very large.

To overcome this problem the first embodiment makes it possible to read and write data repeatedly by switching between the data on the first second third and fourth pages many times. This makes it possible to use an ECC unit including the first second third and fourth pages without making the ECC unit very large and therefore improve the ECC correction efficiency.

While in the first embodiment 16 levels have been stored in a single cell the same holds true when 4 levels 8 levels or more levels are stored in a single cell. To store 4 levels into a single cell only a first and a second page are needed. To store 8 levels into a single cell a first a second and a third page are required.

In the first embodiment page addresses and ECC units have been set as shown in . In a program operation a write operation is carried out by applying a high voltage VPGM to the control gate or selected word line of the selected memory cell as shown in .

Since the resistance and capacitance of the word line are high the voltage rising and falling characteristics of the word line differ according to the distance from the driving circuit of the word line. In a characteristic WLf shown by a dotted line is a characteristic of a word line in a part far away from the driving circuit of the word line and a characteristic WLn shown by a solid line is a characteristic of a word line in a part close to the driving circuit. Since the potential of the word line differs between the part close to the driving circuit and the part far away from the diving circuit the defect percentage of the memory cell connected to the word line differs. That is as the memory cell is closer to the driving circuit the defect percentage of the memory cell may be higher due to program disturbance.

In this case the setting of the relationship between page addresses and ECC units as shown in can be considered. In A and B to G show the relationship between page addresses and ECC units in the case of 4 levels. In A and B to G show the relationship between page addresses and ECC units in the case of 16 levels. According to the column addresses shown in the controller inputs and outputs 512 kB of data in units of 64 kB to and from the NAND flash memory.

Since the ECC circuit does calculations in ECC units of for example 1 kB or 2 kB it inputs and outputs data to and from the NAND flash memory discretely which makes it difficult to realize the configuration of each of .

To overcome this problem the physical locations of the column addresses in the NAND flash memory are configured as shown in and in the second embodiment.

In the case of 16 levels shown in the data on the first second third and fourth page are input according to the column addresses shown in .

While in column addresses have been scrambled bit by bit they may be scrambled at intervals of a plurality of bits.

Specifically in an example shown in column addresses are scrambled at intervals of 8 consecutive bits and at intervals of 8 column addresses. For example the data on the first and second pages are supplied to 8 column addresses A to . Then the data on the first and second pages are supplied to 8 column addresses A to 64 column addresses away from the column addresses to . Similarly 8 column addresses are allocated at intervals of 64 column addresses.

In an example shown in the data on the first second third and fourth pages are supplied in the same column address allocation as in .

The column address allocation shown in is applied to a case where data is written and read. The column address allocation is executed by the column decoder shown in for example . That is a column is selected according to the column address allocation shown in each of .

With the second embodiment column addresses are allocated at intervals of one or more column addresses. Accordingly even if column addresses are input or output consecutively to or from a NAND flash memory the data stored in the memory cells are dispersed in the column direction. Consequently even if the defect percentage differs between the part close to the driving circuit of the word line and the part far away from the driving circuit the defect percentage of all the ECC units can be made uniform.

While in the second embodiment 4 levels or 16 levels have been stored in a single cell the second embodiment may be applied to a memory cell capable of storing 8 or more levels.

Here if the next adjacent cell is written into the threshold level rises slightly. If the next adjacent cell is not written into the threshold level does not rise. Accordingly when the adjacent cell is not written into the data retention margin becomes smaller then when the adjacent cell has been written into. Therefore in the block when the next page is not written into dummy data is written thereby raising the threshold level through the coupling between floating gates to secure a data retention margin. From the viewpoint of data retention it is desirable that data which enables the threshold level of the highest threshold distribution to rise should be used as the dummy data. If the threshold level rises so much that a margin of the space from the next level decreases random data is desirable.

Furthermore with the configuration of each of data is written into cells in a block starting with the cell connected to word line WL in this order the cell connected to word line WL the cell connected to word line WL . . . the cell connected to word line WL. Therefore a cell adjacent to the cell connected to the last word line WL is not written into. Accordingly when the threshold level hasn t risen and the data retention margin has become smaller the verify level in writing data into the cell connected to the last word line WL in the block is raised slightly in advance.

With the third embodiment when an adjacent cell is not written into dummy data is written thereby raising the threshold level. This makes it possible to make the data retention margin larger. Accordingly the reading accuracy can be improved and a rise in the defect percentage can be prevented.

While in the third embodiment four levels have been stored in a single cell the third embodiment may be applied to a memory cell capable of storing 8 16 or more levels.

The controller has an interface I F an interface a microprocessor MPU RAM serving as a buffer and an error correction part ECC . The interface contains an NAND type flash memory which receives a signal from an external device not shown and outputs a signal to an external device not shown . The interface transmits data to and receives data from the semiconductor memory device . The microprocessor performs calculation required for converting a logic address inputted from external device to a physical address. The RAM stores data temporarily. The error correction part generates an error correction code. Moreover a command signal line CMD a clock signal line CLK and a signal line DAT are connected to the interface of the memory card .

In the aforementioned memory card the number of signal lines the bit width of the signal lines and the configuration of the controller may be changed in accordance with the need.

Additional advantages and modifications will readily occur to those skilled in the art. Therefore the invention in its broader aspects is not limited to the specific details and representative embodiments shown and described herein. Accordingly various modifications may be made without departing from the spirit or scope of the general inventive concept as defined by the appended claims and their equivalents.

