---

title: On-demand loading of types of software code of a program executing on a computing device
abstract: A first computing device receives (over a network) from at least a second computing device a container that includes information relating to types of software code that are potentially invoked by a program executing on the first computing device. A determination is made according to an on-demand basis, during execution of the program, whether a particular type of software code is to be loaded from the at least second computing device to the first computing device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08806468&OS=08806468&RS=08806468
owner: Microsoft Corporation
number: 08806468
owner_city: Redmond
owner_country: US
publication_date: 20120114
---
This application is a continuation of and claims priority to U.S. patent application Ser. No. 11 974 816 filed Oct. 16 2007 and entitled ON DEMAND LOADING OF TYPES OF SOFTWARE CODE OF A PROGRAM EXECUTING ON A COMPUTING DEVICE issued as U.S. Pat. No. 8 127 284 on Feb. 28 2012. The disclosure of the above identified application is hereby incorporated by reference in its entirety as if set forth herein in full.

In a distributed computing environment software on a first computing device is often loaded onto a second computing device for execution on the second computing device. A typical scenario is when a client computer downloads software from a server computer over a network for execution on the client computer. This can often come up in the context of a web based environment in which a user at the client computer accesses a web page on the server computer and interaction between the client computer and the server computer causes execution of software programs on the client computer.

A client computer can have a relatively limited amount of resources e.g. storage resources and or processing resources . For example the client computer can be a mobile device such as a personal digital assistant a mobile telephone and the like. Alternatively the network between the client computer and the server computer may be a relatively low bandwidth network. In the above scenarios downloading relatively large amounts of software code some of which may not be needed onto the client computer may be inefficient since overloading of the client computer may occur or network bandwidth may be unnecessarily consumed.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used to limit the scope of the claimed subject matter.

In general according to some embodiments software code of a program executing on a first computing device is loaded from a second computing device according to an on demand basis. A container that includes information relating to types of software code is provided to the first computing device to enable the on demand loading of types of software code to the first computing device.

Other or alternative features will become apparent from the following description from the drawings and from the claims.

In the ensuing discussion reference is made to the client computers and server computer however it is contemplated that the described techniques are applicable to other types of computing devices.

As depicted in the example of a program is executable in the client computer . The program may be a program that is invoked from another program in the client computer such as a web browser not shown . In one specific example the server computer may provide a website that a user at the client computer can visit. A web page can be downloaded from the server computer to the client computer . The web page can provide interactive features through which one or more programs can be invoked. Examples of such programs include JavaScript programs Rich client programs and so forth.

During execution of the program in the client computer various pieces of code are loaded. For example such pieces of a code can be software methods or more simply methods that are loaded to perform predefined tasks. A method refers to any software routine or sequence of code to perform some action s . If the client computer has limited resources e.g. limited storage and or processing resources or if it is desirable to reduce bandwidth consumption of the network then improved efficiency can be achieved by preventing the loading of pieces of code that the program does not need.

In accordance with some embodiments the loading of pieces of software code into the client computer from the server computer can be performed on a type by type basis. As used herein a type is a set of software routines e.g. software methods and their encapsulated states . In some implementations the set of methods of a particular type are relatively highly dependent on each other as a result it makes sense to load the methods of a set together into the client computer .

Types are loaded into the client computer according to an on demand basis during execution of the program . Loading of a type of software code according to an on demand basis refers to loading the type when an executing program invokes or is about to invoke one or more methods in the type. As a particular type is needed by the program during execution in the client computer the particular type is loaded from the server computer to the client computer .

The loading of the various types of methods according to the on demand basis is transparent to the program . In other words the program asks for a particular type regardless of whether the type is already loaded in the client computer for example the program would not need to first determine whether the type is already loaded in the client computer before requesting that the type be loaded.

To enable the on demand loading of types of software code according to some embodiments a client side code loading system and server side code loading system are provided in the client computer and server computer respectively. The client side code loading system includes a loader to perform loading of software code. In response to a request for a particular type of software code from the program the loader will determine if an instance of the particular type was previously loaded. If so that instance is returned. However if the particular type was not previously loaded then the type will be loaded from the server computer as described further below .

Although reference is made to loading software code from the server computer to the client computer it is noted that certain pieces of software code may in fact be loaded from a different computer such as the client computer . Obtaining software code from another client computer provides a peer to peer software loading feature in which a client computer can load pieces of software code from another client computer rather than from a server computer. This may alleviate bottleneck issues if there are multiple client computers all trying to download code from one or a small number of server computer s . In fact different types of software code can be loaded from different computers which can improve throughput.

Another feature of transporting types of code from the server computer to the client computer is that a superset of types can be returned in response to a request for a particular type where the superset of types includes more types than the requested type. To enable this a process in the client computer does not have to wait for a return value in response to a request for a type. As a result multiple types can be transported together. For example in response to a request for type X from client computer the server computer can return type X along with other types e.g. types Y and Z in a superset of X Y and Z. Thus generally in response to a request for a particular type the server computer can deliver the requested type as well as one or more other types if desired.

In accordance with some embodiments the loader is not bound to any specific transport mechanism for loading types of code from the server computer to the client computer . A pluggable loading transport mechanism can be plugged into the client side code loading system where the transport mechanism can be any native transport mechanism associated with a particular environment. By being able to work with a pluggable transport mechanism the client side code loading system can be used with any type of platform even on proprietary platforms. Examples of transport mechanisms include the following 1 XMLHTTPREQUEST which is an API application programming interface that can be used by Javascript or other scripting languages to transfer XML and other text data to and from a server using a Hypertext Transfer Protocol HTTP mechanism 2 a transport mechanism based on script blocks 3 a transport mechanism that is based on reading a file from a file system and so forth.

In accordance with some embodiments to enable the on demand code loading system in the client computer to perform on demand transport of types of code from the server computer to the client computer containers are provided from the server computer to the client computer . The containers hold information to enable the client side code loading system to deduce types of code that may be needed by the program . The containers can refer to each other.

Each container includes information relating to types of software code that may potentially be invoked by the program and thus may have to be transported to the client computer . A specific example of a container is an assembly where an assembly is a partially compiled code library. Specifically an assembly can be a .NET assembly which is according to Microsoft s .NET framework that provides pre coded solutions to various program features such as user interface data access database connectivity web application development network communications and so forth. .NET assemblies written for the .NET framework can be executed in various runtime environments.

Although the ensuing discussion refers to assemblies it is noted that in different implementations other types of containers can be employed.

Initially the assemblies loaded into the client computer include empty data structures that are to be filled lazily with information relating to types of software code according to an on demand basis. An assembly that has empty data structures is also referred to as an assembly placeholder. Note that reference to an assembly in the ensuing discussion can refer to either a fully loaded assembly or an assembly placeholder. The assemblies can be loaded in a local memory of the client computer such as a local cache that is implemented as part of the storage of the client computer where the storage can be implemented with storage devices such as semiconductor storage devices magnetic disk or optical disk storage devices and so forth.

The client side code loading system also provides one or more application programming interfaces APIs containing various API routines that can be invoked to perform tasks associated with the client side code loading system . Examples of various API routines are discussed throughout this description.

The client side code loading system and program are executable on one or more central processing units CPUs in the client computer . The one or more CPUs are connected to the cache as well as to a network interface to enable the client computer to communicate over the network such as with the server computer .

The server computer includes a storage that is connected to one or more CPUs . The server computer includes a server side code loading system that is executable on the one or more CPUs . The server side code loading system is able to process requests from the client side code loading system and to provide appropriate responses to such requests. Also in one embodiment the server side code loading system is able to determine what other types if any are to be transported to the client computer in response to a request for a particular type.

As depicted in the storage of the server computer includes various assemblies that contain code that may be invoked by the program during execution of the program at the client computer .

The server side code loading system includes a compiler that is able to compile each of the assemblies depicted in the storage into a corresponding assembly placeholder which can be in the form of a JavaScript file for example . Compiling the assemblies into assembly placeholders allows for the assembly placeholders to be initially transported to the client computer without having to transport the entire assemblies which would involve having to transport all code associated with the assemblies initially . Instead according to some embodiments after initial loading of the assembly placeholders to the client computer types of software code can be loaded according to an on demand basis.

An example arrangement of assemblies is depicted in . The arrangement includes a root assembly which includes first information that refers to types of code and second information that refers to other assemblies . The assembly can in turn refer to another assembly and the assembly can refer to the assembly .

The first information can be in the form of one or more data structures e.g. a form of containers that are initially empty. The initially empty data structures can be filled with information later on as types are loaded into the client computer . The second information contains references to other assemblies. As the program is executed the program can invoke various methods including methods of a type of software code that has not been loaded on the client computer. Such invocation of the methods can in turn trigger the loading of types to the client computer . As a result the initially empty data structures that can contain type information in the various assemblies are filled with information regarding types that have been loaded.

A general flow for program execution in the client computer is depicted in . Initially an entry assembly which is the assembly that provides the entry into the program is loaded at from the server computer to the client computer where loading of the entry assembly refers to initially loading the assembly placeholder of the entry assembly into the client computer . Loading is accomplished by the program invoking the loader which in turn invokes the pluggable transport mechanism to load the requested code. In one implementation the entry assembly which can be .NET code in one example is compiled at the server computer into the assembly placeholder .

The assembly placeholder for the entry assembly initially contains empty data structures to store one or more types associated with the entry assembly. In one example it is assumed that the entry assembly is associated with an entry type of code associated with entry methods. To continue execution of the program the client side code loading system loads at the entry type along with associated entry methods. An entry method is then executed at .

Note that the entry assembly can also refer to other assemblies such as according to the arrangement of that are to be invoked as the program continues execution. Thus as the program continues to run the program determines at based on the assemblies loaded so far in the client computer other assemblies and or types that are to be loaded to continue execution of the program . In this manner on demand loading of the assemblies and or types into the client computer is performed at . The tasks and are repeated as the program continues to run to enable continued on demand loading of types of code that are to be invoked during execution of the program.

The description of the assembly in the example above provides an identifier of the assembly which in the above example is the identifier string following Name . In the example several empty data structures are provided for storing information associated with types TypeDefs TypeRefs Instances. TypeDefs contain definitions of types TypeRefs contain unique identifiers also referred to as Type References of types and Instances contain instances of types loaded in the client computer.

In addition the above example description of the assembly provides references e.g. ref ref ref to other assemblies that are referenced by this assembly.

Note that in the description of the example assembly above two API routines are invoked GetAssembly and AddAssembly . These API routines can be provided as part of the API s see provided by the client side code loading system . The AddAssembly routine causes the identified assembly to be added to the local cache in the client computer .

The GetAssembly routine is invoked to load an assembly. The GetAssembly routine when invoked can look in the local cache to determine if the assembly has already been loaded in the client computer and if so the GetAssembly returns the instance in the cache . However if the assembly has not been loaded the GetAssembly routine will ask a LoadCode API routine which can also be part of the API s of the client side code loading system to download the assembly using the plugged transport mechanism . Note that assembly loading can also allow for additional assemblies in addition to the requested assembly to be loaded.

The AddAssembly and GetAssembly routines are invoked by the procedure of during execution of the program to perform on demand loading of assemblies.

As noted above the transport mechanism that can be used by the client side code loading system is pluggable so that the appropriate transport mechanism can be used for transporting code from the server computer to the client computer . When the loader is executed in the client computer the loader calls out a routine to detect the loading mechanism used at the client computer . In one example this detection routine can be referred to as DetectLoadingMechanism. The programmer for a proprietary platform at the client computer can overwrite the DetectLoadingMechanism routine to add the desired transport mechanism . To do so a LoadCode API routine can be defined that can be assigned a function corresponding to the transport mechanism. Note that the DetectLoadMechanism and LoadCode routine can be part of the API s depicted in . In one example the DetectLoadMechanism routine can be defined as follows 

In one example the LoadCode method is assigned a function LoadCodeUsingXmlHttp which is a function for loading code from the server computer to the client computer using XMLHTTPREQUEST.

Type loading occurs in a similar fashion as assembly loading. Type loading allows for additional types in addition to the requested type to be loaded together with the requested type.

In one example to load a type into the local cache of the client computer the following API routine which can be part of the API s of can be used AddType Assembly TypeObject Function where Assembly refers to the assembly containing the type TypeObject refers to the type that is to be loaded and Function is the code for retrieving metadata associated with TypeObject. The metadata associated with TypeObject includes the methods associated with TypeObject parent s of TypeObject and other information. An example of loading a type named System.Object which is contained in an assembly identified by CurrentAssembly is provided below 

In the example above the data structure Ret is returned by the AddType routine where the Ret data structure contains the methods associated with the type which are assigned unique names such as m m in the example above the containing assembly which is set equal to CurrentAssembly in the example above the parent s of the type as returned by Parents the static field stored on the type object which are assigned unique names f f etc. and initialized instances of the methods with corresponding instance fields such as instance.f.

The methods and fields on the type are each assigned a unique name that is used to make calls to such methods and fields from within the assembly boundary.

Note that the example above refers to a basic type which is contrasted with modified types discussed further below.

The following are example API routines that can be provided in the API s of the client side code loading system 

The GetTypeDef API routine retrieves a type based on the identified assembly and a string that identifies the type. Since methods and static fields are part of the type object the methods and static fields can be accessed with the Members and Fields properties of the type such as in the following example 

In the above example type.Members is used to retrieve method m and type.Fields is used to retrieve static field f.

The GetTypeRef API routine obtains a unique type reference to uniquely identify the type in the form of a unique identifier and a reference to the containing assembly. The GetTypeRef API routine allows the unique identifier of the type to be obtained without first having to load the type.

As depicted in all instances of a type are cached in the cache of the client computer so that the type instances will yield the same unique identifier each time the instances are called.

To support modified types different from the basic type discussed above such as generic instances arrays reference parameters and so forth a set of helper API routines can be provided that create a type reference representing the modifier. For example the following helper API routines which can be part of the API s of can be provided 

A generic instance contains or wraps another type. An array is a container of multiple instances objects of a specific type. A reference parameter is a pointer container to a type.

In some example implementations assemblies can be rebuilt or patched separately without having to do a full build of the program to avoid long compilation times in general. In accordance with some embodiments the assemblies are separately compiled to assembly placeholders as discussed above. To allow cross assembly calls while still allowing for separate compilation a unique way of identifying a method field is provided.

The field data can be stored according to a public field such as the following which is defined in the type object 

To allow for retrieval of a field across an assembly boundary an API routine GetFieldDef can be defined as follows GetFieldDef can be provided as part of the API s of 

In the above typeDef refers to the type on which the field is defined and name refers to the name of the field.

In one example to retrieve a field of an assembly named AssemblyName1 and from a type having name System.Object the following code can be provided 

In the above the invocation of fd GetFieldDef type FieldName allows for either the static field type.Fields fd or instance field instance.Fields fd to be accessed across assembly boundaries.

To uniquely identify a method such that cross boundary access can be provided a unique identifier for each type is provided in the method signature all parameters and the return type of the method . A mechanism is used to create a unique type identifier at runtime where the unique type identifier is referred to as Type References. This allows types to be identified in a unique short form way without having to build cross assembly knowledge into the identifier.

To obtain a unique Type Reference the GetTypeRef API routine can be used as provided above. The GetTypeRef routine returns a unique ID along with a reference to the containing assembly.

Since a mechanism is provided in which a type can be uniquely identified without loading the type a unique reference to a method can be defined as a method name and a list of the reference types of all corresponding parameters arguments of the method. One example of this is provided below 

In the above example ToString is the method name and the list of the types of arguments parameters of the method two arguments or parameters in the example above is given by GetTypeRef Assembly System. String GetTypeRef Assembly System. String .

In this manner overloading of methods is supported in which multiple methods with the same name can be provided but these multiple methods with the same name e.g. ToString above have different signatures in the form of a list of reference types of the arguments parameters of the corresponding methods.

Method overloading is further supported by providing a dictionary from a method name to dictionaries of reference type lists to method identifiers. In one embodiment the dictionary is provided as an entry in the type object referred in one example as a PublicMethods entry 

Public methods can be accessed across assembly boundaries using the following API routine which can be part of the API s depicted in 

In accordance with some embodiments support for making virtual calls to methods that are described on a type defined in another assembly is provided. For example a call can be made to a parent type referred to as a supertype which can be located in a different assembly. As a result of the virtual call to a method described on a type defined in another assembly some form of translation has to be provided such as in the form of a dictionary e.g. virtual table or vtable . In another scenario a method may be defined in a base type but a derived type derived from the base type may have overridden the base type method. At run time a mechanism should be provided to determine which version of the method defined by the base type or derived type should be called. This is accomplished using the vtable.

The vtable or virtual table acts as a dictionary from a method reference to a method definition. In other words given a call to a particular method the definition of the method has to be retrieved for execution.

Method references are referred to as MethodRefs which are similar to Type References discussed above. MethodRefs represent a method with a unique identifier that is generated at runtime. A MethodRef can be retrieved using the following API routine part of the API s of 

The MethodRefs are relatively small identifiers which allow lookups in a vtable to be relatively fast. An example of obtaining a MethodRef is provided below 

The following is an example of a vtable that can be built according to some embodiments to act as a dictionary from MethodRef to MethodDef 

In the example above the type is derived from base type System.Object and the vtable indicates that the ToString method in method m is overridden. However vtable does not override the GetHashCode method so the entry for that method is pointing to the method definition that was given in the base type System.Object.

Note also that methods can be added to the vtable without loading a base type. In other words mapping from a method reference MethodRef to a method definition MethodDef without loading the base type.

Thus according to some embodiments a mechanism is provided to allow for type by type loading of software code according to an on demand basis during execution of a program on a first computing device. The type of type loading of software code is transparent to the program and types can be performed in a manner where a superset of types can be returned in response to a request for one particular type. Also the transport mechanism to perform the type by type loading of software code is performed is pluggable so that an optimal or better transport mechanism can be used to perform the loading. Moreover unique identifiers can be obtained for types without having to load the types. In addition methods and fields associated with types can be assigned unique identifiers such that they can be accessed across assembly boundaries.

Instructions of software described above are loaded for execution on a processor such as one or more CPUs in . The processor includes microprocessors microcontrollers processor modules or subsystems including one or more microprocessors or microcontrollers or other control or computing devices. A processor can refer to a single component or to plural components.

Data and instructions of the software are stored in respective storage devices which are implemented as one or more computer readable or computer usable storage media. The storage media include different forms of memory including semiconductor memory devices such as dynamic or static random access memories DRAMs or SRAMs erasable and programmable read only memories EPROMs electrically erasable and programmable read only memories EEPROMs and flash memories magnetic disks such as fixed floppy and removable disks other magnetic media including tape and optical media such as compact disks CDs or digital video disks DVDs .

In the foregoing description numerous details are set forth to provide an understanding of the present invention. However it will be understood by those skilled in the art that the present invention may be practiced without these details. While the invention has been disclosed with respect to a limited number of embodiments those skilled in the art will appreciate numerous modifications and variations therefrom. It is intended that the appended claims cover such modifications and variations as fall within the true spirit and scope of the invention.

