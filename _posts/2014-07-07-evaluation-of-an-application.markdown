---

title: Evaluation of an application
abstract: It is presented a method for evaluating an application intended to be installed in a wireless terminal of a cellular network. The method is performed in an application development device and comprises the steps of: obtaining performance data associated with an execution of the application in a test wireless terminal in a simulated or real cellular network, the performance data being obtained for each cellular data session of the execution of the application, each cellular data session being defined as a period when the test wireless terminal is in a cellular network connection state when data transfer is possible; and evaluating the performance data by comparing the in performance data with reference performance data, the comparison being based on the duration of each cellular data session.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09471467&OS=09471467&RS=09471467
owner: Telefonaktiebolaget L M Ericsson (publ)
number: 09471467
owner_city: Stockholm
owner_country: SE
publication_date: 20140707
---
The invention relates to a method an application development device a computer program and a computer program product for evaluating an application intended to be installed in a wireless terminal of a cellular network.

The smartphone application market has exploded in the last few years with a myriad of entertaining and useful applications for smartphone users mostly provided at a reasonable cost.

The development of the applications is simplified by the provision of software development kits SDKs to simplify for developers to develop and maintain applications.

However not much focus has been given to network efficiency or application performance for applications. Hence many applications consume network resources in a far from optimal way. This not only consumes excess resources for the user of the application but also for other users since cellular network resources are shared among many users. Moreover the battery consumption is increased with inefficient network resource usage.

To design and develop applications that are efficient for the cellular network is a complex task that requires detailed knowledge in how cellular networks execute requests deals with bursty traffic handle idling users and much more.

It is an object to provide a way for the developer to conveniently evaluate cellular network performance of an application.

According to a first aspect it is presented a method for evaluating an application intended to be installed in a wireless terminal of a cellular network. The method is performed in an application development device and comprises the steps of obtaining performance data associated with an execution of the application in a test wireless terminal in a simulated or real cellular network the performance data being obtained for each cellular data session of the execution of the application each cellular data session in being defined as a period when the test wireless terminal is in a cellular network connection state when data transfer is possible and evaluating the performance data by comparing the performance data with reference performance data the comparison being based on the duration of each cellular data session. In this way the application is evaluated in terms of impact in the cellular network allowing the application developer to adjust the code of the application e.g. to reduce the cellular data session time required to transfer the desired data.

The method may further comprise the step of presenting a result of the evaluating of performance data.

In the step of obtaining performance data the performance data may comprise a measurement of data transfer magnitude.

In the step of obtaining performance data the performance data may comprise at least one of the following number of transferred uplink bytes number of transferred downlink bytes time spent in a specific cellular network connection state number of transitions of cellular network connection states downlink energy estimate and uplink energy estimate.

The cellular network connection states when data transfer is possible may be only CELL FACH a state when a Forward Access Channel is available and CELL DCH a state when Dedicated Channel is available.

The cellular network connection state when data transfer is possible may consist of a single state of an RRC CONNECTED Radio Resource Control Connected state.

The step of evaluating the performance may comprises comparing the performance data with a strict subset of the reference performance data the strict subset being in defined by a range of durations of the cellular data sessions for reference performance data in which the duration of the cellular data session falls.

According to a second aspect it is presented an application development device arranged to evaluate an application intended to be installed in a wireless terminal of a cellular network. The application development device comprises a processor and a memory storing instructions that when executed by the processor cause the application development device to obtain performance data associated with an execution of the application in a test wireless terminal in a simulated or real cellular network the performance data being obtained for each cellular data session of the execution of the application each cellular data session being defined as a period when the test wireless terminal is in a cellular network connection state when data transfer is possible and evaluate the performance data by comparing the performance data with reference performance data the comparison being based on the duration of each cellular data session.

The instructions stored in the memory of the application development device when executed by the processor may further cause the application development device to present a result of the evaluating of performance data.

The instructions to obtain may comprise instructions that when executed by the processor cause the application development device to obtain performance data comprising a measurement of data transfer magnitude.

The instructions to obtain may comprise instructions that when executed by the processor cause the application development device to obtain performance data comprising at least one of the following number of transferred uplink bytes number of in transferred downlink bytes time in spent in a specific cellular network connection state number of transitions of cellular network connection states downlink energy estimate and uplink energy estimate.

The instructions to obtain performance data may comprise instructions that when executed by the processor cause the application development device to consider the cellular network connection states when data transfer is possible are only CELL FACH a state when Forward Access Channel is available and CELL DCH a state when Dedicated Channel is available.

The instructions to obtain performance data may comprise instructions that when executed by the processor cause the application development device to consider the cellular network connection states when data transfer is possible to consist of a single state of an RRC CONNECTED Radio Resource Control Connected state.

The instructions to evaluate the performance may comprise instructions that when executed by the processor cause the application development device to compare the performance data with a strict subset of the reference performance data the strict subset being defined by a range of durations of the cellular data sessions for reference performance data in which the duration of the cellular data session falls.

According to a third aspect it is presented an application development device comprising means for obtaining performance data associated with an execution of an application in a test wireless terminal in a simulated or real cellular network the application being intended to be installed in a wireless terminal of a cellular network the performance data being obtained for each cellular data session of the execution of the application each cellular data session being defined as a period when the test wireless terminal is in a cellular network connection state when data transfer is possible and in means for evaluating the performance data by comparing the performance data with reference performance data the comparison being based on the duration of each cellular data session.

According to a fourth aspect it is presented a computer program product for evaluating an application intended to be installed in a wireless terminal of a cellular network. The computer program product comprises a non transitory computer readable medium having instructions thereon the instructions comprising code for obtaining performance data associated with an execution of the application in a test wireless terminal in a simulated or real cellular network the performance data being obtained for each cellular data session of the execution of the application each cellular data session being defined as a period when the test wireless terminal is in a cellular network connection state when data transfer is possible and code for evaluating the performance data by comparing the performance data with reference performance data the comparison being based on the duration of each cellular data session.

Generally all terms used in the claims are to be interpreted according to their ordinary meaning in the technical field unless explicitly defined otherwise herein. All references to a an the element apparatus component means step etc. are to be interpreted openly as referring to at least one instance of the element apparatus component means step etc. unless explicitly stated otherwise. The steps of any method disclosed herein do not have to be performed in the exact order disclosed unless explicitly stated.

The invention will now be described more fully hereinafter with reference to the accompanying drawings in which certain embodiments of the invention are shown. This invention may however be embodied in many different forms and should not be construed as limited to the embodiments set forth herein rather these embodiments are provided by way of example so that this disclosure will be thorough and complete and will fully convey the scope of the invention to those skilled in the art. Like numbers in refer to like elements throughout the description.

The cellular network may e.g. comply with any one or a combination of LTE Long Term Evolution W CDMA Wideband Code Division Multiple Access EDGE Enhanced Data Rates for GSM Global System for Mobile communication Evolution GPRS General Packet Radio Service CDMA2000 Code Division Multiple Access 2000 or any other current or future wireless network such as LTE Advanced as long as the principles described hereinafter are applicable.

Over the wireless interface uplink UL communication occurs from the wireless terminal to the radio network node and downlink DL communication occurs from the radio network node to the wireless terminal . The quality of the wireless radio interface to each wireless terminal can vary over time and depending on the position of the wireless terminal due to effects such as fading multipath propagation interference etc.

The radio network node is also connected to the core network for connectivity to central functions and a wide area network such as the Internet.

There is also an application development device connected to the wide area network . The application development device provides an environment for a software developer to be able to develop an application also known as app which is a software program which can be installed in the wireless terminal . The installation can occur by the application developer publishing the application using an application provider . The user of the wireless device can then find the application using the application provider and install the application in the wireless device . The application provider can e.g. be an application repository such as Google Play or Apple App Store.

When the application is executing in the wireless device it will on occasion communicate with an application server e.g. to retrieve data store data or request certain functionality from app server etc. The wireless device will then communicate uplink and downlink via the radio network node core network and the wide area network to reach the application server . Depending on how the application has been developed the cellular network can be better or worse utilised. As is explained in further detail below the application developer using the application development device thus needs guidance as to how efficient the application is when utilising the cellular network .

The evaluator can be included within the SDK or it can be a separate software program. In any case an application developed using the SDK can be evaluated using the evaluator .

The reference performance data comes from statistical data captured from cellular networks based on application activities and traffic characteristics. In other words large amount of execution data from cellular data sessions are beforehand recorded from real cellular networks processed and stored as a database of application execution characteristics. The database is implemented and distributed as part of the SDK and or evaluator and can thus be used by developers to build and test new applications for smartphones tablets etc. The database can be static and updated only when a new in version of the SDK and or evaluator is released or the database can be configured to update its data dynamically over the wide area network.

This data can e.g. comprise session time number of state switches per session total time spent in specific states per session and total data sent in each direction in each state. The data is analysed and characterised to serve as the reference performance data for the application development.

The reference performance data base is thus created by using a large number of session samples from one or more cellular networks. Using these samples the characteristics per sample are calculated the results are binned based on session time and the average values per bin are calculated. The results will then provide a good representation of the average characteristics per session based on the session time in the networks measured and these characteristics can then be used for evaluating new applications to be developed.

The unit loadtime is defined here due to the fact that in a W CDMA system the momentary air interface uplink load is not characterised by transmitted power but by the load in terms of thermal noise rise RoT Rise over Thermal . Corresponding with the definition where energy equals power multiplied by time loadtime is defined as load multiplied by time to arrive at a measurement which is equivalent to energy but in the uplink.

It is to be noted that the graphs of are only examples and are presented to better explain embodiments presented herein. Moreover only a subset of possible parameters are illustrated in .

Looking now to this is a schematic graph illustrating reference performance data in uplink. A solid line represents uplink CP Control Plane cost defined in more detail below . A long dashed line represents uplink loadtime and a dotted line represents data magnitude of uplink data transfer.

A solid line represents minimum downlink data and a short dashed line represents recommended downlink data. A dash dotted line represents maximum downlink CP cost and a long dashed line represents recommended CP cost.

In the graph the performance of sessions from two respective apps are plotted. A session for a first app has a first downlink data value and a first downlink CP cost value . The downlink data value is clearly above the minimum downlink data line and almost at the recommended downlink data line . Moreover the downlink CP cost is on the recommended downlink CP cost line . All in all the first app appears to perform decently with some improvement that can be done particularly in the downlink data value. The developer could address this by moving some time demanding processing which is performed during the cellular data session to instead be performed when the session is not active. This reduces the session time shifting the plotted values to the left which would make the downlink data value approach or even surpass the recommended downlink data line

A session for a second app has a second data value and a second downlink CP cost value . The plotted values for this app are on the recommended lines whereby it performs better relative to the first app.

In an obtain performance data step performance data associated with an execution of the application in a test wireless terminal is obtained. As explained above the test wireless terminal can be part of a simulated cellular network within the application development device or a real cellular network external to the application development device . The performance data is obtained for each cellular data session of the execution of the application where each cellular data session is defined as a period when the test wireless terminal is in a cellular network connection state when data transfer is possible. For instance in W CDMA the states when data transfer is possible consists of the following states CELL FACH a state when a Forward Access Channel is available and CELL DCH a state when Dedicated Channel is available.

In one embodiment the cellular network connection state when data transfer is possible consists of a single state of an RRC CONNECTED Radio Resource Control Connected state.

For instance the performance data can comprise a measurement of data transfer magnitude e.g. downlink data and or uplink data which has proven to be a good measurement of resource usage in a cellular network and which is also easily obtained. Alternatively or additionally the performance data comprises one or more of the following number of transferred uplink bytes number of transferred downlink bytes time spent in a specific cellular network connection state number of transitions of cellular network connection states downlink energy estimate uplink energy estimate.

Hence the application development device gathers the performance data required to calculate the characteristics used for evaluation.

In an evaluate step the performance data is evaluated by comparing the performance data with reference performance data. This comparison is based on the duration of each cellular data session.

In order to give guidance to the developer and encourage the smartphone community to in use the networks in an efficient way recommended and acceptable levels for each characteristic involved can be added to the database see . These levels can be dynamic or adapted or just the average levels multiplied by a constant value. These levels will then serve as a recommended target level for the developer. The levels do not need to be imposed or mandatory to reach before approval since that may lead to negative effects like additional data transmission just to reach a recommended level.

The reference performance data database and the analysis software functionality are then built and included in SDK where it interacts with the application programming interface API of the SDK.

This step may comprise comparing the performance data with a strict subset e.g. bins of the reference performance data the strict subset being defined by a range of durations of the cellular data sessions for reference performance data in which the duration of the cellular data session falls.

By using the reference performance data from cellular networks the developer will get quick feedback of how the application performs in various traffic cases.

The method can use different performance data as a discriminating variable for example the total time spent in connected state and then evaluate the execution based on this. The statistical characteristics for other applications with the same discriminating variable value are used as comparison which enables a straight forward yet accurate measure of how the application performs from a network perspective.

Distinction of application category can be included but in order to get a general performance evaluation this is not required. Also such categorisation can be arbitrary in and to work well it requires well defined category definitions to avoid any erroneous categorisations.

Now the method illustrated in will be described. Only new or modified steps compared to the method of will be described here.

In a present step a result of the evaluating of performance data is presented to the user of the application development device.

Optionally this step comprises presenting recommendations indicating recommended performance data values as shown in and described above .

Also the performance data can optionally be included when the application is presented by the application provider whereby there is a greater incentive for the application developer to develop applications which are efficient in their usage of the cellular network.

An example will now be described for further illustration. The example explains how a reference database is created for application development and then applying this reference database to get a performance evaluation measurement for the application under development. The example will for clarity only use a small set of data but nothing prevents the method to be scaled up to more realistic data set volumes i.e. thousands or millions of samples.

From a live network samples of user data are captured. Each sample describes a session from the connection setup until the session is terminated. In a cellular network the connection usually is kept as short as possible to preserve radio resources leading to session termination after a short time of inactivity. Hence a session usually only consists of a burst of packets all related to the same task e.g. watching a video clip or opening a web page.

The information collected per sample is the time spent in active states e.g. for WCDMA CELL DCH and CELL FACH states the data sent in either direction and in either state and the number of transitions between states. All this will describe the session from a utilisation perspective of the air interface resources which is typically the most scarce resource in a cellular network.

The session samples of reference performance data as given in the example in Table 1 are fed into a formula to calculate the radio interface energy utilised in each session separated into the DL energy and the UL loadtime. The formula is a sum of products where each of the session characteristics are multiplied with a specific weight and summed up to a total value per direction in accordance with formula 1 above.

The components in 1 are here the characteristics outlined in the table above and the weights are as follows 

For the total resource usage in each direction the total sum of products applies resulting in the values in Table 2 

For the resource usage for control plane activities the sum of the costs for state transitions and residing in a state applies DL CP Cost StateCost DL TransCost DL 2 StateCost DL DL Cost time  time  DL Cost time  time  3 TransCost DL DL Cost 22 DL Cost 22 DL Cost 22 DL Cost 22DL Cost 22 DL Cost 22 4 UL CP Cost StateCost UL TransCost UL StateCost UL UL Cost time  time  UL Cost time  time  5 TransCost UL UL Cost 22 UL Cost 22 UL Cost 22 UL Cost 22 UL Cost 22 UL Cost 22 6 

When calculated the values of the CP cost for the 15 session samples in Table 1 are shown in Table 3 

The total data consumption can also be summed up per session sample Total DL Data data   data   7 Total UL Data data   data   8 which will result in the following data volumes per sample 

The total time is thus equal to the session time. This results in the total times per session shown in Table 5 

Table 6 then shows the calculated values per session sample for used air interface resources control plane share of the resource usage the total data volume transferred and the total session time are then sorted according to the total time for each session 

The samples are then binned into suitable bins providing a good representation of the session time value span as shown in Table 7 

Within each bin average values are then calculated for each characteristic as shown in Table 8. These values can then be used for evaluating the execution characteristics for applications.

These values will serve as the base for providing reference values for evaluating app performance. However a scaling can be done in order to set more aggressive target values than just the current average values. To drive improved performance and enhanced utilisation of the radio resources higher activity and more efficient utilisation per connected time unit are encouraged.

This means that more transferred bytes and less control plane activities are desired in relation to a session time and since the vast majority of the air interface energy used comes from data transfers higher total energy per time unit will be used. In this example recommended levels are created from the average levels by multiplying with the following factors 

This results in a database for evaluating app performance which obviously will be of better resolution using millions of samples and preferably smaller bins.

The memory can be any combination of read and write memory RAM and read only memory ROM . The memory also comprises persistent storage which for example can be any single one or combination of magnetic memory optical memory solid state memory or even remotely mounted memory.

A data memory is also provided for reading and or storing data during execution of software instructions in the processor . The data memory can be any combination of read and write memory RAM and read only memory ROM . The data memory can e.g. store reference performance data.

The application development device further comprises an I O interface for communicating with other external entities. The I O interface also includes a user interface e.g. comprising a keyboard a mouse trackpad display etc. Speakers and or a microphone may also form part of the I O interface .

Other components of the application development device are omitted in order not to obscure the concepts presented herein.

A performance data obtainer is arranged to obtain performance data associated with an execution of the application in a test wireless terminal in a simulated or real cellular network. This module corresponds to the obtain performance data step of .

An evaluator is arranged to evaluate the performance data by comparing the performance data with reference performance data. This module corresponds to the evaluate step of .

A presenter is arranged to present a result of the evaluating of performance data. This module corresponds to the present step of .

The invention has mainly been described above with reference to a few embodiments. However as is readily appreciated by a person skilled in the art other embodiments in than the ones disclosed above are equally possible within the scope of the invention as defined by the appended patent claims.

