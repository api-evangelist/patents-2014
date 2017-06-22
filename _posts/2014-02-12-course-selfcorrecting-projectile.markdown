---

title: Course self-correcting projectile
abstract: A new fuze that reduces projectile miss-distance to a target, by correcting for discrepancies in anticipated round velocities through its flight. As a result, the fuze-equipped projectile is nominally aimed at a target and maintains improved accuracy relative to a conventional round. The fuze adjusts for the discrepancies in velocity by using an internal electric motor to mechanically actuate a drag-altering surface on the fuze body. In order to adjust for errors in the anticipated velocity, the fuze compares its preprogrammed velocity to its actual velocity at a given point in time during flight. An anticipated velocity table versus time in flight is constantly referenced so that appropriate adjustments in velocity can be made.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09115968&OS=09115968&RS=09115968
owner: The United States of America as Represented by the Secretary of the Army
number: 09115968
owner_city: Washington
owner_country: US
publication_date: 20140212
---
The invention described herein may be manufactured and used by or for the Government of the United States for governmental purposes without the payment of any royalties thereon.

The present invention generally relates to the field of munitions such as explosive projectiles. Particularly the present invention relates to a projectile that is capable of self correcting its course toward an intended target during flight.

Traditional long range artillery munitions have been a mainstay of warfare over the centuries. Much effort has been spent attempting to improve upon the accuracy of the projectiles. With the development of semiconductors and the integrated circuits it has become possible to install embedded controllers to measure in flight dynamics and to correct for inaccuracies and disturbances as integral components of the artillery rounds.

In terms of accuracy the dispersion pattern of impact locations increases with the increasing range of projectiles. Factors that contribute to the increased dispersion are winds aloft meteorological data propellant temperature variations and marginal errors in gun elevations. The final dispersion pattern is an elongated ellipse with the major axis in the direction of flight.

Winds aloft present one form of disturbance in that crosswinds can send a projectile left or right relative to the intended target and head and tail winds can propel the projectile too far or too short of the intended target.

Recently different propellants have been used some combust more quickly and propel the projectiles out of the cannon at higher velocities than others. As a result resources have been dedicated to characterize the different production lots of propellants as they leave the factory. Ambient temperature also affects the propellant in a gun in that a hot propellant typically produces increased muzzle velocities while a cold propellant produces lower muzzle velocities.

In addition to external dynamics there are issues that affect the performance of the electronics installed within the projectiles. For inertial sensors the severe gun launch environment often produces permanent bias shifts in the measured acceleration of the projectiles. Additionally the high spin rate of the stabilized projectiles may also affect the readings on a sensor by adding spurious centrifugal forces to the sensor that are not in reality affecting the projectile.

One method to improve the accuracy of the projectile is to install GPS receivers that input an accurate estimate of the physical location of the projectile into the controller. Additionally the data from the GPS receivers can be coupled with advanced inertial suites capable of being calibrated and continuously updated throughout the flight of the projectile to improve performance. U.S. Pat. Nos. 7 500 636 and 7 834 300 are examples of the increasing complexity of integrated systems to guide a ballistic munition.

Separately the additional confounding of data by the spin stabilization is to add canards to the fuze as well as high cost bearings. This combination allows the electronics stored in the fuze to be de spun and acts independently of the spinning of the round.

Previous fuze efforts attempted to correct for the range dispersion and to improve the accuracy of spin stabilized projectiles in impact locations by employing a single action drag brake. Reference is made for example to U.S. Pat. Nos. 6 345 785 and 5 816 531. In this application the munition is intentionally fired too long such that if uncorrected the projectile would fly past the intended target. Then while in flight the controller would determine the best time for the drag brake to be deployed.

Incorporating guidance into artillery rounds increases the cost of the entire system. Gun hardened inertial measurement systems are relative costly. Similarly a significant cost driver is the gun hardening of components and electronics e.g. GPS to survive the loads of gun launching and to improve the flight path accuracy.

GPS denial is a modern concern between land space based intentional jamming of signals by adversarial actors solar activity also can prevent GPS signals from being received or correctly interpreted. However should the electronics on board the projectile be duds then the projectile will fly past the intended target and potentially cause collateral damage. For obscurant or illumination it would be beneficial to have a very low cost round that allows soldier assistance without prohibitive expenses.

There is therefore a need for a projectile that is capable of autonomously self correcting its course toward an intended target during flight. The projectile should be capable of being nominally aimed at the target and of maintaining improved accuracy relative to a conventional round. The projectile should not require overshoot adjustment. The projectile should be capable of being deployed at a less full or optimal deployment so that in the event of electronics or mechanism failure to maneuver the nominal flight the projectile would follow the flight trajectory of a conventional projectile including the standard statistical impact dispersion around the target location.

The present invention addresses the concerns of conventional projectiles and presents a new fuze that reduces projectile miss distance to a target by correcting for discrepancies in anticipated round velocities through its flight. As a result the fuze equipped projectile is nominally aimed at a target and maintains improved accuracy relative to a conventional round.

The invention adjusts for the discrepancies in velocity by using an internal electric motor to mechanically actuate a drag altering surface on the fuze body. The resulting increase and decrease in drag affects the velocity profile of the projectile in flight thus affecting its point of impact as it pertains to the distance from launch.

In order to adjust for errors in the anticipated velocity the fuze compares its preprogrammed velocity to its actual velocity at a given point in time during flight. The preprogrammed velocity electronically is inputted before launch into a memory on board the fuze. After the gun launch parameters are determined the RF signal projected by the velocimeter will be provided with an anticipated velocity table versus time in flight. This table will be constantly referenced so that appropriate adjustments in velocity can be made.

A two stage approach is implemented for the fuze to determine its actual velocity during flight. In the first stage the fuze determines velocity via detection of a Doppler shifted signal which originates from a velocimeter that is positioned at the launch location. The velocimeter projects a 10.25 GHz continuous wave RF signal in the direction of the fuze. An internal conformal antenna within the fuze is tuned to this frequency and receives the stationary signal from the velocimeter.

This signal is then mixed with a monolithic microwave integrated circuit MMIC of a similar frequency and low pass filtered to obtain a baseband signal. The frequency of this baseband signal corresponds to a Doppler shift due to the projectile velocity allowing the projectile velocity to be explicitly determined.

Because the velocimeter has a limited gain and thus a limited transmission range the fuze will not be able to receive the velocimeter projected signal as soon as the distance between the velocimeter and the fuze surpasses a threshold distance. As a result the second stage of the velocity determination enters into effect. Once the predetermined threshold distance is surpassed the fuze uses an accelerometer to determine its actual velocity. Acceleration readings are integrated and added to the previous time step velocity value to determine the current velocity.

To implement an accelerometer as a modality for the measurement of velocity in gun launched munitions it has inherent errors that must be overcome. The noisy accelerometer data includes two errors that are inherent in a gun launched and fuze mounted applications the shift after shock bias and the mount error spin bias.

The shift after shock bias occurs at gun launch and persists for the duration of flight. Due to the large G forces experienced during gun launch the accelerometer becomes permanently biased by a static value.

The mount error spin bias occurs as a result of two non ideal placement errors of the accelerometer. These errors are a the distance from the center of the accelerometer to the radial center of the fuze perpendicular to the direction of travel of the fuze and b the angular placement of the accelerometer relative to perpendicular the direction of travel of the fuze.

These two errors are unknown at launch but lead to the error equation where is the static bias error is the angular error component and is the spin rate of the projectile.

To remove the accelerometer error the fuze determines the foregoing three unknowns and . The spin rate is determined by an on board magnetometer. The spin of the projectile will result in a frequency component being visible when sampling the magnetometer that directly corresponds to the spin rate of the projectile.

In order to correct for these errors the actual acceleration must be known. This can be derived from the Doppler calculated velocity. An accurate acceleration is calculated by time filtering and differentiating the velocity.

The two error components the static bias error and the angular error component are determined while the projectile is in range of the muzzle velocimeter. Because the velocimeter provides an accurate and reliable measurement of acceleration every time step that the acceleration is determined by the velocimeter and accelerometer and sampled it yields the bivariate equation where is the acceleration measurement of the accelerometer and is the acceleration measurement of the velocimeter.

These two errors are removed by a least squares solution to the over determined mathematic system that is created by sampling from both acceleration methods many times. Once the error is removed from the accelerometer the fuze can adjust for velocity for the duration of the flight and guide to its intended target with increased accuracy.

Similar numerals refer to similar elements in the drawings. It should be understood that the sizes of the different components in the figures are not necessarily in Exact proportion or to scale and are shown for visual clarity and for the purpose of explanation.

With reference to the present invention provides a new fuze equipped projectile that autonomously self corrects its course toward an intended target during flight. The projectile can be initially nominally aimed at the target and it can self correct its flight path or course to maintain improved accuracy relative to a conventional round. As it will be explained later the projectile uses a continuously variable surface to fine tune the drag forces in order to minimize if not eliminate overshoot adjustment.

With further reference to in order to prevent external jamming of the guidance signals the projectile is provided with a fuze that is jam resistant and GPS independent. To this end the fuze uses three distinct guidance methods or Phases along the flight path .

During the initial Phase I or RF Guidance phase as illustrated by position A of the projectile the fuze uses a reference RF radio frequency signal from the launch position or gun location to calibrate an on board accelerometer for a short period of time following launch. After the projectile has left the vicinity of the launch position it is guided inertially inertial guidance or Phase II as illustrated by positions B through F of the projectile . to an apogee position F and then ballistically ballistic guidance of Phase III to the target as illustrated by positions G through J of the projectile .

To this end the fuze is generally comprised to a fuze body that is secured to a fuze base assembly . An adjustable drag assembly is secured to the fuze body and is located intermediate the fuze body and the fuze base .

Considering now the fuze body in more detail and with further reference to it generally includes an outer ceramic shell that houses and protects the electronic mechanical and other components of the fuze . More specifically these components include without limitation a fuze setter inductive coil whose function is known or available and thus will not be described in greater detail.

An electronics assembly is mounted above an electric motor . It comprises an accelerometer a G switch and a CPU computer or processor and programmable memory .

An electric motor is disposed axially within the outer shell . It includes a motor shaft that contacts a ball bearing which in turn contacts a base plate of the base assembly which allows it to freely rotate. The motor shaft extends through and is further secured to a piston head of the drag assembly in order to regulate the drag blades .

In an exemplary embodiment the electric motor is a brushless DC motor. Alternatively the electric motor can be for example a linear actuator a voice coil solenoid or a shape metal alloy system to generate the inward outward force needed to move the drag assembly .

A magnetometer a conformal 10.25 GHz antenna an MMIC assembly an MMIC assembly and a positional feedback sensor are also positioned within the outer shell . The MMIC assembly includes an MMIC a mixer and a low pass filter circuitry LPF .

Referring now to the drag assembly it generally includes four drag blades that are rotatably mounted onto a drag mount . In turn the drag mount is secured to the piston head . Each drag blade includes an outer drag blade surface whose movement and positioning provide the desired drag to the projectile .

The base assembly houses the battery used to power the various electrical and electronic components and circuitries as well as the electric motor of the fuze .

Among the numerous aspects of the present invention two major aspects will be emphasized herein the drag assembly or drag generation mechanism of and the method for removing errors from the accelerometer to allow for accurate guidance .

While previous drag braking methods include a single use application of drag blades which would use the spin of the projectile to pull the drag brakes into the free stream the present invention uses the opposing inward force of aero dynamic pressure to balance the outward centrifugal force of mass. This minimizes the force and power consumption required to deploy or retract the drag blades as it will be described later in more detail.

The operation and error correction function of the fuze will now be described in more detail with further reference to . During Phase I an ideal velocity profile is pre loaded into the programmable memory of the fuze so that this velocity profile can be used during flight as a reference against which the velocity that is measured by the fuze will be compared.

As illustrated in the exemplary preferred embodiment of the present invention the drag assembly is initially preset by the onboard processor to for example fifty percent deployed. The projectile is then loaded into the gun launch or firing platform at the launch position and fired. The high G force resulting from the gun launch is sensed by the G switch which in turn initiates the algorithms residing on the CPU to start.

The drag blades also referred to as drag brakes can increase or lower wind resistance based on how open they are. If the drag blades were completely closed the fuze would have the same aerodynamics as a normal fuze i.e. a smooth body . While setting the initial position of the drag blades to completely closed would allow for maximum potential range the problem arises that the initial trajectory of the projectile would require an overshoot of the intended target to maximize adjustment capability to the target. If there is some sort of failure in the drag blades after launch the projectile would miss the target by an unsafe margin as its mean point of impact would then be off target. Therefore by having the drag blades set to approximately 50 deployment on launch the sacrifice is approximately 8 of the projectile maximum range for the safety of a catastrophic failure of the drag blades resulting in a dispersion distributed about the intended target .

During Phase I the gun transmits a consistent reference RF signal at for example 10.25 GHz frequency. After the projectile leaves the barrel of the gun it begins to receive the reference RF signal with the frequency shifted by the Doppler effect .

In Phase II the fuze uses the fixed frequency of a velocimeter to read and determine the frequency of the Doppler shifted reference signal for a short period of time after muzzle exit. This Doppler shifted signal can be directly calculated as a velocity . Comparing the calculated velocity to the programmed reference velocity the fuze can then adjust for this discrepancy. Because the angle from the velocimeter to fuze will not be equivalent to the pitch angle of the round a pitch over adjustment must be made by utilizing the reference pitch programmed into memory to determine the true velocity of the fuze .

It is quite unlikely that the accelerometer can be mounted perfectly on the axis of the fuze without any misalignment angles or displacement off center. Any of these off axis placements will contribute some error to the reading of the accelerometer . The present invention uses the magnetometer in the fuze to determine the spin rate of the projectile in flight. It can be assumed that the error contributed to the acceleration measurement will be a function of the displacements multiplied by the square of the spin rate .

The CPU determines blade deployment is by measuring the difference between the preprogrammed reference velocity table with the calculated velocity.

With reference to the accelerometer presents two inherent errors that must be overcome. The noisy accelerometer data includes two errors that are inherent in a gun launched and fuze mounted applications the shift after shock bias and the mount error spin bias. The shift after shock bias occurs at gun launch and persists for the duration of flight. Due to the large G forces experienced during gun launch the accelerometer becomes permanently biased by a static value.

The mount error spin bias occurs as a result of two non ideal placement errors of the accelerometer. These errors are a the distance from the center of the accelerometer to the radial center of the fuze perpendicular to the direction of travel of the fuze and b the angular placement of the accelerometer relative to perpendicular the direction of travel of the fuze. These two errors are unknown at launch but lead to the error equation where is the static bias error is the angular error component and is the spin rate of the projectile .

To remove the accelerometer error the fuze determines the foregoing three unknowns and . The spin rate is determined by the on board magnetometer . The spin of the projectile will result in a frequency component being visible when sampling the magnetometer that directly corresponds to the spin rate of the projectile .

The two error components the static bias error and the angular error component are determined while the fuze is in range of the muzzle velocimeter . Because the velocimeter provides an accurate and reliable measurement of velocity and thus acceleration every time step that the acceleration determined by the velocimeter and the acceleration determined by the accelerometer is sampled it yields the bivariate equation where is the acceleration measurement of the accelerometer and is the acceleration measurement of the velocimeter .

In order to correct for these errors the actual acceleration must be known. This can be derived from the Doppler calculated velocity. An accurate acceleration is calculated by time filtering and differentiating the velocity at .

These two errors are removed by a least squares solution to the over determined mathematic system that is created by sampling from both modalities many times. Once the error is removed from the accelerometer the fuze can adjust for velocity for the duration of Phase II of the flight and guide to its intended target with increased accuracy.

In order to determine the ground velocity of the fuze using the accelerometer the accelerometer utilizes an integrator and the pitch over reference adjustment data to determine the contribution of acceleration due to gravity which is solely a function of pitch over angle. The contribution of the acceleration due to gravity is fed to a velocity adjustment algorithm .

In Phase II the fuze continues to adjust for velocity shifts due to environmental conditions until the projectile reaches the apogee position F which indicate the end of Phase .

Upon reaching the apogee position F the projectile enters the ballistic guidance phase wherein no new adjustments or calculations are entered and the projectile starts descending under the force of gravity toward the target .

Consequently the present projectile improves the flight accuracy toward the target reduces collateral damage and maintains relatively simple instructions for field operations.

Another advantage of the present projectile is its reduced cost of manufacture. The projectile utilizes a simplified guidance system which relies on a single accelerometer to measure the axial velocity of the projectile and the magnetometer which is used to measure the spin rate of the projectile . The reduced number and cost of the components necessarily entails a lower cast as compared to a conventional GPS equipped projectile.

It should be understood that other modifications might be made to the present self correcting projectile without departing from the spirit and scope of the invention.

