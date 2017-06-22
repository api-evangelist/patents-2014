---

title: Image correlation method and electronic device thereof
abstract: Provided is an image correlation method, including establishing and saving correlation relationship for a plurality of image class files to form a correlation image group, displaying image class files of the formed correlation image group on a same page in a combined manner according to the correlation relationship, receiving, in the combined display state, a user's operation instruction for any one image class file of the correlation image group, and separately performing a corresponding operation on the any one image class file according to the operation instruction.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09396572&OS=09396572&RS=09396572
owner: Samsung Electronics Co., Ltd
number: 09396572
owner_city: 
owner_country: KR
publication_date: 20140609
---
This application claims priority under 35 U.S.C. 119 a to a Chinese Patent Application filed in the State Intellectual Property Office on Jun. 9 2013 and assigned Serial No. CN201310232011.8 the contents of which are incorporated herein by reference.

The present invention relates generally to terminal technology and more particularly to an image correlation method and electronic device thereof.

In an existing image management and display mode each image as a separate file is managed displayed and shared. For two or more images that have some correlation when a user needs to browse and use these images the user needs to perform search view and corresponding operations on each image respectively and share each image respectively. This mode prevents the user from establishing a relationship between images having correlation. In the conventional art the management and display of images is inefficient and the user needs to perform repeated operations. When the images are shared to a network peer for saving the images the images are saved step by step which is cumbersome and detrimentally affects the experience.

The present invention has been made to address at least the above mentioned problems and or disadvantages and to provide at least the advantages described below. Accordingly an aspect of the present invention is to provide an image correlation method which can improve efficiency of image management and display.

According to an aspect of the present invention an image correlation method includes establishing and saving a correlation relationship for a plurality of image class files to form a correlation image group displaying combined image class files of the formed correlation image group on a same page according to the correlation relationship and receiving in the combined display state a user s operation instruction for any one image class file of the correlation image group and separately performing a corresponding operation on the any one image class file according to the operation instruction wherein the image class file includes at least one of an image and a correlation image group and wherein the correlation relationship is used to record file information and display position information of each image class file of the correlation image group.

According to another aspect of the present invention an electronic device includes a display and at least one processor operatively coupled to the display the processor configured to perform operations comprising establishing and saving a correlation relationship for a plurality of image class files to form a correlation image group displaying image class files of the formed correlation image group on a same page according to the correlation relationship receiving in the combined display state a user s operation instruction for any one image class file of the correlation image group and separately performing a corresponding operation on the any one image class file according to the operation instruction.

Hereinafter various embodiments of the present invention will be described with reference to the accompanying drawings. Like reference numerals or symbols refer to like elements or components that substantially perform the same function throughout. Detailed descriptions of well known functions and structures incorporated herein may be omitted to avoid obscuring the subject matter of the present invention.

Although terms like first and second may be used to describe various components the components are not limited to these terms which are used only to distinguish one component from other components. For example a first component may be referred to as a second component and vice versa without being departing from the scope of the present invention. As used herein the term and or includes any and all combinations of one or more of the associated listed items.

The term application refers to software executable on a computer Operating System OS or a mobile OS by a user directly. Examples of such applications include a word processor application spread sheet application Social Network System SNS application chatting application map application music player application and video player application.

A magnetic substance refers to a material having magnetism for example a material magnetized in a magnetic field. The magnetic substance includes a ferromagnetic substance a paramagnetic substance a diamagnetic substance or a ferromagnetic substance. The magnetic substance may be included in a speaker a motor a hard disk drive Magnetic Resonance Imaging MRI a cover including magnetic substance to couple to a portable device or a portable device. A portable device according to an embodiment of the present invention includes one or more magnetic substances.

A widget refers to a mini application of a Graphic User Interface GUI for smoothly supporting an interaction between a user and an application or OS. For example widgets include a weather widget a calculator widget and a clock widget. The widget may be installed in a shortcut icon form to a desktop a portable device a blog an Internet caf or a personal homepage and may be used to directly execute a corresponding service by a click instead of a web browser. Additionally the widget includes a shortcut icon for a designated path or a shortcut icon for executing a designated application.

Terms used in this specification are used for describing specific embodiments and are not intended to limit the scope of the present invention. The terms of a singular form include plural forms unless referred to in the contrary. For example a user may be a user of a portable device or a user of an external device. A user may be one or two users. The meaning of include comprise including or comprising specifies a property a region a fixed number a step a process an element and or a component but does not exclude other properties regions fixed numbers steps processes elements and or components. Like reference numerals refer to like elements throughout.

An electronic device according to various embodiments of the present invention may be one or combination of one or more of various devices which include a smart phone a tablet Personal Computer PC a mobile phone a video phone an e book reader a desktop PC a laptop PC a netbook computer a Personal Digital Assistant PDA a Portable Multimedia Player PMP a Moving Picture Experts Group MPEG layer 3 MP3 player a mobile medical device an electronic bracelet an electronic necklace electronic accessories a camera a wearable device an electronic watch a wristwatch smart home appliances e.g. a refrigerator an air conditioner a cleaner a cybot a TeleVision TV a Digital Versatile Disc DVD player an audio an oven a microwave oven a washing machine an air cleaner and an electronic picture frame various medical devices e.g. a Magnetic Resonance Artery MRA a Magnetic Resonance Imaging MRI a CT Computed Tomography an imaging apparatus and a ultrasonic machine a navigation device a Global Positioning System GPS receiver an Event Data Recorder EDR a Flight Data Recorder FDR a set top box a TV box e.g. Samsung HomeSync Apple TV or Google TV an electronic dictionary a car infotainment device electronic equipment for ship e.g. a navigation device for ship and a gyrocompass an air electronic device a security device electronic clothes an electronic key a camcorder a game console a Head Mounted Display HMD a flat panel display an electronic album a part of furniture or a building structure including a communication function an electronic board an electronic signature input device or a projector. It is obvious to a person skilled in the art that the electronic device according to various embodiments of the present invention is not limited to the above described devices.

Referring to the electronic device denoted by includes a bus a processor a memory a user input module a display module or a communication module .

The bus is a circuit that connects components e.g. the processor the memory the user input module the display module or the communication module included in the electronic device with each other and transmits communication e.g. a control message between the components.

The processor receives commands from the components included in the electronic device through the bus decode the received commands and perform calculation or data processing according to the decoded commands.

The memory stores commands or data received from the processor or other components e.g. the user input module the display module and the communication module or generated by the processor or other components.

The memory includes at least one programming module including a kernel a middleware an Application Programming Interface API and an application . Herein at least the one programming module may be software firmware hardware or combination of at least two or more of software firmware and hardware.

The kernel controls or manages system resources e.g. the bus the processor or the memory used to execute an operation or function implemented in the other programming modules e.g. the middleware the API or the application . The kernel may provide an interface that may access a separate component of the electronic device in the middleware the API or the application and control or manage the separate component.

The middleware operates as a go between such that the API or the application communicates with the kernel and transmits and receives data. The middleware performs load balancing for work requests using a method of assigning priority that uses a system resource the bus the processor or the memory of the electronic device to the work requests received from at least the one application .

The API is an interface in which the application controls a function provided from the kernel or the middleware . The API includes at least one interface or function for file control window control image processing or text control.

The user input module receives commands or data from the user and transmits the received commands or data to the processor or the memory through the bus .

The communication module performs communication between the electronic device and other electronic devices and . Herein the communication module may support a local area communication protocol e.g. Wireless Fidelity Wi Fi BlueTooth BT Near Field Communication NFC or network communication e.g. the Internet a Local Area Network LAN a Wide Area Network WAN a telecommunication network a cellular network a satellite network or a Plain Old Telephone Service POTS .

Each of the other electronic devices and may be the same type as the electronic device or different than the electronic device .

As described above the image class file includes images and or correlation image groups. The formed correlation image group includes various image class files and corresponding correlation relationship. The correlation relationship is to record file information and display position information of each image class file of the correlation image group. When one image class file that has been correlated and includes a correlation image group file information of this image class file recorded in the correlation relationship can be correlation relationship information of the correlation image group.

In step according to the correlation relationship established in step image class files of the formed correlation image group are displayed on the same page in a combined manner.

In step in combined display state a user s operation instruction is received for any one image class file of the correlation image group and a corresponding operation is separately performed on the corresponding image class file according to the operation instruction.

In the process shown in the image correlation method of the present invention mainly includes establishment of the correlation relationship change and deletion of the correlation relationship combined display of image class files and operations of the image class files in combined display state. In addition the image correlation method of the present invention can further include sharing of the correlation image group.

Herein a configuration file is established corresponding to a correlation image group to store a correlation relationship. Establishing a configuration file for a corresponding correlation image group will be taken as an example for illustration.

In the image correlation method of the present invention a correlation relationship can be saved in file format. In this embodiment recording a correlation relationship in a correlation configuration file will be taken as an example to explain establishment and saving of the correlation relationship.

Specifically a correlation configuration file is established for a correlation image group to be formed. The correlation configuration file includes various image class files of the correlation image group to be formed file information and display position information of each image class file after having been correlated.

In addition considering the possibility of multi level correlation the correlation configuration file can further include a correlation identifier which indicates each image class file of the correlation image group formed to be an image or a correlation image group. Specifically the correlation identifier can be recorded in binary form and binary digits can be determined by the number of files that have been correlated. For example when two image class files are correlated the correlation identifier can be two digits. Each digit indicates one corresponding image class file to be an image or a correlation image group. If two image files are correlated the correlation identifier can be recorded as 00 in binary form. If one image and another correlation image group are correlated then the correlation identifier can be recorded as 01 in binary form.

For an image its file information can include file name and path information of a corresponding image. For a correlation image group i.e. multi level correlation its file information can include file name and path information of a configuration file corresponding to the correlation image group.

The correlation configuration file can also store display position information of each image class file that can be used to indicate specific display position for each image class file during combined display. More specifically the correlation configuration file can further include display layout and display effect.

When establishing a correlation relationship it is also necessary to determine for which image class files to establish a correlation relationship. One embodiment of the present invention provides three modes Correlation shooting mode user instruction mode and system recommending mode. The following will take correlating images as an example for illustration.

The correlation shooting mode refers to design shooting manners of a camera in a mobile terminal which helps to automatically correlate several taken images when a user takes pictures.

Specifically a correlation shooting mode can be set in a terminal device in advance and the system automatically generates a correlation configuration file that records a correlation relationship. A plurality of pictures successively taken by the user in the correlation shooting mode can be recorded in the correlation configuration file with identified correlation relationship thereby forming a group of correlated pictures. After the user manually exits the correlation shooting mode the correlation shooting ends and pictures taken hereafter will not be added into the correlation image group. The specific operation steps will be explained with reference to the following two examples.

1. The user selects the correlation shooting mode a configuration file that records correlation relationship is created within the system and default correlation display and control manner in the configuration file are selected 

2. The user continuously takes two pictures the system records file attributes including file names and file paths of the two pictures in the correlation configuration file created in step 1 and identifies correlation relationship 

4. The system stores the configuration file created in step 1 determines a correlation relationship between the two pictures taken in step 2 records a correlation identifier as 00 in the correlation configuration file distributes the two pictures according to the default correlation display and displays the pictures.

The pictures taken in the correlation shooting mode can adopt any combined display manner of the present invention. is only an example of adopting an overlapping display.

A user takes new pictures on an existing image and correlates the new pictures with the existing image as shown in .

2. The user selects correlation image and the system creates a correlation configuration file of this image information of this image including file name and file path is recorded in the correlation configuration file 

4. Starting camera function of a terminal and taking a picture of a building at the current position and

The system records file information including file name and file path of the taken picture in the correlation configuration file created in step 2. The system adds a correlation identifier of this picture and the image of step 1 in the correlation configuration file and the correlation identifier is 00. The system sets a default correlation display layout and control manner in the configuration file. The system saves the correlation configuration file and establishes correlation relationship between the screenshot file of step 1 and the new picture taken in step 4 thereby forming a correlation image group.

The system displays the correlated screenshot image and the new picture taken in step 4. The display layout and control select the default settings. provides an example of adopting a correlation overlapping display.

According to the user s instruction a plurality of image class files selected by the user in a terminal device can be correlated. As shown in steps that the user selects two images in a gallery to establish a correlation relationship include 

1. The user selects one image in the gallery and clicks correlation image button or selects correlation image function in a menu. The system automatically establishes a correlation configuration file of this image and records file information including for example file name and file path of this image in the correlation configuration file.

2. The user selects one or more images needed to be correlated. The system records file name and file path of the selected one or more images in the configuration file established in step 1 and establishes a correlation identifier of all image files of step 1 and step 2. Default settings such as default correlation layout and correlation manipulation can be added in the configuration file. A correlation relationship between the image of step 1 and the one or more images selected in step 2 has been established.

3. According to the setting of the correlation layout and correlation manipulation in the configuration file the system correlated displays the above correlated images.

The user can also directly perform step 2 and step 3 i.e. selecting several images needed to be correlated in the gallery to perform image correlation.

According to detection of image properties the correlation system recommends images to be correlated with an image specified by the user. The user selects images from the recommended images for correlation and determines to correlate the image specified by the user with the images selected by the user.

Steps that the user selects recommending correlation function in the gallery to establish image correlation relationship are as follows 

1. The user selects one image in the gallery and clicks recommending correlation button or selects recommending correlation function in a menu 

2. The mobile terminal shows three recommending modes including image matching GPS matching and time matching for the user to choose and

3. After the user makes a selection according to the mode selected by the user the mobile terminal displays top N matching images for the user to choose.

When the system recommends images according to the detection of image properties through the three modes such as image matching GPS matching and time matching the system can recommend a plurality of logically related images for the user to choose whether to establish a correlation relationship. The three matching modes will be described as follows 

The system filters images having similar features from the gallery through the image recognition technology and recommends the filtered images to the user for correlation.

For example as shown in a plurality of pictures contain a same character portrait through the image recognition technology the system recognizes that four images in the following figure contain human face information of the same character and displays the four images to the user so as to recommend the four images for the user to perform correlation. If the user determines to correlate the four images the system automatically establishes a configuration file and records in the configuration file file names and file paths of the four images that are recommended by the system and determined by the user as shown in .

A correlation identifier of the above four images image display layout after correlation can be the default display layout and can be custom set by the user and control manner of the images after correlation can be the default control manner and can be custom set by the user. After establishment and saving of the correlation configuration file setting of the correlation is ended and the correlation relationship recommended by the system is established. The four images in can be correlated displayed and controlled.

In another example shown in through the image recognition technology the system recognizes that four images shown in have similar feature points i.e. a pagoda shown in . In this embodiment the image correlation system displays the four images to the user as recommended correlated images. If the user determines to correlate the four images the system automatically establishes A correlation relationship. The process of establishing a correlation relationship is consistent with the process of the above example shown in .

The image correlation system compares GPS information in properties of all image files of the gallery and centralized displays image files having consistent GPS information to the user and recommends the user to correlate the images obtained through comparison and having consistent GPS information. For example as shown in the image correlation system centralized displays the four image files having the same GPS information i.e. gps pagoda scenic and recommends the user to perform correlation. If the user determines to correlate the four images the system automatically establishes a correlation configuration file.

In the correlation configuration file file information such as file names and file paths of the four images correlation identifier 0000 default correlation display layout template and correlation manipulation manner are recorded. The system saves the correlation configuration file the correlation relationship is established for the four images and the four images can be correlated displayed and controlled.

Through comparing shooting time attributes of all picture files the image correlation system can recommend images to the user and an interval between a shooting time of each recommended image and the image specified by the user is less than a threshold. The criteria of the time threshold can be set by the user.

For example as shown in for pictures taken at one party the user can set one hour as the time threshold. The image correlation system can recommend to the user following images taken within one hour from the shooting time of the image specified by the user for example images having a shooting time in from 2013 01 01 19 01 to 2013 01 01 20 01 will be recommend for correlation. If the user confirms the recommended correlation relationship the image correlation system centralized displays the recommended correlated image files. The system automatically establishes a correlation relationship for the images shown in . The process of establishing a correlation relationship for the recommended images is consistent with the process of establishing a correlation relationship shown in .

In the above processes of establishing a correlation relationship the single level correlation is taken as an example for establishing a correlation relationship for a plurality of images. As mentioned above in the present invention multi level correlation can also be established i.e. establishing a correlation relationship for an image and a correlation image group or establishing a correlation relationship for a plurality of the correlation image groups. The establishment of the multi level correlation relationship will be simply introduced below.

As shown in a correlation relationship is established for the first group photo image and an individual photo of one character and a second level correlation relationship is established for the individual photo and another business card photo. Thus this example establishes a two level correlation relationship.

2. The system records a file name and file path of a picture 1 shown in in the correlation configuration file and records ID of a correlation configuration file of the second correlated image shown in in the correlation configuration file of the . This correlation is a correlation between one image file and a correlation image group 

3. The system records a correlation identifier in the correlation configuration file and the correlation identifier can be set as a binary code 01 which identifies the correlation relationship to be a correlation between one image and one correlation image group 

4. The system records default display layout in the configuration file for example the second correlated image is hidden on the first image shown in in the display layout a hidden identifier can be established to identify that the correlated image is hidden displayed. Position coordinates of a color block which is shown in and is to identify hidden are also recorded in the display layout information of the configuration file and

The system saves the above established correlation configuration file and the multi level correlation relationship shown in is established.

After the establishment of the correlation relationship the user s deletion instruction for any one image class file of the correlation image group can be received and the file information and the display position information of this image class file can be deleted from the correlation relationship. When the correlation relationship saves the file information and the display position information of only one image class file after confirmation by the user corresponding correlation relationship can be deleted.

Alternatively the user s changing instruction for any one image class file of the correlation image group can be received the file information and the display position information of corresponding image class file can be deleted from the correlation relationship and file information and display position information of a changed image class file specified by the user can be added into the correlation relationship.

2. The user selects one image needed to be changed or deleted after long pressing options changing image and delete image appear as shown in and 

3. As shown in the user selects delete image then the system deletes information such as file name and file path et al. of this image from the correlation configuration file and deletes the correlation identifier. The image selected by the user for deletion will be deleted from the correlation relationship and the correlation relationship for the two images is terminated. If the user chooses an operation of saving the image deleted then the system deletes the correlation configuration file and original image will become an independent image file without correlation relationship and

4. As shown in if the user selects change image then the system enters into the process of selecting corrected images to perform steps in B 1 2 so as to establish a correlation relationship with the selected new image the system records file name and file path of the newly selected correlated image in the correlation configuration file and establishes a new correlation identifier. The system correlated displays the newly established correlation image group.

Usually two display modes including independent display mode and correlation display mode can be provided for a terminal device to display images. After the independent display mode is activated the gallery shows independent image files and correlation image groups having established correlation relationship are not shown. When the correlation display mode is activated the gallery shows various correlation image groups having established relationship currently in the system. Through the user s click one correlation image group can be selected and displayed on the terminal device.

In the correlation display mode after receiving the user s instruction of displaying correlation image group for example the user clicks a thumbnail to send a display instruction the present invention discloses how to display the correlation image group on a display screen of the terminal device.

Specifically a variety of display templates can be set in advance in the system for the use of the user. The user can set a display layout of images after correlation by selecting one display template or using a default template in the system and can also create a customized correlation display layout and customize a correlation display template. The set display layout is stored in the correlation relationship. In this manner when displaying the correlation image group the image class files of the correlation image group can be correlated displayed according to the display layout stored in the correlation relationship. For example several correlation display templates are shown in .

The user can select one template as a default display layout when creating the correlation relationship and establishing the correlation configuration file of the correlation image group the default template of the correlation display and control information can be recorded in the correlation configuration file as a default display layout. The display template records an identifier of a hidden displaying image location information of a displayed image and supported control. If the user selects a new correlation layout after the images have been correlated the system updates the display layout information of the correlation configuration file and records the new correlation layout.

The above description is specific processing of the correlation image group for combined displaying. In the combined displaying state an operation instruction corresponding to each correlation image file can also be received and the image file can be separately operated. The general operation instruction can include position sliding scaling hiding display and or double click for example.

In order to perform separate operation of each image class file of the correlation image group a valid range of each image class file can be stored in the correlation relationship. In this manner after one operation instruction is detected in the valid range corresponding to one image class file this detected operation instruction is treated as an operation instruction of the corresponding image class file.

Considering the possibility of multi level correlation when one correlated image class file is a correlation image group the process of separately performing a corresponding operation on the correlation image group according to an operation instruction includes performing in the combined displaying state a corresponding operation on all images that are of corresponding correlation image group and taken as a whole.

The display and operation processes of the correlation image group will be explained hereinafter with reference to examples of performing correlation display and operation on two images and a plurality of images respectively.

As shown in a first picture of two correlated images can be displayed by using a first template in . The control of the correlated images includes position sliding scaling double click and hiding of the images for example.

As shown in for a touch screen mobile phone user the user can select one correlated image needed to be sided and freely drag the selected image to different positions. The user can also use one or more fingers to perform scaling control of one image needed to be enlarged or shrunk.

When a received user instruction is position sliding a corresponding image class file can be displayed on an indicated position according to the operation instruction. After confirmation of the user and the end of the position sliding instruction the current position information of the corresponding image class file can be stored in the correlation relationship.

When a received user instruction is scaling operation display size of all images of corresponding image class file can be adjusted according to the operation instruction. After confirmation by the user the current display size of the corresponding image class file that has been adjusted can be stored in the correlation relationship.

One example of double click operation of one image of the correlation image group is shown in . When the user double clicks on one of overlapping displayed images the clicked image is displayed in the maximized state. When the user double clicks on the image again the image is restored and displayed in an overlapping display layout of thumbnails.

For hiding or display operation of one image of the correlation image group a corresponding hide identifier can be stored in advance for each image class file in the correlation relationship e.g. correlation display layout . In the combined display state according to the hide identifier corresponding to each image class file it is determined whether to display corresponding image class file. When receiving the user s hide operation instruction for one image class file the corresponding image class file is hidden according to the instruction. After confirmation by the user the hide identifier corresponding to the corresponding image class file can be recorded as hidden. When receiving the user s display operation instruction for one image class file the corresponding image class file is displayed according to the instruction in the combined display state. After confirmation by the user the hide identifier corresponding to the corresponding image class file can be recorded as a display.

Specifically the user can realize hiding and display operations of correlated images through two types of operations. In a first type the user long presses one image needed to be hidden until a hidden image option appears thereby realizing hidden of the correlate image. In a second type as shown in the user can perform a shrink operation by using two fingers to slide inwardly from diagonal positions of one image. When the image is shrunk to a certain extent the image is hidden and a button appears. After the user clicks the hide button the hidden image is restored and is displayed.

After the hide operation is completed and saved the system can record a hide identifier in the display layout information of the correlation configuration file.

Through the foregoing the user can re adjust the display layout and display an effect of the correlated images through a variety of operation instructions. The user can select a save operation so that the new layout the hide identifier of display effect and display position information of images can be stored in display layout information of a correlation configuration file that records this correlation relationship.

Examples of displaying and operating of two correlation image groups each formed by a plurality of correlated images are given in as described below. For example in a group photo of persons who joined in a party business card images of some persons in the group photo can be correlated.

1. Assuming that a first picture of is a group photo of persons who joined in a party long pressing one position of the photo until an add correlation image option shown in appears 

2. The user selects one business card image of one person who joined the party from the gallery and confirms correlation 

3. Repeating steps 1 and 2 so as to establish a correlation relationship for the group photo and the business card images of several persons who joined the party 

4. Selecting one display template for correlating a plurality of photos for example a display temple which hides a plurality of correlated images as shown in 

5. The display effect of a plurality of correlated images is shown in and the user can click the hide button to restore the hidden correlated images and

6. The user can drag the hide button so as to place the hide button near a character portrait requiring correlation.

The correlation image group established through the manner of the above steps 1 3 can also use a transparent area of a display template 7 in to perform hidden displaying. The displaying effect of hiding and restoring correlation is shown in as described below.

After establishment of the above correlation relationship for a plurality of images following correlation controls can be performed 

2. Hiding correlated images after hiding the button can also be moved on the correlated group photo and

Example 2 of correlating a plurality of photos is shown in a plurality of party photos taken during a party can be centrally saved as a theme album.

2. The user selects a correlation display template for example template 8 of a template of overlapping display of a plurality of images and

1. Manual click paging manipulation Clicking on a lower right edge of a photo to perform paging down manipulation and clicking on a paging margin at an upper left corner to perform paging up manipulation and

2. Automatic paging play The user can select a automatic paging play mode to view a plurality of correlated photos.

As shown in example 3 of correlating a plurality of photos can use a display template 9 of the multi level correlation link of . The correlation image group in this display template has multi level correlations in which each level image group can be hidden in a correlated correlation image group.

The correlation image group formed according to the image correlation method provided in the present invention can be socially shared. Specifically each image class file of the correlation image group and corresponding correlation relationship can be bound together and shared on the network or shared with other terminal devices. When an established correlation image group is a multi level correlation it is necessary to bind all image class files and each correlation configuration file together for sharing. In a specific binding manner each corresponding file can be packaged into the form of a packet.

Specifically the sharing of correlated images can be divided into two forms. One of the forms is based on an application program which supports the function of correlating images of the present invention and can directly parse and display a shared correlation image data packet. Another form is to compress through common data sharing manner data information of the correlated images into a data package and transmit the data package to a sharing peer. If the sharing peer does not install an application program which supports the image correlation technology of the present invention the sharing peer can directly obtain correlated image files from the compressed package and display and save each image file contained in the correlation data package respectively.

Examples of sharing a correlation image group and specific operation of a sharing peer on the correlation image group are as follows.

1. As shown in selecting a correlation image group needed to be shared clicking on a share button and selecting to share the correlation image group to sina microblogging . as an example assuming that sina microblogging has used the image correlation method of the present invention 

2. As shown in display layout and effect of the correlated images shown in a microblogging client and operations of the correlated images are consistent with those of the user s particular machine and

3. If the user selects to share the correlation image group to a friend the user can directly share the correlation image group by selecting a phone number or QQ instant messaging number of the friend.

The sharing peer can save the shared correlation image group from a social network client such as microblogging client. As shown in the user can select to directly save the correlation image group and can also separately save a single image of the correlation image group.

When the user selects save correlation image the entire correlation image group including all correlated image files and the correlation configuration file containing four elements such as file information of correlated images correlation identifiers correlation display layout and effect of correlated images and manipulation of correlated images can be simultaneously saved in a local file system of the sharing peer.

When the user selects save images respectively the selected single image file can be saved in the local file system of the sharing peer.

When the sharing peer supports the image correlation method of the present invention the peer end device reads and parses information of the correlation configuration file to find corresponding class file picture resources and performs combined displaying according to information of the configuration file. In this manner the same display effect of the correlation image group as that of the sharing end can be seen as shown in .

When establishing a correlation image group in the sharing end the correlation relationship stored in the correlation configuration can be described by using XML language and saved in the form of HTML pages. In this manner even if the sharing peer does not support the image correlation method of the present invention a built in HTML browser toolbar of the sharing peer device can be used to view combined display content after correlation but the present invention is not limited to performing editing and saving operations on the correlation image group.

The above are examples of the image correlation method of the present invention. Through the above manners using the stored correlation relationship to perform combined display of the various image class files of the correlation image group a plurality of image specified by the user can be simultaneously displayed which improves operational efficiency of the user to browse two or more images and does not require an additional saving of a combined display image after correlation which conserves system resources. In the combined displaying state each image class file of the correlation image group can be operated separately which increases operational flexibility.

Methods according to embodiments described in claims and or a specification of the present invention may be implemented in a form of hardware software or a combination thereof.

When implemented with software a computer readable storage medium that stores at least one program software module may be provided. At least one program stored at a computer readable storage medium is formed to execute by at least one processor within an electronic device. At least one program includes an instruction that enables the electronic device to execute methods according to embodiments described in claims and or a specification of the present invention.

Such a program software module software may be stored at a non volatile memory including a Random Access Memory RAM a flash memory a Read Only Memory ROM an Electrically Erasable and Programmable ROM EEPROM a magnetic disk storage device a Compact Disk ROM CD ROM a Digital Versatile Disk DVD or an optical storage device of other form and a magnetic cassette. Alternatively the program may be stored at a memory. Each constituent memory may be included in plural.

While the present invention has been particularly shown and described with reference to embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present invention as defined by the appended claims.

