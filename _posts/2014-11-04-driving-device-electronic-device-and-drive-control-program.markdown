---

title: Driving device, electronic device, and drive control program
abstract: A driving device includes a storage unit configured to store waveform data of driving signals for stopping excitation of an actuator at a sinusoidal wave of a resonance frequency of the actuator, at portions other than a center point of an amplitude of the sinusoidal wave; and a processor programmed to execute a process including reading the waveform data stored in the storage unit and outputting, to the actuator, the driving signals corresponding to the waveform data that has been read.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09310914&OS=09310914&RS=09310914
owner: FUJITSU LIMITED
number: 09310914
owner_city: Kawasaki
owner_country: JP
publication_date: 20141104
---
This application is a U.S. continuation application filed under 35 USC 111 a claiming benefit under 35 USC 120 and 365 c of PCT Application PCT JP2012 064952 filed on Jun. 11 2012 the entire contents of which are incorporated herein by reference.

The embodiments discussed herein are related to a driving device an electronic device and a drive control program for driving an actuator.

Conventionally there is an electronic device including a flat touch panel as an input unit The touch panel is for receiving a touch to the touch panel as an input operation and no considerations have been made for providing a tactile sensation in accordance with the operation. Therefore in a conventional touch panel there has been demand for installing a device for expressing a tactile sensation in accordance with an operation.

Thus in recent years for example considerations have been made to provide a tactile sensation in accordance with an operation by using the vibration caused by a LRA Linear Resonant Actuator . Furthermore as the driving method of a LRA there is an example described in Patent Document 1 and an exclusive use IC Integrated Circuit for controlling a tactile presentation device.

However in the case of a vibration using LRA the vibration does not immediately stop when the input is stopped. Therefore for example it is difficult to express a precipitous tactile sensation caused by an operation of pressing a button of a metal dame type. Furthermore Patent Document 1 describes a vibration suppressing unit for performing antiphase input after the input of the LRA is stopped however the suppression effects have been insufficient. Therefore by the conventional technology it has been difficult to appropriately express the differences in tactile sensations in accordance with different types of operations.

According to an aspect of the embodiments a driving device includes a storage unit configured to store waveform data of driving signals for stopping excitation of an actuator at a sinusoidal wave of a resonance frequency of the actuator at portions other than a center point of an amplitude of the sinusoidal wave and a processor programmed to execute a process including reading the waveform data stored in the storage unit and outputting to the actuator the driving signals corresponding to the waveform data that has been read.

The object and advantages of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the appended claims. It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the invention as claimed.

The vibration indicated by the waveform rapidly attenuates in one through several cycles. Meanwhile the vibration indicated by the waveform continues until the free vibration according to the natural vibration frequency of LRA attenuates even after the supply of driving signals is stopped.

Incidentally the human fingertip becomes incapable of feeling a vibration when the acceleration of the vibration becomes less than or equal to 0.02 G in a vibration frequency 200 Hz. The vibration frequency is the number of vibrations per second. The acceleration of the vibration indicates the amount of change in velocity of the vibration per unit time. illustrates the sensitivity of a human s organ for feeling acceleration. Note that the human s organ for feeling acceleration is the Pacinian corpuscle. The Pacinian corpuscle is one of the four major types of mechanoreceptor mainly found in the skin.

That is to say with respect to the waveform the finger stops feeling the vibration within 0.01 seconds because the acceleration of vibration becomes less than or equal to 0.02 G. Meanwhile with respect to the waveform it takes 0.1 second for the acceleration of vibration to become less than or equal to 0.02 G and therefore the finger continues to feel the vibration. until 0.1 second passes. Therefore the human feels completely different tactile sensations in the case of the vibration indicated by the waveform and in the case of the vibration indicated by the waveform .

Thus in the present embodiment the pattern of the vibration of LRA has been devised to express a clicking feeling when the button is pressed.

In the following a description is given of an electronic device according to the present embodiment with reference to . illustrates an electronic device according to the present embodiment.

The electronic device according to the present embodiment may be any device having a touch panel including for example a display function and an input function as an input unit. For example the electronic device according to the present embodiment may be a smartphone a tablet type computer or a mobile information terminal.

An electronic device according to the present embodiment includes a case a touch panel a double sided tape a LRA and a substrate .

In the electronic device according to the present embodiment the touch panel is fixed to the case by the double sided tape . The LRA is attached to the surface of the touch panel on the side of the case . The LRA is formed by combining a vibration system having a resonance frequency designed in advance and an actuator. The LRA is a vibration device for generating a vibration mainly by driving the actuator with the resonance frequency in which the intensity of vibration changes according to the amplitude of the driving waveform. Note that in the present embodiment the LRA is the vibration device however the vibration device is not limited to a LRA as long as the vibration device has a structure including a resonator and an actuator to be subjected to excitation.

The substrate is arranged inside the case . On the substrate a driving device for controlling the driving of the LRA and a driver IC for outputting driving signals to the LRA are mounted.

When the user s finger contacts the touch panel the electronic device according to the present embodiment detects this contact and drives the LRA by the driving device mounted on the substrate and propagates the vibration of the LRA to the touch panel .

Note that the electronic device according to the present embodiment may be any device including the touch panel as an input operation unit and may therefore be a device such as an ATM Automatic Teller Machine that is installed and used at a particular location.

In the following a description is given of the LRA with reference to . illustrate examples of LRAs. illustrates an example of a LRA using a voice coil and illustrates an example of a LRA using a piezoelectric element.

A LRA illustrated in includes a spring a magnet and a coil . With respect to the LRA the natural vibration frequency f is indicated by the following formula 1 where the spring constant of the spring is k and the mass of the magnet is m.

A LRA illustrated in includes a weight a beam and a piezoelectric element . With respect to the LRA a natural vibration frequency f is indicated by the following formula 2 where the mass of the weight is m the Young s modulus of the beam is E the cross sectional second moment of the beam is I and the length in the longitudinal direction of the beam is L.

As the LRA according to the present embodiment the LRA using a voice coil may be applied or the LRA using the piezoelectric element may be applied.

Next with reference to a description is given of the driving device mounted on the substrate included in the electronic device according to the present embodiment. illustrates the driving device according to the present embodiment.

A driving device according to the present embodiment includes a CPU Central Processing Unit and a memory . The CPU performs a process of driving the LRA described below by reading and executing a drive control program stored in the memory . The memory is provided with a storage area storing the drive control program for controlling the driving of the LRA a storage area storing waveform data and a storage area storing an API Application Programming Interface for providing a tactile sensation.

The drive control program causes the CPU to execute drive control of the LRA . The waveform data is data expressing the waveform of driving signals that are generated in advance for expressing a clicking feeling by a vibration generated by the LRA . Details of the waveform data are described below. The API is activated by the drive control program and performs various processes for providing a tactile sensation. In the API is stored in the memory however the API may be stored in another memory mounted on the substrate .

When the driving device according to the present embodiment detects a contact made with the touch panel step S the driving device activates the API step S . Specifically for example the driving device may activate the API when a contact is made with a button displayed on the touch panel .

The API reads the waveform data stored in the memory and outputs a drive instruction corresponding to the waveform data to a driver IC step S . The driver IC receives the drive instruction and performs D A Digital to Analog conversion on the waveform data step S and amplifies the waveform data by an amplifier step S . The driver IC outputs the amplified signals to the IRA step S .

In the present embodiment attention is focused on the fact that the touch panel itself fixed to the case is also a vibration device that vibrates at a high frequency. In the present embodiment the driving signals of the LRA are signals for stopping the excitation on the LRA at the time point of the peak of the amplitude and the high frequency vibration of the touch panel itself is excited. Accordingly a vibration that rapidly attenuates in one through several cycles is generated to express a clicking feeling.

The driving signal G according to the present embodiment stops exciting the LRA at point P of the peak of the amplitude. The amplitude of the driving signal G becomes zero immediately after the excitation is stopped. As described above in the present embodiment by providing a point of discontinuity in the driving signal G where the value largely changes the vibration of the LRA is removed from the harmonic vibration at this point of discontinuity.

Furthermore in the example of the driving time of the LRA by the driving signal G is set to be a cycle of 7 4 such that the point P of the peak of the amplitude becomes the end of the driving signals G. The end of the driving signals G is the point where the excitation on the LRA is stopped. In the present embodiment the cycle of the driving signals G is 7 4 however the present embodiment is not so limited.

In the present embodiment for example the cycle of the driving signals C may be set such that the driving time of the LRA by the driving signals G is less than or equal to 10 ms. In the present embodiment the shorter the cycle of the driving signals G the shorter the time during which the finger continues to perceive the vibration and therefore it is possible to express a tactile stimulation of a short time that is close to a clicking feeling. Note that in this case in the present embodiment the intensity of the perception is reduced and therefore there is a need for securing a driving time by which a sufficient level of intensity is felt by the presented tactile sensation.

In step S of the driving device according to the present embodiment reads the waveform data indicating the driving signals G by the API and outputs a driving instruction corresponding to the waveform data to the driver IC . The driver IC performs D A conversion on the waveform data and amplifies the waveform data and outputs the waveform data to the LRA .

For example the waveform data according to the present embodiment may include the frequency the amplitude the phase and the driving time cycle of the driving signals G. Furthermore the waveform data may be a formula expressing the waveform of the driving signals G.

In the following a description is given. of a case where the driving signals C are applied to the LRA in the driving device driving device .

In the present embodiment the LRA vibrates at a resonance frequency of 225 Hz. Furthermore the touch panel is vibrated at a resonance frequency of 1 kHz. That is to say the vibration of the LRA is a low frequency vibration and the vibration of the touch panel is a high frequency vibration. Note that the resonance frequency of the touch panel is the resonance frequency in the state where the four sides of the touch panel are fixed to the case .

The high frequency vibration of the touch panel is not excited in the case where the LRA is vibrated at a low frequency of a resonance frequency of 225 Hz. In this state the driving device excites the high frequency vibration of the touch panel by removing the vibration of the LRA from the harmonic vibration and applying a rapid force to the touch panel .

As a result as illustrated in in the driving device at point P a high frequency vibration having a frequency of 1 kHz is excited and a vibration that rapidly attenuates in one through several cycles is generated. Furthermore in the example of by exciting a high frequency vibration at point P the timings of the maximum value of the acceleration in the low frequency vibration and the maximum value of the acceleration in the high frequency vibration are matched and superposed and therefore a precipitous peak having a high intensity is generated within a short period of time.

As described above in the present embodiment by generating a precipitous peak within a short period of time in the acceleration of the vibration it is possible to provide an acute tactile sensation and to express a clicking feeling.

Note that the acceleration of the vibration of the touch panel according to the present embodiment is detected with an acceleration sensor not illustrated arranged at the center of the touch panel .

In the following the effects of the present embodiment are described with reference to . illustrates the acceleration of the vibration of the touch panel when the voltage of the resonance frequency of the LRA is used as the driving signals. The example of illustrates the acceleration of the vibration of the touch panel when an attempt is made to express a clicking feeling by reducing the driving time of the LRA .

However even if the driving time of the LRA is reduced the vibration of the touch panel continues for several cycles because the stand up time for amplifying the vibration and the time until the acceleration of the amplified vibration attenuates to less than or equal to 0.02 G are needed. In the example of it takes approximately 25 ms from the stand up to the attenuation and the vibration. continues for approximately four cycles. Therefore it is difficult to provide an acute tactile sensation like a clicking feeling.

Conversely in a vibration having a frequency of 1 kHz is rapidly standing up and the vibration attenuates within approximately two cycles

Thus in the present embodiment it is possible to express a clicking feeling by generating a precipitous tactile sensation within a short period of time in the acceleration of the vibration.

Furthermore in the examples of the excitation is stopped at the point of the peak of the amplitude of the driving signals G however the point of stopping the excitation is not so limited. In the present embodiment for example the timing of the peak of the acceleration in the low frequency vibration and the timing of the peak of the acceleration in the high frequency vibration are matched and therefore the end of the driving signals may be shifted from the point P.

In the examples of the peak of the amplitude of the acceleration of the high frequency vibration as generated so as to substantially overlap the peak of the amplitude of the acceleration of the low frequency vibration.

In the examples of the low frequency vibration is a resonance frequency and therefore with respect to the waveform of the driving signals G in a phase difference of 2 is generated in the waveform of acceleration in and therefore the acceleration of vibration becomes zero at the point P of the peak of the amplitude in the driving signals G. In the present embodiment a high frequency vibration is excited at the point P that is the end of the driving signals G and the acceleration of the high frequency vibration reaches a peak. Therefore the timing when the acceleration of the high frequency vibration reaches a peak is slightly shifted from the timing of point P of the driving signals.

Specifically for example the peak of the acceleration of the low frequency vibration is supposed to reach a peak at cycle from the point P that is the end of the driving signals G and when this is converted into time the acceleration of the low frequency vibration reaches a peak maximum value at. approximately 1.11 ms later. Meanwhile the high frequency vibration stands up from zero at the point P that is the end of the driving signals G and is supposed to reach a peak of the acceleration in the same direction as that of the low frequency vibration at cycle. When this is converted into time the acceleration of the high frequency vibration reaches a peak maximum value at 0.75 ms later. Thus the peaks of the high and low frequency vibrations occur at a time difference of 0.36 ms. Furthermore assuming that the peak of the acceleration of the low frequency vibration is 100 the peak of the acceleration of the high frequency vibration overlaps a position of an intensity of approximately 87 with respect to the peak of the acceleration of the low frequency vibration.

Thus in the present embodiment assuming that the driving time of the LRA by the driving signals G is 7 4 cycle 0.36 ms and the peak of the amplitude of the driving signals G is 100 the point where the amplitude of the driving signals G is 87 may be set as the end of the driving signals G. By shifting the point P to be the end of the driving signals G it is possible to shift the timing at which the high frequency vibration is excited and the peak of the acceleration of the low frequency vibration and the peak of the acceleration of the high frequency vibration may be superposed.

In in the driving signals G a point P that is slightly shifted from the peak of the amplitude is the end. In the end P of the driving signals G is shifted from the peak of the amplitude and therefore the peak of the acceleration of the high frequency vibration is lower than the value indicated in but the same effects as those of are achieved.

That is to say for example the end of the driving signals in the present embodiment may be any point were it is possible to generate a precipitous peak for expressing a clicking feeling in the waveform expressing the acceleration of the vibration of the touch panel . Specifically the end of the driving signals may be any point where the value of the driving signal and zero become discontinuous. That is to say the end of the driving signals may be any point other than zero that is the center point of the amplitude. Note that the end of the driving signals is preferably a point that is as close to the peak of the amplitude as possible because it is possible to generate a precipitous peak within a short period of time in the waveform of the acceleration of the vibration of the touch panel .

Furthermore in the present embodiment for example after stopping the excitation on the LRA by the driving signals G a brake waveform for suppressing a residual vibration of the LRA may be applied on the LRA . A brake signal is for example signals of an antiphase of the vibration generated in the LRA . In the present embodiment by using the brake signals after stopping the excitation on the LRA by the driving signals G it is possible to reduce the residual vibration and the acceleration of the vibration of the touch panel may be a waveform that rapidly attenuates within a short period of time.

Furthermore in the electronic device according to the present embodiment the LRA is attached to the surface of the touch panel on the side of the case however the present embodiment is not so limited. For example the IRA may be arranged near the substrate arranged inside the case .

When the LRA is inside the case as illustrated in the electronic device A is preferably designed such that the resonance frequency of the touch panel is 1 kHz at the time when the assembly of the electronic device A is completed.

The present embodiment is also applicable to the electronic device A. Furthermore when the present embodiment is applied to the electronic device A it is possible to express a clicking feeling when the button of the metal dome type is pressed similar to the case of the electronic device according to the present embodiment.

According to an aspect of the embodiments a tactile sensation in accordance with an operation is provided.

The driving device the electronic device and the drive control program are not limited to the specific embodiments described herein and variations and modifications may be made without departing from the scope of the present invention.

All examples and conditional language recited herein ate intended for pedagogical purposes to aid the reader in understanding the invention and the concepts contributed by the inventor to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions nor does the organization of such examples in the specification relate to a showing of the superiority and inferiority of the invention. Although the embodiments of the present invention have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

