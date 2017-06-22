---

title: Method for protecting an application program and related computer program product
abstract: A Method for protecting an application program executable on a computer against reverse engineering, said application is created to run with at least one selected dynamic link library (DLL) on said computer, comprises the steps of: adding a specific library loader to the executable application program, said loader either contains or has access to said dynamic link library; setting modified references to said dynamic link library such that upon loading said application program and said loader into the main memory of said computer, said dynamic link library is initialized by said library loader instead of the operating system; The library loader and the pseudo-statically linked library could be embedded into the application program, thereby using unused space within the application. The protected application presents itself as a monolithic application without the vulnerable interface to a DLL.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09355229&OS=09355229&RS=09355229
owner: WIBU-Systems AG
number: 09355229
owner_city: Karlsruhe
owner_country: DE
publication_date: 20120113
---
This application a national phase application of PCT EP2012 050489 filed Jan. 13 2012 claims priority to European Application No. 11150910.5 filed Jan. 14 2011.

The invention relates to protecting an application program executable on a computer against reverse engineering.

Current application programs usually not only use code specially crafted for this application but also some generic code that is to be re used for a plurality of applications. Such code is called a library. Common uses for libraries are on one hand system specific application programming interfaces APIs such as drawing on a screen sound output or writing files to disk. There also exist a number of libraries that are provided either commercially or free of charge to perform special frequently used functionality. For example this could be an interface to a database system a cryptographic library performing some encryption task or a library used for accessing special hardware.

Libraries can be provided to the programmers and user in different form. These different forms have different properties with different advantages and drawbacks. On different platform the different types of libraries have slightly different properties but the basic concepts remain the same across all platforms. In the following the naming for a windows platform is used as these names are the most commonly used names.

The simplest form to distribute code is in form of source code. Here the library developer distributes the whole source code of the library to application developers. This has some advantages 

1. The application developer has access to the complete library and it is easier for him to find errors in his own application or in the library.

3. The application can be a single file and there is no separate file that is added to the application by using the library.

4. The application is well protected against reverse engineering as the APIs are not visible outside the application.

5. Only the necessary code enters the application. Code that is not necessary will not enhance the size of the application.

2. The implementation will probably work only with one specific programming language compiler and version. For different languages compilers or versions there has to be different source code.

4. If multiple applications use the same library it requires more disk space as each application has its own copy of the library already build in.

A static link library SLL is provided as the output of the compiler and can be used in generating a complete executable. In contrast to a source code library it is not possible to see every detail of the implementation or to easily make changes or corrections to the existing library code.

2. The application can be a single file and there is no separate file that is added to the application by using the library.

3. The application is well protected against reverse engineering as the APIs are not visible outside the application.

4. Only the necessary code enters the application. Code that is not necessary will not enhance the size of the application.

2. The application developer has no access to the complete library. It is not easy for him to find errors in the library.

3. The implementation will probably work only with one specific programming language compiler and version. For different languages compilers or versions there have to be different libraries.

5. If multiple applications use the same library it requires more disk space as each application has its own copy of the library already build in.

To counter the drawbacks of having multiple instances of a library and having to rebuild the application each time the library is updated the concept of shared libraries has been developed. In current operating systems most of the systems core functionality is stored inside such dynamic libraries. Under Windows these are called Dynamic Link Libraries DLLs under Linux these are Shared Objects SOs and on MacOS these are Shared Objects or Frameworks. For simplicity hereafter the terms dynamic link library or DLL will mark any shared dynamic libraries irrespective of the operating system they are crafted for.

Many application programs today split the functionality across several dynamic libraries to make the development process easier due to several separate modules with defined functionality. Dynamic link libraries are a way of getting independent of the current development environment as most development systems provide an interface to the system and third party provided dynamic link libraries.

4. If multiple applications use the same library it is used as a shared resource and conservers some memory.

3. The application is not protected against reverse engineering as the APIs are visible to the outside and can be easily redirected or intercepted.

5. The application developer has no access to the complete library. It is not easy for him to find errors in the library.

Summarized the two models used widely are static link libraries SLL and dynamic link libraries DLL . From a development point of view a dynamic library has great advantages over source code libraries and a static library as it is mostly independent of the used compiler and will work together with unusual development environments.

However from a viewpoint of protection of intellectual property and prevention of reverse engineering a dynamic link library has clear advantages as there are no openly documented and accessible interfaces available.

The update property of a static link library can be seen in both directions as on one hand a fix is easier with a dynamic library and on the other hand it is possible that a fix introduces new problems as the software is now running with a library version it has not been designed for and that has never been tested.

The object of the invention is to protect an application program which is created to run with one ore more dynamic link libraries provided by the operating system against reverse engineering thereby avoiding the disadvantages connected with the use of static libraries.

This object is achieved by the method with the method steps of the characterizing part of claim . The object is also achieved by the computer program product with the features defined in claim . The object of the invention is also achieved by the method according to claim .

The invention is intended to be a crossover between the concepts of static link libraries and dynamic link libraries. It tries to build on the advantages of both architectures. The resulting development is on one hand independent of the used development environment. On the other hand the invention avoids the reverse engineering problem of openly accessible interfaces in dynamic link libraries. Hence the invention builds a bridge between two different development paradigms the paradigm of static libraries and the paradigm of dynamic link libraries.

The development of the application program itself is done using an ordinary dynamic link library DLL . After the usual development process is completed the compiled project is converted to use the DLL like a static library or to link it pseudo statically .

The method according to the invention is therefore suitable to provide for all development environments a library implementation with a security that is near to the security of statically linked applications while at the same time offering the developer and the end user the convenience of not having to install additional libraries.

6. A software module Preparer that prepares the application to co operate with the loader whereby such preparer will integrate the loader into the application in some cases.

7. A build process converting the dynamic link library or libraries for use with the Loader or for integration of the dynamic library into the Loader.

On an operating system OS level a DLL is used by specifying the used application programming interfaces APIs inside the application. On application start the operating system will scan the application file for these references will load the DLL and will set references to the necessary APIs inside the application. Likewise a DLL itself can also contain references to other DLLs.

The invention now removes the references to the dynamic library and introduces additional code into the application. The additional code comprise a special Loader which either contains or has access to the DLL to be linked and as a startup code sets the references to the used APIs in the correct places of the application. If additional modules or shared libraries in the same process space try to access the shared DLL that is now linked in pseudo statically the loader may also redirect these references into the pseudo statical linked library.

The simplest way to redirect the call to the DLL is to replicate the standard mechanism used by the OS to reference DLLs. On most modules this list can be continuous as it is usually under Windows or it can be split up into several parts or even be distributed as single values across the executable. For a DLL the OS fills into this list the addresses of the API functions. In the pseudo static case the part of the list referring to the pseudostatic list is filled not by the operating system but by the special loader himself. The procedure take only minimal influence on the way the executable is loaded and is on most platforms easy to implement.

Another method for integration the DLL pseudo statically would be not to simply replace the list as maintained by the operating system but to modify the call that references the table entry. To do this at least part of the executable has to be disassembled and analyzed. The knowledge where the API list is helps greatly in finding the relevant parts of the executable. This method is not as easily employed as but will usually work well and will provide a higher level of protection against reverse engineering.

In addition to the call replacement it is possible to analyze the code further and to do more modifications than simply replace a call. Using such replacements it is possible to extend the protection level significantly as here software obfuscation methods can be integrated into the executable.

To make the pseudo statical link library available not only to one module e.g. the executable program but to other modules e.g. dynamic libraries in the process space as well it is necessary to modify the dynamic loading mechanism of the operating system itself. This can be achieved by the same mechanisms described earlier especially by the method wherein the standard mechanism used by the OS is replicated in order to redirect the call to the used DLL. With this method it is possible to redirect operating system functionality to a different implementation with a different functionality. Using this initial redirection mechanism it is possible to redirect the functions in subsequently loaded modules to the DLL.

As an example in the operating system Windows it is necessary to redirect calls such as LoadLibray GetProcAddess. In Linux the calls would be dlopen and dlsym.

Most operating systems do not regard executables as one solid block but have a distinction into several blocks called sections or segments. Hereafter it will only be referred to sections regardless if a single OS has another terminology. In the executable there is a table directing the OS what sections are present in the executable and what exactly to do with this different sections. Depending on the OS a section containing executable code might be treated differently from a section containing data. If the section table is modified correctly it will contain one or more additional sections. These additional sections can be used to store the loader and the DLL as part of the executable. The executable also contains a description what code to start on loading the program. If this is modified correctly the OS can be forced not load the initial code of the executable but instead to call the startup code of the loader. The loader is than responsible to transfer the control to the original startup code after it has finished its own initialization.

Alternatively the loader could be placed as appendix to the executable application program. If the developer of the executable follows certain instructions he can leave some unused space inside the executable that is large enough to take the loader and or the DLL. The instructions for creating such a gap in the executable are not general but have to be tailored to the used development language compiler and specific compiler version. For some development environments it might even be impossible to create gaps large enough to hold the loader. Identification of the gaps can be made in different ways. The developer might obtain the correct address directly from his development environment or external links like exported symbols might be used or the gap can be identified using a magic number or special internal data structure. But independent of the method used to identify the gap the usage is the same. The method used to find the gap may also be removed from the executable after the gap has been utilized. So an analyst will have it harder to identify the gap and the DLL stored inside.

As a third option it is also conceivable to place the loader not internal to the executable itself but as an external dynamic link library. In this case the executable is modified that it does no longer reference the DLL as dynamic library but instead reference the loader as dynamic link library. So the OS will load and initialize the loader which in turn will fix the references to the DLL inside the executable and if required inside the other DLLs.

The overall process for converting the executable application program into an executable which is protected against reverse engineering is split up into two parts 

The library to be linked pseudo statically is at the beginning a dynamic link library that has been used to develop the application. In this step the DLL is either converted into a pseudo static link library or is completely rebuilt as a pseudo static library. A complete rebuild of the library to convert to a pseudo static library is no real problem here as this library is only built once and should be deployed into several applications.

The preparation of the application is the mechanism by which the compiled executable application is changed so that it either incorporates the special loader itself or is prepared to co operate with the loader. Preparing the application will usually result in the loader being a part of the application but it is also conceivable that the loader is attached as a dynamic link library to the application.

The original application would be loaded by the operating system. Than the dynamic link libraries would be loaded by the OS and the references from the application to the DLLs would be set.

After conversion the application is loaded and most dynamic references are resolved. Only the dynamic link library that has been converted into a pseudo static link library is not loaded. Instead the loader either dynamically creates the references or the references have already been made in the preparation phase. Additionally the loader may take care of other modules in the process room e.g. other shared libraries that also make use of the now pseudo statically linked library. Here the loader has to act as part of the operating system providing the shared libraries with the corrected references to the DLL.

US 2006 070053 A1 describes a system wherein a runtime environment is not capable of loading DLLs. Instead the environment is designed to accept only applications that are linked using static libraries. In this case a change in a library requires a complete new build of the application. To circumvent this a dynamic loader is integrated into the application that is capable to load DLLs at runtime. Moreover this system is designed to specially use a special format for libraries and executables. Within the ELF format there is no real difference between a static and a dynamic library. Consequently for both purposes the same libraries are utilized. Effectively the system according to US 2006 070053 A1 implements a loader for DLLs and has no means to statically bind a dynamically designed library.

Given a complex application program from some vendor. The vendor wants to protect the intellectual property contained in the development of his application. He decides to protect the application using cryptographic measures and a hardware dongle. The dongle provider can offer some protection using encryption tools but the vendor wants to archive more protection and decides to call some encryption routines provided by the dongle provider from inside his own code.

As the vendor used i.e. an old version of Fortran to create his application there is no direct support for him using a static link library from the dongle provider. So he is would be forced to use a dynamic link library DLL instead with the consequence that a hacker could now easily introduce a modified DLL into the system which is used to intercept and record the encryption calls made by the vendors software. The hacker would be able to record the requests and the answers and would therefore be able to replay the correct answers without using the dongle at all.

To counter this threat the vendor uses a pseudo static linking implementation provided by the dongle provider.

At first the vendor develops and tests his application using a dynamic link library which provides the needed encryption functions. The usual mechanism when starting the application is shown in . The original application would be loaded by the operating system OS . Than the used dynamic link library DLL would be loaded and the references to the necessary Application Programming Interfaces API would be set by the OS.

After successful tests the vendor protects the application using a tool provided by the dongle provider. This tool modifies the executable and besides encrypting it removes the references to the needed DLL containing the encryption functions. Instead the tool imbeds a modified version of the DLL into the application itself.

As shown in a specific library loader and the used DLL are attached to or embedded into the executable application thereby using unused space within the application. The loading feature of the operating system is not modified. Instead a modified specific version of the operating system s library loader is used to load the DLL. Upon starting the application the specific LOADER initializes the DLL by calling the initialization code INIT of the DLL. The part of the list of references referring to the used DLL is now filled by the LOADER instead of the OS. To this end the loader code that is normally part of the operating system has to be evaluated by the specific loader code added to the application program. This results in a statically attachment of the used DLL which became now a pseudo static link library. When the program is compiled the attached library is a dynamic type library DLL but at runtime from an operating system point of view it looks like a static link library. It is now something between we call it a pseudo static link library or PLL.

The linked DLL itself also has references to other DLLs at least to some calls to the operating system. If the DLL would merely be added to the program without loader code the proper usage of the DLL would not be given. Also the DLL itself has code that has to be invoked to initialize the DLL. When the DLL would simply be added to the executable this necessary initialization code would never be called.

An alternative method for integration the used DLL is not simply replace the list of references as maintained by the OS but to modify the call that references the table entry. In the additional code introduced into the application causes direct calls of the used DLL which now is a pseudo static link library PLL . The LOADER only calls the initialization code INIT of the DLL.

To a hacker the application now presents itself as a monolithic application without the vulnerable interface to a DLL. To the developer however the application uses a simple DLL interface. For the dongle provider the customer uses a secure integration without the dongle provider having the necessity to provide static link libraries for all possible development environments.

