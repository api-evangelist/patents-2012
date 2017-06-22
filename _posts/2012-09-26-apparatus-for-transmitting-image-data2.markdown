---

title: Apparatus for transmitting image data
abstract: An image data transmitting apparatus is disclosed, the apparatus being configured to receive a right image and a left image and transmit the received right image and left image to a host system using a USB method, such that a depth image and a color image can be compressed in real time by a standard protocol, the compressed depth image and the color image are respectively converted to USB packet data, and the converted depth image and the color image are transmitted to a host system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09621891&OS=09621891&RS=09621891
owner: LG INNOTEK CO., LTD.
number: 09621891
owner_city: Seoul
owner_country: KR
publication_date: 20120926
---
This application is the U.S. national stage application of International Patent Application No. PCT KR2012 007745 filed Sep. 26 2012 which claims priority to Korean Application No. 10 2011 0099854 filed Sep. 30 2011 the disclosures of each of which are incorporated herein by reference in their entirety.

The teachings in accordance with exemplary embodiments of this invention relate generally to an apparatus for transmitting image data hereinafter referred to as image data transmission apparatus or simply apparatus .

Generally a camera system outputting a depth image using a stereo camera transmits two image data of depth image and color image to a host system. is a configurative block diagram illustrating an image data transmitting apparatus according to prior art.

Referring to a conventional image data transmitting apparatus is configured such that a right image of M N and a left image of M N are image processed by an image processor to output a depth image of M N and a color image of M N where frame size and synchronization of the depth image and color image are corrected by an interface which is simultaneously outputted to a host system such as a television or a computer PC .

In the conventional image data transmitting apparatus when the interface unit transmits an image to the host system the image is transmitted to the host system directly or via IEED1394 CAMLINK HDMI High Definition Multimedia Interface or USB Universal Serial Bus . The CAMLINK or HDMI is limited in use due to high price such that an USB type interface is generally used except for handheld devices. Currently USB 2.0 type is used.

However the USB type interface unit suffers from a disadvantage in that frame size is restricted due to bandwidth limitation 480 Mbps in transmitting a depth image and a color image. Furthermore the USB type interface unit suffers from a disadvantage in that the host system tends to be complicated because one endpoint is used for transmitting an image data see a non standard encoder not shown is required for transmitting two image data through one transmission path and the host system requires a non standard decoder not shown for decoding the coded image data.

Meanwhile the host system also suffers from disadvantages in that it must be mounted with separate non standard driver software for recognizing devices and a separate non standard API Application Programming Interface to go with the separate non standard driver software.

Accordingly an exemplary embodiments of the present invention may relate to an image data transmission apparatus that substantially obviates one or more of the above disadvantages problems due to limitations and disadvantages of related art and it is an object of an exemplary embodiment of the present invention to provide an apparatus for transmitting image data image data transmission apparatus or simply apparatus configured to perform by an interface unit a standard image compression encoding to increase a data transmission efficiency and to cope with bandwidth limitation of USB type.

It is another object of an exemplary embodiment of the present invention to provide an image data transmission apparatus configured to use two endpoints of USB interface unit to transmit two images depth image and color image to a host system via each endpoint whereby separate encoding and decoding are not required.

It is another object of an exemplary embodiment of the present invention to provide an image data transmission apparatus configured to support a USB video class to dispense with a separate device driver where a host system processes an image in response to an API relative to the USB video class to dispense with an additional API.

Technical problems to be solved by the present invention are not restricted to the above mentioned description and any other technical problems not mentioned so far will be clearly appreciated from the following description by skilled in the art.

In order to accomplish the above objects in one general aspect of an exemplary embodiment the present disclosure there may be provided an image data transmission apparatus the apparatus comprising a compression unit performing compression on the depth image data and the color image data in real time using a predetermined standard protocol a conversion unit converting the compressed depth image data and the color image data to USB packet data respectively and a transmission unit transmitting the converted depth image data and the color image data to a host system via USB.

In an exemplary embodiment of the present disclosure the standard protocol used by the compression unit may include JPEG or H.242.

In an exemplary embodiment of the present disclosure the host system may decompress the received depth image data and the color image data using the standard protocol used by the compression unit.

In an exemplary embodiment of the present disclosure the transmission unit may transmit the converted depth image data and the color image data by allocating to mutually different endpoints.

In an exemplary embodiment of the present disclosure the host system may selectively or simultaneously use the received depth image data and the color image data.

In an exemplary embodiment of the present disclosure the transmission unit may transmit the depth image data and the color image data using a universal transport protocol.

In an exemplary embodiment of the present disclosure the universal transport protocol may include a UVC Universal Video Class .

In an exemplary embodiment of the present disclosure the host system may further comprise a UVC driver.

In an exemplary embodiment of the present disclosure the apparatus may further comprise an image processor outputting the depth image data and the color image data from a right image and left image in a stereo type.

In an exemplary embodiment of the present disclosure the image processor may comprise a stereo matching unit determining an image distance by receiving the right image and the left image and a line buffer outputting the color image data from the right image and the left image and outputting the depth image data from an output of the stereo matching unit.

In another general aspect of an exemplary embodiment of the present invention there may be provided an image data transmission apparatus configured to receive a right image and a left image and transmit the received right image and left image to a host system using a USB type the apparatus comprising an image processor determining a depth image data and a color image data using a right image and a left image and a USB interface unit compressing the depth image data and the color image data in real time using a standard protocol and transmitting the compressed depth image data and the color image data respectively to a host system via USB.

In an exemplary embodiment of the present disclosure the USB interface unit may comprise a compression unit performing compression on the depth image data and the color image data in real time using a standard protocol a conversion unit converting the compressed depth image data and the color image data to USB packet data respectively and a transmission unit transmitting the converted depth image data and the color image data.

In an exemplary embodiment of the present disclosure the transmission unit may transmit the converted depth image data and the color image data by allocating to mutually different endpoints.

In an exemplary embodiment of the present disclosure the transmission unit may transmit the depth image data and the color image data using a universal transport protocol.

In an exemplary embodiment of the present disclosure the universal transport protocol may include a UVC.

One advantageous effect is that a standard type such as JPEG or H.264 is used to perform a standard image compression to increase transmission efficiency and to overcome a bandwidth limitation of USB type.

Another advantageous effect is that two endpoints of USB interface unit are used to transmit two images depth image and color image to a host system via each endpoint whereby separate encoding and decoding are not required to simplify the system.

Still another advantageous effect is that a standard UVC is used to transmit image data whereby the host system needs no separate device driver and the host system processes the image data in response to API relative to the UVC whereby additional API is not required to simplify the system.

Still further advantageous effect is that a camera can be easily used free from installation of additional software.

The following description is not intended to limit the invention to the form disclosed herein. Consequently variations and modifications commensurate with the following teachings and skill and knowledge of the relevant art are within the scope of the present invention. The embodiments described herein are further intended to explain modes known of practicing the invention and to enable others skilled in the art to utilize the invention in such or other embodiments and with various modifications required by the particular application s or use s of the present invention.

The disclosed embodiments and advantages thereof are best understood by referring to of the drawings like numerals being used for like and corresponding parts of the various drawings. Other features and advantages of the disclosed embodiments will be or will become apparent to one of ordinary skill in the art upon examination of the following figures and detailed description. It is intended that all such additional features and advantages be included within the scope of the disclosed embodiments and protected by the accompanying drawings. Further the illustrated figures are only exemplary and not intended to assert or imply any limitation with regard to the environment architecture or process in which different embodiments may be implemented. Accordingly the described aspect is intended to embrace all such alterations modifications and variations that fall within the scope and novel idea of the present invention.

It will be understood that the terms includes and or including when used in this specification specify the presence of stated features regions integers steps operations elements and or components but do not preclude the presence or addition of one or more other features regions integers steps operations elements components and or groups thereof. That is the terms including includes having has with or variants thereof are used in the detailed description and or the claims to denote non exhaustive inclusion in a manner similar to the term comprising .

Furthermore exemplary is merely meant to mean an example rather than the best. It is also to be appreciated that features layers and or elements depicted herein are illustrated with particular dimensions and or orientations relative to one another for purposes of simplicity and ease of understanding and that the actual dimensions and or orientations may differ substantially from that illustrated. That is in the drawings the size and relative sizes of layers regions and or other elements may be exaggerated or reduced for clarity. Like numbers refer to like elements throughout and explanations that duplicate one another will be omitted. Now the present invention will be described in detail with reference to the accompanying drawings.

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the general inventive concept. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise.

Now the image data transmitting apparatus according to exemplary embodiments of the present invention will be described in detail with reference to the accompanying drawings.

Referring to an image data transmitting apparatus according to an exemplary embodiment of the present invention comprises an image processor and a USB Universal Serial Bus interface unit where an output of the USB interface unit is transmitted to a host system .

The image processor having received stereo type image of a right image of pixels of M N and a left image of pixels of M N outputs a depth image of pixels of M N and a color image of pixels of M N. The USB interface unit performs an image compression encoding of the inputted depth image and color image in a standard protocol allocates mutually different endpoints A B to the two images and transmits the images to the host system via the endpoints. The transmission of the image data is compliant with the UVC USB Video Class .

The host system is equipped with a UVC driver and receives two image data from the image data transmission apparatus according to an exemplary embodiment of the present invention which allows two video devices to be recognized. A user can selectively use one image or two images as necessary and no additional APIs are required by the host system . Hereinafter the image data transmission device will be described in more detail with reference to the accompanying drawings.

Referring to the image processor in the image data transmitting apparatus according to an exemplary embodiment of the present invention comprises a stereo matching unit delaying units and a line buffer .

The stereo matching unit receives a right image of M N and a left image of M N from cameras not shown to determine a distance to an image captured by the cameras. Algorithms used for determining the distance by the stereo matching unit includes dynamic programming and SAD Sum of Absolute Difference . The algorithms used by the stereo matching unit according to an exemplary embodiment of the present invention are not limited thereto and the distance to the image can be determined by various types of algorithms.

A depth image determined by the stereo matching unit is outputted by passing through the line buffer and the right image and the left image are respectively delayed for a predetermined time t by the delaying units to be outputted in color images via the line buffer .

The depth image outputted by the image processor according to an exemplary embodiment of the present invention may be M N in size and configured in a plurality of frames. For example the depth image may be an image data whose bit number per pixel is 8 bits. Furthermore the color image outputted by the image processor according to an exemplary embodiment of the present invention may be M N in size and configured in a plurality of frames. For example the color image may be an image data whose bit number per pixel is 16 bits.

The image size may be changed in response to a processing speed of the image processor according to an exemplary embodiment of the present invention. For example the image size appropriate for the system may be minimally 640 480 pixels and as the image size increases quality of product can be enhanced. In case of size of the image being 640 480 pixels a minimum data amount can be expressed by the following table 

That is a data amount actually transmitted for transmitting an image size of 640 480 pixels is minimally 27.6 Mbyte sec such that data compression is required for transmitting an image data to the host system through the USB interface unit according to an exemplary embodiment of the present invention.

Referring to the USB interface unit according to an exemplary embodiment of the present invention comprises an image receiving unit a standard image compression unit a packet conversion unit and a transmitting unit .

The image receiving unit receives a depth image and a color image from the image processor . The standard image compression unit performs real time image data compression and performs an individual compression on the respective images depth image and color image using the standard protocols of JPEG Joint Photographic Experts Group or H.264. The JPEG and H.264 are video compression standards. It should be apparent to the skilled in the art that the JPEG and H.264 are video compression standards that are well known such that no more detailed explanation thereto will be omitted. However the video compression standards that are used by the standard image compression unit according to an exemplary embodiment of the present invention are not limited to the JPEG and H.264 and therefore it should be apparent to the skilled in the art that use of newly established standard protocols are not ruled out.

The packet conversion unit converts the compressed image data to USB packet data individually to each image data for transmitting the image data compressed by the standard image compressing unit .

The transmitting unit transmits the USB packet data to the host system . The transmitting unit transmits the USB packet data of two images by allocating to mutually different USB endpoints A B whereby the host system can effectively separate two images depth image and color image .

Meanwhile although the conventional interface unit as shown in has transmitted image data to the host system using non standard data protocol the transmitting unit according to an exemplary embodiment of the present invention can use the universal image data transmission protocols. For example the universal image data transmission protocols defined by the Window system or Linux system can be utilized. A representative example is the UVC. As noted from the above description the USB interface unit according to an exemplary embodiment of the present invention uses the universal protocols to allow dispensing with a separate USB device to be used by the host system .

Referring to the host system receiving image data from the image data transmitting apparatus according to an exemplary embodiment of the present invention comprises a UCV driver unit a standard image decompression unit and an application unit which are mounted as defaults in a conventional host systems e.g. notebook computers TVs tablet computers mobile terminals .

The host system receives two types of image data depth image and color image from the USB interface unit via a receiver not shown whereby it is possible to recognize images received from the UVC driver unit as being the images received from two video devices. This can be enabled by use of two endpoints by the USB interface unit according to an exemplary embodiment of the present invention.

The standard image decompression unit decompresses the image data compressed by the standard image compression unit of the USB interface unit . It should be apparent that the decompression using the compression method used by the standard image compression unit of the USB interface unit is well known to the skilled in the art.

The application unit may be for example an API and provides application for use by a user using the image data whereby the user can selectively use one or two images as necessary.

As apparent from the foregoing the image data transmitting apparatus according to an exemplary embodiment of the present invention is advantageous in that data transmission efficiency can be enhanced by the standard image compression unit using the standard protocol such as JPEG or H.264 and limitation of bandwidth using the USB type can be overcome.

Furthermore the image data transmitting apparatus according to an exemplary embodiment of the present invention is advantageous in that two endpoints of the USB interface unit are used to transmit two images depth image and color image to the host system through each endpoint whereby there is no need of requiring separate encoding and decoding processes.

Furthermore the image data transmitting apparatus according to an exemplary embodiment of the present invention is advantageous in that an image data is transmitted using the standard UVC to dispense with a separate driver unit in the host system and an image signal is processed in response to API relative to the UVC whereby additional API is not required to simplify the system. Thus the host system can easily use a camera from installation of additional software.

Meanwhile the exemplary embodiments of the present disclosure may be embodied in the form of program code embodied in tangible media such as magnetic recording media optical recording media solid state memory floppy diskettes CD ROMs hard drives or any other non transitory machine readable storage medium. When the exemplary embodiments of the present disclosure are implemented using software constituent means of the present disclosure may be code segments executing necessary processes. The programs or code segments may be also embodied in the form of program code for example whether stored in a non transitory machine readable storage medium loaded into and or executed by a machine or transmitted over some transmission medium or carrier such as over electrical wiring or cabling through fiber optics or via electromagnetic radiation wherein when the program code is loaded into and executed by a machine such as a computer the machine becomes an apparatus for practicing the disclosure.

The above described embodiments of the present invention can also be embodied as computer readable codes instructions programs on a computer readable recording medium. Examples of the computer readable recording medium include storage media such as magnetic storage media for example ROMs floppy disks hard disks magnetic tapes etc. optical reading media for example CD ROMs DVDs etc. carrier waves for example transmission through the Internet and the like. The computer readable recording medium can also be distributed over network coupled computer systems so that the computer readable code is stored and executed in a distributed fashion.

The previous description of the present invention is provided to enable any person skilled in the art to make or use the invention. Various modifications to the invention will be readily apparent to those skilled in the art and the generic principles defined herein may be applied to other variations without departing from the spirit or scope of the invention. Thus the invention is not intended to limit the examples described herein but is to be accorded the widest scope consistent with the principles and novel features disclosed herein.

The image data transmitting apparatus according to exemplary embodiment of the present invention has an industrial applicability in that a standard protocol such as JPEG or H.264 is used to perform a standard image compression to increase transmission efficiency and to overcome a bandwidth limitation of USB method two endpoints of USB interface unit are used to transmit two images depth image and color image to a host system via each endpoint whereby separate encoding and decoding are not required to simplify the system a standard UVC is used to transmit image data whereby the host system needs no separate device driver and the host system processes the image data in response to API relative to the UVC whereby additional API is not required to simplify the system and a camera can be easily used free from installation of additional software.

