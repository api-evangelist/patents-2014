---

title: Method and device for introducing human interactions in audio sequences
abstract: A method for combining first second audio tracks includes modifying at least one of the two audio tracks; and storing the first and the second audio track in a non-volatile medium, characterized in that the interbeat intervals of the modified first and the second audio track exhibit long-range cross-correlations (LRCC).
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09349362&OS=09349362&RS=09349362
owner: 
number: 09349362
owner_city: 
owner_country: 
publication_date: 20140613
---
The present invention relates to a method and device for introducing human interactions in audio sequences.

Post processing has become an integral part of professional music production. A song e.g. a pop or rock song or a film score is typically assembled from a multitude of different audio tracks representing musical instruments vocals or a software instruments. In audio engineering tracks are often combined where musicians have not actually played together. This may eventually be recognized by a listener.

It is therefore an object of the present invention to provide a method and a device for combining audio tracks where the result sounds like a simultaneous recording of the individual tracks even if they were recorded separately.

This object is achieved by a method and a device according to the independent claims. Advantageous embodiments are defined in the dependent claims.

According to the invention determining these characteristics of scale free fractal musical coupling in human play can be used to imitate the generic interaction between two musicians in arbitrary audio tracks comprising in particular electronically generated rhythms.

More particularly the interbeat intervals exhibit long range correlations LRC when one or more audio tracks are modified and the interbeat intervals exhibit long range cross correlations LRCC when two or more audio tracks are modified.

A time series contains LRC if its power spectral density PSD asymptotically decays in a power law p f 1 f for small frequencies f and 0

Long Range Cross Correlations LRCC between two sequences of interbeat intervals i.e. two non stationary time series exist if the covariance F s defined below asymptotically follows a power law F s s with 0.5

The presence of such cross correlations may be measured using a variant of detrended cross correlation analysis DCCA Podobnik B Stanley H 2008 Detrended Cross Correlation Analysis A New Method for Analyzing Two Nonstationary Time Series. Phys. Rev. Lett. 100 084102 . Global detrending with a polynomial of degree k may be added as an initial step prior to DCCA which has been shown crucial in analyzing slowly varying non stationary signals Podobnik B et al. 2009 Quantifying cross correlations using local and global detrending approaches. Eur. Phys. J. B 71 243 250. . In fact global detrending proved to be a crucial step to calculate the DCCA exponent of the non stationary time series of interbeat intervals analyzed by the inventors. Without global detrending much larger DCCA exponents are obtained i.e. spurious LRCC are detected that reflect global trends.

Given two time series X X where n 1 . . . N the DCCA method including prior global detrending thus consists of the following steps 

 1 Global detrending fitting a polynomial of degree k to Xand a polynomial to X where typically k 1 . . . 5. One may use k 3. It should carefully be checked that the obtained DCCA scaling exponents do not change significantly with k.

 3 Dividing the series into windows of size s 3 Least squares fit tilde over R and tilde over R for both time series in each window.

The invention may be embodied in a computer implemented method or a device for combining a first and a second audio track in a software plugin product e.g. for a digital audio workstation DAW that when executed implements a method according to the invention in an audio signal comprising one or more audio tracks obtained by a method according to the invention and or in a medium storing an audio signal according to the invention.

The procedure to introduce human like musical coupling in two audio tracks A and B is demonstrated using an instrumental version of the song Billie Jean by Michael Jackson. The song Billie Jean was chosen because drum and bass tracks consist of a simple rhythmic and melodic pattern that is repeated continuously throughout the entire song. This leads to a steady beat in drum and bass which is well suited to demonstrate their generic mutual interaction. For simplicity all instruments were merged into two tracks track A includes all drum and keyboard sounds while track B includes the bass.

In step the interbeat intervals of the first and the second audio track are determined. The interbeat intervals of tracks A and B read I X T and I Y T where T is the average interbeat interval given by the tempo here T 256 ms which corresponds to 234 beats per minute in the eighth notes . In case the audio tracks are MIDI files this may be done based on the note on messages. In other case known suitable beat detection procedures may be used.

If the time series Xand Yare long range cross correlated a musical coupling between drum and bass tracks is obtained.

In step the interbeat intervals of at least one of the first audio track A and the second audio track B are modified. Small deviations are added to the interbeat intervals in order to modify a long range cross correlation LRCC between the interbeat intervals of the first and the second audio track. More particularly the interbeat intervals are modified in order to induce LRCC between the interbeat intervals of the two audio tracks with a power law exponent also called DCCA exponent which measures the strength of the LRCC. For 0.5 there are no LRCC while the strength of the LRCC increases with .

More than two audio tracks can be modified by having each additional track responding to the average of all other tracks deviations.

In particular musical coupling between Xand Yis introduced using a two component Autoregressive Fractionally Integrated Moving Average ARFIMA process with 0.9 2 that generates two time series xwhich exhibit LRCC Podobnik B Stanley H 2008 Detrended Cross Correlation Analysis A New Method for Analyzing Two Nonstationary Time Series. Phys. Rev. Lett. 100 084102 Podobnik B Wang D Horvati D Grosse I Stanley H E 2010 Time lag cross correlations in collective phenomena Europhys. Lett. 90 68001 .

The standard deviation chosen for Xand Ywas 10 ms. The time series of deviations Xand Yfor musical coupling are shown in . The measured DCCA exponent reads 0.93 in agreement with the analytical value 0.9 within margins of error showing LRCC.

Introducing LRC in audio tracks is referred to as humanizing . For separately humanized sequences i.e. without adding cross correlations between the sequences however absence of LRCC is expectable. Indeed when humanizing the time series of interbeat intervals separately e.g. with an exponent 0.9 the detrended covariance of Xand Yoscillates around zero i.e. no LRCC are found.

Other processes than the ARFIMA process that generate LRCC can also be used to induce musical coupling. More particularly when two subjects A and B are synchronizing a rhythm each person attempts to partly compensate for the deviations d t tperceived between the two n th beats when generating the n 1 th beat. This is reflected by the following model referred to as the Mutually Interacting Complex Systems MICS model 1 where Cand Care Gaussian distributed 1 f noise time series with exponents 0

The deviations dwhich the musicians perceive and adapt to can be written as a sum over all previous interbeat intervals

A possible extension of the second model is to consider variable coupling strengths W W d . Since larger deviations are likely to be perceived more distinctly one possible scenario is to introduce couplings W that increase with d. For example W may increase when large deviations such as glitches are perceived.

The experimental setup comprises a keyboard connected to speakers and a recorder for recording notes played by test subjects and on the keyboard . Preferably the keyboard has a midi interface and the recording device records midi messages.

The performances were recorded at the Harvard University Studio for Electroacoustic Composition See Supporting Information for details on a Studiologic SL 88o keyboard yielding 57 time series of Musical Instrument Digital Interface MIDI recordings. However the results presented here apply not only to MIDI but also to acoustic recordings.

Each recording typically lasted 6 8 minutes and contained approx. 1000 beats per subject. The temporal occurrences t . . . tof the beats were extracted from the MIDI recordings and the interbeat intervals read I t. . . twith t 0. The subjects were asked to press a key with their index finger according to the following. Task type Ia Two subjects played beats in synchrony with one finger each. Ib Sequential recordings were made where subject B synchronized with prior recorded beats of subject A. Sequential recordings are widely used in professional studio recordings where typically the drummer is recorded first followed by layers of other instruments. Task type II One subject played beats in synchrony with one finger from each hand. Task type III One subject played beats with one finger finger tapping . Finger tapping of single subjects is well studied in literature Repp B H Su Y H 2013 Sensorimotor synchronization A review of recent research 2006 2012 . Psychon B Rev 20 403 452. and serves as a baseline whereas our focus is on synchronization between subjects. In addition to periodic tapping a 4 4 rhythm 1 2.5 3 4 where the second beat is replaced by an offbeat was used in tasks I III .

A comparison of the MICS model right panel with the experiments left panel shows excellent agreement. The vertex at the characteristic frequency fin the PSD is reproduced by the MICS model cf. .

The MICS model predicts emergence of LRCC . This MICS model also predicts that asymptotically the DFA scaling exponents of the interbeat intervals are determined by the clock with the strongest persistence max 1 2. This result is valid for long time series of length N 105 see . Surprisingly even when turning off say clock A i.e. 0 the long time behavior of both Iand Iis asymptotically given by the exponent of the long range correlated clock B and vice versa for large N. Thus the musician with the higher scaling exponent determines the partner s long term memory in the IBIs. However in experiments the exponents can differ significantly in shorter time series of length N 1000 which can be seen by comparing the PSD exponents in .

Evidence for LRCC between Iand Ion time scales up to the total recording time is reported in with DCCA exponent 0.69 0.05. The two subjects are rhythmically bound together on a time scale up to several minutes and the generation of the next beat of one subject depends on all previous beat intervals of both subjects in a scale free manner. LRCC were found in all performances of both laypeople and professionals when two subjects were synchronizing simple rhythms. Thus rhythmic interaction can be seen as a scale free process.

In contrast when a single subject is synchronizing his left and right hands tasks II no significant LRCC were observed suggesting that the interaction of two complex systems is a necessary prerequisite for rhythmic binding.

The inventor identified two distinct regions in the PSD of the interbeat intervals separated by a vertex of the curve at a characteristic frequency f 0.1 f see i The small frequency region asymptotically exhibits long range correlations. This region covers long periods of time up to the total recording time. ii The high frequency region exhibits short range anti correlations. This region translates to short time scales. These two regions were first described in single subjects finger tapping without a metronome Gilden D L Thornton T Mallon M W 1995 1 f noise in human cognition Science 267 1837 1839 . Because these two regions are observed in the entire data set i.e. in all 57 recorded time series across all tasks this suggests that these regions are persistent when musicians interact.

There is a fundamental difference between settings where individuals are provided with a metronome click e.g. over headphones while playing and where no metronome is present also referred to as self paced play that manifests in the PSD of the interbeat intervals.

For self paced play of musical rhythms the PSD of the interbeat intervals exhibits two distinct regions Hennig H et al. 2011 The Nature and Perception of Fluctuations in Human Musical Rhythms PLoS ONE 6 e26457 . Long range correlations are found asymptotically for small frequencies in the PSD. This region relates to correlations over long time scales of up to several minutes as long as the subject does not frequently lose rhythm . On the other hand for high frequencies in the PSD anti correlations are found.

In contrast a different situation is observed in presence of a metronome For play of both complex musical rhythms Hennig H Fleischmann R Geisel T 2012 Musical rhythms The science of being slightly off Physics Today 65 64 65. and finger tapping Repp B H Su Y H 2013 Sensorimotor synchronization A review of recent research 2006 2012 . Psychon B Rev 20 403 452. long range correlations were found in the time series of deviations of the beats from the metronome clicks. Below the difference between the deviations and the interbeat intervals in the PSD will be quantified. The deviations from the metronome clicks are defined as e t M where tis the temporal occurrence e.g. the onset of the n th beat M nT is the temporal occurrence of the n th metronome click and T is the time period between two consecutive metronome clicks. The interbeat intervals read

Hence the interbeat intervals are the derivative of the deviations except for a constant . In the following a relation is derived between the PSD exponents of eand I. Given a time series xwhere the PSD asymptotically decays in a power law 1 f with exponent . Let the time series dot over x x xdenote the derivative of x. Then it can be shown analytically that the PSD of the derivative time series dot over x asymptotically follows a power law with exponent 2 Beran J Statistics for long memory processes Chapman Hall CRC 1994 . Applying this general result to the present case one finds 2

When subjects are synchronizing beats with a metronome the time series of deviations exhibits long range correlations with PSD exponents reported in the range e 0.2 1.3 Hennig H Fleischmann R Geisel T 2012 Musical rhythms The science of being slightly off Physics Today 65 64 65. . Hence one may expect the PSD exponents for the time series of interbeat intervals in the range I e 2 1.8 0.7 . Thus the interbeat intervals are long range anti correlated for settings where a metronome is present. Humanizing a time series of deviations ewith an exponent 0

Different audio tracks are represented as channels and . For each channel the standard deviation of the timing error may be set. In addition the timing error for the spectrum of each channel may be set . Further the motor error standard deviation may also be adjusted for each channel. Finally the user may also set the coupling strength W for each channel. Given these data the software device calculates an offset. More than two channels can be modified by having each additional channel responding to the average of all other channels deviations.

Once the relevant parameters are set the plug in combines the audio tracks according to the previously described method.

