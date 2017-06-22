---

title: Wide band embedded armor antenna using double parasitic elements
abstract: For use with an armored vehicle, a wideband embedded armor antenna is provided. The antenna includes an armor layer mounted to the armored vehicle. A driven dipole is mounted between the armor layer and the vehicle, the dipole operating in the UHF band. A first parasitically driven dipole is mounted on the outside of the armor layer. A second parasitically driven dipole is mounted between the driven dipole and the vehicle. A feed for the driven dipole is provided which does not pierce the armor layer.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09300053&OS=09300053&RS=09300053
owner: BAE Systems Information and Electronic Systems Integration Inc.
number: 09300053
owner_city: Nashua
owner_country: US
publication_date: 20120801
---
This Application claims rights under 35 USC 119 e from U.S. Application Ser. No. 61 522 751 filed Aug. 12 2011 the contents of which are incorporated herein by reference.

The invention was made with United States Government assistance under Contract No. W15P7T 09 C S485 awarded by the US Army. The United States Government has certain rights in the invention.

This invention relates to an antenna utilized on armored vehicles and more particularly to an armor embedded parasitically fed antenna system.

As described in U.S. patent application Ser. No. 13 473 132 filed May 16 2012 incorporated herein by reference it is desirable to provide a thin structure for an antenna embedded in an armor panel and more particularly to provide a parasitic element on top of the armor layer so that when driving the antenna there are no apertures in the armor which would degrade performance. In one embodiment the aperture less embedded antenna system includes a direct fed dipole on the underneath side of the armor layer such that the armor layer is not pierced. There is an identical dipole on the top of the armor layer that is parasitically fed by the driven dipole. In one embodiment the dipoles are in the form of bowties.

As described in the above identified patent application it is desirable to replace antennas such as whip antennas on tanks armored vehicles and the like with broadband antennas that are conformal to the vehicle itself.

Having a forest of antennas that extend from the armored vehicle is undesirable because they are susceptible to damage and attack. It is therefore desirable to be able to provide an antenna system which is embedded in the armor such that the armor protects the embedded antenna both against explosive attacks and ballistic penetration while at the same time eliminating the need for antenna whips and the like which are easily blown off with explosive charges thereby precluding communication with the vehicle.

It is noted that the thin structure of present armor panels presents the greatest challenge to antenna design. Whether the panel is metal backed itself or is mounted on a metal vehicle the close proximity of a conductive surface to a radiating element creates a ground plane that is too close to the element. As will be appreciated in traditional antenna design the ground plane is spaced at least a quarter wavelength away from any driven element. However when dealing with armor for vehicles such as tanks and the like the spacing between the ground plane and the driven element of the antenna is on the order of hundredths of a wavelength.

While initially thought that this limitation would be a disqualifying factor in the antenna design it has been shown that a thin antenna structure can be created which does not rely on deep cavities behind the elements. However it has been found that the close spacing described in the above patent application as well as other factors limits bandwidth and gain and results in non optimal VSWR across the desired bandwidth for instance between 225 GHz and 450 GHz.

Note deep cavity structures have been described in U.S. Pat. No. 6 833 815 which relates to Cavity Embedded Meanderline Loaded Antennas. In this patent the antenna described is a conformal antenna which is cavity backed.

In one embodiment of this Cavity Embedded Meanderline Antenna a bowtie dipole is utilized with the distal ends of the dipole being coupled to surrounding metal utilizing a meanderline structure. The question becomes how one can better configure such dipole antenna into a thin structure for use with at armor plates.

While a single parasitic driver element combination has been used in a thin stacked element array as an embedded armor antenna it has been found that the thin stacked element array achievable using a driven bowtie dipole to the inside of an alumina tile armor plate and a parasitic element on the outside of the armor plate can be improved in terms of boresight gain and VSWR by placing a bottom parasitic element between the driven bowtie and the body of the vehicle in which the subject antenna is embedded. Further improvement is achieved by spacing the bottom or inside parasitic antenna from the vehicle body to form an air gap.

In order to achieve satisfactory embedded antenna performance in the subject invention bowtie dipoles are used both as the directly driven element and for both parasitically driven dipole elements. Moreover along with the air gap each bowtie element is provided with a resistor between the dipole elements the values of which optimize antenna performance. Additionally the lengths of the driven element and the parasitical elements are adjusted to maximize gain minimize VSWR over a wide bandwidth and increase efficiency with the gain being greater than 1 dBi over the entire bandwidth of the antenna in one embodiment 225 450 GHz.

In one embodiment a plurality of armor embedded panels each carrying the driven dipole and the two parasitically driven elements are located side by side for instance on a tank and may driven in phase or may be phased to provide a sharp antenna lobe in a given direction. Thus the gain in a particular direction may be increased with traditional antenna steering. As will be appreciated for a steerable beam one can obtain increased gain in a particular pointing direction.

With a vertically polarized four panel array the gain in the horizontal direction has been found to exceed 1 dBi across the entire bandwidth. It has also been found that with the dual parasitic elements and the air gap the VSWR across at least the 225 450 MHz band can be made to be less than 3 1.

In summary an extremely thin embedded antenna for an armor carrying vehicle utilizes a dipole driven element to the inside of the armor plate and a pair of parasitically driven dipole elements to either side of the driven element with the interior or back parasitic element and an air gap providing improved forward gain and antenna matching characteristics over the single parasitic element embedded antennas described in the above patent application.

Prior to discussion of the specifics of the subject antenna system it is noted that the thin structure of the armor panel is the greatest challenge to the antenna design. Whether the panel is metal backed itself or is mounted on a metal vehicle the close proximity of a conductive surface creates a groundplane to the radiating element. A conventional design would have the groundplane spaced at least a quarter wavelength away. However one is typically dealing with spacing more on the order of hundredths of a wavelength. It was found that this was not a disqualifying factor in antenna designs and an armor embedded antenna with an outside parasitic element provided adequate results. The present antenna which is a modification of the original design improves on this original design by adding an additional parasitically driven element.

Referring now to in the prior art a tank or other armored vehicle may be provided with a number of whip antennas which extend above the vehicle and which are tuned to various frequency bands.

The problem with such a configuration is that the whips are extremely vulnerable to explosive destruction as well as being torn off the vehicle by overhead limbs and the like. Moreover there is considerable cross talk or interference between the antennas.

It will be appreciated that in order to cover the bands of interest for communication with such a vehicle a number of bands are required. It would be desirable to have communication antennas for such vehicles that operate in a 225 MHz to 425 MHz band. However antennas that are wideband enough do not exist other than in whip form.

Referring now to it is the purpose of the subject invention to provide a conformal embedded antenna structure for vehicle in which embedded antenna structures are provided in plates and that when appropriately phased by a phasing network result in an antenna lobe which as illustrated has a 180 azimuthal coverage. Providing the tank with embedded antenna plates on both sides provides a 360 coverage.

The antennas are capable of being used in a transmit and receive mode such that a transceiver can listen for signals in 180 about the horizon or can transmit signals from the transceiver through the panel embedded antennas with an antenna pattern such as that shown by reference character .

The challenge therefore is to be able to provide a panel embedded thin antenna structure that provides close to 180 coverage per side and yet has an ultra wideband coverage characteristic and improved gain and efficiency.

In order to do so and referring now to a driven dipole element is surrounded by parasitic elements and in the form of bowtie dipoles with the bottom parasitic element improving the operation of the original antenna. Here a pair of dipoles and are located to either side of an alumina tile armor layer such that the dipole is driven by a transmission line having conductors and which do not pierce the armor layer tiles. The result is an unapertured armor layer in which energy is coupled to an inner bowtie without having to provide holes in the armor plate.

Bowtie dipole is parasitically driven by bowtie dipole to provide a certain amount of gain. However it was found that this gain could be improved by locating a bottom parasitic dipole between driven element and the vehicle along with providing an air gap between the bottom parasitic dipole and the metallic vehicle body.

Referring now to the construction of the subject parasitic embedded antenna is as follows. Going from the base one has a woven glass S glass armor layer on top of which is provided a thin substrate of RO4003 material. The bottom parasitic dipole is patterned onto the underneath side of substrate with the driven bowtie patterned on the top side of this thin substrate.

On top of the thin substrate is a ceramic layer on top of which is a thin layer of UltraLam 3850 or a polymide with the top parasitic element patterned on the underside of layer . Thereafter a so called nuisance layer is placed on top of the structure.

Referring to an optimal configuration for the subject antenna shows that the driven element top parasitic element and bottom parasitic element are each provided with a resistor between the elements of associated dipoles with the resistors provided with values that optimize performance.

Here it can be seen that driven element is provided with a resistor between the feedlines and . Note that these resistors can take the form of thin film resistors. In the optimal case the length of the driven element is 12.9 inches whereas the value of the resistor between feedline elements and is 610 ohms.

Top parasitic element has a resistor across dipole elements and with the length of the top parasitic element being 8.2 inches and with the value of resistor being 940 ohms.

Referring to the bottom parasitic element this is composed of dipole elements and with a resistor therebetween. The optimal length of the bottom parasitic element is 10 inches whereas the value of resistor is 485 ohms.

Referring to the effect of providing the bottom parasitic element along with resistor is a capacitance coupling between driven element and dipole elements and .

It is purpose of this capacitance effect is to lower the operating frequency of the antenna such that the parasitic element on the bottom acts like an RC circuit to extend the lower band edge of the antenna down to 225 GHz. It also provides a VSWR less than 3 1 with the length of the bottom parasitic element governing capacitance coupling.

It is noted that by variation of the value of resistor and the lengths of the bottom parasitic element one can vary the capacitance effect and thus optimize the VSWR and gain of the antenna.

It is noted that the lower parasitic element is shorter than the driven element as is the top parasitic element.

Referring now to a cross section the subject antenna is illustrated in which the layers are built up from the vehicle body in this case an aluminum plate behind which a spall liner is located.

Woven glass armor layer has an underside spaced from the top side of the aluminum plate ground plane by a distance of 2 inches to 2 inches. It has been found that in addition to the capacitance effect described in the air gap or air space provides better isolation from the ground plane at the same time improving gain and VSWR over a 2 1 bandwidth.

As illustrated by arrow the thickness of the woven glass armor layer is approximately 1 inch with the bottom parasitic element patterned onto the bottom of substrate . Here the substrate has a thickness of 0.060 inches. Note driven element is patterned on the top surface of this thin substrate.

Ceramic armor in the form of a ceramic armor layer is positioned on top of the driven elementand in one embodiment has a thickness of 0.75 inches.

On top of the ceramic armor layer is a thin dielectric substrate with the top parasitic element patterned on the underneath side of this substrate. Thereafter nuisance layer here an epoxy cover is placed on top of the structure to complete the antenna.

As mentioned hereinbefore the originally designed armor embedded antenna did not have an optimal bandwidth or VSWR over the entire 225 GHz to 450 GHz band. It was found that the prior antenna while operational was not as efficient as it could be in. This resulted in reduced radiated power due to the fact that radiation was reflected back towards the generator of the RF energy. While lossy epoxy material was placed on the antenna to reduce the reflected power the epoxy material did not work sufficiently well.

The solution to improvement of the originally designed antenna was to provide the aforementioned bottom parasitic element which acts like an RC circuit to provide additional capacitance from the parasitic element to the driven element. Secondly the aforementioned resistors were placed at the junctions of the dipole elements. Thirdly the lengths of the parasitic elements were adjusted with respect to the driven element to change the capacitance and therefore optimize the VSWR and gain of this antenna. Fourthly further optimization was provided by the aforementioned air gap to obtain additional separation from the ground plane for avoiding shorting of the antenna as well as avoiding poor impedance matching and poor bandwidth. Moreover the air gap increases ballistic penetration resistance.

It is noted that the gain throughout the bandwidth has been shown to be greater than 1 dBi and significantly better across the upper portion of the band.

The benefit of the bottom parasitic and other elements of this antenna includes a better gain over the bandwidth better VSWR and no deleterious effect on the ballistic characteristics of the antenna.

Note bowtie configurations are utilized to broaden the bandwidth because impedance does not markedly change with frequency.

The above operation is confirmed in in which VSWR is graphed against frequency. Note that the dotted line indicates the goal of having the VSWR under 3 1 with the diagram illustrating that the average VSWR is around 2 1.

Referring to what is shown is a graph of the swept gain at the boresight versus frequency with the goal being better than 0 dBi gain. Here it can be seen that the gain for the subject antenna at the low end is above 1 dBi and is considerably above 0 dBi for the remainder of the bandwidth.

While the present invention has been described in connection with the preferred embodiments of the various figures it is to be understood that other similar embodiments may be used or modifications or additions may be made to the described embodiment for performing the same function of the present invention without deviating therefrom. Therefore the present invention should not be limited to any single embodiment but rather construed in breadth and scope in accordance with the recitation of the appended claims.

