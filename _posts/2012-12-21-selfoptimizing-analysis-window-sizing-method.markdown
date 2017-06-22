---

title: Self-optimizing analysis window sizing method
abstract: A method of selecting an optimal window length in a digital processing system includes receiving a digital signal and analyzing the signal with a group of Hanning windows having different sizes. The windows being arranged so that they can be scaled to be comparable. The digital signal is windowed with each selected window and a transform is computed. The transformed signal is scaled and corrected. A metric is computed from the resulting signal for each window. The metrics are compared and the window size is selected based on agreement with a user defined metric. The specific window function, shift and scaling are such that the resulting analysis is mathematically equivalent across different window sizes.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08867862&OS=08867862&RS=08867862
owner: The United States of America as represented by the Secretary of the Navy
number: 08867862
owner_city: Washington
owner_country: US
publication_date: 20121221
---
The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties thereon or therefor.

The current invention relates to a method of signal analysis for signals of unknown duration or bandwidth.

The formation of overlapped Hanning weighted analysis windows is a very common first stage of processing in many time series analysis applications. The FFT typically follows the window analysis. This is the case for example in the short time Fourier transform STFT which is a widely used front end for a variety of applications including automatic speech recognition ASR . It is often necessary to arbitrarily choose an analysis window size that is a compromise between the desire for good time domain and frequency domain resolution. In order to handle a wide range of input time scales it is sometimes necessary to use multiple analysis window sizes in parallel. But this approach creates a new problem the resolution of ambiguous results. In other words one has to decide which FFT size is appropriate for a given input data record. A related technique is spectrogram combining where STFTs are combined in such a way that the choice of best FFT size is made at each grid point in the time and frequency plane. An important step toward solving the comparison problem is the assurance that the various SIFT representations are in some way equivalent . One possible definition of equivalent is the existence of an orthonormal linear transformation relating one analysis at a given window size to another at a different window size. This definition has relevance from a number of different viewpoints from linear subspace analysis to statistical methods including the PDF projection theorem. See The PDF Projection Theorem and the Class Specific Method IEEE Transactions on Signal Processing Vol. 51 No. 3 March 2003 . There is a trivial case where two analyses are related by a permutation and thus equivalent. Consider a time series where the total number of samples T is divisible by Nand N. If we analyze with a rectangular window function and use no overlap between processing windows the two analyses with window sizes Nand Nare permutations of the same input samples. Unfortunately when a non rectangular window function is used and the processing windows are overlapped there is in general no permutation or orthonormal transformation relating the two analyses.

Thus there is a need for a method that will allow comparisons between windowed data having different lengths when non rectangular window functions are used.

A first object of the invention is to determine the most appropriate analysis window sizes for an incoming signal.

Accordingly there is provided a method of selecting an optimal window length in a digital processing system includes receiving a digital signal and analyzing the signal with a group of Hanning windows having different sizes. The windows being arranged so that they can be scaled to be comparable. The digital signal is windowed with each selected window and a transform is computed. The transformed signal is scaled and corrected. A metric is computed from the resulting signal for each window. The metrics are compared and the window size is selected based on agreement with a user defined metric. The specific window function shift and scaling are such that the resulting analysis is mathematically equivalent across different window sizes.

Other objects and advantages of the present invention will become apparent from the following description drawings and claims.

The method of this invention is particularly designed for acoustic data however it can also be applied to other types of data such as that associated with seismic radar and radio signals.

The mathematics behind this method is given in the following text. Input data sample X has a length T such that X x x. . . x . Length T is given in a number of digital samples. It is desirable to analyze X into length N overlapped shaded windows. The windows are shifted by K samples at each update. D is the ratio of window size to time shift such that 

With T being a multiple of K and X being circularly indexed so that x x there will be exactly DT N processing windows. The length N processing windows are denoted by 2 where N is the window length and w w w. . . w is the window function. Y is the complete window analysis the concatenation of the various windowed analysis windows Y y y. . . y. The conversion from X to Y is a linear transformation that can be written as Y A X where A is a DT T matrix and Y is the length DT concatenation of the DT N window y.

Two critical properties occur when using the Hanning weight function. The Hanning weight function is given as 

The overlap add reconstruction of the input X is possible if the shifted window functions add to a constant. This means that the rows of matrix A must add to a constant. The sum of row i of A is 

By these principles there is a full rank orthonormal transformation Qthat allows transformation between the window analysis at Nand the window analysis at N. Mathematically this is given as 7 

As described above Nand Nmust both be divisible by D and D 3. The number of samples T must also be divisible by N D and N D.

Under the conditions given above the columns of A are orthonormal therefore 8 where I is the T T identity matrix. Equation 8 is a direct result of the fact that the row sums of A are constant and the sum of the squared row elements equal 1. Using the matrix form of the overlap add method X can be restored from Yusing 9 

Ycan be generated using 10 The matrix 11 is a DT DT linear transformation of rank T that converts from window analysis Yto Y so it is rank deficient. Note that Ais rank T. The missing rank can be restored using the orthogonal subspace of rank D 1 T. The extended DT DT matrix is 12 where is any DT D 1 T matrix of orthonormal columns spanning the subspace orthogonal to the columns of A. Since 13 then it follows that 14 

The Hanning D analyses can be viewed purely in terms of orthonormal matrices or rotations. A linear orthogonal transform such as the fast Fourier transform FFT discrete cosine transform DCT or discrete wavelet transform DWT can occur after this rotation. This transform isn t required to be the same in each branch and can also be implemented as an orthonormal matrix multiplication. Thus all points can be transformed by a series of coordinate system rotations.

A statistic is computed for each length Nin block . This statistic summarizes the useful information in the transform output bins. An example of a statistic is to compute the mean square bin amplitude and or to locate the largest bin amplitude. Because independent of the window size N there are the same number DT of total bins and because of the scaling in block the bins have the same statistics under noise only input. Therefore it is possible to create a statistic in block that has the same output statistics under noise only hypothesis no matter what the window size N. As provided above this statistic is comparable among the different windowing function lengths and transforms because of the windowing function parameters and the scaling. A preferred length Ncan then be selected from this statistic in block . This preferred length can be utilized either to give information about the signal such as pulse length or to select the best linear transform type and transform length for the given signal.

A first example of using this method is in detecting pulses of unknown duration. Searching for the optimal Fast Fourier Transform FFT size on a given digitized input signal is tantamount to pulse length estimation. This method was demonstrated utilizing synthetic data that consisted of 768 samples of independent identically distributed Gaussian noise plus a short Hanning weighted sinusoidal pulse of random frequency and starting time. The pulse length of the short pulse denoted by P was 96 192 or 384 samples. The signal to noise ratio was quite low and the pulse was difficult to find visually in the time series. In order to maintain detectability at short pulse lengths the amplitude was varied to the P dependent value 15Pat the peak of the Hanning shaped envelope.

The following procedure was performed to form a detection statistic that has identical noise only distribution independent from the analysis window size. A set of sizes was determined as being likely window sizes. These include the following number of samples N 72 96 144 192 288 384 576 768 . For each of these sizes a Hanning 3 analysis D 3 was performed. The fast Fourier transform of the analysis window is calculated for each number of samples. The resulting bins are scaled by

Once the exponentially distributed bins are computed for all the analysis windows for the chosen analysis window size N the exponentially distributed bins of all the analysis windows are combined into a vector w which will have a constant length of DT 2 regardless of N. In this example this results in 3 768 2 1152 exponentially distributed bins regardless of N. As a summarizing statistic the power law statistic is computed for each analysis window size according to 

Under the Hhypothesis the distribution of w does not depend significantly on N. It is always a set of DT 2 bins having standard exponential distribution with mean 1. There is however statistical dependence between bins that is imparted on w by the Hanning weighting but this is not important if the elements of w are treated as unordered. Under the Hhypothesis the distribution of the feature zmust be essentially independent of the number of samples N.

In the demonstration two hundred independent time series were produced at each pulse length. Each sample was analyzed with each analysis window size N and zwas evaluated. The pulse length estimate was arg max 16 In experiments it can be seen that most of the estimates are at or near the true pulse length while for noise only they are widely distributed.

The foregoing description of the preferred embodiments of the invention has been presented for purposes of illustration and description only. It is not intended to be exhaustive nor to limit the invention to the precise form disclosed and obviously many modifications and variations are possible in light of the above teaching. Such modifications and variations that may be apparent to a person skilled in the art are intended to be included within the scope of this invention as defined by the accompanying claims.

