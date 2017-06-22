---

title: Remote web-based visitation system for prisons
abstract: A web-based video conferencing system and method for providing remote visitation with inmates incarnated in a prison. All visitations are initiated by the inmates and no endpoint control by prison personnel is required. “Jail-hardened” terminals in the prison communicate via Internet with visitor Internet-enabled devices. Payment for services is paid by visitors using an on-line payment service relieving prison personnel of any handling of money. All calls (excluding clergy, lawyers, etc.) are typically recorded and no routine monitoring is required by prison personnel. Inmates use the “jail-hardened” terminals to initiate video conference using only a 12-key telephone style keypad. A fee-per-minute is charged. Time is tracked for each call and the call duration and remaining time for a call based upon the maximum allowed call length and an inmate's available minutes are displayed for both the visitor and the inmate.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09094569&OS=09094569&RS=09094569
owner: 
number: 09094569
owner_city: 
owner_country: 
publication_date: 20120201
---
The invention pertains to video conferencing and more particularly to a web based visitation system for use in communicating with incarcerated persons from a remote site.

When two parties want to communicate over great distances in real time the telephone has heretofore been the communication technology of choice. However advancements in communication technologies over the past several years now allow both audio and video communication between parties over great distances typically via the Internet. These forms of communication are commonly referred to as video conferencing. Modern video conferencing depending on the complexity and associated expense of the equipment involved can provide virtually real time communication among two or more parties.

Video conferencing typically requires local equipment associated with each person seeking to participate in the conference. When the conference is to be started the equipment at each location is used to call in e.g. conference in to a call center or the like. As each of these endpoints establishes a connection with the central location the video and audio signals may then be accessed by all of the participants so that a conversation with both audio and video can take place. One common type of video conferencing equipment uses especially dedicated equipment at each geographic location for the participants. Such equipment typically uses an Integrated Services Digital Network ISDN or similar data connection to transmit and receive audio video communication data during the video conference.

Unfortunately conventionally available video conferencing equipment of the prior art has a common characteristic each system requires endpoint initiation and or termination i.e. end point control for each participant in the conference. Such end point control is particularly problematic when the video conferencing system is used as a remote visitation system where one participant is incarcerated i.e. a prisoner in a jail prison penitentiary etc. .

As used hereinafter the term inmate will be applied to such incarcerated persons and the term prison will be used to refer to any and all facilities where an inmate may be incarcerated.

To allow an inmate to have end point control of a remote visitation system is universally disallowed. Prisons do not want inmates to have unrestricted access to the Internet. Consequently in such systems of the prior art prison personnel are required to handle video conference initiation and termination as well as to monitor most if not all non privileged video conferences.

However the advantages of a remote visitation video conferencing system in the prison environment are many. Often an inmate is incarcerated in a location a great distance from his family or friends. Such distances often result in visitation of the inmate being inconvenient or even impossible due to travel time and expense for friends and family. Consequently a video conference with the inmate would seem to provide an acceptable alternative to an in person visit. However the expense and complexity of traditional video visitation equipment and associated personnel cost incurred by the prison to facilitate end point control may be prohibitive. Perhaps more important is the potential security risk if an inmate has endpoint control. In conventional face to face visits conversations between inmates and their visitors are monitored to ensure that no greater security risk is created than already exists with an outsider s presence in the prison. However if endpoint control in Internet based video visitation were given to an inmate it would be difficult to effectively monitor the visit to ensure security. Potential security breaches include but are not limited to coded dialog between the inmate and a visitor as well as hand and facial gestures used to communicate prohibited information.

While traditional video conferencing equipment could potentially be used in the prison environment the above mentioned problems would still be present. To illustrate the point a video communication initiated outside of the prison over the Internet directed to an inmate using a traditional video visitation system must be received by one or more designated prison employees. The prison employee then has to contact prison employees working in the inmate s cell block and determine whether the inmate is available to receive the visit. If the inmate is available to receive a visit then the prison employees working in the inmate s cell block are then required to coordinate ushering the inmate to the designated video visitation station to receive the visit and the visit is connected. Outgoing Internet based video visitation using traditional systems also puts demands on prison personnel in that the system requires prison personnel to initiate the communication and coordinate placement of the inmate at a station within his cell block to receive the communication. Thus a traditional video visitation system using the Internet to facilitate the communication whether the communication is incoming or outgoing places a heavy labor burden on the prison. An Internet based traditional video visitation cannot be initiated directly by an inmate without prison personnel intervention because prisons will not allow unrestricted inmate access to the Internet.

One further reason traditional video conferencing would not be workable for prison visitation and other similar situations is the lack of synchronicity between data connections during the conference. More specifically as each participant in the video conference connects to the conversation a new data connection or path is created. In a prison situation at least three data paths would be present one for the inmate one for the visitor and one for the overseer monitoring the conversation. Unfortunately an inherent latency exists between these multiple connections that pose a significant security risk for the prison. Because of latency in the data path during data transmission communication is not instantaneous the delay is a function of all intermediate equipment and media along the data path. Because different routes may be taken along each data path there may exist a difference in latency and the delay experienced by each when each party is connected with a separate data path. Unfortunately this difference in latency among multiple simultaneous data paths poses a significant security risk for a prison. As a result the visitor or inmate may engage in an improper communication during the visit but the difference in latency between connections prevents the overseer from learning of the improper conduct in time to prevent it or further improper conduct from occurring.

Accordingly what is needed is an Internet based video visitation system that i permits video visits between participants that are initiated by inmates under strictly controlled parameters and ii does not require the assistance of prison personnel to effectuate the communication.

Several attempts to solve some of the problems that are solved by the present invention may be found in the prior art. For example U.S. Pat. No. 5 382 972 for VIDEO CONFERENCING SYSTEM FOR COURTROOM AND OTHER APPLICATIONS issued Jan. 17 1995 to Deno Kannes teaches a conferencing system for interactive video and preferably also audio communication which includes a composite video signal generation means. The system preferably also includes a recording unit for producing a permanent combined video and audio record of a conference. The system includes a monitor for each conferee which displays a composite video signal including a principal video image in a large picture region of the monitor screen and secondary video images in small picture regions of the monitor screen.

U.S. Pat. No. 6 844 893 for RESTAURANT VIDEO CONFERENCING SYSTEM AND METHOD issued Jan. 18 2005 to William G. Miller et al. provides a system and method that combines restaurant services with video conferencing and multimedia access for diverse customer appeal. The MILLER et al. system and method employ a number of booths in a number of restaurants whereby each booth can video conference with each other booth particularly in different time zones while also providing multi media access such as satellite TV cable broadcast TV computer programs and gaming internet access. Each booth is linked to a local area network and is equipped with a display screen and video and audio controls. The local area network of each restaurant is linked to the local area network of each other restaurant forming a corporate intranet that allows media uses and various management capabilities such as scheduling accounting security training and the like.

U.S. Pat. No. 7 046 779 for VIDEO CONFERENCE SYSTEM AND METHODS FOR USE AT MULTI STATION SITES issued May 16 2006 to Thomas H. Hesse provides a video conference system that includes at each of several sites multiple participant stations and a control station. A conference coordinator e.g. a guard or receptionist operating the control station receives notice from the control station that a scheduled conference is about to begin and directs a person identified to be a participant of the conference to a station designated by the notice. Signals from participant stations are monitored and if a participant station is determined to be unavailable the conference may be rescheduled to replace the available station with an alternate available station. Notice sufficient to direct a participant to the alternate station is provided via the control station to the coordinator. The subject of detecting availability and rescheduling alternatives may be an item of equipment or an equipment capability e.g. a recorder channel to be used for recording the conference . Higher ranking requests may force rescheduling of already scheduled lower ranking conferences.

U.S. Pat. No. 7 061 521 for VIDEO CONFERENCE SYSTEM PROVIDING PRIVATE AND ATTORNEY CLIENT PRIVILEGED COMMUNICATIONS issued Jun. 13 2006 to Michael E. Bulriss et al. teaches a conference system includes a first conference station generating at least one of audio and video signals from at least an attorney and a second conference station generating at least one of audio and video signals from the attorney s client the attorney and the attorney s client having a relationship protected by the attorney client privilege. The system also includes at least one communications link connecting the first and second conference stations that carries the audio and or video signals between the first and second conference stations. A signal processor is disposed within the communications link between the first and second conference stations to route signals between the first and second conference stations. At least one control panel communicates with the signal processor and provides control over audio and or video signals so that the attorney and the attorney s client are permitted to engage in a private communication without vitiating the attorney client privilege.

U.S. Pat. No. 7 256 816 for SYSTEMS AND PROCESSES FOR SCHEDULING AND CONDUCTING AUDIO VIDEO COMMUNICATIONS issued Aug. 14 2007 to John D. Profanchik et al. discloses methods of scheduling and conducting video visits as well as computer architecture for providing such scheduling and conducting where the participants in the visit are not required or able to interact with the audio video equipment for the initial connection to start the video visit. In some embodiments participants are also not able to interact with the equipment during the actual visit and thus the equipment employed during the video visit may be isolated from physical contact by the participants. To initiate or terminate a video visit a data center establishes a data connection with each participant and thus the flow of data between the participants moves across a computer network via the data center. The visit may be monitored in virtually real time by splitting the data transmitted between the participants and sending it to a monitoring terminal rather than establishing a separate connection for the monitoring.

United States Published Patent Application No. 2009 0228383 for SYSTEM AND METHOD FOR PROACTIVELY ESTABLISHING A THIRD PARTY PAYMENT ACCOUNT FOR SERVICES RENDERED TO A RESIDENT OF A CONTROLLED ENVIRONMENT FACILITY published Sep. 10 2009 upon application by Veronica Martinez et al. provides systems and methods for proactively establishing a third party payment account for services rendered to a resident of a controlled environment facility CEF . A campaign triggering event is detected which triggers contact of prospective third party 3party payers for a resident of a CEF in order to encourage such prospective 3party payers to establish 3 party payment accounts for the resident. In this manner the prospective 3party payers are proactively contacted prior to an expected future demand for service by the resident. A method thus comprises identifying at least one prospective third party payer for a resident of a controlled environment facility and proactively contacting the identified at least one prospective third party payer prior to demand for service by the resident to encourage the identified at least one prospective third party payer to establish a third party payment account for payment for future service expected for the resident

None of the patents and the published patent application taken singly or in any combination are seen to teach or suggest the novel Remote Web Based Visitation System for Prisons of the present invention.

The present invention provides a video conferencing system and method adapted for use in providing remote visitation of inmates incarnated in a prison. The need for prison personnel to provide endpoint control to initiate or terminate a visit is eliminated in the novel visitation system of the invention. Further all visitations are initiated by the inmates during defined visitation times established by the prison. Also importantly while this is a fee for services system with a programmable per minute charge no monies pass through the prison but rather are paid directly to the owner operator of the remote visitation system.

One or more jail hardened terminals are located typically in common areas in the prison. These terminals and all support equipment are typically provided and maintained by the system owner operator. Inmates use these jail hardened inmate visitation terminals to initiate a video conference using only a 12 key telephone style keypad to select and connect to visitors who have previously registered as an allowable visitor for the inmate.

Unless a visitor has been designated a clergy member or a legal representative with whom the inmate is entitled to privileged communication all visits are recorded. Visits with privileged visitors are not typically recorded.

Visitors need an Internet connected appliance which may be a desktop or notebook computer an Internet connected tablet or a smart phone or any other suitable device capable of supporting video conferencing across the Internet.

Visitors using PayPal or a similar on line payment system prepay for visitation minutes with an individual inmate. A per minute charge may be set for each call made. There is typically no minimum call length.

Time is tracked for each call and the call duration and the minutes remaining for a call based upon the maximum allowed call length and an inmate s available minutes are displayed for both the visitor and the inmate.

During a visit video images of both the inmate and the visitor are displayed at both the inmate terminal and the visitor terminal.

It is therefore an object of the invention to provide a web based audio video visitation system for prisons that allows video conferencing between an inmate in a prison and a visitor across the Internet.

It is another object of the invention to provide a web based audio video visitation system for prisons wherein a jail hardened terminal is provided as an inmate visitation terminal within a prison.

It is an additional object of the invention to provide a web based audio video visitation system for prisons wherein an inmate visitation terminal includes a telephone style numerical keypad or another digitized user specific input device such as but not limited to a card reader a biometric reader or other personalized device the purpose of which is to allow inmate initiation of an Internet based video visit without requiring prison personnel assistance and a corrections grade telephone handset with an armored cord.

It is a further object of the invention to provide a web based audio video visitation system for prisons wherein a visitor station is an Internet connected computer or other Internet appliance.

It is a still further object of the invention to provide a web based audio video visitation system for prisons wherein no endpoint control is required by prison personnel.

It is yet another object of the invention to provide a web based audio video visitation system for prisons wherein no monies flow through or are processed by the prison.

It is another object of the invention to provide a web based audio video visitation system for prisons wherein a prison administrator may block calls from either selected individual inmates or all inmates in the prison as well as block calls from designated visitors or all visitors.

It is an additional object of the invention to provide a web based audio video visitation system for prisons wherein a percentage of the per minute charge for visits may be paid to the prison.

It is an additional object of the invention to provide a web based audio video visitation system for prisons at no cost to the prisons.

It is an additional object of the invention to provide a web based audio video visitation system for prisons displaying real time visual images of the inmate and visitor on the visitor station video screen and on the inmate station video screen.

It is another object of the invention to provide a web based audio video visitation system for prisons that allow real time monitoring and recording by prison personnel.

The present invention provides a system for providing audio video conference visitation between an inmate incarcerated in a prison and a visitor having an Internet connected computer or other Internet appliance.

Referring first to there is shown a front elevational schematic view of a jail hardened communication station for use by an inmate using the system of the invention generally at reference number .

A jail hardened steel cabinet has a top or lid securely affixed thereto. Cabinet is typically formed from 14 gauge hardened cold rolled steel and is formed using a uni body design to prevent any seams being accessible. Cabinet is designed for ease of installation and maintenance while providing the necessary security required for equipment installed in a prison. Cabinet is typically mounted to a vertical wall not shown and is provided with five holes not shown in the back wall not shown of cabinet . Four of the holes may be keyed holes allowing cabinet to be hung on preinstalled screws or other similar fasteners not shown. However a fifth hole is a non keyed hole to prevent cabinet from being slid upward and removed from the wall. Once cabinet is hung on the wall by four screws or the like through the four keyed holes the screws may be tightened and finally a screw is placed through the non keyed hole thereby securely fastening cabinet to the wall.

Ventilation for the equipment housed in cabinet is provided by a series of offset holes not shown in an upper edge of cabinet . These offset holes are hidden by cabinet top and align with complementary offset holes not shown in cover .

Lid or top is typically secured to cabinet with a single security screw not shown that in combination with a series of interlocks not shown allow ready access to an internal region of cabinet by authorized service personnel.

The cabinet is finished with an electrostatically applied sintered metal scratch resistant finish to maintain a good cabinet appearance in a potentially hostile environment.

It is believed that numerous alternate construction methods and materials may be known to those of skill in the art. Cabinets formed from such material or construction methods may be substituted for the steel cabinet chosen for purposes of disclosure. Consequently the invention is not considered limited to the cabinet chosen for purposes of disclosure. Rather the invention is intended to include any suitable cabinet.

Openings and are provided in a front surface of enclosure for a video monitor and a camera respectively. Both openings and are covered with a transparent but destruction resistant polymer not specifically identified. Suitable transparent materials include inch thick Lexan . Lexan is a trademark of SABIC Innovative Plastics formerly General Electric Plastics brand of polycarbonate resin thermoplastic. It will be recognized that alternate material suitable for use in prisons may be known to those of skill in the art and any suitable material may be substituted for the Lexan material chosen for purposes of disclosure.

Lexan covered openings and are considered to be resistant to most physical forces applied thereto including bullets.

An institutional commercial grade telephone handset also formed from a material suitable for a jail telephone system is connected to enclosure by a steel sheathed cable and a steel lanyard not specifically identified.

A chrome steel handset cradle is provided on the front surface of enclosure to facilitate storage of handset when not in active use. Cradle is secured to cabinet in a way to render its removal difficult.

An institutional keypad is also provided on the front surface of enclosure . Keypad is also constructed as a jail hardened device to prevent vandalism or destruction. Keypad is typically a USB connected device.

A video camera typically a USB camera is housed in enclosure and aligned therein such that a camera lens not specifically identified is aimed forward through opening .

A video monitor is mounted within enclosure and a front screen area thereof is aligned with monitor opening . In the embodiment chosen for purposes of disclosure video monitor is a 20 inch video monitor forming a part of a so called all in one PC computer. An ASUS Model ET 2011 has been found satisfactory for the application. It will be recognized by those of skill in the art that other similar computers are or may become available and any suitable computer may be used. Consequently the invention is not considered limited to the ASUS computer chosen for purposes of disclosure.

An electronic unit shown schematically at reference number typically implemented as part of the all in one PC computer is housed within enclosure and operatively connected to handset camera and video monitor . Electronic units such as electronic unit are believed to be well known to those of skill in the video conferencing arts and consequently are not further discussed herein. In the embodiment chosen for purposes of disclosure electronic unit is the CPU of the all in one PC computer of which video monitor is a part.

Electronic unit includes a power supply not specifically identified that is typically connected externally to an electrical power receptacle via an electrical power cord terminating in a connector . Typically electrical power cord is not accessible to an inmate using inmate communication station . Only authorized personnel have access to electrical power cord .

In addition electronic unit includes a network communication interface not specifically identified that is typically designed to connect to an Ethernet or another standard network type via communication cable terminating in a connector . The electrical cable and connector are also inaccessible to all but an authorized person. In the embodiment chosen for purposes of disclosure connector is a standard RJ 45 8 conductor connector.

It will be recognized that other configurations for a jail hardened inmate communication stations may be substituted for the communication station chosen for purposes of disclosure. Consequently the invention is not considered limited to communication station . Rather the invention is intended to include any suitable alternate inmate communication station configurations.

Referring now also to there is shown a simplified schematic block diagram of a web enabled computer suitable for use as a visitor workstation generally at reference number . While a typical so called desktop computer configuration is shown in for purposes of disclosure it will be recognized by those of skill in the art that any Internet enabled device may be substituted therefor. Such devices include but are not limited to smartphones tablet computers netbook computers notebook computers laptop computers and dedicated Internet appliances etc.

The exemplary Internet enabled computer system has a CPU a video monitor a keyboard a pointing device e.g. a mouse and a modem each operatively connected to CPU In addition a camera and a microphone are also operatively connected to CPU . A camera and a microphone complete a computer system suitable for use as a visitor computer system. Such system topologies as well as all included and or attached components are believed to be well known to those of skill in the art. Consequently neither the system topology nor any individual component are further described or discussed herein.

Referring now also to there is shown a simplified system block diagram of the remote web based visitation system RWVS in accordance with the invention generally at reference number . For purposes of disclosure a remote web based visitation system for prisons provided by HomeWAV LLC a limited liability company of the state of Virginia located in Virginia Beach Va. is described. HomeWAV and HomeWAV Web Access Visitation are trademarks of HomeWAV Inc.

A prison facility contains one or more inmate communication stations typically disposed throughout prison . While most inmate communication terminals . . . are typically located in cell block common areas not specifically identified such terminals . . . may be placed at any other convenient locations throughout prison . In some prisons public visitation terminals not specifically identified may be located in areas of the prison accessible to the public.

Each inmate communication station . . . is connected to a network shown schematically at reference number . Network is supported by a network device typically a multiport switch. It will be recognized that numerous network topologies may be implemented within prison . Consequently the invention is not considered limited to any particular network topology or any specific networking components.

Network component is connected to an Internet interface typically a modem . The type of modem and the nature of the Internet connection depends upon the number of inmate visitation stations . . . at the prison . In the embodiment chosen for purposes of disclosure modem is a cable modem. As cable modems as well as other Internet interface devices are believed to be well known to those of skill in the art they are not further described or discussed herein. Consequently the invention is not considered limited to the cable modem chosen for purposes of disclosure. Rather the invention comprehends any and all network interface devices known and to be invented.

A prison administrator workstation PAWS may be located within prison and also connected to either network or directly to network controller e.g. switch . In alternate embodiments PAWS may have its own modem associated and connected directly to the Internet. Also PAWS may be located outside prison when desired.

An Internet connection is provided between Internet interface modem and the Internet cloud represented schematically at reference number .

A visitor workstation or Internet appliance discussed in detail hereinabove is also connected to Internet via an Internet connection . Visitor workstation is intended to represent a plurality of visitor workstations each connected to Internet .

HomeWAV website supports a web server . Web server runs application code not shown that implements the applications of the novel remote web based visitation system of the invention. In the embodiment chosen for purposes of disclosure the applications discussed in detail hereinbelow are implemented in either JAVA or PHP http www.php.net . PHP is a server side HTML embedded scripting language that provides web developers with a full suite of tools for building dynamic websites. In addition some custom Adobe Flash ActionScript codes are provided to interact with flash.homeway.com discussed in more detail hereinbelow. ActionScript is a dialect of ECMAScript i.e. it is a superset of the syntax and semantics of the language more widely known JavaScript and is used primarily for the development of websites and software targeting the Adobe Flash Player platform. ECMAScript is the scripting language standardized by Ecma International in the ECMA 262 specification and ISO IEC 16262 specifications. The language is widely used for client side scripting on the web.

It will be recognized that website design and implementation is believed to be well known to those of skill in the art. Consequently alternate web development tools languages may be utilized to develop similar applications. Consequently the invention is not considered limited to the development tools and or languages chosen for purposes of disclosure. Rather the invention is intended to include any suitable languages scripts etc.

HomeWAV website also embodies and supports storage shown schematically at reference numbers to contain application code and the databases necessary to implement the remote web based visitation system of the invention.

A second website associated with the remote web based visitation system of the invention is Flash.HomeWAV.com website . Flash.HomeWAV.com website records and stores all audio video A V visits. As later discussed certain A V visits by clergy or legal representatives may be exempt from recording. Typically all other A V visits are recorded by one or more A V servers . Storage devices shown schematically at reference numbers . . . retain A V transcripts of all visits not exempt from the recording requirement.

Finally one or more HomeWAV Administrators at workstations that include a computer and a modem and that are connected to the Internet by Internet connection provide certain gate keeping and administrative functions by interacting with HomeWAV website . Such gate keeping and administrative functions are discussed in detail hereinbelow.

The system of is suitable for practicing the method of the invention. For brevity the novel remote web based visitation system for prisons is abbreviated RWVS. RWVS operates completely differently than any prison visitation system of the prior art. Two of the important differences between RWVS and the prior art include the feature that all visitation calls are initiated by inmates with no need for any intervention by prison personnel. All calls are automatically recorded both audio and video unless the call is between an inmate and a clergy person or a lawyer or another professional who has the right to privileged communication with the inmate. A flag in the visitor record of such a visitor automatically suspends recording.

A second unique feature of the RWVS of the invention is that prison personnel are not involved in collecting or handling the fees charged for using the system. Rather RWVS is a pay for services based system wherein all money transactions are initiated by a visitor and all monies are recorded and tracked by the RWVS software. An online payment service such as PayPal is used to receive payments from visitors or potential visitors. Received payments are credited to the visitor s account for use in visiting with a particular inmate. Generally funds associated with one inmate may not be used for visitation with a different inmate. Also deposited funds are associated with the visitor making the deposit and may not be used by a different visitor for visiting that inmate.

Before the RWVS is functional administrative startup tasks must be performed both by HomeWAV administrative personnel and prison administrative personnel at each prison.

A person wishing to utilize the HomeWAV system logs into the system in one of three user categories as a visitor as an inmate or as an administrator. The features available to a visitor are first described.

Referring now also to there is shown a simplified flow chart generally at reference number of the operation of the HomeWAV features available to a visitor i.e. a person outside the prison who will communicate i.e. visit with an inmate in accordance with the method of the invention.

The visitor process starts block with a login process . is a screenshot of the HomeWAV login screen shown generally at reference number .

If the visitor is logging in for the first time block the New Visitor button is selected and the new visitor is then directed to a new visitor screen . Referring now also to there is shown a screenshot of the new visitor screen generally at reference number . A proposed user name and a password are entered. The user must then re enter the password . After that typical demographic information is entered.

If however the visitor has already registered block he she enters a user name and password and selects the Login button . In the event that the visitor has forgotten his her password the Lost Password button may be selected for password help. If Lost Password button is selected the user is asked to enter his her e mail address and a reset password request is then forwarded to that address.

Upon entry of a valid username and password and pressing the login button the visitor is logged into the HomeWAV system and immediately presented the Registered Inmate screen block .

Referring now also to there is shown a screen shot of the Registered Inmates screen . Several actions are available to the visitor proceed to the Your Account screen selectable from the Your Account tab or logout of the HomeWAV system tab . Note that the Registered Inmates tab does nothing as the visitor is already at the registered inmate screen .

The Registered Inmates screen provides information relating to all inmates with which the visitor has registered and with whom a HomeWAV visit may be conducted. The Inmate Status Ball column displays a colored ball indicating the current status of each registered inmate. The colors have the following meanings 

Red Inmate not logged on and or there are no funds available for a visit with the selected inmate. If this is so the call is not allowed 

Green Inmate is currently logged into the HomeWAV system at an inmate visitation station and there are funds available to allow a visit.

A green ball indicates that the inmate is available to initiate a call. The process whereby an inmate initiates a call is discussed in detail hereinbelow.

Available minutes column indicates the number of minutes in the visitor s account available for a visit with the selected registered inmate. Note that minutes purchased for visitation cannot be used for visitation with another inmate.

Adjacent the remaining minutes value is an Add Minutes button that allows the visitor to add additional minutes when necessary.

Selecting the Add Minutes button associated with any registered inmate transfers a visitor to an Add Minutes screen to which the user is directed.

Referring now also to there is shown an Add Minutes screen . An Order Summary block displays the selected inmate name. An Order Quantity box allows the visitor to enter the number of minutes he she wishes to purchase for visitation with the inmate.

For purposes of disclosure PayPal has been chosen as the online payment service through which a visitor may purchase minutes for a selected inmate. PayPal is believed to be well known to those of skill in the art and is therefore not further discussed herein. It will be recognized that any alternate online payment service may be used in addition to or in place of PayPal to purchase visitation minutes. Consequently the invention is not considered limited to any particular on line funds collection and or transfer agent.

Funds paid through PayPal or the like to purchase minutes are automatically transferred to HomeWAV server and are typically recorded and made available to a visitor s account for use in as little as 15 seconds.

A HomewWAV visitor is assumed to have a PayPal or other equivalent account and enters his her e mail address and password and then clicks the login button . When the PayPAl transaction has been completed the user is returned to the Registered Inmate screen .

 Call History button allows a user access to a call log for a selected inmate. Referring now also to there is shown a screen shot of a portion of a call history or call log for the selected inmate generally at reference number .

Two navigation buttons Registered Inmates and Your Account are provided. In addition a Return to Registered Inmates button performs identically to Registered Inmates button .

Call log records each show a date a duration and inmate name and the billed time for the call. Billed time is based upon the minimum number of minutes billed for a call regardless of the actual call duration. Typically there is no minimum call length.

Selecting any Your Account button for example Your Account button on Call History screen directs the user to the Your Account screen block . For simplicity not all paths to block are included on flow chart .

From Your Account screen four actions are possible. First a user may return to the Registered Inmate screen . In addition the user may select one of three other functions Add an Inmate button Delete an Inmate button and Purchase Equipment Minutes button .

If the user selects Registered Inmate button block he she is returned to Registered Inmate screen block .

If however the user selects Add an Inmate button block he see is transferred to Add an Inmate screen .

When registering a new inmate the visitor first selects the detention facility i.e. prison housing the inmate to be registered using a pull down list box .

Once the detention facility has been selected the visitor enters the inmate s first and last name respectively.

A list of inmates registered by the visitor is shown on screen each having a radio button control adjacent each listed inmate name . Only one radio button is labeled to maintain clarity of screen . Selecting the radio button adjacent the name of the inmate from list who is to be deleted and then selecting Delete Inmate button deletes i.e. unregisters the selected inmate at the HomeWAV server .

If the visitor selects Purchase Equipment Minutes button he she is transferred to the Purchase Equipment Minutes screen .

Selecting the Purchase Minutes button returns the visitor to Registered Inmates screen where button associated with the inmate name for which additional minutes are required is used to add the minutes.

A series of equipment . . . is displayed. Any equipment . . . may be purchased by selecting the associated Buy Now button . . .

As has previously been mentioned all visitation calls are initiated by an inmate. The process whereby an inmate initiates a call is described in detail hereinbelow.

To receive a call a visitor logs into the HomeWAV system as previously described and then selects the Registered Inmate screen . As previously discussed Inmate Status Ball column displays a colored ball indicating the current status of each registered inmate. Any inmate displaying a green ball is on line and may initiate a call.

When an inmate initiates a call a ringing sound is heard through speakers at the visitor station at which the visitor is logged into the HomeWAV system. A pop up box also appears on the screen showing the name of the calling inmate. An Answer button in the pop up box is selected to answer the call.

Referring now to there is shown a screen that is displayed once the call is answered. An image of the calling is displayed at the left side of screen while a smaller image of the visitor is displayed at the right side of the screen .

The time remaining for the call based upon the maximum allowable call length is displayed at reference number .

Finally the number of minutes remaining in the account for the inmate to which the visitor is currently talking is displayed at reference number .

Up to this point the HomeWAV system has been described from the perspective of a visitor. The system as utilized by an inmate is now described. Referring now also to there is shown a screenshot of an inmate sign in screen generally at reference number . A schematic representation of keypad forming a part of a jail hardened terminal forming an inmate communication station as shown in . Keypad is the only device available to an inmate with which to communicate at a jail hardened inmate communication station .

A single field Inmate ID is available on screen . The inmate must enter his her ID number using keypad . As there is neither an Enter key nor a Backspace key on keypad the is used as an enter key while the is used as a backspace key. Consequently when the inmate has entered his her ID number he she presses the key on keypad .

The inmate ID number is validated and if not recognized the inmate must reenter his her ID number. Once the inmate ID is validated an inmate PIN screen is displayed.

Referring now also to there is shown an Inmate PIN screen . The inmate is instructed REFERENCE NUMBER to ENTER his her PIN. The inmate then enters his her PIN in field using as an enter key.

Once the entered PIN is verified a screen appears that displays a list of the inmate s visitors and their availability status.

Referring now also to there is shown a screenshot of a Begin Visit screen . The inmate is provided with a reminder that ALL VISITS ARE RECORDED. However as discussed hereinbelow certain visits with clergy legal representatives etc. are generally not recorded.

The names of one or more potential visitors are displayed column each with an associated visitor status ball . A particular number is assigned to each listed visitor which number must be entered on keypad to initiate a visit with that visitor.

Assuming that the visitor status ball is green pressing the associated number initiates the visiting process. If the visitor status ball is red the visitor is not logged on and or there are no funds available for a visit with this visitor and accordingly no visit can be initiated. In such an event the inmate can select an option to send a text message to the red status visitor advising the visitor that the inmate is ready and desiring to initiate a visit. Referring now also to there is shown a screenshot of A Begin Visit screen having a pop up box displayed thereupon. Pop up box shows the name of the visitor being called and the number of rings .

Referring now also to there is shown a screenshot of an Inmate Visit screen . An image of the called visitor is displayed at the left side of screen while a smaller image of the inmate is displayed at the right side of screen .

The remaining available minutes for the call are displayed beneath image . The remaining time is based upon the maximum call length allowed as well as the minutes remaining in the visitor s account for the calling inmate.

The third class of HomeWAV users is administrators. Some functions performed by HomeWAV administrative personnel using management software residing on web server associated with the HomeWAV.com website include 

There are currently three classes of administrator defined within the HomeWAV system. The names and privileges i.e. the allowable operations of each of these classes of administrator are 

An administrator logs into the HomeWAV system using login screen . Once the administrator s user name and password are validated he she is immediately transferred to the Manage Detention Facility screen.

 Manage Inmates buttons Video Playback button and Manage Operators button all direct the operator to different screens each discussed in detail hereinbelow. Logout link logs the operator out of the HomeWAV system.

Displayed on Manage Detention Facility screen are the Facility Name the Facility Location Maximum Call Length Cost per Minute and All Calls Disabled .

Pressing Update Detention Facility Settings button directs the operator to Update Detention Facility Settings screen .

The operator may return to Manage Detention Facility screen by selecting button . Other actions Manage Inmates Video Playback and Manage Operator may be selected using buttons and respectively.

If the operator selects Manage Inmates using button from any screen he she is directed to the Manage Inmates screen .

A list of inmate names reflects the registered inmate population of the selected detention facility. A column of associated PINs Personal Identification Numbers Available Minutes and Calls Disabled Status are associated with each inmate name. Each inmate name also has a Disable Calls button and a Reset Pin button .

Selecting either Disable Calls or Reset PIN buttons respectively does not transfer the operator to a different screen but merely presents a pop up box requesting confirmation of the action.

As with previous screens the operator may return to Manage Detention Facility screen by selecting button . Other actions Manage Inmates Video Playback and Manage Operators may be selected using buttons and respectively.

If an operator selects Video Playback from any screen using the Video Playback button he she is transferred to Video Playback screen .

A pull down list box activated by control displays all inmates of the detention facility that have registered with the HomeWAV system. Selecting an inmate from the list of inmates transfers the operator to Video Display screen .

As with previous screens the operator may return to Manage Detention Facility screen by selecting button . Other actions Manage Inmates Video Playback and Manage Operators may be selected using buttons and respectively.

Referring now to there is shown a screenshot of the Video Display screen . The name and PIN of the selected inmate for whom recorded video is to be viewed is displayed. A matrix of calls with the most recent call at the top of the list is displayed. The columns of the call matrix includes Date Visitor Inmate and Duration . A fifth column includes either a Play button or status information if recorded data for the call is not available.

Selecting Play button associated with a desired call initiates playback of the selected audio video file.

A Call Details area not specifically identified contains date and start time and date and end time of the selected call.

A Visitor video display area and an Inmate video display area display respective visitor and inmate recorded video.

As with previous screens the operator may return to Manage Operators screen by selecting button . Other actions Manage Detention Facility Manage Inmates and Video Playback may be selected using buttons and respectively.

If Manage Operators button is selected from any screen the operator is transported to Manage Operators screen .

Referring now also to there is shown a screenshot of the manage operators screen . An Add Operator button transfers the operator to Add Operator screen described in detail hereinbelow.

A list of operators is displayed. Information displayed in operator list includes Username E Mail Is Controller can make modifications Is monitor can only view and Options . An Edit button associated with each Username is located in Options column .

Selecting Edit column associated with an operator Username transfers the operator to Edit an Operator screen .

Referring now also to there is shown a screenshot of Edit an Operator screen . The Username the E Mail address the Password and the Password Confirmation fields are displayed.

A pair of check boxes respectively allow the operator associated with the selected Username to Modify Facility Settings and Only Display Settings .

When all information on screen is correct the operator selects the Save Changes button to save the record with all changes.

Referring now also to there is shown a screenshot of the Add an Operator screen . As with previous screens the operator may return to Manage Detention Facility screen by selecting button . Other actions Manage Inmates Video Playback and Manage Operators may be selected using buttons and respectively.

Since other modifications and changes varied to fit particular operating requirements and environments will be apparent to those skilled in the art the invention is not considered limited to the example chosen for purposes of disclosure and covers all changes and modifications which do not constitute departures from the true spirit and scope of this invention.

Having thus described the invention what is desired to be protected by Letters Patent is presented in the subsequently appended claims.

