---

title: Method and apparatus of highly linear optical modulation
abstract: In a new optical intensity modulator, a nonlinear change in refractive index is used to balance the nonlinearities in the optical transfer function in a way that leads to highly linear optical intensity modulation.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09329413&OS=09329413&RS=09329413
owner: Sandia Corporation
number: 09329413
owner_city: Albuquerque
owner_country: US
publication_date: 20140520
---
This application claims priority from U.S. Provisional Patent Application Ser. No. 61 825 442 filed May 20 2013.

This invention was developed under Contract DE AC04 94AL85000 between Sandia Corporation and the U.S. Department of Energy. The U.S. Government has certain rights in this invention.

The invention relates to photonic devices that perform modulation switching and filtering functions and the like through application of electro refractive effects.

Conventional lithium niobate optical intensity modulators are widely used not least because they have a relatively large optical bandwidth. The typical linearity of such a modulator is on the order of 122 dB in a 1 Hz bandwidth. There are specialized electro absorption modulators with better linearity than lithium niobate modulators but they generally suffer from a relatively narrow optical bandwidth. Thus there remains a need for modulators that offer the combined advantages of high linearity and high optical bandwidth.

We have provided a new highly linear carrier depletion optical modulator. The linearity of optical modulators particularly optical intensity modulators is a limiting factor in the dynamic range of radio signals sent over optical links. For a typical electro optic material the nonlinearity of the device is determined by the optical transfer function of the device. Here we present a modulator which uses a nonlinear change in refractive index to balance the nonlinearities in the optical transfer function in a way that forms a highly linear optical intensity modulator or optical phase modulator.

The invention offers the potential to significantly improve the linearity of radio over optical links. By having a highly linear modulator higher dynamic range signals can be sent and detected optically. This is an enabling factor for e.g. high performance analog optical systems such as optical analog to digital converters. The invention has applications in various fields including telecommunications data communications and RF photonics.

Previous efforts to make electro optic modulators more linear have relied on engineering of the junction optical transfer function. By contrast our new approach demands only judicious engineering of the optical mode overlap with the p n junction. Applications of our new approach can enable operation over a wider range of conditions with less susceptibility to fabrication imperfections.

An exemplary embodiment of our invention in one aspect is a method for operating an optical modulator of the kind that has a bias voltage and a bias phase as operational parameters. According to our method an operating point is selected that consists of a bias voltage paired with a bias phase wherein the selection is made from a parameter space of paired bias voltages and bias phases and wherein the selection is more particularly made from a region of the parameter space that is designated a low distortion region. The modulator is configured to operate at the selected operating point by setting a base value of the bias voltage and setting at least one other parameter independent of the bias voltage. Examples of such independent parameters are temperature and wavelength of the modulated optical beam.

An exemplary embodiment of our invention in a second aspect is an optical modulation apparatus. The apparatus includes at least one waveguiding path for an optical beam one or more p n junction regions traversed by the waveguiding path and an electrode arrangement for applying bias voltage across one or more of the p n junction regions. The apparatus further includes a control unit. The control unit is configured to select an operating point for the apparatus from a parameter space of paired bias voltages and bias phases wherein the selection is made from a region of the parameter space that is designated a low distortion region.

The magnitude of the electro optic coefficient for crystals exhibiting the Pockels effect is determined by crystal structure. Because silicon has a centrosymmetric crystalline structure it does not exhibit the Pockels effect.

However the effective index of refraction hereinafter index of a silicon optical waveguide can alternatively be modulated by manipulating carrier concentrations by application of a bias voltage. In such an approach the waveguide or a portion of it is made coextensive with at least a portion of a p n junction. A reverse bias applied to the p n junction creates a condition of carrier depletion that changes the index.

A further advantage of such an approach is that the magnitude of the effective index change as a function of the bias voltage for the silicon waveguide is not determined by crystal structure. Instead it can be engineered by control of dopant densities implant energies and waveguide design.

According to perturbation theory the change in effective index of a waveguide n due to the shift of a boundary by h is given by Eq. 1 .

where E is the spatial distribution of the electric field of the optical mode nis the group index of the waveguide mode E is the value of the electric field parallel to the boundary taken at the boundary is the difference in dielectric constant across the boundary D is value of the electric displacement field normal to the boundary taken at the boundary and h is the distance the boundary shifts. Since this line integral depends only upon waveguide geometry and p n junction shape it represents a constant for a given device geometry. Therefore Eq. 1 can be written in a simplified form as 2 

where r is an effective electro optic coefficient defined by Eq. 1 . Within a p n junction a depletion region exists whose width is given by

where is the material dielectric constant is the permittivity of free space q is the electron charge Nis the acceptor concentration Nis the donor concentration V is the applied reverse bias voltage and is the built in potential. Combining Eqs. 2 and 3 and absorbing the constants into the r coefficient we see that the perturbation in the effective index due to modulating the width of a depletion region in a p n junction is given by Eq. 4 . square root over square root over 4 

The quantity r in Eq. 4 is not simply a material parameter rather it depends on waveguide design dopant densities and the location and shape of the p n junction.

There is a striking difference between the form of Eq. 4 and the effective index shift for materials which exhibit an electro optic Pockels coefficient. Inspection of Eq. 4 will show that the index shift caused by carrier depletion modulation is effectively proportional to the square root of the applied voltage. Electro optic materials on the other hand exhibit a shift that is directly proportional to the applied voltage. As will be explained below this fact is central in explaining why carrier depletion modulators can produce highly linear intensity modulation whereas standard electro optic modulators do not.

We will now explain how the functional form for the effective index as a function of voltage as described by Eq. 4 can give rise to extraordinarily linear optical intensity modulators. Consider a Mach Zehnder modulator whose optical intensity transfer function as a function of applied RF voltage I V is given by a raised cosine 

where L is the active length of the modulator is the bias phase and Vis the RF modulating voltage. The effective index nis shown explicitly as functionally dependent on the RF modulating voltage. Note that this intensity modulation is the result of combining a phase modulator with a reference waveguide interferometrically.

Eq. 5 can be written as a Taylor series expansion to clarify the sources of intermodulation distortion 

The first order term in the Taylor series expansion is descriptive of idealized operation because it is directly proportional to the input modulating RF voltage. All of the higher order terms contribute undesirable distortion.

In general distortion terms which are proportional to even powers of V i.e. to terms of the form V where n is an integer are composed of frequencies that are even multiples of the modulation frequency . Those frequencies are out of band for suboctave RF systems and hence can be removed with filtering in either the optical or electrical domain.

It is significant in this regard that linear electro optic materials have an effective index shift that is proportional to the applied voltage. In other words for x 1 all derivatives

it is possible to completely suppress the IMD3 for a simple carrier depletion Mach Zehnder modulator.

In fact there is a continuum of bias phase bias voltage pairs that satisfy this condition. As a consequence a carrier depletion Mach Zehnder modulator can be designed in such a way that it is limited by fifth order and not by lower order intermodulation distortion.

In we have provided an illustrative plot derived from numerical simulations of a device whose operation is based on a silicon p n junction. In the figure we have plotted the bias phase required to completely suppress the IMD3 distortion for each of a continuous range of reverse bias voltages.

It should be noted in this regard that in an optical modulator the bias phase and the bias voltage can be independently controlled. For example the bias phase in an MZM is the phase difference between the two optical paths corresponding to the two interferometer arms of the MZM. This phase difference may be controlled through e.g. the thermo optic effect i.e. the thermal modulation of the refractive index by employing a heater that changes the temperature of one arm relative to the other. In other examples the bias phase may be controlled through chromatic dispersion by varying the wavelength of the modulated light. The bias voltage on the other hand is the voltage applied to the modulator p n junction and as such is directly controllable.

In an exemplary implementation of the principles described here a pair of values consisting of a bias voltage and a bias phase is selected thus defining an operating point for a given modulator. To provide operation with low distortion the operating point is selected from the points on or near a characteristic curve for the modulator that is similar to the curve of but of course particular to the given modulator.

In analog operation for example the selected value of the bias voltage provides a fixed dc offset value and the bias voltage is oscillated about that dc value to modulate an input light beam. For phase modulation this procedure may be performed in a single modulation element. For amplitude modulation this procedure may be performed e.g. in one or both interferometer arms of an MZI. For example it may be performed using a pair of complementarily driven modulation elements situated in respective arms of the MZI.

As will be understood by those skilled in the art the selection of an operating point might involve a tradeoff between modulation depth and distortion rejection. That is the optical power transfer function of e.g. an MZI amplitude modulator has a shape that is roughly speaking proportional to a squared sinusoidal function of the bias phase. For purposes of illustration we assume here that the transfer function is proportional to cos where is the bias phase. In that simplified example the greatest variation in the amount of extinction obtainable by oscillating the bias voltage will be achieved when the dc offset corresponds to a bias phase of 45 135 etc. or in other words 0.785 radians 2.356 radians etc.

It will be evident from the above example that the bias phase setting that provides the greatest extinction ratio will not necessarily be optimal. That is the bias voltage with which it is paired to define a low distortion operating point might be non optimal for extraneous reasons. Moreover as will be better understood by reference to and the following discussion the operating point defined by the bias phase setting that provides the greatest extinction ratio will generally differ from the operating point that achieves the least possible distortion. Hence it will generally be desirable to balance several factors in choosing the best operating point for a given application.

Turning now to it will be seen that we have there provided a contour plot that like was derived from numerical simulations. Plotted in is the spurious free dynamic range SFDR of the MZM of as a function of bias voltage and bias phase. The plot of is superposed on the contour plot with a change in shape due to the differences in scale between the two figures. The SFDR is defined relative to the fifth order distortion. It will be seen on inspection of the figure that for a bias phase of about 2 radians with a reverse bias voltage of 1.2 V a dynamic range of 140 dB Hzis theoretically achievable.

Analyses similar to that discussed above can be performed with similar indications for the suppression of IMD3 for alternative types of silicon carrier depletion modulators such as micro disk and micro ring resonator modulators. In such devices for example the waveguiding path that traverses one or more p n junction regions is provided by the optical mode confining structure of the resonator.

Accordingly it should be understood that the invention is not limited in scope to Mach Zehnder modulators but rather encompasses silicon optical modulators of all designs that can be adapted for carrier depletion operation. It should also be understood that although the illustrative Mach Zehnder modulator described here includes a respective modulator element in each of the interferometer arms alternative arrangements may omit the modulator element from one arm.

Signal generator provides the signal that drives the time varying component of the bias voltage and thereby modulates the optical beam. Control unit sets the heating current and or the bias voltage and it may have additional functions as will be explained below.

In one scenario for example the operator manually inputs the dc component of the bias voltage at port and the controller responds by automatically selecting a corresponding value of the modulator temperature or equivalently of the heater current . The selection of a corresponding temperature may be performed with reference to a distortion minimizing curve in parameter space such as the curve of . For example a look up table or other computer readable or electronically readable representation of such a curve may be stored in memory and accessed when needed by control unit .

Alternatively the operator might e.g. manually input a desired value of the modulator temperature to which the control unit would respond with an automatic selection of a corresponding dc value of the bias voltage.

In some possible implementations a feedback loop is used to optimize the parameter settings. In one illustrative scenario for example control unit directs signal generator to drive the modulator with a test waveform designed to provide a useful indication of harmonic distortion. The resulting output from detector is directed to analyzer which computes a measurement of the amount of distortion that is present. The distortion measurement is fed back as an error signal to control unit which in response varies the operational parameters according to an algorithm designed to seek an operating point that minimizes the error.

With further reference to it will be seen that the detected portion of the output optical beam from the modulator is transmitted by partially reflecting mirror whereas a main portion of the beam is directed downstream for transmission or further processing. It will be understood that the arrangement that is depicted is merely exemplary and that numerous alternative arrangements are possible without departing materially from the principles described here.

