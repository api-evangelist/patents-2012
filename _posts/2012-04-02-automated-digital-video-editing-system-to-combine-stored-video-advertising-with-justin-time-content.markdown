---

title: Automated digital video editing system to combine stored video advertising with just-in time content
abstract: A system and method are provided for an automated digital video editing system that can combine previously stored video advertising with just-in-time content video, such as breaking news, sports, traffic and weather. The system and method can deliver the combined video to mobile devices in accordance with demographic, geographic, or other criteria selected by the advertiser.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08554054&OS=08554054&RS=08554054
owner: 
number: 08554054
owner_city: 
owner_country: 
publication_date: 20120402
---
This application claims the benefit of U.S. Provisional Patent Application No. 61 470 104 filed Mar. 31 2011 the disclosure of which is incorporated herein by reference in its entirety.

This invention relates to an automated digital video editing system and in particular to systems and methods for combining video advertising with just in time content for rapid distribution to mobile devices.

Broadcasters seeking to deliver video to mobile devices face many difficulties. Recent surveys found that 234 million Americans used mobile devices. However only one out of three have access to the Internet. Furthermore 2 out of 3 users cannot receive most videos. Barriers to entry include the fact that there are numerous carriers devices operating systems and features so that a solution that works for one user may not work for another. Rather than the trend favoring interoperability the situation is growing worse due to competing technologies and loose compliance with industry standards.

In addition combining advertising with content in the same format has traditionally been labor intensive and has taken considerable time. Prior art methods have either presented breaking news sports traffic and weather without relevant advertising content or else have combined the content with relevant advertising after a significant delay in time.

It is therefore an object of the present invention to provide a comprehensive solution that can deliver video to mobile users regardless of carrier make model or type of mobile device operating system or features or type of mobile device plan and to do so with an incorporation of relevant advertising in a timely fashion. Another object is to manage the statistics of such advertisements.

The above objects and further advantages are provided by the methods and systems of the invention for improved delivery of video programming and advertising to mobile users.

According to one aspect of the present invention a system and method are provided for delivering video to mobile users regardless of carrier make model or type of mobile device operating system or features or type of mobile device plan. A further advantage can be obtained by reaching all mobile devices without the need to install any applications onto the device.

It is another object of the present invention to provide for secondary content dissemination such as peer to peer forwarding allowing support for viral video and social media.

It is another object of the present invention to provide for managing the advertising statistics so that advertisers can judge the efficacy of an advertisement or advertising campaign and so that a user can track how far an advertisement has been socially disseminated through viral video and social media.

It is a further object of the present invention that broadcasts be upgradeable to meet the requirements of device upgrades emerging devices and media protocols.

It is a further object of the present invention to integrate advertising into the broadcast of content such that advertising media is stored and scheduled by target demographic geography and or news topic as requested by the advertiser and then paired with the relevant programming as it occurs and delivered to the targeted mobile users. The action can be user initiated or automated.

It is a further object of the present invention to integrate custom links forms surveys and barcodes with the delivered video content and advertising allowing the mobile user to respond directly to the network and or advertiser with text photo or video. Mobile analytics can record the user responses.

The present invention broadly comprehends an automated digital video editing system to combine stored video advertising with just in time content for rapid distribution to mobile devices.

Reference will now be made in detail to implementations of the invention examples of which are illustrated in the accompanying drawings.

In step a user uploads an advertising video into a computer memory for example via an Internet server. The user could be the advertiser. Alternatively the user could be the content provider who has obtained the advertising video from the advertiser for example if the content provider insists on approving an advertising video before allowing it to be attached to the content provider s programming . The method supports the upload of the advertising video in a broad range of video formats such as AVI MPEG etc. . The computer memory that stores the advertising video can be located in the physical vicinity of the computer processor that is performing the steps of this embodiment of the invention. Alternatively the computer memory that stores the advertising video can be located remotely from the computer processor for example in an outside server that is coupled to the computer processor via the Internet or other connection. The video can be uploaded via an upload form via an application programming interface API or by storing it in a secure location that can be accessed.

In step the advertising video of step is assigned a unique identifier via a subroutine that runs on a computer processor that is associated with the computer memory.

In step a user provides parameters for broadcasting the advertising video which parameters are stored into a computer memory. These parameters can include the content provider or providers to be associated with the advertising video the number of plays purchased the days of the week and or hours of the day in which the advertising video is to be broadcast a particular subgroup of the subscriber base that should receive the advertisement such as subscribers in a particular geographic region the types of programming for which the advertising video will be broadcast such as breaking news sports highlights weather reports traffic reports action buttons that should be added for example Click here to reach advertiser click to reply to news provider etc. and whether the advertising video should be placed at the beginning end or both beginning and end of the content video.

The steps of this method do not necessarily need to be performed in the order presented. For example step can be performed concurrent with the upload of the advertising video in step . In such a case step of assigning a unique identifier to the advertising video can occur after step . In another example the advertising video can be uploaded in step by the content provider with the unique identifier of step then passed to the content provider so that it can approve the use of the advertising video after which point step can be performed. In yet another example the advertising video can be provided from the advertiser to the content provider which will approve the advertising video and then upload it in step with step either preceding or following step . As can be seen the method allows for great versatility.

In step a subroutine executed in the computer processor analyzes the parameters stored in step and places the advertising video into a queue for integration with content video based upon the identified content provider s types of programming days of the week hours of day geographic limitations and so forth.

In step the advertising video is decompiled and normalized into a universal format such as AVI in preparation for joining together with the content video. Any of a number of video editors can be used for this purpose such as FFmpeg and Apple Quicktime. The video editing software is initiated to automatically convert the video and the end result is stored in a special directory. The invention records the file properties name size the date and time taken in length original format etc. .

In step the advertising video can be edited if desired for example by adding a bug or logo to the advertising video. This optional step is performed during the normalization action within step .

In step action buttons that were identified in step are created containing any specific requirements of the advertiser. The action buttons can be associated with the advertising video with the content video or with both. In another embodiment an advertising video can be presented before the content video with the same advertising video presented after the content video and an action button only presented with the second presentation of the advertising video. In yet another embodiment an advertising video can be presented before the content video with a different advertising video presented after the content video and an action button only presented with the second advertising video. This step can be carried out before and during the normalization process of step . When the user inputs any special requirements they are performed immediately and if necessary are performed in the background while other tasks are being performed i.e. through multitasking.

In step a content programmer such as a news organization or media company uploads a content video into computer memory for example via Internet server. The programmer will also identify what type of content this is such as breaking news weather traffic sports etc. . Depending on the format of the content video and the quality provided the content video can also be subjected to decompilation and normalization into the same universal format that was selected for the advertising video in step .

In step the system selects the next advertising video in the queue that matches the content provider and type of programming.

In step the advertising video is automatically edited to the beginning the end or the beginning and end of the content video as was specified in step forming a joined video. Again any of a number of video editors can be used for this purpose including FFmpeg and Apple Quicktime.

In an alternate embodiment a first advertising video can be integrated at the beginning of the content video and a second advertising video can be integrated at the end of the content video. For example when the content video is a winter storm advisory or traffic advisory it can be proceeded with a first advertising video Michelin BLIZZAK studless ice and snow winter tires feature a patented MULTICELL compound that contains millions of microscopic pores to help grip ice without the use of studs. Following the content video of the weather or traffic report a second advertising video can be For more information about Michelin BLIZZAK studless ice and snow winter tires press the action button. 

In yet another alternate embodiment any number of content and advertising videos can be combined. For example two advertising videos can be presented and then a content video and then another advertising video. The content video can also be broken into two or more pieces with one or more advertising videos inserted between the pieces.

In step action buttons created in step are integrated into the joined video as specified. As noted earlier the action button could be associated with an advertising video with the content video or with both.

In step the joined video is converted into a format or formats best suited for mobile device playback. Once again any of a number of video editors can be used including FFmpeg and Apple Quicktime.

In step the joined video is sent to the relevant list of mobile subscribers. The video can be distributed directly to mobile subscribers or alternatively can be forwarded with the phone numbers of subscribers through an aggregator s API for distribution to mobile subscribers.

In step users can reply via the action buttons using text or video which is then sent back to the content provider for aggregation or integration into their webs sites or other media. The replies are stored in a mail database or other database. Advertisers can view the replies using any of a number of viewing systems for example they can see the replies in a discussion tree format.

Module receives an advertising video for example via an upload form via an API or from a secure location and stores this into a computer memory.

Module receives parameters for broadcasting the advertising video which parameters are stored into a computer memory. These parameters can include the content provider or providers to be associated with the advertising video such as ESPN CNN etc. the number of plays purchased the days of the week and or hours of the day in which the advertising video is to be broadcast a particular subgroup of the subscriber base that should receive the advertisement such as subscribers in a particular geographic region the types of programming for which the advertising video will be broadcast such as breaking news sports highlights weather reports traffic reports action buttons that should be added for example Click here to reach advertiser click to reply to news provider etc. and whether the advertising video should be placed at the beginning end or both beginning and end of the content video.

Module analyzes the parameters stored by module and places the advertising video into a queue for integration with content video based upon the identified content provider s types of programming days of the week hours of day geographic limitations and so forth.

Module decompiles and normalizes the advertising video into a universal format such as AVI in preparation for joining together with the content video. Any of a number of video editors can be used for this purpose such as FFmpeg and Apple Quicktime. The video editing software is initiated to automatically convert the video and the end result is stored in a special directory. The file properties name size the date and time taken in length original format etc. are recorded.

Module edits the advertising video if necessary for example by adding a bug or logo to the advertising video.

Module creates any action buttons that are necessary based on instructions received by module . The action buttons can be associated with the advertising video with the content video or with both.

Module receives a content video for example via Internet server and stores this into computer memory. In addition module receives information regarding the type of content this is such as breaking news weather traffic sports etc. . Depending on the format of the content video and the quality provided the content video can also be subjected to decompilation and normalization into the same universal format that was selected for the advertising video in module .

Module selects the next advertising video in the queue that matches the content provider and type of programming.

Module automatically edits the advertising video to the beginning the end or the beginning and end of the content video according to the instructions received in module . In an alternate embodiment the module can edit a first advertising video at the beginning of the content video and a second advertising video at the end of the content video. In another alternate embodiment the module can edit together any number of content and advertising videos. The module can also break the content video into two or more pieces with one or more advertising videos inserted between the pieces.

Module converts the joined video into a format or formats best suited for mobile device playback. Any of a number of video editors can be used for this purpose such as FFmpeg and Apple Quicktime.

Module sends the joined video to the relevant list of mobile subscribers. The video can be distributed directly to mobile subscribers or alternatively can be forwarded with the phone numbers of subscribers through an aggregator s API for distribution to mobile subscribers.

Module receives replies via the action buttons using text or video and sends these replies back to the content provider for aggregation or integration into their webs sites or other media. The replies are stored in a mail database or other database. Advertisers can view the replies using any of a number of viewing systems.

Program storage memory and data storage memory can each comprise volatile RAM and non volatile ROM memory units and can also comprise hard disk and backup storage capacity and both program storage memory and data storage memory can be embodied in a single memory device or separated in plural memory devices. Program storage memory stores software program modules and associated data and in particular stores an advertising video receiving module advertising video identification module advertising video broadcast parameter receiving module advertising video queuing module advertising video decompilation and normalization module advertising video editing module action button creation module content video receiving decompilation and normalization module advertising video selection module video splicing module action video integration module joined video conversion module converted joined video transmission module user reply receiving module or a combination including at least one of the foregoing modules. Data storage memory stores advertising video content video edited video advertising instructions and other data generated by the one or more modules of the present invention.

It is to be appreciated that the computer system can be any computer such as a personal computer minicomputer workstation mainframe a dedicated controller such as a programmable logic controller or a combination thereof. While the computer system is shown for illustration purposes as a single computer unit the system can comprise a group of computers which can be scaled depending on the processing load and database size.

Computer system preferably supports an operating system for example stored in program storage memory and executed by the processor from volatile memory. According to an embodiment of the invention the operating system contains instructions for interfacing computer system to the Internet and or to private networks.

The system and method of the present invention have been described above and with reference to the attached drawings however modifications will be apparent to those of ordinary skill in the art and the scope of protection for the invention is to be defined by the claims that follow.

