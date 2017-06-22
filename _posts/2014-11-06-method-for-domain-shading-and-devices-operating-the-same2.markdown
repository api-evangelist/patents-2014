---

title: Method for domain shading, and devices operating the same
abstract: A method for domain shading may include analyzing graphics state data, and generating all first primitives through a single-pass domain shading or generating only second primitives which are visible among the first primitives through a two-pass domain shading based on a result of the analysis.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09552618&OS=09552618&RS=09552618
owner: SAMSUNG ELECTRONICS CO., LTD.
number: 09552618
owner_city: Gyeonggi-do
owner_country: KR
publication_date: 20141106
---
This application claims priority under 35 U.S.C. 119 a from Korean Patent Application No. 10 2013 0140915 filed on Nov. 19 2013 the disclosure of which is hereby incorporated by reference in its entirety.

A graphics processing unit GPU renders an image of an object to be displayed on a display. In recent years the GPU performs a tessellation operation so as to more minutely render the image of an object during a process of rendering the image of an object.

The GPU generates a plurality of primitives for the image of an object through the tessellation operation receives information for generating the plurality of primitives from an external memory and transmits the finally generated primitives to a next step or stores the primitives in the external memory. The GPU obtains all data corresponding to the plurality of primitives so as to perform an operation after the tessellation operation thereby causing a waste of bandwidth of data and a large amount of calculation loads and power consumption.

An embodiment of the present inventive concepts is directed to a method for domain shading including analyzing graphics state data and generating all first primitives through a single pass domain shading according to a result of the analysis or generating only second primitives which are visible among the first primitives through a two pass domain shading.

According to an example embodiment when a number of attributes to be generated for each of the first primitives is smaller than a set value all of the attributes of the first primitives may be calculated through the single pass domain shading and the first primitives may be generated according to a result of the calculation. According to another example embodiment when a blending operation is activated all attributes of the first primitives may be calculated through the single pass domain shading and the first primitives may be generated according to a result of the calculation.

According to still another example embodiment when a range of two dimensional space coordinates of the first primitives is not maintained through a location modification calculation performed by a geometry shader all attributes of the first primitives may be calculated through the single pass domain shading and the first primitives may be generated according to a result of the calculation.

According to still another example embodiment when relative depth values between the first primitives are not maintained through a depth modification calculation after the first primitives are processed by a geometry shader all attributes of the first primitives may be calculated through the single pass domain shading and the first primitives may be generated according to a result of the calculation.

According to still another example embodiment when i a number of the attributes to be generated for each of the first primitives is greater than or equal to a set value ii a blending operation is not activated iii a range of two dimensional space coordinates of the first primitives is maintained through a location modification calculation performed by a geometry shader and iv relative depth values between the first primitives are maintained all the time after the geometry shader then i only location attributes may be first calculated among the attributes of the first primitives ii third primitives which are invisible among the first primitives may be removed iii the rest attributes other than location attributes of the second primitives may be calculated and iv the second primitives may be generated according to a result of the calculation.

The analysis may be performed by a central processing unit CPU or a graphics processing unit GPU . The depth modification calculation may be performed by the geometry shader or a pixel shader.

An example embodiment of the present inventive concepts is directed to a graphics processing unit including a control logic which analyzes graphics state data and is configured to control a domain shading according to a result of the analysis and a domain shader. The domain shader includes a first domain shader which calculates space coordinates included in first primitives using data output from a hull shader and tessellation data output from a tessellator a primitive assembler which generates first primitives having only location attributes using the calculated space coordinates a primitive culling unit which removes primitives that are invisible among the first primitives having location attributes only and generates only second primitives that are visible and a second domain shader which calculates the rest attributes other than the location attributes of the second primitives. The domain shader generates all of the first primitives through a single pass domain shading and generates the second primitives through a two pass domain shading according to a control of the control logic.

According to an example embodiment the control logic may be configured to control the domain shader so that the domain shader may perform the single pass domain shading when a number of attributes to be generated for each of the first primitives is smaller than a set value. According to still another example embodiment the control logic may be configured to control the domain shader so that the domain shader may perform the single pass domain shading when a blending operation is activated.

According to still another example embodiment the control logic may be configured to control the domain shader so that the domain shader may perform the single pass domain shading when a range of two dimensional space coordinates of the first primitives is not maintained through location modification calculation performed by the geometry shader.

According to still another example embodiment the control logic may be configured to control the domain shader so that the domain shader may perform the single pass domain shading when relative depth values between the first primitives are not maintained through a depth modification calculation after the first primitives are processed by the geometry shader.

According to still another example embodiment when a number of attributes to be generated for each of the first primitives is greater than or equal to a set value a blending operation is not activated a range of two dimensional space coordinates of the first primitives is maintained through a location modification operation performed by the geometry shader and relative depth values among the first primitives are always maintained after the geometry shader then the control logic may be configured to control the domain shader so that the domain shader may perform the two pass domain shading.

An example embodiment of the present inventive concepts is directed to a system on chip including the graphic processing unit and a CPU which controls the graphic processing unit.

The present inventive concepts now will be described more fully hereinafter with reference to the accompanying drawings in which embodiments of the invention are shown. This invention may however be embodied in many different forms and should not be construed as limited to the embodiments set forth herein. Rather these embodiments are provided so that this disclosure will be thorough and complete and will fully convey the scope of the invention to those skilled in the art. In the drawings the size and relative sizes of layers and regions may be exaggerated for clarity. Like numbers refer to like elements throughout.

It will be understood that when an element is referred to as being connected or coupled to another element it can be directly connected or coupled to the other element or intervening elements may be present. In contrast when an element is referred to as being directly connected or directly coupled to another element there are no intervening elements present. As used herein the term and or includes any and all combinations of one or more of the associated listed items and may be abbreviated as .

It will be understood that although the terms first second etc. may be used herein to describe various elements these elements should not be limited by these terms. These terms are only used to distinguish one element from another. For example a first signal could be termed a second signal and similarly a second signal could be termed a first signal without departing from the teachings of the disclosure.

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the invention. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises and or comprising or includes and or including when used in this specification specify the presence of stated features regions integers steps operations elements and or components but do not preclude the presence or addition of one or more other features regions integers steps operations elements components and or groups thereof.

Unless otherwise defined all terms including technical and scientific terms used herein have the same meaning as commonly understood by one of ordinary skill in the art to which this invention belongs. It will be further understood that terms such as those defined in commonly used dictionaries should be interpreted as having a meaning that is consistent with their meaning in the context of the relevant art and or the present application and will not be interpreted in an idealized or overly formal sense unless expressly so defined herein.

The portable electronic device may be embodied as a laptop computer a mobile phone a smart phone a tablet PC a mobile internet device MID a wearable computer a personal digital assistant PDA an enterprise digital assistant EDA a digital still camera a digital video camera a portable multimedia player PMP a personal navigation device or portable navigation device PND a handheld game console an internet of things IoT device an internet of everything IoE device or an e book.

The data processing device may control the external memory and or the display . That is the data processing device may entirely control an operation of the data processing system . The data processing device may be embodied as a printed circuit board PCB such as a motherboard an integrated circuit IC or a system on chip SoC . For example the data processing device may be an application processor.

The data processing device may include a central processing unit CPU a read only memory ROM a random access memory RAM a display controller a memory interface and a graphics processing unit GPU . According to an example embodiment the data processing device may further include a graphics memory not shown which stores data to be used in the GPU .

The CPU may control an entire operation of the data processing device . For example the CPU may control a ROM a RAM a display controller a memory interface and or the GPU through a bus .

The CPU may read and perform program instructions. For example the CPU may perform an application e.g. a 3D application or a 3D game application.

The 3D application or the 3D game application may output 3D application programming interface API commands. In order to render 3D computer graphics according to the 3D API commands 3D API e.g. OpenGL or Direct3D used in applications may be executed.

For example the 3D API stored in a memory or may be loaded to the GPU and performed according to a control of the CPU . According to an example embodiment the CPU may be embodied in a multi core. The multi core may be a computing component having two or more independent cores.

The ROM may permanently store programs and or data. According to an example embodiment the ROM may be embodied in an erasable programmable read only memory EPROM or an electrically erasable programmable read only memory EEPROM .

The RAM may temporarily store data instructions and or programs or program modules needed in the CPU or the GPU . For example programs and or data stored in a memory or may be temporarily stored in the RAM according to a control of the CPU a control of the GPU or a booting code stored in the ROM .

The RAM may store an operating system OS application programs other program modules and or program data. According to an example embodiment the RAM may be embodied as a dynamic RAM DRAM or a static RAM SRAM .

The GPU may effectively perform an operation related to computer graphics processing according to a control of the CPU . The GPU is an example of a graphics processor including a graphics pipeline.

According to some example embodiments the GPU may analyze graphics state or status data and control a domain shader so that the domain shader may generate all first primitives through a single pass domain shading or generate only second primitives which are visible among the first primitives through a two pass domain shading according to a result of the analysis.

According to some example embodiments the CPU may analyze graphics state data generate a control signal according to a result of the analysis and transmit the generated control signal to the GPU . Here the GPU may control a domain shading e.g. a single pass domain shading or a two pass domain shading of a domain shader in response to the control signal.

The display controller may control an operation of the display . For example the display controller may transmit image data output from the external memory e.g. still image data moving image data 3D image data or stereoscopic 3D image data to the display .

For example the display controller may support an MIPI display serial interface or an embedded Display Port eDP .

The memory interface may perform a function of a memory controller which may access the memory . For example the data processing device e.g. the CPU and or the GPU may communicate with the external memory through the memory interface . That is the CPU and or the GPU may transmit or receive data to from the external memory through the memory interface .

The external memory may store an operating system OS application programs other program modules and or program data. According to a control of the CPU an OS application programs other program modules and or program data stored in the external memory may be loaded to the RAM .

A 3D application a 3D game application or software or API which may perform the method for domain shading described in the inventive concept which is stored in the external memory may be loaded from the external memory to the RAM .

The external memory may be embodied as a volatile memory or a non volatile memory. The volatile memory may be embodied as a dynamic random access memory DRAM a static random access memory SRAM a thyristor RAM T RAM a zero capacitor RAM Z RAM or a Twin Transistor RAM TTRAM .

The non volatile memory device may be embodied as an Electrically Erasable Programmable Read Only Memory EEPROM a flash memory a Magnetic RAM MRAM a Spin Transfer Torque STT MRAM a Conductive bridging RAM CBRAM a Ferroelectric RAM FeRAM a Phase change RAM PRAM a Resistive RAM RRAM a Nanotube RRAM a Polyumer RAM PoRAM a Nano Floating Gate Memory NFGM a holographic memory a Molecular Electronics Memory Device or an Insulator Resistance Change Memory.

According to some example embodiments the external memory may be embodied as a hard disk drive HDD or a solid state drive SSD . According to some example embodiments the external memory may be embodied as a removable storage media or a non removable storage media. For example the external memory may be embodied as a secure digital SD card a multimedia card MMC a universal flash storage UFS an embedded multimedia card eMMC or a USB flash drive.

The display may display an image corresponding to image data output from the display controller . For example the display may be embodied in a touch screen a liquid crystal display LCD a thin film transistor liquid crystal display TFT LCD a liquid emitting diode LED display an organic LED OLED display an active matrix OLED AMOLED display or flexible display.

The GPU may include a control logic a vertex shader a hull shader a tessellator a domain shader a geometry shader a rasterizer a pixel shader and an output merger .

A function and an operation of the components and except the control logic and a domain shader of the GPU in which a technical concepts of the present embodiment is included may be substantially the same as a function and an operation included in a graphics pipeline of Microsoft Direct3D . Therefore detailed description of the components and of the GPU will be omitted.

Moreover each function of the hull shader the tessellator and the domain shader may be substantially the same as each function of a tessellation control shader of Khronos OpenGL 4.0 a tessellation primitive generation and a tessellation evaluation shader.

The control logic may control an entire operation of the GPU . For example the control logic may control an operation of each component and . The control logic may analyze graphics state data G DATA transmitted from the CPU and control a domain shading of the domain shader according to a result of the analysis. The control logic may be embodied in hardware or a circuit.

For example the control logic may analyze graphics state data G DATA generate a control signal CTRL or CTRL corresponding to a result of the analysis and transmit the generated control signal CTRL or CTRL to the domain shader .

The graphics state data G DATA may include data for an output structure of each component and and or data for a program or a shading program .

The program may include a vertex shader program a hull shader program a tessellator program a domain shader program a geometry shader program a rasterizer program a pixel shader program and or an output merger program.

The domain shader may generate all first primitives PR through the single pass domain shading or generate second primitives PR which are visible among the first primitives PR through the two pass domain shading in response to a control of the control logic i.e. the control signal CTRL or CTRL.

The control logic may analyze the number of attributes to be generated for each of the first primitives PR from the domain shader output structure included in the graphics state data G DATA. For example when the number of attributes to be generated for each of the first primitives PT is smaller than a set or reference value the control logic may generate a first control signal CTRL so that the domain shader may perform the single pass domain shading.

For example the attributes to be generated may include attributes such as a position a color a diffuse color a normal vector a tangent vector a bitangent vector or a binormal vector a texture coordinate and or a world coordinate. The attributes to be generated may further include user defined values.

According to an example embodiment the set value may be set or programmed from outside. According to another example embodiment the set value may be set or programmed by the CPU .

The control logic may analyze whether to activate a blending operation according to a shading program included in the graphics state data G DATA. For example when the blending operation is activated the control logic may generate the first control signal CTRL so that the domain shader may perform the single pass domain shading.

The control logic may analyze each depth value of the first primitives PR through a depth modification calculation according to a shading program included in the graphics state data G DATA.

For example when relative depth values between the first primitives PR are not maintained through the depth modification calculation the control logic may generate the first control signal CTRL so that the domain shader may perform the single pass domain shading. According to an example embodiment the depth modification calculation may be performed by the geometry shader and or the pixel shader .

When a range of two dimensional space coordinates of the first primitives PR is not maintained through a location modification calculation performed by the geometry shader the control logic may generate the first control signal CTRL so that the domain shader may perform the single pass domain shading.

When i the number of attributes to be generated for each of the first primitives PR is greater than or equal to a set value ii the blending operation is not activated iii the range of two dimensional space coordinates is maintained through the position modification calculation performed in the geometry shader and iv relative depth values between the first primitives PR are maintained all the time after the first primitives PR are processed by the geometry shader the control logic may generate a second control signal CTRL so that the domain shader may perform a two pass domain shading.

In addition the domain shader A may generate only second primitives PR which are visible among the first primitives PR through the two pass domain shading in response to the second control signal CTRL. For example the domain shader A may calculate first location attributes only among the attributes of the first primitives PR remove third primitives which are invisible among the first primitives PR according to the calculated location attributes and calculate the rest attributes other than the location attributes of the second primitives PR.

The domain shader A may include the first domain shader the primitive culling unit and the second domain shader . The domain shader A illustrated in is an example embodiment of the domain shader illustrated in .

The first domain shader may receive point data P DATA and patch constant data PCD output from the hull shader and tessellation data T DATA output from the tessellator . The point data P DATA may be attribute data of each point e.g. vertex and or control point included in a patch. The attribute data may include data on attributes of each point such as location color normal vector and or texture coordinate.

The patch constant data PCD may include a tessellation factor or tessellation factors coefficients related to a patch equation and or user defined values. For example the tessellation factor may mean a level of detail LOD . The tessellation factor may be an integer a decimal fraction or a floating point.

The patch equation may be a curve equation or a surface equation. For example the curve equation may be a Hermite curve equation a Bezier curve equation a NURBS curve equation or a B spline curve equation.

The tessellation data T DATA may include UV coordinates or UVW coordinates of tessellated points of a patch and topology information on the tessellated points. The topology information may include connectivity information of each of the tessellated points.

The first domain shader operating in response to a first control signal CTRL may calculate all attributes of each of the first primitives PR such as points lines and triangles using the point data P DATA the patch constant data PCD and the tessellation data T DATA and generate the first primitives PR according to a result of the calculation. For example the first domain shader may calculate all attributes of each point e.g. vertex and or control point included in each of the first primitives PR to be generated based on the point data P DATA the patch constant data PCD and the tessellation data T DATA.

The first domain shader may generate the first primitives PR based on all of the calculated attributes. Each of the primitive culling unit and the second domain shader may bypass the first primitives PR in response to the first control signal CTRL. The domain shader A may generate all of the first primitives PR through a single pass domain shading only using the first domain shader .

The first domain shader may receive the point data P DATA and the patch constant data PCD output from the hull shader and the tessellation data T DATA output from the tessellator .

The first domain shader operating in response to the second control signal CTRL may calculate only a location or a position attribute e.g. space coordinate of each point e.g. vertex and or control point included in each of the first primitives PR using the point data P DATA the patch constant data PCD and the tessellation data T DATA. For example the space coordinates may be defined by x y z .

The first domain shader may generate the first primitives PR only having location attributes using the calculated space coordinates.

The primitive culling unit may remove the third primitives which are invisible among the first primitives only having location attributes in response to the second control signal CTRL. That is the primitive culling unit may remove the third primitives which are unnecessary and generate only the second primitives PR which are visible. For example the primitive culling unit may compare a location attribute e.g. space coordinate of the first primitive with a location attribute of the second primitive.

When a range of two dimensional coordinates of the second primitive is included in the range of two dimensional coordinates e.g. an x axis and y axis coordinate of the first primitive and a depth coordinate e.g. a z axis coordinate of the first primitive is smaller than a depth coordinate of the second primitive the primitive culling unit may determine that the first primitive is a visible primitive and the second primitive is an invisible primitive and remove the second primitive according to a result of the determination. According to an example embodiment the primitive culling unit may remove invisible primitive s using a view frustum culling an occlusion culling or a back face culling.

The primitive culling unit may output each point OCP included in each of the second primitives PR to the second domain shader .

The second domain shader may calculate the rest attributes other than the location attributes of the second primitives PR. For example the second domain shader may calculate the rest attributes other than the location attribute of each point OCP included in each of the second primitives PR and generate the second primitives PR according to a result of the calculation.

The domain shader A may generate second primitives PR which are visible among the first primitives PR through the two pass domain shading using the first domain shader the primitive culling unit and the second domain shader . The domain shader A may remove unnecessary primitives on a primitive basis and calculate only the remaining primitives thereby decreasing unnecessary amount of workload and or unnecessary data. In addition the domain shader A may reduce power consumption caused by the unnecessary amount of workload. Accordingly an entire performance of the GPU may be improved and power consumption of the GPU may be reduced.

Referring to a domain shader B may include the first domain shader the primitive culling unit the second domain shader and a primitive assembler .

Except for an operation of the primitive assembler the operation of the domain shader A illustrated in is substantially the same as an operation of the domain shader B illustrated in .

As illustrated in the domain shader B may generate all of the first primitives PR through the single pass domain shading which uses only the first shader in response to the first control signal CTRL. As illustrated in the domain shader B may generate only second primitives PR which are visible among the first primitives PR through the two pass domain shading in response to the second control signal CTRL.

As illustrated in the first domain shader may calculate a location attribute e.g. space coordinate of each point included in each of the first primitives PR using the point data P DATA the patch constant data PCD and the tessellation data T DATA in response to the second control signal CTRL. For example the space coordinate may be defined by x y z .

The first domain shader may transmit the space coordinate calculated for each point included in each of the first primitives PR to the primitive assembler .

The primitive assembler may generate the first primitives PR only having location attributes using the calculated space coordinate. For next processing the generated first primitives PR may be supplied to the primitive culling unit . That is the primitive culling unit may remove third primitives which are invisible among the first primitives PR only having location attributes and generate only the second primitives PR which are visible.

An operation of the primitive culling unit and the second domain shader of the domain shader B illustrated in may be substantially the same as an operation of the primitive culling unit and the second domain shader illustrated in .

The data processing device may generate all of the first primitives PR through a single pass domain shading or generate only second primitives which are visible through the two pass domain shading according to a result of the analysis S .

A method for domain shading and or devices performing the same according to an example embodiment of the present inventive concepts may perform a single pass domain shading or a two pass domain shading according to a result of the analysis of graphics state data.

The method and the devices may remove unnecessary primitives on a primitive basis through the two pass domain shading and calculate only the remaining primitives thereby decreasing an amount of workload. Accordingly according to the decrease in the amount of workload an entire performance of a graphics processing unit may be improved and power consumption of the graphics processing unit may be reduced.

Although a few embodiments of the present general inventive concepts have been shown and described it will be appreciated by those skilled in the art that changes may be made in these embodiments without departing from the principles and spirit of the general inventive concept the scope of which is defined in the appended claims and their equivalents.

