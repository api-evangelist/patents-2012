---

title: System architecture and methods for composing and directing participant experiences
abstract: The present invention contemplates a variety of improved methods and systems for providing an experience platform, as well as sentio or experience codecs, and experience agents for supporting the experience platform. The experience platform may be provided by a service provider to enable an experience provider to compose and direct a participant experience. The service provider monetizes the experience by charging the experience provider and/or the participants for services. The participant experience can involve one or more experience participants. The experience provider can create an experience with a variety of dimensions and features. As will be appreciated, the following description provides one paradigm for understanding the multi-dimensional experience available to the participants. There are many suitable ways of describing, characterizing and implementing the experience platform contemplated herein.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08571956&OS=08571956&RS=08571956
owner: Net Power and Light, Inc.
number: 08571956
owner_city: San Francisco
owner_country: US
publication_date: 20120206
---
The present application is a continuation of U.S. patent application Ser. No. 13 136 869 now U.S. Pat. No. 8 463 677 entitled System and Methods for Experiential Computing Filed Aug. 12 2011 which claims the benefit of and priority to U.S. Provisional Patent Application No. 61 373 193 entitled System Architecture and Methods for Composing and Directing Participant Experiences filed on Aug. 12 2010 both of which are herby incorporated by reference.

The present teaching relates to experience platforms enabling an experience provider the direct and compose an experience for one or more participants which experience may involve a variety of dimensions including video group participation gesture recognition heterogeneous device use emotions etc.

The present invention contemplates a variety of improved methods and systems for providing an experience platform as well as sentio or experience codecs and experience agents for supporting the experience platform. The experience platform may be provided by a service provider to enable an experience provider to compose and direct a participant experience. The service provider monetizes the experience by charging the experience provider and or the participants for services. The participant experience can involve one or more experience participants. The experience provider can create an experience with a variety of dimensions and features. As will be appreciated the following description provides one paradigm for understanding the multi dimensional experience available to the participants. There are many suitable ways of describing characterizing and implementing the experience platform contemplated herein.

In general services are defined at an API layer of the experience platform. The services are categorized into dimensions. The dimension s can be recombined into layers. The layers form to make features in the experience.

By way of example the following are some of the dimensions that can be supported on the experience platform.

Video is the near or substantially real time streaming of the video portion of a video or film with near real time display and interaction.

Audio is the near or substantially real time streaming of the audio portion of a video film karaoke track song with near real time sound and interaction.

Live is the live display and or access to a live video film or audio stream in near real time that can be controlled by another experience dimension. A live display is not limited to single data stream.

Encore is the replaying of a live video film or audio content. This replaying can be the raw version as it was originally experienced or some type of augmented version that has been edited remixed etc.

Graphics is a display that contains graphic elements such as text illustration photos freehand geometry and the attributes size color location associated with these elements. Graphics can be created and controlled using the experience input output command dimension s see below .

Input Output Command s are the ability to control the video audio picture display sound or interactions with human or device based controls. Some examples of input output commands include physical gestures or movements voice sound recognition and keyboard or smart phone device input s .

Interaction is how devices and participants interchange and respond with each other and with the content user experience video graphics audio images etc. displayed in an experience. Interaction can include the defined behavior of an artifact or system and the responses provided to the user and or player.

Game Mechanics are rule based system s that facilitate and encourage players to explore the properties of an experience space and other participants through the use of feedback mechanisms. Some services on the experience Platform that could support the game mechanics dimensions include leader boards polling like dislike featured players star ratings bidding rewarding role playing problem solving etc.

Ensemble is the interaction of several separate but often related parts of video song picture story line players etc. that when woven together create a more engaging and immersive experience than if experienced in isolation.

Auto Tune is the near real time correction of pitch in vocal and or instrumental performances. Auto Tune is used to disguise off key inaccuracies and mistakes and allows singer players to hear back perfectly tuned vocal tracks without the need of singing in tune.

Auto Filter is the near real time augmentation of vocal and or instrumental performances. Types of augmentation could include speeding up or slowing down the playback increasing decreasing the volume or pitch or applying a celebrity style filter to an audio track like a Lady Gaga or Heavy Metal filter .

Remix is the near real time creation of an alternative version of a song track video image etc. made from an original version or multiple original versions of songs tracks videos images etc.

Viewing 360 Panning is the near real time viewing of the 360 horizontal movement of a streaming video feed on a fixed axis. Also the ability to for the player s to control and or display alternative video or camera feeds from any point designated on this fixed axis.

Turning back to the experience platform includes a plurality of devices and a data center . The devices may include devices such as an iPhone an android a set top box a desktop computer and a netbook . At least some of the devices may be located in proximity with each other and coupled via a wireless network. In certain embodiments a participant utilizes multiple devices to enjoy a heterogeneous experience such as using the iPhone to control operation of the other devices. Multiple participants may also share devices at one location or the devices may be distributed across various locations for different participants.

Each device has an experience agent . The experience agent includes a sentio codec and an API. The sentio codec and the API enable the experience agent to communicate with and request services of the components of the data center . The experience agent facilitates direct interaction between other local devices. Because of the multi dimensional aspect of the experience the sentio codec and API are required to fully enable the desired experience. However the functionality of the experience agent is typically tailored to the needs and capabilities of the specific device on which the experience agent is instantiated. In some embodiments services implementing experience dimensions are implemented in a distributed manner across the devices and the data center . In other embodiments the devices have a very thin experience agent with little functionality beyond a minimum API and sentio codec and the bulk of the services and thus composition and direction of the experience are implemented within the data center .

Data center includes an experience server a plurality of content servers and a service platform . As will be appreciated data center can be hosted in a distributed manner in the cloud and typically the elements of the data center are coupled via a low latency network. The experience server servers and service platform can be implemented on a single computer system or more likely distributed across a variety of computer systems and at various locations.

The experience server includes at least one experience agent an experience composition engine and an operating system . In one embodiment the experience composition engine is defined and controlled by the experience provider to compose and direct the experience for one or more participants utilizing devices . Direction and composition is accomplished in part by merging various content layers and other elements into dimensions generated from a variety of sources such as the service provider the devices the content servers and or the service platform .

The content servers may include a video server an ad server and a generic content server . Any content suitable for encoding by an experience agent can be included as an experience layer. These include well know forms such as video audio graphics and text. As described in more detail earlier and below other forms of content such as gestures emotions temperature proximity etc. are contemplated for encoding and inclusion in the experience via a sentio codec and are suitable for creating dimensions and features of the experience.

The service platform includes at least one experience agent a plurality of service engines third party service engines and a monetization engine . In some embodiments each service engine or has a unique corresponding experience agent. In other embodiments a single experience can support multiple service engines or . The service engines and the monetization engines can be instantiated on one server or can be distributed across multiple servers. The service engines correspond to engines generated by the service provider and can provide services such as audio remixing gesture recognition and other services referred to in the context of dimensions above etc. Third party service engines are services included in the service platform by other parties. The service platform may have the third party service engines instantiated directly therein or within the service platform these may correspond to proxies which in turn make calls to servers under control of the third parties.

Monetization of the service platform can be accomplished in a variety of manners. For example the monetization engine may determine how and when to charge the experience provider for use of the services as well as tracking for payment to third parties for use of services from the third party service engines .

The sentio codec is a combination of hardware and or software which enables encoding of many types of data streams for operations such as transmission and storage and decoding for operations such as playback and editing. These data streams can include standard data such as video and audio. Additionally the data can include graphics sensor data gesture data and emotion data. Sentio is Latin roughly corresponding to perception or to perceive with one s senses hence the nomenclature sentio codec. 

The sentio codec can be designed to take all aspects of the experience platform into consideration when executing the transfer protocol. The parameters and aspects include available network bandwidth transmission device characteristics and receiving device characteristics. Additionally the sentio codec can be implemented to be responsive to commands from an experience composition engine or other outside entity to determine how to prioritize data for transmission. In many applications because of human response audio is the most important component of an experience data stream. However a specific application may desire to emphasize video or gesture commands.

The sentio codec provides the capability of encoding data streams corresponding to many different senses or dimensions of an experience. For example a device may include a video camera capturing video images and audio from a participant. The user image and audio data may be encoded and transmitted directly or perhaps after some intermediate processing via the experience composition engine to the service platform where one or a combination of the service engines can analyze the data stream to make a determination about an emotion of the participant. This emotion can then be encoded by the sentio codec and transmitted to the experience composition engine which in turn can incorporate this into a dimension of the experience. Similarly a participant gesture can be captured as a data stream e.g. by a motion sensor or a camera on device and then transmitted to the service platform where the gesture can be interpreted and transmitted to the experience composition engine or directly back to one or more devices for incorporation into a dimension of the experience.

In addition to the above mentioned examples various other modifications and alterations of the invention may be made without departing from the invention. Accordingly the above disclosure is not to be considered as limiting and the appended claims are to be interpreted as encompassing the true spirit and the entire scope of the invention.

