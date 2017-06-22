---

title: Service robot and method of operating same
abstract: In accordance with aspects of the present invention, a service robot, such as a robotic cleaner, can be configured to more effectively service an environment. The service robot can include one or more sensors that sense its location, the location of objects, or both, and can also include noise reduction elements. The service robot can determine that it is under a “furnishing” and implement a different servicing pattern.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09603499&OS=09603499&RS=09603499
owner: SEEGRID CORPORATION
number: 09603499
owner_city: Pittsburgh
owner_country: US
publication_date: 20140916
---
This application is a divisional application of U.S. patent application Ser. No. 12 361 441 filed Jan. 28 2009 which claims the benefit of priority under 35 U.S.C. 119 e from provisional application Ser. No. 61 024 011 entitled METHODS FOR OBJECT SURFACE AND FUNCTION SPECIFIC CLEANING FOR ROBOT CLEANERS filed on Jan. 28 2008 from provisional application Ser. No. 61 023 980 entitled METHOD FOR CLEANING UNDERNEATH FURNISHINGS FOR ROBOTIC CLEANER filed on Jan. 28 2008 from provisional application Ser. No. 61 024 001 entitled METHODS FOR IMPROVING ROBOTIC CLEANING VIA GLOBAL LOCATION AWARENESS filed on Jan. 28 2008 from provisional application Ser. No. 61 024 022 entitled METHODS AND APPARATUSES FOR NOISE REDUCTION FOR ROBOTIC CLEANERS filed Jan. 28 2008 from provisional application Ser. No. 61 024 037 entitled METHODS FOR ENVIRONMENTAL SCHEDULE AWARENESS FOR ROBOTS THAT SERVICE A FACILITY filed on Jan. 28 2008 each of which is incorporated herein by reference in its entirety.

The present inventive concepts relate to methods for effectiveness and efficiency of robotic cleaners.

One of the advantages of robotic cleaners is that they can clean in places that are hard or impossible to clean manually. Many types of furnishings found in houses and commercial and industrial buildings provide a small amount of clearance under the furnishing. Examples include shelves couches and beds. These clearance spaces are often too small to clean easily manually yet they are large enough to accumulate dirt and dust.

Previous attempts at providing robotic cleaners that can clean under furnishing have been limited in their flexibility and also in their success. Most current commercial systems employ a cleaning algorithms technique. In this type of system the cleaner moves in a single or a series of random or semi random patterns around the floor. The pattern s are varied as too time or other calculations the robot cleaner performs. However in all cases the goal of the cleaner is to optimize the cleaning of a larger space that happens to include the space under the furnishings.

These systems also have a design such that the robot is able to fit into the very small under furnishing spaces as well as passably clean the more open spaces of a building. The design compromises required to create a robotic cleaner that can both fit into the very small spaces under furnishings and also clean the open expanses of a building are daunting. Therefore the efficiency and effectiveness of such systems is poor. For this reason many systems have given up on this challenge entirely.

Efficiency and effectiveness of robot cleaners is typically low because the robots do not use techniques that make use of global location awareness. That is they are generally unaware of their actual location. Previous service cleaning robots have ignored this problem resulting in sub optimal cleaning. Without a location context the servicing robots are limited in terms of providing a series of tasks within an overall location for example.

Moreover current robot cleaners do not use what they learn as they do their job to improve their work. As an example current robot cleaners will always clean when scheduled even when there is too much activity in the area to be able to clean at the scheduled time resulting in a cleaning failure each time.

Also that very action of servicing e.g. cleaning an environment or facility is a complex activity that can require a large fund of knowledge to perform adequately. Previous cleaning robots as an example have ignored this fund of knowledge problem. Instead they tend to rely on generalized techniques to clean all different surfaces objects or functional areas of a facility.

Additionally some service robots such as robotic vacuums can produce a relatively large amount of noise. Previous attempts at reducing noise in robotic cleaners have relied on traditional techniques that have been used to quiet manual vacuum cleaners. These include but are not limited to covering the working mechanisms with hard plastic shells carefully designing moving parts to reduce noise production and artificially limiting the strength of the cleaning mechanism to reduce the maximum noise levels products.

In accordance with one aspect of the invention provided is a method of performing robotic cleaning. The method includes navigating a cleaning robot through an environment using automatic self control by the robot sensing furnishings in the environment by the robot while navigating and cleaning and avoiding contact with the furnishings based on sensor data acquired during the sensing.

The navigating can include the robot optimizing its migration through the environment based on the sensor data.

The optimizing can include changing a navigation pattern of the cleaning robot from a first pattern to a second pattern.

The sensing can include determining if the robot can fit underneath a furnishing and the navigating can include migrating under the furnishing when the sensing determines that the robot can fit underneath the furnishing.

The sensing can further include using light sensing including differentiating lower light intensity levels under the furnishing from higher light intensity levels in open spaces.

The sensing can further include upward facing height sensing including differentiating a shorter un occluded distance in an upward direction near the furnishing from a longer un occluded distance in open spaces.

The sensing can further include using one or more of differentiating acoustic or electromagnetic qualities of under furnishing spaces from acoustic or electromagnetic qualities of open spaces.

The sensing can further include determining where open spaces are when robotic cleaner is underneath an object.

In accordance with another aspect of the invention provided is a robotic cleaner configured to determine when it is under a furnishing. The robotic cleaner includes a platform supporting a cleaning subsystem a navigation controller coupled to a drive mechanism and configured to navigate the platform through an environment and one or more sensors configured to sense objects in the environment during navigation and cleaning wherein the navigation controller controls the drive mechanism to avoid contact with the objects based on sensor data acquired by the one or more sensors.

The robotic cleaner can have a height of six inches or less and be optimized to fit under furnishings.

The navigation controller can be configured to optimize its migration through the environment based on the sensor data.

The navigation controller can be configured to optimize the migration of the cleaning robot by changing a navigation pattern of the cleaning robot from a first pattern to a second pattern.

The one or more sensors can be configured to determine if the cleaning robot can fit underneath an object and the navigation controller can be configured to enable migration under the object when the one or more sensors determine that the robot can fit underneath the object.

The one or more sensors can include light sensors configured to differentiate lower light intensity levels under the object from higher light intensity levels in open spaces.

The one or more sensors can include upward facing height sensors configured to differentiate a shorter un occluded distance in an upward direction near an object from a longer un occluded distance in open spaces.

The one or more sensors can include one or more of acoustic and electromagnetic sensors configured to differentiate acoustic or electromagnetic qualities of under object spaces from acoustic or electromagnetic qualities of open spaces.

The one or more sensors can be configured to enable to the robotic cleaner to determine where open spaces are when robotic cleaner is underneath an object.

In accordance with another aspect of the invention provided is a method of performing robotic servicing using global location awareness. The method includes storing in memory identifications of a plurality of locations within an environment servicing the locations with a robot and tracking a frequency of service of each location by the robot.

The method can further include servicing high use locations with greater frequency than lower use locations.

The method can further include tracking dirt levels at each location and varying cleaning activity to clean high dirt level locations with increased frequency.

The method can further comprise assigning functional labels to each location and associating locations with specific events for times of the day after which cleaning should be performed in those locations.

In accordance with another aspect of the invention provided is a service robot configured to utilize global location information. The service robot includes a platform supporting a service subsystem a navigation controller coupled to a drive mechanism and configured to navigate the platform through an environment and a data storage system that stores identifications of a plurality of locations within the environment a navigation controller configured to track a frequency of service of each location by the robot.

The navigation controller can be further configured to tailor servicing routes to enable the robotic cleaner to optimally service all locations.

The navigation controller can be further configured to track dirt levels at each location and vary cleaning activity to clean high dirt level locations with increased frequency.

The navigation controller can be further configured to assign functional labels to each location and associate locations with specific events for times of the day after which cleaning should be performed in those locations.

In accordance with aspects of the invention provided is a robotic cleaner and method that allows superior reduction in the noise of robotic cleaners.

The robotic vacuum cleaner can include layers of sound dampening materials that are incorporated into the robot.

The robotic cleaner can include placement of microphones speakers and electronic computation and circuitry to provide for active noise reduction of the sounds of the robotic cleaner.

In accordance with aspects of the present invention provided are a robot and methods that enable the robot to service a facility optimally by making use of an environmental schedule of the facility.

The robot can be configured to automatically and selectively operate in view of an environmental schedule of a facility and to make the schedule.

The robot can be configured to perform a people census whereby through the robot s own sensing or through receiving such information from an external source the robot learns where people are likely and unlikely to be at various times of the day and uses a statistical model of likelihood to work as much as possible when and where people are not present.

The robot can be configured to perform a people census whereby real time data is used to trigger or queue the robot to begin or end work. For instance a sensor recording when the car leaves the garage or when people leave a room can be used to trigger the robot to begin work.

The robot can be configured to analyze a digitized calendar of appointments of people and to form a plan to work when people are scheduled to not be present according to the calendar.

The robot can be configured to predicatively calculate the likelihood of a person returning at any given time so that the robot can stop working before the person arrives.

In accordance with aspects of the present invention provided is a robot and method that allows a robot to clean a facility by providing access to cleaning knowledge that is specific to the surface or object being cleaned or to the area of the facility being cleaned. Methods in accordance therewith can enable the robot to optimally service a facility.

A knowledgebase can be included in the robot whereby when the robot senses a specific type of object surface or area to be cleaned the robot queries an internal knowledgebase for specific cleaning techniques for cleaning the object or surface.

The knowledgebase can be a knowledgebase of techniques identified as able to work well for cleaning such object surface or area.

A library of learned behaviors can be included in the robot whereby when the robot senses a specific type of object surface or area to be cleaned the robot queries an internal library of learned behaviors for specific cleaning techniques for cleaning the object or surface.

The library can be a library of behaviors that have worked well in the past for cleaning such object surface or area.

A remote knowledgebase can be provided whereby when the robot senses a specific type of object surface or area to be cleaned it queries a remote knowledgebase or bases for specific cleaning techniques for cleaning the object or surface to be cleaned.

The remote knowledge base could be created and or provided by trusted sources such as the manufacturers of the artifacts to be cleaned.

A remote library of learned behaviors could be provided whereby when the robot senses a specific type of object surface or area to be cleaned it queries an remote library of learned behaviors for specific cleaning techniques for cleaning the object or surface to be cleaned.

The remote library can be a library to behaviors that have worked well in the past for cleaning such object surface or area.

Hereinafter aspects of the present invention will be described by explaining illustrative embodiments in accordance therewith with reference to the attached drawings. While describing these embodiments detailed descriptions of well known items functions or configurations are typically omitted for conciseness.

It will be understood that although the terms first second etc. are be used herein to describe various elements these elements should not be limited by these terms. These terms are used to distinguish one element from another but not to imply a required sequence of elements. For example a first element can be termed a second element and similarly a second element can be termed a first element without departing from the scope of the present invention. As used herein the term and or includes any and all combinations of one or more of the associated listed items.

It will be understood that when an element is referred to as being on or connected or coupled to another element it can be directly on or connected or coupled to the other element or intervening elements can be present. In contrast when an element is referred to as being directly on or directly connected or directly coupled to another element there are no intervening elements present. Other words used to describe the relationship between elements should be interpreted in a like fashion e.g. between versus directly between adjacent versus directly adjacent etc. .

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the invention. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises comprising includes and or including when used herein specify the presence of stated features steps operations elements and or components but do not preclude the presence or addition of one or more other features steps operations elements components and or groups thereof.

Spatially relative terms such as beneath below lower above upper and the like may be used to describe an element and or feature s relationship to another element s and or feature s as for example illustrated in the figures. It will be understood that the spatially relative terms are intended to encompass different orientations of the device in use and or operation in addition to the orientation depicted in the figures. For example if the device in the figures is turned over elements described as below and or beneath other elements or features would then be oriented above the other elements or features. The device may be otherwise oriented e.g. rotated 90 degrees or at other orientations and the spatially relative descriptors used herein interpreted accordingly.

In this embodiment the service robot includes a platform supporting a servicing subsystem and a navigation controller coupled to a drive mechanism not shown and configured to navigate the platform through an environment. The service robot also includes one or more sensors as shown in . Sensor data acquired from the sensor s can be stored in a storage media e.g. a hard drive random access memory read only memory or some combination thereof. Other data and program modules can also be stored in storage media . The program modules can be executable by at least one processor to implement methods or portions thereof described herein. Functional modules need not be implemented in executable program code however. One or more functional modules could additionally or alternatively be implemented in hardware firmware or both as examples.

The storage media can also include maps of the environment or other information useful or necessary for migrating the service robot through the environment. In various embodiments the service robot could also build update or both maps of the environment. Such map building and navigation could be done as described in U.S. Pat. No. 7 446 766 entitled Multidimensional Grids and Systems and Methods for Applying Same and or U.S. patent application Ser. No. 12 263 983 filed Nov. 3 2008 entitled Multidimensional Grids and Systems and Methods for Applying Same. The storage media can in various embodiments be used to store robot location information determined using the sensor data.

In various embodiments the navigation controller can be configured to control the drive mechanism to avoid contact with furnishing e.g. object in the environment based on sensor data acquired by the one or more sensors.

In various embodiments the service robot can also include a communications module which could enable wired or wireless communications with a control system other robots or other wireless devices e.g. personal digital assistant cell phone wireless laptop etc. .

In various embodiments e.g. where the service robot is a robotic cleaner the servicing subsystem can include a dirt detector. The dirt detector can be used to track the amount of dirt taken in at a location. This information could be stored and used to determine a schedule of cleaning for various places within the environment.

In various embodiments the service robot can include one or more types of acoustic damping mechanism as discussed in the examples of .

In various embodiments passive acoustic damping materials can include typical materials suited for such purposes such as various types and configurations of foam.

In accordance with aspects of the present invention service robot can be a robotic cleaner configured to implement a method of more effectively cleaning a space that includes furnishings for example. The cleaner and method can determine that the cleaner is under a furnishing and implement a different cleaning pattern as a function thereof. The determination that the robotic cleaner is under a furnishing can be accomplished using any one or more of a plurality of types of sensors mounted on integral with or coupled to the robotic cleaner.

In this embodiment for illustrative purposes it is presumed that the service robot is a robotic cleaner. In step the robotic cleaner begins cleaning. In step the robotic cleaner determines whether it is under a furnishing. As used herein the word furnishing can mean any physical item or object located in a space or environment being cleaned. It need not be limited to furniture for example.

In the present embodiment the robotic cleaner presumes that it is not under a furnishing unless it senses or otherwise determines that it is under a furnishing. If in step the robotic cleaner determined that it was not under a furnishing the robotic cleaner continues to clean the space using a general cleaning pattern in step . This general cleaning pattern can be any of those used in currently available robotic cleaners.

However if in step the robotic cleaner determined that it was under a furnishing the process would continue to step where the robotic cleaner would begin cleaning with a special pattern. The special pattern would be tailored for better cleaning under a furnishing. For example the special cleaning pattern can be tighter since it is designed to be effective in a smaller footprint. In the preferred embodiment when the robotic cleaner senses that it is moving out from underneath the furnishing it turns back the other way so that it stays underneath the furnishing until cleaning is complete.

Ultimately the process can move to step where a determination can be made of whether or not the robotic cleaner is done cleaning the space. If not the process can revert to step . If so the cleaner can exit the cleaning activity in step .

It will be understood by those skilled in the art that the monitoring for whether the robotic cleaner is under a furnishing can be substantially constant since the sensors can be in a sensing mode throughout the use of the robotic cleaner periodic or otherwise intermittent. Thus in some embodiment the sensed condition of moving under a furnishing can serve as an interrupt to the mode of the general open space cleaning. The interrupt can cause the robotic cleaner to begin cleaning with the special pattern.

In other embodiments the determination method may be based on upward facing height sensing as the un occluded distance in the upward direction is much shorter than in open spaces. In still other embodiments the determination may be based on other perceptual techniques such as acoustics or electromagnetic qualities of such under furnishing environments. In still other embodiments the determination method may be based on a combination thereof.

In various embodiments a robotic cleaner such as those in can be a low profile robotic cleaner. For example the robotic cleaner can be less than 6 inches in height and preferably about 2 inches or less in height.

In step the robot is in the process of servicing e.g. cleaning a location or area e.g. a room. In step the robot records completion of the cleaning and the location in a database. In step the robot searches the database to determine the next location to clean. In this embodiment there is a presumption that the location for which the longest time has elapsed since the last cleaning should be the next location cleaned. In step the robot navigates to the next location to be cleaned.

Note that in some embodiments the robot can include the database. However in other embodiments the robot could communicate over a wireless network with a database system within which such information can be stored.

In step the robot is cleaning in a location. In step the robot records completion of the cleaning including associating the date and time of cleaning in the database with location. The robot also senses and records the amount of dirt taken in when cleaning the location. In step an algorithm is run to determine the next location to be cleaned. The algorithm takes into account the last time the location was cleaned and the dirt level associated with that location. In step the robot navigates to a new location to begin cleaning that location.

In other embodiments the robot need not be configured with dirt sensors. However the robot could be preprogrammed with to clean certain locations with higher frequency than other locations. For example in an office building the highest traffic locations could be cleaned more frequently than other locations or public locations could be cleaned more frequently than private locations.

As will be appreciated by those skilled in the art various devices and approaches can be used to configure the robot with location awareness. For example the robot could have a map stored therein and track its own movements relative to the map. The robot could be navigated around the facility to acquire the map called training. The robot could navigate using markers or the like. As another example the robot can be configured to track its movements within a wireless cellular network e.g. using signal strength measuring techniques at access points distributed throughout the locations to be serviced. In short the present invention is not limited with respect to possible location tracking and navigation approaches.

In step people census data is accumulated which can happen in at least two ways. In step the robot accumulates people census data through its own observation. For example the robot can be configured with sensors that can sense the presence of people e.g. motion detectors acoustic sensors cameras light sensor and so on or some combination thereof. The robot can be configured to make observations over time collecting data over multiple uses. In step observation data is provided to the robot. In other embodiments the robot could accumulate observation data using a combination of direct observation and indirect observation

In step statistical modeling can be performed using the accumulated people census data. The modeling can be performed by the robot or in other embodiments the model can be downloaded to the robot. The model can indicate times and locations of people in the facility and or areas therein to be serviced. In step a determination of best times for the robot to service various locations is made. In step a service plan or schedule is made based on the determination in step . In step the service schedule is executed.

The service schedule can be updated over time based on subsequently collected people census data or other relevant information. In one embodiment the robot is configured to collect such people census information and to continually or periodically updated the statistical mode and service schedule.

In step the robot is at rest at a location. In step the robot receives information or data e.g. a trigger that indicates that people have left the location. In step the robot commences servicing the location in response to the trigger. For example when a room becomes vacated a robotic cleaner can begin to vacuum the room. The trigger could be externally provided or could be the product of one or more sensors included in the robot or a combination thereof.

In step the robot queries digital calendars of facility people e.g. as in a Microsoft Outlook calendar database. This can either be a pull query or a push query or a combination thereof. In any case the scheduling data for people in the facility is accumulated. The scheduling data can also include resource scheduling data. For example if a room such as cafeteria is closed or unscheduled from 2 pm to 5 pm the information could be included. In step the robot s work schedule or plan is created and or optimized based on such scheduling data. For example if a cafeteria is closed from 2 pm to 5 pm the robot could schedule cleaning of that room during that time if a conference is not booked for an during a particular day the robot could vacuum that conference room during that time if a building entrance is closed on weekends the robot could schedule cleaning on the weekend. Additionally if a group of people working in the same location are scheduled to be at a meeting at a certain time the robot could schedule cleaning of that location during the time when the people were at the meeting. As another example if an individual was scheduled to be on vacation for a particular day the robot could schedule the cleaning of that person s office on that day. In step the schedule is executed.

In step likely return times of people can be determined. For example the model could show that some people leave for lunch at 11 30 am and it could be predicted that those people will return by 1 pm. In step a robot service schedule or plan is created and executed by the robot. In step the robot stops work before the likely return of people based on the determination in step .

If the robot is interrupted it can stop and wait until the person or people leave. The robot can be configured to resume servicing the location thereafter.

In step the robot identifies an object or surface to be cleaned. For example an object could be a machine piece of furniture or other item. A surface could be glass hardwood flooring carpeting cement and so on as just a few examples. In step the robot queries an onboard knowledgebase which has information relating to object and or surface specific cleaning techniques or procedures stored therein. Based on the object or surface identified in step the robot determines the appropriate cleaning technique in step . In step the robot applies the technique to clean the object or surface. Upon completion the robot continues cleaning using general cleaning techniques in step until another object or surface is identified in step .

In step the robot identifies an object or surface to be cleaned. In step the robot queries an onboard library of object and or surface specific cleaning techniques or procedures . Based on the object or surface identified in step the robot chooses the appropriate cleaning technique in step . In step the robot uses the technique to clean the object or surface. Upon completion the robot continues cleaning using general cleaning techniques in step until another object or surface is identified in step .

In step the robot identifies an object or surface to be cleaned. For example an object could be a machine piece of furniture or other item. In step the robot queries a remote knowledgebase which has information relating to object and or surface specific cleaning techniques or procedures stored therein. Based on the object or surface identified in step the robot determines the appropriate cleaning technique in step . In step the robot applies the technique to clean the object or surface. Upon completion the robot continues cleaning using general cleaning techniques in step until another object or surface is identified in step .

In step the robot identifies an object or surface to be cleaned. In step the robot queries the remote library of object and or surface specific cleaning techniques or procedures . Based on the object or surface identified in step the robot chooses the appropriate cleaning technique in step . In step the robot uses the technique to clean the object or surface. Upon completion the robot continues cleaning using general cleaning techniques in step until another object or surface is identified in step .

Those skilled in the art will appreciate that a service robot could implement any combination of the above described methods.

As will be appreciated by those skilled in the art a service robot e.g. vacuum can include a memory for storing instructions and data and a processor for executing the instructions. Thus the methods discussed above can be programmed into the service robot for execution to accomplish the functions disclosed herein.

Also while the service robot was indicated as a robotic cleaner in this embodiment those skilled in the art will appreciate that methods in accordance with the present invention could be applied to any number of service robots and could implement any number and types of sensors.

While the foregoing has described what are considered to be the best mode and or other preferred embodiments it is understood that various modifications can be made therein and that the invention or inventions may be implemented in various forms and embodiments and that they may be applied in numerous applications only some of which have been described herein.

