---

title: Voltage generating circuit having a discharge part and display apparatus having the voltage generating circuit
abstract: A voltage generating circuit includes a voltage dividing part connected between a main voltage source and a ground configured to divide a main voltage into a plurality of driving voltages and output the plurality of driving voltages, a delay part connected between a driving voltage source and the ground, and configured to delay a driving voltage by a predetermined period and apply the driving voltage to an input terminal of a driver circuit, and a discharge part connected between the voltage dividing part and the delay part, and configured to discharge a voltage charged in the delay part to a ground when the driving voltage is blocked. The discharge part comprises an amplifier, an inverting input of the amplifier being connected to the driving voltage source and a non-inverting input of the amplifier being connected to an output terminal of the delay part.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09384706&OS=09384706&RS=09384706
owner: Samsung Display Co., Ltd.
number: 09384706
owner_city: 
owner_country: KR
publication_date: 20140422
---
This application claims priority to and the benefit of Korean Patent Application No. 10 2013 0157122 filed on Dec. 17 2013 the entire contents of which are incorporated herein by reference.

Exemplary embodiments of the inventive concept relate to a voltage generating circuit and a display apparatus having the voltage generating circuit. More particularly exemplary embodiments of the inventive concept relate to a voltage generating circuit for providing a high reliability and a display apparatus having the voltage generating circuit.

In general a display apparatus includes a liquid crystal LC display panel and a plurality of driver circuits which drives the LC display panel.

The LC display panel includes a plurality of gate lines a plurality of data lines and a plurality of pixels. The driver circuits include a gate driver circuit which drives the gate lines and a data driver circuit which drives the data lines. In addition the driver circuits include a voltage generating circuit which generates a plurality of driving voltages to drive the driver circuits.

When an external voltage is applied to the display apparatus the display apparatus become a turn on state. The external voltage is applied to the voltage generating circuit the voltage generating circuit generates the driving voltages using the external voltage and then the driving voltages are applied to the driver circuits. Thus the display apparatus may be operated.

However when the external voltage is blocked the driving voltages are not supplied to the driver circuits and then the display apparatus become a turn off state. When the display apparatus is in the turn off state a charged voltage in the driver circuits needs to be discharged quickly in order that the driver circuits can be driven normally when the display apparatus is turned on again subsequently. When the charged voltage in the driver circuits does not entirely discharge in the turn off state a false operation of the driver circuits occur.

Exemplary embodiments of the inventive concept provide a voltage generating circuit having a self discharge function.

Exemplary embodiments of the inventive concept provide a display apparatus having the voltage generating circuit.

According to an exemplary embodiment of the invention there is provided a voltage generating circuit. The voltage generating circuit includes a voltage dividing part connected between a main voltage source and a ground and configured to divide a main voltage into a plurality of driving voltages and output the plurality of driving voltages a delay part connected between a driving voltage source and the ground and configured to delay a driving voltage by a predetermined period and apply the driving voltage to an input terminal of a driver circuit and a discharge part connected between the voltage dividing part and the delay part and configured to discharge a voltage charged in the delay part to a ground when the driving voltage is blocked. The discharge part may include an amplifier an inverting input of the amplifier being connected to the driving voltage source and a non inverting input of the amplifier being connected to an output terminal of the delay part.

In an exemplary embodiment the discharge part may further include a transistor which comprises a control electrode connected to an output terminal of the amplifier to output an output signal of the amplifier a first electrode connected to the output terminal of the delay part and a second electrode connected to the ground.

The discharge part further includes a resistor connected between the output terminal of the amplifier and the control terminal of the transistor.

According to an exemplary embodiment of the invention there is provided a display apparatus. The display apparatus includes a display panel comprising a plurality of data lines a plurality of gate lines and a plurality of pixels a panel driving part comprising a plurality of driver circuits which is configured to drive the display panel and a voltage generating part comprising a voltage dividing part which is connected between a main voltage source and a ground the voltage dividing part being configured to generate into a plurality of driving voltages utilizing a main voltage a delay part which is connected between a driving voltage source and the ground the delay part being configured to delay a driving voltage by a predetermined period and apply the driving voltage to an input terminal of a driver circuit and a discharge part which is connected between the voltage dividing part and the delay part the discharge part being configured to discharge a voltage charged in the delay part to a ground when the driving voltage is blocked. The discharge part may include an amplifier an inverting input of the amplifier being connected to the driving voltage source and a non inverting input of the amplifier being connected to an output terminal of the delay part.

In an exemplary embodiment the discharge part may a transistor which comprises a control electrode connected to an output terminal configured to output an output signal of the amplifier a first electrode connected to the output terminal of the delay part and a second electrode connected to the ground.

In an exemplary embodiment the driver circuits may include a data driver part configured to drive the data lines a gate driver part configured to drive the gate lines and a timing control part configured to control a driving timing of the data driver part and the gate driver part.

In an exemplary embodiment the delay part may be configured to delay a driving voltage of the timing control part and to provide a reset terminal of the timing control part with delayed driving voltage.

In an exemplary embodiment the discharge part may be configured to discharge a voltage applied to an output terminal of the delay part to the ground when the main voltage is blocked.

In an exemplary embodiment the amplifier may be driven by a remaining voltage which is dropped from the main voltage when the main voltage is blocked.

According to the inventive concept when the main voltage is blocked the voltage charged in the capacitor of the delay part may be discharged quickly. In addition the abnormal signal charged in the capacitor may be discharged quickly. Therefore a driving reliability of the display apparatus may be improved.

Hereinafter the inventive concept will be explained in detail with reference to the accompanying drawings.

Referring to the display apparatus may include a display panel a voltage generating circuit and a panel driving part . The panel driving part may include a plurality of driver circuits and the driver circuits may include a timing control part a data driver part and a gate driver part .

The display panel may include a plurality of data lines DL a plurality of gate lines GL and a plurality of pixels P.

The data lines DL extend in a first direction D and are arranged in a second direction D crossing the first direction D.

The pixels P are arranged in a matrix configuration which includes a plurality of pixel columns and a plurality of pixel rows. A pixel column may include pixels arranged in the first direction D and a pixel row may include pixels arranged in the second direction D.

Each of pixels P may include a switching element TR a liquid crystal capacitor CLC and a storage capacitor CST. The switching element TR is connected to a gate line GL a data line DL and the liquid crystal capacitor CLC. The storage capacitor CST is connected to the liquid crystal capacitor CLC. A liquid crystal LC common voltage VCOM is applied to a first end portion of the liquid crystal capacitor CLC and a storage common voltage VCST is applied to the storage capacitor CST. The LC common voltage VCOM may have a voltage level equal to that of the storage common voltage VCST.

The voltage generating circuit is configured to generate a plurality of driving voltages to drive a plurality of driver circuits of the display apparatus. The voltage generating circuit may include a voltage dividing part a delay part and a discharge part . The plurality of driver circuits may include the display panel the timing control part the data driver part and the gate driver part .

The voltage dividing part is configured to divide a main voltage VIN received from an external system into a plurality of driving voltages and to output the driving voltages. For example the driving voltages may include a first driving voltage TVDD to drive the timing control part second driving voltages AVDD and DVDD to drive the data driver part third driving voltages VON and VOFF to drive the gate driver part and fourth driving voltage VCOM and VCST to drive the display panel .

The discharge part may be connected to at least one of a plurality of output terminals of the voltage dividing part . The discharge part discharges a voltage applied to an output terminal of the voltage dividing part to a ground when the main voltage VIN is blocked.

The delay part is connected between the output terminal of the voltage dividing part and an input terminal of a driver circuit receiving the driving voltage from the output terminal. The delay part is configured to delay the driving voltage and to provide delayed driving voltage to the driver circuit.

In an exemplary embodiment when the driving voltage is changed from a low level to a high level the transistor in the discharge part is turned off and the driving voltage which is delayed by a predetermined period through the delay part is applied to the input terminal of the driver circuit for example a reset terminal REST of the timing control circuit . However when the driving voltage is changed from the high level to the low level the transistor in the discharge part is turned on and the voltage which is applied to the delay part is discharged to a lower level for example the ground. The voltage applied to the delay part may be a voltage charged in a capacitor of the delay part . Thus the driving voltage is blocked form being applied to the input terminal of the driver circuit.

In addition in a condition in which the main voltage VIN is blocked form being applied to the voltage generating circuit that is the driving voltage is at the low level if an abnormal signal such as an electrostatic charge is applied to the delay part the electrostatic charge is blocked from being applied to the input terminal of the driver circuit by the discharge part which discharges the electrostatic charge by turning on the transistor . Therefore the discharge part may prevent the driver circuit from damaging by the electrostatic charge.

The timing control part receives an original control signal OCS and an image data signal IDATA from the external system.

The timing control part is configured to generate a plurality of timing control signals to drive the plurality of driver circuits based on the original control signal OCS which controls a driving timing of the driver circuits. For example the timing control signals may include a data control signal DCS to control the data driver part and a gate control signal GCS to control the gate driver part . The data control signal DCS may include a vertical synchronization signal a horizontal synchronization signal a data enable signal a load signal and so on. The gate control signal GCS may include a vertical start signal and a plurality of clock signals.

The timing control part is configured to correct the image data signal IDATA using various compensation algorithms and is configured to provide the data driving part with corrected image data signal. The compensation algorithms may include for improving a response time and a color reproduction.

The data driver part is configured to convert the data signal IDATA received from the timing control part into a data voltage using a reference gamma voltage and is configured to provide the data line DL with the data voltage.

The gate driver part is configured to generate a gate signal based on the gate driving voltages VON and VOFF and the gate control signal and is configured to sequentially provide the gate line GL with the gate signal.

Referring to the voltage generating circuit may include a voltage dividing part a discharge part and a delay part .

The voltage dividing part may include a resistor string . The resistor string is connected between the main voltage VIN and a ground GND. The voltage dividing part is configured to divide the main voltage VIN into a plurality of driving voltages through the resistor string and is configured to output the plurality of driving voltages having different levels.

Hereinafter the voltage generating circuit will be explained referring to a driving voltage TVDD applied to the reset terminal REST of the timing control part .

As shown in a first output terminal OT of the voltage dividing part is configured to output the driving voltage TVDD.

The amplifier may be a non inverting amplifier. The amplifier includes a negative power supply T an inverting input T a non inverting input T a positive power supply T and an output T. The negative power supply T is connected to the ground GND the inverting input T is connected to the first output terminal OT of the voltage dividing part and the non inverting input T is connected to a second output terminal OT of the delay part . The positive power supply T is connected to the main voltage VIN and is configured to receive a main voltage VIN and the output T is configured to output an output signal corresponding to a signal applied to the non inverting input T. In an exemplary embodiment the amplifier outputs a non inverted signal which has a same phase as the signal applied to the non inverting input T through the output T. The second output terminal OT of the delay part is configured to output a reset voltage to reset the timing control part .

The transistor include a control electrode CE which is connected to the output T of the amplifier via a resistor a first electrode EE which is connected to the second output terminal OT of the delay part and a second electrode EE which is connected to the ground GND. The transistor may be a NPN transistor. The transistor may be a NPN bipolar transistor.

The delay part may include a resistor R and a capacitor C which is serially connected to the resistor R. For example the delay part may have a RC time constant corresponding to a driving sequence of the driver circuits. The resistor R includes a first end portion E which is connected to the first output terminal OT of the voltage dividing part and a second end portion E which is connected to the second output terminal OT of the delay part . The capacitor C includes a first end portion E which is connected to the second output terminal OT of the delay part and a second end portion E which is connected to the ground GND. The second output terminal OT of the delay part is connected to a reset terminal REST of the timing control part .

A first output node N is connected to the second output terminal OT of the delay part the second end portion E of the resistor R a first end portion E of the capacitor C and the first electrode EE of the transistor . The second output node N is connected to the output T of the amplifier and the control electrode CE of the transistor .

Referring to in a condition in which the voltage generating circuit is turned off when the main voltage VIN is initially applied from the external system the voltage generating circuit receives the main voltage VIN.

The voltage dividing part divides the main voltage VIN such that the driving voltages for driving the driver circuits of the display apparatus are generated.

For example the voltage dividing part outputs the driving voltage TVDD of the high level to drive the timing control part .

The discharge part receives the driving voltage TVDD of the high level. The inverting input T of the amplifier receives the driving voltage TVDD of the high level and the non inverting input T of the amplifier receives a signal of the low level. The voltage generating circuit is in a turn off state before being received the main voltage VIN such that the reset terminal REST of the timing control part initially has a low level. Thus the non inverting input T of the amplifier receives the signal of the low level. The amplifier is operated as the non inverting amplifier such that an output signal has the low level that is a same phase as the low level of the signal applied to the non inverting input T.

The second output node N receives the output signal of the low level. The control electrode CE of the transistor which is connected to the second output node N receives the output signal of the low level such that the transistor is turned off in response to the output signal of the low level. Thus the discharge part is in a turn off state.

The delay part receives the driving voltage TVDD of the high level. The driving voltage TVDD of the high level is delayed by the predetermined period corresponding to the RC time constant of the delay part and then is applied to a reset terminal REST of the timing control part through the second output terminal OT. Thus the reset terminal REST receives the reset voltage of the high level. The timing control part is reset in response to the reset voltage of the high level received from the reset terminal REST.

Referring to in a condition in which the voltage generating circuit is turned off when the main voltage VIN is blocked from the external system the voltage generating circuit does not receive the main voltage VIN.

Therefore the discharge part receives the signal of the low level. That is the inverting input T of the amplifier receives the signal of the low level and the non inverting input T of the amplifier receives the signal of the high level. The voltage generating circuit is in a turn on state before being blocked the main voltage VIN such that the reset terminal REST of the timing control part has the high level. Thus the non inverting input T of the amplifier receives the signal of the high level. The amplifier is operated as the non inverting amplifier and thus outputs an output signal which has the high level that is a same phase as the high level of the signal applied to the non inverting input T.

The second output node N receives the output signal of the high level. The control electrode CE of the transistor which is connected the second output node N receives the output signal of the high level such that the transistor is turned on in response to the output signal of the high level. Thus the transistor discharges the signal of the high level applied to the first electrode EE to the ground connected to the second electrode EE. Therefore a voltage charged in the capacitor C of the delay part may be discharged to the ground through the transistor quickly.

In addition the voltage charged in the capacitor C may be discharged to the reset terminal REST of the timing control part and the first output terminal OT of the voltage dividing part .

In an exemplary embodiment when the main voltage VIN is blocked a voltage charged in the capacitor C may be discharged through the transistor as well as the reset terminal REST of the timing control part and the first output terminal OT of the voltage dividing part . As described above the voltage charged in the capacitor C may be discharged through a plurality of discharge passes such that a discharge time may be decreased. Therefore the voltage of the reset terminal REST may be quickly discharged to a predetermined voltage for example to a ground GND and then the timing control part may be normally driven.

In general the main voltage VIN received from the external system has a high level and is stabilized by a stabilization circuit which includes a plurality of capacitors. When the main voltage VIN is blocked a falling time of the main voltage VIN during which the main voltage VIN falls from the high level to the low level becomes long due to the stabilization circuit. Thus the amplifier may be sufficiently driven by a remaining voltage which is lower than the main voltage. As explained above even when the main voltage VIN is blocked the discharge part may be normally driven.

In addition in an exemplary embodiment in the turn off state of the voltage generating circuit the discharge part may discharge the abnormal signal such as the electrostatic charge or a peak voltage of various signals charged in the capacitor C.

For example when the voltage generating circuit is in the turn off state while the main voltage VIN is applied to the display apparatus a method of discharging the abnormal signal charged in the capacitor C will be explained below.

The voltage generating circuit is in the turn off state and thus the inverting input T of the amplifier receives the signal of the low level and the non inverting input T of the amplifier receives the signal of the high level by the voltage charged in the capacitor C.

The amplifier is driven as the non inverting amplifier and thus outputs the signal of the high level which has a same phase as the high level of the signal applied to the non inverting input T.

The second output node N receives an output signal of the high level. The control electrode CE of the transistor which is connected to the second output node N receives the output signal of the high level such that the transistor is turned on in response to the output signal of the high level. The transistor is turned on and thus the signal of the high level which is applied to the first electrode EE is discharged to the ground which is connected to the second electrode EE. As described above the voltage charged in the capacitor C of the delay part may be discharged to the ground through the transistor .

In addition the voltage charged in the capacitor C may be discharged to the reset terminal REST of the timing control part and the first output terminal OT of the voltage dividing part .

According to an exemplary embodiment a false operation of the driver circuit may be prevented by the abnormal signal. For example when the abnormal signal is charged in the capacitor C an operation of the driver circuit may be different from the operation sequence as intended. In this case the discharge part according to an exemplary embodiment may prevent from the false operation of the driver circuit.

Referring to a voltage generating circuit according to an exemplary embodiment includes the substantially same or like parts as those described in the previous exemplary embodiments except for a transistor.

The voltage generating circuit may include a voltage dividing part a discharge part and a delay part .

The voltage dividing part may include a resistor string . The voltage dividing part is configured to divide a main voltage VIN received from an external system into a plurality of driving voltages and to output the driving voltages having different levels.

Hereinafter the voltage generating circuit will be explained referring to a driving voltage TVDD applied to the timing control part . As shown in a first output terminal OT of the voltage dividing part is configured to output the driving voltage TVDD.

The amplifier may be a non inverting amplifier. The amplifier includes a negative power supply T an inverting input T a non inverting input T a positive power supply T and an output T. The negative power supply T is connected to a ground GND the inverting input T is connected to the first output terminal OT of the voltage dividing part and the non inverting input T is connected to a second output terminal OT of the delay part . The positive power supply T is configured to receive a main voltage VIN and the output T is configured to output an output signal corresponding to a signal applied to the non inverting input T. The second output terminal OT of the delay part is configured to output a reset voltage for resetting the timing control part .

In an exemplary embodiment the amplifier outputs a non inverted signal which has a same phase as the signal applied to the non inverting input T through the output T.

The transistor include a control electrode CE which is connected to the output T of the amplifier via resistor a first electrode EE which is connected to the second output terminal OT of the delay part and a second electrode EE which is connected to the ground GND. The transistor may be a NMOS transistor.

The delay part may include a resistor R and a capacitor C which is connected to the resistor R. For example the delay part may have a RC time constant corresponding to a driving sequence of the driver circuits. The resistor R includes a first end portion E which is connected to the first output terminal OT of the voltage dividing part and a second end portion E which is connected to the second output terminal OT of the delay part . The capacitor C includes a first end portion E which is connected to the second output terminal OT of the delay part and a second end portion E which is connected to the ground GND. The second output terminal OT of the delay part is connected to a reset terminal REST of the timing control part .

A first output node N is connected to the second output terminal OT of the delay part the second end portion E of the resistor R a first end portion E of the capacitor C and the first electrode EE of the transistor . The second output node N is connected to the output T of the amplifier and the control electrode CE of the transistor .

A method of driving the voltage generating circuit according to an exemplary embodiment may be the substantially same as those described in the previous exemplary embodiment referring to and the same detailed explanations are not repeated unless necessary.

The voltage generating circuit according to an exemplary embodiment is the same as that shown in and the voltage generating circuit according to a comparative embodiment omits the discharge part from the voltage generating circuit according to an exemplary embodiment.

Referring to Table and according to the comparative embodiment a rising time of the reset voltage RS with respect to that of the main voltage VIN is about 7.1 ms. Referring to Table and according to the comparative embodiment a falling time of the reset voltage RS with respect to that of the main voltage VIN is about 1.2 ms.

In contrast referring to Table and according to the exemplary embodiment the rising time of the reset voltage RS with respect to that of the main voltage VIN is about 6.9 ms. Referring to Table and according to the exemplary embodiment a falling time of the reset voltage RS with respect to that of the main voltage VIN is about 0.15 ms.

As described above the rising time of the reset voltage RS according to the exemplary embodiment may be similar to the rising time of the reset voltage RS according to the comparative embodiment. However the falling time of the reset voltage RS according to the exemplary embodiment may be reduced tenfold than the falling time of the reset voltage RS according to the comparative embodiment.

As described above the driver circuit is referred to as the timing control part but the driver circuit may correspond to all driver circuits applied to the driving voltages which are generated from the voltage generating circuit. In addition the discharge part may be connected to various terminals of the driver circuit which is required to quickly discharge as well as the reset terminal.

According to exemplary embodiments of the invention when the main voltage is blocked the voltage charged in the capacitor of the delay part may be discharged quickly. In addition the abnormal signal charged in the capacitor may be discharged quickly. Therefore a driving reliability of the display apparatus may be improved.

The foregoing is illustrative of the inventive concept and is not to be construed as limiting the scope of the inventive concept. Although a few exemplary embodiments of the inventive concept have been described those skilled in the art will readily appreciate that many modifications are possible in the exemplary embodiments without materially departing from the novel teachings and advantages of the inventive concept. Accordingly all such modifications are intended to be included within the scope of the inventive concept as defined in the claims. In the claims means plus function clauses are intended to cover the structures described herein as performing the recited function and not only structural equivalents but also equivalent structures. Therefore it is to be understood that the foregoing is illustrative of the inventive concept and is not to be construed as limited to the specific exemplary embodiments disclosed and that modifications to the disclosed exemplary embodiments as well as other exemplary embodiments are intended to be included within the scope of the appended claims. The inventive concept is defined by the following claims with equivalents of the claims to be included therein.

