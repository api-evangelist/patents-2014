---

title: Distributive transmissometer
abstract: A distributive transmissometer, comprising a series of light sources that illuminate and map out a volume of space to be sampled to a one-dimensional space, a light detector, the one-dimensional space being mapped to the light detector such that spatial dust density distribution of the volume to be sampled can be determined; and, a lens for focusing light emitted by the light sources toward the light detector.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09164035&OS=09164035&RS=09164035
owner: The United States of America as represented by the Secretary of the Navy
number: 09164035
owner_city: Washington
owner_country: US
publication_date: 20140218
---
The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without payment of any royalties thereon or therefor.

A transmissometer may be described as but without limitation an instrument for measuring the extinction coefficient of the atmosphere and for the determination of visual range. A tranmissometer typically operates by sending a narrow collimated beam of energy usually a laser through a propagation medium. A narrow field of view receiver at the designated measurement distance determines how much energy is arriving at the detector and determines the path transmission and or extinction coefficient. Transmissometers may be referred to but without limitation as telephotometers transmittance meters or hazemeters.

Currently there is no commercial apparatus available to provide real time spatial dust density distribution in a large volume. Point sampling transmissometers are sometimes used however the spatial samplings from these types of transmissometers are finite and typically limited by beam and detector size. Additionally the spatial resolution provided by point sampling transmissometers is limited.

The present invention is directed to a distributive transmissometer that meets the needs enumerated above and below.

The present invention is directed to a distributive transmissometer which includes a series of light emitting diodes an imaging device and a lens. The series of light emitting diodes illuminate and map out a volume of space to be sampled to a one dimensional space. The one dimensional space is mapped to the imaging device such that spatial dust density distribution of the volume to be sampled can be determined The lens is for focusing light emitted by the light emitting diodes toward the imaging device.

It is a feature of the present invention to provide a distributive transmissometer which provides real time spatial dust density distribution in a large volume.

It is a feature of the present invention to provide a distributive transmissometer with good spatial resolution.

The preferred embodiments of the present invention are illustrated by way of example below and in . As shown in a distributive transmissometer includes a series of light sources a light detector system or imaging device and a lens . The series of light sources illuminate and map out a volume of space to be sampled to a one dimensional space. The one dimensional space is mapped to the light detector system such that spatial dust density distribution of the volume to be sampled can be determined The lens is for focusing light emitted by the light sources toward the light detector system .

In the description of the present invention the invention will be discussed in a military environment however this invention can be utilized for any type of application that requires use of transmissometer.

The series of light sources may be a series of light emitting diodes constructed using a series of LED LASER light sources to reference a volume of space being interrogated. The light detector is a system which measures the intensity of the series of light sources for each section of spatial volume under investigation without any obscurant scatter being present. The light detector system may be but without limitation an imaging system such as a CCD camera. The measurement obtained by the light detector system is now the baseline intensity measurement for what is called a Clear Air sample. As obscurant particulate is being introduced to these spatial volumes the light intensities would diminish. Even as the light intensities diminish the light detector system will continue to sample the spatial volumes for their new intensities values.

With the new intensities and baseline intensity values the transmittance values for each spatial volume is calculated I I . From the transmittance value and the known distance of the light source to the light detector system the quantity of particulates in each volume is calculated. This relationship is given by Beer Lamberet s Law shown in Equation 1 below 

where T is the transmittance measured by the transmissometer is the mass extinction coefficient C is the concentration of obscurant particulate in that volume at a distance L from the detector system. The mass extinction coefficient term is determined experimentally but remains static for the remainder of measurements in this environment. Knowing the transmittance the mass extinction coefficient and the distance from the light sources are from the light detector system the concentration of obscurant particulates may be calculated determining the spatial dust density distribution of the volume to be sampled.

In one of the embodiments of the invention the physical implementation of this system is to use a point like source such as a LED LASER and let the beam diverge as it samples the volume that it is propagating through. This spatial sampling is then recorded with an imaging system such as CCD array that records the spatial intensity for said volume. By multiplexing through the LEDS LASERS array a spatial map of the transmittance is then created using the baseline values and the newly acquired intensities. From these transmittance measurements the concentration for each spatial volume is then determined These measurements are taken real time with no perturbation of the environmental conditions.

The reason that the LED LASERs are multiplexed is to eliminate the cross talk between spatial volumes being sampled. Additionally this provides more detector surface used to gather light intensity for each volume. It can also be used to cut down on the background noise introduced by the ambient environment. In this particular situation the bias on said detector system can be turned on when only a LED LASER is turned on.

The results of each LED LASER strobed unto the CCD array are stored onto bitmaps. The ratio of the new intensities and clear air intensities from these bitmap provides the transmittance value. The reason bitmaps are chosen is bitmaps capture each pixel on the camera digital value that represents the intensity that that the pixel is exposed to. In essence the camera is acting like a power meter with a digitizer. Because we are not interested in the absolute power measurement this method of digitizing the optical power measurement is sufficient to determine the mass concentration.

When introducing elements of the present invention or the preferred embodiment s thereof the articles a an the and said are intended to mean there are one or more of the elements. The terms comprising including and having are intended to be inclusive and mean that there may be additional elements other than the listed elements.

Although the present invention has been described in considerable detail with reference to certain preferred embodiments thereof other embodiments are possible. Therefore the spirit and scope of the appended claims should not be limited to the description of the preferred embodiment s contained herein.

