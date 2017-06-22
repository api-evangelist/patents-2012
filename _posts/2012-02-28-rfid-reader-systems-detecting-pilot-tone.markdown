---

title: RFID reader systems detecting pilot tone
abstract: RFID tags are commanded to generate a pilot tone in their backscatter. When the backscattered pilot tone is received in the reader, the pilot tone is used to estimate the tag period/frequency. Then, the estimate is used to seed and lock a symbol timing recovery loop, which provides a detected signal to one or more correlators for detecting the tag preamble. A delayed version of the received tag signal is compared against a baseline signal threshold established from the received signal to detect the pilot tone.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08350665&OS=08350665&RS=08350665
owner: Impinj, Inc.
number: 08350665
owner_city: Seattle
owner_country: US
publication_date: 20120228
---
This utility patent application is a continuation of U.S. patent application Ser. No. 11 622 092 IMPJ 0179 filed on Jan. 11 2007. The benefit of the earlier filing date of the parent applications is hereby claimed under 35 U.S.C. 120. The parent application is incorporated herein by reference.

This utility patent application claims the benefit of U.S. Provisional Application Ser. No. 60 760 150 filed on Jan. 18 2006 which is hereby claimed under 35 U.S.C. 119 e . The provisional application is incorporated herein by reference.

This utility patent application is a continuation in part CIP of U.S. patent application Ser. No. 11 136 948 IMPJ 0098 filed on Aug. 19 2004. The benefit of the earlier filing date of the parent applications is hereby claimed under 35 U.S.C. 120. The parent application is incorporated herein by reference.

This application may be found to be related to the following application which is incorporated herein by reference Application titled RFID READER SYSTEMS AIDED BY RF POWER MEASUREMENT by inventors Scott A. Cooper and Christopher J. Diorio filed with the USPTO on the same day as the present application and due to be assigned to the same assignee Ser. No. 11 622 066 .

This application may also be found to be related to the following application which is incorporated herein by reference Application titled RFID READER SYSTEMS WITH DIGITAL RATE CONVERSION by inventor Kurt E. Sundstrom filed with the USPTO on the same day as the present application and due to be assigned to the same assignee Ser. No. 11 622 140 .

Radio Frequency IDentification RFID systems typically include RFID tags and RFID readers the latter are also known as RFID reader writers or RFID interrogators . RFID systems can be used in many ways for locating and identifying objects to which the tags are attached. RFID systems are particularly useful in product related and service related industries for tracking large numbers of objects being processed inventoried or handled. In such cases an RFID tag is usually attached to an individual item or to its package.

In principle RFID techniques entail using an RFID reader to interrogate one or more RFID tags. The reader transmitting a Radio Frequency RF wave performs the interrogation. A tag that senses the interrogating RF wave responds by transmitting back another RF wave. The tag generates the transmitted back RF wave either originally or by reflecting back a portion of the interrogating RF wave in a process known as backscatter. Backscatter may take place in a number of ways.

The reflected back RF wave may further encode data stored internally in the tag such as a number. The response is demodulated and decoded by the reader which thereby identifies counts or otherwise interacts with the associated item. The decoded data can denote a serial number a price a date a destination other attribute s any combination of attributes and so on.

An RFID tag typically includes an antenna system a power management section a radio section and frequently a logical section a memory or both. In earlier RFID tags the power management section included an energy storage device such as a battery. RFID tags with an energy storage device are known as active tags. Advances in semiconductor technology have miniaturized the electronics so much that an RFID tag can be powered solely by the RF signal it receives. Such RFID tags do not include an energy storage device and are called passive tags.

In a typical reader tag communication the reader and the tag clocks are not synchronous in frequency or phase. Therefore the reader has to recover the timing information from the received tag signal. To accomplish that the reader needs to estimate and track symbol rate frequency and symbol phase temporal boundaries .

There is a wide variance of when tag responses can be received for detection. Moreover the tag and reader clocks are not synchronized for their period and or phase. The response is due after many cycles of these clocks. So even small discrepancies in their synchronization may accumulate resulting in potentially large variances of time and frequency. Therefore not only are the tag and reader clocks not synchronized in an RFID communication but the frequency errors may be much larger than in traditional wireless communications systems.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used as an aid in determining the scope of the claimed subject matter.

Embodiments are directed to commanding an RFID tag to generate a pilot tone in its backscatter. When the backscattered pilot tone is received in the reader the pilot tone may be used to estimate the tag period frequency. Then the estimate may be used to seed and lock a symbol timing recovery loop which provides a detected signal to a correlator for detecting the tag preamble. According to some embodiments a delayed version of the received tag signal may be compared against a baseline signal threshold established from the received signal and detection of the pilot tone determined based on the comparison.

This and other features and advantages of the invention will be better understood in view of the Detailed Description and the Drawings in which 

Various embodiments will be described in detail with reference to the drawings where like reference numerals represent like parts and assemblies throughout the several views. Reference to various embodiments does not limit the scope of the invention which is limited only by the scope of the claims attached hereto. Additionally any examples set forth in this specification are not intended to be limiting and merely set forth some of the many possible embodiments for the claimed subject matter.

Throughout the specification and claims the following terms take at least the meanings explicitly associated herein unless the context clearly dictates otherwise. The meanings identified below are not intended to limit the terms but merely provide illustrative examples for the terms. The meaning of a an and the includes plural reference the meaning of in includes in and on. The term connected means a direct electrical connection between the items connected without any intermediate devices. The term coupled means either a direct electrical connection between the items connected or an indirect connection through one or more passive or active intermediary devices. The term circuit means either a single component or a multiplicity of components either active and or passive that are coupled together to provide a desired function. The term signal means at least one current voltage charge temperature data or other measurable quantity. The terms RFID reader and RFID tag are used interchangeably with the terms reader and tag respectively throughout the text and claims.

Reader and tag exchange data via wave and wave . In a session of such an exchange each encodes modulates and transmits data to the other and each receives demodulates and decodes data from the other. The data is modulated onto and decoded from RF waveforms.

Encoding the data in waveforms can be performed in a number of different ways. For example protocols are devised to communicate in terms of symbols also called RFID symbols. A symbol for communicating can be a delimiter a calibration symbol and so on. Further symbols can be implemented for ultimately exchanging binary data such as 0 and 1 if that is desired. In turn when the waveforms are processed internally by reader and tag they can be equivalently considered and treated as numbers having corresponding values and so on.

Tag can be a passive tag or an active tag i.e. having its own power source. Where tag is a passive tag it is powered from wave .

Tag is formed on a substantially planar inlay which can be made in many ways known in the art. Tag includes an electrical circuit which is preferably implemented in an integrated circuit IC . IC is arranged on inlay .

Tag also includes an antenna for exchanging wireless signals with its environment. The antenna is usually flat and attached to inlay . IC is electrically coupled to the antenna via suitable antenna ports not shown in .

The antenna may be made in a number of ways as is well known in the art. In the example of the antenna is made from two distinct antenna segments which are shown here forming a dipole. Many other embodiments are possible using any number of antenna segments.

In some embodiments an antenna can be made with even a single segment. Different places of the segment can be coupled to one or more of the antenna ports of IC . For example the antenna can form a single loop with its ends coupled to the ports. When the single segment has more complex shapes it should be remembered that at the frequencies of RFID wireless communication even a single segment could behave like multiple segments.

In operation a signal is received by the antenna and communicated to IC . IC both harvests power and responds if appropriate based on the incoming signal and its internal state. In order to respond by replying IC modulates the reflectance of the antenna which generates the backscatter from a wave transmitted by the reader. Coupling together and uncoupling the antenna ports of IC can modulate the reflectance as can a variety of other means.

In the embodiment of antenna segments are separate from IC . In other embodiments antenna segments may alternately be formed on IC and so on.

The components of the RFID system of may communicate with each other in any number of modes. One such mode is called full duplex. Another such mode is called half duplex and is described below.

RFID reader and RFID tag talk and listen to each other by taking turns. As seen on axis TIME when reader talks to tag the communication session is designated as R T and when tag talks to reader the communication session is designated as T R . Along the TIME axis a sample R T communication session occurs during a time interval and a following sample T R communication session occurs during a time interval . Of course interval is typically of a different duration than interval here the durations are shown approximately equal only for purposes of illustration.

According to blocks and RFID reader talks during interval and listens during interval . According to blocks and RFID tag listens while reader talks during interval and talks while reader listens during interval .

In terms of actual technical behavior during interval reader talks to tag as follows. According to block reader transmits wave which was first described in . At the same time according to block tag receives wave and processes it to extract data and so on. Meanwhile according to block tag does not backscatter with its antenna and according to block reader has no wave to receive from tag .

During interval tag talks to reader as follows. According to block reader transmits a Continuous Wave CW which can be thought of as a carrier signal that ideally encodes no information. As discussed before this carrier signal serves both to be harvested by tag for its own internal power needs and also as a wave that tag can backscatter. Indeed during interval according to block tag does not receive a signal for processing. Instead according to block tag modulates the CW emitted according to block so as to generate backscatter wave . Concurrently according to block reader receives backscatter wave and processes it.

In the above an RFID reader interrogator may communicate with one or more RFID tags in any number of ways. Some such ways are called protocols. A protocol is a specification that calls for specific manners of signaling between the reader and the tags.

One such protocol is called the Specification for RFID Air Interface EPC Radio Frequency Identity Protocols Class 1 Generation 2 UHF RFID Protocol for Communications at 860 MHz 960 MHz which is also colloquially known as the Gen2 Spec . The Gen2 Spec has been ratified by EPCglobal which is an organization that maintains a website at at the time this document is initially filed with the USPTO.

It was described above how reader and tag communicate in terms of time. In addition communications between reader and tag may be restricted according to frequency. One such restriction is that the available frequency spectrum may be partitioned into divisions that are called channels. Different partitioning manners may be specified by different regulatory jurisdictions and authorities e.g. FCC in North America CEPT in Europe etc. .

The reader typically transmits with a transmission spectrum that lies within one channel. In some regulatory jurisdictions the authorities permit aggregating multiple channels into one or more larger channels but for all practical purposes an aggregate channel can again be considered a single albeit larger individual channel.

Tag can respond with a backscatter that is modulated directly onto the frequency of the reader s emitted CW also called baseband backscatter. Alternatively Tag can respond with a backscatter that is modulated onto a frequency developed by Tag that is different from the reader s emitted CW and this modulated tag frequency is then impressed upon the reader s emitted CW. This second type of backscatter is called subcarrier backscatter. The subcarrier frequency can be within the reader s channel can straddle the boundaries with the adjacent channel or can be wholly outside the reader s channel.

A number of jurisdictions require a reader to hop to a new channel on a regular basis. When a reader hops to a new channel it may encounter RF energy there that could interfere with communications.

Embodiments of the present disclosure can be useful in different RFID environments for example in the deployment of RFID readers in sparse or dense reader environments in environments with networked and disconnected readers such as where a hand held reader may enter the field of networked readers in environments with mobile readers or in environments with other interference sources. It will be understood that the present embodiments are not limited to operation in the above environments but may provide improved operation in such environments.

Local block is responsible for communicating with the tags. Local block includes a block of an antenna and a driver of the antenna for communicating with the tags. Some readers like that shown in local block contain a single antenna and driver. Some readers contain multiple antennas and drivers and a method to switch signals among them including sometimes using different antennas for transmitting and for receiving. And some readers contain multiple antennas and drivers that can operate simultaneously. A demodulator decoder block demodulates and decodes backscattered waves received from the tags via antenna block . Modulator encoder block encodes and modulates an RF wave that is to be transmitted to the tags via antenna block .

Local block additionally includes an optional local processor . Processor may be implemented in any number of ways known in the art. Such ways include by way of examples and not of limitation digital and or analog processors such as microprocessors and digital signal processors DSPs controllers such as microcontrollers software running in a machine such as a general purpose computer programmable circuits such as Field Programmable Gate Arrays FPGAs Field Programmable Analog Arrays FPAAs Programmable Logic Devices PLDs Application Specific Integrated Circuits ASIC any combination of one or more of these and so on. In some cases some or all of the decoding function in block the encoding function in block or both may be performed instead by processor .

Local block additionally includes an optional local memory . Memory may be implemented in any number of ways known in the art. Such ways include by way of examples and not of limitation nonvolatile memories NVM read only memories ROM random access memories RAM any combination of one or more of these and so on. Memory if provided can include programs for processor to run if provided.

In some embodiments memory stores data read from tags or data to be written to tags such as Electronic Product Codes EPCs Tag Identifiers TIDs and other data. Memory can also include reference data that is to be compared to the EPC codes instructions and or rules for how to encode commands for the tags modes for controlling antenna and so on. In some of these embodiments local memory is provided as a database.

Some components of local block typically treat the data as analog such as the antenna driver block . Other components such as memory typically treat the data as digital. At some point there is a conversion between analog and digital. Based on where this conversion occurs a whole reader may be characterized as analog or digital but most readers contain a mix of analog and digital functionality.

If remote components are indeed provided they are coupled to local block via an electronic communications network . Network can be a Local Area Network LAN a Metropolitan Area Network MAN a Wide Area Network WAN a network of networks such as the internet and so on. In turn local block then includes a local network connection for communicating with network .

There can be one or more remote component s . If more than one they can be located at the same place with each other or in different places. They can access each other and local block via network or via other similar networks and so on. Accordingly remote component s can use respective remote network connections. Only one such remote network connection is shown which is similar to local network connection etc.

Remote component s can also include a remote processor . Processor can be made in any way known in the art such as was described with reference to local processor .

Remote component s can also include a remote memory . Memory can be made in any way known in the art such as was described with reference to local memory . Memory may include a local database and a different database of a Standards Organization such as one that can reference EPCs.

Of the above described elements it is advantageous to consider a combination of these components designated as operational processing block . Block includes those that are provided of the following local processor remote processor local network connection remote network connection and by extension an applicable portion of network that links connection with connection . The portion can be dynamically changeable etc. In addition block can receive and decode RF waves received via antenna and cause antenna to transmit RF waves according to what it has processed.

Block includes either local processor or remote processor or both. If both are provided remote processor can be made such that it operates in a way complementary with that of local processor . In fact the two can cooperate. It will be appreciated that block as defined this way is in communication with both local memory and remote memory if both are present.

Accordingly block is location agnostic in that its functions can be implemented either by local processor or by remote processor or by a combination of both. Some of these functions are preferably implemented by local processor and some by remote processor . Block accesses local memory or remote memory or both for storing and or retrieving data.

Reader system operates by block generating communications for RFID tags. These communications are ultimately transmitted by antenna block with modulator encoder block encoding and modulating the information on an RF wave. Then data is received from the tags via antenna block demodulated and decoded by demodulator decoder block and processed by processing block .

The invention additionally includes programs and methods of operation of the programs. A program is generally defined as a group of steps or operations leading to a desired result due to the nature of the elements in the steps and their sequence. A program is usually advantageously implemented as a sequence of steps or operations for a processor such as the structures described above.

Performing the steps instructions or operations of a program requires manipulation of physical quantities. Usually though not necessarily these quantities may be transferred combined compared and otherwise manipulated or processed according to the steps or instructions and they may also be stored in a computer readable medium. These quantities include for example electrical magnetic and electromagnetic charges or particles states of matter and in the more general case can include the states of any physical devices or elements. It is convenient at times principally for reasons of common usage to refer to information represented by the states of these quantities as bits data bits samples values symbols characters terms numbers or the like. It should be borne in mind however that all of these and similar terms are associated with the appropriate physical quantities and that these terms are merely convenient labels applied to these physical quantities individually or in groups.

The invention furthermore includes storage media. Such media individually or in combination with others have stored thereon instructions of a program made according to the invention. A storage medium according to the invention is a computer readable medium such as a memory and is read by a processor of the type mentioned above. If a memory it can be implemented in a number of ways such as Read Only Memory ROM Random Access Memory RAM etc. some of which are volatile and some non volatile.

Even though it is said that the program may be stored in a computer readable medium it should be clear to a person skilled in the art that it need not be a single memory or even a single machine. Various portions modules or features of it may reside in separate memories or even separate machines. The separate machines may be connected directly or through a network such as a local access network LAN or a global network such as the Internet.

Often for the sake of convenience only it is desirable to implement and describe a program as software. The software can be unitary or thought in terms of various interconnected distinct software modules.

This detailed description is presented largely in terms of flowcharts algorithms and symbolic representations of operations on data bits on and or within at least one medium that allows computational operations such as a computer with memory. Indeed such descriptions and representations are the type of convenient labels used by those skilled in programming and or the data processing arts to effectively convey the substance of their work to others skilled in the art. A person skilled in the art of programming may use these descriptions to readily generate specific instructions for implementing a program according to the present invention.

Embodiments of an RFID reader system can be implemented as a combination of hardware and software. It is advantageous to consider such a system as subdivided into components or modules. A person skilled in the art will recognize that some of these components or modules can be implemented as hardware some as software some as firmware and some as a combination. An example of such a subdivision is now described.

RFID reader system includes one or more antennas and an RF Front End for interfacing with antenna s . These can be made as described above. In addition Front End typically includes analog components.

System also includes a Signal Processing module . In this embodiment module exchanges waveforms with Front End such as I and Q waveform pairs. In some embodiments signal processing module is implemented by itself in an FPGA.

System also includes a Physical Driver module which is also known as Data Link. In this embodiment module exchanges bits with module . Data Link can be the stage associated with framing of data. In one embodiment module is implemented by a Digital Signal Processor.

System additionally includes a Media Access Control module which is also known as MAC layer. In this embodiment module exchanges packets of bits with module . MAC layer can be the stage for making decisions for sharing the medium of wireless communication which in this case is the air interface. Sharing can be between reader system and tags or between system with another reader or between tags or a combination. In one embodiment module is implemented by a Digital Signal Processor.

System moreover includes an Application Programming Interface module which is also known as API Modem API and MAPI. In some embodiments module is itself an interface for a user.

System further includes a host processor . Processor exchanges signals with MAC layer via module . In some embodiments host processor is not considered as a separate module but one that includes some of the above mentioned modules of system . A user interface is coupled to processor and it can be manual automatic or both.

Host processor can include applications for system . In some embodiments elements of module may be distributed between processor and MAC layer . It will be observed that the modules of system form something of a chain. Adjacent modules in the chain can be coupled by the appropriate instrumentalities for exchanging signals. These instrumentalities include conductors buses interfaces and so on. These instrumentalities can be local e.g. to connect modules that are physically close to each other or over a network for remote communication.

The chain is used in opposite directions for receiving and transmitting. In a receiving mode wireless waves are received by antenna s as signals which are in turn processed successively by the various modules in the chain. Processing can terminate in any one of the modules. In a transmitting mode initiation can be in any one of these modules. That which is to be transmitted becomes ultimately signals for antenna s to transmit as wireless waves.

The architecture of system is presented for purposes of explanation and not of limitation. Its particular subdivision into modules need not be followed for creating embodiments according to the invention. Furthermore the features of the invention can be performed either within a single one of the modules or by a combination of them.

An economy is achieved in the present document in that a single set of flowcharts is used to describe methods in and of themselves along with operations of hardware and or software. This is regardless of how each element is implemented.

Receiver may be a direct down conversion receiver that directly converts a received tag response signal to a baseband signal without an intermediate step of converting to an IF signal. In some embodiments receiver may be a zero IF receiver. In other embodiments receiver may be a low IF receiver in which an IF signal close to zero frequency is generated. Receiver comprises antenna mixers and to convert the tag response signal directly to baseband phase converter to provide 0 deg and 90 deg phases of a local oscillator signal from the local oscillator to the mixers and demodulator .

In some embodiments receiver may also include one or more filters to filter undesirable mixing products and interfering signals as well as to reduce baseband distortion and noise. Antenna may comprise a directional or omnidirectional antenna including for example a dipole antenna a monopole antenna a loop antenna a microstrip antenna or other type of antenna suitable for reception and or transmission of RF signals which may be processed by receiver . In some embodiments antenna may be a tuned antenna.

Receiver may down convert received tag response signals RF to an in phase I channel and a quadrature phase Q channel respectively Iand Q although the scope of the invention is not limited in this respect. In these embodiments mixers and may be I channel and Q channel mixers used to generate I and Q baseband signals based on local oscillator signals. Local oscillator signals may be separated in phase by about 90 degrees.

Although receiver is illustrated as having several separate functional elements one or more of the functional elements may be combined and may be implemented by combinations of software configured elements such as processing elements including digital signal processors DSPs and or other hardware elements. For example some elements may comprise one or more microprocessors DSPs application specific integrated circuits ASICs and combinations of various hardware and logic circuitry for performing at least the functions described herein. In some embodiments at least portions of receiver may be fabricated on a single monolithic semiconductor substrate such as a radio frequency integrated circuit RFIC .

Similarly to receiver of receiver includes antenna mixers and phase converter local oscillator and demodulator . Differently from the previous receiver however receiver includes Analog Digital Converters ADCs and which provide digital Iand Qto demodulator which is arranged to receive digital signals.

FM0 is currently used in ISO standards. This modulation is fast but may be more susceptible to interference. Waveform shows an FM0 preamble without a pilot tone. Tag to reader FM0 signaling begins with the preamble shown in the figure. The v shown in the preamble indicates an FM0 violation i.e. a phase inversion should have occurred but did not .

Miller Subcarrier modulation is slower but less susceptible to errors in RF noisy environments. This algorithm uses narrow spectrum for the tags to send back their signal and fits it between the channels used by the reader. That way the RF signals coming from the reader do not cover the signals coming back from the tags. Miller demodulation uses advanced filtering techniques to separate the tag s response from the reader s transmissions and other noise compared to FM0.

Miller modulated subcarrier sequences contain exactly two four or eight subcarrier cycles per bit depending on the M value specified in a Query command that initiated the inventory round example subcarrier sequences .

One way of detecting the tag s preamble without using a pilot tone is employing a preamble matched filter block comprising a plurality of matched filters in combination with a timebase estimator synchronizer comprising a plurality of magnitude detectors.

In such a system incoming data is provided to the series of preamble matched filters through N each with a different timebase timebases through N . The matched filters block incoming signal except for the filter or filters with a close timebase. This gives a large peak when the expected preamble is filtered through the applicable filter. Each filter s output is provided to a corresponding magnitude detector through N.

One of the matched filter magnitude detector combinations gives the largest peak upon detecting the tag preamble. Maximum magnitude detector of timebase estimator synchronizer detects which magnitude detector captures the expected preamble and provides the signal from that magnitude detector to the demodulator with a known frequency phase and time of arrival.

In such systems multiple matched filters operate in parallel for recovering preamble. The filters are arrayed so that together they can cover the wide variance. The large lock range of bit tracking loop requires a large number of filters and magnitude detectors to detect the tag preamble increasing cost of manufacture power consumption and complexity of circuits.

In a typical tag design the tolerance on the tag s oscillator clock can be as small as 4 or as large as 22 depending on the data rate. This can be contrasted with typical wireless systems where the tolerance can be 

If nothing is done the reader can have errors in detection such as false tag responses and missed tag responses. According to some embodiments the tag may be commanded to generate a pilot tone in its backscatter. When the backscattered pilot tone is received in the reader the pilot tone may be used to estimate the tag period frequency. Then the estimate may be used to seed and lock the few or just one symbol timing recovery loop.

Using the pilot tone to detect a frequency and phase of the tag signal allows synchronous detection of the tag preamble from an asynchronous signal with fewer correlators than any parallel implementation. Indeed an RFID reader detection circuit using the pilot tone may be implemented with a single correlator as described in conjunction with resulting in manufacturing cost savings power consumption reduction and the ability to reduce an integrated circuit size such as an FPGA size to implement the circuits. It also reduces the complexity of the reader circuits.

According to the Gen2 specification a TRbit in a Query command may be used to enable a pilot tone preceding the tag s backscattered preamble. Other methods may also be used to command the tag to transmit the pilot tone prior to sending its data. In the Query command TR 1 chooses the tag to reader T R preamble to be prepended with a pilot tone.

As shown in table an example Query command may include bits defining a DR value for singulation a Miller subcarrier selection bit pair defining what number of cycles per symbol is to be used a TRbit defining whether or not a pilot tone is requested a session identifier a cyclical redundancy check bit and so on.

As shown in diagram the tag response following a Query command with TR 1 includes pilot tone before tag preamble which is followed by tag response packet . The pilot tone is at the period frequency of the tag.

The FM0 preamble shown in includes the same preamble as in prepended with 12 leading zero bits forming the pilot tone . According to other specifications a 1 bit value or a different number of bits may be used as the pilot tone.

Three example Miller preambles of for M 2 M 4 and M 8 are shown in each prepended with 16 leading zero bits serving as the pilot tone. Similarly other bit values or number of bits may also be chosen as pilot tone for use with Miller preambles.

As described in incoming tag signal with the pilot tone includes pilot tone between time points T and T tag preamble between T and T and tag response packet starting at T.

Processing of the tag signal by the reader involves frequency phase and time of arrival acquisition from the pilot tone and tag preamble between T and T. According to some embodiments the reader may also process the preamble in one or more sample rate correlators through N . Normally the correlator performs correlation with an expected preamble. This gives a large peak when the expected preamble is received due to autocorrelation.

In a typical communication session the RFID reader sends a command via an RF wave that encodes symbols which define the command. Then the reader waits for some time while still transmitting RF. At the end of the silent period the tag backscatters a response which the reader is supposed to detect and read. The backscatter includes a preamble and data associated with the command. According to some embodiments the tag response may also include a pilot tone before the preamble if the reader s command specified it.

Input signal IN may include combined I and Q channels of the tag response signal. The signal is provided to buffer delay block for generating a delayed version of the received signal which is provided to mixer . The delay is set by the frequency estimator.

Pilot tone portion of the signal Sis also provided to pilot tone detector frequency estimator . The tag signal frequency is estimated using any one or combination of methods including a discrete Fourier transform DFT fast Fourier transform FFT or analog clock recovery loop prior to the impending arrival of the tag s preamble. So a more accurate estimate of the tag s backscatter data rate can be made.

Pilot tone detector frequency estimator provides an RF signal phase estimation S to mixer such that the I and Q signals can be combined to form S f that is provided as input to symbol timing recovery loop .

A phase of the tag signal may also be estimated by the pilot tone detector . The estimated frequency and or phase Sand S are then provided to symbol timing recovery loop to seed the recovery operation.

Symbol timing recovery loop estimates a narrowed window for the time of arrival of the packet and thus knows when to turn on the correlator s . Once the frequency is established only synchronous detection of the preamble is required. Thus only one correlator may be sufficient for recovering the preamble.

Upon exiting the loop and right before the correlator the signal then is frequency locked and or phase locked. A single correlator may thus yield the exact Time of Arrival. Correlator operates synchronously to detect the tag s preamble response and delivers the preamble to the demodulator.

The circuits described above may be implemented as analog digital DSP FPGA circuitry or any combination thereof. Furthermore at least a portion of the functionality may be implemented as software in dedicated or generic hardware. The described recovery techniques may be used in both baseband and subcarrier modes.

In diagram the main portions of the incoming signal pilot tone tag preamble and tag response packet are shown against a timeline. Between T and T that cover the arrival of pilot tone and tag preamble the reader may perform coarse estimates for RF phase symbol frequency and symbol phase using Fourier transform FT and or asynchronous matched filtering . Because this process may take some time to perform a delay may be introduced to the incoming tag signal e.g. by a variable buffer delay block of the reader resulting in the delayed pilot tone delayed tag preamble and delayed tag response packet .

Thus the new packet epoch time of arrival gets shifted to the beginning point of delayed tag response packet . Following delay the reader may perform fine estimates on the received signal employing symbol time recovery loop and single synchronized matched filter . Following fine estimates data recovery operations may be performed on the delayed tag response packet by the demodulator.

By using frequency and phase estimates to seed and lock the symbol time recovery loop the detection circuit of the reader can zoom in on an expected tag preamble within the relatively large range of possibilities. Therefore a number of correlators for detecting the preamble can be substantially reduced. Correlator block is such an example using only two matched filter magnitude detector sets.

As described previously in conjunction with preamble matched filters and derived from different timebases and receive signal TS and provide a signal to corresponding magnitude detectors and in timebase estimator synchronizer block . During an operation one of the two sets captures the incoming tag preamble and provides a larger magnitude signal to maximum magnitude detector which in turn forwards the detected preamble information to the demodulator.

As mentioned previously due to the lock in on the expected preamble using the pilot tone detection correlator block may be implemented in a preferred embodiment with only a single set of matched filter magnitude detector set.

Since the frequency and phase information associated with the preamble is already determined by the symbol time recovery loop preamble matched filter may be used with a single timebase followed by magnitude detector . Because a single set of matched filter magnitude detector is used no maximum magnitude detector is needed. The detected preamble information is forwarded to the demodulator directly by the magnitude detector .

Pilot tone detector frequency estimator includes pilot tone detection block which is arranged to receive the pilot tone and provide RF phase symbol phase and symbol frequency estimate signals S S and S.

According to some embodiments pilot tone detector frequency estimator may include an optional preamble matched filter block that is arranged to perform the same function employing matched filters instead of the pilot tone detector frequency estimator and provide estimate signals S S and S. The pilot tone detection block may be used for coarse estimates while the preamble matched filter block is used for fine estimates.

Estimate signals S S and Sfrom either block or both may be provided to a selection block such as a selector a state machine and the like. The selection block may provide individual estimate signals S S and Sto other circuits such as correlators.

Circuit includes a channelized filter bank which receives the incoming signal divides into spectral components and provides to peak detector . The received signal Sis also provided to power measurement block . The measured power is scaled by scaler and provided to comparator .

A delayed version of the detected peak of the filtered input signal Sis provided by delay block to comparators and . A peak and hold block receives the detected peaks of the filtered input signals Sand Sfrom peak detector providing an input to scaler as well as a frequency estimate output Sand an input to RF phase estimator for phase estimation.

An output of scaler is provided to comparator for comparison with the delayed version of the signal from delay block . Both comparator and outputs are then combined at combiner to provide a signal for symbol phase S. The estimate signals Sand Smay be used to seed and lock the few or just one symbol timing recovery loop.

According to some embodiments a method for an RFID reader system may include receiving from an RFID tag a backscattered signal detecting the pilot tone estimating a frequency of the pilot tone in the backscattered signal recovering a timing of symbols in the backscattered signal using the estimated frequency demodulating the backscattered signal based on the symbol timing to recover data. The signal may be backscattered from the RFID tag responsive to a command transmitted by the reader where the pilot tone is detected only if the command belongs in a subset of commands.

The pilot tone may be detected by generating a baseline version of the backscattered signal generating a version of the backscattered signal that is delayed with respect to the backscattered signal and establishing detection when the delayed version reaches a detection relationship with the baseline version. The detection relationship may be that the delayed version exceeds the baseline version.

Moreover the baseline version of the tag signal may be generated as a preset portion of a magnitude of the tag signal. The preset portion may be substantially equal to 50 . According to other embodiments the baseline version may have a waveform that rises up to a cusp and then continues at substantially the same value and the delayed version may be delayed enough so that detection is established after the cusp. Detection may be established only if both the delayed version and the baseline version exceed a detection threshold. Furthermore the detection threshold may be defined in terms of detected ambient noise and may be updated.

According to further embodiments the backscattered signal may be received responsive to a command signal transmitted by the RFID reader system the command signal may cause the tag to be silent during a silent period and the detection threshold is defined from a power measurement made during the silent period.

The frequency of the tag signal may be estimated by employing a Discrete Fourier Transform DFT or Fast Fourier Transform FFT of the received pilot tone. The frequency may also be estimated by correlating the backscattered tag signal with an expected version of the backscattered signal.

The method according to embodiments may further include identifying in the backscattered signal a preamble using the symbol timing where the backscattered signal is demodulated based on a timing of the preamble and determining from the preamble timing a Time Of Arrival TOA for a remainder of the backscattered signal where the data is recovered from the remainder. The preamble may be identified using a single correlator.

In yet further embodiments the method may include delaying the remainder of the backscattered signal the preamble by a delay time and adjusting the delay time to compensate for an amount of time taken to estimate the frequency.

The invention also includes methods. Some are methods of operation of an RFID reader or RFID reader system. Others are methods for controlling an RFID reader or RFID reader system.

These methods can be implemented in any number of ways including the structures described in this document. One such way is by machine operations of devices of the type described in this document.

Another optional way is for one or more of the individual operations of the methods to be performed in conjunction with one or more human operators performing some. These human operators need not be collocated with each other but each can be only with a machine that performs a portion of the program.

Process begins at optional operation where the tag signal is received. As mentioned previously tag signal includes a frequency and a phase that is typically not synchronous with a frequency and phase of the reader clock.

According to next operation a baseline version of the tag signal is generated as described above in conjunction with .

According to a next decision operation a determination is made whether the delayed version of the tag signal is larger than the baseline version. If the baseline version is larger no pilot tone has been detected and processing returns to a calling process for further operations.

If the delayed version of the tag signal is larger than the baseline version processing continues from decision operation to optional operation where the pilot tone is detected and operations associated with adjusting a frequency and phase of the reader clock signal may be performed.

The operations included in process are for illustration purposes. Pilot tone detection in an RFID reader by comparing a delayed version of the tag signal with a baseline version may be implemented by similar processes with fewer or additional steps as well as in different order of operations using the principles described herein.

According to some embodiments a pilot tone transmitted by the tag for providing the reader with information about its response frequency and phase may be detected by the reader employing two separate criteria. A first criterion may include detection based on a comparison of the pilot tone with a noise based threshold as shown in diagram .

The noise based threshold is set in response to a measurement performed at a time point before the tag response is expected. The measurement may be a power measurement and the power estimate scaled to set a desired False Alarm Rate FAR and a detection probability. Since the threshold is based on an actual measurement it adapts to a dynamic RFID environment which may include interference noise different tag power levels and so on.

Once the first detection occurs an auto normalized baseline version of the tag signal may be established based on the signal magnitude. The threshold may be peak held and scaled. A delayed signal version may also be derived from the received signal by imposing a preset delay . A leading edge of the received pilot tone increases with the same gradient as the delayed version.

The delayed version is then compared to the signal based threshold baseline version to detect the pilot tone with an accurate time of arrival estimate.

Diagram shows pilot tone magnitude over time. Initially the pilot tone is not detected . The first criterion noise based threshold initiates the implementation of the second criterion signal based threshold . If both are satisfied pilot tone detection is established .

The waveforms and circuits described above illustrate an example embodiment for using comparison between a baseline version and a delayed version of tag signal for tag pilot tone detection. Other circuits and waveforms may also be used without departing from a scope and spirit of the invention.

As described previously in conjunction with the I and Q channels of the detected tag response signal may be provided by the receiver block to a buffer delay block of a frequency and or phase estimator circuit of the reader. The buffer delay block may include in one embodiment a variable rate buffer .

A rate of the variable rate buffer may be controlled by a feedback signal from frequency estimator to compensate for the time it takes to estimate the frequency. Variable rate buffer then provides the buffered tag response signal to a mixer for the symbol timing recovery loop.

In another embodiment a variable delay block may be used to receive the I and Q channels of the detected tag response signal and generate a delayed version based on the estimation control signal from the frequency estimator.

Symbol timing recovery loop block includes data matched filter for receiving signal S f from a mixer that mixes an RF estimated signal and a delayed or buffered version of the tag response signal. Data matched filter provides filtered signal to digital rate converter which in turn provides a derived tag response signal recovered signal TS to other circuits such as one or more correlators of the reader. Digital rate converter also provides the recovered signal to the symbol timing recovery loop comprising in addition to the digital rate converter timing error detector loop filter and numerically controlled oscillator NCO .

A phase detector part of the feedback loop comprising the timing error detector and the loop filter enables digital rate converter to perform conversion that peaks corresponding to correct timing of the derived signal correspond to the peaks of the actual tag signal and can be provided to other digital circuitry within the reader as output.

NCO also receives an estimated frequency input Sfrom frequency estimator and provides feedback phase estimation Sto digital rate converter for adjusting the sample the interpolation and decimation such that the digital rate converter output samples are phase and frequency synchronous with the received tag signal.

In such a system timing recovery circuits may be implemented fully in digital domain and there is no need for an analog PLL or Nth order non linearity. Furthermore ADC clock is allowed to be a single fixed frequency clock unrelated to the received signal frequency. ADC digital processing and back end interfaces may all operate from a single fixed clock. Thus there is no need for adjusting ADC sample clock frequency and phase based on the received signal. The data matched filter may operate synchronous to the received signal providing optimal performance.

Similar to the block diagram of symbol timing recovery loop block includes digital rate converter which provides a derived tag response signal recovered signal to data matched filter which in turn provide output signal TS to other circuits such as one or more correlators of the reader. Data matched filter also provides the recovered signal to the symbol timing recovery loop comprising timing error detector loop filter and numerically controlled oscillator NCO .

Differently from the symbol timing recovery loop block data matched filter is within the timing loop between digital rate converter and timing error detector in the symbol timing recovery loop block of . In other embodiments the symbol timing recovery loop block may be implemented without using a data matched filter at all.

Digital rate converter may derive the recovered signal employing various conversion approaches. According to one embodiment digital rate converter may perform conversion based on time variant fractional adjustment.

Digital rate converter may perform interpolation across an N point sample set followed by variable rate decimation and generate derived samples in response to receiving ADC samples of the tag response signal by fractional delay processing of these samples.

Digital rate converter may include interpolating filter decimator and timing processor . Interpolating filter receives ADC samples S f with a frequency f 1 Tand performs the interpolation. The interpolation may be an exponential interpolation Lagrange interpolation and the like. Interpolating filter also receives an input from timing processor that includes time variant fractional delay coefficient for adjusting sample peaks.

Decimator decimates an output of interpolating filter based on a control signal from timing processor which in turn receives feedback from the NCO of the timing loop. Thus the rate converter decimates the interpolated data samples with the dynamic decimation rate changing with time to produce an output frequency synchronous with the received symbol rate.

Data matched filter may be implemented using filter and decimator . An output of decimator is the recovered tag response signal TS.

In a simple implementation loop filter may include an integrator that receives and output of the phase detector and provides a control signal to the NCO of the timing recovery circuit. The loop filter may include phase lead lag compensation and be of any order.

An NCO is a digital system that synthesizes a range of frequencies through the accumulation of discrete input phase increments. The output frequency range is controlled by the size of the input phase increment and the fixed NCO clock frequency.

The NCO can also be implemented in a number of ways. One example embodiment of NCO includes combiner which receives an output of the loop filter a symbol frequency estimation signal S and a feedback signal from digital feedback register . The combiner s output is provided to amplifier with a preset gain g. The NCO s output is provided to the timing processor of the digital rate converter such that it can control a decimator for decimating selected samples and outputting those that correspond to received sample values synchronous with the received tag signal.

The circuits described above illustrate an example embodiment for using pilot tone based timing recovery from tag signals. Other circuits may also be used without departing from a scope and spirit of the invention.

Process begins at optional operation where the reader transmits a carrier wave with a command that instructs the tags to respond with a pilot tone.

According to a next decision operation a determination is made whether the command affects a tag memory such as a Non Volatile Memory NVM . If the tag memory is affected processing advances to optional operation . If the memory is not affected processing proceeds to operation .

At a next optional operation the backscattered pilot tone in the tag response is detected by comparing the delayed version of the signal to a baseline established from the received signal.

At a next operation a frequency of the tag response is estimated. The estimated frequency is used to seed a symbol timing recovery loop.

At a next operation the delayed version of the received signal is provided to the symbol timing recovery loop and recovered tag signal TS generated using the recovered symbol timing.

At a next operation the recovered tag signal is passed through one or more correlators to detect the preamble of the tag signal.

The operations included in process are for illustration purposes. Demodulation of a tag response signal by symbol timing recovery based on pilot tone detection may be implemented by similar processes with fewer or additional steps as well as in different order of operations using the principles described herein.

In this description numerous details have been set forth in order to provide a thorough understanding. In other instances well known features have not been described in detail in order to not obscure unnecessarily the description.

A person skilled in the art will be able to practice the embodiments in view of this description which is to be taken as a whole. The specific embodiments as disclosed and illustrated herein are not to be considered in a limiting sense. Indeed it should be readily apparent to those skilled in the art that what is described herein may be modified in numerous ways. Such ways can include equivalents to what is described herein.

The following claims define certain combinations and sub combinations of elements features steps and or functions which are regarded as novel and non obvious. Additional claims for other combinations and sub combinations may be presented in this or a related document.

