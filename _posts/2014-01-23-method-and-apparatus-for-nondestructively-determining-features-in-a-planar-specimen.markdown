---

title: Method and apparatus for non-destructively determining features in a planar specimen
abstract: A method and apparatus for non-destructively determining features in a planer specimen includes providing a heat impulse to the specimen, detecting temperatures in the specimen at a plurality of locations, and imaging the specimen from the detected temperatures. A laser can be used to provide a single or a plurality of heat impulses to the specimen. Temperatures in the specimen can be detected utilizing a contact sensor array or a remote infrared detector. These sensors are joined to a data processing device to image the specimen utilizing the detected temperatures.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09316604&OS=09316604&RS=09316604
owner: 
number: 09316604
owner_city: 
owner_country: 
publication_date: 20140123
---
The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties thereon or therefor.

The present invention is directed to non destructive testing and more particularly to a method for detecting microscopic structures within a specimen.

Optical microscopes are commonly used to discern small features embedded in specimens. Electron microscopes are also used to discern small features which can be imaged. Electron microscopes exhibit a significantly lower diffraction limit than optical microscopes because the wavelengths of electron beams are much smaller than wavelengths of light. However electron microscopes are much more expensive than optical microscopes and further require that the specimens be tested in a vacuum.

Photothermal frequency scan imaging is used for materials analysis in semiconductor manufacture. In photothermal frequency scan imaging a sample is subjected to a pulsed laser. This can be used to detect surface conditions of the sample but it has only been found to be effective for a limited depth in the sample. These methods have had problems with internal reflections in smaller samples. These methods have also been used as an indication of homogeneity within a sample and also for determining thermal properties within the sample. These methods have not been used to image individual discontinuities within a sample.

Accordingly it is an object of the present invention to provide a method and apparatus for detecting features embedded in specimens 

Another object is to provide method and apparatus that can detect features without subjecting the specimen to vacuum and

Yet another object is to provide a method and apparatus that can detect features without expensive equipment.

In view of these objects there is provided a method and apparatus for non destructively determining features in a planar specimen that includes providing a heat impulse to the specimen detecting temperatures in the specimen at a plurality of locations and imaging the specimen from the detected temperatures. A laser can be used to provide a single or a plurality of heat impulses to the specimen. Temperatures in the specimen can be detected utilizing a contact sensor array or a remote infrared detector. These sensors are joined to a data processing device to image the specimen utilizing the detected temperatures.

The transient conduction of heat is typically treated as a diffusion process however if the heat source is periodic in nature heat can propagate in a wavelike manner. This can be shown by examining the one dimensional transient heat conduction equation 

wherein is the thermal diffusivity T is the temperature t is time and x is the spatial dimension. If the temperature has a harmonic time dependence e.g. as a result of a pulsed laser then 2 wherein 2 f and f is the pulse frequency then equation 1 can be written in the form 

The above solution for T x t is analogous to the solution to the acoustic wave equation. However the propagation speed of these temperature waves is much slower than that of acoustic waves. Temperature waves propagate at 10 m s and acoustic waves propagate at 5 000 m s for most solids. Attenuation is also much higher for temperature waves than for acoustic waves.

Use of temperature waves gives advantages and disadvantages when compared with other types of radiation. Temperature waves are distinct from infrared IR waves which propagate at the speed of light. Many materials block infrared waves but even if the infrared waves are not blocked their wavelengths are much longer than those of the temperature waves and 10 nanometer resolution is impossible. Infrared sensors thus receive the same signal in each closely spaced sensor.

The formula for the wavenumber equation 5 implies that the propagation speed c square root over i a varies with the radial frequency . This means that the propagation speed associated with the higher frequency energy travels at a faster speed than that of the lower frequency energy. This can enable time gating of the signals that arrive at the thermistor array first to image features based on the highest frequency energy contained in a pulse. The highest frequency energy will also have the shortest wavelength. Significant high frequency energy can be contained by a single very short duration pulse. A pulse having a time duration T will contain significant energy at a frequency f 1 T .

For many thermally insulating materials the thermal diffusivity is on the order of 10m s. Thus using the above equations it can be shown that a laser sending a pulse having a duration T of 10 ns would lead to a wavelength on the order of 10 nm. This is better than the diffraction limit of optical microscopes. It can be improved upon further with a femtosecond pulse laser which would lead to a wavelength on the order of 1 nm. This is two orders of magnitude larger than the diffraction limit that can be achieved with electron microscopes. This method also avoids some of the negative features associated with electron microscopes e.g. their high cost and the necessity of putting the specimen into a vacuum.

In operation pulsed laser provides pulses of light to target location on specimen . Pulses of light cause an increase in temperature at target location . The temperature increase propagates to adjacent regions of specimen by well known heat transfer principles. Sensors of array measure the temperature of specimen at the region of contact with the sensor. The temperature waves propagating through the specimen will interact with discontinuity and propagate to the sensor array contact surface of the specimen . Processor collects the temperature measurements and provides an output indicative of temperature propagation through specimen . Processor can time gate the array output to prevent spurious signals caused by reflection of the temperature waves.

In a second embodiment temperature is measured at a multiplicity of locations on the first surface of specimen by an infrared temperature detector . Infrared temperature detector can be scanned across first surface to measure temperature at each location to be measured. Infrared temperature detector can be an infrared camera that images the entire first surface of specimen at once. Infrared temperature detector is joined to a processor for analysis. Using an infrared detector doesn t have the same limitations as trying to measure infrared propagation through the material however the detector must have sufficient resolution and precision to measure locations at intervals no greater than one half wavelength of the temperature waves.

This approach has the potential to resolve features on the order of nanometers giving a much higher resolution than that of optical microscopes. The specimen however must have a thickness no more than about 10 wavelengths of the temperature waves. For example temperature waves from a 1 ns pulse duration have a 1 T frequency f 1 GHz and have propagation speed c through a typical specimen of about 10 m s. Using the wave equation 6 gives a wavelength of 10 nm. Using equation 5 the wave number k 2 10 square root over i 2.22 10 1 i . Based on this the original temperature signal will decay to 1 e in approximately 10m. Depending on the sensitivity of the thermal array the specimen can have thickness s of up to 10 or 100 nm.

There is thus provided a method for non destructivity determining features embedded in a planar specimen which method is inexpensive requires minimal sample preparation can resolve differences in thermal properties e.g. thermal diffusivity which in some cases means resolving differences in material composition and can have a very low diffraction limit based on the laser pulse frequency because of the slow propagation speed.

It will be understood that many additional changes in the details materials steps and arrangement of parts which have been herein described and illustrated in order to explain the nature of the invention may be made by those skilled in the art within the principle and scope of the invention as expressed in the appended claims.

The foregoing description of the preferred embodiments of the invention has been presented for purposes of illustration and description only. It is not intended to be exhaustive nor to limit the invention to the precise form disclosed and obviously many modification and variations are possible in light of the above teaching. Such modifications and variations that may be apparent to a person skilled in the art are intended to be included within the scope of this invention as defined by the accompanying claims.

