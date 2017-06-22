---

title: Output control device and output control method
abstract: An output control device includes an output instruction unit configured to give an instruction for outputting a single output information item, to an application requesting output of the single output information item as plural output information items having the same identification information based on an output instruction, and to subsequently give an instruction to output end information indicating an end of the single output information item; a storage control unit configured to store the output information items output from the application in a save area upon changing the identification information of the output information items into different identification information items; a determination unit configured to determine whether the instruction to output the end information has been given; and a combining unit configured to combine the output information items stored in the save area, when the determination unit determines that the instruction to output the end information has been given.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09176691&OS=09176691&RS=09176691
owner: RICOH COMPANY, LTD.
number: 09176691
owner_city: Tokyo
owner_country: JP
publication_date: 20140530
---
There is known a system for switching an application for each file type with respect to files created with document editing software and spreadsheet software and printing and computerizing the file. In this system an application is activated and an instruction such as print with printer or computerize by PDF Portable Document Format file is given to output each file in the instructed format.

For example when printing a file data print data is created from the target file with a predetermined printer driver and the created print data is sent to a printer via a TCP IP port monitor. Furthermore when computerizing a file the computerized data created with a computerizing driver such as a PDF driver is output to a folder etc. via a local port monitor.

Note that conventionally there is known a system for combining a print job with another print job output request to create a single job and printing the job see for example Patent Document 1 .

However by the conventional method as described in Patent Document 1 when computerizing a single job output request in a predetermined format there are cases where a single job is determined as including a plurality of jobs by the application. In this case when the jobs are saved in a folder via a local port monitor the jobs are sequentially overwritten and consequently only the file output information of the final job is computerized. Therefore even when a user opens a computerized file only the final job is displayed and the entire single job expected by the user cannot be confirmed.

The present invention provides an output control device and an output control method in which one or more of the above described disadvantages are eliminated.

According to an aspect of the present invention there is provided an output control device including an output instruction unit configured to give an instruction for outputting a single output target information item to an application requesting output of the single output target information item as a plurality of output information items having the same identification information based on an output instruction and to subsequently give an instruction to output end information indicating an end of the single output target information item a storage control unit configured to store the plurality of output information items output from the application in a predetermined save area upon changing the identification information of the plurality of output information items into identification information items that are different from each other a determination unit configured to determine whether the instruction to output the end information has been given by the output instruction unit and a combining unit configured to combine the plurality of output information items stored in the predetermined save area when the determination unit determines that the instruction to output the end information has been given.

According to an aspect of the present invention there is provided a non transitory computer readable recording medium having recorded thereon a program that causes a computer to execute a process including storing by a storage control unit a plurality of output information items output from an application requesting output of a single output target information item as the plurality of output information items having the same identification information based on an output instruction the plurality of output information items being stored in a predetermined save area upon changing the identification information of the plurality of output information items into identification information items that are different from each other determining by a determination unit whether an instruction to output end information indicating an end of the single output target information item has been given after an instruction to output the single output target information item is given and combining by a combining unit the plurality of output information items stored in the predetermined save area when the instruction to output the end information is determined to have been given by the determination unit.

According to an aspect of the present invention there is provided an output control method executed by an output control device the output control method including giving an instruction for outputting a single output target information item to an application requesting output of the single output target information item as a plurality of output information items having the same identification information based on an output instruction and subsequently giving an instruction to output end information indicating an end of the single output target information item storing the plurality of output information items output from the application in a predetermined save area upon changing the identification information of the plurality of output information items into identification information items that are different from each other determining whether the instruction to output the end information has been given and combining the plurality of output information items stored in the predetermined save area when the instruction to output the end information is determined to have been given.

A description is given with reference to the accompanying drawings of embodiments of the present invention.

Before describing the present embodiment a description is given of a specific example of a file output information computerized upon dividing a single job first output target information item into a plurality of jobs with reference to . are for describing a file that is computerized upon being divided into a plurality of jobs.

Furthermore illustrates an example of an Excel registered trademark file including four sheets. Excel is an example of an application in which a single job is divided into a plurality of jobs at the time of printing. When a print instruction is given with the use of an application with respect to the Excel file illustrated in a single job single output target information is divided into a plurality of jobs and the print data divided into a plurality of jobs output information items is output to the computerizing driver.

Note that the reason for dividing a single job into a plurality of jobs is that the respective sheets have different print qualities resolutions or the respective sheets have different color settings color monochrome however the reason is not so limited.

In the example of the job is divided into a plurality of jobs in which the first job includes sheet 1 and sheet 2 and the second job includes sheet 3 and sheet 4. As described above when a single job is divided into a plurality of jobs the computerizing driver sends the print data corresponding to two jobs by sending each job at a time e.g. the first job followed by the second job to a local port monitor for example.

In the local port monitor it is possible to set the port from which data is output. For example when a user sets the identification information for identifying a single job single output target information as test.pdf the first job of the print data to be output in a PDF file is output as test.pdf via the local port monitor. Similarly the second job is output as test.pdf having the same identification information via the local port monitor. Therefore in the conventional technology by outputting the second job the first job test.pdf is overwritten unintentionally.

As a result as illustrated in only the print data output information item of the final job remains as the computerized data and when the user opens this computerized file only the job including the third and fourth sheets is displayed.

Therefore the present embodiment that enables the user to confirm all of the output files of a single job in a case where a single job is computerized upon being divided into a plurality of jobs having the same identification information by the application corresponding to the file type.

The PC and the printer are connected by a network N such as LAN Local Area Network however the present embodiment is not so limited the PC and the printer may be connected in any form as long as data communication is possible. Furthermore the numbers of each of the devices included in the output control system are not limited to those illustrated in .

In the PC a printer driver for controlling the printer and a computerizing driver for computerizing a file are installed. When the PC acquires setting information relevant to processes to be executed by the printer the PC uses the acquired setting information to execute the processes with respect to the printer .

The printer includes for example printers and and outputs the input image data print data . For example the printer is an MFP Multifunction Peripheral including a printer function a fax function and a scanner function however the present embodiment is not so limited.

In the example of the PC switches the application according to the type of output file by a management application for managing an output file created with document editing software and spreadsheet software to print the file by the printer or computerize the file by a computerizing driver.

When computerizing an output file the PC combines one or a plurality of jobs that have been obtained by dividing a single job by an application corresponding to the type of output file based on an end termination notification of an output file obtained from the management application. Accordingly when the user opens the computerized file the entire single job is displayed and the user can confirm the entire job.

After instructing the output of a single output target information item a single job the management application instructs the application to output end information indicating the end of the single output target information item. The management application includes for example a print instruction unit and an end notification print job instruction unit .

In order to open an output file that is a target of computerization saved in a predetermined area the print instruction unit activates the application selects the computerizing driver instructs the print settings to be used when outputting the file and instructs the printing.

After the printing instruction is given by the print instruction unit the end notification print job instruction unit opens an end notification file for example end.xls which is an example of end information saved in a predetermined area specifies the computerizing driver and instructs the printing.

An end notification file is prepared for each type of output file and is used as a particular sign for reporting a notification of the end of printing of an output file the end of a single job however the present embodiment is not so limited.

The application is an application corresponding to the type of output file including document editing software such as Word and spreadsheet software such as Excel. The application requests to output a single output target information item a single job constituted by a plurality of sheets as a plurality of output information items having the same identification information print data divided into a plurality of jobs . The application performs printing based on the computerizing driver specified by the management application and the specified print setting via the OS .

The computerizing driver computerizes the print data in a predetermined format based on setting contents specified by the application and outputs the data to the local port monitor . As the computerizing driver drivers such as XPS XML Paper Specification TIFF Tagged Image File Format and JPEG Joint Photographic Experts Group may be used other than a PDF driver.

The local port monitor includes a print data saving unit as an example of a storage control unit an end notification print job confirmation unit as an example of a determining unit a print data combining unit as an example of a combining unit and a print data output unit .

The print data saving unit changes the identification information of output information items output from the application into identification information items that are different from each other and saves the output information items in a predetermined saving area. The print data saving unit first outputs the print data obtained from the computerizing driver and saves the print data in a print data saving area in response to an instruction from the end notification print job confirmation unit .

For example the print data saving unit applies numbers as the different identification information items to job names for example document names or file names identification information of print data output information divided into a plurality of jobs by a method set in advance for example in the order the print data is input . Furthermore for example the print data saving unit saves the print data divided into a plurality of jobs in the print data saving area .

Note that the predetermined area for saving a file and the print data saving area described above are predetermined storage areas in a storage unit such as a HDD Hard Disk Drive and a memory in the PC .

The end notification print job confirmation unit determines whether the management application has instructed output of end information. For example the end notification print job confirmation unit confirms whether a particular notification sign indicating the end of printing an output file set in advance the end of a single job from the end notification print job instruction unit .

Specifically the end notification print job confirmation unit confirms the job name of print data obtained from the computerizing driver . For example when the end notification print job confirmation unit determines that the job name of the print data is the job name for example end.xls for the end notification end sign the end notification print job confirmation unit instructs the print data combining unit to combine the print data saved in the print data saving area .

The print data combining unit acquires the print data saved in the print data saving area in response to an instruction from the end notification print job confirmation unit combines the acquired print data and outputs the combined print data to the print data output unit .

The print data output unit outputs the print data combined by the print data combining unit to a port that is specified in advance. The print data output unit may output the print data to for example C Users Public BoundJob.pdf which is a port that is specified in advance however the present embodiment is not so limited.

A description is given of an example where the management application instructs to computerize output a single file 4sheet.xls as for example BoundJob.pdf and the application divides the file into two jobs and instructs printing.

The management application opens the file of 4sheet.xls by the print instruction unit selects the computerizing driver makes a print setting and instructs the application to perform printing 1 in .

The application instructs the computerizing driver to print the first job via the OS 2 in . The computerizing driver creates print data based on the instructed print setting and outputs the print data to the local port monitor 3 in .

The local port monitor determines by the end notification print job confirmation unit whether the job name of the print data is for example end.xls which is for reporting an end notification. When the end notification print job confirmation unit determines that the job name of the print data is not end.xls the end notification print job confirmation unit instructs the print data saving unit to save the print data 4 in .

The print data saving unit applies a number to the job name of the print data obtained from the end notification print job confirmation unit for example as 4sheet X.prn X is a number that is a serial number and saves the print data in the print data saving area 5 in .

The print data of the first job is saved as for example 4sheet1.prn . Note that the print data of the second job obtained from the application is also saved as for example 4sheet2.prn in the print data saving area by the same process as that for the first job.

After the print instruction is given by the print instruction unit the management application opens for example an end notification file end.xls by the end notification print job instruction unit selects the computerizing driver and instructs the application to perform printing 6 in .

When the application instructs the computerizing driver to perform printing via the OS 7 in the computerizing driver creates print data and outputs the print data to the local port monitor 8 in .

When the local port monitor determines by the end notification print job confirmation unit that the job name of the print data is the job name for end notification for example end.xls the local port monitor instructs the print data combining unit to combine the print data 9 in .

The print data combining unit combines the files for example 4sheet1.prn 4sheet2.prn saved in the print data saving area in an appropriate order for example as BoundJob.pdf and outputs the combined file to the print data output unit 10 in .

As described above when a single job output request which is based on an output instruction from the management application is divided into a plurality of jobs by the application it is possible to combine the output files which have been divided in accordance with the plurality of jobs into one job. Furthermore the print data output information is combined in procedures after that of the computerizing driver and therefore the print data can be combined in either one of a RAW spool format or an EMF Enhanced MetaFile spool format.

Note that spool data is data that is sent to the spooler where the data is temporarily accumulated or where the data passes through when sending the data from an application to the printer in a Windows registered trademark environment. Furthermore for example a RAW format is a format in which the process depends on the printer and an EMF format is an intermediate data format rendered with the use of a render command of Windows GDI Graphic Device Interface .

Next a description is given of an example of a hardware configuration of an output control device according to the present embodiment. illustrates an example of a hardware configuration of an output control device. Note that illustrates an example of the hardware configuration of the PC corresponding to however the same configuration is applicable to the printer .

As illustrated in the PC includes a CPU Central Processing Unit a RAM Random Access Memory a ROM Read Only Memory a HDD an I F unit a drive device a LCD Liquid Crystal Display an operation unit and a recording medium .

The CPU the RAM the ROM the HDD the I F unit and the drive device are connected via a bus . Furthermore to the I F unit the LCD and the operation unit are connected. Note that in the case of the printer an engine is included for executing image formation output and scanning.

The CPU is a processor that controls the operations of the entire PC . The CPU controls the execution of processes in the respective applications the driver and the local port monitor relevant to the PC illustrated in .

The RAM is a volatile storage medium in which reading writing of information can be performed at high speed. The RAM is used as a work area when the CPU processes information.

The ROM is a non volatile storage medium from which information can be read. The ROM stores programs such as firmware. The HDD is a non volatile storage medium in which reading writing of information can be performed. The HDD stores an OS various control programs and application programs.

The I F unit is connected to various hardware elements and networks. The LCD is for example a display unit for displaying various screens for executing the processes for example a computerizing process according to the present embodiment. The operation unit is for example a keyboard a mouse various hardware buttons a touch panel and is a user interface for receiving information input from a user.

The output control program according to the present embodiment is provided by the recording medium such as a CD ROM. The recording medium is set in the drive device and the output control program included in the recording medium is installed from the recording medium via the drive device .

Note that as the recording medium recording the program various types of recording media may be used including a recording medium for optically electronically or magnetically recording information such as a CD ROM a flexible disk and a magnetooptic disc MO or a semiconductor memory for electrically recording information such as a flash memory.

In the above hardware configuration a program stored in a storage medium such as the ROM the HDD and an optical disk is loaded in the RAM and the CPU performs processing according to the loaded program thereby constituting a software control unit for implementing the processes of the respective units in the PC illustrated in for example. By combining the software control unit constituted as described above with the hardware it is possible to realize the functions of the respective devices constituting the system according to the present embodiment.

The temporal flow of the processes in the above configurations is described by a sequence. illustrates an example of a sequence of an output control process according to the first embodiment. The sequence illustrated in is executed by the management application the application the computerizing driver and the local port monitor .

In the management application instructs by the print instruction unit the application to print a single output file for example 4sheet.xls step S .

When the application acquires the output file for which printing has been instructed by the print instruction unit the application instructs the computerizing driver to print a first job step S . The computerizing driver creates print data based on the instructed print setting step S and outputs the print data to the local port monitor step S .

The local port monitor determines by the end notification print job confirmation unit whether the job name of the print data obtained from the computerizing driver is a job name for end notification for example end.xls step S .

When the local port monitor determines that the job name of the print data is not end.xls for end notification the local port monitor saves by the print data saving unit the print data 4sheet1.prn in the print data saving area step S .

Next the application instructs the computerizing driver to print a second job step S . The computerizing driver creates print data based on the instructed print setting step S and outputs the print data to the local port monitor step S .

The local port monitor determines by the end notification print job confirmation unit whether the job name of the print data obtained from the computerizing driver is a job name for end notification end.xls step S . When the local port monitor determines that the job name of the print data is not end.xls for end notification the local port monitor saves by the print data saving unit the print data 4sheet2.prn in the print data saving area step S .

Next after the print instruction is given by the print instruction unit the management application opens the end notification file by the end notification print job instruction unit and instructs the application to perform printing step S .

When the application acquires the end notification file for which printing has been instructed by the end notification print job instruction unit the application instructs the computerizing driver to perform printing step S . The computerizing driver creates print data step S and outputs the print data to the local port monitor step S .

The local port monitor determines by the end notification print job confirmation unit whether the job name of the print data is a job name for end notification end.xls step S . When the local port monitor determines that the job name of the print data is end.xls for end notification the local port monitor combines by the print data combining unit the files saved in the print data saving area in the order of for example the file numbers step S .

Next the local port monitor outputs by the print data output unit the file combined by the process of step S step S .

As described above even when a single job is divided into a plurality of jobs by the application the files are saved until the end notification is reported and the saved files are combined and output according to the end notification. Accordingly when the user opens the computerized file the entirety of the single job is displayed.

Next a description is given of the data combining process corresponding to the processes of steps S and S illustrated in . is a flowchart of an example of a data combining process. In the process illustrated in print data is created based on a print setting instructed by the computerizing driver and when the print data is output to the local port monitor the end notification print job confirmation unit confirms the job name of the print data obtained from the computerizing driver step S .

The end notification print job confirmation unit determines whether the job name of the print data is a job name for end notification for example end.xls step S . When the end notification print job confirmation unit determines that the job name of the print data is not a job name for end notification end.xls NO in step S the end notification print job confirmation unit applies by the print data saving unit a number that is a serial number to the job name of the print data and moves the print data to the print data saving area step S .

Furthermore when the end notification print job confirmation unit determines that the job name of the print data is the job name for end notification end.xls YES in step S the print data combining unit combines the files print data saved in the print data saving area in an PDF format for example step S . Next the print data output unit outputs the files combined by the process of step S to a port specified in advance step S and ends the process.

Note that when a single job is divided into a plurality of jobs at the time of printing after the process of step S described above the print data of the next job is output from the computerizing driver to the local port monitor and therefore the processes from step S are repeated.

In the example of a single job is divided into a plurality of jobs and the previous job is overwritten by the next job and therefore only the print data of the final job is displayed. Meanwhile in the example of the print data that has been divided into a plurality of jobs is combined into a single job and the entire single job test.pdf file is displayed which is constituted by the first page combination of the first sheet and the second sheet and the second page combination of the third sheet and the fourth sheet .

As described above even when a single job is divided into a plurality of jobs the print data items which have been divided according to the plurality of jobs are combined together and the entire single job is displayed such that the user can confirm the entire single job as expected.

In the PC the print processor includes an EMF data backup unit which is an example of a storage control unit. Furthermore in the PC the dispatcher includes an end notification print job confirmation unit as an example of a determination unit and an EMF data output unit as an example of a combining unit.

In the second embodiment by having the above configuration a single job divided into a plurality of jobs can be appropriately combined. Furthermore the jobs are combined with the use of EMF data that does not depend on PDL Page Description Language and therefore there is no need for an implementation corresponding to PDL. In the following the points that are different from the first embodiment are mainly described. Note that the same elements are denoted by the same reference numerals and detailed descriptions are omitted.

In the example of the virtual driver creates print data in a predetermined format based on a print setting specified by the application . For example the virtual driver creates print data EMF data in an EMF format that does not depend on PDL. Note that the virtual driver is used according to need.

The print processor includes the EMF data backup unit . The EMF data backup unit acquires EMF data of one job or EMF data that has been divided into a plurality of jobs from the application via the OS .

The EMF data backup unit applies numbers to the job names for example document names and file names of the acquired EMF data by a method set in advance for example the order in which the EMF data is input and backs up the EMF data in the EMF data saving area . Note that the EMF data saving area described above is a predetermined storage area in a storage unit such as the HDD and the memory in the PC .

The dispatcher includes the end notification print job confirmation unit and the EMF data output unit . The end notification print job confirmation unit confirms the job name of the EMF data saved in the EMF data saving area and determines whether the job name is a job name for end notification for example end.xls .

The EMF data output unit gives an output instruction of EMF data saved in the EMF data saving area to the OS within a single job in response to an instruction from the end notification print job confirmation unit . Accordingly it is possible to combine EMF data corresponding to a single job saved in for example the EMF data saving area .

The EMF data output unit acquires the file handle of the EMF data from the OS by using for example a GetEnhMetaFile function that is the API Application Programming Interface of Windows. Furthermore the EMF data output unit gives an output instruction by using for example a PlayEnhMetaFile function with respect to the EMF data acquired from the EMF data saving area based on the acquired file handle.

A local port monitor includes the print data output unit . The print data output unit can output the print data acquired from the computerizing driver to a port specified in advance such as C Users Public BoundJob.pdf however the present embodiment is not so limited.

A description is given of an example in which similar to the first embodiment when an instruction is given from the management application to computerize a single file 4sheet.xls as for example BoundJob.pdf the application divides the file into two jobs and instructs printing.

The management application opens the file of 4sheet.xls by the print instruction unit selects the computerizing driver makes a print setting and instructs the application to perform printing 1 in .

The application instructs via the OS the print processor to print the first job 2 and 3 in . The print processor adds by the EMF data backup unit a number to the job name of the EMF data such as emf data X.EMF X is a number that is a serial number and backs up the EMF data in the EMF data saving area 4 in . The EMF data of the first job is saved as for example emf data1.EMF .

The print processor activates the dispatcher and normally ends 5 in . The dispatcher determines by the end notification print job confirmation unit whether there is a job name for end notification such as end.EMF among the job names of the EMF data saved in the EMF data saving area and confirms that there is no end.EMF 6 in .

Note that according to need the virtual driver creates print data in a predetermined file format based on a print instruction obtained from the application via the OS 7 in .

Similar to the first job the EMF data of the second job obtained from the application is named for example emf data2.EMF and saved in the EMF data saving area . Furthermore the end notification print job confirmation unit of the dispatcher determines whether the job name is a job name for end notification end.EMF .

Next after a print instruction is given by the print instruction unit the management application opens by the end notification print job instruction unit the file for end notification end.xls selects the computerizing driver and instructs the application to perform printing 8 in . The application instructs the print processor to perform printing via the OS 9 and 10 in .

In the case of a file for end notification the print processor adds by the EMF data backup unit a job name for end notification end.EMF to the job name of the EMF data and backs up the EMF data in the EMF data saving area 11 in .

The print processor activates the dispatcher and normally ends 12 in . The dispatcher determines by the end notification print job confirmation unit whether there is a job name for end notification such as end.EMF among the job names of the EMF data saved in the EMF data saving area 13 in .

When the EMF data output unit determines by the end notification print job confirmation unit that there is a job name for end notification end.EMF the EMF data output unit acquires a file handle of the EMF data saved in the EMF data saving area from the OS by using for example a GetEnhMetaFile function.

Next the EMF data output unit acquires the EMF data from the EMF data saving area based on the acquired file handle 14 in and gives an output instruction to the OS by using a PlayEnhMetaFile function 15 in .

The OS instructs the computerizing driver to print the print data in response to the output instruction from the EMF data output unit 16 in . The computerizing driver creates print data based on the instructed print setting and outputs the print data to the local port monitor 17 in .

As described above even when a single job is divided into a plurality of jobs by the application the output files which have been divided according to the plurality of jobs can be combined together as a single job. Furthermore data in an EMF format that does not depend on PDL is used and therefore there is no need for an implementation corresponding to PDL.

Furthermore the dispatcher operates according to a process separate from the spooler process and therefore a preview screen can be displayed. Therefore the user can change the output order of pages on the preview screen.

In the management application instructs by the print instruction unit the application to print a single output file for example 4sheet.xls step S .

When the application acquires the output file for which printing is instructed by the print instruction unit the application instructs the OS to print the first job step S . The OS reports a notification of the print instruction of the first job to the print processor step S . The print processor applies by the EMF data backup unit a number to the job name of the EMF data such as emf data X.EMF X is a number that is a serial number and backs up the EMF data in the EMF data saving area step S .

Next the print processor activates the dispatcher step S . The dispatcher determines by the end notification print job confirmation unit whether there is a job name for end notification such as end.EMF among the job names of the EMF data saved in the EMF data saving area step S . Note that according to need the OS sends a notification of the print instruction to the virtual driver step S and acquires print data in a predetermined file format created by the virtual driver .

Next when the application instructs the OS to print the second job step S the OS sends a notification of the print instruction for the second job to the print processor step S . Similar to the first job the print processor adds a number such as emf data2.EMF to the EMF data of the second job obtained from the application and backs up the EMF data in the EMF data saving area step S .

Next the print processor activates the dispatcher step S . The dispatcher determines by the end notification print job confirmation unit whether there is a job name for end notification such as end.EMF among the job names of the EMF data saved in the EMF data saving area step S . Note that according to need the OS sends a notification of the print instruction to the virtual driver step S and acquires print data in a predetermined file format created by the virtual driver .

Next after the print instruction unit has instructed the printing the management application opens by the end notification print job instruction unit the end notification file end.xls selects the computerizing driver and instructs the application to perform printing step S . When the application instructs the OS to print the job for end notification step S the OS sends a notification of the print instruction of the job for end notification to the print processor step S .

The print processor adds by the EMF data backup unit a job name for end notification such as end.EMF to the job name of the EMF data and backs up the EMF data in the EMF data saving area step S .

Next the print processor activates the dispatcher step S . The dispatcher determines by the end notification print job confirmation unit whether there is a job name for end notification such as end.EMF among the job names of the EMF data saved in the EMF data saving area step S .

When the end notification print job confirmation unit determines that there is a job name for end notification end.EMF the dispatcher acquires by the EMF data output unit a file handle of the EMF data saved in the EMF data saving area from the OS by using for example a GetEnhMetaFile function step S .

Next the dispatcher acquires EMF data from the EMF data saving area based on the acquired file handle and with respect to the acquired EMF data the dispatcher gives an output instruction to the OS by using a PlayEnhMetaFile function step S .

The OS instructs the computerizing driver to print the print data by regarding the EMF data acquired from the dispatcher as a single job step S . The computerizing driver creates print data based on the instructed print setting step S and outputs the print data to the local port monitor step S .

In the second embodiment described above when printing the job for end notification the dispatcher gives to the OS an instruction to output EMF data backed up in the EMF data saving area . The OS instructs the computerizing driver to print the data as a single job and the computerizing driver creates and outputs the print data. Accordingly EMF data that has been divided into a plurality of jobs can be finally output as print data of a single job.

In the third embodiment by having the above configuration a single job divided into a plurality of jobs can be appropriately combined. Furthermore in order to combine the print data in the computerizing driver for example either the RAW spool format or the EMF spool format can be used. In the following the points that are different from the first embodiment are mainly described. Note that the same elements are denoted by the same reference numerals and detailed descriptions are omitted.

A description is given of an example similar to the first embodiment in which an instruction is given from the management application to computerize a single file 4sheet.xls as BoundJob.pdf and the application divides the file into two jobs and instructs printing.

The management application opens the file of 4sheet.xls by the print instruction unit selects the computerizing driver makes a print setting and instructs the application to perform printing 1 in .

The application instructs via the OS the computerizing driver to print the first job 2 in . The render unit of the computerizing driver determines by the end notification print job confirmation unit whether the job name of the print data is a job name for end notification for example end.xls . When the end notification print job confirmation unit determines that the job name of the print data is not a job name for end notification end.xls the end notification print job confirmation unit instructs the print data saving unit to save the print data 3 in .

The print data saving unit adds a number to the job name of the print data obtained from the end notification print job confirmation unit such as 4sheet X.prn X is a number that is a serial number and saves the print data in a print data saving area 4 in .

The print data of the first job is saved as for example 4sheet1.prn . Note that the print data of the second job obtained from the application is also saved in the print data saving area as for example 4sheet2.prn by the same process as that for the first job.

Next after the print instruction is given by the print instruction unit the management application opens for example an end notification file end.xls by the end notification print job instruction unit selects the computerizing driver and instructs the application to perform printing 5 in . The application instructs the computerizing driver to perform printing via the OS 6 in .

When the end notification print job confirmation unit determines that the job name of the print data is a job name for end notification such as end.xls the end notification print job confirmation unit instructs the print data combining unit to combine the print data 7 in .

The print data combining unit combines the files for example 4sheet1.prn 4sheet2.prn saved in the print data saving area for example as BoundJob.pdf and outputs the combined file to the local port monitor 8 in .

As described above even when a single job is divided into a plurality of jobs by the application the output files which have been divided according to the plurality of jobs can be combined together as a single job. Furthermore by combining the print data in the render unit of the computerizing driver for example the print data can be combined in the RAW spool format or the EMF spool format.

In the management application instructs by the print instruction unit the application to print a single output file for example 4sheet.xls step S .

The application instructs the computerizing driver to print the first job step S . The render unit of the computerizing driver determines by the end notification print job confirmation unit whether the job name of the print data is a job name for end notification end.xls step S . When the end notification print job confirmation unit determines that the job name of the print data is not a job name for end notification end.xls the end notification print job confirmation unit instructs the print data saving unit to save the print data step S . Note that in the process of step S the print data saving unit adds a number to the job name of the print data obtained from the end notification print job confirmation unit such as 4sheet X.prn X is a number that is a serial number and saves the print data in a print data saving area .

The application instructs the computerizing driver to print the second job step S . Similar to the first job the render unit of the computerizing driver determines by the end notification print job confirmation unit whether the job name of the print data is a job name for end notification and when the end notification print job confirmation unit determines that the job name of the print data is not a job name for end notification the end notification print job confirmation unit instructs the print data saving unit to save the print data step S .

Next after the print instruction is given by the print instruction unit the management application opens for example an end notification file end.xls by the end notification print job instruction unit selects the computerizing driver and instructs the application to perform printing step S . The application instructs the computerizing driver to perform printing step S .

The render unit of the computerizing driver determines by the end notification print job confirmation unit whether the job name of the print data is a job name for end notification end.xls step S . When the end notification print job confirmation unit determines that the job name of the print data is a job name for end notification the end notification print job confirmation unit instructs the print data combining unit to combine the print data step S .

Note that in the process of step S the print data saving unit combines the files for example 4sheet1.prn 4sheet2.prn saved in the print data saving area for example as BoundJob.pdf . The computerizing driver outputs the combined file to the local port monitor step S .

The third embodiment described above is different from the first embodiment in that the computerizing driver can perform the process of determining whether the job name of the print data is a job name for end notification and the process of combining the print data.

In the fourth embodiment by having the above configuration a single job divided into a plurality of jobs can be appropriately combined. Furthermore similar to the second embodiment the jobs are combined with the use of EMF data and therefore there is no need for an implementation corresponding to PDL. Furthermore the PC can be realized by a smaller configuration than that of the second embodiment.

A description is given of an example in which similar to the first embodiment when an instruction is given from the management application to computerize a single file 4sheet.xls as for example BoundJob.pdf the application divides the file into two jobs and instructs printing.

The management application opens the file of 4sheet.xls by the print instruction unit selects the computerizing driver makes a print setting and instructs the application to perform printing 1 in .

The application instructs via the OS the print processor to print the first job 2 and 3 in . The print processor adds by the EMF data backup unit a number to the job name of the EMF data such as emf data X.EMF X is a number that is a serial number and backs up the EMF data in the EMF data saving area 4 in . The EMF data of the first job is saved as for example emf data1.EMF .

The print processor determines by the end notification print job confirmation unit whether there is a job name for end notification such as end.EMF among the job names of the EMF data saved in the EMF data saving area . When the print processor confirms by the end notification print job confirmation unit that there is no job name for end notification such as end.EMF the print processor normally ends the process 5 in .

Similar to the first job the EMF data of the second job obtained from the application is named for example emf data2.EMF and saved in the EMF data saving area . Furthermore the end notification print job confirmation unit determines whether the job name is a job name for end notification end.EMF .

Next after a print instruction is given by the print instruction unit the management application opens by the end notification print job instruction unit the file for end notification end.xls selects the computerizing driver and instructs the application to perform printing 6 in . The application instructs the print processor to perform printing via the OS 7 and 8 in .

In the case of a file for end notification the print processor adds by the EMF data backup unit a job name for end notification end.EMF to the job name of the EMF data and backs up the EMF data in the EMF data saving area 9 in .

The print processor determines by the end notification print job confirmation unit whether there is a job name for end notification such as end.EMF among the job names of the EMF data saved in the EMF data saving area 10 in .

When the print processor determines by the end notification print job confirmation unit that there is a job name for end notification end.EMF the EMF data output unit acquires a file handle of the EMF data saved in the EMF data saving area from the OS by using for example a GetEnhMetaFile function.

Next the EMF data output unit acquires the EMF data from the EMF data saving area based on the acquired file handle 11 in and gives an output instruction to the OS by using a PlayEnhMetaFile function 12 in .

The OS instructs the computerizing driver to print the print data in response to the output instruction from the EMF data output unit 13 in . The computerizing driver creates print data based on the instructed print setting and outputs the print data to the local port monitor 14 in .

As described above even when a single job is divided into a plurality of jobs by the application the output files which have been divided according to the plurality of jobs can be combined together as a single job. Furthermore data in an EMF format that does not depend on PDL is used and therefore there is no need for an implementation corresponding to PDL. Furthermore the PC can be realized by a smaller configuration than that of the second embodiment.

In the management application opens the file of 4sheet.xls by the print instruction unit selects the computerizing driver makes a print setting and instructs the application to perform printing step S .

When the application acquires the output file for which printing is instructed by the print instruction unit the application instructs the OS to print the first job step S . The OS instructs the printing of the first job to the print processor step S . The print processor applies by the EMF data backup unit a number to the job name of the EMF data such as emf data X.EMF X is a number that is a serial number and backs up the EMF data in the EMF data saving area step S .

The print processor determines by the end notification print job confirmation unit whether there is a job name for end notification such as end.EMF among the job names of the EMF data saved in the EMF data saving area step S . When the print processor determines by the end notification print job confirmation unit that there is no job name for end notification such as end.EMF the print processor normally ends the process.

Next when the application instructs the OS to print the second job step S the OS sends a notification of the print instruction for the second job to the print processor step S . Similar to the first job the print processor adds a number such as emf data2.EMF to the EMF data of the second job obtained from the application and backs up the EMF data in the EMF data saving area step S .

Next the print processor determines by the end notification print job confirmation unit whether there is a job name for end notification such as end.EMF among the job names of the EMF data saved in the EMF data saving area step S . When the print processor determines by the end notification print job confirmation unit that there is no job name for end notification such as end.EMF the print processor normally ends the process.

Next after the print instruction unit has instructed the printing the management application opens by the end notification print job instruction unit the end notification file end.xls selects the computerizing driver and instructs the application to perform printing step S . When the application instructs the OS to print the job for end notification step S the OS sends a notification of the print instruction of the job for end notification to the print processor step S .

The print processor adds by the EMF data backup unit a job name for end notification such as end.EMF to the job name of the EMF data in the case of a file for end notification and backs up the EMF data in the EMF data saving area step S .

The print processor determines by the end notification print job confirmation unit whether there is a job name for end notification such as end.EMF among the job names of the EMF data saved in the EMF data saving area step S .

When the print processor determines by the end notification print job confirmation unit that there is a job name for end notification end.EMF the EMF data output unit acquires a file handle of the EMF data saved in the EMF data saving area from the OS by using for example a GetEnhMetaFile function step S .

Next the EMF data output unit acquires EMF data from the EMF data saving area based on the acquired file handle and with respect to the acquired EMF data the EMF data output unit gives an output instruction to the OS by using a PlayEnhMetaFile function step S .

The OS instructs the computerizing driver to print the print data in response to the output instruction from the EMF data output unit step S . The computerizing driver creates print data based on the instructed print setting step S and outputs the print data to the local port monitor step S .

In the fourth embodiment described above the processes performed by the dispatcher of the second embodiment can be executed by the print processor .

According to the embodiments described above a plurality of output information items which have been divided by an application can be combined together. Note that in the above embodiments a description is given with the use of a PC as one example of the information processing device however the information processing device may also be a smartphone a tablet terminal a server etc. and the embodiments are also applicable to an image processing device such as a MFP. Furthermore part of or all of the first through fourth embodiments may be combined together according to need.

According to one embodiment of the present invention an output control device and an output control method are provided in which a plurality of output information items divided by an application can be combined.

The output control device and the output control method are not limited to the specific embodiments described herein and variations and modifications may be made without departing from the spirit and scope of the present invention.

The present application is based on and claims the benefit of priority of Japanese Priority Patent Application No. 2013 118062 filed on Jun. 4 2013 Japanese Priority Patent Application No. 2014 100858 filed on May 14 2014 the entire contents of which are hereby incorporated herein by reference.

