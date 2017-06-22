---

title: Image capturing apparatus, method of controlling same and program therefor
abstract: An image capturing apparatus for capturing the image of a subject includes: a lock/unlock unit adapted to lock and unlock operation of the image capturing apparatus; a registration unit adapted to register a main item and a sub-item that have been selected by a user, wherein the main item is a main setting item among operation items of the image capturing apparatus and the sub-item is a setting item in a layer lower than that of the main item; and a control unit adapted to limit operation solely to a release operation of the image capturing apparatus and to the main item and sub-item, which have been registered by the registration unit, in a case where operation of the image capturing apparatus has been locked by the lock/unlock unit.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08553128&OS=08553128&RS=08553128
owner: Canon Kabushiki Kaisha
number: 08553128
owner_city: Tokyo
owner_country: JP
publication_date: 20120725
---
This application is a continuation of application Ser. No. 12 033 335 filed Feb. 19 2008 the entire disclosure of which is hereby incorporated by reference.

The present invention relates to a technique in an image capturing apparatus such as a digital camera that makes it possible to operate an item desired by a user even in a case where the image capturing apparatus is locked against operation.

Digital cameras have become widespread in recent years and now are being used also in photo studios that have been employing conventional silver halide cameras. In a photo studio often a picture is taken in an environment in which the brightness of illumination and the white balance are fixed and often a picture is taken with exposure fixed as well. For this reason often the camera is set so as to lock items for which a change is unnecessary such as the aperture and shutter speed and to make possible only a minimum necessary operation such as operation of shutter speed.

Further in accordance with the specification of Japanese Patent Laid Open No. 6 103239 a portable computer in which the environment in which a system is used is changed in response to a match with a password is disclosed.

However there are cases where a function that the photographer wishes to render operable differs depending upon the circumstances at the particular photo studio. Conventionally if camera settings are locked only functions decided in advance are operable and these cannot be changed. That is inconveniences can arise such as a case where a function that the photographer wishes to lock cannot be locked or conversely a case where a function that the photographer desires to operate has been locked.

Accordingly the present invention has been devised in view of the above described circumstances and seeks to make it possible to operate a camera function desired by a user even in a case where the camera is locked against operation.

According to a first aspect of the present invention the foregoing object is attained by providing an image capturing apparatus for capturing the image of a subject comprising a lock unlock unit adapted to lock and unlock operation of the image capturing apparatus a registration unit adapted to register a main item and a sub item that have been selected by a user wherein the main item is a main setting item among operation items of the image capturing apparatus and the sub item is a setting item in a layer lower than that of the main item and a control unit adapted to limit operation solely to a release operation of the image capturing apparatus and to the main item and sub item which have been registered by the registration unit in a case where operation of the image capturing apparatus has been locked by the lock unlock unit.

According to a second aspect of the present invention the foregoing object is attained by providing a method of controlling an image capturing apparatus for capturing the image of a subject comprising a lock unlock step of locking and unlocking operation of the image capturing apparatus a registration step of registering a main item and a sub item that have been selected by a user wherein the main item is a main setting item among operation items of the image capturing apparatus and the sub item is a setting item in a layer lower than that of the main item and a control step of limiting operation solely to a release operation of the image capturing apparatus and to the main item and sub item which have been registered at the registration step in a case where operation of the image capturing apparatus has been locked at the lock unlock step.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings.

A preferred embodiment of the present invention will now be described in detail with reference to the accompanying drawings.

In the digital camera of this embodiment a user is capable of changing and setting various parameters setting items relating to photographic use of the camera using a cross key placed on the back of the digital camera and a menu screen displayed on a display unit on the back of the camera. These setting items include a metering mode setting a bracketing setting a shooting mode setting an ISO sensitivity setting a shutter speed setting an aperture setting a white balance setting an image size setting and a picture style setting etc.

Examples of the metering mode that can be set include averaging metering centerweighted metering centerweighted averaging metering spot metering and evaluation metering for dividing a screen into a plurality of areas measuring the brightness of each divisional area and deciding exposure by evaluating the brightness of each divisional area. Examples of a bracketing setting item are an item for setting how many images will be shot by a single depression of the shutter release button and an item for setting to what extent exposure or white balance is changed for every image. A single shooting mode and a continuous shooting mode are examples of shooting modes that can be set. ISO sensitivities that can be set are ISO 100 to ISO 3200 by way of example. Shutter speeds that can be set are e.g. 30 sec to 1 8000 sec. Settable aperture values are e.g. F2.8 to F32. Further sunlight fluorescent lamp electric bulb and cloudy weather etc. can be set for white balance. Examples of settable image sizes are 6 000 000 and 3 000 000 pixels etc. in the case of a camera that uses 10 000 000 pixel image sensor. Further picture style refers to a function whereby the sharpness or color balance of shot image data can be changed according to user preference.

In this embodiment it is possible for these setting items to be locked against change depending upon the volition of the user. In this case the user selects items that are not desired to be locked from among these setting items and sets them as items not locked thereby making it possible to change the settings only of the items that have been selected by the user even in a case where operation of the digital camera has been placed in the locked state.

As a result it is possible for the user to change only items desired to be changed and only items for which a change in setting is not desired can be placed in the locked state by the user. This has the effect of enhancing user convenience.

The blocks in are structural elements classified function by function. First an image capture unit includes an image sensor such as a CCD or CMOS sensor. An image processing unit applies prescribed image processing to the image captured by the image capture unit and converts this image to a JPEG image or RAW image. A recording medium records the image data that has been image processed by the image processing unit and comprises a removable image recording medium such as a memory card. A recording medium sensor senses that a new recording medium has been inserted. A controller arithmetic unit has a program workspace memory and a microcomputer. A program executed by the controller arithmetic unit has been written to a program memory which usually is constituted by a ROM. A work memory is used as a workspace memory for the controller arithmetic unit as a workspace memory employed when a shot image is subjected to image processing and as an image buffer memory for storing image data temporarily. It is usually constituted by a RAM. A display unit displays shot images and images that have been recorded on a recording medium. The display unit is also used as a menu screen for making various settings using an operating unit . The latter allows the operator to set image processing and to designate shooting. A power supply unit supplies power to the overall digital camera.

The display unit shown in is illustrated in . Operating members to constitute the operating unit of . Specifically member is a power switch. When the power switch is in the OFF position supply of power from the power supply unit to the digital camera is stopped and the digital camera is placed in the power OFF state. When the power switch is in the ON position power is supplied from the power supply unit to the digital camera and the digital camera is placed in the power ON state. Member is a cross key. The cross key can be used to select a memory item or to select a reproduced image in response to pressing of any of up down left and right keys. The member is a decide key which is used when an item that has been selected in a menu by the cross key is finalized. The member is a playback button which is used when an image is reproduced and displayed on the display unit . The member is a menu button which is used when a menu is to be displayed.

Next reference will be had to the back panel diagram menu screen diagrams and flowcharts of to describe operation for placing the setting items of various shooting parameters in this embodiment in the locked state or unlock state.

Described first will a method of selecting a main setting item and a method of selecting a subordinate setting item in a layer lower than that of the main setting item when operation of the camera is in the unlocked state. The main item and sub item are shooting parameters that are not locked in this state.

First at step S in the camera is placed in the power ON state when the power switch is operated by the user.

When the menu button is pressed by the user at step S the controller arithmetic unit displays the menu of on the image sensor package . The menu depicted in is a menu that displays setting items for which a selection not to lock has been made by the user. This menu shall be referred to as MY MENU . The two items at the bottom are items necessary for setting of MY MENU and the three menu items in the upper section are menu items that have already been registered in MY MENU as setting items not to be locked.

If the user wishes to increase or decrease the number of setting items that are not to be locked then MY SETTING MENU is selected by the cross key at step S. When this is done the controller arithmetic unit displays the selected menu item in a bold item border so that selection can be discerned. If the user decides entry by pressing the decide key the controller arithmetic unit displays the menu of on the display unit .

While observing the menu illustrated in the user selects REGISTER using the cross key and finalizes this using the decide key at step S. When this is done the controller arithmetic unit displays a registration item menu of the kind illustrated in on the display unit .

While observing the registration item menu illustrated in the user selects e.g. METERING MODE by the cross key and finalizes this using the decide key at step S. When this is done the controller arithmetic unit displays a message of the kind shown in on the display unit .

While observing the message illustrated in the user selects OK by the cross key and finalizes this using the decide key at step S.

In response to this operation the controller arithmetic unit registers the metering mode on the MY MENU screen at step S see . As a result even if the camera has been placed in a state locked against operation the METERING MODE setting can be rendered changeable.

Although a case where a setting is made so as not to lock the METERING MODE has been described an item set so as not to be locked can be selected freely by the user depending upon the wishes of the user from the registration menu items illustrated in . Further by repeating the same operation it is possible to set a plurality of items so as not to be locked.

While observing the menu illustrated in the user selects METERING MODE again by the cross key and finalizes this using the decide key at step S.

In response to this operation the controller arithmetic unit displays a metering mode setting menu which is shown in on the display unit at step S. In all metering modes are selectable.

At step S if the user selects the menu item METERING MODE RESTRICTION the controller arithmetic unit displays a metering mode restricting menu which is shown in on the display unit . Using the cross key and decide key the user places a check mark at the side of menu items e.g. PARTIAL METERING and SPOT METERING which the user wishes to make non selectable in the metering mode restricting menu of . The user then selects APPLY and finalizes this. As a result even in a case where the camera has been placed in a state in which it is locked against operation the setting of METERING MODE is changeable but selection items are restricted in such a manner that partial metering and spot metering cannot be selected as metering modes.

Although partial metering and spot metering have been set here so as not to be selectable it is possible for the user to freely select items desired to be rendered non selectable from the metering mode restricting menu illustrated in . Further a plurality of items can be made non selectable.

While observing the menu illustrated in the user selects METERING MODE again by the cross key and finalizes this using the decide key at step S.

In response to this operation the controller arithmetic unit displays a metering mode setting menu which is shown in on the display unit at step S. In the case of this example partial metering and spot metering are dimmed to render them non selectable. As a result even in a case where the camera has been placed in a state in which it is locked against operation partial metering and spot metering can no longer be selected.

Next reference will be had to the back panel diagram of menu screen diagrams of and the flowchart of to describe a method of switching between the unlocked and locked states and a change of password.

If the user wishes to change over the locked state of the camera or wishes to change the password then the user selects SET LOCK CHANGE PASSWORD from the menu of by the cross key and finalizes this by the decide key at step S. When this is done the controller arithmetic unit displays the menu of on the display unit .

While observing the menu illustrated in and using the cross key and decide key the user enters an already set password selects CHANGE PASSWORD and finalizes this at step S.

At step S the controller arithmetic unit determines whether the entered password is correct or not. Control proceeds to step S if the entered password is correct and returns to step S if the entered password is not correct.

The controller arithmetic unit displays a menu shown in on the display unit at step S. While observing the menu illustrated in and using the cross key and decide key the user enters a new password selects SET and finalizes this. When this is done the controller arithmetic unit changes the password to the new password and the menu returns to the menu shown in .

If the user wishes to place the camera in the locked state then using the cross key and decide key the user enters the already set password selects SET LOCK and finalizes this at step S on the menu shown in .

At step S the controller arithmetic unit determines whether the entered password is correct or not. Control proceeds to step S if the entered password is correct and returns to step S if the entered password is not correct.

The controller arithmetic unit displays a menu shown in on the display unit at step S. This screen displays only the items that have been registered in MY MENU . That is only a change of items registered in MY MENU and a release operation are possible items that have not been registered in MY MENU are locked and cannot be changed.

While observing the menu shown in the user selects METERING MODE by the cross key and finalizes this by the decide key at step S.

In response to this operation the controller arithmetic unit displays a metering mode setting menu which is shown in on the display unit at step S. In this example partial metering and spot metering are dimmed to render them non selectable.

If the user wishes to release the camera from the locked state then while observing the menu shown in the user selects RELEASE LOCK by the cross key and finalizes this by the decide key . When this is done the controller arithmetic unit displays the menu shown in on the display unit .

While observing the menu shown in and using the cross key and decide key the user enters the already set password selects RELEASE LOCK and finalizes this.

At step S the controller arithmetic unit determines whether the entered password is correct or not. Control proceeds to step S if the entered password is correct and returns to step S if the entered password is not correct.

At step S the screen returns to the menu shown in operation of the camera is placed in the unlocked state and all camera functions become capable of being used.

Thus as described above when the camera has been locked against operation the user is capable of selecting a menu item desired to be operated. This has the effect of broadening the operation variations available when the camera has been locked against operation.

Further since it is possible to select a main item and a sub item in a layer lower than the main item the range of setting of camera setting parameters can also be set by way of example and it becomes possible to adopt a method of use in which depending upon the circumstances at a photo studio the brightness parameter is allowed to be changed in limited fashion even if operation of the camera has been locked.

The object of the embodiment is attained also by the following method Specifically a storage medium or recording medium on which the program codes of the software for implementing the functions of the foregoing embodiment is supplied to a system or apparatus. A computer CPU or MPU of the system or apparatus reads out and executes the program codes stored on the storage medium. In this case the program codes per se read from the storage medium implement the functions of the embodiment and the storage medium storing the program codes constitutes the invention. Further by executing the program codes read out by the computer not only are the functions of the embodiment implemented but the following is included in the present invention as well Specifically an operating system or the like running on the computer executes some or all of the actual processing based upon the indications in the program codes and the functions of the above described embodiment are implemented by this processing.

Furthermore the following case also is included in the present invention. Specifically program code read from storage medium is written to a memory provided on a function expansion card inserted into the computer or provided in a function expansion unit connected to the computer. Thereafter a CPU or the like provided on the function expansion card or function expansion unit performs some or all of actual processing based upon the indication in the program codes and the functions of the above embodiment are implemented by this processing.

In a case where the present invention is applied to the above mentioned storage medium program code corresponding to the procedures described earlier is stored on this storage medium.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2007 039827 filed Feb. 20 2007 which is hereby incorporated by reference herein in its entirety.

