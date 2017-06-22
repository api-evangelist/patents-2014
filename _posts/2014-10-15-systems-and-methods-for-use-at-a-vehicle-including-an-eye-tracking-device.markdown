---

title: Systems and methods for use at a vehicle including an eye tracking device
abstract: Systems and methods for a vehicle including an eye tracking device. The systems and methods use input from the eye tracking device. The systems and methods are configured to communicate with a driver based on input from the eye tracking device. For example, the systems and methods are configured to generate indicators on a display based on input from the eye tracking device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09530065&OS=09530065&RS=09530065
owner: GM Global Technology Operations LLC
number: 09530065
owner_city: Detroit
owner_country: US
publication_date: 20141015
---
The present disclosure relates generally to systems and methods for use at a vehicle including an eye tracking device.

Conventional in vehicle user interfaces and instrument clusters include complex displays having multiple visual outputs presented thereon. These displays require a relatively high amount of driver attention and in some cases the use of hands to interact with the user interfaces. Such displays could distract a driver resulting in less safe driving conditions.

According to an exemplary embodiment a method includes displaying an indicator on a display of a vehicle. The indicator includes an indicator area and is associated with a vehicle system. The method further includes comparing sensor data to a threshold. The sensor data is associated with the vehicle system. The threshold represents a separation between a first state or operation e.g. a normal state of the vehicle system and a second state or operation e.g. a critical state of the vehicle system. The method further includes comparing gaze location data to the indicator area and reducing a prominence of the indicator if the sensor data is on a normal state side of the threshold and the gaze location data is found in the indicator area.

According to an exemplary embodiment a method includes displaying an indicator on a display of a vehicle. The indicator includes an indicator area and is associated with a vehicle system. The method further includes comparing sensor data to a threshold. The sensor data is associated with the vehicle system. The threshold represents a separation between a normal state of the vehicle system and a critical state of the vehicle system. The method further includes comparing gaze location data to the indicator area and increasing a prominence of the indicator if sensor data is on a critical state side of the threshold and gaze location data is not found in the indicator area.

According to an exemplary embodiment a method includes receiving information to be communicated to a driver and displaying a notification indicator on a display. The notification indicator includes an indicator area. The method further includes comparing gaze location data to the indicator area and communicating the information if the gaze location data is found in the indicator area.

According to an exemplary embodiment a method includes displaying a first indicator on a vehicle display. The first indicator includes a first indicator area. The method further includes calculating a first gaze frequency associated with the first indicator. The first gaze frequency is calculated over a first period of time and is based on one of a number of times a gaze location moves into the first indicator area and a time a gaze location spends in the first indicator area. The method further includes determining a prominence of the first indicator based on the first gaze frequency.

According to an exemplary embodiment the method further includes displaying a second indicator on a vehicle display. The second indicator includes a second indicator area. The method further includes calculating a second gaze frequency associated with the second indicator. The second gaze frequency is calculated over a second period of time and is based on one of a number of times a gaze location moves into the second indicator area and a time a gaze location spends in the second indicator area. The method further includes determining the prominence of the second indicator based on the second gaze frequency. Positions on the display are ordered based on prominence. Determining the prominence includes determining the position of the first indicator and the second indicator based on an order of the first gaze frequency and the second gaze frequency.

According to an exemplary embodiment a method includes displaying each of a first indicator and a second indicator on a display of a vehicle. The first indicator includes a first indicator area and the second indicator includes a second indicator area. A first distance separates the first indicator and the second indicator. The method further includes analyzing gaze location data on the display and decreasing the first distance if a gaze pattern between the first indicator and the second indicator is identified. The gaze pattern is based on a number of transitions between the first indicator and the second indicator.

According to an exemplary embodiment a method includes accessing a set of default parameter values and comparing the set of default parameter values to output data from a sensor. The sensor is associated with a vehicle system of a vehicle. The method further includes communicating if the output data matches one of the set of default parameter values default information associated with the one of the set of default parameter values registering a gaze associated with the vehicle system if gaze location data is found at a location associated with the vehicle system determining at a time when the gaze is registered an auxiliary parameter generating auxiliary information based on the auxiliary parameter and communicating the auxiliary information.

According to an exemplary embodiment a method includes registering a gaze associated with a vehicle system if gaze location data is found at a location associated with the vehicle system and communicating at a time when the gaze is registered information associated with the vehicle system.

The method further includes determining a context based on sensor data and determining the information associated with the vehicle system based on the context.

As required detailed embodiments of the present disclosure are disclosed herein. The disclosed embodiments are merely examples that may be embodied in various and alternative forms and combinations thereof. As used herein for example exemplary and similar terms refer expansively to embodiments that serve as an illustration specimen model or pattern.

While the present technology is described primarily herein in connection with automobiles the technology is not limited to automobiles. The concepts can be used in a wide variety of applications such as in connection with aircraft marine craft and other vehicles.

According to an embodiment illustrated in a vehicle includes vehicle systems controls for the vehicle systems sensors a computing device and displays . Certain of the sensors are configured to output data reflecting measurements of parameters of the vehicle systems . Certain of the sensors are configured to output data reflecting measurements of an environment of the vehicle .

Vehicle systems are also configured to output data or otherwise provide another source of information. For example the output data is generated by the vehicle system . Vehicle systems that generate output data include electronic control units.

Also information e.g. information from vehicle system is available on a controller area network CAN Bus. For example whether or not the automatic cruise control ACC is engaged the CAN bus includes information about whether the radio is on and at what volume. The CAN bus also includes personalization information that is available to all vehicle systems that indicates the identity of the driver and their preferences.

The computing device is configured to receive the output data . The computing device is configured to store the output data as information or to generate the information based on the output data .

The computing device is further configured to communicate with a driver via a vehicle user interface such as the displays an audio e.g. speaker microphone system or a haptic system e.g. in the steering wheel . For example to communicate the information visually the computing device is configured to generate and position indicators on the displays or generate and position text on the displays . To communicate the information audibly the computing device is configured to generate an audio signal based on the information and play the audio file through the audio system .

The display is a visual output. For example the display can be a two dimensional output or a three dimensional output. Two dimensional output includes an electronic output on a screen or a projection onto a surface. Three dimensional outputs include holographic projections.

For purposes of teaching a device with a display is described in detail below as including an electronic screen on which digital output is displayed. For example the indicators are digital images that are positioned on the display by the computing device .

Referring to the display includes display areas at positions . Here each of the indicators is associated with one of the display areas of the display . Each of the indicators includes an indicator area . For example the indicator area is less than or equal to the associated display area and is scaled as described in further detail below. Alternatively described the indicators are targets and the indicator areas are target regions.

The display can be that of an instrument panel a human machine interface HMI an entertainment or infotainment system e.g. radio video playing systems a navigation system a system that connects to auxiliary devices e.g. bluetooth devices cellular phones or any other system brought into the vehicle here information is presented for example by a smartphone projection or smartphone connection or the auxiliary device itself a head up display HUD e.g. that is projected onto a windshield of the vehicle other devices for providing visual communication and the like.

Referring to for purposes of teaching the display is positioned in a dashboard of the vehicle behind the steering wheel . In some embodiments a display includes one or more screens projections and the like. For example a display can include a first display behind the steering wheel a second display e.g. a HUD projected onto the windshield of the vehicle and a third display in the center of the dashboard e.g. center console . Although a display can include physically separate components the components can be treated as a single display. Otherwise the components can operate as individual displays or different displays can be formed from different components.

In certain embodiments the indicators represent a state or condition of the vehicle systems or environment . Commonly indicators include gauges such as a speedometer tachometer odometer and fuel gauge. Other indicators include a gearshift position a seat belt warning light a parking brake engagement warning light and an engine malfunction light low fuel low oil pressure low tire pressure and faults in the airbag SRS system.

Other indicators can relate to vehicle systems such as heating systems air conditioning systems braking systems acceleration systems entertainment or infotainment systems e.g. radio video playing systems navigation systems mirrors e.g. mirror adjustment systems seats e.g. seat adjustment systems window control systems doors e.g. door lock control systems collision avoidance systems traction control systems a horn windshield wiper systems belts and hoses emission system engine engine cooling system exhaust system lighting and wipers starting charging and batteries steering and suspension transmission sensors switches HVAC cameras communication devices e.g. OnStar devices and other wireless communication devices systems that connect to auxiliary devices e.g. Bluetooth devices cellular phones cluster center stack head up display HUD speech gestures sound and the like.

Continuing with the vehicle further includes a gaze detection device that is configured to output gaze location data reflecting a gaze location over time. For example the gaze location is the location of a gaze of a driver on the display .

For example the gaze detection device detects a gaze location based on the position of the user s eye the position of the display and a direction of the eye. Here the gaze location is where a vector intersecting the position of the user s eye and having the angle of the direction of the user s eye intersects the plane of the surface of the display . The position of the user s eye depends on for example a head pose.

According to an exemplary embodiment the gaze detection device includes a camera that is configured to capture an image of at least a portion of a head e.g. face or eyes of the user and to generate a signal representing the image. The gaze detection device also includes a source of radiant energy such as an infra red light emitting diode to illuminate at least a portion of the head of the user. In certain embodiments more than one camera is used for eye tracking to improve the accuracy of the gaze detection device .

The gaze detection device is configured to analyze the images captured by the camera to determine the position of the eye and the gaze angle. For example the gaze detection device includes a computing device similar to the computing device described below and an analysis application for processing the images.

Alternatively the gaze detection device provides the images to the computing device and the computing device includes an analysis application to analyze the images.

For purposes of teaching gaze location data described below is illustrated as gaze locations measured over time x axis . Gaze location data moves along a y axis to illustrate the movement of the gaze location between various locations in the vehicle e.g. locations on the display . Areas that include a number of locations in the vehicle are indicated by a range on the y axis.

In the figures time periods of fixation at a certain location are indicated by a flat line. Time periods of transition between locations in different areas are indicated by a sloped line. Time periods of saccades between different locations in the same area are indicated by sloped line that remains in an area.

The computing device includes a processor for controlling and or processing data input output data ports and a memory . The processor could be multiple processors which could include distributed processors or parallel processors in a single machine or multiple machines. The processor could include virtual processor s . The processor could include a state machine application specific integrated circuit ASIC programmable gate array PGA including a Field PGA or state machine. When a processor executes instructions to perform operations this could include the processor performing the operations directly and or facilitating directing or cooperating with another device or component to perform the operations.

The computing device can include a variety of computer readable media including volatile media non volatile media removable media and non removable media. The term computer readable media and variants thereof as used in the specification and claims includes storage media. Storage media includes volatile and or non volatile removable and or non removable media such as for example RAM ROM EEPROM flash memory or other memory technology CDROM DVD or other optical disk storage magnetic tape magnetic disk storage or other magnetic storage devices or any other medium that is configured to be used to store information that can be accessed by the computing device .

While the memory is illustrated as residing proximate the processor it should be understood that at least a portion of the memory can be a remotely accessed storage system for example a server on a communication network e.g. a remote server a remote hard disk drive a removable storage medium combinations thereof and the like. Thus any of the data applications and or software described below can be stored within the memory and or accessed via network connections to other data processing systems not shown that may include a local area network LAN a metropolitan area network MAN or a wide area network WAN for example.

The memory includes several categories of software and data used in the computing device including applications a database an operating system and input output device drivers .

As will be appreciated by those skilled in the art the operating system may be any operating system for use with a data processing system. The input output device drivers may include various routines accessed through the operating system by the applications to communicate with devices and certain memory components. The applications can be stored in the memory and or in a firmware not shown as executable instructions and can be executed by the processor .

The applications include various programs that when executed by the processor implement the various features of the computing device including declutter applications system notification applications delayed notification applications driver request applications arrangement applications relationship applications information adjustment applications vehicle system information applications and driver context information applications each of which is described in further detail below. The applications are stored in the memory and are configured to be executed by the processor .

The applications may be applied to data stored in the database such as that of signals received by the sensors e.g. received via the input output data ports along with data received over a wireless data connection . The database represents the static and dynamic data used by the applications the operating system the input output device drivers and other software programs that may reside in the memory .

It should be understood that and the description above are intended to provide a brief general description of a suitable environment in which the various aspects of some embodiments of the present disclosure can be implemented. The terminology computer readable media computer readable storage device and variants thereof as used in the specification and claims can include storage media. Storage media can include volatile and or non volatile removable and or non removable media such as for example RAM ROM EEPROM flash memory or other memory technology CDROM DVD or other optical disk storage magnetic tape magnetic disk storage or other magnetic storage devices or any other medium excluding propagating signals that can be used to store information that can be accessed by the device shown in .

While the description refers to computer readable instructions embodiments of the present disclosure also can be implemented in combination with other program modules and or as a combination of hardware and software in addition to or instead of computer readable instructions.

While the description includes a general context of computer executable instructions the present disclosure can also be implemented in combination with other program modules and or as a combination of hardware and software. The term application or variants thereof is used expansively herein to include routines program modules programs components data structures algorithms and the like. Applications can be implemented on various system configurations including single processor or multiprocessor systems minicomputers mainframe computers personal computers hand held computing devices microprocessor based programmable consumer electronics combinations thereof and the like.

It should be understood that the steps of methods are not necessarily presented in any particular order and that performance of some or all the steps in an alternative order is possible and is contemplated. The steps have been presented in the demonstrated order for ease of description and illustration. Steps can be added omitted and or performed simultaneously without departing from the scope of the appended claims.

It should also be understood that the illustrated methods can be ended at any time. In certain embodiments some or all steps of this process and or substantially equivalent steps are performed by execution of computer readable instructions stored or included on a computer readable medium such as the memory of the computing device described above for example.

Referring to the declutter application includes computer readable instructions that when executed by the processor cause the processor to perform a declutter method .

At a block the processor displays e.g. facilitates display of an indicator as shown in and analyzes sensor data e.g. horizontal x axis is time from the sensor sensor shown in and sensor data shown in .

Continuing with if the sensor data is on a normal operation side of e.g. above or below a threshold at a block the processor analyzes gaze location data e.g. gaze locations measured over time movement between a gaze location outside the indicator area to a gaze location inside the indicator area is represented by arrow . For example the threshold represents separation between a first operation e.g. a normal operation and a second operation e.g. a critical operation of a respective one of the vehicle systems .

Referring again to if the gaze location data includes a gaze location in the indicator area of the indicator that is associated with the vehicle system of the sensor at a block the processor displays the indicator such that the prominence of the indicator is reduced. Reducing the prominence includes reducing size brightness color font type of indicator moving to a less prominent position e.g. away from the center of the display combinations thereof and the like.

As an example referring to the processor displays a fuel level indicator and analyzes fuel level data from the fuel level sensor . If the fuel level data shows the fuel level is above a fuel level threshold the processor analyzes gaze location data. If the fuel level data is greater than the fuel level threshold the fuel level data is acceptable and the information is not immediately important once the driver is aware of the fuel level. If the gaze location data includes a gaze location in an indicator area of the fuel level indicator the driver has noticed the fuel level and the processor reduces the prominence of the fuel level indicator by changing the type of graphic used and or reducing the size of the graphic.

Other examples include the method where the engine temperature data is measured by an engine temperature sensor and compared to an engine temperature threshold e.g. the engine temperature threshold defines a yellow zone the method where air pressure data is measured by an air pressure sensor in one of the wheels and compared to an air pressure threshold e.g. the air pressure threshold is a pressure that is low but not critical such as PSI for a tire whose normal is 32 PSI and the method where oil life data is measured by an oil life sensor and compared to an oil life threshold e.g. the oil life exceeds meaning that an oil change is needed . In these examples engine temperature data below the engine temperature threshold is normal air pressure data above the air pressure threshold is normal and oil life data below the oil life threshold is normal.

Referring to the system notification application includes computer readable instructions that when executed by the processor cause the processor to perform the system notification method .

At a block the processor displays an indicator on the display as shown in and analyzes data e.g. horizontal x axis is time from a sensor as shown in .

Continuing with if the sensor data is on a critical operation side of above or below a threshold at a block the processor analyzes gaze location data e.g. gaze locations measured over time movement between a gaze location outside the indicator area to a gaze location inside the indicator area is represented by arrow as shown in . For example the threshold represents operation of a vehicle system below which a warning is to occur.

Continuing with at a block if the gaze location data does not include a gaze location in the indicator area of the indicator the processor increases the prominence of the indicator . For example the prominence of the indicator is increased e.g. at a rate or for a time until gaze location data includes a gaze location in the indicator area of the indicator which is associated with the vehicle system of the sensor . Increasing the prominence includes increasing size brightness type of indicator moving to a more prominent position e.g. toward the center of the display combinations thereof and the like.

As an example referring to the processor displays a fuel level indicator and analyzes data from the fuel level sensor . If the fuel level sensor data shows the fuel level is below a fuel level threshold the fuel level is not acceptable and the driver is to be notified. The processor analyzes gaze location data. If the gaze location data does not include a gaze location in an indicator area of the fuel level indicator the driver is unaware of the fuel level and the processor increases the prominence of the fuel level indicator by increasing the size of the graphic. Once the gaze location data includes a gaze location in an indicator area of the fuel level indicator the driver has noticed the fuel level.

Other examples include the method where the engine temperature data is measured by an engine temperature sensor and compared to an engine temperature threshold e.g. the engine temperature threshold defines a red zone the method where air pressure data is measured by an air pressure sensor in one of the wheels and compared to an air pressure threshold e.g. the air pressure threshold is a pressure that is critical and the method where oil life data is measured by an oil life sensor and compared to an oil life threshold e.g. the oil life exceeds meaning that an oil change is overdue . In these examples engine temperature data above the engine temperature threshold is critical air pressure data below the air pressure threshold is critical and oil life data above the oil life threshold is critical.

As another example road position data is compared to a lane e.g. threshold and a lane departure warning is communicated to the driver with haptic feedback until the driver looks at a warning indicator or indicator of a lane departure system.

Referring to the delayed notification application includes computer readable instructions that when executed by the processor cause the processor to perform a delayed notification method .

Referring to at a block the processor receives information or generates the information . The processor then generates and displays an indicator that represents an awaiting notification and analyzes gaze location data .

At a block if the gaze location data e.g. gaze locations measured over time movement between a gaze location outside the indicator area to a gaze location inside the indicator area is represented by arrow includes a gaze location in an indicator area of the indicator referring to the processor displays the information e.g. replaces the indicator with the information . In alternative embodiments the gaze location is in the indicator area for a certain amount of time before the information is displayed.

The indicator may be generated and displayed based on data from a sensor . For example referring to at the block the processor generates and displays an indicator that represents an awaiting notification only if sensor data e.g. horizontal x axis is time is below a threshold . Alternatively or additionally at the block the processor displays the information only if sensor data is below the threshold .

Here the threshold represents operation of a vehicle system below which or above which a driver can receive the information without substantially distracting or disturbing the driver. For example the threshold may be a speed an amount of traffic a time to next driving direction etc.

As an example referring to the processor receives a message generates and displays an indicator e.g. an envelope symbol on the display and analyzes gaze location data . If the gaze location data includes a gaze location in an indicator area of the indicator the processor displays the message on the display . In certain embodiments for example the processor only displays the indicator if the speed is measured by a speed sensor to be below ten miles per hour.

Referring to the driver request application includes computer readable instructions that when executed by the processor cause the processor to perform the driver request method .

At a block referring to a gaze or glance frequency is calculated for each of the indicators . The gaze frequency for an indicator is the number of times a gaze location moves into the indicator area e.g. transitions T of the indicator over a time period . In alternative embodiments the gaze frequency is time a gaze location spends in the indicator area e.g. dwell time equals sum of all fixations and saccades between transitions or shifts of gaze to other target areas over the time period . Glance duration can be defined as the time from the moment at which the direction of gaze moves toward a target to the moment it moves away from it. A single glance duration may be referred to as a glance.

The gaze frequency can also be defined as the number of glances to a target within a pre defined sample time period or during a pre defined task where each glance is separated by at least one glance to a different target.

At a block referring to the prominence of each indicator is increased or decreased based on the respective calculated gaze frequency of the indicator . For example a prominence of each indicator is associated with an average gaze frequency . If the calculated gaze frequency is above the average gaze frequency the processor increases the prominence of the indicator . If the calculated gaze frequency is below the average gaze frequency the processor decreases the prominence of the indicator .

In certain embodiments average gaze frequency is the gaze frequency that is calculated over a longer time period.

Referring to the arrangement application includes computer readable instructions that when executed by the processor cause the processor to perform the arrangement method .

According to the arrangement method indicators with greater average gaze frequency are displayed at more prominent positions that have and displayed towards the center of the display or at the most prominent position.

Referring to at a block the processor displays the indicators based on previously calculated average gaze frequency e.g. long term average and analyzes gaze location data . Referring momentarily to for each indicator the processor calculates a current gaze frequency e.g. the number of gaze locations in the indicator area of the indicator or the time that the gaze location is in the indicator area of the indicator over the last one minute and calculates an updated average gaze frequency based on the current gaze frequency .

At a block referring to the processor analyzes the updated average gaze frequencies of the indicators .

At a block referring to the processor arranges the indicators in the display areas at the positions based on the updated average gaze frequencies . For example positions on the display and size ranges at those positions are predefined and ranked by prominence i.e. position and display area .

Generally the indicators with the larger updated average gaze frequencies are arranged in positions with a relatively larger size range e.g. the size of indicator area within display area is determined based on current gaze frequency as described above with respect to method at a more central or easy to find position on the display . Similarly the indicators with the smaller updated average gaze frequencies are arranged in positions with a relatively smaller size range e.g. the size of indicator area within display area is determined based on current gaze frequency as described above with respect to method and a less central position on the display .

Referring to the relationship application includes computer readable instructions that when executed by the processor cause the processor to perform the relationship method .

At a block referring to the processor displays the indicators and analyzes gaze location data e.g. horizontal x axis is time .

At a block referring to a gaze pattern is identified. For example the gaze pattern is identified when a gaze location is found in the indicator area of at least two different ones of the indicators in at least two different time periods . Alternatively a gaze pattern is identified when a number of transitions between two indicators is greater than a threshold number of transitions.

At a block referring to if a gaze pattern is identified the processor decreases a distance between the indicators associated with the gaze pattern or otherwise combines the indicators associated with the gaze pattern .

Referring to the information adjustment application includes computer readable instructions that when executed by the processor cause the processor to perform the information adjustment method . According to the information adjustment method default information is augmented with auxiliary information or otherwise altered based on a gaze of a driver.

The information to be communicated by the computing device may be static e.g. fixed or predetermined content already in memory or may be dynamic e.g. may change over time . Dynamic information includes for example time of day weather and driver state.

The information may be generated and stored to be accessed by the computing device . Alternatively the computing device may generate the information in real time or request that the vehicle system generate the information in real time. For purposes of teaching information is categorized below as default information and auxiliary information.

The memory includes set of default parameter values . Exemplary parameters include location distance and time.

At a block the processor monitors the output data of a sensor or vehicle system . The output data includes values of a parameter associated with the set of default parameter values . The processor compares the output data of the sensor to the set of default parameter values .

When the output data of the sensor matches one of the set of default parameter values e.g. at a block the processor accesses generates or requests a default information based on the matched one of the set of default parameter values e.g. . For example the processor accesses or generates the default information associated with the matched one of the set of default parameter values or requests that the default information is generated by the vehicle system and receives the default information .

At a block the processor communicates the default information to the driver. For example the communication is visual on the display and or audible through the audio system of the vehicle .

At a block the processor analyzes gaze location data e.g. horizontal x axis is time to monitor a gaze location of a driver e.g. . If the gaze location is on the display e.g. HMI for a time that is greater than a threshold time a gaze is registered and the processor generates an auxiliary parameter value at a time the gaze is registered e.g. . Alternatively described the auxiliary parameter value modifies e.g. is added to the set of default parameter values .

Alternatively a gaze is registered if a gaze frequency exceeds a certain threshold. Gaze frequency is the number of times a gaze location is on the display over a time period as described above with respect to gaze frequency .

At a block the processor generates or requests generation of an auxiliary information based on the auxiliary parameter value e.g. .

At a block the auxiliary information is communicated to the driver. For example the auxiliary information is communicated visually on the display and or audibly through the audio system of the vehicle .

In this manner the computing device responds to the gaze location of a driver by increasing the communication of information to the driver. For example the frequency of communication of information is increased by communicating the auxiliary information in addition to the default information .

In certain embodiments a gaze triggers the use in place of the set of default parameters values of a new set of parameter values. The new set of parameter values causes more frequent communication to be provided to the driver as compared to the set of default parameter values . For example the new set of parameter values is a more full set of parameter values or otherwise increases the number of the set of default parameter values .

In certain embodiments if a gaze of a driver is not found in gaze location data during a period of time the absence of a gaze reduces the default communication to the driver. For example the absence of a gaze triggers the use in place of the set of default parameter values of a new set of parameter values. The new set of parameter values causes less frequent communication to be provided to the driver as compared to the set of default parameter values . For example new set of parameter values is a more sparse set of parameters or otherwise reduces the number of the set of default parameter values .

Referring to an example application is now described. Here the information is a direction that is associated with a parameter e.g. locations including locations based on geographical or temporal parameters along a route . The route is generated by the computing device or the vehicle system one or both of which is a navigation system.

For purposes of teaching the parameter is a location. Default location values can be determined in various ways. For example the default location values can be based on relative distance to a turn or other direction along the route or the time to a turn or other direction along the route given the relative distance to the turn and the current speed of the vehicle.

The sensor e.g. of the navigation system is a location sensor the output data of which is the vehicle location .

Referring to the processor monitors the vehicle location and compares the vehicle location to the set of default location values .

Referring to when the vehicle location matches one of the set of default location values the processor generates a default direction based on the matched one of the set of default location values . The processor communicates the default direction to the driver.

Referring to the processor analyzes gaze location data to monitor a gaze from a driver. If a gaze location is on the display for a time that is greater than a threshold time a gaze is registered and the processor generates an auxiliary location value at the time the gaze is registered.

Referring to the processor generates or requests generation of an auxiliary direction based on the auxiliary location value . For example the auxiliary direction is the next turn. Here the turn would have been presented later based on a next one of default location values but is instead presented now because of the auxiliary location value .

Alternatively the auxiliary direction is general information such as I am working properly your next turn will be presented in 10 seconds. Here the next turn is presented in ten seconds when the next one of the set of default parameter values matches the location of the vehicle .

In this manner the computing device responds to the gaze of a driver by increasing the communication of directions to the driver. For example the frequency of communication of directions is increased by communicating the auxiliary direction in addition to the default directions .

One advantage of this technology is that the computing device responds to a driver that is having a new experience and is not calm e.g. as evidenced by a gaze by adjusting the default communication to include more frequent instructions or general messages. For example a new experience is driving a route that a driver has not previously driven. Alternatively if a driver is driving a common route then the lack of gazes reflects the comfort of the driver. In response the computing device includes less frequent instructions e.g. the default directions and or limiting messages to only important alerts e.g. accidents hazards changes in traffic .

Referring to the vehicle system information application includes computer readable instructions that when executed by the processor cause the processor to perform the vehicle system information method . According to the vehicle system information method information associated with a vehicle system is presented when a user gazes for a period of time at a location associated with the vehicle system .

The information to be communicated by the computing device may be static e.g. fixed or predetermined or may be dynamic e.g. may change over time . The information may be generated and stored to be accessed by the computing device . Alternatively the computing device may generate the information in real time or request that the vehicle system generate the information in real time. The location associated with the vehicle system includes the indicator associated with the vehicle system the controls associated with the vehicle system and a designated location in the vehicle e.g. on the dashboard steering wheel or center console .

At a block the processor analyzes gaze location data e.g. horizontal x axis is time to monitor a gaze location of a driver. If the gaze location is at the location associated with a vehicle system for a time that is greater than a threshold time at a block a gaze is registered and at a block the processor communicates the information visually on the display and or audibly through the audio system of the vehicle .

Using an automatic cruise control ACC system as an example of a vehicle system the ACC system is activated when the ACC system is turned on and when a speed is set using the ACC system .

According to one embodiment the location associated with the ACC system is the speedometer and the information includes values on the speedometer including the current speed speed limits and set speed entered by the driver. Alternatively the information includes general information such as I am working properly I am trying to reach your set speed .

According to another embodiment the location associated with the ACC system is a set of controls used to provide input e.g. set speed to the ACC system and the information includes directions on how to use the set of controls to operate the ACC system .

Referring to the driver context information application includes computer readable instructions that when executed by the processor cause the processor to perform the driver context information method . According to the driver context information method information is based on a measurement from the sensor that represents a driver s context and the information is presented when the driver gazes for a period of time at a location associated with a vehicle system .

The information to be communicated by the computing device may be static e.g. fixed or predetermined or may be dynamic e.g. may change over time . The information may be generated and stored to be accessed by the computing device . Alternatively the computing device may generate the information in real time or request that the vehicle system generate the information in real time.

The measurement from the sensor represents the driver s context or is used to identify a context. For example a context includes the driving experience of a driver e.g. novice expert age environment outside the vehicle e.g. weather road conditions environment inside the vehicle e.g. occupancy temperature and the status of the vehicle systems e.g. fuel level . Driver experience can be determined by facial recognition associated with a driver profile that includes an age or experience metric.

At a block the processor analyzes output data from the sensor . At a block the processor identifies or generates a context based on the output data .

At a block the processor identifies or generates context information that is specific to a vehicle system and the context .

Blocks of the driver context information method are similar to blocks of the vehicle system information method and are described with reference to .

At a block the processor analyzes gaze location data to monitor a gaze location of a driver. If the gaze location is at the location associated with a vehicle system for a time that is greater than a threshold time at a block a gaze is registered and at a block the processor communicates the context information associated with the vehicle system i.e. that which is specific to the vehicle system associated with the location . The context information is communicated visually on the display and or audibly through the audio system of the vehicle .

For example the processor analyzes output data from the sensor and based on the output data determines that the driver is a novice . The processor generates or identifies context information for the vehicle systems based on the driver being a novice .

Using the ACC system as an example of a vehicle system a location associated with the ACC system is the dial for the ACC system . When the processor registers a gaze at the dial of the ACC system the processor accesses the context information for the ACC system . For example the context information includes directions for operating the ACC system that would be useful to a novice driver. The processor communicates the context information visually on the display and or audibly through a speaker system of the vehicle .

For example the processor analyzes an output data from the sensor and based on the output data determines an occupancy of the vehicle. The processor generates or identifies context information for the vehicle systems based on the occupancy of the vehicle. Context information includes that which would provide a more comfortable settings to all passengers based on the occupancy .

Using a heating ventilation air conditioning HVAC system as an example of a vehicle system a location associated with the HVAC system is the dial for the HVAC system . When the processor registers a gaze at the dial of the HVAC system the processor accesses the context information for the HVAC system . For example the context information includes directions for operating the back vents of the HVAC system because the occupancy includes passengers in the back seat of the vehicle e.g. the car is fully packed . The processor communicates the context information visually on the display and or audibly through a speaker system of the vehicle .

Various embodiments of the present disclosure are disclosed herein. The disclosed embodiments are merely examples that may be embodied in various and alternative forms and combinations thereof. As used herein for example exemplary and similar terms refer expansively to embodiments that serve as an illustration specimen model or pattern.

Variations modifications and combinations may be made to the above described embodiments without departing from the scope of the claims. All such variations modifications and combinations are included herein by the scope of this disclosure and the following claims.

