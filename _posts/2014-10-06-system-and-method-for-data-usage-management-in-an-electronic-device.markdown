---

title: System and method for data usage management in an electronic device
abstract: A system and method for data usage management in an electronic device is provided. The method includes tracking an estimated cost of a download in a currency set by a user, determining the estimated cost of the download in the currency set by the user, displaying the estimated cost of the download, determining application data usage, implementing notifications of the data usage, and displaying the data usage, wherein a widget or an application is used to display the data usage.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09462137&OS=09462137&RS=09462137
owner: Samsung Electronics Co., Ltd.
number: 09462137
owner_city: 
owner_country: KR
publication_date: 20141006
---
This application claims priority under 35 U.S.C. 119 a to an Indian Patent Application filed on Oct. 4 2013 in the Indian Patent Office and assigned Serial No. 2960 DEL 2013 the entire disclosure of which is incorporated herein by reference.

The present invention relates generally to a system and method for data usage management in an electronic device and more particularly to a system and method for providing enhanced control over estimate and overall cost and consumption of data in electronic devices.

Today is an era of smart phone wired or wireless devices such as but not limited to tablets phablets Personal Digital Assistants PDAs touch phones feature phones wearable computing devices handheld devices flexible devices etc. As the usage of smart phone devices increases so does the uses of associated technology such as but not limited to Internet surfing web chatting instant messaging etc. Also there are certain applications which run in the background. However a user of the device is mostly unaware of the data usage of the various applications or technologies which are running. The effect of this lack of awareness is that the user has to bear the additional cost of the data download.

There are several ways in which the user can identify the data usage like using the data usage setting in the Android devices. However these are all limited to the fact that the usage is shown in the form of data units like MBs Megabytes or in GBs Gigabytes or the like. The user is more concerned about the cost of the data used and is less concerned with the technical terms of the data units.

A conventional solution describes a system and method of providing a notification to the mobile device when the thresholds of certain variables are reached. However notification is only for the threshold reached.

The prior art does not give the user a firsthand experience where he can instantaneously check his data usage nor does it give the user the flexibility to check the data usage in the form of a currency of his choice. The present invention describes a system and method to provide a user with the flexibility to check the data usage by the incurred cost.

The present invention has been made to address at least the problems and disadvantages described above and to provide at least the advantages described below. Accordingly an aspect of the present invention is to provide a system and a method for helping a user to save costs by providing enhanced control over data costs and data usage in mobile devices.

According to another aspect the present invention provides a system and method to show estimated cost by enabling people to view the price they will have to pay for consuming content before after and during downloading of the data or streaming content.

According to another aspect the present invention provides a system and method that will provide a notification to a user when certain thresholds have been reached or exceeded or about to be exceeded as set by user relating to data consumption in the form of data usage notifications for a particular time period such as but not limited to daily notification monthly notification etc. to keep track and manage the data usage by the user. It also provides a system and method that will allow a user to set restrictions on data usage and downloading.

According to another aspect the present invention provides a system and method to track the download expenses in currency set by the user such as but not limited to local currency currency of a foreign country etc. as data usage in data units is not understood by users and budgeting in terms of money is easier rather than data units.

According to another aspect the present invention provides widgets or applications and data displays for monitoring data cost for a time period.

According to another aspect the present invention provides a system and method to provide data handover on roaming.

According to another aspect of the present invention an Application data usage indication is provided which allows the users to view the amount of data being consumed in indicator area while accessing the application.

In accordance with an aspect of the present invention a method for data usage management in an electronic device is provided. The method includes tracking an estimated cost of a download in a currency set by a user determining the estimated cost of the download in the currency set by the user displaying the estimated cost of the download determining application data usage implementing notifications of the data usage and displaying the data usage wherein a widget or an application is used to display the data usage.

In accordance with another aspect of the present invention a method for data handover on roaming in a multi SIM phone is provided. The method includes switching data services to a non roaming SIM from a roaming SIM when a non roaming SIM data preference is set prior to the multi SIM phone moving from a non roaming area to a roaming area and switching data services to the non roaming SIM from the roaming SIM when the SIM is in a roaming area and the non roaming SIM data preference is set after the multi SIM phone is moved to the roaming area.

In accordance with another aspect of the present invention a system for data usage management in an electronic device is provided. The system includes a cost estimation unit configured to determine an estimated cost of a download before after and during downloading of data a notification generation unit configured to display notifications and restrict data usage when a threshold is reached a widget configured to graphically represent the data usage and an application data usage unit configured to determine application data usage.

The embodiments of the present invention and the various features and advantageous details thereof are explained more fully with reference to the accompanying drawings. Descriptions of well known components and processing techniques are omitted so as to not unnecessarily obscure the embodiments herein. The examples used herein are intended merely to facilitate an understanding of ways in which the embodiments herein can be practiced and to further enable those of skill in the art to practice the embodiments herein. Accordingly the examples should not be construed as limiting the scope of the embodiments herein.

Referring to a system for monitoring a mobile communication device is provided. The system provides enhanced control over overall cost and consumption of data in a mobile device by providing an estimate of the cost of a download before after and during downloading of the data.

The system includes a Data Usage Management System DUMS unit a user input unit output unit a network interface unit and a handover unit wherein all the units are bidirectional units and are connected to a common system bus. The system gives output based on the input given by user.

The handover unit is for switching data services in multi SIM phones from roaming SIM to non roaming SIM. A roaming SIM is a SIM which is outside of the home network i.e. a SIM whose connectivity service is extended in a location that is different from the home location that is the location where the service was registered. On the other hand the home SIM or non roaming SIM is a SIM whose connectivity service is inside the home network or inside a particular boundary where the SIM is registered. Data handover is the process of transferring the data services from one SIM to another SIM i.e. from a roaming SIM to a home SIM or non roaming SIM.

The handover unit of the system of present invention further includes means for reading SIM data preference setting means for checking current data subscription of the SIM means for switching the data services to other SIM and means for enabling data services.

Referring to a Data Usage Management System unit of the system is provided. The system includes a cost estimation unit a size calculator an application data usage unit a notification generation unit a widget controller a cost database a time period estimator a DUMS memory a display controller interface and a user input interface .

The cost estimation unit is for cost estimation of the download before after and during downloading of the data. The cost estimation unit further includes means for calculating the size of a selected file means for reading cost details from settings means for estimating cost and a display unit for viewing the estimated cost.

The notification generation unit is for displaying notifications and restricting data usage when a threshold is reached. The notification generation unit further includes means for calculating data usage threshold means for checking data usage by reading consumed data usage details from a radio and or network interface means for showing notifications and means for restricting data usage based on a threshold.

The display controller interface is for displaying a widget or an application and data displays for graphical representation of consumed data 

According to an embodiment of the present invention a system and method provides a user with an option to track and control individual applications so that they do not consume data in the background and during but not limited to roaming. The system and method of the present invention gives users a reminder to switch to a Home network for data usage.

The system of the present invention shows the details of data usage in a currency set by the user. The user is shown the estimated cost and if the user thinks the cost is too high he can schedule the download for a later time when another type of data communication channel such as but not limited to Wi Fi Bluetooth etc is available. The user may choose to share this download cost with people nearby using a separate Data Pooling application. The user may also decide to add this file to a wish list and download it later.

According to an embodiment of the present invention the user is given notification when the user is about to exceed a data limit. This will help the user to control the usage such as on a daily and monthly basis. The user can set the threshold for the notification generation. A widget on the home screen notifies the user by changing color such as but not limited to by becoming red when the threshold is reached. This keeps the user conscious of his data usage. The notification can be in other forms also such as but not limited to a vibration alert a popup a warning etc.

According to an embodiment of the present invention an option is provided to restrict certain applications from using mobile data during but not limited to roaming. This helps in saving data cost incurred by applications while roaming.

In multi SIM phones the system and the method of the present invention gives users the reminder to switch to a Home network for data usage. This applies when the user has multiple SIMs at least one in home network and other roaming networks and when the user is using the roaming network for data usage. It enables the user to restrict background data for certain applications. This ensures that application do not consume heavy data without the user s acknowledgement.

The system and the method of the present invention track and control individual applications so that they do not consume data in the background and also during roaming. It helps in tracking download expenses in the currency set by the user such as but not limited to local currency currency of foreign country etc. A widget gives easy visualization of data consumed. It also gives a quick access to control data.

The present invention shows the usage details in a widget for easy monitoring and control. It enables the user to set his her data plan and customize applications accordingly.

The system and the method of the present invention helps the user to save costs via easy data management by the use of data usage meters such as but not limited to a surfing meter a data download meter a data estimation meter etc.

Referring to the system provides data cost set by user per KB or per MB or in any other data unit. When the user downloads any content the data usage cost will be calculated as Equation 1 Estimated Cost File Size KBs or MBs or GBs data rate per KB MB GB 1 

Without departing from the scope of the invention this estimated cost can be further rounded off to two decimal digits for the convenience of user.

Viewing the estimated cost involves selecting a file to download calculating the file size in KBs or per MBs or in any other data unit by a browser reading data cost details from a user defined setting and calculating the estimated cost for downloading.

Referring to a screen is shown for setting the data usage notification such as daily monthly weekly quarterly etc. by the user.

Based on a monthly limit a daily limit will be calculated. And then the user can set a daily data usage notification. When the daily data usage limit is crossed notification will be displayed to the user. The daily data usage notification will protect the user from the cost of excess downloads in case of prorated data usage calculation.

A sample calculation for daily notifications is shown in Equation 2 Daily Data Usage Limit Monthly Limit 30 Set daily notification

The same calculation can be implemented for setting notifications for other time periods such as but not limited to daily monthly quarterly and annually without departing from the scope of the invention.

Implementing the data usage notifications includes setting data usage limits and notifications reading consumed data usage details from radio and or network interface and calling a framework Application Programming Interface API to notify the user if the data usage exceeds the threshold set by the user.

Referring to a widget which is a graphical representation of the data consumed is shown. The widget is represented by a circle where the entire circle represents the data limit. A green area of the widget represents the data consumed within a data warning range. Once the warning range is reached the green area is replaced by a red area and a notification is generated. The colors mentioned may be different as per the user s choice or may be system defined without departing from the scope of the invention.

Once the entire area has been filled with red it indicates that the data limit has been reached and a notification is generated from the network layer.

The widget periodically checks for the data consumed on A network such as but not limited to a cellular network a Wi Fi network a Bluetooth network etc. for a given data cycle and compares the consumed data with data warning values or a threshold. The widget applies a red circle at a calculated index if the consumed value exceeds the data warning value and applies a green circle at a calculated index if the consumed value does not exceed the data warning value.

The widget periodically checks for the data consumed on the network for a given data cycle. The widget then calculates the index 0 to 15 for the appropriate circles from the list of either green circles or red circles.

The widget then compares the consumed data with the data warning values. If the consumed data exceeds the data warning values the red circle is applied at the calculated index otherwise the green circle is applied.

Referring to in step the widget checks the data plan limit. In step the current data usage is checked. In step depending upon the result the red or green circle is displayed as the widget. If the data usage exceeds the data plan the red circle is displayed. If the data usage does not exceed the data plan the green circle is displayed.

Referring to a data handover on roaming in a multi SIM phone is shown. If one SIM is moved from a home area to a roaming area data services will be switched to another home SIM provided a roaming status setting KEY DATA ROAMING STATUS is set to true. If one SIM is already in roaming and the user then checks a setting for the home SIM data preference the data services will be switched to another home SIM. This means that if the setting was turned on after moving to a roaming area then the functionality would work.

As shown in in step the SIM data preference setting N is read. In step the SIM data preference setting N is compared with the roaming status setting. If the SIM data preference setting is set to roaming then in step the current data subscription of the SIM is checked. In step if the current data subscription SIM is a roaming SIM the data services will be switched to another SIM i.e. to home network SIM. If the SIM data preference setting in step is not roaming or if the current data subscription SIM is a home SIM then in step data services are enabled.

The application data usage unit determines application data usage when an application launches. In this case the framework will broadcast the launched application package detail and the data usage detail will be obtained based on an application ID appID from a Radio Interface Layer RIL and the user will be notified of the usage.

The system of the present invention will identify the application launched by using its application ID appID . The system then queries the INetworkStatsSession class provided by the network layer for the data consumed by the all of the applications for a given cycle which is given in the form of NetworkStats INetworkStatsSession.getSummaryForAllUid NetworkTemplate startDate endDate boolean . The system then iterates the NetworkStat for each NetworkStats.Entry and compares the appID for the desired application. Once the desired NetworkStats.Entry is found the data consumed is calculated for the given application using Equation 3 . NetworkStats.Entry.rxBytes NetworkStats.Entry txBytes 3 

Based on the calculation a notification with the data consumed by a currently launched application may or may not be generated in the Notification Panel.

Without departing from the scope of the invention the network could be a LAN a WAN a MAN a MANET Wi Fi a Bluetooth a peer to peer or the like which are known in the art.

Referring to the cost estimation unit is provided wherein means for calculating the size of a selected file means for reading cost details from settings means for estimating cost and a display unit for viewing the estimated cost are all connected to a Cost Estimation Unit CEU controller .

Referring to the notification generation unit is provided wherein means for calculating data usage threshold means for checking data usage means for showing notifications and means for restricting data usage based on a threshold are all connected to a Notification Generation NG controller .

Referring to the handover unit is provided wherein means for reading SIM data preference setting means for checking current data subscription of the SIM means for switching to another SIM and means for enabling data services are all connected to a Handover Unit HU controller .

According to an embodiment of the present invention the complete flow can be divided into several steps 

Set a data plan Data to be used in a month in Kilobyte Megabytes or Giga Bytes or any other data unit. Set the cost of this data and define the currency. Set a desired threshold for showing notification. Select applications for which background data should always be restricted or can be provided based on user preferences. Select applications to restrict background data on roaming or can be provided based on user preferences.

Enable data usage meter widget. The widget can be placed on a home screen however it is not mandatory.

A user will be able to see a notification whenever he is about to download any file. The notification will display the estimated cost of download based on the plan set by user during configuration . The user can decide to download the file right away or decide to schedule it to be downloaded later when another type of data communication channel such as but not limited to Wi Fi Bluetooth etc. is available. If the user selects the download later option the file will be downloaded automatically when another type of data communication channel such as but not limited to Wi Fi Bluetooth etc. is connected. The user will receive a notification when the threshold value for data has been reached for a time period such as in a day or in a month. Applications for which background data has been restricted will not be consuming any data when running in background. When the user is in roaming networks applications restricted for roaming will not access any data in the roaming network.

According to embodiments of the present invention the estimation of cost is shown before the cost is actually incurred to help the user in making an informed decision. Knowing the details of data consumed in the currency set by the user helps in a better understanding of the costs incurred. There is an option to schedule the download on another type of data communication channel such as but not limited to Wi Fi Bluetooth etc. to save costs. Constant monitoring of data helps in making the best of the data available. Warning notifications may be customized as per the user s choice or could be system default as provided with the widget. Data costs are reduced by restricting data usage of certain applications running in the background and in roaming.

The method of an embodiment of the present invention helps in tracking download expenses in the currency set by user. The method shows the usage details in a widget or an application and data is displayed for easy monitoring and control. The method enables a user to set his her data plan and customize an application accordingly. The data usage meter widget gives easy visualization of data consumed. The method also gives a quick access to control data consumption.

According to an embodiment of the present invention an estimate of the cost of download before after and during downloading of the data is shown. A user can check the estimated cost for download and decide to download now or later. User can also chose to select whether to download content from cellular data communication network or by another type of data network as per the estimated cost. It always shows the details of data usage in the currency set by user and it provides an option to restrict certain applications from using mobile data during but not limited to roaming. This helps in saving data cost incurred by applications in roaming.

In multi SIM phones the method of the present invention gives users a reminder or notification to switch to a home network for data usage. This applies when the user has multiple SIMs one in the home network and others in the roaming network and when the user is using the roaming network for data usage.

The system of the present invention enables the user to restrict background data for certain applications. This ensures that application do not consume heavy data without the user s acknowledgement.

While the foregoing written description of the invention enables one of ordinary skill to make and use what is considered presently to be the best mode thereof those of ordinary skill will understand and appreciate the existence of variations combinations and equivalents of the specific embodiments methods and details herein.

While the various embodiments of the present invention have been described and illustrated it will be appreciated that various changes can be made therein without departing from the scope of the invention as defined by the appended claims and their equivalents.

