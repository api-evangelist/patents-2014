---

title: Random number generator using ring oscillators with initial delay
abstract: Apparatus and method for a ring oscillator based random number generator with intentional startup delays timed for each ring to provide a uniform initial spreading of the ring oscillator transition edges. This invention adds a controlled incremental delay in the startup of each individual ring within the ring oscillator random number generator. Typically the delay units used in the ring oscillators themselves can be used to get a course delay between the start times of each ring. A subset of the rings start up with a particular course delay and different fine delays such that the transition edges of all the rings are spread out over the oscillation period. This spreading of the transition edges ensures the output of the random number generator are not a predictable sequence of ones and zeros based on a simultaneous startup of all rings at the same time.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09361066&OS=09361066&RS=09361066
owner: The United States of America as represented by the Secretary of the Air Force.
number: 09361066
owner_city: Washington
owner_country: US
publication_date: 20140109
---
This patent application claims the priority benefit of the filing date of provisional application Ser. No. 61 817 368 having been filed in the United States Patent and Trademark Office on Apr. 30 2013 and now incorporated by reference herein.

The invention described herein may be manufactured and used by or for the Government for governmental purposes without the payment of any royalty thereon.

One method of generating a random number on a digital integrated circuit is to use a number of ring oscillators typically an odd number of digital inverters connected in a loop with their outputs latched and those latched values having an XOR function performed on them. If the individual ring oscillators have different phases the output cannot be predicted because the capture of the current output state 0 or 1 by the latches will include capturing of some transitioning edges. The results of those that are transitioning will not be predictable due to noise. Prior art designs have relied on random circuit variations unintentionally created during manufacturing to ensure the ring oscillators have slightly different phases between each of the many ring oscillators in the design.

The individual ring oscillators in the prior art typically have circuitry to enable or inhibit their oscillation. There is a possibility that when they are first started the rings may be similar enough that the latching and XORing function will catch a consistent set of all zeros or all ones or behave in a predictable manner delivering a predictable output stream for some period of time.

It is therefore an object of the present invention to provide an apparatus and method that overcomes the prior art s limitations by intentionally staggering the startup of the ring oscillators across one or more of their oscillation cycles by including a delay circuit between each ring oscillator s enable signal and the next ring oscillator s enable signal. Even if each ring oscillator is very similar their intentional offset in starting up will help ensure the bits generated are random.

Referring to the key components of a prior art ring oscillator random number generator are shown. An odd number of inverters shown in the top most ring oscillator are connected in a loop that includes an AND gate used to enable the ring oscillator. When AND gate has a 1 on input the looped back ring consisting of driving driving driving driving driving AND gate input will oscillate. The oscillation period is twice the propagation delay time through the looped circuitry since two passes through the loop are required to return to the original value.

Still referring to the output of each ring is captured by flip flops through which are clocked at a much slower frequency than the ring oscillator s frequency. The outputs of flip flops through are processed through XOR gates through . The output will be random if any one or more of the flip flops through are random. A major source of true randomness is generated from capturing a transitioning edge at the input to the flip flops through .

Referring to the delay cells through provide a delay that increases with ring number in the enable signal s arrival at AND gate inputs through . By delaying the individual ring enable signals through the startup time of the individual rings is staggered ensuring the transitioning edges are spread out over the oscillation cycle. Having equally distributed transitions helps ensure some of the values latched in flip flops through are random.

Referring to the time delays on the enable signals through of each successive ring oscillator are shown delayed over one oscillation time period of the rings. Below each of the enable signals through the inputs to flip flops through are shown as D D through D.

Having described preferred embodiments of the invention with reference to the accompanying drawings it is to be understood that the invention is not limited to those precise embodiments and that various changes and modifications may be effected therein by one skilled in the art without departing from the scope or spirit of the invention as defined in the appended claims.

