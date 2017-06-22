---

title: Vehicle electric power supply apparatus
abstract: A control unit of a vehicle electric power supply apparatus controls an opening and closing unit to set a switch to an OFF state and a voltage detection unit to detect an output voltage of a first power source and an output voltage of a second power source when a second electric load is to be driven, and the control unit inhibits driving of the second electric load when the absolute value of the difference between the output voltage of the first power source and the output voltage of the second power source detected by the voltage detection unit is a predetermined first threshold value or less over a predetermined length of time.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09458813&OS=09458813&RS=09458813
owner: HONDA MOTOR CO., LTD.
number: 09458813
owner_city: Tokyo
owner_country: JP
publication_date: 20140626
---
Priority is claimed on Japanese Patent Application No. 2013 138228 filed on Jul. 1 2013 and Japanese Patent Application No. 2013 138229 filed on Jul. 1 2013 the contents of which are incorporated herein by reference.

In the related art a vehicle electric power supply apparatus which includes a DC DC converter connecting a main power source connected to an electric load and an auxiliary power source connected to a generator that starts an engine and includes a switch between the main power source and the auxiliary power source is known for example refer to Japanese Unexamined Patent Application Publication No. 2010 195336 .

In the vehicle electric power supply apparatus according to the above related art it is desired to detect the presence or absence of an ON failure in which the switch is fixed to an ON state and thereby to prevent unintentional charge and discharge between the main power source and the auxiliary power source from occurring.

In addition in the vehicle electric power supply apparatus according to the above related art in the case that an output voltage of the auxiliary power source is decreased to less than a predetermined value and it is impossible to secure a voltage required to start the engine by the generator the switch is closed and electric power is supplied to the generator directly from the main power source. However only based on determining whether or not the output voltage of the auxiliary power source detected by a voltage sensor is less than the predetermined value it is impossible to appropriately determine whether or not the generator is actually capable of starting the engine and there is a possibility that electric power is unnecessarily supplied to the generator directly from the main power source.

In view of the foregoing an object of an aspect of the present invention is to provide a vehicle electric power supply apparatus capable of detecting the presence or absence of an abnormality of a switch between a first power source and a second power source and preventing unintentional charge and discharge from occurring.

In addition another object is to provide a vehicle electric power supply apparatus capable of appropriately starting an internal combustion engine.

In order to achieve the above object a vehicle electric power supply apparatus according to an aspect of the present invention adopts one of the configurations described below.

According to the aspect of 1 described above the control unit determines that an ON failure in which the switch is fixed to an ON state hereafter simply referred to as ON occurs in the case that the absolute value of the difference between the output voltage of the first power source and the output voltage of the second power source is the predetermined first threshold value or less over the predetermined length of time. In this case by inhibiting the driving of the second electric load connected to the second power source it is possible to prevent the output voltage of the first power source from decreasing and to prevent the shortage of electric power supplied to the first electric load.

Moreover according to the aspect of 2 described above by inhibiting the occurrence of a state that requires starting of the internal combustion engine by the electric motor for example an idle stopping state or the like it is possible to prevent the output voltage of the first power source from decreasing and to prevent the shortage of electric power supplied to the first electric load.

Moreover according to the aspect of 3 described above by inhibiting execution of the idle stopping in a state where restarting of the internal combustion engine from the idle stopping is not allowed i.e. a state having a possibility that the output voltage of the first power source decreases due to the ON failure of the switch the vehicle can be maintained to be operable.

Moreover according to the aspect of 4 described above in the case that the vehicle is stopped by setting an ignition switch to an OFF state hereinafter simply referred to as OFF or the like by removing driving inhibition of the second electric load it is possible to enable next time start up of the vehicle.

In addition according to the aspect of 5 described above the control unit determines that electric power supplied from the second power source to the electric motor is actually insufficient in the case that the rotation frequency after the predetermined length of time elapses in the starting of the internal combustion engine by the electric motor is the predetermined second threshold value or less. In this case by setting the switch to ON it becomes possible to supply electric power from the first power source to the electric motor and it is possible to appropriately start the internal combustion engine.

Moreover according to the aspect of 6 described above by inhibiting execution of the idle stopping in a state where restarting of the internal combustion engine from the idle stopping is not allowed i.e. a state where it is determined that there is a need to set the switch to ON in order to start the internal combustion engine and that there is a possibility of decreasing of the output voltage of the first power source it is possible to keep the vehicle being capable of being driven.

Hereinafter a vehicle electric power supply apparatus according to an embodiment of the present invention will be described with reference to the accompanying drawings.

A vehicle electric power supply apparatus according to the present embodiment is for example as shown in mounted in a vehicle . The vehicle electric power supply apparatus includes at least a capacitor second power source as a secondary battery a battery first power source a DC DC converter a controller control unit idle stopping unit a contactor switch and a contactor relay opening and closing unit .

The vehicle includes the vehicle electric power supply apparatus an FI ECU idle stopping unit a starter magnet switch STMGSW a starter relay a starter motor STM second electric load electric motor a generator ACG an internal combustion engine an electric load first electric load an ignition switch IGSW a first voltage sensor voltage detection unit a second voltage sensor voltage detection unit and a rotation frequency sensor rotation frequency detection unit .

The capacitor is for example an electric double layer capacitor an electrolytic capacitor a lithium ion capacitor and the like and is connected to the starter magnet switch . The capacitor is connected to a first input output terminal of the DC DC converter and a first terminal of the contactor . The capacitor is configured to be capable of being electrically connected to the battery the contactor relay the FI ECU the generator the electric load and the ignition switch via the DC DC converter or the contactor .

The battery is for example a lead battery of a predetermined voltage 12V or the like and the like and is connected to the contactor relay the FI ECU the generator the electric load and the ignition switch . The battery is connected to a second input output terminal of the DC DC converter and a second terminal of the contactor . The battery is configured to be capable of being electrically connected to the capacitor and the starter magnet switch via the DC DC converter or the contactor .

The DC DC converter is capable of increasing or decreasing voltage bi directionally between the first input output terminal and the second input output terminal by the control of the controller . The DC DC converter charges the capacitor by supplying the generated electric power that is produced by the generator at the time of running of the internal combustion engine or the regenerated electric power that is produced by the generator at the time of braking of the vehicle to the capacitor . In addition the DC DC converter discharges the capacitor by supplying the electric power stored in the capacitor to at least the battery or the electric load .

The DC DC converter is for example an H bridge step up step down DC DC converter and includes four first to fourth switching devices for example IGBT Insulated Gate Bipolar mode Transistor SW SW SW and SW that are connected in a bridge form.

The first switching device SW and the second switching device SW are paired and are connected in series between the first input output terminal and a ground terminal . That is a collector of the first switching device SW is connected to the first input output terminal an emitter of the first switching device SW is connected to a collector of the second switching device SW and an emitter of the second switching device SW is connected to the ground terminal

The third switching device SW and the fourth switching device SW are paired and are connected in series between the second input output terminal and the ground terminal . That is a collector of the third switching device SW is connected to the second input output terminal an emitter of the third switching device SW is connected to a collector of the fourth switching device SW and an emitter of the fourth switching device SW is connected to the ground terminal

Each of first to fourth diodes D to D is connected between the emitter and the collector of each of the switching devices SW SW SW and SW such that the direction from the emitter to the collector is the forward direction.

The DC DC converter includes a reactor L that is connected between a connecting point of the first switching device SW and the second switching device SW and a connecting point of the third switching device SW and the fourth switching device SW. In addition the DC DC converter includes a first capacitor Ca that is connected between the first input output terminal and the ground terminal and a second capacitor Cb that is connected between the second input output terminal and the ground terminal

The DC DC converter includes a resistance R and a diode D which are connected in series such that the resistance R and the diode D directly connect the first input output terminal and the second input output terminal . The diode D is provided such that the direction toward the first input output terminal from the second input output terminal is the forward direction of the diode.

The DC DC converter is driven by a signal which is output from the controller and is input to a gate of each of the switching devices SW SW SW and SW.

The controller controls the bi directional voltage increasing decreasing operation of the DC DC converter and connection and disconnection operations of the contactor by the contactor relay . Moreover the controller controls execution permission and execution inhibition of idle stopping by the FI ECU and outputs a control command that commands execution permission and execution inhibition of idle stopping to the FI ECU .

The controller is capable of detecting the internal resistance and the capacitance of the capacitor and determining whether or not the internal resistance is a predetermined value or more and is also capable of determining whether or not the capacitor is degraded based on the internal resistance. The controller is connected to the first voltage sensor that detects the output voltage VC of the capacitor a current sensor not shown in the drawing that detects the charge current and the discharge current of the capacitor and a temperature sensor not shown in the drawing that detects the temperature of the capacitor .

The controller is capable of controlling the discharge of the battery and the depth of discharge of the battery . The controller is connected to the second voltage sensor that detects the output voltage VB of the battery a current sensor not shown in the drawing that detects the charge current and the discharge current of the battery and a temperature sensor not shown in the drawing that detects the temperature of the battery .

The contactor switches between connection and disconnection of the first terminal and the second terminal of the contactor corresponding to an ON state and an OFF state of the contactor relay . The controller controls an ON state and an OFF state of the contactor relay .

Note that the first terminal of the contactor is connected to the first input output terminal of the DC DC converter a positive pole terminal of the capacitor and the starter magnet switch . The second terminal of the contactor is connected to the second input output terminal of the DC DC converter a positive pole terminal of the battery the generator and the electric load . Thereby in a connecting state the contactor connects each of the capacitor and the battery in parallel to the starter magnet switch and the starter motor that are connected in series. Note that a negative pole terminal of the capacitor and a negative pole terminal of the battery are grounded.

The FI ECU is for example an ECU Electronic Control Unit that is configured by an electronic circuit such as a CPU Central Processing Unit and performs various controls relating to operations of the internal combustion engine such as fuel supply and ignition timing. The FI ECU controls starting and stopping of the internal combustion engine by a start request signal and a stop request signal that are output from the ignition switch corresponding to the operation of the driver.

The FI ECU controls idle stopping of the internal combustion engine . In the idle stopping the internal combustion engine in a running state is automatically and temporarily stopped corresponding to establishment of a predetermined pause condition and the internal combustion engine in a pause state is automatically restarted corresponding to establishment of a predetermined return condition. The predetermined pause condition is for example a condition in which the vehicle speed of the vehicle is zero an accelerator pedal opening degree is zero and a brake pedal switch is ON. The predetermined return condition is for example a condition in which the brake pedal switch is OFF.

The FI ECU starts the internal combustion engine by controlling the starter relay to be ON corresponding to the start request by the signal output from the ignition switch or a return request from the pause state of idle stopping. The FI ECU controls the power generation operation of the generator ACG and arbitrarily changes the generated voltage of the generator .

The generator is for example an AC generator linked to a crankshaft not shown in the drawing of the internal combustion engine via a belt or the like. The generator generates electric power using the power of the internal combustion engine in operation and thereby outputs the generated electric power. When the vehicle is decelerated is running in a state where fuel supply is stopped or the like the generator converts kinetic energy of the vehicle body transmitted from drive wheels not shown in the drawing of the vehicle into electric energy regenerated energy and outputs the regenerated electric power. Note that the generator includes a rectifier not shown in the drawing that rectifies an AC output by electric power generation and regeneration into a DC output or the like.

The generator is grounded and also is connected to the second input output terminal of the DC DC converter .

The internal combustion engine is started by the driving force of the starter motor STM . The starter motor is driven to rotate by the application of voltage from the capacitor or the battery via the starter magnet switch STMGSW . The starter magnet switch switches between the presence and absence of electric power supplied to the starter motor corresponding to an ON state and an OFF state of the starter relay . The FI ECU controls an ON state and an OFF state of the starter relay .

The starter motor for example includes a pinion gear not shown in the drawing in a rotating shaft not shown in the drawing . The internal combustion engine for example includes a ring gear not shown in the drawing that engages with the pinion gear of the starter motor in the crankshaft not shown in the drawing . Thereby the starter motor is capable of transmitting the driving force to the internal combustion engine by engaging the pinion gear with the ring gear of the internal combustion engine .

The electric load is one of a variety of auxiliary machines mounted in the vehicle or the like. The electric load is grounded and is also connected to the second input output terminal of the DC DC converter .

The vehicle electric power supply apparatus according to the present embodiment includes the configuration described above. Next operations of the vehicle electric power supply apparatus will be described.

Hereinafter charging and discharging operations of the capacitor and the battery controlled by the controller will be described.

The controller controls the bi directional voltage increasing decreasing operation of the DC DC converter and the connection and disconnection operations of the contactor by the contactor relay such that the output voltage of the capacitor is matched with a predetermined target voltage corresponding to the driving state of the vehicle .

The controller performs nine operation modes M to M as the charging and discharging operations of the capacitor and the battery corresponding to the driving of the vehicle as shown in Table 1 below.

First for example as the period of time t to immediately before time t shown in in a state where the ignition switch is OFF the controller performs the operation of a stopping period charging mode M. In the stopping period charging mode M as shown in the controller charges the capacitor by electric power supply to the capacitor from the battery via the diode D and the resistance R of the DC DC converter . Thereby the controller prevents the output voltage of the capacitor for example corresponding to the voltage of the positive pole terminal with respect to the grounded negative pole terminal from decreasing excessively.

Next for example as time t shown in when the controller receives a start request to start the internal combustion engine by the signal output from the ignition switch the controller performs failure detection of the contactor described later and then performs the operation of a first time start up mode M.

In the first time start up mode M the controller first sets the contactor to be in a disconnecting state by setting the contactor relay to OFF and in the disconnecting state of the contactor the controller sets the starter magnet switch to be in a connecting state by setting the starter relay to ON. Thereby the controller drives the starter motor by electric power supply from only the capacitor .

At this time in the case that a predetermined condition described later is established the controller sets the contactor to be in a connecting state by setting the contactor relay to ON. Thereby as shown in the controller connects each of the capacitor and the battery in parallel to the starter magnet switch and the starter motor that are connected in series. Then the controller drives the starter motor by electric power supply from the capacitor and the battery and starts the internal combustion engine using the driving force of the starter motor .

Note that in the first time start up mode M for example as time t shown in the output voltage and the remaining capacity SOC of the capacitor decreases due to electric power supply from the capacitor to the starter motor .

Next for example as the period of time t to time t shown in in a state where the vehicle is in a running state other than deceleration and where there is no execution command of idle stopping the controller performs the operation of an I S preparation charging mode M. In the I S preparation charging mode M as shown in the controller charges the capacitor by electric power supply to the capacitor from the generator via the DC DC converter using the generated electric power output from the generator that generates electric power by the drive power of the internal combustion engine in a running state. Moreover electric power is supplied from the generator to the electric load and also is supplied from the generator to the battery corresponding to the state of the battery .

In more detail the controller sets the contactor to be in a disconnecting state by setting the contactor relay to OFF and sets the starter magnet switch to be in a disconnecting state by setting the starter relay to OFF. The controller applies a current to the diode D and the resistance R and also applies a current to the third switching device SW in an ON state the reactor L and the first diode D in between the second input output terminal and the first input output terminal of the DC DC converter . The controller charges the capacitor at least until the output voltage of the capacitor reaches a predetermined I S preparation voltage such that electric power required to restart the internal combustion engine is stored in the capacitor in preparation for execution of idle stopping.

Note that the predetermined I S preparation voltage is for example an output voltage corresponding to the remaining capacity SOC of the capacitor capable of performing electric power supply required for the electric load and the like in the pause state of the internal combustion engine over a predetermined period of time due to idle stopping.

Moreover for example as the period of time t to time t shown in in a state where the vehicle is in a running state other than deceleration where there is no execution command of idle stopping and where the output voltage of the capacitor has reached the predetermined I S preparation voltage the controller continues to perform the operation of the I S preparation charging mode M. In this case as shown in the controller switches the third switching device SW from the ON state to the OFF state and applies a current to the diode D and the resistance R in between the second input output terminal and the first input output terminal of the DC DC converter . Thereby the controller maintains the output voltage of the capacitor at the predetermined I S preparation voltage.

Next for example as the period of time t to time t shown in in a state where fuel supply is stopped such as when the vehicle is decelerated the controller performs the operation of a regeneration charging mode M. In the regeneration charging mode M as shown in the controller charges the capacitor by electric power supply to the capacitor from the generator via the DC DC converter using the regenerated electric power output from the generator when the vehicle is decelerated or the like. Moreover electric power is supplied from the generator to the electric load and also is supplied from the generator to the battery corresponding to the state of the battery . The controller converts kinetic energy of the vehicle body transmitted from drive wheels not shown in the drawing of the vehicle into electric energy regenerated energy by the generator and produces the regenerated electric power.

In more detail the controller sets the contactor to be in a disconnecting state by setting the contactor relay to OFF and sets the starter magnet switch to be in a disconnecting state by setting the starter relay to OFF. The controller applies a current to the diode D and the resistance R and also applies a current to the third switching device SW in an ON state the reactor L and the first diode D in between the second input output terminal and the first input output terminal of the DC DC converter . The controller charges the capacitor at least in a range in which the output voltage of the capacitor is a predetermined upper limit voltage or less.

Note that the predetermined upper limit voltage is greater than the I S preparation voltage and is for example an output voltage corresponding to a full charge state namely remaining capacity SOC 100 .

Moreover in a state where fuel supply is stopped such as when the vehicle is decelerated and where the output voltage of the capacitor has reached the predetermined upper limit voltage the controller continues to perform the operation of the regeneration charging mode M. In this case as shown in the controller switches the third switching device SW from the ON state to the OFF state and applies a current to the diode D and the resistance R in between the second input output terminal and the first input output terminal of the DC DC converter . Thereby the controller maintains the output voltage of the capacitor at the predetermined upper limit voltage.

Next for example as the period of time t to time t shown in in a state where the vehicle is running at a constant speed or the like and where there is no execution command of idle stopping the controller performs the operation of a regeneration discharging mode M. In the regeneration discharging mode M as shown in the controller discharges the capacitor by electric power supply from the capacitor to the electric load via the DC DC converter using the regenerated electric power stored in the capacitor exceeding the predetermined I S preparation voltage.

In more detail the controller sets the contactor to be in a disconnecting state by setting the contactor relay to OFF and sets the starter magnet switch to be in a disconnecting state by setting the starter relay to OFF. The controller applies a current to the first switching device SW in an ON state the reactor L and the third diode D in between the first input output terminal and the second input output terminal of the DC DC converter . The controller discharges the capacitor at least until the output voltage of the capacitor reaches the predetermined I S preparation voltage. At this time the controller stops electric power generation and regeneration of the generator or sets the output voltage of the generator to a voltage lower than a specified voltage at normal operations.

Next for example as the period of time t to time t shown in in a state of stopping of the vehicle a state where the vehicle speed is zero and executing idle stopping the controller performs the operation of an I S electric power supply capacitor mode M. In the I S electric power supply capacitor mode M as shown in in the pause state of the internal combustion engine due to idle stopping of the vehicle the controller discharges the capacitor by electric power supply from the capacitor to the electric load via the DC DC converter using the electric power stored in the capacitor exceeding a predetermined I S lower limit voltage.

In more detail the controller sets the contactor to be in a disconnecting state by setting the contactor relay to OFF and sets the starter magnet switch to be in a disconnecting state by setting the starter relay to OFF. The controller applies a current to the first switching device SW in an ON state the reactor L and the third diode D in between the first input output terminal and the second input output terminal of the DC DC converter . The controller discharges the capacitor at least until the output voltage of the capacitor reaches the predetermined I S lower limit voltage while securing electric power required to restart the internal combustion engine corresponding to a return request.

Note that the predetermined I S lower limit voltage is smaller than the I S preparation voltage and is for example an output voltage corresponding to a remaining capacity SOC capable of performing appropriate electric power supply required to restart the internal combustion engine in the pause state by the driving force of the starter motor . In addition appropriate electric power supply by the capacitor means that the capacitor is discharged such that the output voltage of the capacitor is not decreased to less than a predetermined minimum safeguard voltage. Therefore as shown in the controller is capable of charging the capacitor by electric power supply to the capacitor from the battery via the diode D and the resistance R of the DC DC converter in addition to electric power supply to the electric load from the battery . Thereby the controller prevents the output voltage of the capacitor from decreasing to a voltage less than the predetermined minimum safeguard voltage. Note that the minimum safeguard voltage is smaller than the I S lower limit voltage and is for example an output voltage required to maintain the capacitor in an adequate state.

Next for example as the period of time t to immediately before time t shown in in a state of stopping of the vehicle a state where the vehicle speed is zero and idle stopping and where the output voltage of the capacitor has reached the predetermined I S lower limit voltage the controller performs the operation of an I S electric power supply BATT mode M. In the I S electric power supply BATT mode M as shown in in the pause state of the internal combustion engine due to idle stopping of the vehicle the controller charges the capacitor by electric power supply from the battery to the capacitor via the DC DC converter using electric power stored in the battery . Moreover electric power is supplied from the battery to the electric load .

In more detail the controller sets the contactor to be in a disconnecting state by setting the contactor relay to OFF and sets the starter magnet switch to be in a disconnecting state by setting the starter relay to OFF. The controller switches the first switching device SW from the ON state to the OFF state and applies a current to the diode D and the resistance R in between the second input output terminal and the first input output terminal of the DC DC converter . Thereby the controller maintains the output voltage of the capacitor at the predetermined I S lower limit voltage and inhibits discharging from the capacitor in which the minimum electric power required to restart the internal combustion engine corresponding to a return request is secured.

Next for example as time t shown in when the controller receives a return request that requests to restart the internal combustion engine in the pause state due to idle stopping the controller performs the operation of an ENG restarting mode M. In the ENG restarting mode M as shown in the controller sets the contactor to be in a disconnecting state by setting the contactor relay to OFF and sets the starter magnet switch to be in a connecting state by setting the starter relay to ON. The controller drives the starter motor by electric power supply from only the capacitor connected in parallel to the starter magnet switch and the starter motor that are connected in series and restarts the internal combustion engine by the driving force of the starter motor .

The controller supplies electric power from the battery to the electric load and also charges the capacitor by electric power supply from the battery to the capacitor via the DC DC converter . Thereby the controller prevents the output voltage of the capacitor from decreasing to less than the predetermined minimum safeguard voltage if the output voltage and the remaining capacity SOC of the capacitor decreases due to electric power supplied from the capacitor to the starter motor .

Note that for example as time t shown in in the case that it is impossible to restart the internal combustion engine by electric power supply from only the capacitor to the starter motor when the operation of the ENG restarting mode M is performed as shown in the controller sets the contactor to be in a connecting state by setting the contactor relay to ON. Thereby the controller drives the starter motor by electric power supply from the capacitor and the battery and restarts the internal combustion engine by the driving force of the starter motor .

The controller determines that it is impossible to restart the internal combustion engine in the case that the rotation frequency of the internal combustion engine engine rotation frequency NE detected by the rotation frequency sensor is a predetermined rotation frequency or less after a predetermined length of time elapses since the beginning of restarting the internal combustion engine in the case that a signal indicating a starting error of the internal combustion engine output from the FI ECU is received or the like.

The controller inhibits the next execution of idle stopping in the case that the internal combustion engine is restarted by setting the contactor relay to ON. Note that the determination basis of inhibition of the next execution of idle stopping is not limited only to whether or not the internal combustion engine is restarted by setting the contactor relay to ON. The controller may calculate the total number of times of the restarting and inhibit the next execution of idle stopping in the case that the total number of times is a predetermined number of times or more for example once or more . In addition the controller may inhibit the next execution of idle stopping in the case that the output voltage of the battery decreases to a predetermined lower limit voltage or less when the internal combustion engine is restarted by setting the contactor relay to ON.

Next for example as the period of time t to time t shown in in a state where the vehicle is in a running state other than deceleration and where there is no execution command of idle stopping the controller performs the operation of the I S preparation charging mode M described above.

Next the controller performs the operation of a vehicle stopping period mode M over a predetermined length of time since the ignition switch is switched from ON to OFF. In the vehicle stopping period mode M as shown in the controller sets the contactor to be in a disconnecting state by setting the contactor relay to OFF and sets the starter magnet switch to be in a disconnecting state by setting the starter relay to OFF. The controller discharges the capacitor by electric power supply from the capacitor to the battery and the electric load via the DC DC converter and suppresses degradation of the capacitor in the stopping period of the vehicle . In more detail the controller applies a current to the first switching device SW in an ON state the reactor L and the third diode D in between the first input output terminal and the second input output terminal of the DC DC converter .

Note that in order to prevent the output voltage of the capacitor in the stopping period of the vehicle from decreasing to less than the predetermined minimum safeguard voltage the controller charges the capacitor by electric power supply from the battery to the capacitor via the diode D and the resistance R of the DC DC converter in addition to electric power supply from the battery to the electric load .

In the case that the ignition switch is turned off and the vehicle becomes in a stopping state the controller removes inhibition of the next execution of idle stopping that requires restarting of the internal combustion engine by the driving of the starter motor namely driving inhibition of the starter motor .

Hereinafter control of connection and disconnection of the contactor by the contactor relay will be described in detail.

In the starting of the vehicle when the ignition switch is switched from OFF to ON before the starting of the internal combustion engine the controller performs failure detection of the contactor by using the output voltage VC of the capacitor detected by the first voltage sensor and the output voltage VB of the battery detected by the second voltage sensor .

First for example in step S shown in the controller determines whether or not the ignition switch is switched from OFF to ON.

In the case that this determination result is No the determination process of step S is repeatedly performed.

Next in step S the controller detects the presence or absence of the ON failure of the contactor . In more detail the controller determines whether or not the absolute value of the difference between the output voltage VC and the output voltage VB is a predetermined first threshold value or less over a predetermined length of time in a state where it is commanded to set the contactor to be in a disconnecting state by setting the contactor relay to OFF.

On the other hand in the case that this determination result is Yes it is determined that the output voltage VC of the capacitor and the output voltage VB of the battery are substantially the same the difference between the output voltage VC and the output voltage VB is within a range of error due to the occurrence of the ON failure in which the contactor is fixed to be in a connecting state.

Note that the predetermined first threshold value is appropriately set according to the accuracy of the measurement device first voltage sensor second voltage sensor the accuracy of the whole measurement system measurement environments or the like.

For example the first threshold value can be 0.001VC 0.002VC 0.003VC 0.004VC 0.005VC 0.006VC 0.007VC 0.008VC 0.009VC 0.01VC 0.02VC 0.03VC 0.04VC 0.05VC 0.06VC 0.07VC 0.08VC 0.09VC or 0.1VC.

Alternatively the first threshold value can be 0.001VB 0.002VB 0.003VB 0.004VB 0.005VB 0.006VB 0.007VB 0.008VB 0.009VB 0.01VB 0.02VB 0.03VB 0.04VB 0.05VB 0.06VB 0.07VB 0.08VB 0.09VB or 0.1VB.

In the case that the controller determines that an ON failure of the contactor occurs the controller notifies of the ON failure by a notification device not shown in the drawing that performs notification by display or sound output and inhibits execution of idle stopping.

Next in step S the controller commands setting the contactor to be in a connecting state by setting the contactor relay to ON.

Next in step S the controller detects the presence or absence of an OFF failure of the contactor . In more detail the controller determines whether or not the output voltage VC and the output voltage VB change between before and after the controller commands setting the contactor to be in a connecting state.

On the other hand in the case that this determination result is No it is determined that the OFF failure in which the contactor is fixed to be in a disconnecting state occurs.

For example as before time ta shown in in the stopping state of the vehicle normally the controller sets the output voltage of the capacitor to equal to or less than a predetermined voltage which is lower than the output voltage of the battery in order to suppress degradation of the capacitor . In this state as the period of time ta to time tb when electric power supply from the battery to the capacitor is started by setting the contactor relay to ON and the output voltage VB of the battery decreases and the output voltage VC of the capacitor increases the controller determines that the contactor is normal.

In the case that the controller determines that an OFF failure of the contactor occurs the controller notifies the driver of the vehicle of the occurrence of an OFF failure by the notification device not shown in the drawing and inhibits execution of idle stopping. Moreover the controller sets driving of the starter motor to be waiting until the temperature of the capacitor increases to a predetermined temperature or more in order to enable the internal combustion engine to start by electric power supply from only the capacitor at the first time start up. Then the controller notifies the driver of the vehicle by the notification device not shown in the drawing of that the internal combustion engine is set to be waiting for starting.

Next in step S in the case that the contactor relay is set to ON the controller sets the contactor to be in a disconnecting state by switching the contactor relay from ON to OFF.

Next the controller performs failure detection of the contactor and then performs the operation of the first time start up mode M.

First in step S shown in the controller sets the starter magnet switch to be in a connecting state by setting the starter relay to ON. Then the pinion gear of the starter motor is engaged with the ring gear of the internal combustion engine and a state in which the driving force of the starter motor is capable of being transmitted to the internal combustion engine is set.

Next in step S the controller drives the starter motor by electric power supply from only the capacitor .

Next in step S the controller determines whether or not a predetermined condition is established. The predetermined condition is for example that the output voltage VC of the capacitor and the output voltage VB of the battery are a predetermined first voltage or more the output voltage VC of the capacitor is a predetermined second voltage or less and the rotation frequency of the internal combustion engine engine rotation frequency NE detected by the rotation frequency sensor is a predetermined rotation frequency second threshold value or less. The predetermined first voltage is a voltage required to prevent welding and wear of the contactor . The predetermined second voltage is a voltage that is allowed to be applied to the battery during electric power supply from the capacitor to the battery .

Next in step S the controller sets the contactor to be in a connecting state by setting the contactor relay to ON.

Next in step S the controller drives the starter motor by electric power supplied from the capacitor and the battery and starts the internal combustion engine .

Next in step S the controller determines whether or not the states of the internal combustion engine from initial ignition to perfect ignition are confirmed.

In the case that this determination result is No the determination process of step S is repeatedly performed.

Note that the controller determines that perfect ignition occurs in the case that the engine rotation frequency NE detected by the rotation frequency sensor reaches a predetermined determination rotation frequency used to determine perfect ignition of the internal combustion engine .

Next in step S the controller sets the starter magnet switch to be in a disconnecting state by setting the starter relay to OFF and stops the driving of the starter motor . Then the engagement between the pinion gear of the starter motor and the ring gear of the internal combustion engine is removed and power transmission between the starter motor and the internal combustion engine is disconnected.

Next in step S in the case that the contactor relay is set to ON the controller sets the contactor to be in a disconnecting state by switching the contactor relay from ON to OFF and completes starting of the internal combustion engine and the routine proceeds to END.

The controller performs the operation of the ENG restarting mode M in an idle stopping state of the vehicle .

First in step S shown in the controller determines whether or not a return request that requests to restart the internal combustion engine in a pause state due to idle stopping is received.

In the case that this determination result is No the determination process of step S is repeatedly performed.

Note that the return request is for example output from the FI ECU in the case that the brake pedal operation by the driver is removed or the like.

Next in step S the controller sets the starter magnet switch to be in a connecting state by setting the starter relay to ON. Then the pinion gear of the starter motor is engaged with the ring gear of the internal combustion engine and a state in which the driving force of the starter motor is capable of being transmitted to the internal combustion engine is set.

Next in step S the controller drives the starter motor by electric power supply from only the capacitor .

Next in step S the controller determines whether or not the output voltage VC of the capacitor is a predetermined third voltage or more and the engine rotation frequency NE detected by the rotation frequency sensor is greater than a predetermined rotation frequency after a predetermined length of time elapses since the beginning of restarting the internal combustion engine . Note that the predetermined third voltage is a voltage required for a current that flows through the contactor to be a predetermined upper limit current or less in the case that the contactor in a disconnecting state at this time is switched to a connecting state.

In the case that this determination result is No it is determined that the situation is a starting limit and the routine proceeds to step S described later.

Next in step S the controller determines whether or not the states of the internal combustion engine from initial ignition to perfect ignition are confirmed.

In the case that this determination result is No the determination process of step S is repeatedly performed.

Then in step S the controller sets the starter magnet switch to be in a disconnecting state by setting the starter relay to OFF and stops the driving of the starter motor . Then the engagement between the pinion gear of the starter motor and the ring gear of the internal combustion engine is removed and power transmission between the starter motor and the internal combustion engine is disconnected. Thereby the controller completes starting of the internal combustion engine and the routine proceeds to END.

In addition in step S the controller sets the starter magnet switch to be in a disconnecting state by setting the starter relay to OFF and stops driving of the starter motor . Then the engagement between the pinion gear of the starter motor and the ring gear of the internal combustion engine is removed and power transmission between the starter motor and the internal combustion engine is disconnected.

Next in step S the controller notifies the driver of the vehicle by the notification device not shown in the drawing of that it is necessary to perform a predetermined operation for example a predetermined key operation an ON operation of the ignition switch or the like in order to restart the internal combustion engine .

Next in step S the controller determines whether or not the predetermined operation is performed by the driver of the vehicle .

In the case that this determination result is No the determination process of step S is repeatedly performed.

Then in step S the controller starts performing the operation similar to the first time start up mode M. In more detail first the starter magnet switch is set to be in a connecting state by setting the starter relay to ON. Then the pinion gear of the starter motor is engaged with the ring gear of the internal combustion engine and a state in which the driving force of the starter motor is capable of being transmitted to the internal combustion engine is set.

Next in step S the controller drives the starter motor by electric power supply from only the capacitor .

Next in step S the controller determines whether or not the predetermined condition described above is established.

In the case that this determination result is No the determination process of step S is repeatedly performed.

Next in step S the controller sets the contactor to be in a connecting state by setting the contactor relay to ON.

Next in step S the controller drives the starter motor by electric power supplied from the capacitor and the battery and restarts the internal combustion engine .

Next in step S the controller determines whether or not the states of the internal combustion engine from initial ignition to perfect ignition are confirmed.

In the case that this determination result is No the routine proceeds to step S. In this step S it is determined that an abnormality of the internal combustion engine occurs and the routine proceeds to END.

Then in step S the controller sets the starter magnet switch to be in a disconnecting state by setting the starter relay to OFF and stops the driving of the starter motor . Then the engagement between the pinion gear of the starter motor and the ring gear of the internal combustion engine is removed and power transmission between the starter motor and the internal combustion engine is disconnected.

Next in step S the controller sets the contactor to be in a disconnecting state by setting the contactor relay to OFF and completes restarting of the internal combustion engine .

Then in step S the controller commands inhibition of the next execution of idle stopping and the routine proceeds to END.

For example in the case that the engine rotation frequency NE is a predetermined lower limit rotation frequency or less within a predetermined period of time elapsed since the completion of restarting of the internal combustion engine the controller determines that an abnormality of the electric power supply circuit configured by the capacitor and the battery occurs and inhibits the next execution of idle stopping.

In addition for example in the case that the engine rotation frequency NE is a predetermined lower limit rotation frequency or less within a predetermined period of time elapsed since the completion of restarting of the internal combustion engine the controller changes for example increases the predetermined I S lower limit voltage. In the case that the output voltage VC of the capacitor detected by the first voltage sensor is less than the I S lower limit voltage after the change the controller inhibits execution of idle stopping.

As described above according to the vehicle electric power supply apparatus of the present embodiment during the starting of the vehicle when the ignition switch is switched from OFF to ON before the starting of the internal combustion engine the controller detects the presence or absence of an OFF failure of the contactor . At this time the controller commands that the contactor is set to be in a connecting state by setting the contactor relay to ON and therefore in the case that the contactor is normal it is possible to clean up the contact point of the contactor . Moreover it is possible to increase the output voltage of the capacitor by electric power supplied from the battery to the capacitor and it is possible to improve the starting performance and the toughness performance when the internal combustion engine is started by electric power supplied from the capacitor to the starter motor . In addition in the case that an OFF failure occurs the controller sets driving of the starter motor to be waiting until the temperature of the capacitor increases to a predetermined temperature or more at the first time start up and therefore it is possible to start the internal combustion engine adequately by electric power supplied from the capacitor to the starter motor .

Moreover since the controller detects the presence or absence of an ON failure of the contactor and in the case that an ON failure occurs inhibits execution of idle stopping namely inhibits driving of the starter motor it is possible to prevent the output voltage of the battery from decreasing and to prevent electric power supply shortage in the electric load as a variety of auxiliary machines to which electric power is supplied from the battery from occurring.

In addition as described above according to the vehicle electric power supply apparatus of the present embodiment because the controller first drives the starter motor by electric power supplied from only the capacitor when the operation of the first time start up mode is performed it is possible to prevent the output voltage of the battery from decreasing and to prevent electric power supply shortage in the electric load as a variety of auxiliary machines to which electric power is supplied from the battery from occurring. For example by preventing the controller to which electric power is supplied from the battery from being reset it is possible to prevent the starting time when the internal combustion engine is started from being long and to improve the starting performance and the toughness performance.

Moreover because the controller connects the contactor in the case that a predetermined condition is established in a state where the starter motor is driven by electric power supplied from only the capacitor it is possible to prevent the contactor from being unnecessarily connected. Moreover because the contactor is connected in the case that electric power supplied from the capacitor to the starter motor is actually insufficient it becomes possible to supply electric power from the battery to the starter motor and it is possible to appropriately start the internal combustion engine .

Moreover in the case that the controller stops driving of the starter motor because the controller disconnects the starter magnet switch by setting the starter relay to OFF and then disconnects the contactor by setting the contactor relay to OFF it is possible to suppress contact point wearing of the contactor .

Moreover in the case that it is impossible to restart the internal combustion engine by electric power supply from only the capacitor to the starter motor when the operation of the ENG restarting mode is performed the controller stops the starter motor and the internal combustion engine and then connects the contactor . Thereby the controller can prevent the output voltage of the battery from decreasing by supplying electric power from the battery to the capacitor during the driving of the vehicle .

Moreover the controller inhibits execution of the idle stopping in a state where restarting of the internal combustion engine from the idle stopping is not allowed namely in a state where it is necessary to connect the contactor in order to restart the internal combustion engine and therefore there is a possibility that the output voltage of the battery decreases. Thereby it is possible to appropriately keep the vehicle being capable of being driven.

Note that the technical scope of the present invention is not limited to the above described embodiments and a variety of modifications can be made to the above described embodiments without departing from the scope of the present invention. Accordingly it should be understood that the configurations in the embodiments described and illustrated above are exemplary of the invention and can be suitably altered.

For example in the embodiment described above the DC DC converter is an H bridge step up step down DC DC converter but the converter is not limited thereto. The converter may be a step up step down DC DC converter having another configuration.

For example in the embodiment described above in the case that a predetermined condition is established when the operation of the first time start up mode M is performed the controller sets the contactor to be in a connecting state and drives the starter motor by electric power supplied from the capacitor and the battery . However the present invention is not limited thereto. In the case that the remaining capacity SOC of the capacitor is insufficient the controller may inhibit driving of the starter motor and also charge the capacitor by electric power supplied from the battery to the capacitor until the output voltage of the capacitor reaches a voltage which is capable of starting the internal combustion engine .

