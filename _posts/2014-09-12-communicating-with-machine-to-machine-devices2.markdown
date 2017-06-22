---

title: Communicating with machine to machine devices
abstract: Method and system for communicating between a managed device and a device manager comprising sending the managed device a message over a first communications channel. Initiating communication between the managed device and the device manager over a second communications channel in response to the message, wherein the first communications channel and the second communications channel are of different types.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09635057&OS=09635057&RS=09635057
owner: VODAFONE IP LICENSING LTD
number: 09635057
owner_city: Newbury, Bershire
owner_country: GB
publication_date: 20140912
---
The present invention relates to a method and system for communicating with devices and in particular with machine to machine devices.

Managed devices and in particular machine to machine M2M devices may be used in many different situations and incorporated into a variety of different items and hardware. Typically these managed devices will have low computing resources be restricted in power and have restricted functionality. Nevertheless large networks of such managed devices may be developed that require maintenance control and other interaction that require communication with a device manager.

Due to the nature of the managed devices and their limited resources in both power and computing potential it is often necessary to keep the managed devices powered down in a reduced power state or in a dormant state until they are required e.g. to provide a reading or to accept a command . Devices may be scheduled to power up at certain times or intermittently. However if information is required from such managed devices or if control or other management information needs to be sent outside of such scheduled operation times then this approach has drawbacks. Alternatively some form of communication between the managed devices and their device manager may be maintained but this requires additional power and bandwidth especially for large networks of managed devices.

Therefore there is required a method and system for communicating with managed devices that overcomes these problems.

Against this background and in accordance with a first aspect there is provided a method for communicating between a managed device and a device manager the method comprising the steps of 

Preferably the first communications channel may be a cellular channel and the second communications channel is non cellular channel. Cellular communication channels may include those operating on cellular networks including GSM UMTS LTE 3G 3GPP WAP GPRS and CDMA for example. Therefore these cellular communications channels require a network operator or virtual network operator to manage a network of mobile base stations and cells. Non cellular communication channels use different technology but can include many different types. These may include fixed lines e.g. PSTN wireless channels e.g. WiFi and WiMax internet channels e.g. Ethernet and others for example.

Preferably the second communications channel is also secure and has a different security architecture to the first communications channel. For example the first channel may be insecure and the second channel may be secure and so has a different security architecture to the first channel .

The security architecture of either or both channels may include any of GBA cellular bearer security public private key or symmetric key security secured fixed line or other cryptographic security.

Optionally the first communications channel may be within a first communications system and the second communications channel is within a second communications system different to the first communications system.

Preferably the message may be an SMS or mobile terminated SMS SMS MT WAP push or OMA push. SMS messages may be particularly efficient. Other message types may be used.

Optionally the second communications channel may be any one of transmission control protocol TCP user datagram protocol UDP cellular wireless WiFi WiMax wired fixed line and telephone line. Other communications channels or interfaces may be used.

Preferably communications between the managed device and the device manager over the second communications channel may be suspended until the message is received. This further reduces power and other resource requirements.

Optionally receipt of the message at the managed device may additionally cause communications between the managed device and the device manager over a third communications channel to cease and switch to the second communications channel wherein the third communications channel is different to the second communications channel. Rather than waking the device up from a dormant state or in addition this allows a convenient and efficient method for switching between communication channels. For example the device may be switched between wireless connections or from or to fixed line to or from a wireless mode. This is one example of altering an existing communications channel but there may be others. The third communications channel may use higher or lower computing resources e.g. power bandwidth etc. when compared with the second or current communications channel. Therefore this method allows more efficient management of the device and network of devices. It is particularly advantageous to switch from wireless to wired or fixed line as this may provide greater bandwidth reliability power utilisation or other improvements.

Optionally the communications may be switched to the third communications channel from the second communications channel automatically. This may be an automatic procedure or may cause a user or other entity to make a manual switch.

Advantageously the message may be sent to the managed device in response to an increase in data volume a request to send the managed device a file over a predetermined threshold a request for a firmware or software update an increase in electrical power used by the managed device over a predetermined threshold and a decrease in data transfer rate below a predetermined threshold. The message may be sent or generated following other scenarios or criteria.

Optionally the message may be a secured SMS message. For example it may already be protected using generic bootstrapping architecture GBA information such as keys derived by GBA. In other words the SMS channel may be a secured SMS channel in which case any type of security information may be delivered e.g. further key or keys to secure the second communications channel.

Optionally the message may be an unsecured SMS messaged containing generic bootstrapping architecture GBA push information. In this case an unsecured SMS channel is being used and so GBA push information should be included with the message.

The GBA Push Info is described in 3GPP TS 33.223 Section 5.2.1. The encoding is defined in Section 5.3.5. See in particular table 5.2.1.1 and FIG. 5.3.5.1 in 3GPP TS 33.223 V12.0.0 2013 December that may be found http www.3gpp.org ftp Specs archive 33 series 33.223 33223 c00.zip

Advantageously the method may further comprise the step of confirming authenticity of the message using the push GBA information and wherein communication between the managed device and the device manager over the second communications channels is initiated following successful authentication. This prevents the unauthorised waking up of managed devices or the unauthorised switching to a different communications channel of these managed devices.

Advantageously the message is an SMS message and the method may further comprise the step of determining if the SMS message is sent over a secured SMS channel.

Advantageously the first communication channel may be used to establish cryptographic material e.g. a key or keys or a shared secret to secure the second communication channel. This may include the use of GBA GBA push or using the first channel to send a key which protects the second channel for example.

Preferably the communications between the managed device and the device manager may originate at the managed device. In other words the message or wake up message comes from the device manager and the communications are initiated by the managed device.

According to a second aspect there is provided a system for communicating with one or more managed device comprising 

Preferably the first communications interface may be a cellular interface and the second communications interface may be a non cellular interface.

Optionally the second communications interface may be secure and has a different security architecture to the first communications interface.

Preferably the first communications interface may be configured to communicate with a first communications system and the second communications interface is configured to communicate with a second communications system different to the first communications system.

Optionally the second communications interface may be any one of transmission control protocol TCP user datagram protocol UDP cellular wireless WiFi WiMax wired fixed line and telephone line.

Optionally the system may further comprise a third communications interface different to the second communications interface and wherein receipt of the message at the managed device causes communications between the managed device and the device manager using the third communications interface to cease and switch to the second communications interface.

The methods described above may be implemented as a computer program comprising program instructions to operate a computer. The computer program may be stored on a computer readable medium.

The computer system may include a processor such as a central processing unit CPU . The processor may execute logic in the form of a software program. The computer system may include a memory including volatile and non volatile storage medium. A computer readable medium may be included to store the logic or program instructions. The different parts of the system may be connected using a network e.g. wireless networks and wired networks . The computer system may include one or more interfaces. The computer system may contain a suitable operating system such as UNIX Windows or Linux for example.

It should be noted that any feature described above may be used with any particular aspect or embodiment of the invention.

It should be noted that the figures are illustrated for simplicity and are not necessarily drawn to scale. Like features are provided with the same reference numerals.

The system may be described as a Device Management platform as shown in which may provide a core set of services and mechanisms that can be integrated with customer or user application processes that may be described as Vertical Applications .

The applications may form part of a managed device or machine to machine M2M platform or may be separate from it. illustrates a number of vertical applications all interfacing via a device management DM Bus structure with a device manager that may also be described as a Device Management Application Proxy DMAP . The DMAP may be viewed as an enabling technology that can be used by many different Vertical applications. The Vertical application may be limited to a web platform that can trigger basic Device Management functions e.g. getter setters firmware management etc.

The DM platform may support multiple vertical application categories and types. The DMAP virtualises physical devices so as to provide a consistent view of those physical devices to the vertical customer or user application. The underlying mechanisms used to achieve this may be transparent to the Vertical Application and the mechanisms protocols and data structures used to interface with the physical devices may be part of the functioning of the DMAP .

As illustrated schematically in the functionality and data flow of the DM solution can be separated into three architectural components 

An alternative way of viewing the architectural model is as a component in an Enterprise Architecture environment where the Vertical Applications sit above the EA Bus and inter operate with Devices by invoking service orientated architecture SOA services using the Device Management Bus .

The DMAP Server is designed to be an enabling technology intended to satisfy the requirements of many different Device Management applications. As its name suggests it is an Application Proxy. There are many examples of illustrative applications including machine to machine M2M terminals monitoring devices Energy Connected Cabinets ubiquitous computer UBI Mobile Assets etc. The Vertical Application may be a web application that allows staff to perform basic Device Management functions. Additionally a cloud based SaaS approach may be used.

The DMAP may be accessible by third party customers and may manage third party devices assets so a deployment may have similar security requirements to other types of Application Proxy. In other words it may be assumed that the DMAP is an attractive and accessible target for security exploits. The Security approach that is taken is a defence in depth approach using a number of host level security mechanisms not normally used in network elements file integrity checking rootkit scanning security role enforcement host level firewalling .

Five separate bus structures are described in the following section. Connectivity matrices and firewall IoD specifications may map onto these but may be further extended. For example the DM Bus may be used to communicate with different vertical applications with different security requirements. Therefore the DM Bus may be separated into multiple physical logical communications pathways and with appropriate security controls on each.

The DM Bus may communicate with an operator hosted web application that may provide access to the DMAP for use by the operator trusted staff. This may be satisfied with a single VPN connection between the controlling web server The Vertical Application and the DMAP . The DMAP interfaces with the agents which may be components software and or hardware within managed or M2M devices.

Wired and cellular connectivity to Devices may be used. M2M platform managed devices may support a cellular bearer allowing SMS wakeup and APN connectivity. Some devices may also have additional wired connectivity. The M2M platform connectivity may be considered trusted and any other connectivity should be treated on a case by case basis and should be allocated to a separate security domain. Not shown in the diagram are operations and maintenance O M connectivity requirements. These may be implemented locally or use VPNs over the Device Control Bus for example. These may include DNS NTP SNMP SYSLOG SSH and Backup protocols but additional protocols may be supported as required.

Vertical applications are applications that interface with manage and manipulate Devices using the Device Management platform.

Vertical Applications may be used by different sorts of user with varying security roles for example 

The Vertical Application that a particular sort of user will use may similarly vary. Types of application might include but are not limited to 

Many other Vertical Applications may be developed to support the needs of Vertical markets. Example may include UBI Connected Cabinets RMCS.

Vertical Applications may communicate with the DMAP over the North Bound Interface NBi . This is also referred to as the Device Management or DM Bus .

The NBi may provide a Bus interface for communicating with and controlling physical M2M assets managed by the DM platform.

The NBi may allow bi directional communications between the Vertical Applications and the DMAP s NBi. Communications may use web services and connections may be established by Vertical Applications to the DMAP s NBi or from the DMAP to Vertical Applications for example.

Management applications may include logging alerts diagnostics and analytics. Customer applications may include any of the vertical applications described previously or additional applications. An enterprise architecture bus provides an interface between the applications and the DMAP . This may be over an internal or external network for example. Device security and device control buses provide interfaces between the DMAP and a single sign on SSO and a global data service platform GDSP components respectively. A device data bus may provide an interface between the DMAP and managed devices e.g. individual devices other DM platforms or one or more gateway hubs over one or more bearer networks . These bearer networks may include cellular wireless or wired networks.

The DMAP may require an administration interface for operations people. For example this may be used to administer access rights for northbound parties that are later enforced by AAA. An O M interface may be included but this may be treated as a special case and will go into an O M Security zone. An admin Vertical application may perform admin type dashboard functions. Connection management timeout queuing issues may be addressed by a standardised admin kpi capture interface. Assets may be described in terms of data structures where access controls are defined using a role based notation. An authenticated connection may be authorised to have different levels of access to assets using a role based security model. For example this may use a JSON XML model where both requests and responses are described using well formed data structures i.e. XML .

In order to comply with security requirements this application DM Bus protocol may use SSL encryption based on certificate based authentication mechanisms. Additionally VPNs may be used appropriately to ensure correct separation of data traffic over the DM Bus . DM Bus traffic to internal management applications may run over separate VPNs to traffic that passes to third party Vertical Applications on the public internet.

Synchronous requests may arise when a query or an action is requested and the results can be returned immediately. Asynchronous requests may arise when queries are requested and the results will be available at a later point in time. Synchronisation may be maintained by a separate or integrated component or function.

Synchronous requests may be used when the result or status of a resulting action is immediately known. If the status is changing then multiple queries may be used to poll the status. Whilst polling is simple it may not be very efficient.

This provides a mechanism for dealing with changing conditions or events in a more efficient fashion. When the action resulting from an asynchronous request generates a result this result may be supplied back to a specified URL and the result data may be encapsulated using an XML notation. This type of request may be used when 

Actions to be applied to particular devices or groups of devices may be stored within a storage location within memory volatile or non volatile and then synchronised or applied to the device immediately or after a period of time either scheduled or as necessary in the immediate conditions . The actions may be to change add update or delete a particular value or attribute of a device or to obtain data from the device. Therefore the synchronisation may be two way.

The callback mechanism may also be used for sensor data notifications sent from a device. Alerts sensor data diagnostics and asynchronous getters may all use the same callback mechanism.

The URL callback mechanism may be implemented as a setter mechanism where the action requested will be communicated back to the invoking Application by means of a specified URL. The advantage of this approach is that it makes very efficient use of resources and can be used to describe sophisticated behaviours in a simple fashion.

Asynchronous Requests may be used where a single action is being requested and there may be an unknown time delay between the request and the action. For example a command to Lock and Wipe a device may only be performed after the DM platform has established contact with the identified device. If the device is turned off it may take some time before the operation is completed or timed out .

Asynchronous Requests may be used where there will be more than one result. This could be no result or potentially an infinite number of results. An example may be a query for devices with a low signal level. There may be a varying number of devices that satisfy this request returning results over an extended period of time. The callback mechanism provides a mechanism to transfer this sequence of responses in a relatively simple fashion.

Sensor data results may be supplied to a controlling application by means of the callback mechanism. The requesting application may describe the sensor data of interest the conditions that will cause it to be supplied and the URL callback to pass this sensor data to. Note Multiple applications may potentially view the same sensor data simply by describing multiple callback requests.

Alerts may arise when some event occurs that need to be recorded and the information describing the event needs to be communicated. An alert may be how you describe a trigger that will cause the alert to be generated. The triggering condition could be simple e.g. a data field has a specific value or the value enters a specified range.

Alerts and Sensor data shipment may be implemented in the same way. The scheduled shipment of sensor data may also be regarded as Alerts.

More sophisticated alert triggers may be specified with multiple conditions being combined using Boolean logic.

Conceptually these function in a similar same way to Callback Alerts. The only difference will be how a diagnostic alert is defined. Diagnostics may be of interest to support organisations with Helpdesk 1 2 3line support responsibilities. Diagnostics mechanisms may be managed by Applications under the control of this type of Organisation.

An application may request asynchronous activities Callbacks by invoking requests with the URL describing where callback data responses are to be sent. Callbacks for sensor data alerts and diagnostics may use this same mechanism and may perform their functions by specifying a callback with a trigger condition. The trigger condition and consequent action form a pair. This API may contain 

The callback parameters may be specified in a single API call or alternatively one can use previously defined and named definitions of 

In the case of Alerts diagnostics and sensor data and the named callback plus trigger specification may be associated with a device in one of three example ways 

When a Device s instance data a programming term describing the data objects assigned to an object the object may be a virtualised device object changes it will first process all callbacks associated with that Device then it will process callbacks specified at Device Version level and finally it will process callbacks at Device Type level. All callbacks may be named. Once a named callback has been actioned callbacks with the same name at higher levels Device Version Device Type may not be triggered.

This approach of using named data structures and triggers offers the ability to modify returned data structures and triggers dynamically without the need to modify application programs or even the need to restart those applications.

The last step in this Use Case may cause the Alert Diagnostic to be associated with the Device Instance structure representing the Device Types. If an Alert Diagnostic already exists then it may be overwritten with this new definition.

This approach allows the Alert Diagnostic to be specified for a single device a collection of devices at the same version level or all devices of a specified Device Class.

A named trigger defined to detect a device with a specific hardware error might be refined over time to trigger under different circumstances. Over time support personnel or an automated system may refine the trigger so it is more selective and accurate in identifying a specific fault condition or criterion. Once modified the trigger may be activated and all applications using that named trigger may start to receive callbacks for devices that match the new and refined triggering conditions.

This trigger action mechanism will allow the support team to create an increasingly sophisticated diagnostic alerting capability by refining the triggers over time. As new faults are diagnosed or other criteria met then triggers may be re defined to be more specific and selective.

Similarly when defining the Alert Diagnostic it is possible to define it for individual devices or devices at specified versions or for all devices of a specified type.

The Get Set API or Northbound Interface may use an API offered to users or customers by a cloud server e.g. Sierra Wireless s cloud service . SNMP may use the same approach but where callbacks are implemented using trap servers. Using web services to communicate between applications in both directions can be used for managing bi directional flow of information between web service aware applications.

The software may be hosted in a Cloud. Cloud master slave proxy and forwarder configurations can be used.

The Device Management Application Proxy may use declarative mechanism to describe all operations objects and actions. Each DMAP Server may manage 

The DMAP server s Processing Engine may be limited to a small set of simple processes. An example implementation is schematically shown in . These can be implemented as multiple threads of activity or single threaded processes executed in sequence. The processes can access the Device Instances and synchronisation mechanisms may operate at device instance level i.e. the processes may not have any visibility of them .

Each physical device managed by the DM Server may be instanced. These Device Instance data may contain all the latest information pertaining to a physical device and may be thought of as a virtualisation of a physical device . The contents of the Device s instance data may be referenced using the North Bound Interface using any of the getter setter mechanisms.

Setters are not limited to setting data values but they may also support the ability to invoke commands. For example a Data Variable instance representing wipe lock may be used to support the Wipe Lock mechanism by performing a setter operation of lock or lock and wipe on the Device Instance variable representing wipe lock.

The Device Instance data may have a reference to a Device Class Object i.e. there may be a single Device Class Data object for each Device type . These data may also include references to a Device Version instance see Device Version Instancing section Object.

The Device Version object may contain a data structure that describes the Data Model used by Devices at the specified Version Level.

Thus a Device Instance may have a reference to a Device Version Object that may contain the Data Model used by all Devices of that Device type and Version. These data structures and relationships may support mechanisms necessary to transition Devices between Versions of Firmware for example.

A device data model may be defined given a priori knowledge of the device data models used in TR 069 and OMA LWM2M as well as other example protocols . The later development of adapters may therefore become more straightforward. This maps directly onto the LWM2M TR 069 and SNMP MIB data models. Additional features and structures may be included.

Each level may have different requirements but preferably a single XML definition of the device data model may be used and from that the necessary structures for the different levels may be generated see SDK Data modelling tool .

Device Instance Data may be defined using a Data Model where each Version of each Device may have a Data Model associated with it. This Data Model may take the form of an XML defined tree structure for example where each node on the tree describes either a data element of a specific type with defined attributes and meta information associated with it. Alternatively it may be a branch node on the tree of data elements.

The Ring Signals node is shown as a Branch Node and in this example may contain references to multiple different Ring Signal data objects.

Data Model meta information may contain a number of attributes which may constrain how the Device Instance data will be used this may include but may be extended 

Architecturally the Data model may have a hierarchical structure. This can be represented using a relational data base system meaning that the developer can use a database if required. However it may be preferable for the developer to design a data model intelligently.

The Data Model allows the developer to represent collections of related data structures as though they were single data objects. shows a further example data model . In this example the object DM Lists is a list area and references multiple list structures e.g. list names that each has list features . Each of these lists represents different categories of data objects.

The advantage of grouping collections of different data items in this way is that data structures with similar uses can be manipulated collectively as though they were single objects. As shown in this figure three example list structures are shown to have different security roles.

The device data model allows the developer to describe all the data items associated with a device in terms of the names types of data default values and valid ranges of values i.e. for normalisation validation and optimisation of analytics processing .

The precedence of the multiple models may follow Class Group Instance where instance overrides group which overrides class.

As well as the data type information the data model may support other types of meta information about device data items and device capabilities. This may include 

The following application example maps Feature Lists onto OMA DM data structures. In this application example the M2M product designer has developed an M2M device for monitoring the 12 Volt power supply to a low voltage consumer appliance. To facilitate use of the appliance he has created three feature lists 

The designer of the device will specify the feature lists supported by the device. This specification will describe how the data is mapped from the device into the feature list data structures and this mapping will be described in an appropriate fashion ie using an XML declaration notation . For example a temperature sensor reading may be mapped into the List Sensors feature list described above. In the example there are two different temperature sensors one is a board sensor intended to measure the temperature of the M2M device and a second sensor designed to measure the ambient room temperature.

Mapping of the data items into the feature list may also involve some data processing in the case of the temperature sensor the mapping might involve taking the average of a series of readings or a maximum value reading. Irrespectively the mechanism allows the device developer to specify which features are available to different applications in a way that is role specific.

Different applications may make use of different feature lists. The example above describes a device with three different feature lists intended to be used by three different sorts of application each with different security access rights. A third party company providing a service managing the firmware software update mechanism may need access to the Version Lists for each device. This allows the company providing Over the Air OTA updates a mechanism to confirm the version details of devices that need updates. The third party company does not need to know what the various fields mean in the Version List. All it needs to know is that the contents of the Version List need to match the Version info for a particular version of software prior to commencing the Update process.

The same approach can be used for diagnosing device defects the company managing the device diagnostics process needs no knowledge of the contents of the feature lists all it needs is a way to map different feature list values onto actions to take.

By abstracting out the identity of data values and what they represent it is then possible to make use of advanced analytics on the feature list data using supervised and unsupervised machine learning techniques. The organisation performing the analytics on captured device data does not need to know what the various features represent instead all they need to know is the type of data and ranges of values. From this information alone it is possible to identify which features in a feature list are important in predicting future results and trends.

Using the example Feature Lists above there is a feature list called List Sensors. Ordinarily this would be processed simply be GET ting the current feature list values. A more advanced application of feature lists supports the use of time series data whereby a feature list item was created periodically i.e. once every 10 minutes .

A multiple row instance feature list data structure may support the use of a set of feature list values. This would provide the application with a mechanism to collect data that had been acquired over a period of time.

A set of sensor values may be captured every 10 minutes or another interval and an application would GET this data for processing and analysis twice a day. Using a multi row feature list the device developer may append the most recent set of sensor values into the multi row feature lists. Applications querying these data may have the ability to select individual values or ranges of values.

Feature Lists provide a mechanism for describing how data maps onto role specific data structures. Many of the mechanisms to describe and access these data structures are borrowed from set theory and relational database technology. By providing a declarative mechanism to describe how collections of data will be organised and arranged within a device e.g. M2M environment it simplifies the tasks involved in making use of that data. As well as simplifying the application developer s job it also simplifies the security process because in both cases the Feature List data structures may be used and secured using a role based approach.

A consequence of this abstraction process is that there is no longer a requirement for data processing activities to have knowledge of how data is organised because the data will always be served up in the same way to the application developer. The developer no longer needs to understand how the data is generated on the appliance or even what the data represents. An output from a temperature sensor is just a number for processing and the processor of that data does not need to know it is a temperature reading that might indicate a fire is about to start. Instead the processor of the temperature reading will just see a number that is exceeding a maximum value that in turn may trigger an alert process appropriate for automatically initiating a call to the emergency services.

Different applications may make use of the different lists in different ways. The example of shows a device with three different lists intended to be used by three different sorts of application each with different security access rights. A third party entity or company providing a service managing the firmware software update mechanism may need access to the Version Lists for each device. This would allow the company or entity providing Over the Air OTA updates a mechanism to confirm the version details of devices that need updates applying. The third party company does not need to know what the various fields mean in the Version List. All it needs to know is that the contents of the Version List needs to match the Version info for a particular version of software prior to commencing the Update process.

The same approach can be used for diagnosing device defects the company or entity managing the device diagnostics process needs no knowledge of the contents of the feature lists all it needs is a way to map different list values onto actions to take by means of the trigger action callback mechanisms designed to support device diagnostics.

By abstracting out the identity of data values and what they represent it is then possible to make use of advanced analytics on the list data using supervised and unsupervised machine learning techniques or other analytics for example. The organisation performing the analytics on captured device data does not need to know what the various data items represent. Instead all they need to know is the type of data and ranges of values available via the Device Instance Data Model reflection mechanisms . From this information it is possible to identify which features in a list are important in predicting future results and trends.

Device Data models can contain many complex data structures relationships and attributes which will require skill to maintain accurately and correctly. A Data Model editing tool may be used by developers to design develop and maintain Devices. This Data Model tool may create XML or other data structures that describe the functionalities of a device data items security etc. that can be instanced as part of the Device Data Model Instance Objects.

Additionally this data model can be used as a mechanism for describing the processing and operation of the physical device and the code that runs on it. This may require the Data Model tool to create code data structures that can be used by coders working on the device.

Device Class Objects may contain generic information about a device type and its purpose is to act as a collection point for all activities that relate to all devices of that type.

Device Version instance Objects may link to a device type and be used to contain information common to all Devices that are at that version level. This object may encapsulate firmware update apply logic for devices that are being transitioned between firmware version levels or sequences of version levels. Firmware management goes through three phases in this example 

An advantage of using this declarative approach to describing firmware images and the data models differences between firmware images include the ability to

For a particular device type there may be a single Device Class representing all the devices of that particular type. Alternatively Devices of a similar type but with different versioning requirements may be represented by multiple device class objects. In an example a device may have significantly different versioning requirements such as a device designed for Chinese language markets and European markets. The devices could be treated as completely different device types.

The Device Class object has member data items that are descriptive of the device class object. One of these members may be a single link to a Device Version object.

The Device Version object would encapsulate a description of a specific device at that version level. This object may contain 

The Device Data structures may contain information about devices required to transition firmware between different versions. A Device Data Structure Versioning tool for managing the definition of the different data structures and the relationships between them to facilitate automated transitioning between versions of software.

All data structures may support getter setters accessible on the platform and also available via the North Bound Interface . All Device instanced data items described in the Device Version Data Model may also support getter setters.

The only limitation on getter setters may be those described by the role based security model. The security role model for a device may be defined and encapsulated into the Device Version Data Model. All other Data Structures in the Device Class Device Version and Device Instance Objects may support an appropriate security model.

Reflection is the ability to query the data type and associated meta information. Reflection may be supported for access to the Device Data Model.

All Data Structures may be serialisable. This is a mechanism used to support replication back up and master slave configuration.

This allows multiple DMAP servers to interoperate. All data structures may be serialised and once serialised may be transferred between DMAP servers. This mechanism can be used to architect DMAP servers into 

Backup standby hot warm cold can all use the same serialisation mechanism to communicate instance data so that it can be saved and restored when needed.

Alerts diagnostics and logs may all use the same underlying mechanism which is to define the conditions which will result in the Alert Diagnostic Log event happening. This is referred to as the Trigger Action. Data may be generated as a result of the Trigger Action event happening. The Trigger Action may also define where that data is sent.

Trigger Actions may be associated with Device Class or Device Version Instances meaning that an alert could be specific to multiple physical devices all of the same type. It will also be possible to define a Trigger Action on a device by device basis.

Triggers may be instanced and named data structures where each named trigger has a number of conditions associated with it. These conditions can be simple lvalue operator rvalue triplets where 

An example condition trigger may be Voltage sensor GreaterThan 12. Similarly conditions can be chained together using Boolean logic referring to other named triggers i.e. Trigger AND Trigger

A trigger action data structure may be used to describe the action or actions to perform in the event of a trigger condition being applied and the result of processing the conditions is true. The trigger action data structure may be named and may comprise any one or more of 

The Trigger Action processing may be initiated in a number of ways. The mechanism described in this example is data driven.

Other initiating mechanisms may be used to process triggers such as a background process that may iterate through the entire list of Device Instances testing each Device s trigger conditions in turn and repetitively.

The Logical connectivity Model of the DM platform see Logical View SBi supports three categories of communication.

Types of example data communication include SMS and Internet Protocol Connection or connectionless connections. The physical connection pathways will be either over cellular bearers or cellular and wired wireless internet connection mechanisms.

Devices using M2M platform SIMs may be restricted so that they are only able to send SMS Mobile Originated messages to the DM Server in this is shown as the M2M application . This may be used as an alternative communications path from device to DM Server for situations requiring it.

The above rule may mean that SMS MO are initiated by the M2M platform device destined for the M2M application the DM Server on the customer server.

Devices may support Device to DM Server IP connectivity using connection and connectionless protocols. When the communication takes place over the cellular network the Device may establish an APN Device context and the communication may take place over this device context to the identified device instance object represented on the DM Server.

For wired and wireless IP connections the same client server relationship between Device and Device Server may be used 

The Device Data Abstraction mechanisms allows the DM Server to virtualise images of physical Devices this Data Abstraction mechanism refers to the DM Server s views of devices as Instance Data where the contents of this instance data is described declaratively using a Device Data Model description language e.g. XML based . This then allows applications to interact with the physical devices indirectly via the Instance Data.

This declarative and indirect approach to Device Management has a number of benefits. Not least being that it allows the Device Developer Vendor to describe devices and their functionality by means of a Device Data Model.

This Device Data model approach may be supported and used by a number of different application protocols including OMA LWM2M TR 069 and SNMP for example.

This abstraction mechanism may be extended to support additional attributes not necessarily supported by all underlying communication protocols. For example OMA DM supports a role based security model but SNMP and TR 069 do not. By using a Data Model that supports security role attributes it provides compatibility with the application protocols that support it but it also can be used for devices using application protocols that don t support it.

Devices using the SNMP protocol can still use a Data Model that supports security role specification it just means that the device may not support that role based mechanism. It still has value as the Device Developer can now describe the Data Model for the device in terms of the MIB specification and can overlay additional meta information as appropriate.

As described earlier the Device may be functioning as a hub or gateway device to a number of other peripherals where these peripherals are connected via a multiplicity of different communication mechanisms. In this case the Data Model may accommodate this extended view of the Gateway Hub as though these peripheral components were part of the same Data Model. All communications between the Hub Gateway and the Peripherals may then be abstracted out and transparent to the DM Server and any applications accessing it. Where control status mechanisms are required or desirable these can similarly be incorporated into the Device Data Model.

The designer specifier of the Data Model should accurately describe the Device s Hub s Data Model so that it reflects the functionality.

The Device South Bound Interface Layer provides the link between the DM Platform and the Devices . The Device Interface layer performs several functions in this example 

This Device Data Model would best be described using an XML notation. Instances of Device Objects could use XML notation at run time or alternatively at compile time. The Data Model may define a set of variables mapping onto the OMA DM LWM2M data model. The Data Model may include access control list ACL structures for example.

It may be possible to use property models to enforce an ACL on data structures. However a simpler approach is to create a higher level object that contains a device surrogate object and representation of the requester raising the query. This requester object may also include the security role of the requester.

The architectural model may provide interfaces to more than one vendor s devices. Different vendors products may have different capabilities and in some cases very different functionality. Preferably all devices may support a standards based communications protocol.

Each vendor appliance type may require its own specific Device Adaptor Class and each physical virtual device connection may require an instance object of both the surrogate and the adaptor class to represent that connection.

Several types of adapter class may be required. illustrates and example Device Interface Adapter Agent Model that may be 

Abstracting DM Platform to Device connectivity using a Surrogate Adaptor model means that higher level applications may all access devices using the same APIs.

The DM Server may be used to represent many different physical devices as virtualised Device Instances. This Device Instance data is volatile and may have been created over an extended period of time. Device Instances that have not been updated because the physical devices they represent are not available e.g. because they have been turned off may be very old.

If the DM Server is restarted there is the potential for all this cached Device Instance data to be lost. The remedy in this situation will be to re acquire the virtualised Device data from the physical devices AGAIN. The data may be stored permanently in the M2M platform e.g. in some database. As the device instance data is all serialisable it can be stored anywhere including on other DMAP servers.

There are several example approaches that may be used for recovering and distributing Device Instance data in order to improve system availability 

Maintaining managing and supporting multiple versions of Software for Devices may be achieved by the present system. Furthermore the DMAP has been designed to simplify and reduce the cost of this activity.

Mechanisms that may be used to support Firmware management are described. Other types of Software may use similar mechanisms. Such updates may include but are not limited to 

Firmware updates are one category of software assets that require version management. This has additional complexity particularly when many different devices of many different versions are involved. Further management complexity may arise for application software that has been installed by users.

The mechanisms described below are designed for managing firmware however these example mechanisms and principals may be extended to support other types of software asset as required.

Firmware updates may be managed during specific windows of time. Specifically firmware windows may be defined and associated to Device real estate. For example this may be on a country by country basis or all devices may be updated relative to a specific time zone.

Software rollbacks to previous releases may be implemented when managing O S updates. This requirement is met for all software management activities.

To support this requirement additional reference structures in the Device Version object see in may be included in order to support backward linking. Device Objects may also include a reference to a rollback target version.

The Device Vendor application or user may create a new and improved version of firmware for a device. The vendor will test this firmware until he is confident it is sufficiently robust to deploy in the live environment. The stages to deploying a version of firmware may then include note the following description is illustrative only a sequence of steps to represent an update and all associated activities using a declarative approach. The Update may be defined together with all dependencies and actions in an update data object. The update data object may then be linked into a network data structure that describes the relationship between this update and previous updates. Once the update is fully defined as well as its relationship with other updates then the DM platform may process these data structures to automatically transition physical devices through sequences of update operations.

The Firmware Scheduler process may iterate through all device instances invoking firmware transitions as required. The Device Objects may contain data objects referencing the current Version and the target version objects for the Device Class and the firmware images for these. Once a Device Instance has been identified as a candidate for a Device Version transition a series of activities may take place.

The prioritisation and scheduling of this process can be refined as appropriate. Extending the functionality to manage firmware management campaigns in more sophisticated ways may be implemented.

Additional example features may include encrypted searches where the search terms and or the results are encrypted. This may be extended to encrypted diagnostics logs alerts machine learning. Encrypted data may be examined on a neutral third party platform and an action decision may be made based on the encrypted input data. An example may be where an analytics company performed analysis on encrypted input data and inferring results without any knowledge of the plain text of the inputs or outputs.

Homomorphic encryption may also be used as this allows arbitrary computations to be performed on encrypted data e.g. by untrusted parties without breaking the encryption.

A mechanism may be provided that allows the operator to define tests that will exercise the equipment and verify correct operation. For example a memory checksum test may collect Memory Signatures generated using predefined polynomial CRC checks across portions of memory. The memory checksum function is beneficial as it can be used to confirm the version of software and it can be used to confirm correct behaviour of memory read operations on the equipment.

The system provides a way of mapping a collection of data values onto a single list structure such that all of the information specific to a particular task is collected together and can be accessed in a single query.

In the context of the two requirements described above a list data structure with all the version specific data may be created that contains all features and values that can uniquely identify an appliance and which could include a memory checksum to verify that a specific version of software was installed . A second list data structure may be created that contains all the features and values relevant to identifying correct operation and diagnosing possible causes of incorrect operation.

Devices such as M2M capable appliances provide standardised diagnostic monitoring and management functions so that they can be managed in a commercially effective manner.

To define a standard mechanism for collecting data values from devices e.g. M2M appliances such that a single query can be used to gain access to multiple values. These collections of values may be referred to as feature lists as described above.

To define a standard mechanism for specifying data values and data signature values that will be mapped into feature lists

To define a standard mechanism for querying meta information describing the elements of feature lists e.g. type access rights ranges of values etc.

To define a standard mechanism for describing access rights at a feature list level and authentication requirements required to gain access to them in such a way as to protect the integrity and confidentiality of the information represented by the contents of the feature lists.

To define a standard mechanism for describing linkages between features in different feature lists such that the information contained in different feature lists can be combined for analysis purposes.

To define a standard mechanism for specifying signature data values for devices and M2M appliances such that information about the health of an appliance and the assets it represents can be confirmed 

According to one aspect there is provided a mechanism that allows a developer of M2M devices to map data values in such a way as to be appropriate for the way that that data will be used. The mechanism may allow a device or M2M platform operator to provide an automated system for predicting faults in appliances that are being monitored by the device or M2M platform operator without requiring that operator to have any knowledge or understanding of appliances being monitored.

This may allow the provision of a fault diagnostic and prediction service to third parties deploying M2M equipped devices in end customer premises. As an extension to this system it could be integrated with Business Logic to allow additional alerting and prediction capabilities in an application specific way.

One purpose of the device or system is to provide a generic mechanism for mapping unorganised and hierarchically organised data structures into relationally organised list structures that are appropriate for application use.

An application of this device would be to predict future behaviour of an appliance and events that it is monitoring based on past activities. The purpose might be to monitor appliances for correct operation in an automated fashion or it might be used to predict an imminent application specific event such as an increase in power requirements for a household for example.

The mechanism will allow an operator to capture and record behaviour of an appliance over a period of time such that future results from an appliance can be predicted in a fashion that places no reliance on the operator having any knowledge of the appliance or its operation. The results being predicted might concern the correct operation of the appliance being monitored or it could be some other prediction that has some value e.g. predicting identifying a medical emergency .

A device that maps data values into linear list structures such that the contents of the list structures can be collected and analysed without the operator of the collection process or the analysis process requiring any knowledge of what the data represents.

NOTE These data values are subsequently referred to as features in the following examples. Collections of features are referred to as feature lists.

Feature Lists and Features will have associated meta data sufficient to describe the features in a way that will facilitate processing of feature data by third parties without the third parties requiring application level knowledge. Illustrative meta data would include type of feature data ranges of possible values descriptive information etc.

A mechanism for describing feature data in such a way as to minimise the memory storage requirement for describing that feature data. In the case of Checksums it is only necessary to record whether a checksum is correct or incorrect and this feature data item can be described as a single bit. The advantage this confers is to reduce the amount of storage required to record and communicate captured feature data.

A mechanism for describing sets of feature data items into feature lists comprising single compressed sequences of values. The advantage this confers is to minimise the number of communication transactions required in order for an M2M feature data collection mechanism to collect a set of related features from an appliance instead of making multiple requests to query multiple sensors CRC checksums etc. The feature list collection process will make a single Get Feature Data communication request and all feature data for the requested feature list type will be collected in a single transaction.

A mechanism for describing multiple feature lists such that a collection mechanism could request a specific feature list to collect which would be a sub set of the full set of features and only contain feature data items relevant for the purpose it is being collected.

This would allow different feature list collection agencies to collect feature lists appropriate to their requirements. For example a medical appliance might contain patient sensitive information such as location and personal identity which would be valuable for medical diagnostic and epidemiological purposes but of no interest to the equipment vendor. In such an instance one feature list would be collected for use and analysis by the hardware vendor to confirm correct operation of the appliance and a second feature list would be collected by the medical practitioners for the purpose of medically focused analysis.

A mechanism for assigning different access rights on different Feature lists such that different actors have different access rights to different lists with appropriate levels of confidentiality and integrity applied.

A mechanism for querying modifying and deleting features. Using feature lists to describe the feature values of interest such that different actors have different access rights to different lists with appropriate levels of confidentiality and integrity applied.

A mechanism for identifying faulty circuits and associating the failures and types of failure with feature information that had been previously collected as per Clause 3. This is referred to as Result Data in subsequent clauses.

A mechanism for identifying result data other than circuit fault as outlined in Clause 9 such as an indicator that a medical emergency is imminent and that a patient being monitored requires urgent attention

As per clause 10 but for other outcomes such as an indicator that a House hold is not making efficient use of Electrical Power Supply and that an energy audit would be recommended

A process that allows for an electronic appliance to be described using multiple signatures. These signatures may be generated in a variety of ways. Signatures will be generated in a mathematically appropriate fashion designed to best describe an object in a unique way. One mechanism would generate signatures using Cyclic Redundancy Codes CRC in combination with a predefined polynomial.

The device would use a multiplicity of feature types to describe multiple features of an electronic circuit. These feature types may include 

An analysis phase that would correlate feature lists with result data with the purpose of identifying feature value changes that would predict specific result outcomes such as that an item of equipment will fail in 4 hours or that an diabetic patient is at risk of hypoglycaemic coma.

This analysis phase would use mathematical processes linear regression analysis and logistical regression analysis in conjunction with machine learning techniques neural networks to identify which features were important in predicting and identifying results such as the possible imminent failure of an M2M capable appliance or a medical emergency.

NOTE It is important to understand that the system places no reliance on knowing what the features are during the analysis phase and this analysis activity can be completely or partially automated.

A mechanism for describing actions to take in the event of an appliance exhibiting symptoms of failure as predicted during the analysis phase as per Clause 14 . Such as emailing a support person or raising a trouble ticket.

In the event of an automated remedial action ie upgrade software version or disable enable specific feature of equipment the system would initiate that remedial action.

A mechanism for describing linkages between multiple feature lists such that the features in one feature list can be correlated with features in another feature list.

A mechanism for describing location information for a feature list such that the encoding of the location information permits correlation between feature lists but does not disclose real physical location.

A mechanism for describing location information that describes a location in three or four dimensions relative to predefined secret reference points. This would facilitate the analysis of data by location in a fashion that anonymised the actual geographical location analysed.

A mechanism that allows an external device to communicate with a device implementing this invention such as to enable it to change the feature item values in a feature. Such a feature list may be called a Writable Feature List.

A mechanism that causes feature values in a feature list to selectively initiate actions to be performed. Such a feature list may be called an Action Feature List. An example of an Action Feature List might contain three feature value items consisting of 

In other words the first interface allows communication between a user and a managed device e.g. a physical M2M asset via the DM platform.

The DM server also includes mechanisms and structures to allow the various functionalities to work properly. The DM server can be implemented as a hardware platform a software platform and or a cloud service e.g. cloud hosted software as a service etc. .

An abstracted hierarchical model structure is defined and or generated so that it can be used to address any device and or functionalities to be managed through a Device Management platform. The hierarchical model structure can then be used to derive a specific model to be used at a particular level e.g. Vertical Applications level DMAP level protocol level device level . In other words the same structure could be used for representing information associated with the management of a device e.g. M2M device and then be converted so that it can be appropriately used for the right level each level having specific requirements.

The general concept is that by using a surrogate of the receiving entity of a DM communication e.g. an M2M device another DM platform a Hub controlling one or more devices the communication on the two interfaces can be split and simplified in a significant manner.

In particular a surrogate is a replica of the receiving entity within the framework of the DM platform i.e. it conforms to a unified data structure e.g. the abstracted model structure and or to a unified protocol defined for a first interface e.g. the NBi . The surrogate is associated with an instance of the receiving entity.

In this way the communication between the user and the DM platform over the first interface e.g. NBi can be performed using a similar message conforming only to the unified data structure independently of what data structure the actual receiving entity uses. The user effectively communicates with the surrogate rather than with the actual receiving entity.

Similarly the surrogate in the DM platform will communicate to its corresponding receiving entity over the second interface by adapting the unified data structure into the specific data structure used by the corresponding receiving entity. This is done by way of an adapter.

A mechanism for allowing the DM platform to monitor the device on behalf of the user e.g. Vertical Application based on an indication provided by the user and then provide information back to the user when the DM platform identifies that certain criteria provided in the indication are satisfied.

The mechanism may include the DM platform receiving an indication from the user or application specifying at least one criterion to be monitored for one or more devices. The indication may include a specified manner to contact the user once the at least one criterion has been satisfied. The indication may be provided by way of an asynchronous connection e.g. a connection that is essentially set to provide the indication but not to receive the response triggered by the at least one criterion . The DM platform monitors the one or more devices based on the at least one criterion. The DM platform contacts the user or application in response to the at least one criterion being satisfied. The indication may be a trigger.

The ability to upgrade the software on a device so it is up to date is a highly valuable and important feature of Device Management but it is difficult to manage if you have many thousands of devices all at different versions.

The DM platform uses a declarative approach to managing software firmware management for collections of devices that supports different device types different sequences of actions to perform during updates and most importantly a state machine describing the sequence in which update operations should take place i.e. where you need to transition the device through multiple updates in order to bring devices up to the latest release level .

This is a mechanism to deliver secure parameters directly via the wake up message i.e. the message used to wake up a dormant device . The message can be an SMS message for example. This message is sent by the DM platform in order to trigger a connection e.g. UDP connection between the device and the DM platform.

In particular when using an SMS message if no existing SMS key is present i.e. the SMS channel has not been secured then the message may contain a generic bootstrap architecture GBA Push type of info because there is no need to secure SMS . On the other hand if an existing key for SMS is present i.e. the SMS channel has been secured then the message can contain any type of security information for instance further keys that will be used to secure the subsequent connection.

The mechanism may include also a mechanism to determine whether the SMS channel has been secured. One of the advantages of this mechanism is that the signalling between the DM platform and the device may be reduced. It is important to understand that on the present platforms wakeup from DM platform to device may only be used to wake up the device. All data communications is always initiated from the device.

The device manager contains logic that is used to control the system e.g. carry out actions on managed devices and interface with a plurality of communications interfaces and . In this example implementation communications interface is an SMS interface that is arranged to send SMS messages to the managed devices through a cellular network . Communications interfaces and are separate interfaces and of different types e.g. any of transmission control protocol TCP user datagram protocol UDP cellular wireless WiFi WiMax wired fixed line or telephone line and may communicate wirelessly or using a wired or fixed line link to receive data from and send data to the managed devices . This example shows two communications interfaces for sending data to and receiving data from the managed devices . However any number e.g. one two three four etc. may be used on their own or together in any combination.

Communications interface is an optional or alternative communications interface in this example and may be used in place of or to replace communications interface . The SMS interface or another type may be used to send a message from the device manager to any one or more of the managed devices e.g. M2M devices or other device managers to initiate start up wake up or otherwise resume communications. This initialisation of communications may be using either or both communications interfaces or . When communications interface is not present or not in use the message causes the managed devices to initiate or resume communications over communications interface only.

This mechanism may use the wake up message or an alternative message to prompt switching of the connection from the wireless connection over which the message is delivered to either an alternative type of wireless connection e.g. a connection with a bigger bandwidth or to a wired connection. The switching may also be from one wired connection to a different wired connection or to a wireless connection for example. The switching may be determined for example based on detection of a large file to be delivered e.g. which would take too much bandwidth and or time . The message may prompt the device to automatically switch or prompt a user associated with that device to switch connection.

This mechanism could for example save energy in M2M devices and time to download file connection time .

In the example system shown in rather than or as well as causing an initiation of communications from the managed devices the SMS message sent using the SMS interface to the managed devices may cause or trigger a switch from using one communications system or interface either the interface or system used to send the SMS message or a different one to another communications system or interface .

At step a message is sent over a first communications channel using communications interface e.g. SMS . The one or more managed devices receive this message at step . This causes step which is an initiation of communications between the managed devices and the device manager over the second communications channel using interface . Receipt of the message over communications interface may optionally cause a termination of communications over a third channel using interface at step . This may also be described as a switch of the communications channel from using interface to interface i.e. from one channel to another .

The DM Platform uses a Declarative approach and using data structures and their relationships to describe how things work.

A declarative approach is a programming term used to describe a data driven way of representing solutions to problems. The simplest example is traffic lights. To describe declaratively you would describe the traffic lights states declare them as being 

The improved system formalises a mechanism for representing and capturing information and data from appliances especially in M2M applications and simplifies the way the captured data are used and managed. As such it has applications in many areas involving data acquisition from remote appliances.

The system may also facilitate improved diagnostic and functional capabilities especially when working with other M2M appliances and applications. M2M involves capturing lots of data from a wide range of devices and appliances. The challenge and the opportunity is how you analyse and use this data. The improvement provides a method for organising data acquired on from M2M devices that will make it easier to use and make sense of that data.

1 The SNMP protocol supports data structures that are hierarchies of objects and that facilitate external processes to query these data structures. The data is queried either item by item or collections of data within a sub tree of the hierarchy of the data objects can be queried in a single request. This is a mature technology that is widely supported.

2 OMA DM and the nascent LWM2M protocols support the representation of data structures in a way that is hierarchical and very similar to SNMP but optimised for M2M environments.

A deficiency of these hierarchical data models is that they are restrictive and simplistic. They do not reflect the way that the data is required to be used. As a consequence the application developer needs to understand where and how the data is organised and usually needs to make multiple requests for data in order to capture all the data items of interest. Acquiring the data using multiple queries is expensive designing applications that use the data requires domain knowledge which is costly and limits how that data can be used by applications.

The improvement describes a way of organising and representing data values into list structures where data items are organised into contiguous sequences of values. The data items that are of potential interest on an M2M device to application developers are mapped onto list structures. Examples of illustrative lists 

1 Hardware Diagnostics list sequence of data values representing hardware checks on the appliance CRC memory checks electric circuit behaviour temperature sensor water ingress sensors etc. 

2 Equipment version List sequence of version values of all the identifiable components and software elements.

3 Sensor list list of sensor values as unprocessed processed values. An example of a processed value would be where a temperature sensor value was averaged over a five minute period or a radio signal strength was averaged over a three month period.

4 Private Personal list Location information personal details of end customer that is subject to data protection law.

5 Time series lists where multiple lists may be organised into a sequence such that lists can be accessed and managed in a sequential or random access fashion.

1 The Hardware diagnostic list may be used by the organisation maintaining the smart metering equipment in the field and would be used to diagnose and predict defects.

2 The equipment version list may be used by the organisation supplying updates of firmware software to verify that the correct version of update was being applied.

4 The Private Personal List may be used with appropriate security controls to manage customer centric functions.

5 The sensor list see 3 above may be managed as a time series list whereby sensor values are acquired at regular intervals e.g. every 15 minutes and placed into a multi row time series list. Applications may then query the values as appropriate. For instance a meter reading application would query the device twice a day and read all the time series data acquired throughout the preceding period.

In one aspect simple hierarchical data structures for M2M devices are mapped onto list structures using concepts that are common to relational databases. Many of the constructs familiar to SQL relational database programming can be incorporated into this aspect e.g. the use of null values reflection mechanisms triggers primary and foreign keys .

There are many features of this approach please refer to the above clauses that will make the application developers use of data held in lists much easier. The idea could be implemented by the designers of hardware who would define the feature lists into the product in order for third parties to make best use of the products. This could be implemented declaratively by the equipment developer who would use an XML notation to describe the elements of each list and their properties. For example a list item was a moving average with a sample time of x and with results to be normalised within a range a through b.

List management operations may use set theory constructs and so allow two lists to be queried as a Join List 1 List 2 or an intersection List 1 and List 2 or as a difference List 1 List 2 . This may make it easier for application developers to map data queries onto relevant data structures.

List management operations may use the relational SQL operations and constructs to query and modify data structures. List components may be mapped onto other data structures at the application level using relational operators and constructs. For example Temperature Sensor readings may be mapped to a list element as a 30 day moving average. This may make it easier for product developers to present data for application use.

The DM platform may be described as a dataflow machine that uses set theory on input datasets to generate result sets that trigger additional activities analytics diagnostics and alerts .

The device manager receives instructions or commands to take an action on the one or more stored attributes. For example this may be to read write erase or update an attribute or group of attributes. The device manager is also configured to receive from one or more devices values or data that correspond with the stored attributes. A synchroniser maintains synchronisation between the stored attributes and the attributes or values associated with each of the devices. The synchroniser may be part of the device manager separate or remote.

In other words actions may be carried out on the attributes stored in memory and or values may be received or retrieved from the physical devices . The synchroniser ensures that stored attributes and the device values or attributes are maintained in synchronisation or updated to reflect any changes.

The computer system and architecture may include a processor such as a central processing unit CPU . The processor may execute logic in the form of a software program. The computer system may include a memory including volatile and non volatile storage medium. A computer readable medium may be included to store the logic or program instructions. The different parts of the system may be connected using a network e.g. wireless networks and wired networks . The computer system may include one or more interfaces. The computer system may contain a suitable operating system such as UNIX Windows or Linux for example.

As will be appreciated by the skilled person details of the above embodiment may be varied without departing from the scope of the present invention as defined by the appended claims.

Many combinations modifications or alterations to the features of the above embodiments will be readily apparent to the skilled person and are intended to form part of the invention. Any of the features described specifically relating to one embodiment or example may be used in any other embodiment by making the appropriate changes.

