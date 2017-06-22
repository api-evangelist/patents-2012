---

title: Method and apparatus for encoding and/or decoding moving pictures
abstract: A method of encoding moving pictures using a plurality of quantization matrices. The method involves selecting one of the plurality of quantization matrices in consideration of an at least one characteristics of an input image; transforming the input image; and quantizing the transformed input image using the selected quantization matrix.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08902975&OS=08902975&RS=08902975
owner: Samsung Electronics Co., Ltd.
number: 08902975
owner_city: Suwon-Si
owner_country: KR
publication_date: 20121210
---
This application is a continuation of application Ser. No. 12 149 382 filed Apr. 30 2008 which is a continuation of U.S. Pat. No. 7 978 766 filed Oct. 14 2005 which is a continuation of application Ser. No. 10 755 671 filed on Jan. 13 2004 which claims the priority of Korean Patent Application No. 2003 2371 filed on Jan. 14 2003 in the Korean Intellectual Property Office the disclosures of which are incorporated herein by reference.

The present invention relates to a method and apparatus for encoding and or decoding moving pictures and more particularly to a method and an apparatus for encoding and or decoding moving pictures which are capable of enhancing the efficiency of encoding moving pictures by adaptively selecting a quantization matrix in consideration of the characteristics of images input into a moving picture encoder.

In order to provide a video on demand VOD service or to enable a moving picture communication the encoding unit creates a bitstream encoded by a compression technique and the decoding unit restores original images from a bitstream input thereinto.

A discrete cosine transform DCT unit carries out a DCT operation on image data input thereinto in the unit of an 8 8 pixel block in order to remove spatial correlation from the input image data. A quantization unit Q carries out highly efficient data loss compression by carrying out quantization on the input image data using a DCT coefficient obtained by the DCT unit and representing the quantized data by several representative values.

An inverse quantization unit IQ inversely quantizes the quantized image data provided by the quantization unit . An inverse discrete cosine transform IDCT unit carries out an IDCT on the inversely quantized image data provided by the inverse quantization unit . A frame memory unit stores the IDCT ed image data provided by the IDCT unit on a frame by frame basis.

A motion estimation and compensation unit ME MC estimates a motion vector MV for each macroblock and a sum of absolute difference SAD which correspond to a block matching error by using the image data of a current frame inputted thereinto and the image data of a previous frame stored in the frame memory unit .

A variable length coding unit VLC removes statistical redundancy from digital cosine transformed and quantized image data according to the estimated motion vector provided by the motion estimation and compensation unit .

A bitstream encoded by the encoding unit is decoded by the decoding unit . The decoding unit includes a variable length decoding unit VLD an inverse quantization unit an IDCT unit a frame memory unit and a motion estimation unit .

A set top box which receives an analog terrestrial broadcast program and then encodes and stores the received program by using a data compression method such as MPEG2 or MPEG4 has recently been developed. However in the case of a terrestrial broadcast images arriving at a receiving terminal may be distorted due to channel noise. For example an image may look as if white Gaussian noise were added thereto. If the image is compressed as it is the efficiency of compressing the image may be very low due to the influence of the white Gaussian noise.

Therefore in order to get rid of noise in a conventional method of encoding moving pictures a pretreatment filter is provided at an input port of an encoder. However in the case of using the pretreatment filter an additional calculation process for encoding moving pictures is needed.

In addition in such a conventional method of encoding moving pictures a quantization matrix is determined irrespective of the characteristics of an input image and quantization is carried out on the input image by applying the quantization matrix to the input image on a picture by picture basis in which case the efficiency of encoding the inputted image is low.

The present invention provides a method and an apparatus for encoding and or decoding moving pictures which are capable of improving the efficiency and performance of compressing moving pictures.

The present invention also provides a method and an apparatus for encoding and or decoding moving pictures which are capable of removing noise without increasing the number of calculations performed.

According to an aspect of the present invention there is provided a method of encoding moving pictures using a plurality of quantization matrices. The method involves a selecting one of the plurality of quantization matrices in consideration of characteristics of an input image b transforming the input image and c quantizing the transformed input image using the selected quantization matrix.

According to another aspect of the present invention there is provided a method of decoding moving pictures using a plurality of quantization matrices. The method involves a carrying out variable length decoding on encoded image data b extracting index information that specifies one of the plurality of quantization matrices classified according to characteristics of an input image from the variable length decoded image data c selecting one of the plurality of quantization matrices based on the extracted index information and d inversely quantizing each macroblock of the variable length decoded image data using the selected quantization matrix.

According to another aspect of the present invention there is provided an apparatus for encoding moving pictures using a plurality of quantization matrices. The apparatus includes a quantization matrix determination unit that selects one of the plurality of quantization matrices for each macroblock in consideration of characteristics of an input image and generates index information indicating the selected quantization matrix for each macro block a quantization matrix storage unit that stores a plurality of quantization matrices which are classified according to the characteristics of the input image and outputs a quantization matrix for each macroblock according to the index information generated by the quantization matrix determination unit an image transformation unit that transforms the input image and a quantization unit that quantizes the transformed input image using the selected quantization matrix.

According to another aspect of the present invention there is provided an apparatus for decoding moving pictures using a plurality of quantization matrices. The apparatus includes a variable length decoding unit that receives an encoded image stream carries out variable length decoding on the input image stream and extracts index information that specifies one of the plurality of quantization matrices which are classified according to characteristics of an input image from each macroblock of the variable length decoded image stream a quantization matrix storage unit that stores the plurality of quantization matrices selects one of the plurality of quantization matrices based on the extracted index information and outputs the selected quantization matrix and an inverse quantization unit that inversely quantizes each macroblock of the variable length decoded image stream using the quantization matrix output from the quantization matrix storage unit.

Additional aspects and or advantages of the invention will be set forth in part in the description which follows and in part will be obvious from the description or may be learned by practice of the invention.

Reference will now be made in detail to the embodiments of the present invention examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to the like elements throughout. The embodiments are described below to explain the present invention by referring to the figures.

When it comes to encoding moving pictures pre treatment filtering is very important because it can increase the efficiency of encoding the moving pictures by removing noise from images. While a conventional pre treatment filtering technique for removing noise from images is generally carried out in a spatial pixel block in the present invention a noise removal technique is carried out in a DCT block in an apparatus for encoding moving pictures.

In the present invention an approximated generalized Weiner filtering method is used for removing noise from images. In the approximated generalized Weiner filtering method Weiner filtering is realized by taking advantage of fast unitary transformation such as a discrete cosine transform DCT . However a filtering method other than the approximated generalized Weiner filtering method may be selectively used for carrying out filtering in a DCT block.

In v represents an image block containing noise and represents a row ordered column vector of a filtered image block. Since the average of the image block v is not 0 an average estimation unit estimates an average circumflex over m of the image block v and a subtraction unit subtracts the estimated average circumflex over m from the image block v.

A value z output from the subtraction unit as a result of the subtraction is filtered by a filtering unit and the filtering unit outputs filtered data as a result of the filtering. An addition unit adds the estimated average circumflex over m of the image block v to the filtered data and then outputs desirably filtered data as a result of the addition.

Hereinafter an approximated generalized Weiner filtering method for processing an image model whose average is 0 will be described in greater detail.

The approximated generalized Weiner filtering method for processing an image model whose average is 0 can be expressed by Equation 1 below. 1 

In Equation 1 tilde over L AL A L I R R E y y Z Az and represents a noise variance value. In addition in Equation 1 A represents unitary transformation. Since in the present embodiment DCT is used as unitary transformation A represents DCT here. Supposing that Cand represent an 8 8 DCT matrix and a Kronecker operator A CC.

Since in most cases tilde over L is approximately diagonalized in a unitary transformation Equation 1 can be rearranged into Equation 2 below. 2 

In Equation 4 k l represents normalized elements placed along a diagonal line of AL A and represents a variance value of an original image y. In general cannot be known. Therefore is substituted by a result of subtracting the noise variance value from a variance value of z.

As shown in Equation 3 approximated generalized Weiner filtering is carried out on an image block whose average is 0 by multiplying a two dimensional DCT coefficient Z k l by tilde over p k l . Once m n is determined a final filtered image is obtained by adding circumflex over m m n to m n .

Hereinafter an approximated generalized Weiner filtering method for processing an image model whose average is not 0 will be described in greater detail.

Let us assume that an average block is obtained by multiplying an input DCT block containing noise by S k l i.e. the average block satisfied in Equation 5 below. Then the approximated generalized Weiner filter method of which carries out addition and subtraction in the DCT block can be restructured into an approximated generalized Weiner filter of B or C. 5 

By using Equations 3 and 5 an image block filtered in the DCT block can be represented by Equation 6 below.

As shown in Equation 6 the entire filtering process can be simplified into a multiplication of F k l . Equation 7 shows that F k l is determined by a signal to noise ratio SNR a covariance matrix and an average matrix.

In order to determine F k l it is necessary to obtain an average matrix S k l . In the present embodiment among possible candidates for the average matrix S k l the one that is satisfied in Equation 5 is selected. The average matrix S k l can be represented by Equation 8 below. Equation 8 illustrates one of the simplest forms that the average matrix S k l could take in the DCT block.

Hereinafter a pretreatment process performed in an apparatus for encoding moving pictures will be described in greater detail with reference to .

As described above an approximated generalized Weiner filtering process can be carried out on an image block whose average is not 0 by multiplying the image block with a DCT value.

As described in the concepts of the present invention described in can be directly applied to an occasion when an apparatus for encoding moving pictures processes an inter block as long as the noise has been removed from the motion compensated block information p m n .

A covariance value k l is determined depending on whether an input image block is an inter block or an intra block. Therefore F k l of may be varied depending on whether the input image block is an inter block or an intra block.

Hereinafter a method of obtaining an estimated variance value of intra blocks or inter blocks from each of which their average is subtracted will be described in detail with reference to Equation 9 below. Supposing that S represents an N N where N 8 block from which an average of the corresponding block has already been subtracted a variance matrix of the N N block can be obtained using Equation 9 .

Equation 9 has been disclosed by W. Niehsen and M. Brunig in Covariance Analysis of Motion compensated Frame Differences IEEE Trans. Circ. Syst. for Video Technol. June 1999.

An estimated variance value can be obtained by applying Equation 9 to a variety of experimental images. Where an original image block is an intra block an original image is divided into 8 8 blocks and then a variance value of each of the 8 8 blocks is calculated. On the other hand where the original image block is an inter block an estimated variance value is calculated by applying Equation 9 above to each image block that is determined as an inter block.

By using the estimated covariance value the following equation is obtained R E y y . Thereafter by carrying out DCT on R the following equation is obtained ARA .

In Equation 7 the noise variance value can be obtained by using a noise estimator. Given that noise and original image pixels are independent random variables an estimated value circumflex over of the variance of an original image can be calculated using Equation 10 below. circumflex over max circumflex over circumflex over 0 10 

In Equation 10 represents a variance value of each macroblock MB . In a typical type of apparatus for encoding moving pictures is calculated on a macroblock by macroblock basis. In the present embodiment 8 8 blocks in the same macroblock are supposed to have the same variance value. Therefore there is no need to perform additional calculations to obtain a variance value of each of the 8 8 blocks.

In the present embodiment a level of noise contained in the input image is adaptively reflected in a quantization matrix.

Hereinafter the structure and operation of the apparatus for encoding moving pictures according to a preferred embodiment of the present invention will be described in detail with reference to .

The apparatus of includes a discrete cosine transfer unit a quantization unit Q a variable length coding unit VLC an inverse quantization unit IQ an inverse DCT unit IDCT a frame memory unit and a motion estimation and compensation unit which correspond to the DCT unit the quantization unit the VLC unit the inverse quantization unit the inverse DCT unit the frame memory and the motion estimation and compensation unit respectively of the encoding unit of . In addition the apparatus further includes a noise estimation unit a quantization weight matrix determination unit and a quantization weight matrix storage unit .

Since the DCT unit the inverse DCT unit the frame memory unit and the motion estimation and compensation unit serve the same functions as their respective counterparts of their description will not be repeated.

The quantization weight matrix determination unit determines a quantization weight matrix corresponding to a predetermined macroblock based on a noise variance value received from the noise estimation unit and the predetermined macroblock s variance value received from the motion estimation and compensation unit . Thereafter the quantization weight matrix determination unit sends index information corresponding to the determined quantization weight matrix to the quantization weight matrix storage unit and the VLC unit .

Hereinafter a method of determining a quantization weight matrix corresponding to the predetermined macroblock based on received from the noise estimation unit and received from the motion estimation and compensation unit will be described in detail.

As described above with reference to Equation 8 and F k l is determined by Equation 7 . Once F k l is determined the DCT coefficient V k l of an 8 8 block is multiplied by F k l and the result of the multiplication k l is divided by a predetermined quantization weight matrix during a quantization process.

The apparatus of integrates the process of multiplying F k l by the DCT coefficient V k l and the process of dividing k l by the quantization weight matrix into a single process and performs the single process. In other words if a location component of k l of a quantization weight matrix QT is represented by Q k l then a location of k l in a new quantization weight matrix QT is Q k l F k l .

In the present embodiment by integrating the two separate processes into a single process a plurality of F matrices obtained using and are computed in advance and then the new quantization weight matrix QT is then computed using the plurality of F matrices and then is stored in the quantization weight matrix storage unit .

In addition in the present embodiment five new quantization weight matrices obtained using and are stored in the quantization weight matrix storage unit . Once and are determined 

For example if quantization weight matrices stored in the quantization weight matrix storage unit are classified into five different types according to

The quantization weight matrix storage unit transmits a quantization weight matrix corresponding to the index information received from the quantization weight matrix determination unit to the quantization unit and the inverse quantization unit .

The quantization unit quantizes the predetermined macroblock using the quantization weight matrix received from the quantization weight matrix storage unit .

The inverse quantization unit inversely quantizes the predetermined macroblock using the received quantization weight value.

The VLC unit carries out VLC on input image data quantized by the quantization unit and inserts the index information of the quantization weight matrix received from the quantization weight matrix determination unit into a macroblock header.

In the present embodiment the index information of the corresponding quantization weight matrix is inserted into the macroblock header and the macroblock header is transmitted. If there are ten quantization weight matrices stored in the quantization weight matrix storage unit then 4 bit data is required for each macroblock.

Adjacent macroblocks are supposed to have similar image characteristics and there is supposedly a correlation among their index values. Therefore a difference between an index value of one macroblock and an index value of an adjacent macroblock may be used as index information. The amount of index information to be transmitted can be considerably reduced in cases where a single quantization weight matrix is applied to an entire sequence.

In the present embodiment a plurality of quantization weight matrices stored in the quantization weight matrix storage unit should also be stored in a decoding unit. It may also be possible to use a plurality of quantization weight matrices transmitted to the decoding unit on a picture by picture basis using a picture extension header or transmitted to the decoding unit on a sequence by sequence basis using a sequence extension header.

As described above it is possible to remove noise from an input image and enhance the efficiency of encoding the input image by adaptively applying a quantization matrix to each macroblock in consideration of a level of noise contained in the input image.

It is also possible for a user to arbitrarily determine quantization weight matrices. In the present embodiment noise removal has been described as being performed on a Y component of an input image block in a DCT block. However the noise removal can also be applied to a U or V component of the input image block in which case additional quantization weight matrices are required exclusively for the U and V components of the input image block.

More specifically among various characteristics of an input image the edge characteristics of each macroblock of the input image are taken into consideration in the present embodiment.

Referring to an apparatus for encoding moving pictures according to another preferred embodiment of the present invention includes a DCT unit a quantization unit a VLC unit an inverse quantization unit an inverse DCT unit a frame memory unit and a motion estimation and compensation unit which correspond to the DCT unit the quantization unit the VLC unit the inverse quantization unit the inverse DCT unit the frame memory and the motion estimation and compensation unit respectively of the encoding unit of . In addition the apparatus further includes a quantization matrix determination unit and a quantization matrix storage unit . Since the DCT unit the inverse DCT unit the frame memory unit the motion estimation and compensation unit and the VLC unit serve the same functions as their respective counterparts of their description will not be repeated.

The quantization matrix determination unit selects an optimal quantization matrix for each macroblock in consideration of the characteristics of an input image and then transmits index information of the selected quantization matrix to the quantization matrix storage unit and the VLC unit .

The quantization matrix determination unit takes the edge characteristics of each macroblock into consideration as a benchmark for selecting one out of a predetermined number of quantization matrices.

Hereinafter a method of selecting a quantization matrix in consideration of the edge characteristics of a macro block will be described in detail.

In a case where a predetermined macroblock of an input image is an intra block the size and direction of an edge in each pixel of the predetermined macroblock are computed using such an edge detector as a sobel operator. The sobel operation can be represented by Equation 12 .

The quantization matrix determination unit calculates the magnitude of a vertical edge and the magnitude of a horizontal edge using Equation 12 above and calculates the intensity and direction of an edge of the predetermined macroblock using the magnitude of the vertical and horizontal edges. Thereafter the quantization matrix determination unit selects one from among a predetermined number of quantization matrices in consideration of the intensity and direction of the edge of the predetermined macroblock and encoding efficiency. In other words in a case where the predetermined macro block includes a horizontal or vertical edge the quantization matrix determination unit selects a quantization matrix that can enable quantization in full consideration of the horizontal or vertical edge of the predetermined macro block.

In a case where the predetermined macroblock is an inter block the intensity and direction of an edge included in the predetermined macroblock can also be obtained using such an edge detector as a sobel operator.

In the present embodiment a sobel detector is used for computing the intensity and direction of an edge included in the predetermined macroblock. However a spatial filter such as a differential filter or a Robert s filter can also be used for computing the intensity and direction of the edge included in the predetermined macroblock.

In addition in the present embodiment a quantization matrix is selected in consideration of the edge characteristics of the predetermined macroblock. However other characteristics of the predetermined macroblock that can affect encoding efficiency or the quality of an output image can be taken into consideration in adaptively selecting an optimal quantization matrix for the predetermined macroblock.

The quantization matrix storage unit selects a quantization matrix based on the index information received from the quantization matrix determination unit and transmits the selected quantization matrix to the quantization unit and the inverse quantization unit .

The quantization unit carries out quantization using the quantization matrix received from the quantization matrix storage unit .

The inverse quantization unit carries out inverse quantization using the quantization matrix received from the quantization matrix storage unit .

The VLC unit carries out VLC on quantized input image data received from the quantization unit and index information of a quantization matrix corresponding to the predetermined macroblock received from the quantization weight matrix determination unit . The index information is inserted into a macroblock header.

In the present embodiment index information of a quantization weight matrix corresponding to a predetermined macroblock is inserted into a header of the predetermined macroblock and then transmitted. A difference between an index value of one macroblock and an index value of an adjacent macroblock may be used as index information.

In the present embodiment a plurality of quantization weight matrices stored in the quantization matrix storage unit are also stored in a decoding unit. However it may also be possible to use a plurality of quantization weight matrices transmitted to the decoding unit on a picture by picture basis using a picture extension header or transmitted to the decoding unit on a sequence by sequence basis using a sequence extension header.

The variable length decoding unit carries out variable length decoding on an input stream extracts index information of a quantization weight matrix corresponding to a predetermined macroblock of the input stream from a header of the predetermined macroblock and outputs the extracted index information to the quantization weight matrix storage unit .

The quantization weight matrix storage unit outputs a quantization weight matrix corresponding to the index information received from the variable length decoding unit to the inverse quantization unit . The quantization weight matrix storage unit stores a plurality of quantization weight matrices which are classified according to the characteristics of an input image processed by an encoding unit for example a noise variance value as a ratio between an input image variance value and the edge characteristics of the input image.

The plurality of quantization weight matrices stored in the quantization weight matrix storage unit can be transmitted on a picture by picture basis using a picture extension header or transmitted to the decoding unit on a sequence by sequence basis using a sequence extension header. The plurality of quantization weight matrices are transmitted from the variable length decoding unit to the quantization weight matrix storage unit as marked by a dotted line in .

The present invention can be applied to different types of methods and apparatuses for encoding and or decoding moving pictures such as MPEG 1 MPEG 2 or MPEG 4. In addition the present invention can be realized as computer readable codes written on a computer readable recording medium. The computer readable recording medium includes any type of recording device on which data can be written in a computer readable manner. For example the computer readable recording medium includes ROM RAM CD ROM a magnetic tape a hard disk a floppy disk flash memory an optical data storage and a carrier wave such as data transmission through the Internet . In addition the computer readable recording medium can be distributed over a plurality of computer systems which are connected to one another in a network sort of way so that computer readable codes are stored on the computer readable recording medium in a decentralized manner.

As described above the methods of encoding and or decoding moving pictures according to the embodiments of present invention a quantization matrix is adaptively applied to each macroblock of an input image in consideration of the characteristics of the input image. Thus it is possible to enhance the efficiency and performance of encoding the input image.

Although a few embodiments of the present invention have been shown and described it would be appreciated by those skilled in the art that changes may be made in this embodiment without departing from the principles and spirit of the invention the scope of which is defined in the claims and their equivalents.

