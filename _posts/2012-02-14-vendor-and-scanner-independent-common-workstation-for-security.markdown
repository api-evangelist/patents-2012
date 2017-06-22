---

title: Vendor and scanner independent common workstation for security
abstract: Integrating a plurality of security imaging units for an airport security checkpoint into networked common workstations, including: scanning items with a first security imaging unit at a primary inspection area, wherein the first security imaging unit is coupled to a first networked common workstation; displaying the scanned items as a displayed image on a display of the first networked common workstation located at the primary inspection area; re-scanning the items with a second security imaging unit coupled to the first networked common workstation when a possible concealment is observed, wherein the first networked common workstation includes a conversion unit which converts outputs of the first and second security imaging units into a common format for the displayed image; routing the displayed image to a second networked common workstation located at a secondary inspection area when the possible concealment is observed, wherein the secondary inspection area is remote from the primary inspection area.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09094580&OS=09094580&RS=09094580
owner: TELESECURITY SCIENCES, INC.
number: 09094580
owner_city: Las Vegas
owner_country: US
publication_date: 20120214
---
This application claims the benefit of priority of U.S. Provisional Patent Application No. 61 442 696 filed Feb. 14 2011 entitled Vendor and Scanner Independent Common Workstation CW for Security. The disclosure of the above referenced provisional application is incorporated herein by reference.

The present invention relates to workstations and more specifically to vendor and scanner independent common workstation for security.

Security imaging systems are designed to detect and anomalies. At airport security checkpoints the image of a scanned bag is presented on the scanner console for viewing by a Transportation Security Officer TSO . The TSO makes the judgment based on the presented image utilizing prior knowledge on appearances of various threats and anomalies. Currently all carry on scanners including single view TRX TIP Ready X ray and multi view AT Advanced Technology scanners operate as stand alone systems and each scanner requires at least one dedicated TSO to perform the inspection.

Other features and advantages of the present invention will become more readily apparent to those of ordinary skill in the art after reviewing the following detailed description and accompanying drawings.

Certain implementations as disclosed herein provide for vendor and scanner independent common workstation for security. After reading this description it will become apparent how to implement the invention in various implementations and applications. Although various implementations of the present invention will be described herein it is understood that these implementations are presented by way of example only and not limitation. As such this detailed description of various implementations should not be construed to limit the scope or breadth of the present invention.

In one implementation the Common Workstation CW framework can be developed to integrate all imaging systems for airport security checkpoints which can process and display the image data from all appropriate security systems. However there are several problems with current systems. At airport security checkpoints the image of a scanned bag is presented on the scanner console for viewing by a Transportation Security Officer TSO . The TSO makes the judgment based on the presented image utilizing prior knowledge on appearances of various threats and anomalies. Currently all carry on scanners including single view TRX TIP Ready X ray and multi view AT Advanced Technology scanners operate as stand alone systems and each scanner requires at least one dedicated TSO to perform the inspection.

No Remote Inspection Lack of standard networking protocols and vendor proprietary image file formats prohibit communication among scanners and the outside world. As a result it is difficult to network the scanners especially a mix of scanners from different vendors for remote inspection of images or monitor maintenance of scanners . It is even doubtful that scanners from the same vendor could be networked.

No Utilization of 3Party Algorithms Newly developed innovative algorithms by 3rd parties such as Automated Target Recognition ATR and novel limited angle reconstruction algorithms are not utilized. The scanner vendors are reluctant to accept 3party algorithms developed elsewhere due to internal politics.

Inconsistent Display Two different scanners of the same type e.g. two AT scanners will generate visually different images for one identical bag due to vendor dependent color image generation scheme. This can cause confusion and degrade TSO performance.

In one implementation solutions for these problems including the above listed problems provide benefits as noted below 

Remote Inspection Scanner and Vendor Independent The CW will connect to all scanners that are DICOS Digital Image Communication for Security compliant. Currently no security scanners are DICOS compliant and in the interim the use of our internally developed software will allow seamless connection to several different systems including TRX AT and AIT Advanced Imaging Technology scanners enabling remote inspection and monitoring. Our current prototype CW already handles certain vendor s TRX AT and AIT images. Note that all scanners connected to the proposed CW immediately become DICOs compliant as CW communicates to the outside world on behalf of the scanners.

Utilization of 3rd Party Algorithms The CW will accept any 3rd party software such as ATR without affecting the scanner operation. Such ATRs may alleviate the need for TSOs one day. As new innovations are discovered and implemented the new algorithms can become a part of the CW as a plug in. Recent innovations such as iterative image reconstruction algorithms with limited number of views and optimum scanner dependent processing can quickly be integrated into the proposed CW for independent TSA testing.

Consistent Display The image of an identical bag will always look the same independent of the scanner because the proposed CW will utilize identical color image generation scheme for all AT scanners.

Multipurpose Workstation The CW framework allows the workstation to be used for different purposes to expedite the screening process and thus to reduce cost. The CW may be placed next to the scanner for the usual Primary Inspection. Eventually all AT consoles could be replaced by the proposed CW. The CW may be placed at the Secondary Inspection Area perhaps 10 20 ft. away from the scanner where a second TSO can take a second look at the image at the request of the first TSO. The CW may be placed at the Bag Search Area to provide visual cues location to quickly find certain concealments while searching inside the bag.

Quick Incorporation of New Technologies Currently installed scanners may not need to be upgraded if incorporation of new innovative algorithms as plug ins suffices. For instance 3party software could readily be integrated into the proposed CW. In addition the CW can quickly take advantage of recent advances in computing power such as multi core CPUs and NVidia s GPU Graphics Processing Unit technology.

Lower TSO Training Cost Once a TSO is trained on the proposed CW the TSO will not need additional training to inspect security images so long as the inspection is performed on the proposed CW whether it is connected to TRX AT or even AIT.

Expedited Independent TSA Testing of Scanners Use of the proposed CW allows TSA to independently test various security scanners as well all associated 3party software plug ins for image quality and performance.

Networking Component All scanners are networked by virtue of a connection to a CW through a suitable network protocol including certain security measures to be developed.

Universal Image Format Software for handling different image formats from different scanners will be developed. Currently the internally developed TSS software library handles Rapiscan Astrophysics and L 3 image formats. The list will be expanded as necessary.

Image Browsing An intuitive multi touch interface for image browsing and manipulation will be developed. This component allows the CW to function as a local as well as remote TSO inspection workstation.

Remote Inspection The CW allows TSOs to browse the images on any networked scanner from any location anywhere in the world.

Extensible Software Architecture The extensible software architecture allows quick integration of newly developed 3party algorithms as plug ins. The architecture allows ATRs to be quickly upgraded to include newly found threats.

ATR Automatic Target Recognition Capability The extensibility of the proposed CW will be demonstrated by integrating our own ATR algorithms for AT. The ATR will detect materials that human inspectors may not readily identify e.g. liquid explosives or threats buried in the midst of cluttered background. Our current implementation of the ATR takes a few seconds on a conventional Pentium platform and will be made to execute within a second.

Note that the proposed CW framework allows 3.sup.rd parties to develop Threat Image Projection TIP as a CW plug in. For instance there may be an approach to develop a TIP library for a generic scanner that is applicable to all line scanners including TRXs and ATs. The 3.sup.rd party software would use this TIP library to insert threat images into the image data stream in real time. The processing would require some transformations according to the specific scanner geometry data and the real time image data to correctly place the TIP object in the midst of the bag in one TRX or more AT views.

In conclusion the proposed CW framework allows seamless integration of 3.sup.rd party algorithms as plug ins and this extensible framework provides an open pathway to harness the expertise of independent teams of scientists from government labs universities and industry.

Benefits of the proposed CW framework include local and remote inspection with ATR for higher passenger throughput streamlined screening and lower false alarm rates ATR aided inspection simple Integration of 3party software solutions ATR TIP image reconstruction etc. immediate upgrading of all scanners to be DICOS compliant by virtue of a connection to a DICOS compliant CW and interface to all security imaging systems including TRX AT AIT and EDS.

Universal Image Format The scanned image data must be transported from the scanner to the CW over a secure network. Different methods may be used for different type of scanners and the CW framework provides a standardized access. Specifically we investigate the following aspects.

The CW is designed to be DICOS compliant. However until the emerging DICOS standard gains industry wide acceptance software for handling different image formats from different scanners will be developed. Currently our internally developed TSS software library handles Rapiscan Astrophysics and L 3 image formats. The list will be expanded as necessary.

Image Browsing The proposed CW is designed with multi touch Graphical User Interface GUI with the usual multi touch interaction. The touch and move pans the image and the two finger pinch zooms the image similar to Apple s iPhone interface.

Remote Inspection The concept of remote access within a security checkpoint is illustrated in . The two CWs are networked to the four scanners and are equipped to perform remote inspection.

Primary Inspection Area The TSO at one of the scanners upon observing a possible concealment may either request 1 bag check and route the image to the Secondary Inspection Area or 2 bag search and route the image to the Bag Search Area. The CWs located at these areas perform as follows.

Secondary Inspection Area The CW supports the remote inspection performed by a second TSO with more experience perhaps located 10 20 ft. away from the scanner. The proposed CW framework alleviates the second TSO of the need to physically move to the scanner which often times is known to cause bottlenecks during the inspection process. The second TSO may also request bag search.

Bag Search Area The CW aids the bag opening by displaying the image of the scanned bag so that the TSO searching for the potential concealment can quickly find the object.

The image sharing capability can be extended beyond a single airport checkpoint. All CWs are connected to a CW Server and through this server a remote CW located anywhere in the world can access the same data as the local CW at the checkpoint as shown in .

The CW Server manages all communication requests and has the capability to log all relevant data traffic between the local CW and the remote CW. Multiple remote CWs may even access the same data to execute different ATR algorithms in parallel.

Extensible Software Architecture The extensible software architecture accommodates currently available software components and extends the capability by allowing future technologies to be easily integrated. This requires the framework that accepts the standard interface for plug in components. shows this concept of extensible software architecture that accepts plug in components.

The CW will be based around a Reconfigurable Data Pipeline that must perform several essential tasks. First it must configure and mediate the flow of data between its attached plug ins. Modular plug in architectures for similar purposes are common in modern software systems. Well specified and widely used examples include COM OSGi and CORBA although it is common to find custom plug in architectures to address specific needs. TSS will work to specify a plug in architecture that is convenient for ATR vendors to implement. When a plug in is loaded it will provide information to the CW about its expected inputs and outputs so that the CW can configure the data pipeline accordingly. Further the CW must aggregate and integrate analysis information from various ATR plug ins. Plug ins may also need to remain appraised of the system state and operator input. A blackboard system or publish subscribe messaging model will facilitate this communication while allowing the system to remain dynamic and extensible. The process isolation features provided by modern operating systems combined with fault tolerant software engineering practices should enable the CW to handle the failure of any plug in component without interrupting the flow of commerce.

In this architecture the input image data is processed by the reconfigurable data pipeline. All the installed software components process the image data sequentially and deliver the result to the I O Interface. This framework allows future software components to be plugged in whether developed by TSS or by a 3party developer.

ATR Automatic Target Recognition Capability The functionality of the extensible software architecture will be demonstrated by integrating an ATR algorithm developed by TSS through the CW plug in interface. The ATR will detect liquid and explosive concealments in bags. Furthermore the ATR will attempt to identify and classify the detected concealments.

TSS has been developing ATR algorithms applicable to various security imaging systems and in the process we have developed various image processing and analysis algorithms. The immediately applicable software components for the proposed ATR include Image segmentation analysis library Object reconstruction by discrete tomography and Liquid and explosive detection and classification.

The above will conform to the plug in interface of the extensible software architecture of the proposed CW framework.

Networking Component Image transport over the network is well supported in most modern platforms on which the scanner software is hosted. The communication security mechanisms are well established and the network environment may be either on wired or wireless network. In case of wireless the data will be transported over a secure channel based on the WPA2 encryption standard. The network performance will not be an issue as a typical image with a size of 1 Mbytes would take less than second for transfer even on a slow wireless network. In any case the image transportation will be performed in the background to minimize the delay.

Universal Image Format TSS has already developed image handling software for a limited number of vendor proprietary image file formats.

Image Browsing TSS has developed a prototype image browser as shown in . Certain improvements are necessary and should be straightforward.

Remote Inspection Portions of this task have been implemented and we do not foresee any complications.

Extensible Software Architecture Software modularity and extensibility have been the key issue in software design since the beginning of software engineering field 40 years ago. It has come to maturity through many programming paradigms and tools including Object Oriented Design D concepts and extensible software approaches cf. Blackboard Pipes and Filters and FxEngine . No complications are expected for the plug in interface of the CW framework.

ATR Capability TSS ATR has shown outstanding performance in a recent government sponsored study. The ATR for liquid threat detection for TRX scanners showed extraordinary performance 100 PD 0 PFA using dual energy radiographic images that government provided to TSS. ATs are essentially TRXs in series and we have been upgrading the ATR capability to ATs aided by limited angle discrete tomography techniques.

The above description of the disclosed implementations is provided to enable any person skilled in the art to make or use the invention. Various modifications to these implementations will be readily apparent to those skilled in the art and the generic principles described herein can be applied to other implementations without departing from the spirit or scope of the invention. Accordingly additional implementations and variations are also within the scope of the invention. Further it is to be understood that the description and drawings presented herein are representative of the subject matter which is broadly contemplated by the present invention. It is further understood that the scope of the present invention fully encompasses other implementations that may become obvious to those skilled in the art and that the scope of the present invention is accordingly limited by nothing other than the appended claims.

