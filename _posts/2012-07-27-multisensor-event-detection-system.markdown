---

title: Multi-sensor event detection system
abstract: Systems and methods to determine and ascertain the occurrence of an event are provided. The event can manifest its presence through transient signatures that alter short or long term background sensor registered signals. The system can include multiple sensors, one or more data recorders and data reporting devices. Event data from each sensor is collected, recorded and reported. Data from the various sensors is correlated to triangulate or otherwise localize the occurrence of an event. The sensors can be incorporated on a single device or can be a distributed set of independent sensors on separate devices that share their information with the data collection system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08982670&OS=08982670&RS=08982670
owner: The United States of America as represented by the Secretary of the Navy
number: 08982670
owner_city: Washington
owner_country: US
publication_date: 20120727
---
The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties.

The present invention relates to event detection. More particularly the present invention relates to systems and methods to determine and ascertain the occurrence of an event that manifests its presence through transient signatures that alter short term and long term background sensor registered signals.

Currently a number of event detection methods rely on human observation. As an illustrative example current minesweeping systems are towed by a manned platform such as a helicopter or surface ship. Since there is some level of human situational awareness direct observation is used to recognize if the sweep system being employed has indeed swept a mine or not. Accordingly tactical memorandums and concept of operation documents for these systems explicitly state that those manning the platform shall watch for a plume or explosion when sweeping or neutralizing mines.

The fundamental concept of mine hunting and sweeping is shifting from this perspective to an entirely unmanned operation. Larger countermeasure ships and helicopters are slated to be retired in favor of smaller unmanned systems. For mine hunting systems detailed methods of data collection and post mission analysis PMA are prescribed. A human operator downloads and reviews every sonar image or other data that the system collects.

For mine sweeping however PMA has been neglected due to the use of manned platforms and human observations as described previously. Current unmanned sweep systems record when the system is energized and where it is. However there are no provisions for recording whether or not a mine firing has occurred. Further if a mine firing has occurred there are no provisions for recording where the mine firing occurred.

Accordingly the judgment as to whether an area has been cleared of naval sea mines to an acceptable level has to rely on vague position and status data. Such vague data is inadequate for deciding whether to risk lives and assets in moving them through an area that may or may not be sufficiently cleared. Thus if an unmanned sweeping capability is desired there is a need for a multi sensor data collection system that can detect localize and report mine firings that have been actuated by an unmanned sweep system.

It is therefore a general purpose and primary object of the present invention to provide systems and methods to determine and ascertain the occurrence of an event that manifests its presence through transient signatures that alter short or long term background sensor registered signals. The system can include multiple sensors one or more data recorders and data reporting devices.

Event data from each sensor are collected recorded and reported. Data from the various sensors is correlated to triangulate or otherwise localize the occurrence of an event. The sensors can be incorporated on a single device or can be a distributed set of independent sensors on separate devices that share their information with the data collection system.

In one embodiment a method for detecting an event manifesting a plurality of characteristic transient signatures includes detecting one or more of the characteristic transient signatures correlating each of the detected signatures to confirm an occurrence of the event and correlating timing and location information of the detected signatures to determine a timing and location of the occurrence. Further the method can include displaying the occurrence and the timing and location of the occurrence.

The method can include correlating the detected signatures with historical event data to characterize the event and the method can also display the characterization of the occurrence. In detecting the signatures the method can include deploying one or more sensors attuned to detect one or more of the characteristic transient signatures. The method can also include the sensors transmitting the detected signatures to a processor for correlation.

In deploying the sensors the method can include conducting a sweep of an area of interest and forcing at least one occurrence of the event by said sweep. The method can also display an area where further occurrences of the event have been mitigated by the sweep. The sweep can be conducted by an unmanned mine sweeping platform wherein the event is the detonation of a mine.

In one embodiment a method of conducting a mine sweeping operation includes deploying an unmanned mine sweeping platform detecting a plurality of mine explosion characteristics correlating the detected mine explosion characteristics to confirm an occurrence of a mine explosion and determining a time and location of the mine explosion based on timing and location information associated with each of the detected mine explosion characteristics.

The method can include correlating the detected mine explosion characteristics with historical mine explosion data to characterize the mine explosion. Also the method can include displaying the mine explosion the timing and location of the mine explosion and the characterization of the mine explosion. Further the method can display an area where a further occurrence of one such mine explosion event is mitigated by the mine sweeping operation.

For illustration and ease of description but not for limitation the systems and methods are described herein relative to unmanned mine sweeping operations wherein the event occurrence to be ascertained is a mine firing or explosion event. Referring now to there is shown a schematic elevation view of system for detecting a mine explosion event. Unmanned platform is deployed at sea surface and sweeps an area of sea surface in order to detect and detonate mines that may be located beneath surface . Plume illustrates the detonation of one such mine .

Referring also to there is shown a diagrammatic representation of the known effects of detonating a mine . In addition to plume which is characterized by shock spray dome and gas bubble plumes above sea surface surface waves and air blast wave can be observed by sensors aboard platform . Further unmanned surface vehicle USV and unmanned air vehicle UAV can employ respective sensors and to also detect at surface and above surface effects of mine detonation.

As illustrated in the underwater effects of mine detonation include oscillating and migrating gas bubble bubble pulse shock wave and respective surface and bottom reflected shock waves and . Unmanned underwater vehicle UUV can deploy sensors to detect one or more characteristics of the underwater effects. Additionally one or both of USV and UUV can deploy respective towed array sensors and to also detect underwater effects. Other effects can also be observed such as possible radar signatures from parts of detonated mine and temperature anomalies from the explosion.

For ease of reference the various sensors and will be collectively referred to hereinafter as sensors . In addition to detecting explosion effects sensors include known timing and global positioning system GPS capabilities. The data collected by sensors can be transmitted to processing platform or processor . Platform correlates the data from sensors and based on the detected explosion effects from sensors determines if a mine explosion has occurred.

If so processing platform utilizes the timing and GPS information from sensors to determine the timing and GPS location of the explosion event. Additionally using techniques known in the art time signal analysis of shock wave and reflected shock waves and lea can yield information regarding the depth at which mine detonated.

Results from processing platform can be displayed to a human operator. Referring now to there is shown a schematic representation of display . For illustration but not limitation display is depicted as showing the actual track and future track of platform . Actual track is based on GPS information from platform .

In addition to tracking information display can depict location and timing information for detected explosion events illustrated by symbols with associated time in . Further information such as the locations of sensor platforms and may also be depicted on display .

When characterization is possible display can include differing symbols for differing types of mines as indicated by symbol and associated time in . In addition based on actual track and confirmed mine explosion events display can indicate areas that have been cleared of mines to acceptable levels as indicated by dash dot line in . Such information can aid in making the judgment as to whether or not to risk lives and assets in moving them through an area.

Sensors monitor the environment block to detect one or more events as described with respect to . If an event is detected as determined at block the corresponding data is transmitted block to processing platform or processor . Sensors continue monitoring the environment if no characteristics are detected.

When the data is received platform or processor correlates the sensor data block to determine if an actual event has occurred or the data received is an anomaly. If an event is confirmed block timing and location information is obtained block based on the GPS and timing capabilities of sensors .

Additionally by comparing the sensor data to historical data the event is characterized block as described with respect to . As also described with respect to and the event confirmation timing and location information and characterization of the event can be displayed block . Method can then await new data block . If new data is received as determined at block method returns to block to correlate the sensor data. Method also awaits new data when an event is not confirmed after correlating sensor data block .

What have thus been described are systems and methods to determine and ascertain the occurrence of an underwater mine explosion. The system can include multiple manned or unmanned platforms sensors deployed on one or more of the platforms and a processing platform. Event data from each sensor is transmitted to the processing platform. The processing platform correlates the data to determine if a mine explosion has occurred and further determines the location of an event.

The sensors can be incorporated on a single device or can be a distributed set of independent sensors on separate devices that share their information with the data processing platform. The processing platform can also include one or more sensors.

As previously noted the systems and methods are described herein relative to unmanned mine sweeping operations wherein the event occurrence to be ascertained is a mine firing or explosion event. However the systems and methods can be generalized to ascertain the occurrence of events whose transient signatures can be detected by one or more sensors.

Many modifications and variations of the present invention may become apparent in light of the above teachings. For example the types of platforms used need not be limited to nor include all of the platforms shown in . Depending on the type of event to be detected platforms may be airborne satellite based ground based mobile surface based underwater based or some combination thereof. Additionally the sensors may be chosen for the specific characteristics of the event or events to be detected.

It will be understood that many additional changes in details materials steps and arrangements of parts which have been described herein and illustrated in order to explain the nature of the invention may be made by those skilled in the art within the principle and scope of the invention as expressed in the appended claims.

