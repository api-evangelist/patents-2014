---

title: Method and device for the programming and configuration of a programmable logic controller
abstract: A method and device for the programming and configuration of a programmable logic controller are disclosed. The method can include: locating a configuration tool in a programming tool, wherein the configuration tool includes a module in an IEC61131 language; integrating at least one further module into the configuration tool, and executing the programming and configuration of the programmable logic controller in a high-level language using a C-Code editor, and wherein the at least one further module is configured to provide a definition of interfaces between an IEC61131 code and a high-level language code, and provide a configuration of the high-level language code.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09235381&OS=09235381&RS=09235381
owner: ABB AG
number: 09235381
owner_city: Mannheim
owner_country: DE
publication_date: 20140106
---
This application claims priority as a continuation application under 35 U.S.C. 120 to PCT EP2012 002832 which was filed as an International Application on Jul. 5 2012 designating the U.S. and which claims priority to European Application No. 11005514.2 filed on Jul. 6 2011. The entire content of these applications are hereby incorporated by reference in their entireties.

The disclosure relates to a method and a system for the programming and configuration of a programmable logic controller which can be used in the integration of intelligent field devices in a control or automation system in process automation or in machine controls for controlling technical processes and or plant components.

The basis for programming and configuring programmable logic controllers PLC can be for example the device independent programming system according to the international standard IEC 61131 3 with the programming languages described there. Programming environments for programmable logic controllers can also allow the use of high level languages such as BASIC Java C or C C C .

The programming and configuration of the programmable logic controllers can be implemented by means of a PC based programming tool or programming device also called engineering tool as a sequence of individual program instructions technologically or functionally associated program instructions in each case forming one program module also called function block.

A complete PLC program can contain a multiplicity of such program modules. The modules can be input in one of the aforementioned PLC application related programming languages for example as an instruction list as a contact plan as a logic plan as a function plan as a sequence language or a structured text via the programming tool. There are PC based tools for creating translating checking and downloading the PLC code into the devices of the automation system.

A method for inputting the program instructions in the high level language C is for example described in EP 860 758 A1. An input device of the programming device is shown which can be connected via a first data line to a converting device and can be connected via a second data line to a high level language compiler which can translate the program instructions into a code which can be read or processed by the programmable logic controller.

On the product page of the company Bernecker Rainer Industrie Elektronik GmbH B R Automation Studio Integrated IEC 61131 3 Languages CFC and ANSI C see www.br automation.com cps rde xchg br productcatalogue hs.xsl products151728 ENG HTML.htm it is described that the programming language ANSI C can allow the users to call up function blocks and access addresses global access variable from other IEC languages.

Furthermore there are solutions in which various source file languages such as for example IEC61131 C C C Basic or Java can be translated into an intermediate code and the intermediate code can then be retranslated in accordance with the producer related target platforms of the devices used by means of an additional software component. This solution can be used for example by the company KW Software of the Phoenix Contact Gruppe and is shown by way of example in .

A further solution relates to the runtime system of the programmable logic controller according to IEC61131. In this context the C Code functions can only call up variables with the programs described in IEC61131 3. Access to the system resources such as inputs and or outputs or the memories of the devices connected to the programmable logic controller is not provided.

A method for the programming and configuration of a programmable logic controller is disclosed the method comprising locating a configuration tool in a programming tool wherein the configuration tool includes a module in an IEC61131 language integrating at least one further module into the configuration tool and executing the programming and configuration of the programmable logic controller in a high level language using a C Code editor and wherein the at least one further module is configured to provide a definition of interfaces between an IEC61131 code and a high level language code and a configuration of the high level language code.

A device for the programming and configuration of a programmable logic controller is disclosed the device comprising a configuration tool located in a programming tool wherein the configuration tool includes a module in an IEC61131 language and at least one further integrated module configured for programming of the programmable logic controller in a high level language by using a C Code editor and for defining interfaces between an IEC61131 code and a high level language code and for configuration of the high level language code.

The disclosure is based on specifying a method and a device by means of which the programming and configuration of a programmable logic controller can be simplified wherein the program instructions created in a high level language for example C Code run on the devices connected to the programmable logic controller in parallel with the program instructions generated according to IEC 61131 3 and by this means direct access to the system resources such as inputs and or outputs or the memories of the devices connected to the programmable logic controller can be executed. In accordance with an exemplary embodiment for example the user can edit code in the high level language and in IEC61131 languages.

The method according to the disclosure for the programming and configuration of a programmable logic controller can be based on a configuration tool located in a programming tool wherein in the configuration tool apart from a module in an IEC61131 language at least one further module can be integrated by means of which the programming of the programmable logic controller is executed in a high level language by using a C Code editor. By means of the further module a definition of interfaces between an IEC61131 code and a high level language code and the configuration of the high level language code can be provided according to the disclosure.

According to the disclosure an additional module also called plug in can be integrated in the configuration tool for carrying out the method according to the disclosure for the programming and configuration of the programmable logic controller by means of the configuration tool located in the programming tool which additional module can generate and insert library functions in a high level language for example C Code for programming the controller by which means the creation and integration of program instructions created in a high level language into the devices of the automation system becomes executable in a simple manner.

According to the disclosure a high level language editor a library management and an IEC 61131 interface A can be integrated in the additional module.

In accordance with an exemplary embodiment the library management can be used for setting up and managing user defined libraries. In the library management libraries can be configured initially with operating program modules executable in a high level language for example C Code together with corresponding compiler options as C Code plug in tab configuration.

Following this a mapping of hardware devices connectable to the programmable logic controller with their inputs outputs and or local variables can be configured in the IEC 61131 interface in the high level language as C Code plug in tab IEC61131 interface in a library project.

According to an exemplary method sequence the plug in tab configuration and the plug in tab IEC61131 interface can be edited and stored in the additional module.

An application library can be generated from this in an application module not visible to the user by using a compiler and additional library specific header files and the generated application library can be added not visibly to the user to the target project code stored in the programming tool of the programmable logic controller. After that the code can be generated in the corresponding high level language for the target project to be carried out on the programmable logic controller in the programming tool and the program organization unit entities also called program organization unit POU entities contained therein can be implemented and transmitted from the programming tool together with the POUs for the IEC61131 3 applications into the programmable logic controller.

In accordance with an exemplary embodiment the runtime environment for IEC and C Code can be divided into 2 runtime systems between which only a complex data exchange may be possible.

According to the disclosure the sequence of the program instructions created under C Code can take place under a shell according to the IEC 61131 standard so that only this shell and not the C Code running in the background can be visible to the user. The access to the system resources can only be via the existing IEC 61131 interfaces. Accordingly the runtime environment of a C Code sequence appears like a sequence of the program instructions under an IEC 61131 environment.

According to the present disclosure existing tested and proven interfaces of a program sequence according to the IEC 61131 standard can be adopted and in consequence a costly development of new C Code based interfaces can be omitted.

The method described above according to the present disclosure can allow the programmer to use his or her own C Code programs or program instructions only called C Code in the text which follows within an IEC61131 project. For example in this arrangement the program instructions previously created in C Code can run in parallel with those of the IEC 61131 3 program instructions on the devices connected to the programmable logic controller. The system resources such as inputs and or outputs or the memories of the devices connected to the programmable logic controller can be accessed directly.

In accordance with an exemplary embodiment the disclosure can relate to a device and to a system for the programming and configuration of a programmable logic controller.

The device for the programming and configuration of the programmable logic controller can include a configuration tool located in a programming tool in which apart from a module in an IEC61131 language at least one further module can be integrated by means of which the programming of the programmable logic controller can be executed in a high level language by using a C Code editor and which can allow a definition of interfaces between an IEC61131 code and a high level language code and the configuration of the high level language code.

In accordance with an exemplary embodiment an additional module can be integrated in the configuration tool of the controller development system into which additional module generated library functions in a high level language for example C Code can be inserted for programming the controller as a result of which program instructions created in a high level language can be created and integrated into the devices of the automation system in a simple manner.

For this purpose the additional module can include a high level language editor for example a C Code editor a library management in which a library with program modules executable in the high level language for example C Code can be specified or configured together with corresponding compiler options as high level language add on program of the tab configuration and can be used for setting up and managing user defined libraries an IEC 61131 interface in the high level language for example C Code which can map the hardware devices which can be connected to the controller with their inputs outputs and or local variables in a library project. This interface is also called C Code add on program tab IEC61131 interface.

In accordance with an exemplary embodiment the PC based configuration tool can provide the user with the option of combining the various programming languages according to IEC 61131 3 and C. For this purpose a selection unit or interface can be provided for the selection between programming by using a high level language such as C Code or under the programming language based on IEC 61131 3.

Apart from a first application module or interface for programming according to IEC 6113 3 the programming tool can have a second application module or interface for programming in the programming language C switching between programming by using a high level language such as for example C Code or under the programming language based on IEC 61131 3 being provided by means of a selection unit.

The second programming interface can interact with an intermediate language or intermediate code called Common Intermediate Language CIL standardized in the meantime stored on the software platform which can translate the programs created and reproduces them already simplified.

The intermediate code can be translated on an execution computer also called target computer or target platform from a runtime system virtual execution system into the system s own program code usually a machine code in order to be able to thus execute the programs present in CIL in the programmable logic controller.

In this context the translation into the system s own program code can take place not directly but firstly a CIL Code which specifies the corresponding program commands as a sequence of byte values is generated in a first step. The CIL Code can be translated to native machine code and executed in a runtime system on the execution computer .

A third programming interface can be provided as so called user configuration tool for generating CIL Code .

The additional module A can include a C Code editor A a library management A in which a library with program modules executable in C Code can be specified or configured together with corresponding compiler options as C Code add on program the tab configuration an IEC 61131 interface A in C Code which maps the hardware devices connectable to the controller with their inputs outputs and or local variables in a library project. This interface can also be called C Code add on program tab IEC61131 interface.

In a first step 1 libraries with operating program modules executable in C Code together with corresponding compiler options can be initially configured as C Code plug in tab configuration in the library management A.

In a second step 2 the IEC 61131 interface A can be configured in C Code for mapping hardware connectable to the programmable logic controller D with its inputs outputs and or local variables in a library project as C Code plug in tab IEC61131 interface and in a third step the plug in tab configuration and the plug in tab IEC61131 interface is correspondingly edited and stored in the additional module A.

In a fourth step 4 an externally created application library which can be translated into C Code in the background that is to say invisibly to the user from the present source code in a compiler using additional library specific header files can be provided in an application module programmed in C Code for the programming tool B.

After that in a fifth step 5 the externally created application library can be added to the target project code PLC target project code of the programmable logic controller D which can be stored in the programming tool B. This method step too can run in the background.

In a next step 6 the C Code can be generated in the programming tool B for the program to be executed on the programmable logic controller also called target project in the text which follows and the program organization unit entities contained therein which include the entities of the programs function blocks and functions can be implemented.

In a step 7 the target project can now be loaded from the programming tool B to the programmable logic controller D by which means a library of binary C Code programs also called C Code library binary can be linked in and loaded to the controller D.

In an optional step 8 the executable binary code C Code library binary can be relocated from the runtime system of the programmable logic controller D and during this process all external application program interface references API references can be resolved and linked. To access additional functions which can be implemented in a firmware stored in the programmable logic controller the C Code POUs can call up a firmware API application programming interface .

Since the firmware can be encapsulated in the C Code header files the user of the programmable logic controller only needs the functions function modules and programs stored in C Code that is to say no programming knowledge of the special firmware in each case.

It is also proposed that the PC based programming tools B can have an interface which can allow the programmer to select between programming in the high level language and programming in IEC 61131.

By means of the method according to the disclosure new functions application modules and also existing functions in the libraries can be implemented as C Code or in IEC 611131 3 languages and used combined in the target application.

In accordance with an exemplary embodiment the method according to the disclosure can be based on the programming tool B provides external library POUs that can be implemented in C Code. The configurator used can support the plug ins of the C Code libraries the IEC1131 3 interface specification the C Code editor and the compiler integration including the display of compiler errors and or the integration of externally provided libraries in a target project of the PLC.

In an exemplary embodiment of the disclosure system functions for C Code are not mapped as further application modules from the system libraries but mapped as application program interfaces also called application programming interfaces API grouped into function areas for the firmware FW API.

In accordance with an exemplary embodiment before a programmable logic controller can be operational the hardware devices provided for it especially intelligent field devices which can be connected to a controller via communication couplers and a field bus can be mapped in the programming tool B as component of an PLC or controller project information about input output addresses of these hardware devices being stored in the controller project and made accessible to the user program. For example so that the inputs and outputs of the hardware devices of the system can be addressable the controller and the input output units of the hardware can be firstly configured and a configuration of a PLC project also called controller configuration can be created as component of the PLC or controller project.

In accordance with an exemplary embodiment the project configured with the programming interface can be transmitted via an Ethernet bus to which an operating unit can also be connected into the controller of the programmable logic controller and from there via the field bus into the field devices .

For the creation and configuration of the project an application module can be provided in the programming tool B as runtime environment in the programmable logic controller in which global variable application program interfaces IEC61131 3 applications and C Code based applications are integrated which are provided for a transmission into the controller .

The IEC61131 3 applications are organized in the POUs in a POU unit interacting therewith for example as special function block diagrams FBD structured text ST contact plans LD instruction lists IL and or function plans SFC CFC . Additionally to the POUs for the IEC61131 3 applications applications C Code based such as FBD ST LD IL SFC CFC can be implemented in the POU unit . The applications can be correspondingly composed according to the disclosure of application modules programmed in IEC61131 3 languages and programmed in C Code.

All inputs and or outputs of the hardware devices can be mapped as global variable and all POUs share the global variable so that the C Code applications can have access to the inputs and or outputs via the interface of the POU unit .

System functions such as for example real time functions write and read files memory administration floating point operations real time functions and real time clock are not mapped as further application modules from the system libraries according to the disclosure but grouped into function areas as application program interface API for the firmware FW API.

In order to implement the POU unit in the C Code applications the generated application library can be used. The library elements deposited in the application library such as functions function blocks and programs can be specified by the POU interface of the POU unit according to the IEC61131 3 runtime system. In this context the POU interface can define the connection points to other POUs inputs and outputs and to the higher level operating unit mapped as local variable such as for example variable of the input IN output OUT and or input output IN OUT type.

Each local POU variable created according to IEC61131 3 and in C Code can be accessible and addressable via a PC access for example the operating unit or via a representation via the Internet.

The entire configuration of a PLC project consisting of variables and tasks the application modules which reference other application modules can be loaded with the IEC61131 3 applications and the C Code based applications into the controller .

In accordance with an exemplary embodiment since the system resources can only be accessed via the existing IEC 61131 interfaces the runtime environment of a C Code sequence can appear like a sequence of program instructions under an IEC 61131 environment. In accordance with an exemplary embodiment separate downloading of the C Code applications into the controller may not be needed.

In a first method step 11 a function block in the engineering tool B of the programmable logic controller can be specified with all of its inputs and outputs and all internal and local variables in a library project as C Code plug in tab IEC61131 interface and the library project can be stored in the engineering tool B. From the engineering tool B the C Code plug in tab IEC61131 interface can be exported in a second method step 12 in the background to a header file and a C Code source file or frame C file template .

In a third method step 13 the function block can be programmed in C Code by using the C Code plug in tab IEC61131 interface previously specified in the header file and the C Code source file and in a fourth method step 14 the present C source code can be translated into the corresponding binary code by means of the compiler .

After that the application library can be opened in the PLC target project Z in a next method step 15 and in a further method step 16 the function block entities can be generated in the target project Z.

The PLC target project Z can be loaded into the controller in a following step 17 not visibly for the user the applications can be joined to one another and the C Code library binary can be downloaded. The C Code library can contain the interface description for application modules and either the source code of the runtime function or only the executable binary code binary of the runtime function . This is shown for example in .

In a last method step 18 the executable binary code C Code library binary can be linked in by the runtime system of the programmable logic controller D and the references to the FW API can be resolved or relocated. This is shown for example in .

The created application library can be added to the target project code PLC target project code Z of the programmable logic controller D in a step 25. In a next step 26 the C Code can be generated in the programming tool B for the target project to be executed on the programmable logic controller and the application module entities contained therein are implemented.

The target project can then be loaded from the programming tool B to the programmable logic controller D in a further step 28.

The application library with the application modules interface definition and the binary code generated from C Code can be reused advantageously in other projects without the source code files being needed.

All POUs can now be implemented in the languages C Code or according to IEC61131 3 and share the global variables . This can provide direct access to the system resources such as inputs and or outputs or the memories of the devices connected to the programmable logic controller and although there is programming in a high level language for example C Code the programming world now only appears as IEC 61131 3 programming system for the user.

Due to the high level language C Code used too the corresponding firmware application program interfaces API can be called up by utilizing the system libraries the functions of the system libraries including header files can also be available to the C Code programming.

Thus it will be appreciated by those skilled in the art that the present invention can be embodied in other specific forms without departing from the spirit or essential characteristics thereof. The presently disclosed embodiments are therefore considered in all respects to be illustrative and not restricted. The scope of the invention is indicated by the appended claims rather than the foregoing description and all changes that come within the meaning and range and equivalence thereof are intended to be embraced therein.

