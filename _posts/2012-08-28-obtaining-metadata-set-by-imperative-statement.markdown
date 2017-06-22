---

title: Obtaining metadata set by imperative statement
abstract: Aspects of the subject matter described herein relate to imperative attribution. In aspects, metadata of a managed runtime environment may be set by imperative statements included in code of a program executing in the managed runtime environment. A metadata consumer may request the metadata. A metadata identifier of the metadata requested may be provided implicitly or explicitly. A parameter that indicates how to obtain the metadata may also be provided. In response, the metadata may be obtained and provided. The metadata may be computed at parse time, run time, or another time and may be computed based on state available to a managed runtime environment at the time the metadata is computed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09104781&OS=09104781&RS=09104781
owner: Microsoft Technology Licensing, LLC
number: 09104781
owner_city: Redmond
owner_country: US
publication_date: 20120828
---
As software and its development has grown increasingly complex there has been a trend towards augmenting the literal application source code of programs with additional supporting information often referred to as metadata . Program metadata is often consumed by development tools in order to provide a richer tooling experience. For example metadata may indicate that a function or method may not be made inline. A compiler may use this metadata at compile time to create a binary executable where the function or method indicated by the metadata is not inline. After use the metadata is discarded and cannot be retrieved on inspecting the compiled binary. The metadata described above can only include what is known or can be calculated at compile time.

The subject matter claimed herein is not limited to embodiments that solve any disadvantages or that operate only in environments such as those described above. Rather this background is only provided to illustrate one exemplary technology area where some embodiments described herein may be practiced.

Briefly aspects of the subject matter described herein relate to imperative attribution. In aspects metadata of a managed runtime environment may be set by imperative statements included in code of a program executing in the managed runtime environment. A metadata consumer may request the metadata. A metadata identifier of the metadata requested may be provided implicitly or explicitly. A parameter that indicates how to obtain the metadata may also be provided. In response the metadata may be obtained and provided. The metadata may be computed at parse time run time or another time and may be computed based on state available to a managed runtime environment at the time the metadata is computed.

This Summary is provided to briefly identify some aspects of the subject matter that is further described below in the Detailed Description. This Summary is not intended to identify key or essential features of the claimed subject matter nor is it intended to be used to limit the scope of the claimed subject matter.

The phrase subject matter described herein refers to subject matter described in the Detailed Description unless the context clearly indicates otherwise. The term aspects should be read as at least one aspect. Identifying aspects of the subject matter described in the Detailed Description is not intended to identify key or essential features of the claimed subject matter.

The aspects described above and other aspects of the subject matter described herein are illustrated by way of example and not limited in the accompanying figures in which like reference numerals indicate similar elements and in which 

As used herein the term includes and its variants are to be read as open ended terms that mean includes but is not limited to. The term or is to be read as and or unless the context clearly dictates otherwise. The term based on is to be read as based at least in part on. The terms one embodiment and an embodiment are to be read as at least one embodiment. The term another embodiment is to be read as at least one other embodiment. 

As used herein terms such as a an and the are inclusive of one or more of the indicated item or action. In particular in the claims a reference to an item generally means at least one such item is present and a reference to an action means at least one instance of the action is performed.

Sometimes herein the terms first second third and so forth may be used. Without additional context the use of these terms in the claims is not intended to imply an ordering but is rather used for identification purposes. For example the phrases first version and second version do not necessarily mean that the first version is the very first version or was created before the second version or even that the first version is requested or operated on before the second version. Rather these phrases are used to identify different versions.

A programming interface or more simply interface may be viewed as any mechanism process or protocol for enabling one or more segment s of code to communicate with or access the functionality provided by one or more other segment s of code. Alternatively a programming interface may be viewed as one or more mechanism s method s function call s module s object s etc. of a component of a system capable of communicative coupling to one or more mechanism s method s function call s module s etc. of other component s . The term segment of code in the preceding sentence is intended to include one or more instructions or lines of code and includes e.g. code modules objects subroutines functions and so on regardless of the terminology applied or whether the code segments are separately compiled or whether the code segments are provided as source intermediate or object code whether the code segments are utilized in a runtime system or process or whether they are located on the same or different machines or distributed across multiple machines or whether the functionality represented by the segments of code are implemented wholly in software wholly in hardware or a combination of hardware and software.

Headings are for convenience only information on a given topic may be found outside the section whose heading indicates that topic.

One or more of the components illustrated in may be implemented by one or more computing devices. Computing devices may include one or more personal computers server computers hand held or laptop devices multiprocessor systems microcontroller based systems set top boxes programmable consumer electronics network PCs minicomputers mainframe computers cell phones personal digital assistants PDAs gaming devices printers appliances including set top media center or other appliances automobile embedded or attached computing devices other mobile devices hardware capable of executing instructions distributed computing environments that include any of the above systems or devices and the like.

One or more of the components illustrated in may be implemented in a virtual environment. A virtual environment is an environment that is simulated or emulated by a computer. The virtual environment may simulate or emulate a physical machine operating system set of one or more interfaces portions of the above combinations of the above or the like. When a machine is simulated or emulated the machine is sometimes called a virtual machine. A virtual machine is a machine that to software executing on the virtual machine appears to be a physical machine. The software may save files in a virtual storage device such as virtual hard drive virtual floppy disk and the like may read files from a virtual CD may communicate via a virtual network adapter and so forth.

More than one virtual environment may be hosted on a single computer. That is two or more virtual environments may execute on a single physical computer. To software executing in each virtual environment the virtual environment appears to have its own resources e.g. hardware even though the virtual environments hosted on a single computer may physically share one or more physical devices with each other and with the hosting operating system.

The store may include any storage media capable of storing data involved with software development. The term data is to be read broadly to include anything that may be represented by one or more computer storage elements. Logically data may be represented as a series of 1 s and 0 s in volatile or non volatile memory. In computers that have a non binary storage medium data may be represented according to the capabilities of the storage medium. Data may be organized into different types of data structures including simple data types such as numbers letters and the like hierarchical linked or other related data types data structures that include multiple other data structures or simple data types and the like. Some examples of data include information program code program state program data other data and the like.

The store may be implemented as a file system database volatile memory such as RAM other storage some combination of the above and the like and may be distributed across multiple devices. The store may be external internal or include components that are both internal and external to the devices that host components of the software development system .

In one embodiment the software development components may be operable to work with a dynamic programming language. In another embodiment techniques that are described herein may also be applied to non dynamic programming language environments.

At runtime a dynamic programming language environment may perform some actions a non dynamic programming language environment performs if at all at or before compile time. For example during program execution a dynamic programming language environment may add new code extend objects and definitions modify a type system and the like. Some exemplary dynamic programming languages include ActionScript BASIC BeanShell Clojure ColdFusion Lisp Groovy JavaScript VBScript Perl PHP PowerShell Python Ruby Smalltalk Tcl and the like. Some non dynamic programming languages include assembly C C Java Pascal Fortran and others.

The source code editor may allow a software developer to enter delete and modify source code of a program. The source code editor may display source code of a program on a display and receive input via the user interface.

The runtime manager may launch a runtime environment to execute source code. In one embodiment a runtime environment may include a Web browser. In other embodiments a runtime environment may include one or more components that allow code to be executed outside of a Web browser.

The debugger may interact with a runtime environment to test and debug a program. The debugger may allow a software developer to execute a program step by step pause the program at certain points within the program track values of variables and memory locations modify program state and the like. The debugger may allow a software developer to indicate the conditions under which the debugger is notified of exceptions. For example a software developer may want to be notified of exceptions that are raised in user code but not to be notified of exceptions that are raised in library code.

The profiler may be used to collect statistics regarding execution of a program. For example the profiler may measure usage of memory usage of particular instructions frequency and duration of functions calls other statistics and the like. To collect the statistics the profiler may interact with the runtime environment may be a part of the runtime environment may reside in a lower layer that allows the profiler to see what code is executed or may operate in other ways known to those skilled in the art.

The other development tool s represent any other development tools that may be included in the software development system .

The metadata subsystem may include one or more components that allow metadata to be associated with logical elements of a program. Metadata may include static data e.g. the value 5 or dynamic data that is available or computed at parse time compilation time run time or some other time. Metadata may be specified by providing static data code that when executed produces data a reference to code that when executed produces data or the like.

Metadata does not influence the logical flow of the program but may influence the behavior of the environment in which the program executes. For example metadata may be used by a runtime to determine whether an exception is to be raised to a debugger but the metadata does not affect results calculated by the program. Metadata may be used to modify other behavior such as logging mechanisms stack dumping activities memory management techniques other runtime behavior and the like.

As mentioned above metadata may be associated with logical elements of a program. Some exemplary logical elements include functions files code containers lexical scopes current stack frames stack of calling scope properties classes prototypes worker threads specific call instances specific object instances delegates global scope other logical elements and the like. Furthermore a logical element may or may not inherit metadata from its parent e.g. containing or calling logical element based on a configuration or a parameter passed to an API for example.

This association of metadata with a logical element may allow a runtime to obtain the metadata based on a logical element and state that is available via the runtime. This association may also allow the calculation of all or a portion of the metadata based on state of the program. The specific logical element to which to associate metadata may be inferred or explicitly indicated.

Metadata may be set via an application programming interface API . A software developer may cause the API to be called during execution of a program by adding a programming statement to the source or other code of the program for which metadata is desired. In one implementation for flexibility one or more programming statements that call the API may be placed within the source code where any other types of programming statements may be placed. The metadata may indicate data that is immediately available or that may be calculated at runtime. For example the metadata may be calculated based on inspecting a relevant scope stack chain.

The API may include required and optional parameters. Zero or more of the parameters may include static data e.g. data that may be calculated or determined by data included in the parameter while zero or more of the parameters may be calculated based on runtime state. Below some exemplary types of parameters are described in more detail. There is no intention however that the types described below are all inclusive or exhaustive of the types that may be used in accordance with the teachings herein. Indeed based on the teachings herein those skilled in the art may recognize other types of parameters that may be used without departing from the spirit or scope of aspects of the subject matter described herein. Some exemplary types of parameters include 

1. An identifier to associate with the metadata. For example an API may include a parameter that allows a caller of the API to indicate an identifier that is to be associated with the metadata. Subsequently this identifier may be used to obtain the metadata from the metadata subsystem .

2. Specific call instance. In some implementations it may be desirable to have metadata associated with a specific invocation of a function. For example instead of having the metadata associated with every call to the function it may be desirable to have the metadata associated with a certain call to the function or a set of calls to the function. This may be accomplished through the use of a specific call instance.

A specific call instance may be identified via a function name and a number or a set of numbers. The number s may indicate specific invocation s of the function. For example a function may be called many times during the execution of a program. To identify a specific call a statement setting metadata may include an identifier of the function and a number corresponding to the specific call.

3. An applies to parameter. The API may include a parameter that indicates the type of logical element with which the metadata is to be associated. This is sometimes referred to herein as the scope to which the metadata may be applied. This parameter together with the scope from which the API is called may be used to determine a logical element with which to associate the metadata. For example if the API is called from the scope of a block within a function and the parameter indicates the logical element of the metadata is a function the metadata may be associated with the function not the block .

As another example if parameter indicates that the metadata is to be applied to a function but the API is called from a global scope the call may be ignored an error may be generated or the metadata may be stored with information that indicates that the API was called from a global scope.

An applied to parameter may also be used by the runtime to tune the runtime s behavior. For example an applied to parameter that indicates that the metadata is global may be used by the runtime to create a global variable that is modified each time the metadata is changed. As another example an applied to parameter that indicates that the metadata is for a function may be used by the runtime to remove the executable code e.g. from compiled code created at runtime that calls the API after the API has been called once from the function.

An applies to parameter may be inferred by the logical element from which the API is called. For example if the API is called from a global scope the metadata may be associated with a global scope. If the API is called from a function the metadata may be associated with the function scope. If the API is called from within a lexical scope the metadata may be associated with the lexical scope.

4. An identifier of a logical element. The API may include a parameter that indicates a specific logical element with which to associate the metadata. For example the API may allow a caller to indicate a function other than the function from which the API is called.

Where a logical element is not explicitly indicated the logical element may be inferred. For example a logical element may be inferred to be a scope e.g. function block file or the like that includes the call to the API.

5. A disabling parameter. The API may include a parameter that indicates how many times a statement may be used to call the API. For example in some cases it may be desirable to have a statement to set metadata only call the API once. For example it may be useful to know whether a function has ever been called during the execution of a program. In another embodiment it may be useful to know whether a loop has been executed once. In one implementation to improve performance a runtime may remove the executable code e.g. from compiled code created at runtime or at compile time that calls the API after the API has been called the number of times from the desired scope.

Other techniques may be used to remove or otherwise disable an instruction that sets the metadata. Some examples of such techniques include providing a callback with the metadata where the callback indicates whether the instruction is to be removed or otherwise disabled setting a property and the like. Another example includes calling an API providing a metadata identifier and indicating that the instruction is to be removed or otherwise disabled or the like. The above examples are not intended to be all inclusive or exhaustive. Indeed based on the teachings herein those skilled in the art may recognize other techniques that may be used to remove or otherwise disable an instruction that sets metadata without departing from the spirit or scope of aspects of the subject matter described herein.

6. A recursion parameter. The API may include a parameter that indicates how the metadata is to be applied when recursion occurs. This parameter may indicate that the metadata may be associated with a specific level of the recursion so that a metadata consumer may obtain the least recent most recent or some other recursion level at which the metadata was set during the recursion.

7. A relationships parameter. The API may allow a parameter that indicates a relationship of the call to other current stack frames in order to identify a logical element. Some examples of relationships parameters include first setter wins last setter wins set metadata and ignore all subsequent setters in nested frames set metadata for the current frame only and the like. In first setter wins the metadata set by the first stack frame to set the metadata is retained while other metadata that is attempted to be set by later stack frames is discarded or ignored. In last setter wins the metadata set by the last stack frame to set the metadata is retained while other metadata that is attempted to be set by later stack frames is discarded or ignored.

In set metadata and ignore all subsequent setters in nested frames the metadata set by an outer frame is retained while the other metadata that is attempted to be set by stack frames within the outer frame is discarded or ignored. In set metadata for the current frame only metadata set in the current frame is retained while metadata that is attempted to be set by other frames is discarded or ignored.

8. A callback parameter. In one embodiment one or more callback functions may be provided as parameters to the API. For example a statement such as 

may be inserted into code by a developer. The callback function GenValue may be called by the runtime to provide metadata. The callback function may use runtime state to compute the metadata.

In this embodiment calculation of the metadata may be deferred to a time after the statement is encountered in the code. For example the runtime may lazily wait to call the GenValue function until the runtime needs the metadata.

9. An inheritance parameter. In one embodiment a parameter may indicate whether metadata is to be inherited by contained or called logical elements. If the metadata is to be inherited then child logical elements may also be associated with the metadata.

10. Phase. In one embodiment the API may include a parameter that indicates when the metadata setting statement is to be evaluated. For example a parameter may indicate that the metadata setting statement is to be evaluated during first parse second parse or Nth parse during execution during first compilation or re compilation or during some other phase.

11. Payload. The API may include a parameter that indicates the metadata. The payload parameter may include metadata or may include or reference instructions e.g. programming statements for creating the metadata using program state that is available during execution of the program.

1. SetAttribute foo . . . . In this example the API is called with an explicit static identifier foo and zero or more other attributes indicated by the . . . .

2. SetAttribute objfoo . . . . In this example the API may combine data that could be specified by separate parameters by allowing information about the metadata to be specified in an object with properties. For example an object e.g. objfoo may have an identifier property and one or more of a scope property an applies to property and other properties. One example of this is illustrated by the following code snippet 

In this example an object includes two properties. The name property specifies an identifier of the metadata while the appliesTo property indicates the logical elements the metadata may be applied to. Furthermore one or more of the properties may be computed based on state that exists during execution.

3. SetAttribute foo . . . . In this example a reference to a function is passed as a parameter to the API. This function may include statements that return or calculate data used by the API. In one embodiment the function may be called when the metadata is requested by a metadata consumer. In another embodiment the function may be called immediately and the return data stored in a metadata store. In another embodiment the function may be called at one or more other times.

4. SetAttribute http ms.keys foo . . . . In this example a reference to a location accessible via a network is passed as a parameter to the API. In one example the location may be a place to store the metadata. In another example the location may indicate a service that may be called to store the metadata.

The metadata subsystem may maintain information about the scope from which the API is called. For example the API may be called from various nested scopes e.g. where one logical element is within another logical element . For example a function Bar may have nested logical elements such as 

In this example the API may store the identifier i.e. foo and each payload together with sufficient information to identify the scope of the metadata. The first SetMetadata call may have a scope of the function Bar while the second SetMetadata call may have the scope of the unnamed block e.g. the code after the first SetMetadata statement and the third SetMetadata call may have the scope of the function Bar The metadata returned by the API may depend on the metadata identifier and the logical element. For example to precisely specify a specific payload both the metadata identifier e.g. foo and the scope e.g. Bar unnamed block or Bar may be specified.

The creation of metadata may be disabled for a program as a whole or for individual metadata calls. The following exemplary implementations are contemplated 

1. On parse. In this implementation code has not been executed yet but in parsing the code the runtime may find a set metadata call calculate the metadata based on static information included in the metadata call and associate the metadata with logical element. Thereafter the metadata call may be stripped out disabled or ignored.

2. On parse plus dynamic execution. In this implementation code has not been executed yet but in parsing the code the runtime may find a set metadata call calculate the metadata based on static information included in the metadata call together with dynamic execution of code included in the metadata call and associate the metadata with a logical element.

3. One time association. In this implementation the first time a scope is executed that includes the metadata call the metadata is computed. After the statement setting the metadata is executed the metadata call within the scope is stripped out disabled or ignored to improve performance.

4. Every call. In this implementation each time a scope is called that includes the statement setting the metadata the metadata is computed.

5. Caller indicates stop. In this implementation an API may allow a metadata call to pass a parameter that indicates that after the current metadata call succeeds and generates metadata that thereafter the metadata call is stripped out disabled or ignored.

In one embodiment a runtime may include logic to expand a phrase found in a function into one or more metadata calls to set metadata for a logical element. For example a phrase such as SetAllMetadata in a function may be expanded by the runtime into one or more metadata calls within the function. The phrase SetAllMetadata may be defined elsewhere and may be in lined by the runtime or another component replacing it with its defined statements prior to execution. This may be helpful for example where the same metadata needs to be set for multiple functions and may also help to eliminate code clutter.

In another embodiment helper code may be referred to in a function. For example a function may include the following code 

The statement SetAllMetadata may refer to helper code that is defined elsewhere. The helper code may set metadata in the scope of F and any other functions in which the statement SetAllMetadata is found.

In one embodiment the SetMetadata call may be encoded as a comment or other code that is generally not executed. Parsers or compilers that understand the syntax of the SetMetadata comment may set attributes based on the comment while other parsers may ignore the comment. In one implementation this may be used to mark methods that are to be exposed. For example a function may include a statement as follows 

The metadata subsystem may receive requests for metadata. A requestor that seeks to obtain metadata may provide one or more parameters to indicate the metadata desired. Implicit parameter s may be provided by a context provider as described in more detail in conjunction with .

A request for metadata includes at a minimum an identifier of the metadata although this identifier may be supplied explicitly or implicitly. For example in one embodiment to obtain metadata a requestor may call an API and may explicitly pass an identifier of the metadata as a parameter.

In another embodiment a requestor may use a reference to an instance of a metadata object previously obtained to obtain the metadata. For example a function may include a statement as follows 

In another embodiment a requestor may request metadata and supply no metadata identifier. A context provider may determine a scope in which the requestor requested the metadata and provide the scope to the metadata manager. The metadata manager may use the scope to lookup metadata associated with the scope.

In addition to receiving a metadata identifier a metadata subsystem may also obtain a parameter that indicates how to obtain the metadata. This parameter may be received from the requestor that has requested the metadata or may be obtained from a component of the metadata subsystem. The parameter may indicate for example 

2. That metadata associated with a logical unit of processing is to be obtained. A logical unit of processing may include for example a thread a fiber a worker thread e.g. such as those included in JavaScript a transaction a call chain an object that shares some type of context such as address space data or other resources or the like.

When metadata is associated with a call chain the metadata may be associated with scopes execution environments that are chained but otherwise distinct from each other.

3. Whether one or more metadata values are to be returned when the metadata value associated with a metadata identifier has been set multiple times. A metadata identifier may be associated with multiple metadata values. When a requestor requests metadata and provides a single metadata identifier the metadata subsystem may provide multiple metadata values. For example metadata for a metadata identifier may be set by a plurality of imperative statements. If each metadata value that is set is preserved upon receiving a metadata identifier the metadata subsystem may return a plurality of metadata values with or without information that indicates the scopes in which the metadata values were set. The requestor may then operate on the metadata values as desired.

In the example above a parameter may be obtained that indicates whether a single metadata value is to be returned or a plurality of metadata values is to be returned. This parameter may be passed by the requestor in the request for metadata may have been associated with the metadata previously may be determined based on configuration or the like.

To associate this parameter with metadata in one implementation a descriptor may have been provided previously by an imperative statement. A descriptor is data about the metadata that provides additional information about the metadata. A descriptor may include for example rules for storing the payload how to obtain the metadata what logical elements the metadata may be applied to or any other information about the metadata.

The descriptor may indicate whether one or a plurality of values associated with the metadata identifier are returned and may indicate which value s is preserved and which value s is discarded when the metadata identifier is used multiple times to set metadata values. This may operate similarly to the relationship parameter previously described.

In an implementation a descriptor may be provided when defining metadata. For example before setting metadata a CreateMetaData statement may be executed that includes a descriptor. Thereafter the metadata may be set one or multiple times as allowed by the descriptor.

In another implementation a descriptor may be provided as an optional parameter in setting metadata. In this example a metadata provider may supply the descriptor with the first or a subsequent setting of the metadata.

4. A timestamp to use in obtaining the metadata. The requestor may provide a timestamp together with a request to obtain the metadata. In response the metadata system may provide metadata set after the timestamp at the timestamp or before the timestamp depending on configuration or implementation.

5. An identification of a logical element. The requestor may provide an identifier of a logical element of the program for which metadata is requested. In response the metadata subsystem may provide metadata associated with the logical element.

The examples above are not intended to be all inclusive or exhaustive. Based on the teachings herein those skilled in the art may recognize other ways in which a parameter may be supplied that indicates how to obtain the metadata without departing from the spirit or scope of aspects of the subject matter described herein.

The metadata injector represents code that may call the interface and provide metadata. The metadata injector may include an instruction of code that is being executed in a managed runtime environment. The code may call the metadata manager through the interface and may provide one or more parameters that correspond to the parameters previously mentioned. The metadata injector may also include other components that provide data to the metadata manager . For example the metadata injector may include the managed runtime environment in which the code executes. The managed runtime environment may for example provide scope information to the metadata manger .

The interface may comprise a programming interface that allows communication with the metadata manager .

The metadata manager may comprise a component that stores metadata in the metadata store and also stores associations between the metadata and the logical elements . For example the metadata manager may store the metadata in a memory of a managed runtime environment by setting attributes associated with the runtime. When the attributes are manipulated the behavior of the managed runtime environment may be modified.

The metadata manager may also provide metadata from the metadata store to a requestor upon receiving an identifier of the metadata requested. The metadata manager may call code e.g. callback code examine runtime state or perform other actions as needed to calculate the metadata.

The metadata provider includes any component operable to provide metadata in response to evaluating an instruction of code. Some examples of the metadata provider include a program executing in a managed runtime environment a software development tool a managed runtime environment an operating system and the like. The metadata provider may be accessed by an API by which code executing in the managed runtime environment may provide metadata and data associated with the metadata to the metadata manager .

The metadata provider may provide an identifier and a payload to the metadata manager . The metadata provider may also provide other data to the metadata manager in the form of one or more parameters as has been indicated previously. In one implementation the metadata provider may explicitly provide an identifier of a logical element to the metadata manager .

In another implementation the identifier of a logical element may be implicitly provided via the context provider . In this implementation when the metadata provider does not explicitly provide an identifier of a logical element the context provider may determine the identifier of the logical element based on a scope of an executed instruction that calls the metadata manager . The context provider may then pass this identifier to the metadata manager.

In addition when the metadata consumer does not explicitly supply a metadata identifier or other parameter with its request the metadata manager may provide the metadata identifier or other parameter if needed to further qualify the requested metadata.

In addition to the identifiers above there may be one or more other identifiers provided to the metadata manager . For example a grouping identifier may be provided to the metadata manager to further qualify a payload. This grouping identifier may be used to tag metadata in addition to the identifiers described previously. For example a function A may be called by functions B C D and so forth. To create data that readily identifies when the function A was called by B and when the function A was not called by B a grouping identifier e.g. ParentIsB or ParentIsNotB may be provided to and stored by the metadata manager .

This data may then be used by the metadata consumer to obtain additional helpful information. For example a profiler may be interested in calls from B to the function A but may not be interested in calls to the function A from other functions. To obtain the data in which it is interested the profiler may query the metadata manager using the grouping identifier as a qualifier.

The metadata manager is operable to receive the identifiers indicated above and a payload. The identifiers may together form lookup data that may be used to obtain the payload from the store . Lookup data may include the identifiers or be data that is derived e.g. through a function from the identifiers. The payload may include one or more of metadata code that when executed computes the metadata and a reference to code that when executed computes the metadata.

The store may include any storage media capable of storing metadata together with the lookup data and may be implemented in a manner similar to the implementation of the store of .

The metadata consumer is any component that requests metadata from the metadata manager and may include for example the types of components indicated above with respect to the metadata provider . The metadata consumer may provide one or more parameters to the metadata manager and may receive metadata in response thereto. The metadata consumer may include a component of the managed runtime environment in which the metadata was generated code that runs within the managed runtime environment an entity outside of the managed runtime environment or the like. An entity outside the managed runtime environment may include code that is neither a part of the managed runtime environment nor running inside the managed runtime environment.

At block a request for metadata is received. For example referring to a metadata consumer may request metadata from the metadata manager .

At block a qualifying parameter is obtained. For example referring to the metadata manager may receive a qualifying parameter from the metadata provider the metadata consumer the context provider or the store . A qualifying parameter indicates how to obtain the metadata as described previously.

At block the metadata is obtained based on the lookup data and the parameter. For example referring to the metadata manager may use the identifier and the parameter to obtain metadata. The metadata may be stored in the store or generated as needed e.g. via a code that has access to state of a runtime environment .

At block the metadata is provided to the requestor. For example referring to the metadata manager may provide the metadata to the metadata consumer .

At block a request is sent for metadata. The request may be sent implicitly or explicitly with an identifier that identifies the metadata. For example referring to the metadata consumer may send a request for metadata to the metadata manager and may provide a metadata identifier e.g. foo .

At block metadata is received. For example referring to the metadata consumer may receive the metadata is requested.

It is allowed but not required that metadata and the application of metadata be coupled together. For example it is not required that the metadata identifier e.g. setUserUnhandledException indicates the nature or function of the metadata. Indeed metadata and application of the metadata may be decoupled. Some examples of this concept are illustrated in the following code snippets 

As can be seen from the foregoing detailed description aspects have been described related to imperative attribution. While aspects of the subject matter described herein are susceptible to various modifications and alternative constructions certain illustrated embodiments thereof are shown in the drawings and have been described above in detail. It should be understood however that there is no intention to limit aspects of the claimed subject matter to the specific forms disclosed but on the contrary the intention is to cover all modifications alternative constructions and equivalents falling within the spirit and scope of various aspects of the subject matter described herein.

