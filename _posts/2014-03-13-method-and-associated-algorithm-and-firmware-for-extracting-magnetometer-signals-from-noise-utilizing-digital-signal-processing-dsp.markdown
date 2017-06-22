---

title: Method and associated algorithm and firmware for extracting magnetometer signals from noise utilizing digital signal processing (DSP)
abstract: A compact, computationally-efficient, firmware-resident version of a DSP autocorrelation function, extracts periodic information from noise-corrupted signals. The function adapts autocorrelation parameters in real-time either autonomously or via up-link commands from a ground-based system. The function calculates specific determination values that optimize the performance of the autocorrelation process for a specific application. The per-bit multiplication used by the function can be performed by logically ANDing each of the respective samples in the two arrays. The summation of the per-bit multiplication is an integer summation, rather than the more time-consuming floating-point summation. A further aspect of the present function is the utilization of a threshold detection process to discretize the correlation output estimate to a one-bit binary sample.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09471543&OS=09471543&RS=09471543
owner: The United States of America as Represented by the Secretary of the Army
number: 09471543
owner_city: Washington
owner_country: US
publication_date: 20140313
---
The invention described herein may be manufactured and used by or for the Government of the United States for governmental purposes without the payment of any royalties thereon.

The present invention relates to the field of computing devices and particularly relates to an automated digital signal processing DSP autocorrelation algorithm or function that significantly reduces the corrupting effects of interference on a sensor. More specifically the autocorrelation algorithm may be used on board a projectile in a very highly efficient manner with minimal impact on the on board computational energy and payload resources.

The magnetometer sensor on a spinning projectile is used to determine the projectile roll aspect angle with respect to the earth magnetic vector. Modern smart weapon technology requires great accuracy from this and similar sensors. The magnetic sensor requires relatively high gain low noise circuitry in order to produce clean reliable magnetic vector crossing data to the on board processor.

The high gain requirement of the magnetic sensor renders it susceptible to corrupting interference from a number of outside sources. The sources of interference can range from on board currents and voltages electromagnetic radiation within the projectile unintentional off board electromagnetic radiation emitters and intentional disruptive sources.

Therefore a need arises for a digital signal processing DSP autocorrelation algorithm that would significantly reduce the corrupting effects of interference. The algorithm would perform its sensing task while being compact computationally efficient. It would utilize mostly simple binary operations and some limited integer mathematics. As such the algorithm would be highly time efficient with minimal impact on limited on board computational and energy resources. The need for such a DSP autocorrelation algorithm has heretofore remained unsatisfied.

The present invention addresses the concerns related to interferences on sensors and presents a new autocorrelation function that could be implemented by an algorithm i.e. software hardware and or firmware . The autocorrelation function is useful for extracting periodic information from noise corrupted signals because of two of its unique properties.

The first property is that the autocorrelation of a periodic i.e. coherent signal has the same period as the signal.

The second property is that the autocorrelation of white i.e. Gaussian noise is zero except for a Dirac Delta Function peak at t 0.

The continuous form of an autocorrelation Rff of signal f t with lag can be expressed by the following equation 

Since the data in this application is a time sampled real function a simplified discrete time autocorrelation expression can be used.

For a discrete time process of length n defined as X X X . . . X with known mean and variance the estimate of the discrete autocorrelation is expressed by the following equation 

Because the magnetometer signal has some unique properties and a known range of expected periodicity and amplitude the discrete time autocorrelation estimate can be further simplified and expressed by the following equation 

The magnetometer signal available to this process is a binary signal its amplitude is quantized to either a logical zero or a one so it can be considered to be discretely quantized in amplitude and continuous in time. Because of the signal characteristics the actual correlation process can at its minimal form include an integer summation of a finite series of by term binary one bit logical ANDing operations.

With specific knowledge of the nature of the magnetometer signal and of the expected interference the size of the autocorrelation extent i k . . . i . . . i k 2k 1 can be selected to enhance the desired signal while suppressing the interference. The autocorrelation extent is selected so as to enhance the inherent periodicity i.e. coherence of the desired signal.

A similar selection is required for 1 the autocorrelation lag value which is selected to enhance the randomness i.e. incoherence of the undesired interference. The best combination of k and l will provide optimal results for this specific application. As used herein optimal results enhance the desired signal while suppressing the interfering signal and its corrupting effects on the desired signal to a negligible level.

The autocorrelation algorithm can be implemented in an existing on board field programmable gate array FPGA a microprocessor or on a DSP integrated circuit.

Additional aspects of the present invention will be set forth in part in the description which follows and in part will be obvious from the description or may be learned by practice of the invention. The aspects of the invention will be realized and attained by means of the elements and combinations particularly pointed out in the appended claims. It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory only and are not restrictive of the invention as claimed.

The present invention provides a novel and non obvious automated digital signal processing DSP autocorrelation algorithm that significantly reduces the corrupting effects of interference on a sensor. More specifically the autocorrelation algorithm may be used on board a projectile in a very highly efficient manner with minimal impact on the on board computational energy and payload resources. The process computer program product and the associated system are collectively referred to herein as the algorithm the process the method the system the function or the computer program product .

The sensor conditioning module is known in the field and generally performs the following functions analog amplification filtering squaring and level shifting of the magnetometer output for input into the processor .

The on board processor may be or its function may be implemented for example by an off chip such as a microcontroller a microprocessor a Digital Signal Processor DSP or a Field Programmable Gate Array FPGA a microcontroller or a microprocessor and or by an on chip non volatile RAM or ROM.

To this end the DSP autocorrelation algorithm changes the duty ratio on to off time of the desired magnetometer but since the positive going edge is used to determine roll orientation its purity and stability are important parameters. By selecting the signal sampling rate and adjusting the values of k and l in the above equation 3 the autocorrelation can be tuned to accommodate a wide range of desired and corrupting signal combinations.

A further aspect of the present invention is to provide the ability to adapt the DSP autocorrelation algorithm parameters in real time within the on board processor either autonomously or via up link commands from a ground based system.

The foregoing equation 3 describes the mathematical operations performed by the DSP autocorrelation algorithm and executed by the processor to perform the simplified discrete time autocorrelation operation.

The magnetometer signal is sampled at a specific rate that is fast enough to update the samples in order to accurately define the time position of a transition in amplitude but sufficiently slow to allow the on board processor to perform the simplified discrete time autocorrelation for each new sample before the next sample is acquired. Otherwise the autocorrelation output estimate will not be updated in real time defined as processing time that is less than or equal to the time between successive samples .

An exemplary train of the sampled magnetometer signal is illustrated in . The DSP autocorrelation algorithm effectively removes the corrupting noise or reduces it to a level that is no longer significant in order to generate the desired autocorrelation output signal .

The autocorrelation as embodied in equation 3 requires 2k l samples to be acquired before the first autocorrelation estimate output is made available. The time to acquire these samples defines the startup time. The first k 1 samples are not necessarily updated by the DSP autocorrelation algorithm since the process requires a symmetric array of k samples on each side of the sample to be updated. The sample to be updated by the autocorrelation is the nsample in the train.

Once 2k l samples are acquired each successive sample can be updated by the DSP autocorrelation algorithm . An aspect of the present invention is to determine the specific determination values of k and l that optimize the performance of the autocorrelation process for a specific application.

The DSP autocorrelation algorithm performs a discrete time autocorrelation DTA process which is illustrated in . The DTA process requires two arrays or sequences of data. The first array includes a sequence of 2k 1 samples Autocorrelation Ensemble centered on the nth sample . The second array includes a similarly sized array of samples Lagged Ensemble that is delayed by a lag 1 .

The signal available to the on board processor that is performing the DTA process is a binary amplitude either a logical 1 or 0 continuous time signal as shown of . The conditioned magnetometer signal is sampled by the on board processor to produce a sequence of one bit binary samples.

The DTA process requires a per sample multiplication of the two arrays as depicted in . That multiplication will produce an array of 2k 1 values. One of the aspects of the present invention is that this per bit multiplication can be performed by logically ANDing each of the respective samples in the two arrays Autocorrelation Ensemble and Lagged Ensemble to result in a single array with conditions .

The DTA process also requires summing all of the products of the per bit ANDing rather than performing a more time consuming binary or floating point multiplication. Another aspect of the present invention is that this summation is an integer summation rather than the more time consuming floating point summation.

A further aspect of the present invention is the utilization of a threshold detection process to discretize the correlation output estimate waveform to a one bit binary sample. The value of Vin a threshold detector can also be selectively tuned for specific applications.

Another embodiment of the present invention is the employment of an in place discrete time autocorrelation DTA process where a register space for only one data stream ensemble of length 2k 1 l is required. The DTA process starts by setting two index pointers that are separated by lag 1 .

The DTA process then examines the contents of samples n and n l. The contents of these samples are logically ANDed by an AND gate of the on board processor . The two index pointers advance sample by sample until the final samples of the ensemble 2k 1 and 2k 1 l have been ANDed by the AND gate .

A summation block of the on board processor integer sums the output of each ANDing for all 2k 1 operations. When the sum of all 2k 1 operations has been accomplished the final sum is subjected to a thresholding operation where the final output is assigned a logical one 1 if the sum is greater than or equal to a pre determined threshold value otherwise it is assigned a logical zero 0 if it is less than the threshold value.

When the summation exceeds the threshold value the indexing ANDing and summation may be terminated as a possible speed up measure since that data point value has been determined. The ANDing summation and thresholding steps are completed before the ensemble acquires a new data sample advances shifts all samples towards the end of the ensemble and discards the oldest sample.

The in place DTA process is again performed once for each new sample to produce an output data stream which is the best estimate of the desired signal without the corrupting signal. This process uses less on chip register space than a multi register embodiment.

As with all linear and causal processes there are inherent latencies and delays associated with these processes. More specifically as the magnetometer signal begins for example just after muzzle exit and bootup time the DTA process requires 2k l time samples to be acquired before its output is available. This delay is referred to as latency or pipeline delay. After that delay the DTA process continues on a per sample rate that is a new autocorrelation output for each sample advance .

The processing or computational delay must be less than or equal to the signal sampling rate in order for the output of the DSP autocorrelation algorithm to advance at a real time rate. For an exemplary application real time operation is essential. The latency or pipeline delay should be less than the time for one revolution of spin at the highest expected spin rate of the projectile. If the spin acceleration exceeds certain values spin acceleration compensation calculations and corrections are required as well.

Although k and 1 are expressed as integer sample numbers in the above equation 3 the absolute time values of k and 1 with respect to the signal time frequency characteristics are the controlling parameters of the DSP autocorrelation algorithm . Therefore they are dependent on the signal sampling rate and the unique characteristics of the desired and interfering signals. The sampling rate must be fast enough to adequately update changes in signal state with their required time accuracy while allowing enough inter sample time to perform the algorithm s calculations.

The Discrete Correlation Function as well as the Discrete Convolution Function can be implemented in either the time domain or the frequency domain. In the frequency domain both functions become similar by term multiplications of their discrete Fourier Transforms DFTs followed by an inverse DFT of the product. In the case of arrays that contain floating point values there is generally a break even point at an array size of approximately 256 samples where it becomes more computationally efficient to perform the correlation in the frequency domain. An example of a frequency domain correlation is shown in the following equation 4 

Where DFT represents the discrete Fourier Transform A is the autocorrelation ensemble and B is the lagged ensemble . The frequency domain version of convolution may appear to be much more computationally efficient than the time domain version for the anticipated array sizes. However upon considering the specifics of the particular magnetometer application the break even point occurs at much larger array sizes since the data arrays include one bit binary values per sample.

The mathematical operations include simple ANDing and accumulation of one fixed point integer where the DFT is calculated in at least a 32 bit or possibly a 64 bit numerical precision e.g. IEEE 754 binary floating point standard to avoid truncation errors from propagating through the DFT process and corrupting the results.

This is independent of the nature of the input array whether it is one bit binary or full precision floating point since the DFT array calculations internal to the process involve numerous sinusoidal coefficient multiplications and floating point additions. For computational efficiency within the DFT the two arrays are also 2long integral powers of 2 where in the time domain they can be of any length but for symmetry the length is an odd number 2k 1 .

The break even point in the specific application will be determined by the numerical precision of an off chip i.e. Field Programmable Gate Array FPGA Digital Signal Processor DSP microcontroller or microprocessor as well as by the nature of the math libraries used to implement the DFT processes. With the nature of the data one bit binary samples and with the array sizes expected to be utilized in this specific application the time domain implementation will prove to be more computationally efficient.

Although the present DSP autocorrelation algorithm has been described in connection with one exemplary application it should be clear that other modifications may be made to the DSP autocorrelation algorithm without departing from the spirit and scope of the present invention.

Embodiments of the present invention can take the form of an entirely hardware firmware or software or a combination thereof. In a preferred embodiment the invention is implemented in hardware. For the purposes of this description a computer usable or computer readable medium can be any apparatus that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device including but not limited to smart phones. The medium can be an electronic magnetic optical electromagnetic infrared or semiconductor system or apparatus or device or a propagation medium. Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

A data processing system suitable for storing and or executing program code will include at least one processor coupled directly or indirectly to memory elements through a system bus. The memory elements can include local memory employed during actual execution of the program code bulk storage and cache memories which provide temporary storage of at least some program code in order to reduce the number of times code must be retrieved from bulk storage during execution. Input output or I O devices including but not limited to keyboards displays pointing devices etc. can be coupled to the system either directly or through intervening I O controllers. Network adapters may also be coupled to the system to enable the data processing system to become coupled to other data processing systems or remote printers or storage devices through intervening private or public networks. Modems cable modem and Ethernet cards are just a few of the currently available types of network adapters.

