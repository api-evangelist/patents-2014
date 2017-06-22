---

title: Non-integer oversampled timing recovery for higher order quadrature modulation communication systems using quadrature-phase samples
abstract: Apparatus and method for performing entirely digital timing recovery for high bandwidth radio frequency communications. The received digital data source can be sampled from any (minimum 2×) non-integer oversampled transmitted data. This method re-samples the data through interpolation and phase adjustment. The output phase error adjusts the receiver's Analog-to-digital Convertor sampling clock to improve synchronization with the transmitter's Digital-to-analog Convertor clock phase, thus improving transmitted symbol recovery.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09319217&OS=09319217&RS=09319217
owner: The United States of America as represented by the Secretary of the Air Force
number: 09319217
owner_city: Washington
owner_country: US
publication_date: 20141028
---
The invention described herein may be manufactured and used by or for the Government for governmental purposes without the payment of any royalty thereon.

This invention relates generally to timing recovery of higher order modulated radio frequency communications and more specifically to such radio frequency communications systems wherein the digital to analog and analog to digital conversion oversampling frequencies required to properly synchronize phase becomes excessively expensive due to the bandwidth requirements associated with a radio frequency waveform or lack of frequency tunability. This invention also relates to the field of digital interpolation of non coherent sampled signals.

The Digital to analog convertor DAC samples at a specific typically rising edge of a clock that is as close in phase to the modulation clock as possible. To assist in determining the phase of the clock without a known sequence non data aided transmitted communications systems typically oversample the signal and perform analog recovery loops or digital timing recovery schemes. The majority of digital timing recovery schemes require a minimum oversampling of twice though some require 4 the symbol rate. Furthermore these techniques further restrict oversampling to an integer multiple. Many system requirements desired throughput bit error rate bandwidth drive derived requirements that may preclude component selection analog filters due to pass bands digital boards with inadequate clock frequencies etc. . Ultimately the choice of available hardware may prevent the transmitter receiver pair from operating with an integer multiple sampling factor. Decimal oversampling at the transmitter would render many digital timing recovery techniques useless. In addition many timing recovery schemes are not suited for higher order modulations i.e. 16 Quadrature Amplitude Modulation 16 QAM as they rely on zero crossings for phase error calculations and sampling adjustments.

An optimal solution to the timing recovery of received signals is a reconfigurable all digital scheme capable of analyzing and adjusting incoming symbols oversampled at any decimal value at or above 2 . Feedback can be given to the Analog to Digital convertor s clock via a numerical controlled oscillator but results shown for 16 QAM recovery compensate on a free running clock without feedback. The prior art has been able to isolate each of these parameters independently but has failed to optimize for all parameters at once without expansive processing. Specifically the prior art still either uses analog recovery loops prone to component tolerances or complex memory and processing intensive interpolation and decimation schemes.

In A BPSK QPSK Timing Error Detector for Sampled Receivers a digital timing recovery scheme is proposed that has served as the basis for many digital synchronization techniques. This requires integer multiple oversampling of a Binary Phase Shift Keying or Quadrature Phase Shift Keying modulation both of which do not apply to the problem this invention intends to solve.

In U.S. Pat. No. 5 495 203 a QAM demodulator with non integer sampling is used to interpolate and then decimate an incoming signal. The resampled signal is fed into a control loop to recover the data rate and continuously tunes interpolation and decimation until locked to the intended data. A limitation to this approach potentially is the complexity of the interpolation and decimation values to approximate oversampling rates needed.

In U.S. Pat. No. 5 878 088 a variable symbol timing recovery scheme is proposed with two stage interpolation and decimation controlled by multiplexors and based on the phase error within the control loop. This allows the system to increase or decrease the level of granularity needed to estimate the QAM symbol data and adjust a numerically controlled oscillator as needed. However this invention may be affected by excessive delay and control overhead to synchronize the varying interpolation and decimation stages.

In U.S. Pat. No. 6 295 325 an arbitrary oversampling timing recovery loop is proposed. The invention is capable of taking any symbol data rate and oversample by an integer multiple. The flexibility of the oversampling is convenient but a situation where the oversampling frequency is not an integer multiple of the symbol data rate is an issue.

In U.S. Pat. No. 6 854 002 an analog high speed interpolation apparatus is proposed allowing for low latency corrections of the oversampling of a received signal within a timing recovery loop. While a promising invention the necessity for complex and expensive analog components is a limiting factor.

In U.S. Pat. No. 7 149 265 a timing recovery loop is proposed with reconfigurable non integer oversampling. A configurable number of parallel elements examine whether a delay is occurring from the previous sample within the same element and if a shift is found within that sampling cycle element to element and adjust a counter to numerically control incoming samples. This invention requires the sample rate to be a rational number p q where the number of parallel elements N is an integer factor of q. This restricts the selection of p and q thus the selection of the sampling frequency which may be limited to the system hardware.

It is therefore an object of the present invention to provide an apparatus and method that overcomes the prior art s dependency on highly specialized and high complexity ADC and DAC component pairs and processes therein to perform up sampling at integer multiples of the system s symbol rate to enable digital timing recovery.

It is a further object of the present invention to eliminate DAC sampling frequency configuration to properly oversample a system s symbol rate.

It is still a further object of the present invention to provide an apparatus and method wherein an entirely digital timing recovery scheme adjusts DAC sampling eliminating phase error noise introduced by analog components.

It is yet still a further object of the present invention to provide an apparatus and method that is capable of decimal oversampling factors without extensive interpolation and decimation components or logic.

An additional object of the present invention is to provide a means to recover symbols transmitted through higher order modulations i.e. 16 QAM .

Briefly stated the present invention achieves these and other objects through the digital calculation of phase error from sampled data and manipulation of clock phase driving the ADC. Initially the phase which drives the moment when the ADC samples the incoming analog signal will he unsynchronized with the transmitter DAC phase. As the digital timing recovery executes the phase error difference between the desired phase and the current sampling phase at the receiver is calculated based on previous samples. A positive trend in symbol magnitude indicates sampling is occurring too late therefore the phase of the sampling clock should be shifted to the left. Conversely a negative trend indicates sampling is occurring too early and the sampling clock phase should be shifted to the right. This process is continually updating phase as necessary to track phase drift caused by system components or environment impairments.

To achieve timing recovery within a higher order modulation system i.e. 16 QAM with non integer oversampling an efficient calculation of the phase error must occur from a digital data source. For proper execution of this process a precise sampling rate must be known of both the transmitter and receiver. There are no requirements on the two values but it is recognized the exact decimal ratio may not be realizable within hardware i.e. a Field Programmable Gate Array . This is in contrast to the prior art which either requires integer values and limits the system to integer oversampling or utilizes large interpolation and decimation values at the receiver to operate on a subset of non integer oversampling scenarios. Furthermore the majority of prior art operates within binary modulated systems. Nothing in the prior art proposes the flexibility of the present invention.

Therefore it is accurate to say that present invention 1 can ensure recovery of a received oversampled waveform as prior art requires to achieve the same 2 can ensure recovery of a received higher order modulated waveform as prior art requires to achieve the same and 3 can ensure recovery of a received non integer oversampled higher order modulated waveform directly from ADC digital samples while reducing requirements on DAC and ADC sampling frequencies. As such the present invention represents a significant departure from prior art methods.

According to an embodiment of the invention apparatus for performing digital timing recovery comprises software or an FPGA or similar parallel signal processing chip a DAC capable of sufficiently sampling the digital data stream and an ADC capable of sufficiently sampling the received waveform.

The above and other objects features and advantages of the present invention will become apparent from the following description read in conjunction with the accompanying drawings in which like reference numerals designate the same elements.

Referring to the key components of the invention include the digital data source the timing recovery system and the interpolation symbol update . The digital data source is assumed to be the analog to digital convertor sampling the radio frequency input from the receiver antenna at a sampling rate Fand has no bearing on the invention. The timing recovery system is broken down further into the buffering of incoming data the update gain learning factor the timing recovery logic and Lowpass filter .

Still referring to the digital data source consists of in phase I and quadrature phase Q components and respectively. These symbols are buffered a minimum N samples where

Referring to which describes the timing recovery logic the buffered I and Q samples are evaluated by the signum function such that 

This results in arrays being output at and at respectively. The previously calculated phase error is fed into the index calculation logic to determine the sampling indices for the start t center t and end t of the incoming symbol within the arrays at and at . The indices are calculated as follows 

where k is a counter of which symbol is being sampled within the buffer and is the previous symbol phase error present at . The three real valued numbers calculated within index calculation logic form array at which are fed into sampling blocks . Here the arrays at and at are interpolated and sampled approximately at sampled indices to the best ability of the host hardware to form I and Q samples respectively. Each of the I and Q samples are combined in to form a three element complex array output at consisting of start x center x and end x symbols defined as .

Still referring to the three element complex array output at of the I Q combiner is fed into the phase error calculator to determine the amount and direction early or late of phase offset within this sampling iteration. The current phase offset output at is calculated by 

where is the real portion of a complex number and is the complex conjugate. Finally the previous phase offset at current phase offset at and update gain at are fed into the phase adjustment block . If the difference between previous phase offset at and current phase offset at is above a system defined threshold T the phase adjustment at is adjusted accordingly to yield an output at i.e. 

The output of this calculation becomes the new previous phase offset value identified in and for the next incoming symbol.

If hardware resources cannot be given to complete the calculations within a simplified process that requires calculations within I samples or Q samples can be implemented demonstrated within and respectively. There is a potential penalty in tracking latency which results in higher Error Vector Magnitude EVM values when utilizing only I or Q samples. An example test shown in demonstrates no negative effects on EVM for N 2 oversampled system.

Referring to which describes the timing recovery logic the buffered I samples are evaluated by the signum function such that 

This results in an array at . The previously calculated phase offset at is fed into the index calculation logic to determine the sampling indices for the start t center t and end t of the incoming symbol within the array at . The indices are calculated as follows 

Still referring to the output of the sampler is fed into the phase error calculator to determine the amount and direction early or late of phase offset within this sampling iteration. The phase error at is calculated by 

The output of this calculation becomes the new phase offset at value identified in and for the next incoming symbol.

Referring to which describes the timing recovery logic the buffered Q samples are evaluated by the signum function such that 

This results in an array at . The previously calculated phase error at is fed into the index calculation logic to determine the sampling indices for the start t center t and end t of the incoming symbol within an array at . The indices are calculated as follows 

Still referring to the output of the sampler is fed into the phase error calculator to determine the amount and direction early or late of phase offset within this sampling iteration. The phase error at is calculated by 

The output of this calculation becomes the new phase offset value identified in and for the next incoming symbol.

Referring to the four constellation plots represent the received symbol values in terms of I and Q amplitudes. The lighter dots indicated the desired symbol locations for perfect symbol recovery. The darker dots are the values with the respective recovery scheme. In a the best genie sample location was selected to minimize EVM the best for the incoming data in b the proposed method for timing recovery utilizing I and Q samples together is given in c and d the proposed method for timing recovery utilizing I samples only and Q samples only respectively is given. In this case no penalty is realized for utilizing the real or imaginary samples exclusively.

Having described preferred embodiments of the invention with reference to the accompanying drawings it is to be understood that the invention is not limited to those precise embodiments and that various changes and modifications may be effected therein by one skilled in the art without departing from the scope or spirit of the invention as defined in the appended claims.

