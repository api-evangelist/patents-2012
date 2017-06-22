---

title: Delay restricted channel estimation for multi-carrier systems
abstract: A method includes multiplying, at a device, a suppressed estimate of a channel by a first matrix to obtain a delay restricted estimate of the channel. The method also includes demodulating a signal received via the channel based at least in part on the delay restricted estimate of the channel.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08649254&OS=08649254&RS=08649254
owner: AT&T Intellectual Property I, L.P.
number: 08649254
owner_city: Atlanta
owner_country: US
publication_date: 20121001
---
The present application claims priority from and is a continuation of patent application Ser. No. 13 163 996 filed on Jun. 20 2011 now U.S. Pat. No. 8 305 874 and entitled DELAY RESTRICTED CHANNEL ESTIMATION FOR MULTI CARRIER SYSTEMS which is a continuation of patent application Ser. No. 12 467 764 filed on May 18 2009 now U.S. Pat. No. 7 986 614 and entitled DELAY RESTRICTED CHANNEL ESTIMATION FOR MULTI CARRIER SYSTEMS which is a continuation of patent application Ser. No. 11 046 192 filed on Jan. 28 2005 now U.S. Pat. No. 7 551 547 and entitled DELAY RESTRICTED CHANNEL ESTIMATION FOR MULTI CARRIER SYSTEMS the contents of which are expressly incorporated herein by reference in their entirety.

The present disclosure relates to methods and systems for channel estimation of multi carrier modulation transmissions.

In recent years Orthogonal Frequency Division Multiplexing OFDM has attracted attention as a candidate for high data rate video and multimedia communications. OFDM belongs to a family of transmission schemes called multi carrier modulation. Multi carrier modulation is based on dividing a given high bit rate data stream into several parallel low bit rate data streams and modulating each stream on separate sub carriers.

The motivation for using multi carrier modulation is to overcome the problem of inter symbol interference ISI . In wireless channels where radio signals from a transmitter traverse multiple paths to a receiver all the signal energy does not necessarily arrive at the receiver at the same instant of time. This phenomenon of dispersion in a communication channel causes energy from one symbol duration to spill into succeeding symbol durations.

When a time delay due to dispersion is either a significant fraction of or more than the symbol time duration the resultant ISI can be detrimental. ISI causes an irreducible error floor that cannot be overcome by simply changing a radio frequency RF parameter such as a transmit power an antenna pattern or a frequency plan.

In an OFDM system each sub carrier can be viewed as a flat fading channel. A single tap equalizer can be used to equalize the transmitted signal in case of coherent demodulation. This requires the receiver to have knowledge of the channel on a per sub carrier basis.

The discrete version of the OFDM baseband signal shown in equation 1 is identical to the Inverse Discrete Fourier Transform IDFT of the sub carrier symbols x. Thus OFDM modulation is essentially identical to an IDFT operation which may be performed using an Inverse Fast Fourier Transform IFFT . prior art is a block diagram of a baseband representation of an OFDM transmitter. The OFDM transmitter comprises a serial to parallel converter an IFFT processor and a parallel to serial converter .

The sub carrier data symbols can be estimated at a receiver by taking the Discrete Fourier Transform DFT such as a Fast Fourier Transform FFT of a received and equalized OFDM symbol using the following equation.

In a time dispersive channel such as one which introduces multipath fading the signal at the receiver can be written as a convolution of the transmitted signal y and the channel impulse response h. Thus the received signal rin the discrete time domain can be written as 

Even though the channel is time dispersive the effect of the channel can be visualized in the frequency domain i.e. after the DFT by a single multiplicative constant for each of the sub carriers. This results because a convolution operation in the time domain translates to a simple multiplication in the frequency domain. A single tap equalization using a zero forcing equalizer can be used to estimate the sub carrier signal using the following equation.

However in order to use equation 5 the receiver needs to know the channel response in the frequency domain i.e. the values of .

The channel response may be estimated either by embedding pilot symbols within data stream or by using preambles. The known pilot or preamble symbols are used to estimate the channel on the given sub carriers. To estimate the channel in other sub carriers a subsequent channel interpolation can be performed.

Existing channel estimation techniques include zero forcing and linear minimum mean square error LMMSE . Zero forcing channel estimation can be performed over known pilot and or preamble symbols by dividing the received symbol by the expected symbol.

A disadvantage of a zero forcing estimate is its unreliability in low signal to noise ratio SNR conditions. For example a zero forcing estimated channel response can be significantly inaccurate if some of the sub carriers experience a deep fade.

The LMMSE channel estimator is designed to minimize the mean square error between an estimated channel response and an actual channel response. For convenience in formulating the LMMSE estimator the relationship between received and transmitted symbols in the sub carriers carrying the pilot preamble is represented in the following vector form 

The LMMSE estimate circumflex over of the channel impulse response is determined by the following equation circumflex over 8 where A is an estimation matrix.

The estimation matrix A is determined by the following equation . 9 where R is the covariance matrix of the channel impulse response and is the covariance matrix of the noise vector and usually is a diagonal matrix.

In the absence of noise the covariance matrix is equal to a zero matrix. If the fading in the different sub carriers is independent the covariance matrix R of the channel impulse response is an identity matrix. Under both of these two conditions the LMMSE estimate is identical to the zero forcing estimate.

A drawback of the LMMSE channel estimation scheme is its requiring knowledge of the correlation between the fades of different sub carriers to form the covariance matrix R. In most practical systems this information is not known at the receiver a priori thus making the LMMSE estimator impractical.

Channel estimation and equalization are fundamental components of wireless communication systems especially those that have been designed to work in a non line of sight condition. In multi carrier systems such as OFDM equalization is relatively straightforward but sophisticated channel estimation and channel interpolation techniques are presently required.

In a particular embodiment a method includes performing a channel estimation to obtain an estimate of a channel based on a received signal. The method also includes suppressing a subset of elements of the estimate of the channel to obtain a suppressed estimate of the channel. The method further includes multiplying the suppressed estimate of the channel by a matrix to obtain a delay restricted estimate of the channel.

In another particular embodiment an apparatus includes a channel estimator configured to compute a channel estimate based on a received signal. The apparatus also includes a suppressor to suppress a subset of elements of the channel estimate to obtain a suppressed channel estimate of the channel. The suppressor is further configured to suppress a particular element by setting the particular element to zero. The apparatus further includes a multiplier configured to multiply the suppressed channel estimate by a matrix to obtain a delay restricted estimate of the channel.

In another particular embodiment a computer readable storage medium includes instructions that when executed by a processor cause the processor to perform a channel estimation to obtain an estimate of a channel based on a received signal. The instructions when executed by the processor also cause the processor to suppress a subset of elements of the estimate of the channel to obtain a suppressed estimate of the channel. The instructions when executed by the processor further cause the processor to multiply the suppressed estimate of the channel by a matrix to obtain a delay restricted estimate of the channel. The matrix is a unitary matrix obtained from a singular value decomposition of a Fourier transform matrix.

Existing frequency domain channel estimation schemes for OFDM do not incorporate information that the channel impulse response exists only over a finite number of samples in the time domain because the delay spread of the environment is finite and much smaller than the OFDM symbol duration. This assumption can be made since the delay spread of most environments is of the order of a few microseconds e.g. 15 20 microseconds in some environments. Thus in the time domain a span of channel impulse response is essentially limited.

Described herein are embodiments of delay restricted channel estimation methods and systems that take into account a finite spread of the channel impulse response in the time domain to improve the accuracy of channel estimation in the frequency domain. The new methods can be used for preamble based or pilot based channel estimation.

The disclosed methods provide channel estimates that are less susceptible to noise. As a benefit the disclosed methods also allow for estimation of a multi carrier noise variance estimation. Simulation results show a 2 dB improvement in the link performance by implementing a particular disclosed channel estimation method when compared to traditional channel estimation schemes such as zero forcing and LMMSE.

The delay restricted channel estimation can be based on a zero forcing estimate an LMMSE estimate or an alternative estimate with an additional constraint that the impulse response of the channel exists only over a finite and known interval of time.

A vector comprising the values from equation 4 is related to a DFT matrix F and a channel impulse response vector H by the following equation 

The DFT matrix F is an N L matrix of rank L where L is the number of taps over which the channel impulse response exists. A singular value decomposition of the DFT matrix F can be performed to determine a unitary transformation U and V such that 12 where is an N L diagonal matrix containing the singular values of F and U and V are N N and L L dimensional matrices respectively with unitary columns.

The matrices U and V can be viewed as unitary transformation operators in the frequency and time domains respectively. In particular the vector can be pre multiplied by U i.e. the complex conjugate transpose of U to form a transformed vector . The vector H can be pre multiplied by V i.e. the complex conjugate transpose of V to form a transformed vector . The relationship between and is represented by the following equation 13 

The unitary transformation U is used to modify a channel estimate such as either the zero forcing or the LMMSE channel estimate as follows. Once the estimate has been evaluated the elements for i L are suppressed to zero based on the form of given by equation 15 . The transformation U is used to transform back to in the frequency domain i.e. U is multiplied by to obtain a delay restricted estimate of .

To show the derivation both sides of equation 7 are multiplied by Uto transform the received symbol vector S the transmitted symbol matrix P the vector and the noise vector W. 16 

Thus equation 16 relates a transformed received symbol vector a transformed transmitted symbol matrix the transformed vector and the transformed noise vector according to the following equation. 17 

Since the transformation is unitary the covariance matrices of the noise vector W and the transformed noise vector are identical.

The delay restricted zero forcing channel estimate can be determined by i determining the transformed vector based on the equation 18 

 ii suppressing all but the first L elements in to zero and iii transforming back to using the following equation 19 

Similarly the delay restricted LMMSE channel estimate can be determined by i determining the transformed vector based on the equation 20 

 ii suppressing all but the first L elements in to zero and iii transforming back to using the following equation 21 

A traditional zero forcing channel estimate does not allow noise variation estimation to be performed. However by taking advantage of the finite spread of the channel impulse response in the time domain the delay restricted zero forcing channel estimate enables estimation of a noise variance. The estimate of noise is determined by subtracting the estimated signal from the received signal. 22 

This approach to noise variance estimation is unsuitable for the case of a traditional zero forcing estimate since a zero noise variance will result based on the definition of the zero forcing estimate.

As indicated by block the method comprises transforming the transmitted symbol matrix P based on the transformation matrix U. The transformed transmitted symbol matrix is equal to Umultiplied by P.

As indicated by block the method comprises transforming the received symbol vector S based on the transformation matrix U. The transformed received symbol vector is equal to Umultiplied by S.

As indicated by block the method comprises determining a transformed vector based on the transformed transmitted symbol matrix and the transformed received symbol vector . The transformed vector is determined using a channel estimation method such as zero forcing LMMSE or an alternative method. For zero forcing is determined using equation 18 for LMMSE is determined using equation 20 .

As indicated by block the method comprises suppressing all but the first L elements of the transformed vector to zero. Thus the first L elements i.e. elements . . . L of the transformed vector remain the same and the remaining elements i.e. elements L 1 L 2 . . . N are set to zero. It is noted that the scope of this disclosure includes variations wherein all elements after the Lelement are not suppressed exactly to zero but substantially to zero.

As indicated by block the method comprises inverse transforming the suppressed transformed vector based on the matrix U which is an inverse transformation of the matrix U to determine a delay restricted estimate of . The delay restricted estimate of is equal to U multiplied by see equations 19 and 21 . Although the L 1 to the Nelements in the transformed vector are zero the corresponding elements in are not necessarily zero. Moreover it is likely that all N elements of are non zero.

The method can be used to estimate the channel impulse response based on either pilots or preambles having symbol sub carrier combinations that are known a priori. show examples of pilots and preambles where symbol sub carrier combinations that are known a priori are shaded.

Simulations of the delay restricted channel estimation method were performed for an IEEE 802.16 d system. The IEEE 802.16 d system is a 256 sub carrier based OFDM system that has been designed to provide high data rate and high QoS for wireless broadband access.

A 3GPP based multipath channel TS 25.996 was used to simulate the effect of a wireless non line of sight non LOS channel on a baseband signal. At the receiver realistic channel estimation and frequency synchronization algorithms were used to keep the simulation close to real world performance of such systems.

The graphs show that the delay restricted channel estimation has improved throughput compared to conventional zero forcing channel estimation for QPSK 16 QAM and 64 QAM modulation. The overall performance of the system improves by about 2 dB by using the delay restricted channel estimation algorithm which implies that the system requires a signal to noise ratio SNR 2 dB lower than what would be required if this channel estimation algorithm was not used. A significant portion of the gain comes from more accurate channel estimation and significantly better noise variance estimation.

The herein disclosed delay restricted channel estimation method and system can be implemented in a fixed wireless access system. In one embodiment the fixed wireless access system is based on the WiMAX standard. This implementation would lead to an improvement in coverage and capacity in the fixed wireless access system.

The herein disclosed delay restricted channel estimation method and system can be implemented in mobile radio telephones e.g. cellular telephones and or mobile radio telephone base stations. In one embodiment the delay restricted channel estimation method and system are implemented by one or more integrated circuits for mobile telephones e.g. a mobile telephone chip set .

Generally the acts and components described herein can be implemented using a computer system. The computer system is directed by computer program code stored by a computer readable storage medium to perform the acts described.

It will be apparent to those skilled in the art that the disclosed embodiments may be modified in numerous ways and may assume many embodiments other than the particular forms specifically set out and described herein.

The above disclosed subject matter is to be considered illustrative and not restrictive and the appended claims are intended to cover all such modifications enhancements and other embodiments that fall within the true scope of the present invention. Thus to the maximum extent allowed by law the scope of the present invention is to be determined by the broadest permissible interpretation of the following claims and their equivalents and shall not be restricted or limited by the foregoing detailed description.

