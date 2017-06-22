---

title: Rendering processing apparatus and method using multiprocessing
abstract: A rendering processing apparatus and method using multiprocessing are disclosed. The rendering processing method includes dividing an application execution window into frames and generating a rendering processing command for rendering processing of an image on a frame basis by a pre-rendering manager, generating a rendering image on a frame basis according to the rendering processing command by a rendering manager, and storing the generated rendering image in a memory. The generation of a rendering processing command and the generation of a rendering image are performed in a plurality of threads.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08952971&OS=08952971&RS=08952971
owner: Tobesoft Co., Ltd.
number: 08952971
owner_city: Seoul
owner_country: KR
publication_date: 20120913
---
This application claims the benefit of Korean Patent Application No. 10 2012 0088236 filed on Aug. 13 2012 which is hereby incorporated by reference as if fully set forth herein.

The present invention relates to a rendering processing apparatus and method and more particularly to a rendering processing apparatus and method using multiprocessing which can maximize rendering processing performance by simultaneously processing a plurality of threads when an image is processed on a frame basis.

In conventional rendering a single core Central Processing Unit CPU processes an image through double buffering in a single process without using a thread or generates a whole screen by creating one thread in the presence of a performance issue.

The conventional rendering method takes much time to process images included in a plurality of frames. Accordingly considering the recent development of multi core CPUs that is CPUs having 4 or more cores for devices such as a laptop computer a PC a tablet PC or a smart phone there exists a need for a technique for fast processing an image.

Accordingly the present invention is directed to a rendering processing apparatus and method using multiprocessing that substantially obviate one or more problems due to limitations and disadvantages of the related art.

An object of the present invention is to provide a rendering processing apparatus and method using multiprocessing for improving image processing performance by simultaneously processing a plurality of threads when an image is processed on a frame basis.

Additional advantages objects and features of the invention will be set forth in part in the description which follows and in part will become apparent to those having ordinary skill in the art upon examination of the following or may be learned from practice of the invention. The objectives and other advantages of the invention may be realized and attained by the structure particularly pointed out in the written description and claims hereof as well as the appended drawings.

In an aspect of the present invention a rendering processing method using multiprocessing includes dividing an application execution window into frames and generating a rendering processing command for rendering processing of an image on a frame basis by a pre rendering manager generating a rendering image on a frame basis according to the rendering processing command by a rendering manager and storing the generated rendering image in a memory. The generation of a rendering processing command and the generation of a rendering image are performed in a plurality of threads.

The rendering processing command may be generated according to a per frame rendering processing order by the pre rendering manager.

When a Scene Graph SC optimizer determines that a plurality of processing requests are successively received for generation of the same image at the same coordinates in a frame by scanning a pre rendering queue that receives the rendering processing requests processing of only one of the plurality of processing requests may be controlled by the SG optimizer.

A program that performs the rendering processing method may be recorded to a computer readable recording medium.

In another aspect of the present invention a rendering processing apparatus using multiprocessing includes a pre rendering manager for dividing an application execution window into frames and generating a rendering processing command for rendering processing of an image on a frame basis a rendering manager for generating a rendering image on a frame basis according to the rendering processing command and a memory for storing the generated rendering image. The generation of a rendering processing command in the pre rendering manager and the generation of a rendering image in the rendering manager are performed in a plurality of threads.

The pre rendering manager may generate the rendering processing command according to a per frame rendering processing order.

The pre rendering manager may include a pre rendering queue for receiving an image processing event command and an SC optimizer for if determining that a plurality of processing requests are successively received for generation of the same image at the same coordinates in a frame by scanning the pre rendering queue controlling processing of only one of the plurality of processing requests.

A rendering processing apparatus and method using multiprocessing according to an embodiment of the present invention will be described below with reference to the attached drawings.

In the present invention rendering is an image process such as a process of configuring a new window by generating a new image corresponding to an event upon occurrence of the event on a window displayed on a display by executing an application.

Referring to a rendering processing apparatus using multiprocessing includes a rendering engine and a memory .

The pre rendering manager generates a final rendering command by storing and managing information needed for rendering before rendering.

Specifically when an application is executed the pre rendering manager divides an application execution window displayed on a screen into frames and generates a rendering processing command for rendering processing of an image on a frame basis.

Referring to upon execution of an application an application execution window W is displayed. The window W may be divided into different frames F1 F2 and F3.

In the case where rendering processing is performed on a window basis upon occurrence of an event in a specific frame the whole window is subjected to rendering processing even though existing images are maintained in the other frames. As a result a rendering processing speed may be decreased.

In contrast the present invention can increase an image processing speed by dividing a window into frames and processing an image on a frame basis.

The pre rendering manager generates rendering processing commands according to a per frame rendering processing order. Specifically the pre rendering manager sequentially receives rendering processing requests requesting rendering processing on a frame basis. Then the pre rendering manager generates rendering processing commands according to the input order of the rendering processing requests and transmits the rendering processing commands to the rendering manager .

Meanwhile the rendering manager is a rendering module that creates an image by sequentially processing rendering processing commands generated from the pre rendering manager and thus performing drawing in an intended buffer.

The task of generating a rendering processing command in the pre rendering manager and the task of generating a rendering image in the rendering manager may be processed in a plurality of threads.

In case of a single thread only one of the rendering processing command generation task and the rendering image generation task is performed in the single thread at a specific time point. In contrast in case of a plurality of threads a plurality of rendering processing command generation and rendering image generation tasks can be performed simultaneously. Therefore the rendering processing speed can be maximized.

Now a detailed description will be given of the configurations and functions of the pre rendering manager and the rendering manager of the rendering engine .

Referring to the pre rendering manager includes a pre rendering queue a location adjuster a plurality of Scene Graphs SGs an SG manipulator an SG optimizer and an SC commander .

The pre rendering queue receives a rendering processing request and generates a rendering processing command corresponding to the received rendering processing request. The rendering processing request input to the pre rendering queue may be considered in three cases. First of all a command may be input through an element interface. Another case is that when a request regarding specific coordinates of a screen displayed on a display is received the pre rendering queue may receive a command regarding an element at the coordinates from a hittest manager not shown of the rendering engine . Finally the pre rendering queue may receive a command from a canvas module including a drawing interface and a painter.

The location adjuster is a module for processing location information. The location adjuster performs an Update Rect process taking into account correction and transformation of rendering coordinates.

The location adjuster may exclude a covered part of a frame of a window behind another overlapping window on the display from a rendering processing area in order to avoid rendering processing of the covered part.

The SGs store and manage information to be maintained for rendering. The SGs correspond to depth first acyclic graphs. In addition the SGs represent a drawing order and an inclusion relationship determine an object to be rendered in an updated area and generate a rendering processing command from a determined node.

The SG manipulator adds deletes inserts or moves a node of the SGs . The SG manipulator also changes the contents of the SGs .

Especially when determining that rendering processing requests for generation of the same image at the same coordinates in a frame are successively received by scanning the pre rendering queue the SG optimizer may control processing only one of the rendering processing requests.

The SG commander generates a rendering processing command for an updated area generated by the location adjuster .

The hittest manager processes hittest information and determines an element that has been hit with respect to requested coordinates. The hittest manager executes a rendering processing request and processes a response through the pre rendering queue in order to use the SGs .

Referring to the rendering manager includes a rendering queue for executing a rendering processing command a painter for performing drawing and a VGLib being a rendering Application Programming Interface API library.

The painter which is a module for drawing in a drawing buffer has an interface for using the VGLib . In case of drawing through the canvas module an image may be drawn directly using the painter .

As is apparent from the above description the rendering processing apparatus and method using multiprocessing according to the embodiments of the present invention can maximize image processing performance through rendering processing of an image on a frame basis in a plurality of threads using multiprocessing.

The rendering method using multiprocessing according to the embodiment of the present invention may be written to a computer readable recording medium as a program that can be executed by a computer. The computer readable recording medium may include a program command a data file and a data structure alone or in combination. A program command written to the computer readable recording medium may be specially designed and configured for the present invention or known to those skilled in the art of computer software. Examples of the computer readable recording medium include a magnetic storage medium such as a hard disk a floppy disk or a magnetic tape an optical medium such as a CD ROM or a DVD a magneto optical medium such as a floptical disk and a hardware device specially configured to store and execute a program command such as a ROM a RAM or a flash memory. Examples of a program command include a premium language code executable by a computer using an interpreter as well as a machine language code made by a compiler.

Those skilled in the art will appreciate that the present invention may be carried out in other specific ways than those set forth herein without departing from the spirit and essential characteristics of the present invention. The above embodiments are therefore to be construed in all aspects as illustrative and not restrictive. The scope of the invention should be determined by the appended claims and their legal equivalents not by the above description and all changes coming within the meaning and equivalency range of the appended claims are intended to be embraced therein.

