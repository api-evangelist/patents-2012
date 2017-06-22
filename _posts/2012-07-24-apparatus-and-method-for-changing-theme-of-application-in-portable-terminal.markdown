---

title: Apparatus and method for changing theme of application in portable terminal
abstract: An apparatus and a method for changing a theme form of an application to conform the user experience to a web application or a native application in a portable terminal. The apparatus for changing the application theme in the portable terminal may comprise a controlling unit for changing an application theme into an application theme of a different device type, a displaying unit for outputting a change process of the application theme and the application to which the changed theme is applied, an inputting unit for generating a change request of the application theme and a theme application managing unit for converting theme data, obtained from compiled data of an application, through an inverse-compiling process, to data suitable for the theme form of a second application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09411561&OS=09411561&RS=09411561
owner: Samsung Electronics Co., Ltd
number: 09411561
owner_city: 
owner_country: KR
publication_date: 20120724
---
The present application claims priority under 35 U.S.C. 119 a to a Korean patent application filed in the Korean Intellectual Property Office on Jul. 25 2011 and assigned Serial No. 10 2011 0073385 the entire disclosure of which is hereby incorporated by reference.

A portable terminal is used by people of all ages as a necessity of modern life and service providers and terminal manufacturers have been developing various products and services for use with the portable terminal.

The portable terminal has evolved into a multi media device capable of providing various services such as a phone book messaging e mail alarm clock MP3 player schedule management digital camera multimedia messaging and wireless Internet services.

In addition a user of the portable terminal may download and install a paid or free application providing additional functionality. An application operating in a portable terminal may be classified as a native application and a web application. A web application generally operates in a web browser and a native application generally operates by utilizing an Application Programming Interface API defined for a specific platform.

A web application may have a theme configuration for example font font size font color background screen menu form and the like different from that of the native application and as a result user experience may differ depending on the application format web application and native application even though application functionality is identical.

That is the web application may provide a layout based on a web browser and the native application may provide another layout depending on the application design resulting in a different user experience of an identical application depending on the application format. If the user of the portable terminal is comfortable with the theme configuration of the native application he may want the theme configuration of the web application to be set as that of the native application.

The difficulty in utilizing the theme of the native application as discussed above is that a developer has to design an identical application in a native application format and web application format and the user has to select a favorite format to use.

Hence to solve the above mentioned problems an apparatus and a method for converting script data of an application into a suitable application format in a portable terminal are required.

Accordingly the present invention has been made to solve at least the above mentioned problems and or disadvantages and to provide at least the advantages below. Accordingly and an aspect of the present invention is to provide an apparatus and a method for supporting an application of a different device type in a portable terminal.

Another aspect of the present invention is to provide an apparatus and a method for changing a theme configuration of an application by changing a script of an application in a portable terminal.

Yet another aspect of the present invention is to provide an apparatus and a method for generating an application to support a plural of application forms in a portable terminal.

According to an aspect of the present invention an apparatus for changing the theme of an application includes a controlling unit for converting an application theme to be changed into an application theme of a different device type a displaying unit for outputting a change process of the application theme and the application to which the changed theme is applied an inputting unit for generating a change request of the application theme and a theme managing unit for converting obtained conversion data into components suitable for a theme form of a second application after obtaining the conversion data from compiled data of the application through an inverse compiling process.

According to another aspect of the present invention a method for changing the application theme in a portable terminal includes obtaining a conversion data from compiled data of the application for changing the theme through an inverse compiling process and converting the obtained conversion data into components suitable for a theme form of a second application wherein the second application is an application of a different device type for which the theme is changed.

Various embodiments of the present invention are described in detail with reference to the accompanying drawings. Detailed description of known functions or constructions are omitted to avoid obscuring the subject matter of the present invention.

Embodiments of the present invention provide an apparatus and a method for changing a theme form of an application and processing a web application and a native application to conform user experience to the web application and native application in the portable terminal.

Embodiments of the present invention provide an application and a method for automatically changing a script data of an application to support an application of a different device type which may be an application operating based on a web browser and a native application operating with an API defined in a specific platform.

Referring the portable terminal includes a controlling unit a theme managing unit a memory unit an inputting unit a displaying unit and a communicating unit . And the theme managing unit may comprise a data converting unit and a script converting unit .

The controlling unit of the portable terminal controls the overall operation of the portable terminal. For example the controlling unit may carry out a process and control for voice communication and data communication. In addition to the general functions the controlling unit may carry out supporting an application of a different device type in the portable terminal according to the present invention. That is the controlling unit may automatically convert script data and utilize a theme configuration regardless of an application form to conform user experience of the application.

The controlling unit controls the theme managing unit and converts a theme of a web application into that of a native application and vice versa. In addition the method described herein may be provided as one or more instructions in one or more software modules stored in the storage device. The software modules may be executed by the controller.

The theme managing unit changes a theme form of an application according to the control of the controlling unit . For example the theme of the web application may be converted into the theme of the native application in the portable terminal and vice versa.

The data converting unit of the theme managing unit obtains conversion data through inverse compilation of the compiled data of the application in order to edit a script file of the application to which a theme conversion intends to be applied. The conversion data may be Cascading Style Sheet CSS data to the compiled data of the web application or Edje Data Collection EDC data to the compiled data of the native application.

The script converting unit of the theme managing unit converts theme components of the conversion data converted by the data converting unit into theme components suitable for a form of a second application. That is after the script converting unit determines the components of the script file of the native application such as background font font size font color and the like the script conversion unit converts the determined components into components suitable for the script file of the native application.

The theme managing unit the data converting unit and or script converting unit may be referred to as another controller.

The memory unit may comprise a ROM a RAM and a flash ROM. The ROM may store the micro cord of a program for processing and controlling the controlling unit and the theme managing unit and various reference data.

When the memory unit comprises a RAM as the working memory of the controlling unit the controlling part stores temporary data generated during the operation of various programs. When the working memory is a flash ROM the flash ROM stores renewable various data for filing such as a phone book an outgoing message an incoming message and the like and may store a web application or a native application downloaded through the Internet or supplied from the portable terminal according to an embodiment of the present invention.

The method executed by the theme managing unit the data converting unit and or script converting unit may be provided as one or more instructions in one or more software modules stored in the memory unit . In that case the software modules are executed by the controller unit .

The inputting unit may comprise numeral buttons from 0 to 9 a menu button a cancel button a verify button a call button an end button an access button navigation key or direction keys buttons character input keys and the like and provides the controlling unit with key input data corresponding to keys pressed by a user. In addition the inputting unit provides the controlling unit with input data at the request of a user for changing the theme of an application stored previously.

The displaying unit displays status information characters many moving pictures many images and the like generated during the operation of the portable terminal. The displaying unit may use a color liquid display apparatus AMOLED and the like and the displaying unit may have a touch input device to use as an input means for applying a touch input type for the portable terminal. In addition the displaying unit may display an application whose theme is converted according to the present invention. A touch sensitive display referred to as a touch screen may be used as the display unit and touch input may be performed via the touch sensitive display.

The communicating unit transmits and receives wireless signals of data input and output through an antenna. For example the communicating unit may channel code and spread data to be transmitted and generate RF signals for transmitting. Further the communicating unit may convert the received RF signal into a base band signal to spread and channel decode the signal for restoring the data.

The role of the theme managing unit may be performed by the controlling unit of the portable terminal but it is separated from the controlling unit in the foregoing description for convenience and illustration purposes only and not intended to limit the present invention. Alternatively all of the functions described above may be performed by the controlling unit .

Referring to in Step it is verified whether a theme of an application is changed in the portable terminal. Changing the theme of the application refers to changing the theme configuration for example shape of button wallpaper font size of font and color of font and the like of the application supplied from the portable terminal the Internet or a peripheral portable terminal and the theme configuration of a web application may be changed into that of a native application or vice versa. The web application is an application operating in a web browser and the native application is an application operating by using an API defined for a specific platform. Generally the theme configuration of the web application is different from that of the native application and a user has a different experience of an identical application depending on the form of application web application native application . Hence a user of the portable terminal comfortable with the theme configuration of the native application may prefer the theme configuration of the web application to be set to that of the native application.

If it is verified that the application theme is not to be changed in Step a corresponding function for example standby mode may be performed in the portable terminal in Step .

If it is verified that the application theme is changed in Step an application whose theme intends to be changed is selected in Step in the portable terminal. In that case a web application or native application for changing the theme among applications stored previously is selected in the portable terminal. In that case if the web application is selected in the portable terminal in Step the theme configuration of the web application selected by the user results in the web application being changed into the theme configuration of the native application in the portable terminal while if the native application is selected in the portable terminal in Step the theme configuration of the native application selected by the user results in the native application being changed into the theme configuration of the web application in the portable terminal.

In Step the compiled data of the selected application may be verified in the portable terminal. If a web application is selected in Step the complied data includes data made by compiling CSS file while if a native application is selected in Step the compiled data includes data made by compiling EDC file.

The compiled data may be inverse compiled for obtaining a conversion data to the compiled data in the portable terminal in Step . The conversion data includes a CSS file or EDC file to the compiled data.

In Step the conversion data obtained in Step is analyzed in the portable terminal and it is verified whether it is possible to change the theme in Step in the portable terminal. In that case it can be verified whether requisite theme components for example font size wallpaper color and the like for composing a layout construction of the application selected by the user is included in the portable terminal.

If it is verified that it is impossible to change the application theme in Step because the requisite theme components for composing the layout construction is not included an existing application theme that is the application theme selected in Step is utilized in the portable terminal in Step .

In step it is verified that it is possible to change the application theme because the requisite theme components for composing the layout construction are included . In Step the theme components of the conversion data are converted into a theme form of a second application. In this case the second application is an application intended to support the converted theme. That is if the native application is selected for changing the theme in the portable terminal the conversion data of the native application is converted into component data of a web application form in Step . If the web application is selected for changing the theme in the portable terminal the conversion data of the web application is converted into the component data of the native application form in Step .

In Step it is verified whether the converted data form is compatible in the second application in the portable terminal.

If it is verified that the converted theme form is not compatible the existing application theme that is the application theme selected in Step is utilized in Step in the portable terminal.

If it is verified that the theme form converted in Step is compatible the theme converted in Step is applied in Step in the portable terminal. Therefore if a provider for supplying the application provides some application using one script sheet regardless of the application form an application suitable for a form desired by the user is provided by converting the script sheet in the portable terminal.

Referring to as in Step in theme components of conversion data are converted into a theme form of a second application in the portable terminal.

In order to perform the same operation described above theme components are determined in the converted data in Step and then a theme form of a second application for converting is verified in Step . Here in Step a script area corresponding to the theme components in the converted data is verified and in Step it is verified that the application selected by the user is converted into a web application form or a native application form.

In Step the theme components are re made as a form corresponding to the second application in the portable terminal. That is the previously selected theme components such as color menu form and the like are changed into a theme corresponding to the second application in the portable terminal. Further as in Step in a process for verifying whether the converted theme form is compatible in the second application is performed.

Referring to an application for converting is selected for changing a theme configuration for example button shape wallpaper font and size color and the like of an application supplied from the portable terminal or an application supplied from the Internet or a peripheral portable terminal in the portable terminal.

For example a theme of a native application is converted into a theme of a web application in the portable terminal indicated as a solid line .

In order to perform the operation described above the script converting unit of the portable terminal converts the script file of the native application selected previously into a script file of the web application.

That is the script converting unit determines the theme configuration components such as background font font size font color in the script file of the native application and converts the determined components into components suitable for the script file of the web application.

Alternatively the theme of the web application may be converted into the theme of the native application in the portable terminal indicated as dashed line .

In order to perform the operation described above the script converting unit of the portable terminal converts the script file of the web application selected previously into the script file of the native application.

That is the script converting unit determines the theme configuration components such as background font font size font color and the like in the script file of the web application and converts the determined components into components suitable for the script file of the native application.

Therefore one application may be composed of a web application theme and a native application theme in the portable terminal. That is the theme suitable for the web application form or the theme suitable for the native application form may be applied using one script sheet in the portable terminal.

Embodiments of the present invention can be implemented as hardware software or a combination of hardware and software. The software may be stored in the form of volatile or non volatile storage such as for example a storage device like a Read Only Memory ROM erasable or rewritable or in the form of memory such as for example Random Access Memory RAM memory chips device or integrated circuits or on an optically or magnetically readable medium such as for example a Compact Disk CD Digital Versatile Disc DVD magnetic disk or magnetic tape or the like. The storage devices and storage media are implemented as machine readable storage that is suitable for storing a program or programs comprising instructions that when executed perform the method of the present invention. Accordingly embodiments of the present invention provide a program comprising code for implementing an apparatus or a method of the present invention described herein and a machine readable storage storing such a program. Further such programs may be conveyed electronically via any medium such as a communication signal carried over a wired or wireless connection. As discussed above the present invention provides support for different device types in the portable terminal and conforms user experience of the application by automatically converting the script data of the application and utilizing the theme configuration regardless of the application format.

While the present invention has been shown and described with reference to various embodiments thereof it will be understood by those skilled in the art that changes in form and detail may be made without departing from the spirit and scope of the present invention as defined by the appended claims.

