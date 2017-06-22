---

title: Point load sensor
abstract: A point load sensor measures compressive forces exerted on the outside of a ring in diametric compression irrespective of the direction of application of the force. The sensor consists of a ring with strain gauges placed in a configuration to measure the circumferential strain at two positions on the ring ninety degrees apart resulting from bending of the ring as the ring is loaded in diametric compression. The two measurements are corrected and combined to recover the compressive force on the ring. A method for calibrating and resolving the compressive force does not require the angle of loading or sensor orientation as an input, thus allowing resolution irrespective of the direction of the compressive force.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09176015&OS=09176015&RS=09176015
owner: The United States of America as represented by the Secretary of the Navy
number: 09176015
owner_city: Washington
owner_country: US
publication_date: 20120208
---
The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties thereon or therefore.

The present invention relates to load sensors and more particularly to a sensor for measuring forces exerted on a ring in diametric compression.

During the handling of cabling piping or other tubular materials forces are applied to the material by the handling system that can be difficult to measure. As an example thin line sonar arrays that are towed behind submarines.

As the arrays are deployed from and retrieved the array passes through various parts of the handling system. Any problems with the towed array handling system may result in the application of unacceptable forces to the array that can damage the array.

When using the known Guide To Measurement Module GTMM squeeze forces on towed arrays are measured. Specifically the measurement module contains a sensor in the form of a ring instrumented with strain gauges. The placement of the gauges within the ring provides two outputs proportionate to the applied force. These outputs are combined using a vector sum approach.

However the design of this sensor does not take into consideration the variation of strain inside a ring under diametric compression. Without this consideration the placement and wiring of the strain gauges as well as the means of combining the outputs can result in orientation errors greater than thirty percent.

What are therefore needed is a system and method of use for measuring compressive forces exerted on tubular material during handling. The system needs to account for the mechanics of strain inside a ring under diametric compression.

It is therefore a general purpose and primary object of the present invention to provide a sensor for measuring compressive forces exerted on tubular material during handling.

It is a further object of the present invention to provide a system and method of use that incorporates the mechanics of strain within the sensor when determining such compressive forces.

It is a still further object of the present invention to provide a system and method of use for reducing sensor orientation errors.

To attain the above and other objects described above a sensor is provided which measures compressive forces exerted on the outside of a ring in diametric compression irrespective of the direction of application of the force. The sensor comprises a ring with strain gauges placed in a configuration to measure the circumferential strain at two positions on the ring at ninety degrees apart resulting from bending of the ring as the ring is loaded in diametric compression .

The two strain measurements are corrected and combined to recover the compressive force on the ring. The sensor employs a method for calibrating and resolving the compressive force that does not require the angle of loading or sensor orientation as an input thereby allowing resolution irrespective of the direction of the compression. Accordingly the method results in the reduction of sensor orientation errors.

In one embodiment a method for calibrating a sensor ring measuring an unknown diametric compressive force P includes applying a known load P at a plurality of orientations about the sensor ring. A set of first and second output voltages Vand V are measured across respective first and second output connections from respective first and second strain gauges of pairs of biaxial strain gauges circumferentially spaced apart on the ring.

Values for slopes mand m and for offsets band b are initialized with the slopes being assumed as 1 and the offsets as 0 and a corresponding set of parameters Vand V are calculated based on the relationships V mVband V mV b. A set of uncorrected loads UP is initially calculated based on the relationship derived from the strain relations for a thin ring 

The standard deviation for the set of uncorrected loads is obtained. The values of one or more of the slopes or offsets are iteratively varied until the standard deviation of UP is minimized.

The relationship for UP can be generalized to UP A V V right arrow over B V V C V V right arrow over B V V C V V . The coefficients A B and C can be initialized assuming their corresponding values based on the assumption of a thin ring and iteratively varied along with the slopes and offsets thereby allowing generalization to rings that may not be thin.

Once the standard deviation is minimized the load P can be varied at a few sensor orientations to obtain a set of Pversus UP values. A best fit curve for the set of Pversus UP values load can be determined.

In one embodiment a sensor ring calibration includes the steps of calibrating the sensor ring for load orientation and calibrating the sensor ring output for deviations from linearity. Calibrating the sensor ring for load orientation can further include minimizing a standard deviation of an uncorrected load UP wherein 

Calibrating a sensor ring for deviations from linearity can further include varying the load P applied to the sensor ring at a few sensor orientations and determining a best fit curve for the set of Pversus uncorrected load UP values.

Calibrating the sensor ring for load orientation can further include minimizing a standard deviation of an uncorrected load UP wherein right arrow over right arrow over 2 

Referring to there is shown a sensor ring with an inner radius R and a thickness t. Diametrically opposed forces P are applied to the sensor ring such that the sensor ring is placed in diametric compression. As is known in the art there will be a bending moment through the thickness t of the sensor ring at all points from this type of loading.

Considering a bending moment M at some angle it is known in the art that the following relationship holds for a thin ring 

However the sensor ring will measure some voltage V that is directly related to strain through a constant C. Therefore the relationship becomes 

The constant relating V to the load P can be determined during sensor calibration. The problem remains that since the direction of the load on sensor ring is arbitrary and unknown there is not enough information in the above equation to determine V.

Thus it is necessary to measure strain in at least one other direction. For purposes of derivation and illustration but not limitation the strain can be measured at locations circumferentially ninety degrees apart. Those of skill in the art will recognize that separations other than ninety degrees can be used. However the use of ninety degrees separations simplifies the derivations of the equations described hereinafter.

For the illustrative embodiment of but not limitation strain gauges are mounted on inner surface of the sensor ring and are spaced circumferentially ninety degrees apart. Those of skill in the art will also recognize that the methods described hereinafter are equally applicable to strain gauges located on outer surface of the sensor ring or within thickness t of the sensor ring.

Referring also to there is shown a developed view of strain gauges illustrating connections or wiring between the gauges. For clarity only some of connections are designated in . The developed view of corresponds to a panoramic view of inner surface of sensor ring from match line A A about the circumference and back to match line A A.

As is typical of strain gauges used in the art each gauge has two grids orthogonal to one another. For ease of further discussion the grids are labeled through . Grids and are aligned in the circumferential direction of the sensor ring and grids and are aligned in the axial direction of the sensor ring. Each gauge is wired to another gauge displaced circumferentially 180 i.e. grids are connected to grids and grids are connected to grids . Power is provided to grids and and returned from grids and . Any combination of these four strain gauges may be rotated 180 degrees and installed upside down.

Since strain inside the sensor ring is symmetric the strains that are measured 180 circumferentially apart from one another will be equal. Accordingly the gauges that are separated by 180 measure the same strain and are wired so that their outputs are added. The result is a circuit that is sensitive to circumferential strain but not to temperature or hydrostatic pressure. The two pairs of the strain gauges make for two circuits sensitive to strain at points inside the sensor ring separated by ninety degrees.

Referring to Vis taken across grids and while Vis taken across grids and . The unknowns are the angle and the V quantity. It remains simply to solve the above simultaneous equations so as to determine the theoretical voltage V in terms of the measured voltages Vand V .

By moving those terms under a square root to the other side of the equation squaring both sides of the equation and then collecting like terms on one side of the resultant equation Equation 13 can be rewritten as 

As is known in the art quadratic Equation 16 has two possible solutions. Using Equations 6 and values for Vand Vare generated given many values for at small intervals. The generated values for Vand Vare plugged into each of the two solutions to Equation 16 . The one solution that produces real numbers for all values of Vand Vis determined to be the correct solution of Equation 16 . Based on the above the correct solution is 

As stated earlier V Equation 17 is directly proportional to the point load of P. Ideally V can be multiplied by some factor in order to recover the point load of P. However this is based on the output voltages of the sensor ring both reading a value of zero with no load on the gauges and both pairs of gauges having the same sensitivities to load .

In actuality it is not always possible to zero Wheatstone bridge circuits . Typically the outputs have different offset voltages due to small differences in the construction and bonding of each strain gauge . The offset voltages have a tendency to drift over the life of the sensor requiring periodic corrections. In addition the sensitivities of the bridge circuits are not identical due to small misalignments of the strain gauges and differences in their bonding.

The above effects can be compensated for by correcting the voltages as in the following equations 18 . 19 By choosing proper values for correction slopes mand m and offsets band b the results can be used in Equation 17 to recover the point load directly 

For orientation calibration a known point load P can be applied to the sensor ring and the output voltages Vand Vcan be measured. Load Pcan be applied at many different orientations to obtain a set of paired values for Vand V. For example applying load Pto the sensor ring every fifteen degrees yields twenty four paired values for Vand V.

Initial values for correction slopes m m 1 and correction offsets b b 0 are chosen such that V Vand V V. The paired values are plugged into Equation 20 to produce a corresponding set of values for UP. The standard deviation of the set of values for UP can be determined which is a measure of the sensor ring error due to varying orientation of the sensor ring when loaded. The standard deviation is minimized by iteratively varying the calibration coefficients m m band b.

By minimizing the standard deviation the resulting set of values for UP contains minimal error. However the resulting values are not necessarily equal to the point load P. To obtain the point load P the calibration coefficients can be scaled by a common factor with no effect on the orientation error.

Given the previously determined coefficients m m band b the sensor ring can be loaded with various point loads P and a plot of UP versus P can be obtained. Ideally the resultant curve will be linear and a straight line could be drawn through all points. A linearity error can be minimized by applying a best fit curve to the data and correcting UP using these results. As an example but not for limitation a linear correction can be applied resulting in the following 21 with coefficients M and Y determined from the best fit linear curve.

In many applications the sensor ring is exposed to harsh environments and abrasive handling. To protect the sensor ring and the gauges a layer of hard epoxy or similar material can be applied over strain gauges as shown in phantom by coating in . While the protective coating allows sensor ring to remain operational during extreme conditions the coating causes the orientation error of the sensor ring to increase.

As described previously herein Equation 20 is derived from strain equations for thin rings wherein the strain is measured inside the ring. The coating over the strain gauges results in an effectively thicker sensor ring . In addition with the strain gauges embedded in the coating strain is no longer being measured on the inside surface . Both these factors contribute to the increased orientation error.

However the general form of Equation 20 can still apply. As can be seen from examination of Equation 20 there are a large number of constants. As such Equation 20 can be rewritten as follows right arrow over right arrow over 21 

Using Equation 22 calibration now can be accomplished by using the previously described initial values for correction slopes m m 1 and correction offsets b b 0 and by using initial values for the coefficients A B and C of A 4 B 4 and C 4 1 8 . The calibration technique is unchanged except that the coefficients A B and C must now also be determined using standard iteration tools. Accordingly Equations 18 19 22 and 11 are the basis for the design and calibration of the sensor ring .

Referring now to there is shown a block diagram of method for designing and calibrating the sensor ring . With the sensor ring fabricated in accordance with the design described hereinbefore with respect to a known load P is applied to the sensor ring as shown at block .

At block values for Vand Vare obtained from the outputs of the two pairs of the strain gauges . The obtained values are added to a set of values block . If the set is not full as determined at block the orientation of load Pis changed at block and returning to block load P at the new orientation is applied to the sensor ring .

As described previously a full set of values would include load Papplied at a plurality of orientations so as to provide values for Vand Vrepresentative of a full range of orientations about the sensor ring . The specific number of orientations and their distribution about the sensor ring can vary depending on user preference.

If block determines that the set of values is full then initial values for slopes mand m offsets band b and coefficients A B and C are chosen at block . Values for V Vand UP are obtained at block from Equations 16 17 and 20 respectively for each pair of outputs Vand V . Once values for V Vand UP are obtained for each pair of values for Vand V as determined at blocks and the standard deviation of UP is obtained at block .

Values for slopes mand m offsets band b and coefficients A B and C are iteratively varied and new values for V Vand UP are obtained until the standard deviation is minimized as shown at blocks and . Once the standard deviation of UP is minimized a correction for linearity can be obtained by plotting UP versus P.

If a plot has not been populated as determined at block load Pis varied block and this new load Pis applied to the sensor ring returning to block . This process is repeated until a plot of UP versus Pis populated sufficiently to determine a best fit curve at block e.g. Equation 21 .

Referring now to there is shown a block diagram of method for using the sensor ring to measure forces exerted on the sensor ring. Once calibrated as described with respect to an unknown force P applied to sensor ring block results in strain gauges of sensor ring providing outputs Vand V block . Using the slope offset and coefficient values determined from the method values for V Vand UP are obtained from Equations 18 19 and 22 respectively block . The best fit curve as determined from the method is used to obtain the value of force P from the value determined for UP block .

What have thus been described are systems and methods for the design and calibration of a sensor ring for measuring compressive forces exerted on tubular material during handling of the material. Pairs of strain gauges are placed in the ring in a configuration to measure the circumferential strain at two positions on the ring ninety degrees apart resulting from bending of the ring as it is loaded in diametric compression . The strain measurements are corrected and combined to recover the compressive force on the ring.

A method for calibrating and resolving the compressive force is independent of the angle of loading or sensor orientation as an input. Accordingly resolution of the force from the strain gauge readings is possible irrespective of the direction of the compressive force. The method further results in the reduction of sensor orientation errors.

As described previously herein current sensor designs suffer from large orientation errors typically greater than thirty degrees one standard deviation . The above described design and calibration reduce the orientation error to less than ten percent two standard deviations. The reduction in error can be ascribed to a number of factors including configuring the strain gauges to measure circumferential strain at the ring at points ninety degrees apart from one another. Additionally the equations derived and refined herein that combine the measured strains to recover the point load as well as the method of calibration used to determine the optimum coefficients for use in the equations lead to further error reductions.

It will be understood that many modifications and variations of the present invention may become apparent in light of the above considerations. For example and as previously noted many possible configurations and types of strain gauges can effectively measure strain inside a ring at two points. Any of these configurations can also be used for this sensor. Further strain can be measured at two points on the outside of the ring or even at points throughout the thickness of the ring.

Also the ring comprising the sensor may be any size or thickness. Although strain is measured at two points ninety degrees apart strain may also be measured at additional points to reduce error. For example a sensor can measure strain every forty five degrees and have multiple outputs. One pair of gauges can be calibrated separately from the other pair of gauges but the point loads determined from each can be averaged to improve results and reduce error. The sensor is also equally applicable to tensile versus compressive loads on the ring.

It will be understood that many additional changes in the details materials and arrangement of parts which have been herein described and illustrated in order to explain the nature of the invention may be made by those skilled in the art within the principles and scope of the invention as expressed in the appended claims.

