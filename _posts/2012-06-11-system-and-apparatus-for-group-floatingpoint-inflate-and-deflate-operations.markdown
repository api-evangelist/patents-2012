---

title: System and apparatus for group floating-point inflate and deflate operations
abstract: Systems and apparatuses are presented relating a programmable processor comprising an execution unit that is operable to decode and execute instructions received from an instruction path and partition data stored in registers in the register file into multiple data elements, the execution unit capable of executing group data handling operations that re-arrange data elements in different ways in response to data handling instructions, the execution unit further capable of executing a plurality of different group floating-point and group integer arithmetic operations that each arithmetically operates on the multiple data elements stored in registers in the register file to produce a catenated result that is returned to a register in the register file, wherein the catenated result comprises a plurality of individual results.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08769248&OS=08769248&RS=08769248
owner: Microunity Systems Engineering, Inc.
number: 08769248
owner_city: Sunnyvale
owner_country: US
publication_date: 20120611
---
This application is a continuation of U.S. patent application Ser. No. 13 310 508 filed Dec. 2 2011 which is a continuation of U.S. patent application Ser. No. 11 878 803 filed Jul. 27 2007 now U.S. Pat. No. 8 117 426 which is a continuation of U.S. patent application Ser. No. 10 436 340 filed May 13 2003 now U.S. Pat. No. 7 516 308 which is a continuation of U.S. patent application Ser. No. 09 534 745 filed Mar. 24 2000 now U.S. Pat. No. 6 643 765 which is a continuation of U.S. patent application Ser. No. 09 382 402 filed Aug. 24 1999 now U.S. Pat. No. 6 295 599 and which is a continuation in part of U.S. patent application Ser. No. 09 169 963 filed Oct. 13 1998 now U.S. Pat. No. 6 006 318 which is a continuation of U.S. patent application Ser. No. 08 754 827 filed Nov. 22 1996 now U.S. Pat. No. 5 822 603 which is a division of U.S. patent application Ser. No. 08 516 036 filed Aug. 16 1995 now U.S. Pat. No. 5 742 840.

This application is a continuation of U.S. patent application Ser. No. 13 310 508 filed Dec. 2 2011 which is a continuation of U.S. patent application Ser. No. 11 878 803 filed Jul. 27 2007 now U.S. Pat. No. 8 117 426 which is a continuation of U.S. patent application Ser. No. 11 511 466 now abandoned filed Aug. 29 2006 which is a continuation of U.S. patent application Ser. No. 10 646 787 filed Aug. 25 2003 now U.S. Pat. No. 7 216 217 which is a continuation of U.S. patent application Ser. No. 09 922 319 filed Aug. 2 2001 now U.S. Pat. No. 6 725 356 which is a continuation of U.S. patent application Ser. No. 09 382 402 filed Aug. 24 1999 now U.S. Pat. No. 6 295 599 which claims the benefit of priority to Provisional Application No. 60 097 635 filed Aug. 24 1998 and is a continuation in part of U.S. patent application Ser. No. 09 169 963 filed Oct. 13 1998 now U.S. Pat. No. 6 006 318 which is a continuation of U.S. patent application Ser. No. 08 754 827 filed Nov. 22 1996 now U.S. Pat. No. 5 822 603 which is a divisional of U.S. patent application Ser. No. 08 516 036 filed Aug. 16 1995 now U.S. Pat. No. 5 742 840.

The contents of all the U.S. patent applications and provisional applications listed above are hereby incorporated by reference including their appendices in their entirety.

The present invention relates to general purpose processor architectures and particularly relates to general purpose processor architectures capable of executing group operations.

The performance level of a processor and particularly a general purpose processor can be estimated from the multiple of a plurality of interdependent factors clock rate gates per clock number of operands operand and data path width and operand and data path partitioning. Clock rate is largely influenced by the choice of circuit and logic technology but is also influenced by the number of gates per clock. Gates per clock is how many gates in a pipeline may change state in a single clock cycle. This can be reduced by inserting latches into the data path when the number of gates between latches is reduced a higher clock is possible. However the additional latches produce a longer pipeline length and thus come at a cost of increased instruction latency. The number of operands is straightforward for example by adding with carry save techniques three values may be added together with little more delay than is required for adding two values. Operand and data path width defines how much data can be processed at once wider data paths can perform more complex functions but generally this comes at a higher implementation cost. Operand and data path partitioning refers to the efficient use of the data path as width is increased with the objective of maintaining substantially peak usage.

Embodiments of the invention pertain to systems and methods for enhancing the utilization of a general purpose processor by adding classes of instructions. These classes of instructions use the contents of general purpose registers as data path sources partition the operands into symbols of a specified size perform operations in parallel catenate the results and place the catenated results into a general purpose register. Some embodiments of the invention relate to a general purpose microprocessor which has been optimized for processing and transmitting media data streams through significant parallelism.

Some embodiments of the present invention provide a system and method for improving the performance of general purpose processors by including the capability to execute group operations involving multiple floating point operands. In one embodiment a programmable media processor comprises a virtual memory addressing unit a data path a register file comprising a plurality of registers coupled to the data path and an execution unit coupled to the data path capable of executing group floating point operations in which multiple floating point operations stored in partitioned fields of one or more of the plurality of registers are operated on to produce catenated results. The group floating point operations may involve operating on at least two of the multiple floating point operands in parallel. The catenated results may be returned to a register and general purpose registers may used as operand and result registers for the floating point operations. In some embodiments the execution unit may also be capable of performing group floating point operations on floating point data of more than one precision. In some embodiments the group floating point operations may include group add group subtract group compare group multiply and group divide arithmetic operations that operate on catenated floating point data. In some embodiments the group floating point operations may include group multiply add group scale add and group set operations that operate on catenated floating point data.

In one embodiment the execution unit is also capable of executing group integer instructions involving multiple integer operands stored in partitioned fields of registers. The group integer operations may involve operating on at least two of the multiple integer operands in parallel. The group integer operations may include group add group subtract group compare and group multiply arithmetic operations that operate on catenated integer data.

In one embodiment the execution unit is capable of performing group data handling operations including operations that copy operations that shift operations that rearrange and operations that resize catenated integer data stored in a register and return catenated results. The execution unit may also be configurable to perform group data handling operations on integer data having a symbol width of 8 bits group data handling operations on integer data having a symbol width of 16 bits and group data handling operations on integer data having a symbol width of 32 bits. In one embodiment the operations are controlled by values in a register operand. In one embodiment the operations are controlled by values in the instruction.

In one embodiment the multi precision execution unit is capable of executing a Galois field instruction operation.

In one embodiment the multi precision execution unit is configurable to execute a plurality of instruction streams in parallel from a plurality of threads and the programmable media processor further comprises a register file associated with each thread executing in parallel on the multi precision execution unit to support processing of the plurality of threads. In some embodiments the multi precision execution unit executes instructions from the plurality of instruction streams in a round robin manner. In some embodiments the processor ensures only one thread from the plurality of threads can handle an exception at any given time.

Some embodiments of the present invention provide a multiplier array that is fully used for high precision arithmetic but is only partly used for other lower precision operations. This can be accomplished by extracting the high order portion of the multiplier product or sum of products adjusted by a dynamic shift amount from a general register or an adjustment specified as part of the instruction and rounded by a control value from a register or instruction portion. The rounding may be any of several types including round to nearest even toward zero floor or ceiling. Overflows are typically handled by limiting the result to the largest and smallest values that can be accurately represented in the output result.

When an extract is controlled by a register the size of the result can be specified allowing rounding and limiting to a smaller number of bits than can fit in the result. This permits the result to be scaled for use in subsequent operations without concern of overflow or rounding. As a result performance is enhanced. In those instances where the extract is controlled by a register a single register value defines the size of the operands the shift amount and size of the result and the rounding control. By placing such control information in a single register the size of the instruction is reduced over the number of bits that such an instruction would otherwise require again improving performance and enhancing processor flexibility. Exemplary instructions are Ensemble Convolve Extract Ensemble Multiply Extract Ensemble Multiply Add Extract and Ensemble Scale Add Extract. With particular regard to the Ensemble Scale Add Extract Instruction the extract control information is combined in a register with two values used as scalar multipliers to the contents of two vector multiplicands. This combination reduces the number of registers otherwise required thus reducing the number of bits required for the instruction.

In one embodiment the processor performs load and store instructions operable to move values between registers and memory. In one embodiment the processor performs both instructions that verify alignment of memory operands and instructions that permit memory operands to be unaligned. In one embodiment the processor performs store multiplex instructions operable to move to memory a portion of data contents controlled by a corresponding mask contents. In one embodiment this masked storage operation is performed by indivisibly reading modifying writing a memory operand.

In one embodiment all processor memory and interface resources are directly accessible to high level language programs. In one embodiment assembler codes and high level language formats are specified to access enhanced instructions. In one embodiment interface and system state is memory mapped so that it can be manipulated by compiled code. In one embodiment software libraries provide other operations required by the ANSI IEEE floating point standard. In one embodiment software conventions are employed at software module boundaries in order to permit the combination of separately compiled code and to provide standard interfaces between application library and system software. In one embodiment instruction scheduling is performed by a compiler.

In various embodiments of the invention a computer processor architecture referred to here as MicroUnity s Zeus Architecture is presented. MicroUnity s Zeus Architecture describes general purpose processor memory and interface subsystems organized to operate at the enormously high bandwidth rates required for broadband applications.

The Zeus processor performs integer floating point signal processing and non linear operations such as Galois field table lookup and bit switching on data sizes from 1 bit to 128 bits. Group or SIMD single instruction multiple data operations sustain external operand bandwidth rates up to 512 bits i.e. up to four 128 bit operand groups per instruction even on data items of small size. The processor performs ensemble operations such as convolution that maintain full intermediate precision with aggregate internal operand bandwidth rates up to 20 000 bits per instruction. The processor performs wide operations such as crossbar switch matrix multiply and table lookup that use caches embedded in the execution units themselves to extend operands to as much as 32768 bits. All instructions produce at most a single 128 bit register result source at most three 128 bit registers and are free of side effects such as the setting of condition codes and flags. The instruction set design carries the concept of streamlining beyond Reduced Instruction Set Computer RISC architectures to simplify implementations that issue several instructions per machine cycle.

The Zeus memory subsystem provides 64 bit virtual and physical addressing for UNIX Mach and other advanced OS environments. Separate address instructions enable the division of the processor into decoupled access and execution units to reduce the effective latency of memory to the pipeline. The Zeus cache supplies the high data and instruction issue rates of the processor and supports coherency primitives for scaleable multiprocessors. The memory subsystem includes mechanisms for sustaining high data rates not only in block transfer modes but also in non unit stride and scatterred access patterns.

The Zeus interface subsystem is designed to match industry standard Socket 7 protocols and pin outs. In this way Zeus can make use of the immense infrastructure of the PC for building low cost systems. The interface subsystem is modular and can be replaced with appropriate protocols and pin outs for lower cost and higher performance systems.

The goal of the Zeus architecture is to integrate these processor memory and interface capabilities with optimal simplicity and generality. From the software perspective the entire machine state consists of a program counter a single bank of 64 general purpose 128 bit registers and a linear byte addressed shared memory space with mapped interface registers. All interrupts and exceptions are precise and occur with low overhead.

Examples discussed herein are for Zeus software and hardware developers alike and defines the interface at which their designs must meet. Zeus pursues the most efficient tradeoffs between hardware and software complexity by making all processor memory and interface resources directly accessible to high level language programs.

To ensure that Zeus systems may freely interchange data user level programs system level programs and interface devices the Zeus system architecture reaches above the processor level architecture.

Additional devices and interfaces not covered by this standard may be added in specified regions of the physical memory space provided that system reset places these devices and interfaces in an inactive state that does not interfere with the operation of software that runs in any conformant system. The software interface requirements of any such additional devices and interfaces must be made as widely available as this architecture specification.

Nothing in this specification should be construed to limit the implementation choices of the conforming system beyond the specific requirements stated herein. In particular a computer system may conform to the Zeus System Architecture while employing any number of components dissipate any amount of heat require any special environmental facilities or be of any physical size.

The ordering of bits in this document is always little endian regardless of the ordering of bytes within larger data structures. Thus the least significant bit of a data structure is always labeled 0 zero and the most significant bit is labeled as the data structure size in bits minus one.

Zeus memory is an array of 2bytes without a specified byte ordering which is physically distributed among various components.

Larger data structures are constructed from the concatenation of bytes in either little endian or big endian byte ordering. A memory access of a data structure of size s at address i is formed from memory bytes at addresses i through i s 1. Unless otherwise specified there is no specific requirement of alignment it is not generally required that i be a multiple of s. Aligned accesses are preferred whenever possible however as they will often require one fewer processor or memory clock cycle than unaligned accesses.

Zeus memory is byte addressed using either little endian or big endian byte ordering. For consistency with the bit ordering and for compatibility with x86 processors Zeus uses little endian byte ordering when an ordering must be selected. Zeus load and store instructions are available for both little endian and big endian byte ordering. The selection of byte ordering is dynamic so that little endian and big endian processes and even data structures within a process can be intermixed on the processor.

Zeus memory including memory mapped registers must conform to the following requirements regarding side effects of read or load operations 

A memory read must have no side effects on the contents of the addressed memory nor on the contents of any other memory.

Zeus memory including memory mapped registers must conform to the following requirements regarding side effects of read or load operations 

A memory write must affect the contents of the addressed memory so that a memory read of the addressed memory returns the value written and so that a memory read of a portion of the addressed memory returns the appropriate portion of the value written.

A memory write may affect or cause side effects on the contents of memory not addressed by the write operation however a second memory write of the same value to the same address must have no side effects on any memory memory write operations must be idempotent.

Zeus store instructions that are weakly ordered may have side effects on the contents of memory not addressed by the store itself subsequent load instructions which are also weakly ordered mayor may not return values which reflect the side effects.

Zeus provides eight byte 64 bit virtual and physical address sizes and eight byte 64 bit and sixteen byte 128 bit data path sizes and uses fixed length four byte 32 bit instructions. Arithmetic is performed on two s complement or unsigned binary and ANSI IEEE standard 754 1985 conforming binary floating point number representations.

Zeus s floating point formats are designed to satisfy ANSI IEEE standard 754 1985 Binary Floating point Arithmetic. Standard 754 leaves certain aspects to the discretion of implementers additional precision formats encoding of quiet and signaling NaN values details of production and propagation of quiet NaN values. These aspects are detailed below.

Zeus adds additional half precision and quad precision formats to standard 754 s single precision and double precision formats. Zeus s double precision satisfies standard 754 s precision requirements for a single extended format and Zeus s quad precision satisfies standard 754 s precision requirements for a double extended format.

Each precision format employs fields labeled s sign e exponent and f fraction to encode values that are 1 NaN quiet and signaling 2 infinities 1 3 normalized numbers 1 2 1.f denormarlized numbers 1 2 0.f and 5 zero 1 0.

Quiet NaN values are denoted by any sign bit value an exponent field of all one bits and a non zero fraction with the most significant bit set. Quiet NaN values generated by default exception handling of standard operations have a zero sign bit an exponent field of all one bits a fraction field with the most significant bit set and all other bits cleared.

Signaling NaN values are denoted by any sign bit value an exponent field of all one bits and a non zero fraction with the most significant bit cleared.

Infinite values are denoted by any sign bit value an exponent field of all one bits and a zero fraction field.

Normalized number values are denoted by any sign bit value an exponent field that is not all one bits or all zero bits and any fraction field value. The numeric value encoded is 1 2 1.f The bias is equal the value resulting from setting all but the most significant bit of the exponent field half 15 single 127 double 1023 and quad 16383.

Denormalized number values are denoted by any sign bit value an exponent field that is all zero bits and a non zero fraction field value. The numeric value encoded is 1 2 0.f .

Zero values are denoted by any sign bit value and exponent field that is all zero bits and a fraction field that is all zero bits. The numeric value encoded is 1 0. The distinction between 0 and 0 is significant in some operations.

Zeus half precision uses a format similar to standard 754 s requirements reduced to a 16 bit overall format. The format contains sufficient precision and exponent range to hold a 12 bit signed integer.

Zeus quad precision satisfies standard 754 s requirements for double extended but has additional fraction precision to use 128 bits.

MicroUnity s Zeus processor provides the general purpose high bandwidth computation capability of the Zeus system. Zeus includes high bandwidth data paths register files and a memory hierarchy. Zeus s memory hierarchy includes on chip instruction and data memories instruction and data caches a virtual memory facility and interfaces to external devices. Zeus s interfaces in the initial implementation are solely the Super Socket 7 bus but other implementations may have different or additional interfaces.

The Zeus architecture defines a compatible framework for a family of implementations with a range of capabilities. The following implementation defined parameters are used in the rest of the document in boldface. The value indicated is for MicroUnity s first Zeus implementation.

Instructions are specified to Zeus assemblers and other code tools assemblers in the syntax of an instruction mnemonic operation code then optionally white space blanks or tabs followed by a list of operands.

The instruction mnemonics listed in this specification are in upper case capital letters assemblers accept either upper case or lower case letters in the instruction mnemonics. In this specification instruction mnemonics contain periods . to separate elements to make them easier to understand assemblers ignore periods within instruction mnemonics. The instruction mnemonics are designed to be parsed uniquely without the separating periods.

If the instruction produces a register result this operand is listed first. Following this operand if there are one or more source operands is a separator which may be a comma equal or at sign . The equal separates the result operand from the source operands and may optionally be expressed as a comma in assembler code. The at sign indicates that the result operand is also a source operand and may optionally be expressed as a comma in assembler code. If the instruction specification has an equal sign an at sign in assembler code indicates that the result operand should be repeated as the first source operand for example A.ADD.I r4 5 is equivalent to A.ADD.I r4 r4 5 . Commas always separate the remaining source operands.

The result and source operands are case sensitive upper case and lower case letters are distinct. Register operands are specified by the names r0 or r00 through r63 a lower case r immediately followed by a one or two digit number from 0 to 63 or by the special designations of lp for r0 dp for r1 fp for r62 and sp for r63. Integer valued operands are specified by an optional sign or followed by a number and assemblers generally accept a variety of integer valued expressions.

A Zeus instruction is specifically defined as a four byte structure with the little endian ordering shown below. It is different from the quadlet defined above because the placement of instructions into memory must be independent of the byte ordering used for data structures. Instructions must be aligned on four byte boundaries in the diagram below i must be a multiple of 4.

A Zeus gateway is specifically defined as an 8 byte structure with the little endian ordering shown below. A gateway contains a code address used to securely invoke a system call or procedure at a higher privilege level. Gateways are marked by protection information specified in the TB. Gateways must be aligned on 8 byte boundaries in the diagram below i must be a multiple of 8.

The virtual memory system can be used to designate a region of memory as containing gateways. Other data may be placed within the gateway region provided that if an attempt is made to use the additional data as a gateway that security cannot be violated. For example 64 bit data or stack pointers which are aligned to at least 4 bytes and are in little endian byte order have p1 0 so that the privilege level cannot be raised by attempting to use the additional data as a gateway.

The user state consists of hardware data structures that are accessible to all conventional compiled code. The Zeus user state is designed to be as regular as possible and consists only of the general registers the program counter and virtual memory. There are no specialized registers for condition codes operating modes rounding modes integer multiply divide or floating point values.

Zeus user state includes 64 general registers. All are identical there is no dedicated zero valued register and there are no dedicated floating point registers.

Some Zeus instructions have 64 bit register operands. These operands are sign extended to 128 bits when written to the register file and the low order 64 bits are chosen when read from the register file.

The program counter contains the address of the currently executing instruction. This register is implicitly manipulated by branch instructions and read by branch instructions that save a return address in a general register.

The privilege level register contains the privilege level of the currently executing instruction. This register is implicitly manipulated by branch gateway and branch down instructions and read by branch gateway instructions that save a return address in a general register.

The program counter and privilege level may be packed into a single octlet. This combined data structure is saved by the Branch Gateway instruction and restored by the Branch Down instruction.

The system state consists of the facilities not normally used by conventional compiled code. These facilities provide mechanisms to execute such code in a fully virtual environment. All system state is memory mapped so that it can be manipulated by compiled code.

Zeus provides load and store instructions to move data between memory and the registers branch instructions to compare the contents of registers and to transfer control from one code address to another and arithmetic operations to perform computation on the contents of registers returning the result to registers.

The load and store instructions move data between memory and the registers. When loading data from memory into a register values are zero extended or sign extended to fill the register. When storing data from a register into memory values are truncated on the left to fit the specified memory region.

Load and store instructions that specify a memory region of more than one byte may use either little endian or big endian byte ordering the size and ordering are explicitly specified in the instruction. Regions larger than one byte may be either aligned to addresses that are an even multiple of the size of the region or of unspecified alignment alignment checking is also explicitly specified in the instruction.

Load and store instructions specify memory addresses as the sum of a base general register and the product of the size of the memory region and either an immediate value or another general register. Scaling maximizes the memory space which can be reached by immediate offsets from a single base general register and assists in generating memory addresses within iterative loops. Alignment of the address can be reduced to checking the alignment of the first general register.

The load and store instructions are used for fixed point data as well as floating point and digital signal processing data Zeus has a single bank of registers for all data types.

Swap instructions provide multithread and multiprocessor synchronization using indivisible operations add swap compare swap multiplex swap and double compare swap. A store multiplex operation provides the ability to indivisibly write to a portion of an octlet. These instructions always operate on aligned octlet data using either little endian or big endian byte ordering.

The fixed point compare and branch instructions provide all arithmetic tests for equality and inequality of signed and unsigned fixed point values. Tests are performed either between two operands contained in general registers or on the bitwise and of two operands. Depending on the result of the compare either a branch is taken or not taken. A taken branch causes an immediate transfer of the program counter to the target of the branch specified by a 12 bit signed offset from the location of the branch instruction. A non taken branch causes no transfer execution continues with the following instruction.

Other branch instructions provide for unconditional transfer of control to addresses too distant to be reached by a 12 bit offset and to transfer to a target while placing the location following the branch into a register. The branch through gateway instruction provides a secure means to access code at a higher privilege level in a form similar to a normal procedure call.

A subset of general fixed point arithmetic operations is available as addressing operations. These include add subtract Boolean and simple shift operations. These addressing operations may be performed at a point in the Zeus processor pipeline so that they may be completed prior to or in conjunction with the execution of load and store operations in a superspring pipeline in which other arithmetic operations are deferred until the completion of load and store operations.

Many of the operations used for Digital Signal Processing DSP which are described in greater detail below are also used for performing simple scalar operations. These operations perform arithmetic operations on values of 8 16 32 64 or 128 bit sizes which are right aligned in registers. These execution operations include the add subtract boolean and simple shift operations which are also available as addressing operations but further extend the available set to include three operand add subtract three operand boolean dynamic shifts and bit field operations.

Zeus provides all the facilities mandated and recommended by ANSI IEEE standard 754 1985 Binary Floating point Arithmetic with the use of supporting software.

The floating point compare and branch instructions provide all the comparison types required and suggested by the IEEE floating point standard. These floating point comparisons augment the usual types of numeric value comparisons with special handling for NaN not a number values. A NaN value compares as unordered with respect to any other value even that of an identical NaN value.

Zeus floating point compare branch instructions do not generate an exception on comparisons involving quiet or signaling NaN values. If such exceptions are desired they can be obtained by combining the use of a floating point compare set instruction with either a floating point compare branch instruction on the floating point operands or a fixed point compare branch on the set result.

Because the less and greater relations are anti commutative one of each relation that differs from another only by the replacement of an L with a G in the code can be removed by reversing the order of the operands and using the other code. Thus an L relation can be used in place of a G relation by swapping the operands to the compare branch or compare set instruction.

No instructions are provided that branch when the values are unordered. To accomplish such an operation use the reverse condition to branch over an immediately following unconditional branch or in the case of an if then else clause reverse the clauses and use the reverse condition.

The E relation can be used to determine the unordered condition of a single operand by comparing the operand with itself.

The compare set floating point instructions provide all the comparison types supported as branch instructions. Zeus compare set floating point instructions may optionally generate an exception on comparisons involving quiet or signaling NaNs.

The basic operations supported in hardware are floating point add subtract multiply divide square root and conversions among floating point formats and between floating point and binary integer formats.

The operations explicitly specify the precision of the operation and round the result or check that the result is exact to the specified precision at the conclusion of each operation. Each of the basic operations splits operand registers into symbols of the specified precision and performs the same operation on corresponding symbols.

In addition to the basic operations Zeus performs a variety of operations in which one or more products are summed to each other and or to an additional operand. The instructions include a fused multiply add E.MUL.ADD.F convolve E.CON.F matrix multiply E.MUL.MAT.F and scale add E.SCAL.ADD.F .

The results of these operations are computed as if the multiplies are performed to infinite precision added as if in infinite precision then rounded only once. Consequently these operations perform these operations with no rounding of intermediate results that would have limited the accuracy of the result.

ANSI IEEE standard 754 1985 specifies that operations involving a signaling NaN or invalid operation shall if no trap occurs and if a floating point result is to be delivered deliver a quiet NaN as its result. However it fails to specify what quiet NaN value to deliver.

Zeus operations that produce a floating point result and do not trap on invalid operations propagate signaling NaN values from operands to results changing the signaling NaN values to quiet NaN values by setting the most significant fraction bit and leaving the remaining bits unchanged. Other causes of invalid operations produce the default quiet NaN value where the sign bit is zero the exponent field is all one bits the most significant fraction bit is set and the remaing fraction bits are zero bits. For Zeus operations that produce multiple results catenated together signaling NaN propagation or quiet NaN production is handled separately and independently for each result symbol.

ANSI IEEE standard 754 1985 specifies that quiet NaN values should be propagated from operand to result by the basic operations. However it fails to specify which of several quiet NaN values to propagate when more than one operand is a quiet NaN. In addition the standard does not clearly specify how quiet NaN should be propagated for the multiple operation instructions provided in Zeus. The standard does not specify the quiet NaN produced as a result of an operand being a signaling NaN when invalid operation exceptions are handled by default. The standard leaves unspecified how quiet and signaling NaN values are propagated though format conversions and the absolute value negate and copy operations. This section specifies these aspects left unspecified by the standard.

First of all for Zeus operations that produce multiple results catenated together quiet and signaling NaN propagation is handled separately and independently for each result symbol. A quiet or signaling NaN value in a single symbol of an operand causes only those result symbols that are dependent on that operand symbol s value to be propagated as that quiet NaN. Multiple quiet or signaling NaN values in symbols of an operand which influence separate symbols of the result are propagated independently of each other. Any signaling NaN that is propagated has the high order fraction bit set to convert it to a quiet NaN.

For Zeus operations in which multiple symbols among operands upon which a result symbol is dependent are quiet or signaling NaNs a priority Rule will determine which NaN is propagated. Priority shall be given to the operand that is specified by a register definition at a lower numbered little endian bit position within the instruction rb has priority over rc which has priority over rd . In the case of operands which are catenated from two registers priority shall be assigned based on the register which has highest priority lower numbered bit position within the instruction . In the case of tie as when the E.SCAL.ADD scaling operand has two corresponding NaN values or when a E.MUL.CF operand has NaN values for both real and imaginary components of a value the value which is located at a lower numbered little endian bit position within the operand is to receive priority. The identification of a NaN as quiet or signaling shall not confer any priority for selection only the operand position though a signaling NaN will cause an invalid operand exception.

The sign bit of NaN values propagated shall be complemented if the instruction subtracts or negates the corresponding operand or but not and multiplies it by or divides it by or divides it into an operand which has the sign bit set even if that operand is another NaN. If a NaN is both subtracted and multiplied by a negative value the sign bit shall be propagated unchanged.

For Zeus operations that convert between two floating point formats INFLATE and DEFLATE NaN values are propagated by preserving the sign and the most significant fraction bits except that the most significant bit of a signalling NaN is set and for DEFLATE the least significant fraction bit preserved is combined via a logical or of all fraction bits not preserved. All additional fraction bits for INFLATE are set to zero.

For Zeus operations that convert from a floating point format to a fixed point format SINK NaN values produce zero values maximum likelihood estimate . Infinity values produce the largest representable positive or negative fixed point value that fits in the destination field. When exception traps are enabled NaN or Infinity values producE a floating point exception. Underflows do not occur in the SINK operation they produce 1 0 or 1 depending on rounding controls.

For absolute value negate or copy operations NaN values are propagated with the sign bit cleared complemented or copied respectively. Signalling NaN values cause the Invalid operation exception propagating a quieted NaN in corresponding symbol locations default or an exception as specified by the instruction.

Referring to the following functions are defined for use within the detailed instruction definitions in the following section. In these functions an internal format represents infinite precision floating point values as a four element structure consisting of 1 s sign bit 0 for positive 1 for negative 2 t type NORM ZERO SNAN QNAN INFINITY 3 e exponent and 4 f fraction . The mathematical interpretation of a normal value places the binary point at the units of the fraction adjusted by the exponent 1 2 f. The function F converts a packed IEEE floating point value into internal format. The function PackF converts an internal format back into IEEE floating point format with rounding and exception control.

The Zeus processor provides a set of operations that maintain the fullest possible use of 128 bit data paths when operating on lower precision fixed point or floating point vector values. These operations are useful for several application areas including digital signal processing image processing and synthetic graphics. The basic goal of these operations is to accelerate the performance of algorithms that exhibit the following characteristics 

The operands and intermediate results are fixed point values represented in no greater than 64 bit precision. For floating point arithmetic operands and intermediate results are of 16 32 or 64 bit precision.

The fixed point arithmetic operations include add subtract multiply divide shifts and set on compare.

The use of fixed point arithmetic permits various forms of operation reordering that are not permitted in floating point arithmetic. Specifically commutativity and associativity and distribution identities can be used to reorder operations. Compilers can evaluate operations to determine what intermediate precision is required to get the specified arithmetic result.

Zeus supports several levels of precision as well as operations to convert between these different levels. These precision levels are always powers of two and are explicitly specified in the operation code.

When specified add subtract and shift operations may cause a fixed point arithmetic exception to occur on resulting conditions such as signed or unsigned overflow. The fixed point arithmetic exception may also be invoked upon a signed or unsigned comparison.

The algorithms are or can be expressed as operations on sequentially ordered items in memory. Scatter gather memory access or sparse matrix techniques are not required.

Where an index variable is used with a multiplier such multipliers must be powers of two. When the index is of the form nx k the value of n must be a power of two and the values referenced should have k include the majority of values in the range 0..n 1. A negative multiplier may also be used.

The operations performed on these sequentially ordered items are identical and independent. Conditional operations are either rewritten to use Boolean variables or masking or the compiler is permitted to convert the code into such a form.

The characteristics of these algorithms include sequential access to data which permit the use of the normal load and store operations to reference the data. Octlet and hexlet loads and stores reference several sequential items of data the number depending on the operand precision.

The discussion of these operations is independent of byte ordering though the ordering of bit fields within octlets and hexlets must be consistent with the ordering used for bytes. Specifically if big endian byte ordering is used for the loads and stores the figures below should assume that index values increase from left to right and for little endian byte ordering the index values increase from right to left. For this reason the figures indicate different index values with different shades rather than numbering.

When an index of the nx k form is used in array operands where n is a power of 2 data memory sequentially loaded contains elements useful for separate operands. The shuffle instruction divides a triclet of data up into two hexlets with alternate bit fields of the source triclet grouped together into the two results. An immediate field h in the instruction specifies which of the two regrouped hexlets to select for the result. For example two X.SHUFFLE.256 rd rc rb 32 128 h operations rearrange the source triclet c b into two hexlets as in .

In the shuffle operation two hexlet registers specify the source triclet and one of the two result hexlets are specified as hexlet register.

The example above directly applies to the case where n is 2. When n is larger shuffle operations can be used to further subdivide the sequential stream. For example when n is 4 we need to deal out 4 sets of doublet operands as shown in An example of the use of a four way deal is a digital signal processing application such as conversion of color to monochrome .

When an array result of computation is accessed with an index of the form nx k for n a power of 2 the reverse of the deal operation needs to be performed on vectors of results to interleave them for storage in sequential order. The shuffle operation interleaves the bit fields of two octlets of results into a single hex let. For example a X.SHUFFLE.16 operation combines two octlets of doublet fields into a hexlet as shown in .

For larger values of n a series of shuffle operations can be used to combine additional sets of fields similarly to the mechanism used for the deal operations. For example when n is 4 we need to shuffle up 4 sets of doublet operands as shown in An example of the use of a four way shuffle is a digital signal processing application such as conversion of monochrome to color .

When the index of a source array operand or a destination array result is negated or in other words if of the form nx k where n is negative the elements of the array must be arranged in reverse order. The swizzle operation can reverse the order of the bit fields in a hexlet. For example a X. SWIZZLE rd rc 127 112 operation reverses the doublets within a hexlet as shown in .

In some cases it is desirable to use a group instruction in which one or more operands is a single value not an array. The swizzle operation can also copy operands to multiple locations within a hexlet. For example a X.SWIZZLE 15 0 operation copies the low order 16 bits to each double within a hexlet.

Variations of the deal and shuffle operations are also useful for converting from one precision to another. This may be required if one operand is represented in a different precision than another operand or the result or if computation must be performed with intermediate precision greater than that of the operands such as when using an integer multiply.

When converting from a higher precision to a lower precision specifically when halving the precision of a hexlet of bit fields half of the data must be discarded and the bit fields packed together. The compress operation is a variant of the deal operation in which the operand is a hex let and the result is an octlet. An arbitrary half sized sub field of each bit field can be selected to appear in the result. For example a selection of bits .. of each quadlet in a hexlet is performed by the X.COMPRESS rd rc 16 4 operation as shown in .

When converting from lower precision to higher precision specifically when doubling the precision of an octlet of bit fields one of several techniques can be used either multiply expand or shuffle. Each has certain useful properties. In the discussion below m is the precision of the source operand.

The multiply operation described in detail below automatically doubles the precision of the result so multiplication by a constant vector will simultaneously double the precision of the operand and multiply by a constant that can be represented in m bits.

An operand can be doubled in precision and shifted left with the expand operation which is essentially the reverse of the compress operation. For example the X.EXPAND rd rc 16 4 expands from 16 bits to 32 and shifts 4 bits left as shown in .

The shuffle operation can double the precision of an operand and multiply it by 1 unsigned only 2or 2 by specifying the sources of the shuffle operation to be a zeroed register and the source operand the source operand and zero or both to be the source operand. When multiplying by 2m a constant can be freely added to the source operand by specifying the constant as the right operand to the shuffle.

The characteristics of the algorithms that affect the arithmetic operations most directly are low precision arithmetic and vectorizable operations. The fixed point arithmetic operations provided are most of the functions provided in the standard integer unit except for those. That check conditions. These functions include add subtract bitwise Boolean operations shift set on condition and multiply in forms that take packed sets of bit fields of a specified size as operands. The floating point arithmetic operations provided are as complete as the scalar floating point arithmetic set. The result is generally a packed set of bit fields of the same size as the operands except that the fixed point multiply function intrinsically doubles the precision of the bit field.

Conditional operations are provided only in the sense that the set on condition operations can be used to construct bit masks that can select between alternate vector expressions using the bitwise Boolean operations. All instructions operate over the entire octlet or hex let operands and produce a hex let result. The sizes of the bit fields supported are always powers of two.

Zeus provides a general software solution to the most common operations required or Galois Field arithmetic. The instructions provided include a polynomial multiply with the polynomial specified as one register operand. This instruction can be used to perform CRC generation and checking Reed Solomon code generation and checking and spread spectrum encoding and decoding.

The following section describes software conventions that are to be employed at software module boundaries in order to permit the combination of separately compiled code and to provide standard interfaces between application library and system software. Register usage and procedure call conventions may be modified simplified or optimized when a single compilation encloses procedures within a compilation unit so that the procedures have no external interfaces. For example internal procedures may permit a greater number of register passed parameters or have registers allocated to avoid the need to save registers at procedure boundaries or may use a single stack or data pointer allocation to suffice for more than one level of procedure call.

All Zeus registers are identical and general purpose there is no dedicated zero valued register and no dedicated floating point registers. However some procedure call oriented instructions imply usage of registers zero 0 and one 1 in a manner consistent with the conventions described below. By software convention the non specific general registers are used in more specific ways.

At a procedure call boundary registers are saved either by the caller or callee procedure which provides a mechanism for leaf procedures to avoid needing to save registers. Compilers may choose to allocate variables into caller or callee saved registers depending on how their lifetimes overlap with procedure calls.

Procedure parameters are normally allocated in registers starting from register 2 up to register 9. These registers hold up to 8 parameters which may each be of any size from one byte to sixteen bytes hexlet including floating point and small structure parameters. Additional parameters are passed in memory allocated on the stack. For C procedures which use varargs.h or stdarg.h and pass parameters to further procedures the compilers must leave room in the stack memory allocation to save registers 2 through 9 into memory contiguously with the additional stack memory parameters so that procedures such as  doprnt can refer to the parameters as an array.

Procedure return values are also allocated in registers starting from register 2 up to register 9. Larger values are passed in memory allocated on the stack.

There are several pointers maintained in registers for the procedure calling conventions lp sp dp fp.

The lp register contains the address to which the callee should return to at the conclusion of the procedure. If the procedure is also a caller the lp register will need to be saved on the stack once before any procedure call and restored once after all procedure calls. The procedure returns with a branch instruction specifying the lp register.

The sp register is used to form addresses to save parameter and other registers maintain local variables i.e. data that is allocated as a LIFO stack. For procedures that require a stack normally a single allocation is performed which allocates space for input parameters local variables saved registers and output parameters all at once. The sp register is always hexlet aligned.

The dp register is used to address pointers literals and static variables for the procedure. The dp register points to a small approximately 4096 entry array of pointers literals and statically allocated variables which is used locally to the procedure. The uses of the dp register are similar to the use of the gp register on a Mips R series processor except that each procedure may have a different value which expands the space addressable by small offsets from this pointer. This is an important distinction as the offset field of Zeus load and store instructions are only 12 bits. The compiler may use additional registers and or indirect pointers to address larger regions for a single procedure. The compiler may also share a single dp register value between procedures which are compiled as a single unit including procedures which are externally callable eliminating the need to save modify and restore the dp register for calls between procedures which share the same dp register value.

Load and store immediate aligned instructions specifying the dp register as the base register are generally used to obtain values from the dp region. These instructions shift the immediate value by the logarithm of the size of the operand so loads and stores of large operands may reach farther from the dp register than of small operands. Referring to the size of the addressable region is maximized if the elements to be placed in the dp region are sorted according to size with the smallest elements placed closest to the dp base. At points where the size changes appropriate padding is added to keep elements aligned to memory boundaries matching the size of the elements. Using this technique the maximum size of the dp region is always at least 4096 items and may be larger when the dp area is composed of a mixture of data sizes.

The dp register mechanism also permits code to be shared with each static instance of the dp region assigned to a different address in memory. In conjunction with position independent or pc relative branches this allows library code to be dynamically relocated and shared between processes.

To implement an inter module separately compiled procedure call the lp register is loaded with the entry point of the procedure and the dp register is loaded with the value of the dp register required for the procedure. These two values are located adjacent to each other as a pair of octlet quantities in the dp region for the calling procedure. For a statically linked inter module procedure call the linker fills in the values at link time. However this mechanism also provides for dynamic linking by initially filling in the lp and dp fields in the data structure to invoke the dynamic linker. The dynamic linker can use the contents of the lp and or dp registers to determine the identity of the caller and callee to find the location to fill in the pointers and resume execution. Specifically the lp value is initially set to point to an entry point in the dynamic linker and the dp value is set to point to itself the location of the lp and dp values in the dp region of the calling procedure. The identity of the procedure can be discovered from a string following the dp pointer or a separate table indexed by the dp pointer.

The fp register is used to address the stack frame when the stack size varies during execution of a procedure such as when using the GNU C alloca function. When the stack size can be determined at compile time the sp register is used to address the stack frame and the fp register may be used for any other general purpose as a callee saved register. caller 

Procedures that are compiled together may share a common data region in which case there is no need to save load and restore the dp region in the callee assuming that the callee does not modify the dp register. The pc relative addressing of the B.LINK.I instruction permits the code region to be position independent.

When all the callee procedures are intra module the stack frame may also be eliminated from the caller procedure by using temporary caller save registers not utilized by the callee leaf procedures. In addition to the lp value indicated above this usage may include other values and variables that live in the caller procedure across callee procedure calls.

The load instruction is required in the caller following the procedure call to restore the dp register. A second load instruction also restores the lp register which may be located at any point between the last procedure call and the branch instruction which returns from the procedure.

It is an objective to make calls to system facilities and privileged libraries as similar as possible to normal procedure calls as described above. Rather than invoke system calls as an exception which involves significant latency and complication we prefer to use a modified procedure call in which the process privilege level is quietly raised to the required level. To provide this mechanism safely interaction with the virtual memory system is required.

Such a procedure must not be entered from anywhere other than its legitimate entry point to prohibit entering a procedure after the point at which security checks are performed or with invalid register contents otherwise the access to a higher privilege level can lead to a security violation. In addition the procedure generally must have access to memory data for which addresses must be produced by the privileged code. To facilitate generating these addresses the branch gateway instruction allows the privileged code procedure to rely the fact that a single register has been verified to contain a pointer to a valid memory region.

The branch gateway instruction ensures both that the procedure is invoked at a proper entry point and that other registers such as the data pointer and stack pointer can be properly set. To ensure this the branch gateway instruction retrieves a gateway directly from the protected virtual memory space. The gateway contains the virtual address of the entry point of the procedure and the target privilege level. A gateway can only exist in regions of the virtual address space designated to contain them and can only be used to access privilege levels at or below the privilege level at which the memory region can be written to ensure that a gateway cannot be forged.

The branch gateway instruction ensures that register 1 dp contains a valid pointer to the gateway for this target code address by comparing the contents of register 0 lp against the gateway retrieved from memory and causing an exception trap if they do not match. By ensuring that register 1 points to the gateway auxiliary information such as the data pointer and stack pointer can be set by loading values located by the contents of register 1. For example the eight bytes following the gateway may be used as a pointer to a data region for the procedure.

Referring to before executing the branch gateway instruction register 1 must be set to point at the gateway and register 0 must be set to the address of the target code address plus the desired privilege level. A L.I.64.L.A r0 r1 0 instruction is one way to set register 0 if register 1 has already been set but any means of getting the correct value into register 0 is permissible.

Similarly a return from a system or privileged routine involves a reduction of privilege. This need not be carefully controlled by architectural facilities so a procedure may freely branch to a less privileged code address. Normally such a procedure restores the stack frame then uses the branch down instruction to return.

It can be observed that the calling sequence is identical to that of the inter module calling sequence shown above except for the use of the B.GATE instruction instead of a B.LINK instruction. Indeed if a B.GATE instruction is used when the privilege level in the lp register is not higher than the current privilege level the B.GATE instruction performs an identical function to a B.LINK.

The callee if it uses a stack for local variable allocation cannot necessarily trust the value of the sp passed to it as it can be forged. Similarly any pointers which the callee provides should not be used directly unless it they are verified to point to regions which the callee should be permitted to address. This can be avoided by defining application programming interfaces APIs in which all values are passed and returned in registers or by using a trusted intermediate privilege wrapper routine to pass and return parameters. The method described below can also be used.

It can be useful to have highly privileged code call less privileged routines. For example a user may request that errors in a privileged routine be reported by invoking a user supplied error logging routine. To invoke the procedure the privilege can be reduced via the branch down instruction. The return from the procedure actually requires an increase in privilege which must be carefully controlled. This is dealt with by placing the procedure call within a lower privilege procedure wrapper which uses the branch gateway instruction to return to the higher privilege region after the call through a secure re entry point Special care must be taken to ensure that the less privileged routine is not permitted to gain unauthorized access by corruption of the stack or saved registers such as by saving all registers and setting up a new stack frame or restoring the original lower privilege stack that may be manipulated by the less privileged routine. Finally such a technique is vulnerable to an unprivileged routine attempting to use the re entry point directly so it may be appropriate to keep a privileged state variable which controls permission to enter at the re entry point.

Referring first to a general purpose processor is illustrated therein in block diagram form. In four copies of an access unit are shown each with an access instruction fetch queue A Queue . Each access instruction fetch queue A Queue is coupled to an access register file AR which are each coupled to two access functional units A . In a typical embodiment each thread of the processor may have on the order of sixty four general purpose registers e.g. the AR s and ER s . The access units function independently for four simultaneous threads of execution and each compute program control flow by performing arithmetic and branch instructions and access memory by performing load and store instructions. These access units also provide wide operand specifiers for wide operand instructions. These eight access functional units A produce results for access register files AR and memory addresses to a shared memory system .

In one embodiment the memory hierarchy includes on chip instruction and data memories instruction and data caches a virtual memory facility and interfaces to external devices. In the memory system is comprised of a combined cache and niche memory an external bus interface and externally to the device a secondary cache and main memory system with devices . The memory contents fetched from memory system are combined with execute instructions not performed by the access unit and entered into the four execute instruction queues E Queue . In accordance with one embodiment of the present invention from the software perspective the machine state includes a linear byte addressed shared memory space. For wide instructions memory contents fetched from memory system are also provided to wide operand microcaches by bus . Instructions and memory data from E queue are presented to execution register files which fetch execution register file source operands. The instructions are coupled to the execution unit arbitration unit Arbitration that selects which instructions from the four threads are to be routed to the available execution functional units E and X and G and and T . The execution functional units E and the execution functional units X and and the execution functional unit T each contain a wide operand microcache which are each coupled to the memory system by bus .

The execution functional units G and are group arithmetic and logical units that perform simple arithmetic and logical instructions including group operations wherein the source and result operands represent a group of values of a specified symbol size which are partitioned and operated on separately with results catenated together. In a presently preferred embodiment the data path is 128 bits wide although the present invention is not intended to be limited to any specific size of data path.

The execution functional units X and are crossbar switch units that perform crossbar switch instructions. The crossbar switch units and perform data handling operations on the data stream provided over the data path source operand buses including deal shuffles shifts expands compresses swizzles permutes and reverses plus the wide operations discussed hereinafter. In a key element of a first aspect of the invention at least one such operation will be expanded to a width greater than the general register and data path width. Examples of the data manipulation operations are described in another section.

The execution functional units E and are ensemble units that perform ensemble instructions using a large array multiplier including group or vector multiply and matrix multiply of operands partitioned from data path source operand buses S and treated as integer floating point polynomial or Galois field values. According to the present embodiment of the invention a general software solution is provided to the most common operations required for Galois Field arithmetic. The instructions provided include a polynomial multiply with the polynomial specified as one register operand. This instruction can be used to perform CRC generation and checking Reed Solomon code generation and checking and spread spectrum encoding and decoding. Also matrix multiply instructions and other operations described in another section utilize a wide operand loaded into the wide operand microcache and .

The execution functional unit T is a translate unit that performs table look up operations on a group of operands partitioned from a register operand and catenates the result. The Wide Translate instruction included in another section utilizes a wide operand loaded into the wide operand microcache .

The execution functional units E execution functional units X and execution functional unit T each contain dedicated storage to permit storage of source operands including wide operands as discussed hereinafter. The dedicated storage which may be thought of as a wide microcache typically has a width which is a multiple of the width of the data path operands related to the data path source operand buses . Thus if the width of the data path is 128 bits the dedicated storage may have a width of 256 512 1024 or 2048 bits. Operands which utilize the full width of the dedicated storage are referred to herein as wide operands although it is not necessary in all instances that a wide operand use the entirety of the width of the dedicated storage it is sufficient that the wide operand use a portion greater than the width of the memory data path of the output of the memory system and the functional unit data path of the input of the execution functional units though not necessarily greater than the width of the two combined. Because the width of the dedicated storage is greater than the width of the memory operand bus portions of wide operands are loaded sequentially into the dedicated storage . However once loaded the wide operands may then be used at substantially the same time. It can be seen that functional units and associated execution registers form a data functional unit the exact elements of which may vary with implementation.

The execution register file ER source operands are coupled to the execution units using source operand buses and to the execution units using source operand buses . The function unit result operands from execution units are coupled to the execution register file ER using result bus and the function units result operands from execution units are coupled to the execution register file using result bus .

The wide operands used in some embodiments of the present invention provide the ability to execute complex instructions such as the wide multiply matrix instruction shown in which can be appreciated in an alternative form as well from . As can be appreciated from a wide operand permits for example the matrix multiplication of various sizes and shapes which exceed the data path width. The example of involves a matrix specified by register rc having a 128 64 size multiplied by a vector contained in register rb having a 128 size to yield a result placed in register rd of 128 bits.

The operands that are substantially larger than the data path width of the processor are provided by using a general purpose register to specify a memory specifier from which more than one but in some embodiments several data path widths of data can be read into the dedicated storage. The memory specifier typically includes the memory address together with the size and shape of the matrix of data being operated on. The memory specifier or wide operand specifier can be better appreciated from in which a specifier is seen to be an address plus a field representative of the size 2 and a further field representative ofwidthl2 where size is the product of the depth and width of the data. The address is aligned to a specified size for example sixty four bytes so that a plurality of low order bits for example six bits are zero. The specifier can thus be seen to comprise a first field for the address plus two field indicia within the low order six bits to indicate size and width.

The decoding of the specifier may be further appreciated from where for a given specifier made up of an address field together with a field comprising plurality of low order bits. By a series of arithmetic operations shown at steps and the portion of the field representative of widthl2 is developed. In a similar series of steps shown at and the value oft is decoded which can then be used to decode both size and address. The portion of the field representative of size 2 is decoded as shown at steps and while the address is decoded in a similar way at steps and .

The wide function unit may be better appreciated from in which a register number is provided to an operand checker . Wide operand specifier communicates with the operand checker and also addresses memory having a defined memory width. The memory address includes a plurality of register operands A n which are accumulated in a dedicated storage portion of a data functional unit . In the exemplary embodiment shown in the dedicated storage can be seen to have a width equal to eight data path widths such that eight wide operand portions A H are sequentially loaded into the dedicated storage to form the wide operand. Although eight portions are shown in the present invention is not limited to eight or any other specific multiple of data path widths. Once the wide operand portions A H are sequentially loaded they may be used as a single wide operand by the functional element which may be any element s from connected thereto. The result of the wide operand is then provided. to a result register which in a presently preferred embodiment is of the same width as the memory width.

Once the wide operand is successfully loaded into the dedicated storage a second aspect of the present invention may be appreciated. Further execution of this instruction or other similar instructions that specify the same memory address can read the dedicated storage to obtain the operand value under specific conditions that determine whether the memory operand has been altered by intervening instructions. Assuming that these conditions are met the memory operand fetch from the dedicated storage is combined with one or more register operands in the functional unit producing a result. In some embodiments the size of the result is limited to that of a general register so that no similar dedicated storage is required for the result. However in some different embodiments the result may be a wide operand to further enhance performance.

To permit the wide operand value to be addressed by subsequent instructions specifying the same memory address various conditions must be checked and confirmed 

1. Each memory store instruction checks the memory address against the memory addresses recorded for the dedicated storage. Any match causes the storage to be marked invalid since a memory store instruction directed to any of the memory addresses stored in dedicated storage means that data has been overwritten.

2. The register number used to address the storage is recorded. If no intervening instructions have written to the register and the same register is used on the subsequent instruction the storage is valid unless marked invalid by rule 1 .

3. If the register has been modified or a different register number is used the value of the register is read and compared against the address recorded for the dedicated storage. This uses more resources than 1 because of the need to fetch the register contents and because the width of the register is greater than that of the register number itself. If the address matches the storage is valid. The new register number is recorded for the dedicated storage.

If conditions 2 or 3 are not met the register contents are used to address the general purpose processor s memory and load the dedicated storage. If dedicated storage is already fully loaded a portion of the dedicated storage must be discarded victimized to make room for the new value. The instruction is then performed using the newly updated dedicated storage. The address and register number is recorded for the dedicated storage.

By checking the above conditions the need for saving and restoring the dedicated storage is eliminated. In addition if the context of the processor is changed and the new context does not employ Wide instructions that reference the same dedicated storage when the original context is restored the contents of the dedicated storage are allowed to be used without refreshing the value from memory using checking rule 3. Because the values in the dedicated storage are read from memory and not modified directly by performing wide operations the values can be discarded at any time without saving the results into general memory. This property simplifies the implementation of rule 4 above.

1a. Each memory store instruction checks the memory address against the memory addresses recorded for the dedicated storage. Any match causes the dedicated storage to be updated as well as the general memory.

By use of the above rule 1.a memory store instructions can modify the dedicated storage updating just the piece of the dedicated storage that has been changed leaving the remainder intact. By continuing to update the general memory it is still true that the contents of the dedicated memory can be discarded at any time without saving the results into general memory. Thus rule 4 is not made more complicated by this choice. The advantage of this alternate embodiment is that the dedicated storage need not be discarded invalidated by memory store operations.

Referring next to an exemplary arrangement of the data structures of the wide microcache or dedicated storage may be better appreciated. The wide microcache contents wmc.c can be seen to form a plurality of data path widths A n although in the example shown the number is eight. The physical address wmc.pa is shown as 64 bits in the example shown although the invention is not limited to a specific width. The size of the contents wmc.size is also provided in a field which is shown as 10 bits in an exemplary embodiment. A contents valid flag wmc.ev of one bit is also included in the data structure together with a two bit field for thread last used or wmc.th. In addition a six bit field for register last used wmc.reg is provided in an exemplary embodiment. Further a one bit flag for register and thread valid or wmc.rtv may be provided.

The process by which the microcache is initially written with a wide operand and thereafter verified as valid for fast subsequent operations may be better appreciated from . The process begins at and progresses to step where a check of the register contents is made against the stored value wme.rc. If true a check is made at step to verify the thread. If true the process then advances to step to verify whether the register and thread are valid. If step reports as true a check is made at step to verify whether the contents are valid. If all of steps through return as true the subsequent instruction is able to utilize the existing wide operand as shown at step after which the process ends. However if any of steps through return as false the process branches to step where content physical address and size are set. Because steps through all lead to either step or steps through may be performed in any order or simultaneously without altering the process. The process then advances to step where size is checked. This check basically ensures that the size of the translation unit is greater than or equal to the size of the wide operand so that a physical address can directly replace the use of a virtual address. The concern is that in some embodiments the wide operands may be larger than the minimum region that the virtual memory system is capable of mapping. As a result it would be possible for a single contiguous virtual address range to be mapped into multiple disjoint physical address ranges complicating the task of comparing physical addresses. By determining the size of the wide operand and comparing that size against the size of the virtual address mapping region which is referenced the instruction is aborted with an exception trap if the wide operand is larger than the mapping region. This ensures secure operation of the processor. Software can then re map the region using a larger size map to continue execution if desired. Thus if size is reported as unacceptable at step an exception is generated at step . If size is acceptable the process advances to step where physical address is checked. If the check reports as met the process advances to step where a check of the contents valid flag is made. If either check at step or reports as false the process branches and new content is written into the dedicated storage with the fields thereof being set accordingly. Whether the check at step reported true or whether new content was written at step the process advances to step where appropriate fields are set to indicate the validity of the data after which the requested function can be performed at step . The process then ends.

Referring next to which together show the operation of the microcache controller from a hardware standpoint the operation of the microcache controller may be better understood. In the hardware implementation it is clear that conditions which are indicated as sequential steps in above can be performed in parallel reducing the delay for such wide operand checking. Further a copy of the indicated hardware may be included for each wide microcache and thereby all such microcaches as may be alternatively referenced by an instruction can be tested in parallel. It is believed that no further discussion of is required in view of the extensive discussion of FIGS. and above.

Various alternatives to the foregoing approach do exist for the use of wide operands including an implementation in which a single instruction can accept two wide operands partition the operands into symbols multiply corresponding symbols together and add the products to produce a single scalar value or a vector of partitioned values of width of the register file possibly after extraction of a portion of the sums. Such an instruction can be valuable for detection of motion or estimation of motion in video compression. A further enhancement of such an instruction can incrementally update the dedicated storage if the address of one wide operand is within the range of previously specified wide operands in the dedicated storage by loading only the portion not already within the range and shifting the in range portion as required. Such an enhancement allows the operation to be performed over a sliding window of possible values. In such an instruction one wide operand is aligned and supplies the size and shape information while the second wide operand updated incrementally is not aligned.

Another alternative embodiment of the present invention can define additional instructions where the result operand is a wide operand. Such an enhancement removes the limit that a result can be no larger than the size of a general register further enhancing performance. These wide results can be cached locally to the functional unit that created them but must be copied to the general memory system before the storage can be reused and before the virtual memory system alters the mapping of the address of the wide result. Data paths must be added so that load operations and other wide operations can read these wide results forwarding of a wide result from the output of a functional unit back to its input is relatively easy but additional data paths may have to be introduced if it is desired to forward wide results back to other functional units as wide operands.

As previously discussed a specification of the size and shape of the memory operand is included in the low order bits of the address. In a presently preferred implementation such memory operands are typically a power of two in size and aligned to that size. Generally one half the total size is added or inclusively or ed or exclusively or ed to the memory address and one half of the data width is added or inclusively or ed or exclusively or ed to the memory address. These bits can be decoded and stripped from the memory address so that the controller is made to step through all the required addresses. This decreases the number of distinct operands required for these instructions as the size shape and address of the memory operand are combined into a single register operand value.

Particular examples of wide operations which are defined by the present invention include the Wide Switch instruction that performs bit level switching the Wide Translate instruction which performs byte or larger table lookup Wide Multiply Matrix Wide Multiply Matrix Extract and Wide Multiply Matrix Extract Immediate discussed below Wide Multiply Matrix Floating point and Wide Multiply Matrix Galois also discussed below . While the discussion below focuses on particular sizes for the exemplary instructions it will be appreciated that the invention is not limited to a particular width.

The Wide Switch instruction rearranges the contents of up to two registers 256 bits at the bit level producing a full width 128 bits register result. To control the rearrangement a wide operand specified by a single register consisting of eight bits per bit position is used. For each result bit position eight wide operand bits for each bit position select which of the 256 possible source register bits to place in the result. When a wide operand size smaller than 128 bytes the high order bits of the memory operand are replaced with values corresponding to the result bit position so that the memory operand specifies a bit selection within symbols of the operand size performing the same operation on each symbol.

The Wide Translate instructions use a wide operand to specify a table of depth up to 256 entries and width of up to 128 bits. The contents of a register is partitioned into operands of one two four or eight bytes and the partitions are used to select values from the table in parallel. The depth and width of the table can be selected by specifying the size and shape of the wide operand as described above.

The Wide Multiply Matrix instructions use a wide operand to specify a matrix of values of width up to 64 bits one half of register file and data path width and depth of up to 128 bits symbol size. The contents of a general register 128 bits is used as a source operand partitioned into a vector of symbols and multiplied with the matrix producing a vector of width up to 128 bits of symbols of twice the size of the source operand symbols. The width and depth of the matrix can be selected by specifying the size and shape of the wide operand as described above. Controls within the instruction allow specification of signed mixed signed unsigned complex or polynomial operands.

The Wide Multiply Matrix Extract instructions use a wide operand to specify a matrix of value of width up to 128 bits full width of register file and data path and depth of up to 128 bits symbol size. The contents of a general register 128 bits is used as a source operand partitioned into a vector of symbols and multiplied with the matrix producing a vector of width up to 256 bits of symbols of twice the size of the source operand symbols plus additional bits to represent the sums of products without overflow. The results are then extracted in a manner described below Enhanced Multiply Bandwidth by Result Extraction as controlled by the contents of a general register specified by the instruction. The general register also specifies the format of the operands signed mixed signed unsigned and complex as well as the size of the operands byte 8 bit doublet 16 bit quadlet 32 bit or hexlet 64 bit .

The Wide Multiply Matrix Extract Immediate instructions perform the same function as above except that the extraction operand format and size is controlled by fields in the instruction. This form encodes common forms of the above instruction without the need to initialize a register with the required control information. Controls within the instruction allow specification of signed mixed signed unsigned and complex operands.

The Wide Multiply Matrix Floating point instructions perform a matrix multiply in the same form as above except that the multiplies and additions are performed in floating point arithmetic. Sizes of half 16 bit single 32 bit double 64 bit and complex sizes of half single and double can be specified within the instruction.

Wide Multiply Matrix Galois instructions perform a matrix multiply in the same form as above except that the multiples and additions are performed in Galois field arithmetic. A size of 8 bits can be specified within the instruction. The contents of a general register specify the polynomial with which to perform the Galois field remainder operation. The nature of the matrix multiplication is novel and described in detail below.

In another aspect of the invention memory operands of either little endian or big endian conventional byte ordering are facilitated. Consequently all Wide operand instructions are specified in two forms one for little endian byte ordering and one for big endian byte ordering as specified by a portion of the instruction. The byte order specifies to the memory system the order in which to deliver the bytes within units of the data path width 128 bits as well as the order to place multiple memory words 128 bits within a larger Wide operand. Each of these instructions is described in greater detail.

Some embodiments of the present invention address extraction of a high order portion of a multiplier product or sum of products as a way of efficiently utilizing a large multiplier array. Parent U.S. Pat. No. 5 742 840 and U.S. Pat. No. 5 953 241 describe a system and method for enhancing the utilization of a multiplier array by adding specific classes of instructions to a general purpose processor. This addresses the problem of making the most use of a large multiplier array that is fully used for high precision arithmetic for example a 64.times.64 bit multiplier is fully used by a 64 bit by 64 bit multiply but only one quarter used for a 32 bit by 32 bit multiply for relative to the multiplier data width and registers low precision arithmetic operations. In particular operations that perform a great many low precision multiplies which are combined added together in various ways are specified. One of the overriding considerations in selecting the set of operations is a limitation on the size of the result operand. In an exemplary embodiment for example this size might be limited to on the order of 128 bits or a single register although no specific size limitation need exist.

The size of a multiply result a product is generally the sum of the sizes of the operands multiplicands and multiplier. Consequently multiply instructions specify operations in which the size of the result is twice the size of identically sized input operands. For our prior art design for example a multiply instruction accepted two 64 bit register sources and produces a single 128 bit register pair result using an entire 64.times.64 multiplier array for 64 bit symbols or half the multiplier array for pairs of 32 bit symbols or one quarter the multiplier array for quads of 16 bit symbols. For all of these cases note that two register sources of 64 bits are combined yielding a 128 bit result.

In several of the operations including complex multiplies convolve and matrix multiplication low precision multiplier products are added together. The additions further increase the required precision. The sum of two products requires one additional bit of precision adding four products requires two adding eight products requires three adding sixteen products requires four. In some prior designs some of this precision is lost requiring scaling of the multiplier operands to avoid overflow further reducing accuracy of the result.

The use of register pairs creates an undesirable complexity in that both the register pair and individual register values must be bypassed to subsequent instructions. As a result with prior art techniques only half of the source operand 128 bit register values could be employed toward producing a single register 128 bit result.

In some embodiments of the present invention a high order portion of the multiplier product or sum of products is extracted adjusted by a dynamic shift amount from a general register or an adjustment specified as part of the instruction and rounded by a control value from a register or instruction portion as round to nearest even toward zero floor or ceiling. Overflows are handled by limiting the result to the largest and smallest values that can be accurately represented in the output result.

In the present invention when the extract is controlled by a register the size of the result can be specified allowing rounding and limiting to a smaller number of bits than can fit in the result. This permits the result to be scaled to be used in subsequent operations without concern of overflow or rounding enhancing performance.

Also in the present invention when the extract is controlled by a register a single register value defines the size of the operands the shift amount and size of the result and the rounding control. By placing all this control information in a single register the size of the instruction is reduced over the number of bits that such a instruction would otherwise require improving performance and enhancing flexibility of the processor.

The particular instructions included in this aspect of the present invention are Ensemble Convolve Extract Ensemble Multiply Extract Ensemble Multiply Add Extract and Ensemble Scale Add Extract each of which is more thoroughly treated in another section.

An aspect of the present invention defines the Ensemble Scale Add Extract instruction that combines the extract control information in a register along with two values that are used as scalar multipliers to the contents of two vector multiplicands. This combination reduces the number of registers that would otherwise be required or the number of bits that the instruction would otherwise require improving performance.

Several of these instructions Ensemble Convolve Extract Ensemble Multiply Add Extract are typically available only in forms where the extract is specified as part of the instruction. An alternative embodiment can incorporate forms of the operations in which the size of the operand the shift amount and the rounding can be controlled by the contents of a general register as they are in the Ensemble Multiply Extract instruction . The definition of this kind of instruction for Ensemble Convolve Extract and Ensemble Multiply Add Extract would require four source registers which increases complexity by requiring additional general register read ports.

Another alternative embodiment can reduce the number of register read ports required for implementation of instructions in which the size shift and rounding of operands is controlled by a register. The value of the extract control register can be fetched using an additional cycle on an initial execution and retained within or near the functional unit for subsequent executions thus reducing the amount of hardware required for implementation with a small additional performance penalty. The value retained would be marked invalid causing are fetch of the extract control register by instructions that modify the register or alternatively the retained value can be updated by such an operation. Are fetch of the extract control register would also be required if a different register number were specified on a subsequent execution. It should be clear that the properties of the above two alternative embodiments can be combined.

Another embodiment of the invention includes Galois field arithmetic where multiplies are performed by an initial binary polynomial multiplication unsigned binary multiplication with carries suppressed followed by a polynomial modulo remainder operation unsigned binary division with carries suppressed . The remainder operation is relatively expensive in area and delay. In Galois field arithmetic additions are performed by binary addition with carries suppressed or equivalently a bitwise exclusive or operation. In this aspect of the present invention a matrix multiplication is performed using Galois field arithmetic where the multiplies and additions are Galois field multiples and additions.

Using prior art methods a 16 byte vector multiplied by a 16.times.16 byte matrix can be performed as 256 8 bit Galois field multiplies and 16 15 240 8 bit Galois field additions. Included in the 256 Galois field multiplies are 256 polynomial multiplies and 256 polynomial remainder operations. But by use of the present invention the total computation can be reduced significantly by performing 256 polynomial multiplies 240 16 bit polynomial additions and 16 polynomial remainder operations. Note that the cost of the polynomial additions has been doubled as these are now 16 bit operations but the cost of the polynomial remainder functions has been reduced by a factor of 16. Overall this is a favorable tradeoff as the cost of addition is much lower than the cost of remainder.

In a still further aspect of the present invention a technique is provided for incorporating floating point information into processor instructions. In U.S. Pat. No. 5 812 439 a system and method are described for incorporating control of rounding and exceptions for floating point instructions into the instruction itself. The present invention extends this invention to include separate instructions in which rounding is specified but default handling of exceptions is also specified for a particular class of floating point instructions. Specifically the SINK instruction which converts floating point values to integral values is available with control in the instruction that include all previously specified combinations default near rounding and default exceptions Z round toward zero and trap on exceptions N round to nearest and trap on exceptions F floor rounding toward minus infinity and trap on exceptions C ceiling rounding toward plus infinity and trap on exceptions and X trap on inexact and other exceptions as well as three new combinations Z.D round toward zero and default exception handling F.D floor rounding and default exception handling and C.D ceiling rounding and default exception handling . The other combinations N.D is equivalent to the default and X.D trap on inexact but default handling for other exceptions is possible but not particularly valuable .

The next section describes detailed pipeline organization for Zeus which has a significant influence on instruction scheduling. Here we will elaborate some general rules for effective scheduling by a compiler. Specific information on numbers of functional units functional unit parallelism and latency is quite implementation dependent values indicated here are valid for Zeus s first implementation.

Zeus has separate function units to perform addressing operations A L S B instructions from execution operations G X E W instructions . When possible Zeus will execute all the addressing operations of an instruction stream deferring execution of the execution operations until dependent load instructions are completed. Thus the latency of the memory system is hidden so long as addressing operations themselves do not need to wait for memory.

Instructions should generally be scheduled so that previous operations can be completed at the time of issue. When this is not possible the processor inserts sufficient empty cycles to perform the instructions precisely explicit no operation instructions are not required.

Zeus can issue up to two addressing operations and up to two execution operations per cycle per thread. Considering functional unit parallelism described below as many of four instruction issues per cycle are possible per thread.

Zeus has separate function units for several classes of execution operations. An A unit performs scalar add subtract boolean and shift add operations for addressing and branch calculations. The remaining functional units are execution resources which perform operations subsequent to memory loads and which operate on values in a parallel partitioned form. A G unit performs add subtract boolean and shift add operations. An X unit performs general shift operations. An E unit performs multiply and floating point operations. A T unit performs table look up operations.

The latency of each functional unit depends on what operation is performed in the unit and where the result is used. The aggressive nature of the pipeline makes it difficult to characterize the latency of each operation with a single number. Because the addressing unit is decoupled from the execution unit the latency of load operations is generally hidden unless the result of a load instruction must be returned to the addressing unit. Store instructions must be able to compute the address to which the data is to be stored in the addressing unit but the data will not be irrevocably stored until the data is available and it is valid to retire the store instruction. However under certain conditions data may be forwarded from a store instruction to subsequent load instructions once the data is available.

As shown in some embodiments of the present invention employ both decoupled access from execution pipelines and simultaneous multithreading in a unique way. Simultaneous Multithreaded pipelines have been employed in prior art to enhance the utilization of data path units by allowing instructions to be issued from one of several execution threads to each functional unit e.g. Susan Eggers University of Wash papers on Simultaneous Multithreading .

Decoupled access from execution pipelines have been employed in prior art to enhance the utilization of execution data path units by buffering results from an access unit which computes addresses to a memory unit that in turn fetches the requested items from memory and then presenting them to an execution unit e.g. James E. Smith paper on Decoupled Access from Execution .

Compared to conventional pipelines Eggers prior art used an additional pipeline cycle before instructions could be issued to functional units the additional cycle needed to determine which threads should be permitted to issue instructions. Consequently relative to conventional pipelines the prior art design had additional delay including dependent branch delay.

The embodiment shown in contains individual access data path units with associated register files for each execution thread. These access units produce addresses which are aggregated together to a common memory unit which fetches all the addresses and places the memory contents in one or more buffers. Instructions for execution units which are shared to varying degrees among the threads are also buffered for later execution. The execution units then perform operations from all active threads using functional data path units that are shared.

For instructions performed by the execution units the extra cycle required for prior art simultaneous multithreading designs is overlapped with the memory data access time from prior art decoupled access from execution cycles so that no additional delay is incurred by the execution functional units for scheduling resources. For instructions performed by the access units by employing individual access units for each thread the additional cycle for scheduling shared resources is also eliminated.

This is a favorable tradeoff because while threads do not share the access functional units these units are relatively small compared to the execution functional units which are shared by threads.

A difficulty in particular pipeline structures is that dependent operations must be separated by the latency of the pipeline and for highly pipe lined machines the latency of simple operations can be quite significant. According to one embodiment of the present invention very highly pipelined implementations are provided by alternating execution of two or more independent threads. In an embodiment a thread is the state required to maintain an independent execution the architectural state required is that of the register file contents program counter privilege level local TB and when required exception status. In an embodiment ensuring that only one thread may handle an exception at one time may minimize the latter state exception status. In order to ensure that all threads make reasonable forward progress several of the machine resources must be scheduled fairly.

An example of a resource that is critical that it be fairly shared is the data memory cache subsystem. In one embodiment the processor may be able to perform a load operation only on every second cycle and a store operation only on every fourth cycle. The processor schedules these fixed timing resources fairly by using a round robin schedule for a number of threads that is relatively prime to the resource reuse rates. In one embodiment five simultaneous threads of execution ensure that resources which may be used every two or four cycles are fairly shared by allowing the instructions which use those resources to be issued only on every second or fourth issue slot for that thread. More details relating to this pipeline structure are explained in the Superthread Pipeline section.

Referring back to with regard to the sharing of execution units one embodiment of the present invention employs several different classics of functional units for the execution unit with varying cost utilization and performance. In particular the G units which perform simple addition and bitwise operations is relatively inexpensive in area and power compared to the other units and its utilization is relatively high. Consequently the design employs four such units where each unit can be shared between two threads. The X unit which performs a broad class of data switching functions is more expensive and less used so two units are provided that are each shared among two threads. The T unit which performs the Wide Translate instruction is expensive and utilization is low so the single unit is shared among all four threads. The E unit which performs the class of Ensemble instructions is very expensive in area and power compared to the other functional units but utilization is relatively high so we provide two such units each unit shared by two threads.

In four copies of an access unit are shown each with an access instruction fetch queue A Queue coupled to an access register file AR each of which is in turn coupled to two access functional units A . The access units function independently for four simultaneous threads of execution. These eight access functional units A produce results for access register files AR and addresses to a shared memory system . The memory contents fetched from memory system are combined with execute instructions not performed by the access unit and entered into the four execute instruction queues E Queue . Instructions and memory data from E queue are presented to execution register files which fetches execution register file source operands. The instructions are coupled to the execution unit arbitration unit Arbitration that selects which instructions from the four threads are to be routed to the available execution units E and X and and and T . The execution register file source operands ER are coupled to the execution units using source operand buses and to the execution units using source operand buses . The function unit result operands from execution units are coupled to the execution register file using result bus and the function units result operands from execution units are coupled to the execution register file using result bus .

In a still further aspect of the present invention an improved interprivilege gateway is described which involves increased parallelism and leads to enhanced performance. In U.S. application Ser. No. 08 541 416 now U.S. Pat. No. 6 101 590 a system and method is described for implementing an instruction that in a controlled fashion allows the transfer of control branch from a lower privilege level to a higher privilege level. Embodiment of the present invention provides an improved system and method for a modified instruction that accomplishes the same purpose but with specific advantages.

Many processor resources such as control of the virtual memory system itself input and output operations and system control functions are protected from accidental or malicious misuse by enclosing them in a protective privileged region. Entry to this region must be established only though particular entry points called gateways to maintain the integrity of these protected regions.

Prior art versions of this operation generally load an address from a region of memory using a protected virtual memory attribute that is only set for data regions that contain valid gateway entry points then perform a branch to an address contained in the contents of memory. Basically three steps were involved load branch then check. Compared to other instructions such as register to register computation instructions and memory loads and stores and register based branches this is a substantially longer operation which introduces delays and complexity to a pipelined implementation.

In the present invention the branch gateway instruction performs two operations in parallel 1 a branch is performed to the contents of register 0 and 2 a load is performed using the contents of register 1 using a specified byte order little endian and a specified size 64 bits . If the value loaded from memory does not equal the contents of register 0 the instruction is aborted due to an exception. In addition 3 a return address the next sequential instruction address following the branch gateway instruction is written into register 0 provided the instruction is not aborted. This approach essentially uses a first instruction to establish the requisite permission to allow user code to access privileged code and then a second instruction is permitted to branch directly to the privileged code because of the permissions issued for the first instruction.

In the present invention the new privilege level is also contained in register 0 and the second parallel operation does not need to be performed if the new privilege level is not greater than the old privilege level. When this second operation is suppressed the remainder of the instruction performs an identical function to a branch link instruction which is used for invoking procedures that do not require an increase in privilege. The advantage that this feature brings is that the branch gateway instruction can be used to call a procedure that mayor may not require an increase in privilege.

The memory load operation verifies with the virtual memory system that the region that is loaded has been tagged as containing valid gateway data. A further advantage of the present invention is that the called procedure may rely on the fact that register 1 contains the address that the gateway data was loaded from and can use the contents of register 1 to locate additional data or addresses that the procedure may require. Prior art versions of this instruction required that an additional address be loaded from the gateway region of memory in order to initialize that address in a protected manner the present invention allows the address itself to be loaded with a normal load operation that does not require special protection.

The present invention allows a normal load operation to also load the contents of register 0 prior to issuing the branch gateway instruction. The value may be loaded from the same memory address that is loaded by the branch gateway instruction because the present invention contains a virtual memory system in which the region may be enabled for normal load operations as well as the special gateway load operation performed by the branch gateway instruction.

In a further aspect of the present invention a system and method is provided for performing a three input bitwise Boolean operation in a single instruction. A novel method described in detail in another section is used to encode the eight possible output states of such an operation into only seven bits and decoding these seven bits back into the eight states.

In yet a further aspect to the present invention a system and method is described for improving the branch prediction of simple repetitive loops of code. The method includes providing a count field for indicating how many times a branch is likely to be taken before it is not taken which enhances the ability to properly predict both the initial and final branches of simple loops when a compiler can determine the number of iterations that the loop will be performed. This improves performance by avoiding misprediction of the branch at the end of a loop.

Zeus performs all instructions as if executed one by one in order with precise exceptions always available. Consequently code that ignores the subsequent discussion of Zeus pipeline implementations will still perform correctly. However the highest performance of the Zeus processor is achieved only by matching the ordering of instructions to the characteristics of the pipeline. In the following discussion the general characteristics of all Zeus implementations precede discussion of specific choices for specific implementations.

Pipe lining in general refers to hardware structures that overlap various stages of execution of a series of instructions so that the time required to perform the series of instructions is less than the sum of the times required to perform each of the instructions separately. Additionally pipelines carry to connotation of a collection of hardware structures which have a simple ordering and where each structure performs a specialized function.

The diagram below shows the timing of what has become a canonical pipeline structure for a simple RISC processor with time on the horizontal axis increasing to the right and successive instructions on the vertical axis going downward. The stages I R E M and W refer to units which perform instruction fetch register file fetch execution data memory fetch and register file write. The stages are aligned so that the result of the execution of an instruction may be used as the source of the execution of an immediately following instruction as seen by the fact that the end of an E stage bold in line 1 lines up with the beginning of the E stage bold in line 2 immediately below. Also it can be seen that the result of a load operation executing in stages E and M bold in line 3 is not available in the immediately following instruction line 4 but may be used two cycles later line 5 this is the cause of the load delay slot seen on some RISC processors.

In the diagrams below we simplify the diagrams somewhat by eliminating the pipe stages for instruction fetch register file fetch and register file write which can be understood to precede and follow the portions of the pipelines diagrammed. The diagram above is shown again in this new format showing that the canonical pipeline has very little overlap of the actual execution of instructions.

A superscalar pipeline is one capable of simultaneously issuing two or more instructions which are independent in that they can be executed in either order and separately producing the same result as if they were executed serially. The diagram below shows a two way superscalar processor where one instruction may be a register to register operation using stage E and the other may be a register to register operation using stage A or a memory load or store using stages A and M .

A superpipelined pipeline is one capable is issuing simple instructions frequently enough that the result of a simple instruction must be independent of the immediately following one or more instructions. The diagram below shows a two cycle superpipelined implementation 

In the diagrams below pipeline stages are labelled with the type of instruction that may be performed by that stage. The position of the stage further identifies the function of that stage as for example a load operation may require several L stages to complete the instruction.

Zeus architecture provides for implementations designed to fetch and execute several instructions in each clock cycle. For a particular ordering of instruction types one instruction of each type may be issued in a single clock cycle. The ordering required is A L E S B in other words a register to register address calculation a memory load a register to register data calculation a memory store and a branch. Because of the organization of the pipeline each of these instructions may be serially dependent. Instructions of type E include the fixed point execute phase instructions as well as floating point and digital signal processing instructions. We call this form of pipeline organization superstring readers with a background in theoretical physics may have seen this term in an other unrelated context because of the ability to issue a string of dependent instructions in a single clock cycle as distinguished from superscalar or superpipelined organizations which can only issue sets of independent instructions.

These instructions take from one to four cycles of latency to execute and a branch prediction mechanism is used to keep the pipeline filled. The diagram below shows a box for the interval between issue of each instruction and the completion. Bold letters mark the critical latency paths of the instructions that is the periods between the required availability of the source registers and the earliest availability of the result registers. The A L critical latency path is a special case in which the result of the A instruction may be used as the base register of the L instruction without penalty. E instructions may require additional cycles of latency for certain operations such as fixed point multiply and divide floating point and digital signal processing operations.

Zeus architecture provides an additional refinement to the organization defined above in which the time permitted by the pipeline to service load operations may be flexibly extended. Thus the front of the pipeline in which A Land B type instructions are handled is decoupled from the back of the pipeline in which E and S type instructions are handled. This decoupling occurs at the point at which the data cache and its backing memory is referenced similarly a FIFO that is filled by the instruction fetch unit decouples instruction cache references from the front of the pipeline shown above. The depth of the FIFO structures is implementation dependent i.e. not fixed by the architecture.

With the super spring organization the latency of load instructions can be hidden as execute instructions are deferred until the results of the load are available. Nevertheless the execution unit still processes instructions in normal order and provides precise exceptions.

This technique is not employed in the initial Zeus implementation though it was present in an earlier prototype implementation.

A difficulty of superpipelining is that dependent operations must be separated by the latency of the pipeline and for highly pipelined machines the latency of simple operations can be quite significant. The Zeus superthread pipeline provides for very highly pipelined implementations by alternating execution of two or more independent threads. In this context a thread is the state required to maintain an independent execution the architectural state required is that of the register file contents program counter privilege level local TB and when required exception status. Ensuring that only one thread may handle an exception at one time may minimize the latter state exception status. In order to ensure that all threads make reasonable forward progress several of the machine resources must be scheduled fairly.

An example of a resource that is critical that it be fairly shared is the data memory cache subsystem. In a prototype implementation Zeus is able to perform a load operation only on every second cycle and a store operation only on every fourth cycle. Zeus schedules these fixed timing resources fairly by using a round robin schedule for a number of threads that is relatively prime to the resource reuse rates. For this implementation five simultaneous threads of execution ensure that resources which may be used every two or four cycles are fairly shared by allowing the instructions which use those resources to be issued only on every second or fourth issue slot for that thread.

In the diagram below the thread number which issues an instruction is indicated on each clock cycle and below it a list of which functional units may be used by that instruction. The diagram repeats every 20 cycles so cycle 20 is similar to cycle 0 cycle 21 is similar to cycle 1 etc. This schedule ensures that no resource conflict occur between threads for these resources. Thread 0 may issue an E L S or B on cycle 0 but on its next opportunity cycle 5 may only issue E or B and on cycle 10 may issue E L or B and on cycle 15 may issue E or B.

When seen from the perspective of an individual thread the resource use diagram looks similar to that of the collection. Thus an individual thread may use the load unit every two instructions and the store unit every four instructions.

A Zeus Superthread pipeline with 5 simultaneous threads of execution permits simple operations such as register to register add G.ADD to take 5 cycles to complete allowing for an extremely deeply pipelined implementation.

The intial Zeus implementation performs simultaneous multithreading among 4 threads. Each of the 4 threads share a common memory system a common T unit. Pairs of threads share two G units one X unit and one E unit. Each thread individually has two A units. A fair allocation scheme balances access to the shared resources by the four threads.

Zeus does not have delayed branch instructions and so relies upon branch or fetch prediction to keep the pipeline full around unconditional and conditional branch instructions. In the simplest form of branch prediction as in Zeus s first implementation a taken conditional backward toward a lower address branch predicts that a future execution of the same branch will be taken. More elaborate prediction may cache the source and target addresses of multiple branches both conditional and unconditional and both forward and reverse.

The hardware prediction mechanism is tuned for optimizing conditional branches that close loops or express frequent alternatives and will generally require substantially more cycles when executing conditional branches whose outcome is not predominately taken or not taken. For such cases of unpredictable conditional results the use of code that avoids conditional branches in favor of the use of compare set and multiplex instructions may result in greater performance.

Under some conditions the above technique may not be applicable for example if the conditional branch guards code which cannot be performed when the branch is taken. This may occur for example when a conditional branch tests for a valid non zero pointer and the conditional code performs a load or store using the pointer. In these cases the conditional branch has a small positive offset but is unpredictable. A Zeus pipeline may handle this case as if the branch is always predicted to be not taken with the recovery of a misprediction causing cancellation of the instructions which have already been issued but not completed which would be skipped over by the taken conditional branch. This conditional skip optimization is performed by the initial Zeus implementation and requires no specific architectural feature to access or implement.

A Zeus pipeline may also perform branch return optimization in which a branch link instruction saves a branch target address that is used to predict the target of the next returning branch instruction. This optimization may be implemented with a depth of one only one return address kept or as a stack of finite depth where a branch and link pushes onto the stack and a branch register pops from the stack. This optimization can eliminate the misprediction cost of simple procedure calls as the calling branch is susceptible to hardware prediction and the returning branch is predictable by the branch return optimization. Like the conditional skip optimization described above this feature is performed by the initial Zeus implementation and requires no specific architectural feature to access or implement.

Zeus implements two related instructions that can eliminate or reduce branch delays for conditional loops conditional branches and computed branches. The branch hint instruction has no effect on architectural state but informs the instruction fetch unit of a potential future branch instruction giving the addresses of both the branch instruction and of the branch target. The two forms of the instruction specify the branch instruction address relative to the current address as an immediate field and one form branch hint immediate specifies the branch target address relative to the current address as an immediate field and the other branch hint specifies the branch target address from a general register. The branch hint immediate instruction is generally used to give advance notice to the instruction fetch unit of a branch conditional instruction so that instructions at the target of the branch can be fetched in advance of the branch conditional instruction reaching the execution pipeline. Placing the branch hint as early as possible and at a point where the extra instruction will not reduce the execution rate optimizes performance. In other words an optimizing compiler should insert the branch hint instruction as early as possible in the basic block where the parcel will contain at most one other front end instruction.

When temporally adjacent instructions are executed by separate resources the results of the first instruction must generally be forwarded directly to the resource used to execute the second instruction where the result replaces a value which may have been fetched from a register file. Such forwarding paths use significant resources. A Zeus implementation must generally provide forwarding resources so that dependencies from earlier instructions within a string are immediately forwarded to later instructions except between a first and second execution instruction as described above. In addition when forwarding results from the execution units back to the data fetch unit additional delay may be incurred.

This section discusses the caches the translation mechanisms the memory interfaces and how the multiprocessor interface is used to maintain cache coherence.

In general terms the memory management starts from a local virtual address. The local virtual address is translated to a global virtual address by an L TB Local Translation Buffer . In turn the global virtual address is translated to a physical address by a GTB Global Translation Buffer . One of the addresses a local virtual address a global virtual address or a physical address is used to index the cache data and cache tag arrays and one of the addresses is used to check the cache tag array for cache presence. Protection information is assembled from the L TB GTB and optionally the cache tag to determine if the access is legal.

This form varies somewhat depending on implementation choices made. Because the L TB leaves the lower 48 bits of the address alone indexing of the cache arrays with the local virtual address is usually identical to cache arrays indexed by the global virtual address. However indexing cache arrays by the global virtual address rather than the physical address produces a coherence issue if the mapping from global virtual address to physical is many to one.

Starting from a local virtual address the memory management system performs three actions in parallel the low order bits of the virtual address are used to directly access the data in the cache a low order bit field is used to access the cache tag and the high order bits of the virtual address are translated from a local address space to a global virtual address space.

Following these three actions operations vary depending upon the cache implementation. The cache tag may contain either a physical address and access control information a physically tagged cache or may contain a global virtual address and global protection information a virtually tagged cache .

For a physically tagged cache the global virtual address is translated to a physical address by the GTB which generates global protection information. The cache tag is checked against the physical address to determine a cache hit. In parallel the local and global protection information is checked.

For a virtually tagged cache the cache tag is checked against the global virtual address to determine a cache hit and the local and global protection information is checked. If the cache misses the global virtual address is translated to a physical address by the GTB which also generates the global protection information.

The 64 bit global virtual address space is global among all tasks. In a multitask environment requirements for a task local address space arise from operations such as the UNIX fork function in which a task is duplicated into parent and child tasks each now having a unique virtual address space. In addition when switching tasks access to one task s address space must be disabled and another task s access enabled.

Zeus provides for portions of the address space to be made local to individual tasks with a translation to the global virtual space specified by four 16 bit registers for each local virtual space. The registers specify a mask selecting which of the high order 16 address bits are checked to match a particular value and if they match a value with which to modify the virtual address. Zeus avoids setting a fixed page size or local address size these can be set by software conventions.

There are as many LTB as threads and up to 2 8 entries per L TB. Each entry is 128 bits with the high order 64 bits reserved. illustrates the physical address of a LTB entry for thread th entry en byte b.

A failure to match a L TB entry results either in an exception or an access to the global virtual address space depending on privilege level. A single bit selected by the privilege level active for the access from a four bit control register field global access ga determines the result. If gais zero 0 the failure causes an exception if it is one 1 the failure causes the address to be directly used as a global virtual address without modification.

For tasks that have global access disabled at their current privilege level failure to match a LTB entry causes an exception. The exception handler may load a LTB entry and continue execution thus providing access to an arbitrary number of local virtual address ranges.

When failure to match a LTB entry does not cause an exception instructions may access any region in the local virtual address space when a LTB entry matches and may access regions in the global virtual address space when no LTB entry matches. This mechanism permits privileged code to make judicious use of local virtual address ranges which simplifies the manner in which privileged code may manipulate the contents of a local virtual address range on behalf of a less privileged client. Note however that under this model an LTB miss does not cause an exception directly so the use of more local virtual address ranges than LTB entries requires more care the local virtual address ranges should be selected so as not to overlap with the global virtual address ranges and GTB misses to LVA regions must be detected and cause the handler to load an LTB entry.

Each thread has an independent L TB so that threads may independently define local translation. The size of the LTB for each thread is implementation dependent and defined as the LE parameter in the architecture Description register. LE is the log of the number of entries in the local TB per thread an implementation may define LE to be a minimum of 0 meaning one LTB entry per thread or a maximum of 3 meaning eight LTB entries per thread. For the initial Zeus implementation each thread has two entries and LE 1.

A minimum implementation of a LTB context is a single set of lm la lx lp registers per thread. However the need for the LTB to translate both code addresses and data addresses imposes some limits on the use of the LTB in such systems. We need to be able to guarantee forward progress. With a single LTB set per thread either the code or the data must use global addresses or both must use the same local address range as must the LTB and GTB exception handler. To avoid this restriction the implementation must be raised to two sets per thread at least one for code and one for data to guarantee forward progress for arbitrary use of local addresses in the user code but still be limited to using global addresses for exception handlers .

As shown in a single set LTB context may be further simplified by reserving the implementation of the 1m and 1a registers setting them to a read only zero value Note that in such a configuration only a single LA region can be implemented.

If the largest possible space is reserved for an address space identifier the virtual address is partitioned as shown in . Any of the bits marked as local below may be used as offset as desired.

To improve performance an implementation may perform the L TB translation on the value of the base register rc or unincremented program counter provided that a check is performed which prohibits changing the unmasked upper 16 bits by the add or increment. If this optimization is provided and the check fails an AccessDisallowedByVirtualAddress should be signaled. If this optimization is provided the architecture Description parameter LB 1. Otherwise LTB translation is performed on the local address la no checking is required and LB 0.

As shown in the LTB protect field controls the minimum privilege level required for each memory action of read r write w execute x and gateway g as well as memory and cache attributes of write allocate wa detail access da strong ordering so cache disable cd and write through wt . These fields are combined with corresponding bits in the GTB protect field to control these attributes for the mapped memory region.

Global virtual addresses which fail to be accessed in either the LZC the MTB the BTB or PTB are translated to physical references in a table here named the Global Translation Buffer GTB .

Each processor may have one or more GTB s with each GTB shared by one or more threads. The parameter GT the base two log of the number of threads which share a GTB and the parameter T the number of threads allow computation of the number of GTBs T 2 and the number of threads which share each GTB 2 .

If there are two GTBs and four threads GT 1 T 4 GTB 0 services references from threads 0 and 1 and GTB 1 services references from threads 2 and 3. In the first implementation there is one GTB shared by all four threads. GT 2 T 4 . The GTB has 128 entries G 7 .

Per clock cycle each GTB can translate one global virtual address to a physical address yielding protection information as a side effect.

A GTB miss causes a software trap. This trap is designed to permit a fast handler for GlobalTBMiss to be written in software by permitting a second GTB miss to occur as an exception rather than a machine check.

There may be as many GTB as threads and up to is entries per GTB. illustrates the physical address of a GTB entry for thread th entry en byte b. Note that in the low order GT bits of the th value are ignored reflecting that 2threads share a single GTB. A single GTB shared between threads appears multiple times in the address space. Referring to GTB entries are packed together so that entries in a GTB are consecutive.

If the entire contents of the GTB entry is zero 0 the entry will not match any global address at all. If a zero value is written a zero value is read for the GTB entry. Software must not write a zero value for the gs field unless the entire entry is a zero value.

It is an error to write GTB entries that multiply match any global address all GTB entries must have unique non overlapping coverage of the global address space. Hardware may produce a machine check if such overlapping coverage is detected or may produce any physical address and protection information and continue execution.

Limiting the GTB entry size to 128 bits allows up to replace entries atomically with a single store operation which is less complex than the previous design in which the mask portion was first reduced then other entries changed then the mask is expanded. However it is limiting the amount of attribute information or physical address range we can specify. Consequently we are encoding the size as a single additional bit to the global address in order to allow for attribute information.

Because the processor contains multiple threads of execution even when taking virtual memory exceptions it is possible for two threads to nearly simultaneously invoke software GTB miss exception handlers for the same memory region. In order to avoid producing improper GTB state in such cases the GTB includes access facilities for indivisibly checking and then updating the contents of the GTB as a result of a memory write to specific addresses.

A 128 bit write to the address GTBUpdateFill fill 1 as a side effect causes first a check of the global address specified in the data against the GTB. If the global address check results in a match the data is directed to write on the matching entry. If there is no match the address specified by GTBLast is used and GTBLast is incremented. If incrementing GTBLast results in a zero value GTBLast is reset to GTBFirst and GTBBump is set. Note that if the size of the updated value is not equal to the size of the matching entry the global address check may not adequately ensure that no other entries also cover the address range of the updated value. The operation is unpredictable if multiple entries match the global address.

The GTBUpdateFill register is a 128 bit memory mapped location to which a write operation performs the operation defined above. A read operation returns a zero value. The format of the GTBUpdateFill register is identical to that of a GTB entry.

An alternative write address GTBUpdate fill 0 updates a matching entry but makes no change to the GTB if no entry matches. This operation can be used to indivisibly update a GTB entry as to protection or physical address information.

There may be as many GTB as threads and up to 2 registers per GTB 5 registers are implemented . illustrates the physical address of a GTB control register for thread th register m byte b. Note that in the low order GT bits of the th value are ignored reflecting that 2threads share single GTB registers. A single set of GTB registers shared between threads appears multiple times in the address space and manipulates the GTB of the threads with which the registers are associated.

The GTBUpdate register is a 128 bit memory mapped location to which a write operation performs the operation defined above. A read operation returns a zero value. The format of the GTBUpdateFill register is identical to that of a GTB entry. illustrates the registers GTBLast GTBFirst and GTBBump. The registers GTBLast GTBFirst and GTBBump are memory mapped. As shown in the GTBLast and GTBFirst registers are G bits wide and the GTBBump register is one bit.

The address units of each of the four threads provide up to two global virtual addresses of load store or memory instructions for a total of eight addresses. LTB units associated with each thread translate the local addresses into global addresses. The LZC operates on global addresses. MTB BTB and PTB units associated with each thread translate the global addresses into physical addresses and cache addresses. A PTB unit associated with each thread produces physical addresses and cache addresses for program counter references. this is optional as by limiting address generation to two per thread the MTB can be used for program references. 

Cache addresses are presented to the LOC as required and physical addresses are checked against cache tags as required.

The LZC has two banks each servicing up to four requests. The LOC has eight banks each servicing at most one request.

Assuming random request addresses shows the expected rate at which requests are serviced by multi bank multi port memories that have 8 total ports and divided into 1 2 4 or 8 interleaved banks. The LZC is 2 banks each with 4 ports and the LOC is 8 banks each 1 port.

Note a small difference between applying 12 references versus references for the LOC 6.5 vs 5.2 and for the LZC 7.8 vs. 6.9 . This suggests that simplifying the system to produce two address per thread program load store or two load store will not overly hurt performance. A closer simulation taking into account the sequential nature of the program and load store traffic may well yield better numbers as threads will tend to line up in non interfering patterns and program microcaching reduces program fetching.

Note significant differences between 8 port systems and 16 port systems even when used with a maximum of 8 applied references. In particular a 16 bank 1 port system is better than a 4 bank 2 port system with more than 6 applied references. Current layout estimates would require about a 14 area increase assuming no savings from smaller simpler sense amps to switch to a 16 port LOC with a 22 increase in 8 reference throughput.

A program micro cache PMC which holds only program code for each thread may optionally exist and does exist for the initial implementation. The program microcache is flushed by reset or by executing a B.BARRIER instruction. The program microcache is always clean and is not snooped by writes or otherwise kept coherent except by flushing as indicated above. The microcache is not altered by writing to the L TB or GTB and software must execute a B.BARRIER instruction before expecting the nEw contents of the L TB or GTB to affect determination of PMC hit or miss status on program fetches.

In the initial implementation the program microcache holds simple loop code. The microcache holds two separately addressed cache lines. Branches or execution beyond this region cause the microcache to be flushed and refilled at the new address provided that the addresses are executable by the current thread. The program microcache uses the B.HINT and B.HINT.I to accelerate fetching of program code when possible. The program microcache generally functions as a prefetch buffer except that short forward or backward branches within the region covered maintain the contents of the microcache.

Program fetches into the microcache are requested on any cycle in which less than two load store addresses are generated by the address unit unless the microcache is already full. System arbitration logic should give program fetches lower priority than load store references when first presented then equal priority if the fetch fails arbitration a certain number of times. The delay until program fetches have equal priority should be based on the expected time the program fetch data will be executed it may be as small as a single cycle or greater for fetches which are far ahead of the execution point.

A wide microcache WMC which holds only data fetched for wide W instructions may optionally exist and does exist for the initial implementation for each unit which implements one or more wide W instructions.

The wide W instructions each operate on a block of data fetched from memory and the contents of one or more registers producing a result in a register. Generally the amount of data in the block exceeds the maximum amount of data that the memory system can supply in a single cycle so caching the memory data is of particular importance. All the wide W instructions require that the memory data be located at an aligned address an address that is a multiple of the size of the memory data which is always a power of two.

The wide W instructions are performed by functional units which normally perform execute or back end instructions though the loading of the memory data requires use of the access or front end functional units. To minimize the use of the front end functional units special rules are used to maintain the coherence of a wide microcache WMC .

Execution of a wide W instruction has a residual effect of loading the specified memory data into a wide microcache WMC . Under certain conditions a future wide W instruction may be able to reuse the WMC contents.

First of all any store or cache coherency action on the physical addresses referenced by the WMC will invalidate the contents. The minimum translation unit of the virtual memory system 256 bytes defines the number of physical address blocks which must be checked by any store. A WMC for the W.TABLE instruction may be as large as 4096 bytes and so requires as many as 16 such physical address blocks to be checked for each WMC entry. A WMC for the W.SWITCH or W.MUL. instructions need check only one address block for each WMC entry as the maximum size is 128 bytes.

By making these checks on the physical addresses we do not need to be concerned about changes to the virtual memory mapping from virtual to physical addresses and the virtual memory state can be freely changed without invalidating any WMC.

Absent any of the above changes the WMC is only valid if it contains the contents relevant to the current wide W instruction. To check this with minimal use of the front end units each WMC entry contains a first tag with the thread and address register for which it was last used. If the current wide W instruction uses the same thread and address register it may proceed safely. Any intervening writes to that address register by that thread invalidates the WMC thread and address register tag.

If the above test fails the front end is used to fetch the address register and check its contents against a second WMC tag with the physical addresses for which it was last used. If the tag matches it may proceed safely. As detailed above any intervening stores or cache coherency action by any thread to the physical addresses invalidates the WMC entry.

If both the above tests fail for all relevant WMC entries there is no alternative but to load the data from the virtual memory system into the WMC. The front end units are responsible for generating the necessary addresses to the virtual memory system to fetch the entire data block into a WMC.

For the first implementation it is anticipated that there be eight WMC entries for each of the two X units for W. SWITCH instructions eight WMC entries for each of the two E units for W.MUL instructions and four WMC entries for the single T unit. The total number of WMC address tags requires is 8 2 1 8 2 1 4 1 16 96 entries.

The number of WMC address tags can be substantially reduced to 32 4 36 entries by making an implementation restriction requiring that a single translation block be used to translate the data address of W.TABLE instructions. With this restriction each W.TABLE WMC entry uses a contiguous and aligned physical data memory block for which a single address tag can contain the relevant information. The size of such a block is a maximum of 4096 bytes. The restriction can be checked by examining the size field of the referenced GTB entry.

The innermost cache level here named the Level Zero Cache LZC is fully associative and indexed by global address. Entries in the LZC contain global addresses and previously fetched data from the memory system. The LZC is an implementation feature not visible to the Zeus architecture.

Entries in the LZC are also used to hold the global addresses of store instructions that have been issued but not yet completed in the memory system. The LZC entry may also contain the data associated with the global address as maintained either before or after updating with the store data. When it contains the post store data results of stores may be forwarded directly to the requested reference.

With an LZC hit data is returned from the LZC data and protection from the LZC tag. No LOC access is required to complete the reference.

All loads and program fetches are checked against the LZC for conflicts with entries being used as store buffer. On a LZC hit on such entries if the post store data is present data may be returned by the LZC to satisfy the load or program fetch. If the post store data is not present the load or program fetch must stall until the data is available.

With an LZC miss a victim entry is selected and if dirty the victim entry is written to the LOC. The LOC cache is accessed and a valid LZC entry is constructed from data from the LOC and tags from the LOC protection information.

All stores are checked against the LZC for conflicts and further cause a new entry in the LZC or take over a previously clean LZC entry for this purpose. Unaligned stores may require two entries in the LZC. At time of allocation the address is filled in.

Two operations then occur in parallel 1 for write back cached references the remaining bytes of the hexlet are loaded from the LOC or LZC and 2 the addressed bytes are filled in with data from data path. If an exception causes the store to be purged before retirement the LZC entry is marked invalid and not written back. When the store is retired the LZC entry can be written back to LOC or external interface.

The LZC contains 16 fully associative entries that may each contain a single hex let of data at even hexlet addresses LZCE and another 16 entries for odd hex let addresses LZCO . The maximum capacity of the LZC is 16 32 512 bytes.

The tags for these entries are indexed by global virtual address 63..5 and contain access control information detailed below.

The address of entries accessed associatively is also encoded into binary and provided as output from the tags for use in updating the LZC through its write ports.

The next cache level here named the Level One Cache LOC is four set associative and indexed by the physical address. The eight memory addresses are partitioned into up to eight addresses for each of eight independent memory banks. The LOC has a cache block size of 256 bytes with triclet 32 byte sub blocks.

The LOC may be partitioned into two sections one part used as a cache and the remainder used as niche memory. Niche memory is at least as fast as cache memory but unlike cache never misses to main memory. Niche memory may be placed at any virtual address and has physical addresses fixed in the memory map. The 01 field in the control register configures the partitioning of LOC into cache memory and niche memory.

The LOC data memory is 256 8 4 128 2 bits depth to hold 256 entries in each of four sets each entry consisting of one hexlet of data 128 bits one bit of parity and one spare bit. The additional 8 entries in each of four sets hold the LOC tags with 128 bits per entry for of the total cache using 512 bytes per data memory and 4K bytes total.

There are 128 cache blocks per set or 512 cache blocks total. The maximum capacity of the LOC is 128k bytes. Used as a cache the LOC is partitioned into 4 sets each 32k bytes. Physically the LOC is partitioned into 8 interleaved physical blocks each holding 16k bytes.

The physical address pais partitioned as below into a 52 to 54 bit tag three to five bits are duplicated from the following field to accommodate use of portion of the cache as niche 8 bit address to the memory bank 7 bits are physical address pa 1 bit is virtual address v 3 bit memory bank select bn and 4 bit byte address bt . All access to the LOC are in units of 128 bits hexlets so the 4 bit byte address bt does not apply here. The shaded field pa v is translated via n1 to a cache identifier ci and set identifier si and presented to the LOC as the LOC address to LOC bank bn.

The LOC tag consists of 64 bits of information including a 52 to 54 bit tag and other cache state information. Only one MTB entry at a time may contain a LOC tag.

With 256 byte cache lines there are 512 cache blocks. At 64 bits per tag the cache tags require 4k bytes of storage. This storage is adjacent to the LOC data memory itself using physical addresses 1024..1055. Alternatively see detailed Description below physical addresses 0.31 may be used.

To access the LOC a global address is supplied to the Micro Tag Buffer MTB which associatively looks up the global address into a table holding a subset of the LOC tags. In particular each MTB table entry contains the cache index derived from physical address bits .. ci 7 bits and set identifier si 2 bits required to access the LOC data. Each MTB table entry also contains the protection information of the LOC tag.

With an MTB hit protection information is supplied from the MTB. The MTB supplies the resulting cache index ci from the MTB set identifier si 2 bits and virtual address bit v from the LA which are applied to the LOC data bank selected from bits .. of the LA. The diagram below shows the address presented to LOC data bank bn.

With an MTB miss the GTB described below is referenced to obtain a physical address and protection information.

To select the cache line a 7 bit niche limit register nl is compared against the value of pafrom the GTB. If pa

The address modifier am is 1 0 . The bt field specifies the least significant bit used for tag and is nl

Values for nl in the range 113..127 require more than 52 physical address tag bits in the LOC tag and a requisite reduction in LOC features. Note that the presence of bits .. of the physical address in the LOC tag is a result of the possibility that with am 64..127 the cache index value ci cannot be relied upon to supply bit ... Bits .. can be safely inferred from the cache index value ci so long as nl is in the range 0..124. When nl is in the range 113..127 the da bit is used for bit of the physical address so the Tag detail access bit is suppressed. When nl is in the range 121..127 the vs bit is used for bit of the physical address so victim selection is performed without state bits in the LOC tag. When nl is in the range 125.127 the set associativity is decreased so that siis used for bit of the physical address and when nl is 127 siis used for bit of the physical address.

Four tags are fetched from the LOC tags and compared against the PA to determine which of the four sets contain the data. The four tags are contained in two consecutive banks they may be simultaneously or independently fetched. The diagram below shows the address presented to LOC data bank ci si .

Note that the CT architecture Description variable is present in the above address. CT describes whether dedicated locations exist in the LOC for tags at the next power of two boundary above the LOC data. The niche mapping mechanism can provide the storage for the LOC tags so the existence of these dedicated tags is optional If CT 0 addresses at the beginning of the LOC 0.31 for this implementation are used for LOC tags and the 01 value should be adjusted accordingly by software.

The LOC address ci si uniquely identifies the cache location and this LOC address is associatively checked against all MTB entries on changes to the LOC tags such as by cache block replacement bus snooping or software modification. Any matching MTB entries are flushed even if the MTB entry specifies a different global address this permits address aliasing the use of a physical address with more than one global address.

With an LOC miss a victim set is selected LOC victim selection is described below whose contents if any sub block is modified is written to the external memory. A new LOC entry is constructed with address and protection information from the GTB and data fetched from external memory.

The LOC data memory banks are accessed implicitly by cached memory accesses to any physical memory location as shown above. The LOC data memory banks are also accessed explicitly by uncached memory accesses to particular physical address ranges. The address mapping of these ranges is designed to facilitate use of a contiguous portion of the LOC cache as niche memory.

Within the explicit LOC data range starting from a physical address pa the diagram below shows the LOC address pa presented to LOC data bank pa .

The table below shows the LOC data memory bank and address referenced by byte address offsets in the explicit LOC data range. Note that this mapping includes the addresses use for LOC tags.

LOC cells may be fabricated with marginal parameters for which changes in clock timing or power supply voltage may cause these LOC cells to fail or pass. When testing the LOC while the part is in a normal circuit environment rather than a special test environment with changeable power supply levels cells with marginal parameters may not reliably fail testing.

To combat this problem two bits of the control register LOC stress may be set to stress the circuit environment while testing. Under normal operation these bits are cleared 00 while during stress testing one or more of these bits are set 01 10 11 . Self testing should be performed in each of the environment settings and the detected failures combined together to produce a reliable test for cells with marginal parameters.

Each LOC bank has three additional bits of data storage for each 128 bits of memory data for a total of 131 bits . One of these bits is used to retain odd parity over the 128 bits of memory data and the other two bits are spare which can be pressed into service by setting a non zero value in the LOC redundancy control register for that bank.

Each row of a LOC bank contains 131 bits 128 bits of memory data one bit for parity and two spare bits 

Each bit set in the control word causes the corresponding data bit to be selected from a bit address increased by two output data and control or spare data and control parity and or spareand 

The LOC redundancy control register has 129 bits but is written with a 128 bit value. To set the pc bit in the LOC redundancy control a value is written to the control with either bit set 1 or bit set 1 . To set bit of the LOC redundancy control a value is written to the control with both bit set 1 and set 1 . When the LOC redundancy control register is read the process is reversed by selecting the pc bit instead of control bit for the value of bit if control bit is zero 0 .

This system can remove one defective column at an even bit position and one defective column at an odd bit position within each LOC block. For each defective column location x LOC control bit must be set at bits x x 2 x 4 x 6 . . . . If the defective column is in the parity location bit then set bit only. The following table defines the control bits for parity bit and bit other control bits are same as values written 

The LOC redundancy controls are accessed explicitly by uncached memory accesses to particular physical address ranges.

Fields in the LTB GTB and cache tag control various attributes of the memory access in the specified region of memory. These include the control of cache consultation updating allocation prefetching coherence ordering victim selection detail access and cache prefetching.

The cache may be used in one of five ways depending on a three bit cache control field 20 cc in the LTB and GTB. The cache control field may be set to one of seven states NC CD WT WA PF SS and LS 

The Zeus processor controls cc as an attribute in the LTB and GTB thus software may set this attribute for certain address ranges and clear it for others. A three bit field indicates the choice of caching according to the table above. The maximum of the three bit cache control field cc values of the LTB and GTB indicates the choice of caching according to the table above.

No Cache NC is an attribute that can be set on a LTB or GTB translation region to indicate that the cache is to be not to be consulted. No changes to the cache state result from reads or writes with this attribute set except for accesses that directly address the cache via memory mapped region .

Cache Disable CD is an attribute that can be set on a LTB or GTB translation region to indicate that the cache is to be consulted and updated for cache lines which are already present but no new cache lines or sub blocks are to be allocated when the cache does not already contain the addressed memory contents.

The Socket 7 bus also provides a mechanism for supporting chip sets to decide on each access whether data is to be cached using the CACHE and KEN signals. Using these signals external hardware may cause a region selected as WT WA or PF to be treated as CD. This mechanism is only active on the first such access to a memory region if caching is enabled as the cache may satisfy subsequent references without a bus transaction.

Write Through WT is an attribute that can be set on a LTB or GTB translation region to indicate that the writes to the cache must also immediately update backing memory. Reads to addressed memory that is not present in the cache cause cache lines or sub blocks to be allocated. Writes to addressed memory that is not present in the cache does not modify cache state.

The Socket 7 bus also provides a mechanism for supporting chip sets to decide on each access whether data is to be written through using the PWT and WB WT signals. Using these signals external hardware may cause a region selected as WA or PF to be treated as WT. This mechanism is only active on the first write to each region of memory as on subsequent references if the cache line is in the Exclusive or Modified state and writeback caching is enabled on the first reference no subsequent bus operation occurs at least until the cache line is flushed.

Write allocate WA is an attribute that can be set of a LTB or GTB translation region to indicate that the processor is to allocate a memory block to the cache when the data is not previously present in the cache and the operation to be performed is a store. Reads to addressed memory that is not present in the cache cause cache lines or sub blocks to be allocated. For cacheable data write allocate is generally the preferred policy as allocating the data to the cache reduces further bus traffic for subsequent references loads or stores or the data. Write allocate never occurs for data which is not cached. A write allocate brings in the data immediately into the Modified state.

Other Socket 7 processors have the ability to inhibit write allocate to cached locations under certain conditions related by the address range. K6 for example can inhibit write allocate in the range of 15 16 Mbyte or for all addresses above a configurable limit with 4 Mbyte granularity. Pentium has the ability to label address ranges over which write allocate can be inhibited.

Prefetch PF is an attribute that can be set on a LTB or GTB translation region to indicate that increased prefetching is appropriate for references in this region. Each program fetch load or store to a cache line that or does not already contain all the sub blocks causes a prefetch allocation of the remaining sub blocks. Cache misses cause allocation of the requested sub block and prefetch allocation of the remaining sub blocks. Prefetching does not necessarily fill in the entire cache line as prefetch memory references are performed at a lower priority to other cache and memory reference traffic. A limited number of prefetches as low as one in the initial implementation can be queued the older prefetch requests are terminated as new ones are created.

In other respects the PF attribute is handled in the manner of the WA attribute. Prefetching is considered an implementation dependent feature and an implementation may choose to implement region with the PF attribute exactly as with the WA attribute.

Implementations may perform even more aggressive prefetching in future versions. Data may be prefetched into the cache in regions that are cacheable as a result of program fetches loads or stores to nearby addresses. Prefetches may extend beyond the cache line associated with the nearby address. Prefetches shall not occur beyond the reach of the GTB entry associated with the nearby address. Prefetching is terminated if an attempted cache fill results in a bus response that is not cacheable. Prefetches are implementation dependent behavior and such behavior may vary as a result of other memory references or other bus activity.

SubStream SS is an attribute that can be set on a LTB or GTB translation region to indicate that references in this region are to be selected as the next victim on a cache miss. In particular cache misses which normally place the cache line in the last to be victim state instead place the cache line in the first to be victim state except relative to cache lines in the I state.

In other respects the SS attribute is handled in the manner of the WA attribute. SubStream is considered an implementation dependent feature and an implementation may choose to implement region with the SS attribute exactly as with the WA attribute.

The SubStream attribute is appropriate for regions which are large data structures in which the processor is likely to reference the memory data just once or a small number of times but for which the cache permits the data to be fetched using burst transfers. By making it a priority for victimization these references are less likely to interfere with caching of data for which the cache performs a longer term storage function.

LineStream LS is an attribute that can be set on a LTB or GTB translation region to indicate that references in this region are to be selected as the next victim on a cache miss and to enable prefetching. In particular cache misses which normally place the cache line in the last to be victim state instead place the cache line in the first to be victim state except relative to cache lines in the I state.

In other respects the LS attribute is handled in the manner of the PF attribute. LineStream is considered an implementation dependent feature and an implementation may choose to implement region with the SS attribute exactly as with the PF or WA attributes.

Like the SubStream attribute the LineStream attribute is particularly appropriate for regions for which large data structures are used in sequential fashion. By prefetching the entire cache line memory traffic is performed as large sequential bursts of at least 256 bytes maximizing the available bus utilization.

Cache coherency is maintained by using MESI protocols for which each cache line 256 bytes the cache data is kept in one of four states M E S I 

In addition because the Socket 7 bus performs block transfers and cache coherency actions on triclet 32 byte blocks each cache line also maintains 8 bits of triclet valid tv state. Each bit of tv corresponds to a triclet sub block of the cache line bit for bytes 0..31 bit for bytes 32..63 bit for bytes 64..95 etc. If the tv bit is zero 0 the coherence state for that triclet is I no matter what the value of the mesi field. If the tv bit is one 1 the coherence state is defined by the mesi field. If all the tv bits are cleared 0 the mesi field must also be cleared indicating an invalid cache line.

Cache coherency activity generally follows the protocols defined by the Socket 7 bus as defined by Pentium and K6 2 documentation. However because the coherence state of a cache line is represented in only 10 bits per 256 bytes 1.25 bits per triclet a few state transitions are defined differently. The differences are a direct result of attempts to set triclets within a cache line to different IVIES states that cannot be represented. The data structure allows any triclet to be changed to the I state so state transitions in this direction match the Pentium processor exactly.

On the Pentium processor for a cache line in the M state an external bus Inquiry cycle that does not require invalidation INV 0 places the cache line in the S state. On the Zeus processor if no other triclet in the cache line is valid the mesi field is changed to S. If other triclets in the cache line are valid the mesi field is left unchanged and the tv bit for this triclet is turned off effectively changing it to the I state.

On the Pentium processor for a cache line in the E state an external bus Inquiry cycle that does not require invalidation INV 0 places the cache line in the S state. On the Zeus processor the mesi field is changed to S. If other triclets in the cache line are valid the MESI state is effectively changed to the S state for these other triclets.

On the Pentium processor for a cache line in the S state an internal store operation causes a write through cycle and a transition to the E state. On the Zeus processor the mesi field is changed to E. Other triclets in the cache line are invalidated by clearing the tv bits the MESI state is effectively changed to the I state for these other triclets.

When allocating data into the cache due to a store operation data is brought immediately into the Modified state setting the mesi field to M. If the previous mesi field is S other triclets which are valid are invalidated by clearing the tv bits. If the previous mesi field is E other triclets are kept valid and therefore changed to the M state.

When allocating data into the cache due to a load operation data is brought into the Shared state if another processor reports that the data is present in its cache or the mesi field is already set to S the Exclusive state if no processor reports that the data is present in its cache and the mesi field is currently E or I or the Modified state if the mesi field is already set to M. The determination is performed by driving PWT low and checking whether WB WT is sampled high if so the line is brought into the Exclusive state. See page 202 184 of the K6 2 documentation .

Strong ordering so is an attribute which permits certain memory regions to be operated with strong ordering in which all memory operations are performed exactly in the order specified by the program and others to be operated with weak ordering in which some memory operations may be performed out of program order.

The Zeus processor controls strong ordering as an attribute in the LTB and GTB thus software may set this attribute for certain address ranges and clear it for others. A one bit field indicates the choice of access ordering. A one 1 bit indicates strong ordering while a zero 0 bit indicates weak ordering.

With weak ordering the memory system may retain store operations in a store buffer indefinitely for later storage into the memory system or until a synchronization operation to any address performed by the thread that issued the store operation forces the store to occur. Load operations may be performed in any order subject to requirements that they be performed logically subsequent to prior store operations to the same address and subsequent to prior synchronization operations to any address. Under weak ordering it is permitted to forward results from a retained store operation to a future load operation to the same address. Operations are considered to be to the same address when any bytes of the operation are in common. Weak ordering is usually appropriate for conventional memory regions which are side effect free.

With strong ordering the memory system must perform load and store operations in the order specified. In particular strong ordered load operations are performed in the order specified and all load operations whether weak or strong must be delayed until all previous strong ordered store operations have been performed which can have a significant performance impact. Strong ordering is often required for memory mapped I O regions where store operations may have a side effect on the value returned by loads to other addresses. Note that Zeus has memory mapped I O such as the TB for which the use of strong ordering is essential to proper operation of the virtual memory system.

The EWBE signal in Socket 7 is of importance in maintaining strong ordering. When a write is performed with the signal inactive no further writes to E or M state lines may occur until the signal becomes active. Further details are given in Pentium documentation K6 2 documentation may not apply to this signal. 

One bit of the cache tag the vs bit controls the selection of which set of the four sets at a cache address should next be chosen as a victim for cache line replacement. Victim selectrion vs is an attribute associated with LOC cache blocks. No vs bits are present in the LTB or GTB.

There are two hexlets of tag information for a cache line and replacement of a set requires writing only one hexlet. To update priority information for victim selection by writing only one hexlet information in each hexlet is combined by an exclusive or. It is the nature of the exclusive or function that altering either of the two hexlets can change the priority information.

There are 4 3 2 1 24 possible orderings of the four sets which can be completely encoded in as few as 5 bits 2 bits to indicate highest priority 2 bits for second highest priority 1 bit for third highest priority and 0 bits for lowest priority. Dividing this up per set and duplicating per hexlet with the exclusive or scheme above requires three bits per set which suggests simply keeping track of the three highest priority sets with 2 bits each using 6 bits total and three bits per set.

The highest priority for replacement is set vsc second highest priority is set vsc third highest priority is set vsc and lowest priority is vsc vsc vsc. When the highest priority set is replaced it becomes the new lowest priority and the others are moved up computing a new vsc by 1..0

When replacing set vsc for a LineStream or SubStream replacement the priority for 20 replacement is unchanged unless another set contains the invalid MESI state computing a new vsc by 

Cache flushing and invalidations can cause cache lines to be cleared out of sequential order. Flushing or invalidating a cache line moves that set to highest priority. If that set is already highest priority the vsc is unchanged. If the set was second or third highest or lowest priority the vsc is changed to move that set to highest priority moving the others down. or 

Software must initialize the vs bits to a legal consistent state. For example to set the priority highest to lowest to 0 1 2 3 vsc must be set to Ob100100. There are many legal solutions that yield this vsc value such as vs 3 0 vs 2 0 vs 1 4 vs 0 4.

However the orderings are simplified in the first Zeus implementation to reduce the number of vs bits to one per set keeping a two bit vsc state value 32 10 

The highest priority for replacement is set vsc second highest priority is set vsc 1 third highest priority is set vsc 2 and lowest priority is vsc 3. When the highest priority set is replaced it becomes the new lowest priority and the others are moved up. Priority is given to sets with invalid MESI state computing a new vsc by 1 1 2 2 3 3 1

When replacing set vsc for a LineStream or SubStream replacement the priority for replacement is unchanged unless another set contains the invalid MESI state computing a new vsc by 1 1 2 2 3 3 

Cache flushing and invalidations can cause cache sets to be cleared out of sequential order. If the current highest priority for replacement is a valid set the flushed or invalidated set is made highest priority for replacement. 

Software must initialize the vs bits but any state is legal. For example to set the priority highest to lowest to 0 1 2 3 vsc must be set to ObOO. There are many legal solutions that yield this vsc value such as vs 3 0 vs 2 0 vs 1 0 vs 0 0.

To extend the full victim ordering scheme to eight sets 3 7 21 bits are needed which divided among two tags is 11 bits per tag. This is somewhat generous as the minimum required is 8 7 6 5 4 3 2 1 40320 orderings which can be represented in as few as 16 bits. Extending the full victim ordering four set scheme above to represent the first 4 priorities in binary but to use 2 bits for each of the next 3 priorities requires 3 3 3 3 2 2 2 18 bits. Representing fewer distinct orderings can further reduce the number of bits used. As an extreme example using the simplified scheme above with eight sets requires only 3 bits which divided among two tags is 2 bits per tag.

At extreme values of the niche limit register nl in the range 121..124 the bit normally used to hold the vs bit is usurped for use as a physical address bit. Under these conditions no vsc value is maintained per cache line instead a single global vsc value is used to select victims for cache replacement. In this case the cache consists of four lines each with four sets. On each 10 replacement a new si valus is computed from 1

At even more extreme values of the niche limit register nl in the range 125..127 not only is the bit normally used to hold the vs bit is usurped for use as a physical address bit but there is a deficit of one or two physical address bits. In this case the number of sets can be reduced to encode physical address bits into the victim selection allowing the choice of set to indicate physical address bits or bits ... On each replacement a new vsc valus is computed from 1 127 

Detail access is an attribute which can be set on a cache block or translation region to indicate that software needs to be consulted on each potential access to determine whether the access should proceed or not. Setting this attribute causes an exception trap to occur by which software can examine the virtual address by for example locating data in a table and if indicated causes the processor to continue execution. In continuing ephemeral state is set upon returning to the re execution of the instruction that prevents the exception trap from recurring on this particular re execution only. The ephemeral state is cleared as soon as the instruction is either completed or subject to another exception so DetailAccess exceptions can recur on a subsequent execution of the same instruction. Alternatively if the access is not to proceed execution has been trapped to software at this point which can abort the thread or take other corrective action.

The detail access attribute permits specification of access parameters over memory region on arbitrary byte boundaries. This is important for emulators which must prevent store access to code which has been translated and for simulating machines which have byte granularity on segment boundaries. The detail access attribute can also be applied to debuggers which have the need to set breakpoints on byte level data or which may use the feature to set code breakpoints on instruction boundaries without altering the program code enabling breakpoints on code contained in ROM.

A one bit field indicates the choice of detail access. A one 1 bit indicates detail access while a zero 0 bit indicates no detail access. Detail access is an attribute that can be set by the LTB the GTB or a cache tag.

The table below indicates the proper status for all potential values of the detail access bits in the LTB GTB and Tag 

The first eight rows show appropriate activities when all three bits are available. The detail access attributes for the LTB GTB and cache tag work together to define whether and which kind of detail access exception trap occurs. Generally setting a single attribute bit causes an exception while setting two bits inhibits such exceptions. In this way a detail access exception can be narrowed down to cause an exception over a specified region of memory Software generally will set the cache tag detail access bit only for regions in which the LTB or GTB also has a detail access bit set. Because cache activity may flush and refill cache lines implicity it is not generally useful to set the cache tag detail access bit alone but if this occurs the AccessDetailRequiredByTag exception catches such an attempt.

The next two rows show appropropriate activities on a GTB miss. On a GTB miss the detail access bit in the GTB is not present. If the LTB indicates detail access and the GTB misses the AccessDetailRequiredByLTB exception should be indicated. If software continues from the AccessDetailRequiredByLTB exception and has not filled in the GTB the GTBMiss exception happens next. Since the GTBMiss exection is not a continuation exception a re execution after the GTBMiss exception can cause a reoccurence of the AccessDetailRequiredByLTB exception. Alternatively if software continues from the AccessDetailRequiredByLTB exception and has filled in the GTB the AccessDetailRequiredByLTB exception is inhibited for that reference no matter what the status of the GTB and Tag detail bits but the re executed instruction is still subject to the AccessDetailRequiredByGTB and AccessDetailRequiredByTag exceptions.

The last four rows show appropriate activities for a cache miss. On a cache miss the detail access bit in the tag is not present. If the LTB or GTB indicates detail access and the cache misses the AccessDetailRequiredByLTB or AccessDetailRequiredByGTB exception should be indicated. If software continues from these exceptions and has not filled in the cache a cache miss happens next. If software continues from the AccessDetailRequiredByLTB or AccessDetailRequiredByGTB exception and has filled in the cache the previous exception is inhibited for that reference no matter what the status of the Tag detail bit but is still subject to the AccessDetailRequiredByTag exception. When the detail bit must be created from a cache miss the intial value filled in is zero. Software may set the bit thus turning off AccessDetailRequired exceptions per cache line. If the cache line is flushed and refilled the detail access bit in the cache tag is again reset to zero and another AccessDetailRequired exception occurs.

Settings of the niche limit parameter to values that require use of the da bit in the LOC tag for retaining the physical address usurp the capability to set the Tag detail access bit. Under such conditions the Tag detail access bit is effectively always zero 0 so it cannot inhibit AccessDetailRequiredByLTB inhibit AccessDetailRequiredByGTB or cause AccessDetailRequiredByTag.

The execution of a Zeus instruction has a reference to one quadlet of instruction which may be subject to the DetailAccess exceptions and a reference to data which may be unaligned or wide. These unaligned or wide references may cross GTB or cache boundaries and thus involve multiple separate reference that are combined together each of which may be subject to the DetailAccess exception. There is sufficient information in the DetailAccess exception handler to process unaligned or wide references.

The implementation is free to indicate DetailAccess exceptions for unaligned and wide data references either in combined form or with each sub reference separated. For example in an unaligned reference that crosses a GTB or cache boundary a DetailAccess exception may be indicated for a portion of the reference. The exception may report the virtual address and size of the complete reference and upon continuing may inhibit reoccurrence of the DetailAccess exception for any portion of the reference. Alternatively it may report the virtual address and size of only a reference portion and inhibit reoccurrence of the DetailAccess exception for only that portion of the reference subject to another DetailAccess exception occurring for the remaining portion of the reference.

The Micro Translation Buffer MTB is an implementation dependent structure which 25 reduces the access traffic to the GTB and the LOC tags. The MTB contains and caches information read from the GTB and LOC tags and is consulted on each access to the LOC.

To access the LOC a global address is supplied to the Micro Translation Buffer MTB which associatively looks up the global address into a table holding a subset of the LOC tags. In addition each table entry contains the physical address bits .. 7 bits and set identifier 2 bits required to access the LOC data.

In the first Zeus implementation there are two MTB blocks MTB 0 is used for threads 0 and 1 and MTB 1 is used for threads 2 and 3. Per clock cycle each MTB block can check for 5 4 simultaneous references to the LOC. Each MTB block has 16 entries.

Each MTB entry consists of a bit less than 128 bits of information including a 56 bit global address tag 8 bits of privilege level required for read write execute and gateway access a detail bit and 10 bits of cache state indicating for each triclet 32 bytes sub block the MESI state.

The output of the MTB combines physical address and protection information from the GTB and the referenced cache line.

With an MTB hit the resulting cache index 14..8 from the MTB bit from the LA and set identifier 2 bits from the MTB are applied to the LOC data bank selected from bits .. of the GVA. The access protection information pr and rwxg is supplied from the MTB.

With an MTB and BTB miss a victim entry is selected for replacement. The MTB and BTB are always clean so the victim entry is discarded without a writeback. The GTB described below is referenced to obtain a physical address and protection information. Depending on the access information in the GTB either the MTB or BTB is filled.

Note that the processing of the physical address paagainst the niche limit nl can be performed on the physical address from the GTB producing the LOC address ci. The LOC address after processing against the nl is placed into the MTB directly reducing the latency of an MTB hit.

Four tags are fetched from the LOC tags and compared against the PA to determine which of the four sets contain the data. If one of the four sets contains the correct physical address a victim MTB entry is selected for replacement the MTB is filled and the LOC access proceeds. If none of the four sets is a hit an LOC miss occurs.

The operation of the MTB is largely not visible to software hardware mechanisms are responsible for automatically initializing filling and flushing the MTB. Activity that modifies 10 the GTB or LOC tag state may require that one or more MTB entries are flushed.

A write to the GTBUpdate register that updates a matching entry a write to the GTBUpdateFill register or a direct write to the GTB all flush relevant entries from the MTB. MTB flushing is accomplished by searching MTB entries for values that match on the gi field with the GTB entry that has been modified. Each such matching MTB entry is flushed.

The MTB is kept synchronous with the LOC tags particularly with respect to MESI state. On an LOC miss or LOC snoop any changes in MESI state update or flush MTB entries which physically match the address. If the MTB may contain less than the full physical address it is sufficient to retain the LOC physical address ci v si .

Zeus has a per thread Block Translation Buffer BTB . The BTB retains GTB information for uncached address blocks. The BTB is used in parallel with the MTB exactly one of the BTB or MTB may translate a particular reference. When both the BTB and MTB miss the GTB is consulted and depending on the result the block is filled into either the MTB or BTB as appropriate. In the first Zeus implementation the BTB has 2 entries for each thread.

BTB entries cover any power of two granularity as they retain the size information from the GTB. BTB entries contain no MESI state as they only contain uncached blocks.

Each BTB entry consists of 128 bits of information containing the same information in the same format as a GTB entry.

Niche blocks are indicated by GTB information and correspond to blocks of data that are retained in the LOC and never miss. A special physical address range indicates niche blocks. For this address range the BTB enables use of the LOC as a niche memory generating the set select address bits from low order address bits. There is no checking of the LOC tags for consistent use of the LOC as a niche the nl field must be preset by software so that LOC cache replacement never claims the LOC niche space and only BTB miss and protection bits prevent software from using the cache portion of the LOC as niche.

Other address ranges include other on chip resources such as bus interface registers the control register and status register as well as off chip memory accessed through the bus interface. Each of these regions are accessible as uncached memory.

Later implementations of Zeus may optionally have a per thread Program Translation Buffer PTB . The PTB retains GTB and LOC cache tag information. The PTB enables generation of LOC instruction fetching in parallel with load store fetching. The PTB is updated when instruction fetching crosses a cache line boundary each 64 instructions in straight line code . The PTB functions similarly to a one entry MTB but can use the sequential nature of program code fetching to avoid checking the 56 bit match. The PTB is flushed at the same time as the MTB.

The initial implementation of Zeus contains cache which is both indexed and tagged by a physical address. Other prototype implementations have used a global vitual address to index and or tag an internal cache. This section will define the required characteristics of a global vitually indexed cache. TODO

Dedicated hardware mechanisms are provided to fetch data blocks in the levels zero and one caches provided that a matching entry can be found in the MTB or GTB or if the MMU is disabled . Dedicated hardware mechanisms are provided to store back data blocks in the level zero and one caches regardless of the state of the MTB and GTB. When no entry is to be found in the GTB an exception handler is invoked either to generate the required information from the virtual address or to place an entry in the GTB to provide for automatic handling of this and other similarly addressed data blocks.

The initial implementation of Zeus accesses the remainder of the memory system through the Socket 7 interface. Via this interface Zeus accesses a secondary cache DRAM memory external ROM memory and an I O system The size and presence of the secondary cache and the DRAM memory array and the contents of the external ROM memory and the I O system are variables in the processor environment.

Each thread has two address generation units capable of producing two aligned or one unaligned load or store operation per cycle. Alternatively these units may produce a single load or store address and a branch target address.

Each pair of threads has a MTB which looks up the four references into the LOC. The PTB provides for additional references that are program code fetches.

In parallel with the MTB these four references are combined with the four references from the other thread pair and partitioned into even and odd hexlet references. Up to four references are selected for each of the even and odd portions of the LZC. One reference for each of the eight banks of the LOC four are even hexlets four are odd hexlets are selected from the eight load store branch references and the PTB references.

Some references may be directed to both the LZC and LOC in which case the LZC hit causes the LOC data to be ignored. An LZC miss which hits in the MTB is filled from the LOC to the LZC. An LZC miss which misses in the MTB causes a GTB access and LOC tag access then an MTB fill and LOC access then an LZC fill.

The Socket 7 bus requires certain bus accesses to be checked against on chip caches. On a bus read the address is checked against the on chip caches with accesses aborted when requested data is in an internal cache in the M state and the E state the internal cache is changed to the S state. On a bus write data written must update data in on chip caches. To meet these requirements physical bus addresses must be checked against the LOC tags.

The S7 bus requires that responses to inquire cycles occur with fixed timing. At least with certain combinations of bus and processor clock rate inquire cycles will require top priority to meet the inquire response timing requirement.

Synchronization operations must take into account bus activity generally a synchronization operation can only proceed on cached data which is in Exclusive or Modified if cached data in Shared state ownership must be obtained. Data that is not cached must be accessed using locked bus cycles.

Load operations require partitioning into reads that do not cross a hexlet 128 bit boundary checking for store conflicts checking the LZC checking the LOC and reading from memory. Execute and Gateway accesses are always aligned and since they are smaller than a hexlet do not cross a hexlet boundary.

Note S7 processors perform unaligned operations LSB first MSB last up to 64 bits at a time. Unaligned 128 bit loads need 3 64 bit operations LSB octlet MSB. Transfers which are smaller than a hexlet but larger than an octlet are further divided in the S7 bus unit.

Store operations requires partitioning into stores less than 128 bits that do not cross hexlet boundaries checking for store conflicts checking the LZC checking the LOC and 30 storing into memory.

Memory operations require first translating via the LTB and GTB checking for access exceptions then accessing the cache.

In accordance with one embodiment of the invention rounding is specified within the instructions explicitly to avoid explicit state registers for a rounding mode. Similarly the instructions explicitly specify how standard exceptions invalid operation division by zero overflow underflow and inexact are to be handled U.S. Pat. No. 5 812 439 describes this Technique of incorporating floating point information into processor instructions. .

In this embodiment when no rounding is explicitly named by the instruction default round to nearest rounding is performed and all floating point exception signals cause the standard specified default result rather than a trap. When rounding is explicitly named by the instruction N nearest Z zero F floor C ceiling the specified rounding is performed and floating point exception signals other than inexact cause a floating point exception trap. When X exact or exception is specified all floating point exception signals cause a floating point exception trap including inexact. More details regarding rounding and exceptions are described in the Rounding and Exceptions section.

This technique assists the Zeus processor in executing floating point operations with greater parallelism. When default rounding and exception handling control is specified in floating point instructions Zeus may safely retire instructions following them as they are guaranteed not to cause data dependent exceptions. Similarly floating point instructions with N Z F or C control can be guaranteed not to cause data dependent exceptions once the operands have been examined to rule out invalid operations division by zero overflow or underflow exceptions. Only floating point instructions with X control or when exceptions cannot be ruled out with N Z F or C control need to avoid retiring following instructions until the final result is generated.

ANSI IEEE standard 754 1985 specifies information to be given to trap handlers for the five floating point exceptions. The Zeus architecture produces a precise exception The program counter points to the instruction that caused the exception and all register state is present from which all the required information can be produced in software as all source operand values and the specified operation are available.

ANSI IEEE standard 754 1985 specifies a set of five sticky exception bits for recording the occurrence of exceptions that are handled by default. The Zeus architecture produces a precise exception for instructions with N Z F or C control for invalid operation division by zero overflow or underflow exceptions and with X control for all floating point exceptions from which corresponding sticky exception bits can be set. Execution of the same instruction with default control will compute the default result with round to nearest rounding. Most compound operations not specified by the standard are not available with rounding and exception controls.

This section describes the instruction set in complete architectural detail. Operation codes are numerically defined by their position in the following operation code tables and are referred to symbolically in the detailed instruction definitions. Entries that span more than one location in the table define the operation code identifier as the smallest value of all the locations spanned. The value of the symbol can be calculated from the sum of the legend values to the left and above the identifier.

Instructions that have great similarity and identical formats are grouped together. Starting on a new page each category of instructions is named and introduced.

The Operation codes section lists each instruction by mnemonic that is defined on that page. A textual interpretation of each instruction is shown beside each mnemonic.

The Equivalences section lists additional instructions known to assemblers that are equivalent or special cases of base instructions again with a textual interpretation of each instruction beside each mnemonic. Below the list each equivalent instruction is defined either in terms of a base instruction or another equivalent instruction. The symbol between the instruction and the definition has a particular meaning. If it is an arrow or it connects two mathematically equivalent operations and the arrow direction indicates which form is preferred and produced in a reverse assembly. If the symbol is a the form on the left is assembled into the form on the right solely for encoding purposes and the form on the right is otherwise illegal in the assembler. The parameters in these definitions are formal the names are solely for pattern matching purposes even though they may be suggestive of a particular meaning.

The Redundancies section lists instructions and operand values that may also be performed by other instructions in the instruction set. The symbol connecting the two forms is a which indicates that the two forms are mathematically equivalent both are legal but the assembler does not transform one into the other.

The Selection section lists instructions and equivalences together in a tabular form that highlights the structure of the instruction mnemonics.

The Format section lists. 1 the assembler format 2 the C intrinsics format 3 the bit level instruction format and 4 a definition of bit level instruction format fields that are not a one for one match with named fields in the assembler format.

The Exceptions section lists exceptions that may be caused by the execution of the instructions in this category.

All instructions are 32 bits in size and use the high order 8 bits to specify a major operation code.

The major field is filled with a value specified by the following table Blank table entries cause the Reserved Instruction exception to occur. 

For the major operation field values A.M1NOR B.MINOR L.MINOR S.M1NOR G.8 G.16 G.32 G.64 G.128 XSHIFTI XSHIFT E.8 E.16 E.32 E.64 E.128 W.MINOR.L and W.MINOR.B the lowest order six bits in the instruction specify a minor operation code 

For the major operation field values E.MUL.X.I E.MUL.X.I.U E.MUL.X.I.M E.MULX.I.C E.MUL.ADD.X.I E.MUL.ADD.X.I.U E.MUL.ADD.X.I.M E.MUL.ADD.X.I.C E.CON.X.I.L E.CON.X.I.B E.CON.X.I.U.L E.CON.X.I.U.B E.CON.X.I.M.L E.CON.X.I.M.B E.CON.X.I.C.L E.CON.X.I.C.B E.EXTRACT.I E.EXTRACT.I.U W.MUL.MAT.X.I.U.L W.MUL.MAT.X.I.U.B W.MUL.MAT.X.I.M.L. W.MUL.MAT.X.I.M.B W.MUL.MAT.X.I.C.L and W.MUL.MAT.X.I.C.B another six bits in the instruction specify a minor operation code which indicates operand size rounding and shift amount 

The minor field is filled with a value from the following table Note that the shift amount field value shown below is the sh value which is encoded in an instruction dependent manner from the immediate field in the assembler format.

For the major operation field values G.AND.I G.NAND.I G.NOR.I G.OR.I G.XOR.I G.ADD.I G.ADD.I.O G.ADD.I.UO G.SET.AND.E.I G.SET.AND.NE.I G.SET.E.I G.SET.GE.I G.SET.L.I G.SET.NE.I G.SET.GE.I.U G.SET.L.I.U G.SUB.I G.SUB.I.O G.SUB.I.UO two bits in the instruction specify an operand size 

For the major operation field values E.8 E.16 E.32 E.64 E.128 with minor operation field value E.UNARY another six bits in the instruction specify a unary operation code 

For the major operation field values A.MINOR and G.MINOR with minor operation field values A.COM and G.COM another six bits in the instruction specify a comparison operation code 

The general forms of the instructions coded by major and minor operation codes are one of the following 

The general form of the instructions coded by major minor and unary operation codes is the following 

Register rd is either a source register or destination register or both. Registers rc and rb are always source registers. Register ra is always a destination register.

In accordance with one embodiment of the invention these operations take operands from three registers perform Boolean operations on corresponding bits in the operands and place the concatenated results in the third register.

In accordance with one embodiment of the invention the processor handles a variety Group Boolean operations. For example presents various Group Boolean instructions. illustrate an exemplary embodiment of a format and operation codes that can be used to perform the Boolean instructions shown in . As shown in in this exemplary embodiment three values are taken from the contents of registers rd rc and rb. The ih and it fields specify a function of three bits producing a single bit result. The specified function is evaluated for each bit position and the results are catenated and placed in register rd. Register rd is both a source and destination of this instruction.

The function is specified by eight bits which give the result for each possible value of the three source bits in each bit position 

A function can be modified by rearranging the bits of the immediate value. The table below shows how rearrangement of immediate value f7 o can reorder the operands d c b for the same function.

By using such a rearrangement an operation of the form b f d c b can be recoded into a legal form b f b d c . For example the function b f d c b d c b cannot be coded but the equivalent function d c b d can be determined by rearranging the code for d f d c b d c b which is 11001010 according to the rule for f d c b f c b d to the code 11011000.

Encoding Some special characteristics of this rearrangement is the basis of the manner in which the eight function specification bits are compressed to seven immediate bits in this instruction. As seen in the table above in the general case a rearrangement of operands from f d c b to f d b c interchanging rc and rb requires interchanging the values of fand fand the values of fand f.

Among the 256 possible functions which this instruction can perform one quarter of them 64 functions are unchanged by this rearrangement. These functions have the property that f fand f f. The values of rc and rb note that rc and rb are the register specifiers not the register contents can be freely interchanged and so are sorted into rising or falling order to indicate the value of f. A special case arises when rc rb so the sorting of rc and rb cannot convey information. However as only the values f7 f4 f3 and f0 can ever result in this case f6 f5 f2 and f1 need not be coded for this case so no special handling is required. These functions are encoded by the values of f7 f6 f4 f3 and f4 in the immediate field and f2 by whether rc rb thus using 32 immediate values for 64 functions.

Another quarter of the functions have f 1 and f 0. These functions are recoded by interchanging rc and rb fand f fand f. They then share the same encoding as the quarter of the functions where f6 0 and f5 1 and are encoded by the values of f7 f4 f3 f2 fi and fo in the immediate field thus using 64 immediate values for 128 functions.

The remaining quarter of the functions have f fand f.noteq.f. The half of these in which f 1 and f 0 are recoded by interchanging rc and rb fand f fand f. They then share the same encoding as the eighth of the functions where f 0 and f 1 and are encoded by the values of f f f f and fin the immediate field thus using 32 immediate values for 64 functions.

These operations take three values from registers perform a group of calculations on partitions of bits of the operands and place the catenated results in a fourth register.

In accordance with one embodiment of the invention the processor handles group multiplex operations. illustrate an exemplary embodiment of a format and operation codes that can be used to perform the various Group Multiplex instructions. As shown in in this exemplary embodiment the contents of registers rd rc and rb are fetched. Each bit of the result is equal to the corresponding bit of rc if the corresponding bit of rd is set otherwise it is the corresponding bit of rb. The result is placed into register ra. While the use of three operand registers and a different result register is described here and elsewhere in the present specification other arrangements such as the use of immediate values may also be implemented.

The table marked Redundancies in illustrates that for particular values of the register specifiers the Group Multiplex operation performs operations otherwise available within the Group Boolean instructions. More specifically when the result register ra is also present as a source register in the first second or third source operand position of the operation the operation is equivalent to the Group Boolean instruction with arguments of 0.times.11001010 0.times.11100010 or 0.times.11011000 respectively. When the first source operand is the same as the second or third source operand the Group Multiplex operation is equivalent to a bitwise OR or AND operation respectively.

In accordance with one embodiment of the invention these operations take operands from two registers perform operations on partitions of bits in the operands and place the concatenated results in a third register.

In accordance with one embodiment of the invention the processor handles a variety of fixed point or integer group operations. For example presents various examples of Group Add instructions accommodating different operand sizes such as a byte 8 bits doublet 16 bits quadlet 32 bits octlet 64 bits and hexlet 128 bits . illustrate an exemplary embodiment of a format and operation codes that can be used to perform the various Group Add instructions shown in . As shown in in this exemplary embodiment the contents of registers rc and rb are partitioned into groups of operands of the size specified and added and if specified checked for overflow or limited yielding a group of results each of which is the size specified. The group of results is catenated and placed in register rd. While the use of two operand registers and a different result register is described here and elsewhere in the present specification other arrangements such as the use of immediate values may also be implemented.

In the present embodiment for example if the operand size specified is a byte 8 bits and each register is 128 bit wide then the content of each register may be partitioned into 16 individual operands and 16 different individual add operations may take place as the result of a single Group Add instruction. Other instructions involving groups of operands may perform group operations in a similar fashion.

In accordance with one embodiment of the invention these operations take two values from registers perform operations on partitions of bits in the operands and place the concatenated results in a register. Two values are taken from the contents of registers rc and rb. The specified operation is performed and the result is placed in register rd.

Similarly presents various examples of Group Subtract instructions accommodating different operand sizes. illustrate an exemplary embodiment of a format and operation codes that can be used to perform the various Group Subtract instructions. As shown in in this exemplary embodiment the contents of registers rc and rb are partitioned into groups of operands of the size specified and subtracted and if specified checked for overflow or limited yielding a group of results each of which is the size specified. The group of results is catenated and placed in register rd.

In accordance with one embodiment of the invention these operations take two values from registers perform operations on partitions of bits in the operands and place the concatenated results in a register. Two values are taken from the contents of registers rc and rb. The specified operation is performed and the result is placed in register rd.

These operations take two values from registers perform operations on partitions of bits in the operands and place the concatenated results in a register. Two values are taken from the contents of registers rc and rb. The specified operation is performed and the result is placed in register rd.

In an embodiment of the invention conditional operations are provided in the sense that the set on condition operations can be used to construct bit masks that can select between alternate vector expressions using the bitwise Boolean operations.

Embodiments of the invention provide for other fixed point group operations also. presents various examples of Ensemble Divide and Ensemble Multiply instructions accommodating different operand sizes. illustrate an exemplary embodiment of a format and operation codes that can be used to perform the various Ensemble Divide and Ensemble Multiply instructions. As shown in in this exemplary embodiment the contents of registers rc and rb are partitioned into groups of operands of the size specified and divided or multiplied yielding a group of results. The group of results is catenated and placed in register rd.

These operations take operands from two registers perform operations on partitions of bits in the operands and place the concatenated results in a third register. Two values are taken from the contents of registers rc and rb. The specified operation is performed and the result is placed in register rd.

In accordance with one embodiment of the invention the processor also handles a variety floating point group operations accommodating different operand sizes. Here the different operand sizes may represent floating point operands of different precisions such as half precision 16 bits single precision 32 bits double precision 64 bits and quad precision 128 bits . illustrates exemplary functions that are defined for use within the detailed instruction definitions in other sections and figures. In the functions set forth in an internal format represents infinite precision floating point values as a four element structure consisting of 1 s sign bit 0 for positive 1 for negative 2 t type NORM ZERO SNAN QNAN INFINITY 3 e exponent and 4 f fraction . The mathematical interpretation of a normal value places the binary point at the units of the fraction adjusted by the exponent 1 circumflex over s 2circumflex over 0e f. The function F converts a packed IEEE floating point value into internal format. The function PackF converts an internal format back into IEEE floating point format with rounding and exception control.

These operations take two values from registers perform a group of floating point arithmetic operations on partitions of bits in the operands and place the concatenated results in a register. For Ensemble Floating point operations the contents of registers ra and rb are combined using the specified floating point operation. The result is placed in register rc. For Ensemble Reversed Floating point operations the contents of registers rc and rb are combined using the specified floating point operation. The result is placed in register rd.

In the present embodiment the operation is rounded using the specified rounding option or using round to nearest if not specified. If a rounding option is specified the operation raises a floating point exception if a floating point invalid operation divide by zero overflow or underflow occurs or when specified if the result is inexact. If a rounding option is not specified floating point exceptions are not raised and are handled according to the default rules of IEEE 754.

Ensemble Multiply Add Floating Point presents various examples of Ensemble Floating Point Multiply Add instructions. illustrate an exemplary embodiment of formats and operation codes that can be used to perform the various Ensemble Floating Point Multiply Add instructions. In these examples Ensemble Floating Point Multiply Add instructions have been labeled as EnsembleInplaceFloatingPoint. As shown in in this exemplary embodiment operations take operands from three registers perform operations on partitions of bits in the operands and place the concatenated results in the third register. The contents of registers rd rc and rb are fetched. The specified operation is performed on these operands. The result is placed into register rd. Specifically the contents of registers rd rc and rb are partitioned into groups of operands of the size specified and for each partitioned element the contents of registers rc and rb are multiplied and added to the contents of register rd yielding a group of results. The group of results is catenated and placed in register rd. Register rd is both a source and destination of this instruction.

In the present embodiment the operation is rounded using the specified rounding option or using round to nearest if not specified. If a rounding option is specified the operation raises a floating point exception if a floating point invalid operation divide by zero overflow or underflow occurs or when specified if the result is inexact. If a rounding option is not specified floating point exceptions are not raised and are handled according to the default rules of IEEE 754.

In accordance with one embodiment of the invention these operations take three values from registers perform a group of floating point arithmetic operations on partitions of bits in the operands and place the concatenated results in a register.

In accordance with one embodiment of the invention these operations take two values 30 from registers perform a group of floating point arithmetic operations on partitions of bits in the operands and place the concatenated results in a register. The contents of registers ra and rb are combined using the specified floating point operation. The result is placed in register rc. The operation is rounded using the specified rounding option or using round to nearest if not specified. If a rounding option is specified the operation raises a floating point exception if a floating point invalid operation divide by zero overflow or underflow occurs or when specified if the result is inexact. If a rounding option is not specified floating point exceptions are not raised and are handled according to the default rules of IEEE 754.

In accordance with one embodiment of the invention the processor handles different Galois filed operations. For example presents various examples of Ensemble Multiply Gaois Field instructions accommodating different operand sizes. illustrate an exemplary embodiment of a format and operation codes that can be used to perform the Ensemble Multiply Gaois Field instructions shown in . As shown in in this exemplary embodiment the contents of registers rd rc and rb are fetched. The specified operation is performed on these operands. The result is placed into register ra.

The contents of registers rd and rc are partitioned into groups of operands of the size specified and multiplied in the manner of polynomials. The group of values is reduced modulo the polynomial specified by the contents of register rb yielding a group of results each of which is the size specified. The group of results is catenated and placed in register ra.

An ensemble multiply Galois field bytes instruction E.MULG.8 multiplies operand d15 d14 d13 d12 d11 d10 d9 d8 d7 d6 d5 d4 d3 d2 d1 d0 by operand c15 c14 c13 c12 c11 c10 c9 c8 c7 c6 c5 c4 c3 c2 c1 c0 modulo polynomial q yielding the results d15c15 mod q d14c14 mod q . . . d0c0 mod q as illustrated in .

In accordance with one embodiment of the invention these operations take operands from two registers perform operations on partitions of bits in the operands and place the concatenated results in a third register. Two values are taken from the contents of registers rc and rb. The specified operation is performed and the result is placed in register rd.

In one embodiment of the invention crossbar switch units such as units and perform data handling operations as previously discussed. As shown in such data handling operations may include various examples of Crossbar Compress Crossbar Expand Crossbar Rotate and Crossbar Shift operations. illustrate an exemplary embodiment of a format and operation codes that can be used to perform the various Crossbar Compress Crossbar Expand Crossbar Rotate and Crossbar Shift instructions. As shown in in this exemplary embodiment the contents of registers rc and rb are obtained and the contents of register rc is partitioned into groups of operands of the size specified and the specified operation is performed using a shift amount obtained from the contents of register rb masked to values from zero to one less than the size specified yielding a group of results. The group of results is catenated and placed in register rd.

Various Group Compress operations may convert groups of operands from higher precision data to lower precision data. An arbitrary half sized sub field of each bit field can be selected to appear in the result. For example shows an X.COMPRESS.16 rd rc 4 operation which performs a selection of bits .. of each quadlet in a hexlet. Various Group Shift operations may allow shifting of groups of operands by a specified number of bits in a specified direction such as shift right or shift left. As can be seen in certain Group Shift Left instructions may also involve clearing to zero empty low order bits associated with the shift for each operand. Certain Group Shift Right instructions may involve clearing to zero empty high order bits associated with the shift for each operand. Further certain Group Shift Right instructions may involve filling empty high order bits associated with the shift with copies of the sign bit for each operand.

In accordance with one embodiment of the invention these operations take operands from three registers perform operations on partitions of bits in the operands and place the concatenated results in the third register. The contents of registers rd rc and rb are fetched. The specified operation is performed on these operands. The result is placed into register rd.

In one embodiment of the invention as shown in such data handling operations may also include various examples of Shift Merge operations. illustrate an exemplary embodiment of a format and operation codes that can be used to perform the various Shift Merge instructions. As shown in in this exemplary embodiment the contents of registers rd and rc are obtained and the contents of register rd and rc are partitioned into groups of operands of the size specified and the specified operation is performed using a shift amount obtained from the contents of register rb masked to values from zero to one less than the size specified yielding a group of results. The group of results is catenated and placed in register rd. Register rd is both a source and destination of this instruction.

Shift Merge operations may allow shifting of groups of operands by a specified number of bits in a specified direction such as shift right or shift left. As can be seen in certain Shift Merge operations may involve filling empty bits associated with the shift with copies of corresponding bits from the contents of register rd for each operand.

In accordance with one embodiment of the invention these operations take operands from a register and a short immediate value perform operations on partitions of bits in the operands and place the concatenated results in a register. A 128 bit value is taken from the contents of register rc. The second operand is taken from simm. The specified operation is performed and the result is placed in register rd.

In one embodiment of the invention crossbar switch units such as units and perform data handling operations as previously discussed. As shown in such data handling operations may include various examples of Crossbar Compress Immediate Crossbar Expand Immediate Crossbar Rotate Immediate and Crossbar Shift Immediate operations. FIGS. I and J illustrate an exemplary embodiment of a format and operation codes that can be used to perform the various Crossbar Compress Immediate Crossbar Expand Immediate Crossbar Rotate Immediate and Crossbar Shift Immediate instructions. As shown in in this exemplary embodiment the contents of register rc is obtained and is partitioned into groups of operands of the size specified and the specified operation is performed using a shift amount obtained from the instruction masked to values from zero to one less than the size specified yielding a group of results. The group of results is catenated and placed in register rd.

Various Group Compress Immediate operations may convert groups of operands from higher precision data to lower precision data. An arbitrary half sized sub field of each bit field can be selected to appear in the result. For example shows an X.COMPRESS. 16 rd rc 4 operation which performs a selection of bits . . . of each quadlet in a hexlet. Various Group Shift Immediate operations may allow shifting of groups of operands by a specified number of bits in a specified direction such as shift right or shift left. As can be seen in certain Group Shift Left Immediate instructions may also involve clearing to zero empty low order bits associated with the shift for each operand. Certain Group Shift Right Immediate instructions may involve clearing to zero empty high order bits associated with the shift for each operand. Further certain Group Shift Right Immediate instructions may involve filling empty high order bits associated with the shift with copies of the sign bit for each operand.

In accordance with one embodiment of the invention these operations take operands from two registers and a short immediate value perform operations on partitions of bits in the operands and place the concatenated results in the second register. Two 128 bit values are taken from the contents of registers rd and rc. A third operand is taken from simm. The specified operation is performed and the result is placed in register rd. This instruction is undefined and causes a reserved instruction exception if the simm field is greater or equal to the size specified.

In one embodiment of the invention as shown in such data handling operations may also include various examples of Shift Merge Immediate operations. and M illustrate an exemplary embodiment of a format and operation codes that can be used to perform the various Shift Merge Immediate instructions. As shown in in this exemplary embodiment the contents of registers rd and rc are obtained and are partitioned into groups of operands of the size specified and the specified operation is performed using a shift amount obtained from the instruction masked to values from zero to one less than the size specified yielding a group of results. The group of results is catenated and placed in register rd. Register rd is both a source and destination of this instruction.

Shift Merge operations may allow shifting of groups of operands by a specified number of bits in a specified direction such as shift right or shift left. As can be seen in certain Shift Merge operations may involve filling empty bits associated with the shift with copies of corresponding bits from the contents of register rd for each operand.

In one embodiment of the invention data handling operations may also include a Crossbar Extract instruction. These operations take operands from three registers perform operations on partitions of bits in the operands and place the concatenated results in a fourth register. illustrate an exemplary embodiment of a format and operation codes that can be used to perform the Crossbar Extract instruction. These operations take operands from three registers perform operations on partitions of bits in the operands and place the concatenated results in a fourth register. As shown in in this exemplary embodiment the contents of registers rd rc and rb are fetched. The specified operation is performed on these operands. The result is placed into register ra.

The Crossbar Extract instruction allows bits to be extracted from different operands in various ways. Specifically bits . . . of the contents of register rb specifies several parameters which control the manner in which data is extracted and for certain operations the manner in which the operation is performed. The position of the control fields allows for the source position 25 to be added to a fixed control value for dynamic computation and allows for the lower 16 bits of the control field to be set for some of the simpler extract cases by a single GCOPYI.128 instruction. The control fields are further arranged so that if only the low order 8 bits are non zero a 128 bit extraction with truncation and no rounding is performed 

The 9 bit gssp field encodes both the group size gsize and source position spos according to the formula gssp 512 4 gsize spos. The group size gsize is a power of two in the range 1 . . . 128. The source position spos is in the range 0 . . . 2 gsize 1.

For the E.SCAL.ADD.X instruction bits .. of the contents of register rc specifies the multipliers for the multiplicands in registers ra and rb. Specifically bits 2 gsize 1..64 gsize is the multiplier for the contents of register ra and bits gsize 1..64 is the multiplier for the contents of register rb.

As shown in for the X.EXTRACT instruction when m 0 the parameters are interpreted to select a fields from the catenated contents of registers rd and rc extracting values which are catenated and placed in register ra. As shown in for a crossbar merge extract X.EXTR.ACT when m 1 the parameters are interpreted to merge fields from the contents of register rd with the contents of register rc. The results are catenated and placed in register ra.

In one embodiment of the invention data handling operations may also include an Ensemble Extract instruction. These operations take operands from three registers perform operations on partitions of bits in the operands and place the concatenated results in a fourth register. F and G illustrate an exemplary embodiment of a format and operation codes that can be used to perform the Ensemble Extract instruction. As shown in in this exemplary embodiment the contents of registers rd rc and rb are fetched. The specified operation is performed on these operands. The result is placed into register ra.

The Crossbar Extract instruction allows bits to be extracted from different operands in various ways. Specifically bits . . . of the contents of register rb specifies several parameters which control the manner in which data is extracted and for certain operations the manner in which the operation is performed. The position of the control fields allows for the source position to be added to a fixed control value for dynamic computation and allows for the lower 16 bits of the control field to be set for some of the simpler extract cases by a single GCOPYI.128 instruction. The control fields are further arranged so that if only the low order 8 bits are non zero a 128 bit extraction with truncation and no rounding is performed 

The 9 bit gssp field encodes both the group size gsize and source position spos according to the formula gssp 512 4 gsize spos. The group size gsize is a power of two in the range 1 . . . 128. The source position spos is in the range 0 . . . 2 gsize 1.

As shown in an ensemble multiply extract doublets instruction E.MULX multiplies vector ra h g f e d c b a with vector rb p o n m l k j i yielding the result hp go fn em dl ck bj ai rounded and limited as specified by rc31.0.

As shown in an ensemble multiply extract doublets complex instruction E.MUL.X with n set multiplies operand h g fe d c b a by operand p o n m l k j i yielding the result gp ho go hp en fm em fn cl dk ck dl aj bi ai bj rounded and limited as specified. Note that this instruction prefers an organization of complex numbers in which the real part is located to the right lower precision of the imaginary part.

As shown in an ensemble scale add extract doublets instruction E.SCAL.ADD.X multiplies vector ra h gfedcb a with re r and adds the product to the product of vector rb p o n m l k j i with re q yielding the result hr pq gr oq fr nq er mq dr lq cr kq br jq ar iq rounded and limited as specified by rc.

As shown in an ensemble scale add extract doublets complex instruction E.SCLADD.X with n set multiplies vector ra h gfedcb a with rc12.76 t s and adds the product to the product of vector rb p o n m l k j i with re r q yielding the result hs gt pq or gs ht oq pr fs et nq mr es ft mq nr ds ct lq kr cs dt kq lr bs at jq ir as bt iq jr rounded and limited as specified by rc.

As shown in for the E.EXTRACT instruction when m 0 the parameters are interpreted to select a fields from the catenated contents of registers rd and rc extracting values 10 which are catenated and placed in register ra. As shown in for an ensemble merge extract E.EXTRACT when m 1 the parameters are interpreted to merge fields from the contents of register rd with the contents of register rc. The results are catenated and placed in register ra. As can be seen from the operand portion to the left of the selected field is treated as signed or unsigned as controlled by the s field and truncated or saturated as controlled by the t field while the operand portion to the right of the selected field is rounded as controlled by the rnd field.

As shown in in one embodiment of the invention data handling operations include various Deposit and Withdraw instructions. illustrate an exemplary embodiment of a format and operation codes that can be used to perform the various Deposit and Withdraw instructions. As shown in in this exemplary embodiment these operations take operands from a register and two immediate values perform operations on partitions of bits in the operands and place the concatenated results in the second register. Specifically the contents of register rc are fetched and 7 bit immediate values are taken from the 2 bit ih and the 6 bit gsfp and gsfs fields. The specified operation is performed on these operands. The result is placed into register rd.

As shown in the crossbar deposit instructions deposit a bit field from the lower bits of each group partition of the source to a specified bit position in the result. The value is either sign extended or zero extended as specified. As shown in the crossbar withdraw instructions withdraw a bit field from a specified bit position in the each group partition of the source and place it in the lower bits in the result. The value is either sign extended or zero extended as specified.

As shown in in one embodiment of the invention data handling operations include various Deposit Merge instructions. illustrate an exemplary embodiment of a format and operation codes that can be used to perform the various Deposit Merge instructions. As shown in in this exemplary embodiment these operations take operands from two registers and two immediate values perform operations on partitions of bits in the operands and place the concatenated results in the second register. Specifically the contents of registers rc and rd are fetched and 7 bit immediate values are taken from the 2 bit ih and the 6 bit gsfp and gsfs fields. The specified operation is performed on these operands. The result is placed into register rd.

As shown in the crossbar deposit merge instructions deposit a bit field from the lower bits of each group partition of the source to a specified bit position in the result. The value is merged with the contents of register rd at bit positions above and below the deposited bit field. No sign or zero extension is performed by this instruction.

In accordance with one embodiment of the invention these operations take operands from two registers perform operations on partitions of bits in the operands and place the concatenated results in a register.

As shown in in one embodiment of the invention data handling operations may also include various Shuffle instructions which allow the contents of registers to be partitioned into groups of operands and interleaved in a variety of ways. illustrate an exemplary embodiment of a format and operation codes that can be used to perform the various Shuffle instructions. As shown in in this exemplary embodiment one of two operations is performed depending on whether the rc and rb fields are equal. Also and the Description below illustrate the format of and relationship of the rd re rb op v w h and size fields.

In the present embodiment if the re and rb fields are equal a 128 bit operand is taken from the contents of register rc. Items of size v are divided into w piles and shuffled together within groups of size bits according to the value of op. The result is placed in register rd.

Further if the rc and rb fields are not equal the contents of registers rc and rb are catenated into a 256 bit operand. Items of size v are divided into w piles and shuffled together according to the value of op. Depending on the value of h a sub field of op the low 128 bits h 0 or the high 128 bits h 1 of the 256 bit shuffled contents are selected as the result. The result is placed in register rd.

This instruction is undefined and causes a reserved instruction exception if rc and rb are not equal and the op field is greater or equal to 56 or if rc and rb are equal and op4..0 is greater or equal to 28.

As shown in an example of a crossbar 4 way shuffle of bytes within hexlet instruction X.SHUFFLE.128 rd rcb 8 4 divides the 128 bit operand into 16 bytes and partitions the bytes 4 ways indicated by varying shade in the diagram below . The 4 partitions are perfectly shuffled producing a 128 bit result. As shown in an example of a crossbar 4 way shuffle of bytes within triclet instruction X.SHUFFLE.256 rd rc rb 8 4 0 catenates the contents of rc and rb then divides the 256 bit content into 32 bytes and partitions the bytes 4 ways indicated by varying shade in the diagram below . The low order halves of the 4 partitions are perfectly shuffled producing a 128 bit result.

Changing the last immediate value h to 1 X.SHUFFLE.256 rd rc rb 8 4 1 modifies the operation to perform the same function on the high order halves of the 4 partitions. When rc and rb are equal the table below shows the value of the op field and associated values for size v and w.

When rc and rb are not equal the table below shows the value of the op0 field and associated values for size v and w Opis the value of h which controls whether the low order or high order half of each partition is shuffled into the result.

In accordance with one embodiment of the invention these operations perform calculations with a general register value and immediate values placing the result in a general register.

In one embodiment of the invention data handling operations may also include various Crossbar Swizzle instruction. illustrate an exemplary embodiment of a format and operation codes that can be used to perform Crossbar Swizzle instructions. As shown in in this exemplary embodiment the contents of register rc are fetched and 7 bit immediate values icopy and iswap are constructed from the 2 bit ih field and from the 6 10 bit icopya and iswapa fields. The specified operation is performed on these operands. The result is placed into register rd.

The swizzle operation can reverse the order of the bit fields in a hexlet. For example a X. SWIZZLE rd rc 127 112 operation reverses the doublets within a hexlet as shown in . In some cases it is desirable to use a group instruction in which one or more operands is a single value not an array. The swizzle operation can also copy operands to multiple locations within a hexlet. For example a X.SWIZZLE 15 0 operation copies the low order 16 bits to each double within a hexlet.

In accordance with one embodiment of the invention these operations take three values from registers perform a group of calculations on partitions of bits of the operands and place the catenated results in a fourth register. The contents of registers rd rc and rb are fetched. The specified operation is performed on these operands. The result is placed into register ra.

In one embodiment of the invention data handling operations may also include various Crossbar Select instruction. illustrate an exemplary embodiment of a format and operation codes that can be used to perform Crossbar Select instructions. As shown in in this exemplary embodiment the contents of registers rd rc and rb are fetched and the contents of registers rd and rc are catenated producing catenated data dc. The contents of register rb is partitioned into elements and the value expressed in each partition is employed to select one partitioned element of the catenated data dc. The selected elements are catenated together and result is placed into register ra.

As shown in in one embodiment of the invention memory access operations may also include various Load and Load Immediate instructions. These figures and show that the various Load and Load Immediate instructions specify a type of operand either signed or unsigned represented by omitting or including a U respectively. The instructions further specify a size of memory operand byte double quadlet octlet or hexlet representing 8 16 32 64 and 128 bits respectively. The instructions further specify aligned memory operands or not represented by including a A or with the A omitted respectively. The instructions further specify a byte ordering of the memory operand either big endian or little endian represented by B and L respectively.

Each instruction specifies the above items with the following exceptions L.8 L.U8 L.I.8 L.I.U8 need not distinguish between little endian and big endian ordering nor between aligned and unaligned as only a single byte is loaded. L. 128.B L.128.AB L.128.L L.128AL L.I.128.8 L.I.128.AB L.I.128.L and L.I.128AL need not distinguish between signed and unsigned as the hexlet fills the destination register.

Regarding footnote in L.8 need not distinguish between little endian and big endian ordering nor between aligned and unaligned as only a single byte is loaded.

Regarding footnote in L.128.B need not distinguish between signed and unsigned as the hexlet fills the destination register.

Regarding footnote in L.128.AB need not distinguish between signed and unsigned as the hexlet fills the destination register.

Regarding footnote in L.128.L need not distinguish between signed and unsigned as the hexlet fills the destination register.

Regarding footnote in L.128.AL need not distinguish between signed and unsigned as the hexlet fills the destination register.

Regarding footnote in L.U8 need not distinguish between little endian and big endian ordering nor between aligned and unaligned as only a single byte is loaded.

Regarding footnote in LI. 8 need not distinguish between little endian and big endian ordering nor between aligned and unaligned as only a single byte is loaded.

Regarding footnote in LI.128.AB need not distinguish between signed and unsigned as the hexlet fills the destination register.

Regarding footnote in LI.128.B need not distinguish between signed and unsigned as the hexlet fills the destination register.

Regarding footnote in .128.AL need not distinguish between signed and unsigned as the hexlet fills the destination register.

Regarding footnote in LI.128.L need not distinguish between signed and unsigned as the hexlet fills the destination register.

Regarding footnote in LI.U8 need not distinguish between little endian and big endian ordering nor between aligned and unaligned as only a single byte is loaded.

In an exemplary embodiment for both Load and Load Immediate instructions the contents of memory using the specified byte order are read treated as the size specified zero extended or sign extended as specified and placed into register rd. If alignment is specified the computed virtual address must be aligned that is it must be an exact multiple of the size expressed in bytes. If the address is not aligned an access disallowed by virtual address exception occurs.

As shown in in one embodiment of the invention memory access operations may also include various Store and Store Immediate instructions. These figures and show that the various Store and Store Immediate instructions specify a size of memory operand byte double quadlet octlet or hexlet representing 8 16 32 64 and 128 bits respectively. The instructions further specify aligned memory operands or not represented by including a A or with the A omitted respectively. The instructions further specify a byte ordering of the memory operand either big endian or little endian represented by B and L respectively.

Each instruction specifies the above items with the following exceptions L.8 and L.1.8 need not distinguish between little endian and big endian ordering nor between aligned and unaligned as only a single byte is stored.

Regarding footnote I in S.8 need not specify byte ordering nor need it specify alignment checking as it stores a single byte.

Regarding footnote I in SI.8 need not specify byte ordering nor need it specify alignment checking as it stores a single byte.

In an exemplary embodiment for both Store and Store Immediate instructions the contents of register rd treated as the size specified is stored in memory using the specified byte order. If alignment is specified the computed virtual address must be aligned that is it must be an exact multiple of the size expressed in bytes. If the address is not aligned an access disallowed by virtual address exception occurs.

As shown in in one embodiment of the invention memory access operations may also include various Store Multiplex and Store Multiplex Immediate instructions. These figures and show that the various Store Multiplex and Store Multiplex Immediate instructions specify a size of memory operand octlet representing 64 bits. The instructions further specify aligned memory operands represented by including a A. The instructions further specify a byte ordering of the memory operand either big endian or little endian represented by B and L respectively.

In an exemplary embodiment for both Store Multiplex and Store Multiplex Immediate instructions data contents and mask contents of the contents of register rd are identified. The data contents are stored in memory using the specified byte order for values in which the corresponding mask contents are set. In an exemplary embodiment it can be understood that masked writing of data can be accomplished by indivisibly reading the original contents of the addressed memory operand modifying the value and writing the modified value back to the addressed memory operand. In an exemplary embodiment the modification of the value is accomplished using an operation previously identified as a Multiplex operation in the section titled Group Multiplex above and in .

In an exemplary embodiment for both Store Multiplex and Store Multiplex Immediate instructions the computed virtual address must be aligned that is it must be an exact multiple of the size expressed in bytes. If the address is not aligned an access disallowed by virtual address exception occurs.

In an exemplary embodiment studies of the dynamic distribution of instructions on various benchmark suites indicate that the most frequently issued instruction classes are load instructions and execute instructions. In an exemplary embodiment it is advantageous to consider execution pipelines in which the ability to target the machine resources toward issuing load and execute instructions is increased.

In an exemplary embodiment one of the means to increase the ability to issue execute class instructions is to provide the means to issue two execute instructions in a single issue string. The execution unit actually requires several distinct resources so by partitioning these resources the issue capability can be increased without increasing the number of functional units other than the increased register file read and write ports. In an exemplary embodiment the partitioning favored places all instructions that involve shifting and shuffling in one execution unit and all instructions that involve multiplication including fixed point and floating point multiply and add in another unit. In an exemplary embodiment resources used for implementing add subtract and bitwise logical operations may be duplicated being modest in size compared to the shift and multiply units. In another exemplary embodiment resources used are shared between the two units as the operations have low enough latency that two operations might be pipelined within a single issue cycle. These instructions must generally be independent except in another exemplary embodiment that two simple add subtract or bitwise logical instructions may be performed dependently if the resources for executing simple instructions are shared between the execution units.

In an exemplary embodiment one of the means to increase the ability to issue load class instructions is to provide the means to issue two load instructions in a single issue string. This would generally increase the resources required of the data fetch unit and the data cache but a compensating solution is to steal the resources for the store instruction to execute the second load instruction. Thus in an exemplary embodiment a single issue string can then contain either two load instructions or one load instruction and one store instruction which uses the same register read ports and address computation resources as the basic 5 instruction string in another exemplary embodiment.

In an exemplary embodiment this capability also may be employed to provide support for unaligned load and store instructions where a single issue string may contain as an alternative a single unaligned load or store instruction which uses the resources of the two load class units in concert to accomplish the unaligned memory operation.

The reserved instruction exception is raised. Software may depend upon this major operation code raising the reserved instruction exception in all implementations. The choice of operation code intentionally ensures that a branch to a zeroed memory area will raise an exception.

These operations perform calculations with two general register values placing the result in a general register.

The contents of registers rc and rb are fetched and the specified operation is performed on these operands. The result is placed into register rd.

These operations perform calculations with two general register values and generate a fixed point arithmetic exception if the condition specified is met.

The contents of registers rd and rc are fetched and the specified condition is calculated on these operands. If the specified condition is true a fixed point arithmetic exception is generated. This instruction generates no general register results.

An immediate value is sign extended from the 18 bit imm field. The result is placed into register rd.

These operations perform calculations with one general register value and one immediate value placing the result in a general register.

The contents of register rc is fetched and a 64 bit immediate value is sign extended from the 12 bit imm field. The specified operation is performed on these operands. The result is placed into register rd.

These operations perform calculations with one general register value and one immediate value placing the result in a general register.

The contents of register rc is fetched and a 64 bit immediate value is sign extended from the 12 bit imm field. The specified operation is performed on these operands. The result is placed into register rd.

These operations perform calculations with two general register values placing the result in a general register.

The contents of registers rc and rb are fetched and the specified operation is performed on these operands. The result is placed into register rd.

These operations perform calculations with two general register values placing the result in a general register.

The contents of register rb are shifted left by the immediate amount and added to the contents of register rc. The result is placed into register rd.

These operations perform calculations with two general register values placing the result in a general register.

The contents of register rc is subtracted from the contents of register rb shifted left by the immediate amount. The result is placed into register rd.

These operations perform calculations with one general register value and one immediate value placing the result in a general register.

The contents of register rc is fetched and a 6 bit immediate value is taken from the 6 bit simm field. The specified operation is performed on these operands. The result is placed into register rd.

These operations perform calculations with three general register values placing the result in a fourth general register.

The contents of registers rd rc and rb are fetched. The specified operation is performed on these operands. The result is placed into register ra.

Access disallowed exception occurs if the contents of register rd is not aligned on a quadlet boundary.

This operation branches to a location specified by the previous contents of register 0 reduces the current privilege level loads a value from memory and restores register 0 to the value saved on a previous exception.

Processor context including program counter and privilege level is restored from register 0 where it was saved at the last exception. Exception state if set is cleared re enabling normal exception handling. The contents of register 0 saved at the last exception is restored from memory. The privilege level is only lowered so that this instruction need not be privileged.

If the previous exception was an AccessDetail exception Continuation State set at the time of the exception affects the operation of the next instruction after this Branch Back causing the previous AccessDetail exception to be inhibited. If software is performing this instruction to abort a sequence ending in an AccessDetail exception it should abort by branching to an instruction that is not affected by Continuation State.

This operation stops the current thread until all pending stores are completed then branches to a location specified by a register.

The instruction fetch unit is directed to cease execution until all pending stores are completed. Following the barrier any previously pre fetched instructions are discarded and execution branches to the address specified by the contents of register rd.

Access disallowed exception occurs if the contents of register rd is not aligned on a quadlet boundary.

Self modifying dynamically generated or loaded code may require use of this instruction between storing the code into memory and executing the code.

These operations compare two operands and depending on the result of that comparison conditionally branches to a nearby code location.

The contents of registers rd and rc are compared as specified by the op field. If the result of the comparison is true execution branches to the address specified by the offset field. Otherwise execution continues at the next sequential instruction.

These operations compare two floating point operands and depending on the result of that comparison conditionally branches to a nearby code location.

The contents of registers rc and rd are compared as specified by the op field. If the result of the comparison is true execution branches to the address specified by the offset field. Otherwise execution continues at the next sequential instruction.

These operations compare two group floating point operands and depending on the result of that comparison conditionally branches to a nearby code location.

The contents of registers rc and rd are compared as specified by the op field. If the result of the comparison is true execution branches to the address specified by the offset field. Otherwise execution continues at the next sequential instruction.

Each operand is assumed to represent a vertex of the form w z y x packed into a single register. The comparisons check for visibility of a line connecting the vertices against a standard viewing volume defined by the planes x w x w y w y w z 0 z 1. A line is visible V if the vertices are both within the volume. A line is not visible NV is either vertex is outside the volume in such a case the line may be partially visible. A line is invisible I if the vertices are both outside any face of the volume. A line is not invisible NI if the vertices are not both outside any face of the volume.

An exemplary embodiment of the Branch Conditional Visibility Floating Point instructions is shown in .

Execution branches to the address specified by the contents of register rd. The current privilege level is reduced to the level specified by the low order two bits of the contents of register rd.

This operation provides a secure means to call a procedure including those at a higher privilege level.

The contents of register rb is a branch address in the high order 62 bits and a new privilege level in the low order 2 bits. A branch and link occurs to the branch address and the privilege level is raised to the new privilege level. The high order 62 bits of the successor to the current program counter is catenated with the 2 bit current execution privilege and placed in register 0.

If the new privilege level is greater than the current privilege level an octlet of memory data is fetched from the address specified by register 1 using the little endian byte order and a gateway access type. A GatewayDisallowed exception occurs if the original contents of register 0 do not equal the memory data.

If the new privilege level is the same as the current privilege level no checking of register 1 is performed.

An AccessDisallowed exception occurs if the new privilege level is greater than the privilege level required to write the memory data or if the old privilege level is lower than the privilege required to access the memory data as a gateway or if the access is not aligned on an 8 byte boundary.

In the example below a gateway from level 0 to level 2 is illustrated. The gateway pointer located by the contents of register rc 1 is fetched from memory and compared against the contents of register rb 0 . The instruction may only complete if these values are equal. Concurrently the contents of register rb 0 is placed in the program counter and privilege level and the address of the next sequential address and privilege level is placed into register rd 0 . Code at the target of the gateway locates the data pointer at an offset from the gateway pointer register 1 and fetches it into register 1 making a data region available. Referring to stack pointer may be saved and fetched using the data region another region located from the data region or a data region located as an offset from the original gateway pointer.

For additional information on the branch gateway instruction see the System and Privileged Library Calls section.

This instruction gives the target procedure the assurances that register 0 contains a valid return address and privilege level that register I points to the gateway location and that the gateway location is octlet aligned. Register I can then be used to securely reach values in memory. If no sharing of literal pools is desired register 1 may be used as a literal pool pointer directly. If sharing of literal pools is desired register 1 may be used with an appropriate offset to load a new literal pool pointer for example with a one cache line offset from the register 1. Note that because the virtual memory system operates with cache line granularity that several gateway locations must be created together.

Software must ensure that an attempt to use any octlet within the region designated by virtual memory as gateway either functions properly or causes a legitimate exception. For example if the adjacent octlets contain pointers to literal pool locations software should ensure that these literal pools are not executable or that by virtue of being aligned addresses cannot raise the execution privilege level. If register I is used directly as a literal pool location software must ensure that the literal pool locations that are accessible as a gateway do not lead to a security violation.

Register 0 contains a valid return address and privilege level the value is suitable for use directly in the Branch down B.DOWN instruction to return to the gateway callee.

This instruction directs the instruction fetch unit of the processor that a branch is likely to occur count times at simm instructions following the current successor instruction to the address specified by the contents of register rd.

After branching count times the instruction fetch unit should presume that the branch at simm instructions following the current successor instruction is not likely to occur. If count is zero this hint directs the instruction fetch unit that the branch is likely to occur more than 63 times.

Access disallowed exception occurs if the contents of register rd is not aligned on a quadlet boundary.

This instruction directs the instruction fetch unit of the processor that a branch is likely to occur count times at simm instructions following the current successor instruction to the address specified by the offset field.

After branching count times the instruction fetch unit should presume that the branch at simm instructions following the current successor instruction is not likely to occur. If count is zero this hint directs the instruction fetch unit that the branch is likely to occur more than 63 times.

This operation branches to a location that is specified as an offset from the program counter saving the value of the program counter into register 0.

The address of the instruction following this one is placed into register 0. Execution branches to the address specified by the offset field.

This operation branches to a location specified by a register saving the value of the program counter into a register.

The address of the instruction following this one is placed into register rd. Execution branches to the address specified by the contents of register rc.

Access disallowed exception occurs if the contents of register rc is not aligned on a quadlet boundary.

These operations compare two 64 bit values in a register against two 64 bit values read from two 64 bit memory locations as specified by two 64 bit addresses in a register and if equal store two new 64 bit values from a register into the memory locations. The values read from memory are catenated and placed in a register.

Two virtual addresses are extracted from the low order bits of the contents of registers rc and rb. Two 64 bit comparison values are extracted from the high order bits of the contents of registers rc and rb. Two 64 bit replacement values are extracted from the contents of register rd. The contents of memory using the specified byte order are read from the specified addresses treated as 64 bit values compared against the specified comparison values and if both read values are equal to the comparison values the two replacement values are written to memory using the specified byte order. If either are unequal no values are written to memory. The loaded values are catenated and placed in the register specified by rd.

The virtual addresses must be aligned that is it must be an exact multiple of the size expressed in bytes. If the address is not aligned an access disallowed by virtual address exception occurs.

These operations add the contents of a register to a sign extended immediate value to produce a virtual address and store the contents of a register into memory.

A virtual address is computed from the sum of the contents of register rc and the sign extended value of the offset field. The contents of memory using the specified byte order are read and treated as a 64 bit value. A specified operation is performed between the memory contents and the orginal contents of register rd and the result is written to memory using the specified byte order. The original memory contents are placed into register rd.

The computed virtual address must be aligned that is it must be an exact multiple of the size expressed in bytes. If the address is not aligned an access disallowed by virtual address exception occurs.

These operations add the contents of two registers to produce a virtual address and store the contents of a register into memory.

A virtual address is computed from the sum of the contents of register rc and the contents of register rb multiplied by operand size. The contents of memory using the specified byte order are read and treated as 64 bits. A specified operation is performed between the memory contents and the original contents of register rd and the result is written to memory using the specified byte order. The original memory contents are placed into register rd.

The computed virtual address must be aligned that is it must be an exact multiple of the size expressed in bytes. If the address is not aligned an access disallowed by virtual address exception occurs.

These operations take operands from two registers perform operations on partitions of bits in the operands and place the concatenated results in a third register.

The contents of registers rc and rb are partitioned into groups of operands of the size specified added halved and rounded as specified yielding a group of results each of which is the size specified. The results never overflow so limiting is not required by this operation. The group of results is catenated and placed in register rd.

Z zero rounding is not defined for unsigned operations and a Reservedlnstruction exception is raised if attempted. F floor rounding will properly round unsigned results downward.

A 128 bit immediate value is produced from the operation code the size field and the 16 bit imm field. The result is placed into register ra.

These operations take operands from a register and an immediate value perform operations on partitions of bits in the operands and place the concatenated results in a second register.

The contents of register rc is fetched and a 128 bit immediate value is produced from the operation code the size field and the 10 bit imm field. The specified operation is performed on these operands. The result is placed into register ra.

These operations take operands from a register and an immediate value perform operations on partitions of bits in the operands and place the concatenated results in a second register.

The contents of register rc is fetched and a 128 bit immediate value is produced from the operation code the size field and the 10 bit imm field. The specified operation is performed on these operands. The result is placed into register rd.

These operations take operands from three registers perform operations on partitions of bits in the operands and place the concatenated results in the third register.

The contents of registers rd rc and rb are fetched. The specified operation is performed on these operands. The result is placed into register rd.

These operations take operands from two registers perform operations on partitions of bits in the operands and place the concatenated results in a third register.

The contents of registers rc and rb are partitioned into groups of operands of the size specified. Partitions of the contents of register rb are shifted left by the amount specified in the immediate field and added to partitions of the contents of register rc yielding a group of results each of which is the size specified. Overflows are ignored and yield modular arithmetic results. The group of results is catenated and placed in register rd.

These operations take operands from two registers perform operations on partitions of bits in the operands and place the concatenated results in a third register.

The contents of registers rc and rb are partitioned into groups of operands of the size specified. Partitions of the contents of register rc are subtracted from partitions of the contents of register rb shifted left by the amount specified in the immediate field yielding a group of results each of which is the size specified. Overflows are ignored and yield modular arithmetic results. The group of results is catenated and placed in register rd.

These operations take operands from two registers perform operations on partitions of bits in the operands and place the concatenated results in a third register.

The contents of registers rc and rb are partitioned into groups of operands of the size specified and subtracted halved rounded and limited as specified yielding a group of results each of which is the size specified. The group of results is catenated and placed in register rd.

These operations take operands from two registers perform operations on partitions of bits in the operands and place the concatenated results in a third register.

Two values are taken from the contents of registers rc and rb. The specified operation is performed and the result is placed in register rd.

An exemplary embodiment of the Ensemble instructions is shown in . Ensemble Convolve Extract Immediate

These instructions take an address from a general register to fetch a large operand from memory a second operand from a general register perform a group of operations on partitions of bits in the operands and catenate the results together placing the result in a general register.

The contents of registers rd and rc are catenated as specified by the order parameter and used as a first value. A second value is the contents of register rb. The values are partitioned into groups of operands of the size specified and are convolved producing a group of values. The group of values is rounded and limited as specified yielding a group of results which is the size specified. The group of results is catenated and placed in register rd.

Z zero rounding is not defined for unsigned extract operations and a Reservedlnstruction exception is raised if attempted. F floor rounding will properly round unsigned results downward.

The order parameter of the instruction specifies the order in which the contents of registers rd and rc are catenated. The choice is significant because the contents of register rd is overwritten. When little endian order is specified the contents are catenated so that the contents of register rc is most significant left and the contents of register rd is least significant right . When big endian order is specified the contents are catenated so that the contents of register rd is most significant left and the contents of register rc is least significant right .

Referring to an ensemble convolve extract immediate doublets instruction ECON.X.I16 ECON.X.IM16 or ECON.X.IU16 convolves vector x w v u t s r q p o n m l k j i with vector h g f e d c b a yielding the products ax bw cv du et fs gr hq . . . as br cq dp eo fn gm hl ar bq cp do en fm gl hk aq bp co dn em fl gk hj rounded and limited as specified.

Referring to an ensemble convolve extract immediate complex doublets instruction ECON.X.IC 16 convolves vector x w v u t s r q p o n m l k j i with vector h g f e d c b a yielding the products ax bw cv du et fs gr hq as bt cq dr eo fp gm hn ar bq cp do en fm gl hk aq br co dp em fn gk hl rounded and limited as specified.

These instructions take an address from a general register to fetch a large operand from memory a second operand from a general register perform a group of operations on partitions of bits in the operands and catenate the results together placing the result in a general register.

The first value is the catenation of the contents of register rd and rc as specified by the order parameter. A second value is the contents of register rb. The values are partitioned into groups of operands of the size specified. The second values are multiplied with the first values then summed producing a group of result values. The group of result values is catenated and placed in register rd.

Referring to an ensemble convolve floating point half little endian instruction E.CON.F.16.L convolves vector x w v u t s r q p o n m l k j i with vector h gfedcb a yielding the products ax bw cv du et fs gr hq as br cq dp eo fn gm hl ar bq cp do en fm gl hk aq bp co dn em fl gk hj .

Referring to an ensemble convolve complex floating point half little endian instruction E.CON.C.F.16.L convolves vector x w v u t s r q p o n m l k j i with vector h g f e d c b a yielding the products ax bw cv du et fs gr hq as bt cq dr eo fp gm hn ar bq cp do en fin gl hk aq br co dp em fn gk hl .

These operations take operands from two registers and a short immediate value perform operations on partitions of bits in the operands and place the concatenated results in a third register.

The contents of registers rc and rb are partitioned into groups of operands of the size specified and multiplied added or subtracted or are catenated and partitioned into operands of twice the size specified. The group of values is rounded and limited as specified yielding a group of results each of which is the size specified. The group of results is catenated and placed in register rd.

For mixed signed multiplies the contents of register rc is signed and the contents of register rb is unsigned. The extraction operation and the result of mixed signed multiplies is signed.

Z zero rounding is not defined for unsigned extract operations and a Reservedlnstruction exception is raised if attempted. F floor rounding will properly round unsigned results downward.

Referring to an ensemble multiply extract immediate doublets instruction E.MULXI.16 or E.MUL.X.I.U.16 multiplies operand h g f e d c b a by operand p o n m l k j i yielding the products hp go fn em dl ck bj ai rounded and limited as specified.

Referring to another illustration of ensemble multiply extract immediate doublets instruction E.MUL.X.I.16 or E.MUL.X.I.U.16 .

Referring to an ensemble multiply extract immediate complex doublets instruction E.MULXIC.16 or E.MUL.X.I.U.16 multiplies operand h g f e d c b a by operand p o n m l k j i yielding the result gp ho go hp en fm em fn cl dk ck dl aj bi ai bj rounded and limited as specified. Note that this instruction prefers an organization of complex numbers in which the real part is located to the right lower precision of the imaginary part.

Referring to another illustration of ensemble multiply extract immediate complex doublets instruction E.IVIUL.X.I.C.16 or E.MUL.X.I.U.16 .

These operations take operands from two registers and a short immediate value perform operations on partitions of bits in the operands and place the catenated results in a third register.

The contents of registers rc and rb are partitioned into groups of operands of the size specified and multiplied added or subtracted or are catenated and partitioned into operands of twice the size specified. The contents of register rd are partitioned into groups of operands of the size specified and sign or zero ensemble and shifted as specified then added to the group of values computed. The group of values is rounded and limited as specified yielding a group of results which is the size specified. The group of results is catenated and placed in register rd.

For mixed signed multiplies the contents of register rc is signed and the contents of register rb as unsigned. The extraction operation the contents of register rd and the result of mixed signed multiplies are signed.

Z zero rounding is not defined for unsigned extract operations and a Reservedlnstruction exception is raised if attempted. F floor rounding will properly round unsigned results downward.

Referring to an ensemble multiply add extract immediate doublets instruction E.MUL.ADD.X.I.16 or E.MUL.ADD.X.I.U.16 multiplies operand h g f e d c b a by operand p o n m l k j i then adding x w v u t sr q yielding the products hp x go w fn v em u dl t ck s bj r ai q rounded and limited as specified.

Referring to another illustration of ensemble multiply add extract immediate doublets instruction E.MUL.ADDXI.16 or E.MUL.ADD.X.I.U.16 .

An ensemble multiply add extract immediate complex doublets instruction E.MUL.ADD.S.I.C.16 or G.MUL.ADD.X.I.U.16 multiplies operand gfedcb a by operand p o n m l k j i then adding x w v u t s r q yielding the result gp ho x go hp w en fm v em fn u cl dk t ck dl s aj bi r ai bj q rounded and limited as specified. Note that this instruction prefers an organization of complex numbers in which the real part is located to the right lower precision of the imaginary part.

Referring to an ensemble multiply add extract immediate complex doublets instruction E.MUL.ADD.X.I.C.16 or G.MUL.ADD.X.I.U.16 multiplies operand h gfe d c b a by operand p o n m l k j i then adding x w v u t s r q yielding the result gp ho x go hp w en fm v em fn u cl dk t ck dl s aj bi r ai bj q rounded and limited as specified. Note that this instruction prefers an organization of complex numbers in which the real part is located to the right lower precision of the imaginary part.

Referring to another illustration of ensemble add multiply extract immediate complex doublets instruction E.MUL.ADD.X.I.C.16 .

These operations take operands from three registers perform operations on partitions of bits in the operands and place the concatenated results in the third register.

The contents of registers rd rc and rb are fetched. The specified operation is performed on these operands. The result is placed into register rd.

These instructions take an address from a general register to fetch a large operand from memory a second operand from a general register perform a group of operations on partitions of bits in the operands and catenate the results together placing the result in a general register.

The contents of register rc is used as a virtual address and a value of specified size is loaded from memory. A second value is the contents of register rb. The values are partitioned into groups of operands of the size specified. The second values are multiplied with the first values then summed producing a group of result values. The group of result values is catenated and placed in register rd.

The memory multiply instructions W.MUL.MAT W.MUL.MAT.C W.MUL.MAT.M W.MUL.MAT.P W.MUL.MAT.U perform a partitioned array multiply of up to 8192 bits that is 64 128 bits. The width of the array can be limited to 64 32 or 16 bits but not smaller than twice the group size by adding one half the desired size in bytes to the virtual address operand 4 2 or 1. The array can be limited vertically to 128 64 32 or 16 bits but not smaller than twice the group size by adding one half the desired memory operand size in bytes to the virtual address operand.

The virtual address must either be aligned to 1024 gsize bytes or 512 gsize for W.MUL.MAT.C with gsize measured in bits or must be the sum of an aligned address and one half of the size of the memory operand in bytes and or one quarter of the size of the result in bytes. An aligned address must be an exact multiple of the size expressed in bytes. If the address is not valid an access disallowed by virtual address exception occurs.

A wide multiply octlets instruction W.MUL.MAT.type.64 type NONE M U P is not implemented and causes a reserved instruction exception as an ensemble multiply sum octlets instruction E.MUL.SUM.type.64 performs the same operation except that the multiplier is sourced from a 128 bit register rather than memory. Similarly instead of wide multiply complex quadlets instruction W.MUL.MAT.C.32 one should use an ensemble multiply complex quadlets instruction E.MUL.SUM.C.32 .

Referring to a wide multiply doublets instruction W.MUL.MAT W.MUL.MAT.M W.MUL.MAT.P W.MUL.MAT.U multiplies memory m31 m30 . . . m1 m0 with vector h g f e d c b a yielding products hm31 gm27 . . . bm7 am3 hm28 gm24 . . . bm4 am0 .

Referring to a wide multiply matrix complex doublets instruction W.MUL.MAT.C multiplies memory m 15 m 14 . . . m 1 m0 with vector h g f e d c b a yielding products hm 14 gm 15 . . . bm2 am3 hm12 gm 13 . . . bm0 am1 hm 13 gm 12 . . . bm 1 am0 .

These instructions take an address from a general register to fetch a large operand from memory a second operand from a general register perform a group of operations on partitions of bits in the operands and catenate the results together placing the result in a general register.

The contents of register rc is used as a virtual address and a value of specified size is loaded from memory. A second value is the contents of register rd. The group size and other parameters are specified from the contents of register rb. The values are partitioned into groups of operands of the size specified and are multiplied and summed producing a group of values. The group of values is rounded and limited as specified yielding a group of results which is the size specified. The group of results is catenated and placed in register ra.

NOTE The size of this operation is determined from the contents of register rb The multiplier usage is constant but the memory operand size is inversely related to the group size. Presumably this can be checked for cache validity.

We also use low order bits of rc to designate a size which must be consistent with the group size. Because the memory operand is cached the size can also be cached thus eliminating the time required to decode the size whether from rb or from rc.

The wide multiply matrix extract instructions W.MUL.MAT.X.B W.MUL.MAT.X.L perform a partitioned array multiply of up to 16384 bits that is 128 128 bits. The width of the array can be limited to 128 64 32 or 16 bits but not smaller than twice the group size by adding one half the desired size in bytes to the virtual address operand 8 4 2 or 1. The array can be limited vertically to 128 64 32 or 16 bits but not smaller than twice the group size by adding one half the desired memory operand size in bytes to the virtual address operand.

Bits .. of the contents of register rb specifies several parameters which control the manner in which data is extracted. The position and default values of the control fields allows for the source position to be added to a fixed control value for dynamic computation and allows for the lower 16 bits of the control field to be set for some of the simpler extract cases by a single GCOPYI instruction.

The 9 bit gssp field encodes both the group size gsize and source position spos according to the formula gssp 512 4 gsize spos. The group size gsize is a power of two in the range 1..128. The source position spos is in the range 0.. 2 gsize 1.

The virtual address must be aligned that is it must be an exact multiple of the operand size expressed in bytes. If the address is not aligned an access disallowed by virtual address exception occurs.

Z zero rounding is not defined for unsigned extract operations and a Reservedlnstruction exception is raised if attempted. F floor rounding will properly round unsigned results downward.

Referring to a wide multiply matrix extract doublets instruction W.MUL.MAT.X.B or W.MUL.MAT.X.L multiplies memory m63 m62 m61 . . . m2 m1 m0 with vector h g f e d c b a yielding the products

Referring to E a wide multiply matrix extract complex doublets instruction W.MUL.MAT.X with n set in rb multiplies memory m31 m30 m29 . . . m2 m1 m0 with vector h g f e d c b a yielding the products am7 bm6 cm 15 dm 14 em23 fm22 gm31 hm30 . . . 20 am2 bm3 cm10 dm 11 em 18 fm 19 gm26 hm27

am 1 bm0 cm9 dm8 em 17 fm 16 gm25 hm24 am0 bm 1 cm8 drn9 em I 16 fl 7 gm24 hm25 rounded and limited as specified.

These instructions take an address from a general register to fetch a large operand from memory a second operand from a general register perform a group of operations on partitions of bits in the operands and catenate the results together placing the result in a general register.

The contents of register rc is used as a virtual address and a value of specified size is loaded from memory. A second value is the contents of register rb. The values are partitioned into groups of operands of the size specified and are multiplied and summed or are convolved producing a group of sums. The group of sums is rounded and limited as specified yielding a group of results each of which is the size specified. The group of results is catenated and placed in register rd.

The wide multiply extract immediate matrix instructions W.MUL.MAT.X.I W.MUL.MAT.X.I.U W.MUL.MAT.X.I.M W.MUL.MAT.X.I.C perform a partitioned array multiply of up to 16384 bits that is 128 128 bits. The width of the array can be limited to 128 64 32 or 16 bits but not smaller than twice the group size by adding one half the desired size in bytes to the virtual address operand 8 4 2 or 1. The array can be limited vertically to 128 64 32 or 16 bits but not smaller than twice the group size by adding one half the desired memory operand size in bytes to the virtual address operand.

The virtual address must either be aligned to 2048 gsize bytes or 1024 lgsize for W.MUL.MAT.X.I.C or must be the sum of an aligned address and one half of the size of the memory operand in bytes and or one half of the size of the result in bytes. An aligned address must be an exact multiple of the size expressed in bytes. If the address is not valid an access disallowed by virtual address exception occurs.

Z zero rounding is not defined for unsigned extract operations and a Reservedlnstruction exception is raised if attempted. F floor rounding will properly round unsigned results downward.

Referring to a wide multiply extract immediate matrix doublets instruction W.MUL.MAT.X.I.16 or W.MUL.MAT.X.I.U.16 multiplies memory m63 m62 m61 . . . m2 m1 m0 with vector h gfedcb a yielding the products

Referring to a wide multiply matrix extract immediate complex doublets instruction W.MUL.MAT.X.I.C.16 multiplies memory m31 m30 m29 . . . m2 m1 m0 with vector h g f e d c b a yielding the products

 am7 bm6 cm15 dm14 em23 fm22 gm31 hm30 . . . am2 bm3 cm 10 dm11 em18 fm19 gm26 hm27 am1 bm0 cm9 dm8 em17 fm16 gm25 hm24am0 bm1 cm8 dm9 em16 f17 gm24 hm251 rounded and limited as specified.

These instructions take an address from a general register to fetch a large operand from memory a second operand from a general register perform a group of operations on partitions of bits in the operands and catenate the results together placing the result in a general register..

The contents of register rc is used as a virtual address and a value of specified size is loaded from memory. A second value is the contents of register rb. The values are partitioned into groups of operands of the size specified. The second values are multiplied with the first values then summed producing a group of result values. The group of result values is catenated and placed in register rd.

The wide multiply matrix floating point instructions W.MUL.MAT.F W.MUL.MAT.C.F perform a partitioned array multiply of up to 16384 bits that is 128 128 bits. The width of the array can be limited to 128 64 32 bits but not smaller than twice the group size by adding one half the desired size in bytes to the virtual address operand 8 4 or 2. The array can be limited vertically to 128 64 32 or 16 bits but not smaller than twice the group size by adding one half the desired memory operand size in bytes to the virtual address operand.

The virtual address must either be aligned to 2048 gsize bytes or 1024 gsize for W.MUL.MAT.C.F or must be the sum of an aligned address and one half of the size of the memory operand in bytes and or one half of the size of the result in bytes. An aligned address must be an exact multiple of the size expressed in bytes. If the address is not valid an access disallowed by virtual address exception occurs.

Referring to a wide multiply matrix floating point half instruction W.MUL.MAT.F multiplies memory m31 m30 m 1 mO with vector h gfedcb a yielding products lun31 gm27 . . . bm7 am3 hm28 gm24 . . . bm4 am0 .

Referring to a wide multiply matrix complex floating point half instruction W.MUL.MAT.F multiplies memory m15 m14 m 1 mO with vector h gfedcb a yielding products hm14 gm15 . . . bm2 am3 fun 12 gm13 . . . bm0 am1 lun13 gm12 . . . bm1 am0 .

These instructions take an address from a general register to fetch a large operand from memory second and third operands from general registers perform a group of operations on partitions of bits in the operands and catenate the results together placing the result in a general register.

The contents of register rc is used as a virtual address and a value of specified size is loaded from memory. Second and third values are the contents of registers rd and rb. The values are partitioned into groups of operands of the size specified. The second values are multiplied as polynomials with the first value producing a result which is reduced to the Galois field specified by the third value producing a group of result values. The group of result values is catenated and placed in register ra.

The wide multiply matrix Galois instruction W.MUL.MAT.G performs a partitioned array multiply of up to 16384 bits that is 128 128 bits. The width of the array can be limited to 128 64 32 or 16 bits but not smaller than twice the group size of 8 bits by adding one half the desired size in bytes to the virtual address operand 8 4 2 or 1. The array can be limited vertically to 128 64 32 or 16 bits but not smaller than twice the group size of 8 bits by adding one half the desired memory operand size in bytes to the virtual address operand.

The virtual address must either be aligned to 256 bytes or must be the sum of an aligned address and one half of the size of the memory operand in bytes and or one half of the size of the result in bytes. An aligned address must be an exact multiple of the size expressed in bytes. If the address is not valid an access disallowed by virtual address exception occurs.

Referring to a wide multiply matrix Galois instruction W.MUL.MAT.G multiplies memory m255 m254 m 1 mO with vector p o n m l k j i h g f e d c b a reducing the result modulo polynomial q yielding products pm255 om247 . . . bm31 am15 mod q pm254 om246 . . . bm30 am14 mod q pm248 om240 . . . bm16 am0 mod q .

These instructions take an address from a general register to fetch a large operand from memory a second operand from a general register perform a group of operations on partitions of bits in the operands and catenate the results together placing the result in a general register.

The contents of register rc is specifies as a virtual address and optionally an operand size and a value of specified size is loaded from memory. A second value is the catenated contents of registers rd and rb. Eight corresponding bits from the memory value are used to select a single result bit from the second value for each corresponding bit position. The group of results is catenated and placed in register ra.

The virtual address must either be aligned to 128 bytes or must be the sum of an aligned address and one half of the size of the memory operand in bytes. An aligned address must be an exact multiple of the size expressed in bytes. The size of the memory operand must be 8 16 32 64 or 128 bytes. If the address is not valid an access disallowed by virtual address exception occurs. When a size smaller than 128 bits is specified the high order bits of the memory operand are replaced with values corresponding to the bit position so that the same memory operand specifies a bit selection within symbols of the operand size and the same operation is performed on each symbol.

These instructions take an address from a general register to fetch a large operand from memory a second operand from a general register perform a group of operations on partitions of bits in the operands and catenate the results together placing the result in a general register.

The contents of register rc is used as a virtual address and a value of specified size is loaded from memory. A second value is the contents of register rb. The values are partitioned into groups of operands of a size specified. The low order bytes of the second group of values are used as addresses to choose entries from one or more tables constructed from the first value producing a group of values. The group of results is catenated and placed in register rd.

By default the total width of tables is 128 bits and a total table width of 128 64 32 16 or 8 bits but not less than the group size may be specified by adding the desired total table width in bytes to the specified address 16 8 4 2 or 1. When fewer than 128 bits are specified the tables repeat to fill the 128 bit width.

The default depth of each table is 256 entries or in bytes is 32 times the group size in bits. An operation may specify 4 8 16 32 64 128 or 256 entry tables by adding one half of the memory operand size to the address. Table index values are masked to ensure that only the specified portion of the table is used. Tables with just 2 entries cannot be specified if 2 entry tables are desired it is recommended to load the entries into registers and use G.MUX to select the table entries.

Failing to initialize the entire table is a potential security hole as an instruction in with a small depth table could access table entries previously initialized by an instruction with a large depth table. We could close this hole either by initializing the entire table even if extra cycles are required or by masking the index bits so that only the initialized portion of the table is used. Initializing the entire table with no penalty in cycles could require writing to as many as 128 entries at once which is quite likely to cause circuit complications. Initializing the entire table with writes to only one entry at a time requires writing 256 cycles even when the table is smaller. Masking the index bits is the preferred solution.

Masking the index bits suggests that this instruction for tables larger than 256 entries may be useful for a general purpose memory translate function where the processor performs enough independent load operations to fill the 128 bits. Thus the 16 32 and 64 bit versions of this function perform equivalent of 8 4 2 withdraw 8 4 or 2 load indexed and 7 3 or 1 group extract instructions. In other words this instruction can be as powerful as 23 11 or 5 existing instructions. The 8 bit version is a single cycle operation replacing existing instructions so these are not as big a win but nonetheless this is at least a 50 improvement on a 2 issue processor even with one cycle per load timing. To make this possible the default table size would become 65536 232 and 264 for 16 32 and 64 bit versions of the instruction.

For the big endian version of this instruction in the definition below the contents of register rb is complemented. This reflects a desire to organize the table so that the lowest addressed table entries are selected when the index is zero. In the logical implementation complementing the index can be avoided by loading the table memory differently for big endian and little endian versions. A consequence of this shortcut is that a table loaded by a big endian translate instruction cannot be used by a little endian translate instruction and vice versa.

The virtual address must either be aligned to 4096 bytes or must be the sum of an 20 aligned address and one half of the size of the memory operand in bytes and or the desired total table width in bytes. An aligned address must be an exact multiple of the size expressed in bytes. The size of the memory operand must be a power of two from 4 to 4096 bytes but must be at least 4 times the group size and 4 times the total table width. If the address is not valid an access disallowed by virtual address exception occurs.

According to one embodiment of the invention an initial implementation of the processor uses a Super Socket 7 compatible SS7 bus interface which is generally similar to and compatible with other Socket 7 and Super Socket 7 processors such as the Intel Pentium Pentium with MMX Technology AMD K6 K6 II K6 III IDT Winchip C6 2 2A 3 4 Cyrix 6 86 etc. and other Socket 7 chipsets listed below.

The SS7 bus interface behavior is quite complex but well known due to the leading position of the Intel Pentium design. This document does not yet contain all the detailed information related to this bus and will concentrate on the differences between the Zeus SS7 bus and other designs. For functional specification and pin interface behavior the Pentium Processor Family Developer s Manual is a primary reference. For 100 MHz SS7 bus timing data the AMD K6 2 Processor Data Sheet is a primary reference.

In signals which are different from Pentium pinout are indicated by italics and underlining. Generally other Pentium compatible processors such as the AMD K6 2 define these signals.

The Bus Control Register provides direct control of Emulator signals selecting output states and active input states for these signals.

The layout of the Bus Control Register is designed to match the assignment of signals to the Event Register.

Several of the signals A20M INIT NMI SMI STPCLK IGNNE are inputs that have purposes primarily defined by the needs of x86 processor emulation. They have no direct purpose in the Zeus processor other than to signal an event which is handled by software. Each of these signals is an input sampled on the rising edge of each bus clock if the input signal matches the active level specified in the bus control register the corresponding bit in the event register is set. The bit in the event register remains set even if the signal is no longer active until cleared by software. If the event register bit is cleared by software it is set again on each bus clock that the signal is sampled active.

A20M address bit mask inverted when asserted low directs an x86 emulator to generate physical addresses for which bit is zero.

The A20M bit of the bus control register selects which level of the A20M signal will generate an event in the A20M bit of the event register. Clearing to 0 the A20M bit of the bus control register will cause the A20M bit of the event register to be set when the A20M signal is asserted low .

Asserting the A20M signal causes the emulator to modify all current TB mappings to produce a zero value for bit of the byte address. The A20M bit of the bus control register is then set to 1 to cause the A20M bit of the event register to be set when the A20M signal is released high .

Releasing the A20M signal causes the emulator to restore the TB mapping to the original state. The A20M bit of the bus control register is then cleared to 0 again to cause the A20M bit of the event register to be set when the A20M signal is asserted low .

INIT initialize when asserted high directs an x86 emulator to begin execution of the external ROM BIOS.

The INIT bit of the bus control register is normally set to 1 to cause the INIT bit of the event register to be set when the INIT signal is asserted high .

INTR maskable interrupt when asserted high directs an x86 emulator to simulate a maskable interrupt by generating two locked interrupt acknowlege special cycles. External hardware will normally release the INTR signal between the first and second interrupt acknowlege special cycle.

The INTR bit of the bus control register is normally set to 1 to cause the INTR bit of the event register to be set when the INTR signal is asserted high .

NMI non maskable interrupt when asserted high directs an x86 emulator to simulate a non maskable interrupt. External hardware will normally release the NMI signal.

The NMI bit of the bus control register is normally set to 1 to cause the NMI bit of the event register to be set when the NMI signal is asserted high .

SMI system management interrupt inverted when asserted low directs an x86 emulator to simulate a system management interrupt by flushing caches and saving registers and asserting low SMIACT system management interrupt active inverted . External hardware will normally release the SMI .

The SMI bit of the bus control register is normally cleared to 0 to cause the SMI bit of the event register to be set when the SMI signal is asserted low .

STPCLK stop clock inverted when asserted low directs an x86 emulator to simulate a stop clock interrupt by flushing caches and saving. registers and performing a stop grant special cycle.

The STPCLK bit of the bus control register is normally cleared to 0 to cause the STPCLK bit of the event register to be set when the STPCLK signal is asserted low .

Software must set to 1 the STPCLK bit of the bus control register to cause the STPCLK bit of the event register to be set when the STPCLK signal is released high to resume execution. Software must cease producing bus operations after the stop grant special cycle. Usually software will use the B.HALT instruction in all threads to cease performing operations. The processor PLL continues to operate and the processor must still sample INIT INTR RESET NMI SMI to place them in the event register and respond to RESET and inquire and snoop transactions so long as the bus clock continues operating.

The bus clock itself cannot be stopped until the stop grant special cycle. If the bus clock is stopped it must stop in the low 0 state. The bus clock must be operating at frequency for at least 1 ms before releasing STPCLK or releasing RESET. While the bus clock is stopped the processor does not sample inputs or responds to RESET or inquire or snoop transactions.

External hardware will normally release STPCLK when it is desired to resume execution. The processor should respond to the STPCLK bit in the event register by awakening one or more threads.

The IGNNE bit of the bus control register selects which level of the IGNNE signal will generate an event in the IGNNE bit of the event register. Clearing to 0 the IGNNE bit of the bus control register will cause the IGNNE bit of the event register to be set when the IGNNE signal is asserted low .

Asserting the IGNNE signal causes the emulator to modify its processing to ignore numeric errors if suitably enabled to do so. The IGNNE bit of the bus control register is then set to 1 to cause the IGNNE bit of the event register to be set when the IGNNE signal is released high .

Releasing the IGNNE signal causes the emulator to restore the emulation to the original state. The IGNNE bit of the bus control register is then cleared to 0 again to cause the IGNNE bit of the event register to be set when the IGNNE signal is asserted low .

Several of the signals BP3..BPO FERR IERR PM1..PM0 SMIACT are outputs that have purposes primarity defined by the needs of x86 processor emulation. They are driven from the bus control register that can be written by software.

Zeus support the Socket 7 protocols for inquiry invalidation and coherence of cache lines. The protocols are implemented in hardware and do not interrupt the processor as a result of bus activity. Cache access cycles may be stolen for this purpose which may delay completion of processor memory activity.

Locked cycles occur as a result of synchronization operations Store swap instructions performed by the processor. For x86 emulation locked cycles also occur as a result of setting specific memory mapped control registers.

Bus lock LOCK is asserted low automatically as a result of store swap instructions 30 that generate bus activity which always perform locked read modify write cycles on 64 bits of data. Note that store swap instructions that are performed on cache sub blocks that are in the E or M state need not generate bus activity.

Bus lock LOCK is also asserted low on subsequent bus transactions by writing a one 1 to the bus lock bit of the bus control register. Split cycle SCYC is similarly asserted high if a one 1 is also written to the split cycle bit of the bus emulation control register.

All subsequent bus transactions will be performed as a locked sequence of transactions asserting bus lock LOCK low and optionally split cycle SCYC high until zeroes 0 are written to the bus lock and split cycle bits of the bus control register. The next bus transaction completes the locked sequence releasing bus lock LOCK high and split cycle SCYC low at the end of the transaction. If the locked transaction must be aborted because of bus activity such as backoff a lock broken event is signalled and the bus lock is released.

Unless special care is taken the bus transactions of all threads occur as part of the locked sequence of transactions. Software can do so by interrupting all other threads until the locked sequence is completed. Software should also take case to avoid fetching instructions during the locked sequence such as by executing instructions out of niche or ROM memory.

Software should also take care to avoid terminating the sequence with event handling prior to releasing the bus lock such as by executing the sequence with events disabled other than the lock broken event .

The purpose of this facility is primarily for x86 emulation purposes in which we are willing to perform acts such as stopping all the other threads in the name of compatibility. It is possible to take special care in hardware to sort out the activity of other threads and break the lock in response to events. In doing so the bus unit must defer bus activity generated by other threads until the locked sequence is completed. The bus unit should inhibit event handling while the bus is locked.

The Socket 7 bus performs transfers of 1 8 bytes within an octlet boundary or 32 bytes on a triclet boundary.

Transfers sized at 16 bytes hexlet are not available as a single transaction they are 20 performed as two bus transactions.

Bus transactions begin by gaining control of the bus TODO not shown and in the initial cycle asserting ADS M 10 A BE W R CACHE PWT and PCD. These signals indicate the type size and address of the transaction. One or more octiets of data are returned on a read the external system asserts BRDY and or NA and D or accepted on a write TODO not shown .

The external system is permitted to affect the cacheability and exclusivity of data returned to the processor using the KEN and WB WT signals.

Input Output transfers Interrupt acknowledge and special bus cycles stop grant flush acknowledge writeback halt flush shutdown are performed by uncached loads and stores to a memory mapped control region.

An interrupt acknowlege cycle is performed by two byte loads to the control space dc 1 the first with a byte address ba of 4 A31.3 0 BE4 0 BE7.5 3.0 1 the second with a byte address ba of 0 A31.3 0 BE0 0 BE7.1 1 . The first byte read is ignored the second byte contains the interrupt vector. The external system normally releases INTR between the first and second byte load.

A shutdown special cycle is performed by a byte store to the control space dc 1 a byte address ba of 0 A31.3 0 BE0 0 BE7.1 1 .

A flush special cycle is performed by a byte store to the control space dc 1 with a byte address ba of 1 A31.3 0 BE1 0 BE7.2 0 1 .

A halt special cycle is performed by a byte store to the control space dc 1 with a byte address ba of 2 A31.3 0 BE2 0 BE7.3 1.0 1 .

A stop grant special cycle is performed by a byte store to the control space dc 1 with a byte address ba of 0x12 A31.3 2 BE2 0 BE7.3 1.0 1 .

A writeback special cycle is performed by a byte store to the control space dc 1 with a byte address ba of 3 A31.3 0 BE3 0 BE7.4 2.0 1 .

A flush acknowledge special cycle is performed by a byte store to the control space dc 1 with a byte address ba of 4 A31.3 0 BE4 0 BE7.5 3.0 1 .

A back trace message special cycle is performed by a byte store to the control space dc 1 with a byte address ba of 5 A31.3 0 BE5 0 BE7.6 4.0 1 .

Performing load or store operations of other sizes doublet quadlet octlet hexlet to the control space dc 1 or operations with other byte address ba values produce bus operations which are not defined by the Super Socket 7 specifications and have undefined effect on the system.

An input cycle is performed by a byte doublet or quadlet load to the data space dc 0 with a byte address ba of the I O address. The address may not be aligned and if it crosses an octlet boundary will be performed as two separate cycles.

An output cycle is performed by a byte doublet or quadlet store to the data space dc 0 with a byte address ba of the UO address. The address may not be aligned and if it crosses an octlet boundary will be performed as two separate cycles.

Performing load or store operations of other sizes octlet hexlet to the data space dc 0 produce bus operations which are not defined by the Super Socket 7 specifications and have undefined effect on the system.

The other bus cycles are accessed explicitly by uncached memory accesses to particular physical address ranges. Appropriately sized load and store operations must be used to perform the specific bus cycles required for proper operations. The dc field must equal 0 for I O operations and must equal 1 for control operations. Within this address range bus transactions are sized no greater than 4 bytes quadlet and do not cross quadlet boundaries.

Exceptions signal several kinds of events 1 events that are indicative of failure of the software or hardware such as arithmetic overflow or parity error 2 events that are hidden from the virtual process model such as translation buffer misses 3 events that infrequently occur but may require corrective action such as floating point underflow. In addition there are 4 external events that cause scheduling of a computational process such as clock events or completion of a disk transfer.

Each of these types of events require the interruption of the current flow of execution handling of the exception or event and in some cases descheduling of the current task and rescheduling of another. The Zeus processor provides a mechanism that is based on the multi threaded execution model of Mach. Mach divides the well known UNIX process model into two parts one called a task which encompasses the virtual memory space file and resource state and the other called a thread which includes the program counter stack space and other register file state. The sum of a Mach task and a Mach thread exactly equals one UNIX process and the Mach model allows a task to be associated with several threads. On one processor at any one moment in time at least one task with one thread is running.

In the taxonomy of events described above the cause of the event may either be synchronous to the currently running thread generally types 1 2 and 3 or asynchronous and associated with another task and thread that is not currently running generally type 4.

For these events Zeus will suspend the currently running thread in the current task saving a minimum of registers and continue execution at a new program counter. The event handler may perform some minimal computation and return restoring the current threads registers or save the remaining registers and switch to a new task or thread context.

Facilities of the exception memory management and interface systems are themselves memory mapped in order to provide for the manipulation of these facilities by high level language compiled code. The sole exception is the register file itself for which standard store and load instructions can save and restore the state.

Ephemeral Program State EPS is defined as program state which affects the operation of certain instructions but which does not need to be saved and restored as part of user state.

Because these bits are not saved and restored the sizes and values described here are not visible to software. The sizes and values described here were chosen to be convenient for the definitions in this documentation. Any mapping of these values which does not alter the functions described may be used in a conforming implementation. For example either of the EPS states may be implemented as a thermometer coded vector or the ContinuationState field may be represented with specific values for each AccessDetailRequired exception which an instruction execution may encounter.

The ContinuationState bits are ephemeral because if they are cleared as a result of a context switch the associated exceptions can happen over again. The AccessDetail exception handlers will then set the bits again as they were before the context switch. In the case where an AccessDetail exception handler must indicate an error care must be taken to perform some instruction at the target of the Branch Back instruction by the exception handler is exited that will operate properly with ContinuationState0.

The ExceptionState bits are ephemeral because they are explicitly set by event handling and cleared by the termination of event handling including event handling that results in a context switch.

Events are single bit messages used to communicate the occurrence of events between threads and interface devices.

The Event Register appears at several locations in memory with slightly different side effects on read and write operations.

The Event Register appears at three different locations for which three functions of the Event Register are performed as described above. The physical address of an Event Register for function f byte b is 

The table below shows the events and their corresponding event number. The priority of these events is soft in that dispatching from the event register is controlled by software.

TODO notwithstanding the above using the E.LOGMOST.0 instruction is handy for prioritizing these events so if you ve got a preference as to numbering speak up 

The Event Mask one per thread control whether each of the events described above is permitted to cause an exception in the corresponding thread.

There are as many Event Masks as threads. The physical address of an Event Mask for thread th byte b is 

The table below shows the exceptions the corresponding exception number and the parameter supplied by the exception handler in register .

The GlobalTBMiss exception occurs when a load store or instruction fetch is attempted while none of the GlobalTB entries contain a matching virtual address. The Zeus processor uses a fast software based exception handler to fill in a missing GlobalTB entry.

There are several possible ways that software may maintain page tables. For purposes of this discussion it is assumed that a virtual page table is maintained in which 128 bit GTB values for each 4k byte page in a linear table which is itself in virtual memory. By maintaining the page table in virtual memory very large virtual spaces may be managed without keeping a large amount of physical memory dedicated to page tables.

Because the page table is kept in virtual memory it is possible that a valid reference may cause a second GTBMiss exception if the virtual address that contains the page table is not present in the GTB. The processor is designed to permit a second exception to occur within an exception handler causing a branch to the SecondException handler. However to simplify the hardware involved a SecondException exception saves no specific information about the exception handling depends on keeping enough relevant information in registers to recover from the second exception.

Zeus is a multithreaded processor which creates some special considerations in the exception handler. Unlike a single threaded processor it is possible that multiple threads may nearly simultaneously reference the same page and invoke two or more GTB misses and the fully associative construction of the GTB requires that there be no more than one matching entry for each global virtual address. Zeus provides a search and insert operation GTBUpdateFill to simplify the handling of the GTB. This operation also uses hardware GTB pointer registers to select GTB entries for replacement in FIFO priority.

A further problem is that software may need to modify the protection information contained in the GTB such as to remove read and or write access to a page in order to infer which parts of memory are in use or to remove pages from a task. These modifications may occur concurrently with the GTBMiss handler so software must take care to properly synchronize these operations. Zeus provides a search and update operation GTBUpdate to simplify updating GTB entries.

When a large number of page table entries must be changed noting the limited capacity of the GTB can reduce the work. Reading the GTB can be less work than matching all modified entries against the GTB contents. To facilitate this Zeus also provides read access to the hardware GTB pointers to further permit scanning the G7113 for entries which have been replaced since a previous scan. GTB pointer wraparound is also logged so it can be determined that the entire GTB needs to be scanned if all entries have been replaced since a previous scan.

On a GTBMiss the handler retrieves a base address for the virtual page table and constructs an index by shifting away the page offset bits of the virtual address. A single 128 bit indexed load retrieves the new GTB entry directly except that a virtual page table miss causes a second exception handled below . A single 128 bit store to the GTBUpdateFill location places the entry into the GTB after checking to ensure that a concurrent handler has not already placed the entry into the GTB.

A second exception occurs on a virtual page table miss. It is possible to service such a page table miss directly however the page offset bits of the virtual address have been shifted away and have been lost. These bits can be recovered in such a case a dummy GTB entry is constructed which will cause an exception other than GTBMiss upon returning. A re execution of the offending code will then invoke a more extensive handler making the full virtual address available.

For purposes of this example it is assumed that checking the contents of r2 against the 20 contents of BasePT is a good way to ensure that the second exception handler was entered from the GlobalTBMiss handler.

There are no special registers to indicate details about the exception such as the virtual address at which an access was attempted or the operands of a floating point operation that results in an exception. Instead this information is available via general purpose registers or registers stored in memory.

When a synchronous exception or asynchronous event occurs the original contents of registers 0.3 are saved in memory and replaced with 0 program counter privilege level and ephemeral program state 1 event data pointer 2 exception code and 3 when applicable failing address or instruction. A new program counter and privilege level is loaded from memory and execution begins at the new address. After handling the exception and restoring all but one register a branch back instruction restores the final register and resumes execution.

During exception handling any asynchronous events are kept pending until a BranchBack instruction is performed. By this mechanism we can handle exceptions and events one at a time without the need to interrupt and stack exceptions. Software should take care to avoid keeping the handling of asynchronous events pending for too long.

When a second exception occurs in a thread which is handling an exception all the above operations occur except for the saving and replacing of registers 0..3 in memory. A distinct exception code SecondException replaces the normal exception code. By this mechanism a fast exception handler for GlobalTBMiss can be written in which a second GlobalTBMiss or FixedPointOverflow exception may safely occur.

When a third exception occurs in a thread which is handling an exception an immediate transfer of control occurs to the machine check vector address with information about the exception available in the machine check cause field of the status register. The transfer of control may overwrite state that may be necessary to recover from the exception the intent is to provide a satisfactory post mortem indication of the characteristics of the failure.

This section describes in detail the conditions under which exceptions occur the parameters passed to the exception handler and the handling of the result of the procedure.

The Reservedlnstruction exception occurs when an instruction code which is reserved for future definition as part of the Zeus architecture is executed.

This exception occurs when a load store branch or gateway refers to an aligned memory operand with an improperly aligned address or if architecture description parameter LB 1 may also occur if the add or increment of the base register or program counter which generates the address changes the unmasked upper 16 bits of the local address.

This exception occurs when a read load write store execute or gateway attempts to access a virtual address for which the matching cache tag entry does not permit this access.

This exception occurs when a read load write store or execute attempts to access a virtual address for which the matching virtual cache entry would permit this access but the detail bit is set.

The exception handler should determine accessibility. If the access should be allowed the continuepastdetail bit is set and execution returns. Upon return execution is restarted and the access will be retried. Even if the detail bit is set in the matching virtual cache entry access will be permitted.

This exception occurs when a read load write store execute or gateway attempts to access a virtual address for which the matching global TB entry does not permit this access.

The exception handler should determine accessibility modify the virtual memory state if desired and return if the access should be allowed. Upon return execution is restarted and the access will be retried.

This exception occurs when a read load write store execute or gateway attempts to access a virtual address for which the matching global TB entry would permit this access but the detail bit in the global TB entry is set.

The exception handler should determine accessibility and return if the access should be allowed. Upon return execution is restarted and the access will be allowed. If the access is not to be allowed the handler should not return.

This exception occurs when a read load write store execute or gateway attempts to access a virtual address for which no global TB entry matches.

The exception handler should load a global TB entry that defines the translation and protection for this address. Upon return execution is restarted and the global TB access will be attempted again.

This exception occurs when a read load write store execute or gateway attempts to access a virtual address for which the matching local TB entry does not permit this access.

The exception handler should determine accessibility modify the virtual memory state if desired and return if the access should be allowed. Upon return execution is restarted and the access will be retried.

This exception occurs when a read load write store execute or gateway attempts to access a virtual address for which the matching local TB entry would permit this access but the detail bit in the local TB entry is set.

The exception handler should determine accessibility and return if the access should be allowed. Upon return execution is restarted and the access will be allowed. If the access is not to be allowed the handler should not return.

This exception occurs when a read load write store execute or gateway attempts to access a virtual address for which no local TB entry matches.

The exception handler should load a local TB entry that defines the translation and protection for this address. Upon return execution is restarted and the local TB access will be attempted again.

The address of the instruction that was the cause of the exception is passed as the contents of register 0. The exception handler should attempt to perform the function specified in the instruction and service any exceptional conditions that occur.

The address of the instruction which was the cause of the exception is passed as the contents of register 0. The exception handler should attempt to perform the function specified in the instruction and service any exceptional conditions that occur.

Certain external and internal events cause the processor to invoke reset or error recovery operations. These operations consist of a full or partial reset of critical machine state including initialization of the threads to begin fetching instructions from the start vector address. Software may determine the nature of the reset or error by reading the value of the control register in which finding the reset bit set 1 indicates that a reset has occurred and finding both the reset bit cleared 0 indicates that a machine check has occurred. When either a reset or machine check has been indicated the contents of the status register contain more detailed information on the cause.

A reset may be caused by a power on reset a bus reset a write of the control register which sets the reset bit or internally detected errors including meltdown detection and double check.

A reset causes the processor to set the configuration to minimum power and low clock speed note the cause of the reset in the status register stabilize the phase locked loops disable the MMU from the control register and initialize a all threads to begin execution at the start vector address.

Other system state is left undefined by reset and must be explicitly initialized by software this explicitly includes the thread register state LTB and GTB state superspring state and external interface devices. The code at the start vector address is responsible for initializing these remaining system facilities and reading further bootstrap code from an external ROM.

A reset occurs upon initial power on. The cause of the reset is noted by initializing the Status Register and other registers to the reset values noted below.

A reset occurs upon observing that the RESET signal has been at active. The cause of the reset is noted by initializing the Status Register and other registers to the reset values noted below.

A reset occurs upon writing a one to the reset bit of the Control Register. The cause of the reset is noted by initializing the Status Register and other registers to the reset values noted below.

A reset occurs if the temperature is above the threshold set by the meltdown margin field of the configuration register. The cause of the reset is noted by setting the meltdown detected bit of the Status Register.

A reset occurs if a second machine check occurs that prevents recovery from the first machine check. Specifically the occurrence of an exception in event thread watchdog timer error or bus error while any machine check cause bit is still set in the Status Register results in a double machine check reset. The cause of the reset is noted by setting the double check bit of the Status Register.

Detected hardware errors such as communications errors in the bus a watchdog timeout error or internal cache parity errors invoke a machine check. A machine check will disable the MMU to translate all local virtual addresses to equal physical addresses note the cause of the exception in the Status Register and transfer control of the all threads to the start vector address. This action is similar to that of a reset but differs in that the configuration settings and thread state are preserved.

Recovery from machine checks depends on the severity of the error and the potential loss of information as a direct cause of the error. The start vector address is designed to reach internal ROM memory so that operation of machine check diagnostic and recovery code need not depend on proper operation or contents of any external device. The program counter and register file state of the thread prior to the machine check is lost except for the portion of the program counter saved in the Status Register so diagnostic and recovery code must not assume that the register file state is indicative of the prior operating state of the thread. The state of the thread is frozen similarly to that of an exception.

Machine check diagnostic code determines the cause of the machine check from the processor s Status Register and as required the status and other registers of external bus devices.

Recovery code will generally consume enough time that real time interface performance targets may have been missed. Consequently the machine check recovery software may need to repair further damage such as interface buffer underruns and overruns as may have occurred during the intervening time.

This final recovery code which re initializes the state of the interface system and recovers a functional event thread state may return to using the complete machine resources as the condition which caused the machine check will have been resolved.

When a parity or uncorrectable error occurs in an on chip cache such an error is generally non recoverable. These errors are non recoverable because the data in such caches may reside anywhere in memory and because the data in such caches may be the only up to date copy of that memory contents. Consequently the entire contents of the memory store is lost and the severity of the error is high enough to consider such a condition to be a system failure.

The machine check provides an opportunity to report such an error before shutting down a system for repairs.

There are specific means by which a system may recover from such an error without failure such as by restarting from a system level checkpoint from which a consistent memory state can be recovered.

When a parity or communications error occurs in the system bus such an error may be partially recoverable.

Bits corresponding to the affected bus operation are set in the processor s Status Register. Recovery software should determine which devices are affected by querying the Status Register of each device on the affected MediaChannel channels.

If the error is simply a communications error resetting appropriate devices and restarting tasks may recover from the error. Read and write transactions may have been underway at the time of a machine check and may or may not be reflected in the current system state.

If the error is from a parity error in memory the contents of the affected area of memory is lost and consequently the tasks associated with that memory must generally be aborted or resumed from a task level checkpoint. If the contents of the affected memory can be recovered from mass storage a complete recovery is possible.

If the affected memory is that of a critical part of the operating system such a condition is considered a system failure unless recovery can be accomplished from a system level checkpoint.

A watchdog timeout error indicates a general software or hardware failure. Such an error is generally treated as non recoverable and fatal.

When an event thread suffers an exception the cause of the exception and a portion of the virtual address at which the exception occurred are noted in the Status Register. Because under normal circumstances the event thread should be designed not to encounter exceptions such exceptions are treated as non recoverable fatal errors.

A reset or machine check causes the Zeus processor to stabilize the phase locked loops disable the local and global to translate all local virtual addresses to equal physical addresses and initialize all threads to begin execution at the start vector address.

The start address is used to initialize the threads with a program counter upon a reset or machine check. These causes of such initialization can be differentiated by the contents of the Status Register.

The start address is a virtual address which when translated by the local TB and global TB to a physical address is designed to access the internal ROM code. The internal ROM space is chosen to minimize the number of internal resources and interfaces that must be operated to begin execution or recover from a machine check.

Zeus internal ROM code performs reset initialization of on chip resources including the LZC and LOC followed by self testing. The BIOS ROM should be scanned for a special prefix that indicates that Zeus native code is present in the ROM in which case the ROM code is executed directly otherwise execution of a BIOS level x86 emulator is begun.

Zeus defines a 64 bit physical address but while residing in a S7 pin out can address a maximum of 4 Gb of main memory. In other packages the core Zeus design can provide up to 64 bit external physical address spaces. Bit .. of the physical address distinguishes between internal on chip physical addresses where bits .. FFFFFFFF and external off chip physical addresses where bits ..FFFFFFFF.

The last hexlet of the internal ROM contains data that describes implementation dependent choices within the architecture specification. The last quadlet of the internal ROM contains a branch immediate instruction so the architecture description is limited to 96 bits.

The architecture description register contains a machine readable version of the architecture framework parameters T CE CS CT LE GE and GT described in the Architectural Framework section on page 25.

The status register is a 64 bit register with both read and write access though the only legal value which may be written is a zero to clear the register. The result of writing a non zero value is not specified.

The bus reset bit of the status register is set upon the completion of a bus reset initiated by the RESET pin of the Socket 7 interface.

The double check bit of the status register is set when a second machine check occurs that prevents recovery from the first machine check or which is indicative of machine check recovery software failure. Specifically the occurrence of an event exception watchdog timeout bus error or meltdown while any reset or machine check cause bit of the status register is still set results in a double check reset.

The meltdown bit of the status register is set when the meltdown detector has discovered an on chip temperature above the threshold set by the meltdown threshold field of the control register which causes a reset to occur.

The event exception bit of the status register is set when an event thread suffers an exception which causes a machine check. The exception code is loaded into the machine check detail field of the status register and the machine check program counter is loaded with the low order 32 bits of the program counter and privilege level.

The watchdog timeout bit of the status register is set when the watchdog timer register is equal to the clock cycle register causing a machine check.

The bus error bit of the status register is set when a bus transaction error bus timeout invalid transaction code invalid address parity errors has caused a machine check.

The cache error bit of the status register is set when a cache error such as a cache parity error has caused a machine check.

The vm error bit of the status register is set when a virtual memory error such as a GTB multiple entry selection error has caused a machine check.

The machine check detail field of the status register is set when a machine check has been completed. For an exception in event thread the value indicates the type of exception for which the most recent machine check has been reported. For a bus error this field may indicate additional detail on the cause of the bus error. For a cache error this field may indicate the address of the error at which the cache parity error was detected

The machine check program counter field of the status register is loaded with bits .. of the program counter and privilege level at which the most recent machine check has occurred. The value in this field provides a limited diagnostic capability for purposes of software development or possibly for error recovery.

The control register is a 64 bit register with both read and write access. It is altered only by write access to this register.

The reset bit of the control register provides the ability to reset an individual Zeus device in a system. Writing a one 1 to this bit is equivalent to a power on reset or a bus reset.

The duration of the reset is sufficient for the operating state changes to have taken effect. At the completion of the reset operation the internal reset bit of the status register is set and the reset bit of the control register is cleared 0 .

The MMU bit of the control register provides the ability to enable or disable the MMU features of the Zeus processor. Writing a zero 0 to this bit disables the MMU causing all 20 MMU related exceptions to be disabled and causing all load store program and gateway virtual addresses to be treated as physical addresses. Writing a one 1 to this bit enables the MMU and MMU related exceptions. On a reset or machine check this bit is cleared 0 thus disabling the MMU.

The parity bit of the control register provides the ability to enable or disable the cache parity feature of the Zeus processor. Writing a zero 0 to this bit disables the parity check causing the parity check machine check to be disabled. Writing a one 1 to this bit enables the cache parity machine check. On a reset or machine check this bit is cleared 0 thus disabling the cache parity check.

The meltdown bit of the control register provides the ability to enable or disable the meltdown detection feature of the Zeus processor. Writing a zero 0 to this bit disables the meltdown detector causing the meltdown detected machine check to be disabled. Writing a one 1 to this bit enables the meltdown detector. On a reset or machine check this bit is cleared 0 thus disabling the meltdown detector.

The LOC timing bits of the control register provide the ability to adjust the cache timing of the Zeus processor. Writing a zero 0 to this field sets the cache timing to its slowest state enhancing reliability but limiting clock rate. Writing a seven 7 to this field sets the cache timing to its fastest state limiting reliability but enhancing performance. On a reset or machine check this field is cleared 0 thus providing operation at low clock rate. Changing this register should be performed when the cache is not actively being operated.

The LOC stress bits of the control register provide the ability to stress the LOC parameters by adjusting voltage levels within the LOC. Writing a zero 0 to this field sets the cache parameters to its normal state enhancing reliability. Writing a non zero value 1 2 or 3 to this field sets the cache parameters to levels at which cache reliability is slightly compromised. The stressed parameters are used to cause LOC cells with marginal performance to fail during self test so that redundancy can be employed to enhance reliability. On a reset or machine check this field is cleared 0 thus providing operation at normal parameters. Changing this register should be performed when the cache is not actively being operated.

The clock timing bits of the control register provide the ability to adjust the clock timing of the Zeus processor. Writing a zero 0 to this field sets the clock timing to its slowest state enhancing reliability but limiting clock rate. Writing a seven 7 to this field sets the clock timing to its fastest state limiting reliability but enhancing performance. On a power on reset bus reset or machine check this field is cleared 0 thus providing operation at low clock rate. The internal clock rate is set to clock timing 1 2 external clock rate . Changing this register should be performed along with a control register reset.

The global access bits of the control register determine whether a local TB miss cause an exceptions or treatment as a global address. A single bit selected by the privilege level active for the access from four bit configuration register field Global Access GA determines the result. If GA is zero 0 the failure causes an exception if it is one 1 the failure causes the address to be used as a global address directly.

The niche limit bits of the control register determine which cache lines are used for cache access and which lines are used for niche access. For addresses pa14.8

The Zeus processor provides internal clock facilities using three registers a clock cycle register that increments one every cycle a clock event register that sets the clock bit in the event register and a clock watchdog register that invokes a clock watchdog machine check. These registers are memory mapped.

Each Zeus processor includes a clock that maintains processor clock cycle accuracy. The value of the clock cycle register is incremented on every cycle regardless of the number of instructions executed on that cycle. The clock cycle register is 64 bits long.

For testing purposes the clock cycle register is both readable and writable though in normal operation it should be written only at system initialization time there is no mechanism provided for adjusting the value in the clock cycle counter without the possibility of losing cycles.

An event is asserted when the value in the clock cycle register is equal to the value in the clock event register which sets the clock bit in the event register.

It is required that a sufficient number of bits be implemented in the clock event register so that the comparison with the clock cycle register overflows no more frequently than once per second. 32 bits is sufficient for a 4 GHz clock. The remaining unimplemented bits must be zero whenever read and ignored on write. Equality is checked only against bits that are implemented in both the clock cycle and clock event registers.

For testing purposes the clock event register is both readable and writable though in normal operation it is normally written to.

A Machine Check is asserted when the value in the clock cycle register is equal to the value in the clock watchdog register which sets the watchdog timeout bit in the control register.

A Machine Check or a Reset of any cause including a clock watchdog disables the clock watchdog machine check. A write to the clock watchdog register enables the clock watchdog machine check.

It is required that a sufficient number of bits be implemented in the clock watchdog register so that the comparison with the clock cycle register overflows no more frequently than once per second. 32 bits is sufficient for a 4 GHz clock. The remaining unimplemented bits must be zero whenever read and ignored on write. Equality is checked only against bits that are implemented in both the clock cycle and clock watchdog registers.

The clock watchdog register is both readable and writable though in normal operation it is usually and periodically written with a sufficiently large value that the register does not equal the value in the clock cycle register before the next time it is written.

The Clock registers appear at three different locations for which three registers of the Clock are mapped. The Clock Cycle counter is register 0 the Clock Event is register 2 and ClockWatchdog is register 3. The physical address of a Clock Register f byte b is 

Each processor includes two counters that can tally processor related events or operations. The values of the tally counter registers are incremented on each processor clock cycle in which specified events or operations occur. The tally counter registers do not signal events.

It is required that a sufficient number of bits be implemented so that the tally counter registers overflow no more frequently than once per second. 32 bits is sufficient for a 4 GHz clock. The remaining unimplemented bits must be zero whenever read and ignored on write.

For testing purposes each of the tally counter registers are both readable and writable though in normal operation each should be written only at system initialization time there is no mechanism provided for adjusting the value in the event counter registers without the possibility of losing counts.

The Tally Counter registers appear at two different locations for which the two registers are mapped. The physical address of a Tally Counter register f byte b is 

The Tally Control registers appear at two different locations for which the two registers are mapped. The physical address of a Tally Control register f byte b is 

The Zeus processor includes a register that effectively contains the current thread number that reads the register. In this way threads running identical code can discover their own identity.

It is required that a sufficient number of bits be implemented so that each thread receives a distinct value. Values must be consecutive unsigned and include a zero value. The remaining unimplemented bits must be zero whenever read. Writes to this register are ignored.

In one embodiment of the invention all processor memory and interface resources directly accessible to high level language programs. In one embodiment memory is byte addressed using either little endian or big endian byte ordering. In one embodiment for consistency with the bit ordering and for compatibility with x86 processors little endian byte ordering is used when an ordering must be selected. In one embodiment load and store instructions are available for both little endian and big endian byte ordering. In one embodiment interface resources are accessible as memory mapped registers. In one embodiment system state is memory mapped so that it can be manipulated by compiled code.

In one embodiment instructions are specified to assemblers and other code tools in the syntax of an instruction mnemonic operation code then optionally white space followed by a list of operands. In one embodiment instruction mnemonics listed in this specification are in upper case capital letters assemblers accept either upper case or lower case letters in the instruction mnemonics. In this specification instruction mnemonics contain periods . to separate elements to make them easier to understand assemblers ignore periods within instruction mnemonics.

In D B B B B B B E H B F B B B B F L A F B H B A B B B B B and B B the format of instructions to be presented to an assembler is illustrated. Following the assembler format the format for inclusion of instructions into high level compiled languages is 30 indicated. Finally the detailed structure of the instruction fields including pseudo code used to connect the assembler and compiled formats to the instruction fields is shown. Further detailed explanation of the formats and instruction decoding is provided in the section titled Instruction Set. 

In one embodiment an instruction is specifically defined as a four byte structure with the little endian ordering. In one embodiment instructions must be aligned on four byte boundaries. In one embodiment basic floating point operations supported in hardware are floating point add subtract multiply divide square root and conversions among floating point formats and between floating point and binary integer formats. Software libraries provide other operations required by the ANSI IEEE floating point standard.

In one embodiment software conventions are employed at software module boundaries in order to permit the combination of separately compiled code and to provide standard interfaces between application library and system software. In one embodiment register usage and procedure call conventions may be modified simplified or optimized when a single compilation encloses procedures within a compilation unit so that the procedures have no external interfaces. For example internal procedures may permit a greater number of register passed parameters or have registers allocated to avoid the need to save registers at procedure boundaries or may use a single stack or data pointer allocation to suffice for more than one level of procedure call.

In one embodiment at a procedure call boundary registers are saved either by the caller or callee procedure which provides a mechanism for leaf procedures to avoid needing to save registers. Compilers may choose to allocate variables into caller or callee saved registers depending on how their lifetimes overlap with procedure calls.

In one embodiment procedure parameters are normally allocated in registers starting from register 2 up to register 9. These registers hold up to 8 parameters which may each be of any size from one byte to sixteen bytes hexlet including floating point and small structure parameters. Additional parameters are passed in memory allocated on the stack. For C procedures which use varargs.h or stdarg.h and pass parameters to further procedures the compilers must leave room in the stack memory allocation to save registers 2 through 9 into memory contiguously with the additional stack memory parameters so that procedures such as doprnt can refer to the parameters as an array. Procedure return values are also allocated in registers starting from register 2 up to register 9. Larger values are passed in memory allocated on the stack.

In one embodiment instruction scheduling is performed by a compiler. In the manner of software pipelineing instructions should generally be scheduled so that previous operations can be completed at the time of issue. When this is not possible the processor inserts sufficient empty cycles to perform the instructions precisely explicit no operation instructions are not required.

Having fully described various embodiments of the invention those skilled in the art will recognize given the teachings herein that numerous alternatives and equivalents exist which do not depart from the invention. It is therefore intended that the invention not be limited by the foregoing description but only by the appended claims.

