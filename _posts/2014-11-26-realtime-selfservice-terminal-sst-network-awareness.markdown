---

title: Real-time self-service terminal (SST) network awareness
abstract: Operational data and metrics from a Self-Service Terminal (SST) network are continuously acquired in a first format at a server. The first format is normalized and delivered to a configured mobile application on a mobile device. The mobile application selectively renders the operational awareness data/metrics for the SST network within one or more screens of a display on the mobile device. The operator of the mobile application can define views of the data/metrics, define alerts or notifications to propagate, and interact with the data/metrics to obtain more or less detail for that data/metrics.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09471940&OS=09471940&RS=09471940
owner: NCR CORPORATION
number: 09471940
owner_city: Duluth
owner_country: US
publication_date: 20141126
---
Managing an Automated Teller Machine ATM network is challenging for branch managers and service providers. This is so because a variety of services exists to provide management information but such services require a specific interface and login credentials to a website. Learning the interfaces from different service providers and finding a terminal with a screen large enough to support a quality review of the information provided by each of the services providers through a browser are time consuming if not impractical exercises.

Additionally some managers or service providers may have to subscribe to multiple different services because the level of detail provided by one provider may be better than another provider while still another provider may provide different data types or data views that the managers or service providers prefer. This creates even more complication and difficulty for the managers and service providers in quickly ascertaining the health and needs of the ATM networks that they manage.

Moreover the individuals that need to have real time operational information associated with ATM networks do not have the necessary time to dig through and analyze minute details associated with the networks. These individuals want to have the information pushed to them in a format that is easily understood consistent easily visible on a display of a device that they are using and that can be integrated across different ATM networks that are being managed.

Therefore there is a need to provide improved terminal network metrics for network managers and service providers in a more timely consistent and easily understood manner.

In various embodiments methods and a system for providing real time Self Service Terminal SST network awareness information are presented.

According to an embodiment a method for providing real time SST network awareness information is presented.

Specifically data is obtained from a Self Service Terminal SST network repository. Next the data is reformatted in a mobile device compatible format for delivery to a mobile device.

Furthermore the various components that are identified in the are illustrated and the arrangement of the components is presented for purposes of illustration only. It is to be noted that other arrangements with more or less components are possible without departing from the teachings of providing real time SST network awareness information presented herein and below.

The real time SST network awareness information delivery system includes multiple ATM data server systems and an information delivery server and multiple mobile devices and . The information delivery server includes ATM native data formats a data translator normalizer and mobile device data formats . Each mobile device or includes a dashboard and ATM network monitoring app application or .

The ATM data server systems and are each connected to one or more ATM networks. Each ATM data server system or collects real time data for the ATMs within its managed ATM network. Such data can include by way of example only ATM identifiers ATM network identifiers ATM resource status identifiers ink levels in receipt printers currency total and currency denominations available for dispensing etc. ATM or ATM network profitability metrics transaction totals failed transactions transaction load transaction volume incident metrics servicing trips failures of peripherals failures of transactions etc. .

The data housed in each of the ATM data server systems or is organized and accessible through its own data formats data types reporting interface and or query interface. In an embodiment the data format and interface of the ATM data server system is different from and perhaps incompatible with that which is associated with the ATM data server system .

Information delivery server includes interfaces and information pulling from each of the ATM data server systems through the ATM native data formats module . That is the ATM native data formats module utilizes an interface for accessing data and metrics in real time or near real time from the ATM data server system and in some cases a different interface for accessing data and metrics in real time or near real time from the ATM data service system .

Once the data and metrics are obtained the data and metrics are provided as input to the data translator normalizer . Here the data format and the data types obtained from the ATM data server systems and are translated and or normalized into a standard format accessible from a standard interface. Once the data and the metrics are normalized the normalized data and metrics are passed to the mobile device data formats module .

The mobile device data formats module includes a variety of interfaces for interacting with pushing information to information the normalized data and metrics and handling requests for specific types of data from the mobile devices and through those devices dashboard and ATM network monitoring apps and .

The description of the dashboard and ATM network monitoring apps and is presented for just app it is noted that this is being done for improved readability and that which applies to app applies to app as well.

The app includes a dashboard service for the mobile device that permits some aspects of the data from one or more of the ATM data server systems to be continuously displayed and updated in real time on the mobile device . The dashboard service is rendered on a screen within the display of the mobile device . It is noted that the types of real time data or information presented by the dashboard service can be configured by an operator of the mobile device interacting with an interface associated with the app . Moreover the location of the dashboard information or the screen with the display of the mobile device can be configured by the operator of the mobile device using the interface associated with the app . The interface may also be used by the operator of the mobile device to request specific types of data or information from one or more of the ATM server systems and or .

The app also directly interfaces with a standard interface of the mobile device data formats module of the information delivery server to communicate operated initiated requests for data information relevant to the dashboard service and or any operator on demand requests for specific data information.

The app may temporarily hold a variety of supporting data information acquired from the mobile device data formats module in storage and or cache of the mobile device .

The interface provided to the operator of the mobile device by the app may be responsive to selections of data made by the user from the screen having the dashboard service. This permits the operator to drill down into underlying supporting data for a specific dashboard presented data or metric item or even change the view or level of detail presented within the screen for that data or metric item. Additionally the interface provided to the operator may permit the operator to decrease the level of detail to a higher more general view through interaction with the interface. In this way the operator can drill down into metric and data items for more fine grain detail or the operator can aggregated up a current level of detail associated with a selected metric or data item to obtain a coarse grain level of detail.

In this way an operator of mobile device can obtain real time or near real time data information relevant to one or more ATM data server systems and .

Once the dashboard service is configured by an operator of the mobile device the app communicates to a normalized interface associated with the mobile device data formats module a desired configuration of data and metric items for a specific ATM server system or from multiple ATM server systems and . The interface of the mobile device data formats module then communicates perhaps through different interfaces with the data translator normalizer module . The data translator normalizer module formats the requests for data or metrics and communicates with the ATM native formats module . The ATM native formats module selects the appropriate interface or Application Programming Interface API calls to pull the desired data from the needed ATM data server system and or .

Moreover the modules continuously operate to periodically keep pulling the requested data and metrics and delivering the updated data and metrics to the app where the presentation of the data and metrics are continuously updated in real time or near real time.

At any time the operator of the mobile device is free to access the interface of the app to remove data items or metrics from the presentation of data and metrics associated with the dashboard service. Moreover the operator can at any time use the interface of the app to add new data and or metrics or make a specific request for data or a report.

In an embodiment the data passed between the mobile device data formats module and the app is in a Java Script Object Notation JSON . Thus when new data associated with new data types is added to the ATM data server systems this can be delivered to the app and presented to the user to ask if the user is interested in such new data for presentation with the dashboard services. So new data and new data types can be dynamically added and integrated for presentation within the mobile device . In some cases the JSON is dropped as a service on the mobile device to automatically pull the new data to the mobile device . The mobile device data formats module provides the JSON modules to the mobile device .

In an embodiment the app resolves a current physical or geographical location for the mobile device and uses this along with ATM network identifiers and or ATM identifiers to provide geographical context to the operator of the mobile device such as the geographical location of the operator of the mobile device relative to a specific ATM or network of ATMs.

Other customizable geographical context overlay views can be presented on a screen of the display of the mobile device via the app such as a map with a location of each ATM and or ATM network and when a specific network or ATM is selected by the user data or metrics relevant and configured for that network of ATMs or that ATM is presented as a popup menu.

The interface of the app may also permit the user to define alerts and notifications that are automatically pushed to social media and or email to users that have a stake in the ATM networks. Still further the operator of the mobile device can use the interface of the app to manually initiate an alert or notification. So the operator can be proactive in an automated manner or manual manner to alert stakeholders via social media text messages and or email of situations occurring within the ATM networks that are of interest to those stakeholders.

Essentially the views on operational ATM network data the alerts and the notifications can be customized defined and managed by the operator of the mobile device through the interface to the app . This gives proactive dynamic and real time or near real time operational awareness of and control of the ATM networks to the operator of the mobile device .

In an embodiment the SST network information manager is executed on the information delivery server of the .

In an embodiment the device that executes the SST network information manager is a part of a cloud based processing environment.

In an embodiment the device that executes the SST network information manager is part of a retail establishment.

In an embodiment the device that executes the SST network information manager is part of a financial institution.

In an embodiment the device that executes the SST network information manager is a Local Area Network LAN server.

In an embodiment the device that executes the SST network information manager is a Wide Area Network WAN server.

At the SST network information manager selectively obtains data from an SST network repository. In an embodiment the SST network repository is one of the ATM data server systems or of the .

According to an embodiment at the SST network information manager determines based on selections made by an operator of the mobile device through a mobile device interface that communicates with the SST network information manager. So the selections are driven by a mobile device operator such as a manager of an enterprise an executive an enterprise an administrator and or support staff associated with maintaining an SST network.

In an embodiment at the SST network information manager pulls the data from the SST network repository using a native interface or native API associated with the SST network repository.

In an embodiment at the SST network information manager pulls the data from the SST network repository continuously at predefined intervals or based on detection of an event such as a change in a portion of the data .

In an embodiment of and at the SST network information manager obtains at least a portion of the data as real time operational metrics for the one or more SSTs that comprise an SST network that the SST network repository gathers data for.

In an embodiment of and at the SST network information manager obtains at least another portion of the data as incident or support information associated with the SSTs.

At the SST network information manager reformats the data in a mobile device compatible format for delivery to a mobile device. This was discussed at length above with the discussion of the .

According to an embodiment at the SST network information manager pushes the reformatted data to a mobile application on the mobile device. In an embodiment the mobile application is one of the dashboard and ATM network monitoring app or of the .

In an embodiment of and at the SST network information manager updates the reformatted data based on one of a preconfigured interval of time a change in a portion of the data a specific request from the mobile application and automatic detection of a configured event.

In an embodiment at the SST network information manager receives a request for different data from the mobile device acquires the different data from the SST network repository reformats the different data and delivers the reformatted different data to the mobile device.

In an embodiment at the SST network information manager processes an alert or a notification sent from the mobile device in response to the mobile device that evaluates the reformatted data. Processing may include taking an automated action or forwarding the alert or the notification to one or more predefined entities.

In an embodiment the device that executes the SST network information app is the mobile device or of the .

In an embodiment the device that executes the SST network information app is one of a mobile phone a tablet a laptop and a wearable processing device.

In an embodiment the SST network information app is the dashboard and ATM network monitoring app or of the .

The SST network information app interacts with the method of the to provide real time or near real time SST network management information alerts and or notifications to an operator of a mobile device that executes the SST network information app.

At the SST network information app receives selections for data that is relevant to operational awareness data gathered by an SST network repository for SSTs that comprise an SST network. The selections made by the operator that interacts with the interface on the mobile device.

At the SST network information app sends a configuration to an information delivery server that defines the selections for the data. The information delivery server interacts with the SST network repository to obtain the selections for the data.

At the SST network information app renders the data within one or more screens on a display of the mobile device as received back from the information delivery server.

According to an embodiment at the SST network information app provides the rendered data within one or more of the screens as a dashboard service. In an embodiment the dashboard service is the dashboard service discussed above with the .

In an embodiment at the SST network information app provides the rendered data with a data interface and permits the operator to interact with the data interface by interacting with the rendered data to obtain more detailed data less detailed data more detailed views of the data and less detailed views of the data based on the original presented data within the screens.

In an embodiment at the SST network information app provides one or more geographical contextual views of the rendered data within the screens including a current location of the mobile device relative to the SST network and current locations for each of the SSTs within the SST network. In an embodiment the geographical contextual views are presented as interactive geographical maps.

According to an embodiment at the SST network information app receives alert or notification conditions from the operator interacting with the interface.

In an embodiment of and at the SST network information app evaluates conditions against the data to automatically raise an alert or a notification to the information delivery server.

In an embodiment of and at the SST network information app evaluates the conditions against the data to automatically raise an alert or a notification to one or more of a text message number an email account a social media account a news feed and a website portal.

In an embodiment the real time SST network awareness information system implements inter alia the processing discussed above with the .

In an embodiment the real time SST network awareness information system implements inter alia the processing discussed above with the .

In an embodiment the real time SST network awareness information system implements inter alia the processing discussed above with the .

The real time SST network awareness information system includes a server and an SST network information manager .

The server includes one or more processors memory non volatile storage and one or more network connections wired wireless or a combination of wired and wireless .

In an embodiment the SSTs associated with the SST network being managed are self service Point Of Sale POS devices.

In an embodiment the SSTs associated with the SST network are combinations of kiosks ATMs and self service POS devices.

The SST network information manager is adapted and configured to execute on the server obtain SST operational data from a native SST network repository and deliver selective portions of the operational data to a mobile device in real time or near real time.

According to an embodiment the SST network information manager is further adapted and configured to process an alert or a notification provided by the mobile device in response to the selective portions of the operational data.

It should be appreciated that where software is described in a particular form such as a component or module this is merely to aid understanding and is not intended to limit how software that implements those functions may be architected or structured. For example modules are illustrated as separate modules but may be implemented as homogenous code as individual components some but not all of these modules may be combined or the functions may be implemented in software structured in any other convenient manner.

Furthermore although the software modules are illustrated as executing on one piece of hardware the software may be distributed over multiple processors or in any other convenient manner.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

In the foregoing description of the embodiments various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting that the claimed embodiments have more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Description of the Embodiments with each claim standing on its own as a separate exemplary embodiment.

