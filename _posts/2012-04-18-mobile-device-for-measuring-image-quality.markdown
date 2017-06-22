---

title: Mobile device for measuring image quality
abstract: A mobile device and method for measuring image quality parameters, the device including a digital camera configured to capture one or a plurality of images, a processor configured to select one or a plurality of pairs of points from each image of the one or plurality of images, each pair of points connectable by a line, the processor further configured to compute one or a plurality of image quality parameters from at least one of the lines, and the processor further configured to compute a representative image quality parameter from the image quality parameters, and an output unit configured to communicate one or a plurality of representative image quality parameters.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09031344&OS=09031344&RS=09031344
owner: Hewlett-Packard Industrial Printing Ltd.
number: 09031344
owner_city: Netanya
owner_country: IL
publication_date: 20120418
---
In quality control instances particularly in quality control of printed images it may be typical to quantitatively assess the amount of grain i.e. extent of graininess e.g. the extent to which the image or an image of a substance appears to be composed of grain like particles and or amount of mottle i.e. mottledness e.g. spotty or patchy color within an image.

In some examples it may be desired to assess graininess and mottledness in the field or on the manufacturing floor where a dedicated measurement device is not immediately present and when results need to be found immediately.

One way to assess graininess is human metrology. However in the field on a short notice and with untrained personnel there may be some use for a standardizable machine vision approach.

It will be appreciated that for simplicity and clarity of illustration elements shown in the figures have not necessarily been drawn to scale. For example the dimensions of some of the elements may be exaggerated relative to other elements for clarity. Further where considered appropriate reference numerals may be repeated among the figures to indicate corresponding or analogous elements.

In the following detailed description numerous specific details are set forth in order to provide a thorough understanding of the methods and apparatus. However it will be understood by those skilled in the art that the present methods and apparatus may be practiced without these specific details. In other instances well known methods procedures and components have not been described in detail so as not to obscure the present methods and apparatus.

Although the examples disclosed and discussed herein are not limited in this regard the terms plurality and a plurality as used herein may include for example. multiple or two or more . The terms plurality or a plurality may be used throughout the specification to describe two or more components devices elements units parameters or the like. Unless explicitly stated the method examples described herein are not constrained to a particular order or sequence. Additionally some of the described method examples or elements thereof can occur or be performed at the same point in time.

Unless specifically stated otherwise as apparent from the following discussions it is appreciated that throughout the specification discussions utilizing terms such as adding . associating selecting evaluating processing computing calculating determining designating allocating or the like refer to the actions and or processes of a computer computer processor or computing system or similar electronic computing device that manipulate execute andlor transform data represented as physical such as electronic quantities within the computing system s registers and or memories into other data similarly represented as physical quantities within the computing system s memories registers or other such information storage transmission or display devices.

Typically a device in some examples a portable device e.g. a mobile device e.g. a smartphone may be configured to operate a software application an application. In some examples the application may include a non transitory computer readable medium comprising instructions.

In some examples an application is configured to operate on common mobile operating systems OS used by smartphones include Apple s ADS Google s Android Microsoft s Windows Phone RIM s BlackBerry OS and embedded Linux distributions such as Maemo and MeeGo.

Typically smartphones independent of the operating system will allow for advanced application programming interfaces APIs for running third party applications. APIs may typically be source code based specifications intended to be used as an interface by software components to communicate with each other. An API may include specifications for routines data structures object classes and variables. These APIs may allow those applications or applications e.g. application to integrate with the smartphone s OS.

In some examples a smartphone running the Android operating system or a smartphone running other know operating systems may be configured to run an application .

Typically device may be a smartphone with an integrated or in some examples a coupled digital camera other cameras may also be used. In some examples the camera may be in wireless communication with the smartphone. In some examples the smartphone may have a flash associated with digital camera .

Digital camera when operating in conjunction with the application may be configured to capture one or a plurality of images where image is a digitally captured representation of an area .

In some examples area may be part of a larger printed image the user analyzing the images representing area within a larger image for image quality. In some examples the user may examine one or a plurality of areas capturing one or a plurality of images for one or a plurality of areas .

Typically the size of area may be constrained by an angle of viewing. In some examples area may be constrained by focusing capabilities of digital camera .

In some examples a lens may be placed in front of the camera. Typically the lens may be a magnifying lens e.g. a magnifying glass someone s glasses a lens taken from apiece of equipment such as a CD player and or any lens to be found in the field. In some examples the lens may be placed in from of digital camera to reduce the magnitude of area .

In some examples area may be a representative area of substance the user analyzing image as representative of area or lamer area for quality control.

Typically environmental variations will not affect the relative consistency of the results e.g. the output of application may stay relatively the same from location to location. Typically human user variations will not affect the relative consistency of results of application .

Typically application will output valve that may be communicated to an individual who is not at the location where the digital camera is capturing image .

In some examples application may have algorithms that allow application to function consistently independent of digital camera s rotations or in some examples independently of an image s rotation.

In some examples application may have algorithms that allow application to function relatively consistently independent of the hardware associated with or comprising device .

In some examples application may be configured to filter out high frequency noise as described below.

In some examples application may be configured to filer out low frequency noise e.g. illumination variations as described below.

In some examples application may be configured to have linear complexity or near linear complexity e.g. the running time of the algorithm tends to increases linearly with the size of the input.

Typically linear complexity or near linear complexity allows application to have minimal processing requirements and allows in some examples application to be computationally quick independent of hardware and or other platform limitations of device .

In some examples the integrated or coupled digital camera may be configured to run under the control of application . In some examples the image acquired by digital camera is typically configured to be of 5 to 10 megapixels in size.

Typically a megapixel may refer to one million pixels and the term pixel typically refers to a single scalar element of a multi component representation e.g. a photosite in the camera sensor context. The term megapixel may not only be used in referring to the number of pixels in an image but in some examples may also be used to express the number of image sensor elements of digital camera or the number of display elements of digital displays.

In some examples device may contain digital camera . Currently there are in the market many cameras with various resolutions all of which may be used. As an example consider camera that makes a 2580 2048 pixel image digital camera may typically uses a few extra rows and columns as sensor elements and may be commonly said be classed as a 5.2 or 5.3 megapixel camera sensor depending on whether the number reported is the effective or the total pixel count.

Typically digital camera may use photosensitive electronics either a charge coupled device CCD or a complementary metal oxide semiconductor CMOS image sensor. The photosensitive electronics consisting of a large number of single sensor elements may record a measured intensity level.

In some examples the sensor array in digital camera may be covered with a patterned color filter mosaic having red green and blue regions e.g. in the Bayer filter arrangement where a Bayer filter arrangement may refer to a block of four filters which are arranged in the order of blue green green and red.

Typically digital camera may interpolate the color information of neighboring sensor elements through a process called demosaicing to create the final image. These sensor elements are often called pixels even though they typically only record 1 channel only red or green or blue of the final color image.

Typically when a sensor element records 1 channel only red or green or blue of the final color image two of the three color channels for each sensor need to be interpolated. In some examples when two of the three color channels for each sensor need to be interpolated the N megapixel camera that produces an N megapixel image may provide only one third of the information that an image of the same size could get from a scanner or other optical device 

In some examples digital camera may be configured to take images containing more pixels in some examples digital camera may be configured to take pictures containing fewer pixels. In some examples many images are taken in an infinite loop until a user quits or exits application .

In some examples digital camera may be configured to capture image . Typically application is configured to operate digital camera in a macro mode. In some examples captured image may be compressed e.g. as a JPEG. JPEGs and other commonly use methods of lossy compression for digital photography may allow fir the compression to be adjusted allowing for a selectable tradeoff between storage size and image quality. Typically JPEG typically achieves a 10 to 1 compression with little perceptible loss in image quality. Lossy compression algorithms in general for image compression compress data by discarding i.e. losing some of it. The compression algorithms aim to minimize the amount of data that needs to be held handled and or transmitted by the smartphone and or other devices .

In some examples captured image may not be compressed. When captured image is compressed in some examples it can be decompressed by requesting a service from the operating system s kernel e.g. a system call. Typically the operating system executes at the highest level of privilege and allows applications to request services requiring those privileges via system calls which are often executed via interrupts e.g. the interrupt automatically puts a processor into some required privilege level and then passes control to the operating system s kernel which determines whether the calling program should be granted the requested service e.g. a decompression of an image . If the service is granted the kernel executes a specific set of instructions over which the calling program has no direct control returns the privilege level to that of the calling program and then returns control to the calling program.

Typically once image is captured on digital camera the green channel Tay be obtained or extracted from the image. Typically a digital camera may have some multiple of green receptors relative to red and blue receptors. In some mobile operating systems e.g. on the android mobile operating system an image may be obtainable in a YCbCr format. Typically YCbCr Y CbCr or Y Pb Cb Pr Cr also written as YCBCR or Y CBCR is a family of color spaces used as a part of the color image pipeline in digital photography where Y is the luma component and CB and CR are the blue difference and red difference chroma components. In some examples Y CbCr is an encoding ROB information in color space. Typically the actual color displayed may depend on the actual ROB primaries used to display the signal. Therefore a value expressed as Y CbCr may be predictable only if standard RGB primary chromaticities are used. Where in some operating systems the reconstruction algorithm for interpolating over the color channels may not be known only one channel may be used. Typically when the reconstruction algorithm for interpolating over the color channels is not known the green channel is extracted and all other channels are ignored.

Typically when the reconstruction algorithm for interpolating over the color channels is not known and the green channel is extracted with all other channels ignored application may apply algorithms to determine graininess to gray level grain or green level grain and typically not to grain in other color channels.

In some examples when analyzing image a green channel is selected and a red and a blue channel are discarded. Typically when the green channel is selected and the red and the blue channels are discarded the image quality parameter is computed only for the green channel.

In some examples luminescence Y channel is selected and color blue Cb and color red Cr information is discarded. Typically when luminescence Y channel is selected and color blue Cb and color red Cr information is discarded the image quality parameter is computed only of the luminance of image .

Typically image processing may be do by processor on a thread that is separate from a graphical user interface GUI .

In some examples the infinite loop may include the following Capture image via digital camera fill image buffer in digital camera Calculate parameters as described below Output parameters Repeat as described below.

A memory unit is typically configured to store captured images. Memory unit may also be configured to store outputted parameters list in some examples a list of computed image quality parameters described below. Memory unit may typically be the onboard memory of a smartphone or other device on which application is operating in some examples memory unit may be an external memory unit such as a removable flash memory card or other memory units.

Typically application uses sufficient memory to save the individual images. Typically application does not require substantial memory over and above the memory necessary to store the images.

A processor may compute one or a plurality of image quality parameters. Typically digital processor computes an image quality parameter for one or a plurality of the images. In some examples digital processor computes an image quality parameter for less than all of the images. In some examples processor may be a processor that is a component of a smartphone. In some examples processor may be based on an ARM core in some examples processor may be in wireless communication with the smartphone.

In some examples application is configured to solve the algorithms and present a result using even the slow processors running at slow speeds and without any dedicated hardware acceleration.

An output unit in some examples a monitor or a speaker or other methods of outputting information may be configured to communicate said one or a plurality of parameters to a user of application and or to display an output of an algorithm the algorithms described below.

Typically output unit may be the display of the phone but the result e.g. one or a plurality of the parameters may also be communicated by radio waves or through a USB connector or other methods.

In some examples processor may implement a loop program in which a pair of points including point A and point B or coordinates e.g. in image height and width is selected using a random number generator. The random lumber generator may be the Java Math.random function or other random number generators.

The number of iterations for this loop is typically between 100 and 1000 iterations. In some examples a small number of iterations may be performed to increase the speed of the operation of the algorithm. In some examples a larger number of iterations may be used to increase accuracy of the algorithm.

Typically the capabilities of the operating platform and the user s time limitations will be used to determine the number of iterations performed by the algorithm.

In some examples pairs of points are chosen at random without regard to the angle between the two points. Typically the slope of a line m between the pair of points will have minimal affect on the result of the algorithm as grain and mottle are typically relatively invariant to rotation.

In some applications processor may be configured to select prescribed angles between pair of points . For example when measuring banding or strips defects of image quality in image processor may be configured to select vertical or horizontal strips e.g. slope 0. In some examples the horizontal and or vertical of an image may be defined in either relation to the image frame or to the earth s gravity using an accelerometer the accelerometer typically a component of the smartphone.

Typically the distance between point A and point B may be higher than a predetermined number of pixels for example the number of pixels within a tenth of a dimension e.g. width or length of image .

For any given selected pairs of points processor may compute an image quality parameter. Typically a plurality of parameters may be collected for a plurality of pairs of points . Typically the plurality of parameters may be distilled to compute at least one image quality parameter for outputting to a user.

Typically the algorithm may initially acquire an image . The algorithm may loop several times computing a parameter for at least one of the pairs of points over a plurality of pairs of points pairs of points e.g. point A and point B in image over a plurality of images .

Application may distill many parameters relating to one or a plurality of pairs of points to at least one output parameter. Application may take successive images looping and computing the algorithms and distilling many parameters relating to one or a plurality of pairs of points to at least one output parameter for one or a plurality of the pairs of points for at least one of the images resulting in an output to the user.

Typically a line can be drawn between point A and Point B. Line may be divided into at least two segments . Typically when computing the parameters described above only locations e.g. pixels or points in image located at or near line are taken into account to reduce computation time. Typically when line is divided into at least two segments segment image quality parameters may be assessed for at least one or a plurality of segments .

Typically many parameters are distilled for each of the pairs of points generally speaking in reference to the distribution of their values.

In some examples for relatively fast results the median function may be used e.g. Output Median plurality of parameters for pairs of points 

Typically the outputted parameters may be an outputted parameters list e.g. a list of image quality parameters that is generated by one or a plurality of algorithms the algorithms described below in real time or near real time typically from a rate of an item per second to an item per ten seconds.

In some examples the computations of processor may be implemented on the cloud or other non local infrastructure e.g. a remote location from the mobile device 

Typically the computations of processor may be implemented on cloud . An outgoing communication unit in some examples a component of device may communicate image or some by products of image to cloud . Typically this may be a built in capability on a mobile phone platform.

Typically cloud e.g. the internet comprises processing means such as server farms . In some examples server farms may run the computations typically run by processor . Results are from server farms running the computations typically run by processor may be communicated to an incoming communication sub unit also typically a built in capability of a mobile phone.

Typically a segment is a part of line between points A and point B. The pair of points e.g. point A and point B representing a set of pixels on image the image captured via digital camera .

Typically a smooth signal may be calculated via algorithms smooth signal may typically be a product of measured signal of image .

Typically line is divided into one or plurality of segments . In some examples line may be divided into 10 segments each segment being of equal length. In some examples each segment may not be of equal length.

In some examples the size of a segment may typically be 100 pixels. In some examples line is divided into segments the divisions at coordinates of significant change in signal value.

In some examples signal may be filtered via algorithms to produce signal typically by the removal of unwanted frequencies. Typically the algorithm may average together neighboring values of signal using a predetermined weight. In some examples the weights are selected so that the algorithm would emulate visual perception given image resolution and expected distance from the camera lens on digital camera to the measured image and or other image capture parameters.

In some examples a predetermined number of values e.g. 5 10 e.g. 8 are averaged together without weights.

Typically signal may be subtracted from a polynomial of a small degree fitted to signal where a small degree is typically 1 to 5 e.g. 3 to filter out low frequencies. In some examples signal may be subtracted from its third polynomial fit to filter out low frequencies.

Processor described above may compute a parameter of image quality per segment of line . For the image quality parameters of grain or mottle the processor typically compute the standard deviation of values in a segment via an algorithm.

Processor distills in some examples the many parameters for the many segments on line to one parameter for line . In some examples processor may be configured to calculate the standard deviation for at one or a plurality of segments on line . Typically processor may then calculate the median or minimum standard deviation for the entire line and store that in a memory unit the memory unit may be the same or similar to the memory unit described above.

Typically many parameters are distilled the many parameters for the many segments on line to one parameter for line in reference to the distribution of their values. In some examples for very fast results the median or minimum functions may be used e.g. 

Typically the outputted parameters list may be stored and representative values in some examples the most representative values for a captured image are identified and highlighted. The most representative values are typically the largest values. In similar embodiments a value representing a combined output parameter is distilled for the list by list operations such as median mean or maximum

Typically application may calculate a median or a minimum over the results found at one or a plurality of iterations multiply those results by a factor in some examples when image intensity is expressed by numbers between 0 and 255 a factor of 4 may be used to obtain a range of values from 0 to 100. In some examples processor may be configured to drop insignificant digits.

Typically application may iterate the previous steps over one or a plurality of sets of points over one or a plurality of images until the user exits application .

Typically camera coupled to device is configured to capture one or a plurality of images the images typically representative of an area area maybe representative of a larger image the larger image being analyzed by a user as depicted in box .

In some examples a processor within device or in some examples a processor in a cloud may select one or a plurality of pairs of points from the one or plurality of images the points connectable by a line as depicted by box .

In some examples a processor within device or in some examples a processor in a cloud may compute one or a plurality of image quality parameters with regard to line as depicted by box .

Typically a processor within device or in some examples a processor in a cloud may compute one or a plurality of representative image quality parameters from the image quality parameters as depicted in box .

Typically device will output one or a plurality of representative image quality parameters or in some examples an output of the algorithm the output of the algorithm or other outputs to be communicated by output unit as depicted in box .

Examples may include apparatuses for performing the operations described herein. Such apparatuses may be specially constructed for the desired purposes or may comprise computers or processors selectively activated or reconfigured by a computer program stored in the computers. Such computer programs may be stored in a computer readable or processor readable non transitory storage medium any type of disk including floppy disks optical disks CD ROMs magnetic optical disks read only memories ROMs random access memories RAMs electrically programmable read only memories EPROMs electrically erasable and programmable read only memories EEPROMs magnetic or optical cards or any other type of media suitable for storing electronic instructions. It will be appreciated that a variety of programming languages may be used to implement the teachings of examples as described herein. Examples may include an article such as a non transitory computer or processor readable non transitory storage medium such as for example a memory a disk drive or a USB flash memory encoding including or storing instructions e.g. computer executable instructions which when executed by a processor or controller cause the processor or controller to carry out methods disclosed herein. The instructions may cause the processor or controller to execute processes that carry out methods disclosed herein.

Different examples are disclosed herein. Features of certain examples may be combined with features of other examples thus certain examples may be combinations of features of multiple examples. The foregoing description of the examples has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit. It should be appreciated by persons skilled in the art that many modifications variations substitutions changes and equivalents are possible in light of the above teaching. It is therefore to be understood that the appended claims are intended to cover all such modifications and changes.

