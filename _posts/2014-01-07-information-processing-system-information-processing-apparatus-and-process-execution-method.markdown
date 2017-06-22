---

title: Information processing system, information processing apparatus, and process execution method
abstract: An information processing system includes a managing unit that sorts a process execution request based on a type of process of the process execution request; a storing unit that stores the sorted process execution request according to the type of process of the process execution request; and a plurality of executing units that are configured to execute a process corresponding to the process execution request stored in the storing unit. At least one executing unit of the plurality of executing units is configured to split the process corresponding to the process execution request stored in the storing unit into a plurality of processes to be executed by at least two other executing units of the plurality of executing units and store in the storing unit a split process execution request including the split processes for prompting the other executing units to cooperatively execute the split processes.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09383950&OS=09383950&RS=09383950
owner: Ricoh Company, Ltd.
number: 09383950
owner_city: Tokyo
owner_country: JP
publication_date: 20140107
---
This application is based on and claims the benefit of priority of the Japanese Patent Application No. 2013 003182 filed on Jan. 11 2013 and Japanese Patent Application No. 2013 216166 filed on Oct. 17 2013 the entire contents of which are incorporated herein by reference.

The disclosures herein generally relate to an information processing system an information processing apparatus and a process execution method.

Cloud computing systems that are configured to enable cooperation between a device a web service and a platform providing a distributed environment are known see e.g. Japanese Laid Open Patent Publication No. 2011 192250 .

The cloud computer system disclosed in Japanese Laid Open Patent Publication No. 2011 192250 includes a request receiving part that receives a processing request of a job from an image forming device a backend processing part that executes a process based on a message corresponding to the job and a managing part that manages the number of backend processing parts.

The backend processing part includes a determination unit that determines a task execution status of the job and a command unit that selects a task service according to the task execution status of the job from multiple task services provided by a service providing apparatus and issues a command to the service providing device to execute the selected task service.

For example in a case of converting data from one data format to another data format a data conversion engine data conversion program or data conversion library for executing a data format conversion process may be used in order to increase independence and facilitate maintenance of the program.

Note that use of an engine is not limited to the case of executing a data format conversion process. That is a process execution engine process execution program or process execution library for executing some other type of process may similarly be used to increase independence and facilitate maintenance of the program.

However for example in the case of using a data format conversion engine the number of types of data conversion engines that are required corresponds to the number of different combinations of an input data format and an output data format. For example in a case where data may be in either one of three different types of data formats before data conversion input data formats and the data may be converted into one of three different types of data formats output data formats there are nine different combinations of the input data format and the output data format and accordingly nine types of data conversion engines are required. In other words the larger the number of options for the data formats before or after data conversion the larger the number of types of data conversion engines that are required.

Thus the number of process execution engines that need to be prepared increases as the number of types of processes to be executed e.g. data conversion process increases. Accordingly there is a demand for a technique for flexibly adapting to such increase in the number of types of a process.

According to one embodiment of the present invention an information processing system includes a managing unit that sorts a process execution request based on a type of process of the process execution request a storing unit that stores the sorted process execution request according to the type of process of the process execution request and a plurality of executing units that are configured to execute a process corresponding to the process execution request stored in the storing unit. At least one executing unit of the plurality of executing units is configured to split the process corresponding to the process execution request stored in the storing unit into a plurality of processes to be executed by at least two other executing units of the plurality of executing units and store in the storing unit a split process execution request including the split processes for prompting the other executing units to cooperatively execute the split processes.

According to an aspect of the present invention accommodations may be flexibly made in response to an increase in the number of types processes to be executed.

In the following embodiments of the present invention are described with reference to the accompanying drawings.

In step S the server may convert the uploaded electronic document file into print data in RPCS Refined Printing Command Stream which is a page description language developed by RICOH COMPANY LTD. for example. In step S an output end apparatus such as a MFP Multi Function Peripheral may receive the print data from the cloud and output the print data.

When viewed from the cloud side the PC and the MFP correspond to clients. The PC and the MFP as clients establish communication with the server on the cloud to perform a certain process.

In cloud printing a data conversion process may be performed at the cloud so that a data conversion engine may not have to be provided at the PC corresponding to a client. On the other hand a wide range of data conversion engines have to be prepared at the cloud side in order to accommodate various types of electronic document files and the types of electronic document files are expected to increase further in the future. In addition the output end apparatus is not limited to the MFP and other apparatuses such as a projector or a completely unknown apparatus may be used as the output end apparatus. Further a data conversion engine may be desired for converting data into a data format that is compatible with another cloud service for example.

Technical problems associated with such diversification of processes are encountered not only with respect to data conversion processes but various other types of processes executed at the cloud side. For example the above problems may be encountered in a case where an image is scanned by the MFP and a process of executing an OCR optical character reader process on the scanned image and storing the processed image data in an online storage provided by another cloud service is performed at the cloud side.

Also the above problems may be encountered in a case where a file is read from an online storage provided by another cloud service and a data conversion process such as converting the file into print data print file or executing an OCR process on the file is performed at the cloud side.

Note that although a process associated with cloud printing is described below application of the present invention is not limited to cloud printing. For example aspects of the present invention may be applied to the process of executing an OCR optical character reader process on an image scanned by the MFP and storing the processed image data in an online storage provided by another cloud service as described above. Also aspects of the present invention may be applied to the process of reading a file from an online storage provided by another cloud service and converting the file into print data or executing an OCR process on the file as described above for example.

The cloud printing illustrated in may be implemented by a cloud computing type information processing system as illustrated in for example. is a block diagram illustrating an exemplary configuration of the information processing system for implementing cloud printing.

In the local end includes the PC and the MFP . The PC and the MFP may be connected to the Internet via a firewall that is set up in a gateway of the LAN for example. The PC and the MFP may or may not be located within the same network. In the following descriptions it is assumed that the PC and the MFP are not located within the same network.

In the cloud end includes a data conversion system a print job management server a reverse proxy an authentication server and an authentication database .

The data conversion system includes an asynchronous conversion server a shared file storage and a job information management database . The shared file storage may be connected externally to the data conversion system . In addition the job information management database may form a part of the asynchronous conversion server as illustrated in .

The reverse proxy may mediate the communication of the local end apparatus and thus the local end apparatus may execute a process or establish communication without regard for the internal structure of the server group or storage at the cloud end. The authentication server and the authentication database are configured to authenticate the user and or the local end apparatus.

The data conversion system and the print job management server may manage and or register a print job that is uploaded by the PC corresponding to a local end apparatus. In a case where a print request is issued from the MFP corresponding to another local end apparatus the data conversion system and the print job management server may send corresponding print data to the MFP .

The print job may include an electronic document file that is created by a word processor application for example. The data conversion system may convert the electronic document file included in the print job into print data that is electronic data in a data format PDL Page Description Language that may be printed and output from the MFP for example.

Next an exemplary use mode of the information processing system illustrated in is described with reference to . is a flow chart illustrating exemplary process steps involved in cloud printing.

In step S a user logs into the cloud printing service via the PC . The authentication server may perform an authentication process for authenticating the user. In step S the user uploads the electronic document file that is to be printed from the PC to the cloud printing service. This uploading of the electronic document file may correspond to registration of the print job. A registration process for registering the print job may be executed by the print job management server . The procedures of steps S and S are performed by the PC .

When the print job is registered the cloud printing service performs a data conversion process in the background. That is the cloud printing service executes the data conversion process as an exemplary asynchronous process.

In step S the print job management server requests the data conversion system to perform a data conversion process on the registered electronic document file. Details of the data conversion process performed in step S are described below.

When the user wishes to print a print job the following series of steps may be performed at the MFP for example. In step S the cloud end confirms whether the MFP is capable of accepting the cloud print service and in this way the MFP may be authenticated apparatus authentication . Next the user operates the MFP to log into the cloud printing service from the MFP and in this way the user may be authenticated user authentication .

After the authentications in step S the MFP acquires a job list from the cloud printing service and displays the acquired job list on a display unit. Next in step S the user selects a desired print job from the displayed job list.

When the print job to be processed is selected by the user in step S the MFP acquires the print job from the cloud printing service and outputs prints the print job. By using the cloud printing service as described above the PC or the MFP may not need to have a print driver data conversion engine . Thus for example in the case of making overseas business trips the information processing system of the present embodiment may be effectively used to create upload conference materials at the office before the trip and then print out the materials at the travel destination.

The data conversion system of the present embodiment is preferably configured to be capable of accommodating various types of data conversion requests and flexibly adapting to an increase in the number of types of data conversion requests. For example the data conversion system may have a configuration as illustrated in . a block diagram illustrating an exemplary functional configuration of the data conversion system of the present embodiment.

As illustrated in the data conversion system may include a front end application a shared file storage and an asynchronous conversion server . The front end application may be a function of the print job management server . The asynchronous conversion server may provide an asynchronous conversion service. The asynchronous conversion server may include a data conversion request management unit message queues a job information management database and a plurality of converting units .

The print job management server may include a function to receive the print job sent from the input end apparatus such as the PC and to register an electronic document file included in the print job to the shared file storage for example. In addition the print job management server may determine the file conversion that is required and control the data conversion system to execute the required file conversion.

The converted file may be registered in the shared file storage . For example when an output command for the print job is received from the MFP corresponding to an output end apparatus the print job management server may send the converted file that is registered in the shared file storage to the MFP .

The front end application may include a function to determine the file conversion required to execute the output command. In a case where the registered electronic file is a document file and the MFP issuing the output command employs the RPCS for example the front end application may determine that the registered electronic file requires conversion from the document file data format into the RPCS data format.

The front end application may embed the type of data conversion required as a parameter such as type doc2rpcs for example in a data conversion request to be sent to the asynchronous conversion server .

Similarly a parameter such as a URI Uniform Resource Indicator of the data or source data before the conversion may be embedded in the data conversion request. The URI is information indicating a location of the data within the shared file storage .

In the asynchronous conversion server that receives the data conversion request with the type of data conversion and the URI of the data embedded therein the data conversion request management unit may receive the data conversion request and analyze the data conversion request. The data conversion request management unit may then enqueue a message job in one of the message queues according to the type of data conversion of the data conversion request.

At the same time the data conversion request management unit may register or update information relating to the data conversion request in the job information management database in parallel with the operation of enqueuing the message into one of the message queues .

The information registered in the job information management database may include the location of the file URI in the shared file storage the type of data conversion included in the data conversion request and a status of the data conversion request for example. The status of the data conversion request may include statuses such as executing data conversion converting data and data conversion completed for example. The status of the data conversion request may represent the progress or processing status of the data conversion.

The message queues may include queues corresponding to each of the plurality of converting units . illustrates an example in which each converting unit and each queue of the message queues correspond to one another on a one to one basis however in other examples two or more converting units may correspond to two or more queues of the message queues . In other words the correspondence between the converting units and the queues of the message queues may be one to one or many to many.

Each converting unit may monitor the corresponding queue of the message queues . When a message is enqueued into the corresponding queue the converting unit may acquire the registered information of the data conversion request corresponding to the message from the job information management database . Each converting unit may acquire corresponding data stored in the shared file storage based on the URI included in the information of the data conversion request acquired from the job information management database .

Then each converting unit may convert the acquired data. Each converting unit may register the converted data in the shared file storage and rewrite and update the registered information of the data conversion request in the job information management database . In addition as described in detail below when two or more of the converting units are to cooperatively perform a data conversion process each of the converting units that completes data conversion may enqueue a new message into a next queue of the message queues corresponding to the next converting unit that is to perform data conversion.

The conversion process library may also perform a process of rewriting and updating information of a data conversion request registered in the job information management database . Further in the case of cooperating with another converting unit to perform a data conversion process the conversion process library may perform a process of inserting a new message after data conversion into a next queue of the message queues corresponding to the other converting unit that is to perform the next data conversion. For example the conversion engine may include the following 

Next an exemplary flow of the asynchronous conversion service provided by the asynchronous conversion server illustrated in is described with reference to . is a sequence chart illustrating exemplary operations of the asynchronous conversion server .

In step S the front end application sends a data conversion request job registration request with respect to data registered in the shared file storage to the data conversion request management unit of the data conversion system . That is the asynchronous conversion service is started when the front end application sends the data conversion request with respect to data stored in the shared file storage to the data conversion request management unit .

The data conversion request sent in step S may have a parameter indicating a type of data conversion such as type doc2rpcs embedded therein. Also the data conversion request may have a parameter such as a URI indicating the location of the data to be converted embedded therein.

In step S the data conversion request management unit that receives the data conversion request job may analyze the job and determine whether there is a converting unit that executes data conversion matching the type of data conversion of the data conversion request. When there is a converting unit that executes data conversion matching the type of data conversion of the data conversion request the data conversion request management unit may register the job in a queue of the message queues corresponding to such converting unit .

In step S the data conversion request management unit returns a job registration result to the front end application . In the following descriptions it is assumed that the job has been registered in a queue of the message queues corresponding to a first converting unit of the converting units . The queue corresponding to the first converting unit queues jobs that may be processed by the first executing unit .

In step S the first converting unit which monitors its corresponding queue detects that a job has been added registered to its corresponding queue. In step S the first converting unit acquires information of the job registered in the queue from the job information management database .

The first converting unit analyzes a task included in the acquired job information and splits the task into plural types of tasks data conversion tasks that may be processed by the converting units . For example the process of splitting a task into plural types of task in step S may be performed as illustrated in .

Accordingly the front end application arranges for a plurality of the converting units to cooperatively perform the data conversion html2rpcs. For example the front end application may register the job with the task html2rpcs in the queue of the message queues corresponding to the first converting unit which can split the task html2rpcs into two tasks html2pdf and pdf2rpcs. The first converting unit upon detecting that the job has been registered in its corresponding queue may split the task html2rpcs into two tasks html2pdf and pdf2rpcs. Then the first converting unit may re register the job as a job including the two tasks html2pdf and pdf2rpcs in a queue corresponding to the type of data conversion to be performed as a next task. In this way data conversion may be performed through cooperation of a plurality of converting units .

In the present example the first converting unit that is capable of splitting the task html2rpcs into two tasks html2pdf and pdf2rpcs is used to change the job format of into a job format as illustrated in . The job format illustrated in includes the two tasks html2pdf and pdf2rpcs split from the task html2rpcs. 

The first converting unit generates a job including tasks for types of data conversion that may be performed by the second converting unit and the third converting unit from a job including a task for a type of data conversion that cannot be performed by any of the converting units . By generating a job including tasks for types of data conversion that may be performed by the second converting unit and the third converting unit the first converting unit may enable the second converting unit and the third converting unit to cooperatively perform a data conversion process.

Referring back to in step S the first converting unit registers the job including the split tasks in a queue corresponding to one of the converting units that is configured to perform the type of data conversion designated as a next task e.g. html2pdf . In step S the second converting unit which monitors its corresponding queue that accepts jobs executable by the second converting unit detects that a job has been registered in its corresponding queue.

In step S the second converting unit acquires job information of the job registered in its corresponding queue from the job information management database . The second converting unit analyzes the acquired job information and acquires data from the shared file storage based on a URI included in information of a first task at the front of the queue. Then the second converting unit performs data conversion on the acquired data according to the type of data conversion designated by the information of the first task.

After converting the data the second converting unit registers or updates the converted data in the shared file storage . Also the second converting unit updates job information of the relevant job registered in the job information management database to indicate that the second converting unit has converted the data. For example the status of the data conversion request job may be updated to data conversion in progress. 

Then in step S the second converting unit deletes the information of the first task processed task from the job information and registers the job including the remaining tasks in a queue corresponding to one of the converting units that is configured to perform the type of data conversion designated as the next task e.g. pdf2rpcs .

In step S the third converting unit which monitors its corresponding queue that accepts jobs executable by the third converting unit detects that a job has been registered in its corresponding queue. In step S the third converting unit acquires the job information of the registered job from the job information management database .

The third converting unit analyzes the acquired job information acquires data stored in the shared file storage based on a URI included in information of a first task at the front of the queue and performs data conversion on the acquired data according to the type of data conversion designated in the information of the first task.

After converting the data the third converting unit registers or updates the converted data in the shared file storage . Also the third converting unit updates job information of the relevant job registered in the job information management database to indicate that the third converting unit has converted the data. For example the status of the data conversion request job may be updated to data conversion completed. Then in step S the third converting unit deletes the information of the first task processed task from the job and because the job information includes no more subsequent tasks to be executed the third converting unit ends the process without registering the job in another queue.

According to an aspect of the present embodiment by performing the above described operations even when a converting unit that is capable of directly converting data according to a data conversion request is unavailable a new converting unit that is capable of such direct conversion does not have to be prepared and instead a plurality of existing converting units may be arranged to cooperatively process the data conversion request.

As described above the number of types of data conversion that may be requested may increase after the data conversion system is launched. The present embodiment may be capable of flexibly adapting to such a situation as illustrated in .

Also according to another aspect of the present embodiment the front end application may register a job as that including only one task to be executed by one of the converting units . That is the front end application need not treat the job as that including a plurality of tasks to be executed by a plurality of the converting units and the job may still be executed through cooperation of the plurality of the converting units .

Note that the converting units are not limited to the examples described above. In other examples a converting unit that is capable of converting a barcode image data into character string data a converting unit that is capable of performing an OCR process on data of an image file to convert the data into character string data and converting units capable of performing other types of conversion processes may be provided. Note also that embodiments of the present invention may be combined to the extent practicable.

In the following a second embodiment of the present invention is described. Note that features of the second embodiment that overlap with those of the first embodiment are given the same reference numerals and their descriptions are omitted.

In step S the MFP as an exemplary input end apparatus may generate image data image file by scanning a document for example. In step S the MFP uploads the generated image file to the server on the cloud .

In step S the server performs an OCR process on the uploaded image file to convert the image file into a text file. In step S the server stores the converted text file in an online storage on the cloud . Note that the types of the online storage provided over the cloud are expected to increase in the future.

Accordingly the same problems as those encountered in the case of performing data conversion for cloud printing as described above are encountered in the case of performing an OCR process on an image scanned by the MFP at the cloud side and storing the processed data in an online storage provided by another cloud service.

The process of performing an OCR process on an image file and storing the processed data in an online storage as illustrated in may be implemented by a cloud computing type information processing system as illustrated in for example. is a block diagram illustrating an exemplary configuration of an information processing system for implementing the process of performing an OCR process on an image file and storing the processed data in an online storage.

In the MFP is provided at the local side. The MFP is connected to a network such as the Internet via the firewall . The cloud side includes a process execution system a job management server the reverse proxy the authentication server and the authentication database .

The information processing system as illustrated in differs from that illustrated in in that the local side does not include the PC the data conversion system is replaced by the process execution system and the print job management server is replaced by the job management server . The process execution system of may execute various types of processes including performing an OCR process on an image file storing a text file in an online storage and the data conversion processes described above in connection with the first embodiment.

The process execution system includes an asynchronous process server a shared file storage and a job information management database . Note that the shared file storage may be identical to the shared file storage of the first embodiment and the job information management database may be identical to the job information management database of the first embodiment.

The process execution system and the job management server manage register jobs that are uploaded by the MFP corresponding to a local side apparatus. The process execution system performs an OCR process on an image file included in a job to convert the image file into a text file. The process execution system stores the stores the text file converted from the image file by the OCR process in the online storage . Note that a job uploaded by the MFP includes an image file of an image scanned by the MFP .

In order to accommodate various process execution requests and flexibly adapt to an increase in the number of types process execution requests the process execution system according to the present embodiment may have a configuration as described below for example.

The job management server may include a function to receive a job sent from the input end apparatus such as the MFP and to register a file such as an image file included in the job to the shared file storage for example. In addition the job management server may determine a process that needs to be executed and control the process execution system to execute the required process.

The process execution system defines tasks that make up a process of a job and treats the job as a plurality of tasks. The process execution system registers jobs in the message queues to have the executing units execute the processes requested by the jobs. The executing units may be implemented by a worker for example. For example the executing unit may perform an OCR process on an image file sent from an input side apparatus such as the MFP and store the processed data in the online storage .

The front end application may include a function to determine the required process. The front end application may embed the type of process required as a parameter in a process execution request job to be sent to the asynchronous process server . Similarly front end application may embed a URI Uniform Resource Indicator of the image file on which a process is to be executed as a parameter in the process execution request.

In the asynchronous process server that receives the process execution request including at least the type of process and the URI of the image file the process execution request management unit may receive the process execution request and analyze the process execution request. The process execution request management unit may then enqueue the job message in one of the message queues according to the type of process being requested.

At the same time the process execution request management unit may register or update information relating to the process execution request in the job information management database in parallel with the operation of enqueuing the message into one of the message queues . The information registered in the job information management database may include the location of the relevant file such as the image file URI on the shared file storage the type of process included in the process execution request and a status of the process execution request for example.

The message queues may include queues corresponding to each of the plurality of executing units . illustrates an example in which each executing unit and each queue of the message queues correspond to one another on a one to one basis however in other examples two or more executing units may correspond to two or more queues of the message queues . In other words the correspondence between the executing units and the queues of the message queues may be one to one or many to many.

Each executing unit may monitor its corresponding queue of the message queues . Upon detecting that a message has been enqueued in its corresponding queue the executing unit may acquire job information of the process execution request corresponding to the queued message from the job information management database . Each executing unit may acquire corresponding data stored in the shared file storage based on the URI included in the job information of the process execution request acquired from the job information management database .

Then each executing unit may process the acquired data. Each executing unit may register the processed data in the shared file storage and rewrite and update the job information of the process execution request in the job information management database . In addition when two or more of the executing units are to cooperatively perform a process each of the executing units that completes a relevant process may enqueue a new message into a next queue of the message queues corresponding to the next executing unit that is to perform a next process.

The process library may also perform a process of rewriting and updating information of a process execution request registered in the job information management database . Further in the case of cooperating with another executing unit to perform a process the process library after completing a relevant process may enqueue a new message in a next queue of the message queues corresponding to the other executing unit that is to perform a next process.

Next an exemplary flow of the asynchronous process service provided by the asynchronous process server illustrated in is described with reference to . is a sequence chart illustrating exemplary operations of the asynchronous process server .

In step S the front end application sends a process execution request job registration request with respect to data registered in the shared file storage to the process execution request management unit of the process execution system . That is the asynchronous process service is started when the front end application sends the data conversion request with respect to data stored in the shared file storage to the process execution request management unit .

The process execution request sent in step S may be have a parameter indicating a type of process such as type img2ocr embedded therein. Also the process execution request may have a parameter such as a URI indicating the location of the data to be processed embedded therein.

In step S the process execution request management unit that receives the process execution request job registration request may analyze the job and determine whether there is an executing unit that executes a process matching the type of process of the job. When there is an executing that executes a process matching the type of process of the job the process execution request management unit may register the job in a queue of the message queues corresponding to such executing unit .

In step S the process execution request management unit returns a job registration result to the front end application . In the following descriptions it is assumed that the job has been registered in a queue of the message queues corresponding to a first executing unit of the executing units . The queue corresponding to the first executing unit queues jobs that may be processed by the first executing unit e.g. process of performing an OCR process on an image file and storing the processed file in an online storage .

In step S the first executing unit which monitors its corresponding queue detects that a job has been registered in its corresponding queue. In step S the first executing unit acquires information of the job registered in the queue from the job information management database .

The first executing unit analyzes a task included in the acquired job information and splits the task into plural types of tasks that may be processed by the executing units . For example the process of splitting a task into plural types of task in step S may be performed as illustrated in .

Accordingly the front end application arranges for a plurality of the executing units to cooperatively perform the process img2storageA. For example the front end application may register the job with the task img2storageA in the queue of the message queues corresponding to the first executing unit which can split the task img2storageA into two tasks img2ocr and txt2storageA. After splitting the task the first executing unit may re register the job as a job including the two tasks img2ocr and txt2storageA in a queue corresponding to an executing unit that can execute the next task. In this way a process may be performed through cooperation of a plurality of executing units .

That is the first executing unit generates a job including types of tasks that can be processed by a second executing unit and a third executing unit from a job including a task that cannot be processed by the any of the executing units . In this way the first executing unit may enable the second executing unit and the third executing unit to cooperatively execute a process.

Referring back to in step S the first executing unit registers the job including the split tasks in a queue corresponding to one of the executing units that is configured to perform the type of process designated as a next task e.g. img2ocr . In step S the second executing unit which monitors its corresponding queue that accepts jobs executable by the second executing unit detects that a job has been registered in its corresponding queue.

In step S the second executing unit acquires job information of the job registered in its corresponding queue from the job information management database . The second executing unit analyzes the acquired job information acquires data from the shared file storage based on a URI included in information of a first task at the front of the queue and performs a process on the acquired data according to the type of process designated by the information of the first task.

The second executing unit then registers or updates the processed data in the shared file storage . Also the second executing unit updates job information of the relevant job registered in the job information management database to indicate that the second executing unit has converted the data. For example the status of the process execution request job may be updated to process in progress. 

Then in step S the second executing unit deletes the information of the first task processed task from the job information and registers the job including the remaining tasks in a queue corresponding to one of the executing units that is configured to perform the type of process designated as the next task e.g. txt2storageA .

In step S the third executing unit which monitors its corresponding queue that accepts jobs executable by the third executing unit detects that a job has been registered in its corresponding queue. In step S the third executing unit acquires the job information of the registered job from the job information management database .

The third executing unit analyzes the acquired job information acquires data stored in the shared file storage based on a URI included in information of a first task at the front of the queue and performs a process on the acquired data according to the type of process designated in the information of the first task. For example the third executing unit may execute a process of storing processed data in the online storage A. Also the third executing unit updates job information of the relevant job registered in the job information management database to indicate that the third executing unit has executed the above process. For example the status of the process execution request job may be updated to process completed. 

Then in step S the third executing unit deletes the information of the first task processed task from the job information and because the job information includes no more subsequent tasks to be executed the third executing unit ends the process without registering the job in another queue.

According to an aspect of the present embodiment by performing the above described operations even when an executing unit capable of directly performing a process corresponding to a process execution request is unavailable a new executing unit that is capable of executing such a process does not have to be prepared and instead a plurality of existing executing units process engines may be arranged to cooperatively process the process execution request.

As described above the number of types of process execution requests may increase after the process execution system is launched. The present embodiment may be capable of flexibly adapting to such a situation. Also according to another aspect of the present embodiment the front end application may register a job including only one task. That is the front end application need not treat the job as including a plurality of tasks to be executed by a plurality of the converting units but the job may still be executed through cooperation of the plurality of the converting units .

Note that the types of the executing units are not limited to the above described examples. Also embodiments of the present invention may be combined to the extent practicable.

In the following a third embodiment of the present invention is described for flexibly adapting to an increase in the types of processes such as data conversion processes. Note that the third embodiment is described below in connection with an exemplary case of flexibly adapting to an increase in the types of data conversion processes.

The network N1 may be a private network at the inner side of a firewall FW. The firewall FW may be set up at a node between the network N1 and the network N3 in order to detect and block unauthorized access. A client terminal portable terminals and an image forming apparatus such as a MFP may be connected to the network N1.

The client terminal is an example of a terminal apparatus. The client terminal may be implemented by an information processing apparatus having a general OS Operating System installed therein for example. The client terminal may include a wired or wireless communication unit for establishing communication via the network N1 for example. The client terminal may be implemented by a tablet PC a lap top PC or other types of terminals that may be operated by the user.

The portable terminal is an example of a terminal apparatus. The portable terminal may include a wired or wireless communication unit for establishing communication via the network N1 for example. The portable terminal may be implemented by a mobile or cellular phone such as a smart phone a tablet PC a lap top PC and other terminals that may be carried by the user.

The image forming apparatus is an example of an apparatus having an image forming function such as a MFP. The image forming apparatus may include a wired or wireless communication unit for establishing communication via the network N1 for example. The image forming apparatus may be an apparatus that performs a process related to image formation such as the MFP a copying machine a scanner a printer a laser printer a projector an electronic blackboard etc. In the example illustrated in one client terminal one portable terminal and one image forming apparatus are provided in the network N1 however a plurality of client terminals and or a plurality of portable terminals and or a plurality of image forming apparatuses may be provided in the network N1.

The client terminal and the portable terminal may correspond to the PC of the first embodiment. The image forming apparatus may correspond to the MFP of the first embodiment.

The network N2 may be connected to the network N3 via an access control apparatus . The security of the network N2 may be protected by the access control apparatus . A print service providing apparatus a scan service providing apparatus and other service providing apparatus may be connected to the network N2.

In the system illustrated in the access control apparatus the print service providing apparatus the scan service providing apparatus and the other service providing apparatus may form a service providing system. This service providing system may correspond to the data conversion system the print job management server the reverse proxy the authentication server and the authentication database of the first embodiment.

The access control apparatus may control login operations for gaining access to a print service provided by the print service providing apparatus and a scan service provided by the scan service providing apparatus for example.

Note that in some embodiments each of the access control apparatus the print service providing apparatus the scan service providing apparatus and other service providing apparatus may be implemented by one or more information processing apparatuses.

In other embodiments the access control apparatus the print service providing apparatus the scan service providing apparatus and other service providing apparatus may be integrated into a single information processing apparatus. Alternatively functions of the access control apparatus the print service providing apparatus the scan service providing apparatus and other services providing apparatus may be distributed and implemented by a plurality of information processing apparatuses.

Also a part of the services on the side of the network N2 may be provided at a location other than the network N2. The portable terminal may be provided in a network other than the network N1 such as the network within the office. In the system illustrated in the portable terminal is provided in the network N1 and in the network N3.

Each of the client terminal the portable terminal the access control apparatus the print service providing apparatus the scan service providing apparatus and the other service providing apparatus may be implemented by a computer system having a hardware configuration as illustrated in for example.

The input device may include a keyboard a mouse a touchscreen panel etc. The input device may be operated by the user to input various operation signals to the computer system . The display unit may include a display and may be configured to display information such as a process results of the computer system for example.

The communication I F provides an interface to connect the computer system to the networks N1 through N3. In this way the computer system may exchange data with an external device via the communication I F .

The HDD is an example of a nonvolatile storage unit that stores programs and data. The programs and data stored in the HDD may include the OS corresponding to basic software controlling the entire computer system and application software providing various functions on the OS for example.

The HDD may manage the programs and data stored therein in a predetermined file system and or a database DB . The external I F provides an interface between the computer system and an external apparatus. The external apparatus may include a recording medium or storage medium . In this way the computer system may perform a read operation and or a write operation with respect to the recording medium via the external I F . The recording medium may be a flexible disk a CD Compact Disk a DVD Digital Versatile Disk a SD Secure Digital memory card a USB Universal Serial Bus memory etc.

The ROM is an example of a nonvolatile semiconductor memory or memory device capable of storing programs and data even when power is turned off. The ROM may store programs and data including a BIOS Basic Input Output System that is executed when starting the computer system OS settings network settings etc. The RAM is an example of a volatile semiconductor memory or memory device capable of temporarily storing programs and data.

The CPU is a processing unit that controls overall operations of the computer system by reading the programs and data from storage devices such as the ROM and the HDD into the RAM and executing the programs for example.

The client terminal the portable terminal the access control apparatus the print service providing apparatus the scan service providing apparatus and the other service providing apparatus may each have the hardware configuration of the computer system as described above and be configured to implement the various processes described below for example.

The service providing system according to the third embodiment may be implemented by a software configuration as illustrated in for example. is a block diagram illustrating an exemplary functional configuration of a service providing system of the third embodiment.

The service providing system illustrated in may implement service applications a platform a management data storage unit and a platform API Application Programming Interface by executing one or more programs.

The service applications may include a print service application a scan service application and one or more other service applications for example. The print service application may provide a print service. The scan service application may provide a scan service. The other service application may provide some other service.

The platform API may provide an interface to enable the service applications such as the print service application the scan service application and the other service application to utilize the platform . The platform API may be a predefined interface that is provided for the platform to receive the request from the service application and may be implemented by a function or a class for example. In a case where functions of the service providing system are distributed to a plurality of information processing apparatuses the platform API may be implemented by a Web API for example that may be utilized via a network.

The platform may include an authentication processing unit an apparatus communication unit a session management unit a process control unit and a data process unit . The data process unit may include message queues and data format converting units .

The authentication processing unit corresponds to the authentication server of the first embodiment. The authentication processing unit may execute an authentication process based on a login request from an office apparatus such as the client terminal and the image forming apparatus . The office apparatus may be a generic name for the client terminal the portable terminal the image forming apparatus and other apparatuses and terminals at the office. The authentication processing unit may authenticate a user by referring to a user management information storage part which is described below. In addition the authentication processing unit may authenticate an apparatus such as the image forming apparatus by making referring to an organization management information storage part and an apparatus management information storage part for example.

The apparatus communication unit may establish communication with an office apparatus. The session management unit may manage a session with the office apparatus. The process control unit may control a data process executed by the data process unit based on a request from the service application . The data process unit may execute the data process under the control of the process control unit . The process control unit may correspond to the data conversion request management unit of the first embodiment. The message queues of the data process unit may correspond to the message queues of the first embodiment. The data format converting unit may correspond to the converting unit of the first embodiment.

The message queues may include queues corresponding to different types of data conversion processes which are described below. Each of the message queues may be configured to receive a message of a request for data conversion from the process control unit . Each of the data format converting units may be configured to monitor its corresponding queue. Upon detecting that a message has been enqueued in its corresponding queue each of the data format converting units may be configured to perform a corresponding process such as data conversion or splitting a task included in the data conversion request for example. Note that process operations of an asynchronous conversion service of the third embodiment are described in detail below.

The management data storage unit may include the organization management information storage part the user management information storage part the apparatus management information storage part a job management information storage part and a data storage .

The organization management information storage part may store organization management information which is described below. The user management information storage part may store user management information which is described below. The apparatus management information storage part may store apparatus management information which is described below. The organization management information storage part the user management information storage part and the apparatus management information storage part may correspond to the authentication database of the first embodiment.

The job management information storage part may correspond to the job information management database of the first embodiment and may store information relating to a data conversion request. The data storage may correspond to the shared file storage of the first embodiment and may store data such as an electronic document file included in a print job for example.

The service providing system may act as a cloud base or cloud that includes functions such as an authentication function and a data format converting function and a service group that provides services such as the print service by utilizing the functions of the cloud base. For example the cloud base may be implemented by the platform the management data storage unit and the platform API . For example the service group may be implemented by the service applications .

The authentication function of the cloud base of the service providing system may be implemented by the authentication processing unit and an authentication database for example. The authentication database may be implemented by the organization management information storage part the user management information storage part and the apparatus management information storage part for example.

The data format converting function of the cloud base of the service providing system may be implemented by the data process unit the job management information storage part and the data storage for example. The service group may provide services by utilizing the authentication function and data format converting function of the cloud base of the service providing system .

Also the service providing system illustrated in may aggregate the authentication function by managing the organization management information the user management information and the apparatus management information as management data to be shared by the plurality of service applications .

In certain examples information identifying an electronic medium e.g. IC card carried by the user may be used as the user ID. The electronic medium carried by the user is not limited to an IC card and may be a mobile or cellular phone a tablet terminal an electronic book terminal or some other type of device. The information identifying the electronic medium may be a card ID a serial ID a telephone number of the mobile or cellular phone or profile information of the terminal for example. A combination of two or more types of the above information may be used to identify the electronic medium as well.

In the following detailed process operations of the service providing system according to the third embodiment are described. Note that features of the present embodiment that may be identical to those of the first embodiment are given the same reference numerals and their descriptions may be omitted.

The service providing system of the third embodiment may have the following configuration in order to accommodate various types of data conversion requests and to flexibly adapt to an increase in the number of types of the data conversion requests. illustrates an exemplary functional configuration of a data conversion process implemented in the service providing system . illustrates an exemplary process flow of the data conversion process according to the third embodiment. Note that many features illustrated in may be substantially identical to those illustrated in so that overlapping descriptions may be omitted.

As illustrated in the service providing system may include a front end application that is a function of the print service application a data storage a process control unit message queues a job management information storage part and a plurality of data format converting units .

The process control unit the message queues the job management information storage part and the plurality of data format converting units may provide asynchronous data conversion services. In a cloud printing solution the front end application may have functions to receive a print job from the input end apparatus such as the client terminal and to register data such as an electronic document file included in the print job in the data storage . The front end application may determine a required file conversion and control the asynchronous data conversion services to execute data conversion processes.

The converted file may be registered in the data storage . When an output instruction for the print job is received from an output end apparatus such as the image forming apparatus the print service application may send the converted file registered in the data storage to the image forming apparatus corresponding to the sender of the output instruction.

The front end application may include a function to determine a file conversion required for executing the output instruction. The front end application may embed the type of data conversion required as a parameter such as doc2rpcs for example in a data conversion request to be sent to the process control unit . Similarly the front end application may embed the URI of data source data to be subject to the data conversion as a parameter indicating the location of the data in the data conversion request.

The process control unit may receive the data conversion request including at least the type of data conversion and the URI of the data. The process control unit may analyze the data conversion request and enqueue a message in a queue of the message queues with the matching type of data conversion.

At the same time the process control unit may register the information of the data conversion request in the job management information storage part in parallel with the above operation of enqueuing the message in a queue of the message queues . The information of the data conversion request registered in the job management information storage part may include the location of the file URI in the data storage the type of data conversion included in the data conversion request and the status of the data conversion request for example. The status of the data conversion request may be indicated as accepted executing completed etc. The status of the data conversion request may represent a status or progress of the data conversion process.

The message queues may include queues corresponding to the plurality of data format converting units . illustrates an example in which each data format converting unit and each queue of the message queues correspond to each other on a one to one basis however in alternative examples two or more data format converting units may correspond to two or more queues of the message queue . In other words the correspondence between the data format converting units and the queues of the message queue may be one to one or many to many.

Each data format converting unit may monitor its corresponding queue of the message queues . Upon detecting that a message has been enqueued in its corresponding queue the data format converting unit may perform a corresponding process such data conversion or splitting the data conversion request according to the enqueued message for example.

In the case of performing a data conversion process for example the data format converting unit may acquire data stored in the data storage based on the URI of the data included in the message and convert the acquired data. The data format converting unit may register the converted data in the data storage and update the information of the data conversion request registered in the job management information storage part .

In the case of splitting the data conversion request the data format converting unit may split the data conversion request into multiple data conversion processes to be executed in multiple stages and convert the data conversion request into multiple jobs corresponding to the multiple processes. As described above at least one of the plurality of data format converting units of the present embodiment may be configured to perform a process of splitting a data conversion request rather than performing a data conversion process. Note that the process of splitting a data conversion request is described in greater detail below.

The data conversion processes are split based on conversion engines included in the asynchronous data conversion service. The multiple jobs into which the data conversion request is split are enqueued in corresponding queues of the message queues according to the types of data conversion. Then corresponding data conversion processes may be performed in a manner similar to the data conversion process described above.

The correspondence between the queues of the message queues and the data format converting units may be set up as illustrated in for example. illustrates an exemplary correspondence between queues and data format converting units.

The message queues include a plurality of queues. The queues may be divided according to different types of data conversion processes such as doc2rpcs doc2 pcl etc. The data format converting units may operate on a Worker Node. For example the Worker Node may be implemented by a WINDOWS registered trademark server or a LINUX registered trademark server.

In one example two data format converting units may be arranged to operate on a single WINDOWS server while three data format converting units may be arranged to operate on a single LINUX server.

In the data format converting units operating on a WINDOWS registered trademark server are configured to perform data conversion processes doc2rpcs doc2 pcl pdf2rpcs and pdf2 pcl. Also the data format converting units operating on the LINUX server are configured to perform data conversion processes html2pdf and img2pdf. 

As illustrated in the data format converting unit may perform polling of jobs enqueued in a plurality of queues through a single connection. However the plurality of queues that may be polled by the data format converting unit in a single connection may be restricted to the corresponding queues of the data format converting units operating on the same OS server for example.

In the following a process of splitting a data conversion request for the data conversion process img2rpcs is described as an exemplary process of splitting a data conversion request. illustrate exemplary process steps of the process of splitting the data conversion request.

Note that the illustrated process from step S of and thereafter may be performed after the process control unit receives from the front end application the data conversion request including at least the type of data conversion img2rpcs and the URI of the data.

In step S the process control unit may register the data conversion request received from the front end application as a job in the management information storage part .

In step S the process control unit may submit or enqueue the data conversion request received from the front end application as a job Job a in the queue corresponding to the type of data conversion img2rpcs .

The data format converting unit corresponding to the type of data conversion img2rpcs monitors its corresponding queue and in step S acquires the job Job a enqueued in the corresponding queue subscribes to job . In step S the data format converting unit may perform a process corresponding to the acquired job Job a .

In the following detailed process operations of the data format converting unit in step S are described with reference to . illustrates exemplary process operations of step S. Note that in the data format converting unit is identified as a Worker. Also illustrates states of virtual task queues. A virtual task queue refers to a sequence or queue held within the Worker.

In 1 of the task queue includes a task img2rpcs corresponding to the job Job a acquired by the data format converting unit . In 2 of the data format converting unit corresponding to the type of data conversion img2rpcs adds to the task queue tasks img2pdf and pdf2rpcs that are required to perform the data conversion from the image file to the RPCS.

In 3 of the data format converting unit checks the first task img2rpcs at the front or head of the task queue and deletes dequeues the job Job a from the queue corresponding to the type of data conversion img2rpcs .

In 4 of the data format converting unit deletes the task img2rpcs at the front of the task queue. Then in 5 of the data format converting unit checks the task img2pdf at the front of the task queue and enqueues a job Job b into the queue corresponding to the type of data conversion img2pdf .

The deletion of the job Job a in 3 of and the enqueueing of the job Job b in 5 of may be performed by the process of step S illustrated in .

Referring back to after the job Job a is deleted and the job Job b is enqueued in step S enqueue dequeue job the data format converting unit corresponding to the type of data conversion img2rpcs may write an execution result of the job Job a to the job management information storage part in step S. After the execution result of the job Job a is written in step S the job management information may have a data configuration as illustrated in for example.

In step S of the data format converting unit corresponding to the type of data conversion img2rpcs may acquire the job Job b enqueued in the queue that is being monitored subscribe to job . In step S the data format converting unit may perform a process corresponding to the job Job b .

In the following the process operations of the data format converting unit in step S are described in detail with reference to . illustrates exemplary process operations of step S.

In 1 of the task queue includes tasks img2pdf and pdf2rpcs . In 2 of the data format converting unit corresponding to the type of data conversion img2pdf checks the first task img2pdf at the front of the task queue and performs a process that includes acquiring the file from the data storage opening the file converting the data of the file uploading the file and deleting dequeueing the job Job b .

In 3 of the data format converting unit deletes the first task img2pdf at the front of the task queue. In 4 of the data format converting unit checks the first task pdf2rpcs at the front of the task queue and enqueues a job Job c into the queue corresponding to the type of data conversion pdf2prcs .

The deletion of the job Job b in 2 of and the enqueueing of the job Job c in 4 of may be performed by the process of step S illustrated in .

Referring back to after the job Job b is deleted and the job Job c is enqueued enqueue dequeue job in step S the data format converting unit corresponding to the type of data conversion img2pdf may write an execution result of the job Job b to the job management information storage part in step S. After the execution result of the job Job b is written in step S the job management information may have a data configuration as illustrated in for example.

In step S of the data format converting unit corresponding to the type of data conversion pdf2rpcs may acquire the job Job c enqueued in the queue that is being monitored subscribe to job . In step S the data format converting unit may perform a process corresponding to the job Job c .

In the following operations of the data format converting unit in step S are described in greater detail with reference to . illustrates exemplary process operations of step S.

In 1 of the task queue includes task pdf2rpcs . In 2 of the data format converting unit corresponding to the type of data conversion pdf2rpcs checks the first task pdf2rpcs at the front of the task queue and performs a process that includes acquiring the file from the data storage opening the file converting the data of the file uploading the file and dequeueing the job Job c .

In 3 of the data format converting unit deletes the first task pdf2rpcs at the front of the task queue. When the task pdf2rpcs is deleted the task queue becomes empty. The dequeuing of the job Job c in 2 of may correspond to step S of .

Referring back to after the job Job c is dequeued in step S the data format converting unit corresponding to the type of data conversion pdf2rpcs may write the execution result of the job Job c to the job management information storage part in step S. After the execution result of the job Job c is written in step S the job management information may have a data configuration as illustrated in for example.

According to an aspect of the present embodiment a data conversion process may be executed through cooperation of a plurality of data format converting units . Thus even when data format options before conversion and or after conversion are increased the number of data conversion engines that need to be prepared to accommodate for such an increase may be reduced compared to a conventional data conversion system. That is the present embodiment may flexibly adapt to an increase in the number of types of data formats that need to be handled as data formats before conversion and or after conversion.

Note that although a data conversion process is described above as an exemplary application of the third embodiment aspects of the third embodiment may also be applied to other various types of processes such as a process of performing an OCR process on an image file and storing the processed file in an online storage as described above in connection with the second embodiment. In this case the data format converting units may be replaced by the executing units as described above in connection with the second embodiment.

In one preferred embodiment the executing units may be configured to execute a process requested by a process execution request and also execute a next process that is expected to be requested e.g. preview process in the background for example.

In another preferred embodiment the converting units of the first embodiment the executing units of the second embodiment and the data format converting units of the third embodiment may be configured to cooperatively execute a process. In this way for example the following processes may be performed 

In the above first through third embodiments jobs are processed in the order in which they are received. In contrast in a fourth embodiment of the present invention certain jobs may be given higher priority over other jobs and jobs may be processed based on priority. For example users may be divided into general users and premium users and jobs of premium users may be prioritized over jobs of general users. In another example jobs may be divided into jobs requiring a short processing time and jobs requiring a long processing time and the jobs requiring a short processing time may be prioritized over jobs requiring a long processing time.

Note that the fourth embodiment is described below with reference to an exemplary case of assigning priority to the processing order of jobs in the data conversion system according the first embodiment. However priority may similarly be assigned to jobs in the process execution system of the second embodiment and the data conversion system of third embodiment for example. Note that features of an exemplary data conversion system according to the fourth embodiment that may be identical to those of the first embodiment are given the same reference numerals and their descriptions may be omitted.

First referring to the data conversion system that does not assign priority to the processing order of jobs is described. is a block diagram illustrating an exemplary configuration of the data conversion system that does not assign priority to the processing order of jobs.

Note that the data conversion system illustrated in corresponds to the data conversion system illustrated in . However in illustrations of the shared file storage and the job information management database are omitted and the converting units are represented as workers .

As illustrated in the data conversion system has jobs registered in the message queues and has the workers process the jobs one by one. In the example illustrated in the message queues include queues corresponding to the types of data conversion doc2rpcs and pdf2rpcs . Also in the workers are configured to be capable of executing the data conversion processes doc2rpcs and pdf2rpcs .

The front end application embeds a parameter indicating a required type of data conversion such as type doc2rpcs in a data conversion request job to be sent to the asynchronous conversion server .

The data conversion request management unit of the asynchronous conversion server that receives the data conversion request analyzes the received data conversion request and enqueues the job message in the queue of the message queues corresponding to the type of data conversion doc2rpcs matching the type of data conversion included in the data conversion request.

In the following descriptions it is assumed that Job 1 and Job 3 are jobs of general users and Job 2 and Job 4 are jobs of premium users. As illustrated in in the data conversion system that does not assign priority to the processing order of jobs the jobs of generals users and the jobs of premium users are all enqueued in the same queue and the jobs are processed in the order in which they are enqueued in the queue. Note that such indiscriminate processing of jobs may similarly be implemented in a case where there are jobs requiring a short processing time and jobs requiring a long processing time for example.

That is the workers monitor the queues corresponding to the types of data conversions doc2rpcs and pdf2rpcs and process the jobs in the order in which they are enqueued in the queues being monitored.

Next referring to the data conversion system that assigns priority to the processing order of jobs is described. is a block diagram illustrating an exemplary configuration of the data conversion system that assigns priority to the processing order of jobs.

Note that the data conversion system illustrated in corresponds to the data conversion system illustrated in . However in illustrations of the shared file storage and the job information management database are omitted and the converting units are represented as workers .

The message queues of the data conversion system illustrated in include queues for general users and queues for premium users. That is in the message queues include queues for general users corresponding to the types of data process doc2rpcs and pdf2rpcs and queues for premium users corresponding to the types of data process doc2rpcs and pdf2rpcs .

Note that in the queue for general users corresponding to the type of data conversion doc2rpcs is represented as queue doc2rpcs . The queue for general users corresponding to the type of data conversion pdf2rpcs is represented as queue pdf2rpcs .

Also the queue for premium users corresponding to the type of data conversion doc2rpcs is represented as queue doc2rpcs prem . The queue for premium users corresponding to the type of data conversion pdf2rpcs is represented as queue pdf2rpcs prem .

Also the data conversion system illustrated in includes workers prioritizing premium users and a worker prioritizing general users. Note that in the workers prioritizing premium users and the worker prioritizing general users are capable of performing the same types of data conversion processes but differ in the manner they select jobs to be processed from the queues.

For example in the worker prioritizing general users gives priority to processing jobs enqueued in the queues for general users. The workers prioritizing premium users give priority to processing jobs enqueued in the queues for premium users. Note that in each of the workers illustrated in the queues of the message queues are listed according to the order of priority in which they are to be processed.

As illustrated in by providing a greater number of workers prioritizing premium users compared to the number of workers prioritizing general users processing of a job enqueued in a queue for premium users may be prioritized over a job enqueued in a queue for general users even in a case where the job in the queue for general users is enqueued earlier.

Note that in a case where no job is enqueued in the queues for premium users the workers prioritizing premium users may process jobs enequeued in the queues for general users. In this way a situation in which the workers remain idle even when jobs to be processed are enqueued may be avoided and operation efficiency may be improved.

Similarly in a case where no jobs are enqueued in the queues for general users the worker prioritizing general users may process jobs enqueued in the queues for premium users. In this way a situation in which the worker remains idle even when jobs to be processed are enqueued may be avoided and operation efficiency may be improved.

The front end application embeds a parameter indicating a required type of data conversion such as type doc2rpcs in a data conversion request job to be sent to the asynchronous conversion server .

The data conversion request management unit of the asynchronous conversion server that receives the data conversion request analyzes the received data conversion request and determines whether the data conversion request is from a general user or a premium user. The determination of whether the data conversion request is from a general user or a premium user may be made based on an identifier included in the data conversion request or user identification information such as a user ID included in the data conversion request for example. In one example user identification information such as a user ID may be registered in the authentication database in association with information indicating whether the user is a general user or a premium user. In this way a general user may be prevented from impersonating as a premium user for example.

In a case where the data conversion request management unit determines that the data conversion request is from a general user the data conversion request management unit sorts enqueues the job message into a queue for general users corresponding to the type of data conversion matching the type of data conversion included in the data conversion request. In a case where the data conversion request management unit determines that the data conversion request is from a premium user the data conversion request management unit sorts the job into a queue for premium users corresponding to the type of data conversion matching the type of data conversion included in the data conversion request.

In the example illustrated in Job 1 through Job 3 as jobs from generals users are sorted into the queue doc2rpcs for general users. Also Job 1 through Job 5 as jobs from premium users are sorted into the queue doc2rpcs prem . The job Job 1 sorted into the queue for general users is being processed by the worker prioritizing general users. The jobs Job 1 through Job 3 sorted into the queue for premium users are being processed by the workers prioritizing premium users.

In the data conversion system that assigns priority to the processing order of jobs a job of a general user and a job of a premium user may be enqueued in different queues so that processing of the job of the premium user may be prioritized over the job of the general user.

Note that although the data conversion request management unit is configured to sort jobs into different queues based on the type of user in the above example the data conversion request management unit may also be configured to sort jobs into different queues based on other factors such as the type of organization e.g. whether an organization issuing the data conversion request corresponds to a general organization or a premium organization .

According to an aspect of the present embodiment the processing order of jobs may be altered based on priority assigned to the jobs. For example by assigning priority to processing jobs of premium users over jobs of general users utility value of premium users may be improved for example. Also by assigning priority to processing jobs requiring a short processing time over jobs requiring a long processing time a situation may be avoided in which a job requiring only a short processing time has to wait for the completion of a job requiring a long processing time and user convenience may be improved for example.

Although the present invention has been described above with reference to certain embodiments the present invention is not limited to these embodiments and numerous variations and modifications may be made without departing from the scope of the present invention. Note that an executing unit of the present invention may be implemented by the converting unit the executing unit or the data format converting unit of the above described embodiments for example. A managing unit of the present invention may be implemented by the data conversion request management unit the process execution request management unit or the process control unit of the above described embodiments for example. A storing unit of the present invention may be implemented by the message queues and of the above described embodiments for example. A data storage device of the present invention may be implemented by the online storage of the above described embodiments for example.

