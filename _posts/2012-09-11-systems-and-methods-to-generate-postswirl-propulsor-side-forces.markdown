---

title: Systems and methods to generate post-swirl propulsor side forces
abstract: Systems and methods for maneuvering an underwater vehicle by generating vehicle maneuvering forces from a propulsor of the vehicle are provided. A post-swirl propulsor is configured such that pitch angles of downstream stator blades can be individually varied. The variation in pitch results in the generation of multiple forces and moments for vehicle control.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09315250&OS=09315250&RS=09315250
owner: The United States of America as represented by the Secretary of the Navy
number: 09315250
owner_city: Washington
owner_country: US
publication_date: 20120911
---
The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties thereon or therefor.

This application is related to co pending U.S. patent application Ser. No. 12 651 559 filed on Jan. 4 2010 and entitled SYSTEMS AND METHODS TO GENERATE PROPULSOR SIDE FORCES this application being by the same inventors as the co pending application.

The present invention relates to maneuvering an underwater vehicle and more specifically to systems and methods for generating vehicle maneuvering forces from a post swirl propulsor.

Standard torpedoes and Unmanned Undersea Vehicles UUVs utilize a single propulsor at the stern in combination with control surfaces to provide the vehicle with necessary forces and moments to produce control of the vehicle. At higher speeds this combination is generally satisfactory in terms of offering sufficient control. At low speeds control surface effectiveness is significantly diminished with the extreme condition being zero forward velocity e.g. Bollard condition . There are several operations where low speed control is vitally important for UUV mission requirements. These include UUV recovery station keeping and synthetic aperture sonar.

In the art side forces have been generated using thrust vectoring. In thrust vectoring the thrust is re directed off axis to generate side forces for control. To meet low speed requirements autonomous research vehicles have utilized tunnel thrusters to offer lateral and vertical control.

The difficulty is that thrust vectoring is most effective for zero speeds. As the flow velocity is increased tunnel thruster effectiveness is significantly diminished. For example it has been shown that tunnel thrusters are only 20 effective above five knots. The tunnel thrusters also increase drag such that maximum velocities are reduced. In addition tunnel thrusters use considerable volume that could otherwise be used for energy or payload.

Another prior art design is referred to as the Haselton bow propulsor. In this concept a pair of propellers one at the bow and one at the stern is used in tandem to provide vehicle control. Side forces are generated via cyclic pitch actuation similar to that used for helicopter rotors.

The Haselton design utilizes a swashplate so that angle of attack is varied over a single propeller rotation. For example if maximum and minimum angles of attack are reached at 0 and 180 the higher thrust force at 0 and lower thrust force at 180 will generate a moment couple. By adding rake and skew to the propeller it is then possible to generate a substantial side force component.

A disadvantage is that the Haselton bow propulsor concept remains mechanically complex for implementation on undersea vehicles. In addition placing a propulsor at the bow of the vehicle interferes with the forward looking sonar that is used on most UUVs and torpedoes.

In previous research a pre swirl propulsor capable of generating side forces of sufficient magnitude to provide vehicle control and maneuvering was investigated. It was found that varying the pitch angles of the upstream stator blades of a ducted pre swirl propulsor can both generate a mean stator side force and subsequently vary the axial velocity and swirl that is ingested into the inflow. The rotor can then generate a side force in response to the inflow.

The research also showed that the stator row generated significantly larger forces compared with the rotor. The rotor generates side forces in response to the stator modified inflow. For baseline rotor designs the side forces are in a direction opposite to the stator forces i.e. the rotor effectively attenuates the stator side forces .

Additionally it was found that open propulsors i.e. propulsors without a shroud generated side forces in a manner as to be more efficient than standard vehicle control surfaces. By sinusoidally varying the stator blade pitch distribution about the circumference it is possible to generate significant side forces.

However ducted pre swirl propulsor configurations i.e. propulsors with a shroud generated side forces with magnitudes approximately three times smaller than open configurations. The shroud produces opposing forces resulting in the diminishment of the overall side forces. For this reason open pre swirl propulsor configurations were proposed for further examination to offer an alternative for vehicle control.

There are several undersea vehicle applications where a ducted propulsor configuration is desirable. This includes pumpjet and rim driven electric motor configurations. For these cases a post swirl propulsor is utilized with an upstream rotor blade row and a downstream stator blade row. For normal post swirl designs propulsive efficiency can be improved with effective stator blade row design. The rotor swirls the flow ingested into the stator. The stator can be designed to remove the swirl and at the same time generate roll moment to counter the rotor roll moment.

What are therefore needed are systems and methods for maneuvering an underwater vehicle having a ducted post swirl propulsor. The systems and methods should be effective at reasonable operating speeds should not significantly reduce maximum velocities and should not take up considerable volume. Additionally the systems and methods should be relatively simple to implement without interfering with forward looking sonar.

It is therefore a general purpose and primary object of the present invention to provide systems and methods for maneuvering an underwater vehicle by generating vehicle maneuvering forces from a propulsor of the vehicle.

This object is attained by the present invention by configuring a post swirl propulsor such that the pitch angles of the downstream stator blades can be individually varied. The variation in pitch results in the generation of multiple forces and moments to allow for vehicle control.

In one embodiment a post swirl propulsor system for an underwater vehicle includes a rotor and a row of stator blades downstream of the rotor. A pitch angle of the stator blades varies about a circumference of the vehicle. A thrust flow from the rotor combines with a circumferentially varying flow from the stator blades to produce a force on the vehicle that is perpendicular to a main axis of the vehicle.

The pitch angle is adjustable and the pitch angle of each stator blade can be adjusted. The system can include a controller to determine the pitch angle for each stator blade. A servo motor is connected to each stator blade. The pitch angle of the stator blade connected to the servo motor is adjustable by actuation of the servo motor by the controller.

In one embodiment a system for maneuvering an underwater vehicle includes a rotor and a plurality of stator blades downstream of the rotor. The stator blades form a row about the circumference of the vehicle and the pitch angle of the stator blades is adjustable.

The system includes a plurality of servo motors with each servo motor connected to one or more of the stator blades. When actuated the servo motor adjusts the pitch angle of the one or more stator blades connected thereto.

A controller is connected to the servo motors and coordinates the actuation of the servo motors to vary the pitch angles of the stator blades about the circumference. The varying pitch produces a circumferentially varying flow from the stator blades which produces a force on the vehicle perpendicular to a main axis of the vehicle. Additionally the system can include a shroud about the rotor and the shroud may extend about the stator blades.

Referring to there is shown a schematic side view of an underwater vehicle having a ducted post swirl propulsor . For clarity of illustration in a duct or shroud of the propulsor is shown in phantom. Stator blades are situated downstream of a rotor .

During normal operation the downstream stator blades are each situated at the same pitch angle or angle of attack. The flow coming off the rotor illustrated by arrow is swirled by the stator blades . As is known to those of skill in the art post swirling the flow results in generating a roll moment which counters the moment produced by the rotor .

Referring now to there is shown a cross sectional side view of an exemplary stator blade taken at line A A of . The stator blade is connected to a shaft . As shown in the stator blade is positioned exterior to a hull of the vehicle . The shaft penetrates through the hull and extends interior to the hull. A seal surrounds the shaft to provide a waterproof seal for the shaft.

Activation of a servo motor results in the extension or retraction of an actuator arm as indicated by arrow . The actuator arm engages the shaft to turn the shaft about its axis X X as indicated schematically by arrow . Rotation of the shaft results in varying the pitch angle of the stator blade . For illustration but not limitation teeth on actuator arm are depicted as engaging teeth on the shaft .

For the propulsor to generate vehicle maneuvering forces downstream stator blades are situated at varying pitch angles using the servo motors . Experiments with pre swirl propulsors indicate that this variation in pitch angles results in the downstream stator blades generating a stator side force as illustrated by arrow F in perpendicular to axis Y Y of vehicle . A controller illustrated within the hull in connects to each servo motor illustrated by line in and coordinates the actions of the servo motors to obtain the desired maneuvering forces.

What has thus been described is a propulsor system that generates side forces utilizing a post swirl propulsor configuration with the downstream stator blades situated at varying pitch angles to generate a circumferentially varying flow. This variation in stator blade pitch also results in side force generation by the stator blade row.

The pre swirl results of are a combined experimental and numerical evaluation. Two advance ratios J V nD where J is the advance ratio V is the flow velocity n is the rotational velocity in Hz and D is the propeller diameter were examined. For J 1.91 the propulsor produces little to no thrust and J 1.43 the propulsor produced sufficient thrust to overcome the drag produced by a body stator and shroud.

The post swirl normal side forces are based on computational predictions. As shown in maximum normal forces for the pre swirl maneuvering propulsor configuration are on the order of 0.3 for an open configuration 0.075 for a ducted configuration. The post swirl maneuvering propulsor normal forces are significantly larger even at 12 degree maximum stator pitch amplitude with maximum forces of 0.45 seen for the open configuration and 0.3 for the ducted configuration. These forces would be potentially larger for 15 degrees.

In addition the normal forces increase with a decreased advance ratio corresponding to increased propeller thrust. The differences for the thrusting compared to the non thrusting situations for the pre swirl maneuvering propulsor are insignificant. Conversely the ducted post swirl maneuvering propulsor configuration produces sufficient side forces to enable vehicle control whereas the pre swirl maneuvering propulsor configuration does not. As such the post swirl maneuvering propulsor calculations highlight a significant improvement to produce side forces sufficient for vehicle control.

Obviously many modifications and variations of the present invention may become apparent in light of the above teachings. For example the design of the stator blades and the number of stator blades in the propulsor system described herein can be varied. Also the pitch of the stator blades can be varied in any number of ways provided that the pitch variance produces the side forces and circumferentially varying flow described herein.

In light of the above it is therefore understood that within the scope of the appended claims the invention may be practiced otherwise than as specifically described.

