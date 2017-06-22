---

title: Data generating apparatus, data generating method, and non-transitory storage medium
abstract: The numbers of pages making up respective records are acquired as individual page counts by analyzing page description data used for variable data printing. The maximum page count among the acquired individual page counts is determined as a common page count. Imposition data representing a common and single page layout made up of the determined common page count are generated.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09626606&OS=09626606&RS=09626606
owner: FUJIFILM Corporation
number: 09626606
owner_city: Minato-Ku, Tokyo
owner_country: JP
publication_date: 20140612
---
This application is based upon and claims the benefit of priority from Japanese Patent Application No. 2013 126297 filed on Jun. 17 2013 the contents of which are incorporated herein by reference.

The present invention relates to a data generating apparatus a data generating method and a non transitory storage medium for generating imposition data suitable for variable data printing.

Recently the work flow of printing processes has been digitized as a whole because of the widespread use of DTP DeskTop Publishing and CTP Computer To Plate processes in the printing field. In particular various technologies about variable data printing have been proposed in the art as a process of efficiently producing a plurality of productions e.g. the detailed statements of charges on bills which share certain contents information.

Japanese Laid Open Patent Publication No. 2007 130947 discloses a method of and an apparatus for generating control data for variable data printing hereinafter referred to as data for variable data printing by duplicating and correcting page editing data that represent one layout unit.

A record that serves as a printing unit for data for variable data printing may be made up of not only a single page but also a plurality of pages. Further even in one set of data for variable data printing a different number of pages can be set depending on a record.

The method and apparatus disclosed in Japanese Laid Open Patent Publication No. 2007 130947 do not take into account the above editing procedure for data for variable data printing. In order to deal with complex page arrangements page layouts for records may be saved and managed altogether. However the amount of page layout data thus saved and managed is so large that such a data handling is not preferable from the standpoint of data management and processing.

It is an object of the present invention to provide a data generating apparatus a data generating method and a non transitory storage medium which are capable of generating imposition data suitable for variable data printing highly efficiently from the standpoint of data management and processing.

According to the present invention there is provided a data generating apparatus including an individual page count acquirer for acquiring as individual page counts the numbers of pages making up respective records by analyzing page description data used for variable data printing a common page count determiner for determining as a common page count the maximum page count among the individual page counts acquired by the individual page count acquirer and an imposition data generator for generating imposition data representing a common and single page layout made up of the common page count determined by the common page count determiner.

Since the maximum page count among the individual page counts is determined as a common page count and the imposition data representing a common and single page layout made up of the common page count are generated it is enough to handle an amount of data corresponding to one record and the imposition data for variable data printing can be generated highly efficiently from the standpoint of data management and processing.

The imposition data generator should preferably generate the imposition data by inserting blank pages into the respective records to make up for lacking pages in a case where the individual page counts are smaller than the common page count.

The imposition data generator should preferably generate the imposition data that indicate the page layout of a plurality of signatures.

The data generating apparatus should preferably further include a sheet count calculator for calculating a minimum number of sheets by which each of the records can be printed based on the number of pages assigned to one sheet the total number of records and the common page count.

According to the present invention there is also provided a data generating method for enabling a computer to perform the steps of acquiring as individual page counts the numbers of pages making up respective records by analyzing page description data used for variable data printing determining as a common page count the maximum page count among the acquired individual page counts and generating imposition data representing a common and single page layout made up of the determined common page count.

The step of generating should preferably generate the imposition data by inserting blank pages into the respective records to make up for lacking pages in a case where the individual page counts are smaller than the common page count.

The step of generating should preferably generate the imposition data that indicate the page layout of a plurality of signatures.

The data generating method should preferably further include the step of calculating a minimum number of sheets by which each of the records can be printed based on the number of pages assigned to one sheet the total number of records and the common page count.

According to the present invention there is further provided a non transitory storage medium storing a program for enabling a computer to perform the steps of acquiring as individual page counts the numbers of pages making up respective records by analyzing page description data used for variable data printing determining as a common page count the maximum page count among the acquired individual page counts and generating imposition data representing a common and single page layout made up of the determined common page count.

With the data generating apparatus the data generating method and the non transitory storage medium according to the present invention since the maximum page count among the individual page counts is determined as a common page count and the imposition data representing a common and single page layout made up of the common page count are generated it is enough to handle an amount of data corresponding to one record and the imposition data for variable data printing can be generated highly efficiently from the standpoint of data management and processing.

The above and other objects features and advantages of the present invention will become more apparent from the following description when taken in conjunction with the accompanying drawings in which a preferred embodiment of the present invention is shown by way of illustrative example.

A data generating method according to a preferred embodiment of the present invention in relation to a data generating apparatus and a non transitory storage medium that stores a data generating program for performing the data generating method will be described in detail below with reference to the accompanying drawings.

As shown in the print production system includes a router serving as a relay device for connection to a network a server which is accessible through the network from terminal devices not shown belonging to external networks a DTP terminal for performing DTP DeskTop Publishing process including an editing process on data acquired from the server etc. an imposition apparatus for imposing contents data processed by the DTP terminal an RIP apparatus for performing various image processing processes including a rasterizing process a color conversion process etc. based on output data imposed by the imposition apparatus a proof press for printing a proof based on proofread data sent from the RIP apparatus and a digital printing press for producing a print based on platemaking data sent from the RIP apparatus .

The server is an apparatus that plays a central role in the workflow management in the print production system . The server is connected to various terminal devices of at least one of designers and production companies not shown for communication therewith through the router and the network . The server is also connected to the DTP terminal the imposition apparatus and the RIP apparatus for communication therewith through a LAN Local Area Network constructed in the print production system .

Specifically the server is capable of performing a function as a file server for storing and transferring various data files a function as an authorization management server for managing task authorizations that are available for terminals users or print jobs and a function as a mail server for generating and distributing notification mails at certain times such as process starting and ending times.

The data files that can be managed by the server as the file server include contents data printing data e.g. platemaking data printing plate data or proofread data job tickets e.g. JDF Job Definition Format files ICC International Color Consortium profiles color sample data etc.

The DTP terminal generates image data per page from contents data representing characters figures patterns pictures etc. which have been processed by a preflight process. The imposition apparatus performs an imposing process according to a binding process and a page folding process which have been designated by referring to the tag information of a job ticket.

The RIP apparatus functions as a printing processing server for at least one type of printing press. In the RIP apparatus is connected to the proof press and the digital printing press for communication therewith. The RIP apparatus converts data expressed in a page description language PDL hereinafter referred to as page description data into output data suitable for output devices and supplies the output data to the proof press or the digital printing press .

The proof press prints a proof having images on a proof sheet not shown based on the proofread data supplied from the RIP apparatus . The proof press may comprise a DDCP Direct Digital Color Proofer an ink jet color proofer a low resolution color laser printer electrophotographic printer an ink jet printer or the like.

The digital printing press produces a print which has images printed on a print medium without producing intermediate products such as printing plates or the like so called direct printing . The digital printing press may comprise an ink jet printing press a wide format printing press an ink jet color proofer a color laser printer or the like.

The communication I F is an interface I F for sending electric signals to and receiving electric signals from external apparatus. Thus the imposition apparatus can acquire various data e.g. PDF VT data from the server through the communication I F and can supply various data e.g. imposition data to the server .

The display controller comprises a control circuit for controlling the display unit under the control of the controller . Specifically the display controller outputs a display control signal via an I F not shown to the display unit whereby the display unit is energized to display various images including a window W1 and a window W2 .

The input unit comprises various input devices including a mouse a trackball a keyboard a touch sensor etc. The display function of the display unit and the input function of the input unit are combined into a user interface.

The memory stores programs and data which are required for the controller to control various components. In the memory stores page description data in a PDF VT format hereinafter referred to as PDF VT data and imposition data in a JDF.

The memory may comprise a non transitory computer readable storage medium. The computer readable storage medium comprises a portable medium such as a magnetooptic disk a ROM a CD ROM a flash memory or the like or a storage device such as a hard disk or the like incorporated in a computer system. The storage medium also may comprise a medium for dynamically holding programs for a short period of time or a medium for holding programs for a certain period of time.

The controller comprises a processor such as a CPU Central Processing Unit . The controller reads and executes programs stored in the memory to perform the functions of a variable data printing setter a display data generator and an imposition data generator .

The variable data printing setter sets various parameters about variable data printing. Specifically the variable data printing setter includes an individual page count acquirer for acquiring the numbers of pages i.e. the page counts making up respective records hereinafter referred to as individual page counts a common page count determiner for determining a number of common pages or a common page count from the respective individual page counts and a sheet count calculator for calculating a number of sheets or a sheet count suitable for cut and stack.

The display data generator has an editing mode acquirer for acquiring a present editing mode and a screen generator for generating display data for a job editing screen etc. . The display data may comprise image data generated by application software or may comprise various parameters for utilizing an API Application Programming Interface function provided by basic software.

The imposition data generator generates imposition data on which the contents of settings made by the variable data printing setter are reflected. As described later the imposition data are data representing a common and single page layout made up of the number of common pages.

PDF VT Portable Document Format Variable Transactional refers to an international standard for the handling of variable data transaction documents and is defined by ISO International Standard Organization 16612 2 2010.

The data structure also includes page layout information that stores a succession of 200 sheets which are numbered i.e. the sheet numbers of 1 to 200 each made up of 4 pages. On each sheet four types of pages are regularly assigned in the sequence 1 back B and right side R 2 face F and left side L 3 face F and right side R 4 back B and left side L .

The imposition apparatus according to the present embodiment is constructed as described above. Operation of the imposition apparatus shown in will be described in detail below primarily with reference to a flowchart shown in .

Prior to the operation sequence the imposition apparatus displays a job editing screen that is used to make settings for an imposing process. In response to an instruction to start making settings the screen generator generates display data for the job editing screen and then supplies the generated display data to the display controller . The display controller controls the display unit to display a window W1 including the job editing screen .

As shown in the job editing screen includes a first setting field a second setting field a third setting field a fourth setting field and a button group having buttons indicated as CANCEL and SAVE . The user of the imposition apparatus also referred to as the operator can operate the input unit to make various settings through the various setting fields.

The first setting field includes a button indicated as ADD in its upper area. The ADD button is clicked on whereby a data file to be imposed can be added. In an icon having a file name MobileBill.pdf is displayed in the first setting field .

The second setting field includes a button indicated as ADD in its upper area. The ADD button is clicked on whereby a page to be read can be added. In four thumbnails or more specifically a thumbnail representing a first page a thumbnail representing a second page a thumbnail representing a third page and a thumbnail representing a fourth page are displayed in the order named from above in the second setting field . The total number of pages 800 of the file MobileBill.pdf is displayed in a field positioned directly below the ADD button .

The third setting field includes a button indicated as ADD in its upper area. The ADD button is clicked on whereby a section of the job structure can be added. The third setting field also includes a hierarchical menu which displays all the pages 800 pages on the same hierarchical level. In only some pages i.e. page 1 through page 9 are displayed due to dimensional limitations of the third setting field .

The fourth setting field includes a pulldown menu a button group having buttons indicated as SEARCH GENERATE EDIT and a template image of both sides including a face image and a back image . In the template image represents an imposition pattern titled Custom Template according to a 2 up imposition double sided printing process. The imposition pattern of the template image can be updated in response to update operation through the pulldown menu .

In step S shown in it is judged whether an instruction to start making settings for variable data printing has been received or not. In a case where no instruction is received control stays in step S. In a case where the instruction has been received control goes to step S.

In step S the individual page count acquirer reads PDF VT data for use in variable data printing from the memory or the like and analyzes the contents of the PDF VT data . The individual page count acquirer acquires the numbers of pages that make up the respective records as respective individual page counts. In the data structure shown in the individual page count acquirer acquires the number of pages 8 which is common to all the records as the respective individual page counts.

In step S the common page count determiner determines the maximum page count among the individual page counts acquired in step S as a common page count. In the data structure shown in since all the individual page counts for the record numbers 1 through 100 are 8 the common page count determiner determines 8 as the common page count.

In step S the editing mode acquirer acquires an editing mode that is being currently designated. As with general purpose printing settings variable data printing settings include a job editing mode for editing a job and an imposition editing mode for editing an imposition template. In a case where the job editing mode is designated for example the imposition apparatus continuously displays a job editing screen that is titled JOB EDITING in step S.

As shown in the job editing screen includes a first setting field a second setting field a third setting field a fourth setting field and a button group as with the job editing screen shown in . In the case of the variable data printing settings the job editing screen shown in has some displayed items different from those of the job editing screen according to the general purpose printing settings shown in .

For example the first setting field has an ADD button and the second setting field has an ADD button . These ADD buttons are displayed as passive buttons i.e. in an inoperable state . The third setting field has an EDIT button instead of the ADD button . The EDIT button is clicked on whereby the common page count 8 determined in step S can be manually changed.

The third setting field further includes a field directly below the EDIT button and RECORD COUNT 100 8 is newly displayed in the field indicating that the total number of records is 100 and the common page count is 8 . The third setting field also includes a hierarchical menu which displays pages Page 1 through Page 8 that make up one record. A face image schematically represents the form of a sheet indicated by the sheet number C1 and a back image schematically represents the form of a sheet indicated by the sheet number C2.

In step S the variable data printing setter judges whether it has received an instruction to save the settings or not. Specifically the variable data printing setter judges whether the button group particularly the SAVE button has been clicked on or not. In a case where the button group has not been clicked on control goes back to step S to repeat steps S through S.

In a case where the imposition editing mode is designated in step S then the imposition apparatus continuously displays an imposition editing screen that is titled IMPOSITION VIEW in step S.

Referring back to the button group particularly the EDIT button is clicked on whereby the screen generator generates display data for an imposition editing screen and supplies the generated display data to the display controller . The display controller controls the display unit to display another window W2 which includes the imposition editing screen .

As shown in the imposition editing screen includes an icon group an imposition display field a thumbnail display field a fourth setting field and a button group having buttons indicated as UPDATE CLOSE and SAVE . The operator can make various settings on the imposition editing screen by operating the input unit .

The imposition display field displays a preview image on a sheet. The operator can use an indication field positioned above the imposition display field to designate a record number R in an upper position or a sheet number S in a lower position to be displayed.

The thumbnail display field displays thumbnail images corresponding to the preview image . In a case where there are a plurality of thumbnail images displayed the operator can select one of them to call up the imposition pattern of the sheet corresponding to the selected thumbnail image into the imposition display field .

The fourth setting field includes an icon group and three check boxes . The operator can set various parameters about the imposing process through the check boxes .

In a case where an icon for selecting a normal mode is in an ON state the imposition editing screen shown in is displayed. On the other hand an icon is clicked on whereby the icon is brought into an ON state and as a result the C S mode is selected. The C S mode is an editing mode for cut and stack.

In response to the selection operation of the C S mode the sheet count calculator calculates a minimum number of sheets by which each record can be printed based on the number of pages assigned to one sheet the total number of records and the common page count. A specific example of the calculation of the minimum number of sheets for printing each record will be described below.

It is assumed that a 4 up imposition print is cut into halves and the 2 up imposition sheets are stacked. It is also assumed that the number of pages assigned per sheet is 8 the total number of records is 100 and the common page count is 8 . In this case the minimum number of sheets is calculated as common page count total number of records number of assigned pages 8 100 8 100.

For example the imposition display field displays a preview image in a layout for cut and stack. The thumbnail display field displays a thumbnail image corresponding to the preview image .

The C S setting field includes a group table with respect to cut and stack and a button group having buttons indicated as NEW GROUP and DELETE . The group table displays group numbers group names and sheet counts. Initially one group Cut Stack is generated and the sheet count thereof agrees with a value calculated by the sheet count calculator . The operator can click on the button group to change the number of groups for cut and stack or the distribution of sheet counts.

In step S in in a case where the variable data printing setter judges that the button group in particularly the SAVE button has been clicked on i.e. it has received an instruction to save the settings control goes to step S.

In step S the imposition data generator generates imposition data representing the imposition information finalized in steps S through S. Specifically the imposition data generator generates imposition data that indicate a page layout of one or more signatures. In the imposition data the record information is linked to the sheet information .

Thereafter the imposition data generator stores and saves the imposition data in the memory . The imposition apparatus may then send out the imposition data through the communication I F so that the server will hold the imposition data .

In step S the controller judges whether there is an instruction for printing from the operator or not. In a case where there is no instruction for printing then control stays in step S. In a case where there is an instruction for printing then control goes to step S.

In step S the RIP apparatus rasterizes imposed page description data and supplies the rasterized page description data as printing data to the digital printing press . Specifically the RIP apparatus rasterizes imposed page description data for one record then performs a differential process required for variable data printing on the rasterized page description data and supplies the processed page description data as printing data to the digital printing press . In this manner the variable data printing process is simplified and speeded up.

In step S the digital printing press produces a print per record based on the printing data processed and supplied thereto in step S.

In the example shown in the numbers of pages that make up the respective records are identical to each other. The present invention is also applicable to different numbers of pages that make up records.

Then as shown in one blank page is produced in the record indicated by the record number 1 two blank pages are produced in the record indicated by the record number 2 and one blank page is produced in the record indicated by the record number 4 .

The imposition data generator generates imposition data by inserting the blank pages through into the respective records to make up for the lacking pages in a case where their individual page counts are smaller than the common page count. More specifically the imposition data generator changes the page numbers of the record information see depending on the common page count and associates corresponding page description data to the blank pages through .

Therefore even in a case where the numbers of pages that make up respective records are different from each other a desired variable data printing process can be carried out. The above process is performed after the common page count has been changed through the EDIT button after the button group SAVE button has been clicked on or at other timings.

As described above the imposition apparatus includes the individual page count acquirer which acquires the numbers of pages making up respective records as individual page counts by analyzing the PDF VT data used for variable data printing the common page count determiner which determines as a common page count the maximum page count among the individual page counts and the imposition data generator which generates imposition data representing common and single page layout information made up of the common page count.

Since the maximum page count among the individual page counts is determined as a common page count and imposition data representing a common and single page layout made up of the common page count are generated it is enough to handle an amount of data corresponding to one record and the imposition data for variable data printing can be generated highly efficiently from the standpoint of data management and processing.

The present invention is not limited to the illustrated embodiment but many changes and modifications can be made to the embodiment without departing from the scope of the present invention.

