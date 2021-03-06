---

title: Scoring server
abstract: A scoring server for assessing technical skills in a practical environment. A client application acts as a middle man between a terminal and an operating system to capture and forward all input from and output to students to the scoring server. The scoring server compares recorded student activity against a list of tasks deemed capable of accomplishing course objectives assigned to students. As objectives are met by a student, the students' grade is updated in real-time. Each student passes or fails an exam based on tasks performed and skills employed. The client application exists for two operating system types: WINDOWS® and LINUX®. A LINUX® client employs a pseudoterminal to permit access to terminal input/output and communication through stdin, stdout, and stderr channels. A WINDOWS® client (WC) comprises a WC command line activity logger and a WC monitor process to intercept all communication through stdin, stdout, and stderr communication channels.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09548000&OS=09548000&RS=09548000
owner: Telecommunication Systems, Inc.
number: 09548000
owner_city: Annapolis
owner_country: US
publication_date: 20140321
---
The present invention claims priority from U.S. Provisional No. 61 829 708 filed May 31 2013 entitled Scoring Server and from U.S. Provisional No. 61 803 986 filed Mar. 21 2013 entitled Scorebot the entirety of both of which are expressly incorporated herein by reference.

This invention relates generally to telecommunications and more particularly to cyber security and operations training.

Unlike typical academic training a large part of cyber security and operations training involves practical application of concepts and techniques. However there currently exists no recognized mechanism for assessing student technical skills in a practical environment. Consequently most technical training courses administer knowledge exams to evaluate student skill sets.

Most attempts to assess student skills in a practical application environment center around Capture the Flag CTF competitions. A conventional Capture the Flag CTF competition tracks activity of persons or teams attempting a given objective against other persons or teams attempting the same objective. For example if a goal of a Capture The Flag CTF competition is to maintain an active web server the Capture The Flag CTF system periodically checks to ensure student web servers are functional. Competing students teams may attempt to bring other students teams web servers down to prevent those students teams from earning points. If a students teams web server is brought down it is up to that student team to get their service up and running again

Unfortunately Capture the Flag CTF competitions do not include skill evaluation capabilities. For instance CyberNEXS is an exemplary Capture the Flag CTF product commercially manufactured by SAIC devoid of training skill evaluation capabilities. Hence in a Capture the Flag CTF competition with a goal of maintaining an active web server the Capture the Flag CTF system only checks to ensure web servers are running. The Capture the Flag CTF system has no way of assessing how quickly a problem is identified or how efficiently a problem is solved.

While Capture the Flag CTF competitions are fun they do not identify strengths and weaknesses of students nor do they assess skills toward a standard. The training industry is in dire need of a mechanism that can assess actual skills in a practical environment.

A method and apparatus for assessing technical skills in a practical environment comprises a scoring server aka a PerformanScore .

In accordance with the principles of the present invention a client application acts as a middle man between a terminal and an operating system to successfully capture all input from and output to a student undergoing evaluation in a practical training environment. The client application then transmits all recorded student activity to the scoring server which uses the recorded student activity to assess student technical skills in a practical environment.

In accordance with the principles of the present invention each student undergoing evaluation in a practical training environment is assigned one or more course objectives. To assess a student s performance the scoring server compares all activity recorded for the student against a list of tasks capable of accomplishing course objectives assigned to the student. If a command performed by a student meets a task deemed capable of accomplishing an objective assigned to that student the objective is marked as complete. As objectives are met by students grades are updated in real time.

When a student completes a practical exam the scoring server generates a report for the student that outlines all objectives met all objectives missed and a comprehensive final score. Students either pass or fail exams based on tasks performed and skills employed as opposed to simply knowledge memorized.

In accordance with the principles of the present invention client applications exist for two operating system types windows and LINUX . A client WC application comprises two individual components a WINDOWS client WC command line activity CLA logger and a WINDOWS client WC monitor process. The WINDOWS client WC intercepts all communication through standard in standard out and standard error communication channels of machines used to evaluate student performance.

Alternatively a LINUX client application comprises a pseudoterminal to permit access to terminal input output and communication through standard in standard out and standard error channels of machines used to evaluate student performance. Moreover the inventive LINUX client implements a well known system hooking tactic libhook.so to ascertain commands executed on machines and transparently retrieves command responses by creating a second pseudoterminal and linking the second pseudoterminal to a primary user terminal.

To attribute commands issued on target machines in a practical training environment to individual students a WINDOWS LINUX client application sends all commands issued on target machines to the scoring server along with a command process ID a timestamp host name network statistics netstat and a process list associated with the machine the command was executed on. Using information received in a netstat and process list the scoring server back traces to find an originating IP address for a command and then matches the IP address to a student ID.

The present invention provides a scoring server aka a PerformanScore to assess student technical skills in a practical environment.

In accordance with the principles of the present invention the inventive scoring server assesses student activity performed in a practical training environment against objectives related to student training.

Currently there exists no mechanism capable of assessing student technical skills in a practical environment. For instance in an exemplary course in penetration testing students are required to perform the following tasks conduct an external reconnaissance of a network port scan the network to find operational hosts identify applications running on hosts identify vulnerabilities within applications exploit application vulnerabilities to gain access to hosts and conduct a reconnaissance of the system and internal network to identify important information. Unfortunately traditional training courses are incapable of grading a student s ability to do such tasks and instead simply test students knowledge of such tasks. Traditional training courses thus promote data memorization and do not necessarily produce students capable of performing job functions.

The present invention scores students not only based on what they know but also based on what they do.

In accordance with the principles of the present invention the inventive scoring server utilizes a client application to capture all student activity performed during practical application exercises and exams. The client application acts as a middleman between a terminal and an operating system to successfully capture all input from and output to a student. The inventive client application then sends all recorded student activity to the scoring server located elsewhere on a system network and the scoring server uses recorded student activity to assess student performance. For example a client application captures all commands e.g. commands to initiate a port scan of a network performed by a student in a practical training environment and passes recorded commands and relevant command information e.g. command student host etc. to the scoring server . The scoring server then uses the recorded commands and relevant command information to evaluate the student s performance.

The inventive scoring server aka PerformanScore preferably comprises an apache web server with PHP and a MySql scoring server database to store and maintain student data course data and recorded student activity.

Course and student information is preferably uploaded to the scoring server via a scoring server web interface as depicted in . In particular the following course information is preferably stored in the scoring server course name course description associated rubric s . Moreover the following student information is preferably stored in the scoring server first name last name IP addresses assigned team commands issued on machines.

In particular as portrayed in students are preferably assigned IP addresses of machines and or virtual machines they will be using during performance evaluation to enable student commands to be linked back to IP addresses . Students can also be assigned to teams for which evaluation and scoring may be performed on a team or student basis. Student records are preferably organized in the scoring server database according to course .

Each course in the inventive scoring server system has an associated rubric for scoring and grading students . A course rubric preferably details specific objectives students are expected to complete and each objective is assigned a point value used to determine a student s score. Each objective additionally includes a task list which comprises tasks deemed capable of achieving that objective . Tasks are entered as a regular expression.

In accordance with the principles of the present invention to assess a student s performance during a practical exam training exercise the scoring server compares actions performed by the student and recorded by a client application against a list of tasks deemed capable of accomplishing course objectives assigned to that student a list of tasks is utilized to account for the many different ways in which a particular assignment may be accomplished . If a command performed by a student meets a task deemed capable of accomplishing one or more course objectives assigned to that student e.g. correct IP range options etc. the scoring server marks the objective s as complete and the student s grade is updated in real time. It is possible for a student to complete multiple objectives with one command as long as the command matches a task listed in each objective s task list . For each objective sections modules or content associated with the objective can be uploaded to the scoring server to aid student remediation.

A course administrator can review all commands executed by students via a scoring server web interface . If at any time an administrator feels that a command that failed to deem an objective complete does in fact complete the objective the administrator can mark the objective as complete and list the command in a task list associated with the objective .

The scoring server web interface also provides a course administrator the ability to view the commands executed by the students in realtime.

When a student completes a practical exam exercise the scoring server generates a report for the student that outlines all objectives met all objectives missed and a comprehensive final score.

The inventive scoring server additionally compiles command reports per class student and team. Commands in a command report are listed in chronological order and each command identifies a host machine on which the command was executed and initiated. A command report for a student team also displays a comprehensive final score compiled for that student team. A team command report depicts which students on a team completed which tasks. A report may also be generated to show what parts of training a student should review based on course objectives left incomplete.

Students either pass or fail exams based on tasks they performed and skills they employed rather than simply knowledge they memorized.

In accordance with the principles of the present invention client applications exist for two operating system types WINDOWS and LINUX . The WINDOWS client application intercepts communication on standard in standard error and standard out channels of machines used in a practical training environment. The WINDOWS client application forwards all data flowing from a student to a system and all data flowing from a system to a student to the scoring server via a secure communications channel.

In addition to standard in standard error and standard out communication channels LINUX machines occasionally use added channels of communication. These added channels unfortunately negate the effectiveness of a simple standard in standard out and standard error communication capture.

Thus to implement a client application in a LINUX or UNIX setting the present invention employs a pseudoterminal. A pseudoterminal for a LINUX client allows communication through standard in standard error and standard out channels of machines used in a practical training environment and additionally permits access to terminal input output. Terminal input output is used to pass terminal codes and secure terminal to terminal communication typically passwords . In accordance with the principles of the present invention the LINUX client forwards all data flowing from a student to a system and all data flowing from a system to a student to the scoring server via a secure communications channel. Both LINUX and WINDOWS client applications send commands responses and other information relevant to performance evaluation to the scoring server via a POST request.

In accordance with the principles of the present invention the scoring server stores commands and responses executed on multiple machines in a practical training environment each machine running a client application e.g. a WINDOWS LINUX client application . To attribute commands issued on target machines to individual students a WINDOWS LINUX client application sends all commands issued on target machines to the scoring server along with a command process ID a timestamp host name network statistics netstat and a process list ps associated with the machine the command was executed on. Netstat information includes local IP addresses and ports foreign IP addresses and ports and process IDs. A process list ps contains process IDs and parent process IDs.

Upon receipt of a command and relevant command information the scoring server saves the command command process ID command parent process ID host name and time stamp to a commands table in the scoring server database and then saves netstat and process list ps information in an appropriate manner.

In particular each line of a netstat is stored as an individual record in a netstat table see the database schema displayed in . Being that a netsat sent to the scoring server by a client application is a uniform resource locator URL encoded string the scoring server first decodes the string and then parses the decoded string by row. The scoring server parses data maintained in each row of a netstat into proper columns and then writes the information to a database . To link associated netstat rows together the server writes an associated command process ID host name and timestamp on each row. The scoring server stores the process list using the same process in a process list ps table .

Using information received in a netstat and process list ps the scoring server back traces to find an originating IP address for a command and then matches the IP address to a student ID see CLA attribution initiation in windowsclient.odt . The scoring server then updates the command record with the student ID to attribute the command to the student. In particular the client application preferably sends a response and attaches an original command process ID host name and timestamp associated with the command to the response. The response is then used to update the command record with student information.

In particular as depicted in the purpose of a scoring server LINUX client is to provide the scoring server with local command line activity CLA and to permit the scoring server to attribute local activity to a remote student.

The scoring server LINUX client utilizes multiple approaches that work in tandem to identify commands executed on a machine in a practical training environment computer responses and who executed what.

In particular to ascertain commands executed on a machine the inventive LINUX client implements a well known system hooking tactic libhook.so that places the client between a user and an operating system kernel. Using an LD PRELOAD hooking technique targeting an execve system call the LINUX client intercepts any attempt to start a new executable file the only way to launch a program legitimately in UNIX . The placement of the client application within the present invention allows interception of any command issued in a hooked terminal. The hooking approach can easily be expanded to intercept all actions including actions performed via a graphical user interface GUI .

To transparently retrieve command responses the inventive LINUX client creates a second pseudoterminal and links the second pseudoterminal to a primary user terminal. The terminal connection allows the LINUX client to intercept all communication to and from a student s terminal. The terminal connection is also able to ascertain commands executed on a machine. However the hooked system call method provides greater information better attribution and is scalable for future use within a graphical user interface GUI .

Moreover to attribute commands to individual students the LINUX client sends process and network information relevant to each command to the inventive scoring server . Since certain network and process information is privileged this component runs as a service in the background. This service additionally functions as a communications hub to coordinate communication between LINUX client application components and the scoring server .

In accordance with the principles of the present invention when a student enters a command at a scoring server prompt keystrokes pass transparently to the secondary pseudoterminal of the LINUX client. The pseudoterminal subsequently calls execve providing the location of the binary to run as well as any argument values specified by the student. The modified hooked call is then implemented which takes and forwards data for execve to the local administrative service server before handing the data to the actual execve system call. The administrative service then immediately sends data relevant to the command to the scoring server as it does not know when the command is going to end. The results of the binary come back to the pseudoterminal and the pseudoterminal forwards the response data to the administrative service before passing the response data back to the main terminal seen by the user. The administrative service keeps reading data from the pseudoterminal until a notification for a new command is received at which point the administrative service sends all response data for the previous command to the scoring server .

The inventive approach has evolved to include multiple release candidates. Some failed attempts at LINUX clients include 

1 A simple redirection pipe that allows the LINUX client to grab all data coming into a terminal on a standard input channel and all data leaving the terminal on a standard output channel. While this approach does meet many requirements it fails for the following reasons 

2 A single executable pseudoterminal that intercepts commands and responses and forwards them to the scoring server. This implementation fails because the pseudoterminal has trouble separating command response starts and stops and assumes a new command is launched every time a user selects an enter key an assumption that is unreliable an prone to abuse .

3 A hooked library and a pseudoterminal the first two components of the current solution . This implementation fails for the following reasons 

The current implementation of a LINUX client application supports communication and is capable of retrieving machine status command and response data from multiple users and multiple terminal WINDOWS . The inventive LINUX client tracks WINDOWS independently and allows any number of students to work on the same machine. The inventive LINUX client also reports all necessary information to the scoring server to permit successful differentiation of commands.

Command line activity CLA is a conventional term that refers to user initiated activity executed through a command line or shell. For example starting a command line cmd.exe and running ipconfig.exe constitutes command line activity CLA . Moreover TelNet ing into remote host server.remotehost.com and running ipconfig.exe constitutes command line activity CLA initiated from a user machine and executed on a remote machine server.remotehost.com . This combines direct user input with effects and accomplishments.

In accordance with the principles of the present invention the inventive WINDOWS client WC comprises two individual components a WINDOWS client WC command line activity CLA logger and a WINDOWS client WC monitor process.

The WINDOWS client WC command line activity CLA logger is responsible for recording streams of command line activity CLA executed on a WINDOWS machine and is not responsible for breaking up streams into individual commands. The WINDOWS client WC monitor process asynchronously consumes output from the WINDOWS client WC command line activity CLA logger as new process events are triggered.

The present invention aims to make WINDOWS client WC command line activity CLA logger actions completely transparent to users. All disclosed embodiments involve instrumenting cmd.exe. The WINDOWS client WC does not catch command line activity CLA streams on any other shells e.g. cygwin .

The inventive WINDOWS client WC is not a keystroke logger. A keystroke logger KS logs all keys that have been typed by a user onto a keyboard physically attached to a machine e.g. stu1 and is only capable of identifying machines on which sessions have been initiated not machines on which command line activity CLA is executed. However it is essential to know what machine command line activity CLA is initiated on and what machine command line activity CLA is executed on to determine what students users run what commands on what hosts.

As shown in session 1 is initiated on server and executed on server session 2 is initiated on stu2 and executed on server session 3 is initiated on stu1 and executed on redir and session 4 is initiated on stu1 and executed on server .

Since a keystroke logger KS is only able to identify machines on which sessions have been initiated a keystroke KS logger on server would only pick up information about session 1 and a keystroke logger KS on redir would not pick up any information. Information retrieved by a keystroke logger KS on stu1 and stu2 would include commands initiated on redir and server but would not distinguish that they ran on redir and server .

As portrayed in by instrumenting a single host the WINDOWS client WC can retrieve all command line activity CLA executed on the host . The WINDOWS client WC monitors all input and output of all instances of cmd.exe run on the host to obtain distinct streams of command line activity CLA . By gathering distinct streams of command line activity CLA a WINDOWS client WC is able to determine which parts of a command line activity CLA stream are executed locally. For example if a user SSH es into another machine and then executes several cat commands remotely the WINDOWS client WC can see that the ssh command was executed locally and that the cat commands were executed remotely. The inventive WINDOWS client WC also monitors process and network states to determine where command line activity CLA is initiated and executed.

In accordance with the principles of the present invention the WINDOWS client WC monitors process creation and ties command line activity CLA streams to process starts on machines in a practical training environment. Streams matched to process starts on a machine are known to be executed on that machine. The WINDOWS client WC also gathers network information about ancestor processes to determine whether a command line activity CLA stream process start was initiated locally or on a remote host.

In the following exemplary command line activity CLA stream a user SSH es into remote host housefire 

The entire exemplary command line activity CLA stream exemplified above is associated with a single ssh command performed on a local host. Dir and cat commands are executed remotely in the command line activity CLA stream and do not create new local processes. Thus dir and cat commands are ignored by the local WINDOWS client WC monitor process.

On the local host on which the command line activity CLA is initiated the entire command line activity CLA stream is perceived to be single command ssh executed on the local host.

The following depicts an exemplary command line activity CLA stream monitored from remote host housefire as a result of the previous command line activity CLA stream executed on the local host 

From the perspective of housefire the command line activity CLA stream includes events dir and cat which were executed on housefire.

By monitoring processes the WINDOWS client WC determines where command line activity CLA is executed.

Moreover to determine where command line activity CLA is initiated a WINDOWS client WC regularly reports a list of processes TCP UDP connections and new process creations performed on machines in a practical training environment. The WINDOWS client WC determines where a process is initiated by analyzing ancestor processes associated with the process. If ancestor processes of a process have open network connections that tie the process to a process with an active connection on another machine then the WINDOWS client WC concludes the process was initiated on the other machine.

For instance in the exemplary housefire command line activity CLA stream the scoring server obtains process information for dir on housefire along with process list and netstat information TCP UDP connection info . The server then determines that dir is owned by a bin bash process which is owned by sshd which has a connection to a WINDOWS host. The WINDOWS client WC monitor process is then checked which reports that ssh.exe is on the other side of the connection and the parent process is cmd.exe whose parent process is explorer.exe. So dir is determined to have initiated from a local WINDOWS machine. To attribute remotely initiated process starts to individual students this process is traced back over multiple hops to a machine associated with a student.

A priority of the present invention is to make WINDOWS client command line activity CLA logger activity completely transparent to users students. The following implementations exemplify approaches for achieving this all of which involve instrumenting cmd.exe 

In accordance with the principles of the present invention a new cmd.exe i.e. a wrapper around the original cmd.exe and executed as a subprocess can be created and the original cmd.exe can be left on disk with a different name or dropped to disk from the new cmd.exe. One downside of this approach is that both the original cmd.exe and the new cmd.exe wrapper appear in a process list which may look strange to users students. Another downside is that the approach does not preserve all cmd.exe behavior transparently which affects command history functionality.

A dll can be injected into cmd.exe at startup to replace stdout stderr handles with pipes to the injected code. An advantage of this implementation is that a dll injected into cmd.exe does not show up in a process list. However an injected dll may show up in a cmd.exe module list though less visible .

In accordance with the principles of the present invention an appinit dlls injection mechanism is used to inject a dll into a cmd.exe. Injection via appinit dlls is visible and changeable in the registry and serves to inject code into many unrelated processes. Code injection may alternatively be implemented via another process that is less apt to stand out.

A driver can be installed to monitor stdout stderr handles of all cmd.exe instances or child processes. This implementation is completely transparent and thus much less detectable to users.

In accordance with the principles of the present invention a WINDOWS client WC monitor process is implemented as a console application running on a client machine during a training exercise and can be implemented as a service. The WINDOWS client WC monitor process reports process information network information and input output information every time a new process is started or stopped on a machine .

In accordance with the principles of the present invention process events are handled via a WINDOWS management instrumentation WMI event listener. However this approach only works asynchronously and does not work well in WINDOWS 2000 and previous versions . It is thus possible for process information to disappear before it is processed a race condition so far not a real issue in practice . Limitations associated with the WINDOWS management instrumentation WMI event listener implementation may be solved by implementing process events synchronously with application programming interface API hooks or a driver.

In accordance with the principles of the present invention process and netstat information is reported every time a process terminates. The process and netstat tcp udp connection info information is gathered programmatically and does not trigger new process events. Process and netstat information can additionally be reported periodically or every time a state of network connections changes.

The WINDOWS client WC command line activity CLA logger and WINDOWS client WC monitor process components communicate via a file system. Each cmd.exe logger writes a command line activity CLA stream to file according to its personal identification device pid . When the WINDOWS WC client monitor process detects that a process has concluded the monitor process reads reports deletes a parent command line activity CLA stream file associated with the process if the parent is cmd.exe . This implementation is not ideal because it allows for alteration by a user. Hence an alternative method for implementing this e.g. inter process communication IPC may be employed.

The present invention also preferably hashes process start images. In particular the inventive scoring server aka PerformanScore tracks commands run and processes started on machines used in a practical training environment. However students in a training course may be asked to rename tools on remote systems to make them look less suspicious. By hashing process start images the scoring server is able to identify which programs are really being executed.

The inventive scoring server provides training for customers desirous of practical skills assessments and has particular applicability to cyber security and cyber operations training of customers and vendors.

A future embodiment of the present invention includes support for interception of commands implemented through a graphical user interface GUI . The current implementation does not support interception of commands implemented via a graphical user interface GUI but doing so is relatively straight forward requiring change to a hook location and the addition of an efficient filtering method both of which can be done using conventional known methods . While the invention has been described with reference to the exemplary embodiments thereof those skilled in the art will be able to make various modifications to the described embodiments of the invention without departing from the true spirit and scope of the invention.

