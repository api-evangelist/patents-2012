---

title: Programming learning center
abstract: A programming learning center includes a learning center workshop and a learning module generator. The learning center workshop allows a user to create a computing program by connecting programming blocks portrayed visually within the learning center workshop as building blocks. The learning module generator generates a learning module from the computing program. The learning module iterates through the computing program to generate a sequential list of steps. The learning module generator allows the user to add notations to the sequential list of steps and to reorder steps in the sequential list of steps.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09595202&OS=09595202&RS=09595202
owner: NEURON FUEL, INC.
number: 09595202
owner_city: Mountain View
owner_country: US
publication_date: 20121214
---
Computers are ubiquitous and used for business education recreation and so on. Familiarity with the principles of computer programming and experience in computer programming is a useful skill. While familiarity with commonly used programming languages may be beyond the competency of many younger children even at a young age children can learn the basic principles of computer programming.

For example the learning center integrates social learning and unique game mechanics with a guided curriculum to deliver a highly engaging and rewarding experience to children of all ages. The learning center allows children to perform creative activities such as write digital storybooks and scrapbooks build video games animate their favorite characters and share these with friends and family.

Learning center workshop allows a user on a learning center client to build learning center programs visually using the interface for the learning center client. Learning center runtime allows a user on a learning center client to run learning center programs.

Learning module generator allows a user on a learning center client to generate learning modules from learning center programs. Learning module engine allows a user on the learning center client to run learning modules and guides the user to build a learning center program. The learning module engine validates all known triggers and keeps parameters within a known range.

A user from a learning center client accesses learning center workshop through an interface. For example the interface is a web browser or a dedicated app located on a computing device such as a personal computer or a tablet. When learning is launched a user can build a project which is essentially a computer program. Learning center workshop allows a user to construct a project computer program and save it. The computer program can be run using learning center runtime .

Upon entering learning center workshop a user can elect to build a new computer program from scratch or open an existing computer program.

To build a computer program from scratch the user utilizes blocks of programming instructions represented visually as building blocks within learning center workshop . The tools provided within learning center workshop allow a user to create a scene that includes a background main objects and actors. Learning center workshop allows a user to add computer program logic to the actors and the background. The user acts by dragging and dropping visual blocks into code areas. The visual blocks snap into place to form logic sequences.

Learning center workshop saves the computer program and all its assets as the computer program is being built. For example learning center workshop saves the computer program in a persistent format so that the computer program can be loaded later. This can be done for example in a Javascript Object Notation JSON format Extensible Markup Language XML or some other structured syntax. The computer program file may be stored on learning center server and in addition or instead of stored on the learning center client used by the user.

The flying bird project illustrated within interface shown in can be stored in file using language blocks for the learning center. For example Table 3 below sets out contents for such a file.

A user can use learning center runtime shown in to run a computer program built in learning center workshop . For example the interface by which the user accesses learning center runtime is a web browser on a computing device such as a personal computer or a tablet or is an app running on a mobile phone or tablet computer. For example the user may iterate through refining a computer program by making modifications such as adding and removing logic changing the code blocks used and testing the computer program to see how the computer program runs.

Scripts are registered against specific event types e.g. program start key event mouse event . As illustrated by arrow an external trigger event results in a script that has been registered in event registrations list being added to a scheduler which is a list of running scripts. Run loop picks up a script to execute from scheduler . The scripts are executed in parallel by scheduler . Scheduler determines how to select the next script e.g. round robin priority queue time queue . The execution context is restored from a runtime stack specific to that script. The instruction is executed as a non blocking process.

For example within a project runner in a block a next script is fetched from the scheduler. In a block execution context is restored for the fetched script. In a block an instruction is run. In a block context is moved to a next instruction. As illustrated by arrow block and block are continued until there is a context switch. A context switches occurs for example when the script has executed a yield instruction a time slice expires user interrupts execution etc. When there is a context switch in a block execution context is saved and context is returned to block . If the end of the script has not been reached the script is retained in the scheduler . If the end of the script has been reached the script is removed from runtime stack and the list of running scripts within scheduler .

For example for learning center runtime scripts are written using Javascript. Javascript is a single threaded environment in a web browser. A sequence of instructions is executed sequentially until the sequence relinquishes control back to the web browser before other instruction sequences will execute. As a result multiple Javascript sequences cannot run at the same time.

For example the learning center represents instructions as blocks so that each block represents one instruction that executes atomically that is without being interrupted by another block. Each block must relinquish control back to the web browser in a timely fashion. Scheduler therefore maintains a context for each script sequence. Scheduler selects a script sequence switches to that script s context and executes a predetermined number of blocks for each turn. Scheduler then selects the next script sequence and repeats until all scheduled scripts have run theft turn. At this point scheduler relinquishes control back to the web browser. The web browser starts up another time slice where another script sequence is executed. As a result multiple scripts can be run at the same time.

In a block a project is loaded. In a block assets are iterated. In a block assets are fetched from assets storage . In a block paths to assets are resolved and rewritten. In a block optimization is performed. For example the optimization can include removing assets not used by a target as shown in a block . Likewise the optimization can include recompressing and or scaling assets for the target as shown in a block . Also the optimization can include native code generation as shown in a block .

Once a computer program project is complete a user can choose to create a lesson module based on the computer program. For example the user can choose a create lesson option in learning center workshop to activate learning module generator .

Learning module generator includes a parser that parses through the computer program that the user built and generates a task list for the lesson module. For example learning module generator reads through the computer program identifies all objects and identifies actions to recreate the computer program. Then different kinds of steps are generated based on the results of parsing the computer program. A list of ordered steps are generated where complex tasks are outlined and grouped together.

As shown in a drop down menu accessed by a user from the Tropical Bird label on the menu bar of user interface includes a selection to Create Lesson . As a result learning module generator shown in is invoked and generates a lesson module from the computer program shown in Table 3 for the flying bird project.

In a block learning module generator iterates through scripts. This is done for example to discover dependencies between messages and actors etc. as shown in block to sequence script steps by dependencies as shown in block and to determine cyclic dependencies and establish a preference for definitions as shown in block .

As represented by arrow learning module generator then generates a sequential list of steps . As illustrated by block a user can add notations to sequential list of steps . As illustrated by block a user can reorder steps within sequential list of steps .

Once the list or ordered steps are generated the user can customize the lesson module. For example the user can change the order of steps so that the reconstruction of the steps of computer program occurs in a different order than the steps as they originally appeared in the in the computer program when authored. Learning module generator is used to assure that dependencies between steps are accounted for.

For example learning module generator allows a user to add voice over in each step. The voice over is played back while the lesson module is being run within learning center runtime . Similarly learning module generator allows a user to add video in any step. The video is played back while the lesson module is being run within learning center runtime . Also learning module generator allows additional steps to be added in between the steps for the lesson module originally generated by learning module generator . For example text for the lesson module can be customized. When the user has completed modifications learning module generator saves the workflow as a lesson module.

Table 4 shows an example of computer program for a complex project lesson produced based on language blocks from the flying bird project set out in Table 3 

Learning module engine shown in is invoked when a user runs a lesson module. For example a user from a learning center client utilizes learning center workshop through an interface to invoke the lesson module. For example the interface is a web browser on a computing device such as a personal computer or a tablet. For example when learning is launched a user chooses to run the lesson module using a browser. Then learning module engine takes over and guides the user to complete the lesson within the lesson module.

For example learning module engine displays a lesson bar that shows the steps that the user must perform. The area of the screen that the user must work on is highlighted and in order to proceed the user must complete a current task. For example learning module engine provides the user with real time help such as a Hint Show Me button. Learning module engine also plays any voice over or video associated with the lesson module. Learning module engine also for example provides a user with an option to fast forward several steps in a larger task and an option to step backwards.

For example learning module engine while the user adds logic highlights the source and target areas of the task. If the user makes a mistake learning module engine takes the user back to a known state. Once the user has recreated the original program the lesson is complete. The user can then use learning module generator to modify the lesson module.

For example learning module engine can also operate in other modes. For example learning module engine can include a mode where a user can open a lesson module and learning module engine will animate the lesson module to a certain step. Similarly learning module engine can include a mode where a lesson module is run in slow motion continuously with voiceover. This mode can be useful for example when a user wants to generate a video.

From within a lesson runner a get instruction block fetches an instruction within the instructions loaded by lesson loader . The instruction may include for example lessons steps from lesson steps assets from assets and blocks from blocks used . Get instruction determines the type of instruction and passes it to the appropriate lesson step handler.

A determine type block within learning module engine sequentially handles instructions from lesson loader and determines instruction type.

For a plain note the message is displayed and or spoken. This is an informational message requiring either a timeout or user acknowledgement to continue. This is represented in where for a note learning module engine displays a message as represented by a block .

When a resource instruction is run the resources that are to be used when hints are turned on are highlighted. The lesson step instructions are displayed and or spoken with entered explanations from the lesson creator. A check is performed that the resource was placed in the correct place by checking the associated project data structures for the correct placement. This is represented in where for a resource instruction learning module engine displays a workshop window and highlights change as represented by a block . Learning module engine also validates settings as represented by a block .

A code block instruction when run highlights the block to be used when hints are turned on and shows where the block should be placed on the code canvas. The lesson step instructions are displayed and or spoken with entered explanations from the lesson creator. A check is made that the block was placed in the correct place by checking the associated project code data structures. If validation is not successful a message appears offering some hints. For example the hints might include such things as animating actions highlighting location on the display or masking location on the display.

Users are optionally allowed to proceed to the next step in which case the lesson runner performs the action on behalf of the user. If validation was successful the next lesson step is executed. This is represented in where for a code block instruction learning module engine displays code and highlight blocks as represented by a block . Learning module engine also validates programming blocks as represented by a block .

After an instruction is processed in a block a next instruction is obtained. The lesson proceeds until no more steps at which point the runner can offer additional activities or the user lesson creator can embed additional activities that can be done.

For example the Learning Center also allows the creation and running of puzzle type lessons with system validating success and failure type triggers.

That is a puzzle is an example of a special kind of lesson that has bunt in validation. For example the puzzle has a specific success criteria that the author defines such as Make the robot go to the green square. 

The author of a puzzle lesson module builds the project computer program using learning center workshop. When building the lesson modules the author uses two special blocks of code a success criteria block and a failure criteria block. The author uses the blocks to define success and failure and to indicate the consequences of success and failure. The author then uses learning module generator to generate a lesson module for the project.

When a user opens the project in a lesson running mode upon a user completing an action learning module engine will check whether the success or failure criteria are valid. Learning module engine will then execute the consequences of success or failure as appropriate. This is illustrated in .

For example the learning center allows a user to define activities that can be automatically validated by the learning runtime. For example a task is presented to the student to accomplish a goal such as to write code to move a golf ball into a hole. The student creates the code. In order to check whether the code accomplishes the task code blocks that the student has added can be checked to see that the code blocks are in the correct order. Alternatively a trigger methodology can be used to determine whether the task was accomplished.

For example a trigger is assigned to the objects that a user manipulates. The trigger is based on whether a criteria placed within the computing program has been satisfied. For example the objects are a ball and a hole. The triggers are hidden from the user. The triggers are code instructions that check for the criteria as delineated by parameters. If the parameters are satisfied the trigger is fired and the process that checks that the code can determine whether the user accomplished the task. For example a geometric criteria specifies that a ball must travel a certain distance. For example a hole trigger checks that the ball is within the bounds of the hole.

In addition other types of criteria can be used. For example a time based criteria indicates whether a task is completed within a specified amount of time. For example did a mouse finish a maze in under 8 seconds A code based criteria determines whether code used to accomplish a task is within predetermined parameters. For example was a lesson completed using under 8 code blocks and without using recursion Value based criteria determine whether a particular value was reached. For example was a score greater than 25 Event criteria determine whether a certain event criteria was received. For example was a message sent by one of the actors A physics based criteria indicates a physical property or phenomena occurred. For example did a cannon ball reach a velocity of at least 25 meters per second An external physical criteria indicates some real activity outside the program occur. For example did a sensor on a physical stage robot move 10 feet 

An activity monitor within lesson runner includes a timer module a resource monitor and an event monitor . Lesson runner performs a compare function with a step list . Step list includes steps resources used and blocks used . Each of steps may be an asset to add step a code to add step or a property to change step .

After a project author generates a lesson module within learning center server the author can make the lesson module available to other users of learning center server . For example other users are charged a fee for using a lesson module made available by an author and the author receives a portion of the fee based for example on the number of other users that use the lesson module.

For example an author is reimbursed based on tracking the number of times another user views or completes a lesson authored by the author. For example an author gets paid 2 for every 1000 lesson views inside a paid course authored by the author. Alternatively an author can sell a lesson for a flat fee.

The foregoing discussion discloses and describes merely exemplary methods and implementations. As will be understood by those familiar with the art the disclosed subject matter may be embodied in other specific forms without departing from the spirit or characteristics thereof. Accordingly the present disclosure is intended to be illustrative but not limiting of the scope of the invention which is set forth in the following claims.

