---

title: Non-real time image processing method, image capturing apparatus applying the same, and image processing system
abstract: An image processing method, an image capturing apparatus applying the same, and an image processing system. The image processing method includes capturing an image, generating intermediate data by primarily processing the captured image, generating final processing data including instructions to initiate a final process to convert the intermediate data into final data, and transmitting the intermediate data and the final processing data to an external image processing apparatus to perform the final process. Accordingly, an image quality of the image is improved as compared to an image quality of a final image processed in real time by a conventional image capturing apparatus, and a variety of functions can be provided.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08797420&OS=08797420&RS=08797420
owner: Samsung Electronics Co., Ltd
number: 08797420
owner_city: Suwon-si
owner_country: KR
publication_date: 20120328
---
This application claims priority under 35 U.S.C. 119 a from Korean Patent Application No. 10 2011 0028295 filed on Mar. 29 2011 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference it its entirety.

The present general inventive concept generally relates to an image processing method an image capturing apparatus applying the same and an image processing system and more particularly to an image processing method to process an image within an external image processing apparatus an image capturing apparatus applying the same and an image processing system.

A conventional mobile image capturing apparatus includes various functions that can be selected by a user and transmits data that is generated from the selected function to an external appliance such as a computer. The transmitted data may be data that does not require reprocessing such as a still image a moving image clip etc.

For example a digital camera allows a user to select functions such as still image capturing moving image capturing high speed continuous shot etc. and outputs data as JPEG GIF TIFF PNG BMP or MPEG files. The output data is stored in a storage device or is transmitted to an external computer or a server where it may be modified.

However the conventional mobile image capturing apparatus unlike a tabletop mounted image processing apparatus e.g. a computer is limited in CPU capability and memory storage space and thus image processing functions and performance quality are limited. Due to such limitations the conventional mobile image capturing apparatus is designed to perform simple functions in comparison to the tabletop mounted image processing apparatus.

Further due to limitations regarding algorithm simplification optimization and overall performance quality the conventional mobile image capturing apparatus such as a digital camera a camcorder a portable phone etc. excludes advanced functions to avoid overburdening the conventional mobile image capturing apparatus CPU or memory.

The present general inventive concept provides an image processing method an image capturing apparatus applying the same and an image processing system which can transmit intermediate data that is generated through primary processing of a captured image and final processing information including instructions to initiate a final process to convert the intermediate data into final data to an external image processing apparatus and instruct the external image processing apparatus to perform the final process.

Additional aspects and utilities of the present general inventive concept will be set forth in part in the description which follows and in part will be obvious from the description or may be learned by practice of the general inventive concept.

The foregoing and or other features and utilities of the present general inventive concept may be achieved by an image processing method of an image capturing apparatus including capturing an image generating intermediate data by primarily processing the captured image generating final processing data including instructions to initiate a final process to convert the intermediate data into final data and transmitting the intermediate data and the final processing data to an external image processing to perform the final process.

The image processing method may further include displaying a User Interface UI to set at least one of image quality data of the final data and special effect data of the final data which are included in the final processing data.

The UI may include at least one state adjustment to set the image quality data of the final data and the generation of the final processing data may generate the final processing data of the intermediate data so that an adjustment icon of the at least one state adjustment bar moves in a first direction to improve an image quality of the final data.

The UI may include an image quality selection menu to allow a user to select a level corresponding to the image quality data of the final data.

The UI may set detailed image setting functions of the image quality data in order to set the image quality data of the final data.

The UI may include at least one of a real time selection portion to set a real time processing mode in which the image capturing apparatus performs the final process with respect to the detailed image setting functions in real time an automatic selection portion to set an automatic processing mode in which the detailed image setting items are automatically set according to image capturing conditions when the image is captured and a level selection portion to set the detailed image setting functions of the image quality data.

The image processing method may further include displaying the intermediate data obtained by primarily processing the captured image.

The intermediate data obtained by primarily processing the captured image may be a raw data file and the final data obtained by performing the final process with respect to the intermediate data may be one of a JPEG file and an MPEG file.

The final processing data may include at least one of the image quality data of the final data that is generated through the final process special effect data that is applied to the final data and protocol data to allow the capturing apparatus to communicate with the image processing apparatus to perform the final process of the intermediate data.

The foregoing and or other features and utilities of the present general inventive concept may also be achieved by an image capturing apparatus including an image capturing unit to capture an image an image processing unit to generate intermediate data by primarily processing the image captured by the image capturing unit a transceiver unit connected to an external image processing apparatus and a control unit generate final processing data including instructions to initiate a final process to convert the intermediate into final data and to transmit the intermediate data and the final processing data to the external image processing apparatus through the transceiver unit.

The image capturing apparatus may further include a User Interface UI generation unit to generate a UI wherein the control unit controls the UI generation unit to generate the UI to set at least one of image quality data of the final data and special effect data of the final data which are included in the final processing data.

The UI may include at least one state adjustment bar to set the image quality data of the final data and the control unit may generate the final processing information of the intermediate data so that an adjustment icon of the at least one state adjustment bar moves in a first direction according to a user s input to improve an image quality of the final data.

The UI may include an image quality selection menu to allow a user to select a level corresponding to the image quality data of the final data.

The UI may set detailed image setting functions of the image quality data in order to set the image quality data of the final data.

The UI may include at least one of a real time selection portion to set a real time processing mode in which the image capturing apparatus performs the final process with respect to the detailed image setting functions in real time an automatic selection portion to set an automatic processing mode in which the final processing data of the detailed image setting functions are automatically set according to image capturing conditions when the image is captured and a level selection portion to set the detailed image setting functions of the image quality data.

The image capturing apparatus may further include a display unit wherein the control unit controls the display unit to display the intermediate data obtained by primarily processing the captured image.

The intermediate data obtained by primarily processing the captured image may be a raw data file and the final data obtained by performing the final process with respect to the intermediate data may be one of a JPEG file and an MPEG file.

The final processing data may include at least one of the image quality data of the final data that is generated through the final process special effect data that is applied to the final data and protocol data to allow the image capturing device to communicate with the image processing apparatus to perform the final process of the intermediate data.

The foregoing and or other features and utilities of the present general inventive concept may also be achieved by an image processing system including an image capturing apparatus to capture an image to generate intermediate data by primarily processing the captured image to generate final processing data including instructions to initiate a final process to convert the intermediate data into final data and to transmit the generated intermediate data and the final processing data and an image processing apparatus to receive the intermediate data and the final processing data transmitted from the image capturing apparatus and to perform the final process of the intermediate data as to generate the final data.

The foregoing and or other features and utilities of the present general inventive concept may also be achieved by an image processing system including an image capturing apparatus to capture an image and generate a raw data file corresponding to the captured image a user interface to allow a user to input image quality settings and an image processing apparatus to receive the raw data file from the image capturing apparatus and to modify the raw data file based on the user s input.

The image processing apparatus may include a processing unit to convert the modified raw data file into one of a JPEG file and an MPEG file.

The user interface may include at least one of a state adjustment bar a check box and a radio button.

The user interface may include at least one of a menu to modify the image quality settings individually and a menu to modify the image quality settings simultaneously.

The image quality settings may include at least one of Noise Reduction Low Light Shot High Dynamic Range Blur Detection Blur Correction Auto Contrast and Auto Brightness.

The input image quality settings may be generated as modification processing data and the image processing apparatus may receive the modification processing data together with the raw data.

The modification processing data and raw data may be received by the image processing apparatus wirelessly.

Reference will now be made in detail to the embodiments of the present general inventive concept examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to the like elements throughout. The embodiments are described below in order to explain the present general inventive concept while referring to the figures.

The image capturing apparatus captures an image through an image capturing unit and generates intermediate data by primarily processing the captured image. The intermediate data includes image data that has not been modified or manipulated. For example the intermediate data may include a raw data file.

Further the image capturing apparatus may generate final processing data including instructions to initiate a final process to convert the intermediate data into final data. The final data includes image data that has been processed modified or manipulated e.g. a user sets image quality data or selects a special effect function . For example the final data may include an MPEG file or a JPEG file.

The final processing data may include image quality data of the final data that is generated during the final process special effect data that is applied to the final data and protocol data to allow the image capturing apparatus to communicate with an external image processing apparatus such as the image processing apparatus to perform the final processing of the intermediate data.

Further the image capturing apparatus may set the image quality data of the final data special effect data that is applied to the final data etc. which are included in the final processing data according to the user s input. A User Interface UI to set the image quality data of the final data the special effect data that is applied to the final data etc. will be described in detail with reference to .

Further the image capturing apparatus transmits the generated intermediate data and the final processing data to the external image processing apparatus through a transceiver unit so that the external image processing apparatus performs the final processing of the intermediate data. The intermediate data and the final processing data may be transmitted to the external image processing apparatus via a wired interface such as a USB cable or a wireless interface such as a Bluetooth module.

The external image processing apparatus generates final data using the intermediate data and the final processing data received from the image capturing apparatus . Specifically the external image processing apparatus performs the final process with respect to the intermediate data by applying the image quality data final data and the special effect data which are included in the final processing data to the intermediate data and generates the final data.

The above described image processing system generates an image with an image quality superior to an image quality of an image processed in real time by a conventional image capturing apparatus and the image capturing apparatus can provide a user with a variety of functions.

Hereinafter the image capturing apparatus and the image processing apparatus will be described with reference to .

The image capturing unit captures a still image or a moving image through a lens not illustrated . Specifically the image capturing unit forms an image on a sensor region not illustrated using the lens. Further the image capturing unit performs photoelectric conversion that is converts light incident through the lens into an electric signal using an image sensor not illustrated .

The image processing unit receives the captured image from the image capturing unit and performs primary data processing on the captured image to acquire intermediate data. The intermediate data includes image data that has not been modified or manipulated. For example the intermediate data may include a raw data file.

The intermediate data may be stored in the storage unit or may be displayed on the display unit . In addition the intermediate data is transmitted to the external image processing apparatus through the transceiver unit together with the final processing data including instructions to initiate the final process to convert the intermediate data into the final data.

The display unit displays the image that is processed by the image processing unit . In particular the display unit can display the intermediate data that is primarily processed by the image processing unit . Further the display unit can display the User Interface generated by the UI generation unit and the final data that is processed by and received from the external image processing apparatus .

The UI generation unit generates the User Interface corresponding to various settings in the image capturing apparatus . The generated User Interface will be later described in detail with reference to .

The storage unit stores the image data that is processed by the image processing unit in a compressed form. In particular the storage unit can compress and store the intermediate data that is primarily processed by the image processing unit . The storage unit may include a nonvolatile memory a hard disk etc.

The transceiver unit communicates with an external apparatus in order to transmit and or receive various kinds of image data. In particular the transceiver unit can transmit the intermediate data and the final processing data to the external image processing apparatus .

The transceiver unit may include a wire interface unit such as a USB cable or a wireless interface unit such as a Bluetooth module.

The control unit receives a user command transferred from a user input unit not illustrated and controls an operation of the image capturing apparatus according to the received user command.

In particular the control unit generates the final processing data including instructions to initiate the final process to convert the intermediate data that is primarily processed by the image processing unit into the final data.

The control unit can control the UI generation unit to generate a User Interface to set at least one of the image quality data of the final data and the special effect data of the final data which are included in the final processing data.

The generated User Interface is hereinafter described with reference to . is a diagram illustrating a User Interface that is provided in the image capturing apparatus according to an exemplary embodiment of the present general inventive concept.

Referring to the generated User Interface includes a state adjustment bar to set an image quality of the final data that is included in the final processing data. The image quality of the final data that is included in the final processing data may include an attribute of the final data an image quality process improvement function etc. For example the attribute of the final data may include information regarding an image quality size of the final data resolution contrast and brightness but is not limited thereto and the image quality process improvement function may include information regarding noise reduction and blur correction but is not limited thereto.

For example referring to when an adjustment icon of the state adjustment bar is moved in a rightward direction in response to the user s input i.e. toward MAX as illustrated in the control unit generates image quality process data so that the image quality of the final data is improved.

More specifically when the adjustment icon of the state adjustment bar is moved in the rightward direction the image quality size of the final data is enlarged the resolution increases and a contrast ratio increases. Further the noise reduction amount that is applied to the final data is increased and the blur correction amount is also increased.

In contrast when the adjustment icon of the state adjustment bar is moved in the leftward direction in response to the user s input i.e. toward MIN the control unit generates image quality process data so that the image quality of the final data decreases. However when the adjustment icon of the state adjustment bar is moved in the leftward direction the image quality of the final data decreases and capacitance to process the image quality is reduced to make prompt processing possible.

For example if the adjustment icon of the state adjustment bar is moved in the leftward direction the image quality size of the final result is reduced the resolution is lowered and the contrast ratio is lowered. Further the noise reduction amount that is applied to the final data is decreased and the blur correction amount is also decreased.

As described above by adjusting various types of image quality data with one state adjustment bar a user can select a desired image quality level and the processing speed more easily.

As illustrated in the generated User Interface includes an image quality selection menu to allow a user to select the image quality of the final data. The image quality selection menu enables a plurality of levels to be set so that the image quality data of the final data can be easily selected. As a higher level is selected the control unit generates the image quality process data so that the image quality of the final data improves. In contrast as a lower level is selected the image quality of the final data decreases but the control unit is able to generate image quality process data with a high processing speed.

For example LEVEL 4 can provide the final data with better image quality than that of LEVEL 2 . That is the image size of the final data at LEVEL 4 is larger than the image size of the final data at LEVEL 2 and the resolution of the final data at LEVEL 4 is higher than that of the final data at LEVEL 2 . Further the contrast ratio of the final data at level 4 is higher than the contrast ratio of the final data at LEVEL 2 and the noise reduction amount of the final data at LEVEL 4 is larger than the noise reduction amount of the final data at LEVEL 2 . Moreover the blur correction amount of the final data at LEVEL 4 is larger than the blur correction amount of the final data at LEVEL 2 .

As described above by adjusting various types of image quality data through one image quality selection menu the user can select a desired image quality level more easily.

The User Interface illustrated in includes a plurality of state adjustment bars through which are similar to the state adjustment bar as illustrated in . However in various types of image quality data is simultaneously set through one state adjustment bar whereas in each type of image quality data can be set separately.

For example referring to the image quality data related to the IMAGE QUALITY ATTRIBUTE may be set using a first state adjustment bar the image quality data related to the IMAGE QUALITY IMPROVEMENT FUNCTION may be set using a second state adjustment bar and the BACKUP RESTORE FUNCTION may be set using a third state adjustment bar

Referring to by adjusting the various types of image quality data through one state adjustment bar the image quality data can be adjusted more easily while in by adjusting the various types of image quality data through a plurality of state adjustment bars and respectively a user may individually select and alter a particular type of image quality data.

The User Interface illustrated in is a User Interface to allow a user to individually select a plurality of detailed image setting functions . More specifically as illustrated in the generated User Interface includes a plurality of User Interface selection portions including a real time selection portion to set a real time processing mode in which the image capturing apparatus performs the final process with respect to the detailed image setting functions in real time an automatic selection portion to set an automatic processing mode in which the final processing data of the detailed image setting functions are automatically set according to image capturing conditions when the image is captured and a level selection portion to allow a user to manually select the level of the image quality information corresponding to each of the detailed image setting functions . To facilitate selection the real time selection portion the automatic selection portion and the level selection portion may include option buttons such as check boxes and radio buttons but are not limited thereto.

Referring to the plurality of detailed image setting functions that a user may select includes but is not limited to Noise Reduction Low Light Shot High Dynamic Range Blur Detection Blur Correction Auto Contrast and Auto Brightness. 

The real time selection portion allows a corresponding one of the plurality of detailed image setting functions to be processed in real time by the image capturing apparatus . For example when the noise reduction function is set in a real time processing mode the data corresponding to the noise reduction function is not included in the image quality process data but is performed in real time according to a value set by the image capturing apparatus .

The UI automatic selection portion allows a corresponding one of the plurality of detailed image setting functions to be set automatically according to capturing conditions. For example when the automatic contrast function is set in an automatic processing mode the image capturing apparatus automatically sets the automatic contrast value in consideration of the image capturing time zone the brightness at the time of image capturing etc.

The level selection portion is similar to the image quality section menu as described in . However unlike the image quality selection menu illustrated in the level selection portion of allows a user to individually select the image quality of the each of the various particular detailed image setting functions .

By using the image quality data of the final data and the special effect data which are set through the User Interfaces as illustrated in the control unit can generate the image quality process data.

Further the control unit may control the display unit to display the intermediate data that is obtained by primarily processing the captured image. Accordingly the user can confirm the displayed image is correct even if the displayed image is not the modified final data.

Further the control unit operates to transmit the intermediate data and the final processing data to the external image processing apparatus through the transceiver unit so that the external image processing apparatus can perform the final process with respect to the intermediate data.

The above described image capturing apparatus generates an image with an image quality superior to an image quality of a final image processed in real time by a conventional image capturing apparatus and the image capturing apparatus can provide a user with a variety of functions.

The transceiver unit communicates with the image capturing apparatus of . In particular the transceiver unit receives the final processing data including instructions to initiate the final process to convert the intermediate data into the final data in the image capturing apparatus .

The transceiver unit transmits the received intermediate data and the final processing data to the processing unit .

The processing unit performs the final process with respect to the intermediate data by applying the image quality data of the final data and the special effect data of the final data which are included in the final processing information to the intermediate data. As a result of performing the final process the processing unit generates the final data.

The generated final data may be displayed by the display unit and may be transmitted again to the image capturing apparatus through the transceiver unit .

Accordingly by processing the image through the image processing apparatus having superior performance than the image capturing apparatus the image processing apparatus can provide the user with an image with superior image quality and the image capturing apparatus can provide a user with a variety of functions.

Hereinafter referring to an image processing method of the image capturing apparatus will be described. is a flowchart illustrating an image processing method of the image capturing apparatus according to an exemplary embodiment of the present general inventive concept.

The image capturing apparatus sets the final processing data through the User Interface UI operation S . The final processing data includes instructions to initiate the final process to convert the intermediate data that is obtained by primarily processing the captured image into the final data. Further the setting of the final processing data through the User Interface may be performed when the image capturing apparatus is initially powered on or when a user desires to modify the final processing data.

After the final processing information is set the image capturing apparatus captures an image from a specified object operation S .

The image capturing apparatus generates the intermediate data by primarily processing the captured image operation S . As stated above the intermediate data includes image data that has not been modified or manipulated. For example the intermediate data may be a raw data file.

The image capturing apparatus generates the final processing data including instructions to initiate the final process to convert the primarily processed intermediate data into the final data operation S . As described above the final data includes image data to which the image quality data set by the user the special effect function etc. is applied. For example the final data may include an MPEG file or a JPEG file. Here the final processing data may include the image quality data of the final data that is generated through the final process special effect data that is applied to the final data and protocol data to allow the image capturing apparatus to communicate with the external image processing apparatus to perform final processing of the intermediate data.

Further the image capturing apparatus transmits the generated intermediate data and the final processing data to the external image processing apparatus through the transceiver unit so that the external image processing apparatus performs the final processing of the intermediate data operation S . The intermediate data and the final processing data may be transmitted to the external image processing apparatus via a wire interface such as a USB cable or a wireless interface such as a Bluetooth module.

The above described image processing method generates an image with an image quality superior to an image quality of an image processed in real time by a conventional image capturing apparatus and the image capturing apparatus can provide a user with a variety of functions.

Although a few embodiments of the present general inventive concept have been shown and described it will be appreciated by those skilled in the art that changes may be made in these embodiments without departing from the principles and spirit of the general inventive concept the scope of which is defined in the appended claims and their equivalents.

