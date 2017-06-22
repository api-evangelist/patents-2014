---

title: Methods and systems for producing, evaluating and simulating executable applications
abstract: A method and system for producing executable applications comprises selecting a processor type and compiling a binary code module for execution by the selected processor type. The method and system further comprise selecting one or more operating systems and linking the binary code module with a loader module for each selected operating system to produce an executable application to be executed on that operating system. Methods and systems for evaluating and simulating executable applications are also disclosed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09372680&OS=09372680&RS=09372680
owner: Marmalade Technologies Limited, a United Kingdom Private Limited Company
number: 09372680
owner_city: London
owner_country: GB
publication_date: 20140305
---
This application is a Continuation application of PCT International Application Number PCT EP2012 067346 titled METHODS AND SYSTEMS FOR PRODUCING EVALUATING AND SIMULATING EXECUTABLE APPLICATIONS filed Sep. 5 2012 and claims priority to foreign patent applications GB1115501.7 titled A METHOD AND SYSTEM FOR PRODUCING EXECUTABLE APPLICATIONS filed Sep. 8 2011 GB1117001.6 titled A METHOD AND SYSTEM FOR EVALUATING EXECUTABLE APPLICATIONS filed Oct. 3 2011 and GB1119103.8 titled A METHOD AND ARRANGEMENT FOR SIMULATING EXECUTION OF AN EXECUTABLE APPLICATION filed Nov. 4 2011 all incorporated by reference herein in their entirety.

The present invention relates to a method and system for producing executable applications and more particularly relates to a method and system for producing executable applications to be executed on different devices running different operating systems.

The present invention also relates to a method and system for evaluating executable applications and more particularly relates to a method and system for evaluating executable applications produced for different devices on a host system.

The present invention also relates to a method and arrangement for simulating execution of an executable application and more particularly relates to a method and arrangement for simulating execution of an executable application using a host system and a target device.

Many application developers require their applications or apps to run across multiple operating systems. Each operating system provider typically provides a Software Development Kit SDK allowing applications to be developed only for the provider s specific operating system. Developers have two options 

Option 1 Develop for each target operating system OS using each respective OS specific SDK. The problem with this option is that is can be expensive and time consuming each OS specific SDK environment requires domain knowledge the SDK environments mandate different programming languages C C Objective C Java etc. each implementation must be separately tested etc.

Option 2 Develop for multiple target OSs simultaneously by using a cross platform SDK. A cross platform approach allows developers to maintain a single body of source code whilst still being able to compile and deploy to multiple target OS platforms. Cross platform SDKs are generally provided by Independent Software Vendors ISVs rather than the OS providers. The number of ISVs providing Option 2 is increasing because Option 1 is becoming more expensive and time consuming.

Each cross platform SDK presents the developer with an abstracted Application Programming Interface API set the OS abstraction API allowing a single application source code to target multiple OS environments. The application source code is usually prevented from referencing OS specific APIs the application s only interaction with the OS must be through the abstracted APIs.

Variation A Virtual Machine VM . Source code is authored in a language such as JavaScript Java or C . The source code is compiled to a bytecode instruction set for delivery to a target device. The bytecode is not machine code native to any specific CPU.

The target device contains a runtime interpreter for the bytecode this interpreter may itself be bundled and delivered with the app or it may already be resident on the target device . This interpreter is known as a Virtual Machine VM . Typically the SDK provider will provide a separate version of the VM for each target OS.

When the application is executed the bytecode is interpreted by the VM and converted into machine code native to the CPU of the device. This conversion process can happen on the fly every time each bytecode instruction is interpreted or Just In Time JIT by interpreting a block of instructions converting to machine code and caching the resulting code in memory so that it does not need to be converted again within the same execution of the application or Ahead Of Time AOT by applying the JIT process to the entire bytecode as soon as the application is launched this is the most time consuming and memory intensive approach .

The Variation A approach requires only one compilation of the source code to the VM bytecode and everything else is handled at application execution time by the VM. Examples include J2ME from Oracle Flash from Adobe and .NET or the Common Language Runtime from Microsoft .

Variation A provides the purest form of binary portability but at the expense of runtime performance. Interpreted code is slower than pre compiled code and yet conducting the code compilation process on the target device either JIT or AOT itself impacts performance.

Variation B Transcoding or Code Morphing. Source code can be authored in a variety of languages. Standard compilers such as the CodeSourcery GCC compiler are comprised of stages. Typically one stage the front end compiles the source code into an intermediary binary code another stage the back end then compiles the intermediary binary code into executable code for the target application execution environment which might be machine code native to a specific CPU or might be a bytecode for a VM.

The Code Morphing approach typically extracts the intermediary binary code from the first stage of the compilation process and then decompiles this binary code into a source code target native to an OS specific SDK. For example the source code might be authored in Java the GCC compiler front end would convert this into intermediary binary code the cross platform SDK might then extract the binary code and decompile it into Objective C in a manner suitable for recompilation within the Apple iPhone SDK. The cross platform SDK would support decompilation into multiple OS specific source codes and the developer would then be responsible for compiling these within multiple OS specific SDKs in order to generate native applications for all of the desired targets.

This approach requires multiple separate compilations of the automatically generated OS specific source code and therefore requires the developer to install multiple OS specific SDKs. Examples include MoSync from Mobile Sourcery and Metismo from Software AG .

Variation B does not require any on device code interpretation but the process of decompiling the intermediary compiler binary code and recompiling within the OS specific SDK results in code which is far from optimally performant. Furthermore the auto generation of OS specific source code from the developer s original source code makes source code management more complex there is a temptation for the developer to modify the auto generated source code and these modifications can be lost if the auto generation process is repeated. Finally this approach requires the auto generated code to be compiled separately within each OS specific SDK environment. The resultant versions of the application are very different in terms of CPU machine code and therefore the likelihood of OS specific bugs is increased.

Variation C Source Code Compatibility. This is in some ways the simplest approach. The cross platform SDK presents the developer with a set of programming interfaces that have been implemented separately within each OS specific SDK. The developer can then simply compile their application source code combined with the cross platform SDK implementation within the OS specific SDK environment in order to generate an application for the target OS. This approach requires multiple separate compilations of the application source code and therefore requires the developer to install multiple OS specific SDKs. However the main flaw of this approach is that the developer source code can only be compiled within OS specific SDKs that accept that source code language choice. For example source code authored in Java could be compiled within Google s Android SDK but not within Apple s iPhone SDK. Examples include Qt from Nokia many developers also create their own in house solutions using this approach.

Variation C is the best in terms of compiled code performance as the code compiler provided by each OS specific SDK can be utilised as intended with all compiler optimisations applied. However the source code still needs to be compiled separately within each OS specific SDK environment and resultant versions of the application are very different in terms of CPU machine code with the likelihood of OS specific bugs being increased. The major downside is that the number of supportable OS platforms is highly restricted as the developer must make a single choice of source code language yet currently many of the most popular target OS platforms have OS specific SDKs that mandate a single and differing source code language choice.

There is a need for a new approach to cross platform application development that achieves an optimal balance of binary code portability with high runtime performance.

The present invention seeks to provide an improved method and system for evaluating executable applications.

A common convenient method of evaluating applications is to run a version of the application on the host development system. Given the configuration of the host development system this evaluation may be within a processor architecture and operating system that differs from all or most of the target devices. Such an evaluation can be termed a simulation . Furthermore the hardware form factor of the host development system is likely to differ considerably from that of all or most of the target devices for example the host development system may receive inputs from a mouse and alphanumeric keyboard whilst the target devices might receive inputs from a touchscreen and a small number of specific buttons.

The present invention seeks to provide an improved method and arrangement for simulating execution of an executable application.

According to one aspect of the present invention there is provided a method of producing an executable application the method comprising selecting a processor type generating a code module comprising instructions which are executable by the selected processor type selecting an operating system providing a loader module for execution by the selected operating system and packaging the loader module with the code module to form an executable application so that when the executable application is provided on a device incorporating a processor of the selected processor type and running the selected operating system the device can execute the executable application to execute the loader module to load the code module for execution by the processor.

According to another aspect of the present invention there is provided a method of producing executable applications comprising selecting a processor type generating a code module comprising instructions which are executable by the selected processor type selecting a first operating system providing a first loader module for execution by the selected first operating system packaging the first loader module with the code module to form a first executable application so that when the first executable application is provided on a first device incorporating a processor of the selected processor type and running the selected first operating system the first device can execute the first executable application to execute the first loader module to load the code module for execution by the processor selecting a second operating system providing a second loader module for execution by the selected second operating system and packaging the second loader module with a copy of the code module to form a second executable application so that when the second executable application is provided on a second device incorporating a processor of the selected processor type and running the selected second operating system the second device can execute the second executable application to execute the second loader module to load the copy of the code module for execution by the processor.

Conveniently the linking occurs before or at the same time as the loader module is packaged with the code module to form an executable application.

In one embodiment the linking occurs each time the or each executable application is executed on the device.

In another embodiment the linking links the code module to an operating system abstraction application programming interface provided in the loader module.

Preferably the method further comprises generating a loader module for each respective selected operating system.

Conveniently generating each loader module comprises incorporating an operating system abstraction application programming interface header.

Advantageously generating each loader module comprises incorporating generic functional code which can be executed by more than one operating system.

Preferably generating each loader module comprises incorporating functional code which is specific to a selected operating system.

Conveniently the code module is machine code and the step of generating the code module comprises compiling the machine code from source code using a compiler for a selected processor type.

Advantageously the code module incorporates a single function entry point to initiate execution of the code module.

Preferably the code module has an external dependency to an operating system abstraction application programming interface.

Advantageously generating the code module comprises using an object file linker to link a machine code object file into a binary library file in an executable and linkable format.

Preferably generating the code module further comprises modifying the executable and linkable format library file into a format suitable for linking with the loader module.

Conveniently the step of packaging comprises storing each code module with a respective loader module in a single executable application file.

Advantageously the step of packaging further comprises storing application assets in the single executable application file.

Preferably the step of packaging further comprises storing metadata in the single executable application file.

In a further embodiment at least one of the selected operating systems is a Linux based operating system.

In a still further embodiment at least one of the selected operating systems is an Android operating system.

In a yet further embodiment at least one of the selected operating systems is a MeeGo operating system.

According to a yet further aspect of the present invention there is provided a system for producing an executable application the system comprising an interface for selecting a processor type and an operating system a compiler to generate a code module comprising instructions which are executable by a processor type selected using the interface a storage module for storing a loader module configured for execution by an operating system selected using the interface and a packaging module for packaging the loader module with the code module to form an executable application so that when the executable application is provided on a device incorporating a processor of the selected processor type and running the selected operating system the device can execute the executable application to execute the loader module to load the code module for execution by the processor.

According to a still further aspect of the present invention there is provided a system for producing an executable application the system comprising an interface for selecting a processor type a first operating system and a second operating system a compiler to generate a code module comprising instructions which are executable by a processor type selected using the interface a storage module for storing a first loader module configured for execution by a first operating system selected using the interface and a second loader module configured for execution by a second operating system selected using the interface and a packaging module which is configured to package the first loader module with the code module to form a first executable application so that when the first executable application is provided on a device incorporating a processor of the selected processor type and running the selected first operating system the device can execute the first executable application to execute the first loader module to load the code module for execution by the processor wherein the packaging module is also configured to package the second loader module with a copy of the code module to form a second executable application so that when the second executable application is provided on a device incorporating a processor of the selected processor type and running the selected second operating system the device can execute the second executable application to execute the second loader module to load the code module for execution by the processor.

Preferably the system further comprises a linker module which is configured to link each code module to a respective loader module.

According to another aspect of the present invention there is provided a device comprising at least one executable application produced in accordance with the method of any one of claims to hereinafter.

According to one aspect of the present invention there is provided a method of evaluating an executable application on a host system wherein the host system incorporates a memory and a first processor type and wherein the application comprises a loader module configured to execute on the host system and a code module configured to execute on a second processor type which is different from the first processor type the method comprising executing the loader module on the host system executing an emulator module to provide an emulation environment on the host system which emulates the second processor type executing the code module within the emulation environment to generate a functional command writing the functional command into the memory of the host system and executing the functional command within the loader module.

Preferably the emulator module is executed in response to the loader module generating a functional call to the code module.

Conveniently the emulator module generates an exception signal when the functional command is written into the memory.

Advantageously the loader module executes the functional command in response to the generation of the exception signal.

Conveniently the method further comprises passing execution back to the code module in the emulation environment after the functional command has been executed within the loader module.

In another embodiment the method further comprises initially producing the application by selecting the second processor type generating the code module comprising instructions which are executable by the second processor type providing the loader module for execution by the operating system of the host system and packaging the loader module with the code module to form the executable application.

Conveniently the linking occurs before or at the same time as the loader module is packaged with the code module to form an executable application.

Advantageously the linking links the code module to an operating system abstraction application programming interface provided in the loader module.

Conveniently the code module is machine code and the step of generating the code module comprises compiling the machine code from source code using a compiler for a selected processor type.

Advantageously the code module incorporates a single function entry point to initiate execution of the code module.

Preferably the code module has an external dependency to an operating system abstraction application programming interface.

Advantageously generating the code module comprises using an object file linker to link a machine code object file into a binary library file in an executable and linkable format.

Preferably generating the code module further comprises modifying the executable and linkable format library file into a format suitable for linking with the loader module.

Conveniently the step of packaging comprises storing each code module with a respective loader module in a single executable application file.

Advantageously the step of packaging further comprises storing application assets in the single executable application file.

Preferably the step of packaging further comprises storing metadata in the single executable application file.

According to another aspect of the present invention there is provided a system for evaluating executable applications the system comprising a memory a processor of a first processor type and an emulator module which when executed provides an emulation environment which emulates a second processor type which is different from the first processor type wherein the system is configured to execute a loader module of an application execute the emulator module to provide an emulation environment which emulates the second processor type execute a code module of the application within the emulation environment to generate a functional command write the functional command into the memory of the system and execute the functional command within the loader module.

Preferably the system is configured to execute the emulator module in response to the loader module generating a functional call to the code module.

Conveniently the emulator module is configured to generate an exception signal when the functional command is written into the memory.

Advantageously the loader module is configured to execute the functional command in response to the generation of the exception signal.

Conveniently the system is configured to pass execution back to the code module in the emulation environment after the functional command has been executed within the loader module.

Preferably the system further comprises a system for producing an executable application which incorporates an interface for selecting a processor type and an operating system a compiler to generate a code module comprising instructions which are executable by a processor type selected using the interface a storage module for storing a loader module configured for execution by an operating system selected using the interface and a packaging module for packaging the loader module with the code module to form an executable application so that when the executable application is provided on a device incorporating a processor of the selected processor type and running the selected operating system the device can execute the executable application to execute the loader module to load the code module for execution by the processor.

Conveniently the system further comprises a linker module which is configured to link the code module to the loader module.

According to one aspect of the present invention there is provided a method of simulating execution of an executable application using a host system the method comprising providing a host system with an executable application comprising host loader module and a host code module providing a target device with a target interface module establishing a communication link between the host system and the target device executing the executable application on the host system so that the host code module generates a functional command passing the functional command from the host code module to the host loader module communicating the functional command from the host loader module to the target interface module executing the functional command on the target device generating a result value on the target device and passing the result value to the target interface module and communicating the result value from the target interface module to the host loader module to return the result value for input to the executable application running on the host system.

Preferably the target device is provided with a target loader module and wherein the method further comprises communicating the functional command from the target interface module to the target loader module and the step of executing the functional command comprises executing the functional command within the target loader module.

Conveniently the method further comprises receiving at least one input at the target device and using the at least one input to generate the result value.

Preferably the or each sensor is selected from a group consisting of an accelerometer a positioning sensor a proximity sensor a magnetometer a thermometer and a video camera.

Conveniently the target device incorporates a screen and the method further comprises generating display data within the host system transmitting the display data to the target device and outputting the display data by displaying elements on the screen of the target device.

Advantageously the displayed elements are substantially identical to elements that would be displayed on the screen of the target device if the executable application was running on the target device.

Conveniently the operating system of the host system is different from the operating system of the target device.

Advantageously the host system and the target device each incorporate a respective central processing unit and wherein the central processing units are of a different type to one another.

Preferably the communication link between the host system and the target device is a wireless communication link.

Conveniently the communication link between the host system and the target device is a wired communication link.

Advantageously the method further comprises initially producing the executable application by generating the host code module comprising instructions which are executable by a central processing unit of the host system providing the host loader module for execution by the operating system of the host system and packaging the host loader module with the host code module to form the executable application.

According to another aspect of the present invention there is provided an arrangement for simulating execution of an executable application using a host system wherein the arrangement comprises a host system which is provided with an executable application comprising host loader module and a host code module a target device incorporating a target interface module and a communication arrangement for establishing a communication link between the host system and the target device the host system being configured to execute the executable application so that the host code module generates a functional command and passes the functional command from the host code module to the host loader module the communication arrangement being configured to communicate the functional command from the host loader module to the target interface module for execution on the target device wherein the target device is configured to generate a result value pass the result value to the target interface module and communicate the result value from the target interface module to the host loader module to return the result value for input to the executable application running on the host system.

Preferably the target device is provided with a target loader module and wherein the target device is configured to communicate the functional command from the target interface module to the target loader module for execution within the target loader module.

Conveniently the target device is configured to receive at least one input and use the at least one input to generate the result value.

Advantageously wherein the target device incorporates a touchscreen to receive the at least one input.

Preferably the or each sensor is selected from a group consisting of an accelerometer a positioning sensor a proximity sensor a magnetometer a thermometer and a video camera.

Conveniently the target device incorporates a screen and wherein the host system is configured to generate display data and transmit the display data to the target device and the target device is configured to output the display data by displaying elements on the screen of the target device.

Advantageously the displayed elements are substantially identical to elements that would be displayed on the screen of the target device if the executable application was running on the target device.

Conveniently the operating system of the host system is different from the operating system of the target device.

Advantageously the host system and the target device each incorporate a respective central processing unit and wherein the central processing units are of a different type to one another.

Preferably the communication arrangement between the host system and the target device is a wireless communication arrangement.

Conveniently the communication arrangement between the host system and the target device is a wired communication arrangement.

The inventors of the present invention noted that the variance in the number of target CPU architecture families is small. Popular CPU architectures include Intel s x86 architecture ARM s architecture and the MIPS architecture. If one considers only one target device sector for instance embedded devices including smartphones and tablets then in general the variance is even smaller in the embedded case over 90 of devices use the ARM architecture .

Embodiments of the present invention use the concept of binary code library linkage whereby separate areas of application functionality can be compiled separately into multiple code libraries and later linked together to form a single executable application. Each library advertises its linkage points through a table of function entry points points that other libraries can link to and external dependencies points that the library itself is requiring linkage to . Embodiments of the invention can operate using both static linking whereby the linkage step is performed at application deployment time or dynamic linking whereby the linkage step is performed each time the application is executed.

Embodiments of the invention allow an application to be compiled as a code module which is preferably a CPU dependent but OS agnostic binary code library an App Binary allowing the developer to leverage all optimisations available from supporting compilers. The code module will be referred to as an App Binary in the following description.

The App Binary code library advertises a single function entry point the main function which would be called to initiate execution of the application. The library has two sets of external dependencies 

ED1 External dependencies to an OS abstraction API. As described above the application source code can never reference OS specific APIs its only interaction with the OS must be through the abstracted APIs.

ED2 External dependencies to device drivers that are commonly expected to be present on all of the target devices.

Because the App Binary has no OS specific dependencies it is entirely portable across OS platforms. The App Binary is compiled CPU machine code so it has a dependency on the CPU architecture choice of the compiler for example an App Binary compiled using the GCC ARM compiler with the appropriate settings could run on almost any embedded device utilising an ARM CPU but could not run on a device utilising an Intel x86 CPU.

The App Binary cannot be executed in isolation as it has external dependencies. Embodiments of the invention therefore provide a second component the Loader . A Loader is provided for each target OS and in each case it is a standard OS specific application containing the following functionality 

FD Ability to dynamically link the external dependencies 2 to any industry standard drivers that are commonly expected to be present on all of the target devices

This design enables all OS specific code to reside within the Loaders. The Loaders are provided within the SDK itself so have been pre compiled using the OS specific SDKs in each case. The application developer is not required to compile the source code for the Loaders and may not even be provided with such source code which have to be maintained using the specific code language choices mandated by the OS providers. Because the App Binary requires no knowledge of the Loader it might be linked to it is free to be compiled within a toolchain entirely independent of any OS specific mandate and the application source code language choice is similarly independent.

Embodiments of the invention may produce executable applications for use with operating systems selected from a group consisting of iOS Android Windows MeeGo and webOS. However it is to be appreciated that further embodiments of the invention may produce executable applications for use with any other operating system.

Referring now to of the accompanying drawings a Loader for three different OSs is created as follows 

1. The OS abstraction API implemented by each Loader is defined by a single source code header file or series of header files which are shared across all Loaders.

2. Functionalities FA FC and FD are common across all target OS platforms. Therefore the code to implement these functionalities is generic and shared between all Loaders.

3. Some subsets of the functionalities of FB may be common across some target OS platforms. For example target OS platforms based on Linux including Android webOS and MeeGo may be able to share some code related to subsets of FB.

4. The bulk of the functionalities of FB will be specific to the target OS platform and make use of APIs that are provided only by that OS platform s specific SDK.

5. Each target OS platform will provide a standard SDK that can be used to build applications for execution on that target OS. The Loader for each target OS must be compiled using this standard SDK.

6. The end result of compiling 1 2 3 and 4 within the relevant OS specific SDK 5 will be the Loader for the respective target OS.

1. A developer s application consists of standard source code and header files. Function calls to the OS abstraction API require the inclusion of the header file describing that API. Function calls to industry standard drivers expected to be on the target device require the inclusion of the header files describing those drivers APIs.

2. A code compiler for example the CodeSourcery GCC compiler is used to compile the application source code into native CPU instructions for the target CPU architecture.

4. An object file linker for example the CodeSourcery GCC linker is used to link the binary object files together into a single binary library file. At this stage the library file will be in an Executable and Linkable Format ELF that is the output from the linker tool. ELF files contain the compiled code and structural information which enables the code to be loaded at any memory address and linked to other libraries.

5. A post linker tool is provided to modify the standard ELF file into a form more suitable for linking with the Loader. For example standard ELF files are required to be seeked upon loading this means that if the standard ELF is compressed if must be entirely decompressed into memory before it can start to be read. This can be impractical when loading large ELF files on memory constrained devices. The modified ELF file does not require seeking the entire file can be compressed and when loaded it can be decompressed section by section. The modified ELF file is typically 20 40 the size of the standard ELF file.

Once the App Binary and Loader have been created the two can be deployed for execution on a target device. Three deployment configurations will now be discussed below.

Referring now to of the accompanying drawings an App Binary can be statically linked to the Loader at deployment time as follows 

1. The App Binary is created from the developer s source code as shown in . The Loader for the target OS has already been built by the ISV as shown in and is provided to the developer within the SDK. The Loader is a an executable application as understood by the target OS.

2. The App Binary is statically linked with the Loader using an offline tool provided within the SDK. The linkage process is identical to that indicated in FB.

3. The application assets or resources including images fonts text strings and any other data files used by the application are placed alongside the statically linked executable code. The application metadata required by the target OS including the application name desktop icons in various sizes manifests and other required files are also placed alongside.

4. All the files aforementioned are bundled into a standard application installer package as defined by the target OS. This bundling process may involve file compression and usually involves use of tools from within the OS specific SDK. However these tools are usually made available under permissive licenses enabling them to be redistributed within the ISV SDK for the developer s convenience. Finally the application installer package may be signed or encrypted using a process proscribed by the OS vendor. Again these signing tools are often able to be redistributed within the ISV SDK.

The end result is a standard application installer package for the target OS that can either be deployed directly to the target device or hosted for distribution to the target device for example on an app store no additional ISV software is required to be resident on the target device.

Referring now to of the accompanying drawings an App Binary can be dynamically linked to the Loader at execution time as follows 

1. The App Binary Loader Assets and Metadata as defined in are all placed alongside one another. Note that no linkage is created between the App Binary and Loader.

2. Using the same process described in step these components are packaged together into a standard application installer package for the target OS and installed on the target device either through direct deployment or via some distribution mechanism such as an app store .

3. When the package is installed onto the device the components parts App Binary Loader Assets and Metadata once again end up alongside one another usually in uncompressed form.

4. The Loader is actually the executable app as understood by the OS. Upon execution the Loader performs the steps FA FC FD described earlier and the App Binary is dynamically linked to the Loader.

Referring now to of the accompanying drawings an App Binary can be linked to the Loader on a target device if the Loader is already resident on the target device as follows 

1. In this arrangement the target device already has a resident Loader that is capable of linking against an App Binary. This Loader is contained as part of a single executable application on the target device such as a Storefront app that is used to download and execute multiple other applications created using the ISV SDK. Therefore for each further application to be delivered to the device only the App Binary and Assets are required.

3. The ISV package file is delivered to the device perhaps as a download process initiated by the Storefront app so that the App Binary and Assets are alongside each other. The Storefront application and Loader as already resident on the device.

4. The delivered application is usually executed as an action within the Storefront application itself. The Storefront application can ask the Loader to link and execute the App Binary just as if the delivered application were executed from the device desktop. The Loader then performs a dynamic link and executes the application as shown in .

Next a specific example will be described in which an application is created and deployed. The application is a Hello World example being the industry standard simplest code example for an SDK. The deployment targets will be an iOS device and an Android device.

The OS abstraction API is known as the S3E API and is described by the C header file s3e.h . Function calls starting with the s3e prefix are calls to the OS abstraction API. This example contains only 5 function calls all of them to the OS abstraction API. A short description of each of these follows 

Prints a text message on the current surface using a standard simple font provided within the Loader.

Displays the current surface to the device screen. Most systems employ a double buffering system whereby the surface drawn to is not made visible on the screen until this function is called.

This also allows the OS to do any required processing for this application for example processing device or user interface messages. It may also permit the CPU to enter a low power state. The user can specify the amount of time to yield for if this value is passed as zero the Loader will yield for the minimum amount of time required by the underlying OS to perform essential processing.

As described earlier the main function will become the single point of entry for the App Binary library. The five calls to the OS abstraction API will become the only external dependencies of the App Binary library.

In this specific example a deployment environment is then initiated in which the developer deploys the same ELF file simultaneously to iOS and Android as part of an application installer package for those platforms as follows 

It is to be appreciated that the embodiments of the invention described above enable source code to be written in a preferred language compiled using a CPU specific compiler and then published for execution on a plurality of different operating systems. This has the advantage of producing CPU optimised code with minimal bugs.

Embodiments of the present invention may produce executable applications to run on devices such as mobile telephones tablet computers laptop computers televisions or set top boxes. Devices for use with embodiments of the invention may be embedded devices.

It is to be appreciated that some embodiments of the invention produce a single executable file or app whereas other embodiments of the invention produce an executable application which is composed of a collection of separate files.

It is to be appreciated that the arrangements described above enable source code to be written in a preferred language compiled using a CPU specific compiler and then published for execution on a plurality of different operating systems. This has the advantage of producing CPU optimised code with minimal bugs.

The arrangements described above may produce executable applications to run on devices such as mobile telephones tablet computers laptop computers televisions or set top boxes. The devices may be embedded devices.

It is to be appreciated that the above arrangements can produce a single executable file or app whereas other arrangements produce an executable application which is composed of a collection of separate files.

The arrangements described above provide a mechanism for all OS dependencies to be separated into a binary form the Loader which is distinct from the core application the App Binary . This leads to the possibility of executing the App Binary on a different CPU architecture from that of the Loader.

Embodiments of the present invention aim to provide value to application developers during the development and debugging of code destined to be deployed on remote devices. The host environment is the development environment typically a desktop computer running Windows or OSX and typically utilising an x86 CPU architecture. The target environments are the devices on which the application will be deployed this may include mobile telephones tablets and TVs. The target environments typically do not utilise an x86 CPU architecture.

The most common application development scenario is that the App Binary is compiled for the host CPU architecture typically x86 and the host Loader typically compiled for x86 and running on Windows OSX or Linux dynamically links to and executes the App Binary. The App Binary makes function calls to the Loader through its external dependencies namely the OS abstraction APIs.

Embodiments of the present invention seek to provide an additional scenario whereby the App Binary is compiled for a different CPU architecture typically ARM or MIPS . The host Loader remains the same typically compiled for x86 and running on Windows OSX or Linux but instead of executing the App Binary by calling directly into its main entry point it initialises a CPU emulation environment to start emulating the App Binary from the main entry point. Whenever the App Binary makes a call to the OS abstraction API some mechanism is used as supported by both the chosen emulation environment and the host environment to pass execution through to the Loader. Once the Loader has completed execution of the OS abstraction API function it passes execution back to the CPU emulation environment.

Embodiments of the invention offer a way for developers to test a substantial portion of the target application the App Binary within the host environment. This can save a large amount of time as typically bugs specific to compilation for the target CPU architectures would only be discovered when the application was executed on the target devices where debugging is a time consuming experience. Embodiments of the invention allow the App Binary compiled for the target CPU architectures to be tested within the host environment which typically provides a much more efficient debugging environment.

Next a specific example will be described whereby the App Binary is running under emulation within a host environment. The host environment is a desktop PC utilising the x86 CPU architecture and running the Windows OS. The emulation environment is QEMU an open source project described here http wiki.qemu.org Main Page configured to emulate the ARM architecture.

When running the App Binary under emulation calls to the OS abstraction API are diverted such that each API call ends up writing to a specially designated memory address. QEMU is configured so as to throw a CPU exception whenever this memory address is written. The CPU exception is trapped by the Loader which is able to extract the functional arguments from QEMU s ARM register list and invoke the relevant Loader OS abstraction function with the correct arguments. In this specific a scenario a critical requirement is met whereby the QEMU emulation environment and the Loader share the same memory address space and therefore memory pointers passed as functional arguments from the emulation environment are still meaningful within the Loader.

Once execution of the function has been completed within the Loader the function return value is copied into the relevant QEMU ARM register and the emulation environment is invoked once more to continue emulation.

1. The host environment is the standard environment for application development typically a Windows or OSX environment running on x86

2. The Loader is the standard Loader for the host environment typically a Windows Loader running on x86

4. The emulation environment is a CPU emulation environment typically provided by a 3party and potentially modified to support the architecture of the invention

1. The source code of the application contains 5 function calls to the OS abstraction API these are the function calls with the s3e prefix

2. The disassembly of the App Binary compiled for ARM shows how the lines of source code become ARM CPU instructions. Each of the 5 boxes containing a b1 . . . instruction corresponds to 1 of the 5 function calls to the OS abstraction API. For example the ARM CPU instruction b1 0x4a00016c corresponds to the call to the function s3eDeviceCheckQuitRequest . Assuming the same implementation system as described in the Specific Example above the QEMU emulation environment will emulate the ARM CPU instructions up to and including this instruction the ARM code jumped to by the b1 instruction does not contain an implementation of the s3eDeviceCheckQuitRequest function rather it contains ARM code provided by the embodiment of the invention that writes to a specific memory address that has been trapped by the Loader the Loader running in the host environment that is Windows running on x86 catches this exception extracts any function call arguments in this case there are none from the QEMU environment and invokes the host environment Windows running on x86 implementation of the s3eDeviceCheckQuitRequest function which will return true if the user has closed down the application within the host environment for example by clicking the standard Windows application exit button once the s3eDeviceCheckQuitRequest function has been completed within the host environment the Loader invokes the QEMU environment to continue emulated execution from the next ARM instruction in this case the instruction mov r3 r0 emulated execution then continues until the next disassembled s3e function i.e. the next b1 . . . instruction at which point a similar pattern is repeated

The specific example described above illustrates how embodiments of the invention enable an application to be executed on a host system so that the application can be easily tested by the developer.

It is to be appreciated that embodiments of the invention may incorporate the method steps and system features which enable a developer to produce an application.

The arrangements described above provide a mechanism for all OS dependencies to be separated into a binary form the Loader which is distinct from the core application the App Binary . This leads to the possibility of executing a Loader and App Binary within the host development environment whilst at the same time executing a Loader within a target device environment such that the Loader within the host development environment can retrieve information from the Loader within the target device environment.

Embodiments of the present invention aim to provide value to application developers during the development and debugging of code destined to be deployed on remote devices. The host system or environment is the development environment typically a desktop computer running Windows or OSX and typically utilising an x86 CPU architecture. The target device or environments are the devices on which the application will be deployed this may include mobile telephones tablets and TVs. The target environments typically do not utilise an x86 CPU architecture.

The most common application development scenario is that the App Binary is compiled for the host CPU architecture typically x86 and the host Loader typically compiled for x86 and running on Windows OSX or Linux dynamically links to and executes the App Binary. The App Binary makes function calls to the Loader through its external dependencies namely the OS abstraction APIs.

Embodiments of the present invention seek to extend this scenario whereby a target device running a target Loader module appropriate for that device is connected to the host Loader module of the host environment through a target interface module in the form of an application running on the target device. In an alternative embodiment the target device may only be provided with a target interface module and not a target Loader module. The host Loader remains the same typically compiled for x86 and running on Windows OSX or Linux . Whenever the App Binary running within the host environment makes a function call functional command to the OS abstraction API the host environment Loader checks to see if a target device is connected to the host environment in such a way that this particular function call should be re routed to the target device. This connection is preferably established in advance for example by running a Remote Client application on the target device and having both the host environment Loader and the Remote Client application broadcast their availability over a local wireless network. If such a communication link exists and the host environment has been configured to re route this particular function call remotely then the host environment Loader issues a command to the Remote Client application to execute the function call using the target device Loader and return the result value to the host environment Loader. This result value is subsequently returned to the App Binary running within the host environment .

The issuing of the command to the Remote Client and the returning of the resulting value s is typically done using standard network communication protocols such as sending to and receiving from network sockets. As far as the App Binary is concerned the function call was executed by the host environment Loader and it has no knowledge of whether the function was evaluated purely within the host environment Loader or by delegation to any target device. This mechanism is known as a Remote Procedure Call RPC .

In embodiments of the invention the target device is preferably configured to receive at least one input. The target device preferably uses the at least one input to generate a result value.

To receive the or each input the target device preferably incorporates a touchscreen at least one button a microphone or a sensor such as an accelerometer a positioning sensor a proximity sensor a magnetometer a thermometer or a video camera.

Embodiments of the invention offer a way for developers to test the target application within the host environment but using inputs from connected target devices. This can save a large amount of time as typically issues relating to user interfaces can only be tested using the hardware form factors of the target devices. Embodiments of the invention allow the user interface to be tested using the target device form factors whilst still keeping the App Binary execution within the host environment which typically provides a much more efficient debugging environment.

In order to ensure that the user interface inputs received from the target device are as consistent as possible with those received if the entire application were executing on the target device the visual display produced by the application running within the host environment is preferably sent over the network connection to the target device so that the visual display of the target device matches that of the host environment.

Next a specific example will be described. The host environment is a desktop PC utilising the x86 CPU architecture and running the Windows OS. The target device is a mobile tablet utilising the ARM architecture and running the Android OS.

H. The host environment is the standard environment for application development typically a Windows or OSX environment running on x86

H1. The host environment Loader is the standard Loader for the host environment typically a Windows Loader running on x86

T. The target device is typically a mobile device in this case we assume running the Android OS within an ARM CPU architecture

T1. The target device Loader is the standard Loader for the target environment in this case the Android Loader for ARM

T2. The Remote Client application is a target device interface module which allows connection to the host environment Loader and communication between the two Loaders

HT. The Remote Client application and the host environment Loader communicate via a network connection typically a local wireless network or a wired communication link

The Remote Client application T2 has been deployed to the target device and executed. The host environment Loader H1 contains a graphical user interface allowing the developer to search for target devices on available network connections that might be running the Remote Client application. When the target device in question has been found the host environment Loader and Remote Client application can now communicate over the network connection HT .

The flow of execution of the App Binary can be examined by considering each line of the source code in turn 

The specific example described above illustrates how embodiments of the invention enable an application to be executed on a host system whilst receiving inputs from a target device so that the application can be easily tested and debugged by the developer without ignoring the specific user interface facilities and constraints of the target devices.

It is to be appreciated that embodiments of the invention may incorporate the method steps and system features which enable a developer to produce an application.

When used in this specification and claims the terms comprises and comprising and variations thereof mean that the specified features steps or integers are included. The terms are not to be interpreted to exclude the presence of other features steps or components.

While the disclosure has been described in detail and with reference to specific embodiments thereof it will be apparent to one skilled in the art that various changes and modifications can be made therein without departing from the spirit and scope of the embodiments. Thus it is intended that the present disclosure cover the modifications and variations of this disclosure provided they come within the scope of the appended claims and their equivalents.

