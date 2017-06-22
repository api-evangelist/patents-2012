---

title: Apparatus and method for a web programmable telephone
abstract: A web programmable telephone and a method for operating a web programmable telephone are disclosed. In one embodiment of the present invention, a voice module of a wireless household telephone is controlled by an internal web module that can retrieve and execute data operations from a remote portal or server thus adding data functionality to the conventional functions of a telephone. The programmable web module controls all functionality of the web programmable telephone so that every function of the telephone can be programmed and customized by a user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08538475&OS=08538475&RS=08538475
owner: TP Lab, Inc.
number: 08538475
owner_city: Palo Alto
owner_country: US
publication_date: 20120418
---
This application is a continuation of co pending U.S. patent application Ser. No. 12 900 310 filed on Oct. 7 2010 which in turn is a continuation of U.S. patent application Ser. No. 12 179 269 filed on Jul. 24 2008 issued as U.S. Pat. No. 7 835 765 which in turn is a continuation of U.S. patent application Ser. No. 11 001 407 filed on Nov. 30 2004 issued as U.S. Pat. No. 7 613 477.

This invention relates generally to telecommunications more specifically to an apparatus combining a web module and a voice module allowing the web module to control the voice module to establish voice functionality such as making a call receiving a call dropping a call accessing a contact list and more sophisticated data functionality.

Cordless telephones have become a commodity household item. The convenience and flexibility provided by a telephone handset not physically attached to a telephone jack or an electrical outlet fits well with modern life. In addition the price of cordless telephones has been declining steadily while the quality has been improving. Nevertheless cordless telephones are primarily designed for voice communication. Their ability to handle data is extremely limited. The most common data application with current cordless telephones is limited to simple memory stored speed dial numbers.

As consumers grow more technologically savvy they are continuously seeking more sophisticated integration of voice data and other features to make life more convenient and productive. The trend is apparent in mobile voice services as well as entertainment devices such as MP3 music players and portable video players. Currently cellular telephones are fully capable of supporting voice communication features such as voice tags as well as data applications such as text picture and video messaging and Internet browsing. The differences in capabilities between household telephones and cellular telephones represent an interesting contrast of otherwise similar modern conveniences. Therefore there is a need for a household telephone with data technologies to be in par with other integrated data and voice technologies.

This invention resides in an apparatus and method to make and operate a web programmable telephone. A programmable module that is linked to a remote server or portal controls all conventional telephone functionality of a voice module. Additionally sophisticated programmable functionality can be added to a telephone by enabling a web interface capable of retrieving loading and executing programs from remotely stored web pages. Such added data functionality includes but is not limited to interactive multimedia interface home control and security interface and more sophisticated telephone operations such as display of detailed caller information.

In one embodiment the voice module combines the Media Service Provider MSP and the Telephony Service Provider TSP .

In one embodiment the controlling interface presents the call controlling interface similar to that of Q.931.

In one embodiment the controlling interface is a CTI or CTI equivalent interface. The implementation of the controlling interface should be obvious to those skilled in the art.

The telephony processor can apply different processing to the audio signals received from the microphone and the signals received from the signal interface depending on the different types of signal interface .

In one embodiment the signal interface is a digital signal interface DS. The telephony processor performs analog to digital conversion on the audio signals from the microphone and digital to analog conversion on the signals from the signal interface .

In one embodiment the signal interface is a wireless interface supporting 900 MHz 2.4 GHz 5.8 GHz and DECT frequency. These are typical spectrum for cordless telephones. Other equivalent frequencies can also serve as the signal interface .

In one embodiment the signal interface is a voice over IP interface. The telephony processor converts the analog audio signals to digital format formats the bits into proper RTP Real Time Protocol packets and transmits the packets in an IP network. In the reverse direction the telephony processor receives the IP packets from the signal interface extracts the RTP packets further extracts the digital signals within the RTP packets applies jitter and packet loss control converts the digital signals into analog signals and plays the analog signals onto the speaker.

In one embodiment the telephony processor compresses the digital content before formatting into RTP packets and decompresses the content from the RTP packets. The telephony processor the speaker the microphone and the signal interface are common in the telecommunications industry. Implementation of such should be known to those skilled in the art.

In one embodiment the browser is a Java run time engine which communicates to other Java run time engines through Java specific and recommended protocols such as RMI JINI and LDAP.

In one embodiment the browser is a .NET environment. The browser connects to the display for presenting the web page content. There are different possible types of displays including text display graphical display monochrome and color.

Optionally display may include a speaker or an audio out jack for playing audio content. With audio capability a web programmable telephone can be used to play music files from a central music file server. A web programmable telephone can be programmed to receive and decode music files from a server through network interface and played on the optional speaker or audio out jack of display .

Optionally a web programmable telephone can be programmed to play music broadcast from a central portal to the signal interface and played on the speaker or an optional audio out jack capable of be coupled to external speakers or audio system.

In one embodiment a web programmable telephone can be programmed to act as room monitor wherein microphone sends audio signals to telephony processor for appropriate processing which then broadcast the signal through signal interface to a central portal or another web programmable telephone as needed.

In one embodiment a web programmable telephone can be use both network interface and signal interface to act as a multimedia interface to files on a central server. In such an embodiment single player and multi player games could be played where the visual and controller data can be handled by the web module and the audio content is delivered through voice module .

In one embodiment a web programmable telephone can be programmed to act as a home security interface providing for data code transmission through input subsystem of web module and optional added voice recognition security capabilities through voice module .

In one embodiment a web programmable telephone can be used to browse the Internet. Browser can run an Internet browsing page in which a user can enter a desired domain name or IP address of a website through input subsystem and the browser would then retrieve data from a website through network interface . The data can then be displayed on display or played on either an optional speaker built into display or played on speaker of the voice module of the web programmable telephone.

In one embodiment there is no visual display. Web page content is played to the speaker only. The browser receives user input from the input subsystem . The input subsystem may include a keypad a keyboard a touch screen a touch screen for use with a stylus for input or a microphone. Furthermore the browser accesses the data store for configurations and other data.

The network interface connects the browser to other computing devices in one more networks. The network interface includes one or more network access methods including but not limited to wired network such as Ethernet or wireless networks such as CDMA 1x GPRS 3GPP Bluetooth infra red Wi Fi. The network interface contains the necessary protocol stacks to communicate with other computing devices so that a communication session can be established between the browser and a computing server.

In one embodiment the browser is a Web browser and a computing server is a Web server. The network interface accesses the data store for configuration and other data.

The typical telephone functions such as making a telephone call receiving a telephone call and dropping a telephone call are handled by the three web pages dialing page receiving page and disconnecting page respectively. The processing of these pages is illustrated later in this description.

When the web programmable telephone is powered on browser is initialized which then initializes the web module . The browser determines from the configuration stored in data store the location of the web server.

In one embodiment the user selects one web server when there are many web servers capable of serving the web programmable telephone.

After the web programmable telephone is initialized the browser gets the receiving page from the web server. The main function of the receiving page is to receive a call. The processing of receiving a call is illustrated in . Upon successful receipt of an incoming call the receiving page instructs the browser to get the disconnecting page from the web server. The main function of the disconnecting page is to drop a call. The processing of dropping a call is illustrated in . After the telephone call is dropped the browser gets the receiving page from the web server in order to receive the next telephone call. When a user directs the web programmable telephone to make a call the browser gets the dialing page from the web server. The main function of dialing page is to make a call. The processing of making a call is illustrated in . Upon success of making a call the browser gets the disconnecting page from the web server in order to drop a call.

Typically the web module will cycle through the processing of the dialing page receiving page and disconnecting page until the web programmable telephone is powered off.

In one embodiment the web programmable telephone allows the user to access a contact list page from the web server. The browser gets the contact list page from the web server. An example of processing a contact list page is illustrated in .

In one embodiment the web programmable telephone supports other voice functionalities such as voice mail teleconferencing and call forwarding. Additional web pages can be obtained from the web server. The browser will obtain these web pages as instructed by other web pages. These web pages employ the programmability of the HTML XML Java JavaScript and other hypertext and scripting languages supported by the browser as well as the programmability of the controlling interface .

In one embodiment the receiving page after accepting the telephone call instructed the browser to get the disconnecting page . In the same embodiment the disconnecting page instructs the browser to get the receiving page when the telephone call is terminated. While the browser is displaying the receiving page the receiving page receives the input that the user picks up the telephone and instructs the browser to get the dialing page

In one embodiment the receiving page displays a Call button. Upon receiving a user input of the selection of the Call button the receiving page instructs the browser to get the dialing page

In embodiment the dialing page plays the dial tone as soon as it is loaded into the browser. Optionally the dialing page plays the dial tone after it receives partially or completely the input. Then the dialing page invokes the controlling interface to initiate a telephone call to the calling telephone number. Upon receiving the completion indication of the telephone call initiation from the controlling interface the dialing page asks the browser to get the disconnecting page .

Optionally dialing page will include an option to dial two or more telephone numbers for the purpose of conducting a teleconference call.

Optionally a separate teleconferencing page that can be called from dialing page can handle teleconferencing. The teleconferencing page can be implemented in a number of ways depending on the telephony system to which the web programmable telephone is connected.

In one embodiment the web programmable telephone is connected to two or more distinct telephone lines and the teleconferencing page would place a call to two or more of those lines such that one or more of the people called can participate in the teleconference conversation.

In one embodiment the web programmable telephone is connected to a telephone system that controls the teleconferencing. The teleconferencing page would provide the telephone numbers to the telephone system such that one or more of the people called could participate in the telephone conversation.

Optionally the teleconferencing page can designate which of the telephone numbers called for a teleconference will have full or limited participation in the teleconference call. In the case that the number called is designated as a full participant in the teleconference then the person called on that number would be able to hear and respond to every other person in the teleconference. In the case that the number called is designated as a limited participant in the teleconference then the person called on that number would only be able to hear or respond to a limited number of teleconference participants.

Optionally the dialing page will include an option to dial into the either a service provider voice mail system or connect to a telephone answering machine.

In one embodiment the dialing page contains an option for the user to choose a telephone number from a contact list. When the user selects the option the dialing page asks the browser to load the contact list page . The processing of the contact list page is described later in .

In one embodiment the browser loads the dialing page with a default calling telephone number. The user confirms the calling telephone number. The dialing page proceeds to make the telephone call as described above. This embodiment is used for example after the user selects the calling telephone number from the contact list page .

Optionally the dialing page automatically makes the telephone call with the default calling telephone number without asking the user for confirmation.

Optionally the dialing page invokes the controlling interface to play the dial tone before prompting the user for the calling telephone number or confirmation.

In one embodiment the incoming call indication includes information about the caller. The incoming call information includes for example the caller identity. Upon receipt of the incoming call indication from the controlling interface the receiving page retrieves any given incoming call information indicated by the controlling interface .

In one embodiment the receiving page uses the incoming call information such as the caller identity or the calling telephone number to determine a ring tone to play.

In one embodiment the receiving page displays an incoming call indication to the display . The display can be a flashing LED light. The display can also be an icon or a digital image on the display .

The receiving page waits for the user to pick up the web programmable telephone to answer the incoming call.

In one embodiment when a user picks up the web programmable telephone the receiving page immediately turns off the display of an incoming call indication. It then invokes the controlling interface to accept the telephone call.

In one embodiment the receiving page only displays an incoming call LED. When a user picks up the web programmable telephone the receiving page displays the incoming call information.

In one embodiment the receiving page posts a query using the incoming call information to a web server. The web server may have a telephone directory containing names addresses and other personal and business information about the caller. The web server responds to the query with the found additional information. The receiving page displays the information to the display .

In one embodiment the receiving page asks the browser to load a different receiving page that contains the additional caller information. Upon reviewing the additional caller information the user confirms to accept the telephone call. The receiving page then invokes the controlling interface to receive the telephone call.

While the receiving page is waiting for an incoming call if the user picks up the web programmable telephone the receiving page asks the browser to load the dialing page . In another embodiment the user presses the on button to indicate to the receiving page to ask the browser to load the dialing page .

In one embodiment the user touches an Off button on input subsystem . When the disconnecting page receives the input from the input subsystem it invokes the controlling interface to disconnect the telephone call.

There are a number of embodiments to handle the possible scenario in which the other party drops a call first.

In one embodiment the disconnecting page does not detect the situation. The user eventually realizes the other party is no longer on the telephone call. The user presses the off button to drop the call. The disconnecting page proceeds the processing as described previously.

In one embodiment the voice module monitors the call and detects a long silence period. The voice module determines the other party has either dropped the call or has no interests in continuing the call. The voice module indicates to the disconnecting page of the dropped call event. The disconnecting page displays the indication of the dropped call event to the user and prompts the user to then proceed to drop the call as described above.

In one embodiment telephone being called is connected to a telephone system that will generate a disconnect signal such as a dial tone. The voice module detects the disconnect signal or indication through the signal interface and further indicates to the disconnecting page through the controlling interface that the call has been disconnected. The disconnecting page indicates to the user of the call drop and prompts the user to drop the call as described above.

In one embodiment the disconnecting page invokes the controlling interface to ask the voice module to disconnect the call. The disconnecting page then informs the user that the call is dropped. After the call is disconnected the disconnecting page asks the browser to load the receiving page to wait for an incoming call.

In one embodiment there is an option on the dialing page for the user to access a telephone list. When the user selects the telephone list option the browser will load the contact list page from a web server through the network interface . The user navigates the contact list page and selects a number to dial. The contact list page asks the browser to load the dialing page with the calling telephone number. The dialing page then prompts the user to confirm the number and makes the call as illustrated in .

In one embodiment the dialing page without prompting user confirmation automatically makes the call as illustrated in .

In one embodiment the contact list page allows the user to make modification to the contact list page entries by accepting user input from the input subsystem. The modification is posted by the browser to a web server specified in the contact list page . Such implementation should be obvious to those skilled in the art.

In the above illustrations the web programmable telephone is used to make regular telephone calls. In one embodiment a web programmable telephone is used only for receiving calls. Receiving page does not perform any action to make a call when the user picks up the telephone.

Optionally receiving page displays no options for the user to make a call. In such an embodiment it is possible to combine the receiving page and the disconnecting page into a single page.

In one embodiment the web programmable telephone is used only for making calls. The receiving page always rejects incoming calls indicated by the controlling interface .

In one embodiment the web programmable telephone supports multiple lines and can handle two telephone calls simultaneously. The browser runs multiple pages simultaneously. A user can make a telephone call using the dialing page while on another call using the disconnecting page .

In one embodiment the browser handles the multiple pages by having multiple processing threads. In such an embodiment the user is on a call conducting the telephone conversation while browser is displaying the disconnecting page in one processing thread another processing thread of the browser is processing the receiving page . When incoming call event occurs receiving page instructs the browser to alert the user of an incoming call. An option to instruct browser to switch to the receiving page is displayed. Receiving page would then display an option to accept or to decline the call.

In one embodiment the user can access the contact list page while she is conducting a telephone conversation.

In a different embodiment the browser handles a plurality of processing threads allowing the user to handle a plurality of simultaneous activities.

Foregoing described embodiments of the invention are provided as illustrations and descriptions. They are not intended to limit the invention to precise form described. In particular it is contemplated that functional implementation of invention described herein may be implemented equivalently in hardware software firmware and or other available functional components or building blocks and that networks may be wired wireless or a combination of wired and wireless. Other variations and embodiments are possible in light of above teachings and it is thus intended that the scope of invention not be limited by this Detailed Description but rather by Claims following.

