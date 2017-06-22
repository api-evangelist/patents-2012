---

title: Method and system for SMS messaging verification
abstract: A method and system for testing a SMS text messaging network is disclosed herein. The method and system allows for real-time testing of the mobile terminated (“MT”) and mobile originated (“MO”) delivery delays across the major American mobile phone carriers, and accurately measures the progress on SMS broadcasts and records when a broadcast has been completed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08463306&OS=08463306&RS=08463306
owner: Mobivity, Inc.
number: 08463306
owner_city: Chandler
owner_country: US
publication_date: 20120521
---
The present application claims priority to U.S. Patent Application No. 61 488 767 filed on May 22 2011 which is hereby incorporated by reference in its entirety.

Text messaging campaigns have become routine to market advertise a product service political position political candidate and the like. Organizations whether companies non profits political parties unions broadcasters schools and the like spend enormous resources trying to get their message to their intended audience. Many times these text messaging campaigns are time sensitive. For example if a political organization wants an intended audience to watch to a broadcast of a candidate the text messaging campaign would be worthless if the text message informing the intended audience of the broadcast wasn t received by the intended audience until after the broadcast ended.

Interactive voice response IVR is a telephone technology in which a user uses a phone to interact with a database to acquire information.

Hypertext Transfer Protocol HTTP is a set of conventions for controlling the transfer of information via the Internet from a web server computer to a client computer and also from a client computer to a web server.

Internet is the worldwide decentralized totality of server computers and data transmission paths which can supply information to a connected and browser equipped client computer and can receive and forward information entered from the client computer.

FTP or File Transfer Protocol is a protocol for moving files over the Internet from one computer to another.

Application Programming Interface API is a collection of computer software code usually a set of class definitions that can perform a set of related complex tasks but has a limited set of controls that may be manipulated by other software code entities. The set of controls is deliberately limited for the sake of clarity and ease of use so that programmers do not have to work with the detail contained within the given API itself.

Direct Inward Dialing DID involves a carrier providing one or more trunk lines to a customer for connection to the customer s private branch exchange PBX and a range of telephone lines are allocated to this line.

Voice over Internet Protocol VoIP relates to communications transmitted over the Internet such as SKYPE.

User Interface or UI is the junction between a user and a computer program. An interface is a set of commands or menus through which a user communicates with a program. A command driven interface is one in which the user enter commands. A menu driven interface is one in which the user selects command choices from various menus displayed on the screen.

Web Browser is a complex software program resident in a client computer that is capable of loading and displaying text and images and exhibiting behaviors as encoded in HTML HyperText Markup Language from the Internet and also from the client computer s memory. Major browsers include MICROSOFT INTERNET EXPLORER NETSCAPE APPLE SAFARI MOZILLA FIREFOX and OPERA.

Web Server is a computer able to simultaneously manage many Internet information exchange processes at the same time. Normally server computers are more powerful than client computers and are administratively and or geographically centralized. An interactive form information collection process generally is controlled from a server computer to which the sponsor of the process has access.

The prior art has failed to provide a universal method and system for verification of text messaging delays.

An Object of the invention is to measure the mobile terminated MT and mobile originated MO delivery delays across the four major American mobile phone carriers VERIZON AT T T MOBILE and SPRINT.

Another object of the invention is to accurately measure progress on SMS broadcasts and record when a broadcast has been completed.

Another object of the invention is to detect when MOs and MTs are not received by a certain threshold time and notify an operator.

Having briefly described the present invention the above and further objects features and advantages thereof will be recognized by those skilled in the pertinent art from the following detailed description of the invention when taken in conjunction with the accompanying drawings.

A preferred embodiment of the present invention is a verification of the timeliness of a text messaging system. At some specific interval every five minutes a ping service records a timestamp in a database and receives a unique identification for the specific ping request.

An ADROID SMS PONG app is triggered upon receipt of the SMS message to 772937 short code and then calls the PONG.HTTP service over HTTP with the id provided in the SMS text message.

The ANDROID app is preferably installed on customer mobile phones at various geographic locations with various carriers for greater robustness of the verification system.

In one example a C4 account for two campaigns in it was created with one campaign for a PING service and one for a scripted sanity check.

The time between pnig table createTime and the corresponding PONG HTTP response Time is MT dealy. The time between PONG HTTP repsonseTime and the PONG SMS responseTlme is the MO dealy.

The present invention preferably does not need a newly created infrastructure and can be implemented using an existing communications infrastructure.

Preferred telephonic computing devices utilized with the present invention include the IPHONE smartphone from Apple Inc. BLACKBERRY smartphones from Research In Motion the ANDROID smartphone from Google Inc. the TRE smartphone from Palm Inc. and many more.

From the foregoing it is believed that those skilled in the pertinent art will recognize the meritorious advancement of this invention and will readily understand that while the present invention has been described in association with a preferred embodiment thereof and other embodiments illustrated in the accompanying drawings numerous changes modification and substitutions of equivalents may be made therein without departing from the spirit and scope of this invention which is intended to be unlimited by the foregoing except as may appear in the following appended claim. Therefore the embodiments of the invention in which an exclusive property or privilege is claimed are defined in the following appended claims.

