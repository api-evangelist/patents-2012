---

title: True random number generator using GPU and signal processing techniques
abstract: A true random number generator (TRNG) uses sources of uncertainty found within graphics processing units (GPUs) together with signal processing techniques, for example histogram equalization, to obtain maximum entropy.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09459834&OS=09459834&RS=09459834
owner: 
number: 09459834
owner_city: 
owner_country: 
publication_date: 20120208
---
This application is a national phase filing of PCT CA2012 050069 and claims benefit under 35 U.S.C. 119 e of U.S. Provisional Application Ser. No. 61 440 492 filed Feb. 8 2011.

The present invention relates to a novel technique to implement a true random number generator TRNG using sources of uncertainty found within graphics processing units GPUs together with signal processing techniques for example histogram equalization to obtain maximum entropy.

Pseudo Random Number Generators PRNGs are widely used in a variety of applications such as encryption simulation gaming art and communications to name just a few examples. In some cases the quality of random numbers is of paramount importance. Under such conditions it is not advisable to use PRNGs. For such special cases another class of random number generators called True Random Number Generators TRNGs is frequently used.

The most commonly used random number generators are the PRNGs. A PRNG uses a deterministic system and an initial seed to reproduce the output sequence. Most common PRNGs are classified as congruential generators feedback shift register generators generators based on cellular automata and generators based on chaotic systems etc. Shannon s entropy of the output depends on the entropy of the seed and the entropy of the output can never exceed the entropy of the initial seed. PRNGs reproducibility is a great asset for simulation meanwhile entropy dependency and the seed selection become a great challenge for exploiting its parallelism and scalability.

TRNGs on the other hand are based on a non deterministic source such as radio noise radioactive decay thermal noise generated from a semiconductor diode thermal flow etc. Complex and slow methods have been implemented before based on user interaction or hardware events such as capturing keystrokes the mouse movement the hard drive seek times system activity and configuration or delays.

Overall TRNGs have various advantages over PRNGs. First the unpredictability of TRNGs offers better randomness. Second a TRNG lacks periodicity or data dependencies making it the best option for meeting the stringent requirement for communication and encryption. Although TRNGs have many advantages over PRNGs PRNGs are very popular due to their flexibility low cost and sometimes its generation time. In fact one of the main reasons why PRNGs are preferred over TRNGs is the implementation cost which for some TRNGs cases involves a huge initial investment.

The randomness of a TRNG output depends on a non deterministic source and its corresponding deterministic post processing step. In some cases the source of randomness does not produce random numbers according to the needs of the user. For this reason the post processing stage is used to modify the generated random numbers according to a specified distribution.

TRNGs can be subdivided into three phases. The first phase generates digitized analog signal DAS random numbers which are obtained from sources like random microcosmic processes i.e. the semiconductor thermal noise or the shot noise of a Zener diode and periodic digitization of the time continuous analog signal from the source. The second phase generates the internal random numbers which represent the DAS random numbers after being post processed to reduce its distribution weakness. The third phase is called external random numbers and it corresponds to the final result of the algorithm for extracting the random number. This approach has been adopted since 2001 by the German IT security certification authority BSI in its AIS 31 publication. In general a good post processing algorithm guarantees higher entropy than the entropy of the source as long as the source is probed to be independent.

Another way to generate random numbers is by combining several independent sources. The randomness and independence of these cumulative sources depends directly on the number of combined sources however some statistical defects might still be present which can be alleviated by the post processing phase. This allows the flexibility of verifying the entropy directly after the post processing phase leaving an open window to design any post processing algorithm.

It is well known that PRNGs fit most of the application needs however sometimes the generated numbers lack strong statistical properties. There are demanding situations where PRNGs are substituted by TRNGs such as generating cryptographic keys generating lists of lottery winner tickets or stochastic simulations. In these situations the use of PRNGs can become unreliable since its sequence becomes predictable due to its geometrical properties.

Extensive research has been done on PRNGs a good survey can be found in D. Knuth The Art of Computer Programming Addison Wesley Publishing Company 1998. Research for TRNGs has been concentrated on the development of better physical noise sources. TRNGs can be found in low cost semiconductors using digital design techniques that fit reconfigurable devices i.e. FPGAs CPLDs and microcontrollers . Multiple designs based on different sources of randomness and different techniques to generate the internal random numbers had been proposed in Berk Sunar William J. Martin Douglas R. Stinson A Provably Secure True Random Number Generator with Built In Tolerance to Active Attacks IEEE Transactions on Computers pp 109 119 January 2007. For instance some of them use the combination of analog and digital designs to generate and process white noise some other apply a simple architecture of stable states by recombining a large number of circuits.

Most of the existing approaches for parallelizing the random number generation are based on PRNGs by either batches or using texture memories found in GPUs architectures. New approaches had been explored by NVidia based on CUDA Compute Unified Device Architecture . In a recent study it was established that GPUs are highly efficient in parallel PRNGs when compared to CPUs. However all these approaches are based on the use of a PRNG. To the best of our knowledge the use of GPUs for TRNGs has not been documented before.

According to one aspect of the invention there is provided a method of generating random numbers comprising 

providing a general purpose computation device having a primary function other than random number generation 

Nowadays the use of General Purpose GPUs GPGPUs in high performance computing applications is becoming a very popular new field of applied research of high performance computing applications. GPUs have been shown to be very effective in data parallel problems. The present invention provides an opportunity to develop a TRNG that generates high quality random numbers in a scalable and economical design.

Preferably the general purpose computation device comprises a general purpose processing unit and said at least one non deterministic characteristic comprises a characteristic of the processing unit.

Preferably the general purpose computation device comprises an embedded system and said at least one non deterministic characteristic comprises a characteristic of the embedded system.

Preferably the general purpose computation device comprises a graphics processing unit and said at least one non deterministic characteristic comprises a characteristic of the graphics processing unit.

The non deterministic characteristic may comprise one or both of two independent characteristics which are 

When the processor comprises a graphics processing unit including a thermal control interface and an application programming interface preferably the temperature value is extracted by the application programming interface from the thermal control interface.

The post processing function may include performing data compression on the extracted random data according to the following function 10mod 1.0 

where tis the elapsed time of the group of possible race conditions and the first n decimal places are removed and the value is considered from that point to the right.

The post processing function may include performing data compression on the extracted random data according to the following function 10mod 1.0 

where tis the completion time for sampling and processing the temperature value and the first n decimal places are removed and the value is considered from that point to the right.

Preferably the method includes performing the post processing function on the extracted random number data such that statistical properties of the extracted random number data are improved using a statistical matching and normalization technique arranged for uniformly distributing gray level values in image processing.

According to a further aspect of the present invention there is provided a method of generating random numbers comprising 

performing a post processing function on the random number data using a statistical matching and normalization technique arranged for uniformly distributing gray level values in image processing.

A transformation function is preferably used to linearize a cumulative distribution function of the random number data along the value range.

The method preferably includes interpolating values within limits of a selected bin associated with the data and changing the value to be uniformly distributed along the bin when the same value is present in the bin.

The statistical matching and normalization technique may be selected from the group including histogram equalization and exact histogram equalization.

assigning a value to each group by interpolating values within limits of a bin associated with the data and changing the value to be uniformly distributed along the bin when the same value is present in the bin.

According to a further aspect of the present invention there is provided a method of generating random numbers comprising 

providing a source having at least one non deterministic characteristic extracting random number data from said at least one non deterministic characteristic of the source and

Various embodiments of the invention will now be described in conjunction with the accompanying drawings in which 

The present invention relates to a low cost effective and novel technique for designing a TRNG using sources of uncertainty in a GPU. For experiments a NVidia GeForce 9400M graphic card was used. It was also demonstrated that the present invention offers fast execution times and can be easily implemented on parallel architectures. The quality of the random number generator was tested by using statistical tests on the two proposed sources of uncertainties i threads race conditions and ii GPU core temperature.

Because of the more frequent use of GPUs in today s computational systems the present invention highlights the benefits of implementing a parallel and completely independent TRNG based on the GPU architecture. An easy and effective way to generate TRNGs is provided herein without compromising the importance of PRNGs.

As described further below the random numbers generated by the present invention have been evaluated using four tests. First we measure the correlation values between two sequences of random numbers second we measure the entropy values third we use watermarking an application used in network security and finally we use Monte Carlo analysis for pi value calculation. Based on these quality measurements our method has achieved better results than popular random number generators compared in this work. Furthermore this approach is a massively scalable solution ideal for high performance computing implementations.

As suggested by M. Hocko and T. Kalibera Reducing performance non determinism via cache aware page allocation strategies In Proceedings of the First Joint WOSP SIPEW international Conference on Performance Engineering San Jose Calif. USA. Jan. 28 30 2010 pages 223 234 sources of randomness can be found in most computational devices in the following three classifications 1 sources originating in the hardware like core temperature 2 sources originating from PRNG like a linear congruential RNG and 3 sources originating from very complex deterministic processes like page allocators or system schedulers or race conditions.

Therefore GPU programs are not the exception to non deterministic behavior during race conditions in which an unknown behavior is observed from multiple unsynchronized threads writing and reading from the same memory location 4 . During a race condition as mentioned in M. Boyer K. Skadron W. Weimer Automated dynamic analysis of CUDA programs In Third Workshop on SoftwareTools for MultiCore Systems 2008 a source of randomness can be obtained thus the measurement of the elapsed time of a group of possible race conditions can be a feasible and indirect measurement of this source of randomness.

Another non deterministic behavior present in all semiconductors is the core temperature change. It was observed that the temperature extracted from the NVIDIA Application Programming Interface NV API using the GPU thermal control interface follows a non deterministic behavior in the elapsed time of its calculation. One limitation is the accuracy cut off of the decimal part which shows a true random behavior. Additionally race conditions and thermal flow are also well known sources of randomness. Nevertheless to the best of our knowledge the use of the above mentioned random sources to extract true random numbers from GPUs has not been considered before. Our focus is then on these sources of randomness to generate true random numbers.

We analyzed two cases i the time measurement of a group of race conditions and ii the measurement of the time taken to sample the core temperature. These options appear inside the Digitized noise source in the general block diagram of the proposed random number generator in .

CUDA was designed by NVidia in 2006 to unify two different groups of processors and to optimize the power consumption CUDA contains an intelligent thread scheduler module which assigns the load to threads in a round robin fashion. This programming model called SIMT Single Instruction Multiple Threads executes the same instruction on all threads created for that process. However the scheduler is oblivious to the order in which the threads will finish their tasks. Even without this information the scheduler is able to predict and avoid race conditions for memory access beforehand by manipulating the order of instructions and introducing context switching among threads. In our case an interesting phenomenon was observed using the code described in in particular when the number of threads is 32n 1 the case of 129 threads or the variable SIZE 129.

Taking advantage of the speed of shared memory and its supported coherency model two vectors were defined in lines and where the vector size s is lower than the out vector with the purpose of introducing an unknown value X that will be propagated depending on the order that threads and finish.

In lines and the assignment to s id is not synchronized with the following reading instruction for s id 1 and its storage in out id in this case there will be occasions where out id will be id 1 but this is not guaranteed and the value is unknown since it is still being written or is about to be written by the thread id 1.

In the GeForce family line of products the NVidia core is provided with a diode as a built in temperature measurement device. It is well known that diode thermometers are used in temperature measurements due to their low cost stability of nearly 0.8 C for a range from 55 C to 150 C linearity simple circuitry and good sensitivity.

As the temperature changes in the diode the forward voltage across the p n junction changes linearly. This voltage is digitized and stored in a register which indirectly represents the core temperature. The time for retrieving the register by a call from the NV API behaves like a non deterministic process. In other core diode thermometers used in the GeForce family the registers access follows a round robin selection method such as in the ADT7473 diode. Therefore it can be identified that the measurement of the completion time for extracting the temperature value is the source of randomness.

By doing a simple inspection of the histograms of both suggested sources of randomness shown in no particular shape associated to a common probability distribution function is evident. It can be noted also that the numbers are concentrated within a small specific range thus a post processing stage is needed if random samples are needed that are distributed as a more common distribution such as the standard uniform.

For a better understanding of the post processing stage this stage is subdivided into three sections data compression mapping functions and statistical matching with normalization techniques. These sections are illustrated in . In the statistical matching stage two very well known image processing techniques histogram equalization and exact histogram equalization will be used to modify the random samples in such a way to obtain random samples with a uniform distribution. This in fact leads to maximum entropy as it will be explained in subsequent sections.

The first stage of the post processing algorithm is the data compression meaning that information will be encoded in smaller representation units. There are tradeoffs by applying data compression for example how the statistical weaknesses are masked and transformed into others meanwhile the entropy increases. In this sense the stage is implemented with the following equations 10mod 1.0 1 10mod 1.0 2 where the first n decimal places are removed and the value is considered from that point to the right trepresents the sequence of random numbers obtained from the race condition source and tfrom the temperature source. The modulus operation has a range on 0 1.0 .

For the second stage seven basic mapping functions were arbitrarily selected with the purpose of measuring their impact after the third stage. This includes addition subtraction multiplication exponentiation and modulus of two signals. The evaluated functions were f f 3 f f 4 mod 1.0 5 f ff 6 1 mod 1.0 7 1 mod 1.0 8 f f 9 

The third stage is the statistical matching with normalization techniques where histogram equalization and exact histogram equalization were used in order to obtain uniform distributed random numbers which at the same time offer maximum entropy.

Histogram equalization HE is a technique used in image processing that enhances the contrast of an image by guaranteeing a final image with a distribution of gray level values that resembles the uniform distribution as described in R. C. Gonzalez R. E. Woods Digital Image Processing 2nd Edition Prentice Hall 2002. HE is based on the following mathematical observations 

Given a discrete random variable X with the probability mass function p.m.f. or histogram 0 1 10 the cumulative distribution function c.d.f. or the accumulated normalized histogram is 

The HE technique suggests using a transformation function in the form of 12 where the transformation function will linearize the c.d.f. of x along the value range and then Y is supposed to have a uniform distribution. A slight modification is proposed since the distribution inside the bins needs to be preserved and not replaced by an integer value. The modification then consists on interpolating the value within the limits of the bin and in the only case where the same value is present in the bin this value is changed and uniformly distributed along the bin.

Although HE can be considered as one of the most popular approaches among the image enhancement techniques it can show spikes and gaps in the final uniform histogram. The second technique that will be evaluated then is Exact Histogram Equalization EHE that yields a final histogram that is completely flat without having the undesired effects mentioned above. Exact Histogram Equalization is described in D. Coltuc P. Bolon J. M. Chassery Exact histogram specification IEEE Transaction on Image Processing 15 5 pages 1143 1152 May 2006. The necessary steps to achieve these complete uniform histograms are 

3 A value is assigned to each group. Specifically in this step a similar interpolation as in HE is introduced in order to preserve the source distribution within the bin. The scheme of EHE yields the exact results since the dataset is transformed exactly into the desired distribution by fixing the bin elements count.

The evaluation is divided into four stages. The first stage evaluates the independence of the das random numbers and the post processing establishes that if the internal random numbers are independent from the noise source then the entropy can be evaluated after the post processing without compromising the statistical properties. The Pearson product moment correlation coefficient was used to measure the independence of the two random variables 

The second evaluation stage is based on measurements of the normalized entropy H as proposed in A. Kaufmann Introduction to the theory of fuzzy subsets New York Academic Pr vol. 1 1975 

The third stage consists of a proof of concept via an actual application of the random numbers generated by the proposed approach. The evaluation considers two methods for digital image watermarking i Least Significant Bit LSB modification as described in R. G. van Schyndel A. Z. Tirkel N. R. A. Mee and C. F. Osborne A Digital Watermark First IEEE Image Processing Conference Houston Tex. November 1994 vol II pages 86 90 and ii Discrete Cosine Transform DCT modification as described in C. Chan T. Chen and H. Hsia An Image Watermarking Scheme Using Pattern Coding Technique In Proceedings of the First international Conference on innovative Computing information and Control Volume 3 Aug. 30 Sep. 1 2006 ICICIC IEEE Computer Society Washington D.C. pages 467 470. In this stage for the case of LSB the image in was encoded with an image containing random numbers as the watermark shown in . For the DCT case a 64 byte key random numbers was encoded as the watermark in the image shown in . In the next step the encoded image was exposed to Gaussian noise 0 0.01 and salt and pepper noise density 0.05 . Finally the encoded image was decoded to retrieve the watermark.

Once decoded the Peak Signal to Noise Ratio PSNR was selected as a quality metric that shows how visible and robust the watermark is. In consequence the higher the PNSR value the better invisibility implying a closer resemblance between the reconstructed and the original watermark.

Consider Ias the original watermark for an 8 bit grey scale image of size mn or a 64 byte key. Iwill represent the reconstructed watermarked image or the reconstructed 64 byte key meanwhile the Mean Squared Error MSE is defined as 

In our case a minimum of 38 dB is expected for a decent invisibility. This was also compared to the evaluation of an image or a key of random numbers from the Mersenne Twister PRNG.

The fourth evaluation stage consists of another very well known application that uses random numbers the approximation of u using the Monte Carlo method. Consider a pair of random variables X Y U 0 1 i 1 . . . n and

where represents the cardinality of the set. Then an error estimator for z can be defined as z from the subtraction from the decimal representation of truncated to 50 decimal places z 

As it can be observed from Table 1 the independence of das random numbers and the first post processing stage was reliable for both random sources when the data compression was taken from 10 or n 1. But independency becomes poor after the data was compressed for 10. This can be related to how the data concentrates in a similar uniform shape in while in a poor concentration on the centers can be observed. Hence the signals that yielded the histograms in were not considered for further investigation.

Since it s only reliable to evaluate elements which are independent from the source the evaluation of the proposed functions and the statistical matching with normalization techniques was focused in data compression results from 10to 10only. This can be observed in Table 6. Also it can be noticed how the Exact Histogram Equalization improves the entropy tremendously so the highest value and a standard uniform distribution is achieved.

Based on the previous testing stage results only the random numbers obtained after the Exact Histogram Equalization was used as shown in Tables 2 through 5. It can be observed how the watermarking invisibility is better with the proposed TRNG key than when using the Mersenne Twister random number key. This result suggests that the use of the proposed TRNG can be applied for encryption of the watermarks even under noise attacks.

The results for this section show how the pi approximation yields better results when using the proposed TRNG as shown in Tables 7 9. Additionally the number of iterations needed to achieve better performance is smaller. As it can be observed the smaller error percentage occurs in f n 3 for 10000 iterations.

A novel technique for extracting and post processing random numbers using the GPU architecture has been presented showing the advantage of implementing a TRNG on GPUs as a scalable and inexpensive solution. A roadmap for analysis has also been discussed showing the benefits of applying data compression followed by exact histogram equalization to improve the statistical deficiencies of the TRNG. In this sense the TRNG was shown to have an excellent performance in security and privacy applications as well as in stochastic simulations leaving open for future research its optimization and the analysis of other noise sources in GPUs.

Since various modifications can be made in my invention as herein above described and many apparently widely different embodiments of same made within the spirit and scope of the claims without department from such spirit and scope it is intended that all matter contained in the accompanying specification shall be interpreted as illustrative only and not in a limiting sense.

