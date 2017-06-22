---

title: Computer program product and computer system for language-enhanced programming tools
abstract: Statements of a computer program expressed using a first source natural language are made meaningful to a programmer familiar with a second target natural language. The first source natural language of the computer program is determined from the programmer, or through analysis, and the second target natural language desired by the programmer is selected. Textual constructs may be parsed, with reference to stored coding conventions to determine meaningful lexical tokens. Such tokens are translated with a translation engine, and displayed to the programmer, desirably using a graphical user interface feature of an integrated development, environment (IDE) for computer programming in a particular programming language.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09141603&OS=09141603&RS=09141603
owner: International Business Machines Corporation
number: 09141603
owner_city: Armonk
owner_country: US
publication_date: 20121019
---
This application is a continuation of prior application Ser. No. 12 475 471 filed on May 30 2009 which was a continuation of application Ser. No. 12 180 541 filed on Jul. 27 2008 which was a continuation of patent application Ser. No. 10 734 794 filed on Dec. 12 2003 now U.S. Pat. No. 7 412 388 issued Aug. 12 2008 and this application claims the benefit of those earlier filing dates.

A computer programming language has a predefined syntax that allows programmers to express logical statements of in a universal manner. In any computer program there is an intimate link between the universal and predetermined nature of a computer language in which the logical statements of the computer program are encoded and the arbitrary semantic constructs from a particular human language such as English French German etc. in which those statements are expressed. For example comments and the names of variables and functions are often derived from the programmer s first natural language or native tongue .

Thus while a computer program may rely upon a universally understood grammar the semantic content of that computer program may in many cases be difficult to comprehend for programmers who do not share the author s natural language.

As an example consider a team of German programmers which has produced a large software project. The computer code is commented using commentary in the German language with which all of the German programmers are familiar. Accordingly each of the German programmers can readily understand each other s work and can contribute to their peers work as informed observers. The software project is deployed in many countries and in for example Canada a major rewrite of the project is required to comply with local regulations.

As the Canadian programmers understand one or both of English and French but rarely German the Canadian programmers are at a distinct disadvantage. While the grammar of the language is entirely familiar and the meaning of the code can be deduced from logical statements and their structural context the semantic context upon which a full understanding so heavily relies is largely indecipherable to the Canadian programmers.

With the advent of reliable global data communications computer software projects are simultaneously conducted in various geographical locations using programmers that have different competencies in different natural languages. Similarly computer code originating in one country is commonly deployed in many other countries as in the hypothetical example given above.

Accordingly in view of the above observations a need clearly exists for an improved manner of allowing the semantic content of computer programs to be accessible to those who do not understand the natural language from which this semantic content derives.

Techniques are described herein for making statements of a computer program in a first source natural language so that semantic content of the computer program is meaningful to a programmer familiar with a second target natural language. These techniques involve first determining the first source natural language of the computer program either through analysis or user settings and the second target natural language selected by the programmer.

Once the source and target languages are established textual constructs in the source natural language of the computer program are determined for translation into the desired target natural language. Subtokenization is performed to form as required lexical tokens from the textual constructs. Subtokenization may rely on likely or detected coding conventions. The necessary translation is performed using a translation engine having a standard application programming interface API . The translation results are displayed in any convenient form for the benefit of the programmer. For example a mouse pointer may be used to indicate a particular textual construct such as a function name and a translation is provided in a pop up window in the graphical user interface.

In most cases identified textual constructs are further broken into individual lexical tokens prior to translation. These tokens are usually parts of particular textual constructs identified in any appropriate manner. One approach is to rely upon a repository of coding style conventions that encapsulate a coding style for naming functions variable etc. Using such coding conventions individual tokens that can be translated by the translation engine can be identified.

The techniques described herein are advantageously incorporated into an integrated development environment IDE with which programmers are familiar. Additional translation features as described herein can then be provided for use by the programmer.

A detailed description is provided of the facilities that are added to programming development tools to allow programmers that use different natural languages to have the freedom of expressing their thoughts and understanding each other s thoughts without restricting the natural language that is used in the computer programming language.

Translation is the act of converting words and sentences expressed in one natural language into another natural language. schematically represents the architecture of a translation engine and its operation.

The translation engine may in same cases have embedded intelligence to detect the natural language of the source text in which case the input for the natural language of the text is not required.

The output of the translation engine is the translated text in the desired natural language that is the translated text . An example of a translation engine is described below.

The translation engine s main module acts as a consistent and standard interface for users. The inputs and output of the translation engine are as described above. The main module delegates the task of translating text to the relevant submodules . The choice of the submodules depends on the inputs of the user. Such an arrangement can be provided for use in the form of binaries Dynamic Link Libraries executables etc or in the form of Web services so that other software can make use of this facility in their code.

Code editors differ from code displayers. Code editors such as the vi editor used in Unix and related computer operating systems allow the programmer to alter the code. Code displayers are seen in debuggers such as gdb also used in the Unix environment which provide a facility for displaying the code only. Source code in a viewer is read only and in an editor the source code is read write. In gdb this is done through the list command. The term editor is used herein for editors and displayers interchangeably.

Source code in its most basic form is a stream of characters. To generate a binary executable from the source code the compiler requires the source code to pass through various stages. Various tools for example editors also apply similar steps to identify various tokens of a computer program. One use of tokenizing a program is to display various tokens in different colors. This process is referred to as syntax highlighting .

Breaking a character stream into tokens is performed by lexically analyzing the source code. Lexical analysis is also termed scanning and the modules that perform this task of tokenizing a program are known as lexical analyzers or less formally scanners . For example lexical analysis helps the editor determine comments in source code. Lexical analyzers are coded by programmers or as in many cases tools such as lex are used to generate these programs. Tokens are the output of a lexical analyzer. A lexeme is the stream of characters that form a token. For example a C style comment function to do this and that will be identified as a token TOKEN COMMENT and the lexeme is the comment string itself.

Re tokenizing a computer program completely is expensive in terms of the computer processing time. Editors cannot afford to do this when the user is constantly editing the source code. A technique called incremental lexical analysis is used to re tokenize the altered portion of the source code and code in the vicinity of this altered portion. This technique localizes the re tokenizing process around the altered text during an editing session. Tim A. Wagner describes a suitable algorithm in further detail in published Mar. 10 1998 in Chapter 5 entitled General Incremental Lexical Analysis . This reference describes in detail how editors can implement incremental lexical analysis to avoid re tokenizing the whole program when the user is continuously editing the program. This publication has the details of the most commonly used generic incremental lexical algorithm.

Identifying statements expressions and declarations based on the grammar of a programming language is achieved by parsing the tokens obtained from lexical analysis. Tools such as Yacc can assist in generating programs that can parse a stream of tokens using a set of rules set by the grammar. For example parsing identifies a declaration of a variable. Lexical analysis and parsing helps in identifying various constructs of a computer program.

Editors implement lexical analysis in submodules or delegate the task of tokenizing parsing to other tools. For example a tool called Ctags can scan a source tree and identify the function names variables in a source file. This information is used by various editors that do not have a strong lexical engine built into the editors. An integrated development environment IDE has at least editor a compiler and a debugger. Editors can reuse the output of various tools. For example editors may reuse the lexically analyzed output of the compilers. Different arrangements exist but more importantly editors can be made capable of lexically analyzing and parsing code to determine various tokens and language constructs.

Editors interface with translation engines and display the translatable code in the native language selected by the programmer. The kind of tokens to be translated can be configured by a user.

Translatable code usually consists of comments variable names function names and so on. For example editors provide the facility of translating the comments that are originally expressed in for example the German language into comments expressed in for example the English language.

The following description uses the term construct for one such translatable code item. The procedure of how lexical analysis and parsing facilitates their extraction from the source code is described above. Editors can implement or already implement the procedure for both techniques using standard lexical analysis and parsing algorithms.

A hypothetical example is where a user instructs the editor that comments and function names should be translated from German to English. The editor upon processing the code as described according the steps above displays the comments and function names in English using any convenient technique.

A minor variation upon the steps described above are presented in Table 3 below using substitute steps W and which replace step .

Feeding a function name such as sort array or SortArray may not yield a correct translation. Naming a function depends on the coding style of the program. Therefore the tokenizing and parsing provided by existing editors may not suffice to break a function name into meaningful words. In this case the editor can provide an interface in which a programmer can tell the editor the coding convention being used.

Alternatively the editor can attempt detecting the coding convention by keeping a repository of various coding styles in a language understood internally by the debugger. For example an input such as W  W may denote that a function variable name consists of English words followed by an underscore optionally followed by a word and another underscore multiple times and finally ending with a English language word. As stated earlier the editor itself can hold such expressions in a repository for intelligent detection of words in a variable or function name or any other token that the programmer finds fit for translation.

Debugging assists in detecting bugs in a program during runtime. A commonly used technique is called interactive debugging which involves inserting breakpoints and observing the state of a program when a breakpoint is hit. A state of a program at an instance includes the call stack variables memory registers etc. A compiler generates binary executables from source code. The binaries that are meant to run on customer s sites do not have additional information that facilitates the querying of a program s state during runtime. Using such binaries can be tedious without this information to debug them. To provide support for debugging a special directive usually a switch instructs compilers to generate additional information. This information aids in displaying variable names function names source code mapping etc in a form that the programmer readily comprehends. This extra information is called the debug information or debug symbols. These symbols help the debugger provide the following listed items of information 

The debug information is either combined with the object files or is stored separately in a different file. COFF and PDB are two formats for debug information.

Code is desirably viewed in a language that one understands but the translated text may not exactly match with the original text when one is debugging the variables displayed by the debugger. The debugger also interfaces with the translation engine or uses cached results and translate the function variable names and other tokens so that the programmer s view of the variable names function names etc is the same as that displayed in the translated view of the code.

The technique described above in the subsection entitled Translation of parsed function and variable names together with cached translations can be used in the debugger. This solution can be further extended to tools that dump the debug information in various formats. For example the tool objdump may dump translated versions of the debug information so that this information makes more sense to the programmer.

If variable names in an editor are translated into another language then similar techniques when applied to the debug information allow programmers to view translated variable names in tools that make use of this information. For example if the editor translates the variable InputName in source code then viewing this variable in the debugger should show the translated name to the users of the debugger. This enhances the debugger to let users observe the state of the program using translated debug symbols.

If the translation engine translates code from the editor the results can be cached and subsequently used by the debugger to display variable and function names in their translated form. More generally any tool that makes use of the debug symbols can translate the symbols to allow the users to view translated names of these symbols in the desired natural language.

Debuggers and related tools often allow programmers to input the variable names for display manipulation etc. These names are matched in the symbol table and the debugging information stored during compile time. If no match is found for the input provided the debugger flags an error. The debugger in this case allows the programmer to input these names in the translated string. The name is not only searched in the symbol table debug information but also in the list of variables that were translated and used in the debugger.

Debuggers let programmers input symbol names in expressions in a watch window a command line etc. The debugger flags an error if the symbol is not found in the debug information. is a flowchart that describes how symbols are conventionally used in debuggers. These steps are outlined in Table 8 using correspondingly numbered steps.

Translated names can even be used in the above scenario. is a flowchart that describes steps required for a debug session to accept translated names. These steps are outlined in the Table 9 using correspondingly numbered steps.

Various combinations the facilities described above may be used. Therefore the tools also provide a user configurability to cater to the needs of all programmers. For example the editor may be configured to overwrite in display only the comment with the translated version. Optionally the translated version can be displayed in the status bar or other graphical user interface GUI controls. Similarly the user may have the option of translating function names but not variable names. The programmer may additionally have user interface controls that let her or him translate comments in a highlighted area. Many options are possible. The above solution can further be extended to other tools such as design tools other debugging utilities etc.

Integrated Development Environments IDEs are user interfaces that combine various programming tools together in a single computer environment . IDEs provide an interface to various development tools such as debuggers and compilers. IDEs also have editors so that the edit compile debug cycle can be performed from the same program. Microsoft Visual Studio is an example of such an IDE. An integrated environment improves the productivity of programmers. Creating an IDE requires creating a graphical user interface GUI to the various tools.

Editors debuggers and other debugging tools can use a translation module to facilitate understanding of certain portions of a computer program in the desired natural language as described herein. An IDE can be used in a similar manner and consequently uses tools that support the translation. As an example an IDE can be constructed having

A common translation engine may be deployed and the task of translation can be thus centralized between all tools used by an IDE. The common translation engine fulfills the translations needs of the editor and the debugger. Centralizing translation allows translation to result to be cached to avoid unnecessary retranslation.

An IDE can thus be constructed by using editors and debuggers with translation capabilities. Optionally the IDE may perform translation tokenizing and re tokenizing as required centrally for all tools.

The components of the computer system include a computer a keyboard and mouse and a video display . The computer includes a processor a memory input output I O interfaces a video interface and a storage device .

The processor is a central processing unit CPU that executes the operating system and the computer software executing under the operating system. The memory includes random access memory RAM and read only memory ROM and is used under direction of the processor .

The video interface is connected to video display and provides video signals for display on the video display . User input to operate the computer is provided from the keyboard and mouse . The storage device can include a disk drive or any other suitable storage medium.

Each of the components of the computer is connected to an internal bus that includes data address and control buses to allow components of the computer to communicate with each other via the bus .

The computer system can be connected to one or more other similar computers via a input output I O interface using a communication channel to a network represented as the Internet .

The debugger software may be recorded on a portable storage medium in which case the computer software program is accessed by the computer system from the storage device . Alternatively the debugger software can be accessed directly from the Internet by the computer . In either case a user can interact with the computer system using the keyboard and mouse to operate the programmed computer software executing on the computer .

Other configurations or types of computer systems can be equally well used to implement the described techniques. The computer system described above is described only as an example of a particular type of system suitable for implementing the described techniques.

The debugger described herein allows for development of computer software code in various geographical locations by reducing language related problems. Programmers can achieve a better understanding of legacy computer software code written that relies upon expressions in a natural language with which the programmer is not familiar. That is a programmer interpreting another programmer s code can debug computer software in an environment that caters to their own language needs. Conversely a programmer developing source code can rely upon their native language to freely expression ideas within the computer code.

The problem of poor translation accuracy decreases as translation engines become ever more sophisticated. Thus the benefits of permitting a programmer to use their native language are available with only little disadvantage.

Various alterations and modifications can be made to the techniques and arrangements described herein as would be apparent to one skilled in the relevant art.

