---

title: Method and device for determining a display mode of electronic documents
abstract: A method and a device for determining a display mode of an electronic document on a screen are provided. The method may comprise: obtaining the size of the screen and the original layout size of the electronic document; determining, from the obtained original layout size, a document layout length in a layout direction of the original layout of the electronic document; determining, from the obtained size of the screen, a screen reading length in a reading direction of the screen; and comparing the document layout length with the screen reading length to determine whether a fixed-layout display mode or a flow display mode shall be selected to display the electronic document.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08898561&OS=08898561&RS=08898561
owner: Beijing Founder Apabi Technology Ltd.
number: 08898561
owner_city: Beijing
owner_country: CN
publication_date: 20121231
---
This application claims the benefit of Chinese Patent Application No. 201110457686.3 filed on Dec. 30 2011 which is incorporated herein by reference in its entirety as part of this application.

The application relates to digital publishing technology and in particular to a method and a device for determining a mode for displaying electronic documents and for displaying the electronic documents.

Common electronic documents can be classified into fixed layout documents and flow layout documents based on different display modes thereof. Fixed layout documents utilize an absolute positioning mode to record the location and the size of each primitive such that the documents are scalable as a whole in accordance with various display screen sizes using a consistent typesetting format i.e. the layout the font or the like are entirely consistent with those of the corresponding paper documents . Therefore fixed layout documents have the same display effects as the corresponding paper documents. In contrast flow layout documents only record the size of each primitive and the sequential relationship between the primitives and thus various display formats are available based on different screen sizes. Hence the line feeds between paragraphs and the word sizes are adjustable according to the width of display screens.

2 those from which data content can be extracted such as PDF Portable Document Format documents. For this kind of documents the data contents can be reformatted according to the storage order thereof without considering their absolute positioning.

In addition to the above fixed layout and flow layout documents there is another kind of document named as fixed flow layout documents. Fixed flow layout documents record not only the absolute location and the size of each primitive but also the sequential relationship between the primitives. Therefore fixed flow layout documents can be displayed using both the fixed layout mode and the flow layout mode.

Accordingly fixed flow layout documents and fixed layout documents from which data content can be extracted such as PDF documents can be displayed using the fixed layout mode or the flow layout mode. Nowadays fixed flow layout documents are generally displayed in fixed layout by default on large screens such as the screen of an office computer and in flow layout by default on screens of mobile equipment such as the screen of a mobile phone . However with the development of electronic equipment their screen sizes have become highly diversified for example the screens of tablet PCs have become smaller and smaller while those of mobile phones have become wider and wider. Therefore it may be unreliable to select display modes based on equipment types and unable to achieve optimal display effects using conventional default display methods.

The application provides a method and a device for determining a display mode of electronic documents to solve at least one of the issues in the art as mentioned above.

In one aspect a method for determining a display mode of an electronic document on a screen is provided. The method may comprise 

determining from the obtained original layout size of the electronic document a document layout length in a layout direction of the original layout of the electronic document 

determining from the obtained size of the screen a screen reading length in a reading direction of the screen and

comparing the document layout length with the screen reading length to determine whether a fixed layout display mode or a flow display mode shall be selected to display the electronic document.

In another aspect a device for determining a display mode of an electronic document on a screen is provided. The device may comprise 

a size obtaining module configured to obtain the size of the screen and the original layout size of the electronic document 

a layout length module configured to determine from the obtained original layout size of the electronic document a document layout length in a layout direction of the original layout of the electronic document 

a reading length module configured to determine from the obtained size of the screen a screen reading length in a reading direction of the screen and

a mode determining module configured to compare the document layout length with the screen reading length to determine whether a fixed layout display mode or a flow display mode shall be selected to display the electronic document.

Hereinafter the embodiments of the methods and devices for determining display modes of electronic documents will be described in detail with reference to the detailed description as well as the drawings.

In one embodiment as shown in the method for determining a display mode of an electronic document on a screen of an equipment may comprise 

step determining from the obtained original layout size of the electronic document a document layout length in a layout direction of the original layout of the electronic document 

step determining from the obtained size of the screen a screen reading length in a reading direction of the screen and

step comparing the document layout length with the screen reading length to determine whether a fixed layout display mode or a flow display mode shall be selected to display the electronic document. In the fixed layout display mode the electronic document may be displayed according to the original layout of the electronic document. In the flow display mode the electronic document may be displayed according to a layout obtained after the electronic document is reformatted.

The method disclosed in the present application may solve the problem in determining the optimal display mode for fixed flow layout documents and fixed layout documents from which data content can be extracted based on various screen sizes.

In some embodiments in step the size of the screen may be determined by determining a ratio of a screen resolution of the equipment to an equipment resolution wherein the screen resolution of the equipment is the number of all pixels displayed on the screen and the equipment resolution is the number of pixels per inch displayed on the screen.

In step the size of the screen may be obtained in any appropriate methods. In some embodiments the size of the screen may be calculated by a program obtained automatically or inputted manually. The method for obtaining the size of the screen is not limited. In some embodiments the screen resolution of the equipment and the equipment resolution may be obtained through the API Application Programming Interface of the equipment.

In some embodiments step may comprise determining whether the document layout length is smaller than the screen reading length if yes the fixed layout display mode may be selected otherwise the flow display mode may be selected.

Since the screen size may be smaller than the original layout size of the electronic document the result of comparison between the screen size and the original layout size of the electronic document may be used to determine whether the document shall be reformatted and then displayed i.e. to determine which display mode shall be selected the fixed layout display mode or the flow display mode. Nowadays display equipment such as mobile phones tablet PCs and the like may have two display modes a landscape display mode and a portrait display mode. Meanwhile electronic documents may also have two layout directions a horizontal type and a vertical type. In some embodiments of the method disclosed in the present application the current reading direction length of the screen the screen reading length may be first compared with the layout direction length of the original layout of the electronic document the document layout length i.e. the reading length and then it is determined according to the comparison result whether the fixed layout display mode or the flow display mode shall be selected.

determining whether the scaled layout size is smaller than the screen reading length if yes selecting the fixed layout display mode and displaying the electronic document based on the scaled layout size otherwise selecting the flow display mode to display the electronic document.

The original layout size of the electronic document may be consistent with the layout sizes used in print publication such as A4 layout B5 layout and the like. However the screen size of many equipments may be smaller than the layout sizes used in print publication. In fact the electronic document may not need to be reformatted when the screen reading length is slightly smaller than the document layout length. For example if the screen reading length is 0.01 inch smaller than the document layout length the electronic document may not need to be reformatted and may be displayed better through appropriately scaling the original layout size of the electronic document within a scaling scope visible to human eyes . Therefore in some embodiments if the difference between the screen reading length and the document layout length is within a certain predetermined range the electronic document may not need to be reformatted for display but may be displayed based on the original layout of the document through slightly scaling the original layout size of the document. Thus in some embodiments the fixed layout display mode obtained through slightly scaling the original layout size of the document rather than the flow layout display mode may be selected.

In some embodiments for determining whether the flow display mode or the fixed layout display mode obtained through slightly scaling the original layout size of the document shall be selected the following method may also be used 

determining whether the scaled layout size is smaller than the screen reading length if yes selecting the fixed layout display mode and displaying the electronic document based on the scaled layout size otherwise selecting the flow display mode to display the electronic document.

In some embodiments a program may be provided to supply a data sheet comprising scale factors corresponding to the original layouts of various documents. The scale factors may be determined empirically. In some embodiments the scale factor of an electronic document to be displayed may be determined by the program according to the original layout size of the document and the screen size of the equipment. A scaled layout size may be then obtained by multiplying the document layout length by the scale factor. For a document it may be determined whether the scaled layout size is smaller than the screen reading length and if yes the fixed layout display mode may be selected to display the electronic document based on the scaled layout size otherwise the flow display mode may be selected to display the electronic document. The scale factor may be determined according to the original layout size of the document to provide a better human visual perception.

In some embodiments when the flow display mode is selected the method disclosed herein may further comprise 

step calculating according to the screen reading length and a predetermined number of words per line a font size to be used when the document is displayed with the predetermined number of words per line along the reading direction of the screen and

step determining whether the calculated font size is smaller than a predetermined font size and if yes selecting the predetermined font size to display otherwise selecting the calculated font size to display.

Whatever type of equipment is used human visual perception may be affected by the font the font size and the number of words per line. In some embodiments to ensure that the reader will have a better visual experience with any equipment i.e. the reader will not feel eye irritation caused by a too small or too large font size or by too many or too few words per line the program disclosed herein may determine the predetermined number of words per line based on an optimal number of words per line according to a practical experience and determine the predetermined font size based on a minimum font size which can be resolved by human eyes under normal sight distance according to a practical experience. In some embodiments the following process may be carried out when the flow display mode is selected 1 calculating according to the screen reading length and a predetermined number of words per line a font size to be used when the document is displayed with the predetermined number of words per line along the reading direction and 2 determining whether the calculated font size is smaller than the predetermined font size and if yes selecting the predetermined font size to display otherwise selecting the calculated font size to display. When using predetermined font size to display the number of words per line may not be the same as the predetermined number of words per line. Hence the display effect may be suitable for human eyes when the document is reformatted with the selection of the flow display mode or when the document is displayed based on the predetermined number of words per line or the predetermined font size.

Hereinafter the method for determining the display mode of electronic documents will be further described with reference of embodiments.

Specifically the screen resolution of the tablet PC which is 768 1024 pixels and the equipment resolution of the table PC which is 132 pixels inch are obtained and the ratio of the screen resolution to the equipment resolution is calculated to obtain the screen size of the tablet PC which is 5.82 7.76 inches . Hence when the tablet PC is used in the landscape display mode the screen reading length i.e. the length in the reading direction of the screen is 5.82 inches when the table PC is used in the vertical display mode the screen reading length is 7.76 inches. The original layout size of the e book is 8.27 width 11.69 height inches according to the A4 layout wherein the document layout length i.e. the length in the layout direction of the original layout of the e book is 8.27 inches.

Step A2 the document scale factor is determined as 0.7 and the scaled layout size is obtained by multiplying the document layout length by the document scale factor. For example the document layout length is 8.27 inches and the document scale factor is 0.7. Accordingly the scaled layout size is 5.79 inches.

Step A3 it is determined whether the scaled layout size is less than the screen reading length and if yes the fixed layout display mode will be selected otherwise the flow display mode will be selected.

Specifically if the tablet PC is used in the landscape display mode the screen reading length which is 5.82 inches is greater than the scaled layout size which is 5.79 inches and thus the fixed layout display mode is selected i.e. the e book is displayed with the scaled layout size of 5.79 inches according to the original layout of the e book.

If the table PC is used in the vertical display mode the screen reading length which is 7.76 inches is greater than the scaled layout size which is 5.79 inches and thus the fixed layout display mode is selected again. That is the e book is displayed with the scaled layout size of 5.79 inches according to the original layout of the e book.

Specifically the screen resolution of the mobile phone which is 640 960 pixels and the equipment resolution of the mobile phone which is 326 pixels inch are obtained. The ratio of the screen resolution to the equipment resolution is calculated to obtain the screen size of the mobile phone which is 1.96 2.94 inches . Hence when the mobile phone is used in the landscape display mode the screen reading length is 1.96 inches and when the mobile phone is used with the vertical display mode the screen reading length is 2.94 inches. The original layout size of the e book is 8.27 width 11.69 height inches and its document layout length is 8.27 inches.

Step B2 the document scale factor is determined as 0.7 and the scaled layout size is obtained by multiplying the document layout length by the document scale factor. Specifically the document layout length is 8.27 inches and the document scale factor is 0.7. Accordingly the scaled layout size is 5.79 inches.

Step B3 it is determined whether the scaled layout size is smaller than the screen reading length and if yes the fixed layout display mode will be selected otherwise the flow display mode will be selected.

Specifically if the mobile phone is used in the landscape display mode the screen reading length of 1.96 inches is smaller than the scaled layout size which is 5.79 inches and thus the flow display mode will be selected. If the mobile phone is used in the vertical display mode the screen reading length of 2.94 inches is smaller than the scaled layout size which is 5.79 inches and thus the flow display mode will be selected again.

Step B4 the font size with which the document would be displayed based on the predetermined number of words per line along the current reading direction of the screen is calculated according to the screen reading length and the predetermined number of words per line. And then it is determined whether the calculated font size is smaller than the predetermined font size. If yes the document will be displayed with the predetermined font size otherwise the document will be displayed with the predetermined number of words per line.

For example the predetermined number of words per line may be determined as 20 and the predetermined font size may be determined as 12 points.

When the mobile phone is used in the landscape display mode the screen reading length is 1.96 inches and the font size would be 7 points if the number of word per line is 20. The font size of 7 points is smaller than the predetermined font size of 12 points. Therefore the predetermined word size of 12 points will be selected to display the document.

When the mobile phone is used in the vertical display mode the screen reading length is 2.94 inches and the font size will be 10 points if the number of words per line is 20. The font size is smaller than the predetermined font size of 12 points. Therefore the predetermined word size of 12 points will be selected to display the document.

In some embodiments as shown in a device for determining a display mode of an electronic document on a screen of an equipment is also provided. The device may comprise 

a size obtaining module configured to obtain the size of the screen and the original layout size of the electronic document 

a layout length module configured to determine from the obtained original layout size of the electronic document a document layout length in a layout direction of the original layout of the electronic document 

a reading length module configured to determine from the obtained size of the screen a screen reading length in a reading direction of the screen and

a mode determining module configured to compare the document layout length with the screen reading length to determine whether a fixed layout display mode or a flow display mode shall be selected to display the electronic document.

In some embodiments the size obtaining module may be configured to calculate a ratio of a screen resolution of the equipment to an equipment resolution so as to obtain the screen size wherein the screen resolution of the equipment is the number of all pixels displayed on the screen and the equipment resolution is the number of pixels per inch displayed on the screen.

In some embodiments the mode determining module may be configured to determine whether the document layout length is smaller than the screen reading length and if yes selecting the fixed layout display mode otherwise selecting the flow display mode.

In some embodiments the mode determining module may be configured to determine a scale factor based on the original layout size of the document so as to calculate a scaled layout size by multiplying the document layout length by the scale factor. The mode determining module may also be configured to determine whether the scaled layout size is smaller than the screen reading length and if yes select the fixed layout display mode so that the document is displayed with the scaled layout size otherwise select the flow display mode.

In some embodiments the device for determining the display mode of the electronic document may further comprise 

a flow layout module configured to calculate when the document is displayed based on a predetermined number of words per line along the current reading direction of the screen a font size according to the screen reading length and the predetermined number of words per line and to determine whether the calculated font size is smaller than the predetermined font size and if yes select the predetermined font size for display otherwise select the calculated font size for display.

A person having ordinary skill in the art should appreciate that the function and operation of each module mentioned above in the device disclosed herein may be implemented by a processor of the device. The methods for determining the display mode of the electronic document described above may be implemented by a processor. The device may include a storage medium that stores the program for performing the methods. The storage medium may include one or more magnetic storage media such as hard drive disks one or more optical storage media such as computer disks CDs DVDs one or more semiconductor storage medium such as flash drives SD cards memory sticks or any other suitable computer readable medium.

Embodiments and implementations of the present application have been illustrated and described and it should be understood that various other changes may be made therein without departing form the scope of the application.

