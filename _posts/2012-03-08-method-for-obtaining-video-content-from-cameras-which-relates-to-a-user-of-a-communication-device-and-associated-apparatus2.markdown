---

title: Method for obtaining video content from cameras which relates to a user of a communication device, and associated apparatus
abstract: A method is dedicated to the obtaining of video recordings related to a user who has a communication device (EC) capable of connecting to a wireless communications network (RC) and whose position is determinable. This method comprises the following steps: (i) determining the position of the spot where the communication device (EC) is located, (ii) determining whether there is at least one camera (C) capable of providing video recordings, of a part of an observation area that may include that determined spot, accessible via the communications network (RC), and (iii) in the event that such a camera (C) is determined, transmitting to the communication device (EC), via the communications network (RC), at least a portion of a video recording made by that camera (C) while the communication device (EC) is in its observation zone.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09560268&OS=09560268&RS=09560268
owner: Alcatel Lucent
number: 09560268
owner_city: Boulogne-Billancourt
owner_country: FR
publication_date: 20120308
---
The invention relates to video recordings which are made by cameras and more specifically obtaining and potentially using some of these video recordings.

As is known to a person skilled in the art certain video cameras make video recordings within observation areas which may affect some users of mobile communication devices.

Here mobile communication device refers to any machine that has a communication module capable of connecting to at least one wireless communications network potentially a peer to peer network in order to establish communications with at least one other communication device and or at least one network device and also is capable of presenting video content or signals to its user. It may therefore for example be a mobile telephone potentially a smartphone a laptop computer a personal digital assistant or PDA a digital graphics tablet a communicating monitor or a communicating gaming console.

Multiple solutions have been proposed to notify a user of the presence of a camera in his or her environment.

It has been proposed in the patent document WO 2010 027772 to detect cameras within an area in which they are prohibited from recording by taking multiple photographs of that area when it is lit and then by locating the prohibited cameras based on the particular reflection of their optics.

It has also been proposed in the patent documents GB 2372364 and U.S. Pat. No. 7 398 104 to detect the emissions that some wireless cameras produce when they transmit their video recordings to a wireless communications network.

The aforementioned known solutions all exhibit at least one drawback. They either require the use of an auxiliary illumination and detection device which is relatively bulky and expensive or they only pertain to wireless cameras and therefore cannot detect the presence of wired cameras which substantially limits their benefit.

Furthermore no known solution makes it possible to determine whether the user of a mobile communication device is actually within a detected camera s observation area which further limits their benefit. This means that although the user is alerted of the presence of a camera in his or her environment he or she does not know whether that camera filmed him or her and therefore if there is a locally stored record of his or her visit. Consequently the user must first perform several operations with his or her mobile communication device in order to attempt to obtain the detected camera s video recording provided that he or she is authorized to do so then must view that video recording afterward with his or her mobile communication device in order to determine whether or not he or she is in that video recording and if that recording concerns him or her. It should be understood that these several operations are restrictive for a user or even nearly impossible to perform when the user is using his or her mobile communication device for other tasks.

It should be noted that this latter drawback makes it particularly complicated to generate video content within a user s communication device based on a downloaded video recording excerpt that concerns that user. However such generating may prove useful to some users who have a personal website or blog as it allows them to enhance their agglomerated text posts within a blog with video content potentially in an at least partially automated fashion while protecting their privacy as they desire by means of operations such as deletions or face blurring for example.

It is therefore a purpose of the invention to improve the situation in particular with respect to detecting cameras in the vicinity of a mobile communication device s user.

According to a first aspect the invention proposes a method devoted to obtaining video recordings related to a user who has a communication device capable of connecting to a wireless communications network and whose position is determinable and comprising the following steps 

The method may comprise other characteristics that may be taken separately or in combination and in particular 

According to a second aspect the invention proposes an apparatus devoted to obtaining video recordings made by cameras for a communication device which is capable of connecting to a wireless communications network and whose position may be determined and furthermore comprising 

Such an apparatus may also potentially comprise generation means configured to generate a piece of video content based on a video recording portion transmitted upon request to the communication device and control means operative to order the communication device to provide a generated piece of video content to a chosen personal or group website in view of making it available potentially under chosen conditions.

According to a third aspect the invention proposes a communication device which firstly is capable of connecting to a wireless communications network secondly possesses a determinable geographic position and thirdly comprises an apparatus for obtaining video recordings of the type described above.

It is a particular object of the invention to enable users of mobile communication devices EC to obtain video recordings or content made by cameras Ci and which concern them.

It should be noted that the invention relates to any type of mobile communication device EC provided that it has a communication module MCN capable both of connecting to at least one wireless communications network RC potentially a peer to peer network in order to establish communications with at least one other communication device and or at least one network device and of playing and using video content. It may therefore for example be a mobile telephone potentially a smartphone a laptop computer a personal digital assistant or PDA a digital graphics tablet a communicating monitor or a communicating gaming console.

It is assumed in what follows by way of an exhaustive example that users communication devices EC are capable of establishing communications via a mobile or cellular communications network. However the users communication devices EC may be capable of establishing communications via a peer to peer wireless network.

The sole figure depicts a communications network RC to which are connected the following a user s mobile communication device EC equipped with an apparatus for obtaining video recordings D according to the invention two cameras Ci i 1 or 2 a server SI that stores information related to the cameras Ci and a blog server SB storing for example personal websites or blogs belonging to different users including the one who is using the aforementioned mobile communication device EC or a social network site e.g. Facebook or similar .

It should be noted in the example depicted in the sole figure only a single communication network RC is depicted. However the various equipment and servers may be connected to different communications networks inter connected with one another and particularly to the Internet.

The information that the server SI may store within storage means MS may particularly include known geographic positions of certain cameras Ci and corresponding camera identifiers.

The positions of the cameras CI may particularly be either declared by their owners for example due to a legal requirement or provided by users who discover them collaboratively.

The storage means MS may appear in any form known to the person skilled in the art and particularly in the form of a memory computer file or database.

The blog server SB comprises storage means MS in which it stores in this case personal websites or blogs that belong to different users comprising a mobile communication device EC. This blog server SB belongs for example to a social network publisher.

The storage means MS may be in any form known to the person skilled in the art and particularly in the form of a memory computer file or database.

Each camera Ci is operative to record video images within an observation area that depends on its technical characteristics and on its environment s configuration.

The various characteristics may particularly include the aperture angle the focal length the height above the ground at which it is fastened the tilt with respect to a horizontal plane and the swivel with respect to a vertical plane.

It should be noted that information data hereafter refers to data that defines a camera s Ci technical characteristics or the configuration of a camera s Ci environment.

Each camera Ci also comprises a communication module MCN capable of connecting to at least one wired and wireless communication device particularly for transmitting at least portions of its video recordings.

As depicted each camera Ci may comprise storage means MS in which it stores the digital data that define its information data. These storage means MS may be in any form known to the person skilled in the art and particularly in the form of a memory or a computer file.

However it is preferable to store within the information server s SI storage means MS the information data related to each listed camera Ci as a match for that camera s Ci position and identifier. This is because in this situation it is possible to obtain with just one query the position identifier and information data of a camera Ci.

Each camera Ci may also comprise as depicted storage means MS in which it stores the digital data defining each video recording made as a match for a date and a time. These storage means MS may appear in any form known to the person skilled in the art and particularly in the form of a memory computer file or database.

Each camera Ci may also comprise as depicted an access interface IA preferentially an API Application Programming Interface which allows a communication device EC or a server for accessing the video recordings which are potentially stored within its storage means MS.

Each camera Ci may also comprise as depicted an access controller CA that enables a communication device EC or a server to access the information data which are potentially stored within its storage means MS and or to control access to the storage means MS and or as we shall see later on to control access to a local processing module MT tasked with performing upon request at least one processing on the video recordings stored within the storage means MS.

It is important to note that in the example described below each camera Ci locally stores its video recordings. Consequently the video recordings must be obtained from the cameras Ci via their access interface IA and their access controller CA. However in one variant the cameras CI may be operative to transmit the video recordings that they make to a server which is then tasked with storing them in a centralized fashion as matches for their camera identifiers. In this situation the cameras Ci no longer actually need to comprise an access interface IA and an access controller CA.

It should be noted that if there is centralized video storage the access interface IA of a camera Ci may make it possible to redirect a user s communication device EC to the video server if that server is not known to that communication device EC in fact the access interface may allow transparent access whether the video storage is local or remote . It should also be noted that semi distributed or hybrid storage may also be conceived for example in different servers associated with different network operators depending on the owners of the cameras Ci and if so the access interface IA may enable transparent access.

The invention proposes implementing a method for obtaining video recordings within a communication installation of the type depicted in a non exhaustive fashion in the sole figure.

A first main step i consists of determining the position of the spot where a communication device EC is located.

This determination may be made by any means known to the person skilled in the art. Thus it may be made by means of a positioning device EP which potentially comprises the communication device EC. Such a positioning device EP may for example be a GPS Global Positioning System device. However in one variant it may be made by triangulation within the network RC or by detecting a connection within a micro or femtocell of the network RC for example. It should be noted that the technique used for this position determination may influence the accuracy of the later calculations that use these results.

It should also be noted that each first main step i may be performed either automatically at periodic intervals i.e. at intervals predefined by the user upon the request of the communication device s EC user when he or she wants to obtain a video recording of the spot where he or she is located with proof of his or her presence if possible.

A second main step ii of the inventive method consists of determining whether there is at least one camera Ci capable of providing video recordings made within a part of an observation area that might include a spot determined is during a first main step i and accessible via the network RC.

It should be noted that it is the apparatus for obtaining video recordings D according to the invention which is tasked with performing that second main step ii and potentially with requesting the position of its communication device EC during the first main step i when it is not communicated automatically in this case by the positioning device EP .

This determination is done by sending a request in this case to the information server SI via the network RC and by means of the communication module MCN of the mobile communication device EC.

For example the search means MR may compare the position of the communication device EC which was determined during the first main step i at known positions of cameras CI which are stored in storage means MS of the information server SI as matches for the camera identifiers in order to determine whether there is a camera Ci which might be located within the vicinity of the communication device EC. Next if such a camera CI exists the search means MR are operative to determine whether that camera CI offers an observation area which includes the communication device s EC determined position. Finally if so the search means MR are operative to perform the third main step iii that will be described later on using the identifier of the camera Ci that was determined.

It should be noted that in order to make the determination of a camera Ci more accurate it is particularly advantageous to also determine the communication device s EC trajectory during the first step i .

To do so one may for example use velocity data representative of the current velocity of the communication device EC and orientation and direction data representative of the general orientation and direction followed by the communication device EC. This physical parameter data speed orientation direction may be provided by devices that the communication device EC comprises such as for example an accelerometer AC and a compass BO or by a positioning device used for geolocation for example a GPS device .

It should be noted that the positioning device EP and or the accelerometer or analog AC and or the compass or analog BO may potentially form part of the apparatus D.

It should be understood that when the search means MR have the position velocity orientation and direction of the communication device EC they may calculate its trajectory and therefore they may determine during a second main step ii if that trajectory will cross or crosses the observation area of a camera Ci. It is thereby possible to anticipate the visitation of a communication device EC within an observation area of a camera Ci in order to obtain in advance the right to use a portion of that camera s Ci video recording or to notify the user of the communication device EC of the possibility of obtaining a portion of that camera s Ci video recording.

It should also be noted that the search means MR may be operative to determine during a second main step ii the observation area of a camera Ci based on information data which relate to that camera Ci and or to its environment. As previously indicated this information data may be for example obtained from storage means MS of the information server SI at the same time as the position and identifier of the camera Ci in question.

It should be understood that once the search means MR have a camera s Ci position and information data they can calculate or at least estimate that camera s Ci observation area. The observation zone s determined accuracy naturally depends on the number and accuracy of a camera s Ci information data.

It should also be noted that the transmission of a part of a video recording may be contingent on meeting a predefined set of rule s . If so during the second main step ii the transmission of only a part of a video recording is only permitted if all of the predefined rule s have been met.

Any type of rule known to the person skilled in the art that exhibits a relationship with the obtaining of a video recording may be conceived. This way it may for example be a local rule instituted due to a law and relating to the use of video recordings or an authorization to use a video recording if and only if no third party is recognizable or when each third party has provided authorization to use video sequences in which it appears potentially partially blurred or a permission to use a video recording when the user of a communication device EC has an authorization to use video recordings that concern him or her for example because that user has an identifier stored in a list of authorized users or it may be the providing by the communication device EC of an identifier previously provided when searching for information data related to a camera Ci and or to its environment. In the case of the last rule mentioned the identifier may for example by a token that is specifically assigned by the information server SI to a communication device EC when the communication device EC transmits to it a request intended to determine at least one identifier of a camera Ci whose position is in the vicinity of that communication device s EC position and which is transmitted to that device EC in the message responding to its request.

A third main step iii of the inventive method consists when a camera Ci has been determined in this case by search means MR of transmitting to the communication device EC upon its request and via the network RC at least one part of the video recording made by that camera Ci while the communication device EC is in its observation area.

In the non exhaustive example described here the apparatus D comprises processing means MT which are tasked with generating a request containing at least the identifier of the determined camera Ci and a request to obtain a portion of a video recording starting at the current date and time and with asking its communication device EC to transmit that request to the identified camera Ci. However in one variant the request may be transmitted to a storing server in particular that camera s Ci video recordings.

This request is sent via the network RC and by means of the communication module MCN of the mobile communication device EC.

It should be noted that during the third main step iii at least one processing of the requested video recording portion based on instructions that were provided by the communication device EC. That or each processing effort may potentially be performed within the camera Ci that was determined whenever that camera Ci comprises a processing module MT operative for that purposes and when it also stores its video recordings. This is advantageous as it makes it possible to free up the apparatus D from one or more processing efforts. Furthermore the definition of each requested processing effort may advantageously be transmitted in the request to obtain a video recording.

Any type of video image processing known to the person skilled in the art that is relatively fast and simple may be requested. Thus it may for example be blurring the faces of people or third parties detected within the images of a video recording manually and or automatically selecting at least one sequence of a portion of a video recording such as for example a summary when that video lasts longer than a predefined threshold deleting a portion of a video recording or sharing a portion of a video recording with at least one third party.

More specifically the fourth step iv consists of generating a piece of video content within the communication device EC based on a portion of a video recording that was obtained by transmission and the fifth step v consists of providing a piece of video content that was generated during a fourth main step iv to a personal website of the user stored in this case within the blog server SB in view of making it available potentially under chosen conditions.

Here the term video content refers to a set of digital data defining a sequence of video images and placed in a format that makes it possible to add them to a blog and to make them usable by video players. Consequently a piece of video content may be constituted by a video recording portion potentially post processing or by digital data resulting from processing a downloaded video recording portion.

The conditions for making a piece of video content available if any are chosen by the user. For example they form part of the policy for accessing his or her blog which he or she predefined and which is in force or access policies defined by a social networking site such as Facebook when the video is published by the user on a third party service.

This fourth step iv is performed by the apparatus D and more specifically by generation means MG that it comprises and which are is operative to generate a piece of video content based on a video recording portion transmitted upon request to the communication device EC.

It should be noted that at least one processing effort may be performed within the communication device EC during that fourth step iv . If so the generation means MG are the ones which are preferably tasked with this processing.

As previously indicated any type of video image processing known to the person skilled in the art which is relatively fast and simple may be performed by the generation means MG. This processing may potentially complement those performed within a camera Ci by the processing means MT if any. Consequently it may for example be blurring the faces of people or third parties detected in the images of a downloaded video recording portion manually and or automatically selecting at least one sequence of a portion of a video recording such as for example a summary when that video lasts longer than a predefined threshold deleting a portion of a video recording or sharing a portion of a video recording with at least one third party.

Preferentially and as depicted the apparatus D comprises storage means MS wherein it stores the generated video content as well as potentially the downloaded video recording portions. This particularly makes it possible to perform additional processing or more simply the viewing of video content by the user when he or she so desires. This way a user may for example put together a long video sequence with multiple pieces of video content potentially to publish it in his or blog.

The storage means MS may appear in any form known to the person skilled in the art and particularly in the form of a memory computer file or database.

The fifth step v is performed by the apparatus D and more specifically by control means MC that it comprises and which are operative to order the communication device EC to provide a piece of video content which had been generated by the generation means MG to the personal website.

It should be noted that at least one of the steps i to v may be performed based on a set of instructions that had been predefined by the user of the communication device EC.

Any type of instruction known to the person skilled in the art that makes it possible to automate potentially in a contextual fashion a function or operation may be used. This way it may be data defining a determination period launching the method or a systematic storage of video recording portions potentially after at least one predefined processing a storage of video recording portions based on a predefined context potentially after at least one predefined processing and the automatic generating and providing of a piece of video content potentially based on a predefined context. By way of a contextual example it is conceivable that there might be an instruction that requests the storage of a video recording portion every time that the communication device EC is located in a new spot where it had never been before. It is conceivable that there might be an instruction requesting that the length of each video recording portion be shortened to about 10 seconds potentially except when the communication device EC is located in a new spot where it had never been before and if so the duration is set to 30 seconds. It is also conceivable that there might be an instruction requesting that the method alone be launched when the communication device EC is located in a new spot where it had never been before or in a predefined location. It is also conceivable that there might be an instruction requesting that the user s authorization always be obtained before ever downloading a video recording portion or before ever locally storing a downloaded video recording portion.

Preferentially and as depicted the apparatus D comprises storage means MS in which it stores each set of instructions predefined by the user. As a set s instructions may relate to multiple means or modules of the apparatus D the storage means MS may therefore be accessible to each of its means or modules .

These storage means MS may come in any form known to the person skilled in the art and particularly in the form of a memory a computer file or particularly for the rules a database.

It should also be noted that the user of the communication device EC may be notified every time there is a video recording that concerns him or her. This may for example serve to notify him or her that it is providing an instruction requesting that the method continue potentially under certain conditions or that the method be stopped or more simply to tell him or her that he or she will soon have access to new video content potentially added to his or her blog or to a chosen social networking site in accordance with the set of instructions that he or she predefined and which is in force.

The notifications may be for example generated by the control means MC. It should be noted that these means MC may potentially comprise a rules engine tasked with controlling the application of each instruction of the predefined set in force.

It should also be noted that all of the exchanges that took place between the user and the apparatus D in both directions are carried out via a human machine interface IN which is preferentially part of the communication device EC. However this human machine interface IN may form part of the apparatus D.

It should also be noted that the apparatus D is preferentially carried out in the form of a combination of electronic circuit and software or computer modules. However it may also be constructed in the form of software modules.

The invention is not limited to the embodiments of the apparatus for obtaining video recordings user communication device and method for obtaining video recordings described above which are given only as examples rather it encompasses all variants that the person skilled in the art may envision within the framework of the claims below.

