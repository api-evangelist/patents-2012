---

title: Techniques for overlaying a custom interface onto an existing kiosk interface utilizing non-visible tags into screen definitions of the existing interface
abstract: Techniques for overlaying a custom interface onto an existing kiosk interface are provided. An event is detected that triggers a kiosk to process an agent that overlays, and without modifying, the kiosk's existing interface. The agent alters screen features and visual presentation of the existing interface and provides additional alternative operations for navigating and executing features defined in the existing interface. In an embodiment, the agent provides a custom interface overlaid onto the existing interface to provide a customer-facing interface for individuals that are sight impaired, and the method further comprises injecting non-visible tags into screen definitions for the existing interface that are recognized only by the agents to handle exception conditions and actively ignored by the existing interface.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09626199&OS=09626199&RS=09626199
owner: NCR Corporation
number: 09626199
owner_city: Duluth
owner_country: US
publication_date: 20120209
---
Consumers are increasingly using kiosks to conduct business with enterprises. The kiosks come in a variety of sizes and are used for a variety of purposes. Some kiosks are drive through such as fast food establishments pharmacies banks and the like. Other kiosks are stationary located in gas stations airlines grocery stores department stores and the like.

In addition what is considered a kiosk is evolving with today s technology. For example digital signs now provide advertisements and mechanisms for users to interact with the displays to perform transactions. Such mechanisms include blue tooth communication Near Field Communication NFC Quick Response QR code scanning WiFi communication and the like.

So increasingly customers are engaging in a variety of technologies to automatically interact with enterprises to perform transactions. The transactions may result in purchases or may result in such things as registration for loyalty programs enrolling in promotional events requesting additional information for a good or service and others. That is the transactions via these kiosks are not strictly tied to purchases although some transactions are purchase related.

As kiosks become more pervasive in today s marketplace more and more people with disabilities are being left behind because the interfaces of most kiosks do not adequately account for an individual s disabilities.

As a result the government is pressing more and more for kiosks to become compliant with the American with Disabilities Act ADA . Heretofore the industry has resisted compliance due to the perceived cost associated with redoing and redeploying interfaces for existing kiosks. Thus very few kiosks properly comply with what the government considers appropriate for individuals with disabilities such as the sight impaired.

Also when someone with a disability is unable to access goods and services on his her own they become more dependent on society or loved ones and add to the cost that society must pay to care for him her.

In various embodiments techniques for overlaying a custom interface onto an existing kiosk interface are presented. According to an embodiment a method for overlaying a custom interface onto an existing kiosk interface is provided.

Specifically an event at a kiosk is detected that triggers a change in mode of operation for the kiosk. Next the kiosk acquires configuration information for the changed mode and one or more references to agents that interact with an existing interface of the kiosk. The configuration information defines additional visual information and placement for the additional visual information and existing visual information for the existing interface. Then the kiosk processes the one or more agents to overlay the additional visual information and the existing visual information in the placement defined by the configuration information on a display of the kiosk. Finally the kiosk and a user interact with one another the user navigates and transacts with the kiosk using the additional visual information and the agents overlaid on top the existing interface.

The custom kiosk interface overlay manager executes on one or more processors of a kiosk. In some embodiments the custom kiosk interface overlay manager operates in a cloud processing environment and is available as a cloud service over the Internet to send dynamic configuration instructions to a kiosk to overlay a custom interface on the kiosk.

In some instances the custom kiosk interface overlay manager interacts with consumer mobile device apps applications and services of enterprise systems and or other third party services utilized by consumers and or enterprises for transaction processing loyalty processing and or other customer relationship management processing.

Various embodiments of the techniques presented herein provide extensions to typical screen layout descriptions that can in combination with changes at the rendering level via a rendering agent allow any application to provide a custom interface overlay to existing kiosk interfaces such as interfaces for the sight impaired for use in ADA compliance.

The techniques recognize that extensions to graphic elements are readily permitted as additional attributes and can provide narrative text storage and tab order. Multiple levels of tab order are recognized a primary level which moves between the main screen headings and areas ultimately including the control buttons ok cancel help etc. and a secondary tab order used within screen areas that present functional options such as Cash Back Amount 20 40 60 80 or 100 for Automated Teller Machines ATM a type of kiosk . Controls may be defined which are not visible that allow additional text to be defined and presented in tab order without disrupting the visible buttons of the existing kiosk interface.

Tags are defined and injected into the screen definitions for any exception handling requirements thereby permitting a default behavior to be defined that only needs overridden for exception conditions.

Moreover in some cases an insertion of a headphone jack into a kiosk port or recognition of a Blue Tooth connection with a mobile device of a consumer enables certain features within the kiosk. So in some circumstances text to speech is used to generate audio from the configured textual descriptions. The text speaker can be interrupted at any point with navigation commands. Moreover voice to text can be used to navigate an existing kiosk interface that was never designed to provide such features via the custom overlaid interface.

Navigation commands are derived from messages sent to the User Interface UI engine from a physical keyboard device. Typically and as one example commands include move Left L Right R Up U and Down D tab enter and cancel. Key stroke events may be generated from a distinct device consumer mobile phone and the like or from an existing device including the touch screen used with the existing kiosk interface with reserved area definitions representing keystrokes etc.

As will be detailed more completely herein and below the approaches presented can be used to extend any solution using a configurable UI to provide ADA sight impaired compliance or user specific disability without modification of the underlying legacy kiosk interface application. This greatly speeds application compliance with new and changing ADA laws lowers the cost and risk of compliance changes. Moreover because the narrative is represented in simple text it is easily extended or modified by the solution owner to achieve a custom interface overlaid onto an existing and legacy kiosk interface.

At the custom kiosk interface overlay manager detects an event that triggers a change in mode of operation for the kiosk. That is the kiosk that the custom kiosk interface overlay manager executes on includes a legacy interface that processes in its existing interface mode of operation until an event is detected that changes that mode of operation in accordance with what is described herein.

According to an embodiment at the custom kiosk interface overlay manager recognizes the event as one of a selection made by the user from the existing interface on the kiosk a command sent from a mobile app processing on a mobile device of the user and a profile obtained for the user based on a loyalty card scanned inputted or swiped on the kiosk.

At the custom kiosk interface overlay manager acquires configuration information for the changed mode of operation and for one or more references to agents that interact with an existing interface of the kiosk. The configuration information defines additional visual information and placement for the additional visual information and existing visual information for the existing interface. The kiosk knows how to respond and transact via the legacy and existing interface and the configuration information combined with the agents provide an overlay interface for a user to use that is user facing but underneath utilizes the existing commands of the legacy kiosk interface.

In an embodiment at the custom kiosk interface overlay manager initiates the agents for execution on the kiosk. The agents utilize an existing Application Programming Interface API of the existing interface to direct and control the existing interface. So the custom kiosk interface overlay manager presents a new interface but underneath communicates with the kiosk via the legacy and existing interface of the kiosk.

In another situation at the custom kiosk interface overlay manager derives the configuration information as embedded attributes defined on graphical elements of the existing interface that are recognized and processed by the agents. So the existing interface does not need to know or recognize the extended attributes placed on the graphical elements since the agents will recognize the extended attributes and communicate with the existing interface utilizing the API of the existing interface.

In one case at the custom kiosk interface overlay manager identifies at least some attributes as first order placement on the display for the graphical elements to which the at least some attributes relate. So as discussed above graphical tabs may include a ordering and placement within the display of the kiosk that are defined via the attributes.

Continuing with the embodiment of and at the custom kiosk interface overlay manager recognizes particular attributes as having a secondary order placement on the display relative to the first order placement. Again such a situation was discussed above where existing operations of the existing interface are placed in a second order relative to the first order placement of graphical tabs.

In a situation at the custom kiosk interface overlay manager obtains the configuration information from a mobile device of the user interfaced to the kiosk. So the user can carry the definition and references to the used agents on the mobile device via a mobile app and communicate the overlay interface combination of configuration information and the agents dynamically to the kiosk and correspondingly the custom kiosk interface overlay manager via a network connection.

According to an embodiment at the custom kiosk interface overlay manager injects non visible tags into screen definitions for the existing interface that are recognized and processed by the agents to handle exception processing. Again such tags may not in some cases be recognized and may be actively ignored by the existing interface and its API since the agents recognize and process the tags.

At the custom kiosk interface overlay manager processes the one or more agents to overlay the additional visual information and the existing visual information in the placement defined by the configuration information on a display of the kiosk.

In an embodiment at the custom kiosk interface overlay manager processes some of the agents as intermediaries that provide text to speech or voice translation of the additional visual information and the existing visual information to the user in an audible manner from the kiosk. This may be useful for blind individuals that are more than simply visually impaired.

Continuing with the embodiment of and at the custom kiosk interface overlay manager processes particular agents as additional intermediaries that provide speech of voice to text translation of user commands that are audibly communicated by the user to commands recognized by the existing interface.

Still continuing with the embodiment of and at the custom kiosk interface overlay manager acquires the user commands from a mobile app executing on a mobile device of the user.

At the custom kiosk interface overlay manager interacts with the user to navigate and transact with the kiosk using the additional visual information and the agents overlaid on top of the existing interface.

The overlaid interface is customized for preferences and or disabilities of the user. It is noted that this is particular useful for the sight impaired or elderly users but can also be customized for those that are mentally challenged or even technology illiterate.

The mobile app is controlled by a consumer customer and or user and interacts with the custom kiosk interface overlay manager represented by the method of the .

It is noted that the mobile app can be installed and initiated by the consumer on the mobile device in a variety of manners before the processing occurs as detailed below. For instance in one situation during a registration process of the mobile device with enterprise loyalty system the mobile app is downloaded and initiated on the mobile device. In another instance during an initial contact by the mobile device by activating a QR code for a first time that represents a unique transaction code for a retailer the preference configuring service is automatically contacted and downloads and installs on the mobile device and initiates a registration process. The remaining processing described for the mobile app assumes the mobile app is installed and executing on a mobile device of a consumer.

At the mobile app establishes at the mobile device a connection with the kiosk. This connection can occur over a variety of networks and in a variety of manners some initiated by the user and some automatically occurring.

The connection can be initiated by the kiosk detecting the mobile device within a predefined range of the kiosk or can be initiated by the user via the mobile app that detects and reports the presence of the kiosk. This may be audible communication to the user via the mobile device.

At the mobile app provides from the mobile device an identity for the user of the mobile device. Again this can be an interactive process or an automated process.

Continuing with the embodiment of and at the mobile app passes a token media access control address for the mobile device and or a password to the kiosk in order for the kiosk to perform the authentication. Authentication provides the identity of the user to the kiosk and a backend enterprise system associated with the kiosk.

In still other cases the user can scan input or swipe a loyalty card to provide the identity of the user to the kiosk and the backend enterprise system associated with the kiosk.

At the mobile app interacts via the mobile device with the kiosk to perform a transaction. The interaction occurring via an overlay interface provided on the mobile device that uses agents on the kiosk to translate operations recognized by an existing interface of the kiosk.

In an embodiment at the mobile app uses the overlay interface as text to voice and voice to text command driven interface that acts as an intermediary between the existing interface and the mobile device.

In still another case at the mobile app uses the overlay interface as a translator between input mechanisms of the mobile device and commands recognized by the existing interface.

The described the processing for overlaying a custom interface onto an existing kiosk interface from the perspective of the kiosk. The described the processing from the perspective of the consumer s mobile app on a consumer s mobile device and the custom overlay interface system describes the processing for transacting from both the kiosk s and the mobile device s perspectives.

The custom overlay interface system includes a custom kiosk interface overlay manager and a mobile app . Each of these and their interactions with one another will now be discussed in turn.

The custom overlay interface system includes a kiosk having one or more processors that execute the custom kiosk interface overlay manager which is implemented programmed and resides within a non transitory computer readable storage medium. Example processing associated with the custom kiosk interface overlay manager was presented above in detail with reference to the .

The custom kiosk interface overlay manager is configured to overlay an interface on top of an existing interface of the kiosk and provide one or more aspects of the overlaid interface to the mobile app for a user to transact with the kiosk via the overlay interface.

The custom overlay interface system also includes a mobile app that is configured to execute on one or more processors of a mobile device such as a mobile phone a tablet a laptop etc. Example processing associated with the mobile app was presented above in detail with reference to the .

The mobile app is configured to connect to the kiosk and the custom kiosk interface overlay manager and utilizes the overlay interface provided by the custom kiosk interface overlay manager for the user to transact with the kiosk via the underlying existing interface of the kiosk.

In still another case the kiosk is an Automated Teller Machine ATM . In other cases the kiosk is any self service enterprise kiosk designed to provide customer information and or sell goods or services of the enterprise.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

The Abstract is provided to comply with 37 C.F.R. 1.72 b and will allow the reader to quickly ascertain the nature and gist of the technical disclosure. It is submitted with the understanding that it will not be used to interpret or limit the scope or meaning of the claims.

In the foregoing description of the embodiments various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting that the claimed embodiments have more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Description of the Embodiments with each claim standing on its own as a separate exemplary embodiment.

