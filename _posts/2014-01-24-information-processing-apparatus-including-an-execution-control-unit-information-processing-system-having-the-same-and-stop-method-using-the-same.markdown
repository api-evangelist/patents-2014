---

title: Information processing apparatus including an execution control unit, information processing system having the same, and stop method using the same
abstract: An information processing apparatus includes a first preservation unit configured to preserve execution request information for information processing; an execution unit configured to execute one or more types of the information processing; an execution control unit configured to have the execution unit being capable of executing one of the types of the information processing execute the information processing of the execution request information preserved by the first preservation unit; and a second preservation unit configured to preserve a stop command of the execution unit. If the execution unit does not execute the information processing, the execution control unit checks the second preservation unit if the second preservation unit preserves the stop command to have the execution unit execute a stop procedure.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09317396&OS=09317396&RS=09317396
owner: RICOH COMPANY, LTD.
number: 09317396
owner_city: Tokyo
owner_country: JP
publication_date: 20140124
---
The disclosures herein generally relate to an information processing apparatus an information processing system and a stop method.

Conventionally a technology is known in that a client sends a print command to a server then the server that received the print command converts content to be printed into print data. In such a technology a server provides a service for generating print data to a client.

In recent years cloud computing has been drawing attention which is a form of providing services from a server to a client as described above. In cloud computing many computing resources are used for distributed execution of data conversion and data processing to process a considerable number of requests from clients. There are too many vendors that provide various services by implementing web services in cloud computing environments for realizing cloud computing as described above see for example Patent Document 1 .

A server executing data conversion may use for example a data conversion engine a data conversion program data conversion library and the like to improve independence and maintainability of the program.

Also a server executing some sort of processing other than data conversion may use a data processing engine a data processing program data processing library and the like to improve independence and maintainability of the program.

If multiple types of data conversion and or data processing are required a considerable number of data conversion engines and data processing engines are required. For an information processing system in production use using such data conversion engines and or data processing engines it is common to stop the information processing system when updating the data conversion engines and or data processing engines.

A problem of the information processing system using the data conversion engines and or data processing engines is that it is not easy to update the data conversion engines and or data processing engines because the entire information processing system needs to be stopped.

In view of the above it is a general object of at least one embodiment of the present invention to provide an image processing apparatus an information processing system and a stop method that can easily update a program included in the information processing system in operation.

According to at least one of embodiments of the present invention an information processing apparatus includes a first preservation unit configured to preserve execution request information for information processing an execution unit configured to execute one or more types of the information processing an execution control unit configured to have the execution unit being capable of executing one of the types of the information processing execute the information processing of the execution request information preserved by the first preservation unit and a second preservation unit configured to preserve a stop command of the execution unit. If the execution unit does not execute the information processing the execution control unit checks the second preservation unit if the second preservation unit preserves the stop command to have the execution unit execute a stop procedure.

According to at least one embodiment of the present invention it is possible to easily update a program included in an information processing system in operation.

In the following embodiments of the present invention will be described with reference to the accompanying drawings.

The network N is a private network behind a firewall FW. The firewall FW is installed at a contact point between the network N and the network N and detects and blocks unauthorized access. To the network N a client terminal a mobile terminal and an image forming apparatus such as a multifunction peripheral are connected.

The client terminal is an example of a terminal device. The client terminal is realized by an information processing apparatus in which a typical OS is installed. The client terminal includes a unit for performing radio communication or a unit for performing cable communication. The client terminal is a terminal that can be operated by a user such as a tablet PC and a notebook PC.

The mobile terminal is an example of a terminal device. The mobile terminal includes a unit for performing radio communication or a unit for performing cable communication. The mobile terminal is a terminal that is portable for a user such as a smartphone a mobile phone a tablet PC and a notebook PC.

The image forming apparatus is a device having an image forming function such as a multifunction peripheral. The image forming apparatus includes a unit for performing radio communication or a unit for performing cable communication. The image forming apparatus is a device for performing processes relevant to image formation such as a multifunction peripheral a copier a scanner a printer a laser printer a projector and an electronic blackboard. illustrates an example including one of each of the client terminal the mobile terminal and the image forming apparatus . There may be a plurality of each of these devices.

The network N is connected with the network N via an access control device . The security of the network N is protected by the access control device . To the network N a print service providing device a scan service providing device and another service providing device are connected.

In the information processing system of the access control device the print service providing device the scan service providing device and the other service providing device realize the service providing system. The print service providing device the scan service providing device and the other service providing device provide a print service a scan service and other services respectively.

The access control device controls a log in operation to a print service provided by the print service providing device and a scan service provided by the scan service providing device .

The access control device the print service providing device the scan service providing device and the other service providing device are realized by one or more information processing apparatus.

The access control device the print service providing device the scan service providing device and the other service providing device may be realized by being integrated in a single information processing apparatus or may be realized by being distributed across a plurality of information processing apparatuses.

Part of the services on the network N side may be outside the network N. The mobile terminal may be outside the network N that is a network inside the office. In the example of the information processing system of the mobile terminal is in the network N and in the network N.

An online storage connected with the network N is a device for preserving files. The online storage may be a device for preserving files provided by a vendor.

The configuration of the service providing system of is one example. The service providing system may be realized by a configuration illustrated in . is a configuration diagram of another example of the service providing system. In the service providing system of the network N is connected to the network N by a firewall FW.

In the network N service providing devices of a SaaS Software as a Service system service providing devices of a common service Network Service Platform system and storage devices of the storage system are connected. The service providing devices of the common service system provides services that can be commonly used by the service providing devices of the SaaS system.

The service providing devices of the SaaS system include service providing devices according to the service to be provided such as a portal service providing device a print service providing device and a scan service providing device . Furthermore the service providing devices of the common service system include service providing devices according to a common service to be provided such as an authentication service providing device a data process service providing device and a temporary data saving service providing device . The storage devices of the storage system include storage devices according to the information data to be stored such as an authentication information storage device a job information storage device and a temporary data storage device .

In the service providing system of security is protected by authentication services provided by for example the firewall FW and the authentication service providing device . Note that the configuration of the service providing system of is also one example and the service providing system may have other configurations.

The client terminal the mobile terminal the access control device the print service providing device the scan service providing device and the other service providing device are realized by for example a computer system having a hardware configuration as illustrated in .

The service providing devices of the SaaS system the service providing devices of the common service system and the storage devices of the storage system illustrated in may also be realized by for example a computer system having a hardware configuration as illustrated in .

The input device includes a keyboard a mouse and a touch panel which are used by a user for inputting operation signals. The display device includes a display etc. and displays processing results obtained by the computer system .

The communication I F is an interface for connecting the computer system to the networks N through N. Accordingly the computer system can perform data communication via the communication I F .

The HDD is a nonvolatile storage device storing programs and data. Examples of stored programs and data are an OS Operating System which is basic software for controlling the entire computer system and application software for providing various functions on the OS.

The HDD manages the stored programs and data by a predetermined file system and or a DB database . The external I F is an interface between the computer system and an external device. An example of the external device is a recording medium . Accordingly the computer system can read data from and or write data in the recording medium via the external I F . Examples of the recording medium are a flexible disk a CD Compact Disk a DVD Digital Versatile Disk an SD memory card and an USB memory Universal Serial Bus memory .

The ROM is a nonvolatile semiconductor memory storage device that can hold programs and data even after the power is turned off. The ROM stores programs and data such as BIOS Basic Input Output System that is executed when the computer system is activated OS settings and network settings. The RAM is a volatile semiconductor memory storage device for temporarily storing programs and data.

The CPU is a processor for loading the programs and data from storage devices such as the ROM and the HDD into the RAM and executing processes to control the entire computer system and to realize functions.

The client terminal the mobile terminal the access control device the print service providing device the scan service providing device and the other service providing device can realize various processes as described below by the hardware configuration of the computer system . Furthermore the service providing device of the SaaS system the service providing device of the common service system and the storage device of the storage system can also realize various processes as described below by the hardware configuration of the computer system . Note that descriptions of hardware configurations of the image forming apparatus and the firewall FW illustrated in are omitted.

The service providing system according to the first embodiment is realized by for example process blocks as illustrated in . is a process block diagram of an example of the service providing system according to the first embodiment.

The service providing system realizes applications common services a database DB and a platform API Application Programming Interface by executing programs.

The applications include for example a portal service application a scan service application and a print service application .

The portal service application is an application for providing a portal service. A portal service provides a service acting as an entrance for using the service providing system . The scan service application is an application for providing a scan service. The print service application is an application for providing a print application. The applications may include other service applications.

The platform API is an interface for using the common services by the applications by the portal service application the scan service application and the print service application . The platform API is an interface that is defined in advance which is provided for the common services to receive requests from the applications . The platform API is constituted by for example functions and classes.

The platform API is realized by for example a Web API that can be used via the network when the service providing system is constituted by a plurality of information processing apparatuses.

The common services include an authentication authorization unit an organization managing unit a user management unit a license management unit a device management unit a temporary image saving unit an image processing workflow control unit and a log collecting unit .

Furthermore the image processing workflow control unit includes a message queue and at least one worker . The worker realizes functions such as image conversion and image transmission.

The authentication authorization unit executes authentication authorization based on a log in request from office devices such as the client terminal and the image forming apparatus . The office device is a collective term of the client terminal the mobile terminal and the image forming apparatus .

The authentication authorization unit authenticates authorizes a user by accessing for example a user information storage unit and a license information storage unit described below. Furthermore the authentication authorization unit authenticates for example the image forming apparatus by accessing for example the organization information storage unit and the device information storage unit described below.

The organization managing unit manages organization information stored in an organization information storage unit described below. The user management unit manages user information stored in the user information storage unit described below.

The license management unit manages license information stored in the license information storage unit described below. The device management unit manages device information stored in a device information storage unit described below. The temporary image preservation unit saves temporary images in a temporary image storage unit described below and acquires temporary images from the temporary image storage unit .

The image processing workflow control unit controls a workflow relevant to image processing based on a request from the applications . The message queue includes a queue corresponding to the type of process. The image processing workflow control unit submits the message of the request relevant to the process job in the queue corresponding to the type of the job.

The worker monitors the corresponding queue. When a message is submitted in the queue the worker performs a process such as image conversion and image transmission according to the type of the corresponding job. Note that the submitted message may be subjectively read pulled by the worker or may be provided pushed from the queue to the worker . The image processing workflow control unit will be described later in detail.

The database includes a log information storage unit an organization information storage unit a user information storage unit a license information storage unit a device information storage unit a temporary image storage unit a job information storage unit and an application specific setting information storage unit .

The log information storage unit stores log information. The organization information storage unit stores organization information described below. The user information storage unit stores user information described below. The license information storage unit stores license information. The device information storage unit stores device information described below.

The temporary image storage unit stores temporary images. A temporary image is for example a file or data of a scan image to be processed by the worker . The job information storage unit stores information job information of a request relevant to a process job . The application specific setting information storage unit stores setting information specific to the application .

The service providing system functions as an integrated base for providing common services such as a workflow relevant to authentication authorization and image processing and a group of services providing application services by using the function of the integrated base such as a scan service a print service and a portal service. The integrated base is constituted with for example the common services the database and the platform API . The group of services is constituted with for example the applications .

Note that process blocks in the service providing system illustrated in are classified as an example. It is not a mandatory requirement for the applications common services and DB to be classified in the hierarchy illustrated in . It is not limited to a specific classification such as the hierarchical relationship illustrated in as long as processing for the service providing system can be executed according to the first embodiment.

The organization name is a name of a group such as a company and a department. The country represents a name of a country in which a group such as a company and a department resides. The language represents a language used by a group such as a company and a department. The address information represents mail addresses of a group such as a company and a department.

Furthermore as the user name information for identifying an electronic medium for example an IC card held by a user may be used. As such an electronic medium held by a user an IC card a mobile phone a tablet terminal and an electronic book terminal may be used. As the information for identifying an electronic medium a card ID a serial ID a telephone number of a mobile phone and profile information of a terminal may be used. The information for identifying an electronic medium may be used in combination.

The service providing system according to the first embodiment updates a worker in the service providing system in operation without influencing the service providing system . The service providing system according to the first embodiment updates a worker as illustrated in .

The worker server receives a command from a developer as an actor. The actor may be a person in charge of server maintenance or the like. The worker A and worker B in include a worker framework which will be described later. The worker A and worker B are activated processes. The worker A is a worker that does not processes a job. The worker B is a worker that processes a job whose execution is started at Step S.

At Step S the developer as the actor issues a command to stop the worker A and worker B. The stop command can be given by a command line or the like on a computer system in which the worker server is running or a client terminal or a portable terminal that is connected with the computer system for data communication.

At Step S in response to receiving the stop command to stop the worker A and worker B from the developer the worker server sets stop flags of the worker A and worker B ON. Setting the stop flag ON can be done for example by creating a file having a predetermined name in a predetermined file storage location such as a folder.

For example the worker server may set the stop flag of the worker A ON by generating a file named WorkerA exit.file in a predetermined folder. Also the worker server may set the stop flag of the worker B ON by generating a file named WorkerB exit.file in a predetermined folder.

Note that the method of generating a file in a predetermined file storage location to determine whether the worker A or worker B is to be stopped is an example of a method to set the stop flag ON. It is not limited to the method of generating a file as long as it is possible to determine whether the worker A or worker B is to be stopped.

At Step S the worker server checks whether an exit.file such as WorkerA exit.file still exists or not in the predetermined file storage location at predetermined intervals for example every five minutes to determine that every exit.file is deleted.

The worker server determines that the stop flag is set ON if the exit.file exists in the predetermined file storage location. In the worker server determines the stop flags of the worker A and worker B are set ON.

At Step S the worker A that does not process a job checks the stop flag of the worker server . Note that a function for checking the stop flag of the worker server is implemented in the worker framework .

The worker A that does not process a job checks the stop flag at predetermined intervals for example every minute . If determining that the stop flag is set ON the worker A executes a stop procedure which will be described later at Step S. Note that a function for stopping the worker is implemented in the worker framework . If determining that the stop flag is OFF the worker A checks the stop flag of the worker server again after the predetermined interval. At Step S the worker A deletes WorkerA exit.file in the predetermined file storage location of the worker server . After Step S the worker A stops.

At Step S the worker B that processes a job checks the stop flag at timing when the job processing is completed. If determining that the stop flag is set ON the worker B executes the stop procedure which will be described later at Step S.

If determining that the stop flag is OFF the worker B checks the stop flag of the workers again after the predetermined interval similarly to the worker A. At Step S the worker B deletes WorkerB exit.file in the predetermined file storage location of the worker server . After Step S the worker B stops.

If all exit.files are deleted in the predetermined file storage location the worker server determines that the worker A and worker B to be updated are stopped at Step S. The worker server indicates that all the workers to be updated are stopped to the developer as the actor. The indication to the developer as the actor may be done by displaying a string on a command line or with a dialogue.

At Step S the developer as the actor directs to update the worker A and worker B to be updated. At Step S the worker server rewrites programs of the worker A worker B and worker framework to update the worker A and worker B to be updated.

Note that at Step S the worker server may rewrite both of the programs of the worker and worker framework or may rewrite one of the programs. Also at Step S the worker server may rewrite programs of a part of workers among multiple workers . If updating a part of the workers among the multiple workers workers other than those to be updated may not be stopped.

In this way the service providing system according to the first embodiment can stop the worker B appropriately by waiting for the job is completed by the worker B that has been processing the job.

Therefore the service providing system according to the first embodiment can update the workers without causing an error in the job processed by the worker B and without affecting the service providing system in operation.

Note that although the stop flag is implemented by creating a file in the predetermined file storage location in the sequence chart in it can be implemented for example by a function for indicating ON OFF of the stop flag in response to a query made by the worker .

At Step S the worker indicates disconnection to the message queue . After the execution of Step S the message queue does not make a request for processing a job to the worker that is to be stopped. Note that if Step S is not executed there is a likelihood that the message queue makes a request for processing a job to the worker which may be left unprocessed.

At Step S the worker releases activated applications required for processing if there are any. The applications activated by the worker may remain activated if Step S is not executed.

If an application remains activated having a file opened it may lead to a problem in that the file cannot be opened by another application or applications cannot be activated at the same time. Also it is left in a state where a user file remains open which may cause a security problem.

At Step S the worker closes a file if the file has been opened. A file opened by the worker may remain open if Step S is not executed. If the file remains open it may lead to a fault in that the file cannot be opened. Also it is left in a state where a user file remains open which may cause a security problem.

At Step S the worker empties a temporary folder. Files in the temporary folder may cause a fault in that the files remain forever if Step S is not executed. Also if Step S is not executed it causes a fault in that the files cannot be deleted in the temporary folder. Moreover also it is left in a state where a user file remains in the temporary folder which may cause a security problem.

According to the stop procedure of the worker illustrated in the flowchart in the worker can be stopped appropriately without causing the problems described above. Note that the stop procedure illustrated in is an example and it may be replaced with for example a procedure including at least a part of steps in .

The service providing system according to the first embodiment can test and activate a worker in the service providing system in operation without affecting the service providing system . The service providing system according to the first embodiment tests and activates the worker as illustrated in .

Note that the worker server is in a state before production use and hence it can run the test program. Note that production use means a state where the worker running on the worker server is activated so that it receives messages from a user queue called a normal queue hereafter . The test program may be run on a test server provided separately from the worker server .

At Step S the developer as the actor directs the worker server to activate the worker A and worker B updated by the procedure described with the sequence chart in . Note that an activation for testing means a state where the worker A and worker B running on the worker server receive messages from a test queue called a dummy queue hereafter instead of the normal queue. The developer as the actor can specify whether to activate the worker A and worker B for production use or for testing for example by an argument when giving the direction to activate.

At Step S the worker server specifies the dummy queue and activates the worker A. At Step S the worker A makes a request for connecting with the dummy queue to the message queue . The message queue creates the dummy queue if it has not been created.

The message queue connects the worker A with the dummy queue. After the execution of Step S the worker A receives requests from the message queue for processing jobs related to messages entered into the dummy queue. Note that test jobs are registered into the dummy queue.

At Step S the worker server specifies the dummy queue and activates the worker A. At Step S the worker B makes a request for connecting with the dummy queue to the message queue .

The message queue connects the worker B with the dummy queue. After the execution of Step S the worker B receives requests from the message queue for processing jobs related to messages entered into the dummy queue.

Having the worker A and worker B activated the developer as the actor directs the test program of the worker server to test the worker A and worker B at Step S. Note that Steps S S which will be described later are repeated for the number of tests.

At Step S the test program of the worker server makes a request for registering job information to the image processing workflow control unit with specifying the dummy queue which is used for testing as a type of processing. Note that the job information received from the test program includes items for example illustrated in .

The job ID is information for identifying a job. The task ID is information for identifying a task. The parent job ID is provided for making a correspondence between a task and a job which is the same as the job ID in the part defining the job. Note that job information received by the image processing workflow control unit has the job ID task ID and parent job ID not specified.

The type represents a type of a procedure executed by the worker which is set depending on a function of the procedure. Note that in The type is set to dummy queue that represents testing.

The parameters Params are parameters that are required for an execution by the worker . In a folder ID a filename an organization ID a federation ID and a file are set as the parameters that are required for an execution of a procedure for preserving a file into the online storage .

The folder ID represents a folder in which a file is preserved. The filename represents the name of a file used when preserving the file. The organization ID and federation ID represent information for obtaining a token for connecting with the online storage from the authentication authorization unit . The file represents information for designating the original location of a file to be preserved into the online storage . For example the file is set to a URI that designates the storage location where a file of a scan image preserved in the temporary image storage unit .

Note that the parameters Params depend on the type of a procedure executed by the worker . The parameters Params are specific to the type of a procedure executed by the worker .

The user ID is information representing a user that makes a request for executing a job. The organization ID is information representing an organization that makes a request for executing a job. The application ID is information representing a request source that makes a request for executing a job such as the application . The URL for callback is information representing a callback destination. The cookie information required for the callback is the information used when making a callback to the request source.

At Step S the image processing workflow control unit registers job information of the test job to which a registration request has been made into the job information storage unit . The job information storage unit issues a job ID and a task ID of the registered job. The job information storage unit appends the issued job ID and task ID to the job ID task ID and parent job ID in the job information. Next the job information storage unit returns the job ID of the test job registered in the job information to the image processing workflow control unit .

At Step S the image processing workflow control unit analyzes whether it is a test job based on the type included in the job information. The image processing workflow control unit enqueues a request message related to the test job into the dummy queue of the message queue . Note that the message includes the job ID.

The image processing workflow control unit returns the job ID of the test job to the test program as a result of the job registration. At Step S the test program of the worker server waits for the completion of the test job.

The worker framework of the worker A monitors the dummy queue of the message queue . The worker framework of the worker A obtains the message registered into the dummy queue at Step S.

At Step S the worker framework obtains the job information of the job ID included in the obtained message from the job information storage unit . At Step S the worker framework directs to execute the test job to the worker A following the job information. The worker A processes the job following the direction to execute the job from the worker framework .

Also at Step S the worker framework of the worker A indicates the completion of the test job to the job information storage unit . The job information storage unit updates for example status information of the test job that has been completed.

At Step S the worker framework indicates the completion of the job to the test program of the worker server that is registered as the callback destination which is included in the part relating to the definition of a job in the job information. Note that if the cookie information required for the callback is set in the part relating to the definition of a job in the job information the worker framework can add the cookie information to the callback.

Next at Step S the test program evaluates the result of the job executed by the worker A as will be described later. The test of the worker B is substantially the same as the test of the worker A and its description is omitted.

At Step S the developer as the actor directs to stop the worker A and worker B. The procedure for stopping the worker A and worker B is the same as the sequence chart in and its description is omitted.

Having received the result of the test job if there are no problems the developer as the actor directs the worker server to activate the worker A and worker B for production use that have been updated by the procedure of the sequence chart in at Step S. At Step S the worker server activates the worker A with specifying the normal queue. At Step S the worker A makes a request for connecting with the normal queue to the message queue . The message queue newly creates the normal queue if not exits. The message queue connects the worker A with the normal queue.

After the execution of Step S the worker A receives requests from the message queue for processing jobs related to messages entered into the normal queue. Similarly to the worker A the worker B receives requests from the message queue for processing jobs related to messages entered into the normal queue.

Note that although the example in is described in which the worker A and worker B that have been updated by the procedure of the sequence chart in are tested before activation it is substantially the same for the worker A and worker B which have been added are tested before activation.

Evaluation executed by the test program at Step S uses for example an indication of the job completion as illustrated in .

The job information in includes a part defining a job and a part defining a task similarly to job information in . The part defining a job is similar to the job information in which is added with reserved elements that makes it possible to have arbitrary parameters in future.

Also the part defining a task is similar to the job information in although it defines two tasks. The first task is an example of the procedure for applying OCR to a scan image. The second task is an example of the procedure for preserving a generated file into the online storage .

The parameters Params included in the definition of the first task are parameters specific to the procedure for applying OCR to a scan image. The parameters specific to the procedure for applying OCR to a scan image include setting of file format after OCR setting of language with which OCR is applied setting of an image size of the file after OCR and the like.

The parameters Params included in the definition of the second task are parameters specific to the procedure for preserving a generated file into the online storage . The parameters specific to the procedure for preserving a generated file into the online storage include an URL that designates the storage location of a file stored in the online storage . In the example in the URL that designates the storage location of a file stored in the online storage is set to 1 which indicates that a result of the first task is to be used.

The parameters specific to the procedure for preserving a generated file into the online storage also include setting of a folder in which the file is preserved setting for obtaining a token to connect with the online storage from the authentication authorization unit .

Also the indication of the job completion illustrated in and includes a part defining a job a part defining tasks and a part defining execution results of the task.

The part defining a job includes a job ID an application ID an organization ID a user ID a status error information created date and time of the job updated date and time of the job a URL for callback cookie information required for the callback reserved elements and the like. The status is a status of the job which is set to received processing completed error or the like. The error information is set to information that indicates which type of an error occurs if the status indicates an error.

The part defining tasks include the part defining a task in and additional items of a task ID and a parent job ID. The part defining execution results of the task enumerates results of an execution of two tasks defined in the part defining tasks.

The definition of execution results of the first task includes the definition of the first task that is set in the part defining tasks in error information details of execution results started date and time of the task and the completion date and time of the task.

Details of the execution results include for example for the procedure for applying OCR to a scan image the URL that indicates the storage location of the file after execution the size of the file after execution and the like. Also detailed information of execution commonly provided across functions includes elapsed time for the task as a whole worker framework and worker elapsed time used by the engine worker and the like.

The definition of execution results of the second task includes the definition of the second task that is set in the part defining tasks in error information details of the execution results started date and time of the task and the completion date and time of the task. Details of the execution results include for example for the procedure for preserving a generated file into the online storage a name of the preserved file a file ID issued by the online storage an URL that designates the storage location of the preserved file and the like. Also detailed information of execution commonly provided across functions includes elapsed time for the task as a whole worker framework and worker elapsed time used by the engine worker and the like which are similar to the first task.

At Step S the test program evaluates the job result executed by the worker using the indication of the job completion illustrated in and a correspondence table describing correspondences between functions input values and expected values as illustrated in . is a schematic view illustrating an example of the correspondence table used for evaluating a job result by a worker.

The correspondence table in describes correspondences between functions of the worker input values for executing the functions of the worker and expected values of execution results included in the indication of the job completion. The test program reads expected values of execution results from the correspondence table in based on the function set to the type and an indication of the job completion and the input values set as parameters Params .

Next the test program compares the execution results included in the indication of the job completion with the expected values read from the correspondence table in to evaluate the job result by the worker . For example if the execution results included in the indication of the job completion are equivalent to the expected values read from the correspondence table in the test program determines that the job result by the worker is normal.

At Step S the developer directs the worker server to stop. When the worker stops the developer directs the worker server to update the worker . At Step S the developer directs the worker server to activate the worker that has been confirmed having no problems with the result of the test job. After activating the worker for testing at Step S the developer directs the test program of the worker server to test the worker activated for testing.

At Step S the developer determines the result of the job and if determining it is abnormal the problem is corrected at Step S and the procedure goes back to Step S. If the result of the test job is normal the developer directs the workers server to stop the worker that has been activated for testing at Step S. Next at Step S the developer performs an instruction to activate the worker for production use that has been confirmed having no problems by the result of test job.

The operational steps for updating testing and activating a worker by the developer can be automated by executing the test program of the worker server with batch processing. If the test program is executed with batch processing it is possible to consider for example that the worker is switched back to the one before update as a correction of a problem at Step S. Also if the test program is executed with batch processing instead of correcting a problem at Step S abnormality may be indicated to the developer to terminate the procedure in .

Asynchronous processing by the service providing system illustrated in will be described in detail. is a schematic view illustrating an example of asynchronous processing by the service providing system .

The application makes a request for preserving a file of a scan image uploaded from the image forming apparatus to the temporary image preserving unit . The temporary image preserving unit preserves the file of the scan image into the temporary image storage unit and returns a URI that designates the storage location of the file to the scan service application . The application makes a request for registering job information to the image processing workflow control unit . The image processing workflow control unit registers the job information to the job information storage unit . The job information storage unit issues a job ID of the job whose job information has been registered and returns the job ID to the image processing workflow control unit .

The image processing workflow control unit analyzes the type of processing from the type included in the job information. The image processing workflow control unit enqueues the message of the request related to the job into a queue of the message queue that coincides with the type of processing. The image processing workflow control unit analyzes the type of required processing and executes control for performing asynchronous processing.

The message queue includes multiple queues that correspond to types of processing. In a line connects a worker with a queue processed by the worker . As illustrated in a worker may process one or more queues. Also as illustrated in a queue may be processed by one or more workers .

For example in types processed by workers include doc2XXX pdf2XXX XXX2pdf storage2XXX ocr and pdf2XXX ocr . A worker that processes the type pdf2XXX ocr is an example of the worker that processes multiple types.

The worker framework that monitors the queues of the message queue detects the message of the request related to the job entered into the queue. The worker framework obtains the message registered into the queue. The worker framework is not illustrated in .

The worker framework obtains job information of the job ID included in the obtained message from the job information storage unit . The worker framework reads a URI that designates the storage location of the file of the scan image preserved in the temporary image storage unit .

Next the worker framework obtains the file of the scan image from the temporary image storage unit by specifying the URI that designates the storage location of the file of the scan image preserved in the temporary image storage unit .

The worker framework analyzes the type of processing from the obtained job information and directs the worker that has the coincident type of processing to execute the job. The worker that completes to execute the job returns an execution result of the job to the worker framework .

The worker framework indicates the job completion to the job information storage unit to update the status information of the completed job. Also the worker framework reads the URI for callback from the job information to indicate the job completion to the URL for callback.

The relationship between a queue in the message queue a worker and a worker framework can be represented for example as illustrated in .

Also the worker and worker framework operate on the worker servers A B. The worker servers A B are implemented with for example a Windows trademark server or a Linux trademark server.

For example the worker servers A B which may be Windows trademark servers have two workers operate. Also the worker servers A B which may be Linux trademark servers have three workers operate. As illustrated in the worker servers A B are loaded with the worker framework and multiple workers .

As illustrated in the worker framework can execute polling on multiple queues by a single connection. However a range of multiple queues for polling by the single connection is set to the range of the workers operating on the same OS server.

With the relationship among the queues in the message queue the workers and the worker frameworks as illustrated in the service providing system can implement asynchronous processing. Note that a relationship between a queue in the message queue a worker and a worker framework when updating testing and activating the worker can be represented for example as illustrated in .

Also the worker servers A B have the configuration of the worker servers A B in added with the test program. The worker servers A B in activate the workers for testing. Therefore in a line connecting the worker framework with the dummy queue represents that the worker processes the dummy queue.

With the relationship between the dummy queue of the message queue the worker the worker framework and the test program as illustrated in the service providing system can implement the procedure of the sequence chart illustrated in and .

With the service providing system according to the first embodiment it is possible to update or add test and activate a worker in the service providing system in operation without affecting the service providing system .

Also with the service providing system according to the first embodiment a mechanism can be implemented in which a dummy queue can be added dynamically and a queue processed by a worker can be changed dynamically.

With the service providing system according to the first embodiment by using a dummy queue it is possible to confirm operations of the workers in the service providing system in operation. In addition with the service providing system according to the first embodiment a worker that has been confirmed for the operations can be activated for production use.

Namely with the service providing system according to the first embodiment workers to be updated are stopped and separated one by one among the multiple workers within a redundant configuration which may be switched back to the redundant configuration after having confirmed the operations of the workers after update.

Moreover with the service providing system according to the first embodiment a worker to be updated can be stopped appropriately after the worker has completed a job.

The present invention is not limited to the specific embodiments described herein but variations and modifications may be made without departing from the spirit and scope of the present invention. Note that a first preservation unit in claims corresponds for example to a message queue . An execution unit corresponds for example to a worker . An execution control unit corresponds for example to a worker framework . A second preservation unit corresponds for example to a predetermined folder where a stop flag is implemented.

Execution request information corresponds for example to job information. An activation unit corresponds to the operation of Step S of a worker server . A registration unit corresponds to the operation of Step S of a worker server . An evaluation unit corresponds to the operation of Step S of a worker server .

The present application is based on and claims the benefit of priority of Japanese Priority Patent Application No. 2013 021263 filed on Feb. 6 2013 the entire contents of which are hereby incorporated herein by reference.

