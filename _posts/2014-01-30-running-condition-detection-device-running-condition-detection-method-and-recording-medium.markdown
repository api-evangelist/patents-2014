---

title: Running condition detection device, running condition detection method, and recording medium
abstract: A running condition detection device includes


url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09234767&OS=09234767&RS=09234767
owner: CASIO COMPUTER CO., LTD.
number: 09234767
owner_city: Tokyo
owner_country: JP
publication_date: 20140130
---
The present invention relates to a running condition detection device and a running condition detection method and a recording medium for detecting and reporting where the current position is located in a predetermined route.

In recent years more and more people have been enjoying running such as jogging as a daily routine and taking part in a marathon event. A small global positioning system GPS equipped electronic device that such a runner wears for recording a run course and time is available on the market.

Typical GPS receivers show variations in precision of positional data acquired by the GPS. For example even when a mobile body from which positional data is to be acquired is running in a straight line the positional data is acquired at regular intervals swaying to the right and left of the straight line.

Accordingly when a moved distance of the runner is measured by taking a difference of the positional data acquired at regular intervals the moved distance is measured longer than an actual distance.

In order to reduce such an error in the measurement distance measurement without including great variations in the positional data can be considered by skipping the positional data to be used at preset time intervals or moved distance intervals the positional data being acquired at regular intervals.

However for example when the positional data is skipped in a situation where the runner is passing a street corner another problem arises that the moved distance cannot be measured in accordance with the corner because the positional data takes a shortcut between before and after the street corner.

A vehicle position correction system that corrects a vehicle position calculated from a detection output of a GPS sensor in accordance with a detection output of a distance sensor and a direction sensor is considered for example refer to JP 2010 008095 A .

An on board navigation system that corrects a vehicle position calculated from a detection output of a GPS sensor in accordance with a detection output of a geomagnetic sensor is considered for example refer to JP 05 018773 A .

For example a marathon course prescribes whether runners must run along a left line a right line or a central line on each road included in the course. Accordingly predetermined distances of marathons such as a full marathon and a half marathon are established. A distance from a start position to each check position is established by defining each street corner included in the course as a check position.

In contrast runners do not necessarily run precisely along the prescribed line on each road in the marathon course. Runners sometimes run in a zigzag direction or run along an opposite line leading to a gap between the prescribed distance on the course and the runner s moved distance as a natural consequence. Moreover as described above the moved distance measured based on the positional data from the GPS receiver that the runner carries which is longer than the actual distance does not coincide as is with the prescribed distance on the course.

Therefore the measurement precision of the moved distance can be improved by correcting the moved distance measured based on the GPS receiver at each street corner check position based on the distance data established in the marathon course along which runners run. For that purpose accurate detection of each street corner bend position on the course is required.

The present invention has been made in view of the above problems and an object of the present invention is to provide a running condition detection device and method for allowing accurate detection of a street corner that runners run.

a direction determination unit which obtains a current moving direction based on current positional data and last positional data from the GPS receiving unit 

a first bend determination unit which compares current moving direction data obtained by the direction determination unit and reference direction data to determine passage of a street corner 

a second bend determination unit which compares geomagnetic data detected by the geomagnetic sensor and reference geomagnetic data to determine passage of a street corner and

a determination control unit which prohibits the first and second bend determination units from determining passage of a street corner during a given period of time after passage of a street corner is determined by one of the first bend determination unit and the second bend determination unit and to maintain determination of passage of a street corner by the first and second bend determination units when determination is not prohibited.

Embodiments of the present invention will be described below with reference to the drawings. is a front view illustrating an appearance configuration of a wristwatch type electronic device according to the embodiments of a running condition detection device of the present invention.

The running condition detection device can be achieved by a portable terminal type electronic device such as a mobile phone a handheld game machine and a portable personal computer PC besides the wristwatch type electronic device described below.

A key input unit having a plurality of buttons for performing various mode settings instructions of setting the time instructions of start stop and the like is provided on a side of a body of the electronic device . In addition a display unit for displaying content depending on the preset mode is provided on a front surface of the body. A reference numeral is a wristband.

The electronic device has a function suitable for the use by a runner such as a function to display a course map when the runner runs the preset course a function to display how many kilometers from a start on the course the runner is located a function to display elapsed time a function to display how many kilometers there are from a current position on the course to a next checkpoint or goal and a function to display transit time per unit distance lap time .

The electronic circuit of the electronic device includes a central processing unit or CPU a control unit which is a computer.

The CPU controls operations of each part of the circuit by using a random access memory RAM as a working memory and performs various functions in accordance with an electronic device control program stored in a storage device in advance or an electronic device control program loaded from outside via an input output interface and stored in the storage device . The program performs a process in accordance with a user operation signal from a key input unit positioning latitude and longitude data at a current point based on reception by a GPS receiving unit each of three axis X axis Y axis Z axis geomagnetic data from a geomagnetic sensor unit various sensor signals from a motion sensor unit in accordance with a motion of the user or a communication signal from an external apparatus via the input output interface .

The GPS receiving unit receives an electric wave signal from a plurality of GPS satellites with an antenna demodulates the signal and outputs information such as latitude and longitude of the current point and time every second as positioning data.

The geomagnetic sensor unit has a three axis geomagnetic sensor. For example the geomagnetic sensor unit averages in two seconds each of the three axis X axis Y axis Z axis geomagnetic data measured every 0.2 second to eliminate noise generated under the influence of swinging an arm or for other reasons. The geomagnetic sensor unit then outputs every second each of the geomagnetic data T averaged in two seconds. The geomagnetic sensor unit detects as a street corner a portion in which variations of two axes are larger than a threshold value as illustrated in a portion encircled by a range D among each of the geomagnetic data output from the geomagnetic sensor unit .

The motion sensor unit has an accelerometer and a gyroscope sensor and measures or detects and outputs data such as a movement size a direction change and a motion of walking associated with the user s movement based on each of the sensor signals.

The input output interface is connected to for example an external PC and inputs and outputs various data directly with the external PC or with a server device on the Internet via the external PC.

In addition to the electronic device control program the storage device stores the map data course information of a plurality of running courses such as for example a jogging course and an exercise course for a marathon event before the user runs. As illustrated in for example the data includes positional data from a start position to each check position a street corner in the present embodiments which is a mid course transit point and to a goal position. Each positional data includes latitude and longitude data of each position and distance data indicating a distance from the start position. The map data course information is prepared by the user from a map displayed in a PC with predetermined software or provided as data from sources such as an event organizer and stored in the storage device via the input output interface of the electronic device . The distance data may not be converted into digital data in advance and may be calculated during a process based on the latitude and longitude data.

The RAM includes a display data memory a current position memory a final check flag position memory a total moved distance memory a GPS reference direction memory a GPS current direction memory a geomagnetic reference value memory a geomagnetic current value memory a next street corner memory a footstep count memory and a step memory

Display data for the display unit is converted into bit map image data and stored in the display data memory

The current position memory stores for example a moving position of the user runner according to the running course selected from the map data course information . As the moving position positional data according to the positioning data from the GPS receiving unit is stored.

A moved distance may be calculated with a difference between the current positional data obtained from the GPS receiving unit and last positional data and a total moved distance may be calculated by adding the difference. However a variation error of each positional data accumulates leading to an error from an actual total moved distance. In order to reduce the error a check flag is set in the positional data obtained every second from the GPS receiving unit at regular intervals for example four seconds during straight running. A moved distance calculated from a difference between the positional data in which the check flag is set is regarded as valid. In a case where the runner passes a street corner in the middle of the above described interval in order to prevent calculation with a moved distance of the interval being shortcut when passage determination of a street corner described later is made a check flag is set also in positional data obtained from the GPS receiving unit at that time. This allows calculation of the moved distance by making the positional data including the error obtained from the GPS receiving unit a straight shape as much as possible. This also allows precise calculation of the moved distance at a place where the course is bent.

The final check flag position memory stores latest positional data current position in which the check flag is set as a final check flag position.

The total moved distance memory stores for example a moved distance of the user runner in accordance with the running course selected from the map data course information 

The electronic device has a function to detect whether a direction in which the runner runs has made a turn based on a change of current direction data deg calculated in accordance with the current positional data acquired every second from the GPS receiving unit and last positional data a change equal to or greater than a threshold value from reference direction data deg . The electronic device also has a function to detect whether a direction in which the runner runs has made a turn based on a change of each of the three axis geomagnetic data T acquired every second from the geomagnetic sensor unit a change equal to or greater than a threshold value from at least two axis reference geomagnetic data T .

The GPS reference direction memory stores the reference direction data deg for detecting a bend of the direction in which the runner runs in accordance with output timing every second of the positioning data acquired from the GPS receiving unit . The current direction data deg is stored as is as initial reference direction data deg . After that every time a bend is detected the memory is updated to current direction data deg when the bend is detected. In the present embodiments direction data deg refers to a clockwise angle with due north being set to zero.

The GPS current direction memory stores current direction data deg calculated based on the current positional data and the last positional data every time positioning data is output from the GPS receiving unit every second .

The present embodiments assume that a bend detection threshold value based on the positioning data from the GPS receiving unit is set to 50 . When a change of the current direction data deg relative to the reference direction data deg is equal to or greater than the bend detection threshold value 50 it is determined that the runner has passed a street corner.

In the example illustrated in when initial reference direction data which is current direction data is 55 deg current direction data calculated by the 55th sampling is 108 deg and the change is equal to or greater than the threshold value 50 . Accordingly it is detected that the runner has passed a street corner. Then reference direction data is updated to the current direction data of 108 deg when the street corner is detected as new reference direction data.

The geomagnetic reference value memory stores the reference geomagnetic data T for detecting a bend of a direction in which the runner runs for each of the three axes X axis Y axis Z axis in accordance with output timing one second of the geomagnetic data T acquired from the geomagnetic sensor unit . The current geomagnetic data T is stored as is as initial reference geomagnetic data T . After that every time a bend is detected the geomagnetic reference value memory is updated to the current geomagnetic data T when the bend is detected.

The geomagnetic current value memory stores the current geomagnetic data T of each of the three axes X axis Y axis Z axis averaged in two seconds every time the geomagnetic data is output from the geomagnetic sensor unit every second .

The present embodiments assume that a bend detection threshold value based on each of the geomagnetic data is set to 15 T . When a change of the current geomagnetic data T relative to the reference geomagnetic data T is equal to or greater than the bend detection threshold value 15 T for at least two axes thereof it is determined that the runner has passed a street corner.

In the specific example illustrated in when the initial reference geomagnetic data which is the current geomagnetic data is 10 T the 55th output current geomagnetic data output is 27 T and the variation is equal to or greater than the threshold value 15 T . Accordingly it is detected that the runner has passed a street corner. Then the reference geomagnetic data is updated to the current geomagnetic data of 27 T when the street corner is detected as new reference geomagnetic data.

The next street corner memory stores positional data latitude and longitude data and distance data of a first check position of the map data when the running course is set before running. Subsequently the user begins running and every time the user arrives at a check position latitude and longitude data and distance data corresponding to a next check position are stored.

The footstep count memory stores footstep count data counted based on a sensor signal output from the motion sensor unit in accordance with the user s motion.

The step memory stores step data calculated based on a moved distance and a footstep count between certain points.

The analysis data storage unit stores data such as the positioning data from the GPS receiving unit each of the three axis geomagnetic data from the geomagnetic sensor unit each sensor signal from the motion sensor unit the current position the total moved distance the footstep count the step the lap time analyzed based on the elapsed time from the start the distance to the goal an average speed and an amount of movement.

The electronic device has a function to classify positioning precision of the positioning data obtained from the GPS receiving unit into good sufficient and bad poor to make a determination based on data of a protocol specified by national marine electronics association NMEA output from a GPS module depending on conformity to predetermined conditions.

Specifically for example a positioning error of 10 m or less is determined to be good sufficient and a positioning error larger than 10 m is determined to be bad poor .

Regarding each of the three axis geomagnetic data obtained from the geomagnetic sensor unit the electronic device has a function to determine whether the value of each of the geomagnetic data cannot be used because of disturbance.

Specifically the presence of disturbance is determined based on whether the square root of the sum of squares of each of the three axis geomagnetic intensity exceeds a predetermined value.

The electronic device configured in this way achieves the functions described in the following operational description by the CPU controlling operations of each part of the circuit in accordance with a command described in the electronic device control program and software and hardware operating in cooperation.

Next a runner support function of the electronic device according to the above configuration will be described.

The user operation of the key input unit activates the electronic device control program . Setting an operational mode to a runner support mode resets each data memory to in the RAM and causes a course setting message urging the user to set the running course along which the user will run subsequently to be displayed on the display unit .

In accordance with the course setting message the running course is set by the user selecting a desired running course from the plurality of map data course information stored in the storage device step S . Latitude and longitude data and distance data corresponding to a first check position of the set course are stored in the next street corner memory step S .

When a start button is pressed at a start position and running starts in accordance with the set course step S Yes the GPS receiving unit the geomagnetic sensor unit and the motion sensor unit start operations step S .

In accordance with a moved distance measurement process described later with reference to a moved distance from the running start is then calculated based on positioning data acquired from the GPS receiving unit stored in the total moved distance memory step SA and elapsed time is calculated step S .

At this time the display unit displays information such as the moved distance from the start stored in the total moved distance memory the calculated elapsed time lap time a distance to a next check position CP obtained by subtracting the total moved distance from the distance data corresponding to the first check position stored in the next street corner memory and a distance to the goal obtained by subtracting the total moved distance from the distance data of the set course refer to .

The runner s movement running motion is analyzed and the footstep count from the running start is measured and stored in the footstep count memory based on the sensor signal of the accelerometer acquired from the motion sensor unit step S .

Then it is determined whether the user has made a turn at a street corner in accordance with the bend determination process described later with reference to based on the positioning data acquired from the GPS receiving unit or the geomagnetic data acquired from the geomagnetic sensor unit step SB .

When it is not determined that the user has made a turn at a street corner step S No and when it is not determined that the stop button is pressed step S No a calculation process of the total moved distance from the running start a calculation process of the elapsed time and a measurement process of the footstep count are performed repeatedly and then the total moved distance the elapsed time the lap time and the distance to the next check position CP and the goal are updated sequentially and displayed steps SA S and S .

Subsequently when it is determined that the user has made a turn at the street corner herein the first check position in accordance with the bend determination process described later steps SB S Yes the current positional data latitude and longitude acquired from the GPS receiving unit and stored in the current position memory is corrected to the latitude and longitude data corresponding to the first check position set in the next street corner memory step S . This is intended to detect that the user has passed the street corner and to modify the data to an accurate position because an error of several meters to tens of meters may occur in a position obtained by the GPS depending on a receiving condition.

In addition the moved distance data stored in the total moved distance memory is corrected to the distance data corresponding to the first check position set in the next street corner memory step S . This is intended to detect that the user has passed the street corner and to modify the data to an accurate value because an error occurs in the position obtained from the GPS and in the distance calculated from the output of the motion sensor unit .

The user s step is then calculated and stored in the step memory by dividing the distance from the start position to the first check position set in the next street corner memory by an actual footstep count to the first check position stored in the footstep count memory step S .

The latitude and longitude data and the distance data corresponding to the next check position herein a second check position are then set stored in the next street corner memory step S .

At this time the distance corresponding to the first check position is subtracted from the distance corresponding to the second check position or the distance of the set course and the resulting distance is displayed as a distance to the next check position CP or a distance to the goal on the display unit in response to user operations.

Subsequently returning to the process from the step SA the calculation of the total moved distance based on the positioning data from the GPS receiving unit and the update process thereof the update process of the elapsed time and the footstep count measurement process based on the sensor signal from the motion sensor unit are performed repeatedly until it is determined that the user has made a turn at the street corner corresponding to the second check position steps SA to S SA .

Subsequently in a similar way to the above described steps a process for correcting the latitude and longitude data of the current position stored in the current position memory step S a process for correcting the total moved distance data stored in the total moved distance memory step S a process for calculating the latest step step S and a process for setting a next check position step S are performed repeatedly every time it is determined that the user has made a turn at the next check position street corner set in the next street corner memory such as the second check position a third check position and so on step S Yes .

Accordingly for example as illustrated in since the total moved distance after the start based on the set running course is corrected in accordance with the distance to each check position specified on the running course every time the user passes the check positions 1 2 and so on which are each transit point sufficiently precise moved distances can be calculated and displayed even if the moved distance from the passed check position to the next check position is calculated and added based on the positioning data a difference of the positional data sampled acquired from the GPS receiving unit .

Next the moved distance measurement process step SA of will be described in detail with reference to .

The check flag setting process is performed in response to the positional data being acquired from the GPS receiving unit at regular intervals one second . When the bend determination process refer to described later determines that the user has made a turn at a street corner step A Yes and when the bend determination process determines that there has been no determination that the user has made a turn at the street corner during an interval for example four seconds or more step A Yes a check flag is set in the positional data stored in the current position memory step A . On the other hand when the bend determination process does not determine that the user has made a turn step A No and when the bend determination process further does not determine that the user has not made a turn during the interval or more step A No a check flag is not set in the positional data stored in the current position memory step A .

When positional data is acquired from the GPS receiving unit at regular intervals one second and stored in the current position memory a moved distance according to a difference between the positional data in which the final check flag stored in the final check flag position memory is set and the positional data stored in the current position memory is calculated step A .

The current total moved distance is calculated by the moved distance calculated this time being added to the total moved distance stored in the total moved distance memory in accordance with the last moved distance measurement process. When it is confirmed that the current total moved distance is longer than the last total moved distance step A Yes the total moved distance stored in the total moved distance memory is updated to the current total moved distance step A .

When a check flag is set in the positional data stored in the current position memory step A Yes the positional data is stored in the final check flag position memory as positional data in which the final check flag is set step A .

This allows making the positional data including an error obtained from the GPS receiving unit a straight shape as much as possible to calculate the moved distance and precise calculation of the moved distance at a point where the course is bent.

When positioning precision of the positioning data acquired from the GPS receiving unit is bad or when the positioning data itself is not acquired the moved distance is calculated from the footstep count and the step acquired based on the sensor signal from the motion sensor unit and the calculated moved distance is added to the previous total moved distance to update the total moved distance.

The bend determination process is performed in accordance with a sampling interval one second of the positioning data from the GPS receiving unit and includes a GPS bend detection process step B a geomagnetism bend detection process step B an integrated bend detection process step B and a reference value update process step B . Each of the processes will be described in detail with reference to .

When the positioning data is acquired from the GPS receiving unit at regular intervals one second it is determined whether positioning precision of the positioning data is good OK or bad NG step B .

When the positioning precision of the GPS receiving unit is determined to be good OK step B Yes a moving vector current direction data deg is calculated based on the current positional data acquired from the present positioning data and the last positional data and stored in the GPS current direction memory refer to step B .

Then a difference change between the reference direction data deg stored in the GPS reference direction memory refer to and the current direction data deg is calculated step B to determine whether the difference is equal to or greater than a bend detection threshold value 50 step B .

When it is determined that the difference change is equal to or greater than the bend detection threshold value 50 step B Yes it is detected that the runner has passed a street corner step B .

On the other hand when it is determined in the above described step B that the positioning precision is bad NG step B No and when it is determined in the above described step B that the difference change is less than the threshold value step B No then the process is performed as a bend being not detected by the GPS step B .

While the bend detection GPS process is configured to calculate the current direction data moving vector from the last and present positional data acquired from the GPS receiving unit the bend detection GPS process may be configured to calculate a velocity vector by the Doppler effect to estimate the current direction data.

When the geomagnetic data is acquired from the geomagnetic sensor unit at regular intervals one second it is determined whether disturbance occurs in the current geomagnetism step B .

When it is determined that the current geomagnetism is free of disturbance step B Yes an average value two second average of the geomagnetic data measured every 0.2 second in association with an immediately preceding two second movement is calculated and stored in the geomagnetic current value memory as the current geomagnetic data T refer to step B .

Since each of the measured three axis geomagnetic data is stored with a flag with without disturbance being set when the two second average is calculated geomagnetic data in which the flag with disturbance is set is complemented and calculated by immediately preceding geomagnetic data in which the flag without disturbance is set.

Next a difference change between the reference geomagnetic data T stored in the geomagnetic reference value memory refer to and the current geomagnetic data T stored in the geomagnetic current value memory is calculated step B to determine whether the difference change is equal to or greater than a predetermined bend detection threshold value 15 T step B .

Regarding at least two axis data among each of the three axis current geomagnetic data T when it is determined that the difference change is equal to or greater than the bend detection threshold value 15 T step B Yes it is detected that the runner has passed a street corner step B .

On the other hand when it is determined in the above described step B that the geomagnetic data acquired from the geomagnetic sensor unit is not free of disturbance step B No and when it is determined in the above described step B that the change is less than the threshold value regarding at least two axis data among each of the three axis geomagnetic data step B No the process is performed as a bend being not detected by geomagnetism step B .

The integrated bend detection process prohibits bend determination while the runner is at a stop and during a given period of time for example five seconds after a bend is detected by the GPS bend detection process or the geomagnetism bend detection process to prevent wrong determination during a stop and wrong determination of making a turn twice at one street corner.

First it is determined whether the runner is at a stop by checking whether the positional data acquired from the GPS receiving unit includes a change or checking whether the runner s running motion is detected by various sensor signals acquired from the motion sensor unit step B .

When it is determined that the runner is not at a stop but is moving step B No it is determined whether the process is in the determination prohibition period of the given period of time after the bend is detected last time in the GPS bend detection process or the geomagnetism bend detection process step B .

When a counter that counts the given period of time five seconds after detection of the last bend reaches full count and is at a stop it is determined that the process is not in the determination prohibition period step B No . It is then determined whether passage of the street corner by the runner is detected in the GPS bend detection process or the geomagnetism bend detection process steps B and B .

When it is determined that either of the GPS bend detection process or the geomagnetism bend detection process detects that the runner has passed the street corner step B Yes or B Yes the counter of the given period of time five seconds is reset and counting of the determination prohibition period starts step B .

On the other hand when it is determined in the above described step B that the runner is at a stop step B Yes or when it is determined in the above described step B that the counter of the given period of time five seconds is counting and that the process is in the determination prohibition period step B Yes or when it is determined that neither the GPS bend detection process nor the geomagnetism bend detection process detects that the runner has passed a street corner steps B and B No the process is performed as a bend being not determined step B .

In the reference value update process first when it is determined that either of the GPS bend detection process or the geomagnetism bend detection process detects that the runner has passed a street corner step B Yes or B Yes the current direction data deg stored in the GPS current direction memory is stored as is in the GPS reference direction memory to update the reference direction data deg and the current geomagnetic data T stored in the geomagnetic current value memory is stored as is in the geomagnetic reference value memory to update the reference geomagnetic data T step B .

Next in step B of the GPS bend detection process refer to when the positioning precision of the positioning data acquired from the GPS receiving unit is determined to have restored from the bad NG condition to the good OK condition step B Yes the current direction data deg stored in the GPS current direction memory is stored as is in the GPS reference direction memory to update the reference direction data deg step B .

In step B of the geomagnetism bend detection process refer to when it is also determined that each of the three axis geomagnetic data acquired from the geomagnetic sensor unit has restored from the condition with disturbance to the condition without disturbance step B Yes the current geomagnetic data T stored in the geomagnetic current value memory is stored as is in the geomagnetic reference value memory to update the reference geomagnetic data T step B .

According to the above configuration of the electronic device since a given period of time is specified to be the determination prohibition period when either of the GPS receiving unit or the geomagnetic sensor unit determines that the runner has passed a street corner multiple times of bend detection at one street corner can be prevented.

Therefore it is possible to accurately determine that the runner has passed a street corner in a running course optionally set by the user and each time positional data and distance data at a check position corresponding to the street corner can be corrected to an accurate value.

When the positioning precision of the positioning data acquired from the GPS receiving unit is bad determination of a bend based on this data is not performed. When disturbance occurs in the geomagnetic data acquired from the geomagnetic sensor unit determination of a bend based on this data is not performed.

The above described embodiments are configured to perform all the processes by the running condition detection function including the moved distance measurement process and the bend determination process described with reference to inside the electronic device in accordance with the electronic device control program

In contrast the electronic device may be configured to receive and display data such as the highly precise current position and the total moved distance analyzed by a server device on a network performing processes by causing the server to include each of the functions and databases and by transmitting from the input output interface to the server device the user operation signal from the key input unit of the electronic device the positioning data acquired from the GPS receiving unit each of the three axis geomagnetic data acquired from the geomagnetic sensor unit and each sensor signal acquired from the motion sensor unit .

Techniques and databases of each process performed by the electronic device described in each of the embodiments that is each technique such as the running condition detection process illustrated in the flow chart of the check flag setting process illustrated in the flow chart of the moved distance measurement process associated with the running condition detection process illustrated in the flow chart of and the bend determination process associated with the running condition detection process illustrated in the flow charts of and a database including the map data course information may all be a program that a computer can execute and may be stored in an external recording medium not shown such as a memory card including a read only memory ROM card and a random access memory RAM card a magnetic disk including a floppy disk and a hard disk an optical disk including a compact disk read only memory CD ROM and a digital versatile disk DVD and a semiconductor memory for distribution. A computer which is the portable electronic device including the GPS receiving unit the geomagnetic sensor unit and the motion sensor unit can achieve the highly precise running condition detection function described in the embodiments and perform similar processes in accordance with the techniques described above by loading the program recorded in the external recording medium into the storage device and by the loaded program controlling the operation.

The data of the program for achieving each of the above described techniques can be transmitted over a network N in a form of a program code. The highly precise running condition detection function described above can also be achieved by downloading this program data by communication into the computer of the portable electronic device including the GPS receiving unit the geomagnetic sensor unit and the motion sensor unit .

The present invention is not limited to each of the embodiments described above. Various modifications may be made in an implementation stage without departing from the spirit of the invention. Furthermore aspects of the present invention in various stages are included in each of the above described embodiments and various aspects of the present invention may be extracted by an appropriate combination of a plurality of constituent features disclosed. For example even when some constituent features are deleted from all constituent features described in each embodiment or some constituent features are combined in a different form when the problem described in the section of Description of the Related Art can be solved and the effect described in the section of Advantage of the Invention is obtained the configuration with the constituent features deleted or combined may be extracted as aspects of the present invention.

