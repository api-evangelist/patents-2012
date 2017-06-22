---

title: High resolution wireless indoor positioning system for legacy standards-based narrowband mobile radios
abstract: Two or more data packets transmitted through a wireless channel are received using a receiver device. The two or more data packets are a result of two or more transmissions that are made sequentially in time at different center frequencies in order to span a desired bandwidth. Each data packet of the two or more data packets is transmitted at a single center frequency. Time differences and/or carrier phase differences among the two or more transmissions are estimated. A time-of-arrival of one or more data packets of the two or more data packets is calculated using each data packet of the two or more data packets and one or more of the estimated time differences, the different center frequencies, and the estimated carrier phase differences.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08265011&OS=08265011&RS=08265011
owner: Diani Systems, Inc.
number: 08265011
owner_city: Ijamsville
owner_country: US
publication_date: 20120122
---
This application is a continuation in part application of U.S. patent application Ser. No. 13 286 649 filed Nov. 1 2011 the 649 application and claims the benefit of U.S. Provisional Patent Application No. 61 435 269 filed Jan. 22 2011. The 649 application claims the benefit of U.S. Provisional Patent Application No. 61 409 123 filed Nov. 2 2010 and U.S. Provisional Patent Application No. 61 421 641 filed Dec. 10 2010. All of the above mentioned applications are incorporated by reference herein in their entireties.

The 649 application describes a method for high resolution channel sounding that can be used to combat multipath in indoor wireless time of flight based positioning systems. Using this technique referred to herein as Time Frequency Offset Wideband TF WB signaling a transmitter device sends a sequence of narrowband packets to a receiver device at different times and frequencies in order to span a desired bandwidth where it is assumed that the time frequency and carrier phase differences among the signal transmissions are known to the receiver. The receiver listens for the transmissions at the known times and frequencies while digitizing and storing them for post processing then uses the stored receive signals and the known time frequency and carrier phase differences to obtain a high resolution time of arrival estimate of the received signals at its antenna.

Although it enjoys significant advantages over state of the art wideband and ultra wideband signaling systems the technique described in the 649 application requires both transmit and receive devices to have knowledge of TF WB and to collaborate in order to make it work. Since there are literally billions of wireless devices shipped each year there is a clear motivation to require only one side of the link the network side to have this knowledge.

Before one or more embodiments of the present teachings are described in detail one skilled in the art will appreciate that the present teachings are not limited in their application to the details of construction the arrangements of components and the arrangement of steps set forth in the following detailed description or illustrated in the drawings. Also it is to be understood that the phraseology and terminology used herein is for the purpose of description and should not be regarded as limiting.

Time frequency offset wideband TF WB signaling is described in the 649 application which is incorporated by reference herein in its entirety. TF WB is a technique that allows the time of arrival ToA of multiple narrowband signals sent sequentially in time and at different center frequencies to be calculated with the same accuracy as a wideband signal spanning the same bandwidth. Although there are other known protocols such as Multi band OFDM also referred to as MB OFDM or ECMA 368 an ultra wideband or UWB standard that use a similar means of generating wideband signals to facilitate high resolution ToA estimates a key advantage TF WB provides over such techniques is that TF WB is designed specifically to be used with pre existing wireless standards such as IEEE 802.11 WiFi Bluetooth GSM GPRS EDGE CDMA etc. Techniques like those prescribed by MB OFDM on the other hand require very specific changes to the physical layer representation of each data packet and as such cannot be applied more generally to other wireless standards. These conceptual differences are illustrated in which show the physical layer characteristics of MB OFDM and TF WB respectively.

In summary unlike other known methods of transmitting multiple narrowband signals sequentially in time and at different center frequencies to improve TOA accuracy TF WB allows data packets to be transmitted at fixed center frequencies and with arbitrary time and carrier phase offsets. These key differences come from its being designed specifically to facilitate high resolution TOA measurements using pre existing wireless protocols.

In various embodiments legacy time frequency offset wideband LTF WB signaling allows a network of wireless receivers to locate a mobile transmitter using TF WB signaling techniques without requiring the mobile to know anything about TF WB or even that it s being located. LTF WB allows for example a network of LTF WB capable IEEE 802.11 WiFi Access Points to locate any WiFi mobile device even if it doesn t support TF WB per se.

While the techniques described herein can be applied to a broad class of wireless protocols including cellular 3G WiMax etc the following examples relate to the IEEE 802.11 Wireless LAN WiFi standard.

SE devices typically the size of a WiFi Access Point AP are placed in various known positions in an indoor environment such as a hospital retail store or a shopping mall. A primary function of SE devices is to measure the ToAs of LTF WB transmissions received from Client device in order to estimate its position. All SE devices in a network are coarsely time synchronized to a common time base in order to simultaneously receive digitize and store incoming transmissions from Client device . SE devices also perform 802.11 transmit functions in order to spoof the Client devices as is discussed below.

Server is used to control the behavior of the Client devices and SE devices during the ToA measurements and to estimate the position u of Client device based on ToA measurements received from the SE devices by solving

As described in the 649 application the basic steps for TF WB transmission reception and TOA estimation are as follows 

In various embodiments the steps for LTF WB transmission reception and TOA estimation are as follows 

In various embodiments Client device is an IEEE 802.11 WiFi Client. Methods for spoofing a WiFi Client include but are not limited to 

In various embodiments a mathematical representation of the sequence of transmissions leaving the Client s antenna in response to the SE s spoof message is

In various embodiments an SE device uses the following high level steps to estimate the time of arrival of a received downconverted digitized. and stored LTF WB waveform 

Since there are only a handful of manufacturers of WiFi chipsets in various embodiments the behavior of each manufacturer s chipset is measured and characterized in response to the spoof messages in order to optimize the efficiency of the AP Client exchange. For example the order at which the Client visits the frequencies the time it spends on each frequency and or the number of times it transmits at each frequency can be measured since some of this information is not clearly specified in the 802.11 standard and left up to the Client manufacturer s discretion. This vendor specific information could then store be stored in a database and later retrieved by the AP when it s online using the vendor ID portion of the Client s MAC address to determine the Client manufacturer s identity.

The IEEE 802.11v standard supports a time stamp mechanism in which the PHY loads the contents of a high speed timer into the TIME OF DEPARTURE field of each packet immediately before transmission. In various embodiments an LTF WB capable AP can decode from the packets received from the Client and subtract the time stamps to obtain the actual time offsets i.e. the vector r defined in Step 3 above. This removes r as an unknown from Step 5 and simplifies the search considerably. More specifically using to denote the actual time differences computed by decoding and subtracting the time stamps the multidimensional search in Step 5 would simplify to the following note that the minimization is now only over and not and 

Nearly all IEEE 802.11n compatible APs and some Clients are equipped with multi input receivers allowing them to receive downconvert and digitize signals through up to 4 antenna paths simultaneously. In various embodiments a multi input receiver can be leveraged to improve the accuracy of the ToA estimates in indoor environments. The improved performance comes from having additional uncorrelated or loosely correlated observations of the ToA through the new antenna paths.

If a multi input receiver is used to receive a LTF WB signal that receiver downconverts digitizes and stores each incoming narrowband transmission through each of its M antenna paths simultaneously. For ToA estimation it computes wideband observation waveforms and Wiener filters for each antenna path and uses the following formula to estimate the ToA which is a generalization of the formula in Step 5 above for multiple antenna paths 

where y nT and h are the wideband observation waveform and Wiener filters respectively and is the average noise power per sample in the mth antenna path. This can be shown to be a maximum likelihood estimate for the ToA given the system model described herein. The estimator can be described in words as follows 

An alternative to the approach described above of summing the MSE s for each antenna path at each candidate TOA would be to estimate the TOA for each antenna path using steps 1 5 above or any other technique and combine these TOAs into a final TOA estimate by computing their mean max min median mode etc.

It should be noted that the multi input ToA estimator described above can be used to enhance the performance of any single antenna path ToA estimator not just one that uses LTF WB signaling. In other words for any system that transmits a known reference waveform circumflex over nT through a multipath additive white Gaussian noise channel with propagation delay and receives through a multi input receiver yielding observation waveforms y nT m 1 . . . M for each of the M antenna paths the approach described above can be shown to provide the optimum ToA estimate.

In addition to improving the time resolution of indoor time of arrival ToA measurements LTF WB can also be used to improve the accuracy of indoor angle of arrival AoA measurements as well. A multi input receiver is required for AoA.

Instead of spoofing the client into sending an LTF WB sequence one may use software on the client to get it to send the sequence. For example the operating system used on Google Android smartphones provides a function in its application programming interface API which when executed causes the smartphone to perform an 802.11 Active Scan sending 802.11 Probe Request messages on each of its supported RF frequencies in sequence. This for example would allow a programmer to write a Google Android application that can generate LTF WB sequences by doing 802.11 Active Scans on command from the network. Unlike spoofing this would obviously require a modification to the client device to support this new functionality but the change is only in software no hardware changes to the client are necessary. Note however that without hardware changes on the client side the time offsets and carrier phase differences between the narrowband transmissions will not generally be available to the client software and so will have to be estimated by the LTF WB enabled receiver on the network side in order to estimate the TOA of the received sequence.

Most digital receivers use some sort of automatic gain control AGC to adjust their received signal level entering the analog to digital converter ADC . The gain control circuit is often implemented as a set of variable gain amplifiers VGAs in series that can be either switched on and off depending on the value of an input gain control word. When a VGA stage is turned on vs. off it can create a carrier phase and or group delay change. If the receiver changes its AGC setting to receive the narrowband transmissions at different frequencies the phase shifts and group delay changes will create distortion in the received waveforms.

Fortunately these phase and group delay vs. Rx gain variations don t change much across time and temperature so they can be calibrated i.e. measured at the time of manufacturing stored in a table and compensated for during data digitization and data storage.

Referring to a system for calculating the time of arrival of a wireless signal through a wireless channel includes receiver device . Receiver device can include but is not limited to an access point a smartphone a laptop computer or a wireless smart tag. Receiver device can include hardware software or a combination of hardware and software.

Receiver device receives two or more data packets transmitted through a wireless channel. The two or more data packets are a result of two or more transmissions that are made sequentially in time at different center frequencies in order to span a desired bandwidth. Each data packet of the two or more data packets is transmitted at a single center frequency.

Receiver device estimates time differences among the two or more transmissions and or carrier phase differences among the two or more transmissions.

Receiver device calculates a time of arrival of one or more data packets of the two or more data packets using each data packet of the two or more received data packets and one or more of the estimated time differences the different center frequencies and the estimated carrier phase differences.

The two or more data packets are different data packets for example. In various embodiments the two or more data packets are the same data packets.

In various embodiments the two or more data packets conform to the IEEE 802.11 Wi Fi standard the Bluetooth standard or the Global System for Mobile Communications GSM standard.

In various embodiments the two or more data packets include IEEE 802.11 Probe Request packets path loss measurement packets or IEEE 802.11v or Cisco CCX path loss measurement packets sent at different times and frequencies.

In various embodiments receiver device further calculates an angle of arrival of at least one data packet of the two or more data packets. Receiver device receives the two or more data packets through two or more antenna paths and simultaneously. Receiver device estimates carrier phases of the two or more data packets received through each antenna path. Receiver device converts the estimated carrier phases into an angle of arrival estimate.

In various embodiments at least one additional receiver device is included that receives the two or more data packets. The at least one additional receiver device calculates an additional time of arrival for the two or more data packets. The time of arrival and the additional time of arrival are used to calculate a location for a device that transmitted the two or more data packets.

In various embodiments the estimated time offsets and or estimated carrier phase offsets and or center frequencies of two or more data packets associated with a group of devices that share a common vendor ID in their MAC address are stored in a database. The information is later retrieved from the database using the decoded vendor IDs from the two or more data packets. The retrieved information is then used in the time of arrival calculation.

In various embodiments receiver device sends a spoof message before receiving the two or more data packets that causes the two or more transmissions. The spoof message includes an 802.11 DISASSOCIATE message and the two or more transmissions include PROBE REQUEST messages for example. In various embodiments the spoof message includes an 802.11k BEACON REQUEST message and the two or more transmissions include PROBE REQUEST messages. In various embodiments the spoof message includes an 802.11v LOCATION CONFIGURATION REQUEST message that provides the different center frequencies and the two or more transmissions include LOCATION TRACK NOTIFICATION messages.

In various embodiments receiver device further receives two or more calibration data packets before receiving the two or more data packets. Receiver device uses the two or more calibration data packets to construct a calibration table. The calibration table stores measured changes in group delay and phase shift over a set of receiver gain settings and or RF center frequencies. Receiver device later uses the calibration table contents in time of arrival and or angle of arrival calculations.

In various embodiments the two or more data packets are 802.11v data packets that include time stamps. Receiver device uses differences among the time stamps as the estimated time differences.

In various embodiments the two or more data packets are received simultaneously through a plurality of antenna paths and . A time of arrival is calculated for each antenna path producing a plurality of time of arrival values. The plurality of time of arrival values are combined into a final time of arrival estimate.

In various embodiments the two or more data packets are received simultaneously through a plurality of antenna paths and . The steps of estimating and calculating are based on received data packets from each antenna path of the plurality of antenna paths.

In various embodiments receiver device sends a message to a transmitter device not shown before receiving the two or more data packets causing application software running in the transmitter device to perform an 802.11 Active Scan. The transmitter device is a smartphone and the application software is an application running on the smartphone operating system for example.

In step of method two or more data packets transmitted through a wireless channel are received using a receiver device. The two or more data packets are a result of two or more transmissions that are made sequentially in time at different center frequencies in order to span a desired bandwidth. Each data packet of the two or more data packets is transmitted at a single center frequency.

In step time differences among the two or more transmissions and or carrier phase differences among the two or more transmissions are estimated.

In step a time of arrival of one or more data packets of the two or more data packets is calculated using each data packet of the two or more data packets and one or more of the estimated time differences the different center frequencies and the estimated carrier phase differences.

While the present teachings are described in conjunction with various embodiments it is not intended that the present teachings be limited to such embodiments. On the contrary the present teachings encompass various alternatives modifications and equivalents as will be appreciated by those of skill in the art.

Further in describing various embodiments the specification may have presented a method and or process as a particular sequence of steps. However to the extent that the method or process does not rely on the particular order of steps set forth herein the method or process should not be limited to the particular sequence of steps described. As one of ordinary skill in the art would appreciate other sequences of steps may be possible. Therefore the particular order of the steps set forth in the specification should not be construed as limitations on the claims. In addition the claims directed to the method and or process should not be limited to the performance of their steps in the order written and one skilled in the art can readily appreciate that the sequences may be varied and still remain within the spirit and scope of the various embodiments.

