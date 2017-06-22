---

title: Integrated circuit test-port architecture and method and apparatus of test-port generation
abstract: A method and apparatus are provided for generating RTL code for a test-port interface of an integrated circuit. In an embodiment, a test-port table is provided as input data. A computer automatically parses the test-port table into data structures and analyzes it to determine input, output, local, and output-enable port names. The computer generates address-detect and test-enable logic constructed from combinational functions. The computer generates one-hot multiplexer logic for at least some of the output ports. The one-hot multiplexer logic for each port is generated so as to enable the port to toggle between data signals and test signals. The computer then completes the generation of the RTL code.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09311444&OS=09311444&RS=09311444
owner: Sandia Corporation
number: 09311444
owner_city: Albuquerque
owner_country: US
publication_date: 20140710
---
This invention was made with Government support under contract no. DE AC04 94AL85000 awarded by the U.S. Department of Energy to Sandia Corporation. The Government has certain rights in the invention.

The present invention relates to Design for Test DFT integrated circuits ICs and to methods and apparatus for the digital design of DFT circuits.

After the user functional specification has been created for an integrated circuit the circuit designer must next transform the user specification into a register transfer level RTL description that specifies the logical design of the IC. More specifically the RTL declares the registers that synchronize the operation of the IC to the clock cycle and it specifies the combinational logic that performs the logical functions of the IC. In addition to describing the desired behavior of logical circuits the RTL specifies the interconnections to inputs and outputs.

In the physical design stage a logic synthesis tool is typically used to convert the RTL to a gate level description of the IC. More specifically the synthesis software operating on the RTL description generates a logically equivalent description referred to as a netlist .

The netlist consists of elementary logic primitives drawn from whatever set of such primitives is available in the pertinent physical integrated circuit technology. Many of the elementary logic primitives may be provided by manufacturers as cells belonging to a proprietary cell library.

A typical netlist includes a definition for each occurrence of such an elementary logic primitive. The definition lists the ports or pins that are the connection points to the primitive and it may also define certain properties of the primitive. The netlist also lists the wires referred to as nets that interconnect the primitives and other elements of the IC. The netlist associates the nets by name to the ports to which they are connected.

Application specific integrated circuits ASICS are a class of ICs that have rapidly growing commercial importance. An ASIC is an IC whose design is customized for a particular use. As the demand for ASICs has grown so has their complexity. Indeed a contemporary ASIC may have as many as 100 million gates or more.

Not surprisingly manufacturers of ASICs must perform post fabrication testing to screen out parts with manufacturing defects. For effective testing it is necessary to gain access to internal blocks within the circuit under test CUT . Absent special provisions it would be impractical to attempt such access from the primary input output I O pins of the CUT.

Designers have therefore made a special provision for test access referred to as a test port. The test port is a combination of logic and I O pins. A body of techniques referred to as Design for Test DFT has evolved for incorporating test port logic and test port I O into ASIC designs among others. DFT features are typically included in the RTL description of the ASIC.

Standardized test ports e.g. JTAG1 compatible test ports are generally available for implementation in commodity IC devices. However it is more typical to implement proprietary test port interfaces in custom ASICs. In addition custom ASICs intended for high reliability applications often have more stringent test port usage requirements than those that are typically implemented in commercial test port IP blocks. Hence these devices in particular will generally implement custom or proprietary test port interfaces.

The development and implementation of custom or proprietary test port interfaces has associated costs that could be very high. Because the test port is likely to be highly unique to a particular ASIC design it will often be necessary to manually develop the hardware source code using an RTL language such as Verilog or VHDL. The effort can be complex not least because it will in many cases require the multiplexing of hundreds of signals from the logic core.

Moreover there is often a demand to update the source code late in the ASIC design cycle as the core design is finalized.

These factors drive up costs for various reasons. For example efforts must be duplicated because the manually developed test port interfaces are not re usable across ASIC designs. Moreover the test port interfaces are prone to logic bugs and the test port interfaces are resource intensive to generate and validate. Hence there is a need for a more economical approach for developing and implementing ASIC test port interfaces.

We have developed such an approach. More specifically we have developed a new architecture for a test port interface and we have developed an automated method for generating the test port RTL code from a table specification also referred to as a spreadsheet specification . The new test port architecture has special features that facilitate the automated code generation.

Accordingly the invention in a first aspect relates to a method for generating RTL code for a test port interface of an integrated circuit. In an embodiment a test port table is provided as input data. A computer or other digital data processing machine acting under a stored set of instructions hereinafter the computer automatically parses the test port table into data structures and analyzes it to determine input output local and output enable port names.

The computer then generates address detect and test enable logic constructed from combinational functions. Combinational functions also referred to as static functions are state free. This distinguishes them from sequential logic circuits whose output depends not only on the current input but on the past history of inputs. 

The computer then generates one hot multiplexer logic for at least some of the output ports. A one hot multiplexer allows only one input at a time. The one hot multiplexer logic for each port is generated so as to enable the port to toggle between data signals and test signals.

The sequence of steps as listed above is typical but not exclusive. For example the step of generating address detect and test enable logic could in other implementations be performed in parallel with the step of generating one hot multiplexer logic.

In another aspect the invention relates to a non transitory machine readable medium in which instructions are stored for a computer or other digital data processing machine to perform the method as described above.

In another aspect the invention relates to a computer or other digital data processing machine that has been configured to perform the method as described above. The configuration of the machine for that purpose may be by dedicated circuitry or by a stored software program or by a combination of both.

In yet another aspect the invention relates to an integrated circuit that embodies a test port interface. The test port interface includes a logical circuit and a plurality of I O pins.

The logical circuit is configured to implement a plurality of distinct test mode blocks. A test mode block is a logical functionality for configuring and re mapping core stimulus signals and core observation signals according to the various functions that are to be performed with input and output via the test port pins. The test mode blocks are implemented in physical circuitry in the test port interface.

The test mode blocks are multiplexed so as to share a group of bidirectional test port pins for input and for output. For output the outputs of the respective test mode blocks are merged in a one hot multiplexer which enables the output from only one test mode block at a time.

A subset of the test port pins are configured as address pins. When they are suitably energized the address pins control which test mode block is enabled. The logical circuit is configured such that only one test mode block can be enabled at a time. Each test mode block includes an address detect and test enable circuit that reads the address pins and in response conditionally enables its test mode block i.e. enables the block when it reads an appropriate address.

Each test mode block is configured to monitor a specifiable number of core observation signals and to drive a specifiable number of core stimulus signals.

Each test mode block is configured to read and to drive each of the bidirectional test port pins and to remap the bidirectional test port pins among the I O types input output tristate and bidirectional. As will be known to those skilled in the art a tristate pad is a pad that can drive a low voltage logic 0 a high voltage logic 1 or no voltage floating output .

Table 1 is an example of a table generated RTL file for a test port written in the Verilog language. As noted above this RTL file was generated from the table of .

Table 2 is an example of an ASIC pad table. The pad table is used by the RTL code generator i.e. the RTL compiler to analyze the top level pin requirements for the ASIC and from that to create the RTL file that contains instantiations of the core block and the test port block.

In our new test port architecture a plurality of ASIC test functions share a limited number of bidirectional I O input output test pin resources. In implementations our architecture is efficient has low overhead is scalable for small and large ASIC designs and can support an arbitrary number of test signals and test modes.

As will be explained in more detail below the high level test port specification for implementations of our architecture can be concisely defined in a table also referred to herein as a spreadsheet . A compiler is provided that automatically generates the test port RTL code from the table. Among other things the RTL code logically defines all of the wires and ports that are needed to implement the test port. Moreover the generated RTL code is synthesizable to combinational i.e. static logic hence the use of sequential i.e. state based logic can be avoided as is desirable e.g. for high reliability systems.

In the specification table a subset of the test port pins is defined as the set of address pins. The set of signal values on the respective address pins specifies which Test Mode block is to be enabled at each given time.

During testing only one Test Mode block is enabled at any given time. The address detect and test enable logic contained within each Test Mode block reads the test port pins and responds by enabling that Test Mode block if it is the one that has been designated. This property allows efficient one hot multiplexers implemented with an N input OR gate to be used to merge the outputs of all the Test Mode blocks.

Core observation signals among other are wiring signals that go from the ASIC core to the test port. Core stimulus signals among others are wiring signals that go from the test port to the ASIC core. In accordance with definitions provided in the specification table each Test Mode block can monitor an arbitrary number of core observation signals and can drive an arbitrary number of core stimulus signals.

Likewise each Test Mode block has access to each bidirectional test port pin and can re map the test port pins as input output tristate or bidirectional I O types in accordance with definitions provided in the specification table.

As shown in the figure test port inputs are broadcast from bidirectional I O pad to the test mode blocks. Test port outputs travel from the respective test mode blocks to the multiplexer arrangement from which they travel when enabled through pad to the designated pins .

With further reference to it will be seen that the left most vertical column is labeled with the header Address and the vertical column immediately to its right i.e. the second column is labeled with the header Test Mode . The entries in these columns are for the convenience of human readers and are not read by the compiler i.e. by the RTL generation apparatus.

The next five columns i.e. the columns under the header Test Port Pads list the respective values on the five in this example test port pins which as seen in the header row are respectively indexed tp00 tp01 tp02 tp03 and tp04. It will be seen that each row of the table following the header rows corresponds to one of three test modes which are respectively System Mode ATPG Test Mode and Memory Test Mode. The set of five test port pins takes on a respective 5 tuple of values for each of the three test modes. These values are discussed below. A value of x in the Test Port Pads columns signifies don t care .

The last six columns of the table i.e. the columns under the header Internal Signals to chip core define the values of internal signals that go from the test port to the ASIC core. As seen in the table each of the signals is defined with the o name syntax. This indicates that they are all stimulus signals. In more general cases some of the internal signals which would be defined with the l name syntax are local wires rather than stimulus signals.

The possible internal signal values are 1 0 and x. A value of x in the Internal Signals columns signifies that the pertinent signal will take the value defined by one of the test port pads. For example x is listed as the internal signal value at address 0 1 internal signal o osc en. This signifies that the osc en stimulus signal will take the value driven on the tp01 test port pad because it has i osc en defined for the relevant test mode.

The respective internal signals identified in the header row are Scan Mode Built In Self Test BIST Mode Scan Test Enable Scan Test Input Oscillator Enable and PSM Enable . Output variables used in only one place in the spreadsheet are implicitly inferred and need not be explicitly declared in the header row. It will be seen that the set of six internal signal ports takes on a respective 6 tuple of values for each of the three test modes. These values are discussed below.

Observation signals which as noted are among the wiring signals that go from the ASIC core to the test port do not need to be declared. They are implicitly inferred from their usage in the spreadsheet. However local wires inside of the test port such as output enable control signals for the test port pins that are controlled by other test port pin inputs should be declared in the header row with e.g. a l name syntax.

Accordingly it will be seen that in the example of the address pins are test port pins 04 and 03 which respectively take the values 0 x in System Mode 1 0 in ATPG Test Mode and 1 1 in Memory Test Mode.

 ATPG stands for Automatic Test Pattern Generation. ATPG Test Mode enables the internal logic scan chains and allows the design to be tested with ATPG vectors.

Memory Test Mode enables the internal memory scan chains and allows the internal memories to be tested.

In System Mode test port pins 02 01 and 00 respectively carry the clock monitor output signal the oscillator enable input signal and the Power Supply Monitor PSM enable input signal. In ATPG Test Mode they respectively carry the oscillator output signal the scan chain input signal and the scan chain enable input signal. In Memory Test Mode they respectively carry the internal i.e. to or from the chip core scan test output input and enable signals.

As noted above the respective internal signals identified in the example of are Scan Mode Built In Self Test BIST Mode Scan Test Enable Oscillator Enable and PSM Enable . In System Mode the first four of these take the value 0 and the last two are don t care . In ATPG Test Mode the Scan Mode signal takes the value 1 and the rest are 0. In Memory Test Mode the Built In Self Test Mode signal takes the value 1 the Scan Test Enable and Scan Test Input signals are don t care and the rest take the value 0.

The algorithm described above for generating the test port RTL file can be implemented as one of two linked phases for specifying the entire ASIC by generating an RTL file that contains instantiations of both the core block and the test port block. Seen in the lower portion of is an algorithm for generating the ASIC top level RTL file that specifies the ASIC of .

ASIC pad table provides input to the algorithm that generates the top level RTL file. According to that algorithm the pad table is parsed the ASIC s top level pin requirements are analyzed and the resulting RTL file containing instantiations of the core block and the test port block is written out .

As indicated by the arrow drawn in the figure from block to block data flows from the test port algorithm i.e. the upper branch of the figure to the top level algorithm i.e. the lower branch of the figure . Specifically test port pin names core stimulus signal names and core observation signal names are passed from the upper branch to the lower branch. This information is used by the lower branch to hook up the internal signals and wires that go between the core and the test port block.

As those skilled in the art will understand algorithms for performing the sequence of steps represented in the lower portion of i.e. the analysis of the ASIC Pad Table and the generation from it of top level core RTL without the test port description are available for conventional use.

With reference to the figure it will be seen that dedicated test port tp bidirectional pins are used to configure the ASIC into the various test modes. The test modes represented in the figure include logic scan chain testing Logic Scan mode memory scan chain testing Memory Scan mode and analog block testing not shown in the figure .

Logic Scan mode uses the scan enable se and scan input si stimulus signals to apply test patterns to the core from the test port pins and it uses the scan output so observation signal to observe test results. Memory Scan mode uses the scan enable scanTestEn and scan input scanTestIn stimulus signals to apply memory test patterns to the core from the test ports pins and it uses the scan out scanTestOut observation signal to observe test results.

The scanMode signal represented symbolically in the figure configures the ASIC into Logic Scan mode. The bistMode signal configures the ASIC into Memory Scan mode. The burnMode signal configures the ASIC pads into Burn in test mode in which the ASIC is exposed to elevated temperature and voltage to screen for infant mortality manufacturing defects. The iddqMode signal configures the ASIC pads into Quiescent IDD test mode in which the ASIC is checked for elevated power consumption due to manufacturing defects. The bypassClockMode signal disables internally generated clock sources inside of the ASIC and instead uses more accurate externally generated clock sources to test the ASIC. The various test modes listed here are well known to those skilled in the art.

Other test modes include the User Test modes that use the user in stimulus signals to apply test patterns to the core from the test port pins and the user out and user oe observation signals to observe test results. The user out observation signals can also be used to passively monitor internal states during normal non test ASIC operation. The User Test mode offers substantial advantages in the context of the flexible test port architecture described here because an arbitrary number of number of user defined test modes can be defined in the table specification to adapt to the complexity of any ASIC.

The test port pins are also used to apply stimulus signals which will be directed from the test port to the ASIC core. As noted above user out signals on the test port pins bring out internal states of the core for observation.

Although a typical ASIC design requires fifteen to thirty test port pins approximately 75 of these pins may be recovered for general use by multiplexing them with easy to test functions such as analog block enables power supply monitor outputs clock and reset monitor outputs or analog trim settings.

As noted above Table 1 is an example of an RTL file for a test port generated from the table of . The compiler reads the lines of the table and processes them to generate an RTL output file. The RTL output file assigns logical equations to the respective pins. In the synthesis stage of ASIC design these logical equations will be realized as logic gates.

All of the information needed to generate the logical equations is provided in the specification table. The coding of a suitable compiler is a straightforward problem in computer programming that is soluble by conventional techniques and need not be described here in detail. By way of example a compiler can be written in Perl or C and be implemented as a standalone program independent of the specification table. Alternatively VisualBASIC or JAVA can be used to more elegantly integrate the compiler directly into the spreadsheet program used to create the specification table.

In Table 1 rows of the spreadsheet are referenced by the syntax row number i.e. 0 1 or 2 . The logical operations referred to in the figure include the following 

 OR Verilog e.g. defines this as a bitwise OR treating the operands as binary bits wherein all of the binary bits in the operands are OR ed together .

As noted above Table 2 provides an example of an ASIC pad table. The cell types referred to in the table which are named arbitrarily refer to entries in a cell library. As those skilled in the art will understand the cells collected in a cell library are implementations of logic functions. The logic functions are provided in representations that are usable by automated ASIC design tools for synthesis placement and routing.

