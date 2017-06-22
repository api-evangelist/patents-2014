---

title: Control systems for repetitive printing
abstract: Complicating programs installed on a control device, and wasting recording media, are suppressed. A registration device driver that generates and outputs control commands instructing registering a static image in an inkjet printer based on input of information related to a static image from an application AP, and a device control driver that generates and outputs a control command to print the static image registered in the inkjet printer superimposed with the variable image based on input of information related to the variable image from an application, are installed on a host computer. An application calls the device driver appropriate to the process.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09069492&OS=09069492&RS=09069492
owner: Seiko Epson Corporation
number: 09069492
owner_city: Suwa-shi
owner_country: JP
publication_date: 20140522
---
Priority is claimed under 35 U.S.C. 119 from Japanese patent application nos. JP 2013 107949 filed on May 22 2013 and JP 2014 044069 filed on Mar. 6 2014 which are hereby incorporated by reference in their entirety.

The present disclosure relates to a control device that connects to a printer capable of printing labels repeatedly and to a control system including the control device and the printer.

Printing devices label printers that repeatedly print images on recording media while conveying the recording medium label paper are known from the literature. See for example JP A 2007 136913.

One type of recording medium commonly used in such printers is label paper having multiple labels of a specific size affixed with a constant gap therebetween to a continuous liner. The printer repeatedly prints images on consecutive labels. The label paper may also be preprinted with a static image such as an image forming a border on the label that is the same on each label.

When using label paper with a fixed imaged preprinted on each label label paper that was already produced with the fixed image may be wasted when the fixed image is changed due to a design change for example. The label paper may also be frequently replaced in order to print different labels preprinted with a different static image.

The printer is also usually connected to a control device and repeatedly prints images to the recording medium as controlled by the control device. A program that generates control commands conforming to the command language of the printer is also installed on the control device and the control device controls the printer using a function of the program.

Suppressing the complexity of the program that gets installed to the control device is also desirable.

At least one embodiment of the present invention suppresses waste and the need to replace the recording medium and suppresses complicating the program installed to the control device.

One aspect of at least one embodiment of the present invention is a control device connected to a printing device capable of repeatedly printing an image on recording media. The image includes a variable image that can be changed in each repeatedly printed image and a static image that is the same in each repeatedly printed image. The control device includes a registration device driver execution unit that runs a registration device driver with the ability to instruct registering the static image on the printing device and a device control driver execution unit that runs a device control driver with the ability to instruct printing the variable image superimposed with the static image registered in the printing device. The registration device driver execution unit generates and outputs to the printing device a control command instructing registering the static image based on input of information related to the static image and the device control driver execution unit generates and outputs to the printing device a control command instructing printing the variable image superimposed with the static image registered in the printing device based on input of information related to the variable image.

In this aspect of the invention the control device can repeatedly send information related to the variable image to the printing device after registering the static image in the printing device superimpose the registered static image with each variable image and print label images continuously. As a result there is no need to preprint label paper or other recording medium with a static image recording media is not destroyed when there is a design change in the static image for example and recording media waste can be suppressed. The need to frequently replace the recording medium can also be suppressed.

The control device in this configuration also has a registration device driver execution unit that executes a process related to registering the static image by a function of the registration device driver and a device control driver execution unit that executes a process related to controlling image printing by a function of the device control driver.

A configuration in which the function for registering a static image and the function controlling printing are both embodied in a single device driver is conceivable. In this event the device driver must be configured so that either function can be selectively executed by changing the mode and the application or other program that calls the device driver must be configured so that the device driver mode can be changed by applying an appropriate command to the device driver. As a result the program that calls the device driver must be specifically programmed according to the specifications of the device driver and the device driver must be programmed specifically for the application. In other words programming becomes increasingly complex.

In this aspect of the invention the control device can simply call the registration device driver to register a static image and call the device control driver to print. More specifically by changing the device driver that is called a static image can be registered and images printed while not complicating programming.

In a control device according to another aspect of at least one embodiment of the present invention the registration device driver execution unit generates and outputs a control command instructing registering the static image in the printing device based on input of information related to the static image from a specific program and the device control driver execution unit generates and outputs to the printing device a control command instructing printing the variable image superimposed with the static image registered in the printing device based on input of information related to the variable image from the specific program.

In another aspect of at least one embodiment of the present invention the specific program is an application capable of outputting information related to an image to print on a recording medium.

In another aspect of at least one embodiment of the present invention the specific program is an application programming interface API that is called by an application and handles data input output between the application and a device driver.

When the control device repeatedly prints the image on the recording medium in another aspect of at least one embodiment of the present invention the registration device driver execution unit is called by the specific program and generates and outputs to the printing device a control command instructing registering the static image in the printing device based on input of information related to the static image from the specific program and the device control driver execution unit is called by the specific program and generates and outputs to the printing device a control command instructing printing the variable image superimposed with the static image registered in the printing device based on input of information related to the variable image from the specific program.

In this aspect of the invention the registration device driver and the device control driver cooperate without human intervention and can automatically register the static image and repeatedly print label images using the registered static image and user convenience is excellent.

In a control device according to another aspect of at least one embodiment of the present invention the control device provides a user interface to select the registration device driver and the device control driver when repeatedly printing images on the recording medium.

This aspect of the invention enables accurately identifying the registration device driver and device control driver for the application.

Another aspect of at least one embodiment of the present invention is a control system comprising a printing device capable of repeatedly printing an image on recording media and a control device connected to the printing device wherein the image includes a variable image that can be changed in each repeatedly printed image and a static image that is the same in each repeatedly printed image the control device includes a registration device driver execution unit that runs a registration device driver with the ability to instruct registering the static image on the printing device and generates and outputs to the printing device a control command instructing registering the static image based on input of information related to the static image and a device control driver execution unit that runs a device control driver with the ability to instruct printing the variable image superimposed with the static image registered in the printing device and generates and outputs to the printing device a control command instructing printing the variable image superimposed with the static image registered in the printing device based on input of information related to the variable image and the printing device includes a control unit that registers the static image based on a control command instructing registering the static image and prints the registered static image superimposed with the variable image on the recording medium when a control command instructing printing the static image superimposed with the variable image is received.

This aspect of the invention can reduce recording media waste reduce replacing the recording medium and prevent complicating programming.

In a control system according to another aspect of at least one embodiment of the present invention the registration device driver execution unit generates and outputs a control command instructing registering the static image in the printing device based on input of information related to the static image from a specific program and the device control driver execution unit generates and outputs to the printing device a control command instructing printing the variable image superimposed with the static image registered in the printing device based on input of information related to the variable image from the specific program.

Some embodiments of the present invention are described below with reference to the accompanying figures.

The inkjet printer is an inkjet printer that prints images on label paper by ejecting ink from an inkjet head onto the label paper while conveying the label paper recording medium in the forward feed direction YJ conveyance direction by a conveyance roller .

The inkjet printer can at least record images on label paper used as an example of the recording medium.

As shown in the label paper is a continuous sheet with multiple labels S affixed with a specific gap therebetween on the printing side of the liner. The part corresponding to each label S is an adhesive seal and can be peeled along its edges from the liner. The length of each label S along the length of the liner is constant and the gap between each label S is also constant. As described below the inkjet printer prints an image in each of the labels S affixed to the label paper .

When the inkjet printer prints on the label paper the label paper is set in the inkjet printer so that the length of the label paper is aligned with the forward conveyance direction YJ and specific images are appropriately printed on the labels S as the label paper is conveyed in the forward conveyance direction YJ.

As shown in a black mark BM is formed on the back side of the label paper at reference positions corresponding to the labels S. While not shown in a black mark sensor that optically detects the black marks BM formed on the conveyed label paper is disposed to a specific position on the label paper conveyance path in the inkjet printer . Based on the output of the black mark sensor the inkjet printer detects when a black mark BM reaches the position of the sensor. The inkjet printer also adjusts the position of the label paper and adjusts the media conveyance process based on sensor output.

As shown in the inkjet printer is an inkjet line printer and has an upstream head unit and a downstream head unit .

The upstream head unit has three staggered printheads upstream top printhead T upstream left printhead L and upstream right printhead R. The downstream head unit similarly has three staggered recording heads downstream top printhead T downstream left printhead L and downstream right printhead R.

A black nozzle row and a cyan nozzle row disposed downstream from the black nozzle row are disposed to the upstream top printhead T.

The black nozzle row is a nozzle row having nozzles not shown that eject ink as fine ink droplets formed in the nozzle row direction YJ which is perpendicular to the forward conveyance direction YJ. Ink is supplied to the black nozzle row from a black K ink cartridge not shown . The upstream top printhead T pushes ink supplied from the black K ink cartridge by an actuator such as a piezoelectric device toward the label paper ejecting fine ink droplets from specific nozzles.

Similarly to the black nozzle row the cyan nozzle row is a nozzle row of nozzles formed in the nozzle row direction and has ink supplied from a cyan C ink cartridge not shown .

The upstream right printhead R and the upstream left printhead L are configured identically to the upstream top printhead T and each has a black nozzle row and a cyan nozzle row disposed on the downstream side of the black nozzle row .

A magenta nozzle row and a yellow nozzle row located downstream from the magenta nozzle row are disposed to the downstream top printhead T.

Like the black nozzle row the magenta nozzle row is a row of nozzles formed in the nozzle row direction and has ink supplied from a magenta M ink cartridge not shown .

Like the black nozzle row the yellow nozzle row is also a row of nozzles formed in the nozzle row direction and has ink supplied from a yellow Y ink cartridge not shown .

The downstream right printhead R and downstream left printhead L are configured identically to the downstream top printhead T and each has a magenta nozzle row and a yellow nozzle row disposed on the downstream side of the magenta nozzle row .

Note that the printheads and the nozzle rows of the recording heads are shown in for convenience of description but the recording heads are actually configured to eject ink vertically downward from the nozzles of the nozzle rows and other parts enabling this operation are also disposed.

The inkjet printer ejects ink and forms dots on the label paper and prints images by the combination of dots. The basic operation forming a single dot on the label paper is described below using .

Forming a dot of a specific color at a desired position P on the label paper when the label paper is set to the position shown in is described below. The specific color in this example is a color that is produced by ejecting specific amounts of black K cyan C magenta M and yellow Y ink. Position P in the inkjet printer is the position where position P on the conveyed recording medium passes the black nozzle row of the upstream top printhead T. Position P position P and position P are similar positions.

The inkjet printer conveys the label paper in the forward conveyance direction YJ at a substantially constant speed while forming dots on the label paper . Conveyance of the label paper in the forward conveyance direction YJ proceeds from the position shown in and the inkjet printer ejects a specific amount of black K ink from the nozzle corresponding to position P timed to position P on the label paper reaching the position corresponding to position P. The inkjet printer likewise ejects a specific amount of cyan C ink from the nozzle corresponding to position P timed to position P on the label paper reaching the position corresponding to position P ejects a specific amount of magenta M ink from the nozzle corresponding to position P timed to position P on the label paper reaching the position corresponding to position P and ejects a specific amount of yellow Y ink from the nozzle corresponding to position P timed to position P on the label paper reaching the position corresponding to position P.

Specific amounts of black K cyan C magenta M and yellow Y ink are thus ejected to position P on the label paper and a dot of a specific color is formed at position P.

With a inkjet printer according to some embodiments of the invention the position of the inkjet line head is fixed during the image printing process the label paper moves at a constant speed relative to the stationary inkjet line head ink is desirably ejected from the inkjet line head to form dots and an image is printed.

As shown in the printing system includes an inkjet printer and a host computer control device that can connect to the inkjet printer and controls the inkjet printer .

The printer control unit control unit of the inkjet printer controls other parts of the inkjet printer and includes a CPU as an operating unit firmware that can be run by the CPU ROM that nonvolatilely stores data related to the firmware RAM that temporarily stores the firmware executed by the CPU and data related to the firmware and other peripheral circuits.

The printer control unit prints an image on the label paper by driving the actuators of the inkjet head units of the inkjet line head and ejecting the required amount of ink from each of the appropriate nozzles. The printer control unit also drives a paper feed motor for driving the conveyance roller and moves the label paper a specific amount. The conveyance roller turns as the paper feed motor is driven and the recording medium is conveyed a specific amount in the forward conveyance direction YJ.

The paper feed motor is a stepper motor and the printer control unit can precisely control the paper feed distance based on the number of steps the paper feed motor is driven.

A black mark sensor optically reads the black marks BM formed on the label paper conveyed through the conveyance path and outputs the detected result to the printer control unit . The display unit has multiple LEDs and turns specific LEDs on off in specific patterns as controlled by the printer control unit to report inkjet printer status information or to report if an error occurred.

The printer input unit is connected to operating switches disposed to the inkjet printer detects operation of the switches and outputs to the printer control unit . The image buffer includes EEPROM a hard disk drive or other nonvolatile memory and nonvolatilely stores data rewritably. A communication interface communicates with the host computer according to a specific protocol as controlled by the printer control unit .

As shown in the host computer has a host control unit that controls other parts of the host computer . The host control unit has a print control unit and the print control unit includes a registration device driver execution unit and a device control driver execution unit as further described below.

The host computer also has a host display unit for displaying information a host input unit for detecting operation of the connected input devices a host storage unit for storing data and a communication interface for communicating with the inkjet printer .

Images can be repeatedly printed to the labels S of the label paper in the printing system according to this embodiment. Printing images on the labels S of the label paper is described more specifically below.

Each label image G includes a variable image G that may differ in each label image G and a static image G that is the same in every label image G.

In the example in the static image G is an image of a red border printed along the outside edge of the label S. The name of the television manufacturer AAA Company in this example is printed at a position along the top border of the label S. As shown in the example in the static image G printed on each label S is the same.

The variable image G is an image printed in the area surround by the border created by the static image G. The variable image G includes a string XX YYYY in the example in identifying the model of television a barcode representing a code assigned uniquely to each television and a string a five digit number in the example in representing an identification number uniquely assigned to each television. The printed barcode and identification number are different in each variable image G. The content of the variable image G is therefore different in each label image G.

Label paper Q as shown in is used in the conventional system to produce labels S with a label image G including the variable image G and the static image G.

As shown in the static image G is preprinted to the labels S on the conventional label paper Q. The conventional printer produces the label image G including the static image G and variable image G on each label S by simply printing the variable image G on each label S.

The following problems can occur in this event. Specifically the static image G is preprinted on the label paper Q. As a result when the design of the static image G changes label paper Q that was printed with the static image G used before the design change may be wasted. Alternatively the label paper may need to be frequently replaced depending upon the labels to be printed.

The printing system according to some embodiments of the invention solves this problem of the related art by executing the process described below with the configuration described below. More particularly the printing system according to some embodiments of the invention solves the problem of the related art without complicating the application AP described below and the device driver described below programs.

The application AP is a program with a function for outputting information related to images printed on the recording medium label paper in this embodiment by the inkjet printer .

As shown in two device drivers a registration device driver DD and a device control driver DD are installed on the host computer . These device drivers are separate independent device drivers. More specifically individual identification information is assigned with reference to the operating system OS to each device driver as identification information for recognizing the device driver. The application AP can call the device drivers using an API Application Programming Interface provided by the OS. Either registration device driver DD or device control driver DD can be selectively called when calling a device driver. Note that the API can be provided by the OS or a dedicated API with this function could be used.

The registration device driver execution unit is a function block that executes processes by reading and running the registration device driver DD. The device control driver execution unit is a function block that executes processes by reading and running the device control driver DD.

The application execution unit is a function block that executes processes by reading and running the application AP.

To print the label image G on the labels S of the label paper with the printing system the user first instructs displaying the dedicated user interface UI. In response to this command the application execution unit of the host control unit of the host computer displays the user interface UI on the display panel step SA .

As shown in the user interface UI has an input field R for selecting the folder location in a hierarchical storage area where image data for the static image G is stored and selecting the image data for the static image G in the selected folder. Using a tool provided by the application AP for example the user previously creates and stores the image data for the static image G in an appropriate folder. The user then uses the input field R in the user interface UI to select the storage location of the image data used for the static image G and select the desired image data.

A selection field R for selecting the device driver used to register the image data of the static image G in the inkjet printer is also disposed to the user interface UI. The selection field R in this embodiment is a pull down menu that enables selecting one device driver from a group of multiple device drivers. In this example the user selects the registration device driver DD labelled the device registration driver in in selection field R.

A selection field R for selecting the device driver used to print the label image G is also provided in the user interface UI. The selection field R is also a pull down menu and enables selecting one device driver from a group of multiple device drivers. In this example the user selects the device control driver DD labelled the device control driver in in selection field R.

After inputting the selections in the user interface UI and confirming the input the user instructs starting to print the label image G by a specific means.

As will be clear below when the user inputs selections to the user interface UI and instructs starting to print the image data for the static image G is registered and the label image G is repeatedly printed systematically without further human intervention.

Triggered by this command the application execution unit accesses the folder selected in the input field R of the user interface UI and retrieves the image data for the static image G step SA . Next the application execution unit calls the device driver selected in the selection field R of the user interface UI registration device driver DD in this example using the API step SA .

Next the application execution unit outputs the image data acquired for the static image G information related to a static image through a specific API to the registration device driver DD and instructs printing the static image G step SA . The application AP thus applies a print command using an existing API to the registration device driver DD when registering image data for the static image G in the inkjet printer in some embodiments of the invention. More specifically data can be communicated between the application AP and the registration device driver DD using an existing API and there is no need for a new specialized API for registering images.

When image data for the static image G is input the registration device driver execution unit generates a control command C including the image data of the static image G and instructing registering the image data step SA and outputs the control command C to the inkjet printer step SA .

More specifically the registration device driver DD is a device driver including a function for generating and outputting a control command C instructing registering image data for the static image G when a command to print the static image G is asserted by the application AP through the API.

The printer control unit of the inkjet printer then receives the control command C step SB and registers the static image G based on the control command C step SB .

More specifically when the control command C is received the printer control unit extracts the image data for the static image G from the command in step SB. The printer control unit then stores the extracted image data for the static image G to a specific area in working memory created in RAM. Storing the image data for the static image G in working memory in this embodiment is an example of registering image data for the static image G.

After outputting the control command C instructing registering image data for the static image G the application execution unit calls and runs the device control driver DD using the API step SA . Calling the device control driver DD in this embodiment thus occurs without further human intervention after outputting the control command C.

Next the host computer and inkjet printer execute respective continuous printing processes step SA step SB .

In the continuous printing process the application execution unit generates variable image related data which is information related to the variable image G that should be printed on a single label S step SC . The variable image related data is described below. As described above the variable image G in this embodiment includes an image related to a string representing the model name of the television product model string image below a barcode image of the barcode representing a code uniquely assigned to each television barcode image below and an image related to a string expressing the identification number uniquely assigned to each television identification number string image below . The variable image related data includes for each image at least information indicating where the image is to be printed information indicating the type of image string or barcode and information indicating the content of the image. The information indicating the content of the image is a string representing the model name for the model string image information indicating the barcode for the barcode image and the string representing the identification number for the identification number string image.

The model name printed on the label S is the same for each label S that is XX YYYY in this example. The code of the barcode is a serial number that is incremented 1 for each label S. The identification number is also a serial number that is incremented 1 for each label S. For example if the barcode encodes the code 00001 and the identification number is the string 00001 on one label S the barcode 00002 and the identification number string 00002 are printed on the next label S and the barcode 00003 and the identification number string 00003 are then printed on the next label S. The user previously registers the rules for changing the barcode code and the identification number through a specific user interface. Alternatively the user interface UI described could also be configured to enable inputting the rules and the user can then input the rules using the user interface UI.

In step SC the application execution unit calculates the barcode code and the identification number according to the rules registered by the user for changing the barcode and the identification number and then generates the variable image related data which is the information related to the variable image G to be printed on one label S.

Next the application execution unit outputs the generated variable image related data to the device control driver execution unit step SC .

Next the application execution unit determines if generating and outputting the variable image related data for all labels S to be printed with the label image G is completed step SC . If not completed step SC returns NO the application execution unit returns to step SC and generates the variable image related data for the variable image G to be printed on the next label S.

When variable image related data is input from the application execution unit the device control driver execution unit generates a control command C for superimposing the static image G and variable image G based on the input data step SD . Next the device control driver execution unit sends the generated control command C to the inkjet printer step SD .

Operation of the inkjet printer when this control command C is received operation during the continuous printing process in step SB is described next.

When the control command C is received the printer control unit of the inkjet printer writes the image data for the static image G stored in working memory to the print buffer not shown in the figure used for printing the label image G. Next the printer control unit generates image data for the variable image G based on the control command C and writes the generated image data to the print buffer. At this time the printer control unit writes the image data for the variable image G so that it merges with the image data for the static image G already written to the print buffer. As a result image data for a label image G containing both the static image G and the variable image G is compiled in the print buffer. Next the printer control unit controls the printing related mechanisms based on the image data written to the print buffer the image data for the label image G and prints the label image G on a label S. As a result a label image G combining the superimposed static image G and variable image G is printed on a label S.

As described above when printing a label image G in a printing system according to this embodiment a static image G and a variable image G are merged to print the label image G on each label S instead of using label paper that is previously printed with the static image G on each label S. As a result there is no need to destroy label paper and wasting label paper can be prevented even when the design of the static image G changes. Frequent replacement of the label paper can also be suppressed.

When printing a label image G on a label Sin this embodiment the following process is executed instead of the host computer sending a control command instructing printing a label image G containing the static image G and the variable image G to the inkjet printer . Specifically image data for the static image G is first registered in the inkjet printer in this embodiment. The inkjet printer then prints the static image G based on the previously stored registered image data for the static image G and based on the received control command C prints the variable image G superimposed with the static image G. As a result there is no need to send the image data for the static image G each time for each label S to print and the data size of the control command C can be reduced. Because the data size of the control command C is small efficient communication between the host computer and inkjet printer is possible and the receive buffer of the inkjet printer can effectively be prevented from overflowing.

The registration device driver DD and device control driver DD in this embodiment are separate device drivers.

A configuration in which the function for registering the static image G function corresponding to the registration device driver DD and the function controlling printing function corresponding to the device control driver DD are both embodied in a single device driver is conceivable. In this event the device driver must be configured so that either function can be executed by changing the mode and the application AP must be configured so that the device driver mode can be changed by asserting an appropriate command to the device driver. As a result the application AP must be specifically programmed according to the specifications of the device driver and the device driver must be programmed specifically for the application. Creating a special API may also be necessary. In other words both the application and the device driver can become increasingly complex.

In some embodiments of the invention however the registration device driver DD and the device control driver DD are separate device drivers. As a result the application AP can call the registration device driver DD to register a static image and can call the device control driver DD to print for example using an API provided by the OS. More specifically the application AP can register a static image G and print a label image G by changing the device driver that is called using an existing API and complicating the application AP and the device driver can be suppressed.

As described above a registration device driver DD and a device control driver DD are both installed to the host computer in the printing system control system according to some embodiments of the invention. The registration device driver DD has a function for generating and outputting a control command C instructing printing a static image G based on input of image data for the static image G from an application AP. The device control driver DD generates and outputs a control command C that controls printing a variable image G superimposed with the static image G based on input of information related to the variable image G from the application AP.

To repeatedly print the label image G to label paper the application execution unit calls the registration device driver DD and using a function of the driver generates and outputs the control command C to the inkjet printer . The application AP then calls the device control driver DD and through a function of this driver repeatedly executes a process of generating and sending control command C to the inkjet printer .

Based on the control command C the inkjet printer registers stores the static image G and when a control command C is then received prints the variable image G superimposed with the registered static image G on a label S of the label paper based on the control command C.

With this configuration there is no need to destroy label paper and wasting label paper can be prevented even when the design of the static image G changes. Frequent replacement of the label paper can also be suppressed.

This configuration also enables the application AP to register a static image G and print an image by changing the device driver using an existing API as described above and complicating the application AP and device driver can be prevented.

When a label image G is repeatedly printed on label paper in this embodiment the application execution unit first calls the registration device driver DD and using a function of the device driver registers the static image G in the inkjet printer . Next the application AP calls the device control driver DD and using a function of the device driver repeatedly executes a process of generating and outputting a control command C instructing printing the static image G registered in the inkjet printer superimposed with a variable image G.

The application AP registration device driver DD and device control driver DD cooperate in this configuration without human intervention to automatically repeatedly print the label image G and user convenience is excellent.

Some embodiments of the invention also provide a user interface UI for selecting the registration device driver DD and the device control driver DD for repeatedly printing label images G on label paper .

This configuration enables accurately specifying the registration device driver DD and the device control driver DD for the application AP.

The application AP in the above embodiment calls a registration device driver DD and a device control driver DD. In the example described below the API calls these device drivers to execute a process.

While not shown in the figures the host control unit in this example also has an API execution unit as a function block that executes a process by reading and running an API.

As shown in A to print the label image G repeatedly the user first commands displaying the user interface UI. The application execution unit then displays the user interface UI on the display panel step SE .

As described above the user interface UI enables selecting where the image data for the static image G is stored the device driver for registering the image data and the device driver that controls printing. The user interface UI could also be configured to enable inputting the rules related to the variable image G.

In this example the user selects the registration device driver DD as the device driver for registering image data and the device control driver DD as the device driver for controlling printing.

The application execution unit then calls a specific API corresponding API below step SE and outputs the information input to the user interface UI to the corresponding API step SE .

Next the API execution unit outputs information including the information identifying the storage location of the image data for the static image G to the registration device driver DD step SF .

As shown in C the registration device driver execution unit generates and sends a control command C instructing registering the image data for the static image G to the inkjet printer step SG .

As shown in E the printer control unit of the inkjet printer registers the static image G based on the control command C when the control command is received step SI .

Next the API execution unit outputs information required for the continuous printing process including the rules related to the variable image G to the device control driver DD step SF .

AS shown in D and E the device control driver execution unit and the inkjet printer execute the continuous printing process step SH step SI .

Some embodiments of the invention can therefore achieve the same effect as the embodiment described above when the API calls the device driver for registering image data and the device driver for controlling printing to execute a continuous process. The API that calls the registration device driver DD could also be an API supplied by the operating system.

Some embodiments of the invention are described above with reference to a preferred embodiment thereof but some embodiments of the invention are not limited thereto and can be modified and adapted in many ways without departing from the scope of the accompanying claims.

For example the configuration of the label image G shown in is only an example. More specifically the label image G conceptually includes any image combining a static image G and a variable image G. In the foregoing embodiments the variable image G is an image of content that changes according to specific rules of change and the rules of change are not limited to those described above. The image data of the variable image G could also be prepared in advance for each label S.

The function blocks shown in can also be desirably achieved by the cooperation of hardware and software and do not suggest a specific hardware configuration. Functions of the host computer and inkjet printer could also be rendered by separate devices externally connected thereto. The host computer and inkjet printer could also operate as described above by executing a program stored to an externally connected storage medium.

The disclosure being thus described it will be apparent that it may be varied in many ways. Such variations are not to be regarded as a departure from the spirit and scope of the disclosure and all such modifications as would be apparent to one skilled in the art are intended to be included within the scope of the following claims.

