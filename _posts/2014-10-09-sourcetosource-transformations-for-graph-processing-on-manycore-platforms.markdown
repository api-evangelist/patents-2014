---

title: Source-to-source transformations for graph processing on many-core platforms
abstract: Methods are provided for source-to-source transformations for graph processing on many-core platforms. A method includes receiving a graph application including one graph, expressed by a graph application programming interface configured for defining and manipulating graphs. The method further includes transforming, by a source-to-source compiler, the graph application into a plurality of parallel code variants. Each of the plurality of parallel code variants is specifically configured for parallel execution by a target one of a plurality of different many-core processors. The method also includes selecting and tuning, by a runtime component, a particular one of the parallel code variants for the parallel execution responsive to graph application characteristics, graph data, and an underlying code execution platform of the plurality of different many-core processors.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09335981&OS=09335981&RS=09335981
owner: NEC Corporation
number: 09335981
owner_city: 
owner_country: JP
publication_date: 20141009
---
This application claims priority to provisional application Ser. No. 61 892 497 filed on Oct. 18 2013 and to provisional application Ser. No. 61 929 521 filed on Jan. 21 2014 incorporated herein by reference.

The present invention relates to data processing and more particularly to source to source transformations for graph processing on many core platforms.

Many applications use graphs to represent and analyze data but the effective deployment of graph algorithms on many core processors is still a challenge task. Although there are good compilation and runtime frameworks for parallelizing graph applications on multi core CPUs such frameworks do not exist for many core devices. There is a need for efficient source to source compilers that automatically compile and parallelize graph applications on many core processors because a many core devices offer higher peak performance than multi core devices and b many core programming is still a highly specialized and error prone skill.

These and other drawbacks and disadvantages of the prior art are addressed by the present principles which are directed to source to source transformations for graph processing on many core platforms.

According to an aspect of the present principles a method is provided. The method includes receiving a graph application including one graph expressed by a graph application programming interface configured for defining and manipulating graphs. The method further includes transforming by a source to source compiler the graph application into a plurality of parallel code variants. Each of the plurality of parallel code variants is specifically configured for parallel execution by a target one of a plurality of different many core processors. The method also includes selecting and tuning by a runtime component a particular one of the parallel code variants for the parallel execution responsive to graph application characteristics graph data and an underlying code execution platform of the plurality of different many core processors.

According to another aspect of the present principles a method is provided. The method includes performing using a compiling processor source to source compiling on a graph application that includes at least one graph. The source to source compiling step includes transforming the graph application and related container data structures into platform specific container data structures using parallel code transformation responsive to parallel iterators and using parallel blocks of code for primitives. The source to source compiling step further includes managing execution synchronizations for the graph the platform specific container data structures and the iterators. The source to source compiling step also includes converting platform independent synchronization primitives into platform specific synchronization primitives.

According to yet another aspect of the present principles a method is provided. The method includes configuring a graph processing run time library with a selection processor configured to select a particular parallel code variant from among a plurality of received parallel code variants of a graph application including at least one graph for parallel execution by a target many core coprocessor responsive to graph application characteristics graph data and an underlying code execution platform of the target many core processor. The method further includes configuring the run time library with dynamic memory allocation management for an execution of the particular parallel code variant the graph application.

These and other features and advantages will become apparent from the following detailed description of illustrative embodiments thereof which is to be read in connection with the accompanying drawings.

The present principles are directed to source to source transformations for graph processing on many core platforms. Advantageously the present principles are suitable for use with graph applications. However it is to be appreciated that the present principles can be used with other types of applications while maintaining the spirit of the present principles.

The present principles provide a new source to source compiler that automatically generates parallel code for different many core platforms e.g. including but not limited to GPUs and the Intel Xeon Phi starting from a single platform agnostic graph programming Application Programming Interface API .

The present principles advantageously automate the development of high performance graph applications on many core platforms using the source to source compiler of the present principles.

In an embodiment the source to source compiler is processor based. Of course other elements of can be processor based while maintaining the spirit of the present principles.

The source to source compiler includes an internal graph data structure transformer an internal collections implementator a set of parallel basic blocks a set of platform specific synchronization mechanisms transformer a Compute Unified Device Architecture CUDA code writer and an OpenMP code writer .

The internal collections implementator includes containers. The containers include for example a set container A a 31 multi set container B and a queue container C. Of course other containers can also be used.

The set of parallel basic blocks include primitives. The primitives include a BFS iterator A a reduction primitive B and a scan primitive C.

The platform specific synchronization mechanisms transformer includes a global local barrier A and a flat hierarchical atomizer .

The source to source compiler outputs variants variants and variants corresponding to the system being used with a multi core CPU an INTEL XEON PHI processor and or an NVIDIA Graphics Processing Unit GPU respectively.

In an embodiment an application developer writes the graph application using a programming interface that includes a high level graph programming API and a set of platform agnostic sequential and parallel constructs that allow the user to define generic graph applications. The graph programming API is implemented and executed by our new runtime library .

Then the application developer uses the source to source compiler to generate an efficient highly parallelized implementation of the graph application which can run on different many core processors like the Intel Xeon Phi or a GPU.

The source to source compiler generates different code variants for multi core CPUs Intel Xeon Phi coprocessors and NVIDIA GPUs. These code variants may differ in several aspects including for example from the type of parallelization performed to the implementation of the underlying data structures to the handling of nested parallelism and more. The generated code is written in OpenMP and CUDA and in an embodiment it uses the offload execution model on the Intel Phi. During code generation the graph and the containers sets A multi sets B and queues C are transformed into internal platform specific data structures by the platform specific synchronization mechanisms transformer . In addition existing parallel basic blocks are used for common primitives such as reduction A sort B and scan C. Parallelization is enabled by the presence of parallel iterators which can be explicitly inserted in the code by the programmer. The source to source compiler automatically handles synchronizations associated with the graph the iterators and the containers. Synchronizations associated with custom data structures can be explicitly indicated by the programmer using high level platform independent synchronization primitives which are transformed into platform specific synchronization mechanisms by the platform specific synchronization mechanisms transformer .

Finally the runtime system supports two important functions i selecting by the variant selector and tuner A the most suitable code variant depending on the characteristics of the application the dataset and the underlying platform and ii supporting by the dynamic memory handler B dynamic memory allocation through the offset address.

In an embodiment the variant selector and tuner A includes a selection processor for implementing the selection and tuning. In an embodiment the selection processor can also be used to execute a selected code variant for a graph application including at least one graph. Tuning can be performed on a selected code variant to avoid execution errors and to optimize parallel execution of at least portions of the selected code variant.

At step receive a graph application that includes at least one graph expressed by a graph programming application programming interface API specifically configured for defining and manipulating graphs. The expression of the graph application can include node information edge information root information weight information and so forth. The expression of the graph application received at step can further include for example but is not limited to primitives. The primitives can include but are not limited to dynamic memory management primitives parallel primitives synchronization primitives and runtime primitives.

Further regarding step as well as API the API includes methods to define and manipulate application specific attributes container data structures parallel code iterators dynamic memory management primitives parallel primitives synchronization primitives and runtime primitives.

At step transform the graph data into a source to source compiler to generate parallel code for different many core processors.

At step A determine internal graph container data structures e.g. ordered set unordered set multi set queue etc. . These internal graph container data structures are typically platform independent.

At step B transform the internal graph container data structures into internal platform specific container data structures by the platform specific synchronization mechanisms transformer using parallel code transformation performed by parallel iterators and using parallel blocks of code for primitives.

At step C transform platform independent synchronization primitives into platform specific synchronization primitives by the platform specific synchronization mechanisms transformer .

At step D generate manage synchronizations associated with the graph the containers and the iterators.

At step invoke the run time library to perform code variant selection and tuning responsive to graph characteristics graph data and an underlying code execution platform.

A description will now be given regarding some of the benefits advantages of the present principles over the prior art.

The graph programming API has many primitives that specifically help in automatically generating parallelized code for a variety of different many core platforms.

The source to source compiler has many new transformations to generate efficient parallelized code by recognizing parallelizing opportunities exposed by the use of the graph programming API by the application developer to write the graph application.

The design of the run time library is specific to each many core platform and one key strength of the run time library is that it can dynamically select and tune the code variant that better fits the characteristics of the target dataset and the hardware profile as well as enable dynamic memory allocation.

A description will now be given of some of the many attendant competitive competitive values of the present principles.

The present principles offer at least the following two values a our source to source compiler generates parallelized code for graph applications so that they execute as fast as manually optimized code for many core processors and b the time required to develop good parallel versions of the code that can execute on many core processors is reduced by 10 to 100 and our procedure is completely automatic.

Embodiments described herein may be entirely hardware entirely software or including both hardware and software elements. In a preferred embodiment the present invention is implemented in software which includes but is not limited to firmware resident software microcode etc.

Embodiments may include a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. A computer usable or computer readable medium may include any apparatus that stores communicates propagates or transports the program for use by or in connection with the instruction execution system apparatus or device. The medium can be magnetic optical electronic electromagnetic infrared or semiconductor system or apparatus or device or a propagation medium. The medium may include a computer readable medium such as a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk etc.

It is to be appreciated that the use of any of the following and or and at least one of for example in the cases of A B A and or B and at least one of A and B is intended to encompass the selection of the first listed option A only or the selection of the second listed option B only or the selection of both options A and B . As a further example in the cases of A B and or C and at least one of A B and C such phrasing is intended to encompass the selection of the first listed option A only or the selection of the second listed option B only or the selection of the third listed option C only or the selection of the first and the second listed options A and B only or the selection of the first and third listed options A and C only or the selection of the second and third listed options B and C only or the selection of all three options A and B and C . This may be extended as readily apparent by one of ordinary skill in this and related arts for as many items listed.

The foregoing is to be understood as being in every respect illustrative and exemplary but not restrictive and the scope of the invention disclosed herein is not to be determined from the Detailed Description but rather from the claims as interpreted according to the full breadth permitted by the patent laws. Additional information is provided in an appendix to the application entitled Additional Information . It is to be understood that the embodiments shown and described herein are only illustrative of the principles of the present invention and that those skilled in the art may implement various modifications without departing from the scope and spirit of the invention. Those skilled in the art could implement various other feature combinations without departing from the scope and spirit of the invention.

