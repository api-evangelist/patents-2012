---

title: Method of controlling resolution of digital data broadcasting receiver, apparatus therefor, and digital data broadcasting receiver using the same
abstract: Provided are a method of controlling a resolution desired by a user in a graphics device of a digital data broadcasting receiver, an apparatus therefor, and a digital data broadcasting receiver using the same. The method includes providing a list of resolutions available on a graphic plane to a user; changing a resolution of the graphic plane according to a resolution selected by the user from the resolution list; and displaying an application on the graphic plane, the resolution of which has been changed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08570440&OS=08570440&RS=08570440
owner: Samsung Electronics Co., Ltd.
number: 08570440
owner_city: Suwon-si
owner_country: KR
publication_date: 20120309
---
This application is a continuation of U.S. application Ser. No. 11 606 112 filed in the U.S. Patent and Trademark Office on Nov. 30 2006 which claims priority from Korean Patent Application No. 10 2005 00115846 filed on Nov. 30 2005 in the Korean Intellectual Property Office the disclosures of which are incorporated herein in its entirety by reference.

Methods and apparatuses consistent with the present invention relate to a digital data broadcasting receiver and more particularly to a method of controlling a resolution desired by a user in a graphics device of a digital data broadcasting receiver an apparatus therefor and a digital data broadcasting receiver using the same.

Digital data broadcasting is a service of transmitting text pictures graphics sound images program packages and multimedia data to terminals such as set top boxes computers and portable phones at a very high speed. The digital data broadcasting provides broadcasting programs and related program information life information electronic commerce and interactive entertainment using communication media such as cable terrestrial wave and satellite wave.

The digital data broadcasting provides various programs to users through a number of channels and also provides various applications to provide more interactive information and various kinds of information to users. The applications are Java virtual machine JVM based application programs executed in a digital data broadcasting receiver. The applications are transmitted from a broadcasting station tuned by a user s request and loaded by the digital data broadcasting receiver.

In general the digital data broadcasting receiver displays an image by classifying display planes into three planes.

Referring to the display planes of the digital data broadcasting receiver are largely classified into a background plane a video plane and a graphic plane.

The background plane which is a plane on which a single color is presented or a still image is displayed displays an image existing farthest from a user s vision.

The video plane above the background plane is a plane on which a video image is displayed. That is as illustrated in the video plane is a plane on which a broadcasting program transmitted from a broadcasting station is displayed.

The graphic plane above the video plane is a plane on which applications implemented according to various digital data broadcasting standards e.g. the Advanced Common Application Platform ACAP the OpenCable Application Platform OCAP and the Multimedia Home Platform MHP are displayed in reality.

Although each of the background plane the video plane and the graphic plane can have a different resolution and be implemented individually the three planes are eventually combined into a single screen.

The digital data broadcasting standard such as the OCAP or the ACAP provides a Java application programming interface API for controlling each of the display planes. The background plane can be controlled using an HBackgroundDevice class the video plane can be controlled using an HVideoDevice class and the graphic plane can be controlled using an HGraphicsDevice class.

The graphic plane must fundamentally support at least each one of standard definition SD class resolution and high definition HD class resolution and can optionally support additional resolutions. Several applications can coexist on the graphic plane. If an application having a 640 480 window is transmitted from a broadcasting station and the graphic plane of the digital data broadcasting receiver is set to an SD class 640 480 resolution the application is output to a full screen. If the graphic plane of the digital data broadcasting receiver is set to an HD class 960 540 resolution the application cannot be output to a full screen.

Referring to when the application illustrated in which is realized based on an HD class resolution is executed the graphic plane is set to a high resolution according to a high resolution of the application . Thereafter if the application illustrated in which is realized based on an SD class resolution is executed the application having a low resolution changes the resolution of the graphic plane to a low resolution and accordingly the application having a high resolution exceeds the graphic plane.

Referring to when the application illustrated in which is realized based on an SD class resolution is executed the graphic plane is set to a low resolution according to a low resolution of the application . Thereafter if the application illustrated in which is realized based on an HD class resolution is executed the application having a high resolution changes the resolution of the graphic plane to a high resolution and accordingly the application having a low resolution is one sidedly displayed compared to its normal position.

As described above according to the related art in the case where a new application tries to change a resolution when a certain application has already been displayed on the graphic plane if resolutions of the two applications are different the already displayed application exceeds the graphic plane or the new application is one sidedly displayed at a position different from a desired one. That is a resolution change of the graphic plane is performed by only applications without concerns with a user s selection right.

The present invention provides a method and apparatus for allowing a user to control a resolution of a graphic plane on which applications are displayed in a digital data broadcasting receiver.

According to an aspect of the present invention there is provided a method of controlling a resolution of a graphic plane on which an application is displayed in a digital data broadcasting receiver the method comprising selecting one of a plurality of resolutions available on the graphic plane changing the resolution of the graphic plane according to the selected resolution and displaying the application on the graphic plane the resolution of which has been changed.

The changing of the resolution of the graphic plane may further comprise trying to reserve a use right of a graphics device managing the graphic plane and obtaining the use right of the graphics device.

When the use right is not obtained even if the reservation of the use right of the graphics device managing the graphic plane is tried a resolution change failure message may be output.

The method may further comprise informing modules of the digital data broadcasting receiver whether the resolution of the graphic plane has been changed.

According to another aspect of the present invention there is provided an apparatus for controlling a resolution of a graphic plane on which an application is displayed in a digital data broadcasting receiver the apparatus comprising a user resolution manager which provides a list of resolutions available on the graphic plane a resolution changer which changes the resolution of the graphic plane according to a resolution selected from the resolution list and a display unit which displays the application on the graphic plane the resolution of which has been changed.

The apparatus may further comprise a use right manager managing reservation and restoration of a use right of a graphics device managing the graphic plane wherein the user resolution manager requests the use right manager to grant the use right of the graphics device according to the selected resolution.

The user resolution manager may output a resolution change failure message if the use right of the graphics device is not obtained from the use right manager.

The apparatus may further comprise a resolution change notifier which informs modules of the digital data broadcasting receiver whether the resolution of the graphic plane has been changed.

According to another aspect of the present invention there is provided a digital data broadcasting receiver comprising a tuner which receives a digital data broadcasting signal a channel decoder which extracts an application from the digital data broadcasting signal received through the tuner an application processing unit which processes the extracted application a controller which provides a list of resolutions available on the graphic plane on which the processed application is displayed and changes a resolution of the graphic plane according to a selected resolution and a display unit which displays the application on the graphic plane the resolution of which has been changed.

When the resolution of the graphic plane is changed according to the selected resolution the controller may inform modules of the digital data broadcasting receiver that the resolution of the graphic plane has been changed.

When the resolution of the graphic plane cannot be changed according to the selected resolution the controller may output a resolution change failure message.

The present invention will now be described more fully with reference to the accompanying drawings in which exemplary embodiments of the invention are shown.

Referring to the digital data broadcasting receiver includes a tuner a demodulator a channel decoder an audio decoder a video decoder an application processing unit a display unit a user interface a remote control and a controller .

The digital data broadcasting receiver receives a digital data broadcasting signal including video audio and application through an antenna.

The application supported by digital data broadcasting and displayed on the graphic plane is made by predetermined content producers and transmitted from a broadcasting station and can be any type of applications. Examples of the application are an application for purchasing products used in a drama during a video service an application providing character information and or outline information of a drama an application for watching a scene at several angles in a sports broadcasting service and an application for transmitting or receiving an e mail or a short message separately from a provided video or audio service. Examples of a configuration of the application can include an execution file .exe a configuration file .cfg indicating a characteristic related to settings of the application an icon file .icon indicating graphics and a data file .data having user available data.

The tuner receives a modulated signal and outputs the modulated signal to the demodulator . The demodulator generates a transport stream by demodulating and error correcting the modulated signal input from the tuner and outputs the generated transport stream to the channel decoder .

The channel decoder extracts video and audio data of a channel which is selected by a user operating the remote control from the input transport stream in which video audio and application data of a plurality of channels are time division multiplexed and respectively outputs the extracted audio and video data to the audio decoder and video decoder . The channel decoder also extracts application data from the input transport stream and outputs the extracted application data to the application processing unit . The application processing unit processes the input application data and can store the processed application data in a memory not shown or provide the processed application data to the display unit to immediately display it.

The audio decoder decodes the audio data input from the channel decoder and the video decoder decodes the video data input from the channel decoder and provides the decoded video data to the display unit to display it on a screen of the display unit .

The controller controls the components included in the digital data broadcasting receiver . The controller provides a resolution list to the user so that the user can select a resolution of the graphic plane on which the application is displayed and changes the resolution of the graphic plane according to the resolution selected by the user.

The user can select a desired channel or the resolution of the graphic plane on which the application is displayed by directly operating the remote control or a function key included in the digital data broadcasting receiver . The resolution selected by the user is transmitted to the controller . Then the controller changes the resolution of the graphic plane according to the resolution selected by the user and the display unit re displays the input application according to the changed resolution.

Referring to the controller includes a user resolution manager a resolution changer a use right manager and a resolution change notifier .

The user resolution manager displays a list of resolutions which the digital data broadcasting receiver can provide through the user interface . Thereby the user can set a desired resolution through an input device such as the remote control . As described above when more than two applications coexist on the graphic plane a display state of the applications having different resolutions may be changed and thus the resolution list is provided to the user to give the user a resolution selection right so that a particularly concerned application can be normally displayed.

The resolution selected by the user is transmitted to the user resolution manager and then the user resolution manager tries to reserve a use right of a graphics device not shown managing the graphic plane to the use right manager . All modules of the digital data broadcasting receiver must obtain the use right of the graphics device before using the graphics device because a collision can occur if the use right is granted to another module before a certain module which has obtained the use right of the graphics device returns the use right. Thus the use right manager manages reservation and restoration of the use right of the graphics device among the modules of the digital data broadcasting receiver . The graphics device is a device which is constructed of hardware and software controlling a general operation which includes the resolution management of the graphic plane. For example according to the OCAP or ACAP digital data broadcasting middleware standard the graphics device may be the HGraphicDevice class.

If the graphics device is available the use right manager grants the use right of the graphics device to the user resolution manager in response to a request of the user resolution manager and prevents other modules e.g. another application from changing the resolution of the graphic plane by informing the resolution changer of the grant of the use right.

If the graphics device is being used by another module of the digital data broadcasting receiver i.e. if the resolution cannot be changed by a user s selection as a result of determining whether the graphics device is available in response to a request of the user resolution manager the use right manager informs the user resolution manager that the graphics device is busy and can output a resolution change failure message in a predetermined state display window provided by the user interface as illustrated in .

The resolution changer changes the resolution of the graphic plane to a resolution selected by the user from the resolution list in response to a request of the user resolution manager which has obtained the use right of the graphics device.

The display unit newly displays the application processed by the application processing unit on the graphic plane the resolution of which has been changed by the user s selection.

If the resolution of the graphic plane is changed by the user s selection the resolution changer informs the resolution change notifier of the resolution change of the graphic plane. The resolution change notifier informs each module of the resolution change in order to prevent the resolution selected by the user from being re changed by other modules. That is by informing the use right manager and an application which is being executed in the digital data broadcasting receiver of the resolution change the resolution selected by the user can be prevented from being re changed. To do this modules which are affected by the resolution of the graphic plane or affect it can be previously registered to the resolution change notifier and then when the resolution is changed the modules can receive the resolution change as an event.

Referring to in operation the user resolution manager provides a list of resolutions of the graphic plane which can be provided by the digital data broadcasting receiver through the user interface .

In operation the user selects a desired resolution through an input device such as the remote control . In operation the user resolution manager tries to reserve a use right of a graphics device managing the graphic plane to the use right manager .

If another module of the digital data broadcasting receiver is using the graphics device in operation the use right manager informs the user resolution manager that the graphics device is busy and then the user resolution manager outputs a resolution change failure message.

If the graphics device is available in operation the resolution changer changes the resolution of the graphic plane to a resolution selected by the user in response to a request of the user resolution manager which has obtained the use right of the graphics device.

In operation the display unit newly displays an application processed by the application processing unit on the graphic plane the resolution of which has been changed by the user s selection.

In operation the resolution changer informs the resolution change notifier that the resolution of the graphic plane has been changed by the user s selection and then the resolution change notifier informs each module of the resolution change in order to prevent the resolution selected by the user from being re changed by other modules.

In operation the use right manager which has received the resolution change notice cancels the use right of the graphics device which has been granted to the user resolution manager .

The method of controlling a resolution of a graphic plane according to the exemplary embodiments of the present invention can be implemented as computer programs. Codes and code segments for accomplishing the computer programs can be easily construed by programmers skilled in the art to which the present invention pertains. The computer programs are stored in a computer readable recording medium and embody the method of controlling a resolution of a graphic plane by being read by a computer and executed. Examples of the computer readable recording medium include magnetic storage media optical recording media and storage media such as carrier waves.

As described above according to exemplary embodiments of the present invention by allowing a user to select a resolution of a graphic plane at which an application is displayed the resolution of the graphic plane can be prevented from being changed by an application included in a digital data broadcasting program regardless of a user s desire. In addition the user convenience can be increased by allowing the user to set the resolution so that a specific application of interest can be normally displayed.

While this invention has been particularly shown and described with reference to exemplary embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the invention as defined by the appended claims. The exemplary embodiments should be considered in descriptive sense only and not for purposes of limitation. Therefore the scope of the invention is defined not by the detailed description of the invention but by the appended claims and all differences within the scope will be construed as being included in the present invention.

