---

title: Machine processor
abstract: Disclosed are machine processors and methods performed thereby. The processor has access to processing units for performing data processing and to libraries. Functions in the libraries are implementable to perform parallel processing and graphics processing. The processor may be configured to acquire (e.g., to download from a web server) a download script, possibly with extensions specifying bindings to library functions. Running the script may cause the processor to create, for each processing unit, contexts in which functions may be run, and to run, on the processing units and within a respective context, a portion of the download script. Running the script may also cause the processor to create, for a processing unit, a memory object, transfer data into that memory object, and transfer data back to the processor in such a way that a memory address of the data in the memory object is not returned to the processor.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09069549&OS=09069549&RS=09069549
owner: GOOGLE TECHNOLOGY HOLDINGS LLC
number: 09069549
owner_city: Mountain View
owner_country: US
publication_date: 20121010
---
The present application claims priority to U.S. Provisional Application No. 61 546 317 entitled JAVASCRIPT BINDINGS TO OPENCL filed Oct. 12 2011. The present application is related to U.S. patent application Ser. No. 13 648 349 entitled MACHINE PROCESSOR filed Oct. 10 2012 U.S. patent application Ser. No. 13 648 354 entitled MACHINE PROCESSOR filed Oct. 10 2012 U.S. patent application Ser. No. 13 648 366 entitled PROVISION OF A DOWNLOAD SCRIPT filed Oct. 10 2012 and U.S. patent application Ser. No. 13 648 373 entitled PROVISION AND RUNNING A DOWNLOAD SCRIPT filed Oct. 10 2012.

The OpenCL framework is a framework for writing computer programs. OpenCL provides for parallel computing to be performed. Further information on OpenCL may be found for example in The OpenCL Specification Version 1.1 A. Munshi June 2011 which is incorporated herein by reference.

Typically websites web pages web applications etc. are provided in the form of scripts e.g. in HTML format or in JavaScript etc. and are not compiled computer programs.

Turning to the drawings wherein like reference numerals refer to like elements techniques of the present disclosure are illustrated as being implemented in a suitable environment. The following description is based on embodiments of the claims and should not be taken as limiting the claims with regard to alternative embodiments that are not explicitly described herein.

The present inventors have realized that as websites become more complicated there is a desire or need for websites web pages web applications etc. to use the power of the computers they are running on i.e. there is a desire for web pages etc. to be able to use the multiple processor cores graphics cards etc. of a computer . The present inventors have realized that in order to do so a mechanism that allows access to the OpenCL methods and functions from within a script needs to be provided.

Embodiments provide a machine processor e.g. a virtual machine processor such as a JavaScript module capable of executing JavaScript commands and a method performed by the machine processor. The machine processor may have access to one or more underlying processing units e.g. a graphics processing unit or a central processing unit of a computer for performing data processing. The machine processor may have access to a function library e.g. an OpenCL function library which is described in more detail below which may contain one or more functions e.g. OpenCL functions which are described in more detail below . The functions may be implementable by the underlying processing units to perform parallel processing. The machine processor may be configured to acquire e.g. by downloading over the Internet from a web server a download script e.g. a web page etc. . This download script may comprise commands e.g. written in JavaScript for the machine processor that comprises a binding e.g. a JavaScript binding to a corresponding function in the function library. The machine processor may be further configured to run the download script such that the commands are run. This may cause the machine processor to create for each underlying processing unit a context i.e. a parallel context in which one or more of the functions may be run and run on one or more underlying processing units and within a respective context a portion of the download script.

Further embodiments provide a machine processor e.g. a virtual machine processor such as a JavaScript module capable of executing JavaScript commands and a method performed by the machine processor. The machine processor may have access to an underlying processing unit e.g. a graphics processing unit or a central processing unit of a computer for performing data processing. The machine processor may have access to a function library e.g. an OpenCL function library which is described in more detail below which may contain one or more functions e.g. OpenCL functions which are described in more detail below . The functions may be implementable by the underlying processing unit e.g. to perform parallel processing. The machine processor may be configured to acquire e.g. by downloading over the Internet from a web server a download script e.g. a web page etc. . This download script may comprise commands e.g. written in JavaScript for the machine processor that comprises a binding e.g. a JavaScript binding to a corresponding function in the function library. The machine processor may be further configured to run the download script such that the commands are run. This may cause the machine processor to create for the underlying processing unit a memory object or buffer thereby reserving at least part of the memory of that underlying processing unit into which data may be transferred from the machine processor and to transfer data from the machine processor into that memory object or buffer. The memory object or buffer may be such that the underlying processing unit for which the memory object or buffer has been created may process the data transferred into the memory object or buffer. Running the script may further cause data after having been processed by the processing unit to be transferred back from the memory object or buffer to the machine processor in such a way that a memory address of the data in the memory object or buffer is not returned to the machine processor.

Further embodiments provide a machine processor e.g. a virtual machine processor such as a JavaScript module capable of executing JavaScript commands and a method performed by the machine processor. The machine processor may have access to an underlying processing unit e.g. a graphics processing unit for performing data processing. The machine processor may have access to a function library e.g. an OpenCL function library which is described in more detail below which may contain one or more functions e.g. OpenCL functions which are described in more detail below . The functions may be implementable by the underlying processing unit e.g. to perform parallel processing. The machine processor may also have access to a further function library e.g. an OpenGL function library which is described in more detail below which may contain one or more further functions e.g. OpenGL functions which are described in more detail below . The further functions may be implementable by the underlying processing unit e.g. to perform graphics processing or rendering. The machine processor may be configured to acquire e.g. by downloading over the Internet from a web server a download script e.g. a web page etc. . This download script may comprise commands e.g. written in JavaScript for the machine processor that comprises a binding e.g. a JavaScript binding to a corresponding function or further function. The machine processor may be further configured to run the download script such that the commands are run. This may cause the machine processor to create for the underlying processing unit a context in which one or more of the functions may be run create for the underlying processing unit a further context in which one or more of the further functions may be run run on the underlying processing unit and within the context a portion of the download script and run on the underlying processing unit and within the further context a further portion of the download script.

Further embodiments provide methods and apparatus for providing download script for accessing or downloading by a machine processor for running by the machine processor . The machine processor may have access to one or more underlying processing units e.g. a graphics processing under or a central processing unit of a computer for performing data processing. The machine processor may have access to a function library e.g. an OpenCL function library which is described in more detail below which may contain one or more functions e.g. OpenCL functions which are described in more detail below . The functions may be implementable by the underlying processing units to perform parallel processing. The methods may comprise a computer sending e.g. via the Internet to a first web server a request for an extension to be returned to the computer. The extension may specify one or more bindings to a corresponding function in the function library. The extension may be such that when run e.g. by the machine processor a corresponding function from the function library is called. The method may further comprise after receiving the request the web server sending the extension back to the computer. The computer may then receive the requested extension which may then be used to write a script for implementation by the machine processor. The script may be uploaded to a further web server from which it may be accessed or downloaded by the machine processor.

Further embodiments provide methods and apparatus for storing e.g. on a web server and running a download script. The download script may be stored such that it is accessible or downloadable by a machine processor. The machine processor may have access to one or more underlying processing units e.g. a graphics processing unit or a central processing unit of a computer for performing data processing. The machine processor may have access to a function library e.g. an OpenCL function library which is described in more detail below which may contain one or more functions e.g. OpenCL functions which are described in more detail below . The functions may be implementable by the underlying processing units to perform parallel processing. The script may be such that when run by the machine processor the machine processor creates for an underlying processing unit a memory object or buffer thereby reserving at least part of the memory of that underlying processing unit into which data may be transferred from the web browser. The memory object or buffer may be such that a data type for each data item within the memory object or buffer is specified thereby providing that data may be stored in the memory object or buffer as a typed array.

An apparatus for implementing any of the below described arrangements and for performing any of the below described methods may be provided by configuring or adapting any suitable apparatus for example one or more computers or other processing apparatus or processors or providing additional modules. The apparatus may include a computer a network of computers or one or more processors for implementing instructions and using data including instructions and data in the form of a computer program or plurality of computer programs stored in or on a machine readable storage medium such as computer memory a computer disk ROM PROM etc. or any combination of these or other storage media.

It should be noted that certain of the processes depicted in the below described process flowcharts may be omitted or such processes may be performed in an order different from that presented below and shown in the process flowcharts. Furthermore although all the processes have for convenience and ease of understanding been depicted as discrete and temporally sequential nevertheless some of the processes may in fact be performed simultaneously or at least overlapping to some extent temporally.

Referring now to the figures is a schematic illustration not to scale of an example network in which embodiments can be implemented.

The network comprises a first web server a second web server the Internet a first computer and a second computer .

The first web server is described in more detail below with reference to . The first web server is connected to each of the second web server the first computer and the second computer . These connections are via the Internet . These connections are such that information may be sent between the first web server and each of the second web server the first computer and the second computer e.g. as described in more detail below with reference to and .

The second web server is described in more detail below with reference to . In addition to being connected to the first web server the second web server is connected to the first computer and to the second computer . These connections are via the Internet . These connections are such that information may be sent between the second web server and each of the first computer and the second computer e.g. as described in more detail below with reference to and .

In this embodiment the first and second web servers are separate web servers. However in other embodiments the first and second web servers may be provided by a single web server.

The first computer is described in more detail below with reference to . In addition to being connected to the first and second web servers via the Internet the first computer is connected to the second computer . The connection between the first computer and the second computer may be via the Internet . The connection between the first computer and the second computer is such that information may be passed between the first computer and the second computer e.g. as described in more detail below with reference to and .

In this embodiment the first and second computers are separate computing devices. However the functionality described in more detail below of the first and second computers may be provided by a different number computing devices e.g. by a single computing device.

Each of the first and second computers may be any appropriate type of computer for example a desktop personal computer a laptop computer a tablet computer a mobile station a smartphone a netbook etc.

In this embodiment the first web server hosts a web page . The web page is accessible or downloadable by the first computer via the Internet . The web page may comprise HTML code Cascading Style Sheets scripts indicated in by a box and the reference numeral and an image indicated in by a box and the reference numeral . The image may for example be in the form of a .jpg file. In other embodiments a reference to an image that may be used to retrieve or locate that image may form part of the web page .

The scripts comprise code written in the JavaScript scripting language. This JavaScript code is indicated in by a box and the reference numeral . The scripts may further comprise other scripts that may for example include kernel code.

The JavaScript code comprises one or more commands. The commands are hereinafter referred to as WebCL commands and are indicated in FIG. by the reference numeral . The WebCL commands are commands for an application programming interface API hereinafter referred to as the WebCL API. The WebCL API is described in more detail below with reference to . In this embodiment the WebCL API is located on the first computer . In other words the WebCL commands are commands that are specified using a framework hereinafter referred to as the WebCL framework. The WebCL framework is described in more detail below. The WebCL API is an API for the WebCL framework.

In this embodiment the first web server hosts a web page specified using a script . However in other embodiments the script may specify different content i.e. other than a web page. For example in other embodiments the script may specify image or video data.

The second web server comprises a repository i.e. memory or storage . The contents of the repository are accessible or downloadable by the first and second computer via the Internet . The repository may comprise one or more extensions hereinafter referred to as WebCL extensions and indicated in by the reference numeral . WebCL extensions are described in more detail below. A WebCL extension may comprise or specify one or more commands methods interfaces attributes etc. for use by a computer programmer or software developer when writing WebCL scripts or by the WebCL API. A WebCL extension may comprise or specify one or more commands methods interfaces attributes etc. that do not form part of the WebCL framework.

The first computer comprises a web browser a graphical processing unit GPU a central processing unit CPU an OpenCL library and a display .

The web browser is described in more detail below with reference to . The terminology web browser is used herein to refer an application that may retrieve and process information resources on the World Wide Web via the Internet . The web browser is connected to the GPU and to the CPU such that information may be sent between the web browser and each of the GPU and the CPU . The web browser may for example be running on the CPU . Also the web browser is connected to the OpenCL library such that information stored in the OpenCL library may be retrieved from the OpenCL library by the web browser . Also the web browser is connected to the display such that information may be sent from the web browser to the display .

The OpenCL library is a library comprising functions methods interfaces attributes etc. of the OpenCL framework. Such functions methods interfaces attributes etc. of the OpenCL framework are indicated schematically in by boxes and by the reference numeral . The OpenCL framework is a framework for heterogeneous parallel computing. Further information on OpenCL may be found for example in The OpenCL Specification Version 1.1 A. Munshi June 2011.

The OpenCL library and the web browser may be linked e.g. statically or dynamically . For example a static linking between the OpenCL library and the web browser may provide that OpenCL code may be compiled as part of the web browser. Also for example a dynamic linking between the OpenCL library and the web browser may provide that the OpenCL library may be installed somewhere else on the first computer and the web browser may simply access the OpenCL library .

The GPU and the CPU may each be configured to process information received from the web browser . For example a computer program received by the GPU or by the CPU may be implemented by the GPU or by the CPU respectively . Information that has been processed by the web browser may be returned from the GPU or from the CPU to the web browser . The functionalities of the GPU and the CPU are described in more detail below with reference to . Each of the GPU and the CPU may be controlled or accessed using OpenCL commands or language. In other words the GPU and the CPU are pieces of hardware that can be controlled or accessed using OpenCL . Thus the GPU and the CPU are both OpenCL devices as defined in The OpenCL Specification Version 1.1 A. Munshi June 2011. In some embodiments a different type of OpenCL device e.g. a different type of CPU a different type of GPU etc. may be used instead of or in addition to the GPU or the CPU .

The display may be any appropriate type of display e.g. a touch screen display. The display may be configured to display information sent to it from the web browser .

The web browser comprises a JavaScript module . The JavaScript module is configured to process run or execute the JavaScript code of the web page . The JavaScript module therefore provides a machine processor or virtual machine processor for processing scripts. The JavaScript module comprises the WebCL API .

The WebCL API is an API for a framework hereinafter referred to as the WebCL framework and described in more detail below. The WebCL framework is a JavaScript binding for the OpenCL framework. The WebCL framework advantageously allows for the execution of OpenCL code in JavaScript . OpenCL code advantageously tends to facilitate or allow computer applications to use or exploit the power of a computer e.g. by executing programs using multiple processor cores graphics cards etc. . The WebCL API is configured to process run or execute the WebCL commands of the JavaScript code of the web page . The WebCL API may act as an interface between the web browser and the OpenCL library such that when a WebCL command is run by the web browser OpenCL functions corresponding to that WebCL command are called.

In this embodiment the WebCL API may comprise or have access to one or more interfaces hereinafter referred to as WebCL interfaces and indicated in by the reference numeral . Each WebCL interface may comprise one or more methods or objects which are jointly indicated in by the reference numeral . When processing running or executing a WebCL command the WebCL API may call a corresponding OpenCL function or method from the OpenCL library . In other words when a WebCL command is run the OpenCL function that that WebCL command is a binding to may be called. Thus running WebCL commands can be thought of as translating those commands into the OpenCL language e.g. for use by an OpenCL device. An OpenCL device is defined in The OpenCL Specification Version 1.1 A. Munshi June 2011. In this embodiment the GPU of the first computer is an OpenCL device and may be controlled using OpenCL commands methods functions etc.

The web browser may further comprise a number of further modules not shown in the figures. For example the web browser may comprise a kernel module that may function as a bridge between the web browser application and the data processing hardware e.g. the GPU or the CPU of the first computer . Such a kernel may be configured to manage the resources of the first computer .

The processing module is connected to the user interface such that information may be passed between the processing module and the user interface . The processing unit is also configured to receive information via the Internet e.g. from a web server . The processing module is configured to process information received by it.

The user interface may receive inputs from a user of the second computer . A user of the second computer may be a computer programmer website designer software developer etc. The user interface may for example comprise a user input device e.g. a keyboard a mouse etc. and a display.

The functionalities of the processing module and of the user interface are described in more detail below with reference to .

At step s the first web server hosts the web page . In other words the web page is stored by the first web server and made available for access or download via the Internet by one or more client devices.

At step s the first computer accesses or downloads via the Internet the web page . The script including the JavaScript WebCL commands and the image data may be downloaded onto the first computer . This process may comprise a user of the first computer inputting into the first computer a web address for the web page . The first computer may then using the web address retrieve the web page from the first web server .

At step s the web browser of the first computer executes or runs the script of the web page . For example the script may be run in a line by line fashion. The JavaScript module of the web browser may execute or run any JavaScript code in the script . Also the WebCL API may execute or run any WebCL commands .

At step s when or before a WebCL command is encountered in the script the script being run by the web browser may query whether the WebCL language is supported by the web browser . For example it may be queried by the script whether or not the WebCL API has been installed on the web browser is part of the web browser or is in some other way accessible by the web browser .

The querying as to whether or not WebCL is supported by the web browser may be performed by running any appropriate code or script for example 

In this embodiment the WebCL API is installed on the web browser . In other words in this embodiment the WebCL language is supported by the web browser . However in other embodiments WebCL may not be supported and an exception or error may be returned.

At step s after it has been determined that WebCL is supported by the web browser the running of the script by the web browser may query what platform i.e. operating platform i.e. the type of the first computer the web browser is running on. It may also be queried what OpenCL devices i.e. hardware accelerators or other processing devices or modules that may be operated or controlled using the OpenCL programming language are available to the web browser .

The querying as to what platform the WebCL API is running on may be performed by running any appropriate code or script for example 

This method is expressed in the interface description language IDL or web IDL. That is to say the first part of the method WebCLPlatform i.e. an identifier for a platform that WebCL is running on is the object or value that is returned by the method the second part of the method getPlatformIDs is the function name i.e. the function of the method and the third part of the method which is expressed in parentheses and in this case is empty is the parameters used by the function. In other words the function getPlatformIDs will return identifiers for the platform the WebCL API is running on i.e. the first computer .

The querying as to what OpenCL devices are available may be performed using the following method which is expressed using IDL 

In other words the function getDevices may use a parameter that specifies a device type e.g. GPU type etc. to return identifiers for available OpenCL devices. In this embodiment an identifier for each of the GPU and the CPU which are OpenCL devices may be returned.

At step s the GPU or the CPU are selected as the OpenCL device s that are to process some or all of the web page data e.g. data relating to the image .

At step s the running of the script i.e. the Web CL commands by the web browser and the WebCL API creates a WebCL context in or for each of the selected OpenCL devices i.e. the GPU or the CPU . A context may be an execution context in which programs or code may be run. Thus a WebCL context may be a runtime execution context for a WebCL program. A WebCL context may be used to provide a link or to allow communication between the OpenCL device i.e. the GPU and the web browser . Thus a WebCL context may be created for each selected OpenCL device. In other words parallel contexts i.e. contexts that may be used in parallel may be created for multiple OpenCL devices. In other embodiments parallel contexts may be created for a single selected OpenCL device.

The creation of a WebCL context on or for the GPU or the CPU may be performed by running any appropriate code or script for example 

In other words the function createContext may use a parameter that specifies a device type or device to create a context for in order to create a WebCLContext. In this embodiment a WebCL context is created in or for the GPU .

At step s the execution or running of the script is continued. This may comprise when the web browser which may comprise the WebCL API executes or runs a WebCL command the web browser or WebCL API calls a corresponding OpenCL function from the OpenCL library . The OpenCL function or method called when a WebCL command is executed may be the OpenCL function or method for which that particular WebCL command is a JavaScript binding.

The called OpenCL functions may be run or executed within the WebCL context created within the GPU or within the parallel WebCL context created for the CPU . Thus in effect OpenCL code may be run in the context of a WebCL environment within or for the GPU .

Command queues may also be created to facilitate organize or manage the transfer of data from the web browser i.e. from the web browser s memory i.e. the host memory to an OpenCL device memory e.g. the GPU or CPU control execution of programs and kernels synchronize events etc. Code or methods that may be used to create command queues is provided below. A command queue may hold lists of functions etc. that may then be executed in list order .

In this embodiment the script specifies that data corresponding to the image that are to be processed by the GPU . Steps s to s describe how this may be performed.

At step s the running of the script i.e. the Web CL commands by the web browser and the WebCL API creates a WebCL memory object in the WebCL context in the GPU . This WebCL memory object may be or comprise or in some other way specify an amount of memory to be reserved for the image data . The created WebCL memory object may be a buffer within the WebCL context. This buffer may be a buffer for containing general data or a buffer that may be optimized for containing image data e.g. data relating to the image . The WebCL memory object may be a buffer configured to contain e.g. either a JavaScript or untied array or a typed array of data.

In this embodiment the WebCL memory object is a buffer that is configured to contain a typed array of data. Such a WebCL memory object may be provided as follows. The script specifying the WebCL memory object i.e. the buffer may describe its layout e.g. the script may specify that the first value in the buffer is an integer the second value is a float value etc. A data item within a crated buffer may be specified as any appropriate data type for example an integer a Boolean value a character a floating point number an alphanumeric string a vector etc. When the WebCL memory object is created by running the script the WebCL memory object has the specified layout. Thus when the values within the WebCL memory object are set by transferring data from the web browser into the WebCL memory object buffer the data type of each data item within the WebCL memory object is specified.

Thus data types of the values in a C area of memory i.e. GPU memory may be set. Advantageously this setting of the types of the values of a C area of memory tends to facilitate the use of local arguments memory objects and samplers and user defined structures e.g. within OpenCL restrictions . Furthermore a problem that may be caused by the size of an array of values JavaScript is untyped and so numbers are in general 64 bit double tends to be overcome. In particular these 64 bit double numbers may be unsupported by certain devices. This tends to make it impractical to identify the distinction between char int float types etc. without inspecting the code of the kernel. This problem tends to be overcome by setting the data types of an area of memory as described herein.

At step s data i.e. image data are transferred for the web browser into the WebCL memory object within the WebCL context within the GPU .

The transfer of the image data from the web browser i.e. the host memory that may be provided e.g. by a CPU to the memory of the GPU may comprise using one or more command queues to hold a list of commands that may be executed in list order to perform the transfer. Example code or method that may be used to create a command queue is provided below. A write command may be used to write the image data onto the WebCL memory object .

At step s the image data transferred to the WebCL memory object in the GPU are processed by the GPU . By running the script the web browser may run WebCL commands that may call OpenCL functions that may be run in the WebCL context by the GPU to process the image data .

The processing of the image data by the GPU may be managed or performed using one or more command queues. Example code or method that may be used to create a command queue is provided below.

At step s the processed image data i.e. the image data after having been processed by the GPU may be transferred back to the web browser .

The transfer of the image data from the memory of the GPU i.e. the OpenCL device memory to the web browser i.e. the host memory may be managed or performed using one or more command queues. A read command may be used by the web browser to read processed image data from the WebCL memory object .

Some OpenCL methods when implemented to process information return values i.e. processed information e.g. the processed image data as well as information that may be used to identify the one or more memory regions e.g. a memory address for a region of the GPU from which those values are returned. Using a WebCL memory object within a WebCL memory context within the GPU advantageously tends to hide the identity of the memory regions from which data are returned. Thus identifiers for the memory regions tend not to be returned to the web browser . Advantageously this may oppose or prevent a malicious party from using the information that identifies a memory region to access parts of the GPU or other computer memory.

At step s the web page may be displayed by the web browser on the display of the first computer e.g. to a user of the first computer . Displaying the web page may comprise displaying an image that corresponds to or is specified by the processed image data .

In this embodiment in addition to comprising WebCL commands the JavaScript of the web page comprises WebGL commands not shown in the figures . In other words the JavaScript of the web page further comprises commands that have been specified using the WebGL framework. Further information about the WebGL framework or specification may be found for example in WebGL Specification 1.0 which is incorporated herein by reference. Furthermore in this embodiment in addition to comprising the WebCL API the web browser comprises a WebGL API not shown in the figures .

In other words WebGL is supported by the web browser . The WebGL API is a JavaScript API for rendering interactive 3D graphics and 2D graphics. WebGL advantageously allows a GPU accelerated usage of physics and image processing. WebGL may effect a part of a web page canvas. Typically WebGL computer programs comprise control code written in JavaScript and shader code that is executed on a computer s GPU.

Also in this embodiment the GPU in addition to being an OpenCL device is a WebGL device or OpenGL device i.e. a device that may be controlled using functions or methods specified in the WebGL or OpenGL specifications . Further information on OpenGL may be found for example in OpenGL Programming Guide 7th edition which is incorporated herein by reference.

At step s the first computer accesses or downloads via the Internet the web page . The script including the JavaScript WebCL commands and the JavaScript WebGL commands and the image data may be downloaded onto the first computer .

At step s the web browser of the first computer executes or runs the script of the web page . The JavaScript module of the web browser may execute or run any JavaScript code in the script . Also the WebCL API may execute or run any WebCL commands . Also the WebGL API of the web browser may execute or run any WebGL commands.

At step s when or before a WebGL command is encountered in the script the script being run by the web browser may query whether the WebGL language is supported by the web browser . This querying may be performed by running any appropriate code or script or implementing any appropriate WebGL method.

In this embodiment the WebGL API is installed on the web browser . In other words WebGL language is supported by the web browser .

At step s after it has been determined that WebGL is supported by the web browser the running of the script by the web browser may query what WebGL or OpenGL devices i.e. what hardware accelerators or other processing devices or modules that may be operated or controlled using the WebGL or OpenGL programming languages are available to the web browser . This querying may be performed by running any appropriate code or script using any appropriate WebGL method. In this embodiment the GPU is identified as a WebGL or OpenGL device.

At step s the GPU is selected as the WebGL or OpenGL device that is to process some or all of the web page data e.g. is to render the image .

At step s the running of the script i.e. the Web GL commands by the web browser and the WebGL API creates a WebGL context in or for the GPU . A WebGL context may be an execution context in which WebGL or OpenGL programs or code may be run. A WebGL context may be used to provide a link or to allow communication between the GPU and the web browser . The creation of a WebGL context on the GPU may be performed by running any appropriate code or script or by using any appropriate WebGL methods.

At step s when or before a WebCL command is encountered in the script the script being run by the web browser may query whether the WebCL language is supported by the web browser . This querying may be performed as described at step s of above.

At step s after it has been determined that WebCL is supported by the web browser the running of the script by the web browser may query what platform i.e. operating platform i.e. the type of the first computer the web browser is running on. It may also be queried what OpenCL devices i.e. what hardware accelerators or other processing devices or modules that may be operated or controlled using the OpenCL programming language are available to the web browser . This querying may be performed as described at step s of above.

At step s the GPU is selected as the OpenCL device that is to process some or all of the web page data e.g. data relating to the image .

At step s the running of the script i.e. the Web CL commands by the web browser and the WebCL API creates a WebCL context in or for the GPU . The creation of the WebCL context may be as described at step s of above. In other embodiments the WebCL context may be created within the previously selected WebGL context or vice versa . In such a case the WebCL context may be thought of as a sub context.

This running of the script may comprise when the web browser which may comprise the WebCL API executes or runs a WebCL command the web browser or WebCL API calling a corresponding OpenCL function from the OpenCL library . The OpenCL function or method called when a WebCL command is executed may be the OpenCL function or method for which that particular WebCL command is a JavaScript binding. The called OpenCL functions may be run or executed within the WebCL context created within the GPU . Thus in effect OpenCL code may be run in the context of a WebCL environment within or for the GPU .

WebCL command queues may also be created to facilitate organize or manage the transfer of data from the web browser i.e. from the web browser s memory i.e. the host memory to the GPU i.e. the OpenCL device memory control execution of programs and kernels synchronize events etc. Code or methods that may be used to create command queues are provided below.

Also the running of the script may comprise when the web browser which may comprise the WebGL API executes or runs a WebGL command the web browser or WebGL API calling a corresponding OpenGL function e.g. from an OpenGL library that may be part of the WebGL API or accessible by the WebGL API. The called OpenGL functions may be run or executed within the WebGL context created within the GPU .

WebGL command queues may also be create to facilitate organize or manage the transfer of data from the web browser i.e. from the web browser s memory i.e. the host memory to the GPU i.e. the OpenCL device memory control execution of programs and kernels synchronize events etc.

In this embodiment the script specifies that data corresponding to the image are to be processed by the GPU using both WebCL or OpenCL and WebGL or OpenGL methods. For example the script may specify that the image data are to be processed using WebCL or OpenCL by the GPU before being rendered using using WebGL or OpenGL by the GPU . Steps s to s describe how this may be performed.

At step s the running of the script by the web browser creates a memory object in which the image data are to be placed. This memory object may be or comprise or in some other way specify an amount of GPU memory to be reserved for the image data . The created memory object may be a buffer. This buffer may be within both the WebCL context and the WebGL context. In other words the buffer into which the image data are to be transferred is shared between the WebCL context and the WebGL context. Thus this buffer is hereinafter referred to as the shared buffer. 

The shared buffer may be a buffer for containing general data or a buffer that may be optimized for containing image data e.g. data relating to the image . The shared buffer may be a buffer configured to contain e.g. either a JavaScript or untyped array or a typed array of data.

The sharing of the shared buffer may be provided by any appropriate code or methods. In other words the specification of the shared buffer may be provided by any appropriate code or methods. Example code for providing such interoperability between WebCL and WebGL is provided below.

The shared buffer may be configured to contain a typed array of data e.g. as described above for the WebCL memory object .

At step s data i.e. image data are transferred from the web browser into the shared buffer within the GPU . This transfer of data may be managed or performed using one or more command queues. A write command may be used to write the image data into the shared buffer .

At step s the image data transferred to the WebCL memory object in the GPU are processed by the GPU using a WebCL or OpenCL program being executed in the WebCL context . By running the script the web browser may run WebCL commands that may call OpenCL functions that may be run in the WebCL context by the GPU to process the image data .

The processing of the image data by the GPU may be managed or performed using one or more command queues.

At step s the image data processed using programs running in the WebCL context may be rendered by the GPU using a WebGL or OpenGL program being executed in the WebGL context . By running the script the web browser may run WebGL commands that may call OpenGL functions that may be run in the WebGL context by the GPU to render the processed image data in the shared buffer .

The transfer of the image data from the memory of the GPU i.e. the shared buffer to the web browser i.e. the host memory may be managed or performed using one or more command queues. A read command may be used by the web browser to read processed image data from the shared buffer .

At step s the web page may be displayed by the web browser on the display of the first computer e.g. to a user of the first computer . Displaying the web page may comprise displaying a rendered image that corresponds to or is specified by the processed and rendered image data .

A web site developer may use WebCL commands in accordance with or specified by the WebCL framework methods and functions of which are provided below to specify a web page. Advantageously the WebCL framework may support extensions in a similar way to how extensions are supported by the OpenCL framework. Such extensions may also be used to specify a web page. An extension to a framework may relate to a capability e.g. a new capability of a device e.g. the GPU that may be optionally supported but is not a core capability of that framework. An extension to a framework may for example be represented as a class or interface that includes one or more methods or attributes. Extensions to the WebCL framework i.e. WebCL extensions may be specified e.g. by users of the WebCL framework. A WebCL extension may be a general extension to the WebCL framework. Alternatively a WebCL extension may be a proprietary extension that may be useable only by a certain piece of hardware e.g. certain accelerator hardware e.g. a specific CPU or GPU . A WebCL extension may be made available to other users of the WebCL framework for example by storing that extension in a location e.g. the repository that is accessible to other users of the WebCL framework such that those other users may retrieve access or use that WebCL extension .

At step s a user of the second computer inputs an instruction e.g. by typing a command using the user interface into the second computer . This instruction is an instruction to access or download a list of all WebCL extensions that are available in the repository . This may for example be achieved by the user of the second computer inputting into the second computer using the user interface the following command 

At step s the instruction is sent from the second computer e.g. by the processing module to the second web server that hosts the repository .

At step s the second web server receives the instruction and returns to the second computer a list of the WebCL extensions that are available in the repository .

This returned list may for example be displayed to the user of the second computer using the user interface .

At step s the user selects a WebCL extension that he wishes to use in the specification of the web page . Examples of possible WebCL extensions are provided below.

At step s the user of the second computer inputs an instruction e.g. by typing a command using the user interface into the second computer . This instruction is an instruction to access or download the selected WebCL extension from the repository . This may for example be achieved by the user of the second computer inputting into the second computer using the user interface the following command 

where extension name is the name of the WebCL extension that the user of the second computer wishes returned.

At step s the instruction is sent from the second computer e.g. by the processing module to the second web server that hosts the repository .

At step s the second web server receives the instruction and returns to the second computer the selected WebCL extension .

At step s using methods functions parameters etc. specified in the returned WebCL extension the user of the second computer may write the web page . This writing of the web page may further comprise writing one or more WebCL commands using the WebCL framework. This writing of the web page may further comprise writing one or more WebGL commands using the WebGL framework. This writing of the web page may further comprise writing other JavaScript commands or specifying other data e.g. image data for the web page .

At step s the completed i.e. written web page may be uploaded from the second computer onto the first web server . This may be so that the web page may be accessed or downloaded via the Internet e.g. by the first computer as described in more detail above with reference to .

Now described are methods functions etc. that may form the WebCL framework i.e. methods functions etc. that may be used to write WebCL commands . This information will be useful in understanding the above described methods and apparatus.

The WebCL framework may be used for writing web pages web applications or computer programs that may be executed on the web browser or any other device or application that is capable of downloading or accessing data via the Internet .

The WebCL framework provides a set of JavaScript bindings to the Khronos OpenCL framework for heterogeneous parallel computing. The JavaScript bindings to OpenCL may be thought of as wrapper code between the native code i.e. OpenCL and JavaScript code. The JavaScript bindings may allow the native code i.e. OpenCL to be called using JavaScript code and vice versa.

Similarly to the OpenCL framework the WebCL framework comprises a plurality of document object model DOM interfaces. An interface may include one or more methods or one or more attributes that may be used when writing e.g. a WebCL command that forms part of a specification for a web page . Also an instance of an interface is a class or object. Further information on DOM may be found for example in Document Object Model Core The DOMString Type World Wide Web Consortium W3C which is incorporated herein by reference.

In this description methods of the WebCL framework are specified using IDL or web IDL. In other words the first term in the definition of a method or function is the object or value that is returned by the method. The second part of the definition of a method is the function name i.e. the function of the method. The third part of the method which is included in parentheses is the set of parameters used by the function to return the return first term i.e. the return object . For example 

means that using the parameters parameters the function getReturnObject would return an object of the type ReturnObject. The specific object returned would depend on the specific parameters used.

A first interface of the WebCL framework is the WebCLMemory interface. The WebCLMemory interface may derive from i.e. be a JavaScript binding of the ArrayBuffer interface of OpenCL . The WebCLMemory interface may be defined in. as follows 

However in other embodiments this interface may have a different definition or an equivalent definition that is expressed differently.

A further interface of the WebCL framework is the ImageFormat interface. The ImageFormat interface may be an associative array with two keys namely order and data type. The ImageFormat interface may be defined as follows 

A further interface of the WebCL framework is the WebCLMappedRegion interface. Some OpenCL methods when implemented return values as well as information that may be used to identify the one or more memory regions e.g. a memory address from which those values are returned. The WebCLMappedRegion interface of the WebCL framework advantageously tends to hide the identity of the memory regions from which values are returned. Thus identifiers for the memory regions tend not to be returned to an application. Advantageously this may oppose or prevent a malicious party from using the information that identifies a memory region to access parts of the memory of the computer . The WebCLMappedRegion interface may be defined as follows 

A further interface of the WebCL framework is the WebCL interface. The WebCL interface includes JavaScript bindings for the methods for general objects defined in the OpenCL framework. The WebCL interface may be defined as follows 

The following list of methods includes methods that may be included in the WebCL interface and describes uses of those methods. Also in the following list for each parameter of the methods in the WebCL interface a default value is shown.

A further interface of the WebCL framework is the WebCLCommandQueue interface. The WebCLCommandQueue interface includes JavaScript bindings for the OpenCL methods defined in the OpenCL framework that relate to command queues e.g. methods for creating command queues etc. . The WebCLCommandQueue interface may be defined as follows 

In any or all of the methods described herein e.g. the methods in the WebCLCommandQueue interface an array object may for example be an untyped array buffer or a typed array buffer. For small buffers it may be may preferable for an array object to be an untyped array buffer e.g. an ECMAScript array whereas for larger buffers it may be preferable for an array object to be a typed array thereby avoiding a relatively large computational cost of converting data from ECMAScript VM space to native memory space .

The following list of methods includes methods that may be included in the WebCLCommandQueue interface and describes uses of those methods. Also in the following list for each parameter of the methods in the WebCLCommandQueue interface a default value is provided.

This method returns a value for the input int name. The type of value returned is the natural type for the int name as specified in the following table 

The above provided methods of the WebCLCommandQueue interface may be defined or implemented in a different way. For example the WebCLCommandQueue interface may be implemented using associative arrays e.g. as for the ImageFormat interface defined earlier above i.e. as opposed to implementing the WebCLCommandQueue interface as a list of parameters. For example instead of using a long list of arguments as defined in the OpenCL 1.1 specification the following further definition of the WebCLCommandQueue interface use an associative array WebCLRegion to specify an area being read or written within an ArrayBuffer WebCLMemory 

The following list of methods includes methods that may be included in the further WebCLCommandQueue interface and describes uses of those methods. In the following list for each parameter of the methods in the WebCLCommandQueue interface a default value is provided. Also in the following list WebCLRegion specifies a memory region that may be used. This advantageously tends to simplify the number of methods in the WebCLCommandQueue object.

3. WebCLEvent enqueueNDRangeKernel WebCLKernel kernel int offsets 1 . . . 3 int globals 1 . . . 3 int locals 1 . . . 3 WebCLEvent event wait list NULL 

5. WebCLEvent enqueueWriteBuffer WebCLMemory buffer boolean blocking write WebCLRegion array int size WebCLEvent event wait list NULL 

6. WebCLEvent enqueueReadBuffer WebCLMemory buffer boolean blocking read WebCLRegion array int size WebCLEvent event wait list NULL 

7. WebCLEvent enqueueCopyBuffer WebCLRegion src WebCLRegion dst int size WebCLEvent event wait list NULL 

8. WebCLEvent enqueueCopyImageToBuffer WebCLRegion src image WebCLMemory dst buffer WebCLEvent event wait list NULL 

9. WebCLEvent enqueueCopyBufferToImage WebCLMemory src buffer WebCLRegion dst image WebCLEvent event wait list NULL 

10. WebCLMappedRegion enqueueMapBuffer WebCLRegion buffer boolean blocking map int map flags WebCLEvent event wait list NULL 

11. WebCLEvent enqueueUnmapMemObject WebCLMemory memory WebCLMappedRegion mapped region WebCLEvent event wait list NULL 

This method may be used to release OpenCL memory objects that have been created from WebGL objects. These objects may be released before they can be used by OpenGL.

A further interface of the WebCL framework is the WebCLContext interface. The WebCLContext interface includes JavaScript bindings for the OpenCL methods relating to contexts e.g. methods for creating contexts etc . The WebCLContext interface may be defined as follows 

The following list of methods includes methods that may be included in the WebCLContext interface and describes uses of those methods. Also in the following list for each parameter of the methods in the WebCLContext interface a default value is provided.

Properties of this method may be as defined in the OpenCL framework. This method is used to create a WebCL context e.g. the WebCL context .

This method may return a value for int name. The type of value returned is the natural type for the requested int name as specified in the following table 

A further interface of the WebCL framework is the WebCLDevice interface. The WebCLDevice interface includes JavaScript bindings for the OpenCL methods relating to device objects e.g. querying what WebCL or OpenCL devices are available etc . The WebCLDevice interface may be defined as follows 

The following list of methods includes methods that may be included in the WebCLDevice interface and describes uses of those methods. Also in the following list for each parameter of the methods in the WebCLDevice interface a default value is provided.

This method may return the value for the int name. The type of value returned is the natural type for the requested int name as specified in the following table 

A further interface of the WebCL framework is the WebCLEvent interface. The WebCLEvent interface includes JavaScript bindings for the OpenCL methods relating to Event objects. Furthermore the WebCLEvent interface includes JavaScript bindings for the methods for UserEvent objects defined in the OpenCL framework. The WebCLEvent interface may be defined as follows 

The following list of methods includes methods that may be included in the WebCLEvent interface and describes uses of those methods. Also in the following list for each parameter of the methods in the WebCLEvent interface a default value is provided.

This method may return the value for the passed int name. The type of value returned is the natural type for the requested int name as specified in the following table 

A further interface of the WebCL framework is the WebCLKernel interface. The WebCLKernel interface includes JavaScript bindings for the OpenCL methods related to Kernel objects. The WebCLKernel interface may be defined as follows 

The following list of methods includes methods that may be included in the WebCLKernel interface and describes uses of those methods. Also in the following list for each parameter of the methods in the WebCLKernel interface a default value is provided.

This method may return the value for the passed int name. The type of value returned is the natural type for the requested int name as specified in the following table 

A further interface of the WebCL framework is the WebCLMemory interface. The WebCLMemory interface includes JavaScript bindings for the methods related to memory objects defined in the OpenCL framework e.g. methods for creating memory objects etc. . As described in more detail above when using the WebCL framework a memory object e.g. the WebCL memory object may be a typed array. Further information on Typed Arrays may be found for example in Typed Array Specification Editor s Draft July 2012 which is incorporated herein by reference. The WebCLMemory interface may be defined as follows 

The following list of methods includes methods that may be included in the WebCLMemory interface and describes uses of those methods. Also in the following list for each parameter of the methods in the WebCLMemory interface a default value is provided.

This method may return the value for int name. The type of value returned is the natural type for the requested int name as specified in the following table 

A further interface of the WebCL framework is the WebCLPlatform interface. The WebCLPlatform interface includes JavaScript bindings for the OpenCL methods relating to platform objects e.g. querying what platform or platform type the script is being run on . The WebCLPlatform interface may be defined as follows 

The following list of methods includes methods that may be included in the WebCLPlatform interface and describes uses of those methods. Also in the following list for each parameter of the methods in the WebCLPlatform interface a default value is provided.

This method may return the value for int name. The type of value returned is the natural type for the requested int name as specified in the following table 

A further interface of the WebCL framework is the WebCLProgram interface. The WebCLProgram interface includes JavaScript bindings for the OpenCL methods relating to Program objects. The WebCLProgram interface may be defined as follows 

The following list of methods includes methods that may be included in the WebCLProgram interface and describes uses of those methods. Also in the following list for each parameter of the methods in the WebCLProgram interface a default value is provided.

This method may return the value for int name. The type of value returned is the natural type for the requested int name as specified in the following table 

A further interface of the WebCL framework is the WebCLSampler interface. The WebCLSampler interface includes JavaScript bindings for the OpenCL methods for Sampler objects. The WebCLSampler interface may be defined as follows 

The following list of methods includes methods that may be included in the WebCLSampler interface and describes uses of those methods. Also in the following list for each parameter of the methods in the WebCLSampler interface a default value is provided.

This method may return the value for int name. The type of value returned is the natural type for the requested int name as specified in the following table 

The WebCL framework may include a plurality of constant values or constants. In some embodiments the constants of the WebCL framework may be the same as those defined in the OpenCL framework including optional extensions . However in other embodiments one or more of the constants of the WebCL framework may be different from defined in the OpenCL framework. For completeness the constants of the WebCL framework in this embodiment are as follows 

As described above the WebCL framework advantageously may support and be used with WebCL extensions .

A first example WebCL extension consider the cl gl sharing extension. The cl gl sharing extension is an extension that may provide that WebCL methods may use e.g. as their argument objects of the WebGL framework. This extension may also provide that WebGL methods may use e.g. as their argument objects of the WebCL framework.

The cl gl sharing extension advantageously tends to provide that buffers e.g. the shared buffer may be shared between WebCL and WebGL contexts. The cl gl sharing extension may comprise a plurality of methods and may be defined as follows 

In other embodiments one or more of the methods included in the cl gl sharing extension and described above may be omitted. Also in other embodiments the cl gl sharing extension may comprise one or more different methods instead of or in addition to one or more of the methods included in the cl gl sharing extension and described above. Thus the cl gl sharing extension may be defined in a different way for example as follows 

The following list of methods includes methods that may be included in the cl gl sharing extension and describes uses of those methods. Also in the following list for each parameter of the methods in the cl gl sharing extension a default value is provided.

2. WebCLMemoryObject createFromGLTexture2D WebCLContext context CLenum flags GLenum target GLint miplevel GLuint texture 

3. WebCLMemoryObject createFromGLTexture3D WebCLContext context CLenum flags GLenum target GLint miplevel GLuint texture 

4. WebCLMemoryObject createFromGLRenderbuffer WebCLContext context CLenum flags WebGLRenderBuffer renderbuffer 

This method may return information about the WebGL object used to create a WebCL memory object. The WebGLObjectInfo may be a dictionary defined as follows 

The cl gl sharing extension may be used to link together WebGL and WebCL. In particular the cl gl sharing extension tends to provide that buffers may be shared between WebCL and WebGL contexts i.e. values in a buffer may be processed by a program running in a WebCL context and a program running in a WebGL context .

A second example WebCL extension is the WebCLGLSync extension. This extension allows creation of OpenCL event objects linked to OpenGL fence sync objects. Advantageously this tends to improve efficiency of sharing images and buffers between the WebCL and WebGL contexts. The WebCLGLSync extension may comprise a plurality of methods and may be defined as follows 

Further example extensions to the WebCL framework include WebCL compiler extensions. These extensions do not provide new JavaScript methods and constants. Instead these extensions may be used to indicate support in an OpenCL C compiler for features a developer may use e.g. for enhancing kernel code. For example if a WebCLDevice.getExtension extension name command returns a non null object support for that extension name is indicated. The WebCL compiler extensions may be defined as follows 

The following list of methods includes methods that may be included in this definition of the WebCLCommandQueue interface.

1. ArrayBuffer enqueueMapMemObject WebCLRegion buffer CLboolean blocking map CLenum map flags optional WebCLEvent event wait list optional CLboolean generate event false 

In some embodiments WebCLBuffer and WebCLImage may be WebCL Memory Objects. This tends to provide mapping of device memory regions onto the host memory. In one embodiment WebCLRegion is a dictionary defining the origin and size of the region of the memory object to be mapped. 2. WebCLCommandQueue enqueueUnmapMemObject WebCLMemoryObject memory ArrayBuffer mapped region optional WebCLEvent event wait list This method may unmap a previously mapped region with enqueueMapMemObject . Maped region is an ArrayBuffer returned by enqueueMapMemObject.

In the above described WebCL framework setting the arguments of a kernel typically would use knowledge of a C structure used as arguments in a kernel method. However since JavaScript is untyped it tends to be difficult or impossible to uniquely map JavaScript types to native C types.

The above described WebCL framework comprises the method WebCLKernel.setArg CLuint index any value optional CLtype type . This method advantageously tends to allow any value to be passed to an OpenCL kernel. This method tends to be particularly suitable for basic scalar and vector types.

An example extension to the WebCL framework that may be used to set data types in a C area of memory is the ctypes extension. The ctypes extension may be defined as follows 

The following list of methods includes methods that may be included in the ctypes extension and describes uses of those methods. Also in the following list for each parameter of the methods in the ctypes extension a default value is provided.

This method compiles a ctypes struct definition into an ArrayBuffer. The ctypes struct is a dictionary of fields in the C structure. Fields may be defined in the same order as they are in the C struct defined in the kernel method e.g. as follows 

An example code specifying an example method of setting the values of a C area of memory and to computing its size is as follows 

Now is an example of a script that may be used to perform a task of adding together two vectors. The example script is as follows 

The WebCL specification advantageously provides additional computing context objects for the HTML5 specification. These content objects tend to allow computing using an application programming interface that conforms closely to the OpenCL API .

An advantage provided by the above described WebCL specification methods and systems is that increased security tends to be provided. Some OpenCL methods when implemented return information that may be used to identify the one or more memory regions e.g. a memory address of a computer. A malicious party may use this information to access parts of the computer memory. The above described WebCL framework advantageously tends not to return i.e. hides this memory address information. Thus the above described WebCL framework tends to provide a higher level of security than e.g. the OpenCL framework.

The above described WebCL specification tends to allow for a JavaScript API design that is familiar to many computer programmers.

The above described WebCL specification tends to have fewer methods than other frameworks e.g. the OpenCL . Method overloading has advantageously been exploited to provide this. The WebCL specification provides an object oriented representation of OpenCL that tends to be relatively simple compared to OpenCL .

An advantage provided by the above described WebCL specification methods and systems is that a method that creates an object is attached to the object that creates it. This is instead of that method being a constructor of the created object. For example if a first WebCL object calls a for example create platform method a WebCL Platform Object is returned. The first WebCL object is a parent of the WebCL Platform Object i.e. the WebCL Platform Object is a child of the first WebCL object. The parent and child objects are linked. For example if a parent objects is deleted its children are automatically deleted. This is advantageous for example during memory reclamation. This is in contrast to for example the OpenCL framework.

In the above described WebCL framework exceptions are used instead of error codes. If an exception is returned or thrown then an argument of the exception may contain details of the corresponding OpenCL error. This use of exceptions as opposed to error messages advantageously tends to avoid a cascade of run time errors. Thus by using exceptions lock down e.g. of the GPU may be avoided.

Conveniently the constants used by the above described WebCL framework are those of the OpenCL framework.

In the above described WebCL framework OpenCL Event and UserEvent classes are advantageously merged into a single class namely the WebCLEvent class. Thus in JavaScript only a single Event Object is used. For a software developer this tends to simplify the process of creating a computer program.

A method by which the above described WebCL framework may be extended is advantageously provided. For example extensions that allow WebCL and WebGL to interoperate are advantageously provided. These extensions advantageously tend to facilitate rendering of GPU accelerated buffers from OpenCL using OpenGL standards. This tends to avoiding information transfer from the GPU to the CPU. Further extensions to the WebCL framework tend to provide JavaScript representations of OpenCL extensions for compiler features available in a GPU. This beneficially tends to allow a software developer to select the best kernel for various applications.

The above described WebCL framework advantageously tends to enable web applications to harness GPU and multi core CPU parallel processing e.g. from within a web browser. This tends to enable significant acceleration of applications such as image and video processing and advanced physics e.g. for WebGL games. Furthermore the WebCL framework tends to extend the capabilities of e.g. an HTML 5 web browser to accelerate computationally intensive and rich visual computing applications.

In the above embodiments running the script which in the above embodiments is JavaScript but may be a different type of script by the machine processor which in the above embodiments is a JavaScript module but may be a different type of machine processor creates a context for an underlying processing unit e.g. the GPU . Also in the above embodiments running the script by the machine processor creates a memory object or buffer within the created context. However in other embodiments running the script by the machine processor may implement different types of objects within a created context or may implement different types of functions within the created context. This may be instead of or in addition to creating the memory object or buffer within the context. Also in other embodiments running the script by the machine processor may create a memory object or buffer that is not within a created context.

In view of the many possible embodiments to which the principles of the present discussion may be applied it should be recognized that the embodiments described herein with respect to the drawing figures are meant to be illustrative only and should not be taken as limiting the scope of the claims. Therefore the techniques as described herein contemplate all such embodiments as may come within the scope of the following claims and equivalents thereof.

